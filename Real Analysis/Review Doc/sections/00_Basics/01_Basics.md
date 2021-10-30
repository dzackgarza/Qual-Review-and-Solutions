---
title: Basics
---

# Basics

## Table of Notation

+--------------------------------------------------------------------------------------------------------------------+---------------------------+
|                                            Notation                                                                | Definition                |
+====================================================================================================================+===========================+
| \[\norm{f}_\infty \da \sup_{x\in \dom(f)} \abs{f(x)}\]                                                             | The Sup norm |
+--------------------------------------------------------------------------------------------------------------------+---------------------------+
| \[ \norm{f}_{L^\infty} \da \inf\ts{M \geq 0 \st \abs{f(x)} \leq M \text{ for a.e. } x } \]                         | The \( L^ \infty \) norm  |
+--------------------------------------------------------------------------------------------------------------------+---------------------------+
| \[ f_n \converges{n \to \infty }\to f \]                                                                           |  Convergence of a sequence |
+--------------------------------------------------------------------------------------------------------------------+----------------------------+
| \[ f(x) \converges{\abs x \to \infty}\to 0 \]                                                                      | Vanishing at infinity      |
+--------------------------------------------------------------------------------------------------------------------+----------------------------+
| \[ \int_{\abs{x} \geq N} f \converges{N\to \infty}\to 0 \]                                                         | Having small tails         |
+--------------------------------------------------------------------------------------------------------------------+----------------------------+
| \[ H, \mathcal{H} \]                                                                                               | A Hilbert space            |
+--------------------------------------------------------------------------------------------------------------------+----------------------------+
| \[ X \]                                                                                                            | A topological space |
+--------------------------------------------------------------------------------------------------------------------+---------------------+


## Useful Techniques

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

## The Absolute Essentials

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


## Quintessential Qual Problems


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

## Definitions

### Convergence and Continuity

:::{.definition title="Limsup/Liminf"}
\[  
\limsup_n a_n = \lim_{n\to \infty} \sup_{j\geq n} a_j &= \inf_{n\geq 0} \sup_{j\geq n} a_j \\ 
\liminf_n a_n = \lim_{n\to \infty} \inf_{j\geq n} a_j &= \sup_{n\geq 0} \inf_{j\geq n} a_j
.\]
:::

:::{.definition title="Continuity and Uniform Continuity"}
A function $f: \RR\to \RR$ is **continuous** on $X$ iff for all $x_0\in X$,
\[
&\forall \varepsilon \quad \exists \delta(\varepsilon, x_0) \text{ such that }\quad \forall y, \abs{x_0 - y} < \delta &&\implies \abs{f(x_0) - f(y)} < \varepsilon \\
\iff &\forall \varepsilon \quad \exists \delta(\varepsilon, x_0) \text{ such that }\quad \forall h, \abs{h} < \delta &&\implies \abs{f(x_0) - f(x_0 \pm h)} < \varepsilon
.\]

$f$ is **uniformly continuous** on $X$ iff

\[
  &\forall \varepsilon \quad \exists \delta(\varepsilon) \text{ such that }\quad \forall x, y, \in X \quad \abs{x - y} < \delta &&\implies \abs{f(x) - f(y)} < \varepsilon \\
\iff &\forall \varepsilon \quad \exists \delta(\varepsilon) \text{ such that} \quad \, \forall x, h, \quad \abs{h} < \delta &&\implies \abs{f(x) - f(x \pm h)} < \varepsilon
.\]
These follow from the substitutions $x_0-y = \mp h \implies y = x_0 \pm h$.
:::

:::{.remark}
The main difference is that $\delta$ may depend on $x_0$ and $\eps$ in continuity, but only depends on $\eps$ in the uniform version.
I.e. once $\delta$ is fixed, for continuity one may only range over $x$, but in uniform continuity one can range over all pairs $x,y$.
:::

:::{.proposition title="Lipschitz implies uniformly continuous"}
If $f$ is Lipschitz on $X$, then $f$ is uniformly continuous on $X$.

