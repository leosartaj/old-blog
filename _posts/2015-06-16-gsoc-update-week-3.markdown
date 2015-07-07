---
layout: post
title: "GSoC: Update Week-3"
date: 2015-06-15T21:39:51+00:00
tags:
  - OpenSource
  - GSoC
  - SymPy
permalink: /gsoc-update-week-3
---

This week PR-[\#9435](http://github.com/sympy/sympy/pull/9435), introducing sequences module in SymPy finally got merged. A big thanks to my mentors,
for patiently reviewing my PR.

During the week I worked on ``SeriesBase`` and ``FourierSeries`` class. Much
of the time was spent on polishing these classes. I have opened
PR-[\#9523](http://github.com/sympy/sympy/pull/9523) implementing
the two classes.

<!-- excerpt -->
I also revised my notes on the algorithm for computing Formal Power Series(FPS)
as described in the paper *Formal Power Series, Dominik Gruntz and Wolfram Koepf*.

### What is Formal Power Series?

As wikipedia states

> In mathematics, formal power series are a generalization of polynomials as formal objects, where the number of terms is allowed to be infinite; this implies giving up the possibility to substitute arbitrary values for indeterminates. This perspective contrasts with that of power series, whose variables designate numerical values, and which series therefore only have a definite value if convergence can be established. Formal power series are often used merely to represent the whole collection of their coefficients.

Formal Power series of a functions is of the form \\( f(x) = \sum\limits\_{k=0}^\infty a\_k x^k \\)

### Algorithm for computing FPS of a function

1. If \\( f(x) \\) or \\( f^k(x) \\) is a rational function. Apply <a name='rational' class='int-links'>rational algorithm</a>.
    
    1. Calculate a complex [PFD](http://en.wikipedia.org/wiki/Partial_fraction_decomposition) of f

    2. The coefficient can be found by expanding into binomial series.

        $$ \frac{c}{(x - \alpha)^j} \to \frac{(-1)^j}{\alpha^{j + k}} \binom{j + k - 1}{k} $$ 

2. Find a simpleDE

    1. Fix a number \\( N\_{max} \in N \\) the maximal order of the DE searched for; a suitable value is \\( N\_{max} := 4 \\).

    2. Set N := 1

    3. Search for a DE of the form

        $$ f^k(x) + \sum\limits\_{j=0}^{k-1} A\_j f^j(x) = 0 $$

        \\( A\_j \\) should be rational functions in x.

    4. If (3) is unsuccessful, increase N by 1 and go back to (3), until N = \\( N\_{max} \\)

3. Find the corresponding <a name='RE' class='int-links'>RE</a> of the form

    $$ a\_{n + 1} = \sum\limits\_{k=0}^M r\_{k} a\_{n-k} $$
    
    RE can be found by the following substitution into the DE

    $$ x^l j^k \to (n + 1 - j)\_k . a\_{n + k - j} $$

4. Check the type of RE

    1. If the RE contains only one summand \\( r\_{j} a\_{n-j} \\) on it's right
    hand side, then f is of hypergeometric type and RE can be solved, using
    some initial conditions.

    2. If the DE has constant coefficients, then f is exp-like and can also
    be solved.

    3. If the RE is none of the above types. There are two options.
      
      1. Look for a DE of higher degree, so that a RE of hypergeometric type can be found.
      2. Try to solve RE using known RE solvers.

### Tasks Week-4:

* I have started implementing the Rational Algorithm.
Initial results are promising. In sympy-master computing first 100 terms of series
expansion of \\( \ln(1 + x) \\) takes about 2.92 sec while using rational algorithm and sequences takes
about 15.3 ms, that's faster by roughly a factor of 190.

* Implement a ``FormalPowerSeries`` class that supports functions that are rational or their derivatives are rational, for now.

* If am able to complete this, next on my list will be computing simple DE. This is can be tricky. Sometimes the DE found is not suitable. In this
case a DE of higher degree must be found out. I will have to work out a fast way of doing this.

That's all for now. See you next week.
