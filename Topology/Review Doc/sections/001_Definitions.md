# Definitions

## Point-Set Topology

:::{.definition title="Bounded"}
A set $S$ in a metric space $(X, d)$ is *bounded* iff there exists an $m\in \RR$ such that $d(x, y) < m$ for every $x, y\in S$.
:::

:::{.definition title="Connected"}
There does not exist a disconnecting set $X = A\disjoint B$ such that $\emptyset \neq A, B \subsetneq$, i.e. $X$ is the union of two proper disjoint nonempty sets.
Additional condition for a subspace $Y\subset X$: $\cl_{Y}(A) \intersect V = A \intersect \cl_{Y}(B) = \emptyset$.
  
Equivalently, $X$ contains no proper nonempty clopen sets.
:::

:::{.definition title="Connected Components"}
Set $x\sim y$ iff there exists a connected set $U\ni x, y$ and take equivalence classes.
:::

:::{.definition title="Closed Sets"}
\envlist

- A set is closed if and only if its complement is open.
- A set is closed iff it contains all of its limit points.
- A closet set in a subspace: $Y\subset X \implies \cl_{Y}(A) \da \cl_{X}(A)\intersect Y$.

:::

:::{.definition title="Closed Maps"}
See \cref{def:open_closed_maps}.
:::


:::{.definition title="Closure of a set"}
$\Cl_X(U) = \intersect_{\substack{ B\supseteq U \\ \text{ closed} }} B$, the intersection of all closed sets in $X$ containing $U$. 

:::


:::{.definition title="Compact"}
A topological space $(X, \tau)$ is **compact** if every open cover has a *finite* subcover.

That is, if $\theset{U_{j} \suchthat j\in J} \subset \tau$ is a collection of open sets such that $X = \union_{j\in J} U_{j}$, then there exists a *finite* subset $J' \subset J$ such that $X \subseteq \union_{j\in J'} U_{j}$.
:::

:::{.definition title="Continuous Map"}
A map $f:X\to Y$ between topological spaces is **continuous** if and only if whenever $U \subseteq Y$ is open, $f ^{-1} (U) \subseteq X$ is open.
:::

:::{.definition title="Cover"}
A collection of subsets $\theset{U_\alpha}$ of $X$ is said to *cover $X$* iff $X = \union_{\alpha} U_\alpha$.
If $A\subseteq X$ is a subspace, then this collection *covers $A$* iff $A\subseteq \union_{\alpha} U_\alpha$.
:::

:::{.definition title="Dense"}
A subset $Q\subset X$ is dense iff $y\in N_{y} \subset X \implies N_{y} \intersect Q \neq \emptyset$ iff $\bar Q = X$.
:::

:::{.definition title="First Countable"}
A space is *first-countable* iff every point admits a countable neighborhood basis.
:::

:::{.definition title="Hausdorff"}
A topological space $X$ is *Hausdorff* iff for every $p\neq q \in X$ there exist disjoint open sets $U\ni p$ and $V\ni q$. 
:::

:::{.definition title="Injection"}
A map $\iota$ with a **left** inverse $f$ satisfying $f\circ \iota = \id$
:::

:::{.definition title="Lebesgue Number"}
For $(X, d)$ a compact metric space and $\theset{U_\alpha}\covers X$, there exist $\delta_{L} > 0$ such that 
\[
A\subset X, ~ \diam(A) < \delta_{L} \implies A\subseteq U_\alpha \text{ for some } \alpha
.\]
:::

:::{.definition title="Limit Point"}
For $A\subset X$, $x$ is a limit point of $A$ if every punctured neighborhood $P_{x}$ of $x$ satisfies $P_{x} \intersect A \neq \emptyset$, i.e. every neighborhood of $x$ intersects $A$ in some point other than $x$ itself.
    
Equivalently, $x$ is a limit point of $A$ iff $x\in \cl_{X}(A\setminus\theset{x})$.
:::

:::{.definition title="Locally Connected"}
A space is *locally connected* at a point $x$ iff $\forall N_{x} \ni x$, there exists a $U\subset N_{x}$ containing $x$ that is connected.
:::

:::{.definition title="Locally Compact"}
A space $X$ is *locally compact* iff every $x\in X$ has a neighborhood contained in a compact subset of $X$.
:::

:::{.definition title="Locally Finite"}
A collection of subsets $\mcs$ of $X$ is *locally finite* iff each point of $M$ has a neighborhood that intersects at most finitely many elements of $\mcs$.
:::

:::{.definition title="Locally Path-Connected"}
A space is **locally path-connected** if it admits a basis of path-connected open subsets.
:::

:::{.definition title="Neighborhood"}
A **neighborhood** of a point $x$ is *any* open set containing $x$.
:::

:::{.definition title="Normal"}
A space is **normal** if any two disjoint closed subsets can be separated by neighborhoods.
:::

:::{.definition title="Neighborhood Basis"}
If $p\in X$, a **neighborhood basis** at $p$ is a collection $\mcb_{p}$ of neighborhoods of $p$ such that if $N_{p}$ is a neighborhood of $p$, then $N_{p} \supseteq B$ for at least one $B\in \mcb_{p}$.
:::

