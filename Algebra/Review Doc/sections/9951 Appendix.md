# Appendix: Extra Topics

## Characteristic Subgroups

:::{.definition title="Normal Closure of a Subgroup"}
The smallest normal subgroup of $G$ containing $H$:
\[
H^G \definedas \{gHg^{-1}: g\in G\} = \bigcap \theset{N: H \leq N \normal G }
.\]
:::

:::{.definition title="Normal Core of a subgroup"}
The largest normal subgroup of $G$ containing $H$:
\[
H_G = \intersect_{g\in G} gHg^{-1} = \gens{ N: N \normal G ~\&~ N \leq H} = \ker \psi
.\]
where
\[
\psi: G &\to \Aut(G/H) \\
g &\mapsto (xH\mapsto gxH)
\]
:::

:::{.definition title="Characteristic subgroup"}
$H\leq G$ is *characteristic* iff $H$ is fixed by every element of $\Aut(G)$. 
:::


:::{.theorem title="Fratini's Argument"}
If $H\normal G$ and $P \in \mathrm{Syl}_p(G)$, then $H N_G(P) = G$ and $[G: H]$ divides $\abs{N_G(P)}$.
:::

## Nilpotent Groups

:::{.definition title="Nilpotent"}
A group $G$ is **nilpotent** iff $G$ has a terminating upper central series.
:::

> Moral: the adjoint map is nilpotent.

:::{.theorem title="Nilpotents Have All Sylows Normal"}
A group $G$ is nilpotent iff all of its Sylow $p\dash$subgroups are normal for every $p$ dividing $\abs{G}$.
:::

:::{.theorem title="Nilpotent Implies Maximal Normals"}
A group $G$ is nilpotent iff every maximal subgroup is normal.
:::

:::{.theorem title="Characterization of Nilpotent Groups"}
$G$ is nilpotent iff $G$ has an upper central series terminating at $G$.
:::

:::{.theorem title="Characterization of Nilpotent Groups"}
$G$ is nilpotent iff $G$ has a lower central series terminating at $1$.
:::

:::{.proposition}
For $G$ a finite group, TFAE:

- $G$ is nilpotent
- Normalizers grow (i.e.$H < N_G(H)$ whenever $H$ is proper)
- Every Sylow-p subgroup is normal
- $G$ is the direct product of its Sylow p-subgroups
- Every maximal subgroup is normal
- $G$ has a terminating *Lower* Central Series
- $G$ has a terminating *Upper* Central Series
:::

**Lemmas:**

- Nilpotent groups satisfy the 2 out of 3 property.\todo{Todo. Specify.}
- $G$ has normal subgroups of order $d$ for *every* $d$ dividing $\abs{G}$