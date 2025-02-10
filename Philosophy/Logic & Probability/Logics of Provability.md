# Introduction
---
Provability logics are modal logics meant to capture the formal principles of various provability operators (which apply to sentences) or predicates (which apply to sentence names).

The first candidate for a provability logic was the modal logic S4, which contains as axioms all substitutions ofclassical tautologies, all substitutions of the sch2emata:
$$\text{(K) }\Box(\varphi \to \psi) \to (\Box\varphi \to \Box\psi)$$
$$\text{(M) }\Box\varphi \to \varphi$$
$$\text{(K4) }\Box\varphi \to \Box\Box\varphi$$
and is closed under two rules of inference: *modus ponens* (from $\vdash \varphi$ and $\vdash \varphi \to \psi$ infer $\vdash \psi$), and *necessitation*: if $\vdash \varphi$ then $\vdash \Box\varphi$.

The principles of S4 seem sensible when $\Box \varphi$ is read as 'it is provable that $\varphi$: if an implication and its antecedent are provable, then so is its consequent. Whatever is provable should be true, and if something is provable, we can prove that it is.

This system was used by Godel to interpret intuitionistic propositional calculus. In the end, S4 turned out inadequate as a tool for modelling the behavior of formal provability predicate within axiomatic arithmetic, mostly due to the fact that (M), also (in the context of provability logics) called *local reflection*, while intuitively plausible, cannot be provable in a consistent sufficiently strong axiomatic arithmetic for the formal provability predicate of the arithmetic. Let's elaborate

Let's focus our attention on the standard first-order axiomatic arithmetic called *Peano Arithmetic* (PA). With this system in the background, instead of talking about an arithmetical formula $\varphi$, we can use a coding to represent it by some natural number, denoted $\ulcorner \varphi \urcorner$.  Once we've done this, there's a standard way to construct an arithmetical formula $\text{Prov}_{\textbf{PA}}(x)$ true exactly about the codes of those formulas, which are provable in the PA. This is the formal provability predicate of PA.

A crucial property of this predicate is stated by Lob's theorem. According to which, for any arithmetical $\varphi$, if $\textbf{PA} \vdash \text{Prov}_{\textbf{PA}}(\ulcorner \varphi \urcorner) \to \varphi$ , then already $\textbf{PA} \vdash \varphi$. This means local reflection can hold only for those sentences which are already theorems of PA, and not universally for all sentences of arithmetic, and so S4 cannot be the logic of formal provability predicate.

Another modal logic is the provability logic of formal arithmetical provability, it's the Godel-Lob logic GL. Its axioms are all the substitutions of classical tautologies, all the substitutions of (K), all the substitutions of: $$\text{(Lob) }\Box(\Box\varphi \to \varphi) \to \Box\varphi$$
and the rules of *modus ponens* and *necessitation*. Various modal logics similar to GL have been developed for various notions of provability related to the standard formal provability.

In the language of GL we can express claims such as 'p is provable', but we cannot express things such as 't is a proof of p', that is we cannot express explicit provability statements. The latter task can be achieved in the so-called Logic of Proofs (LP). LP's language is much richer, it contains terms for proofs, ways of constructing complex terms for proofs, and a predicate '_ is a proof of \_'. LP is an adequate logic of explicit provability, but various extensions have been developed.

Somewhat independently of the research on the logic of the formal provability predicate, attempts have been made to develop a formal logic of informal mathematical provability, for which (M) holds. The challenge is to develop a sensible system which can be mixed with other parts of mathematics without running into inconsistency due to Lob or related reasons.

# The Beginnings
---
## Modal Logic S4
The modal logic that will be of particular interest here is S4, which is obtained from K by adding as axioms all instances of the following schemata:$$\text{(M) }\Box\varphi \to \varphi$$ $$\text{(4) }\Box\varphi \to \Box\Box\varphi$$
S4 is sound and complete with respect to frames in which the accessibility relation is reflexive and transitive.

