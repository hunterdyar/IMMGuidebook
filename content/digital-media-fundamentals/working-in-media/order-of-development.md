---
title: Order Of Development
oldlink: https://guidebook.hdyar.com/docs/digital-media-fundamentals/order-of-development/
---
# Order Of Development

Work along your protects primary axis. Different projects require different workflows, and identifying this is often challenging for beginners.

Generally: work out a draft and refine. What constitutes draft? What elements are refinement? What is necessary for understanding core, fundamental, parts of your project?

In animation, One doesn't animate Start to finish, timing is a key part or animation, so the animator starts with notable moment poses, and timings, and places key frames first, then they go add the in between frames, after spending time tweaking the timing. *You need to find the "key frames" of your project, and get those down before worrying about the metaphorical "in-betweens".*

A digital painter does not paint element by element. They block out the composition. It's harder to change a large composition after the fact, since it will mean re-doing a lot of the detail work. Thus, you want to save that detail work for later in the progress.

For whatever tool or workflow, the goals involve minimizing work and maximizing iteration and feedback.

When a sculptor makes a statue out of marble, it would be ridiculous for them to go top-down, such that they never go back to a previous area twice. This is obvious! Yet for whatever reason, programmers never seemed to think this applies to them. "Refining a script? That just means you didn't write it well enough the first time!". This thinking is absurd. Hey programmers: stop implementing subsystems before you have your core gameplay working.

## Determining What Goes First
Have some kind of plan or concept in mind. I can't believe I need to say this, but that's where it starts. Don't just open the software and start clicking.

Frontload large parts of the project that will change and affect other elements. Sketch it out first.

Determine what elements are blocked. Are there discreet stages to development? Working non-destructively can't always be avoided, and you don't want to refine your print-making process before you've got your negatives developed how you wan them.

## Prioritize The Feedback You Need

The less you have to do before looking at it and going "hmmmm", the better.

For animators, start with the timing and poses.

For game developers, focus on the core game loop. Animating the character, nice particle effects, implementing audio - none of that matters until you have your tight core gameplay.

## Bypass Intuition

Level design starts with a block out. Music starts as loose sketches and loops. A painting begins with a sketch. Better artists **don't need** better intuition, they work in a way that lets them visualize early and visualize often. They bypass the need for intuition. By being smarter about where they focus their attention. They put things on the 'page' that are difficult to imagine (visualize), and test those first. Artists are always frontloading iteration, talented artists make working easier on themselves.

A character design doesn't need to be inked and colored before the artist understands if the pose and proportions are correct.

But this is true in less obvious cases than a drawing. In game design, you really need to start with the core game loop, the fundamental elements to the players' experience. I can't stress enough how important it is to get gameplay to be *fun* before you make it look good or be bug-free. You don't need to be a brilliant genius able to imagine complex interactions of systems, you just need to be able to make prototypes, give and take feedback, and iterate.

## Prioritize Things that Affect Other Things
Do the big things that affect other things first.

In a game, this might mean implementing your core gameplay manager before implementing your audio manager. Not because the audio manager is less *important*, but because the design decisions of other systems probably won't affect how the audio manager is implemented. But the design decisions of many systems (including the audio manager) probably cares about, say, how your event system is implemented. So do those earlier.

This obvious advice often gets ignored because it's hard to make a decision about something precisely *because* it affects so much else, and it's easy to work on some compartmentalized subsystem with confidence that you won't be messing up your future-self and re-doing work.

Even with the most cleanly architected systems, you need to just accept that you will have to re-do some work, budget some time to let that happen, and just get started on the big stuff early.


## Get External Feedback Early
Getting feedback from outside sources is self-explanatory, but only *possible* when you work in an appropriate order.
