# Group Theory

## Big List of Notation

+--------------------------------------+------------------------------------------------------------------------------------------------------------------+
| Notation                             | Definition                                                                                                       |
+======================================+==================================================================================================================+
| $C_G(x)$                             | Centralizer of an element \ |
|                                      | \( \da \ts{g\in \Gamma \st [g, x] = 1} \subseteq \Gamma \) \ |
+--------------------------------------+---------------------------------------------------------------------------------------+
| $C_G(H)$                             | Centralizer of an subgroup \ |
|                                      | \( \da \ts{g\in \Gamma \st [g, x] = 1\,\, \forall h\in H} = \Intersect_{h\in H} C_H(h) \subseteq G \) \ |
+--------------------------------------+---------------------------------------------------------------------------------------+
| $C(H)$                               | Conjugacy Class  \ |
|                                      | \( \da \ts{ ghg ^{-1} \st g\in G} \leq G \subseteq G \) \ |
+--------------------------------------+---------------------------------------------------------------------------------------+
| \( Z(G) \)                           | Center \ |
|                                      | \( \da \ts{ x\in G \st \forall g\in G,\, gxg ^{-1} = x } \subseteq G \)		|
+--------------------------------------+---------------------------------------------------------------------------------------+
| \( N_G(H) \)                         | Normalizer \ |
|                                      | \( \da \ts{ g\in G \st gHg ^{-1} = H } \subseteq G \)		|
+--------------------------------------+---------------------------------------------------------------------------------------+
| \( \mathrm{Inn}(G) \)                | Inner Automorphisms \ |
|                                      | \( \da \ts{ \varphi _g(x) \da gxg ^{-1} } \subseteq \Aut(G) \)  |
+--------------------------------------+---------------------------------------------------------------------------------------+
| \( \mathrm{Out}(G) \)                | Outer Automorphisms \ |
|                                      | \( \Aut(G) / \Inn(G) \mapsfrom \Aut(G) \) |
+--------------------------------------+---------------------------------------------------------------------------------------+
|  \( [g h] \)                         |  Commutator of Elements  \ |
|                                      |  \( \da ghg ^{-1} \in G \)  |
+--------------------------------------+---------------------------------------------------------------------------------------+
|  \( [G H] \)                         |  Commutator of Subgroups  \ |
|                                      |  \( \da \gens{ \ts{ [gh] \st g \in G,\, h \in H } } \leq G \)  |
+--------------------------------------+---------------------------------------------------------------------------------------+
|  \( \OO_x,\, Gx \)                   |  Orbit of an Element  \ |
|                                      |  \( \da \ts{ gx \st  x \in X} \)  |
+--------------------------------------+---------------------------------------------------------------------------------------+
|  \( \mathrm{Stab}_G(x),\, G_x \)     |  Stabilizer of an Element \ |
|                                      |  \( \da \ts{ g \in G \st gx = x } \subseteq G \)  |
+--------------------------------------+---------------------------------------------------------------------------------------+
|  \( X/G \)                           |  Set of Orbits  \ |
|                                      |  \( \da \ts{ G_x \st x \in X } \subseteq 2^X \)  |
+--------------------------------------+---------------------------------------------------------------------------------------+
|  \( X^g \)                           |  Fixed Points  \ |
|                                      |  \( \ts{x \in X \st \forall g \in G,\, gx = x} \subseteq X \)  |
+--------------------------------------+---------------------------------------------------------------------------------------+
|  \( 2^X \)                           |  The powerset of \( X \)   \ |
|                                      |  \( \da \ts{ U \subseteq X }  \)  |
+--------------------------------------+---------------------------------------------------------------------------------------+

- For any $p$ dividing the order of $G$, $\mathrm{Syl}_p(G)$ denotes the *set* of Sylow$\dash p$ subgroups of $G$.

## Definitions

:::{.fact}
An set morphism that is *either* injective or surjective between sets of the same size is automatically a bijection.
Consequently, a group morphism between groups of the same size that is either injective or surjective is automatically an isomorphism.

:::

