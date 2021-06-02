# Integrals and Cauchy's Theorem (8155d)

## 2 $\work$

State and prove Green's Theorem for rectangles.
Use this to prove Cauchy's Theorem for functions that are analytic in a rectangle.


## 3 $\work$

Suppose $\theset{f_n}_{n\in \NN}$ is a sequence of analytic functions on $\DD \definedas \theset{z\in \CC \suchthat \abs{z} < 1}$.

Show that if $f_n\to g$ for some $g: \DD \to \CC$ uniformly on every compact $K\subset \DD$, then $g$ is analytic on $\DD$.


## 4 $\work$

Suppose $\theset{f_n}_{n\in \NN}$ is a sequence of entire functions where

- $f_n \to g$ pointwise for some $g:\CC\to\CC$.
- On every line segment in $\CC$, $f_n \to g$ uniformly.

Show that 

- $g$ is entire, and
- $f_n\to g$ uniformly on every compact subset of $\CC$.

## 5 $\done$

Prove that there is no sequence of polynomials that uniformly converge to $f(z) = {1\over z}$ on $S^1$.


:::{.concept}
\envlist

- Uniform limit of holomorphic function is holomorphic

:::

:::{.solution}

- By Cauchy's integral formula, $\int_{S^1} f = 2\pi i$
- If $p_j$ is any polynomial, then $p_j$ is holomorphic in $\DD$, so $\int_{S^1} p_j = 0$.
- Contradiction: compact sets in $\CC$ are bounded, so 
  \[
  \abs{\int f - \int p_j} \leq \int \abs{p_j - f} \leq \int \norm{p_j - f}_\infty  = \norm{p_j - f}_\infty \int_{S^1} 1 \,dz = \norm{p_j-f}_\infty \cdot 2\pi \to 0
  \]
  which forces $\int f = \int p_j = 0$.
:::

## 6 $\work$

Suppose that $f: \RR\to\RR$ is a continuous function that vanishes outside of some finite interval.
For each $z\in \CC$, define
\[
g(z) = \int_{-\infty}^\infty f(t) e^{-izt} \,dt
.\]

Show that $g$ is entire.


## 7 $\work$

Suppose $f: \CC\to \CC$ is entire and
\[
\abs{f(z)} \leq \abs{z}^{1\over 2} \quad\text{ when } \abs{z} > 10
.\]

Prove that $f$ is constant.

## 8 $\work$

Let $\gamma$ be a smooth curve joining two distinct points $a, b\in \CC$.

Prove that the function
\[
f(z) \definedas \int_\gamma {g(w) \over w-z} \,dw
\]
is analytic in $\CC\setminus\gamma$.

## 9 $\done$
Suppose that $f: \CC\to\CC$ is continuous everywhere and analytic on $\CC\setminus \RR$ and prove that $f$ is entire.

\todo[inline]{Something missing?}
:::{.solution}
\hfill
:::{.concept}
\hfill

:::
- Note $f$ is continuous on $\CC$ since analytic implies continuous ($f$ equals its power series, where the partials sums uniformly converge to it, and uniform limit of continuous is continuous).
- Strategy: take $D$ a disc centered at a point $x\in \RR$, show $f$ is holomorphic in $D$ by Morera's theorem.
- Let $\Delta \subset D$ be a triangle in $D$.
- Case 1: If $\Delta \intersect \RR = 0$, then $f$ is holomorphic on $\Delta$ and $\int_\Delta f = 0$.
- Case 2: one side or vertex of $\Delta$ intersects $\RR$, and wlog the rest of $\Delta$ is in $\HH^+$.
  - Then let $\Delta_\eps$ be the perturbation $\Delta + i\eps = \theset{z+ i\eps \suchthat z\in \Delta}$; then $\Delta_\eps \intersect \RR = 0$ and $\int_{\Delta_\eps} f = 0$.
  - Now let $\eps\to 0$ and conclude by continuity of $f$ (???)
    - We want
    \begin{align*}
    \int_{\Delta_\eps} f = \int_a^b f(\gamma_\eps(t)) \gamma_\eps'(t)\,dt \converges{\eps\to 0}\to \int_a^b f(\gamma(t)) \gamma_\eps'(t)\,dt =\int_{\Delta}  f
    \end{align*}
    where $\gamma_\eps, \gamma$ are curves parametrizing $\Delta_\eps, \Delta$ respectively.
    - Since $\gamma, \gamma_\eps$ are closed and bounded in $\CC$, they are compact subsets. Thus it suffices to show that $f(\gamma_\eps(t)) \gamma_\eps'(t)$ converges uniformly to $f(\gamma(t))\gamma'(t)$.
    -  ??