Supposing that
\[
\norm{f(x) - f(y)} \leq C \norm{x-y}
,\]
for a fixed $\eps$ take $\delta(\eps) \da \eps/C$, then
\[
\norm{f(x) - f(y)}
&\leq C \norm{x-y} \\
&\leq C \delta \\
&= C \qty{\eps/C} \\
&= \eps
.\]
:::

:::{.definition title="Topological Notions"}
Let $X$ be a metric space and $A$ a subset.
Let $A'$ denote the limit points of $A$, and $\bar{A} \da A\union A'$ to be its closure.

- A **neighborhood** of $p$ is an open set $U_p$ containing $p$.

- An $\eps\dash$**neighborhood** of $p$ is an open ball $B_r(p) \da \ts{q \st d(p, q) < r}$ for some $r>0$.

- A point $p\in X$ is an **accumulation point** or a **limit point** of $A$ iff every *punctured* neighborhood $U_p\sm\ts{p}$ contains a point $q\in A$, so $q\neq p$.

- If $p\in A$ and $p$ is not a limit point of $A$, then $p$ is an **isolated point** of $A$.

- $A$ is **closed**  iff $A' \subset A$, so $A$ contains all of its limit points.

- A point $p\in A$ is **interior** iff there is a neighborhood $U_p \subset A$ that is strictly contained in $A$.

- $A$ is **open** iff every point of $A$ is interior.

- $A$ is **perfect** iff $A$ is closed and $A\subset A'$, so every point of $A$ is a limit point of $A$.

- $A$ is **bounded** iff there is a real number $M$ and a point $q\in X$ such that $d(p, q) < M$ for all $p\in A$.

- $A$ is **dense** in $X$ iff every point $x\in X$ is either a point of $A$, so $x\in A$, or a limit point of $A$, so $x\in A'$.
  I.e., $X\subset A\union A'$.

  - Alternatively, $\bar{A} = X$, so the closure of $A$ is $X$.

:::

:::{.definition title="Pointwise Convergence"}
A sequence of functions \( \ts{ f_j } \)  is said to **converge pointwise** to \( f \) if and only if 
\[  
(\forall \varepsilon>0)(\forall x \in S)\left(\exists n_{0} = n_0(x, \eps) \right)\left(\forall n>n_{0}\right)\left(\left|f_{n}(x)-f(x)\right|<\varepsilon\right)
.\]
:::

:::{.definition title="Uniform Convergence"}
\[
(\forall \varepsilon>0)\left(\exists n_{0} = n_0(\eps) \right)(\forall x \in S)\left(\forall n>n_{0}\right)\left(\left|f_{n}(x)-f(x)\right|<\varepsilon\right)
.\]
Negated:[^Negated_uniform_convergence]
\[  
(\exists \varepsilon>0)\left(\forall n_{0} = n_0 (\eps) \right)(\exists x = x(n_0) \in S)\left(\exists n>n_{0}\right)\left(\left|f_{n}(x)-f(x)\right| \geq \varepsilon\right)
.\]

[^Negated_uniform_convergence]: Slogan: to negate, find a bad $x$ depending on $n_0$ that are larger than some $\eps$.

:::

### Function Spaces

:::{.definition title="Completeness"}
A metric space is **complete** if every Cauchy sequence converges.
:::

:::{.fact}
If $X$ is complete, then absolutely convergent implies convergent.
:::

:::{.definition title="Nowhere Dense Sets"}
Recall that a set $S$ in $X$ is **dense** $\iff$ every open $U\subseteq X$ intersects $S$.
A set $S$ is **nowhere dense** in $X$ $\iff$ the closure of $S$ has empty interior $\iff$ every subset (or interval) contains an open set (or a subinterval) that does not intersect $S$.
This just says $S$ is not dense in any subset $S' \subseteq X$, by negating what it means to be dense.
:::

:::{.definition title="Meager Sets"}
A set is **meager** if it is a *countable* union of nowhere dense sets.
:::

:::{.proposition title="Finite unions of nowhere dense sets are still nowhere dense"}
A *finite* union of nowhere dense is again nowhere dense.
:::

:::{.definition title="Baire Space"}
A space $X$ is a **Baire space** if and only if every countable intersections of open, dense sets is still dense.
:::

### Measure Theory

