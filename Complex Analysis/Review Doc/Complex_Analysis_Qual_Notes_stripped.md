# Useful Techniques

**Showing a function is constant:**

-   Write \( f = u + iv \) and use Cauchy-Riemann to show \( u_x, u_y = 0 \), etc.
-   Show that \( f \) is entire and bounded.

**Showing a function is zero**: Show \( f \) is entire, bounded, and \( \lim_{z\to\infty} f(z) = 0 \).

Things to know well:

-   Estimates for derivatives, mean value theorem

-   ```{=tex}
    \hyperref[CauchyTheorem]{Cauchy's Theorem}
    ```

-   ```{=tex}
    \hyperref[CauchyIntegral]{Cauchy's Integral Formula}
    ```

-   ```{=tex}
    \hyperref[CauchyInequality]{Cauchy's Inequality}
    ```

-   ```{=tex}
    \hyperref[Morera]{Morera's Theorem}
    ```

-   ```{=tex}
    \hyperref[SchwarzReflection]{The Schwarz Reflection Principle}
    ```

-   ```{=tex}
    \hyperref[MaximumModulus]{Maximum Modulus Principle}
    ```

-   ```{=tex}
    \hyperref[SchwarzLemma]{The Schwarz Lemma}
    ```

-   ```{=tex}
    \hyperref[Liouville]{Liouville's Theorem}
    ```

-   ```{=tex}
    \hyperref[Casorati]{Casorati-Weierstrass Theorem}
    ```

-   ```{=tex}
    \hyperref[Rouche]{Rouché's Theorem}
    ```

-   Properties of linear fractional transformations

-   Automorphisms of \( {\mathbb{D}}, {\mathbb{C}}, {\mathbb{CP}}^1 \).

**Computing Arguments:** \( \operatorname{Arg}(z/w) = \operatorname{Arg}(z) - \operatorname{Arg}(w) \).

# Definitions

::: {.definition title="Analytic"}
A function \( f:\Omega \to {\mathbb{C}} \) is *analytic* at \( z_0\in \Omega \) iff there exists a power series \( g(z) = \sum a_n (z-z_0)^n \) with radius of convergence \( R>0 \) and a neighborhood \( U\ni z_0 \) such that \( f(z) = g(z) \) on \( U \).
:::

::: {.definition title="Holomorphic"}
A function \( f:{\mathbb{C}}\to {\mathbb{C}} \) is *holomorphic* at \( z_0 \) if the following limit converges:
\[  
\lim_{h\to 0} {1\over h} \qty{f(z_0 + h) - f(z_0)} \coloneqq f'(z_0)
.\]
:::

Examples:

-   \( f(z) = {1\over z} \) is holomorphic on \( {\mathbb{C}}\setminus\left\{{0}\right\} \).
-   \( f(z) = \mkern 1.5mu\overline{\mkern-1.5muz\mkern-1.5mu}\mkern 1.5mu \) is *not* holomorphic, since \( \mkern 1.5mu\overline{\mkern-1.5muh\mkern-1.5mu}\mkern 1.5mu \over h \) does not converge (but is real differentiable).

::: {.definition title="Entire"}
A function that is holomorphic on \( {\mathbb{C}} \) is said to be *entire*.
:::

::: {.definition title="Meromorphic"}
A function \( f:\Omega\to{\mathbb{C}} \) is *meromorphic* iff there exists a sequence \( \left\{{z_n}\right\} \) such that

-   \( \left\{{z_n}\right\} \) has no limit points in \( \Omega \).
-   \( f \) is holomorphic in \( \Omega\setminus\left\{{z_n}\right\} \).
-   \( f \) has poles at the points \( \left\{{z_n}\right\} \).

If \( f \) is either holomorphic or has a pole at \( z=\infty \) is said to be meromorphic on \( {\mathbb{CP}}^1 \).
:::

