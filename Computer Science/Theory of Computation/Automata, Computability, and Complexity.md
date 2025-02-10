There are three traditionally central areas of the theory of computation: automata, computability, and complexity. They're linked by the question:

*What are the fundamental capabilities and limitations of computers?*

In each of these three areas this question is interpreted differently, and answers vary according to the interpretation.

# Complexity Theory
---
Computer problems come in different varsities; some are easy, and some are hard. sorting a list of numbers in ascending order is easy, even a small computer can sort a million numbers rather quickly. Compare that to a scheduling problem. Finding some schedule of classes for the entire university to satisfy some reasonable constraints is a much harder problem. If you have a thousand classes, finding the best schedule may require centuries. So it's reasonable to ask

*What makes some problems computationally hard and others easy?*

This is the central question of complexity theory. In one important achievement of complexity theory thus far, researchers have discovered an elegant scheme for classifying problems according to their computational difficulty. It's analogous to the periodic table for classifying elements according to their chemical properties.

You have several options when you confront a problem that appears computationally hard.
1. By understanding which aspect of the problem is at the root of the difficulty, you may be able to alter it so that the problem is more easily solvable.
2. You may be able to settle for less than a perfect solution to the problem. In some cases finding solutions that only approximate the perfect one is relatively easy.
3. Some problems are hard only in the worst case situation, but easy most of the time. Depending on the application, you may be satisfied with a procedure that is occasionally slow but usually runs quickly.
4. You may consider alternative types of computation, such as randomized computation, that can speed up certain tasks.

One applied area that has been affected directly by complexity theory is cryptography. In most fields, an easy computational problem is preferable to a hard one because easy ones are cheaper to solve. Cryptography is unusual because it specifically requires computational problems that are hard, rather than easy. Secret codes *should* be hard to break without the secret key or password. Complexity theory has pointed cryptographers in the direction of computationally hard problems around which they've designed revolutionary new codes.

# Computability Theory
---
During the first half of the twentieth century, mathematicians such as Kurt Godel, Alan Turing, and Alonzo Church discovered that certain basic problems cannot be solved by computers. One example of this phenomenon is the problem of determining whether a mathematical statement is true or false.

Among the consequences of this result was the development of ideas concerning theoretical models of computers that would help lead to the construction of actual computers.

The theories of computability and complexity are closely related. In complexity theory the objective is to classify problems as easy ones and hard ones; whereas in computability theory, the classification of problems is by those that are solvable and those that are not. Computability theory introduces several of the concepts used in complexity theory.

# Automata Theory
---
Automata theory deals with the definitions and properties of mathematical models of computation. These models play a role in several applied areas of computer science. One model, called the *[[Regular Languages|finite automaton]]*, is used in text processing, compilers, and hardware design. Another model, called the *context-free grammar*, is used in programming languages and artificial intelligence.

Automata theory is an excellent place to being the study of the theory of computation. The theories of computability and complexity require a precise definition of a *computer*. Automata theory allows practice iwth formal definitions of computation.