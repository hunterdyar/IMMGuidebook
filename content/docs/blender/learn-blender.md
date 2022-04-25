---
title: Learn Blender
---

# Blender Learning Path
This page is a learning path for learning Blender. Assuming you know nothing, you can follow through from top to bottom and learn enough Blender that you can continue teaching yourself. The goal is twofold: First: Learn enough to get past the initial difficulty curve into the space where you can hack and learn easily through external resources. Second: Learn the skills for Immersive Media development.

This webpage avoids any single 'full tutorial', and encourages you to jump between guides. If you want to ignore all of that, then the infamous (but now updated and improved for 3.0) [Donut Tutorial](https://www.youtube.com/playlist?list=PLjEaoINr3zgFX8ZsChQVQsuDSjEqdWMAD) from Blender Guru is how many blender users first learned the software. I don't recommend this tutorial simply because it is long, and covers a very wide breadth of Blender features, most of which my students do not need. It absolutely will not hurt you to follow along through it - the more Blender features you learn, the easier it is to pick up other Blender features, as Blender's features have consistent design paradigms and patterns.

## The First Steps
First, of course, [Install Blender]({{< ref "docs/blender/install-blender.md">}}).

Next, keep your eye on the version of blender mentioned in tutorials/guides. Blender made a significant change to it's user interface in version 2.8. Versions for 2.7 and previous are out of date, but versions for 2.8 and newer should be fine.

### The Blender Manual
One of your best resources is one of the most obvious but least used: [The Blender Manual](https://docs.blender.org/manual/en/latest/index.html#). It is unused because it contains so *much* information, and makes no note of which pieces of information are important or are unimportant. It doesn't help you prioritize knowledge, which is challenging because blender has *so many things* in it, and a lot of it's features we can safely ignore.

First, the introductory pages of the manual are helpful, and written with a way that does not assume you already know everything else.

Second, the manual is a **great** place to find out a specific piece of information, or learn how a specific tool works. Most of it's sections begin with an "Introduction" page that is almost always extremely helpful to read.

### 3D Models
Installing blender isn't really the first step. The first step is understanding the basics of 3D models - what they are, how computers represent and work with 3D data, and (abstractly) how computers render graphics. This prerequisite knowledge will be more useful than any follow-along blender tutorial, and allow you to not get lost in the weeds.

- [Blender Manual: Structure](https://docs.blender.org/manual/en/latest/modeling/meshes/structure.html)

### The Interface
The next step is understanding the interface. This, of course, makes following other tutorials easier. We want to be comfortable in the software, and not forced to go exact-step by exact-step through a sequence of memorized processes. We need to know what operations will affect our model, and what operations won't. We need to be able to return to a comfortable starting place if we get lost. A lot of this, yes, will simply come with practice. I want to emphasize spending time learning how to get around Blender before doing follow-along tutorials.

 - Read through the [Blenders manual](https://docs.blender.org/manual/en/latest/interface/window_system/introduction.html) section on User Interface, while identifying the same elements in the software.
 - Blender official tutorial [Interface Overview](https://www.youtube.com/watch?v=8XyIYRW_2xk)
 - Another Blender [interface overview video](https://www.youtube.com/watch?v=tV1ajY2059g), recorded on a mac.

#### The Viewport
- [Viewport Navigation Video](https://www.youtube.com/watch?v=ILqOWe3zAbk)
- Learn about the difference between [Orthographic and Perspective](https://impr.hdyar.com/notes/perspectiveAndProjections.html) projections.
- [Blender Manual: Perspective/Orthographic](https://docs.blender.org/manual/en/latest/editors/3dview/navigate/projections.html)
- [Blender Manual: Navigating Viewport](https://docs.blender.org/manual/en/latest/editors/3dview/navigate/navigation.html)
- [Blender Manual: Fly/Walk Navigation](https://docs.blender.org/manual/en/latest/editors/3dview/navigate/walk_fly.html)

#### The Number Pad
The Number Pad (numpad) is the set of 9 number keys laid out in a grid, usually on the right-hand side of a keyboard.
Some tutorials assume you have a numpad and will make no mention of what to do if you don't.

If you don't, I recommend picking up an external one. This Bluetooth one from [Microsoft](https://www.amazon.com/Microsoft-Number-Pad-Matte-Black/dp/B08J88QBR8/) isn't the cheapest out there, but it's from a reputable brand.

Some guides will tell you to enable the "Emulate Numpad" setting in Blender. I don't recommend this, it can mess with other keyboard shortcuts, which is particularly frustrating when trying to follow a tutorial that may use those shortcuts. Instead, I suggest just pressing the **~** (Tilde) key to bring up a pie-menu that allows you to quickly switch between different views.

### Jargon
A lot of 3D Modeling vocabulary will be strange and particular. Computer Scientists, in general, have a bad habit of borrowing terms that sort-of-kind-of mean what they want from all sorts of other disciplines like mathematics. Listening to 3D modeler and animators talk can sound like gibberish. It's more like the gibberish of a modern English speaker reading [Beowulf](https://en.wikipedia.org/wiki/Old_English), not the gibberish of a modern English speaker reading Latin - you can recognize a lot of the words being said, but what they mean by them doesn't make any sense.

My largest pet peeve is that a lot of explanations tend to briefly, and slightly incorrectly, half-define the various terms they are using. A lot of instructional youtubers may say things that are nominally correct but are lacking in specificity or even wrong by technicality. This should bother you. My advice is to, at least, never trust any one individual's word on the matter. Eventually, pick up a book that had an editor read over it, or find other more academic sources. Or just head to the [glossary](https://docs.blender.org/manual/en/latest/glossary/index.html) page in the Blender manual.

A lot of "helpful" guides will also try to tell you what you *don't* need to know. The goal is to be less overwhelming and less intimidating. But 3D modeling is hard! It is overwhelming, and can be intimidating. It takes time to learn, that's okay. Keep a notes document and fill it with questions or vocab that seemed like it was skipped, so you can remember to go back to it later.

These guides sell themselves as aimed at getting started quickly and easily, without having to bother learning "all the hard stuff". Avoid this line of thinking. Pedagogically, I suggest you attack the subject from three sides.

  1. A bottom-up foundational approach (learn all the jargon)
  2. A top-down pragmatic approach (follow-along videos to learn various sequence of steps)
  3. A practice/project based approach (trial and error)

Do all of it. Learn everything. No knowledge is bad knowledge, no one approach is best.

### Blender Projects & The Outliner
Blender projects are primarily interfaced with via the Outliner.

- Blender Manual: [Scenes](https://docs.blender.org/manual/en/latest/scene_layout/scene/introduction.html) and [Objects](https://docs.blender.org/manual/en/latest/scene_layout/object/introduction.html)
- Learn about [Collections](https://www.youtube.com/watch?v=u_yIGGhubZs)
- [Outliner overview](https://www.youtube.com/watch?v=u918WfK3oac)

## Modeling

### Selecting and Moving Objects Basics
Learning goals: Selection, Object/Edit modes

- [Selecting Objects & Transform](https://www.youtube.com/watch?v=hTL6AKR8YDs)
- [Object and Edit mode](https://www.youtube.com/watch?v=34FBeC9mktE)
- [Box, Circle, or Lasso?](https://www.youtube.com/watch?v=BOcKMcaPhpY)

#### Lazy Tutorials
The [Lazy Tutorials](https://www.youtube.com/watch?v=U1f6NDCttUY&list=PL4Dq5VyfewIxxjzS34k2NES_PuDUIjRcY) series by Ian Hubert may not, exactly, teach you blender. It will more likely inspire you to create things with Blender, and to not worry too much about all the little details, or doing things some 'correct' way. Especially when just getting started.

I particularly enjoy [Creating Custom Buildings](https://www.youtube.com/watch?v=t_c58ryJ-Sw), [Make Cities with Blender](https://www.youtube.com/watch?v=JjnyapZ_P-g), and [Animate Moths in Blender](https://www.youtube.com/watch?v=imkSdlbXB_U).

While you are at it, Ian Hubert's talk from Blender Conference 2019, '[World Building in Blender](https://www.youtube.com/watch?v=whPWKecazgM)' is worth watching. Particularly, [his comments at 28:03](https://youtu.be/whPWKecazgM?t=1682) on reference and mental models.

### Modeling Basics

#### 2D to 3D Workflow
- Helpful video tutorial modeling [low-poly animals](https://www.youtube.com/watch?v=6mT4XFJYq-4)
- Well paced step-by-step [2D Drawing to 3D Model](https://www.youtube.com/watch?v=AlPPYkZg9D4) aimed at character creation.

#### Extrude to Detail Workflow

- [Extrude](https://www.youtube.com/watch?v=2qD_tcPMhOs)
- [Blender 2.8 Beginner 3D Modeling Tutorial](https://www.youtube.com/watch?v=elUJCEC06r8)
- [Common problems with extrude in Blender](https://www.youtube.com/watch?v=V4PG30MjVwM)
- [Loop Cut and Loop Select](https://www.youtube.com/watch?v=5EsCR1sF-d0)

#### Follow-Along
At this point in your Blender journey, it's past time to actually make something. If you haven't followed along with some videos yet, please do follow one. They won't explain *why* they are doing the various steps, or choosing various methods (you don't want to *only* do follow-alongs), but going through the process can, nonetheless, reveal techniques and approaches. Just remember that there is no one correct way to do anything in Blender.

- [Create a 3D Isometric Bedroom](https://www.youtube.com/watch?v=yCHT23A6aJA)
- My own follow-along video about making mistakes and just trying things: [Modeling a Mug in Blender (poorly)](https://youtu.be/cz1uuflzJUM)

### Blender Daily Sketch Assignment
In your Blender Projects folder (that you probably have by now?) create a new folder called "Dailies". In that, create a new folder with the days date in YYYY-MM-DD format (so when sorted alphabetically, it sorts chronologically). In that, save a new blender project.

Using one of the follow-along's as a workflow, close all of your YouTube browser tabs, open a new blender project, and model something. Grab a post-it note and sketch the shape of some object, like a mug, then just try to model it. You will probably mess something up. That's okay! Try to get yourself somewhere useful, and see how far you can get. When you get stuck, don't know how to do something, or mess something up, make note of it.

Try to spend 30 minutes on it, and try *not* to spend more than an hour on it.

When you're done, stuck, ready to give up, close the file and never open it again. Tomorrow, another folder, another project, another 30 minutes attempting a small simple model of some item.

#### Other Workflows
Other approaches to modeling, like Curves, [Geometry Nodes](https://www.youtube.com/watch?v=g7EGSCo1YBI), or [Sculpting](https://www.youtube.com/watch?v=Cmi0KoFtc-4) are not covered on this page. That doesn't mean they are not important (in fact, Geometry Nodes are my personal favorite).

### Modifiers
By this point, you should have seen some modifiers in use in some follow-along Tutorials.

- [Blender Manual: Modifiers Introduction](https://docs.blender.org/manual/en/latest/modeling/modifiers/introduction.html)
- [All You Need to Know about Modifiers in General](https://www.youtube.com/watch?v=V6VHdSM5lMQ)
- [Subdivision Surface Modeling Tutorial](https://www.youtube.com/watch?v=AeMz9aPXpa4)

## Materials & Texturing

### Models & Material Slots

### UV Maps

### Materials vs. Shaders

### Materials and Other Rendering Engines