:::{.definition title="Limsup and Liminf of Sets"}
\[
\liminf_{n} E_{n} \da \Union_{N=1}^\infty \Intersect_{n=N}^\infty E_{n} &= \theset{x \suchthat x\in E_{n} \text{ for all but finitely many } n}  \\
\limsup_{n} E_{n} \da \Intersect_{N=1}^\infty \Union_{n=N}^{\infty} E_{n} &= \theset{x \suchthat x\in E_{n} \text{ for infinitely many } n} 
.\]

  
:::

:::{.remark}
How to derive these definitions: use that $\inf$ corresponds to intersections/existence and $\sup$ corresponds to unions/forall.

- For $\liminf E_n$: 
  - $x\in \liminf E_n \iff$ there exists some $N$ such that $x\in \intersect_{n\geq N} E_n$, i.e. $x\in E_n$ for all $n\geq N$.
    So $x$ is in *all* but finitely many $n$.
  - How to remember:  $\liminf_{n} x_n = \sup_{n} \inf_{k\geq n} x_n$ for sequences, where sups look like unions and infs look like intersections.
  - Alternatively: there exists an $n$ (union) such that for all $k\geq n$ (intersection)...
    

- For $\limsup E_n$: 
  - $x\in \limsup E_n \iff$ for every $N$, there exists some $n\geq N$ such that $x\in E_n$.
    So $x$ is an infinitely many $E_n$.
  - How to remember:  $\limsup_{n} x_n = \inf{n} \sup{k\geq n} x_n$ for sequences, where sups look like unions and infs look like intersections.
  - Alternatively: for all $n$ (intersection) there exists a $k\geq n$ (union)...

It's also useful to note that $\liminf E_n \subseteq \limsup E_n$, since $\liminf E_n$ are elements that are eventually in all sets, and $\limsup E_n$ are elements in infinitely many sets.

Why these are useful: for finite measure spaces,
\[
\mu\qty{\liminf_n E_n }\leq \liminf_n \mu(E_n) \leq \lim_n \mu(E_n) \leq \limsup_n \mu(E_n) \leq \mu\qty{\limsup_n E_n}
.\]
If the $\limsup$ and $\liminf$ sets are equal, then one can define the set $\lim_n E_n \da \union_n E_n$ if $E_n \increasesto E$ or $\lim_n E_n \da \intersect_n E_n$ if $E_n\decreasesto E$ in which case continuity of measure states
\[
\mu\qty{\lim_n E_n} = \lim_n \mu(E_n)
.\]



:::

:::{.definition title="$F_\sigma$ and $G_\delta$ Sets"}
An $F_\sigma$ set is a union of closed sets, and a $G_\delta$ set is an intersection of opens. [^Mnemonic_Ferme]

[^Mnemonic_Ferme]: 
Mnemonic: "F" stands for *ferme*, which is "closed" in French, and $\sigma$ corresponds to a "sum", i.e. a union.

:::

:::{.definition title="Outer Measure"}
The **outer measure** of a set is given by
\[
m_*(E) \da \inf_{\substack{\theset{Q_{i}} \rightrightarrows E \\ \text{closed cubes}}} \sum \abs{Q_{i}}
,\]
where $\abs{Q_i}$ is the standard Euclidean volume of a cube in $\RR^n$.
:::

:::{.definition title="Lebesgue Measurable Sets"}
A subset $E\subseteq \RR^n$ is **Lebesgue measurable** iff for every $\eps> 0$ there exists an open set $O \supseteq E$ such that $m_*(O\setminus E) < \eps$.
In this case, we define $m(E) \da m_*(E)$.
:::

:::{.definition title="$L^+$: Measurable non-negative functions."}
$f\in L^+$ iff $f$ is measurable and non-negative.
:::

### Integrals and $L^p$ Spaces

:::{.definition title="Integrability"}
A measurable function is **integrable** iff $\norm{f}_1 < \infty$.
:::

:::{.definition title="The Infinity Norm / Essential supremum / Essentially bounded"}
\[
\norm{f}_\infty &\definedas \inf_{\alpha \geq 0} \theset{\alpha \suchthat \mu\qty{\theset{\abs{f} \geq \alpha}} = 0}
.\]
In words, this is the smallest upper bound that holds almost everywhere, so $\abs{f(x)} \leq \norm{f}_\infty$ holds for almost every $x$.
A function $f:X \to \CC$ is **essentially bounded** iff there exists a real number $c$ such that $\mu(\theset{\abs{f} > x}) = 0$, i.e. $\norm{f}_\infty < \infty$.
:::

