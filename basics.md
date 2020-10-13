# Basics of Haskell
## Introducing the basics of Haskell
> __*By Vincent Jodjana*__

### Before you start.
Make sure you have Haskell downloaded (see [Haskell Platform](https://www.haskell.org/platform/))
Once you have it installed in your terminal, run the command

    stack exec ghci

Something like this should appear

    GHCi, version 8.8.3: https://www.haskell.org/ghc/  :? for help
    Prelude>

Next to Prelude, you could actually type simple instructions directly to the Haskell platform such as

    Prelude> 1 * 3
    3
    Prelude> 2 + 2
    4

You can also write strings which have to be in double quotes.

    Prelude> "Hello, World!"
    Hello, World!
    Prelude> "Hello, Vincent!"
    Hello, Vincent!

In a file such as length.hs, you write the following in your text editor.

    len [] = 0
    len (x:xs) = 1 + len xs

Here the function is known as len which tells you the length of the list.
The first line represents a case where you have an empty list. The second
line is a bit complicated at first, but this is a case where you have a
nonempty list. x represents a piece of data while xs represents the rest
in the list. After the equality sign, there is a recursion where you are
calling the function len again after counting 1 piece of data. This process
will continue to recurse until it reaches the end of the list.

to compile a file on your terminal, run

    stack exec ghci
    Prelude> :load len.hs
 
 Unless it gives you any errors, run

    *Main> len [1, 4, 2, 5, 6, 7]
    6








