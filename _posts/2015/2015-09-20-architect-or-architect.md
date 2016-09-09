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
---
I recently discovered that there are two very different types of people in large companies, who
  (at least in case of my customer) both claim to be "architects".

The one type is what I expect when I talk about architects. It is
also what I mean when I claim to be an architect: Someone who helps
a project to avoid the worst technical problems and solve those they
fail to avoid. He or she does that by making the important technical
decisions early enough but not too early.

The other type doesn't really care too much about the project. Her focus instead is
that of the enterprise. Often she concerns herself with questions like data security
which the project might ignore, because it is not a direct concern of the project.
Both roles are important. Without the first role (it doesn't have to be a single person)
a project is in great danger of failing because it doesn't meet it's non-functional-requirements.
Possibly because they aren't even known to the project team. Without the second role the project
might ignore non-functional-requirements that don't come from the projects own stakeholder, but
from the enterprise. This kind of mistake might result in the company making the front page
because critical data was stolen, lost or leaked. Nothing you want to happen to your
employer. Architects of this kind don't deliver solutions to technical problems,
instead they are forcing additional requirements on the project.

If you are working for a large company you probably have both roles, but are the
project members aware of the different roles? I wasn't until recently and I think
this is really bad. In my opinion:

* The roles should be clearly distinguished by very different titles, so nobody thinks these two are the same.
* The two roles should be performed by different people, because a single person trying to perform both gets into some awkward conflict of interest: Should he stop a project that fails to implement a critical non-functional-requirement and thereby setting himself up as the architect who failed? I don't think this works very well. More importantly: It fails especially  when things get difficult and failure has the worst possible effects.

So how is this handled at your company? Is it handled at all?
