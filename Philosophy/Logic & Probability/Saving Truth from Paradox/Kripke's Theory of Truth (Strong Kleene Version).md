The most influential paper on truth since Tarski is Saul Kripke's paper "Outline of a Theory of Truth".

The paper beings with a point alluded to in [[Self-Reference and Tarski's Theorem]]. It's extremely easy to enter the domain of paradoxes inadvertently, and this seems to make the Tarskian hierarchical approach inadequate to our needs. Kripke considers the example of Jones who says

1. Most of Nixon's assertions about Watergate are untrue.

This seems like the sort of thing people often say. But, Kripke says, suppose one of the things Nixon said was

2. Everything Jones says about Watergate is true.

and that everything else Nixon said about Watergate is evenly divided between the unproblematically true and the unproblematically false. Then it looks like Jones' assertion (1) is true if and only if Nixon's assertion (2) is untrue, and Nixon's assertion (2) is untrue if and only if Jones' assertion (1) is untrue. So Jones' assertion is true if and only if it is untrue and we have a contradiction.

To guard against the possibility of paradox, Jones might assert 

1. Most of Nixon's assertions about Watergate are not $\text{true}_0$.

This would block the paradox, but wouldn't be true of what Jones wanted to say: Jones might have known that Nixon made many claims about Watergate that involved the notion of truth unproblematically, and meant to make a far stropnger statement than would be made if these were counted as trivially untrue. What Jones must do to avoid this problem is to choose a subscript higher than all the subscripts on 'true' employed in Nixon's utterances. But Jones might now know which subscripts Nixon employed, and he if chooses one that's too low then his statement would not have the content he wanted it to have,

If we were to speak in accord with the Tarskain theory, there would be pressure on ach of us to choose very high subscripts: if we don't there will be a high risk that what we say will fall short of what we hope to say. But in raising the subscripts on our own assertions we make it harder for others to fulfill their intentions.

Nixon and Dean each try to say that nothing the other says is true, each trying to include the other's assertions within the scope of his own. At most one of them can succeed, since success requires using a higher subscript than the other guy uses.

The problem Kripke observes is that one the Tarskain theory each utterance has a pre-assigned level.  One might imagine a theory that takes 'true' to work indexically. A theory on which the tarskian indices still appear but where there is in addition an unsubscripted term 'true' whose "extension" in a given context is always the same as one of the unsubscripted predicates, but a difference one in each context. This approach is suggested in Burge 1979.

Kripke gives a theory that treats 'true' as a single non-indexical term, governed by precise semantic rules; to the extent that the theory contains an analog of Tarski's notion of level, it includes a precise account of how such levels are assigned. And the theory fulfulls the intuitive idea that "utterances should seek their own levels".

Kripke actually gives more than one such theory. We'll focus on versions based on what is called *strong Kleene semantics* and for simplicity, we'll mostly focus on what are called *minimal fixed points* in such a semantics. Even with the restrictions, there is more than one Kripkean theory.

# The Kripke Construction for Restricted Languages
---
The focus in this section will be on adding a truth predicate to a language $\mathcal{L}_0$ that is expressively weak enough for Tarskian truth-in-$\mathcal{L}_0$ to be definable in set-theoretic terms. $\mathcal{L}_0$ will be rich enough to express elementary arithmetic is that self-referential constructions can be performed with it; for related reasons, it needs to have the means of expressing elementary facts about finite sequences. We can allow it to have the means of expressing non-mathematical facts. We can also allow it to express more mathematics such as the theory of real numbers; but we must deny it the ability to speak of arbitrary sets, since that would preclude truth-in-$\mathcal{L}_0$ from being set-theoretically definable. In short: quantifiers in the language must be restricted so as to range only over the members of some set U.

The idea will be to expand $\mathcal{L}_0$ to a new language $\mathcal{L}_0^+$ just like $\mathcal{L}_0$ with a new 1-place predicate 'True'. 'True' is a primitive of $\mathcal{L}_0^+$; what's going to be explicitly defined in this term of $\mathcal{L}_0^+$ but rather a term in the set-theoretic metalanguage $\text{ML}_0^+$ used to describe $\mathcal{L}_0^+$. Kripke uses the term 'True' for that metalinguistic term too, a source of possible confusion. To avoid that, we'll start out using the colorless term 'has semantic value 1' for the metalinguistic term to be defined.

Suppose that the original $\mathcal{L}_0$ is a first order language with names, predicates, and function symbols, and that $\mathcal{L}_0^+$ results from it by adding a new 1-place predicate 'True'. We imagine that the variables range over the members of a set U, that each name names an object in U, and that each $n$-place function symbol corresponds to an $n$-place operation on U. Just as in original Tarskain theory, these determine a denotation for each singular term relative to each assignment function; where an assignment function is a function assigning members of U to the variables of $\mathcal{L}_0$.

Each $n$-place predicate of the original language $\mathcal{L}_0$ has a set of n-tuples of members of U as its extension. We do not start out by assigning 'True' any such permanent extension; instead, we consider various temporary quasi-extensions for it. Each temporary quasi-extension X is a subset of U satisfying two conditions:
1. all of the members of X are (Godel numbers of) sentences
2. No sentence and its negation are both in X

We let $X^\text{neg}$ consist of everything in U that is either not a sentence or else the negation of a member  of X. By condition (2) the set is disjoint with X. Look at the book for assignments of values relative to an assignment unction s and a temporary quasi-extension X for 'True.

Because X and $X^\text{neg}$ need not be exhaustive, formulas sometimes will neither have a value 1 or 0 relative to a given assignment function and temporary quasi-extension X.  It's convenient to say such formulas get value 1/2 relative to an assignment function and quasi-extension.

The assignment function is drops out as irrelevant in cases of sentences (formulas with no free variables). So for sentences we can speak just of semantic value relative to X. 

Here is the heart of Kripke theory: the choice of a permanent quasi-extension. We'll start with the simplest case, where we take this to be "the minimal fixed point". Let $X_0$ be the empty set. Let $X_1$ be the set of sentences that have value 1 relative to $X_0$. Generally, for any ordinal $\alpha$, let $X_{\alpha + 1}$ be the set of sentences that have value 1 relative to $X_\alpha$. For a limit ordinal $\lambda$, let $X_\lambda$ be the set of sentences that have value 1 relative to some $X_\beta$ where $\beta < \lambda$. It's easy to see that if a sentence is in $X_\alpha$, it is also in $X_\beta$ for any $\beta > \alpha$. (The *Roach Motel property*: once a sentence checks in, it never checks out.) But the $X_{\alpha^S}$ can't keep growing forever: there is a fixed cardinality C of the sentences in the language, so there must be an ordinal $\beta$ with no more than C predecessors for which $X_{\beta + 1} = X_{\beta}$. This is the minimal fixed point. (See footnote for more general treatment that adds a 2-place predicate of 'True-of' rather than 1-place predicate 'True'. Such modification simply modifies clauses governing quasi-extensions in obvious way.)

Regard a sentence as having value 1 *tout court* if it has value 1 in the minimal fixed point; similarly for value 0 and value 1/2. By the fixed point property:

(\*) The sentences with value 1 in the fixed point are precisely the members of the fixed point. (And the sentence with value 0 in the fixed point are precisely the sentences whose negations are in the fixed point.)

Some sentences clearly will have value 1/2; an example is any Liar sentence (i.e., any sentence Q for which $\vdash Q \leftrightarrow \neg \text{True}(\langle Q \rangle)$), as one can easily check. Note the following three properties of this construction.

1. Every true sentence of the ground language $\mathcal{L}_0$ gets value 1; every false sentence gets value 0. The reason: every true sentence of $\mathcal{L}_0$ is already in $X_1$, and every false sentence has its negation already in $X_1$.
2. For any sentence A (of $\mathcal{L}_0^+$), A has a value 1 iff True($\langle A \rangle$) has value 1, and analogously for values 0 and 1/2. (The reason: by clause 2, True($\langle A \rangle$) has value 1 in the fixed point if and only if A is in the fixed point, and has value 0 in the fixed point if and only if $\neg A$ is in the fixed point; so the result follows from (\*) ).
3. For any sentences A, W, and X, if A is a sub-sentence of W and Z is just like W except with an occurrence of A replaced True($\langle A \rangle$), then W has value 1 iff Z has value 1. This follows from (2) by induction on the complexity of the embedding of the occurence of A in W.

Reflection on these properties and on the facts that our assignments of values five having value 1 compositional features analogous to those we might expect for truth, might tempt one to identify having value 1 with being true, for sentences of $\mathcal{L}_0^+$. This is what Kripke has in mind when he speaks of having defined truth for $\mathcal{L}_0^+$. This identification is a bad one.

# The Kripke Construction for Unrestricted Languages
---
An initial point about Kripke's identification of being true with having semantic value 1 is it looks quite implausible in the case of languages in which the quantifiers aren't sufficiently restricted. Let's see why.

In the construction given, we consider only the case where the range of the quantifiers in the ground language $\mathcal{L}_0$ is a set. This ruled out applying the construction to the case of set theory: for the quantifiers of set theory range over all sets, and there is not set of all sets.

We restricted discussion ot the case where the range of quantifiers in the ground language is a set because if not, one couldn't turn the implicit definition of the single X, e..g the empty set into an explicit definition. So without being able to to define $X_0$ in the inductive specification of the minimal fixed point, the inductive definition of the minimal fixed point couldn't have gotten off the ground. And so defining 'has semantic value 1' as meaning 'has semantic value 1 in the minimal fixed point' could not be done.

If we misinterpret the quantifiers as restricted we can have the inductive definition. We can easily do this in fact, we can interpret them as ranging only over the members of some set, even when in reality they don't When we do that the construction proceeds without a hitch. The cost is that the construction no longer has property (1): semantic value 1 no longer coincides with truth for sentences in the ground language.

A better way to put this matter is we now need to introduce an additional variable in our account of semantic value, a variable U for the range of quantifiers. We regard U as a free variable throughout the inductive definition: so it is an inductive definition of 'A has semantic value 1 relative to s, X, and U', where s is requited to have only objects in U in its range. The definition of 'minimal fixed point' then becomes a definition of 'minimal fixed point relative to U', and the definition of 'semantic value' then becomes a definition of 'semantic value relative to U'.

The key point is that the semantic value of a sentence is always relative to a choice of a set U that restricts the quantifiers. Given this, there should be no temptation to think of having semantic value 1 relative to some given U as necessarily coinciding with truth.

Often we can specify some U for which the impact on property (1) is fairly minimal. For instance, suppose that the background set theory in which we are working is Zermelo-Fraenkel set theory, with axiom of choice plus the postulate of inaccessible cardinals. Let us choose as a value of U (the set we 'misinterpret the quantifiers as restricted to') the set of all sets of rank less than the smallest inaccessible cardinal. If we do this, for a great many assertions in the language of set theory, they get semantic value 1 relative to this U if and only if they are true. In particular, all the axioms of Zermelo-Fraenkel set theory with choice get semantic value 1 relative to this U. This coincidence of truth with semantic value 1 relative to this U is not perfect, for the restriction "falsifies" the postulate of inaccessible cardinals. In other words, that postulate gets semantic  value 0 relative to this U, even though it;s true. Note that the postulate in question doesn't itself contain 'true': truth diverges from semantic value 1 (relative to this choice of U) even for the 'true'-free sentences of the language.

This is not an accident of the example. There is simply no way to define a set U for which having semantic value 1 relative to U coincides with truth. This is a consequence of Tarski's undefinability theorem.

What then are we to make of Kripke's claim to have shown to define truth for languages with a truth predicate? He does not explicitly confine his claim to languages with only explicitly restricted quantifiers, but perhaps he thought that such a restriction was so obviously needed as to not have to be made explicit.

Or maybe he thought: even though you can't define truth for expanded set theory  (set theory plus truth predicate) *within set theory*, still an obvious modification of the procedure would define truth for expanded set theory within a language C that quantifiers over proper classes as well as sets. This of course just raises the question of defining truth for the language C. That we can sensibly talk of such a never ending hierarchy is the contentious assumption already mentioned in [[Self-Reference and Tarski's Theorem]] section concerning set-theoretic truth. If Kripke intends his remarks to apply without restriction then it must depend on this assumption.

