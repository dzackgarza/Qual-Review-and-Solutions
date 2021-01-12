# Useful Techniques

## Notation
| Notation                                                     | Definition                                             |
|--------------------------------------------------------------|--------------------------------------------------------|
| $\DD \da \ts{z \st \abs{z} \leq 1}$                          | The unit disc                                          |
| $\HH \da \ts{x+iy \st y > 0}$                                | The upper half-plane                                   |
| $X_{1\over 2}$                                               | A "half version of $X$", see examples                  |
| $\HH_{1\over 2}$                                             | The first quadrant                                     |
| $\DD_{1\over 2}$                                             | The portion of the first quadrant inside the unit disc |
| $S \definedas \theset{x + iy \suchthat x\in \RR,\, 0<y<\pi}$ | The horizonta strip |
|                                                              |                                                        |
|                                                              |                                                        |
|                                                              |                                                        |
|                                                              |                                                        |
|                                                              |                                                        |
|                                                              |                                                        |
|                                                              |                                                        |

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

- $z\bar z = \abs{z}^2$
\[
\Re(z) = { z + \bar z \over 2} && && 
\Im(z) = {z - \bar{z} \over 2i}
.\]

- $\Arg(z/w) = \Arg(z) - \Arg(w)$.
- Exponential forms of cosine and sine:
\[
\cos(\theta) = \frac 1 2 \qty{e^{i\theta} + e^{-i\theta}} && &&
\sin(\theta) = \frac{1}{2i}\qty{e^{i\theta} - e^{-i\theta}}
.\]
- Various differentials:
\[
dz &= dx + i~dy \\
d\bar z &= dx - i~dy \\ \\
f_z &= f_x = f_y / i
.\]
- Integral of a complex exponential:
\[
\int_{0}^{2 \pi} e^{i \ell x} d x
&=\left\{\begin{array}{ll}
{2 \pi} & {\ell=0} \\ 
{0} & \text{else}
\end{array}\right.
.\]


:::

:::{.fact title="Some useful series"}
\[
\sum_{k=1}^{n} k &=\frac{n(n+1)}{2} \\
\sum_{k=1}^{n} k^{2} &=\frac{n(n+1)(2 n+1)}{6} \\
\sum_{k=1}^{n} k^{3} &=\frac{n^{2}(n+1)^{2}}{4}  \\
\log(z) &= \sum_{n=0}^\infty { (-1)^n \over n} \qty{z-a}^n \\
\dd{}{z} \sum_{j=0}^\infty a_j z^j &= \sum_{j=0}^\infty a_{j+1}z^j
\]
:::


