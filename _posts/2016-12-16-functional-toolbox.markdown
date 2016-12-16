---
published: true
title: Functional Toolbox
layout: post
---
There are a fewreally handy features in Haskell that have proved invaluable while I've been working through the first few Euler problems. These are the fold, filter and map functions.

##fold

Fold allows us to combine a given list using a function of our choosing. Unlike multiplication or addition, not all functions have the associative property, which is why Haskell supplies us with two alternatives: foldl, combines the last element with the iterative results of combining the rest of the list to the left, or foldr, which combines the first element with the iterative results of combining the rest of the list to the right. 

The foldl and foldr functions also accept an initial value - this initial value is the one combined with the list's first value in the case of using foldr is used once the list has been fully iterated over. This is what happens in practice:

```

   > foldr (-) 0 [1,2,3]
   -- ((1 - (2-3)) - 0)= 2
   2

```

```

   > foldl (-) 0 [1,2,3]
   -- (((0-3)-2)-1) = -6
   -6

```

##filter

Filter allows us to quickly narrow down a list to only those elements that meet certain criteria. For instance, we can quickly figure out which numbers in a list are divisible by either 3 or 7 by doing the following:

```

   let xs = [3, 12, 13, 14, 15, 16]
   > filter (\n -> (mod n 3 == 0) || (mod n 7 == 0)) xs
   [3,12,14,15]

```

##map

Map allows us to transform a list by applying a given function to each element. For instance, in the following example, we replace each element of a list with its remainder when it is divided by two:

```

   let xs = [3,4,5,6,7]
   > map (\n -> mod n 2) xs
   [1,0,1,0,1]

```

