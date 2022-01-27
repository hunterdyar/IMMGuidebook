---
title: Follow-Along Project
draft: true
---

The following project is for students to follow along with and create a project with me, one that focuses on actually making an entire thing that has multiple levels and a game state.

[Playlist of videos](https://www.youtube.com/playlist?list=PLK7QSPwGqmFt6wA-jCUdawcYA1WYPZQ5p).

## Part 1
This part we think of our game, make a todo list, use Unity's tilemap system to create a level, and create a player movement system. We write our first recursive function, and we manage picking up items as we move. We also flounder about with particles.

{{< youtube XtRe7eF-cZU >}}

Additional Resources:
- [Unity Tilemap](https://docs.unity3d.com/Manual/class-Tilemap.html) in the manual.
- [Intro to Tilemaps](https://learn.unity.com/tutorial/introduction-to-tilemaps) at Unity Learn.
- [2D Tilemap asset workflow](https://blog.unity.com/technology/2d-tilemap-asset-workflow-from-image-to-level) on Unity's Blog.
- [A lightning round of great tips for 2D Games](https://blog.unity.com/technology/a-lightning-round-of-great-tips-for-2d-games) on Unity's blog.
- [Kanban plugin](http://matthewmeye.rs/obsidian-kanban/) for [Obsidian](https://obsidian.md/).
- [What on Earth is Recursion](https://www.youtube.com/watch?v=Mv9NEXX1VHc) video from Computerphile.
- [Programming Loops vs Recursion](https://www.youtube.com/watch?v=HXNhEYqFo0o) video from Computerphile. 
- [Physics2D.OverlapPoint](https://docs.unity3d.com/ScriptReference/Physics2D.OverlapPoint.html) in the Unity Scripting API.
- [Introduction to Particle Systems](https://learn.unity.com/tutorial/introduction-to-particle-systems) at Unity Learn.
- [Particle Systems](https://docs.unity3d.com/Manual/ParticleSystems.html) in the Unity Manual.

## Part 2
This is the real meat of this assignment, so to speak.

This part we create a game manager which keeps track of the state of the game, which other systems listen to. We make an interactable component that helps compartmentalize functionality (and a future use-case of OOP), We also set up a basic UI to demonstrate this things. I struggle with variable names.

{{< youtube 4puABQLJJMU >}}

**Notes:**
- I also said at the beginning that we would not use ScriptableObjects, but I changed my mind when I got to part 3. 
- I forgot to move all my code to it's own namespace(s), but we should do that.
In this part, I was wrong about the gear manager icon, and the reasons are interesting but [not really worth getting into right now.](https://stackoverflow.com/questions/48965981/special-icon-when-naming-a-monobehaviour-class-gamemanager).

**Additional Resources:**
- [Enums](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/enum) in the MSDN docs.
- [Enumerations](https://learn.unity.com/tutorial/enumerations#) at Unity Learn
- [C# Enumerations in Unity!](https://www.youtube.com/watch?v=L2E2aB1CMYw) Unity official beginner scripting tutorial.
- [FindObjectOfType](https://docs.unity3d.com/ScriptReference/Object.FindObjectOfType.html) in Unity Manual. (Note, the following line from this official documentation: *"Please note that this function is very slow. It is not recommended to use this function every frame. In most cases you can use the singleton pattern instead."*).
- [Working with UI in Unity](https://learn.unity.com/tutorial/working-with-ui-in-unity)



## Part 3
This part we create a Level manager, first explaining a prefab approach, and getting it completely working. Then changing it to a ScriptableObject approach. The last part of this is code-cleanup. If you are following along, be aware that I write and refactor code on this part, which is an honest explanation of how programming actually works - it's never really true that we just type everything right through from the start. 

After the level manager I even remembered to finish pickups.

Here we switch from 'we' to 'I', as the "follow-along" part is no longer required. I fixed a bug (the hard way) where you lose lives when you push a direction you can't move. After that I refactored the particle system to it's own script. I got confused about particle systems again, and stared at a working project thinking it might be broken. Apparently they do play On Enable if Play On Awake is selected.

{{< youtube OgcODNIQbi0 >}}

## Part 4
This video is less of a follow-along, but I took the less programming-centric parts of putting it together.

I use:
- Sprite Import Settings
- Sprite Sheets
- Unity's Animation system (Animator Controller and Animations)
- Cinemachine (with Impulse and Confiner2D controller)
- Turn the Main Menu into an actual menu screen.

{{< youtube 8FqGGiG71ys >}}

Additional Resources:
- [Aseprite](https://www.aseprite.org/)
