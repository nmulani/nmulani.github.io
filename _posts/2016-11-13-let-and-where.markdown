---
published: true
title: Let and Where
layout: post
---
In Haskell, "let" and "where" are both tools used to define the scope over which a variable binding applies. 
"Let" introduces an expression and can allow for nested bindings, as in the following example:

```
let y   = a*b
     f c = c*y
in f d - f e
```

On the other hand, "where" is declarative and is bound to a syntactical construct, which makes it convenient to apply a binding to a set of guarded equations (guarded equations in Haskell are similar to [piecewise functions](https://en.wikipedia.org/wiki/Piecewise) in mathematics):

```
f x
  | conditionA x   = c
  | conditionB x   = g c
  | otherwise = f (h x c)
  where
    c = w x
```