# Integrals and Cauchy's Theorem

> Some interesting problems: 3, 4, 9, 10.

## 1

Suppose $f, g: [0, 1] \to \RR$ where $f$ is Riemann integrable and for $x, y\in [0, 1]$,
\begin{align*}
\abs{g(x) - g(y)} \leq \abs{f(x) - f(y)}
.\end{align*}

Prove that $g$ is Riemann integrable.

## 2

State and prove Green's Theorem for rectangles.

Then use it to prove Cauchy's Theory for functions that are analytic in a rectangle.


## 3

Suppose $\theset{f_n}_{n\in \NN}$ is a sequence of analytic functions on $\DD^\circ \definedas \theset{z\in \CC \suchthat \abs{z} < 1}$.

Show that if $f_n\to g$ for some $g: \DD^\circ \to \CC$ uniformly on every compact $K\subset \DD^\circ$, then $g$ is analytic on $\DD^\circ$.


## 4

Suppose $\theset{f_n}_{n\in \NN}$ is a sequence of entire functions where

- $f_n \to g$ pointwise for some $g:\CC\to\CC$.
- On every line segment in $\CC$, $f_n \to g$ uniformly.

Show that 

- $g$ is entire, and
- $f_n\to g$ uniformly on every compact subset of $\CC$.


## 5

Prove that there is no sequence of polynomials that uniformly converge to $f(z) = {1\over z}$ on $S^1$.


## 6

Suppose that $f: \RR\to\RR$ is a continuous function that vanishes outside of some finite interval.
For each $z\in \CC$, define
\begin{align*}
g(z) = \int_{-\infty}^\infty f(t) e^{-izt} \,dt
.\end{align*}

Show that $g$ is entire.


## 7

Suppose $f: \CC\to \CC$ is entire and
\begin{align*}
\abs{f(z)} \leq \abs{z}^{1\over 2} \quad\text{ when } \abs{z} > 10
.\end{align*}

Prove that $f$ is constant.

## 8

Let $\gamma$ be a smooth curve joining two distinct points $a, b\in \CC$.

Prove that the function
\begin{align*}
f(z) \definedas \int_\gamma {g(w) \over w-z} \,dw
\end{align*}
is analytic in $\CC\setminus\gamma$.

## 9
Suppose that $f: \CC\to\CC$ is continuous everywhere and analytic on $\CC\setminus \RR$ and prove that $f$ is entire.

## 10
Prove Liouville's theorem: suppose $f:\CC\to\CC$ is entire and bounded. 
Use Cauchy's formula to prove that $f'\equiv 0$ and hence $f$ is constant.

