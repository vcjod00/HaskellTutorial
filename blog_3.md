# What's the Difference Between Functional and Imperative Programming Languages?
## A blog describing the differences between functional and imperative programming languages
> __*By Vincent Jodjana*__

Perhaps the most significant difference between functional and imperative programming languages is the fact that functional languages tend to avoid side effects. Side effects are used in imperative languages to implement state and input/output. Pure functional programming languages like Haskell completely prevent side effects and provide referential transparency.

# Side by Side Comparison of Imperative and Functional Programming
Both programs in Javascript multiply all their even numbers in an array by 10 and add. Then, they store the final sum in the variable result.

Traditional Imperative Loop in Javascript:
    const numList = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
    let result = 0;
    for (let i = 0; i < numList.length; i++) {
        if (numList[i] % 2 === 0) {
            result += numList[i] * 10;
        }
    }

This utilizes looping like in most imperative languages

Functional Programming in Javascript with Higher Order Functions:
    const result = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
               .filter(n => n % 2 === 0)
               .map(a => a * 10)
               .reduce((a, b) => a + b);

This utilizes higher order functions like in functional languages

# Simulating State
There are tasks like maintaining a bank account balance that are implemented with state. In Haskell, they implement these using monads. Monads offer a way to absract certain types of computational patterns. Functional languages can also simulate states through passing around immutable states. For example, one could make a function accept the state as one of its parameters and return a new state together with the result, leaving the old state unchanged.

# Efficiency Issues
Functional Programming Languages tend to be less efficient in terms of their CPU and memory than imperative languages. It is related towards the fact some mutable data structures like arrays have very clear implementations using present hardware. Flat arrays may be accessed very efficiently with deeply pipelined CPUs, prefetched efficiently through caches or handled with SIMD instructions. It is also not easy to create their equally efficient general-purpose immutable counterparts. For purely functional languages, the worst-case scenario is logarithmic in the number of memory cells used because mutable memory can be represented by a purely functional data structure with logarithmic access time. However, such slowdowns are not universal. Languages that perform intensive numerical computations such as OCaml and Clean are only slightly slower than C according to The Computer Language Benchmarks Game. Programs that handle large matrices and multidimensional databases, array functional languages (such as J and K) were designed with speed optimizations.

# Functional Programming in non-functional languages
It is possible to use a functional style of programming in languages that are not traditionally considered functional languages. For example, Python had first class functions from their inception. Python had support for "lambda", "map", "reduce", and "filter" in 1994, as well as closures in Python 2.2 though Python 3 relegated "reduce" to the functools standard library module. First-class functions have been introduced into other mainstream languages such as PHP, C#, C++, and Kotlin. In PHP, anonymous classes, closures and lambdas are fully supported. Libraries and language extensions for immutable data structures are being developed to aid programming in the functional style. In Java, anonymous classes can sometimes be used to simulate closures. However, anonymous classes are not always proper replacements to closures because they have more limited capabilities. Certain Java versions such as Java 8 also support lambda expressions as a replacement for some anonymous classes. In C#, anonymous classes are not necessary, because closures and lambdas are fully supported. Libraries and language extensions for immutable data structures are being developed to aid programming in the functional style in C#. In addition, many object-oriented design patterns are expressible in functional programming terms: for example, the strategy pattern simply dictates use of a higher-order function, and the visitor pattern roughly corresponds to a catamorphism, or fold. Similarly, the idea of immutable data from functional programming is often included in imperative programming languages. For example the tuple in Python, which is an immutable array.

The next blog will be installing Haskell and how to run it
- [Before You Start Writing Haskell Code](https://github.com/vcjod00/HaskellTutorial/blob/main/blog_4.md)

References:
- [Imperative vs Functional Programming from CPSC 354](https://hackmd.io/@alexhkurz/SJKWvna6U)
- [Functional Programming on Wikipedia](https://en.wikipedia.org/wiki/Functional_programming)