# Appendix: Extra Topics

:::{.proposition title="NC Theorem"}
$N_G(H) / C_G(H)$ is isomorphic to a subgroup of $\Aut(H)$.
:::

:::{.definition title="Normalizers Grow"}
If for every proper $H < G$, $H\normal N_G(H)$ is again proper, then "normalizers grow" in $G$.
:::

## Characteristic Subgroups

:::{.slogan}
Normality is not transitive!

I.e. if $H\normal G$ and $N\normal H$, it's not necessarily the case that $N\normal G$.
:::

:::{.definition title="Characteristic Subgroups"}
A subgroup $H\leq G$ is **characteristic** in $G$, written $H \ch G$, iff for every $\phi \in \Aut(G)$, $\phi(H) \leq H$.
Equivalently, $\phi(H) = H$.
I.e. $H$ is fixed (not necessarily pointwise) under every automorphism of the ambient group $G$.
:::

:::{.remark title="Characteristic isn't equivalent to normalcy"}
Characteristic subgroups are normal, because $\psi_g(\wait) \da g(\wait)g\inv$ is an (inner) automorphic of $G$.
Not every normal subgroup is characteristic: take $G \da H_1 \cross H_2$ and $\psi(x, y) = (y, x)$.
:::

:::{.proposition title="Fixing transitivity of normality"}
Characteristic subgroups of normal subgroups are normal, i.e. if $H\normal G$ and $N \ch H$, then $N\normal G$.
:::

:::{.proof title="?"}
$A \ch B \normal C \implies A\normal C$:

- $A\ch B$ iff $A$ is fixed by every $\psi\in \Aut(B)$., WTS $cAc\inv = A$ for all $c\in C$.
- Since $B\normal C$, the automorphism $\psi(\wait) \da c(\wait)c\inv$ descends to an element of $\Aut(B)$.
- Then $\psi(A) = A$ since $A\ch B$, so $cAc\inv = A$ and $A\normal C$.
:::

:::{.proposition title="Centers are characteristic"}
For any group $G$,
\[
Z(G) \ch G
.\]
:::

:::{.proof title="?"}
Let $\psi \in \Aut(H)$ and $x=\psi(y)\in \psi(Z(H))$ so $y\in Z(H)$, then for arbitrary $h\in H$,
\[
\psi(y)h 
&= \psi(y) (\psi \circ \psi\inv)(h) \\
&= \psi( y \cdot \psi\inv(h) ) \\
&= \psi( \psi\inv(h) \cdot y ) && \text{since } \psi\inv(h)\in H, \, y\in Z(H) \\
&= h\psi(y)
.\]
:::

## Normal Closures and Cores

:::{.definition title="Normal Closure of a Subgroup"}
The smallest normal subgroup of $G$ containing $H$:
\[
H^G \definedas \{gHg^{-1}: g\in G\} = \bigcap \theset{N: H \leq N \normal G }
.\]
:::

:::{.definition title="Normal Core of a subgroup"}
The largest normal subgroup of $G$ containing $H$:
\[
H_G = \Intersect_{g\in G} gHg^{-1} = \gens{ N: N \normal G ~\&~ N \leq H} = \ker \psi
.\]
where
\[
\psi: G &\to \Aut(G/H) \\
g &\mapsto (xH\mapsto gxH)
\]
:::

:::{.theorem title="Fratini's Argument"}
If $H\normal G$ and $P \in \mathrm{Syl}_p(G)$, then $H N_G(P) = G$ and $[G: H]$ divides $\abs{N_G(P)}$.
:::

### Exercises

:::{.exercise title="?"}
Show that $Z(G) \leq G$ is always characteristic.
:::

:::{.solution}
Let $\psi\in \Aut(G)$.
For one containment, we can show $\psi(g) = h = h\psi(g)$ for all $\psi(g) \in \psi(G)$ and $h\in G$.
This is a computation:
\[
\psi(g) h 
&= \psi(g) (\psi \psi\inv)(h) \\
&= \psi( g ) \psi( \psi \inv (h)) \\
&= \psi( \psi\inv(h) g) \\
&= (\psi\psi\inv)(h) \psi(g) \\
&= h\psi(g)
.\]
This yields $\psi(Z(G)) \subseteq Z(G)$.
Applying the same argument to $\psi\inv$ yields $\psi\inv(Z(G)) \subseteq Z(G)$.
Since $\psi$ is a bijection, $\psi\psi\inv(A) = A$ for all $A\leq G$, 
so $Z(G) \subseteq \psi(Z(G))$.

:::

## Nilpotent Groups

:::{.definition title="Nilpotent"}
A group $G$ is **nilpotent** iff $G$ has a terminating upper central series.
:::

> Moral: the adjoint map is nilpotent.

:::{.theorem title="Characterization of Nilpotent Groups"}
$G$ is nilpotent iff $G$ has an upper central series terminating at $G$.
:::

:::{.theorem title="Characterization of Nilpotent Groups"}
$G$ is nilpotent iff $G$ has a lower central series terminating at $1$.
:::

:::{.theorem title="Nilpotents Have All Sylows Normal"}
A group $G$ is nilpotent iff all of its Sylow $p\dash$subgroups are normal for every $p$ dividing $\abs{G}$.
:::

:::{.theorem title="Nilpotent Implies Maximal Normals"}
A group $G$ is nilpotent iff every maximal subgroup is normal.
:::

:::{.proposition}
For $G$ a finite group, TFAE:

- $G$ is nilpotent
- Normalizers grow, i.e. if $H < G$ is proper then $H < N_G(H)$.
- Every Sylow-p subgroup is normal
- $G$ is the direct product of its Sylow p-subgroups
- Every maximal subgroup is normal
- $G$ has a terminating *Lower* Central Series
- $G$ has a terminating *Upper* Central Series
:::

:::{.fact}
\envlist

- Nilpotent groups satisfy the 2 out of 3 property.\todo{Todo. Specify.}
- $G$ has normal subgroups of order $d$ for *every* $d$ dividing $\abs{G}$

:::

## Rings

:::{.definition title="Gorenstein Rings"}
A commutative Noetherian ring $R$ is **Gorenstein** iff $R$ viewed as an $R\dash$module has finite injective dimension.
:::

:::{.example title="Why care about Gorenstein rings?"}
If $R\in \gr\kAlg$ with $\dim_k R < \infty$, then $R$ decomposes as $R = R_0 \oplus R_1 \oplus \cdots R_n$ with $R_0 \da k$, and $R$ is Gorenstein iff $R$ satisfies "Poincaré duality": $\dim_k R_0 = \dim_k R_m = 1$ and there is a perfect pairing $R_i \tensor_k R_{n-j} \to R_n$.
:::

