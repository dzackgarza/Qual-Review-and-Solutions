# Summary

* Algebraic topology topics:
	* Classification of compact surfaces
	* Euler characteristic
	* Connect sum
	* Homology and cohomology groups
	* Fundamental group
	* Singular/cellular/simplicial homology
	* Mayer-Vietoris long exact sequences for homology and cohomology
	* Diagram chasing
	* Degree of maps from $S^n \to S^n$
	* Orientability, compactness
	* Top-level homology and cohomology
	* Reduced homology and cohomology
	* Relative homology
	* Homotopy and homotopy invariance
	* Deformation retract
	* Retract
	* Excision
	* Kunneth formula
	* Factoring maps
	* Fundamental theorem of algebra
* Algebraic topology theorems:
	* Brouwer fixed point theorem
	* Poincare lemma
	* Poincare duality
	* de Rham theorem
	* Seifert-van Kampen theorem
* Covering space theory topics:
	* Covering maps
	* Free actions
	* Properly discontinuous action
	* Universal cover
	* Correspondence between covering spaces and subgroups of the fundamental group of the base.
	* Lifting paths
	* Homotopy lifting property
	* Deck transformations
	* The action of the fundamental group
	* Normal/regular cover

# Unsorted




## Results for Manifolds

- Every $\CC\dash$manifold is canonically orientable.
- If $M^n$ is **closed and connected**, then $H_{\geq n}(X) = 0$ and $M^n$ is orientable iff $H_n(X) = \ZZ$.
- Poincare Duality
- If $M^n$ is a **closed orientable manifold without boundary**, then $H^k(M^n; F) \cong H_{n-k}(M^n; F)$ for a field $F$.
- This is a strict implication, so failure of the RHS implies missing conditions on the LHS.
- The intersection pairing is nondegenerate modulo torsion.
- Lefschetz Duality
- If $M^n$ is a **closed orientable manifold with boundary** then  $H_k(M^n; \ZZ) \cong H^{n-k}(M^n, \del M^n; \ZZ)$
- $M^n$ closed, connected, and orientable $\implies H_n = \ZZ$ and $\mathbf{T}(H_{n-1}) = 0$
- $M^n$ closed and $n$ odd implies $\chi(M^n) = 0$.
- Any map $X \to Y$ with $X$ factors through the orientation cover $\tilde Y_o$.
- If $Y$ is non-orientable, this is a double cover.
- If $n$ is odd, $\chi(M^n) = 0$ by Poincare Duality.
- $M$ is orientable if $\pi_1(M)$ has no subgroup of index 2.
- If $M^\text{orientable} \mapsvia{\pi_k} M^\text{non-orientable}$ is a $k\dash$fold cover, then $k$ is even or $\infty$.


# Major Results






# Low Dimensional Homology Examples

\begin{align*}
\begin{array}{cccccccccc}
S^1   &=  &[&\ZZ, &\ZZ,               &0,    &0,      &0,    &0\rightarrow & ]\\
\MM   &=  &[&\ZZ, &\ZZ,               &0,    &0,      &0,    &0\rightarrow & ]\\
\RP^1 &=  &[&\ZZ, &\ZZ,               &0,    &0,      &0,    &0\rightarrow & ]\\
\RP^2 &=  &[&\ZZ, &\ZZ_2,             &0,    &0,      &0,    &0\rightarrow & ]\\
\RP^3 &=  &[&\ZZ, &\ZZ_2,             &0,    &\ZZ,    &0,    &0\rightarrow & ]\\
\RP^4 &=  &[&\ZZ, &\ZZ_2,             &0,    &\ZZ_2,  &0,    &0\rightarrow & ]\\
 S^2  &=  &[&\ZZ, &0,                 &\ZZ,  &0,      &0,    &0\rightarrow & ]\\
