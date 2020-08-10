# Commutative Algebra

## Spring 2020 #5

Let $R$ be a ring and $f: M\to N$ and $g: N\to M$ be $R\dash$module homomorphisms such that $g\circ f = \id_M$.
Show that $N \cong \im f \oplus \ker g$.

## Fall 2019 #3

Let $R$ be a ring with the property that for every $a \in R, a^2 = a$.

(a) Prove that $R$ has characteristic 2.

(b) Prove that $R$ is commutative.


## Fall 2019 #6

Let $R$ be a commutative ring with multiplicative identity. Assume Zorn's Lemma.

(a) Show that
$$
N = \{r \in R \mid r^n = 0 \text{ for some } n > 0\}
$$
is an ideal which is contained in any prime ideal.

(b) Let $r$ be an element of $R$ not in $N$.
Let $S$ be the collection of all proper ideals of $R$ not containing any positive power of $r$. Use Zorn's Lemma to prove that
there is a prime ideal in $S$.

(c) Suppose that $R$ has exactly one prime ideal $P$ . Prove that every element $r$ of $R$ is either nilpotent or a unit.

## Spring 2019 #6

Let $R$ be a commutative ring with 1.

> Recall that $x \in R$ is nilpotent iff $xn = 0$ for
some positive integer $n$.

(a) Show that every proper ideal of $R$ is contained within a maximal ideal.

(b) Let $J(R)$ denote the intersection of all maximal ideals of $R$.

    Show that $x \in J(R) \iff 1 + rx$ is a unit for all $r \in R$.

(c) Suppose now that $R$ is finite. Show that in this case $J(R)$ consists precisely
of the nilpotent elements in R.


## Fall 2018 #7

Let $R$ be a commutative ring.

(a) Let $r \in R$. Show that the map
\[
r\bullet : R &\to R \\
x &\mapsto r x
.\]
is an $R\dash$module endomorphism of $R$.

(b) We say that $r$ is a **zero-divisor** if r$\bullet$ is not injective.
Show that if $r$ is a zero-divisor and $r \neq 0$, then the kernel and image of $R$ each consist of zero-divisors.

(c) Let $n \geq 2$ be an integer. Show: if $R$ has exactly $n$ zero-divisors, then $\#R \leq n^2$ .

(d) Show that up to isomorphism there are exactly two commutative rings $R$ with precisely 2 zero-divisors.

> You may use without proof the following fact: every ring of order 4 is isomorphic to exactly one of the
following:
$$
\frac{ \ZZ }{ 4\ZZ}, \quad
\frac{ \frac{  \ZZ }{ 2\ZZ} [t]}{(t^2 + t + 1)}, \quad
\frac{ \frac{ \ZZ }{ 2\ZZ} [t]}{ (t^2 - t)}, \quad
\frac{ \frac{ \ZZ}{2\ZZ}[t]}{(t^2 )}
.$$


## Spring 2018 #5

Let 
$$
M=\left(\begin{array}{ll}{a} & {b} \\ {c} & {d}\end{array}\right)
\quad \text{and} \quad 
N=\left(\begin{array}{cc}{x} & {u} \\ {-y} & {-v}\end{array}\right)
$$

over a commutative ring $R$, where $b$ and $x$ are units of $R$. 
Prove that
$$
M N=\left(\begin{array}{ll}{0} & {0} \\ {0} & {*}\end{array}\right)
\implies MN = 0
.$$


## Spring 2018 #8

Let $R = C[0, 1]$ be the ring of continuous real-valued functions on the interval $[0, 1]$. Let I be an ideal of $R$.

(a) Show that if $f \in I, a \in [0, 1]$ are such that $f (a) \neq 0$, then there exists $g \in I$ such that $g(x) \geq 0$ for all $x \in [0, 1]$, and $g(x) > 0$ for all $x$ in some open neighborhood of $a$.

