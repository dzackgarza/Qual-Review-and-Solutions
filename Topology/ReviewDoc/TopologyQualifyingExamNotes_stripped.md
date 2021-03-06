
# Preface

References:

-   Munkres [@munkres_2018]
-   Hatcher [@hatcher_2002]

Some fun resources:

-   [The Line with Two Origins](https://blogs.scientificamerican.com/roots-of-unity/a-few-of-my-favorite-spaces-the-line-with-2-origins/)

## Notation

  Notation                                                   Definition
  ---------------------------------------------------------- -----------------------------------------
  \( X\times Y, \prod_{j\in J} X_j, X^{\times n} \)          Direct Products
  \( X\oplus Y, \bigoplus_{j\in J} X_j, X^{\oplus n} \)      Direct sums
  \( X\otimes Y, \bigotimes_{j\in J} X_j, X^{\otimes n} \)   Tensor products
  \( X\ast Y, \ast_{j\in J} X_j, X^{\ast n} \)               Free products
  \( {\mathbb{Z}}^n \)                                       The free abelian group of rank \( n \)
  \( F_n, {\mathbb{Z}}^{\ast n} \)                           The free group on \( n \) generators
  \( \pi_0(X) \)                                             The *set* of path components of \( X \)
  \( G=1 \)                                                  The trivial abelian group
  \( G=0 \)                                                  The trivial nonabelian group

::: {.remark}
I use \( e_G \) or \( 1_G, 0_G \) to denote identity elements in a group \( G \).
:::

::: {.remark title="on direct sums vs direct products"}
\( A\times B \) denotes the **direct product** of modules. \( A\oplus B \) denotes a **direct sum**: the subset of \( A\times B \) where only finitely many terms are nonzero. Both the product and direct sum have coordinate-wise operations. For finite index sets \( {\left\lvert {J} \right\rvert}< \infty \), the direct sum and product coincide, but in general there is only an injection \( \bigoplus_j X_i \hookrightarrow\prod_j X_j \). In the direct sum \( \bigoplus_j X_j \) have only finitely many nonzero entries, while the product allows *infinitely* many nonzero entries. So in general, I always use the product notation.
:::

::: {.remark title="on notation for free groups and free products"}
The free group on \( n \) generators is the free product of \( n \) free abelian groups, but is not generally abelian! So we use multiplicative notation, and elements
\[
x \in {\mathbb{Z}}^{\ast n} = \left< a_1, \ldots, a_n\right>
\]
are finite words in the noncommuting symbols \( a_i^k \) for \( k\in {\mathbb{Z}} \). E.g. an element may look like
\[
x = a_1^2 a_2^4 a_1 a_2^{-2}
.\]
:::

::: {.remark title="on notation for free abelian groups"}
The free abelian group of rank \( n \) is the abelianization of \( {\mathbb{Z}}^{\ast n} \), and its elements are characterized by
\[
x\in {\mathbb{Z}}^{\ast n} = \left\langle{ a_1, \cdots, a_n }\right\rangle \implies x = \sum_n c_i a_i \text{ for some } c_i \in {\mathbb{Z}}
\]
where the \( a_i \) are some generating set of \( n \) elements and we used additive notation since the group is abelian. E.g. such an element may look like
\[
x = 2a_1 + 4a_2 + a_1 - a_2 = 3a_1 + 3a_2
.\]
:::

::: {.remark title="on indexing conventions and list notation"}
Spaces are assumed to be connected and path connected, so \( \pi_0(X) = H_0(X) = {\mathbb{Z}} \). So I virtually never consider anything occurring at index zero in these notes.

Graded objects such as \( \pi_*, H_*, H^* \) are sometimes represented as lists, which always start indexing at 1. Examples:
\[
\pi_*(X) &= [\pi_1(X), \pi_2(X), \pi_3(X), \cdots] \\
H_*(X) &= [H_1(X), H_2(X), H_3(X), \cdots]
.\]
:::

## Background Algebra

::: {.fact}
An injective group morphism \( f:X\hookrightarrow Y \) where \( X \) is trivial forces \( Y \) to be trivial.
:::

::: {.proposition title="Morphisms between groups finite and infinite groups"}
There are no nontrivial homomorphisms from finite groups into free groups. In particular, any group morphism \( f: {\mathbb{Z}}_n \to {\mathbb{Z}} \) is trivial.
:::

::: {.proof title="?"}
Let \( f: G\to H \), then \( f(1_G) = 1_H \). Supposing \( g\in G \) is torsion of order \( n \), we have
\[
1_H = f(1_G) = f(g^n) = f(g)^n 
,\]

so \( f(g) \) is torsion of order dividing \( n \). But a free group is torsionfree.
:::

::: {.remark title="How to use this fact"}
This is especially useful if you have some \( f: A\to B \) and you look at the induced homomorphism \( f_*: \pi_1(A) \to\pi_1(B) \). If the former is finite and the latter contains a copy of \( {\mathbb{Z}} \), then \( f_* \) has to be the trivial map \( f_*([\alpha]) = e \in \pi_1(B) \) for every \( [\alpha] \in \pi_1(A) \). You can play a similar game when you take homology or cohomology.
:::

# Summary and Topics: Point-Set Topology

Some key high-level topics:

-   Connectedness
-   Compactness
-   Metric spaces
-   Hausdorff spaces

# Definitions

## Point-Set Topology

::: {.remark title="on the term 'locally'"}
The prefix "locally blah" almost always means that for every \( x\in X \), there exists *some* neighborhood \( N_x\ni x \) which has property "blah".
:::

::: {.definition title="Basis for a topology"}
A set \( \mathcal{B} \) is a **basis** for a topology iff

-   \( \mathcal{B} \) is closed under intersections,
-   Every \( x\in X \) is in some basic set,
-   If \( x \) is in the intersection of two basis sets \( B_1 \cap B_2 \), there is a third basic open \( B_3 \ni x \) with \( B_3 \subset B_1 \cap B_2 \).

The topology **generated** by \( \mathcal{B} \) is the following: \( U\subseteq X \) is open iff for each \( x\in U \) there is a basic open \( B \) with \( x\in B \subset U \). Equivalently, every open set is a union of basic open sets.
:::

::: {.definition title="Bounded"}
A set \( S \) in a metric space \( (X, d) \) is *bounded* iff there exists an \( m\in {\mathbb{R}} \) such that \( d(x, y) < m \) for every \( x, y\in S \).
:::

::: {.definition title="Comparability of topologies"}
Given two topologies \( \tau_1, \tau_2 \),

-   \( \tau_1 \) is **finer** than \( \tau_2 \) iff \( \tau_1 \supseteq\tau_2 \).
-   \( \tau_1 \) is **coarser** than \( \tau_2 \) iff \( \tau_1 \supseteq\tau_2 \).

Two topologies are **comparable** if either \( \tau_1 < \tau_2 \) or \( \tau_2 < \tau_1 \).

> Note: more open sets is like having a "finer" resolution.
:::

```{=tex}
\todo[inline]{Is this actually a poset relation? Fails reflexivity.}
```
::: {.definition title="Connected"}
A space \( X \) is **connected** iff there does not exist a disconnection \( X = A{\coprod}B \) with \( A, B \) nonempty open sets. I.e. \( X \) can not be written as the disjoint union of two proper nonempty open sets. Equivalently, \( X \) contains no proper nonempty clopen sets.

Note that there is an additional condition for a subspace \( Y\subset X \) to be connected:
\[
{ \operatorname{cl}} _{Y}(A) \cap V = A \cap{ \operatorname{cl}} _{Y}(B) = \emptyset
.\]
:::

::: {.definition title="Connected Components"}
Set \( x\sim y \) iff there exists a connected set \( U\ni x, y \) and take equivalence classes. These classes are the **connected components** of \( X \).
:::

::: {.definition title="Closed Sets"}
```{=tex}
\envlist
```
-   A set is closed if and only if its complement is open.
-   A set is closed iff it contains all of its limit points.
-   A closed set in a subspace: \( Y\subset X \implies { \operatorname{cl}} _{Y}(A) \coloneqq{ \operatorname{cl}} _{X}(A)\cap Y \).
:::

::: {.definition title="Closed Maps"}
See `\cref{def:open_closed_maps}`{=tex}.
:::

::: {.definition title="Closure of a set"}
For \( U \subseteq X \), the closure of \( U \) in \( X \) is given by \( { \operatorname{Cl}} _X(U) = \cap_{\substack{ B\supseteq U \\ \text{ closed} }} B \), the intersection of all closed sets in \( X \) containing \( U \). For \( Y\subseteq X \) a subspace containing \( U \), the closure of \( U \) in \( Y \) is \( { \operatorname{Cl}} _Y(U) = { \operatorname{Cl}} _X(U) \cap Y \).[^1] In general, we write \( \mkern 1.5mu\overline{\mkern-1.5muU\mkern-1.5mu}\mkern 1.5mu \coloneqq{ \operatorname{cl}} _X(U) \).

An equivalent condition: \( x\in \mkern 1.5mu\overline{\mkern-1.5muU\mkern-1.5mu}\mkern 1.5mu \iff \) every neighborhood of \( x \) intersects \( U \).[^2]
:::

::: {.definition title="Compact"}
A topological space \( (X, \tau) \) is **compact** iff every open cover has a *finite* subcover. That is, if \( \left\{{U_{j}}\right\}_{j\in J} \subseteq \tau \) is a collection of open sets such that \( X = \displaystyle\bigcup_{j\in J} U_{j} \), then there exists a *finite* subset \( J' \subset J \) such that \( X \subseteq \displaystyle\bigcup_{j\in J'} U_{j} \).
:::

::: {.definition title="Continuous Map"}
A map \( f:X\to Y \) between topological spaces is **continuous** if and only if whenever \( U \subseteq Y \) is open, \( f ^{-1} (U) \subseteq X \) is open.
:::

::: {.definition title="Cover"}
A collection of subsets \( \left\{{U_\alpha}\right\} \) of \( X \) is said to **cover** \( X \) iff \( X = \cup_{\alpha} U_\alpha \). If \( A\subseteq X \) is a subspace, then this collection **covers** \( A \) iff \( A\subseteq \cup_{\alpha} U_\alpha \).
:::

::: {.definition title="Dense"}
A subspace \( Q\subset X \) is **dense** iff every neighborhood of every point in \( x \) intersects \( Q \). Equivalently, \( { \operatorname{cl}} _X(Q) = Q \).
:::

::: {.definition title="First Countable"}
A space is **first-countable** iff every point admits a countable neighborhood basis.
:::

::: {.definition title="Hausdorff"}
A topological space \( X \) is *Hausdorff* iff points can be separated by disjoint neighborhoods: for every \( p\neq q \in X \) there exist disjoint open sets \( U\ni p \) and \( V\ni q \).
:::

::: {.definition title="Injection"}
A map \( \iota:A\to B \) with a **left** inverse \( f:B\to A \) satisfying \( f\circ \iota = \operatorname{id}_A \). Note that this is equivalent to \( f(x) = f(y) \implies x = y \).
:::

::: {.definition title="Lebesgue Number"}
For \( (X, d) \) a compact metric space and \( \left\{{U_\alpha}\right\}\rightrightarrows X \), there exists a **Lebesgue number** \( \delta_{L} > 0 \) which satisfies
\[
A\subset X, ~ {\operatorname{diam}}(A) < \delta_{L} \implies A\subseteq U_\alpha \text{ for some } \alpha
.\]
:::

::: {.definition title="Limit Point"}
For \( A\subset X \), \( x \) is a **limit point** of \( A \) if every punctured neighborhood \( P_{x} \) of \( x \) intersects \( A \). I.e., every neighborhood of \( x \) intersects \( A \) at a point other than \( x \). Equivalently, \( x\in { \operatorname{cl}} _{X}(A\setminus\left\{{x}\right\}) \).
:::

::: {.definition title="Locally Connected"}
A space is **locally connected** iff every neighborhood of every point admits a smaller connected neighborhood. I.e. for all \( x\in X \), for all \( N_x \ni x \), there exists a connected set \( U \subset X \) with \( x\in U \).
:::

::: {.definition title="Locally Compact"}
A space \( X \) is *locally compact* iff every \( x\in X \) has a neighborhood contained in a compact subset of \( X \).

> Note: authors such as Hartshorne often *also* require that \( X \) is Hausdorff, and refer to the above definition as **quasicompactness**.
:::

::: {.definition title="Locally Finite"}
A collection of subsets \( {\mathcal{S}} \) of \( X \) is *locally finite* iff each point of \( M \) has a neighborhood that intersects at most finitely many elements of \( {\mathcal{S}} \).
:::

::: {.definition title="Locally Path-Connected"}
A space \( X \) is **locally path-connected** iff every point in \( X \) admits some path-connected neighborhood. Equivalently, \( X \) admits a basis of path-connected open subsets.
:::

::: {.definition title="Neighborhood"}
A **neighborhood** of a point \( x \) is *any* open set containing \( x \).
:::

::: {.definition title="Normal"}
A space is **normal** if any two disjoint closed subsets can be separated by neighborhoods.
:::

::: {.definition title="Neighborhood Basis"}
If \( p\in X \), a **neighborhood basis** at \( p \) is a collection \( {\mathcal{B}}_{p} \) of neighborhoods of \( p \) such that if \( N_{p} \) is a neighborhood of \( p \), then \( N_{p} \supseteq B \) for at least one \( B\in {\mathcal{B}}_{p} \).
:::

::: {.definition title="Open and Closed Maps" ref="def:open_closed_maps"}
A map \( f:X\to Y \) is an **open map** (respectively a **closed map**) if and only if whenever \( U \subseteq X \) is open (resp. closed), \( f(U) \) is again open (resp. closed)\>
:::

::: {.definition title="Paracompact"}
A topological space \( X \) is **paracompact** iff every open cover of \( X \) admits an open locally finite refinement.
:::

::: {.definition title="Quotient Map"}
A map \( q:X\to Y \) is a **quotient map** if and only if

1.  \( q \) is surjective, and
2.  \( U \subseteq Y \) is open if and only if \( q ^{-1} (U) \) is open.
:::

::: {.definition title="Path Connected"}
A space \( X \) is **path connected** if and only if for every pair of points \( x\neq y \) there exists a continuous map \( f:I \to X \) such that \( f(0) = x \) and \( f(1) = y \).
:::

::: {.definition title="Path Components"}
Set \( x\sim y \) iff there exists a path-connected set \( U\ni x, y \) and take equivalence classes.
:::

::: {.definition title="Precompact"}
A subset \( A\subseteq X \) is **precompact** iff \( { \operatorname{cl}} _{X}(A) \) is compact.
:::

::: {.definition title="Product topology"}
For \( (X, \tau_X) \) and \( (Y, \tau_Y) \) topological spaces, defining
\[
\tau_{X \times Y} \coloneqq\left\{{U \times V {~\mathrel{\Big|}~}U\in \tau_X,\, V\in \tau_Y}\right\}
\]
yields the **product topology** on \( X \times Y \).
:::

::: {.definition title="Quasicompact"}
A topological space \( X \) (possible non-Hausdorff) is **quasi-compact** iff every open cover admits a finite subcover. If \( X \) is additionally Hausdorff, \( X \) is said to be **compact**.

> Note: this is a distinction coming from algebraic geometry, and Hartshorne in particular.
:::

::: {.definition title="Refinement"}
A cover \( {\mathcal{V}}\rightrightarrows X \) is a **refinement** of \( {\mathcal{U}}\rightrightarrows X \) iff for each \( V\in {\mathcal{V}} \) there exists a \( U\in{\mathcal{U}} \) such that \( V\subseteq U \).
:::

::: {.definition title="Regular"}
A space \( X \) is **regular** if whenever \( x\in X \) and \( F\not\ni x \) is closed, \( F \) and \( x \) are separated by neighborhoods.
:::

::: {.definition title="Retract"}
A map \( r \) in \( A\mathrel{\textstyle\substack{\hookrightarrow^{\iota}\\\textstyle\dashleftarrow_{r}}} B \) satisfying
\[r\circ\iota = \operatorname{id}_{A}.\]
A **retract** of \( B \) onto a subspace \( A \) is a map \( r:B\to A \) that is a left-inverse for the inclusion \( f:A\hookrightarrow B \), so \( r \circ f = \operatorname{id}_A \):

