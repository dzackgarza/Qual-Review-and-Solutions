# Unsorted 


## Definitions

- Topology: arbitrary unions, finite intersections

## Common Spaces and Operations

Spaces
\begin{align*}
S^n, \DD^n, T^n \RP^n, \CP^n, M, K, \Sigma_g, \RP^\infty, \CP^\infty
.\end{align*}

- Knot complements in $S^3$
- Lens spaces
- Prism spaces
- $\HP^n$
- Dunce Cap
- Matrix groups
- Pair of pants
- Covering spaces (hyperbolic geometry)
- Seifert surfaces
- Surgery
- Hawaiian earring
- Horned sphere
- Cantor set
- Simplicial Complexes
  - Nice minimal example:
  
![](figures/image_2020-05-22-18-58-03.png) 

Operations

- Cartesian product $A\cross B$
- Wedge product $A \vee B$
- Connect Sum $A \# B$
- Quotienting $A/B$
- Puncturing $A\setminus \theset{a_i}$
- Smash product
- Join
- Cones
- Suspension
- Loop space
-  Identifying a finite number of points

## Theorems

General Topology

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

---

Algebraic Topology

Theorem (Van Kampen)
:   The pushout is the northwest colimit of the following diagram
    \begin{center}
    \begin{tikzcd}
    A \disjoint_Z B   & A \ar[d] \ar[l] \\
    B \ar[r]          & Z \ar[l, "\iota_B"] \ar[u, "\iota_A"]
    \end{tikzcd}
    \end{center}

    For groups, the pushout is given by the amalgamated free product: if $A = \generators{G_A \suchthat R_A}, B = \generators{G_B \suchthat R_B}$, then $A \ast_Z B = \generators{G_A, G_B \suchthat R_A, R_B, T}$ where $T$ is a set of relations given by $T = \theset{\iota_A(z) \iota_B(z)\inv \suchthat z\in Z}$.

    Example: $A = \ZZ/4\ZZ = \gens{x \suchthat x^4}, B = \ZZ/6\ZZ = \gens{y \suchthat x^6}, Z = \ZZ/2\ZZ = \gens{z \suchthat z^2}$.
    Then we can identify $Z$ as a subgroup of $A, B$ using $\iota_A(z) = x^2$ and $\iota_B(z) = y^3$.
    So $$A\ast_Z B = \gens{x, y \suchthat x^4, y^6, x^2y^{-3}}$$.

    Suppose $X = U_1 \union U_2$ such that $U_1\intersect U_2 \neq \emptyset$ is path connected.
    Then taking $x_0 \in U\definedas U_1 \intersect U_2$ yields a pushout of fundamental groups

    \begin{align*}
    \pi_1(X; x_0) = \pi_1(U_1;x_0) \ast_{\pi_1(U; x_0)} \pi_1(U_2; x_0)
    .\end{align*}