# Conservativeness
---
Here, we'll argue even in the case of restricted languages where an "absolute" definition of semantic value is possible, we should not equate semantic value 1 with truth, and so should reject Kripke's claims to have defined truth. And further, we'll address the puzzle: If semantic value 1 isn't truth, then of what possible value is his construction?

The answer is that Kripke's construction implicitly gives a non-classical model theory for a language with a truth-predicate; and a large part of the value of this model theory is that it shows the consistency of a certain theory of truth which is "built into the fixed points". The two key features of the theory are:
1. that it is based on a certain logic K3 appropriate to the Kleene semantics (a logic that does not include the law of excluded middle)
2. and that it contains an inferential rule (the intersubstitutivity principle) that allows us to substitute occurrences of True($\langle A \rangle$) for occurrences of A, or vice versa, in any non-intensional context when A is a sentence. (We should also take this theory to include basic principles of syntax. This background syntax is assumed to include all instances of the LEM that are in the syntactic language)

This Kripkean theory is standardly called KFS and I will use that name. There is room for small variations over what KFS is taken to include: e.g. over exactly how powerful the background syntax we build in, or whether we take it to be part of the theory that non-sentences are never true, etc. but for current purposes such variants wont matte.r

What's crucial for what follows is just that the theory KFS includes (1) and (2) (and that it not include anything, such as the law of excluded middle, that would prevent the Kripke construction from providing the desired consistency proof).

