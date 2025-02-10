- **terms**
	- Examples: $f(x, y), s(s(0))$
- **predicate symbols**
	- Examples: $P, Q$
- $\neg$ **negation**
- **binary connectives**
	- $\lor$ (disjunction)
	- $\land$ (conjunction)
	- $\to$ (implication)
- **quantifiers**
	- $\forall$ (for all)
	- $\exists$ (exists)
	- Example: $\forall x P(x)$

These are **syntactic** components. The **semantics** define what these constructs means.

## Semantics
---
An **interpretation** of a first-order language defined:
- a nonempty set $D$, the domain of discourse.
- a function $I$, mapping function symbols to functions $D^n \to D$ and predicate symbols to relations over $D^n$

A formula is **satisfiable** if there is an interpretation under which it is true. Such an interpretation is called a **model**.

A formula is **valid** if it is true under all interpretations.

If every interpretation that makes A true also makes B true, then B is a **semantic consequence** of A, written $A \vDash B$.

## Relations
---
- $<(x, y)$, or, in infix notation: $x < y$
- $P(x, y)$
- $A(x, y)$
- $a = b$
- etc.

## Theories
---
A **theory** is a set of sentences. The sentences are called **theorems**.

Commonly specified as a set of **axioms**.

For example, Zermelo-Fraenkel **set theory** (ZF): 
- $(\forall x) (\forall y)((\forall z)(z \in c \iff z \in y) \to x = y)$  (extensionality)
- $(\forall x)(x \neq \emptyset \to (\exists y)(y \in x \land y \cap x = \emptyset))$ (regularity) 
- $(z \subseteq x) \iff (\forall q)(q \in z \to q \in x)$ 
- $(\forall x)(\exists y)(\forall z)(z \subseteq c \to z \in y)$ (power set)
- etcc., and the semantic consequences of these axioms.

This is called a deductive theory, because it closed under the consequence relation. 

Suppose we've managed to state the key properties we want to express about sets in the language of predicate logic, a few questions arise:

Semantic consistency/Satisfiability: Does the conjunction of these sentences have a model?

Syntactic consistency: $\phi \notin \text{ZF}$ or $\neg \phi \notin \text{ZF}$ for all sentences $\phi$? 

> [!box] Model Existence Theorem
> 
> If a first-order theory with a well-orderable language is syntactically consistent, then it has a model. This means the semantic notion of consistency coincides with the syntactic notion in first order theories with a well-orderable language. ZF (and ZF-c) are examples of such a language.
> 
> The model existence theorem is an important link between the syntax and semantic of a theory. Notably, this connection breaks down for second and higher-order logics.

ZF is widely believed to be consistent, but its not known to be consistent. What is known is that many important statements are independent of ZF: $\phi \notin \text{ZF}$ and $\neg \phi \notin \text{ZF}$.

For example, Kurt Godel proved that if ZF is consistent, than ZF plus the axiom of choice is consistent. In 1963 Paul Cohen used a technique known as forcing to show that if ZF is consistent, then so is ZF plus the negation of the axiom of choice.

A closely relation question, what are the semantic consequences of these axioms?

How do we even determine semantic consequences?

There are infinitely many possible interpretations! Even uncountably many, so we can't simply try all interpretations, even more so because a theory may have infinitely many axioms.

This is the case for ZF, because ZF includes axiom schemata, which stands for infinite families of axioms. In fact one can show that in contrast to other set theories, ZF is not finitely axiomatizable.

There's a even more fundamental issue, we used to the concept of set in the very definition of interpretations. (We said we have a non-empty set of discourse). In fact we used the concept of set to define what a theory is. We have already used the concept we purport to be defining with these axioms. For these reasons its not clear how to proceed with only semantic considerations.

Nevertheless we're still interested in semantic consequences. We only need a good way to find and verify them. This is where deductive systems come handy.

## Deductive Systems
---
Main goal: Prove semantic consequences on a purely syntactic basis. We want to arrive at semantic consequences only by symbolic reasoning without having to consider all interpretations (or in fact any).

A **proof** is a finite sequence of inferencetheoremhoods, starting from a set of axioms and using inference rules to deduce theorems.

