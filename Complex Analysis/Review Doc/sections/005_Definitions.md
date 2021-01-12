# Definitions

:::{.definition title="Analytic"}
A function $f:\Omega \to \CC$ is *analytic* at $z_0\in \Omega$ iff there exists a power series $g(z) = \sum a_n (z-z_0)^n$ with radius of convergence $R>0$ and a neighborhood $U\ni z_0$ such that $f(z) = g(z)$ on $U$.
:::

:::{.definition title="Cauchy-Riemann Equations"}
\[
u_x = v_y \quad\text{and}\quad u_y = -v_x \\
\frac{\partial u}{\partial r}=\frac{1}{r} \frac{\partial v}{\partial \theta} \quad \text { and } \quad \frac{\partial v}{\partial r}=-\frac{1}{r} \frac{\partial u}{\partial \theta} \\
.\]
:::

:::{.definition title="Entire"}
A function that is holomorphic on $\CC$ is said to be *entire*.
:::

:::{.definition title="Essential Singularity"}
A singularity $z_0$ is *essential* iff it is neither removable nor a pole.

Equivalently, a Laurent series expansion about $z_0$ has a principal part with infinitely many terms.
:::

:::{.definition title="Holomorphic"}
A function $f:\CC\to \CC$ is *holomorphic* at $z_0$ if the following limit converges:
\[  
\lim_{h\to 0} {1\over h} \qty{f(z_0 + h) - f(z_0)} \definedas f'(z_0)
.\]
:::

:::{.definition title="Harmonic"}
A real function of two variables $u(x, y)$ is *harmonic* iff its Laplacian vanishes:
\[  
\Delta u \definedas \qty{\dd{^2}{x^2} + \dd{^2}{y^2}}u = 0
.\]
:::

:::{.definition title="Meromorphic"}
A function $f:\Omega\to\CC$ is *meromorphic* iff there exists a sequence $\theset{z_n}$ such that

- $\theset{z_n}$ has no limit points in $\Omega$.
- $f$ is holomorphic in $\Omega\setminus\theset{z_n}$.
- $f$ has poles at the points $\theset{z_n}$.

If $f$ is either holomorphic or has a pole at $z=\infty$ is said to be meromorphic on $\CP^1$.
:::

:::{.definition title="Poles (and associated terminology)"}
A *pole* $z_0$ of a meromorphic function $f(z)$ is a zero of $g(z) \definedas {1\over f(z)}$.
If there exists an $n$ such that
\[  
\lim_{z\to z_0}\qty{z-z_0}^nf(z)
\]
is holomorphic and nonzero in a neighborhood of $z_0$, then the minimal such $n$ is the *order* of the pole.
A pole of order 1 is said to be a *simple pole*.

The pole $z_0$ is *isolated* iff there exists a neighborhood of $z_0$ containing no other poles of $f$.
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



