---
layout: post
title: "GSoC: Update Week-4"
date: 2015-06-25T09:39:58+00:00
tags:
  - OpenSource
  - GSoC
  - SymPy
permalink: /gsoc-update-week-4
---

This week was mostly spent on completing the [rational algorithm](/gsoc-update-week-3/#rational) for computing
Formal Power Series of a function. It took some time, mainly due to testing.

Rational algorithm is now mostly complete and I have opened 
PR-[\#9572](http://github.com/sympy/sympy/pull/9572) bringing in the changes.
It is still a work in progress. There is still lots to do and test.
So, am gonna spend the next few weeks implementing the rest of the algorithm.

<!-- excerpt -->
So far, the results are good. It is in general [faster](https://github.com/sympy/sympy/pull/9572#issuecomment-115160001) 
than the ``series`` function already implemented in SymPy.

### Tasks Week-5:

* Get PR-[\#9523](http://github.com/sympy/sympy/pull/9523) polished and 
merged.

* Improve the ``FormalPowerSeries`` class.

* Start implementing ``SimpleDE`` and ``DEtoRE`` functions.

I guess, that's it. See you later.
