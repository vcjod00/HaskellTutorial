# Recursion
## A blog discussing Recursion and how it's used in Haskell
> __*By Vincent Jodjana*__

Recursion plays a central role in Haskell, as well as many other functional programming languages. It is applied a lot in computer science and mathematics. Recursion is a form of repitition in its basic definition or a recursive function is a function that has the ability to invoke itself. Only when a condition is met does it invoke itself, as with an if/else/then expression or a pattern match which contains at least one base case that terminates the recursion, or a recursive case which causes the function to call itself, creating a loop. Without a terminating condition, a recursive function has the potential to remain in a loop forever, causing an infinite loop.

# The Factorial Function
In mathematics, there is a function known as a factorial. What it does basically is take a single non-negative integer as an argument, find all of the positive integers less than or equal to "n", and multiply them all together. For example, the factorial of 3 (3!) is 1 * 2 * 3 = 6. We can use recursion to define a factorial function in Haskell. However, before that we want to see factorials of consecutive numbers to figure out how to create the algorithm for a factorial function.

    Factorial of 4 = 1 * 2 * 3 * 4
    Factorial of 3 = 1 * 2 * 3
    Factorial of 2 = 1 * 2
    Factorial of 1 = 1

What is the factorial of 0? It is one. 0 is the base case for the recursion. When we get 0, we immediately no the answer is one with no recursion necessary. Thus, here is our definition of the factorial function.

    The factorial of 0 is 1.
    The factorial of any other number is the number multiplied by the factorial of the number one less than it.

This is what it would be written like in Haskell.

    factorial 0 = 1
    factorial n = n * factorial (n - 1)

Here, we are defining a function called factorial. The first line declares that the factorial of 0 is 1, and the second line says that factorial of any other number n is equal to n times the factorial of n - 1. In addition, you can actually write this function in GHCI as a one liner due to it being a small function.

    Prelude> let factorial 0 = 1; factorial n = n * factorial (n - 1)

Let's run factorial 2 in Haskell

    *Main> factorial 2
    2

2 is not 0, so we calculate the factorial of 1. 1 is also not 0, so we calculate the factorial of 0. 0 is the base case, so we return 1. To complete the calculation of factorial 1, we multiply the current number 1 by the factorial of 0 which is 1 which means 1. To complete the calculation for factorial 2, we multiply the current number 2, by the factorial of 1, which is 1, obtaining 2. Thus the function overall returns 2 at the end when ran.

# Loops, Recursion, and Accumulating Parameters

Imperative languages use loops similar to how Haskell uses recursion. For example, here is how to write the factorial function in an imperative language like C.

    int factorial(int n) {
        int res = 1;
        for ( ; n > 1; n --)
            res * = n;
        return res;
    }

The loop causes res to be multiplied by n repeatedly. After each repetition, 1 is subtracted from n or is decrementing. The repetition ultimately stops when n is no longer greater than 1. Unfortunately for Haskell, you cannot directly translate it from C because changing the variables res and n wouldn't be allowed.

# Other Recursive Functions
Multiplication is another function that uses recursion in programming languages like Haskell. In discrete mathematics, we learned that multiplication is learned through a slow process of repeated addition. Take 5 * 4 for example. 5 * 4 is basically summing four copies of the number 5 or 5 + 5 + 5 + 5. Summing four copies is the same as summing three copies and adding one more or 5 * 4 = 5 * 3 + 5. This shows us the natural recursive definition of mulitplication.

    mult a 0 = 0
    mult a b = (mult a (b - 1)) + n

The first one again is our base case. Any number times 0 ultimately becomes 0 whether 1 * 0 or infinity * 0. The second case obviously involves recursion. When multiplied, you multiply by one less, then add an extra copy, just like our case with 5 * 4 = 5 * 3 + 5 and so forth.

# List - Based Recursion
There are recursive functions in Haskell concerning lists. For example, using the length function.

    myLength [] = 0
    myLength (a:as) = 1 + myLength as

Again, your base case is if it is an empty list, than the length is 0. Otherwise, we go to the recursive case: if a list isn't empty, it can be broken down to a first element a and the rest of the list will be as. The length will be 1 plus the length of as or the tail. We can also do a concatenation function, which joins two lists together.

    [] ++ ys = ys
    (x:xs) ++ ys = x : xs ++ ys

The base case is when you concatenate anything with an empty string, you get the exact same as before or ys in this case. For the recursive case, you break the first list into its head and tail. Then you concatenate the two lists. Recursion ultimately is used to define nearly all functions with lists and numbers.

The next blog will be on Extra Sources for learning Haskell. 
- [Extra Sources](https://github.com/vcjod00/HaskellTutorial/blob/main/blog_9.md)

References:
- [Haskell/Recursion](https://en.wikibooks.org/wiki/Haskell/Recursion)
- [Imperative vs Functional Programming](https://hackmd.io/@alexhkurz/SJKWvna6U)
- [Haskell: Recursion in Functional Programming](https://hackmd.io/@alexhkurz/H1jUka4Gv)
