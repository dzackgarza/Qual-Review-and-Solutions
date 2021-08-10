# Commutative Algebra

## Spring 2020 #5 $\done$
Let $R$ be a ring and $f: M\to N$ and $g: N\to M$ be $R\dash$module homomorphisms such that $g\circ f = \id_M$.
Show that $N \cong \im f \oplus \ker g$.

## Fall 2019 #3 $\work$
Let $R$ be a ring with the property that for every $a \in R, a^2 = a$.

a.
Prove that $R$ has characteristic 2.

b.
Prove that $R$ is commutative.

:::{.concept}
\envlist

- Todo
:::

:::{.strategy}
\envlist

- Just fiddle with direct computations.
- Context hint: that we should be considering things like $x^2$ and $a+b$.

:::

:::{.solution}
\envlist

:::{.proof title="of a"}
\[
2a  = (2a)^2 = 4a^2 = 4a \implies 2a = 0
.\]
Note that this implies $x = -x$ for all $x\in R$.
:::

:::{.proof title="of b"}
\[
a+b = (a+b)^2 &= a^2 + ab + ba + b^2 = a + ab + ba + b \\
&\implies ab + ba = 0 \\
&\implies ab = -ba \\
&\implies ab = ba \quad\text{by (a)}
.\]

:::

:::

## Fall 2019 #6 $\done$
Let $R$ be a commutative ring with multiplicative identity. Assume Zorn's Lemma.

a.
Show that
$$
N = \{r \in R \mid r^n = 0 \text{ for some } n > 0\}
$$
is an ideal which is contained in any prime ideal.

b.
Let $r$ be an element of $R$ not in $N$.
Let $S$ be the collection of all proper ideals of $R$ not containing any positive power of $r$. Use Zorn's Lemma to prove that
there is a prime ideal in $S$.

c.
Suppose that $R$ has exactly one prime ideal $P$ . Prove that every element $r$ of $R$ is either nilpotent or a unit.

:::{.concept}
\envlist

- Prime ideal: $\mathfrak{p}$ is prime iff $ab \in \mathfrak{p} \implies a\in \mathfrak{p}$ or $b\in \mathfrak{p}$.
- Silly fact: 0 is in every ideal!
 
- **Zorn's Lemma:** Given a poset, if every chain has an upper bound, then there is a maximal element. (Chain: totally ordered subset.)
 
- **Corollary:** If $S\subset R$ is multiplicatively closed with $0\not\in S$ then $\theset{I \normal R \suchthat J\intersect S = \emptyset}$ has a maximal element.

  \todo[inline]{Prove this}

- **Theorem:** If $R$ is commutative, maximal $\implies$ prime for ideals.

  \todo[inline]{Prove this}

- **Theorem:** Non-units are contained in a maximal ideal. (See HW?)

:::

:::{.solution}
\envlist

:::{.proof title="of a"}
\envlist

- Let $\mathfrak{p}$ be prime and $x\in N$.
- Then $x^k = 0 \in \mathfrak{p}$ for some $k$, and thus $x^k = x x^{k-1} \in \mathfrak p$.
- Since $\mathfrak p$ is prime, inductively we obtain $x\in\mathfrak p$.
:::

:::{.proof title="of b"}
\envlist

- Let $S = \theset{r^k \mid k\in \NN}$ be the set of positive powers of $r$. 

- Then $S^2 \subseteq S$, since $r^{k_1}r^{k_2} = r^{k_1+k_2}$ is also a positive power of $r$, and $0\not\in S$ since $r\neq 0$ and $r\not\in N$.

- By the corollary, $\theset{I \normal R \suchthat I\intersect S = \emptyset}$ has a maximal element $\mathfrak{p}$.

- Since $R$ is commutative, $\mathfrak{p}$ is prime.

:::

:::{.proof title="of c"}
\envlist

- Suppose $R$ has a unique prime ideal $\mathfrak{p}$.

- Suppose $r\in R$ is not a unit, and toward a contradiction, suppose that $r$ is also not nilpotent.

- Since $r$ is not a unit, $r$ is contained in some maximal (and thus prime) ideal, and thus $r \in \mathfrak{p}$.

