## 1. Introduction
---
Fine-tuning is considered one of the strongest arguments for the existence of God. The core of the fine-tuning argument is as follows:
> (1) Given the fine-tuning evidence, a life-permitting universe (LPU) is very, very epistemically unlikely under Naturalism and a single universe (NSU): that is, P(LPU|NSU & k′) << 1, where k′ represents some appropriately chosen background information, and << represents much, much less than (thus making P(LPU|NSU & k′) close to zero).  
> 
> (2) Given the fine-tuning evidence, LPU is not unlikely under Theism (T): that is, ~P(LPU|T & k′) << 1.  
> 
> (3) T was advocated prior to the fine-tuning evidence (and has independent  motivation).  
> 
> (4) Therefore, by the restricted version of the Likelihood Principle, LPU strongly supports T over NSU

## 2. Arguing for (1)
---
The gist of this evidence is that in order for life to be possible in our universe, given our best understanding of physics, the fundamental constants of our universe must lie withing extremely narrow intervals, relative to the range of values that *[[Kinds of Truths|a priori]]* they might have taken.

### 2.1 The Principle of Indifference
How do you get from "narrow intervals" to "low probability"? You must assume some *[[Probability Overview|probability distribution]]* on the possible values the fundamental constants could have taken.

The theist argues that we have no reason to think any values of the fundamental constants are *a priori* more likely than any other, and so we should assume a *uniform distribution* on the possible values of the constants. The assumption of a uniform distribution is faulty.

The virtues of the Principle of Indifference:
- Given no information, a uniform distribution is most natural to assume because it does not arbitrarily favor any particular outcome over any other for no good reason.
- A uniform distribution is what you get when you average over all distributions that might govern the outcome.

We will suppose our fine-tuned constant $\mathcal{C}$ is randomly sampled from an unknown distribution $\mathcal{D}$. Then, **if we have no information regarding** $\mathcal{D}$, we should assume it is uniform.

## 3. The things we know about $\mathcal{D}$.
---
A state of total ignorance about $\mathcal{D}$ isn't the situation we find ourselves in.

### 3.1 Normality
If we are supposing Naturalism, we must suppose that the universe and its constants came about by some natural process. 

The thing about natural processes: They don't tend to give rise to uniform Distributions. Consider for example the distribution of human height or IQ which aren't uniform distributions. They resemble *normal distributions*. Normal distributions are extremely prevalent among naturally occuring quantities.

Given this, it is reasonable *a priori* to suppose that $\mathcal{D} \sim \mathcal{N}(\mu, \sigma^2)$, a normal distribution with an unknown mean $\mu$ and a standard deviation $\sigma$.

### 3.2 An estimate for the mean
At first, this assumption of normality seems to achieve very little. We have no clue what $\mu$ might be, so by the principle of indifference, we must suppose $\mu$ is uniformly distributed. But then our best guess for $\mathcal{D}$ is an average of normal distributions over all possible means, which is a uniform distribution.

Still, we are not in a situation where the principle of indifference applies. We do not have no information at all about the distribution governing our universe: we have **a data point**. The actual value for $\mathcal{C}$ in this universe is a value sampled from $\mathcal{D}$, and therefore is on average close to the mean of $\mathcal{D}$.

More formally, given the data that $\mathcal{C}$ takes a given value, it's standard to infer that $\mu$ takes whatever value that would make it most likely we would observe the data (this is called the *maximum a posteriori estimator* or MAP). But that data is most likely when it is exactly average, so we should infer that $\mu$ equals the value for $\mathcal{C}$ that we observe.

(Bayesians may object to using MAP here, in which case we can easily show that if $\mu$ is a uniform prior distribution, and we observe that $\mathcal{C} = c$, then we have posterior distribution for the mean $\mu \sim \mathcal{N}(c, \sigma^2)$.)

## 4. Conclusion
---
The argument above aims to show the following:

**Given Naturalism, we should infer that the possible values for the constants of the universe are normally distributed with mean *the values we observe them as taking.***

Given this, it's no longer clear that on [[Defining Physicalism|Naturalism]] it is unlikely that a given constant will fall in the life-permitting range. Whether this is true or not will depend on the width of the life-permitting region relative to the unknown standard deviation $\sigma$.

If $\sigma$ is low then it is quite likely a universe will permit life, whilst as $\sigma \to \infty$ we return to the case of a uniform distribution. But this then presents a roadblock for the proponent of the fine-tuning argument: by what principle do they propose to argue that $\sigma$ is large rather than small?