(b) If $I \neq R$, show that the set $Z(I) = \{x \in [0, 1] \suchthat f(x) = 0 \text{ for all } f \in I\}$ is nonempty.

(c) Show that if $I$ is maximal, then there exists $x_0 \in [0, 1]$ such that $I = \{ f \in R \suchthat f (x_0 ) = 0\}$.

## Fall 2017 #5

A ring R is called *simple* if its only two-sided ideals are $0$ and $R$.

(a) Suppose $R$ is a commutative ring with 1. Prove $R$ is simple if and only if $R$ is a field.

(b) Let $k$ be a field. Show the ring $M_n (k)$, $n \times n$ matrices with entries in $k$, is a simple ring.


## Fall 2017 #6

For a ring $R$, let $U(R)$ denote the multiplicative group of units in $R$. Recall that in an integral domain $R$, $r \in R$ is called *irreducible* if $r$ is not a unit in R, and the only divisors of $r$ have the form $ru$ with $u$ a unit in $R$. 

We call a non-zero, non-unit $r \in R$ *prime* in $R$ if $r \divides ab \implies r \divides a$ or $r \divides b$. 
Consider the ring $R = \{a + b \sqrt{-5}\suchthat a, b \in Z\}$.

(a) Prove $R$ is an integral domain.

(b) Show $U(R) = \{\pm1\}$.

(c) Show $3, 2 + \sqrt{-5}$, and $2 - \sqrt{-5}$ are irreducible in $R$.

(d) Show 3 is not prime in $R$.

(e) Conclude $R$ is not a PID.


## Spring 2017 #3

Let $R$ be a commutative ring with 1.
Suppose that $M$ is a free $R\dash$module with a finite basis $X$.

a. Let $I \normal R$ be a proper ideal.
  Prove that $M/IM$ is a free $R/I\dash$module with basis $X'$, where $X'$ is the image of $X$ under the canonical map $M\to M/IM$.

b. Prove that any two bases of $M$ have the same number of elements.
  You may assume that the result is true when $R$ is a field.


## Spring 2017 #4

