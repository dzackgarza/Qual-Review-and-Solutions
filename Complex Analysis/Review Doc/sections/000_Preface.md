# Useful Techniques

## Notation

- $S \definedas \theset{x + iy \suchthat x\in \RR,\, 0<y<\pi}$.
- $\DD$ the disc
- $\HH$ the upper half plane
- $X_{1\over 2}$: a "half" version of $X$.


:::{.remark title="Showing a function is constant"}
If you want to show that a function $f$ is constant, try one of the following:

- Write $f = u + iv$ and use Cauchy-Riemann to show $u_x, u_y = 0$, etc.
- Show that $f$ is entire and bounded.

If you additionally want to show $f$ is zero, try one of these:

- Show $f$ is entire, bounded, and $\lim_{z\to\infty} f(z) = 0$.
:::

## Greatest Hits

Things to know well:

- Estimates for derivatives, mean value theorem
- \cref[CauchyTheorem]{Cauchy's Theorem}
- \cref[CauchyIntegral]{Cauchy's Integral Formula}
- \cref[CauchyInequality]{Cauchy's Inequality}
- \cref[Morera]{Morera's Theorem}
- \cref[SchwarzReflection]{The Schwarz Reflection Principle}
- \cref[MaximumModulus]{Maximum Modulus Principle}
- \cref[SchwarzLemma]{The Schwarz Lemma}
- \cref[Liouville]{Liouville's Theorem}
- \cref[Casorati]{Casorati-Weierstrass Theorem}
- \cref[Rouche]{Rouché's Theorem}
- Properties of linear fractional transformations
- Automorphisms of $\DD, \CC, \CP^1$.

## Basic but Useful Facts

:::{.fact title="Some useful facts about basic complex algebra"}
\envlist

- $\Re(z) = \frac 1 2 (z + \bar z)$ and $\Im(z) = \frac{1}{2i}(z - \bar z)$.
- $z\bar z = \abs{z}^2$
- Exponential forms of cosine and sine:
  - $\cos(\theta) = \frac 1 2 \qty{e^{i\theta} + e^{-i\theta}}$
  - $\sin(\theta) = \frac{1}{2i}\qty{e^{i\theta} - e^{-i\theta}}$.
- $\Arg(z/w) = \Arg(z) - \Arg(w)$.
\[
dz &= dx + i~dy \\
d\bar z &= dx - i~dy \\
f_z &= f_x = i\inv f_y \\
\int_{0}^{2 \pi} e^{i \ell x} d x
&=\left\{\begin{array}{ll}{2 \pi} & {(\ell=0)} \\ {0} & {(\ell \neq 0)}\end{array}\right.
.\]

:::

:::{.fact title="Some useful series"}
\[
\sum_{k=1}^{n} k &=\frac{n(n+1)}{2} \\
\sum_{k=1}^{n} k^{2} &=\frac{n(n+1)(2 n+1)}{6} \\
\sum_{k=1}^{n} k^{3} &=\frac{n^{2}(n+1)^{2}}{4}  \\
\log(z) &= \sum_{j=0}^\infty (-1)^j \frac{\qty{z-a}^j}{j}
\dd{}{z} \sum_{j=0}^\infty a_j z^j &= \sum_{j=0}^\infty a_{j+1}z^j
\]
:::


