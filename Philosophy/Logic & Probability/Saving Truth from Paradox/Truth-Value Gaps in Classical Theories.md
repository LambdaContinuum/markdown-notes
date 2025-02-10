# Gaps And (T-Out)
---
One response to the Liar is to divide up the classically inconsistent truth schema into two components and retain one of them. The two components:

(T-OUT): $\text{True}(\langle A \rangle) \to A$
(T-IN): $A \to \text{True}(\langle A \rangle)$

Which to keep? The most popular choice is to retain (T-OUT), while restricting (T-IN) while adding further laws to compensate for the restriction.

There's two different ways to develop this idea, "Kleene-like gap theories" and "supervaluation-style gap theories". The first is exemplified by the Kripke-Feferman theory KF that Hartry calls [[Kripke's Theory of Truth (Strong Kleene Version)|FM]].

The other is exemplified by gap theories based on supervaluational fixed points, though it has other exemplifications, like gap theories based on revision-rule constructions.

In either, it's not enough to keep (T-OUT) and a restricted version of (T-IN), since any reasonable theory will have to imply certain additional schemas such as

(C+): $\text{True}(\langle A \land B \rangle) \leftrightarrow \text{True}(\langle A \rangle) \land \text{True}(\langle B \rangle)$

And not all instances of (C+) are derivable from (T-OUT) plus a restricted (T-IN) (unless those restrictions are too weak to avoid inconsistency) should be clear. So an advocate of (T-OUT) need either adopt (C+) as a primitive schema or adopt a universal generalization:

(CONJ+): For any sentences x and y, $\text{True}(conj(x, y)) \leftrightarrow \text{True}(x) \land \text{True}(y)$

This will be part of both Kleene-like and supervaluation-style gap theories. The most symptomatic difference between those two types of theories will be over the corresponding rules for disjunction.

Let's see what happens when we simply retain (T-OUT). One immediate consequence of (T-OUT) alone is that the Liar sentence isn't true.
1. $T(\langle Q \rangle) \to Q$ by (T-OUT)
2. $Q \to \neg T(\langle Q \rangle)$ by the construction of Q
3. So $T(\langle Q \rangle) \to \neg T(\langle Q \rangle)$ by transitivity
4. So $\neg T(\langle Q \rangle)$

The last set of this uses the rule $A \to \neg A \vdash \neg A$; this not in valid in non-classical logics of the sort we will be discussing, but it's valid in classical logic. This claim $\neg T(\langle Q \rangle)$ has superficial appeal, but the appeal lessens when one reflects that claim is equivalent to Q itself. So all classical (T-OUT) theories imply the following odd claim:

1. $Q  \land \neg T(\langle Q \rangle)$

or what amounts to the same thing

2. $\neg T(\langle Q \rangle) \land \neg T (\langle \neg T(\langle Q \rangle)\rangle)$

The first conjunct asserts a claim and the second conjunct asserts the first conjunct isn't true. Before exploring this further, let's look at some more consequences. The next is that Q also isn't false, i.e. its negation isn't true. This proof is easy too:

1. $T(\langle \neg Q \rangle) \to \neg Q$ by (T-OUT)
2. $\neg Q \to \neg T(\langle \neg Q \rangle)$ by the contraposition
3. but $Q$ as previously proven
4. So $\neg T(\langle \neg Q \rangle)$

Letting falsehood mean truth of negation, this allows us to expand (1) to 

3. $Q \land \neg T(\langle Q \rangle) \land \neg F(\langle Q \rangle)$

Let's introduce the term Gappy for "not true and not false", rewrite this as

$Q \land Gappy(\langle Q \rangle)$

This might ameliorate the situation with the liar; maybe it's ok to assert a sentence while declaring in the same breath that it isn't true, if this is because you're willing to also declare that it's gappy? There's a sense in which it is so: for if Q were declared not just untrue but false, this would be doubly odd in that it would violate the second incoherence principle as well as the first. I don't see how this makes the violation of the first incoherence principle any less counterintuitive.