:::{.definition title="$L^\infty$"}
\[
L^\infty(X)
\definedas \theset{f: X\to \CC \suchthat f \text{ is essentially bounded }}
\definedas \theset{f: X\to \CC \suchthat \pnorm{f}\infty < \infty}
.\]

:::

:::{.definition title="Convolution"}
$$f * g(x)=\int f(x-y) g(y) d y .$$
:::

:::{.definition title="Fourier Transform"}
\[
\hat f(\xi) = \int f(x) ~e^{2\pi i x \cdot \xi} ~dx
.\]

:::

:::{.definition title="Dilation"}
\[
\phi_{t}(x) = t^{-n} \phi\left(t^{-1} x\right)
.\]
:::

:::{.definition title="Approximations to the identity"}
For $\phi\in L^1$, the dilations satisfy $\int \phi_{t} = \int \phi$, and if $\int \phi = 1$ then $\phi$ is an **approximate identity**. 
:::

### Functional Analysis

:::{.definition title="Dual Norm"}
For $X$ a normed vector space and $L \in X\dual$, the **dual norm** or **operator norm** is defined by
\[
\norm{L}_{X\dual} 
\da \sup_{ \substack{x\in X \\ \norm{x} = 1} } \abs{L(x)}
= \sup_{ \substack{x\in X \\ \norm{x} \leq  1} } \abs{L(x)}
.\]

:::

:::{.definition title="Orthonormal sequence "}
A countable collection of elements \( \ts{ u_i } \)  is **orthonormal** if and only if 

1. \( \inner{u_i}{u_j} = 0 \) for all \( j \neq k \) and
2. \( \norm{u_j}^2 \da \inner{u_j}{u_j} = 1 \) for all \( j \).  

:::

:::{.definition title="Basis of a Hilbert space"}
A set $\theset{u_{n}}$ is a **basis** for a Hilbert space $\mch$ iff it is dense in $\mch$.
:::

:::{.definition title="Completeness of a Hilbert space"}
A collection of vectors $\theset{u_{n}}\subset H$ is **complete** iff $\inner{x}{u_{n}} = 0$ for all $n \iff x = 0$ in $H$.
:::

:::{.definition title="Dual of a Hilbert space"}
The **dual** of a Hilbert space \( H \) is defined as 
\[
H\dual \da \theset{L: H\to \CC \suchthat L \text{ is continuous }}
.\]

:::

:::{.definition title="Linear functionals"}
A map $L: X \to \CC$ is a **linear functional** iff
\[
L(\alpha\vector x + \vector y) = \alpha L(\vector x) + L(\vector y).
.\]
:::

:::{.definition title="Banach Space"}
A space is a **Banach space** if and only if it is a complete normed vector space.
:::

:::{.definition title="Hilbert Space"}
A **Hilbert space** is an inner product space which is a Banach space under the induced norm.
:::


## Theorems

:::{.theorem title="Folland 0.25"}
For $E \subseteq (X, d)$ a metric space, TFAE:

- $E$ is complete and totally bounded.
- $E$ is sequentially compact: Every sequence in $E$ has a subsequence that converges to a point in $E$.
- $E$ is compact: every open cover has a finite subcover.

Note that $E$ is complete as a metric space with the induced metric iff $E$ is closed in $X$, and $E$ is bounded iff it is totally bounded.
:::

:::{.theorem title="Mean Value Theorem"}
If $f: [a, b] \to \RR$ is continuous on a closed interval and differentiable on $(a, b)$, then there exists $\xi \in [a, b]$ such that 
\[
f(b) - f(a) = f'(\xi)(b-a)
.\]


:::

