# Fields and Galois Theory

## Spring 2020 #3

Let $E$ be an extension field of $F$ and $\alpha\in E$ be algebraic of odd degree over $F$.

a. Show that $F(\alpha) = F(\alpha^2)$.

b. Prove that $\alpha^{2020}$ is algebraic of odd degree over $F$.

## Spring 2020 #4

Let $f(x) = x^4-2 \in \QQ[x]$.

a. Define what it means for a finite extension field $E$ of a field $F$ to be a Galois extension.

b. Determine the Galois group $\gal(E/\QQ)$ for the polynomial $f(x)$, and justify your answer carefully.

c. Exhibit a subfield $K$ in $(b)$ such that $\QQ \leq K \leq E$ with $K$ not a Galois extension over $\QQ$. Explain.

## Fall 2019 #4 $\bowtie$

Let $F$ be a finite field with $q$ elements.

Let $n$ be a positive integer relatively prime to $q$ and let $\omega$ be a primitive $n$th root of unity in an extension field of $F$.

Let $E = F [\omega]$ and let $k = [E : F]$.

(a) Prove that $n$ divides $q^{k}-1$.

(b) Let $m$ be the order of $q$ in $\ZZ/n\ZZ\units$.
Prove that $m$ divides $k$.

(c) Prove that $m = k$.

:::{.solution}

Concepts used:

- Theorem: $F\units$ is always cyclic for $F$ a field

**Solution**:

### a

Since $\abs{F} = q$ and $[E:F] = k$, we have $\abs{E} = q^k$ and $\abs{E\units} = q^k-1$.
Noting that $\zeta \in E\units$ we must have $n = o(\zeta) \divides \abs{E\units} = q^k-1$ by Lagrange's theorem.

### b

Rephrasing (a), we have 
\[
n \divides q^k-1 
&\iff q^k-1 \cong 0 \mod n \\
&\iff q^k \cong 1 \mod n \\
&\iff m \definedas o(q) \divides k
.\]

### c

Since $m\divides k \iff k = \ell m$, (**claim**) there is an intermediate subfield $M$ such that
\[
E \leq M \leq F \quad k = [F:E] = [F:M] [M:E] = \ell m
,\]

so $M$ is a degree $m$ extension of $E$.

Now consider $M\units$. 
By the argument in (a), $n$ divides $q^m - 1 = \abs{M\units}$, and $M\units$ is cyclic, so it contains a cyclic subgroup $H$ of order $n$.

But then $x\in H \implies p(x)\definedas x^n-1 = 0$, and since $p(x)$ has at most $n$ roots in a field. 
So $H = \theset{x \in M \suchthat x^n-1 = 0}$, i.e. $H$ contains all solutions to $x^n-1$ in $E[x]$.

But $\zeta$ is one such solution, so $\zeta \in H \subset M\units \subset M$.
Since $F[\zeta]$ is the smallest field extension containing $\zeta$, we must have $F = M$, so $\ell = 1$, and $k = m$.

\todo{Revisit. Tricky!}


:::



## Fall 2019 #7 $\bowtie$

Let $\zeta_n$ denote a primitive $n$th root of 1 $\in \QQ$.
You may assume the roots of the minimal polynomial $p_n(x)$ of $\zeta_n$ are exactly the primitive $n$th roots of 1.

Show that the field extension $\QQ(\zeta_n )$ over $\QQ$ is Galois and prove its Galois group is $(\ZZ/n\ZZ)\units$.

How many subfields are there of $\QQ(\zeta_{20} )$?

:::{.solution}

Concepts Used:

- **Galois** = normal + separable.

- **Separable**: Minimal polynomial of every element has distinct roots.

- **Normal (if separable)**: Splitting field of an irreducible polynomial.

- Definition: $\zeta$ is a primitive root of unity iff $o(\zeta) = n$ in $F\units$.
 
- $\phi(p^k) = p^{k-1}(p-1)$

- The lattice: 