- Since $r\not\in N$, by (b) there is a maximal ideal $\mathfrak{m}$ that avoids all positive powers of $r$. 
Since $\mathfrak{m}$ is prime, we must have $\mathfrak{m} = \mathfrak{p}$.
  But then $r\not\in \mathfrak{p}$, a contradiction.

:::

:::

## Spring 2019 #6 $\done$
Let $R$ be a commutative ring with 1.

> Recall that $x \in R$ is nilpotent iff $xn = 0$ for
some positive integer $n$.

a.
Show that every proper ideal of $R$ is contained within a maximal ideal.

b.
Let $J(R)$ denote the intersection of all maximal ideals of $R$.
Show that $x \in J(R) \iff 1 + rx$ is a unit for all $r \in R$.

c.
Suppose now that $R$ is finite. Show that in this case $J(R)$ consists precisely
of the nilpotent elements in R.

:::{.concept}
\envlist

- Definitions:
\[
N(R) &\da \theset{x\in R \suchthat x^n = 0 \text{ for some } n} \\
J(R) &\da \intersect _{\mfm \in \mspec} \mfm
.\]

- Zorn's lemma: if $P$ is a poset in which every chain has an upper bound, $P$ contains a maximal element.


:::

:::{.solution}
\envlist

:::{.proof title="of a"}
Define the set of proper ideals
$$
S = \theset{J \suchthat I   \subseteq J < R}
,$$

which is a poset under set inclusion.

Given a chain $J_1 \subseteq \cdots$, there is an upper bound $J \definedas \union J_i$, so Zorn's lemma applies.


:::

:::{.proof title="of b, $\implies$"}
$\implies$:

- We will show that $x\in J(R) \implies 1+x \in R\units$, from which the result follows by letting $x=rx$.

- Let $x\in J(R)$, so it is in every maximal ideal, and suppose toward a contradiction that $1+x$ is **not** a unit.

- Then consider $I = \generators{1+x} \normal R$. 
Since $1+x$ is not a unit, we can't write $s(1+x) = 1$ for any $s\in R$, and so $1 \not\in I$ and $I\neq R$

- So $I < R$ is proper and thus contained in some maximal proper ideal $\mathfrak{m} < R$ by part (1), and so we have $1+x \in \mathfrak{m}$.
Since $x\in J(R)$, $x\in \mathfrak{m}$ as well.

- But then $(1+x) - x = 1 \in \mathfrak{m}$ which forces $\mathfrak{m} = R$.

:::

:::{.proof title="of b, $\impliedby$"}
$\impliedby$

- Fix $x\in R$, and suppose $1+rx$ is a unit for all $r\in R$.

 
- Suppose towards a contradiction that there is a maximal ideal $\mathfrak{m}$ such that $x\not \in \mathfrak{m}$ and thus $x\not\in J(R)$.

- Consider 
\[
M' \definedas \theset{rx + m \suchthat r\in R,~ m\in M}
.\]

- Since $\mathfrak{m}$ was maximal, $\mathfrak{m} \subsetneq M'$ and so $M' = R$.

- So every element in $R$ can be written as $rx + m$ for some $r\in R, m\in M$.
But $1\in R$, so we have 
\[
1 = rx + m
.\] 

- So let $s = -r$ and write $1 = sx - m$, and so $m = 1 + sx$.

- Since $s\in R$ by assumption $1+sx$ is a unit and thus $m \in \mathfrak{m}$ is a unit, a contradiction.

- So $x\in \mathfrak{m}$ for every $\mathfrak{m}$ and thus $x\in J(R)$.

:::

:::{.proof title="of c"}
- We want to show $J(R) = \mathfrak N(R)$.

$\mathfrak N(R) \subseteq J(R)$:

- We'll use the fact $x\in \mathfrak N(R) \implies x^n = 0 \implies 1 + rx$ is a unit $\iff x\in J(R)$ by (b):
$$
\sum_{k=1}^{n-1} (-x)^k = \frac{1 - (-x)^n}{1- (-x)} = (1+x)\inv
.$$

- $J(R) \subseteq \mathfrak N(R)$:

- Let $x \in J(R) \setminus \mathfrak N(R)$.

- Since $R$ is finite, $x^m = x$ for some $m > 0$.

- Without loss of generality, we can suppose $x^2 = x$ by replacing $x^m$ with $x^{2m}$.

- If $1-x$ is not a unit, then $\generators{1-x}$ is a nontrivial proper ideal, which by (a) is contained in some maximal ideal $\mm$. 
But then $x\in \mm$ and $1-x \in \mm \implies x + (1-x) = 1 \in \mm$, a contradiction.

- So $1-x$ is a unit, so let $u = (1-x)\inv$.

- Then
\[
(1-x)x &= x - x^2 = x - x = 0 \\
&\implies u (1-x)x = x = 0 \\
&\implies x=0
.\]

:::

:::

## Fall 2018 #7 $\done$
Let $R$ be a commutative ring.

a.
Let $r \in R$. Show that the map
\[
r\bullet : R &\to R \\
x &\mapsto r x
.\]
is an $R\dash$module endomorphism of $R$.

b.
We say that $r$ is a **zero-divisor** if $r\bullet$ is not injective.
Show that if $r$ is a zero-divisor and $r \neq 0$, then the kernel and image of $R$ each consist of zero-divisors.

c.
Let $n \geq 2$ be an integer. Show: if $R$ has exactly $n$ zero-divisors, then $\#R \leq n^2$ .

d.
Show that up to isomorphism there are exactly two commutative rings $R$ with precisely 2 zero-divisors.

> You may use without proof the following fact: every ring of order 4 is isomorphic to exactly one of the
following:
\[
\frac{ \ZZ }{ 4\ZZ}, \quad
\frac{ \frac{  \ZZ }{ 2\ZZ} [t]}{(t^2 + t + 1)}, \quad
\frac{ \frac{ \ZZ }{ 2\ZZ} [t]}{ (t^2 - t)}, \quad
\frac{ \frac{ \ZZ}{2\ZZ}[t]}{(t^2 )}
.\]

:::{.concept}
\envlist

- Todo
- See 1964 Annals "Properties of rings with a finite number of zero divisors"
:::

:::{.solution}
\envlist

:::{.proof title="of a"}
\envlist

- Let $\phi$ denote the map in question, it suffices to show that $\phi$ is $R\dash$linear, i.e. $\phi(s\vector x + \vector y) = s\phi(\vector x) + \phi(\vector y)$:
\[
\phi(s\vector x + \vector y) 
&= r(s\vector x + \vector y) \\
&= rs\vector x + r\vector y \\
&= s(r\vector x) + (r\vector y) \\
&= s\phi(\vector x) + \phi(\vector y)
.\]
:::

:::{.proof title="of b"}
Let $\phi_r(x) \da rx$ be the multiplication map.

- Let $x\in \ker \phi_r \da \ts{x\in R \st rx = 0}$.

- Since $R$ is commutative $0 = rx = xr$, and so $r\in \ker \phi_x$, so $\ker \phi_x \neq 0$ and $x$ is a zero divisor by definition.

- Let $y\in \im \phi_r \da \theset{y \da rx \suchthat x\in R}$, we want to show $\ker \phi_y$ is nontrivial by producing some $z$ such that $yz=0$.
  Write $y\da rx$ for some $x\in R$.

- Since $r$ is a zero divisor, we can produce some $z\neq 0 \in \ker \phi_r$, so $rz = 0$. 

- Now using that $R$ is commutative, we can compute
\[
yz = (rx)z = (xr)z = x (rz) = x(0) = 0
,\]
so $z\in \ker \phi_y$.
:::

:::{.proof title="of c"}
\envlist

- Let $Z \definedas \theset{z_i}_{i=1}^n$ be the set of $n$ zero divisors in $R$.
- Let $\phi_i$ be the $n$ maps $x \mapsto z_i x$, and let $K_i = \ker \phi_i$ be the corresponding kernels.
- Fix an $i$.
- By (b), $K_i$ consists of zero divisors, so 
\[
\abs{K_i} \leq n < \infty \quad \text{for each } i
.\]

