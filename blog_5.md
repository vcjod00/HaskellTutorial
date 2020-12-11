# Variables in Haskell
## A blog introducing and showing variables in Haskell
> __*By Vincent Jodjana*__

In Haskell, a variable is some valid expression. Unlike other imperative languages, Haskell variables can be kind of misleading, since a variable's value never varies during a program's runtime. Instead, the concept is closer towards a mathematical sense of variables. For example, think of the variable pi to mean 3.14.... This value does not change in the middle of performing a mathematical calculation or proof like imperative languages where one can change the value of their variables

    x = 1
    x = 4

The = operator is used to assign a value to a variable, for example

    phi = 1.618

The scope of these variables can be controlled by using let or where clauses. You can also use variables in Haskell as former parameters to a function. For example,

    add a b = a + b

In this case, a and b are formal parameters for the add function. This would correspond to the notion of "variable" in lambda calculus concepts.

As mentioned earlier, we can store immediate results by assigning them to variables. When you run Haskell, each variable will be substituted for the value to which it refers.

    Prelude> 3.141592653 * 10
    31.4192653

This is an approximate circumference of a circle with the diameter being 10. This of course is according to the circumference formula C = pi * d. Fortunately, Haskell also contains variables like pi that store over a dozen digits of pi for us.

    Prelude> pi 
    3.141592653589793
    Prelude> pi * 10
    31.41592653589793

the variable pi and its value can be used interchangeably in calculations.

# Haskell Source Files
Here is how to write a variable to a file and run it in Haskell. The first step would be to create a file called variable.hs. Then in the file, write the following code.

    d = 10

Then to compile your file, go into your terminal and run

    stack exec ghci

Something like this should appear.

    GHCi, version 8.8.3: https://www.haskell.org/ghc/  :? for help
    Prelude>

Next to Prelude> go ahead and run

    Prelude> :load variable.hs

Something like this should appear.
    
    [1 of 1]  Compiling Main          (variable.hs, interpreted)
    Ok, modules loaded: Main.
    *Main>

Right next to the main, you can go ahead and type

    *Main> d
    10

d means diameter, and it prints out the d variable which has the value 10. We can also simulate the formula for the circumference again by multiplying d with the pi variable. Go ahead and run this, and it should give you back the circumeference of a circle with diameter 10.

    *Main> pi * d
    31.41592653589793

We could also make the circumference formula easier to access by defining a variable name in the variable.hs file. Go back to your file and run this.

    d = 10
    circ = pi * d

Make sure you save the file, go back to your terminal. If you restarted from scratch, you need to do stack exec ghci and then :load variable.hs. If you kept the ghci running, then type :reload like this.

    *Main> :reload
    Compiling Main                  (variable.hs, interpreted)
    Ok, modules loaded: Main.

Now you can go ahead and play with the variables d and circ which is circumference

    *Main> circ
    31.41592653589793
    *Main> circ / 10
    3.141592653589793

In addition, you could also use the let keyword which can help define variables directly at the GHCI prompt without a source file.

    Prelude> let circ = pi * d
    31.41592653589793

# Comparison With Variables in Imperative Languages
As I mentioned before, imperative languages tend to treat variables as changeable locations in a computer's memory. This approach ultimately connects to basic operating principles for computers: that imperative programs explicitly give the computer instructions. On the other hand, functional languages offer a way to think in higher-level mathematical terms, defining how variables relate to one another, and leaving the compiler to translate these to step by step instructions a computer can process. 

    d = 10
    d = 20
    print(d)

You are able to run and print this using python and any other imperative language, but not with Haskell. With python, it would be read as simply setting d = 10 and then d = 20. However, in Haskell, the compiler would respond with an error like multiple declarations of d. In other words, within a given scope, Haskell variables only get defined once and cannot change. The best term to describe Haskell variables are that they are immutable. Immutable means they vary only based on the data we enter into the program.

Another major difference is this:

    d = d + 1

This in Haskell is a recursive definition of d instead of incrementing the variable d. This would be incrementing in the context of an imperative programming language. 




