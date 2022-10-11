---
title: Learn Blender
weight: 2
---
<!-- <img src="/images/blender/learn/important-green.svg" style="width:1em;height:1em;display:inline-block;margin-right:0.5em" /> -->

{{< hint info >}}
Students in IMM103, the <img src="/images/blender/learn/important-green.svg" style="width:1em;height:1em;display:inline-block;margin-right:0.1em" /> 'important' icon means the topic is required, and the <img src="/images/blender/learn/bookmark.svg" style="width:1em;height:1em;display:inline-block;margin-right:0.1em" /> bookmark icon means the topic is encouraged; and a good resource to return to.
{{</hint>}}

# Blender Learning Path
This page is a learning path for learning Blender. Assuming you know nothing, you can follow through from top to bottom and learn enough Blender that you can continue teaching yourself. The goal is to learn enough to get past the initial difficulty curve, and get into the space where you can hack and learn easily through external resources.

This webpage avoids any single 'full tutorial', and encourages you to jump between guides. If you want to ignore all of that, then the popular [Donut Tutorial](https://www.youtube.com/playlist?list=PLjEaoINr3zgFX8ZsChQVQsuDSjEqdWMAD) from Blender Guru is how many blender users first learned the software. This long tutorial provides a broad overview of almost everything you can do in Blender, and will leave you confident in the user interface. I would explore shorter resources and more experimentation-based approaches first, and consider going through it later to "round out" your knowledge of the interface.

## <img src="/images/blender/learn/important-green.svg" style="width:1em;height:1em;display:inline-block" /> The First Steps
First, of course, [Install Blender]({{< ref "docs/blender/install-blender.md">}}).

Next, keep your eye on the version of blender mentioned in tutorials/guides. Blender made a significant change to it's user interface in version 2.8. Versions for 2.7 and previous are out of date, but versions for 2.8 and newer should be fine.

### The Blender Manual
One of your best resources is too easily overlooked: [The Blender Manual](https://docs.blender.org/manual/en/latest/index.html#). The challenge of the manual is that it contains so *much* information, and provides no insight into which pieces of information are important or unimportant (and makes no attempt to). This is challenging because blender has *so many things* in it, and a lot of these features we can safely ignore. Keep this in mind as you use the software.

First, the introductory pages of the manual are helpful, and written with a way that does not assume you already know everything else.

Second, the manual is a **great** place to find out a specific piece of information, or learn how a specific tool works. Most of it's sections begin with an "Introduction" page that is almost always extremely helpful to read.

### 3D Models
Installing blender isn't really the first step. The first step is understanding the basics of 3D models - what they are, how computers represent and work with 3D data, and (abstractly) how computers render graphics. This prerequisite knowledge will be more useful than any follow-along blender tutorial, and allow you to not get lost in the weeds.


- <img src="/images/blender/learn/important-green.svg" style="width:1em;height:1em;display:inline-block;margin-right:0.2em"/>[Blender Manual: Structure](https://docs.blender.org/manual/en/latest/modeling/meshes/structure.html)
- <img src="/images/blender/learn/bookmark.svg" style="width:1em;height:1em;display:inline-block;margin-right:0.5em" />This [Guidebook page]({{< ref "3d-models.md" >}}) on what 3D models are.

### The Interface
The next step is understanding the interface. This makes following tutorials and guides easier. We want to be comfortable in the software, and not forced to go exact-step by exact-step through a sequence of memorized processes.

We need to know what operations will affect our model, and what operations won't. **You should be able to return to a comfortable starting place if you get tripped up.** A lot of this, yes, will simply come with practice. I want to emphasize spending time learning how to get around Blender before doing follow-along tutorials.

When you're following along with a tutorial, you want to follow the higher-level operations, not focus on some specific sequence of button presses (unless you're learning a keyboard shortcut, I suppose). In other words, do your best to think in terms of "switch to edit mode" and not "now press tab".

 - Read through the [Blenders manual](https://docs.blender.org/manual/en/latest/interface/window_system/introduction.html) section on User Interface, while navigating through and identifying the same elements in the software.
 - <img src="/images/blender/learn/important-green.svg" style="width:1em;height:1em;display:inline-block;margin-right:0.5em" /> Blender's official tutorial is very good: [Interface Overview](https://www.youtube.com/watch?v=8XyIYRW_2xk). When you're following another tutorial and you get stuck on a step, perhaps having to rewind to see what button they pressed, make a note of the tool. Later, find the **[Blender Fundamentals](https://www.youtube.com/playlist?list=PLa1F2ddGya_-UvuAqHAksYnB0qL9yWDO6)** video, from this series, and review.
 - Another Blender [interface overview video](https://www.youtube.com/watch?v=tV1ajY2059g), this one recorded on a mac.
- [Blender 3 - Complete Beginners Guide - Part 1](https://youtu.be/jnj2BL4chaQ?list=PLn3ukorJv4vuU3ILv3g3xnUyEGOQR-D8J).

{{< youtube 8XyIYRW_2xk >}}

#### The Viewport
- <img src="/images/blender/learn/important-green.svg" style="width:1em;height:1em;display:inline-block;margin-right:0.2em"/> [Viewport Navigation Video](https://www.youtube.com/watch?v=ILqOWe3zAbk)
- <img src="/images/blender/learn/important-green.svg" style="width:1em;height:1em;display:inline-block;margin-right:0.5em" />Learn about the difference between [Orthographic and Perspective]({{< ref "/docs/digital-media-fundamentals/perspective-distortion-and-projections.md">}}) projections.
- [Blender Manual: Perspective/Orthographic](https://docs.blender.org/manual/en/latest/editors/3dview/navigate/projections.html)
- [Blender Manual: Navigating Viewport](https://docs.blender.org/manual/en/latest/editors/3dview/navigate/navigation.html)
- [Blender Manual: Fly/Walk Navigation](https://docs.blender.org/manual/en/latest/editors/3dview/navigate/walk_fly.html)

{{< youtube ILqOWe3zAbk >}}

#### <img src="/images/blender/learn/important-green.svg" style="width:1em;height:1em;display:inline-block;margin-right:0.2em"/> The Number Pad
The Number Pad (numpad) is the set of 9 number keys laid out in a grid, usually on the right-hand side of a keyboard.
Some tutorials assume you have a numpad and will make no mention of what to do if you don't.

If you don't, I recommend picking up an external one. This Bluetooth one from [Microsoft](https://www.amazon.com/Microsoft-Number-Pad-Matte-Black/dp/B08J88QBR8/) isn't the cheapest out there, but it's from a reputable brand.

{{<hint warning>}}
Some guides will tell you to enable the "**Emulate Numpad**" setting in Blender. I don't recommend this, it can mess with other keyboard shortcuts, which is particularly frustrating when trying to follow a tutorial that may use those shortcuts. Instead, I suggest just pressing the **~** (Tilde) key to bring up a pie-menu that allows you to quickly switch between different views.
{{</hint>}}

## <img src="/images/blender/learn/important-green.svg" style="width:1em;height:1em;display:inline-block;margin-right:0.2em"/>How To Get The Most out of Follow-Along Videos
A lot of 3D Modeling vocabulary will be strange and particular. Computer Scientists, in general, have a bad habit of borrowing terms that sort-of-kind-of mean what they want from all sorts of other disciplines like mathematics. Listening to 3D modeler and animators talk during a tutorial can sound like gibberish.

Additionally, a lot of explanations tend to briefly, and slightly incorrectly, half-define the various terms they are using. My advice is to, at least, never trust any one individual's word on the matter (even mine). Our source of jargon truth is the [glossary](https://docs.blender.org/manual/en/latest/glossary/index.html) page in the Blender manual.

A lot of "helpful" guides will try to be less overwhelming and less intimidating, and direct you away from "what you don't need to know". This is a neccesity when getting started, but ... a lot of the skipped pieces we will eventually need to know! So, again, don't trust any one source of information or any one workflow.

It is overwhelming, and can be intimidating. It takes time to learn, that's okay. Keep a notes document and fill it with questions or vocab that seemed like it was skipped, so you can remember to go back to it later.

Some guides sell themselves as aimed at getting started quickly and easily, without having to bother learning "all the hard stuff". **Avoid this line of thinking**. Pedagogically, I suggest you apprach learning Blender from three sides.

  1. A bottom-up foundational approach (learn all the jargon/tech)
  2. A top-down pragmatic approach (follow-along videos to learn various sequence of steps)
  3. A practice/project based approach (trial and error)

Do all of it. Learn everything. No knowledge is bad knowledge, no one approach is best. With all this said, let's get back to learning Blender!

### Blender Projects & The Outliner
Blender projects are primarily interfaced with via the Outliner.

- Blender Manual: [Scenes](https://docs.blender.org/manual/en/latest/scene_layout/scene/introduction.html) and [Objects](https://docs.blender.org/manual/en/latest/scene_layout/object/introduction.html)
- <img src="/images/blender/learn/important-green.svg" style="width:1em;height:1em;display:inline-block;margin-right:0.2em"/>Learn about [Collections](https://www.youtube.com/watch?v=u_yIGGhubZs)
- <img src="/images/blender/learn/important-green.svg" style="width:1em;height:1em;display:inline-block;margin-right:0.2em"/>[Outliner overview](https://www.youtube.com/watch?v=u918WfK3oac)

### The Properties Window
- <img src="/images/blender/learn/important-green.svg" style="width:1em;height:1em;display:inline-block;margin-right:0.2em"/> [Blender Properties Window Overview](https://youtu.be/tt-Ggohc6Ls)

{{< youtube tt-Ggohc6Ls >}}

## <img src="/images/blender/learn/important-green.svg" style="width:1em;height:1em;display:inline-block;margin-right:0.2em"/>Modeling

### Selecting and Moving Objects Basics
Be warned: selection is more complex in Blender than in other pieces of software. It may not behave like you expect it to from other software. For example, the order you multi-select objects can be important.

Learning goals: Selection, Object/Edit modes

- [Blender Manual: Selections and Active Object](https://docs.blender.org/manual/en/latest/scene_layout/object/selecting.html)
- <img src="/images/blender/learn/important-green.svg" style="width:1em;height:1em;display:inline-block;margin-right:0.2em"/> [Selecting Objects & Transform](https://www.youtube.com/watch?v=hTL6AKR8YDs)
- <img src="/images/blender/learn/important-green.svg" style="width:1em;height:1em;display:inline-block;margin-right:0.2em"/>[Object and Edit mode](https://www.youtube.com/watch?v=34FBeC9mktE)
- [Box, Circle, or Lasso?](https://www.youtube.com/watch?v=BOcKMcaPhpY)

#### <img src="/images/blender/learn/bookmark.svg" style="width:1em;height:1em;display:inline-block;margin-right:0.2em"/>Prelude/Bonus: Lazy Tutorials
The [Lazy Tutorials](https://www.youtube.com/watch?v=U1f6NDCttUY&list=PL4Dq5VyfewIxxjzS34k2NES_PuDUIjRcY) series by Ian Hubert may not, exactly, teach you blender. It will more likely inspire you to create things with Blender, and to not worry too much about all the little details. Especially when just getting started. Check them out - they are only about a minute long.

I particularly enjoy [Creating Custom Buildings](https://www.youtube.com/watch?v=t_c58ryJ-Sw), [Make Cities with Blender](https://www.youtube.com/watch?v=JjnyapZ_P-g), and [Animate Moths in Blender](https://www.youtube.com/watch?v=imkSdlbXB_U).

While you are at it, Ian Hubert's talk from Blender Conference 2019, '[World Building in Blender](https://www.youtube.com/watch?v=whPWKecazgM)' is worth watching. Particularly, [his comments at 28:03](https://youtu.be/whPWKecazgM?t=1682) on reference and mental models.

{{< youtube imkSdlbXB_U >}}

### Modeling Basics

#### 2D to 3D Workflow
- <img src="/images/blender/learn/important-green.svg" style="width:1em;height:1em;display:inline-block;margin-right:0.2em"/>Helpful video tutorial modeling [low-poly animals](https://www.youtube.com/watch?v=6mT4XFJYq-4)
- Well paced step-by-step [2D Drawing to 3D Model](https://www.youtube.com/watch?v=AlPPYkZg9D4) aimed at character creation.

{{< youtube 6mT4XFJYq-4 >}}

#### <img src="/images/blender/learn/bookmark.svg" style="width:1em;height:1em;display:inline-block;margin-right:0.2em"/>Extrude to Detail Workflow

- [Extrude](https://www.youtube.com/watch?v=2qD_tcPMhOs)
- [Blender 2.8 Beginner 3D Modeling Tutorial](https://www.youtube.com/watch?v=elUJCEC06r8)
- [Common problems with extrude in Blender](https://www.youtube.com/watch?v=V4PG30MjVwM)
- [Loop Cut and Loop Select](https://www.youtube.com/watch?v=5EsCR1sF-d0)

#### Follow-Along
At this point in your Blender journey, it's past time to actually make something. If you haven't followed along with some videos yet, please do follow one. They won't explain *why* they are doing the various steps, or choosing various methods (you don't want to *only* do follow-alongs), but going through the process can, nonetheless, reveal techniques and approaches. Just remember that there is no one correct way to do anything in Blender.

- [Create a 3D Isometric Bedroom](https://www.youtube.com/watch?v=yCHT23A6aJA)
- My own follow-along video about making mistakes and just trying things: [Modeling a Mug in Blender (poorly)](https://youtu.be/cz1uuflzJUM)
- <img src="/images/blender/learn/bookmark.svg" style="width:1em;height:1em;display:inline-block;margin-right:0.2em"/>[Modeling a Hot Air Balloon](https://youtu.be/c_OpgHi1jic)
- Eve Sculpts [How To Make a 3D Room for Beginners](https://www.youtube.com/watch?v=efRA1eeos9g)

### <img src="/images/blender/learn/important-green.svg" style="width:1em;height:1em;display:inline-block;margin-right:0.2em"/> Blender Daily Sketch Assignment
In your Blender Projects folder (that you probably have by now?) create a new folder called "Dailies". In that, create a new folder with the days date in YYYY-MM-DD format (so when sorted alphabetically, it sorts chronologically). In that, save a new blender project.

Using one of the follow-along's as a workflow, close all of your YouTube browser tabs, open a new blender project, and model something. Grab a post-it note and sketch the shape of some object, like a mug, then just try to model it. You will probably mess something up. That's okay! Try to get yourself somewhere useful, and see how far you can get. When you get stuck, don't know how to do something, or mess something up, make note of it.

Try to spend 30 minutes on it, and try *not* to spend more than an hour on it.

When you're done, stuck, ready to give up, close the file and never open it again. Tomorrow, another folder, another project, another 30 minutes attempting a small simple model of some item.

{{< hint info >}}
<img src="/images/blender/learn/important-green.svg" style="width:1em;height:1em;display:inline-block;margin-right:0.2em"/> IMM103 Students. Bring 4 Sketches to next week's class. The sketches can come from follow-along video projects, but at least one must be an original attempt. It is ungraded, you cannot fail - just try your best to make something from nothing.
{{</hint>}}

#### <img src="/images/blender/learn/bookmark.svg" style="width:1em;height:1em;display:inline-block;margin-right:0.2em"/> Other Workflows
Other approaches to modeling, like Curves, [Geometry Nodes](https://www.youtube.com/watch?v=g7EGSCo1YBI), or [Sculpting](https://www.youtube.com/watch?v=Cmi0KoFtc-4) are not covered on this page. That doesn't mean they are not important (in fact, Geometry Nodes are my personal favorite).

### Modifiers
By this point, you should have seen some modifiers in use in some follow-along Tutorials.

- [Blender Manual: Modifiers Introduction](https://docs.blender.org/manual/en/latest/modeling/modifiers/introduction.html)
- [All You Need to Know about Modifiers in General](https://www.youtube.com/watch?v=V6VHdSM5lMQ)
- [Subdivision Surface Modeling Tutorial](https://www.youtube.com/watch?v=AeMz9aPXpa4)

## <img src="/images/blender/learn/important-green.svg" style="width:1em;height:1em;display:inline-block;margin-right:0.2em"/> Shading, Materials, Texturing
 - [About Vertex Normals](https://youtu.be/JGqOCdJ0DDg)

### Models & Material Slots

### UV Maps
- <img src="/images/blender/learn/important-green.svg" style="width:1em;height:1em;display:inline-block;margin-right:0.2em"/> [What Are UV Maps?](https://explainers.hdyar.com/uvmaps/index.html) article
- <img src="/images/blender/learn/important-green.svg" style="width:1em;height:1em;display:inline-block;margin-right:0.2em"/> [How To make Hibiscus flower in Blender](https://www.youtube.com/watch?v=wRcL0CPljMA)

First just watch this 'lazy tutorial' on UV Maps.
{{< youtube JjnyapZ_P-g >}}

This flower tutorial covers, among other things, UV Mapping.
{{< youtube wRcL0CPljMA >}}

### Materials vs. Shaders

### Materials and Other Rendering Engines

### Rendering & Exporting

## <img src="/images/blender/learn/bookmark.svg" style="width:1em;height:1em;display:inline-block;margin-right:0.2em"/> Complete Guides, Tutorials, and other resources

- Blender's [Blender Fundamentals](https://www.youtube.com/playlist?list=PLa1F2ddGya_-UvuAqHAksYnB0qL9yWDO6)
- Blender Guru: [Donut Tutorial](https://www.youtube.com/watch?v=nIoXOplUvAw&list=PLjEaoINr3zgFX8ZsChQVQsuDSjEqdWMAD)
- Grant Abbitt: [Complete Beginner Guide](https://www.youtube.com/playlist?list=PLn3ukorJv4vs_eSJUQPxBRaDS8PrVmIri)
- [Learn Sculpting in Blender 2.8](https://www.youtube.com/playlist?list=PLn3ukorJv4vvJM7tvjet4PP-LVjJx13oB)
- Grant Abbitt: [Get Good At Blender](https://www.youtube.com/playlist?list=PLn3ukorJv4vvv3ZpWJYvV5Tmvo7ISO-NN) (I recommend this practice-based approach)
- CGCookie [Blender 3.0 Complete Course](https://www.youtube.com/playlist?list=PL3GeP3YLZn5ixsnIOIx9tB4v6s-rsw48X)
- [3DBestie.com](https://www.3dbestie.com/)
- [Blender Daily](https://www.youtube.com/c/BlenderDaily), particularly [Blender Traps For Beginners](https://www.youtube.com/playlist?list=PLSlMI4YOEdKcYzDPgE8vF2Fq_dkgWS6NP)
- [Blender Secrets](https://www.blendersecrets.org/) [(youtube)](https://www.youtube.com/channel/UCp7EwodJcppc6GqiRcnCpOw)
- [Ksenia Starkova](https://www.youtube.com/c/KseniaStarkova/featured) - No voice over or narration on videos, just slow but clear presentation. Nice approach to watch a process come together, and pick up some strategies.
- Kevandram [Grease Pencil Bakery Shop Tutorial](https://www.youtube.com/watch?v=nZyB30-xZFs). A different 2D-in-3D based workflow using grease pencil.
