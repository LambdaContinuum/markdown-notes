
What is Logic? It's a very broad topic.

Logic is concerned with the properties of, and relations between:
- syntax (formulae, sentences, etc.)
- semantics (truth, validity, semantic consequences, etc.)
- inferences (proof, theorems, soundness, completeness, etc.)

## Logics
---
- Propositional logic
	Formulas: $\textbf{t}, \textbf{f}, A, B, A \land B, A \lor B, A \to B, \text{ etc}$.
	
	Propositional logic can express NP-complete problems. (Obviously, boolean satisfiability is NP-Complete).

- Predicate logic
	- First-order predicate logic
		Formulas: $P(x), \forall x (P(x) \to Q(x)),  \exists x (x > 0), \text{ etc}$
		
		First-order predicate logic can describe a Turing machine.
		
		For every given Turing machine we can construct a first order formula that is valid iff the Turing machine holds, from this it follows that first-order predicate logic that validity and satisfiability are in general not decidable.
		This means that First-order predicate logic is expressive enough to express all possible computations.
		
		First-order predicate logic is strongly complete, so we can derive all semantic consequences by syntactic inference. From this it follows that validity and unsatisfiability are semi-decidable.
	- Second- and higher order logics
		This allows statements about relations between relations etc.

A general principle: **Increased expressiveness has a price**

The price in this case is reasoning about the sentences in the logic becomes much harder. In fact, in second- and higher order logics reasoning becomes so hard that reasoning whether a sentence is valid is not even semi-decidable, it's truly undecidable.

## Classical Logic
---
"Classical logic" denotes propositional and predicate logic as found in Gottlob Frege's *Begriffsschrift (1879)*.

Some characteristic properties:
- law of excluded middle: $A \lor \neg A$ *tertium non datur*
- commutativity of conjunction: $(A \land B) \to (B \land A)$
- law of non-contradiction: $\neg(A \land \neg A)$
- etc.

Some situations justify different foundational laws. For example, when rasoning about proofs, we have $\nvDash (A \lor \neg A)$. 

Different foundational laws lead to different Logics

## Non-classical Logics
---
Examples:
- intuitionistic logic
- [[Necessity and Possibility|modal logic]]'s (temporal logic, epistemic logic, [[Deontic Logic|deontic logic]], etc.)
- many-valued logic's (Lukasiewicz logic, fuzzy logic, etc.)
- substructural logics (linear logic, relevance logic, etc.)
- ...

This is a bit similar to programming languages: You pick a logic that is *suitable* for your domains of interest.

The relation between logic and computer science is comparable to the relation between mathematics and physics.

Consider Prolog:

Prolog is a programming language based on a turing complete subset of predicate logic (horn clauses). Prolog also supports a few higher-order and meta-logical features.

Prolog's execution mechanism can be regarded as a specific form of *theorem proving*. It is incomplete in the sense that -in general- not all logical consequences of a program are derived.

RIchard O'Keefe says "Prolog is an efficient programming language because it is a very stupid theorem prover."

The reason for this trade-off is efficiency! We get an efficient programming language at the cost of completeness.

See next: [[Predicate Logic]]