- Now consider $R/K_i \definedas \theset{r + K_i}$.
- By the first isomorphism theorem, $R/K_i \cong \im \phi$, and by (b) every element in the image is a zero divisor, so 
\[
[R: K_i] = \abs{R/K_i} = \abs{\im \phi_i} \leq n 
.\]

- But then 
\[
\abs{R} = [R:K_i]\cdot \abs{K_i} \leq n\cdot n = n^2 
.\]

:::

:::{.proof title="of d"}
\envlist

- By (c), if there are exactly 2 zero divisors then $\abs{R} \leq 4$.
Since every element in a finite ring is either a unit or a zero divisor, and $\abs{R\units} \geq 2$ since $\pm 1$ are always units, we must have $\abs{R} = 4$.

- Since the characteristic of a ring must divide its size, we have $\ch R = 2$ or $4$.

- Using the hint, we see that only $\ZZ/(4)$ has characteristic 4, which has exactly 2 zero divisors given by $[0]_4$ and $[2]_4$.

- If $R$ has characteristic 2, we can check the other 3 possibilities.

- We can write $\ZZ/(2)[t]/(t^2) = \theset{a + bt \suchthat a,b\in \ZZ/(2)}$, and checking the multiplication table we have
\[
\begin{array}{c|cccc}
			& 0 & 1 	& t & 1+t 	\\ \hline
0 		& 0 & 0 	& 0 & 0   	\\ 
1 		& 0 & 1 	& t & 1+t 	\\ 
t 		& 0 & t 	& \mathbf{0} & t   	\\ 
1 + t & 0 & 1+t & t & 1   	\\ 
\end{array}
,\]

  and so we find that $t, 0$ are the zero divisors.

- In $\ZZ/(2)[t]/(t^2 - t)$, we can check that $t^2 = t \implies t t^2 = t^2 \implies t(t^2 + 1) = 0 \implies t(t+1) = 0$, so both $t$ and $t+1$ are zero divisors, along with zero, so this is not a possibility.

- Similarly, in $\ZZ/(2)[t]/(t^2 + t + 1)$, we can check the bottom-right corner of the multiplication table to find
\[
\left[\begin{array}{c|cc}
	& t 	& 1 +t \\ \hline
t & 1+t & 1 \\
t & 1 	& t \\
\end{array}\right]
,\]

  and so this ring only has one zero divisor.

- Thus the only possibilities are:
\[
R &\cong \ZZ/(4) \\
R &\cong \ZZ/(2)[t] / (t^2)
.\]

:::

:::

## Spring 2018 #5 $\work$
Let 
\[
M=\left(\begin{array}{ll}{a} & {b} \\ {c} & {d}\end{array}\right)
\quad \text{and} \quad 
N=\left(\begin{array}{cc}{x} & {u} \\ {-y} & {-v}\end{array}\right)
\]

over a commutative ring $R$, where $b$ and $x$ are units of $R$. 
Prove that
\[
M N=\left(\begin{array}{ll}{0} & {0} \\ {0} & {*}\end{array}\right)
\implies MN = 0
.\]

## Spring 2018 #8 $\work$
Let $R = C[0, 1]$ be the ring of continuous real-valued functions on the interval $[0, 1]$. Let I be an ideal of $R$.

a.
Show that if $f \in I, a \in [0, 1]$ are such that $f (a) \neq 0$, then there exists $g \in I$ such that $g(x) \geq 0$ for all $x \in [0, 1]$, and $g(x) > 0$ for all $x$ in some open neighborhood of $a$.

b.
If $I \neq R$, show that the set $Z(I) = \{x \in [0, 1] \suchthat f(x) = 0 \text{ for all } f \in I\}$ is nonempty.

c.
Show that if $I$ is maximal, then there exists $x_0 \in [0, 1]$ such that $I = \{ f \in R \suchthat f (x_0 ) = 0\}$.

## Fall 2017 #5 $\work$
A ring \( R \) is called *simple* if its only two-sided ideals are $0$ and $R$.

a.
Suppose $R$ is a commutative ring with 1. Prove $R$ is simple if and only if $R$ is a field.

