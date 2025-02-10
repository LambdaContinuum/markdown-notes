## Forming the Deontic Language
---
The sentences of a deontic language are formed recursively in three steps:
1. Atomic sentences devoid of normative content are the starting material. Truth-functional combinations such as $p \lor q$ are formed from atomic sentences.
2. Deontic operators such as $O$ are prefixed to the outcomes of the first step, this gives rise to atomic deontic sentences.
3. Truth functional combinations are formed from the outcomes of the previous step.

## Standard Deontic Logic
---
Georg Henrik von Wright can be said to have founded modern deontic logic, in his famous 1951 paper he set forth a number of axioms that in his view characterize rational reasoning about norms. This was before the advent of possible world semantics.

A crucial difference between modal and deontic possible worlds semantics is that the accessibility relation should be reflexive in the former but not in the later; so that $\Box p \to p$ holds but not $Op \to p$.

William Hanson constructed deontic semantics so that it differs from modal semantics only in respect to the accessibility relation not being reflexive. This elegant construction yields the logical principles that von Wright had proposed for deontic logic with one exception. In his 1951 paper, von Wright had proclaimed a principle of "deontic contingency" for tautologies, namely: "A tautologous act is not necessarily obligatory", $\neg O(p \lor \neg p)$. Possible world semantics validated the opposite principle: $$O(p \lor \neg p) \text{ (The axiom of the empty duty)}$$
In spite of its intuitive implausibility, this postulate was rapidly accepted as a tribute to logical elegance.

Most deontic logicians were primarily interested in unnested deontic sentences, i.e. sentences in which no deontic operator is positioned within the scope of another such operator. With this limitation, the accessibility relation of modal-style deontic logic can be replaced by a strikingly simple semantic construction:

> [!box_name] *Ideal Worlds Intersection* (IWI)
> There is a subset $\mathcal{I}$ of the set $\mathcal{W}$ of possible worlds, such that:
> For all $p$, $Op$ holds if and only if $p \in w$ for all $w \in \mathcal{I}$

$\mathcal{I}$ is called the set of "ideal" worlds (or "deontically ideal" or "(deontically) perfect" worlds). It's easy to show that the sentences that are valid in this simple model coincide with those that are derivable from the following three axioms: $$\begin{align}&Op \to \neg O\neg p\\ &Op \land Oq \iff O(p \land q)\\ &O(p \lor \neg p)\end{align}$$
The first two of these axioms were presented in von Wright's paper, whereas the third is the axiom of the empty duty that had to replace its negation in order to fit into the semantics. The second axiom is equivalent to the combination of the following two: $$\begin{align}&Op \land Oq \to O(p \land q) && \text{(agglomeration)}\\
&\text{If }Op, \text{ and }p \text{ logically implies }q, \text{ then } Oq. && \text{(necessitation)} \text{}\end{align}$$
In 1969 Bengt Hansson introduced the term "standard deontic logic" (SDL) to denote the deontic logic that can be characterized either by these axioms or by the semantic principle of Ideal Worlds Intersection.

It was realized at an early stage that SDL in its original form lacks a credible account of conditional obligation. A sentence such as "If you insult her then you ought to apologize to her" can be semi-formalized as "If $p$ then $Oq$", but what does a full formalization look like?

The two obvious options in the SDL language, $O(p \to q)$ and $p \to Oq$ can be shown to give rise to absurd conclusions. To solve this, Hansson introduced a two place predicate $O(q\mid p)$ ("if $p$ then $q$ is obligatory"). He also proposed a simple semantic principle for conditional obligation. Instead of just dividing the possible worlds into ideal worlds and non-ideal worlds, we can order them in more than two grades. Immediately beneath the ideal worlds we have second-best worlds, beneath them third-best worlds, etc. In order to determine the conditional obligations relative to some statement $p$, we restrict our attention to worlds in which $p$ is true. Then $O(q\mid p)$ holds if and only if $q$ holds in all those worlds that are best among the worlds in which $p$ is true.

