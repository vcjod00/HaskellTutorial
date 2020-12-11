# Before You Start Writing Haskell Code
## A blog introducing and showing how to install and run your first haskell code
> __*By Vincent Jodjana*__

# Installing Haskell.
This is installing Haskell on a Mac machine. Your first step is to go ahead and copy and paste on your terminal.

    curl -sSL https://get.haskellstack.org/ | sh

to upgrade to the latest version of stack, run this command.

    stack upgrade

For installing Haskell on Windows, 
You want to configure [chocolatey](https://chocolatey.org/install) on your machine.
Once you have that, run the command at an elevated command prompt like power shell

    choco install haskell-dev refreshenv

# Running Haskell
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

It should return 6 as there are 6 pieces of data in the list.

The next blog will be on variables in Haskell.
- [Variables in Haskell](https://github.com/vcjod00/HaskellTutorial/blob/main/blog_5.md)

References:
- [Installing Haskell from CPSC 354](https://hackmd.io/@alexhkurz/Hk86XnCzD)
- [Haskell: Recursion in Functional Programming](https://hackmd.io/@alexhkurz/H1jUka4Gv)
- [The Haskell Tool Stack](https://docs.haskellstack.org/en/stable/README/)
- [Installing the Haskell Platform on Windows](https://www.haskell.org/platform/windows.html)