:::{.theorem title="Lagrange and Cauchy Remainders"}
If $f$ is $n$ times differentiable on a neighborhood of a point $p$, say $N_\delta(p)$, then for all points $x$ in the deleted neighborhood $N_\delta(p) - \theset{p}$ , there exists a point $\xi$ strictly between $x$ and $p$ such that
\[
x \in N_\delta(p)-\theset{p} \implies f(x) 
&= \sum_{k=0}^{n-1} \frac{f^{(k)}(p)}{k!}(x-p)^k + \frac{f^{(n)}(\xi)}{n!}(x-p)^n \\ \\
&= \sum_{k=0}^{n-1} \frac{f^{(k)}(p)}{k!}(x-p)^k + \int_c^x \frac{1}{n!} \dd{^n f}{x^n}(t) (x-t)^n ~dt
\]
:::

:::{.proposition title="Sufficient condition for Taylor convergence"}
Given a point $c$ and some $\varepsilon>0$, if $f \in C^\infty(I)$ and there exists an $M$ such that 
$$
x \in N_\varepsilon(c) \implies \abs{f^{(n)}(x)} \leq M^n
$$
then the Taylor expansion about $c$ converges on $N_\varepsilon(c)$.
:::

### Topology / Sets

:::{.theorem title="Heine-Cantor"}
Every continuous function $f:X\to Y$ where $X$ is a compact metric space is uniformly continuous.
:::

:::{.proof title="?"}
Fix $\eps>0$, we'll find a $\delta$ that works for all $x\in X$ uniformly.
For every $x\in X$, pick a $\delta_x$ neighborhood satisfying the conditions for (assumed) continuity.
Take an open cover by $\delta_x/2$ balls, extract a finite subcover, take $\delta$ the minimal radius.
:::

:::{.proposition title="Compact if and only if sequentially compact for metric spaces"}
Metric spaces are compact iff they are sequentially compact, (i.e. every sequence has a convergent subsequence).
:::

:::{.proof title="?"}
Todo.
\todo[inline]{Proof.}
:::

:::{.proposition title="A unit ball that is not compact"}
The unit ball in $C([0, 1])$ with the sup norm is not compact.
:::

:::{.proof title="?"}
Take $f_k(x) = x^n$, which converges to $\chi(x=1)$. 
The limit is not continuous, so no subsequence can converge.
:::



:::{.theorem title="Heine-Borel"}
$X\subseteq \RR^n$ is compact $\iff X$ is closed and bounded.
:::

:::{.proposition title="Geometric Series"}
\[
\sum_{k=0}^\infty x^k = \frac 1 {1-x} \iff \abs{x} < 1
.\]
:::

:::{.corollary title="?"}
\[
\sum_{k=0}^\infty \frac 1 {2^k} = 1
.\]
:::

:::{.proposition title="?"}
The Cantor set is closed with empty interior.
:::

:::{.proof title="?"}
Its complement is a union of open intervals, and can't contain an interval since intervals have positive measure and $m(C_n)$ tends to zero.
:::

:::{.corollary title="?"}
The Cantor set is nowhere dense.
:::

:::{.proposition title="?"}
Singleton sets in $\RR$ are closed, and thus $\QQ$ is an $F_\sigma$ set.
:::

:::{.theorem title="Baire"}
$\RR$ is a **Baire space** 
Thus $\RR$ can not be written as a countable union of nowhere dense sets.
:::

:::{.lemma title="?"}
Any nonempty set which is bounded from above (resp. below) has a well-defined supremum (resp. infimum).
:::

### Functions

:::{.proposition title="Existence of Smooth Compactly Supported Functions"}
There exist smooth compactly supported functions, e.g. take 
\[
f(x) = e^{-\frac{1}{x^2}} \chi_{(0, \infty)}(x)
.\]
:::

:::{.lemma title="Function discontinuous on the rationals"}
There is a function discontinuous precisely on $\QQ$.
:::

:::{.proof title="?"}
$f(x) = \frac 1 n$ if $x = r_n \in \QQ$ is an enumeration of the rationals, and zero otherwise.
The limit at every point is 0.
:::

:::{.proposition title="No functions discontinuous on the irrationals"}
There *do not* exist functions that are discontinuous precisely on $\RR\setminus \QQ$.
:::

