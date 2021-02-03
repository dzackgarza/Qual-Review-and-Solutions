```{=tex}
\def\contradiction
{
\tikz[baseline, x=0.2em, y=0.2em, line width=0.04em]
\draw (0,0) -- ({4*cos(45)},{4*sin(45)})
    (-1,1) -- ({-1 + 4*cos(45)},{1 + 4*sin(45)})
    (-1,3) -- ({-1 + 4*cos(315)},{3 + 4*sin(315)})
    (0,4) -- ({0 + 4*cos(315)},{4 + 4*sin(315)});
}
```
Exercises from Folland:

-   Chapter 1: Exercises 3, 7, 10, 12, 14 (with the sets in 3(a) being non-empty) Exercises 15, 17, 18, 19, 22(a), 24, 28 Exercises 26, 30 (also check out 31)

-   Chapter 2: Exercises 2, 3, 7, 9 (in 9(c) you can use Exercise 1.29 without proof Exercises 10, 12, 13, 14, 16, 19 Exercises 24, 25, 28(a,b), 33, 34, 35, 38, 41 (note that 24 shows that upper sums are not needed in the definition of integrals, and the extra hypotheses also show that they are not desired either) Exercises 40, 44, 47, 49, 50, 51, 52, 54, 56, 58, 59

-   Chapter 3: Exercises 3(b,c), 5, 6, 9, 12, 13, 14, 16, 20, 21, 22

# Basics

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Notation                                                                                                                                                                  Definition
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ---------------------------
                                                                                                                                                                            The Sup norm
  \[{\left\lVert {f} \right\rVert}_\infty \coloneqq\sup_{x\in \operatorname{dom}(f)} {\left\lvert {f(x)} \right\rvert}\]                                                    

                                                                                                                                                                            The \( L^ \infty \) norm
  \[ {\left\lVert {f} \right\rVert}_{L^\infty} \coloneqq\inf\left\{{M \geq 0 {~\mathrel{\Big|}~}{\left\lvert {f(x)} \right\rvert} \leq M \text{ for a.e. } x }\right\} \]   

                                                                                                                                                                            Convergence of a sequence
  \[ f_n \overset{n \to \infty }\to f \]                                                                                                                                    

                                                                                                                                                                            Vanishing at infinity
  \[ f(x) \overset{{\left\lvert {x} \right\rvert} \to \infty}\to 0 \]                                                                                                       

                                                                                                                                                                            Having small tails
  \[ \int_{{\left\lvert {x} \right\rvert} \geq N} f \overset{N\to \infty}\to 0 \]                                                                                           

                                                                                                                                                                            A Hilbert space
  \[ H, \mathcal{H} \]                                                                                                                                                      

                                                                                                                                                                            A topological space
  \[ X \]                                                                                                                                                                   
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Useful Techniques

-   General advice: try swapping the orders of limits, sums, integrals, etc.

-   Limits:

    -   Take the \( \limsup \) or \( \liminf \), which always exist, and aim for an inequality like
        \[  
        c \leq \liminf a_n \leq \limsup a_n \leq c
        .\]
    -   \( \lim f_n = \limsup f_n = \liminf f_n \) iff the limit exists, so to show some \( g \) is a limit, show
        \[  
        \limsup f_n \leq g \leq \liminf f_n \qquad (\implies g = \lim f) 
        .\]
    -   A limit does *not* exist if \( \liminf a_n > \limsup a_n \).

-   Sequences and Series

    -   If \( f_n \) has a global maximum (computed using \( f_n' \) and the first derivative test) \( M_n \to 0 \), then \( f_n \to 0 \) uniformly.
    -   For a fixed \( x \), if \( f = \sum f_n \) converges *uniformly* on some \( B_r(x) \) and each \( f_n \) is continuous at \( x \), then \( f \) is also continuous at \( x \) .

-   Equalities

    -   Split into upper and lower bounds:
        \[  
        a=b \iff a\leq b \text{ and }  a\geq b
        .\]
    -   Use an epsilon of room:
        \[  
        \qty{ \forall \epsilon, \,\,a < b + \varepsilon} \implies a\leq b 
        .\]
    -   Showing something is zero:
        \[  
        \qty{ \forall \epsilon, \,\, {\left\lVert {a} \right\rVert} < \varepsilon} \implies a = 0
        .\]

-   Continuity / differentiability: show it holds on \( [-M, M] \) for all \( M \) to get it to hold on \( {\mathbb{R}} \).

-   Simplifications:

    -   To show something for a measurable set, show it for bounded/compact/elementary sets/
    -   To show something for a function, show it for continuous, bounded, compactly supported, simple, indicator functions, \( L^1 \), etc
    -   Replace a continuous sequence (\( \varepsilon\to 0 \)) with an arbitrary countable sequence (\( x_n \to 0 \))
    -   Intersect with a ball \( B_r(\mathbf{0})\subset {\mathbb{R}}^n \).

-   Integrals

    -   Calculus techniques: Taylor series, IVT, MVT, etc.
    -   Break up \( {\mathbb{R}}^n = \left\{{{\left\lvert {x} \right\rvert} \leq 1}\right\} \coprod \left\{{{\left\lvert {x} \right\rvert} > 1}\right\} \).
        -   Or break integration region into disjoint annuli.
    -   Break up into \( \left\{{f>g}\right\} {\coprod}\left\{{f=g}\right\} {\coprod}\left\{{f< g}\right\} \).
    -   Tail estimates!
    -   Most of what works for integrals will work for sums.

-   Measure theory:

    -   Always consider bounded sets, and if \( E \) is unbounded write \( E = \cup_{n} B_{n}(0) \cap E \) and use countable subadditivity or continuity of measure.

    -   \( F_\sigma \) sets are Borel, so establish something for Borel sets and use this to extend it to Lebesgue.

    -   \( s = \inf\left\{{x\in X}\right\} \implies \) for every \( \varepsilon \) there is an \( x\in X \) such that \( x \leq s + \varepsilon \).

-   Approximate by dense subsets of functions

-   Useful facts about compactly supported (\( C_c({\mathbb{R}}) \)) continuous functions:

    -   Uniformly continuous
    -   Bounded almost everywhere

## Definitions

::: {.definition title="Uniform Continuity"}
\( f \) is uniformly continuous iff

\[
    &\forall \varepsilon \quad \exists \delta(\varepsilon) \mathrel{\Big|}\quad \forall x, y, \quad {\left\lvert {x - y} \right\rvert} < \delta \implies {\left\lvert {f(x) - f(y)} \right\rvert} < \varepsilon \\
\iff &\forall \varepsilon \quad \exists \delta(\varepsilon) \mathrel{\Big|}\quad \forall x, y, \quad {\left\lvert {y} \right\rvert} < \delta \implies {\left\lvert {f(x-y) - f(y)} \right\rvert} < \varepsilon
.\]
:::

::: {.definition title="Nowhere Dense Sets"}
A set \( S \) is **nowhere dense** iff the closure of \( S \) has empty interior iff every interval contains a subinterval that does not intersect \( S \).
:::

::: {.definition title="Meager Sets"}
A set is **meager** if it is a *countable* union of nowhere dense sets.
:::

::: {.definition title="$F_\\sigma$ and $G_\\delta$ Sets"}
An \( F_\sigma \) set is a union of closed sets, and a \( G_\delta \) set is an intersection of opens. [^1]
:::

::: {.definition title="Limsup/Liminf"}
\[  
\limsup_n a_n = \lim_{n\to \infty} \sup_{j\geq n} a_j &= \inf_{n\geq 0} \sup_{j\geq n} a_j \\ 
\liminf_n a_n = \lim_{n\to \infty} \inf_{j\geq n} a_j &= \sup_{n\geq 0} \inf_{j\geq n} a_j
.\]
:::

::: {.definition title="Topological Notions"}
Let \( X \) be a metric space and \( A \) a subset. Let \( A' \) denote the limit points of \( A \), and \( \mkern 1.5mu\overline{\mkern-1.5muA\mkern-1.5mu}\mkern 1.5mu \coloneqq A\cup A' \) to be its closure.

-   A **neighborhood** of \( p \) is an open set \( U_p \) containing \( p \).

-   An \( \varepsilon{\hbox{-}} \)**neighborhood** of \( p \) is an open ball \( B_r(p) \coloneqq\left\{{q {~\mathrel{\Big|}~}d(p, q) < r}\right\} \) for some \( r>0 \).

-   A point \( p\in X \) is an **accumulation point** of \( A \) iff every neighborhood \( U_p \) of \( p \) contains a point \( q\in Q \)

-   A point \( p\in X \) is a **limit point** of \( A \) iff every *punctured* neighborhood \( U_p\setminus\left\{{p}\right\} \) contains a point \( q\in A \).

-   If \( p\in A \) and \( p \) is not a limit point of \( A \), then \( p \) is an **isolated point** of \( A \).

-   \( A \) is **closed** iff \( A' \subset A \), so \( A \) contains all of its limit points.

-   A point \( p\in A \) is **interior** iff there is a neighborhood \( U_p \subset A \) that is strictly contained in \( A \).

-   \( A \) is **open** iff every point of \( A \) is interior.

-   \( A \) is **perfect** iff \( A \) is closed and \( A\subset A' \), so every point of \( A \) is a limit point of \( A \).

-   \( A \) is **bounded** iff there is a real number \( M \) and a point \( q\in X \) such that \( d(p, q) < M \) for all \( p\in A \).

-   \( A \) is **dense** in \( X \) iff every point \( x\in X \) is either a point of \( A \), so \( x\in A \), or a limit point of \( A \), so \( x\in A' \). I.e., \( X\subset A\cup A' \).

    -   Alternatively, \( \mkern 1.5mu\overline{\mkern-1.5muA\mkern-1.5mu}\mkern 1.5mu = X \), so the closure of \( A \) is \( X \).
:::

::: {.definition title="Uniform Convergence"}
\[
(\forall \varepsilon>0)\left(\exists n_{0} = n_0(\varepsilon) \right)(\forall x \in S)\left(\forall n>n_{0}\right)\left(\left|f_{n}(x)-f(x)\right|<\varepsilon\right)
.\]
Negated:[^2]
\[  
(\exists \varepsilon>0)\left(\forall n_{0} = n_0 (\varepsilon) \right)(\exists x = x(n_0) \in S)\left(\exists n>n_{0}\right)\left(\left|f_{n}(x)-f(x)\right| \geq \varepsilon\right)
.\]
:::

::: {.definition title="Pointwise Convergence"}
A sequence of functions \( \left\{{ f_j }\right\} \) is said to **converge pointwise** to \( f \) if and only if
\[  
(\forall \varepsilon>0)(\forall x \in S)\left(\exists n_{0} = n_0(x, \varepsilon) \right)\left(\forall n>n_{0}\right)\left(\left|f_{n}(x)-f(x)\right|<\varepsilon\right)
.\]
:::

::: {.definition title="Outer Measure"}
The **outer measure** of a set is given by
\[
m_*(E) \coloneqq\inf_{\substack{\left\{{Q_{i}}\right\} \rightrightarrows E \\ \text{closed cubes}}} \sum {\left\lvert {Q_{i}} \right\rvert}
.\]
:::

::: {.definition title="Limsup and Liminf of Sets"}
\[
\limsup_{n} A_{n} \coloneqq\cap_{n} \cup_{j\geq n} A_{j}&= \left\{{x {~\mathrel{\Big|}~}x\in A_{n} \text{ for inf. many $n$}}\right\}  \\
\liminf_{n} A_{n} \coloneqq\cup_{n} \cap_{j\geq n} A_{j} &= \left\{{x {~\mathrel{\Big|}~}x\in A_{n} \text{ for all except fin. many $n$}}\right\}  \\
.\]
:::

::: {.definition title="Lebesgue Measurable Sets"}
A subset \( E\subseteq {\mathbb{R}}^n \) is **Lebesgue measurable** iff for every \( \varepsilon> 0 \) there exists an open set \( O \supseteq E \) such that \( m_*(O\setminus E) < \varepsilon \). In this case, we define \( m(E) \coloneqq m_*(E) \).
:::

::: {.definition title="$L^+$: Measurable non-negative functions."}
\( f\in L^+ \) iff \( f \) is measurable and non-negative.
:::

::: {.definition title="Integrability"}
A measurable function is **integrable** iff \( {\left\lVert {f} \right\rVert}_1 < \infty \).
:::

::: {.definition title="The Infinity Norm"}
\[
{\left\lVert {f} \right\rVert}_\infty &\coloneqq\inf_{\alpha \geq 0} \left\{{\alpha {~\mathrel{\Big|}~}m\left\{{{\left\lvert {f} \right\rvert} \geq \alpha}\right\} = 0}\right\}
.\]
:::

::: {.definition title="Essentially Bounded Functions"}
A function \( f:X \to {\mathbb{C}} \) is **essentially bounded** iff there exists a real number \( c \) such that \( \mu(\left\{{{\left\lvert {f} \right\rvert} > x}\right\}) = 0 \), i.e. \( {\left\lVert {f} \right\rVert}_\infty < \infty \).
:::

::: {.definition title="$L^\\infty$"}
\[
L^\infty(X)
\coloneqq\left\{{f: X\to {\mathbb{C}}{~\mathrel{\Big|}~}f \text{ is essentially bounded }}\right\}
\coloneqq\left\{{f: X\to {\mathbb{C}}{~\mathrel{\Big|}~}{\left\lVert {f} \right\rVert}_{\infty }< \infty}\right\}
.\]
:::

::: {.definition title="Dual Norm"}
For \( X \) a normed vector space and \( \Lambda \in X^\vee \),
\[
{\left\lVert {\Lambda} \right\rVert}_{X^\vee} \coloneqq\sup_{\left\{{x\in X {~\mathrel{\Big|}~}{\left\lVert {x} \right\rVert}_X \leq 1}\right\}} {\left\lvert {f(x)} \right\rvert}
.\]
:::

::: {.definition title="Convolution"}
\[f * g(x)=\int f(x-y) g(y) d y .\]
:::

::: {.definition title="Fourier Transform"}
\[
\widehat{f}(\xi) = \int f(x) ~e^{2\pi i x \cdot \xi} ~dx
.\]
:::

::: {.definition title="Dilation"}
\[
\phi_{t}(x) = t^{-n} \phi\left(t^{-1} x\right)
.\]
:::

::: {.definition title="Approximations to the identity"}
For \( \phi\in L^1 \), the dilations satisfy \( \int \phi_{t} = \int \phi \), and if \( \int \phi = 1 \) then \( \phi \) is an **approximate identity**.
:::

::: {.definition title="Baire Space"}
A space \( X \) is a **Baire space** if and only if every countable intersections of open, dense sets is still dense.
:::

### Functional Analysis

::: {.definition title="Orthonormal sequence "}
A countable collection of elements \( \left\{{ u_i }\right\} \) is **orthonormal** if and only if

1.  \( {\left\langle {u_i},~{u_j} \right\rangle} = 0 \) for all \( j \neq k \) and
2.  \( {\left\lVert {u_j} \right\rVert}^2 \coloneqq{\left\langle {u_j},~{u_j} \right\rangle} = 1 \) for all \( j \).
:::

::: {.definition title="Basis of a Hilbert space"}
A set \( \left\{{u_{n}}\right\} \) is a **basis** for a Hilbert space \( {\mathcal{H}} \) iff it is dense in \( {\mathcal{H}} \).
:::

::: {.definition title="Completeness of a Hilbert space"}
A collection of vectors \( \left\{{u_{n}}\right\}\subset H \) is **complete** iff \( {\left\langle {x},~{u_{n}} \right\rangle} = 0 \) for all \( n \iff x = 0 \) in \( H \).
:::

::: {.definition title="Dual of a Hilbert space"}
The **dual** of a Hilbert space \( H \) is defined as
\[
H^\vee\coloneqq\left\{{L: H\to {\mathbb{C}}{~\mathrel{\Big|}~}L \text{ is continuous }}\right\}
.\]
:::

::: {.definition title="Linear functionals"}
A map \( L: X \to {\mathbb{C}} \) is a **linear functional** iff
\[
L(\alpha\mathbf{x} + \mathbf{y}) = \alpha L(\mathbf{x}) + L(\mathbf{y}).
.\]
:::

::: {.definition title="Operator norm"}
The **operator norm** of an operator \( L \) is defined as
\[
{\left\lVert {L} \right\rVert}_{X^\vee} \coloneqq\sup_{ \substack{x\in X \\ {\left\lVert {x} \right\rVert} = 1} } {\left\lvert {L(x)} \right\rvert}
.\]
:::

::: {.definition title="Banach Space"}
A space is a **Banach space** if and only if it is a complete normed vector space.
:::

::: {.definition title="Hilbert Space"}
A **Hilbert space** is an inner product space which is a Banach space under the induced norm.
:::

## Theorems

### Topology / Sets

::: {.theorem title="Heine-Cantor"}
Every continuous function on a compact space is uniformly continuous.
:::

::: {.proposition title="Compact if and only if sequentially compact for metric spaces"}
Metric spaces are compact iff they are sequentially compact, (i.e. every sequence has a convergent subsequence).
:::

::: {.proposition title="A unit ball that is not compact"}
The unit ball in \( C([0, 1]) \) with the sup norm is not compact.
:::

::: {.proof title="?"}
Take \( f_k(x) = x^n \), which converges to \( \chi(x=1) \). The limit is not continuous, so no subsequence can converge.
:::

::: {.proposition title="?"}
A *finite* union of nowhere dense is again nowhere dense.
:::

::: {.proposition title="Convergent Sums Have Small Tails"}
\[\sum a_n < \infty \implies a_n \to 0 {\quad \operatorname{and} \quad} \sum_{k=N}^\infty a_n \overset{N\to\infty}\to 0\]
:::

::: {.theorem title="Heine-Borel"}
\( X\subseteq {\mathbb{R}}^n \) is compact \( \iff X \) is closed and bounded.
:::

::: {.proposition title="Geometric Series"}
\[
\sum_{k=0}^\infty x^k = \frac 1 {1-x} \iff {\left\lvert {x} \right\rvert} < 1
.\]
:::

::: {.corollary title="?"}
\[
\sum_{k=0}^\infty \frac 1 {2^k} = 1
.\]
:::

::: {.proposition title="?"}
The Cantor set is closed with empty interior.
:::

::: {.proof title="?"}
Its complement is a union of open intervals, and can't contain an interval since intervals have positive measure and \( m(C_n) \) tends to zero.
:::

::: {.corollary title="?"}
The Cantor set is nowhere dense.
:::

::: {.proposition title="?"}
Singleton sets in \( {\mathbb{R}} \) are closed, and thus \( {\mathbb{Q}} \) is an \( F_\sigma \) set.
:::

::: {.theorem title="Baire"}
\( {\mathbb{R}} \) is a **Baire space** Thus \( {\mathbb{R}} \) can not be written as a countable union of nowhere dense sets.
:::

::: {.lemma title="?"}
Any nonempty set which is bounded from above (resp. below) has a well-defined supremum (resp. infimum).
:::

### Functions

::: {.proposition title="Existence of Smooth Compactly Supported Functions"}
There exist smooth compactly supported functions, e.g. take
\[
f(x) = e^{-\frac{1}{x^2}} \chi_{(0, \infty)}(x)
.\]
:::

::: {.lemma title="Function discontinuous on the rationals"}
There is a function discontinuous precisely on \( {\mathbb{Q}} \).
:::

::: {.proof title="?"}
\( f(x) = \frac 1 n \) if \( x = r_n \in {\mathbb{Q}} \) is an enumeration of the rationals, and zero otherwise. The limit at every point is 0.
:::

::: {.proposition title="No functions discontinuous on the irrationals"}
There *do not* exist functions that are discontinuous precisely on \( {\mathbb{R}}\setminus {\mathbb{Q}} \).
:::

::: {.proof title="?"}
\( D_f \) is always an \( F_\sigma \) set, which follows by considering the oscillation \( \omega_f \). \( \omega_f(x) = 0 \iff f \) is continuous at \( x \), and \( D_f = \cup_n A_{\frac 1 n} \) where \( A_\varepsilon = \left\{{\omega_f \geq \varepsilon}\right\} \) is closed.
:::

::: {.proposition title="Lipschitz $\\iff$ differentiable with bounded derivative."}
A function \( f: (a, b) \to {\mathbb{R}} \) is Lipschitz \( \iff f \) is differentiable and \( f' \) is bounded. In this case, \( {\left\lvert {f'(x)} \right\rvert} \leq C \), the Lipschitz constant.
:::

## Uniform Convergence

::: {.proposition title="Testing Uniform Convergence: The Sup Norm Test"}
\( f_n \to f \) uniformly iff there exists an \( M_n \) such that \( {\left\lVert {f_n - f} \right\rVert}_\infty \leq M_n \to 0 \).
:::

::: {.remark title="Negating the Sup Norm test"}
**Negating**: find an \( x \) which depends on \( n \) for which \( {\left\lVert {f_n} \right\rVert}_\infty > \varepsilon \) (negating small tails) or \( {\left\lVert {f_n - f_m} \right\rVert} > \varepsilon \) (negating the Cauchy criterion).
:::

### Example: Completeness of a Normed Function Space

:::{.proposition title=\" \( C(I) \) is complete\"} The space \( X = C([0, 1]) \), continuous functions \( f: [0, 1] \to {\mathbb{R}} \), equipped with the norm
\[
{\left\lVert {f} \right\rVert}_\infty \coloneqq\sup_{x\in [0, 1]} {\left\lvert {f(x)} \right\rvert}
\]
is a **complete** metric space. :::

::: {.proof}
```{=tex}
\envlist
```
1.  Let \( \left\{{f_k}\right\} \) be Cauchy in \( X \).

2.  Define a candidate limit using pointwise convergence:

    Fix an \( x \); since
    \[
      {\left\lvert {f_k(x) - f_j(x)} \right\rvert}  \leq {\left\lVert {f_k - f_k} \right\rVert} \to 0
      \]
    the sequence \( \left\{{f_k(x)}\right\} \) is Cauchy in \( {\mathbb{R}} \). So define \( f(x) \coloneqq\lim_k f_k(x) \).

3.  Show that \( {\left\lVert {f_k - f} \right\rVert} \to 0 \):
    \[
      {\left\lvert {f_k(x) - f_j(x)} \right\rvert} < \varepsilon ~\forall x \implies \lim_{j} {\left\lvert {f_k(x) - f_j(x)} \right\rvert} <\varepsilon ~\forall x
      \]
    Alternatively, \( {\left\lVert {f_k-f} \right\rVert} \leq {\left\lVert {f_k - f_N} \right\rVert} + {\left\lVert {f_N - f_j} \right\rVert} \), where \( N, j \) can be chosen large enough to bound each term by \( \varepsilon/2 \).

4.  Show that \( f\in X \):

    The uniform limit of continuous functions is continuous.
:::

::: {.remark}
In other cases, you may need to show the limit is bounded, or has bounded derivative, or whatever other conditions define \( X \).
:::

::: {.theorem title="Uniform Limit Theorem"}
If \( f_n\to f \) pointwise and uniformly with each \( f_n \) continuous, then \( f \) is continuous. [^3]
:::

::: {.proof}
```{=tex}
\envlist
```
-   Follows from an \( \varepsilon/3 \) argument:
    \[  
    {\left\lvert {F(x) - F(y} \right\rvert} \leq 
    {\left\lvert {F(x) - F_N(x)} \right\rvert} + {\left\lvert {F_N(x) - F_N(y)} \right\rvert} + {\left\lvert {F_N(y) - F(y)} \right\rvert} 
    \leq \varepsilon\to 0
    .\]

    -   The first and last \( \varepsilon/3 \) come from uniform convergence of \( F_N\to F \).
    -   The middle \( \varepsilon/3 \) comes from continuity of each \( F_N \).

-   So just need to choose \( N \) large enough and \( \delta \) small enough to make all 3 \( \varepsilon \) bounds hold.
:::

::: {.proposition title="Uniform Limits Commute with Integrals"}
If \( f_n \to f \) uniformly, then \( \int f_n = \int f \).
:::

### Series

::: {.proposition title="p-tests"}
Let \( n \) be a fixed dimension and set \( B = \left\{{x\in {\mathbb{R}}^n {~\mathrel{\Big|}~}{\left\lVert {x} \right\rVert} \leq 1}\right\} \).
\[
\sum \frac 1 {n^p} < \infty &\iff p>1 \\
\int_\varepsilon^\infty \frac 1 {x^p} < \infty 
&\iff p>1 \\
\int_0^1 \frac 1 {x^p} < \infty 
&\iff p<1 \\
\int_B \frac{1}{{\left\lvert {x} \right\rvert}^p} < \infty &\iff p < n \\
\int_{B^c} \frac{1}{{\left\lvert {x} \right\rvert}^p} < \infty &\iff p > n \\
.\]
:::

::: {.proposition title="Comparison Test"}
If \( 0\leq a_n \leq b_n \), then

-   \( \sum b_n < \infty \implies \sum a_n < \infty \), and
-   \( \sum a_n = \infty \implies \sum b_n = \infty \).
:::

::: {.proposition title="Small Tails for Series of Functions"}
If \( \sum f_n \) converges then \( f_n \to 0 \) uniformly.
:::

::: {.corollary title="Term by Term Continuity Theorem"}
If \( f_n \) are continuous and \( \sum f_n \to f \) converges uniformly, then \( f \) is continuous.
:::

::: {.proposition title="Weak $M\\dash$Test"}
If \( f_n(x) \leq M_n \) **for a fixed \( x \)** where \( \sum M_n < \infty \), then the series \( f(x) = \sum f_n(x) \) converges.[^4]
:::

::: {.proposition title="The Weierstrass $M\\dash$Test"}
If \( \sup_{x\in A} {\left\lvert {f_n(x)} \right\rvert} \leq M_n \) for each \( n \) where \( \sum M_n < \infty \), then \( \sum_{n=1}^\infty f_n(x) \) converges uniformly and absolutely on \( A \). [^5] Conversely, if \( \sum f_n \) converges uniformly on \( A \) then \( \sup_{x\in A} {\left\lvert {f_n(x)} \right\rvert} \to 0 \).
:::

::: {.proposition title="Cauchy criterion for sums"}
\( f_n \) are uniformly Cauchy (so \( {\left\lVert {f_n - f_m} \right\rVert}_\infty < \varepsilon \)) iff \( f_n \) is uniformly convergent.
:::

#### Derivatives

::: {.theorem title="Term by Term Differentiability Theorem"}
If \( f_n \) are differentiable, \( \sum f_n' \to g \) uniformly, and there exists one point[^6] \( x_0 \) such that \( \sum f_n(x) \) converges, then there exist an \( f \) such that \( \sum f_n \to f \) uniformly and \( f' = g \).[^7]
:::

## Commuting Limiting Operations

::: {.proposition title="Limits of bounded functions need not be bounded"}
\[  
\lim_{n\to \infty}\sup_{x\in X} {\left\lvert {f_n(x) } \right\rvert} \neq \sup_{x\in X} {\left\lvert {\lim_{n\to\infty} f_n(x) } \right\rvert}
.\]
:::

::: {.proposition title="Limits of continuous functions need not be continuous"}
\[  
\lim_{k\to \infty} \lim_{n\to\infty} f_n(x_k) \neq
\lim_{n\to \infty} \lim_{k\to\infty} f_n(x_k)
.\]
:::

::: {.proposition title="Limits of differentiable functions need not be differentiable"}
\[  
\lim_{n\to \infty} {\frac{\partial }{\partial x}\,} f_n \neq {\frac{\partial }{\partial n}\,} \qty{\lim_{n\to \infty} f_n}
.\]
:::

::: {.proposition title="?"}
\[  
\lim_{n\to \infty} \int_a^b f_n(x) \,dx \neq \int_a^b \lim_{n\to \infty} \qty{ f_n(x) } \,dx
.\]
:::

## Slightly Advanced Stuff

::: {.theorem title="Weierstrass Approximation"}
If \( [a, b] \subset {\mathbb{R}} \) is a closed interval and \( f \) is continuous, then for every \( \varepsilon> 0 \) there exists a polynomial \( p_\varepsilon \) such that \( {\left\lVert {f- p_\varepsilon} \right\rVert}_{L^\infty([a, b])} \overset{\varepsilon\to 0}\to 0 \).

Equivalently, polynomials are dense in the Banach space \( C([0, 1], {\left\lVert {{\,\cdot\,}} \right\rVert}_\infty) \).
:::

::: {.theorem title="Egorov"}
Let \( E \subseteq {\mathbb{R}}^n \) be measurable with \( m(E) > 0 \) and \( \left\{{f_k: E \to {\mathbb{R}}}\right\} \) be measurable functions such that
\[  
f(x) \coloneqq\lim_{k\to\infty} f_k(x) < \infty 
\]
exists almost everywhere.

Then \( f_k \to f \) *almost uniformly*, i.e.
\[
\forall\varepsilon > 0, ~\exists F \subseteq E ~\text{closed such that } &
m(E\setminus F) < \varepsilon ~\text{ and }~ f_k\to f ~\text{uniformly on}~ F
.\]
:::

## Examples

::: {.example title="?"}
A series of continuous functions that does *not* converge uniformly but is still continuous:
\[  
g(x) \coloneqq\sum {1 \over 1 + n^2 x}
.\]

Take \( x = 1/n^2 \).
:::

# Measure Theory

## Theorems

::: {.proposition title="Opens are unions of almost disjoint intervals."}
Every open subset of \( {\mathbb{R}} \) (resp \( {\mathbb{R}}^n \)) can be written as a unique countable union of disjoint (resp. almost disjoint) intervals (resp. cubes).
:::

::: {.proposition title="Properties of Outer Measure"}
```{=tex}
\envlist
```
1.  Monotonicity: \( E\subseteq F \implies m_*(E) \leq m_*(F) \).
2.  Countable Subadditivity: \( m_*(\cup E_{i}) \leq \sum m_*(E_{i}) \).
3.  Approximation: For all \( E \) there exists a \( G \supseteq E \) such that \( m_*(G) \leq m_*(E) + \varepsilon \).
4.  Disjoint[^8] Additivity: \( m_*(A {\coprod}B) = m_*(A) + m_*(B) \).
:::

::: {.proposition title="Subtraction of Measures"}
\[m(A) = m(B) + m(C) {\quad \operatorname{and} \quad} m(C) < \infty \implies m(A) - m(C) = m(B).\]
:::

::: {.proposition title="Continuity of Measure"}
\[
E_{i} \nearrow E &\implies m(E_{i}) \to m(E) \\
m(E_{1}) < \infty \text{ and } E_{i} \searrow E &\implies m(E_{i}) \to m(E)
.\]
:::

::: {.proof title="of continuity of measure"}
```{=tex}
\envlist
```
1.  Break into disjoint annuli \( A_{2} = E_{2}\setminus E_{1} \), etc then apply countable disjoint additivity to \( E = {\coprod}A_{i} \).

2.  Use \( E_{1} = ({\coprod}E_{j}\setminus E_{j+1}) {\coprod}(\cap E_{j}) \), taking measures yields a telescoping sum,and use countable disjoint additivity.
:::

::: {.theorem title="Measurable sets can be approximated by open/closed/compact sets."}
Suppose \( E \) is measurable; then for every \( \varepsilon>0 \),

1.  There exists an open \( O\supset E \) with \( m(O\setminus E) < \varepsilon \)
2.  There exists a closed \( F\subset E \) with \( m(E\setminus F) < \varepsilon \)
3.  There exists a compact \( K\subset E \) with \( m(E\setminus K) < \varepsilon \).
:::

::: {.proof title="that measurable sets can be approximated"}
```{=tex}
\envlist
```
-   (1): Take \( \left\{{Q_{i}}\right\} \rightrightarrows E \) and set \( O = \cup Q_{i} \).
-   (2): Since \( E^c \) is measurable, produce \( O\supset E^c \) with \( m(O\setminus E^c) < \varepsilon \).
    -   Set \( F = O^c \), so \( F \) is closed.
    -   Then \( F\subset E \) by taking complements of \( O\supset E^c \)
    -   \( E\setminus F = O\setminus E^c \) and taking measures yields \( m(E\setminus F) < \varepsilon \)
-   (3): Pick \( F\subset E \) with \( m(E\setminus F) < \varepsilon/2 \).
    -   Set \( K_{n} = F\cap{\mathbb{D}}_{n} \), a ball of radius \( n \) about \( 0 \).
    -   Then \( E\setminus K_{n} \searrow E\setminus F \)
    -   Since \( m(E) < \infty \), there is an \( N \) such that \( n\geq N \implies m(E\setminus K_{n}) < \varepsilon \).
:::

::: {.proposition title="Translation and Dilation Invariance"}
Lebesgue measure is translation and dilation invariant.
:::

::: {.proof title="(Todo) of translation/dilation invariance"}
Obvious for cubes; if \( Q_{i} \rightrightarrows E \) then \( Q_{i} + k \rightrightarrows E + k \), etc. `<!--\todo{Flesh out this proof.}-->`{=html}
:::

::: {.theorem title="Non-measurable sets exist"}
There is a non-measurable set.
:::

::: {.proof title="Constructing a non-measurable set"}
```{=tex}
\envlist
```
-   Use AOC to choose one representative from every coset of \( {\mathbb{R}}/{\mathbb{Q}} \) on \( [0, 1) \), which is countable, and assemble them into a set \( N \)
-   Enumerate the rationals in \( [0, 1] \) as \( q_{j} \), and define \( N_{j} = N + q_{j} \). These intersect trivially.
-   Define \( M \coloneqq{\coprod}N_{j} \), then \( [0, 1) \subseteq M \subseteq [-1, 2) \), so the measure must be between 1 and 3.
-   By translation invariance, \( m(N_{j}) = m(N) \), and disjoint additivity forces \( m(M) = 0 \), a contradiction.
:::

::: {.proposition title="Borel Characterization of Measurable Sets"}
If \( E \) is Lebesgue measurable, then \( E = H {\coprod}N \) where \( H \in F_\sigma \) and \( N \) is null.
:::

::: {.proof title="of Borel characterization"}
For every \( \frac 1 n \) there exists a closed set \( K_{n} \subset E \) such that \( m(E\setminus K_{n}) \leq \frac 1 n \). Take \( K = \cup K_{n} \), wlog \( K_{n} \nearrow K \) so \( m(K) = \lim m(K_{n}) = m(E) \). Take \( N\coloneqq E\setminus K \), then \( m(N) = 0 \).
:::

::: {.proposition title="Limsups/infs of measurable sets are measurable."}
If \( A_{n} \) are all measurable, \( \limsup A_{n} \) and \( \liminf A_{n} \) are measurable.
:::

::: {.proof title="That limsups/infs are measurable"}
Measurable sets form a sigma algebra, and these are expressed as countable unions/intersections of measurable sets.
:::

::: {.theorem title="Borel-Cantelli"}
Let \( \{E_{k}\} \) be a countable collection of measurable sets. Then
\[
\sum_{k} m(E_{k}) < \infty \implies \text{ almost every } x\in {\mathbb{R}}\text{ is in at most finitely many } E_{k}
.\]
:::

::: {.proof title="of Borel-Cantelli"}
```{=tex}
\envlist
```
-   If \( E = \limsup_{j} E_{j} \) with \( \sum m(E_{j}) < \infty \) then \( m(E) = 0 \).
-   If \( E_{j} \) are measurable, then \( \limsup_{j} E_{j} \) is measurable.
-   If \( \sum_{j} m(E_{j}) < \infty \), then \( \sum_{j=N}^\infty m(E_{j}) \overset{N\to\infty}\to 0 \) as the tail of a convergent sequence.
-   \( E = \limsup_{j} E_{j} = \cap_{k=1}^\infty \cup_{j=k}^\infty E_{j} \implies E \subseteq \cup_{j=k}^\infty \) for all \( k \)
-   \( E \subset \cup_{j=k}^\infty \implies m(E) \leq \sum_{j=k}^\infty m(E_{j}) \overset{k\to\infty}\to 0 \).
:::

::: {.proposition title="Extending the class of measurable functions."}
-   Characteristic functions are measurable
-   If \( f_{n} \) are measurable, so are \( {\left\lvert {f_{n}} \right\rvert}, \limsup f_{n}, \liminf f_{n}, \lim f_{n} \),
-   Sums and differences of measurable functions are measurable,
-   Cones \( F(x,y) = f(x) \) are measurable,
-   Compositions \( f\circ T \) for \( T \) a linear transformation are measurable,
-   "Convolution-ish" transformations \( (x,y) \mapsto f(x-y) \) are measurable
:::

::: {.proof title="Convolution"}
Take the cone on \( f \) to get \( F(x, y) = f(x) \), then compose \( F \) with the linear transformation \( T = [1, -1; 1, 0] \).
:::

# Integration

## Theorems

::: {.remark}
If \( f\in L^\infty(X) \), then \( f \) is equal to some bounded function \( g \) almost everywhere.
:::

::: {.example title="?"}
\( f(x) = x\chi_{\mathbb{Q}}(x) \) is essentially bounded but not bounded.
:::

::: {.theorem title="p-Test for Integrals"}
\[
\int_0^1 {1\over x^p} < \infty \iff  p < 1 \\
\int_1^\infty {1\over x^p} < \infty \iff  p > 1 
.\]
:::

::: {.slogan}
Large powers of \( x \) help us in neighborhoods of infinity and hurt around zero
:::

### Convergence Theorems

::: {.theorem title="Monotone Convergence"}
If \( f_n \in L^+ \) and \( f_n \nearrow f \) almost everywhere, then
\[
\lim \int f_n
= \int \lim f_n = \int f
\quad \text{i.e.}~~ \int f_n \to \int f
.\]

> Needs to be positive and increasing.
:::

::: {.theorem title="Dominated Convergence"}
If \( f_n \in L^1 \) and \( f_n \to f \) almost everywhere with \( {\left\lvert {f_n} \right\rvert} \leq g \) for some \( g\in L^1 \), then \( f\in L^1 \) and
\[
\lim \int f_n = \int \lim f_n = \int f \quad \text{i.e.}~~ \int f_n \to \int f < \infty
,\]

and more generally,
\[
\int {\left\lvert {f_n - f} \right\rvert} \to 0
.\]

> Positivity *not* needed.
:::

::: {.theorem title="Generalized DCT"}
If

-   \( f_n \in L^1 \) with \( f_n \to f \) almost everywhere,
-   There exist \( g_n \in L^1 \) with \( {\left\lvert {f_n} \right\rvert} \leq g_n \), \( g_n \geq 0 \).
-   \( g_n\to g \) almost everywhere with \( g\in L^1 \), and
-   \( \lim \int g_n = \int g \),

then \( f\in L^1 \) and \( \lim \int f_n = \int f < \infty \).

> Note that this is the DCT with \( {\left\lvert {f_n} \right\rvert} < {\left\lvert {g} \right\rvert} \) relaxed to \( {\left\lvert {f_n} \right\rvert} < g_n \to g\in L^1 \).
:::

::: {.proof}
Proceed by showing \( \limsup \int f_n \leq \int f \leq \liminf \int f_n \):

-   \( \int f \geq \limsup \int f_n \):
    \[
    \int g - \int f 
    &= \int \qty{g-f} \\
    &\leq \liminf \int \qty{g_n - f_n} \quad \text{Fatou} \\
    &= \lim \int g_n + \liminf \int (-f_n) \\
    &= \lim \int g_n - \limsup \int f_n \\
    &= \int g - \limsup \int f_n \\
    \\
    \implies \int f &\geq \limsup \int f_n
    .\]

    -   Here we use \( g_n - f_n \overset{n\to\infty} g-f \) with \( 0 \leq {\left\lvert {f_n} \right\rvert} - f_n \leq g_n - f_n \), so \( g_n - f_n \) are nonnegative (and measurable) and Fatou's lemma applies.

-   \( \int f \leq \liminf \int f_n \):
    \[
    \int g + \int f 
    &= \int(g+f) \\
    &\leq \liminf \int \qty{g_n + f_n} \\
    &= \lim \int g_n + \liminf \int f_n \\
    &= \int g + \liminf f_n \\
    \\
    \int f &\leq \liminf \int f_n
    .\]

    -   Here we use that \( g_n + f_n \to g+f \) with \( 0 \leq {\left\lvert {f_n} \right\rvert} + f_n \leq g_n + f_n \) so Fatou's lemma again applies.
:::

::: {.proposition title="Convergence in $L^1$ implies convergence of $L^1$ norm"}
If \( f\in L^1 \), then
\[
\int{\left\lvert {f_n - f} \right\rvert} \to 0 \iff \int {\left\lvert {f_n} \right\rvert} \to \int {\left\lvert {f} \right\rvert}
.\]
:::

::: {.proof}
Let \( g_n = {\left\lvert {f_n} \right\rvert} - {\left\lvert {f_n - f} \right\rvert} \), then \( g_n \to {\left\lvert {f} \right\rvert} \) and
\[
{\left\lvert {g_n} \right\rvert} = {\left\lvert { {\left\lvert {f_n} \right\rvert} - {\left\lvert {f_n - f} \right\rvert} } \right\rvert} \leq {\left\lvert {f_n - (f_n - f)} \right\rvert} = {\left\lvert {f} \right\rvert} \in L^1
,\]
so the DCT applies to \( g_n \) and
\[
{\left\lVert {f_n - f} \right\rVert}_1 = \int {\left\lvert {f_n - f} \right\rvert} + {\left\lvert {f_n} \right\rvert} - {\left\lvert {f_n} \right\rvert}
= \int {\left\lvert {f_n} \right\rvert} - g_n\\
\to_{DCT} \lim \int {\left\lvert {f_n} \right\rvert} - \int {\left\lvert {f} \right\rvert}
.\]
:::

::: {.theorem title="Fatou"}
If \( f_n \) is a sequence of nonnegative measurable functions, then
\[
\int \liminf_n f_n &\leq \liminf_n \int f_n \\
\limsup_n \int f_n &\leq \int \limsup_n f_n
.\]
:::

::: {.theorem title="Tonelli (Non-Negative, Measurable)"}
For \( f(x, y) \) **non-negative and measurable**, for almost every \( x\in {\mathbb{R}}^n \),

-   \( f_x(y) \) is a **measurable** function
-   \( F(x) = \int f(x, y) ~dy \) is a **measurable** function,
-   For \( E \) measurable, the slices \( E_x \coloneqq\left\{{y {~\mathrel{\Big|}~}(x, y) \in E}\right\} \) are measurable.
-   \( \int f = \int \int F \), i.e. any iterated integral is equal to the original.
:::

::: {.theorem title="Fubini (Integrable)"}
For \( f(x, y) \) **integrable**, for almost every \( x\in {\mathbb{R}}^n \),

-   \( f_x(y) \) is an **integrable** function
-   \( F(x) \coloneqq\int f(x, y) ~dy \) is an **integrable** function,
-   For \( E \) measurable, the slices \( E_x \coloneqq\left\{{y {~\mathrel{\Big|}~}(x, y) \in E}\right\} \) are measurable.
-   \( \int f = \int \int f(x,y) \), i.e. any iterated integral is equal to the original
:::

::: {.theorem title="Fubini-Tonelli"}
If any iterated integral is **absolutely integrable**, i.e. \( \int \int {\left\lvert {f(x, y)} \right\rvert} < \infty \), then \( f \) is integrable and \( \int f \) equals any iterated integral.
:::

::: {.proposition title="Measurable Slices"}
Let \( E \) be a measurable subset of \( {\mathbb{R}}^n \). Then

-   For almost every \( x\in {\mathbb{R}}^{n_1} \), the slice \( E_x \coloneqq\left\{{y \in {\mathbb{R}}^{n_2} \mathrel{\Big|}(x,y) \in E}\right\} \) is measurable in \( {\mathbb{R}}^{n_2} \).
-   The function

\[
F: {\mathbb{R}}^{n_1} &\to {\mathbb{R}}\\
x &\mapsto m(E_x) = \int_{{\mathbb{R}}^{n_2}} \chi_{E_x} ~dy
\]
is measurable and
\[
m(E) = \int_{{\mathbb{R}}^{n_1}} m(E_x) ~dx 
= \int_{{\mathbb{R}}^{n_1}} \int_{{\mathbb{R}}^{n_2}} \chi_{E_x} ~dy ~dx
.\]
:::

::: {.proof}
```{=tex}
\envlist
```
\( \implies \):

-   Let \( f \) be measurable on \( {\mathbb{R}}^n \).
-   Then the cylinders \( F(x, y) = f(x) \) and \( G(x, y) = f(y) \) are both measurable on \( {\mathbb{R}}^{n+1} \).
-   Write \( \mathcal{A} = \left\{{G \leq F}\right\} \cap\left\{{G \geq 0}\right\} \); both are measurable.

\( \impliedby \):

-   Let \( A \) be measurable in \( {\mathbb{R}}^{n+1} \).
-   Define \( A_x = \left\{{y\in {\mathbb{R}}\mathrel{\Big|}(x, y) \in \mathcal{A}}\right\} \), then \( m(A_x) = f(x) \).
-   By the corollary, \( A_x \) is measurable set, \( x \mapsto A_x \) is a measurable function, and \( m(A) = \int f(x) ~dx \).
-   Then explicitly, \( f(x) = \chi_{A} \), which makes \( f \) a measurable function.
:::

::: {.proposition title="Differentiating Under an Integral"}
If \( {\left\lvert {{\frac{\partial }{\partial t}\,}f(x, t)} \right\rvert} \leq g(x) \in L^1 \), then letting \( F(t) = \int f(x, t) ~dt \),
\[
{\frac{\partial }{\partial t}\,} F(t)
&\coloneqq\lim_{h \rightarrow 0} \int \frac{f(x, t+h)-f(x, t)}{h} d x \\
&\mathop{\mathrm{=}}^{\scriptstyle\text{DCT}} \int {\frac{\partial }{\partial t}\,} f(x, t) ~dx
.\]

To justify passing the limit, let \( h_k \to 0 \) be any sequence and define
\[
f_k(x, t) = \frac{f(x, t+h_k)-f(x, t)}{h_k}
,\]
so \( f_k \overset{\text{pointwise}}\to {\frac{\partial }{\partial t}\,}f \).

Apply the MVT to \( f_k \) to get \( f_k(x, t) = f_k(\xi, t) \) for some \( \xi \in [0, h_k] \), and show that \( f_k(\xi, t) \in L_1 \).
:::

::: {.proposition title="Commuting Sums with Integrals (non-negative)"}
If \( f_n \) are non-negative and \( \sum \int {\left\lvert {f} \right\rvert}_n < \infty \), then \( \sum \int f_n = \int \sum f_n \).
:::

::: {.proof}
-   Idea: MCT.
-   Let \( F_N = \sum^N f_n \) be a finite partial sum;
-   Then there are simple functions \( \phi_n \nearrow f_n \)
-   So \( \sum^N \phi_n \nearrow F_N \) and MCT applies
:::

::: {.theorem title="Commuting Sums with Integrals (integrable)"}
If \( \left\{{f_n}\right\} \) integrable with either \( \sum \int {\left\lvert {f_n} \right\rvert} < \infty \) or \( \int\sum {\left\lvert {f_n} \right\rvert} < \infty \), then
\[  
\int\sum f_n = \sum \int f_n
.\]
:::

::: {.proof}
-   By Tonelli, if \( f_n(x) \geq 0 \) for all \( n \), taking the counting measure allows interchanging the order of "integration".
-   By Fubini on \( {\left\lvert {f_n} \right\rvert} \), if either "iterated integral" is finite then the result follows.
:::

::: {.proposition title="?"}
If \( f_k \in L^1 \) and \( \sum {\left\lVert {f_k} \right\rVert}_1 < \infty \) then \( \sum f_k \) converges almost everywhere and in \( L^1 \).
:::

::: {.proof title="?"}
Define \( F_N = \sum^N f_k \) and \( F = \lim_N F_N \), then \( {\left\lVert {F_N} \right\rVert}_1 \leq \sum^N {\left\lVert {f_k} \right\rVert} < \infty \) so \( F\in L^1 \) and \( {\left\lVert {F_N - F} \right\rVert}_1 \to 0 \) so the sum converges in \( L^1 \). Almost everywhere convergence: ?
:::

## Examples of (Non)Integrable Functions

::: {.example title="Examples of integrable functions"}
```{=tex}
\envlist
```
-   \( \int {1\over 1 + x^2} = \arctan(x) \overset{x\to\infty}\to \pi/2 < \infty \)

-   Any bounded function (or continuous on a compact set, by EVT)

-   \( \int_0^1 {1 \over \sqrt{x}} < \infty \)

-   \( \int_0^1 {1\over x^{1-\varepsilon}} < \infty \)

-   \( \int_1^\infty {1\over x^{1+\varepsilon}} < \infty \)
:::

::: {.example title="Examples of non-integrable functions"}
```{=tex}
\envlist
```
-   \( \int_0^1 {1\over x} = \infty \).
-   \( \int_1^\infty {1\over x} = \infty \).
-   \( \int_1^\infty {1 \over \sqrt{x}} = \infty \)
-   \( \int_1^\infty {1\over x^{1-\varepsilon}} = \infty \)
-   \( \int_0^1 {1\over x^{1+\varepsilon}} = \infty \)
:::

## \( L^1 \) Facts {#l1-facts}

::: {.proposition title="Zero in $L^1$ iff zero almost everywhere"}
For \( f\in L^+ \),
\[  
\int f = 0 \quad\iff\quad f \equiv 0 \text{ almost everywhere}
.\]
:::

::: {.proof}
```{=tex}
\envlist
```
-   Obvious for simple functions:
    -   If \( f(x) = \sum_{j=1}^n c_j \chi_{E_j} \), then \( \int f = 0 \) iff for each \( j \), either \( c_j=0 \) or \( m(E_j) = 0 \).
    -   Since nonzero \( c_j \) correspond to sets where \( f\neq 0 \), this says \( m\qty{\left\{{f\neq 0}\right\}} = 0 \).
-   \( \impliedby \):
    -   If \( f= 0 \) almost everywhere and \( \phi \nearrow f \), then \( \phi = 0 \) almost everywhere since \( \phi(x) \leq f(x) \) -Then
        \[  
        \int f = \sup_{\phi \leq f} \int \phi = \sup_{\phi \leq f} 0 = 0
        .\]
-   \( \implies \):
    -   Instead show negating "\( f=0 \) almost everywhere" implies \( \int f \neq 0 \).
    -   Write \( \left\{{f\neq 0}\right\} = \cup_{n\in {\mathbb{N}}} S_n \) where \( S_n \coloneqq\left\{{x{~\mathrel{\Big|}~}f(x) \geq {1\over n}}\right\} \).
    -   Since "not \( f=0 \) almost everywhere", there exists an \( n \) such that \( m(S_n) > 0 \).
    -   Then
        \[  
        0 < {1\over n} \chi_{E_n} \leq f \implies 
        0 < \int {1\over n} \chi_{E_n} \leq \int f
        .\]
:::

::: {.proposition title="Translation Invariance"}
The Lebesgue integral is translation invariant, i.e.
\[
\int f(x) ~dx = \int f(x + h) ~dx &&\text{for any} h
.\]
:::

::: {.proof}
```{=tex}
\envlist
```
-   Let \( E\subseteq X \); for characteristic functions,
    \[
    \int_X \chi_E(x+h) 
    = \int_{X} \chi_{E+h}(x) = m(E+h) = m(E) = \int_X \chi_E(x)
    \]
    by translation invariance of measure.
-   So this also holds for simple functions by linearity.
-   For \( f\in L^+ \), choose \( \phi_n \nearrow f \) so \( \int \phi_n \to \int f \).
-   Similarly, \( \tau_h \phi_n \nearrow \tau_h f \) so \( \int \tau_h f \to \int f \)
-   Finally \( \left\{{\int \tau_h \phi}\right\} = \left\{{\int \phi}\right\} \) by step 1, and the suprema are equal by uniqueness of limits.
:::

::: {.proposition title="Integrals distribute over disjoint sets"}
If \( X \subseteq A \cup B \), then \( \int_X f \leq \int_A f + \int_{A^c} f \) with equality iff \( X = A{\coprod}B \).
:::

::: {.proposition title="Uniformly continuous $L^1$ functions vanish at infinity."}
If \( f \in L^1 \) and \( f \) is uniformly continuous, then \( f(x) \overset{{\left\lvert {x} \right\rvert}\to\infty}\to 0 \).
:::

::: {.warnings}
This doesn't hold for general \( L^1 \) functions, take any train of triangles with height 1 and summable areas.
:::

::: {.theorem title="Small Tails in $L^1$"}
If \( f\in L^1 \), then for every \( \varepsilon \) there exists a radius \( R \) such that if \( A = B_R(0)^c \), then \( \int_A {\left\lvert {f} \right\rvert} < \varepsilon \).
:::

::: {.proof}
```{=tex}
\envlist
```
-   Approximate with compactly supported functions.
-   Take \( g\overset{L_1}\to f \) with \( g\in C_c \)
-   Then choose \( N \) large enough so that \( g=0 \) on \( E\coloneqq B_N(0) \)
-   Then
    \[ \int_E {\left\lvert {f} \right\rvert} \leq \int_E{\left\lvert {f-g} \right\rvert} + \int_E {\left\lvert {g} \right\rvert}.\]
:::

::: {.proposition title="$L^1$ functions are absolutely continuous."}
\( m(E) \to 0 \implies \int_E f \to 0 \).
:::

::: {.proof title="?"}
Approximate with compactly supported functions. Take \( g\overset{L_1}\to f \), then \( g \leq M \) so \( \int_E{f} \leq \int_E{f-g} + \int_E g \to 0 + M \cdot m(E) \to 0 \).
:::

::: {.proposition title="$L^1$ functions are finite almost everywhere."}
If \( f\in L^1 \), then \( m(\left\{{f(x) = \infty}\right\}) = 0 \).
:::

::: {.proof title="?"}
Idea: Split up domain Let \( A = \left\{{f(x) = \infty}\right\} \), then \( \infty > \int f = \int_A f + \int_{A^c} f = \infty \cdot m(A) + \int_{A^c} f \implies m(X) =0 \).
:::

::: {.theorem title="Continuity in $L^1$"}
\[ 
{\left\lVert {\tau_h f - f} \right\rVert}_1 \overset{h\to 0}\to 0
\]
:::

::: {.proof}
```{=tex}
\envlist
```
Approximate with compactly supported functions. Take \( g\overset{L_1}\to f \) with \( g\in C_c \).
\[
\int f(x+h) - f(x) 
&\leq \int f(x+h) - g(x+h) + \int g(x+h) - g(x) + \int g(x) - f(x) \\
&\overset{?\to?}\to 2 \varepsilon + \int g(x+h) - g(x) \\
&= \int_K g(x+h) - g(x) + \int_{K^c} g(x+h) - g(x)\\
&\overset{??}\to 0
,\]
which follows because we can enlarge the support of \( g \) to \( K \) where the integrand is zero on \( K^c \), then apply uniform continuity on \( K \).
:::

::: {.proposition title="Integration by parts, special case"}
\[
F(x):=\int_{0}^{x} f(y) d y \quad \text { and } \quad G(x):=\int_{0}^{x} g(y) d y \\ 
\implies
\int_{0}^{1} F(x) g(x) d x=F(1) G(1)-\int_{0}^{1} f(x) G(x) d x
.\]
:::

::: {.proof title="?"}
Fubini-Tonelli, and sketch region to change integration bounds.
:::

::: {.theorem title="Lebesgue Density"}
\[
A_{h}(f)(x):=\frac{1}{2 h} \int_{x-h}^{x+h} f(y) d y
\implies {\left\lVert {A_h(f) - f} \right\rVert} \overset{h\to 0}\to 0
.\]
:::

::: {.proof title="?"}
Fubini-Tonelli, and sketch region to change integration bounds, and continuity in \( L^1 \).
:::

## Lp Facts

::: {.proposition title="Dense subspaces of $L^2(I)$ "}
The following are dense subspaces of \( L^2([0, 1]) \):

-   Simple functions
-   Step functions
-   \( C_0([0, 1]) \)
-   Smoothly differentiable functions \( C_0^\infty([0, 1]) \)
-   Smooth compactly supported functions \( C_c^\infty \)
:::

::: {.theorem title="?"}
\[
m(X) < \infty \implies \lim_{p\to\infty} {\left\lVert {f} \right\rVert}_p = {\left\lVert {f} \right\rVert}_\infty 
.\]
:::

::: {.proof title="?"}
Let \( M = {\left\lVert {f} \right\rVert}_\infty \).

-   For any \( L < M \), let \( S = \left\{{{\left\lvert {f} \right\rvert} \geq L}\right\} \).
-   Then \( m(S) > 0 \) and

\[
{\left\lVert {f} \right\rVert}_{p} 
&= \left( \int_X {\left\lvert {f} \right\rvert}^p \right)^{\frac 1 p} \\
&\geq \left( \int_S {\left\lvert {f} \right\rvert}^p \right)^{\frac 1 p} \\
&\geq L ~m(S)^{\frac 1 p} \overset{p\to\infty}\to L \\
&\implies \liminf_p {\left\lVert {f} \right\rVert}_{p} \geq M
.\]

We also have
\[
{\left\lVert {f} \right\rVert}_{p} 
&=  \left( \int_X {\left\lvert {f} \right\rvert}^p \right)^{\frac 1 p} \\
&\leq \left( \int_X M^p \right)^{\frac 1 p} \\
&= M ~m(X)^{\frac 1 p} \xrightarrow{p\to\infty} M \\
&\implies \limsup_p {\left\lVert {f} \right\rVert}_{p} \leq M \hfill\blacksquare
.\]
:::

::: {.theorem title="Duals for $L^p$ spaces"}
For \( 1\leq p< \infty \), \( (L^p)^\vee\cong L^q \).
:::

::: {.proof title="$p=1$ case"}
?
:::

```{=tex}
\todo[inline]{todo}
```
::: {.proof title="$p=2$ case"}
Use Riesz Representation for Hilbert spaces.
:::

::: {.proposition title="$L^1$ is not quite the dual of $L^\\infty$."}
\( L^1 \subset (L^\infty)^\vee \), since the isometric mapping is always injective, but *never* surjective.
:::

# Fourier Transform and Convolution

## The Fourier Transform

::: {.proposition title="?"}
If \( \widehat{f} = \widehat{g} \) then \( f=g \) almost everywhere.
:::

::: {.proposition title="Riemann-Lebesgue: Fourier transforms have small tails."}
\[
f\in L^1 \implies
\widehat{f}(\xi) \rightarrow 0 \text { as }|\xi| \rightarrow \infty
,\]

if \( f \in L^1 \), then \( \widehat{f} \) is continuous and bounded.
:::

::: {.proof title="?"}
```{=tex}
\envlist
```
-   Boundedness:
    \[
    {\left\lvert {\widehat{f}(\xi)} \right\rvert} 
    \leq \int {\left\lvert {f} \right\rvert}\cdot {\left\lvert {e^{2\pi i x\cdot \xi }} \right\rvert} 
    = {\left\lVert {f} \right\rVert}_{1}
    .\]

-   Continuity:

-   \( {\left\lvert {\widehat{f}(\xi_{n}) - \widehat{f} (\xi) } \right\rvert} \)

-   Apply DCT to show \( a\overset{n\to\infty}\to 0 \).
:::

::: {.theorem title="Fourier Inversion"}
\[
f(x)=\int_{\mathbb{R}^{n}} \widehat{f}(x) e^{2 \pi i x \cdot \xi} d \xi
.\]
:::

::: {.warnings}
Fubini-Tonelli does not work here!
:::

::: {.proof title="?"}
Idea: Fubini-Tonelli doesn't work directly, so introduce a convergence factor, take limits, and use uniqueness of limits.

-   Take the modified integral:

\[
I_{t}(x)
&= \int \widehat{f}(\xi) ~e^{2\pi i x \cdot \xi} ~e^{-\pi t^2 {\left\lvert {\xi} \right\rvert}^2} \\
&= \int \widehat{f}(\xi) \phi(\xi) \\
&= \int f(\xi) \widehat{\phi}(\xi) \\
&= \int f(\xi) \widehat{\widehat{g}}(\xi - x) \\
&= \int f(\xi) g_{t}(x - \xi)  ~d\xi \\
&= \int f(y-x) g_{t}(y) ~dy  \quad (\xi = y-x)\\
&= (f \ast g_{t}) \\
&\to f \text{ in $L^1$ as }t \to 0
.\]

-   We also have
    \[
    \lim_{t\to 0} I_{t}(x)
    &= 
    \lim_{t\to 0} \int \widehat{f}(\xi) ~e^{2\pi i x \cdot \xi} ~e^{-\pi t^2 {\left\lvert {\xi} \right\rvert}^2} \\
    &= 
    \lim_{t\to 0} \int \widehat{f}(\xi) \phi(\xi) \\
    &=_{DCT} 
    \int \widehat{f}(\xi) \lim_{t\to 0} \phi(\xi) \\
    &=
    \int \widehat{f}(\xi) ~e^{2\pi i x \cdot \xi} \\
    .\]

-   So
    \[
    I_{t}(x) \to \int \widehat{f}(\xi) ~e^{2\pi i x \cdot \xi} ~\text{ pointwise and }~{\left\lVert {I_{t}(x) - f(x)} \right\rVert}_{1} \to 0
    .\]

-   So there is a subsequence \( I_{t_{n}} \) such that \( I_{t_{n}}(x) \to f(x) \) almost everywhere

-   Thus \( f(x) = \int \widehat{f}(\xi) ~e^{2\pi i x \cdot \xi} \) almost everywhere by uniqueness of limits.
:::

::: {.proposition title="Eigenfunction of the Fourier transform"}
\[
g(x) \coloneqq e^{-\pi {\left\lvert {t} \right\rvert}^2} \implies \widehat{g}(\xi) = g(\xi) {\quad \operatorname{and} \quad}
\widehat{g}_{t}(x) = g(tx) = e^{-\pi t^2 {\left\lvert {x} \right\rvert}^2}
.\]
:::

## Approximate Identities

::: {.example title="of an approximation to the identity."}
\[
\phi(x) \coloneqq e^{-\pi x^2}
.\]
:::

::: {.theorem title="Convolving against an approximate identity converges in $L^1$."}
\[
{\left\lVert {f \ast \phi_{t} - f} \right\rVert}_{1} \overset{t\to 0}\to 0
.\]
:::

::: {.proof title="?"}
\[
{\left\lVert {f - f\ast \phi_{t}} \right\rVert}_1 
&= \int f(x) - \int f(x-y)\phi_{t}(y) ~dy dx \\
&= \int f(x)\int \phi_{t}(y) ~dy - \int f(x-y)\phi_{t}(y) ~dy dx \\
&= \int \int \phi_{t}(y)[f(x) - f(x-y)] ~dy dx \\
&=_{FT} \int \int \phi_{t}(y)[f(x) - f(x-y)] ~dx dy \\
&= \int \phi_{t}(y) \int f(x) - f(x-y) ~dx dy \\
&= \int \phi_{t}(y) {\left\lVert {f - \tau_{y} f} \right\rVert}_1 dy \\
&= \int_{y < \delta} \phi_{t}(y) {\left\lVert {f - \tau_{y} f} \right\rVert}_1 dy  +
\int_{y \geq \delta} \phi_{t}(y) {\left\lVert {f - \tau_{y} f} \right\rVert}_1 dy \\
&\leq \int_{y < \delta} \phi_{t}(y) \varepsilon +
\int_{y \geq \delta} \phi_{t}(y) \left( {\left\lVert {f} \right\rVert}_1 + {\left\lVert {\tau_{y} f} \right\rVert}_1 \right) dy \quad\text{by continuity in } L^1 \\
&\leq \varepsilon + 
2{\left\lVert {f} \right\rVert}_1 \int_{y \geq \delta} \phi_{t}(y) dy \\
&\leq \varepsilon + 2{\left\lVert {f} \right\rVert}_1 \cdot \varepsilon \quad\text{since $\phi_{t}$ has small tails} \\
&\overset{\varepsilon\to 0}\to 0 
.\]
:::

::: {.theorem title="Convolutions vanish at infinity"}
\[
f,g \in L^1 \text{ and  bounded}  \implies \lim_{|x| \rightarrow \infty} (f * g)(x) = 0
.\]
:::

::: {.proof title="?"}
-   Choose \( M \geq f,g \).

-   By small tails, choose \( N \) such that \( \int_{B_{N}^c} {\left\lvert {f} \right\rvert}, \int_{B_{n}^c} {\left\lvert {g} \right\rvert} < \varepsilon \)

-   Note
    \[
    {\left\lvert {f \ast g} \right\rvert} \leq \displaystyle\int {\left\lvert {f(x-y)} \right\rvert} ~{\left\lvert {g(y)} \right\rvert} ~dy \coloneqq I
    .\]

-   Use \( {\left\lvert {x} \right\rvert} \leq {\left\lvert {x-y} \right\rvert} + {\left\lvert {y} \right\rvert} \), take \( {\left\lvert {x} \right\rvert}\geq 2N \) so either
    \[
    {\left\lvert {x-y} \right\rvert} \geq N \implies I \leq \int_{\left\{{x-y \geq N}\right\}} {\left\lvert {f(x-y)} \right\rvert}M ~dy\leq \varepsilon M \to 0
    \]
    then
    \[
    {\left\lvert {y} \right\rvert} \geq N \implies I \leq \int_{\left\{{y \geq N}\right\}} M{\left\lvert {g(y)} \right\rvert} ~dy\leq  M \varepsilon \to 0
    .\]
:::

::: {.proposition title="Corollary of Young's inequality"}
Take \( q = 1 \) in Young's inequality to obtain
\[
{\left\lVert {f \ast g} \right\rVert}_{p} \leq {\left\lVert {f} \right\rVert}p {\left\lVert {g} \right\rVert}1
.\]
:::

::: {.proposition title="$L^1$ is closed under convolution."}
If \( f, g \in L^1 \) then \( f\ast g\in L^1 \).
:::

# Functional Analysis

## Theorems

::: {.theorem title="Bessel's Inequality"}
For any orthonormal set \( \left\{{u_{n}}\right\} \subseteq {\mathcal{H}} \) a Hilbert space (not necessarily a basis),
\[
\left\|x-\sum_{n=1}^{N}\left\langle x, u_{n}\right\rangle u_{n}\right\|^{2}=\|x\|^{2}-\sum_{n=1}^{N}\left|\left\langle x, u_{n}\right\rangle\right|^{2}
\]
and thus
\[
\sum_{n=1}^{\infty}\left|\left\langle x, u_{n}\right\rangle\right|^{2} \leq\|x\|^{2}
.\]
:::

::: {.proof title="of Bessel's inequality"}
```{=tex}
\envlist
```
-   Let \( S_{N} = \sum_{n=1}^N {\left\langle {x},~{u_{n}} \right\rangle} u_{n} \)
    \[
    {\left\lVert {x - S_{N}} \right\rVert}^2 
    &= {\left\langle {x - S_{n}},~{x - S_{N}} \right\rangle} \\
    &= {\left\lVert {x} \right\rVert}^2 + {\left\lVert {S_{N}} \right\rVert}^2 - 2\Re{\left\langle {x},~{S_{N}} \right\rangle} \\
    &= {\left\lVert {x} \right\rVert}^2 + {\left\lVert {S_{N}} \right\rVert}^2 - 2\Re {\left\langle {x},~{\sum_{n=1}^N {\left\langle {x},~{u_{n}} \right\rangle}u_{n}} \right\rangle} \\
    &= {\left\lVert {x} \right\rVert}^2 + {\left\lVert {S_{N}} \right\rVert}^2 - 2\Re \sum_{n=1}^N {\left\langle {x},~{ {\left\langle {x},~{u_{n}} \right\rangle}u_{n}} \right\rangle} \\
    &= {\left\lVert {x} \right\rVert}^2 + {\left\lVert {S_{N}} \right\rVert}^2 - 2\Re \sum_{n=1}^N \overline{{\left\langle {x},~{u_{n}} \right\rangle}}{\left\langle {x},~{u_{n}} \right\rangle} \\
    &= {\left\lVert {x} \right\rVert}^2 + \left\|\sum_{n=1}^N {\left\langle {x},~{u_{n}} \right\rangle} u_{n}\right\|^2 - 2 \sum_{n=1}^N {\left\lvert {{\left\langle {x},~{u_{n}} \right\rangle}} \right\rvert}^2 \\
    &= {\left\lVert {x} \right\rVert}^2 + \sum_{n=1}^N {\left\lvert {{\left\langle {x},~{u_{n}} \right\rangle}} \right\rvert}^2 - 2 \sum_{n=1}^N {\left\lvert {{\left\langle {x},~{u_{n}} \right\rangle}} \right\rvert}^2 \\
    &= {\left\lVert {x} \right\rVert}^2 - \sum_{n=1}^N {\left\lvert {{\left\langle {x},~{u_{n}} \right\rangle}} \right\rvert}^2
    .\]

-   By continuity of the norm and inner product, we have
    \[
    \lim_{N\to\infty} {\left\lVert {x - S_{N}} \right\rVert}^2 
    &= \lim_{N\to\infty} {\left\lVert {x} \right\rVert}^2 - \sum_{n=1}^N {\left\lvert {{\left\langle {x},~{u_{n}} \right\rangle}} \right\rvert}^2 \\
    \implies {\left\lVert {x - \lim_{N\to\infty} S_{N}} \right\rVert}^2 &= {\left\lVert {x} \right\rVert}^2 - \lim_{N\to\infty}\sum_{n=1}^N {\left\lvert {{\left\langle {x},~{u_{n}} \right\rangle}} \right\rvert}^2\\
    \implies 
    {\left\lVert {x - \sum_{n=1}^\infty {\left\langle {x},~{u_{n}} \right\rangle} u_{n}} \right\rVert}^2 &= {\left\lVert {x} \right\rVert}^2 - 
    \sum_{n=1}^\infty {\left\lvert {{\left\langle {x},~{u_{n}} \right\rangle}} \right\rvert}^2
    .\]

-   Then noting that \( 0 \leq {\left\lVert {x - S_{N}} \right\rVert}^2 \),
    \[
    0 &\leq 
    {\left\lVert {x} \right\rVert}^2 - 
    \sum_{n=1}^\infty {\left\lvert {{\left\langle {x},~{u_{n}} \right\rangle}} \right\rvert}^2 \\
    \implies 
    \sum_{n=1}^\infty {\left\lvert {{\left\langle {x},~{u_{n}} \right\rangle}} \right\rvert}^2 &\leq 
    {\left\lVert {x} \right\rVert}^2 \hfill\blacksquare
    .\]
:::

::: {.theorem title="Riesz Representation for Hilbert Spaces"}
If \( \Lambda \) is a continuous linear functional on a Hilbert space \( H \), then there exists a unique \( y \in H \) such that
\[
\forall x\in H,\quad \Lambda(x) = {\left\langle {x},~{y} \right\rangle}.
.\]
:::

::: {.proof title="?"}
```{=tex}
\envlist
```
-   Define \( M \coloneqq\ker \Lambda \).
-   Then \( M \) is a closed subspace and so \( H = M \oplus M^\perp \)
-   There is some \( z\in M^\perp \) such that \( {\left\lVert {z} \right\rVert} = 1 \).
-   Set \( u \coloneqq\Lambda(x) z - \Lambda(z) x \)
-   Check

\[\Lambda(u) = \Lambda(\Lambda(x) z - \Lambda(z) x) = \Lambda(x) \Lambda(z) - \Lambda(z) \Lambda(x) = 0 \implies u\in M\]

-   Compute

\[
0 &= {\left\langle {u},~{z} \right\rangle} \\ 
&= {\left\langle {\Lambda(x) z - \Lambda(z) x},~{z} \right\rangle} \\
&= {\left\langle {\Lambda(x) z},~{z} \right\rangle} - {\left\langle {\Lambda(z) x},~{z} \right\rangle} \\
&= \Lambda(x) {\left\langle {z},~{z} \right\rangle} - \Lambda(z) {\left\langle {x},~{z} \right\rangle} \\
&= \Lambda(x) {\left\lVert {z} \right\rVert}^2 - \Lambda(z) {\left\langle {x},~{z} \right\rangle} \\
&= \Lambda(x) - \Lambda(z) {\left\langle {x},~{z} \right\rangle} \\
&= \Lambda(x) -  {\left\langle {x},~{\overline{\Lambda(z)} z} \right\rangle}
,\]

-   Choose \( y \coloneqq\overline{\Lambda(z)} z \).
-   Check uniqueness:

\[
{\left\langle {x},~{y} \right\rangle} &= {\left\langle {x},~{y'} \right\rangle} \quad\forall x \\
\implies  {\left\langle {x},~{y-y'} \right\rangle} &= 0 \quad\forall x \\
\implies {\left\langle {y-y'},~{y-y'} \right\rangle} &= 0 \\
\implies {\left\lVert {y-y'} \right\rVert} &= 0 \\
\implies y-y' &= \mathbf{0} \implies y = y'
.\]
:::

::: {.theorem title="Functionals are continuous if and only if bounded"}
Let \( L:X \to {\mathbb{C}} \) be a linear functional, then the following are equivalent:

1.  \( L \) is continuous
2.  \( L \) is continuous at zero
3.  \( L \) is bounded, i.e. \( \exists c\geq 0 {~\mathrel{\Big|}~}{\left\lvert {L(x)} \right\rvert} \leq c {\left\lVert {x} \right\rVert} \) for all \( x\in H \)
:::

::: {.proof title="?"}
\( 2 \implies 3 \): Choose \( \delta < 1 \) such that
\[
{\left\lVert {x} \right\rVert} \leq \delta \implies {\left\lvert {L(x)} \right\rvert} < 1.
\]
Then
\[
{\left\lvert {L(x)} \right\rvert} 
&= {\left\lvert {L\left( \frac{{\left\lVert {x} \right\rVert}}{\delta} \frac{\delta }{{\left\lVert {x} \right\rVert}} x \right)} \right\rvert} \\
&= \frac{{\left\lVert {x} \right\rVert}}{\delta} ~{\left\lvert {L\left( \delta \frac{x }{{\left\lVert {x} \right\rVert}} \right)} \right\rvert} \\
&\leq \frac{{\left\lVert {x} \right\rVert}}{\delta} 1
,\]
so we can take \( c = \frac 1 \delta \). \( \hfill\blacksquare \)

\( 3 \implies 1 \):

We have \( {\left\lvert {L(x-y)} \right\rvert} \leq c{\left\lVert {x-y} \right\rVert} \), so given \( \varepsilon \geq 0 \) simply choose \( \delta = \frac \varepsilon c \).
:::

::: {.theorem title="The operator norm is a norm"}
If \( H \) is a Hilbert space, then \( (H^\vee, {\left\lVert {{\,\cdot\,}} \right\rVert}_{\text{op}}) \) is a normed space.
:::

::: {.proof title="?"}
The only nontrivial property is the triangle inequality, but
\[
{\left\lVert {L_{1} + L_{2}} \right\rVert}_{^{\operatorname{op}}} = \sup {\left\lvert {L_{1}(x) + L_{2}(x)} \right\rvert} \leq \sup {\left\lvert {L_{1}(x)} \right\rvert} + {\left\lvert {\sup L_{2}(x)} \right\rvert} = {\left\lVert {L_{1}} \right\rVert}_{^{\operatorname{op}}}+ {\left\lVert {L_{2}} \right\rVert}_{^{\operatorname{op}}}
.\]
:::

::: {.theorem title="The operator norm on $X\\dual$ yields a Banach space"}
If \( X \) is a normed vector space, then \( (X^\vee, {\left\lVert {{\,\cdot\,}} \right\rVert}_{\text{op}}) \) is a Banach space.
:::

::: {.proof title="?"}
```{=tex}
\envlist
```
-   Let \( \left\{{L_{n}}\right\} \) be Cauchy in \( X^\vee \).

-   Then for all \( x\in C \), \( \left\{{L_{n}(x)}\right\} \subset {\mathbb{C}} \) is Cauchy and converges to something denoted \( L(x) \).

-   Need to show \( L \) is continuous and \( {\left\lVert {L_{n} - L} \right\rVert} \to 0 \).

-   Since \( \left\{{L_{n}}\right\} \) is Cauchy in \( X^\vee \), choose \( N \) large enough so that
    \[
    n, m \geq N \implies {\left\lVert {L_{n} - L_{m}} \right\rVert} < \varepsilon \implies {\left\lvert {L_{m}(x) - L_{n}(x)} \right\rvert} < \varepsilon \quad \forall x {~\mathrel{\Big|}~}{\left\lVert {x} \right\rVert} = 1
    .\]

-   Take \( n\to \infty \) to obtain
    \[m \geq N 
    &\implies {\left\lvert {L_{m}(x) - L(x)} \right\rvert} < \varepsilon \quad \forall x {~\mathrel{\Big|}~}{\left\lVert {x} \right\rVert} = 1\\
    &\implies {\left\lVert {L_{m} - L} \right\rVert} < \varepsilon \to 0
    .\]

-   Continuity:
    \[
    {\left\lvert {L(x)} \right\rvert} &= {\left\lvert {L(x) - L_{n}(x) + L_{n}(x)} \right\rvert} \\
    &\leq  {\left\lvert {L(x) - L_{n}(x)} \right\rvert} + {\left\lvert {L_{n}(x)} \right\rvert} \\
    &\leq \varepsilon {\left\lVert {x} \right\rVert} + c{\left\lVert {x} \right\rVert} \\
    &= (\varepsilon + c){\left\lVert {x} \right\rVert} \hfill\blacksquare
    .\]
:::

::: {.theorem title="Riesz-Fischer"}
Let \( U = \left\{{u_{n}}\right\}_{n=1}^\infty \) be an orthonormal set (not necessarily a basis), then

1.  There is an isometric surjection

\[
\mathcal{H} &\to \ell^2({\mathbb{N}}) \\
\mathbf{x} &\mapsto \left\{{{\left\langle {\mathbf{x}},~{\mathbf{u}_{n}} \right\rangle}}\right\}_{n=1}^\infty
\]

i.e. if \( \left\{{a_{n}}\right\} \in \ell^2({\mathbb{N}}) \), so \( \sum {\left\lvert {a_{n}} \right\rvert}^2 < \infty \), then there exists a \( \mathbf{x} \in \mathcal{H} \) such that
\[
a_{n} = {\left\langle {\mathbf{x}},~{\mathbf{u}_{n}} \right\rangle} \quad \forall n.
\]

2.  \( \mathbf{x} \) can be chosen such that
    \[
    {\left\lVert {\mathbf{x}} \right\rVert}^2 = \sum {\left\lvert {a_{n}} \right\rvert}^2
    \]

> Note: the choice of \( \mathbf{x} \) is unique \( \iff \) \( \left\{{u_{n}}\right\} \) is **complete**, i.e. \( {\left\langle {\mathbf{x}},~{\mathbf{u}_{n}} \right\rangle} = 0 \) for all \( n \) implies \( \mathbf{x} = \mathbf{0} \).
:::

::: {.proof title="?"}
```{=tex}
\envlist
```
-   Given \( \left\{{a_{n}}\right\} \), define \( S_{N} = \sum^N a_{n} \mathbf{u}_{n} \).
-   \( S_{N} \) is Cauchy in \( \mathcal{H} \) and so \( S_{N} \to \mathbf{x} \) for some \( \mathbf{x} \in \mathcal{H} \).
-   \( {\left\langle {x},~{u_{n}} \right\rangle} = {\left\langle {x - S_{N}},~{u_{n}} \right\rangle} + {\left\langle {S_{N}},~{u_{n}} \right\rangle} \to a_{n} \)
-   By construction, \( {\left\lVert {x-S_{N}} \right\rVert}^2 = {\left\lVert {x} \right\rVert}^2 - \sum^N {\left\lvert {a_{n}} \right\rvert}^2 \to 0 \), so \( {\left\lVert {x} \right\rVert}^2 = \sum^\infty {\left\lvert {a_{n}} \right\rvert}^2 \).
:::

# Extra Problems

## Greatest Hits

-   \( \star \): Show that for \( E\subseteq {\mathbb{R}}^n \), TFAE:

    1.  \( E \) is measurable
    2.  \( E = H\cup Z \) here \( H \) is \( F_\sigma \) and \( Z \) is null
    3.  \( E = V\setminus Z' \) where \( V\in G_\delta \) and \( Z' \) is null.

-   \( \star \): Show that if \( E\subseteq {\mathbb{R}}^n \) is measurable then \( m(E) = \sup \left\{{ m(K) {~\mathrel{\Big|}~}K\subset E\text{ compact}}\right\} \) iff for all \( \varepsilon> 0 \) there exists a compact \( K\subseteq E \) such that \( m(K) \geq m(E) - \varepsilon \).

-   \( \star \): Show that cylinder functions are measurable, i.e. if \( f \) is measurable on \( {\mathbb{R}}^s \), then \( F(x, y) \coloneqq f(x) \) is measurable on \( {\mathbb{R}}^s\times{\mathbb{R}}^t \) for any \( t \).

-   \( \star \): Prove that the Lebesgue integral is translation invariant, i.e. if \( \tau_h(x) = x+h \) then \( \int \tau_h f = \int f \).

-   \( \star \): Prove that the Lebesgue integral is dilation invariant, i.e. if \( f_\delta(x) = {f({x\over \delta}) \over \delta^n} \) then \( \int f_\delta = \int f \).

-   \( \star \): Prove continuity in \( L^1 \), i.e.
    \[
    f \in L^{1} \Longrightarrow \lim _{h \rightarrow 0} \int|f(x+h)-f(x)|=0
    .\]

-   \( \star \): Show that
    \[f,g \in L^1 \implies f\ast g \in L^1 {\quad \operatorname{and} \quad} {\left\lVert {f\ast g} \right\rVert}_1 \leq {\left\lVert {f} \right\rVert}_1 {\left\lVert {g} \right\rVert}_1.\]

-   \( \star \): Show that if \( X\subseteq {\mathbb{R}} \) with \( \mu(X) < \infty \) then
    \[  
    {\left\lVert {f} \right\rVert}_p \overset{p\to\infty}\to {\left\lVert {f} \right\rVert}_\infty
    .\]

## By Topic

### Topology

-   Show that every compact set is closed and bounded.
-   Show that if a subset of a metric space is complete and totally bounded, then it is compact.
-   Show that if \( K \) is compact and \( F \) is closed with \( K, F \) disjoint then \( \operatorname{dist}(K, F) > 0 \).

### Continuity

-   Show that a continuous function on a compact set is uniformly continuous.

### Differentiation

-   Show that if \( f\in C^1({\mathbb{R}}) \) and both \( \lim_{x\to \infty} f(x) \) and \( \lim_{x\to \infty} f'(x) \) exist, then \( \lim_{x\to\infty} f'(x) \) must be zero.

### Advanced Limitology

-   If \( f \) is continuous, is it necessarily the case that \( f' \) is continuous?
-   If \( f_n \to f \), is it necessarily the case that \( f_n' \) converges to \( f' \) (or at all)?
-   Is it true that the sum of differentiable functions is differentiable?
-   Is it true that the limit of integrals equals the integral of the limit?
-   Is it true that a limit of continuous functions is continuous?
-   Show that a subset of a metric space is closed iff it is complete.
-   Show that if \( m(E) < \infty \) and \( f_n\to f \) uniformly, then \( \lim \int_E f_n = \int_E f \).

Uniform Convergence

-   Show that a uniform limit of bounded functions is bounded.
-   Show that a uniform limit of continuous function is continuous.
    -   I.e. if \( f_n\to f \) uniformly with each \( f_n \) continuous then \( f \) is continuous.
-   Show that if \( f_n\to f \) pointwise, \( f_n' \to g \) uniformly for some \( f, g \), then \( f \) is differentiable and \( g = f' \).
-   Prove that uniform convergence implies pointwise convergence implies a.e. convergence, but none of the implications may be reversed.
-   Show that \( \sum {x^n \over n!} \) converges uniformly on any compact subset of \( {\mathbb{R}} \).

Measure Theory

-   Show that continuity of measure from above/below holds for outer measures.

-   Show that a countable union of null sets is null.

Measurability

-   Show that \( f=0 \) a.e. iff \( \int_E f = 0 \) for every measurable set \( E \).

Integrability

-   Show that if \( f \) is a measurable function, then \( f=0 \) a.e. iff \( \int f = 0 \).
-   Show that a bounded function is Lebesgue integrable iff it is measurable.
-   Show that simple functions are dense in \( L^1 \).
-   Show that step functions are dense in \( L^1 \).
-   Show that smooth compactly supported functions are dense in \( L^1 \).

Convergence

-   Prove Fatou's lemma using the Monotone Convergence Theorem.
-   Show that if \( \left\{{f_n}\right\} \) is in \( L^1 \) and \( \sum \int {\left\lvert {f_n} \right\rvert} < \infty \) then \( \sum f_n \) converges to an \( L^1 \) function and
    \[\int \sum f_n = \sum \int f_n.\]

Convolution

-   Show that if \( f\in L^1 \) and \( g \) is bounded, then \( f\ast g \) is bounded and uniformly continuous.
-   If \( f, g \) are compactly supported, is it necessarily the case that \( f\ast g \) is compactly supported?
-   Show that under any of the following assumptions, \( f\ast g \) vanishes at infinity:
    -   \( f, g\in L^1 \) are both bounded.
    -   \( f, g\in L^1 \) with just \( g \) bounded.
    -   \( f, g \) smooth and compactly supported (and in fact \( f\ast g \) is smooth)
    -   \( f\in L^1 \) and \( g \) smooth and compactly supported (and in fact \( f\ast g \) is smooth)
-   Show that if \( f\in L^1 \) and \( g' \) exists with \( {\frac{\partial g}{\partial x_i}\,} \) all bounded, then
    \[{\frac{\partial }{\partial x_i}\,}(f\ast g) = f \ast {\frac{\partial g}{\partial x_i}\,}\]

Fourier Analysis

-   Show that if \( f\in L^1 \) then \( \widehat{f} \) is bounded and uniformly continuous.
-   Is it the case that \( f\in L^1 \) implies \( \widehat{f}\in L^1 \)?
-   Show that if \( f, \widehat{f} \in L^1 \) then \( f \) is bounded, uniformly continuous, and vanishes at infinity.
    -   Show that this is not true for arbitrary \( L^1 \) functions.
-   Show that if \( f\in L^1 \) and \( \widehat{f} = 0 \) almost everywhere then \( f = 0 \) almost everywhere.
    -   Prove that \( \widehat{f} = \widehat{g} \) implies that \( f=g \) a.e.
-   Show that if \( f, g \in L^1 \) then
    \[\int \widehat{f} g = \int f\widehat{g}.\]
    -   Give an example showing that this fails if \( g \) is not bounded.
-   Show that if \( f\in C^1 \) then \( f \) is equal to its Fourier *series*.

Approximate Identities

-   Show that if \( \phi \) is an approximate identity, then
    \[{\left\lVert {f\ast \phi_t - f} \right\rVert}_1 \overset{t\to 0}\to 0.\]
    -   Show that if additionally \( {\left\lvert {\phi(x)} \right\rvert} \leq c(1 + {\left\lvert {x} \right\rvert})^{-n-\varepsilon} \) for some \( c,\varepsilon>0 \), then this converges is almost everywhere.
-   Show that is \( f \) is bounded and uniformly continuous and \( \phi_t \) is an approximation to the identity, then \( f\ast \phi_t \) uniformly converges to \( f \).

\( L^p \) Spaces

-   Show that if \( E\subseteq {\mathbb{R}}^n \) is measurable with \( \mu(E) < \infty \) and \( f\in L^p(X) \) then
    \[{\left\lVert {f} \right\rVert}_{L^p(X)} \overset{p\to\infty}\to {\left\lVert {f} \right\rVert}_\infty.\]
-   Is it true that the converse to the DCT holds? I.e. if \( \int f_n \to \int f \), is there a \( g\in L^p \) such that \( f_n < g \) a.e. for every \( n \)?
-   Prove continuity in \( L^p \): If \( f \) is uniformly continuous then for all \( p \),
    \[{\left\lVert {\tau_h f - f} \right\rVert}_p \overset{h\to 0}\to 0.\]
-   Prove the following inclusions of \( L^p \) spaces for \( m(X) < \infty \):
    \[
    L^\infty(X) &\subset L^2(X) \subset L^1(X) \\
    \ell^2({\mathbb{Z}}) &\subset \ell^1({\mathbb{Z}}) \subset \ell^\infty({\mathbb{Z}})
    .\]

# Midterm Exam 2 (December 2014)

## 1

> Note: (a) is a repeat.

-   Let \( \Lambda\in L^2(X)^\vee \).
    -   Show that \( M\coloneqq\left\{{f\in L^2(X) {~\mathrel{\Big|}~}\Lambda(f) = 0}\right\} \subseteq L^2(X) \) is a closed subspace, and \( L^2(X) = M \oplus M\perp \).
    -   Prove that there exists a unique \( g\in L^2(X) \) such that \( \Lambda(f) = \int_X g \mkern 1.5mu\overline{\mkern-1.5muf\mkern-1.5mu}\mkern 1.5mu \).

## 2

a.  In parts:

-   Given a definition of \( L^\infty({\mathbb{R}}^n) \).
-   Verify that \( {\left\lVert {{\,\cdot\,}} \right\rVert}_\infty \) defines a norm on \( L^\infty({\mathbb{R}}^n) \).
-   Carefully proved that \( (L^\infty({\mathbb{R}}^n), {\left\lVert {{\,\cdot\,}} \right\rVert}_\infty) \) is a Banach space.

b.  Prove that for any measurable \( f:{\mathbb{R}}^n \to {\mathbb{C}} \), `\begin{align*}
    L^1({\mathbb{R}}^n) \cap L^\infty({\mathbb{R}}^n) \subset L^2({\mathbb{R}}^n) {\quad \operatorname{and} \quad} {\left\lVert {f} \right\rVert}_2 \leq {\left\lVert {f} \right\rVert}_1^{1\over 2} \cdot {\left\lVert {f} \right\rVert}_\infty^{1\over 2}
    .\end{align*}`{=tex}

## 3

a.  Prove that if \( f, g: {\mathbb{R}}^n\to {\mathbb{C}} \) is both measurable then \( F(x, y) \coloneqq f(x) \) and \( h(x, y)\coloneqq f(x-y) g(y) \) is measurable on \( {\mathbb{R}}^n\times{\mathbb{R}}^n \).

b.  Show that if \( f\in L^1({\mathbb{R}}^n) \cap L^\infty({\mathbb{R}}^n) \) and \( g\in L^1({\mathbb{R}}^n) \), then \( f\ast g \in L^1({\mathbb{R}}^n) \cap L^\infty({\mathbb{R}}^n) \) is well defined, and carefully show that it satisfies the following properties: `\begin{align*}
    {\left\lVert {f\ast g} \right\rVert}_\infty &\leq {\left\lVert {g} \right\rVert}_1 {\left\lVert {f} \right\rVert}_\infty
    {\left\lVert {f\ast g} \right\rVert}_1      &\leq {\left\lVert {g} \right\rVert}_1 {\left\lVert {f} \right\rVert}_1
    {\left\lVert {f\ast g} \right\rVert}_2      &\leq {\left\lVert {g} \right\rVert}_1 {\left\lVert {f} \right\rVert}_2
    .\end{align*}`{=tex}

> Hint: first show \( {\left\lvert {f\ast g} \right\rvert}^2 \leq {\left\lVert {g} \right\rVert}_1 \qty{ {\left\lvert {f} \right\rvert}^2 \ast {\left\lvert {g} \right\rvert}} \).

## 4 (Weierstrass Approximation Theorem)

> Note: (a) is a repeat.

Let \( f: [0, 1]\to {\mathbb{R}} \) be continuous, and prove the Weierstrass approximation theorem: for any \( \varepsilon> 0 \) there exists a polynomial \( P \) such that \( {\left\lVert {f - P} \right\rVert}_{\infty} < \varepsilon \).

# Midterm Exam 1 (October 2018)

## Problem 1

Let \( E \subseteq {\mathbb{R}}^n \) be bounded. Prove the following are equivalent:

1.  For any \( \epsilon>0 \) there exists and open set \( G \) and a closed set \( F \) such that
    \[
    F \subseteq E \subseteq G && m(G\setminus F) < \epsilon
    .\]

2.  There exists a \( G_ \delta \) set \( V \) and an \( F_ \sigma \) set \( H \) such that
    \[
    m(V\setminus H) = 0
    .\]

## Problem 2

Let \( \left\{{ f_k }\right\} _{k=1}^{\infty } \) be a sequence of extended real-valued Lebesgue measurable functions.

a.  Prove that \( \sup_k f_k \) is a Lebesgue measurable function.

b.  Prove that if \( \lim_{k \to \infty } f_k(x) \) exists for every \( x \in {\mathbb{R}}^n \) then \( \lim_{k\to \infty } f_k \) is also a measurable function.

## Problem 3

### a

Prove that if \( E \subseteq {\mathbb{R}}^n \) is a Lebesgue measurable set, then for any \( h \in {\mathbb{R}} \) the set
\[
E+h \coloneqq\left\{{x + h {~\mathrel{\Big|}~}x\in E }\right\}
\]
is also Lebesgue measurable and satisfies \( m(E + h) = m(E) \).

### b

Prove that if \( f \) is a non-negative measurable function on \( {\mathbb{R}}^n \) and \( h\in {\mathbb{R}}^n \) then the function
\[
\tau_h d(x) \coloneqq f(x-h)
\]
is a non-negative measurable function and
\[
\int f(x) \,dx= \int f(x-h) \,dx
.\]

## Problem 4

Let \( f: {\mathbb{R}}^n\to {\mathbb{R}} \) be a Lebesgue measurable function.

a.  Prove that for all \( \alpha> 0 \) ,
    \[
    A_ \alpha  \coloneqq\left\{{x\in {\mathbb{R}}^n {~\mathrel{\Big|}~}{\left\lvert { f(x) } \right\rvert} > \alpha}\right\} \implies m(A_ \alpha) \leq {1\over \alpha} \int {\left\lvert {f (x)} \right\rvert} \,dx
    .\]

b.  Prove that
    \[
    \int {\left\lvert { f(x) } \right\rvert} \,dx= 0 \iff f = 0 \text{ almost everywhere}
    .\]

## Problem 5

Let \( \left\{{ f_k }\right\}_{k=1}^{\infty } \subseteq L^2([0, 1]) \) be a sequence which *converges in \( L^1 \)* to a function \( f \).

a.  Prove that \( f\in L^1([0, 1]) \).

b.  Give an example illustrating that \( f_k \) may not converge to \( f \) almost everywhere.

c.  Prove that \( \left\{{f_k}\right\} \) must contain a subsequence that converges to \( f \) almost everywhere.

# Midterm Exam 2 (November 2018)

## Problem 1

Let \( f, g\in L^1([0, 1]) \), define \( F(x) = \int_0^x f(y)\,dy \) and \( G(x) = \int_0^x g(y)\,dy \), and show
\[
\int_0^1 F(x)g(x) \,dx = F(1)G(1) - \int_0^1 f(x) G(x) \, dx
.\]

## Problem 2

Let \( \phi\in L^1({\mathbb{R}}^n) \) such that \( \int \phi = 1 \) and define \( \phi_t(x) = t^{-n}\phi(t^{-1}x) \). Show that if \( f \) is bounded and uniformly continuous then \( f\ast \phi_t \overset{t\to 0}\to f \) uniformly.

## Problem 3

Let \( g\in L^\infty([0, 1]) \).

a.  Prove
    \[
    {\left\lVert {g} \right\rVert}_{L^p([0, 1])}  \overset{p\to\infty}\to {\left\lVert {g} \right\rVert}_{L^\infty([0, 1])}
    .\]

b.  Prove that the map
    \[
    \Lambda_g: L^1([0, 1]) &\to {\mathbb{C}}\\
    f &\mapsto \int_0^1 fg
    \]
    defines an element of \( L^1([0, 1])^\vee \) with \( {\left\lVert {\Lambda_g} \right\rVert}_{L^1([0, 1])^\vee}= {\left\lVert {g} \right\rVert}_{L^\infty([0, 1])} \).

## Problem 4

See `\cref{hilbert_space_exam_question}`{=tex}

# Practice Exam (November 2014)

## 1: Fubini-Tonelli

### a

Carefully state Tonelli's theorem for a nonnegative function \( F(x, t) \) on \( {\mathbb{R}}^n\times{\mathbb{R}} \).

### b

Let \( f:{\mathbb{R}}^n\to [0, \infty] \) and define `\begin{align*}
{\mathcal{A}}\coloneqq\left\{{(x, t) \in {\mathbb{R}}^n\times{\mathbb{R}}{~\mathrel{\Big|}~}0\leq t \leq f(x)}\right\}
.\end{align*}`{=tex}

Prove the validity of the following two statements:

1.  \( f \) is Lebesgue measurable on \( {\mathbb{R}}^{n} \iff {\mathcal{A}} \) is a Lebesgue measurable subset of \( {\mathbb{R}}^{n+1} \).
2.  If \( f \) is Lebesgue measurable on \( {\mathbb{R}}^n \) then `\begin{align*}
    m(\mathcal{A})=\int_{\mathbb{R}^{n}} f(x) d x=\int_{0}^{\infty} m\left(\left\{x \in \mathbb{R}^{n}{~\mathrel{\Big|}~}f(x) \geq t\right\}\right) d t
    .\end{align*}`{=tex}

## 2: Convolutions and the Fourier Transform

### a

Let \( f, g\in L^1({\mathbb{R}}^n) \) and give a definition of \( f\ast g \).

### b

Prove that if \( f, g \) are integrable and bounded, then `\begin{align*}
(f\ast g)(x) \overset{{\left\lvert {x} \right\rvert}\to\infty}\to 0
.\end{align*}`{=tex}

### c

1.  Define the *Fourier transform* of an integrable function \( f \) on \( {\mathbb{R}}^n \).
2.  Give an outline of the proof of the Fourier inversion formula.
3.  Give an example of a function \( f\in L^1({\mathbb{R}}^n) \) such that \( \widehat{f} \) is not in \( L^1({\mathbb{R}}^n) \).

## 3: Hilbert Spaces

`\label{hilbert_space_exam_question}`{=tex}

Let \( \left\{{u_n}\right\}_{n=1}^\infty \) be an orthonormal sequence in a Hilbert space \( H \).

### a

Let \( x\in H \) and verify that `\begin{align*}
\left\|x-\sum_{n=1}^{N}\left\langle x, u_{n}\right\rangle u_{n}\right\|_H^{2}
=
\|x\|_H^{2}-\sum_{n=1}^{N}\left|\left\langle x, u_{n}\right\rangle\right|^{2}
.\end{align*}`{=tex} for any \( N\in {\mathbb{N}} \) and deduce that `\begin{align*}
\sum_{n=1}^{\infty}\left|\left\langle x, u_{n}\right\rangle\right|^{2} \leq\|x\|_H^{2}
.\end{align*}`{=tex}

### b

Let \( \left\{{a_n}\right\}_{n\in {\mathbb{N}}} \in \ell^2({\mathbb{N}}) \) and prove that there exists an \( x\in H \) such that \( a_n = {\left\langle {x},~{u_n} \right\rangle} \) for all \( n\in {\mathbb{N}} \), and moreover \( x \) may be chosen such that `\begin{align*}
{\left\lVert {x} \right\rVert}_H = \qty{ \sum_{n\in {\mathbb{N}}} {\left\lvert {a_n} \right\rvert}^2}^{1\over 2}
.\end{align*}`{=tex}

Proof

:   ```{=tex}
    \hfill
    ```
    -   Take \( \left\{{a_n}\right\} \in \ell^2 \), then note that \( \sum {\left\lvert {a_n} \right\rvert}^2 < \infty \implies \) the tails vanish.

    -   Define \( x \coloneqq\displaystyle\lim_{N\to\infty} S_N \) where \( S_N = \sum_{k=1}^N a_k u_k \)

    -   \( \left\{{S_N}\right\} \) is Cauchy and \( H \) is complete, so \( x\in H \).

    -   By construction, `\begin{align*}
        {\left\langle {x},~{u_n} \right\rangle} = {\left\langle {\sum_k a_k u_k},~{u_n} \right\rangle} = \sum_k a_k {\left\langle {u_k},~{u_n} \right\rangle} = a_n 
        \end{align*}`{=tex} since the \( u_k \) are all orthogonal.

    -   By Pythagoras since the \( u_k \) are normal, `\begin{align*}
        {\left\lVert {x} \right\rVert}^2 = {\left\lVert {\sum_k a_k u_k} \right\rVert}^2 = \sum_k {\left\lVert {a_k u_k} \right\rVert}^2 = \sum_k {\left\lvert {a_k} \right\rvert}^2
        .\end{align*}`{=tex}

### c

Prove that if \( \left\{{u_n}\right\} \) is *complete*, Bessel's inequality becomes an equality.

Proof

:   Let \( x \) and \( u_n \) be arbitrary.

    `\begin{align*}
    {\left\langle {x - \sum_{k=1}^\infty {\left\langle {x},~{u_k} \right\rangle}u_k },~{u_n} \right\rangle}
    &=
    {\left\langle {x},~{u_n} \right\rangle}
    -
    {\left\langle {\sum_{k=1}^\infty {\left\langle {x},~{u_k} \right\rangle}u_k },~{u_n} \right\rangle} \\
    &=
    {\left\langle {x},~{u_n} \right\rangle}
    -
    \sum_{k=1}^\infty  {\left\langle {{\left\langle {x},~{u_k} \right\rangle}u_k },~{u_n} \right\rangle} \\
    &=
    {\left\langle {x},~{u_n} \right\rangle}
    -
    \sum_{k=1}^\infty  {\left\langle {x},~{u_k} \right\rangle} {\left\langle {u_k },~{u_n} \right\rangle} \\
    &= {\left\langle {x},~{u_n} \right\rangle} - {\left\langle {x},~{u_n} \right\rangle} = 0 \\
    \implies 
    x - \sum_{k=1}^\infty {\left\langle {x},~{u_k} \right\rangle}u_k &= 0 \quad\text{by completeness}
    .\end{align*}`{=tex}

    So `\begin{align*}
    x = \sum_{k=1}^\infty {\left\langle {x},~{u_k} \right\rangle} u_k
    \implies
    {\left\lVert {x} \right\rVert}^2 = \sum_{k=1}^\infty {\left\lvert {{\left\langle {x},~{u_k} \right\rangle}} \right\rvert}^2. \hfill\blacksquare
    .\end{align*}`{=tex}

## 4: \( L^p \) Spaces {#lp-spaces}

### a

Prove Holder's inequality: let \( f\in L^p, g\in L^q \) with \( p, q \) conjugate, and show that `\begin{align*}
{\left\lVert {fg} \right\rVert}_{p} \leq {\left\lVert {f} \right\rVert}_{p} \cdot {\left\lVert {g} \right\rVert}_{q}
.\end{align*}`{=tex}

### b

Prove Minkowski's Inequality: `\begin{align*}
1\leq p < \infty \implies {\left\lVert {f+g} \right\rVert}_{p} \leq {\left\lVert {f} \right\rVert}_{p}+ {\left\lVert {g} \right\rVert}_{p}
.\end{align*}`{=tex} Conclude that if \( f, g\in L^p({\mathbb{R}}^n) \) then so is \( f+g \).

### c

Let \( X = [0, 1] \subset {\mathbb{R}} \).

1.  Give a definition of the Banach space \( L^\infty(X) \) of essentially bounded functions of \( X \).

2.  Let \( f \) be non-negative and measurable on \( X \), prove that `\begin{align*}
    \int_X f(x)^p \,dx \overset{p\to\infty}\to
    \begin{dcases}
    \infty \quad\text{or} \\
    m\qty{\left\{{f^{-1}(1)}\right\}}
    \end{dcases}
    ,\end{align*}`{=tex} and characterize the functions of each type

::: {.solution}
`\begin{align*}
\int f^p 
&= \int_{x < 1} f^p + \int_{x=1}f^p + \int_{x > 1} f^p\\
&= \int_{x < 1} f^p + \int_{x=1}1 + \int_{x > 1} f^p \\
&= \int_{x < 1} f^p + m(\left\{{f = 1}\right\}) + \int_{x > 1} f^p \\
&\overset{p\to\infty}\to 0  + m(\left\{{f = 1}\right\}) + 
\begin{cases} 
0 & m(\left\{{x\geq 1}\right\}) = 0 \\ 
\infty & m(\left\{{x\geq 1}\right\}) > 0.
\end{cases}
\end{align*}`{=tex}
:::

```{=html}
<!--\todo{Justify passing limit into integrals.}-->
```
## 5: Dual Spaces

Let \( X \) be a normed vector space.

### a

Give the definition of what it means for a map \( L:X\to {\mathbb{C}} \) to be a *linear functional*.

### b

Define what it means for \( L \) to be *bounded* and show \( L \) is bounded \( \iff L \) is continuous.

### c

Prove that \( (X^\vee, {\left\lVert {{\,\cdot\,}} \right\rVert}_{^{\operatorname{op}}}) \) is a Banach space.

# Common Inequalities

::: {.proposition title="Reverse Triangle Inequality"}
\[  
{\left\lvert {{\left\lVert {x} \right\rVert} - {\left\lVert {y} \right\rVert}} \right\rvert} \leq {\left\lVert {x - y} \right\rVert}
.\]
:::

::: {.proposition title="Chebyshev's Inequality"}
\[  
\mu(\{x:|f(x)|>\alpha\}) \leq\left(\frac{{\left\lVert {f} \right\rVert}_{p}}{\alpha}\right)^{p}
.\]
:::

::: {.proposition title="Holder's Inequality"}
\[  
\frac 1 p + \frac 1 q = 1 \implies {\left\lVert {f g} \right\rVert}_{1} \leq {\left\lVert {f} \right\rVert}_{p} {\left\lVert {g} \right\rVert}_{q}
.\]
:::

::: {.proof title="of Holder's inequality"}
It suffices to show this when \( {\left\lVert {f} \right\rVert}_p = {\left\lVert {g} \right\rVert}_q = 1 \), since
\[  
\|f g\|_{1} \leq\|f\|_{p}\|f\|_{q} \Longleftrightarrow \int \frac{|f|}{\|f\|_{p}} \frac{|g|}{\|g\|_{q}} \leq 1
.\]

Using \( AB \leq \frac 1 p A^p + \frac 1 q B^q \), we have
\[  
\int|f \| g| \leq \int \frac{|f|^{p}}{p} \frac{|g|^{q}}{q}=\frac{1}{p}+\frac{1}{q}=1
.\]
:::

::: {.example title="Application of Holder's inequality: containment of $L^p$ spaces"}
For finite measure spaces,
\[
1 \leq p < q \leq \infty \implies L^q \subset L^p \quad (\text{ and } \ell^p \subset \ell^q)
.\]
:::

::: {.proof title="of containment of $L^p$ spaces"}
Fix \( p, q \), let \( r = \frac q p \) and \( s = \frac{r}{r-1} \) so \( r^{-1}+ s^{-1}= 1 \). Then let \( h = {\left\lvert {f} \right\rvert}^p \):

\[  
{\left\lVert {f} \right\rVert}_{p}^p 
= {\left\lVert {h\cdot 1} \right\rVert}_{1} \leq {\left\lVert {1} \right\rVert}_{s} {\left\lVert {h} \right\rVert}_{r} 
= \mu(X)^{\frac 1 s} {\left\lVert {f} \right\rVert}_{q}^{\frac q r}
\implies {\left\lVert {f} \right\rVert}_{p} 
\leq \mu(X)^{\frac 1 p - \frac 1 q} {\left\lVert {f} \right\rVert}_{q}
.\]

> Note: doesn't work for \( \ell_p \) spaces, but just note that \( \sum {\left\lvert {x_n} \right\rvert} < \infty \implies x_n < 1 \) for large enough \( n \), and thus \( p<q \implies {\left\lvert {x_n} \right\rvert}^q \leq {\left\lvert {x_n} \right\rvert}^q \).
:::

::: {.proposition title="Cauchy-Schwarz Inequality"}
\[  
{\left\lvert {{\left\langle {f},~{g} \right\rangle}} \right\rvert} = {\left\lVert {fg} \right\rVert}_{1} \leq {\left\lVert {f} \right\rVert}_{2} {\left\lVert {g} \right\rVert}_{2}
&& \text{with equality} \iff f = \lambda g
.\]
:::

::: {.remark}
In general, Cauchy-Schwarz relates inner product to norm, and only happens to relate norms in \( L^1 \).
:::

::: {.proposition title="Minkowski's Inequality"}
\[  
1\leq p < \infty \implies {\left\lVert {f+g} \right\rVert}_{p} \leq {\left\lVert {f} \right\rVert}_{p}+ {\left\lVert {g} \right\rVert}_{p}
.\]
:::

::: {.remark}
This does not handle \( p=\infty \) case. Use to prove \( L^p \) is a normed space.
:::

::: {.proof title="?"}
```{=tex}
\envlist
```
-   We first note
    \[  
    {\left\lvert {f+g} \right\rvert}^p = {\left\lvert {f+g} \right\rvert}{\left\lvert {f+g} \right\rvert}^{p-1} \leq \left( {\left\lvert {f} \right\rvert} + {\left\lvert {g} \right\rvert}\right) {\left\lvert {f+g} \right\rvert}^{p-1}
    .\]

-   Note that if \( p,q \) are conjugate exponents then
    \[  
    \frac 1 q &= 1 - \frac 1 p = \frac{p-1} p \\
    q &= \frac p {p-1} 
    .\]

-   Then taking integrals yields
    \[  
    {\left\lVert {f+g} \right\rVert}_p^p &=
    \int {\left\lvert {f+g} \right\rvert}^p \\
    &\leq \int \left( {\left\lvert {f} \right\rvert} + {\left\lvert {g} \right\rvert}\right) {\left\lvert {f+g} \right\rvert}^{p-1} \\ 
    &= \int {\left\lvert {f} \right\rvert} {\left\lvert {f+g} \right\rvert}^{p-1} + \int {\left\lvert {g} \right\rvert} {\left\lvert {f+g} \right\rvert}^{p-1} \\
    &= {\left\lVert {f(f+g)^{p-1}} \right\rVert}_1 + {\left\lVert {g(f+g)^{p-1}} \right\rVert}_1 \\
    &\leq {\left\lVert {f} \right\rVert}_p ~{\left\lVert {(f+g)^{p-1})} \right\rVert}_q + {\left\lVert {g} \right\rVert}_p ~{\left\lVert {(f+g)^{p-1})} \right\rVert}_q \\
    &= \left( {\left\lVert {f} \right\rVert}_p + {\left\lVert {g} \right\rVert}_p \right) {\left\lVert { (f+g)^{p-1})} \right\rVert}_q \\
    &= \left( {\left\lVert {f} \right\rVert}_p + {\left\lVert {g} \right\rVert}_p \right) \left( \int {\left\lvert {f+g} \right\rvert}^{(p-1)q} \right)^{\frac 1 q} \\
    &= \left( {\left\lVert {f} \right\rVert}_p + {\left\lVert {g} \right\rVert}_p \right) \left( \int {\left\lvert {f+g} \right\rvert}^{p} \right)^{1 - \frac 1 p} \\
    &= \left( {\left\lVert {f} \right\rVert}_p + {\left\lVert {g} \right\rVert}_p \right) \frac{\int {\left\lvert {f+g} \right\rvert}^{p} }{\left( \int {\left\lvert {f+g} \right\rvert}^{p} \right)^{\frac 1 p}} \\
    &= \left( {\left\lVert {f} \right\rVert}_p + {\left\lVert {g} \right\rVert}_p \right)  \frac{{\left\lVert {f+g} \right\rVert}_p^p}{{\left\lVert {f+g} \right\rVert}_p}
    .\]

-   Cancelling common terms yields
    \[  
    1 &\leq \left( {\left\lVert {f} \right\rVert}_p + {\left\lVert {g} \right\rVert}_p \right) \frac{1}{{\left\lVert {f+g} \right\rVert}_p} \\
    &\implies 
    {\left\lVert {f+g} \right\rVert}_p
    \leq {\left\lVert {f} \right\rVert}_p + {\left\lVert {g} \right\rVert}_p 
    .\]
:::

::: {.proposition title="Young's Inequality"}
\[
\frac 1 p + \frac 1 q = \frac 1 r + 1 \implies
\|f \ast g\|_{r} \leq\|f\|_{p}\|g\|_{q}
\]
:::

::: {.remark title="some useful special cases"}
\[  
{\left\lVert {f\ast g} \right\rVert}_1      & \leq {\left\lVert {f} \right\rVert}_1 {\left\lVert {g} \right\rVert}_1 \\
\|f * g\|_{p}         & \leq {\left\lVert {f} \right\rVert}_1 {\left\lVert {g} \right\rVert}p, \\
{\left\lVert {f\ast g} \right\rVert}_\infty & \leq {\left\lVert {f} \right\rVert}_2 {\left\lVert {g} \right\rVert}_2 \\
{\left\lVert {f\ast g} \right\rVert}_\infty & \leq {\left\lVert {f} \right\rVert}_p {\left\lVert {g} \right\rVert}_q
.\]
:::

::: {.proposition title="Bessel's Inequality"}
For \( x\in H \) a Hilbert space and \( \left\{{e_k}\right\} \) an orthonormal sequence,
\[  
\sum_{k=1}^{\infty}\| {\left\langle {x},~{e_{k} } \right\rangle} \|^{2} \leq \|x\|^{2}
.\]

> Note that this does not need to be a basis.
:::

::: {.proposition title="Parseval's Identity"}
Equality in Bessel's inequality, attained when \( \left\{{e_k}\right\} \) is a *basis*, i.e. it is complete, i.e. the span of its closure is all of \( H \).
:::

# Less Explicitly Used Inequalities

::: {.proposition title="AM-GM Inequality"}
\[
\sqrt{ab} \leq \frac{a+b}{2}
.\]
:::

::: {.proposition title="Jensen's Inequality"}
\[
f(tx + (1-t)y) \leq tf(x) + (1-t)f(y)
.\]
:::

::: {.proposition title="Young's Product Inequality"}
\[
AB \leq {A^p \over p} + {B^q \over q}
.\]
:::

::: {.proposition title="?"}
\[
(a+b)^p \leq 2^{p-1} (a^p + b^p)
.\]
:::

::: {.proposition title="Bernoulli's Inequality"}
\[
(1 + x)^n \geq 1 +nx \quad x\geq -1, \text{ or } n\in 2{\mathbb{Z}}\text{ and } \forall x
.\]
:::

::: {.proposition title="Exponential Inequality"}
\[  
\forall t\in {\mathbb{R}},\quad 1 + t \leq  e^t
.\]
:::

::: {.proof}
```{=tex}
\envlist
```
-   It's an equality when \( t=0 \).
-   \( {\frac{\partial }{\partial t}\,} 1+ t < {\frac{\partial t}{\partial e}\,}^t \iff t<0 \)
:::

::: {.proposition title="Young's Convolution Inequality"}
\[
{1\over r} \coloneqq{1\over p} + {1\over q} - 1 \implies {\left\lVert {f \ast g} \right\rVert}_{r} \leq {\left\lVert {f} \right\rVert}_{p} {\left\lVert {g} \right\rVert}{q}
.\]
:::

[^1]: Mnemonic: "F" stands for *ferme*, which is "closed" in French, and \( \sigma \) corresponds to a "sum", i.e. a union.

[^2]: Slogan: to negate, find a bad \( x \) depending on \( n_0 \) that are larger than some \( \varepsilon \).

[^3]: Slogan: a uniform limit of continuous functions is continuous.

[^4]: Note that this is only pointwise convergence of \( f \), whereas the full \( M{\hbox{-}} \)test gives uniform convergence.

[^5]: It suffices to show \( {\left\lvert {f_n(x)} \right\rvert} \leq M_n \) for some \( M_n \) not depending on \( x \).

[^6]: So this implicitly holds if \( f \) is the pointwise limit of \( f_n \).

[^7]: See Abbott theorem 6.4.3, pp 168.

[^8]: This holds for outer measure **iff** \( \mathrm{dist}(A, B) > 0 \).
