For the calculus required see: [[Vector Calculus]]
## Probability Space
---
> [!definition] Probability Space
> A **Probability Space** is a mathematical construct in probability theory that provides a formal model for randomness and uncertainty. It is defined as a triple $\langle \Omega, \mathcal{F}, P\rangle$.

1. **Sample Space** ($\Omega$):
	- This is the set of all possible outcomes of a random experiment.
	- Example: For a coin toss, $\Omega = \{\text{heads}, \text{tails}\}$.
2. **Sigma-algebra** ($\mathcal{F}$):
	- Also known as a **sigma-field**, this is a collection of subsets of $\Omega$ that satisfies certain properties.
	- It includes the empty set and $\Omega$ itself, and is closed under the operations of complementation and countable unions..
	- Example: For a coin toss, $\mathcal{F} = \{\emptyset, \{\text{heads}\}, \{\text{tails}\}, \{\text{heads, tails}\}\}$.
3. **Probability Measure** ($P$):
	- A function that assigns a probability to each set in $\mathcal{F}$.
	- This function must satisfy three axioms:
		- **Non-negativity**: For every $A \in \mathcal{F}, P(A) \geq 0$.
		- **Normalization**: $P(\Omega) = 1$.
		- **Countable Additivity**: For any countable sequence of mutually exclusive sets $A_1, A_2, ... \in \mathcal{F}, P(\bigcup_{i=1}^{\infty}A_i) = \sum_{i=1}^{\infty} P(A_i)$.

The probability space provides a framework for calculating probabilities of events and understanding the behavior of random processes.

**Exercise.** Let $S$ be a sample space with probability measure $P$. Let $A$ and $B$ be any events in $S$. Then the following hold.

1. $P(A^c) = 1 - P(A)$
2. $P(\emptyset) = 0$

**Proof.**

1. For the first property, note that by definition of the complement of an event $A$ we have $$A \cup A^c = S \text{ and } A \cap A^c = \emptyset$$ In other words, given any event $A$, we can represent the sample space $S$ as a disjoint union of $A$ with its complement. Thus, by the first and third axioms, we derive the first property: $$1 = P(S) = P(A \cup A^c) = P(A) + P(A^c)$$ which implies $$P(A^c) = 1 - P(A)$$
2. For the second property, note that we can write $S = S \cup \emptyset$, and that this is a disjoint union, since anything intersected with the empty set will necessarily be empty.  So, using the first and third axioms, we derive the second property: $$1 = P(S) = P(S \cup \emptyset) = P(S) + P(\emptyset)$$ which implies $$P(\emptyset) = 0$$ Let's toss a fair coin $n_{tosses} = 1000$ times and estimate the probability of observing heads using the fraction $$\frac{\#\text{heads}}{\#\text{tosses}}$$
```julia
coin_sides = ["Tails", "Heads"]
n_tosses = 1000 

random_tosses = rand(coin_sides, n_tosses) 

probability_heads = count(==("Heads"), random_tosses) / n_tosses
probability_tails = count(==("Tails"), random_tosses) / n_tosses 

println("Probability of Heads: ", probability_heads) println("Probability of Tails: ", probability_tails)
```

```
Probability of Heads: 0.505
Probability of Tails: 0.495
```

## Random Variables
---
### What is a Random Variable
A **Random Variable** is a variable that taken on different values determined by the outcome of a random process. Formally, it's a function that maps outcomes from the sample space of a probability experiment to real numbers.

> [!definition] Random Variable
> Given a probability space $\langle \Omega, \mathcal{F}, P\rangle$, a random variable $X$ is a function $X: \Omega \to \mathbb{R}$, such that for every real number $x$, the set $\{\omega \in \Omega : X(\omega) \leq x\}$ belongs to $\mathcal{F}$ 

