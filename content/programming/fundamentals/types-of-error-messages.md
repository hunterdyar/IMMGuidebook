---
title: Types of Error Messages
---
# Types of Error Messages
Not all error messages are created equally, and understanding the differences is important to being able to hunt down and squash the bugs that are causing the messages.

As far as C# is concerned, there are two types of error messages: **Compiler** Errors and **Runtime** Errors.

In terms of how you will encounter errors, I would like to add a third type: **IDE Errors**.

Lets go through them.

## Compiler Errors
When you compile code, it's the computers turn to try to read what you have written. It attempts to parse all of the symbols in all the files and turn them into machine code that it can deliver to the CPU. (This is a horrendously simplified summary).

If it can't parse what you have written - it reaches a symbol it doesn't know what to do with, or it doesn't know what a keyword means, or _whatever_, it will throw a compiler error.

Unity will not let you enter play mode when you have compiler errors. If you have been doing Unity development for any amount of time, you have probably seen this message before:

![Unity: "All errors must be fixed before you can enter play mode"](/images/programming/allCompilerErrorsMessage.png)

When this happens, head to the console:

![Missing Semicolon](/images/programming/errorsCompiler2.png)
The above errors are caused by a single missing semicolon. The compiler is smart enough to understand that a new expression began before the current one was terminated, so it gives us a fairly useful error message "; expected". It's not going to fix it for us, C# makes no assumptions, it doesn't know what your code is on about. If you wrote the code wrong, it's just going to stop and tell you so you can fix it.

The following errors are caused by removing the "using UnityEngine;" line at the top of the file. Suddenly all sorts of classes and functions that are defined in the UnityEngine library (like MonoBehaviour, Transform, Vector3) aren't defined anywhere, and the computer doesn't know what to do. 
![A Lot of errors from a single missing line of code](/images/programming/errorsCompiler1.png)

## Runtime Errors
Runtime errors don't happen when the code is compiled. They happen when the game is actually running. The most common are "Out of Bounds" error, when using lists or arrays, and a "Null Reference Exception". Both happen when we ask the computer to go look in memory for some variable, and there is no instance for it to find. 

For example, in a script that moves an object via a Rigidbody, we often store a reference to the rigidbody component in a variable.

{{< highlight csharp >}}
private Rigidbody2D _rigidbody;
private void Awake()
{
    _rigidbody = GetComponent<Rigidbody2D>();
}
{{< /highlight >}}
If we forget to type this GetComponent line, we will get the following error the first time the __rigidbody_ variable is used. There is no problem with the code's ability to compile. It only hits this error when the game is executing. 

![Screenshot of the famous Null Reference Exception error](/images/programming/errorNullReference.png)

Depending on the runtime error, Unity will pause execution right then and there.

## Clearing Errors
Runtime errors happen when the game is running, and they stick around in the console so you can review them, double click them to jump to the problematic line of code, and so on. If you fix the error - the compiler has no idea. This is a runtime error, we are only going to hit it because of some way the code is executing. The computer won't know it's fixed. Because of this, the error is just going to hang out in the console until we **clear** it. 

We clear errors by clicking "clear" in the console. This wipes the slate for us. By default, there is "Clear On Play" enabled, which will clear previous errors before entering play mode again. I recommend you leave this on.

A **really easy** mistake to make is to spend time trying to fix an error message, but no matter what you do, *it just wont go away*. It might already be fixed - but is a runtime error. So the code re-compiles without error, and you're good... but you still see a red X in the console. If an unfixable error is driving you mad, try just clicking the **clear** button and see if it simply goes away. 

Now, that doesn't guarantee that the actual problem is fixed, but at least you can run your game, maybe hit the problem again, and get back on the right track with debugging.

# IDE Errors
The Unity Console just reports what the Compiler says. You can receive errors from another source: Your IDE (text editor) analyzing your code for you, in order to help out. 

Remember the missing semicolon error?

![A Lot of errors from a single missing line of code](/images/programming/errorsCompiler2.png)

This is what it looks like in the IDE:

![A Lot of errors from a single missing line of code](/images/programming/errorsIDE1.png)

It gives me a red squiggly line under my code, and the message "Unexpected Token". It also gives me a warning that my name is incorrect. It's not how I name functions! Well, it's a variable, not a function (method). The IDE can't tell because of the missing semicolon. So that warning is irrelevant. Sorry IDE, you were trying to be helpful, but aren't as smart as you'd like to be.

I want to stress that "; expected" and "Unexpected Token" are different errors, and the compiler error is more useful in it's reporting, but the IDE error is more useful since it's right in context, and can often offer helpful suggestions and fixes. Or completely wrong suggestions and fixes.

The compiler error is the **real** error. It's the actual problem your code has. The IDE is analyzing your code and - before we attempt to compile it - trying to alert your of potential issues and problems. Jetbrains Rider is pretty good at this! Microsoft Visual Studio is also pretty good at it, calling it's solution "[Intellisense](https://docs.microsoft.com/en-US/visualstudio/ide/visual-csharp-intellisense?view=vs-2022)" and it's these same code-analysis tools that give us our helpful - or unhelpful - autocompletions.

These are just tools of the IDE. They're useful! But they aren't always accurate. Rider, by default, is pretty picky about your code style conventions (which is, to be fair, important and a good thing to be picky about), but it means students learning have lots of errors that *super don't matter right now*. Just be aware of what is a warning and an error, and make sure you are using a color scheme where it's clear to tell the difference. 

Don't let your IDE get in your way. When you're in the middle of fixing lots of errors, it can be helpful to jump over to Unity, let it attempt to compile, and give you new error messages. Compiler error messages are consistent and usually very helpful.

## Video Review
{{< youtube xISgtKeLWQU >}}