---
layout: post
title: "GSoC: Fun Begins"
date: 2015-05-27T19:10:32+00:00
tags:
  - OpenSource
  - GSoC
  - SymPy
permalink: /GSoC-Fun-Begins
---

The community bonding period ended a few days ago (25th May). Community bonding period provided me with ample time to again go through my [proposal](https://github.com/sympy/sympy/wiki/GSoC-2015-Application-Sartaj-Singh:-Improving-the-series-package-and-limits-in-SymPy), which I did.
I had a meeting with my mentors [Jim Crist](http://github.com/jcrist) and [Sean Vig](http://github.com/flacjacket) on 13th May on
sympy's [gitter](http://gitter.im/sympy/sympy) channel. We discussed on the first part of my proposal i.e. [sequences](https://github.com/sympy/sympy/wiki/GSoC-2015-Application-Sartaj-Singh:-Improving-the-series-package-and-limits-in-SymPy).

<!-- excerpt -->
We decided that there will be a base class, from which every sequence will inherit (Periodical, functional and formula based sequences).
Another major point was about caching and it's importance in general. It is still a little fuzzy and it will be best to decide after some experimentation.

### Coding Period Begins!

Well, the coding period has begun. I again had a meeting on 26th May. This was more focused on my progress and any general problem, I maybe facing.
I had made two commits by then, implementing SeqBase class and EmptySequence.

In my timeline, I reserved first two weeks for implementing sequences and operations on them.

Main Tasks for this and the upcoming week:

* SeqBase Class
* EmptySequence
* SeqExpr Class (SeqPer, SeqFunc, SeqFormula inherit from it)
* SeqPer, SeqFormula, SeqFunc class
* Container class and function for the above sequences
* Term-wise addition/subtraction
* term-wise Multiplication
* Experimenting with Caching
* Pretty Printing

I have implemented the first version of the first four points. The work is still in progress but I have made a
[PR(#9435)](http://github.com/sympy/sympy/pull/9435), as suggested by my mentors, to start the review process *early*.

I will be back by the end of this week. Should get back to work. Have fun.
