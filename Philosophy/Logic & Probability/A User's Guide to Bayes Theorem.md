## 1. What is Bayes' theorem?
---
An equation for calculating probabilities. It strictly follows from the axioms of probability theory. It's also:
- A tool for updating beliefs in light of new evidence
- A tool for assessing the probability of various hypotheses in light of data.
	- Confirmation and dis-confirmation
- A formal constraint on rational credences.
## 2. Key background
---
### 2.1 Belief and Credence
**Propositional attitude**: An attitude that an agent adopts toward a proposition.

**Propositions**: Meanings of declarative sentences, bearers of truth value.

For example, "The apple is red" **expresses the proposition** \<the apple is red\>
##### Belief
Belief is **purely representational** - it simply represents the way the world is according to the agent.

**Doxastic attitudes**: Propositional attitudes that are belief-like in that they are purely representational.
- Includes: Belief, disbelief, certainty, doubt, suspension of belief/judgement, credence, etc.

##### Credences
**Credence**: An agent's degree of confidence in proposition
- Also known as degree of belief
- Range from $0\%$ to $100\%$

Beliefs are **binary**, credences are **not**.

##### Why beliefs and credences?
- Introspection
	- It just seems introspectively obvious that we find ourselves with different degrees of confidence in different propositions. They aren't binary, it's gradient, sometimes we find ourselves believing strongly, sometimes we believe but are very open to being swayed, etc.
- Explanatory power
	- Unable to account for many facts of agent's doxastic lives with just beliefs. We need credences to explain these various facts.
	- Differences in risk-involving decisions
	- New evidence, same belief.

Note: There's some idealization and simplification involved. But there's also utility and approximate accuracy.
### 2.2 Interpretations of probability
**Probability**: $P(p)$ or $Pr(p)$
**Credence**: $cr(p)$
**Objective probability**: Mind-independent features of reality
- For, instance there might be an objective probability of $50\%$ that an in-deterministic atom will decay within the next hour. This probability doesn't depend us.
- It's not a measure of our credence or degree of belief. Rather, it's a matter of some objective feature of the atom itself. Maybe it's a propensity or tendency inherit to it, maybe it's a statistical fact about the frequency of decays among atoms of its kinds. Maybe it's something else entirely. What matters is it's mind-independent.
**Subjective probability**: Mind-dependent
- One dominant way of understanding this type of probability is just identifying it with credences.
- Some think this distinction is confused.

##### Interpretations
- Before we continue, note that some people argue that all probability claims is captured by just one of these interpretations.
- It's plausible that in different contexts we use different notions of probability. Sometimes we talk about frequencies, sometimes we talk about propensities, sometimes we talk about rational credences, etc.
- We leave out the "classical" interpretation because it fell out of a favor. According to that view, probability is counting the number of favorable outcomes out of the number of total outcomes.


- **Propensity**: Probabilities are objective tendencies or propensities for certain outcomes.
	- Propensities are roughly degree's of causal influence. Different sets of causal factors have stronger or weaker tendencies to produce certain outcomes.
	- Probabilities measure the strength of those tendencies or propensities.
	- Arguably the notion of probability at play in quantum in-determinism. If so, when we say a radioactive atom has a 50% probability of decaying in a given time period, we're attributing to the atom a certain quantitative propensity, tendency, inclination, etc to decay. It would still exist even if agents with credences never existed.
- **Frequency**: Probabilities are actual or hypothetical frequencies of certain outcomes/events under certain conditions.
- **Actual credence**: Probability are **actual** credences.
	- Probabilities are always indexed to agents.
	- Thoroughly mind-dependent.
- **Rational credences**: Probabilities are **rational** credences.
	- The credence an agent **should** have in light of the evidence.
	- Is this an objective or subjective understanding of probability? There's elements of both.
- **Degree's of Support**: Probabilities are mind-independent, degreed relations of support between propositions.
	- Determine which credences are rational, but they themselves aren't credences.
	- Under this account, the unconditional probability of a proposition is the degree to which the proposition is supported by *a priori* truths and tautologies.