Random variables are used to quantify the outcome of random processes and to conduct probability and statistical analysis. For example, if we toss the coin twice, there exists four possible events that define our sample space $\{\omega_1 = (H, H), \omega_2 = (T, T), \omega_3 = (H, T), \omega_4 = (T, H)\}$. An example of a random variable is the number of heads in this experiment. For example $X(\omega_1) = 2$  and $X(\omega_4) = 1$.

### What is a Discrete Random Variable
A **Discrete Random Variable** is a type of random variable that can take on a countable number of distinct values. The values can be finite or countably infinite.
- **Characteristics:**
	- The probability distribution can be described using a probability mass function (PMF)
	- Examples include the numbers of heads in a coin tosses, the number of red cards drawn from a deck, etc.
- **Probability Mass Function (PMF)**: For a discrete random variable $X$, the PMF is given by $p_X(x) = P(X = x)$, which provides the probability that $X$ takes the value $x$.

In the example where we flip a fair coin twice, the PMF is as follows: $$p_X(0) = \frac{1}{4}, p_X(1) = \frac{1}{2}, p_X(2) = \frac{1}{4}$$
Let's explore some significant discrete probability distributions.

#### Bernoulli Distribution
A random variable $X$ follows the Bernoulli distribution $Ber(X;p)$ or $Ber(X\mid p)$ if $$Pr(X = x) = \begin{cases} 1 - p & \text{if } x = 0\\ p & \text{if } x = 1\\\end{cases}$$
```julia
Base.@kwdef struct Bernoulli 
    p::Float64 = 0.5
end    


function simulate(trial::Bernoulli)
    return rand() < trial.p ? 1 : 0
end


ber = Bernoulli()

for i in 1:10
    res = simulate(ber)
    println("Result of $(i)-th simulation of Bernoulli with p = $(ber.p) is $(res)")
end
```

#### Binomial Distribution
The binomial distribution has two parameters $N$ and $p$. $N$ is a positive integer and $p$ is a probability. It is the distribution of the number of successes in a sequence of $N$ independent experiment, each having a probability $p$ of success.

A binomial random variable can be written as the sum of $N$ independent identically distributed Bernoulli $Ber(p)$ random variables. When $N = 1$ the binomial random variable is the same as a Bernoulli random variable. The binomial distribution for a random variable $X \sim Bin(N, p)$ is defined by: $$Bin(k\mid N, p) \equiv Pr(X = k) = {N \choose k} p^k(1-p)^{N-k}$$
where ${N \choose k} \equiv \frac{N!}{(N-k)!k!}$  is the number of ways to choose $k$ items from $N$.

```julia
Base.@kwdef struct BinomialRV 
	n::Int = 1000 
	p::Float64 = 0.5 
end 

function simulate(binom_rv::BinomialRV) 
	successes = sum(rand() < binom_rv.p for _ in 1:binom_rv.n) 
	return successes 
end 

function generate_samples(binom_rv::BinomialRV, num_samples::Int) 
	return [simulate(binom_rv) for _ in 1:num_samples]
end 

# Example usage: generate 1000 samples from a Binomial distribution with n=100 and p=0.5 
binom_rv = BinomialRV(n=100, p=0.5) 
samples = generate_samples(binom_rv, 1000) 

histogram(samples, bins=0:binom_rv.n, legend=false,
		xlabel="Number of Successes", ylabel="Frequency", 
		title="Histogram of Binomial Distribution")
```

#### Discrete uniform
The discrete uniform distribution is a symmetric probability distribution wherein a finite number of values are equally likely to be observed. For example, the outcome of a fair die follows the discrete uniform distribution with the set of possible values being $\{1, ..., 6\}$.

