---
published: true
title: Function Definition in Haskell
layout: post
---
Lambda calculus can be [referred to](http://www.inf.fu-berlin.de/lehre/WS03/alpi/lambda.pdf) as the “smallest universal programming language.” There are two key parts to it: a single way of defining functions, and a single way to evaluate functions (through substituting values for variables).

As in lambda calculus, Haskell functions take one argument and return one result. A function maps one or many arguments to a single output, and will always evaluate to the same output when given the same inputs.

An example of a simple Haskell function: 

`quadruple x = x*4`

`quadruple` is the declaration, which specifies the name of the function.

`x` is the parameter of this function. This corresponds to the “head” of a lambda abstraction and specifies a bound variable occurring in the body.

`=` is used to define the function. It is not a test for equality.

`x*4` is the body of the function, which is evaluated when the function is applied to an argument. The bound variable (in this case, the x) is replaced with the argument.

#### Function Evaluation

Haskell uses “lazy evaluation,” which means terms are not evaluated until forced to by other terms referring to them.  This is also known as “non-strict evaluation.”  This delays evaluation of a function until its output is needed by program execution and can greatly reduce run-time.

The opposite is “eager evaluation” or “strict evaluation.” In this case, expressions are evaluated as soon as variables are bound. This may cause expressions to be unnecessarily evaluated, but also allows the programmer to control order of execution by ordering source code.

#### Prefix vs Infix Syntax

In Haskell, functions default to executing by prefix syntax. This means that the function being applied is at the start of the expression. For instance, the quadruple function we created earlier uses prefix syntax:

```
    > quadruple 10
    40
```

Other functions (such as the arithmetic operators +, -, /…) are, by default, found in an infix position. Functions which can be used in an infix position are referred to as operators:

```
    > 1+1
    2
```

Prefix functions can be sometimes used in an infix position by placing backquotes around them.  Infix functions can be sometimes used in a prefix position with parentheses:

```
    > (+) 1 1
    2
```
