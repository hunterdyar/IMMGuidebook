---
title: The Game View
oldlink: https://guidebook.hdyar.com/docs/unity/unity-interface/game-view/
---
# The Game View
The game view is where we run our games. See the unity manual on the [Game View](https://docs.unity3d.com/Manual/GameView.html).

First, our scene view camera and our game view camera are two completely separate things. The scene view, and its 'camera' that you control with the mouse, is an editor tool. The camera's location has no impact on the final, finished, game. The game view, then, allows us to see the games current *actual* state, how it will be rendered.

When you are in **play mode**, the game view is where we play and test the game. When we are not in play mode, we can get a preview of the active cameras current view, which is helpful for setting up the camera, UI, and other things. 

In the game view we get to see what actually happens in the game when we test it. It shows us what players will ultimately see.

It’s very important to know that while the game is running, **any changes we make will not be saved**.  At first, this can seem frustrating, but it’s for a good reason: The  game is running!

Players playing the game are also making changes to properties (like the position of a main character), and it would be  really annoying if we had to move them back to the start of a level  after every time we tested it.

Every beginner will start  adjusting settings and forget that Unity is “in play mode” (running the  game), and then they will lose their changes. It happens to all of us.  One way to help prevent this is with a play mode overlay tint.

## Unity Official video on the Game View
{{< youtube w7RLUM9TBXY>}} 
