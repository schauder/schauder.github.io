---
layout: default
status: publish
published: true
title: Project Reactors flatMap - a Closer Look
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

An important part of reactive programming is backpressure. 
The idea being that only those events get published, that can be processed by the downstream operators.
That's why the following code prints ten lines as one might expect:

```java
long start = System.currentTimeMillis();
AtomicInteger integer = new AtomicInteger();

Flux
        .<Integer>generate(s -> {

            int next = integer.incrementAndGet();
            System.out.println(System.currentTimeMillis() - start + " - " + next);
            s.next(next);
        })
        .take(10)
        .blockLast(Duration.ofSeconds(1));
```
                
This is some example output I'm getting:

```
246 - 1
246 - 2
246 - 3
246 - 4
246 - 5
246 - 6
246 - 7
246 - 8
246 - 9
246 - 10
```  
Nothing to see here.

Of course nothing changes if I introduce an identity transformation using `flatMap`

```java
long start = System.currentTimeMillis();
AtomicInteger integer = new AtomicInteger();

Flux
        .<Integer>generate(s -> {

            int next = integer.incrementAndGet();
            System.out.println(System.currentTimeMillis() - start + " - " + next);
            s.next(next);
        })
        .flatMap(Mono::just)
        .take(10)
        .blockLast(Duration.ofSeconds(1));
```

produces

```
277 - 1
277 - 2
277 - 3
277 - 4
277 - 5
277 - 6
277 - 7
277 - 8
277 - 9
277 - 10
```

Now imagine the identity transformation to be a lengthy process off-loaded to a `ThreadPool`. 
Maybe your elements are ids and you are performing a lookup in a database. 
To simulate that lets delay the flat-mapping step:

```java
long start = System.currentTimeMillis();
AtomicInteger integer = new AtomicInteger();

Flux
        .<Integer>generate(s -> {

            System.out.println(System.currentTimeMillis() - start + " - " + integer.get());
            s.next(integer.incrementAndGet());
        })
        .flatMap(i -> Mono.just(i).delayElement(Duration.ofMillis(20)))
        .take(10)
        .blockLast(Duration.ofSeconds(1));
```

The result:

```
241 - 0
282 - 1
283 - 2
283 - 3
283 - 4
283 - 5
283 - 6
283 - 7
283 - 8
284 - 9
284 - 10
284 - 11
284 - 12
284 - 13
284 - 14
284 - 15

   ...

296 - 253
296 - 254
296 - 255
```

256 lines of output!
Imagine creating these events is an expensive operation! We only wanted 10? 
What is going on?

If you think about it, it is really rather obvious.
`flatMap` is described like this

> Transform the elements emitted by this Flux asynchronously into Publishers, then flatten these inner publishers into a single Flux through merging, which allow them to interleave.

If the events of the `Publisher`s can interleave, they (or at least multiple of them) must get subscribed to and it turns out `flatMap` subscribes to 256 subscribers by default.
And that means it requests 256 elements from the upstream `Publisher`

If you don't want this for one reason or another you can control the concurrency of `flatMap` with an additional parameter:

So this:

```java
        long start = System.currentTimeMillis();
        AtomicInteger integer = new AtomicInteger();

        Flux
                .<Integer>generate(s -> {

                    System.out.println(System.currentTimeMillis() - start + " - " + integer.get());
                    s.next(integer.incrementAndGet());
                })
                .flatMap(i -> Mono.just(i).delayElement(Duration.ofMillis(20)), 20)
                .take(10)
                .blockLast(Duration.ofSeconds(1));
```

produces this output:

```
243 - 0
280 - 1
280 - 2
280 - 3
280 - 4
280 - 5
281 - 6
281 - 7
281 - 8
281 - 9
281 - 10
281 - 11
281 - 12
281 - 13
281 - 14
281 - 15
281 - 16
281 - 17
281 - 18
281 - 19
301 - 20
301 - 21
301 - 22
301 - 23
301 - 24
301 - 25
301 - 26
```

And if you don't want any of the eager subscribing stuff use `concatMap` instead of `flatMap`.
This will wait request an element from upstream, convert it to a `Producer`, subscribe to it and  only when it is closed a new element is requested from upstream.

Just in case you now think I understand all this.
I don't. 
From what I just wrote, one would think that if one simply sleeps in the `Producer` inside a `flatMap` one would again see the 256 elements generated. 
Turns out you don't, you only see 5. 
Not sure yet why, but that is a question for another day.

If you found this arcticle intersting you might als like [my first article about Project Reactor and Threads](/2017/04/15/multithreading-reactor/).