Modal connectives of various modal systems admit various interpretations. $\Box$ can be interpreted as logical necessity, metaphysical necessity, physical necessity, moral obligation, knowledge, etc. Different modal systems capture different principles essential to these various notions. We'll read $\Box \varphi$ as 'it is provable that $\varphi$'.

Prima facie, S4 seems like a decent candidate for the modal logic that adequately captures the formal principles that hold on this reading.

(K) holds because the consequent of a provable implication whose antecedent is provable is also provable. (M) holds because whatever is provable is true. (4) holds because if $\varphi$ is provable, then by producing a proof of $\varphi$, you are proving that it is provable. This isn't enough.

1. We still don't know if there aren't any principles that hold for provability but are not provable in S4.
2. We need a more precise explication of the notion of provability involved.
3. We have to check if all principles of S4 hold with respect to the explication.

## Intuitionism and S4
S4 was first proposed as a logic of provability in the context of Brouwer's intuitionistic logic, which, roughly speaking, results from replacing the notion of truth with that of constructive provability. This intuitionistic logic was formalized by Heyting as Intuitionistic Propositional Calculus (IPC).

On the intuitionistic approach, a mathematical claim is true just in case it has a proof, and false just in case there is a proof that it leads to contradiction.

This idea inspired Heyting  and Kolmogorov to introduce the so-called *Brouver-Heyting-Kolmogorov* (BHK) semantics which identifies truth with provability, falsehood with refutability, and further specifies:

A proof of $\varphi \land \psi$ consists of a proof of $\varphi$ and a proof of $\psi$
A proof of $\varphi \lor \psi$ consists of a proof of $\varphi$ or a proof of $\psi$
A proof of $\varphi \to \psi$ consists of a construction of proofs of $\psi$ from proofs of $\varphi$
$\bot$ has not proof and $\neg \varphi$ means $\varphi \to \bot$

Godel attempted to formalize the BHK semantics. He put forward S4 as the logic of classical provability.  He suggests a method of translation from a non-modal language of intuitionistic logic into S4 modal logic.

Godel provides that if $\textbf{IPC} \vdash \varphi$ then $\textbf{S4} \vdash t(\varphi)$. The implication in the opposite direction had been later proven by McKinsey and Tarski. Thus, IPC can be taken to be about classical provability if and only if S4 is the logic of classical provability.

An explicit provability semantics of $\Box$ in S4 was missing. One natural candidate for the interpretation of $\Box$ was a formal provability predicate in a standar axiomatized mathematical theory.

## Arithmetical Provability Predicate
Considerations of formal provability predicates are usually developed in the context of an axiomatic arithmetic.

This is the case for various reasons:
1. via Godel coding, instead of expressions we can talk about numbers.
2. standard arithmetical theories are usually strong enough to include a sufficiently reach theory of syntax (modulo coding)
3. arithmetic in general is a field where many results are already known and can be borrowed and applied to syntax.

We'll focus on a fairly standard axiomatic arithmetic: Peano Arithmetic. The language of PA, $\mathcal{L}_{PA}$ is a first-order language with identity and a few specific symbols: $0, S, \times, +$. For any number $m$, the standard numeral for $m$ has the form $S...S0$ with $m$ $S$'s and is abbreviated by $\bar{m}$. 

The specific axioms of PA consists of: (look these are obvious im not writing them)

Formulas of $\mathcal{L}_{PA}$ can be classified according to their logical complexity. If $t$ is a term not containing $x$, $\forall x\leq t,  \varphi(x)$ and $\exists x \leq t, \varphi(x)$ abbreviate $\forall x(x \leq t \to \varphi(x))$  and $\exists x (x \leq t \land \varphi(x))$ respectively.

Such occurrences of quantifiers are called bounded, and formulas whose all quantifiers are bounded are called $\Delta_0$-formulas.

