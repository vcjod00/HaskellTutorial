# Lists and Tuples in Haskell
## A blog introducing and showing lists and tuples in Haskell
> __*By Vincent Jodjana*__

Haskell use lists and tuples as fundamental structures for managing several values. Lists and tuples are similar in the sense that they group multiple values into a single combined value. Lists are also very similar to arrays in Java and C++.

    Prelude> let numbers = [2, 4, 6, 8]
    Prelude> let truths = [True, True, False]
    Prelude> let strings = ["these", "are", "a", "few", "strings"]

These are very similar to the way you would write lists in python.

    >>> numbers = [2, 4, 5, 8]
    >>> truths = [True, True, False]
    >>> strings = ["these", "are", "a", "few", "strings"]

However, unlike Python lists, Haskell lists must be of the same type

    >>> random = [2, "four", False, 8.0]
    >>> print(random)
    [2, 'four', False, 8.0]

Haskell lists with different types would produce an error like this.
    Prelude> let random = [2, "four", False, 8.0]

    <interactive>:4:26: error:
        • Couldn't match expected type ‘[Char]’ with actual type ‘Bool’
        • In the expression: False
        In the expression: [2, "four", False, 8.0]
        In an equation for ‘random’: random = [2, "four", False, ....]

# Building lists
You can build up lists piece by piece using the : operator. It is known as the "cons" operator. This term to describe building up a list is known as consing. It originated from LISP programmers who invented the word "to cons", meaning constructor, to refer to this specific task of prepending an element to a list.

    Prelude> let list = [1, 2]
    Prelude> list
    Prelude> 0:list
    [0,1,2]

When you cons something onto a list (something:someList), you get back another list. In other words, you are allowed to keep consing for as long as you wish. The cons operator takes the first value to its left, and the whole expression to its right.

    Prelude> 1:0:list
    [1,0,1,2]
    Prelude> 4:3:2:1:list
    [4,3,2,1,1,2]

When using cons, it is important to remember that the elements of a list must have the same type and you can only cons something onto a list, and not the other way around. In other words, the final item on the righ has to be a list, and the items of the left must be independent elements.

    Prelude> False:True
    <interactive>:12:7: error:
        • Couldn't match expected type ‘[Bool]’ with actual type ‘Bool’
        • In the second argument of ‘(:)’, namely ‘True’
        In the expression: False : True
        In an equation for ‘it’: it = False : True

# Strings are lists


