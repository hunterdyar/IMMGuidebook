---
title: Syntax of Variables and Functions
type: docs
weight: 1

---
# Basic Syntax: Variables and Functions

## Variables 

## Declaring Variables

The keywords to declare a variable are as follows:
> [**scope**][space][**type**][space][**variableName**][semicolon]
> 
> scope type variableName;

When naming our variables, we use lowercaseCamelCase. Also called [pascalCase](https://en.wikipedia.org/wiki/Camel_case). 

You cannot start a variable with a number.

{{< hint info >}}
C# requires that we  declare the variable type. We can't just say "let x be some variable. A number? A word? I dunno, you figure it out". You can think of types as letting the compiler know *how* to interpret the sequence of bits (1s and 0s) that the variable is storing. Does **01011001** refer to the 8-bit binary number 89,  Or the ascii character code for "Y"? In every programming language, the computer needs to know, and in C# it's our responsibility to tell it.
{{< /hint >}}

Common data types are: *string*, *int*, *float*, *bool*, *char*. 

### Declaring data variables:

{{< highlight csharp >}}
public string weUseCamelCase;//Variable names uppercase every word except the first, and cannot start with numbers. We do not use snake_case.
private int someNumber = 4;//you set values during declaration
bool isAwesome = true; //The scope is 'private' by default, so we don't have to type 'private'. 
{{< / highlight >}}

### Data Structures
Declaring structs is very similar to regular variables. We just use the type of the struct for the type:
{{< highlight csharp >}}
private Vector3 someVelocity;
public Quaternion rotationStorage;
Vector2 inputDir;
{{< / highlight >}}

Where it differs is how we create structs. Structs use the same constructor/deconstructor syntax as classes. We type "new" then the type name, followed by parenthesis, and then we put our appropriate values in the parenthesis like parameters to a function. 
{{< hint info >}}
Vector3, the most common struct we use in Unity, takes 3 float values for its x, y,and z values in that order.
{{< /hint >}}

{{< highlight csharp >}}
private Vector3 someVelocity = new Vector3(0,0,3);//0 on the x axis, 0 on the y axis, 3 on the z axis.
Vector2 inputDir = new Vector2(-1,0);
Vecto2 newInputDir = inputDir;//We don't need to create new variables, we can copy other structs values.
Vector3 otherDir = Vector3.right;//Here we copy a built-in variable, see below.
{{< / highlight >}}

{{< hint info >}}
Vector3.right is a [shorthand](https://docs.unity3d.com/ScriptReference/Vector3-right.html), its basically an already existing variable thats equal to Vector3(1,0,0). In the above example, we simply copied these values into our variable. Vector3.right (and the other short-hands) are much easier to type than "new Vector3(1,0,0)", and makes the code easier to understand when reading it..
{{< /hint >}}

### Declaring Classes
The syntax for variables that store a class *(or a reference to an instance of a class)* is the same as structs. "private Thing something = new Thing();" There is just one notable exception: They do not have default values. When you declare a class, it will be null. We have to either set it equal to a new instance of the class. ( =new Thing() )

## Functions

The Syntax for a function is simple. Just like variables, we start with the scope (public/private), then the return type, and then the function name (CapitalizedCamelCase). What makes a function a function (syntactically speaking) is parenthesis. They follow the function name without a space.

The parenthesis hold are 'arguments' or 'parameters', but even when we don't have any arguments, we still need the parenthesis. The () is how we can always recognize a function. After the parenthesis we put curly braces, which contain the code that makes up our function.

> [**scope**][space][**returnType**][space][**FunctionName**][(parenthesis)][{curlyBraces}]
> 
> scope returntype functionName(){}

{{< highlight csharp >}}
private void Start()
{
	//Code here, indented.
}
{{< / highlight >}}

### Creating Functions With Parameters
To pass data into a function, we declare variables inside of the parenthesis. We declare them like a regular syntax for declaring a variable (without scope), inside of the parenthesis, separated by commas. They can only be used inside the function.

{{< hint warning >}}
Variables created this way are called "parameters" or "arguments".
{{< /hint >}}

{{< highlight csharp >}}
private void GiveMeSomeNumbersToWorkWith(int a, int b)
{
	//This code now has two integer variables to work with, a and b.
}
private void GiveMeOtherInformation(string words, int andANumber)
{
	//This function has been given a string variable and an integer variable.
}
private void GiveMeOtherInformation(float someNumber)
{
	//This function has the same name as the above function. This is allowed so long as the paremeters are different.
}
{{< / highlight >}}

{{< hint info >}}
Functions with the same name but different parameters are allowed in C#. We would say it has a different "method signature". One would expect the functions to do the same thing. This is a way of writing the same function multiple times, except to allow for different types of input from the parameters. We have seen this with the "Instantiate" function from the intro roll-a-ball lesson.

Take a look at the [documentation for the Instantiate](https://docs.unity3d.com/ScriptReference/Object.Instantiate.html) function built into Unity. Notice it has a number of different declarations. {{< /hint >}}

### Indentation and spacing
{{< highlight csharp >}}
//C# Does not care about line breaks.
private void Start(){}
{{< / highlight >}}
{{< highlight csharp >}}
//C# Does not care about line breaks.
private void Start()
{//We put the first curly brace on a new line
	//we indent every line of code inside of the curly braces
	if(something == true)
	{
		//Some other code inside curly braces, indented again.
		Debug.Log("something is true.");
	}
}//the closing curly brace is at the same indentation as the first one, so we can tell which ones go with which.
{{< / highlight >}}

### Calling Functions
To execute a function, we just type the name of the function followed by parenthesis, and a semicolon. Just like any other statement in C#

{{< highlight csharp >}}
private void Start()
{
	SayHelloWorld();
}
private void SayHelloWorld()
{
	Debug.Log("Hello, World");
}
{{< / highlight >}}

{{< hint warning >}}

"Executing", "Running" and "Calling" functions are all perfectly fine ways to refer to the same thing: make it do it's thing.

{{< /hint >}}

If the function has parameters, we pass those in, in order, separated by commas. We can type the values directly, or use a different variable whose value or reference will be passed along.

{{< highlight csharp >}}
private void Start()
{
	SayHelloToMe("World");//prints "Hello, World"
    string myName = "Abby";
    SayHelloToUs(myName,"Ben","Chris")//prints "Hello Abby, Ben, and Chris."
}
private void SayHelloToMe(string yourName)
{
	Debug.Log("Hello, " + yourName);
}
private void SayHelloToUs(string a, string b, string c)
{
	Debug.Log("Hello "+a+", "+b+", and "+c+".");
}
{{< / highlight >}}