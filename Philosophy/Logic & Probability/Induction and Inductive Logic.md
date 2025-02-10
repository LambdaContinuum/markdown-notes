 Inductive reasoning, initially identified with enumerative induction is now more widely understood as any reasoning based on only partial support that premises give to conclusions.

> [!box_name] Enumerative Induction
> Inferring a universal claim from an incomplete list of particular cases

This is a tad too sweeping, for this includes any inconclusive reasoning. A more moderate characterization requires that inductive reasoning not only include generalizations, but also any predictions or explanations obtained in absence of suitable deductive premises.

Inductive logic is meant to provide guidance in choosing the most supported from a given assembly of conjectures.

Approaches to inductive reasoning are so varied that it's difficult to find a specific characterization of all of them. In an attempt to draw at least a partial connection, let's observe the requirements which such a logic is often expected to satisfiy:

- *Connection with deduction:* [[Basic overview of logic|Deductive consequence]] and logical contradiction should fit into an inductive logic as extreme cases of support that a conclusion can obtain from premises.
- *Objectivity:* If premises support the conclusion, this fact depends only on the meaning of the premises and the conclusion.
- *Connection with probability:* Some notion of [[Probability Overview|probability]] should play an important role in the development of inductive logic.

The last two requirements are not universally accepted.

Consider the [[Probability Overview|Kolmogorov axioms]]:

1. $\Pr(p) \geq 0$ for any proposition $p$
2. $\Pr(p) = 1$ if $p$ is necessary
3. $\Pr(p \lor q) = \Pr(p) + \Pr(q)$ if $p$ and $q$ exclude each other

The first attempt to capture the notion of the support that a piece of evidence $E$ gives to a hypothesis $H$ might be to identify it with the probability of the material conditional $E \to H$.

This doesn't work, since $E \to H$ has the same probability as $\neg E \lor H$, which means even if there is no connection between $E$ and $H$, if the probability of $H$ is high enough or the probability of $E$ is low enough, the probability of $E \to H$ is still high. Thus the connection between inductive support and probability must be more sophisticated.

The *received view* is that the degree of confirmation is to be identified with the *conditional* probability of the hypothesis given the evidence. Probability telling us how probabilities are related in not a full theory of confirmation, we need to explain and justify the basic assignment of probabilities to probabilities involved, their probability measure.

The first mathematically developed proposal following this path was put forward by Carnap, we'll start with his approach meant to satisfy all three above-mentioned requirements.

We'll then survey Reichenbach's attempt to satisfy all three requirements.

Then we'll discuss one of the main theories today, [[A User's Guide to Bayes Theorem|Bayesianism]], which drops the second requirement.

Next is Popper's approach which attempts to drop the third requirement.

Finally, we'll discuss the adaptive approach to inductive generalization, which proceeds qualitatively and drops the third requirement, not taking any degrees of confirmation as necessary for inductive inferences.

## Carnap and Induction
---
### *Preliminaries*
The main notion which Carnap's approach to induction is meant to explicate is the logical notion of *the degree of confirmation of a hypothesis H by a given body of evidence E:* $c(H, E)$.

If $E$ is the conjunction of all available observation data, $c(H, E)$ expresses the degree of confidence or belief one should assign to $H$.

Consider a first-order language containing a finite number of logically independent monadic predicates, a finite number of individual constants, and standard Boolean connectives. A *literal* in such a language is either an atomic formula or its negation.

A *state description* in such a language is a conjunction which for any predicate and any constant contains exactly one literal composed of them (e.g. either $Ga$ or $\neg Ga$ but not both).

Thus, a state description for any property and any object says whether this object has this property. Every sentence is logically equivalent to the disjunction of the state descriptions which entail it. If every object in the domain is named by a different individual constant, then the set of all state descriptions exhaust the possible states of the domain as describable in the language.

A *structure description* generated from a given state description $\phi$ is the set of all state descriptions that result from $\phi$ by a permutation of individual constants. Structure descriptions can be interpreted as encoding information about the numerical distribution of properties among objects.

