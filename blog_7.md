# Functions in Haskell
## A blog introducing and discussing functions in Haskell
> __*By Vincent Jodjana*__

If you have taken some programming course before, you should know a function is something in programming that takes an argument value or parameter and gives a result value. If you think about it, it is essentially the same as a mathematical function. To define functions in Haskell is similar to defining a variable. The difference between defining a variable and defining a function is when defining functions, you take note of the function argument that you put on the left hand side. For example, this program defines a function called circumference that is dependent on an argument called d for diameter.

    circumference d = pi * d

This the syntax of a function in Haskell. First is the function name (circumference). Then follows the parameter or argument, which is d. After the = sign is the function definition or the formula that uses the argument with an already defined terms. With the circumference function, we can plug in different values for the argument to call the function. Save the code in a file, load up Haskell, compile the file, and run it.

    stack exec ghci
    Prelude>:load circumference.hs
    *Main> circumference 10
    31.41592653589793
    *Main> circumference 5
    15.707963267948966

# Multiple Parameters
Functions can take more than one parameter. A simple function for calculating the area of a rectangle will prove this.

    area l w = l * w

    *Main> area 5 2
    10

In this example, multiple parameters are separated by spaces, but sometimes you need to use parentheses to group expressions. For example, if you want to quadruple x, you cannot write

    quadruple x = double double x  --this will cause an error

What this would do is apply another function named double to the two arguments double and x. Thus, in order to fix this error, we need to put parentheses arpound the argument.

    quadruple x = double (double x)

In addition, arguments are always passed in the given order. These examples prove my point.

    minus a b = a - b

    *Main> minus 20 10
    10
    *Main> minus 10 20
    -10

You can also utilize functions to define new functions, just like how you can use predefined functions like addition (+) or multiplication (*). To calculate the area of a square, we can reuse our function that calculates the area of a rectangle.

    areaRectangle l w = l * w
    areaSquare s = areaRectangle s s

    *Main> areaSquare 3
    9

# Where Clauses
When you are defining a function, you sometimes need to define intermediate results that are local to the function. One example is using Heron's formula for calculating the area of a triangle with sides x, y, and z:

heron x y z = sqrt(s * (s - x) * (s - y) * (s - z))
    where
    s = (x + y + z) / 2

s is the variable for half the perimeter of the triangle. We wouldn't want to write out s four times in the argument of the square root function sqrt.

# Function Composition
Function composition basically means to apply one function to a value and apply another function to the result. For example, let's say we have these simple functions:

    func x = x + 5
    double x = x ^ 2

We can compose these two functions in different ways, depending on which we apply first:

Prelude> double (func 1)
36
Prelude> double (func 3)
64
Prelude> func (square 2)
9

The parentheses around the inner function are necessary, or the interpreter will think you are trying to get the value of square func or func square, which either or would result in multiple errors. What is interesting is the composition of these two functions result in a function in its own right. If we were to regularly apply func and square or the reverse, we should generate a new variable name for the resulting combinations:

    squareOfFunc x = square (func x)
    funcOfSquare x = func (square x)

Another way to write composed functions is to use (.). This is the function composition operator. Here is how to write it syntatically.

    squareOfFunc x = (square . func) x
    funcOfSquare x = (func . square) x

Interestingly, this idea is modeled after a mathetical operator o, which works in functions like (f o g)(x) = f(g(x)) in mathematics. 

The next blog will be on Recursion in Haskell.
- [Recursion in Haskell](https://github.com/vcjod00/HaskellTutorial/blob/main/blog_7.md)

References:
- [Haskell/Variables and functions](https://en.wikibooks.org/wiki/Haskell/Lists_and_tuples)
- [Haskell/Building Vocabulary](https://en.wikibooks.org/wiki/Haskell/Building_vocabulary)