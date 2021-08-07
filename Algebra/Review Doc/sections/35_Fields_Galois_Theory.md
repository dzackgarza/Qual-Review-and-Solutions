# General Field Theory

:::{.fact}
\envlist
- All fields are simple rings (no proper nontrivial ideals).
  - Thus every field morphism is either zero or injective.
- The characteristic of any field $k$ is either 0 or $p$ a prime.
- If $L/k$ is algebraic, then $\min(\alpha, L)$ divides $\min(\alpha, k)$.
:::

:::{.proposition title="Towers are multiplicative in degree"}
Let $L/F/k$ be a finite tower of field extensions.
\[
[L : k] = [L: F][F: k]
.\]
:::

## Finite Fields

:::{.theorem title="Construction of Finite Fields"}
$\GF(p^n)\cong \frac{\FF_p}{(f)}$ where $f \in \FF_p[x]$ is any irreducible of degree $n$, and $\GF(p^n) \cong \FF[\alpha] \cong \spanof_\FF\theset{1, \alpha, \cdots, \alpha^{n-1}}$ for any root $\alpha$ of $f$.
:::

:::{.proposition title="Prime Subfields of Finite Fields"}
Every finite field $F$ is isomorphic to a unique field of the form $\GF(p^n)$ and if $\ch F = p$, it has prime subfield $\FF_p$.
:::

:::{.proposition title="Containment of Finite Fields"}
$\GF(p^\ell) \leq \GF(p^k) \iff \ell$ divides $k$.
:::

:::{.proposition title="Identification of Finite Fields as Splitting Fields"}
$\GF(p^n)$ is the splitting field of $\rho(x) = x^{p^n} - x$, and the elements are exactly the roots of $\rho$.
:::

:::{.proof}
Todo.
Every element is a root by Cauchy's theorem, and the $p^n$ roots are distinct since its derivative is identically $-1$.
:::

:::{.proposition title="Splits Product of Irreducibles"}
Let $\rho_n \definedas x^{p^n} - x$.
Then $f(x) \divides \rho_n(x) \iff \deg f \divides n$ and $f$ is irreducible.
:::

:::{.corollary}
$x^{p^n} - x = \prod f_i(x)$ over all irreducible monic $f_i \in \FF_p[x]$ of degree $d$ dividing $n$.
:::

:::{.proof}
$\impliedby$:

- Suppose $f$ is irreducible of degree $d$.
- Then $f \divides x^{p^d} - x$, by considering $F[x]/\gens{f}$.
- Thus $x^{p^d} - x \divides x^{p^n} - x \iff d\divides n$.

$\implies$:

- $\alpha \in \GF(p^n) \iff \alpha^{p^n} - \alpha = 0$, so every element is a root of $\phi_n$ and $\deg \min(\alpha, \FF_p) \divides n$ since $\FF_p(\alpha)$ is an intermediate extension.

- So if $f$ is an irreducible factor of $\phi_n$, $f$ is the minimal polynomial of some root $\alpha$ of $\phi_n$, so $\deg f \divides n$.

-  $\phi_n'(x) = p^nx^{p^{n-1}} \neq 0$, so $\phi_n$ is squarefree and thus has no repeated factors. So $\phi_n$ is the product of all such irreducible $f$.
:::

:::{.proposition title="Finite fields are not algebraically closed"}
If $\FF$ is a finite field then $F\neq \bar{F}$.
:::

:::{.proof}
If \( k = \ts{ a_1, a_2, \cdots a_n } \)  then define the polynomial 
\[
f(x) \da 1 +\prod_{j=1}^n (x-a_j) \in k[x]
.\]
This has no roots in $k$.
:::
\todo{Proof}

## Cyclotomic Polynomials

:::{.definition title="Cyclotomic Polynomials"}
Let $\zeta_n = e^{2\pi i/n}$, then the **$n$th cyclotomic polynomial** is given by
$$
\Phi_{n}(x)=\prod_{k=1 \atop (j, n)=1}^{n}\left(x- \zeta_n^k\right) \in \ZZ[x]
,$$

which is a product over primitive roots of unity.
It is the unique irreducible polynomial which is a divisor of $x^n - 1$ but *not* a divisor of $x^k-1$ for any $k<n$.


Note that $\deg \Phi_n(x) = \phi(n)$ for $\phi$ the totient function.
:::

:::{.definition title="Cyclotomic Field"}
Any subfield of $\SF(x^n-1)$ is a **cyclotomic field**.
:::


:::{.proposition title="Computing Cyclotomic Polynomials"}
**Computing $\Phi_n$:**

