## Gottlob Frege - Origins of the Modern Enterprise
---
### *Foundations of Philosophical Semantics*
It wasn't until the late nineteenth century that philosophy of language emerged as a systematic and self-conscious area of study. For publications by Frege marked this emergence. Two of these, Begriffsschrift (Concept-Script) (1879) and Grundgesetze der Arithmetik (The Basic Laws of Arithmetic) (1893/1903), focused on logic and the foundations of math. Their aims were:
1. To set out a formalized language and [[Proof Theory|proof procedure]] sufficient for mathematics
2. To derive arithmetic from the axioms of this system, and thereby provide a logical basis for all of mathematics.

The degree to which Frege achieved (2) is a matter of debate, the degree to which he achieved (1) is not. His systems were the starting point for the development of mathematical logic and for the use of logical ideas and techniques in the study of natural language.

Two other classics, "Function and Concept" (1891) and "On Sense and Reference" (1892a), made contributions to both. 

In the former, Frege uses the key notion of a function to develop the [[Predicate Logic|semantics of his logical language]].  He beings by refining the prevailing mathematical conceptions, clearly distinguishing functions from the expressions that designate them. He then extends the notion to include functions designated by predicate expressions, functions designated by truth-function connectives, and functions designated by the quantifiers for all x and for some x. In the end we're given a calculus with a mechanical procedure for proving formulas and a set of concepts interpreting them. With this, Frege laid the groundwork for the systematic study of the relations between syntax and semantics, form and meaning, and proof and truth.

In the latter, Frege extends his approach in two ways:
1. Meaning and Reference are distinguished, with composition principles determining the meanings and referents of sentences and other compound expressions from the meanings and referents of their part.
2. The idea of logical semantics are applied to natural language. The resulting picture is one in which the central feature of language is how it represents the world. For a declarative sentence $S$ to be meaningful is for it to represent the world as being a certain way, which is to impose conditions the world must satisfy, if $S$ is to be true. Since $S$ is true iff the world is the way $S$ represents it to be, these are the truth conditions of $S$. Thus, the systematic study of meaning requires the specification of the truth conditions of sentences on the basis of their syntactic structure, and the representational contents of their parts.

### *Frege's Distinction between Sense and Reference*
Sentences represent the world because they are made up of words and phrases that stand for objects, events, concepts, and properties. Since meaning is representational, it may seem that what these expressions stand for (refer to) is what they mean. This view leads to a problem, known as "Frege's puzzle". The puzzle involves explaining why substitution of coreferential terms in a sentence sometimes changes meaning. Consider the following:

1. The author of *Life on the Mississippi* was the author of *The Adventures of Tom Sawyer*.
2. The author of *Life on the Mississippi* was the author of *Life on the Mississippi*.
3. Mark Twain was the author of *Life on the Mississippi*.
4. Mark Twain was Mark Twain.
5. Samuel Clemens was Mark Twain.
6. Samuel Clemens was Samuel Clemens.

These sentences all seem to mean different things, even though they differ only in the substitution of coreferential terms. His contention is supported by three facts:

1. One can understand both sentences, and so know what they mean, without taking them to mean the same thing (or agree in truth value).
2. One who assertively utters 1, 3, or 5 would typically be deemed to say or convey more than one who 2, 4, or 6.
3. One would standardly use the sentences in ascriptions <A believes that S\> to report what one took to be different beliefs.

If this is sufficient for the sentences to differ in meaning, then T1, T2, and T3 cannot jointly be maintained.

- T1: The meaning of a genuine referring expression (singular term) is its referent.
- T2: Both singular definite descriptions, i.e., expressions of the form *the F*, and ordinary proper names are genuine referring expressions.
- T3: The meaning of a sentence $S$ is a function of its grammatical structure plus the meaning of its parts; thus, substitution of expressions with the same meaning doesn't change the meaning of $S$.

Frege rejects T1. For him, the meaning of a name is not its bearer and the meaning of a definite description is not what it denotes. Instead, meaning determines reference. The meaning, or sense, of 'the largest city in California' is something like the property of being a California city larger than all others. Its referent is whatever has this property, Los Angeles.

Different terms with the same sense must have the same referent, terms with the same referents may have different senses, which explains the meaning differences between sentences 1-6.

