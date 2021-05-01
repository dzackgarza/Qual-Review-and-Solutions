---
date: 2020-01-27
tags: 
  - Unfiled
---

[../../Talks Index](../../Talks%20Index.md)

Tags: #zeta_functions #L_functions #number_theory #algebraic_geometry


Recall that the Riemann-Zeta function has a product expansion


\begin{align*}
\zeta(s) = \sum n^{-s} = \prod_{p\in P} (1-p^{-s})\inv
\end{align*}

where the product is taken over all primes $P$.

Let $X = V(\theset{f_i})\definedas V(f)$ be the vanishing locus of a family of polynomials in $F = \FF_q[x_1, \cdots, x_n]$ for some prime power $q$.

Let $N_m = \abs{\theset{ \vector x \in X(\FF_q) \suchthat f_i(\vector x) = 0 }} = \abs{V(f)} \subset F$, the number of $\FF_q$ points, or equivalently just the size of this variety.

Then the Hasse-Weil Zeta function is defined as


\begin{align*}
\zeta_X(t) = \exp{\displaystyle\sum_{m\geq 1} \frac {N_m} m  t^m}
\end{align*}

We immediately make a change of variables and send $t\to q^{-s}$ to obtain

\begin{align*}
\zeta_X(s) = \exp{\sum_{m\geq 1} \frac {N_m} m \qty{q^{-s}}^m }
.\end{align*}

> Why? Turns the zeta function into a Dirichlet series in $s$.
> Yields $\abs{t} = q^{-\Re(s)}$.
> Defined for $\abs{t} < \frac 1 q$ in $\CC$, extended to all of $\CC$ as a rational function in $x$.
> Converts "All zeros of $\zeta_X$ have absolute value $\frac{1}{\sqrt q}$" to "All zeros of $\zeta_X$ have real part $\frac 1 2$".

[Explanation of why exponential appears](https://mathoverflow.net/questions/325186/motivation-for-zeta-function-of-an-algebraic-variety)

Rough explanation: Take a bad first approximation and then correct.
Let $X$ be a fixed variety, for $p\in X$ define $\norm{p}_X = q^n$ where $n$ is the $n$ occurring in the minimal field of definition of $p$, which is $\FF_{q^n}$. 

Attempt to define
\begin{align*}
\zeta_{X, q}(s) = \prod_{p\in X} \frac{1}{1-\norm{p}_X^{-s}}
.\end{align*}

Note that $-\log(x+1) = \sum_{n\geq 1} \frac{x^n}{n}$.

Now fix one $p\in X$ and consider the factor it contributes, and take its logarithm:

\begin{align*}
\log\qty{\frac{1}{1-\norm{p}_X^{-s}}} 
&= - \log(1-\norm{p}_X^{-s}) \\
&=  - \log(-\norm{p}_X^{-s} + 1) \\
&= \sum_{j\geq 1} \frac{\norm{p}_X^{-js}}{k} \\
&= \sum_{j\geq 1} \frac{q^{-nks}}{k} \\
&= \sum_{j\geq 1} \frac{n}{nk}(q^{-s})^{nk} \\
(m=nk)\quad &= \sum_{j\geq 1} \frac{n}{m}(q^{-s})^{m}
,\end{align*}

so we see this single point contributes $n$ to $N_m$, when instead we'd like it to contribute exactly 1.

Fix:
If $p$ is minimally defined over $\FF_{q^n}$, consider its Galois orbit (taking automorphisms of $\FF_{q^n}$).
There are exactly $n$ points in the orbit of $p$ -- namely, the conjugates of $p$ -- so if we redefine

\begin{align*}
\zeta_{X, q}(s) = \prod_{\text{One } p \text{ in each Galois orbit}} \frac{1}{1-\norm{p}_{X}^{-s} }
.\end{align*}

Then the above argument shows that each orbit now contributes $n$, and each orbit is of size $n$, so the contribution now accurately reflects the number of points.

# Examples

1: $f(x) = x$ over $\FF_q$.

Define $X_q = V(f)$, then this has exactly $q  points over $\FF_q^{n}$ point for every $n$, so $N_n = 1$ and

\begin{align*}
\zeta_{X_q}(s) = \exp{\sum_{n\geq 1} \frac 1 n  (p^{-sn})} &= e^{-\log(1 - p^{-s})}= (1-p^{-s})\inv
.\end{align*}

> Note that the usual $\zeta_s = \prod_{p\text{ prime}} \zeta_{X_p}(s)$, i.e. Riemann Zeta is a product of Hasse-Weil zetas over all primes.

2. $V = \CP^1$ the projective line.

Here 
\begin{align*}
\zeta_V(s) = \frac{1}{(1-q^{-s})(1-q^{1-s})}
.\end{align*}

Corresponds to Riemann sphere, can check Betti numbers.

3. $V = \CP^n$:

\begin{align*}
\zeta_V(s) = \prod_{j=0}^n \frac{1}{1-q^{j-s}}
.\end{align*}

4. An elliptic curve:

$N_m$ is given by $1 - \alpha^m - \beta^m + q^m$ where $\alpha = \bar\beta$ are complex conjugates with absolute value $\sqrt{q}$.

\begin{align*}
\zeta(E, s)=\frac{\left(1-\alpha q^{-s}\right)\left(1-\beta q^{-s}\right)}{\left(1-q^{-s}\right)\left(1-q^{1-s}\right)}
.\end{align*}
