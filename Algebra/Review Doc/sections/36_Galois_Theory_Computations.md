# Galois Theory: Computations


:::{.proposition title="Irreducible quartics"}
The Galois groups of irreducible quartics can be determined using a bit of number theory:

![](figures/2021-07-20_22-06-48.png)

:::



:::{.definition title="Discriminant"}
For $f = \sum a_k x^k$ monic,
\[
\Delta_f = \prod_{i<j} (r_i - r_j)^2
.\]

:::


:::{.example title="Cubics"}
For $f(x) =x^3 +ax + b$ over $\ch k\neq 2,3$, then the Galois group $G$ is known:

- If $\Delta$ is a perfect square in $K$, $G= A_3$.
- Else, $G= S_3$.

Note that $\Delta = -4a^3 - 27b^2$ here.

More generally, $G\injects A_n \iff \Delta$ is a perfect square in $k$.

:::




:::{.exercise title="?"}
\envlist

- $K/k \da \QQ(\sqrt 2, \sqrt 3)/\QQ$: $\Gal(K/k) = (\ZZ/2)^{\times 2}$.

- $K/k = \SF(x^3-2)/\QQ = \QQ(2^{1\over 3}, \zeta_3)$: $\Gal(K/k) = S_3$.


- $f(x) \da x^n-1$ over $\QQ$: $G = (\ZZ/n)\units$

- $f(x) \da x^3-x+1$ over $\QQ$: $G = S_3$ since $\Delta = -23$ is squarefree in $\QQ$.

- $f(x) \da x^3-3x+1$ over $\QQ$: $G=A_3$ since $\Delta = 81$.

- $f(x) \da x^4-2$ over $\QQ$: $G=D_4$ since $i\mapsto -i$ is order 2 and $2^{1\over 4}\mapsto i2^{1\over 4}$ is order 4, and this eliminates all other possibilities for groups of order 8.




:::





