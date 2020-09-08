
---
title: "Complex Analysis Qualifying Exam Notes"
---

# Useful Techniques

**Showing a function is constant:**

- Write $f = u + iv$ and use Cauchy-Riemann to show $u_x, u_y = 0$, etc.
- Show that $f$ is entire and bounded.

**Showing a function is zero**:
Show $f$ is entire, bounded, and $\lim_{z\to\infty} f(z) = 0$.

Things to know well:

- Estimates for derivatives, mean value theorem
- \hyperref[CauchyTheorem]{Cauchy's Theorem}
- \hyperref[CauchyIntegral]{Cauchy's Integral Formula}
- \hyperref[CauchyInequality]{Cauchy's Inequality}
- \hyperref[Morera]{Morera's Theorem}
- \hyperref[SchwarzReflection]{The Schwarz Reflection Principle}
- \hyperref[MaximumModulus]{Maximum Modulus Principle}
- \hyperref[SchwarzLemma]{The Schwarz Lemma}
- \hyperref[Liouville]{Liouville's Theorem}
- \hyperref[Casorati]{Casorati-Weierstrass Theorem}
- \hyperref[Rouche]{Rouché's Theorem}
- Properties of linear fractional transformations
- Automorphisms of $\DD, \CC, \CP^1$.


**Computing Arguments:**
$\Arg(z/w) = \Arg(z) - \Arg(w)$.



# Definitions

:::{.definition title="Analytic"}
A function $f:\Omega \to \CC$ is *analytic* at $z_0\in \Omega$ iff there exists a power series $g(z) = \sum a_n (z-z_0)^n$ with radius of convergence $R>0$ and a neighborhood $U\ni z_0$ such that $f(z) = g(z)$ on $U$.
:::

:::{.definition title="Holomorphic"}
A function $f:\CC\to \CC$ is *holomorphic* at $z_0$ if the following limit converges:
\[  
\lim_{h\to 0} {1\over h} \qty{f(z_0 + h) - f(z_0)} \definedas f'(z_0)
.\]
:::

Examples:

- $f(z) = {1\over z}$ is holomorphic on $\CC\smz$.
- $f(z) = \bar{z}$ is *not* holomorphic, since $\bar h \over h$ does not converge (but is real differentiable).


:::{.definition title="Entire"}
A function that is holomorphic on $\CC$ is said to be *entire*.
:::

:::{.definition title="Meromorphic"}
A function $f:\Omega\to\CC$ is *meromorphic* iff there exists a sequence $\theset{z_n}$ such that

- $\theset{z_n}$ has no limit points in $\Omega$.
- $f$ is holomorphic in $\Omega\setminus\theset{z_n}$.
- $f$ has poles at the points $\theset{z_n}$.

If $f$ is either holomorphic or has a pole at $z=\infty$ is said to be meromorphic on $\CP^1$.
:::

:::{.definition title="Harmonic"}
A real function of two variables $u(x, y)$ is *harmonic* iff its Laplacian vanishes:
\[  
\Delta u \definedas \qty{\dd{^2}{x^2} + \dd{^2}{y^2}}u = 0
.\]
:::

:::{.definition title="Cauchy-Riemann Equations"}
\[
u_x = v_y \quad\text{and}\quad u_y = -v_x \\
\frac{\partial u}{\partial r}=\frac{1}{r} \frac{\partial v}{\partial \theta} \quad \text { and } \quad \frac{\partial v}{\partial r}=-\frac{1}{r} \frac{\partial u}{\partial \theta} \\
.\]
:::

:::{.definition title="Principal Part and Residue"}
In a Laurent series $f(z) \definedas \sum_{n\in \ZZ} c_n (z-z_0)^n$, the *principal part of $f$ at $z_0$* consists of terms with negative degree:
\[  
P_f(z) \definedas \sum_{n=1}^\infty c_{-n}(z-z_0)^{-n}
.\]

The *residue* of $f$ at $z_0$ is the coefficient $c_{-1}$.
:::

:::{.definition title="Removable Singularities"}
If $z_0$ is a singularity of $f$ and there exists a $g$ such that $f(z) = g(z)$ for all $z$ in some deleted neighborhood $U\setminus\theset{z_0}$, then $z_0$ is a *removable singularity* of $f$.
:::


:::{.definition title="Pole Terminology"}
A *pole* $z_0$ of a meromorphic function $f(z)$ is a zero of $g(z) \definedas {1\over f(z)}$.
If there exists an $n$ such that
\[  
\lim_{z\to z_0}\qty{z-z_0}^nf(z)
\]
is holomorphic and nonzero in a neighborhood of $z_0$, then the minimal such $n$ is the *order* of the pole.
A pole of order 1 is said to be a *simple pole*.

The pole $z_0$ is *isolated* iff there exists a neighborhood of $z_0$ containing no other poles of $f$.
:::

:::{.definition title="Essential Singularity"}
A singularity $z_0$ is *essential* iff it is neither removable nor a pole.

Equivalently, a Laurent series expansion about $z_0$ has a principal part with infinitely many terms.
:::






# Theorems

## Basics

:::{.theorem title="Green's Theorem"}
If $\Omega \subseteq \CC$ is bounded with $\bd \Omega$ piecewise smooth and $f, g\in C^1(\bar \Omega)$, then $$\int_{\bd \Omega} f\, dx + g\, dy = \iint_{\Omega} \qty{ \dd{g}{x} - \dd{f}{y} } \, dA.$$
:::

:::{.theorem title="Summation by Parts"}
Define the forward difference operator $\Delta f_k = f_{k+1} - f_k$, then
\[
\sum_{k=m}^n f_k \Delta g_k  + \sum_{k=m}^{n-1} g_{k+1}\Delta f_k = f_n g_{n+1} - f_m g_m
\]

> Note: compare to $\int_a^b f \, dg  + \int_a^b g\, df = f(b) g(b) - f(a) g(a)$.

:::

## Holomorphic and Entire Functions

### Key Theorems

:::{.theorem title="Cauchy's Theorem \label{CauchyTheorem}"}
If $f$ is holomorphic on $\Omega$, then 
\[  
\int_{\bd \Omega} f(z) \, dz = 0
.\]

> Slogan: closed path integrals of holomorphic functions vanish.

:::

:::{.theorem title="Morera's Theorem \label{Morera}  "}
If $f$ is continuous on a domain $\Omega$ and $\int_T f = 0$ for every triangle $T\subset \Omega$, then $f$ is holomorphic.

> Slogan: if every integral along a triangle vanishes, implies holomorphic.

:::

:::{.theorem title="Liouville's Theorem \label{Liouville}  "}
If $f$ is entire and bounded, $f$ is constant.
:::

:::{.theorem title="Cauchy Integral Formula \label{CauchyIntegral}"}
Suppose $f$ is holomorphic on $\Omega$, then 
\[
f(z) = {1 \over 2\pi i} \oint_{\bd \Omega} {f(\xi) \over \xi-z}\,d\xi
\]
and
\[
\dd{^nf }{z^n}(z) = {n! \over 2\pi i} \int_{\bd \Omega} {f(\xi) \over (\xi - z)^{n+1}} \,d\xi
.\]
:::

### Others

:::{.theorem title="Holomorphic functions have harmonic components"}
If $f(z) = u(x, y) + iv(x, y)$, then $u, v$ are harmonic.
:::

:::{.theorem title="Holomorphic functions are continuous."}
$f$ is holomorphic at $z_0$ iff there exists an $a\in \CC$ such that
\[  
f(z_0 + h) - f(z_0) - ah = h \psi(h), \quad \psi(h) \converges{h\to 0}\to 0
.\]
In this case, $a = f'(z_0)$.
:::

:::{.proposition title="Cauchy-Riemann implies holomorphic"}
If $f = u+iv$ with $u, v\in C^1(\RR)$ satisfying the Cauchy-Riemann equations on $\Omega$, then $f$ is holomorphic on $\Omega$ and $f'(z) = \dd{f}{z} = {1 \over 2} \qty{\dd{}{x} + {1\over i} \dd{}{y}}f$.
:::

:::{.proposition title="Polar Cauchy-Riemann equations"}
\[  
\frac{\partial u}{\partial r}=\frac{1}{r} \frac{\partial v}{\partial \theta} \quad \text { and } \quad \frac{1}{r} \frac{\partial u}{\partial \theta}=-\frac{\partial v}{\partial r}
.\]
:::
:::{.proof}
\hfill
:::{.concept}
\hfill
- See [walkthrough here](https://users.math.msu.edu/users/shapiro/Teaching/classes/425/crpolar.pdf).
- See problem set 1.
:::
- Take derivative along two paths, along a ray with constant angle $\theta_0$ and along a circular arc of constant radius $r_0$.
- Then equate real and imaginary parts.
:::

:::{.theorem title="Open Mapping"}
Any holomorphic non-constant map is an open map.
:::

## Series and Analytic Functions

:::{.proposition title="Power Series are Smooth"}
Any power series is smooth and its derivatives can be obtained using term-by-term differentiation.
:::

:::{.proposition title="Uniform Convergence of Series"}
A series of functions $\sum_{n=1}^\infty f_n(x)$ converges uniformly iff 
\[  
\lim_{n\to \infty} \norm{ \sum_{k\geq n} f_k }_\infty = 0
.\]
:::

:::{.theorem title="Weierstrass $M\dash$Test"}
If $\theset{f_n}$ with $f_n: \Omega \to \CC$ and there exists a sequence $\theset{M_n}$ with $\norm{f_n}_\infty \leq M_n$ and $\sum_{n\in \NN} M_n < \infty$, then $f(x) \definedas \sum_{n\in \NN} f_n(x)$ converges absolutely and uniformly on $\Omega$.

Moreover, if the $f_n$ are continuous, by the uniform limit theorem, $f$ is again continuous.
:::

:::{.proposition title="Exponential is uniformly convergent in discs"}
$f(z) = e^z$ is uniformly convergent in any disc in $\CC$.
:::
:::{.proof}
Apply the estimate
\[  
\abs{e^z} \leq \sum {\abs {z}^n \over n!} = e^{\abs{z}}
.\]
Now by the $M\dash$test, 
\[  
\abs{z} \leq R < \infty \implies \abs{\sum {z^n \over n!}} \leq e^R < \infty
.\]
:::

:::{.proposition title="Checking radius of convergence"}
For a power series $f(z) = \sum a_n z^n$, define $R$ by
\[  
{1\over R}\definedas \limsup \abs{a_n}^{1\over n}
.\]

Then $f$ converges absolutely on $\abs{z} < R$ and diverges on $\abs{z} > R$.
:::


:::{.theorem title="Maximum Modulus \label{MaximumModulus}  "}
If $f$ is holomorphic and nonconstant on an open region $\Omega$, then $\abs{f}$ can not attain a maximum on $\Omega$.

If $\Omega$ is bounded and $f$ is continuous on $\bar \Omega$, then $\max_{\bar \Omega} \abs{f}$ occurs on $\bd \Omega$.
  
Conversely, if $f$ attains a local maximum at $z_0 \in \Omega$, then $f$ is constant on $\Omega$.
:::

## Others

:::{.theorem title="Casorati-Weierstrass \label{Casorati}  "}
If $f$ is holomorphic on $\Omega\setminus\theset{z_0}$ where $z_0$ is an essential singularity, then for every $V\subset \Omega\setminus\theset{z_0}$, $f(V)$ is dense in $\CC$.

> The image of a disc punctured at an essential singularity is dense in $\CC$.

:::

:::{.theorem title="Little Picard"}
Todo
:::
\todo{???}

:::{.theorem title="Continuation Principle / Identity Theorem"}
If $f$ is holomorphic on a bounded connected domain $\Omega$ and there exists a sequence $\theset{z_i}$ with a limit point in $\Omega$ such that $f(z_i) = 0$, then $f\equiv 0$ on $\Omega$.

> Two functions agreeing on a set with a limit point are equal on a domain.

:::

:::{.corollary}
The ring of holomorphic functions on a domain in $\CC$ has no zero divisors.
:::

\todo[inline]{Find the proof!}
:::{.proof}
???
:::








# Residues

:::{.theorem title="Cauchy's Inequality\label{CauchyInequality}"}
For $z_o \in D_R(z_0) \subset \Omega$, we have
\[
\abs{ f^{(n)} (z_0) } 
\leq \frac{n !}{2 \pi} \int_{0}^{2 \pi} \frac{ \norm{f}_{\infty} } {R^{n+1}} R \,d\theta
= \frac{n !\norm{f}_{\infty}}{R^n} 
,\]
where $\norm{f}_{\infty}\definedas \sup_{z\in C_R} \abs{f(z)}$.

> Slogan: the $n$th Taylor coefficient of an analytic function is at most $\sup_{\abs z = R} \abs{f}/R^n$.

:::

:::{.proof}
\hfill
- Given $z_0\in \Omega$, pick the largest disc $D_R(z_0) \subset \Omega$ and let $C_R = \bd D_R$.
- Then apply the integral formula.
:::

:::{.theorem title="The Residue Theorem"}
If $f$ is holomorphic on an open set $\Omega$ containing a curve $\gamma$ and its interior $\gamma^\circ$, except for finitely many poles $\theset{z_k}_{k=1}^N \subset \gamma^\circ$.
Then
\[  
\int_\gamma f(z) \,dz = 2\pi i \sum_{k=1}^N \res_{z_k} f
.\]
:::


:::{.proposition title="For simple poles"}
If $z_0$ is a simple pole of $f$, then
\[  
\res_{z_0}f = \lim_{z\to z_0} (z-z_0) f(z)
.\]
:::

Example: 
Let $f(z) = \frac{1}{1+z^2}$, then $\Res(i, f) = \frac{1}{2i}$.

:::{.proposition title="For higher order poles"}
If $f$ has a pole $z_0$ of order $n$, then
\[  
\res_{z=z_0} f = \lim_{z\to z_0} {1 \over (n-1)!} \qty{\dd{}{z}}^{n-1} (z-z_0)^n f(z)
.\]
:::



# Conformal Maps

Notation: 

- $S \definedas \theset{x + iy \suchthat x\in \RR,\, 0<y<\pi}$.
- $\DD$ the disc
- $\HH$ the upper half plane
- $X_{1\over 2}$: a "half" version of $X$.

:::{.theorem title="Classification of Conformal Maps"}
There are 8 major types of conformal maps:

| Type/Domains | Formula | 
| ------------ | ------- |
| Translation/Dilation/Rotation | $z\mapsto e^{i\theta}(cz + h)$ |
| Sectors to sectors | $z\mapsto z^n$ |
| $\DD_{1\over 2} \to \HH_{1\over 2}$, the first quadrant | $z\mapsto {1+z \over 1-z}$ |
| $\HH\to S$ | $z\mapsto \log(z)$ | 
| $\DD_{1\over 2} \to S_{1\over 2}$ | $z\mapsto \log(z)$ |
| $S_{1\over 2} \to \DD_{1\over 2}$ | $z\mapsto e^{iz}$ |
| $\DD_{1\over 2} \to \HH$ |  $z\mapsto {1\over 2}\qty{z + {1\over z}}$ |
| $S_{1\over 2} \to \HH$ | $z\mapsto \sin(z)$ |

:::

Conformal maps $\DD\to\DD$ have the form
\begin{align*}
g(z) = \lambda {1-a \over 1 - \bar a z}, \quad \abs{a} < 1, \quad \abs{\lambda} = 1
.\end{align*}

## Plane to Disc

\begin{align*}
\phi: \HH &\to \DD \\
\phi(z) &= {z - i \over z + i} \qquad f\inv(z) = i\qty{1 + w \over 1 - w}
.\end{align*}

## Sector to Disc

For $S_\alpha \definedas \theset{z\in\CC \suchthat 0 < \arg(z) < \alpha }$ an open sector for $\alpha$ some angle, first map the sector to the half-plane:
\begin{align*}
g: S_\alpha &\to \HH \\
g(z) &= z^{\pi \over \alpha}
.\end{align*}

Then compose with a map $\HH\to\DD$:
\begin{align*}
f: S_\alpha &\to \DD \\
f(z) &= (\phi \circ g)(z) = {z^{\pi\over \alpha} - i \over z^{\pi\over\alpha} + i}
.\end{align*}

![](figures/image_2020-07-22-13-22-46.png)

## Strip to Disc

- Map to horizontal strip by rotation $z\mapsto \lambda z$.
- Map horizontal strip to sector by $z \mapsto e^z$
- Map sector to $\HH$ by $z\mapsto z^{\pi\over\alpha}$.
- Map $\HH\to\DD$.


:::{.theorem title="Riemann Mapping"}
If $\Omega$ is simply connected, nonempty, and not $\CC$, then for every $z_0\in \Omega$ there exists a unique conformal map $F:\Omega \to \DD$ such that $F(z_0) = 0$ and $F'(z_0) > 0$.

Thus any two such sets $\Omega_1, \Omega_2$ are conformally equivalent.
:::


# Schwarz Reflection

:::{.theorem title="Schwarz Reflection \label{SchwarzReflection}  "}
If $f$ is continuous and holomorphic on $\HH^+$ and real-valued on $\RR$, then the extension defined by $F(z) = \bar{f(\bar{z})}$ for $z\in \HH^-$ is a well-defined holomorphic function on $\CC$.
:::

:::{.remark}
$\HH^+, \HH^-$ can be replaced with any region symmetric about a line segment $L\subseteq \RR$.
:::

# Zeros and Poles

## Singularities

:::{.theorem title="Riemann's Removable Singularity Theorem"}
If $f$ is holomorphic on $\Omega$ except possibly at $z_0$ and $f$ is bounded on $\Omega\setminus\theset{z_0}$, then $z_0$ is a removable singularity.
:::

## Counting Zeros 

:::{.theorem title="Argument Principle"}
For $f$ meromorphic in $\gamma^\circ$, if $f$ has no poles and is nonvanishing on $\gamma$ then
\[  
\Delta_\gamma \arg f(z) = \int_\gamma {f'(z) \over f(z)} \,dz = 2\pi (Z_f - P_f)
,\]
where $Z_f$ and $P_f$ are the number of zeros and poles respectively enclosed by $\gamma$, counted with multiplicity.
:::

:::{.theorem title="Rouché's Theorem \label{Rouche}"}
If $f, g$ are analytic on a domain $\Omega$ with finitely many zeros in $\Omega$ and $\gamma \subset \Omega$ is a closed curve surrounding each point exactly once, where $\abs{g} < \abs{f}$ on $\gamma$, then $f$ and $f+g$ have the same number of zeros.

Alternatively:

Suppose $f = g + h$ with $g \neq 0, \infty$ on $\gamma$ with $\abs g > \abs h$ on $\gamma$.
Then $$\Delta_\gamma \arg(f) = \Delta_\gamma \arg(h)\quad\text{ and } Z_f - P_f = Z_g - P_g.$$
:::

:::{.example}
- Take $P(z) = z^4 + 6z + 3$.
- On $\abs{z} < 2$:
  - Set $f(z) = z^4$ and $g(z) = 6z + 3$, then $\abs{g(z)} \leq 6\abs{z} + 3 = 15 < 16= \abs{f(z)}$.
  - So $P$ has 4 zeros here.
- On $\abs{z} < 1$:
  - Set $f(z) = 6z$ and $g(z) = z^4 + 3$.
  - Check $\abs{g(z)} \leq \abs{z}^4 + 3 = 4 < 6 = \abs{f(z)}$.
  - So $P$ has 1 zero here.
:::

:::{.example}
- Claim: the equation $\alpha z e^z = 1$ where $\abs{\alpha} > e$ has exactly one solution in $\DD$.
- Set $f(z) = \alpha z$ and $g(z) = e^{-z}$.
- Estimate at $\abs{z} =1$ we have $\abs{g} =\abs{e^{-z}} = e^{-\Re(z)} \leq e^1 < \abs{\alpha} = \abs{f(z)}$
- $f$ has one zero at $z_0 = 0$, thus so does $f+g$.
:::


# Linear Fractional Transformations

:::{.definition title="Linear Fractional Transformation"}
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

:::{.theorem title="Cayley Transform"}
The fractional linear transformation given by $F(z) = {i - z \over i + z}$ maps $\DD\to \HH$ with inverse $G(w) = i {1-w \over 1 + w}$.
:::

:::{.theorem title="Schwarz Lemma \label{SchwarzLemma}  "}
If $f: \DD \to \DD$ is holomorphic with $f(0) = 0$, then

1. $\abs{f(z)} \leq \abs z$ for all $z\in \DD$
2. $\abs{f'(0)} \leq 1$.

Moreover, if $\abs{f(z_0)} = \abs{z_0}$ for any $z_0\in \DD$ or $\abs{f'(0)} = 1$, then $f$ is a rotation
:::


# Appendix: Proofs of the Fundamental Theorem of Algebra

### Fundamental Theorem of Algebra: Argument Principle 

- Let $P(z) = a_nz^n + \cdots + a_0$ and $g(z) = P'(z)/P(z)$, note $P$ is holomorphic
- Since $\lim_{\abs z \to \infty} P(z) = \infty$, there exist an $R>0$ such that $P$ has no roots in $\theset{\abs{z} \geq R}$.
- Apply the argument principle:
\begin{align*}
N(0) = {1\over 2\pi i} \oint_{\abs{\xi} = R} g(\xi) \,d\xi
.\end{align*}
- Check that $\lim_{\abs{z\to \infty}}zg(z) = n$, so $g$ has a simple pole at $\infty$
- Then $g$ has a Laurent series ${n\over z} + {c_2 \over z^2} + \cdots$
- Integrate term-by-term to get $N(0) = n$.



### Fundamental Theorem of Algebra: Rouche's Theorem

- Let $P(z) = a_nz^n + \cdots + a_0$
- Set $f(z) = a_n z^n$ and $g(z) = P(z) - f(z) = a_{n-1}z^{n-1} + \cdots + a_0$, so $f+g = P$.
- Choose $R > \max\qty{ { \abs{a_{n-1}} + \cdots + \abs{a_0} \over \abs{a_n} }, 1}$, then

\begin{align*}
|g(z)| 
&\definedas |a_{n-1}z^{n-1} + \cdots + a_1 z + a_0 | \\
&\leq |a_{n-1}z^{n-1}| + \cdots + |a_1 z| + |a_0 | \quad\text{by the triangle inequality} \\
&= |a_{n-1}|\cdot |z^{n-1}| + \cdots + |a_1|\cdot| z| + |a_0 | \\
&=  |a_{n-1}|\cdot R^{n-1} + \cdots + |a_1| R + |a_0 | \\
&\leq |a_{n-1}|\cdot R^{n-1}+|a_{n-2}|\cdot R^{n-1} + \cdots + |a_1| \cdot R^{n-1} + |a_0 |\cdot R^{n-1} \quad\text{since } R>1 \implies R^{a+b} \geq R^a \\
&= R^{n-1} \left( |a_{n-1}| + |a_{n-2}| + \cdots + |a_1| + |a_0| \right) \\
&\leq R^{n-1} \left( |a_n|\cdot R \right) \quad\text{by choice of } R   \\
&= R^{n} |a_n| \\
&= |a_n z^n| \\
&\definedas  |f(z)|
\end{align*}

- Then $a_n z^n$ has $n$ zeros in $\abs{z} < R$, so $f+g$ also has $n$ zeros.

### Fundamental Theorem of Algebra: Liouville's Theorem

- Suppose $p$ is nonconstant and has no roots, then ${1\over p}$ is entire
- Write $g(z) \definedas \frac{p(z)}{z^{n}}=a_{n}\left(\frac{a_{n-1}}{z}+\dots+\frac{a_{0}}{z^{n}}\right)$
- Outside a disc:
  - Note $\lim_{z\to \infty} = 0$ for the parenthesized terms, so there exists an $R$ large enough such that $\abs{g(z)} \geq {1\over 2} \abs{a_n}$
  - Then $\abs{p(z)} \geq {R^n\over 2} \abs{a_n}$ implies ${1\over p}$ is bounded in $\abs{z} > R$
- Inside a disc:
  - $p$ is continuous with no roots so $p$ is bounded below on $\abs{z} < R$.
  - $p$ is continuous on a compact set and thus achieves a min $A$
  - Set $B = \min(A, {R^n \over 2} \abs{a_n})$, then $p \geq B$ on $\abs{z} < R$.
- Thus $p$ is bounded below everywhere and thus ${1\over p}$ is bounded above everywhere, thus bounded.
- Thus ${1\over p}$ is constant, forcing $p$ to be constant.

### Fundamental Theorem of Algebra: Open Mapping Theorem

- $p$ induces a continuous map $\CP^1 \to \CP^1$
- The continuous image of compact space is compact; 
- Since the codomain is Hausdorff space, the image is closed.
- $p$ is holomorphic and non-constant, so by the Open Mapping Theorem, the image is open.
- Thus the image is clopen in $\CP^1$.
- The image is nonempty, since $p(1) = \sum a_i \in \CC$
- $\CP^1$ is connected
- But the only nonempty clopen subset of a connected space is the entire space.
- So $p$ is surjective, and $p\inv(0)$ is nonempty.
- So $p$ has a root.

# Appendix
\[
dz &= dx + i~dy \\
d\bar z &= dx - i~dy \\
f_z &= f_x = i\inv f_y \\
\int_{0}^{2 \pi} e^{i \ell x} d x
&=\left\{\begin{array}{ll}{2 \pi} & {(\ell=0)} \\ {0} & {(\ell \neq 0)}\end{array}\right.
.\]

## Misc Prerequisites

**Standard forms of conic sections:**

- Circle: $x^2 + y^2 = r^2$
- Ellipse: $\qty{\frac x a}^2  + \qty{\frac y b}^2 = 1$
- Hyperbola: $\qty{\frac x a}^2  - \qty{\frac y b}^2 = 1$
  - Rectangular Hyperbola: $xy = \frac{c^2}{2}$.
- Parabola: $-4ax + y^2 = 0$.

> Mnemonic:
> Write $f(x, y) = Ax^2 + Bxy + Cy^2 + \cdots$, then consider the discriminant $\Delta = B^2 - 4AC$:
>
> - $\Delta < 0 \iff$ ellipse
>   - $\Delta < 0$ and $A=C, B=0 \iff$ circle
> - $\Delta = 0 \iff$ parabola
> - $\Delta > 0 \iff$ hyperbola

**Completing the square:**

\[
x^2 - bx = (x - s)^2 - s^2 \quad\text{where} s = \frac{b}{2} \\
x^2 + bx = (x + s)^2 - s^2 \quad\text{where} s = \frac{b}{2}
.\]


**Useful Properties**

- $\Re(z) = \frac 1 2 (z + \bar z)$ and $\Im(z) = \frac{1}{2i}(z - \bar z)$.
- $z\bar z = \abs{z}^2$
- Exponential forms of cosine and sine:
  - $\cos(\theta) = \frac 1 2 \qty{e^{i\theta} + e^{-i\theta}}$
  - $\sin(\theta) = \frac{1}{2i}\qty{e^{i\theta} - e^{-i\theta}}$.

**Useful Series**

\[
\sum_{k=1}^{n} k &=\frac{n(n+1)}{2} \\
\sum_{k=1}^{n} k^{2} &=\frac{n(n+1)(2 n+1)}{6} \\
\sum_{k=1}^{n} k^{3} &=\frac{n^{2}(n+1)^{2}}{4}  \\
\log(z) &= \sum_{j=0}^\infty (-1)^j \frac{\qty{z-a}^j}{j}
\dd{}{z} \sum_{j=0}^\infty a_j z^j &= \sum_{j=0}^\infty a_{j+1}z^j
\]

The sum of the interior angles of an $n\dash$gon is $(n-2)\pi$, where each angle is $\frac{n-2}{n}\pi$.


Basics

- Show that ${1\over z} \sum_{k=1}^\infty {z^k \over k}$ converges on $S^1 \setminus\theset{1}$ using summation by parts.
- Show that any power series is continuous on its domain of convergence.
- Show that a uniform limit of continuous functions is continuous.

??

- Show that if $f$ is holomorphic on $\DD$ then $f$ has a power series expansion that converges uniformly on every compact $K\subset \DD$.
- Show that any holomorphic function $f$ can be uniformly approximated by polynomials.
- Show that if $f$ is holomorphic on a connected region $\Omega$ and $f'\equiv 0$ on $\Omega$, then $f$ is constant on $\Omega$.

- Show that if $\abs{f} = 0$ on $\bd \Omega$ then either $f$ is constant or $f$ has a zero in $\Omega$.
- Show that if $\theset{f_n}$ is a sequence of holomorphic functions converging uniformly to a function $f$ on every compact subset of $\Omega$, then $f$ is holomorphic on $\Omega$ and $\theset{f_n'}$ converges uniformly to $f'$ on every such compact subset.
- Show that if each $f_n$ is holomorphic on $\Omega$ and $F \definedas \sum f_n$ converges uniformly on every compact subset of $\Omega$, then $F$ is holomorphic.
- Show that if $f$ is once complex differentiable at each point of $\Omega$, then $f$ is holomorphic.

