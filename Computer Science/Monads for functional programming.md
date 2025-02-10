## 1 Introduction
---
Functional programming community divides into two camps:
1. **Pure** languages such as Miranda and Haskell are lambda calculus pure and simple.
2. **Impure** languages such as Scheme and Standard ML, augment lambda calculus with a number of possible *effects* such as assignment, exceptions, or continuations.

Pure languages are easier to reason about and may benefit from lazy evaluation. Impure languages offer efficiency benefits and sometimes make possible a more compact mode of expression.

Recent advanced have suggested new approaches that may integrate the benefits of the pure and impure schools. These notes describe one, the use of *monads* to integrate impure effects into pure functional languages.

-  The application of monads will be illustrated with three case studies. 
- Section 2 introduced monads by showing they can be used to structure a simple evaluator so that it is easy to modify. 
- Section 3 described the laws satisfied by monads.
- Section 4 shows how monads provide a new solution to the old problem of providing updatable state in pure functional languages.
- Section 5 applies monads to the problem of building recursive descent parsers.

It is doubtful that the structuring methods presented here would have been discovered without the insight afforded by category theory. 

## 2 Evaluating monads
---
Pure functional languages have this advantage: all flow of data is made explicit. And this disadvantage: sometimes it is painfully explicit.

A program in a pure functional language is written as a set of equations. 

Explicit data flow ensures that the value of an expression depends only on its free variables. Hence substitution of equals for equals is always valid, making such programs especially easy to reason about. Explicit data flow also ensures that the order of computation is irrelevant, making such programs susceptible to lazy evaluation.

It is with regard to modularity that explicit data flow becomes both a blessing and a curse.
-  All data in and all data out are rendered manifest and accessible, providing a maximum of flexibility.
-  The essence of an algorithm can become buried under the plumbing required to carry data from its point of creation to its point of use.

Say you write an evaluator in a pure functional language.
- To add error handling to it, I need to modify each recursive call to check for and handle errors appropriately. Had I used an impure language with exceptions, no such restructuring would be needed.
- To add a count of operations performed to it, I need to modify each recursive call to pass around such counts appropriately. Had I used an impure language with a global variable that could be incremented, no such restructuring would be needed.
- To add an execution trace to it, I need to modify each recursive call to pass around such traces appropriately. Had I used an impure language that performed output as a side effect, no such restructuring would be needed.

Or, you could use a *monad*.

These notes show how to use monads to structure an evaluator so that the changes mentioned above are simple to make. In each case, all that is required is to redefine the monad and to make a few local changes.

We begin with the basic evaluator for simple terms, then consider variations that mimic exceptions, state, and output. We analyse these for commonalities, and abstract from these the concept of a monad. We then show how each of the variations fits into the monadic framework.

### 2.1 Variation zero: The basic evaluator
The evaluator acts on terms, which for purposes of illustration are simple.

```
data Term = Con Int | Div Term Term
```

A term is either a constant `Con a`, where `a` is an integer, or a quotient, `Div t u`, where `t` and `u` are terms. The basic evaluatior:

```
eval           :: Term -> Int
eval (Con a)   = a
eval (Div t u) = eval t / eval u
```

We use "/" to denote integer division. The following will provide running examples.

```
answer, error :: Term
answer        = (Div (Div (Con 1972)(Con 2))(Con 23))
error         = (Div (Con 1)(Con 0))
```

Computing *eval answers* yields the value of $(1972/2)/23$ which is $42$. The basic evaluator does not incorporate error handling so the result of eval error is undefined.

### 2.2 Variation one: Exceptions
Say we want to add error checking, in an impure language this is easily achieved with the use of exceptions. In a pure language exception handling may be mimicked by introducing a type to represent computations that may raise an exception.

```
data M a       = Raise Exception | Return a
type Exception = String
```

A value of type `M a` either has the form of `Raise e` where `e` is an exception or `Return a` where `a` is a value of type `a`.

