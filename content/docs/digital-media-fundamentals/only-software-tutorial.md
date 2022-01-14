---
title: The Only Software Tutorial You Will Ever Need
draft: true
---
As I have improved at many giant pieces of creative software, there are some commonalities between improving at Photoshop, Blender, Unity, Programming, and so on. I am going to attempt to identify the universal principles that come up when you learn software.

I want to say this is about "creative" software, because it is. I am mostly focused on creative software. Big tools used to make and export stuff. A lot of this isn't even software-dependent, but applicable for working with any tool. I imagine that many engineers will find common ground.
	
# Change one thing to change one thing
If we change one thing and multiple things get affected, that's bad. How many inputs affect how many outputs? If we need to change multiple things in order to make one change, that's also bad. Please stay with me through the generalities.

The issue could stem from dependencies, from data structures, or from our workflow. It's usually how we choose to structure or assemble our project. It also can come from how different parts of the project are - or are not - linked to each other. 

- In 3D animation, this is using rig mechanisms to automate counter-animation.
	- In one sense, rigging is "expose one nice clean editable property to an animator". Everybody likes a good rig. 
- In programming, we keep our architecture clean of spaghetti code, with nice interfaces that let me change internals of one thing without needing to edit other things to match.
- In photoshop, I use adjustment layers on groups, and heavily use separate layers to keep my colors and inks independent of each other.
	- "Oh no! I was drawing on my sketch layer!" cried the comic artist, again.
- In Unreal Engine, this is having good blueprints.

This is often done with various forms of **compartmentalization** and **automation**.

Compartmentalization: Keep my edits from touching other things.

Automation: Let the other things edit themselves in response.

So compartmentalization prevents us from needing to edit multiple things. Automation, on the other hand, is having our tool do chained/dependency/systematic edits for us. Often they are exactly the kind of repetitive, predictable edits that tools are very good at doing.

Many IDE's, like visual studio code or JetBrains Rider, have refactor code options. One of these options is renaming a variable. Let the IDE go find all and replace. Don't do that by hand. You are doing one thing: renaming a variable. Don't go finding and re-typing it 30 times, that's stupid. Change one thing to change one thing. 

# Isolate Unlinked Elements
This point is repeating "compartmentalize". But that section is about the workflow. I want to elaborate further on the structure.

