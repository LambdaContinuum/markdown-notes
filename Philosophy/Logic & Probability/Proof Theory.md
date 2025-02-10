fProof theory began in the 1920s as a part of Hilbert's program, which aimed to secure the foundations of mathematics by modeling infinitary mathematics with formal axiomatic systems and proving those systems consistent using finitary means.

The program viewed mathematics as a system of reasoning with precise linguistic norms, governed by rules that can be described and studied in concrete terms.

## Introduction
---
At the turn of the nineteenth century, mathematics exhibited a style of argumentation that was more explicitly computation than is common today. The introduction abstract algebraic methods helped unify developments in analysis, number theory, geometry, and the theory of equations, and work by mathematicians like Richard Dedekind, Cantor, and Hilbert towards the end of the century introduced set-theoretic language and infinitary methods that served to downplay or suppress computation content.

This shift in emphasis away from calculation gave rise to concerns as to whether such methods were meaningful and appropriate in mathematics. The discovery of paradoxes stemming from naive set theory led to even more pressing concerns as to whether the modern methods were even consistent. This led to heated debates in the early twentieth century and what is sometimes called the "crisis of foundations."

In 1922, Hilbert launched his *Beweistheorie*, or Proof Theory, which aimed to justify the use of modern methods and settle the problem of foundations once and for all. Hilbert argued this could be achieved as follows:

1. Represent portions of the abstract, infinitary mathematical reasoning in question using formal axiomatic systems, which prescribe a fixed formal language and precise rules of inference.
2. View proofs in these systems as finite, combinatorial objects, and prove the consistency of such system, that is, prove the fact that there is no way to derive a contradiction. 

Godel's second incompleteness theorem showed that any "unobjectionable" portion of mathematics is insufficient to establish its own consistency, let alone the consistency of any theory properly extending it. This dealt a blow to Hilbert's program as it was originally formulated, but the more general project of studying mathematical reasoning in syntactic terms, especially with respect to questions of algorithmic or otherwise concrete content, has been fruitful. Moreover, the general strategy of separating syntactic and semantic concerns and of maintaining a syntactic viewpoint where possible has become a powerful tool in formal epistemology.

Today, Proof Theory can be viewed as the general study of formal deductive systems. Given that formal systems can be used to model a wide range of types of inference:

- [[Necessity and Possibility|Modal]]
- Temporal
- [[Probability Overview|Probabilistic]]
- [[Induction and Inductive Logic|Inductive]]
- Defeasible
- [[Deontic Logic|Deontic]]
- and so on

work in this field is diverse. Here we'll focus on the proof theory of *mathematical* reasoning, even with this restriction the field is very broad.

## Natural Deduction and Sequent Calculi
---
Contemporary logic introductions typically present formal calculi for first-order logic with a long list of axioms and a few simple rules, but these are generally not very convenient for modeling deductive arguments or studying their properties. A system which fares better on both counts is given by Gentzen's system of *natural deduction*, which we will now consider.

Natural deduction is based on two fundamental observations:

1. It is natural to describe the meaning, or appropriate use, of a logical connective by giving the conditions under which one can *introduce* it, that is, derive a statement in which that connective occurs, and the methods by which one can *eliminate it*, that is, draw conclusions from statements in which it occurs. For example, one can establish a conjunction $\phi \land \psi$ by establishing both $\phi$ and $\psi$, and conversely, if one assumes $\phi \land \psi$, one can conclude either $\phi$ or $\psi$ at will.
2. It is natural to model logical arguments as taking place under the context of a list of hypotheses, either implicit or explicitly stated. If $\Gamma$ is a finite set of hypotheses and $\phi$ is a first-order formula, the *sequent* $\Gamma \Rightarrow \phi$ is intended to denote that $\phi$ follows from $\Gamma$. For the most part, these hypotheses stay fixed over the course of an argument, but under certain circumstance they can be removed, or *canceled*. For example, one can prove an implication $\phi \to \psi$ by temporarily assuming $\phi$ holds and arguing that $\psi$ follows. The introduction rule for implication reflects the fact that deriving $\psi$ from a set of hypothesis $\Gamma$ together with $\phi$ is the same as deriving $\phi \to \psi$ from $\Gamma$.