For example: take a language with only one predicate $G$ and only two constants $a$ and $b$. There are four state descriptions:

1. $Ga \land Gb$
2. $Ga \land \neg Gb$
3. $\neg Ga \land Gb$
4. $\neg Ga \land \neg Gb$

and three structure descriptions:

1. $\{Ga \land Gb\}$ ('all objects have property $G$')
2. $\{Ga \land \neg Gb, \neg Ga \land Gb \}$ ('exactly one object has property $G$')
3. $\{\neg Ga \land \neg Gb\}$ ('no object has property $G$')

A *probability measure* assigns probabilities to state descriptions, so that the sum of the probability measures of all state descriptions is $1$. As state descriptions are mutually exclusive, the probability measure of a disjunction of state descriptions is the sum of the probability measures of all disjuncts. 

Each sentence is equivalent to a disjunction of state descriptions, so the probability measure covers all sentences. Given a probability measure $m$, $c(H, E)  = \frac{m(H \land E)}{m(E)}$.

That is, the degree to which evidence E confirms hypothesis H is the proportion of the probability of the hypothesis and the evidence to the probability of the evidence. Thus various confirmation functions arise from various probability measures.

### *Probability Measures $m^{\dagger}$ and $m^{*}$*
One way to define a probability measure is to divide the probabilities equally among the state descriptions. If there are $k$ available (up to logical equivalence) state descriptions, and exactly $n$ of those state descriptions logically imply sentence $H$, the probability of $H$ is defined by $m^{\dagger}(H) = n/k$.

Each state description in our example is assigned the $m^{\dagger}$-value of $1/4$. So, $m^{\dagger}(\neg Ga) = m^{\dagger}(3) + m^{\dagger}(4) = 1/4 + 1/4 = 1/2$. The degree of confirmation of $\neg Ga$ by $Gb$ is also $1/2$: $$c^{\dagger}(\neg Ga, Gb) = \frac{m^{\dagger}(\neg Ga \land Gb)}{m^{\dagger}(Gb)} = \frac{m^{\dagger}(c)}{m^{\dagger}(a) + m^{\dagger}(c)} = \frac{1/4}{1/2} = 1/2.$$
Analogous calculations show that $m^{\dagger}(Ga) = c^{\dagger}(Ga, Gb) = 1/2$. But this shows that observed $Gb$ has no impact on the degree of belief one should assign to $Ga$. 

The problem with this independence generalized. Even for a thousand objects $a_1, a_2, ..., a_{1000}$ the following will hold: $$c(P(a_1), P(a_2)\land ... \land P(a_{1000})) = c(\neg P(a_1), P(a_2)\land ... \land P(a_{1000})) = m(P(a_1))$$
This means that no amount of evidence will have any impact on the level of confirmation of $P(a_1)$.

This led Carnap to consider a different probability measure $m^{*}$. The method of assigning $m^{*}$ is quite simple: first divide probability $1$ equally among the available structure descriptions, thus building in the assumption that each structure description is equally probable. Then, divide the probability of each structure description equally among its members.

In our example. each of the three structure descriptions is assigned probability measure $1/3$. Since (1) and (3) contain exactly one state description, each is assigned probability measure $1/3$. Each element in (2) obtains $1/6$.

To see how this probability measure favors homogeneous descriptions and deals with independence issues, compare the probability measure of $\neg Ga$ with the confirmation of the hypothesis $\neg Ga$ on the evidence that $Gb$. $\neg Ga$ holds in (3) and (4) and hence $m^*(\neg Ga) = m^*(c) + m^*(d) = 1/3 + 1/6 = 1/2$. On the other hand: $$c^*(\neg Ga, Gb) = \frac{m^*(\neg Ga \land Gb)}{m^*(Gb)} = \frac{m^*(c)}{m^*(a) + m^*(c)} = \frac{1/6}{3/6} = 1/3.$$
$c^*(\neg Ga, Gb) < m^*(\neg Ga)$. Similarly, $c^*(Ga, Gb) = 2/3 > m^*(Ga) = 1/2$, so $Gb$ partially confirms $G$a and partially disconfirms $\neg Ga$.

