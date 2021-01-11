# Theorems

Properties preserved and not preserved by continuous functions: [Link](https://people.clas.ufl.edu/groisser/files/cont_img_preimg.pdf)

- Properties pushed forward through continuous maps:
  - Compactness?
  - Connectedness (when surjective)
  - Separability
  - Density **only when** $f$ is surjective
  - **Not** openness
  - **Not** closedness


## Metric Spaces and Analysis


:::{.theorem title="Cantor's Intersection Theorem"}
A bounded collection of nested closed sets $C_1 \supset C_2 \supset \cdots$ in a metric space $X$ is nonempty $\iff X$ is complete.
:::


:::{.theorem title="Cantor's Nested Intervals Theorem"}
If $\theset{[a_n, b_n] \suchthat n\in \ZZ^{\geq 0}}$ is a nested sequence of **closed and bounded** intervals, then their intersection is nonempty.
If $\diam([a_n, b_n]) \converges{n\to\infty}0$, then the intersection contains exactly one point.
:::


:::{.proposition title="Continuous on compact $\implies$ uniformly continuous"}
A continuous function on a compact set is uniformly continuous.
:::


:::{.proof title="?"}
Take $\theset{B_{\eps \over 2}(y) \suchthat y\in Y}\covers Y$, pull back to an open cover of $X$, has Lebesgue number $\delta_L > 0$, then $x' \in B_{\delta_L}(x) \implies f(x), f(x') \in B_{\eps \over 2}(y)$ for some $y$. 
:::

Corollary
: Lipschitz continuity implies uniform continuity (take $\delta = \eps/C$)

Counterexample to the converse: $f(x) = \sqrt x$ on $[0, 1]$ has unbounded derivative.

Theorem (Extreme Value Theorem)
: For $f:X \to Y$ continuous with $X$ compact and $Y$ ordered in the order topology, there exist points $c, d\in X$ such that $f(x) \in [f(c), f(d)]$ for every $x$.

Theorem
: A metric space $X$ is sequentially compact iff it is complete and totally bounded.

Theorem
: A metric space is totally bounded iff every sequence has a Cauchy subsequence.

Theorem
: A metric space is compact iff it is complete and totally bounded.

Theorem (Baire)
: If $X$ is a complete metric space, then the intersection of countably many dense open sets is dense in $X$.



## Connectedness

Theorem (Tube Lemma)
:   \todo[inline]{Todo}

## Compactness

Theorem
: $U\subset X$ a Hausdorff spaces is closed $\iff$ it is compact. 

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
: A closed subset of a Hausdorff space is compact.

Theorem
: A continuous bijection $f: X\to Y$ where $X$ is compact and $Y$ is Hausdorff is an open map and hence a homeomorphism.

## Separability

Proposition 
: A retract of a Hausdorff/connected/compact space is closed/connected/compact respectively.

Theorem
: Points are closed in $T_1$ spaces.


## Maps and Homeomorphism

Theorem
: A continuous bijective open map is a homeomorphism.

Theorem (Munkres 18.1)
:   For $f:X\to Y$, TFAE:

    - $f$ is continuous
    - $A\subset X \implies f(\cl_X(A)) \subset \cl_X(f(A))$
    - $B$ closed in $Y \implies f\inv(B)$ closed in $X$.
    - For each $x\in X$ and each neighborhood $V \ni f(x)$, there is a neighborhood $U\ni x$ such that $f(U) \subset V$.

Proof
: \todo[inline]{Todo, see Munkres page 104}

Theorem (Lee A.52)
:   If $f:X\to Y$ is continuous where $X$ is compact and $Y$ is Hausdorff, then 

    - $f$ is a closed map.
    - If $f$ is surjective, $f$ is a quotient map.
    - If $f$ is injective, $f$ is a topological embedding.
    - If $f$ is bijective, it is a homeomorphism.
