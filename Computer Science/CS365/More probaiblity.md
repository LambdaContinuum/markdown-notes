## Markov's inequality
---
Let $X$ be a non-negative random variable and suppose that $\mathbb{E}[X]$ exists. $$\text{For any }t>0\text{, } \Pr(X \geq t) \leq \frac{\mathbb{E}[X]}{t}$$
Best possible inequality if we only know the expectation.

**Proof:** $$\mathbb{E}[X] = \int_0^\infty xf(x)dx = \int_0^t xf(x)dx + \int_t^\infty xf(x)dx \geq \int_t^\infty xf(x)dx \geq t\int_t^\infty f(x)dx = t\Pr(X > t)$$
### Examples
- Let $X$ be a non-negative RV. Then, $\Pr(X \geq k\mathbb{E}[X]) \leq \frac{1}{k}$ 
	- For example $X \sim Bin(1000, 0.1)$. Then $\mathbb{E}[X] = 100$. The tail probability $\Pr(X \geq 400) \leq \frac{1}{4}$.
	- The bound is not tight, we can get much tighter bounds (to be seen)
		- Exponential method
		- Nifty manipulation of the binomial coefficients, i.e., $$\sum_{k = 400}^{1000} {n \choose k}p^k(1-p)^{1000 -k} = \sum_{k = 400}^{1000} {n \choose k}^k(\frac{1}{10})^{10}(\frac{9}{10})^{1000-k} \leq ...$$

## Chebyshev's inequality
---
Let $\mu = \mathbb{E}[X], \sigma^2 = \mathbb{Var}[X]$. Then, $$\Pr(|X - \mu| \geq t) \leq \frac{\sigma^2}{t^2}$$
### Examples
Let's consider the same example as before, namely bound the tail $\Pr(X \geq 400)$ where $X \sim Bin(1000, 0.1).$ Let's apply Chebyshev

## Weak law of large numbers
---
Let $X_1, X_2, ...$ be a sequence of iid RVs with mean $\mu$ and standard deviation $\sigma$. Consider the sum $$S_n =X_1+ ... + X_n$$
Then as $n \to \infty$, for all $\epsilon > 0$ the empirical average converges to $\mu$ in probability, i.e., $$\lim_{n \to \infty} \Pr(|\frac{S_n}{n} - \mu | > \epsilon) = 0$$

Proof of WLLN using Chebyshev's inequality: $$\Pr(|\frac{S_n}{n} - \mu| > \epsilon) \leq \frac{\mathbb{Var}(S_n/n)}{\epsilon^2} = \frac{\sigma^2}{n\epsilon^2} \to 0 \text{ as }n\to \infty$$
### Examples
Consider rolling a regular dice $n$ times. Then by WLLN we obtain that the sum of the first $n$ rolls as $n$ grows, for any $\epsilon > 0$ satisfies $$\Pr(|\frac{S_n}{n} - \frac{7}{2}| > \epsilon) \to 0$$

