# Beliefs about the future
---
The problem of induction is the problem of justifying any belief that is not guaranteed to be true by our evidence.

Consider the following argument:

Premise: The sun rose yesterday
Conclusion: The sun will rise tomorrow

Why does the belief that the sun rose yesterday justify the belief that it will rise tomorrow? The natural answer is that the inference is justified by a belief in the laws of nature. The laws of classical mechanics say that a rotating body will continue to rotate unless acted upon by an outside force. Adding this as a premise:

Premise: The sun rose yesterday
Premise: (Classical mechanics) A rotating body will continue to rotate unless acted upon by an outside force
Conclusion: The sun will rise tomorrow

But this belief in classical mechanics faces the same challenge, it held yesterday but why should you believe it will hold tomorrow? We now want to justify the following inference:

Premise: The laws of classical mechanics held yesterday
Conclusion: The laws of classical mechanics will hold tomorrow

This argument has the same structure as the original argument that the sun will rise tomorrow, so the appeal to laws of nature hasn't helped.

In both cases we need a *Principle of Uniformity*, a principle that states the future will resemble the past.

Why should we believe the future will resemble the past? The first though is we should believe the future will resemble the past because it always has before. This generates the following hopeless argument for the Principle of Uniformity

1. In the past, the future resembled the past
2. *Principle of Uniformity*: The future will resemble the past
3. Conclusion: In the future, the future will resemble the past (The Principle of Uniformity)

Clearly this argument fails because it assumes what's supposed to be shown. It's circular! The problem of induction remains. 

*Clarifications:*
1. We're not trying to fully justify a belief or find conclusive reason to believe. The question is whether we have *any reason at all* to have beliefs about the future.
2. We're not concerned with the cause of beliefs, we're concerned with their justification. We can grant that the belief that the sun rose yesterday causes the belief that the sun will rise tomorrow.
3. The skeptic need not claim to know that we don't have knowledge concerning induction.
4. The skeptic need not believe the sun will not rise tomorrow, so they need not justify it. She is merely challenging whether we know. She isn't understood to be making a positive suggestion.

# Extending the problem
---
Our examples were about what we should believe about the future. But the problem of induction applies to any non-deductive inference. We can extend the argument from beliefs  about the future to beliefs about the past: Why do you believe that the law of gravity held in the distant past?

We can extend the arguments from beliefs about other times to beliefs about other places as well. For example, the law of gravity holds around here. Why should we believe that it holds in remote parts of the universe?

There is an underlying pattern here. Want to make an inference from what we're observing to what we are not observing. What we are observing is described in our evidence. The problem is whether the evidence justifies claims not described in our evidence. We can see the problem extends to sampling inferences.

Suppose you have a sample of objects of some type F, of which a certain proportion have some property, say, being green. It's natural to take this as evidence that the whole population of Fs has the some proportion of green objects.

1. x% of observed Fs are green
2. Conclusion: x% of unobserved Fs are green

But why should we believe the proportion of green objects in the sample is probably the same as the proportion of green objects in the rest of population? We need a Principle of Uniformity taking us from the sample to the rest of the population.

1. x% of observed Fs are green
2. *Principle of Uniformity-Sampling:* Samples resemble the rest of the population
3. Conclusion: x% of unobserved Fs are green

This principle of uniformity needs justification.

What would an answer to Hume look like? What's needed is a justification for the Principles of Uniformity. Answers can be divided into those who offer a justification based on our evidence and those which offer a justification independent of our evidence.

Justification based on our evidence will focus on likelihoods and justifications independent of our evidence will focus on priors.

# Circularity
---
Could evidence justify our belief that nature is uniform? The evidence used would be about the observed, but the conclusion that nature is uniform is partly about the unobserved. So such an argument would go from observed evidence to a conclusion about the unobserved. But to do that one needs to assume that nature is uniform. And for this reason the argument would fail. We're trying to show that what is observed can give us justification about the unobserved, so it's circular to assume that what is observed can give us evidence about the unobserved.

Some have argued that the circularity needed is acceptable. Here's the sketch of an argument associated with Max Black. Recall the argument from earlier:

*Premise-Circular Argument*
1. In the past, the future resembled the past
2. *Principle of Uniformity*: The future will resemble the past
3. Conclusion: In the future, the future will resemble the past (The Principle of Uniformity)

Call this type of argument premise-circular because the conclusion appears as a premise. Black offers an alternative argument that is not premise-circular. The key is to understand the Principle of Uniformity not as a premise but as a rule of inference.

Rules of inference are not premises of the argument, instead they license the inference from premise to conclusion. Consider the following inductive rule of inference, we'll call it R:

Infer from the "in the past, X" to "in the future, X" where X is a type of event.

This rule of inference is sufficient to justify the following argument:

1. Premise: In the past, the sun has risen
2. Conclusion: In the future, the sun will rise