![](figures/2019-12-24-13-19-15.png)

**Solution**:

Let $K = \QQ(\zeta)$. 
Then $K$ is the splitting field of $f(x) = x^n - 1$, which is irreducible over $\QQ$, so $K/\QQ$ is normal.
We also have $f'(x) = nx^{n-1}$ and $\gcd(f, f') = 1$ since they can not share any roots.

> Or equivalently, $f$ splits into distinct linear factors $f(x) = \prod_{k\leq n}(x-\zeta^k)$.

Since it is a Galois extension, $\abs{\Gal(K/\QQ)} = [K: \QQ] = \phi(n)$ for the totient function.

We can now define maps
\[
\tau_j: K &\to K \\
\zeta &\mapsto \zeta^j 
\]

and if we restrict to $j$ such that $\gcd(n, j) = 1$, this yields $\phi(n)$ maps.
Noting that if $\zeta$ is a primitive root, then $(n, j) = 1$ implies that that $\zeta^j$ is also a primitive root, and hence another root of $\min(\zeta, \QQ)$, and so these are in fact automorphisms of $K$ that fix $\QQ$ and thus elements of $\Gal(K/\QQ)$.

So define a map
\[
\theta: \ZZ_n\units &\to K \\
[j]_n &\mapsto \tau_j
.\]

from the *multiplicative* group of units to the Galois group.

The claim is that this is a surjective homomorphism, and since both groups are the same size, an isomorphism.

**Surjectivity:**

Letting $\sigma \in K$ be arbitrary, noting that $[K: \QQ]$ has a basis $\theset{1, \zeta, \zeta^2, \cdots, \zeta^{n-1}}$, it suffices to specify $\sigma(\zeta)$ to fully determine the automorphism.
(Since $\sigma(\zeta^k) = \sigma(\zeta)^k$.)

In particular, $\sigma(\zeta)$ satisfies the polynomial $x^n - 1$, since $\sigma(\zeta)^n = \sigma(\zeta^n) = \sigma(1) = 1$, which means $\sigma(\zeta)$ is another root of unity and $\sigma(\zeta) = \zeta^k$ for some $1\leq k \leq n$.

Moreover, since $o(\zeta) = n \in K\units$, we must have $o(\zeta^k) = n \in K\units$ as well. Noting that $\theset{\zeta^i}$ forms a cyclic subgroup $H\leq K\units$, then $o(\zeta^k) = n \iff (n, k) = 1$ (by general theory of cyclic groups).

Thus $\theta$ is surjective.

**Homomorphism:**

\[
\tau_j \circ \tau_k (\zeta) =\tau_j(\zeta^k) = \zeta^{jk} \implies
\tau_{jk} = \theta(jk) = \tau_j \circ \tau_k
.\]

**Part 2:**

We have $K \cong \ZZ_{20}\units$ and $\phi(20) = 8$, so $K \cong \ZZ_8$, so we have the following subgroups and corresponding intermediate fields:

- $0 \sim \QQ(\zeta_{20})$
- $\ZZ_2 \sim \QQ(\omega_1)$
- $\ZZ_4 \sim \QQ(\omega_2)$
- $\ZZ_8 \sim \QQ$

For some elements $\omega_i$ which exist by the primitive element theorem.



:::

## Spring 2019 #2 $\bowtie$

Let $F = \FF_p$ , where $p$ is a prime number.

(a) Show that if $\pi(x) \in F[x]$ is irreducible of degree $d$, then $\pi(x)$ divides $x^{p^d} - x$.


(b) Show that if $\pi(x) \in F[x]$ is an irreducible polynomial that divides $x^{p^n} - x$,
then $\deg \pi(x)$ divides $n$.

:::{.solution}

### (a)

> Go to a field extension.
> Orders of multiplicative groups for finite fields are known.

