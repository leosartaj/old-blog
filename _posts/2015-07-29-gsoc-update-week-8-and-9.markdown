---
layout: post
title: "GSoC: Update Week 8 and 9"
date: 2015-07-29T18:20:56+00:00
tags:
  - OpenSource
  - GSoC
  - SymPy
permalink: /gsoc-update-week-8-and-9
---

It's been a long time since my last post. Holidays are now over and 
my classes have started. Last few days have been hectic for me.
Here's the highlights of my last two weeks with SymPy.

<!-- excerpt -->
### Highlights:

My implementation of the algorithm to compute formal
power series is finally done. As a result [\#9639](http://github.com/sympy/sympy/pull/9639)
finally got merged. Thanks Jim and Sean for all the help. 
As [\#9639](http://github.com/sympy/sympy/pull/9639) brought in all the necessary changes
[\#9572](http://github.com/sympy/sympy/pull/9572) was closed.

In the SymPy master,

```
>>> fps(sin(x), x)
x - x**3/6 + x**5/120 + O(x**6)
>>> fps(1/(1-x), x)
1 + x + x**2 + x**3 + x**4 + x**5 + O(x**6)
```

On a side note, I was invited for Push access by Aaron.
Thanks Aaron. :)

### Tasks:

* Improve test coverage of ``series.formal``.
* Start working on operations on Formal Power Series.