\TT^2 &=  &[&\ZZ, &\ZZ^2,             &\ZZ,  &0,      &0,    &0\rightarrow & ]\\
\KK   &=  &[&\ZZ, &\ZZ \oplus \ZZ_2,  &0,    &0,      &0,    &0\rightarrow & ]\\
\CP^1 &=  &[&\ZZ, &0,                 &\ZZ,  &0,      &0,    &0\rightarrow & ]\\
\CP^2 &=  &[&\ZZ, &0,                 &\ZZ,  &0,      &\ZZ,  &0\rightarrow & ]\\
\end{array}
.\end{align*}



# Further Notes

On the complements of spaces in $\RR^3$:

> > My personal crutch is to just think about complements in $S^3$, which are usually easier since knot complements in $S^3$ are always $K(\pi, 1)$s. 
> Now if $K$ is a knot and $X$ is its complement in $S^3$, then you can prove that its complement in $\RR^3$ is homotopy equivalent to $S^2\vee X$



If $M$ is a closed 3-manifold and $K$ is a nullhomologous knot in $M$, then $H_1(X -n(K)) \cong H_1(X) \times \ZZ$ where $n(K)$ is a tubular neighborhood.

Take $M=S^3$, $K$ any knot, then $H_*(S^3 - K) = [\ZZ, \ZZ, 0\rightarrow]$. Follows from Mayer-Vietoris, taking $S^3 = n(K) \cup (S^3-K)$, where $n(K) \homotopic S^1$ and $S^3-K \cap n(K) \homotopic T^2$. (Note $S^3-K$ is a connected, open 3-manifold, so $H^3(S^3-K) =0$).

When covering spaces are involved in any way, try computing Euler characteristics - this sometimes yields nice numerical constraints.

To show something is not a manifold, try looking at local homology. Can use point-set style techniques like removing points, i.e. $H_1(X, X-\pt)$; this should essentially always yield $\ZZ$ by excision arguments.

# Unsorted 2

## Basic Facts About Spheres
- $S^{2n+1} \subset \CC^{n+1}$
- $\CP^n = S^{2n+1} / S^n$

## Lemma: There are no nontrivial homomorphisms from finite groups into free groups.

In particular, any homomorphism $\ZZ_n \to \ZZ$ is trivial.

Proof: homomorphisms preserve torsion; the former has $n\dash$torsion while the latter does not.

This is especially useful if you have some $f: A\into B$ and you look at the induced homomorphism $f_*: \pi_1(A) \into \pi_1(B)$. If the former is finite and the latter contains a copy of $\ZZ$, then $f_*$ has to be the trivial map $f_*([\alpha]) = e \in \pi_1(B)$ for every $[\alpha] \in \pi_1(A)$.


## Different Types of Product/Sum Structures

- Cartesian Product $X\cross Y, \prod_i X_i$
- Direct Sum $X \oplus Y, \bigoplus_i X_i$
- Direct Product $X \ast Y, \ast_i X_i$
  - Element-wise multiplication, allows infinitely many entries
  - $\ast_i X_i= \oplus_i X_i$ for $i < \infty$
- Tensor Product $X \tensor Y, \bigotimes_i X_i, X^{\otimes_i}$

## Lemma: Contracting Spaces in Products

$X\cross \RR^n \homotopic X \cross \pt \cong X$


## Mayer-Vietoris

Given $A,B \subset X$ such that $A^\circ \cup B^\circ = X$, there is a long exact sequence in homology:

\begin{tikzcd}
 &  &  &  & \cdots \arrow[lllldd, out=0, in=-180, "\delta_3"'] \\
 &  &  &  &  \\
H_2(A\cap B) \arrow[rr] \arrow[rr, "{(i^*, -j^*)_2}"] &  & H_2 A \oplus H_2 B \arrow[rr, "(l^* - r^*)_2"] &  & H_2 (A\cup B) \arrow[lllldd, "\delta_2"', out=0, in=-180] \\
 &  &  &  &  \\
H_1(A\cap B) \arrow[rr, "{(i^*, -j^*)_1}"] &  & H_1 A \oplus H_1 B \arrow[rr, "(l^*-r^*)_1"] &  & H_1 (A\cup B) \arrow[lllldd, "\delta_1"', out=0, in=-180] \\
 &  &  &  &  \\
H_0 (A\cap B) \arrow[rr, "{(i^*, -j^*)_0}"] &  & H_0 A \oplus H_0 B \arrow[rr, "(l^* - r^*)_0"] &  & H_0 (A\cup B) \arrow[lllldd, "\delta_0"', out=0, in=-180] \\
 &  &  &  &  \\
0 &  &  &  &
\end{tikzcd}


This is sometimes written in the following compact form:
$$ \cdots  H_n(A \cap B) \xrightarrow{(i^*,~ j^*)} H_n(A) \oplus H_n(B) \xrightarrow{l^* - r^*}  H_n(X) \xrightarrow{\delta} H_{n-1}(A\cap B)\cdots$$

Where

- $i: A\cap B \hookrightarrow A$ induces $i^*: H_*(A\cap B) \to H_*(A)$

- $j: A\cap B \hookrightarrow B$ induces $j^*: H_*(A\cap B) \to H_*(B)$

- $l: A \hookrightarrow A\cup B$ induces $l^*: H_*(A) \to H_*(X)$

- $r: B \hookrightarrow A\cup B$ induces $r^*: H_*(B) \to H_*(X)$

The connecting homomorphisms $\delta_n :H_n(X) \to H_{n-1}(X)$ are defined by taking a class $[\alpha] \in H_n(X)$, writing it as an $n$-cycle $z$, then decomposing $z = \sum c_i$ where each $c_i$ is an $x+y$ chain. Then $\del(c_i) = \del(x+y) = 0$, since the boundary of a cycle is zero, so $\del(x) = -\del(y)$. So then just define $\delta([\alpha]) = [\del x] = [-\del y]$.

Handy mnemonic diagram:
\begin{align*}
\begin{matrix}
 && A\intersect B & \\
&\large\diagup &  & \large\diagdown \\
A\union B & & \large\longleftarrow &  & A \oplus B
\end{matrix}
.\end{align*}

### Application: Isomorphisms in the homology of spheres.

Claim: $H^i(S^n) \cong H^{i-1}(S^{n-1})$.

Write $X = A \cup B$, the northern and southern hemispheres, so that $A \cap B = S^{n-1}$, the equator. In the LES, we have:

\begin{align*}
H^{i+1}(S^n) \xrightarrow{} H^i(S^{n-1}) \xrightarrow{} H^iA \oplus H^i B \xrightarrow{} H^i S^n \xrightarrow{} H^{i-1}(S^{n-1}) \xrightarrow{} H^{i-1}A \oplus H^{i-1}B
.\end{align*}

But $A, B$ are contractible, so $H^iA= H^iB = 0$, so we have

\begin{align*}
H^{i+1}(S^n) \xrightarrow{} H^{i}(S^{n-1}) \xrightarrow{} 0 \oplus 0 \xrightarrow{}H^i(S^n) \xrightarrow{} H^{i-1}(S^{n-1}) \xrightarrow{} 0
.\end{align*}

And in particular, we have the shape $0 \to A \to B \to 0$ in an exact sequence, which is always an isomorphism.

## The Long Exact Sequence of a Pair

LES of pair $(A,B) \implies \cdots H_n(B) \into H_n(A) \into H_n(A,B) \into H_{n-1}(B) \cdots$

\begin{align*}
\begin{matrix}
  && B & \\
&\large\diagup &  & \large\diagdown \\
(A,B) & & \large\longleftarrow &  & A
\end{matrix}
.\end{align*}

![Barycentric Subdivision](figures/image_2020-06-01-00-35-21.png)
