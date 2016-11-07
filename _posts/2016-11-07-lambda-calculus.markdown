---
published: true
title: Lambda Calculus
layout: post
tags: [functional, lambda, haskell]
---
While starting to learn Haskell, I've been learning about the lambda calculus, a formal system for describing computational problems. The lambda calculus consists of three parts:

#### Abstractions

Abstractions are functions. They consist of a head (a lambda) and a body. Abstractions are generalizations of computational problems - they become a  specific, concrete instance of a computational problem once applied to arguments.

#### Variables

Variables have no intrinsic meaning or value, but are rather used to denote names of inputs to functions.

#### Expressions

Expressions are combinations of variables, abstractions, and other expressions.

* * *

A typical lambda calculus expression may look like the following:

```
(λx.x)1
```

The "λx" portion of the expression denotes the head of the abstraction, in which the "x" is the parameter accepted by this function. The "x" following the "." is the body of the function, which will be evaluated once the function is applied to an argument. The argument this function is applied to is the 1.

The process for evaluating a function and applying a function to an argument is referred to as beta reduction. The argument is applying to all bound variables within the function. Evaluating a function looks like the following:

```
(λx.x)1
[x := 1]
1
```

The above simple example of a lambda calculus expression is referred to as the "identity function."