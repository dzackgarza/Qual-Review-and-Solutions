# Appendix: Homological Algebra

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