- Case 3: $\Delta$ intersects both $\HH^+$ and $\HH^-$.
  - Break into smaller triangles, each of which falls into one of the previous two cases.

:::


## 10 $\done$
Prove Liouville's theorem: suppose $f:\CC\to\CC$ is entire and bounded. 
Use Cauchy's formula to prove that $f'\equiv 0$ and hence $f$ is constant.

:::{.solution}
\hfill
:::{.concept}
\hfill

:::
- Suffices to prove $f' = 0$ because $\CC$ is connected (see Stein Ch 1, 3.4)
  - Idea: Fix $w_0$, show $f(w) = f(w_0)$ for any $w\neq w_0$
  - Connected = Path connected in $\CC$, so take $\gamma$ joining $w$ to $w_0$.
  - $f$ is a primitive for $f'$, and $\int_\gamma f' = f(w) - f(w_0)$, but $f'=0$.
- Fix $z_0\in \CC$, let $B$ be the bound for $f$, so $\abs{f(z)} \leq B$ for all $z$.
- Apply Cauchy inequalities: if $f$ is holomorphic on $U\supset \bar D_R(z_0)$ then setting $\norm{f}_C \definedas \sup_{z\in C} \abs{f(z)}$,
  \begin{align*}
  \abs{f^{(n)} (z_0)} \leq {n! \norm{f}_C \over R^n}
  .\end{align*}
  - Yields $\abs{ f'(z_0) } \leq B/R$
- Take $R\to \infty$, QED.
:::


# Extra


## ?
Assume $f$ is continuous in the region:
$0< |z-a| \leq R, \; 0 \leq \arg(z-a) \leq \beta_0$
($0 < \beta_0 \leq 2 \pi$) and the limit
$\displaystyle \lim_{z \rightarrow a} (z-a) f(z) = A$ exists. Show that
$$\lim_{r \rightarrow 0} \int_{\gamma_r} f(z) dz  = i A \beta_0 \; , \; \;$$
where
$\gamma_r : = \{ z \; | \; z = a + r e^{it}, \; 0 \leq  t \leq \beta_0 \}.$

### Tie's Extra Questions: Fall 2009

Let $f$ be a continuous function in the region
$$D=\{z \suchthat  \abs{z}>R, 0\leq \arg z\leq \theta\}\quad\text{where}\quad
1\leq \theta \leq 2\pi.$$ If there exists $k$ such that
$\displaystyle{\lim_{z\to\infty} zf(z)=k}$ for $z$ in the region
$D$.
Show that $$\lim_{R'\to\infty} \int_{L} f(z) dz=i\theta k,$$
where $L$ is the part of the circle $|z|=R'$ which lies in the
region $D$.

### Spring 2020 HW 2 #  2.6.5

Suppose $f\in C_\CC^1(\Omega)$ and $T\subset \Omega$ is a triangle with $T^\circ \subset \Omega$.
1. Apply Green's theorem to show that $\int_T f(z) ~dz = 0$.

2. Assume that $f'$ is continuous and prove Goursat's theorem.

> Hint: Green's theorem states
\[
\int_{T} F d x+G d y=\int_{T^\circ}\left(\frac{\partial G}{\partial x}-\frac{\partial F}{\partial y}\right) d x d y
.\]

### Spring 2020 HW 2 #  2.6.6

Suppose that $f$ is holomorphic on a punctured open set $\Omega\setminus\theset{w_0}$ and let $T\subset \Omega$ be a triangle containing $w_0$.
Prove that if $f$ is bounded near $w_0$, then $\int_T f(z) ~dz = 0$.


### Spring 2020 HW 2 #  2.6.7

Suppose $f: \DD \to \CC$ is holomorphic and let $d \definedas \sup_{z, w\in \DD}\abs{f(z) - f(w)}$ be the diameter of the image of $f$.
Show that $2 \abs{f'(0)} \leq d$, and that equality holds iff $f$ is linear, so $f(z) = a_1 z + a_2$.

> Hint: 
\[
2f'(0) = \frac{1}{2\pi i} \int_{\abs \xi = r} \frac{ f(\xi) - f(-\xi)  }{\xi^2} ~d\xi
\]
whenever $0<r<1$.


### Spring 2020 HW 2 #  2.6.8

Suppose that $f$ is holomorphic on the strip $S = \theset{x+iy \suchthat x\in \RR,~ -1<y<1}$ with $\abs{f(z)} \leq A \qty{1 + \abs z}^\nu$ for $\nu$ some fixed real number.
Show that for all $z\in S$, for each integer $n\geq 0$ there exists an $A_n \geq 0$ such that $\abs{f^{(n)}(x)} \leq A_n (1 + \abs x)^\nu$ for all $x\in \RR$.

> Hint: Use the Cauchy inequalities.

### Spring 2020 HW 2 #  2.6.9

Let $\Omega \subset \CC$ be open and bounded and $\phi: \Omega \to \Omega$ holomorphic.
Prove that if there exists a point $z_0 \in \Omega$ such that $\phi(z_0) = z_0$ and $\phi'(z_0) = 1$, then $\phi$ is linear.

> Hint: assume $z_0 = 0$ (explain why this can be done) and write $\phi(z)  = z + a_n z^n + O(z^{n+1})$ near $0$.
  Let $\phi_k = \phi \circ \phi \circ \cdots \circ \phi$ and prove that $\phi_k(z) = z + ka_nz^n  + O(z^{n+1})$.
  Apply Cauchy's inequalities and let $k\to \infty$ to conclude.

### Spring 2020 HW 2 #  6
Show by example that there exists a function $f(z)$ that is holomorphic on $\theset{z\in \CC \suchthat 0 < \abs{z} < 1}$ and for all $r<1$,
\[
\int_{\abs z = r} f(z) \, dz = 0
,\]
but $f$ is not holomorphic at $z=0$.

### Spring 2020 HW 2 #  7
Let $f$ be analytic on a region $R$ and suppose $f'(z_0) \neq 0$ for some $z_0 \in R$.
Show that if $C$ is a circle of sufficiently small radius centered at $z_0$, then 
\[
\frac{2 \pi i}{f^{\prime}\left(z_{0}\right)}=\int_{C} \frac{d z}{f(z)-f\left(z_{0}\right)}
.\]

> Hint: use the inverse function theorem.

### Spring 2020 HW 2 #  8
Assume two functions $u, b: \RR^2 \to \RR$ have continuous partial derivatives at $(x_0 ,y_0)$.
Show that $f \definedas u + iv$ has derivative $f'(z_0)$ at $z_0 = x_0 + iy_0$ if and only if
\[
\lim _{r \rightarrow 0} \frac{1}{\pi r^{2}} \int_{\left|z-z_{0}\right|=r} f(z) d z=0
.\]


### Spring 2020 HW 2 #  9 (Cauchy's Formula for Exterior Regions)

Let $\gamma$ be a piecewise smooth simple closed curve with interior $\Omega_1$ and exterior $\Omega_2$.
Assume $f'$ exists in an open set containing $\gamma$ and $\Omega_2$ with $\lim_{z\to \infty} f(z) = A$.
Show that
\[
\frac{1}{2 \pi i} \int_{\gamma} \frac{f(\xi)}{\xi-z} d \xi=\left\{\begin{array}{ll}
A, & \text { if } z \in \Omega_{1} \\
-f(z)+A, & \text { if } z \in \Omega_{2}
\end{array}\right.
.\]

### Spring 2020 HW 2 #  10
Let $f(z)$ be bounded and analytic in $\CC$.
Let $a\neq b$ be any fixed complex numbers.
Show that the following limit exists:
\[
\lim_{R\to \infty} \int_{\abs z = R} {f(z) \over (z-a)(z-b)} \,dz
.\]

Use this to show that $f(z)$ must be constant.


### Spring 2020 HW 2 #  11
Suppose $f(z)$ is entire and 
\[
\lim_{z\to\infty} {f(z) \over z} = 0
.\]

Show that $f(z)$ is a constant.

### Spring 2020 HW 2 #  12
Let $f$ be analytic in a domain $D$ and $\gamma$ be a closed curve in $D$.
For any $z_0\in D$ not on $\gamma$, show that
\[
\int_{\gamma} \frac{f^{\prime}(z)}{\left(z-z_{0}\right)} d z=\int_{\gamma} \frac{f(z)}{\left(z-z_{0}\right)^{2}} d z
.\]
Give a generalization of this result.


### Spring 2020 HW 2 #  13

Compute
\[
\int_{\abs z = 1} \qty{z + {1\over z}}^{2n} {dz \over z}
\]
and use it to show that
\[
\int_0^{2\pi} \cos^{2n}(\theta) \, d\theta = 2\pi \qty{1\cdot 3 \cdot 5 \cdots (2n-1) \over 2 \cdot 4 \cdot 6 \cdots (2n)}
.\]

### Entire and $O$ of polynomial implies polynomial $\done$

:::{.problem title="?"}
Let $f(z)$ be entire and assume that $\abs{f(z)} \leq M |z|^2$ outside of some disk for some constant $M$. 
Show that $f(z)$ is a polynomial in $z$ of degree $\leq 2$.
:::


:::{.solution}
\envlist

- Prove a more general statement: if $\abs{f(z)} \leq M\abs{z}^n$, then $f$ is a polynomial of degree at most $n$.
- Since $f$ is entire, it is analytic everywhere, so $f(z) = \sum_{k\geq 0}c_k z^k$ where $c_k = f^{(k)}(0)/n!$ is given by the coefficient of its Taylor expansion about $z=0$.
- Applying Cauchy's estimate, on a circle of radius $R$, 
\[
\abs{f^{(k)}(0)} \leq { \sup_{\gamma}\abs{f(z)} n! \over R^k} \leq {M\abs{z}^n n! \over R^k} = {M R^n n! \over R^k} 
.\]

- So for $k \geq n+1$, this goes to zero as $R\to \infty$, so $\abs{f^{k}(0)} = 0$ for all such $k$.
- But then $f$ is a power series annihilated by taking $n+1$ derivatives, so it is a polynomial of degree at most $n$.
:::


## Uniform sequence implies uniform derivatives $\done$

:::{.problem title="?"}
Let $a_n(z)$ be an analytic sequence in a domain $D$ such that
$\displaystyle \sum_{n=0}^\infty |a_n(z)|$ converges uniformly on
bounded and closed sub-regions of $D$. 
Show that $\displaystyle \sum_{n=0}^\infty |a'_n(z)|$ converges uniformly on bounded and closed sub-regions of $D$.
:::

:::{.solution}
\envlist

- Show a stronger statement: if $f_n\to f$ uniformly with each $f_n$ holomorphic on every compact subset of $D$ then $f_n'\to f'$ on every compact subset of $D$.

- We have $\norm{f_n-f}_{\infty, D}\to 0$, the sup norm on $D$.
- Pick a $\gamma$ in $\interior{D}$

:::