The hierarchy proceeds in two "layers", that of $\Pi_n$ and that of $\Sigma_n$ formulas. $$\Pi_0 = \Sigma_0 = \Delta_0$$
$\Sigma_{n+1}$-formulas are of the form $\exists x_1,...,x_k \varphi(x_1, ..., x_k)$, where $\varphi(x_1, ..., x_k)$ is $\Pi_n$. 
$\Pi_{n+1}$-formulas are of the form $\forall x_1, ..., x_k\varphi(x_1, ..., x_j)$, where $\varphi(x_1, ..., x_k)$ is $\Sigma_n$.

Every formula in $\mathcal{L}_{PA}$ is logically equivalent to a $\Sigma_n$ formula and to a $\Pi_m$ formula. for some n and m. There always exist the least such n and m.

The class of $\Sigma_1$ formulas is of particular interest, because it turns out that a function is   just in case it is $\Sigma_1$-definable. This result makes sure that an axiomatic system which is strong enough to handle $\Sigma_1$-sentences is strong enough to properly handle computable functions, including those related to syntactic manipulations, and so is strong enough to prove things about syntax of a formal language within it.

We say an arithmetical theory $T$ is $\Sigma_1$-sound just in case for any $\Sigma_1$-formula $\varphi$, if $T \vdash \varphi$, then $\mathbb{N} \models \varphi$ (that is, $\varphi$ is true in the standard model of arithmetic). The dual notion is that of $\Sigma_1$-completeness. $T$ is $\Sigma_1$-complete just in case for any sentence $\varphi \in \Sigma_1$, if $\mathbb{N}\models \varphi$ then $T \vdash \varphi$.

Here's a fact, PA is $\Sigma_1$-complete.

There are various ways of coding syntax, effectively mapping syntactic objects such as expressions, formulas, sentences, and sequences thereof to natural numbers, so that each syntactic object $\tau$ of $\mathcal{L}_{PA}$ is represented by its Godel code $\ulcorner \tau \urcorner$. Here's one.

Consider any theory $T$ in $\mathcal{L}_{PA}$ extending $PA$. It is said to be *elementary presented* just in case there is an arithmetical $\Delta_0$-formula $Ax_{T}(x)$ true of a natural number just in case it is a code of an axiom of T. Such a formula can be used in a fairly standard way to construct a $\Delta_0$ arithmetical formula $Prf_T(y, x)$ which is the standard binary proof predicate of $T$ such that it is true of natural numbers $m$ and $n$ just in case $m$ is the code of a sequence of formulas which is a proof of the formula whose code is $n$.

Moreover: 
If in the standard model $Prf_T(m, n)$ then $PA \vdash Prf_T(\bar{m}, \bar{n})$
If in the standard model $\neg Prf_T(m, n)$ then $PA \vdash \neg Prf_T(\bar{m}, \bar{n})$
(Binumeration)

$Prf_{T}(y, x)$ can be further used to define the so-called *standard provability predicate* and the consistency statement:

$$Prov_T(x) := \exists y Prf_T(y, x)$$
$$Con(x) := \neg Prov_T(\ulcorner\bot\urcorner)$$

$Prov_T(y)$ is obtained from a $\Delta_0$ formula by preceding it with an existential quantifier, and so, it is a $\Sigma_1$-formula. Therefore, by $\Sigma_1$-completeness, the first half of (Binumeration) holds for it. The second one fails:

If in the standard model $Prov_T(n)$ is true, then $PA \vdash Prov_T(n)$

Note that even though the second half of (Binumeration) fails, $Prov_T(x)$ succeeds in defining provability in the sense that $Prov_T(\bar{\ulcorner \varphi \urcorner})$ is true in the stnadard model fo arithmetic just in case in fact $T \vdash \varphi$. From now on we'll skip using the bar above numbers coding of formulas, assuming it is normally there, that is, that in the formulas we'll mention, numerals of codes of formulas are standard.

Assuming $T$ is elementary presented, $Prov_T(x)$ satisfies the following HIlbert-Bernays conditions, for any arithmetical formula $\varphi, \psi$:

1. $T \vdash \varphi$ iff $PA \vdash Prov_T(\ulcorner \varphi \urcorner)$
2. see book for rest.

