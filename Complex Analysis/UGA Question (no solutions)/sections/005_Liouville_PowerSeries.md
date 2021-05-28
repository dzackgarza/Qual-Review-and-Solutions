# Liouville's Theorem, Power Series (8155e)

## 1 $\done$

Suppose $f$ is analytic on a region $\Omega$ such that $\DD \subseteq \Omega \subseteq \CC$ and $f(z) = \sum_{n=0}^\infty a_n z^n$ is a power series with radius of convergence exactly 1.

a. $\done$
Give an example of such an $f$ that converges at every point of $S^1$.

b.  $\work$
Give an example of such an $f$ which is analytic at $1$ but $\sum_{n=0}^\infty a_n$ diverges.

c.  $\work$
Prove that $f$ can not be analytic at *every* point of $S^1$.

\todo[inline]{Missing part (c)}
:::{.solution}
\hfill
:::{.concept}
\hfill

:::

a.  $\done$

- Take $\sum {z^n \over n^2}$
- Then \[\abs{z}\leq 1 \implies \abs{z^n\over n^2} \leq {1\over n^2}\] which is summable
- So the series converges for $\abs{z}\leq 1$.

b. $\work$
- Take $\sum {z^n \over n}$; 
- Then $z=1$ yields the harmonic series, which diverges.

- For $z\in S^1\setminus\theset{1}$, we have $z = e^{2\pi it}$ for $0<t<2\pi$. 
- So fix $t$.

- Toward applying the Dirichlet test, set $a_n = 1/n, b_n = z^n$.

- Then for all $N$,
\[
\abs{\sum_{n=1}^N b_n}
= \abs{\sum_{n=1}^N b_n}
= \abs{\sum_{n=1}^N z^n}
= \abs{  {z-z^{N+1} \over \abs{1 - z}} } 
\leq {2 \over 1-z} < \infty
.\]

- Thus $\sum a_n b_n < \infty$ and $\sum z^n/n$ converges.

c. ?

:::

## 2 $\work$

Suppose $f$ is entire and has Taylor series $\sum a_n z^n$ about 0.

a.  $\work$
Express $a_n$ as a contour integral along the circle $\abs{z} = R$.

b. $\work$
Apply (a) to show that the above Taylor series converges uniformly on every bounded subset of $\CC$.

c. $\work$
Determine those functions $f$ for which the above Taylor series converges uniformly on all of $\CC$.




## 3 $\work$

Suppose $D$ is a domain and $f, g$ are analytic on $D$.

Prove that if $fg = 0$ on $D$, then either $f \equiv 0$ or $g\equiv 0$ on $D$.


## 4 $\work$

Suppose $f$ is analytic on $\DD^\circ$.
Determine with proof which of the following are possible:

a. $f\qty{1\over n} = (-1)^n$ for each $n>1$.

b. $f\qty{1\over n} = e^{-n}$ for each even integer $n>1$ while $f\qty{1\over n} = 0$ for each odd integer $n>1$.

c. $f\qty{1\over n^2} = {1\over n}$ for each integer $n>1$.

d. $f\qty{1\over n} = {n-2 \over n-1}$ for each integer $n>1$.


## 5 $\done$

Prove the Fundamental Theorem of Algebra (using complex analysis).

:::{.solution}
\hfill
:::{.concept}
\hfill

:::
- Strategy: By contradiction with Liouville's Theorem
- Suppose $p$ is non-constant and has no roots.
- Claim: $1/p(z)$ is a bounded holomorphic function on $\CC$.
  - Holomorphic: clear? Since $p$ has no roots.
  - Bounded: for $z\neq 0$, write
    \begin{align*}
    \frac{P(z)}{z^{n}}=a_{n}+\left(\frac{a_{n-1}}{z}+\cdots+\frac{a_{0}}{z^{n}}\right)
    .\end{align*}

  - The term in parentheses goes to 0 as $\abs{z}\to \infty$
  - Thus there exists an $R>0$ such that
    \begin{align*}
    \abs{z} > R \implies \abs{P(z) \over z^n} \geq c \definedas {\abs{a_n} \over 2}
    .\end{align*}

  - So $p$ is bounded below when $\abs{z} > R$
  - Since $p$ is continuous and has no roots in $\abs{z} \leq R$, it is bounded below when $\abs{z} \leq R$.
  - Thus $p$ is bounded below on $\CC$ and thus $1/p$ is bounded above on $\CC$.
- By Liouville's theorem, $1/p$ is constant and thus $p$ is constant, a contradiction.
:::



## 6 $\done$
Find all entire functions that satisfy
\[
\abs{f(z)} \geq \abs{z} \quad \forall z\in \CC
.\]
Prove this list is complete.

:::{.solution}
\hfill
:::{.concept}
\hfill

:::
- Suppose $f$ is entire and define $g(z) \definedas {z \over f(z)}$.
- By the inequality, $\abs{g(z)} \leq 1$, so $g$ is bounded.
- $g$ potentially has singularities at the zeros $Z_f \definedas f\inv(0)$, but since $f$ is entire, $g$ is holomorphic on $\CC\setminus Z_f$.
- Claim: $Z_f = \theset{0}$.
  - If $f(z) = 0$, then $\abs{z} \leq \abs{f(z)} = 0$ which forces $z=0$.
