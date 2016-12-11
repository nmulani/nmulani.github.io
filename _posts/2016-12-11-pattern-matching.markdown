---
published: true
title: Pattern Matching
layout: post
---
Pattern matching allows us to filter values by patterns and bind variables to successfully identified matches. In practice, this allows us to dissect datatypes for their constituent values and create conditional logic based on different possible values held by variables.

At its most basic, pattern matching allows us to do something like the following example, which looks to see if a variable value holds a certain value or not:


```

   findTen :: Integer -> Bool
   findTen 10 = True
   findTen _ = False

```

If we order our pattern matching from most specific value case to least specific value case, the _ allows us create a conditional pattern based on all the remaining possible pattern values we have not yet filtered for. 

If we do not cover all possible values when doing pattern matching, our program will throw an exception at run-time when such a pattern is encountered. To prevent this, we can use the `-wall` flag to catch these missed pattern combinations at compile time.

Pattern matching is most useful because it allows us to deconstruct more complex datatypes and create conditional logic based on the constituent values of those pieces of data. For instance, we could recombine tuples in the following manner:


```

   f :: (a, b) -> (c, d) -> (e, f) -> ((a, c, e) (b, d, f))
   f (a, b) (c, d) (e, f) = ((a, c, e) (b, d, f))

```

