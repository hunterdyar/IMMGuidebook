---
title: Timers
---
# Considerations and Strategies for Timers

First, I will discuss the thought process for deciding how to implement timers. If you just want the example code, scroll down.

## Considerations for Timers
The rules of thumb are to keep the timer implementation as simple as possible - and no simpler; and to keep the logic as "close" to the action as possible. In other words, let gameObjects be responsible for themselve

### Ownership
Timers are a tricky subjet in Unity development, but can be tricky to get right. The hardest part of timers isn't implementing the logic of them, but - in my experience - determining which object should be responsible for the timer.

In general, you want things to be responsible for themselves. If you have a missile that explodes after a certain amount of time, a player that has a cooldown between attacks, or a tool that recharges, then these objects should own their own timer.

This can get undweildy if you have hundreds of items all connected to the same underlying system. If you many systems that use one timer (like a farming game), or many systems that deal with a single timer (like a racecar countdown), you may want to move the timer into it's own manager.


### Fixed or Variable Length
Can a timer be stopped? Paused? Can something add to it while it is running? Can it be 'sped up' with a powerup or ability - attack cooldown timers can get complicated in these cases, and we will be hamstrung if we implement it in a way that isn't amenable to the complexity of the system.

For fixed timers, without a lot of itneruption, I prefer a simple float variable that we change in update. For timers with lots of complications, I prefer a coroutine, with it's own yield loop that can check all of the different conditions we care about. The later solution is far too complicated for most cases, so starting with a float and refactoring it to a coroutine later is the way to go, as a rule of thumb.

### Interuptions
Consider what happens when gameObjects get destroyed. Would we start getting Null Reference exceptions? So wrap everything in null checks? Gross. If you have a coroutine timer, be careful if it references objects beyond itself. Further, try to ensure that an object that started the coroutine (called the StartCoroutine function) is the one being referenced by it. If an object gets destroyed, its coroutines will safely die. But coroutines elsewhere won't.

This is why I don't like using [Invoke](https://docs.unity3d.com/ScriptReference/MonoBehaviour.Invoke.html). While the same rules as coroutines apply, it feels so magical and hands-off that I find it difficult to debug. There's nowhere to put a break point and check on it's status.

### Games with Clocks
Consdider a farming game or economy sim. In these cases you would want one master clock that can manage the movement of time, and implement a "void Tick(float delta){}" function of our own on every thing that progresses over time.
Sort of like having Update and Time.deltaTime, but our manager would have total control over it.

The manager can broadcast an action that every plant, farmer, tool recharge, and economy can listen to and implement it's own logic itself. The player can pause or speed-up the game with a single source of truth. Everything implementing the logic just gets told how much time has passed since the last tick.

### Controlling the Time
In games like Minecraft, the player presses and holds a button against an object to start mining/digging/using/etc that item. For a system like this, the item doesn't tick from Update, but from some InteractionTick(float delta) function. The player initiates the timer, but the timer itself should be owned and managed by the object in question.

Otherwise, they work the same as all the other timers, logically.

### A Timer Class
One elegant solution is to create a single timer class that listens to all the appropriate functions.

## Strategies for Implementing Timers

