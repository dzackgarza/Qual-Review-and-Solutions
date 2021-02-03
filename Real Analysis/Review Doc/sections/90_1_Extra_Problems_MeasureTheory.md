# Extra Problems: Measure Theory

## Greatest Hits

- $\star$: Show that for $E\subseteq \RR^n$, TFAE: 
  1. $E$ is measurable
  2. $E = H\union Z$ here $H$ is $F_\sigma$ and $Z$ is null
  3. $E = V\setminus Z'$ where $V\in G_\delta$ and $Z'$ is null.
- $\star$: Show that if $E\subseteq \RR^n$ is measurable then $m(E) = \sup \theset{ m(K) \suchthat K\subset E\text{ compact}}$ iff for all $\eps> 0$ there exists a compact $K\subseteq E$ such that $m(K) \geq m(E) - \eps$.
- $\star$: Show that cylinder functions are measurable, i.e. if $f$ is measurable on $\RR^s$, then $F(x, y) \definedas f(x)$ is measurable on $\RR^s\cross \RR^t$ for any $t$.
- $\star$: Prove that the Lebesgue integral is translation invariant, i.e. if $\tau_h(x) = x+h$ then $\int \tau_h f = \int f$.
- $\star$: Prove that the Lebesgue integral is dilation invariant, i.e. if $f_\delta(x) = {f({x\over \delta}) \over \delta^n}$ then $\int f_\delta = \int f$.
- $\star$: Prove continuity in $L^1$, i.e.
  \[
  f \in L^{1} \Longrightarrow \lim _{h \rightarrow 0} \int|f(x+h)-f(x)|=0
  .\]
- $\star$: Show that $$f,g \in L^1 \implies f\ast g \in L^1 \qtext{and} \norm{f\ast g}_1 \leq \norm{f}_1 \norm{g}_1.$$

- $\star$: Show that if $X\subseteq \RR$ with $\mu(X) < \infty$ then
\[  
\norm{f}_p \converges{p\to\infty}\to \norm{f}_\infty
.\]



## By Topic

### Topology

- Show that every compact set is closed and bounded.
- Show that if a subset of a metric space is complete and totally bounded, then it is compact.
- Show that if $K$ is compact and $F$ is closed with $K, F$ disjoint then $\dist(K, F) > 0$.

### Continuity

- Show that a continuous function on a compact set is uniformly continuous.

### Differentiation

- Show that if $f\in C^1(\RR)$ and both $\lim_{x\to \infty} f(x)$ and $\lim_{x\to \infty} f'(x)$ exist, then $\lim_{x\to\infty} f'(x)$ must be zero.

### Advanced Limitology

- If $f$ is continuous, is it necessarily the case that $f'$ is continuous?
- If $f_n \to f$, is it necessarily the case that $f_n'$ converges to $f'$ (or at all)?
- Is it true that the sum of differentiable functions is differentiable?
- Is it true that the limit of integrals equals the integral of the limit?
- Is it true that a limit of continuous functions is continuous?
- Show that a subset of a metric space is closed iff it is complete. 
- Show that if $m(E) < \infty$ and $f_n\to f$ uniformly, then $\lim \int_E f_n = \int_E f$.


Uniform Convergence

- Show that a uniform limit of bounded functions is bounded.
- Show that a uniform limit of continuous function is continuous.
  - I.e. if $f_n\to f$ uniformly with each $f_n$ continuous then $f$ is continuous.
- Show that if $f_n\to f$ pointwise, $f_n' \to g$ uniformly for some $f, g$, then $f$ is differentiable and $g = f'$.
- Prove that uniform convergence implies pointwise convergence implies a.e. convergence, but none of the implications may be reversed.
- Show that $\sum {x^n \over n!}$ converges uniformly on any compact subset of $\RR$. 

Measure Theory


- Show that continuity of measure from above/below holds for outer measures.

- Show that a countable union of null sets is null.

Measurability

- Show that $f=0$ a.e. iff $\int_E f = 0$ for every measurable set $E$.

Integrability

- Show that if $f$ is a measurable function, then $f=0$ a.e. iff $\int f = 0$.
- Show that a bounded function is Lebesgue integrable iff it is measurable.
- Show that simple functions are dense in $L^1$.
- Show that step functions are dense in $L^1$.
- Show that smooth compactly supported functions are dense in $L^1$.

