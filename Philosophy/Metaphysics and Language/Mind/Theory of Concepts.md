The word 'concept' is sometimes used as a synonym for 'property', but many authors use it in a more specific sense. For example, as:

- Unsaturated entities whose extensions are sets and classes
- [[The Logical Study of Language|Fregean Senses]]
- Abstract objects
- etc.

There is no universal agreement on a definition of concepts, a viable theory of concepts has to address a number of formal issues:
- How to deal with [[Conditionals|counterfactuals]] and possibly contradictory concepts (?).
- How to restrict comprehension schemes in higher-order [[Basic overview of logic|logic]] to avoid semantic paradoxes like the Paradox of Predication.
- How to nominalize concepts.
- How to express similarity and typicality of concepts.

## Key Notions and Problems
---
Concept theories draw on a rich tradition, ranging from Plato and Aristotle over Leibniz to Frege. Two key aspects of a theory of concepts need to be distinguished:

1. The cognitive aspect regards the role of concepts in cognition and how these enable an epistemic agent to classify and categorize reality. A concept system is sometimes considered the cornerstone and starting point of a 'logic of thinking'.
2. From a metaphysical point of view, concept theory must provide an [[Grounding, Ontological Dependence, and Fundamentality|explanation]] of the ontological status of universals, how these combine, whether there are different modes of predication, and what it means in general for an object to fall under a concept.

Both will be addressed in what follows, we'll start here with a brief overview of some problems and positions.

***The Demarcation Problem.*** There is no general agreement on what a concept is. Sometimes 'concept' is used as a synonym for 'property', but many other authors use it in a more specific sense. One goal shared by many authors is to carve out the differences between closely related notions such as concepts, properties, abstract objects, Leibnizian concepts, or Fregean senses and make these notions more precise.

***Nominalism, Realism, Cognitivism.*** A particular object is said to fall under a singular or individual concept and likewise a group of objects sharing some common trait is said to fall under a general concept. Being sorts of universals, different stances toward general concepts may be taken:
- According to strict nominalism, there are only particulars; quantification over predicate expressions is not allowed at all or very limitidely. In this view, general concepts do not exist in reality although they might play a role as thinking devices.
- In contrast, according to realism predicates denote universals either directly or whenever the predicate has been normalized. There *are* universals in the sense that one may fully quantify over them although they might not be considered to exist in the narrow sense. Cognitivism is a mixed position, there are universals but only insofar they are represented by mental states.

***Intensionality, Hyperintensionality, Contradictory Concepts.*** Having a heart and having a liver are often given as an example of two different concepts with the same extension. [[Necessity and Possibility|Modal logics]] have been used to account for this difference. Possible world semantics do not provide the means to distinguish two different mathematical concepts with the same extension from each other. For example, two different ways of describing an equiangular triangle will determine the same set of objects in all possible worlds. To tackle this problem a stronger form of intensionality known as hyperintensionality is needed. Moreover, a person might erroneously believe that $37$ is a prime number while not believing that $21 + 16$ is prime, might erroneously believe that $\sqrt{2}$ is a rational number, or might muse about round squares. To represent irrational attitudes and impossible objects a logic must in one way or another allow contradictory statements. Since in classical logic any formula can be derived from a contradiction (ex falso quod libet) a para-consistent logic is needed; such a logic allows one to derive some, but not arbitrary consequences from a contradiction.

***Similarity.***  A concept may be more or less similar to other concepts. For example, the concept of being a chair is similar to a concept of being a stool and both of them are more similar to each other than any of them is to the concept of being the back of a horse. From a cognitive perspective, it is desirable to have a concept theory that allows for a measure of similarity between concepts and the objects falling under them.

***Typicality.*** Typically chairs have four legs, but some have less. Typically birds can fly, but penguins cannot fly. How can this typicality be accounted for?)

## Preliminaries of Logic Concept Theory
---
In order to formulate a broadly-conceived logical theory of concepts it is necessary to quantify over concepts or corresponding abstract objects. Unless a very strict nominalism based on [[Predicate Logic|first-order logic]] is defended this naturally involves the use of second-order logic. For this reason results from mathematical logic need to be taken into account when developing a logical theory of concepts.

***Henkin Models and Standard Models.*** There are two kinds of models for higher-order logic. In a standard model, first-order variables range from a domain $D$, second-order variables over $\mathcal{P}(D)$ for predicates and $\mathcal{P}(D_1 \times ... \times D_n)$ for $n$-ary relations, third-order predicate predicate variables over $\mathcal{P}(\mathcal{P}(D))$, and so on. 

