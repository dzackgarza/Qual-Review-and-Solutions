
---
title: "Complex Analysis Qualifying Exam Notes"
---

**Preface**

References

- Simon

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

## Integrals and Residues


:::{.theorem title="Cauchy Integral Formula"}
Suppose $f$ is holomorphic on $\Omega$, then 

\[
f(z) = {1 \over 2\pi i} \oint_{\bd \Omega} {f(z) \over z-a}\,dz
\]
and
\[
\dd{^nf }{z^n}(z) - {n! \over 2\pi i} \oint_{\bd \Omega} {f\xi \over (\xi - z)^{n+1}} \,d\xi
.\]
:::

The $n$th Taylor coefficient of an analytic function is at most $\sup_{\abs z = R} \abs{f}/R^n$:
:::{.theorem title="Cauchy's Inequality"}
For $z_o \in D_R(z_0) \subset \Omega$, we have
\[
\left|f^{(n)}\left(z_{0}\right)\right| \leq \frac{n !}{2 \pi} \int_{0}^{2 \pi} \frac{\|f\|_{C_{R}}}{R^{n+1}} R d \theta=\frac{n !\|f\|_{C_{R}}}{R^{n}} 
.\]
:::
\todo{These don't quite match up.}

## Holomorphic and Entire Functions

Integrals of holomorphic functions vanish:
:::{.theorem title="Cauchy's Theorem"}
If $f$ is holomorphic on $\Omega$, then 
\[  
\int_{\bd \Omega} f(z) \, dz = 0
.\]
:::

:::{.theorem title="Morera's Theorem"}
If $f$ is continuous on a domain $\Omega$ and $\int_T f = 0$ for every triangle $T\subset \Omega$, then $f$ is holomorphic.
:::

:::{.theorem title="Liouville"}
If $f$ is entire and bounded, $f$ is constant.
:::

## Rouché

The logarithmic derivative measures the difference of zeros and poles:
:::{.theorem title="Argument Principle"}
Todo
:::
\todo{Argument principle.}

:::{.theorem title="Rouché"}
If $f, g$ are analytic on a domain $\Omega$ with finitely many zeros in $\Omega$ and $\gamma \subset \Omega$ is a closed curve surrounding each point exactly once, where $\abs{g} < \abs{f}$ on $\gamma$, then $f$ and $f+g$ have the same number of zeros.
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

Holomorphic functions preserve open sets:
:::{.theorem title="Open Mapping"}
Any holomorphic non-constant map is an open map.
:::


:::{.theorem title="Maximum Modulus"}
If $f$ is holomorphic and nonconstant on an open region $\Omega$, then $\abs{f}$ can not attain a maximum on $\Omega$.

If $\Omega$ is bounded and $f$ is continuous on $\bar \Omega$, then $\max_{\bar \Omega} \abs{f}$ occurs on $\bd \Omega$.
  
Conversely, if $f$ attains a local maximum at $z_0 \in \Omega$, then $f$ is constant on $\Omega$.


:::

The image of a disc punctured at an essential singularity is dense in $\CC$:
:::{.theorem title="Casorati-Weierstrass"}
If $f$ is holomorphic on $\Omega\setminus\theset{z_0}$ where $z_0$ is an essential singularity, then for every $V\subset \Omega\setminus\theset{z_0}$, $f(V)$ is dense in $\CC$.
:::

:::{.theorem title="Cayley Transform"}
The fractional linear transformation given by $F(z) = {i - z \over i + z}$ maps $\DD\to \HH$ with inverse $G(w) = i {1-w \over 1 + w}$.
:::

Two functions agreeing on a set with a limit point are equal on a domain
:::{.theorem title="Continuation Principle / Identity Theorem"}
If $f$ is holomorphic on a bounded connected domain $\Omega$ and there exists a sequence $\theset{z_i}$ with a limit point in $\Omega$ such that $f(z_i) = 0$, then $f\equiv 0$ on $\Omega$.
:::


:::{.theorem title="Schwarz Reflection"}
If $f$ is continuous and holomorphic on $\HH^+$ and real-valued on $\RR$, then the extension defined by $F(z) = \bar{f(\bar{z})}$ for $z\in \HH^-$ is a well-defined holomorphic function on $\CC$.
:::

:::{.remark}
$\HH^+, \HH^-$ can be replaced with any region symmetric about a line segment $L\subseteq \RR$.
:::

:::{.theorem title="Schwarz Lemma"}
If $f: \DD \to \DD$ is holomorphic with $f(0) = 0$, then

1. $\abs{f(z)} \leq \abs z$ for all $z\in \DD$
2. $\abs{f'(0)} \leq 1$.

Moreover, if $\abs{f(z_0)} = \abs{z_0}$ for any $z_0\in \DD$ or $\abs{f'(0)} = 1$, then $f$ is a rotation
:::

:::{.theorem title="Riemann Mapping"}
If $\Omega$ is simply connected, nonempty, and not $\CC$, then for every $z_0\in \Omega$ there exists a unique conformal map $F:\Omega \to \DD$ such that $F(z_0) = 0$ and $F'(z_0) > 0$.

Thus any two such sets $\Omega_1, \Omega_2$ are conformally equivalent.
:::




# Stuff

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

# Conformal Maps

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

# Appendix

\[
dz &= dx + i~dy \\
d\bar z &= dx - i~dy \\
f_z &= f_x = i\inv f_y \\
\int_{0}^{2 \pi} e^{i \ell x} d x
&=\left\{\begin{array}{ll}{2 \pi} & {(\ell=0)} \\ {0} & {(\ell \neq 0)}\end{array}\right.
.\]

- Holomorphic: once complex differentiable in neighborhoods of every point.
- Analytic: equal to its Taylor series expansion

> Collection of facts used on problem sets

## Things to know well:

- Cauchy Integral Formula
- Estimates for derivatives, mean value theorem
- Rouché's theorem
- Casorati-Weierstrass
- The 8 types of conformal maps

## Theorems

### The Argument Principle

Theorem (Statement 1)
: For $f$ meromorphic in $\gamma^\circ$, $$\Delta_\gamma \arg f(z) = 2\pi (Z_f - P_f).$$

### Rouche

Theorem (Statement 1)
:   Suppose $f = g + h$ with $g \neq 0, \infty$ on $\gamma$ with $\abs g > \abs h$ on $\gamma$.
    Then $$\Delta_\gamma \arg(f) = \Delta_\gamma \arg(h)\quad\text{ and } Z_f - P_f = Z_g - P_g.$$

## Misc Prereq

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
- $\cos(\theta) = \frac 1 2 \qty{e^{i\theta} + e^{-i\theta}}$
- $\sin(\theta) = \frac{1}{2i}\qty{e^{i\theta} - e^{-i\theta}}$.

**Useful Series**

\[
\sum_{k=1}^{n} k &=\frac{n(n+1)}{2} \\
\sum_{k=1}^{n} k^{2} &=\frac{n(n+1)(2 n+1)}{6} \\
\sum_{k=1}^{n} k^{3} &=\frac{n^{2}(n+1)^{2}}{4}  \\
\log(z) &= \sum_{j=0}^\infty (-1)^j \frac{\qty{z-a}^j}{j}
\]


**Cauchy-Riemann Equations**

\[
u_x = v_y \quad\text{and}\quad u_y = -v_x \\
\frac{\partial u}{\partial r}=\frac{1}{r} \frac{\partial v}{\partial \theta} \quad \text { and } \quad \frac{\partial v}{\partial r}=-\frac{1}{r} \frac{\partial u}{\partial \theta} \\
.\]



## Useful Techniques

**Showing a function is constant:**

- Write $f = u + iv$ and use Cauchy-Riemann to show $u_x, u_y = 0$, etc.
- Show that $f$ is entire and bounded.

**Showing a function is zero**:
Show $f$ is entire, bounded, and $\lim_{z\to\infty} f(z) = 0$.


**Deriving Polar Cauchy-Riemann:**
See [walkthrough here](https://users.math.msu.edu/users/shapiro/Teaching/classes/425/crpolar.pdf).
Take derivative along two paths, along a ray with constant angle $\theta_0$ and along a circular arc of constant radius $r_0$.
Then equate real and imaginary parts.
See problem set 1.

**Computing Arguments:**
$\Arg(z/w) = \Arg(z) - \Arg(w)$.

The sum of the interior angles of an $n\dash$gon is $(n-2)\pi$, where each angle is $\frac{n-2}{n}\pi$.

## Residues

If $p$ is a simple pole, $\Res(p, f) = \lim_{z\to p} (z-p)f(z)$.
Example: Let $f(z) = \frac{1}{1+z^2}$, then $\Res(i, f) = \frac{1}{2i}$.


Green's Theorem:
Todo

$\dd{}{z} \sum_{j=0}^\infty a_j z^j = \sum_{j=0}^\infty a_{j+1}z^j$.

## Pithy Statements

- Little Picard: $f$ misses at most one point and is a homeomorphism onto its image.
- Baire's Theorem: The intersection of open dense sets is open.
- Morera: Integrals vanishing along every rectangle implies holomorphic.
- Schwarz Reflection: ???
- The ring of holomorphic functions on a domain in $\CC$ has no zero divisors (by the identity principle).

## Precise Refinements

**Cauchy Inequality:**
Given $z_0\in \Omega$, pick the largest disc $D_R(z_0) \subset \Omega$ and let $C_R = \bd D_R$.
Using the integral formula, defining $\norm{f}_{C_R} = \max_{\abs{z-z_0} = R} \abs{f(z)}$

\[
\abs{ f^{(n)}(z_0) } \leq \frac{n!}{2\pi} \int_0^{2\pi} \frac{\norm{f}_{C_R}}{R^{n+1}} R~d\theta = \frac{n! \norm{f}_{C_R}}{R^{n}}
.\]

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

