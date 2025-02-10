\Conditional constructions, constructs of the form If A then B, have been subject to intense study in a wide variety of philosophical areas. One important reason is that such constructs allow one to encode *connections* and *dependencies*, be they causal, epistemic, conceptual, or metaphysical.

We will outline some of the main formal models that have been employed to analyze such constructs, as well as their philosophical motivation.

## Background
---
The conditional construction is a small construction that for decades has attracted massive interest form philosophers, logicians, linguists, computer scientists, and cognitive psychologist.

This huge interest can be traced to two circumstances:

1. The conditional is one of our primary vehicles for talking about, describing, and representing *connections* and *dependencies*, be they causal, conceptual, metaphysical, epistemic, or logico-semantic.
2. The problems one has in accounting for the meaning of the conditional to a large extent overlaps with the problems one has in accounting for the nature of these connections and dependencies.

The study of the conditional is a pathway into a large body of issues with ramifications far beyond the seemingly minor issue of the semantics of a small unassuming construction.

Formal methods have been introduced in order to deal with the problem posed by conditionals, and they have proved to be useful and illuminating in a range of other areas. This are is rife with controversy.

Consider the following conditionals:
1. If $x$ is even and greater than $2$, then $x$ is not prime.
2. If the conditions of the Versaille treaty had not been so severe, there would have been no WW2.
3. If Shakespeare didn't write Hamlet, someone else did.

The first of these can be used to express that *even* and *prime* are conceptually related properties; the second conditional can be used to express there is a causal connection between the conditions set up in the Versaille treaty and the breakout of WW2; the third conditional can be used to express that there is some degree of epistemic independence between one's conviction that *Shakespeare* wrote Hamlet and one's conviction that *someone* wrote Hamlet.

Three conditionals that can be used to express three very different kind of connections and dependencies. Various fundamental semantic questions have been brought up:

Is there at some deeper semantic level only one type of conditional or are there different semantic kinds of conditionals? Compare the difference between an *indicative* conditional and a *subjunctive* conditional.

Does the semantic value of a conditional depend on the (conceptual/epistemic/causal) connections and dependencies it is used to express, or does the conditional express the connections and dependencies that it does through the pragmatics of assertion?

Can conditionals have truth values and, if so, do they always have truth values or do they express 'gappy' propositions?

Is the truth value of a conditional a function of the truth values of its constituent sentences or is the conditional semantically intensional?

Many approach the study of conditionals from another direction. Since conditionals are linguistic vehicles for expressing connections and dependencies, one may ask what kind of connections do they express. Here we investigate more structural phenomena.

One important phenomenon is *defeasibility* (also known as *failure of antecedent strengthening* or *non-monotonicity*). From the fact that one accepts $A \to C$, (where $\to$ is a generic conditional) it does not follow that one thereby should accept $(A \land B) \to C$. For instance, from the fact that one accepts:

4. If the match is struck it will light.

it does not follow that one should accept:

5. If the match is struck and it's submerged in water it will light.

The phenomenon of defeasibility reflects the fact that connections and dependencies often do not hold unconditionally or by necessity; often they depend on things being as they *normally* are, or on contingencies that just happen to be the case, or on other things *being equal* (*ceteris paribus*).

A fundamental problem is that typically it is *impossible* to spell out in full detail how things normally are, what contingencies are necessary and sufficient, or what the "other things" are that are to be considered equal.

The expressive power of conditionals to a large extent derive from the fact that thy implicitly invoke dependencies that are impossible to spell out. Nearly all discourse outside the realm of mathematics deals with such defeasible connections and dependencies, so it's important to understand how conditionals do the magic of depending on what cannot be spelled out.

We make no progress by merely mentioning that a conditional depends on that things are as they normally are or on other things being equal. For from the fact that one accepts:

7. If the match is struck it will, other things being equal, light.

It still does not follow that one should accept:

8. If the match is struck and is submerged in water, other things being equal, light.

The phenomenon of defeasibility is a core feature of the conditional itself, and the development of formal methods for analyzing this phenomenon has been of central interest in the literature on conditionals.