Try to separate elements from each other when they are not inherently linked. Separate layers for your stencils, colors, and inks in that digital painting. Separate buses/groups for your different audio sections in your DAW (I don't do music, but I edit radio. Separating background, voice over, foley, etc) from each other so I can edit them more coherently. 

Separate your input systems and your animation systems. Separate your player input code from your player movement code. Even when they always go together, it's nice to edit and work with this *very different* problems in *different locations*. This way you can apply different solutions to them without everything getting tied up in a big mess.

# Groupings
The exact opposite of isolating is grouping. When do you want to make a change that *does* affect multiple things. The litmus test is repeating yourself. **Avoid repeating yourself.**

When to use groups and when to separate (compartmentalize) things is software-specific, but broadly speaking, you need to make your data structure (its organization, its grouping), something that is both sensible to you, and that aligns with the edits you will do. 

Most photoshop users don't take advantage of groups enough. You can group layers into a folder, then make an adjustment layer and set it to only edit the below layer, which is the entire group of layers. It's *great.*

Some warning: be careful when grouping things adds its own behaviors.
In Unity, many developers use empty parent objects as a folder, but they are parent-tranasforms, and with all 3D software, the child transforms are now relative to the parent. If they aren't paying attention, the empty parent 'folder' object could have some position, rotation, or god-forbid, scale; and all the children objects are not going to behave as expected, or things will totally break on you. 

In blender, you would avoid this by using Collections (or the awful layer system, for the <2.8 folk) instead of Empties. In Unity, be sure to zero-out your empty-parent transforms, at least. Remember the hierarchy is not an outliner, but an actual view of your scene. It doesn't have empty folders because that human-only-metadata thing isn't usually something you want to emply in actual data.

# Impose A Structure
You want your projects structure to match your mental model of the project. 

You can organize by what things are literally - armatures on this layer, and meshes on that layer - or by what things are - characters on this layer, background props on that layer. 

You could organize a song by recorded/synthesized, or by instrument type, section of the song, or whatever? It depends on the songs structure - you want to reduce the amount ot time you have to apply an edit/effect to multiple locations. So it depends on what things are sonically linked, as you determine it.

The divisons are never so clear cut. In a game engine, do you keep materials assets together, with the model assets that use them, or with folders from where you *got* them.

I can't answer that for you, it depends on your project. Often, software defaults are pretty light on organizing, as they can't really get away with imposing a structure on you. It's up to you to impose a structure on yourself. So... just pick one, and be consistent with it. 

Organizing assets by their source is nice if youre just testing assets and might want to delete them with one click, or if they are placeholders that will get replaced later. Organizing by game-element that uses the assets is nice when there's lots of iteration on that game element, like a characters design, and you constantly need to tweak things in tandem. Organizing by material type can make things easy to find in contexts where you care about the elements in a system (like multiple materials reacting to lighting in a consistent way). 

In Cinema4D, do your cameras/lights go in a collection, and your meshes in another? Do your lights stay conceptually linked with the things being lit by them, or in their own "lighting" collection. There's no right answer, it depends on your workflow.

Try different ones on a different project, and see which one you liked better. In Unity, I like my materials together and my textures with the mesh files. It doesn't make a lot of sense at first glance, but it works with my workflow: I edit textures when I am messing with the model asset, I edit materials when I am working on scene lighting. 

Find ways to isolate (and group) your projects elements in a way that makes sense to your workflow.

Take advantage of software (like game engines) ability to filter things for you. Filtering by file type is usually pretty easy, so feel free to impose a structure that *isn't that*, since you get it baked in for free. For example, consider naming all of your assets that are for the 'player character' with a consistent prefix ("p_"), or 'tag' or 'color', depending on the tool. Then you can type that in the filter/search box, and get a free new grouping, thanks to your naming scheme. Doing this, the structure you impose is free to more closely match your workflow or mental model of the project in other convenient ways.

No matter what, be consistent.

# Dont copy and paste edits
Use 'groups' of whatever kind to edit multiple things coherently. Use presets, prefabs, action-sets, or whatever theyre called to re-apply edits without re-creating them.

Create presets liberally.

# Non-destructive workflows
Some actions edit some data directly. Others save the edit operation as a piece of metadata while preserving your original unedited data. The cannonical examples are photoshops adjustment window, vs. its adjustment layers; or a DAW having filters being applied to the audio vs. creating an effects rack.

- In every piece of software I have ever used, a non-destructive approach has basically always been better. 
	- Are there exceptions? Of course. I spent a month 3D modeling entirely with a houdini-like 'geometry node' tree in Blender, which was much more annoying than the more destructive hard modeling or sculpting workflows. Using curves isn't always better than polygons, and sometimes you have to apply your dang modifiers/filters/adjustments/effects. 
- When you can do things a non-destructive or destructive way, err on the side of non-destructive. 
- Same for photoshop. Sometimes you need to clean your adjustment layers up and apply them. 
- I often make a copy of my things before doing a destructive action. Duplicate and hide the thing before applying a complex set of adjustments/modifiers/filters. Also, save-as the entire file. You can usually open old files up and copy/paste between them.
- Non-destructive workflows are absolutely KEY to not being forced into sequential operation workflows.

# Non sequential tasks
- Being able to go back to an earlier change and mess with it before returning to the later state is key. Having something like an adjustment stack, or so on, makes that easier.
- Lightroom is great at this. I can edit any part of my photo at any time. Compare that to having to first do the Adobe Camera Raw -> Photoshop for the same task. Or compare that to GIMP, which every edit is destructive. I hate using GIMP.
- Same for working with audio. Love the effects rack I use in Reaper, don't love applying the changes in Audacity.
- As much as possible, learn the tools that let you do things in any order, that let you re-order your operations, and so on.

Being creative is so much easier when you can go back and change your mind about something. Being paralyzed by decisions when you are forced to commit to something and move on *sucks.* It's better to not be forced into a sequence of operations, each one a point-of-no-return.

# Gain the knowledge to work out of a memorized order
Learning blender, tutorials teach parent/child relationships as this odd sequence of "click this first, then that, then press these buttons". They aren't wrong, but memorizing the task as a sequence is so much harder to build upon than learning the task a bit more holistically. 

This is true for all sorts of little tricks in all sorts of software pieces. We end up learning a way where if things aren't set up the same way, then we don't know how to do the trick. We can't come at it from the a different angle.

For the blender parenting example, one would have to go learn about what the different off-yellow highlight colors mean, which tells us what selection is primary and what selection is a secondary selection (i forget blenders officail names for this). This is the actual information that the parent-object action uses.

Knowing this information, it's easier to remember which one is which when parenting, and you don't need to think "okay, deselect everything. No select this, no select that."

I watch students edit photos, and often they do things in a consistent order - which is largely good. But they end up not learning how the internal systems are applying the edits - what order they go in - so they don't have as strong an ability to go make changes to the "earlier" edits, whose results are now less predictable. They struggle to work out of order. They need to learn how the edits get applied, and they'll just be *better* at image editing - or video compositing, or audio producting, or any sort of signal-chain work.

> Blender compositing, DaVince Resolve, Substance Painter/Designer, Isadora, and MaxMSP, have node workflows for image editing. In practice, nodes are a terrible way to edit images, but it *works really well* for mentally understanding the sequence/operations that are happening to the images: data pipelines. The application in Substance Designer is obvious, but even in DaVinci Resolves' case, data-pipeline structure is convenient for working with images together with time/animation/motion graphics. This is what it's mostly used for.
> For what it's worth, nodes are a pretty good way to edit shaders, which are quite similar to image editing systems.

# Name/Label Your Things
- Name your variables and functions usefully. Write the special comments that led your IDE use quick-documentation features on mouse-over. 
- Name your blender control empties. Name your Meshes. Name your Collections. Name your Bones.
- Name Your lightroom presets. Even if you don't use descriptive names, i often make a first name by calling my preset the image I created the preset with. "Where is that one setting I used on the photo of the moost? ah, moose2017." A terrible name, but memorable.
- Name your photoshop layers. You fucking monsters. Photoshop should add an option that when you create a new layer, it opens a GIANT popup that blocks your view of your art with a text box selected to type the layer name in. 
- Name your track buses.
- Name your GameObjects.
- Name your Effects Presets or Actions.
- Holy fucking shit just label stuff okay?

# "What makes a good name?"
This is a different essay. Maybe i'll write it. But just... it should be descriptive and disambiguating. And especially: 

# No Acronyms for Singular Things
Dont make something an acronym if its only going to be used in one context or setting, and especially if its only going to be used once! Stop doing that!

# Sequential vs. Non-Sequential Naming
Stop naming things sequentially (i.e.: numbered) (e.g.: 001, 002, 003) if the information they represent is NOT conceptually ordered, or if it doesn't have some inheirently sequental meaning (that we care about). Maybe it is ordered, like numbering things by time-of-creation, but often that order is *totally irrelevent* to the thing that the label represents, or our understanding/relationship to that thing.

	> An anecdote. In the game rocket league, there are two unofficial community "rule 1s". Rule 1 is to keep the ball up at 0 seconds, and rule 1 is also to stay in a headlock with another car. These are not actual rules in the game, more... social ettiquite where players do silly things and call it a rule. The big problem is there is a lot of argument about which rule is rule 1. Whichever way the player heard it first, for them, THATS rule 1. Numbers here are implying multiple things: is the rule the first one that showed up in the community? Thus, the number one? Or is the rule the MOST important rule in the community? Thus, the number one? Well the truth is that nobody cares and there is no right answer, it's all made up community BS anyway. A linguist or socialogist might have the tools to explain it. What I know: Numbering is a TERRIBLE naming convention! Its ambiguous as to what the number even represents! And everybodies opinions on what it COULD represent are as valid as anybody elses. So its stupid. The whole debate is stupid. And thats fine, and its a silly stupid thing that gives the game character. In my opinion, we should call keeping the ball up at 0 seconds just that (I will allow "playing keepsy upsies", as one esports caster charmingly put it), and "headlock" for the other Rule 1. To avoid chat spamming twitch channles with "Thats not rule 1! :(" some casters have just starting calling it headlock, and nobody performs the same useless conversation again, and we all move on with out lives. 
	> Yes this makes me arbitrarily angry. Dont use numerical labels in a context that is not numerical, or in a context where it's ambiguous what the numbers represent. 

One problem is we do use numbers in a coherent way, but we also use numbers in a incoherent way at the same time, and now i have to remember which ones are which. Is the file number the variation as I experiment, or the versioning of a file as I progress?

To solve the above problem, you could develop a consistent naming system. For files, I know an artist that always uses 'a,b,c,d' numbering (like painting-a, painting-b) for different variations/looks. For example, as they try different color palettes, multiple-of-which could be a "valid" version of the digital painting. They use numbers (painting-a-1.psd) for sequentially verisoning, where the highest number is ALWAYS the most recent, most important one. Nice and clean!

I've also seen projectVersionOne01.psd, ProjectVersionTwo01.psd and ProjectVersionOne02.psd. Same process as above, and even consistent, but its also absurd and easy to mess up.

> Here is your test: if the number comes from the order you created the thing, you need to rename it.

We want to work non-sequentially, without having to remember, or *ever care about* the order we made things. We want tobe able to pick up a project in the future without having to remember our *creation process* of it.

Audio Tracks are a good example. Most DAW's name your next audio track the new number, and it fucking sucks.

Sometimes you do want sequential names. Usually when representing sequential data. How about, when versioning your files, builds, mixdowns, or renders, instead of using "inProgress.psd", "file\_final.psd", or "file\_final\_final.psd", we use "output1.psd" then "output2.psd". When we are looking for the latest, or "correct" one, we just look for the highest number.

In fact, we shouldn't have to even scan for the highest number. We should name sequential files in such a way that our file explorer/outliner/project view can sort them alphanumerically, and they are just in order. So the latest one is at the top or bottom. 

# Create Workflow Systems

Tools and workflow are as important, if not more important than

# Learn Actions and the History State
For software where you use tools to edit some data, like *most software*, for example, lets say photoshop, some actions you perform will do a single thing on your data (canvas). like a brush stroke, or creating a layer. These actions get stacked onto your history stack (which photoshop has a great little 'history' window to let you see, visually, that I wish more software had. You can jump way up and back down, its great).

Other actions that you do *won't do anything to the stack.* For most of us "experts", its intuitive which is which. What actions I do that edit the data in front of me, and what actions - like changing my layout, zooming in or out, closing a window, etc - aren't adding anything to my undo history, and aren't actually affecting my data.

For beginners, especially those who have memorized something as a sequence of steps they take, or are following someone else, the distinction is not so intuitive. So, if youre a beginner, you should learn about what you can do that will edit your *actual thing, your file*, and what you can do that isn't that at all, often when changing your view/windows.

Some software can show little status updates for every action performed in a window, some software lets you see your history. But, you can always start by doing something, and then just seeing if you can undo it.

> Blender has the "Adjust Last Operation" menu, often called the "undo" menu for obvious reason. Instead of Undo-ing and re-doing, you can just press F9 and go edit the properties of the action. All software should implement this. It's great. 

# Give yourself more undo's
Software is tuned to run well on slow computers, less the internet complains about how much RAM photoshop is using. If you can, go to your settings and see if you can increase the number of history steps the software will save - the maximum number of times you can press 'ctrl+z'. Its 2021, you probably have enough RAM to at least double whatever the default is.

# Learn The Names Of Your Actions & Tools
I'm going to use "Action", but its also sometimes called "command", "operation", and sometimes "process" in different software.

Basically every action you do has a name. Scrolling through the photoshop history panel and you will see them. You will also see them in your regular old menus. FIle, Edit, all those friends? There they are, old familiar friends. 

Hover over your tools/icons to get a tooltip of its name. This is true like *most* of the time.

Other times, there will be a status bar, usually along the very bottom of your software, and it will say things like the currently selected tool, last performed action, and so on. God I wish more software implemented a status bar, or did a better job having it be informative.

If your software has place to edit your keyboard shortcuts, you just discovered a list of almsot every action your software can do. Look it over. Neat.

> In Blender, there is a menu called the 'n' menu. It's called that because you press the 'n' keyboard shortcut to show/hide it. It's actually called the sidebar.... I think.

Learn the names of your actions and tools. Just memorize them. Learning the names of what you are doing, and the official names of them. Don't grab the "finger pinch" tool, thats the *burn* tool. Dodge and Burn have silly icons for important reasons involving the history of photographic image development. It's not stupid and unintuitive, you are! Sorry. Im sensitive about dodge and burn. Respect your elders!

Learning the names isn't just an exercise of memorization. It's *really fucking important* for being able to learn the software by, say, reading the manual. Or following along on a tutorial. Or changing your keyboard shortcuts. Nothing will make learning software easier than knowing what the developers call the different parts of it, because thats what we *all* call the different parts of it, and it lets you communicate with other people (like someone teaching you, or a stranger in a video online) and understand what the heck they are talking about.

> Dear person making video lessons. if you are making a video lesson, please say the names of the things you are doing, and the names of the tools you are switching to. Don't just repeat your keystrokes out loud. Sincerely, Everybody.

Whats more, most software has a search box that lets you type the name of the action or tool you want. Adobe added a menu search in all it's software, Unity added ctrl+' quick-search, most text editors have an 'omnibox' that lets you type and search for any tool/action/file/class/variable/thing thats just *incredible*, and I wish all software had. 

> To this day, I do not know where the "flip normals" command is in Blender. I just memorized finding it via search. That's bad. Don't fall into that trap. You know what, just because I'm typing this now, im going to go learn. Okay! It's under the mesh>normals menu and I can open that quickly with Alt+N. I learned that shortcut by looking at the menu, it just had it printed out next to the action/command name.

While most software these days has a menu/action search, very few software really gets it to be universally helpful. Rider, VSCode, Sublime Text, and others, basically text editors  all do this super great.

On OSX, searching through menus is a thing in *all* software on a operating systems level. Knowing the name of the tool/action you cant find is so important, because it lets you find it easily! Just type it! 

# Stop Scanning
I hate google drive. Because it HIDES my data structure - my folders where i save things - and displays them in a "Smart" list, that is sometimes recent things, other times like, a document from 2004. What the fuck. But its unpredictable, and being unpredictable, it means I need to scan it, go down the list, and read the name to find what I want.

It sucks! Use office.com instead. EXCEPT OFFICE DOES THE SAME THING. (screams into pillow)

Instead, label your things clearly. Group them in collapsable ways. Use filters to re-order your information based on things like last modified, name, or file size. Stop scanning data. These examples are saving files, but they are also for inside your tools too. 

Basically, use the above search tool instead of scanning for tools. Uh, and memorize your tool layouts (but that comes with practice)

Audacity has this effect menu, and all the effects are in there, alphabetical. Except halfway down, theres a separate section thats also alphabetized. That stinks.

Knowing the names and category of things helps you stop scanning, because you know where it is in the alphabet, and where to first look to try and find it.

# Learn Tool Properties
Most tools have properties. Often saved in a properties window. Click different tools in the toolbar, and the property window contextually changes to show you the tools ... properties. 

It's wild how many users don't explore the properties of their tools. Especially 'brushes' in drawing/painting/sculting tools. Changing snap behavior, of brush strength, these things are so important. You don't need to be crazy precise! Just make your tool less sensitive and go to town. Make it easy to use!

One thing for brushes thats pretty universal, is like, more+weaker strokes instead of fewer+stronger strokes. Whether your scultpting in z-brush or painting in corel, give it a try.

# Passive Keyboard Shortcut Learning
Starting by learning the proper names of tools helps you learn keyboard shortcuts WAY easier. 

My favorite plugin in any software is a plugin in the Jetbrains IDE's called "Key Promoter X". Every time you do something with a mouse or menu, it opens a small unobtrusive pop-up, easily ignored, that says the name of the action you did, and the keyboard shortcut for it. Its a tool to learn keyboard shortcuts, and its amazing.

In most software, if you do open a menu, the shortcut should be listed right there. So take note, close the menu without selecting the thing, then try the shortcut. Nice. You're learning. Slowly.

# Stop getting lost
The first thing I do when teaching Photoshop is invite the students to just attempt to crash the software until they get stuck.

For Unity, I invite the students to change the window layouts to as rediculous a pattern as possible, something so absurd even I can't get back to normal. 

Then I go around and, usually just with a few keystrokes (tap 'esc', reset windows), return them all to sanity. Its an exercise that i hope makes them a bit more comfortable in the software - you aren't gonna break it by clicking wildly, feel free to experiment and click randomly more than you do. Nothing is gonna explode. It also teaches them how to reset things.

The important lesson here, is that you need to be able to travel to as obtuse a metaphorical hallway as possible. Lets say the software is a building. I should be able to drop you in any room of the building, and you could quickly and efficiently get back to the front loby. Some buildings are designed more sensibly than others, some have better signage/feedback. Some follow universal standards, some dont. 

Some software has different 'modes' (like Blender). Lots of software has tools that enter some 'mode' or 'state' that takes over your interface (try tapping escape), and lots of complex creative software has all sorts of panel/window layouts. 

Learn how to change panels, reset to defaults, open/close/split them. Learn what tools take over your mode. Learn how the software communicates its current mode to you, so you can find out where you are, and get back to the entrance lobby where everything is familiar and safe.

Oh, and doing it without messing up your actual file. Restarting the software is a not really a viable solution. That's important too.

If you can, have the software *tell* you what it's current mode is. Try to acoid using keyboard shortcuts that 'toggle' modes, and prefer ones that force you to choose what mode you are going to. Seems annoying, but it keeps you always directly aware when you switch modes, of where you came from and where you are going.

> In Blender, turn on the "Tab for pie menu" option, which makes you look at the mode you are switching to when you press tab, and makes it way harder to forget what mode you are in.

## Spend Time Setting Up Tools: Make Life Easy For Yourself
Stop taking shortcuts. Spend the extra headroom time setting you your tools to make editing and changing things easier. In the world of 3D animation, this is an entire career: rigging. A good rig allows an animator to deform a mesh without having to repeat actions, do counter-animation, or figure out integrals/derivitives. The property they want to animate is the property that is exposed, and everything works nicely.

Creating rigs takes time, and is hard. But ask any animator: the better the rig, the better the animation, and the less time it will take to do. Plus you save them from busy work, and they spend more time iterating, being creative, and making significant an unpredictable, non-automatable, changes. The ones that make the project better.

To a lesser extent, this is true in all software. Lightroom presets are a godsend to save you from repeative tasks. So are LUT's.

# Give Yourself The Right Feedback 

Please stop making life hard on yourself. Make life easy on yourself. Let computers do things computers are really good at, like working with numbers. 

When building a system:
- Add comments
- Write fragile code that breaks in the place where the error i
- Don't write "robust" code that is immune to receiving innaproprite inputs, sanitizing it silently. I want to know when i am giving that function the wrong input! Thats a different bug I want to be able to find! Let my code be a nice loud squeaky wheel when I am not using it correctly.

When working with data:
- Know all the different 'views' on the same data you can use.

When trying to align two objects, 1) use a snapping feature and let the computer do it for you. But 2) zoom in, switch to an orthographic camera with a side view, and just like... make it really easy to align the objects. This is an example and a metaphor. I think this is best explained with a list of examples.
- Change you virtual camera's perspective
- Stop squinting and zoom In
- The 'rainbow brackets' extension for IDE's that color matching () {} [] pairs.
- Switch to orthographic view
- Open your Histogram (you need to check your histogram) in photo editing software.
- Turning on highlight clipping alerts in lightroom or Capture One (or anything)
- View your audio track as a spectogram, or a waveform/spectograme top-bottom view, as I prefer.
- Video Editors have tons of color analysis tools. Histograms, Video Waveform, Vectorscopes, RGB Parade
- A node editors "preview up to selected node" feature. Substance Designer shows each nodes output in an icon.
- MaxMSP, Isadora, and most node-based software let you hover over various nodes and get insights as to what that connection is doing, its data type, etc. You can group and isolate nodes to test changes without messing with the rest of your system, such as with the 'viewer' node in Blender.
- Working on tones, not colors? Switch to black and white. Reduce the noise to your signal.
- Working on a single track? "solo" that audio track.
- Programmers, stop typing "print" or "Log" everywhere and actually learn to use your IDE's debugger. There are so much faster, easier, and more insightful ways to get an understanding of what your program is doing, and whats going wrong than a litany of console logs.
- Normalize your audio files so your post-normalization levels adjustments make clear, visual sense. Louder means louder and quieter means quieter. Nice! If your originals aren't normalized, and you lower the volume to make it a "normal" volume, that is unclear in the UI. It looks quiet, but it isn't. 

