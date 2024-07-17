---
title: Installing Blender
weight: 1
---

# Installing Blender
You can always download and install the latest stable release of Blender at [blender.org](https://www.blender.org/).

## Blender Launcher
Only if you want to use brand new or experimental features (at the time of writing, new Geometry Nodes), you may want to explore different development branches of Blender. Dealing with multiple versions of Blender on one machine can be annoying. The best way to do this is with a piece of open source software called [Blender Launcher](https://github.com/DotBow/Blender-Launcher).

Blender Launcher will download and manage different blender versions, and let you easily change shortcuts/file associations for them.

## MeshLab
I also recommend installing [MeshLab](https://www.meshlab.net/). MeshLab is open source software for working with models. It's not modeling software, itself, it's more like a set of processes and utilities.

In its own words, MeshLab is a

>  ...system for processing and editing 3D triangular meshes.
It provides a set of tools for editing, cleaning, healing, inspecting, rendering, texturing and converting meshes. It offers features for processing raw data produced by 3D digitization tools/devices and for preparing models for 3D printing.

The first reason I recommend MeshLab is because it can import many different file types, and convert  them to new file types. It can also more robustly attempt to read and understand a corrupted 3D model. If you get a 3D model in some esoteric format that Blender cannot support, if it's corrupt, or if it's just incredibly large - try bringing it into MeshLab to convert it into a model that Blender can understand.

It's also great for [decimating](https://en.wikipedia.org/wiki/Downsampling_(signal_processing)) giant (multi-gigabyte) 3D models into smaller ones, reducing the polycount. Particularly useful when working with 3D scan data.

You may not need it for most day-to-day modeling, but if you do you will be glad you have it.