> [!note] 
> A word on the difference between ‘data’ and ‘type’ declarations. A ‘data’ declaration introduces a new data type, in this case M , and new constructors for values of that type, in this case Raise and Return. A ‘type’ declaration introduces a new name for an existing type, in this case Exception becomes another name for String.

It's straightforward but tedious to adapt the evaluator to this representation.

```
eval           :: Term -> M Int
eval (Con a)   = Return a
eval (Div t u) = case eval t of
                   Raise e -> Raise e
                   Return a ->
                     case eval u of 
                       Raise e -> Raise e
                       Return b ->
                         if b == 0
                           then Raise "divide by zero"
                           else Return (a / b)
```

At each call of the evaluator, the form of the result must be checked: if an exception was raised it is re-raised, and if a value was returned it is processed.

### 2.3 Variation two: State
Forget errors, say we desire to count the number of divisions performed during evaluation. In an impure language, this is easily achieved by using state. Set a given variable to zero and increment it by one each time a division occurs. In a pure language, state may be mimicked by introducing a type to represent computations that act on state.

```
type M a   = State -> (a, State)
type State = Int
```

Now a value type `M a` is a function that accepts the initial state, and returns the computed value paired with the final state.

Again, it's straightforward but tedious to adapt the evaluator to this representation.

```
eval             :: Term -> M Int
eval (Con a) x   = (a, x)
eval (Div t u) x = let (a, y) = eval t x in
                   let (b, z) = eval u y in
                   (a / b, z + 1)
```

At each call of the evaluator, the old state must be passed in, and the new state extracted from the result and passed on appropriately.

### 2.4 Variation three: Output
Say you want to display a trace of execution. In an impure language, this is easily done by inserting output commands at appropriate points.

In a pure language, output may be mimicked by introducing a type to represent computations that generate output.

```
type M a    = (Output, a)
type Output = String
```

Now a value of type `M a` consists of the output generated paired with the value computed.

It's straightforward but tedious to adapt the evaluator to this representation.

```
eval           :: Term -> M int
eval (Con a)   = (line (Con a) a, a)
eval (Div t u) = let (x, a) = eval t in
				 let (y, b) = eval u in 
				 (x ++ y ++ line (Div t u) (a / b), a/b)

line           :: Term -> Int -> Output
line t a       = "eval (" ++ showterm t ++ ") <= " ++ showint a ++ "↩"
```

At each call of the evaluator, the outputs must be collected and assembled to form the output of the enclosing call. The function line generates one line of the output. Here `showterm` and `showint` convert terms and integers to strings, ++ concatenates strings, and “↩” represents the string consisting of a newline.

From the discussion so far, it may appear that programs in impure languages are easier to modify than those in pure languages. But sometimes the reverse is true. Say that it was desired to modify the previous program to display the execution trace in the reverse order.

This is easy to achieve with the pure program: just replace the term
```
x ++ y ++ line (Div t u) (a / b)
```
with
```
line (Div t u) (a / b) ++ y ++ x
```

It is not so easy to modify the impure program to achieve this effect. The problem is that output occurs as a side-effect of computation, but one now desires to display the result of computing a term before displaying the output generated by that computation. This can be achieved in a variety of ways, but all require substantial modification to the impure program.

### 2.5 A monadic evaluator
Each of the variations on the interpreter has a similar structure, which may be abstracted to yield the notion of a *monad*.

In each variation, we introduce a type of computations. M represented the computations that could raise exceptions, act on state, and generate output. M here obviously stands for *monad*.

The original evaluator has a type `Term -> Int`, while in each variation its type took the form `Term -> M Int`. In general a function of type `a -> b` is replaced by a function of type `a -> M b`. This can be read as a function that accepts an argument of type `a` and returns a result of type `b` with a possible additional effect captured by `M`. This effect may be to act on state, generate output, raise an exception, or what have you.