:::{.definition title="Open and Closed Maps" ref="def:open_closed_maps"}
A map $f:X\to Y$ is an **open map** (respectively a **closed map**) if and only if whenever $U \subseteq X$ is open (resp. closed), $f(U)$ is again open (resp. closed)>
:::

:::{.definition title="Paracompact"}
A topological space $X$ is **paracompact** iff every open cover of $X$ admits an open locally finite refinement.
:::

:::{.definition title="Quotient Map"}
A map $q:X\to Y$ is a **quotient map** if and only if 

1. $q$ is surjective, and
2. $U \subseteq Y$ is open if and only if $q ^{-1} (U)$ is open.

:::

:::{.definition title="Path Connected"}
A space $X$ is **path connected** if and only if for every pair of points $x\neq y$ there exists a continuous map $f:I \to X$ such that $f(0) = x$ and $f(1) = y$.
:::

:::{.definition title="Path Components"}
Set $x\sim y$ iff there exists a path-connected set $U\ni x, y$ and take equivalence classes.
:::

:::{.definition title="Precompact"}
A subset $A\subseteq X$ is **precompact** iff $\cl_{X}(A)$ is compact.
:::

:::{.definition title="The product topology"}
For $(X, \tau_X)$ and $(Y, \tau_Y)$ topological spaces, defining 
\[
\tau_{X \cross Y} \da \ts{U \cross V \st U\in \tau_X,\, V\in \tau_Y}
\]
yields the **product topology** on $X \cross Y$.
:::

:::{.definition title="Refinement"}
A cover $\mcv \covers X$ is a **refinement** of $\mcu \covers X$ iff for each $V\in \mcv$ there exists a $U\in\mcu$ such that $V\subseteq U$.
:::

:::{.definition title="Regular"}
A space $X$ is **regular** if whenever $x\in X$ and $F\not\ni x$ is closed, $F$ and $x$ are separated by neighborhoods.
:::

:::{.definition title="Retract"}
A map $r$ in $A\mathrel{\textstyle\substack{\injects^{\iota}\\\textstyle\dashleftarrow_{r}}} X$ satisfying $$r\circ\iota = \id_{A}.$$
Equivalently $X \surjects_{r} A$ and $\restrictionof{r}{A} = \id_{A}$. If $X$ retracts onto $A$, then $i_*$ is injective.

Alt:
Let $X$ be a topological space and $A \subset X$ be a subspace, then a **retraction** of $X$ onto $A$ is a map $r: X\into X$ such that the image of $X$ is $A$ and $r$ restricted to $A$ is the identity map on $A$.
:::


:::{.definition title="Saturated"}
A subset $U \subseteq X$ is **saturated** with respect to a surjective map $p: X\surjects Y$ if and only if whenever $U \intersect p ^{-1} (y) = V \neq \emptyset$, we have $V \subseteq U$, i.e. $U$ contains every set $p ^{-1} (y)$ that it intersects.
Equivalently, $U$ is the complete inverse image of a subset of $Y$.
:::

:::{.definition title="Separable spaces"}
A space $X$ is **separable** iff $X$ contains a countable dense subset.
:::

:::{.definition title="Second Countable"}
A space is *second-countable* iff it admits a countable basis.
:::

:::{.definition title="The subspace topology"}
For $(X, \tau)$ a topological space and $U \subseteq X$ an arbitrary subset, the space $(U, \tau_U)$ is a topological space with a **subspace topology** defined by
\[
\tau_U \da \ts {Y \intersect U \st U \in \tau}
.\]
:::

:::{.definition title="Surjection"}
A map $\pi$ with a **right** inverse $f$ satisfying $$\pi \circ f = \id$$
:::

:::{.definition title="$T_n$ Spaces (Separation Axioms)"}
\envlist

- $T_0$: Points are distinguishable.
  For any 2 points $x_1\neq x_2$, at least one $x_i$ (say $x_1$) admits a neighborhood not containing $x_2$.

- $T_1$: For any 2 points, *both* admit neighborhoods not containing the other.
  Equivalently, points are closed.

- $T_2$: For any 2 points, both admit *disjoint* separating neighborhoods.

- $T_{2.5}$: For any 2 points, both admit *disjoint closed* separating neighborhoods.

- $T_3$: $T_0$ & *regular*. 
  Given any point $x$ and any closed $F\not\ni x$, there are neighborhoods separating $F$ and $x$.

- $T_{3.5}$: $T_0$ & completely regular.
  Any point $x$ and closed $F\not\ni x$ can be separated by a continuous function.

- $T_4$: $T_1$ & normal.
  Any two disjoint closed subsets can be separated by neighborhoods.

:::


:::{.example title="Counterexamples for separation axioms"}
\envlist

- Not $T_0$: the space \( \ts{ f:\RR\to \CC\st \int_\RR \abs{f}^2 < \infty } \), since two a.e. equal functions aren't *distinguishable* (they have precisely the same set of neighborhoods).
- $T_1$ but not $T_0$: $\spec R$ for $R\in \CRing$ with the Zariski topology.
  There are points that aren't closed: $\spec R \sm \mspec R$.
:::


:::{.definition title="Topology"}
\envlist

- Using open sets: closed under arbitrary unions and finite intersections.
- Using closed sets: closed under arbitrary intersections and finite unions.
:::


