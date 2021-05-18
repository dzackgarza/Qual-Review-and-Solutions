# Preliminaries

## Complex Arithmetic and Calculus

### Holomorphy and Cauchy-Riemann
:::{.definition title="Analytic"}
A function $f:\Omega \to \CC$ is *analytic* at $z_0\in \Omega$ iff there exists a power series $g(z) = \sum a_n (z-z_0)^n$ with radius of convergence $R>0$ and a neighborhood $U\ni z_0$ such that $f(z) = g(z)$ on $U$.
:::

:::{.definition title="Complex differentiable / holomorphic"}
A function $f: \CC\to \CC$ is **complex differentiable** or **holomorphic** at $z_0$ iff the following limit exists:
\[
\lim_{h\to 0} { f(z_0 + h) - f(h) \over h  } 
.\]

Equivalently, there exists an $\alpha\in \CC$ such that
\[
f(z_0+h) - f(z_0) = \alpha h + R(h) && R(h) \converges{h\to 0}\too 0 
.\]
In this case, $\alpha = f'(z_0)$.

:::

:::{.example title="Holomorphic vs non-holomorphic"}
\envlist
- $f(z) = {1\over z}$ is holomorphic on $\CC\smz$.
- $f(z) = \bar{z}$ is *not* holomorphic, since $\bar h \over h$ does not converge (but is real differentiable).
:::

:::{.definition title="Real (multivariate) differentiable"}
A function $F: \RR^n\to \RR^m$ is **real-differentiable** at $\vector p$ iff there exists a linear transformation $A$ such that
\[
{ \norm{ F(\vector p + \vector h) - F(\vector p) - A(\vector h) } \over \norm{ \vector h } } \converges{\norm{\vector h}\to 0}\too 0
.\]
Rewriting,
\[
\norm{ F(\vector p + \vector h) - F(\vector p)  - A(\vector h) } = \norm{ \vector{h} } \norm{ R(\vector h) }
&& \norm{R(\vector h) }\converges{\norm{\vector h } \to 0}\too 0
.\]

Equivalently, 
\[
F(\vector p + \vector h) - F(\vector p) = A(\vector h) + \norm{\vector h} R(\vector h) && \norm{R(\vector h) }\converges{\norm{\vector h } \to 0}\too 0
.\]

Or in a slightly more useful form,
\[
F(\vector p + \vector h) = F(\vector p) + A(\vector h) + R(\vector h) && R\in o( \norm{\vector h}), \text{ i.e. }
{ \norm{ R(\vector h) } \over  \norm{\vector h}} \converges{\vector h\to 0}\too 0
.\]
:::

:::{.proposition title="Derivation of Cauchy-Riemann"}
If $f$ is differentiable at $z_0$, then the limit defining $f'(z_0)$ must exist when approaching from any direction.
Identify $f(z) = f(x, y)$ and write $z_0 = x+ iy$, then first consider $h\in RR$, so $h = h_1 + ih_2$ with $h_2 = 0$.
Then
\[
f'(z_0) = 
\lim_{h_1\to 0} { f(x+h_1, y) - f(x, y) \over h_1}
\da \dd{f}{x}(x, y)
.\]
Taking $h \in i\RR$ purely imaginary, so $h= ih_2$,
\[
f'(z_0)
= \lim_{ih_2\to 0} { f(x, y+h_2) - f(x, y) \over ih_2 } \da {1\over i} \dd{f}{y}(x, y)
.\]
Equating,
\[
\dd{f}{x} = {1\over i} \dd{f}{y}
,\]
and writing $f = u + iv$ and $1/i = -i$ yields
\[
\dd{f}{x} &= \dd{u}{x} + i \dd{v}{x} \\
{1\over i} \dd{f}{y} &= {1\over i} \qty{ \dd{u}{y} + i \dd{v}{y}} = \dd{v}{y} - i\dd{u}{y} 
.\]
Thus
\[
\dd{u}{x} = \dd{v}{y} \hspace{8em} \dd{u}{y} = -\dd{v}{x}
.\]
:::

:::{.exercise title="Polar Form of Cauchy-Riemann"}
![image_2021-05-17-10-27-08](figures/image_2021-05-17-10-27-08.png)
:::

:::{.solution}
Setting 
\[
z = re^{i\theta} = r(\cos(\theta) + i\sin(\theta) ) = x+iy
\]
yields $x=r\cos(\theta), y=r\sin(\theta)$, one can identify
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


### Delbar, Harmonic Functions, Laplacian