The suffixes "scope", "gram", and "graph" are gonna show up a lot. FInd them. Read them. Understand them. Having these tools is like most of the reason to be in the software in the first place!

## Know The Units
First, if the software has units, figure out what they are. Set up your interface to display them. (Not knowing when I have to type in degrees or radians is a constant pet peeve of mine).

Is your document in inches? pixels? centimeters? Work in units that make sense for your project! Which, probably means *not inches*. 

Work in units that approxamate reality. Modeling a car? Make it car sized. Adjusting physics settings in a game enginge? Use realistic weights. It's going to make life easier, **especially** when moving assets between different projects. Don't you want things to *just work* and not require tedius fiddling? 

Same goes for which axis is up. Is Y up or is Z up? You should know. Like "real world units", It's arbitrary, but it really matters when we move between software.

>If X is up, seek immedeate assistance.

## Context: Modes or Panels
In photoshop or Unity, everything is hidden in a window/panel, and you just have to go to the various correct one.

In Premiere Pro, Adobe Lightroom, or DaVinci Resolve, you switch between different modes, which change the panel/window layout, but the separation is distinct. Sometimes you cant even open one panel from the wrong mode. It changes the behavior of the software as you focus on different tasks.

Why the difference? Because the big picture modes change *other things too*, like your keyboard shortcuts. It's important to be aware! If youre used to photoshop, you are used to keyboard shortcuts that should *always do one thing*. But some software will *change what your keyboard shortcuts do* as you navigate different modes.

