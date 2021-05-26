
> A great deal of content borrowed from the following: <https://web.stanford.edu/~chriseur/notes_pdf/Eur_ComplexAnalysis_Notes.pdf>

# Useful Techniques

## Notation

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------
  Notation                                                                                                 Definition
  -------------------------------------------------------------------------------------------------------- --------------------------------------------------------
  \( {\mathbb{D}}\coloneqq\left\{{z {~\mathrel{\Big|}~}{\left\lvert {z} \right\rvert} \leq 1}\right\} \)   The unit disc

  \( {\mathbb{H}}\coloneqq\left\{{x+iy {~\mathrel{\Big|}~}y > 0}\right\} \)                                The upper half-plane

  \( X_{1\over 2} \)                                                                                       A "half version of \( X \)", see examples

  \( {\mathbb{H}}_{1\over 2} \)                                                                            The first quadrant

  \( {\mathbb{D}}_{1\over 2} \)                                                                            The portion of the first quadrant inside the unit disc

  \( S \coloneqq\left\{{x + iy {~\mathrel{\Big|}~}x\in {\mathbb{R}},\, 0<y<\pi}\right\} \)                 The horizonta strip

                                                                                                           

                                                                                                           

                                                                                                           

                                                                                                           

                                                                                                           

                                                                                                           

                                                                                                           
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------

::: {.remark title="Showing a function is constant"}
If you want to show that a function \( f \) is constant, try one of the following:

-   Write \( f = u + iv \) and use Cauchy-Riemann to show \( u_x, u_y = 0 \), etc.
-   Show that \( f \) is entire and bounded.

If you additionally want to show \( f \) is zero, try one of these:

-   Show \( f \) is entire, bounded, and \( \lim_{z\to\infty} f(z) = 0 \).
:::

## Greatest Hits

Things to know well:

-   Estimates for derivatives, mean value theorem
-   `\cref[CauchyTheorem]{Cauchy's Theorem}`{=tex}
-   `\cref[CauchyIntegral]{Cauchy's Integral Formula}`{=tex}
-   `\cref[CauchyInequality]{Cauchy's Inequality}`{=tex}
-   `\cref[Morera]{Morera's Theorem}`{=tex}
-   `\cref[SchwarzReflection]{The Schwarz Reflection Principle}`{=tex}
-   `\cref[MaximumModulus]{Maximum Modulus Principle}`{=tex}
-   `\cref[SchwarzLemma]{The Schwarz Lemma}`{=tex}
-   `\cref[Liouville]{Liouville's Theorem}`{=tex}
-   `\cref[Casorati]{Casorati-Weierstrass Theorem}`{=tex}
-   `\cref[Rouche]{Rouché's Theorem}`{=tex}
-   Properties of linear fractional transformations
-   Automorphisms of \( {\mathbb{D}}, {\mathbb{C}}, {\mathbb{CP}}^1 \).

## Basic but Useful Facts

::: {.fact title="Some useful facts about basic complex algebra"}
```{=tex}
\envlist
```
-   \( z\mkern 1.5mu\overline{\mkern-1.5muz\mkern-1.5mu}\mkern 1.5mu = {\left\lvert {z} \right\rvert}^2 \)
    \[
    \Re(z) = { z + \mkern 1.5mu\overline{\mkern-1.5muz\mkern-1.5mu}\mkern 1.5mu \over 2} && && 
    \Im(z) = {z - \mkern 1.5mu\overline{\mkern-1.5muz\mkern-1.5mu}\mkern 1.5mu \over 2i}
    .\]

-   \( \operatorname{Arg}(z/w) = \operatorname{Arg}(z) - \operatorname{Arg}(w) \).

-   Exponential forms of cosine and sine:
    \[
    \cos(\theta) = \frac 1 2 \qty{e^{i\theta} + e^{-i\theta}} && &&
    \sin(\theta) = \frac{1}{2i}\qty{e^{i\theta} - e^{-i\theta}}
    .\]

-   Various differentials:
    \[
    dz &= dx + i~dy \\
    d\mkern 1.5mu\overline{\mkern-1.5muz\mkern-1.5mu}\mkern 1.5mu &= dx - i~dy \\ \\
    f_z &= f_x = f_y / i
    .\]

