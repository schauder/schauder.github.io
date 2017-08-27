---
layout: default
title: Handling blocking stuff in Reactor
author:
  display_name: Jens Schauder
categories: article
tags:
- spring data
- pivotal
- remote
- career
---

It's now over 6 months since I joined the Spring Data Team. Time for some looking back.

When I started the new job there were many things I was looking forward to and they basically all worked out more or less as I expected:

* **Working with very smart people with a passion for software development**. 
Before I was used to being the most or at least one of the experienced developers in the team. That was great for the ego.
It was also enjoyable because it gave me comparable big leverage on decisions made in the project.
Now I'm the junior in many respects. 
Which is great because now I'm learning something every single day at work.
Sometimes it is just small stuff, e.g. some shortcut or a smoth way for rebasing stuff.
Sometimes it is project specific stuff like abstractions used inside Spring Data.
But often it is the kind I like most: Features about programming languages and libraries. 
So far I was able to use Java 8 almost all the time sometimes even JDK 9.
I learned about MyBatis, JOOQ, Querydsl, Lombok and many more.
It's just great. 
It is also rather challenging to see your coworkers being way faster than you are. 
More about that later.

* **Working with great hardware**.
I spend a serious part of the last year with my previous employer fighting to get reasonable hardware for my team and myself.
It famously ended with the statement: 
> Ok you proved that faster machines are actually faster for the stuff you do all day. That isn't a reason to get them.

Which is kind of funny considering that the whole thing started with the premise.
> You don't get more than a secretary, because I don't believe your work will actually benefit from it

Yeah, I know, pretty funny in hindside. 
    
Compare that to how things worked for me at Pivotal: I got two questions in order to decide which hardware I would get:

> Do you prefere 15" or 13"? What kind of keyboard layout do you want?

Because it was assumed that I would want an Apple and it was also assumed that I would get the (almost) fully loaded version. (It doesn't have the largest SSD but I have plenty of space so that is fine.)

* **Working on a great project**.
I guess not everybody is a Spring fan. 
That is fine.
But I happend to be a fan since I used it for the first time.
And it definetly has a huge user base.
So I'm working on something that many people use every day, because they want to. 
When I was working on Enterprise software the user base was tiny most of the time.
Sometimes even zero when the project died before the first release.
And I never ever had a user play with what I build in her spare time in order to try all the new feature or even demoing it on a conference.
That is a cool feeling.

And then there are the things that scared me a little.
Or that I didn't think about at all.

* **Working at remote, alone, in my tiny home office**.
Luckily this worked out great too. I you only know my from the internet and conferences you might not be aware of it but I'm an introvert.
One effect of this is that I actually enjoy being alone. 
So that part is no problem at all.
Not having to commute 45-90min one way is a great plus.
Seeing my family obviously too.
On the not so good side: I really miss pair programming but in a few weeks Gerrit will join the team, so there might be a chance for that.

In general the lack of social contact was a little scary, but again it worked out great. 
I make sure I meet plenty of people in my spare time so that is taken care of. 

My office is tiny.
It would probably be illegal to have so much stuff in a normal office in Germany. But it is all my stuff so while it might be horrible for others it is really comfortable for myself. 
I'm enjoying it a lot. 
Especially when I have some reading to do and can cuddle in the comfy chair I inherited from my dad.

* **Working in public with everyone watching you**
Almost all my work result end up on public repositories on Github.
Or at least in repositories that will be public eventually.
So every typo, every stupid mistake is there for you to see and to make fun about it.
Some mistakes where found. 
Fast. 
Did I mention the whole Spring stuff is popular?
And Spring Data is used by many other Spring projects?
Turns out, if you break a snapshot build you learn about it within an hour.
Trust me. 
I tried it.

Shit like this happens. 
Time to remind yourself that making mistakes is an essential part of learning.
I'm still trying to get used to it, but I'm making progress.

* **Working with no one watching you or telling you what to do**
If you end up doing nothing, you'll have a hard time comming up with something on the next standup.
Other than that nothing would happen. 
There are no coworkers glancing at your screen and wondering if playing jewels is an important part of your project.
There isn't even anybody looking at you hours.
If you are living in an enterprise world you are probably used to 

1. Writing down how long you worked.

2. Assignining your work time to different projects.

3. Getting complains if you assign to much time to a project

4. Having to enter that information in at least 2 systems, once for your employer and once for the customer (my personal record was 7 I think).

5. Having someone comparing the numbers from the different systems and complaining when they don't match.

We have nothing of that. 
That feels weird after being used to the system above for almost 20 years.
Interestingly it has the opposite effect of what one might expect, at least for me.

I'm really slow compared to my coworkers.
Fast just isn't my thing.
And I'm (still) new, so I need more of the slow working than my coworkers need of there fast working.
It made me feel really unproductive.
Early on this tempted me to compansate by working extra hours.
But I know from past experience this makes me effectively even slower. 
So I put up my own Google Docs Sheet to track my hours, so I can be fair to Pivotal by working the hours I promised and also to myself and my family.

After some timme getting used to it it feels great.
And I actually work more concentrated than I used to, because now I'm getting paid for my work, while before I was essentially being paid for being in the office.

* **Managing interuptions**
While I talk about productivity there is one thing that kind of caught me of guard.
Pretty much everybody works remote on the Spring teams.
So tools like Slack, Google hangout, Skype, E-Mail and even Twitter are essential (in more or less that order).

I hardly used Slack before but now I wanted to have it open all the time so I see what people on my team are talking about.

Problem: Slack by default notifies you when something happens. Possibly worse: if you have an unread message it displays a big red dot on the icon when you use CMD-Tab to switch windows. 
This creates a strong urge to check what message that is.
Flow interupted.
Not good.

After some configuration of notification settings nothing interupts me anymore, except very few exceptions: mentions on slack, phone calls and SMS. 
Much better. 