Some software tries to play it both ways, and your shortcuts can change depending on what window is currently selected, or what window your mouse is hovering over. This is annoying. 

> PTGui, a panorama stitching software, handles its different modes fairly elgently: It opens entire new sofware windows. Switching between them works the same way as any window in your operating system. The change in context is clear, returning to the original software is workflow is clear. Having multiple windows that edit the same thing isn't as confusing as it sounds. Frankly, its a great solution, and more software should probably stop spending time recreating operating system features like 'windows' and inventing its own unique way of changing them. Why not be inheirently universal and easy to learn? So I tip my hat to you: Unreal Engine.
> It's also baked in support for multiple monitors! Yes!
> If more software used multiple windows, and users got used to this paradigm - and operating systems got better at showing you feedback about these contextually grouped windows, like in the windows taskbar, the world would be a better place.
> But instead I am teaching you about photosop panels and their shortcuts, and unity panels and snap behavior thats *totally different.* 
> But whatever. Its not that bad, just learn it.
> Actually, lots of software *can* do this, like Unity and Blender and Maya and Cinema4D, and even Photoshop, but it can be annoying to set up.

So be aware. Learn the context and modes early, and always be aware of what mode you are in.

# Learn how to identify good resources
That thing thats called a tutorial, is it a tutorial, or is it just a guide.

