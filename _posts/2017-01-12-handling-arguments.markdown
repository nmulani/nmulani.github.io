---
published: true
title: Handling Arguments
layout: post
---

As part of my tic-tac-toe project, I wanted to make it possible for the user to decide how difficult their game of tic-tac-toe would be. To do this, I allow the user to pass an argument to the program when initiating it (either `E` for easy or `H` for hard.)

In order to accept arguments in Haskell, the `System.Environment` package needs to be imported. From there, it's simply a matter of creating a case statement within main to deal with various argument scenarios.

I made the initial mistake of assuming I'd be able to test passing arguments in the interpreter with `main`, but I continually faced errors when attempting to do this. It seems like the program must be compiled and then arguments must be passed to the binary for proper testing.

```

> stack ghc tictactoe.hs
> ./tictactoe E

```

This is how the case statement within main can be structured to handle arguments passed - arguments are passed as part of a list of `String`s:

```

main :: IO ()
main = do args <- getArgs
          case args of
             ["H"] -> do clearScreen
                         putStrLn "Playing in hard mode"
                         playGame startingBoard "H"
             ["E"] -> do clearScreen
                         putStrLn "Playing in easy mode"
                         playGame startingBoard "E"
             _ -> do clearScreen
                     putStrLn "Arguments not understood. Playing in default easy mode."
                     playGame startingBoard "E"

```