Writing $\Gamma, \phi$ as an abbreviation for $\Gamma \cup \{\phi\}$, the rules for natural deduction are: $$
\begin{prooftree}
\AxiomC{}
\UnaryInfC{$\Gamma, \phi \Rightarrow \phi$}
\end{prooftree}
$$$$
\begin{prooftree}
\AxiomC{$\Gamma \Rightarrow \phi$}
\AxiomC{$\Gamma \Rightarrow \psi$}
\BinaryInfC{$\Gamma \Rightarrow \phi \land \psi$}
\end{prooftree}
$$$$
\begin{prooftree}
\AxiomC{$\Gamma \Rightarrow \phi_0 \land \phi_1$}
\UnaryInfC{$\Gamma \Rightarrow \phi_i$}
\end{prooftree}
$$$$\begin{prooftree}
\AxiomC{$\Gamma \Rightarrow \phi_0 \land \phi_1$}
\UnaryInfC{$\Gamma \Rightarrow \phi_i$}
\end{prooftree}$$$$
\begin{prooftree}
\AxiomC{$\Gamma \Rightarrow \phi_i$}
\UnaryInfC{$\Gamma \Rightarrow \phi_0 \lor \phi_1$}
\end{prooftree}$$$$\begin{prooftree}
\AxiomC{$\Gamma \Rightarrow \phi \lor \psi$}
\AxiomC{$\Gamma, \phi \Rightarrow \theta$}
\AxiomC{$\Gamma, \psi \Rightarrow \theta$}
\TrinaryInfC{$\Gamma \Rightarrow \theta$}
\end{prooftree}$$$$\begin{prooftree}
\AxiomC{$\Gamma, \phi \Rightarrow \psi$}
\UnaryInfC{$\Gamma \Rightarrow \phi \to \psi$}
\end{prooftree}$$$$\begin{prooftree}
\AxiomC{$\Gamma\Rightarrow \phi \to \psi$}
\AxiomC{$\Gamma\Rightarrow \phi$}
\BinaryInfC{$\Gamma \Rightarrow \psi$}
\end{prooftree}$$$$\begin{prooftree}
\AxiomC{$\Gamma\Rightarrow \phi$}
\UnaryInfC{$\Gamma \Rightarrow \forall y \phi[y/x]$}
\end{prooftree}$$$$\begin{prooftree}
\AxiomC{$\Gamma\Rightarrow \forall x \phi$}
\UnaryInfC{$\Gamma \Rightarrow \phi[t/x]$}
\end{prooftree}$$$$\begin{prooftree}
\AxiomC{$\Gamma\Rightarrow \phi[t/x]$}
\UnaryInfC{$\Gamma \Rightarrow \exists x \phi$}
\end{prooftree}$$$$\begin{prooftree}
\AxiomC{$\Gamma\Rightarrow \exists y \phi[y/x]$}
\AxiomC{$\Gamma, \phi\Rightarrow \psi$}
\BinaryInfC{$\Gamma \Rightarrow \psi$}
\end{prooftree}$$
The quantifier rules are subject to the usual restrictions. For example, in the introduction rule for the universal quantifier, the variable $x$ cannot be free in any hypothesis. For intuitionistic logic, one also needs the rules *ex falso sequitur quodlibet*, which allows one to conclude $\Gamma \Rightarrow \phi$ from $\Gamma \Rightarrow \bot$, where $\bot$ represents falsity. One can then define negation $\neg \phi$ as $\phi \to \bot$. For classical logic, one adds *reductio ad absurdum*, or proof by contradiction, which allows one to conclude $\Gamma \Rightarrow \phi$ from $\Gamma, \neg \phi \Rightarrow \bot$.

