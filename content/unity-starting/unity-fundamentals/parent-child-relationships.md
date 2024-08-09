---
title: Parent-Child Relationships
---
# Parent-Child relationships
One core concept to understand is that of 'parenting'. Parent/Child relationships are edited in the [hierarchy window]({{< ref "../unity-interface/hierarchy.md" >}}).

If we remember that scenes are cartesian coordinate systems, we can define any point as a point on the number line. It can be thought of as the distance away from the scene origin on each axis. We will use the words **scene** and **world** interchangeably when talking about parenting. Scene is a unity-specific term and world is generic term, in this context.

Rotation and scale can be thought of the same way. My orientation is defined as a rotation from a default orientation. The number of degrees around each axis. 0 degrees around every axis means the object has the same orientation as the world - up is up, right is right, etc.

Making an object a **child** of another object makes that object relative to the **parent** object, instead of the world.

This means the child's position is not defined as distance away from the world origin, but distance along each axis away from the parent. So if the parent moves, the child moves with it - it's distance away from it's parent is not changing, but it's position in 'world space' is. It's moving with the parent.

Same with rotation and scale. We scale a parent object up, all it's children should scale up with it.

When we talk about **local** and **world** space, we are talking about how the object relates itself to the Unity scene.

## Creating Parent/Child relationships in Unity
You create parent/child relationships by dragging and dropping GameObjects on each other in the Hierarchy window.

![Parenting objects in Unity by dragging/dropping them](/images/unity/fundamentals/parenting.gif)

## Make An Object Rotate around a point
To make an object rotate around something, make an empty gameObject at the position we want the object to rotate around. Let's call it "parent". Make the object we care about a child of this parent object, and position it how we want. Now simply rotate the parent object.

## Video Overview
{{< youtube rTFM__TzQsc >}}

## Hierarchy and Code

### Transforms Control Hierarchy
Transform component is the one that is in charge of parent/child relationships, in terms of underlying data structure. This is not obvious in the Unity editor, and it doesn't really need to be. When working in code, it's useful to know you can get an objects children, loop through the objects children as transforms, GetComponentInChildren<>(), and other such utilities that can take advantage of your object hierarchy. You can set an objects parent via the "transform.SetParent" function.

Just look at all the child-related functions in the [Unity Scripting API page for Transform](https://docs.unity3d.com/ScriptReference/Transform.html).

### Looping through Children

If you wanted to loop through all of the children objects of a child, you could do it easily with a for loop:
{{< highlight csharp >}}
for(int i = 0;i < transform.childCount;i++)
{
    Transform child = transform.GetChild(i);
    Debug.Log(child.gameObject.name+" is "+child.localPosition.magnitude + " units away from parent position.");
}
{{< /highlight>}}

But there is a niftier way to do this. You can plug transform into a foreach loop. When treated as a collection, a transform object can behave like a collection of it's child transforms. Neat!

{{< highlight csharp >}}
foreach (Transform child in transform)
{
    //code to execute for each child...

    Debug.Log(child.gameObject.name+" is "+child.localPosition.magnitude + " units away from parent position.");
}
{{< /highlight>}}