In a Henkin model (general model), only a fixed subset of the powerset is chosen respectively.  So for instance the quantifier in $\forall F[F(a)]$ ranges over a fixed subset of $\mathcal{P}(D)$. Higher-order logic with Henkin models is essentially a variant of many-sorted first-order predicate logic. It is complete, compact, and the Löwenheim-Skolem theorems hold in it, but does not allow one to define certain mathematical structures categorically, i.e. in a way that is unique apart from differences captured by the notion of an isomorphism between models.

In contrast, higher-order logic with standard models is not complete, not compact, and the [[Predicate Logic#^e20f61|Löwenheim-Skolem]] do not hold in it. Lack of a full-fledged proof theory is compensated by the ability to categorically define important concepts such as countable vs uncountable domains, quantifiers like 'most', and well-foundedness conditions.

The distinction between higher-order logic and second-order logic with standard models is less important since the former can be reduced to the latter without significant loss of expressivity.

***Logical Paradoxes and Comprehension.*** Given some condition expressible in a formal language, what concepts are there? One way to answer this question is by specifying a comprehension scheme. Unrestricted comprehension asserts that there is a concept corresponding to any condition $\phi$ that can be formulated in the language (See principle 1 in the below box). It allows one to introduce Russell's paradox of predication. Take the predicate $P(x)$ that is not predicable of itself and is defined as $\neg x (x)$. Choosing $\phi := \neg x(x)$ and existential instantiation allows one to derive $\forall x [P(x) \iff \neg x (x)]$ and by universal instantiation the contradiction $P(P) \iff \neg P(P)$.  Different provisions to avoid such inconsistencies lead to higher-order logics with varying expressive power that reflect different stances towards nominalism, cognitivism, and realism.

***Predicativity vs. Impredicativity.*** A definition is impredicative iff it quantifies over a collection of objects to which the defined object belongs; otherwise it's predicative. Russell held the view that paradoxes arise because a logic with unrestricted comprehension allows for impredicative definitions. As a solution, the logic is made predicative. 

One way to achieve this is by assigning an order to all variables and prescribe that in any atomic formula $P(x_1, ..., x_n)$ in a condition $\phi$ formulated in the language the order of all $x$ must be lower than the order of $P$ (see principle 2 in the box below and stratification). This makes $\neg x (x)$ ungrammatical.  Church's influential Simple Type Theory (STT) is another way to define a predicative higher-order logic. Every term has a type with corresponding domain. Starting with finitely many base types, infinitely many compound types can be built. If $\alpha$ and $\beta$ are types, then ($\alpha \beta$) is the type of a function that takes an object of type $\beta$ and yields an object of type $\alpha$ where $\beta$ and $\alpha$ may themselves be compound types. Predicates and relations are represented by several functions. This is called Currying. For example, a unary predicate $P$ is of type ($\sigma \iota$), indicating a function that takes a term  of type $\iota$ and yielding a truth-value of type $\sigma$, a second-order predicate is of type ($\sigma$($\sigma \iota$)), and so on.

Impredicativity does not automatically lead to paradoxes. On the contrary, many useful mathematical concepts such as the induction principle used for defining natural numbers are impredicative. For this reason, some conceptual realists opt for impredicative second-order logics that give rise to larger mathematical universes. In these logics comprehension is restricted less radically than in predicative ones (see 3 in the below box) or full comprehension is combined with a limited substitution principle in order to gain more expressivity while avoiding paradoxes. The downside is that it's harder to ensure consistency in such systems.

> [!box_name] Comprehension schemes and stratification
> Stratification: Formula $\phi$ is homogeneously stratified iff there is a function $f(.)$ that maps terms and formulas of the language to natural numbers such that for any atomic formula $P(x_1, ..., x_n)$ in $\phi, f(P) = \text{ max}[f(x_i)] + 1$ and $f(x_i) = f(x_j) \text{ for }1\leq i, j \leq n.$ $$\begin{align}&\exists F \forall \overrightarrow{x}[F(\overrightarrow{x}) \iff \phi(\overrightarrow{x})] && \text{(Scheme A)}\\ &\exists F \forall \overrightarrow{x}[F(\overrightarrow{x}) \iff (G(\overrightarrow{x}) \land \phi(\overrightarrow{x}))] && \text{(Scheme B)}\end{align}$$
> Conditions: (I) $\overrightarrow{x} := x_1, ..., x_n$ are free in $\phi$, i.e. bound in the whole scheme; (II) $F$ is not free in $\phi$, i.e. not bound in the whole scheme; (III) $\phi$ is homogeneously stratified.
> 1. Unrestricted Comprehension: Scheme A + I
> 2. Predicative Comprehension: Scheme A + I, II, III
> 3. Separation Axiom: B + I, II
 
***Philosophical Relevance.*** 
- First-order logic and predicative higher-order logic with Henkin models reflect a strict nominalist stance. 
- Predicative higher-order logic with standard models may also be considered nominalist in spirit, because predicative comprehension reduces the existence of general concepts to conditions explicitly given in the language. 
- Impredicative higher-order logics with standard models clearly reflect a realist stance.

## Concepts as Abstract Objects
---
***Possibilism.*** The conceptual realist wants to talk about concepts, but it's implausible to claim that concepts exist in the same sense as ordinary objects. Therefore, many conceptual realists distinguish between quantification as a means of counting and quantification as a means of asserting existence.

A logic in which non-trivial properties can be ascribed to nonexistent objects is possibilist or Meinongian. In a classical setting, possibilism can be obtained by introducing two sorts of quantifiers. Actualist quantifiers are mere means of counting and run over the total domain, whereas possibilist quantifiers additionally assert existence and run only over a subset of the total domain. Alternatively, a unary existence predicate $E(x)$ may be introduced to which possibilist quantifiers are relativized, for instance $\forall^{*}x A := \forall x [E(X) \to A]$ and $\exists^* A := \exists x [E(x) \land A]$.

***Nominalization.*** One positive answer to the problem  of universals is to assert that we cannot only quantify over concepts but are also able to talk about concepts like *being nice* as objects. Sometimes, $\lambda$-abstraction is thought to fulfill this purpose.

Semantically, a term of the form $\lambda x. P(x)$ is interpreted as the function that with respect to an assignment $g$ takes an $a$ within the domain of $x$ and whose result is the same as $P(x)$ evaluated with respect to the modified assignment $g'$ that is the same as $g$ excepts that $g'(x) = a$.

One might then consider $\lambda x. P(x)$ to stand for *being nice* if $P$ stands for the predicate *nice*. However, $\lambda$-terms can be used instead of relations and the converse transformation is also possible in a logic with both functions and relations, and so $\lambda$-abstraction might not be considered a tool for nominalization in the narrow sense.

Abstract object theory and alternative ontologies such as trope theories provide more elaborate nominalization mechanics. Differing in details, generally these approaches distinguish nuclear and extranuclear properties:

- Nuclear properties are constitutive of an object.
- extranuclear properties are not.

Two different modes of predicate are available then:

- An object encodes a property if the property takes part of a description or listing of the object's essential feature.
- An object exemplifies a property if it has the property accidentally.

For example, in bundle trope theories, an object (need not be concrete or existent) encodes a property if its constituting bundle of properties contains the property, and exemplifies a property if it stands in a designated relation to the property.

A concept in this view is a nonexistent non-concrete bundle of primitive properties. Analogously, in abstract object theory $aF$ stands for the fact that the abstract (non-existent) object $a$ encodes property $F$. 

Care must be taken to restrict the range of properties that can be encoded, for example forming an abstract object *existent red sphere* must either be disallowed or the existence-entailing predicate "existent" must be interpreted in a non-literal way.

## Concepts and Intensionality
---
***Modal Concepts and Intensionality.*** Modal operators may be added to higher-order logic in the same way they are added to first-order logic, which in the second-order setting allows one to precisely express philosophical positions about the modal properties of concepts. For example, Anti-Essentialism may be expressed as adding the following axiom: $$\forall F[\exists x \Box F(x) \to \forall x \Box F(x)]$$
which may be paraphrased as "if an object has an essential property, then any object has this essential property."

***Hyperintensionality.*** Inspired by Frege's informal distinction between the sense and denotation of an expression, there is a tradition of hyperintensional logics in which the following Axiom of Extensionality does not hold: $$\forall F\forall G(\forall \overrightarrow{x}[F(\overrightarrow{x}) \iff G(\overrightarrow{x})] \to \forall H[H(F) \to H(G)])$$
The axiom states that if exactly the same objects fall under two concepts, then the concepts are identical in Leibniz's sense of having the same properties. Their are differences in detail, but generally hyperintensional logics invalidate this axiom by interpreting expressions over a domain of fine-grained intensions, which are in turn mapped to their extensions by an extension function. 

Consequently, two notions of identity are available in such a logic: coarse-grained extensional identity and fine-grained intensional identity interpreted over intensions.

By interpreting functions and operators standing for notions like de dicto belief over intensions it is possible to distinguish having a heart from having a liver and deal with ordinary cases of referential opacity like the Morning-Evening Star example. Additionally, strong intensions allow one to represent attitudes that aren't closed under logical consequence.

***Contradictory Concepts.*** Not writing about this, it's nonsense bro.

## Geometrical Approaches
---
There are alternatives to the logical approach. These geometrical concept approaches fare well with issues related to the cognitive aspects of concepts such as vagueness, typicality, and similarity, and can be combined with or thought to complement with logical theories.

***Typicality.*** In a qualitative approach, a preorder relation (preference relation) between all objects falling under a concept can be used to order objects falling under a given concept according to their typicality. The center represents a prototype and the nearer an object is to the center the more typical it is.

In a logical setting, this kind of typicality can be expressed in Preference Logics and related descendants of Lewis's Conditional Logic. Quantitative accounts induce a similar ordering by assigning a degree of typicality as a real number between $0$ and $1$ to each object as dependent on the concept it falls under, and despite some differences the two approaches can for many practical purposes be translated into each other.

***Conceptual Spaces.*** Gärdenfors proposes to model concepts not just on a symbolic, but also on a geometric level. A conceptual space is an $n$-dimensional metric space with $n$-quality dimensions, each of which represents a basic quality like *height*, *width*, *hue*, *saturation*, or *loudness*.

A distance function allows for measuring the distance between any two points in such a space. In the simplest case of familiar $n$-dimensional Euclidean space this distance measure between two points $x = \langle x_1, ..., x_n \rangle$ and $y = \langle y_1, ..., y_n \rangle$ is: $$d_{E}(x, y) = \sqrt{\sum_{i=1}^n w_i(x_i - y_i)^2}$$
where $w_i$ represents the weights of the respective quality dimension. More general topological definitions of spaces allow for an adequate treatment of purely qualitative dimensions. Generally speaking, in conceptual spaces objects are represented as vectors $x = \langle x_1, ..., x_n \rangle$
 and concepts by regions in the space. Similarity between two objects in a conceptual space is defined as a function of their distance.

Gärdenfors has conjectured that natural concepts should be represented by convex regions. A region $C$ of a space $S$ is convex iff for any two points $x, y \in C$ and point $tx + (1-t)y$, where $0 \leq t \leq 1$, on the line segment $\overline{xy}$ between $x$ and $y$ is also in $C$.

One advantage of this assumption is that every convex region has a center, which may be interpreted as a prototypical object falling under the concept. 

The convexity condition has also been taken as a first step toward distinguishing between natural and non-natural concepts. For example, with ‘standard’ quality dimensions Goodman’s artificial concept *grue*, which is true of green objects before some point in time and of blue ones afterwards, is represented by a non-convex region. However, this solution depends on criteria for finding natural quality dimensions, as a natural concept may be turned into a non-natural one by changing the underlying dimensions and vice versa..

***Formal Concept Analysis.*** In formal concept analysis a set $M$ of attributes is associated with a set of objects $G$ by a binary relation $I(x, y)$ read as "object $x$ has attribute $G$", where the triple $\langle M, G, I\rangle$ is called a context.

Such a context can be thought of as a table with objects as rows and attributes as columns and a mark at the row-column intersection if the object as that row has the respective attribute.

A formal concept is then a pair $\langle A, B\rangle$ of subsets $A\subseteq G$ and $B \subseteq M$ such that all objects in $A$ share all the attributes in $B$. The formal concepts of a context can be ordered by a relation $(A, B) \leq (C, D)$ which is true iff $A \subseteq C$, false otherwise.

Ordering all concepts in a context yields a *lattice* structure in which the least specific concept is at the bottom and the most specific one is at top. Various methods and algorithms based on this representation have been used for data mining, machine learning, discovering new relationships between concepts, concept visualization, explaining human concept acquisition, and models of concept change.

