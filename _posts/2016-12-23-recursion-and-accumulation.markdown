---
published: true
title: Recursion and Accumulation
layout: post
---

While working through one of the Euler problems, I realized I needed to increment my input into a recursive function during each go-around. Since I am used to the Javascript for-loop method of just adding a ++ or +=, I just added a "+1" to the recursive function call, as follows:

```

   recursiveFunction :: Integer -> Integer
   recursiveFunction x
     | all (\y->(mod x y == 0)) [1,2,3,4] = x
     | otherwise = recursiveFunction x+1

```

This function adds one to our input value until we find a number that is divisible by 1, 2, 3 and 4. However, when we run this with the input value 1, we get the following error:

```

    > recursiveFunction 1
    *** Exception: stack overflow


```

But if we were to type in "recursiveFunction 12," we would immediately get the answer 12, because our testing logic is correct. Then what's the issue here?

The issue is that the actions to increment the variable are being added to a long list of calculations that the compiler is waiting to complete. In Haskell-speak, the "x+1" in our function is referred to as the "accumulating parameter," which allows us to make our function "tail recursive."

In order to make sure that the accumulating parameter is evaluated prior to the function re-executing, we can use the "$!" marker, like so:

```

   recursiveFunction :: Integer -> Integer
   recursiveFunction x
     | all (\y->(mod x y == 0)) [1,2,3,4] = x
     | otherwise = recursiveFunction $! x+1

```

This ensures the "x+1" will be evaluated prior to tail recursion, and prevents stack overflow from occurring.
