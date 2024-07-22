---
title: The Intro Lectures
weight: 1
---
# The Intro Lectures

These are recordings of in-class lectures I give about Unity. I hope most of this website will get to the point where Unity information is not hidden in these hour-long videos to reference, but It is still important for me to have the lectures proper recorded and online. They are not about a "easy win" or first "fun" project, and you won't necessarily have the confidence to _do_ much afterwards, but I am working on building out a solid foundation of knowledge to build on top of, so to speak.

The purpose is to give you the knowledge that makes teaching yourself Unity easier.

These are not lectures designed for video, they are designed for mostly-listening students who are clicking away in Unity while I talk. What's more: in video format I have expanded room for some more detail than I usually go over, as I don't spend time walking around the room and letting students practice. Thus: sorry about the long-winded and rambling nature (but not really).

If you don't know where to start, and are starting from scratch, you can start here.

## The Intro Lesson
{{< youtube Xau1z_Bzgk4 >}}

## The Roll-a-Ball Project
A slow introduction to writing your first component. Follow along with this one.

{{< youtube xPlMAMNgVW0 >}}

## Your First Assignment
The next step is to step away from long videos, and just poke around in Unity. Here is your first assignment: Make a level for your roll-a-ball.

Practice creating and moving GameObjects, manipulating the scene view, and creating assets (materials). Enter play mode and try rolling the ball through the level, then go back and change things. Try changing the balls mass, angular drag, or other physics settings.

## Parent-Child Relationships
Next, read [this page]({{< ref "parent-child-relationships.md" >}}) on Parent/Child relationships in Unity.

Before continuing, I also recommend reading overviews of some of the Unity windows the Unity Interface section.

## A Camera Follow Script
The next step, after we did the above assignment practice, is to create another script - a behavior that lets the camera object follow along with the player.

Programming and Game Design can be thought of as being two discreet roles. When we write our code, we are creating a set of tools with which we use to create the game. When we design the game, we use and manipulate these tools. This distinction may seem trivial when we are, alone, creating games (or whatever the project may be). It's important because it helps guide us to writing nice clean, reusable, editable code. Things that we might want to change - like the players movement speed - should be accessible in the Inspector, we should not have to go into code to change _design_ elements of the project.

{{< youtube pzTFJyW9ap8 >}}

Now we have created a nice, compartmentalized little script that we can use in many places that adds a simple behavior to whatever our GameObjects we want. A lot of Unity development is doing this. We create systems that exist without us having to go in and edit it. For example: Physics. You don't have to extend Unity classes to use the physics system. You just use the components, and use public functions (like "AddForce"). We should aim to create our systems with the same independent philosophy.

## Prefabs
Next, head over to [this page]({{< ref "prefabs.md" >}}) on Prefabs and watch the video there.

## Part 4
Part 4: GameObject properties, Instantiating Objects, The Unity Event System, Collision Events, Basic Loops, and some other miscellaneous things.

{{< youtube uQETtbRB-DA >}}

## Next Steps
That concludes the intro lectures! What's next?

Make a game, participate in a jam! Try one from scratch, discover what specific systems you need to learn, then spend time learning them. The next step is *your* next step, in whatever direction that leads you towards making the kinds of projects you are interested in making.

For programming, the next step is thinking through things like managers and how mechanics might connect to each other to make a game loop. I have a video series making [breakout](https://hdyar.com/blog/posts/breakout-followalong/) that I put together for this. Part 1 [here](https://www.youtube.com/watch?v=Gt3BagRGwoI).
