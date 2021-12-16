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

Behind the scenes, enums get treated as integers when the code gets compiled. Theyre just _some value_, and their use is in how we use them.

> In fact, you can specify what the [underlying type](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/language-specification/enums) is. You can optimize your enums to be bytes, uints, longs, or whathaveyou. This is a rare use-case, don't worry about it.

## Enums In Action
One of the best ways to understand enums is to see how they are actually used. We used enums on our very first script, the roll-a-ball script. We specified the [ForceMode](https://docs.unity3d.com/ScriptReference/ForceMode.html) that the Rigidbody AddForce function used. ForceMode is just an enum, a set of named values we chose from. Making them an enum - giving the various values names - makes the AddForce functions much easier to use.

Other common enums built into Unity are [LoadSceneMode](https://docs.unity3d.com/ScriptReference/SceneManagement.LoadSceneMode.html), and Camera [Clear Flags](https://docs.unity3d.com/ScriptReference/CameraClearFlags.html).

They are often used for defining simple values.

## Enum Use Cases
I often find myself replacing booleans with enums. Often we think something will be a simple "on/off" toggle, but edge cases reveal themselves and things are more complicated. Do I keep adding booleans, or what's really going here - often an enum allows me to create an easily namable data type that fits its role well.

One of the best things about enums is how Unity treats them. Much like tags and layers, Unity will give you a drop-down list to choose from when you have an Enum.

I have used enums for simpler state-management cases. Each state gets an enum, and a variable of the type can only have one of value.