---
layout: default
status: publish
published: true
title: Handling blocking stuff in Reactor
author:
  display_name: Jens Schauder
categories: article
tags:
- java
- reactive
- reactor
- blocking
- threads
---
Let's assume you have some nice reactive pipeline implemented with Reactor. 
Let's now also assume that you need to perform a blocking operation. 
Maybe you need to read from some relational database. 

Hopefully you are aware that you shouldn't just put blocking operations in your pipeline. 
The problem with that is, that normally for the processing of a pipeline you will have a thread pool tightly bound to your CPUs cores, so that each thread is continuously executed on a core (or maybe two threads per core to accommodate for hyperthreading). 
If you now encounter a blocking operation, a core will sit idle without doing any work and there also wouldn't be another task available to get executed by that core. 
What a waste of CPU cycles.

What you really want is no blocking operation at all. 
But sometime you don't really have a choice. 
What you can do instead is: create a separate `ThreadPool`. 
On it you only want to execute the blocking operation. 
Because you have that other `ThreadPool` reserved for computation. 
And you don't want the two `ThreadPool`s fighting for the cores to do the work. 

The `ThreadPool` for the blocking 