---
layout: default
status: publish
published: true
title: Multithreading with Reactor
author:
  display_name: Jens Schauder
categories: article
tags:
- java
- reactive
- reactor
---

I recently started working with (ok, fooling around is a better wording) Reactor, a reactive library that gets used by the new reactive parts of Spring. I'm especially interested in how multithreading works with Reactor. So here is what I learned so far.


## Some utilities

Break points are difficult to use with call backs and almost useless in multithreaded scenarios, so when playing around with Reactor I soon created some tiny tools to help me along.

The first tool is a tiny function that appends the name of the current `Thread` to the string representation of the `Flux`s elements.

```java
static Flux<String> addThread(Flux<?> flux) {
	return flux.map(e -> e + " " + Thread.currentThread());
}
```

It can help a lot when trying to understand what is going on with `Threads`

The second one requires that operations on a `Flux` get executed in a certain `Thread`. It uses JUnit and Hamcrest for this.

```java
static <T> Flux<T> assertThread(Flux<T> flux, String name) {
	return flux.doOnNext(
			e -> assertThat(Thread.currentThread().getName(),
					startsWith(name))
	);
}
```
Also the tests have a `String` member `threadName`, containing the name of the `Thread` executing the test.

## Reactor is single threaded by default.

We can see this with the following simple test.

```java
@Test
public void reactorIsSingleThreadedByDefault() {

	Flux<Integer> flux = Flux.range(0, 1000);

	assertThread(flux, threadName)
			.blockLast(Duration.ofSeconds(1));
}
```
	
But there are many operations that use other `Thread`s, especially those that delay elements.

```java
@Test
public void delayingElementsIntroducesThreads() {
	Flux<Integer> flux = Flux.range(0, 1000)
			.delayElements(Duration.ofMillis(1));
	assertThread(flux, "timer")
			.blockLast(Duration.ofSeconds(3));
}
```

## How to execute stuff on other threads

If you search for ways to do multithreading, you probably come across the two methods `subscribeOn` and `publishOn`. Both cause the following operation to execute on the specified thread (actually you provide a `Scheduler`, which in our case encapsulates a thread).

```java
@Test
public void publishOn() {

	Flux<Integer> flux = Flux.range(0, 1000)
			.publishOn(Schedulers.newSingle("newThread"));

	assertThread(flux, "newThread")
			.blockLast(Duration.ofSeconds(1));
}

@Test
public void subscribeOn() {

	Flux<Integer> flux = Flux.range(0, 1000)
			.subscribeOn(Schedulers.newSingle("newThread"));

	assertThread(flux, "newThread")
			.blockLast(Duration.ofSeconds(1));
}
```

The obvious question is "What is the difference?"

For this to understand we look at what happens when we combine multiple calls to these methods.

```java
@Test
public void publishOnTwice() {
	Flux<Integer> flux = Flux.range(0, 1000);
	Flux<Integer> fluxOnOne = assertThread(flux.publishOn(Schedulers.newSingle("one")), "one");
	Flux<Integer> fluxOnOneOnTwo = assertThread(fluxOnOne.publishOn(Schedulers.newSingle("two")), "two");
	fluxOnOneOnTwo.blockLast(Duration.ofSeconds(1));
}
@Test
public void subscribeOnTwice() {
	Flux<Integer> flux = Flux.range(0, 1000);
	Flux<Integer> fluxOnOne = assertThread(flux.subscribeOn(Schedulers.newSingle("one")), "one");
	Flux<Integer> fluxOnOneOnTwo = assertThread(fluxOnOne.subscribeOn(Schedulers.newSingle("two")), "one");
	fluxOnOneOnTwo.blockLast(Duration.ofSeconds(1));
}
```

`publishOn` causes the execution of everything after it to happen on the `Scheduler` past in as an argument, until `publishOn` gets invoked again. Compare that to `suscrieOn` where basically the first call determines which `Scheduler` gets used and the calls afterwards get ignored.

Well not ignored, but they don't have an effect that is easily visible. To understand this we need to think what actually happens inside a reactive pipeline. If we use "operators" on a `Flux` (_A_) we create a new `Flux` (_B_). When we subscribe to _B_ it in turn subscribes to _A_. _A_ in turn starts to publish events by calling _B_, which in turn calls our `Subscriber`. So we basically go through the stack of `Fluxe`s twice, once on the "subscribe way", and once (or actually for each event) on the "publish way". All the asserting we are doing only happens on the publish way, where also all of the normal functionality in a real call. 

If we have multiple `subscribeOn`s in the pipeline they affect only the subscribe way but we normally don't see that. Only the last `subscribeOn` affects the publish way. This is the only one we see.

Multiple `publishOn`s on the other hand affect the publish way and we can observe every step of it, so we actually do see the effect of each of it.

The code for the test is [available as a Gist](https://gist.github.com/schauder/7f14d898ef00b85e49d92ecbbf78cd7a).

Next up should be an article how `publishOn` and `subscribeOn` interact with `flatMap`. Hope it doesn't take as long as this article.