:::{.remark}
A mnemonic: in $\RR$, $\intersect_{n\in \NN} (-1/n, 1/n) = \ts{0}$ which is closed in $\RR$.
:::


:::{.definition title="Topology generated by a basis"}
For $X$ an arbitrary set, a collection of subsets $\mcb$ is a *basis for $X$* iff $\mcb$ is closed under intersections, and every intersection of basis elements contains another basis element.
The set of unions of elements in $B$ is a topology and is denoted *the topology generated by $\mcb$*.
:::

:::{.definition title="Topological Embedding"}
A continuous map $f:X \to Y$ for which $X\cong f(X)$ are homeomorphic is called a **topological embedding**.
:::

:::{.definition title="Uniform Continuity"}
For $f: (X, d_{x}) \to (Y, d_{Y})$ metric spaces,
\[
\forall \eps > 0, ~\exists \delta > 0 \text{ such that } \quad d_{X}(x_{1}, x_{2}) < \delta \implies d_{Y}(f(x_{1}), f(x_{2})) < \eps
.\] 
:::


## Algebraic Topology

:::{.definition title="Acyclic"}

:::
\todo[inline]{Definitions}

:::{.definition title="Alexander duality"}

:::
\todo[inline]{Definitions}

:::{.definition title="Basis"}
For an $R\dash$module $M$, a basis $B$ is a linearly independent generating set.
:::

:::{.definition title="Boundary"}

:::
\todo[inline]{Definitions}

:::{.definition title="Boundary of a manifold"}
Points $x\in M^n$ defined by 
$$
\del M = \theset{x\in M: H_{n}(M, M-\theset{x}; \ZZ) = 0}
$$

:::

:::{.definition title="Cap Product"}
Denoting $\Delta^p \mapsvia{\sigma} X \in C_{p}(X; G)$, a map that sends pairs ($p\dash$chains, $q\dash$cochains) to $(p-q)\dash$chains $\Delta^{p-q} \to X$ by
$$
H_{p}(X; R)\cross H^q(X; R) \mapsvia{\frown} H_{p-q}(X; R)\\
\sigma \frown \psi = \psi(F_{0}^q(\sigma))F_{q}^p(\sigma)
$$
where $F_{i}^j$ is the face operator, which acts on a simplicial map $\sigma$ by restriction to the face spanned by $[v_{i} \ldots v_{j}]$, i.e. $F_{i}^j(\sigma) =\restrictionof{\sigma}{[v_{i} \ldots v_{j}]}$.


:::

:::{.definition title="Cellular Homology"}

:::
\todo[inline]{Definitions}

:::{.definition title="Cellular Map"}
A map $X \mapsvia{f} Y$ is said to be cellular if $f(X^{(n)}) \subseteq Y^{(n)}$ where $X^{(n)}$ denotes the $n\dash$ skeleton.
:::

:::{.definition title="Chain"}
An element $c \in C_{p}(X; R)$ can be represented as the singular $p$ simplex $\Delta^p \to X$.
:::

:::{.definition title="Chain Homotopy"}
Given two maps between chain complexes $(C_*, \del_{C}) \mapsvia{f, ~g} (D_*, \del_{D})$, a chain homotopy is a family $h_{i}: C_{i} \to B_{i+1}$ satisfying $$f_{i}-g_{i} = \del_{B, i-1}\circ h_{n} + h_{i+1}\circ \del_{A, i}$$. 

