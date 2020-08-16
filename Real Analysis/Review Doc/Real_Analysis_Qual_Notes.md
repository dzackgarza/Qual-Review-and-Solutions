
---
title: Real Analysis Review Notes
---

# Basics

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
  a=b \iff a\leq b \txand a\geq b
  .\]
  - Use an epsilon of room:
  \[  
  a < b + \eps \,\forall \eps \implies a\leq b 
  .\]
  - Showing something is zero:
  \[  
  \abs{a} \leq \eps \,\forall\eps\implies a = 0
  .\]

- Simplifications:
  - To show something for a measurable set, show it for bounded/compact/elementary sets/
  - To show something for a function, show it for continuous, bounded, compactly supported, simple, indicator functions, $L^1$, etc
  - Replace a continuous sequence ($\eps\to 0$) with an arbitrary countable sequence ($x_n \to 0$)
  - Intersect with a ball $B_r(\vector 0)\subset \RR^n$.

- Integrals
  - Break up $\RR^n = \theset{\abs{x} \leq 1} \coprod \theset{\abs{x} > 1}$.

## Definitions

:::{.definition title="Uniform Continuity"}
$f$ is uniformly continuous iff

\[
    &\forall \varepsilon \quad \exists \delta(\varepsilon) \mid \quad \forall x, y, \quad \abs{x - y} < \delta \implies \abs{f(x) - f(y)} < \varepsilon \\
\iff &\forall \varepsilon \quad \exists \delta(\varepsilon) \mid \quad \forall x, y, \quad \abs{y} < \delta \implies \abs{f(x-y) - f(y)} < \varepsilon
.\]
:::


Definition (Nowhere Dense Sets)
: A set $S$ is **nowhere dense** iff the closure of $S$ has empty interior iff every interval contains a subinterval that does not intersect $S$.

Definition (Meager Sets)
: A set is **meager** if it is a *countable* union of nowhere dense sets.

:::{.definition title="$F_\sigma$ and $G_\delta$ Sets"}
An $F_\sigma$ set is a union of closed sets, and a $G_\delta$ set is an intersection of opens.
:::
  
> Mnemonic: "F" stands for *ferme*, which is "closed" in French, and $\sigma$ corresponds to a "sum", i.e. a union.

Theorem (Heine-Cantor)
: Every continuous function on a compact space is uniformly continuous.

:::{.definition title="Limsup/Liminf"}
\[  
\limsup_n a_n = \lim_{n\to \infty} \sup_{j\geq n} a_j &= \inf_{n\geq 0} \sup_{j\geq n} a_j \\ 
\liminf_n a_n = \lim_{n\to \infty} \inf_{j\geq n} a_j &= \sup_{n\geq 0} \inf_{j\geq n} a_j
.\]
:::


## Theorems

### Topology / Sets


Lemma
:	Metric spaces are compact iff they are sequentially compact, (i.e. every sequence has a convergent subsequence).

Proposition
: The unit ball in $C([0, 1])$ with the sup norm is not compact.

Proof 
: Take $f_k(x) = x^n$, which converges to a dirac delta at 1. The limit is not continuous, so no subsequence can converge.


Proposition
: A *finite* union of nowhere dense is again nowhere dense.

Lemma (Convergent Sums Have Small Tails)
:   $$\sum a_n < \infty \implies a_n \to 0 \qtext{and} \sum_{k=N}^\infty a_n \converges{N\to\infty}\to 0$$

Theorem (Heine-Borel)
: $X\subseteq \RR^n$ is compact $\iff X$ is closed and bounded.

Lemma (Geometric Series)
:   \[
    \sum_{k=0}^\infty x^k = \frac 1 {1-x} \iff \abs{x} < 1
    .\]

    *Corollary:* 
    $\sum_{k=0}^\infty \frac 1 {2^k} = 1$.

Lemma
: The Cantor set is closed with empty interior.

Proof
:   Its complement is a union of open intervals, and can't contain an interval since intervals have positive measure and $m(C_n)$ tends to zero.

Corollary
: The Cantor set is nowhere dense.

Lemma
:	Singleton sets in $\RR$ are closed, and thus $\QQ$ is an $F_\sigma$ set.

Theorem (Baire)
: $\RR$ is a **Baire space** (countable intersections of open, dense sets are still dense). 
  Thus $\RR$ can not be written as a countable union of nowhere dense sets.

Lemma
:	Any nonempty set which is bounded from above (resp. below) has a well-defined supremum (resp. infimum).

### Functions

Proposition (Existence of Smooth Compactly Supported Functions)
: There exist smooth compactly supported functions, e.g. take 
$$f(x) = e^{-\frac{1}{x^2}} \chi_{(0, \infty)}(x).$$

Lemma
:	There is a function discontinuous precisely on $\QQ$.

Proof
: $f(x) = \frac 1 n$ if $x = r_n \in \QQ$ is an enumeration of the rationals, and zero otherwise.
  The limit at every point is 0.

Lemma
:	There *do not* exist functions that are discontinuous precisely on $\RR\setminus \QQ$.

Proof
:   $D_f$ is always an $F_\sigma$ set, which follows by considering the oscillation $\omega_f$.
    $\omega_f(x) = 0 \iff f$ is continuous at $x$, and $D_f = \union_n A_{\frac 1 n}$ where $A_\varepsilon = \theset{\omega_f \geq \varepsilon}$ is closed.

