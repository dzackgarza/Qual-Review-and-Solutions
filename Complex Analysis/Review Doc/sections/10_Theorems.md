# Definitions

:::{.definition title="Complex Differentiable"}
???
:::

:::{.definition title="Analytic"}
???
:::

once complex differentiable in neighborhoods of every point.
:::{.definition title="Holomorphic"}
???
:::



# Theorems

## Basics

:::{.theorem title="Baire Category Theorem"}
The intersection of open dense sets is open.
:::

:::{.theorem title="Mean Value Theorem"}
?
:::
\todo[inline]{???}


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


:::{.theorem title="$\star$ Cauchy Integral Formula"}
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

:::{.proof}
Given $z_0\in \Omega$, pick the largest disc $D_R(z_0) \subset \Omega$ and let $C_R = \bd D_R$.
Using the integral formula, defining $\norm{f}_{C_R} = \max_{\abs{z-z_0} = R} \abs{f(z)}$

\[
\abs{ f^{(n)}(z_0) } \leq \frac{n!}{2\pi} \int_0^{2\pi} \frac{\norm{f}_{C_R}}{R^{n+1}} R~d\theta = \frac{n! \norm{f}_{C_R}}{R^{n}}
.\]
:::


## Holomorphic and Entire Functions

Integrals of holomorphic functions vanish:
:::{.theorem title="Cauchy's Theorem"}
If $f$ is holomorphic on $\Omega$, then 
\[  
\int_{\bd \Omega} f(z) \, dz = 0
.\]
:::


All integrals vanishing along every triangle implies holomorphic:
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

:::{.theorem title="$\star$ Rouché"}
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
:::{.theorem title="$\star$ Casorati-Weierstrass"}
If $f$ is holomorphic on $\Omega\setminus\theset{z_0}$ where $z_0$ is an essential singularity, then for every $V\subset \Omega\setminus\theset{z_0}$, $f(V)$ is dense in $\CC$.
:::

:::{.theorem title="Cayley Transform"}
The fractional linear transformation given by $F(z) = {i - z \over i + z}$ maps $\DD\to \HH$ with inverse $G(w) = i {1-w \over 1 + w}$.
:::

Two functions agreeing on a set with a limit point are equal on a domain:
:::{.theorem title="Continuation Principle / Identity Theorem"}
If $f$ is holomorphic on a bounded connected domain $\Omega$ and there exists a sequence $\theset{z_i}$ with a limit point in $\Omega$ such that $f(z_i) = 0$, then $f\equiv 0$ on $\Omega$.
:::

:::{.corollary}
The ring of holomorphic functions on a domain in $\CC$ has no zero divisors.
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


:::{.theorem title="Little Picard"}
Todo
:::
\todo{???}

## Conformal Maps

:::{.theorem title="Riemann Mapping"}
If $\Omega$ is simply connected, nonempty, and not $\CC$, then for every $z_0\in \Omega$ there exists a unique conformal map $F:\Omega \to \DD$ such that $F(z_0) = 0$ and $F'(z_0) > 0$.

Thus any two such sets $\Omega_1, \Omega_2$ are conformally equivalent.
:::

:::{.theorem title="Classification of Conformal Maps"}
There are 8 major types of conformal maps:

- ?
- ?
:::
\todo[inline]{???}
