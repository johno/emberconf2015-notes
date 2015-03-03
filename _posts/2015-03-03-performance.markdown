---
layout: post
title:  Performance 
date:   2015-03-03 11:03:20
categories:
speaker: Stefan Penner
---

Javascript performance is about iterating over arrays, the black box of Javascript
performance.

> Promises seem really slow.

Until promises became an order of magnitude faster.

#### What'd they do?

Bluebird did less work: Allocate fewer objects and align with the underlying primitives.
This was done without an external API change!

> stability without stagnation

## Continue with performance

By reducing confusion, we can make Ember faster than it is today.

Guided evolution, can't evolve too quickly. Must be productive for developers, but performant.

## So it goes...

Patch 1: 5% improvement
Patch 2: 5% improvement
Patch 1 + Patch 2: 10% regression

Is type information optimizable? Sure, we can specialize (crankshaft).

`a + b` can be optimized to b 100x faster. However, it can be more brittle.

The compiler has a concept of shapes. If the runtime believes the code is stable, it can
be optimized. Allocation and cleanup is _expensive_. Just like closures, objects, compiled code,
and shape allocations.

Well-factored code can introduce fewer shapes => performance.

## Mis-alignments

* Ember does too much work
  * Actions up, bindings down
  * Singleton controllers
  * Improved clarity => faster
* Init/super
  * Hard to learn
  * Extra shapes
  * Prototype reads
  * Mis-aligned with ES2015
  * We should embrace super

