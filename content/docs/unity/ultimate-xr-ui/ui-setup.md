---
title: UltimateXR UI Options
draft: false
---
{{< hint info >}}
*This is a general overview of the UXR related UI menu, input, and setup. For more in-depth information about the components or questions go the [UXR Website UI Interaction Page](https://www.ultimatexr.io/guides/ui-interaction) for reference.*
{{< /hint >}}

There are two options available when interacting with UI options in UXR. That is the **UXRFingerTip** and **UXRLaserPointer**. 

## Set-up
Setting up your UI with UXR is fairly simple. The first thing you need to do is add a Unity Event system to your scene by going to *GameObject --> UI --> EventSystem*.  

![Adding Event System](/images/unity/ultimate-xr/adding-event-system.png)  

Once you have your event system added to the scene, add the UXR Pointer Input Module component. The good thing about this component, is that when you hit play mode, any canvas that works in World Mode will automatically have the UXR Canvas components added to it.  

![World Mode Canvas](/images/unity/ultimate-xr/world-mode.png)  
![Component Canvas Adding](/images/unity/ultimate-xr/component-canvas.png)  

Otherwise, you will manually add the UXRCanvas component. 

# Avatar Setup

## UXR Avatar
The UXR Avatar automatically comes with both laser's and fingerstip UI manipulation. By default **fingertips are enabled and lasers are disabled.** To enable the lasers just turn them on in the hierarchy.  

![Laser Location](/images/unity/ultimate-xr/laser-location.png)  

## Custom Avatar
### Fingertip Setup
In order to enable the fingertip interaction, you need to add the component **UXRFingertip** to the index finger of each hand (standard placement). You can also use a game object (empty game object) that is attached to the finger tip. 

### Laser Setup
The UI lasers can be enabled by using the **UXRLaserPointer** component. This is usually attached to an object hanging from the hand in the avatar (such as an empty object, item, etc).

## UXR Control Input
The **UXRControlInput** component allows you add additional functionality when interacting with objects such as buttons, sliders, and more. Some things this includes is:
- Audio playback when manipulating elements (sliders, clicks, etc)
- Haptic feedback on click, release, and press

This option allows for easy haptic feedback configurations when it comes to interacting with UI.  

![UXR Control Input Menu](/images/unity/ultimate-xr/uxr-control-input.png)  

{{< hint info >}}
*For more in-depth information about the components or questions go the [UXR Website UI Interaction Page](https://www.ultimatexr.io/guides/ui-interaction) for reference.*
{{< /hint >}}