The obvious question is whether we're justified in using R. Black argues that R can be justified by using R:

*Rule-Circular Argument*
1. Premise: in the past, R has been successful
2. Conclusion: in the future, R will be successful

This argument is rule-circular, it uses the rule of inference, R, whose correctness is asserted by the conclusion. R supports itself. Black claims rule-circularity is acceptable.

## Objections to rule-circular arguments
Why think rule-circularity is acceptable? Why think that any rule that can be used to support itself is acceptable? There are rules which support themselves that do not seem acceptable. For example:

Anti-R Infer from "in the past, not X" to "in the future, X"

This licenses the following inference:

1. Premise: In the past, Anti-R has not been successful
2. Conclusion: In the future, Anti-R will be successful

Anti-R supports itself in the same way that R does. This parody arises because Black's reasoning seems to allow us to infer that a rule is reliable just by using it, without antecedent justification for it.

# Sampling
---
David Stove's is a philosopher who attempted to justify induction. His argument has been somewhat neglected but it's interesting for testing one's understanding of the problem.

Recall the version of the problem of induction concerning inferences from a sample to the population.

*Principle of Uniformity-Sampling*: Samples resemble the rest of the population.

Stove offers a statistical argument that a population probably resembles a random sample taken from it. If correct, we can rationally infer from a sample to the population, which would solve the problem of induction.

Suppose there is a population of two emeralds that are either green or white, generating three hypotheses:

Green = Both emeralds are green
Mixed = One emerald sampled is green and the other is white
White = Both emeralds are white

Now we need the concept of a random sample:

Random sample = A sample such that each member of the population has an equal probability of being in it.

Now suppose the evidence is that a green emerald has been sampled at random:

E = one emerald has been sampled at random and is green

These conditional beliefs follow:

P(E|Green) = 1
P(E|Mixed) = 1/2
P(E|White) = 0

And, crucially,

P(E|Green) = 1 > P(E)

Applying the probability raising theory of justification, E justifies Green. Therefore, the evidence justifies the hypothesis that all emeralds are green. This solves the problem of induction.

## Objections to Stove
There are two ways to object to Stove's argument. Deny that our sample is random, and deny that the conclusion follows even if it is.

Stove's argument assumes that our sample is selected at random, but why should we think this? This assumption requires a principle of indifference which would itself be in need of justification.

Let's grant that our samples are randomly selected.  Now some inductive inferences are justified, but we have to take care about exactly which ones. The evidence justifies that all emeralds are green, but still does not justify the hypothesis that the next emerald is green.

If we take into account the order in which emeralds are observed, there are the following four hypotheses:

GG = Both emeralds are green
GW = The first sampled emerald is green and the other is white
WG = The first sampled emerald is white and the other is green
WW = Both emeralds are white
P(E|GG) = 1
P(E|GW) = 1
P(E|WG) = 0
P(E|WW) = 0

E justifies the next emerald is green if and only if P(E|GG or WG) > P(E). But we've been given no reason to think this holds. In fact the evidence refutes WG and it justifies GW just as strongly as it justifies GG, and GW says the next emerald is white.

Stove might reply that in the long run, and random sample of green emeralds is more likely to come from a population of green emeralds than non-green emeralds. That's true but irrelevant. It isn't relevant to appeal to the long run because at any given time we only have a finite number of observed emeralds in our sample. However many green emeralds are in our sample, we are interested in whether the unobserved emeralds are green. And the following hypotheses will be equally supported by our evidence:

- There are many green emeralds in my sample, and the rest are green.
- There are many green emeralds in my sample, and the rest are white.

So we may have reason to believe:

*Principle of Uniformity-Sampling*: Samples resemble the (whole) population.

But this falls short of what we need:

*Principle of Uniformity-Sampling*: Samples resemble the rest of the population.

Even if we assume we have random selection and fix the values of P(E|H), this isn't enough to justify reasonable beliefs about the unobserved, they also depend on the initial value of P(H).

# Semantic justification
---
An argument that P(H) should have a particular initial value would require an [[Kinds of Truths|a priori]] argument. We need a reasonably high *a priori* probability that the future will resemble the past. COuld there be an *a priori* argument that nature is uniform?

There are two main candidate sources of *a priori* justification. The first is that we have some faculty that allows us to "perceive" that some sentences are probably true. This view is associated with Kant who argued that we have intuitions that allow us a priori justification of various areas.