::: {.definition title="Harmonic"}
A real function of two variables \( u(x, y) \) is *harmonic* iff its Laplacian vanishes:
\[  
\Delta u \coloneqq\qty{{\frac{\partial ^2}{\partial x^2}\,} + {\frac{\partial ^2}{\partial y^2}\,}}u = 0
.\]
:::

::: {.definition title="Cauchy-Riemann Equations"}
\[
u_x = v_y \quad\text{and}\quad u_y = -v_x \\
\frac{\partial u}{\partial r}=\frac{1}{r} \frac{\partial v}{\partial \theta} \quad \text { and } \quad \frac{\partial v}{\partial r}=-\frac{1}{r} \frac{\partial u}{\partial \theta} \\
.\]
:::

::: {.definition title="Principal Part and Residue"}
In a Laurent series \( f(z) \coloneqq\sum_{n\in {\mathbb{Z}}} c_n (z-z_0)^n \), the *principal part of \( f \) at \( z_0 \)* consists of terms with negative degree:
\[  
P_f(z) \coloneqq\sum_{n=1}^\infty c_{-n}(z-z_0)^{-n}
.\]

The *residue* of \( f \) at \( z_0 \) is the coefficient \( c_{-1} \).
:::

::: {.definition title="Removable Singularities"}
If \( z_0 \) is a singularity of \( f \) and there exists a \( g \) such that \( f(z) = g(z) \) for all \( z \) in some deleted neighborhood \( U\setminus\left\{{z_0}\right\} \), then \( z_0 \) is a *removable singularity* of \( f \).
:::

::: {.definition title="Pole Terminology"}
A *pole* \( z_0 \) of a meromorphic function \( f(z) \) is a zero of \( g(z) \coloneqq{1\over f(z)} \). If there exists an \( n \) such that
\[  
\lim_{z\to z_0}\qty{z-z_0}^nf(z)
\]
is holomorphic and nonzero in a neighborhood of \( z_0 \), then the minimal such \( n \) is the *order* of the pole. A pole of order 1 is said to be a *simple pole*.

The pole \( z_0 \) is *isolated* iff there exists a neighborhood of \( z_0 \) containing no other poles of \( f \).
:::

::: {.definition title="Essential Singularity"}
A singularity \( z_0 \) is *essential* iff it is neither removable nor a pole.

Equivalently, a Laurent series expansion about \( z_0 \) has a principal part with infinitely many terms.
:::

# Theorems

## Basics

::: {.theorem title="Green's Theorem"}
If \( \Omega \subseteq {\mathbb{C}} \) is bounded with \( {{\partial}}\Omega \) piecewise smooth and \( f, g\in C^1(\mkern 1.5mu\overline{\mkern-1.5mu\Omega\mkern-1.5mu}\mkern 1.5mu) \), then
\[\int_{{{\partial}}\Omega} f\, dx + g\, dy = \iint_{\Omega} \qty{ {\frac{\partial g}{\partial x}\,} - {\frac{\partial f}{\partial y}\,} } \, dA.\]
:::

::: {.theorem title="Summation by Parts"}
Define the forward difference operator \( \Delta f_k = f_{k+1} - f_k \), then
\[
\sum_{k=m}^n f_k \Delta g_k  + \sum_{k=m}^{n-1} g_{k+1}\Delta f_k = f_n g_{n+1} - f_m g_m
\]

> Note: compare to \( \int_a^b f \, dg + \int_a^b g\, df = f(b) g(b) - f(a) g(a) \).
:::

## Holomorphic and Entire Functions

### Key Theorems

::: {.theorem title="Cauchy's Theorem \\label{CauchyTheorem}"}
If \( f \) is holomorphic on \( \Omega \), then
\[  
\int_{{{\partial}}\Omega} f(z) \, dz = 0
.\]

> Slogan: closed path integrals of holomorphic functions vanish.
:::

::: {.theorem title="Morera's Theorem \\label{Morera}  "}
If \( f \) is continuous on a domain \( \Omega \) and \( \int_T f = 0 \) for every triangle \( T\subset \Omega \), then \( f \) is holomorphic.

