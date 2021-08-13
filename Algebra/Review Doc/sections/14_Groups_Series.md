## Series of Groups

:::{.definition title="Normal Series"}
A **normal series** of a group $G$ is a sequence $G \to G^1 \to G^2 \to \cdots$ such that $G^{i+1} \normal G_i$ for every $i$.
:::

:::{.definition title="Central Series"}
A **central series** for a group $G$ is a terminating normal series $G \to G^1 \to \cdots \to \theset{e}$ such that each quotient is **central**, i.e. $[G, G^i] \leq G^{i-1}$ for all $i$.
:::

:::{.definition title="Composition Series"}
A **composition series** of a group $G$ is a finite normal series such that $G^{i+1}$ is a *maximal proper* normal subgroup of $G^i$.
:::

:::{.theorem title="Jordan-Holder"}
Any two composition series of a group have the same length and isomorphic composition factors (up to permutation).
:::

:::{.definition title="Simple Groups"}
A group $G$ is **simple** iff $H\normal G \implies H = \theset{e}, G$, i.e. it has no non-trivial proper subgroups.
:::

:::{.proposition}
If $G$ is *not* simple, then $G$ is an extension of any of its normal subgroups.
I.e. for any $N\normal G$, $G \cong E$ for some extension of the form $N\to E\to G/N$.
:::

:::{.definition title="Lower Central Series"}
Set $G^0 = G$ and $G^{i+1} = [G, G^i]$, then $G^0 \geq G^1 \geq \cdots$ is the *lower central series* of $G$.
:::

> Mnemonic: "lower" because the chain is descending.
> Iterate the adjoint map $[\wait, G]$, if this terminates then the map is nilpotent, so call $G$ nilpotent!

:::{.definition title="Upper Central Series"}
Set $Z_0 = 1$, $Z_1 = Z(G)$, and $Z_{i+1} \leq G$ to be the subgroup satisfying $Z_{i+1}/Z_i = Z(G/Z_i)$.
Then $Z_0 \leq Z_1 \leq \cdots$ is the *upper central series* of $G$.

Equivalently, since $Z_i\normal G$, there is a quotient map $\pi:G\to G/Z_i$, so define $Z_{i+1} \definedas \pi\inv(Z(G/Z_i))$ (?).

> Mnemonic: "upper" because the chain is ascending. "Take higher centers".

:::

:::{.definition title="Derived Series"}
Set $G^{(0)} = G$ and $G^{(i+1)} = [G^{(i)}, G^{(i)}]$, then $G^{(0)} \geq G^{(1)} \geq \cdots$ is the *derived series* of $G$.
:::

## Solvability


:::{.remark}
A useful way to extract normal subgroups: let $G$ act on literally anything by $\phi: G\to \Aut(X)$.
Then $\ker \phi \normal G$ is always a normal subgroup.
Some examples:

- $G\actson G$ by $x\mapsto gx$.
- $G\actson \ts{H\leq G}$ by $H\mapsto gH$ or $H\mapsto gHg\inv$.
- $G\actsons \ts{\Syl_p(G)}$ for a fixed $p$ by $S_p \mapsto gS_p g\inv$.
- $G\actson H$ for $H\normal G$ by inner automorphisms $h\mapsto ghg\inv$.
:::


:::{.definition title="Solvable"}
A group $G$ is **solvable** iff $G$ has a terminating normal series with abelian composition factors, i.e.
\[
G \da G_n > G_{n-1} > \cdots > G_2 > G_1 \da \ts{ e } && \text{ with } G^{i}/G^{i+1}\text{ abelian for all } i
.\]
:::

:::{.remark}
If $G = \Gal(L/K)$ is a Galois group corresponding to a polynomial $f$, then $G$ is solvable as a group iff $f$ is solvable in radicals: 
there is a tower of extensions $K = F_0 \subset F_1 \subset F_2 \subset \cdots \subset F_m = L$ where

1. $F_i = F_{i-1}(\alpha_i)$ where \( \alpha_i^{m_i } \in F_{i-1} \) for some power $m_i \in \ZZ^{\geq 0}$, and 
2. $F_m \supseteq \SF(f)$ contains a splitting field for $f$.
:::

:::{.theorem title="Characterization of Solvable"}
A group $G$ is solvable iff its derived series terminates.
:::

:::{.theorem title="$S_n$ is Almost Always Solvable"}
If $n\geq 4$ then $S_n$ is solvable.
:::

:::{.fact}
Some useful facts about solvable groups:

- $G$ is solvable iff $G$ has a terminating *derived series*.
- Solvable groups satisfy the 2 out of 3 property
- Abelian $\implies$ solvable
- Every group of order less than 60 is solvable.
:::





