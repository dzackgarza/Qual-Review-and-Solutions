# Preface

References:

- Munkres [@munkres_2018]
- Hatcher [@hatcher_2002]

Some fun resources:

- [The Line with Two Origins](https://blogs.scientificamerican.com/roots-of-unity/a-few-of-my-favorite-spaces-the-line-with-2-origins/)

## Notation

| Notation                                             | Definition                          |
|------------------------------------------------------|-------------------------------------|
| $X\cross Y, \prod_{j\in J} X_j, X^{\cross n}$        | Direct Products                     |
| $X\oplus Y, \bigoplus_{j\in J} X_j, X^{\oplus n}$    | Direct sums                         |
| $X\tensor Y, \bigotimes_{j\in J} X_j, X^{\tensor n}$ | Tensor products                     |
| $X\ast Y, \ast_{j\in J} X_j, X^{\ast n}$             | Free products                       |
| $\ZZ^n$                                              | The free abelian group of rank $n$  |
| $F_n, \ZZ^{\ast n}$                                  | The free group on $n$ generators    |
| $\pi_0(X)$                                           | The *set* of path components of $X$ |
| $G=1$                                                | The trivial abelian group           |
| $G=0$                                                | The trivial nonabelian group        |


:::{.remark}
I use $e_G$ or $1_G, 0_G$ to denote identity elements in a group $G$.
:::

:::{.remark title="on direct sums vs direct products"}
$A\times B$ denotes the **direct product** of modules.
$A\oplus B$ denotes a **direct sum**: the subset of $A\cross B$ where only finitely many terms are nonzero.
Both the product and direct sum have coordinate-wise operations.
For finite index sets $\abs{J}< \infty$, the direct sum and product coincide, but in general there is only an injection $\bigoplus_j X_i \injects \prod_j X_j$.
In the direct sum $\bigoplus_j X_j$ have only finitely many nonzero entries, while the product allows *infinitely* many nonzero entries.
So in general, I always use the product notation.
:::

:::{.remark title="on notation for free groups and free products"}
The free group on $n$ generators is the free product of $n$ free abelian groups, but is not generally abelian!
So we use multiplicative notation, and elements 
\[
x \in \ZZ^{\ast n} = \left< a_1, \ldots, a_n\right>
\]
are finite words in the noncommuting symbols $a_i^k$ for $k\in \ZZ$.
E.g. an element may look like 
\[
x = a_1^2 a_2^4 a_1 a_2^{-2}
.\]
:::

:::{.remark title="on notation for free abelian groups"}
The free abelian group of rank $n$ is the abelianization of $\ZZ^{\ast n}$,
and its elements are characterized by
\[
x\in \ZZ^{\ast n} = \gens{ a_1, \cdots, a_n } \implies x = \sum_n c_i a_i \text{ for some } c_i \in \ZZ
\]
where the $a_i$ are some generating set of $n$ elements and we used additive notation since the group is abelian.
E.g. such an element may look like 
\[
x = 2a_1 + 4a_2 + a_1 - a_2 = 3a_1 + 3a_2
.\]
:::

:::{.remark title="on indexing conventions and list notation"}
Spaces are assumed to be connected and path connected, so $\pi_0(X) = H_0(X) = \ZZ$.
So I virtually never consider anything occurring at index zero in these notes.

Graded objects such as $\pi_*, H_*, H^*$ are sometimes represented as lists, which always start indexing at 1.
Examples: 
\[
\pi_*(X) &= [\pi_1(X), \pi_2(X), \pi_3(X), \cdots] \\
H_*(X) &= [H_1(X), H_2(X), H_3(X), \cdots]
.\]

:::

## Background Algebra 

:::{.fact}
An injective group morphism $f:X\injects Y$ where $X$ is trivial forces $Y$ to be trivial.
:::

:::{.proposition title="Morphisms between groups finite and infinite groups"}
There are no nontrivial homomorphisms from finite groups into free groups.
In particular, any group morphism $f: \ZZ_n \to \ZZ$ is trivial.
:::

:::{.proof title="?"}
Let $f: G\to H$, then $f(1_G) = 1_H$.
Supposing $g\in G$ is torsion of order $n$, we have
\[
1_H = f(1_G) = f(g^n) = f(g)^n 
,\]

so $f(g)$ is torsion of order dividing $n$.
But a free group is torsionfree.
:::

:::{.remark title="How to use this fact"}
This is especially useful if you have some $f: A\into B$ and you look at the induced homomorphism $f_*: \pi_1(A) \into \pi_1(B)$. If the former is finite and the latter contains a copy of $\ZZ$, then $f_*$ has to be the trivial map $f_*([\alpha]) = e \in \pi_1(B)$ for every $[\alpha] \in \pi_1(A)$.

:::

 
