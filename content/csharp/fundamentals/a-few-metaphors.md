---
title: A Few Metaphors
oldlink: https://guidebook.hdyar.com/docs/programming/fundamentals/a-few-metaphors/
---
# A Few Metaphors
I  generally do not like teaching with metaphors. They can provide quick high-level insight, but I find they can get in the way when we wish to expand on the high-level concept in lower-level ways. It's like learning a mental trick to do multiplication - you might be presented with a problem that you _know_ the answer to, having memorized it, but instead of simply having it, you find yourself walking through the steps of your "trick" in your head. The shortcut has become an impedance.

It must be stated that they are not useless, particularly _after_ one has become mildly comfortable with a concept and it's applications. So, all this being said, some programming metaphors.

## Function Properties are Pronouns
Inside the "local context" of a function, we write code to work on unknown properties. We use placeholders, and they serve much the same function that a pronoun does in language. Many placeholder words exist in the English language, not just pronouns, like "it", "that", "thing", "what's-it", "thingamajig", "doodad", "you-know-who", "John Doe", and so on.

{{< highlight csharp >}}
void Square(int them)
{
    Debug.Log(them * them);
}
{{< / highlight >}}

I can write a function - and speak a sentence - that is perfectly syntactically and programmatically - and grammatically - sound, while not actually knowing _who_ "them" refers to. The function will not, until it is executed by the program.

## Procedures are Flow Charts
Consider the equation to convert a number in Fahrenheit to Celsius: Subtract 32, then multiply by 5/9ths.

We could more concisely write this as a mathematical formula:

![The equation for F to C written in clear mathematical notation](/images/programming/FtoCMath.png)


There are a number of operations that we must evaluate in the correct order. x-32 and 5 divided by 9 each must be evaluated, and then the answer to those operations should be multiplied. In that order. In mathematics, the order of operations ("PEMDOS") provides clarity. In programming, PEMODOS is used as well, but there are further methods to control the way a process is executed. 

Instead of thinking of order-of-operations, one might consider the each operation as some block with inputs and outputs, and we evaluate the entire thing from left to right.

![The equation for F to C visualized in Blender's Geometry Nodes](/images/programming/FtoCGeoNodes.png)

Each grey line represents a number, connected from the output of one "function" or "process", and determined by it's various inputs.

This visualization can be quite useful for understanding programming, as it clearly shows how complex operations are grouped and chunked, and one can always trace a piece of data as it get's processed. Many programming languages directly use a "flow" metaphor as their interface. From older languages like [Fabrik](https://web.archive.org/web/20070927190552/http://users.ipa.net/~dwighth/smalltalk/Fabrik/Fabrik.html) to complex and modern systems like Unreal Engine's Blueprints. 

Without switching to a 'visual' language, one can take advantage of flow-chart diagrams. Programmers often scribble such charts on whiteboards (to varying degree's of clarity or legibility, often just enough to get a sense of what they want to do as a visual structure). Understanding their process in the visual "readable" version then becomes a helpful reference when returning to the less visually parse-able code.

## Code is Recipes
When we code, we are creating abstract processes that can be followed by a machine. One does the same thing when writing a recipe, only it must be followed by another human. One uses shorthand and shortcuts, and only the minimal of instructions, because the one cooking surely knows what "mix" and "chop" mean, and mostly need to be told which ingredients to combine, how long to bake, and how finely to chop the onions.

Yet, as any chef knows, communicating _exactly_ what one should do can be a challenge. 

{{< youtube NywzrUJnmTo >}}

## Road Networks
Programming is not like driving. Programming is like designing and building out a road network. One full of streets, signs, and so on. We create repeatable small structures ("stop sign", "left turn lane", "speed bump"), and build out a system that can be navigated not just by one car, but an entire system ("city"?) of cars, all going their various ways.

A single traffic light can be setup and thought through. Let traffic flow along this path, then along that path, and signal appropriately. The challenge in programming isn't often creating an elegant traffic light, but designing a series of them to work well together. Hundreds of traffic lights in a complex network, and if even just one is misbehaving, the result can cascades out of control and quickly become chaos. 

## Writing
[Writing Software is Like ... Writing](https://www.artima.com/weblogs/viewpost.jsp?thread=255898) blog post by Bruce Eckel, 2009.