The idea of the consistency proof is that the inferences allowed in KFS never lead from premises in the fixed point to a conclusion not in the fixed point. Since contradictions can never be in any fixed points, the rules of KFS can never lead to inconsistency.

Kripke's construction shows more than consistency; it shows that KFS has an important property of conservativeness (it is "conservative" over $\omega$-models).

Let $\mathcal{L}_0$ be any language in which arithmetic (or protosyntax) can be developed; its quantifiers needn't be restricted to the members of some set, though they may be. Let M be any classical $\omega$-model of $\mathcal{L}_0$. That is, its arithmetic (protosyntax portion) is an $\omega$-model.  This means, for arithgmetic, that for each thing $n$ that satisfies 'natural number' in the model, there are only finitely many things in the model that satisfy 'natural number that precedes n'. For protosyntax it means that for each thing e in the model that satisfes 'expression of $\mathcal{L}$' there are only finitely many things in the model that satisfy 'expression that is part of e'. It's evident that our interest in the theory of truth should be focused on $\omega$-models.

The conservativeness property is this: If we do the Kripke construction for $\mathcal{L}_0^+$ starting from M, we'll get a 3-valued model of the language $\mathcal{L}_0^+$ that validates the theory KFS and that is exactly like M in its 'True'-free part. This means that we can add that theory of truth to any theory in $\mathcal{L}_0$ that one likes and preserve consistency in $\omega$-logic: if the original 'true'-free theory in $\mathcal{L}_0$ is consistent in $\omega$-logic, so is the theory that results by ading the theory of truth to it.

