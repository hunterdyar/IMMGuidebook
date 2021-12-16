---
title: Enums
draft: true
---
# Enums
Enums are a simple and useful data type.

When we think about creating custom data structures in our own projects, enums are just the place to start. "List of options" is as simple a data structure as it gets, but it's incredible useful to have data that's simply named what it is.

Often we find ourselves needing to flag information, and we revert to using booleans or integers to represent things that are not inherently boolean or numeric. **Enumerations** are an excellent replacement for this situation. Enums, as we will call them, are distinct value types, where their value is one of a set of constants. The key: we can name them whatever we want.

{{< highlight csharp >}}
enum Color
{
    cyan,
    yellow,
    magenta,
    black
}
{{< /highlight>}}
{{< hint info >}}
You can write enums in their own files, just like classes. I often use enums as an 'embedded type', declaring it inside of a class, if more-or-less only that class will use the enum. In that case, you would access the enum from elsewhere with the same dot-access that you are used to: ClassName.EnumName.enumValue.
{{< /hint >}}

Behind the scenes, enums get treated as integers when the code gets compiled. Theyre just _some value_, and their use is in how we use them.

> In fact, you can specify what the [underlying type](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/language-specification/enums) is. You can optimize your enums to be any integral (whole number) type, like bytes, uints, longs, or short. This is a rare use-case, don't worry about it. It's good to know that there is an underlying type because you can cast your enum into numbers easily. You can control that and manually set the values that the enums get represented as. Doing this lets you compare enum properties by casting enums to enum, and they can be "greater/less than" or "odd/even" or "non-zero" and so on. Neat.

## Enums In Action
One of the best ways to understand enums is to see how they are actually used. We used enums on our very first script, the roll-a-ball script. We specified the [ForceMode](https://docs.unity3d.com/ScriptReference/ForceMode.html) that the Rigidbody AddForce function used. ForceMode is just an enum, a set of named values we chose from. Making them an enum - giving the various values names - makes the AddForce functions much easier to use.

Other common enums built into Unity are [LoadSceneMode](https://docs.unity3d.com/ScriptReference/SceneManagement.LoadSceneMode.html), and Camera [Clear Flags](https://docs.unity3d.com/ScriptReference/CameraClearFlags.html), and Input [KeyCode](https://docs.unity3d.com/ScriptReference/KeyCode.html)

They are often used for defining simple values where one chooses an item or behavior from a set of possible options.

## Enum Use Cases
I often find myself replacing booleans with enums. Often we think something will be a simple "on/off" toggle, but edge cases reveal themselves and things are more complicated. Do I keep adding booleans, or what's really going here - often an enum allows me to create an easily namable data type that fits its role well.

{{< highlight csharp >}}
public enum Suit
{
    hearts,
    diamonds,
    spades,
    clubs
}
{{< /highlight>}}

Consider the suit of a playing cards. You could store this as an integer, or even just a byte, but why not store it something that will be instantly and easily readable for what it is? Store it as a _suit_. It's a suit, so whats the perfect data type? Why not ... **Suit**. Make an enum and call it Suit, give it appropriate values, it's that easy.

## Enums in Unity
One of the best things about enums is how Unity treats them. Much like tags and layers, Unity will give you a drop-down list to choose from when you have an Enum.

![Image of an Enum DropDown in the unity inspector](/images/programming/enumDropDown.png)

## Enum Casting and Manual Value Settings
Enums can be cast to integer values, because they have an underlying integer type that stores them as such. See below for a mildly contrived example.

{{< highlight csharp >}}
public enum Suit
{
    hearts = 1,
    diamonds = 2,
    spades = -1,
    clubs = -2
}
public static bool IsRed(Suit suit)
{
    return ((int)(suit)) > 0;
}
{{< /highlight>}}