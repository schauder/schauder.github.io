---
layout: default
title: From AsciiDoc to HTML 5 - My Tech Stack for Slides.
author:
  display_name: Jens Schauder
categories: article
tags:
- reveal.js
- asciidoctor
- html
- css
- maven
---

PowerPoint drives me insane.
Appart from issues like spontaneously replacing a font in a presentation while I present the slides there is a more fundamental issue:
PowerPoint forces you to use PowerPoint. 
I can't use my favorite text editor.
I can't use my favorite version control.
Well, I can but I won't get useful diffs out of it.  
Or try checking the content of your slides with a tool like Grammarly.
And good luck presenting slides done in one version with a different version of PowerPoint (or none at all).
If you do slides to present once during a meeting that is probably not an issue for you.

But when I do slides they are mostly for talks.
Even if I sometimes fail to make it show: A lot of time goes into these slides.
And I try to give these talks multiple time.
Which often left me with folders full of variations of a slide deck and no idea what the differences are.

So a couple of years ago I decided I have to find an alternative. 
And by now I'm somewhat happy with what I found and as usual, learned a lot about the tools I ended up using.

Here are my original goals:

**Diffable**: Everything should be text based so I can use git in a useful way.

**Consistent look**: I want a certain style for my slides and I don't want to recreate that every time I create a new slide deck.

**DRY** (don't repeat yourself): I want to reuse parts of slides like the "About Me" slide and the style.

**Automated**: Since the first point meant I was going for something text-based, the process to convert it into actual slides should be automated.

**Include code from actual sources**: About half of my talks are technical and might include traces of source code. 
    I want this source code to come from actual source files that I can compile and test, so I can be reasonably sure that they actually work.

**Reusable knowledge**: I'd like to use technology that I can use in other contexts. 

And this is what I came up with:

The first choice I made was [**Reveal.js**](https://revealjs.com/#/). 
It is a JavaScript framework for creating slides. 
On its own, it lets you write HTML which then gets rendered as slides, with transitions and everything as one might expect.
I used it quite some time as a standalone solution. 

Since the slides are just HTML you can host them easily whereever you want, which for me means GitHub pages.
And all you need to present them is either the files or an internet connection and a computer with a browser.
But typing **HTML** is something for a bigger masochist than me.

After trying MarkDown which turned out not to be powerful enough for the stuff I wanted I ended up with [**AsciiDoc**](http://www.methods.co.nz/asciidoc/) for authoring the slides.
AsciiDoc is originally intended as an easy to write replacement for DocBook. DocBook is an XML format for documentation which can be converted into all kinds of formats. 
HTML and PDF are the most important ones I guess.
AsciiDoc is used in many places to write documentation including the Spring documentation.
It is also easy to write since it uses mostly plain Ascii characters for formatting, similar to MarkDown.
It also allows to include source code either directly or as an include from other files, which fit my requirements really nicely.
Same goes for partial documents so stuff you want to reuse in multiple places can be extracted in separate files.
A good plus for DRY.
Fortunately, there is a Reveal.js backend which creates Reveal.js slides from AsciiDoc documents.

I didn't like the way the slides looked in Reveal.js by default. 
To some extent because I just wanted to have my own style. 
Not necessarily because my style is in any way better than the standard.
Since Reveal.js is just HTML5 you can do that by writing **CSS** which I know almost nothing about. 
That's what I call a good opportunity to learn.
But Reveal.js doesn't use CSS directly, it uses [**SASS**](https://sass-lang.com/) instead which makes CSS more DRY.

Finally, I have to put everything together.
Since I'm a Java guy I wanted to use one of the established build tools.
I started with Gradle since that was what I preferred at the time because it is less verbose than Maven.
But eventually, my slides were the only stuff left that was build with Gradle. 
And I really didn't understand my own build file anymore. 
This was at least to some extent because I only worked with it sporadically.
At the same time, I also learned more about how Maven actually works and with Spring Data I worked on a project that actually used AsciiDoc and processed it using Maven.
So I switched to **Maven** for my slides as well.

So this is my tech stack for my slides:

* AsciiDoc for writing slides
* SASS for styling them
* Maven for converting them
* Reveal.js as the target format.
* Atom, IntelliJ, and Grammarly for editing
* Git for versions control
* GitHub for hosting the repositories and the final pages.

Making everything work was some serious work, and there are still things I want to improve.
But by now I'm somewhat satisfied with what I got.
I'll write more about how everything works and what I learned along the way, but that are topics for future articles.
 
For now, you can take a look at [a typical project on Github](https://github.com/schauder/spring-data-reactive-talk) and [the resulting slides](http://blog.schauderhaft.de/spring-data-reactive-talk/talk.html#/).  