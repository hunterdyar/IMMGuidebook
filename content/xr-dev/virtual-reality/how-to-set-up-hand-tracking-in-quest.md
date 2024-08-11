---
title: Hand Tracking in Quest 3
oldlink: https://guidebook.hdyar.com/docs/unity/virtual-reality/how-to-set-up-hand-tracking-in-quest/
---

# How to Set Up Hand Tracking in Quest 3 Using Unity and the "Meta XR All in One SDK"

## Prepare Unity and SDKs:
This can be done in a new or existing Unity project. The render pipeline (URP or Standard) does not matter.

2. Make sure you're running a modern version of Unity (2021-2024).
3. [Install]({{< ref "/unity-starting/setup/packages-assets-modules.md" >}}) the [Meta XR All in One SDK](https://assetstore.unity.com/packages/tools/integration/meta-xr-all-in-one-sdk-269657) from the Unity Asset Store.

[![meta SDK Screenshot](/images/unity/hand-tracking/MetaSDKAll.png)](https://assetstore.unity.com/packages/tools/integration/meta-xr-all-in-one-sdk-269657)

> Note: Quest Hand Tracking is not currenty compatible with Unity's XR Interaction Toolkit. For doing a hand tracking project using this tool, one should use Meta's tools. This is for things like grabbables, teleportation, etc.

## Configure XR Plugin Management:

1. Install the [XR Plugin Management](https://docs.unity3d.com/Packages/com.unity.xr.management@4.4/manual/index.html) package. (For package installation instructions, see '[Packages, Assets, Modules]({{< ref "/unity-starting/setup/packages-assets-modules.md" >}})')
2. Go to `Edit -> Project Settings`.
3. Select XR Plugin Management.
4. Enable Android Build Support.

![This is an alt text.](/images/unity/hand-tracking/XRManageSetting.png "This is a sample image.")

4. Click on the Oculus tab under XR Plugin Management.
5. Enable the Oculus integration for the target device you're building to.
6. Change to Android in the Build Settings, if you have not already done so.

## Access Oculus Tools:

1. Click on the Oculus tab located on the top left of Unity’s interface.
2. Navigate to `Tools -> Building Blocks`.

![This is an alt text.](/images/unity/hand-tracking/BuildingBlocks.png "This is a sample image.")

### Using Building Blocks:

1. In the Building Blocks window, click on the bottom right corner of the components you want to include in your project.
2. These components will automatically appear in your Unity Hierarchy.

## Build to the Quest 3:

- Connect your Quest 3 to your computer via a USB-C cable.

1. Open Meta Developer Hub on your computer.
2. Connect and configure your Quest headset within the Developer Hub.
3. Configure [Build Settings]({{< ref "unity-starting/unity-fundamentals/builds.md">}}) in Unity, ensuring you're on Android Build Mode.