For many purposes, *sequent calculi* provide a more convenient representation of logical derivations. Here, sequents are of the form $\Gamma \Rightarrow \Delta$, where $\Gamma$ and $\Delta$ are finite sets of formulas, with the intended meaning that the conjunction of the hypothesis in $\Gamma$ implies the *disjunction* of the assertions of $\Delta$. The rules are as follows: $$
\begin{prooftree}
\AxiomC{}
\UnaryInfC{$\Gamma, \phi \Rightarrow \Delta, \phi$}
\end{prooftree}$$
$$\begin{prooftree}
\AxiomC{$\Gamma, \phi_i \Rightarrow \Delta$}
\UnaryInfC{$\Gamma, \phi_0 \land \phi_1 \Rightarrow \Delta$}
\end{prooftree}$$
$$\begin{prooftree}
\AxiomC{$\Gamma \Rightarrow \Delta, \phi$}
\AxiomC{$\Gamma \Rightarrow \Delta, \psi$}
\BinaryInfC{$\Gamma \Rightarrow \Delta, \phi \land \psi$}
\end{prooftree}$$
$$\begin{prooftree}
\AxiomC{$\Gamma, \phi \Rightarrow \Delta$}
\AxiomC{$\Gamma, \theta \Rightarrow \Delta$}
\BinaryInfC{$\Gamma, \phi \lor \theta \Rightarrow \Delta$}
\end{prooftree}$$
$$\begin{prooftree}
\AxiomC{$\Gamma \Rightarrow \Delta, \phi_i$}
\UnaryInfC{$\Gamma \Rightarrow \Delta, \phi_0 \lor \phi_1$}
\end{prooftree}$$

and there's more, but I got lazy. The following rule is called the *cut rule*: $$\begin{prooftree}
\AxiomC{$\Gamma \Rightarrow \Delta, \phi$}
\AxiomC{$\Gamma, \phi \Rightarrow \Delta$}
\BinaryInfC{$\Gamma \Rightarrow \Delta$}\end{prooftree}$$
The cut rule is the only rule containing a formula in the hypothesis that my be entirely unrelated to the formulas in the conclusion. Proofs that do not use the cut rule are said to be *cut free*. One obtains a proof system for intuitionistic logic by restricting $\Delta$ to contain at most one formula, and adding an axiomatic version of *ex falso sequitur quodlibet*: $\Gamma, \bot \Rightarrow \phi$.

The cut-elimination theorem is as follows:

> [!box_name] Cut Theorem
> If $\Gamma \Rightarrow \Delta$ is derivable in the sequent calculus with cut, then it's derivable without cut.
> 

Gentzen's proof gives an explicit algorithm for removing cuts from a proof. The algorithm, unfortuntely, can yield an iterated expontential increase in the size of proofs, and one can show that there are cases in which such an increase cannot be avoided.

The advantage of having a cut-free proof is that the formulas in each sequent are built up directly form the formulas in the sequents above it, making it easy to extract useful information. 

For example, the following are two consequences of the cut-elimination theorem, easily proven by induction on cut-free proofs.

1. *Herbrand's theorem*: Recall that a formula of first-order logic is said to be *existential* if it consists of a block of existential quantifiers followed by a quantifier-free formula. Similarly, a formula is said to be *universal* if it consists of a block of universal quantifiers followed by a quantifier-free formula. Herbrand's theorem says that if it's possible to prove an existential statement from some universal hypotheses, then there is an explicit sequence of terms in the language that witness the truth of the conclusion.

>[!box_name] Herbrand's Theorem
>Suppose $\exists \overrightarrow{x} \phi(\overrightarrow{x})$ is derivable in classical first-order logic from a set of hypotheses $\Gamma$, where $\phi$ is quantifier-free and the sentences in $\Gamma$ are universal sentences. Then there are sequences of terms $\overrightarrow{t_1}, \overrightarrow{t_2}, ..., \overrightarrow{t_k}$ such that the disjunction $\phi(\overrightarrow{t_1}) \lor \phi(\overrightarrow{t_2}) \lor ... \lor \phi(\overrightarrow{t_k})$ has a quantifier-free proof from instances of the sentences in $\Gamma$

