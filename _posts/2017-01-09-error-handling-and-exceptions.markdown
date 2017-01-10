---
published: true
title: Error Handling and Exceptions
layout: post
---

While working on an implementation of tic-tac-toe in Haskell, I had to figure out how to handle user input errors. The user's position must be entered in the form of a tuple. In order to catch the exception thrown by the parser if the user does not put in a tuple, I ended up using the Either-Left-Right pattern, which works in the following manner:

```

tuple <- getLine
readTuple <- try ((readIO tuple)) :: IO (Either SomeException (Int, Int))
case readTuple of
  Left _ -> do putStrLn "I didn't understand that...try again?"
               getUserMove
  Right _ -> do return (read tuple)

```

In this case statement, the pattern matching allows us to handle exceptions by printing an error message and asking for user input again. If we receive valid input, we can proceed with the program.
