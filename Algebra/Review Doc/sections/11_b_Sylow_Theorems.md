# Sylow Theorems

## Sylow Theorems

:::{.definition}
A **$p\dash$group** is a group $G$ such that every element is order $p^k$ for some $k$.
  If $G$ is a finite $p\dash$group, then $\abs G = p^j$ for some $j$.
:::

Write


- $\abs{G} = p^k m$ where $(p, m) = 1$,
- $S_p$ a Sylow$\dash p$ subgroup, and
- $n_p$ the number of Sylow$\dash p$ subgroups.



### Sylow 1 (Cauchy for Prime Powers)


:::{.theorem title="Sylow 1"}
\[
\forall p^n \text{ dividing } \abs{G} \text{, there exists a subgroup of size } p^n
.\]
:::

Idea: Sylow $p\dash$subgroups exist for any $p$ dividing $\abs{G}$, and are maximal in the sense that every $p\dash$subgroup of $G$ is contained in a Sylow $p\dash$subgroup.

If $\abs G = \prod p_i^{\alpha_i}$, then there exist subgroups of order $p_i^{\beta_i}$ for every $i$ and every $0 \leq \beta_i \leq \alpha_i$.
In particular, Sylow $p\dash$subgroups always exist.

### Sylow 2 (Sylows are Conjugate)


:::{.theorem title="Sylow 2"}
All Sylow$\dash p$ subgroups $S_p$ are conjugate, i.e.
\[
S_p^i, S_p^j \in \mathrm{Syl}_p(G) \implies \exists g \text{ such that } g S_p^i g\inv = S_p^j
\]

:::


:::{.corollary}
\[
n_p = 1 \iff S_p \normal G
.\]
:::

### Sylow 3 (Numerical Constraints)


:::{.theorem title="Sylow 3"}
\envlist

1. $n_p \divides m~$ (in particular, $n_p \leq m$),

2. $n_p \equiv 1 \mod p$,

3. $n_p = [G : N_G(S_p)]$ where $N_G$ is the normalizer.

:::



:::{.corollary}
$p$ does not divide $n_p$.
:::

:::{.proposition}
Every $p\dash$subgroup of $G$ is contained in a Sylow $p\dash$subgroup.
:::
:::{.proof}
Let $H \leq G$ be a $p\dash$subgroup.
If $H$ is not *properly* contained in any other $p\dash$subgroup, it is a Sylow $p\dash$subgroup by definition.
Otherwise, it is contained in some $p\dash$subgroup $H^1$.
Inductively this yields a chain $H \subsetneq H^1 \subsetneq \cdots$, and by Zorn's lemma $H\definedas \union_i H^i$ is maximal and thus a Sylow $p\dash$subgroup.
:::

### Proof of Sylow Theorems

\todo[inline]{Proof of Sylows}