### *The $\lambda$-Continuum of Confirmation Functions*
There is a wide variety of confirmation functions. To see how such a variety arises, consider the following. If $F_1, F_2, .. F_k$ are all monadic predicates of a given language, we say that a $Q$-formula predicates of a constant $a$ is of the form: $$\pm F_1 a \land \pm F_2 a \land ... \land \pm F_k a$$
where each $\pm$ stands either for a negation or for nothing. $Q$-formulas of such a language can be enumerated , let's pick the $i$-th one and call it $Q_i$. One of the key confirmation assignments we would like to calculate is that of $c(H_{Q_i}, E_Q)$ where $H_{Q_i}$ is the $Q_i$-formula predicated of a certain constant $a$ and $E_Q$ is a conjunction of certain $Q$-formulas predicates of some constants different from $a$.

There are at least two important factors in our assessment of $c(H_{Q_i}, E_Q)$:
1. One is the empirical factor of the relative frequency of $Q_i$s in $E_Q: s_i/s$ where  $s_i$ is the number of occurrences (modulo logical equivalences) of $Q_i$ in $E$ and $s$ is the number of non-equivalent $Q$-formulas  in $E$.
2. The other is the logical one: the logical factor of $Q_i$ equals $1/K$, where $K$ is the number of all $Q$-predicates of the language.

Following Carnap, $c(H_{Q_i}, E_Q)$ should be somewhere between these two values. A convenient way of representing this is to take it to be their weighted mean defined by: $$c(H_{Q_i}, E_Q) = \frac{\frac{w_1s_i}{s} + \frac{w_2}{K}}{w_1 + w_2}$$
where $w_1$ and $w_2$ are weights. Since what matters is the ratio of the weights, one of them can be parameterized. Carnap suggested parameterizing $w_1$ and taking it to be $s$, thus making sure that the empirical factor gains weight as more observations are being made. The other weight is usually represented as $\lambda$: $$c(H_{Q_i}, E_Q) = \frac{s_i + \lambda/K}{s + \lambda}$$
Any choice of $\lambda$ gives a new confirmation function. Consider what happens when we take $\lambda = 0$. In this case: $$c(H_{Q_i}, E_Q) = \frac{s_i + 0/K}{s + 0} = s_i/s$$
Suppose that there are only three constants, $a, b, c$ and only one predicate $F$ and that we so far observed only two of them, which turned out to be $F$. What are the confirmation values of the hypothesis that the last object will also be $F$ and of the other hypothesis, if $\lambda = 0$?

