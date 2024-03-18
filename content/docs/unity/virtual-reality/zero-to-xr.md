---
title: Zero to Quest - Interaction Toolkit
---

 ## Unity Guide to Implementing XR Interaction Toolkit for Oculus Quest VR

### Introduction:
Welcome to the immersive world of Virtual Reality (VR) on the Oculus Quest headset! In this guide, we'll walk you through the process of implementing the XR Interaction Toolkit, a powerful framework for creating interactive and engaging VR experiences. By the end of this guide, you'll be ready to dive into the world of VR and start building your own interactive applications.


### Preface: Creating the game
1. Upon opening the Unity Hub click new project.

2. Select 3d and name your project.

3. Click Create Project.

### Section 1: Setting Up Your Development Environment
Before you can start implementing the XR Interaction Toolkit, make sure you have the necessary tools and software installed. Follow these steps:

 1. In Unity, go to "Edit" > "Project Settings" > "Player."

 2. Click on the Android button instead of the Windows tab which it starts on. 
 ![Android Settings](/images/unity/Zero-XR/Android.png)
 
 3. If the button for Android is not there, go to “File” > “Build Settings” and click “Install Android Modules” under the Android tab.

### Section 2: Installing XR Interaction Toolkit

Now that your development environment is set up, let's integrate the XR Interaction Toolkit:

Download XR Interaction Toolkit:

 1. Visit the Unity Package Manager (Window > Package Manager).
 
 2. In the top left corner switch from Packages: in project to Packages in Unity registry. 
 
 ![Installing XR Plugin Management](/images/unity/Zero-XR/Packagemanager.png)

 3. Search for "XR Interaction Toolkit" and click "Install."

 4. Under samples install sample assets. 
 

 ![XR Sample Assets](/images/unity/Zero-XR/SampleAssets.png)

#### Set Up Scene:

In the mid-top left corner hit the plus found under the word Hierarchy, select 3D object, and select plane, on the right side of the screen find the inspector tab and under Transform find the position slot and type 0 in all the position slots to center the plane in the scene.

Follow the same steps to make a cube. In the scale tab under the transform tab in the inspector, assign the values .3 to all slots. Then grabbing the green arrow pointing vertically, drag the cube above the plane. Also, drag it to one side of the plane so you can reach and grab it later.

Your scene should look like this now:
 ![Unity Scene](/images/unity/Zero-XR/Scene.png)
 
 #### Set Up Interactions:
1. Delete the Main Camera object.
 
2. In the mid-top left corner hit the plus and select XR

3. Add the "XROrgin(Vr)" prefab from the XR Interaction Toolkit to your scene.

4. Click the arrow on the left side of the screen that is on the XR Origin object, do the same to the Camera Offset, select the LeftHand and on the right side of the screen click the second to the right button that looks like two sliders and Select XRI Default Left Hand Interactions. Do the same but for the right hand, making sure to select the XRI Default RightHand Interactions.
 ![Build Settings](/images/unity/Zero-XR/BuildSetting.png)
 
 #### Implement Interactable Objects:
1. Select the Cube object.

2. Under the inspector select Add component.

3. Add the "XR Grab Interactable" component to these objects.

4. Select the options: smooth position on and smooth rotation on.

5. Switch the movement type to kinematic.  


 ![XR Grab Interactable](/images/unity/Zero-XR/XRGrab.png)
 
 ### Section 3: Configuring Locomotion
{{< youtube SfQS9lfRRm0 >}}

Now, let's configure how users will interact with the VR environment:
 
1. Select the XR Origin.

2. Add a component labeled locomotion system
In the slot labeled XR Origin (None) select the above xr origin and drag it into the slot.

Great! Now movement and turning can be handled a few different ways depending on what you want. 

1. Add a new component, either a snap turn provider (action-based) or a Continuous turn provider (action-based). 

These will dictate how you turn, by pushing the joystick to either side you will either instantly snap to a new position or smoothly rotate to be looking in a new direction, chose based on the feel of the game you are developing. 

2. Drag the Locomotion System component from above into the turn provider “system” slot.
Movement provider: Continuous movement provider (action-based) or a Teleportation provider.

3. Repeat the same steps with one of the following move providers.

Note: If using a teleportation provider you must make a cube, disable the mesh renderer, and apply the component teleportation area to it, the size of the cube is the area your player can move through.

 ![Locomotion1](/images/unity/Zero-XR/Locomotion1.png) ![Locomotion2](/images/unity/Zero-XR/Locomotion2.png)


### Section 4: Testing Your VR Experience

It's time to put on your Oculus Quest headset and test your interactive VR environment!

#### Connect Oculus Quest to Unity:
1. Enable Developer Mode on your Oculus Quest (follow Oculus documentation).

2. Connect your Oculus Quest to your computer with a USB C cable.

#### Build and Deploy:

1. In Unity, go to "File" > "Build Settings" and select your target platform as Oculus Quest.

2. Make sure the right scene is selected at the top of build settings, and that your headset is selected under the Run Device tab.

3. Click "Build and Run" to deploy your VR application to the Oculus Quest.

  ![Android Build Settings](/images/unity/Zero-XR/BuildAndroid.png)


### Enjoy Your VR Experience:

Put on your Oculus Quest headset and explore the interactive environment you've created.

Congratulations! You've successfully implemented the XR Interaction Toolkit for Oculus Quest VR. Now, let your creativity run wild as you continue to enhance and expand your VR experiences. Happy coding!
