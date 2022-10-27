---
title: Zero to Quest - Ultimate XR
---

 ## Installing Ultimate XR into Your Unity Project

### Walkthrough Video

{{< youtube 4kRyh-uJAy4 >}}

### Overview

 0. Make sure Android is added as a build target for the appropriate version of Unity. You can do this in the Unity Hub. Go to Installs, click the gear icon next to the appropriate version of Unity, and choose "Add Modules". Add Android Build Support, and the JDK, SDK, and NDK tools.

 1. Go to [UltimateXR](https://www.ultimatexr.io/) and click on the download link below the "Watch Teaser" button.  

 2. Open a new project in 3D (URP), you may need to download it. DO NOT download the sample scene option.  
 ![Installing URP Project](/images/unity/virtual-reality/installing-urp-project.png)

 3. After your project opens, go to File, Build Settings at the bottom of the drop down and click on the Android icon in the platform area. Click **Switch Platform** in bottom right.  
 ![Changing Build Platform](/images/unity/virtual-reality/change-build-settings-to-android.png)

 4. Right click on the assets area in the project tab (bottom by default). Then click on Import Package – Custom Package. Find where you saved the UltimateXR unity add-on and double click. After it loads click import for everything.  
 ![Import Custom Package](/images/unity/virtual-reality/import-custom-package.png)

 5. Next, go to the project settings. At the very bottom of the list there is a tab called XR Plugin Management. Click it. Install XR Plugin Management.  
 ![Installing XR Plugin Management](/images/unity/virtual-reality/installing-xr-plugin-management.png)

 6. Click the android icon, select the oculus check box icon.  
 ![Checking Android Icon in Management](/images/unity/virtual-reality/oculus-checkbox-manage.png)

 7. **Optional** - You can select the desktop icon on the far left and click the same check box, oculus. This will allow you to view the game view in your headset without building an apk, using "Oculus Link".  
 ![Optional Android Icon in Management](/images/unity/virtual-reality/optional-oculus-checkbox-manage.png)

 8.	Finally, if you are getting an error related to color management, go to your player settings (it is in the same area as XR-Plugin management tab, just go up the list), select the android icon, and check off Auto Graphics API (under other settings).
 ![Checking Graphics API Box](/images/unity/virtual-reality/checking-auto-graphics-api.png)
![Overview of Graphics API Without Error](/images/unity/virtual-reality/auto-graphics-api-overview.png)
