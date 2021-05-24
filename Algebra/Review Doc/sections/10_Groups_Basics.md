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



:::{.definition title="Subgroup Generated by a Subset"}
If $H\subset G$, then $\gens{H}$ is the smallest subgroup containing $H$:
\[
\gens{H} = \intersect \theset{H\suchthat H\subseteq M \leq G} M = \theset{ h_1^{\pm 1} \cdots h_n^{\pm 1} \suchthat n\geq 0, h_i \in H}
\]
where adjacent $h_i$ are distinct.
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

:::{.definition title="Centralizer"}
\[
C_G(H) = \theset{g\in G \suchthat ghg\inv = h ~\forall h\in H}
\]
:::

:::{.definition title="Normalizer"}
\[
N_G(H) = \theset{g\in G \suchthat gHg\inv = H} = \union \theset{H\suchthat H \normal M \leq G} M
\]
:::

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

:::{.proposition title="The division algorithm"}
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



## Subgroups and Quotients

:::{.fact }
Coprime order subgroups are disjoint, or more generally $\ZZ_p, \ZZ_q \subset G \implies \ZZ_p \intersect \ZZ_q = \ZZ_{(p,q)}$.
:::

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

:::{.remark title="Common coset trick"}
If you can reduce a problem to showing $X \subseteq H$, it suffices to show $xH = H$ for all $x\in X$.
:::

:::{.theorem title="Counting Quotients"}
If $H\normal G$, then
\[
[G: H] = \abs{G/H} = {\abs G \over \abs H}
.\]
:::

:::{.theorem title="Counting by Towers"}
\[
[G:K] = [G:H]\, [H:K]
.\]
:::

## Special Classes of Groups

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


## Counting Theorems

