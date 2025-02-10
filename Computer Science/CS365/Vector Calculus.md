## Level Curves
---
The level curves of a function $f$ of two variables $x, y$ are the curves with equation $$f(x, y) = c$$
where $c$ is a constant in the range of $f$.

## Refresher: Single variable function
---
The different quotient computes the slope of the secant line through two points of $y=f(x)$. $$\frac{\delta y}{\delta x} = \frac{f(x + \delta x) - f(x)}{\delta x}$$
The idea of the derivative $f'(x)$ is that it is the slope of the tangent line at $x$ to the curve. $$\frac{df}{dx}=\lim_{h \to 0}\frac{f(x + h)-f(x)}{h}$$
- Product rule: $(f(x)g(x))' = f'(x)g(x) + f(x)g'(x)$
- Quotient rule: $(\frac{f(x)}{g(x)})' = \frac{f'(x)g(x) - f(x)g'(x)}{(g(x))^2}$
- Sum rule: $(f(x) + g(x))' = f'(x) + g'(x)$
- Chain rule: $(g(f(x)))' = (g \circ f)'(x) = g'(f(x))f'(x)$

## Matrix Calculus
---
Scalar field: A function $f$ that maps a vectors to reals $f: \mathbb{R}^n \to \mathbb{R}$.
Vector field: $f: \mathbb{R}^n \to \mathbb{R}^m$.

## Gradient of Scalar Field
---
Partial derivative at $x = (x_1, ..., x_n)$: $$\frac{\partial f}{\partial x_i} = \lim_{h \to 0} \frac{f(x_1, ..., x_i + h, ..., x_n) - f(x_1, ..., x_i, ..., x_n)}{h}, i= 1,...,n$$
We collect them at the row vector known as the gradient of the function $f$:  $$\nabla f(x) = \nabla_x f = \text{grad}f = (\frac{\partial f}{\partial x_1}, \frac{\partial f}{\partial x_2}, ..., \frac{\partial f}{\partial x_n}) \in \mathbb{R}^{1 \times n}$$
Remark: the gradient collects the slopes in the positive $x_i$ direction for all $i = 1..n$ 
## Directional Derivative
---
Instead of computing the slopes in the positive $x_i$ direction for all $i = 1 ... n$, we can compute the derivative along any direction.
	- Directional derivative

$$\nabla_v f(x) = D_vf(x) = \lim_{h \to 0} \frac{f(x + hv) - f(x)}{h} = \nabla f(x) \cdot v$$

## Hessian of a scalar field
---
If all second partial derivatives of $f$ exist and are continuous over the domain of the function, then the Hessian matrix is a square matrix, usually defined and arranged as follows: $$\mathbf{H}_f = \begin{bmatrix}\frac{\partial^2f}{\partial x^2_1} & \frac{\partial^2f}{\partial x_1 \partial x_2} & ... & \frac{\partial^2f}{\partial x_1\partial x_n}\\
\frac{\partial^2f}{\partial x_2 \partial x_1} & \frac{\partial^2f}{\partial x^2_2} & ... & 
\frac{\partial^2f}{\partial x_2 \partial x_n}\\
\vdots & \vdots & \ddots & \vdots\\
\frac{\partial^2f}{\partial x_n \partial x_1} & 
\frac{\partial^2f}{\partial x_n \partial x_2} & ... & \frac{\partial^2f}{\partial x^2_n}\end{bmatrix}$$
- The symmetry of $H$ is not a coincidence; if $f(x, y)$ is twice continuously differentiable function, then $$\frac{\partial^2f}{\partial x \partial y} = \frac{\partial^2f}{\partial y \partial x}$$
- This is known as Schwarz's theorem.


## Taylor Polynomial
---
The Taylor Polynomial of degree $n$ of $f: \mathbb{R} \to \mathbb{R}$ at $x_0$ is defined as 

