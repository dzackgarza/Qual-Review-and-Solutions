# Surfaces and Manifolds

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