- **Degree's of Justification**: Probabilities are degrees of justification that propositions have in light of an agent's current evidence.
	- Differs from rational credence because it isn't saying probabilities are rational degree's of belief, instead probabilities are degree's of justification. One can think they come apart.
	- So a proposition has a probability of 1 just in case we have conclusive justification for believing it.

- there are other flavors, these are the main ones.
##### Epistemic Probabilities
The probabilities we reason about in **epistemic contexts**
- **Epistemic context**: a context in which we reason about things like...
	- how probable a scientific theory is
	- how strongly a theory predicts some evidence
	- to what degree evidence confirms a theory/hypothesis
	- etc.

It's then an open question which of the above understandings of probability, epistemic probability should be identified with.

##### Epistemic probability = ?
Hildebrand and Metcalf:
- **Subjective epistemic probabilities**: describe your personal credence in the relevant propositions.
- **Objective epistemic probabilities**: describe how strongly you **ought** to believe the propositions given your total evidence.

Huemer: **degrees of justification**

Climenhaga: **degrees of support**

### 2.3 Bayesian Epistemology
**Bayesian Epistemologists** study norms governing credences, including how credences should change in response to a varying body of evidence.

Any **Bayesian epistemology** characteristically endorses two principles:
1. Agents have certain doxastic attitudes - **credences** - that can usually be represented by assigning real numbers to propositions.
2. **Rational requirements** on those credences can be represented by **mathematical constraints** on the real-number assignments **given by the [[Probability Overview|probability calculus]]**.

##### Core normative rules
- Kolmogorov's three probability axioms
- Ratio Formula
- Conditionalization principle
#### 2.3. Important note
We'll articulate the norms in terms of probability instead of just credences. This better depicts that we're demonstrating rational norms instead of just actual credences.
#### 2.3.2 Kolmogorov's axioms
1. **Non-Negativity**: For any $p$, $P(p) \geq 0$.
2. **Normality**: For any tautology $T$, $P(T) = 1$.
3. **Finite Additivity**: For any mutually exclusive propositions $p$ and $q$, $P(p \lor q) = P(p) + P(q)$.

These axioms generate the following consequences:
- $P(\neg p) = 1 - P(p)$
- **General Additivity**: $P(p \lor q) = P(p) + P(q) - P(p \land q)$.
- **Maximality**: For any $p$, $P(p) \leq 1$.
- **Contradiction**: For any contradiction $F$, $P(F) = 0$.
- **Entailment**: For any $p$ and $q$, if $p$ logically entails $q$, then $P(p) \leq P(q)$.
- **Equivalence**: For any $p$ and $q$, if $p$ logically entails $q$ and if $q$ logically entails $p$, then $P(p) = P(q)$.
- **Finite Additivity**: For any finite set of mutually exclusive propositions $\{p_1, p_2, ..., p_n\}, P(p_1 \lor p_2 \lor ... \lor p_n) = P(p_1) + P(p_2) + ... + P(p_n)$.

##### Dutch Books
What's so irrational about flouting these constraints? There's nothing in psychology that rules out the possibility of an agent violating these constraints.

A **Dutch Book** is a set of bets which guarantee that the gamblers lose money no matter the outcome.
- Someone's credence: $P(\text{It will rain}) = 0.6$ and $P(\text{it won't rain}) = 0.6$
	- They'll pay $60$ cents to win $\$1$ on rain and $60$ cents to win $\$1$ on no rain.
	- But then they're guaranteed to lose money - they pay $\$1.20$ but only win $\$1$
Since it seems clearly irrational to adopt attitudes that guarantee you lose, and that a dutch book can be constructed to work on you if your credences don't abide by the probability axioms, it follows that any rational agent will have degrees of belief that conform to the axioms of probability.
#### 2.3.3 Ratio Formula
**Conditional probability**: The probability of one proposition being true on the assumption of another proposition being true.

$$\text{Ratio Formula: For any }p \text{ and } q, P(p \mid q) = \frac{P(p \land q)}{P(q)}, 
\text{ where } P(q) > 0.$$
#### 2.3.4 Conditionalization Principle
When you acquire new evidence, you should update your beliefs that the evidence bears on by **conditionalization**.