where $f^{(k)}(x_0)$ is the $k$-th derivative of $f$ at $x_0$. $$T_n (x) = \sum^n_{k = 0}\frac{f^{(k)}(x_0)}{k!}(x - x_0)^k$$
**Example:**
- Taylor polynomial $T_6$ for $f(x) = x^4$ evaluated at $x_0 = 1$. $$T_6(x) = 1 + 4(x - 1) + 6(x - 1)^2 + 4(x - 1)^3 + (x - 1)^2 + 0 = ... = x^4$$
- Taylor Series for trigonometric functions: $$\cos(x) = \sum_{k=0}^\infty (-1)^k\frac{1}{(2k)!}x^{2k}$$ $$\sin(x) = \sum_{k=0}^\infty (-1)^k\frac{1}{(2k + 1)!}x^{2k + 1}$$
 
## Taylor Series
---
The Taylor series of a smooth function $f: \mathbb{R} \to \mathbb{R}$ at $x_0$ is defined as $$T_\infty (x) = \sum_{k=0}^{+\infty}\frac{f^{(k)}(x_0)}{k!}(x-x_0)^k$$ For $x_0 = 0$, we obtain Maclaurin series as a special instance of the Taylor series.

**Example:**
$$f(x) \approx f(x_0) + \nabla f(x_0)(x-x_0) + \frac{1}{2}(x-x_0)^T H_f(x_0)(x-x_0)$$

## Chain rule
---
$$\frac{\partial}{\partial x}(g \circ f)(x)= \frac{\partial}{\partial x}g(f(x)) = \frac{\partial g}{\partial f}\frac{\partial f}{\partial x}$$
**Examples:**
Consider a function $f: \mathbb{R}^2 \to  \mathbb{R}$ of two variables $x_1, x_2$. Furthermore, suppose that $x_1, x_2$ are functions of a variable $t$. $$\frac{df}{dt} = \begin{bmatrix}\frac{\partial f}{\partial x_1} & \frac{\partial f}{\partial x_2}\end{bmatrix} \begin{bmatrix}\frac{\partial x_1 (t)}{\partial t} \\ \frac{\partial x_2(t)}{\partial t}\end{bmatrix}$$
Consider a function $f: \mathbb{R}^2 \to  \mathbb{R}$ of two variables $x_1, x_2$. Furthermore, suppose that $x_1, x_2$ are functions of two variables  $s, t$. $$\text{Let } q = \begin{bmatrix}s, t\end{bmatrix}. \frac{df}{dq} = \begin{bmatrix}\frac{\partial f}{\partial x_1} & \frac{\partial f}{\partial x_2}\end{bmatrix} \begin{bmatrix}\frac{\partial x_1 (s, t)}{\partial s} & \frac{\partial x_1 (s, t)}{\partial t} \\ \frac{\partial x_2(s, t)}{\partial s} & \frac{\partial x_2(s, t)}{\partial t}\end{bmatrix}$$
## Generalized Chain rule
---
Let $z = f(x_1, ..., x_m)$ be a scalar field of $m$ variables, each of which is a differential function of $n$ independent variables $x_i = xi(t_1, ..., t_n)$. Then: $$\frac{\partial z}{\partial t_i} = \sum_{j=1}^m \frac{\partial z}{\partial x_j}\frac{\partial x_j}{\partial t_i} = \frac{\partial z}{\partial x_1}\frac{\partial x_1}{\partial t_i} + ... + \frac{\partial z}{\partial x_m}\frac{\partial x_m}{\partial t_i},i=1, ..., n$$
## 1st order derivatives of a vector field: Jacobian
---
$$f(x_1, ..., x_n) = \begin{bmatrix}f_1(x_1, ..., x_n)\\
...\\
f_m(x_1, ..., x_n)\end{bmatrix}$$
The collection of all first-order derivatives of a vector field/vector-valued function $f: \mathbb{R}^n \to \mathbb{R}^m$ is called the Jacobian. $$J = \nabla_\infty f = \frac{df(x)}{dx} = \begin{bmatrix}\frac{\partial f(x)}{\partial x_1} & ... & \frac{\partial f(x)}{\partial x_n}\end{bmatrix} = \begin{bmatrix}\frac{\partial f_1(x)}{\partial x_1} & ... & \frac{\partial f_1(x)}{\partial x_n}\\\vdots & \ddots & \vdots\\
\frac{\partial f_m(x)}{\partial x_1} & ... & \frac{\partial f_m(x)}{\partial x_n}
\end{bmatrix}$$
## Jacobian
---
Let $y_1 = -2x_1 + x_2$ and $y_2 = x_1 + x_2$. The Jacobian is simply $$J = \begin{bmatrix}\frac{\partial y_1}{\partial x_1} & \frac{\partial y_1}{\partial x_2}\\ \frac{\partial y_2}{\partial x_1} & \frac{\partial y_2}{\partial x_2}\end{bmatrix} = \begin{bmatrix}-2 & 1\\ 1 & 1\end{bmatrix}$$
This example generalized to the following. Let $f(x) = Ax$, where $A$ is a $m \times n$ matrix, and $x$ is an $m \times 1$ vector. Then, $$\frac{df}{dx} = A$$
## Parallelogram of Maximum Area
---
Find parallelogram of maximum area with a given perimeter.

