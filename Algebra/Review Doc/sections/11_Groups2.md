## Series of Groups

Definition
: A **normal series** of a group $G$ is a sequence $G \to G^1 \to G^2 \to \cdots$ such that $G^{i+1} \normal G_i$ for every $i$.

Definition
: A **central series** for a group $G$ is a terminating normal series $G \to G^1 \to \cdots \to \theset{e}$ such that each quotient is **central**, i.e. $[G, G^i] \leq G^{i-1}$ for all $i$.

Definition (Composition Series)
: A **composition series** of a group $G$ is a finite normal series such that $G^{i+1}$ is a *maximal proper* normal subgroup of $G^i$.

Theorem (Jordan-Holder)
: Any two composition series of a group have the same length and isomorphic composition factors (up to permutation).

Definition (Simple Groups)
: A group $G$ is **simple** iff $H\normal G \implies H = \theset{e}, G$, i.e. it has no non-trivial proper subgroups.

Lemma
: If $G$ is *not* simple, then for any $N\normal G$, it is the case that $G \cong E$ for an extension of the form $N\to E\to G/N$.

Definition (Lower Central Series)
: Set $G^0 = G$ and $G^{i+1} = [G, G^i]$, then $G^0 \geq G^1 \geq \cdots$ is the *lower central series* of $G$.

> Moral: Iterate the adjoint map $[\wait, G]$.
> Mnemonic: "lower" because the chain is descending.


> $G$ is nilpotent $\iff$ the LCS terminates.


Definition (Upper Central Series)
: Set $Z_0 = 1$, $Z_1 = Z(G)$, and $Z_{i+1} \leq G$ to be the subgroup satisfying $Z_{i+1}/Z_i = Z(G/Z_i)$.
  Then $Z_0 \leq Z_1 \leq \cdots$ is the *upper central series* of $G$.

  Equivalently, since $Z_i\normal G$, 

> Mnemonic: "upper" because the chain is ascending

Definition (Derived Series)
: Set $G^{(0)} = G$ and $G^{(i+1)} = [G^{(i)}, G^{(i)}]$, then $G^{(0)} \geq G^{(1)} \geq \cdots$ is the *derived series* of $G$.

Definition (Solvable)
: A group $G$ is **solvable** iff $G$ has a terminating normal series with abelian composition factors, i.e.
  $$
  G \to G^1 \to \cdots \to \theset{e} \text{ with } G^{i}/G^{i+1}\text{ abelian for all } i
  .$$

Theorem
: A group $G$ is solvable iff its derived series terminates.

Theorem
: If $n\geq 4$ then $S_n$ is solvable.

Lemmas
:   \hfill

    - $G$ is solvable iff $G$ has a terminating *derived series*.
    - Solvable groups satisfy the 2 out of 3 property
    - Abelian $\implies$ solvable
    - Every group of order less than 60 is solvable.


Definition (Nilpotent)
: A group $G$ is **nilpotent** iff $G$ has a terminating upper central series.

> Moral: the adjoint map is nilpotent.

Theorem
: A group $G$ is nilpotent iff all of its Sylow $p\dash$subgroups are normal for every $p$ dividing $\abs{G}$.

Theorem
: A group $G$ is nilpotent iff every maximal subgroup is normal.

Theorem
: $G$ is nilpotent iff $G$ has an upper central series terminating at $G$.

Theorem 
: $G$ is nilpotent iff $G$ has a lower central series terminating at $1$.


**Lemma:**
For $G$ a finite group, TFAE:

- $G$ is nilpotent
- Normalizers grow (i.e.$H < N_G(H)$ whenever $H$ is proper)
- Every Sylow-p subgroup is normal
- $G$ is the direct product of its Sylow p-subgroups
- Every maximal subgroup is normal
- $G$ has a terminating *Lower* Central Series
- $G$ has a terminating *Upper* Central Series

**Lemmas:**

- $G$ nilpotent $\implies G$ solvable
- Nilpotent groups satisfy the 2 out of 3 property.
- $G$ has normal subgroups of order $d$ for *every* $d$ dividing $\abs{G}$
- $G$ nilpotent $\implies Z(G) \neq 0$
- Abelian $\implies$ nilpotent
- p-groups $\implies$ nilpotent



## Series of Groups



**Definition:**
An **upper central series** is a terminating normal series $G \to G^1 \to \cdots \to \theset{e}$ such that $G^1 = Z(G)$ and $G^{i+1}$ is defined such that $G^{i+1}/G^i = Z(G^i)$.

> Moral: Iterate taking "higher centers".