We can consider the quotient $K = \displaystyle{\frac{\FF_p[x]}{\generators{\pi(x)}}}$, which since $\pi(x)$ is irreducible is an extension of $\FF_p$ of degree $d$ and thus a field of size $p^d$ with a natural quotient map of rings $\rho: \FF_p[x] \to K$.

Since $K\units$ is a group of size $p^d-1$, we know that for any $y \in K\units$, we have by Lagrange's theorem that the order of $y$ divides $p^d-1$ and so $y^{p^d} = y$.

So every element in $K$ is a root of $q(x) = x^{p^d}-x$.

Since $\rho$ is a ring morphism, we have

\[
\rho(q(x)) = \rho(x^{p^d} - x) = \rho(x)^{p^d} - \rho(x)
&= 0 \in K \\
&\iff q(x) \in \ker \rho \\
&\iff q(x) \in \generators{\pi(x)} \\
&\iff \pi(x) \divides q(x) = x^{p^d}-x \quad\text{"to contain is to divide"}
.\]

$\qed$

### (b)

> Some potentially useful facts:
>
> - $\GF(p^n)$ is the splitting field of $x^{p^n} - x \in \FF_p[x]$.
> - $x^{p^d} - x \divides x^{p^n} - x \iff d \divides n$
> - $\GF(p^d) \leq \GF(p^n) \iff d\divides n$
> - $x^{p^n} - x = \prod f_i(x)$ over all irreducible monic $f_i$ of degree $d$ dividing $n$.

Claim: $\pi(x)$ divides $x^{p^n}-x \iff \deg \pi$ divides $n$.

$\implies$:
Let $L \cong \GF(p^n)$ be the splitting field of $\phi_n(x) \definedas x^{p^n}-x$; then since $\pi \divides \phi_n$ by assumption, $\pi$ splits in $L$.
Let $\alpha \in L$ be any root of $\pi$; then there is a tower of extensions $\FF_p \leq \FF_p(\alpha) \leq L$.

Then $\FF_p \leq \FF_p(\alpha) \leq L$, and so
\[
n &= [L: \FF_p] \\
&= [L: \FF_p(\alpha)]~[\FF_p(\alpha): \FF_p] \\
&= \ell d
,\]

for some $\ell \in \ZZ^{\geq 1}$, so $d$ divides $n$.


$\impliedby$:
If $d\divides n$, use the fact (claim) that $x^{p^n} - x = \prod f_i(x)$ over all irreducible monic $f_i$ of degree $d$ dividing $n$. 
So $f = f_i$ for some $i$.


:::



## Spring 2019 #8 $\bowtie$

Let $\zeta = e^{2\pi i/8}$.

(a) What is the degree of $\QQ(\zeta)/\QQ$?

(b) How many quadratic subfields of $\QQ(\zeta)$ are there?

(c) What is the degree of $\QQ(\zeta, \sqrt[4] 2)$ over $\QQ$?


:::{.solution}

Concepts used:

- $\zeta_n \definedas e^{2\pi i \over n}$, and $\zeta_n^k$ is a primitive $n$th root of unity $\iff \gcd(n, k) = 1$
  - In general, $\zeta_n^k$ is a primitive ${n \over \gcd(n, k)}$th root of unity.
- $\deg \Phi_n(x) = \phi(n)$
- $\phi(p^k) = p^k - p^{k-1} = p^{k-1}(p-1)$ (proof: for a nontrivial gcd, the possibilities are $p, 2p, 3p, 4p, \cdots, p^{k-2}p, p^{k-1}p$.)
- $\Gal(\QQ(\zeta)/\QQ) \cong \ZZ/(n)\units$

**Solution**:

Let $K = \QQ(\zeta)$

### a

- $\zeta \definedas e^{2\pi i / 8}$ is a primitive $8$th root of unity
- The minimal polynomial of an $n$th root of unity is the $n$th cyclotomic polynomial $\Phi_n$
- The degree of the field extension is the degree of $\Phi_8$, which is
\[
\phi(8) = \phi(2^3) = 2^{3-1} \cdot (2-1) = 4
.\]
- So $[\QQ(\zeta): \QQ] = 4$.