> Slogan: if every integral along a triangle vanishes, implies holomorphic.
:::

::: {.theorem title="Liouville's Theorem \\label{Liouville}  "}
If \( f \) is entire and bounded, \( f \) is constant.
:::

::: {.theorem title="Cauchy Integral Formula \\label{CauchyIntegral}"}
Suppose \( f \) is holomorphic on \( \Omega \), then
\[
f(z) = {1 \over 2\pi i} \oint_{{{\partial}}\Omega} {f(\xi) \over \xi-z}\,d\xi
\]
and
\[
{\frac{\partial ^nf }{\partial z^n}\,}(z) = {n! \over 2\pi i} \int_{{{\partial}}\Omega} {f(\xi) \over (\xi - z)^{n+1}} \,d\xi
.\]
:::

### Others

::: {.theorem title="Holomorphic functions have harmonic components"}
If \( f(z) = u(x, y) + iv(x, y) \), then \( u, v \) are harmonic.
:::

::: {.theorem title="Holomorphic functions are continuous."}
\( f \) is holomorphic at \( z_0 \) iff there exists an \( a\in {\mathbb{C}} \) such that
\[  
f(z_0 + h) - f(z_0) - ah = h \psi(h), \quad \psi(h) \overset{h\to 0}\to 0
.\]
In this case, \( a = f'(z_0) \).
:::

::: {.proposition title="Cauchy-Riemann implies holomorphic"}
If \( f = u+iv \) with \( u, v\in C^1({\mathbb{R}}) \) satisfying the Cauchy-Riemann equations on \( \Omega \), then \( f \) is holomorphic on \( \Omega \) and \( f'(z) = {\frac{\partial f}{\partial z}\,} = {1 \over 2} \qty{{\frac{\partial }{\partial x}\,} + {1\over i} {\frac{\partial }{\partial y}\,}}f \).
:::

::: {.proposition title="Polar Cauchy-Riemann equations"}
\[  
\frac{\partial u}{\partial r}=\frac{1}{r} \frac{\partial v}{\partial \theta} \quad \text { and } \quad \frac{1}{r} \frac{\partial u}{\partial \theta}=-\frac{\partial v}{\partial r}
.\]
:::

::: {.proof}
```{=tex}
\hfill
```
::: {.concept}
```{=tex}
\hfill
```
-   See [walkthrough here](https://users.math.msu.edu/users/shapiro/Teaching/classes/425/crpolar.pdf).
-   See problem set 1.
:::

-   Take derivative along two paths, along a ray with constant angle \( \theta_0 \) and along a circular arc of constant radius \( r_0 \).
-   Then equate real and imaginary parts.
:::

::: {.theorem title="Open Mapping"}
Any holomorphic non-constant map is an open map.
:::

## Series and Analytic Functions

::: {.proposition title="Power Series are Smooth"}
Any power series is smooth and its derivatives can be obtained using term-by-term differentiation.
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

::: {.proposition title="Checking radius of convergence"}
For a power series \( f(z) = \sum a_n z^n \), define \( R \) by
\[  
{1\over R}\coloneqq\limsup {\left\lvert {a_n} \right\rvert}^{1\over n}
.\]

Then \( f \) converges absolutely on \( {\left\lvert {z} \right\rvert} < R \) and diverges on \( {\left\lvert {z} \right\rvert} > R \).
:::

::: {.theorem title="Maximum Modulus \\label{MaximumModulus}  "}
If \( f \) is holomorphic and nonconstant on an open region \( \Omega \), then \( {\left\lvert {f} \right\rvert} \) can not attain a maximum on \( \Omega \).

If \( \Omega \) is bounded and \( f \) is continuous on \( \mkern 1.5mu\overline{\mkern-1.5mu\Omega\mkern-1.5mu}\mkern 1.5mu \), then \( \max_{\mkern 1.5mu\overline{\mkern-1.5mu\Omega\mkern-1.5mu}\mkern 1.5mu} {\left\lvert {f} \right\rvert} \) occurs on \( {{\partial}}\Omega \).

Conversely, if \( f \) attains a local maximum at \( z_0 \in \Omega \), then \( f \) is constant on \( \Omega \).
:::

## Others

::: {.theorem title="Casorati-Weierstrass \\label{Casorati}  "}
If \( f \) is holomorphic on \( \Omega\setminus\left\{{z_0}\right\} \) where \( z_0 \) is an essential singularity, then for every \( V\subset \Omega\setminus\left\{{z_0}\right\} \), \( f(V) \) is dense in \( {\mathbb{C}} \).

> The image of a disc punctured at an essential singularity is dense in \( {\mathbb{C}} \).
:::

::: {.theorem title="Little Picard"}
Todo
:::

```{=tex}
\todo{???}
```
::: {.theorem title="Continuation Principle / Identity Theorem"}
If \( f \) is holomorphic on a bounded connected domain \( \Omega \) and there exists a sequence \( \left\{{z_i}\right\} \) with a limit point in \( \Omega \) such that \( f(z_i) = 0 \), then \( f\equiv 0 \) on \( \Omega \).

> Two functions agreeing on a set with a limit point are equal on a domain.
:::

::: {.corollary}
The ring of holomorphic functions on a domain in \( {\mathbb{C}} \) has no zero divisors.
:::

```{=tex}
\todo[inline]{Find the proof!}
```
::: {.proof}
???
:::

::: {.proposition title="Injectivity Relates to Derivatives"}
If \( z_0 \) is a zero of \( f' \) of order \( n \), then \( f \) is \( (n+1) \)-to-one in a neighborhood of \( z_0 \).
:::

::: {.proof}
?
:::

::: {.proposition title="Bounded Complex Analytic Functions form a Banach Space"}
For \( \Omega\subseteq{\mathbb{C}} \), show that \( A({\mathbb{C}})\coloneqq\left\{{f: \Omega \to {\mathbb{C}}{~\mathrel{\Big|}~}f\text{ is bounded}}\right\} \) is a Banach space.
:::

::: {.proof}
?

> Apply Morera's Theorem and Cauchy's Theorem
:::

# Residues

::: {.theorem title="Cauchy's Inequality\\label{CauchyInequality}"}
For \( z_o \in D_R(z_0) \subset \Omega \), we have
\[
{\left\lvert { f^{(n)} (z_0) } \right\rvert} 
\leq \frac{n !}{2 \pi} \int_{0}^{2 \pi} \frac{ {\left\lVert {f} \right\rVert}_{\infty} } {R^{n+1}} R \,d\theta
= \frac{n !{\left\lVert {f} \right\rVert}_{\infty}}{R^n} 
,\]
where \( {\left\lVert {f} \right\rVert}_{\infty}\coloneqq\sup_{z\in C_R} {\left\lvert {f(z)} \right\rvert} \).

> Slogan: the \( n \)th Taylor coefficient of an analytic function is at most \( \sup_{{\left\lvert {z} \right\rvert} = R} {\left\lvert {f} \right\rvert}/R^n \).
:::

::: {.proof}
```{=tex}
\hfill
```
-   Given \( z_0\in \Omega \), pick the largest disc \( D_R(z_0) \subset \Omega \) and let \( C_R = {{\partial}}D_R \).
-   Then apply the integral formula.
:::

::: {.theorem title="The Residue Theorem"}
If \( f \) is holomorphic on an open set \( \Omega \) containing a curve \( \gamma \) and its interior \( \gamma^\circ \), except for finitely many poles \( \left\{{z_k}\right\}_{k=1}^N \subset \gamma^\circ \). Then
\[  
\int_\gamma f(z) \,dz = 2\pi i \sum_{k=1}^N \operatorname{Res}_{z_k} f
.\]
:::

::: {.proposition title="For simple poles"}
If \( z_0 \) is a simple pole of \( f \), then
\[  
\operatorname{Res}_{z_0}f = \lim_{z\to z_0} (z-z_0) f(z)
.\]
:::

Example: Let \( f(z) = \frac{1}{1+z^2} \), then \( \operatorname{Res}(i, f) = \frac{1}{2i} \).

::: {.proposition title="For higher order poles"}
If \( f \) has a pole \( z_0 \) of order \( n \), then
\[  
\operatorname{Res}_{z=z_0} f = \lim_{z\to z_0} {1 \over (n-1)!} \qty{{\frac{\partial }{\partial z}\,}}^{n-1} (z-z_0)^n f(z)
.\]
:::

# Conformal Maps

Notation:

-   \( S \coloneqq\left\{{x + iy {~\mathrel{\Big|}~}x\in {\mathbb{R}},\, 0<y<\pi}\right\} \).
-   \( {\mathbb{D}} \) the disc
-   \( {\mathbb{H}} \) the upper half plane
-   \( X_{1\over 2} \): a "half" version of \( X \).

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

Conformal maps \( {\mathbb{D}}\to{\mathbb{D}} \) have the form `\begin{align*}
g(z) = \lambda {1-a \over 1 - \mkern 1.5mu\overline{\mkern-1.5mua\mkern-1.5mu}\mkern 1.5mu z}, \quad {\left\lvert {a} \right\rvert} < 1, \quad {\left\lvert {\lambda} \right\rvert} = 1
.\end{align*}`{=tex}

## Plane to Disc

`\begin{align*}
\phi: {\mathbb{H}}&\to {\mathbb{D}}\\
\phi(z) &= {z - i \over z + i} \qquad f^{-1}(z) = i\qty{1 + w \over 1 - w}
.\end{align*}`{=tex}

## Sector to Disc

For \( S_\alpha \coloneqq\left\{{z\in{\mathbb{C}}{~\mathrel{\Big|}~}0 < \arg(z) < \alpha }\right\} \) an open sector for \( \alpha \) some angle, first map the sector to the half-plane: `\begin{align*}
g: S_\alpha &\to {\mathbb{H}}\\
g(z) &= z^{\pi \over \alpha}
.\end{align*}`{=tex}

Then compose with a map \( {\mathbb{H}}\to{\mathbb{D}} \): `\begin{align*}
f: S_\alpha &\to {\mathbb{D}}\\
f(z) &= (\phi \circ g)(z) = {z^{\pi\over \alpha} - i \over z^{\pi\over\alpha} + i}
.\end{align*}`{=tex}

![](figures/image_2020-07-22-13-22-46.png)

## Strip to Disc

-   Map to horizontal strip by rotation \( z\mapsto \lambda z \).
-   Map horizontal strip to sector by \( z \mapsto e^z \)
-   Map sector to \( {\mathbb{H}} \) by \( z\mapsto z^{\pi\over\alpha} \).
-   Map \( {\mathbb{H}}\to{\mathbb{D}} \).

::: {.theorem title="Riemann Mapping"}
If \( \Omega \) is simply connected, nonempty, and not \( {\mathbb{C}} \), then for every \( z_0\in \Omega \) there exists a unique conformal map \( F:\Omega \to {\mathbb{D}} \) such that \( F(z_0) = 0 \) and \( F'(z_0) > 0 \).

Thus any two such sets \( \Omega_1, \Omega_2 \) are conformally equivalent.
:::

# Schwarz Reflection

::: {.theorem title="Schwarz Reflection \\label{SchwarzReflection}  "}
If \( f \) is continuous and holomorphic on \( {\mathbb{H}}^+ \) and real-valued on \( {\mathbb{R}} \), then the extension defined by \( F(z) = \mkern 1.5mu\overline{\mkern-1.5muf(\mkern 1.5mu\overline{\mkern-1.5muz\mkern-1.5mu}\mkern 1.5mu)\mkern-1.5mu}\mkern 1.5mu \) for \( z\in {\mathbb{H}}^- \) is a well-defined holomorphic function on \( {\mathbb{C}} \).
:::

::: {.remark}
\( {\mathbb{H}}^+, {\mathbb{H}}^- \) can be replaced with any region symmetric about a line segment \( L\subseteq {\mathbb{R}} \).
:::

# Zeros and Poles

## Singularities

::: {.theorem title="Riemann's Removable Singularity Theorem"}
If \( f \) is holomorphic on \( \Omega \) except possibly at \( z_0 \) and \( f \) is bounded on \( \Omega\setminus\left\{{z_0}\right\} \), then \( z_0 \) is a removable singularity.
:::

## Counting Zeros

::: {.theorem title="Argument Principle"}
For \( f \) meromorphic in \( \gamma^\circ \), if \( f \) has no poles and is nonvanishing on \( \gamma \) then
\[  
\Delta_\gamma \arg f(z) = \int_\gamma {f'(z) \over f(z)} \,dz = 2\pi (Z_f - P_f)
,\]
where \( Z_f \) and \( P_f \) are the number of zeros and poles respectively enclosed by \( \gamma \), counted with multiplicity.
:::

::: {.theorem title="Rouché's Theorem \\label{Rouche}"}
If \( f, g \) are analytic on a domain \( \Omega \) with finitely many zeros in \( \Omega \) and \( \gamma \subset \Omega \) is a closed curve surrounding each point exactly once, where \( {\left\lvert {g} \right\rvert} < {\left\lvert {f} \right\rvert} \) on \( \gamma \), then \( f \) and \( f+g \) have the same number of zeros.

Alternatively:

Suppose \( f = g + h \) with \( g \neq 0, \infty \) on \( \gamma \) with \( {\left\lvert {g} \right\rvert} > {\left\lvert {h} \right\rvert} \) on \( \gamma \). Then
\[\Delta_\gamma \arg(f) = \Delta_\gamma \arg(h)\quad\text{ and } Z_f - P_f = Z_g - P_g.\]
:::

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

# Linear Fractional Transformations

::: {.definition title="Linear Fractional Transformation"}
A map of the following form is a *linear fractional transformation*:
\[  
T(z) = {az + b \over cz + d}
,\]
where the denominator is assumed to not be a multiple of the numerator.

These have inverses given by
\[  
T^{-1}(w) = {dw-b \over -cw + a}
.\]
:::

::: {.theorem title="Cayley Transform"}
The fractional linear transformation given by \( F(z) = {i - z \over i + z} \) maps \( {\mathbb{D}}\to {\mathbb{H}} \) with inverse \( G(w) = i {1-w \over 1 + w} \).
:::

::: {.theorem title="Schwarz Lemma \\label{SchwarzLemma}  "}
If \( f: {\mathbb{D}}\to {\mathbb{D}} \) is holomorphic with \( f(0) = 0 \), then

1.  \( {\left\lvert {f(z)} \right\rvert} \leq {\left\lvert {z} \right\rvert} \) for all \( z\in {\mathbb{D}} \)
2.  \( {\left\lvert {f'(0)} \right\rvert} \leq 1 \).

Moreover, if \( {\left\lvert {f(z_0)} \right\rvert} = {\left\lvert {z_0} \right\rvert} \) for any \( z_0\in {\mathbb{D}} \) or \( {\left\lvert {f'(0)} \right\rvert} = 1 \), then \( f \) is a rotation
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

-   Suppose \( p \) is nonconstant and has no roots, then \( {1\over p} \) is entire
-   Write \( g(z) \coloneqq\frac{p(z)}{z^{n}}=a_{n}\left(\frac{a_{n-1}}{z}+\dots+\frac{a_{0}}{z^{n}}\right) \)
-   Outside a disc:
    -   Note \( \lim_{z\to \infty} = 0 \) for the parenthesized terms, so there exists an \( R \) large enough such that \( {\left\lvert {g(z)} \right\rvert} \geq {1\over 2} {\left\lvert {a_n} \right\rvert} \)
    -   Then \( {\left\lvert {p(z)} \right\rvert} \geq {R^n\over 2} {\left\lvert {a_n} \right\rvert} \) implies \( {1\over p} \) is bounded in \( {\left\lvert {z} \right\rvert} > R \)
-   Inside a disc:
    -   \( p \) is continuous with no roots so \( p \) is bounded below on \( {\left\lvert {z} \right\rvert} < R \).
    -   \( p \) is continuous on a compact set and thus achieves a min \( A \)
    -   Set \( B = \min(A, {R^n \over 2} {\left\lvert {a_n} \right\rvert}) \), then \( p \geq B \) on \( {\left\lvert {z} \right\rvert} < R \).
-   Thus \( p \) is bounded below everywhere and thus \( {1\over p} \) is bounded above everywhere, thus bounded.
-   Thus \( {1\over p} \) is constant, forcing \( p \) to be constant.

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

\[
dz &= dx + i~dy \\
d\mkern 1.5mu\overline{\mkern-1.5muz\mkern-1.5mu}\mkern 1.5mu &= dx - i~dy \\
f_z &= f_x = i^{-1}f_y \\
\int_{0}^{2 \pi} e^{i \ell x} d x
&=\left\{\begin{array}{ll}{2 \pi} & {(\ell=0)} \\ {0} & {(\ell \neq 0)}\end{array}\right.
.\]

## Misc Prerequisites

**Standard forms of conic sections:**

-   Circle: \( x^2 + y^2 = r^2 \)
-   Ellipse: \( \qty{\frac x a}^2 + \qty{\frac y b}^2 = 1 \)
-   Hyperbola: \( \qty{\frac x a}^2 - \qty{\frac y b}^2 = 1 \)
    -   Rectangular Hyperbola: \( xy = \frac{c^2}{2} \).
-   Parabola: \( -4ax + y^2 = 0 \).

> Mnemonic: Write \( f(x, y) = Ax^2 + Bxy + Cy^2 + \cdots \), then consider the discriminant \( \Delta = B^2 - 4AC \):
>
> -   \( \Delta < 0 \iff \) ellipse
>     -   \( \Delta < 0 \) and \( A=C, B=0 \iff \) circle
> -   \( \Delta = 0 \iff \) parabola
> -   \( \Delta > 0 \iff \) hyperbola

**Completing the square:**

\[
x^2 - bx = (x - s)^2 - s^2 \quad\text{where} s = \frac{b}{2} \\
x^2 + bx = (x + s)^2 - s^2 \quad\text{where} s = \frac{b}{2}
.\]

**Useful Properties**

-   \( \Re(z) = \frac 1 2 (z + \mkern 1.5mu\overline{\mkern-1.5muz\mkern-1.5mu}\mkern 1.5mu) \) and \( \Im(z) = \frac{1}{2i}(z - \mkern 1.5mu\overline{\mkern-1.5muz\mkern-1.5mu}\mkern 1.5mu) \).
-   \( z\mkern 1.5mu\overline{\mkern-1.5muz\mkern-1.5mu}\mkern 1.5mu = {\left\lvert {z} \right\rvert}^2 \)
-   Exponential forms of cosine and sine:
    -   \( \cos(\theta) = \frac 1 2 \qty{e^{i\theta} + e^{-i\theta}} \)
    -   \( \sin(\theta) = \frac{1}{2i}\qty{e^{i\theta} - e^{-i\theta}} \).

**Useful Series**

\[
\sum_{k=1}^{n} k &=\frac{n(n+1)}{2} \\
\sum_{k=1}^{n} k^{2} &=\frac{n(n+1)(2 n+1)}{6} \\
\sum_{k=1}^{n} k^{3} &=\frac{n^{2}(n+1)^{2}}{4}  \\
\log(z) &= \sum_{j=0}^\infty (-1)^j \frac{\qty{z-a}^j}{j}
{\frac{\partial }{\partial z}\,} \sum_{j=0}^\infty a_j z^j &= \sum_{j=0}^\infty a_{j+1}z^j
\]

The sum of the interior angles of an \( n{\hbox{-}} \)gon is \( (n-2)\pi \), where each angle is \( \frac{n-2}{n}\pi \).

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