A formula $A$ is a **syntactic consequence** of a set of formulas $\Gamma$, written $\Gamma \vdash A$, if there is a proof of $A$ from $\Gamma$.

There are many deductive systems for predicate logic:
- Hilbert-style systems 
	- Well suited for comparing different logics
	- One key characteristic of Hilbert-style systems is they have many axioms but only a small number of inference)
- Gentzen-style systems
	- Natural deduction (This is closely related to $\lambda$-calculus by the curry howard isomporhism)
	- Sequent calculus
	- Gentzen style systems have more inference rules than Hilbert style
- Resolution
	- Very well suited for automated theorem proving
	- Prolog uses a specific form of resolution
- ...

The most important property we expect from a deductive system is **soundness**.

> [!Theorem] Soundness:
> $\Gamma \vdash A \to \Gamma \vDash A$

The converse is called **completeness**.

>[!Theorem] Completeness:
> $\Gamma \vDash A \to \Gamma \vdash A$

This is also a desirable property because it means we can focus on purely syntactic reasoning and need not consider all interpretations.

One property that holds for all systems mentioned is the deduction theorem.

> [!Theorem] Deduction Theorem:
> $\Gamma, A \vdash B \to \Gamma \vdash A \to B$

Very important theorem as it gives the formal justification for conditional proofs. In particular: $A \vdash B \to (\vdash A \to B)$

## Turing Machine
---
Let $\mathcal{T}$ denote the conjunction of sentences that describe the Turing machine TM.

Results of the computation correspond to *semantic consequences* of $\mathcal{T}$.

"The machine reaches its final state", i.e., it *halts*:
$$(\exists x)(\exists y) T(q_f, x, y)$$
Then we have $$\text{TM halts } \iff \mathcal{T} \to (\exists x)(\exists y) T(q_f, x, y) \text{ is valid}$$
This means validity is not decidable in predicate logic as the Halting problem is famously semi-decidable. This means there is a procedure that terminates and says yes if a given sentence is valid, and rejects or continues forever if its invalid.