:::{.definition title="del and delbar operators"}
\[
\del 
\da \frac{\partial}{\partial z} 
\da \frac{1}{2}\left(\frac{\partial}{\partial x}-i \frac{\partial}{\partial y}\right) 
\quad
\text{ and }
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


:::{.fact}
Consider $\sum c_k z^k$, set $R = \lim \abs{c_{k+1} \over c_k}$, and recall the **ratio test**:

- $R\in (0, 1) \implies$ convergence.
- $R\in [1, \infty] \implies$ divergence.
- $R=1$ yields no information.

:::


:::{.proposition title="Radius of Convergence by the Root Test"}
For $f(z) = \sum_{k\in \NN} c_k z^k$, defining
\[
{1\over R} \da \limsup_{k} \abs{a_k}^{1\over k}
,\]
then $f$ converges absolutely and uniformly for $D_R \da\abs{z} < R$ and diverges for $\abs{z} > R$.
Moreover $f$ is holomorphic in $D_R$, can be differentiated term-by-term, and $f' = \sum_{k\in \NN} n c_k z^k$.
:::


:::{.fact}
Recall the **$p\dash$test**:
\[
\sum n^{-p} < \infty \iff p \in (1, \infty)
.\]

  
:::

:::{.theorem title="Improved Taylor's Theorem"}
If $f$ is holomorphic on a region $\Omega$ with $\closure{ D_R(z_0)} \subseteq \Omega$, and for every $z\in D_r(z_0)$, $f$ has a power series expansion of the following form:
\[
f(z)=\sum_{n=0}^{\infty} a_{n}\left(z-z_{0}\right)^{n} \quad\text{where} a_{n}=\frac{f^{(n)}\left(z_{0}\right)}{n !}
= {1 \over 2\pi r^n}\int_0^{2\pi} f(z_0 + re^{i\theta})e^{-in\theta} \dtheta
.\]
:::

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


### Exercises

:::{.exercise title="Summation by Parts"}
Setting $A_n \da \sum_{k=1}^n b_k$ and $B_0 \da 0$,
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


:::{.solution}
An inelegant proof: define $A_n \da \sum_{k\leq n} a_k$, use that $a_k = A_k - A_{k-1}$, reindex, and peel a top/bottom term off of each sum to pattern-match.
\

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


:::{.lemma title="Abel's Summation Lemma"}
Given two sequences of real numbers \( \ts{ a_k } , \ts{ b_k } \) which satisfy

1. The sequence of partial sums \( \ts{ A_n } \) is bounded,
2. \( \ts{ b_k } \) is monotonically decreasing, and
3. $b_k \converges{k\to\infty}\too 0$,

then 
\[
\sum_{k\geq 1} a_k b_k < \infty
.\]
:::

:::{.proof title="?"}
Use summation by parts and the Cauchy criterion.

Fix $\eps>0$, suppose $\abs{A_n} \leq M$ is assumed the uniform bound, and choose $M\gg 1$ so that $b_M \leq \eps/2M$.
Then
\[
\norm{ \sum_{m\leq k \leq n} a_k b_k }
=
\norm{ A_nb_n - A_{m-1} b_m + \sum_{m\leq k \leq n-1} A_k (b_k- b_{k-1} ) }
.\]

:::




:::{.theorem title="Abel's Theorem"}
If $\sum_{k=1}^\infty c_k$ converges, then 
\[
\lim_{z\to 1^-} \sum_{k\in \NN} c_k z^k = \sum_{k\in \NN} c_k
.\]

:::


:::{.exercise title="1.20"}
Show that

1. $\sum kz^k$ diverges on $S^1$.
2. $\sum k^{-2} z^k$ converges on $S^1$.
3. $\sum k\inv z^k$ converges on $S^1\sm\ts{1}$ and diverges at $1$.
:::


:::{.remark}
Recall that absolutely convergent implies convergent, but not conversely: $\sum k\inv = \infty$ but $\sum (-1)^k k\inv < \infty$.
This converges because the even (odd) partial sums are monotone increasing/decreasing respectively and in $(0, 1)$, so they converge to a finite number.
Their difference converges to 0, and their common limit is the limit of the sum.
:::





:::{.solution}

1. Use that $\abs{z^k} = 1$ and $\sum c_kz^k < \infty \implies \abs{c_k} \to 0$, but $\abs{kz^k} = \abs{k} \to \infty$ here.
2. Use that absolutely convergent implies convergent, and $\sum \abs{k^{-2} z^k} = \sum \abs{k^{-2}}$ converges by the $p\dash$test.
3. 

:::




![](figures/image_2021-05-17-10-27-21.png)

