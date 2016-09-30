---
layout: default
status: publish
published: true
title: Work Breackdown Structure vs Backlog
author:
  display_name: Jens Schauder
categories: article
tags:
- agile
- waterfall
- wbs
- backlog
---

Lately people keep telling me that things that are common practice in agile projects are done in waterfall
based processes as well. And you know what? Some are. But others aren't and again others are completely missing.
So lets make a loose series of articles about waterfall artifacts and practices compared
to matching agile artifacts and practices.

My view on classical projectmanagement stemms from my IPMA certification from 2004. So it is theoretical, a little old
but in many cases it seems better grounded in reality then that of some project managers. 

My view on agile practices stems from my last 10 years of software development in teams that
tried to be agile and succeeded in various degrees.

Of course you are welcome to disagree, either in your own blog or down in the comments.

Let's get started with the Work Breakdown Structure or WBS for short.

[Wikipedia quotes the PMBOK5 for a definition](https://en.wikipedia.org/wiki/Work_breakdown_structure):

> "A hierarchical decomposition of the total scope of work to be carried out by the project team to 
accomplish the project objectives and create the required deliverables."
  
At first sight this might look similar to the 
[definition of a Backlog (again from Wikipedia)](https://en.wikipedia.org/wiki/Scrum_(software_development)#Product_Backlog)

> "The Product Backlog comprises an ordered list of requirements that a Scrum Team maintains for a product. It consists 
of features, bug fixes, non-functional requirements, etc.—whatever must be done to successfully deliver a viable product"

But there are some important differences (both in theory and in praxis):

1. **The Backlog does not strive to be complete**
The WBS must be complete by definition. (Note: that nobody says, that it has to have the same granularity in all areas)
This is necessary, because it is used as a basis for estimating the complete project. This means, that very early in 
the project decisions are made, about what goes into a project and what not. In a good case the decisions get revisited
and revised later on. In that case they are just a form of waste. But often they are not revised leading to much greater
waste, by implementing stuff that nobody really needs anymore.

2. **The Backlog is linear**
The WBS is inherently a Tree Structure, or even a multidimensional matrix: Every element is typically assigned things like:

    - Project phase
    - Technical Domain (like Frontend, Backend, Database)

    and often many more categories. This makes it nice and easy to slice and dice the elements to your likings. But it doesn't 
    really help that much. The Backlog on the other side focuses on on single bit of information: What should we do next, a.k.a.
    priority. This again is affected mainly by: How much does it cost and what is it's value. Whereby the value explicitely
    includes things like reduced risk. If done right, this leads to the important stuff getting done early, so when time
    is  up and one has to drop stuff from the scope of the project we loose only stuff of lesser importance. 
    I consider that
    a good thing.

3. **The WBS doesn't care about value**
The elements of a WBS each on it's own are basically of no value. They are isolated tasks, that only together with
many other tasks create value for the project. This also means that although a WBS tries to define criteria for each
task when it is done, you only really know once it is integrated with all the other tasks. And that typically is a
separate task planned for much later. During all that time the finished task is just waste, just as groceries are waste
that are lying around in the warehouse. And just as those, software can turn bad almost on its own. A backlog item by
comparison is done when it can be used as intended. If it can get used it is done and creates value. If it isn't, well
it is not done. In my experience a much easier to use criteria.

4. **The Backlog is worked on together**
In my experience the WBS is worked on only by the Project Manager, or a small team. This very often leads to complete
decoupling of the the WBS and the actual work the team. Many team members have a hard time to take a WBS serious that
don't map properly into any kind of real work flow. A Backlog on the other hand is groomed regularly by the whole team.
So if for example items on the backlog are to large to finish them in appropriate short time everybody in the team
is allowed and expected to bring this issue up. The common work on the backlog often leads to a much better identification
of teammembers with the way how work gets structured.

5. **Who cares about dependencies?**
This is not actually part of the WBS, but build on top of it: The dependencies of all the elements. Stuff like: Before
we can build X, we have to build Y. There is almost no place for this in a Backlog. Instead one strives to create
Backlog elements that are indepedent of each other. This approach reduces the amount of dependencies very often in
such a way that no explicit handling of dependencies is necessary. This is actually the one criteria that I found valid,
 that would make me consider a waterfall based approach to be useful: If the problem to solve has so many dependencies
 that you can't even decide in a short discussion what to do first. But I have never seen this with software. In the
 world of physical stuff this might be pretty normal. When you build an Aircraft Carrier you probably can't start with
 building the flight deck because it produces the most value. If you'd try you'd learn later on that it is really difficult
 to mount such a big slab of steel on a ship. With properly build software this is exactly the kind of thing you can do.

Since the WBS is at the center of planning in a project it pops up in other areas as well, so we'll mention it
again in other articles of this series.

Do you see other relevant differences between a WBS and a Backlog