b.
Let $k$ be a field. Show the ring $M_n (k)$, $n \times n$ matrices with entries in $k$, is a simple ring.

## Fall 2017 #6 $\work$
For a ring $R$, let $U(R)$ denote the multiplicative group of units in $R$. Recall that in an integral domain $R$, $r \in R$ is called *irreducible* if $r$ is not a unit in R, and the only divisors of $r$ have the form $ru$ with $u$ a unit in $R$. 

We call a non-zero, non-unit $r \in R$ *prime* in $R$ if $r \divides ab \implies r \divides a$ or $r \divides b$. 
Consider the ring $R = \{a + b \sqrt{-5}\suchthat a, b \in Z\}$.

a.
Prove $R$ is an integral domain.

b.
Show $U(R) = \{\pm1\}$.

c.
Show $3, 2 + \sqrt{-5}$, and $2 - \sqrt{-5}$ are irreducible in $R$.

d.
Show 3 is not prime in $R$.

e.
Conclude $R$ is not a PID.

## Spring 2017 #3 $\work$
Let $R$ be a commutative ring with 1.
Suppose that $M$ is a free $R\dash$module with a finite basis $X$.

a.
Let $I \normal R$ be a proper ideal.
Prove that $M/IM$ is a free $R/I\dash$module with basis $X'$, where $X'$ is the image of $X$ under the canonical map $M\to M/IM$.

b.
Prove that any two bases of $M$ have the same number of elements.
You may assume that the result is true when $R$ is a field.


## Spring 2017 #4 $\work$