$$\begin{align}
\max_{a, b, h}ah\\
2a + 2b = l\\
h \leq b\\
a, b, h \geq 0
\end{align}$$
Say we have a function
$$f : \mathbb{R}^n \to \mathbb{R}^{n \times n}$$
where $f(x) = \mathbf{x}\mathbf{x}^t$

How does the derivative look?

$\nabla f = (a_1, ..., a_n)$

what should the coordinates be? they're going to be matrixes

The partial derivatives have the same dimensionality as the output.

knapsack problem:

You have a bag with a capacity $C$, we have a bunch of items $1, ..., n$, has a value $v_1, ..., v_n$ and a weight $w_1, ..., w_n$.

We want to fill up the bag such that the value is maximized. Formally: Choose a subset $S \subseteq [n]$ such that the value of $S$ is maximized such that the total weight of $S \leq C$.

We should introduce a variable $X_i = \{0, 1\}$ where $X_i = 1$ means we choose the item. 

$$\max \sum_{i = 1}^{n} v_i \cdot X_i$$
s.t. $$\sum_{i=1}^n w_i X_i \leq C$$
Decision problem variant is NP-Complete (remember to look for a polytime reduction later)


clearly $a, b, h = b$ is an obvious solution so we have the following problem, find the parallelogram of max area with a given perimeter

$$\begin{align}
\max_{a, b}ab\\
2a + 2b = l\\
a, b \geq 0
\end{align}$$


well we know $a + b = \frac{l}{2}$

so $\max a(\frac{l}{2} -a)$, graphing shows the peak at $1/4$

Optimal solution: $a = b = \frac{l}{4} (h = b)$, so the optimal solution is a square.

## Transportation Problem
---
Minimize the cost of goods transported from:
- a set of $m$ sources to...
- a set of $n$ destinations
	- Subject to the supply and demand of the sources and destination respectively.

**Given:**
- $a_1, ..., a_m$: units to transfer from sources
- $b_1, ..., b_m$: units to receive by destinations
- $c_{ij}$: cost of transferring a unit from source $i$ to destination $j$.

Define $xij$ to be the number of units sent from $i$ to $j$, with constraints we're given:

$$
\min \sum_{i = 1}^{m}\sum_{j = 1}^{n}c_{ij}x_{ij}
$$
with the constraint that every factory sends out exactly its production:
$$
\sum_{j = 1}^n x_{ij} = a_i, i = 1, ..., m$$
and if the supply is equal to the demand
$$
\sum_{i = 1}^m x_{ij} = b_j, i = 1, ..., n$$

and the constraint that $x_{ij} \geq 0$

## a not so toy ml problem
---

If the data set is linearly separable (if there is a straight line that separates the positive from negative ), how would you model this problem?

what our are parameters?
how do we model our constraints?

paramteres: we want to find a line, a line is defined by a equation, and equation has parameters.

we want something of the form ax + b in the simple case, so we have parameters a and b.

$$\begin{align}y(N) > a(N) + b\\
y(P) < a(P) + b\end{align}$$

we want to see if $\exists a, b$ s.t. the above holds for every happy face and every negative face.

This is called a feasbility problem. not all problems are linearly separable, like the XOR problem.

so our constraints are:

$\begin{align}&\max m\\ &y(red_i) \geq a red_{i} + b + m, i = 1, ..., n \\ &y(green_i) \leq a green_{i} + b - m, i = 1, ..., k \end{align}$

