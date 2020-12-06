# What's the Difference Between Functional and Imperative Programming Languages?
## A blog describing the differences between functional and imperative programming languages
> __*By Vincent Jodjana*__

Perhaps the most significant difference between functional and imperative programming languages is the fact that functional languages tend to avoid side effects. Side effects are used in imperative languages to implement state and input/output. Pure functional programming languages like Haskell completely prevent side effects and provide referential transparency.

Traditional Imperative Loop:
    num = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
    result = 0
    for i in num:
        if num[i] % 2 == 0:
            result += num[i] * 10

Functional Programming

References:
- [Imperative vs Functional Programming from CPSC 354](https://hackmd.io/@alexhkurz/SJKWvna6U)
- [Functional Programming on Wikipedia](https://en.wikipedia.org/wiki/Functional_programming)