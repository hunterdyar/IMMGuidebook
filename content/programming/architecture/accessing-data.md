---
title: Accessing Data (from elsewhere)
---

# How to Access Data From Another Script in Unity

To access data that an object has, we need a reference to the appropriate instance of the object. The real challenge is, for the most part, getting the appropriate reference ("resolving" a "dependency"), and not actually accessing the data.

Also see: [Data-oriented design]({{< ref "/programming/architecture/data-oriented-design-scriptable-objects.md" >}}).

Also see: [Event Systems]({{< ref "/programming/architecture/event-systems.md" >}}).

## Public and Serialized Fields

The simplest, easiest, minimum-viable option is to make a public field. Then you just drag-and-drop the appropriate GameObject (with the component) or component into the slot. 

When you make a field public, or when you make it private with the [SerializeField] attribute (recommended), Unity gives you a little drag-and-drop-able slot you can manually assign your reference with.

public fields:
{{< highlight csharp >}}
public class Player : MonoBehaviour
{
    public float score;
}
public class ScoreManager : MonoBehaviour
{
    public Player player;
    
    void DisplayScore()
    {
        //...
        float playerScore = player.score;
    }
}

{{< /highlight >}}

Serialized fields:

{{< highlight csharp >}}

public class ScoreManager : MonoBehaviour
{
    [SerializeField] private Player player;
    //...
}

{{< /highlight >}}

Minimal setup, minimal overhead. Minimal setup has another positive, which is minimal refactoring when you want to replace it. It's Often the easiest solution to prototype with before replacing it with a more complicated solution later. 
However, you have to set it up in the Unity Editor. This means it doesn't work well when using it on objects that get instantiated _while_ the game is running, like enemies that spawn in, and may not work well for prefab workflows.

It also can mean lots of manual work, and it can be annoying to have your inspector be for _setup_ and not _configuration_. It's annoying to assign objects in the scene over and over again.

I highly recommend you use default to using the [SerializeField] attribute instead of simply making fields public, especially when working with data. If you try to access or read the field from another script, you should be aware that is what you are trying to do, and you can make it public then, if need be. This will save you from bugs and too-tightly-coupled code in the long run.

## FindObjectOfType
There are a number of different Find functions in Unity, all fairly notorious for being slow. You shouldn't use any of them in an Update loop. The only one I really recommend using is [FindObjectOfType](https://docs.unity3d.com/ScriptReference/Object.FindObjectOfType.html). It will search in the scene for the first active object it can find of a certain type. This is useful when you are sure there is only one object of a certain type.
{{< highlight csharp >}}

public class ScoreManager : MonoBehaviour
{
    private Player player;
    void Awake()
    {
        player = FindObjectOfType<Player>();
        if(player == null)
        {
            Debug.LogError("Player not found",gameObject);
        }
    }
}

{{< /highlight >}}

## Event Systems
Another clever way to resolve dependencies is to change how we think about them. Instead of being dependent on _objects_, we could be dependent on _the event we care about_. See [Event Systems]({{< ref "/programming/architecture/event-systems.md" >}}) for more about this pattern.

Often our dependency problems are caused by "[race conditions](https://en.wikipedia.org/wiki/Race_condition)" when we are loading scenes, especially when working with multiple scenes. One unexpected benefit of event systems can move a some of our trouble outside of the race, to when the data actually starts getting used. 

## ScriptableObjects
We can take the data we care about and move it outside of the entire scene loading game loop, and make it always exist in memory, and as an easily editable object in our file system that represents _data_. Sounds magical? We do this with a [data-oriented design]({{< ref "/programming/architecture/data-oriented-design-scriptable-objects.md" >}}) approach. See that page for more.

{{< highlight csharp >}}
public class FloatData : ScriptableObject
{
    public float value;
}
public class Player : MonoBehaviour
{
    [SerializeField] private FloatData playerScore;
    //update playerScore.value when appropriate.
}
public class ScoreManager : MonoBehaviour
{
    [SerializeField] private FloatData playerScore;
    void DisplayScore()
    {
        //...
        float playerScore = playerHealth.value;
    }
}
{{< /highlight >}}

Instead of one object being dependent on another, both objects are dependent on a third data-object. This is more dependencies, but the dependency on a scriptableObject is a less troublesome one because its always hanging out in our project's memory, regardless of what order objects are loaded in.

## Static Properties
Making the data we care about static takes it outside of the need for a dependency on a specific instance. This can be great, but it tends to become a pain in the butt once projects get more complex. It leads to taking shortcuts that are difficult to refactor, as well as not having the flexibility such that the refactoring is likely necessary.

Instead of having static data, one could have static instances... and now we are using a [singleton pattern]({{< ref "/programming/architecture/singleton-pattern.md" >}}).

See more about [static]({{< ref "/csharp/advanced/static-objects-and-unity.md" >}}) members.

{{< highlight csharp >}}
public class Player : MonoBehaviour
{
    public static float score;
}
public class ScoreManager : MonoBehaviour
{
    void DisplayScore()
    {
        //...
        float playerScore = Player.score;
    }
}
{{< /highlight >}}
