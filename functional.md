# An Understanding of Functional Programming
## A blog describing what is functional programming
> __*By Vincent Jodjana*__

What was your first language when you first learned to code? Mine was C++. Some people started with Python. Others with Java. What do those languages have in common? Well, they are known as imperative programming languages. When I took a class called Programming Languages or CPSC 354 in my senior year at Chapman, I learned about a functional programming language called Haskell.

![Chapman University](https://www.glumac.com/content/uploads/2016/03/m_2507_0001.jpg)

So what is a functional programming language? Well, they are essentially programming languages that are constructed by applying and composing functions, hence the name functional. The functional definitions in functional languages are trees of expressions that each return a value. This is different from imperative languages in that imperative programming languages can use instructional statements that can change the state of a program. For more information regarding the difference between functional programming and imperative programming, you can check the blog on [comparing imperative and functional programming languages](https://github.com/vcjod00/HaskellTutorial/blob/main/comparison.md).

Interestingly, functional programming has roots in academics, coming from concepts of lambda calculus which is a formal system of computation based on functions. Lambda calculus was developed by a man named Alonzo Church, who discovered his theory on lambda calculus and the Turing machines invented by Alan Turing are equivalent models of computation. Turing machines are mathematical models of computation that defines abstract machines. They manipulate symbols on strips of tapes according to a tabel of rules. The amazing thing about the Turing Machine is any computer algorithm is capable of being simulated by it. Church proved in 1937 that lambda calculus is Turing complete and would be the foundation of the functional programming languages we see today.

![Alonzo Church](https://theturingcentenary.files.wordpress.com/2012/02/alonzo_church.jpg)

![Lambda Calculus](http://bach.ai/images/the-lambda-calculus-for-absolute-dummies/lambda1.png)

![Turing Machine replica made out of wood](https://cdn8.openculture.com/2018/03/08224424/turing-machine-e1520578134134.png)

The first ever functional programming language was known as LISP. LISP functions were defined utilizing lambda notation. It also included a label construct that would allow recursive functions to work. LISP is also an example of a specified type of functional programming language known as impure functional languages. Haskell would be an example of a pure functional language. The difference between the two is pure functional languages support only the functional paradigms whereas impure support both functional paradigms and imperative style programming.

![LISP](https://1.bp.blogspot.com/-H1jFlpeAtjU/UeJ_nn2QlaI/AAAAAAAAAIk/9vmh_lHJp3g/s1600/lisp.jpg))

![Haskell Logo](https://qualityassignmenthelp.com///wp-content/uploads/2016/11/haskell-logo.jpg)

There are some pretty important concepts to know in regards to functional programming languages. Many of them are foreign and not used in imperative programming languages. Here are the most noticeable concepts.
1. First Class and higher order functions
2. Pure Functions
3. Recursion
4. Strict and Nonstrict Evaluation
5. Type Systems
6. Referential Transparency
7. Data Structures

# First Class and Higher Order Functions
Higher order functions are functions that take functions as arguments or return functions as results. An example related to Calculus would look something like this.

![Higher Order Derivatives](https://www.shelovesmath.com/wp-content/uploads/2013/02/Higher-Order-Derivatives.png)

In addition, higher order functions enable currying, which is a technique that applies functions to its arguments one at a time. Each application would then return a new function that accepts the next argument. An example would look something like 1 is defined to be S(O), and the addition on natural numbers looks like 

    m + O = m
    m + S(n) = S(m + n)

This is a successor function that could compute the addition of two natural numbers. For example, 1 + 2 = 1 + S(1) = S(1 + 1) + S(1 + S(O)) = S(S(1 + 0)) = S(S(1)) = S(2) = 3

First class are similar to higher order functions, but first class is a computer science term for programming language entities that do not have restrictions on their use.

# Pure Functions
Pure functions are functions that have no memory or input/output. They have several useful properties which optimize the code:

1. If the result of a pure function isn't used, then it can be removed without affecting other expressions.
2. Referential Trasparency: The idea that if a pure function is called with arguments that have no memory or I/O, the result is constant with respect to that argument list. 
3. If there is no data dependency between two pure expressions, their order can be reversed. In other words, the evaluation of any pure expression is thread-safe.
4. If the entire language does not allow side-effects, then any evaluation strategy can be used. This allows the compiler to reorder or combine the evaluation of expressions in a program. 

# Recursion


# Strict and Nonstrict Evaluation

# Type Systems

# Referential Trasparency

# Data Structures

References:
[Imperative vs Functional Programming from CPSC 354](https://hackmd.io/@alexhkurz/SJKWvna6U)
[Functional Programming on Wikipedia](https://en.wikipedia.org/wiki/Functional_programming)
[Turing Machine on Wikipedia](https://en.wikipedia.org/wiki/Turing_machine)
[Functional Programming Introduction on Tutorialspoint](https://www.tutorialspoint.com/functional_programming/functional_programming_introduction.htm)
[Successor Function](https://en.wikipedia.org/wiki/Successor_function)
