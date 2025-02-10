Basic introduction to modal logic. This includes:
- Possible world semantics
- Axiom systems
- Quantification

Ideas and formal machinery are discussed, but proofs are omitted.

## Introduction
---
Modal operators qualify truth in some way: necessary truth, knowable truth, provable truth, eventual truth, and so on. All of these have many formal properties in common.

One can abstract these properties and study them for their own sake. The idea in all cases is that abstraction should provide us with a simple setting in which the formal manipulation of symbols according to precise rules will lead us to results that can be applied back to the complex 'real' world in which the problems arose.

If modal operators are many, what then formally constitutes a modal operator? A good working definition is, a modal operator is one we can investigate using tools that have been developed for this purpose. Here, we consider the core of the subject *normal modal logics*.

Modal operators come in dual pairs. Dual to necessity is possibility: $X$ is possibly true if it is not necessary that not-$X$ is true, and $X$ is necessarily true if it is not possible that not-$X$ is true. Similarly knowability and consistency are duals, and so on. Following customs we will use $\Box$ for any necessity-like modal operator $\Diamond$ for its dual.

Propositional formulas are built up from propositions letters using propositional connectives, just as in classical propositional logic, together with a rule of formation saying:

- If $X$ is a formula, so is $\Box X$
- If $X$ is a formula, so is $\Diamond X$

What tools are available for formal modal investigation? Historically, axiom systems came first in modern times, with natural deduction systems, tableau systems, and such following. Algebraic generalizations of truth tables came along in the 1940s. But ever since *possible world semantics* was developed in the 1960s, it's been the common starting point.

## Possible World Semantics
---
What are possible worlds? Don't ask. This is generally a misleading question. One doesn't need to know what truth is in order to use truth tables, one just needs to know how it behaves with respect to the logical connectives.

Likewise, one doesn't need to know what constitutes domains of classical first-order models. It's whatever you like. You specify the intended application. The logical truths of first-order logic are those that hold no matter what domain.

Possible worlds are like that. You can specify what possible worlds are, according to their intended application, and the logical truths of modal logics are those that hold no matter what your specification might have been.

Besides possible worlds there is one more essential piece of machinery: an *accessibility relation*. For a particular application it may easily be that not all possibles worlds are equally possible under all circumstances. For example, suppose the modal operator we have in mind is *from now on*. Then in evaluating the truth of a formula today, we must take tomorrow into account, but we can ignore yesterday, tomorrow is accessible from today, but yesterday is not. If the modal operator is *has always been* the situation is reversed.

>[!box_name] Definition 2.1
>A *frame* is a pair $\langle \mathcal{G}, \mathcal{R} \rangle$ in which $\mathcal{G}$ is a non-empty set and $\mathcal{R}$ is a binary relation on $\mathcal{G}$.

When working with a frame, $\langle \mathcal{G}, \mathcal{R}\rangle$ the members of $\mathcal{G}$ are called *possible worlds* or *states*, and for $x, y \in \mathcal{G}$, if $x\mathcal{R}y$ one says that $y$ *is accessible from* $x$. For the time being we'll put no constraints on $\mathcal{R}$.

>[!box_name] Definition 2.2
>A *model* is a triple, $\mathcal{M} = \langle \mathcal{G}, \mathcal{R}, \mathcal{V}\rangle$ where $\langle \mathcal{G}, \mathcal{R}\rangle$ is a frame and $\mathcal{V}$ assigns a truth value to each propositional letter at each possible world (a *valuation*). That is, if $P$ is a propositional letter and $w \in \mathcal{G}$ then $\mathcal{V}(P, w) \in \{true, false\}$. We say the model $\langle \mathcal{G}, \mathcal{R}, \mathcal{V} \rangle$ is *based* on the frame $\langle \mathcal{G}, \mathcal{R} \rangle$.

Given a model, truth values for complex formulas are calculated, world by world, according to a certain set of rules. Here are the evaluation rules stated precisely. Assume $\mathcal{M} = \langle \mathcal{G}, \mathcal{R}, \mathcal{V} \rangle$ is a model, we write $\mathcal{M}, w \Vdash X$ to indicate that formula $X$ is true at possible world $w$ of model $\mathcal{M}$ and $\mathcal{M}, w \nVdash X$ to indicate that it is not. $$\begin{align}\mathcal{M}, w \Vdash P &\iff \mathcal{V}(P,w)= true,\text{for } P \text{ a propositional letter}\\
\mathcal{M}, w \Vdash X \to Y &\iff \mathcal{M}, w \nVdash X \text{ or } \mathcal{M}, w \Vdash Y\\
\mathcal{M}, w \Vdash \Box X &\iff \mathcal{M}, z \Vdash X \text{ for every }z \in  \mathcal{G} \text{ with }w\mathcal{R}z\\
\mathcal{M}, w \Vdash \Diamond X &\iff \mathcal{M}, z \Vdash X \text{ for some }z \in  \mathcal{G} \text{ with }w\mathcal{R}z
\end{align}$$
Call a formula K-valid if it evaluates to *true* at every possible world of every model., The 'K' refers to Kripke, since this is the logic that is given by all possible world models (Kripke models) without any special conditions or restrictions. Typical examples of validities of K are: $$\begin{align}\Box(A \land B) &\iff \Box A \land \Box B\\
\Diamond(A \lor B) &\iff \Diamond A \lor \Diamond B\\
\Box A \land \Diamond B &\Longrightarrow \Diamond(A \land B) \end{align}$$
## Axiomatics
---
**Basic Axiom Schemes:**
- All classical tautologies
- $\Box(X \to Y) \to (\Box X \to \Box Y)$
- $\Diamond X \equiv \neg \Box \neg X$