Does this resource have a large plan in mind, or is it a small one-off thing? A chapter of a book has an editor and a whole book, and its a piece of a large plan someone put together that represents a holistic instruction. A single youtube video about doing a single thing is like, wtf is that.

Stop following along videos. As i type this i have a blender rigging video up on my second monitor, in the background. Watch the video. Pause. Do the action. Go back and watch the video. Stop doing it at the same time, you masochists. It's insane. Knowledge is for your brain, not your hands. The videos are for your brains! Not your hands! Your hands are great at repeating what you see, but they suck at doing it again when you aren't looking at it. So knowledge to brain, brain to hands. Dont look at the youtube video when you do the steps, and then, tomorrow, when you have to do it again, you can do the brain to hand action again. 

---
Universal properties of using different software. Most tools are variations on the spreadsheet, wordnproces


---
Enabling views of things like file sizes and file types will give you good important feedback. "but it adds clutter" thats only a problem if you are finding files by scanning for them. Name and organize your files well and that wont be an issue.

# The Right Kind of Lazy
When we work in software, we work with tools to create things. A lot of the tools are about the tools - such as labels. Changing a photoshop layer name has **no effect** on my final image. Beginners see this kind of "user-oriented" work as uneccesary or as time-consuming. Experienced creators know that the more they can create an easier workflow for themselves, - easy to see things, identify things, and especially change/tweak things - the less work they will have to do.

