---
layout: default
title: Don't convince your coworkers to do TDD.
author:
  display_name: Jens Schauder
categories: article
tags:
- TDD
- agile
- team
---

At the beginning of the year I had a little twitter discussion about TDD. 
It started of as a request for some documentation about TDD.
But after some back and forth it turned out that the goal was to convince the members of a team to adopt TDD in order to fight quality problems.

My advice was and is: "Don't".
Here is why.

Just for those that never discussed software development with me: I'm a huge fan of TDD. 
I think it is an essential skill.
And assuming you want to work as a software developer, if you find yourself in a place where you are not encouraged to do TDD I encourage you to find a new job.
The place you are currently at is most probably a dead end career wise.

So why shouldn't you convince your coworkers to do TDD in order to fix quality problems? 
Two reasons:

1. It is a stereotypical example of "If you only have a hammer every problem looks like a nail."

2. If you push a solution the chance that it will get rejected is really big. And that would be a sad state for such a powerful tool as TDD.

Instead of proposing your favorite tool to fix the problem, spend the time to find a solution together with the team.
This starts by finding out if there is a problem. 
You might think there is a problem. 
Others might not.

I once was involved in a software release which was rejected after 1-2 days of testing by the customer as way too buggy and basically not fit for use.
After the meeting in which the customer explained his opinion to us I drove home together with our test manager. 
The dialog went something like this:

Me: Wow, that was embarrassing!

TM: I don't think so.

Me: But we delivered software that was rejected immediately by the customer!

TM: Not our problem. 
It's his task to test the software.

Me: ---

I still think the TM was failing at his job, badly. 
But that is not the point here. 
The point is that our opinions about if there is a problem differed widely. 
What you might experience as an embarrassment might be completely normal for the guy next to you.
And vice versa!

**Have an open discussion about what you percive as a quality problem**

Maybe the others agree. 
If so you made a big step forward.
If everybody acknowledges there is a problem it is much easier to convince people to do something about it.

If your opinions differ you have another discussion upcoming: How do you arrive to so different evaluations and what to do about it?

Let's assume for now you agree on having a quality problem. 
Where does it come from?
And what might be good measures to fix it or at least make it less sever?

TDD might be a solution. 
But there are many scenarios where it isn't.
Here are some I have seen in the past:

**No version control system or one not up to the task.** 
You might think everybody is using Git by now?
Probably not. 
I'm sure there are tons of projects that use VSS, CVS, SVN, PVCS or just the occasional zip file.

**Lack of skills**
Maybe there are team members that don't have the required skills and just need training or coaching.

**Lack of understanding what is expected**
I have seen developers that consider it sufficient when their code compiles and they know one example where it produces the correct result.
The rest is the job of the test team.

**Unclear requirements**
I once worked in a project where we needed 3 times as long es planned for a task. 
But not to actually implement it, but just to understand what is expected. 
Only then could we start with actual coding.
I guess it doesn't surprise anybody that the quality was abysmal.

In all these scenarios and in many others TDD is of no help.

But even when your quality problems are of the kind that could be improved by applying TDD there might be better alternatives.
Have you tried code reviews?
Is anybody testing the product at all? 
Manual tests, explorative or other wise are options that might help more in your current situation.
Maybe integration tests can help more right now?
Or how about pair programming?
Or better monitoring in order to identify and therefor fix problems faster?

All these are valid tools to improve the quality of software.
Which one is the right one depends on your situation.

If this is discussed in the team and agreement achieved that TDD sounds most promissing: 
Then do TDD. 
Your chances that it will actually help are now much better. 
Among others because the team won't go "I told you that TDD shit is useless" on the first bug that gets passt the shiny unit tests.
