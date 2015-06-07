---
layout: post
title: "GSoC: Update Week-2"
date: 2015-06-07T20:02:29+00:00
tags:
  - OpenSource
  - GSoC
  - SymPy
permalink: /GSoC-Update-Week-2
---

Time flies fast. Two weeks have already passed since I started working on the project. Here's what I have been upto.

### Week-2:

I was hoping [\#9435](http://github.com/sympy/sympy/pull/9435) will get merged this week, but that didn't really went my way.
PR went through another round of review and I got plenty of good suggestions to work with.
It still needs a little more love, to get merged.
 
<!-- excerpt -->
Also started my work on series based classes. I worked on ``SeriesBase`` class. It will be the base class for all the other type of series.
It defines a common interface that other classes should follow.

A long time ago(before GSoC), I wrote some code for computing Fourier series [\#9050](http://github.com/sympy/sympy/pull/9050)
that never got completed. So, I gave a try to port it to the new sequences based system.
It's still not complete and needs some more work. The biggest challenge is speed, it's slow 
because integration is slow. Speeding up integration can be whole new project on it's own.
So, I am not going to touch integration for now, but am still trying to speed it up in the best way I can.

On a side note, I had been working on Fraction Part or ``frac(x)`` ([\#9342](http://github.com/sympy/sympy/pull/9342))
for quite some time now (almost a month). Today it also got merged into the codebase. 
A big thanks to [@jksuom](http://github.com/jksuom) for patiently working with me.

So, overall it's been an average GSoC week with SymPy.

### Tasks Week-3:

* Polish [\#9435](http://github.com/sympy/sympy/pull/9435) and get it merged.
* Complete ``SeriesBase``, ``FourierSeries``
* Start with ``FormalPowerSeries``

That's all for now. Catch you later.