### b
- $\Gal(\QQ(\zeta)/\QQ) \cong \ZZ/(8)\units \cong \ZZ/(4)$ by general theory 
- $\ZZ/(4)$ has exactly one subgroup of index 2.
- Thus there is exactly **one** intermediate field of degree 2 (a quadratic extension).

### c
- Let $L = \QQ(\zeta, \sqrt[4] 2)$.

- Note $\QQ(\zeta) = \QQ(i, \sqrt 2)$
  - $\QQ(i, \sqrt{2})\subseteq \QQ(\zeta)$
    - $\zeta_8^2 = i$, and $\zeta_8 = \sqrt{2}\inv + i\sqrt{2}\inv$ so $\zeta_8 + \zeta_8 \inv = 2/\sqrt{2} = \sqrt{2}$.
  - $\QQ(\zeta) \subseteq \QQ(i, \sqrt{2})$: 
    - $\zeta = e^{2\pi i / 8} = \sin(\pi/4) + i\cos(\pi/4) = {\sqrt 2 \over 2}\qty{1+i}$.

- Thus $L = \QQ(i, \sqrt{2})(\sqrt[4]{2}) = \QQ(i, \sqrt 2, \sqrt[4] 2) = \QQ(i, \sqrt[4]{2})$.
  - Uses the fact that $\QQ(\sqrt 2) \subseteq \QQ(\sqrt[4] 2)$ since $\sqrt[4]{2}^2 = \sqrt{2}$ 

- Conclude
\[
[L: \QQ] = [L: \QQ(\sqrt[4] 2)] ~[\QQ(\sqrt[4] 2): \QQ] = 2 \cdot 4 = 8
\]
  using the fact that the minimal polynomial of $i$ over any subfield of $\RR$ is always $x^2 + 1$, so $\min_{\QQ(\sqrt[4] 2)}(i) = x^2 + 1$ which is degree 2.


:::



## Fall 2018 #3

Let $F \subset K \subset L$ be finite degree field extensions.
For each of the following assertions, give a proof or a counterexample.

(a) If $L/F$ is Galois, then so is $K/F$.

(b) If $L/F$ is Galois, then so is $L/K$.

(c) If $K/F$ and $L/K$ are both Galois, then so is $L/F$.


## Spring 2018 #2

Let $f(x) = x^4 - 4x^2 + 2 \in \QQ[x]$.

(a) Find the splitting field $K$ of $f$, and compute $[K: \QQ]$.

(b) Find the Galois group $G$ of $f$, both as an explicit group of automorphisms, and as a familiar abstract group to which it is isomorphic.

(c) Exhibit explicitly the correspondence between subgroups of $G$ and intermediate fields between $\QQ$ and $k$.

## Spring 2018 #3

Let $K$ be a Galois extension of $\QQ$ with Galois group $G$, and let $E_1 , E_2$ be intermediate fields of $K$ which are the splitting fields of irreducible $f_i (x) \in \QQ[x]$. 

Let $E = E_1 E_2 \subset K$. 

Let $H_i = \Gal(K/E_i)$ and $H = \Gal(K/E)$.

(a) Show that $H = H_1 \cap H_2$.

(b) Show that $H_1 H_2$ is a subgroup of $G$.

(c) Show that 
$$
\Gal(K/(E_1 \cap E_2 )) = H_1 H_2
.$$

## Fall 2017 #3

Let $F$ be a field. Let $f(x)$ be an irreducible polynomial in $F[x]$ of degree $n$ and let $g(x)$
be any polynomial in $F[x]$. Let $p(x)$ be an irreducible factor (of degree $m$) of the polynomial $f(g(x))$.

Prove that $n$ divides $m$. Use this to prove that if $r$ is an integer which is not a perfect square, and $n$ is a positive integer then every irreducible factor of $x^{2n} - r$ over $\QQ[x]$ has even degree.

