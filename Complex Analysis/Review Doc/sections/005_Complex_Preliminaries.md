# Preliminaries

## Complex Arithmetic

:::{.fact title="Complex roots of a number"}
The complex $n$th roots of $z \da r e^{i\theta}$ are given by
\[
\ts{ \omega_k \da r^{1/n} e^{i \qty{ \theta + 2k\pi \over n} } \st 0 \leq k \leq n-1 }
.\]
Note that one root is $r^{1/n}\in \RR$, and the rest are separated by angles of $2\pi/n$.
Mnemonic: 
\[
z = re^{i\theta} = re^{i\qty{\theta + 2k\pi}} \implies z^{1/n} = \cdots
.\]
:::

:::{.fact}
Common trick:
\[
f^{1/n} = e^{{1\over n} \log(f)}
,\]
taking (say) a principal branch of $\log$ given by $\CC \sm (-\infty, 0] \cross 0$.

:::


:::{.fact}
Some computations that come up frequently:
\[
\abs{z \pm w}^2 &= \abs{z}^2 + \abs{w}^z + 2\Re(\bar{w}z) \\
(a+bi)(c+di) = (ac - bd) + (ad + bc)
.\]

:::


## Complex Log

:::{.fact title="Complex Log"}
For $z= r e^{i\theta}\neq 0$, $\theta$ is of the form $\Theta + 2k\pi$ where $\Theta = \Arg z$
:::

:::{.proposition title="Existence of complex log"}
Suppose $\Omega$ is a simply-connected region such that $1\in \Omega, 0\not\in\Omega$.
Then there exists a branch of $F(z) \da \Log(z)$ such that

- $F$ is holomorphic on $\Omega$,
- $e^{F(z)} = z$ for all $z\in \Omega$
- $F(x) = \log(x)$ for $x\in \RR$ in a neighborhood of $1$.
:::

:::{.definition title="Principal branch and exponential"}
Take $\CC$ and delete $\RR^{\leq 0}$ to obtain the **principal branch** of the logarithm, defined as 
\[
\Log(z) \da \log(r) + i\theta && \abs{\theta} < \pi
.\]
Similarly define
\[
z^{\alpha} \da e^{\alpha \Log(z)}
.\]
:::

:::{.theorem title="Existence of log"}
If $f$ is holomorphic and nonvanishing on a simply-connected region $\Omega$, then there exists a holomorphic $G$ on $\Omega$ such that
\[
f(z) = e^{G(z)}
.\]

:::


## Complex Calculus


:::{.remark}
When parameterizing integrals $\int_\gamma f(z)\dz$, parameterize $\gamma$ by $\theta$ and write $z=re^{i\theta}$ so $\dz = ire^{i\theta}\dtheta$.
:::

:::{.warnings}
$f(z) = \sin(z), \cos(z)$ are unbounded on $\CC$!
An easy way to see this: they are nonconstant and entire, thus unbounded by Liouville.

:::

:::{.example title="?"}
You can show $f(z) = \sqrt{z}$ is not holomorphic by showing its integral over $S^1$ is nonzero.
This is a direct computation:
\[
\int_{S^1} z^{1/2} \dz 
&= \int_0^{2\pi} (e^{i\theta})^{1/2} ie^{i\theta} \dtheta \\
&= i \int_0^{2\pi} e^{i3\theta \over 2}\dtheta \\
&= i \qty{2\over 3i} e^{i3\theta \over 2}\evalfrom_{0}^{2\pi} \\
&= {2\over 3}\qty{e^{3\pi i - 1}} \\
&= -{4\over 3}
.\]

Note an issue: a different parameterization yields a different (still nonzero) number
\[
\cdots 
&= \int_{-\pi}^{\pi} (e^{i\theta})^{1/2} ie^{i\theta} \dtheta \\
&= {2\over 3}\qty{ e^{3\pi i \over 2} - e^{-3\pi i \over 2}} \\
&= -{4i\over 3}
.\]
This is these are paths that don't lift to closed loops on the Riemann surface defined by $z\mapsto z^2$.
:::

