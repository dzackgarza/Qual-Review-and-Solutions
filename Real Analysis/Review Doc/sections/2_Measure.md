# Measure Theory

**Useful Technique:**
$s = \inf\theset{x\in X} \implies$ for every $\varepsilon$ there is an $x\in X$ such that $x \leq s + \varepsilon$.

**Useful Techniques**:
Always consider bounded sets, and if $E$ is unbounded write $E = \union_n B_n(0) \intersect E$ and use countable subadditivity or continuity of measure.

Lemma
:	Every open subset of $\RR$ (resp $\RR^n$) can be written as a unique countable union of disjoint (resp. almost disjoint) intervals (resp. cubes).

Definition
:   The outer measure of a set is given by
    \begin{align*}
    m_*(E) = \inf_{\substack{\theset{Q_i} \rightrightarrows E \\ \text{closed cubes}}} \sum \abs{Q_i}
    .\end{align*}

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
: If $E$ is Lebesgue measurable, then $$\mu(E) = \inf_{U\supseteq E \text{ open}} \mu(U) = \sup_{K\subseteq E \text{ compact}} \mu(K).$$

Proof
:   \hfill
    - First equality:
      - Fix $\eps>0$, then there exists (claim) an a *open* covering $\theset{Q_i} \covers E$ with $\mu(E) \leq \qty{\sum \abs{Q_i}} + \eps$
      - Set $U\definedas \union Q_i$ then $U$ is open, $E\subseteq U$, and $\mu(U) \leq \mu(E) + \eps$
      - Since $E\subset U$, we have $\mu(E) \leq \mu(U)$. 
    - Second equality

Lemma
:	Lebesgue measure is translation and dilation invariant.

Proof
: Obvious for cubes; if $Q_i \rightrightarrows E$ then $Q_i + k \rightrightarrows E + k$, etc.

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

Definition
:   \hfill	
    \begin{align*}
    \limsup_n A_n \definedas \intersect_n \union_{j\geq n} A_j&= \theset{x \suchthat x\in A_n \text{ for inf. many $n$}}  \\
    \liminf_n A_n \definedas \union_n \intersect_{j\geq n} A_j &= \theset{x \suchthat x\in A_n \text{ for all except fin. many $n$}}  \\
    .\end{align*}

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

