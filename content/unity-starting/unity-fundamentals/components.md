---
title: Components
weight: 5
oldlink: https://guidebook.hdyar.com/docs/unity/unity-fundamentals/components/
---
# What are Components?
Components are where the real functionality of GameObjects gets implemented.

The **[Transform](http://unity.hdyar.com/fundamentals/the-transform-component/)** [component](http://unity.hdyar.com/fundamentals/the-transform-component/) is part of every single [GameObject](http://unity.hdyar.com/fundamentals/what-are-gameobjects/) in Unity. You can’t delete it, because every gameObject **has** to have one. An Empty game object still has a position in the scene. It gives objects positions, rotations, and scales. It also handles how  objects can be “children” or “parents” of each other.

![Screenshot of Unity Main Camera](/images/unity/components/mainCamera.png)
*The Default Main Camera in new scenes have three components: Transform, Camera, and Audio Listener.*

####   Properties 

It’s important to understand the main feature that Components give us:  properties. Components add behavior and functionality to GameObjects. Properties makes this useful. We can edit many properties of any GameObject’s component. The position, rotation, and scale values in the Transform component are it’s *properties*. 

There are two types of properties: *Values* and *References.* Basically, properties are either:

- **Values**: Data. Numbers. Variables in a script. Any direct value such as booleans, colors, strings, numbers, vectors, and so on. 
- **References**: Telling us which *other* thing to use. Such as other GameObjects, other Components, or Assets.

For Example, the **audio source** component has a volume property, which is a number (a *value*) telling unity how loud to play the audio, but it also has an AudioClip property. This property is a *reference.* We point it to an audio file in our assets folder.

####   Editing Properties 

Many value properties are just numbers or letters, and editing them is as  simple as typing in whatever number we want. Some values, like colors,  would be annoying to edit as numbers (do you know the RGBa values for  all of the colors you want to use?). Unity gives us special editors for  many values. Colors, to continue the example, have a color picker that  will be familiar to you if you have used almost any graphics software.

For numerical properties, you can change the value by clicking and dragging left/right on the properties label. I find it especially useful to  click and drag on the “x”, “y” or “z” text to the left of the value in  the Transform component to quickly shuttle objects around the scene  without messing up my scene view.

![animated gif of clicking and dragging on labels](/images/unity/components/draggingLabel.gif)

*Clicking and dragging on labels can easily adjust numerical properties.*

Reference properties look like light grey rectangles and have a small circle to  the side of them. We can drag and drop files from our assets (ie: the  project window) into here to tell components what *thing* to use. Audio sources need to know what audio clip, sprite renderer’s need to  know what sprite to render, colliders often use physics materials, and  so on.



![Dragging an asset into a property](/images/unity/components/draggingAndDroppingAssetToProperty.gif)

*Dragging a Physics Material, from the Project  window, onto an appropriate property in the Inspector  window*

The little circle is the Object Picker, which basically lets us not have to drag and drop from  the project window, it opens a window with the possible things from our  game that the property could be referencing, and we can quickly select  them there without navigating around the project window.

![img](/images/unity/components/UsingTheQuickSelector.gif)

*Using the Object Picker to quickly grab the desired asset.*

Read about how to edit many types of properties in the [Unity Manual](https://docs.unity3d.com/Manual/EditingValueProperties.html).

####   Adding Components To GameObjects 

With a GameObject selected (Click on it in the Hierarchy or in the Scene  view), it’s components are available to be edited in the Inspector  Window. In the [Inspector window](http://unity.hdyar.com/interface/the-inspector/), there is an “Add Component” button at the bottom you can use.

![img](/images/unity/components/AddingAComponentInTheInspector.gif)

*Adding the rigidbody component to a gameObject in the inspector.*

Without using the inspector window, you can use the Component menu at the top  menu bar to add a component to a selected GameObject.

A third way to add components to a GameObject is with code. Components can be added and removed during a games run-time.

####   Making Our Own Components 

When we make a script for Unity, most of the time that script will behave as a component. In fact, all components are written in C#, and we can even look at their code. Neat!

####   Common Components 

Other fundamental components we will see in most 3D projects include: [Camera](http://unity.hdyar.com/fundamentals/camera-component/), Light, Mesh Filter, Mesh Renderer, Collider Components, and [Rigidbody](http://unity.hdyar.com/fundamentals/rigidbody-component/). 2D games can use components for 3D games, but there are also components specific to 2D. Sprite Renderer’s are one example. There are also 2D  versions of many components (for performance reasons).

Lets break down something fundamental into the components involved: A Cube.

![The Cube](/images/unity/components/theCube.png)

A cube has 3 Components.

- Mesh Filter
- Mesh Renderer
- Box Collider

You don’t need to worry about the **mesh filter**. It takes a mesh asset (the file on your computer) and make it usable by the mesh renderer. The specifics of this don’t matter to us. So much  that if you add a Mesh Renderer to a GameObject, Unity will  automatically add a mesh renderer.

The **Mesh Renderer** makes the mesh visible to the cameras. Look at it’s properties: Cast  Shadows (on/off), Recieve Shadows, Materials, light probes, and other  graphics jargon. All of it affects how the mesh is seen by the camera,  in the scene. Useful!

The third component is a **Box Collider**. This makes the cube *solid*. Without a collider, the box would just be visible, but unity’s physics  system would not be able to calculate if something is colliding with it  or not.
