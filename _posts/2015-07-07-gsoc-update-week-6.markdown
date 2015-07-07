---
layout: post
title: "GSoC: Update Week-6"
date: 2015-07-07T17:56:40+00:00
tags:
  - OpenSource
  - GSoC
  - SymPy
permalink: /gsoc-update-week-6
---

Midterm evaluations are complete. I got to say Google was fairly
quick in mailing the results. It was just after a few minutes
after the deadline, I received a mail telling me I had passed. Yay!

Here's my report for week 6.

<!-- excerpt -->
### Highlights:

#### 1. Formal Power Series:

For the most of the week I worked towards improving the implementation for the second part of the algorithm.
I was able to increase the range of admissible functions.
For this I had to write a custom solver for solving the RE of [hypergeometric](/gsoc-update-week-3/#RE) type.
It's lot faster and better in solving the specific type of RE's this algorithm generates in comparison to
just using ``rsolve`` for all the cases. However, it still has some issues.
It's currently in testing phase and probably will be PR ready by the end of this week.

The code can be found [here](https://github.com/leosartaj/sympy/tree/hyper2).

While working on it, I also added some more features to ``FormalPowerSeries``([\#9572](https://github.com/sympy/sympy/pull/9572)).

Some working examples.
(All the examples were run in isympy)

```
In [1]: fps(sin(x), x)
Out[1]: x - x**3/6 + x**5/120 + O(x**6)
In [2]: fps(cos(x), x)
Out[2]: 1 - x**2/2 + x**4/24 + O(x**6)
In [3]: fps(exp(acosh(x))
Out[3]: I + x - I*x**2/2 - I*x**4/8 + O(x**6)
```

#### 2. rsolve:

During testing, I found that ``rsolve`` raises exceptions
while trying to solve RE's, like ``(k + 1)*g(k)``
and ``(k + 1)*g(k) + (k + 3)*g(k+1) + (k + 5)*g(k+2)`` rather
than simply returning ``None`` which it generally does
incase it is unable to solve a particular RE.
The first and the second RE are formed by functions ``1/x`` and
``(x**2 + x + 1)/x**3`` respectively which can often come up in practice. So, to solve
this I opened [\#9615](https://github.com/sympy/sympy/pull/9615). It is still under review.

#### 3. Fourier Series:

[\#9523](https://github.com/sympy/sympy/pull/9523) introduced ``SeriesBase`` class and ``FourierSeries``.
Both ``FormalPowerSeries`` and ``FourierSeries`` are based on ``SeriesBase``.
Thanks [@flacjacket](https://github.com/flacjacket) and [@jcrist](https://github.com/jcrist)
for reviewing and merging this.

```
In [1]: f = Piecewise((0, x <= 0), (1, True))
In [2]: fourier_series(f, (x, -pi, pi)
Out[2]: 2*sin(x)/pi + 2*sin(3*x)/(3*pi) + 1/2 + ...
```

#### 4. Sequences:

While playing around with sequences, I realized periodic
sequences can be made more powerful. They can now be used for 
periodic formulas([\#9613](https://github.com/sympy/sympy/pull/9613)).

```
In [1]: sequence((k, k**2, k**3))
Out[2]: [0, 1, 8, 3, ...]
```

#### 5. Others:

Well I got tired with ``FormalPowerSeries``(I am just a human), so
I took a little detour from my regular project work and opened 
[\#9622](https://github.com/sympy/sympy/pull/9622) and [\#9626](https://github.com/sympy/sympy/pull/9626)
The first one deals with inconsistent diff of Polys while
while the second adds more assumption handler's like ``is_positive``
to ``Min/Max``.

### Tasks Week-7:

* Test and polish [hyper2](https://github.com/leosartaj/sympy/tree/hyper2) branch. Complete the algorithm.
* Add sphinx docs for ``FourierSeries``.
* Start thinking on the operations that can be performed on ``FormalPowerSeries``.

That's it. See you all next week. Happy Coding!
