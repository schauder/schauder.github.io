---
layout: default
title: Don't use LocalDateTime.
author:
  display_name: Jens Schauder
categories: article
tags:
- java
- date
- time
- instant
---

A couple of weeks ago I fixed a bug in Spring Data related to date conversions.
For this I read up on the "new" `java.time` API which I had hardly used so far.
To my surprise I learned that we used it wrongly in Spring Data.
And judging from what I saw on Stackoverflow and the rest of the internet many others make the same mistake.
The mistake is to use `LocalDateTime`.

You might think: The new API is based on Joda Time which is awesome.
How can it be possible a mistake to use a class from this API?

The problem is that there is a very common use case when using the `java.time` API and at first `LocalDateTime` seems to be the right choice for this use case but it actually isn't.
The use case is this:

> You want to represent a point in time without worrying about time zones.

Sure enough `LocalDateTime` doesn't include any time zone information. 
So what is the problem?
Lets take a look in the documentation:

> `LocalDateTime` is an immutable date-time object that represents a date-time,
    often viewed as year-month-day-hour-minute-second.
    [...]
    This class does not store or represent a time-zone.
    Instead, it is a description of the date, as used for birthdays, combined with
    the local time as seen on a wall clock.
    It cannot represent an instant on the time-line without additional information
    such as an offset or time-zone.
    
Let me repeat the important part

> **[`LocalDateTime`] cannot represent an instant on the time-line without additional information.**

If you invoke `LocalDateTime.now()` an hour apart before and after your default timezone turns the clocks back due to daylight savings time you'll get two identical instances and you will have no way to tell them apart.
Most likely this is not what you want in most use cases.
And definitely not in the use case described above.
What you want instead is `Instant`.
Lets look into its JavaDoc:

> This class models a single instantaneous point on the time-line.
  This might be used to record event time-stamps in the application.
  
Just what you want.

This leaves the question: What is the use case for `LocalDateTime`?
So far all examples I came up with had one thing in common: the `LocalDateTime` information comes from a different source than the time zone information and get combined to actually get a point in time. 
One example I came up with is sending out mass E-mails.
You might want to control when people are getting the E-mails. 
Maybe you want them to arrive early during the workday or right after lunch.
So you pick a `LocalDateTime` to represent that like "next Monday 8 am" or "Tuesday at 1 pm". 
Then you can combine that with the time zone based on the physical location of the E-mail recipient to determine the right point in time to send the E-mail out.

I know, it's a contrived example but that is my point: It is hard to come up with a valid and realistic use case for `LocalDateTime`.
The next time you want to type that class name think twice if this is really what you want.