<!--![](https://upload.wikimedia.org/wikipedia/commons/thumb/c/cb/Chain_{homotopy_{between_chain_complexes}}.svg/650px-Chain_{homotopy_{between_chain_complexes}}.svg.png)-->

:::

:::{.definition title="Chain Map"}
A map between chain complexes $(C_*, \del_{C}) \mapsvia{f} (D_*, \del_{D})$ is a chain map iff each component $C_{i} \mapsvia{f_{i}} D_{i}$ satisfies 
$$
f_{i-1}\circ\del_{C, i} = \del_{D,i} \circ f_{i}
$$ 
(i.e this forms a commuting ladder) 

<!--![](https://upload.wikimedia.org/wikipedia/commons/thumb/9/9b/Chain_{map}.svg/650px-Chain_{map}.svg.png)-->


:::

:::{.definition title="Closed manifold"}
A manifold that is compact, with or without boundary.
:::

:::{.definition title="Coboundary"}

:::
\todo[inline]{Definitions}

:::{.definition title="Cochain"}
An cochain $c \in C^p(X; R)$ is a map $c \in \hom(C_{p}(X; R), R)$ on chains.
:::

:::{.definition title="Cocycle"}

:::
\todo[inline]{Definitions}

:::{.definition title="Constant Map"}
A *constant map* $f: X\to Y$ iff $f(X) = y_{0}$ for some $y_{0}\in Y$, i.e. for every $x\in X$ the output value $f(x) = y_{0}$ is the same.
:::

:::{.definition title="Colimit"}
For a directed system $(X_{i}, f_{ij}$, the **colimit** is an object $X$ with a sequence of projections $\pi_{i}:X\to X_{i}$ such that for any $Y$ mapping into the system, the following diagram commutes:

\begin{tikzcd}
                 &                            &  & Y \arrow[lldddd, "\psi_{j}"] \arrow[rrdddd, "\psi_{i}"] \arrow[dd, "\exists!", dashed] &  &               &        \\
                 &                            &  &                                                                                    &  &               &        \\
                 &                            &  & X \arrow[lldd, "\pi_{j}"] \arrow[rrdd, "\pi_{i}"]                                      &  &               &        \\
                 &                            &  &                                                                                    &  &               &        \\
\cdots \arrow[r] & X_{j} \arrow[rrrr, "f_{ij}"] &  &                                                                                    &  & X_{i} \arrow[r] & \cdots
\end{tikzcd}
:::

:::{.example title="of colimits"}
\envlist

- Products
- Pullbacks
- Inverse / projective limits
- The \( p\dash \)adic integers \( \ZZ_{p} \).
:::

:::{.definition title="Cone"}
For a space $X$, defined as
\[  
CX = \frac{X\cross I} {X \cross \theset{0}}
.\]
Example: The cone on the circle $CS^1$ 

<!--![](https://upload.wikimedia.org/wikipedia/commons/thumb/8/8c/Cone.svg/250px-Cone.svg.png)-->

Note that the cone embeds $X$ in a contractible space $CX$.
:::

:::{.definition title="Contractible"}
A space $X$ is **contractible** if $\id_X$ is nullhomotopic. i.e. the identity is homotopic to a constant map $c(x) = x_0$.

Equivalently, $X$ is contractible if $X \homotopic \theset{x_0}$ is homotopy equivalent to a point.
This means that there exists a mutually inverse pair of maps $f: X \into \theset{x_0}$ and $g:\theset{x_0} \into X$ such that $f\circ g \homotopic \id_{\theset{x_0}}$ and $g\circ f \homotopic \id_X$.[^contractible_is_useful]

[^contractible_is_useful]: 
This is a useful property because it supplies you with a homotopy.

:::

:::{.definition title="Coproduct"}

:::
\todo[inline]{Definitions}

:::{.definition title="Covering Space"}
A **covering space** of $X$ is the data $p: \tilde X \to X$ such that

1. Each $x\in X$ admits a neighborhood $U$ such that $p ^{-1} (U)$ is a union of disjoint open sets in $\tilde V_i \subseteq X$ (the **sheets** of $\tilde X$ over $U$),
2. $\ro{p}{V_i}: V_i \to U$ is a homeomorphism for each sheet.

An **isomorphism** of covering spaces $\tilde X_1 \cong \tilde X_2$ is a commutative diagram

\begin{tikzcd}
	{\tilde X_1} && {\tilde X_2} \\
	\\
	& {X}
	\arrow["{p_1}"', from=1-1, to=3-2]
	\arrow["{p_2}", from=1-3, to=3-2]
	\arrow["{f}", from=1-1, to=1-3]
\end{tikzcd}
> [Link to diagram](https://q.uiver.app/?q=WzAsMyxbMCwwLCJcXHRpbGRlIFhfMSJdLFsxLDIsIlgiXSxbMiwwLCJcXHRpbGRlIFhfMiJdLFswLDEsInBfMSIsMl0sWzIsMSwicF8yIl0sWzAsMiwiZiJdXQ==)

:::

:::{.definition title="Cup Product"}
A map taking pairs ($p\dash$cocycles, $q\dash$cocycles) to $(p+q)\dash$cocyles by
\[
H^p(X; R) \cross H^q(X; R) \mapsvia{\smile} H^{p+q}(X; R)\\
(a \cup b)(\sigma) = a(\sigma \circ I_{0}^p)~b(\sigma \circ I_{p}^{p+q})
\]
where $\Delta^{p+q} \mapsvia{\sigma} X$ is a singular $p+q$ simplex and

\[I_{i}^j: [i, \cdots, j] \injects\Delta^{p+q}
.\]

is an embedding of the $(j-i)\dash$simplex into a $(p+q)\dash$simplex.
:::
	
:::{.example title="Applications of the cup product"}
On a manifold, the cup product is Poincaré dual to the intersection of submanifolds.
Also used to show $T^2 \not\homotopic S^2 \vee S^1 \vee S^1$. 
:::

:::{.definition title="CW Complex"}

:::
\todo[inline]{Definitions}

:::{.definition title="CW Cell"}
An $n\dash$cell of $X$, say $e^n$, is the image of a map $\Phi: B^n \to X$. That is, $e^n = \Phi(B^n)$. Attaching an $n\dash$cell to $X$ is equivalent to forming the space $B^n \coprod_{f} X$ where $f: \del B^n \to X$.

- A $0\dash$cell is a point.
- A $1\dash$cell is an interval $[-1, 1] = B^1 \subset \RR^1$. Attaching requires a map from $S^0 =\theset{-1, +1} \to X$
- A $2\dash$cell is a solid disk $B^2 \subset \RR^2$ in the plane. Attaching requires a map $S^1 \to X$.
- A $3\dash$cell is a solid ball $B^3 \subset \RR^3$. Attaching requires a map from the sphere $S^2 \to X$.


:::

:::{.definition title="Cycle"}

:::
\todo[inline]{Definitions}

:::{.definition title="Deck transformation"}
For a covering space $\tilde X \mapsvia{p} X$, self-isomorphisms $f:\tilde X \to \tilde X$ of covering spaces are referred to as **deck transformations**.
:::

:::{.definition title="Deformation"}

:::
\todo[inline]{Definitions}

:::{.definition title="Deformation Retract"}
A map $r$ in $A\mathrel{\textstyle\substack{\injects^{\iota}\\\textstyle\dashleftarrow_{r}}} X$ that is a retraction (so $r\circ \iota = \id_{A}$) *that also satisfies* $\iota \circ r \homotopic \id_{X}$.

> Note that this is equality in one direction, but only homotopy equivalence in the other.

Equivalently, a map $F:I\cross X\to X$ such that 
\[
F_{0}(x) &= \id_{X}
F_{t}(x)\mid_{A} &= \id_{A}
F_{1}(X) &= A
.\]

Alt:

A **deformation retract** is a homotopy $H:X\cross I \into X$ from the identity on $X$ to the identity on $A$ that fixes $A$ at all times:
$$
H: X\cross I \to X \\
H(x, 0) = \id_X \\
H(x, 1) = \id_A \\
x\in A \implies H(x, t) \in A \quad \forall t
$$

Equivalently, this requires that $\restrictionof{H}{A} = \id_A$
:::

:::{.remark}
A deformation retract between a space and a subspace is a homotopy equivalence, and further $X\homotopic Y$ iff there is a $Z$ such that both $X$ and $Y$ are deformation retracts of $Z$. Moreover, if $A$ and $B$ both have deformation retracts onto a common space $X$, then $A \homotopic B$.


:::

:::{.definition title="Degree of a Map of Spheres"}
Given any $f: S^n \into S^n$, there are induced maps on homotopy and homology groups. 
Taking $f^*: H^n(S^n) \into H^n(S^n)$ and identifying $H^n(S^n) \cong \ZZ$, we have $f^*: \ZZ \into \ZZ$. 
But homomorphisms of free groups are entirely determined by their action on generators. 
So if $f^*(1) = n$, define $n$ to be the **degree** of $f$.
:::

:::{.definition title="Derived Functor"}
For a functor $T$ and an $R\dash$module $A$, a *left derived functor* $(L_{nT})$ is defined as $h_{n}(TP_{A})$, where $P_{A}$ is a projective resolution of $A$.
:::

:::{.definition title="Dimension of a manifold"}
For $x\in M$, the only nonvanishing homology group $H_{i}(M, M - \theset{x}; \ZZ)$
:::

:::{.definition title="Direct Limit"}

:::
\todo[inline]{Definitions}

:::{.definition title="Direct Product"}

:::
\todo[inline]{Definitions}

:::{.definition title="Direct Sum"}

:::
\todo[inline]{Definitions}

:::{.definition title="Eilenberg-MacLane Space"}

:::
\todo[inline]{Definitions}

:::{.definition title="Euler Characteristic"}

:::
\todo[inline]{Definitions}

:::{.definition title="Exact Functor"}
A functor $T$ is *right exact* if a short exact sequence 

\[0 \to A \to B \to C \to 0
\]
yields an exact sequence 

\[\ldots TA \to TB \to TC \to 0
\]
and is *left exact* if it yields 

\[0 \to TA \to TB \to TC \to \ldots
\]
Thus a functor is exact iff it is both left and right exact, yielding

\[0 \to TA \to TB \to TC \to 0
.\]

:::

:::{.example title="of an exact functor"}
$\wait \tensor_{R} \wait$ is a right exact bifunctor.
:::

:::{.definition title="Exact Sequence"}

:::
\todo[inline]{Definitions}

:::{.definition title="Excision"}

:::
\todo[inline]{Definitions}

:::{.definition title="Ext Group"}

:::
\todo[inline]{Definitions}

:::{.definition title="Flat"}
An $R\dash$module is flat if $A\tensor_{R} \wait$ is an exact functor.
:::

:::{.definition title="Free and Properly Discontinuous"}
An action $G\actson X$ is **properly discontinuous** if each $x\in X$ has a neighborhood $U$ such that all of the images $g(U)$ for $g\in G$ are disjoint, i.e. $g_1(U) \intersect g_2(U) \neq \emptyset \implies g_1 = g_2$.
The action is **free** if there are no fixed points.

Sometimes a slightly weaker condition is used: every point $x\in X$ has a neighborhood $U$ such that $U \intersect G(U) \neq \emptyset$ for only finitely many $G$.
:::
\todo[inline]{Definitions}

:::{.definition title="Free module"}
A $\dash$module $M$ with a basis $S = \theset{s_{i}}$ of generating elements. Every such module is the image of a unique map $\mathcal{F}(S) = R^S \surjects M$, and if $M = \left< S \mid \mathcal{R} \right>$  for some set of relations $\mathcal{R}$, then $M \cong R^S / \mathcal{R}$.
:::

:::{.definition title="Free Product"}

:::
\todo[inline]{Definitions}

:::{.definition title="Free product with amalgamation"}

:::
\todo[inline]{Definitions}

:::{.definition title="Fundamental Class"}
For a connected, closed, orientable manifold, $[M]$ is a generator of $H_{n}(M; \ZZ) = \ZZ$.
:::

:::{.definition title="Fundamental Group"}

:::
\todo[inline]{Definitions}

:::{.definition title="Generating Set"}
$S = \theset{s_{i}}$ is a generating set for an $R\dash$ module $M$ iff $$x\in M \implies x = \sum r_{i} s_{i}$$ for some coefficients $r_{i} \in R$ (where this sum may be infinite).
:::

:::{.definition title="Gluing Along a Map"}

:::
\todo[inline]{Definitions}

:::{.definition title="Group Ring"}

:::
\todo[inline]{Definitions}

:::{.definition title="Homologous"}

:::
\todo[inline]{Definitions}

:::{.definition title="Homotopic"}

:::
\todo[inline]{Definitions}

:::{.definition title="Homotopy"}
Let $X, Y$ be topological spaces and $f,g: X \to Y$ continuous maps. Then a **homotopy** from $f$ to $g$ is a continuous function

$F: X \cross I \into Y$

such that

$F(x, 0) = f(x)$ and  $F(x,1) = g(x)$

for all $x\in X$. If such a homotopy exists, we write $f\homotopic g$. This is an equivalence relation on $\text{Hom}(X,Y)$, and the set of such classes is denoted $[X,Y] \definedas \hom (X,Y)/\homotopic$.

:::

:::{.definition title="Homotopy Class"}

:::
\todo[inline]{Definitions}

:::{.definition title="Homotopy Equivalence"}
Let $f: X \to Y$ be a continuous map, then $f$ is said to be a *homotopy equivalence* if there exists a continuous map $g: X \to Y$ such that

$f\circ g \homotopic \id_Y$ and $g\circ f \homotopic \id_X$.

Such a map $g$ is called a homotopy inverse of $f$, the pair of maps is a homotopy equivalence.

If such an $f$ exists, we write $X \homotopic Y$ and say $X$ and $Y$ have the same homotopy type, or that they are homotopy equivalent.

> Note that homotopy equivalence is strictly weaker than homeomorphic equivalence, i.e., $X\cong Y$ implies $X \homotopic Y$ but not necessarily the converse.


:::

:::{.definition title="Homotopy Extension Property"}

:::
\todo[inline]{Definitions}

:::{.definition title="Homotopy Groups"}

:::
\todo[inline]{Definitions}

:::{.definition title="Homotopy Lifting Property"}

:::
\todo[inline]{Definitions}

:::{.definition title="Intersection Pairing"}
For a manifold $M$, a map on homology defined by
\[
H_{\hat i}M \tensor H_{\hat j}M \to H_{\widehat{i+j}}X\\
\alpha\tensor \beta \mapsto \left< \alpha, \beta \right>
\]
obtained by conjugating the cup product with Poincaré Duality, i.e. 

\[\left< \alpha, \beta \right> = [M] \frown ([\alpha]\dual \smile [\beta]\dual)
.\]

Then, if $[A], [B]$ are transversely intersecting submanifolds representing $\alpha, \beta$, then $$\left<\alpha, \beta\right> = [A\intersect B]$$.
If $\hat i = j$ then $\left< \alpha, \beta \right> \in H_{0} M = \ZZ$ is the signed number of intersection points.

Alt:
The pairing obtained from dualizing Poincare Duality to obtain $$\mathrm{F}(H_{i} M) \tensor \mathrm{F}(H_{n-i}M) \to \ZZ$$
Computed as an oriented intersection number between two homology classes (perturbed to be transverse).


:::

:::{.definition title="Inverse Limit"}

:::
\todo[inline]{Definitions}

:::{.definition title="Intersection Form"}
The nondegenerate bilinear form cohomology induced by the Kronecker Pairing: $$I: H^k(M_{n}) \cross H^{n-k}(M^n) \to \ZZ$$
where $n=2k$.

- When $k$ is odd, $I$ is skew-symmetric and thus a *symplectic form.*
- When $k$ is even (and thus $n \equiv 0 \mod 4$) this is a symmetric form.
- Satisfies $I(x,y) = (-1)^{k(n-k)} I(y, x)$
:::
	
:::{.definition title="Kronecker Pairing"}
A map pairing a chain with a cochain, given by 
\[
H^n(X; R) \cross H_{n}(X; R) \to R \\ ([\psi, \alpha]) \mapsto \psi(\alpha)
\]
which is a nondegenerate bilinear form.
:::

:::{.definition title="Kronecker Product"}

:::
\todo[inline]{Definitions}

:::{.definition title="Lefschetz duality"}

:::
\todo[inline]{Definitions}

:::{.definition title="Lefschetz Number"}

:::
\todo[inline]{Definitions}

:::{.definition title="Lens Space"}

:::
\todo[inline]{Definitions}

:::{.definition title="Local Degree"}
At a point $x \in V \subset M$, a generator of $H_{n}(V, V-\theset{x})$. The degree of a map $S^n \to S^n$ is the sum of its local degrees.
:::

:::{.definition title="Local Orientation"}

:::
\todo[inline]{Definitions}

:::{.definition title="Limit"}

:::
\todo[inline]{Definitions}

:::{.definition title="Linear Independence"}
A generating $S$ for a module $M$ is linearly independent if $\sum r_{i} s_{i} = 0_M \implies \forall i,~r_{i} = 0$ where $s_{i}\in S, r_{i} \in R$.
:::

:::{.definition title="Local homology"}
$H_{n}(X, X-A; \ZZ)$ is the local homology at $A$, also denoted $H_{n}(X \mid A)$
:::

:::{.definition title="Local orientation of a manifold"}
At a point $x\in M^n$, a choice of a generator $\mu_{x}$ of $H_{n}(M, M - \theset{x}) = \ZZ$.
:::

:::{.definition title="Long exact sequence"}

:::
\todo[inline]{Definitions}

:::{.definition title="Loop Space"}

:::
\todo[inline]{Definitions}

:::{.definition title="Manifold"}
An $n\dash$manifold is a Hausdorff space in which each neighborhood has an open neighborhood homeomorphic to $\RR^n$.
:::

:::{.definition title="Manifold with boundary"}
A manifold in which open neighborhoods may be isomorphic to either $\RR^n$ or a half-space $\theset{\mathbf{x} \in \RR^n \mid x_{i} > 0}$.
:::

:::{.definition title="Mapping Cone"}

:::
\todo[inline]{Definitions}

:::{.definition title="Mapping Cylinder"}

:::
\todo[inline]{Definitions}

:::{.definition title="Mapping Path Space"}

:::
\todo[inline]{Definitions}

:::{.definition title="Mayer-Vietoris Sequence"}

:::
\todo[inline]{Definitions}

:::{.definition title="Monodromy"}

:::
\todo[inline]{Definitions}

:::{.definition title="Moore Space"}

:::
\todo[inline]{Definitions}

:::{.definition title="N-cell"}

:::
\todo[inline]{Definitions}

:::{.definition title="N-connected"}

:::
\todo[inline]{Definitions}

:::{.definition title="Normal covering space (a.k.a. 'regular')"}
A covering space is **normal** if and only if for every $x\in X$ and every pair of lifts $\tilde x_1, \tilde x_2$, there is a deck transformation $f$ such that $f(\tilde x_1) = \tilde x_2$.
:::

:::{.definition title="Nullhomotopic"}
A map $X\mapsvia{f} Y$ is *nullhomotopic* if it is homotopic to a constant map $X \mapsvia{g} \theset{y_{0}}$; that is, there exists a homotopy 
\[  
F: X\cross I &\to Y \\
\restrictionof{F}{X\cross\theset{0}} &= f \quad F(x, 0) = f(x) \\
\restrictionof{F}{X\cross\theset{1}} &= g  \quad F(x, 1) = g(x) = y_{0}\\
.\]

Alt:

If $f$ is homotopic to a constant map, say $f: x \mapsto y_0$ for some fixed $y_0 \in Y$, then $f$ is said to be *nullhomotopic*. In other words, if $f:X\into Y$ is nullhomotopic, then there exists a homotopy $H: X\cross I \into Y$ such that $H(x, 0) = f(x)$ and $H(x, 1) = y_0$.

Note that constant maps (or anything homotopic) induce zero homomorphisms.


:::

:::{.definition title="Orbit space"}
For a group action $G\actson X$, the **orbit space** $X/G$ is defined as $X/\sim$  where $\forall x,y\in X, x\sim y \iff \exists g\in G \mid g.x = y$.
:::

:::{.definition title="Orientable manifold"}
A manifold for which an orientation exists, see "Orientation of a Manifold".
:::

:::{.definition title="Orientation cover"}
For any manifold $M$, a two sheeted orientable covering space $\tilde M_{o}$. $M$ is orientable iff $\tilde M$ is disconnected. Constructed as 
\[
\tilde M = \coprod_{x\in M}\theset{\mu_{x} \mid \mu_{x}~ \text{is a local orientation}}
.\]
:::

:::{.definition title="Orientation of a manifold"}
A family of $\theset{\mu_{x}}_{x\in M}$ with local consistency: if $x,y \in U$ then $\mu_{x}, \mu_{y}$ are related via a propagation.

Formally, a function $$M^n \to \coprod_{x\in M} H(X \mid \theset{x})\\ x \mapsto \mu_{x}$$ such that $\forall x \exists N_{x}$ in which  $\forall y\in N_{x}$, the preimage of each $\mu_{y}$ under the map $H_{n}(M\mid N_{x}) \surjects H_{n}(M\mid y)$ is a single generator $\mu_{N_{x}}$.

TFAE:

- $M$ is orientable.
- The map $W: (M, x) \to \ZZ_{2}$ is trivial.
- $\tilde M_{o} = M \coprod \ZZ_{2}$ (two sheets).
- $\tilde M_{o}$ is disconnected
- The projection $\tilde M_{o} \to M$ admits a section.

:::

:::{.definition title="Oriented manifold"}

:::
\todo[inline]{Definitions}

:::{.definition title="Path"}

:::
\todo[inline]{Definitions}

:::{.definition title="Path Lifting Property"}

:::
\todo[inline]{Definitions}

:::{.definition title="Perfect Pairing"}
A pairing alone is an $R\dash$bilinear module map, or equivalently a map out of a tensor product since $p: M\tensor_{R} N \to L$ can be partially applied to yield $\phi: M \to L^N = \hom_{R}(N, L)$. A pairing is **perfect** when $\phi$ is an isomorphism.
:::

:::{.definition title="Poincaré Duality"}
For a closed, orientable $n\dash$manifold, following map $[M] \frown \wait$ is an isomorphism: $$ D: H^k(M; R) \to H_{n-k}(M; R) \\ D(\alpha) = [M] \frown \alpha$$
:::

:::{.definition title="Projective Resolution"}

:::
\todo[inline]{Definitions}

:::{.definition title="Properly Discontinuous"}

:::
\todo[inline]{Definitions}

:::{.definition title="Pullback"}

:::
\todo[inline]{Definitions}

:::{.definition title="Pushout"}

:::
\todo[inline]{Definitions}

:::{.definition title="Quasi-isomorphism"}

:::
\todo[inline]{Definitions}

:::{.definition title="R-orientability"}

:::
\todo[inline]{Definitions}

:::{.definition title="Relative boundaries"}

:::
\todo[inline]{Definitions}

:::{.definition title="Relative cycles"}

:::
\todo[inline]{Definitions}

:::{.definition title="Relative homotopy groups"}

:::
\todo[inline]{Definitions}

:::{.definition title="Semilocally Simply Connected"}
A space $X$ is **semilocally simply connected** if every $x\in X$ has a neighborhood $U$ such that $U\injects X$ induces the trivial map $\pi_1(U;x) \to \pi_1(X, x)$.
:::

:::{.definition title="Short exact sequence"}

:::
\todo[inline]{Definitions}

:::{.definition title="Simplicial Complex"}
Given a simplex $\sigma = [v_1 \cdots v_n]$, define the **face map** 
\[
\del_i:\Delta^n &\to \Delta^{n-1} \\ 
\sigma &\mapsto  [v_1 \cdots \hat v_i \cdots v_n]
\]

A **simplicial complex** is a set $K$ satisfying

1. $\sigma \in K \implies \del_i\sigma \in K$.

2. $\sigma,\tau\in K \implies \sigma\intersect\tau = \emptyset,~ \del_i\sigma,~\text{or}~\del_i\tau$.

  This amounts to saying that any collection of $(n-1)$-simplices uniquely determines an $n$-simplex (or its lack thereof), or that that map $\Delta^k \into X$ is a continuous injection from the standard simplex in $\RR^n$.

3. $\abs{K\intersect B_\varepsilon(\sigma)} < \infty$ for every $\sigma\in K$, identifying $\sigma \subseteq \RR^n$.

:::

:::{.definition title="Simplicial Map"}
For a map $$K\mapsvia{f} L$$ between simplicial complexes, $f$ is a simplicial map if for any set of vertices $\theset{v_{i}}$ spanning a simplex in $K$, the set $\theset{f(v_{i})}$ are the vertices of a simplex in $L$.
:::

:::{.definition title="Simply Connected"}
A space $X$ is **simply connected** if and only if $X$ is path-connected and every loop \( \gamma : S^1 \mapsvia{} X \) can be contracted to a point.

Equivalently, there exists a lift \( \hat \gamma : D^2 \mapsvia{} X \) such that \( \ro{\hat \gamma}{\bd D^2} = \gamma  \).

Equivalently, for any two paths \( p_1, p_2: I \mapsvia{} X \) such that \( p_1(0) = p_2(0) \) and \( p_1(1) = p_2(1) \), there exists a homotopy \( F: I^2 \mapsvia{} X \) such that \( \ro{F}{0} = p_1,\, \ro{F}{0} = p_2 \).

Equivalently, \( \pi _1 X = 1 \) is trivial.
:::

:::{.definition title="Singular Chain"}

\[x \in C_{n}(x) \implies X = \sum_{i} n_{i} \sigma_{i} = \sum_{i} n_{i} (\Delta^n \mapsvia{\sigma_{i}} X)
.\]
:::

:::{.definition title="Singular Cochain"}

\[x \in C^n(x) \implies X = \sum_{i} n_{i} \psi_{i} = \sum_{i} n_{i} (\sigma_{i} \mapsvia{\psi_{i}} X)
.\]
:::

:::{.definition title="Singular Homology"}

:::
\todo[inline]{Definitions}

:::{.definition title="Smash Product"}

:::
\todo[inline]{Definitions}

:::{.definition title="Suspension"}
Compact represented as $\Sigma X = CX \coprod_{\id_{X}} CX$, two cones on $X$ glued along $X$.
Explicitly given by

\[\Sigma X = \frac{X\cross I}{(X\cross \theset{0}) \union (X\cross \theset{1}) \union (\theset{x_{0}} \cross I)}
.\]
:::

:::{.definition title="Tor Group"}
For an $R\dash$module
\[
\tor_{R}^n(\wait, B) = L_{n}(\wait \tensor_{R} B)
,\]
where $L_{n}$ denotes the $n$th left derived functor.
:::

:::{.definition title="Universal Cover"}

:::
\todo[inline]{Definitions}

:::{.definition title="Weak Homotopy Equivalence"}

:::
\todo[inline]{Definitions}

:::{.definition title="Weak Topology"}

:::
\todo[inline]{Definitions}

:::{.definition title="Wedge Product"}

:::
\todo[inline]{Definitions}