Like descriptions, ordinary proper names have senses that determine, but are distinct from, their referents. In the case of names, it is common for different speakers to use the same name to refer to the same thing, even though they associate it with different senses.

Frege's example (5 and 6) suggests that he regards the sense of a name n, as used by a speaker s at a time t, to be a condition or property associated with n by s at t, which could in principle, be expressed by a description. On this view, n (as used by s at t) refers to o iff o is the unique object that has the property associated with n by s. When there is no such object, n is meaningful, but refers to nothing.

### *The Compositionality of Sense and Reference*
In addition to T3 and T4, Frege also accepts T4 and T5, including its corollaries, T5a and T5b.

- T4: The reference of a compound term $E$ is a function of its grammatical structure, plus the referents of its parts. Substitution of one coreferential term for another in $E$ doesn't change the referent of $E$. If one term in $E$ fails to refer, then $E$ does too.
- T5: The truth or falsity of a sentence is a function of its structure, plus the referents of its parts.
- T5a: Substitution of one coreferential term for another doesn't change the truth value of a sentence.
- T5b: If one term in a sentence $S$ fails to refer, $S$ lacks a truth value.

For Frege, predicates designate concepts, which he takes to be functions that assign the values truth and false to objects. Quantifiers are higher-order predicates that designate functions that assign truth values to the functions designated by ordinary predicates (and formulas generally).

The truth value of a sentence $S$ consisting of a predicate $P$ plus a singular term $t$ is the truth value assigned to the referent of $t$ by the function to which $P$ refers. When $t$ fails to refer, there is no argument, so $S$ has no truth value. This analysis generalized to many-place predicates and truth-functional connectives. In all such cases, reference failures in one argument place results in the whole sentence being truth valueless.

This entails the following claims are neither true nor false:

7. Either there is no king of France, or *the king of France* is in hiding.
8. There is a king of France, and *the king of France* is in hiding.

Frege regarded it to be a defect of natural languages that they contain non-denoting singular terms. Such terms complicate formal proof procedures of the kind that interested Frege. Still, no descriptive analysis of natural language can be correct if it claims 7 and 8 are truth valueless. Thus his semantic analysis must be modified if it is to be applied to English.

Noticing that the truth values of a sentence typically depends on the referents of its parts, Frege subsumed T5 under T4 by holding that sentences refer to truth values. On this picture, the referent (truth-value) of a sentence is determined by the referents of its parts, while its meaning (the thought it expresses) is composed of the meaning of its parts.

Being a platonic realist about senses, Frege accepted the commonplace observations that there is such a thing as *the* meaning of "is German", and that different speakers who understand this predicate know that it had meaning. For him, senses, including the thoughts expressed by sentences, are public objects available to different thinkers.

For example, there is one thought, *that the square of the hypotenuse of a right triangle is equal to the sum of the squares of the remaining sides*, that is believed by all who believe the Pythagorean theorem. It is this that is preserved in translation, and this that is believed or asserted by agents who sincerely accept a sentence synonymous with the one just used to state the theorem. For Frege, thoughts and their constituents are abstract objects imperceptible to the senses but graspable by the intellect. It is only in relation to these things that our use of language is to be understood.

### *Frege's Hierarchy of Indirect Senses and Referents*
Frege recognized that, given T4, he had to qualify the view that sentences refer to truth values. While applying to many occurrences, it doesn't apply to the occurrences of sentences in attitude ascriptions <A asserted/believed/... that S\>. Suppose that (9) is true, and so refers to truth.

9. John believes that $2 + 3 = 5$

Since '$2 + 3 = 5$' is true, substituting any other true sentence for it ought by T4 give us another true statement, 10, of what John believes.

10. John believes that Frege was German.

but this is obviously absurd. An agent believe one truth without believing every truth. Thus, if the truth values of attitude ascriptions are functions of their grammatical structure, plus the referents of their parts, then the complement clause of such ascriptions must refer to something other than the truth values of sentences occurring there.

Frege's solution to this problem is illustrated by (11) in which the putative object of belief in indicated by the italicized noun phrase.

11. John believes *the claim expressed at the top of page 76*.

Since the phrase is not a sentence, its sense is not a thought. Thus, what is said to believed in (10) must be its referent, rather than its sense. This result is generalized in T6.

- T6: The thing said to be believed in attitude ascription <A believes E\> or similar indirect discourse report is what the occurrence of E in the ascription refers to.

