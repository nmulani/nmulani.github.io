---
published: true
title: Anonymous Functions
layout: post
---
Anonymous functions are, quite literally, functions "without names." They are particularly useful when we need to whip up a function on-the-fly, either as an input into another function, or as output returned from another function.

For instance, we could write a function to subtract 10 from a given function in one of two ways:

**Named**

```

   subtractTen :: Integer -> Integer
   subtractTen x = x - 10

```


**Anonymous**

```

   (\x -> x -10) :: Integer -> Integer

```

A function which might commonly accept another function as input is `map`. In the below example, we are adding one to each element in a list using an anonymous function passed to `map`:

```

   addOneList lst = map (\x -> x + 1) lst

```