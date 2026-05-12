# The Barcan Formula
---

the metaphysical dispute between contingentism and necessitism is intimately connected with technical issues in QML over two principles known as the Barcan Formula and its converse. Those principles interpreted in the relevant way are accepted by necessists and rejected by contingentists. In some logical settings, each of them is equivalent to the central necessitist claim that necessarily everything is necessarily something.

The Barcan formula and its converse appeared in the context of logical positivism, where logic and metaphysics were considered disjoint. The former as meaningful but analytic, the latter as not even being meaningful.

QML is a combination of quantified logic and modal logic. It therefore inherits any philosophical problems raised by the logic of a quantified logic and also any philosophical problems raised by the logic of a modal language. It also raises new problems for its own, concerning the interaction between the quantifiers and the modal operators. The Barcan formula and its converse are principles about that interaction.

The first publifcation of a fully formal system of QML comes out in March 1946 by Ruth Barcan. She takes the preferred axiomatic system S2 of unquantified modal logic from the seminal text Symbolic Logic by C.I. Lewis and C.H. Langford and expands the language. Her methodology is austerely snytactic, she proposes no semantics for the formal language.

Unlike contemporary modal logicians, who normally take <> or [] as their primitive modal operator, Marcus follows Lewis and Langford in taking as primitive a symbol for strict implication, in contemporary symbols it's equivalent to [](A -> B). Informally: whereas every falsehood materially implies everything, no contingent falsehood strictly implies everything (although every necessary falsehood does); whereas every truth is materially implied by everything, no contingent truth is strictly implied by everything (although every necessary truth is).

There is one distinctive schema for the interaction of modal operators and quantifiers:

1. [](<>Ex:v A -> Ex:v<>A)

An instance of (1) says that necessarily, if there could have been an individual that satisfied the condition, then there is an individual that could have satisfied the condition. As with other axiom schemas and rules of inference, no attempt is made to justify (1). It's main role in the paper is to permit the derivation of the result of putting strict implication for material implication in the standard non-modal principle Ax:v (A -> B) -> (Ax:v A -> Ax:v B).


The phrase 'the Barcan formula' has come to be used not for (1) but for its unnecessitated variant:

BF: <>Ex:v A -> Ex:v <>A 

BF is a schema with infinitely many formulas as its instances. We can derive a logical equivalent of BF by contraposing it and using the duality of <> with [] and Ex with Ax.

BF': Ax:v []A -> []Ax:v A

In english: if everything necessarily satisfies a condition, then necessarily everything satisfies the condition. BF' is somtimes called the Barcan formula as well since on standard assumptions if BF is a valid schema then BF' is a valid schema. The converse also holds as well. Since BF is easier to engage with than BF', it will be taken as the canonical form.

In contemporary systems of QML any modal closure of a theorem is itself a theorem, where a modal closure of a formula B is any formula that results from prefixing B with a finite string of universal quantifiers and necessity operators in any order. For example, any instance of (1) is a modal closure of the corrresponding instance of BF. In such a system, every instance of BF is a theorem only if every instance of (1) is a theorem. So, BF is derivable from (1) in the system of the 1946 paper.

Formally contingentism is consistent even with full BF. Without auxiliary assumptions, one cannot deduce from full BF the formalization of the defining necessitist claim that necessarily everything is necessarily something, whose negation is the defining contingent claim.

In practice, however, almost all contingentists reject BF and a fortiori (1) and full BF, when Ex is read as an unrestricted individial quantifier and <> as an oeprator of metaphyiscal possibility. According to them there could have been something that is actually nothing because, for example, there could have been more things than there actually are. However, everyone agrees that there is not smoething that could have been actually nothing, where actually (@) is a rigidifying operator that always returns the semantic evaluation to the world of utterance. In symbols, BF has this instance:

2. <>Ex:x @~Ex:y x=y -> Ex:x <>@~Ex:y x=y

Since the rigidifying effect of @ makes <> redundant in <>@, the consequent is equivalent to Ex:x @~Ex:y x=y  whch has the same truth value as Ex:x ~Ex:y x = y because @ makes no difference when not in the scope of another modal operator; but that is inconsistent in first-order logic with identity. Thus the consequent of (2) is clearly false, whereas its antecedent is by normal contingentist lights obviously true.

Strictly speaking (2) is not an instance of BF in the language of Marcus's original system, which does not have the @ operator. But that doesn't matter, we can achieve the same effect by using @~Ex:y x =y informally to interpret the atomic 1-place predicate F in this instance of BF:

3. <>Ex:x Fx -> Ex:x <>Fx

read F as "is a child of John F. Kennedy and Marilyn Monroe". On this reading, the antecedent is obviously true. How does one verify the consequent? Contingentists can appeal to the plausible doctrine of the essentiality of origins to argue that anyone who is not actually their child could not have been their child. They can insist that reading falsifies the consequent of 3. They are simpler examples against Marcus's original axiom schema (1), and therefore against full BF. For any instance, they can substitute the open formula x=y for A

4. [](<>EXx x=y -> EXx <>x=y)

As value of the variable y, assign any ordinary material object: say, the mountain K2. Then (4) in effect says that necessarily, if there could have been K2 then there is something that could have been K2. Contingentists respond that this scenario is possible: nothing is K2 so nothing even could have been K2 But still there could have been K2.

Formally: from the obvious truth that EXx x=y, they argue to []<>EXx x=y by the principle that the actual is necessarily possible, and from there to []EXx <>x=y by (4) and standard modal reasoning; but []EXx <>x=y is obviously false by normal contingentist lights. It's not necessary for there to be something that could have been K2; for necessarily whatever could have been K2 is K2 and its not necessary for there to be K2. Thus, (4) is false.

How does the necessitist react? Take (3) first, When F is read as "is actually nothing", they reject the antecedent on the grounds that there could not have been something that is actually nothing. When F is read as "is a child of John F. Kennedy and Marilyn Monroe", they accept both the antecedent and the consequent, arguing that the latter is verified by a merely possible child, something that is not but could have been concrete.

In the case of (4) they accept []EXx x=y and therefore []EXx <>x=y for any value of y. More generally, necessitsts accept every instance of BF on the grounds that if a condition could have been satisfied it would have been satisfied by something that was necessarily something, and so is actually something, thus there actually is something that satisfies the condition. Indeed, since necessitists attribute universal and necessary force to such reasoning, they accept every instance of full BF, and so every instance of Marcus's axiom schema (1).

Thus, necessitists and contingentists divide over the Barcan formula. 