What sort of operations are required on the type *M*? Examination of the examples reveals two. First, we need a way to turn a value into the computation that returns that value and does nothing else.

```
unit :: a -> M a
```

Second, we need a way to apply a function of type `a -> M b` to a computation of type `M a`. It is convenient to write these in an order where the argument comes before the fucntion.

```
(*) :: M a -> (a -> M b) -> M b
```

> [!definition] 
> A *monad* is a triple $\langle M, unit, *\rangle$ consisting of a type constructor $M$ and two operations of the given polymorphic types. These operations must satisfy three laws given in Section 3.
> 

We often write expressions in the form $$m * \lambda a.n$$
where *m* and *n* are expressions, and *a* is a variable. The form $\lambda a. n$ is a lambda expression, with the scope of the bound variable *a* being the expression *n*. The above can be read as follows: perform computation *m*, bind *a* to the resulting value, and then perform computation *n*.

Types provide a useful guide. From the type of `(*)`, we can see the expression *m* has the type `M a`, variable *a* has the type `a`, expression *n* has the type `M b`, lambda expression $\lambda a. n$ has the type `a -> M b`, and the whole expression has type `M b`.

The above is analogous to the expression
```
let a = m in n
```

In an impure language, this has the same reading: Perform computation m, bind a to the resulting value, then perform computation n and return its value.

Here the types say nothing to distinguish values from computations: expression m has type a, variable a has type a, expression n has type b, and the whole expression has type b. The analogy with ‘let’ explains the choice of the order of arguments to `*`. It is convenient for argument m to appear before the function $\lambda a. n$, since  computation m is performed before computation n.

The evaluator is easily rewritten in terms of these abstractions.

```
eval :: Term -> M Int
eval (Con a) = unit a
eval (Div t u) = eval t *  λa. eval u * λb. unit (a / b)
```

A word on precedence: lambda abstraction binds least tightly and application binds most tightly.

The type `Term -> M Int` indicates that the evaluator takes a term and performs a computation yielding and integer. To compute `(Con a)`, just return `a`. To compute `(Div t u)`, first compute `t`, bind `a` to the result, then compute `u`, bind `b` to the result, and then return `a / b`.

The new evaluator is a little more complex than the original basic evaluator but much more flexible. Each of the variations given above may be achieved by simply changing the definition of `M`, `unit`, and `*`, and by making one or two local modifications.

### 2.6 Variation zero, revisited: The basic evaluator
In the simplest monad, a computation is no different from a value.
```
type M a = a
unit     :: a -> I a
unit a   = a
(*)      :: M a -> (a -> M b) -> M b
a * k    = k a
```

This is called the *identity* monad: *M* is the identity function on types, *unit* is the identity function, and * is just application.

Taking M, unit, and * as above in the monadic evaluator of section 2.5 and simplifying yields the basic evaluator of section 2.1

### 2.7 Variation one, revisited: Exceptions
In the exception monad, a computation may either raise an exception or return a value.
```
data M a       = Raise Exception | Return a
type Exception = String
unit           :: a -> M a
unit a         = Return a
(*)            :: M a -> (a -> M b) -> M b 
m * k          = case m of
				   raise e -> raise e
				   Return a -> k a
raise          :: Exception -> M a
raise e        = Raise e
```


### 2.8 Variation two, revisited: State
```
type M a   = State -> (a, State)
type State = Int
unit       :: a -> M a
unit a     = λx . (a, x)
(*)        :: M a -> (a -> M b) -> M b
m * k      = λx . let (a, y) = m x in
                  let (b, z) = k a y in
                  (b, z)
tick       :: M ()
tick       = λx . ((), x + 1)
```

In an impure language, an operation like tick would be represented by a function of type `() -> ()`. The spurious argument `()` is required to delay the effect until the function is applied, and since the output type is `()` one may guess that the function’s purpose lies in a side effect. In contrast, here tick has type `M ()`: no spurious argument is needed, and the appearance of M explicitly indicates what sort of effect may occur.

