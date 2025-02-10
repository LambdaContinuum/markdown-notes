# Language and Logic
---
The formal language of the system accommodates quantification over properties, and property-expressions that can occupy term and predicate positions. Consider, for example, the '$G(x) \iff \forall \phi [P(\phi) \to \phi(x)]$', the so called definition of '$G$': The property-variable '$\phi$' stands in a term position in '$P(\phi)$' which says $\phi$ is P ($\phi$ is positive), and '$\phi$' stands in the predicate position in '$\phi(x)$' which says that x is, or has, $\phi$.

Similarly, 'G' occupies a predicate position '$G(x)$' which says that x is God-like, whereas it occupies a term position in $'P(G)'$ that says God-likeness is a positive property. 'P' is for a property of properties. It occupies only predicate positions, never term positions.

The language features sorted quantification. Variables x and y range over everything. The variables $\phi$ and $\psi$ range over only properties. 

There is in the language an abstraction operator for a kind of property expression; these occur sometimes in its proof though never in axioms, definitions, or theorems. Godel operates with a generous notion of a property that for one important thing does not make redundant the description 'possibly instantiated property'.

Both $\hat{x}[x = x]$ and $\hat{x}[x \neq x]$ for the properties of self-identicalness and non-self-identicalness occur in our texts. The scheme $\neg \phi = \hat{x}[\neg \phi (x)]$  is given without comment, evidently as an explanation of notation for properties that are 'the complements' of properties.

Sobel adds the scheme $\neg \phi = \hat{x}[(\neg\phi) x]$, to say that a thing has the negation of a property if and only if it does not have this property this way.

Property expressions occupy both term and predicate positions, so the negation sign applies sometimes to formulas and sometimes to property expressions.

One gathers that in general $\neg\hat{x}[\phi] = \hat{x}[\neg \phi(x)]$. The property identity $\neg [x = x] = \hat{x}[x \neq x]$ plays a role in the proof of Theorem 1.

The system's can be third order (third 'Russell-order' or 'Church-level' for there is in the language the property of properties symbol 'P) quantified S5-modal with identity and abstraction. Quantification into modal-contexts is countenanced, but every case implicit in our texts of 'quantification in' is of '*property* quantification in'.

'Closed' property-terms of the system name properties, which are identified with functions from worlds to sets of things; intuitively, a 'closed' property-term names the function whose value for a world is a set of things that at the world has the property that the look-alike property predicate signifies. Properties, that is, these functions, exist in all worlds, so that subsets of world-domains of properties are the same. This makes property quantification into modal contexts unproblematic. The logic of the system, on the other hand, is not elementary and, if pressed, may prove problematic.

# Axioms, Definitions, and Two Theorems
---
## *Positive properties*
$P$ is the primitive of the theory. It abbreviates sometimes 'positiveness'  and sometimes 'is positive'. Its intended interpretation must be gleaned from cryptic explanatory sentence fragments in Godel's hand.

> Positive means positive in the moral aesthetic sense (independently of the accidental structure of the world). Only then \[is/are?] the ax. \[axiom/axioms? – the reference may be specifically to something equivalent to Axiom 2, given below, or, more likely I think, to all the axioms] true.

For relevance to the object of proving the existence of *God*, the moral aesthetic sense is useful.

Godel was inclined to a Platonic equation of goodness (moral/aesthetic) with being (pure, without privation). Notes of which are prominent in Leibniz's philosophy. ("Perfection ... is nothing else but  ... quantity of essence).

His theory would be served by this combination. It can use a moral aesthetic interpretation of 'positive' for spiritual and religious *relevance*, while, for the *prima facie* truth of some of its axiom, Godel writes, it can use a logical/ontological interpretation of this primitive.

It's a another matter whether he can *have* such a combination. He doesn't seem to have had in mind a settled sense for his primitive with which he was satisfied. It's perhaps best to assume that he thought of his ontological argument, not as a conclusive proof of the existence of God, but as an attempt at a reconstruction of Leibniz's argument.

Godel hoped that his reconstruction could be turned into a conclusive proof of God's existence. A proof in search of an interpretation.

