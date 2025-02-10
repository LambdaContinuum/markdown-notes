## The Streaming model
**Input**
- Stream of elements
- Order may be adversarial
- One pass over the stream

**Goals**
- Compute as accurately as possible statistics of interest
- Key constraint: space
- Ideally, fast query and update times

## Distinct elements
- A steam is received, one element from the universe at a time.
- **Number of distinct elements** is the number of items in the universe that appear at least once in the stream.
- We wish to maintain a small sketch S, whose size is independent of m, so we can return an approximate value F0 to the true value F0 of distinct elements.
- There exists two broad families of algorithms for estimating F0 in terms of the different types of guarantees they provide.

**Key constraints:**
1. Limited space
2. One pass over stream
3. Few operations per value
4. accurate as possible
5. fast query time

## Moment estimation problem
- Distinct elements is a special case of computing p-th frequency moments: $$F_p = \sum_{i = 1}^n f^p_I$$
- **p = 0**: distinct elements
- **p = 1**: length of stream
- **p = 2**: size of self-join in DB
- **p = +inf**: here we define $F_\infty^* = \max_i(f_i)$

In practice we'll be interested in finding heavy hitters, elements that appear frequently in streams

## Reservoir sampling
How do we get a random sample from a stream of size n if size n is unknown? 
- Algoirthm: When element $x_j$ arrives we update our sample with value $x_j$ with probability $1/j$.

## Estimating F0
**Naive algorithmic solutions**:
- Maintain a bitmask with n bits, one per item in the universe. When an element x appears in the stream, if BITMASK\[x] = 0, set it to 1. Space complexity of O(n)
- Store the whole stream. Space complexity O(mlog(n))
- Let d be a dictionary, for each x in stream, if x is in dictionary d, do nothing, else add x to d. Return size of d. O(min(n, mlog(n))) in worst case.

**Algorithm 1: Linear counting**
Suppose we send each item x in the stream to a bucket according to some random hash function. Let Z be the number of buckets that didn't receive any item. In expectation, E\[Z]= k(1 - 1/k)^F0.

Estimator: F0 = k ln (k/z)

- Setting the number of bins k requires knowing F_0, the quanity we want to estimate.
- By computing the variance od Z, then applying Chebyshev, we obtain the corollary: Setting k = f0/12 yields standard error of less than 1%
- however, f0 can be O(n) so the space can be large using this approach.
Can do we better?

**Algorithm 2: Idealized F0 estimation**
Suppose we have access to a random hash function h:U -> \[0, 1].
- V <- +inf
- For each x
	- if h(x) < V then V <- h(x)
- At the end of the stream output 1/v-1 as our estimate

Why does this work? Assume the hash function is fully random
- Z = min(X1, ..., Xn) where Xi ~ U\[0, 1] for i in \[n]

whats the expectation of E\[Z].

E\[Z] = integral from 0 to 1 of Pr(Z > t)dt = 1/n + 1

key assumption here is an idealized hash function that maps each element of universe into a string of random bytes.

## Algorithms for estimating F1
**Morris Algorithm**
- Key idea: instead of maintain the actual length of the stream m, keep the logarithim. This lets us represent m approximatiely.


**How to save 1 bit?**
- Maintain a counter **c**
- init c <- 0
- process()
- For each item in the stream
	- increase c with probability 1/2
	- o/w keep the same value
- output estimate 2c.

Let Z be the value of the counter after m increments
- Z~Bin(m, 1/2)
	- E\[Z] = m/2
	- Var\[Z] = m/4
	- Space complexity: log(m/2) = log(m) - 1 -> we've saved one bit at the cost of accuracy.

**How to save k bits?**
- Maintain a counter **c**
- init c <- 0
- process()
- For each item in the stream
	- increase c with probability 1/2^k
	- o/w keep the same value
- output estimate (2^k)c.

Let Z be the value of the counter after m increments
- Z~Bin(m, 2^-k)
	- E\[Z] = m/2^k
	- Var\[Z] ~ m/2^k
	- Space complexity: log(m/2) = log(m) - k -> we've saved one bit at the cost of accuracy.

## Properties of Morris algorithm
1. The expectation of the variable Z = 2^xm satisfies the following: E\[Z] = m + 1

Corollary: Morris algorithm outputs an unbiased estimator of m.
1. The variance of Z is equal to m(m-1)/2

Suppose we run s morris counters and we output the average?
- The average of the estimator is the same
- The variance scales down by a factor of 1/s

Morris algorithm was recently proven to be space optimal for F1.