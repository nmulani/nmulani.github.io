---
published: true
title: Function Composition and Pointfree Style
layout: post
---

Function composition is a method of passing the results of a first function to be used by a second function. The following three statements in Haskell have identical results and allow us to compose two functions:

```

   abs . sum $ [2,4,6]
   abs (sum [2,4,6])
   (abs . sum) [2,4,6]

```

In the first of the above statements, The composition operator (.) expects a function as input, which is why we include the $ to delay evaluation of the "sum" function until the two functions have been composed.

We can also compose functions without specifying arguments, using "pointfree style":

```

    > let f = abs . sum
    > f [2,4,6]

```