Proposition
:   A function $f: (a, b) \to \RR$ is Lipschitz $\iff f$ is differentiable and $f'$ is bounded.
    In this case, $\abs{f'(x)} \leq C$, the Lipschitz constant.


## Uniform Convergence

Theorem (Weierstrass Approximation)
: If $[a, b] \subset \RR$ is a closed interval and $f$ is continuous, then for every $\eps> 0$ there exists a polynomial $p_\eps$ such that $\norm{f- p_\eps}_{L^\infty([a, b])} \converges{\eps \to 0}\to 0$.

Theorem (Egorov)
:   Let $E \subseteq \RR^n$ be measurable with $m(E) > 0$ and $\theset{f_k: E \to \RR}$ be measurable functions such that $$f(x) \definedas \displaystyle\lim_{k\to\infty} f_k(x) < \infty$$ exists almost everywhere.

    Then $f_k \to f$ *almost uniformly*, i.e.
    \[
    \forall\varepsilon > 0, ~\exists F \subseteq E ~\text{closed such that } &
    m(E\setminus F) < \varepsilon ~\text{ and }~ f_k \mapsvia{u}  f ~\text{on}~ F
    .\]

Proposition 
: The space $X = C([0, 1])$, continuous functions $f: [0, 1] \to \RR$, equipped with the norm $\norm{f} = \sup_{x\in [0, 1]} \abs{f(x)}$, is a **complete** metric space.

Proof
:   \hfill

    1.  Let $\theset{f_k}$ be Cauchy in $X$.

    2.  Define a candidate limit using pointwise convergence:

        Fix an $x$; since
        $$
        \abs{f_k(x) - f_j(x)}  \leq \norm{f_k - f_k} \to 0
        $$ 
        the sequence $\theset{f_k(x)}$ is Cauchy in $\RR$.
        So define $f(x) \definedas \lim_k f_k(x)$.


    3.  Show that $\norm{f_k - f} \to 0$:
        $$
        \abs{f_k(x) - f_j(x)} < \varepsilon ~\forall x \implies \lim_{j} \abs{f_k(x) - f_j(x)} <\varepsilon ~\forall x
        $$
        Alternatively, $\norm{f_k-f} \leq \norm{f_k - f_N} + \norm{f_N - f_j}$, where $N, j$ can be chosen large enough to bound each term by $\varepsilon/2$.

    4.  Show that $f\in X$:

        The uniform limit of continuous functions is continuous.

        > Note: in other cases, you may need to show the limit is bounded, or has bounded derivative, or whatever other conditions define $X$.

Theorem (Uniform Limits of Continuous Functions are Continuous)
:	A uniform limit of continuous functions is continuous.



:::{.proposition title="Testing Uniform Convergence: The Sup Norm"}
$f_n \to f$ uniformly iff there exists an $M_n$ such that $\norm{f_n - f}_\infty \leq M_n \to 0$.
:::
> **Negating**: find an $x$ which depends on $n$ for which the norm is bounded *below*.


:::{.proposition title="Testing Uniform Convergence: The Weierstrass $M\dash$Test"}
If $\sup_{x\in A} \abs{f_n(x)} \leq M_n$ for each $n$ where $\sum M_n < \infty$, then $\sum_{n=1}^\infty f_n(x)$ converges uniformly and absolutely on $A$.
:::


Lemma (Uniform Limits Commute with Integrals)
: If $f_n \to f$ uniformly, then $\int f_n = \int f$.

Lemma (Uniform Convergence and Derivatives)
: If $f_n' \to g$ uniformly for some $g$ and $f_n \to f$ pointwise (or at least at one point), then $g = f'$.

### Series

Lemma (Pointwise Convergence for a Series of Functions)
: If $f_n(x) \leq M_n$ **for a fixed $x$** where $\sum M_n < \infty$, then the series $f(x) = \sum f_n(x)$ converges pointwise.

Lemma (Small Tails for Series of Functions)
:	If $\sum f_n$ converges then $f_n \to 0$ uniformly.

Lemma (M-test for Series)
: If $\abs{f_n(x)} \leq M_n$ which does not depend on $x$, then $\sum f_n$ converges uniformly.

Lemma (p-tests)
:   Let $n$ be a fixed dimension and set $B = \theset{x\in \RR^n \suchthat \norm{x} \leq 1}$. 
    \[
    \sum \frac 1 {n^p} < \infty &\iff p>1 \\
    \int_\varepsilon^\infty \frac 1 {x^p} < \infty 
    &\iff p>1 \\
    \int_0^1 \frac 1 {x^p} < \infty 
    &\iff p<1 \\
    \int_B \frac{1}{\abs{x}^p} < \infty &\iff p < n \\
    \int_{B^c} \frac{1}{\abs{x}^p} < \infty &\iff p > n \\
    .\]


# Measure Theory

## Useful Techniques

- $s = \inf\theset{x\in X} \implies$ for every $\varepsilon$ there is an $x\in X$ such that $x \leq s + \varepsilon$.

- Always consider bounded sets, and if $E$ is unbounded write $E = \union_n B_n(0) \intersect E$ and use countable subadditivity or continuity of measure.

## Definitions

Definition (Outer Measure)
:   The outer measure of a set is given by
    \begin{align*}
    m_*(E) \definedas \inf_{\substack{\theset{Q_i} \rightrightarrows E \\ \text{closed cubes}}} \sum \abs{Q_i}
    .\end{align*}

Definition (Limsup and Liminf of Sets)
:   \hfill	
    \begin{align*}
    \limsup_n A_n \definedas \intersect_n \union_{j\geq n} A_j&= \theset{x \suchthat x\in A_n \text{ for inf. many $n$}}  \\
    \liminf_n A_n \definedas \union_n \intersect_{j\geq n} A_j &= \theset{x \suchthat x\in A_n \text{ for all except fin. many $n$}}  \\
    .\end{align*}

Definition (Lebesgue Measurable Set)
: A subset $E\subseteq \RR^n$ is *Lebesgue measurable* iff for every $\eps> 0$ there exists an open set $O \supseteq E$ such that $m_*(O\setminus E) < \eps$.
In this case, we define $m(E) \definedas m_*(E)$.


## Theorems

Lemma
:	Every open subset of $\RR$ (resp $\RR^n$) can be written as a unique countable union of disjoint (resp. almost disjoint) intervals (resp. cubes).

Lemma (Properties of Outer Measure)
:   \hfill
    - Montonicity: $E\subseteq F \implies m_*(E) \leq m_*(F)$.
    - Countable Subadditivity: $m_*(\union E_i) \leq \sum m_*(E_i)$.
    - Approximation: For all $E$ there exists a $G \supseteq E$ such that $m_*(G) \leq m_*(E) + \varepsilon$.
    - Disjoint[^1] Additivity: $m_*(A \disjoint B) = m_*(A) + m_*(B)$. 
  
    [^1]: This holds for outer measure **iff** $\mathrm{dist}(A, B) > 0$.

Lemma (Subtraction of Measure)
: $$m(A) = m(B) + m(C) \qtext{and} m(C) < \infty \implies m(A) - m(C) = m(B).$$

Lemma (Continuity of Measure)
:   \hfill

    \begin{align*}
    E_i \nearrow E &\implies m(E_i) \to m(E) \\
    m(E_1) < \infty \text{ and } E_i \searrow E &\implies m(E_i) \to m(E)
    .\end{align*}

Proof
:   \hfill
    1. Break into disjoint annuli $A_2 = E_2\setminus E_1$, etc then apply countable disjoint additivity to $E = \disjoint A_i$.

    2. Use $E_1 = (\disjoint E_j\setminus E_{j+1}) \disjoint (\intersect E_j)$, taking measures yields a telescoping sum,and use countable disjoint additivity.

Theorem
:   Suppose $E$ is measurable; then for every $\eps>0$,

    1. There exists an open $O\supset E$ with $m(O\setminus E) < \eps$
    2. There exists a closed $F\subset E$ with $m(E\setminus F) < \eps$
    3. There exists a compact $K\subset E$ with $m(E\setminus K) < \eps$.

Proof
:   \hfill

    - (1): Take $\theset{Q_i} \covers E$ and set $O = \union Q_i$.
    - (2): Since $E^c$ is measurable, produce $O\supset E^c$ with $m(O\setminus E^c) < \eps$.
      - Set $F = O^c$, so $F$ is closed.
      - Then $F\subset E$ by taking complements of $O\supset E^c$
      - $E\setminus F = O\setminus E^c$ and taking measures yields $m(E\setminus F) < \eps$
    - (3): Pick $F\subset E$ with $m(E\setminus F) < \eps/2$.
      - Set $K_n = F\intersect \DD_n$, a ball of radius $n$ about $0$.
      - Then $E\setminus K_n \searrow E\setminus F$
      - Since $m(E) < \infty$, there is an $N$ such that $n\geq N \implies m(E\setminus K_n) < \eps$.

Lemma
:	Lebesgue measure is translation and dilation invariant.

Proof
: Obvious for cubes; if $Q_i \rightrightarrows E$ then $Q_i + k \rightrightarrows E + k$, etc.

\todo{Flesh out this proof.}

Theorem (Non-Measurable Sets)
: There is a non-measurable set.

Proof
:   \hfill
    - Use AOC to choose one representative from every coset of $\RR/\QQ$ on $[0, 1)$, which is countable, and assemble them into a set $N$
    - Enumerate the rationals in $[0, 1]$ as $q_j$, and define $N_j = N + q_j$. These intersect trivially.
    - Define $M \definedas \disjoint N_j$, then $[0, 1) \subseteq  M \subseteq [-1, 2)$, so the measure must be between 1 and 3.
    By translation invariance, $m(N_j) = m(N)$, and disjoint additivity forces $m(M) = 0$, a contradiction.

Proposition (Borel Characterization of Measurable Sets)
: If $E$ is Lebesgue measurable, then $E = H \disjoint N$ where $H \in F_\sigma$ and $N$ is null.

> **Useful technique:** $F_\sigma$ sets are Borel, so establish something for Borel sets and use this to extend it to Lebesgue.

Proof 
:   For every $\frac 1 n$ there exists a closed set $K_n \subset E$ such that $m(E\setminus K_n) \leq \frac 1 n$.
    Take $K = \union K_n$, wlog $K_n \nearrow K$ so $m(K) = \lim m(K_n) = m(E)$.
    Take $N\definedas E\setminus K$, then $m(N) = 0$.

Lemma
:	If $A_n$ are all measurable, $\limsup A_n$ and $\liminf A_n$ are measurable.

Proof
: Measurable sets form a sigma algebra, and these are expressed as countable unions/intersections of measurable sets.

Theorem (Borel-Cantelli)
:   Let $\{E_k\}$ be a countable collection of measurable sets.
    Then
    $$
    \sum_k m(E_k) < \infty \implies \text{ almost every } x\in \RR \text{ is in at most finitely many } E_k
    .$$

Proof
:   \hfill

    - If $E = \limsup_j E_j$ with $\sum m(E_j) < \infty$ then $m(E) = 0$.
    - If $E_j$ are measurable, then $\limsup_j E_j$ is measurable.
    - If $\sum_j m(E_j) < \infty$, then $\sum_{j=N}^\infty m(E_j) \converges{N\to\infty}\to 0$ as the tail of a convergent sequence.
    - $E = \limsup_j E_j = \intersect_{k=1}^\infty \union_{j=k}^\infty E_j \implies E \subseteq \union_{j=k}^\infty$ for all $k$
    - $E \subset \union_{j=k}^\infty \implies m(E) \leq \sum_{j=k}^\infty m(E_j) \converges{k\to\infty}\to 0$.

Lemma
:	  \hfill
    
    - Characteristic functions are measurable
    - If $f_n$ are measurable, so are $\abs{f_n}, \limsup f_n, \liminf f_n, \lim f_n$, 
    - Sums and differences of measurable functions are measurable, 
    - Cones $F(x,y) = f(x)$ are measurable, 
    - Compositions $f\circ T$ for $T$ a linear transformation are measurable,
    - "Convolution-ish" transformations $(x,y) \mapsto f(x-y)$ are measurable

Proof (Convolution)
: Take the cone on $f$ to get $F(x, y) = f(x)$, then compose $F$ with the linear transformation $T = [1, -1; 1, 0]$.


# Integration

Notation:

- "$f$ vanishes at infinity" means $f(x) \converges{\abs x \to \infty}\to 0$.
- "$f$ has small tails" means $\int_{\abs{x} \geq N} f \converges{N\to \infty}\to 0$.

## Useful Techniques

- Break integration domain up into disjoint annuli.
- Break integrals or sums into $x < 1$ and $x\geq 1$.
- Calculus techniques: Taylor series, IVT, ...
- Approximate by dense subsets of functions

- Useful facts about compactly supported continuous functions:
  - Uniformly continuous
  - Bounded



## Definitions

Definition (\$L^+\$)
:	$f\in L^+$ iff $f$ is measurable and non-negative.

Definition (Integrable)
:	A measurable function is integrable iff $\norm{f}_1 < \infty$.

Definition (The Infinity Norm)
:   \hfill
    \begin{align*}
    \norm{f}_\infty &\definedas \inf_{\alpha \geq 0} \theset{\alpha \suchthat m\theset{\abs{f} \geq \alpha} = 0}
    .\end{align*}


Definition (Essentially Bounded Functions)
: A function $f:X \to \CC$ is *essentially bounded* iff there exists a real number $c$ such that $\mu(\theset{\abs{f} > x}) = 0$, i.e. $\norm{f}_\infty < \infty$.

If $f\in L^\infty(X)$, then $f$ is equal to some bounded function $g$ almost everywhere.

Definition (L infty)
:   \hfill

    \begin{align*}
    L^\infty(X) 
    \definedas \theset{f: X\to \CC \suchthat f \text{ is essentially bounded }}
    \definedas \theset{f: X\to \CC \suchthat \pnorm{f}\infty < \infty}
    ,\end{align*}

Example:

- $f(x) = x\chi_\QQ(x)$ is essentially bounded but not bounded.



## Theorems

Useful facts about $C_c$ functions:

- Bounded almost everywhere
- Uniformly continuous


Theorem (p-Test for Integrals in \$\\RR\$)
:   \hfill
\begin{align*}
\int_0^1 {1\over x^p} < \infty \iff  p < 1 \\
\int_1^\infty {1\over x^p} < \infty \iff  p > 1 
.\end{align*}

> Slogan: big powers of $x$ help us in neighborhoods of infinity and hurt around zero

Some integrable functions:

- $\int {1\over 1 + x^2} = \arctan(x) \converges{x\to\infty} \pi/2 < \infty$
- Any bounded function (or continuous on a compact set, by EVT)
- $\int_0^1 {1 \over \sqrt{x}} < \infty$
- $\int_0^1 {1\over x^{1-\eps}} < \infty$
- $\int_1^\infty {1\over x^{1+\eps}} < \infty$

Some non-integrable functions:

- $\int_0^1 {1\over x} = \infty$.
- $\int_1^\infty {1\over x} = \infty$.
- $\int_1^\infty {1 \over \sqrt{x}} = \infty$
- $\int_1^\infty {1\over x^{1-\eps}} = \infty$
- $\int_0^1 {1\over x^{1+\eps}} = \infty$


###  Convergence Theorems

Theorem (Monotone Convergence)
:   If $f_n \in L^+$ and $f_n \nearrow f$ a.e., then
    $$
    \lim \int f_n
    = \int \lim f_n = \int f
    \quad \text{i.e.}~~ \int f_n \to \int f
    .$$

    > Needs to be positive and increasing.

Theorem (Dominated Convergence)

:   If $f_n \in L^1$ and $f_n \to f$ a.e. with $\abs {f_n} \leq g$ for some $g\in L^1$, then $f\in L^1$ and
    $$
    \lim \int f_n = \int \lim f_n = \int f \quad \text{i.e.}~~ \int f_n \to \int f < \infty
    ,$$

    and more generally,
    $$
    \int \abs{f_n - f} \to 0
    .$$

    > Positivity *not* needed.

Theorem (Generalized DCT)
:   If 
    
    - $f_n \in L^1$ with $f_n \to f$ a.e., 
    - There exist $g_n \in L^1$ with $\abs{f_n} \leq g_n$, $g_n \geq 0$.
    - $g_n\to g$ a.e. with $g\in L^1$, and 
    - $\lim \int g_n = \int g$, 

    then $f\in L^1$ and $\lim \int f_n = \int f < \infty$.

    > Note that this is the DCT with $\abs{f_n} < \abs{g}$ relaxed to $\abs{f_n} < g_n \to g\in L^1$.

Proof (Generalized DCT)
:   Proceed by showing $\limsup \int f_n \leq \int f \leq \liminf \int f_n$:

    - $\int f \geq \limsup \int f_n$:
    \begin{align*}
    \int g - \int f 
    &= \int \qty{g-f} \\
    &\leq \liminf \int \qty{g_n - f_n} \quad \text{Fatou} \\
    &= \lim \int g_n + \liminf \int (-f_n) \\
    &= \lim \int g_n - \limsup \int f_n \\
    &= \int g - \limsup \int f_n \\
    \\
    \implies \int f &\geq \limsup \int f_n
    .\end{align*}

      - Here we use $g_n - f_n \converges{n\to\infty} g-f$ with $0 \leq \abs{f_n} - f_n \leq g_n - f_n$, so $g_n - f_n$ are nonnegative (and measurable) and Fatou's lemma applies.

    - $\int f \leq \liminf \int f_n$:
    \begin{align*}
    \int g + \int f 
    &= \int(g+f) \\
    &\leq \liminf \int \qty{g_n + f_n} \\
    &= \lim \int g_n + \liminf \int f_n \\
    &= \int g + \liminf f_n \\
    \\
    \int f &\leq \liminf \int f_n
    .\end{align*}

      - Here we use that $g_n + f_n \to g+f$ with $0 \leq \abs{f_n} + f_n \leq g_n + f_n$ so Fatou's lemma again applies.
  

Lemma (Converges in \$L^1\$ implies convergence of \$L^1\$ norms)
:   If $f\in L^1$, then
    \begin{align*}
    \int\abs{f_n - f} \to 0 \iff \int \abs{f_n} \to \int \abs{f}
    .\end{align*}

Proof 
:   Let $g_n = \abs{f_n} - \abs{f_n - f}$, then $g_n \to \abs{f}$ and 
    \begin{align*}
    \abs{g_n} = \abs{ \abs{f_n} - \abs{f_n - f} } \leq \abs{f_n - (f_n - f)} = \abs{f} \in L^1
    ,\end{align*}
    so the DCT applies to $g_n$ and
    \begin{align*}
    \norm{f_n - f}_1 = \int \abs{f_n - f} + \abs{f_n} - \abs{f_n}
    = \int \abs{f_n} - g_n\\
    \to_{DCT} \lim \int \abs{f_n} - \int \abs{f}
    .\end{align*}

Theorem (Fatou's Lemma)
:   If $f_n$ is a sequence of nonnegative measurable functions, then
    \begin{align*}
    \int \liminf_n f_n &\leq \liminf_n \int f_n \\
    \limsup_n \int f_n &\leq \int \limsup_n f_n
    .\end{align*}


Theorem (Tonelli)
:   For $f(x, y)$ **non-negative and measurable**, for almost every $x\in \RR^n$, 

    - $f_x(y)$ is a **measurable** function
    - $F(x) = \int f(x, y) ~dy$ is a **measurable** function,
    - For $E$ measurable, the slices $E_x \definedas \theset{y \suchthat (x, y) \in E}$ are measurable.
    - $\int f = \int \int F$, i.e. any iterated integral is equal to the original.

Theorem (Fubini)
:   For $f(x, y)$ **integrable**, for almost every $x\in \RR^n$, 

    - $f_x(y)$ is an **integrable** function
    - $F(x) \definedas \int f(x, y) ~dy$ is an **integrable** function,
    - For $E$ measurable, the slices $E_x \definedas \theset{y \suchthat (x, y) \in E}$ are measurable.
    - $\int f = \int \int f(x,y)$, i.e. any iterated integral is equal to the original

Theorem (Fubini/Tonelli)
: If any iterated integral is **absolutely integrable**, i.e. $\int \int \abs{f(x, y)} < \infty$, then $f$ is integrable and $\int f$ equals any iterated integral.

Corollary (Measurable Slices)
:   Let $E$ be a measurable subset of $\RR^n$. Then

    - For almost every $x\in \RR^{n_1}$, the slice $E_x \definedas \theset{y \in \RR^{n_2} \mid  (x,y) \in E}$ is measurable in $\RR^{n_2}$.
    - The function

    \begin{align*}
    F: \RR^{n_1} &\to \RR \\
    x &\mapsto m(E_x) = \int_{\RR^{n_2}} \chi_{E_x} ~dy
    \end{align*}
    is measurable and 
    $$
    m(E) = \int_{\RR^{n_1}} m(E_x) ~dx 
    = \int_{\RR^{n_1}} \int_{\RR^{n_2}} \chi_{E_x} ~dy ~dx
    $$

Proof (Measurable Slices)
:   \hfill

    $\implies$:

    - Let $f$ be measurable on $\RR^n$.
    - Then the cylinders $F(x, y) = f(x)$ and $G(x, y) = f(y)$ are both measurable on $\RR^{n+1}$.
    - Write $\mathcal{A} = \theset{G \leq F} \intersect \theset{G \geq 0}$; both are measurable.


    $\impliedby$:

    - Let $A$ be measurable in $\RR^{n+1}$.
    - Define $A_x = \theset{y\in \RR \mid (x, y) \in \mathcal{A}}$, then $m(A_x) = f(x)$.
    - By the corollary, $A_x$ is measurable set, $x \mapsto A_x$ is a measurable function, and $m(A) = \int f(x) ~dx$.
    - Then explicitly, $f(x) = \chi_{A}$, which makes $f$ a measurable function.


Proposition (Differentiating Under an Integral)
:   If $\abs{\dd{}{t}f(x, t)} \leq g(x) \in L^1$, then letting $F(t) = \int f(x, t) ~dt$,
    \begin{align*}
    \dd{}{t} F(t)
    &\definedas \lim_{h \rightarrow 0} \int \frac{f(x, t+h)-f(x, t)}{h} d x \\
    &\equalsbecause{DCT} \int \dd{}{t} f(x, t) ~dx
    .\end{align*}

    To justify passing the limit, let $h_k \to 0$ be any sequence and define
    $$
    f_k(x, t) = \frac{f(x, t+h_k)-f(x, t)}{h_k}
    ,$$
    so $f_k \converges{\text{pointwise}}\to \dd{}{t}f$.

    Apply the MVT to $f_k$ to get $f_k(x, t) = f_k(\xi, t)$ for some $\xi \in [0, h_k]$, and show that $f_k(\xi, t) \in L_1$.


Proposition (Swapping Sum and Integral)
: If $f_n$ are non-negative and $\sum \int \abs f_n < \infty$, then $\sum \int f_n = \int \sum f_n$.

Proof
: MCT. Let $F_N = \sum^N f_n$ be a finite partial sum; then there are simple functions $\phi_n \nearrow f_n$ and so $\sum^N \phi_n \nearrow F_N$, so apply MCT.

Lemma
:   If $f_k \in L^1$ and $\sum \norm{f_k}_1 < \infty$ then $\sum f_k$ converges almost everywhere and in $L^1$.

Proof
:   Define $F_N = \sum^N f_k$ and $F = \lim_N F_N$, then $\norm{F_N}_1 \leq \sum^N \norm{f_k} < \infty$ so $F\in L^1$ and $\norm{F_N - F}_1 \to 0$ so the sum converges in $L^1$.
    Almost everywhere convergence: ?

## $L^1$ Facts

Lemma (Translation Invariance)
:   The Lebesgue integral is translation invariant, i.e. 
    $\int f(x) ~dx = \int f(x + h) ~dx$ for any $h$.

Proof
:   \hfill
    - For characteristic functions, $\int_E f(x+h) = \int_{E + h} f(x) = m(E+h) = m(E) = \int_E f$ by translation invariance of measure.
    - So this also holds for simple functions by linearity
    - For $f\in L^+$, choose $\phi_n \nearrow f$ so $\int \phi_n \to \int f$.
    - Similarly, $\tau_h \phi_n \nearrow \tau_h f$ so $\int \tau_h f \to \int f$
    - Finally $\theset{\int \tau_h \phi} = \theset{\int \phi}$ by step 1, and the suprema are equal by uniqueness of limits.

Lemma (Integrals Distribute Over Disjoint Sets)
: If $X \subseteq A \union B$, then $\int_X f \leq \int_A f + \int_{A^c} f$ with equality iff $X = A\disjoint B$.


Lemma (Unif. Cts. L1 Functions Vanish at Infinity)
: If $f \in L^1$ and $f$ is uniformly continuous, then $f(x) \converges{\abs{x}\to\infty}\to 0$.

> Doesn't hold for general $L^1$ functions, take any train of triangles with height 1 and summable areas.

Lemma (L1 Functions Have Small Tails)
: If $f\in L^1$, then for every $\varepsilon$ there exists a radius $R$ such that if $A = B_R(0)^c$, then $\int_A \abs f < \varepsilon$. 

Proof
:   Approximate with compactly supported functions.
    Take $g\converges{L_1}\to f$ with $g\in C_c$, then choose $N$ large enough so that $g=0$ on $E\definedas B_N(0)^c$, then $\int_E \abs{f} \leq \int_E\abs{f-g} + \int_E \abs{g}$.

Lemma (\$L^1\$ Functions Have Absolutely Continuity)
: $m(E) \to 0 \implies \int_E f \to 0$.

Proof
:   Approximate with compactly supported functions.
    Take $g\converges{L_1}\to f$, then $g \leq M$ so $\int_E{f} \leq \int_E{f-g} + \int_E g \to 0 + M \cdot m(E) \to 0$.

Lemma (\$L^1\$ Functions Are Finite Almost Everywhere)
: If $f\in L^1$, then $m(\theset{f(x) = \infty}) = 0$.

Proof 
:   Idea: Split up domain
    Let $A = \theset{f(x) = \infty}$, then $\infty > \int f = \int_A f + \int_{A^c} f = \infty \cdot m(A) + \int_{A^c} f \implies m(X) =0$.

Proposition (Continuity in \$L^1\$)
: $$\norm{\tau_h f - f}_1 \converges{h\to 0}\to 0$$

Proof
:   Approximate with compactly supported functions.
    Take $g\converges{L_1}\to f$ with $g\in C_c$.
    \begin{align*}
    \int f(x+h) - f(x) 
    &\leq \int f(x+h) - g(x+h) + \int g(x+h) - g(x) + \int g(x) - f(x) \\
    &\converges{?\to?}\to 2 \varepsilon + \int g(x+h) - g(x) \\
    &= \int_K g(x+h) - g(x) + \int_{K^c} g(x+h) - g(x)\\
    &\converges{??}\to 0
    ,\end{align*}
    which follows because we can enlarge the support of $g$ to $K$ where the integrand is zero on $K^c$, then apply uniform continuity on $K$.

Proposition (Integration by Parts, Special Case)
:   \begin{align*}
    F(x):=\int_{0}^{x} f(y) d y \quad \text { and } \quad G(x):=\int_{0}^{x} g(y) d y \\ 
    \implies
    \int_{0}^{1} F(x) g(x) d x=F(1) G(1)-\int_{0}^{1} f(x) G(x) d x
    .\end{align*}

Proof 
: Fubini-Tonelli, and sketch region to change integration bounds.

Theorem (Lebesgue Density)
: \begin{align*}
  A_{h}(f)(x):=\frac{1}{2 h} \int_{x-h}^{x+h} f(y) d y
  \implies \norm{A_h(f) - f} \converges{h\to 0}\to 0
  .\end{align*}

Proof
: Fubini-Tonelli, and sketch region to change integration bounds, and continuity in $L^1$.


## $L^p$ Spaces

Lemma
:   The following are dense subspaces of $L^2([0, 1])$:

    - Simple functions
    - Step functions
    - $C_0([0, 1])$
    - Smoothly differentiable functions $C_0^\infty([0, 1])$
    - Smooth compactly supported functions $C_c^\infty$
Theorem
:
\begin{align*}
m(X) < \infty \implies \lim_{p\to\infty} \norm{f}_p = \norm{f}_\infty 
.\end{align*}

Proof
:   \hfill
    - Let $M = \norm{f}_\infty$.
    - For any $L < M$, let $S = \theset{\abs{f} \geq L}$. 
    - Then $m(S) > 0$ and

    \begin{align*}
    \pnorm{f}p 
    &= \left( \int_X \abs{f}^p \right)^{\frac 1 p} \\
    &\geq \left( \int_S \abs{f}^p \right)^{\frac 1 p} \\
    &\geq L ~m(S)^{\frac 1 p} \converges{p\to\infty}\to L \\
    &\implies \liminf_p \pnorm{f}p \geq M
    .\end{align*}

    We also have
    \begin{align*}
    \pnorm{f}p 
    &=  \left( \int_X \abs{f}^p \right)^{\frac 1 p} \\
    &\leq \left( \int_X M^p \right)^{\frac 1 p} \\
    &= M ~m(X)^{\frac 1 p} \mapsvia{p\to\infty} M \\
    &\implies \limsup_p \pnorm{f}p \leq M \qed
    .\end{align*}


Theorem (Dual Lp Spaces)
:   For $p\neq \infty$, $(L^p)\dual \cong L^q$.

Proof (p=1)
: ?

Proof (p=2)
: Use Riesz Representation for Hilbert spaces.
 
:::{.proof}
$L^1 \subset (L^\infty)\dual$, since the isometric mapping is always injective, but *never* surjective. 
:::

# Fourier Transform and Convolution

## The Fourier Transform

Definition (Convolution)
: $$f * g(x)=\int f(x-y) g(y) d y .$$


Definition (The Fourier Transform)
:   \hfill
    \begin{align*}
    \hat f(\xi) = \int f(x) ~e^{2\pi i x \cdot \xi} ~dx
    .\end{align*}

Lemma
: If $\hat f = \hat g$ then $f=g$ almost everywhere.

Lemma (Riemann-Lebesgue\: Fourier transforms have small tails)
:   \hfill
    
    \begin{align*}
    f\in L^1 \implies
    \hat{f}(\xi) \rightarrow 0 \text { as }|\xi| \rightarrow \infty
    ,\end{align*}

    if $f \in L^1$, then $\hat f$ is continuous and bounded.

Proof
:   \hfill 
    - Boundedness:
    \begin{align*}
    \abs{\hat f(\xi)} 
    \leq \int \abs{f}\cdot \abs{e^{2\pi i x\cdot \xi }} 
    = \pnorm{f}{1}
    .\end{align*}

    - Continuity:
      - $\abs{\hat{f}(\xi_n) - \hat{f} (\xi) }$
      - Apply DCT to show $a\converges{n\to\infty}\to 0$.


Theorem (Fourier Inversion)
:   \hfill
    \begin{align*}
    f(x)=\int_{\mathbb{R}^{n}} \widehat{f}(x) e^{2 \pi i x \cdot \xi} d \xi
    .\end{align*}

Proof
:   Idea: Fubini-Tonelli doesn't work directly, so introduce a convergence factor, take limits, and use uniqueness of limits.

    - Take the modified integral:
    
    \begin{align*}
    I_t(x)
    &= \int \hat f(\xi) ~e^{2\pi i x \cdot \xi} ~e^{-\pi t^2 \abs{\xi}^2} \\
    &= \int \hat f(\xi) \phi(\xi) \\
    &= \int f(\xi) \hat \phi(\xi) \\
    &= \int f(\xi) \widehat{\hat g}(\xi - x) \\
    &= \int f(\xi) g_t(x - \xi)  ~d\xi \\
    &= \int f(y-x) g_t(y) ~dy  \quad (\xi = y-x)\\
    &= (f \ast g_t) \\
    &\to f \text{ in $L^1$ as }t \to 0
    .\end{align*}

    - We also have
    \begin{align*}
    \lim_{t\to 0} I_t(x)
    &= 
    \lim_{t\to 0} \int \hat f(\xi) ~e^{2\pi i x \cdot \xi} ~e^{-\pi t^2 \abs{\xi}^2} \\
    &= 
    \lim_{t\to 0} \int \hat f(\xi) \phi(\xi) \\
    &=_{DCT} 
    \int \hat f(\xi) \lim_{t\to 0} \phi(\xi) \\
    &=
    \int \hat f(\xi) ~e^{2\pi i x \cdot \xi} \\
    .\end{align*}

    - So 
    \begin{align*}
    I_t(x) \to \int \hat f(\xi) ~e^{2\pi i x \cdot \xi} ~\text{ pointwise and }~\pnorm{I_t(x) - f(x)}{1} \to 0
    .\end{align*}

    - So there is a subsequence $I_{t_n}$ such that $I_{t_n}(x) \to f(x)$ almost everywhere
    - Thus $f(x) = \int \hat f(\xi) ~e^{2\pi i x \cdot \xi}$ almost everywhere by uniqueness of limits. 


Proposition (Eigenfunction of the Fourier Transform)
: \hfill
  \begin{align*}
  g(x) \definedas e^{-\pi \abs{t}^2} \implies \hat g(\xi) = g(\xi) \qtext{and}
  \hat g_t(x) = g(tx) = e^{-\pi t^2 \abs{x}^2}
  .\end{align*}

Proposition (Properties of the Fourier Transform)
: 
\begin{align*}
??? & ??
.\end{align*}

## Approximate Identities 

Definition (Dilation)
: 
\begin{align*}
\phi_{t}(x) = t^{-n} \phi\left(t^{-1} x\right)
.\end{align*}


Definition (Approximation to the Identity)
:   For $\phi\in L^1$, the dilations satisfy $\int \phi_t = \int \phi$, and if $\int \phi = 1$ then $\phi$ is an *approximate identity*. 
    
    Example: $\phi(x) = e^{-\pi x^2}$


Theorem (Convolution Against Approximate Identities Converge in \$L^1\$)
: 
\begin{align*}
\pnorm{f \ast \phi_t - f}{1} \converges{t\to 0}\to 0
.\end{align*}


Proof
: 
\begin{align*}
\norm{f - f\ast \phi_t}_1 
&= \int f(x) - \int f(x-y)\phi_t(y) ~dy dx \\
&= \int f(x)\int \phi_t(y) ~dy - \int f(x-y)\phi_t(y) ~dy dx \\
&= \int \int \phi_t(y)[f(x) - f(x-y)] ~dy dx \\
&=_{FT} \int \int \phi_t(y)[f(x) - f(x-y)] ~dx dy \\
&= \int \phi_t(y) \int f(x) - f(x-y) ~dx dy \\
&= \int \phi_t(y) \norm{f - \tau_y f}_1 dy \\
&= \int_{y < \delta} \phi_t(y) \norm{f - \tau_y f}_1 dy  +
\int_{y \geq \delta} \phi_t(y) \norm{f - \tau_y f}_1 dy \\
&\leq \int_{y < \delta} \phi_t(y) \varepsilon +
\int_{y \geq \delta} \phi_t(y) \left( \norm{f}_1 + \norm{\tau_y f}_1 \right) dy \quad\text{by continuity in } L^1 \\
&\leq \varepsilon + 
2\norm{f}_1 \int_{y \geq \delta} \phi_t(y) dy \\
&\leq \varepsilon + 2\norm{f}_1 \cdot \varepsilon \quad\text{since $\phi_t$ has small tails} \\
&\converges{\eps\to 0}\to 0 
.\end{align*}

Theorem (Convolutions Vanish at Infinity)
: 
\begin{align*}
f,g \in L^1 \text{ and  bounded}  \implies \lim_{|x| \rightarrow \infty} (f * g)(x) = 0
.\end{align*}

Proof
:   \hfill
    
    - Choose $M \geq f,g$.
    
    - By small tails, choose $N$ such that $\int_{B_N^c} \abs{f}, \int_{B_n^c} \abs{g} < \varepsilon$

    - Note 
    \begin{align*}
    \abs{f \ast g} \leq \displaystyle\int \abs{f(x-y)} ~\abs{g(y)} ~dy \definedas I
    .\end{align*}

    - Use $\abs{x} \leq \abs{x-y} + \abs{y}$, take $\abs{x}\geq 2N$ so either
    \begin{align*}
    \abs{x-y} \geq N \implies I \leq \int_{\theset{x-y \geq N}} \abs{f(x-y)}M ~dy\leq \varepsilon M \to 0
    \end{align*}
      then
    \begin{align*}
      \abs{y} \geq N \implies I \leq \int_{\theset{y \geq N}} M\abs{g(y)} ~dy\leq  M \varepsilon \to 0
    .\end{align*}


Proposition (Young's Inequality?)
:
\begin{align*}
{1\over r} \definedas {1\over p} + {1\over q} - 1 \implies \pnorm{f \ast g}{r} \leq \pnorm{f}{p} \norm{g}{q}
.\end{align*}

Corollary
: Take $q = 1$ to obtain
\begin{align*}
\pnorm{f \ast g}p \leq \norm{f}p \norm{g}1
.\end{align*}

Corollary
: If $f, g \in L^1$ then $f\ast g\in L^1$.


# Functional Analysis

## Definitions

Notation: $H$ denotes a Hilbert space.

Definition (Orthonormal Sequence)
: ?

Definition (Basis)
: A set $\theset{u_n}$ is a *basis* for a Hilbert space $\mch$ iff it is dense in $\mch$.

Definition (Complete)
: A collection of vectors $\theset{u_n}\subset H$ is *complete* iff $\inner{x}{u_n} = 0$ for all $n \iff x = 0$ in $H$.

Definition (Dual Space)
: 
\begin{align*}
X\dual \definedas \theset{L :X\to \CC \suchthat L \text{ is continuous }}
.\end{align*}

Definition
:   A map $L: X \to \CC$ is a linear functional iff
    \begin{align*}
    L(\alpha\vector x + \vector y) = \alpha L(\vector x) + L(\vector y).
    .\end{align*}

Definition (Operator Norm)
: 
\begin{align*}
\norm{L}_{X\dual} \definedas \sup_{ \substack{x\in X \\ \norm{x} = 1} } \abs{L(x)}
.\end{align*}

Definition (Banach Space)
: A complete normed vector space.

Definition (Hilbert Space)
: An inner product space which is a Banach space under the induced norm.

## Theorems

Theorem (Bessel's Inequality)
:   For any orthonormal set $\theset{u_n} \subseteq \mch$ a Hilbert space (not necessarily a basis),
    \begin{align*}
    \left\|x-\sum_{n=1}^{N}\left\langle x, u_{n}\right\rangle u_{n}\right\|^{2}=\|x\|^{2}-\sum_{n=1}^{N}\left|\left\langle x, u_{n}\right\rangle\right|^{2}
    \end{align*}
    and thus
    \begin{align*}
    \sum_{n=1}^{\infty}\left|\left\langle x, u_{n}\right\rangle\right|^{2} \leq\|x\|^{2}
    .\end{align*}


Proof
:   \hfill 

    - Let $S_N = \sum_{n=1}^N \inner{x}{u_n} u_n$
    \begin{align*}
    \norm{x - S_N}^2 
    &= \inner{x - S_n}{x - S_N} \\
    &= \norm{x}^2 + \norm{S_N}^2 - 2\Re\inner{x}{S_N} \\
    &= \norm{x}^2 + \norm{S_N}^2 - 2\Re \inner{x}{\sum_{n=1}^N \inner{x}{u_n}u_n} \\
    &= \norm{x}^2 + \norm{S_N}^2 - 2\Re \sum_{n=1}^N \inner{x}{ \inner{x}{u_n}u_n} \\
    &= \norm{x}^2 + \norm{S_N}^2 - 2\Re \sum_{n=1}^N \overline{\inner{x}{u_n}}\inner{x}{u_n} \\
    &= \norm{x}^2 + \left\|\sum_{n=1}^N \inner{x}{u_n} u_n\right\|^2 - 2 \sum_{n=1}^N \abs{\inner{x}{u_n}}^2 \\
    &= \norm{x}^2 + \sum_{n=1}^N \abs{\inner{x}{u_n}}^2 - 2 \sum_{n=1}^N \abs{\inner{x}{u_n}}^2 \\
    &= \norm{x}^2 - \sum_{n=1}^N \abs{\inner{x}{u_n}}^2
    .\end{align*}

    - By continuity of the norm and inner product, we have
    \begin{align*}
    \lim_{N\to\infty} \norm{x - S_N}^2 
    &= \lim_{N\to\infty} \norm{x}^2 - \sum_{n=1}^N \abs{\inner{x}{u_n}}^2 \\
    \implies \norm{x - \lim_{N\to\infty} S_N}^2 &= \norm{x}^2 - \lim_{N\to\infty}\sum_{n=1}^N \abs{\inner{x}{u_n}}^2\\
    \implies 
    \norm{x - \sum_{n=1}^\infty \inner{x}{u_n} u_n}^2 &= \norm{x}^2 - 
    \sum_{n=1}^\infty \abs{\inner{x}{u_n}}^2
    .\end{align*}

    - Then noting that $0 \leq \norm{x - S_N}^2$, 
    \begin{align*}
    0 &\leq 
    \norm{x}^2 - 
    \sum_{n=1}^\infty \abs{\inner{x}{u_n}}^2 \\
    \implies 
    \sum_{n=1}^\infty \abs{\inner{x}{u_n}}^2 &\leq 
    \norm{x}^2 \qed
    .\end{align*}




Theorem (Riesz Representation for Hilbert Spaces)
:   If $\Lambda$ is a continuous linear functional on a Hilbert space $H$, then there exists a unique $y \in H$ such that
    \begin{align*}
    \forall x\in H,\quad \Lambda(x) = \inner{x}{y}.
    .\end{align*}

Proof
:   \hfill
    - Define $M \definedas \ker \Lambda$.
    - Then $M$ is a closed subspace and so $H = M \oplus M^\perp$
    - There is some $z\in M^\perp$ such that $\norm{z} = 1$.
    - Set $u \definedas \Lambda(x) z - \Lambda(z) x$
    - Check 

    $$\Lambda(u) = \Lambda(\Lambda(x) z - \Lambda(z) x) = \Lambda(x) \Lambda(z) - \Lambda(z) \Lambda(x) = 0 \implies u\in M$$

    - Compute

    \begin{align*}
    0 &= \inner{u}{z} \\ 
    &= \inner{\Lambda(x) z - \Lambda(z) x}{z} \\
    &= \inner{\Lambda(x) z}{z} - \inner{\Lambda(z) x}{z} \\
    &= \Lambda(x) \inner{z}{z} - \Lambda(z) \inner{x}{z} \\
    &= \Lambda(x) \norm{z}^2 - \Lambda(z) \inner{x}{z} \\
    &= \Lambda(x) - \Lambda(z) \inner{x}{z} \\
    &= \Lambda(x) -  \inner{x}{\overline{\Lambda(z)} z}
    ,\end{align*}

    - Choose $y \definedas \overline{\Lambda(z)} z$.
    - Check uniqueness:

    \begin{align*}
    \inner{x}{y} &= \inner{x}{y'} \quad\forall x \\
    \implies  \inner{x}{y-y'} &= 0 \quad\forall x \\
    \implies \inner{y-y'}{y-y'} &= 0 \\
    \implies \norm{y-y'} &= 0 \\
    \implies y-y' &= \vector 0 \implies y = y'
    .\end{align*}

Theorem (Continuous iff Bounded)
:   Let $L:X \to \CC$ be a linear functional, then the following are equivalent:

    1. $L$ is continuous
    2. $L$ is continuous at zero
    3. $L$ is bounded, i.e. $\exists c\geq 0 \suchthat \abs{L(x)} \leq c \norm{x}$ for all $x\in H$

Proof
:   \hfill
    $2 \implies 3$:
    Choose $\delta < 1$ such that 
    $$
    \norm{x} \leq \delta \implies \abs{L(x)} < 1.
    $$
    Then
    \begin{align*}
    \abs{L(x)} 
    &= \abs{L\left( \frac{\norm x}{\delta} \frac{\delta }{\norm x} x \right)} \\
    &= \frac{\norm x}{\delta} ~\abs{L\left( \delta \frac{x }{\norm x} \right)} \\
    &\leq \frac{\norm x}{\delta} 1
    ,\end{align*}
    so we can take $c = \frac 1 \delta$. $\qed$

    $3 \implies 1$:

    We have $\abs{L(x-y)} \leq c\norm{x-y}$, so given $\varepsilon \geq 0$ simply choose $\delta = \frac \varepsilon c$.

Theorem (Operator Norm is a Norm)
: If $H$ is a Hilbert space, then $(H\dual, \norm{\wait}_{\text{op}})$ is a normed space.

Proof
: The only nontrivial property is the triangle inequality, but
  \begin{align*}
  \pnorm{L_1 + L_2}{\op} = \sup \abs{L_1(x) + L_2(x)} \leq \sup \abs{L_1(x)} + \abs{\sup L_2(x)} = \pnorm{L_1}\op + \pnorm{L_2}\op
  .\end{align*}

Theorem (Completeness in Operator Norm)
: If $X$ is a normed vector space, then $(X\dual, \norm{\wait}_{\text{op}})$ is a Banach space.

Proof
:   \hfill
    - Let $\theset{L_n}$ be Cauchy in $X\dual$.
    
    - Then for all $x\in C$, $\theset{L_n(x)} \subset \CC$ is Cauchy and converges to something denoted $L(x)$.
    
    - Need to show $L$ is continuous and $\norm{L_n - L} \to 0$.
    
    - Since $\theset{L_n}$ is Cauchy in $X\dual$, choose $N$ large enough so that
    \begin{align*}
    n, m \geq N \implies \norm{L_n - L_m} < \varepsilon \implies \abs{L_m(x) - L_n(x)} < \varepsilon \quad \forall x \suchthat \norm{x} = 1
    .\end{align*}
    
    - Take $n\to \infty$ to obtain
    \begin{align*}m \geq N 
    &\implies \abs{L_m(x) - L(x)} < \varepsilon \quad \forall x \suchthat \norm{x} = 1\\
    &\implies \norm{L_m - L} < \varepsilon \to 0
    .\end{align*}
    
    - Continuity:
    \begin{align*}
    \abs{L(x)} &= \abs{L(x) - L_n(x) + L_n(x)} \\
    &\leq  \abs{L(x) - L_n(x)} + \abs{L_n(x)} \\
    &\leq \varepsilon \norm{x} + c\norm{x} \\
    &= (\varepsilon + c)\norm{x} \qed
    .\end{align*}

Theorem (Riesz-Fischer)
:   Let $U = \theset{u_n}_{n=1}^\infty$ be an orthonormal set (not necessarily a basis), then

    1. There is an isometric surjection

    \begin{align*}
    \mathcal{H} &\to \ell^2(\NN) \\
    \vector x &\mapsto \theset{\inner{\vector x}{\vector u_n}}_{n=1}^\infty
    \end{align*}

    i.e. if $\theset{a_n} \in \ell^2(\NN)$, so $\sum \abs{a_n}^2 < \infty$, then there exists a $\vector x \in \mathcal{H}$ such that
    $$
    a_n = \inner{\vector x}{\vector u_n} \quad \forall n.
    $$

    2. $\vector x$ can be chosen such that
    $$
    \norm{\vector x}^2 = \sum \abs{a_n}^2
    $$

    > Note: the choice of $\vector x$ is unique $\iff$ $\theset{u_n}$ is **complete**, i.e. $\inner{\vector x}{\vector u_n} = 0$ for all $n$ implies $\vector x = \vector 0$.

Proof
:   \hfill
    
    - Given $\theset{a_n}$, define $S_N = \sum^N a_n \vector u_n$.
    - $S_N$ is Cauchy in $\mathcal{H}$ and so $S_N \to \vector x$ for some $\vector x \in \mathcal{H}$.
    - $\inner{x}{u_n} = \inner{x - S_N}{u_n} + \inner{S_N}{u_n} \to a_n$
    - By construction, $\norm{x-S_N}^2 = \norm{x}^2 - \sum^N \abs{a_n}^2 \to 0$, so $\norm{x}^2 = \sum^\infty \abs{a_n}^2$.



# Extra Problems

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


# Practice Exam (November 2014)

## 1: Fubini-Tonelli

### a

Carefully state Tonelli's theorem for a nonnegative function $F(x, t)$ on $\RR^n\cross \RR$.

### b

Let $f:\RR^n\to [0, \infty]$ and define
\begin{align*}
\mca \definedas \theset{(x, t) \in \RR^n\cross \RR \suchthat 0\leq t \leq f(x)}
.\end{align*}

Prove the validity of the following two statements:

1. $f$ is Lebesgue measurable on $\RR^{n} \iff \mca$ is a Lebesgue measurable subset of $\RR^{n+1}$.
2. If $f$ is Lebesgue measurable on $\RR^n$ then
\begin{align*}
m(\mathcal{A})=\int_{\mathbb{R}^{n}} f(x) d x=\int_{0}^{\infty} m\left(\left\{x \in \mathbb{R}^{n}\suchthat f(x) \geq t\right\}\right) d t
.\end{align*}


## 2: Convolutions and the Fourier Transform

### a

Let $f, g\in L^1(\RR^n)$ and give a definition of $f\ast g$.

### b

Prove that if $f, g$ are integrable and bounded, then
\begin{align*}
(f\ast g)(x) \converges{\abs x\to\infty}\to 0
.\end{align*}


### c

1. Define the *Fourier transform* of an integrable function $f$ on $\RR^n$.
2. Give an outline of the proof of the Fourier inversion formula.
3. Give an example of a function $f\in L^1(\RR^n)$ such that $\hat{f}$ is not in $L^1(\RR^n)$.


## 3: Hilbert Spaces

Let $\theset{u_n}_{n=1}^\infty$ be an orthonormal sequence in a Hilbert space $H$.

### a

Let $x\in H$ and verify that 
\begin{align*}
\left\|x-\sum_{n=1}^{N}\left\langle x, u_{n}\right\rangle u_{n}\right\|_H^{2}
=
\|x\|_H^{2}-\sum_{n=1}^{N}\left|\left\langle x, u_{n}\right\rangle\right|^{2}
.\end{align*}
for any $N\in \NN$ and deduce that
\begin{align*}
\sum_{n=1}^{\infty}\left|\left\langle x, u_{n}\right\rangle\right|^{2} \leq\|x\|_H^{2}
.\end{align*}


### b

Let $\theset{a_n}_{n\in \NN} \in \ell^2(\NN)$ and prove that there exists an $x\in H$ such that $a_n = \inner{x}{u_n}$ for all $n\in \NN$, and moreover $x$ may be chosen such that 
\begin{align*}
\norm{x}_H = \qty{ \sum_{n\in \NN} \abs{a_n}^2}^{1\over 2}
.\end{align*}

Proof
:   \hfill

    - Take $\theset{a_n} \in \ell^2$, then note that $\sum \abs{a_n}^2 < \infty \implies$ the tails vanish.

    - Define $x \definedas \displaystyle\lim_{N\to\infty} S_N$ where $S_N = \sum_{k=1}^N a_k u_k$

    - $\theset{S_N}$ is Cauchy and $H$ is complete, so $x\in H$.

    - By construction, 
    \begin{align*}
    \inner{x}{u_n} = \inner{\sum_k a_k u_k}{u_n} = \sum_k a_k \inner{u_k}{u_n} = a_n 
    \end{align*}
    since the $u_k$ are all orthogonal.
    
    - By Pythagoras since the $u_k$ are normal,
    \begin{align*}
    \norm{x}^2 = \norm{\sum_k a_k u_k}^2 = \sum_k \norm{a_k u_k}^2 = \sum_k \abs{a_k}^2
    .\end{align*}

### c
Prove that if $\theset{u_n}$ is *complete*, Bessel's inequality becomes an equality.

Proof
:   Let $x$ and $u_n$ be arbitrary. 

    \begin{align*}
    \inner{x - \sum_{k=1}^\infty \inner{x}{u_k}u_k }{u_n}
    &=
    \inner{x}{u_n}
    -
    \inner{\sum_{k=1}^\infty \inner{x}{u_k}u_k }{u_n} \\
    &=
    \inner{x}{u_n}
    -
    \sum_{k=1}^\infty  \inner{\inner{x}{u_k}u_k }{u_n} \\
    &=
    \inner{x}{u_n}
    -
    \sum_{k=1}^\infty  \inner{x}{u_k} \inner{u_k }{u_n} \\
    &= \inner{x}{u_n} - \inner{x}{u_n} = 0 \\
    \implies 
    x - \sum_{k=1}^\infty \inner{x}{u_k}u_k &= 0 \quad\text{by completeness}
    .\end{align*}

    So 
    \begin{align*}
    x = \sum_{k=1}^\infty \inner{x}{u_k} u_k
    \implies
    \norm{x}^2 = \sum_{k=1}^\infty \abs{\inner{x}{u_k}}^2. \qed
    .\end{align*}


## 4: $L^p$ Spaces


### a
Prove Holder's inequality:
let $f\in L^p, g\in L^q$ with $p, q$ conjugate, and show that
\begin{align*}
\pnorm{fg}p \leq \pnorm{f}p \cdot \pnorm{g}q
.\end{align*}

### b
Prove Minkowski's Inequality:
\begin{align*}
1\leq p < \infty \implies \pnorm{f+g}{p} \leq \pnorm{f}{p}+ \pnorm{g}{p}
.\end{align*}
Conclude that if $f, g\in L^p(\RR^n)$ then so is $f+g$.

### c
Let $X = [0, 1] \subset \RR$.

1. Give a definition of the Banach space $L^\infty(X)$ of essentially bounded functions of $X$.

2. Let $f$ be non-negative and measurable on $X$, prove that
\begin{align*}
\int_X f(x)^p \,dx \converges{p\to\infty}\to
\begin{dcases}
\infty \quad\text{or} \\
m\qty{\theset{f\inv(1)}}
\end{dcases}
,\end{align*}
and characterize the functions of each type

Proof
:   \hfill
    \begin{align*}
    \int f^p 
    &= \int_{x < 1} f^p + \int_{x=1}f^p + \int_{x > 1} f^p\\
    &= \int_{x < 1} f^p + \int_{x=1}1 + \int_{x > 1} f^p \\
    &= \int_{x < 1} f^p + m(\theset{f = 1}) + \int_{x > 1} f^p \\
    &\converges{p\to\infty}\to 0  + m(\theset{f = 1}) + 
    \begin{cases} 
    0 & m(\theset{x\geq 1}) = 0 \\ 
    \infty & m(\theset{x\geq 1}) > 0.
    \end{cases}
    \end{align*} 

\todo{Justify passing limit into integrals.}


## 5: Dual Spaces

Let $X$ be a normed vector space.

### a
Give the definition of what it means for a map $L:X\to \CC$ to be a *linear functional*.

### b
Define what it means for $L$ to be *bounded* and show $L$ is bounded $\iff L$ is continuous.


### c
Prove that $(X\dual, \norm{\wait}_{\op})$ is a Banach space.



# Midterm Exam 2 (November 2018)

## 1 (Integration by Parts)

Let $f, g\in L^1([0, 1])$, define $F(x) = \int_0^x f$ and $G(x) = \int_0^x g$, and show
\begin{align*}
\int_0^1 F(x)g(x) \,dx = F(1)G(1) - \int_0^1 f(x) G(x) \, dx
.\end{align*}

## 2
Let $\phi\in L^1(\RR^n)$ such that $\int \phi = 1$ and define $\phi_t(x) = t^{-n}\phi(t\inv x)$.

Show that if $f$ is bounded and uniformly continuous then $f\ast \phi_t \converges{t\to 0} f$ uniformly.

## 3

Let $g\in L^\infty([0, 1])$.

a. Prove
\begin{align*}
\norm{g}_{L^p([0, 1])}  \converges{p\to\infty}\to \norm{g}_{L^\infty([0, 1])}
.\end{align*}

b. Prove that the map
\begin{align*}
\Lambda_g: L^1([0, 1]) &\to \CC \\
f &\mapsto \int_0^1 fg
\end{align*}
  defines an element of $L^1([0, 1])\dual$ with $\norm{\Lambda_g}_{L^1([0, 1])\dual}= \norm{g}_{L^\infty([0, 1])}$.

> Note: 4 is a repeat.

# Midterm Exam 2 (December 2014)

## 1

> Note: (a) is a repeat.

- Let $\Lambda\in L^2(X)\dual$.
  - Show that $M\definedas \theset{f\in L^2(X) \suchthat \Lambda(f) = 0} \subseteq L^2(X)$ is a closed subspace, and $L^2(X) = M \oplus M\perp$.
  - Prove that there exists a unique $g\in L^2(X)$ such that $\Lambda(f) = \int_X g \bar f$.

## 2

a. In parts:
  - Given a definition of $L^\infty(\RR^n)$.
  - Verify that $\norm{\wait}_\infty$ defines a norm on $L^\infty(\RR^n)$.
  - Carefully proved that $(L^\infty(\RR^n), \norm{\wait}_\infty)$ is a Banach space.

b. Prove that for any measurable $f:\RR^n \to \CC$,
\begin{align*}
L^1(\RR^n) \intersect L^\infty(\RR^n) \subset L^2(\RR^n) \qtext{and} \norm{f}_2 \leq \norm{f}_1^{1\over 2} \cdot \norm{f}_\infty^{1\over 2}
.\end{align*}

## 3

a. Prove that if $f, g: \RR^n\to \CC$ is both measurable then $F(x, y) \definedas f(x)$ and $h(x, y)\definedas f(x-y) g(y)$ is measurable on $\RR^n\cross \RR^n$.

b. Show that if $f\in L^1(\RR^n) \intersect L^\infty(\RR^n)$ and $g\in L^1(\RR^n)$, then $f\ast g \in L^1(\RR^n) \intersect L^\infty(\RR^n)$ is well defined, and carefully show that it satisfies the following properties:
\begin{align*}
\norm{f\ast g}_\infty &\leq \norm{g}_1 \norm{f}_\infty
\norm{f\ast g}_1      &\leq \norm{g}_1 \norm{f}_1
\norm{f\ast g}_2      &\leq \norm{g}_1 \norm{f}_2
.\end{align*}

> Hint: first show $\abs{f\ast g}^2 \leq \norm{g}_1 \qty{ \abs{f}^2 \ast \abs{g}}$.

## 4 (Weierstrass Approximation Theorem)

> Note: (a) is a repeat.

Let $f: [0, 1]\to \RR$ be continuous, and prove the Weierstrass approximation theorem: for any $\eps> 0$ there exists a polynomial $P$ such that $\norm{f - P}_{\infty} < \eps$.

# Inequalities and Equalities

Proposition (Reverse Triangle Inequality)
:	\hfill
  \[  
  \abs{\norm{x} - \norm{y}} \leq \norm{x - y}
  .\]

Proposition (Chebyshev's Inequality)
:	\hfill
  \[  
  \mu(\{x:|f(x)|>\alpha\}) \leq\left(\frac{\pnorm{f}{p}}{\alpha}\right)^{p}
  .\]

Proposition (Holder's Inequality When Surjective)
:	\hfill
  \[  
  \frac 1 p + \frac 1 q = 1 \implies \pnorm{f g}{1} \leq \pnorm{f}{p} \pnorm{g}{q}
  .\]

*Application:*
For finite measure spaces,
\[
1 \leq p < q \leq \infty \implies L^q \subset L^p \quad (\text{ and } \ell^p \subset \ell^q)
.\]

Proof (Holder's Inequality) 
: Fix $p, q$, let $r = \frac q p$ and $s = \frac{r}{r-1}$ so $r\inv + s\inv = 1$.
  Then let $h = \abs{f}^p$:
  
  \[  
  \pnorm{f}{p}^p 
  = \pnorm{h\cdot 1}1 \leq \pnorm{1}s \pnorm{h}r 
  = \mu(X)^{\frac 1 s} \pnorm{f}q^{\frac q r}
  \implies \pnorm{f}p 
  \leq \mu(X)^{\frac 1 p - \frac 1 q} \pnorm{f}q
  .\]

> Note: doesn't work for $\ell_p$ spaces, but just note that $\sum \abs{x_n} < \infty \implies x_n < 1$ for large enough $n$, and thus $p<q \implies \abs{x_n}^q \leq \abs{x_n}^q$.

Proof (Holder's Inequality)
:   It suffices to show this when $\norm{f}_p = \norm{g}_q = 1$, since

    \[  
    \|f g\|_{1} \leq\|f\|_{p}\|f\|_{q} \Longleftrightarrow \int \frac{|f|}{\|f\|_{p}} \frac{|g|}{\|g\|_{q}} \leq 1
    .\]

    Using $AB \leq \frac 1 p A^p + \frac 1 q B^q$, we have
    \[  
    \int|f \| g| \leq \int \frac{|f|^{p}}{p} \frac{|g|^{q}}{q}=\frac{1}{p}+\frac{1}{q}=1
    .\]


Proposition (Cauchy-Schwarz Inequality)
:	\hfill
  \[  
  \abs{\inner{f}{g}} = \pnorm{fg}1 \leq \pnorm{f}2 \pnorm{g}2
  \qtext{with equality} \iff f = \lambda g
  .\]

Note: Relates inner product to norm, and only happens to relate norms in $L^1$.

Proof
: ?

Proposition (Minkowski's Inequality:)
:	\hfill
  \[  
  1\leq p < \infty \implies \pnorm{f+g}{p} \leq \pnorm{f}{p}+ \pnorm{g}{p}
  .\]

> Note: does not handle $p=\infty$ case.
> Use to prove $L^p$ is a normed space.

Proof
:   \hfill

    - We first note
    \[  
    \abs{f+g}^p = \abs{f+g}\abs{f+g}^{p-1} \leq \left( \abs{f} + \abs{g}\right) \abs{f+g}^{p-1}
    .\]

    - Note that if $p,q$ are conjugate exponents then
    \[  
    \frac 1 q &= 1 - \frac 1 p = \frac{p-1} p \\
    q &= \frac p {p-1} 
    .\]

    - Then taking integrals yields
    \[  
    \norm{f+g}_p^p &=
    \int \abs{f+g}^p \\
    &\leq \int \left( \abs{f} + \abs{g}\right) \abs{f+g}^{p-1} \\ 
    &= \int \abs{f} \abs{f+g}^{p-1} + \int \abs{g} \abs{f+g}^{p-1} \\
    &= \norm{f(f+g)^{p-1}}_1 + \norm{g(f+g)^{p-1}}_1 \\
    &\leq \norm{f}_p ~\norm{(f+g)^{p-1})}_q + \norm{g}_p ~\norm{(f+g)^{p-1})}_q \\
    &= \left( \norm{f}_p + \norm{g}_p \right) \norm{ (f+g)^{p-1})}_q \\
    &= \left( \norm{f}_p + \norm{g}_p \right) \left( \int \abs{f+g}^{(p-1)q} \right)^{\frac 1 q} \\
    &= \left( \norm{f}_p + \norm{g}_p \right) \left( \int \abs{f+g}^{p} \right)^{1 - \frac 1 p} \\
    &= \left( \norm{f}_p + \norm{g}_p \right) \frac{\int \abs{f+g}^{p} }{\left( \int \abs{f+g}^{p} \right)^{\frac 1 p}} \\
    &= \left( \norm{f}_p + \norm{g}_p \right)  \frac{\norm{f+g}_p^p}{\norm{f+g}_p}
    .\]

    - Cancelling common terms yields
    \[  
    1 &\leq \left( \norm{f}_p + \norm{g}_p \right) \frac{1}{\norm{f+g}_p} \\
    &\implies 
    \norm{f+g}_p
    \leq \norm{f}_p + \norm{g}_p 
    .\]


Proposition (Young's Inequality*)
:	  \hfill
    \[
    \frac 1 p + \frac 1 q = \frac 1 r + 1 \implies
    \|f \ast g\|_{r} \leq\|f\|_{p}\|g\|_{q}
    \]

**Application**:
Some useful specific cases:
\[  
\norm{f\ast g}_1      & \leq \norm{f}_1 \norm{g}_1 \\
\|f * g\|_{p}         & \leq \norm{f}_1 \norm{g}p, \\
\norm{f\ast g}_\infty & \leq \norm{f}_2 \norm{g}_2 \\
\norm{f\ast g}_\infty & \leq \norm{f}_p \norm{g}_q
.\]


Proposition (Bessel's Inequality:)
:	\hfill

For $x\in H$ a Hilbert space and $\theset{e_k}$ an orthonormal sequence,
\[  
\sum_{k=1}^{\infty}\| \inner{x}{e_{k} } \|^{2} \leq \|x\|^{2}
.\]

> Note: this does not need to be a basis.

Proposition (Parseval's Identity:)
:	Equality in Bessel's inequality, attained when $\theset{e_k}$ is a *basis*, i.e. it is complete, i.e. the span of its closure is all of $H$.

## Less Explicitly Used Inequalities

Proposition (AM-GM Inequality)
:	\hfill
  \[
  \sqrt{ab} \leq \frac{a+b}{2}
  .\]


Proposition (Jensen's Inequality)
: \hfill
  \[
  f(tx + (1-t)y) \leq tf(x) + (1-t)f(y)
  .\]

Proposition (???)
:
\[
AB \leq {A^p \over p} + {B^q \over q}
.\]


Proposition (? Inequality)
:	\hfill
\[
(a+b)^p \leq 2^p (a^p + b^p)
.\]


Proposition (Bernoulli's Inequality)
: 
\[
(1 + x)^n \geq 1 +nx \quad x\geq -1, \text{ or } n\in 2\ZZ \text{ and } \forall x
.\]