:::{.fact title="The division algorithm"}
If $a, b\in \ZZ$ with $\gcd(a, b) = d$, then there exist $s,t\in \ZZ$ such that
\[
as + bt = d
.\]

:::

:::{.remark}
Useful context clue!
In particular, this works when $a, b$ are coprime and $d=1$.
If you see "coprime" in a finite group question, try the division algorithm.
:::

:::{.definition title="Subgroup Generated by a Subset"}
If $H\subset G$, then $\gens{H}$ is the smallest subgroup containing $H$:
\[
\gens{H} = \intersect \theset{H\suchthat H\subseteq M \leq G} M = \theset{ h_1^{\pm 1} \cdots h_n^{\pm 1} \suchthat n\geq 0, h_i \in H}
\]
where adjacent $h_i$ are distinct.
:::

:::{.definition title="Conjugacy class"}
The **conjugacy class** of $h$ is defined as 
\[
C(h) \da \ts{ ghg\inv \st g\in G } 
.\]
:::

:::{.remark}
$[e] = \ts{ e }$ is always in a conjugacy class of size one -- this is useful for counting and divisibility arguments.
Conjugacy classes are **not** subgroups in general, since they don't generally contain $e$.
However, by orbit-stabilizer and the conjugation action, their sizes always divide the order of $G$.
\

Also note that$[x] = \ts{ x } \iff x\in Z(G)$, i.e. having a trivial conjugacy class is the same as being central.
:::

:::{.definition title="Conjugate subgroups"}
Two subgroups $H, K \leq G$ are **conjugate** iff there exists some $g\in G$ such that $gHg\inv = K$.
Note that all conjugates have the same cardinality.
:::

:::{.definition title="Normal subgroup"}
A subgroup $N\leq G$ is **normal** iff $gH = Hg$ for every $g\in G$, or equivalently $gHg\inv = H$ for all $g$, so $H$ has only itself as a conjugate.
We denote this by $N\normal G$.
Equivalently, for every inner automorphism $\psi \in \Inn(G)$, $\psi(N) = N$.
:::

:::{.proposition title="Normal iff disjoint union of conjugacy classes"}
$N\normal G \iff N = \disjoint' [h_i]$ is a disjoint union of conjugacy classes, where the index set for this union is one $h_i$ from each conjugacy class.
:::

:::{.proof title="?"}
Note that $C(h_i) = \ts{ gh_i g\inv \st g\in G }$, and $gh_i g\inv \in H$ since $H$ is normal, so $C(h_i) \subseteq G$ for all $i$.
Conversely, if $C(h_i) \subseteq H$ for all $h_i \in H$, then $gh_ig\inv \in H$ for all $i$ and $H$ is normal.
:::

:::{.definition title="Centralizer"}
\[
C_G(H) = \theset{g\in G \suchthat ghg\inv = h ~\forall h\in H}
\]
These are elements that fix $H$ pointwise under the conjugation action.
:::

:::{.definition title="Normalizer"}
\[
N_G(H) = \theset{g\in G \suchthat gHg\inv = H} = \union \theset{H\suchthat H \normal M \leq G} M
\]
Contrast to the centralizer: these don't have to fix $H$ pointwise.
:::

:::{.remark}
$C_G(S) \normal N_G(H)$ for any $H$.
:::

:::{.definition title="Commutator"}
The **commutator subgroup** of $G$ is denoted $[G, G] \leq G$.
It is the subgroup generated by all elementary commutators:
\[
[G, G] \da \gens{ aba\inv b\inv \st a, b\in G } 
.\]

It is the smallest normal subgroup $N\normal G$ such that $G/N$ is abelian, so if $H\leq G$ and $G/H$ is abelian, $H\subseteq [G, G]$.
:::

:::{.definition title="Group Presentation"}
An expression of the form $G = \gens{S \st R}$ where $S$ is a set of elements and $R$ a set of words defining relations means that $G \da F[S] / \cl_n(R)$ where $F[S]$ is the free group on the set $S$ and $\cl_n(R)$ is the normal closure, the smallest normal subgroup of $F[S]$ containing $R$.
:::

