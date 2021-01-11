# Appendix: Homological Algebra


## Exact Sequences


:::{.proposition title="?"}
The sequence $A \mapsvia{f_1} B \mapsvia{f_2} C$ is exact if and only if $\im f_i = \ker f_{i+1}$ and thus $f_2 \circ f_1 = 0$.
:::


:::{.fact}
Some useful results:

- $0 \into A \injects_{f} B$ is exact iff $f$ is **injective**
- $B\surjects_{f} C \into 0$ is exact iff $f$ is **surjective**
- $0\into A \into B \into 0$ is exact iff $A \cong B$.
- $A \injects B \to C \to D \surjects E$ iff $C = 0$
- $0\to A \to B \mapsvia{\cong} C \to D\to 0$ iff $A = D = 0$.
	- Todo: Proof
- $0\to A\to B \to C \to 0$ splits iff $C$ is free.
- Can think of $C \cong \frac{B}{\im f_1}$.

:::





:::{.definition title="Splitting an exact sequence"}
The sequences *splits* when a morphism $f_2^{-1}: C \into B$ exists. In $\textbf{Ab}$, this means $B \cong A \oplus C$, in $\mathbf{Grp}$ it's $B \cong A \semidirect_\phi C$.
:::

:::{.example title="of exact sequences"}
\envlist

- $0 \into \ZZ \mapsvia{\times 2} \ZZ \mapsvia{\text{mod}~2} \frac{\ZZ}{2\ZZ} \into 0$
- $1 \into N \mapsvia{\iota} G \mapsvia{p} \frac{G}{N} \into 1$
  - Groups and normal subgroups
- $1 \into \frac{\ZZ}{n\ZZ} \mapsvia{\iota} D_{2n} \mapsvia{?} \frac{\ZZ}{2\ZZ} \into 1$
  - Dihedral group and cyclic groups
- $0 \into I \intersect J \mapsvia{\Delta: x\mapsto(x,x)} I \oplus J \mapsvia{f:(x,y) \mapsto x-y} I + J \into 0$
  - $R$-Modules
- $0 \into \frac{R}{I \intersect J} \mapsvia{\Delta: x\mapsto(x,x)} \frac{R}{I} \oplus \frac{R}{J} \mapsvia{f:(x,y) \mapsto x-y} \frac{R}{I + J} \into 0$
- $0 \into \mathbb{H}_1 \mapsvia{\nabla} \mathbb{H}_\text{curl} \mapsvia{\nabla \cross} \mathbb{H}_\text{div} \mapsvia{\nabla \cdot} \mathbb{L}_2 \into 0$
  - Since $\nabla \cross \nabla F = \nabla \cdot\nabla\cross \bar{v} = 0$ in Hilbert spaces


:::


:::{.remark}
Is $f_1\circ f_2 = 0$ equivalent to exactness..?
Answer: yes, every exact sequence is a chain complex with trivial homology. 
Therefore homology measures the failure of exactness.

> Alternatively stated: Exact sequences are chain complexes with no cycles.
:::