```{=tex}
\begin{tikzcd}
    A && B
    \arrow["f", from=1-1, to=1-3]
    \arrow["r"', curve={height=18pt}, dashed, from=1-3, to=1-1]
    \arrow[loop left, from=1-1]{l}{\mathrm{id}_A} 
\end{tikzcd}
```
> [Link to (partial) Diagram](https://q.uiver.app/?q=WzAsMixbMCwwLCJBIl0sWzIsMCwiQiJdLFswLDEsImYiXSxbMSwwLCJyIiwyLHsiY3VydmUiOjMsInN0eWxlIjp7ImJvZHkiOnsibmFtZSI6ImRhc2hlZCJ9fX1dXQ==)

Equivalently, a continuous map \( r:B\to A \) with \( { \left.{{r}} \right|_{{A}} } = \operatorname{id}_A \) restricting to the identity on \( A \), i.e. fixing \( A \) pointwise. Note that \( r \) is necessarily a surjection.

Alt: Let \( X \) be a topological space and \( A \subset X \) be a subspace, then a **retraction** of \( X \) onto \( A \) is a map \( r: X\to X \) such that the image of \( X \) is \( A \) and \( r \) restricted to \( A \) is the identity.
:::

::: {.remark}
If \( X \) retracts onto \( A \) with \( \iota:A\hookrightarrow X \), then \( i_* \) is injective. Any nonempty space retracts to a point via a constant map.
:::

::: {.definition title="Saturated"}
A subset \( U \subseteq X \) is **saturated** with respect to a surjective map \( p: X\twoheadrightarrow Y \) if and only if whenever \( U \cap p ^{-1} (y) = V \neq \emptyset \), we have \( V \subseteq U \), i.e. \( U \) contains every set \( p ^{-1} (y) \) that it intersects. Equivalently, \( U \) is the complete inverse image of a subset of \( Y \).
:::

::: {.definition title="Separable spaces"}
A space \( X \) is **separable** iff \( X \) contains a countable dense subset.
:::

::: {.definition title="Second Countable"}
A space is *second-countable* iff it admits a countable basis.
:::

::: {.definition title="The subspace topology"}
For \( (X, \tau) \) a topological space and \( U \subseteq X \) an arbitrary subset, the space \( (U, \tau_U) \) is a topological space with a **subspace topology** defined by
\[
\tau_U \coloneqq\left\{{Y \cap U {~\mathrel{\Big|}~}U \in \tau}\right\}
.\]
:::

::: {.definition title="Surjection"}
A map \( \pi \) with a **right** inverse \( f \) satisfying
\[\pi \circ f = \operatorname{id}\]
:::

::: {.definition title="$T_n$ Spaces (Separation Axioms)"}
```{=tex}
\envlist
```
-   \( T_0 \): Points are distinguishable. For any 2 points \( x_1\neq x_2 \), at least one \( x_i \) (say \( x_1 \)) admits a neighborhood not containing \( x_2 \).

-   \( T_1 \): For any 2 points, *both* admit neighborhoods not containing the other. Equivalently, points are closed.

-   \( T_2 \): For any 2 points, both admit *disjoint* separating neighborhoods.

-   \( T_{2.5} \): For any 2 points, both admit *disjoint closed* separating neighborhoods.

-   \( T_3 \): \( T_0 \) & *regular*. Given any point \( x \) and any closed \( F\not\ni x \), there are neighborhoods separating \( F \) and \( x \).

-   \( T_{3.5} \): \( T_0 \) & completely regular. Any point \( x \) and closed \( F\not\ni x \) can be separated by a continuous function.

-   \( T_4 \): \( T_1 \) & normal. Any two disjoint closed subsets can be separated by neighborhoods.
:::

::: {.example title="Counterexamples for separation axioms"}
```{=tex}
\envlist
```
-   Not \( T_0 \): the space \( \left\{{ f:{\mathbb{R}}\to {\mathbb{C}}{~\mathrel{\Big|}~}\int_{\mathbb{R}}{\left\lvert {f} \right\rvert}^2 < \infty }\right\} \), since two a.e. equal functions aren't *distinguishable* (they have precisely the same set of neighborhoods).
-   \( T_1 \) but not \( T_0 \): \( \operatorname{Spec}R \) for \( R\in \mathsf{CRing} \) with the Zariski topology. There are points that aren't closed: \( \operatorname{Spec}R \setminus\operatorname{mSpec}R \).
:::

::: {.definition title="Topology"}
```{=tex}
\envlist
```
-   Using open sets: closed under arbitrary unions and finite intersections.
-   Using closed sets: closed under arbitrary intersections and finite unions.
:::

::: {.remark}
A mnemonic: in \( {\mathbb{R}} \), \( \cap_{n\in {\mathbb{N}}} (-1/n, 1/n) = \left\{{0}\right\} \) which is closed in \( {\mathbb{R}} \).
:::

::: {.definition title="Topological Embedding"}
A topological **embedding** is a continuous map \( f:X\to Y \) which is a homeomorphism onto its image, i.e. \( X\cong_{{\mathsf{Top}}} f(X) \).
:::

::: {.definition title="Uniform Continuity"}
For \( f: (X, d_{x}) \to (Y, d_{Y}) \) metric spaces,
\[
\forall \varepsilon> 0, ~\exists \delta > 0 \text{ such that } \quad d_{X}(x_{1}, x_{2}) < \delta \implies d_{Y}(f(x_{1}), f(x_{2})) < \varepsilon
.\]
:::

## Algebraic Topology

::: {.definition title="Acyclic"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Alexander duality"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Basis of a module"}
For an \( R{\hbox{-}} \)module \( M \), a basis \( B \) is a linearly independent generating set.
:::

::: {.definition title="Boundary"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Boundary of a manifold"}
Points \( x\in M^n \) defined by
\[
{\partial}M = \left\{{x\in M: H_{n}(M, M-\left\{{x}\right\}; {\mathbb{Z}}) = 0}\right\}
\]
:::

::: {.definition title="Cap Product"}
Denoting \( \Delta^p \xrightarrow{\sigma} X \in C_{p}(X; G) \), a map that sends pairs (\( p{\hbox{-}} \)chains, \( q{\hbox{-}} \)cochains) to \( (p-q){\hbox{-}} \)chains \( \Delta^{p-q} \to X \) by
\[
H_{p}(X; R)\times H^q(X; R) \xrightarrow{\frown} H_{p-q}(X; R)\\
\sigma \frown \psi = \psi(F_{0}^q(\sigma))F_{q}^p(\sigma)
\]
where \( F_{i}^j \) is the face operator, which acts on a simplicial map \( \sigma \) by restriction to the face spanned by \( [v_{i} \ldots v_{j}] \), i.e. \( F_{i}^j(\sigma) = {\left.{{\sigma}} \right|_{{[v_{i} \ldots v_{j}]}} }  \).
:::

::: {.definition title="Cellular Homology"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Cellular Map"}
A map \( X \xrightarrow{f} Y \) is said to be cellular if \( f(X^{(n)}) \subseteq Y^{(n)} \) where \( X^{(n)} \) denotes the \( n{\hbox{-}} \) skeleton.
:::

::: {.definition title="Chain"}
An element \( c \in C_{p}(X; R) \) can be represented as the singular \( p \) simplex \( \Delta^p \to X \).
:::

::: {.definition title="Chain Homotopy"}
Given two maps between chain complexes \( (C_*, {\partial}_{C}) \xrightarrow{f, ~g} (D_*, {\partial}_{D}) \), a chain homotopy is a family \( h_{i}: C_{i} \to B_{i+1} \) satisfying
\[f_{i}-g_{i} = {\partial}_{B, i-1}\circ h_{n} + h_{i+1}\circ {\partial}_{A, i}\]
.

```{=html}
<!--![](https://upload.wikimedia.org/wikipedia/commons/thumb/c/cb/Chain_{homotopy_{between_chain_complexes}}.svg/650px-Chain_{homotopy_{between_chain_complexes}}.svg.png)-->
```
:::

::: {.definition title="Chain Map"}
A map between chain complexes \( (C_*, {\partial}_{C}) \xrightarrow{f} (D_*, {\partial}_{D}) \) is a chain map iff each component \( C_{i} \xrightarrow{f_{i}} D_{i} \) satisfies
\[
f_{i-1}\circ{\partial}_{C, i} = {\partial}_{D,i} \circ f_{i}
\]
(i.e this forms a commuting ladder)

```{=html}
<!--![](https://upload.wikimedia.org/wikipedia/commons/thumb/9/9b/Chain_{map}.svg/650px-Chain_{map}.svg.png)-->
```
:::

::: {.definition title="Closed manifold"}
A manifold that is compact, with or without boundary.
:::

::: {.definition title="Coboundary"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Cochain"}
An cochain \( c \in C^p(X; R) \) is a map \( c \in \hom(C_{p}(X; R), R) \) on chains.
:::

::: {.definition title="Cocycle"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Constant Map"}
A *constant map* \( f: X\to Y \) iff \( f(X) = y_{0} \) for some \( y_{0}\in Y \), i.e. for every \( x\in X \) the output value \( f(x) = y_{0} \) is the same.
:::

::: {.definition title="Colimit"}
For a directed system \( (X_{i}, f_{ij} \), the **colimit** is an object \( X \) with a sequence of projections \( \pi_{i}:X\to X_{i} \) such that for any \( Y \) mapping into the system, the following diagram commutes:

```{=tex}
\begin{tikzcd}
                 &                            &  & Y \arrow[lldddd, "\psi_{j}"] \arrow[rrdddd, "\psi_{i}"] \arrow[dd, "\exists!", dashed] &  &               &        \\
                 &                            &  &                                                                                    &  &               &        \\
                 &                            &  & X \arrow[lldd, "\pi_{j}"] \arrow[rrdd, "\pi_{i}"]                                      &  &               &        \\
                 &                            &  &                                                                                    &  &               &        \\
\cdots \arrow[r] & X_{j} \arrow[rrrr, "f_{ij}"] &  &                                                                                    &  & X_{i} \arrow[r] & \cdots
\end{tikzcd}
```
:::

::: {.example title="of colimits"}
```{=tex}
\envlist
```
-   Products
-   Pullbacks
-   Inverse / projective limits
-   The \( p{\hbox{-}} \)adic integers \( {\mathbb{Z}}_{p} \).
:::

::: {.definition title="Contractible"}
A space \( X \) is **contractible** if \( \operatorname{id}_X \) is nullhomotopic. i.e. the identity is homotopic to a constant map \( c(x) = x_0 \).

Equivalently, \( X \) is contractible if \( X \simeq\left\{{x_0}\right\} \) is homotopy equivalent to a point. This means that there exists a mutually inverse pair of maps \( f: X \to\left\{{x_0}\right\} \) and \( g:\left\{{x_0}\right\} \to X \) such that \( f\circ g \simeq\operatorname{id}_{\left\{{x_0}\right\}} \) and \( g\circ f \simeq\operatorname{id}_X \).[^3]
:::

::: {.definition title="Coproduct"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Covering Space"}
A **covering space** of \( X \) is the data \( p: \tilde X \to X \) such that

1.  Each \( x\in X \) admits a neighborhood \( U \) such that \( p ^{-1} (U) \) is a union of disjoint open sets in \( \tilde V_i \subseteq X \) (the **sheets** of \( \tilde X \) over \( U \)),
2.  \( { \left.{{p}} \right|_{{V_i}} }: V_i \to U \) is a homeomorphism for each sheet.

An **isomorphism** of covering spaces \( \tilde X_1 \cong \tilde X_2 \) is a commutative diagram

```{=tex}
\begin{tikzcd}
    {\tilde X_1} && {\tilde X_2} \\
    \\
    & {X}
    \arrow["{p_1}"', from=1-1, to=3-2]
    \arrow["{p_2}", from=1-3, to=3-2]
    \arrow["{f}", from=1-1, to=1-3]
\end{tikzcd}
```
> [Link to diagram](https://q.uiver.app/?q=WzAsMyxbMCwwLCJcXHRpbGRlIFhfMSJdLFsxLDIsIlgiXSxbMiwwLCJcXHRpbGRlIFhfMiJdLFswLDEsInBfMSIsMl0sWzIsMSwicF8yIl0sWzAsMiwiZiJdXQ==)
:::

::: {.definition title="Cup Product"}
A map taking pairs (\( p{\hbox{-}} \)cocycles, \( q{\hbox{-}} \)cocycles) to \( (p+q){\hbox{-}} \)cocyles by
\[
H^p(X; R) \times H^q(X; R) \xrightarrow{\smile} H^{p+q}(X; R)\\
(a \cup b)(\sigma) = a(\sigma \circ I_{0}^p)~b(\sigma \circ I_{p}^{p+q})
\]
where \( \Delta^{p+q} \xrightarrow{\sigma} X \) is a singular \( p+q \) simplex and

\[I_{i}^j: [i, \cdots, j] \hookrightarrow\Delta^{p+q}
.\]

is an embedding of the \( (j-i){\hbox{-}} \)simplex into a \( (p+q){\hbox{-}} \)simplex.
:::

::: {.example title="Applications of the cup product"}
On a manifold, the cup product is Poincaré dual to the intersection of submanifolds. Also used to show \( T^2 \not\simeq S^2 \vee S^1 \vee S^1 \).
:::

::: {.definition title="CW Complex"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="CW Cell"}
An \( n{\hbox{-}} \)cell of \( X \), say \( e^n \), is the image of a map \( \Phi: B^n \to X \). That is, \( e^n = \Phi(B^n) \). Attaching an \( n{\hbox{-}} \)cell to \( X \) is equivalent to forming the space \( B^n \coprod_{f} X \) where \( f: {\partial}B^n \to X \).

-   A \( 0{\hbox{-}} \)cell is a point.
-   A \( 1{\hbox{-}} \)cell is an interval \( [-1, 1] = B^1 \subset {\mathbb{R}}^1 \). Attaching requires a map from \( S^0 =\left\{{-1, +1}\right\} \to X \)
-   A \( 2{\hbox{-}} \)cell is a solid disk \( B^2 \subset {\mathbb{R}}^2 \) in the plane. Attaching requires a map \( S^1 \to X \).
-   A \( 3{\hbox{-}} \)cell is a solid ball \( B^3 \subset {\mathbb{R}}^3 \). Attaching requires a map from the sphere \( S^2 \to X \).
:::

::: {.definition title="Cycle"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Deck transformation"}
For a covering space \( \tilde X \xrightarrow{p} X \), self-isomorphisms \( f:\tilde X \to \tilde X \) of covering spaces are referred to as **deck transformations**.
:::

::: {.definition title="Deformation"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Deformation Retract"}
A map \( r \) in \( A\mathrel{\textstyle\substack{\hookrightarrow^{\iota}\\\textstyle\dashleftarrow_{r}}} X \) that is a retraction (so \( r\circ \iota = \operatorname{id}_{A} \)) *that also satisfies* \( \iota \circ r \simeq\operatorname{id}_{X} \).

> Note that this is equality in one direction, but only homotopy equivalence in the other.

Equivalently, a map \( F:I\times X\to X \) such that
\[
F_{0}(x) &= \operatorname{id}_{X}
F_{t}(x)\mathrel{\Big|}_{A} &= \operatorname{id}_{A}
F_{1}(X) &= A
.\]

Alt:

A **deformation retract** is a homotopy \( H:X\times I \to X \) from \( \operatorname{id}_X \) to \( \operatorname{id}_A \) where \( { \left.{{H}} \right|_{{A}} } = \operatorname{id}_A \) fixes \( A \) at all times.
\[
H: X\times I \to X \\
H(x, 0) = \operatorname{id}_X \\
H(x, 1) = \operatorname{id}_A \\
x\in A \implies H(x, t) \in A \quad \forall t
\]
:::

::: {.remark}
A deformation retract between a space and a subspace is a homotopy equivalence, and further \( X\simeq Y \) iff there is a \( Z \) such that both \( X \) and \( Y \) are deformation retracts of \( Z \). Moreover, if \( A \) and \( B \) both have deformation retracts onto a common space \( X \), then \( A \simeq B \).
:::

::: {.definition title="Degree of a Map of Spheres"}
Given any \( f: S^n \to S^n \), there are induced maps on homotopy and homology groups. Taking \( f^*: H^n(S^n) \to H^n(S^n) \) and identifying \( H^n(S^n) \cong {\mathbb{Z}} \), we have \( f^*: {\mathbb{Z}}\to{\mathbb{Z}} \). But homomorphisms of free groups are entirely determined by their action on generators. So if \( f^*(1) = n \), define \( n \) to be the **degree** of \( f \).
:::

::: {.definition title="Derived Functor"}
For a functor \( T \) and an \( R{\hbox{-}} \)module \( A \), a *left derived functor* \( (L_{nT}) \) is defined as \( h_{n}(TP_{A}) \), where \( P_{A} \) is a projective resolution of \( A \).
:::

::: {.definition title="Dimension of a manifold"}
For \( x\in M \), the only nonvanishing homology group \( H_{i}(M, M - \left\{{x}\right\}; {\mathbb{Z}}) \)
:::

::: {.definition title="Direct Limit"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Direct Product"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Direct Sum"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Euler Characteristic"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Exact Functor"}
A functor \( T \) is *right exact* if a short exact sequence

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

::: {.example title="of an exact functor"}
\( {-}\otimes_{R} {-} \) is a right exact bifunctor.
:::

::: {.definition title="Exact Sequence"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Excision"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Ext Group"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Flat"}
An \( R{\hbox{-}} \)module is flat if \( A\otimes_{R} {-} \) is an exact functor.
:::

::: {.definition title="Free and Properly Discontinuous"}
An action \( G\curvearrowright X \) is **properly discontinuous** if each \( x\in X \) has a neighborhood \( U \) such that all of the images \( g(U) \) for \( g\in G \) are disjoint, i.e. \( g_1(U) \cap g_2(U) \neq \emptyset \implies g_1 = g_2 \). The action is **free** if there are no fixed points.

Sometimes a slightly weaker condition is used: every point \( x\in X \) has a neighborhood \( U \) such that \( U \cap G(U) \neq \emptyset \) for only finitely many \( G \).
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Free module"}
A \( {\hbox{-}} \)module \( M \) with a basis \( S = \left\{{s_{i}}\right\} \) of generating elements. Every such module is the image of a unique map \( \mathcal{F}(S) = R^S \twoheadrightarrow M \), and if \( M = \left< S \mathrel{\Big|}\mathcal{R} \right> \) for some set of relations \( \mathcal{R} \), then \( M \cong R^S / \mathcal{R} \).
:::

::: {.definition title="Free Product"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Free product with amalgamation"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Fundamental Class"}
For a connected, closed, orientable manifold, \( [M] \) is a generator of \( H_{n}(M; {\mathbb{Z}}) = {\mathbb{Z}} \).
:::

::: {.definition title="Fundamental Group"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Generating Set"}
\( S = \left\{{s_{i}}\right\} \) is a generating set for an \( R{\hbox{-}} \) module \( M \) iff
\[x\in M \implies x = \sum r_{i} s_{i}\]
for some coefficients \( r_{i} \in R \) (where this sum may be infinite).
:::

::: {.definition title="Gluing Along a Map"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Group Ring"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Homologous"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Homotopic"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Homotopy"}
Let \( X, Y \) be topological spaces and \( f,g: X \to Y \) continuous maps. Then a **homotopy** from \( f \) to \( g \) is a continuous function

\( F: X \times I \to Y \)

such that

\( F(x, 0) = f(x) \) and \( F(x,1) = g(x) \)

for all \( x\in X \). If such a homotopy exists, we write \( f\simeq g \). This is an equivalence relation on \( \text{Hom}(X,Y) \), and the set of such classes is denoted \( [X,Y] \coloneqq\hom (X,Y)/\simeq \).
:::

::: {.definition title="Homotopy Class"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Homotopy Equivalence"}
Let \( f: X \to Y \) be a continuous map, then \( f \) is said to be a *homotopy equivalence* if there exists a continuous map \( g: X \to Y \) such that

\( f\circ g \simeq\operatorname{id}_Y \) and \( g\circ f \simeq\operatorname{id}_X \).

Such a map \( g \) is called a homotopy inverse of \( f \), the pair of maps is a homotopy equivalence.

If such an \( f \) exists, we write \( X \simeq Y \) and say \( X \) and \( Y \) have the same homotopy type, or that they are homotopy equivalent.

> Note that homotopy equivalence is strictly weaker than homeomorphic equivalence, i.e., \( X\cong Y \) implies \( X \simeq Y \) but not necessarily the converse.
:::

::: {.definition title="Homotopy Extension Property"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Homotopy Groups"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Homotopy Lifting Property"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Intersection Pairing"}
For a manifold \( M \), a map on homology defined by
\[
H_{\widehat{i}}M \otimes H_{\widehat{j}}M \to H_{\widehat{i+j}}X\\
\alpha\otimes\beta \mapsto \left< \alpha, \beta \right>
\]
obtained by conjugating the cup product with Poincaré Duality, i.e. 

\[\left< \alpha, \beta \right> = [M] \frown ([\alpha] {}^{ \check{} }\smile [\beta] {}^{ \check{} })
.\]

Then, if \( [A], [B] \) are transversely intersecting submanifolds representing \( \alpha, \beta \), then
\[\left<\alpha, \beta\right> = [A\cap B]\]
. If \( \widehat{i} = j \) then \( \left< \alpha, \beta \right> \in H_{0} M = {\mathbb{Z}} \) is the signed number of intersection points.

Alt: The pairing obtained from dualizing Poincare Duality to obtain
\[\mathrm{F}(H_{i} M) \otimes\mathrm{F}(H_{n-i}M) \to {\mathbb{Z}}\]
Computed as an oriented intersection number between two homology classes (perturbed to be transverse).
:::

::: {.definition title="Inverse Limit"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Intersection Form"}
The nondegenerate bilinear form cohomology induced by the Kronecker Pairing:
\[I: H^k(M_{n}) \times H^{n-k}(M^n) \to {\mathbb{Z}}\]
where \( n=2k \).

-   When \( k \) is odd, \( I \) is skew-symmetric and thus a *symplectic form.*
-   When \( k \) is even (and thus \( n \equiv 0 \pmod 4 \)) this is a symmetric form.
-   Satisfies \( I(x,y) = (-1)^{k(n-k)} I(y, x) \)
:::

::: {.definition title="Kronecker Pairing"}
A map pairing a chain with a cochain, given by
\[
H^n(X; R) \times H_{n}(X; R) \to R \\ ([\psi, \alpha]) \mapsto \psi(\alpha)
\]
which is a nondegenerate bilinear form.
:::

::: {.definition title="Kronecker Product"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Lefschetz duality"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Lefschetz Number"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Lens Space"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Local Degree"}
At a point \( x \in V \subset M \), a generator of \( H_{n}(V, V-\left\{{x}\right\}) \). The degree of a map \( S^n \to S^n \) is the sum of its local degrees.
:::

::: {.definition title="Local Orientation"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Limit"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Linear Independence"}
A generating \( S \) for a module \( M \) is linearly independent if \( \sum r_{i} s_{i} = 0_M \implies \forall i,~r_{i} = 0 \) where \( s_{i}\in S, r_{i} \in R \).
:::

::: {.definition title="Local homology"}
\( H_{n}(X, X-A; {\mathbb{Z}}) \) is the local homology at \( A \), also denoted \( H_{n}(X \mathrel{\Big|}A) \)
:::

::: {.definition title="Local orientation of a manifold"}
At a point \( x\in M^n \), a choice of a generator \( \mu_{x} \) of \( H_{n}(M, M - \left\{{x}\right\}) = {\mathbb{Z}} \).
:::

::: {.definition title="Long exact sequence"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Manifold"}
An \( n{\hbox{-}} \)manifold is a Hausdorff space in which each neighborhood has an open neighborhood homeomorphic to \( {\mathbb{R}}^n \).
:::

::: {.definition title="Manifold with boundary"}
A manifold in which open neighborhoods may be isomorphic to either \( {\mathbb{R}}^n \) or a half-space \( \left\{{\mathbf{x} \in {\mathbb{R}}^n \mathrel{\Big|}x_{i} > 0}\right\} \).
:::

::: {.definition title="Mayer-Vietoris Sequence"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Monodromy"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="N-cell"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="N-connected"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Normal covering space (a.k.a. 'regular')"}
A covering space is **normal** if and only if for every \( x\in X \) and every pair of lifts \( \tilde x_1, \tilde x_2 \), there is a deck transformation \( f \) such that \( f(\tilde x_1) = \tilde x_2 \).
:::

::: {.definition title="Nullhomotopic"}
A map \( X\xrightarrow{f} Y \) is *nullhomotopic* if it is homotopic to a constant map \( X \xrightarrow{g} \left\{{y_{0}}\right\} \); that is, there exists a homotopy
\[  
F: X\times I &\to Y \\
 {\left.{{F}} \right|_{{X\times\left\{{0}\right\}}} }  &= f \quad F(x, 0) = f(x) \\
 {\left.{{F}} \right|_{{X\times\left\{{1}\right\}}} }  &= g  \quad F(x, 1) = g(x) = y_{0}\\
.\]

Alt:

If \( f \) is homotopic to a constant map, say \( f: x \mapsto y_0 \) for some fixed \( y_0 \in Y \), then \( f \) is said to be *nullhomotopic*. In other words, if \( f:X\to Y \) is nullhomotopic, then there exists a homotopy \( H: X\times I \to Y \) such that \( H(x, 0) = f(x) \) and \( H(x, 1) = y_0 \).

Note that constant maps (or anything homotopic) induce zero homomorphisms.
:::

::: {.definition title="Orbit space"}
For a group action \( G\curvearrowright X \), the **orbit space** \( X/G \) is defined as \( X/\sim \) where \( \forall x,y\in X, x\sim y \iff \exists g\in G \mathrel{\Big|}g.x = y \).
:::

::: {.definition title="Orientable manifold"}
A manifold for which an orientation exists, see "Orientation of a Manifold".
:::

::: {.definition title="Orientation cover"}
For any manifold \( M \), a two sheeted orientable covering space \( \tilde M_{o} \). \( M \) is orientable iff \( \tilde M \) is disconnected. Constructed as
\[
\tilde M = \coprod_{x\in M}\left\{{\mu_{x} \mathrel{\Big|}\mu_{x}~ \text{is a local orientation}}\right\}
.\]
:::

::: {.definition title="Orientation of a manifold"}
A family of \( \left\{{\mu_{x}}\right\}_{x\in M} \) with local consistency: if \( x,y \in U \) then \( \mu_{x}, \mu_{y} \) are related via a propagation.

Formally, a function
\[M^n \to \coprod_{x\in M} H(X \mathrel{\Big|}\left\{{x}\right\})\\ x \mapsto \mu_{x}\]
such that \( \forall x \exists N_{x} \) in which \( \forall y\in N_{x} \), the preimage of each \( \mu_{y} \) under the map \( H_{n}(M\mathrel{\Big|}N_{x}) \twoheadrightarrow H_{n}(M\mathrel{\Big|}y) \) is a single generator \( \mu_{N_{x}} \).

TFAE:

-   \( M \) is orientable.
-   The map \( W: (M, x) \to {\mathbb{Z}}_{2} \) is trivial.
-   \( \tilde M_{o} = M \coprod {\mathbb{Z}}_{2} \) (two sheets).
-   \( \tilde M_{o} \) is disconnected
-   The projection \( \tilde M_{o} \to M \) admits a section.
:::

::: {.definition title="Oriented manifold"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Path"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Path Lifting Property"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Perfect Pairing"}
A pairing alone is an \( R{\hbox{-}} \)bilinear module map, or equivalently a map out of a tensor product since \( p: M\otimes_{R} N \to L \) can be partially applied to yield \( \phi: M \to L^N = \hom_{R}(N, L) \). A pairing is **perfect** when \( \phi \) is an isomorphism.
:::

::: {.definition title="Poincaré Duality"}
For a closed, orientable \( n{\hbox{-}} \)manifold, following map \( [M] \frown {-} \) is an isomorphism:
\[ D: H^k(M; R) \to H_{n-k}(M; R) \\ D(\alpha) = [M] \frown \alpha\]
:::

::: {.definition title="Projective Resolution"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Properly Discontinuous"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Pullback"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Pushout"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Quasi-isomorphism"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="R-orientability"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Relative boundaries"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Relative cycles"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Relative homotopy groups"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Semilocally Simply Connected"}
A space \( X \) is **semilocally simply connected** if every \( x\in X \) has a neighborhood \( U \) such that \( U\hookrightarrow X \) induces the trivial map \( \pi_1(U;x) \to \pi_1(X, x) \).
:::

::: {.definition title="Short exact sequence"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Simplicial Complex"}
Given a simplex \( \sigma = [v_1 \cdots v_n] \), define the **face map**
\[
{\partial}_i:\Delta^n &\to \Delta^{n-1} \\ 
\sigma &\mapsto  [v_1 \cdots \widehat{v}_i \cdots v_n]
\]

A **simplicial complex** is a set \( K \) satisfying

1.  \( \sigma \in K \implies {\partial}_i\sigma \in K \).

2.  \( \sigma,\tau\in K \implies \sigma\cap\tau = \emptyset,~ {\partial}_i\sigma,~\text{or}~{\partial}_i\tau \).

This amounts to saying that any collection of \( (n-1) \)-simplices uniquely determines an \( n \)-simplex (or its lack thereof), or that that map \( \Delta^k \to X \) is a continuous injection from the standard simplex in \( {\mathbb{R}}^n \).

3.  \( {\left\lvert {K\cap B_\varepsilon(\sigma)} \right\rvert} < \infty \) for every \( \sigma\in K \), identifying \( \sigma \subseteq {\mathbb{R}}^n \).
:::

::: {.definition title="Simplicial Map"}
For a map
\[K\xrightarrow{f} L\]
between simplicial complexes, \( f \) is a simplicial map if for any set of vertices \( \left\{{v_{i}}\right\} \) spanning a simplex in \( K \), the set \( \left\{{f(v_{i})}\right\} \) are the vertices of a simplex in \( L \).
:::

::: {.definition title="Simply Connected"}
A space \( X \) is **simply connected** if and only if \( X \) is path-connected and every loop \( \gamma : S^1 \xrightarrow{} X \) can be contracted to a point.

Equivalently, there exists a lift \( \widehat{\gamma }: D^2 \xrightarrow{} X \) such that \( { \left.{{\widehat{\gamma}}} \right|_{{{{\partial}}D^2}} } = \gamma \).

Equivalently, for any two paths \( p_1, p_2: I \xrightarrow{} X \) such that \( p_1(0) = p_2(0) \) and \( p_1(1) = p_2(1) \), there exists a homotopy \( F: I^2 \xrightarrow{} X \) such that \( { \left.{{F}} \right|_{{0}} } = p_1,\, { \left.{{F}} \right|_{{0}} } = p_2 \).

Equivalently, \( \pi _1 X = 1 \) is trivial.
:::

::: {.definition title="Singular Chain"}
\[x \in C_{n}(x) \implies X = \sum_{i} n_{i} \sigma_{i} = \sum_{i} n_{i} (\Delta^n \xrightarrow{\sigma_{i}} X)
.\]
:::

::: {.definition title="Singular Cochain"}
\[x \in C^n(x) \implies X = \sum_{i} n_{i} \psi_{i} = \sum_{i} n_{i} (\sigma_{i} \xrightarrow{\psi_{i}} X)
.\]
:::

::: {.definition title="Singular Homology"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Tor Group"}
For an \( R{\hbox{-}} \)module
\[
\operatorname{Tor}_{R}^n({-}, B) = L_{n}({-}\otimes_{R} B)
,\]
where \( L_{n} \) denotes the \( n \)th left derived functor.
:::

::: {.definition title="Universal Cover"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Weak Homotopy Equivalence"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Weak Topology"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Wedge Product"}
:::

```{=tex}
\todo[inline]{Definitions}
```
## Homotopy

::: {.definition title="Cone"}
For a space \( X \), defined as
\[  
CX = \frac{X\times I} {X \times\left\{{0}\right\}}
.\]
Example: The cone on the circle \( CS^1 \)

```{=html}
<!--![](https://upload.wikimedia.org/wikipedia/commons/thumb/8/8c/Cone.svg/250px-Cone.svg.png)-->
```
Note that the cone embeds \( X \) in a contractible space \( CX \).
:::

::: {.definition title="Suspension"}
Compact represented as \( \Sigma X = CX \coprod_{\operatorname{id}_{X}} CX \), two cones on \( X \) glued along \( X \). Explicitly given by

\[\Sigma X = \frac{X\times I}{(X\times\left\{{0}\right\}) \cup(X\times\left\{{1}\right\}) \cup(\left\{{x_{0}}\right\} \times I)}
.\]
:::

::: {.definition title="Smash Product"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Moore Space"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Mapping Cone"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Mapping Cylinder"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Mapping Path Space"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Loop Space"}
:::

```{=tex}
\todo[inline]{Definitions}
```
::: {.definition title="Eilenberg-MacLane Space"}
:::

```{=tex}
\todo[inline]{Definitions}
```
# Examples

## Point-Set

### Common Spaces and Operations

::: {.example title="Nice spaces"}
The following are some standard "nice" spaces:
\[
S^n, {\mathbb{D}}^n, T^n, {\mathbb{RP}}^n, {\mathbb{CP}}^n, \mathbb{M}, \mathbb{K}, \Sigma_{g}, {\mathbb{RP}}^\infty, {\mathbb{CP}}^\infty
.\]
:::

::: {.example title="A bank of counterexamples"}
The following are useful spaces to keep in mind to furnish counterexamples:

-   Finite discrete sets with the discrete topology.
-   Subspaces of \( {\mathbb{R}} \): \( (a, b), (a, b], (a, \infty) \), etc.
    -   Sets given by real sequences, such as \( \left\{{0}\right\} \cup\left\{{{1 \over n}{~\mathrel{\Big|}~}n\in {\mathbb{Z}}^{\geq 1}}\right\} \)
-   \( {\mathbb{Q}} \)
-   The topologist's sine curve
-   One-point compactifications
-   \( {\mathbb{R}}^\omega \) for \( \omega \) the least uncountable ordinal (?)
-   The Hawaiian earring
-   The Cantor set

Examples of some more exotic spaces that show up less frequently:

-   \( {\operatorname{HP}}^n \), quaternionic projective space
-   The Dunce Cap
-   The Alexander Horned sphere
:::

```{=tex}
\todo[inline]{Break these into separate examples and explain properties.}
```
::: {.example title="Non-Hausdorff spaces"}
The following spaces are non-Hausdorff:

-   The cofinite topology on any infinite set.
-   \( {\mathbb{R}}/{\mathbb{Q}} \)
-   The line with two origins.
-   Any variety \( V(J) \subseteq {\mathbb{A}}^n_{/k} \) for \( k \) a field and \( J{~\trianglelefteq~}k[x_1, \cdots, x_{n}] \).
:::

::: {.example title="Constructed spaces"}
The following are some examples of ways to construct specific spaces for examples or counterexamples:

-   Knot complements in \( S^3 \)

-   Covering spaces (hyperbolic geometry)

-   Lens spaces

-   Matrix groups

-   Prism spaces

-   Pair of pants

-   Seifert surfaces

-   Surgery

-   Simplicial Complexes

    -   Nice minimal example:

![](figures/image_2020-05-22-18-58-03.png)
:::

::: {.fact title="Operations"}
Some common operations that combine spaces:\

-   Cartesian product \( A\times B \)
-   Wedge product \( A \vee B \)
-   Connect Sum \( A \# B \)
-   Quotienting \( A/B \)
-   Puncturing \( A\setminus \left\{{a_{i}}\right\} \)
-   Smash product
-   Join
-   Cones
-   Suspension
-   Loop space
-   Identifying a finite number of points
:::

### Alternative Topologies

::: {.example title="Nonstandard topologies"}
The following are some nice examples of topologies to put on familiar spaces to produce counterexamples:

-   Discrete
-   Cofinite
-   Discrete and Indiscrete
-   Uniform
:::

::: {.example title="The cofinite topology"}
The cofinite topology on any space \( X \) is always

-   Non-Hausdorff
-   Compact
:::

::: {.proposition title="Topology is discrete if and only if points are open"}
A topology \( (X, \tau) \) is the discrete topology iff points \( x\in X \) are open.
:::

::: {.proof title="?"}
If \( \left\{{x}\right\}_i \) is open for each \( x_i \in X \), then

-   Any set \( U \) can be written as \( U = \cup_{i\in I} x_I \) (for some \( I \) depending on \( U \)), and
-   Unions of open sets are open.

Thus \( U \) is open.
:::

::: {.example title="The discrete topology"}
Some facts about the discrete topology:

-   Definition: every subset is open.
-   Always Hausdorff
-   Compact iff finite
-   Totally disconnected
-   If \( X \) is discrete, every map \( f:X\to Y \) for any \( Y \) is continuous (obvious!)
:::

::: {.example title="The indiscrete topology"}
Some facts about the indiscrete topology:

-   Definition: the only open sets are \( \emptyset, X \)
-   Never Hausdorff
-   If \( Y \) is indiscrete, every map \( f:X\to Y \) is continuous (obvious!)
-   Always compact
:::

### Connectedness

  Space                     Connected          Locally Connected
  ------------------------- ------------------ -------------------
  \( {\mathbb{R}} \)        \( \checkmark \)   \( \checkmark \)
  \( [0, 1] \cup[2, 3] \)                      \( \checkmark \)
  Sine Curve                \( \checkmark \)   
  \( {\mathbb{Q}} \)                           

# "Analysis"-esque Results in Topology

::: {.proposition title="The rationals are neither open nor closed"}
\( {\mathbb{Q}}\subset {\mathbb{R}} \) is not open and not closed.

\

This follows because every neighborhood of \( q\in {\mathbb{Q}} \) contains an irrational and every neighborhood of \( q' \in {\mathbb{R}}\setminus{\mathbb{Q}} \) contains a rational.
:::

# Theorems

::: {.proposition title="The continuous image of a..."}
The following properties are "pushed forward" through continuous maps, in the sense that if property \( P \) holds for \( X \) and \( f:X\to Y \), then \( f(X) \) also satisfies \( P \):

-   Compactness
-   Separability
-   If \( f \) is surjective:
    -   Connectedness
    -   Density

The following are **not preserved**:

-   Openness
-   Closedness

> [See more here.](https://people.clas.ufl.edu/groisser/files/cont_img_preimg.pdf)
:::

## Metric Spaces and Analysis

::: {.theorem title="Cantor's Intersection Theorem"}
A bounded collection of nested closed sets \( C_1 \supset C_2 \supset \cdots \) in a metric space \( X \) is nonempty \( \iff X \) is complete.
:::

::: {.theorem title="Cantor's Nested Intervals Theorem"}
If \( \left\{{[a_n, b_n] {~\mathrel{\Big|}~}n\in {\mathbb{Z}}^{\geq 0}}\right\} \) is a nested sequence of compact intervals in a topological space \( X \), then their intersection is nonempty.

If \( X \) is a complete metric space and the diameters \( {\operatorname{diam}}([a_n, b_n]) \overset{n\to\infty}\longrightarrow 0 \), then their intersection contains exactly one point.
:::

::: {.proposition title="Continuous on compact $\\implies$ uniformly continuous"}
A continuous function on a compact set is uniformly continuous.
:::

::: {.proof title="?"}
Take \( \left\{{B_{\varepsilon\over 2}(y) {~\mathrel{\Big|}~}y\in Y}\right\}\rightrightarrows Y \), pull back to an open cover of \( X \), has Lebesgue number \( \delta_L > 0 \), then \( x' \in B_{\delta_L}(x) \implies f(x), f(x') \in B_{\varepsilon\over 2}(y) \) for some \( y \).
:::

::: {.corollary title="Lipschitz implies uniformly continuous"}
Lipschitz continuity implies uniform continuity (take \( \delta = \varepsilon/C \))
:::

::: {.remark}
Counterexample to the converse: \( f(x) = \sqrt x \) on \( [0, 1] \) has unbounded derivative.
:::

::: {.theorem title="Extreme Value Theorem"}
For \( f:X \to Y \) continuous with \( X \) compact and \( Y \) ordered in the order topology, there exist points \( c, d\in X \) such that \( f(x) \in [f(c), f(d)] \) for every \( x \).
:::

::: {.theorem title="Sequentially compact if and only if complete and totally bounded"}
A metric space \( X \) is sequentially compact iff it is complete and totally bounded.
:::

::: {.theorem title="Totally bounded if and only if Cauchy subsequences exist"}
A metric space is totally bounded iff every sequence has a Cauchy subsequence.
:::

::: {.theorem title="Compact if and only if complete and totally bounded"}
A metric space is compact iff it is complete and totally bounded.
:::

::: {.theorem title="Baire"}
If \( X \) is a complete metric space, \( X \) is a **Baire space**: the intersection of countably many dense open sets in \( X \) is again dense in \( X \).
:::

## Compactness

::: {.theorem title="Closed if and only if compact in Hausdorff spaces"}
\( U\subset X \) a Hausdorff spaces is closed \( \iff \) it is compact.
:::

::: {.theorem title="Closed subset of compact is compact"}
A closed subset \( A \) of a compact set \( B \) is compact.
:::

::: {.proof title="?"}
```{=tex}
\envlist
```
-   Let \( \left\{{A_i}\right\} \rightrightarrows A \) be a covering of \( A \) by sets open in \( A \).
-   Each \( A_i = B_i \cap A \) for some \( B_i \) open in \( B \) (definition of subspace topology)
-   Define \( V = \left\{{B_i}\right\} \), then \( V \rightrightarrows A \) is an open cover.
-   Since \( A \) is closed, \( W\coloneqq B\setminus A \) is open
-   Then \( V\cup W \) is an open cover of \( B \), and has a finite subcover \( \left\{{V_i}\right\} \)
-   Then \( \left\{{V_i \cap A}\right\} \) is a finite open cover of \( A \).
:::

::: {.theorem title="Continuous image of compact is compact"}
The continuous image of a compact set is compact.
:::

::: {.proof title="?"}
Let \( f:X\to f(X) \) be continuous. Take an open covering \( \mathcal{U} \rightrightarrows f(X) \), then \( f^{-1}(\mathcal{U}) \rightrightarrows X \), which is cover by opens since \( f \) is continuous. Take a finite subcover by compactness of \( X \), then they push forward to a finite subcover of \( f(X) \).
:::

::: {.theorem title="Closed in Hausdorff $\\implies$ compact"}
A closed subset of a Hausdorff space is compact.
:::

## Separability

::: {.proposition title="Properties preserved under retracts"}
A retract of a Hausdorff/connected/compact space is closed/connected/compact respectively.
:::

::: {.proposition title="?"}
Points are closed in \( T_1 \) spaces.
:::

## Maps and Homeomorphism

::: {.theorem title="Continuous bijections from compact to Hausdorff are homeomorphisms"}
A continuous bijection \( f: X\to Y \) with \( X \) is compact and \( Y \) is Hausdorff is a homeomorphism.
:::

::: {.proof title="?"}
Show that \( f^{-1} \) is continuous by showing \( f \) is a closed map. If \( A\subseteq X \) is closed in a compact space, \( A \) is compact. The continuous image of a compact set is compact, so \( f(A) \) is compact. A compact set in a Hausdorff space is closed, so \( f(A) \) is closed in \( Y \).
:::

::: {.remark title="On retractions"}
Every space has at least one retraction - for example, the constant map \( r:X \to\left\{{x_0}\right\} \) for any \( x\_0 \in X \).
:::

::: {.theorem title="When open maps are homeomorphisms"}
A continuous bijective open map is a homeomorphism.
:::

::: {.theorem title="Characterizations of continuous maps, Munkres 18.1"}
For \( f:X\to Y \), TFAE:

-   \( f \) is continuous
-   \( A\subset X \implies f({ \operatorname{cl}} _X(A)) \subset { \operatorname{cl}} _X(f(A)) \)
-   \( B \) closed in \( Y \implies f^{-1}(B) \) closed in \( X \).
-   For each \( x\in X \) and each neighborhood \( V \ni f(x) \), there is a neighborhood \( U\ni x \) such that \( f(U) \subset V \).
:::

::: {.proof title="?"}
See Munkres page 104.
:::

::: {.theorem title="Maps from compact to Hausdorff spaces, Lee A.52"}
If \( f:X\to Y \) is continuous where \( X \) is compact and \( Y \) is Hausdorff, then

-   \( f \) is a closed map.
-   If \( f \) is surjective, \( f \) is a quotient map.
-   If \( f \) is injective, \( f \) is a topological embedding.
-   If \( f \) is bijective, it is a homeomorphism.
:::

## The Tube Lemma

::: {.theorem title="The Tube Lemma"}
Let \( X, Y \) be spaces with \( Y \) compact, and let \( x_0\in X \). Let \( N\subseteq X\times Y \) be an open set containing the slice \( x_0 \times Y \), then there is a neighborhood \( W\ni x \) in \( X \) such that \( N \supset W\times Y \):

![image_2021-05-21-00-28-13](figures/image_2021-05-21-00-28-13.png)
:::

::: {.remark}
Compactness in one factor is a necessary condition. For a counterexample, \( {\mathbb{R}}^2 \) and let \( N \) be the set contained between a Gaussian and its reflection across the \( x{\hbox{-}} \)axis. Then no tube about \( y=0 \) is entirely contained within \( N \):

![image_2021-05-21-01-39-26](figures/image_2021-05-21-01-39-26.png)
:::

::: {.proof title="Sketch"}
```{=tex}
\envlist
```
-   For each \( y\in Y \) choose neighborhoods \( A_y, B_y \subseteq Y \) such that
    \[
    (x, y) \in A_y \times B_y \subseteq U
    .\]
-   By compactness of \( Y \), reduce this to finitely many \( B_y \rightrightarrows Y \) so \( Y = \displaystyle\bigcup_{j=1}^n B_{y_j} \)
-   Set \( O\coloneqq\cap_{j=1}^n B_{y_j} \); this works.
:::

::: {.proof title="Detailed proof of the Tube Lemma"}
```{=tex}
\todo[inline]{Check this proof!}
```
-   Let \( \left\{{U_j\times V_j {~\mathrel{\Big|}~}j\in J}\right\} \rightrightarrows X\times Y \).
-   Fix a point \( x_0\in X \), then \( \left\{{x_0}\right\}\times Y \subset N \) for some open set \( N \).
-   By the tube lemma, there is a \( U^x \subset X \) such that the tube \( U^x \times Y \subset N \).
-   Since \( \left\{{x_0}\right\}\times Y \cong Y \) which is compact, there is a finite subcover \( \left\{{U_j \times V_j {~\mathrel{\Big|}~}j\leq n}\right\} \rightrightarrows\left\{{x_0}\right\}\times Y \).
-   "Integrate the \( X \)": write
    \[W = \cap_{j=1}^n U_j,\]
    then \( x_0 \in W \) and \( W \) is a finite intersection of open sets and thus open.
-   Claim: \( \left\{{U_j \times V_j {~\mathrel{\Big|}~}j\leq n}\right\}\rightrightarrows W\times Y \)
    -   Let \( (x, y) \in W\times Y \); want to show \( (x, y)\in U_j \times V_j \) for some \( j\leq n \).
    -   Then \( (x_0, y) \in \left\{{x_0}\right\}\times Y \) is on the same horizontal line
    -   \( (x_0, y)\in U_j \times V_j \) for some \( j \) by construction
    -   So \( y\in V_j \) for this \( j \)
    -   Since \( x\in W \), \( x\in U_j \) for *every* \( j \), thus \( x\in U_j \).
    -   So \( (x, y) \in U_j \times V_j \)
:::

# Summary of Standard Topics

-   Algebraic topology topics:
    -   Classification of compact surfaces
    -   Euler characteristic
    -   Connect sum
    -   Homology and cohomology groups
    -   Fundamental group
    -   Singular/cellular/simplicial homology
    -   Mayer-Vietoris long exact sequences for homology and cohomology
    -   Diagram chasing
    -   Degree of maps from \( S^n \to S^n \)
    -   Orientability, compactness
    -   Top-level homology and cohomology
    -   Reduced homology and cohomology
    -   Relative homology
    -   Homotopy and homotopy invariance
    -   Deformation retract
    -   Retract
    -   Excision
    -   Kunneth formula
    -   Factoring maps
    -   Fundamental theorem of algebra
-   Algebraic topology theorems:
    -   Brouwer fixed point theorem
    -   Poincaré lemma
    -   Poincaré duality
    -   de Rham theorem
    -   Seifert-van Kampen theorem
-   Covering space theory topics:
    -   Covering maps
    -   Free actions
    -   Properly discontinuous action
    -   Universal cover
    -   Correspondence between covering spaces and subgroups of the fundamental group of the base.
    -   Lifting paths
    -   Homotopy lifting property
    -   Deck transformations
    -   The action of the fundamental group
    -   Normal/regular cover

# Examples: Algebraic Topology

## Standard Spaces and Modifications

::: {.example title="Spheres and Balls"}
\[
{\mathbb{D}}^n = \mathbb{B}^n &\coloneqq\left\{{ \mathbf{x} \in {\mathbb{R}}^{n} {~\mathrel{\Big|}~}{\left\lVert {\mathbf{x}} \right\rVert} \leq 1}\right\}
{\mathbb{S}}^n &\coloneqq\left\{{ \mathbf{x} \in {\mathbb{R}}^{n+1} {~\mathrel{\Big|}~}{\left\lVert {\mathbf{x}} \right\rVert} = 1}\right\} = {{\partial}}{\mathbb{D}}^n \\
.\]

> Note: I'll immediately drop the blackboard notation, this is just to emphasize that they're "canonical" objects.

The sphere can be constructed in several equivalent ways:

-   \( S^n \cong D^n / {{\partial}}D^n \): collapsing the boundary of a disc is homeomorphic to a sphere.
-   \( S^n \cong D^n \displaystyle\coprod_{{{\partial}}D^n} D^n \): gluing two discs along their boundary.

Note the subtle differences in dimension: \( S^n \) is a manifold of dimension \( n \) embedded in a space of dimension \( n+1 \).

```{=html}
<!--\begin{tikzpicture}-->
```
```{=html}
<!--\node (node_one) at (0,0) {-->
```
```{=html}
<!--\includegraphics{/home/zack/SparkleShare/github.com/Qual-Review-and-Solutions/Topology/Review\ Doc/sections/figures/spheres_and_balls}-->
```
```{=html}
<!--};-->
```
```{=html}
<!--\node at (-5.6, 1) {$\DD^1$};-->
```
```{=html}
<!--\node at (-0.2, 1) {$\DD^2$};-->
```
```{=html}
<!--\node at (5.9, 1) {$\DD^3$};-->
```
```{=html}
<!--\node at (-5.6, -5.5) {$\SS^0$};-->
```
```{=html}
<!--\node at (-0.2, -5.5) {$\SS^1$};-->
```
```{=html}
<!--\node at (5.9, -5.5) {$\SS^2$};-->
```
```{=html}
<!--\end{tikzpicture}-->
```
![Low Dimensional Discs/Balls vs Spheres](figures/image_2021-01-10-23-20-27.png)
:::

::: {.example title="Real Projective Space"}
Constructed in one of several equivalent ways:

-   \( S^n/\sim \) where \( \mathbf{x} \sim -\mathbf{x} \), i.e. antipodal points are identified.
-   The space of lines in \( {\mathbb{R}}^{n+1} \).

One can also define \( {\mathbb{RP}}^ \infty \coloneqq\varinjlim_{n} {\mathbb{RP}}^n \). Fits into a fiber bundle of the form

```{=tex}
\begin{tikzcd}
S^0 
  \ar[r] 
& 
S^n
  \ar[d] 
\\
& 
{\mathbb{RP}}^n 
\end{tikzcd}
```
:::

::: {.example title="Complex Projective Space"}
Defined in a similar ways,

-   Taking the unit sphere in \( {\mathbb{C}}^n \) and identifying \( \mathbf{z} \sim -\mathbf{z} \).
-   The space of lines in \( {\mathbb{C}}^{n+1} \)

Can similarly define \( {\mathbb{CP}}^ \infty \coloneqq\varinjlim_n {\mathbb{CP}}^n \). Fits into a fiber bundle of the form

```{=tex}
\begin{tikzcd}
S^1 
  \ar[r] 
& 
S^{2n+1}
  \ar[d] 
\\
& 
{\mathbb{CP}}^n 
\end{tikzcd}
```
:::

::: {.example title="Torii"}
The \( n{\hbox{-}} \)torus, defined as
\[
T^n \coloneqq\prod_{j=1}^n S^1 = S^1 \times S^1 \times \cdots
.\]
:::

::: {.example title="Grassmannians"}
The real Grassmannian, \( {\operatorname{Gr}}(n, k)_{/{\mathbb{R}}} \), i.e. the set of \( k \) dimensional subspaces of \( {\mathbb{R}}^n \). One can similar define \( {\operatorname{Gr}}(n, k)_{{\mathbb{C}}} \) for complex subspaces. Note that \( {\mathbb{RP}}^n = {\operatorname{Gr}}(n, 1)_{{\mathbb{R}}} \) and \( {\mathbb{CP}}^n = {\operatorname{Gr}}(n, 1)_{/{\mathbb{C}}} \).
:::

::: {.example title="Stiefel Manifolds"}
The Stiefel manifold \( V_{n}(k)_{{\mathbb{R}}} \), the space of orthonormal \( k{\hbox{-}} \)frames in \( {\mathbb{R}}^n \)?
:::

::: {.example title="Lie Groups"}
Lie Groups:

-   The general linear group, \( \operatorname{GL}_{n}({\mathbb{R}}) \)
    -   The special linear group \( SL_{n}({\mathbb{R}}) \)
-   The orthogonal group, \( O_{n}({\mathbb{R}}) \)
    -   The special orthogonal group, \( SO_{n}({\mathbb{R}}) \)
-   The real unitary group, \( U_{n}({\mathbb{C}}) \)
    -   The special unitary group, \( SU_{n}({\mathbb{R}}) \)
-   The symplectic group \( Sp(2n) \)
:::

::: {.example title="More random geometric examples"}
Some other spaces that show up, but don't usually have great algebraic topological properties:

-   Affine \( n \)-space over a field \( {\mathbb{A}}^n(k) = k^n \rtimes GL_{n}(k) \)
-   The projective space \( {\mathbb{P}}^n(k) \)
-   The projective linear group over a ring \( R \), \( PGL_{n}(R) \)
-   The projective special linear group over a ring \( R \), \( PSL_{n}(R) \)
-   The modular groups \( PSL_{n}({\mathbb{Z}}) \)
    -   Specifically \( PSL_{2}({\mathbb{Z}}) \)
:::

::: {.example title="Eilenberg-MacLane Spaces"}
\( K(G, n) \) is an Eilenberg-MacLane space, the homotopy-unique space satisfying
\[
\pi_{k}(K(G, n)) = 
\begin{cases}
G & k=n, \\ 
0 & \text{else}
\end{cases}
\]

Some known examples:

-   \( K({\mathbb{Z}}, 1) = S^1 \)
-   \( K({\mathbb{Z}}, 2) = {\mathbb{CP}}^\infty \)
-   \( K({\mathbb{Z}}/2{\mathbb{Z}}, 1) = {\mathbb{RP}}^\infty \)
:::

::: {.example title="Moore Spaces"}
\( M(G, n) \) is a Moore space, the homotopy-unique space satisfying
\[
H_{k}(M(G, n); G) = 
\begin{cases}
G & k=n, \\ 
0 & k\neq n.
\end{cases}
\]

Some known examples:

-   \( M({\mathbb{Z}}, n) = S^n \)
-   \( M({\mathbb{Z}}/2{\mathbb{Z}}, 1) = {\mathbb{RP}}^2 \)
-   \( M({\mathbb{Z}}/p{\mathbb{Z}}, n) \) is made by attaching \( e^{n+1} \) to \( S^n \) via a degree \( p \) map.
:::

::: {.fact title="about standard low-dimensional spaces"}
```{=tex}
\envlist
```
-   \( {\mathcal{M}}\simeq S^1 \) where \( {\mathcal{M}} \) is the Mobius band.
-   \( {\mathbb{CP}}^n = {\mathbb{C}}^n \coprod {\mathbb{CP}}^{n-1} = \coprod_{i=0}^n {\mathbb{C}}^i \)
-   \( {\mathbb{CP}}^n = S^{2n+1} / S^n \)
-   \( S^n / S^k \simeq S^n \vee \Sigma S^k \).
:::

::: {.remark title="Accidental isomorphisms"}
In low dimensions, there are some "accidental" homeomorphisms:

-   \( {\mathbb{RP}}^1 \cong S^1 \)
-   \( {\mathbb{CP}}^1 \cong S^2 \)
-   \( {\operatorname{SO}}(3) \cong {\mathbb{RP}}^2 \)?
:::

## Modifying Known Spaces

::: {.example title="Deleting points"}
Write \( D(k, X) \) for the space \( X \) with \( k\in {\mathbb{N}} \) distinct points deleted, i.e. the punctured space \( X - \left\{{x_{1}, x_{2}, \ldots x_{k}}\right\} \) where each \( x_{i} \in X \).
:::

::: {.example title="Bouquets of Spheres"}
The "generalized uniform bouquet"? \( \mathcal{B}^n(m) = \bigvee_{i=1}^n S^m \). There's no standard name for this, but it's an interesting enough object to consider!
:::

::: {.example title="Other ways to modify a known space"}
Possible modifications to a space \( X \):

-   Remove a line segment
-   Remove an entire line/axis
-   Remove a hole
-   Quotient by a group action (e.g. antipodal map, or rotation)
-   Remove a knot
-   Take complement in ambient space
:::

# Low Dimensional Homology Examples

::: {.fact title="Table of low-dimensional homology"}
\[
\begin{array}{cccccccccc}
S^1   &=  &[&{\mathbb{Z}}, &{\mathbb{Z}},               &0,    &0,      &0,    &0\rightarrow & ]\\
{\mathcal{M}}&=  &[&{\mathbb{Z}}, &{\mathbb{Z}},               &0,    &0,      &0,    &0\rightarrow & ]\\
{\mathbb{RP}}^1 &=  &[&{\mathbb{Z}}, &{\mathbb{Z}},               &0,    &0,      &0,    &0\rightarrow & ]\\
{\mathbb{RP}}^2 &=  &[&{\mathbb{Z}}, &{\mathbb{Z}}_{2},             &0,    &0,      &0,    &0\rightarrow & ]\\
{\mathbb{RP}}^3 &=  &[&{\mathbb{Z}}, &{\mathbb{Z}}_{2},             &0,    &{\mathbb{Z}},    &0,    &0\rightarrow & ]\\
{\mathbb{RP}}^4 &=  &[&{\mathbb{Z}}, &{\mathbb{Z}}_{2},             &0,    &{\mathbb{Z}}_{2},  &0,    &0\rightarrow & ]\\
 S^2  &=  &[&{\mathbb{Z}}, &0,                 &{\mathbb{Z}},  &0,      &0,    &0\rightarrow & ]\\
{\mathbb{T}}^2 &=  &[&{\mathbb{Z}}, &{\mathbb{Z}}^2,             &{\mathbb{Z}},  &0,      &0,    &0\rightarrow & ]\\
{\mathbb{K}}&=  &[&{\mathbb{Z}}, &{\mathbb{Z}}\oplus {\mathbb{Z}}_{2},  &0,    &0,      &0,    &0\rightarrow & ]\\
{\mathbb{CP}}^1 &=  &[&{\mathbb{Z}}, &0,                 &{\mathbb{Z}},  &0,      &0,    &0\rightarrow & ]\\
{\mathbb{CP}}^2 &=  &[&{\mathbb{Z}}, &0,                 &{\mathbb{Z}},  &0,      &{\mathbb{Z}},  &0\rightarrow & ]\\
\end{array}
.\]
:::

# Table of Homotopy and Homology Structures

::: {.remark}
The following is a giant list of known homology/homotopy.

```{=tex}
\scriptsize
```
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  \( X \)                                \( \pi_*(X) \)                                           \( H_*(X) \)                                                                              CW Structure                                          \( H^*(X) \)
  -------------------------------------- -------------------------------------------------------- ----------------------------------------------------------------------------------------- ----------------------------------------------------- ------------------------------------------------------------------------------------------
  \( {\mathbb{R}}^1 \)                   \( 0 \)                                                  \( 0 \)                                                                                   \( {\mathbb{Z}}\cdot 1 + {\mathbb{Z}}\cdot x \)       0

  \( {\mathbb{R}}^n \)                   \( 0 \)                                                  \( 0 \)                                                                                   \( ({\mathbb{Z}}\cdot 1 + {\mathbb{Z}}\cdot x)^n \)   0

  \( D(k, {\mathbb{R}}^n) \)             \( \pi_*\bigvee^k S^1 \)                                 \( \bigoplus_{k} H_* M({\mathbb{Z}}, 1) \)                                                \( 1 + kx \)                                          ?

  \( B^n \)                              \( \pi_*({\mathbb{R}}^n) \)                              \( H_*({\mathbb{R}}^n) \)                                                                 \( 1 + x^n + x^{n+1} \)                               0

  \( S^n \)                              \( [0 \ldots , {\mathbb{Z}}, ? \ldots] \)                \( H_*M({\mathbb{Z}}, n) \)                                                               \( 1 + x^n \) or \( \sum_{i=0}^n 2x^i \)              \( {\mathbb{Z}}[{}_{n}x]/(x^2) \)

  \( D(k, S^n) \)                        \( \pi_*\bigvee^{k-1}S^1 \)                              \( \bigoplus_{k-1}H_*M({\mathbb{Z}}, 1) \)                                                \( 1 + (k-1)x^1 \)                                    ?

  \( T^2 \)                              \( \pi_*S^1 \times \pi_* S^1 \)                          \( (H_* M({\mathbb{Z}}, 1))^2 \times H_* M({\mathbb{Z}}, 2) \)                            \( 1 + 2x + x^2 \)                                    \( \Lambda({}_{1}x_{1}, {}_{1}x_{2}) \)

  \( T^n \)                              \( \prod^n \pi_* S^1 \)                                  \( \prod_{i=1}^n (H_* M({\mathbb{Z}}, i))^{n\choose i} \)                                 \( (1 + x)^n \)                                       \( \Lambda({}_{1}x_{1}, {}_{1}x_{2}, \ldots {}_{1}x_{n}) \)

  \( D(k, T^n) \)                        \( [0, 0, 0, 0, \ldots] \)?                              \( [0, 0, 0, 0, \ldots] \)?                                                               \( 1 + x \)                                           ?

  \( S^1 \vee S^1 \)                     \( \pi_*S^1 \ast \pi_* S^1 \)                            \( (H_*M({\mathbb{Z}}, 1))^2 \)                                                           \( 1 + 2x \)                                          ?

  \( \bigvee^n S^1 \)                    \( \ast^n \pi_* S^1 \)                                   \( \prod H_* M({\mathbb{Z}}, 1) \)                                                        \( 1 + x \)                                           ?

  \( {\mathbb{RP}}^1 \)                  \( \pi_* S^1 \)                                          \( H_* M({\mathbb{Z}}, 1) \)                                                              \( 1 + x \)                                           \( {}_{0}{\mathbb{Z}}\times {}_{1}{\mathbb{Z}} \)

  \( {\mathbb{RP}}^2 \)                  \( \pi_*K({\mathbb{Z}}/2{\mathbb{Z}}, 1)+ \pi_* S^2 \)   \( H_*M({\mathbb{Z}}/2{\mathbb{Z}}, 1) \)                                                 \( 1 + x + x^2 \)                                     \( {}_{0}{\mathbb{Z}}\times {}_{2}{\mathbb{Z}}/2{\mathbb{Z}} \)

  \( {\mathbb{RP}}^3 \)                  \( \pi_*K({\mathbb{Z}}/2{\mathbb{Z}}, 1)+ \pi_* S^3 \)   \( H_*M({\mathbb{Z}}/2{\mathbb{Z}}, 1) + H_*M({\mathbb{Z}}, 3) \)                         \( 1 + x + x^2 + x^3 \)                               \( {}_{0}{\mathbb{Z}}\times {}_{2}{\mathbb{Z}}/2{\mathbb{Z}}\times {}_{3}{\mathbb{Z}} \)

  \( {\mathbb{RP}}^4 \)                  \( \pi_*K({\mathbb{Z}}/2{\mathbb{Z}}, 1)+ \pi_* S^4 \)   \( H_*M({\mathbb{Z}}/2{\mathbb{Z}}, 1) + H_*M({\mathbb{Z}}/2{\mathbb{Z}}, 3) \)           \( 1 + x + x^2 + x^3 + x^4 \)                         \( {}_{0}{\mathbb{Z}}\times ({}_{2}{\mathbb{Z}}/2{\mathbb{Z}})^2 \)

  \( {\mathbb{RP}}^n, n \geq 4 \) even   \( \pi_*K({\mathbb{Z}}/2{\mathbb{Z}}, 1)+ \pi_*S^n \)    \( \prod_{\text{odd}~i < n} H_*M({\mathbb{Z}}/2{\mathbb{Z}}, i) \)                        \( \sum_{i=1}^n x^i \)                                \( {}_{0}{\mathbb{Z}}\times \prod_{i=1}^{n/2}{}_{2}{\mathbb{Z}}/2{\mathbb{Z}} \)

  \( {\mathbb{RP}}^n, n \geq 4 \) odd    \( \pi_*K({\mathbb{Z}}/2{\mathbb{Z}}, 1)+ \pi_*S^n \)    \( \prod_{\text{odd}~ i \leq n-2} H_*M({\mathbb{Z}}/2{\mathbb{Z}}, i) \times H_* S^n \)   \( \sum_{i=1}^n x^i \)                                \( H^*({\mathbb{RP}}^{n-1}) \times {}_{n}{\mathbb{Z}} \)

  \( {\mathbb{CP}}^1 \)                  \( \pi_*K({\mathbb{Z}}, 2) + \pi_* S^3 \)                \( H_* S^2 \)                                                                             \( x^0 + x^2 \)                                       \( {\mathbb{Z}}[{}_{2}x]/({}_2x^{2}) \)

  \( {\mathbb{CP}}^2 \)                  \( \pi_*K({\mathbb{Z}}, 2) + \pi_* S^5 \)                \( H_*S^2 \times H_* S^4 \)                                                               \( x^0 + x^2 + x^4 \)                                 \( {\mathbb{Z}}[{}_{2}x]/({}_2x^{3}) \)

  \( {\mathbb{CP}}^n, n \geq 2 \)        \( \pi_*K({\mathbb{Z}}, 2) + \pi_*S^{2n+1} \)            \( \prod_{i=1}^n H_* S^{2i} \)                                                            \( \sum_{i=1}^n x^{2i} \)                             \( {\mathbb{Z}}[{}_{2}x]/({}_2x^{n+1}) \)

  Mobius Band                            \( \pi_* S^1 \)                                          \( H_* S^1 \)                                                                             \( 1 + x \)                                           ?

  Klein Bottle                           \( K({\mathbb{Z}}\rtimes_{-1} {\mathbb{Z}}, 1) \)        \( H_*S^1 \times H_* {\mathbb{RP}}^\infty \)                                              \( 1 + 2x + x^2 \)                                    ?
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

```{=tex}
\normalsize
```
:::

::: {.fact title="used to fill out the above table"}
```{=tex}
\envlist
```
-   \( {\mathbb{R}}^n \) is a contractible space, and so \( [S^m, {\mathbb{R}}^n] = 0 \) for all \( n, m \) which makes its homotopy groups all zero.

-   \( D(k, {\mathbb{R}}^n) = {\mathbb{R}}^n - \left\{{x_{1} \ldots x_{k}}\right\} \simeq\bigvee_{i=1}^k S^1 \) by a deformation retract.

-   \( S^n \cong B^n / {\partial}B^n \) and employs an attaching map

\[
\phi: (D^n, {\partial}D^n) &\to S^n \\ 
(D^n, {\partial}D^n) &\mapsto (e^n, e^0)
.\]

-   \( B^n \simeq{\mathbb{R}}^n \) by normalizing vectors.

-   Use the inclusion \( S^n \hookrightarrow B^{n+1} \) as the attaching map.

-   \( {\mathbb{CP}}^1 \cong S^2 \).

-   \( {\mathbb{RP}}^1 \cong S^1 \).

-   Use \( \left[ \pi_{1}, \prod \right]= 0 \) and the universal cover \( {\mathbb{R}}^1 \twoheadrightarrow S^1 \) to yield the cover \( {\mathbb{R}}^n \twoheadrightarrow T^n \).

-   Take the universal double cover \( S^n \twoheadrightarrow^{\times 2} {\mathbb{RP}}^n \) to get equality in \( \pi_{i\geq 2} \).

-   Use \( {\mathbb{CP}}^n = S^{2n+1} / S^1 \)

-   Alternatively, the fundamental group is \( {\mathbb{Z}}\ast{\mathbb{Z}}/ bab^{-1}a \). Use the fact the \( \tilde K = {\mathbb{R}}^2 \).

-   \( M \simeq S^1 \) by deformation-retracting onto the center circle.

-   \( D(1, S^n) \cong {\mathbb{R}}^n \) and thus \( D(k, S^n) \cong D(k-1, {\mathbb{R}}^n) \cong \bigvee^{k-1} S^1 \)
:::

# Theorems: Algebraic Topology

## General Homotopies

::: {.fact title="Contracting Spaces in Products"}
\[
X\times{\mathbb{R}}^n \simeq X \times{\operatorname{pt}}\cong X
.\]
:::

::: {.fact title="$\\pi_0, H_0$ detect path components"}
The ranks of \( \pi_{0} \) and \( H_{0} \) are the number of path components.
:::

::: {.theorem title="Convex sets admit homotopies"}
Any two continuous functions into a convex set are homotopic.
:::

::: {.proof title="?"}
The linear homotopy. Supposing \( X \) is convex, for any two points \( x,y\in X \), the line \( tx + (1-t)y \) is contained in \( X \) for every \( t\in[0,1] \). So let \( f, g: Z \to X \) be any continuous functions into \( X \). Then define \( H: Z \times I \to X \) by \( H(z,t) = tf(z) + (1-t)g(z) \), the linear homotopy between \( f,g \). By convexity, the image is contained in \( X \) for every \( t,z \), so this is a homotopy between \( f,g \).
:::

## Fundamental Group

### Definition

::: {.definition title="The Fundamental Group"}
Given a pointed space \( (X,x_{0}) \), we define the fundamental group \( \pi_{1}(X) \) as follows:

-   Take the set
    \[
    L \coloneqq\left\{{\alpha: S^1\to X \mathrel{\Big|}\alpha(0) = \alpha(1) = x_{0}}\right\}
    .\]

-   Define an equivalence relation \( \alpha \sim \beta \) iff \( \alpha \simeq\beta \) in \( X \), so there exists a homotopy

\[
H: &S^1 \times I  \to X \\ 
&
\begin{cases}
H(s, 0) = \alpha(s)\\
H(s, 1) = \beta(s) ,
\end{cases}
\]
- Check that this relation is

-   Symmetric: Follows from considering \( H(s, 1-t) \).

-   Reflexive: Take \( H(s, t) = \alpha (s) \) for all \( t \).

-   Transitive: Follows from reparameterizing.

-   Define \( L/\sim \), which contains elements like \( [\alpha] \) and \( [\operatorname{id}_{x_{0}}] \), the equivalence classes of loops after quotienting by this relation.

-   Define a product structure: for \( [\alpha], [\beta] \in L/\sim \), define \( [\alpha][\beta] = [\alpha \cdot \beta] \), where we just need to define a product structure on actual loops. Do this by reparameterizing:
    \[
    (\alpha \cdot \beta )(s) \coloneqq
    \begin{cases}
    \alpha (2s) &  s \in [0, 1/2]
    \\
    \beta (2s-1) & 
    s \in [1/2, 1]
    .
    \end{cases}
    \]

-   Check that this map is:

    -   Continuous: by the pasting lemma and assumed continuity of \( f, g \).

    -   Well-defined: ?

-   Check that this is actually a group

    -   Identity element: The constant loop \( \operatorname{id}_{x_0}: I\to X \) where \( \operatorname{id}_{x_0}(t) = x_0 \) for all \( t \).

    -   Inverses: The reverse loop \( \mkern 1.5mu\overline{\mkern-1.5mu\alpha\mkern-1.5mu}\mkern 1.5mu(t) \coloneqq\alpha(1-t) \).

    -   Closure: Follows from the fact that start/end points match after composing loops, and reparameterizing.

    -   Associativity: Follows from reparameterizing.
:::

::: {.remark title="a summary"}
Elements of the fundamental group are *homotopy classes of loops*, and every continuous map between spaces induces a homomorphism on fundamental groups.
:::

### Conjugacy in \( \pi_{1} \): {#conjugacy-in-pi_1}

-   See Hatcher 1.19, p.28
-   See Hatcher's proof that \( \pi_{1} \) is a group
-   See change of basepoint map

### Calculating \( \pi_1 \) {#calculating-pi_1}

::: {.proposition title="Using universal covers"}
If \( \tilde X \to X \) the universal cover of \( X \) and \( G\curvearrowright\tilde X \) with \( \tilde X/G = X \) then \( \pi_1(X) = G \).
:::

::: {.proposition title="Killing homotopy"}
\( \pi_1 X \) for \( X \) a CW-complex only depends on the 2-skeleton \( X^{2} \), and in general \( \pi_k(X) \) only depends on the \( k+2 \)-skeleton. Thus attaching \( k+2 \) or higher cells does not change \( \pi_k \).
:::

::: {.theorem title="Seifert-van Kampen"}
Suppose \( X = U_{1} \cup U_{2} \) where \( U_1, U_2 \), and \( U \coloneqq U_{1} \cap U_{2} \neq \emptyset \) are open and path-connected [^4]

, and let \( x_0 \in U \).

Then the inclusion maps \( i_{1}: U_{1} \hookrightarrow X \) and \( i_{2}: U_{2} \hookrightarrow X \) induce the following group homomorphisms:
\[
i_{1}^*: \pi_{1}(U_{1}, x_0) \to\pi_{1}(X, x_0) \\
i_{2}^*: \pi_{1}(U_{2}, x_0) \to\pi_{1}(X, x_0)
\]

There is a natural isomorphism
\[
\pi_{1}(X) \cong \pi_{1} U \ast_{\pi_{1}(U \cap V)} \pi_{1} V
,\]

where the amalgamated product can be computed as follows: A **pushout** is the colimit of the following diagram

```{=tex}
\begin{tikzcd}
A \displaystyle\coprod_{Z} B   & A\ar[l] \\
B \ar[u]          & Z \ar[l, "\iota_{B}"] \ar[u, "\iota_{A}"]
\end{tikzcd}
```
![Example of a pushout of spaces](figures/image_2020-06-01-00-07-39.png)

For groups, the pushout is realized by the amalgamated free product: if
\[
\begin{cases}
\pi_1 U_1 = A = \left\langle{G_{A} {~\mathrel{\Big|}~}R_{A}}\right\rangle \\
\pi_1 U_2 = B = \left\langle{G_{B} {~\mathrel{\Big|}~}R_{B}}\right\rangle
\end{cases}
\implies 
A \ast_{Z} B \coloneqq\left\langle{ G_{A}, G_{B} {~\mathrel{\Big|}~}R_{A}, R_{B}, T}\right\rangle
\]
where \( T \) is a set of relations given by
\[
T = \left\{{\iota_{1}^*(z) \iota_{2}^*  (z) ^{-1}   {~\mathrel{\Big|}~}z\in \pi_1 (U_1 \cap U_2)}\right\}
,\]
where \( \iota_2^*(z) ^{-1} \) denotes the inverse group element. If we have presentations

\[ 
\pi_{1}(U, x_0) &=
\left\langle u_{1}, \cdots, u_{k} {~\mathrel{\Big|}~}\alpha_{1}, \cdots, \alpha_{l}\right\rangle \\ 
\pi_{1}(V, w) &=\left\langle v_{1}, \cdots, v_{m} {~\mathrel{\Big|}~}\beta_{1}, \cdots, \beta_{n}\right\rangle \\ 
\pi_{1}(U \cap V, x_0) 
&=\left\langle w_{1}, \cdots, w_{p} {~\mathrel{\Big|}~}\gamma_{1}, \cdots, \gamma_{q}\right\rangle 
\]

then
\[
\pi_{1}(X, w) 
&= \left\langle 
u_{1}, \cdots, u_{k}, v_{1}, \cdots, v_{m} 
\middle\vert
\begin{cases}
\alpha_{1}, 
\cdots, 
\alpha_{l}
\\
\beta_{1}, 
\cdots, 
\beta_{n}
\\
  I\left(w_{1}\right) J\left(w_{1}\right)^{-1}, 
  \cdots, 
  I\left(w_{p}\right) J\left(w_{p}\right)^{-1}
\\ 
\end{cases}
\right\rangle \\ \\
&= 
\frac{
  \pi_{1}(U_1) \ast \pi_{1}(U_2)
} {
  \left\langle{
    \left\{{\iota_1^*(w_{i}) \iota_2^*(w_{i})^{-1}{~\mathrel{\Big|}~}1\leq i \leq p}\right\}
  }\right\rangle
}
\]
:::

::: {.proof title="Sketch"}
```{=tex}
\envlist
```
-   Construct a map going backwards
-   Show it is surjective
    -   "There and back" paths
-   Show it is injective
    -   Divide \( I\times I \) into a grid
:::

::: {.example title="Pushing out with van Kampen"}
\( A = {\mathbb{Z}}/4{\mathbb{Z}}= \left\langle{x {~\mathrel{\Big|}~}x^4}\right\rangle, B = {\mathbb{Z}}/6{\mathbb{Z}}= \left\langle{y {~\mathrel{\Big|}~}x^6}\right\rangle, Z = {\mathbb{Z}}/2{\mathbb{Z}}= \left\langle{z {~\mathrel{\Big|}~}z^2}\right\rangle \). Then we can identify \( Z \) as a subgroup of \( A, B \) using \( \iota_{A}(z) = x^2 \) and \( \iota_{B}(z) = y^3 \). So
\[A\ast_{Z} B = \left\langle{x, y {~\mathrel{\Big|}~}x^4, y^6, x^2y^{-3}}\right\rangle\]
.
:::

::: {.proposition title="$\\pi_1$ of a wedge"}
\[
\pi_1(X \vee Y) = \pi_1(X) \ast \pi_1(Y)
.\]
:::

::: {.proof title="?"}
By van Kampen, this is equivalent to the amalgamated product over \( \pi_1(x_0) = 1 \), which is just a free product.
:::

### Facts

::: {.fact}
\( H_{1} \) is the abelianization of \( \pi_{1} \).
:::

::: {.proposition title="$\\pi_1$ of a product, Hatcher 1.12"}
If \( X, Y \) are path-connected, then
\[
\pi_1 (X \times Y) = \pi_1(X) \times\pi_2(Y)
.\]
:::

::: {.proof title="sketch"}
```{=tex}
\envlist
```
-   A loop in \( X \times Y \) is a continuous map \( \gamma : I \xrightarrow{} X \times Y \) given by \( \gamma (t) = (f(t), g(t) \) in components.
-   \( \gamma \) being continuous in the product topology is equivalent to \( f, g \) being continuous maps to \( X, Y \) respectively.
-   Similarly a homotopy \( F: I^2 \to X \times Y \) is equivalent to a pair of homotopies \( f_t, g_t \) of the corresponding loops.
-   So the map \( [ \gamma ] \mapsto ([f], [g]) \) is the desired bijection.
:::

::: {.proposition title="$\\pi_1$ detects simply-connectedness"}
\( \pi_{1}(X) = 1 \) iff \( X \) is simply connected.
:::

::: {.proof title="?"}
\( \Rightarrow \): Suppose \( X \) is simply connected. Then every loop in \( X \) contracts to a point, so if \( \alpha \) is a loop in \( X \), \( [\alpha] = [\operatorname{id}_{x_{0}}] \), the identity element of \( \pi_{1}(X) \). But then there is only one element in in this group.

\( \Leftarrow \): Suppose \( \pi_{1}(X) = 0 \). Then there is just one element in the fundamental group, the identity element, so if \( \alpha \) is a loop in \( X \) then \( [\alpha] = [\operatorname{id}_{x_{0}}] \). So there is a homotopy taking \( \alpha \) to the constant map, which is a contraction of \( \alpha \) to a point.
:::

:::{.fact "Unsorted facts"} `\envlist`{=tex}

-   For a graph \( G \), we always have \( \pi_{1}(G) \cong {\mathbb{Z}}^n \) where \( n = |E(G - T)| \), the complement of the set of edges in any maximal tree. Equivalently, \( n = 1-\chi(G) \). Moreover, \( X \simeq\bigvee^n S^1 \) in this case.

:::

## General Homotopy Theory

::: {.theorem title="Whitehead's Theorem"}
A map \( X \xrightarrow{f} Y \) on CW complexes that is a weak homotopy equivalence (inducing isomorphisms in homotopy) is in fact a homotopy equivalence.
:::

::: {.warnings}
Individual maps may not work: take \( S^2 \times{\mathbb{RP}}^3 \) and \( S^3 \times{\mathbb{RP}}^2 \) which have isomorphic homotopy but not homology.
:::

::: {.theorem title="Hurewicz"}
The Hurewicz map on an \( n-1{\hbox{-}} \)connected space \( X \) is an isomorphism \( \pi_{k\leq n}X \to H_{k\leq n} X \).

> I.e. for the minimal \( i\geq 2 \) for which \( \pi_{iX} \neq 0 \) but \( \pi_{\leq i-1}X = 0 \), \( \pi_{iX} \cong H_{iX} \).
:::

::: {.theorem title="Cellular Approximation"}
Any continuous map between CW complexes is homotopy equivalent to a cellular map.
:::

::: {.example title="Applications of cellular approximation"}
```{=tex}
\envlist
```
-   \( \pi_{k\leq n}S^n = 0 \)
-   \( \pi_{n}(X) \cong \pi_{n}(X^{(n)}) \)
:::

::: {.theorem title="Freudenthal Suspension"}
:::

```{=tex}
\todo[inline]{Theorem}
```
:::{.fact title=\"Unsorted facts about higher homotopy groups} `\envlist`{=tex}

-   \( \pi_{i\geq 2}(X) \) is always abelian.

    -   \( X \) simply connected \( \implies \pi_{k}(X) \cong H_{k}(X) \) up to and including the first nonvanishing \( H_{k} \)

-   \( \pi_{k} \bigvee X \neq \prod \pi_{k} X \) (counterexample: \( S^1 \vee S^2 \))

    -   Nice case: \( \pi_{1}\bigvee X = \ast \pi_{1} X \) by Van Kampen.

-   \( \pi_{i}(\widehat{X}) \cong \pi_{i}(X) \) for \( i\geq 2 \) whenever \( \widehat{X} \twoheadrightarrow X \) is a universal cover.

-   \( \pi_{i}(S^n) = 0 \) for \( i < n \), \( \pi_{n}(S^n) = {\mathbb{Z}} \)

    -   Not necessarily true that \( \pi_{i}(S^n) = 0 \) when \( i > n \)!!!
        -   E.g. \( \pi_{3}(S^2) = {\mathbb{Z}} \) by Hopf fibration

-   \( S^n / S^k \simeq S^n \vee \Sigma S^{k} \)

    -   \( \Sigma S^n = S^{n+1} \)

-   General mantra: homotopy plays nicely with products, homology with wedge products.[^5]

-   \( \pi_{k}\prod X = \prod \pi_{k} X \) by LES.[^6]

-   In general, homotopy groups behave nicely under homotopy pull-backs (e.g., fibrations and products), but not homotopy push-outs (e.g., cofibrations and wedges). Homology is the opposite.

-   Constructing a \( K(\pi, 1) \): since \( \pi = \left< S \mathrel{\Big|}R\right> = F(S)/R \), take \( \bigvee^{|S|} S^1 \cup_{|R|} e^2 \). In English, wedge a circle for each generator and attach spheres for relations.

:::

# Covering Spaces

Some pictures to keep in mind when it comes to covers and path lifting:

![Picture to keep in mind](figures/image_2021-01-10-13-45-42.png)

![A more complicated situation](figures/image_2021-01-09-00-19-03.png)

## Useful Facts

::: {.remark}
When covering spaces are involved in any way, try computing Euler characteristics - this sometimes yields nice numerical constraints.
:::

::: {.fact title="Euler characteristics are multiplicative on covering spaces"}
For \( p: A \xrightarrow{} B \) an \( n{\hbox{-}} \)fold cover,
\[
\chi(A) = n\, \chi(B)
.\]
:::

::: {.fact}
Covering spaces of orientable manifolds are orientable.
:::

::: {.fact}
The preimage of a boundary point under a covering map must also be a boundary point
:::

::: {.fact}
Normal subgroups correspond to *normal/regular* coverings, where automorphisms act freely/transitively. These are "maximally symmetric".
:::

## Universal Covers

::: {.proposition title="Existence of universal covers"}
If \( X \) is

-   Connected,
-   Locally path-connected, and
-   Semilocally simply connected,

then \( X \) admits a universal cover: if \( C \xrightarrow{q} X \) is a covering map with \( C \) connected, then there exists a covering map \( \tilde p: \tilde X \to C \) making the following diagram commute:

```{=tex}
\begin{tikzcd}
    {C} && {\tilde X} \\
    \\
    {X}
    \arrow["{q}", from=1-1, to=3-1, two heads]
    \arrow["{p}", from=1-3, to=3-1, two heads]
    \arrow["{\tilde p}"', from=1-3, to=1-1, dashed, two heads]
\end{tikzcd}
```
> [Link to diagram](https://q.uiver.app/?q=WzAsMyxbMCwyLCJYIl0sWzAsMCwiQyJdLFsyLDAsIlxcdGlsZGUgWCJdLFsxLDAsInEiLDAseyJzdHlsZSI6eyJoZWFkIjp7Im5hbWUiOiJlcGkifX19XSxbMiwwLCJwIiwwLHsic3R5bGUiOnsiaGVhZCI6eyJuYW1lIjoiZXBpIn19fV0sWzIsMSwiXFx0aWxkZSBwIiwyLHsic3R5bGUiOnsiYm9keSI6eyJuYW1lIjoiZGFzaGVkIn0sImhlYWQiOnsibmFtZSI6ImVwaSJ9fX1dXQ==)

That is, any other cover \( C \) of \( X \) is itself covered by \( \tilde X \). Note that by this universal property, \( \tilde X \) is unique up to homeomorphism when it exists.
:::

::: {.theorem title="Homotopy lifting property for covers, Hatcher 1.30"}
Let \( p:\tilde X \to X \) be any covering space, \( F: Y \times I \to X \) be any homotopy, and \( \tilde F_0: Y\to \tilde X \) be any lift of \( F_0 \). Then there exists a unique homotopy \( \tilde F:Y\to \tilde X \) of \( \tilde F_0 \) that lifts \( F \):

```{=tex}
\begin{tikzcd}
    {Y} && {\tilde X} \\
    \\
    {Y\times I} && {X}
    \arrow["{p}", from=1-3, to=3-3]
    \arrow["{F}"', from=3-1, to=3-3]
    \arrow["{\tilde F_0}", from=1-1, to=1-3]
    \arrow["{\exists \tilde F}", from=3-1, to=1-3, dashed]
    \arrow["{y \mapsto (y, 0)}"', from=1-1, to=3-1, hook]
\end{tikzcd}
```
> [Link to diagram](https://q.uiver.app/?q=WzAsNCxbMiwwLCJcXHRpbGRlIFgiXSxbMiwyLCJYIl0sWzAsMiwiWVxcY3Jvc3MgSSJdLFswLDAsIlkiXSxbMCwxLCJwIl0sWzIsMSwiRiIsMl0sWzMsMCwiXFx0aWxkZSBGXzAiXSxbMiwwLCJcXGV4aXN0cyBcXHRpbGRlIEYiLDAseyJzdHlsZSI6eyJib2R5Ijp7Im5hbWUiOiJkYXNoZWQifX19XSxbMywyLCJ5IFxcbWFwc3RvICh5LCAwKSIsMix7InN0eWxlIjp7InRhaWwiOnsibmFtZSI6Imhvb2siLCJzaWRlIjoidG9wIn19fV1d)
:::

::: {.theorem title="Lifting criterion for covers, Hatcher 1.33"}
If \( f: Y\to X \) with \( Y \) path-connected and locally path-connected, then there exists a unique lift \( \tilde f: Y\to \tilde X \) if and only if \( f_*(\pi_1(Y)) \subset \pi_*(\pi_1 (\tilde X)) \):

```{=tex}
\begin{tikzcd}
    && {\tilde X} \\
    \\
    {Y} && {X}
    \arrow["{p}", from=1-3, to=3-3]
    \arrow["{f}"', from=3-1, to=3-3]
    \arrow["{\tilde f}", from=3-1, to=1-3, dashed]
\end{tikzcd}
```
> [Link to diagram](https://q.uiver.app/?q=WzAsMyxbMCwyLCJZIl0sWzIsMiwiWCJdLFsyLDAsIlxcdGlsZGUgWCJdLFsyLDEsInAiXSxbMCwxLCJmIiwyXSxbMCwyLCJcXHRpbGRlIGYiLDAseyJzdHlsZSI6eyJib2R5Ijp7Im5hbWUiOiJkYXNoZWQifX19XV0=)

Moreover, lifts are *unique* if they agree at a single point.
:::

::: {.remark title="Automatic lifts"}
Note that if \( Y \) is simply connected, then \( \pi_1(Y) = 0 \) and this holds automatically!
:::

::: {.proposition title="Covering spaces induce injections on $\\pi_1$, Hatcher 1.31"}
Given a covering space \( \tilde X \xrightarrow{p} X \), the induced map \( p^*: \pi_1(\tilde X) \to \pi_1(X) \) is injective. The image consists of classes \( [\gamma] \) whose lifts to \( \tilde X \) are again loops.
:::

::: {.theorem title="Fundamental theorem of covering spaces, Hatcher 1.39"}
For \( \tilde X \xrightarrow{p} X \) a covering space with

-   \( \tilde X \) path-connected,
-   \( X \) path-connected and locally path-connected,

letting \( H \) be the image of \( \pi_1(\tilde X) \) in \( \pi_1(X) \), we have

1.  \( \tilde X \) is normal if and only if \( H{~\trianglelefteq~}\pi_1(X) \),

2.  \( G(\tilde X) \cong {\operatorname{Aut}}_{\mathrm{Cov}(\tilde X) } N_{\pi_1(X)}(H) \), the normalizer of \( H \) in \( \pi_1(X) \).

In particular, if \( \tilde X \) is normal, \( {\operatorname{Aut}}(\tilde X) \cong \pi_1(X) / H \), and if \( \tilde X \) is the universal cover, \( {\operatorname{Aut}}(\tilde X) = \pi_1(X) \).
:::

::: {.fact}
There is a contravariant bijective correspondence
\[
\left\{{\substack{
  \text{Connected covering spaces} \\
  p: \tilde X \xrightarrow{} X
}}\right\}_{/\sim}
&\rightleftharpoons
\left\{{\substack{
  \text{Conjugacy classes of subgroups} \\
  \text{of } \pi_1(X)
}}\right\}
.\]
If one fixes \( \tilde x_0 \) as a basepoint for \( \pi_1(\tilde X) \), this yields
\[
\left\{{\substack{
  \text{Connected covering spaces} \\
  p: \tilde X \xrightarrow{} X
}}\right\}_{/\sim}
&\rightleftharpoons
\left\{{\substack{
  \text{Subgroups of } \pi_1(X)
}}\right\}
.\]
:::

::: {.proposition title="Number of sheets in a covering space, Hatcher 1.32"}
For \( X, \tilde X \) both path-connected, the number of sheets of a covering space is equal to the index
\[
[p^*(\pi_1(\tilde X)): \pi_1(X)]
.\]

Note that the number of sheets is always equal to the cardinality of \( p ^{-1} (x_0) \).
:::

### Examples

::: {.example title="The circle $S^1$"}
Identify \( S^1 \subset {\mathbb{C}} \), then every map \( p_n: S^1 \to S^1 \) given by \( z\mapsto z^n \) a yields a covering space \( \tilde X_n \). The induced map can be described on generators as
\[
p_n^*: \pi_1(S^1) &\to \pi_1(S^1) \\
[\omega_1] &\mapsto [\omega_n] = n[\omega_1]
\]
and so the image is isomorphic to \( n{\mathbb{Z}} \) and thus
\[
p_n^*(\pi_1(S^1)) = {\operatorname{Aut}}_{\mathrm{Cov} }(\tilde X_n) = {\mathbb{Z}}/n{\mathbb{Z}}
.\]
where the deck transformations are rotations of the circle by \( 2\pi/n \). The universal cover of \( S^1 \) is \( {\mathbb{R}} \); this is an infinitely sheeted cover, and the fiber above \( x_0 \) has cardinality \( {\left\lvert {{\mathbb{Z}}} \right\rvert} \).
:::

::: {.example title="Projective $n\\dash$space $\\RP^n$"}
The universal cover of \( {\mathbb{RP}}^n \) is \( S^n \); this is a two-sheeted cover. The fiber above \( x_0 \) contains the two antipodal points.
:::

::: {.example title="The torus"}
The universal cover of \( T = S^1 \times S^1 \) is \( \tilde X ={\mathbb{R}}\times{\mathbb{R}} \). The fiber above the base point contains every point on the integer lattice \( {\mathbb{Z}}\times{\mathbb{Z}}= \pi_1(T) = \text{Aut}(\tilde X) \)
:::

::: {.fact}
For a wedge product \( X = \bigvee_i^n \tilde X_i \), the covering space \( \tilde X \) is constructed as a infinite tree with \( n{\hbox{-}} \)colored vertices:

-   Each vertex corresponds to one of the universal covers \( \tilde X_i \),
-   The color corresponds to which summand \( \tilde X_i \) appears,
-   T The neighborhood of each colored vertex has edges corresponding (not bijectively) to generators of \( \pi_1(X_i) \).
:::

::: {.example title="Covering spaces of wedges of spheres"}
The fundamental group of \( S^1 \vee S^1 \) is \( {\mathbb{Z}}\ast {\mathbb{Z}} \), and the universal cover is the following 4-valent Cayley graph:

![The universal cover of \( \S^1 \vee S^1 \)](figures/image_2021-01-10-13-19-32.png)

See Hatcher p.58 for other covers.
:::

::: {.corollary title="Every subgroup of a free group is free"}
Idea for a particular case: use the fact that \( \pi_1(\bigvee^k S^1) = {\mathbb{Z}}^{\ast k} \), so if \( G \leq {\mathbb{Z}}^{\ast k} \) then there is a covering space \( X \twoheadrightarrow\bigvee^k S^1 \) such that \( \pi_1(X) = G \). Since \( X \) can be explicitly constructed as a graph, i.e. a CW complex with only a 1-skeleton, \( \pi_1(X) \) is free on its maximal tree. \( \hfill\blacksquare \)
:::

::: {.example title="of a universal covering space"}
The fundamental group of \( {\mathbb{RP}}^2 \vee {\mathbb{RP}}^2 \) is \( {\mathbb{Z}}_2 \ast {\mathbb{Z}}_2 \), corresponding to an infinite string of copies of 2-valent \( S^2 \)s:

![Another universal cover.](figures/image_2021-01-10-13-14-27.png)
:::

::: {.example title="of a universal covering space"}
The fundamental group of \( {\mathbb{RP}}^2 \vee T^2 \) is \( {\mathbb{Z}}_2 \ast {\mathbb{Z}} \), and the universal cover is shown in the following image. Each red vertex corresponds to a copy of \( S^2 \) covering \( {\mathbb{RP}}^2 \) (having exactly 2 neighbors each), and each blue vertex corresponds to \( {\mathbb{R}}^2 \) cover \( {\mathbb{T}}^2 \), with \( {\left\lvert {{\mathbb{Z}}^2} \right\rvert} \) many vertices as neighbors.

![Universal cover of \( {\mathbb{T}}^2 \vee {\mathbb{RP}}^2 \)](figures/tree_cover.png)
:::

### Applications

::: {.theorem title="Maps into contractible spaces are always nullhomotopic"}
If \( X \) is contractible, every map \( f: Y \to X \) is nullhomotopic.
:::

::: {.proof title="?"}
If \( X \) is contractible, there is a homotopy \( H: X\times I \to X \) between \( \operatorname{id}_X \) and a constant map \( c: x \mapsto x_0 \). So construct
\[
H': Y\times I &\to X \\
H'(y, t) 
&\coloneqq
\begin{cases}
H(f(y), 0) = (\operatorname{id}_X \circ f)(y) = f(y) & t=0 \\
H(f(y), 1) = (c \circ f)(y) = c(y) = x_0 & t=1 \\
H(f(y), t) & \text{else}.
\end{cases}
\]
Then \( H' \) is a homotopy between \( f \) and a constant map, and \( f \) is nullhomotopic.
:::

::: {.corollary title="Factoring through a contractible space implies nullhomotopic"}
Any map \( f:X\to Y \) that factors through a contractible space \( Z \) is nullhomotopic.
:::

::: {.proof title="?"}
We have the following situation where \( f = p \circ \tilde f \):

```{=tex}
\begin{tikzcd}
    && {Z} \\
    \\
    {Y} && {X}
    \arrow["{p}", from=1-3, to=3-3]
    \arrow["{\tilde f}", from=3-1, to=1-3, dashed]
    \arrow["{f}"', from=3-1, to=3-3]
\end{tikzcd}
```
> [Link to diagram](https://q.uiver.app/?q=WzAsMyxbMCwyLCJZIl0sWzIsMiwiWCJdLFsyLDAsIloiXSxbMiwxLCJwIl0sWzAsMiwiXFx0aWxkZSBmIiwwLHsic3R5bGUiOnsiYm9keSI6eyJuYW1lIjoiZGFzaGVkIn19fV0sWzAsMSwiZiIsMl1d)

Since every map into a contractible space is nullhomotopic, there is a homotopy \( \tilde H: Y\times I \to Z \) from \( \tilde f \) to a constant map \( c: Y\to Z \), say \( c(y) = z_0 \) for all \( y \). But then \( p\circ \tilde H: X \times I \to Y \) is also a homotopy from \( f \) to the map \( p\circ c \), which satisfies \( (p\circ c)(y) = p(z_0) = x_0 \) for some \( x_0 \in X \), and is in particular a constant map.
:::

::: {.proposition title="Application: showing one space can not cover another"}
There is no covering map \( p: {\mathbb{RP}}^2 \to {\mathbb{T}}^2 \).
:::

::: {.proof title="?"}
```{=tex}
\envlist
```
-   Use the fact that \( \pi_1({\mathbb{T}}^2) \cong {\mathbb{Z}}^2 \) and \( \pi_1({\mathbb{RP}}^2) = {\mathbb{Z}}/2{\mathbb{Z}} \) are known.
-   The universal cover of \( {\mathbb{T}}^2 \) is \( {\mathbb{R}}^2 \), which is contractible.
-   Using the following two facts, \( p_* \) is the trivial map:
    -   By the previous results, \( p \) is thus nullhomotopic.
    -   Since \( p \) is a covering map, \( p_*: {\mathbb{Z}}/2{\mathbb{Z}}\hookrightarrow{\mathbb{Z}}^2 \) is injective.
-   Since \( p \) was supposed a cover, this can be used to imply that \( \operatorname{id}_{{\mathbb{T}}^2} \) is nullhomotopic.
-   Covering maps induce injections on \( \pi_1 \), and the only way the trivial map can be injective is if \( \pi_1(T^2) = 0 \), a contradiction.
:::

::: {.theorem title="When actions yield covering maps onto their quotients, Hatcher 1.40"}
If \( G\curvearrowright X \) is a free and properly discontinuous action, then

1.  The quotient map \( p:X \to X/G \) given by \( p(y) = Gy \) is a normal covering space,

2.  If \( X \) is path-connected, then \( G = {\operatorname{Aut}}_{\mathrm{Cov}} (X) \) is the group of deck transformations for the cover \( p \),

3.  If \( X \) is path-connected and locally path-connected, then \( G\cong \pi_1(X/G) / p_*(\pi_1(X)) \).
:::

::: {.fact title="Some common covering spaces"}
```{=tex}
\begin{tikzcd}
{\mathbb{Z}}
  \ar[r] 
& 
{\mathbb{R}}
  \ar[d] 
\\
& 
S^1 
\end{tikzcd}
```
```{=tex}
\begin{tikzcd}
{\mathbb{Z}}^n 
  \ar[r] 
& 
{\mathbb{R}}^n
  \ar[d] 
\\
& 
{\mathbb{T}}^n 
\end{tikzcd}
```
```{=tex}
\begin{tikzcd}
{\mathbb{Z}}/2{\mathbb{Z}}
  \ar[r] 
& 
S^n
  \ar[d] 
\\
& 
{\mathbb{RP}}^n 
\end{tikzcd}
```
```{=tex}
\begin{tikzcd}
{\mathbb{Z}}^{\ast n} 
  \ar[r] 
& 
\mathrm{Cayley}(n)
  \ar[d] 
\\
& 
\bigvee_n S^1 
\end{tikzcd}
```
given by the \( n{\hbox{-}} \)valent Cayley graph covering a wedge of circles.

-   \( T^2 \xrightarrow{\times 2} {\mathbb{K}} \)
-   \( {\mathbb{Z}}/q{\mathbb{Z}}\to L_{p/q} \xrightarrow{\pi} S^3 \)
-   \( {\mathbb{Z}}/n{\mathbb{Z}}\to {\mathbb{C}}^* \xrightarrow{z^n} {\mathbb{C}} \)
:::

# CW and Simplicial Complexes

```{=tex}
\todo[inline]{Missing a lot on CW complexes}
```
## Degrees

::: {.fact title="Useful properties of the degree of a map between spheres"}
```{=tex}
\envlist
```
-   \( \text{deg}~\operatorname{id}_{S^n} = 1 \)

-   \( \text{deg} (f\circ g) = \text{deg}~f \cdot \text{deg}~g \)

-   \( \text{deg}~r = -1 \) where \( r \) is any rotation about a hyperplane, i.e. \( r({\left[ {x_1 \cdots x_i \cdots x_n} \right]}) = {\left[ {x_1 \cdots -x_i \cdots x_n} \right]} \).

-   The antipodal map on \( S^n\subset {\mathbb{R}}^{n+1} \) is the composition of \( n+1 \) reflections, so \( \text{deg}~\alpha = (-1)^{n+1} \).
:::

## Examples of CW Complexes/Structures

::: {.example title="Spheres"}
\( S^n = e^0 \cup e^n \): a point and an \( n{\hbox{-}} \)cell.
:::

::: {.example title="Real Projective Space"}
\( {\mathbb{RP}}^n = e^1 \cup e^2 \cup \cdots \cup e^n \): one cell in each dimension.
:::

::: {.example title="Complex Projective Space"}
\( \mathbb{CP}^n =e^2 \cup e^4 \cup \cdots e^{2n} \)
:::

::: {.example title="Surfaces"}
![Fundamental domains](figures/1513064067523.png)
:::

## Examples of Simplicial Complexes

::: {.remark}
To write down a simplicial complex, label the vertices with increasing integers. Then each \( n \)-cell will correspond to a set of \( n+1 \) of these integers - throw them in a list.
:::

::: {.example title="Torus"}
![Torus](figures/1513062466927.png)
:::

::: {.example title="Klein Bottle and $\\RP^2$"}
![Klein Bottle and \( {\mathbb{RP}}^2 \)](figures/1513062526623.png)
:::

::: {.example title="Non-example"}
For counterexamples, note that this fails to be a triangulation of \( T \):

![Not a Torus](figures/1513062599096.png)

This fails - for example, the specification of a simplex \( [1,2,1] \) does not uniquely determine a triangle in the this picture.
:::

## Cellular Homology

-   \( S^n \) has the CW complex structure of 2 \( k \)-cells for each \( 0\leq k \leq n \).

How to compute:

1.  Write cellular complex
    \[0 \to C^n \to C^{n-1} \to \cdots C^2 \to C^1 \to C^0 \to 0\]

2.  Compute differentials \( {\partial}_{i}: C^i \to C^{i-1} \)

3.  *Note: if \( C^0 \) is a point, \( {\partial}_{1} \) is the zero map.*

4.  *Note: \( H_{n} X = 0 \iff C^n = \emptyset \).*

5.  Compute degrees: Use \( {\partial}_{n}(e_{i}^n) = \sum_{i} d_{i} e_{i}^{n-1} \) where
    \[d_{i} = \deg(\text{Attach }e_{i}^n \to \text{Collapse } X^{n-1}{\hbox{-}}\text{skeleton}),\]
    which is a map \( S^{n-1} \to S^{n-1} \).

Alternatively, choose orientations for both spheres. Then pick a point in the target, and look at points in the fiber. Sum them up with a weight of +1 if the orientations match and -1 otherwise.

6.  Note that \( {\mathbb{Z}}^m \xrightarrow{f} {\mathbb{Z}}^n \) has an \( n\times m \) matrix

7.  Row reduce, image is span of rows with pivots. Kernel can be easily found by taking RREF, padding with zeros so matrix is square and has all diagonals, then reading down diagonal - if a zero is encountered on \( n \)th element, take that column vector as a basis element with \( -1 \) substituted in for the \( n \)th entry.

For example:
\[
\begin{matrix}
\mathbf1&2&0&2\\0&0&\mathbf1&-1\\0&0&0&\mathbf0
\end{matrix} 
\to
\begin{matrix}
\mathbf1&2&0&2\\0&\mathbf0&0&0\\0&0&\mathbf1&-1\\0&0&0&\mathbf0
\end{matrix}
\begin{matrix}
\mathbf1&2&0&2\\0&\mathbf0&0&0\\0&0&\mathbf1&-1\\0&0&0&\mathbf0
\end{matrix} \\
\ker = 
\begin{matrix}
2\\-1\\0\\0
\end{matrix} 
\begin{matrix}
3\\0\\-1\\-1
\end{matrix}\\
\operatorname{im}= \left\langle{a+2b+2d,c-d}\right\rangle
.\]

6.  Or look at elementary divisors, say \( n_{i} \), then the image is isomorphic to \( \bigoplus n_{i} {\mathbb{Z}} \)

## Constructing a CW Complex with Prescribed Homology

Given \( G = \bigoplus G_{i} \), and want a space such that \( H_{i} X = G \)? Construct \( X = \bigvee X_{i} \) and then \( H_{i} (\bigvee X_{i}) = \bigoplus H_{i} X_{i} \). Reduces problem to: given a group \( H \), find a space \( Y \) such that \( H_{n}(Y) = G \). By the structure theorem of finitely generated abelian groups, it suffices to know how to do this for \( {\mathbb{Z}} \) and \( {\mathbb{Z}}/n{\mathbb{Z}} \), since their powers are just obtained by wedging (previous remark). Recipe:

1.  Attach an \( e^n \) to a point to get \( H_{n} = {\mathbb{Z}} \)

2.  Attach an \( e^{n+1} \) with attaching map of degree \( d \) to get \( H_{n} = {\mathbb{Z}}_{d} \)

# Homology

## Useful Facts

::: {.fact}
\( H_0(X) \) is a free abelian group on the set of path components of \( X \). Thus if \( X \) is path connected, \( H_0(X) \cong {\mathbb{Z}} \). In general, \( H_0(X) \cong {\mathbb{Z}}^{{\left\lvert {\pi_0(X)} \right\rvert}} \), where \( {\left\lvert {\pi_0(X)} \right\rvert} \) is the number of path components of \( X \).
:::

::: {.proposition title="Homology commutes with wedge products"}
\[
\tilde H_*(A\vee B) &\cong H_*(A) \times H_*(B) \\
H_{n}\qty{\bigvee_\alpha X_\alpha} &\cong \prod_\alpha H_{n} X_\alpha
\]
See footnote for categorical interpretation.[^7]
:::

```{=tex}
\todo[inline]{May need some good pair condition?}
```
::: {.example title="Application"}
\[
H_{n}(\bigvee_{k} S^n) = {\mathbb{Z}}^k
.\]
:::

::: {.proof title="?"}
Mayer-Vietoris.
:::

::: {.warnings}
\( H_{k} \qty{ \prod_ \alpha X_ \alpha} \) is **not** generally equal to \( \prod_ \alpha \qty{ H_{k} X_ \alpha } \). The obstruction is due to torsion -- if all groups are torsionfree, then the Kunneth theorem[^8] yields
\[
H_{k} (A\times B) = \prod_{i+j=k} H_{i} A \otimes H_{j} B
\]
:::

::: {.theorem title="Excision"}
Todo
:::

```{=tex}
\todo[inline]{Excision.}
```
:::{.fact title=\"Assorted facts} `\envlist`{=tex}

-   \( H_{n}(X) = 0 \iff X \) has no \( n{\hbox{-}} \)cells.
-   \( C^0 X = {\operatorname{pt}}\implies d_{1}: C^1 \to C^0 \) is the zero map. :::

## Known Homology

::: {.example title="Spheres"}
\[
H_{i}(S^n) = 
\begin{cases}
{\mathbb{Z}}& i = 0, n
\\
0 & \text{else}.
\end{cases}
\]
:::

::: {.example title="Real Projective Spaces"}
:::

::: {.example title="Complex Projective Spaces"}
:::

::: {.example title="Surfaces"}
:::

```{=tex}
\todo[inline]{Homology examples.}
```
## Mayer-Vietoris

::: {.fact title="Useful algebra fact"}
Since \( {\mathbb{Z}} \) is free and thus projective, any exact sequence of the form \( 0 \to {\mathbb{Z}}^n \to A \to {\mathbb{Z}}^m \to 0 \) splits and \( A\cong {\mathbb{Z}}^{n}\times{\mathbb{Z}}^m \).
:::

::: {.theorem title="Mayer-Vietoris"}
> Mnemonic: \( X = A \cup B \leadsto (\cap, \oplus, \cup) \)

Let \( X = A^\circ \cup B^\circ \); then there is a SES of chain complexes
\[
0 \to C_{n}(A\cap B) \xrightarrow{x\mapsto (x, -x)} C_{n}(A) \oplus C_{n}(B) \xrightarrow{(x, y) \mapsto x+y} C_{n}(A + B) \to 0
\]
where \( C_{n}(A+B) \) denotes the chains that are sums of chains in \( A \) and chains in \( B \). This yields a LES in homology:
\[
\cdots  H_{n}(A \cap B) \xrightarrow{(i^*,~ j^*)} H_{n}(A) \oplus H_{n}(B) \xrightarrow{l^* - r^*}  H_{n}(X) \xrightarrow{\delta} H_{n-1}(A\cap B)\cdots
\]
where

-   \( i: A\cap B \hookrightarrow A \) induces \( i^*: H_*(A\cap B) \to H_*(A) \)

-   \( j: A\cap B \hookrightarrow B \) induces \( j^*: H_*(A\cap B) \to H_*(B) \)

-   \( l: A \hookrightarrow A\cup B \) induces \( l^*: H_*(A) \to H_*(X) \)

-   \( r: B \hookrightarrow A\cup B \) induces \( r^*: H_*(B) \to H_*(X) \)

More explicitly,

```{=tex}
\begin{tikzcd}
 &  &  &  & \cdots \arrow[lllldd, out=0, in=-180, "\delta_{3}"'] 
 \\
 &  &  &  &  
 \\
H_{2}(A\cap B) \arrow[rr] \arrow[rr, "{(i^*, -j^*)_2}"] &  & H_{2} A \oplus H_{2} B \arrow[rr, "(l^* - r^*)_2"] &  & H_{2} (A\cup B) \arrow[lllldd, "\delta_{2}"', out=0, in=-180] 
\\
 &  &  &  &  
 \\
H_{1}(A\cap B) \arrow[rr, "{(i^*, -j^*)_1}"] &  & H_{1} A \oplus H_{1} B \arrow[rr, "(l^*-r^*)_1"] &  & H_{1} (A\cup B) \arrow[lllldd, "\delta_{1}"', out=0, in=-180] 
\\
 &  &  &  &  
 \\
H_{0} (A\cap B) \arrow[rr, "{(i^*, -j^*)_0}"] &  & H_{0} A \oplus H_{0} B \arrow[rr, "(l^* - r^*)_0"] &  & H_{0} (A\cup B) \arrow[lllldd, "\delta_{0}"', out=0, in=-180] 
\\
 &  &  &  &  
 \\
0 &  &  &  &
\end{tikzcd}
```
The connecting homomorphisms \( \delta_{n} :H_{n}(X) \to H_{n-1}(X) \) are defined by taking a class \( [\alpha] \in H_{n}(X) \), writing it as an \( n \)-cycle \( z \), then decomposing \( z = \sum c_{i} \) where each \( c_{i} \) is an \( x+y \) chain. Then \( {\partial}(c_{i}) = {\partial}(x+y) = 0 \), since the boundary of a cycle is zero, so \( {\partial}(x) = -{\partial}(y) \). So then just define \( \delta([\alpha]) = [{\partial}x] = [-{\partial}y] \).

Handy mnemonic diagram:
\[
\begin{matrix}
 && A\cap B & \\
&\diagup &  & \diagdown \\
A\cup B & & \longleftarrow &  & A \oplus B
\end{matrix}
.\]
:::

::: {.example title="Application: computing the homology of a connect sum"}
\( H_*(A \# B) \): Use the fact that \( A\# B = A \cup_{S^n} B \) to apply Mayer-Vietoris.
:::

::: {.proposition title="Application: isomorphisms in the homology of spheres"}
\[H^i(S^n) \cong H^{i-1}(S^{n-1}).\]
:::

::: {.proof}
Write \( X = A \cup B \), the northern and southern hemispheres, so that \( A \cap B = S^{n-1} \), the equator. In the LES, we have:

\[
H^{i+1}(S^n) \xrightarrow{} H^i(S^{n-1}) \xrightarrow{} H^iA \oplus H^i B \xrightarrow{} H^i S^n \xrightarrow{} H^{i-1}(S^{n-1}) \xrightarrow{} H^{i-1}A \oplus H^{i-1}B
.\]

But \( A, B \) are contractible, so \( H^iA= H^iB = 0 \), so we have

\[
H^{i+1}(S^n) \xrightarrow{} H^{i}(S^{n-1}) \xrightarrow{} 0 \oplus 0 \xrightarrow{}H^i(S^n) \xrightarrow{} H^{i-1}(S^{n-1}) \xrightarrow{} 0
.\]

In particular, we have the shape \( 0 \to A \to B \to 0 \) in an exact sequence, which is always an isomorphism.
:::

## More Exact Sequences

::: {.theorem title="Kunneth"}
There exists a short exact sequence
\[
0 \to \prod_{i+j=k} H_{j}(X; R) \otimes_{R} H_{i}(Y; R) \to H_{k}(X\times Y; R) \to \prod_{i+j=k-1} \operatorname{Tor}_{R}^1(H_{i}(X; R), H_{j}(Y; R))
.\]
If \( R \) is a free \( R{\hbox{-}} \)module, a PID, or a field, then there is a (non-canonical) splitting given by
\[
H_{k} (X\times Y) \cong \left( \prod_{i+j = k} H_{i} X \oplus H_{j} Y\right) \times\prod_{i+j = k-1}\operatorname{Tor}(H_{i}X, H_{j} Y) \\
\]
:::

::: {.theorem title="UCT for Change of Group"}
For changing coefficients from \( {\mathbb{Z}} \) to \( G \) an arbitrary group, there are short exact sequences

\[
0\to \operatorname{Tor}_{\mathbb{Z}}^0 (H_{i}(X;{\mathbb{Z}}), A) &\to H_{i}(X;A)\to \operatorname{Tor}_{\mathbb{Z}}^1 (H_{i-1}(X;{\mathbb{Z}}),A)\to 0 \\
& \quad \Downarrow \\ \\
0 \to H_{i} X \otimes G &\to H_{i}(X; G) \to \operatorname{Tor}_{\mathbb{Z}}^1(H_{i-1}X, G) \to 0 
\]
and
\[
0\to \operatorname{Ext} _{{\mathbb{Z}}}^{1}(H_{i-1}(X; {\mathbb{Z}}),A) &\to H^{i}(X; A)\to \operatorname{Ext} _{{\mathbb{Z}}}^{0}(H_{i}(X; {\mathbb{Z}}),A) \to 0 \\
&\quad \Downarrow \\ \\ 
0 \to \operatorname{Ext} (H_{i-1} X, G) &\to H^i(X;G) \to \hom(H_{i} X, G) \to 0
.\]
These split unnaturally:
\[
H_{i}(X;G) &= (H_{iX}\otimes G) \oplus \operatorname{Tor}(H_{i-1}X; G) \\
H^i(X; G) &= \hom(H_{i}X, G) \oplus \operatorname{Ext} (H_{i-1}X; G)
\]

When all of the \( H_{i}X \) are all finitely generated (e.g. if \( G \) is a field), writing \( H_{i}(X; {\mathbb{Z}}) = {\mathbb{Z}}^{\beta_{i}} \oplus T_{i} \) as the sum of a free and a torsionfree module, we have
\[
H^i(X; {\mathbb{Z}}) &\cong {\mathbb{Z}}^{\beta_{i}} \times T_{i-1} \\
H^i(X; A) &\cong \qty{H_i(X; G)} {}^{ \check{} }\coloneqq\hom_{\mathbb{Z}}(H_{i}(X; G), G)
.\]

In other words, letting \( F({-}) \) be the free part and \( T({-}) \) be the torsion part, we have
\[
H^i(X; {\mathbb{Z}}) &= F(H_{i}(X; {\mathbb{Z}})) \times T(H_{i-1}(X; {\mathbb{Z}}))\\
H_{i}(X; {\mathbb{Z}}) &= F(H^i(X; {\mathbb{Z}})) \times T(H^{i+1}(X; {\mathbb{Z}}))
\]
:::

```{=tex}
\todo[inline]{Might need assumptions: finite CW complex?}
```
## Relative Homology

::: {.fact title="Some assorted facts"}
```{=tex}
\envlist
```
-   \( H_{n}(X/A) \cong \tilde H_{n}(X, A) \) when \( A\subset X \) has a neighborhood that deformation retracts onto it.

-   LES of a pair

    -   \( (A \hookrightarrow X) \mapsto (A, X, X/A) \)

-   For CW complexes \( X = \left\{{X^{(i)}}\right\} \), we have
    \[
    H_{n}(X^{(k)},X^{(k-1)}) \cong \begin{cases}{\mathbb{Z}}[\left\{{e^n}\right\}]~ &k=n,\\ 0 &\text{otherwise}\end{cases} \qquad\text{ since } X^k/X^{k-1} \cong \bigvee S^k
    \]

-   \( H_{n}(X, A) \cong_? H_{n}(X/A, {\operatorname{pt}}) \)
:::

# Fixed Points and Degree Theory

::: {.theorem title="Lefschetz Fixed Point"}
For \( f:X\to X \), define the **trace** of \( f \) to be
\[
\Lambda_f \coloneqq\sum_{k \geq 0} (-1)^k ~\mathrm{Tr}(f_* \mathrel{\Big|}H_k(X; {\mathbb{Q}}))
\]
where \( f_*: H_k(X; {\mathbb{Q}}) \to H_k(X; {\mathbb{Q}}) \) is the induced map on homology. If \( \Lambda_f \neq 0 \) then \( f \) has a fixed point.
:::

::: {.theorem title="?"}
Every \( f: B^n \to B^n \) has a fixed point.
:::

::: {.proof title="?"}
:::

```{=tex}
\todo[inline]{Proof}
```
::: {.theorem title="Hairy Ball"}
There is no non-vanishing tangent vector field on even dimensional spheres \( S^{2n} \).
:::

::: {.theorem title="Borsuk-Ulam"}
For every \( S^n \xrightarrow{f} {\mathbb{R}}^n \exists x\in S^n \) such that \( f(x) = f(-x) \).
:::

# Surfaces and Manifolds

::: {.remark}
The most common spaces appearing in this theory:

-   \( {\mathbb{S}}^2 \),
-   \( {\mathbb{T}}^2 \coloneqq S^1\times S^1 \),
-   \( {\mathbb{RP}}^2 \)
-   \( {\mathbb{K}} \) the Klein bottle
-   \( {\mathbb{M}} \) the Möbius Strip
-   \( \Sigma_n \coloneqq\#_{i=1}^n {\mathbb{T}}^2 \).

The first 4 can be obtained from the following pasting diagrams:

![Pasting Diagrams for Surfaces](figures/PastingDiagrams.png)
:::

## Classification of Surfaces

::: {.theorem title="Classification of Surfaces"}
The set of surfaces under connect sum forms a monoid with the presentation
\[  
\left\langle{ {\mathbb{S}}^2, {\mathbb{RP}}^2, {\mathbb{T}}{~\mathrel{\Big|}~}{\mathbb{S}}^2 = 0, 3{\mathbb{RP}}^2 = {\mathbb{RP}}^2 + {\mathbb{T}}^2}\right\rangle = \left\{{ \Sigma_{g, n} {~\mathrel{\Big|}~}g, n \in {\mathbb{Z}}^{\geq 0} }\right\} 
.\]
where \( \Sigma_{g, n} \) is a surface of genus \( g \) with \( n \) discs removed to form boundary components.

Surfaces are classified up to homeomorphism by orientability and \( \chi \), or equivalently "genus"

-   In orientable case, actual genus, \( g \) equals the number of copies of \( {\mathbb{T}}^2 \).
-   In nonorientable case, \( k \) equals the number of copies of \( {\mathbb{RP}}^2 \).

In each case, there is a formula
\[  
\chi(X) = 
\begin{cases}
2-2g - b & \text{orientable} \\
2 - k & \text{non-orientable}.
\end{cases}
\]
:::

::: {.proposition title="Polygon Models for Surfaces"}
Every surface can be obtained as the identification space of a polygon labeled with sides \( \alpha_i, \beta_i, \rho_i \).

![\( \Sigma_{3, 3} \)](figures/image_2021-04-08-19-40-14.png)? ![image_2021-04-08-19-40-31](figures/image_2021-04-08-19-40-31.png) ![image_2021-04-08-19-40-41](figures/image_2021-04-08-19-40-41.png)
:::

```{=tex}
\todo[inline]{Examples, general procedure?}
```
::: {.fact table="Table of surfaces possible for a given Euler characteristic"}
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Orientable?              \( -4 \)         \( -3 \)          \( -2 \)         \( -1 \)          \( 0 \)                             \( 1 \)                 \( 2 \)
  ------------------------ ---------------- ----------------- ---------------- ----------------- ----------------------------------- ----------------------- ----------------------
  Yes                      \( \Sigma_3 \)   \( \emptyset \)   \( \Sigma_2 \)   \( \emptyset \)   \( {\mathbb{T}}^2, S^1\times I \)   \( {\mathbb{D}}^2 \)    \( {\mathbb{S}}^2 \)

  No                       ?                ?                 ?                ?                 \( {\mathbb{K}}, {\mathbb{M}} \)    \( {\mathbb{RP}}^2 \)   \( \emptyset \)
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
:::

::: {.proposition title="Inclusion-Exclusion"}
\[  
X = U\cup V \implies \chi(X) = \chi(U) + \chi(V) - \chi (U\cap V)
.\]
:::

::: {.proof}
Todo
:::

```{=tex}
\todo{Proof.}
```
::: {.corollary title="Euler for Connect Sums"}
\[  
\chi(A \# B) = \chi(A) + \chi(B) - 2
.\]
:::

::: {.proof}
Set \( U= A, B=V \), then by definition of the connect sum, \( A\cap B = {\mathbb{S}}^2 \) where \( \chi({\mathbb{S}}^2) = 2 \)
:::

::: {.proposition title="Decomposing $\\RP^2$"}
\[  
{\mathbb{RP}}^2 = {\mathbb{M}}{\coprod}_{\operatorname{id}_{{{\partial}}{\mathbb{M}}}} {\mathbb{M}}
.\]
:::

::: {.proposition title="Decomposing a Klein Bottle"}
\[  
{\mathbb{K}}\cong {\mathbb{RP}}^2 \# {\mathbb{RP}}^2
.\]
:::

::: {.proof}
Todo
:::

```{=tex}
\todo{Proof.}
```
::: {.proposition title="Rewriting a Klein Bottle"}
\[  
{\mathbb{RP}}^2 \# {\mathbb{K}}\cong {\mathbb{RP}}^2 \# {\mathbb{T}}^2
.\]
:::

::: {.proof}
Todo
:::

```{=tex}
\todo{Proof.}
```
## Manifolds

::: {.remark}
To show something is not a manifold, try looking at local homology. Can use point-set style techniques like removing points, i.e. \( H_1(X, X-{\operatorname{pt}}) \); this should essentially always yield \( {\mathbb{Z}} \) by excision arguments.
:::

::: {.proposition title="Dimension vanishing for homology of manifolds"}
If \( M^n \) is a closed and connected \( n{\hbox{-}} \)manifold, then \( H^{\geq n} X = 0 \).
:::

::: {.proposition title="Top homology for manifolds"}
If \( M^n \) is a closed connected manifold, then \( H_n = {\mathbb{Z}} \) and \( \operatorname{Tor}(H_{n-1}) = 0 \). More generally,
\[
\begin{cases}
{\mathbb{Z}}& M^n \text{ is orientable } 
\\
0 & \text{else}.
\end{cases}
\]
:::

::: {.proposition title="Poincaré Duality for manifolds"}
For \( M^n \) a closed orientable manifold without boundary and \( {\mathbb{F}} \) a field,
\[
H_k(M^n; {\mathbb{F}}) \cong H^{n-k}(M^n; {\mathbb{F}})
\iff
M^n \text{ is closed and orientable}
.\]
:::

::: {.proposition title="Relative Poincaré Duality for manifolds"}
If \( M^n \) is a closed orientable manifold with boundary then
\[
H_k(M^n; {\mathbb{Z}}) \cong H^{n-k}(M^n, {\partial}M^n; {\mathbb{Z}})
.\]
:::

::: {.proposition title="Known Euler characteristics"}
If \( M^n \) is closed and \( n \) is odd, then \( \chi(M^n) = 0 \).
:::

::: {.proof title="?"}
Todo. Uses Poincaré duality?
:::

```{=tex}
\todo[inline]{Proof!}
```
::: {.proposition title="Nondegenerate intersection pairings"}
For \( M^n \) closed and orientable, the intersection pairing is nondegenerate modulo torsion.
:::

::: {.proposition title="Orientation covers"}
For any manifold \( X \) there exists a covering space \( p: \tilde X_o\to X \), the **orientation cover**, where any map \( Y\to X \) factors through \( \tilde X_o \). If \( X \) is nonorientable, then \( p \) is a double cover.
:::

::: {.theorem title="Lefschetz Duality"}
Todo
:::

```{=tex}
\todo[inline]{Statement of Lefschetz duality.}
```
### 3-Manifolds, and Knot Complements

::: {.fact}
Every \( {\mathbb{C}}{\hbox{-}} \)manifold is canonically orientable.
:::

::: {.proposition title="Homology of 3-manifolds"}
Let \( M^3 \) be a 3-manifold, then its homology is given by the following (by cases):

-   Orientable: \( H_* = ({\mathbb{Z}}, {\mathbb{Z}}^r, {\mathbb{Z}}^r, {\mathbb{Z}}) \)

-   Nonorientable: \( H_* = ({\mathbb{Z}}, {\mathbb{Z}}^r, {\mathbb{Z}}^{r-1} \oplus {\mathbb{Z}}_2, {\mathbb{Z}}) \)
:::

::: {.proposition title="Homotopy type of knot complements"}
For \( K \) a knot, \( S^3\setminus K \) is a \( K(\pi, 1) \), and \( {\mathbb{R}}^3 \setminus K \simeq S^2 \vee \qty{S^3 \setminus K} \). Moreover, if \( K \) is nullhomologous and \( X \) is any 3-manifold,
\[
H_1\qty{X\setminus\nu(K)} \cong H_1 X \times{\mathbb{Z}}
\]
where \( \nu(K) \) is a tubular neighborhood of \( K \).
:::

::: {.proof title="?"}
Todo
:::

```{=tex}
\todo[inline]{todo}
```
::: {.proposition title="Homology of knot complements in $S^3$"}
For \( K \) a knot,
\[
H_*(S^3 \setminus K) = [{\mathbb{Z}}, {\mathbb{Z}}, 0, 0, \cdots]
.\]
:::

::: {.proof}
Apply Mayer-Vietoris, taking \( S^3 = n(K) \cup (S^3-K) \), where \( n(K) \simeq S^1 \) and \( S^3-K \cap n(K) \simeq T^2 \). Use the fact that \( S^3-K \) is a connected, open 3-manifold, so \( H^3(S^3-K) =0 \).
:::

# Extra Problems: Algebraic Topology

## Homotopy 101

-   Show that if \( X\xrightarrow{f} X^n \) is not surjective, then \( f \) is nullhomotopic.

## \( \pi_1 \) {#pi_1}

-   Compute \( \pi_1(S^1 \vee S^1) \)
-   Compute \( \pi_1(S^1 \times S^1) \)

## Surfaces

-   Show that if \( M^\text{orientable} \xrightarrow{\pi_k} M^\text{non-orientable} \) is a \( k{\hbox{-}} \)fold cover, then \( k \) is even or \( \infty \).
-   Show that \( M \) is orientable if \( \pi_1(M) \) has no subgroup of index 2.

# Fall 2014

## 1 {#section}

Let \( X = {\mathbb{R}}^3 - \Delta^{(1)} \), the complement of the skeleton of regular tetrahedron, and compute \( \pi_1(X) \) and \( H_*(X) \).

::: {.solution}
Lay the graph out flat in the plane, then take a maximal tree - these leaves 3 edges, and so \( \pi_1(X) = {\mathbb{Z}}^{\ast 3} \).

Moreover \( X \simeq S^1\vee S^1 \vee S^1 \) which has only a 1-skeleton, thus \( H_*(X) = [{\mathbb{Z}}, {\mathbb{Z}}^3, 0\rightarrow] \).
:::

## 2 {#section-1}

Let \( X = S^1 \times B^2 - L \) where \( L \) is two linked solid torii inside a larger solid torus. Compute \( H_*(X) \). `\todo[inline]{Solution}`{=tex}

## 3 {#section-2}

Let \( L \) be a 3-manifold with homology \( [{\mathbb{Z}}, {\mathbb{Z}}_3, 0, {\mathbb{Z}}, \ldots] \) and let \( X = L \times\Sigma L \). Compute \( H_*(X), H^*(X) \).

::: {.solution}
Useful facts:

-   \( H_{k}(X\times Y) \cong \bigoplus _{{i+j=k}}H_{i}(X)\otimes H_{j}(Y) \bigoplus_{i+j=k-1}\operatorname{Tor}(H_i(X), H_j(Y)) \)
-   \( \tilde H_i(\Sigma X) = \tilde H_{i-1}(X) \)

We will use the fact that \( H_*(\Sigma L) = [{\mathbb{Z}}, {\mathbb{Z}}, {\mathbb{Z}}_3, 0, {\mathbb{Z}}] \).

Represent \( H_*(L) \) by \( p(x, y) = 1 + yx + x^3 \) and \( H_*(\Sigma L) \) by \( q(x,y) = 1 + x + yx^2 + x^4 \), we can extract the free part of \( H_*(X) \) by multiplying

\[p(x,y)q(x,y) = 1 + (1+y)x + 2yx^2 + (y^2+1)x^3 + 2x^4 + 2yx^5 + x^7\]

where multiplication corresponds to the tensor product, addition to the direct sum/product.

So the free portion is
\[H_*(X) = [{\mathbb{Z}}, {\mathbb{Z}}\oplus {\mathbb{Z}}_3, {\mathbb{Z}}_3\otimes{\mathbb{Z}}_3, {\mathbb{Z}}\oplus {\mathbb{Z}}_3\otimes{\mathbb{Z}}_3, {\mathbb{Z}}^2, {\mathbb{Z}}_3^2, 0, {\mathbb{Z}}] \\
=[{\mathbb{Z}}, {\mathbb{Z}}\oplus {\mathbb{Z}}_3, {\mathbb{Z}}_3, {\mathbb{Z}}\oplus {\mathbb{Z}}_3, {\mathbb{Z}}^2, {\mathbb{Z}}_3^2, 0, {\mathbb{Z}}]
\]

We can add in the correction from torsion by noting that only terms of the form \( \operatorname{Tor}({\mathbb{Z}}_3, {\mathbb{Z}}_3) = {\mathbb{Z}}_3 \) survive. These come from the terms \( i=1, j=2 \), so \( i+j=k-1 \implies k = 1+2+1 = 4 \) and there is thus an additional torsion term appearing in dimension 4. So we have

\[H_*(X) = [{\mathbb{Z}}, {\mathbb{Z}}\times {\mathbb{Z}}_3, {\mathbb{Z}}_3, {\mathbb{Z}}\times {\mathbb{Z}}_3, {\mathbb{Z}}^2 \times {\mathbb{Z}}_3, {\mathbb{Z}}_3^2, 0, {\mathbb{Z}}] \\ = [{\mathbb{Z}}, {\mathbb{Z}}, 0,{\mathbb{Z}},{\mathbb{Z}}^2,0,0,{\mathbb{Z}}] \times [0,{\mathbb{Z}}_3,{\mathbb{Z}}_3,{\mathbb{Z}}_3,{\mathbb{Z}}_3,{\mathbb{Z}}_3^2,0,0]\]

and
\[H^*(X)= [{\mathbb{Z}}, {\mathbb{Z}}, 0,{\mathbb{Z}},{\mathbb{Z}}^2,0,0,{\mathbb{Z}}] \times [0, 0,{\mathbb{Z}}_3,{\mathbb{Z}}_3,{\mathbb{Z}}_3,{\mathbb{Z}}_3,{\mathbb{Z}}_3^2,0] \\ = [{\mathbb{Z}}, {\mathbb{Z}}, {\mathbb{Z}}_3,{\mathbb{Z}}\times {\mathbb{Z}}_3,{\mathbb{Z}}^2\times {\mathbb{Z}}_3,{\mathbb{Z}}_3,{\mathbb{Z}}_3^2,{\mathbb{Z}}].\]
:::

## 4 {#section-3}

Let \( M \) be a closed, connected, oriented 4-manifold such that \( H_2(M; {\mathbb{Z}}) \) has rank 1. Show that there is not a free \( {\mathbb{Z}}_2 \) action on \( M \).

::: {.solution}
Useful facts:

-   \( X \twoheadrightarrow_{\times p} Y \) induces \( \chi(X) = p\chi(Y) \)
-   Moral: always try a simple Euler characteristic argument first!

We know that \( H_*(M) = [{\mathbb{Z}}, A, {\mathbb{Z}}\times G, A, {\mathbb{Z}}] \) for some group \( A \) and some torsion group \( G \). Letting \( n=\mathrm{rank}(A) \) and taking the Euler characteristic, we have \( \chi(M) = (1)1 + (-1)n + (1)1 + (-1)n + (1)1 = 3-2n \). Note that this is odd for any \( n \).

However, a free action of \( {\mathbb{Z}}_2 \curvearrowright M \) would produce a double covering \( M \twoheadrightarrow_{\times 2} M/{\mathbb{Z}}_2 \), and multiplicativity of Euler characteristics would force \( \chi(M) = 2 \chi(M/{\mathbb{Z}}_2) \) and thus \( 3-2n = 2k \) for some integer \( k \). This would require \( 3-2n \) to be even, so we have a contradiction.
:::

## 5 {#section-4}

Let \( X \) be \( T^2 \) with a 2-cell attached to the interior along a longitude. Compute \( \pi_2(X) \).

::: {.solution}
Useful facts:

-   \( T^2 = e^0 + e^1_1 + e^1_2 + e^2 \) as a CW complex.
-   \( S^2/(x_0 \sim x_1) \simeq S^2 \wedge S^1 \) when \( x_0, x_1 \) are two distinct points. (Picture: sphere with a string handle connecting north/south poles.)
-   \( \pi_{\geq 2}(\tilde X) \cong \pi_{\geq 2}(X) \) for \( \tilde X \twoheadrightarrow X \) the universal cover.

Write \( T^2 = e^0 + e^1_1 + e^1_2 + e^2 \), where the first and second 1-cells denote the longitude and meridian respectively. By symmetry, we could have equivalently attached a disk to the meridian instead of the longitude, filling the center hole in the torus. Contract this disk to a point, then pull it vertically in both directions to obtain \( S^2 \) with two points identified, which is homotopy-equivalent to \( S^2 \vee S_1 \).

Take the universal cover, which is \( {\mathbb{R}}^1 \cup_{{\mathbb{Z}}} S^2 \) and has the same \( \pi_2 \). This is homotopy-equivalent to \( \bigvee_{i\in {\mathbb{Z}}}S^2 \) and so \( \pi_2(X) = \prod_{i\in {\mathbb{Z}}} {\mathbb{Z}} \) generated by each distinct copy of \( S^2 \). (Alternatively written as \( {\mathbb{Z}}[t, t^{-1}] \)).
:::

# Summer 2003

## 1 {#section-5}

Describe all possible covering maps between \( S^2, T^2, K \)

::: {.solution}
```{=tex}
\envlist
```
::: {.concept}
```{=tex}
\envlist
```
1.  \( \tilde X \twoheadrightarrow X \) induces \( \pi_1(\tilde X) \hookrightarrow\pi_1(X) \)
2.  \( \chi(\tilde X) = n \chi (X) \)
3.  \( \pi_n(X) = [S^n, X] \)
4.  \( Y \to X \) with \( \pi_1(Y) = 0 \) and \( \tilde X \simeq{\operatorname{pt}}\implies \) every \( Y\xrightarrow{f} X \) is nullhomotopic.
5.  \( \pi_*(T^2) = [{\mathbb{Z}}\ast {\mathbb{Z}}, 0\rightarrow] \)
6.  \( \pi_*(K) = [{\mathbb{Z}}\rtimes_{{\mathbb{Z}}_2} {\mathbb{Z}}, 0\rightarrow] \)
7.  Universal covers are homeomorphic.
8.  \( \pi_{\geq 2}(\tilde X) \cong \pi_{\geq 2}(X) \)
:::

Spaces

-   \( S^2 \twoheadrightarrow T^2 \)
-   \( S^2 \twoheadrightarrow K \)
-   \( K \twoheadrightarrow S^2 \)
-   \( T^2 \twoheadrightarrow S^2 \)
    -   All covered by the fact that
        \[
          {\mathbb{Z}}= \pi_2(S^2) \neq \pi_2(X) = 0
          \]
        for \( X = T^2, K \).
-   \( K \twoheadrightarrow T^2 \)
    -   Doesn't cover, would induce \( \pi_1(K) \hookrightarrow\pi_1(T^2) \implies {\mathbb{Z}}\rtimes{\mathbb{Z}}\hookrightarrow{\mathbb{Z}}^2 \) but this would be a non-abelian subgroup of an abelian group.
-   \( T^2 \twoheadrightarrow K \)
    -   ?

```{=tex}
\todo[inline]{Not complete!}
```
:::

## 2 {#section-6}

Show that \( {\mathbb{Z}}^{\ast 2} \) has subgroups isomorphic to \( {\mathbb{Z}}^{\ast n} \) for every \( n \).

::: {.solution}
```{=tex}
\envlist
```
::: {.concept}
```{=tex}
\envlist
```
1.  \( \pi_1(\bigvee^k S^1) = {\mathbb{Z}}^{\ast k} \)
2.  \( \tilde X \twoheadrightarrow X \implies \pi_1(\tilde X) \hookrightarrow\pi_1(X) \)
3.  Every subgroup \( G \leq \pi_1(X) \) corresponds to a covering space \( X_G \twoheadrightarrow X \)
4.  \( A \subseteq B \implies F(A) \leq F(B) \) for free groups.
:::

It is easier to prove the stronger claim that \( {\mathbb{Z}}^{\mathbb{N}}\leq {\mathbb{Z}}^{\ast 2} \) (i.e. the free group on countably many generators) and use fact 4 above. Just take the covering space \( \tilde X \twoheadrightarrow S^1 \vee S^1 \) defined via the gluing map \( {\mathbb{R}}\cup_{{\mathbb{Z}}} S^1 \) which attaches a circle to each integer point, taking 0 as the base point. Then let \( a \) denote a translation and \( b \) denote traversing a circle, so we have \( \pi_1(\tilde X) = \left<\cup_{n\in{\mathbb{Z}}}a^nba^{-n}\right> \) which is a free group on countably many generators. Since \( \tilde X \) is a covering space, \( \pi_1(\tilde X) \hookrightarrow\pi_1(S^1 \vee S^1) = {\mathbb{Z}}^{\ast 2} \). By 4, we can restrict this to \( n \) generators for any \( n \) to get a subgroup, and \( A\leq B \leq C \implies A \leq C \) as groups.
:::

## 3 {#section-7}

Construct a space having \( H_*(X) = [{\mathbb{Z}}, 0, 0, 0, 0, {\mathbb{Z}}_4, 0, \cdots] \).

::: {.solution}
```{=tex}
\envlist
```
::: {.concept}
```{=tex}
\envlist
```
-   Construction of Moore Spaces
-   \( \tilde H_n(\Sigma X) = \tilde H_{n-1}(X) \), using \( \Sigma X = C_X \cup_X C_X \) and Mayer-Vietoris.
:::

Take \( X = e^0 \cup_{\Phi_1} e^5 \cup_{\Phi_2} e^6 \), where
\[
\Phi_1: {\partial}B^5 = S^4 \xrightarrow{z~\mapsto z^0} e^0 \\
\Phi_2: {\partial}B^6 = S^5 \xrightarrow{z~\mapsto z^4} e^5
.\]

where \( \deg \Phi_2 = 4 \).
:::

## 4 {#section-8}

Compute \( H_* \) of the complement of a knotted solid torus in \( S^3 \).

::: {.solution}
```{=tex}
\envlist
```
::: {.concept}
```{=tex}
\envlist
```
-   \( H_*(T^2) = [{\mathbb{Z}}, {\mathbb{Z}}^2, {\mathbb{Z}}, 0\rightarrow] \)
-   \( N^{(1)} \simeq S^1 \), so \( H_{\geq 2}(N) = 0 \).
-   A SES \( 0\to A\to B \to F \to 0 \) with \( F \) free splits.
-   \( 0\to A \to B \xrightarrow{\cong} C \to D \to 0 \) implies \( A = D = 0 \).
:::

Let \( N \) be the knotted solid torus, so that \( {\partial}N = T^2 \), and let \( X = S^3 - N \). Then

-   \( S^3 = N \cup_{T^2} X \)
-   \( N \cap X = T^2 \)

and we apply Mayer-Vietoris to the reduced homology of \( S^3 \):

```{=tex}
\begin{tikzcd}
    {H_4(T^2)} && {H_4(N) \oplus H_4(X)} && {H_4(S^3)} \\
    \\
    {H_3(T^2)} && {H_3(N) \oplus H_3(X)} && {H_3(S^3)} \\
    \\
    {H_2(T^2)} && {H_2(N) \oplus H_2(X)} && {H_2(S^3)} \\
    \\
    {H_1(S^3)} && {H_1(N) \oplus H_1(X)} && {H_1(S^3)}
    \arrow[from=5-1, to=5-3]
    \arrow[from=5-3, to=5-5]
    \arrow[from=5-5, to=7-1, out=360, in=180]
    \arrow[from=7-1, to=7-3]
    \arrow[from=7-3, to=7-5]
    \arrow[from=3-1, to=3-3]
    \arrow[from=3-3, to=3-5]
    \arrow[from=3-5, to=5-1, out=360, in=180]
    \arrow[from=5-3, to=5-5]
    \arrow[from=1-5, to=3-1, out=360, in=180]
    \arrow[from=1-1, to=1-3]
    \arrow[from=1-3, to=1-5]
\end{tikzcd}
```
We can plug in known information and deduce some maps:

```{=tex}
\begin{tikzcd}
    0 && 0 && 0 \\
    \\
    \textcolor{rgb,255:red,92;green,92;blue,214}{0} && \textcolor{rgb,255:red,92;green,92;blue,214}{H_3(X)} && \textcolor{rgb,255:red,92;green,92;blue,214}{{\mathbb{Z}}} \\
    \\
    \textcolor{rgb,255:red,92;green,92;blue,214}{{\mathbb{Z}}} && \textcolor{rgb,255:red,92;green,92;blue,214}{H_2(X)} && \textcolor{rgb,255:red,92;green,92;blue,214}{0} \\
    \\
    {{\mathbb{Z}}^{\oplus 2}} && {{\mathbb{Z}}\oplus H_1(X) } && 0
    \arrow[color={rgb,255:red,92;green,92;blue,214}, from=5-1, to=5-3]
    \arrow[from=5-5, to=7-1, out=360, in=180]
    \arrow["\sim", hook, two heads, from=7-1, to=7-3]
    \arrow[from=7-3, to=7-5]
    \arrow[color={rgb,255:red,92;green,92;blue,214}, from=5-3, to=5-5]
    \arrow[color={rgb,255:red,92;green,92;blue,214}, from=3-1, to=3-3]
    \arrow[color={rgb,255:red,92;green,92;blue,214}, from=3-3, to=3-5]
    \arrow[color={rgb,255:red,92;green,92;blue,214}, from=3-5, to=5-1, out=360, in=180]
    \arrow[from=1-5, to=3-1, out=360, in=180]
    \arrow[from=1-1, to=1-3]
    \arrow[from=1-3, to=1-5]
\end{tikzcd}
```
We then deduce:

-   \( H_0(X) = {\mathbb{Z}} \): ? (Appeal to some path-connectedness argument?)

-   \( H_1(X) = {\mathbb{Z}} \) using the SES appearing on the first row:
    \[
    0 \to {\mathbb{Z}}^{ \oplus 2} \to {\mathbb{Z}}\oplus H_1(X) \to 0
    \]
    which is thus an isomorphism.

-   \( H_2(X) = H_3(X) = 0 \) by examining the SES spanning lines 3 and 2:
    \[
    0 \hookrightarrow H_3(X) \hookrightarrow{\mathbb{Z}}\xrightarrow{\cong_{{\partial}_3}} {\mathbb{Z}}\twoheadrightarrow H_2(X) \twoheadrightarrow 0
    \]
    Claim: \( {{\partial}}_3 \) must be an isomorphism. If this is true, \( H_3(X) \cong \ker {{\partial}}_3 = 0 \) and \( H_2(X) \cong \operatorname{coker}({{\partial}}_3) \coloneqq{\mathbb{Z}}/\operatorname{im}({{\partial}}_3) \cong {\mathbb{Z}}/{\mathbb{Z}}= 0 \).

    ```{=tex}
    \todo[inline]{Why is this true?}
    ```
:::

## 5 {#section-9}

Compute the homology and cohomology of a closed, connected, oriented 3-manifold \( M \) with \( \pi_1(M) = {\mathbb{Z}}^{\ast 2} \).

::: {.solution}
Facts used:

-   \( M \) closed, connected, oriented \( \implies H_i(M)\cong H^{n-i}(M) \)
-   \( H_1(X) = {\mathsf{Ab}}(\pi_1(X)) \).
-   For orientable manifolds \( H_n(M^n) = {\mathbb{Z}} \)

**Homology**

-   Since \( M \) is connected, \( H_0 = {\mathbb{Z}} \)
-   Since \( \pi_1(M) = {\mathbb{Z}}^{\ast 2} \), \( H_1 \) is the abelianization and \( H_1(X) = {\mathbb{Z}}^2 \)
-   Since \( M \) is closed/connected/oriented, Poincaré Duality holds and \( H_2 = H^{3-2} = H^1 = \mathbf{F} H_1 + \mathbf{T}H_0 \) by UCT. Since \( H_0={\mathbb{Z}} \) is torsion-free, we have \( H_2(M) = H_1(M) = {\mathbb{Z}}^2 \).
-   Since \( M \) is an orientable manifold, \( H_3(M) = {\mathbb{Z}} \)
-   So \( H_*(M) = [{\mathbb{Z}}, {\mathbb{Z}}^2, {\mathbb{Z}}^2, {\mathbb{Z}}, 0\rightarrow] \)

**Cohomology**

-   By Poincaré Duality, \( H^*(M) = \widehat{H_*(M)} = [{\mathbb{Z}}, {\mathbb{Z}}^2, {\mathbb{Z}}^2, {\mathbb{Z}}, 0, \cdots] \). (Where the hat denotes reversing the list.)
:::

## 6 {#section-10}

Compute \( \operatorname{Ext} ({\mathbb{Z}}\oplus {\mathbb{Z}}/2 \oplus {\mathbb{Z}}/3, {\mathbb{Z}}\oplus {\mathbb{Z}}/4 \oplus {\mathbb{Z}}/5) \).

::: {.solution}
```{=tex}
\envlist
```
::: {.concept}
```{=tex}
\envlist
```
Facts Used:[^9]

-   Since \( {\mathbb{Z}} \) is a free \( {\mathbb{Z}}{\hbox{-}} \)module,
    \[
    \operatorname{Ext} ({\mathbb{Z}}, {\mathbb{Z}}/m) = 0
    \]

-   Using the usual projective resolution \( 0 \to {\mathbb{Z}}\to {\mathbb{Z}}\to {\mathbb{Z}}/n \to 0 \),
    \[
    \operatorname{Ext} ({\mathbb{Z}}/n, {\mathbb{Z}}) = {\mathbb{Z}}/n
    .\]

-   
    \[
    \operatorname{Ext} ({\mathbb{Z}}/n, {\mathbb{Z}}/m) = ({\mathbb{Z}}/m) / (n \cdot {\mathbb{Z}}/m) \cong ({\mathbb{Z}}/m) / (d \cdot {\mathbb{Z}}/m) && 
    \text{where } d \coloneqq\gcd(m, n)
    .\]
    General principle: \( \operatorname{Ext} ({\mathbb{Z}}/n, G) = G/nG \)

    By applying \( \mathop{\mathrm{Hom}}_{\mathbb{Z}}({-}, G) \) to the above resolution:

```{=tex}
\begin{tikzcd}
    & 0 & {\operatorname{Ext} ^1_{\mathbb{Z}}({\mathbb{Z}}/n, G)} \\
    \\
    {\mathop{\mathrm{Hom}}_{\mathbb{Z}}({\mathbb{Z}}, G)} & {\mathop{\mathrm{Hom}}_{\mathbb{Z}}({\mathbb{Z}}, G)} & {\mathop{\mathrm{Hom}}_{\mathbb{Z}}({\mathbb{Z}}/n, G)} & 0 \\
    &&& {}
    \arrow[hook', from=3-3, to=3-2]
    \arrow["{\cdot n}"', from=3-2, to=3-1]
    \arrow[two heads, from=3-1, to=1-3, out=180, in=360]
    \arrow[from=1-3, to=1-2]
    \arrow[from=3-4, to=3-3]
\end{tikzcd}
```
> [Link to Diagram](https://q.uiver.app/?q=WzAsNyxbMiwwLCIwIl0sWzAsMiwiXFxIb21fXFxaWihcXFpaLCBHKSJdLFsyLDIsIlxcSG9tX1xcWlooXFxaWiwgRykiXSxbNCwyLCJcXEhvbV9cXFpaKFxcWlovbiwgRykiXSxbNCwwLCJcXEV4dF4xX1xcWlooXFxaWi9uLCBHKSJdLFs2LDIsIjAiXSxbNCwzXSxbMywyLCIiLDIseyJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6ImJvdHRvbSJ9fX1dLFsyLDEsIlxcY2RvdCBuIiwyXSxbMSw0LCIiLDAseyJzdHlsZSI6eyJoZWFkIjp7Im5hbWUiOiJlcGkifX19XSxbNCwwXSxbNSwzXV0=)

which can be identified with:

```{=tex}
\begin{tikzcd}
    && 0 && {G/nG} \\
    \\
    G && G && {\mathop{\mathrm{Hom}}_{\mathbb{Z}}({\mathbb{Z}}/n, G)} && 0 \\
    &&&& {}
    \arrow[hook', from=3-5, to=3-3]
    \arrow["{\cdot n}"', from=3-3, to=3-1]
    \arrow[two heads, from=3-1, to=1-5, out=180, in=360]
    \arrow[from=1-5, to=1-3]
    \arrow[from=3-7, to=3-5]
\end{tikzcd}
```
> [Link to Diagram](https://q.uiver.app/?q=WzAsNyxbMiwwLCIwIl0sWzAsMiwiRyJdLFsyLDIsIkciXSxbNCwyLCJcXEhvbV9cXFpaKFxcWlovbiwgRykiXSxbNCwwLCJHL25HIl0sWzYsMiwiMCJdLFs0LDNdLFszLDIsIiIsMix7InN0eWxlIjp7InRhaWwiOnsibmFtZSI6Imhvb2siLCJzaWRlIjoiYm90dG9tIn19fV0sWzIsMSwiXFxjZG90IG4iLDJdLFsxLDQsIiIsMCx7InN0eWxlIjp7ImhlYWQiOnsibmFtZSI6ImVwaSJ9fX1dLFs0LDBdLFs1LDNdXQ==)

3.  Contravariant Hom takes coproducts to products:
    \[
    \operatorname{Ext} (\bigoplus_{i\in I} A_i, \prod_{k\in K} B_k) = \prod_{i\in I} \prod_{k\in K} \operatorname{Ext} (A_i, B_k)
    .\]
:::

Write
\[
A_{-}&\coloneqq A_1 \oplus A_2 \oplus A_3 \coloneqq{\mathbb{Z}}\oplus  {\mathbb{Z}}/2 \oplus  {\mathbb{Z}}/3 \\
B_{-}&\coloneqq B_1 \oplus B_2 \oplus B_3 \coloneqq{\mathbb{Z}}\oplus {\mathbb{Z}}/4 \oplus  {\mathbb{Z}}/5
.\]

We can then define the bicomplex
\[
C_{{-}, {-}} \coloneqq\operatorname{Ext} (A_{-}, B_{-}) = \bigoplus_{0 \leq i, k \leq 3} \operatorname{Ext} (A_i, B_k)
,\]
i.e. \( C_{i, k} \coloneqq\operatorname{Ext} (A_i, B_k) \), which can be organized into the following diagram where we take the Ext at each position and sum them all together:

```{=tex}
\begin{tikzcd}
    {\operatorname{Ext} (A_1, B_1)} && {\operatorname{Ext} (A_1, B_2)} && {\operatorname{Ext} (A_1, B_3)} \\
    \\
    {\operatorname{Ext} (A_2, B_1)} && {\operatorname{Ext} (A_2, B_2)} && {\operatorname{Ext} (A_2, B_3)} \\
    \\
    {\operatorname{Ext} (A_3, B_1)} && {\operatorname{Ext} (A_3, B_2)} && {\operatorname{Ext} (A_3, B_3)}
\end{tikzcd}
```
> [Link to Diagram](https://q.uiver.app/?q=WzAsOSxbMCwwLCJcXEV4dF8xXlxcWlooQV8xLCBCXzEpIl0sWzAsMiwiXFxFeHRfMV5cXFpaKEFfMiwgQl8xKSJdLFswLDQsIlxcRXh0XzFeXFxaWihBXzMsIEJfMSkiXSxbMiwwLCJcXEV4dF8xXlxcWlooQV8xLCBCXzIpIl0sWzQsMCwiXFxFeHRfMV5cXFpaKEFfMSwgQl8zKSJdLFsyLDIsIlxcRXh0XzFeXFxaWihBXzIsIEJfMikiXSxbNCwyLCJcXEV4dF8xXlxcWlooQV8yLCBCXzMpIl0sWzIsNCwiXFxFeHRfMV5cXFpaKEFfMywgQl8yKSJdLFs0LDQsIlxcRXh0XzFeXFxaWihBXzMsIEJfMykiXV0=)

This equals the following:

```{=tex}
\begin{tikzcd}
    {\operatorname{Ext} ({\mathbb{Z}}, {\mathbb{Z}})} && {\operatorname{Ext} ({\mathbb{Z}}, {\mathbb{Z}}/4)} && {\operatorname{Ext} ({\mathbb{Z}}, {\mathbb{Z}}/5)} \\
    \\
    {\operatorname{Ext} ({\mathbb{Z}}/2, {\mathbb{Z}})} && {\operatorname{Ext} ({\mathbb{Z}}/2, {\mathbb{Z}}/4)} && {\operatorname{Ext} ({\mathbb{Z}}/2, {\mathbb{Z}}/5)} \\
    \\
    {\operatorname{Ext} ({\mathbb{Z}}/3, {\mathbb{Z}})} && {\operatorname{Ext} ({\mathbb{Z}}/3, {\mathbb{Z}}/4)} && {\operatorname{Ext} ({\mathbb{Z}}/3, {\mathbb{Z}}/5)}
\end{tikzcd}
```
> [Link to Diagram](https://q.uiver.app/?q=WzAsOSxbMCwwLCJcXEV4dF8xXlxcWlooQV8xLCBCXzEpIl0sWzAsMiwiXFxFeHRfMV5cXFpaKEFfMiwgQl8xKSJdLFswLDQsIlxcRXh0XzFeXFxaWihBXzMsIEJfMSkiXSxbMiwwLCJcXEV4dF8xXlxcWlooQV8xLCBCXzIpIl0sWzQsMCwiXFxFeHRfMV5cXFpaKEFfMSwgQl8zKSJdLFsyLDIsIlxcRXh0XzFeXFxaWihBXzIsIEJfMikiXSxbNCwyLCJcXEV4dF8xXlxcWlooQV8yLCBCXzMpIl0sWzIsNCwiXFxFeHRfMV5cXFpaKEFfMywgQl8yKSJdLFs0LDQsIlxcRXh0XzFeXFxaWihBXzMsIEJfMykiXV0=)

Which simplifies to:

```{=tex}
\begin{tikzcd}
    0 && 0 && 0 \\
    \\
    {{\mathbb{Z}}/2} && {{\mathbb{Z}}/2} && 0 \\
    \\
    {{\mathbb{Z}}/3} && {0} && {0}
\end{tikzcd}
```
> [Link to Diagram](https://q.uiver.app/?q=WzAsOSxbMCwwLCJcXEV4dF8xXlxcWlooQV8xLCBCXzEpIl0sWzAsMiwiXFxFeHRfMV5cXFpaKEFfMiwgQl8xKSJdLFswLDQsIlxcRXh0XzFeXFxaWihBXzMsIEJfMSkiXSxbMiwwLCJcXEV4dF8xXlxcWlooQV8xLCBCXzIpIl0sWzQsMCwiXFxFeHRfMV5cXFpaKEFfMSwgQl8zKSJdLFsyLDIsIlxcRXh0XzFeXFxaWihBXzIsIEJfMikiXSxbNCwyLCJcXEV4dF8xXlxcWlooQV8yLCBCXzMpIl0sWzIsNCwiXFxFeHRfMV5cXFpaKEFfMywgQl8yKSJdLFs0LDQsIlxcRXh0XzFeXFxaWihBXzMsIEJfMykiXV0=)

So the answer is \( {\mathbb{Z}}/2 \oplus {\mathbb{Z}}/2 \oplus {\mathbb{Z}}/3 \cong {\mathbb{Z}}/2 \oplus {\mathbb{Z}}/6 \).
:::

## 7 {#section-11}

Show there is no homeomorphism \( {\mathbb{CP}}^2 \xrightarrow{f} {\mathbb{CP}}^2 \) such that \( f({\mathbb{CP}}^1) \) is disjoint from \( {\mathbb{CP}}_1 \subset {\mathbb{CP}}_2 \).

::: {.solution}
```{=tex}
\envlist
```
::: {.concept}
```{=tex}
\envlist
```
1.  Every homeomorphism induces isomorphisms on homotopy/homology/cohomology.
2.  \( H^*({\mathbb{CP}}^2) = {\mathbb{Z}}[\alpha] / (\alpha^2) \) where \( \deg \alpha = 2 \).
3.  \( [f(X)] = f_*([X]) \)
4.  \( a\frown b = 0 \implies a=0~\text{or}~b=0 \) (nondegeneracy).
:::

Supposing such a homeomorphism exists, we would have \( [{\mathbb{CP}}^1] \frown[f({\mathbb{CP}}^1)] = 0 \) by the definition of these submanifolds being disjoint. But \( [{\mathbb{CP}}^1]\frown[f({\mathbb{CP}}^1)] = [{\mathbb{CP}}^1]\frown f_*([{\mathbb{CP}}^1]) \), where
\[
f_*: H^*({\mathbb{CP}}^2) \to H^*({\mathbb{CP}}^2)
\]
is the induced map on cohomology. Since the intersection pairing is nondegenerate, either \( [{\mathbb{CP}}^1] = 0 \) or \( f_*([{\mathbb{CP}}^1]) = 0 \). We know that \( H^*({\mathbb{CP}}^2) = {\mathbb{Z}}[\alpha] / \alpha^2 \) where \( \alpha = [{\mathbb{CP}}^1] \), however, so this forces \( f_*([{\mathbb{CP}}^1]) = 0 \). But since this was a generator of \( H^* \), we have \( f_*(H^*({\mathbb{CP}}^2)) = 0 \), so \( f \) is not an isomorphism on cohomology.
:::

## 8 {#section-12}

Describe the universal cover of \( X = (S^1 \times S^1) \vee S^2 \) and compute \( \pi_2(X) \).

::: {.solution}
```{=tex}
\envlist
```
::: {.concept}
```{=tex}
\envlist
```
-   \( \pi_{\geq 2}(\overline{X} ) \cong \pi_{\geq 2}(X) \) for \( \overline{X} \) the universal cover of \( X \)
-   Structure of the universal cover of a wedges
-   \( \overline{T^2} = {\mathbb{R}}^2 \) and \( \overline{S^2} = S^2 \)
-   By Mayer-Vietoris, \( H_n(\bigvee X_i) = \bigoplus H_n(X_i) \).
:::

The universal cover can be identified as
\[
\overline{X} = {\mathbb{R}}^2 \bigvee_{i, j \in {\mathbb{Z}}^2} S^2
,\]
i.e. the plane with a sphere wedged onto every integer lattice point. We can then check
\[
\pi_1(X) 
&\cong \pi_1(\overline{X} ) \\
&= \pi_1( {\mathbb{R}}^2 \bigvee_{i, j \in {\mathbb{Z}}^2} S^2 ) \\
&= \pi_1( {\mathbb{R}}^2 \bigvee_{i, j \in {\mathbb{Z}}^2} S^2 ) \\
&= \prod_{i,j \in {\mathbb{Z}}^2} \pi_1({\mathbb{R}}^2) \times\pi_1(S^2) \\
&= 0
,\]
using that \( \pi_1(S^2) = 0 \). Then by Hurewicz, \( \pi_2(X) \cong H_2(X) \), so we can compute
\[
H_2(X) 
&= H_2( {\mathbb{R}}^2 \bigvee_{i, j \in {\mathbb{Z}}^2} S^2 ) \\
&= \bigoplus_{i,j \in {\mathbb{Z}}^2} H_2({\mathbb{R}}^2) \oplus H_2(S^2) \\
&= \bigoplus_{i,j \in {\mathbb{Z}}^2} {\mathbb{Z}}
.\]
:::

## 9 {#section-13}

Let \( S^3 \to E \to S^5 \) be a fiber bundle and compute \( H_3(E) \).

::: {.solution title="Using the LES in Homotopy"}
```{=tex}
\envlist
```
::: {.concept}
```{=tex}
\envlist
```
-   Homotopy LES: \( F\to E\to B \leadsto \pi_*F() \to \pi_*(E) \to \pi_*(B) \).
-   Hurewicz: \( \pi_{\leq n}(X) = 0, \pi_n(X) \neq 0 \implies \pi_n(X) \cong H_n(X) \).
-   \( 0\to A\to B \to 0 \) exact iff \( A\cong B \)
:::

From the LES in homotopy we have

```{=tex}
\begin{tikzcd}
    {\pi_4(S^3)} && {\pi_4(E)} && {\pi_4(S^5)} \\
    \\
    {\pi_3(S^3)} && {\pi_3(E)} && {\pi_3(S^5)} \\
    \\
    {\pi_2(S^3)} && {\pi_2(E)} & {} & {\pi_2(S^5)} \\
    \\
    {\pi_1(S^3)} && {\pi_1(E)} && {\pi_1(S^5)} \\
    \\
    {\pi_0(S^3)} && {\pi_0(E)} && {\pi_0(S^5)}
    \arrow[from=1-1, to=1-3]
    \arrow[from=1-3, to=1-5]
    \arrow[from=1-5, to=3-1, in=180, out=360]
    \arrow[from=3-1, to=3-3]
    \arrow[from=3-3, to=3-5]
    \arrow[from=3-5, to=5-1, in=180, out=360]
    \arrow[from=5-1, to=5-3]
    \arrow[from=5-3, to=5-5]
    \arrow[from=5-5, to=7-1, in=180, out=360]
    \arrow[from=7-1, to=7-3]
    \arrow[from=7-3, to=7-5]
    \arrow[from=7-5, to=9-1, in=180, out=360]
    \arrow[from=9-1, to=9-3]
    \arrow[from=9-3, to=9-5]
\end{tikzcd}
```
> [Link to Diagram](https://q.uiver.app/?q=WzAsMTYsWzAsMCwiXFxwaV80KFNeMykiXSxbMiwwLCJcXHBpXzQoRSkiXSxbNCwwLCJcXHBpXzQoU141KSJdLFswLDIsIlxccGlfMyhTXjMpIl0sWzIsMiwiXFxwaV8zKEUpIl0sWzQsMiwiXFxwaV8zKFNeNSkiXSxbMyw0XSxbMCw0LCJcXHBpXzIoU14zKSJdLFswLDYsIlxccGlfMShTXjMpIl0sWzAsOCwiXFxwaV8wKFNeMykiXSxbMiw0LCJcXHBpXzIoRSkiXSxbNCw0LCJcXHBpXzIoU141KSJdLFsyLDYsIlxccGlfMShFKSJdLFs0LDYsIlxccGlfMShTXjUpIl0sWzIsOCwiXFxwaV8wKEUpIl0sWzQsOCwiXFxwaV8wKFNeNSkiXSxbMCwxXSxbMSwyXSxbMiwzXSxbMyw0XSxbNCw1XSxbNSw3XSxbNywxMF0sWzEwLDExXSxbMTEsOF0sWzgsMTJdLFsxMiwxM10sWzEzLDldLFs5LDE0XSxbMTQsMTVdXQ==)

and plugging in known information yields

```{=tex}
\begin{tikzcd}
    {\pi_4(S^3)} && {\pi_4(E)} && 0 \\
    \\
    \textcolor{rgb,255:red,92;green,92;blue,214}{{\mathbb{Z}}} && \textcolor{rgb,255:red,92;green,92;blue,214}{\pi_3(E)} && 0 \\
    \\
    0 && \textcolor{rgb,255:red,214;green,92;blue,92}{\pi_2(E) = 0} & {} & 0 \\
    \\
    0 && \textcolor{rgb,255:red,214;green,92;blue,92}{\pi_1(E)=0} && 0 \\
    \\
    {\mathbb{Z}}&& {\pi_0(E)} && {\mathbb{Z}}
    \arrow[from=1-1, to=1-3]
    \arrow[from=1-3, to=1-5]
    \arrow[from=1-5, to=3-1, in=180, out=360]
    \arrow["\sim", color={rgb,255:red,92;green,92;blue,214}, hook, two heads, from=3-1, to=3-3]
    \arrow[no head, from=3-3, to=3-5]
    \arrow[from=3-5, to=5-1, in=180, out=360]
    \arrow[from=5-1, to=5-3]
    \arrow[from=5-3, to=5-5]
    \arrow[from=5-5, to=7-1, in=180, out=360]
    \arrow[from=7-1, to=7-3]
    \arrow[from=7-3, to=7-5]
    \arrow[from=7-5, to=9-1, in=180, out=360]
    \arrow[hook, from=9-1, to=9-3]
    \arrow[two heads, from=9-3, to=9-5]
\end{tikzcd}
```
> [Link to Diagram](https://q.uiver.app/?q=WzAsMTYsWzAsMCwiXFxwaV80KFNeMykiXSxbMiwwLCJcXHBpXzQoRSkiXSxbNCwwLCIwIl0sWzAsMiwiXFxaWiIsWzI0MCw2MCw2MCwxXV0sWzIsMiwiXFxwaV8zKEUpIixbMjQwLDYwLDYwLDFdXSxbNCwyLCIwIl0sWzMsNF0sWzAsNCwiMCJdLFswLDYsIjAiXSxbMCw4LCJcXFpaIl0sWzIsNCwiXFxwaV8yKEUpID0gMCIsWzAsNjAsNjAsMV1dLFs0LDQsIjAiXSxbMiw2LCJcXHBpXzEoRSk9MCIsWzAsNjAsNjAsMV1dLFs0LDYsIjAiXSxbMiw4LCJcXHBpXzAoRSkiXSxbNCw4LCJcXFpaIl0sWzAsMV0sWzEsMl0sWzIsM10sWzMsNCwiXFxjb25nIiwxLHsiY29sb3VyIjpbMjQwLDYwLDYwXSwic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoiaG9vayIsInNpZGUiOiJ0b3AifSwiaGVhZCI6eyJuYW1lIjoiZXBpIn19fSxbMjQwLDYwLDYwLDFdXSxbNCw1LCIiLDAseyJzdHlsZSI6eyJoZWFkIjp7Im5hbWUiOiJub25lIn19fV0sWzUsN10sWzcsMTBdLFsxMCwxMV0sWzExLDhdLFs4LDEyXSxbMTIsMTNdLFsxMyw5XSxbOSwxNCwiIiwwLHsic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoiaG9vayIsInNpZGUiOiJ0b3AifX19XSxbMTQsMTUsIiIsMCx7InN0eWxlIjp7ImhlYWQiOnsibmFtZSI6ImVwaSJ9fX1dXQ==)

where

-   Rows 3 and 4 force \( \pi_3(E) \cong {\mathbb{Z}} \),
-   Rows 0 and 1 force \( \pi_0(E) = {\mathbb{Z}} \) (todo: not clear if this is true... is it even needed here?)
-   The remaining rows force \( \pi_1(E) = \pi_2(E) = 0 \).

By Hurewicz, we thus have \( H_3(E) = \pi_3(E) = {\mathbb{Z}} \).
:::

::: {.solution title="Using the Serre spectral sequence"}
```{=tex}
\todo[inline]{Four-corner spectral sequences, only homology in degrees 1,3,5,8. No differentials hit anything!}
```
:::

# Fall 2017 Final

## 1 {#section-14}

Let \( X \) be the subspace of the unit cube \( I^3 \) consisting of the union of the 6 faces and the 4 internal diagonals. Compute \( \pi_1(X) \).

## 2 {#section-15}

Let \( X \) be an arbitrary topological space, and compute \( \pi_1(\Sigma X) \).

::: {.solution}
Write \( \Sigma X = U \cup V \) where \( U = \Sigma X - (X\times[0,1/2]) \) and \( U = \Sigma X - X\times[1/2, 1]) \). Then \( U\cap V = X \times\{1/2\} \cong X \), so \( \pi_1(U\cap V) =\pi_1(X) \).

But both \( U \) and \( V \) can be identified by the cone on \( X \), given by \( CX = \frac{X \times I}{X \times 1} \), by just rescaling the interval with the maps:

\( i_U: U \to CX \) where \( (x,s) \mapsto (x, 2s-1) \) (The second component just maps \( [1/2, 1] \to[0,1] \). )

\( i_V: V \to CX \) where \( (x, s) \mapsto (x, 2s) \). (The second component just maps \( [0,1/2] \to [0, 1] \))

But \( CX \) is contractible by the homotopy \( H:CX \times I \to CX \) where \( H((c,s), t) = (c, s(1-t)) \).

So \( \pi_1(U) = \pi_1(V) = 0 \).

By Van Kampen, we have \( \pi_1(X) = 0 \ast_{\pi_1(X)} 0 = 0. \)
:::

## 3 {#section-16}

Let \( X = S^1 \times S^1 \) and \( A\subset X \) be a subspace with \( A \cong S^1 \vee S^1 \). Show that there is no retraction from \( X \) to \( A \).

::: {.solution}
We have \( \pi_1(S^1 \times S^1) = \pi_1(S^1) \times\pi_1(S^1) \) since \( S^1 \) is path-connected (by a lemma from the problem sets), and this equals \( {\mathbb{Z}}\times{\mathbb{Z}} \).

We also have \( \pi_1(S^1 \vee S^1) = \pi_1(S^1) \ast_{\left\{{pt}\right\}} \pi_1(S^1) \), which by Van-Kampen is \( {\mathbb{Z}}\ast {\mathbb{Z}} \).

Suppose \( X \) retracts onto \( A \), we can then look at the inclusion \( \iota: A \hookrightarrow X \). The induced homomorphism \( \iota_*: \pi_1(A) \hookrightarrow\pi_1(X) \) is then also injective, so we've produced an injection from \( f: {\mathbb{Z}}\ast {\mathbb{Z}}\hookrightarrow{\mathbb{Z}}\times{\mathbb{Z}} \).

This is a contradiction, because no such injection can exists. In particular, the commutator \( [a,b] \) is nontrivial in the source. But \( f(aba^{-1}b^{-1}) = f(a)f(b)f(a)^{-1}f(b)^{-1} \) since \( f \) is a homomorphism, but since the target is a commutative group, this has to equal \( f(a)f(a)^{-1} f(b)f(b)^{-1} = e \). So there is a non-trivial element in the kernel of \( f \), and \( f \) can not be injective - a contradiction.
:::

## 4 {#section-17}

Show that for every map \( f: S^2 \to S^1 \), there is a point \( x\in S^2 \) such that \( f(x) = f(-x) \).

::: {.solution}
Suppose towards a contradiction that \( f \) does not possess this property, so there is no \( x\in S^2 \) such that \( f(x) = f(-x) \).

Then define \( g: S^2 \to S^1 \) by \( g(x) = {f(x) - f(-x)} \); by assumption, this is a nontrivial map, i.e. \( g(x) \neq 0 \) for *any* \( x\in S^2 \).

In particular, \( -g(-x) = -{(f(-x) - f(x))} = {f(x) - f(-x)} = g(x) \), so \( -g(x) = g(-x) \) and thus \( g \) commutes with the antipodal map \( \alpha: S^2 \to S^2 \).

This means \( g \) is constant on the fibers of the quotient map \( p: S^2 \to{\mathbb{RP}}2 \), and thus descends to a well defined map \( \tilde g: {\mathbb{RP}}2 \to S^1 \), and since \( S^1 \cong {\mathbb{RP}}1 \), we can identify this with a map \( \tilde g: {\mathbb{RP}}2 \to{\mathbb{RP}}1 \) which thus induces a homomorphism \( \tilde g_*: \pi_1({\mathbb{RP}}2) \to \pi_1({\mathbb{RP}}1) \).

Since \( g \) was nontrivial, \( \tilde g \) is nontrivial, and by functoriality of \( \pi_1 \), \( \tilde g_* \) is nontrivial.

But \( \pi_1({\mathbb{RP}}2) = {\mathbb{Z}}_2 \) and \( \pi_1({\mathbb{RP}}1) = {\mathbb{Z}} \), and \( \tilde g_*: {\mathbb{Z}}^2 \to{\mathbb{Z}} \) can only be the trivial homomorphism - a contradiction.
:::

::: {.remark}
**Alternate Solution** Use covering space \( {\mathbb{R}}\twoheadrightarrow S^1 \)?
:::

## 5 {#section-18}

How many path-connected 2-fold covering spaces does \( S^1 \vee {\mathbb{RP}}2 \) have? What are the total spaces?

::: {.solution}
First note that \( \pi_1(X) = \pi_1(S^1) \ast_{{\operatorname{pt}}} \pi_1({\mathbb{RP}}2) \) by Van-Kampen, and this is equal to \( {\mathbb{Z}}\ast {\mathbb{Z}}_2 \).
:::

## 6 {#section-19}

Let \( G = <a, b> \) and \( H \leq G \) where \( H = <aba^{-1}b^{-1},~ a^2ba^{-2}b^{-1},~ a^{-1}bab^{-1},~ aba^{-2}b^{-1}a> \). To what well-known group is \( H \) isomorphic?

# Appendix: Homological Algebra

## Exact Sequences

::: {.proposition title="?"}
The sequence \( A \xrightarrow{f_1} B \xrightarrow{f_2} C \) is exact if and only if \( \operatorname{im}f_i = \ker f_{i+1} \) and thus \( f_2 \circ f_1 = 0 \).
:::

::: {.fact}
Some useful results:

-   \( 0 \to A \hookrightarrow_{f} B \) is exact iff \( f \) is **injective**
-   \( B\twoheadrightarrow_{f} C \to 0 \) is exact iff \( f \) is **surjective**
-   \( 0\to A \to B \to 0 \) is exact iff \( A \cong B \).
-   \( A \hookrightarrow B \to C \to D \twoheadrightarrow E \) iff \( C = 0 \)
-   \( 0\to A \to B \xrightarrow{\cong} C \to D\to 0 \) iff \( A = D = 0 \).
    -   Todo: Proof
-   \( 0\to A\to B \to C \to 0 \) splits iff \( C \) is free.
-   Can think of \( C \cong \frac{B}{\operatorname{im}f_1} \).
:::

::: {.definition title="Splitting an exact sequence"}
The sequences *splits* when a morphism \( f_2^{-1}: C \to B \) exists. In \( \textbf{Ab} \), this means \( B \cong A \oplus C \), in \( \mathbf{Grp} \) it's \( B \cong A \rtimes_\phi C \).
:::

::: {.example title="of exact sequences"}
```{=tex}
\envlist
```
-   \( 0 \to{\mathbb{Z}}\xrightarrow{\times 2} {\mathbb{Z}}\xrightarrow{\text{mod}~2} \frac{{\mathbb{Z}}}{2{\mathbb{Z}}} \to 0 \)
-   \( 1 \to N \xrightarrow{\iota} G \xrightarrow{p} \frac{G}{N} \to 1 \)
    -   Groups and normal subgroups
-   \( 1 \to\frac{{\mathbb{Z}}}{n{\mathbb{Z}}} \xrightarrow{\iota} D_{2n} \xrightarrow{?} \frac{{\mathbb{Z}}}{2{\mathbb{Z}}} \to 1 \)
    -   Dihedral group and cyclic groups
-   \( 0 \to I \cap J \xrightarrow{\Delta: x\mapsto(x,x)} I \oplus J \xrightarrow{f:(x,y) \mapsto x-y} I + J \to 0 \)
    -   \( R \)-Modules
-   \( 0 \to\frac{R}{I \cap J} \xrightarrow{\Delta: x\mapsto(x,x)} \frac{R}{I} \oplus \frac{R}{J} \xrightarrow{f:(x,y) \mapsto x-y} \frac{R}{I + J} \to 0 \)
-   \( 0 \to\mathbb{H}_1 \xrightarrow{\nabla} \mathbb{H}_\text{curl} \xrightarrow{\nabla \times} \mathbb{H}_\text{div} \xrightarrow{\nabla \cdot} \mathbb{L}_2 \to 0 \)
    -   Since \( \nabla \times\nabla F = \nabla \cdot\nabla\times\mkern 1.5mu\overline{\mkern-1.5muv\mkern-1.5mu}\mkern 1.5mu = 0 \) in Hilbert spaces
:::

::: {.remark}
Is \( f_1\circ f_2 = 0 \) equivalent to exactness..? Answer: yes, every exact sequence is a chain complex with trivial homology. Therefore homology measures the failure of exactness.

> Alternatively stated: Exact sequences are chain complexes with no cycles.
:::

::: {.remark}
Any LES \( A_1 \to\cdots \to A_6 \) decomposes into a twisted collection of SES's; define \( C_k = \ker (A_k \to A_{k+1}) \cong \operatorname{im}(A_{k-1} \to A_k)) \cong \operatorname{coker}(A_{k-2} \to A_{k-1}) \), then all diagonals here are exact: `<!--![Long short exact sequences.png](https://upload.wikimedia.org/wikipedia/commons/b/b9/Long_short_exact_sequences.png)-->`{=html}
:::

## Five Lemma

::: {.theorem title="?"}
If \( m, p \) are isomorphisms, \( l \) is an **surjection**, and \( q \) is an **injection**, then \( n \) is an **isomorphism**.

```{=html}
<!--![5 lemma.svg](https://upload.wikimedia.org/wikipedia/commons/thumb/f/f8/5_lemma.svg/388px-5_lemma.svg.png)-->
```
Proof: diagram chase two "four lemmas", one on each side. Full proof [here](https://en.wikipedia.org/wiki/Five_lemma).
:::

## Free Resolutions

::: {.example title="?"}
The canonical example:
\[
0 \to {\mathbb{Z}}\xrightarrow{\times m} {\mathbb{Z}}\xrightarrow{\pmod m} {\mathbb{Z}}_m \to 0
\]

Or more generally for a finitely generated group \( G = \left\langle{g_1, g_2, \cdots, g_n}\right\rangle \),
\[
\cdots \to \ker(f) \to F[g_1, g_2, \cdots, g_n] \xrightarrow{f} G \to 0
\]
where \( F \) denotes taking the free group.

Every abelian groups has a resolution of this form and length 2.
:::

## Properties of Tensor Products

-   \( A\otimes B \cong B\otimes A \)
-   \( ({-}) \otimes_R R^n = \operatorname{id} \)
-   \( \bigoplus_i A_i \otimes\bigoplus_j B_j = \bigoplus_i\bigoplus_j(A_i \otimes B_j) \)
-   \( {\mathbb{Z}}_m \otimes{\mathbb{Z}}_n = {\mathbb{Z}}_d \)
-   \( {\mathbb{Z}}_n \otimes A = A/nA \)

## Properties of Hom

-   \( \hom_R (\bigoplus_i A_i, \prod B_j) = \bigoplus_i \prod_j \hom(A_i, B_j) \)
-   Contravariant in first slot, covariant in second
-   Exact over vector spaces

## Properties of Tor

-   \( \operatorname{Tor}_R^0(A, B) = A \otimes_R B \)
-   \( \operatorname{Tor}(\bigoplus_i A_i, \bigoplus_j B) = \bigoplus_i \bigoplus_j \operatorname{Tor}(\mathbf{T}A_i, \mathbf{T}B_j) \) where \( \mathbf{T}G \) is the torsion component of \( G \).
-   \( \operatorname{Tor}({\mathbb{Z}}_n, G) = \ker (g \mapsto ng) = \left\{{g\in G\mathrel{\Big|}ng = 0}\right\} \)
-   \( \operatorname{Tor}(A, B) = \operatorname{Tor}(B, A) \)

## Properties of Ext

-   \( \operatorname{Ext} _R^0(A, B) = \hom_R(A, B) \)
-   \( \operatorname{Ext} (\bigoplus_i A_i, \prod_j B_j) = \bigoplus_i \prod_j \operatorname{Ext} (\mathbf{T}A_i, B_j) \)
-   \( \operatorname{Ext} (F, G) = 0 \) if \( F \) is free
-   \( \operatorname{Ext} ({\mathbb{Z}}_n, G) \cong G/nG \)

## Computing Tor

\[
\operatorname{Tor}(A, B) = h[\cdots \to A_n \otimes B \to A_{n-1}\otimes B \to \cdots A_1\otimes B \to 0]
\]
where \( A_* \) is any free resolution of \( A \).

Shorthand/mnemonic:
\[
\operatorname{Tor}: \mathcal{F}(A) \to ({-}\otimes B) \to H_*
\]

## Computing Ext

\[
\operatorname{Ext} (A, B) = h[\cdots \hom(A, B_n) \to \hom(A, B_{n-1}) \to \cdots \to \hom(A, B_1) \to 0 ]
\]
where \( B_* \) is a any free resolution of \( B \).

Shorthand/mnemonic:
\[
\operatorname{Ext} : \mathcal{F}(B) \to \hom(A, {-}) \to H_*
\]

## Hom/Ext/Tor Tables

  \( \hom \)             \( {\mathbb{Z}}_m \)   \( {\mathbb{Z}} \)   \( {\mathbb{Q}} \)
  ---------------------- ---------------------- -------------------- --------------------
  \( {\mathbb{Z}}_n \)   \( {\mathbb{Z}}_d \)   \( 0 \)              \( 0 \)
  \( {\mathbb{Z}} \)     \( {\mathbb{Z}}_m \)   \( {\mathbb{Z}} \)   \( {\mathbb{Q}} \)
  \( {\mathbb{Q}} \)     \( 0 \)                \( 0 \)              \( {\mathbb{Q}} \)

  \( \operatorname{Tor} \)   \( {\mathbb{Z}}_m \)   \( {\mathbb{Z}} \)   \( {\mathbb{Q}} \)
  -------------------------- ---------------------- -------------------- --------------------
  \( {\mathbb{Z}}_n \)       \( {\mathbb{Z}}_d \)   \( 0 \)              \( 0 \)
  \( {\mathbb{Z}} \)         \( 0 \)                \( 0 \)              \( 0 \)
  \( {\mathbb{Q}} \)         \( 0 \)                \( 0 \)              \( 0 \)

  \( \operatorname{Ext}  \)   \( {\mathbb{Z}}_m \)   \( {\mathbb{Z}} \)                 \( {\mathbb{Q}} \)
  --------------------------- ---------------------- ---------------------------------- --------------------
  \( {\mathbb{Z}}_n \)        \( {\mathbb{Z}}_d \)   \( {\mathbb{Z}}_n \)               \( 0 \)
  \( {\mathbb{Z}} \)          \( 0 \)                \( 0 \)                            \( 0 \)
  \( {\mathbb{Q}} \)          \( 0 \)                \( \mathcal{A_p}/{\mathbb{Q}} \)   \( 0 \)

Where \( d = \gcd(m, n) \) and \( {\mathbb{Z}}_0 \coloneqq 0 \).

Things that behave like "the zero functor":

-   \( \operatorname{Ext} ({\mathbb{Z}}, {-}) \)
-   \( \operatorname{Tor}({-}, {\mathbb{Z}}), \operatorname{Tor}({\mathbb{Z}}, {-}) \)
-   \( \operatorname{Tor}({-}, {\mathbb{Q}}), \operatorname{Tor}({\mathbb{Q}}, {-}) \)

Thins that behave like "the identity functor":

-   \( \hom({\mathbb{Z}}, {-}) \)
-   \( {-}\otimes_{\mathbb{Z}}{\mathbb{Z}} \) and \( {\mathbb{Z}}\otimes_{\mathbb{Z}}{-} \)

For description of \( \mathcal{A_p} \), see [here](http://math.jhu.edu/~jmb/note/torext.pdf). This is a certain ring of adeles.

# Appendix: Unsorted Stuff

-   Assorted info about other Lie Groups:

-   \( O_n, U_n, SO_n, SU_n, Sp_n \)

-   \( \pi_k(U_n) = {\mathbb{Z}}\cdot\indic{k~\text{odd}} \)

    -   \( \pi_1(U_n) = 1 \)

-   \( \pi_k(SU_n) = {\mathbb{Z}}\cdot\indic{k~\text{odd}} \)

    -   \( \pi_1(SU_n) = 0 \)

-   \( \pi_k(U_n) = {\mathbb{Z}}/2{\mathbb{Z}}\cdot\indic{k = 0,1\pmod 8} + {\mathbb{Z}}\cdot\indic{k = 3,7 \pmod 8} \)

-   \( \pi_k(SP_n) = {\mathbb{Z}}/2{\mathbb{Z}}\cdot\indic{k = 4,5\pmod 8} + {\mathbb{Z}}\cdot\indic{k = 3,7 \pmod 8} \)

-   Groups and Group Actions

    -   \( \pi_0(G) = G \) for \( G \) a discrete topological group.
    -   \( \pi_k(G/H) = \pi_k(G) \) if \( \pi_k(H) = \pi_{k-1}(H) = 0 \).
    -   \( \pi_1(X/G) = \pi_0(G) \) when \( G \) acts freely/transitively on \( X \).

## Cap and Cup Products

\[
\cup: H^p \times H^q \to H^{p+q}; (a^p \cup b^q)(\sigma) = a^p(\sigma \circ F_p) b^q(\sigma \circ B_q)
\]
where \( F_p, B_q \) is embedding into a \( p+q \) simplex.

For \( f \) continuous, \( f^*(a\cup b) = f^*a \cup f^*b \)

It satisfies the Leibniz rule
\[{\partial}(a^p \cup b^q) = {\partial}a^p \cup b^q + (-1)^p(a^p\cup {\partial}b^q)\]

\[
\cap: H_p \times H^q \to H_{p-q}; \sigma \cap \psi = \psi(F\circ\sigma)(B\circ \sigma)
\]
where \( F,B \) are the front/back face maps.

Given \( \psi \in C^q, \phi \in C^p, \sigma: \Delta^{p+q} \to X \), we have
\[
\psi(\sigma \cap \phi) = (\phi \cup \psi)(\sigma)\\
{\left\langle {\phi\cup \psi},~{\sigma} \right\rangle} = {\left\langle {\psi},~{\sigma \cap \phi} \right\rangle}
\]

Let \( M^n \) be a closed oriented smooth manifold, and \( A^{\widehat{i}}, B^{\widehat{j}} \subseteq X \) be submanifolds of codimension \( i \) and \( j \) respectively that intersect transversely (so \( \forall p\in A\cap B \), the inclusion-induced map \( T_pA \times T_p B \to T_p X \) is surjective.)

Then \( A\cap B \) is a submanifold of codimension \( i+j \) and there is a short exact sequence
\[
0 \to T_p(A\cap B) \to T_p A \times T_p B \to T_p X \to 0
\]

which determines an orientation on \( A\cap B \).

Then the images under inclusion define homology classes

-   \( [A] \in H_{\widehat{i}}X \)
-   \( [B] \in H_{\widehat{j}}X \)
-   \( [A\cap B] \in H_{\widehat{i+j}}X \).

Denoting their Poincare duals by

-   \( [A] {}^{ \check{} }\in H^i X \)
-   \( [B] {}^{ \check{} }\in H^j X \)
-   \( [A\cap B] {}^{ \check{} }\in H^{i+j}X \)

We then have
\[
[A] {}^{ \check{} }\smile [B] {}^{ \check{} }= [A\cap B] {}^{ \check{} }\in H^{i+j} X
\]

Example: in \( {\mathbb{CP}}^n \), each even-dimensional cohomology \( H^{2i}{\mathbb{CP}}^n \) has a generator \( \alpha_i \) with is Poincare dual to an \( \widehat{i} \) plane. A generic \( \widehat{i} \) plane intersects a \( \widehat{j} \) plane in a \( \widehat{i+j} \) plane, yielding \( \alpha_i \smile \alpha_j = \alpha_{i+j} \) for \( i+j \leq n \).

Example: For \( T^2 \), we have - \( H_1T^2 = {\mathbb{Z}}^2 \) generated by \( [A], [B] \), the longitudinal and meridian circles. - \( H_0T^2 = {\mathbb{Z}} \) generated by \( [p] \), the class of a point.

Then \( A\cap B = \pm [p] \), and so
\[
[A] {}^{ \check{} }\smile [B] {}^{ \check{} }= [p] {}^{ \check{} }\\
[B] {}^{ \check{} }\smile [A] {}^{ \check{} }= -[p] {}^{ \check{} }
\]

## The Long Exact Sequence of a Pair

LES of pair \( (A,B) \implies \cdots H_n(B) \to H_n(A) \to H_n(A,B) \to H_{n-1}(B) \cdots \)

`\begin{align*}
\begin{matrix}
  && B & \\
&\diagup &  & \diagdown \\
(A,B) & & \longleftarrow &  & A
\end{matrix}
.\end{align*}`{=tex}

![Barycentric Subdivision](figures/image_2020-06-01-00-35-21.png)

## Tables

![Higher homotopy groups of \( {\mathbb{RP}}^n \)](figures/image_2020-09-20-01-35-23.png)

![Higher homotopy groups of \( {\mathbb{CP}}^n \)](figures/image_2020-09-20-01-35-51.png)

![Homotopy groups of spheres.](figures/image_2020-09-20-01-39-16.png)

![Homotopy groups of exceptional groups](figures/image_2020-09-20-01-40-22.png)

## Homotopy Groups of Lie Groups

-   \( O(n) \): \( \pi_k O_n = ? \)
-   \( U(n): \pi_k U_n \) is \( {\mathbb{Z}} \) in odd degrees and \( \pi_1 U_n = 1 \) `\todo[inline]{Check}`{=tex}
-   \( SU(n): \pi_k U_n \) is \( {\mathbb{Z}} \) in odd degrees and \( \pi_1 U_n = 0 \).
-   \( U_n: \pi_k(U_n) \) is \( {\mathbb{Z}}/2{\mathbb{Z}} \) in degrees?

## Higher Homotopy

-   \( n \geq 2 \implies \pi_n(X) \in \mathbf{Ab} \)

-   \( \Sigma S^n = S^{n+1} \)

-   \( [\Sigma^n X, Y] \cong [X, \Omega^n Y] \)

-   \( \pi*n(\Omega X) = \pi*{n+1}(X) \)

    -   \( \pi_n(X) \cong \pi_0(\Omega^n X) \)

-   \( n\geq 2 \implies \pi_n(S^1) = 0 \)

-   \( k < n \implies \pi_k(S^n) = 0 \)

-   \( \pi_n(X) \) is the obstruction to \( f: S^n \to X \) being lifted to \( \widehat{f}: D^{n+1} \to X \)

-   \( \pi_n(X) \cong H_n(X) \) for the first \( n \) such that \( \pi_n(X) \neq 0 \); \( \forall k<n, ~H_k(X) = 0 \).

-   \( k+2 \leq 2n \implies \pi_k(S^n) \cong \pi_{k+1}(S^{n+1}) \)

-   \( \pi_k(S^n) = \pi_{k+1}S^{n+1} = \cdots =\pi_{k+i}S^{n+i} \)

-   \( F\to E \to B \) a fibration yields \( \cdots\pi_n(F) \to\pi_n(E) \to\pi_n(B) \to\pi*{n-1}(F) \cdots \)

-   Freundenthal suspension, stable homotopy groups

## Higher Homotopy Groups of the Sphere

-   \( \pi_n(S^n) = {\mathbb{Z}} \)
-   \( \pi_{n+1}S^n = {\mathbb{Z}}_2 \) for \( n \geq 4 \)
-   \( \pi_{n+2}(S^n) \cong {\mathbb{Z}}_2 \)
-   \( \pi_{n+3}S^n = {\mathbb{Z}}_8 \) for \( n\geq 5 \)
-   \( \pi_5 S^2 = {\mathbb{Z}}_2 \)
-   \( \pi_6 S^3 = {\mathbb{Z}}_4 \)
-   \( \pi_7 S^4 = {\mathbb{Z}}\oplus {\mathbb{Z}}_4 \)
-   \( \pi_k S^2 \cong \pi_k S^3 \)
-   \( \pi_3 S^2 \cong {\mathbb{Z}} \)
-   \( \pi_4 S^2 \cong {\mathbb{Z}}_2 \)

## Misc

-   \( \Omega({-}) \) is an exact functor.

## Building a Moore Space

-   To build a Moore space \( M(n, {\mathbb{Z}}_p) \), take \( X = S^n \) and attach \( e^{n+1} \) via a map \( \Phi: S^n = {\partial}B^{n+1}\to X^{(n)} = S^n \) of degree \( p \).
    -   To obtain \( M(n, \prod G_i) \) take the corresponding \( \bigvee X_i \)
    -   Can also use Mayer Vietoris to conclude \( H_{n+1}(\Sigma X) = H_n(X) \), and just suspend spaces with known homology.

[^1]: This is theorem 17.4 in Munkres

[^2]: Munkres 17.5

[^3]: This is a useful property because it supplies you with a homotopy.

[^4]: Note that the hypothesis that \( U_1 \cap U_2 \) is path-connected is necessary: take \( S^1 \) with \( U,V \) neighborhoods of the poles, whose intersection is two disjoint components.

[^5]: More generally, in \( \mathbf{Top} \), we can look at \( A \leftarrow{\operatorname{pt}}\to B \) -- then \( A\times B \) is the pullback and \( A \vee B \) is the pushout. In this case, homology \( h: \mathbf{Top} \to \mathbf{Grp} \) takes pushouts to pullbacks but doesn't behave well with pullbacks. Similarly, while \( \pi \) takes pullbacks to pullbacks, it doesn't behave nicely with pushouts.

[^6]: This follows because \( X\times Y \twoheadrightarrow X \) is a fiber bundle, so use LES in homotopy and the fact that \( \pi_{i\geq 2} \in \mathbf{Ab} \).

[^7]: \( \bigvee \) is the coproduct in the category \( \mathbf{Top}_0 \) of pointed topological spaces, and alternatively, \( X\vee Y \) is the pushout in \( \mathbf{Top} \) of \( X \leftarrow{\operatorname{pt}}\to Y \)

[^8]: The generalization of Kunneth is as follows: write \( \mathcal{P}(n, k) \) be the set of partitions of \( n \) into \( k \) parts, i.e. \( \mathbf{x} \in \mathcal{P}(n,k) \implies \mathbf{x} = (x_{1}, x_{2}, \ldots, x_{k}) \) where \( \sum x_{i} = n \). Then
    \[
    H_{n}\qty{\prod_{j=1}^k X_{j}} = \bigoplus_{\mathbf{x} \in \mathcal{P}(n,k)} \bigotimes_{i=1}^{k} H_{x_{i}}(X_{i}).
    \]

[^9]: Thanks to Oskar Henriksson for some fixes/clarifications and further explanations here!