```julia
Base.@kwdef struct DiscreteUniformRV #special case of a discrete uar, could be a set rather than a range 
	a::Int=0 # Lower bound 
	b::Int=1 # Upper bound, for these default values this is a Bernoulli(0.5) 
end

function simulate(du_rv::DiscreteUniformRV) 
	return rand(du_rv.a:du_rv.b) 
end

# Generate discrete uniform samples 
function generate_samples(du_rv::DiscreteUniformRV, num_samples::Int) 
	return [simulate(du_rv) for _ in 1:num_samples] 
end

# Example usage: generate 1000 samples from a Discrete Uniform distribution with bounds a=1, b=6
du_rv = DiscreteUniformRV(a=1, b=6)
samples = generate_samples(du_rv, 1000)

# Calculate frequencies for each outcome
frequencies = countmap(samples)

# Plot the bar chart
bar(collect(du_rv.a:du_rv.b), [get(frequencies, x, 0) for x in du_rv.a:du_rv.b], legend=false, xlabel="Value", ylabel="Frequency", title="Bar Chart of Discrete Uniform Distribution")
```

#### Multinomial distribution
Suppose an experiment is conducted where $n$ balls are drawn from a bag containing balls of $k$ different colors, with each draw being replaced. Balls of the same color are considered indistinguishable. Let $X_i$ represent the random variable corresponding to the count of balls of color $i$ (where $i = 1, ..., k$) that have been drawn, and let $p_i$ denote the probability of drawing a ball of color $i$ in a single trial. The probability mass function (PMF) for the multinomial distribution is given by: $$f(x_1, ..., x_k;n, p_1, ..., p_k) = Pr(X_1 = x_1 \text{ and ... and } X_k = x_k) = \begin{cases}\frac{n!}{x_1!...x_k!}p_1^{x_1}...p_k^{x_k}, & \text{when} \sum_{i=1}^{k} x_i = n,\\0 & \text{otherwise,}\\\end{cases}$$
where the $x_i$ are non-negative integers that represent the count of occurrences for each color and must sum to $n$.

The PMF can also be expressed using the gamma function for a more generalized formulation: $$f(x_1, ..., x_k;p_1, ..., p_k) = \frac{\Gamma(\sum_{i=1}^k x_i + 1)}{\prod_{i=1}^k \Gamma(x_i + 1)}\prod_{i=1}^k p_i^{x_i}.$$
Here, $\Gamma$ represents the gamma function, which generalizes the factorial function with $\Gamma(n) = (n-1)!$ for an integer $n$.

```julia
struct MultinomialRV 
	outcomes_probs::Dict{Any, Float64} 
	n::Int 
end

function simulate(multinomial_rv::MultinomialRV) 
	outcomes = collect(keys(multinomial_rv.outcomes_probs))
	probabilities = collect(values(multinomial_rv.outcomes_probs))
	multinomial_dist = Multinomial(multinomial_rv.n, probabilities) 
	sample = rand(multinomial_dist) 
	return Dict(zip(outcomes, sample)) 
end

function generate_samples(multinomial_rv::MultinomialRV, num_samples::Int)
	return [simulate(multinomial_rv) for _ in 1:num_samples]
end

outcomes_probs = Dict("A" => 0.2, "B" => 0.3, "C" => 0.5) multinomial_rv = MultinomialRV(outcomes_probs, 100) # 10 trials 
samples = generate_samples(multinomial_rv, 1000)
```

#### Poisson distribution
A discrete random variable $X$ is said to have a Poisson distribution, with parameter $\lambda > 0$, if it has a probability mass function given by: $$f(k; \lambda) \equiv Pr(X = k) = \frac{\lambda^k e^{-\lambda}}{k!},$$
where
- $k$ is the number of occurrences ($k = 0, 1, 2, ...$)
- $e$ is Euler's number ($e \approx 2.71828...$)
- $k!$ is the factorial of $k$.

We will use the package *Distributions* to simulate the Poisson.

```julia
using Distributions

Base.@kwdef struct PoissonRV
	λ::Float64 # Rate parameter (lambda)
end

# Simulate function for a Poisson random variable
function simulate(poisson_rv::PoissonRV)
	poisson_dist = Poisson(poisson_rv.λ)
	return rand(poisson_dist)
end

# Generate Poisson samples
function generate_samples(poisson_rv::PoissonRV, num_samples::Int)
	return [simulate(poisson_rv) for _ in 1:num_samples]
end

# Example usage: generate 1000 samples from a Poisson distribution with λ=4.0
poisson_rv = PoissonRV(λ=4.0)
samples = generate_samples(poisson_rv, 1000)

# Plot the histogram
histogram(samples, bins=0:maximum(samples)+1, legend=false, xlabel="Number of Events", ylabel="Frequency", title="Histogram of Poisson Distribution")
```