## Fall 2017 #4

(a) Let $f (x)$ be an irreducible polynomial of degree 4 in $\QQ[x]$ whose splitting field $K$ over $\QQ$ has Galois group $G = S_4$. 

    Let $\theta$ be a root of $f(x)$. Prove that $\QQ[\theta]$ is an extension of $\QQ$ of degree 4 and that there are no intermediate fields between $\QQ$ and $\QQ[\theta]$.

(b) Prove that if $K$ is a Galois extension of $\QQ$ of degree 4, then there is an intermediate subfield between $K$ and $\QQ$.



## Spring 2017 #7 

Let $F$ be a field and let $f(x) \in F[x]$.

a. Define what a splitting field of $f(x)$ over $F$ is.

b. Let $F$ now be a finite field with $q$ elements.
  Let $E/F$ be a finite extension of degree $n>0$.
  Exhibit an explicit polynomial $g(x) \in F[x]$ such that $E/F$ is a splitting field of $g(x)$ over $F$.
  Fully justify your answer.

c. Show that the extension $E/F$ in (b) is a Galois extension.


## Spring 2017 #8

a. Let $K$ denote the splitting field of $x^5 - 2$ over $\QQ$.
  Show that the Galois group of $K/\QQ$ is isomorphic to the group of invertible matrices

  \[
  \left(\begin{array}{ll}
  a & b \\
  0 & 1
  \end{array}\right) 
  \qtext{where} a\in \FF_5\units \text{ and } b\in \FF_5
  .\]

b. Determine all intermediate fields between $K$ and $\QQ$ which are Galois over $\QQ$.


## Fall 2016 #4

Set $f(x) = x^3 - 5 \in \QQ[x]$.

a. Find the splitting field $K$ of $f(x)$ over $\QQ$.

b. Find the Galois group $G$ of $K$ over $\QQ$.

c. Exhibit explicitly the correspondence between subgroups of $G$ and intermediate fields between $\QQ$ and $K$.


## $\star$ Fall 2016 #5

How many monic irreducible polynomials over $\FF_p$ of prime degree $\ell$ are there?
Justify your answer.


## Spring 2016 #2

Let $K = \QQ[\sqrt 2 + \sqrt 5]$.

a. Find $[K: \QQ]$.

b. Show that $K/\QQ$ is Galois, and find the Galois group $G$ of $K/\QQ$.

c. Exhibit explicitly the correspondence between subgroups of $G$ and intermediate fields between $\QQ$ and $K$.


## Spring 2016 #6

Let $K$ be a Galois extension of a field $F$ with $[K: F] = 2015$.
Prove that $K$ is an extension by radicals of the field $F$.


## Fall 2015 #5
Let $u = \sqrt{2 + \sqrt{2}}$, $v = \sqrt{2 - \sqrt{2}}$, and $E = \QQ(u)$.

a. Find (with justification) the minimal polynomial $f(x)$ of $u$ over $\QQ$.

b. Show $v\in E$, and show that $E$ is a splitting field of $f(x)$ over $\QQ$.

c. Determine the Galois group of $E$ over $\QQ$ and determine all of the intermediate fields $F$ such that $\QQ \subset F \subset E$.


## Fall 2015 #6

a. Let $G$ be a finite group.
  Show that there exists a field extension $K/F$ with $\gal(K/F) = G$.

  > You may assume that for any natural number $n$ there is a field extension with Galois group $S_n$.

b. Let $K$ be a Galois extension of $F$ with $\abs{\gal(K/F)} = 12$.
  Prove that there exists an intermediate field $E$ of $K/F$ with $[E: F] = 3$.

c. With $K/F$ as in (b), does an intermediate field $L$ necessarily exist satisfying $[L: F] = 2$?
  Give a proof or counterexample.


## Spring 2015 #2
Let $\FF$ be a finite field.

