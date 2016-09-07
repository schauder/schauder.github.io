---
layout: default
status: publish
published: true
title: Architect or Architect?
author:
  display_name: Jens Schauder
  login: admin
  email: jens@schauderhaft.de
  url: http://blog.schauderhaft.de
author_login: admin
author_email: jens@schauderhaft.de
author_url: http://blog.schauderhaft.de
wordpress_id: 1527
wordpress_url: http://blog.schauderhaft.de/?p=1527
date: '2015-09-20 18:58:31 +0200'
date_gmt: '2015-09-20 16:58:31 +0200'
categories:
- article
- Softwaredevelopment
tags:
- architecture
- enterprise
comments:
- id: 404765
  author: timothep
  author_email: twitter.timothep@example.com
  author_url: https://twitter.com/timothep
  date: '2015-09-20 21:02:35 +0200'
  date_gmt: '2015-09-20 19:02:35 +0200'
  content: "Hi Jens, I came to the same conclusion not so long ago. The project I
    was working on was very much mix-and-matching both. I tend to  describe those
    positions with a qualifier now: \"Project Architect\" vs \"Enterprise Architect\".
    \r\n\r\nNevertheless, remains the problem of the \"Architect\". Without a qualifier,
    I automatically assume the first... which remains dangerous from a project perspective
    and can lead to balls being dropped as nobody feels responsible for some flying
    parts.\r\n\r\nThe way we finally handled it in that project was first to push
    down as much of the architecture as we can to the Scrum teams. Then we introduced
    a so called \"Tech-PO\" being the owner of the Domain Model and overseeing the
    code-architecture. Finally trying to corner the remaining \"architects\" outside
    of the project i.e. at the enterprise level or at project-strategy-level (can
    we upgrade this component to version X++ or integrate this library)... this last
    point is IMO the least rewarding of all and is thus hard to fill up... we're still
    working on it.\r\n\r\nHope this helps. Tim"
- id: 404771
  author: nipafx
  author_email: twitter.2847809129@example.com
  author_url: https://twitter.com/nipafx
  date: '2015-09-20 20:58:36 +0200'
  date_gmt: '2015-09-20 18:58:36 +0200'
  content: |-
    What kind of architect are you? Project scoped or company/enterprise scoped?

    http://t.co/4KPGSGTMuW

    by @jensschauder
- id: 404778
  author: timothep
  author_email: twitter.15500629@example.com
  author_url: https://twitter.com/timothep
  date: '2015-09-20 22:59:31 +0200'
  date_gmt: '2015-09-20 20:59:31 +0200'
  content: 'RT @jensschauder: I blogged: Architect or Architect? http://t.co/LUKOyDrGPl'
- id: 405376
  author: 'Java Weekly 40/15: JMH and CDI, MVC, Microservice Truths'
  author_email: ''
  author_url: http://www.thoughts-on-java.org/java-weekly-4015/
  date: '2015-09-28 04:52:05 +0200'
  date_gmt: '2015-09-28 02:52:05 +0200'
  content: "[&#8230;] Jens Schauder wrote an interesting post about two kind of architects
    that exist in bigger companies. Both kinds&Acirc;&nbsp;have different tasks and
    view the project from a different angle:&Acirc;&nbsp;ARCHITECT OR ARCHITECT? [&#8230;]"
---
<p>I recently discovered that there are two very different types of people in large companies, who
  (at least in case of my customer) both claim to be "architects".</p>
<p>The one type is what I expect when I talk about architects. It is also what I mean when I claim to be an architect: Someone who helps a project to avoid the worst technical problems and solve those they fail to avoid. He or she does that by making the important technical decisions early enough but not too early.</p>
<p>The other type doesn't really care too much about the project. Her focus instead is that of the enterprise. Often she concerns herself with questions like data security which the project might ignore, because it is not a direct concern of the project.</p>
<p>Both roles are important. Without the first role (it doesn't have to be a single person) a project is in great danger of failing because it doesn't meet it's non-functional-requirements. Possibly because they aren't even known to the project team. Without the second role the project might ignore non-functional-requirements that don't come from the projects own stakeholder, but from the enterprise. This kind of mistake might result in the company making the front page because critical data was stolen, lost or leaked. Nothing you want to happen to your employer. Architects of this kind don't deliver solutions to technical problems, instead they are forcing additional requirements on the project.</p>
<p>If you are working for a large company you probably have both roles, but are the project members aware of the different roles? I wasn't until recently and I think<br />
this is really bad. In my opinion:</p>
<ul>
<li>The roles should be clearly distinguished by very different titles, so nobody thinks these two are the same.</li>
<li>The two roles should be performed by different people, because a single person trying to perform both gets into some awkward conflict of interest: Should he stop a project that fails to implement a critical non-functional-requirement and thereby setting himself up as the architect who failed? I don't think this works very well. More importantly: It fails especially  when things get difficult and failure has the worst possible effects.</li>
</ul>
</p>
<p>So how is this handled at your company? Is it handled at all?</p>
