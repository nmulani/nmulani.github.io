---
published: true
title: String Operators
layout: post
tags: [haskell, strings]
---
In Haskell, strings are lists of characters (their type is [Char]). There are a few operators useful to manipulate strings:

### : or cons
: can be used to add an element to a list.
```haskell
> 'a' : "bcd"
"abcd"
```

### head
Head returns the first element in a list.
```haskell
> head "Hello World"
"H"
```

### tail
Tail returns the rest of a list after the head
```haskell
> tail "Hello World"
"ello World"
```

### take
Take returns the first x items of a list
```haskell
> take 5 "Hello World"
"Hello"
```

### drop
Drop removes the first x elements from a list and returns the remainder
```haskell
> drop 5 "Hello World"
" World"
```

### !!
!! returns the element at the specified index in the list
```haskell
> "Hello World" !! 5
" "
```

### ++
++ is used to concatenate, or join together, lists.
```haskell
> "Hello " ++ "World"
"Hello World"
```
