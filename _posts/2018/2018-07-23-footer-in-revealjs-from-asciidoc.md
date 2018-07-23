---
layout: default
title: Footers in Reveal.js slides generated from AsciiDoc.
author:
  display_name: Jens Schauder
categories: article
tags:
- reveal.js
- asciidoctor
- html
- css
- footer
---
In my last [article](/2018/03/25/my-tech-stack-for-slides/) I outlined the tech stack behind my talk slides based on  [Reveal.js](https://revealjs.com/#/) and [AsciiDoc](http://www.methods.co.nz/asciidoc/).
This article will show how to create a footer for slides using these tools.

I really hate the footers in many slide templates. 
Often they contain information either nobody cares about at all, or if someone cares they shouldn't be in the talk.
Examples are *the current date* the *number of slides* and the *title of the talk*.
Although I have to admit I once ended up in the wrong lecture at university and I would have loved a slide warning me about that because sitting in a bad economics lecture is really scary for a physicist in training. 
But that was at a time when slides where hand-drawn with chalk on a black board and dinosaurs roamed the earth.

But there are a couple of things I'd actually like to have on each and every slide:

* a twitter handle or hashtag for the event I'm presenting on
* a hashtag for the talk
* my own twitter handle

The idea being that this makes sharing content on social media easier.

So lets have a footer on each and every slide.
Easy, right?
Well, not really.
At least with my setup and my non-existing knowledge of frontend technology.

The problem is that AsciiDoc puts whatever content you have in `section` tags in the generated HTML, but you really want something that breaks out of these tags in order to be relative to the full screen and also to be the same for all the slides.
After some googling and experimenting it turns out, it is actually really easy.
This is actually so easy, even I can do it using the following steps:

1. Have a section that is literally included in the output without any processing by AsciiDoc. You get those by putting the content between a pair of `++++`
2. In that section have a div containing your footer content, with a nice unique id like so:

        ++++
        <div id="schauderhaft-footer" class="footer">
            <span class="element">#cool-talk</span>
            <span class="element">@some-conf</span>
            <span class="element">@jensschauder</span>
        </div>
        ++++
        
3. Add a tiny piece of javascript that moves the div to the location where you actually want it to be. The following script tag goes between the pair of `++++` as well:

        <script type="text/javascript">
            window.addEventListener("load", function() {
        
                revealDiv = document.querySelector("body div.reveal")
                footer = document.getElementById("schauderhaft-footer");
                revealDiv.appendChild(footer);
        
            } );
        </script>
        
4. Add styling to your sass template to make it look as you wish. These are the styling I use:

        .footer {
          position: absolute;
          display: table;
          width: 100%;
          bottom: 0;
        
          color: $color-primary-2;
        }
        
        .footer span {
          display: table-cell;
          padding: 0px 15px 5px;
        
          text-align: center;
          font-family: "Roboto Mono", monospace;
          font-size: 70%;
        }
        
        .footer span:nth-of-type(1) {
          text-align: left;
        }
        .footer span:nth-last-child(1) {
          text-align: right;
        }

Not that bad, isn't it?

I'll try to not let you wait for the next installment of my blog for that long.