In particular, the provability predicate of T can be taken to be that of PA itself.  Keep in mind most of the results apply to certain theories weaker than PA and to elementary presented theories extending PA.

Here's another imporant piece, Godel's incompleteness theorems, here's a modernized statement.

If an elementary presented theory T extends PA and is consistent, then there is a sentence $G \in \mathcal{L}_{PA}$ such that $T \nvdash G$  and $T \nvdash \neg G$. Moreover, $T \nvdash Con(T)$.

Incompleteness follows from a more general result:

Now consider the following Lemma, the Diagonal Lemma: For any formula $\varphi(x) \in \mathcal{L}_{PA}$ there is a sentence $\lambda \in \mathcal{L}_{PA}$ such that $$PA \vdash \lambda \equiv \varphi(\ulcorner \lambda \urcorner)$$
The diagonal lemma, when we take $\varphi(x)$ to be $\neg Prov_{PA}(x)$ entails the existence of a sentence that can be used in the incompleteness proof, which provably satisfies the condition:
$$G \equiv \neg Prov_{PA}(\ulcorner G \urcorner)$$
Such a G is independent of PA. The result generalizes: if a theory satisfies certain requirements and is consistent, it's Godel sentence is independent of it.

Years later Henkin asked a related question: what happens with sentences such as $H \equiv Prov_T(\ulcorner H \urcorner)$. This question was answered by Lob:

Lob's theorem states if the Diagonal Lemma applies to T, and the provability predicate of a theory T satisfies his formulation of the Hilbert Bernays conditions, $T \vdash Prov_T(\ulcorner \varphi \urcorner) \to \varphi$ if and only if $T \vdash \varphi$.

For a given sentence $\varphi$, the formula $Prov_T(\ulcorner \varphi \urcorner) \to \varphi$ is called *reflection for $\varphi$ over T*, and Lob's theorem says that reflection is provable in T for all and only all theorems of T. The theorem can be obtained fairly easily from the Diagonal Lemma applied to $Prov_T(x) \to \varphi$. For if the Diagonal lemma applies to T (it's enough that T extends PA), the Lemma entails the existence of a $\psi$ such that $T \vdash \psi \equiv (Prov_T(\ulcorner \psi \urcorner) \to \varphi)$

The rest of the reasoning is proposition (see book for proof).

## The Inadequacy of S4 with Respect to Formal Provability
Coming back to the question of whether $\Box$ of S4 can be sensibly interpreted as the formal provability predicate: what happens when we take $\Box \varphi$ to mean $Prov_T(\ulcorner \varphi \urcorner)$? For the sake of simplicity take the case where T = PA, but the point generalizes to consistent recursively axiomatizable extensions of PA.

Since $S4 \vdash \Box \varphi \to \varphi$ for any $\varphi$, the interpretation would requite that for all $\phi \in \mathcal{L}_{PA}, PA \vdash Prov_{PA}(\ulcorner \varphi \urcorner) \to \varphi$. But this, jointly with Lob's theorem, would entail that for any $\varphi \in \mathcal{L}_{PA}, PA \vdash \varphi$. So, if PA is consistent, S4 is not the logic of the formal provability predicate of PA.

There's a different way to notice the inadequacy of S4 in this context, brought up by Godel. The formula expressing $Con(PA)$ is $\neg Prov_{PA}(\ulcorner \bot \urcorner)$ which is logically equivalent to $Prov_{PA}(\ulcorner \bot \urcorner) \to \bot$. At the modal level, this is just an axiom of S4, since $\Box \bot \to \bot$ falls under schema (M). Thus, if S4 was adequate, we could have $PA \vdash Con(PA)$ which contradicts Godel's second incompleteness theorem. Moreover, necessitation would yield $\Box(\Box \bot \to \bot)$, and so in S4 we would be able to derive that claim that the consistency claim is derivable, which again contradicts Godel's second incompleteness theorem.

So, what is the right modal logic of formal provability? What's the right provability semantics for S4?