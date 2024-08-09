---
title: Terrain Tools
draft: true
---

# Terrain Tools

Hello! Welcome to a quick overview of how to setup terrain tools! If your looking for deeper instruction on what is what, please consult the links at the end of this page!

Unity by default comes with <mark>Terrain</mark>, a basic tool for creating a large 1000 unit by 1000 unit object that can be deformed from this:

*insert image*

To this:

*Insert Photo*

It's simple to use, but lacks the necessary tools needed for adding subtle detail we may want in our projects. This is where <mark>Terrain Tools</mark>  comes in! It adds additional functionality to Unity Terrain to work like a drawing software (adobe, substance painter, etc).

In this tutorial we will go over the setup of Terrain tools, then move on to how to use each of the 5 tabs on a surface level.

## Setup:

Create a new project with 2020.X LTS or greater. It can be in any render pipeline *URP, HDRP, SRP.*

Go to the top of your Unity window, select the "window" drop down, and select **Package Manager.** Look under Unity Registry then search "Terrain Tools". Click download, then install! Your all done!

As a recommendation, download the demo scene provided by unity. It is another recourse that will help show the extent which Terrain Tools can be used.

Once installed, your done! All you need to do now is create a terrain Object in your scene.

## Terrain Component Overview

Creating a terrain is just like creating any primitive object.

- Right click your hierarchy.
- Scroll down to "3D Object".
- Select "Terrain".

Selecting the terrain you will get see three components in your Inspector, "Transform" "Terrain" and "Terrain Collider".

Let us focus on the *Terrain* Component. There are 5 tabs inside the component:

- Create Neighboring Terrains
- Paint Terrain
- Paint Trees
- Paint Details
- Terrain Settings

The first tab creates terrains next to your existing terrain deforming the terrain mesh to fit with the exisitng terrain(s)
The middle three tabs are the meat of the tool and where we will focus on. Each one directly edits the terrain and adds details by directly painting onto the Terrain surface.
The last tab is for specific settings about your terrain. We will not go in depth here. Consult the end of this page for further links.

## How to Modify and Paint





The first tab allows you to create a terrain directly next to an existing terrain. With each Terrain, a Terrain group is created. Each new terrain added to an existing Terrain will inherit as a child of the Terrain group. This cleans up your hierarchy, and avoids you (the user) painfully aligning Terrains next to each other.

## Further Terrain Resources:
[Terrain tools](https://tinyurl.com/TerrainTools)

[Worldbuilding](https://tinyurl.com/TerrainOverview)
