# Self-Reference and Godel-Tarski Dagonalization
---
The simplest way to achieve self-reference is via empirical description. Suppose someone I think little of is talking, and I say "What is being said by the person in this room with the lowest IQ isn't true." Suppose that the person in the room with the lowest IQ is not him but me, so I've uttered what Hartry calls a "contingent Liar sentence".

This sort of Liar sentence(involving what we'll call *Contingent Self-Reference*) requires a language with empirical predicates, and in formal investigations it is often convenient to consider simpler languages that don't have such predicates. One possibility (which we'll call *Artificial Self-Reference*) is to consider languages within which we can have a name for sentences that contain that vary name: we let 'Q' be the name of the sentence 'Q is not true'. This could well seem suspicious. There's a third route to self-reference, which produces the same effect but through much less artificial means. It's due to Kurt Godel and Alfred Tarski, so we'll call it *Godel-Tarski Self-Reference*.

The background for *Godel-Tarski Self-Reference* is the observation that any language of sufficient power can express its own syntax. Let's consider two ways in which we might set up a simple language $\mathcal{L}$ that can accomplish this.

The obvious idea suggested by Tarski would be to set up $\mathcal{L}$ so that it has its own expressions as its direct subject matter. If $\mathcal{L}$ is a normal language, its expressions are formed from the letters of a finite alphabet $V$; so to get direct self-reference we should imagine that among the names in $\mathcal{L}$ (which like all expressions in $\mathcal{L}$ are strings of letters in $V$) are names of each member of $V$. We also imagine that $\mathcal{L}$ contains a predicate '$\mathcal{L}$-expression' that holds of precisely the finite strings of alphabet items; and it contains a 2-place function symbol '^' such that 'x ^ y' means 'the result of concatenating x and y in that order'.

Using this, we get for each $\mathcal{L}$-expression $e$, a singular term $\langle e\rangle$ that denotes $e$. With a few other devices, we can formulate all the basic syntactic properties of $\mathcal{L}$ within $\mathcal{L}$. We can formulate a theory in the language (called *concatenation theory* or *protosyntax*) in which we can prove a very comprehensive body of truths about those syntactic properties.

Rather than proceeding in this direct way, it's easier and more tradition to proceed via number theory. By setting up a correlation between letters in the alphabet of the theory with certain numbers, and between the concatenation relation and a certain relation among numbers, we can set up a secondary interpretation of number theory in which it is in part a theory of its own syntax. This idea is due to Godel and is called Godel numbering. We get for each expression $e$ of the language a term $\langle e \rangle$ that stands for *the number correlated with* $e$. We may as well identify the expression with the corresponding number, and say that $\langle e\rangle$ stands for $e$ itself.

Either way we do it, we get a striking result due both to Godel and Tarski: that for any property expressible in the language, we can find a sentence in the language that in effect attributes that property to itself (or to its own Godel number, if we want to make that distinction). More precisely:

> [!theorem] Godel-Tarski Diagonalization Lemma (semantic version):
>  For any formula $C(v)$ in the language of arithmetic (or the syntactic language) with $v$ as its only free variable, there is a sentence $F$ in that language such that $F \iff C(\langle F \rangle)$ is an arithmetical truth (or on the direct approach, a truth of the syntactic theory).

The Diagonalization Lemma is often called the (Godel-Tarski) Fixed Point Lemma.

This semantic version of the Dagonalization Lemma uses the notion of arithmetic truth which cannot be formulated in arithmetic language. For this reason the following version is more useful:

> [!theorem] Godel-Tarski Diagonalization Lemma (proof-theoretic version):
>  For any formula $C(v)$ in the language of arithmetic (or the syntactic language) with $v$ as its only free variable, there is a sentence $F$ in that language such that $F \iff C(\langle F \rangle)$ is *provable in the arithmetic (or syntactic) theory*.

Since the arithmetic theory is intuitively true, the semantic version is an intuitive consequence of the proof-theoretic, even though it can't be stated in the language.

**Proof of Diagonalization Lemma**. Let the *self-application* of a formula $B(v)$ be the sentence $B(\langle B \rangle)$ that results from substituting the name $\langle B \rangle$ for all free occurrences of $v$ in $B$. This operation is expressible in the syntactic (or arithmetic) language. Now given the formula $C(v)$, let $D(v)$ be the formula $$\exists x[x \text{ is the self-application of }v \land C(x)].$$
Let $F$ be the self-application of the formula $D(v)$, i.e., the formula $$\exists x[x \text{ is the self-application of} \langle D(v)\rangle \land C(x) ].$$
But the claim $$\langle F \rangle \text{ is the unique self-application of }\langle D(v)\rangle$$
is an obvious truth that is provable by very elementary means available in the arithmetic or syntactic theory. From this and the nature of the formula $F$, it's clear that $$F \leftrightarrow \exists x[x = \langle F \rangle \land C(x)]$$
and hence $$F \leftrightarrow C(\langle F \rangle)$$
Here's a minor observation: $F$ doesn't literally say of itself (or even, of its Godel number) that it has the property $C$; still, it's provably equivalent to a sentence that says $F$ (or it's Godel number) has property $C$. We've achieved something very like self-reference by indirect but unquestionably legitimate means. In fact, if the language contained a description operator $\iota$, you could get literal self-reference, relative to the Godel numbering: F could be taken to be $C(\iota x[x \text{ is the self-application of }\langle D(v)\rangle])$, and the description would refer to (the Godel number of) F. The use of self-reference by description rather than by name avoids the artificiality of Aritifical Self-reference.

Here's an important observation: The Diagonalization Lemme generalizes automatically to apply to richer theories in which arithmetic can be embedded. The richer theories can contain new vocabulary; $C(v)$ can then be an arbitrary formula in the richer language. **The result even applies when the logic of the richer theory is weaker than classical**, as long as
1. classical logic holds for the arithmetic or protosyntactic subtheory
2. a modicum of standard quantifier reasoning is allowed
3. the logic of the biconditional '$\leftrightarrow$' is reasonable; more particularly
	1. $A \iff A$ and $\exists x [x = t \land C(x)] \leftrightarrow C(t)$ are theorems
	2. If $A \leftrightarrow B$ is a theorem then intersubstituting $B$ for $A$ preserves theoremhood.

See proof in *Saving Truth from Paradox* p.g. 27

# Tarski's 'Undefinability Theorem'
---
The Diagonalization Lemma will have many applications in what follows. The first is Tarski's "Undefinability Theorem".

> [!theorem] Tarski's theorem for the language of arithmetic (proof-theoretic version): 
> If $B(v)$ is any formula in the language of arithmetic with $v$ the only free variable, then there is a sentence $Q$ in the language such that $\vdash_N \neg[Q \leftrightarrow B(\langle Q \rangle)]$.

**Proof.** Apply the Diagonalization Lemma to the negation of B, getting $\vdash_N Q \leftrightarrow \neg B(\langle Q \rangle)$. In classical logic, $Q \leftrightarrow \neg B(\langle Q\rangle)$ implies $\neg[Q \leftrightarrow B(\langle Q \rangle)]$.

It seems that any candidate for True for a predicate of arithmetic truth should satisfy the condition that for any sentence $A$ of arithmetic, $A \leftrightarrow \text{True}(\langle A \rangle)$. So Tarski's Theorem as just formulated says that no formula definable in the arithmetic language can be a truth-predicate for arithmetic. "Arithmetic truth is not arithmetically definable".

The proof just given amounts to this: if arithmetic truth were definable in arithmetic, we could construct the Liar paradox within arithmetic, and thus get a contradiction from the uncontroversial assumption that classical logic holds within arithmetic and that *at least when* $A$ *is arithmetic*, $A \leftrightarrow \text{True}(\langle A \rangle)$. The contradiction shows that arithmetic truth can't be arithmetically definable.

It's clear that Tarski's Theorem generalizes to theories in classical logic in which the theory N can be embedded. Let's consider several extensions.

Call the first extension $\mathcal{L}_1^\text{arithm}$. It's the result of adding to the language $\mathcal{L}_0^\text{arithm}$ of arithmetic a primitive truth predicate of arithmetic truth, '$\text{Truth}_0^\text{arithm}$, meaning 'is a true sentence of the language $\mathcal{L}_0^\text{arithm}$'. Assuming classical logic applies to this predicate, the generalized proof of Tarski's theorem tells us that there is a sentence $Q$ such that it's provable in the expanded language that $\neg[Q \leftrightarrow \text{Truth}_0^\text{arithm}(\langle Q \rangle)]$. From the proof of the Diagonalization Lemma, it's clear that $Q$ will itself contain the predicate $\text{Truth}_0^\text{arithm}$. There is no problem in consistently adding as axioms for the expanded language all instances of $A \leftrightarrow \text{Truth}_0^\text{arithm}(\langle A \rangle)$ *for those A in the pure arithmetic language* $\mathcal{L}_0^\text{arithm}$ which does not include Q. In fact those instances of the truth schema don't entail any important generalizations and we can consistently add compositional principles that do entail such generalizations.

So we can get a good theory of pure arithmetic truth, truth for sentences of $\mathcal{L}_0^\text{arithm}$, within $\mathcal{L}_1^\text{arithm}$. But the theorem shows we can't consistently extend the interpretation of '$\text{Truth}_0^\text{arithm}$' to make it an adequate truth predicate for sentences of $\mathcal{L}_1^\text{arithm}$. $\mathcal{L}_1^\text{arithm}$ can't contain its own truth predicate, any more than $\mathcal{L}_0^\text{arithm}$ can.

As a second extension we can consider the language $\mathcal{L}_2^\text{arithm}$ obtained by adding to arithmetic not only the predicate '$\text{Truth}_0^\text{arithm}$' but also a new predicate '$\text{Truth}_1^\text{arithm}$'. We can keep on extending this process a very long way (beyond the natural numbers in fact, and for a quite a long way through the countable ordinals). We'll call this hierarchy the *Tarski hierarchy over arithmetic*. (This is a bit historically inaccurate).

A more far-reaching extension of arithmetic is to the language of standard set theory, which is a classical-logic theory in which number theory can be embedded. Each of the truth predicates in the Tarski hierarchy over arithmetic can be defined within set theory: extending arithmetic to set theory is far more powerful than extending it by adding a predicate of arithmetic truth. But the generalized theorem implies that the notion of *set-theoretic* truth cannot be defined within set theory.

The next extension to consider is to the language of set theory supplemented by a predicate '$\text{Truth}_0^\text{set}$' of set-theoretic truth, together with appropriate axioms governing it. Again, we assume that classical logic applies to this predicate. The generalized theorem then implies that this language can't contain its own truth predicate, and so we are launched on a new hierarchy of truth predicates which might be called *the Tarski hierarchy over set theory*.

Is there some sort of theory that stands to set theory as set theory stands to arithmetic? Maybe, but no one has any idea what it is. And even if there was one, if it's a classical theory it cannot contain its own truth-predicate and we'll just launch a new hierarchy.

It seems that whatever mathematical theory we start with, we can successively extend it indefinitely, by going up in a Tarski hierarchy over that mathematical theory. But we need to be careful, as we'll show below.

# Tarski's "Undefinability Theorem" States more than Undefiniability
---
Let's consider one last extension of Tarski's theorem. Suppose we start with set theory and add a predicate not of set-theoretic truth, but simply of truth *tout court*, together with some axioms governing this notion.  Truth is being added as a primitive predicate.

If we assume classical logic applies to this predicate, the Tarski theorem implies that there is a "Liar sentence" $Q$ in the language such that we can prove in the resulting theory that $\neg [Q \leftrightarrow \text{True}(\langle Q \rangle)]$.

If one is unwilling to contemplate the idea that the Tarski truth schema, $\langle A \rangle$ is true if and only if A, might have exception, then we seem to have proven what we've added can't really b a truth predicate. So Tarski's theorem is far more than an undefinability theorem; it says that full truth cannot appear in the language *even as a primitive predicate*, if full truth is assumed to obey both the Tarski schema and classical logic.

This conclusion is odd: it should lead us to suspect that we don't even understand a concept of full truth that obeys both the Tarski schema and classical logic. There seems to be three possible concluions:
1. There's no coherent concept of full truth at all.
2. There is such a concept, but it violates the Tarski schema.
3. There is such a concept, but in dealing with it one must generalize the rules of classical logic somehow.

(1) is the standard Tarskian picture of an increasing hierarchy of truth predicates, each more extensive than the previous. (2) and (3) each avoid this, at what may at first seem like a high cost.

Views of type (2) and type (3) are extensions of the views of type (1), in that with a general truth predicate, we can define the restricted Tarskain predicates and within such views we can maintain classical logic and the appropriate instances of the Tarski truth schema for the restrictive predicates. Odd behavior of (2) and (3) occur only in a domain where view (1) doesn't venture, so in evaluating view (1) we must compare the cost of not venturing into that domain with the cost of venturing there but saying something in that domain which intuitively seems odd.

The viewpoint underlying this *Saving Truth from Paradox* is that because it's extremely easy to enter the dangerous domain inadvertently, the cost of ensuring that one doesn't enter is extraordinarily high. This gives a striking advantage to views of type (2) and (3) over views of type (1).

First, we should understand why (3) isn't blocked by Tarskis theorem. Recall the diagonalization lemma extends to non-classical logics provided that they meet some fairly minimal conditions. Hartry is not proposing that we weaken logic to such an extent as to drop any of these conditions; so the Diagonalization Lemma will be accepted even in the weakened logic he proposes. So why does Tarski's theorem not generalize? The Diagonalization Lemma yields only the conclusion $Q \leftrightarrow \neg \text{True}(\langle Q \rangle)$; we need an additional step to get form this to $\neg[Q \leftrightarrow \text{True(\langle Q \rangle)}]$ as required by Tarski's theorem. The inference from $A \leftrightarrow \neg B$ to $\neg (A \leftrightarrow B)$ is valid according to classical logic, and there's no doubt that it can legitimately be assumed in many circumstances; but Hartry thinks it's contentious to assume it valid without restriction. If $A \leftrightarrow \neg \neg A$ is valid then the contentious assumption yields the validity of $\neg(A \leftrightarrow \neg A)$, and this is a possible source of the heterlogicality paradox an the Russell paradox for properties.

So even if the assumptions required for the Diagonalization Lemma are satisfied, Tarki's theorem in the form stated as the start need not be valid in a non-classical extension of classical arithmetic.

We do still have that truth is not definable in set-theory, or indeed in any classical language. We can this in two ways:
1. if 'true' were definable in set theory, then the more restrictive predicate 'true sentence of set theory' would also be definable, which conflicts with the extension of Tarski's Theorem to set theory; and since set theory is classical, that extension of Tarski's Theorem is valid. Analogous arguments can be given for any other classical theory in which arithmetic embeds.
2. If 'true' were definable in a classical theory like set theory, then it would have to be a classical predicate, so Tarski's theorem would have to apply.

# Another Form of Tarski's Theorem
Tarski's theorem is often stated in a semantic version.

> [!theorem] Tarski's theorem for the language of arithmetic (semantic version): 
> No formula $B(v)$ in the language of arithmetic can be true of precisely the true sentences of arithmetic.

The semantic version clearly follows from the proof-theoretic version. So it's certainly a theorem of set theory. But it is not a theorem of arithmetic itself. Indeed, it cannot even be *stated* in arithmetic itself, since arithmetic doesn't contain its own truth predicate.

For the same reason as for arithmetic, a generalization of the semantic theorem to set theory cannot be stated within the language of set theory. There are those who think of set theory as our all-purpose mathematical theory. For them, Tarski's theorem in its semantic form simply has no analog in the set-theoretic case. The proof-theoretic version is thus of more general applicability.

Similar to the proof-theoretic form, the theorem in the semantic form does not generalize to all non-classical theories. That's why there is hope for a theory that contains its own truth predicate.

# Can Set-Theoretic Truth Be Defined?
---
Even though Tarski's Theorem in the form stated needn't apply when the language is non-classical, the undefinability claim still holds. A general notion of truth, if such a notion is recognized, cannot be definable in any classical sublanguage, such as the language of set-theory. A general notion of truth must be taken as primitive. Some will find this unappealing. 

However, that does not seem unique to general notions of truth: it seems to arise equally for classical notions of truth in the Tarski hierarchy over sufficiently rich mathematical theories. Indeed, it seems to arise even at the lowest level of the Tarski hierarchy. Hartry says "seems" because there is a somewhat controversial philosophical issue involved here.

The issue then will be the definability of $\text{truth}_0$, that is, the definability of true-in-$\mathcal{L}$ for languages $\mathcal{L}$ that do not themselves contain 'true' or related notions.

It is sometimes said that Tarski showed that a truth predicate for a language $\mathcal{L}$ is always definable, though only in a more powerful language $\mathcal{L}^*$. This is a contentious claim. It's also a claim that Tarski explicitly denied. He says that such a definition is possible only when $\mathcal{L}$ is limited in its expressive power. He says that for "richer" languages, definition is impossible, and the goal should be replaced by that of giving an axiomatic theory of truth. The reason he gives for why it's impossible to define truth for richer languages is precisely the undefinability theorem we've already discussed.

This seems like the natural conclusion to draw from Tarski's Theorem. It's true that arithmetic truth can be defined in a richer language, the language of set theory. But what about set-theoretic truth? One could say that it's trivially definable in the language of set theory *plus the notion '$\text{True}_0^\text{set}$' of set theoretic truth*. But this sort of trivial definition isn't what Tarski had in mind. He had in mind definition in terms of notions of a "non-semantic" nature. There remains the possibility we introduce a richer theory and define set-theoretic truth within it.

It might be protested we have such a theory: proper classes. These would have to be the impredicative proper classes of the Morse-Kelley theory of classes. Predicative classes of the Godel-Beranys theory of classes don't suffice for defining set-theoretic truth. But within Morse-Kelley class theory truth is undefinable.

A further protest might be that truth-in-Morse-Kelley is definable, by an extension of Morse-Kelley to include "super-classes". The protest continues:
1. This process of introducing more and more powerful entities is never-ending, in a way that precludes the possibility of a single theory governing all of the entities obtainable by the process.

and yes.
2. the powerful entities to be introduced at later stages in the process are available now for defining truth for sentences at earlier sstages.

Each of these claims raises huge philosophical issues. Assumption (1) (that "ontology is indefinitely extensible") has been much discussed recently with little consensus. But many versions of (A) do not support (B). For instance, one natural way to defend the indefinite extensibility of ontology is to argue that mathematical entities are fictions, and that it's always possible to extend any fiction.. But finding a way to fruitfully extend a mathematical fiction is not a routine matter, and when working within a given fiction of any kind that we know how to clearly articulate, it makes sense to talk unrestrictedly of all mathematical objects.

The point is that to invoke "indefinite extensibility of ontology", and to declare that it can be used to show that any truth concept is definable, is extraordinarily contentious. Without both contentious assumptions, we cannot suppose that we can always define a truth predicate for a language $\mathcal{L}$ in non-semantic terms by going to a more powerful language $\mathcal{L}$.

# Inductive Characterizations and Restricted Truth Definitions
---
Tarski showed how to characterize truth inductively, for languages that don't themselves contain truth predicates. In the case of the usual language of arithmetic, where all quantifiers are implicitly restricted to the natural numbers and every object in the restricted domain is denoted by some term in the language, it's very easy to give the inductive definition.

We start with an inductive characterization of denotation:
1. (The Godel number of) the name '$0$' denotes $0$ and nothing else.
2. For any closed singular terms $t_1$ and $t_2$ and any number $n$, $\ulcorner t_1 + t_2 \urcorner$ denotes $n$ if and only if there are numbers $m_1$ and $m_2$ such that $t_1$ denotes $m_1$, $t_2$ denotes $m_2$, and $n = m_1 + m_2$.

plus similar clauses for the other primitive names and function symbols.

Skipping this section except last paragraph.

In the case of arithmetic truth, we could make the inductive characterization explicit evein in arithmetic if instead of quantifiers over natural numbers, we had only quantifiers bounded by a specific natural number. The analog holds here: an attempt at making the definition of truth explciit would work fine if the quantifiers ranged only over sets of rank less than some specific ordinal $\alpha$, for then there would be sets meeting certain conditions for truth. We can now see why truth is definable in Tarski's languages with variables of bounded order, but not in his languages with variables of unbounded order.


