# Theorems

## Basics


## Holomorphic and Entire Functions

### Key Theorems

:::{.theorem title="Cauchy's Theorem" ref="CauchyTheorem"}
If $f$ is holomorphic on $\Omega$, then 
\[  
\int_{\bd \Omega} f(z) \, dz = 0
.\]

> Slogan: closed path integrals of holomorphic functions vanish.

:::

:::{.theorem title="Morera's Theorem" ref="Morera"}
If $f$ is continuous on a domain $\Omega$ and $\int_T f = 0$ for every triangle $T\subset \Omega$, then $f$ is holomorphic.

> Slogan: if every integral along a triangle vanishes, implies holomorphic.

:::

:::{.theorem title="Maximum Modulus" ref="MaximumModulus"}
If $f$ is holomorphic and nonconstant on an open connected region $\Omega$, then $\abs{f}$ can not attain a maximum on $\Omega$.
If $\Omega$ is bounded and $f$ is continuous on $\bar \Omega$, then $\max_{\bar \Omega} \abs{f}$ occurs on $\bd \Omega$.
Conversely, if $f$ attains a local supremum at $z_0 \in \Omega$, then $f$ is constant on $\Omega$.
:::

:::{.theorem title="Liouville's Theorem" ref="Liouville"}
If $f$ is entire and bounded, $f$ is constant.
:::

:::{.theorem title="Cauchy Integral Formula" ref="CauchyIntegral"}
Suppose $f$ is holomorphic on $\Omega$, then 
\[
f(z) = {1 \over 2\pi i} \oint_{\bd \Omega} {f(\xi) \over \xi-z}\,d\xi
\]
and
\[
\dd{^nf }{z^n}(z) = {n! \over 2\pi i} \int_{\bd \Omega} {f(\xi) \over (\xi - z)^{n+1}} \,d\xi
.\]
:::

:::{.theorem title="Cauchy's Inequality" ref="CauchyInequality"}
For $z_0 \in D_R(z_0) \subset \Omega$, we have
\[
\abs{ f^{(n)} (z_0) } 
\leq \frac{n !}{2 \pi} \int_{0}^{2 \pi} \frac{ \norm{f}_{\infty} } {R^{n+1}} R \,d\theta
= \frac{n !\norm{f}_{\infty}}{R^n} 
,\]
where $\norm{f}_{\infty}\definedas \sup_{z\in C_R} \abs{f(z)}$.

:::{.slogan}
The $n$th Taylor coefficient of an analytic function is at most $\sup_{\abs z = R} \abs{f}/R^n$.
:::


:::