SDL has been under constant attack due to the implausible results that have been derived from it. Consider the next two sections.

## Free Choice Permission
---
Recently when a neighbor asked me if he could borrow a crowbar, I showed him my crowbars and said:

> You may borrow either the big or the small crowbar.

In saying so, I offered him a choice between the two tools. However, in another context the same sentence could have another meaning. Suppose that the tools belonged to someone else who had authorized me to lend one of them to the neighbor. However, I had forgotten which of the two he could borrow. Then I could have said:

> You may borrow either the big or the small crowbar, but I do not know which.

The first case illustrates *free choice permission*. In natural language, this is by far the most common meaning of permissive expressions that refer to a disjunction. A formal permission operator that represents it should expectedly satisfy the postulate: $$P(a \lor b) \to Pa \land Pb.$$
However, this principle does not hold in SDL. The most obvious solution would be to just add the axiom $P(a \lor b) \to Pa \land Pb$ to the SDL axioms. However, this axiom combined with the original postulates gives rise to a whole series of implausible results. See: $$\begin{align}
&O(\neg a \land \neg b) \to O \neg a && \text{Holds in SDL.}\\
&O\neg(a \lor b) \to O\neg a && \text{Equiv to 1.}\\
&\neg O\neg a \to \neg O\neg(a \lor b) && \text{Contrapositive.}\\
&Pa \to P(a \lor b) && \text{Definition of P.}\\
&Pa \to Pb && \text{From added postulate.}
\end{align}$$
What this means is that if something is permitted $(Pa)$ then so is everything else $(Pb)$. This is obviously an intolerable result. Therefore, we cannot solve the "free choice problem" by just turning the SDL permission operator into an operator of free choice permission..

Having realized this, deontic logicians tried instead to add a second permission operator $P_c$ to supplement rather than replace the SDL operator $P$. Arguably, this could most naturally be done with the definition $$P_c(a \lor b) \iff Pa \land Pb.$$
However, this definition has implausible consequences as shown for instance in the following derivation: $$\begin{align}
&Pa \to (Pa \land P(a \lor b)) && Pa \to P(a \lor b)\text{ holds in SDL}\\
& Pa \to P_c(a \lor (a \lor b)) && \text{Definition of }P_c\\
&Pa \to P_c(a \lor b)
\end{align}$$
Hence, if you're permitted to borrow a book ($Pa$), then you have a free choice to either borrow or steal the book ($P_c(a \lor b)$).

Several other more complex constructions of free choice operators have been tried out, but they all have been shown to have absurd consequences. The underlying reason for this all is that all rely on the following assumption that's usually been taken for granted:

> *The single sentence assumption:* Free choice between $a$ and $b$ can be represented as a property of a single sentence, namely $a \lor b$.

Provided that logically equivalent sentences are interchangeable, the single sentence assumption has the following implication:

> If $a \lor b$ is equivalent with $c \lor d$, then there is a free choice permission between $a$ and $b$ if and only if there is a free choice permission between $c$ and $d$.

This leads to absurd conclusions:

> *The vegetarian's free lunch*
> In this restaurant I may have a meal with meat or a meal without meat. Therefore I may either have a meal and pay for it or have a meal and not pay for it.
> *Proof.* Let $m$ denote that you have a meal with meat, $v$ that you have a meal without meat, and $p$ that you pay. $P(m \lor v)$ is equivalent with $P(((m \lor v) \land p) \lor ((m \lor v)\land \neg p))$.

To sum up, free choice permission is a permission to perform either the action represented by the sentence $a$ or the sentence $b$. We've found that it is not a function of a single sentence $a \lor b$ but a function of the two sentences $a$ and $b$. Therefore, free choice permission should be represented as a property of a set of action-describing sentences ($\{a, b\}$) rather than a property of the disjunction of these sentences ($a \lor b$).

## The Deontic Paradoxes
---
The problem with free choice permission is that we had an intuitively plausible deontic principle that does not hold in SDL.

