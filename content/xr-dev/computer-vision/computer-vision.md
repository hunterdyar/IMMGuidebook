---
title: Introduction to Computer Vision in Unity
---

# Introduction to Computer Vision in Unity

## Overview

Computer vision is a tool for analyzing image data, often from realtime video feeds like webcams. Various tools are available to integrate computer vision into Unity projects, the most popular is a library called '[OpenCV](https://opencv.org)' which is primarily interfaced with C++ or Python. In order to use it in Unity, we need some translation or conversation layer to talk to it. This guide explores three methods to implement the OpenCV computer vision framework in the Unity game engine.

## Methods

### Emgu CV Asset

- **Cost:** Free for open-source use, $399 for closed (commercial) use. Development is supported through this dual-license model. 
- **Resource (paid):** [Emgu CV Asset](https://assetstore.unity.com/packages/tools/behavior-ai/emgu-cv-v4-x-144853)
- **Resource (free):** [Emgu NuGet Installation Guide](https://www.emgu.com/wiki/index.php/Emgu_TF_Download_And_Installation#Nuget)
### Manual Integration of Emgu

- **Resources:**
  - [GitHub Repository](https://github.com/dao-duc-tung/face-detection-unity-emgucv-onnx )
- **Procedure:** Follow documentation and instructions provided on the GitHub repository for manual integration of Emgu using NuGet in Unity.

### OpenCV For Unity (Enox Software)
- **Cost:** $95 
- **Resource:** [OpenCV for Unity](https://assetstore.unity.com/packages/tools/integration/opencv-for-unity-21088)


### OpenCV Plus Unity (Paper Planes Tools)

- **Resource:** [OpenCV Plus Unity](https://assetstore.unity.com/packages/tools/integration/opencv-plus-unity-85928)
- **Issues:** Has not been updated since 2019, resulting in code errors.
- **Resolution:** Enable 'Allow Unsafe Code' in Unity. For Unity 2022. Modify this outdated code to ensure compatibility:

```csharp
void OnDestroy() { 			 
    SceneManager.UnloadScene ("DocumentScannerScene");
}

```
And change it to this so it works with newer Unity versions:
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
  - Remove any non-functioning script attached to the Main Camera Object.
- **Integration:** Implement computer vision scenes by:
  - Selecting the example scene that serves the purpose you want. The example scene should just work if you follow the instructions above.
  - *Note:* You may have to build the scene for it to work without buffering, it will run smoothly in a build, not as well in the editor.