:::{.theorem title="Lagrange's Theorem"}
\[H \leq G \implies \# H \divides \# G.\]
Moreover, there is an equality $[G:H] = \# G/ \# H$ when $G$ is finite.
:::

:::{.proof title="of Lagrange's theorem"}
Write $G/H = \ts{g_0 H, g_1 H, \cdots, g_N H}$ for some $N \da [G:H]$.
Since cosets are equal or disjoint and have equal cardinality, 
\[
G = \disjoint_{k \leq N} g_k H \implies \#G = \sum_{k\leq N} \# \qty{g_k H} = \sum_{k\leq N} \# H = N \# H
,\]
so $\# G = N \# H$, $\#H$ divides $\# G$ and $N = [G:H]$ divides $\# G$.
:::


:::{.corollary title="?"}
\[
\# G = \#(G/H) \#H \da [G:H] \, \# H
,\]
or written another way,
\[
\#(G/H) = \# G/ \# H
.\]
:::

:::{.corollary}
The order of every element divides the size of $G$, i.e.
$$
g\in G \implies o(g) \divides o(G) \implies g^{\abs G} = e
.$$
:::

:::{.warnings}
There do **not** necessarily exist $H \leq G$ with $\abs H = n$ for every $n \divides \abs{G}$.
Counterexample: take $G = A_5$, then $\# G = 5!/2 = 60$ but $G$ has no subgroup of order $30$.
If it did, this would be index 2 and thus normal, but $A_{n\geq 5}$ is simple.

Another direct counterexample: $\abs{A_4} = 12$ but has no subgroup of order 6.
If such an $H$ existed, it can't contain every 3-cycle, since $A_4$ is generated by 3-cycles.
For $x$ any 3-cycle *not* in $H$, use that $\# A_4/H = 2$ and consider $H, xH, x^2H$.
$x\not\in H$, so $H\neq xH$, but two must be equal:

- $x^2H = H$: use $x^2 = x\inv$ since $x^3=e$, but $x\in H \implies x\inv\in H$, $\contradiction$
- $xH = x^2H$: the fundamental theorem of cosets forces $x\inv x^2 \in H$, so $x\in H$. $\contradiction$
:::


:::{.theorem title="Cauchy's Theorem"}
For every prime $p$ dividing $\abs{G}$. there is an element (and thus a subgroup) of order $p$.

> This is a partial converse to Lagrange's theorem, and strengthened by Sylow's theorem.

:::


:::{.proof title="?"}
See [https://kconrad.math.uconn.edu/blurbs/grouptheory/cauchypf.pdf](https://kconrad.math.uconn.edu/blurbs/grouptheory/cauchypf.pdf).
:::



### Group Actions

:::{.definition title="Group Action"}
An action of $G$ on $X$ is a group morphism
\[
\phi:G \times X &\rightarrow X \\ 
(g,x) &\mapsto g x
\]
or equivalently
\[
\phi: G &\to \Aut(X) \\
g &\mapsto (x \mapsto \phi_g (x) \definedas g\cdot x)
\]
satisfying

1. $e\cdot x = x$
2. $g\cdot (h\cdot x) = (gh)\cdot x$
:::

:::{.fact}
For any group action, the kernel is the intersection of all stabilizers:
\[
\ker \psi = \Intersect_{x\in X} G_x
.\]
:::

:::{.definition title="Transitive Group Action"}
A group action $G\actson X$ is **transitive** iff for all $x, y\in X$ there exists a $g\in G$ such that $g\cdot x = x$.
Equivalently, the action has a single orbit.
:::


:::{.proposition title="Orbit Stabilizer Isomorphism"}
If $G\actson X$ transitively, then for any choice of $x\in X$ there is an isomorphism of sets given by
\[
\Phi: G/G_{x} &\mapsvia{\sim} X \\
gG_{x} &\mapsto g\actson x
.\]
:::


:::{.proof title="?"}
\envlist

- Injectivity: $\Phi(gG_x) = \Phi(hG_x) \iff g\actson x=h\actson x \iff gh\inv \actson x = x \iff gh\inv \in G_x \iff gG_x = hG_x$.

- Well-definedness: use $gG_x = hG_x \iff gh\inv \in G_x \iff g\inv h \actson x = x$.
  Then $g (g\inv h) \actson x = g \actson x$ on one hand, and on the other $(gg\inv)h\actson x = h\actson x$, so
  \[
  \Phi(hG_x) \da h\actson x = (gg\inv) h\actson x = g(g\inv h)\actson x = g\actson x = \Phi(gG_x)
  .\]

- Surjectivity: equivalent to the action being transitive.

:::


:::{.proposition title="?"}
If $X\in \GSets$ where $G\actson X$ transitively, then for any points $x_i\in X$, the stabilizers $G_{x_0}$ and $G_{x_1}$ are conjugate.
:::

\todo[inline]{Prove}


:::{.proof title="?"}
\envlist

- Injectivity: check that $\phi(\bar{g}) = \phi(\bar{h}) \iff g\actson x_0 = h\actson x_0 \iff gh\inv \in G_{x_0}$.
- Surjectivity: follows from transitivity.
:::


:::{.remark title="Reminder of notation"}
For a group $G$ acting on a set $X$,

+-----------------------------------------------------------------+---------------+
|  Notation                                                       |  Definition   |
+=================================================================+===============+
| \( \OO(x) = G\cdot x = \theset{g\cdot x \suchthat g\in G} \subseteq X \) |  Orbit        |
+-----------------------------------------------------------------+---------------+
| \(\Stab(x) = G_x = \ts{ g \in G \st gx=x } \leq G \)                       | Stabilizer    |
+-----------------------------------------------------------------+---------------+
| \( X/G \subseteq 2^X \)                                         | Set of Orbits |
+-----------------------------------------------------------------+---------------+
| \( \Fix(G) = X^G = \theset{x\in X \suchthat g\cdot x = x\, \forall g\in G} \subseteq X \)  | Fixed Points  |
+-----------------------------------------------------------------+---------------+

Note that being in the same orbit is an equivalence relation which partitions $X$, and $G$ acts transitively if restricted to any single orbit.
:::



:::{.theorem title="Orbit-Stabilizer"}

\[\# {Gx} = [G: G_x] = \# {G} / \#{G_x} \quad \text{if $G$ is finite}
.\]

> Mnemonic: $G/G_x \cong Gx$.

:::


### Examples of Orbit-Stabilizer and the Class Equation

:::{.example title="Trivial"}
Let $G$ act on itself by left translation, where $g \mapsto (h\mapsto gh)$.

- The orbit $\OO_x = Gx = G$ is the entire group.
  - This action is transitive.
- The set of fixed points \( \Fix(G) = \ts{ e } \) is just the identity.
- The stabilizer \( G_x = \ts{ e } \) is only the identity.
- The kernel is the identity.


:::


#### The Class Equation and Burnside's Lemma

:::{.example title="Conjugation yields centers/centralizers"}
Let $G$ act on *itself* by conjugation.

- The orbit $\OO(g) = C(g)$ is the **conjugacy class** of $x$.
  - Thus the action is transitive iff there is one conjugacy class.
- The set of fixed points $\Fix(G) = Z(G)$ is the **center**.
- The stabilizer is $\Stab(g) = Z(g) = C_G(g)$, the **centralizer** of $g$.
- The kernel is the intersection of all centralizers, i.e. the **center** $Z(G)$.


:::

:::{.remark}
Note that $[G: C_G(x_i)]$ is the number of elements in the conjugacy class of $x_i$, and each $x_i \in Z(G)$ has a singleton conjugacy class.
:::

:::{.corollary}
Directly interpreting this using the orbit-stabilizer formula, the size of a conjugacy class $C(x)$ is the index of its centralizer, $[G: C_G(x)]$, i.e.
\[
\# {C(x)} = [G: Z(x)]
.\]

:::

:::{.corollary title="The Class Equation"}
\[
\abs{G} = \abs{Z(G)} + \sum_{\substack{\text{One $g$ from} \\ \text{each nontrivial} \\ \text{conj. class}}} [G: Z(g)]
\]
:::

:::{.proof title="of the class equation"}
$G$ is a disjoint union of its conjugacy classes, so $G = \Disjoint'_{g\in G} C(g)$ where $\disjoint'$ denotes taking one representative from each conjugacy class.
Thus 
\[
\# G = \Sum'_{g\in G} \# C(g) = \Sum'_{g\in G} [G: Z(g)]
.\]
Elements $g \in Z(g)$ in the center satisfy $Z(g) = \ts{ e }$ and $[G: Z(g)] = 1$ since $Z(g) = G$, so pulling these out of the sum yields
\[
\# G 
&= \Sum'_{\substack{g\in G' \\ \# [G:Z(g)] = 1 }} [G: Z(g)] +  \Sum'_{\substack{g\in G \\ [G:Z(g)] > 1} } [G: Z(g)] \\
&= \Sum'_{\substack{g\in G' \\ \# [G:Z(g)] = 1 }} 1 +  \Sum'_{\substack{g\in G \\ [G:Z(g)] > 1} } [G: Z(g)] \\
&= \# Z(G) +  \Sum'_{\substack{g\in G \\ [G:Z(g)] > 1} } [G: Z(g)]
.\]

:::

:::{.proposition title="Application of the Class Equation"}
If $G$ is simple, $H < G$ proper, and $[G:H] = n$, then there exists an injective map $\phi: G \injects S_n$.
:::

:::{.proof}
This action induces $\phi$; it is nontrivial since $gH = H$ for all $g$ implies $H = G$; $\ker \phi \normal G$ and $G$ simple implies $\ker \phi = 1$.
:::

:::{.corollary title="Burnside's Lemma"}
For $G$ a finite group acting on $X$, 
\[
\# {X/G} = \frac{1}{\# G }\sum_{g\in G} \# {X^g}
\]

> Mnemonic: the number of orbits is equal to the average number of fixed points, i.e.

:::

:::{.proof title="of Burnside's Lemma"}
Strategy: form the set $A \da \ts{ (g,x) \in G\cross X \st g\actson x = x }$ and write/count it in two different ways.
First union over $G$:
\[
A = \Disjoint_{g\in G} \ts{ (g, x) \st gx = x } \cong \Disjoint_{g\in G} \ts{g}\cross X^g
.\]

Then union over $X$:
\[
A = \Disjoint_{x\in X} \ts{ (g, x) \st gx= x } \cong \Disjoint_{x\in X} G_x \cross \ts{ g } 
.\]
Taking cardinalities, and using the fact that $\ts{p} \cross A \cong  A$ as sets for any set $A$,
\[
\Disjoint_{g\in G} X^g
\cong
\Disjoint_{x\in X} G_x
\implies 
\sum_{g\in G}\# X^g
=
\sum_{x\in X} \# G_x
.\]
Apply orbit-stabilizer:
\[
\# G_x = {\# G \over \# Gx} \implies
\sum_{g\in G} X^g
&= \sum_{x\in X} \# G_x \\
&= \sum_{x\in X} {\# G \over  \# Gx} \\
&= \# G\sum_{x\in X} {1 \over  \# Gx}
,\]
so it suffices to show $\sum_{x\in X}{1\over \# Gx} = \# X/G$.
Proceed by grouping terms in this sum according to which orbit they're in:
\[
\sum_{x\in X} {1\over \# Gx} 
&=
\sum_{Gx \in X/G} \sum_{y\in Gx} {1\over \# Gx} \\
&=
\sum_{Gx \in X/G} {1\over \# Gx} \sum_{y\in Gx} 1 \\
&=
\sum_{Gx \in X/G} {1\over \# Gx} \# G_x \\
&=
\sum_{Gx \in X/G} 1 \\
&= \# X/G
.\]

:::


#### Conjugation on Subgroups

:::{.example title="?"}
Let $G$ act on $X \da\ts{H \st H\leq G}$ (its set of *subgroups*) by conjugation.

- The orbit $\OO(H) = \theset{gHg\inv \st g\in G}$ is the **set of conjugate subgroups** of $H$.
  - This action is transitive iff all subgroups are conjugate.
- The fixed points $\Fix(G)$ form the set of **normal subgroups** of $G$.

- The stabilizer $\Stab(H) = N_G(H)$ is the **normalizer** of $H$ in $G$.

- The kernel is the intersection of all normalizers.

:::

:::{.corollary}
Given $H \leq G$, the number of conjugate subgroups is $[G: N_G(H)]$, i.e.
\[
\abs{\ts{ gHg ^{-1} \st g \in G } } = [G: N_G(H)]
.\]

:::

#### Left Translation on Cosets

:::{.example title="?"}
For a fixed proper subgroup $H< G$, let $G$ act on its cosets $X \da G/H \da \theset{gH\suchthat g\in G}$ by left translation.

- The orbit $\OO(xH) = G/H$, the entire set of cosets.

  - Note that this is a *transitive* action.

- The stabilizer $\Stab(xH) = xHx\inv$, a **conjugate subgroup** of $H$

- The fixed points form $\Fix(G) = \emptyset$.

- The kernel of this action is $\Intersect_{g\in G} gHg\inv$, the intersection of all conjugates of $H$.

:::

:::{.proposition title="Application of translation action on cosets"}
If $G$ is a finite group and $p\da [G:H]$ is the smallest prime dividing $\# G$, then $H\normal G$.
:::

:::{.proof title="?"}
\envlist

- Let $\phi: G\actson X\da \ts{xH}$, noting that $\# X = p$ and $\Sym(X) \cong S_p$.
- Then $K\da \ker \phi \subseteq H$.
- Since $G$ is finite and $K\leq G$, we have $[G:K] = \# (G/K) = \# G/ \# K$ so $\# (G/K)$ divides $\# G$.
- Since $G/K \cong K'$ is isomorphic to a subgroup of $S_p$, $\# (G/K)$ divides $\# S_p = p!$
- So $\# (G/K)$ divides $\gcd( \# G, p!)$, which is $p$ since it was the minimal prime dividing $\# G$.
- $p$ is prime, so if $\# G/K\neq 1$ we have $\# G/K = p$.
- Since $K \subset H$ and $[G:H] = p = [G: K]$, we have $K = H$.
- But $K = \ker \phi \normal G$, so $H\normal G$.

:::


## Exercises

- Prove that the size of a conjugacy class of $g_i$ is the index of its centralizer, $[G: Z(g_i)] \da [G: C_G(g_i)]$.