### Holomorphy and Cauchy-Riemann

:::{.definition title="Analytic"}
A function $f:\Omega \to \CC$ is *analytic* at $z_0\in \Omega$ iff there exists a power series $g(z) = \sum a_n (z-z_0)^n$ with radius of convergence $R>0$ and a neighborhood $U\ni z_0$ such that $f(z) = g(z)$ on $U$.
:::

:::{.definition title="Complex differentiable / holomorphic /entire"}
A function $f: \CC\to \CC$ is **complex differentiable** or **holomorphic** at $z_0$ iff the following limit exists:
\[
\lim_{h\to 0} { f(z_0 + h) - f(h) \over h  } 
.\]
A function that is holomorphic on $\CC$ is said to be **entire**.

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

:::{.proposition title="Complex differentiable implies Cauchy-Riemann"}
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

:::{.proposition title="Polar Cauchy-Riemann equations"}
\[  
\frac{\partial u}{\partial r}=\frac{1}{r} \frac{\partial v}{\partial \theta} \quad \text { and } \quad \frac{1}{r} \frac{\partial u}{\partial \theta}=-\frac{\partial v}{\partial r}
.\]
:::

:::{.proof}
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


:::{.proposition title="Holomorphic functions are continuous."}
$f$ is holomorphic at $z_0$ iff there exists an $a\in \CC$ such that
\[  
f(z_0 + h) - f(z_0) - ah = h \psi(h), \quad \psi(h) \converges{h\to 0}\to 0
.\]
In this case, $a = f'(z_0)$.
:::

\todo[inline]{Prove}



### Delbar and the Laplacian

:::{.definition title="del and delbar operators"}
\[
\del \da \del_z \da {1\over 2}\qty{\del_x - i \del_y}
\quad
\text{ and }
\quad
\delbar
\da \del_{\bar z}
={1\over 2}\qty{ \del_x + i\del_y}
.\]
Moreover, $f' = \del f + \delbar f$.
:::

:::{.proposition title="Holomorphic iff delbar vanishes"}
$f$ is holomorphic at $z_0$ iff $\delbar f(z_0) = 0$:
\[
2\delbar f 
&\da (\del_x + i \del_y) (u+iv) \\
&= u_x + iv_x + iu_y - v_y \\
&= (u_x - v_y) + i(u_y + v_x) \\
&= 0 && \text{by Cauchy-Riemann}
.\]
:::

### Harmonic Functions and the Laplacian

:::{.definition title="Laplacian and Harmonic Functions"}
A real function of two variables $u(x, y)$ is **harmonic** iff it is in the kernel of the Laplacian operator:
\[  
\Delta u \definedas \qty{\dd{^2}{x^2} + \dd{^2}{y^2}}u = 0
.\]
:::

:::{.proposition title="Cauchy-Riemann implies holomorphic"}
If $f = u+iv$ with $u, v\in C^1(\RR)$ satisfying the Cauchy-Riemann equations on $\Omega$, then $f$ is holomorphic on $\Omega$ and 
\[
f'(z) = \del f = {1\over 2}\qty{u_x + iv_x}
.\]
:::

:::{.proposition title="Holomorphic functions have harmonic components"}
If $f(z) = u(x, y) + iv(x, y)$ is holomorphic, then $u, v$ are harmonic.
:::

:::{.proof title="?"}
\envlist

- By CR, 
\[
u_x = v_y && u_y = -v_x
.\]

