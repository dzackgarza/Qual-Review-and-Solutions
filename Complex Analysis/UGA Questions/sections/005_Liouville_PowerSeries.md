# Liouville's Theorem, Power Series (8155e)

## 1

Suppose $f$ is analytic on a region $\Omega$ such that $\DD \subseteq \Omega \subseteq \CC$ and $f(z) = \sum_{n=0}^\infty a_n z^n$ is a power series with radius of convergence exactly 1.

### a
Give an example of such an $f$ that converges at every point of $S^1$.

### b 
Given an example of such an $f$ which is analytic at $1$ but $\sum_{n=0}^\infty a_n$ diverges.

c. Prove that $f$ can not be analytic at *every* point of $S^1$.

## 2

Suppose $f$ is entire and has Taylor series $\sum a_n z^n$ about 0.

a. Express $a_n$ as a contour integral along the circle $\abs{z} = R$.

b. Apply (a) to show that the above Taylor series converges uniformly on every bounded subset of $\CC$.

c. Determine those functions $f$ for which the above Taylor series converges uniformly on all of $\CC$.


## 3

Suppose $D$ is a domain and $f, g$ are analytic on $D$.

Prove that if $fg = 0$ on $D$, then either $f \equiv 0$ or $g\equiv 0$ on $D$.


## 4

Suppose $f$ is analytic on $\DD^\circ$.
Determine with proof which of the following are possible:

a. $f\qty{1\over n} = (-1)^n$ for each $n>1$.

b. $f\qty{1\over n} = e^{-n}$ for each even integer $n>1$ while $f\qty{1\over n} = 0$ for each odd integer $n>1$.

c. $f\qty{1\over n^2} = {1\over n}$ for each integer $n>1$.

d. $f\qty{1\over n} = {n-2 \over n-1}$ for each integer $n>1$.


## 5

Prove the Fundamental Theorem of Algebra (using complex analysis).


## 6
Find all entire functions that satisfy
\begin{align*}
\abs{f(z)} \geq \abs{z} \quad \forall z\in \CC
.\end{align*}
Prove this list is complete.

## 7
Suppose $\sum_{n=0}^\infty a_n z^n$ converges for some $z_0 \neq 0$.

a. Prove that the series converges absolutely for each $z$ with $\abs z < \abs z_0$.

b. Suppose $0 < r < \abs{z_0}$ and show that the series converges uniformly on $\abs{z} \leq r$.

## 8

Suppose $f$ is entire and suppose that for some integer $n\geq 1$,
\begin{align*}
\lim_{z\to \infty} {f(z) \over z^n} = 0
.\end{align*}

Prove that $f$ is a polynomial of degree at most $n-1$.


## 9

Find all entire functions satisfying
\begin{align*}
\abs{f(z)} \leq \abs{z}^{1\over 2} \quad\text{ for } \abs{z} > 10
.\end{align*}


## 10

Prove that the following series converges uniformly on the set $\theset{z \suchthat \Im(z) < \ln 2}$:
\begin{align*}
\sum_{n=1}^\infty {\sin(nz) \over 2^n}
.\end{align*}

