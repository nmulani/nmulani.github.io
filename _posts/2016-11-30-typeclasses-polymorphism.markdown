---
published: true
title: Typeclasses & Polymorphism
layout: post
---
In Haskell, variable “types” can simultaneously refer to more than one concrete type. This way, functionality can be re-used across specific types that are instances of a more general type. To better explain this, it helps to break down the two types of polymorphism in Haskell:

* Parametric polymorphism describes function parameters which are unconstrained by typeclass. An example of this is the identity function ``` id ```, which has the type signature ``` a -> a ```.

* Ad-hoc polymorphism (also called constrained polymorphism) describes function parameters which have typeclass constraints on them. An example of this is seen with the function negate, which has the type signature ``` Num a -> a -> a ```. This constrains the a variable to the ``` Num ``` typeclass, but now we can do more with the variable ``` a ```. The functionality in the Num class is then passed down to subclasses such as the ``` Double ``` and ``` Int ``` classes.

Typically, parameters defined in a parametric polymorphic manner will usually have less functionality than those defined in a constrained manner. The more specific the typeclass, the more operations are brought into scope for performing on the variable.