-   Integral of a complex exponential:
    \[
    \int_{0}^{2 \pi} e^{i \ell x} d x
    &=\left\{\begin{array}{ll}
    {2 \pi} & {\ell=0} \\ 
    {0} & \text{else}
    \end{array}\right.
    .\]
:::

::: {.fact title="Some useful series"}
\[
\sum_{k=1}^{n} k &=\frac{n(n+1)}{2} \\
\sum_{k=1}^{n} k^{2} &=\frac{n(n+1)(2 n+1)}{6} \\
\sum_{k=1}^{n} k^{3} &=\frac{n^{2}(n+1)^{2}}{4}  \\
\log(z) &= \sum_{n=0}^\infty { (-1)^n \over n} \qty{z-a}^n \\
{\frac{\partial }{\partial z}\,} \sum_{j=0}^\infty a_j z^j &= \sum_{j=0}^\infty a_{j+1}z^j
\]
:::

## Advice

-   Consider \( 1/f(z) \) and \( f(1/z) \).

# Calculus Preliminaries

::: {.theorem title="Implicit Function Theorem"}
:::

::: {.theorem title="Inverse Function Theorem"}
:::

::: {.theorem title="Green's Theorem"}
If \( \Omega \subseteq {\mathbb{C}} \) is bounded with \( {{\partial}}\Omega \) piecewise smooth and \( f, g\in C^1(\mkern 1.5mu\overline{\mkern-1.5mu\Omega\mkern-1.5mu}\mkern 1.5mu) \), then
\[\int_{{{\partial}}\Omega} f\, dx + g\, dy = \iint_{\Omega} \qty{ {\frac{\partial g}{\partial x}\,} - {\frac{\partial f}{\partial y}\,} } \, dA.\]
:::

## Convergence

::: {.remark}
Recall that absolutely convergent implies convergent, but not conversely: \( \sum k^{-1}= \infty \) but \( \sum (-1)^k k^{-1}< \infty \). This converges because the even (odd) partial sums are monotone increasing/decreasing respectively and in \( (0, 1) \), so they converge to a finite number. Their difference converges to 0, and their common limit is the limit of the sum.
:::

::: {.proposition title="Uniform Convergence of Series"}
A series of functions \( \sum_{n=1}^\infty f_n(x) \) converges uniformly iff
\[  
\lim_{n\to \infty} {\left\lVert { \sum_{k\geq n} f_k } \right\rVert}_\infty = 0
.\]
:::

::: {.theorem title="Weierstrass $M\\dash$Test"}
If \( \left\{{f_n}\right\} \) with \( f_n: \Omega \to {\mathbb{C}} \) and there exists a sequence \( \left\{{M_n}\right\} \) with \( {\left\lVert {f_n} \right\rVert}_\infty \leq M_n \) and \( \sum_{n\in {\mathbb{N}}} M_n < \infty \), then \( f(x) \coloneqq\sum_{n\in {\mathbb{N}}} f_n(x) \) converges absolutely and uniformly on \( \Omega \).

Moreover, if the \( f_n \) are continuous, by the uniform limit theorem, \( f \) is again continuous.
:::

## Series and Sequences

::: {.remark}
Note that if a power series converges uniformly, then summing commutes with integrating or differentiating.
:::

::: {.fact}
Consider \( \sum c_k z^k \), set \( R = \lim {\left\lvert {c_{k+1} \over c_k} \right\rvert} \), and recall the **ratio test**:

-   \( R\in (0, 1) \implies \) convergence.
-   \( R\in [1, \infty] \implies \) divergence.
-   \( R=1 \) yields no information.
:::

::: {.proposition title="Radius of Convergence by the Root Test"}
For \( f(z) = \sum_{k\in {\mathbb{N}}} c_k z^k \), defining
\[
{1\over R} \coloneqq\limsup_{k} {\left\lvert {a_k} \right\rvert}^{1\over k}
,\]
then \( f \) converges absolutely and uniformly for \( D_R \coloneqq{\left\lvert {z} \right\rvert} < R \) and diverges for \( {\left\lvert {z} \right\rvert} > R \). Moreover \( f \) is holomorphic in \( D_R \), can be differentiated term-by-term, and \( f' = \sum_{k\in {\mathbb{N}}} n c_k z^k \).
:::

::: {.fact}
Recall the **\( p{\hbox{-}} \)test**:
\[
\sum n^{-p} < \infty \iff p \in (1, \infty)
.\]
:::

::: {.fact}
The product of two sequences is given by the Cauchy product
\[
\sum a_kz^k \cdot \sum b_k z^k = \sum c_k z^k,\quad c_k \coloneqq\sum_{j\leq k} a_k b_{k-j}
.\]
:::

::: {.fact}
Recall how to carry out polynomial long division:

```{=tex}
\todo[inline]{Polynomial long division}
```
:::

::: {.fact title="Partial Fraction Decomposition"}
```{=tex}
\envlist
```
-   For every root \( r_i \) of multiplicity 1, include a term \( A/(x-r_i) \).
-   For any factors \( g(x) \) of multiplicity \( k \), include terms \( A_1/g(x), A_2/g(x)^2, \cdots, A_k / g(x)^k \).
-   For irreducible quadratic factors \( h_i(x) \), include terms of the form \( {Ax+B \over h_i(x)} \).
:::

::: {.fact title="Generalized Binomial Theorem"}
Define \( (n)_k \) to be the falling factorial \( \prod_{j=0}^{k-1} (n-k) = n(n-1)\cdots(n-k+1) \) and set \( {n\choose k} \coloneqq(n)_k/k! \), then
\[
(x+y)^n = \sum_{k\geq 0} {n\choose k} x^{k}y^{n-k}
.\]
:::

::: {.fact title="Some useful series"}
\[
\sqrt{1+x} = (1+x)^{1/2} = 1 + {1\over 2} x - {1\over 8}x^2 + {1\over 16}x^3 - \cdots
.\]
:::

::: {.fact}
Useful trick for expanding square roots:
\[
\sqrt{z} = \sqrt{z_0 + z - z_0} = \sqrt{z_0 \qty{ 1 + {z-z_0 \over z} }} = \sqrt{z_0} \sqrt{1+u},\quad u\coloneqq{z-z_0 \over z} \\
\implies \sqrt{z} = \sqrt{z_0} \sum_{k\geq 0} {1/2 \choose k} \qty{z- z_0 \over z}^k
.\]
:::

## Exercises

::: {.exercise title="?"}
Find the radius of convergences for the power series expansion of \( \sqrt{z} \) about \( z_0 = 4 +3i \).
:::

# Preliminaries

## Complex Arithmetic

::: {.fact title="Complex roots of a number"}
The complex \( n \)th roots of \( z \coloneqq r e^{i\theta} \) are given by
\[
\left\{{ \omega_k \coloneqq r^{1/n} e^{i \qty{ \theta + 2k\pi \over n} } {~\mathrel{\Big|}~}0 \leq k \leq n-1 }\right\}
.\]
Note that one root is \( r^{1/n}\in {\mathbb{R}} \), and the rest are separated by angles of \( 2\pi/n \). Mnemonic:
\[
z = re^{i\theta} = re^{i\qty{\theta + 2k\pi}} \implies z^{1/n} = \cdots
.\]
:::

::: {.fact title="Complex Log"}
For \( z= r e^{i\theta}\neq 0 \), \( \theta \) is of the form \( \Theta + 2k\pi \) where \( \Theta = \operatorname{Arg}z \)
:::

::: {.fact}
Common trick:
\[
f^{1/n} = e^{{1\over n} \log(f)}
,\]
taking (say) a principal branch of \( \log \) given by \( {\mathbb{C}}\setminus(-\infty, 0] \times 0 \).
:::

## Complex Calculus

::: {.remark}
When parameterizing integrals \$`\int`{=tex}\_`\gamma `{=tex}f(z)`\,dz `{=tex}\$, parameterize \( \gamma \) by \( \theta \) and write \( z=re^{i\theta} \) so \( \,dz= ire^{i\theta}\,d\theta \).
:::

::: {.warnings}
\( f(z) = \sin(z), \cos(z) \) are unbounded on \( {\mathbb{C}} \)! An easy way to see this: they are nonconstant and entire, thus unbounded by Liouville.
:::

::: {.example title="?"}
You can show \( f(z) = \sqrt{z} \) is not holomorphic by showing its integral over \( S^1 \) is nonzero. This is a direct computation:
\[
\int_{S^1} z^{1/2} \,dz
&= \int_0^{2\pi} (e^{i\theta})^{1/2} ie^{i\theta} \,d\theta\\
&= i \int_0^{2\pi} e^{i3\theta \over 2}\,d\theta\\
&= i \qty{2\over 3i} e^{i3\theta \over 2}\Big|_{0}^{2\pi} \\
&= {2\over 3}\qty{e^{3\pi i - 1}} \\
&= -{4\over 3}
.\]

Note an issue: a different parameterization yields a different (still nonzero) number
\[
\cdots 
&= \int_{-\pi}^{\pi} (e^{i\theta})^{1/2} ie^{i\theta} \,d\theta\\
&= {2\over 3}\qty{ e^{3\pi i \over 2} - e^{-3\pi i \over 2}} \\
&= -{4i\over 3}
.\]
This is these are paths that don't lift to closed loops on the Riemann surface defined by \( z\mapsto z^2 \).
:::

### Holomorphy and Cauchy-Riemann

::: {.definition title="Analytic"}
A function \( f:\Omega \to {\mathbb{C}} \) is *analytic* at \( z_0\in \Omega \) iff there exists a power series \( g(z) = \sum a_n (z-z_0)^n \) with radius of convergence \( R>0 \) and a neighborhood \( U\ni z_0 \) such that \( f(z) = g(z) \) on \( U \).
:::

::: {.definition title="Complex differentiable / holomorphic /entire"}
A function \( f: {\mathbb{C}}\to {\mathbb{C}} \) is **complex differentiable** or **holomorphic** at \( z_0 \) iff the following limit exists:
\[
\lim_{h\to 0} { f(z_0 + h) - f(h) \over h  } 
.\]
A function that is holomorphic on \( {\mathbb{C}} \) is said to be **entire**.

Equivalently, there exists an \( \alpha\in {\mathbb{C}} \) such that
\[
f(z_0+h) - f(z_0) = \alpha h + R(h) && R(h) \overset{h\to 0}\longrightarrow 0 
.\]
In this case, \( \alpha = f'(z_0) \).
:::

::: {.example title="Holomorphic vs non-holomorphic"}
```{=tex}
\envlist
```
-   \( f(z) = {1\over z} \) is holomorphic on \( {\mathbb{C}}\setminus\left\{{0}\right\} \).
-   \( f(z) = \mkern 1.5mu\overline{\mkern-1.5muz\mkern-1.5mu}\mkern 1.5mu \) is *not* holomorphic, since \( \mkern 1.5mu\overline{\mkern-1.5muh\mkern-1.5mu}\mkern 1.5mu \over h \) does not converge (but is real differentiable).
:::

::: {.definition title="Real (multivariate) differentiable"}
A function \( F: {\mathbb{R}}^n\to {\mathbb{R}}^m \) is **real-differentiable** at \( \mathbf{p} \) iff there exists a linear transformation \( A \) such that
\[
{ {\left\lVert { F(\mathbf{p} + \mathbf{h}) - F(\mathbf{p}) - A(\mathbf{h}) } \right\rVert} \over {\left\lVert { \mathbf{h} } \right\rVert} } \overset{{\left\lVert {\mathbf{h}} \right\rVert}\to 0}\longrightarrow 0
.\]
Rewriting,
\[
{\left\lVert { F(\mathbf{p} + \mathbf{h}) - F(\mathbf{p})  - A(\mathbf{h}) } \right\rVert} = {\left\lVert { \mathbf{h} } \right\rVert} {\left\lVert { R(\mathbf{h}) } \right\rVert}
&& {\left\lVert {R(\mathbf{h}) } \right\rVert}\overset{{\left\lVert {\mathbf{h} } \right\rVert} \to 0}\longrightarrow 0
.\]

Equivalently,
\[
F(\mathbf{p} + \mathbf{h}) - F(\mathbf{p}) = A(\mathbf{h}) + {\left\lVert {\mathbf{h}} \right\rVert} R(\mathbf{h}) && {\left\lVert {R(\mathbf{h}) } \right\rVert}\overset{{\left\lVert {\mathbf{h} } \right\rVert} \to 0}\longrightarrow 0
.\]

Or in a slightly more useful form,
\[
F(\mathbf{p} + \mathbf{h}) = F(\mathbf{p}) + A(\mathbf{h}) + R(\mathbf{h}) && R\in o( {\left\lVert {\mathbf{h}} \right\rVert}), \text{ i.e. }
{ {\left\lVert { R(\mathbf{h}) } \right\rVert} \over  {\left\lVert {\mathbf{h}} \right\rVert}} \overset{\mathbf{h}\to 0}\longrightarrow 0
.\]
:::

::: {.proposition title="Complex differentiable implies Cauchy-Riemann"}
If \( f \) is differentiable at \( z_0 \), then the limit defining \( f'(z_0) \) must exist when approaching from any direction. Identify \( f(z) = f(x, y) \) and write \( z_0 = x+ iy \), then first consider \( h\in RR \), so \( h = h_1 + ih_2 \) with \( h_2 = 0 \). Then
\[
f'(z_0) = 
\lim_{h_1\to 0} { f(x+h_1, y) - f(x, y) \over h_1}
\coloneqq{\frac{\partial f}{\partial x}\,}(x, y)
.\]
Taking \( h \in i{\mathbb{R}} \) purely imaginary, so \( h= ih_2 \),
\[
f'(z_0)
= \lim_{ih_2\to 0} { f(x, y+h_2) - f(x, y) \over ih_2 } \coloneqq{1\over i} {\frac{\partial f}{\partial y}\,}(x, y)
.\]
Equating,
\[
{\frac{\partial f}{\partial x}\,} = {1\over i} {\frac{\partial f}{\partial y}\,}
,\]
and writing \( f = u + iv \) and \( 1/i = -i \) yields
\[
{\frac{\partial f}{\partial x}\,} &= {\frac{\partial u}{\partial x}\,} + i {\frac{\partial v}{\partial x}\,} \\
{1\over i} {\frac{\partial f}{\partial y}\,} &= {1\over i} \qty{ {\frac{\partial u}{\partial y}\,} + i {\frac{\partial v}{\partial y}\,}} = {\frac{\partial v}{\partial y}\,} - i{\frac{\partial u}{\partial y}\,} 
.\]
Thus
\[
{\frac{\partial u}{\partial x}\,} = {\frac{\partial v}{\partial y}\,} \hspace{8em} {\frac{\partial u}{\partial y}\,} = -{\frac{\partial v}{\partial x}\,}
.\]
:::

::: {.proposition title="Polar Cauchy-Riemann equations"}
\[  
\frac{\partial u}{\partial r}=\frac{1}{r} \frac{\partial v}{\partial \theta} \quad \text { and } \quad \frac{1}{r} \frac{\partial u}{\partial \theta}=-\frac{\partial v}{\partial r}
.\]
:::

::: {.proof}
Setting
\[
z = re^{i\theta} = r(\cos(\theta) + i\sin(\theta) ) = x+iy
\]
yields \( x=r\cos(\theta), y=r\sin(\theta) \), one can identify
\[
x_r = \cos(\theta)&, x_\theta = -r\sin(\theta) \\
y_r = \sin(\theta)&, y_\theta = r\cos(\theta)
.\]

Now apply the chain rule:
\[
u_r 
&= u_x x_r + u_y y_r \\
&= v_y x_r -v_x y_r && \text{CR}\\
&= v_y \cos(\theta) - v_x \sin(\theta) \\
&= {1\over r}\qty{ v_y r\cos(\theta) - v_x r\sin(\theta) } \\
&= {1\over r}\qty { v_y y_\theta + v_x x_\theta} \\
&= {1\over r} v_\theta
.\]
Similarly,
\[
v_r
&= v_x x_r + v_y y_r \\
&= v_x \cos(\theta) + v_y\sin(\theta) \\
&= -u_y\cos(\theta) + u_x\sin(\theta) && \text{CR} \\
&= {1\over r}\qty{ -u_y r\cos(\theta) + u_x r\sin(\theta)} \\
&= {1\over r}\qty{ -u_y y_\theta - u_x x_0 } \\
&= -{1\over r} u_\theta
.\]

Thus
\[
\frac{\partial u}{\partial r}=\frac{1}{r} \frac{\partial v}{\partial \theta} \quad \text { and } \quad \frac{\partial v}{\partial r}=-\frac{1}{r} \frac{\partial u}{\partial \theta} \\
.\]
:::

::: {.proposition title="Holomorphic functions have harmonic components"}
If \( f(z) = u(x, y) + iv(x, y) \) is holomorphic, then \( u, v \) are harmonic.
:::

::: {.proposition title="Holomorphic functions are continuous."}
\( f \) is holomorphic at \( z_0 \) iff there exists an \( a\in {\mathbb{C}} \) such that
\[  
f(z_0 + h) - f(z_0) - ah = h \psi(h), \quad \psi(h) \overset{h\to 0}\to 0
.\]
In this case, \( a = f'(z_0) \).
:::

::: {.proposition title="Cauchy-Riemann implies holomorphic"}
Recall that in general, \( f' = {\partial}f + \mkern 1.5mu\overline{\mkern-1.5mu{\partial}\mkern-1.5mu}\mkern 1.5muf \). If \( f = u+iv \) with \( u, v\in C^1({\mathbb{R}}) \) satisfying the Cauchy-Riemann equations on \( \Omega \), then \( f \) is holomorphic on \( \Omega \) and
\[
f'(z) = {\partial}f = {1 \over 2} \qty{{\frac{\partial }{\partial x}\,} + {1\over i} {\frac{\partial }{\partial y}\,}}f = {1\over 2}\qty{u_x + iv_x}
.\]
:::

::: {.theorem title="Analytic functions have harmonic components"}
If \( f=u+iv \) is analytic, then \( u, v \) are harmonic.
:::

::: {.proof title="?"}
```{=tex}
\envlist
```
-   By CR,
    \[
    u_x = v_y && u_y = -v_x
    .\]

-   Differentiate with respect to \( x \):
    \[
    u_{xx} = v_{yx} && u_{yx} = -v_{xx}
    .\]

-   Differentiate with respect to \( y \):
    \[
    u_{xy} = v_{yy} && u_{yy} = -v_{xy}
    .\]

-   Clairaut's theorem: partials are equal, so
    \[
    u_{xx} - v_{yx} = 0 \implies u_{xx} + u_{yy} = 0 \\ \\
    v_{xx} + u_{yx} = 0 \implies v_{xx} + v_{yy} = 0 \\ \\
    .\]
:::

### Delbar, Harmonic Functions, Laplacian

::: {.definition title="del and delbar operators"}
\[
{\partial}\coloneqq{\partial}_z \coloneqq{1\over 2}\qty{{\partial}_x - i {\partial}_y}
\quad
\text{ and }
\quad
\mkern 1.5mu\overline{\mkern-1.5mu{\partial}\mkern-1.5mu}\mkern 1.5mu
\coloneqq{\partial}_{\mkern 1.5mu\overline{\mkern-1.5muz\mkern-1.5mu}\mkern 1.5mu}
={1\over 2}\qty{ {\partial}_x + i{\partial}_y}
.\]
:::

::: {.proposition title="Holomorphic iff delbar vanishes"}
\( f \) is holomorphic at \( z_0 \) iff \( \mkern 1.5mu\overline{\mkern-1.5mu{\partial}\mkern-1.5mu}\mkern 1.5muf(z_0) = 0 \):
\[
2\mkern 1.5mu\overline{\mkern-1.5mu{\partial}\mkern-1.5mu}\mkern 1.5muf 
&\coloneqq({\partial}_x + i {\partial}_y) (u+iv) \\
&= u_x + iv_x + iu_y - v_y \\
&= (u_x - v_y) + i(u_y + v_x) \\
&= 0 && \text{by Cauchy-Riemann}
.\]
:::

::: {.definition title="Laplacian and Harmonic Functions"}
A real function of two variables \( u(x, y) \) is **harmonic** iff it is in the kernel of the Laplacian operator:
\[  
\Delta u \coloneqq\qty{{\frac{\partial ^2}{\partial x^2}\,} + {\frac{\partial ^2}{\partial y^2}\,}}u = 0
.\]
:::

### Exercises

::: {.proposition title="Injectivity Relates to Derivatives"}
If \( z_0 \) is a zero of \( f' \) of order \( n \), then \( f \) is \( (n+1) \)-to-one in a neighborhood of \( z_0 \).
:::

::: {.proof}
?
:::

```{=tex}
\todo[inline]{proof}
```
::: {.exercise title="Zero derivative implies constant"}
Show that if \( f' = 0 \) on a domain \( \Omega \), then \( f \) is constant on \( \Omega \)
:::

::: {.solution}
Write \( f = u + iv \), then \( 0 = 2 f' = u_x + iv_x = u_y - iu_y \), so \( \operatorname{grad}u = \operatorname{grad}v = 0 \). Show \( f \) is constant along every straight line segment \( L \) by computing the directional derivative \( \operatorname{grad}u \cdot \mathbf{v} = 0 \) along \( L \) connecting \( p, q \). Then \( u(p) = u(q) = a \) some constant, and \( v(p) = v(q) = b \), so \( f(z) = a+bi \) everywhere.
:::

::: {.exercise title="f and fbar holomorphic implies constant"}
Show that if \( f \) and \( \mkern 1.5mu\overline{\mkern-1.5muf\mkern-1.5mu}\mkern 1.5mu \) are both holomorphic on a domain \( \Omega \), then \( f \) is constant on \( \Omega \).
:::

::: {.solution}
```{=tex}
\envlist
```
-   Strategy: show \( f'=0 \).

-   Write \( f = u + iv \). Since \( f \) is analytic, it satisfies CR, so
    \[
    u_x = v_y && u_y = -v_x
    .\]

-   Similarly write \( \mkern 1.5mu\overline{\mkern-1.5muf\mkern-1.5mu}\mkern 1.5mu = U + iV \) where \( U = u \) and \( V = -v \). Since \( \mkern 1.5mu\overline{\mkern-1.5muf\mkern-1.5mu}\mkern 1.5mu \) is analytic, it also satisfies CR , so
    \[
    U_x = V_y && U_y = -V_x \\ \\
    \implies u_x = -v_y && u_y = v_x
    .\]

-   Add the LHS of these two equations to get \( 2u_x = 0 \implies u_x = 0 \). Subtract the right-hand side to get \( -2v_x = 0 \implies v_x = 0 \)

-   Since \( f \) is analytic, it is holomorphic, so \( f' \) exists and satisfies \( f' = u_x + iv_x \). But by above, this is zero.

-   By the previous exercise, \( f'=0 \implies f \) is constant.
:::

::: {.exercise title="S&S 1.13: Constant real/imaginary/magnitude implies constant"}
If \( f \) is holomorphic on \( \Omega \) and any of the following hold, then \( f \) is constant:

1.  \( \Re(f) \) is constant.
2.  \( \Im(f) \) is constant.
3.  \( {\left\lvert {f} \right\rvert} \) is constant.
:::

::: {.solution}
**Part 3**:

-   Write \( {\left\lvert {f} \right\rvert} = c \in {\mathbb{R}} \).
-   If \( c=0 \), done, so suppose \( c>0 \).
-   Use \( f\mkern 1.5mu\overline{\mkern-1.5muf\mkern-1.5mu}\mkern 1.5mu = {\left\lvert {f} \right\rvert}^2 = c^2 \) to write \( \mkern 1.5mu\overline{\mkern-1.5muf\mkern-1.5mu}\mkern 1.5mu=c^2/f \).
-   Since \( {\left\lvert {f(z)} \right\rvert} = 0 \iff f(z) = 0 \), we have \( f\neq 0 \) on \( \Omega \), so \( \mkern 1.5mu\overline{\mkern-1.5muf\mkern-1.5mu}\mkern 1.5mu \) is analytic.
-   Similarly \( f \) is analytic, and \( f,\mkern 1.5mu\overline{\mkern-1.5muf\mkern-1.5mu}\mkern 1.5mu \) analytic implies \( f'=0 \) implies \( f \) is constant.
:::

```{=tex}
\todo[inline]{Finish}
```
## Power Series

::: {.theorem title="Improved Taylor's Theorem"}
If \( f \) is holomorphic on a region \( \Omega \) with \( \overline{ D_R(z_0)} \subseteq \Omega \), and for every \( z\in D_r(z_0) \), \( f \) has a power series expansion of the following form:
\[
f(z)=\sum_{n=0}^{\infty} a_{n}\left(z-z_{0}\right)^{n} \quad\text{where} a_{n}=\frac{f^{(n)}\left(z_{0}\right)}{n !}
= {1 \over 2\pi r^n}\int_0^{2\pi} f(z_0 + re^{i\theta})e^{-in\theta} \,d\theta
.\]
:::

::: {.proposition title="Power Series are Smooth"}
Any power series is smooth (and thus holomorphic) on its disc of convergence, and its derivatives can be obtained using term-by-term differentiation:
\[
{\frac{\partial }{\partial z}\,} f(z) = {\frac{\partial }{\partial z}\,} \sum_{k\geq 0} c_k (z-z_0)^k = \sum_{k\geq 1} kc_k (z-z_0)^k
.\]
Moreover, the coefficients are given by
\[
c_k = {f^{(n)}(z_0) \over n! }
.\]
:::

::: {.proposition title="Exponential is uniformly convergent in discs"}
\( f(z) = e^z \) is uniformly convergent in any disc in \( {\mathbb{C}} \).
:::

::: {.proof}
Apply the estimate
\[  
{\left\lvert {e^z} \right\rvert} \leq \sum {{\left\lvert {z} \right\rvert}^n \over n!} = e^{{\left\lvert {z} \right\rvert}}
.\]
Now by the \( M{\hbox{-}} \)test,
\[  
{\left\lvert {z} \right\rvert} \leq R < \infty \implies {\left\lvert {\sum {z^n \over n!}} \right\rvert} \leq e^R < \infty
.\]
:::

::: {.lemma title="Dirichlet's Test"}
Given two sequences of real numbers \( \left\{{ a_k }\right\} , \left\{{ b_k }\right\} \) which satisfy

1.  The sequence of partial sums \( \left\{{ A_n }\right\} \) is bounded,
2.  \( b_k \searrow 0 \).

then
\[
\sum_{k\geq 1} a_k b_k < \infty
.\]
:::

::: {.proof title="?"}
> See <http://www.math.uwaterloo.ca/~krdavids/Comp/Abel.pdf>

Use summation by parts. For a fixed \( \sum a_k b_k \), write
\[
\sum_{n=1}^m x_n Y_n + \sum_{n=1}^m X_n y_{n+1} = X_m Y_{m+1}
.\]
Set \( x_n \coloneqq a_n, y_N \coloneqq b_n - b_{n-1} \), so \( X_n = A_n \) and \( Y_n = b_n \) as a telescoping sum. Importantly, all \( y_n \) are negative, so \( {\left\lvert {y_n} \right\rvert} = {\left\lvert {b_n - b_{n-1}} \right\rvert} = b_{n-1} - b_n \), and moreover \( a_n b_n = x_n Y_n \) for all \( n \). We have
\[
\sum_{n\geq 1} a_n b_n 
&= \lim_{N\to\infty} \sum_{n\leq N} x_n Y_n \\
&= \lim_{N\to\infty} \sum_{n\leq N} X_N Y_N - \sum_{n\leq N} X_n y_{n+1} \\
&= - \sum_{n\geq 1} X_n y_{n+1},
\]
where in the last step we've used that
\[
{\left\lvert {X_N} \right\rvert} = {\left\lvert {A_N} \right\rvert}\leq M \implies {\left\lvert {X_N Y_{N} } \right\rvert} = {\left\lvert {X_N} \right\rvert} {\left\lvert {b_{n+1}} \right\rvert} \leq M b_{n+1} \to 0
.\]
So it suffices to bound the latter sum:
\[
\sum_{k\geq n}{\left\lvert { X_k y_{k+1} } \right\rvert} 
&\leq M \sum_{k\geq 1} {\left\lvert {y_{k+1}} \right\rvert}\\
&\leq M \sum_{k\geq 1} b_{k} - b_{k+1} \\
&\leq 2M(b_1 - b_{n+1})\\
&\leq 2M b_1
.\]
:::

::: {.theorem title="Abel's Theorem"}
If \( \sum_{k=1}^\infty c_k \) converges, then
\[
\lim_{z\to 1^-} \sum_{k\in {\mathbb{N}}} c_k z^k = \sum_{k\in {\mathbb{N}}} c_k
.\]
:::

::: {.lemma title="Abel's Test"}
If \( f(z) \coloneqq\sum c_k z^k \) is a power series with \( c_k \in {\mathbb{R}}^{\geq 0} \) and \( a_n\searrow 0 \), then \( f \) converges on \( S^1 \) except possibly at \( z=1 \).
:::

::: {.example title="application of Abel's theorem"}
Integrate a geometric series to obtain
\[
\sum {(-1)^k z^k \over n} = \log(z+1) && {\left\lvert {z} \right\rvert} < 1
.\]
Since \( c_k \coloneqq(-1)^k/k \searrow 0 \), this converges at \( z=1 \), and by Abel's theorem \( f(1) = \log(2) \).
:::

::: {.remark}
The converse to Abel's theorem is false: take \( f(z) = \sum (-z)^n = 1/(1+z) \). Then \( f(1) = 1-1+1-\cdots \) diverges at 1, but \( 1/1+1 = 1/2 \). So the limit \( s\coloneqq\lim_{x\to 1^-} f(x) 1/2 \), but \( \sum a_n \) doesn't converge to \( s \).
:::

::: {.proposition title="Summation by Parts"}
Setting \( A_n \coloneqq\sum_{k=1}^n b_k \) and \( B_0 \coloneqq 0 \),
\[
\sum_{k=m}^n a_k b_k 
&= A_nb_n - A_{m-1} b_m - \sum_{k=m}^{n-1} A_k(b_{k+1} - b_{k})
.\]
Compare this to integrating by parts:
\[
\int_a^b f g = F(b)g(b) - F(a)g(a) - \int_a^b Fg'
.\]

Note there is a useful form for taking the product of sums:
\[
A_{n} B_{n}=\sum_{k=1}^{n} A_{k} b_{k}+\sum_{k=1}^{n} a_{k} B_{k-1}
.\]
:::

### Exercises: Series

::: {.exercise title="Application of summation by parts"}
Use summation by parts to show that \( \sin(n)/n \) converges.
:::

::: {.solution}
An inelegant proof: define \( A_n \coloneqq\sum_{k\leq n} a_k \), use that \( a_k = A_k - A_{k-1} \), reindex, and peel a top/bottom term off of each sum to pattern-match.\

Behold:
\[
\sum_{m\leq k \leq n} a_k b_k 
&= \sum_{m\leq k \leq n} (A_k - A_{k-1}) b_k \\
&= \sum_{m\leq k \leq n} A_kb_k - \sum_{m\leq k \leq n} A_{k-1} b_k \\
&= \sum_{m\leq k \leq n} A_kb_k - \sum_{m-1\leq k \leq n-1} A_{k} b_{k+1} \\
&= A_nb_n + \sum_{m\leq k \leq n-1} A_kb_k - \sum_{m-1\leq k \leq n-1} A_{k} b_{k+1} \\
&= A_nb_n - A_{m-1} b_{m} + \sum_{m\leq k \leq n-1} A_kb_k - \sum_{m\leq k \leq n-1} A_{k} b_{k+1} \\
&= A_nb_n - A_{m-1} b_{m} + \sum_{m\leq k \leq n-1} A_k(b_k - b_{k+1}) \\
&= A_nb_n - A_{m-1} b_{m} - \sum_{m\leq k \leq n-1} A_k(b_{k+1} - b_{k}) 
.\]
:::

::: {.exercise title="1.20: Series convergence on the circle"}
Show that

1.  \( \sum kz^k \) diverges on \( S^1 \).
2.  \( \sum k^{-2} z^k \) converges on \( S^1 \).
3.  \( \sum k^{-1}z^k \) converges on \( S^1\setminus\left\{{1}\right\} \) and diverges at \( 1 \).
:::

::: {.solution}
1.  Use that \( {\left\lvert {z^k} \right\rvert} = 1 \) and \( \sum c_kz^k < \infty \implies {\left\lvert {c_k} \right\rvert} \to 0 \), but \( {\left\lvert {kz^k} \right\rvert} = {\left\lvert {k} \right\rvert} \to \infty \) here.
2.  Use that absolutely convergent implies convergent, and \( \sum {\left\lvert {k^{-2} z^k} \right\rvert} = \sum {\left\lvert {k^{-2}} \right\rvert} \) converges by the \( p{\hbox{-}} \)test.
3.  If \( z=1 \), this is the harmonic series. Otherwise take \( a_k = 1/k, b_k = e^{i k \theta} \) where \( \theta \in (0, 2\pi) \) is some constant, and apply Dirichlet's test. It suffices to bound the partial sums of the \( b_k \). Recalling that \( \sum_{k\leq N} r^k = (1-r^{N+1}) / (1-r) \),
    \[
      {\left\lVert { \sum_{k\leq m} e^{ik\theta } } \right\rVert} = {\left\lVert {1 - e^{i(m+1)\theta} \over 1 - e^{i\theta}} \right\rVert} \leq {2 \over {\left\lVert { 1- e^{i\theta}} \right\rVert}} \coloneqq M
      ,\]
    which is a constant. Here we've used that two points on \( S^1 \) are at most distance 2 from each other.
:::

::: {.exercise title="Laurent expansions inside and outside of a disc"}
Expand \( f(z) = {1\over z(z-1)} \) in both

-   \( {\left\lvert {z} \right\rvert} < 1 \)
-   \( {\left\lvert {z} \right\rvert} > 1 \)
:::

::: {.solution}
\[
{1\over z(z-1)} = -{1\over z}{1 \over 1-z} = -{1\over z}\sum z^k
.\]
and
\[
{1\over z(z-1)} = {1\over z^2(1 - {1\over z})} = {1\over z^2} \sum \qty{1\over z}^k
.\]
:::

::: {.exercise title="Laurent expansions about different points"}
Find the Laurent expansion about \( z=0 \) and \( z=1 \) respectively of the following function:
\[
f(z) \coloneqq{z+1 \over z(z-1)}
.\]
:::

::: {.solution}
Note: once you see that everything is in terms of powers of \( (z-z_0) \), you're essentially done. For \( z=0 \):
\[
{z+1 \over z(z-1)}
&= {1\over z} {z+1 \over z-1} \\
&= -{z+1\over z} {1\over 1-z} \\
&= -\qty{1 + {1\over z}}\sum_{k\geq 0} z^k
.\]

For \( z=1 \):
\[
{z+1 \over z(z-1)}
&= {1\over z-1}\qty{1 + {1\over z} } \\
&= {1\over z-1}\qty{1 + {1\over 1 - (1-z)} } \\
&= {1\over z-1} \qty{1 + \sum_{k\geq 0} (1-z)^k } \\
&= {1\over z-1} \qty{1 + \sum_{k\geq 0} (-1)^k (z-1)^k }
.\]
:::

# Cauchy's Theorem

## Complex Integrals

::: {.definition title="Complex Integral"}
\[
\int_{\gamma} f d z:=\int_{I} f(\gamma(t)) \gamma^{\prime}(t) \,dt
= \int_\gamma (u+iv)\,dx\wedge (-v+iu)\,dy
.\]
:::

::: {.proposition title="Crude integral estimate"}
Define the *length* of a curve by
\[
\operatorname{len}(\gamma) \coloneqq\int_\gamma {\left\lvert {\,dz} \right\rvert} = \int_I {\left\lvert {\gamma'(t)} \right\rvert} \,dt
.\]

Then there is an estimate of the following form:
\[
\left|\int_{\gamma} f d z\right| \leq \int_{\gamma}|f||d z| \leq\left(\sup _{\gamma}|f|\right) \cdot \operatorname{len}(\gamma)
.\]
:::

::: {.exercise title="Primitives imply vanishing integral"}
Show that if \( f \) has a primitive \( F \) on \( \Omega \) then \( \int_\gamma f = 0 \) for every closed curve \( \gamma \subseteq \Omega \).
:::

::: {.theorem title="Goursat"}
If \( f \) is analytic on a rectangle \( R \) with horizontal and vertical sides, then \( \int_{{{\partial}}R} f = 0 \).
:::

::: {.theorem title="Cauchy's Theorem" ref="CauchyTheorem"}
If \( f \) is holomorphic on a simply-connected region \( \Omega \), then for any closed path \( \gamma \subseteq \Omega \),
\[  
\int_{\gamma} f(z) \,dz= 0
.\]
:::

::: {.slogan}
Closed path integrals of holomorphic functions vanish.
:::

## Applications of Cauchy's Theorem

### Integral Formulas and Estimates

::: {.theorem title="Cauchy Integral Formula" ref="CauchyIntegral"}
Suppose \( f \) is holomorphic on \( \Omega \), then for any \( z_0 \in \Omega \) and any open disc \( \overline{D_R(z_0)} \) such that \( \gamma \coloneqq{{\partial}}\overline{D_R(z_0)} \subseteq \Omega \),
\[
f(z_0) = {1 \over 2\pi i} \int_{\gamma} {f(\xi) \over \xi-z_0}\ \,d\xi
\]
and
\[
{\frac{\partial ^nf }{\partial z^n}\,}(z_0) = {n! \over 2\pi i} \int_{\gamma} {f(\xi) \over (\xi - z_0)^{n+1}} \,d\xi
.\]
:::

::: {.theorem title="Cauchy's Inequality" ref="CauchyInequality"}
For \( z_0 \in D_R(z_0) \subset \Omega \), we have
\[
{\left\lvert { f^{(n)} (z_0) } \right\rvert} 
\leq \frac{n !}{2 \pi} \int_{0}^{2 \pi} \frac{ {\left\lVert {f} \right\rVert}_{\infty} } {R^{n+1}} R \,d\theta
= \frac{n !{\left\lVert {f} \right\rVert}_{\infty}}{R^n} 
,\]
where \( {\left\lVert {f} \right\rVert}_{\infty}\coloneqq\sup_{z\in C_R} {\left\lvert {f(z)} \right\rvert} \).
:::

::: {.proof title="of Cauchy's inequality"}
```{=tex}
\envlist
```
-   Given \( z_0\in \Omega \), pick the largest disc \( D_R(z_0) \subset \Omega \) and let \( C_R = {{\partial}}D_R \).
-   Then apply the integral formula.
:::

::: {.slogan}
The \( n \)th Taylor coefficient of an analytic function is at most \( \sup_{{\left\lvert {z} \right\rvert} = R} {\left\lvert {f} \right\rvert}/R^n \).
:::

::: {.theorem title="Mean Value Theorem for Holomorphic Functions"}
If \( f \) is holomorphic on \( D_r(z_0) \)
\[
f(z_0) 
= {1\over 2\pi} \int_0^{2\pi} f(z_0 + re^{i\theta}) \,d\theta
= {1\over \pi r^2} \iint_{D_r(z_0)} f(z)\, dA
.\]
:::

### Liouville

::: {.theorem title="Liouville's Theorem" ref="Liouville"}
If \( f \) is entire and bounded, \( f \) is constant.
:::

::: {.proof title="?"}
Use Cauchy's inequality to show \( f'\equiv 0 \).
:::

::: {.exercise title="?"}
![image_2021-05-17-11-54-14](figures/image_2021-05-17-11-54-14.png)
:::

### Continuation Principle

::: {.theorem title="Continuation Principle / Identity Theorem"}
If \( f \) is holomorphic on a bounded connected domain \( \Omega \) and there exists a sequence \( \left\{{z_i}\right\} \) with a limit point in \( \Omega \) such that \( f(z_i) = 0 \), then \( f\equiv 0 \) on \( \Omega \).
:::

::: {.slogan}
Two functions agreeing on a set with a limit point are equal on a domain.
:::

::: {.proof title="?"}
Apply Improved Taylor Theorem? `\todo[inline]{todo}`{=tex}
:::

::: {.exercise title="?"}
![image_2021-05-17-11-53-33](figures/image_2021-05-17-11-53-33.png)
:::

## Morera's Theorem

::: {.theorem title="Morera's Theorem" ref="Morera"}
If \( f \) is continuous on a domain \( \Omega \) and \( \int_T f = 0 \) for every triangle \( T\subset \Omega \), then \( f \) is holomorphic.
:::

::: {.slogan}
If every integral along a triangle vanishes, implies holomorphic.
:::

::: {.corollary title="Sufficient condition for a sequence to converge to a holomorphic function"}
If \( \left\{{ f_n }\right\}_{n\in {\mathbb{N}}} \) is a holomorphic sequence on a region \( \Omega \) which uniformly converges to \( f \) on every compact subset \( K \subseteq \Omega \), then \( f \) is holomorphic, and \( f_n' \to f' \) uniformly on every such compact subset \( K \).
:::

::: {.proof title="?"}
Commute limit with integral and apply Morera's theorem.
:::

::: {.remark}
This can be applied to series of the form \( \sum_k f_k(z) \).
:::

### Symmetric Regions

In this section, take \( \Omega \) to be a region symmetric about the real axis, so \( z\in \Omega \iff \mkern 1.5mu\overline{\mkern-1.5muz\mkern-1.5mu}\mkern 1.5mu \in \Omega \). Partition this set as \( \Omega^+ \subseteq {\mathbb{H}}, I \subseteq {\mathbb{R}}, \Omega^- \subseteq \mkern 1.5mu\overline{\mkern-1.5mu{\mathbb{H}}\mkern-1.5mu}\mkern 1.5mu \).

::: {.theorem title="Symmetry Principle"}
Suppose that \( f^+ \) is holomorphic on \( \Omega^+ \) and \( f^- \) is holomorphic on \( \Omega^- \), and \( f \) extends continuously to \( I \) with \( f^+(x) = f^-(x) \) for \( x\in I \). Then the following piecewise-defined function is holomorphic on \( \Omega \):
\[
f(z) 
\coloneqq
\begin{cases}
f^+(z) & z\in \Omega^+ 
\\
f^-(z) & z\in \Omega^-
\\
f^+(z) = f^-(z) & z\in I.
\end{cases}
\]
:::

::: {.proof title="?"}
Apply Morera?
:::

::: {.theorem title="Schwarz Reflection " ref="SchwarzReflection"}
If \( f \) is continuous and holomorphic on \( {\mathbb{H}}^+ \) and real-valued on \( {\mathbb{R}} \), then the extension defined by \( F^-(z) = \mkern 1.5mu\overline{\mkern-1.5muf(\mkern 1.5mu\overline{\mkern-1.5muz\mkern-1.5mu}\mkern 1.5mu)\mkern-1.5mu}\mkern 1.5mu \) for \( z\in {\mathbb{H}}^- \) is a well-defined holomorphic function on \( {\mathbb{C}} \).
:::

::: {.proof title="?"}
Apply the symmetry principle.
:::

::: {.remark}
\( {\mathbb{H}}^+, {\mathbb{H}}^- \) can be replaced with any region symmetric about a line segment \( L\subseteq {\mathbb{R}} \).
:::

# Zeros and Singularities

::: {.definition title="Singularity"}
A point \( z_0 \) is an **isolated singularity** if \( f(z_0) \) is undefined but \( f(z) \) is defined in a punctured neighborhood \( D(z_0)\setminus\left\{{z_0}\right\} \) of \( z_0 \).

There are three types of isolated singularities:

-   Removable singularities
-   Poles
-   Essential singularities
:::

::: {.example title="?"}
The singularities of a rational function are always isolated, since there are finitely many zeros of any polynomial. The function \( F(z) \coloneqq\operatorname{Log}(z) \) has a singularity at \( z=0 \) that is **not** isolated, since every neighborhood intersects the branch cut \( (-\infty, 0) \times\left\{{ 0 }\right\} \), where \( F \) is not even defined. The function \( G(z) \coloneqq 1/\sin(\pi/z) \) has a non-isolated singularity at 0 and isolated singularities at \( 1/n \) for all \( n \).
:::

::: {.definition title="Removable Singularities"}
If \( z_0 \) is a singularity of \( f \). then \( z_0 \) is a **removable singularity** iff there exists a holomorphic function \( g \) such that \( f(z) = g(z) \) in a punctured neighborhood of \( z_0 \). Equivalently,
\[
\lim_{z\to \z_0}(z-z_0) f(z) = 0
.\]
Equivalently, \( f \) is bounded on a neighborhood of \( z_0 \).
:::

::: {.theorem title="Extension over removable singularities"}
If \( f \) is holomorphic on \( \Omega\setminus\left\{{z_0}\right\} \) where \( z_0 \) is a removable singularity, then there is a unique holomorphic extension of \( f \) to all of \( \Omega \).
:::

::: {.proof title="?"}
Take \( \gamma \) to be a circle centered at \( z_0 \) and use
\[
f(z) \coloneqq\int_\gamma { f(\xi) \over \xi - z} \dxii
.\]
This is valid for \( z\neq z_0 \), but the right-hand side is analytic. (?)
:::

```{=tex}
\todo[inline]{Revisit}
```
::: {.theorem title="Improved Taylor Remainder Theorem"}
If \( f \) is analytic on a region \( \Omega \) containing \( z_0 \), then \( f \) can be written as
\[
f(z)
=\left(\sum_{k=0}^{n-1} \frac{f^{(k)}\left(z_{0}\right)}{k !}\left(z-z_{0}\right)^{k}\right)+ 
R_{n}(z)\left(z-z_{0}\right)^{n}
,\]
where \( R_n \) is analytic.
:::

::: {.definition title="Zeros"}
If \( f \) is analytic and not identically zero on \( \Omega \) with \( f(z_0) = 0 \), then there exists a nonvanishing holomorphic function \( g \) such that
\[
f(z) = (z-z_0)^n g(z)
.\]
We refer to \( z_0 \) as a **zero of order \( n \)**.
:::

::: {.definition title="Poles (and associated terminology)"}
A *pole* \( z_0 \) of a function \( f(z) \) is a zero of \( g(z) \coloneqq{1\over f(z)} \). Equivalently, \( \lim_{z\to z_0} f(z) = \infty \). In this case there exists a minimal \( n \) and a holomorphic \( h \) such that
\[  
f(z) = \qty{z-z_0}^{-n} h(z)
.\]
Such an \( n \) is the *order* of the pole. A pole of order 1 is said to be a *simple pole*.
:::

::: {.definition title="Principal Part and Residue"}
If \( f \) has a pole of order \( n \) at \( z_0 \), then there exist a holomorphic \( G \) in a neighborhood of \( z_0 \) such that
\[
f(z) = {a_{-n} \over (z-z_0)^n } + \cdots + {a_{-1} \over z-z_0} + G(z) \coloneqq P(z) + G(z)
.\]

The term \( P(z) \) is referred to as the *principal part of \( f \) at \( z_0 \)* consists of terms with negative degree, and the *residue* of \( f \) at \( z_0 \) is the coefficient \( a_{-1} \).
:::

::: {.definition title="Essential Singularity"}
A singularity \( z_0 \) is *essential* iff it is neither removable nor a pole. Equivalently, a Laurent series expansion about \( z_0 \) has a principal part with infinitely many terms.
:::

::: {.theorem title="Casorati-Weierstrass" ref="Casorati"}
If \( f \) is holomorphic on \( \Omega\setminus\left\{{z_0}\right\} \) where \( z_0 \) is an essential singularity, then for every \( V\subset \Omega\setminus\left\{{z_0}\right\} \), \( f(V) \) is dense in \( {\mathbb{C}} \).
:::

::: {.slogan}
The image of a punctured disc at an essential singularity is dense in \( {\mathbb{C}} \).
:::

::: {.proof title="of Casorati-Weierstrass"}
Pick \( w\in {\mathbb{C}} \) and suppose toward a contradiction that \( D_R(w) \cap f(V) \) is empty. Consider
\[
g(z) \coloneqq{1\over f(z) - w}
,\]
and use that it's bounded to conclude that \( z_0 \) is either removable or a pole for \( f \).
:::

::: {.definition title="Singularities at infinity"}
For any \( f \) holomorphic on an unbounded region, we say \( z=\infty \) is a singularity (of any of the above types) of \( f \) if \( g(z) \coloneqq f(1/z) \) has a corresponding singularity at \( z=0 \).
:::

::: {.definition title="Meromorphic"}
A function \( f:\Omega\to{\mathbb{C}} \) is *meromorphic* iff there exists a sequence \( \left\{{z_n}\right\} \) such that

-   \( \left\{{z_n}\right\} \) has no limit points in \( \Omega \).
-   \( f \) is holomorphic in \( \Omega\setminus\left\{{z_n}\right\} \).
-   \( f \) has poles at the points \( \left\{{z_n}\right\} \).

Equivalently, \( f \) is holomorphic on \( \Omega \) with a discrete set of points delete which are all poles of \( f \).
:::

::: {.theorem title="Meromorphic implies rational"}
Meromorphic functions on \( {\mathbb{C}} \) are rational functions.
:::

::: {.proof title="?"}
Consider \( f(z) - P(z) \), subtracting off the principal part at each pole \( z_0 \), to get a bounded entire function and apply Liouville.
:::

::: {.theorem title="Riemann Extension Theorem"}
A singularity of a holomorphic function is removable if and only if the function is bounded in some punctured neighborhood of the singular point.
:::

# Residues

::: {.fact}
Some useful facts:
\[
{\left\lvert {e^{z}} \right\rvert} = e^{\Re(z)}
.\]

On \( S^1 \),
\[
1/z = e^{-i\theta} \\
\cos (\theta)=\frac{\mathrm{e}^{i \theta}+\mathrm{e}^{-i \theta}}{2}=\frac{z+1 / z}{2} \\
\sin (\theta)=\frac{\mathrm{e}^{i \theta}-\mathrm{e}^{-i \theta}}{2 i}=\frac{z-1 / z}{2 i} 
.\]
:::

::: {.fact}
The major fact that reduces integrals to residues:
\[
\int_\gamma z^k \,dz= \int_0^{2\pi} e^{ik\theta} ie^{i\theta } \,d\theta= \int_0^{2\pi} e^{i(k+1)\theta \,d\theta}
=
\begin{cases}
2\pi i & k=-1 
\\
0 & \text{else}.
\end{cases}
.\]
Thus
\[
\int \sum_{k\geq -M} c_k z^k = \sum_{k\geq -M} \int c_k z^k = 2\pi i c_{-1}
,\]
i.e. the integral picks out the \( c_{-1} \) coefficient in a Laurent series expansion.
:::

::: {.remark}
Check: do you need residues at all?? You may be able to just compute an integral!

-   Directly by parameterization:
    \[
    \int_\gamma f = \int_a^b f(z(t))\, z'(t) && \text{for } z(t) \text{ a parameterization of } \gamma
    ,\]

-   Finding a primitive \( F \),

-   Writing \( z= z_0 + re^{i \theta } \)
:::

## Computing Residues

::: {.definition title="Toy contour"}
A closed Jordan curve that separates \( {\mathbb{C}} \) into an exterior and interior region is referred to as a **toy contour**.
:::

::: {.definition title="Winding Number"}
For \( \gamma \subseteq \Omega \) a closed curve not passing through a point \( z_0 \), the **winding number of \( \gamma \) about \( z_0 \)** is defined as
\[
n_\gamma(z_0) \coloneqq{1\over 2\pi i} \int_\gamma {1\over \xi -z_0}\,d\xi
.\]
:::

::: {.proposition title="Residue formula for higher order poles"}
If \( f \) has a pole \( z_0 \) of order \( n \), then
\[  
\mathop{\mathrm{Res}}_{z=z_0} f = \lim_{z\to z_0} {1 \over (n-1)!} \qty{{\frac{\partial }{\partial z}\,}}^{n-1} (z-z_0)^n f(z)
.\]
:::

::: {.proposition title="Residue formula for simple poles"}
As a special case, if \( z_0 \) is a simple pole of \( f \), then
\[  
\mathop{\mathrm{Res}}_{z=z_0}f = \lim_{z\to z_0} (z-z_0) f(z)
.\]
:::

::: {.corollary title="Better derivative formula that sometimes works for simple poles"}
If additionally \( f=g/h \) where \( h(z_0) = 0 \) and \( h'(z_0)\neq 0 \), we can apply L'Hopital's rule to compute this residue:
\[
(z-z_0) {g(z) \over h(z)} = {(z-z_0) g(z) \over h(z) } \overset{LH}{=}
{g(z) + (z-z_0) g'(z) \over h'(z)} \overset{z\to z_0}\longrightarrow{g(z_0) \over h'(z_0)}
.\]
:::

::: {.example title="Residue of a simple pole (order 1)"}
Let \( f(z) = \frac{1}{1+z^2} \), then \( \mathop{\mathrm{Res}}(i, f) = \frac{1}{2i} \).
:::

::: {.theorem title="The Residue Theorem"}
Let \( f \) be meromorphic on a region \( \Omega \) with poles \( \left\{{ { {z}_1, {z}_2, \cdots, {z}_{N}} }\right\} \). Then for any \( \gamma \in \Omega\setminus\left\{{ { {z}_1, {z}_2, \cdots, {z}_{N}} }\right\} \),
\[
{1 \over 2\pi i } \int_\gamma f(z) \,dz= \sum_{j=1}^N n_\gamma(z_j) \mathop{\mathrm{Res}}_{z=z_j} f
.\]
If \( \gamma \) is a toy contour, then\
\[
{1\over 2\pi i}\int_\gamma f\,dz= \sum_{j=1}^N \mathop{\mathrm{Res}}_{z=z_j}f
.\]
:::

### Exercises

> Some good computations [here](https://math.mit.edu/~jorloff/18.04/notes/topic9.pdf).

![image_2021-05-17-13-32-46](figures/image_2021-05-17-13-32-46.png) ![image_2021-05-17-13-32-57](figures/image_2021-05-17-13-32-57.png) ![image_2021-05-17-13-33-12](figures/image_2021-05-17-13-33-12.png) ![image_2021-05-17-13-33-30](figures/image_2021-05-17-13-33-30.png)

::: {.exercise title="?"}
\[
\int_{\mathbb{R}}{1 \over (1+x^2)^2} \,dx
.\]
:::

::: {.solution}
```{=tex}
\envlist
```
-   Factor \( (1+z^2)^2 = ((z-i)(z+i))^2 \), so \( f \) has poles at \( \pm i \) of order 2.
-   Take a semicircular contour \( \gamma \coloneqq I_R \cup D_R \), then \( f(z) \approx 1/z^4 \to 0 \) for large \( R \) and \( \int_{D_R} f \to 0 \).
-   Note \( \int_{I_R} f \to \int_{\mathbb{R}}f \), so \( \int_\gamma f \to \int_{\mathbb{R}}f \).
-   \( \int_\gamma f = 2\pi i \sum_{z_0} \mathop{\mathrm{Res}}_{z=z_0} f \), and \( z_0 = i \) is the only pole in this region.
-   Compute
    \[
    \mathop{\mathrm{Res}}_{z=i} f 
    &= \lim_{z\to i} {1\over (2-1)!} {\frac{\partial }{\partial z}\,} (z-i)^2 f(z) \\
    &= \lim_{z\to i} {\frac{\partial }{\partial z}\,} {1\over (z+i)^2 } \\
    &= \lim_{z\to i} {-2 \over (z+i)^3 } \\
    &= -{2 \over (2i)^3 } \\
    &= {1\over 4i} \\ \\
    \implies
    \int_\gamma f &= {2\pi i \over 4i} = \pi/2
    ,\]
:::

## Argument Principle

::: {.theorem title="Argument Principle"}
For \( f \) meromorphic in \( \gamma^\circ \) with zeros \( \left\{{ z_j }\right\} \) and poles \( \left\{{ p_k }\right\} \) repeated with multiplicity where \( \gamma \) does not intersect any zeros or poles, then
\[  
\Delta_\gamma \arg f(z) \coloneqq{1\over 2\pi i} \int_\gamma {f'(z) \over f(z)} \,dz= \sum_{j} n_\gamma(z_j) - \sum_k n_\gamma(p_k) = Z_f - P_f
,\]
where \( Z_f \) and \( P_f \) are the number of zeros and poles respectively enclosed by \( \gamma \), counted with multiplicity.
:::

::: {.proof title="?"}
Residue formula applied to \( f'\over f \)?
:::

::: {.corollary title="Rouché's Theorem" ref="Rouche"}
If \( f, g \) are analytic on a domain \( \Omega \) with finitely many zeros in \( \Omega \) and \( \gamma \subset \Omega \) is a closed curve surrounding each point exactly once, where \( {\left\lvert {g} \right\rvert} < {\left\lvert {f} \right\rvert} \) on \( \gamma \), then \( f \) and \( f+g \) have the same number of zeros.

Alternatively:

Suppose \( f = g + h \) with \( g \neq 0, \infty \) on \( \gamma \) with \( {\left\lvert {g} \right\rvert} > {\left\lvert {h} \right\rvert} \) on \( \gamma \). Then
\[\Delta_\gamma \arg(f) = \Delta_\gamma \arg(h)\quad\text{ and } Z_f - P_f = Z_g - P_g.\]
:::

```{=tex}
\todo[inline]{Prove}
```
::: {.corollary title="Open Mapping"}
Any holomorphic non-constant map is an open map.
:::

```{=tex}
\todo[inline]{Prove}
```
::: {.corollary title="Maximum Modulus" ref="MaximumModulus"}
If \( f \) is holomorphic and nonconstant on an open connected region \( \Omega \), then \( {\left\lvert {f} \right\rvert} \) can not attain a maximum on \( \Omega \). If \( \Omega \) is bounded and \( f \) is continuous on \( \mkern 1.5mu\overline{\mkern-1.5mu\Omega\mkern-1.5mu}\mkern 1.5mu \), then \( \max_{\mkern 1.5mu\overline{\mkern-1.5mu\Omega\mkern-1.5mu}\mkern 1.5mu} {\left\lvert {f} \right\rvert} \) occurs on \( {{\partial}}\Omega \). Conversely, if \( f \) attains a local supremum at \( z_0 \in \Omega \), then \( f \) is constant on \( \Omega \).
:::

```{=tex}
\todo[inline]{Prove}
```
### Exercises

![image_2021-05-17-13-33-55](figures/image_2021-05-17-13-33-55.png)

## Complex Log

::: {.proposition title="Existence of complex log"}
Suppose \( \Omega \) is a simply-connected region such that \( 1\in \Omega, 0\not\in\Omega \). Then there exists a branch of \( F(z) \coloneqq\operatorname{Log}(z) \) such that

-   \( F \) is holomorphic on \( \Omega \),
-   \( e^{F(z)} = z \) for all \( z\in \Omega \)
-   \( F(x) = \log(x) \) for \( x\in {\mathbb{R}} \) in a neighborhood of \( 1 \).
:::

::: {.definition title="Principal branch and exponential"}
Take \( {\mathbb{C}} \) and delete \( {\mathbb{R}}^{\leq 0} \) to obtain the **principal branch** of the logarithm, defined as
\[
\operatorname{Log}(z) \coloneqq\log(r) + i\theta && {\left\lvert {\theta} \right\rvert} < \pi
.\]
Similarly define
\[
z^{\alpha} \coloneqq e^{\alpha \operatorname{Log}(z)}
.\]
:::

::: {.theorem title="Existence of log"}
If \( f \) is holomorphic and nonvanishing on a simply-connected region \( \Omega \), then there exists a holomorphic \( G \) on \( \Omega \) such that
\[
f(z) = e^{G(z)}
.\]
:::

# Rouche

## Counting Zeros

::: {.example}
-   Take \( P(z) = z^4 + 6z + 3 \).
-   On \( {\left\lvert {z} \right\rvert} < 2 \):
    -   Set \( f(z) = z^4 \) and \( g(z) = 6z + 3 \), then \( {\left\lvert {g(z)} \right\rvert} \leq 6{\left\lvert {z} \right\rvert} + 3 = 15 < 16= {\left\lvert {f(z)} \right\rvert} \).
    -   So \( P \) has 4 zeros here.
-   On \( {\left\lvert {z} \right\rvert} < 1 \):
    -   Set \( f(z) = 6z \) and \( g(z) = z^4 + 3 \).
    -   Check \( {\left\lvert {g(z)} \right\rvert} \leq {\left\lvert {z} \right\rvert}^4 + 3 = 4 < 6 = {\left\lvert {f(z)} \right\rvert} \).
    -   So \( P \) has 1 zero here.
:::

::: {.example}
-   Claim: the equation \( \alpha z e^z = 1 \) where \( {\left\lvert {\alpha} \right\rvert} > e \) has exactly one solution in \( {\mathbb{D}} \).
-   Set \( f(z) = \alpha z \) and \( g(z) = e^{-z} \).
-   Estimate at \( {\left\lvert {z} \right\rvert} =1 \) we have \( {\left\lvert {g} \right\rvert} ={\left\lvert {e^{-z}} \right\rvert} = e^{-\Re(z)} \leq e^1 < {\left\lvert {\alpha} \right\rvert} = {\left\lvert {f(z)} \right\rvert} \)
-   \( f \) has one zero at \( z_0 = 0 \), thus so does \( f+g \).
:::

# Conformal Maps

## Linear Fractional Transformations

::: {.definition title="Conformal Map / Biholomorphism"}
A map \( f \) is **conformal** on \( \Omega \) iff \( f \) is complex-differentiable, \( f'(z)\neq 0 \) for \( z\in \Omega \), and \( f \) preserves signed angles (so \( f \) is orientation-preserving). Conformal implies holomorphic, and a bijective conformal map has a holomorphic inverse. A bijective conformal map \( f:U\to V \) is called a **biholomorphism**, and we say \( U \) and \( V \) are **biholomorphic**. Self-biholomorphisms of a domain \( \Omega \) form a group \( {\operatorname{Aut}}_{\mathbb{C}}(\Omega) \).
:::

::: {.remark}
There is an oft-used weaker condition that \( f'(z) \neq 0 \) for any point. Note that that this condition alone doesn't necessarily imply \( f \) is holomorphic, since anti-holomorphic maps may be nonzero derivative. For example, take \( f(z) = \mkern 1.5mu\overline{\mkern-1.5muz\mkern-1.5mu}\mkern 1.5mu \), so \( f(x+iy) = x-iy \) -- this does not satisfy the Cauchy-Riemann equations.
:::

::: {.remark}
A bijective holomorphic map automatically has a holomorphic inverse. This can be weakened: an injective holomorphic map satisfies \( f'(z) \neq 0 \) and \( f ^{-1} \) is well-defined on its range and holomorphic.
:::

::: {.definition title="Linear fractional transformation / Mobius transformation"}
A map of the following form is a *linear fractional transformation*:
\[  
T(z) = {az + b \over cz + d}
,\]
where the denominator is assumed to not be a multiple of the numerator. These have inverses given by
\[  
T^{-1}(w) = {dw-b \over -cw + a}
.\]
:::

::: {.proposition title="?"}
Given any three points \( z_1, z_2, z_3 \), the following Mobius transformation sends them to \( 1, 0, \infty \) respectively:
\[
f(z) \coloneqq{ (z-z_2) (z_1-z_3) \over (z-z_3) (z_1 - z_2)}
.\]
Such a map is sometimes denoted \( (z, z_1, z_2, z_3) \).
:::

::: {.example title="?"}
```{=tex}
\envlist
```
-   \( (z, i, 1, -1): {\mathbb{D}}\to {\mathbb{H}} \)
-   \( (z, 0, -1, 1): {\mathbb{D}}\cap{\mathbb{H}}\to Q_1 \).
:::

::: {.theorem title="Cayley Transform"}
The fractional linear transformation given by \( F(z) = {i - z \over i + z} \) maps \( {\mathbb{D}}\to {\mathbb{H}} \) with inverse \( G(w) = i {1-w \over 1 + w} \).
:::

::: {.theorem title="Classification of Conformal Maps"}
There are 8 major types of conformal maps:

  -------------------------------------------------------------------------------------------------------------------------------
  Type/Domains                                                                    Formula
  ------------------------------------------------------------------------------- -----------------------------------------------
  Translation/Dilation/Rotation                                                   \( z\mapsto e^{i\theta}(cz + h) \)

  Sectors to sectors                                                              \( z\mapsto z^n \)

  \( {\mathbb{D}}_{1\over 2} \to {\mathbb{H}}_{1\over 2} \), the first quadrant   \( z\mapsto {1+z \over 1-z} \)

  \( {\mathbb{H}}\to S \)                                                         \( z\mapsto \log(z) \)

  \( {\mathbb{D}}_{1\over 2} \to S_{1\over 2} \)                                  \( z\mapsto \log(z) \)

  \( S_{1\over 2} \to {\mathbb{D}}_{1\over 2} \)                                  \( z\mapsto e^{iz} \)

  \( {\mathbb{D}}_{1\over 2} \to {\mathbb{H}} \)                                  \( z\mapsto {1\over 2}\qty{z + {1\over z}} \)

  \( S_{1\over 2} \to {\mathbb{H}} \)                                             \( z\mapsto \sin(z) \)
  -------------------------------------------------------------------------------------------------------------------------------
:::

::: {.theorem title="Characterization of conformal maps"}
Conformal maps \( {\mathbb{D}}\to{\mathbb{D}} \) have the form
\[
g(z) = \lambda {1-a \over 1 - \mkern 1.5mu\overline{\mkern-1.5mua\mkern-1.5mu}\mkern 1.5mu z}, \quad {\left\lvert {a} \right\rvert} < 1, \quad {\left\lvert {\lambda} \right\rvert} = 1
.\]
:::

## Schwarz

::: {.theorem title="Schwarz Lemma" ref="SchwarzzLemma"}
If \( f: {\mathbb{D}}\to {\mathbb{D}} \) is holomorphic with \( f(0) = 0 \), then

1.  \( {\left\lvert {f(z)} \right\rvert} \leq {\left\lvert {z} \right\rvert} \) for all \( z\in {\mathbb{D}} \)
2.  \( {\left\lvert {f'(0)} \right\rvert} \leq 1 \).

Moreover, if

-   \( {\left\lvert {f(z_0)} \right\rvert} = {\left\lvert {z_0} \right\rvert} \) for any \( z_0\in {\mathbb{D}} \), or
-   \( {\left\lvert {f'(0)} \right\rvert} = 1 \),

then \( f \) is a rotation.
:::

::: {.proof title="?"}
Apply the maximum modulus principle to \( f(z)/z \).
:::

::: {.exercise title="?"}
Show that \( {\operatorname{Aut}}_{\mathbb{C}}({\mathbb{C}}) = \left\{{ z \mapsto az+b{~\mathrel{\Big|}~}a\in {\mathbb{C}}^{\times}, b\in {\mathbb{C}}}\right\} \).
:::

::: {.theorem title="Biholomorphisms of the disc"}
\[
{\operatorname{Aut}}_{\mathbb{C}}({\mathbb{D}}) = \left\{{ z\mapsto e^{i\theta} \qty{\alpha - z \over 1 - \mkern 1.5mu\overline{\mkern-1.5mu\alpha\mkern-1.5mu}\mkern 1.5mu z} }\right\}
.\]
:::

::: {.proof title="?"}
Schwarz lemma.
:::

::: {.theorem title="?"}
\[
{\operatorname{Aut}}_{\mathbb{C}}({\mathbb{H}}) = \left\{{ z \mapsto {az+b \over cz+d} {~\mathrel{\Big|}~}a,b,c,d\in {\mathbb{C}}, ad-bc=1 }\right\} \cong{\operatorname{PSL}}_2({\mathbb{R}})
.\]
:::

## By Type

### Plane to Disc

\[
\phi: {\mathbb{H}}&\to {\mathbb{D}}\\
\phi(z) &= {z - i \over z + i} \qquad f^{-1}(z) = i\qty{1 + w \over 1 - w}
.\]

### Sector to Disc

For \( S_\alpha \coloneqq\left\{{z\in{\mathbb{C}}{~\mathrel{\Big|}~}0 < \arg(z) < \alpha }\right\} \) an open sector for \( \alpha \) some angle, first map the sector to the half-plane:
\[
g: S_\alpha &\to {\mathbb{H}}\\
g(z) &= z^{\pi \over \alpha}
.\]

Then compose with a map \( {\mathbb{H}}\to{\mathbb{D}} \):
\[
f: S_\alpha &\to {\mathbb{D}}\\
f(z) &= (\phi \circ g)(z) = {z^{\pi\over \alpha} - i \over z^{\pi\over\alpha} + i}
.\]

![](figures/image_2020-07-22-13-22-46.png)

### Strip to Disc

-   Map to horizontal strip by rotation \( z\mapsto \lambda z \).
-   Map horizontal strip to sector by \( z \mapsto e^z \)
-   Map sector to \( {\mathbb{H}} \) by \( z\mapsto z^{\pi\over\alpha} \).
-   Map \( {\mathbb{H}}\to{\mathbb{D}} \).

\[
e^z: {\mathbb{R}}\times(0, \pi) \to {\mathbb{R}}\times(0, \infty)
.\]

# Schwarz Reflection

# Linear Fractional Transformations

# Unsorted Theorems

::: {.theorem title="Riemann Mapping"}
If \( \Omega \) is simply connected, nonempty, and not \( {\mathbb{C}} \), then for every \( z_{0}\in \Omega \) there exists a unique conformal map \( F:\Omega \to {\mathbb{D}} \) such that \( F(z_{0}) = 0 \) and \( F'(z_{0}) > 0 \).

Thus any two such sets \( \Omega_{1}, \Omega_{2} \) are conformally equivalent.
:::

::: {.theorem title="Riemann's Removable Singularity Theorem"}
If \( f \) is holomorphic on \( \Omega \) except possibly at \( z_0 \) and \( f \) is bounded on \( \Omega\setminus\left\{{z_0}\right\} \), then \( z_0 \) is a removable singularity.
:::

::: {.theorem title="Little Picard"}
If \( f:{\mathbb{C}}\to {\mathbb{C}} \) is entire and nonconstant, then \( \operatorname{im}(f) \) is either \( {\mathbb{C}} \) or \( {\mathbb{C}}\setminus\left\{{z_0}\right\} \) for some point \( z_0 \).
:::

```{=tex}
\todo{???}
```
::: {.corollary}
The ring of holomorphic functions on a domain in \( {\mathbb{C}} \) has no zero divisors.
:::

::: {.proof}
???
:::

```{=tex}
\todo[inline]{Find the proof!}
```
Morera

::: {.proposition title="Bounded Complex Analytic Functions form a Banach Space"}
For \( \Omega\subseteq{\mathbb{C}} \), show that \( A({\mathbb{C}})\coloneqq\left\{{f: \Omega \to {\mathbb{C}}{~\mathrel{\Big|}~}f\text{ is bounded}}\right\} \) is a Banach space.
:::

::: {.proof}
?

> Apply Morera's Theorem and Cauchy's Theorem
:::

# Appendix: Proofs of the Fundamental Theorem of Algebra

### Fundamental Theorem of Algebra: Argument Principle

-   Let \( P(z) = a_nz^n + \cdots + a_0 \) and \( g(z) = P'(z)/P(z) \), note \( P \) is holomorphic
-   Since \( \lim_{{\left\lvert {z} \right\rvert} \to \infty} P(z) = \infty \), there exist an \( R>0 \) such that \( P \) has no roots in \( \left\{{{\left\lvert {z} \right\rvert} \geq R}\right\} \).
-   Apply the argument principle: `\begin{align*}
    N(0) = {1\over 2\pi i} \oint_{{\left\lvert {\xi} \right\rvert} = R} g(\xi) \,d\xi
    .\end{align*}`{=tex}
-   Check that \( \lim_{{\left\lvert {z\to \infty} \right\rvert}}zg(z) = n \), so \( g \) has a simple pole at \( \infty \)
-   Then \( g \) has a Laurent series \( {n\over z} + {c_2 \over z^2} + \cdots \)
-   Integrate term-by-term to get \( N(0) = n \).

### Fundamental Theorem of Algebra: Rouche's Theorem

-   Let \( P(z) = a_nz^n + \cdots + a_0 \)
-   Set \( f(z) = a_n z^n \) and \( g(z) = P(z) - f(z) = a_{n-1}z^{n-1} + \cdots + a_0 \), so \( f+g = P \).
-   Choose \( R > \max\qty{ { {\left\lvert {a_{n-1}} \right\rvert} + \cdots + {\left\lvert {a_0} \right\rvert} \over {\left\lvert {a_n} \right\rvert} }, 1} \), then

`\begin{align*}
|g(z)| 
&\coloneqq|a_{n-1}z^{n-1} + \cdots + a_1 z + a_0 | \\
&\leq |a_{n-1}z^{n-1}| + \cdots + |a_1 z| + |a_0 | \quad\text{by the triangle inequality} \\
&= |a_{n-1}|\cdot |z^{n-1}| + \cdots + |a_1|\cdot| z| + |a_0 | \\
&=  |a_{n-1}|\cdot R^{n-1} + \cdots + |a_1| R + |a_0 | \\
&\leq |a_{n-1}|\cdot R^{n-1}+|a_{n-2}|\cdot R^{n-1} + \cdots + |a_1| \cdot R^{n-1} + |a_0 |\cdot R^{n-1} \quad\text{since } R>1 \implies R^{a+b} \geq R^a \\
&= R^{n-1} \left( |a_{n-1}| + |a_{n-2}| + \cdots + |a_1| + |a_0| \right) \\
&\leq R^{n-1} \left( |a_n|\cdot R \right) \quad\text{by choice of } R   \\
&= R^{n} |a_n| \\
&= |a_n z^n| \\
&\coloneqq|f(z)|
\end{align*}`{=tex}

-   Then \( a_n z^n \) has \( n \) zeros in \( {\left\lvert {z} \right\rvert} < R \), so \( f+g \) also has \( n \) zeros.

### Fundamental Theorem of Algebra: Liouville's Theorem

-   Suppose \( p \) is nonconstant and has no roots, then \( {1\over p} \) is entire. We will show it is also bounded and thus constant, a contradiction.
-   Write \( p(z) = z^n \left(a_n + \frac{a_{n-1}}{z}+\dots+\frac{a_{0}}{z^{n}}\right) \)
-   Outside a disc:
    -   Note that \( p(z) \overset{z\to \infty }\to \infty \). so there exists an \( R \) large enough such that \( {\left\lvert {p(z)} \right\rvert} \geq {1\over A} \) for any fixed chosen constant \( A \).
    -   Then \( {\left\lvert { 1/p(z)} \right\rvert} \leq A \) outside of \( {\left\lvert {z} \right\rvert} >R \), i.e. \( 1/p(z) \) is bounded there.
-   Inside a disc:
    -   \( p \) is continuous with no roots and thus must be bounded below on \( {\left\lvert {z} \right\rvert} < R \).
    -   \( p \) is entire and thus continuous, and since \( \mkern 1.5mu\overline{\mkern-1.5muD\mkern-1.5mu}\mkern 1.5mu_r(0) \) is a compact set, \( p \) achieves a min \( A \) there
    -   Set \( C \coloneqq\min(A, B) \), then \( {\left\lvert {p(z)} \right\rvert} \geq C \) on all of \( {\mathbb{C}} \) and thus \( {\left\lvert {1/p(z)} \right\rvert} \leq C \) everywhere.
    -   So \( 1/p(z) \) is bounded an entire and thus constant by Liouville's theorem -- but this forces \( p \) to be constant. \( \contradiction \)

### Fundamental Theorem of Algebra: Open Mapping Theorem

-   \( p \) induces a continuous map \( {\mathbb{CP}}^1 \to {\mathbb{CP}}^1 \)
-   The continuous image of compact space is compact;
-   Since the codomain is Hausdorff space, the image is closed.
-   \( p \) is holomorphic and non-constant, so by the Open Mapping Theorem, the image is open.
-   Thus the image is clopen in \( {\mathbb{CP}}^1 \).
-   The image is nonempty, since \( p(1) = \sum a_i \in {\mathbb{C}} \)
-   \( {\mathbb{CP}}^1 \) is connected
-   But the only nonempty clopen subset of a connected space is the entire space.
-   So \( p \) is surjective, and \( p^{-1}(0) \) is nonempty.
-   So \( p \) has a root.

# Appendix

## Misc Basic Algebra

::: {.fact title="Standard forms of conic sections"}
```{=tex}
\envlist
```
-   Circle: \( x^2 + y^2 = r^2 \)
-   Ellipse: \( \qty{\frac x a}^2 + \qty{\frac y b}^2 = 1 \)
-   Hyperbola: \( \qty{\frac x a}^2 - \qty{\frac y b}^2 = 1 \)
    -   Rectangular Hyperbola: \( xy = \frac{c^2}{2} \).
-   Parabola: \( -4ax + y^2 = 0 \).

Mnemonic: Write \( f(x, y) = Ax^2 + Bxy + Cy^2 + \cdots \), then consider the discriminant \( \Delta = B^2 - 4AC \):

-   \( \Delta < 0 \iff \) ellipse
    -   \( \Delta < 0 \) and \( A=C, B=0 \iff \) circle
-   \( \Delta = 0 \iff \) parabola
-   \( \Delta > 0 \iff \) hyperbola
:::

::: {.fact title="Completing the square"}
\[
x^2 - bx = (x - s)^2 - s^2 \quad\text{where} s = \frac{b}{2} \\
x^2 + bx = (x + s)^2 - s^2 \quad\text{where} s = \frac{b}{2}
.\]
:::

::: {.fact}
The sum of the interior angles of an \( n{\hbox{-}} \)gon is \( (n-2)\pi \), where each angle is \( \frac{n-2}{n}\pi \).
:::

::: {.definition title="The Dirichlet Problem"}
Given a bounded piecewise continuous function \( u:S^1\to {\mathbb{R}} \), is there a unique extension to a continuous harmonic function \( \tilde u: {\mathbb{D}}\to {\mathbb{R}} \)?
:::

::: {.remark}
More generally, this is a boundary value problem for a region where the *values* of the function on the boundary are given. Compare to prescribing conditions on the normal vector on the boundary, which would be a Neumann BVP. Why these show up: a harmonic function on a simply connected region has a harmonic conjugate, and solutions of BVPs are always analytic functions with harmonic real/imaginary parts.
:::

::: {.example title="Dirichlet problem on the strip"}
See section 27, example 1 in Brown and Churchill. On the strip \( (x, y)\in (0, \pi) \times(0, \infty) \), set up the BVP for temperature on a thin plate with no sinks/sources:
\[
\Laplacian T = 0 && T(0, y) = 0,\, T(\pi, y) = 0 \,\,\forall y \\ \\
T(x, 0) = \sin(x) && T(x, y) \overset{y\to\infty}\longrightarrow 0
.\]

Then the following function is harmonic on \( {\mathbb{R}}^2 \) and satisfies that Dirichlet problem:
\[
T(x ,y) = e^{-y} \sin(x) = \Re(-ie^{iz}) = \Im(e^{iz})
.\]
:::

::: {.definition title="Logarithmic Derivative"}
The **logarithmic derivative** of \( f \) is \( (\ln f)' = f'/f \).
:::

::: {.remark}
Why this is useful: deriving the argument principle. If \( f \) has a pole of order \( n \) at \( z_0 \), then write \( f(z) = (z-z_0)^{-n} g(z) \) with \( g \) analytic in a neighborhood of \( z_0 \). Then a direct computation of the derivatives will show
\[
(\ln f)' \coloneqq{f'(z) \over f(z)} = -{n\over z-z_0} + {g'(z) \over g(z)}
.\]
Thus
\[
{1\over 2\pi i } \int_\gamma (\ln f)' = -n
,\]
for \( \gamma \) a small circle about \( z_0 \). A similar argument for \( z_0 \) a **zero** of \( f \) yields
\[
{1\over 2\pi i } \int_\gamma h = +n
.\]
:::

::: {.exercise title="?"}
Show that there is no continuous square root function defined on all of \( {\mathbb{C}} \).
:::

::: {.solution}
Suppose \( f(z)^2 = z \). Then \( f \) is a section to the covering map
\[
p: {\mathbb{C}}^{\times}&\to {\mathbb{C}}^{\times}\\
z & \mapsto z^2
,\]
so \( p\circ f = \operatorname{id} \). Using \( \pi_1({\mathbb{C}}^{\times}) = {\mathbb{Z}} \), the induced maps are \( p_*(1) = 2 \) and \( f_*(1) = n \) for some \( n\in {\mathbb{Z}} \). But then \( p_* \circ f_* \) is multiplication by \( 2n \), contradicting \( p_* \circ f_* = \operatorname{id} \) by functoriality.
:::

Basics

-   Show that \( {1\over z} \sum_{k=1}^\infty {z^k \over k} \) converges on \( S^1 \setminus\left\{{1}\right\} \) using summation by parts.
-   Show that any power series is continuous on its domain of convergence.
-   Show that a uniform limit of continuous functions is continuous.

??

-   Show that if \( f \) is holomorphic on \( {\mathbb{D}} \) then \( f \) has a power series expansion that converges uniformly on every compact \( K\subset {\mathbb{D}} \).

-   Show that any holomorphic function \( f \) can be uniformly approximated by polynomials.

-   Show that if \( f \) is holomorphic on a connected region \( \Omega \) and \( f'\equiv 0 \) on \( \Omega \), then \( f \) is constant on \( \Omega \).

-   Show that if \( {\left\lvert {f} \right\rvert} = 0 \) on \( {{\partial}}\Omega \) then either \( f \) is constant or \( f \) has a zero in \( \Omega \).

-   Show that if \( \left\{{f_n}\right\} \) is a sequence of holomorphic functions converging uniformly to a function \( f \) on every compact subset of \( \Omega \), then \( f \) is holomorphic on \( \Omega \) and \( \left\{{f_n'}\right\} \) converges uniformly to \( f' \) on every such compact subset.

-   Show that if each \( f_n \) is holomorphic on \( \Omega \) and \( F \coloneqq\sum f_n \) converges uniformly on every compact subset of \( \Omega \), then \( F \) is holomorphic.

-   Show that if \( f \) is once complex differentiable at each point of \( \Omega \), then \( f \) is holomorphic.

# Draft of Problem Book

-   Prove the triangle inequality
-   Prove the reverse triangle inequality
-   Show that \( \sum z^{k-1}/k \) converges for all \( z\in S^1 \) except \( z=1 \).
-   What is an example of a noncontinuous limit of continuous functions?
-   Show that the uniform limit of continuous functions is continuous.
-   Show that \( f \) is holomorphic if and only if \( \mkern 1.5mu\overline{\mkern-1.5mu{\partial}\mkern-1.5mu}\mkern 1.5muf = 0 \).
-   Show \( n^{1\over n} \overset{n\to \infty } \to 1 \).
-   Show that if \( f \) is holomorphic with \( f'=0 \) on \( \Omega \) then \( f \) is constant.
-   Show that holomorphic implies analytic.
-   Use Cauchy's inequality to prove Liouville's theorem

::: {.problem title="?"}
What is a pair of conformal equivalences between \( {\mathbb{H}} \) and \( {\mathbb{D}} \)?

::: {.solution}
\[
F: HH &\to {\mathbb{D}}\\
z & \mapsto {i-z \over i+z}
\\
\\
G: {\mathbb{D}}&\to {\mathbb{H}}\\
w &\mapsto i{1-w \over 1 + w}
.\]

> Mnemonic: any point in \( {\mathbb{H}} \) is closer to \( i \) than \( -i \), so \( {\left\lvert {F(z)} \right\rvert} < 1 \).

-   Maps \( {\mathbb{R}}\to S^1\setminus\left\{{-1}\right\} \).
:::
:::

::: {.problem title="?"}
What is conformal equivalence \( {\mathbb{H}}\rightleftharpoons S \coloneqq\left\{{w\in {\mathbb{C}}{~\mathrel{\Big|}~}0 < \arg(w) < \alpha \pi}\right\} \)?

::: {.solution}
\[
f(z) = z^ \alpha
.\]
:::
:::
