# Theorems

## Point-Set

- Closed subsets of Hausdorff spaces are compact? (check)
- Cantor's intersection theorem?
- Tube lemma

- Properties pushed forward through continuous maps:
  - Compactness?
  - Connectedness (when surjective)
  - Separability
  - Density **only when** $f$ is surjective
  - **Not** openness
  - **Not** closedness

- A retract of a Hausdorff/connected/compact space is closed/connected/compact respectively.

Proposition
: A continuous function on a compact set is uniformly continuous.

Proof
: Take $\theset{B_{\eps \over 2}(y) \suchthat y\in Y}\covers Y$, pull back to an open cover of $X$, has Lebesgue number $\delta_L > 0$, then $x' \in B_{\delta_L}(x) \implies f(x), f(x') \in B_{\eps \over 2}(y)$ for some $y$. 

- Lipschitz continuity implies uniform continuity (take $\delta = \eps/C$)
  - Counterexample to converse: $f(x) = \sqrt x$ on $[0, 1]$ has unbounded derivative.

- Extreme Value Theorem: for $f:X \to Y$ continuous with $X$ compact and $Y$ ordered in the order topology, there exist points $c, d\in X$ such that $f(x) \in [f(c), f(d)]$ for every $x$.


Theorem
: Points are closed in $T_1$ spaces.

Theorem
: A metric space $X$ is sequentially compact iff it is complete and totally bounded.

Theorem
: A metric space is totally bounded iff every sequence has a Cauchy subsequence.

Theorem
: A metric space is compact iff it is complete and totally bounded.

Theorem (Baire)
: If $X$ is a complete metric space, then the intersection of countably many dense open sets is dense in $X$.

Theorem
: A continuous bijective open map is a homeomorphism.

Theorem
: A closed subset $A$ of a compact set $B$ is compact.

Proof
:   \hfill

    - Let $\theset{A_i} \rightrightarrows A$ be a covering of $A$ by sets open in $A$.
    - Each $A_i = B_i \intersect A$ for some $B_i$ open in $B$ (definition of subspace topology)
    - Define $V = \theset{B_i}$, then $V \rightrightarrows A$ is an open cover.
    - Since $A$ is closed, $W\definedas B\setminus A$ is open
    - Then $V\union W$ is an open cover of $B$, and has a finite subcover $\theset{V_i}$
    - Then $\theset{V_i \intersect A}$ is a finite open cover of $A$.

Theorem
: The continuous image of a compact set is compact.

Theorem
:   A closed subset of a Hausdorff space is compact.



## Algebraic

> Todo: Merge the two van Kampen theorems.

Theorem (Van Kampen)
:   The pushout is the northwest colimit of the following diagram
    \begin{center}
    \begin{tikzcd}
    A \disjoint_Z B   & A \ar[d] \ar[l] \\
    B \ar[u]\ar[r]          & Z \ar[l, "\iota_B"] \ar[u, "\iota_A"]
    \end{tikzcd}
    \end{center}

    For groups, the pushout is given by the amalgamated free product: if $A = \generators{G_A \suchthat R_A}, B = \generators{G_B \suchthat R_B}$, then $$A \ast_Z B = \generators{G_A, G_B \suchthat R_A, R_B, T}$$ where $T$ is a set of relations given by $$T = \theset{\iota_A(z) \iota_B(z)\inv \suchthat z\in Z}.$$

    Example: $A = \ZZ/4\ZZ = \gens{x \suchthat x^4}, B = \ZZ/6\ZZ = \gens{y \suchthat x^6}, Z = \ZZ/2\ZZ = \gens{z \suchthat z^2}$.
    Then we can identify $Z$ as a subgroup of $A, B$ using $\iota_A(z) = x^2$ and $\iota_B(z) = y^3$.
    So $$A\ast_Z B = \gens{x, y \suchthat x^4, y^6, x^2y^{-3}}$$.

    Suppose $X = U_1 \union U_2$ such that $U_1\intersect U_2 \neq \emptyset$ is path connected.
    Then taking $x_0 \in U\definedas U_1 \intersect U_2$ yields a pushout of fundamental groups

    \begin{align*}
    \pi_1(X; x_0) = \pi_1(U_1;x_0) \ast_{\pi_1(U; x_0)} \pi_1(U_2; x_0)
    .\end{align*}

Theorem (Van Kampen)
:   If $X = U \union V$ where $U, V, U\intersect V$ are all path-connected then

    \begin{align*}
    \pi_1(X) = \pi_1 U \ast_{\pi_1(U \intersect V)} \pi_1 V
    ,\end{align*}

    where the amalgamated product can be computed as follows: 
    If we have presentations

    \begin{align*} 
    \pi_{1}(U, w) &=
    \left\langle u_{1}, \cdots, u_{k} \suchthat \alpha_{1}, \cdots, \alpha_{l}\right\rangle \\ 
    \pi_{1}(V, w) &=\left\langle v_{1}, \cdots, v_{m} \suchthat \beta_{1}, \cdots, \beta_{n}\right\rangle \\ 
    \pi_{1}(U \cap V, w) &=\left\langle w_{1}, \cdots, w_{p} \suchthat \gamma_{1}, \cdots, \gamma_{q}\right\rangle 
    \end{align*}

    then

    \begin{align*}
    \pi_{1}(X, w) 
    &= \left\langle u_{1}, \cdots, u_{k}, v_{1}, \cdots, v_{m}\right\rangle \\ 
    &\mod 
    \left\langle \alpha_{1}, \cdots, \alpha_{l}, \beta_{1}, \cdots, \beta_{n}, I\left(w_{1}\right) J\left(w_{1}\right)^{-1}, \cdots, I\left(w_{p}\right) J\left(w_{p}\right)^{-1}\right\rangle \\
    &= \frac{\pi_1(U) \ast \pi_1(B)} {\generators{\theset{I(w_i) J(w_i)\inv \suchthat 1\leq i \leq p}}}
    \end{align*}

    where

    \begin{align*}
    I: \pi_{1}(U \cap V, w) &\rightarrow \pi_{1}(U, w) \\
    J: \pi_{1}(U \cap V, w) &\rightarrow \pi_{1}(V, w)
    .\end{align*}