## *Initial axioms and a theorem*
It's announced that, of every property and its negation, exactly one is positive, Axiom 1: $$P(\neg\phi) \iff \neg P(\phi)$$
which is equivalent to $$[P(\neg \phi) \lor P(\phi)] \land \neg [P(\neg \phi) \land P(\phi)]$$
and short for $$\Box\forall \phi[P(\neg \phi) \iff \neg P(\phi)]$$
(Axioms, definitions, theorems, and consequences thereof are all implicitly 'necessities of universal closure). It isn't clear why, on either an axiological or logical interpretation of 'positive', that this should be so. That $P(\neg \phi) \lor P(\phi)$ challenges even the sympathetic reader on axiological interpretations of 'positive'., though not on Godel's logical interpretation.

It is next said that every property necessarily contained in a positive property is itself a positive property: $$P(\phi) \land \Box\forall x[\phi(x) \to \psi(x)] \to P(\psi)$$
On an axiological interpretation, if there is a positive property, then every necessarily universal property such as being self-identical and being either red or not red, is a positive property.

Now comes the theorem that each positive property is possibly instantiated: $$P(\phi) \to \Diamond\exists x\phi(x)$$
The argument given for this theorem assumes that
1. $P(\phi)$
2. $\neg\Diamond \exists x \phi(x)$

for an indirect proof. Look at Sobel's book if you want to see the proof.

It's settled by a definition that "x is God-like if it possesses all positive propertes", Def G: $$G(x) \iff \forall\phi[P(\phi) \to \phi(x)]$$
Next comes: $$P(G)$$
an axiom stating that God is positive. Any such property ought also itself be positive. 

It is stated immediately after Axiom 3 that the possibility of a God-like being, $\Diamond \exists x G(x)$, holds as a corollary. This possibility is an easy consequence of axiom 3 and theorem 1.

Axiom 3 is not used in the proof of Theorem 2 and is used just once in the proof of Theorem 3. It is used there with Theorem 1 to infer that God-likeness is possibly instantiated, $\Diamond \exists x G(x)$, which possibility could, for all that $P(G)$ contributes, have been assumed instead as an axiom. Indeed, given Axioms 1 and 2, Def G, and Axiom 4 below, the possibility of God-likeness and its positiveness are equivalent. From those four principles: $$\Diamond\exists x G(x) \iff P(G)$$
is derivable.

Axiom 2 and 3 generate a problem for disjunctive properties. Let Devil-likeness be having all properties that are *not* positive. From Axioms 2 and 3, it follows that being either Godlike or Devil-like is positive, $P(G \lor D)$. The difficulty has been said to be that the proposition that this disjunctive property is positive in either a moral/aesthetic or a logical/ontological sense appears counter-intuitive.

The difficulty is worse. There is *prima facie* no more reason for saying that this disjunctive property is positive than there is for saying that it isn't positive; it is entailed by a property that is positive according to Axiom 3, and it is entailed by a property that is presumably 'equally negative'. Axioms 2 and 3 at least challenge any interpretation of 'positive' that can serve Godel's purpose.

Being a positive property is logical, hence, necessary. This is axiom 4: $$P(\phi) \to \Box P(\phi)$$
Godel justifies axiom 4 "because it follows from the nature of the property".

## *Essences and necessary existence*
In Godel's theory an *essence* of an individual is a property of it that entails each of its properties: $$\phi \textbf{ Ess }x \iff \phi(x) \land \forall \psi[\psi (x) \to \Box \forall y[\phi(y) \to \psi(y)]]$$
since, if $\phi$ is an essence of x, x has $\phi$; $\phi$ is possibly instantiated and does not entail every property, rather, it entails every property of x, and only these properties. Since for every property $\psi$, x has either $\psi$ or $\neg \psi$, Essences are 'maximally consistent properties'. It's shown that any essence of any God-like individual is God-likeness: $$G(x) \to G \textbf{ Ess } x$$
**Necessary existence** is defined in the system in terms of essences. It is explained that $$NE(x) \iff \forall \phi[\phi \textbf{ Ess }x \to \Box\exists\phi(x)]$$
If $\phi$ has an essence of x, and x has Necessary existence, then it is necessary that x itself exists and has $\phi$.

If $x$ does not have an essence, then x has Necessary existence. 

The point intended is that, for an x that has an essence, NE(x) ‘means’ or implies that x necessarily exists. To make sure that there are not essenceless necessary existents that do not necessarily exist

One could either lay it down that every existent has an essence or modify Def NE along the lines of Def Ess by requiring for NE(x) that $\exists \phi\phi \textbf{ Ess } x$.

Necessary existence is, by the last axiom, ruled a positive property as Anselmians would have it be: $$P(NE)$$
# That it is Necessary that there is a God-like Being.
---
Here is the theorem and proof as they stand in Scott's notes: $$\begin{align}\text{Theorem 3. }\Box\exists x G(x)\\
G(x)\to NE(x) \land G \textbf{ Ess }x \to \Box\exists xG(x)\\
\exists xG(x) \to \Box \exists xG(x)\\
\Diamond \exists x G(x) \to \Diamond\Box\exists x G(x) \to \Box \exists x G(x)\\
\text{But } \Diamond\exists x G(x) \text{ by Theorem 1.}\\
\Box \exists x G(x) \text{ Q.E.D}\end{align}$$
The proof can be seen to execute the Leibnizian strategy, which is, to show that God is necessary, show that God is possible, and that if God is possible, then God is necessary. 

Theorem 3 has a substantive corollary, namely that God exists.

## Would that be God? Could it be God?
---
To cut a long story short, P as in positive is a primitive and depending on how you interpret it various theorems can be shown to be false.

Come back later for further point on Modal COllapse
