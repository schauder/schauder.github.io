---
layout: default
title: Includes and Variables in AsciiDoc.
author:
  display_name: Jens Schauder
categories: article
tags:
- reveal.js
- asciidoctor
---
In first [article](/2018/03/25/my-tech-stack-for-slides/) I outlined the tech stack behind my talk slides based on  [Reveal.js](https://revealjs.com/#/) and [AsciiDoc](http://www.methods.co.nz/asciidoc/).

In [the previous one](/2018/07/23/footer-in-revealjs-from-asciidoc/) I described how to add a footer to your slides or actually put html code from AsciiDoc anywhere in the resulting HTML pages where you want or need it. 

If I may remind you this piece of code in your AsciiDoc document creates some HTML for a footer:

    ++++
    <div id="schauderhaft-footer" class="footer">
        <span class="element">#cool-talk</span>
        <span class="element">@some-conf</span>
        <span class="element">@jensschauder</span>
    </div>
        
    <script type="text/javascript">
        window.addEventListener("load", function() {
        
            revealDiv = document.querySelector("body div.reveal")
            footer = document.getElementById("schauderhaft-footer");
            revealDiv.appendChild(footer);
        
        } );
    </script>
    ++++
     
But if you do many presentations you probably want a similar footer everywhere and change only a very small part of it: 
The hash tag for the event and the talk, while all the boiler plate stays the same.

The solution to this are includes and variables.

Includes are easy and obvious. 
They allow you to reference one document from the other in AsciiDoc and AsciiDoc will replace the reference with the content of the included file before processing it.

It looks like this:

    include::footer.ad[]    
    
This will pretty much pretend the content of `footer.ad` is right there instead of the include statement.
So you can hide all that ugly HTML in a separate file.

But I wanted to easily modify details of the footer.
Variables are the answer.

At the beginning of my main document I have this:

    :twitter-tag: @jensschauder
    :conference-tag: @JUGNBG
    :talk-tag: #sd-jdbc
    
This defines three variables and sets their respective values.    

And the `<div>` in my `footer.ad` actually looks like this:

    <div id="schauderhaft-footer" class="footer">
        <span class="element">{twitter-tag}</span>
        <span class="element">{conference-tag}</span>
        <span class="element">{talk-tag}</span>
    </div>
    
So now you can easily set the content of your footer in your main document, without even looking at HTML anymore.

You are welcome.