For intuitionistic logic, one has a stronger property, known as the *explicit definability property*.

>[!box_name] Explicit Definability Property
> Suppose $\exists \overrightarrow{x} \phi(\overrightarrow{x})$ is derivable in intuitionstic first-order logic from a set of hypotheses $\Gamma$ in which neither $\lor$ nor $\exists$ occurs in a strictly positive part. Then there are terms $\overrightarrow{t}$ such that $\phi(\overrightarrow{t})$ is also derivable from $\Gamma$.

Herbrand's theorem provides a sense in which explicit information can be extracted from certain classical proofs, and the explicit definability property provides a sense in which intuitionistic logic is constructive. We have thus already encountered some of the central themes of proof-theoretic analysis:
- Important fragments of mathematical reasoning can be captured by formal systems.
- One can study the properties of these formal systems, for example, describing transformations of formulas and proofs, translations between formulas and proofs in different systems, and canonical normal forms for formulas and proofs.
- The methods provide information about the logic that is independent of the choice of formal system that is used to represent it.

## Methods and Goals
---
### *Classical Foundations*
Recall that Hilbert's program, broadly construed, involves representing mathematical reasoning in formal systems and then studying those formal systems as mathematical objects themselves.

The first step requires finding the right formal systems. It is common today to view mathematical reasoning as consisting of a properly mathematical part that is used in conjunction with more general forms of logical reasoning, though there are still debates as to where to draw the line between the two.

The following list portrays some natural systems of reasoning in increasing logical/mathematical strength:

1. pure [[Predicate Logic|first-order logic]]
2. primitive recursive arithmetic ($PRA$)
3. first-order arithmetic ($PA$)
4. second-order arithmetic ($PA^2$)
5. higher-order arithmetic ($PA^{\omega}$)
6. Zermelo-Fraenkel set theory ($ZF$)

Primitive recursive arithmetic was designed by Hilbert and Bernays to be a patently finitary system of reasoning. The system allows one to define functions on natural numbers using a simple schema of primitive recursion, and prove facts about them using a principle of induction: $$\phi(0) \land \forall x (\phi(x) \to \phi(x + 1)) \to \forall x \phi(x).$$
Here $\phi$ is assumed to be a quantifier-free formula. One can replace this axiom with a suitable induction *rule* whereby primitive recursive arithmetic can be formulated without quantifiers at all.

Surprisingly, via coding of finitary objects as natural numbers, this system is expressive and strong enough to develop most portions of mathematics that involve only finite objects and structures. Peano arithmetic can be viewed as the extension of $PRA$ with induction for all first-order formulas.