Conservativeness in the $\omega$-logic sense just sketched is obviously a highly desirable feature of a theory of truth. Bare consistency isn't enough, a theory of truth might be consistent and yet entail things that no theory of truth should entail! Conseravtiveness entails a very strong consistency property: the theory of truth is not only consistent, but consistent (in $\omega$-logic) with any theory not containing 'true' that is itself consistent in $\omega$-logic..

Given the difficulties of finding theories of truth that consistently (let alone conservatively) deal with paradoxes, I think a construction that yields a conservativeness proof is valuable. Hartry is not satisfied with the logic that Kripke's construction shows to be conservative, but his construction will be a paradigm for more complicated constructions.

Conservativeness is a generalization of consistency: it means "can be consistently added to any consistent theory" taking consistent in each occurrence to mean consistent in $\omega$-logic.

Kripke's construction has another value besides proving conservativeness. It also provides an easy way to figure out which inferences involving truth are legitimate in the truth theory provided by the construction. This a significant fact. For KFS is a non-classical theory (a *paracomplete* theory to be specific as LEM isn't valid). Those of us who have been trained in classical logic find it initially difficult to figure out what reasoning is legitimate in such a non-classical logic and what isn't. Using Kripke's construction, we can use easy classical reasoning to determine the answer.

# Does Truth Coincide With Semantic Value 1 Even For Restricted Languages?
---
For restricted languages we can at least define 'has semantic value 1' without relativizing the latter to an unintended domain, so it might make sense to contemplate identifying truth with having valuw 1.

