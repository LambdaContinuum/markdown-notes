What rules should an agent's degrees of belief satisfy? We'll argue they should satisfy the rules of probability.

The rules an agent should (epistemically) rationally satisfy are called rationality constraints. A central question of epistemology is what these constraints are.

We'll start here with a basic a widely accepted rationality constraint: probabilism. We'll evaluate three arguments for probabilism. The Dutch Book argument, the Accuracy argument, and the representation theorem argument.

# Probabilism
---
Probabilism is the view that an agent's degrees of belief should be probabilities.

Degrees of belief are probabilities if and only if they satisfy the following rules, where X and Y represent propositions and B represents the set of beliefs of the agent:
1. Non-negativity: $P(X) \geq 0$ for all $X$ in $B$
2. Normalization: $P(T) = 1$ for any tautology $T$ in $B$
3. Finite additivity: $P(X \lor Y) = P(X) + P(Y)$ for all $X$ and $Y$ in $B$ such that $X$ is incompatible with $Y$.

Non-negativity says all beliefs have a credence greater than or equal to 0. This seems obvious.

Normalization says that beliefs in tautologies should have credence of 1. This is more controversial since it says all tautologies should have credence 1, not just all known tautologies. This comes apart if there are unknown tautologies. So normalization says that all agents should have a degree of belief of 1 in say some mathematical theorem, even those who haven't heard the proof. This seems wrong, so some philosophers object to normalization, and therefore probabilism. This is called the logical omniscience objection to probabilism, since its based on the fact that probabilism entails that rational agents should be certain of all mathematical and logical truths.

One response is that probabilism is a constraint on fully rational agents so it doesn't matter that we flawed humans aren't certain that certain mathematical theories are true. All probabilism requires is that fully rational agents are. But that seems to require too much rationality. Is someone who doesn't know all mathematical truths thereby irrational? Maybe the best response is just that we should assume normalization because of its simplifying power. This assumption allows us to use probability theory to model agents. If we didn't assume normalization, we would have to use some more complicated theory that might be more accurate but difficult to use.

Finite additivity connects degrees of belief to each other and therefore imposes a structure on the beliefs.

# Dutch Book Argument
---
This argument says that anyone who violates probabilism is susceptible to a guaranteed monetary loss.

A Dutch Book is a series of bets that result in the bettor losing money, however the world turns out. The bettor is guaranteed to lose money. Such a fate awaits those whose credences violate the rules of probability.

## Dutch Book Theorem
We first need the concept of a betting price. The betting price is the largest amount the agent is willing to pay for a ticket that pays $1 if H is true (and $0 if H is false), It's also the smallest amount for which the agent is willing to sell a ticket which pays out $1 if H (and $0 if false). Suppose you have signed a ticket that promises to pay the bearer $1 if H. IF your credence in H is 0.8, then you will need at least 80c to sell it.

The Dutch Book Theorem is that if a set of betting prices violates the rules of probability, then there is a dutch book consisting of bets at those prices.

If your betting prices violate the rules of probability, you are susceptible to a guaranteed loss. Now let's see how violating each of these rules leaves one Dutch-bookable.

Non-negativity: Suppose an agent's betting prices violate Non-negativity, meaning they have negative betting price in some hypothesis H. A negative price means you are willing to pay someone to take it away. Such an agent is willing to stop a stranger in the street and pay them to take a ticket that turns into a further $1 if H. Such an agent is guaranteed to lose money.

Normalization:  Suppose your betting price in a tautology T is greater than 1. Then you are willing to pay more than $1 for a bet that pays $1. You pay more than $1 to win only $1, so you're guaranteed to lose. Suppose your betting price on a tautology is less than 1. Then you are willing to bet on not T, but T is certain to happen so you are guaranteed a loss.

Finite additivity: Suppose that your betting prices on X and Y are 0.4 each but your betting prince on \[X or Y\] is 0.6, that is, less than 0.4 + 0.4. You are assigning each individual possibility too high a betting price, so you're prepared to bet too heavily in favor of each of them happening individually. Let's construct the dutch book which consists of three bets.

