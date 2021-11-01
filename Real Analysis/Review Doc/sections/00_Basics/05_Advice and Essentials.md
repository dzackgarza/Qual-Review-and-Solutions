---
order: 5
---

# Advice and Essentials 

- General advice: try swapping the orders of limits, sums, integrals, etc.
- Limits:
  - Take the $\limsup$ or $\liminf$, which always exist, and aim for an inequality like
  \[  
  c \leq \liminf a_n \leq \limsup a_n \leq c
  .\]
  - $\lim f_n = \limsup f_n = \liminf f_n$ iff the limit exists, so to show some $g$ is a limit, show
  \[  
\limsup f_n \leq g \leq \liminf f_n \qquad (\implies g = \lim f) 
  .\]
  - A  limit does *not* exist if $\liminf a_n > \limsup a_n$.

- Sequences and Series
  - If $f_n$ has a global maximum (computed using $f_n'$ and the first derivative test) $M_n \to 0$, then $f_n \to 0$ uniformly.
  - For a fixed $x$, if $f = \sum f_n$ converges *uniformly* on some $B_r(x)$ and each $f_n$ is continuous at $x$, then $f$ is also continuous at $x$ .

- Equalities
  - Split into upper and lower bounds:
  \[  
  a=b \iff a\leq b \text{ and }  a\geq b
  .\]
  - Use an epsilon of room:
  \[  
  \qty{ \forall \epsilon, \,\,a < b + \eps} \implies a\leq b 
  .\]
  - Showing something is zero:
  \[  
  \qty{ \forall \epsilon, \,\, \norm{a} < \eps} \implies a = 0
  .\]

- Continuity / differentiability: 
  - Show it holds on $[-M, M]$ for all $M$ to get it to hold on $\RR$.
  - In higher dimensions: intersect with a ball $B_R(\vector 0)\subset \RR^n$ about zero.

- Simplifications:
  - To show something for a measurable set, show it for bounded/compact/elementary sets and use approximations in measure.
  - To show something for an arbitrary function, try various dense classes of functions: 
    continuous, bounded, compactly supported, simple, indicator functions, etc and use approximations in norm.
  - Replace $\eps\to 0$ with an arbitrary countable sequence ($x_n \to 0$)
    - Note: this is not always helpful, since you now have to predicate over all such sequences.

- Integrals
  - Calculus techniques: Taylor series, IVT, MVT, etc.
  - Break up $\RR^n = \theset{\abs{x} \leq 1} \coprod \theset{\abs{x} > 1}$.
    - Or break integration region into disjoint annuli.
  - For pairs of functions $f, g$: break up into $\theset{f>g} \disjoint \theset{f=g} \disjoint \theset{f< g}$.
  - Tail estimates!
  - Most of what works for integrals will work for sums.

- Measure theory:

  - Always consider bounded sets, and if $E$ is unbounded write $E = \Union_{n\geq 0} \qty{ B_{n}(0) \intersect E}$ and use countable subadditivity or continuity of measure.

  - $F_\sigma$ sets are Borel, so establish something for Borel sets and use this to extend it to Lebesgue.

  - $s = \inf\theset{x\in X} \implies$ for every $\varepsilon$ there is an $x\in X$ such that $x \leq s + \varepsilon$ or $x\in [s, s+\eps]$.

- Useful facts about continuous compactly supported ($C_c^0(\RR)$) functions:
  - Uniformly continuous
  - Bounded almost everywhere

- Pass to a subsequence!

- Add and subtract a thing. 
  Eg, $\norm{T_nx_n - Tx} = \norm{T_nx_n - Tx_n + Tx_n - Tx}$.

- $(a_k) \in \ell^2(\ZZ)$ is much weaker than $(a_k) \in \ell^1(\ZZ)$.
- Littlewood's principles:
  - Measurable sets are almost finite unions of intervals,
  - Measurable functions are almost continuous,
  - Pointwise convergent sequences of measurable functions are almost uniformly convergent.

- $L^p$ spaces shrink as $p\nearrow \infty$ (by Holder).

- Every Borel is $F_\sigma$ up to a null set.

# The Absolute Essentials

:::{.proposition title="Convergent Sums Have Small Tails"}
$$\sum a_n < \infty \implies a_n \to 0 \qtext{and} \sum_{k=N}^\infty a_n \converges{N\to\infty}\to 0$$
:::

:::{.theorem title="Uniform Limit Theorem"}
If $f_n\to f$ pointwise and uniformly with each $f_n$ continuous, then $f$ is continuous. [^uniform_limit_is_cts]

[^uniform_limit_is_cts]: Slogan: a uniform limit of continuous functions is continuous.

:::

:::{.proof}
\envlist
- Follows from an $\varepsilon/3$ argument: 
  \[  
  \abs{F(x) - F(y} \leq 
  \abs{F(x) - F_N(x)} + \abs{F_N(x) - F_N(y)} + \abs{F_N(y) - F(y)} 
  \leq \eps \to 0
  .\]

  - The first and last $\eps/3$ come from uniform convergence of $F_N\to F$.
  - The middle $\eps/3$ comes from continuity of each $F_N$.
- So just need to choose $N$ large enough and $\delta$ small enough to make all 3 $\varepsilon$ bounds hold.
:::

:::{.proposition title="Uniform Limits Commute with Integrals"}
If $f_n \to f$ uniformly, then $\int f_n = \int f$.
:::

:::{.proposition title="Weak $M\dash$Test"}
If $f_n(x) \leq M_n$ **for a fixed $x$** where $\sum M_n < \infty$, then the series $f(x) = \sum f_n(x)$ converges pointwise.[^note_about_pointwise_convergence]

[^note_about_pointwise_convergence]: Note that this is only pointwise convergence of $f$, whereas the full $M\dash$test gives uniform convergence.

:::

:::{.proposition title="The Weierstrass $M\dash$Test"}
If $\sup_{x\in A} \abs{f_n(x)} \leq M_n$ for each $n$ where $\sum M_n < \infty$, then $\sum_{n=1}^\infty f_n(x)$ converges uniformly and absolutely on $A$.
[^m_test_suffices]
Conversely, if $\sum f_n$ converges uniformly on $A$ then $\sup_{x\in A} \abs{f_n(x)} \to 0$. 

[^m_test_suffices]: 
It suffices to show $\abs{f_n(x)} \leq M_n$ for some $M_n$ not depending on $x$.

:::

:::{.proposition title="Borel Characterization of Measurable Sets"}
If $E$ is Lebesgue measurable, then $E = H \disjoint N$ where $H \in F_\sigma$ and $N$ is null.
:::

:::{.proof title="of Borel characterization"}
For every $\frac 1 n$ there exists a closed set $K_{n} \subset E$ such that $m(E\setminus K_{n}) \leq \frac 1 n$.
Take $K = \union K_{n}$, wlog $K_{n} \nearrow K$ so $m(K) = \lim m(K_{n}) = m(E)$.
Take $N\da E\setminus K$, then $m(N) = 0$.
:::

:::{.theorem title="Measurable sets can be approximated by open/closed/compact sets."}
Suppose $E$ is measurable; then for every $\eps>0$,

1. There exists an open $O\supset E$ with $m(O\setminus E) < \eps$
2. There exists a closed $F\subset E$ with $m(E\setminus F) < \eps$
3. There exists a compact $K\subset E$ with $m(E\setminus K) < \eps$.
:::

:::{.proof title="that measurable sets can be approximated"}
\envlist

- (1): Take $\theset{Q_{i}} \covers E$ and set $O = \union Q_{i}$.
- (2): Since $E^c$ is measurable, produce $O\supset E^c$ with $m(O\setminus E^c) < \eps$.
  - Set $F = O^c$, so $F$ is closed.
  - Then $F\subset E$ by taking complements of $O\supset E^c$
  - $E\setminus F = O\setminus E^c$ and taking measures yields $m(E\setminus F) < \eps$
- (3): Pick $F\subset E$ with $m(E\setminus F) < \eps/2$.
  - Set $K_{n} = F\intersect \DD_{n}$, a ball of radius $n$ about $0$.
  - Then $E\setminus K_{n} \searrow E\setminus F$
  - Since $m(E) < \infty$, there is an $N$ such that $n\geq N \implies m(E\setminus K_{n}) < \eps$.
:::


# Quintessential Qual Problems


:::{.exercise title="?"}
\envlist

- Prove the Lebesgue integral is translation/dilation invariant.
- Prove continuity in $L_1$: $\norm{\tau_hf - f}\converges{h\to 0}\too 0$.
- Prove that $E$ is measurable $\iff$ $E = F \disjoint Z$ with $F\in F_\sigma$ and $Z$ null $\iff$ $E = G\sm Z$ with $G\in G_\delta$ and $Z$ null.
- Show that $m(E) = \sup_{K \subseteq E}m(K) \iff$ there exists $K = K(\eps)$ with $m(K) \in [m(E) - \eps, m(E)]$.
  - What's most useful here is the proof technique, not so much the result itself.
- Apply Fubini and Tonelli to literally anything.
- Prove that $\norm{f}_p\to \norm{f}_\infty$ over a finite measure space.
- Apply Cauchy-Schwarz to literally anything, in the form of $\norm{fg}_1 \leq \norm{f}_2 \norm{g}_2$.

:::

:::{.proposition title="Measurable Slices"}
Let $E$ be a measurable subset of $\RR^n$. Then

- For almost every $x\in \RR^{n_1}$, the slice $E_x \definedas \theset{y \in \RR^{n_2} \mid  (x,y) \in E}$ is measurable in $\RR^{n_2}$.

- The function

\[
F: \RR^{n_1} &\to \RR \\
x &\mapsto m(E_x) = \int_{\RR^{n_2}} \chi_{E_x} ~dy
\]

is measurable and 
\[
m(E) = \int_{\RR^{n_1}} m(E_x) ~dx 
= \int_{\RR^{n_1}} \int_{\RR^{n_2}} \chi_{E_x} ~dy ~dx
.\]

:::

:::{.proof title="of measurable slices"}
\envlist

$\implies$:

- Let $f$ be measurable on $\RR^n$.
- Then the cylinders $F(x, y) = f(x)$ and $G(x, y) = f(y)$ are both measurable on $\RR^{n+1}$.
- Write $\mathcal{A} = \theset{G \leq F} \intersect \theset{G \geq 0}$; both are measurable.


$\impliedby$:

- Let $A$ be measurable in $\RR^{n+1}$.
- Define $A_x = \theset{y\in \RR \mid (x, y) \in \mathcal{A}}$, then $m(A_x) = f(x)$.
- By the corollary, $A_x$ is measurable set, $x \mapsto A_x$ is a measurable function, and $m(A) = \int f(x) ~dx$.
- Then explicitly, $f(x) = \chi_{A}$, which makes $f$ a measurable function.
:::