:::{.remark}
Any LES $A_1 \into \cdots \into A_6$ decomposes into a twisted collection of SES's; define $C_k = \ker (A_k \into A_{k+1}) \cong \im(A_{k-1} \into A_k)) \cong \coker(A_{k-2} \into A_{k-1})$, then all diagonals here are exact:
<!--![Long short exact sequences.png](https://upload.wikimedia.org/wikipedia/commons/b/b9/Long_short_exact_sequences.png)-->

:::

## Five Lemma


:::{.theorem title="?"}
If $m, p$ are isomorphisms, $l$ is an **surjection**, and $q$ is an **injection**, then $n$ is an **isomorphism**.

<!--![5 lemma.svg](https://upload.wikimedia.org/wikipedia/commons/thumb/f/f8/5_lemma.svg/388px-5_lemma.svg.png)-->

Proof: diagram chase two "four lemmas", one on each side. 
Full proof [here](https://en.wikipedia.org/wiki/Five_lemma).
:::




## Free Resolutions

The canonical example:
$$
0 \to \ZZ \mapsvia{\times m} \ZZ \mapsvia{\mod m} \ZZ_m \to 0
$$

Or more generally for a finitely generated group $G = \generators{g_1, g_2, \cdots, g_n}$,
$$
\cdots \to \ker(f) \to F[g_1, g_2, \cdots, g_n] \mapsvia{f} G \to 0
$$ 
where $F$ denotes taking the free group.

Every abelian groups has a resolution of this form and length 2.

## Computing Tor

$$
\tor(A, B) = h[\cdots \to A_n \tensor B \to A_{n-1}\tensor B \to \cdots A_1\tensor B \to 0]
$$ 
where $A_*$ is any free resolution of $A$.

Shorthand/mnemonic: 
$$
\tor: \mathcal{F}(A) \to (\wait \tensor B) \to H_*
$$

## Computing Ext
$$
\ext(A, B) = h[\cdots \hom(A, B_n) \to \hom(A, B_{n-1}) \to \cdots \to \hom(A, B_1) \to 0 ]
$$ 
where $B_*$ is a any free resolution of $B$.

Shorthand/mnemonic: 
$$
\ext: \mathcal{F}(B) \to \hom(A, \wait) \to H_*
$$

## Properties of Tensor Products

- $A\tensor B \cong B\tensor A$
- $(\wait) \tensor_R R^n = \id$
- $\bigoplus_i A_i \tensor \bigoplus_j B_j = \bigoplus_i\bigoplus_j(A_i \tensor B_j)$
- $\ZZ_m \tensor \ZZ_n = \ZZ_d$
- $\ZZ_n \tensor A = A/nA$

## Properties of Hom

- $\hom_R (\bigoplus_i A_i, \prod B_j) = \bigoplus_i \prod_j \hom(A_i, B_j)$
- Contravariant in first slot, covariant in second
- Exact over vector spaces

## Properties of Tor

- $\tor_R^0(A, B) = A \tensor_R B$
- $\tor(\bigoplus_i A_i, \bigoplus_j B) = \bigoplus_i \bigoplus_j \tor(\mathbf{T}A_i, \mathbf{T}B_j)$  where $\mathbf{T}G$ is the torsion component of $G$.
- $\tor(\ZZ_n, G) = \ker (g \mapsto ng) = \theset{g\in G\mid ng = 0}$
- $\tor(A, B) = \tor(B, A)$

## Properties of Ext

- $\ext_R^0(A, B) = \hom_R(A, B)$
- $\ext(\bigoplus_i A_i, \prod_j B_j) = \bigoplus_i \prod_j \ext(\mathbf{T}A_i, B_j)$
- $\ext(F, G) = 0$ if $F$ is free
- $\ext(\ZZ_n, G) \cong G/nG$

## Hom/Ext/Tor Tables

$\hom$    | $\ZZ_m$  | $\ZZ$  | $\QQ$
--|---|---|--
$\ZZ_n$   | $\ZZ_d$  | $0$    | $0$
$\ZZ$     | $\ZZ_m$  | $\ZZ$  | $\QQ$
$\QQ$     | $0$      | $0$    | $\QQ$

$\tor$    | $\ZZ_m$ | $\ZZ$ | $\QQ$
--|---|---|--
$\ZZ_n$   | $\ZZ_d$ | $0$   | $0$
$\ZZ$     | $0$     | $0$   | $0$
$\QQ$     | $0$     | $0$   | $0$

$\ext$    | $\ZZ_m$   | $\ZZ$                 | $\QQ$
--|---|---|--
$\ZZ_n$   | $\ZZ_d$   | $\ZZ_n$               | $0$
$\ZZ$     | $0$       | $0$                   | $0$
$\QQ$     | $0$       | $\mathcal{A_p}/\QQ$   | $0$

Where $d = \gcd(m, n)$ and $\ZZ_0 \definedas 0$.

Things that behave like "the zero functor":

- $\ext(\ZZ, \wait)$
- $\tor(\wait, \ZZ), \tor(\ZZ, \wait)$
- $\tor(\wait, \QQ), \tor(\QQ, \wait)$

Thins that behave like "the identity functor":

- $\hom(\ZZ, \wait)$
- $\wait \tensor_\ZZ \ZZ$ and $\ZZ \tensor_\ZZ \wait$

For description of $\mathcal{A_p}$, see [here](http://math.jhu.edu/~jmb/note/torext.pdf). 
This is a certain ring of adeles.