The second source of *a priori* justification is that some sentences can be justified in virtue of understanding the meanings of the words they contain. Call these sentences [[Kinds of Truths#Analytic and Synthetic|analytic]].

We'll see Strawson's application of this second source to the problem of induction.

## Semantic solution
Suppose my nephew invents a new word "yego" which means "yellow piece of lego". Then it is *a priori* that if something is yego then it is yellow.

Let's apply this to induction. The idea is that the Principle of Uniformity can be justified *a priori* in virtue of its meaning. "If someone believes the sun rose yesterday then they have justification to believe it will rise tomorrow", could this sentence be analytic?

Strawson argues that it is. Part of the meaning of "the sun rose yesterday" is "there is justification to believe that the sun will rise tomorrow." This seems very implausible, but Strawson gives an ingenious argument.

He first claims that it is analytic that if you've observed instances of the sun rising, then you have evidence that the sun will rise tomorrow. He then claims that it is analytic that if you have evidence that the sun will rise tomorrow, you have justification to believe the sun will rise tomorrow.

So the argument is:
1. S has observed instances of the sun rising
2. S has evidence that the sun will rise tomorrow
3. Therefore, S has justification to believe that the sun will rise tomorrow.

Each step follows analytically from the last. The schema is:
1. S has observed instances of X
2. S has evidence that X will occur in the future
3. Therefore S has justification to believe X will occur in the future.

For example, the meaning of "vixen" licenses the inference:

"Foxy is a vixen" -> "Foxy is a female fox"

Similarly the meaning of evidence licenses:

"Past instances of X" -> "Evidence for future X" -> "Justification to believe in future X"

If Strawson is right we have a priori justification for the inductive principles needed to solve the problem of induction

## First objection to the semantic solution: Implausibility
This objection is the initial implausibility of the position. "The sun rose yesterday" is only about what the sun did yesterday but according to Strawson, it's also about what the sun will do tomorrow. The meaning of "The sun rose yesterday" is that the sun will rise tomorrow. Words have meanings we didn't expect according to Strawson, one may object that our words simply do not mean what Strawson's theory says they mean.

## Second objection to the semantic solution: Ambiguity
BonJour argues that 1-3 are ambiguous. There's one sense of "evidence for future X" which means "there are past instances of X" and another which means "there is justification to believe in future X." The inference from 1 to 2 is correct given the first meaning; the inference from 2 to 3 is correct given the second meaning; but the inference from 1 to 3 is fallacious.

## Carnapian rejoinder
Neither of these objections settle the matter. Even if the objectors are right about the actual meaning of "evidence", we could easily have spoken a different language containing a word that has the meaning Strawson suggests. We can just use the word "evidence" to express Strawson's meaning. If we use the word "evidence" this way, we have *a priori* justification for induction.
## Third objection to the semantic solution: Defective concepts
Dummet points out that someone might use "boche" in such a way that "if S is German then S is boche" and "if S is boche then S is cruel" are both analytic.  This seems to allow them to iner on meeting any German that the GErman is cruel.

But this would be a mistake. Instead, we should look at the world, notice not all Germans are cruel, and reject "boche" as a defective concept. It's defective because it licenses inferences from true sentences to false ones. Strawson's concept expressed by "evidence" plays an analogous role to that expressed by "boche".

"Evidence" may be defective for the same reason as "boche". We have no *a priori* reason to think it isn't defective, so Strawson has failed to give an *a priori* argument for Principle of Uniformity.

This focuses on Strawson but similar problems arise to any semantic solution to the problem of induction. Carnap similar tried to solve the problem by inventing artificial languages. But the same problems apply. An analysis of language alone cannot tell us anything about what the world is like.

Let's now consider two influential skeptical responses.

# Skeptical responses
---
## Pragmatic vindication of induction
Hans Reichenbach suggested we should use induction because if anything works, induction works.

|                     | Nature is uniform  | Nature is not uniform |
| ------------------- | ------------------ | --------------------- |
| Use induction       | Success            | Failure               |
| Don't use induction | Success or Failure | Failure               |

If nature is not uniform then nature is random and unpredictable, so any method used for prediction will fail. We only have a chance of success if nature is uniform. If nature is uniform then we will make successful predictions by using induction. We might also make successful predictions by using other methods for predicting the future such as crystal ball gazing. But if so, some inductive inferences will be correct.

## Objections to pragmatic vindication of induction
Suppose I offer you $100 to believe the moon is made of cheese. Do you have justification to believe the moon is made of cheese? We can say you have pragmatic justification to believe the moon is made of cheese. But you don't have justification to think the belief is true. You don't have epistemic reason.

The same applies to the pragmatic vindication of induction. We're asking for epistemic justification, to provide pragmatic justification is to miss the point of the question.

## Popper's falsificationism
Popper accepts Hume's conclusion, evidence never justifies hypotheses. This isn't a problem for scientists since they don't justify theories. They try to falsify them. Theories that survive falsification are corroborated. But being corroborated doesn't mean we have justification to believe the theory is true.

## Objections to Popper

This view accepts Hume's skeptical conclusion that we have no justification to believe the sun will rise tomorrow. There's traditional objection like [[The Duhem Thesis and the Quine Thesis|duhem quine]]