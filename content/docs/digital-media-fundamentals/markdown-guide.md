---
title: Markdown
---

# What is Markdown?

Markdown is a plaintext syntax with formatting capabilities. It is not a specific program, but is a way of writing using plaintext, but allows for formatting, like the picture below. That means it’s not a text editor like Notepad or word processor like Word, but would be useable on both of those programs. It is a lightweight format, using less data than Google Docs, for example. It also means that it is compatible with many programs, software, and computers.
![An example of what Markdown could look like.](/images/digital-media/markdown/markdown_preview_ex.jpg)

### Plain text vs. Rich text

Plain text includes no formatting capabilities, is compatible with any program or computer, and has a smaller file size. Rich text is more common and interesting, but formatting can be messed up when used across versions and devices.

### Why use Markdown?

Markdown was created for website content creation (like with Hugo), but it is good for simple notetaking, lists, books, emails, and presentations. [This website](https://www.markdownguide.org/getting-started/) goes into further detail of the applications to create different products of text.

### Markdown Syntax

\# are used for headings. They go in front of the phrase that you wish to be changed followed by a space.

![heading guide](/images/digital-media/markdown/heading_examples.png)

To be italicized, phrases are constructed \*like this* ( and come out looking *like this*)
To be bold, phrases are constructed \*\*like this** (and come out looking **like this**)
To be both, phrases are constructed \*\*\*like this*** (and come out looking ***like this***)
![More formatting examples!](/images/digital-media/markdown/formatting_examples.png)

For numbered lists, you just need to start with 1., and then the rest doesn't matter

1\. One
1\. Two
5. Three
3. Four

Looks like:

1. One
2. Two
3. Three
4. Four

Bulleted lists use the same principles, but with *, -, or +.

\* like this

\- this

\+ or this

Either way, it comes out

- Looking
* Like
+ This

Blockquotes are used with > and >> to nest them.

> hey ( "> hey" )
> 
> > hello ( ">> hello" )

Links are written with brackets around the title [Google], aka the clickable part, where the link will be inserted. Inside the parenthesis goes the link ([https://google.com](https://google.com)). 

I.e. \[Click here to Google](http://google.com) looks like [Click here to Google](http://google.com)

Images are placed with \!\[]() 
They can be accessed from the absolute location (i.e. from your c: drive on your computer), or if it's in the same folder, then just the file name, or lastly, using a web link to the image.

![How to insert a link](/images/digital-media/markdown/how_to_insert_link.png)

Lastly, since we use markdown to write these, it would obviously present an issue to show you how to type something. By using \ before each character, the backslash clears and you can type the character needed

```
\*like this* or \*\*this**
```

And to create that block? You use three tick marks (```), a new line, and 3 more tick marks after the last line.

\`\`\`
blah blah blah a block of text!
\`\`\`
comes out like:

```
blah blah blah a block of text!
```