It's worth to make explicit that according to the theory are there are not two kinds of untrue sentences, but three:
1. false sentences,
2. gappy sentences like $\neg Q$ that, like false sentences, it would be wrong to believe,
3. gappy sentences like $Q$ that are "untrue, but not in the bad way". Unlike those in (2) we should believe these despite their being gappy.

Let's sketch the two main types of classical gap theories. And to be clear, gap theories aren't just theories that posit gaps, but rather in particular liar sentences are gappy.

# Kleene-Style Gaps Versus Supervaluation-Style Gaps
---
No one can seriously entertain giving up (T-IN) entirely; that would be compatible with nothing being true, or with only sentences containing the word 'zebra' being true.

## Kleene-style gaps
The most famous theory that keeps (T-OUT) but restricts (T-IN) is the Kripke-Feferman theory KF, mentioned in passing but totally different from the theory KFS.

It's prominent features are
1. that it posits truth-value gaps
2. that it takes truth to obey the strong Kleene truth rules

Hartry focuses on KF as the main exemplar of theories with these features. In proof-theoretic contexts where the discussion of KF most offten occurs, precise details of its formulation matter: for instance, whether principles such as the "no-glut" principle are stated as single axioms or in a weaker schematic form. Such issues won't be of huge relevance in what follows, so we'll be a bit cavalier about the distinction. For the record, the stronger single axiom form is almost always to be preferred, even when the formulations given are in schematic form.

The distinction between KFS and FM is best seen by concentrating on a given starting $\omega$-model M and a given Kleene-based fixed point based on it, and looking what what Hartry calls the *internal theory* and the *external theory* of that fixed point. The internal theory is simply the set of sentences in the fixed point. Since no Kleene-based fixed point contains all instances of excluded middle, no such internal theory can possibly be classical The external theory of a fixed point based on M is the set of sentences that come out true in the classical model obtained from M by letting the extension of 'true' be that fixed point. By construction this is a classical theory.

If a sentence A is in the fixed point, then $T(\langle A \rangle)$ is in both the internal and the external theory. If, on the other hand, A is not in the fixed point, then $\neg T(\langle A\rangle)$ is in the external theory; but it is in the internal theory only if $\neg A$ is in the fixed point. 

KFS is just the common part of the internal theories of all the fixed points; or as we might put it, it is the internal theory *of the fixed points collectively*. Similarly, FM is the common part of the external theories of all the fixed points: it is the external theory of the fixed points collectively.

It's clear that in FM, $\neg T(\langle A \rangle)$ doesn't imply $T(\langle \neg A \rangle)$: consider any sentence that the theory takes to be "gappy", such as $Q$. Though we have:

(COMMUTE) $T(\langle \neg T(\langle A \rangle)\rangle) \leftrightarrow T(\langle T(\langle \neg A \rangle)\rangle)$ 

This is valid in the given interpretation since the sentences named in the outer occurrences of each side of the biconditional , $\neg T(\langle A \rangle)$ and $T(\langle \neg A \rangle)$, though inequivalent in FM are equivalent in KFS; that is, one of these "inner occurrences" is in the fixed point if and only if the other is.

It's time to give more detail about FM theory. We want all the instances of (T-OUT) to be at least theorems, and for expository reasons we'll currently take them as axioms. The axioms should also include the instance of (COMMUTE), but what else does it have? First, it includes all instances of (T-IN) which A either:
1. doesn't contain the predicate 'True', or
2. is of the form 'True(t)'

More instances of (T-IN) follow from these. (T-IN) clearly does not hold in general when A is the negation of a sentence of form "True(t)". For instance,

it is *not* the case that: $\neg T(\langle Q \rangle) \to T(\langle \neg T (\langle Q \rangle)\rangle)$

See the book for compositional rules for connectives.

The Kripke construction of the minimal Kleene fixed point can be used to show that it is consistent, and indeed conservative over $\omega$-models. The presence of the compositional rules, together with the declaration that some sentences are neither true nor false, makes it natural to call FM a "Kleene-style gap theory".