Bet 1 is for a ticket that pays $1 if and only if X; Bet 2 is for a ticket that pays $1 if and only if Y. Since you assign each a probability of 0.4, you're willing to pay $0.4 for each, and so $0.8 for both. For bet 3, you sell the bookie a ticket that pays $1 if and only if either X or Y is true. You sell this ticket for your betting price of $0.6. This means you get $0.6 and give the bookie a ticket that promises the bearer $1 if X or Y. After these bets are made, you are out of pocket $0.8 - $0.6 = $0.2, and there is no way you can make the money back. There are three possibilities for what happens next:

If X is true you win $1 on bet 1 but lose $1 on bet 3.
If Y is true you win $1 on bet 2 but lose $1 on bet 3.
If niether are true, no further money changes hands.

Whatever happens you lose $0.2.

This is just an example, but it generalizes. Whenever finite additivity is violated, a Dutch Book can be made. Say for example, the betting prices of X and Y individually are too low instead of too high, then the bookie reverses the direction of the bets, so bets that he bought are now sold and those he sold are now bought.

We conclude that the Dutch Book Theorem is true: If a set of betting prices violates the rules of probability, then there is a Dutch Book consisting of bets at those prices.

## Dutch Book Argument
The argument proceeds as follows:
1. Your degrees of belief should be matched by your betting prices.
2. If your betting prices violate the rules of probability, then there is a Dutch Book consisting of bets at your betting prices. (Dutch Book Theorem)
3. If there is a Dutch Book consisting of bets at your betting prices then you are susceptible to a guaranteed loss.
4. If you are susceptible to a guaranteed loss, then you are irrational.
5. Therefore, if your degrees of belief violate the rules of probability then you are irrational.


## Objections to Dutch Book Argument
### Objections to P1
P1 says your degrees of belief should be matched by your betting prices. But there are cases where you degrees of belief should not be matched by your betting prices. Suppose a bus ticket home costs $1 but you only have 60c. Someone offers you a bet that pays $1 if and only if a fair coin lands Head, and charges you 60c. If you really want to ride home, you may rationally choose to take the bet. Your degree of belief that the coin lands Heads is 0.5, but your betting price is 0.6. These come apart because you will be so much happier with $1 than you will be with 99c.

The technical term for such happiness is utility. Think of utility as expressing a psychological property of the agent. The problem for P1 Is that utility is not proportional to money. You have much more utility with $1 than 99c, but there is only a tiny difference in money. The fact that utility is not proportional to wealth explains many futures of human behavior.

### Responses to Objections to P1
One response is to reformulate the argument in terms of utility rather than money. But this response faces criticism on the grounds that utility is a mysterious concept.

A simpler response is to stipulate that the argument only applies to agents whose utility is proportional to their money. Call them simple agents. For simple agents, monetary payoffs function as utilities. This ensures the truth of P1.

### Objections to P3
There are ways to block this inference. For example, you are not susceptible to a guaranteed loss if you don't bet. Perhaps you foresee that you are susceptible to  Dutch Book and so refuses to make any bets at all.

### Objections to P4
Maybe you can be susceptible to a sure loss and be rational. One could argue that all agents are susceptible to a sure loss or one could argue that there is an upside to being susceptible to a sure loss.

The former is incorrect, there are probabilistic agents that are never susceptible to a sure Loss. This result was proved in 1955 and known as the Converse Dutch Book Theorem. If your betting prices satisfy the probability calculus, then there does not exist a Dutch Book consisting of bets at your prices.

The latter is more interesting, perhaps having degrees of belief that violate the rules of probability open up possibilities for gains that would otherwise be closed off. Maybe  non-probabilistic agents can benefit from sets of bets that guarantee a gain, whereas the probabilistic agent will miss the opportunity. But in fact the probabilistic agent will not miss the opportunity.

All objections given have the same underlying problem. The Dutch Book argument tells us about agents that lose money, but what we're really interested in is beliefs, and losing money is only indirected related to beliefs. Call more direct arguments de-pragmatized Dutch Book arguments.

## De-pragmatized Dutch Book Argument
