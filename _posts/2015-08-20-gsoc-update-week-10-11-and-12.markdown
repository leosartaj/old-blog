---
layout: post
title: "GSoC: Update Week-10, 11 and 12"
date: 2015-08-20T14:28:44+00:00
tags:
  - OpenSource
  - GSoC
  - SymPy
permalink: /gsoc-update-week-10-11-and-12
---

This is the 12th week. Hard deadline is this Friday. GSoC is coming to an end leaving behind a wonderful experience.
Well here's how my past few weeks went.

<!-- excerpt -->
### Highlights:

Work on Formal Power Series:

* [\#9776](https://github.com/sympy/sympy/pull/9776) added the ``fps`` method in ``Expr`` class. Instead of
  ``fps(sin(x))``, user can now simply do ``sin(x).fps()``.
* [\#9782](https://github.com/sympy/sympy/pull/9782) implements some basic operations like addition, subtraction
  on ``FormalPowerSeries``. The review is almost complete and should get
  merged soon.
* [\#9783](https://github.com/sympy/sympy/pull/9783) added the sphinx docs for the ``series.formal`` module.
* [\#9789](https://github.com/sympy/sympy/pull/9789) replaced all the ``solve`` calls in the ``series.formal`` with the
  new ``solveset`` function.

Work on computing limits of sequences:

This is the second part of my GSoC project aiming to implement the algorithm
for computing limits of sequences as described in the poster
*Computing Limits Of Sequences* by *Manuel Kauers*.

* [\#9803](https://github.com/sympy/sympy/pull/9803) implemented the ``difference_delta`` function.
  ``difference_delta(a(n), n)`` is defined as `a(n + 1) - a(n)`. It is the
  discrete analogous of differentiation.
* [\#9836](https://github.com/sympy/sympy/pull/9836) aims at completing the implementation of the algorithm.
  It is still under review and hopefully it will be in soon.

### Final Tasks:

Get [\#9782](https://github.com/sympy/sympy/pull/9782) and [\#9836](https://github.com/sympy/sympy/pull/9836) merged soon.

### Upcoming:

A thank you post ;)
