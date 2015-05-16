---
layout: post
title: "Google Summer Of Code with SymPy"
date: 2015-05-16T16:27:59+00:00
tags:
  - OpenSource
  - GSoC
  - SymPy
---

![GSoC](/assets/gsoc/gsoc2015.png)

Much awaited results of [Google Summer Of Code 2015](http://www.google-melange.com/gsoc/projects/list/google/gsoc2015) are finally out. My project **Improving series package and limits in SymPy** has been selected! I will be working with [SymPy](http://www.sympy.org/en/index.html) under [Python Software Foundation](http://www.python.org/psf).

### A little about GSoC

> **[Google Summer of Code](http://en.wikipedia.org/wiki/Google_Summer_of_Code)** is a global program that offers students stipends to write code for open source projects.

### SymPy

> SymPy is a Python library for symbolic mathematics. It aims to become a full-featured **[Computer Algebra System](http://en.wikipedia.org/wiki/Computer_algebra_system)** (CAS) while keeping the code as simple as possible in order to be comprehensible and easily extensible.

### My Project

My Project will be mentored by [Jim Crist](http://github.com/jcrist), [Sean Vig](https://github.com/flacjacket) and [Ondřej Čertík](https://github.com/certik).

The project aims at improving the series infrastructure and limits in SymPy. Sympy currently lacks a proper structure for handling and
manipulating series. All the series related functionality is defined
as methods in *Expr* class. I plan to give the series package a
concrete structure for future development and improvement. I plan to
do the following over the summer.

* Sequence classes for defining sequences of coefficients.
* Classes to represent series in general.
* Implement *Formal Power Series*, using the above implemented structure.
* Computing limits of sequences.

My proposal lives [here](https://github.com/leosartaj/gsoc/tree/master/2015/proposal.pdf)

Looking forward to a great summer!
