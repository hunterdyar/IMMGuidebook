---
title: Syntax of Code Flow
type: docs
weight: 2

---

# Code Flow

Inside of functions, there are a number of different ways to change how code executes. Without messing with code flow, and just having a bunch of statements, code will execute top to bottom, left to right. Code flow is how we get more complicated.

There are 2 main ways to manipulate code flow: Branches and Loops.

Branches, which will likely never be referred to as "branches" again, are a way of executing functions *only in some situations.* We have two main forms: **The If Statement** and **Switch Statements.** Lets ignore switch statements for now, and focus on the if statement.

# Statement
A statement is an action of a program. Usually, a single line of code is a statement. We generally end our statements with semicolons. Statements are the code _doing some single thing._ 

Declaring a variable? Thats a statement. Assigning it a new value? That's a statement.

## Statement Blocks
Any code inside of curly braces could be considered a **block**, or **statement block.** We contain a number of statements inside some curly braces, and now we can put multiple statements, wrapped up in curly's, and treat it like one statement from the outside.

## The If Statement

The If statement takes a [conditional]({{< relref conditionals >}}) and will only execute statment if the conditional is true.

The syntax is: the word if, followed immediately by parenthesis that contain a conditional. The code will execute or not execute the statement that follows it depending on the conditional.
{{< highlight csharp >}}
if(conditional == true)
    DoSomething();
{{< / highlight >}}

Except, you should basically never write your if statements without using a statment block -- curly braces. We use a curly braces basically 100% of the time. The above is valid, and considered a shorthand, but we want our code to be consistent and readable. So, in practice, the syntax of an if statement is: 

The keyword 'if', followed by parenthesis that contain a conditional, immediately followed by curly braces.

{{< highlight csharp >}}
if(conditional == true)
{
    DoSomething();
}
{{< / highlight >}}

## The If-Else Statement

The 'else' keyword can be added to after the if statement to provide some code that will only happen if the conditional is false. It's like an "otherwise" clause.

{{< highlight csharp >}}
if(conditional == true)
{
    DoSomething();
}
else
{
    DoADifferentThing();
}

if(conditional == true)
{
    DoSomething();
} else //programmers will fight over the appropriate line spacing of the else statement. I have no strong opinions. 
{
    DoADifferentThing();
}
{{< / highlight >}}

You can chain if-else statements together
{{< highlight csharp >}}
if(inputDir == Vector2.left)
{
    MoveInDir(Vector2.left);
}
else if(inputDir == Vector2.right)
{
    MoveInDir(Vector2.right);
}else if(inputDir == Vector2.up)
{
    MoveInDir(Vector2.up);
}
else if(inputDir == Vector2.down)
{
    MoveInDir(Vector2.down);
}else
{
    StopMoving();
}

{{< / highlight >}}

# Loops
Loops allow us to execute a statement block multiple times.

The simplest loop is the while loop.
## The While Loop
It's basically the same syntax as a simple if statement, but with the keyword while.

So long as the conditional is true, the code in the blocks will execute.

{{< highlight csharp >}}
while(true)
{
    //The word 'true' is always true, so this code will run over and over again forever and crash your computer.
    //This is called an infinite loop, and every programmer has made this mistake at least once.
}
{{< / highlight >}}

We can use a while loop and an integer to build a simple counter.
{{< highlight csharp >}}
int i = 0;//A
while(i < 10)//B
{
    //Some code we want to run multiple times.
    Debug.Log(i);
    i = i + 1;//C
}
//This will spit out 0 - 9 in the console. 10 numbers, starting at 0, and going to 9 - not including 10.
{{< / highlight >}}

It turns out this little pattern is really common. We have some code that happens before the while loop (labeled A, above). Then some conditional we check every loop (i<10, labeled B). Then some code we run every single time in the loop (labeled C).

This pattern is so common, that the programming deities gave us a nicer way to type it out: the **for loop**. 

## The For Loop

{{< hint warning >}}
Actually, the for loop first appeared in ALGOL 58, a programming language developed in 1958, 63 years ago as I type this.
{{< /hint >}}

The for loop is simple loop that is much less prone to accidentally writing infinite loops. It's syntax is:

The keyword for, followed by three statements inside of the parenthesis, seperated by commas. Then a curly brace containing our loop.

{{< highlight csharp >}}
for(A;B;C){}
{{< /highlight >}}


The A,B,and C's here match the functionality of the code labeled A,B, and C in the while loop example above. 

The statements are:
- A: something that happens once at the top of a loop.
- B: a conditional
- C: something that happens every loop.

99% of the time we:
- A: Create a variable. int i = 0;
- B: Compare it to something. A < 10;
- C: Increment it: i++;

{{< highlight csharp >}}
for(int i = 0;i<10;i++)
{
    //do something 10 times, with access to the variable i.
    Debug.Log(i);
}
{{< / highlight >}}

{{< hint info >}}
We always use the variable "i" for a counter integer. i for iterator. 
{{< /hint >}}

{{< hint info >}}
i++; is shorthand for writing i = i + 1; It's just a little bit tidier.
"++" as an operator will add 1 to the variable to it's left. 

Similarly, i-- will subtract one from a number.
{{< /hint >}}