:::{.proof title="?"}
$D_f$ is always an $F_\sigma$ set, which follows by considering the oscillation $\omega_f$.
Use that $\omega_f(x) = 0 \iff f$ is continuous at $x$, and $D_f = \union_n A_{\frac 1 n}$ where $A_\varepsilon = \theset{\omega_f \geq \varepsilon}$ is closed.
:::

:::{.proposition title="Lipschitz $\iff$ differentiable with bounded derivative."}
A function $f: (a, b) \to \RR$ is Lipschitz $\iff f$ is differentiable and $f'$ is bounded.
In this case, $\abs{f'(x)} \leq C$, the Lipschitz constant.
:::

### Sequences and Series

:::{.proposition title="The Cauchy condensation test"}
For $\ts{a_k}$ is a non-increasing sequence in $\RR$ then
\[
\sum_{k\geq 1} a_k < \infty \iff \sum_{k\geq 1} 2^k a_{2^k}<\infty
.\]
:::

:::{.proof title="showing a useful trick"}
Show that
\[
\sum a_k \leq \sum 2^k a_{2^k} \leq 2 \sum a_k
\]
using 
\[
\sum a_k = a_0 + a_1 + a_2 + a_3 + \cdots
\leq \qty{a_1} + \qty{a_2 + a_2} + \qty {a_3 + a_3 + a_3 + a_3} + \cdots \\
\]
where each group with $a_k$ has $2^k$ terms.

:::


## Uniform Convergence

:::{.proposition title="Testing Uniform Convergence: The Sup Norm Test"}
$f_n \to f$ uniformly iff there exists an $M_n$ such that $\norm{f_n - f}_\infty \leq M_n \to 0$.
:::

:::{.remark title="Negating the Sup Norm test"}
**Negating**: find an $x$ which depends on $n$ for which $\norm{f_n}_\infty > \eps$ (negating small tails) or $\norm{f_n - f_m} > \eps$ (negating the Cauchy criterion).
:::

:::{.proposition title="$C(I)$ is complete"}
The space $X = C([0, 1])$, continuous functions $f: [0, 1] \to \RR$, equipped with the norm 
\[
\norm{f}_\infty \da \sup_{x\in [0, 1]} \abs{f(x)}
\]
is a **complete** metric space.

:::

:::{.proof}
\envlist

1.  Let $\theset{f_k}$ be Cauchy in $X$.

2.  Define a candidate limit using pointwise convergence:

    Fix an $x$; since
  \[
  \abs{f_k(x) - f_j(x)}  \leq \norm{f_k - f_k} \to 0
  \] 
    the sequence $\theset{f_k(x)}$ is Cauchy in $\RR$.
    So define $f(x) \definedas \lim_k f_k(x)$.


3.  Show that $\norm{f_k - f} \to 0$:
  \[
  \abs{f_k(x) - f_j(x)} < \varepsilon ~\forall x \implies \lim_{j} \abs{f_k(x) - f_j(x)} <\varepsilon ~\forall x
  \]
    Alternatively, $\norm{f_k-f} \leq \norm{f_k - f_N} + \norm{f_N - f_j}$, where $N, j$ can be chosen large enough to bound each term by $\varepsilon/2$.

4.  Show that $f\in X$:

    The uniform limit of continuous functions is continuous.

:::

:::{.remark}
In other cases, you may need to show the limit is bounded, or has bounded derivative, or whatever other conditions define $X$.
:::


### Series

:::{.proposition title="p-tests"}
Let $n$ be a fixed dimension and set $B = \theset{x\in \RR^n \suchthat \norm{x} \leq 1}$. 
\[
\sum \frac 1 {n^p} < \infty &\iff p>1 \\
\int_\varepsilon^\infty \frac 1 {x^p} < \infty 
&\iff p>1 \\
\int_0^1 \frac 1 {x^p} < \infty 
&\iff p<1 \\
\int_B \frac{1}{\abs{x}^p} < \infty &\iff p < n \\
\int_{B^c} \frac{1}{\abs{x}^p} < \infty &\iff p > n \\
.\]
:::

:::{.proposition title="Comparison Test"}
If $0\leq a_n \leq b_n$, then 

- $\sum b_n < \infty \implies \sum a_n < \infty$, and 
- $\sum a_n = \infty \implies \sum b_n = \infty$.

:::

:::{.proposition title="Small Tails for Series of Functions"}
If $\sum f_n$ converges then $f_n \to 0$ uniformly.
:::

:::{.corollary title="Term by Term Continuity Theorem"}
If $f_n$ are continuous and $\sum f_n \to f$ converges uniformly, then $f$ is continuous.
:::


:::{.proposition title="Cauchy criterion for sums"}
$f_n$ are uniformly Cauchy (so $\norm{f_n - f_m}_\infty < \eps$) iff $f_n$ is uniformly convergent.
:::

#### Derivatives

:::{.theorem title="Term by Term Differentiability Theorem"}
If $f_n$ are differentiable, $\sum f_n' \to g$ uniformly, and there exists one point[^pointwise_works_too] $x_0$ such that $\sum f_n(x)$ converges, then there exist an $f$ such that $\sum f_n \to f$ uniformly and $f' = g$.[^theorem_referfence_6.4.3_Abbott]

[^theorem_referfence_6.4.3_Abbott]: See Abbott theorem 6.4.3, pp 168.

[^pointwise_works_too]: So this implicitly holds if $f$ is the pointwise limit of $f_n$.

:::

## Commuting Limiting Operations

:::{.proposition title="Limits of bounded functions need not be bounded"}
\[  
\lim_{n\to \infty}\sup_{x\in X} \abs{f_n(x) } \neq \sup_{x\in X} \abs{\lim_{n\to\infty} f_n(x) }
.\]
:::

:::{.proposition title="Limits of continuous functions need not be continuous"}
\[  
\lim_{k\to \infty} \lim_{n\to\infty} f_n(x_k) \neq
\lim_{n\to \infty} \lim_{k\to\infty} f_n(x_k)
.\]
:::

:::{.proposition title="Limits of differentiable functions need not be differentiable"}
\[  
\lim_{n\to \infty} \dd{}{x} f_n \neq \dd{}{n} \qty{\lim_{n\to \infty} f_n}
.\]
Note that uniform convergence of $f_n$ and $f_n'$ is sufficient to guarantee that $f$ is differentiable.
Even worse: every continuous function is a uniform limit of polynomials by the Weierstrass approximation theorem.
:::

:::{.example title="?"}
As a counterexample:
\[
f_n(x) \da \sqrt{x^2 + {1\over n}} \converges{n\to\infty}\too f(x) \da \abs{x}
,\]
and this convergence is even uniform.
:::

:::{.example title="?"}
\[
f_n(x) \da {x\over 1 + nx^2}
.\]
Then by Calculus, $f_n(x) \leq 1/2\sqrt{n} \da M_n$ and $f_n\to 0$ uniformly, so $f' = 0$.
But 
\[
f_n'(x) = {1-nx^2 \over\qty{1 + nx^2}^2}
,\]
and $f_n'(0) \to 1$.
:::

:::{.proposition title="?"}
\[  
\lim_{n\to \infty} \int_a^b f_n(x) \,dx \neq \int_a^b \lim_{n\to \infty} \qty{ f_n(x) } \,dx
.\]
:::

## Probabilist Tools: "Almost" Theorems

:::{.theorem title="Egorov's Theorem"}
Let $E \subseteq \RR^d$ be measurable of positive finite measure with $f_k\to f$ almost everywhere on $E$.
Then for every $\eps > 0$ there is a closed $A_\eps \subseteq E$ with $\mu(E\sm A_\eps) < \eps$ and $f_k\to f$ uniformly on $A_\eps$.
:::

:::{.proof title="of Egorov"}


![](figures/2021-06-11_18-07-43.png)

![](figures/2021-06-11_18-07-58.png)

:::

:::{.theorem title="Lusin's Theorem"}
If $f$ is measurable and finite-valued on $E$ with $\mu(E) < \infty$ then for every $\eps>0$ there exists a closed set $F_\eps$ with
\[
F_\eps \subset F && \mu(E - F_\eps) \leq \eps
\]
where $f$ restricted to $F_\eps$ is continuous.

> Note: this means that the separate function $\tilde f \da \ro{f}{F_\eps}$ is continuous, not that the function $f$ defined on all of $E$ is continuous at points of $F_\eps$.

:::

:::{.proof title="of Lusin"}

![](figures/2021-06-11_18-04-52.png)
:::

## Slightly Advanced Stuff

:::{.theorem title="Weierstrass Approximation"}
If $[a, b] \subset \RR$ is a closed interval and $f$ is continuous, then for every $\eps> 0$ there exists a polynomial $p_\eps$ such that $\norm{f- p_\eps}_{L^\infty([a, b])} \converges{\eps \to 0}\to 0$.

Equivalently, polynomials are dense in the Banach space $C([0, 1], \norm{\wait}_\infty)$.
:::

## Examples and Counterexamples

:::{.example title="?"}
A series of continuous functions that does *not* converge uniformly but is still continuous:
\[  
g(x) \da \sum {1 \over 1 + n^2 x}
.\]

Take $x = 1/n^2$.
:::

Let all of the following integrals to be over a compact interval $[a, b]$ with $0 \leq a < b$.

Questions to ask:

- Where is/isn't $f$ continuous?
- Where is/isn't $f$ differentiable?
- Is $f$ Riemann integrable?

### Dirichlet function
$$
f ( x ) = b + (a-b)~\chi(x\in \QQ) = \begin{cases}
a, & x\in \QQ \\
b, & \text{else}
\end{cases}
$$
(usually take $a=1, b=0$)

- Continuous nowhere
- Discontinuous everywhere
- Not integrable
- Differentiable nowhere

### Dirichlet with a Continuous Point
$$
f ( x ) = x~\chi(\QQ) = 
\begin{cases}
x, & x\in \QQ \\
0, & \text{else}
\end{cases}
$$

- Continuous at 0
- Discontinuous at $\RR-\theset{0}$
- Not integrable
  - $U(f) > \frac 1 4$ but $L(f) = 0$.
- Differentiable nowhere

### Dirichlet with a Differentiable Point
$$
f ( x ) = x^2~\chi(\QQ) = \begin{cases}
x^2, & x\in \QQ \\
0, & \text{else}
\end{cases}
$$

- Continuous at 0
- Discontinuous at $\RR-\theset{0}$
- Not integrable
- Differentiable at 0 

### Dirichlet with Two Functions
$$
f ( x ) = x~\chi{\QQ} + (-x)\chi(\RR-\QQ) = \begin{cases}
x, & x\in \QQ \\
-x, & \text{else}
\end{cases}
$$

- Continuous at 0
- Discontinuous at $\RR-\theset{0}$
- Differentiable nowhere.
- Not integrable


:::{.proof title="of non-integrability"}
Restrict attention to $\tv{\frac 1 2, 1}$
\[
\overline{\int_0^1} f 
&= \inf \theset{ \sum \sup f(x) (x_i - x_{i-1}) } \\
\sup f(x) = x_i \implies 
\sum \sup f(x) (x_i - x_{i-1}) &= \sum x_i (x_i - x_{i-1}) \\
&> \sum \frac 1 2 (x_i - x_{i-1}) \\
&= \frac 1 2 \left(\frac 1 2\right) = \frac 1 4 \\
\implies \overline{\int_0^1} f &\geq \frac 1 4
\]
and 
\[
\underline{\int_0^1} f 
&= \sup \theset{ \sum \inf f(x) (x_i - x_{i-1})} \\
\inf f(x)= -x_i \implies 
\sum \inf f(x) (x_i - x_{i-1}) 
&= \sum -x_i (x_i - x_{i-1}) \\
&< -\sum \frac 1 2 (x_i - x_{i-1}) \\
&= -\frac 1 2 \left( \frac 1 2 \right) = -\frac 1 4 \\
\implies \underline{\int_0^1} f &\leq -\frac 1 4
\]
So we have $\underline{\int_0^1} f \lneq 0 \lneq \overline{\int_0^1} f$.
:::


## The Thomae function:
$$
f ( x ) = \begin{cases}
\frac 1 q, & x = \frac p q \in \QQ,~(p,q) = 1 \\
0, & \text{else}
\end{cases}
$$

- Continuous on $\RR-\QQ$
- Discontinuous on $\QQ$
- Integrable with $\int_a^b f = 0$
- Differentiable nowhere

