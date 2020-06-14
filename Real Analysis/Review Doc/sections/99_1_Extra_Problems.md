Measure Theory

- $\star$: Show that for $E\subseteq \RR^n$, TFAE: 
  1. $E$ is measurable
  2. $E = H\union Z$ here $H$ is $F_\sigma$ and $Z$ is null
  3. $E = V\etminus Z'$ where $V\in G_\delta$ and $Z'$ is null.

Continuity

- Show that a continuous function on a compact set is uniformly continuous.

Measurability

- Show that $f=0$ a.e. iff $\int_E f = 0$ for every measurable set $E$.

Integrability

- $\star$: Prove that the Lebesgue integral is translation invariant.
- Show that
  \begin{align*}
  f \in L^{1} \Longrightarrow \lim _{h \rightarrow 0} \int|f(x+h)-f(x)|=0
  .\end{align*}
- Show that a bounded function is Lebesgue integrable iff it is measurable.
- Show that simple functions are dense in $L^1$.
- Show that step functions are dense in $L^1$.
- Show that smooth compactly supposed functions are dense in $L^1$.
- 

Fourier Analysis

- Show that if $f\in L^1$ then $\hat f$ is bounded and uniformly continuous. 
- Is it the case that $f\in L^1$ implies $\hat f\in L^1$?
- Show that if $f, \hat f \in L^1$ then $f$ is bounded, continuous, and vanishes at infinity.
  - Show that this is not true for arbitrary $L^1$ functions.
- Show that if $f\in L^1$ and $\hat f = 0$ a.e. then $f=0$ a.e.
  - Prove that $\hat f = \hat g$ implies that $f=g$ a.e.
- Show that if $f, g \in L^1$ then $\int \hat f g = \int f\hat g$.
- Is it the case that $f, g\in C_c$ implies that $f\ast g \in C_c$?
- $\star$: show that if $f, g\in L^1$, then $\norm{f\ast g}_{1} \leq \norm{f}_1 \norm{g}_1$.
- Show that if $f,g \in L^1$ and $g$ is bounded, then $\lim_{\abs x\to\infty}(f\ast g)(x) = 0$.
  - Give an example showing that this fails if $g$ is not bounded.
- Show that if $f\in L^1$ and $g\in C_c^\infty$ then $f\ast g$ is smooth and $f\ast g$ vanishes at infinity.
