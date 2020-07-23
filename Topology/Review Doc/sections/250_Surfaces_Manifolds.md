# Surfaces and Manifolds

To show something is not a manifold, try looking at local homology. Can use point-set style techniques like removing points, i.e. $H_1(X, X-\pt)$; this should essentially always yield $\ZZ$ by excision arguments.

## Euler Characteristics

\todo[inline]{General formula involving genus and nonorientable genus. Presentation of monoid of surfaces}

- Only surfaces with positive $\chi$:
	- $\chi S^2 = 2$
	- $\chi \RP^2 = 1$
	- $\chi B^2 = 1$
- Manifolds with zero $\chi$
	- $T^2, K, M, S^1 \cross I$
- Manifolds with negative $\chi$
	- $\Sigma_{g \geq 2}$ by $\chi(X) = 2-2g$.


## Classification of Surfaces

- Orientable: $S^n, T^n, \RP^\text{odd}$
- Nonorientable: $\RP^\text{even}, \mathbb{M}, \mathbb{K}$

**Pasting Diagrams**

$S^2, \RP^2, T^2, \KK$, Mobius Strip
\todo[inline]{Pasting diagrams.}

- Classified by $\chi$ and orientability.
- $\chi X = \chi U + \chi V - \chi (U\cap V)$
- $\chi A \# B = \chi A + \chi B - 2$
- Connected closed surfaces: $<S, P, T, K \mid S = 1, P^2 = K, P^3 = PT>$
- $\chi X = 2 \implies X \cong S$
- $\chi X = 0 \implies X \cong T^2$ or $K$
- $\chi X = -2 \implies X \cong P$
- $\chi X = -n, X$ orientable $\implies \chi X \cong \Sigma_{1-\frac{n}{2}}$
- $\chi X = -n, X$ non-orientable $\implies \chi X \cong \tilde\Sigma_{1-\frac{n}{2}}$
- $\chi M^n = 0$ for $n$ odd.
- $M^n$ closed/connected $\implies H_n = \ZZ$ and $\tor(H_{n-1}) = 0$
- 3-manifolds:
  - Orientable: $H_* = (\ZZ, \ZZ^r, \ZZ^r, \ZZ)$
  - Nonorientable: $H_* = (\ZZ, \ZZ^r, \ZZ^{r-1} \oplus \ZZ_2, \ZZ)$




## Manifolds


* $H^n(M^n) = \ZZ$ if $M^n$ is orientable and zero if $M^n$ is nonorientable.
* Poincare Duality: $H_i M^n =\cong H^{n-i} M^n$ iff $M^n$ is closed and orientable.

On the complements of spaces in $\RR^3$:

> My personal crutch is to just think about complements in $S^3$, which are usually easier since knot complements in $S^3$ are always $K(\pi, 1)$s. 
> Now if $K$ is a knot and $X$ is its complement in $S^3$, then you can prove that its complement in $\RR^3$ is homotopy equivalent to $S^2\vee X$

If $M$ is a closed 3-manifold and $K$ is a nullhomologous knot in $M$, then $H_1(X -n(K)) \cong H_1(X) \times \ZZ$ where $n(K)$ is a tubular neighborhood.

Take $M=S^3$, $K$ any knot, then $H_*(S^3 - K) = [\ZZ, \ZZ, 0\rightarrow]$. Follows from Mayer-Vietoris, taking $S^3 = n(K) \cup (S^3-K)$, where $n(K) \homotopic S^1$ and $S^3-K \cap n(K) \homotopic T^2$. (Note $S^3-K$ is a connected, open 3-manifold, so $H^3(S^3-K) =0$).

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



