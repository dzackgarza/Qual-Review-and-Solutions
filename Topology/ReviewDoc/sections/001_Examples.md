# Examples



## Point-Set


:::{.definition title="Topological Notions in Analysis"}
A useful list:

![image_2021-05-27-20-18-15](figures/image_2021-05-27-20-18-15.png)

Note that limit points require punctured neighborhoods!

:::

:::{.example title="Some useful examples of openness and closedness"}

- $\QQ \subseteq \RR$ is neither open nor closed:
  - No point is interior, since every neighborhood of $q\in \QQ$ intersects some $p\in \RR\sm\QQ$.
    No point in the complement is interior for a similar reason.
  - It has no isolated points, and every $r\in \RR$ is a boundary and accumulation point.
- $\ZZ \subseteq \RR$ is closed and not open.
  - Just write $\RR\sm\ZZ = \union_{n\in \ZZ} (n, n+1)$, a countable union of open sets.
    There are no interior points: every neighborhood of $n\in \ZZ$ intersects $\RR\sm \ZZ$.
  - Every point is a boundary and accumulation point.
- Points are closed in $\RR$: $\RR \sm \ts{ p } = (-\infty, p) \union (p, \infty)$.
  - An infinite intersection of open sets need not be open: $\intersect_{n\in \NN} (p-1/n, p+1/n) = \ts{ p }$ which is closed.
- Intervals $(a, b)$ are open in $\RR^1$ but not in $\RR^d$ for $d\geq 2$.
- $\ts{1/n}$ has only isolated boundary points, and no interior points.
  The point $0$ is an accumulation point.
- The Cantor set has no interior points and no isolated points.
  Every point is a boundary point and an accumulation point.

:::



### Common Spaces and Operations

:::{.example title="Nice spaces"}
The following are some standard "nice" spaces:
\[
S^n, \DD^n, T^n, \RP^n, \CP^n, \mathbb{M}, \mathbb{K}, \Sigma_{g}, \RP^\infty, \CP^\infty
.\]
:::

:::{.example title="A bank of counterexamples"}
The following are useful spaces to keep in mind to furnish counterexamples:

- Finite discrete sets with the discrete topology.
- Subspaces of $\RR$: $(a, b), (a, b], (a, \infty)$, etc.
  - Sets given by real sequences, such as $\ts{0} \union \ts{{1 \over n}\suchthat n\in \ZZ^{\geq 1}}$
- $\QQ$
- The topologist's sine curve
- One-point compactifications
- $\RR^\omega$ for \( \omega \) the least uncountable ordinal (?)
- The Hawaiian earring
- The Cantor set

Examples of some more exotic spaces that show up less frequently:

- $\HP^n$, quaternionic projective space
- The Dunce Cap
- The Alexander Horned sphere

:::

\todo[inline]{Break these into separate examples and explain properties.}

:::{.example title="Non-Hausdorff spaces"}
The following spaces are non-Hausdorff:

- The cofinite topology on any infinite set.
- $\RR/\QQ$
- The line with two origins.
- Any variety $V(J) \subseteq \AA^n_{/k}$ for $k$ a field and $J\normal \kx{n}$.

:::

:::{.example title="Constructed spaces"}
The following are some examples of ways to construct specific spaces for examples or counterexamples:

- Knot complements in $S^3$
- Covering spaces (hyperbolic geometry)
- Lens spaces
- Matrix groups
- Prism spaces
- Pair of pants
- Seifert surfaces
- Surgery

- Simplicial Complexes
  - Nice minimal example:
  
![](figures/image_2020-05-22-18-58-03.png) 

:::

:::{.fact title="Operations"}
Some common operations that combine spaces:\

- Cartesian product $A\cross B$
- Wedge product $A \vee B$
- Connect Sum $A \# B$
- Quotienting $A/B$
- Puncturing $A\setminus \theset{a_{i}}$
- Smash product
- Join
- Cones
- Suspension
- Loop space
-  Identifying a finite number of points

:::


### Alternative Topologies

:::{.example title="Nonstandard topologies"}
The following are some nice examples of topologies to put on familiar spaces to produce counterexamples:

- Discrete
- Cofinite
- Discrete and Indiscrete
- Uniform
:::

:::{.example title="The cofinite topology"}
The cofinite topology on any space $X$ is always

- Non-Hausdorff
- Compact
:::

:::{.proposition title="Topology is discrete if and only if points are open"}
A topology $(X, \tau)$ is the discrete topology iff points $x\in X$ are open.
:::

:::{.proof title="?"}
If $\ts x_i$ is open for each $x_i \in X$, then 

- Any set $U$ can be written as $U = \union_{i\in I} x_I$ (for some $I$ depending on $U$), and 
- Unions of open sets are open.

Thus $U$ is open.
:::

:::{.example title="The discrete topology"}
Some facts about the discrete topology:

- Definition: every subset is open.
- Always Hausdorff
- Compact iff finite
- Totally disconnected
- If $X$ is discrete, every map $f:X\to Y$ for any $Y$ is continuous (obvious!)
:::

:::{.example title="The indiscrete topology"}
Some facts about the indiscrete topology:

- Definition: the only open sets are $\emptyset, X$
- Never Hausdorff
- If $Y$ is indiscrete, every map $f:X\to Y$ is continuous (obvious!)
- Always compact
:::

### Connectedness

| Space                  | Connected    | Locally Connected |
| ------                 | ---------    | ----------------- |
| $\RR$                  | $\checkmark$ | $\checkmark$      |
| $[0, 1] \union [2, 3]$ |              | $\checkmark$      |
| Sine Curve             | $\checkmark$ |                   |
| $\QQ$                  |              |                   |