One notable feature of FM, which will distinguish it from the supervalution-style gap theories to follow, is that not all sentences of the form $T(\langle A \lor \neg A \rangle)$ are part of FM; indeed, FM has theorems of form $\neg T(\langle A \lor \neg A\rangle)$, the case where A is the Liar sentence for example. Nonetheless, all instances of excluded middle are part of the theory: the theory asserts "Either A or not A, but it's not the case that $\langle$A or not A$\rangle$ is true" We saw previously that the theory does the same for Liar sentences, that it does this for instances of excluded middle is perhaps a bit more surprising but not drastically different in kind. Admittedly it's odd.

Given that the theory asserts instances of excluded middle that it declares untrue, a verbal question arises: Should we describe the theory as accepting classical logic? Maudlin says no: the theory is one in which not all instances of excluded middle are true, so it's one in which excluded middle is invalid, so it is not a classical theory.  Admittedly, the theory employs classical reasoning, and regards it as fully legitimate to do so (and in some sense incorrect not to do so). But according to Maudlin, this just shows that we need to make a sharp distinction between *permissible* reasoning and *valid* reasoning: employing excluded middle is permissible but invalid.  Hartry prefers an alternative description: the theory, since it employs classical logic counts as a classical theory, on which excluded middle is valid; but it takes some valid sentences not to be true. Whether you take Mauldin's terminology or Hartry's isn't of importance

I'll skip the supervaluationist section

# Declaring One's Axioms Untrue
---
A curious consequence of adopting the instances of (T-OUT) as axioms in a classical theory is that this not only results in the theory declaring A, but $\langle$A$\rangle$ for certain degenerate sentences A like the liar sentence Q. It also results in the theory declaring this for certain instances of (T-OUT) itself.

In the usual such theories we get this result for the instantiation of (T-OUT) by the Liar sentence: we can prove

1. $\neg T[\langle T(\langle Q \rangle) \to Q \rangle]$ 

For instance, in a theory based on a reasonable fixed point construction, whether Kleene or supervaluational, $T(\langle Q \rangle) \to Q$ will never be in a fixed point, and so (1) will be part of the external theory. This result holds for just about any Kleene theory. It also holds in *most* supervaluation-style theories. For some it may not, but something similar does:

There's a more complicated sentence Z that yields an instance of (T-OUT) whose untruth we can prove; that is, we can prove

1. $\neg T[\langle T(\langle Z \rangle) \to Z \rangle]$

That is the content of **Montague's Theorem**. Consider any theory that
1. contains (T-OUT)
2. proves $T(\langle A \rangle)$ whenever A is a classical logical truth or a theorem of arithmetic
3. asserts that modus ponens is truth-preserving.
Then for a certain sentence Z, the theory proves 1, even though the sentence that (1) asserts not to be true is an axiom of the theory.

It might be protested that it isn't necessary for a gap theorist to take all the instances of (T-OUT) as axioms: if one instead takes just the instances for atomic A together with the "no-glut" schema

(NG) $T(\langle \neg A \rangle) \to \neg T(\langle A \rangle)$

as axiomatic, the other instances of (T-OUT) can be derived by an obvious induction, using the other principles of the theory. But this doesn't change the underlying point: the theory will still declare some of its axioms untrue. In any case, I think the focus on (T-OUT) is justified since whether or not its officially an axiom schema, it's central to the intuitive idea of gap theory; declaring instances of it untrue seems more counterintuitive then declaring an "unintended theorem" like the Liar sentence untrue..

Its highly peculiar to adopt a theory that directly or indirectly postulates all instances of (T-OUT) when one is then going to go on to declare some of these instances untrue. I submit that if we really were forced to declare some of the instances of (T-OUT) untrue, that should lead us to restrict (T-OUT).

The next two sections we'll discuss one attempt to resist this conclusion, and in the one after that an attempt to take the conclusion to heart. Both make use of a very controversial notion of proposition and Hartry argues both attempts are misguided and serve to muddy the waters. Neither addresses Maudlin's defense of the idea that a theory should declare itself untrue, which does not turn at all on propositionalist obscurantism though it does get into heavy-duty metaphysics. In the final section, we'll make an effort to buttress the view that we should not accept theories that declare themselves untrue.