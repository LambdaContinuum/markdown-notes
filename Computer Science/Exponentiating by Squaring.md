This is a general method fort fast computation of large positive integer powers of a number.

**Basic Method**.

For any integer n > 0: $$x^n = x(x^2)^{(n-1)/2}, 
\text{ if n is odd}$$ $$x^n = (x^2)^{n/2}, 
\text{ if n is odd}$$
If the exponent n is zero then the answer is 1. If the exponent is negative then we can reuse the previous formula by rewriting the value using a positive exponent. $$x^n = (\frac{1}{x})^{-n}$$
Together, you can implement this directly as a recursive algorithm:
```
 In: a real number x; an integer n
 Out: xn
 
 exp_by_squaring(x, n)
   if n < 0 then
      return exp_by_squaring(1 / x, -n);
   else if n = 0 then 
      return 1;
   else if n is even then 
      return exp_by_squaring(x * x, n / 2);
   else if n is odd then 
      return x * exp_by_squaring(x * x, (n - 1) / 2);
 end function
```

On each recursive call, the least significant digits of the binary representation of n is removed. It follows the number of recursive calls is $\lceil \log_2 n \rceil$, the number of bits of the binary representation of n.

This algorithm computes this number of squares and a lower number of multiplication, which is equal to the number of 1 in the binary representation of n. This logarithmic number of operations is to be compared with the trivial algorithm which requires n-1 multiplication.

This algorithm isn't tail recursive. It requires an amount of memory that is roughly proportional to the number of recursive calls, maybe higher if the amount of data per iteration is increasing.

See version with constant auxiliary memory at wiki

**Computational Complexity**
Such an algorithm uses $\lfloor \log_2 n \rfloor$ squaring and at most $\lfloor \log_2 n \rfloor$ multiplications. The number of multiplications is one less than the number of ones present in the binary expansion of n. For n greater than about 4 this is computationally more efficient then naively multiplying the base with itself repeatedly. 

Each squaring results in approximately double the number of digits of the previous, so, if multiplication of two d-digit numbers is implemented in $O(d^k)$ operations for some fixed $k$ then the complexity of computing $x^n$ is given by: $$\sum^{O(\log n)}_{i = 0} (2^i O(\log x ))^k = O(
(n \log x)^k)$$
Further methods of implementing more complex versions of this algorithm on the wiki.