We'll run through some of the main approaches to the analysis of conditionals, outline the formal structures that have made the analyses possible, and briefly indicate their philosophical underpinnings, with a particular eye towards how they account for how conditionals can be used to express connections and dependencies.

The two basic kinds of analyses to be considered are:
1. Those that assign truth conditions to the conditional
2. Those that assign acceptance conditions (using the *Ramsey Test*).

## Conditionals with Truth Values
---
### *Formal Preliminaries*
Assuming a language with atoms $p, q, r, ...$ closed under $\neg, \land, \text{ and } \lor$. The language will be extended with the generic conditional $\to$. Non-atomic sentences will be denoted $A, B, C, ...$

The semantics for this language will be given relative a set $U$ of *states*; these can be thought of as assignments of truth values to the atoms, or as *possible worlds*, or as pairs of possible worlds and moments in time, what is crucial is each state determines the truth values of the atomic sentences.

1. $u \models p$ if and only if $p$ is true at $u$.
2. $u \models \neg A$ if and only if it is not the case that $u \models A$.
3. $u \models A \land B$ if and only if $u \models A$ and $u \models B$.
4. $u \models A \lor B$ if and only if $u \models A$ or $u \models B$

We say a sentence $B$ is a *consequence* of, i.e. $A_1, ..., A_n \models B$, if and only if $u \models B$  whenever $u \models A_1, ..., A_n$.

### *The Material Conditional*
The *material conditional*, written as $A \to B$, is the [[Basic overview of logic|first]] fully analyzed conditional that students of logic encounter. Such an interpretation has the virtue of simplicity (truth-tables are among the simplest of formal structures), furthermore it can be derived from seemingly compelling logical principles; for instance one can show that it is the interpretation that $\to$ must have if it is to be truth-functional and satisfy (given the classical interpretation of negation) the following:

$$\begin{align}A, A \to B &\models B. \text{ (Modus Ponens)}\\ \neg B, A \to B &\models \neg A. \text{ (Modus Tollens)}\\ \text{If }A \models B, &\text{ then } \models A \to B.\end{align}$$

It is clear from the semantics of the material conditional that its truth value does not depend in any interesting way on connections between antecedents and consequents: the material conditional is only sensitive to their truth value.

As a result if we take the indicative conditional of natural language to have the semantics of the material conditional, semantics alone does very little to explain how and when such conditionals are asserted or denied. On the basis of semantics alone, one would predict both of the following conditionals would be generally accepted:

9. If Shakespeare didn't write Hamlet, then his grandmother did.
10. Even if someone other than Shakespeare wrote Hamlet, Shakespeare wrote Hamlet.

If Shakespeare wrote Hamlet then both these conditionals are true, yet those who believe that Shakespeare wrote Hamlet are not in general inclined to accept the conditionals. Indeed most are inclined to *reject* these conditionals. There is a deep mismatch between the truth values of the conditionals and speakers inclinations to use them. Such systematic mismatch is sometimes labeled as 'paradoxes' of the material conditional and can be traced back to various logical properties such as:

$$\begin{align} \neg A &\models A \to B\\ B &\models A \to B \end{align}$$
If the semantics of the material conditional is to have any credibility as a semantics of the conditional in natural language (specifically the indicative conditional) then most of the explanatory work must be relegated to pragmatics. For example, one can hold that the reason why one is not inclined to accept (9) is the same as the reason why one is not inclined to assert

11. Either Shakespeare wrote Hamlet or his grandmother did.

Even though one believes that it's true (since one of the disjuncts is true) it would be misleading and would convey less information than the simple "Shakespeare wrote Hamlet". This strategy was proposed by Grice.

Many have come to the conclusion that the discrepancy between the semantics of the material conditional and the way in which indicate conditionals are used is too great: the semantics lack credibility.

Some have argued that the most blatant collisions between semantics and pragmatics (e.g. cases where one is inclined to reject a conditional that one believes is true) can be avoided by allowing conditionals to have 'gappy' truth conditions:

$$
\begin{array}{|c c|c|}
A & B & A \to B\\ % Use & to separate the columns
\hline 
T & T & T\\
T & F & F\\
F & T & -\\
F & F & -\\
\end{array}$$
The conditional is taken to lack truth value when the antecedent is false. This still leaves much explanatory work to pragmatics but at least does not force pragmatics to explain why true conditionals are rejected.

This account is still viewed with skepticism, mainly regarding the intelligibility of truth-value gaps and how such gaps are to be accommodated in a wider story where conditionals embed in more complex sentences.

### *The Strict Conditional*
An example of a conditional that semantically reflects a stronger connection between the antecedent and the consequent is the *strict* conditional, with the truth-conditions: $$u \models A \to B \text{ if and only if } v \models B \text{ for every state }v \text{ such that } v \models A.$$
The strict conditional is not supposed to reflect any particular construction in natural language, but it is a nice simple example of how a language can contain conditionals that reflect interesting connections between their antecedents and consequents. In this case: the connection of semantic consequence. If the English indicative conditional had these truth conditions then:

12. If you are a bachelor then you are not married

would be true, while

13. If Jim was run over by a truck, he died

would be false (even if Jim was run over by a truck and died).

Notably, as semantic consequence involves the preservation of property, the strict conditional is not defeasible, we still have the property: $$A \to C \models (A \land B) \to C$$
### *Ontic Selection Functions: Counterfactuals*
An explosion of interest in the formal structures used to represent conditionals came with the work of Stalnaker and Lewis. In different ways they introduced the idea of a selection function $\gamma$ that for each state $u$ and each sentence $A$ picks out a sub-set of states in which $A$ is true.

Given such a selection function one can give truth conditions for a conditional as follows: $$u \models A \to B \text{ if and only if } v \models B \text{ for every }v \text{ in }\gamma(u, A)$$
A selection function gives rises to many degrees of freedom both in terms of abstract structural properties and in terms of substantive interpretations. Common examples of structural constraints are: $$\begin{align}&\text{If }v \text{ is in }\gamma(u, A), \text{ then }v \models A.\\
&\text{If }u \models A, \text{ then }\gamma(u, A) \text{ is in the unit set } \{u\}. \text{ (Centering)}\\
&\text{If } v \models B \text{ for each }v \text{ in } \gamma(u, A), \text{ then } \gamma(u, A) = \gamma(u, A \land B).\end{align}$$
In these cases each structural constraint gives rise to a logical property: $$\begin{align}&\models A \to A.\\A, A \to B &\models B.\\
A \to B, A \to C &\models (A \land B) \to C.\end{align}$$
Notably, the semantics allows for *defeasibility*, that is, we do not in general h

ave: $$A \to C \models (A \land B) \to C.$$
For instance, consider the graphical representations in the following image: ![[Pasted image 20240316211130.png]]

of the states in which $A, B, C$ are true and the areas selected by the selection function.

From the picture it's clear that we can have $u \models A \to C$ although we do not have $u \models (A \land B) \to C.$

It's the prospect that selection functions can be used to represent fundamental structures, the kind of structures that underlie the connections we express by natural language conditionals, that has been the main philosophical driving force for investigating selection-function semantics for conditionals.

The most influential interpretation is due to David Lewis who suggested that the selection function $\gamma (u, A)$ selects those $A$-worlds (on his account states are [[Necessity and Possibility|possible worlds]]) that are *most similar* to $u$; that is, the selection function is based on a similarity relation $v \leq_{u} w$ between possible worlds ($v \leq_{u} w$ holds if $v$ is no less similar to $u$ than is $w$).

The similarity relation is standardly taken to be *reflexice, transitive and complete* and to satisfy some proviso, *the limit assumption*, to ensure that in a given set of worlds there is at least one world that is *most similar* to the target world, that is one needs to guarantee that there are no infinitely descending chains of similarity.

