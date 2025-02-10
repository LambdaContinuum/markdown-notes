Strings of characters are a fundamental building block in computer science. The alphabet over which the strings are defined may vary with the application.

We define an *alphabet* to be any non-empty finite set. The members of the alphabet are the *symbols* of the alphabet. We generally use capital Greek letters $\Sigma$ and $\Gamma$ to designate alphabets.

The following are a few examples of alphabets.
$$\Sigma_1 = \{0, 1\}$$
$$\Sigma_2 = \{a, b, c,d ,e, f, g, h, i, j, k, l, m, n , o, p, q, r, s, t, u, v, w , x, y , z\}$$
$$\Gamma = \{0, 1, x, y, z\}$$
A *string over an alphabet* is a finite sequence of symbols from that alphabet usually written next to one another and not separated by commas. If $\Sigma_1 = \{0, 1\}$, then $01001$ is a string over $\Sigma_1$. 

If $w$ is a string over $\Sigma$ the *length* of $w$, written $|w|$, is the number of symbols that it contains. 

The string of length zero is called the *empty string* and is written $\epsilon$. The empty string plays the role of $0$ in a number system. 

If $w$ has length $n$, we can write $w = w_1w_2...w_n$ where each $w_i\in \Sigma$. The *reverse* of $w$, written $w^{\mathcal{R}}$, is the string obtained by writing $w$ in the opposite order (i.e., $w_nw_{n-1}...w_1$).

String $z$ is a *substring* of $w$ if $z$ appears consecutively within $w$. For example $cad$ is a substring of $abracadabra$.

If we have string $x$ of length $m$ and string $y$ of length $n$, the *concatenation* of $x$ and $y$, written $xy$, is the string obtained by appending $y$ to the end of $x$, as in $x_1...x_my_1...y_n$.

To concatenate a string with itself many times, we use the superscript notation $x^k$ to mean $$\overbrace{xx...x}^{k}.$$
The *lexicographic order* of strings is the same as the familiar dictionary order. We occasionally use a modified lexicographic order called *shortlex order* or simply *string order*, that is identical to lexicographic order, except that shorter strings precede longer strings. Thus the string ordering of all strings over the alphabet $\{0, 1\}$ is $$(\epsilon, 0, 1, 00, 01, 10, 11, 000, ...)$$
Say that $x$ is a *prefix* of string $y$ if a string $x$ exists where $xz = y$, and that $x$ is a *proper prefix* of $y$ if in addition $x \neq y$. 

A *language* is a set of strings. A language is *prefix-free* if no member is a proper prefix of another member.