a.
Let $R$ be an integral domain with quotient field $F$.
Suppose that $p(x), a(x), b(x)$ are monic polynomials in $F[x]$ with $p(x) = a(x) b(x)$ and with $p(x) \in R[x]$, $a(x)$ not in $R[x]$, and both $a(x), b(x)$ not constant.

  Prove that $R$ is not a UFD.

  > (You may assume Gauss' lemma)

b.
Prove that $\ZZ[2\sqrt{2}]$ is not a UFD.

  > Hint: let $p(x) = x^2-2$.

## Spring 2016 #8 $\work$
Let $R$ be a simple rng (a nonzero ring which is not assume to have a 1, whose only two-sided ideals are $(0)$ and $R$) satisfying the following two conditions:

i. $R$ has no zero divisors, and
ii. If $x\in R$ with $x\neq 0$ then $2x\neq 0$, where $2x\definedas x+x$.

Prove the following:

a.
For each $x\in R$ there is one and only one element $y\in R$ such that $x = 2y$.

b.
Suppose $x,y\in R$ such that $x\neq 0$ and $2(xy) = x$, then $yz = zy$ for all $z\in R$.

> You can get partial credit for (b) by showing it in the case $R$ has a 1.

## Fall 2015 #3 $\work$
Let $R$ be a rng (a ring without 1) which contains an element $u$ such that for all $y\in R$, there exists an $x\in R$ such that $xu=y$.

Prove that $R$ contains a maximal left ideal.

> Hint: imitate the proof (using Zorn's lemma) in the case where $R$ does have a 1.

## Fall 2015 #4 $\work$
Let $R$ be a PID and $(a_1) < (a_2) < \cdots$ be an ascending chain of ideals in $R$.
Prove that for some $n$, we have $(a_j) = (a_n)$ for all $j\geq n$.

## Spring 2015 #7 $\work$
Let $R$ be a commutative ring, and $S\subset R$ be a nonempty subset that does not contain 0 such that for all $x, y\in S$ we have $xy\in S$.
Let $\mci$ be the set of all ideals $I\normal R$ such that $I\intersect S = \emptyset$.

Show that for every ideal $I\in \mci$, there is an ideal $J\in \mci$ such that $I\subset J$ and $J$ is not properly contained in any other ideal in $\mci$.

Prove that every such ideal $J$ is prime.

## Fall 2014 #7 $\work$
Give a careful proof that $\CC[x, y]$ is not a PID.

## Fall 2014 #8 $\work$
Let $R$ be a nonzero commutative ring without unit such that $R$ does not contain a proper maximal ideal.
Prove that for all $x\in R$, the ideal $xR$ is proper.

> You may assume the axiom of choice.

## Spring 2014 #5 $\work$
Let $R$ be a commutative ring and $a\in R$.
Prove that $a$ is not nilpotent $\iff$ there exists a commutative ring $S$ and a ring homomorphism $\phi: R\to S$ such that $\phi(a)$ is a unit.

> Note: by definition, $a$ is nilpotent $\iff$ there is a natural number $n$ such that $a^n = 0$.

## Spring 2014 #6 $\work$
 $R$ be a commutative ring with identity and let $n$ be a positive integer.

a.
Prove that every surjective $R\dash$linear endomorphism $T: R^n \to R^n$ is injective.

b.
Show that an injective $R\dash$linear endomorphism of $R^n$ need not be surjective.

## Fall 2013 #3 $\work$

a.
Define *prime ideal*, give an example of a nontrivial ideal in the ring $\ZZ$ that is not prime, and prove that it is not prime.

b.
Define *maximal ideal*, give an example of a nontrivial maximal ideal in $\ZZ$ and prove that it is maximal.

## Fall 2013 #4 $\work$
Let $R$ be a commutative ring with $1\neq 0$.
Recall that $x\in R$ is *nilpotent* iff $x^n = 0$ for some positive integer $n$.

a.
Show that the collection of nilpotent elements in $R$ forms an ideal.

b.
Show that if $x$ is nilpotent, then $x$ is contained in every prime ideal of $R$.

c.
Suppose $x\in R$ is not nilpotent and let $S = \theset{x^n \suchthat n\in \NN}$.
There is at least on ideal of $R$ disjoint from $S$, namely $(0)$.

By Zorn's lemma the set of ideals disjoint from $S$ has a maximal element with respect to inclusion, say $I$.
In other words, $I$ is disjoint from $S$ and if $J$ is any ideal disjoint from $S$ with $I\subseteq J \subseteq R$ then $J=I$ or $J=R$.

Show that $I$ is a prime ideal.

d. 
Deduce from (a) and (b) that the set of nilpotent elements of $R$ is the intersection of all prime ideals of $R$.

## Spring 2013 #1 $\work$
Let $R$ be a commutative ring.

a.
Define a *maximal ideal* and prove that $R$ has a maximal ideal.

b.
Show than an element $r\in R$ is not invertible $\iff r$ is contained in a maximal ideal.

c.
Let $M$ be an $R\dash$module, and recall that for $0\neq \mu \in M$, the *annihilator* of $\mu$ is the set
\[
\ann(\mu) = \theset{r\in R \suchthat r\mu = 0}
.\]
Suppose that $I$ is an ideal in $R$ which is maximal with respect to the property that there exists an element $\mu \in M$ such that $I = \ann(\mu)$ for some $\mu \in M$.
In other words, $I = \ann(\mu)$ but there does not exist $\nu\in M$ with $J = \ann(\nu) \subsetneq R$ such that $I\subsetneq J$.

Prove that $I$ is a prime ideal.

## Spring 2013 #2 $\work$

a.
Define a *Euclidean domain*.

b.
Define a *unique factorization domain*.

c.
Is a Euclidean domain an UFD? 
Give either a proof or a counterexample with justification.

d.
Is a UFD a Euclidean domain?
Give either a proof or a counterexample with justification.

## Spring 2021 #5 $\done$

:::{.problem title="Spring 2021"}
Suppose that $f(x) \in (\ZZ/n\ZZ)[x]$ is a zero divisor.
Show that there is a nonzero $a\in \ZZ/n\ZZ$ with $af(x) = 0$.
:::

:::{.solution}
\envlist

- Write $f(x) = \sum_{k=0}^n a_k x^k$, and supposing it's a zero divisor choose $g(x) = \sum_{k=0}^m b_k x^k$ of minimal degree so that $g\neq 0, b_m\neq 0$, and $f(x)g(x) = 0$.
- The claim is that the top coefficient $b_m$ will suffice.
- Write the product:
\[
0 = f(x)g(x) 
= (a_0 + \cdots + a_{n-1}x^{n-1} + a_n x^n)
(b_0 + \cdots + b_{m-1}x^{m-1} + b_m x^m)
.\]
- Equating coefficients, the coefficient for $x^{m+n}$ must be zero, so (**importantly**) $a_n b_m = 0$.
  - Since $a_n b_m=0$, consider $a_ng(x)$.
    This has degree $d_1 \leq m-1$ but satisfies $a_ng(x)f(x) = a_n(g(x)f(x)) = 0$, so by minimality $a_ng(x) = 0$.
  - This forces $a_n b_0 = \cdots = a_n b_{m-1} = 0$, so $a_n$ annihilates all of the $b_k$.
- Now consider the coefficient of $x^{m+n-1}$, given by $a_{n-1}b_m + a_{n}b_{m-1}$.
  - The second term $a_n b_{m-1}=0$ since $a_n$ annihilates all $b_k$, so (**importantly**) $a_{n-1} b_m = 0$.
  - Considering now $a_{n-1}g(x)$:
    - The same argument shows this has degree $d_2 \leq m-1$ but $a_{n-1}g(x)f(x) = 0$, so $a_{n-1}g(x) = 0$.
    - So $a_{n-1}$ annihilates all $b_k$, and allowing this process to continue inductively.
- For good measure, the coefficient of $x^{m+n-2}$ is $a_{n-2}b_m + a_{n-1}b_{m-1} + a_{n}b_{m-2}$.
  - Note that $a_n, a_{n-1}$ annihilate all $b_k$, so (**importantly**) $a_{n-2} b_m=0$, and so on.

- Thus $a_k b_m = 0$ for all $0\leq k \leq n$, and by linearity and commutativity, we have
\[
b_m f(x) = b_m \sum_{k=0}^n a_k x^k = \sum_{k=0}^n (b_m a_k) x^k = 0
.\]

:::



## Spring 2021 #6

a. 
Carefully state the definition of **Noetherian** for a commutative ring $R$.

b. 
Let $R$ be a subset of $\ZZ[x]$ consisting of all polynomials 
\[
f(x) = a_ 0 + a_1 x + a_2 x^2 + \cdots + a_nx^n
\]
such that $a_k$ is even for $1\leq k \leq n$.
Show that $R$ is a subring of $\ZZ[x]$.

c. Show that $R$ is not Noetherian.

  > *Hint: consider the ideal generated by \( \ts{ 2x^k \st 1\leq k \in \ZZ } \).*



:::{.solution}

- A ring is **Noetherian** iff $R$ satisfies the ascending chain condition: every chain of ideals $A_1 \subseteq A_2 \subseteq \cdots$ eventually stabilizes, so $A_m \subseteq A_{m+1} = A_{m+2} = \cdots$.

- That $R$ is a subring of $\ZZ[x]$:
  - $(R, +)$ is an abelian subgroup: note that $f(x) + g(x) = \sum a_k x^k + \sum b_k x^k = \sum (a_k + b_k) x^k$, so if $a_k, b_k$ are even then $a_k + b_k$ is even.
    It's closed under inverses, since $a_k$ is even iff $-a_k$ is even, and contains zero.
  - $(R, \cdot)$ is a submonoid: $f(x) g(x) = \sum_{n=1}^N \qty{ \sum_{k=1}^n a_k b_{n-k}} x^k$ where without loss of generality, $\deg f = \deg g = n$ by setting coefficients to zero.
    Then sums and products of even integers are even, so $fg \in R$.

- That $R$ is not Noetherian: it suffices to show that $R$ contains an ideal that is not finitely generated.
- The claim is that setting $S \da \ts{2x^k}_{k\in \ZZ_{\geq 1}}$ and taking 
\[
I \da \gens{S} = \sum_{k\in \ZZ_{\geq 1}} R\cdot 2x^k \da \ts{ \sum_{i=1}^m r_k(x) 2x^k \st r_k(x) \in 2\ZZ[x], m\in \ZZ_{\geq 0}}
\]
  yields an ideal that is not finitely generated.

- Suppose toward a contradiction that $\ts{g_1, g_2, \cdots, g_M}$ were a finite generating set, where each $g_i \in I$.

\todo[inline]{???}


:::