There is no effective axiomatization of second or higher order logic that is [[Predicate Logic#^e20f61|complete]] for the standard semantics, where second-order quantifiers are assumed to range over all subsets of the universe of individuals.

As a result, one has to distinguish axiomatic second and higher order logic from the corresponding semantic characterization. Axiomatically, one typically augments first-order logic with comprehension rules that assert that every formula defines a set (or predicate): $$\exists X \forall y(X(y) \iff \phi)$$
Here $\phi$ is a formula in which $X$ does not occur, although $\phi$ is allowed to have other free variables in addition to $y$. One can augment these with suitable choice principles as well. Second-order arithmetic can be viewed as the extension of Peano arithmetic with second-order logic and second-order principles of induction, but one can, alternatively, interpret second-order arithmetic in second-order logic together with an axiom asserting the existence of an infinite domain. Similar considerations hold for higher-order logic as well.

Axioms for set-theory can be found in any intro set theory textbook, these axioms of course can be extended with stronger hypotheses such as large cardinal axioms.

### *Constructive Foundations*
Given the history of Hilbert's program, it should not be surprising that proof theorists have also had a strong interest in formal representations of constructive and intuitionistic reasoning. From an intuitionistic standpoint the use of excluded middle $\phi \lor \neg \phi$ is not acceptable since, generally speaking, one may not know (or have an algorithm to determine) which disjunct holds.

For example, in classical first-order arithmetic, one is allowed to assert $\phi \lor \neg \phi$ for a formula $\phi$ that expresses the twin primes conjecture, even though we don't know which is the case. If one restricts the underlying logic to intuitionistic logic, one obtains *Heytin arithmetic*, which is constructively valid.

Stronger systems tend to be based on what has come to be known as the Curry-Howard-Tait *propositions as types* correspondence. The idea is that, from the constructive perspective, any proposition can be viewed as specifying a type of data, namely, the the type of construction that warrants the claim that the proposition is true.

A proof of the proposition is thus a construction of the corresponding type. For example. a proof of $\phi \land \psi$ is a proof of $\phi$ paired with a proof of $\psi$, and so $\phi \land \psi$ corresponds to the type of data consisting of pairs of type $\phi$ and $\psi$. Similarly, a proof of $\phi \to \psi$ should be a procedure transforming a proof of $\phi$ into a proof of $\psi$, so $\phi \to \psi$ corresponds to a type of functions.

This gives rise to systems of *constructive type theory*, of which the most important examples are *Martin-Löf type theory* and an impredicative variant designed by Coquand and Huet, the *calculus of constructions*. 

Thus, our representative sample of constructive proof systems in increasing strength is as follows:

1. intuitionistic first-order logic
2. primitive recursive arithmetic ($PRA$)
3. Heyting arithmetic ($HA$)
4. Martin-Löf type theory ($ML$)
5. the calculus of inductive constructions ($CIC$)

### *Reverse Mathematics*
In the 1970s, Friedman observed that by restricting the induction and comprehension principles in full axiomatic second-order arithmetic, one obtains theories that are strong enough to represent significant parts of ordinary mathematics but weak enough to be amenable to proof-theoretic analysis.

He then suggested calibrating various mathematical theorems in terms of their axiomatic strength. Whereas in ordinary (meta)mathematics, one proves theorems from axioms, Friedman noted that its often the case that a mathematical theorem can be used in the other direction, namely, to prove an underlying set-existence principle, over a weak base theory. That is, it's often the case that a theorem of mathematics is formally *equivalent* to a set comprehension principle that is used to prove it.

In the years that followed, Friedman, Simpson, and others worked to calibrate the axiomatic assumptions used in a wide range of subjects. They isolated five key theories along the way:

1. $RCA_0$: a weak base theory, conservative over primitive recursive arithmetic, with a *recursive comprehension axiom*, that is, a principle of comprehension for recursive (computable) sets.
2. $WKL_0$: adds *weak König's lemma*, a compactness principle, to $RCA_0$.
3. $ACA_0$: adds the *arithmetic comprehension axiom*, that is, comprehension for arithmetically definable sets.
4. $ATR_0$: adds a principle of *arithmetic transfinite recursion*, which allows one to iterate arithmetic comprehension along countable well-orderings.
5. $\Pi_1^1 - CA_0$: adds the $\Pi_1^1$ *comprehension axiom*, that is, comprehension for $\Pi_1^1$ sets.

### *Comparative Analysis and Reduction*
We have now seen a sampling of the many formal systems that have been designed to formalize various aspects of mathematics. Proof theorists have also invested a good deal of energy in understanding the relationships between the systems. Often results take the form of *conservation theorems* which fit the following pattern, where $T_1$ and $T_2$ are theories and $\Gamma$ is a class of sentences:

> [!box_name] Conservation Theorems
> Suppose $T_1$ proves a sentence $\phi$, where $\phi$ is in $\Gamma$. Then $T_2$ proves it as well (or perhaps a certain translation, $\phi'$)

Such a result, when proved in a suitably restricted base theory, provides a foundational reduction of theory $T_1$ to $T_2$, justifying the principles of $T_1$ relative to $T_2$.

For example: such theorems can be used to reduce:
- an infinitary theory to a finitary one
- a nonconstructive theory to a constructive one
- an impredicative theory to a predicative one
- a nonstandard theory to a standard one

Actual examples:
1. Versions of primitive recursive arithmetic based on classical, intuitionistic, or quantifier-free logic all prove the same $\Pi_2$ theorems (in an appropriate sense).
2. The Gödel-Gentzen double-negation interpretation and variations, like the Friedman-Dragalin A-translation, interpret a number of classical systems in intuitionistic ones, such as $PA$ in $HA$.
3. There are various translations between theories in the language of (first-, second-, or higher-order) arithmetic and subsystems of set theory.
4. Both $I\Sigma_I$, the subsystem of Peano arithmetic in which induction is restricted to $\Sigma_I$ formulas, and $WKL_0$, the subsystem of second-order arithmetic based on Weak König’s Lemma, are conservative over primitive recursive arithmetic for the class of $\Pi_2$ sentences.
5. Cut elimination or an easy model-theoretic argument shows that a restricted second-order version, $ACA_0$, of Peano arithmetic is a conservative extension of Peano arithmetic itself. Similarly, Gödel-Bernays-von Neumann set theory $GBN$, which has both sets and classes, is a conservative extension of Zermelo-Fraenkel set theory. In general, proofs in $ACA_0$ may suffer an iterated exponential increase in length when translated to $PA$, and similarly for $GBN$ and $ZF$, or $I\Sigma_I$ and $PRA$.
6. Theories of nonstandard arithmetic and analysis can be calibrated in terms of the strength of standard theories.
7. The axiom of choice and the continuum hypothesis are conservative extensions of set theory for $\Sigma_1^2$ sentences in the analytic hierarchy.

Such results draw on a variety of methods. Some can be obtained by direct translation of one theory into another. Many are proved using cut-elimination or normalization. The double-negation translation is a remarkably effective tool when it comes to reducing classical theories to constructive ones, and can often be supplemented by realizability, functional interpretation, or other arguments.

Model-theoretic methods can often be used, though they do not provide specific algorithms to carry out the translation. Even forcing methods, originally developed as a set-theoretic technique, can be fruitfully be applied in proof-theoretic settings.

### *Characterizing Logical Strength*
#### Consistency Strength
The results described in the previous section serve to characterize the strength of one axiomatic theory in terms of another. Showing that a theory $T_2$ is conservative over $T_1$ shows that $T_2$ is consist if $T_1$ is. This provides a comparison of the *consistency strength* of the two theories.

#### Ordinal Strength
But there are other ways of characterizing the strength of a theory. For example, the notion of *ordinal* generalizes the notion of a counting number. Starting the natural numbers, we can add an infinite "number" $\omega$ and keep going: $$0, 1, 2, 3, ..., \omega, \omega + 1, \omega+2, \omega + 3, ...$$
We can then proceed to add even more exotic numbers like $\omega \cdot 2$, $\omega^2$, and $\omega^\omega$. The ordering on these particular expressions is computable, in the sense that one can write a computer program to compare any two of them.

What makes them ordinals is that they satisfy a principle of *transfinite induction*, which generalizes the principle of induction on the natural numbers. Ordinal analysis gauges the strength of a theory in terms of such computable ordinals: the stronger a theory is, the more powerful the principles of transfinite induction it can prove.

#### Computational Strength
Alternatively, we can focus on a theory's *computational strength*. Suppose a theory $T$ proves a statement of the form $\forall x \exists y R(x, y)$, where $x$ and $y$ range over the natural numbers, and $R$ is a computationally decidable predicate. This tells us that a computer program that, on input $x$, systematically searches for a $y$ satisfying $R(x, y)$, always succeeds in finding one. 

Now suppose $f$ is a function that, on input $x$, returns a value that is easily computed from the least $y$ satisfying $R(x, y)$. Then $f$ is a computable function, and we can say that the theory, $T$, proves that $f$ is totally defined on the natural numbers. A simple diagonalization shows that no effectively axiomatized theory can prove the totality of every computable functions in this way, so this suggests using the set of computable functions that the theory can prove to be a total as a measure of strength.

#### Examples
A number of theories have been analyzed in these terms. For example, by the results in the last sections, the provably total computable functions of $PRA, I\Sigma_I, RCA_0, \text{ and } WKL_0$ are all the primitive recursive functions.

In contrast, one can characterize the provably total computable functions of $PA$ and $HA$ in terms of higher-type primitive recursions, or using principles of primitive recursion along an ordinal known as $\epsilon_0$. Weaker theories of arithmetic can be used to characterize complexity classes like the polynomial time computable functions.

## Applications
---
We'll describe some of the ways that proof theory interacts with other disciplines. We'll only consider applications of the traditional meta-mathematical branch of proof theory.

### *Proof Mining*
Traditional proof-theoretic methods have been applied to the process or extracting useful information from ordinary mathematical proofs. The reductive results of the 20th century showed, in principle, that many classical proofs can be interpreted in constructive terms. These ideas have been extended and adapted to the analysis of ordinary mathematical proofs. This process used to be dubbed "unwinding proofs" and has more recently adopted the name "proof mining".

Substantial work is needed to turn this vague idea into something practicable. Ordinary mathematical proofs are not presented in formal systems, so there are choices to be made in the formal modeling. In addition, the general meta-mathematical tools have to be tailored and adjusted to yield the information that is sought in particular domains.

The field has already had a number of successes in fields like functional analysis and ergodic theory.

### *Combinatorial Independences*
Another domain where syntactic foundational perspective is important is in the search for natural combinatorial independences, that is, natural finitary combinatorial principles that are independent of conventional mathematical methods.

The Paris-Harrington statement is an early example of such a principle. Since then, Harvey Friedman, in particular, has long sought to find exotic combinatorial behavior in familiar mathematical settings. Such work gives us glimpses into what goes on just beyond ordinary patterns of mathematical reasoning, and yields interesting mathematics as well.

### *Constructive Mathematics and Type Theory*
Proof theory is often linked with constructive mathematics for historical reasons. After all, Hilbert’s program was initially an attempt to justify mathematics with respect to methods that are finitary, which is to say, syntactic, algorithmic, and impeccably constructive. Contemporary work in constructive mathematics and type theory draws on the following facts:
- Logical constructions can often be interpreted as programming principles.
- Conversely, programming principles can be interpreted as logical constructions.
- One can thereby design (constructive) proof systems that combine aspects of both programming and proving.

### *Automated Reasoning and Formal Verification*
Proof-theoretic methods are of central importance in the field of automated reasoning and formal verification. In computer science, researchers use formal methods to help verify that hardware and software are bug-free and conform to their specifications. 

Moreover, recent developments have shown that computational formal methods can be used to help verify the correctness of complex mathematical proofs as well. Both efforts have led to interactive approaches, whereby a user works with a computational proof assistant to construct a formal proof of the relevant claims. 

They have also led to more automated approaches, where software is supposed to carry out the task with little user input. In both cases, proof-theoretic methods are invaluable, for designing the relevant logical calculi, for isolating features of proofs that enable one to cut down the search space and traverse it effectively, and for replacing proof search with calculation wherever possible.

### *Proof Complexity*
The field of proof complexity combined methods and insights from proof theory and computational complexity. For example, the complexity class $\text{NP}$ can be viewed as the class of problems for which an affirmative answer has a polynomial-size proof in a suitable calculus. Thus the conjecture that $\text{NP}$ is not equal to $\text{co-NP}$ is equivalent to saying that in general there is no propositional calculus that has efficient proofs of every tautology.

Cook has suggested that one way of building up to the problem is to show that *particular* proof systems are not efficient, by establishing explicit lower bounds. Such information is also of interest in automated reasoning.