Convergence

- Prove Fatou's lemma using the Monotone Convergence Theorem.
- Show that if $\theset{f_n}$ is in $L^1$ and $\sum \int \abs{f_n} < \infty$ then $\sum f_n$ converges to an $L^1$ function and 
  $$\int \sum f_n = \sum \int f_n.$$

Convolution

- Show that if $f\in L^1$ and $g$ is bounded, then  $f\ast g$ is bounded and uniformly continuous.
- If $f, g$ are compactly supported, is it necessarily the case that $f\ast g$ is compactly supported?
- Show that under any of the following assumptions, $f\ast g$ vanishes at infinity:
  - $f, g\in L^1$ are both bounded.
  - $f, g\in L^1$ with just $g$ bounded. 
  - $f, g$ smooth and compactly supported (and in fact $f\ast g$ is smooth)
  - $f\in L^1$ and $g$ smooth and compactly supported (and in fact $f\ast g$ is smooth)
- Show that if $f\in L^1$ and $g'$ exists with $\dd{g}{x_i}$ all bounded, then $$\dd{}{x_i}(f\ast g) = f \ast \dd{g}{x_i}$$

Fourier Analysis

- Show that if $f\in L^1$ then $\hat f$ is bounded and uniformly continuous. 
- Is it the case that $f\in L^1$ implies $\hat f\in L^1$?
- Show that if $f, \hat f \in L^1$ then $f$ is bounded, uniformly continuous, and vanishes at infinity.
  - Show that this is not true for arbitrary $L^1$ functions.
- Show that if $f\in L^1$ and $\hat f = 0$ almost everywhere then $f = 0$ almost everywhere.
  - Prove that $\hat f = \hat g$ implies that $f=g$ a.e.
- Show that if $f, g \in L^1$ then $$\int \hat f g = \int f\hat g.$$
  - Give an example showing that this fails if $g$ is not bounded.
- Show that if $f\in C^1$ then $f$ is equal to its Fourier *series*.

Approximate Identities

- Show that if $\phi$ is an approximate identity, then $$\norm{f\ast \phi_t - f}_1 \converges{t\to 0}\to 0.$$
  - Show that if additionally $\abs{\phi(x)} \leq c(1 + \abs{x})^{-n-\eps}$ for some $c,\eps>0$, then this converges is almost everywhere.
- Show that is $f$ is bounded and uniformly continuous and $\phi_t$ is an approximation to the identity, then $f\ast \phi_t$ uniformly converges to $f$.

$L^p$ Spaces

- Show that if $E\subseteq \RR^n$ is measurable with $\mu(E) < \infty$ and $f\in L^p(X)$ then $$\norm{f}_{L^p(X)} \converges{p\to\infty}\to \norm{f}_\infty.$$
- Is it true that the converse to the DCT holds? 
  I.e. if $\int f_n \to \int f$, is there a $g\in L^p$ such that $f_n < g$ a.e. for every $n$?
- Prove continuity in $L^p$: If $f$ is uniformly continuous then for all $p$, $$\norm{\tau_h f - f}_p \converges{h\to 0}\to 0.$$ 
- Prove the following inclusions of $L^p$ spaces for $m(X) < \infty$:
\[
L^\infty(X) &\subset L^2(X) \subset L^1(X) \\
\ell^2(\ZZ) &\subset \ell^1(\ZZ) \subset \ell^\infty(\ZZ)
.\]


### Unsorted


:::{.proposition title="Volumes of Rectangles"}
If $\ts{R_j} \covers R$ is a covering of $R$ by rectangles,
\[
R = \overset{\circ}{\Disjoint_{j}} R_j &\implies \abs R = \sum \abs R_j \\
R \subseteq \Union_j R_j &\implies \abs R \leq \sum \abs R_j
.\]

:::

- Show that any disjoint intervals is countable.
- Show that every open $U \subseteq \RR$ is a countable union of disjoint open intervals.
- Show that every open $U \subseteq \RR^n$ is a countable union of *almost* disjoint closed cubes.
- Show that that Cantor middle-thirds set is compact, totally disconnected, and perfect, with outer measure zero.
- Prove the Borel-Cantelli lemma.

## Rectangles

## Outer Measure

## Lebesgue Measurable Sets

## Lebesgue Measurable Functions


