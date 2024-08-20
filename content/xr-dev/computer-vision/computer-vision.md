---
title: Setting up Computer Vision Libraries in Unity
---

# Setting up Computer Vision Libraries in Unity

## Overview

Computer vision is an approach for analyzing image data, often from realtime video feeds like webcams. 
Various tools are available to integrate computer vision into Unity projects, the most popular is a library called '[OpenCV](https://opencv.org)' which is primarily interfaced with from C++ or Python. OpenCV is open source and free to use.  

In order to use it within Unity, we need some translation or conversation layer to talk to the OpenCV Library. This guide explores three different wrappers for the OpenCV computer vision framework in the Unity game engine.

## Methods

### Emgu CV Asset
- **Cost:** Free for open-source use, $399 for closed (commercial) use. Development is supported through this dual-license model. 
- **Resource (paid):** [Emgu CV Asset](https://assetstore.unity.com/packages/tools/behavior-ai/emgu-cv-v4-x-144853)
- **Resource (free):** [Emgu NuGet Installation Guide](https://www.emgu.com/wiki/index.php/Emgu_TF_Download_And_Installation#Nuget)

### Manual Integration of Emgu
- **Resources:** [GitHub Repository](https://github.com/dao-duc-tung/face-detection-unity-emgucv-onnx )
- **Procedure:** Follow documentation and instructions provided on the GitHub repository for manual integration of Emgu using NuGet in Unity.

### OpenCV For Unity (Enox Software)
- **Cost:** $95 
- **Resource:** [OpenCV for Unity](https://assetstore.unity.com/packages/tools/integration/opencv-for-unity-21088)

### OpenCV Plus Unity (Paper Planes Tools)
- **Resource:** [OpenCV Plus Unity](https://assetstore.unity.com/packages/tools/integration/opencv-plus-unity-85928)
- **Issues:** Has not been updated since 2019, resulting in code errors.
- **Resolution:** Enable 'Allow Unsafe Code' in Unity. For Unity 2022. Modify this outdated code to ensure compatibility:

The error that appears from this line:

```csharp
void OnDestroy() { 			 
    SceneManager.UnloadScene ("DocumentScannerScene");
}

```
Can be changed it to this to work with newer Unity versions (*tested with 2022.2*):

```csharp
void OnDestroy() {
    Scene scene = SceneManager.GetSceneByName("DocumentScannerScene");
    if (scene.isLoaded) {
        SceneManager.UnloadSceneAsync(scene);
    } else {
        Debug.LogError("Scene not loaded: DocumentScannerScene");
    }
}
```
- **Integration:** Implement computer vision scenes by:
  - Selecting the example scene that serves the purpose you want. The example scene should just work if you follow the instructions above.
  - *Note:* You may have to build the scene for it to work without buffering, it will run smoothly in a build, not as well in the editor.