Similarity relations between worlds can be though of as providing a substantive interpretation of the *ceteris paribus* intuition in the evaluation of conditionals: a conditional is true if it is the case that if the antecedent were true, and *as much as possible* (this is where the similarity relation kicks in) remained the same, then the consequent would be true.

You may ask:*Similar in what way?* There are various ways of approaching this question. Lewis, who followed a tradition broadly deriving from Hume, took special interest in similarity criteria that would allow for a reductive analysis of causal relations in terms of the similarity relation (and so for a reductive analysis of causal relations in terms of counterfactuals.)

Lewis-style similarity semantics provides a robust and convincing model (even if you're skeptical about underlying metaphysical assumptions) for the analysis of *counterfactual conditionals* a class of conditionals that largely coincides with conditionals in the *subjunctive* mood:

14. If the match had been struck, it would have lit.
15. The Vietnam war would have escalated even if Kennedy had not been murdered

As we typically take the truth values of such conditionals to depend on underlying causal connections, this provides strong support for the idea that similarity relations can be used to encode important aspects of the causal structure of the world.

Accordingly, the Lewis-Stalnaker analysis remains the dominant paradigm in the semantics of counterfactual conditionals, one where the *truth-value* of a conditional is sensitive to underlying causal connections between antecedents and consequents.

Within the more linguistically orientated study of the semantics of conditionals, the dominant tradition is to take conditionals to have an underlying Lewis-Stalnaker-style semantic structure.

For example, Kratzer combines a Lewis-style semantics with a 'restrictor' analysis of conditionals: the antecedent of a conditional is taken to restrict the space of possibilities relative to which the consequent is evaluated. 

## Epistemic Interpretations
---
Epistemic interpretations of conditionals cannot be discussed without mention of Frank Ramsey's famous footnote:

> If two people are arguing 'if $p$ will $q$?' and both are in doubt as to $p$, they are adding $p$ hypothetically to their stock of knowledge and arguing on that basis about $q$. We can say that they are fixing their degrees of belief in $q$ given $p$. If $p$ turns out false, these degrees of belief are rendered void. If either party believes $\neg p$ for certain, the question ceases to mean anything to him except as a question about what follows from certain laws and hypotheses.

Here, Ramsey identifies the main feature of what has become known as the *Ramsey Test*: conditionals are evaluated on the basis of what one would take to hold on the hypothetical assumption that the antecedent is true. 

Epistemic interpretations of conditionals typically do not take the connections expressed by the use of a conditional to reside in its truth-conditions. The epistemic connections expressed by a conditional are features of one's own epistemic state rather than being objective features of the world.

There is wide agreement that the epistemic interpretation provides a good analysis of non-embedded *indicative* conditionals. From the POV of meaning theoretical orthodoxy the problem with the epistemic interpretation is that it doesn't provide truth-conditions for the conditional. 

This creates a problem both in accounting for its logic, as the semantic consequence relation is based on sentences taking a truth value, and in accounting for its interaction with other connectives like negation and disjunction, as those are truth-functional.

Some have sought to combine epistemic interpretations with truth-functional accounts and take the epistemic interpretation to spell out the pragmatics of indicative conditionals, thus maintaining the traditional semantic-pragmatic distinction. Others have taken this to show that the indicative conditional is inherently different from other truth-conditional constructions and has no semantics proper.

### *The Ramsey Test and Logic*
The epistemic interpretation relies on the notion of an epistemic state $\mathcal{E}$ and on a function $*$ that takes a sentence $A$ and returns the epistemic state $\mathcal{E} * A$ that corresponds to the epistemic state in which it is hypothetically assumed that $A$.

Since neither the acceptance conditions of conditions nor their logic are derivable from their truth-conditions, one needs a separate account of acceptance conditions and of *epistemic* consequence. $$\text{ If }\mathcal{E} \Vdash A \to B \text{ if and only if } \mathcal{E} * A \Vdash B$$
The Ramsey Test by itself gives no indication of the acceptance conditions for other kinds of sentences or  of their logic. So let $A_1, ..., A_N \Vdash B$ stand for $B$ is *an epistemic consequence of* $A_1, ..., A_n$. A reasonable minimal requirement is that as long as the sentence are not conditionals we have: $$\textbf{Semantic Closure: } \text{ If } A_1, ..., A_n \models B, \text{ then } A_1, ..., A_n \Vdash B.$$
A further reasonable requirement is: $$\begin{align}&\textbf{Epistemic Closure: } \text{ If }\mathcal{E} \Vdash A_1, ..., \mathcal{E} \Vdash A_n \text{ implies } \mathcal{E} \Vdash B \text{ for every}\\&\text{epistemic state } \mathcal{E}, \text{ then }A_1, ..., A_n \Vdash B.\end{align}$$
If we allow for the converse direction then the epistemic consequence relation can be fully analyzed by acceptance conditions:

$$\begin{align}&\textbf{Reverse Epistemic Closure: } \text{ If }A_1, ..., A_n \Vdash B, \text{ then } \mathcal{E} \Vdash A_1,..., \\&\mathcal{E} \Vdash A_n \text{ implies } \mathcal{E} \Vdash B\end{align}$$

The logical properties of the conditional will to large extent depend on the properties of the $*$-operator. Here are two candidate properties: $$\begin{align}&\textbf{Success: } \mathcal{E} * A \Vdash A.\\&\textbf{Vacuity: }\text{If }\mathcal{E} \Vdash A, \text{ then } \mathcal{E} * A = E.\end{align}$$ 
These give rise to the properties: $$\begin{align}&\Vdash A \to A.\\A, A \to B &\Vdash B.\end{align}$$
Another possible requirement is: $$\textbf{Iteration: }\mathcal{E} * A * B = E * (A \land B)$$
This gives rise to the logical export-import-properties: $$\begin{align}A \to (B \to C) &\Vdash (A \land B) \to C.\\ (A \land B) \to C &\Vdash A \to (B \to C).\end{align}$$
It's typically not assumed that $*$ satisfies *monotonicity*: $$\textbf{Monotonicity: }\text{ If } \mathcal{E} \Vdash B, \text{ then } \mathcal{E} * A \Vdash B.$$
Accordingly, the epistemic conditional can be defeasible: It is not in general the case that $A \to C \Vdash (A \land B) \to C.$ Sometimes weaker properties than monotonicity are assumed, such as: $$\textbf{Preservation: }\text{ If } \mathcal{E} \Vdash B \text{ and } \mathcal{E} \nVdash \neg A, \text{ then }\mathcal{E} * A \Vdash B$$
With preservation and logical closure this entails that as long as one doesn't reject the antecedent of a conditional the acceptance conditions of the epistemic conditional coincides with acceptance conditions of the material conditional.

This is important as the counter-intuitive properties of material implication mainly emerge in cases when the antecedent is believed to be false. The epistemic conditional thus keeps the 'good' parts of the material analysis of the conditional but avoids the problematic parts. For instance, in the absence of the monotonicity requirement we do not have: $$\begin{align}\neg A &\Vdash A \to B\\ B &\Vdash A \to B\end{align}$$
### *Formal Models*
Two main types of formal structures are often used to model epistemic states: 
1. Models that assign *probabilities* to sentences and a broad range of models
2. Models that rank sentences according to their *entrenchment* (*plausibility*, etc.).

Often the latter kind of models use qualitative relations.

[[Probability Overview|Probabilistic]] models follow a [[A User's Guide to Bayes Theorem|Bayesian]] tradition in which epistemic states are taken to be [[Induction and Inductive Logic|probability measures]]. The revision operator $*$ in such a model takes a probability measure $\mathcal{E}_P$ and a sentence $A$ and returns a new probability measure $\mathcal{E}_P * A$ by *conditionalization*: $$(\mathcal{E}_P * A)(B) = \mathcal{E}_p(B \mid A) = \mathcal{E}_p(A \land B)/\mathcal{E}_p(A).$$
In a simple model of probabilistic acceptance one accepts all and only those non-conditional sentences that exceed some threshold $\alpha$ $(.5 \leq \alpha \leq 1),$ so that, when $A$ is not conditional: $$\mathcal{E}_P \Vdash A \text{ if and only if }\mathcal{E}_p(A) > \alpha$$
For the epistemic consequence relation there are different options for example the $p$-consequence relation (the uncertainty of the conclusion cannot be greater than the sum of uncertainty of the premises): $$A_1, ..., A_n \Vdash B \text{ if and only if } (1 - \mathcal{E}_p(B)) \leq (1- \mathcal{E}_P(A_1)) + ... + (1- \mathcal{E}_P(A_n)) \text{ for all }\mathcal{E}_p$$
These jointly ensure that Semantic Closure and Epistemic Closure are satisfied. The model ensures we have a defeasible conditional that satisfies important logical properties like modus ponens and export-import.

As an example of qualitative representation of a epistemic state one can consider an epistemic state to be represented as an epistemic selection function $\mathcal{E}_\gamma$ that for any sentence $B$ that has truth conditions picks out the set $\mathcal{E}_{\gamma}(B)$ of *most plausible* B-states (the B-states are the states in U where B is true)

Here again we have a selection function, but note that while the selection functions in the ontics models were relativized to the states (worlds) themselves, here they are relativized to *epistemic states*, making the evaluation procedure speaker-dependent. The epistemic state that results from making the hypothetical assumption that $A$, $\mathcal{E}_\gamma * A$, can then be defined to be the epistemic selection function that for any sentence $B$ picks out the set of *most plausible* B-states that are also A-states (i.e. the most plausible $A \land B$-states): $$(\mathcal{E}_\gamma * A)(B) = \mathcal{E}_\gamma(A \land B).$$
A non-conditional sentence is accepted if it is true in all the most plausible models, i.e., letting $\top$ be an arbitrary tautology ($\mathcal{E}_\gamma (\top)$ will pick out the most plausible of all states) and $A$ a non-conditional sentence: $$\mathcal{E}_\gamma \Vdash A \text{ if and only if }v \models A, \text{ for all }v \in \mathcal{E}_\gamma (\top).$$
The epistemic consequence relation can be defined as: $$A_1, ..., A_n \Vdash B \text{ if and only if } \mathcal{E}_\gamma \Vdash A_1, ..., \mathcal{E}_\gamma \Vdash A_n \text{ implies } \mathcal{E}_\gamma \Vdash B, \text{ for all } \mathcal{E}_\gamma$$
These jointly ensure that Semantic Closure, Epistemic Closure, and Reverse Epistemic Closure are satisfied. The model also ensures that we have a defeasible conditional that satisfies important logical properties like modus ponens and export-import.

Both kinds of models allow for a rich but by no means exhaustive representation of evidential relations and justificational structures and are able to explain intuitive judgments about indicative conditions quite well.

### *Impossibility Results*
As noted, epistemic interpretations of conditionals often treat them as *exceptional*, particularly, by not assigning truth-conditions to them. However, could it not be the case that conditional has truth-conditions that are such that they just happen to satisfy the Ramsey Test? For instance, couldn't the conditional have truth-conditions that, given the axioms of probability, forced the equality: $$\Pr(A \to B) = \Pr(B \mid A)$$
No, Lewis showed that a language with a conditional that embeds just like other connectives cannot on pain of triviality satisfy this equality. As long as the standard axioms of probability are satisfied, the equality forces the probability of $A$ to be either $0$ or $1$.

So to satisfy the epistemic interpretation the conditional must truly be exceptional. This conclusion is not undermined by the fact that the above equality can be non-trivially satisfied if one allows for *gappy* truth-conditions as gappy truth-conditions are exceptional in their own right and probability measures on gappy propositions will not in general satisfy the standard axioms of probability.

## Concluding Remarks
Over the past century the conditional has been the locus of a rich and diverse range of philosophical debates. Considerable progress has been made in the understanding of how conditionals can be used to express connections and dependencies, as well as in the understanding of their defeasible character.

The progress can be traced back to the careful study of the formal apparatus used to represent the underlying structures.