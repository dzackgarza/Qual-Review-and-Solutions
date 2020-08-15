# Integrals and Cauchy's Theorem (8155d)

> Some interesting problems: 3, 4, 9, 10.

## 1 $\work$

Suppose $f, g: [0, 1] \to \RR$ where $f$ is Riemann integrable and for $x, y\in [0, 1]$,
\[
\abs{g(x) - g(y)} \leq \abs{f(x) - f(y)}
.\]

Prove that $g$ is Riemann integrable.

## 2 $\work$

State and prove Green's Theorem for rectangles.

Then use it to prove Cauchy's Theory for functions that are analytic in a rectangle.


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

:::{.solution}
\hfill
:::{.concept}
\hfill

:::

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