- Differentiate with respect to $x$: 
\[
u_{xx} = v_{yx} && u_{yx} = -v_{xx}
.\]
- Differentiate with respect to $y$:
\[
u_{xy} = v_{yy} && u_{yy} = -v_{xy}
.\]
- Clairaut's theorem: partials are equal, so
\[
u_{xx} - v_{yx} = 0 \implies u_{xx} + u_{yy} = 0 \\ \\
v_{xx} + u_{yx} = 0 \implies v_{xx} + v_{yy} = 0 \\ \\
.\]



:::


### Exercises

:::{.proposition title="Injectivity Relates to Derivatives"}
If $z_0$ is a zero of $f'$ of order $n$, then $f$ is $(n+1)$-to-one in a neighborhood of $z_0$.
:::

:::{.proof}
?
:::

\todo[inline]{proof}

:::{.exercise title="Zero derivative implies constant"}
Show that if $f' = 0$ on a domain $\Omega$, then $f$ is constant on $\Omega$
:::

:::{.solution}
Write $f = u + iv$, then $0 = 2 f' = u_x + iv_x = u_y - iu_y$, so $\grad u = \grad v = 0$.
Show $f$ is constant along every straight line segment $L$ by computing the directional derivative $\grad u \cdot \vector v = 0$ along $L$ connecting $p, q$.
Then $u(p) = u(q) = a$ some constant, and $v(p) = v(q) = b$, so $f(z) = a+bi$ everywhere.
:::

:::{.exercise title="f and fbar holomorphic implies constant"}
Show that if $f$ and $\bar{f}$ are both holomorphic on a domain $\Omega$, then $f$ is constant on $\Omega$.
:::

:::{.solution}
\envlist

- Strategy: show $f'=0$.
- Write $f = u + iv$. 
  Since $f$ is analytic, it satisfies CR, so 
  \[
  u_x = v_y && u_y = -v_x
  .\]

- Similarly write $\bar f = U + iV$ where $U = u$ and $V = -v$.
  Since $\bar f$ is analytic, it also satisfies CR , so
\[
U_x = V_y && U_y = -V_x \\ \\
\implies u_x = -v_y && u_y = v_x
.\]

- Add the LHS of these two equations to get $2u_x = 0 \implies u_x = 0$.
  Subtract the right-hand side to get $-2v_x = 0 \implies v_x = 0$

- Since $f$ is analytic, it is holomorphic, so $f'$ exists and satisfies $f' = u_x + iv_x$.
  But by above, this is zero.
- By the previous exercise, $f'=0 \implies f$ is constant.
:::

:::{.exercise title="SS 1.13: Constant real/imaginary/magnitude implies constant"}
If $f$ is holomorphic on $\Omega$ and any of the following hold, then $f$ is constant:

1. $\Re(f)$ is constant.
2. $\Im(f)$ is constant.
3. $\abs{f}$ is constant.

:::

:::{.solution}
**Part 3**:

- Write $\abs{f} = c \in \RR$.
- If $c=0$, done, so suppose $c>0$.
- Use $f\bar{f} = \abs{f}^2 = c^2$ to write $\bar{f}=c^2/f$.
- Since $\abs{f(z)} = 0 \iff f(z) = 0$, we have $f\neq 0$ on $\Omega$, so $\bar{f}$ is analytic.
- Similarly $f$ is analytic, and $f,\bar{f}$ analytic implies $f'=0$ implies $f$ is constant. 

:::

\todo[inline]{Finish}

## Power Series

:::{.theorem title="Improved Taylor's Theorem"}
If $f$ is holomorphic on a region $\Omega$ with $\closure{ D_R(z_0)} \subseteq \Omega$, and for every $z\in D_r(z_0)$, $f$ has a power series expansion of the following form:
\[
f(z)=\sum_{n=0}^{\infty} a_{n}\left(z-z_{0}\right)^{n} \quad\text{ where } a_{n}=\frac{f^{(n)}\left(z_{0}\right)}{n !}
= {1 \over 2\pi r^n}\int_0^{2\pi} f(z_0 + re^{i\theta})e^{-in\theta} \dtheta
.\]
:::