There are many cases in which the difference goes the other way around: A property holds in SDL but it is not intuitively plausible. Such divergences are called "deontic paradoxes". The best-known of them is Ross's paradox. It's a counterexample to the following SDL theorem: $$\begin{align}P(p \lor q) \to Pp \land Pq && \text{If p is obligatory then so is p or q.}\end{align}$$Ross proposed the following counter-example:

> If you ought mail the letter, then you ought mail or burn it.

Several other deontic paradoxes have been proposed: Consider Åqvist's knower paradox:

> If the police officer ought to know that Smith robbed Jones, then Smith ought to rob Jones.

This is a counter-example to the SDL principle of necessitation. The paradox also makes use of the epistemic principle that only what which is true can be known.

As von Wright pointed out, all the major deontic paradoxes rely on necessitation. Necessitation in its turn follows from the basic construction of possible world semantics for SDL, namely that a sentence is valid if and only if it holds in all elements of a certain set of possible worlds. The paradoxes put this construction in doubt.

This construction has also been criticized on more fundamental ethical grounds. Important types of obligation that are recognized and discussed in moral philosophy are difficult to account for in SDL semantics. This applies for instance to obligations of compensation and reparation.

Suppose John sees a small child fall into the pool in front of him. It would be easy for him to save the child's life. Does he have an obligation to do so? According to SDL semantics, we have to consider what his actions would have been in an ideal world. In an ideal world, the child would presumably not have fallen into the water. (This may apply even if we consider the ideal worlds to be ideal only in terms of obligation-fulfillment. If the child's parents had fulfilled their obligations, then the accident would not have happened.) Hence, in the ideal worlds the child would not have been in danger, and John could not have saved it. It follows that John is under no moral obligation to save the child. This example is due to Holly Goldman, according to whom SDL "ignores the fact that particular obligations flow from abstract principles *together with* contingent features of the world", and these features "do not appear in *all* the morally best worlds".

Preventive actions are almost as difficult as compensatory ones to account for in SDL semantics. In an ideal world there will be no acts of violence or racism, and consequently no one will act to prevent such misdeeds. Therefore, if our obligations in the actual world consist in doing what we would have done in the ideal worlds, then there can be no obligation in the actual world to act against violence or racism.

## Alternative Semantics
---
Instead of judging the obligatoriness of actions according to the value of the worlds in which these actions take place, we can relate obligatoriness to the value of these actions themselves. This can be done by relating normative predicates to an underlying preference relation $\geq$. The following definition will then have a central role:

> A predicate $H$ is *positive* with respect to a preference relation $\geq$ if and only if it holds for all $p$ and $q$ that if $Hp$ and $q \geq p$, then $Hq$. Which is to say if $p$ has the $H$-property and $q$ is at least as good as $p$, then $q$ has the $H$-property.

A plausible preference-based deontic logic can be founded on the simple principle that the permissive predicate $P$ is positive with respect to some underlying preference relation $\geq$. That is to say, if $p$ is permitted and $q$ is at least as good as $p$, then $q$ is also permitted. In contrast, the prescriptive predicate $O$ cannot be assumed to satisfy this. To see this, suppose that you have an unexpected, hungry visitor. Let $p$ denote that you give your hungry visitor something to eat and $q$ that you serve her a gourmet meal. It's quite plausible to value $q$ at least as highly as $p$. But even if we do so we can hold $p$ to be morally required without also holding $q$ to be morally required. In other words, we can have $Op, q \geq p$ and $\neg Oq$, which shows the obligation predicate $O$ does not satisfy positivity.

Under this framework, the validity of postulates in deontic logic will depend on the properties of the underlying preference relation. Standard preference relations give rise to a deontic logic in which the necessitation postulate (the source of the deontic paradoxes) does not hold, but several other, more plausible postulates hold. See the following: $$
\begin{align}
&Op \land Oq \to O(p \land q)\\
&O(p \land q) \to Op \lor Oq\\
&P(p \land q) \land P(p \land \neg q) \to P p
\end{align}
$$