:::{.theorem title="Argument Principle"}
For $f$ meromorphic in $\gamma^\circ$, if $f$ has no poles and is nonvanishing on $\gamma$ then
\[  
\Delta_\gamma \arg f(z) = \int_\gamma {f'(z) \over f(z)} \,dz = 2\pi (Z_f - P_f)
,\]
where $Z_f$ and $P_f$ are the number of zeros and poles respectively enclosed by $\gamma$, counted with multiplicity.
:::

:::{.theorem title="Rouché's Theorem" ref="Rouche"}
If $f, g$ are analytic on a domain $\Omega$ with finitely many zeros in $\Omega$ and $\gamma \subset \Omega$ is a closed curve surrounding each point exactly once, where $\abs{g} < \abs{f}$ on $\gamma$, then $f$ and $f+g$ have the same number of zeros.

Alternatively:

Suppose $f = g + h$ with $g \neq 0, \infty$ on $\gamma$ with $\abs g > \abs h$ on $\gamma$.
Then $$\Delta_\gamma \arg(f) = \Delta_\gamma \arg(h)\quad\text{ and } Z_f - P_f = Z_g - P_g.$$
:::

:::{.theorem title="The Residue Theorem"}
If $f$ is holomorphic on an open set $\Omega$ containing a curve $\gamma$ and its interior $\gamma^\circ$, except for finitely many poles $\theset{z_k}_{k=1}^N \subset \gamma^\circ$.
Then
\[  
\int_\gamma f(z) \,dz = 2\pi i \sum_{k=1}^N \res_{z_k} f
.\]
:::

:::{.theorem title="Cayley Transform"}
The fractional linear transformation given by $F(z) = {i - z \over i + z}$ maps $\DD\to \HH$ with inverse $G(w) = i {1-w \over 1 + w}$.
:::

:::{.theorem title="Schwarz Lemma" ref="SchwarzLemma"}
If $f: \DD \to \DD$ is holomorphic with $f(0) = 0$, then

1. $\abs{f(z)} \leq \abs z$ for all $z\in \DD$
2. $\abs{f'(0)} \leq 1$.

Moreover, if $\abs{f(z_0)} = \abs{z_0}$ for any $z_0\in \DD$ or $\abs{f'(0)} = 1$, then $f$ is a rotation
:::

:::{.theorem title="Mean Value Theorem for Holomorphic Functions"}
\[
f(z_0) = {1\over \pi r^2} \iint_{D_r(z_0)} f(z)\, dA
.\]

:::

:::{.theorem title="Schwarz Reflection " ref="SchwarzReflection"}
If $f$ is continuous and holomorphic on $\HH^+$ and real-valued on $\RR$, then the extension defined by $F(z) = \bar{f(\bar{z})}$ for $z\in \HH^-$ is a well-defined holomorphic function on $\CC$.
:::

:::{.theorem title="Classification of Conformal Maps"}
There are 8 major types of conformal maps:

| Type/Domains                                            | Formula                                   |
| ------------                                            | -------                                   |
| Translation/Dilation/Rotation                           | $z\mapsto e^{i\theta}(cz + h)$            |
| Sectors to sectors                                      | $z\mapsto z^n$                            |
| $\DD_{1\over 2} \to \HH_{1\over 2}$, the first quadrant | $z\mapsto {1+z \over 1-z}$                |
| $\HH\to S$                                              | $z\mapsto \log(z)$                        |
| $\DD_{1\over 2} \to S_{1\over 2}$                       | $z\mapsto \log(z)$                        |
| $S_{1\over 2} \to \DD_{1\over 2}$                       | $z\mapsto e^{iz}$                         |
| $\DD_{1\over 2} \to \HH$                                | $z\mapsto {1\over 2}\qty{z + {1\over z}}$ |
| $S_{1\over 2} \to \HH$                                  | $z\mapsto \sin(z)$                        |

:::

:::{.theorem title="Characterization of conformal maps"}
Conformal maps $\DD\to\DD$ have the form
\[
g(z) = \lambda {1-a \over 1 - \bar a z}, \quad \abs{a} < 1, \quad \abs{\lambda} = 1
.\]
:::

### Others

:::{.theorem title="Riemann Mapping"}
If $\Omega$ is simply connected, nonempty, and not $\CC$, then for every $z_{0}\in \Omega$ there exists a unique conformal map $F:\Omega \to \DD$ such that $F(z_{0}) = 0$ and $F'(z_{0}) > 0$.

Thus any two such sets $\Omega_{1}, \Omega_{2}$ are conformally equivalent.
:::

:::{.theorem title="Riemann's Removable Singularity Theorem"}
If $f$ is holomorphic on $\Omega$ except possibly at $z_0$ and $f$ is bounded on $\Omega\setminus\theset{z_0}$, then $z_0$ is a removable singularity.
:::

:::{.proposition title="Holomorphic functions have harmonic components"}
If $f(z) = u(x, y) + iv(x, y)$ is holomorphic, then $u, v$ are harmonic.
:::

:::{.proposition title="Holomorphic functions are continuous."}
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

## Others

:::{.theorem title="Casorati-Weierstrass" ref="Casorati"}
If $f$ is holomorphic on $\Omega\setminus\theset{z_0}$ where $z_0$ is an essential singularity, then for every $V\subset \Omega\setminus\theset{z_0}$, $f(V)$ is dense in $\CC$.

> The image of a disc punctured at an essential singularity is dense in $\CC$.

:::

:::{.theorem title="Little Picard"}
If $f:\CC\to \CC$ is entire and nonconstant, then $\im(f)$ is either $\CC$ or $\CC\sm\ts{z_0}$ for some point $z_0$.
:::
\todo{???}

:::{.theorem title="Continuation Principle / Identity Theorem"}
If $f$ is holomorphic on a bounded connected domain $\Omega$ and there exists a sequence $\theset{z_i}$ with a limit point in $\Omega$ such that $f(z_i) = 0$, then $f\equiv 0$ on $\Omega$.

> Two functions agreeing on a set with a limit point are equal on a domain.

:::

:::{.corollary}
The ring of holomorphic functions on a domain in $\CC$ has no zero divisors.
:::

:::{.proof}
???
:::
\todo[inline]{Find the proof!}

:::{.proposition title="Injectivity Relates to Derivatives"}
If $z_0$ is a zero of $f'$ of order $n$, then $f$ is $(n+1)$-to-one in a neighborhood of $z_0$.
:::

:::{.proof}
?
:::

:::{.proposition title="Bounded Complex Analytic Functions form a Banach Space"}
For $\Omega\subseteq\CC$, show that $A(\CC)\definedas \theset{f: \Omega \to \CC \st f\text{ is bounded}}$ is a Banach space.
:::

:::{.proof}
?

> Apply Morera's Theorem and Cauchy's Theorem

:::

