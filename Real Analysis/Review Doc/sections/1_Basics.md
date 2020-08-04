# Basics

## Useful Techniques

- Limits:
  - Take the $\limsup$ or $\liminf$, which always exist, and aim for an inequality like
  \[  
  c \leq \liminf a_n \leq \limsup a_n \leq c
  .\]
  - $\lim f_n = \limsup f_n = \liminf f_n$ iff the limit exists, so to show some $g$ is a limit, show
  \[  
\limsup f_n \leq g \leq \liminf f_n \qquad (\implies g = \lim f) 
  .\]
  - A  limit does *not* exist iff $\liminf f_n > \limsup f_n$.

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

Definition (Uniform Continuity)
:   $f$ is uniformly continuous iff  

    \begin{align*}
        &\forall \varepsilon \quad \exists \delta(\varepsilon) \mid \quad \forall x, y, \quad \abs{x - y} < \delta \implies \abs{f(x) - f(y)} < \varepsilon \\
    \iff &\forall \varepsilon \quad \exists \delta(\varepsilon) \mid \quad \forall x, y, \quad \abs{y} < \delta \implies \abs{f(x-y) - f(y)} < \varepsilon \\
    .\end{align*}


Definition (Nowhere Dense Sets)
: A set $S$ is **nowhere dense** iff the closure of $S$ has empty interior iff every interval contains a subinterval that does not intersect $S$.

Definition (Meager Sets)
: A set is **meager** if it is a *countable* union of nowhere dense sets.

Definition (\$F_\\sigma\$ and \$G_\\delta\$)
:	  An $F_\sigma$ set is a union of closed sets, and a $G_\delta$ set is an intersection of opens.
  
> Mnemonic: "F" stands for *ferme*, which is "closed" in French, and $\sigma$ corresponds to a "sum", i.e. a union.

Theorem (Heine-Cantor)
: Every continuous function on a compact space is uniformly continuous.

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
:   \begin{align*}
    \sum_{k=0}^\infty x^k = \frac 1 {1-x} \iff \abs{x} < 1
    .\end{align*}

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
    \begin{align*}
    \forall\varepsilon > 0, ~\exists F \subseteq E ~\text{closed such that } &
    m(E\setminus F) < \varepsilon ~\text{ and }~ f_k \mapsvia{u}  f ~\text{on}~ F
    .\end{align*}

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


Lemma (Testing Uniform Convergence)
:   $f_n \to f$ uniformly iff there exists an $M_n$ such that $\norm{f_n - f}_\infty \leq M_n \to 0$.

    **Negating**: find an $x$ which depends on $n$ for which the norm is bounded below.

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
    \begin{align*}
    \sum \frac 1 {n^p} < \infty &\iff p>1 \\
    \int_\varepsilon^\infty \frac 1 {x^p} < \infty 
    &\iff p>1 \\
    \int_0^1 \frac 1 {x^p} < \infty 
    &\iff p<1 \\
    \int_B \frac{1}{\abs{x}^p} < \infty &\iff p < n \\
    \int_{B^c} \frac{1}{\abs{x}^p} < \infty &\iff p > n \\
    .\end{align*}