a. Give (with proof) the decomposition of the additive group $(\FF, +)$ into a direct sum of cyclic groups.

b. The *exponent* of a finite group is the least common multiple of the orders of its elements.
  Prove that a finite abelian group has an element of order equal to its exponent.

c. Prove that the multiplicative group $(\FF\units, \cdot)$ is cyclic.


## Spring 2015 #5
Let $f(x) = x^4 - 5 \in \QQ[x]$.

a. Compute the Galois group of $f$ over $\QQ$.
b. Compute the Galois group of $f$ over $\QQ(\sqrt{5})$.


## Fall 2014 #1
Let $f\in \QQ[x]$ be an irreducible polynomial and $L$ a finite Galois extension of $\QQ$.
Let $f(x) = g_1(x)g_2(x)\cdots g_r(x)$ be a factorization of $f$ into irreducibles in $L[x]$.

a. Prove that each of the factors $g_i(x)$ has the same degree.

b. Give an example showing that if $L$ is not Galois over $\QQ$, the conclusion of part (a) need not hold.



## Fall 2014 #3
Consider the polynomial $f(x) = x^4 - 7 \in \QQ[x]$ and let $E/\QQ$ be the splitting field of $f$.

a. What is the structure of the Galois group of $E/\QQ$?

b. Give an explicit description of all of the intermediate subfields $\QQ \subset K \subset E$ in the form $K = \QQ(\alpha), \QQ(\alpha, \beta), \cdots$ where $\alpha, \beta$, etc are complex numbers.
  Describe the corresponding subgroups of the Galois group.

## Spring 2014 #3
Let $F\subset C$ be a field extension with $C$ algebraically closed.

a. Prove that the intermediate field $C_{\text{alg}} \subset C$ consisting of elements algebraic over $F$ is algebraically closed.

b. Prove that if $F\to E$ is an algebraic extension, there exists a homomorphism $E\to C$ that is the identity on $F$.


## Spring 2014 #4
Let $E\subset \CC$ denote the splitting field over $\QQ$ of the polynomial $x^3 - 11$.

a. Prove that if $n$ is a squarefree positive integer, then $\sqrt{n}\not\in E$.

  > Hint: you can describe all quadratic extensions of $\QQ$ contained in $E$.

b. Find the Galois group of $(x^3 - 11)(x^2 - 2)$ over $\QQ$.

c. Prove that the minimal polynomial of $11^{1/3} + 2^{1/2}$ over $\QQ$ has degree 6.

## Fall 2013 #5
Let $L/K$ be a finite extension of fields.

a. Define what it means for $L/K$ to be *separable*.

b. Show that if $K$ is a finite field, then $L/K$ is always separable.

c. Give an example of a finite extension $L/K$ that is not separable.


## Fall 2013 #6
Let $K$ be the splitting field of $x^4-2$ over $\QQ$ and set $G = \gal(K/\QQ)$.

a. Show that $K/\QQ$ contains both $\QQ(i)$ and $\QQ(\sqrt[4]{2})$ and has degree 8 over $\QQ$/

b. Let $N = \gal(K/\QQ(i))$ and $H = \gal(K/\QQ(\sqrt[4]{2}))$.
  Show that $N$ is normal in $G$ and $NH = G$.

  > Hint: what field is fixed by $NH$?

c. Show that $\gal(K/\QQ)$ is generated by elements $\sigma, \tau$, of orders 4 and 2 respectively, with $\tau \sigma\tau\inv = \sigma\inv$.

  > Equivalently, show it is the dihedral group of order 8.

d. How many distinct quartic subfields of $K$ are there? 
  Justify your answer.



## $\star$ Fall 2013 #7
Let $F = \FF_2$ and let $\bar F$ denote its algebraic closure.

a. Show that $\bar F$ is not a finite extension of $F$.

b. Suppose that $\alpha \in \bar F$ satisfies $\alpha^{17} = 1$ and $\alpha\neq 1$.
  Show that $F(\alpha)/F$ has degree 8.