$$\begin{align}c(Fc, Fa \land Fb) &= s_F/s = 2/2 = 1\\ c(\neg Fc, Fa \land Fb) &= S_{\neg F}/s = 0/2 = 0\end{align}$$
If however, one observed object is $F$ and another one isn't, we get: $$c(Fc, Fa \land \neg Fb) = s_F/s = 1/2$$
In this sense, for $\lambda = 0$ assigns maximal role to the evidence and no role whatsoever to the logical possibilities (It corresponds to Reichenbach's straight rule).

To compare, consider what happens as $\lambda$ approaches $\infty$: in the limit our function yields $1/K$. So, no matter whether we observed any other objects which are $F$, the confirmation of the hypothesis that the next object will be $F$ is just the prior logical probability of that hypothesis: $$c(Fc, Fa \land Fb) = c(Fc, \neg Fa \land \neg Fb) = m(Fc) = 1/2$$
So taking $\lambda = \infty$ assigns maximal importance to the logical factor and no role to the evidence and does not allow for learning from experience. This confirmation function thus defined is $c^{\dagger}$, which was already discussed.

The above choices of $\lambda$ are two extremes of a continuum of confirmation functions, where the lower the $\lambda$ the more important the impact of evidence on the confirmation value of the hypothesis. One may ask where is $c^*$ in this continuum? It's obtained by equating $\lambda$ to $K$, which yields the following: $$c(H_{Q_i}, E_Q) = \frac{s_i + K/K}{s + K} = \frac{s_1 + 1}{s + K}$$
### *Challenges and Tweaks*
One difficulty is the above framework provides a variety of probability measures without indicating why we should prefer any of them over the others. 

Some see this is a serious challenges, others more moderate point out that given certain basic restrictions (Most notably, regularity (every state description has a non-zero probability) and symmetry (complete permutations of individual constants and predicates of the same type do not change the value of the function)) even if the confirmation function is not unique, quite a few useful claims hold no matter which non-extreme function we pick.

Initially, Carnap felt quite strongly about $m^*$ but came to accept a somewhat subjectivist attitude consisting in saying that there is a wide variety of options which remain open, even after all methodological considerations have been brought it.

Some see nothing wrong in relativizing confirmation to probability measures and using the logically objective "given such-and-such probability measure, the confirmation degree in this case is...". It's been compared to special relativity theory, in which it is not velocity, but rather velocity with respect to a frame of reference that is objective.

Another problem with Carnap's inductive logic is it's not very successful at handling reasoning by analogy. Intuitively, the more primitive properties two objects share, the more likely it should be that they would agree on other properties. Yet $c^*$ fails to capture this intuition.

For instance, suppose we have a language with two predicates $F$ and $G$ and two constants $a$ and $b$. If reasoning by analogy worked, then the fact that $Fa \land Fb \land Ga$ should give more support to the hypothesis that $Gb$ than just the evidence $Ga$: $$c^*(Gb, Fa \land Fb \land Ga) > c^*(Gb, Ga)$$
And yet, that isn't true, because in this case both degrees of confirmation are equal! Carnap attempted to deal with such issues by introducing a new parameter, $\eta$, but the success is quite limited.

Once we generalize the notions to infinite domains, Carnap's inductive methods a priori assign zero probabilities to universal generalizations. This is considered a problem because usually laws of nature are taken to be universal and if it were true that no finite evidence can provide support for any universal statement, this would go against our intuitions that certain scientific hypothesis are better confirmed than others.

The requirements put on confirmation functions can be modified to allow for non-zero probabilities of universal generalizations and
some attempts to give a systematic account of non-zero probabilities of universal claims have been put forward. Most notable are those by Hintikka, who introduced yet another parameter $\alpha$ dependent on the number of constants available in the language to contribute to the non-zero confirmation of universal claims.

There are worries that on a Carnapian account nothing warrants the relevance of the evidence to the hypothesis, and irrelevant evidence may highly confirm a hypothesis just because the hypothesis is highly likely or the evidence highly unlikely.  Fitelson suggests the only historically proposed definition of confirmation that obeys certain basic relevance requirements is that of Kemeny and Oppenheim, which identifies it with: $$\frac{\Pr(E \mid H) - \Pr(E \mid \neg H)}{\Pr(E \mid H) + \Pr(E \mid \neg H)}$$
Goodman posed a challenge to purely syntactic approaches to confirmation. Say we've drawn a marble from a certain bowl on each of the past ninety days and they all have been red. It seems, the evidence that the first ninety marbles were red increased the confirmation of the hypothesis that the next one will be red as well. But take another predicate, $S$, defined as "drawn up to today and red, or drawn after today and blue." Our evidence tells us that the ninety marbles observed so far were S, and so, if Carnapian theory was adequate, that the next one will be S too. This is clearly not the case (?), our evidence does not confirm the hypothesis that the next marble will be blue. The lesson here is which predicates can be sensibly used in inductive reasoning is an extralogical issue.

Carnap set out to solve the problem of confirmation in terms of logical probability, expecting there would be a single adequate probability measure. After 1952, it turned out that he had to justify a choice of a probability measure. The only sensible way of achieving this which he saw was in terms of empirically motivated methodological consideration.

He turned his program upside down. For instance, choosing different $w_1$ leads to a new variety of measures and parameterizing on $s$ already presupposed that induction is justified (for example, weighing it with $1/s$ leads to an anti-inductive measure).

## Reichenbach's Straight Rule and Pragmatic Justification
---
Reichenbach identifies the probability of an event with the limit of the relative frequency of events of the same kind. Give that we normally observe only finite sequences of events, the question arises as to how we are to assess the relative frequency at the limit and how our general strategy of achieving this is to be justified.

Reichenbach's response to the first question is that we should apply what he calls that *straight rule* (SR), which says that one should take observed relative frequencies to be the limiting relative frequencies (and adjust as new observations are made).

Reichenbach attempts to motivate the SR, and hence induction, with the following considerations:
1. Either there is an inductive method which succeeds or there is none.
2. If there is none, we do not lose anything by using SR.
3. If there is one, then SR will succeed as well.

This justification is problematic because there are many inductive methods which agree with SR on past success ratio, vary from it in predictions about the future which they legitimize at any finite point, and converge on the same value.

Reichenbach provides no way of picking SR from among its rivals.

A related difficulty is that the type of convergence involved in SR is somewhat weak because if one wants to obtain knowledge about infinitely many probabilistic relations there might be no single upper limit on the number of observations that have to be made even if for each such relation an upper limit exists.

## Bayesian Approaches to Induction
---
### *Bayesianism and Subjective Probability*
The "embarrassment of riches" which haunts the Carnapian objectivist program is embraced by Bayesians. While the logical approach faces the difficulty of finding a justification for a specific choice of initial probabilities, the personalistic Bayesians take the choice of initial probabilities to be an extralogical (and personal) issue.

For them, an important task of a formal theory of inductive reasoning is to explain how, given certain initial degrees of belief, one has to revise their commitment when faced with new evidence.

An important role in updating beliefs in face of new evidence is played by a theorem of probability theory called [[A User's Guide to Bayes Theorem|Bayes’ Theorem]].

### *Arguments for Bayesianism*
Why would a rational agent's degree of beliefs satisfy the axioms of probability? The claim is supported by considerations meaning to show that acceptance of the axioms of probability theory is required to avoid being susceptible to sure loss.

A Dutch Book against an agent is a bet (or a series thereof) which, collectively taken, the agent has to lose. Agents are called *coherent* if they are not susceptible to a Dutch Book. It's been proved that if one's degrees of belief do not comply to the axioms of probability theory, one is not coherent. The implication in the opposite direction also holds.

If you worry that grounding an epistemic standard in pragmatic considerations is inappropriate consider a class of arguments developed from the perspective of *epistemic utility theory*.

Think of truth as $1$ and falsehood as $0$. Pick a measure of distance between a given degree of belief and the given sentence's truth-value (for example, squared difference). The lower the score, the greater the accuracy of your belief. Define some sensible way of aggregating inaccuracies of one’s beliefs into one global measure of inaccuracy.  Now, *Accuracy theorem* is available to the effect that if a set of degrees of beliefs violates the axioms of probability, there is a set of probabilistic degrees of belief which are more accurate, no matter what truth-values the beliefs have, and the *Converse accuracy theorem* says that no probabilistic set of beliefs is so dominated by a non-probabilistic one. From this perspective, not being Bayesian is irrational, because it entails being further from the truth, no matter what the truth is.

### *Challenges to Bayesianism*
- Bayesianism does not say anything about the choice of initial probabilities of $E$, of $H$, and so on, so the same evidence might legitimately motivate two researches to assign quite different probabilities to a hypothesis, if their initial probabilities are sufficiently different.
	- The Bayesian response to this difficulty is that one can prove that as the amount of evidence increases, probabilities assigned to relevant hypotheses will converge almost independently of what the initial subjective probabilities are. The problem is that
	1. This works only if the initial subjective probabilities are not $0$ or $1$, and,
	2. Extreme initial probabilities (close to $1$ or $0$) prevent rapid converges and make the further search for evidence practically useless.
- In actual reasoning, rational agents rarely can assign or even decently approximate subjective probabilities to the relevant factors, and its unclear whether betting preferences are a sufficient and correct way of discovering the priors.
- If $\Pr(E) = 1$. then $\Pr(H \mid E) = \Pr(H)$, so old evidence cannot confirm any hypothesis eve if one realizes now that the evidence is relevant for the hypothesis, for example because it is implied by it (this is called *the problem of old evidence*). Some try to avoid it by weakening the assumption that agents are logically omniscient, but it's not clear what modifications of the Bayesian formal apparatus this move entails.
- Bayesianism in a sense disregards the structure of explanation and does not take into account such factors as its simplicity or the unity of the underlying theory. That is, all that is considered when we evaluate a given theory is our prior probabilities and available evidence in its favor: factors like simplicity or unity intuitively important for the evaluation of a theory, are not explicitly considered in the evaluation procedure. Sure, one can take these factors to be incorporated among prior probabilities, but if that is the case, bayesianism does not really explain how these factors are to be assessed and sweeps them under the carpet of unexplained prior belief degrees.
- Bayesianism tells a story about rationality and its relation to betting behavior. Yet, it does not say much about why being rational in this sense should put one in an epistemologically privileged position. Why does the fact that I obey rules which would help me to avoid a Dutch Book result in Bayesian updating being the best way to go about scientific reasoning? It is not immediately clear why scientific success and winning bets should be related.
- Conditionalization does not follow from Bayes’ Theorem and is not justified as an a priori rule of rationality. It does not follow from Bayes’ Theorem, because one can obey Bayes’ Theorem at each moment while completely changing one’s degrees of beliefs between moments. Nor does it seem a priori, because it is diachronic, which means that it incorporates a prediction about what will happen at a later time based on what has happened so far (and such moves are usually not considered a priori since Hume). Some diachronic Dutch Book arguments have been given by David Lewis, but they rely on stronger assumptions which themselves do not seem a priori.
- The claim that rational agents should obey the laws of probability implies their logical omniscience (insofar as deductive logic is involved). This difficulty Bayesianism shares with many formal approaches to epistemology. 
	- A twist to this problem is that once classical logic becomes the underlying logic, Bayesianism is unable to account for the possibility of the underlying logic being revised and to explain how evidence might motivate a change of underlying logic.

Given a variety of troubles that a fully subjectivist approach to priors encounters, various unorthodox versions of Bayesianism are being put forward which try to put some additional constraints on priors without running into the problems that fully objectivist and syntactical accounts run into.

## Popper
---
For Popper, the central mechanism of scientific methodology is falsification. Popper rejects the idea of confirmation in the sense in which it was used before here. No finite set of observational data can justify one to raise one's degree of belief in a theory; a single falsification to the contrary justifies one's rejection of the theory. Popper rejects the very idea of inductive logic, all logic is deductive.

Popper considered Carnap's $m^{\dagger}$ as the only methodologically acceptable measure function for logical probability. All other measure functions can only be justified by non-logical considerations. So any occurrence of $\Pr$ in this section should be interpreted in terms of $m^{\dagger}$.

Testing a theory means trying to bring about an observable fact that falsifies the theory. So the first question for Popper's methodology is which theories one should test first. A theory is *falsifiable* if a possible observable fact contradicts. [[The Duhem Thesis and the Quine Thesis|Non falsifiable theories]] are deemed unscientific.

A theory is more falsifiable to the extent that more logically possible facts contradict it. This brings Popper to two criteria: generality and specificity: 
1. A hypothesis is more general to the extent that it concerns a logically larger set of objects
2. It is more precise to the extent that it species more about those objects.

For example, where $P, Q,$ and $R$ are logically independent predicates, $\forall x(Px \to Qx)$ is more general than $\forall x ((Px \land Rx) \to Qx)$: the former is contradicted by every sentence of the form $P\alpha \land \neg Q \alpha$ whereas the latter is only contradicted by sentences of the form $P\alpha \land R\alpha \land \neg Q\alpha$.  But $\forall x(Px \to (Qx \land Rx))$ is more specific than $\forall x (Px \to Qx)$: the former is contradicted by sentences of the form $P\alpha \land \neg Q \alpha$  and $P\alpha \land \neg R \alpha$ whereas the latter is only falsified by the former sentences.

Popper identifies the *content* of a sentence $A$ with the falsifiability of $A$ and measures it.

Needless to say, $m^{\dagger}$ is unable to capture the differences between the general sentences from the previous paragraph if the domain is infinite. All those sentences have probability zero. These probabilities are defined by a limit for the number of elements of the domain going to infinity. Popper introduces a "fine-structure of probability". Even if $\Pr(A) = \Pr(B) = 0$, it's possible that $\Pr(A \mid B) > \Pr(B \mid A)$, and this indicates that $B$ has a higher content than $A$.

The objective is clear: formualte and test *bold hypotheses*. If the hypothesis survives the tests, one obtains a corroborated informative hypothesis. If it fails, one may still move to a non-falsified hypothesis that has the next highest content (degree of falsifiability). Of course, no single (non-falsified) hypothesis has the highest content.  Popper let's people decide.

To compare theories, Popper introduced the notion of *versismilitude* or *truthlikeness*. Its qualitative version is as follows: Take an interpreted theory $T$ and let $T^1$ ($T^0$) be the set of its true (false) sentences. $T$ is more truthlike than a theory $S$ iff both $S^1 \subseteq T^1$ and $T^0 \subseteq S^0$, and either $S^1 \neq T^1$ or $T^0 \neq S^0$.

> [!box_name] Versismilitude
> A theory to be more truthlike has to surpass the other in its truth content without surpassing it in its falsity content, or to have a smaller falsity content without being ahead in its truth content.

Suppose then some theories survived the imposed tests. How good are they? Here too, Popper formulates a measure which he calls the degree of corroboration of a hypothesis: $$C(H, E) = \frac{\Pr(E \mid H) - \Pr(E)}{\Pr(E \mid H) - \Pr(E \land H) + \Pr(E)}$$
Where $E$ is the conjunction of all available empirical evidence, the degree of corroboration of the hypothesis $H$ is proportional to the difference between the probability of the evidence given the hypothesis and the absolute probability of the evidence. The denominator is a normalizing factor which keeps the values between $-1$ and $+1$. If $E$ contradicts $H$, $\Pr(E \mid H) = \Pr(E \land H) = 0$. So the degree of corroboration of $H$ is $-1$ indicating the $H$ is falsified. The maximal value to which $H$ may be corroborated is obtained if $E$ is identical to $H$. This will apply if $H$ is a singular statement or if, being God, you see that $H$ obtains.

The maximal degree to which a hypothesis $H$ may be corroborated is the content of $H$ (the falsifiability degree of $H$.) The higher the content of a hypothesis, the higher its potential degree of corroboration.

Popper stresses that the corroboration of $H$ is only significant if $H$ was subjected to the severest possible tests. We have seen before that these are the tests that are most likely to falsify the hypothesis. That Popper never offered a formal criterion for this, is presumably related to a weak spot in his formalisms.

Intuitively, repeating an experiment that did not lead to falsification is not a severe test. But why is that? Apparently because, in view of previous instances of the test, the next instance is likely not to lead to falsification. But why is that so? Apparently this conclusion can only be drawn if we presume that the outcome of the next instance of the test is likely similar to the outcome of previous instances.

To presume so, however, is to presume a measure function different from Carnap’s $m^{\dagger}$, viz. one that assigns a non-zero weight to the empirical factor. And this Popper does not want.

Indeed, Popper always stressed that a (non-falsifying) degree of corroboration of $H$ should not affect our degree of rational belief in $H$ . He nevertheless advised one to use the best tested theory as basis for action, and some take this to mean that the degree of rational belief of those theories is raised. Popper tried to remove this confusion. He distinguished preferring the best tested theory as basis for action from relying on that theory. Preferring such theory is justified, because of the merits the theory proved to have in the past. But this says nothing about the future. So we cannot rely on the theory; no theory was shown true or can be shown true. Our present most corroborated theories embody the best knowledge available today. Only fools take alternative theories as better. But even our best theories may be falsified tomorrow.