- We can now apply Riemann's removable singularity theorem:
  - Check $g$ is bounded on some open subset $D\smz$, clear since it's bounded everywhere
  - Check $g$ is holomorphic on $D\smz$, clear since the only singularity of $g$ is $z=0$.
- By Riemann's removable singularity theorem, the singularity $z = 0$ is removable and $g$ has an extension to an entire function $\tilde g$.
- By continuity, we have $\abs{\tilde g(z)} \leq 1$ on all of $\CC$
  - If not, then $\abs{\tilde g(0)} = 1+\eps > 1$, but then there would be a domain $\Omega \subseteq \CC\smz$ such that $1 < \abs{\tilde g(z)} \leq 1 +\eps$ on $\Omega$, a contradiction.
- By Liouville, $\tilde g$ is constant, so $\tilde g(z) = c_0$ with $\abs {c_0} \leq 1$
- Thus $f(z) = c_0\inv z \definedas cz$ where $\abs{c}\geq 1$

Thus all such functions are of the form $f(z) = cz$ for some $c\in \CC$ with $\abs{c}\geq 1$.
:::


## 7 $\work$
Suppose $\sum_{n=0}^\infty a_n z^n$ converges for some $z_0 \neq 0$.

a.  $\work$
Prove that the series converges absolutely for each $z$ with $\abs z < \abs z_0$.

b.  $\work$
Suppose $0 < r < \abs{z_0}$ and show that the series converges uniformly on $\abs{z} \leq r$.

## 8 $\work$

Suppose $f$ is entire and suppose that for some integer $n\geq 1$,
\[
\lim_{z\to \infty} {f(z) \over z^n} = 0
.\]

Prove that $f$ is a polynomial of degree at most $n-1$.


## 9 $\work$

Find all entire functions satisfying
\[
\abs{f(z)} \leq \abs{z}^{1\over 2} \quad\text{ for } \abs{z} > 10
.\]


## 10 $\work$

Prove that the following series converges uniformly on the set $\theset{z \suchthat \Im(z) < \ln 2}$:
\[
\sum_{n=1}^\infty {\sin(nz) \over 2^n}
.\]


# Extra


## Tie's Questions
Let $f(z)$ be entire and assume values of $f(z)$ lie outside a
*bounded* open set $\Omega$. Show without using Picard's theorems
that $f(z)$ is a constant.

Let $f(z)$ be entire and assume values of $f(z)$ lie outside a *bounded* open set $\Omega$. 

Show without using Picard's theorems that $f(z)$ is a constant.


## Tie's Questions

1. 
Assume $\displaystyle f(z) = \sum_{n=0}^\infty c_n z^n$ converges in $|z| < R$. 

Show that for $r <R$,
$$
\frac{1}{2 \pi} \int_0^{2 \pi} |f(r e^{i \theta})|^2 d \theta = \sum_{n=0}^\infty |c_n|^2 r^{2n}
.$$

2.
Deduce Liouville's theorem from (1).

### Tie's Extra Questions: Fall 2009
Suppose $f$ is entire and there exist $A, R >0$ and natural number
$N$ such that $$|f(z)| \geq A |z|^N\ \text{for}\ |z| \geq R.$$ Show
that

1. $f$ is a polynomial and
2. the degree of $f$ is at least $N$.

### Tie's Extra Questions: Fall 2009

Let $f(z)$ be entire and assume values of $f(z)$ lie outside a *bounded*
open set $\Omega$. Show without using Picard's theorems that $f(z)$ is a
constant.

### Tie's Extra Questions: Fall 2009

Let $f(z)$ be entire and assume that $f(z) \leq M |z|^2$ outside some
disk for some constant $M$. Show that $f(z)$ is a polynomial in $z$ of
degree $\leq 2$.

### Spring 20202 HW 2 #  4
Without using Cauchy's integral formula, show that if $\abs{a} < r < \abs{b}$, then
\[
\int_{\gamma} \frac{d z}{(z-\alpha)(z-\beta)}=\frac{2 \pi i}{\alpha-\beta}
\]
where $\gamma$ denotes the circle centered at the origin of radius $r$ with positive orientation.

> Hint: take a Laurent expansion.

### Spring 20202 HW 3 #  1

Prove that if $f$ has two Laurent series expansions,
\[
f(z) = \sum c_n(z-a)^n \quad\text{and}\quad f(z) = \sum c_n'(z-a)^n
\]
then $c_n = c_n'$.

### Spring 20202 HW 3 #  2

Find Laurent series expansions of
\[
\frac{1}{1-z^2} + \frac{1}{3-z}
\]
How many such expansions are there? In what domains are each valid?

### Spring 20202 HW 3 #  3

Let $P, Q$ be polynomials with no common zeros. Assume $a$ is a root of
$Q$.
Find the principal part of $P/Q$ at $z=a$ in terms of $P$ and $Q$ if $a$ is (1) a simple root, and (2) a double root.

### Spring 20202 HW 3 #  5

Show that if $f$ is entire and $\lim_{z\to\infty}f(z) = \infty$, then
$f$ is a polynomial.

