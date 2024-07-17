---
title: 3D Model Filetypes
draft: true
---

3D Models come in a number of shapes, with various pros and cons. Remember that you can _almost_ always convert between file types. Before discussing the specifics, some things to know.

## What Makes The File Types Different
There are a lot of technical differences between file types, such as ease-of-compression, how amenable they are to bulk data processing, what kind of encoding they use, and other variations that we don't really care about.

When it comes to 3D models, there are only a few features that one might have that we _really_ care about, and that's the number of supported sub-data types. 

If you think of a file as a folder-of-files (called a "container"), it's easier to visualize. Consider video files. They have the video data, but also audio tracks, subtitles, metadata, and so on. 3D models can be the same way with material properties, image texture data, animations, and such. 

Once we consider the amount of data that can be encapsualted by a 3D model, it's clear that they can be very complicated (just see this [overview pdf](https://www.khronos.org/files/gltf20-reference-guide.pdf) of glTF).

## Working with Unity
Unity operates with FBX files behind-the-scenes, and will convert your models to FBX. Whether or not a file format is supported by Unity basically comes down to whether or not Unity has to pay licensing fees to use the file type. Otherwise, it supports most file types. The notable exception is [glTF](https://www.khronos.org/gltf/).

In Unity, we generally keep our 'model' data separate from our materials and textures. Often, this means "unpacking" a model (the container) into it's various pieces. This automatically happens when you import a model in Unity, the various elements it contains are treated as separate assets when it is imported. 