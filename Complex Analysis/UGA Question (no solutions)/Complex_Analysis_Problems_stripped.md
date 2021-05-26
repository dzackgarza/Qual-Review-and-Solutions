
# Preface

I'd like to thank the following individuals for their contributions to this document:

-   Edward Azoff, for supplying a problem sheet broken out by topic.
-   Mentzelos Melistas, for explaining and documenting many solutions to these questions.
-   Jingzhi Tie, for supplying many additional problems and solutions.

# Topology and Functions of One Variable (8155a)

## 1 \( \work \) {#work}

Let \( x_0 = a, x_1 = b \), and set
\[  
x_n \coloneqq{x_{n-1} + x_{n-2} \over 2} \quad n\geq 2
.\]

Show that \( \left\{{x_n}\right\} \) is a Cauchy sequence and find its limit in terms of \( a \) and \( b \).

## 2 \( \work \) {#work-1}

Suppose \( f:{\mathbb{R}}\to{\mathbb{R}} \) is continuous and \( \lim_{x\to \pm \infty} f(x) = 0 \). Prove that \( f \) is uniformly continuous.

## 3 \( \work \) {#work-2}

Give an example of a function \( f:{\mathbb{R}}\to {\mathbb{R}} \) that is everywhere differentiable but \( f' \) is not continuous at 0.

## 4 \( \work \) {#work-3}

Suppose \( \left\{{g_n}\right\} \) is a uniformly convergent sequence of functions from \( {\mathbb{R}} \) to \( {\mathbb{R}} \) and \( f:{\mathbb{R}}\to {\mathbb{R}} \) is uniformly continuous. Prove that the sequence \( \left\{{f\circ g_n}\right\} \) is uniformly convergent.

## 5 \( \work \) {#work-4}

Let \( f \) be differentiable on \( [a, b] \). Say that \( f \) is *uniformly differentiable* iff

\[  
\forall \varepsilon > 0,\, \exists \delta > 0 \text{ such that } \quad {\left\lvert {x-y} \right\rvert} < \delta \implies {\left\lvert { {f(x) - f(y) \over x-y}  - f'(y)} \right\rvert}  < \varepsilon
.\]

Prove that \( f \) is uniformly differentiable on \( [a, b] \iff f' \) is continuous on \( [a, b] \).

## 6 \( \work \) {#work-5}

Suppose \( A, B \subseteq {\mathbb{R}}^n \) are disjoint and compact. Prove that there exist \( a\in A, b\in B \) such that
\[  
{\left\lVert {a - b} \right\rVert} = \inf\left\{{{\left\lVert {x-y} \right\rVert} {~\mathrel{\Big|}~}x\in A,\, y\in B}\right\}
.\]

## 7 \( \work \) {#work-6}

Suppose \( A, B\subseteq {\mathbb{R}}^n \) are connected and not disjoint. Prove that \( A\cup B \) is also connected.

## 8 \( \work \) {#work-7}

Suppose \( \left\{{f_n}\right\}_{n\in {\mathbb{N}}} \) is a sequence of continuous functions \( f_n: [0, 1]\to {\mathbb{R}} \) such that
\[  
f_n(x) \geq f_{n+1}(x) \geq 0 \quad \forall n\in {\mathbb{N}},\, \forall x\in [0, 1]
.\]
Prove that if \( \left\{{f_n}\right\} \) converges pointwise to \( 0 \) on \( [0, 1] \) then it converges to \( 0 \) uniformly on \( [0, 1] \).

## 9 \( \work \) {#work-8}

Show that if \( E\subset [0, 1] \) is uncountable, then there is some \( t\in {\mathbb{R}} \) such that \( E\cap(-\infty ,t) \) and \( E\cap(t, \infty) \) are also uncountable.

# Several Variables (8155h)

## 1 \( \work \) {#work-9}

Is the following function continuous, differentiable, continuously differentiable?
\[  
f: {\mathbb{R}}^2 &\to {\mathbb{R}}\\
f(x, y) &= 
\begin{cases}
{xy \over \sqrt{x^2 + y^2}} & (x, y) \neq (0, 0) \\
0 & \text{else}.
\end{cases}
\]

## 2 \( \work \) {#work-10}

### a \( \work \) {#a-work}

Complete this definition: "\( f: {\mathbb{R}}^n\to {\mathbb{R}}^m \) is real-differentiable a point \( p\in {\mathbb{R}}^n \) iff there exists a linear transformation..."

### b \( \work \) {#b-work}

Give an example of a function \( f:{\mathbb{R}}^2\to {\mathbb{R}} \) whose first-order partial derivatives exist everywhere but \( f \) is not differentiable at \( (0, 0) \).

### c \( \work \) {#c-work}

Give an example of a function \( f: {\mathbb{R}}^2 \to {\mathbb{R}} \) which is real-differentiable everywhere but nowhere complex-differentiable.

## 3 \( \work \) {#work-11}

Let \( f:{\mathbb{R}}^2\to {\mathbb{R}} \).

### a \( \work \) {#a-work-1}

Define in terms of linear transformations what it means for \( f \) to be differentiable at a point \( (a, b) \in {\mathbb{R}}^2 \).

### b \( \work \) {#b-work-1}

State a version of the inverse function theorem in this setting.

### c \( \work \) {#c-work-1}

Identify \( {\mathbb{R}}^2 \) with \( {\mathbb{C}} \) and give a necessary and sufficient condition for a real-differentiable function at \( (a, b) \) to be complex differentiable at the point \( a+ib \).

## 4 \( \work \) {#work-12}

Let \( f = u+iv \) be complex-differentiable with continuous partial derivatives at a point \( z = re^{i\theta} \) with \( r\neq 0 \). Show that
\[  
{\frac{\partial u}{\partial r}\,} = {1\over r}{\frac{\partial v}{\partial \theta}\,} \qquad {\frac{\partial v}{\partial r}\,} = -{1\over r}{\frac{\partial u}{\partial \theta}\,}
.\]

## 5 \( \work \) {#work-13}

Let \( P = (1, 3) \in {\mathbb{R}}^2 \) and define
\[  
f(s, t) \coloneqq ps^3 -6st + t^2
.\]

### a \( \work \) {#a-work-2}

State the conclusion of the implicit function theorem concerning \( f(s, t) = 0 \) when \( f \) is considered a function \( {\mathbb{R}}^2\to{\mathbb{R}} \).

### b \( \work \) {#b-work-2}

State the above conclusion when \( f \) is considered a function \( {\mathbb{C}}^2\to {\mathbb{C}} \).

### c \( \work \) {#c-work-2}

Use the implicit function theorem for a function \( {\mathbb{R}}\times{\mathbb{R}}^2 \to {\mathbb{R}}^2 \) to prove (b).

> There are various approaches: using the definition of the complex derivative, the Cauchy-Riemann equations, considering total derivatives, etc.

## 6 \( \work \) {#work-14}

Let \( F:{\mathbb{R}}^2\to {\mathbb{R}} \) be continuously differentiable with \( F(0, 0) = 0 \) and \( {\left\lVert {\nabla F(0, 0)} \right\rVert} < 1 \).

Prove that there is some real number \( r> 0 \) such that \( {\left\lvert {F(x, y)} \right\rvert} < r \) whenever \( {\left\lVert {(x, y)} \right\rVert} < r \).

## 7 \( \work \) {#work-15}

State the most general version of the implicit function theorem for real functions and outline how it can be proved using the inverse function theorem.

# Several Variables: Extra Questions

## ? {#section}

Let \( f=u+iv \) be differentiable (i.e. \( f'(z) \) exists) with continuous partial derivatives at a point \( z=re^{i\theta} \), \( r\not= 0 \).

Show that
\[
\frac{\partial u}{\partial r}=\frac{1}{r}\frac{\partial v}{\partial \theta},\quad
\frac{\partial v}{\partial r}=-\frac{1}{r}\frac{\partial u}{\partial \theta}
.\]

## ? {#section-1}

Give an example of a

Show that \( f(z) = z^2 \) is uniformly continuous in any open disk \( |z| < R \), where \( R>0 \) is fixed, but it is not uniformly continuous on \( \mathbb C \).

### 1 {#section-2}

Show that the function \( u=u(x,y) \) given by
\[
u(x,y)=\frac{e^{ny}-e^{-ny}}{2n^2}\sin nx\quad \text{for}\ n\in {\mathbf N}
\]
is the solution on \( D=\{(x,y)\ | x^2+y^2<1\} \) of the Cauchy problem for the Laplace equation
\[\frac{\partial ^2u}{\partial x^2}+\frac{\partial ^2u}{\partial y^2}=0,\quad
u(x,0)=0,\quad \frac{\partial u}{\partial y}(x,0)=\frac{\sin nx}{n}.\]

### 2 {#section-3}

Show that there exist points \( (x,y)\in D \) such that \( \displaystyle{\limsup_{n\to\infty} |u(x,y)|=\infty} \).

# Integrals and Cauchy's Theorem (8155d)

> Some interesting problems: 3, 4, 9, 10.

## 1 \( \work \) {#work-16}

Suppose \( f, g: [0, 1] \to {\mathbb{R}} \) where \( f \) is Riemann integrable and for \( x, y\in [0, 1] \),
\[
{\left\lvert {g(x) - g(y)} \right\rvert} \leq {\left\lvert {f(x) - f(y)} \right\rvert}
.\]

Prove that \( g \) is Riemann integrable.

## 2 \( \work \) {#work-17}

State and prove Green's Theorem for rectangles.

Then use it to prove Cauchy's Theory for functions that are analytic in a rectangle.

## 3 \( \work \) {#work-18}

Suppose \( \left\{{f_n}\right\}_{n\in {\mathbb{N}}} \) is a sequence of analytic functions on \( {\mathbb{D}}\coloneqq\left\{{z\in {\mathbb{C}}{~\mathrel{\Big|}~}{\left\lvert {z} \right\rvert} < 1}\right\} \).

Show that if \( f_n\to g \) for some \( g: {\mathbb{D}}\to {\mathbb{C}} \) uniformly on every compact \( K\subset {\mathbb{D}} \), then \( g \) is analytic on \( {\mathbb{D}} \).

## 4 \( \work \) {#work-19}

Suppose \( \left\{{f_n}\right\}_{n\in {\mathbb{N}}} \) is a sequence of entire functions where

-   \( f_n \to g \) pointwise for some \( g:{\mathbb{C}}\to{\mathbb{C}} \).
-   On every line segment in \( {\mathbb{C}} \), \( f_n \to g \) uniformly.

Show that

-   \( g \) is entire, and
-   \( f_n\to g \) uniformly on every compact subset of \( {\mathbb{C}} \).

## 5 \( \done \) {#done}

Prove that there is no sequence of polynomials that uniformly converge to \( f(z) = {1\over z} \) on \( S^1 \).

::: {.solution}
```{=tex}
\hfill
```
::: {.concept}
```{=tex}
\hfill
```
:::

-   By Cauchy's integral formula, \( \int_{S^1} f = 2\pi i \)
-   If \( p_j \) is any polynomial, then \( p_j \) is holomorphic in \( {\mathbb{D}} \), so \( \int_{S^1} p_j = 0 \).
-   Contradiction: compact sets in \( {\mathbb{C}} \) are bounded, so
    \[
    {\left\lvert {\int f - \int p_j} \right\rvert} \leq \int {\left\lvert {p_j - f} \right\rvert} \leq \int {\left\lVert {p_j - f} \right\rVert}_\infty  = {\left\lVert {p_j - f} \right\rVert}_\infty \int_{S^1} 1 \,dz = {\left\lVert {p_j-f} \right\rVert}_\infty \cdot 2\pi \to 0
    \]
    which forces \( \int f = \int p_j = 0 \).
:::

## 6 \( \work \) {#work-20}

Suppose that \( f: {\mathbb{R}}\to{\mathbb{R}} \) is a continuous function that vanishes outside of some finite interval. For each \( z\in {\mathbb{C}} \), define
\[
g(z) = \int_{-\infty}^\infty f(t) e^{-izt} \,dt
.\]

Show that \( g \) is entire.

## 7 \( \work \) {#work-21}

Suppose \( f: {\mathbb{C}}\to {\mathbb{C}} \) is entire and
\[
{\left\lvert {f(z)} \right\rvert} \leq {\left\lvert {z} \right\rvert}^{1\over 2} \quad\text{ when } {\left\lvert {z} \right\rvert} > 10
.\]

Prove that \( f \) is constant.

## 8 \( \work \) {#work-22}

Let \( \gamma \) be a smooth curve joining two distinct points \( a, b\in {\mathbb{C}} \).

Prove that the function
\[
f(z) \coloneqq\int_\gamma {g(w) \over w-z} \,dw
\]
is analytic in \( {\mathbb{C}}\setminus\gamma \).

## 9 \( \done \) {#done-1}

Suppose that \( f: {\mathbb{C}}\to{\mathbb{C}} \) is continuous everywhere and analytic on \( {\mathbb{C}}\setminus {\mathbb{R}} \) and prove that \( f \) is entire.

```{=tex}
\todo[inline]{Something missing?}
```
::: {.solution}
```{=tex}
\hfill
```
::: {.concept}
```{=tex}
\hfill
```
:::

-   Note \( f \) is continuous on \( {\mathbb{C}} \) since analytic implies continuous (\( f \) equals its power series, where the partials sums uniformly converge to it, and uniform limit of continuous is continuous).
-   Strategy: take \( D \) a disc centered at a point \( x\in {\mathbb{R}} \), show \( f \) is holomorphic in \( D \) by Morera's theorem.
-   Let \( \Delta \subset D \) be a triangle in \( D \).
-   Case 1: If \( \Delta \cap{\mathbb{R}}= 0 \), then \( f \) is holomorphic on \( \Delta \) and \( \int_\Delta f = 0 \).
-   Case 2: one side or vertex of \( \Delta \) intersects \( {\mathbb{R}} \), and wlog the rest of \( \Delta \) is in \( {\mathbb{H}}^+ \).
    -   Then let \( \Delta_\varepsilon \) be the perturbation \( \Delta + i\varepsilon= \left\{{z+ i\varepsilon{~\mathrel{\Big|}~}z\in \Delta}\right\} \); then \( \Delta_\varepsilon\cap{\mathbb{R}}= 0 \) and \( \int_{\Delta_\varepsilon} f = 0 \).
    -   Now let \( \varepsilon\to 0 \) and conclude by continuity of \( f \) (???)
        -   We want `\begin{align*}
            \int_{\Delta_\varepsilon} f = \int_a^b f(\gamma_\varepsilon(t)) \gamma_\varepsilon'(t)\,dt \overset{\varepsilon\to 0}\to \int_a^b f(\gamma(t)) \gamma_\varepsilon'(t)\,dt =\int_{\Delta}  f
            \end{align*}`{=tex} where \( \gamma_\varepsilon, \gamma \) are curves parametrizing \( \Delta_\varepsilon, \Delta \) respectively.
        -   Since \( \gamma, \gamma_\varepsilon \) are closed and bounded in \( {\mathbb{C}} \), they are compact subsets. Thus it suffices to show that \( f(\gamma_\varepsilon(t)) \gamma_\varepsilon'(t) \) converges uniformly to \( f(\gamma(t))\gamma'(t) \).
        -   ??
-   Case 3: \( \Delta \) intersects both \( {\mathbb{H}}^+ \) and \( {\mathbb{H}}^- \).
    -   Break into smaller triangles, each of which falls into one of the previous two cases.
:::

## 10 \( \done \) {#done-2}

Prove Liouville's theorem: suppose \( f:{\mathbb{C}}\to{\mathbb{C}} \) is entire and bounded. Use Cauchy's formula to prove that \( f'\equiv 0 \) and hence \( f \) is constant.

::: {.solution}
```{=tex}
\hfill
```
::: {.concept}
```{=tex}
\hfill
```
:::

-   Suffices to prove \( f' = 0 \) because \( {\mathbb{C}} \) is connected (see Stein Ch 1, 3.4)
    -   Idea: Fix \( w_0 \), show \( f(w) = f(w_0) \) for any \( w\neq w_0 \)
    -   Connected = Path connected in \( {\mathbb{C}} \), so take \( \gamma \) joining \( w \) to \( w_0 \).
    -   \( f \) is a primitive for \( f' \), and \( \int_\gamma f' = f(w) - f(w_0) \), but \( f'=0 \).
-   Fix \( z_0\in {\mathbb{C}} \), let \( B \) be the bound for \( f \), so \( {\left\lvert {f(z)} \right\rvert} \leq B \) for all \( z \).
-   Apply Cauchy inequalities: if \( f \) is holomorphic on \( U\supset \mkern 1.5mu\overline{\mkern-1.5muD\mkern-1.5mu}\mkern 1.5mu_R(z_0) \) then setting \( {\left\lVert {f} \right\rVert}_C \coloneqq\sup_{z\in C} {\left\lvert {f(z)} \right\rvert} \), `\begin{align*}
    {\left\lvert {f^{(n)} (z_0)} \right\rvert} \leq {n! {\left\lVert {f} \right\rVert}_C \over R^n}
    .\end{align*}`{=tex}
    -   Yields \( {\left\lvert { f'(z_0) } \right\rvert} \leq B/R \)
-   Take \( R\to \infty \), QED.
:::

# Extra

## ? {#section-4}

Assume \( f \) is continuous in the region: \( 0< |z-a| \leq R, \; 0 \leq \arg(z-a) \leq \beta_0 \) (\( 0 < \beta_0 \leq 2 \pi \)) and the limit \( \displaystyle \lim_{z \rightarrow a} (z-a) f(z) = A \) exists. Show that
\[\lim_{r \rightarrow 0} \int_{\gamma_r} f(z) dz  = i A \beta_0 \; , \; \;\]
where \( \gamma_r : = \{ z \; | \; z = a + r e^{it}, \; 0 \leq t \leq \beta_0 \}. \)

# Liouville's Theorem, Power Series (8155e)

## 1 \( \done \) {#done-3}

Suppose \( f \) is analytic on a region \( \Omega \) such that \( {\mathbb{D}}\subseteq \Omega \subseteq {\mathbb{C}} \) and \( f(z) = \sum_{n=0}^\infty a_n z^n \) is a power series with radius of convergence exactly 1.

### a \( \done \) {#a-done}

Give an example of such an \( f \) that converges at every point of \( S^1 \).

### b \( \work \) {#b-work-3}

Give an example of such an \( f \) which is analytic at \( 1 \) but \( \sum_{n=0}^\infty a_n \) diverges.

### c \( \work \) {#c-work-3}

Prove that \( f \) can not be analytic at *every* point of \( S^1 \).

```{=tex}
\todo[inline]{Missing part (c)}
```
::: {.solution}
```{=tex}
\hfill
```
::: {.concept}
```{=tex}
\hfill
```
:::

### a \( \done \) {#a-done-1}

-   Take \( \sum {z^n \over n^2} \)
-   Then
    \[{\left\lvert {z} \right\rvert}\leq 1 \implies {\left\lvert {z^n\over n^2} \right\rvert} \leq {1\over n^2}\]
    which is summable
-   So the series converges for \( {\left\lvert {z} \right\rvert}\leq 1 \).

### b \( \work \) {#b-work-4}

-   Take \( \sum {z^n \over n} \);

-   Then \( z=1 \) yields the harmonic series, which diverges.

-   For \( z\in S^1\setminus\left\{{1}\right\} \), we have \( z = e^{2\pi it} \) for \( 0<t<2\pi \).

-   So fix \( t \).

-   Toward applying the Dirichlet test, set \( a_n = 1/n, b_n = z^n \).

-   Then for all \( N \),
    \[
    {\left\lvert {\sum_{n=1}^N b_n} \right\rvert}
    = {\left\lvert {\sum_{n=1}^N b_n} \right\rvert}
    = {\left\lvert {\sum_{n=1}^N z^n} \right\rvert}
    = {\left\lvert {  {z-z^{N+1} \over {\left\lvert {1 - z} \right\rvert}} } \right\rvert} 
    \leq {2 \over 1-z} < \infty
    .\]

-   Thus \( \sum a_n b_n < \infty \) and \( \sum z^n/n \) converges.

c.  ?
:::

## 2 \( \work \) {#work-23}

Suppose \( f \) is entire and has Taylor series \( \sum a_n z^n \) about 0.

### a \( \work \) {#a-work-3}

Express \( a_n \) as a contour integral along the circle \( {\left\lvert {z} \right\rvert} = R \).

### b \( \work \) {#b-work-5}

Apply (a) to show that the above Taylor series converges uniformly on every bounded subset of \( {\mathbb{C}} \).

### c \( \work \) {#c-work-4}

Determine those functions \( f \) for which the above Taylor series converges uniformly on all of \( {\mathbb{C}} \).

## 3 \( \work \) {#work-24}

Suppose \( D \) is a domain and \( f, g \) are analytic on \( D \).

Prove that if \( fg = 0 \) on \( D \), then either \( f \equiv 0 \) or \( g\equiv 0 \) on \( D \).

## 4 \( \work \) {#work-25}

Suppose \( f \) is analytic on \( {\mathbb{D}}^\circ \). Determine with proof which of the following are possible:

a.  \( f\qty{1\over n} = (-1)^n \) for each \( n>1 \).

b.  \( f\qty{1\over n} = e^{-n} \) for each even integer \( n>1 \) while \( f\qty{1\over n} = 0 \) for each odd integer \( n>1 \).

c.  \( f\qty{1\over n^2} = {1\over n} \) for each integer \( n>1 \).

d.  \( f\qty{1\over n} = {n-2 \over n-1} \) for each integer \( n>1 \).

## 5 \( \done \) {#done-4}

Prove the Fundamental Theorem of Algebra (using complex analysis).

::: {.solution}
```{=tex}
\hfill
```
::: {.concept}
```{=tex}
\hfill
```
:::

-   Strategy: By contradiction with Liouville's Theorem
-   Suppose \( p \) is non-constant and has no roots.
-   Claim: \( 1/p(z) \) is a bounded holomorphic function on \( {\mathbb{C}} \).
    -   Holomorphic: clear? Since \( p \) has no roots.

    -   Bounded: for \( z\neq 0 \), write `\begin{align*}
        \frac{P(z)}{z^{n}}=a_{n}+\left(\frac{a_{n-1}}{z}+\cdots+\frac{a_{0}}{z^{n}}\right)
        .\end{align*}`{=tex}

    -   The term in parentheses goes to 0 as \( {\left\lvert {z} \right\rvert}\to \infty \)

    -   Thus there exists an \( R>0 \) such that `\begin{align*}
        {\left\lvert {z} \right\rvert} > R \implies {\left\lvert {P(z) \over z^n} \right\rvert} \geq c \coloneqq{{\left\lvert {a_n} \right\rvert} \over 2}
        .\end{align*}`{=tex}

    -   So \( p \) is bounded below when \( {\left\lvert {z} \right\rvert} > R \)

    -   Since \( p \) is continuous and has no roots in \( {\left\lvert {z} \right\rvert} \leq R \), it is bounded below when \( {\left\lvert {z} \right\rvert} \leq R \).

    -   Thus \( p \) is bounded below on \( {\mathbb{C}} \) and thus \( 1/p \) is bounded above on \( {\mathbb{C}} \).
-   By Liouville's theorem, \( 1/p \) is constant and thus \( p \) is constant, a contradiction.
:::

## 6 \( \done \) {#done-5}

Find all entire functions that satisfy
\[
{\left\lvert {f(z)} \right\rvert} \geq {\left\lvert {z} \right\rvert} \quad \forall z\in {\mathbb{C}}
.\]
Prove this list is complete.

::: {.solution}
```{=tex}
\hfill
```
::: {.concept}
```{=tex}
\hfill
```
:::

-   Suppose \( f \) is entire and define \( g(z) \coloneqq{z \over f(z)} \).
-   By the inequality, \( {\left\lvert {g(z)} \right\rvert} \leq 1 \), so \( g \) is bounded.
-   \( g \) potentially has singularities at the zeros \( Z_f \coloneqq f^{-1}(0) \), but since \( f \) is entire, \( g \) is holomorphic on \( {\mathbb{C}}\setminus Z_f \).
-   Claim: \( Z_f = \left\{{0}\right\} \).
    -   If \( f(z) = 0 \), then \( {\left\lvert {z} \right\rvert} \leq {\left\lvert {f(z)} \right\rvert} = 0 \) which forces \( z=0 \).
-   We can now apply Riemann's removable singularity theorem:
    -   Check \( g \) is bounded on some open subset \( D\setminus\left\{{0}\right\} \), clear since it's bounded everywhere
    -   Check \( g \) is holomorphic on \( D\setminus\left\{{0}\right\} \), clear since the only singularity of \( g \) is \( z=0 \).
-   By Riemann's removable singularity theorem, the singularity \( z = 0 \) is removable and \( g \) has an extension to an entire function \( \tilde g \).
-   By continuity, we have \( {\left\lvert {\tilde g(z)} \right\rvert} \leq 1 \) on all of \( {\mathbb{C}} \)
    -   If not, then \( {\left\lvert {\tilde g(0)} \right\rvert} = 1+\varepsilon> 1 \), but then there would be a domain \( \Omega \subseteq {\mathbb{C}}\setminus\left\{{0}\right\} \) such that \( 1 < {\left\lvert {\tilde g(z)} \right\rvert} \leq 1 +\varepsilon \) on \( \Omega \), a contradiction.
-   By Liouville, \( \tilde g \) is constant, so \( \tilde g(z) = c_0 \) with \( {\left\lvert {c_0} \right\rvert} \leq 1 \)
-   Thus \( f(z) = c_0^{-1}z \coloneqq cz \) where \( {\left\lvert {c} \right\rvert}\geq 1 \)

Thus all such functions are of the form \( f(z) = cz \) for some \( c\in {\mathbb{C}} \) with \( {\left\lvert {c} \right\rvert}\geq 1 \).
:::

## 7 \( \work \) {#work-26}

Suppose \( \sum_{n=0}^\infty a_n z^n \) converges for some \( z_0 \neq 0 \).

### a \( \work \) {#a-work-4}

Prove that the series converges absolutely for each \( z \) with \( {\left\lvert {z} \right\rvert} < {\left\lvert {z} \right\rvert}_0 \).

### b \( \work \) {#b-work-6}

Suppose \( 0 < r < {\left\lvert {z_0} \right\rvert} \) and show that the series converges uniformly on \( {\left\lvert {z} \right\rvert} \leq r \).

## 8 \( \work \) {#work-27}

Suppose \( f \) is entire and suppose that for some integer \( n\geq 1 \),
\[
\lim_{z\to \infty} {f(z) \over z^n} = 0
.\]

Prove that \( f \) is a polynomial of degree at most \( n-1 \).

## 9 \( \work \) {#work-28}

Find all entire functions satisfying
\[
{\left\lvert {f(z)} \right\rvert} \leq {\left\lvert {z} \right\rvert}^{1\over 2} \quad\text{ for } {\left\lvert {z} \right\rvert} > 10
.\]

## 10 \( \work \) {#work-29}

Prove that the following series converges uniformly on the set \( \left\{{z {~\mathrel{\Big|}~}\Im(z) < \ln 2}\right\} \):
\[
\sum_{n=1}^\infty {\sin(nz) \over 2^n}
.\]

# Extra

## ? {#section-5}

Let \( f(z) \) be entire and assume values of \( f(z) \) lie outside a *bounded* open set \( \Omega \). Show without using Picard's theorems that \( f(z) \) is a constant.

Let \( f(z) \) be entire and assume values of \( f(z) \) lie outside a *bounded* open set \( \Omega \).

Show without using Picard's theorems that \( f(z) \) is a constant.

## ? {#section-6}

### 1 {#section-7}

Assume \( \displaystyle f(z) = \sum_{n=0}^\infty c_n z^n \) converges in \( |z| < R \).

Show that for \( r <R \),
\[
\frac{1}{2 \pi} \int_0^{2 \pi} |f(r e^{i \theta})|^2 d \theta = \sum_{n=0}^\infty |c_n|^2 r^{2n}
.\]

### 2 {#section-8}

Deduce Liouville's theorem from (1).

# Laurent Expansions and Singularities (8155f)

## 1 \( \done \) {#done-6}

Find the Laurent expansion of
\[
f(z) = {z + 1 \over z(z-1)}
\]
about \( z=0 \) and \( z=1 \) respectively.

::: {.solution}
```{=tex}
\hfill
```
::: {.concept}
```{=tex}
\hfill
```
:::

Let \( f(z) = {z+1\over z(z-1)} \).

About \( z=0 \):

`\begin{align*}
f(z) 
&= (z+1) \qty{- {1 \over z} + {1\over z-1} } \\
&=  -(z+1) \qty{{1\over z} + \sum_{n=0}^\infty z^n } \\
&= -(z+1)\sum_{n=-1}^\infty z^n \\
&= {1\over z} + 2\sum_{n=0}^\infty z^n \\
&= -{1\over z} -2 - 2z - 2z^2 - \cdots
.\end{align*}`{=tex}

About \( z=1 \):

`\begin{align*}
f(z) 
&= \qty{(1-z) -2 \over 1-z} \qty{1 \over 1 - (1-z)} \\
&= \qty{1 - {2\over 1-z}} \sum_{n=0}^\infty (1-z)^n \\ 
&= \sum_{n=0}^\infty (1-z)^n - 2 \sum_{n=-1}^\infty (1-z)^n \\
&= -{2\over 1-z} - \sum_{n=0}^\infty (1-z)^n \\
&= {2\over z-1} + \sum_{n=0}^\infty (-1)^{n+1} (z-1)^n \\
&= {2\over z-1} - 1 + (z-1) - (z-1)^2 + \cdots
.\end{align*}`{=tex}
:::

## 2 \( \done \) {#done-7}

Find the Laurent expansions about \( z=0 \) of the following functions:
\[
e^{1\over z} \hspace{8em} \cos \qty{1\over z}
.\]

::: {.solution}
```{=tex}
\hfill
```
::: {.concept}
```{=tex}
\hfill
```
:::

Let \( f(z) = {z+1\over z(z-1)} \).

About \( z=0 \):

`\begin{align*}
f(z) 
&= (z+1) \qty{- {1 \over z} + {1\over z-1} } \\
&=  -(z+1) \qty{{1\over z} + \sum_{n=0}^\infty z^n } \\
&= -(z+1)\sum_{n=-1}^\infty z^n \\
&= {1\over z} + 2\sum_{n=0}^\infty z^n \\
&= -{1\over z} -2 - 2z - 2z^2 - \cdots
.\end{align*}`{=tex}

About \( z=1 \):

`\begin{align*}
f(z) 
&= \qty{(1-z) -2 \over 1-z} \qty{1 \over 1 - (1-z)} \\
&= \qty{1 - {2\over 1-z}} \sum_{n=0}^\infty (1-z)^n \\ 
&= \sum_{n=0}^\infty (1-z)^n - 2 \sum_{n=-1}^\infty (1-z)^n \\
&= -{2\over 1-z} - \sum_{n=0}^\infty (1-z)^n \\
&= {2\over z-1} + \sum_{n=0}^\infty (-1)^{n+1} (z-1)^n \\
&= {2\over z-1} - 1 + (z-1) - (z-1)^2 + \cdots
.\end{align*}`{=tex}
:::

## 3 \( \work \) {#work-30}

Find the Laurent expansion of
\[
f(z) = {z+1 \over z(z-1)^2}
\]
about \( z=0 \) and \( z=1 \) respectively.

> Hint: recall that power series can be differentiated.

## 4 \( \work \) {#work-31}

For the following functions, find the Laurent series about \( 0 \) and classify their singularities there:
\[
{\sin^2(z) \over z} \\
z \exp{1\over z^2} \\
{1 \over z(4-z)}
.\]

## 5 \( \work \) {#work-32}

Find all entire functions with have poles at \( \infty \).

## 6 \( \work \) {#work-33}

Find all functions on the Riemann sphere that have a simple pole at \( z=2 \) and a double pole at \( z=\infty \), but are analytic elsewhere.

## 7 \( \work \) {#work-34}

Let \( f \) be entire, and discuss (with proofs and examples) the types of singularities \( f \) might have (removable, pole, or essential) at \( z=\infty \) in the following cases:

1.  \( f \) has at most finitely many zeros in \( {\mathbb{C}} \).
2.  \( f \) has infinitely many zeros in \( {\mathbb{C}} \).

## 8 \( \work \) {#work-35}

Define
\[
f(z) &= {\pi^2 \over \sin^2 \qty{\pi z} } \\
g(z) &= \sum_{n\in {\mathbb{Z}}} {1\over (z-n)^2}
.\]

a.  Show that \( f \) and \( g \) have the same singularities in \( {\mathbb{C}} \).
b.  Show that \( f \) and \( g \) have the same singular parts at each of their singularities.
c.  Show that \( f, g \) each have period one and approach zero uniformly on \( 0\leq x \leq 1 \) as \( {\left\lvert {y} \right\rvert}\to \infty \).
d.  Conclude that \( f = g \).

```{=tex}
\todo[inline]{Not finished.}
```
::: {.solution}
```{=tex}
\hfill
```
::: {.concept}
```{=tex}
\hfill
```
Idea: show their \( f-g \) is analytic by taking away all of the negative powers, and bounded by (c).
:::
:::

# Conformal Maps (8155c)

> Notation: \( {\mathbb{D}} \) is the open unit disc, \( {\mathbb{H}} \) is the open upper half-plane.

## 1 \( \work \) {#work-36}

Find a conformal map from \( {\mathbb{D}} \) to \( {\mathbb{H}} \).

## 2 \( \work \) {#work-37}

Find a conformal map from the strip \( \left\{{z\in {\mathbb{C}}{~\mathrel{\Big|}~}0 < \Im(z) < 1}\right\} \) to \( {\mathbb{H}} \).

## 3 \( \work \) {#work-38}

Find a fractional linear transformation \( T \) which maps \( {\mathbb{H}} \) to \( {\mathbb{D}} \), and explicitly describe the image of the first quadrant under \( T \).

## 4 \( \work \) {#work-39}

Find a conformal map from \( \left\{{z\in {\mathbb{C}}{~\mathrel{\Big|}~}{\left\lvert {z-i} \right\rvert} > 1,\, \Re(z) > 0}\right\} \) to \( {\mathbb{H}} \).

## 5 \( \work \) {#work-40}

Find a conformal map from \( \left\{{z\in {\mathbb{C}}{~\mathrel{\Big|}~}{\left\lvert {z} \right\rvert} < 1,\, {\left\lvert {z - {1\over 2}} \right\rvert} > {1\over 2} }\right\} \) to \( {\mathbb{D}} \).

## 6 \( \work \) {#work-41}

Find a conformal map from \( \left\{{{\left\lvert {z-1} \right\rvert} < 2}\right\} \cap\left\{{{\left\lvert {z+1} \right\rvert} < 2}\right\} \) to \( {\mathbb{H}} \).

## 7 \( \work \) {#work-42}

Let \( \Omega \) be the region inside the unit circle \( {\left\lvert {z} \right\rvert} = 1 \) and outside the circle \( {\left\lvert {z-{1\over 4}} \right\rvert} = {1\over 4} \).

Find an injective conformal map from \( \Omega \) onto some annulus \( \left\{{r < {\left\lvert {z} \right\rvert} < 1}\right\} \) for constant \( r \).

## 8 \( \work \) {#work-43}

Let \( D \) be the region obtained by deleting the real interval \( [0, 1) \) from \( {\mathbb{D}} \); find a conformal map from \( D \) to \( {\mathbb{D}} \).

## 9 \( \work \) {#work-44}

Find a conformal map from \( {\mathbb{C}}\setminus\left\{{x\in {\mathbb{R}}{~\mathrel{\Big|}~}x\leq 0}\right\} \) to \( {\mathbb{D}} \).

## 10 \( \work \) {#work-45}

Find a conformal map from \( {\mathbb{C}}\setminus\left\{{x\in {\mathbb{R}}{~\mathrel{\Big|}~}x\geq 1}\right\} \) to \( {\mathbb{D}} \).

## 11 \( \work \) {#work-46}

Find a bijective conformal map from \( G \) to \( {\mathbb{H}} \), where
\[  
G \coloneqq\left\{{z\in {\mathbb{C}}{~\mathrel{\Big|}~}{\left\lvert {z-1} \right\rvert} < \sqrt 2,\, {\left\lvert {z+1} \right\rvert} < \sqrt 2}\right\} \setminus [0, i)
.\]

## 12 \( \work \) {#work-47}

Prove that TFAE for a Möbius transformation \( T \) given by \( T(z) = {az + b \over cz + d} \):

a.  \( T \) maps \( {\mathbb{R}}\cup\left\{{\infty}\right\} \) to itself.
b.  It is possible to choose \( a,b,c,d \) to be real numbers.
c.  \( \mkern 1.5mu\overline{\mkern-1.5muT(z)\mkern-1.5mu}\mkern 1.5mu = T(\mkern 1.5mu\overline{\mkern-1.5muz\mkern-1.5mu}\mkern 1.5mu) \) for every \( z\in {\mathbb{CP}}^1 \).
d.  There exist \( \alpha\in {\mathbb{R}}, \beta \in {\mathbb{C}}\setminus {\mathbb{R}} \) such that \( T(\alpha) = \alpha \) and \( T(\mkern 1.5mu\overline{\mkern-1.5mu\beta\mkern-1.5mu}\mkern 1.5mu) = \mkern 1.5mu\overline{\mkern-1.5muT(\beta)\mkern-1.5mu}\mkern 1.5mu \).

## 13 {#section-9}

Find a conformal map from \( D = \{z :\  |z| < 1,\ |z - 1/2| > 1/2\} \) to the unit disk \( \Delta=\{z: \ |z|<1\} \).

# Residues

## \( \work \) {#work-48}

::: {.problem title="?"}
Calculate
\[
\int_0^\infty {1 \over (1+z)^2 (z+9x^2)} \, dx
.\]
:::

## \( \work \) {#work-49}

::: {.problem title="?"}
Let \( a>0 \) and calculate
\[
\int_0^\infty {x\sin(x) \over x^2 + a^2} \,dx
.\]
:::

## \( \work \) {#work-50}

::: {.problem title="?"}
Calculate
\[
\int_0^\infty {\sqrt x \over (x+1)^2} \,dx
.\]
:::

## \( \work \) {#work-51}

::: {.problem title="?"}
Calculate
\[
\int_0^\infty {\cos(x) - \cos(4x) \over x^2} \, dx
.\]
:::

## \( \work \) {#work-52}

::: {.problem title="?"}
Let \( a>0 \) and calculate
\[
\int_0^\infty {x^2 \over (x^2 + a^2)^2} \, dx
.\]
:::

## \( \work \) {#work-53}

::: {.problem title="?"}
Calculate
\[
\int_0^\infty {\sin(x) \over x}\, dx
.\]
:::

## \( \work \) {#work-54}

::: {.problem title="?"}
Calculate
\[
\int_0^\infty {\sin(x) \over x(x^2+1)}\, dx
.\]
:::

## \( \work \) {#work-55}

::: {.problem title="?"}
Calculate
\[
\int_0^\infty {\sqrt x \over 1 + x^2} \, dx
.\]
:::

## \( \work \) {#work-56}

::: {.problem title="?"}
Calculate
\[
\int_{-\infty}^\infty {1+x^2 \over 1+x^4}\, dx
.\]
:::

## \( \work \) {#work-57}

::: {.problem title="?"}
Let \( a>0 \) and calculate
\[
\int_0^\infty {\cos(x) \over (x^2 + a^2)^2}\, dx
.\]
:::

## \( \work \) {#work-58}

::: {.problem title="?"}
Calculate
\[
\int_0^\infty {\sin^3(x) \over x^3} \, dx
.\]
:::

## \( \work \) {#work-59}

::: {.problem title="?"}
Let \( n\in {\mathbb{Z}}^{\geq 1} \) and \( 0<\theta<\pi \) and show that
\[
{1\over 2\pi i} \int_{{\left\lvert {z} \right\rvert} = 2} {z^n \over 1 -3z\cos(\theta) + z^2} \,dz = {\sin(n\theta) \over \sin(\theta)}
.\]
:::

## \( \work \) {#work-60}

::: {.problem title="?"}
Suppose \( a>b>0 \) and calculate
\[
\int_0^{2\pi} {1 \over (a+b\cos(\theta))^2} \,d\theta
.\]
:::

# Extra Questions

## \( \work \) {#work-61}

::: {.problem title="?"}
Suppose that \( f \) is an analytic function in the region \( D \) which contains the point \( a \). Let
\[F(z)= z-a-qf(z),\quad \text{where}\quad q \ \text{is a complex
parameter}.\]

1.  Let \( K\subset D \) be a circle with the center at point \( a \) and also we assume that \( f(z)\not =0 \) for \( z\in K \). Prove that the function \( F \) has one and only one zero \( z=w \) on the closed disc \( \mkern 1.5mu\overline{\mkern-1.5muK\mkern-1.5mu}\mkern 1.5mu \) whose boundary is the circle \( K \) if
    \[
    \displaystyle{ |q|<\min_{z\in K} \frac{|z-a|}{|f(z)|}.}
    .\]

2.  Let \( G(z) \) be an analytic function on the disk \( \mkern 1.5mu\overline{\mkern-1.5muK\mkern-1.5mu}\mkern 1.5mu \). Apply the residue theorem to prove that
    \[
    \displaystyle{ \frac{G(w)}{F'(w)}=\frac{1}{2\pi i}\int_K \frac{G(z)}{F(z)} dz,}
    \]
    where \( w \) is the zero from (1).
:::

## \( \work \) {#work-62}

::: {.problem title="?"}
Evaluate
\[
\displaystyle{ \int_{0}^{\infty}\frac{x\sin x}{x^2+a^2} \, dx }
.\]
:::

## \( \work \) {#work-63}

::: {.problem title="?"}
Show that
\[
\displaystyle \int_0^\infty \frac{x^{a-1}}{1+x^n} dx=\frac{\pi}{n\sin \frac{a\pi}{n}}
\]
using complex analysis, \( 0< a < n \). Here \( n \) is a positive integer.
:::

## \( \done \) {#done-8}

::: {.problem title="?"}
Show that
\[
\int_0^{\infty} {\cos(x) \over x^2 + b^2}\,dx= {\pi e^{-b} \over 2b}
.\]
:::

::: {.solution}
```{=tex}
\envlist
```
-   Let \( I \) be the integral over \( {\mathbb{R}} \). Since \( f(x) \) is even, the original integral is \( {1\over 2}I \).

-   Write \( f(z) = e^{iz} / (z^2 + b^2) \). Take a semicircular contour \( \Gamma \coloneqq\gamma_1 + \gamma_2 \) where \( \gamma_1 \) is \( [-R, R] \) on \( {\mathbb{R}} \) and \( \gamma_2 \) is the usual half-circle of radius \( R \).

-   Claim: \( \int_{\gamma_2} f \overset{R\to\infty}\longrightarrow 0 \), so \( \int_\Gamma \to \int_{\mathbb{R}}f(z) \).

    -   Easy estimate, just be careful with the \( i \) in the exponent:
        \[
        {\left\lvert {f} \right\rvert} = { {\left\lvert {e^{iz} } \right\rvert} \over {\left\lvert {z^2 + b^2} \right\rvert} } = {e^{-\Re z} \over {\left\lvert {z^2 + b^2} \right\rvert} } \leq {1\over {\left\lvert {z^2 + b^2} \right\rvert}} \overset{R\to\infty}\longrightarrow 0
        .\]

-   Compute \( \int_\Gamma f \) by residues: factor \( z^2 + b^2 = (z+ib)(z-ib) \), so the contour only contains the order 1 pole \( z_0 = ib \).

-   Compute the residue:
    \[
    \mathop{\mathrm{Res}}_{z=ib}f = \lim_{z\to ib} (z-ib) {e^{iz} \over (z+ib)(z-ib) } = { e^{iz} \over z+ib} \Big|_{z=ib} = {e^{i(ib)} \over 2ib} = {e^{-b} \over 2ib}
    .\]

-   So the intermediate integral is \( I \) is \( 2\pi i \) times this, i.e. \( I = \pi e^{-b} / b \).

-   And the original integral is \( {1\over 2}I = \pi e^{-b} \over 2b \).
:::

# Rouche's Theorem (8155h)

## 1 \( \done \) {#done-9}

Prove that for every \( n\in {\mathbb{Z}}^{\geq 0} \) the following polynomial has no roots in the open unit disc:
\[
f_n(x) \coloneqq\sum_{k=0}^n {z^k \over k!}
.\]

> Hint: check \( n=1,2 \) directly.

::: {.solution}
```{=tex}
\hfill
```
::: {.concept}
```{=tex}
\hfill
```
:::

Note

-   \( f_1(z) = 1+z \), which has the single root \( z=-1 \) which is not inside \( {\left\lvert {z} \right\rvert} < 1 \).

-   \( f_2(z) = 1 + z + {1\over 2}z^2 = (z - (1+i))(z- (1-i)) \), and \( {\left\lvert {1\pm i} \right\rvert} = \sqrt 2 >1 \).

-   Note that \( p_n(z) \overset{n\to\infty}e^z \) uniformly on any compact set.

-   Let \( r \) be arbitrary and fix \( N \coloneqq{\mathbb{D}}_r(0) \), then \( p_n(z) \to e^z \) uniformly on \( \mkern 1.5mu\overline{\mkern-1.5muN\mkern-1.5mu}\mkern 1.5mu \).

-   Set \( g_n(z) \coloneqq p_n(z) / e^z \), then \( g_n \to 1 \) uniformly on \( \mkern 1.5mu\overline{\mkern-1.5muN\mkern-1.5mu}\mkern 1.5mu \).

-   Choose \( n\gg 0 \) so that \( {\left\lvert {f(z) - 1} \right\rvert} < \varepsilon< 1 \) for all \( z\in \mkern 1.5mu\overline{\mkern-1.5muN\mkern-1.5mu}\mkern 1.5mu \).

-   So take \( h(z) = 1 \), then on \( {{\partial}}N \),?
:::

## 2 \( \done \) {#done-10}

Assume that \( {\left\lvert {b} \right\rvert} < 1 \) and show that the following polynomial has exactly two roots (counting multiplicity) in \( {\left\lvert {z} \right\rvert} < 1 \):
\[
f(z) \coloneqq z^3 + 3z^2 + bz + b^2
.\]

::: {.solution}
```{=tex}
\hfill
```
::: {.concept}
```{=tex}
\hfill
```
Multiple versions of Rouches theorem!
:::

-   Set \( h(z) = 3z^2 \) and \( g(z) = z^3 + bz + b^2 \).

-   Then on \( {\left\lvert {z} \right\rvert} = 1 \), `\begin{align*}
    {\left\lvert {g(z)} \right\rvert} \leq 1 + b + b^2 < 3 = 3{\left\lvert {z} \right\rvert}^2 = {\left\lvert {3z^2} \right\rvert} = {\left\lvert {h} \right\rvert}
    ,\end{align*}`{=tex} so \( g, h \) have the same number of roots in \( {\left\lvert {z} \right\rvert} \leq_? 1 \).

-   But \( h \) evidently has two roots in this region.
:::

## 3 \( \work \) {#work-64}

Let \( c\in {\mathbb{C}} \) with \( {\left\lvert {c} \right\rvert} < {1\over 3} \). Show that on the open set \( \left\{{z\in {\mathbb{C}}{~\mathrel{\Big|}~}\Re(z) < 1}\right\} \), the function \( f(z) \coloneqq ce^z \) has exactly one fixed point.

## 4 \( \done \) {#done-11}

How many roots does the following polynomial have in the open disc \( {\left\lvert {z} \right\rvert} < 1 \)?
\[
f(z) = z^7 - 4z^3 - 1
.\]

::: {.solution}
```{=tex}
\hfill
```
::: {.concept}
```{=tex}
\hfill
```
:::

-   Set \( h(z) = -4z^3 \) and \( g(z) = z^7 - 1 \), then on \( {\left\lvert {z} \right\rvert} = 1 \), `\begin{align*}
    {\left\lvert {g(z)} \right\rvert} = {\left\lvert {z^7 - 1} \right\rvert} \leq 1 + 1 = 2 < 4 = {\left\lvert {-4z^3} \right\rvert} = {\left\lvert {h(z)} \right\rvert}
    .\end{align*}`{=tex}

-   So \( h \) and \( h+g \) have the same number of roots, but \( h \) has three roots here.
:::

## 5 \( \done \) {#done-12}

Let \( n\in {\mathbb{Z}}^{\geq 0} \) and show that the equation
\[
e^z = az^n
\]
has \( n \) solutions in the open unit disc if \( {\left\lvert {a} \right\rvert} > e \), and no solutions if \( {\left\lvert {a} \right\rvert} < {1\over e} \).

## 6 \( \work \) {#work-65}

Let \( f \) be analytic in a domain \( D \) and fix \( z_0 \in D \) with \( w_0 \coloneqq f(z_0) \). Suppose \( z_0 \) is a zero of \( f(z) - w_0 \) with finite multiplicity \( m \). Show that there exists \( \delta >0 \) and \( \varepsilon> 0 \) such that for each \( w \) such that \( 0 < {\left\lvert {w-w_0} \right\rvert} < \varepsilon \), the equation \( f(z) - w = 0 \) has exactly \( m \) *distinct* solutions inside the disc \( {\left\lvert {z-z_0} \right\rvert} < \delta \).

## 7 \( \work \) {#work-66}

For \( k=1,2,\cdots, n \), suppose \( {\left\lvert {a_k} \right\rvert} < 1 \) and
\[
f(z) \coloneqq\qty{z - a_1 \over 1 - \mkern 1.5mu\overline{\mkern-1.5mua\mkern-1.5mu}\mkern 1.5mu_q z} \qty{z-a_2 \over 1 - \mkern 1.5mu\overline{\mkern-1.5mua\mkern-1.5mu}\mkern 1.5mu_2 z} \cdots \qty{z - a_n \over 1 - \mkern 1.5mu\overline{\mkern-1.5mua\mkern-1.5mu}\mkern 1.5mu_n z}
.\]
Show that \( f(z) = b \) has \( n \) solutions in \( {\left\lvert {z} \right\rvert} < 1 \).

## 8 \( \work \) {#work-67}

For each \( n\in {\mathbb{Z}}^{\geq 1} \), let
\[
P_n(z) = 1 + z + {1\over 2!} z^2 + \cdots + {1\over n!}z^n
.\]
Show that for sufficiently large \( n \), the polynomial \( P_n \) has no zeros in \( {\left\lvert {z} \right\rvert} < 10 \), while the polynomial \( P_n(z) - 1 \) has precisely 3 zeros there.

## 9 \( \work \) {#work-68}

Prove that
\[
\max_{{\left\lvert {z} \right\rvert} = 1} {\left\lvert {a_0 + a_1 z + \cdots + a_{n-1}z^{n-1} + z^n} \right\rvert} \geq 1
.\]

> Hint: the first part of the problem asks for a statement of Rouche's theorem.

## 10 \( \work \) {#work-69}

Use Rouche's theorem to prove the Fundamental Theorem of Algebra.

# Extras

## ? {#section-10}

Apply Rouché's Theorem to prove the Fundamental Theorem of Algebra:

If
\[
P_n(z) = a_0 + a_1z + \cdots + a_{n-1}z^{n-1} + a_nz^n\quad  (a_n \neq 0)
\]
is a polynomial of degree \( n \), then it has \( n \) zeros in \( \mathbb{C} \).

## ? {#section-11}

Suppose \( f \) is entire and there exist \( A, R >0 \) and natural number \( N \) such that
\[|f(z)| \geq A |z|^N\ \text{for}\ |z| \geq R.\]

Show that (i) \( f \) is a polynomial and (ii) the degree of \( f \) is at least \( N \).

# Schwarz Lemma and Reflection Principle (8155i)

## 1 \( \work \) {#work-70}

Suppose \( f:{\mathbb{D}}\to{\mathbb{D}} \) is analytic and admits a continuous extension \( \tilde f: \mkern 1.5mu\overline{\mkern-1.5mu{\mathbb{D}}\mkern-1.5mu}\mkern 1.5mu\to \mkern 1.5mu\overline{\mkern-1.5mu{\mathbb{D}}\mkern-1.5mu}\mkern 1.5mu \) such that \( {\left\lvert {z} \right\rvert} = 1 \implies {\left\lvert {f(z)} \right\rvert} = 1 \).

### a \( \work \) {#a-work-5}

Prove that \( f \) is a rational function.

### b \( \work \) {#b-work-7}

Suppose that \( z=0 \) is the unique zero of \( f \). Show that
\[  
\exists n\in {\mathbb{N}}, \lambda \in S^1 {\quad \operatorname{ such that } \quad}f(z) = \lambda z^n
.\]

### c \( \work \) {#c-work-5}

Suppose that \( a_1, \cdots, a_n \in {\mathbb{D}} \) are the zeros of \( f \) and prove that
\[  
\exists \lambda \in S^1 {\quad \operatorname{such that} \quad} f(z) = \lambda \prod_{j=1}^n {z - a_j \over 1 - \mkern 1.5mu\overline{\mkern-1.5mua_j\mkern-1.5mu}\mkern 1.5mu z}
.\]

## 2 \( \work \) {#work-71}

Let \( \mkern 1.5mu\overline{\mkern-1.5muB\mkern-1.5mu}\mkern 1.5mu(a, r) \) denote the closed disc of radius \( r \) about \( a\in {\mathbb{C}} \). Let \( f \) be holomorphic on an open set containing \( \mkern 1.5mu\overline{\mkern-1.5muB\mkern-1.5mu}\mkern 1.5mu(a, r) \) and let
\[  
M \coloneqq\sup_{z\in \mkern 1.5mu\overline{\mkern-1.5muB\mkern-1.5mu}\mkern 1.5mu(a, r)} {\left\lvert {f(z)} \right\rvert}
.\]

Prove that
\[  
z\in \mkern 1.5mu\overline{\mkern-1.5muB\mkern-1.5mu}\mkern 1.5mu\qty{a, {r\over 2}},\,z\neq a, \qquad {{\left\lvert { f(z) - f(a)} \right\rvert} \over {\left\lvert {z-a} \right\rvert}} \leq {2M \over r}
.\]

## 3 \( \work \) {#work-72}

Define
\[  
G \coloneqq\left\{{z\in {\mathbb{C}}{~\mathrel{\Big|}~}\Re(z) > 0, \, {\left\lvert {z-1} \right\rvert} > 1}\right\}
.\]

Find all of the injective conformal maps \( G\to {\mathbb{D}} \). These may be expressed as compositions of maps, but explain why this list is complete.

## 4 \( \work \) {#work-73}

Suppose \( f: {\mathbb{H}}\cup{\mathbb{R}}\to {\mathbb{C}} \) satisfies the following:

-   \( f(i) = i \)
-   \( f \) is continuous
-   \( f \) is analytic on \( {\mathbb{H}} \)
-   \( f(z) \in {\mathbb{R}}\iff z\in {\mathbb{R}} \).

Show that \( f({\mathbb{H}}) \) is a dense subset of \( {\mathbb{H}} \).

## 5 \( \work \) {#work-74}

Suppose \( f: {\mathbb{D}}\to {\mathbb{H}} \) is analytic and satisfies \( f(0) = 2 \). Find a sharp upper bound for \( {\left\lvert {f'(0)} \right\rvert} \), and prove it is sharp by example.

## 6 \( \work \) {#work-75}

Suppose \( f:{\mathbb{D}}\to{\mathbb{D}} \) is analytic, has a single zero of order \( k \) at \( z=0 \), and satsifies \( \lim_{{\left\lvert {z} \right\rvert} \to 1} {\left\lvert {f(z)} \right\rvert} = 1 \). Give with proof a formula for \( f(z) \).

## 7 \( \work \) {#work-76}

### a \( \work \) {#a-work-6}

State the standard Schwarz reflection principle involving reflection across the real axis.

### b \( \work \) {#b-work-8}

Give a linear fractional transformation \( T \) mapping \( {\mathbb{D}} \) to \( {\mathbb{H}} \). Let \( g(z) = \mkern 1.5mu\overline{\mkern-1.5muz\mkern-1.5mu}\mkern 1.5mu \), and show
\[  
(T^{-1} \circ g \circ T)(z) = 1/\mkern 1.5mu\overline{\mkern-1.5muz\mkern-1.5mu}\mkern 1.5mu
.\]

### c \( \work \) {#c-work-6}

Suppose that \( f \) is holomorphic on \( {\mathbb{D}} \), continuous on \( \mkern 1.5mu\overline{\mkern-1.5mu{\mathbb{D}}\mkern-1.5mu}\mkern 1.5mu \), and real on \( S^1 \). Show that \( f \) must be constant.

## 8 \( \work \) {#work-77}

Suppose \( f, g: {\mathbb{D}}\to \Omega \) are holomorphic with \( f \) injective and \( f(0) = g(0) \).

Show that
\[  
\mathop{\mathrm{\forall}}0 < r < 1,\qquad g\qty{\left\{{{\left\lvert {z} \right\rvert} < r}\right\}} \subseteq f\qty{\left\{{{\left\lvert {z} \right\rvert} < r}\right\}}
.\]

> The first part of this problem asks for a statement of the Schwarz lemma.

## 9 \( \work \) {#work-78}

Let \( S\coloneqq\left\{{z\in {\mathbb{D}}{~\mathrel{\Big|}~}\Im(z) \geq 0}\right\} \). Suppose \( f:S\to {\mathbb{C}} \) is continuous on \( S \), real on \( S\cap{\mathbb{R}} \), and holomorphic on \( S^\circ \).

Prove that \( f \) is the restriction of a holomorphic function on \( {\mathbb{D}} \).

## 10 \( \work \) {#work-79}

Suppose \( f:{\mathbb{D}}\to {\mathbb{D}} \) is analytic. Prove that
\[  
\forall a\in {\mathbb{D}}, \qquad {{\left\lvert {f'(a)} \right\rvert} \over 1 - {\left\lvert {f(a)} \right\rvert}^2 } \leq {1 \over 1 - {\left\lvert {a} \right\rvert}^2}
.\]

# Unsorted/Unknown

## ? {#section-12}

## ? {#section-13}

Let \( f \) be a continuous function in the region
\[
D=\{z\ |  |z|>R, 0\leq \arg Z\leq \theta\}\quad\text{where}\quad 0\leq \theta \leq 2\pi
.\]
If there exists \( k \) such that \( \displaystyle{\lim_{z\to\infty} zf(z)=k} \) for \( z \) in the region \( D \).

Show that
\[\lim_{R'\to\infty} \int_{L} f(z) dz=i\theta k,\]
where \( L \) is the part of the circle \( |z|=R' \) which lies in the region \( D \).

## 3 {#section-14}

If \( z\in K \), prove that the function \( \displaystyle{\frac{1}{F(z)}} \) can be represented as a convergent series with respect to \( q \):
\[
\displaystyle{
\frac{1}{F(z)}=\sum_{n=0}^{\infty} \frac{(qf(z))^n}{(z-a)^{n+1}}.}\]

## ? {#section-15}

Show that
\[
\displaystyle \int_0^\infty \frac{x^{a-1}}{1+x^n} dx=\frac{\pi}{n\sin \frac{a\pi}{n}}
\]
using complex analysis, \( 0< a < n \).

> Here \( n \) is a positive integer.

## 11. {#section-16}

Let \( g \) be analytic for \( |z|\leq 1 \) and \( |g(z)| < 1 \) for \( |z| = 1 \).

### a {#a}

Show that \( g \) has a unique fixed point in \( |z| < 1 \).

### b {#b}

What happens if we replace \( |g(z)| < 1 \) with \( |g(z)|\leq 1 \) for \( |z|=1 \)?

Give an example if (a) is not true or give an proof if (a) is still true.

### c {#c}

What happens if we simply assume that \( f \) is analytic for \( |z| < 1 \) and \( |f(z)| < 1 \) for \( |z| < 1 \)? Suppose that \( f(z)\not\equiv z \).

Can \( f \) have more than one fixed point in\( |z| < 1 \)?

> Hint: The map
> \[\displaystyle{\psi_{\alpha}(z)=\frac{\alpha-z}{1-\mkern 1.5mu\overline{\mkern-1.5mu\alpha\mkern-1.5mu}\mkern 1.5muz}}\]
> may be useful.

## ? {#section-17}

Let \( f(z) \) be entire and assume that \( f(z) \leq M |z|^2 \) outside some disk for some constant \( M \).

Show that \( f(z) \) is a polynomial in \( z \) of degree \( \leq 2 \).

## ? {#section-18}

Let \( a_n(z) \) be an analytic sequence in a domain \( D \) such that \( \displaystyle \sum_{n=0}^\infty |a_n(z)| \) converges uniformly on bounded and closed sub-regions of \( D \).

Show that \( \displaystyle \sum_{n=0}^\infty |a'_n(z)| \) converges uniformly on bounded and closed sub-regions of \( D \).

## 16 {#section-19}

Let \( f(z) \) be analytic in an open set \( \Omega \) except possibly at a point \( z_0 \) inside \( \Omega \).

Show that if \( f(z) \) is bounded in near \( z_0 \), then \( \displaystyle \int_\Delta f(z) dz = 0 \) for all triangles \( \Delta \) in \( \Omega \).

# Riemann Mapping and Casorati-Weierstrass

## 10. {#section-20}

Let \( f: {\mathbb C} \rightarrow {\mathbb C} \) be an injective analytic (also called univalent) function. Show that there exist complex numbers \( a \neq 0 \) and \( b \) such that \( f(z) = az + b \).

# Spring 2020 Homework 1

## 1 {#section-21}

Geometrically describe the following subsets of \( {\mathbb{C}} \):

a.  \( {\left\lvert {z-1} \right\rvert} = 1 \)
b.  \( {\left\lvert {z-1} \right\rvert} = 2{\left\lvert {z-2} \right\rvert} \)
c.  \( 1/z = \mkern 1.5mu\overline{\mkern-1.5muz\mkern-1.5mu}\mkern 1.5mu \)
d.  \( \Re(z) = 3 \)
e.  \( \Im(z) = a \) with \( a\in {\mathbb{R}} \).
f.  \( \Re(z) > a \) with \( a\in {\mathbb{R}} \).
g.  \( {\left\lvert {z-1} \right\rvert} < 2{\left\lvert {z-2} \right\rvert} \)

## 2 {#section-22}

Prove the following inequality, and explain when equality holds:
\[
{\left\lvert {z+w} \right\rvert} \geq {\left\lvert { {\left\lvert {z} \right\rvert} - {\left\lvert {w} \right\rvert} } \right\rvert}
.\]

## 3 {#section-23}

Prove that the following polynomial has its roots outside of the unit circle:
\[
p(z) = z^3 + 2z + 4
.\]

> Hint: What is the maximum value of the modulus of the first two terms if \( {\left\lvert {z} \right\rvert} \leq 1 \)?

## 4 {#section-24}

a.  Prove that if \( c>0 \),
    \[
    {\left\lvert {w_1} \right\rvert} = c{\left\lvert {w_2} \right\rvert} \implies {\left\lvert {w_1 - c^2 w_2} \right\rvert} = c{\left\lvert {w_1 - w_2} \right\rvert}
    .\]

b.  Prove that if \( c>0 \) and \( c\neq 1 \), with \( z_1\neq z_2 \), then the following equation represents a circle:
    \[
     {\left\lvert {z-z_1 \over z-z_2} \right\rvert} = c
     .\]
    Find its center and radius.

    > Hint: use part (a)

## 5 {#section-25}

a.  Let \( z, w \in {\mathbb{C}} \) with \( \mkern 1.5mu\overline{\mkern-1.5muz\mkern-1.5mu}\mkern 1.5mu w \neq 1 \). Prove that
    \[
     {\left\lvert {w-z \over 1 - \mkern 1.5mu\overline{\mkern-1.5muw\mkern-1.5mu}\mkern 1.5mu z} \right\rvert} < 1 \quad\text{ if } {\left\lvert {z} \right\rvert}<1,~ {\left\lvert {w} \right\rvert} < 1
     \]
    with equality when \( {\left\lvert {z} \right\rvert} = 1 \) or \( {\left\lvert {w} \right\rvert} = 1 \).

b.  Prove that for a fixed \( w\in {\mathbb{D}} \), the mapping \( F: z\mapsto {w-z \over 1 - \mkern 1.5mu\overline{\mkern-1.5muw\mkern-1.5mu}\mkern 1.5mu z} \) satisfies

    -   \( F \) maps \( {\mathbb{D}} \) to itself and is holomorphic.
    -   \( F(0) = w \) and \( F(w) = 0 \).
    -   \( {\left\lvert {z} \right\rvert} = 1 \) implies \( {\left\lvert {F(z)} \right\rvert} = 1 \).

## 6 {#section-26}

Use \( n \)th roots of unity to show that
\[
2^{n-1} \sin\qty{\pi \over n} \sin\qty{2\pi \over n} \cdots \sin\qty{(n-1)\pi \over n} = n
.\]

> Hint:
> \[
> 1 - \cos(2\theta) &= 2\sin^2(\theta) \\
> 2 \sin(2\theta) &= 2\sin(\theta) \cos(\theta)
> .\]

## 7 {#section-27}

Prove that \( f(z) = {\left\lvert {z} \right\rvert}^2 \) has a derivative at \( z=0 \) and nowhere else.

## 8 {#section-28}

Let \( f(z) \) be analytic in a domain, and prove that \( f \) is constant if it satisfies any of the following conditions:

a.  \( {\left\lvert {f(z)} \right\rvert} \) is constant.
b.  \( \Re(f(z)) \) is constant.
c.  \( \arg(f(z)) \) is constant.
d.  \( \mkern 1.5mu\overline{\mkern-1.5muf(z)\mkern-1.5mu}\mkern 1.5mu \) is analytic.

How do you generalize (a) and (b)?

## 9 {#section-29}

Prove that if \( z\mapsto f(z) \) is analytic, then \( z \mapsto \mkern 1.5mu\overline{\mkern-1.5muf(\mkern 1.5mu\overline{\mkern-1.5muz\mkern-1.5mu}\mkern 1.5mu)\mkern-1.5mu}\mkern 1.5mu \) is analytic.

## 10 {#section-30}

a.  Show that in polar coordinates, the Cauchy-Riemann equations take the form
    \[
      \frac{\partial u}{\partial r}=\frac{1}{r} \frac{\partial v}{\partial \theta} \text { and } \frac{\partial v}{\partial r}=-\frac{1}{r} \frac{\partial u}{\partial \theta}
      .\]

b.  Use (a) to show that the logarithm function, defined as
    \[
      \log z=\log r+i \theta \text { where } z=r e^{i \theta} \text { with }-\pi<\theta<\pi
      .\]
    is holomorphic on the region \( r> 0, -\pi < \theta < \pi \).

Also show that this function is not continuous in \( r>0 \).

## 11 {#section-31}

Prove that the distinct complex numbers \( z_1, z_2, z_3 \) are the vertices of an equilateral triangle if and only if
\[
z_{1}^{2}+z_{2}^{2}+z_{3}^{2}=z_{1} z_{2}+z_{2} z_{3}+z_{3} z_{1}
.\]

# Spring 2020 Homework 2

> Note on notation: I sometimes use \( f_x \coloneqq{\frac{\partial f}{\partial x}\,} \) to denote partial derivatives, and \( {{\partial}}_z^n f \) as \( f^{(n)}(z) \).

## Stein And Shakarchi

### 2.6.1 {#section-32}

Show that
\[
\int_{0}^{\infty} \sin \left(x^{2}\right) d x=\int_{0}^{\infty} \cos \left(x^{2}\right) d x=\frac{\sqrt{2 \pi}}{4}
.\]

> Hint: integrate \( e^{-x^2} \) over the following contour, using the fact that \( \int_{-\infty}^{\infty} e^{-x^{2}} d x=\sqrt{\pi} \):

![Image](figures/2020-02-03-13:51.png)\

### 2.6.2 {#section-33}

Show that

\[
\int_{0}^{\infty} \frac{\sin x}{x} d x=\frac{\pi}{2}
.\]

> Hint: use the fact that this integral equals \( \frac{1}{2 i} \int_{-\infty}^{\infty} \frac{e^{i x}-1}{x} d x \), and integrate around an indented semicircle.

### 2.6.5 {#section-34}

Suppose \( f\in C_{\mathbb{C}}^1(\Omega) \) and \( T\subset \Omega \) is a triangle with \( T^\circ \subset \Omega \). Apply Green's theorem to show that \( \int_T f(z) ~dz = 0 \).

Assume that \( f' \) is continuous and prove Goursat's theorem.

> Hint: Green's theorem states

\[
\int_{T} F d x+G d y=\int_{T^\circ}\left(\frac{\partial G}{\partial x}-\frac{\partial F}{\partial y}\right) d x d y
.\]

### 2.6.6 {#section-35}

Suppose that \( f \) is holomorphic on a punctured open set \( \Omega\setminus\left\{{w_0}\right\} \) and let \( T\subset \Omega \) be a triangle containing \( w_0 \). Prove that if \( f \) is bounded near \( w_0 \), then \( \int_T f(z) ~dz = 0 \).

### 2.6.7 {#section-36}

Suppose \( f: {\mathbb{D}}\to {\mathbb{C}} \) is holomorphic and let \( d \coloneqq\sup_{z, w\in {\mathbb{D}}}{\left\lvert {f(z) - f(w)} \right\rvert} \) be the diameter of the image of \( f \). Show that \( 2 {\left\lvert {f'(0)} \right\rvert} \leq d \), and that equality holds iff \( f \) is linear, so \( f(z) = a_1 z + a_2 \).

> Hint: \( 2f'(0) = \frac{1}{2\pi i} \int_{{\left\lvert {\xi } \right\rvert}= r} \frac{ f(\xi) - f(-\xi) }{\xi^2} ~d\xi \) whenever \( 0<r<1 \).

### 2.6.8 {#section-37}

Suppose that \( f \) is holomorphic on the strip \( S = \left\{{x+iy {~\mathrel{\Big|}~}x\in {\mathbb{R}},~ -1<y<1}\right\} \) with \( {\left\lvert {f(z)} \right\rvert} \leq A \qty{1 + {\left\lvert {z} \right\rvert}}^\nu \) for \( \nu \) some fixed real number. Show that for all \( z\in S \), for each integer \( n\geq 0 \) there exists an \( A_n \geq 0 \) such that \( {\left\lvert {f^{(n)}(x)} \right\rvert} \leq A_n (1 + {\left\lvert {x} \right\rvert})^\nu \) for all \( x\in {\mathbb{R}} \).

> Hint: Use the Cauchy inequalities.

### 2.6.9 {#section-38}

Let \( \Omega \subset {\mathbb{C}} \) be open and bounded and \( \phi: \Omega \to \Omega \) holomorphic. Prove that if there exists a point \( z_0 \in \Omega \) such that \( \phi(z_0) = z_0 \) and \( \phi'(z_0) = 1 \), then \( \phi \) is linear.

> Hint: assume \( z_0 = 0 \) (explain why this can be done) and write \( \phi(z) = z + a_n z^n + O(z^{n+1}) \) near \( 0 \). Let \( \phi_k = \phi \circ \phi \circ \cdots \circ \phi \) and prove that \( \phi_k(z) = z + ka_nz^n + O(z^{n+1}) \). Apply Cauchy's inequalities and let \( k\to \infty \) to conclude.

### 2.6.10 {#section-39}

Can every continuous function on \( \mkern 1.5mu\overline{\mkern-1.5mu{\mathbb{D}}\mkern-1.5mu}\mkern 1.5mu \) be uniformly approximated by polynomials in the variable \( z \)?

> Hint: compare to Weierstrass for the real interval.

### 2.6.13 {#section-40}

Suppose \( f \) is analytic, defined on all of \( {\mathbb{C}} \), and for each \( z_0 \in {\mathbb{C}} \) there is at least one coefficient in the expansion \( f(z) = \sum_{n=0}^\infty c_n(z-z_0)^n \) is zero. Prove that \( f \) is a polynomial.

> Hint: use the fact that \( c_n n! = f^{(n)}(z_0) \) and use a countability argument.

### 2.6.14 {#section-41}

Suppose that \( f \) is holomorphic in an open set containing \( {\mathbb{D}} \) except for a pole \( z_0 \in {{\partial}}{\mathbb{D}} \). Let \( \sum_{n=0}^\infty a_n z^n \) be the power series expansion of \( f \) in \( {\mathbb{D}} \), and show that \( \lim \frac{a_n}{a_{n+1}} = z_0 \).

### 2.6.15 {#section-42}

Suppose \( f \) is continuous and nonvanishing on \( \mkern 1.5mu\overline{\mkern-1.5mu{\mathbb{D}}\mkern-1.5mu}\mkern 1.5mu \), and holomorphic in \( {\mathbb{D}} \). Prove that if \( {\left\lvert {z} \right\rvert} = 1 \implies {\left\lvert {f(z)} \right\rvert} = 1 \), then \( f \) is constant.

> Hint: Extend \( f \) to all of \( {\mathbb{C}} \) by \( f(z) = 1/ \mkern 1.5mu\overline{\mkern-1.5muf(1/\mkern 1.5mu\overline{\mkern-1.5muz\mkern-1.5mu}\mkern 1.5mu)\mkern-1.5mu}\mkern 1.5mu \) for any \( {\left\lvert {z} \right\rvert} > 1 \), and argue as in the Schwarz reflection principle.

## Additional Problems

### 1 {#section-43}

Let \( a_n\neq 0 \) and show that
\[
\lim_{n\to \infty} {{\left\lvert {a_{n+1}} \right\rvert} \over {\left\lvert {a_n} \right\rvert}} = L \implies \lim_{n\to\infty} {\left\lvert {a_n} \right\rvert}^{1\over n} = L
.\]

In particular, this shows that when applicable, the ratio test can be used to calculate the radius of convergence of a power series.

### 2 {#section-44}

Let \( f \) be a power series centered at the origin. Prove that \( f \) has a power series expansion about any point in its disc of convergence.

### 3 {#section-45}

Prove the following:

a.  \( \sum_{n} nz^n \) does not converge at any point of \( S^1 \)

b.  \( \sum_n {z^n \over n^2} \) converges at every point of \( S^1 \).

c.  \( \sum_n {z^n \over n} \) converges at every point of \( S^1 \) except \( z=1 \).

### 4 {#section-46}

Without using Cauchy's integral formula, show that if \( {\left\lvert {a} \right\rvert} < r < {\left\lvert {b} \right\rvert} \), then
\[
\int_{\gamma} \frac{d z}{(z-\alpha)(z-\beta)}=\frac{2 \pi i}{\alpha-\beta}
\]
where \( \gamma \) denotes the circle centered at the origin of radius \( r \) with positive orientation.

### 5 {#section-47}

Assume \( f \) is continuous in the region \( \left\{{x+iy {~\mathrel{\Big|}~}x\geq x_0, ~ 0\leq y \leq b}\right\} \), and the following limit exists independent of \( y \):
\[
\lim_{x\to +\infty}f(x+iy) = A
.\]

Show that if \( \gamma_x \coloneqq\left\{{z = x+it {~\mathrel{\Big|}~}0 \leq t \leq b}\right\} \), then
\[
\lim_{x\to +\infty} \int_{\gamma_x} f(z) \,dz = iAb
.\]

### 6 {#section-48}

Show by example that there exists a function \( f(z) \) that is holomorphic on \( \left\{{z\in {\mathbb{C}}{~\mathrel{\Big|}~}0 < {\left\lvert {z} \right\rvert} < 1}\right\} \) and for all \( r<1 \),
\[
\int_{{\left\lvert {z} \right\rvert} = r} f(z) \, dz = 0
,\]
but \( f \) is not holomorphic at \( z=0 \).

### 7 {#section-49}

Let \( f \) be analytic on a region \( R \) and suppose \( f'(z_0) \neq 0 \) for some \( z_0 \in R \). Show that if \( C \) is a circle of sufficiently small radius centered at \( z_0 \), then
\[
\frac{2 \pi i}{f^{\prime}\left(z_{0}\right)}=\int_{C} \frac{d z}{f(z)-f\left(z_{0}\right)}
.\]

> Hint: use the inverse function theorem.

### 8 {#section-50}

Assume two functions \( u, b: {\mathbb{R}}^2 \to {\mathbb{R}} \) have continuous partial derivatives at \( (x_0 ,y_0) \). Show that \( f \coloneqq u + iv \) has derivative \( f'(z_0) \) at \( z_0 = =x_0 + iy_0 \) if and only if
\[
\lim _{r \rightarrow 0} \frac{1}{\pi r^{2}} \int_{\left|z-z_{0}\right|=r} f(z) d z=0
.\]

### 9 (Cauchy's Formula for Exterior Regions)

Let \( \gamma \) be a piecewise smooth simple closed curve with interior \( \Omega_1 \) and exterior \( \Omega_2 \). Assume \( f' \) exists in an open set containing \( \gamma \) and \( \Omega_2 \) with \( \lim_{z\to \infty} f(z) = A \). Show that
\[
\frac{1}{2 \pi i} \int_{\gamma} \frac{f(\xi)}{\xi-z} d \xi=\left\{\begin{array}{ll}
A, & \text { if } z \in \Omega_{1} \\
-f(z)+A, & \text { if } z \in \Omega_{2}
\end{array}\right.
.\]

### 10 {#section-51}

Let \( f(z) \) be bounded and analytic in \( {\mathbb{C}} \). Let \( a\neq b \) be any fixed complex numbers. Show that the following limit exists:
\[
\lim_{R\to \infty} \int_{{\left\lvert {z} \right\rvert} = R} {f(z) \over (z-a)(z-b)} \,dz
.\]

Use this to show that \( f(z) \) must be constant.

### 11 {#section-52}

Suppose \( f(z) \) is entire and
\[
\lim_{z\to\infty} {f(z) \over z} = 0
.\]

Show that \( f(z) \) is a constant.

### 12 {#section-53}

Let \( f \) be analytic in a domain \( D \) and \( \gamma \) be a closed curve in \( D \). For any \( z_0\in D \) not on \( \gamma \), show that
\[
\int_{\gamma} \frac{f^{\prime}(z)}{\left(z-z_{0}\right)} d z=\int_{\gamma} \frac{f(z)}{\left(z-z_{0}\right)^{2}} d z
.\]
Give a generalization of this result.

### 13 {#section-54}

Compute
\[
\int_{{\left\lvert {z} \right\rvert} = 1} \qty{z + {1\over z}}^{2n} {dz \over z}
\]
and use it to show that
\[
\int_0^{2\pi} \cos^{2n}(\theta) \, d\theta = 2\pi \qty{1\cdot 3 \cdot 5 \cdots (2n-1) \over 2 \cdot 4 \cdot 6 \cdots (2n)}
.\]

# Spring 2020 Homework 3

## Stein and Shakarchi

### 3.8.1 {#section-55}

Use the following formula to show that the complex zeros of \( \sin(\pi z) \) are exactly the integers, and they are each of order 1:
\[
\sin \pi z=\frac{e^{i \pi z}-e^{-i \pi z}}{2 i}
.\]

Calculate the residue of \( {1\over \sin(\pi z)} \) at \( z=n\in {\mathbb{Z}} \).

### 3.8.2 {#section-56}

Evaluate the integral
\[
\int_{\mathbb{R}}{dx \over 1 + x^4}
.\]

What are the poles of \( {1\over 1 + z^4} \) ?

### 3.8.4 {#section-57}

Show that
\[
\int_{-\infty}^{\infty} \frac{x \sin x}{x^{2}+a^{2}} d x=\pi e^{-a}, \quad \text { for all } a>0
.\]

### 3.8.5 {#section-58}

Show that if \( \xi\in {\mathbb{R}} \), then
\[
\int_{-\infty}^{\infty} \frac{e^{-2 \pi i x \xi}}{\left(1+x^{2}\right)^{2}} d x=\frac{\pi}{2}(1+2 \pi|\xi|) e^{-2 \pi|\xi|}
.\]

### 3.8.6 {#section-59}

Show that
\[
\int_{-\infty}^{\infty} \frac{d x}{\left(1+x^{2}\right)^{n+1}}=\frac{1 \cdot 3 \cdot 5 \cdots(2 n-1)}{2 \cdot 4 \cdot 6 \cdots(2 n)} \cdot \pi
.\]

### 3.8.7 {#section-60}

Show that
\[
\int_{0}^{2 \pi} \frac{d \theta}{(a+\cos \theta)^{2}}=\frac{2 \pi a}{\left(a^{2}-1\right)^{3 / 2}}, \quad \text { whenever } a>1
.\]

### 3.8.8 {#section-61}

Show that if \( a,b\in {\mathbb{R}} \) with \( a > {\left\lvert {b} \right\rvert} \), then
\[
\int_{0}^{2 \pi} \frac{d \theta}{a+b \cos \theta}=\frac{2 \pi}{\sqrt{a^{2}-b^{2}}}
.\]

### 3.8.9 {#section-62}

Show that
\[
\int_{0}^{1} \log (\sin \pi x) d x=-\log 2
.\]

> Hint: use the following contour.
>
> ![](figures/image_2020-06-17-21-52-40.png)

### 3.8.10 {#section-63}

Show that if \( a>0 \), then
\[
\int_{0}^{\infty} \frac{\log x}{x^{2}+a^{2}} d x=\frac{\pi}{2 a} \log a
.\]

> Hint: use the following contour.
>
> ![](figures/image_2020-06-17-21-53-19.png)

### 3.8.14 {#section-64}

Prove that all entire functions that are injective are of the form \( f(z) = az + b \) with \( a,b\in {\mathbb{C}} \) and \( a\neq 0 \).

> Hint: Apply the Casorati-Weierstrass theorem to \( f(1/z) \).

### 3.8.15 {#section-65}

Use the Cauchy inequalities or the maximum modulus principle to solve the following problems:

a.  Prove that if \( f \) is an entire function that satisfies
    \[
     \sup _{|z|=R}|f(z)| \leq A R^{k}+B
     \]
    for all \( R>0 \), some integer \( k\geq 0 \), and some constants \( A, B > 0 \), then \( f \) is a polynomial of degree \( \leq k \).

b.  Show that if \( f \) is holomorphic in the unit disc, is bounded, and converges uniformly to zero in the sector \( \theta < \arg(z) < \phi \) as \( {\left\lvert {z} \right\rvert} \to 0 \), then \( f \equiv 0 \).

c.  Let \( w_1, \cdots w_n \) be points on \( S^1 \subset {\mathbb{C}} \). Prove that there exists a point \( z\in S^1 \) such that the product of the distances from \( z \) to the points \( w_j \) is at least 1.

    Conclude that there exists a point \( w\in S^1 \) such that the product of the above distances is *exactly* 1.

d.  Show that if the real part of an entire function is bounded, then \( f \) is constant.

### 3.8.17 {#section-66}

Let \( f \) be non-constant and holomorphic in an open set containing the closed unit disc.

a.  Show that if \( {\left\lvert {f(z)} \right\rvert} = 1 \) whenever \( {\left\lvert {z} \right\rvert} = 1 \), then the image of \( f \) contains the unit disc.

    > Hint: Show that \( f(z) = w_0 \) has a root for every \( w_0 \in {\mathbb{D}} \), for which it suffices to show that \( f(z) = 0 \) has a root. Conclude using the maximum modulus principle.

b.  If \( {\left\lvert {f(z)} \right\rvert} \geq 1 \) whenever \( {\left\lvert {z} \right\rvert} = 1 \) and there exists a \( z_0\in {\mathbb{D}} \) such that \( {\left\lvert {f(z_0)} \right\rvert} < 1 \), then the image of \( f \) contains the unit disc.

### 3.8.19 {#section-67}

Prove that maximum principle for harmonic functions, i.e.

a.  If \( u \) is a non-constant real-valued harmonic function in a region \( \Omega \), then \( u \) can not attain a maximum or a minimum in \( \Omega \).

b.  Suppose \( \Omega \) is a region with compact closure \( \mkern 1.5mu\overline{\mkern-1.5mu\Omega\mkern-1.5mu}\mkern 1.5mu \). If \( u \) is harmonic in \( \Omega \) and continuous in \( \mkern 1.5mu\overline{\mkern-1.5mu\Omega\mkern-1.5mu}\mkern 1.5mu \), then
    \[
     \sup _{z \in \Omega}|u(z)| \leq \sup _{z \in \mkern 1.5mu\overline{\mkern-1.5mu\Omega \mkern-1.5mu}\mkern 1.5mu-\Omega}|u(z)|
     .\]

> Hint: to prove (a), assume \( u \) attains a local maximum at \( z_0 \). Let \( f \) be holomorphic near \( z_0 \) with \( \Re(f) = u \), and show that \( f \) is not an open map. Then (a) implies (b).

## Extra Problems

### 1 {#section-68}

Problem
:   Prove that if \( f \) has two Laurent series expansions,
    \[
      f(z) = \sum c_n(z-a)^n \quad\text{and}\quad f(z) = \sum c_n'(z-a)^n
      \]
    then \( c_n = c_n' \).

### 2 {#section-69}

Problem
:   Find Laurent series expansions of
    \[
      \frac{1}{1-z^2} + \frac{1}{3-z}
      \]
    How many such expansions are there? In what domains are each valid?

### 3 {#section-70}

Problem
:   Let \( P, Q \) be polynomials with no common zeros. Assume \( a \) is a root of \( Q \). Find the principal part of \( P/Q \) at \( z=a \) in terms of \( P \) and \( Q \) if \( a \) is (1) a simple root, and (2) a double root.

### 4 {#section-71}

Problem

:   Let \( f \) be non-constant, analytic in \( {\left\lvert {z} \right\rvert} > 0 \), where \( f(z_n) = 0 \) for infinitely many points \( z_n \) with \( \lim_{n\to\infty} z_n = 0 \).

    Show that \( z=0 \) is an essential singularity for \( f \).

    > Example: \( f(z) = \sin(1/z) \).

### 5 {#section-72}

Problem
:   Show that if \( f \) is entire and \( \lim_{z\to\infty}f(z) = \infty \), then \( f \) is a polynomial.

### 6 {#section-73}

Problem

:   ```{=tex}
    \hfill
    ```
    a.  Show (without using 3.8.9 in the S&S) that
        \[
        \int_0^{2\pi} \log{\left\lvert {1 - e^{i\theta}} \right\rvert}~d\theta = 0
        \]
    b.  Show that this identity is equivalent to S&S 3.8.9:
        \[
        \int_0^1 \log(\sin(\pi x)) ~dx = -\log 2
        .\]

### 7 {#section-74}

Problem
:   Let \( 0<a<4 \) and evaluate
    \[
      \int_0^\infty \frac{x^{\alpha-1}}{1+x^3} ~dx
      \]

### 8 {#section-75}

Problem

:   Prove the fundamental theorem of Algebra using

    a.  Rouche's Theorem.
    b.  The maximum modulus principle.

### 9 {#section-76}

Problem

:   Let \( f \) be analytic in a region \( D \) and \( \gamma \) a rectifiable curve in \( D \) with interior in \( D \).

    Prove that if \( f(z) \) is real for all \( z\in \gamma \), then \( f \) is constant.

### 10 {#section-77}

Problem
:   For \( a> 0 \), evaluate
    \[
      \int_0^{\pi/2} \frac{d\theta}{a + \sin^2 \theta}
      \]

### 11 {#section-78}

Problem
:   Find the number of roots of \( p(z) = 4z^4 - 6z + 3 \) in \( {\left\lvert {z} \right\rvert} < 1 \) and \( 1 < {\left\lvert {z} \right\rvert} < 2 \) respectively.

### 12 {#section-79}

Problem
:   Prove that \( z^4 + 2z^3 -2z + 10 \) has exactly one root in each open quadrant.

### 13 {#section-80}

Problem
:   Prove that for \( a> 0 \), \( z\tan z - a \) has only real roots.

### 14 {#section-81}

Problem

:   Let \( f \) be nonzero, analytic on a bounded region \( \Omega \) and continuous on its closure \( \overline \Omega \).

    Show that if \( {\left\lvert {f(z)} \right\rvert} \equiv M \) is constant for \( z\in \partial \Omega \), then \( f(z) \equiv Me^{i\theta} \) for some real constant \( \theta \).

# Extra Questions from Jingzhi Tie

## Fall 2009

### ? {#section-82}

(1) Assume \( \displaystyle f(z) = \sum_{n=0}^\infty c_n z^n \) converges in \( |z| < R \). Show that for \( r <R \),
    \[\frac{1}{2 \pi} \int_0^{2 \pi} |f(r e^{i \theta})|^2 d \theta =
    \sum_{n=0}^\infty |c_n|^2 r^{2n} \; .\]

(2) Deduce Liouville's theorem from (1).

### ? {#section-83}

Let \( f \) be a continuous function in the region
\[D=\{z {~\mathrel{\Big|}~}{\left\lvert {z} \right\rvert}>R, 0\leq \arg z\leq \theta\}\quad\text{where}\quad
1\leq \theta \leq 2\pi.\]
If there exists \( k \) such that \( \displaystyle{\lim_{z\to\infty} zf(z)=k} \) for \( z \) in the region \( D \). Show that
\[\lim_{R'\to\infty} \int_{L} f(z) dz=i\theta k,\]
where \( L \) is the part of the circle \( |z|=R' \) which lies in the region \( D \).

### ? {#section-84}

Suppose that \( f \) is an analytic function in the region \( D \) which contains the point \( a \). Let
\[F(z)= z-a-qf(z),\quad \text{where}~ q \ \text{is a complex
parameter}.\]

(1) Let \( K\subset D \) be a circle with the center at point \( a \) and also we assume that \( f(z)\not =0 \) for \( z\in K \). Prove that the function \( F \) has one and only one zero \( z=w \) on the closed disc \( \mkern 1.5mu\overline{\mkern-1.5muK\mkern-1.5mu}\mkern 1.5mu \) whose boundary is the circle \( K \) if \( \displaystyle{ |q|<\min_{z\in K} \frac{|z-a|}{|f(z)|}.} \)\

(2) Let \( G(z) \) be an analytic function on the disk \( \mkern 1.5mu\overline{\mkern-1.5muK\mkern-1.5mu}\mkern 1.5mu \). Apply the residue theorem to prove that \( \displaystyle{ \frac{G(w)}{F'(w)}=\frac{1}{2\pi i}\int_K \frac{G(z)}{F(z)} dz,} \) where \( w \) is the zero from (1).\

(3) If \( z\in K \), prove that the function \( \displaystyle{\frac{1}{F(z)}} \) can be represented as a convergent series with respect to \( q \): \( \displaystyle{ \frac{1}{F(z)}=\sum_{n=0}^{\infty} \frac{(qf(z))^n}{(z-a)^{n+1}}.} \)

### ? {#section-85}

Evaluate
\[\displaystyle{ \int_{0}^{\infty}\frac{x\sin x}{x^2+a^2} \,
dx }.\]

### ? {#section-86}

Let \( f=u+iv \) be differentiable (i.e. \( f'(z) \) exists) with continuous partial derivatives at a point \( z=re^{i\theta} \), \( r\not= 0 \). Show that
\[\frac{\partial u}{\partial r}=\frac{1}{r}\frac{\partial v}{\partial \theta},\quad
\frac{\partial v}{\partial r}=-\frac{1}{r}\frac{\partial u}{\partial \theta}.\]

### ? {#section-87}

Show that \( \displaystyle \int_0^\infty \frac{x^{a-1}}{1+x^n} dx=\frac{\pi}{n\sin \frac{a\pi}{n}} \) using complex analysis, \( 0< a < n \). Here \( n \) is a positive integer.

### ? {#section-88}

For \( s>0 \), the **gamma function** is defined by \( \displaystyle{\Gamma(s)=\int_0^{\infty} e^{-t}t^{s-1} dt} \).

1.  Show that the gamma function is analytic in the half-plane \( \Re (s)>0 \), and is still given there by the integral formula above.

2.  Apply the formula in the previous question to show that
    \[\Gamma(s)\Gamma(1-s)=\frac{\pi}{\sin \pi s}.\]

> Hint: You may need \( \displaystyle{\Gamma(1-s)=t \int_0^{\infty}e^{-vt}(vt)^{-s} dv} \) for \( t>0 \).

### ? {#section-89}

Apply Rouché's Theorem to prove the Fundamental Theorem of Algebra: If
\[P_n(z) = a_0 + a_1z + \cdots + a_{n-1}z^{n-1} + a_nz^n\quad  (a_n \neq 0)\]
is a polynomial of degree n, then it has n zeros in \( \mathbb C \).

### ? {#section-90}

Suppose \( f \) is entire and there exist \( A, R >0 \) and natural number \( N \) such that
\[|f(z)| \geq A |z|^N\ \text{for}\ |z| \geq R.\]
Show that (i) \( f \) is a polynomial and (ii) the degree of \( f \) is at least \( N \).

### ? {#section-91}

Let \( f: {\mathbb C} \rightarrow {\mathbb C} \) be an injective analytic (also called *univalent*) function. Show that there exist complex numbers \( a \neq 0 \) and \( b \) such that \( f(z) = az + b \).

### ? {#section-92}

Let \( g \) be analytic for \( |z|\leq 1 \) and \( |g(z)| < 1 \) for \( |z| = 1 \).

1.  Show that \( g \) has a unique fixed point in \( |z| < 1 \).

2.  What happens if we replace \( |g(z)| < 1 \) with \( |g(z)|\leq 1 \) for \( |z|=1 \)? Give an example if (a) is not true or give an proof if (a) is still true.

3.  What happens if we simply assume that \( f \) is analytic for \( |z| < 1 \) and \( |f(z)| < 1 \) for \( |z| < 1 \)? Suppose that \( f(z) \not\equiv z \). Can f have more than one fixed point in \( |z| < 1 \)?

> Hint: The map \( \displaystyle{\psi_{\alpha}(z)=\frac{\alpha-z}{1-\mkern 1.5mu\overline{\mkern-1.5mu\alpha\mkern-1.5mu}\mkern 1.5muz}} \) may be useful.

### ? {#section-93}

Find a conformal map from \( D = \{z :\  |z| < 1,\ |z - 1/2| > 1/2\} \) to the unit disk \( \Delta=\{z: \ |z|<1\} \).

### ? {#section-94}

Let \( f(z) \) be entire and assume values of \( f(z) \) lie outside a *bounded* open set \( \Omega \). Show without using Picard's theorems that \( f(z) \) is a constant.

### ? {#section-95}

(1) Assume \( \displaystyle f(z) = \sum_{n=0}^\infty c_n z^n \) converges in \( |z| < R \). Show that for \( r <R \),
    \[\frac{1}{2 \pi} \int_0^{2 \pi} |f(r e^{i \theta})|^2 d \theta
    = \sum_{n=0}^\infty |c_n|^2 r^{2n} \; .\]

(2) Deduce Liouville's theorem from (1).

### ? {#section-96}

Let \( f(z) \) be entire and assume that \( f(z) \leq M |z|^2 \) outside some disk for some constant \( M \). Show that \( f(z) \) is a polynomial in \( z \) of degree \( \leq 2 \).

### ? {#section-97}

Let \( a_n(z) \) be an analytic sequence in a domain \( D \) such that \( \displaystyle \sum_{n=0}^\infty |a_n(z)| \) converges uniformly on bounded and closed sub-regions of \( D \). Show that \( \displaystyle \sum_{n=0}^\infty |a'_n(z)| \) converges uniformly on bounded and closed sub-regions of \( D \).

### ? {#section-98}

Let \( f(z) \) be analytic in an open set \( \Omega \) except possibly at a point \( z_0 \) inside \( \Omega \). Show that if \( f(z) \) is bounded in near \( z_0 \), then \( \displaystyle \int_\Delta f(z) dz = 0 \) for all triangles \( \Delta \) in \( \Omega \).

### ? {#section-99}

Assume \( f \) is continuous in the region: \( 0< |z-a| \leq R, \; 0 \leq \arg(z-a) \leq \beta_0 \) (\( 0 < \beta_0 \leq 2 \pi \)) and the limit \( \displaystyle \lim_{z \rightarrow a} (z-a) f(z) = A \) exists. Show that
\[\lim_{r \rightarrow 0} \int_{\gamma_r} f(z) dz  = i A \beta_0 \; , \; \;\]
where \( \gamma_r : = \{ z \; | \; z = a + r e^{it}, \; 0 \leq t \leq \beta_0 \}. \)

### ? {#section-100}

Show that \( f(z) = z^2 \) is uniformly continuous in any open disk \( |z| < R \), where \( R>0 \) is fixed, but it is not uniformly continuous on \( \mathbb C \).

### ? {#section-101}

(1) Show that the function \( u=u(x,y) \) given by
    \[u(x,y)=\frac{e^{ny}-e^{-ny}}{2n^2}\sin nx\quad \text{for}\ n\in {\mathbf N}\]
    is the solution on \( D=\{(x,y)\ | x^2+y^2<1\} \) of the Cauchy problem for the Laplace equation
    \[\frac{\partial ^2u}{\partial x^2}+\frac{\partial ^2u}{\partial y^2}=0,\quad
    u(x,0)=0,\quad \frac{\partial u}{\partial y}(x,0)=\frac{\sin nx}{n}.\]
(2) Show that there exist points \( (x,y)\in D \) such that \( \displaystyle{\limsup_{n\to\infty} |u(x,y)|=\infty} \).

## Fall 2011

### ? {#section-102}

(1) Assume \( \displaystyle f(z) = \sum_{n=0}^\infty c_n z^n \) converges in \( |z| < R \). Show that for \( r <R \),
    \[\frac{1}{2 \pi} \int_0^{2 \pi} |f(r e^{i \theta})|^2 d \theta =
    \sum_{n=0}^\infty |c_n|^2 r^{2n} \; .\]

(2) Deduce Liouville's theorem from (1).

### ? {#section-103}

Let \( f \) be a continuous function in the region
\[D=\{z\ |  |z|>R, 0\leq \arg Z\leq \theta\}\quad\text{where}\quad
0\leq \theta \leq 2\pi.\]
If there exists \( k \) such that \( \displaystyle{\lim_{z\to\infty} zf(z)=k} \) for \( z \) in the region \( D \). Show that
\[\lim_{R'\to\infty} \int_{L} f(z) dz=i\theta k,\]
where \( L \) is the part of the circle \( |z|=R' \) which lies in the region \( D \).

### ? {#section-104}

Suppose that \( f \) is an analytic function in the region \( D \) which contains the point \( a \). Let
\[F(z)= z-a-qf(z),\quad \text{where}\quad q \ \text{is a complex
parameter}.\]

(1) Let \( K\subset D \) be a circle with the center at point \( a \) and also we assume that \( f(z)\not =0 \) for \( z\in K \). Prove that the function \( F \) has one and only one zero \( z=w \) on the closed disc \( \mkern 1.5mu\overline{\mkern-1.5muK\mkern-1.5mu}\mkern 1.5mu \) whose boundary is the circle \( K \) if \( \displaystyle{ |q|<\min_{z\in K} \frac{|z-a|}{|f(z)|}.} \)\

(2) Let \( G(z) \) be an analytic function on the disk \( \mkern 1.5mu\overline{\mkern-1.5muK\mkern-1.5mu}\mkern 1.5mu \). Apply the residue theorem to prove that \( \displaystyle{ \frac{G(w)}{F'(w)}=\frac{1}{2\pi i}\int_K \frac{G(z)}{F(z)} dz,} \) where \( w \) is the zero from (1).\

(3) If \( z\in K \), prove that the function \( \displaystyle{\frac{1}{F(z)}} \) can be represented as a convergent series with respect to \( q \): \( \displaystyle{ \frac{1}{F(z)}=\sum_{n=0}^{\infty} \frac{(qf(z))^n}{(z-a)^{n+1}}.} \)

### ? {#section-105}

Evaluate \( \displaystyle{ \int_{0}^{\infty}\frac{x\sin x}{x^2+a^2} \, dx } \).

### ? {#section-106}

Let \( f=u+iv \) be differentiable (i.e. \( f'(z) \) exists) with continuous partial derivatives at a point \( z=re^{i\theta} \), \( r\not= 0 \). Show that
\[\frac{\partial u}{\partial r}=\frac{1}{r}\frac{\partial v}{\partial \theta},\quad
\frac{\partial v}{\partial r}=-\frac{1}{r}\frac{\partial u}{\partial \theta}.\]

### ? {#section-107}

Show that \( \displaystyle \int_0^\infty \frac{x^{a-1}}{1+x^n} dx=\frac{\pi}{n\sin \frac{a\pi}{n}} \) using complex analysis, \( 0< a < n \). Here \( n \) is a positive integer.

### ? {#section-108}

For \( s>0 \), the **gamma function** is defined by \( \displaystyle{\Gamma(s)=\int_0^{\infty} e^{-t}t^{s-1} dt} \).

1.  Show that the gamma function is analytic in the half-plane \( \Re (s)>0 \), and is still given there by the integral formula above.

2.  Apply the formula in the previous question to show that
    \[\Gamma(s)\Gamma(1-s)=\frac{\pi}{\sin \pi s}.\]

> Hint: You may need \( \displaystyle{\Gamma(1-s)=t \int_0^{\infty}e^{-vt}(vt)^{-s} dv} \) for \( t>0 \).

### ? {#section-109}

Apply Rouché's Theorem to prove the Fundamental Theorem of Algebra: If
\[P_n(z) = a_0 + a_1z + \cdots + a_{n-1}z^{n-1} + a_nz^n\quad  (a_n \neq 0)\]
is a polynomial of degree n, then it has n zeros in \( \mathbb C \).

### ? {#section-110}

Suppose \( f \) is entire and there exist \( A, R >0 \) and natural number \( N \) such that
\[|f(z)| \geq A |z|^N\ \text{for}\ |z| \geq R.\]
Show that (i) \( f \) is a polynomial and (ii) the degree of \( f \) is at least \( N \).

### ? {#section-111}

Let \( f: {\mathbb C} \rightarrow {\mathbb C} \) be an injective analytic (also called univalent) function. Show that there exist complex numbers \( a \neq 0 \) and \( b \) such that \( f(z) = az + b \).

### ? {#section-112}

Let \( g \) be analytic for \( |z|\leq 1 \) and \( |g(z)| < 1 \) for \( |z| = 1 \).

-   Show that \( g \) has a unique fixed point in \( |z| < 1 \).

-   What happens if we replace \( |g(z)| < 1 \) with \( |g(z)|\leq 1 \) for \( |z|=1 \)? Give an example if (a) is not true or give an proof if (a) is still true.

-   What happens if we simply assume that \( f \) is analytic for \( |z| < 1 \) and \( |f(z)| < 1 \) for \( |z| < 1 \)? Suppose that \( f(z) \not\equiv z \). Can f have more than one fixed point in \( |z| < 1 \)?

> Hint: The map \( \displaystyle{\psi_{\alpha}(z)=\frac{\alpha-z}{1-\mkern 1.5mu\overline{\mkern-1.5mu\alpha\mkern-1.5mu}\mkern 1.5muz}} \) may be useful.

### ? {#section-113}

Find a conformal map from \( D = \{z :\  |z| < 1,\ |z - 1/2| > 1/2\} \) to the unit disk \( \Delta=\{z: \ |z|<1\} \).

### ? {#section-114}

Let \( f(z) \) be entire and assume values of \( f(z) \) lie outside a *bounded* open set \( \Omega \). Show without using Picard's theorems that \( f(z) \) is a constant.

### ? {#section-115}

Let \( f(z) \) be entire and assume values of \( f(z) \) lie outside a *bounded* open set \( \Omega \). Show without using Picard's theorems that \( f(z) \) is a constant.

### ? {#section-116}

(1) Assume \( \displaystyle f(z) = \sum_{n=0}^\infty c_n z^n \) converges in \( |z| < R \). Show that for \( r <R \),
    \[\frac{1}{2 \pi} \int_0^{2 \pi} |f(r e^{i \theta})|^2 d \theta
    = \sum_{n=0}^\infty |c_n|^2 r^{2n} \; .\]

(2) Deduce Liouville's theorem from (1).

### ? {#section-117}

Let \( f(z) \) be entire and assume that \( f(z) \leq M |z|^2 \) outside some disk for some constant \( M \). Show that \( f(z) \) is a polynomial in \( z \) of degree \( \leq 2 \).

### ? {#section-118}

Let \( a_n(z) \) be an analytic sequence in a domain \( D \) such that \( \displaystyle \sum_{n=0}^\infty |a_n(z)| \) converges uniformly on bounded and closed sub-regions of \( D \). Show that \( \displaystyle \sum_{n=0}^\infty |a'_n(z)| \) converges uniformly on bounded and closed sub-regions of \( D \).

### ? {#section-119}

Let \( f(z) \) be analytic in an open set \( \Omega \) except possibly at a point \( z_0 \) inside \( \Omega \). Show that if \( f(z) \) is bounded in near \( z_0 \), then \( \displaystyle \int_\Delta f(z) dz = 0 \) for all triangles \( \Delta \) in \( \Omega \).

### ? {#section-120}

Assume \( f \) is continuous in the region: \( 0< |z-a| \leq R, \; 0 \leq \arg(z-a) \leq \beta_0 \) (\( 0 < \beta_0 \leq 2 \pi \)) and the limit \( \displaystyle \lim_{z \rightarrow a} (z-a) f(z) = A \) exists. Show that
\[\lim_{r \rightarrow 0} \int_{\gamma_r} f(z) dz  = i A \beta_0 \; , \; \;\]
where \( \gamma_r : = \{ z \; | \; z = a + r e^{it}, \; 0 \leq t \leq \beta_0 \}. \)

### ? {#section-121}

Show that \( f(z) = z^2 \) is uniformly continuous in any open disk \( |z| < R \), where \( R>0 \) is fixed, but it is not uniformly continuous on \( \mathbb C \).

(1) Show that the function \( u=u(x,y) \) given by
    \[u(x,y)=\frac{e^{ny}-e^{-ny}}{2n^2}\sin nx\quad \text{for}\ n\in {\mathbf N}\]
    is the solution on \( D=\{(x,y)\ | x^2+y^2<1\} \) of the Cauchy problem for the Laplace equation
    \[\frac{\partial ^2u}{\partial x^2}+\frac{\partial ^2u}{\partial y^2}=0,\quad
    u(x,0)=0,\quad \frac{\partial u}{\partial y}(x,0)=\frac{\sin nx}{n}.\]
(2) Show that there exist points \( (x,y)\in D \) such that \( \displaystyle{\limsup_{n\to\infty} |u(x,y)|=\infty} \).

## Spring 2014

### ? {#section-122}

The question provides some insight into Cauchy's theorem. Solve the problem without using the Cauchy theorem.

1.  Evaluate the integral \( \displaystyle{\int_{\gamma} z^n dz} \) for all integers \( n \). Here \( \gamma \) is any circle centered at the origin with the positive (counterclockwise) orientation.

2.  Same question as (a), but with \( \gamma \) any circle not containing the origin.

3.  Show that if \( |a|<r<|b| \), then \( \displaystyle{\int_{\gamma}\frac{dz}{(z-a)(z-b)} dz=\frac{2\pi i}{a-b}} \). Here \( \gamma \) denotes the circle centered at the origin, of radius \( r \), with the positive orientation.

### ? {#section-123}

(1) Assume the infinite series \( \displaystyle \sum_{n=0}^\infty c_n z^n \) converges in \( |z| < R \) and let \( f(z) \) be the limit. Show that for \( r <R \),
    \[\frac{1}{2 \pi} \int_0^{2 \pi} |f(r e^{i \theta})|^2 d \theta =
    \sum_{n=0}^\infty |c_n|^2 r^{2n} \; .\]

(2) Deduce Liouville's theorem from (1). Liouville's theorem: If \( f(z) \) is entire and bounded, then \( f \) is constant.

### ? {#section-124}

Let \( f \) be a continuous function in the region
\[D=\{z\ |  |z|>R, 0\leq \arg Z\leq \theta\}\quad\text{where}\quad
0\leq \theta \leq 2\pi.\]
If there exists \( k \) such that \( \displaystyle{\lim_{z\to\infty} zf(z)=k} \) for \( z \) in the region \( D \). Show that
\[\lim_{R'\to\infty} \int_{L} f(z) dz=i\theta k,\]
where \( L \) is the part of the circle \( |z|=R' \) which lies in the region \( D \).

### ? {#section-125}

Evaluate \( \displaystyle{ \int_{0}^{\infty}\frac{x\sin x}{x^2+a^2} \, dx } \).

### ? {#section-126}

Let \( f=u+iv \) be differentiable (i.e. \( f'(z) \) exists) with continuous partial derivatives at a point \( z=re^{i\theta} \), \( r\not= 0 \). Show that
\[\frac{\partial u}{\partial r}=\frac{1}{r}\frac{\partial v}{\partial \theta},\quad
\frac{\partial v}{\partial r}=-\frac{1}{r}\frac{\partial u}{\partial \theta}.\]

### ? {#section-127}

Show that \( \displaystyle \int_0^\infty \frac{x^{a-1}}{1+x^n} dx=\frac{\pi}{n\sin \frac{a\pi}{n}} \) using complex analysis, \( 0< a < n \). Here \( n \) is a positive integer.

### ? {#section-128}

For \( s>0 \), the **gamma function** is defined by \( \displaystyle{\Gamma(s)=\int_0^{\infty} e^{-t}t^{s-1} dt} \).

-   Show that the gamma function is analytic in the half-plane \( \Re (s)>0 \), and is still given there by the integral formula above.

-   Apply the formula in the previous question to show that
    \[\Gamma(s)\Gamma(1-s)=\frac{\pi}{\sin \pi s}.\]

> Hint: You may need \( \displaystyle{\Gamma(1-s)=t \int_0^{\infty}e^{-vt}(vt)^{-s} dv} \) for \( t>0 \).

### ? {#section-129}

Apply Rouché's Theorem to prove the Fundamental Theorem of Algebra: If
\[P_n(z) = a_0 + a_1z + \cdots + a_{n-1}z^{n-1} + a_nz^n\quad  (a_n \neq 0)\]
is a polynomial of degree n, then it has n zeros in \( \mathbf C \).

### ? {#section-130}

Suppose \( f \) is entire and there exist \( A, R >0 \) and natural number \( N \) such that
\[|f(z)| \geq A |z|^N\ \text{for}\ |z| \geq R.\]
Show that (i) \( f \) is a polynomial and (ii) the degree of \( f \) is at least \( N \).

### ? {#section-131}

Let \( f: {\mathbb C} \rightarrow {\mathbb C} \) be an injective analytic (also called univalent) function. Show that there exist complex numbers \( a \neq 0 \) and \( b \) such that \( f(z) = az + b \).

### ? {#section-132}

Let \( g \) be analytic for \( |z|\leq 1 \) and \( |g(z)| < 1 \) for \( |z| = 1 \).

-   Show that \( g \) has a unique fixed point in \( |z| < 1 \).

-   What happens if we replace \( |g(z)| < 1 \) with \( |g(z)|\leq 1 \) for \( |z|=1 \)? Give an example if (a) is not true or give an proof if (a) is still true.

-   What happens if we simply assume that \( f \) is analytic for \( |z| < 1 \) and \( |f(z)| < 1 \) for \( |z| < 1 \)? Suppose that \( f(z) \not\equiv z \). Can f have more than one fixed point in \( |z| < 1 \)?

> Hint: The map \( \displaystyle{\psi_{\alpha}(z)=\frac{\alpha-z}{1-\mkern 1.5mu\overline{\mkern-1.5mu\alpha\mkern-1.5mu}\mkern 1.5muz}} \) may be useful.

### ? {#section-133}

Find a conformal map from \( D = \{z :\  |z| < 1,\ |z - 1/2| > 1/2\} \) to the unit disk \( \Delta=\{z: \ |z|<1\} \).

## Fall 2015

### ? {#section-134}

Let \( a_n \neq 0 \) and assume that \( \displaystyle \lim_{n \rightarrow \infty} \frac{|a_{n+1}|}{|a_n|} = L \). Show that \( \displaystyle \lim_{n \rightarrow \infty} \sqrt[n]{|a_n|} = L. %p_n^{\frac{1}{n}} = L. \) In particular, this shows that when applicable, the ratio test can be used to calculate the radius of convergence of a power series.

### ? {#section-135}

(a) Let \( z, w \) be complex numbers, such that \( \mkern 1.5mu\overline{\mkern-1.5muz\mkern-1.5mu}\mkern 1.5mu w \neq 1 \). Prove that
    \[{\left\lvert {\frac{w - z}{1 - \mkern 1.5mu\overline{\mkern-1.5muw\mkern-1.5mu}\mkern 1.5mu z}} \right\rvert} < 1 \; \; \; \mbox{if} \; |z| < 1 \; \mbox{and}\; |w| < 1,\]
    and also that
    \[{\left\lvert {\frac{w - z}{1 - \mkern 1.5mu\overline{\mkern-1.5muw\mkern-1.5mu}\mkern 1.5mu z}} \right\rvert} = 1 \; \; \; \mbox{if} \; |z| = 1 \; \mbox{or}\; |w| = 1.\]

(b) Prove that for fixed \( w \) in the unit disk \( \mathbb D \), the mapping
    \[F: z \mapsto \frac{w - z}{1 - \mkern 1.5mu\overline{\mkern-1.5muw\mkern-1.5mu}\mkern 1.5mu z}\]
    satisfies the following conditions:

(c) \( F \) maps \( \mathbb D \) to itself and is holomorphic. 

```{=html}
<!-- -->
```
(ii) \( F \) interchanges \( 0 \) and \( w \), namely, \( F(0) = w \) and \( F(w) = 0 \).

(iii) \( |F(z)| = 1 \) if \( |z| = 1 \).

(iv) \( F: {\mathbb D} \mapsto {\mathbb D} \) is bijective.

> Hint: Calculate \( F \circ F \).

### ? {#section-136}

Use \( n \)-th roots of unity (i.e. solutions of \( z^n - 1 =0 \)) to show that
\[2^{n-1} \sin\frac{\pi}{n} \sin\frac{2\pi}{n} \cdots \sin\frac{(n-1)\pi}{n}
= n
\; .\]

> Hint: \( 1 - \cos 2 \theta = 2 \sin^2 \theta,\; \sin 2 \theta = 2 \sin \theta \cos \theta \).

(a) Show that in polar coordinates, the Cauchy-Riemann equations take the form

\[\frac{\partial u}{\partial r} = \frac{1}{r} \frac{\partial v}{\partial \theta}
\; \; \; \text{and} \; \; \;
\frac{\partial v}{\partial r} = - \frac{1}{r} \frac{\partial u}{\partial \theta}\]

(b) Use these equations to show that the logarithm function defined by
    \[\log z = \log r + i \theta \; \;
    \mbox{where} \; z = r e^{i \theta } \; \mbox{with} \; - \pi < \theta < \pi\]
    is a holomorphic function in the region \( r>0, \; - \pi < \theta < \pi \). Also show that \( \log z \) defined above is not continuous in \( r>0 \).

### ? {#section-137}

Assume \( f \) is continuous in the region: \( x \geq x_0, \; 0 \leq y \leq b \) and the limit
\[\displaystyle \lim_{x \rightarrow + \infty} f(x + iy) = A\]
exists uniformly with respect to \( y \) (independent of \( y \)). Show that
\[\lim_{x \rightarrow + \infty} \int_{\gamma_x} f(z) dz  = iA b \; , \; \;\]
where \( \gamma_x : = \{ z \; | \; z = x + it, \; 0 \leq t \leq b\}. \)

### ? {#section-138}

(Cauchy's formula for "exterior" region) Let \( \gamma \) be piecewise smooth simple closed curve with interior \( \Omega_1 \) and exterior \( \Omega_2 \). Assume \( f'(z) \) exists in an open set containing \( \gamma \) and \( \Omega_2 \) and \( \lim_{z \rightarrow \infty } f(z) = A \). Show that
\[\frac{1}{2 \pi i} \int_\gamma \frac{f(\xi)}{\xi - z} \, d \xi =
\begin{cases}
A,          &     \text{if\ $z \in \Omega_1$}, \\
-f (z) + A, &  \text{if\ $z \in \Omega_2$}
\end{cases}\]

### ? {#section-139}

Let \( f(z) \) be bounded and analytic in \( \mathbb C \). Let \( a \neq b \) be any fixed complex numbers. Show that the following limit exists
\[\lim_{R \rightarrow \infty} \int_{|z|=R} \frac{f(z)}{(z-a)(z-b)} dz.\]
Use this to show that \( f(z) \) must be a constant (Liouville's theorem).

### ? {#section-140}

Prove by *justifying all steps* that for all \( \xi \in {\mathbb C} \) we have \( \displaystyle e^{- \pi \xi^2} = \int_{- \infty}^\infty e^{- \pi x^2} e^{2 \pi i x \xi} dx \; . \)

> Hint: You may use that fact in Example 1 on p. 42 of the textbook without proof, i.e., you may assume the above is true for real values of \( \xi \).

### ? {#section-141}

Suppose that \( f \) is holomorphic in an open set containing the closed unit disc, except for a pole at \( z_0 \) on the unit circle. Let \( \displaystyle %f(z) = \sum_{n = 1}^\infty a_n z^n f(z) = \sum_{n = 1}^\infty c_n z^n \) denote the the power series in the open disc. Show that (1) \( c_n \neq 0 \) for all large enough \( n \)'s, and (2) \( \displaystyle \lim_{n \rightarrow \infty} \frac{c_n}{c_{n+1}}= z_0 \).

### ? {#section-142}

Let \( f(z) \) be a non-constant analytic function in \( |z|>0 \) such that \( f(z_n) = 0 \) for infinite many points \( z_n \) with \( \lim_{n \rightarrow \infty} z_n =0 \). Show that \( z=0 \) is an essential singularity for \( f(z) \). (An example of such a function is \( f(z) = \sin (1/z) \).)

### ? {#section-143}

Let \( f \) be entire and suppose that \( \lim_{z \rightarrow \infty} f(z) = \infty \). Show that \( f \) is a polynomial.

### ? {#section-144}

Expand the following functions into Laurent series in the indicated regions:

(a) \( \displaystyle f(z) = \frac{z^2 - 1}{ (z+2)(z+3)}, \; \; 2 < |z| < 3 \), \( 3 < |z| < + \infty \).

(b) \( \displaystyle f(z) = \sin \frac{z}{1-z}, \; \; 0 < |z-1| < + \infty \)

### ? {#section-145}

Assume \( f(z) \) is analytic in region \( D \) and \( \Gamma \) is a rectifiable curve in \( D \) with interior in \( D \). Prove that if \( f(z) \) is real for all \( z \in \Gamma \), then \( f(z) \) is a constant.

### ? {#section-146}

Find the number of roots of \( z^4 - 6z + 3 =0 \) in \( |z|<1 \) and \( 1 < |z| < 2 \) respectively.

### ? {#section-147}

Prove that \( z^4 + 2 z^3 - 2z + 10 =0 \) has exactly one root in each open quadrant.

### ? {#section-148}

(1) Let \( f(z) \in H({\mathbb D}) \), \( \text{Re}(f(z)) >0 \), \( f(0)= a>0 \). Show that
    \[|\frac{f(z)-a}{f(z)+a}| \leq |z|, \; \; \;
    |f'(0)| \leq 2a.\]

(2) Show that the above is still true if \( \text{Re}(f(z)) >0 \) is replaced with \( \text{Re}(f(z)) \geq 0 \).

### ? {#section-149}

Assume \( f(z) \) is analytic in \( {\mathbb D} \) and \( f(0)=0 \) and is not a rotation (i.e. \( f(z) \neq e^{i \theta} z \)). Show that \( \displaystyle \sum_{n=1}^\infty f^{n}(z) \) converges uniformly to an analytic function on compact subsets of \( {\mathbb D} \), where \( f^{n+1}(z) = f(f^{n}(z)) \).

### ? {#section-150}

Let \( f(z) = \sum_{n=0}^\infty c_n z^n \) be analytic and one-to-one in \( |z| < 1 \). For \( 0<r<1 \), let \( D_r \) be the disk \( |z|<r \). Show that the area of \( f(D_r) \) is finite and is given by
\[S = \pi \sum_{n=1}^\infty n |c_n|^2 r^{2n}.\]
(Note that in general the area of \( f(D_1) \) is infinite.)

### ? {#section-151}

Let \( f(z) = \sum_{n= -\infty}^\infty c_n z^n \) be analytic and one-to-one in \( r_0< |z| < R_0 \). For \( r_0<r<R<R_0 \), let \( D(r,R) \) be the annulus \( r<|z|<R \). Show that the area of \( f(D(r,R)) \) is finite and is given by
\[S = \pi \sum_{n=- \infty}^\infty n |c_n|^2 (R^{2n} - r^{2n}).\]

## Spring 2015

### ? {#section-152}

Let \( a_n(z) \) be an analytic sequence in a domain \( D \) such that \( \displaystyle \sum_{n=0}^\infty |a_n(z)| \) converges uniformly on bounded and closed sub-regions of \( D \). Show that \( \displaystyle \sum_{n=0}^\infty |a'_n(z)| \) converges uniformly on bounded and closed sub-regions of \( D \).

### ? {#section-153}

Let \( f_n, f \) be analytic functions on the unit disk \( {\mathbb D} \). Show that the following are equivalent.

(i) \( f_n(z) \) converges to \( f(z) \) uniformly on compact subsets in \( \mathbb D \).

(ii) \( \int_{|z|= r} |f_n(z) - f(z)| \, |dz| \) converges to \( 0 \) if \( 0< r<1 \).

### ? {#section-154}

Let \( f \) and \( g \) be non-zero analytic functions on a region \( \Omega \). Assume \( |f(z)| = |g(z)| \) for all \( z \) in \( \Omega \). Show that \( f(z) = e^{i \theta} g(z) \) in \( \Omega \) for some \( 0 \leq \theta < 2 \pi \).

### ? {#section-155}

Suppose \( f \) is analytic in an open set containing the unit disc \( \mathbb D \) and \( |f(z)| =1 \) when \( |z| \)=1. Show that either \( f(z) = e^{i \theta} \) for some \( \theta \in \mathbb R \) or there are finite number of \( z_k \in \mathbb D \), \( k \leq n \) and \( \theta \in \mathbb R \) such that \( \displaystyle f(z) = e^{i\theta} \prod_{k=1}^n \frac{z-z_k}{1 - \mkern 1.5mu\overline{\mkern-1.5muz\mkern-1.5mu}\mkern 1.5mu_k z } \, . \)

> Also cf. Stein et al, 1.4.7, 3.8.17

### ? {#section-156}

(1) Let \( p(z) \) be a polynomial, \( R>0 \) any positive number, and \( m \geq 1 \) an integer. Let \( M_R = \sup \{ |z^{m} p(z) - 1|: |z| = R \} \). Show that \( M_R>1 \).

(2) Let \( m \geq 1 \) be an integer and \( K = \{z \in {\mathbb C}: r \leq |z| \leq R \} \) where \( r<R \). Show (i) using (1) as well as, (ii) without using (1) that there exists a positive number \( \varepsilon_0>0 \) such that for each polynomial \( p(z) \),
    \[\sup \{|p(z) - z^{-m}|: z \in K  \} \geq \varepsilon_0 \, .\]

### ? {#section-157}

Let \( \displaystyle f(z) = \frac{1}{z} + \frac{1}{z^2 -1} \). Find all the Laurent series of \( f \) and describe the largest annuli in which these series are valid.

### ? {#section-158}

Suppose \( f \) is entire and there exist \( A, R >0 \) and natural number \( N \) such that \( |f(z)| \leq A |z|^N \) for \( |z| \geq R \). Show that (i) \( f \) is a polynomial and (ii) the degree of \( f \) is at most \( N \).

### ? {#section-159}

Suppose \( f \) is entire and there exist \( A, R >0 \) and natural number \( N \) such that \( |f(z)| \geq A |z|^N \) for \( |z| \geq R \). Show that (i) \( f \) is a polynomial and (ii) the degree of \( f \) is at least \( N \).

### ? {#section-160}

(1) Explicitly write down an example of a non-zero analytic function in \( |z|<1 \) which has infinitely zeros in \( |z|<1 \).

(2) Why does not the phenomenon in (1) contradict the uniqueness theorem?

### ? {#section-161}

(1) Assume \( u \) is harmonic on open set \( O \) and \( z_n \) is a sequence in \( O \) such that \( u(z_n) = 0 \) and \( \lim z_n \in O \). Prove or disprove that \( u \) is identically zero. What if \( O \) is a region?

(2) Assume \( u \) is harmonic on open set \( O \) and \( u(z) = 0 \) on a disc in \( O \). Prove or disprove that \( u \) is identically zero. What if \( O \) is a region?

(3) Formulate and prove a Schwarz reflection principle for harmonic functions

> cf. Theorem 5.6 on p.60 of Stein et al.

> Hint: Verify the mean value property for your new function obtained by Schwarz reflection principle.

### ? {#section-162}

Let \( f \) be holomorphic in a neighborhood of \( D_r(z_0) \). Show that for any \( s<r \), there exists a constant \( c>0 \) such that
\[||f||_{(\infty, s)} \leq c ||f||_{(1, r)},\]
where \( \displaystyle |f||_{(\infty, s)} = \text{sup}_{z \in D_s(z_0)}|f(z)| \) and \( \displaystyle ||f||_{(1, r)} = \int_{D_r(z_0)} |f(z)|dx dy \).

> Note: Exercise 3.8.20 on p.107 in Stein et al is a straightforward consequence of this stronger result using the integral form of the Cauchy-Schwarz inequality in real analysis.

### ? {#section-163}

(1) Let \( f \) be analytic in \( \Omega: 0<|z-a|<r \) except at a sequence of poles \( a_n \in \Omega \) with \( \lim_{n \rightarrow \infty} a_n = a \). Show that for any \( w \in \mathbb C \), there exists a sequence \( z_n \in \Omega \) such that \( \lim_{n \rightarrow \infty} f(z_n) = w \).

(2) Explain the similarity and difference between the above assertion and the Weierstrass-Casorati theorem.

### ? {#section-164}

Compute the following integrals.

\( i \) \( \displaystyle \int_0^\infty \frac{1}{(1 + x^n)^2} \, dx \), \( n \geq 1 \) (ii) \( \displaystyle \int_0^\infty \frac{\cos x}{(x^2 + a^2)^2} \, dx \), \( a \in \mathbb R \) (iii) \( \displaystyle \int_0^\pi \frac{1}{a + \sin \theta} \, d \theta \), \( a>1 \)

\( iv \) \( \displaystyle \int_0^{\frac{\pi}{2}} \frac{d \theta}{a+ \sin ^2 \theta}, \) \( a >0 \). (v) \( \displaystyle \int_{|z|=2} \frac{1}{(z^{5} -1) (z-3)} \, dz \) (v) \( \displaystyle \int_{- \infty}^{\infty} \frac{\sin \pi a}{\cosh \pi x + \cos \pi a} e^{- i x \xi} \, d x \), \( 0< a <1 \), \( \xi \in \mathbb R \) (vi) \( \displaystyle \int_{|z| = 1} \cot^2 z \, dz \).

### ? {#section-165}

Compute the following integrals.

\( i \) \( \displaystyle \int_0^\infty \frac{\sin x}{x} \, dx \) (ii) \( \displaystyle \int_0^\infty (\frac{\sin x}{x})^2 \, dx \) (iii) \( \displaystyle \int_0^\infty \frac{x^{a-1}}{(1 + x)^2} \, dx \), \( 0< a < 2 \)

\( i \) \( \displaystyle \int_0^\infty \frac{\cos a x - \cos bx}{x^2} dx \), \( a, b >0 \) (ii) \( \displaystyle \int_0^\infty \frac{x^{a-1}}{1 + x^n} \, dx \), \( 0< a < n \)

\( iii \) \( \displaystyle \int_0^\infty \frac{\log x}{1 + x^n} \, dx \), \( n \geq 2 \) (iv) \( \displaystyle \int_0^\infty \frac{\log x}{(1 + x^2)^2} dx \) (v) \( \displaystyle \int_0^{\pi} \log|1 - a \sin \theta| d \theta \), \( a \in \mathbb C \)

### ? {#section-166}

Let \( 0<r<1 \). Show that polynomials \( P_n(z) = 1 + 2z + 3 z^2 + \cdots + n z^{n-1} \) have no zeros in \( |z|<r \) for all sufficiently large \( n \)'s.

### ? {#section-167}

Let \( f \) be an analytic function on a region \( \Omega \). Show that \( f \) is a constant if there is a simple closed curve \( \gamma \) in \( \Omega \) such that its image \( f(\gamma) \) is contained in the real axis.

### ? {#section-168}

(1) Show that \( \displaystyle \frac{\pi^2}{\sin^2 \pi z} \) and \( \displaystyle g(z) = \sum_{n = - \infty}^{ \infty} \frac{1}{(z-n)^2} \) have the same principal part at each integer point.

(2) Show that \( \displaystyle h(z) = \frac{\pi^2}{\sin^2 \pi z} - g(z) \) is bounded on \( \mathbb C \) and conclude that \( \displaystyle \frac{\pi^2}{\sin^2 \pi z} = \sum_{n = - \infty}^{ \infty} \frac{1}{(z-n)^2} \, . \)

### ? {#section-169}

Let \( f(z) \) be an analytic function on \( {\mathbb C} \backslash \{ z_0 \} \), where \( z_0 \) is a fixed point. Assume that \( f(z) \) is bijective from \( {\mathbb C} \backslash \{ z_0 \} \) onto its image, and that \( f(z) \) is bounded outside \( D_r(z_0) \), where \( r \) is some fixed positive number. Show that there exist \( a, b, c, d \in \mathbb C \) with \( ad-bc \neq 0 \), \( c \neq 0 \) such that \( \displaystyle f(z) = \frac{az + b}{cz + d} \).

### ? {#section-170}

Assume \( f(z) \) is analytic in \( {\mathbb D}: |z|<1 \) and \( f(0)=0 \) and is not a rotation (i.e. \( f(z) \neq e^{i \theta} z \)). Show that \( \displaystyle \sum_{n=1}^\infty f^{n}(z) \) converges uniformly to an analytic function on compact subsets of \( {\mathbb D} \), where \( f^{n+1}(z) = f(f^{n}(z)) \).

### ? {#section-171}

Let \( f \) be a non-constant analytic function on \( \mathbb D \) with \( f(\mathbb D) \subseteq \mathbb D \). Use \( \psi_{a} (f(z)) \) (where \( a=f(0) \), \( \displaystyle \psi_a(z) = \frac{a - z}{1 - \mkern 1.5mu\overline{\mkern-1.5mua\mkern-1.5mu}\mkern 1.5muz} \)) to prove that \( \displaystyle \frac{|f(0)| - |z|}{1 + |f(0)||z|} \leq |f(z)| \leq \frac{|f(0)| + |z|}{1 - |f(0)||z|} \).

### ? {#section-172}

Find a conformal map

1.  from \( \{ z: |z - 1/2| > 1/2, \text{Re}(z)>0 \} \) to \( \mathbb H \)

2.  from \( \{ z: |z - 1/2| > 1/2, |z| <1 \} \) to \( \mathbb D \)

3.  from the intersection of the disk \( |z + i| < \sqrt{2} \) with \( {\mathbb H} \) to \( {\mathbb D} \).

4.  from \( {\mathbb D} \backslash [a, 1) \) to \( {\mathbb D} \backslash [0, 1) \) (\( 0<a<1) \).
    \[ Short solution
    possible using Blaschke factor\]

5.  from \( \{ z: |z| < 1, \text{Re}(z) > 0 \} \backslash (0, 1/2] \) to \( \mathbb H \).

### ? {#section-173}

Let \( C \) and \( C' \) be two circles and let \( z_1 \in C \), \( z_2 \notin C \), \( z'_1 \in C' \), \( z'_2 \notin C' \). Show that there is a unique fractional linear transformation \( f \) with \( f(C) = C' \) and \( f(z_1) = z'_1 \), \( f(z_2) = z'_2 \).

### ? {#section-174}

Assume \( f_n \in H(\Omega) \) is a sequence of holomorphic functions on the region \( \Omega \) that are uniformly bounded on compact subsets and \( f \in H(\Omega) \) is such that the set \( \displaystyle \{z \in \Omega: \lim_{n \rightarrow \infty} f_n(z) = f(z) \} \) has a limit point in \( \Omega \). Show that \( f_n \) converges to \( f \) uniformly on compact subsets of \( \Omega \).

### ? {#section-175}

Let \( \displaystyle{\psi_{\alpha}(z)=\frac{\alpha-z}{1-\mkern 1.5mu\overline{\mkern-1.5mu\alpha\mkern-1.5mu}\mkern 1.5muz}} \) with \( |\alpha|<1 \) and \( {\mathbb D}=\{z:\ |z|<1\} \). Prove that

-   \( \displaystyle{\frac{1}{\pi}\iint_{{\mathbb D}} |\psi'_{\alpha}|^2 dx dy =1} \).

-   \( \displaystyle{\frac{1}{\pi}\iint_{{\mathbb D}} |\psi'_{\alpha}| dx dy =\frac{1-|\alpha|^2}{|\alpha|^2} \log \frac{1}{1-|\alpha|^2}} \).

### ? {#section-176}

Prove that \( \displaystyle{f(z)=-\frac{1}{2}\left(z+\frac{1}{z}\right)} \) is a conformal map from half disc \( \{z=x+iy:\ |z|<1,\ y>0\} \) to upper half plane \( {\mathbb H}=\{z=x+iy:\ y>0\} \).

### ? {#section-177}

Let \( \Omega \) be a simply connected open set and let \( \gamma \) be a simple closed contour in \( \Omega \) and enclosing a bounded region \( U \) anticlockwise. Let \( f: \ \Omega \to {\mathbb C} \) be a holomorphic function and \( |f(z)|\leq M \) for all \( z\in \gamma \). Prove that \( |f(z)|\leq M \) for all \( z\in U \).

### ? {#section-178}

Compute the following integrals. (i) \( \displaystyle \int_0^\infty \frac{x^{a-1}}{1 + x^n} \, dx \), \( 0< a < n \) (ii) \( \displaystyle \int_0^\infty \frac{\log x}{(1 + x^2)^2}\, dx \)

### ? {#section-179}

Let \( 0<r<1 \). Show that polynomials \( P_n(z) = 1 + 2z + 3 z^2 + \cdots + n z^{n-1} \) have no zeros in \( |z|<r \) for all sufficiently large \( n \)'s.

### ? {#section-180}

Let \( f \) be holomorphic in a neighborhood of \( D_r(z_0) \). Show that for any \( s<r \), there exists a constant \( c>0 \) such that
\[\|f\|_{(\infty, s)} \leq c \|f\|_{(1, r)},\]
where \( \displaystyle \|f\|_{(\infty, s)} = \text{sup}_{z \in D_s(z_0)}|f(z)| \) and \( \displaystyle \|f\|_{(1, r)} = \int_{D_r(z_0)} |f(z)|dx dy \).

### ? {#section-181}

Let \( \displaystyle{\psi_{\alpha}(z)=\frac{\alpha-z}{1-\mkern 1.5mu\overline{\mkern-1.5mu\alpha\mkern-1.5mu}\mkern 1.5muz}} \) with \( |\alpha|<1 \) and \( {\mathbb D}=\{z:\ |z|<1\} \). Prove that

-   \( \displaystyle{\frac{1}{\pi}\iint_{{\mathbb D}} |\psi'_{\alpha}|^2 dx dy =1} \).

-   \( \displaystyle{\frac{1}{\pi}\iint_{{\mathbb D}} |\psi'_{\alpha}| dx dy =\frac{1-|\alpha|^2}{|\alpha|^2} \log \frac{1}{1-|\alpha|^2}} \).

Prove that \( \displaystyle{f(z)=-\frac{1}{2}\left(z+\frac{1}{z}\right)} \) is a conformal map from half disc \( \{z=x+iy:\ |z|<1,\ y>0\} \) to upper half plane \( \mathbb H=\{z=x+iy:\ y>0\} \).

### ? {#section-182}

Let \( \Omega \) be a simply connected open set and let \( \gamma \) be a simple closed contour in \( \Omega \) and enclosing a bounded region \( U \) anticlockwise. Let \( f: \ \Omega \to {\mathbb C} \) be a holomorphic function and \( |f(z)|\leq M \) for all \( z\in \gamma \). Prove that \( |f(z)|\leq M \) for all \( z\in U \).

### ? {#section-183}

Compute the following integrals. (i) \( \displaystyle \int_0^\infty \frac{x^{a-1}}{1 + x^n} \, dx \), \( 0< a < n \) (ii) \( \displaystyle \int_0^\infty \frac{\log x}{(1 + x^2)^2}\, dx \)

### ? {#section-184}

Let \( 0<r<1 \). Show that polynomials \( P_n(z) = 1 + 2z + 3 z^2 + \cdots + n z^{n-1} \) have no zeros in \( |z|<r \) for all sufficiently large \( n \)'s.

### ? {#section-185}

Let \( f \) be holomorphic in a neighborhood of \( D_r(z_0) \). Show that for any \( s<r \), there exists a constant \( c>0 \) such that
\[\|f\|_{(\infty, s)} \leq c \|f\|_{(1, r)},\]
where \( \displaystyle \|f\|_{(\infty, s)} = \text{sup}_{z \in D_s(z_0)}|f(z)| \) and \( \displaystyle \|f\|_{(1, r)} = \int_{D_r(z_0)} |f(z)|dx dy \).

## Fall 2016

### ? {#section-186}

Let \( u(x,y) \) be harmonic and have continuous partial derivatives of order three in an open disc of radius \( R>0 \).

(a) Let two points \( (a,b), (x,y) \) in this disk be given. Show that the following integral is independent of the path in this disk joining these points:
    \[v(x,y) = \int_{a,b}^{x,y} ( -\frac{\partial u}{\partial y}dx +  \frac{\partial u}{\partial x}dy).\]
    \

(b) ```{=tex}
    \hfill
    ```
    (i) Prove that \( u(x,y)+i v(x,y) \) is an analytic function in this disc.

    (ii) Prove that \( v(x,y) \) is harmonic in this disc.

### ? {#section-187}

(a) \( f(z)= u(x,y) +i v(x,y) \) be analytic in a domain \( D\subset {\mathbb C} \). Let \( z_0=(x_0,y_0) \) be a point in \( D \) which is in the intersection of the curves \( u(x,y)= c_1 \) and \( v(x,y)=c_2 \), where \( c_1 \) and \( c_2 \) are constants. Suppose that \( f'(z_0)\neq 0 \). Prove that the lines tangent to these curves at \( z_0 \) are perpendicular.

(b) Let \( f(z)=z^2 \) be defined in \( {\mathbb C} \).

(c) Describe the level curves of \( \mbox{\textrm Re}{(f)} \) and of \( \mbox{Im}{(f)} \).

```{=html}
<!-- -->
```
(ii) What are the angles of intersections between the level curves \( \mbox{\textrm Re}{(f)}=0 \) and \( \mbox{\textrm Im}{(f)} \)? Is your answer in agreement with part a) of this question?

### ? {#section-188}

(a) \( f: D\rightarrow {\mathbb C} \) be a continuous function, where \( D\subset {\mathbb C} \) is a domain.Let \( \alpha:[a,b]\rightarrow D \) be a smooth curve. Give a precise definition of the *complex line integral*
    \[\int_{\alpha} f.\]

(b) Assume that there exists a constant \( M \) such that \( |f(\tau)|\leq M \) for all \( \tau\in \mbox{\textrm Image}(\alpha \)). Prove that
    \[\big | \int_{\alpha} f \big |\leq M \times \mbox{\textrm length}(\alpha).\]

(c) Let \( C_R \) be the circle \( |z|=R \), described in the counterclockwise direction, where \( R>1 \). Provide an upper bound for \( \big | \int_{C_R} \dfrac{\log{(z)} }{z^2} \big |, \) which depends [only]{.ul} on \( R \) and other constants.

### ? {#section-189}

(a) Let Let \( f:{\mathbb C}\rightarrow {\mathbb C} \) be an entire function. Assume the existence of a non-negative integer \( m \), and of positive constants \( L \) and \( R \), such that for all \( z \) with \( |z|>R \) the inequality
    \[|f(z)| \leq L |z|^m\]
    holds. Prove that \( f \) is a polynomial of degree \( \leq m \).

(b) Let \( f:{\mathbb C}\rightarrow {\mathbb C} \) be an entire function. Suppose that there exists a real number M such that for all \( z\in {\mathbb C} \)
    \[\mbox{\textrm Re} (f) \leq M.\]
    Prove that \( f \) must be a constant.

### ? {#section-190}

Prove that all the roots of the complex polynomial
\[z^7 - 5 z^3 +12 =0\]
lie between the circles \( |z|=1 \) and \( |z|=2 \).

### ? {#section-191}

(a) Let \( F \) be an analytic function inside and on a simple closed curve \( C \), except for a pole of order \( m\geq 1 \) at \( z=a \) inside \( C \). Prove that

\[\frac{1}{2 \pi i}\oint_{C} F(\tau) d\tau = 
\lim_{\tau\rightarrow a} \frac{d^{m-1}}{d\tau^{m-1}}\big((\tau-a)^m F(\tau))\big).\]

(b) Evaluate
    \[\oint_{C}\frac{e^{\tau}}{(\tau^2+\pi^2)^2}d\tau\]
    where \( C \) is the circle \( |z|=4 \).

### ? {#section-192}

Find the conformal map that takes the upper half-plane comformally onto the half-strip \( \{ w=x+iy:\ -\pi/2<x<\pi/2\ y>0\} \).

### ? {#section-193}

Compute the integral \( \displaystyle{\int_{-\infty}^{\infty} \frac{e^{-2\pi ix\xi}}{\cosh\pi x}dx} \) where \( \displaystyle{\cosh z=\frac{e^{z}+e^{-z}}{2}} \).