:::{.proposition title="Power Series are Smooth"}
Any power series is smooth (and thus holomorphic) on its disc of convergence, and its derivatives can be obtained using term-by-term differentiation:
\[
\dd{}{z} f(z) = \dd{}{z} \sum_{k\geq 0} c_k (z-z_0)^k = \sum_{k\geq 1} kc_k (z-z_0)^k
.\]
Moreover, the coefficients are given by 
\[
c_k = {f^{(n)}(z_0) \over n! }
.\]
:::

:::{.remark}
By an application of the Cauchy integral formula (see S&S 7.1) if $f$ is holomorphic on $D_R(z_0)$ there is a formula for all $k\geq 0$ and all $0<r<R$:
\[
c_k = {1\over 2\pi r^k} \int_0^{2\pi} f(z_0 + re^{i\theta}) e^{-in\theta}\dtheta
.\]
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

:::{.lemma title="Dirichlet's Test"}
Given two sequences of real numbers \( \ts{ a_k } , \ts{ b_k } \) which satisfy

1. The sequence of partial sums \( \ts{ A_n } \) is bounded,
2. $b_k \searrow 0$.

then 
\[
\sum_{k\geq 1} a_k b_k < \infty
.\]
:::

:::{.proof title="?"}

> See <http://www.math.uwaterloo.ca/~krdavids/Comp/Abel.pdf>

Use summation by parts.
For a fixed $\sum a_k b_k$, write 
\[
\sum_{n=1}^m x_n Y_n + \sum_{n=1}^m X_n y_{n+1} = X_m Y_{m+1}
.\]
Set $x_n \da a_n, y_N \da b_n - b_{n-1}$, so $X_n = A_n$ and $Y_n = b_n$ as a telescoping sum.
Importantly, all $y_n$ are negative, so $\abs{y_n} = \abs{b_n - b_{n-1}} = b_{n-1} - b_n$, and moreover $a_n b_n = x_n Y_n$ for all $n$.
We have
\[
\sum_{n\geq 1} a_n b_n 
&= \lim_{N\to\infty} \sum_{n\leq N} x_n Y_n \\
&= \lim_{N\to\infty} \sum_{n\leq N} X_N Y_N - \sum_{n\leq N} X_n y_{n+1} \\
&= - \sum_{n\geq 1} X_n y_{n+1},
\]
where in the last step we've used that 
\[
\abs{X_N} = \abs{A_N}\leq M \implies \abs{X_N Y_{N} } = \abs{X_N} \abs{b_{n+1}} \leq M b_{n+1} \to 0
.\]
So it suffices to bound the latter sum:
\[
\sum_{k\geq n}\abs{ X_k y_{k+1} } 
&\leq M \sum_{k\geq 1} \abs{y_{k+1}}\\
&\leq M \sum_{k\geq 1} b_{k} - b_{k+1} \\
&\leq 2M(b_1 - b_{n+1})\\
&\leq 2M b_1
.\]

:::

:::{.theorem title="Abel's Theorem"}
If $\sum_{k=1}^\infty c_k z^j$ converges on $\abs{z} < 1$ then 
\[
\lim_{z\to 1^-} \sum_{k\in \NN} c_k z^k = \sum_{k\in \NN} c_k
.\]
:::

:::{.lemma title="Abel's Test"}
If $f(z) \da \sum c_k z^k$ is a power series with $c_k \in \RR^{\geq 0}$ and $c_k\decreasesto 0$, then $f$ converges on $S^1$ except possibly at $z=1$.
:::

:::{.example title="application of Abel's theorem"}
What is the value of the alternating harmonic series?
Integrate a geometric series to obtain
\[
\sum {(-1)^k z^k \over n} = \log(z+1) && \abs{z} < 1
.\]
Since $c_k \da (-1)^k/k \decreasesto 0$, this converges at $z=1$, and by Abel's theorem $f(1) = \log(2)$.

