---
title: Classes and Components
weight: 5
oldlink: https://guidebook.hdyar.com/docs/programming/fundamentals/classes-and-components/
---
# Classes and Components
Classes are the fundamental building blocks of programming. A class allows us to create instances of the class, called objects, which we ... do everything with.

Oddly enough, in Unity programming, we don't use classes that often. This is a lie. We use them in every single script we right, but we let **Unity** handle the creation and destruction of our classes for us. This is because most of our classes will be a unity component.

A basic Unity Script has the following line of code.
{{< highlight csharp>}}
public class AgentMovement : MonoBehaviour
{
    //everything goes in here
}
{{< /highlight >}}


When we create a component, we are creating a public **class** that extends "MonoBehaviour". We will learn more about extending classes and creating our own special classes in the future. Let's focus on components for now.

{{< youtube K--SiP8xM6I >}}
