# What's the Difference Between Functional and Imperative Programming Languages?
## A blog describing the differences between functional and imperative programming languages
> __*By Vincent Jodjana*__

How does Haskell compare with my personal favorite programming lanuage Python?
Well, the first thing that was interesting was they can both be instructed to
directly. For example, in Haskell you have

    stack exec ghci
    Prelude> 1 * 5
    5

Python you can instruct it similarly

    python
    >>> 1 * 5
    5

Another thing is syntatically, they are both fairly simple. Syntax like C++, C, or
Java can really throw someone off at first sight. That is probably why Python is
one of the most suggested languages to start with when people are first exposed to
programming.

Where it differentiates is first in the fact that Python is an imperative programming
language and Haskell is a functional programming language. You can look at my
[introduction](https://github.com/vcjod00/HaskellTutorial/blob/main/introduction.md)
blog for more details on the difference between Haskell and an imperative programming
language.

Their syntax for how they set up their functions are also different. Haskell simply gives
a function name.

    add O n = n
    add (S n) m = S (add n m)

Python, on the other hand...

    def add(s, n):
        if s == 0:
            ...
        else:
            ...add(s, n)

Remember Haskell is functional, so everything is expressive. There are not assigned statements
like in Python. While Python can use recursive statements, they can also use loops whereas
Haskell not so much.