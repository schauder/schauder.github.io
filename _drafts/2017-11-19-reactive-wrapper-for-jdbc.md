---
layout: default
title: Reactive JDBC?
author:
  display_name: Jens Schauder
categories: article
tags:
- spring data
- jdbc
- reactive
---

I wrote twice this year about Project Reactor and Threads. 
The reason I'm interested in is the lack of a reactive JDBC.
Reactive programming pulls lots of interest.
When members of the Spring Data team do conference talks about the reactive features of Spring Data one of the questions that gets asked every single time is:

> What about JDBC?

So here is my answer.
While I thought a lot about this lately I don't claim to be a final source of truth in this.
There are many smart people that disagree.
And I hope that some of them state their opinion and arguments in the comments, so that everybody can learn from the discussion.

JDBC is blocking.
This means it is a poor fit for reactive programming.
You really want to have a reactive persistence store for your reactive application.

But I've worked long enough with large enterprises to understand that there might be forces that make relational databases mandatory.

So lets start by ignoring constraint and look what happens.





Pretty much the obvious idea when faced with this conflict is to delegate any blocking calls to some kind of thread pool, so they don't block the main thread pool of the application. 