## Spring 2013 #7
Let $f(x) = g(x) h(x) \in \QQ[x]$ and $E,B,C/\QQ$ be the splitting fields of $f,g,h$ respectively.

a. Prove that $\gal(E/B)$ and $\gal(E/C)$ are normal subgroups of $\gal(E/\QQ)$.

b. Prove that $\gal(E/B) \intersect \gal(E/C) = \theset{1}$.

c. If $B\intersect C = \QQ$, show that $\gal(E/B) \gal(E/C) = \gal(E/\QQ)$.

d. Under the hypothesis of (c), show that $\gal(E/\QQ) \cong \gal(E/B) \times \gal(E/C)$.

e. Use (d) to describe $\gal(\QQ[\alpha]/\QQ)$ where $\alpha = \sqrt 2 + \sqrt 3$.


## Spring 2013 #8
Let $F$ be the field with 2 elements and $K$ a splitting field of $f(x) = x^6 + x^3 + 1$ over $F$.
You may assume that $f$ is irreducible over $F$.

a. Show that if $r$ is a root of $f$ in $K$, then $r^9 = 1$ but $r^3\neq 1$.

b. Find $\gal(K/F)$ and express each intermediate field between $F$ and $K$ as $F(\beta)$ for an appropriate $\beta \in K$.



## Fall 2012 #3
Let $f(x) \in \QQ[x]$ be an irreducible polynomial of degree 5.
Assume that $f$ has all but two roots in $\RR$.
Compute the Galois group of $f(x)$ over $\QQ$ and justify your answer.


## Fall 2012 #4
Let $f(x) \in \QQ[x]$ be a polynomial and $K$ be a splitting field of $f$ over $\QQ$.
Assume that $[K:\QQ] = 1225$ and show that $f(x)$ is solvable by radicals.

## Spring 2012 #1
Suppose that $F\subset E$ are fields such that $E/F$ is Galois and $\abs{\gal(E/F)} = 14$.

a. Show that there exists a unique intermediate field $K$ with $F\subset K \subset E$ such that $[K: F] = 2$.

b. Assume that there are at least two distinct intermediate subfields $F \subset L_1, L_2 \subset E$ with $[L_i: F]= 7$.
  Prove that $\gal(E/F)$ is nonabelian.


## Spring 2012 #4
Let $f(x) = x^7 - 3\in \QQ[x]$ and $E/\QQ$ be a splitting field of $f$ with $\alpha \in E$ a root of $f$.

a. Show that $E$ contains a primitive 7th root of unity.

b. Show that $E\neq \QQ(\alpha)$.

## Fall 2019 Midterm #6 
Compute the Galois group of $f(x) = x^3-3x -3\in \QQ[x]/\QQ$.

## Fall 2019 Midterm #7 
Show that a field $k$ of characteristic $p\neq 0$ is perfect $\iff$ for every $x\in k$ there exists a $y\in k$ such that $y^p=x$.

## Fall 2019 Midterm #8 
Let $k$ be a field of characteristic $p\neq 0$ and $f\in k[x]$ irreducible. Show that $f(x) = g(x^{p^d})$ where $g(x) \in k[x]$ is irreducible and separable. Concluded that every root of $f$ has the same multiplicity $p^d$ in the splitting field of $f$ over $k$.

## Fall 2019 Midterm #9 
Let $n\geq 3$ and $\zeta_n$ be a primitive $n$th root of unity. Show that $[\QQ(\zeta_n + \zeta_n\inv): \QQ] = \phi(n)/2$ for $\phi$ the totient function.
10. Let $L/K$ be a finite normal extension
  - Show that if $L/K$ is cyclic and $E/K$ is normal with $L/E/K$ then $L/E$ and $E/K$ are cyclic.
  - Show that if $L/K$ is cyclic then there exists exactly one extension $E/K$ of degree $n$ with $L/E/K$ for each divisor $n$ of $[L:K]$.