a. Let $R$ be an integral domain with quotient field $F$.
  Suppose that $p(x), a(x), b(x)$ are monic polynomials in $F[x]$ with $p(x) = a(x) b(x)$ and with $p(x) \in R[x]$, $a(x)$ not in $R[x]$, and both $a(x), b(x)$ not constant.
  Prove that $R$ is not a UFD.
  (You may assume Gauss' lemma)

b. Prove that $\ZZ[2\sqrt{2}]$ is not a UFD.

  > Hint: let $p(x) = x^2-2$.


## Spring 2016 #8

Let $R$ be a simple rng (a nonzero ring which is not assume to have a 1, whose only two-sided ideals are $(0)$ and $R$) satisfying the following two conditions:

i. $R$ has no zero divisors, and
ii. If $x\in R$ with $x\neq 0$ then $2x\neq 0$, where $2x\definedas x+x$.

Prove the following:

a. For each $x\in R$ there is one and only one element $y\in R$ such that $x = 2y$.
b. Suppose $x,y\in R$ such that $x\neq 0$ and $2(xy) = x$, then $yz = zy$ for all $z\in R$.

> You can get partial credit for (b) by showing it in the case $R$ has a 1.

## Fall 2015 #3
Let $R$ be a rng (a ring without 1) which contains an element $u$ such that for all $y\in R$, there exists an $x\in R$ such that $xu=y$.

Prove that $R$ contains a maximal left ideal.

> Hint: imitate the proof (using Zorn's lemma) in the case where $R$ does have a 1.

## Fall 2015 #4
Let $R$ be a PID and $(a_1) < (a_2) < \cdots$ be an ascending chain of ideals in $R$.
Prove that for some $n$, we have $(a_j) = (a_n)$ for all $j\geq n$.

## Spring 2015 #7
Let $R$ be a commutative ring, and $S\subset R$ be a nonempty subset that does not contain 0 such that for all $x, y\in S$ we have $xy\in S$.
Let $\mci$ be the set of all ideals $I\normal R$ such that $I\intersect S = \emptyset$.

Show that for every ideal $I\in \mci$, there is an ideal $J\in \mci$ such that $I\subset J$ and $J$ is not properly contained in any other ideal in $\mci$.

Prove that every such ideal $J$ is prime.


## Fall 2014 #7
Give a careful proof that $\CC[x, y]$ is not a PID.


## Fall 2014 #8
Let $R$ be a nonzero commutative ring without unit such that $R$ does not contain a proper maximal ideal.
Prove that for all $x\in R$, the ideal $xR$ is proper.
You may assume the axiom of choice.

## Spring 2014 #5

Let $R$ be a commutative ring and $a\in R$.
Prove that $a$ is not nilpotent $\iff$ there exists a commutative ring $S$ and a ring homomorphism $\phi: R\to S$ such that $\phi(a)$ is a unit.

> Note: by definition, $a$ is nilpotent $\iff$ there is a natural number $n$ such that $a^n = 0$.

## Spring 2014 #6
Let $R$ be a commutative ring with identity and let $n$ be a positive integer.

a. Prove that every surjective $R\dash$linear endomorphism $T: R^n \to R^n$ is injective.

b. Show that an injective $R\dash$linear endomorphism of $R^n$ need not be surjective.


## Fall 2013 #3

a. Define *prime ideal*, give an example of a nontrivial ideal in the ring $\ZZ$ that is not prime, and prove that it is not prime.

b. Define *maximal ideal*, give an example of a nontrivial maximal ideal in $\ZZ$ and prove that it is maximal.


## Fall 2013 #4
Let $R$ be a commutative ring with $1\neq 0$.
Recall that $x\in R$ is *nilpotent* iff $x^n = 0$ for some positive integer $n$.

a. Show that the collection of nilpotent elements in $R$ forms an ideal.

b. Show that if $x$ is nilpotent, then $x$ is contained in every prime ideal of $R$.

c. Suppose $x\in R$ is not nilpotent and let $S = \theset{x^n \suchthat n\in \NN}$.
  There is at least on ideal of $R$ disjoint from $S$, namely $(0)$.
  By Zorn's lemma the set of ideals disjoint from $S$ has a maximal element with respect to inclusion, say $I$.
  In other words, $I$ is disjoint from $S$ and if $J$ is any ideal disjoint from $S$ with $I\subseteq J \subseteq R$ then $J=I$ or $J=R$.

  Show that $I$ is a prime ideal.

d. Deduce from (a) and (b) that the set of nilpotent elements of $R$ is the intersection of all prime ideals of $R$.

## Spring 2013 #1
Let $R$ be a commutative ring.

a. Define a *maximal ideal* and prove that $R$ has a maximal ideal.

b. Show than an element $r\in R$ is not invertible $\iff r$ is contained in a maximal ideal.

c. Let $M$ be an $R\dash$module, and recall that for $0\neq \mu \in M$, the *annihilator* of $\mu$ is the set
  \[
  \ann(\mu) = \theset{r\in R \suchthat r\mu = 0}
  .\]
  Suppose that $I$ is an ideal in $R$ which is maximal with respect to the property that there exists an element $\mu \in M$ such that $I = \ann(\mu)$ for some $\mu \in M$.
  In other words, $I = \ann(\mu)$ but there does not exist $\nu\in M$ with $J = \ann(\nu) \subsetneq R$ such that $I\subsetneq J$.

  Prove that $I$ is a prime ideal.

## Spring 2013 #2

a. Define a *Euclidean domain*.

b. Define a *unique factorization domain*.

c. Is a Euclidean domain an UFD? 
  Give either a proof or a counterexample with justification.

d. Is a UFD a Euclidean domain?
  Give either a proof or a counterexample with justification.