:::{.remark}
Finding morphisms between presentations: if $G$ is presented with generators $g_i$ with relations $r_i$ and $H$ is any group containing elements $h_i$ also satisfying $r_i$, there is a group morphism
\[
\phi: G &\to H \\
g_i &\mapsto h_i \quad \forall i
.\]
Why this exists: the presentation yields a morphism $\pi: F(g_i) \to G$ with $G\cong F(g_i) / \ker \pi$.
Define a map $\psi: F(g_i) \to H$ where $g_i\mapsto h_i$, then since the $h_i$ satisfy the relations $r_i$, $\ker \pi \subseteq \ker \psi$.
So $\psi$ factors through $\ker \pi$ yielding a morphism $F/\ker \pi \to H$.
:::

:::{.proposition title="NC Theorem"}
$N_G(H) / C_G(H)$ is isomorphic to a subgroup of $\Aut(H)$.
:::

## Subgroups, Cosets, Quotients

:::{.definition title="Subgroup"}
A subset $H\subseteq G$ is a **subgroup** iff

1. Closure: $HH \subset H$
2. Identity: $e\in H$
3. Inverses: $g\in H \iff g\inv \in H$.
:::

:::{.proposition title="One-step subgroup test"}
If $H \subseteq G$ and $a,b\in H \implies ab\inv\in H$, then $H\leq G$.
:::

:::{.proof title="of the one-step subgroup test"}
\envlist

- Identity: $a=b=x\implies xx\inv=e\in H$
- Inverses: $a=e, b=x \implies x\inv \in H$.
- Closure: let $x, y\in H$, then $y\inv \in H$ by above, so $xy = x(y\inv )\inv \in H$.
:::

:::{.fact }
Coprime order subgroups are disjoint, or more generally $\ZZ_p, \ZZ_q \subset G \implies \ZZ_p \intersect \ZZ_q = \ZZ_{(p,q)}$.
:::

:::{.proposition title="Intersection of subgroups is a subgroup"}
If $H, K\leq G$ then $J \da H \intersect K \leq G$ is a subgroup.
Moreover $J\leq H$ and $J \leq K$.
:::

:::{.proof title="?"}
One-step subgroup test.
:::

:::{.proposition title="Tower law for subgroups"}
\[
K\leq H \leq G \implies [G: K] = [G:H] [H: K]
.\]
:::


:::{.proposition title="Indices grow"}
If $H, K \leq G$, then 
\[
[G: H \intersect K ]\leq [G: K] 
.\]
:::


## Cosets

:::{.proposition title="Cosets are identical or disjoint"}
Any two cosets $xH, yH$ are either identical or disjoint.
:::

:::{.proof title="?"}
Note $x\in xH$, since $e\in H$ because $H$ is a subgroup and we can take $h=e$ to get $x = xe \da xh \in xH$.
The reverse containment is clear, so $G = \union_{x\in G} xH$ is a union of its cosets.
Suppose toward a contradiction that $\ell \in xH \intersect yH$ we'll show $xH = yH$.
Write $\ell =xh_1 =yh_2$ for some $h_i$, then
\[
xh_1 = yh_2 &\implies x = yh_2 h_1\inv \\
xh_3\in xH &\implies xh_3 = (yh_2h_1\inv) h_3 \in yH
,\]
so $xH \subseteq yH$.
A symmetric argument shows $y_H \subseteq xH$.
[^df_p80_identical_disjoint]

[^df_p80_identical_disjoint]: 
See full argument: D&F p.80.

:::

:::{.theorem title="The Fundamental Theorem of Cosets"}
\[
aH = bH \iff a\inv b \in H \iff b\inv a\in H
.\]
:::

:::{.proof title="?"}
[^df_p80_identical_disjoint]
\[
aH = bH \iff a\in bH \iff a=bh \text{ for some } h \iff b\inv a = h \iff ba\inv \in H
.\]
:::

:::{.definition title="Index of a subgroup"}
The **index** $[G: H]$ of a subgroup $H\leq G$ is the number of left (or right) cosets $gH$.
:::