This is a bad idea. For the 'external' notion of having semantic value 1 is very unlike the 'internal' notion used in the language $\mathcal{L}_0^+$, and the theory of external notion (which will be called FM) is very different from the theory KFS of the internal notion.

The internal notion of truth is primarily important; the external notion should be viewed largely as a technical device, used 
1. as an aid to help the logician trained in classical logic to figure out what reasoning is valid in the internal theory
2. as the basis for a conservativeness proof

What does Hartry mean by saying the external notion of having semantic value 1 is unlike the internal notion? Consider:
1. It's easy to see that in the Kripke construction, a Liar sentence Q can't have value 1 (or 0, it must have 1/2). But if it doesn't have value 1, and value 1 is truth, then it isn't true. The claim $\neg \text{True}(\langle Q \rangle)$ that Q isn't true would thus become part of the theory FM that identifies truth with having semantic value 1; but this claim does not appear in the fixed point. There's an unsatisfying divergence between the assertions of the theory FM and the contents of the fixed point. This is disconcerting because the theory FM declares anything not in the fixed point to be untrue. So the claim that the Liar sentence is not true, which is part of the theory FM, is delcared untrue by that theory. The theory delcares itself untrue. This isn't inconsistent, but it's a serious anomaly.
2. see the book

A specific version of the theory FM that results from identifying truth with having value 1 is the Kleene-based Kripke theory called KS. We use the name FM instead of KS because the similarity in the acronyms is confusing.


The odd features mentioned are not part of KFS. KFS consists only of sentences that are in the fixed point. Since, some instances of excluded middle are not contained in the fixed point, they are not part of the theory: the theory is 'paracomplete'.

An additional difference, FM postulates truth value gaps (sentences neither true nor false): any sentence that gets value 1/2 in the minimal fixed point is declared to be neither true nor false. KFS on the other hand asserts neither that there are truth value gaps nor that there aren't.

To beclear, there are "semantic value gaps" in that there are sentences with neither value 1 nor value 0= in the classical semantics for the theory. But failure to have semantic value 1 or 0 is not failure to be true or false.

The theory accepts neither the existence or non-existence of truth value gluts, despite a misguided view about KFS being it holds there are no truth value gluts.

In fact, gaps and gluts as concepts are logically equivalent in KFS. See book for proof.

What then is the relation between truth value and semantic value for KFS? In the case of restricted theories (ones in which we have an unrelativized notion of semantic value), we can say this: having semantic value 1 is sufficient for being true, and having semantic value 0 is sufficient for being false. Sentences with semantic value 1/2 cannot be called true or not true, or false or not false. We can't say that they're "gappy" and we can't say that they are "glutty". Our inability to say these things can't be attributed to ignorance, for we don't accept that there is a truth about the matter. This isn't to say we think there is no truth about the matter: we don't think there is and we don't think there isn't. And we don't think there either is or isn't. Paracompleteness runs deep.

# The Weakness of Kripke's Construction
---
KFS does not seem adequate. We'll mention three reasons.

The first is that the theory is too weak to carry out ordinary reasoning. The most notable weakness is that it does not contain a decent conditional or biconditional. The standard material conditional is passable as a condition the presence of LEM, but it completely inadequate without LEM: we wouldn't get elementary laws of the condition like $A \rightarrow A$. The lack of a conditional crippled ordinary reasoning.

The second problem is that though the theory validates the intersubstitutivity of True($\langle A \rangle$) with A, it does not validate the truth schema. This is obvious: each direction of the truth schema is equivalent to $A \rightarrow A$.

The second problem may not be independent of the first. There's dispute about this.

The third problem involves expressive weakness: there are things that we would like to say about the Liar sentence that we can't express in the language. We have no way to express a determinately true operator so no way to express the Liar sentence isn't determinately true.

# Acceptance and Rejection in KFS
---
We must not overstate the third problem, even within the KFS it make sense to reject the Liar sentence: an advocate of KFS can and should distinguish between rejection and acceptance of the negation.

Rejection should involve at the very least a commitment to not accept. Continue reading the book if interewted in ftureu