### Time Dot DeltaTime
Unity provides a static variable called 'deltaTime'. [Delta](https://en.wikipedia.org/wiki/Delta_(letter)) comes from the symbol used in sciences to commonly refer to "a change in" or "difference". This stores the amount of time in seconds that has passed since the previous frame. In other words, the time since the last Update() function was called. If the game is running at 60fps, it will be about 1/60th. If we increment a variable by this number every Update, that number will get larger at a rate of 1 unit per second. A timer!

### Time Dot Time
Besides deltaTIme, where we consider and measure changes; we could also just store the [time](https://docs.unity3d.com/Manual/TimeFrameManagement.html). Time.time is the amount of seconds since the game began. We can store it, but then add a certain number of seconds to it. When Time.time is larger than this variable, that many seconds have passed. This method may be less code - and more efficient - than incrementing a number every frame, but it comes with some drawbacks: Control. It's hard to pause, hard to change the timer while it runs, hard to speed up or slow down the clock, and hard to debug or get progress. It's advantages are that it is extremely simple.

### A Timer Float
This example is to trigger something every x seconds, but can easily be modified to fit your needs.

The simplest and one of the most robust ways to implement a timer (read: good enough in many cases) is to just use a float variable. It can count up or down, whatever is easier to debug or matches more closely with the model of the data in question. I prefer timers that count down, since "is less than zero" just reads as a "time up" to me when I am looking at code.

{{< highlight csharp >}}
float timer;
float maxTime;

void Start()
{
    //reset the timer. Set it to 0 to have it fire instantly.
    timer = maxTime;    
}
void Update()
{
    //timer logic
    timer -= Time.deltaTime;
    if(timer <= 0)
    {
        timer = maxTime;//reset the timer.
        DoAction();
    }
}
void DoAction()
{
    Debug.Log("Time up");    
}
{{< /highlight >}}

The biggest gotcha is resetting the timer. Since many different functions in a MonoBehaviour can change the timer, we want to be very careful about when we set and reset it.

### A Timer Float: Refactored
Some improvements I might choose to implement:
- Wrapping this "timer = startTime;" logic in a "ResetTimer()" function can make debugging easier.
- Wrapping the timer in a timerTick function also makes debugging easier, and keeps the Update loop clean, as there is likely other complex logic going on in Update. I use the word 'Tick' to refer to functions I expect to be called by Update.
- Trivially, we can use a bool as a local pause without changing the timers value. 
- We can add a modifier to the Time.deltaTime amount to contorl the speed the timer runs.
- We can be clear about functionality with better names and comments/tooltips.

These changes might give us the following:

{{< highlight csharp >}}
//This is inside of a MonoBehaviour.

[Tooltip("once per this many seconds, action will happen.")]
public float ActionFrequency;
[Tooltip("1 is no modifier. 2 is double speed, 0 is paused, etc.")]
public float Modifier = 1;
public bool TimerIsActive = true;

//internal control variable.
private float _timer;

void Start()
{
      ResetTimer();  
}
void ResetTimer()
{
    //reset the timer. Set it to 0 to have it fire instantly.
    _timer = ActionFrequency;
    TimerIsActive = true;//you may
}
void Update()
{
    TimerTick()
}
void TimerTick()
{
    //we can return out of this function without skipping the rest of whatever else we have going on in Update.
    if(!TimerIsActive){
        return;
    }
    //timer logic
    timer -= Time.deltaTime * modifier;
    if(_timer <= 0)
    {
        //Note that these two functions stay separate. We don't want timer control muddled up with output.
        ResetTimer();
        DoAction();
    }
}
//Doing the... whatever... is completely separate from the timer control. This is good!
void DoAction()
{
    Debug.Log("Time up");
    
}
{{< /highlight >}}

### Coroutines For Timers

A coroutine is a way to have functions run outside of the regular Unity Game Loop. They are a way to have a function that can pause it's execution while waiting for something else. We call this pausing 'yielding', and the something else is usually controlled by Unity's ggame loop. Often we talk about coroutines as if they are like a separate thread, but they are in the same thread as everything else.

> Coroutines will get stopped if the GameObject that started them is destroyed or disabled, but they *won't* get stopped if the MonoBehaviour that started them is only disabled. This can be a cause of bugs when using coroutines. GameObjects are disabled with the gameObject.SetActive(false); function, while MonoBehaviours use the .enabled = false; variable.

Coroutines have a unique syntax, so they can feel confusing and unfamiliar. See [the page on coroutines]({{< ref "../advanced/coroutines.md" >}}) for a deeper dive and videos on the topic.

Here is the simplest setup, a function that starts a coroutine using the StartCoroutine function provided by Unity.
The "yield return new WaitForSeconds" is the secret sauce. The yield command returns to the game loop an object that tells it when to resume execution of the coroutine. We can take an educated guess at what "WaitForSeconds" waits for, but the other yield commands are not as obvious.

#### Simple Time Delay Coroutine

{{< highlight csharp >}}
//inside a MonoBehaviour.

void BeginTrigger()
{
    StartCoroutine(DelayThenActionRoutine(2));
}

IEnumerator DelayThenActionRoutine(float secondsToWait)
{
    yield return new WaitForSeconds(secondsToWait);
    Debug.Log("Action!");
}
{{< /highlight >}}

#### Coroutine For Repetition

{{< highlight csharp >}}
//inside a MonoBehaviour.

private Coroutine _repeatingRoutine;

void BeginRepetition()
{
    _repeatingRoutine = StartCoroutine(RepeatActionRoutine(2));
}

void StopRepetition()
{
    if(_repeatingRoutine != null)
    {
        StopCoroutine(_repeatingRoutine);
    }
}

IEnumerator RepeatActionRoutine(float secondsToWait)
{
    bool repeat = true;
    while(repeat)
    {
        yield return new WaitForSeconds(secondsToWait);
        Debug.Log("Action!");//presumably you would replace this with your important code.
    }
}
{{< /highlight >}}

For this example, the coroutine will last forever... Well, until this GameObject is destroyed or deactivated. a while(true) loop is usually a recipe for disaster. One way to be able to stop the coroutine is to move the repeat variable out to the monoBehaviour, and set it to false. This is easy enough, but I find changing a boolean to be an unsatisfying way to say "stop". Will it last go more time before actually stopping? (in the above example, it likely will! We could move the yield code to after the action as a fix).

> If it gets deactivated and reactivated, the routine may need to be restarted in OnEnable()

The solution is to store a Coroutine object, which can reference a coroutine. We can use this in Unity's StopCoroutine function, which is clear, readable, and immedeate. The only gotcha is to do a null-check, if we stop the routine before assigning that variable (ie: before starting it), that will throw an error.
