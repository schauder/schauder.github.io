---
layout: default
status: publish
published: true
title: What's Your Next Language?
author:
  display_name: Jens Schauder
categories: article
tags:
- language
- java
- javascript
- clojure
- frege
- haskell
- learning
- scala
- kotlin
- groovy
---

A common recommendation for software developers is to learn a new language each and every year.
While I consider this a little over the top, learning a new language from time to time is certainly a good
idea, but what language should you pick? 

As so often the answer is "It depends".

Let's assume you know mainly Java (as the typical reader of this blog probably does) and you don't really know 
any other current language. CSS, HTML and SQL aren't considered languages in this context and Fortran, Cobol and 
Applesoft Basic aren't current.

The answer to the question depends on what your primary goal is, and your attitude to strong type systems.

If you want a language that you can put to good use immediately, the obvious answer is: Javascript (Doesn't matter
what type system you prefer, the one of Javascript is broken). It is
a butt-ugly language and probably the last one you would learn for the sake of learning, but you 
can't really avoid it 
if you do any web development at all.

If you find Java a bit ugly and verbose and want to switch to something less verbose, consider Groovy (dynamically typed)
or Kotlin (statically typed), both seem to offer more concise syntax and profit from some mistakes Java made by
avoiding them. Both languages are rather similar to Java so you should be able to use them in real project
pretty soon (if you can decide on the language used)

If you really want to lean something I recommend a real functional language: Clojure which is a LISP dialect (dynamically typed)
or Frege a Haskell for the JVM. If you never came in contact with functional language they will make quite some 
knots into your brain, but that is just the sweet feeling of learning. 

I personally find Frege extremely interesting right now, because you can do some cool shit with it. Dierk König 
showed me on a JUG meeting a couple of weeks agao how trying to do side effects on the JavaFX event thread or 
accessing Java FX components while not on the JavaFX event thread cause compile time exceptions! In my eyes it doesn't
get much cooler than that.

People that know me might be a little surprised, that Scala doesn't appear in this list. A couple of years ago, when 
Oracle took control of Java and seemed intend to run it into the ground, I wanted an alternative language for my CV.
At that time it took up the position of Kotlin now. On the other hand it supports functional constructs rather nicely.
So I also used it for things I would today pick Frege for. That combination was nice and I learned a lot from
learning Scala. It was a good choice, but today I would rather pick Kotlin or Frege, depending on what my goal for
learning a new language would be. 

Having said that: As soon as I have finalized some tasks that keep me busy right now, I'll have to get my hands dirty with
some Frege.

So what language are you going to learn next?
