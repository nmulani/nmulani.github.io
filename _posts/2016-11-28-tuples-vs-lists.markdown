---
published: false
title: Tuples vs Lists
layout: post
---
Tuples allows us to store multiple values in a single value. Each tuple has a fixed number of members. This means that when tuples are defined as (a, b) or (a, b, c), they will always have two or three members, respectively. The members of each of these tuples can change but the number of members of each tuple cannot change.

We can use fst and snd to obtain the first or second values of a tuple:

```

 > fst (1,2)
  1
 > snd (3, 4)
  4

```

We can also use the swap function from Data.Tuple to change the order of tuple members

```

 > import Data.Tuple
 > swap (“hey”, “ho”)
 (“ho”, “hey”)

```

Like tuples, lists can also store multiple values in a single value. However, they are different from tuples in a few ways:
	1. All list members must be of the same type, but tuple members don’t need to be of the same type. (For example, a list must be [1,2,3] or [“a”, “b”,”c”] but a tuple could be (1, “a”, 2).
	2. Lists use the [...] syntax as opposed to the tuple’s (...).
	3. The number of items in a list can change over time. In a tuple, the [arity](https://en.wikipedia.org/wiki/Arity) is immutable. “Arity” refers to the number of arguments accepted.