## Notable Properties
---
A few key properties of classical **first-order** predicate logic:
- **Monotonicity** of entailment: $P \vDash C \to P, A \vDash C$.
- **Completeness**, by Godel's *completeness theorem*: For every first-order theory $T$ with a well-orderable language, for any sentence $s$ in the language of $T: T \vDash s \to T \vdash s$. Not very interesting by itself, only interesting if we can prove all and only all semantic consequences. That is indeed the case, that is $T \vDash s \iff T \vdash s$. This is nice, because it means we only need to perform purely syntactic operations to derive semantic consequences, and syntactic operations can be easily automated. This means in first-order logic we can mechanize logical reasoning by es arching for proofs.
	- As a special case for the empty theory ($T = \emptyset$),  we can therefore prove every valid sentence, this is called weak completeness: $\vDash s \iff \vdash s$. This is why first-order predicate logic is semi-decidable. If a formula is valid, there is a proof. So we only need to systematically search for a proof, and if its valid, due to weak completeness, we'll find a proof.
	- An equivalent way to state this, is that every sentence is either satisfiable or refutable. Phrased more explicitly as a model existence theorem: If a first-order sentence is not refutable, then it has a model. Validity is still only semi-decidable. Satisfiability is not even semi-decidable. It's truly undecidable.
	- This is **semantic completeness**, not syntactic completeness. Incompleteness theorems are about [[#Syntactic Completeness|syntactic completeness]].
- **Compactness**: A set $S$ of first-order sentences has a model if and only if every finite subset of $S$ has a model.
	- This implies that if a set of sentences is unsatisfiable then there is a finite subset we can use as a weakness.
	- If every finite subset is satisfiable, then the entire theory is satisfiable.
	- This is a key theorem that makes resolution work, in fact the compactness theorem is equivalent to the completeness theorem for well-orderable languages, and therefore for countable language.
- Upward and Downward **Löwenheim–Skolem theorem**: If a countable first-order theory has an infinite model, then for every infinite cardinal number $k$ it has a model of size $k$.
	- Downward Löwenheim–Skolem leads to Skolem's Paradox.
	- Skolem's Paradox: $\text{ZF} \vdash \text{There is an uncountable set}.$
	- We can formulate and prove from ZF a sentence that states "there is a set that is not uncountable" because ZF proves Cantor's theorem, that is there is no projection between a set and its power set. Together with the axiom of power set, ZF proves there's a set which can't be put in projection with a set of integers.
	- So ZF proves there are uncountable sets, on the other hand we know from the Downward Löwenheim–Skolem theorem that if ZF is consistent, it has a countable model. In such a model of course all sets are also countable. This shows that the notion of countability is relative! Because there are sets that are only uncountable from the perspective of certain models of ZF, not the perspective of all models.
		- Recall a set if countable iff it is finite or can be put in one-to-one correspondence with the set of naturals, a one-to-one correspondence is a relation, ergo it is also a set! This paradox arises because it's possible that a particular set $u$ is countable, but not countable in a particular model of set theory, because the there is no one-to-one correspondence set so to speak in that model.
- **Lindström's theorem**: Among all logic's that satisfy certain regularity conditions, the countable compactness theorem and the downward Löwenheim–Skolem theorem characterize first-order predicate logic as the strongest logic. As a consequence, if we want more expressive power from our logic, we need to sacrifice at least one of these properties. ^e20f61
	- For example, in second-order logic, both theorems fail to hold.

### Syntactic Completeness
A formal system $\mathcal{S}$ is **syntactically complete** iff for each sentence $\phi$ of the system, either $\mathcal{S} \vdash \phi$ or $\mathcal{S} \vdash \neg \phi$.

That is, for each statement we formulate, we have a definite answer one way or the other. Such an $\mathcal{S}$ is also called deductively complete, maximally complete, negation complete, or complete.

Syntactic incompleteness is nothing unusual, an example: If ZF is consistent, it is incomplete.

> [!Theorem] Godel's first incompleteness theorem:
>  Any consistent formal system within which a certain amount of arithmetic can be carried out is incomplete. 

One way to see this is once we have a certain amount of arithmetic available, we can formulate statements about Turing Machines and computations in the shape of statements about numbers, sets, etc. If we had a formal system that can correctly prove or refute all statements we can make about such computations then we can use such a system to decide questions that are known to be undecidable, and therefore such a system cannot exist.

## Expressiveness
---
We've seen that first-order predicate logic is quite expressive and can in fact describe all known computations.

Many concepts *cannot* be expressed in first-order predicate logic:
- We can't define the intended model of the real numbers
	- Due to the Löwenheim–Skolem theorem we cannot control the cardinality of infinite models, so for instance if we use a countable first-order theory to specify the real numbers and the theory has a model, then it also has a countable model. Where the intended model of the reals isn't countable!
- We also cannot define [[#Reachability|reachability]]. The same holds for Hamiltonicity of a graph, and the transitive closure relation.
- We can't define the class of finite connected graphs
- We can't define the [[#Natural Numbers|natural numbers]] with only the intended model.
- ...

A lot of these things can be defined in second-order predicate logic, unfortunately with second-order predicate logic we lose important properties like semantic completeness. We can no longer automatically derive or detect all semantic consequences of these theories.

Even though first-order logic can express all known computations, it can't express many important mathematical concepts.

There's ways to kinda get around this, consider the situation with Prolog. Prolog is based on first-order predicate logic but simplicity only considers a particular kind of model, namely *least Herbrand models.*

For this reason, we can actually define many of these things in Prolog and obtain only the intended results.

 **Example:**
 ```prolog
 natnum(0).
 natnum(s(X)) :- natnum(X).
```

The above predicate is true iff the argument is a natural number in successful notation. So considered as a first-order theory this program consists of two sentences that closely corresponds to the syntax of first-order logic.

We can use this predicate to generate and test solutions, we do this by posting queries, that is asking for logical consequences of the theory.

For example, lets ask the most general thing we can ask about this predicate. Namely for which X is it the case that the predicate holds.

```prolog
?- natnum(X).
X = 0 ;
X = s(0) ;
X = s(s(0)) ;
X = s(s(s(0))) ;
X = s(s(s(s(0)))) ;
X = s(s(s(s(s(0))))) ;
```

Each solution is a *semantic consequence* of the theory.

The least Herbrand model reflects all information expressed by the program, and nothing more. One can show the least Herbrand model is unique.

### Reachability
Suppose we have a first-order formula $\phi(x, y) \iff y \text{ is reachable from }x$.
Then let's define a certain class of graphs:
- $\psi_1 := (\forall x)(\forall y) \phi(x, y)$ <- graph is strongly connected.
- $\psi_2 := (\forall x)(\exists y)(E(x, y) \land (\forall z) (E(x, z) \to y = z))$ <- each node has an out-degree of 1
- $\psi_3 := (\forall x)(\exists y)(E(y, x) \land (\forall z) (E(z, x) \to y = z))$ <- each node has an in-degree of 1

The sentences up to here characterize a cyclic-graph, in addition we define a set of formulas $I_k$.
- $I_k := (\forall x_1)(\forall x_2)...(\forall x_{k - 1})(\exists x_k)(x_k \neq x_1 \land x_k \neq x_2 \land ... \land x_k \neq x_{k - 1})$ <- each $I_k$ is only true if at least k domain elements are present, and there is an $x_k$ that is different from $x_1$ to $x_{k-1}$ 

**Example**: 

We can take the first three axioms and enforce that there are at least three domain elements. $$\{\psi_1, \psi_2, \psi_3, I_3\}$$
This theory clearly has a model, take for example the directed cycle with three nodes.

Likewise there is also a model with 4, 5, 6, 7, etc domain elements.

It's easy to see our theory which described a cyclic graph $\{\psi_1, \psi_2, \psi_3\}$ has arbitrary large finite models. Hence, by the **overspill principle**, it has an infinite model.

This is a consequence of the compactness theorem, because if we take our theory and add for every natural number $n$ a sentence saying there is at least $n$ domain elements, and we know that there are arbitrary large models, then every finite subset of these sentences is satisfiable and therefore by the compactness theorem there is a model of the entire theory and that model must have infinite cardinality.

$$\{\psi_1, \psi_2, \psi_3, I_1, I_2, ...\} \text{ has a model: an "infinite cycle"} \rightarrow\leftarrow$$
In our concrete example we can use the formula phi to describe an infinite cycle, which leads to a contradiction because if we start at some nodes and we follow all out-degrees because the graph is strongly connected we'll visit all nodes. But the node we started from  has indegree 1 so there must be a node in the graph from which we return to where we started. But that means the graph must be finite. 

So we must drop an assumption, and the only assumption we made was that $\phi$ exists, so we conclude that $\phi$ does not exist.

$$\to \text{A first-order formula }\phi \text{ that defines reachability does not exist.}$$

### Natural Numbers
We can state many requirements for natural numbers in first-order logic. For example:
- $(\forall x) (s(x) \neq 0)$
- $(\forall x)(x = 0 \lor (\exists y)(s(y) = x))$
- $(\forall x)(\forall y)(s(x) = s(y) \to x = y)$
- $(\forall x)(x + 0 = x)$
- etc.

We can't define the intended model in first-order.

Due to the compactness theorem and Löwenheim–Skolem theorem, all first-order theories of the natural numbers allow **non-standard** models.

To be more clear, no matter what we state, we know that as long as we use only first-order logic and as long as the theory has an infinite model there will also be a model that has a non-standard element in it, that is an element that is different from all natural numbers in the conventional sense.

We can obtain such a model by stating suitable disequalities as we have just done for reachability and from the compactness theorem it follows that the conjunction of all such disequalities has a model, and further from the upward Löwenheim–Skolem theorem, which is a consequence of the compactness theorem, if the theory has an infinite model then it has models of all greater infinite cardinalities, so the theory will also have an uncountable model, which is of course not what we intend with the natural numbers. Such interpretations are called non-standard interpretations and we can't rule them out by using only first-order logic.

One way to rule them out is to add second order axioms, this is for example done in the Peano axioms of arithmetic. This means we add a sentence that quantifies over predicates, for example the induction axiom. This way we obtain a categorical model of the natural numbers.