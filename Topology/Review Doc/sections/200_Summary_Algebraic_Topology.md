# Broadly Applicable Facts 

## Different Types of Product/Sum Structures

- Cartesian Product $X\cross Y, \prod_i X_i$
- Direct Sum $X \oplus Y, \bigoplus_i X_i$
- Direct Product $X \ast Y, \ast_i X_i$
  - Element-wise multiplication, allows infinitely many entries
  - $\ast_i X_i= \oplus_i X_i$ for $i < \infty$
- Tensor Product $X \tensor Y, \bigotimes_i X_i, X^{\otimes_i}$

*   For a finite index set $I$, $\prod_I G = \bigoplus_I G$ in $\mathbf{Grp}$, i.e. the finite direct product and finite direct sum coincide. 

    Otherwise, if $I$ is infinite, the direct sum requires cofinitely many zero entries (i.e. finitely many nonzero entries), so here we always use $\prod$. 

    In other words, there is an injective map $$\bigoplus_I G \injects \prod_I G$$ which is an isomorphism when $\abs{I} < \infty$

* The free abelian group of rank $n$: 
  $$
  \ZZ^n \definedas \prod_{i=1}^n \ZZ = \ZZ \times \ZZ \times \ldots \ZZ
  .$$ 
	- $x \in \ZZ^n = \left< a_1, \cdots, a_n\right> \implies x = \sum_n c_i a_i$ for some $c_i \in \ZZ$ , i.e. $a_i$ form a basis.
	- Example: $x = 2a_1 + 4a_2 + a_1 - a_2 = 3a_1 + 3a_2$.

* The **free product** of $n$ free abelian groups:
  $$
  \ZZ^{\ast n} \definedas \Conv_{i=1}^n \ZZ = \ZZ \ast \ZZ \ast \ldots \ZZ
  $$ 
  This is a free *nonabelian* group on $n$ generators.

	- $x \in \ZZ^{\ast n} = \left< a_1, \ldots, a_n\right>$ implies that $x$ is a finite word in the noncommuting symbols $a_i^k$ for $k\in \ZZ$.
	- Example: $x = a_1^2 a_2^4 a_1 a_2^{-2}$

Proposition
:   There are no nontrivial homomorphisms from finite groups into free groups.

    In particular, any homomorphism $\ZZ_n \to \ZZ$ is trivial.

Proof
:   Homomorphisms preserve torsion; the former has $n\dash$torsion while the latter does not.

This is especially useful if you have some $f: A\into B$ and you look at the induced homomorphism $f_*: \pi_1(A) \into \pi_1(B)$. If the former is finite and the latter contains a copy of $\ZZ$, then $f_*$ has to be the trivial map $f_*([\alpha]) = e \in \pi_1(B)$ for every $[\alpha] \in \pi_1(A)$.



## Conventions

- Generally assume spaces are connected.

* $\pi_0(X)$ is the set of path components of $X$, and I write $\pi_0(X) = \ZZ$ if $X$ is path-connected (although it is not a group). 
  Similarly, $H_0(X)$ is a free abelian group on the set of path components of $X$.

* Lists start at entry 1, since all spaces are connected here and thus $\pi_0 = H_0 = \ZZ$. That is,
	* $\pi_*(X) = [\pi_1(X), \pi_2(X), \pi_3(X), \cdots]$
	* $H_*(X) = [H_1(X), H_2(X), H_3(X), \cdots]$


