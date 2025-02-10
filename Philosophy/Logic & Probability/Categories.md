Mathematical categories provide an abstract and general framework for [[Basic overview of logic|logic]] and mathematics. As such, they could be used by philosophers in all the basic fields of the discipline: semantics, epistemology, and ontology.

Here, we'll present the basic definitions and notions and suggest some of the ways categories are starting to infiltrate formal philosophy.
## Introduction
---
Mathematical categories were introduced in $1945$ by the mathematicians Eilenberg and Mac Lane in order to define two concepts that were seen at the time to be more important and mathematically relevant, the concept of functors and natural transformations.

The concepts introduced were so general that Eilenberg and Mac Lane picked from the philosophers' vocab:

> Now the discovery of ideas as general as these is chiefly the willingness to make a brash or speculative abstraction, in this case supported by the pleasure of purloining words from the philosophers: “Category” from Aristotle and Kant, “Functor” from Carnap, and “natural transformation” from then current informal parlance.

Eilenberg and Mac Lane themselves never made anything of the connection with the philosophical meaning of the term, although with hindsight, it is clear that they made a prescient choice of terminology.

The original definition they give does suggest that a mathematical category is a system of a uniform mathematical "kind" or type, e.g. the category of groups. Thus many mathematical kinds form categories, allowing mathematicians to relate and compare those kinds via functors and natural transformations.

Hence, categories could be thought of as some sort of organizational or classification tool for mathematical structures, although it certainly does not yield a proper classification in terms of a partition of mathematical structures.

Mathematical categories are relevant to formal philosophy and
metaphysics in at least two complementary ways:

1. First, as formal tools, category theory and categorical logic can be seen to be generalizations of first-order logic and set theory. As such, they become fundamental frameworks to model, analyze and give a precise expression to philosophical concepts and theories. Thus, in as much as logical and set-theoretical tools can be used for philosophical purposes, categorical methods provide a more general and conceptual framework for the same purposes. By so doing, it often opens the door to unexpected connections and links between heretofore unrelated domains.
2.  Second, mathematical categories occupy a central and fundamental place in contemporary mathematics and the organization and foundations of contemporary mathematics can now be understood from this perspective. Thus, if one of the goals of metaphysics is to provide an understanding of various kinds of beings, in particular mathematical beings, then mathematical categories are more than relevant to this enterprise.

## Categories: Definition
---
Informally, a category can be thought of as a network satisfying simple properties. The network is made of nodes $X, Y, Z, ...$ who exchange information. A sender can send multiple information and in various ways to a receiver. 

We can of think of the sender $X$ as representing a property and the information into a receiver $Y$ as a way of transforming the given representation in $X$ into a representation in $Y$.

One such way is represented by an arrow from sender $X$ to the receiver $Y$, namely by :

```tikz
\usepackage{tikz-cd} 
\begin{document}
\begin{tikzcd} 
X \arrow[r, "f"] & Y 
\end{tikzcd}
\end{document}
```

Notice that there can be many different arrows from one receiver to a sender as there are many different information that $X$ can send to $Y$. An information is automatically and always attached to a sender and a receiver.

Information is always traceable, naturally there can be arrows going the opposite way and one and the same node can be the sender and receiver of information. It's also assumed that whenever a sender $X$ sends information to a receiver $Y$ and the latter sends information to another receiver $Z$, then $Z$ can retrieve the information that $Y$ received from $X$, but only from the message it received from $Y$. This is to say that information composes. It's assumed that Nodes are always active, that is they always send information to themselves, which we will call the identity information and will denote by $1_X$ for a specific node $X$. Transfer of information is assumed to be associative. Informally, this says that in the end, the intermediary steps are irrelevant in the exchange of information. A second simple property is that the identity information does not affect the information coming in nor out.

A mathematical category can be thought of as such a simple network, see the formal definition below.

> [!box_name] Definition 1
> A *category* $\mathbf{C}$ is a system made up of nodes or objects $X, Y, Z, ...$ and arrows (or morphisms) $f, g, h, ...$ such that
> - For each arrow $f$ there are given nodes $dom(f), cod(f)$, respectively the *domain* and the *codomain*, and we write what's below whenever $X = dom(f)$ and $y = cod(f);$
>   
>```tikz
\usepackage{tikz-cd} 
\begin{document}
\begin{tikzcd} 
X \arrow[r, "f"] & Y & or & f:X \arrow[r] & Y
\end{tikzcd}
\end{document}
>   ```
>   - Given the arrows below $f, g$, there exists aN arrow $g \circ f$ called the *composite* of $f$ and $g$.
>```tikz 
\usepackage{tikz-cd}
\begin{document}
\begin{tikzcd} 
f:X \arrow[r,] \arrow[r] & Y & g:Y \arrow[r] & Z & g \circ f : X \arrow[r] & Z
\end{tikzcd}
\end{document}
> ```
> - For each node $X$, there is an arrow called the *identity arrow* of X.
> ```tikz 
\usepackage{tikz-cd}
\begin{document}
\begin{tikzcd} 
1_X:X \arrow[r] \arrow[r] & X
\end{tikzcd}
\end{document}
> ```
> These data must satisfy the following properties:
> - Composition is associative $$h \circ (g \circ f) = (h \circ g) \circ f$$
> - The identity arrow is a unit $$f \circ 1_X = f = 1_Y \circ f$$
>
>The arrows of a category $\mathbf{C}$ automatically yield a criterion of identity for nodes.

> [!box_name] Definition 2
> An arrow $f$ is said to be an isomorphism if it has an inverse, that is there is an arrow $g$ such that $f \circ g = 1_Y$ and $g \circ f = 1_x$ where:
>```tikz
\usepackage{tikz-cd} 
\begin{document}
\begin{tikzcd} 
f: X \arrow[r] & Y & g:Y \arrow[r] & X
\end{tikzcd}
\end{document}
>   ``` 

