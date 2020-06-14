Basics

- If $f$ is continuous, is it necessarily the case that $f'$ is continuous?
- If $f_n \to f$, is it necessarily the case that $f_n'$ converges to $f'$ (or at all)?
- Is it true that the sum of differentiable functions is differentiable?
- Is it true that the limit of integrals equals the integral of the limit?
- Is it true that a limit of continuous functions is continuous?
- Prove that uniform convergence implies pointwise convergence implies a.e. convergence, but none of the implications may be reversed.

Measure Theory

- $\star$: Show that for $E\subseteq \RR^n$, TFAE: 
  1. $E$ is measurable
  2. $E = H\union Z$ here $H$ is $F_\sigma$ and $Z$ is null
  3. $E = V\setminus Z'$ where $V\in G_\delta$ and $Z'$ is null.

- $\star$: Show that if $E\subseteq \RR^n$ is measurable then $m(E) = \sup_{K\subset E\text{ compact}} m(K)$ iff for all $\eps> 0$ there exists a compact $K\subseteq E$ such that $m(K) \geq m(E) - \eps$.

Continuity

- Show that a continuous function on a compact set is uniformly continuous.

Measurability

- Show that $f=0$ a.e. iff $\int_E f = 0$ for every measurable set $E$.
- $\star$: Show that cylinder functions are measurable, i.e. if $f$ is measurable on $\RR^s$, then $F(x, y) \definedas f(x)$ is measurable on $\RR^s\cross \RR^t$ for any $t$.

Integrability

- $\star$: Prove that the Lebesgue integral is translation invariant, i.e. if $\tau_h(x) = x+h$ then $\int \tau_h f = \int f$.
- $\star$: Prove that the Lebesgue integral is dilation invariant, i.e. if $f_\delta(x) = {f({x\over \delta}) \over \delta^n}$ then $\int f_\delta = \int f$.
- $\star$: Prove continuity in $L^1$, i.e.
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
- Show that if $f\in C^1$ then $f$ is equal to its Fourier series.

Lp

- Show that if $E\subseteq \RR^n$ is measurable with $\mu(E) < \infty$ and $f\in L^p(X)$ then $\norm{f}_{L^p(X)} \coverges{p\to\infty}\to \norm{f}_\infty$.
- Is it true that the converse to the DCT holds? 
  I.e. if $\int f_n \to \int f$, is there a $g\in L^p$ such that $f_n < g$ a.e. for every $n$?
- Prove continuity in $L^p$: If $f$ is uniformly continuous then $\norm{\tau_h f - f}_p \to 0$ as $h\to 0$ for all $p$.
