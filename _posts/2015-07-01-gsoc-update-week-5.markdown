---
layout: post
title: "GSoC: Update Week-5"
date: 2015-07-01T17:03:41+00:00
tags:
  - OpenSource
  - GSoC
  - SymPy
permalink: /gsoc-update-week-5
---

Yesterday, I had a meeting with my mentor [@jcrist](http://github.com/jcrist). It was decided
that we will meet every Tuesday on [gitter](http://gitter.im/sympy/sympy) at 7:30 P.M IST. We discussed
my next steps in implementing the algorithm and completing ``FormalPowerSeries``.

<!-- excerpt -->
### Highlights:

* Most of my time was spent on writing a rough implementation
  for the second part of the algorithm. Currently it is able
  to compute series for some functions. But fails for a lot
  of them. Some early testing indicates, this maybe due to
  ``rsolve`` not being able to solve some type of recurrence equations.

* ``FourierSeries`` and ``FormalPowerSeries`` no longer computes the
  series of a function. Computation is performed inside ``fourier_series``
  and ``fps`` functions respectively. Both the classes are now
  used for *representing* the series only.

* I decided it was time to add sphinx documentation for
  ``sequences``. So, I opened [\#9590](http://github.com/sympy/sympy/pull/9590). Probably, it will be
  best to add documentation at the same time as the implementation from
  next time.

* Also opened [\#9599](http://github.com/sympy/sympy/pull/9599) that allows ``Idx`` instances to be used
  as limits in both ``Sum`` and ``sequence``.

### Tasks Week-6:

* [\#9523](http://github.com/sympy/sympy/pull/9523)'s review is mostly done and should get merged soon. Also,
  add the documentation for Fourier series.

* Polish [\#9572](http://github.com/sympy/sympy/pull/9572) and make it more robust.

* Improve the range of functions for which series can be computed. Probably
  will need to improve the algorithm for solving the recurrence equations.

This week is going to be fun. Lots to do :)