Poisson distribution models several real-world processes.
- Number of Calls: The number of calls received by a call center in an hour.
- Public Transport: The number of buses arriving at a bus stop in a given period of time.
- Website Traffic: The number of visits to a website in a day.
- Mail Reception: The number of mail or packages a post office receives per day.
- Biology: The number of times a bacterium divides over a fixed time interval.
- Defects in Manufacturing: The number of defects found in a batch of products.
- Natural Events: The number of natural occurrences, such as earthquakes in a region over a year.

The distribution is named after the French mathematician and physicist [Simon Denis Poisson](https://en.wikipedia.org/wiki/Sim%C3%A9on_Denis_Poisson)
#### Geometric random variable
The geometric distribution gives the probability that the first occurrence of success requires  $k$ independent trials, each with success probability $p$. If the probability of success on each trial is $p$, then the probability that the $k$-th trial is the first success is $$Pr(X = k) = (1 - p)^{k-1}p, k = 1, 2, 3, 4, ...$$
```julia
@kwdef struct GeometricRV 
	p::Float64=0.5 
end 

function simulate(geom_rv::GeometricRV) 
	return rand(Geometric(geom_rv.p)) 
end 

function generate_samples(geom_rv::GeometricRV, num_samples::Int) 
	return [simulate(geom_rv) for _ in 1:num_samples] 
end 

# Example usage: generate 1000 samples from a Geometric distribution with p=0.05 
geom_rv = GeometricRV(p=0.05) 
samples = generate_samples(geom_rv, 1000) 
# Plot the histogram 
histogram(samples, bins=0:maximum(samples), legend=false, xlabel="Number of Trials", ylabel="Frequency", title="Histogram of Geometric Distribution") 

# Plot a vertical line at the expected value 1/p 
vline!([1/geom_rv.p], label="Expected value", color=:red)
```

The geometric distribution is a special case of a negative binomial random variable that we discuss next.

#### Negative binomial random variable
Suppose we have an "urn" with $N$ balls, $R$ of which are red and $B$ of which are blue. We consider drawing a red ball a "failure", and drawing a blue ball a "success".

Suppose we keep drawing balls until we observe $r$ failures. Let $X$ be the resulting number of successes (blue balls); it can be shown that $X \sim NegBinom(r, p)$ which is the negative binomial distribution defined by $$NegBinom(x\mid r, p) \equiv {x + r - 1 \choose x} (1 -p)^rp^x$$
for $x \in \{0, 1, 2, ...\}$. (If $r$ is real-valued, we replace ${x+r-1 \choose x}$ with $\frac{\Gamma (x + r)}{x!\Gamma(r)}$, exploiting the fact that $(x-1)! = \Gamma(x)$.)

```julia
@kwdef struct NegativeBinomialRV
	r::Int=1 # Number of failures until stopping, by default we set it a Geom(p) 
	p::Float64=0.1 # Probability of success 
end

# Simulate function for a Negative Binomial random variable
function simulate(negbin_rv::NegativeBinomialRV)
	return rand(NegativeBinomial(negbin_rv.r,negbin_rv.p))
end

# Generate negative binomial samples
function generate_samples(negbin_rv::NegativeBinomialRV, num_samples::Int)
	return [simulate(negbin_rv) for _ in 1:num_samples]
end

# Example usage: generate 1000 samples from a Negative Binomial distribution with r=3, p=0.5
negbin_rv = NegativeBinomialRV(r=3, p=0.1)
samples = generate_samples(negbin_rv, 10000)

# Calculate the empirical mean of the samples
empirical_mean = mean(samples)

# Plot the histogram
histogram(samples, bins=0:maximum(samples)+1, legend=false, xlabel="Number of Successes", ylabel="Frequency", title="Histogram of Negative Binomial Distribution")

# Plot a vertical line at the expected value r/p
vline!([negbin_rv.r/negbin_rv.p], label="Mean value", color=:red)
vline!([mean(samples)], label="Expected value", color=:black)
```

### What is a Continuous Random Variable
A **Continuous Random Variable** is a random variable that can take on an infinite number of possible values, typically any value within an interval on the real number line.
- **Characteristics:**
	- The probability distribution is described using a probability density function (PDF).
	- Examples include the exact height of students in a class, the time it takes for a chemical reaction to complete, etc.
- **Probability Density Function (PDF):** For a continuous random variable $X$, the PDF, denoted as $f(x)$, is such that the probability that $X$ is in the interval $(a, b)$ is given by the integral $\int_a^b f(x)dx$

In both discrete and continuous random variables, the main goal is to study the behavior of these variables and use them to make predictions or inferences about the underlying random processes.

#### Gaussian distribution
A univariate distribution we will come across a lot is the Gaussian distribution. The pdf (probability density function) of the Gaussian is given by $$\mathcal{N}(x; \mu, \sigma^2) \equiv \mathcal{N}(x\mid\mu, \sigma^2) \equiv f_X(x) = \frac{1}{\sqrt{2\pi\sigma^2}}e^{-\frac{1}{2\sigma^2}(x-\mu)^2}$$
The cumulative distribution function or cdf of the Gaussian is defined as $$\Phi(x;\mu, \sigma^2) \equiv \int_{-\infty}^x \mathcal{N}(z\mid\mu,\sigma^2)dz$$
If $\mu = 0$ and $\sigma = 1$ (known as the standard normal distribution), we just write $\Phi(x)$.

#### Laplace distribution
Another important distribution with heavy tails is the Laplace distribution. It also has two parameters, the Gaussian $\mu$ is a location parameter and $b > 0$ is a scale parameter. The pdf is the following: $$Laplace(x\mid \mu, b) \equiv \frac{1}{2b}\text{exp}\left( -\frac{|x - \mu|}{b} \right)$$
```julia
@kwdef struct LaplaceRV
	μ::Float64=0 # Mean
	b::Float64=1 # scale parameter
end

function simulate(laplace_rv::LaplaceRV)
	return rand(Laplace(laplace_rv.μ, laplace_rv.b))
end

function generate_samples(laplace_rv::LaplaceRV, num_samples::Int)
	return [simulate(laplace_rv) for _ in 1:num_samples]
end

laplace_rv = LaplaceRV(μ=0, b=1) 
samples = generate_samples(laplace_rv, 10000)

histogram(samples, bins=50, legend=false, xlabel="Value", ylabel="Frequency", title="Histogram of Laplace Distribution")

vline!([laplace_rv.μ], label="Mean", color=:red)
```

#### Beta distribution
The beta distribution is an important distribution that yields the uniform distribution as a special case. It has support over the interval $[0, 1]$ and is defined by the following pdf: $$Beta(x \mid a, b)= \frac{1}{B(a, b)}x^{a-1}(1-x)^{b-1}$$
where $B(a, b)$ is the beta function. The parameters $a, b > 0$ are positive to ensure that $B(a, b)$ exists. When $a=b=1$ we get the uniform distribution

```julia
using Distributions 
using Plots 

# Number of samples to draw 
num_samples = 10000 

# Define parameters for the beta distributions 
params = [(1, 1), (2, 5), (5,2), (2, 20)] 

# Create beta distribution objects with the specified parameters 
distributions = [Beta(a, b) for (a, b) in params] 

# Generate samples and plot histograms for each set of parameters
histograms = [] 
for dist in distributions 
	samples = rand(dist, num_samples) 
	push!(histograms, histogram(samples, bins=50, alpha=0.6, label="a=(dist.β)")) 
end 

# Combine the histograms into a single plot 
plot(histograms..., layout=(2,2), legend=:topright, xlabel="Value", ylabel="Frequency")
```

## Algorithm for Estimating π using 2d uniform random variables
---
To estimate the value of $\pi$, we can employ a simple yet effective algorithm involving random point generation within a unit square. Here's how the process works:
1. Begin by generating a series of $n$ random points with coordinates $(x, y)$ such that each point lies within the confines of a unity square, specifically in the interval $[0, 1]$ for both $x$ and $y$.
2. For each generated plot, determine whether it resides within the quarter circle inscribed within the unit square. The quarter circle is defined by the area where $$x^2 + y^2 \leq 1$$
3. Count the number of points that fall inside the quarter circle. Denote this count as $S_n$.
4. The estimate for $\pi$ is then calculated using the ratio of the number of points inside the quarter circle to the total number of points, multiplied by $4$. Mathematically, this estimate is represented as: $$\hat{\pi} = 4 \times \frac{S_n}{n}$$
This algorithm is grounded in the principles of geometric probability and leverages the area of a circle in relation to the square that encloses it. Since the area of the circle is $\pi$ times the radius squared, and the radius of the inscribed quarter circle is $1$, the ratio of the areas is $\pi/4$. Therefore, as the number of random points increase, the proportion within the quarter circle should converge to $\pi/4$ making the algorithm a practical approach to approximating $\pi$.

## Expectation, Variance, and Moments of random variables
---
For a **discrete random variable** $X$ with possible values $x_i$ and corresponding probabilities $P(X = x_i)$, the expectation or expected value is calculated as: $$E[X] = \sum_i x_i P(X=x_i)$$
For a **continuous random variable** $X$ with probability density function $f(x)$, the expectation is given by the integral: $$E[X] = \int_{-\infty}^{\infty}xf(x)dx$$
The variance of a **discrete random variable** $X$, denoted by $Var(X)$ or $\sigma^2$, is the expected value of the squared deviation from the mean $\mu = E[X]$ : $$Var(X) = E[(X - \mu^2)] = \sum_i (x_i - \mu)^2 P(X = x_i)$$
The variance of a **continuous random variable** $X$ with probability density function $f(x)$ is similarly defined as: $$Var(X) = \int_{-\infty}^{\infty}(x - \mu)^2f(x)dx$$
Variance measures the spread of the random variable's possible values from the mean, indicating the degree of dispersion or concentration around the expected value.

Moments are a set of measures that provide significant insights into the shape and characteristics of a probability distribution. Specifically, the moments of a random variable offer a systematic way to describe various aspects of its distribution.

The **k-th moment** of a random variable $X$, denoted as $M_k(X)$ is defined as mathematically as the expected value of $X$ raised to the power of $k$: $$M_k(X) = E[X^k]$$
- When $k = 0$, $M_0 (X)$ is always 1.
- When $k = 1$, $M_1(X)$ corresponds to the expected value of $X$, denoted $E[X]$ which is the mean of the distribution.
- When $k = 2, M_2(X)$ does not directly give the variance; Instead it represents the mean of the square of $X$. The variance can be derived by subtracting the square of the first moment from the second moment: $$Var(X) = M_2(X) = (M_1(X))^2$$
Moving beyond raw moments, we encounter the **central moments** which shifts the focus to the deviations from the mean. The **k-th central moment** of a random variable $X$, represented by $\mu_k$, is the expected value of the $k$-th power of the deviation of $X$ from its mean: $$\mu_k(X) = E[(X - E[X])^k]$$
Central moments are particularly valuable as they describe the variability and shape of the distribution without being influenced by the location of the distribution. For example, the second central moment, $\mu_2(X)$ is the variance of $X$ reflecting the dispersion of the distribution around the mean.

The use of moments and central moments in statistical analysis provides a comprehensive toolkit for describing and understanding the fundamental properties of distributions.

More Probability [[More probaiblity|here]]