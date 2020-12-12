# Lists and Tuples in Haskell
## A blog introducing and showing lists and tuples in Haskell
> __*By Vincent Jodjana*__

Haskell use lists as fundamental structures for managing several values. Lists are also very similar to arrays in Java and C++.

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
If you think about it, strings in Haskells are just lists of characters. This also means values of the type String can be manipulated just like any other list. Instead of entering strings directly as a sequence of characters enclosed in double quotation marks, they can also be constructed through a sequence of Char values. These Char values can be either linked with : and terminated by an empty list or using a comma and bracket notation.

    Prelude> "hello" == ['h', 'e', 'l', 'l', 'o']
    True
    Prelude> "hello: == ['h':'e':'l':'l':'o']
    True

# Lists of Lists
List are able to contain anything under the condition that each value are the same type. Thus, lists are able to contain other lists.

    Prelude> let listOfLists = [[2, 4], [6, 8]]
    Prelude> listOfLists
    [[2, 4], [6, 8]]

You do have to be careful because a list of things does not have the same type as a thing all by itself. For example,

    Prelude> []:[[1,2], [3, 4]]
    [[],[1,2],[3,4]]

    Prelude> ['a']:[[1,2], [3, 4]]
    <interactive>:2:9: error:
        • No instance for (Num Char) arising from the literal ‘1’
        • In the expression: 1
        In the expression: [1, 2]
        In the second argument of ‘(:)’, namely ‘[[1, 2], [3, 4]]’

An empty list can be consed by lists of anything, but ['a'] cannot be consed with a list of list of numbers.

# Tuples
Tuples offer another way to store multiple values in a single values. There are two key differences between lists and tuples:

1. Tuples are immutable or they have a fixed number of elements. You cannot cons to a tuple. It would be best to use tuples in scenarios when you know in advance how many values are to be stored.

2. The elements of a tuple do not have to be of the same type. This is useful compared to lists because list can only be of the same type.

Here are some examples of tuples.

    (False, 2)
    ("Hello", 2, 3, True)

Tuples can also come in handy when you want to return more than one value from a function.

# Tuples Within Tuples
Just like lists, you are able to store tuples within tuples. In addition, you could also have a list of tuples or tuples of lists.

    ((1, 2), False)
    ((1, 2), [1, 2])
    [("a", 2), ("b", 4), ("c", 6), ("d", 8)]

The next blog will be on functions in Haskell.
- [Functions in Haskell](https://github.com/vcjod00/HaskellTutorial/blob/main/blog_7.md)

References:
- [Haskell/Lists and tuples](https://en.wikibooks.org/wiki/Haskell/Lists_and_tuples)



