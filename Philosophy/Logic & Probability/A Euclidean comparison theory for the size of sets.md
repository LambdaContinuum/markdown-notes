# Intro
In the history of Math the problem of comparing the size of mathematical objects has been studied extensively.

A satisfactory notion of *measure of size* should abide by five common notions of Euclid's Elements, which embody the properties of any kind of magnitudines:
1. Things equal to the same thing are also equal to one another.
2. And if equals be added to equals, the wholes are equal.
3. And if equals be subtracted from equals, the remained are equal.
4. Things exactly applying onto one another are equal to one another.
5. The whole is greater than the part.

Following ancient praxis of comparing magnitudes of homogeneous objects: A very general notion of size of sets, whose essential property is general comparability of sizes, can be given through a total preordering $\preceq$ of sets according to their size, with the intended  meaning that *equinumerosity*, i.e. equality of size, is the corresponding equivalence relation $A \simeq B \iff A \preceq B \preceq A$.

So, the first Euclidean common notion (1) is subsumed because $\simeq$ is an equivalence.  

The comparison should naturally extend set-theoretic inclusion and be consistent with *equinumerosity*. So one has to assume that $A \preceq B \iff \exists A',B' (A \simeq A' \subseteq B' \simeq B)$ .

The equivalence classes module $\simeq$, called the magnitudines of the theory, are totally ordered by the ordering induced by $\simeq$.

In set theory the usual measure for the size of sets is given by the classical Cantorian notion of "cardinality", whose ground is the so called Hume's Principle: Two sets have the same size if and only if there exists a biunique correspondence between them.

This principle amounts to to encompass the largest possible class of exact applications (congruences) admissible in the fourth Euclidean notion, namely *all bijections*. This assumption might seem natural but it strongly violates the equally natural Euclid's principle applied to (infinite sets): A set is greater than its proper subsets. This seems implicit in the notion of manitudo, even for sets.

So one could distinguish to basic kinds of size theories for sets:
- A size theory is *Cantorian* if, for all A, B: $$\text{(HP) }(Hume'sPrinciple)\text{ } A \preceq B \iff \exists f: A\to B \text{ 1-to-1}$$
- A size theory is *Euclidean* if, for all A, B: $$\text{(EP) }(Euclide'sPrinciple) \text{ } A \prec B \iff \exists A', B' (A \simeq A' \subseteq B' \simeq B).$$
The development of Cantorian set theory in the twentieth century has put Euclid's principle in oblivion. We've recently seen a limited resurgence in proposals including it at the cost of severe limitations to Hume's principle.

The main value of Euclidean theories is the excellent arithmetic they allow, namely that of an ordered semiring, to be contrasted with the awkward cardinal arithmetic. The main problem in Euclidean theories lies in the fact that the preordering of sets, defined by the natural set theoretical characterization (EP) should induce the "algebraic" total ordering of the semiring of numerosities, which in turn is equivalent to the subtraction property $$\text{(Diff) } A \prec B \iff \exists C \neq \emptyset (A \cap C = \emptyset \land A \cup C \simeq B)$$
A notion of "number of elements" (*numerosity*) that fulfills the Euclidean Principle has been found up to now only for special countable sets and generalizing later to point sets on countable lines. The consistency of the full principle for uncountable sets appeared problematic from the beginning, and this question has been posed in several papers where only the literal set-theoretical translation of the fifth Euclidean notion i.e., the weaker principle requires the sole left pointing arrow of (EP), 

5. $A \subset B \to A \prec B$

has been obtained. It's worth recalling that the totality of the Cantorian weak cardinal ordering had to wait a couple of decades before Zermelo's new axiom of choice established it.