1.
$$
\Phi_{n}(z)=\prod_{\substack{ d \divides n \\  d > 0} }\left(z^{d}-1\right)^{\mu\left(\frac{n}{d}\right)}
$$
where
$$
\mu(n) \equiv\left\{ \begin{array}{ll}{0} & {\text { if } n \text { has one or more repeated prime factors }} \\ {1} & {\text { if } n=1} \\ {(-1)^{k}} & {\text { if } n \text { is a product of } k \text { distinct primes, }}\end{array}\right.
$$

2.
\[
x^{n}-1=\prod_{d | n} \Phi_{d}(x) \implies \Phi_n(x) = \qty{x^n-1} \qty{\prod_{d | n \atop d < n} \Phi_{d}(x)}\inv,
\]
so just use polynomial long division.

:::

:::{.fact title="computing cyclotomic polynomials, special cases and examples"}
\[
\Phi_{p}(x)   &=  x^{p-1}+x^{p-2}+\cdots+x+1 \\
\Phi_{2 p}(x) &=  x^{p-1}-x^{p-2}+\cdots-x+1 \\
\\
k\divides n \implies \Phi_{n}(x) &= \Phi_{n\over k}\left(x^{k}\right)
\\ \\
\Phi_1(z) &= z-1 \\
\Phi_2(z) &= z+1 \\
\Phi_4(z) &= z^2+1 \\
\Phi_6(z) &= z^2 -z + 1 \\
\Phi_8(z) &= z^4+1 
.\]
:::

:::{.proposition title="Splitting Fields of Cyclotomic Polynomials"}
The splitting field of $x^m-1$ is $\QQ(\zeta_m)$ for $\zeta_m$ any primitive root of unity, and 
\[
\Gal(\QQ(\zeta_m)_{/\QQ}) \cong (\ZZ/m\ZZ)\units
.\]
:::

:::{.theorem title="Kronecker-Weber"}
If $K_{/\QQ}$ is an abelian extension, then $K \subseteq \QQ(\zeta_m)$ for some $m$.
:::

## Misc


:::{.proposition title="?"}
If $f\in k[x]^{\irr}$ with $\ch k = p$, then there is a unique separable $g\in k[x]^{\irr}$ such that $f(x) = g(x^{p^k})$ for some unique $k$.
:::

:::{.definition title="Separable degree"}
The **separable degree** of an extension $L/k$ is defined by fixing an embedding $\sigma: k\embeds \bar{k}$ and letting $[L:k]_s$ be the number of lifts of $\sigma$ to $\sigma':L\to \bar{k}$:

\begin{tikzcd}
	L && {\bar{k}} \\
	\\
	& k
	\arrow["\sigma"', hook, from=3-2, to=1-3]
	\arrow[dashed, hook, from=1-1, to=1-3]
	\arrow[hook', from=3-2, to=1-1]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsMyxbMSwyLCJrIl0sWzIsMCwiXFxiYXJ7a30iXSxbMCwwLCJMIl0sWzAsMSwiXFxzaWdtYSIsMix7InN0eWxlIjp7InRhaWwiOnsibmFtZSI6Imhvb2siLCJzaWRlIjoidG9wIn19fV0sWzIsMSwiIiwwLHsic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoiaG9vayIsInNpZGUiOiJ0b3AifSwiYm9keSI6eyJuYW1lIjoiZGFzaGVkIn19fV0sWzAsMiwiIiwwLHsic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoiaG9vayIsInNpZGUiOiJib3R0b20ifX19XV0=)

:::

:::{.definition title="Elementary Symmetric Functions"}
\todo[inline]{todo}
:::



:::{.exercise title="?"}
Show 
\[
x^\ell - 1 \divides x^m-1 \iff \ell\divides m
.\]
:::


:::{.solution}

$\implies$
- Write $m = \ell q + r$ with $0\leq r < \ell$.
- Write 
\[
p(x) = {x^m-1 \over x^\ell - 1}
= {x^{lq+r} -1 \over x^\ell - 1}
= x^r{x^{lq} - 1 \over x^\ell - 1} + {x^r - 1 \over x^\ell - 1}
= q(x) + {x^r-1 \over x^\ell - 1}
,\]
where $p,q$ are polynomial by divisibility.
- So the remaining ratio must be polynomial, but since $r<\ell$ is strict this forces $r=0$.
  Thus $\ell \divides m$.

$\impliedby$:

- Write $m = \ell q + r$, then $r=0$ by divisibility.
- Then $x^m-1 = x^{\ell q} - 1 \da z^q-1$ where $z\da x^\ell$. 
- Use that $z-1 \divides z^q - 1$, so $x^{\ell}-1 \divides x{\lq} -1 = x^m-1$.



:::


:::{.exercise title="?"}
Show that if $f \in \FF_p[x]^{\irr}$ is degree $d$,
\[
f \divides x^{p^n}-x \iff d\divides n
.\]
:::


:::{.solution}


:::


