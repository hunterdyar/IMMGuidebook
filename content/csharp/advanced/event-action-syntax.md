---
title: C# Actions & Event Syntax
oldlink: https://guidebook.hdyar.com/docs/programming/advanced/event-action-syntax/
---
# Event Syntax

## Types Of Events in Unity

There are a number of systems built into C# that can be used to create an event system. You have UnityEvents, Events, Delegates, Funcs, Actions, and more. 

The underlying principle is "How do we treat a function like a variable?" I.E.: How do we create a function call that we can change at runtime, pass around, and so forth? There are many C# features that deal with this kind of functionality. They are not overlapping ways to do events, but a set of foundational C# features. Creating an event system is just one thing we can use these features for.

There are ways to do event systems that are not entirelly via code, but can be manipulated via the editor. I prefer to use **Actions** for things that game designers shouldn't have to think about, systems that should "just work". 

> If you want events that are exposed to designers, look into **UnityEvents**, or into a ScriptableObject Event system, as described in [this talk](https://guidebook.hdyar.com/docs/programming/architecture/data-oriented-design-scriptable-objects/).
>
> If you're curious as to disambiguate between these various and overlapping features, check out [this video](https://www.youtube.com/watch?v=oc3sQamIh-Q) by Jason Weimann.

This page covers the syntax of using the C# feature of Actions.

## What Actions Do

Actions act as a **placeholder for function calls**. We create them like any variable. Then, we add any number of functions to that action, and then when we "invoke" the action, it calls all of the functions that have been added to it.

## Creating Actions

The syntax for declaring an event is just like creating any variable of type "Action".

 Then, with this variable, we call the "Invoke" function after checking that it is not null. Because this null check is so common, it's usually written with the [Null Conditional Operator](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/operators/member-access-operators#null-conditional-operators--and-). 

```c#
public class ClassName : MonoBehaviour
{

​	public Action OnSomeEvent;

​	void Start()
	{
	
    	OnSomeEvent?.Invoke();
	}

}
```

## Empty Actions

If an action has 0 functions added to it, invoking it will throw an error. This is appropriate - it should throw an error when we are trying to call a function on... nothing.

Because of how we tend to use Actions in Unity - as "optional events you can subscribe to or not", not having subscribers is often not considered an invalid state. So it's pretty standard to do a null-check on the action and just ignore it if it's empty.

We check for there being no subscribers by checking if the action is **null** or not:

```c#
if(someAction != null)
{
	someAction.Invoke();
}
//or
someAction?.Invoke();
```

## Subscribing To Actions

To subscribe to an Action, we use the plus operator, to add our function to the event. This is one of those bits of programming that makes more sense when spoken out loud than when we look at the code. It's just one of those quirks where the '+' operator isn't being used for mathematical addition (or '-' for subtraction), and probably one of the only times where we will write a function name without the parenthesis.

We must **remember to unsubscribe** from an action when we are done. This is an extremely common cause of bugs. **Especially when using static actions.** For example, we may deactivate a gameObject, expecting it to not do anything - but it may still receive actions. C# actions don't "know" about Unity active states. Even though an object is disabled, it will still get an action.

It's considered best practice to subscribe to an Action in OnEnable and unsubscribe in OnDisable. If you just follow this pattern of subscribing in OnEnable and unsubscribing in OnDisable, life will be easier.

```C#
public class Broadcaster : MonoBehaviour
{
    //Invoke this at some appropriate time.
	public Action someAction;
}

public class Listener : MonoBehaviour 
{
    public Broadcaster broadcaster;
    
	void OnEnable()
    {
        broadcaster.someAction += MyFunction;
    }
    
    void OnDisable()
    {
        broadcaster.someAction -= MyFunction;
    }
    
    void MyFunction()
    {
        //do something when someAction gets invoked.
    }
}
```

## Static Events

One of the most useful uses of Actions is to clean up dependencies and reference-spaghett--nightmares in Unity scenes. This often means making our actions static. [Static Objects and Unity]({{< ref "/csharp/advanced/static-objects-and-unity.md">}}).

```c#
public class GameManager : MonoBehaviour
{
	public static Action OnGameOver;
	
	public void PlayerDied()
	{
		OnGameOver?.Invoke();
	}
}

public class UIManager : MonoBehaviour
{
    //Note that this class does not need a reference to the GameManager in the scene.
    //In fact, there doesn't even need to be a GameManager instance in the scene, we can always just subscribe to, and invoke, the public static action.
    
    void OnEnable()
    {
        GameManager.OnGameOver += DisplayGameOverPanel;
    }
    void OnDisable()
    {
        GameManager.OnGameOver -= DisplayGameOverPanel;
    }
    private void DisplayGameOverPanel()
    {
        //etc.
    }
}
```

## Usage Notes

When using Public Static actions, remember that we don't have an ability to make "subscribe only" actions. Any class anywhere could call the action. Often we would want to limit our actions to an appropriate scope, so keep this in mind. 

It's considered good practice to add a <Summary> [comment](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/xmldoc/) tag above an action that briefly explains what calls it. This way, in our IDE, we can quickly remember when/who calls an action, and make clarifications.

```C#
///<Summary>
/// Called by the game manager when the player dies or loses a life. This event is still called before the gameOver event when the player loses their last life.
///</Summary>
public static Action OnPlayerDeath;
```

---

## Review Videos

{{< youtube GUTURxgcoj4 >}}

Practical Application:

{{< youtube VeHr3MK7lCc >}}

