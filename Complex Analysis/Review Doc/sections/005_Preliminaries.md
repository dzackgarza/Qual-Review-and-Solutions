# Preliminaries

## Complex Arithmetic and Calculus

:::{.definition title="Analytic"}
A function $f:\Omega \to \CC$ is *analytic* at $z_0\in \Omega$ iff there exists a power series $g(z) = \sum a_n (z-z_0)^n$ with radius of convergence $R>0$ and a neighborhood $U\ni z_0$ such that $f(z) = g(z)$ on $U$.
:::

:::{.definition title="Complex Differentiable"}
A function $f: \CC\to \CC$ is **complex differentiable** at $z_0$ iff the following limit exists:
\[
\lim_{h\to 0} { f(z_0 + h) - f(h) \over h  } 
.\]

:::

:::{.definition title="Cauchy-Riemann Equations"}
\[
u_x = v_y \quad\text{and}\quad u_y = -v_x \\
\frac{\partial u}{\partial r}=\frac{1}{r} \frac{\partial v}{\partial \theta} \quad \text { and } \quad \frac{\partial v}{\partial r}=-\frac{1}{r} \frac{\partial u}{\partial \theta} \\
.\]
:::

:::{.definition title="Holomorphic"}
A function $f:\CC\to \CC$ is *holomorphic* at $z_0$ if the following limit converges:
\[  
\lim_{h\to 0} {1\over h} \qty{f(z_0 + h) - f(z_0)} \definedas f'(z_0)
.\]
:::

:::{.example title="Holomorphic vs non-holomorphic"}
\envlist
- $f(z) = {1\over z}$ is holomorphic on $\CC\smz$.
- $f(z) = \bar{z}$ is *not* holomorphic, since $\bar h \over h$ does not converge (but is real differentiable).
:::

:::{.definition title="del and delbar operators"}
\[
\del 
\da \frac{\partial}{\partial z} 
\da \frac{1}{2}\left(\frac{\partial}{\partial x}-i \frac{\partial}{\partial y}\right) 
\quad 
\delbar 
\da \frac{\partial}{\partial \bar{z}} 
\da \frac{1}{2}\left(\frac{\partial}{\partial x}+i \frac{\partial}{\partial y}\right)
.\]

:::

:::{.proposition title="Holomorphic iff delbar vanishes"}
$f$ is holomorphic at $z_0$ iff $\delbar f(z_0) = 0$.
:::

:::{.definition title="Entire"}
A function that is holomorphic on $\CC$ is said to be *entire*.
:::

:::{.definition title="Laplacian and Harmonic Functions"}
A real function of two variables $u(x, y)$ is *harmonic* iff its Laplacian vanishes:
\[  
\Delta u \definedas \qty{\dd{^2}{x^2} + \dd{^2}{y^2}}u = 0
.\]
:::

:::{.theorem title="Green's Theorem"}
If $\Omega \subseteq \CC$ is bounded with $\bd \Omega$ piecewise smooth and $f, g\in C^1(\bar \Omega)$, then $$\int_{\bd \Omega} f\, dx + g\, dy = \iint_{\Omega} \qty{ \dd{g}{x} - \dd{f}{y} } \, dA.$$
:::

### Exercises

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

:::{.concept}
\hfill
- See [walkthrough here](https://users.math.msu.edu/users/shapiro/Teaching/classes/425/crpolar.pdf).
- See problem set 1.
:::

:::{.proof}
\envlist

- Take derivative along two paths, along a ray with constant angle $\theta_0$ and along a circular arc of constant radius $r_0$.
- Then equate real and imaginary parts.
:::

\todo[inline]{proof}

:::{.proposition title="Injectivity Relates to Derivatives"}
If $z_0$ is a zero of $f'$ of order $n$, then $f$ is $(n+1)$-to-one in a neighborhood of $z_0$.
:::

:::{.proof}
?
:::

\todo[inline]{proof}


## Power Series


:::{.remark}
Note that if a power series converges uniformly, then summing commutes with integrating or differentiating.
:::

:::{.proposition title="Radius of Convergence by the Root Test"}
For $f(z) = \sum_{k\in \NN} c_k z^k$, defining
\[
{1\over R} \da \limsup_{k} \abs{a_k}^{1\over k}
,\]
then $f$ converges absolutely and uniformly for $D_R \da\abs{z} < R$ and diverges for $\abs{z} > R$.
Moreover $f$ is holomorphic in $D_R$, can be differentiated term-by-term, and $f' = \sum_{k\in \NN} n c_k z^k$.
:::

:::{.proposition title="Ratio test"}

:::

\todo[inline]{todo}

:::{.theorem title="Summation by Parts"}
Define the forward difference operator $\Delta f_k = f_{k+1} - f_k$, then
\[
\sum_{k=m}^n f_k \Delta g_k  + \sum_{k=m}^{n-1} g_{k+1}\Delta f_k = f_n g_{n+1} - f_m g_m
\]

> Note: compare to $\int_a^b f \, dg  + \int_a^b g\, df = f(b) g(b) - f(a) g(a)$.

:::

:::{.theorem title="Abel's Theorem"}
If $\sum_{k=1}^\infty c_k$ converges, then 
\[
\lim_{z\to 1^-} \sum_{k\in \NN} c_k z^k = \sum_{k\in \NN} c_k
.\]

:::


:::{.theorem title="Improved Taylor's Theorem"}
If $f$ is holomorphic on a region $\Omega$ with $\closure{ D_R(z_0)} \subseteq \Omega$, and for every $z\in D_r(z_0)$, $f$ has a power series expansion of the following form:
\[
f(z)=\sum_{n=0}^{\infty} a_{n}\left(z-z_{0}\right)^{n} \quad\text{where} a_{n}=\frac{f^{(n)}\left(z_{0}\right)}{n !}
= {1 \over 2\pi r^n}\int_0^{2\pi} f(z_0 + re^{i\theta})e^{-in\theta} \dtheta
.\]

:::


### Exercises

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


- ![image_2021-05-17-10-27-08](figures/image_2021-05-17-10-27-08.png)
- ![](figures/image_2021-05-17-10-27-21.png)
- ![image_2021-05-17-10-29-25](figures/image_2021-05-17-10-29-25.png)
