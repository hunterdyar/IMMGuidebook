---
title: Conditionals
type: docs
weight: 2

---

# Conditionals

Conditionals are anything that can be true or false.

## Boolean
The simplest conditional is a "boolean" data type. A boolean is a variable that can be equal to either "True" or "False", and Nothing else. They are stored as a single bit, a 1 or a 0, so they *literally,* can only be true or false.

In C#, and in most programming languages, this data type is called "bool".

{{< hint info>}}

The word "Boolean" comes from a mathematician named [George Boole](https://en.wikipedia.org/wiki/George_Boole). 

{{< /hint >}}

{{< highlight csharp >}}
private bool trueOrFalse;//false by default.
private bool isAmazing = true;
{{< / highlight >}}

{{< hint warning>}}

We often use "is","are","can", and similar prefixes in our variable names. (sucha ss "bool isCool;"). This naming helps us read the code, it's is grammatically easy to understand that this variable is something true or false.
{{< /hint >}}

## Conditional Operators
Booleans are great for storing something that is true or false, but they don't help us dynamically determine if something is true or false. For that, we need operators.

You are probably familiar with mathematical operators:
-  plus: \+
- minus: \-
- multiplication: \*
- division: \\

> In programming, an operator is like shorthand syntax. It's a symbol with data on either side of it. It takes the left and right side of it, and tehn returns a new data value. The "+" operator takes two numbers to either side of it, mathematically adds them together, and returns the new single number of whatever their  their sum is.

Conditional operators returns a boolean. Common conditional operators:
- Greater Than: >
- Less Than: <
- Greater Than or Equal To: >=
- Less Than or Equal To: <=
- Is Equal To: ==
- Is Not Equal To: !=

{{< hint info>}}
Pay attention to the  >= and <= operators We cannot flip around the greater than or equal to signs. => and =< are different symbols that mean something else.  => is a '[lambda operator](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/operators/lambda-operator)', and  would be gibberish to the compiler in the context of a conditional.
{{< /hint >}}

{{< hint info>}}
Also note the == operator. In C# programming, one equal sign (=) will very specifically take the right hand value and **assign** it to the left hand side. Two equals signs (==) will compare the left and right hand sides, and then evaluate if they are equivalent or not. They are used in completely different ways. 

Unfortunately, in english, we say "equals" for both of these different things. I recommed you read "==" as "Is Equal To?" and "=" as "is".
{{< /hint >}}

## Logical Operators
Logical Operators are used to connect multiple conditionals together to form another greator conditional. Like all operators, they consider the information to their left and their right (in this case bools), and they give us a new value, another bool.

Logical Operators:
- And: &&
- Or: ||
- Not: !

{{< hint warning>}}

The | is the 'pipe symbol', it's often located above the enter key on keyboards. OR is two pipe symbols: ||.

{{< /hint >}}

The AND operator will return true if either side of it are both true. If one or both of them are false, then it will be false.

- true && true == true
- true && false == false
- false && true == false
- false && false == false

The Or operator will return true if one or both of its sides are true.
- true || true == true
- true || false == true
- false || true == true
- false || false == false

{{< hint info>}}

Why two ampersands, or two pipe symbols? It turns out you can use single ones too.

The operator evaluates either side of it. The code on the left evaluates first, then the code on the right. For an AND operator, if the left side is true, it doesn't matter what the right side is. The double && and double || versions of the operator will **not** evaluate the right-hand side if it isn't needed. This is more efficient code, and considered good practice.

Read about them in the [official documentation](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/operators/boolean-logical-operators).

{{< /hint >}}



---

Of course, we can combine conditional operators and logical operators in complicated ways. When we do so, we can use parenthesis to disambiguate our order of operations, just like in algebra. 

> ! is not an operator in the way I described operators above, with a left and right side. It's more of a prefix. It's still called an operator in the more broad programming syntax sense of a symbol that has a special purpose and meaning.

See [Syntax of Code Flow]({{< relref "syntax-of-code-flow" >}}) for an explainer of if statements, the most common use case for conditionals.

{{< highlight csharp >}}
int a = 4;
if(a < 5 && a > 0)
{
	//a must be 1,2,3,or 4 for this code to run.
}
{{< / highlight >}}

{{< highlight csharp >}}
int a = 4;
int b = 5;
bool runAnyway = true;
if((a < b && b == 7) || runAnyway)
{
	//a must be less than b and b must be exactly 7, or runAnyway is equal to true.
}
{{< / highlight >}}

## Not
Also called the "[Logical Negation Operator](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/operators/boolean-logical-operators)". A ! placed before a conditional will negate it, flipping it from true to false and from false to true.

- !true == false
- !false == true
- !(a == b) and (a != b) evaluate the same

{{< hint warning>}}
The ! symbol is called "bang", which is much easier to say than "exclamation point".
{{< /hint >}}

{{< highlight csharp >}}
//Hypothetical jump code for some game
bool inTheAir = !CheckIfGrounded();
//We read this part as "if JumpKeyIsPressed And Not inTheAir". 
//This is almost grammatically coherent. Naming variables and functions in this way can make your code easier to understand
if(JumpKeyIsPressed() && !inTheAir)
{
	Jump();
}

{{< / highlight >}}