**Rules of Inference:**
- $X, X \to Y \therefore Y$
- $X \therefore \Box X$

An axiomatic proof is a finite sequences of formulas each of which is an instance of an axiom scheme or follows from earlier lines by one of the rules of inference. A proof proves its last line. Call the axiom system above K. it can be shown that formulas provable in K are exactly the formulas that are K-valid, as defined semantically.

The modal logics given by constraints on the accessibility relation can be axiomatized by adding schemes to the system for K. See the following:

| Validity | Axiom Schemes                                                 |
| -------- | ------------------------------------------------------------- |
| D        | $\Box X \to \Diamond X$                                       |
| T        | $\Box X \to X$                                                |
| K4       | $\Box X \to \Box \Box X$                                      |
| S4       | $\Box X \to X, \Box X \to \Box \Box X$                        |
| KD       | $X \to \Box \Diamond X$                                       |
| S5       | $\Box X \to X, \Box X \to \Box \Box X, X \to \Box \Diamond X$ |
In addition to axiom systems many modal logics have natural deduction systems, tableau proof systems, and Gentzen sequent calculi. However, there are many modal logics that have axiom systems but not known proof systems of these other kinds.

## Quantification
---
In classical logic, quantification is relatively straightforward. The language is enhanced by adding individual variables and relation symbols. Quantifiers, $\forall$ and $\exists$ are also added, along with relatively uncomplicated rules of formation.

Classical models are introduced consisting of a non-empty domain and an interpretation of relation symbols by relations on that domain. Then machinery is introduced that have the effect of making a universally quantified formula true if every value from the domain makes the formula being quantified true, and an existentially quantified formula true if some value from the domain does so.

Modally things are not as simple. If one understands quantification from an *actualist* point of view, quantifiers range over what actually exists, while from a *possibilist* point of view quantifiers range over what might exist. (Corresponding temporal versions are *presentist* and *eternalist*.) These differing conceptions can be represented using possible world models in a rather directed way.

Non-empty domains are involved, and relation symbols are interpreted by relations on the domain, but the interpretation might vary from possible world to possible world:

- For an actualist quantification semantics, we associate with each possible world of a model a non-empty domain, where different worlds can have different domains. These might be disjoint, overlap, or have some other more complex relationship. When evaluating a quantified formula at a possible world, the quantifier is understood to range over the things in the domain of that world only.
- For a possibilist quantification semantics, we can think of these separate domains as being combined into one single set, with quantifiers ranging over it no matter what possible world the truth of a quantified statement is being evaluated at.

Possibilist semantics validate: $\forall x \Box A(x) \equiv \Box \forall x A(x)$ while actualist semantics does not.

The different semantic versions are commonly referred to as *constant domain* (possibilist) and *varying domain* (actualist). It is not the case that one is right and the other is wrong, but rather each represents a distinct notion of what quantification in a model setting is about. In a sense, modal machinery does not dictate, but rather it tells you the consequences of a choice which is made for reasons of philosophical position, taste, or just convenience.

One can have a formal language with both actualist and possibilist quantifiers, and investigate interactions between the two of them and modal operators. Alternatively, one could introduce an *existence predicate*, say $E(x)$. Then one could work with underlying possibilist semantics, think of the things that $E$ is true of at a possible world as the actual existents there, and understand actualist quantification as possibilist quantification relativized to $E$. The machinery is versatile.

A treatment of equality can be added to the formal machinery. This is closely related to what one imagines the "things" in the quantifier domain to be. Suppose we understand domains to consist of objects in some concrete sense, chairs, tables, beer, mugs. Objects do not, so to speak, split apart, so we would want the validity of $(x = y) \to \Box (x = y).$ Likewise, neither do they combine so we would also want the validity of $\neg(x = y) \to \Box \neg (x = y)$. It is rather straightforward to achieve this.

Otherwise, we can think of things more intensionally. Are 'the tallest towers in Paris' and 'the tallest structure built by Eiffel' equal or not? They are in the actual world, but one could certainly create alternative possible words in which they are different, or even in which one but not the other is non-existent. These are [[Naming and Necessity#^58edcf|non-rigid designators]] and their behavior is more complex then that of the objects mentioned earlier. It's possible to introduce quantification over such things too, but it requires more care and nuance.

The quantificational semantics described so far descends directly from the work of Saul Kripke. There is an alternative version due to David Lewis. According to Lewis things cannot exist in the domains of more than one possible world, but they can have *counterparts* in other worlds. Indeed, something existing in one world can have one, many, or no counterparts in an alternative world. Formally, models consist of possible worlds, an alternativeness relation, and a counterpart relation relating quantifier domains.

Roughly speaking, something has a property necessarily at a world if at all alternative worlds, all its counterparts have the property. This is an extremely flexible semantics, with relationships to the Kripke-style version.