Because there will be changes. Iteration is fundamental to the creative process, and workflows that are not amenable to iteration are worse creative workflows. 

In other words, everybody takes shortcuts. Experienced software users are just smarter and more experienced about what shortcuts they take. 

Not to belabor a point, but lets consider - again - the shortcut of "not bothering to label things". (Or code comments, bad variable/function names, gameObject names, audio track Names, node group names, etc etc). Experienced software users know that minimizing the time they spend scanning over their lists-of-stuff saves them *tons* of time over the few seconds it took to rename something. It lets them stay mentally focused on the task they are *actually* trying to acheive. Renaming things *is* the shortcut. It reduces cognitive load, reduces time spent scanning, and reduces their need to reverse-engineer something after one has forgotten what it does.

Beginner users, perhaps those who have never worked on one project for longer than a week or so, have not experienced these benefits. From working on shorter projects, projects that only last as long as they are currently looking them, or simpler projects without as many moving parts, or whatever. In their experience, renaming things is the NON-lazy solution. "I don't have to remember this anyway because I won't even look at this project again after I close it."

Sure... but it also develops into a habit. Then one day, it bites our hypothetical novice in the ass. *Then* they rename something once, and goes "oh that's helpful".  

Okay, enough talk about comments. A lot of the advice that *feels* like "do it the non-lazy non-shortcut way" is actually experienced devopers **being lazy.** They're just being a smarter kind of lazy. From animation rigs to node groups to code refactoring, so much of a creators time is spent on things that don't directly affect the actual data output. It takes experience to understand that all of these "meta" things - be it a rig, color labels, or even entire code systems (code tests!), are the lazy way to do things. 