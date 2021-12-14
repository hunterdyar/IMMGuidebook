---
title: Object Oriented Syntax
---
# Object-Oriented Syntax

## Declaring Classes
The syntax for declaring a class is as demonstrated:

{{< highlight csharp >}}
public class ClassName
{

}

public class ChildClassName : ParentClassName
{

}

{{< /highlight >}}

We almost always write one class per file. We tend to keep sibling classes as sibling files in our file structure, although this is not necessary. C# does not care where your files are located, so you have the freedom to organize them in a way that makes sense to you, your project, your team, and your source control system.

{{< hint warning >}}
It's not entirely true that C# doesn't care where our files are located. The exception comes with [assembly definitions](https://docs.unity3d.com/Manual/ScriptCompilationAssemblyDefinitionFiles.html).
{{< /hint >}}

## Overriding Members
The two keywords we care about are **virtual** and **override**.

### Virtual
The virtual keyword modifies a member of a base class. It allows it to be overridden by child classes. You can override methods,properties, indexers, and event declarations. Most of the time we use it on methods (aka functions).

The method being overridden cannot be private. How could it be overridden if the child classes cannot access it?

{{< highlight csharp >}}
public class ParentClassName
{
    public virtual void SomeFunction()
    {
        //stuff
    }
}
{{< /highlight >}}

### Override
The override keyword goes on a matching function on the children.

{{< highlight csharp >}}
public class ChildClassName : ParentClassName
{
    public override void SomeFunction()
    {
        //stuff
    }
}
{{< /highlight >}}

The function name, scope, and [method signature (properties)](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/methods#method-signatures) all must match the parent.

{{< hint info>}}
If you are coming to this page from the OOP intro lesson, you can turn back now.
{{< /hint >}}

## Hiding
### Hiding
Instead of overriding a function, the other option that a child class can take is to hide the base function. The [difference](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords) is important, but it is only evident when the class is used polymorphically. I want my students to default to always overriding the parent class.

For beginners still working to grasp polymorphism, code will behave more **consistently** and **predictably** if you default to using the override keyword. After we have been using polymorphic code for a while, we can come back and learn more about the differences between hiding and overriding functions.

### Hiding In A Nutshell
In many contexts, a hidden method and an overridden method will behave the same (executing the code in the child class), but in other contexts - dealing with polymorphism - they will not. For the curious, explore the above link and the docs on the [new](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/new-modifier) keyword.

The difference appears when we create child objects that are the parent type. _That sentence is only not gibberish because of polymorphism._

{{< highlight csharp >}}
ParentClassName someVariable = new ChildClassName();
{{< /highlight >}}

In this case, the someVariable will execute the the function declared on the child if it is overridden, but if said function is merely hidden, it will execute the parents code - because it is types as the parent type, it can directly "see" the "hidden" parent classes functions. 

## Event Functions
Whether you can hide or override them, Unity will still "find" the event function and the code should behave as expected - calling the child class functions. It will work.

In general, I recommend you attempt to avoid situations where you override or hide Unity Event functions (like start or update), generally by writing the main logic in their own functions, and use event functions where appropriate. Often, only a parent, or only a child will need event functions. 

{{< hint info >}}
For example, you can define the OnCollisionEnter function on the parent, and then have it call another function (TakeDamage, or whatever), and it's that function that gets overridden.
{{< /hint >}}

When I do use event functions in both parent and child classes, I prefer to set event functions as virtual and override them. I call the base class's function from the child basically every time I use an event function. 
{{< hint info >}}
While this is more syntax than simply typing "new", this forces me - when programming in the parent class - to understand that this function is getting overridden, as it has the virtual keyword. I prefer the extra verbose-ness as a bit of feedback, and I tend to make less mistakes when working this way.
{{< /hint >}}

{{< highlight csharp >}}
public class ParentClassName : MonoBehaviour
{
    protected override void Start()
    {
        //stuff
    }
}
public class ChildClassName : ParentClassName
{
    protected override void Start()
    {
        //Call whatever setup logic my parent class has.
        base.Start();
        //Then additional logic here
    }
}
{{< /highlight >}}