:::

:::{.remark}
The converse to Abel's theorem is false: take $f(z) = \sum  (-z)^n = 1/(1+z)$.
Then $f(1) = 1-1+1-\cdots$ diverges at 1, but $1/1+1 = 1/2$.
So the limit $s\da \lim_{x\to 1^-} f(x) 1/2$, but $\sum a_n$ doesn't converge to $s$.
:::

:::{.proposition title="Summation by Parts"}
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

:::{.proof title="?"}
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




:::{.proposition title="?"}
If $f$ is non-constant, then $f'$ is analytic and the zeros of $f'$ are isolated.
If $f,g$ are analytic with $f'=g'$, then $f-g$ is constant.
:::


### Exercises: Series

:::{.exercise title="Application of summation by parts"}
Use summation by parts to show that $\sin(n)/n$ converges.
:::

:::{.exercise title="1.20: Series convergence on the circle"}
Show that

1. $\sum kz^k$ diverges on $S^1$.
2. $\sum k^{-2} z^k$ converges on $S^1$.
3. $\sum k\inv z^k$ converges on $S^1\sm\ts{1}$ and diverges at $1$.
:::

:::{.solution}

1. Use that $\abs{z^k} = 1$ and $\sum c_kz^k < \infty \implies \abs{c_k} \to 0$, but $\abs{kz^k} = \abs{k} \to \infty$ here.
2. Use that absolutely convergent implies convergent, and $\sum \abs{k^{-2} z^k} = \sum \abs{k^{-2}}$ converges by the $p\dash$test.
3. If $z=1$, this is the harmonic series. 
  Otherwise take $a_k = 1/k, b_k = e^{i k \theta}$ where $\theta \in (0, 2\pi)$ is some constant, and apply Dirichlet's test.
  It suffices to bound the partial sums of the $b_k$.
  Recalling that $\sum_{k\leq N} r^k = (1-r^{N+1}) / (1-r)$,
  \[
  \norm{ \sum_{k\leq m} e^{ik\theta } } = \norm{1 - e^{i(m+1)\theta} \over 1 - e^{i\theta}} \leq {2 \over \norm{ 1- e^{i\theta}}} \da M
  ,\]
  which is a constant.
  Here we've used that two points on $S^1$ are at most distance 2 from each other.
:::

:::{.exercise title="Laurent expansions inside and outside of a disc"}
Expand $f(z) = {1\over z(z-1)}$ in both

- $\abs{z} < 1$
- $\abs{z} > 1$


:::

:::{.solution}
\[
{1\over z(z-1)} = -{1\over z}{1 \over 1-z} = -{1\over z}\sum z^k
.\]
and
\[
{1\over z(z-1)} = {1\over z^2(1 - {1\over z})} = {1\over z^2} \sum \qty{1\over z}^k
.\]


:::

:::{.exercise title="Laurent expansions about different points"}
Find the Laurent expansion about $z=0$ and $z=1$ respectively of the following function:
\[
f(z) \da {z+1 \over z(z-1)}
.\]

:::

:::{.solution}
Note: once you see that everything is in terms of powers of $(z-z_0)$, you're essentially done.
For $z=0$:
\[
{z+1 \over z(z-1)}
&= {1\over z} {z+1 \over z-1} \\
&= -{z+1\over z} {1\over 1-z} \\
&= -\qty{1 + {1\over z}}\sum_{k\geq 0} z^k
.\]

For $z=1$:
\[
{z+1 \over z(z-1)}
&= {1\over z-1}\qty{1 + {1\over z} } \\
&= {1\over z-1}\qty{1 + {1\over 1 - (1-z)} } \\
&= {1\over z-1} \qty{1 + \sum_{k\geq 0} (1-z)^k } \\
&= {1\over z-1} \qty{1 + \sum_{k\geq 0} (-1)^k (z-1)^k }
.\]
:::