### 2.9 Variation three, revisited: Output
```
type M a    = (Output, a)
type Output = String
unit        :: a -> M a
unit a      = (“ ”, a)
(*)         :: M a -> (a -> M b) -> M b
m * k = let (x , a) = m in
		let (y, b) = k a in
		(x ++ y, b)
out         :: Output -> M ()
out x       = (x , ())
```

## 3 Monad laws
---
The operations of a monad satisfy three laws.

1. *Left unit.* Compute the value $a$, bind $b$ to the result, and compute $n$. The result is the same as $n$ with the value $a$ substituted for variable $b$. $$\text{unit } a * \lambda b. n = n[a/b].$$
2. *Right unit.* Compute $m$, bind the result to $a$, and return $a$. The result is the same as $m$. $$m * \lambda a. \text{unit } a = m.$$
3. *Associative.* Compute $m$, bind the result to $a$, compute $n$, bind the result to $b$, compute $o$. The order of parentheses in such a computation is irrelevant. $$m * (\lambda a. n * \lambda b. o) = (m * \lambda a. n) * \lambda b. o$$ The scope of the variable a includes o on the left but excludes o on the right, so this law is valid only when a does not appear free in o.

A binary operation with left and right unit that is associative is called a monoid. A monad differs from a monoid in that the right operand involves a binding operation.

To demonstrate the utility of these laws, we prove that addition is associative. Consider a variant of the evaluator based on addition rather than division.

```
data Term      = Con Int | Add Term Term
eval           :: Term -> M Int
eval (Con a)   = unit a
eval (Add t u) = eval t * λa. eval u * λb. unit (a / b)
```

We show that evaluation of 

```
Add t (Add u v ) and Add (Add t u) v,
```

both compute the same result. Simplify the left term:
```
eval (Add t (Add u v ))
= { def’n eval }
eval t * λa. eval (Add u v ) * λx . unit (a + x )
= { def’n eval }
eval t * λa. (eval u * λb. eval v * λc. unit (b + c)) * λx . unit (a + x )
= { associative }
eval t * λa. eval u * λb. eval v * λc. unit (b + c) * λx . unit (a + x )
= { left unit }
eval t * λa. eval u * λb. eval v * λc. unit (a + (b + c))
```

Simplify the right term similarly:
```
eval (Add (Add t u) v )
= { as before }
eval t * λa. eval u * λb. eval v * λc. unit ((a + b) + c)
```

The result follows by the associativity of addition. This proof is trivial; without the monad laws, it would be impossible.

The proof works in any monad.

Note that for each monad we can define the following operations.
```
map     :: (a -> b) -> (M a -> M b)
map f m = m * λa. unit (f a)
join    :: M (M a) -> M a
join z  = z * λm. m
```

The map operation simply applies a function to the result yielded by a computation. To compute map f m, first compute m, bind a to the result, and then return f a. The join operation is trickier. Let z be a computation that itself yields a computation. To compute join z, first compute z, binds m to the result, and then behaves as computation m. Thus, join flattens a mind-boggling double layer of computation into a run-of-the-mill single layer of computation. Lists form a monad, and for this monad map applies a function to each element of a list, and join concatenates a list of lists.

Using `id` for the identity function `(id x = x )`, and `(·)` for function composition
`((f · g) x = f (g x ))`, one can then formulate a number of laws.

```
map id          = id
map (f · g)     = map f · map g
map f · unit    = unit · f
map f · join    = join · map (map f )
join · unit     = id
join · map unit = id
join · map join = join · join
m * k           = join (map k m)
```

The proof of each is a simple consequence of the definitions of map and join and the three monad laws.

Often, monads are defined not in terms of unit and `*`, but rather in terms of unit, join, and map.

The three monad laws are replaced by the first seven of the eight laws above. If one defines `*` by the eighth law, then the three monad laws follow. Hence the two definitions are equivalent.
