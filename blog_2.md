# Introduction to Haskell
## An introduction to the functional programming language Haskell.
> __*By Vincent Jodjana*__

References:

[Imperative vs Functional Programming from CPSC 354](https://hackmd.io/@alexhkurz/SJKWvna6U)

What is Haskell? The first time I had ever heard of a language came from my CPSC 354 class during my
senior year at Chapman University. Up until then I had no idea of what a functional programming language
was much less Haskell.

![Haskell Logo](https://qualityassignmenthelp.com///wp-content/uploads/2016/11/haskell-logo.jpg)

Haskell first appeared in the 1990s and was named after a mathematician named Haskell Curry.

![Haskell Curry](https://upload.wikimedia.org/wikipedia/commons/8/86/HaskellBCurry.jpg)

# History
Haskell and its semantics were historically based off of the Miranda programming language. Miranda is a type of non-strict purely functional programming language, meaning it lacks imperative programming features. At a conference on Functional Programming Languages and Computer Architecture, there was a discussion to consolidate existing functional languages into a common one to serve as a basis for future research in functional-language design. The first version of Haskell, Haskell 1.0, was defined in 1990. This version of Haskell included Type classes, which enable type-safe operator overloading.

In 1997, Haskell 98 was defined and intended to specify a stable, portable version of Haskell, a standard library for teaching, and to become a base for future extensions of Haskell. This standard was originally published as The Haskell 98 Report. In January 2003, a revised version was published as Haskell 98 Language and Libraries: The Revised Report. The language continues to evolve rapidly, with the Glasgow Haskell Compiler (GHC) implementation representing the current de facto standard.

Haskell 2010, was announced in November 2009 and published in July 2010. It is an incremental update to Haskell, incorporating many kinds of features: hierarchichal module names, foreign function interface (FFI), n + k patterns, type inference, syntax, and language pragma

## Hierarchichal Module Names
Module names are allowed to consist of dot-separated sequences of capitalized identifiers, rather than only one such identifier. This lets modules be named in a hierarchichal manner, although technically modules are still in a single monolithic namespace. 

## Foreign Function Interface
FFI allows bindings to other programming languages. Therefore, data type declarations contained no constructors, enabling robust nonce types for foreign data that could not be constructed in Haskell.

## n + k Patterns
    fact (n + 1) = (n + 1) * fact n
definitions of this form were no longer around. It had misleading semantics where the code looked like it used +, but it desugared code using - and >=.

## Type Inference
The rules of type inference were relaxed for more flexibility to type check

## Syntax
syntax issues, including changes in former grammar, were fixed.
1. pattern guards were added, allowing pattern matching within guards.
2. resolution of operator fixity was specified in a simpler way that reflected actual practice.
3. an edge case in the interaction of the language's lexical syntax of operators and comments was addressed.
4. the interaction of do-notation and if-then-else was tweaked to eliinate unexpected syntax errors.

## Language Pragma
The Language Pragma was specified. Dozens of extensions to Haskell were in use, and the Glascow Haskell Compiler (GHC) and others provided the Language pragma to specify individual extensions with a list of identifiers. Haskell 2010 compilers are required to support Haskell2010 extension as well as others.

# Features
In addition, Haskell features lazy evaluation, lambda expressions, pattern matching, list comprehension, type classes, and type polymorphism. It is a purely functional language, as mentioned previously. It has a strong static type system based on Hindley-Milner type inference. The principal innovation in this area is the type classes. They were originally conceived as a principled way to add overloading to Haskell, but it has found many more uses. Haskell has open, published specification, and multiple implementations exist. However, its main implementation, GHC, is both an interpreter and native-code compiler that runs on most platforms. GHC is noted for its rich type system incorporating recent innovations like generalized algebraic data types and type families.

Now that you know the history and features of Haskell, we will move on to showing the differences between a functional language like Haskell and an Imperative Programming Language like Python.
[What's the difference between Functional and Imperative Programming Languages](https://github.com/vcjod00/HaskellTutorial/blob/main/comparison.md)

References:
- [Haskell on Wikipedia](https://en.wikipedia.org/wiki/Haskell_(programming_language))
- [Miranda on Wikipedia](https://en.wikipedia.org/wiki/Miranda_(programming_language))