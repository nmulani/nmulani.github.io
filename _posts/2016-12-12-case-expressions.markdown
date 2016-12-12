---
published: true
title: Case Expressions
layout: post
---
Case expressions are a formal way to write out the conditional logic we previously saw in pattern matching piece-wise functions.

Let's take a piece-wise function 'findTen' similar to the one that used pattern matching to tell us if a value was equivalent to 10:

```

   findTen :: Integer -> [Char]
     findTen 10 = "Found ten"
     findTen _ = "Didn't find ten"

```

As a case expression, the same function could be written as:


```

   findTen :: Integer -> Bool
     findTen n = case (n == 10) of
       True -> "Found ten"
       False -> "Didn't find ten"

```

Usually, case expressions will be most useful in cases where there are more than just two "True" or "False" cases. For instance, imagine the output cases of using the [compare](http://zvon.org/other/haskell/Outputprelude/compare_f.html) function. The possible cases involve GT (Greater Than), LT (Less Than) and EQ (Equal):


```

   greaterThanTen :: Integer -> [Char]
     greaterThanTen n = case compare n 10 of
       GT -> "Value was greater than ten"
       EQ -> "Value is equivalent to ten"
       LT -> "Value is less than ten"

```
