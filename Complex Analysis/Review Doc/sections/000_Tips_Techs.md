> A great deal of content borrowed from the following: <https://web.stanford.edu/~chriseur/notes_pdf/Eur_ComplexAnalysis_Notes.pdf>

# Useful Techniques

## Notation
| Notation                                                     | Definition                                             |
|--------------------------------------------------------------|--------------------------------------------------------|
| $\DD \da \ts{z \st \abs{z} \leq 1}$                          | The unit disc                                          |
| $\HH \da \ts{x+iy \st y > 0}$                                | The upper half-plane                                   |
| $X_{1\over 2}$                                               | A "half version of $X$", see examples                  |
| $\HH_{1\over 2}$                                             | The first quadrant                                     |
| $\DD_{1\over 2}$                                             | The portion of the first quadrant inside the unit disc |
| $S \definedas \theset{x + iy \suchthat x\in \RR,\, 0<y<\pi}$ | The horizontal strip                                   |
|                                                              |                                                        |
|                                                              |                                                        |

## Greatest Hits

Things to know well:

- Estimates for derivatives, mean value theorem
- \cref[CauchyTheorem]{Cauchy's Theorem}
- \cref[CauchyIntegral]{Cauchy's Integral Formula}
- \cref[CauchyInequality]{Cauchy's Inequality}

- \cref[Morera]{Morera's Theorem}
- \cref[Liouville]{Liouville's Theorem}

- \cref[MaximumModulus]{Maximum Modulus Principle}
- \cref[Rouche]{Rouché's Theorem}

- \cref[SchwarzReflection]{The Schwarz Reflection Principle}
- \cref[SchwarzLemma]{The Schwarz Lemma}
- \cref[Casorati]{Casorati-Weierstrass Theorem}
- Properties of linear fractional transformations
- Automorphisms of $\DD, \CC, \CP^1$.

## Common Tricks

- Virtually any time: consider $1/f(z)$ and $f(1/z)$.

:::{.remark title="Showing a function is constant"}
If you want to show that a function $f$ is constant, try one of the following:

- Write $f = u + iv$ and use Cauchy-Riemann to show $u_x, u_y = 0$, etc.
- Show that $f$ is entire and bounded.
  - If you additionally want to show $f$ is zero, show $\lim_{z\to\infty} f(z) = 0$.
:::

## Basic but Useful Facts

:::{.fact title="Some useful facts about basic complex algebra"}
\envlist

- $z\bar z = \abs{z}^2$
\[
\Re(z) = { z + \bar z \over 2} && && 
\Im(z) = {z - \bar{z} \over 2i}
.\]

- $\Arg(z/w) = \Arg(z) - \Arg(w)$.
- Exponential forms of cosine and sine, where it's sometimes useful to set $w\da e^{iz}$:
\[
\cos(z) 
&= \frac 1 2 \qty{e^{iz} + e^{-iz}} = {1\over 2}(w+ w\inv)\\
\sin(z) 
&= \frac{1}{2i}\qty{e^{iz} - e^{-iz}} = {1\over 2i}(w-w\inv)
\\ \\
\cosh(z) = \cos(iz) 
&= {1\over 2}\qty{e^z + e^{-z}} \\
\sinh(z) = \sin(iz) 
&= {1\over 2}\qty{e^z - e^{-z}} 
.\]
- Setting $w=e^z$ is useful:
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

:::{.fact title="Generalized Binomial Theorem"}
Define $(n)_k$ to be the falling factorial 
\[
\prod_{j=0}^{k-1} (n-k) = n(n-1)\cdots(n-k+1)
\]
and set ${n\choose k} \da (n)_k/k!$, then
\[
(x+y)^n = \sum_{k\geq 0} {n\choose k} x^{k}y^{n-k}
.\]
:::

:::{.fact title="Some useful series"}
\[
\sum_{k=1}^{n} k &=\frac{n(n+1)}{2} \\
\sum_{k=1}^{n} k^{2} &=\frac{n(n+1)(2 n+1)}{6} \\
\sum_{k=1}^{n} k^{3} &=\frac{n^{2}(n+1)^{2}}{4}  \\
\log(1-x) 
  &= \sum_{k \geq 0} {z^k\over k} \quad \abs{z} < 1 \\
\dd{}{z} \sum_{k=0}^\infty a_k z^k 
  &= \sum_{k=0}^\infty a_{k+1}z^k \\
\sqrt{1+x} = (1+x)^{1/2} 
  &= 1 + (1/2)x + {(1/2)(-1/2) \over 2!}x^2 + {(1/2)(-1/2)(-3/2) \over 3!}x^3 + \cdots \\
  &= 1 + {1\over 2} x - {1\over 8}x^2 + {1\over 16}x^3 - \cdots
\]
:::

:::{.fact}
Useful trick for expanding square roots:
\[
\sqrt{z} = \sqrt{z_0 + z - z_0} = \sqrt{z_0 \qty{ 1 + {z-z_0 \over z} }} = \sqrt{z_0} \sqrt{1+u},\quad u\da {z-z_0 \over z} \\
\implies \sqrt{z} = \sqrt{z_0} \sum_{k\geq 0} {1/2 \choose k} \qty{z- z_0 \over z}^k
.\]

:::

