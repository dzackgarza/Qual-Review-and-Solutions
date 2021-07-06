# Field Theory

## Facts and Definitions


:::{.remark}
Let $k$ denote a field, and $L/k$ extension.
Every field morphism is an embedding (injection).
An *embedding* of $k\dash$algebras $L\embeds L'$ will refer to any ring morphism over $k$, i.e. a field morphism that restricts to the identity on $k$:


\begin{tikzcd}
	L && {L'} \\
	\\
	& k
	\arrow[hook', from=3-2, to=1-1]
	\arrow[hook, from=3-2, to=1-3]
	\arrow[hook, from=1-1, to=1-3]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsMyxbMCwwLCJMIl0sWzIsMCwiTCciXSxbMSwyLCJrIl0sWzIsMCwiIiwwLHsic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoiaG9vayIsInNpZGUiOiJib3R0b20ifX19XSxbMiwxLCIiLDIseyJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6InRvcCJ9fX1dLFswLDEsIiIsMCx7InN0eWxlIjp7InRhaWwiOnsibmFtZSI6Imhvb2siLCJzaWRlIjoidG9wIn19fV1d)

More generally, we can ask for lifts of any map $\sigma: k\to k_\sigma$:

\begin{tikzcd}
	L && {L'} \\
	\\
	k && {k_\sigma}
	\arrow[""{name=0, anchor=center, inner sep=0}, hook, from=1-1, to=1-3]
	\arrow[""{name=1, anchor=center, inner sep=0}, "\sigma", hook, from=3-1, to=3-3]
	\arrow[hook, from=3-1, to=1-1]
	\arrow[hook, from=3-3, to=1-3]
	\arrow[shorten <=9pt, shorten >=9pt, Rightarrow, from=1, to=0]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsNCxbMCwwLCJMIl0sWzIsMCwiTCciXSxbMCwyLCJrIl0sWzIsMiwia19cXHNpZ21hIl0sWzAsMSwiIiwwLHsic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoiaG9vayIsInNpZGUiOiJ0b3AifX19XSxbMiwzLCJcXHNpZ21hIiwwLHsic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoiaG9vayIsInNpZGUiOiJ0b3AifX19XSxbMiwwLCIiLDEseyJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6InRvcCJ9fX1dLFszLDEsIiIsMSx7InN0eWxlIjp7InRhaWwiOnsibmFtZSI6Imhvb2siLCJzaWRlIjoidG9wIn19fV0sWzUsNCwiIiwwLHsic2hvcnRlbiI6eyJzb3VyY2UiOjIwLCJ0YXJnZXQiOjIwfX1dXQ==)

Most often, we'll take $\sigma: k\to k$ to be the identity.
:::

:::{.remark}
\envlist

- $[L: K] = \dim_{\Vect_K} L$, the dimension of $L$ as a $K\dash$vector space
- \( \Aut(L/k) \da \ts{ \sigma: L \to L' \st \ro{\sigma}{K} = \one_K } \), the lifts of the identity on $K$.
- \( \ts{ L: K } \da \# \Aut(L/k) \da \ts{ \sigma: L \to L' \st \ro{\sigma}{K} = \one_K} \), the number of lifts of the identity on $K$.
- $\Gal(E/F) \da \Aut_{\Fieldsover{k} }$ if $E$ is finite, normal, and separable.
:::


:::{.definition title="Distinguished Classes"}
A collection of field extensions $\mathcal{S}$ is **distinguished** iff

- For any tower $L/K/k$, $L/k \in \mathcal{S} \iff L/K, K/k\in \mathcal{S}$, and
- If $K/k\in \mathcal{S}$ and $L/k$ is any extension, then $LK/k \in \mathcal{S}$:

\begin{tikzcd}
	L &&&& L \\
	\\
	K && \iff && K \\
	\\
	k &&&& k
	\arrow[hook, from=5-1, to=3-1]
	\arrow[hook, from=3-1, to=1-1]
	\arrow[hook, from=5-5, to=3-5]
	\arrow[hook, from=3-5, to=1-5]
	\arrow[color={rgb,255:red,214;green,92;blue,92}, curve={height=18pt}, dashed, hook, from=5-1, to=1-1]
	\arrow[color={rgb,255:red,214;green,92;blue,92}, curve={height=18pt}, dashed, hook, from=5-5, to=3-5]
	\arrow[color={rgb,255:red,214;green,92;blue,92}, curve={height=18pt}, dashed, hook, from=3-5, to=1-5]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsNyxbMCw0LCJrIl0sWzAsMiwiSyJdLFswLDAsIkwiXSxbNCw0LCJrIl0sWzQsMiwiSyJdLFs0LDAsIkwiXSxbMiwyLCJcXGlmZiJdLFswLDEsIiIsMCx7InN0eWxlIjp7InRhaWwiOnsibmFtZSI6Imhvb2siLCJzaWRlIjoidG9wIn19fV0sWzEsMiwiIiwwLHsic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoiaG9vayIsInNpZGUiOiJ0b3AifX19XSxbMyw0LCIiLDAseyJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6InRvcCJ9fX1dLFs0LDUsIiIsMCx7InN0eWxlIjp7InRhaWwiOnsibmFtZSI6Imhvb2siLCJzaWRlIjoidG9wIn19fV0sWzAsMiwiIiwyLHsiY3VydmUiOjMsImNvbG91ciI6WzAsNjAsNjBdLCJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6InRvcCJ9LCJib2R5Ijp7Im5hbWUiOiJkYXNoZWQifX19XSxbMyw0LCIiLDIseyJjdXJ2ZSI6MywiY29sb3VyIjpbMCw2MCw2MF0sInN0eWxlIjp7InRhaWwiOnsibmFtZSI6Imhvb2siLCJzaWRlIjoidG9wIn0sImJvZHkiOnsibmFtZSI6ImRhc2hlZCJ9fX1dLFs0LDUsIiIsMix7ImN1cnZlIjozLCJjb2xvdXIiOlswLDYwLDYwXSwic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoiaG9vayIsInNpZGUiOiJ0b3AifSwiYm9keSI6eyJuYW1lIjoiZGFzaGVkIn19fV1d)

\begin{tikzcd}
	& LK \\
	L && K \\
	& k
	\arrow[color={rgb,255:red,214;green,92;blue,92}, hook, from=3-2, to=2-3]
	\arrow[hook', from=3-2, to=2-1]
	\arrow[hook', from=2-1, to=1-2]
	\arrow[hook, from=2-3, to=1-2]
	\arrow[color={rgb,255:red,214;green,92;blue,92}, dashed, hook, from=3-2, to=1-2]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsNCxbMSwyLCJrIl0sWzIsMSwiSyJdLFswLDEsIkwiXSxbMSwwLCJMSyJdLFswLDEsIiIsMCx7ImNvbG91ciI6WzAsNjAsNjBdLCJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6InRvcCJ9fX1dLFswLDIsIiIsMix7InN0eWxlIjp7InRhaWwiOnsibmFtZSI6Imhvb2siLCJzaWRlIjoiYm90dG9tIn19fV0sWzIsMywiIiwyLHsic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoiaG9vayIsInNpZGUiOiJib3R0b20ifX19XSxbMSwzLCIiLDAseyJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6InRvcCJ9fX1dLFswLDMsIiIsMSx7ImNvbG91ciI6WzAsNjAsNjBdLCJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6InRvcCJ9LCJib2R5Ijp7Im5hbWUiOiJkYXNoZWQifX19XV0=)

:::





:::{.definition title="Simple Extensions"}
An extension $L/k$ is **simple** iff $L = K( \alpha)$ for some \( \alpha\in L \).
:::


:::{.definition title="Fixed Field"}
For $H \leq \Aut_{\Fieldsover{k}}(L)$,
\[
L^H \da \ts{ \ell \in L \st  \sigma(l) = \ell }
.\]

:::



:::{.definition title="Prime Subfield"}
The **prime subfield** of a field $F$ is the subfield generated by $1$.
:::

:::{.fact}
\envlist

- Irreducible $\implies$ separable.
- The minimal polynomial of an algebraic element is always irreducible.
- Every irreducible polynomial over a perfect field is separable.
- Every finite extension of a perfect field is separable. 
:::

:::{.definition title="Field Automorphisms"}
\[ 
\Aut(L/k) = \theset{\sigma: L \to L \suchthat \restrictionof{\sigma}{k} = \id_k}
.\]

:::{.definition title="Reducible and Irreducible Polynomials"}
For $\FF$ a field, a polynomial $f\in \FF[x]$ is **reducible** if and only if $f$ can be factored as $f(x) = g(x) h(x)$ for some $g, h\in \FF[x]$ with $\deg g, \deg h \geq 1$ (so $g, h$ are nonconstant).
$f$ is **irreducible** if $f$ is not reducible.
:::

:::

:::{.remark}
Note that in general, 
\[
\abs{ \Aut(L/k) } \leq [L: K]
.\]

:::

:::{.definition title="Characterizations of Perfect Fields"}
The following are equivalent:

- $k$ is a **perfect** field.

- Every irreducible polynomial $p\in k[x]$ is separable

- Every finite extension $F/k$ is separable.

- If $\ch k > 0$, the Frobenius is an automorphism of $k$.
:::

:::{.fact}
\envlist
- The characteristic of any field $k$ is either 0 or $p$ a prime.
- All fields are simple rings (no proper nontrivial ideals).
- If $L/k$ is algebraic, then $\min(\alpha, L)$ divides $\min(\alpha, k)$.
- Every field morphism is either zero or injective.
:::

:::{.theorem title="Gauss' Lemma"}
Let $R$ be a UFD and $F$ its field of fractions.
Then a primitive $p\in R[x]$ is irreducible in $R[x] \iff p$ is irreducible in $F[x]$.
:::

:::{.corollary}
A primitive polynomial $p\in \QQ[x]$ is irreducible $\iff p$ is irreducible in $\ZZ[x]$.
:::

:::{.theorem title="Eisenstein's Criterion"}
If $f(x) = \sum_{i=0}^n \alpha_i x^i \in \QQ[x]$ and $\exists p$ such that

- $p$ divides every coefficient *except* $a_n$ and
- $p^2$ does not divide $a_0$,

then $f$ is irreducible over $\QQ[x]$, and by Gauss' lemma, over $\ZZ[x]$.
:::

:::{.definition title="Elementary Symmetric Functions"}
Todo
:::

## Extensions




:::{.definition title="Algebraic Field Extension"}
A field extension $L/k$ is **algebraic** iff every $\alpha \in L$ is the root of some polynomial $f\in k[x]$.
:::

:::{.proposition title="Normal Field Extension"}
Let $L/k$ be an extension.
Then TFAE:

- $L/k$ is **normal**.

- Every irreducible polynomial $f\in k[x]$ that has one root in $L$ has *all* of its roots in $L$
  - So if $\alpha\in L$ then every Galois conjugate $\alpha_k \in L$ as well..
   Thus either $f$ splits in $L$ or $f$ has no roots in $L$.

- Every embedding $\sigma: L \injects \bar{k}$ over $k$ satisfies $\sigma(L) = L$, so $\sigma$ is an automorphism of $L$ over $k$.

- If $L$ is separable: $L$ is the splitting field of some irreducible $f\in k[x]$.
:::


:::{.example title="of normal extensions"}
\envlist

- If $[L: k] = 2$ then $L/k$ is normal.
- $L \da \QQ(2^{1\over 3})$ is not normal, since $(x^3-2) = \prod_k x-\zeta_3^k 2^{1\over 3}$ with $\zeta_3, \zeta_3^2$ not in $L \subset \RR$.
- $\QQ(\zeta_k)$ is normal for $\zeta_k$ any primitive $k$th root of unity.
:::


:::{.proof title="?"}
\todo[inline]{todo}
:::

:::{.definition title="Separable Field Extension"}
Let $L/k$ be a field extension, $\alpha \in L$ be arbitrary, and $f(x) \definedas\min(\alpha, k)$.
The following are equivalent 

- $L/k$ is **separable**
- Every element ${\alpha} \in L$ has separable minimal polynomial $\min_{\alpha, L}(x) \in \bar{k}[x]$ (D&F's definition, p. 551).
- $f$ has no repeated factors/roots, i.e. $f$ has distinct roots in $L$.
- $\gcd(f, f') = 1$.
- $f' \not\equiv 0$

If $L/k$ is a finite extension, then, TFAE:

- $L/k$ is separable.
- \( L = k( \alpha) \) for \( \alpha \)  a separable element.
- \( L = k( \ts{ \alpha_i } ) \) for \( \alpha_i \) separable elements
- $[L: k] = \ts{ L: k } \da \# \Aut_{\Fieldsover k}(L)$

:::

:::{.definition title="Galois Extension and Galois Group"}
Let $L/k$ be a finite field extension.
The following are equivalent:

1. \( L/k \) is a **Galois extension**.
2. $\# \Aut_{\Fieldsover{k}} (L) = [L: k] = \ts{ L: k}$ (D&F's definition).
3. The fixed field of $\mathrm{Aut}(L/k)$ is exactly $k$.
4. $L$ is the splitting field of a separable polynomial $p\in K[x]$.
5. $L$ is finite, normal, and separable (most general definition?)
- $L$ is a finite separable splitting field of an irreducible polynomial.
- $L/k$ is separable and normal.
- The fixed field $L^H$ for $H \da \Aut_{\Fieldsover{k}}(L)$ is precisely $k$.

In this case, we define the **Galois group** as 
\[
\Gal(L/k) \definedas \Aut_{\Fieldsover{k}} (L)
.\]
:::

:::{.definition title="Simple Extension"}
An extension $F/k$ is **simple** if $F = k[\alpha]$ for a single element $\alpha$.
:::

:::{.definition title="Primitive Extension"}
For $R$ a UFD, a polynomial $p\in R[x]$ is **primitive** iff the greatest common divisors of its coefficients is a unit.
:::

:::{.proposition title="Classification of quadratic extensions"}
\todo[inline]{todo}
If $\FF$ is a field with $\ch(\FF)\neq 2$ and $E_{/\FF}$ is a degree 2 extension, then $E$ is Galois and $E = F(\sqrt{a})$ for some squarefree $a\in \FF$.
:::

:::{.corollary title="Quadratic extensions of rationals"}
If $E_{/\QQ}$ is a quadratic extension, $E = \QQ(\sqrt{p\over q})$ for some $p, q\in \ZZ$.
:::

:::{.proposition title="?"}
For $\FF_p$ a finite field of prime order, all quadratic extensions $E/\FF_p$ are isomorphic.
:::

:::{.theorem title="Finite Extensions are Algebraic"}
Every finite extension is algebraic.
:::

:::{.proof}
If \( K/F \) and \( [K:F] = n \), then pick any \( \alpha \in K \) and consider \( 1, \alpha , \alpha ^2, ...  \).
This yields \( n+1 \) elements in an \( n\dash \)dimensional vector space, and thus there is a linear dependence 
\[
f(\alpha ) \da \sum_{j=1}^n c_j \alpha ^j = 0
.\]
But then \( \alpha \) is the root of the polynomial \( f \).

:::

:::{.theorem title="Primitive Element Theorem"}
Every finite separable extension is simple.
:::

:::{.corollary}
$\GF(p^n)$ is a simple extension over $\FF_p$.
:::


:::{.proposition title="?"}
If $L/k$ is separable, then
\[
[L: k] = \ts{ L: k } 
.\]
If $L/k$ is a splitting field, then
\[
[L:K] = \# \Aut_{\Fieldsover{k}}(L) \da \# \Gal(L/k)
.\]

:::


## Finite Fields

:::{.theorem title="Characterization of Prime Subfields"}
The prime subfield of any field is isomorphic to either $\QQ$ or $\FF_p$ for some $p$.
:::

:::{.proposition}
If $\ch k = p$ then $(a+b)^p = a^p + b^p$ and $(ab)^p = a^p b^p$.
:::

:::{.proof}
Todo
:::
\todo{Proof}

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

:::{.definition title="Cyclotomic Field"}
Any subfield of the splitting field $E$ of $f(x) = x^m-1$ is a **cyclotomic field**.
:::

:::{.proposition}
$\deg \Phi_n(x) = \phi(n)$ for $\phi$ the totient function.
:::

:::{.proof}
$\deg \Phi_n(x)$ is the number of $n$th primitive roots, which is the number of numbers less than and coprime to $n$.
:::

:::{.proposition title="Computing Totient Functions"}
**Computing $\Phi_n$:**

1.
$$
\Phi_{n}(z)=\prod_{d | n, d>0}\left(z^{d}-1\right)^{\mu\left(\frac{n}{d}\right)}
$$
where
$$
\mu(n) \equiv\left\{ \begin{array}{ll}{0} & {\text { if } n \text { has one or more repeated prime factors }} \\ {1} & {\text { if } n=1} \\ {(-1)^{k}} & {\text { if } n \text { is a product of } k \text { distinct primes, }}\end{array}\right.
$$

2.
\[
x^{n}-1=\prod_{d | n} \Phi_{d}(x) \implies \Phi_n(x) = \frac{x^n-1}{\prod_{d | n \atop d < n} \Phi_{d}(x)},
\]
so just use polynomial long division.

:::

:::{.proposition}
\[
\Phi_{p}(x)   &=  x^{p-1}+x^{p-2}+\cdots+x+1 \\
\Phi_{2 p}(x) &=  x^{p-1}-x^{p-2}+\cdots-x+1
\]
:::

:::{.proposition}
\[
k\divides n \implies \Phi_{n k}(x)=\Phi_{n}\left(x^{k}\right)
\]
:::

:::{.definition title="Cyclotomic Polynomials"}
Let $\zeta_n = e^{2\pi i/n}$, then the **$n$th cyclotomic polynomial** is given by
$$
\Phi_{n}(x)=\prod_{k=1 \atop (j, n)=1}^{n}\left(x- \zeta_n^k\right) \in \ZZ[x]
,$$

which is a product over primitive roots of unity.
It is the unique irreducible polynomial which is a divisor of $x^n - 1$ but *not* a divisor of $x^k-1$ for any $k<n$.
:::

:::{.proposition title="Table of cyclotomic polynomials"}
\todo[inline]{todo}
:::

:::{.proposition title="Galois Groups of Cyclotomic Fields"}
For $\zeta$ any primitive root of unity, $\Gal(\QQ(\zeta_m)_{/\QQ}) \cong (\ZZ/m\ZZ)\units$.
:::

:::{.theorem title="Kronecker-Weber"}
If $K_{/\QQ}$ is an abelian extension, then $K \subseteq \QQ(\zeta_m)$ for some $m$.
:::


## Splitting Fields

:::{.proposition title="Splitting Fields of Cyclotomic Polynomials"}
The splitting field of $x^m-1$ is $\QQ(\zeta_m)$ for $\zeta_m$ any primitive root of unity.
:::



## Unsorted


:::{.proposition title="?"}
A polynomial $f$ has multiple roots $\iff \gcd(f, f') \neq 1$, and the multiple roots of $f$ are precisely the roots of $\gcd(f, f')$.
:::

:::{.proposition title="?"}
Irreducible polynomials have distinct roots after passing to a splitting field.
:::

:::{.proof title="?"}
\todo[inline]{todo}

:::