It can be readily shown that whenever such an inverse exists, it is unique and for that reason it is written $f^{-1}$.

Two nodes $X$ and $Y$ are *isomorphic,* written $X \simeq Y$, whenever there is an isomorphism between them. It's important to understand that isomorphic nodes are, from the point of view of the category in which they sit, indistinguishable.

Informally, we could say that two isomorphic nodes contain the same information, possibly encoded differently, thus it might not be obvious that they're isomorphic and they can be isomorphic in more than one way.

Categories automatically come with a duality via the notion of the opposite category, denoted by $\mathbf{C}^{op}$ of a category $\mathbf{C}$. The nodes of $\mathbf{C}^{op}$ are the same as those of $\mathbf{C}$, but the arrows go in the opposite direction. Thus, there is an arrow :
```tikz
\usepackage{tikz-cd} 
\begin{document}
\begin{tikzcd} 
f^0:Y \arrow[r] & X 
\end{tikzcd}
\end{document}
```
in $\mathbf{C}^{op}$ if there is an arrow:
```tikz
\usepackage{tikz-cd} 
\begin{document}
\begin{tikzcd} 
f:X \arrow[r] & Y 
\end{tikzcd}
\end{document}
```
in $\mathbf{C}$.  Composition is defined by: $$f^0 \circ g^0 = (g \circ f)^0$$
Categories abound and are varied in nature. Philosophers have to keep in mind that the nodes and arrows can be interpreted in many different ways and in many different contexts. In other words, the nodes do not have to be entities of a specific kind, they do not have to be constituted in a uniform manner from one category to the next. The best way to illustrate this is by giving examples, see the next section.

## Categories: Examples
---
There are two drawbacks to examples coming from mathematics:
1. One has to rely on already known mathematical structures and functions, otherwise the examples are just as opaque as the definition of categories itself and one fails to see the shift from the already known concept to the conceptually new level. Few philosophers are familiar with a large spectrum of mathematical structures, e.g. modules, groups, vector, spaces, rings, fields, Banach spaces, Hilbert spaces, Lie algebras, etc., in which case one fails to see clearly the *variety* of cases naturally falling under the concept.
2. The mathematical examples might lead readers to believe that there is what might first appear to be a "deeper" unity of categories, namely that the nodes are in fact sets and the arrows are in fact functions between sets, that a category is merely a metamathematical device allowing mathematicians to put some order in their otherwise chaotic house of structures. This would be an undesirable impression.

That being said, let's start with examples coming from logic and abstract algebra and then give a few standard examples form mathematics.

1. We'll begin this enumeration with simple, abstract, but useful examples. The category $\mathbf{0}$ has no node and no arrow. It's the empty category. The category $\mathbf{1}$ has one node and only the identity arrow. The category $\mathbf{2}$ has two nodes and one arrow between them besides the identity arrows. Finally, the category $\mathbf{3}$ has three nodes and three non-trivial arrows, one of them being the composite of the other two.  These can can be pictured as follows:

```tikz
\usepackage{tikz-cd} 
\begin{document}
\begin{tikzcd} 
\bullet \arrow[loop, distance=2em, in=125, out=55]
\end{tikzcd}
\begin{tikzcd} 
\bullet \arrow[loop, distance=2em, in=125, out=55] \arrow[r] & \bullet \arrow[loop, distance=2em, in=125, out=55]
\end{tikzcd}
\begin{tikzcd}
\bullet \arrow[loop, distance=2em, in=125, out=55] \arrow[rr] \arrow[rd] &                                                     & \bullet \arrow[ld] \arrow[loop, distance=2em, in=125, out=55] \\
                                                                         & \bullet \arrow[loop, distance=2em, in=235, out=305] &                                                              
\end{tikzcd}
\end{document}
```
2. Let $(P, \leq)$ be a pre-order, that is a reflexive and transitive relation. As a category, its objects are the points $p, q, r, ...$ of $P$ and there is an arrow $f$ (see below) if and only if $p \leq q$. There is at most one arrow between two nodes. It's easily verified that in this way one gets a category. In particular, any partial order is a category. This suggests immediately that category theory ought to be useful in mereology.

```tikz
\usepackage{tikz-cd} 
\begin{document}
\begin{tikzcd} 
f:p \arrow[r] & q 
\end{tikzcd}
\end{document}
```

3. Consider propositions and logical relations between them, i.e. a deductive system. The nodes are propositions $p, q, r, ...$ and there is an arrow $f$ if and only if $p \vdash q$. One immediately verifies that this is a category.
4. Let $T$ be a first-order theory in a standard first-order language $L$. It is possible to construct a category from $T$ denoted $C_T$  and calls its *syntactic category* or its *category of concepts*. Here is a sketch of the construction.
5. Consider a functional programming language $L$, like Haskell. The nodes of the associated category are the data types of $L$ and the arrows are the computable functions of $L$, e.g. the "programs". This is a purely syntactic construction.
6. The category $\textbf{Set}$ has as its nodes sets and arrows, functions between sets. The category $\textbf{Top}$ of topological spaces and continuous functions between them can easily been seen to be a category. So is the category $\textbf{Grp}$ of groups and group homomorphisms. Given a type of mathematical entity and structure-preserving functions between them, it's easy to see whether they form a category or not.
7. Any monoid $M$ (or group more generally) is a category. It has one object, which we might simply denote by a $\bullet$, and an arrow is simply an element of $M$. Composition of arrows correspond to composition of elements.

## Basic Categorical Constructions
---
Finish category theory stuff later
