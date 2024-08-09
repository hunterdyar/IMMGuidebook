---
title: Object Oriented Programming
---
# Object Oriented Programming

Object oriented programming is not unique to C# programming. The concepts introduced here are utilized by an incredible number of programming languages. Java, C++, Python, R, Ruby, Swift, and Perl are some other languages that use an object-oriented paradigm.

Object oriented programming is programming around data structures that contain variables and functions.

{{< hint info >}}
There are three main "pillars" of object oriented programming: Encapsulation, Inheritance, and Polymorphism.
_Depending on who you ask, there is a fourth pillar: Abstraction._

We will be introducing and discussing [inheritance](https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/object-oriented/inheritance) here, but leaving [encapsulation](https://en.wikipedia.org/wiki/Encapsulation_(computer_programming)) and [polymorphism](https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/object-oriented/polymorphism) to the side for now.
{{< /hint >}}

This lesson is really about two main concepts: **Classes & Objects**, and **Object Inheritance**.

### Classes & Objects
**Classes** are definitions of data structures and available functions (operations, methods) that one can do with the data.
**Objects** are instances of the class.

### Inheritance
Inheritance is the primary tool that allows for code flexibilty and code reuse. It allows data structures to share properties of one another, by having one class _inherit_ or copy the various setup of another class as a starting point.

All of the scripts we have been writing in Unity, so far, have been inheriting their properties from "MonoBehaviour", which is the UnityEngine term for "component". This inheritance is what has allowed us to drag and drop these behaviors onto GameObjects, and allowed Unity to find and execute their event functions like Start and Update.

## Introduction
{{< youtube bHvjTkvd_vY >}}

## Prerequisite Concepts Review
First, be sure you have a strong grasp of [Classes and Components]({{< ref "/csharp/fundamentals/classes-and-components.md">}}).

### Data Structures
A data structure is an organization of data. When we have a collection of information that is related, we can put it in a structure that allows easy access, use, comparison, and manipulation of that data. The [List of Data Structures](https://en.wikipedia.org/wiki/List_of_data_structures) on Wikipedia is overwhelming but interesting. For a more fundamental introduction, check out this [Crash Course](https://www.youtube.com/watch?v=DuDz6B4cqVc) video.

### Hierarchy
Hierarchy. Hierarchical relationships is a way of organizing things that places things on different related levels. Things can be related to each other as above an other thing, below an other thing, or at the same level as an other thing. Hierarchies are sometimes called "tree structures".

We will call the higher level things parents, the lower level things children, and things at the same level siblings. In programming, we also use the terms "base" to refer to an objects parent, and "extending" to the process of creating a child.

Also see this page on [Hierarchail Data structures]({{< ref "/csharp/fundamentals/hierarchial-data-structures.md">}}).

### Taxonomy
Taxonomy is not a programming concept, but knowing about taxonomies will be helpful. Taxonomy is a system of classification, and most taxonomies you have likely heard of are structured as hierarchies. In other words, Taxonomies are practical examples of hierarchies. Creating taxonomies - somebody has to decide how to organize the library (thanks Dewey). It is interesting (one might say 'productive procrastination' to browse through lists of example taxonomy on [wikipedia](https://en.wikipedia.org/wiki/Taxonomy).)

### Inheritance
From the [MSDN C# Docs Overview Page](https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/object-oriented/) page:
> _A class that derives from another class, called the base class, automatically contains all the public, protected, and internal members of the base class except its constructors and finalizers._

From the [MSDN C# Docs Inheritance](https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/object-oriented/inheritance) page:
> _Inheritance enables you to create new classes that reuse, extend, and modify the behavior defined in other classes. The class whose members are inherited is called the base class, and the class that inherits those members is called the derived class._

### Members
A member is all of the things that make an object what it is. An objects variables and functions are an objects members. Members is our new word for 'thing' in the context of objects and classes. Objects can inherit members from other objects. From the [MSDN Docs](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/members):

> _Classes and structs have members that represent their data and behavior. A class's members include all the members declared in the class, along with all members (except constructors and finalizers) declared in all classes in its inheritance hierarchy._

## Component Systems
Component-based architecture is discussed in the [Architecture Lecture]({{< ref "/code-architecture/architecture/the-architecture-lecture.md" >}}), and you can review the pattern on its own in the excellent [Game Programming Patterns Book](https://gameprogrammingpatterns.com/component.html) (free, online).

## The Lesson

{{< youtube xMD5UOwPcMk >}}

## Overriding Members & Example

{{< youtube Evkj2w0P5IM >}}

## Syntax
See the [Object Oriented Syntax]({{<ref "/csharp/advanced/object-oriented-syntax.md">}}) page.

## Resources & Next Steps
The next step will be to implement these concepts yourself in a project! In the meantime...

### Reinforce Concepts
Reinforce your vocabulary by reviewing other object-oriented programming introductions, like [this video](https://www.youtube.com/watch?v=pTB0EiLXUC8) and [this video](https://www.youtube.com/watch?v=YcbcfkLzgvs), which explain the same things, but are short and use different languages.

### Further Concepts
The next concepts we will be covering are [static objects]({{< ref "/csharp/advanced/static-objects-and-unity.md" >}}) and [abstract](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/abstract) classes, as well as learning a lot of the ins-and-outs of actually writing and using polymorphic ([new vocab word](https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/object-oriented/polymorphism)) code.

### Reviewing Docs
A number of pages on the official MSDN C# Docs will be useful to read over. As we improve our vocabulary, these vocab-heavy pages will become more and more accessible, and will become a highly useful and pleasantly concise resource.
- [MSDN Object-Oriented Programming](https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/object-oriented/)
- [Knowing When to Use Override and New Keywords](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords)
- [How to override the ToString method](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/how-to-override-the-tostring-method)
- [Objects Overview](https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/object-oriented/objects)
