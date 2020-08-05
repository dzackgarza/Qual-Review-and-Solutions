# Integrals and Cauchy's Theorem (8155d)


## 5

Show that there is no sequence of polynomials converging uniformly to $f(z) = 1/z$ on $S^1$.

Solution

- By Cauchy's integral formula, $\int_{S^1} f = 2\pi i$
- If $p_j$ is any polynomial, then $p_j$ is holomorphic in $\DD$, so $\int_{S^1} p_j = 0$.
- Contradiction: compact sets in $\CC$ are bounded, so 
  \begin{align*}
  \abs{\int f - \int p_j} \leq \int \abs{p_j - f} \leq \int \norm{p_j - f}_\infty  = \norm{p_j - f}_\infty \int_{S^1} 1 \,dz = \norm{p_j-f}_\infty \cdot 2\pi \to 0
  \end{align*}
  which forces $\int f = \int p_j = 0$.

## 9

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

## 10

Suppose $f:\CC\to\CC$ is entire and bounded, and use Cauchy's theorem to prove that $f' \equiv 0$ and thus $f$ is constant.

Solution

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


