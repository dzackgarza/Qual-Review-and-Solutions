# Unsorted 

## Definitions

- Neighborhood: A neighborhood of a point $x$ is any open set containing $x$.

- Hausdorff

- Second Countable: admits a countable basis.

- Closed (several characterizations)
 - Closure in a subspace: $Y\subset X \implies \cl_Y(A) \definedas \cl_X(A)\intersect Y$.

- Bounded

- Compact:
    A topological space $(X, \tau)$ is **compact** if every open cover has a *finite* subcover.
    That is, if $\theset{U_j \suchthat j\in J} \subset \tau$ is a collection of open sets such that $X \subseteq \union_{j\in J} U_j$, then there exists a *finite* subset $J' \subset J$ such that $X \subseteq \union_{j\in J'} U_j$.


- Locally compact
  For every $x\in X$, there exists a $K_x \ni x$ such that $K_x$ is compact.

- Connected: 
  There does not exist a disconnecting set $X = A\disjoint B$ such that $\emptyset \neq A, B \subsetneq$, i.e. $X$ is the union of two proper disjoint nonempty sets.
  Equivalently, $X$ contains no proper nonempty clopen sets.
  - Additional condition for a subspace $Y\subset X$: $\cl_Y(A) \intersect V = A \intersect \cl_Y(B) = \emptyset$.

- Locally connected:
  A space is locally connected at a point $x$ iff $\forall N_x \ni x$, there exists a $U\subset N_x$ containing $x$ that is connected.
  
- Retract: A subspace $A \subset X$ is a *retract* of $X$ iff there exists a continuous map $f: X\to A$ such that $f\mid_{A} = \id_A$. Equivalently it is a *left* inverse to the inclusion.

- Uniform Continuity: For $f: (X, d_x) \to (Y, d_Y)$ metric spaces,
\begin{align*}
\forall \eps > 0, ~\exists \delta > 0 \text{ such that } \quad d_X(x_1, x_2) < \delta \implies d_Y(f(x_1), f(x_2)) < \eps
.\end{align*} 

- Lebesgue number: For $(X, d)$ a compact metric space and $\theset{U_\alpha}\covers X$, there exist $\delta_L > 0$ such that 
\begin{align*}
A\subset X, ~ \diam(A) < \delta_L \implies A\subseteq U_\alpha \text{ for some } \alpha
.\end{align*}

- Paracompact

- Components: 
  Set $x\sim y$ iff there exists a connected set $U\ni x, y$ and take equivalence classes.

- Path Components:
  Set $x\sim y$ iff there exists a path-connected set $U\ni x, y$ and take equivalence classes.

- Separable: countable dense subset.

- Limit Point:
    For $A\subset X$, $x$ is a limit point of $A$ if every punctured neighborhood $P_x$ of $x$ satisfies $P_x \intersect A \neq \emptyset$, i.e. every neighborhood of $x$ intersects $A$ in some point other than $x$ itself.
    Equivalently, $x$ is a limit point of $A$ iff $x\in \cl_X(A\setminus\theset{x})$.

## Sandbox of Spaces

- Finite discrete sets with the discrete topology 
- Subspaces of $\RR$: $(a, b), (a, b], (a, \infty)$, etc.
  - $\ts{0} \union \ts{{1 \over n}\suchthat n\in \ZZ^{\geq 1}}$
- $\QQ$
- The topologist's sine curve
- One-point compactifications
- $\RR^\omega$

Alternative topologies to consider:

- Cofinite
- Discrete and Indiscrete
- Uniform


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
    A \disjoint_Z B   & A \ar[d] \ar[l] \
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