That basically just means that when you learn a new information $E$, your new $P(H)$ should equal your old $P(H \mid E)$.

**Conditionalization**: If your old conditional probability $P_{\text{old}}(p \mid q) = x$, and you come to know $q$, then the $P_{\text{new}}(p) = x$.

More formally:

**Conditionalization**: For any time $t$ and later time $t^*$, if proposition $E$ represents everything an agent learns between $t$ and $t^*$, and if $P_{t}(E) > 0$, then for any proposition H, $$P_{t^*}(H) = P_t(H \mid E)$$ where $P_t$ and $P_{t^*}$ are the agent's probability distributions at two times.

Bayes' theorem offers us a way to **calculate** the $P_t(H \mid E)$. So: **Conditionalization**, together with Bayes' Theorem, gives the rational way to update our beliefs and confirm/dis-confirm our theories in light of new evidence.

#### 2.3.5 Subjective vs. Objective Bayesianism

Different ways to articulate the distinction, but an essential way (sometimes known as the normative distinction) is in what rational constraints they put on credences.
##### What are the rational constraints on credence?
**Subjective Bayesians**: The $5$ core normative rules expressed above.
**Objective Bayesians**: The $5$ core normative rules expressed above + further constraints.
## 3. The theorem
---
### 3.1 Standard forms
$$\text{Bayes' Theorem: For any H and E, }P(H \mid E) = \frac{P(E \mid H)P(H)}{P(E)}$$
- E is some piece of data/evidence
- H is some hypothesis
- P(H|E) is the posterior probability of H
- P(E|H) is the likelihood of H
- P(H) is the prior probability of H (different from the intrinsic probability)
- P(E) is the probability of the evidence itself

**Proof**:
1. $P(H \mid E) = \frac{P(H \land E)}{P(E)}$ from Ratio Formula
2. $P(E \mid H) = \frac{P(E \land H)}{P(H)}$ from Ratio Formula
3. $P(H \mid E)P(E) = P(H \land E)$ from 1
4. $P(E \mid H)P(H) = P(E \land H)$ from 2
5. $P(H \land E) = P(E \land H)$ from Equivalence
6. $P(H \mid E)P(E) = P(E \mid H)P(H)$ from 3-5
7. $P(H \mid E) = \frac{P(E \mid H)P(H)}{P(E)}$ from 6

Another formulation: $$\text{Bayes' Theorem: For any H and E, } P(H \mid E) = \frac{P(E\mid H)P(H)}{P(E\mid H)P(H) + P(E\mid\neg H)P(\neg H)}$$
Meaning: $$P(E) = P(E \mid H)P(H) + P(E \mid \neg H)P(\neg H)$$
Three things determine the posterior probability of H:
1. It's proportional to the prior probability of H, the more probable the hypothesis starts out, the more probable it ends out. This supports the claim "extraordinary claims require extraordinary advice." If you started with a plausible hypothesis not as much evidence is needed to be believable.
2. It's good if the likelihood of H is high, if you want to support a theory, you want the theory to strongly predict some possible evidence, where the evidence then occurs. To strongly predict something is to imply that thing is quite likely.
3. It's good if the probability of E is quite low, you can see that if the probability of E is lowered, the probability of H given E goes up. Ideally, we want a theory that strongly predicts evidence that is otherwise highly unlikely. That's a straightforward path to strong confirmation.
### 3.2 Odd form
$$\textbf{Odds Form: }\frac{P(H\mid E)}{P(\neg H\mid E)} = \frac{P(E \mid H)}{P(E \mid \neg H)} \times \frac{P(H)}{P(\neg H)}$$
**Slogan**: The **posterior odds** equals the **likelihood ratio** times the **prior odds**.
- **Left**: ratio of the posteriors, posterior ratio, posterior odds
- **Middle**: likelihood ratio, Bayes factor, relative likelihoods
- **Right**: ratio of the priors, prior ratio, prior odds 
### 3.3 Evidence
**E is evidence for H** just in case $P(H \mid E) > P(H)$.

$P(H \mid E) > P(H)$ just in case **the likelihood ratio is greater than $1$** - i.e., just in case $P(E\mid H) > P(E \mid \neg H)$.

1. $\frac{P(H\mid E)}{P(\neg H\mid E)} = \frac{P(E \mid H)}{P(E \mid \neg H)} \times \frac{P(H)}{P(\neg H)}$ Odds Form
2. $\frac{P(H\mid E)}{P(\neg H\mid E)} = \frac{P(E \mid H)}{P(E \mid \neg H)} \times \frac{k}{1-k}$
3.  $\frac{P(H\mid E)}{P(\neg H\mid E)} = \frac{k}{1-k}$ if you let the likelihood ratio be $1$.

If the likelihood ratio is $1$ then the posterior ratio is the same thing as the prior ratio. The absolute value of $P(H \mid E)$ is $k/(k + (1-k))$ which is just $k$. So $P(H \mid E) = P(H) = k$ so when the likelihood ratio is $1$, E isn't evidence for H.

Suppose the likelihood ratio is greater than $1$, say $2$ in this case.
1. $\frac{P(H\mid E)}{P(\neg H\mid E)} = 2 \times \frac{k}{1-k}$
2. $\frac{P(H\mid E)}{P(\neg H\mid E)} = \frac{2k}{1-k}$

Note that we've increased the numerator by a factor of 2 while keeping the denominator the same, hence we've doubled the odds of $P(H \mid E)$ in relation to $P(\neg H \mid E)$. Hence, the $P(H \mid E)$ is higher when the likelihood ratio is 2 compared to when the likelihood ratio is 1.

This easily generalizes to any likelihood ratio greater than 1, and since we've seen for a likelihood ratio of $1$, $P(H \mid E) = k$ when the likelihood ratio is greater than 1, $P(H \mid E) > k$ and hence $P(H\mid E) > P(H)$.

By parity of reason we can demonstrate that $P(H \mid E) < P(H)$ when the likelihood ratio is less than $1$.

##### The core point
The likelihood ratio, $\frac{P(E \mid H)}{P(E \mid \neg H)}$, is the key to evidence.
- When the likelihood ratio is $>1$, $P(H \mid E) > P(H)$ and hence E is evidence for H
- When the likelihood ratio is $<1$, $P(H \mid E) < P(H)$ and hence E is evidence against H
- When the likelihood ratio is $=1$, $P(H \mid E) = P(H)$ and hence E is irrelevant to H

##### Another equivalent way to think about evidence
1. $P(H \mid E) = \frac{P(E \mid H)P(H)}{P(E)}$
2. therefore $P(H \mid E) = \frac{P(E \mid H)}{P(E)}P(H)$

Under what condition is $P(H \mid E) > P(H)$? Just when $P(E\mid H) > P(E)$.

So: H renders E more probable than E would be otherwise. When that happens, **E is evidence for H**.

## 4. Common mistakes
---
##### Base rate fallacy - or, ignoring priors.
Recall the odds form: $\frac{P(H\mid E)}{P(\neg H\mid E)} = \frac{P(E \mid H)}{P(E \mid \neg H)} \times \frac{P(H)}{P(\neg H)}$

Note the posterior ratio is a function of the likelihood ratio and the prior ratio. Often times we'll ignore the prior ratio when determining the posterior ratio and that's disastrous, since even if the likelihood ratio is very top heavy, the prior ratio can be very bottom heavy and by ignoring the prior ratio we'll incorrectly conclude the posterior ratio is top heavy and hence the posterior probability of the hypothesis is high after conditionalizing on the evidence. 

##### Evidence for H vs. Making H probable
Just because E is evidence for H doesn't mean that H is probable. It just means that E raises the probability of hypothesis.

##### Ignoring the total evidence requirement
When assessing the overall probabilities of hypotheses, we should take into account all of the relevant evidence at our disposal instead of just some proper part of that evidence.

##### Fallacy of understated evidence
Paul Draper argues that many evidential arguments for theism are guilty of appearing convincing only because they understate the evidence.

They identify some general fact about some topic that is more surprising on naturalism than on theism, but ignore other more specific facts about that topic, facts that, *given the general fact*, are significantly more surprising on theism than on naturalism.

##### Confirmation is comparative
Recall that E is evidence for H iff $\frac{P(E \mid H)}{P(E \mid \neg H)} > 1$.

Notice this is essentially comparative. Even if E is very improbable under H, it can stil be powerful evidence for H. What matters is E is more probable under H than it is on the negation of H.

Another mistake kind of related is demanding strict precise numerical likelihoods of the data conditional on the hypothesis. When you have the comparative nature of Bayesian confirmation in mind, you can see that isn't strictly necessary.  

Swinburne writes: "To accept that Bayes's theorem governs all claims about the support given by evidence to hypotheses does not involve holding that the various probabilities can be given exact numerical values (and, as I noted earlier, inductive probabilities do not normally have exact numerical values.). One can think of them as having rough values, values within certain limits; and the theorem, as putting limits on the values of some probabilities, given the limits on others."

##### Evidential Symmetry
If E is evidence for H, then ~E is evidence against H. This follows from Bayes' Theorem.

1. Suppose E is evidence for H. That is $\frac{P(E \mid H)}{P(E \mid \neg H)} > 1$
2. Say that  $\frac{P(E \mid H)}{P(E \mid \neg H)} > \frac{x}{x-n}$
3. Note that $P(E \mid H) + P(\neg E \mid H) = 1$
4. So $P(\neg E \mid H) = 1 - P(E \mid H)$
5.  $P(\neg E \mid \neg H) = 1 - P(E \mid \neg H)$
6. So $\frac{P(\neg E \mid H)}{P(\neg E \mid \neg H)} = \frac{1-x}{1-(x-n)} = \frac{1-x}{1-x+n} = \frac{(1-x)}{(1-x) + n} < 1$
7. Therefore $\frac{P(\neg E \mid H)}{P(\neg E \mid \neg H)} < 1$

This means: $$\text{If }\frac{P(E \mid H)}{P(E \mid \neg H)} > 1 \text{ then } \frac{P(\neg E \mid H)}{P(\neg E \mid \neg H)} < 1.$$
Since the likelihood ratio is less than $1$, we've proven that if E is evidence for H, then ~E is evidence against H.

##### Strength Asymmetry
Consider the following:
- E = The star spells out the first 14 verses of John
- T = Theism, ~T = Atheism.

- $P(E \mid \neg T) =$ $1$ in a billion $= 0.000000001$
	- So $P(\neg E \mid \neg T) = 0.999999999$ 
- $P(E \mid T) =$ $1$ in a million = $0.000001$
	- So $P(\neg E \mid T) = 0.999999$

Say we observe $E$, the Bayes factor indicating the strength of the evidential confirmation of theism is: $$\frac{P(E \mid T)}{P(E \mid \neg T)} = \frac{0.000001}{0.000000001} = \frac{1000}{1} = 1000$$
That's very powerful evidence. Say we observe $\neg E$, the Bayes factor indicating the strength of the evidential confirmation of the $\neg T$, Atheism is: $$\frac{P(\neg E \mid \neg T)}{P(\neg E \mid T)} = \frac{0.999999999}{0.999999} = 1.000000999$$
##### Unfalsifiable (non-disconfirmable) theories
If there is nothing in principle that could disconfirm or count as evidence against a hypothesis, there's nothing in principle that could confirm or count as evidence for the hypothesis.

This follows from evidential symmetry.

##### Likelihood ratio rigging
- **Likelihood ratio rigging**: Baking into your hypothesis something that entails or strongly probabilifies the data.
	- **Problem**: Often you're just purchasing predictive power at the cost of correspondingly lowering the prior probability of your hypothesis.
	- **No probabilstic headway has been made.** The posterior probability of H is going to be the same after modifying your evidence.
 
## 5. Conclusion
**Bayes' Theorem is really important.** It gives us a rigorous and formal way of updating our beliefs in light of the evidence.