:::{.remark title="Common coset trick"}
If you can reduce a problem to showing $X \subseteq H$, it suffices to show $xH = H$ for all $x\in X$.
:::

:::{.remark}
Cosets form an equivalence relation and thus partition a group.
Nice trick: write $G/H = \ts{ g_1 H, g_2 H,\cdots, g_n H }$, then $G = \disjoint_{i\leq n} g_i H$.
:::

:::{.theorem title="Counting Cosets"}
If $H\normal G$, then
\[
[G: H] = \abs{G/H} = {\abs G \over \abs H}
.\]
:::


## Special Classes of Groups

:::{.definition title="The Dihedral Group"}
A **dihedral group** of order $2n$ is given by 
\[
D_n = \gens{r, s \suchthat r^n, s^2, rsr\inv = s\inv } = \gens{r, s \st r^n, s^2, (rs)^2 }
\]
:::

:::{.definition title="The Quaternion Group"}
The **Quaternion group** of order 8 is given by
\[
Q &= \gens{x,y,z \suchthat x^2 = y^2 = z^2 = xyz = -1} \\
  &= \gens{x, y \suchthat  x^4 = y^4, x^2 = y^2, yxy\inv = x\inv}
\]
Mnemonic: multiply clockwise to preserve sign, counter-clockwise to negate sign.
Everything squares to $-1$, and the triple product is $-1$:

\begin{tikzcd}
	&& {-1} \\
	\\
	&& i \\
	\\
	\\
	k &&& {} & j
	\arrow["{ki=j}"', from=3-3, to=6-5]
	\arrow["{ij=k}"', from=6-5, to=6-1]
	\arrow["{jk=i}"', from=6-1, to=3-3]
	\arrow["{ik=-j}"', curve={height=30pt}, dashed, from=6-1, to=6-5]
	\arrow["{kj=-i}"', curve={height=30pt}, dashed, from=6-5, to=3-3]
	\arrow["{ji=-k}"', curve={height=30pt}, dashed, from=3-3, to=6-1]
	\arrow["{ijk=-1}"', from=3-3, to=1-3]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsNSxbMiwyLCJpIl0sWzMsNV0sWzAsNSwiayJdLFs0LDUsImoiXSxbMiwwLCItMSJdLFswLDMsImtpPWoiLDJdLFszLDIsImlqPWsiLDJdLFsyLDAsImprPWkiLDJdLFsyLDMsImlrPS1qIiwyLHsiY3VydmUiOjUsInN0eWxlIjp7ImJvZHkiOnsibmFtZSI6ImRhc2hlZCJ9fX1dLFszLDAsImtqPS1pIiwyLHsiY3VydmUiOjUsInN0eWxlIjp7ImJvZHkiOnsibmFtZSI6ImRhc2hlZCJ9fX1dLFswLDIsImppPS1rIiwyLHsiY3VydmUiOjUsInN0eWxlIjp7ImJvZHkiOnsibmFtZSI6ImRhc2hlZCJ9fX1dLFswLDQsImlqaz0tMSIsMl1d)

:::

:::{.definition title="Transitive Subgroup"}
A subgroup of $S_n$ is **transitive** iff its action on $\theset{1, 2, \cdots, n}$ is transitive. 
:::

### Cyclic Groups

:::{.theorem title="Subgroups of Cyclic Groups"}
$G$ is cyclic of order $n \da \# G$ iff $G$ has a unique subgroup of order $d$ for each $d$ dividing $n$.
:::


:::{.proof title="?"}
$\impliedby$:
Use that $\sum_{d\divides n} \phi(d) = n$, and that there are at most $\phi(d)$ elements of order $d$, forcing equality.

$\implies$:
If $G = \gens{ a }$ with $a^n=e$, then for each $d\divides n$ take $H_d \da \gens{ a^{n\over d} }$ for existence.
:::



### The Symmetric Group


:::{.definition title="The symmetric group"}
The transposition presentation:
\[
S_n \da \gens{ \sigma_1, \cdots, \sigma_{n-1} \st \sigma_i^2, [\sigma_i, \sigma_j]\, (j\neq i+1), \sigma_i \sigma_{i+1} \sigma_i = \sigma_{i+1} \sigma_i \sigma_{i+1} } 
.\]

:::


:::{.definition title="The sign homomorphism"}
Defined by the map
\[
\sgn: S_n &\to (\ZZ/2, +) \\
\prod_{i\leq 2k} (a_i b_i) &\mapsto 0 \\
\prod_{i\leq 2k+1} (a_i b_i) &\mapsto 1
.\]

- The kernel is the alternating group, cycles that 
  - **Even** cycles
  - For a single cycle: has **odd** length
  - Have an **even** number of even length cycles.
  - Can be written as an **even** number of transpositions
- The fiber over 1 is everything else:
  - **Odd** cycles
  - For a single cycle: has **even** length
  - Have an **odd** number of even length cycles.
  - Can be written as an **odd** number of transpositions

> Mnemonic: the cycle parity of a $k\dash$cycle is the integer parity of $k-1$.

:::

:::{.definition title="Alternating Group"}
The **alternating group** is the subgroup of **even** permutations, i.e.
\[
A_n \definedas \theset{\sigma \in S_n \suchthat \sgn(\sigma) = 0}
\] 
:::

:::{.proposition title="$A_n$ is generated by 3-cycles"}
For $n\geq 3$, $A_n$ is generated by 3-cycles.
:::

:::{.proof title="?"}
Every 3-cycle $(abc)$ is even, and thus in $A_n$.
Given an arbitrary even permutation $(t_1\ldots t_{2k})$, it decomposes into a product of an odd number of transpositions $(t_{2j-1} t_{2j})$.
So it suffices to write every such transposition as a 3-cycle.
There are only 3 cases the occur:

- $(ab)(ab) = ()$
- $(ab)(ac) = (abc)$
- $(ab)(cd) = (abc)(adc)$.

:::

:::{.example title="Of an explicit alternating group"}
\[
A_4 =
& \{\id, \\
& (1,3)(2,4),
(1,2)(3,4),
(1,4)(2,3), \\
& (1,2,3),
(1,3,2), \\
& (1,2,4),
(1,4,2), \\
& (1,3,4),
(1,4,3), \\
& (2,3,4),
(2,4,3) \}
\]
:::

:::{.fact title="Some useful facts"}
\envlist

- $\sigma \circ (a_1 \cdots a_k)\circ \sigma^{-1} = (\sigma(a_1), \cdots \sigma(a_k))$
- Conjugacy classes are determined by cycle type
- The order of a cycle is its length.
- The order of an element is the least common multiple of the sizes of its disjoint cycles.
- Disjoint cycles commute.
- $A_{n\geq 5}$ is *simple*.

:::



## Exercises

- Prove that the size of a conjugacy class of $g_i$ is the index of its centralizer, $[G: Z(g_i)] \da [G: C_G(g_i)]$.
- Prove that if $G$ is a $p\dash$group, every normal subgroup $N\normal G$ intersects the center $Z(G)$.
- Show that if $G$ is a finite group acting transitively on a set $X$ with at least two elements,
then there exists $g \in G$ which fixes no point of $X$.
- Let $p$ be prime.
  For each abelian group $K$ of order $p^2$, how many subgroups $H\leq \ZZ^{\times 3}$ are there with $\ZZ^3/H \cong K$?
- Let $\# G = pq$, with $p,q$ distinct primes.
  Show that $G$ has a nontrivial proper normal subgroup, and if $p\not\equiv 1\mod q$ and $q\not \equiv 1 \mod p$ then $G$ is abelian.

- Let $G$ be a finite group and let $p$ be the smallest prime dividing $\# G$, and assume $G$ has a normal subgroup of order $p$.
  Show that $H \subset Z(G)$.

- Let $G$ be finite and $P$ a Sylow 2-subgroup.
  Assume $P$ is cyclic and generated by $x$.
  Show that the sign of the permutation of $G$ corresponding to $x\mapsto gx$ is 1, and deduce that $G$ has a nontrivial quotient of order 2.

