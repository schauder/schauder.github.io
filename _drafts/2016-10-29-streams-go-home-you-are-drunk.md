---
layout: default
status: publish
published: true
title: Streams Go Home, You Are Drunk
author:
  display_name: Jens Schauder
categories: article
tags:
- java8
- streams
- broken
---

For quite some time now, I was confused by the Stream API introduced in Java 8. 
The first question I asked myself was: Why aren't Collections Streams? In every other language
I know functions like map, filter and the like are directly implemented on Lists, Sets and so on.

Ok, Streams are not reusable. So if you create a Stream of Integers from 1 to 10 and used it
to produce the sum of the integers 1 to 10, you can't use the same stream to use the product
of the integers 1 to 10. This is *really* annoying, but at least I can understand that you don't
 want not reusable Lists. 
 
Of course this begs the question, why aren't Streams reusable? I honestly don't know.

But now it gets even worse! consider this piece of code:

    private IntSupplier generator = new IntSupplier() {
        AtomicInteger atomi = new AtomicInteger(0);

        @Override
        public int getAsInt() {
            return atomi.incrementAndGet();
        }
    };


    IntStream.generate(generator)
            .limit(100)
            .map(a -> a * a)
            .sum()

The generator just creates incrementing ints. The last expression then takes the first 100, squares each int
and finally sums them. Pretty trivial stuff. If you do care, the result is 338350

Since we don't have side effect, we should be able to make the calculation parallel:

    IntStream.generate(generator)
            .limit(100)
            .parallel()
            .map(a -> a * a)
            .sum()

So what is the effect of that? Answer: We created a random number generator. I seriously don't know what is going
on, but this returns different numbers on every execution. Only in some rare cases it yields the correct result.

I assume this is a bug, but why does a bug result in a blog article? For me this is a strong sign,
that the Stream API is broken beyond repair. Streams in some way store the manipulations performeed on them,
instead of just creating a new Stream that references the old one and performs the required operation.

This design decision seems to be the reason for

- Streams not being reusable
- Collections not directly being usable as Streams
- And disastrous bugs in trivial code.

Feel free to correct the various assumptions I made in the comments.