---
title: Hierarchical Data Structures
oldlink: https://guidebook.hdyar.com/docs/programming/fundamentals/hierarchial-data-structures/
---
# Hierarchical Data Structures

### Introduction
Hierarchical data refers to a structure of data. Data - whatever it may be - is linked to other data in parent/child relationships. Understanding Hierarchial data structures is important to operating computers, and learning programming in general.

The good news is: It's fairly simple! The grammar for describing this is as complex as the concept itself. That's one of the *problems* with programming - it's complicated and challenging to talk about some programming concepts (like describing a data structure) with language. A lot of learning programming is going to start with learning jargon and vocabulary. By the time you have that sorted out, you're probably 90% the way there with understanding the concept. In other words, the concept isn't usually, fundamentally, the hard part - it's learning how we communicate and parse it.

---

### Understanding Hierarchical Data Structures

Before we start programming or working with Unity, it is nice to have a broad understanding of Hierarchical data structures.

The idea is simple. Things can be made up of other things.

Lets think about how we describe things grammatically. In order to communicate effectively, we often use shorthand, grouping things together into a single concept and talking about that concept. This grammar could be modeled with a hierarchial data structure.

Lets say I was speaking to someone about improvements I wanted to make to my desk. What do I mean by "desk?"

My Desk is a desk-top, desk legs, computer chair, as well as various accoutrement on my desk, my computer monitors and their mounts, and relative position of all of these things to each other.

I can point at the entire thing and say "that's my desk", or point out the desk legs, which are part of the desk. My computer mouse is also part of my desk, despite also being a completely unique object as well.

I have a large concept of "desk" that is composed of many smaller elements. In language, the borders between categories often break down when we examine them in detail (Is cereal a soup? Is a hot dog a sandwich? It doesn't matter). In programming and with well designed data structures, we don't have to worry about that ambiguity.

![Matroshka](/images/programming/matroshka.jpg)
*Russian Matroshka dolls by Wikimedia commons user Fanghong.*

### Unnecessary Note On Context-Shifting
> I probably am not referring to my computer when talking about improving my desk, but I am referring to my computer when I tell someone "give me a second, I'll email you when I get back to my desk". The meaning of "desk" has changed as the context it is used in has changed. This complexity of language is something we don't have to worry about with how we use hierarchial data structures in computers. In Unity, if I create a desk, I will only ever mean the same specific list of arbitrary things that make up the desk. So Unity is simpler than real life day-to-day communication!

If you can handle the literary comprehension challenge of parsing all of these sentences, you can definitely handle computer programming.

## Enough About Desks

"Hierarchial Data Structures" is a new name for some old concepts you are likely already familiar with. And, frankly, the name itself ("Hierarchial Data Structure") is the least important part of all of this. You can forget it completely if you want. There will not be a vocabulary quiz.

It's simple to see that things are composed of other things. We don't edit computers by changing the 1s and 0s with [a steady hand](https://xkcd.com/378/) - there are layers of abstraction. The key insight with hierarchial data structures is that we can identify what a thing "is" at every layer of it's of assembly.

A color, in Unity, is defined by 4 numbers. Values for Red, Green, Blue, and Alpha (Transparency). That's all a color is in Unity, just 4 numbers. (With color, we call these values "[channels](https://en.wikipedia.org/wiki/Channel_(digital_image))").

In Unity, a "color" is just a container for 4 numbers. It's a meaningful and useful container.

See [Color.adobe.com](https://color.adobe.com/create/color-wheel) for an interactive color picker. It provides sliders to control the underlying RGB properties. There are other ways to represent colors (for example: CMYK, HSB, and LAB). This is a digression, so I'll leave an exploration of representing-colors-with-comptuers as an exercise to the reader.

In Unity, It's useful to collect numbers into containers like this all the time. The most common one is probably "position", which is made up of three number values, representing positions on an x axis, y axis, and z axis; together a single position in a cartesian coordinate system. I.E. a point in 3D space.

That way, every time I wanted to, say, make something red I could just tell the computer to "make something the color red" instead of telling the computer to make something "100% on the red channel, 0% on the green channel, 0% on the blue channel, and 100% on the alpha channel." That would get really tedious if I had to explain every component the computer needs every single time. But I have a single data object that represents red, it has the appropriate RGBA values for red, and I can just refer to that

> Alpha means Transparency. The word 'Alpha' comes from the greek letter which was used by mathemeticians in a formula (for linear interpolation). While the etymology is arbitrary, it has stuck around.

In the same way, I could describe a 3D model by it's parts: mesh data, texture data, color data, etc. So in the same way, its nice to just be able to say "this 3d model" instead of "this mesh data, texture map data, vertex color data".

#### Continuing the example:

The hypothetical 3D model is composed of *things*, and these things can also be containers for other things. It's "things" all the way down! *Note: all the way down, in the case of computers, eventually lands us into a pile of 1s and 0s.*

A 3D Model has its mesh data (think: shape) as well as a material (think: paint). That material may include a color, which includes a numerical value for the red channel.

We can translate this sentence into a sentence a little closer to computer grammar:

> 3d model has material which has color which has red channel value.

And we can move all the way from language to programming "dot-access" syntax:

> model.material.color.r;

I can refer to the information at any point on the hierarchy. (model or material or color or r). What I am referring to will include the collection of all of the data pieces contained within it. Many computer languages use dots as the grammar that says "the right side of this dot is a property of the thing on the left side of this dot".

It's data all the way down! That's Hierarchical data structures!

### It can't actually just contain other things all the way down, eventually it has to be something.

It's not sub-data **all** the way down. We are collecting layers of abstraction until eventually you get to "real" data. That's 1's and 0s, but we never go quite that far. We stop at: Numbers, Sentences, Characters, True/False information, and... well pretty much just that. Sometimes we have to pay attention to [unicode](https://en.wikipedia.org/wiki/Unicode) and [ASCII](https://en.wikipedia.org/wiki/ASCII), or various forms of encoding, but all of the details on what layers of abstractions computers are built on is a topic for another time.
