---
title: Preferences Setup
---

Here are the settings that I prefer to change for Blender. Open the preferences by going to **Edit > Preferences**.

## Interface
**Interface > Menus > Open on Mouse Over.** I find this feature helpful during mouse-only operation.

## Viewport
Display > 3D Viewport Axis Size. I set mine axis size to be easier to see, easier to check my orientation at a glance. Although I use 1440 and 4k monitors.

## Keymap
The F3 button opens a menu-search popup in Blender, which is a life-saver. If you don't have a f-row (or, as with many laptops, your f-row is media keys by default, requiring you to hold the 'fn' button down to use), **and** you aren't doing animation in Blender, then it can be very helpful to have the spacebar open search.

![The search button popup](/images/blender/toolbox/searchmenu.png)

## Tab For Pie Menu
In the Keymap section of preferences, I recommend checking "Tab For Pie Menu".
Instead of the tab key switching between Object and Edit mode, tab will open a pie menu of various modes.

![The Tab for Pie Menu popup](/images/blender/toolbox/tabForPieMenu.png)

This forces you to be aware of the mode you are switching to. It's much harder to forget which mode you are in, and you never do the little dance where you tap tab repeatedly trying to reset yourself. It's also nice when working with workflows like rigging or sculpting.

## Performance
Blender runs great on most machines, but if your machine is more powerful or has more memory, you can give yourself some extra freedom. Depending on your machine, you may want to:

In the **System** section
- Increase the Undo Steps (I set mine to 124)

In the **Save and Load** section
- Increase the "Save Versions". When manually saving, it won't overwrite the previous file, but keep a recent history of files. With extensions ".blend1" and ".blend2", they're easily enough to ignore and delete to save space. But when you need it, they're there. I keep 3 around.
- Increase the number of recent files to show in the "File > Open Recent" menu.
- Turn on Auto-Save. Every x minutes, this will save another version of your project to the Temp directory. If Blender crashes, you can [recover](https://docs.blender.org/manual/en/latest/troubleshooting/recover.html) your project.
