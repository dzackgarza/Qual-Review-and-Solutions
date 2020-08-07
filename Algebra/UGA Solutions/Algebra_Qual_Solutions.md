
---
title: "Algebraic Qualifying Exam Solutions"
---

# Problem Session Links

Problem Session 1: Group Theory

- 3.2, Sylow Theory
  \hyperref[problem:session_1_3_2_soln]{Solution} 
- 5.1, Class Equation
  \hyperref[problem:session_1_5_1_soln]{Solution} 
- 6.1, Sylow Theory
  \hyperref[problem:session_1_6_1_soln]{Solution} 
- 6.2, Group Actions
  \hyperref[problem:session_1_6_2_soln]{Solution} 
- Bonus: 2.4, Conjugacy Classes
  \hyperref[problem:session_1_2_4_soln]{Solution} 



# Spring 2020


## 1 ?

## 2 ?

## 3 ?

## 4 ?

## 5 ?

## 6
Let $R$ be a ring with 1.

### a
An $R\dash$module $M$ is **free** if any of the following conditions hold:

- $M$ admits an $R\dash$linearly independent spanning set $\theset{\vector b_\alpha}$, so $$m\in M \implies m = \sum_\alpha r_\alpha \vector b_\alpha$$ and $$\sum_\alpha r_\alpha \vector b_\alpha = 0_M \implies r_\alpha = 0_R$$ for all $\alpha$.
- $M \cong \bigoplus_{\alpha} R$ are isomorphic as $R\dash$modules.
- There is a nonempty set $X$ and an inclusion $X\injects M$ such that for every $R\dash$modules $N$, every map $X\to N$ lifts to a unique map $M\to N$, so the following diagram commutes:
\begin{center}
\begin{tikzcd}
M \ar[rd, dotted, "\exists ! \tilde f"] & \\
X \ar[u, hook] \ar[r, "f"] & N
\end{tikzcd}
\end{center}

### b

$M$ is **torsionfree** iff $M_t \definedas \theset{m\in M \suchthat \ann(m) \neq 0} \leq M$ is the trivial submodule, where $\ann(m) \definedas \theset{r\in R \suchthat r\cdot m = 0_M} \normal R$.

### c

- Let the following be an SES where $F$ is a free $R\dash$module:
\begin{align*}
0 \to N \to M \mapsvia{\pi} F \to 0
.\end{align*}

- Since $F$ is free, there is a generating set $X = \theset{x_\alpha}$ and a map $\iota:X\injects M$ satisfying the 3rd property from (a).
- If we construct a map $f: X\to M$, then the universal property of free modules will give a lift $\tilde f: F\to M$
- Note $\theset{\iota(x_\alpha)} \subseteq F$ and $\pi$ is surjective, so choose fibers $\theset{y_\alpha} \subseteq M$ such that $$\pi(y_\alpha) = \iota(x_\alpha).$$
- Define a map
\begin{align*}
f: X&\to M \\
x_\alpha &\mapsto y_\alpha
.\end{align*}
- By the universal property, this yields a map $h: F\to M$, commutativity forces $(h\circ \iota)(x_\alpha) = y_\alpha$, i.e. we have a diagram
\begin{center}
\begin{tikzcd}
& & & X=\theset{x_\alpha} \ar[dd, hook, "\iota"]\ar[ddl, "f"'] &  \\ \\
0 \ar[r]& N \ar[r] & M\ar[r, "\pi"'] & \ar[l, bend right, dotted ,"\exists ! h"'] F \ar[r] & 0
\end{tikzcd}
\end{center}

- It remains to check that it's a section:
\begin{align*}
f\in F \implies f = \sum_\alpha r_\alpha { \iota(x_\alpha) } \\
\implies (\pi \circ h)(f) 
&= \pi \qty{h\qty{\sum_\alpha r_\alpha \iota(x_\alpha) }}  \\
&= \pi\qty{\sum_\alpha r_\alpha h(\iota(x_\alpha))} \\
&= \pi\qty{ \sum_\alpha r_\alpha y_\alpha} \\
&= \sum_\alpha r_\alpha \pi(y_\alpha) \\
&= \sum_\alpha r_\alpha \iota(x_\alpha) \\
&\definedas f
\end{align*}

- Checking $(h\circ \pi)(m) = m$: seems to be hard! 
- Both $\pi\circ h$ and $\id_F$ are two maps that agree on the spanning set $\theset{\iota(x_\alpha)}$, so in fact they are *equal*.


Short proof:

- Free implies projective
- Universal property of projective modules: for every surjective $\pi:M\to N$ and every $f:P\to N$ there exists a unique lift $\tilde f: P\to M$:
\begin{center}
\begin{tikzcd}
 & P\ar[d, "f"] \ar[dl, dotted, "\exists ! \tilde f"'] \\
M \ar[r, "\pi"] & N
\end{tikzcd}
\end{center}
- Take the identity map:
\begin{center}
\begin{tikzcd}
 & & & F\ar[d, "\id_F"]\ar[dl, "\exists ! h"'] & \\
0 \ar[r] & N\ar[r] & M\ar[r] & F \ar[r] & 0
\end{tikzcd}
\end{center}

### d

- Claim: if $R$ is a PID and $M$ is a finitely generated $R\dash$module, then $M \cong M_t \oplus M/M_t$ where $M_t \leq M$ is the torsion submodule.
- Claim: $M/M_t$ is torsionfree, and since a f.g. torsion free module over a PID is free, $M/M_t$ is free.
  - Let $m+M_t \in M/M_t$ and suppose it is torsion, we will show that is must be the zero coset.
  - Then there exists an $r\in R$ such that $r(m + M_t) = M_t$
  - Then $rm + M_t = M_t$, so $rm\in M_t$.
  - By definition of $M_t$, every element is torsion, so there exists some $s\in R$ such $s(rm) = 0_M$.
  - Then $(sr)m = 0_M$ which forces $m\in M_t$
  - Then $m + M_t = M_t$, so $m+ M_t$ is the zero coset.
- There is a SES
\begin{center}
\begin{tikzcd}
0 \ar[r] & M_t \ar[r] & M \ar[r] & M/M_t \ar[r] & 0
\end{tikzcd}
\end{center}
  and since $M/M_t$ is free, by (c) this sequence splits and $M \cong M \oplus M/M_t$.

## 7 ?

## 8 ?

# Fall 2019

## 1

> Centralizer: 
$$
C_G(h) = Z(h) = \theset{g\in G \suchthat [g,h] = 1}
\quad\text{Centralizer}
$$
>
> Class equation: 
$$
\abs{G} = \sum_{\substack{\text{One $h$ from each } \\ \text{ conjugacy class}}} \frac{\abs{G}}{\abs{Z(h)}}
$$
> Notation:
> \begin{align*}
h^g &= ghg\inv \\
h^G &= \theset{ h^g \suchthat g\in G} \quad\text{Conjugacy Class}\\
H^g &= \theset{h^g \suchthat h\in H} \\
N_G(H) &= \theset{g\in G \suchthat H^g = H} \supseteq H \quad\text{Normalizer}
.\end{align*}
>
> **Theorem 1**: $\abs{h^G} = [G: Z(h)]$
> 
> **Theorem 2**: $\abs{\theset{H^g \suchthat g\in G}} = [G: N_G(H)]$
>
> *Proof:* Let $G\actson \theset{H \suchthat H \leq G}$ by $H \mapsto gHg\inv$.
> Then the $\mathcal O_H$ is the set of conjugate subgroups, $\mathrm{Stab}(H) = N_G(H)$.
> So Orbit-Stabilizer says $\mathcal O_h \cong G/\mathrm{Stab}(H)$; then just take sizes.

> **Theorem 3:** $\union_{g\in G} H^g = \union_{g\in G} gHg\inv \subsetneq G$ for any proper $H \leq G$.
>
> *Proof:* By theorem 2, since each coset is of size $\abs{H}$, which only intersect at the identity, and there are exactly $[G: N_G(H)]$ of them
\begin{align*}
\abs{\union_{g\in G} H^g} 
&= \qty{ \abs{H} - 1} [G: N_G(H)] + 1\\
&= \abs{H} [G: N_G(H)]  - [G:N_G(H)] + 1\\
&= \abs{G} \frac{\abs G}{\abs{N_G(H)}} - \frac{\abs G}{\abs{N_G(H)}} + 1 \\
&\leq \abs{H} \frac{\abs G}{\abs{H}} - \frac{\abs G}{\abs{H}} + 1 \\
&= \abs{G} - ([G: H] - 1) \\
&< \abs{G} 
.\end{align*}
> where we use the fact that $H \subseteq N_G(H) \implies \abs{H} \leq \abs{N_G(H)} \implies \frac{1}{\abs{N_G(H)}} \leq \frac{1}{\abs{H}}$, and since $H < G$ is proper, $[G:H] \geq 2$.

Since $[g_i, g_j] = 1$, we have $g_i \in Z(g_j)$ for every $i, j$.

Then
\begin{align*}
g\in G 
&\implies g = g_i^h \quad \text{ for some } h \\
&\implies g \in Z(g_\mathbf{j})^h \quad\text{for every } j \text{ since }g_i \in Z(g_j) ~\forall j \\
&\implies g \in \union_{h\in G} Z(g_j)^h \quad\text{for every } j\\
&\implies G \subseteq \union_{h\in G} Z(g_j)^h \quad\text{for every } j
,\end{align*}

which by Theorem 3, if $Z(g_j) < G$ were proper, then the RHS is properly contained in $G$. 
So it must be the case that that $Z(g_j)$ is not proper and thus equal to $G$ for every $j$.

But $Z(g_i) = G \iff g_i \in Z(G)$, and so each conjugacy class is size one.
So for every $g\in G$, we have $g = g_j$ for some $j$, and thus $g = g_j \in Z(g_j) = Z(G)$, so $g$ is central.
Then $G\subseteq Z(G)$ and $G$ is abelian.


## 2 \label{problem:session_1_3_2_soln}

Relevant Ideas:

- The $pqr$ theorem.
- Sylow 3: $\abs{G} = p^n m$ implies $n_p \divides m$ and $n_p \cong 1 \mod p$.
- **Theorem**: If $H, K \leq G$ and any of the following conditions hold, $HK$ is a subgroup:
  - $H\normal G$ (wlog)
  - $[H, K] = 1$
  - $H \leq N_G(K)$ 

- **Theorem**: For a positive integer $n$, all groups of order $n$ are cyclic $\iff n$ is
squarefree and, for each pair of distinct primes $p$ and $q$ dividing $n$, $q - 1 \neq 0 \mod p$.

- **Theorem:** 
\begin{align*}
A_i\normal G, \quad G = A_1 \cdots A_k,\quad A_k \intersect \prod_{i\neq k} A_i = \emptyset \implies G = \prod A_i
.\end{align*}

- The intersection of subgroups is a again a subgroup.
- Any subgroups of coprime order intersect trivially?


### a
We have 

- $n_3 \divides 5\cdot 7, \quad n_3 \cong 1 \mod 3 \implies n_3 \in \theset{1, 5, 7, 35} \setminus \theset{5, 35}$
- $n_5 \divides 3\cdot 7, \quad n_5 \cong 1 \mod 5 \implies n_5 \in \theset{1, 3, 7, 21}\setminus \theset{3, 7}$
- $n_7 \divides 3\cdot 5, \quad n_7 \cong 1 \mod 7 \implies n_7 \in \theset{1, 3, 5, 15}\setminus\theset{3, 5}$

Thus
\begin{align*}
n_3 \in \theset{1, 7} \quad n_5 \in \theset{1, 21} \quad n_7 \in \theset{1, 15}
.\end{align*}

Toward a contradiction, if $n_5\neq 1$ and $n_7 \neq 1$, then 
\begin{align*}
\abs{\syl(5) \union \syl(7)} = (5-1)n_5 + (7-1)n_7 + 1 
&= 4(21) + 6(15) = 174 > 105 \text{ elements}
\end{align*}
using the fact that Sylow $p\dash$subgroups for distinct primes $p$ intersect trivially (?).

### b (Todo)

By (a), either $Q$ or $R$ is normal.
Thus $QR \leq G$ is a subgroup, and it has order $\abs{Q} \cdot \abs{R} = 5\cdot 7 = 35$.

By the $pqr$ theorem, since $5$ does not divide $7-1=6$, $QR$ is cyclic.

### c
We want to show $Q, R\normal G$, so we proceed by showing $\textbf{not }\qty{n_5 = 21 \text{ or } n_7 = 15}$, which is equivalent to $\qty{n_5 = 1 \text{ and } n_7 = 1}$ by the previous restrictions.

Note that we can write
\begin{align*}
G = \theset{\text{elements of order } n} \disjoint \theset{\text{elements of order not } n}
.\end{align*}
for any $n$, so we count for $n=5, 7$:

- Elements in $QR$ of order **not** equal to 5: $\abs{QR - Q\theset{\id} + \theset{\id}} = 35 - 5 + 1 = 31$
- Elements in $QR$ of order **not** equal to 7: $\abs{QR - \theset{\id}R + \theset{\id}} = 35 - 7 + 1 = 29$

Since $QR \leq G$, we have

- Elements in $G$ of order **not** equal to 5 $\geq 31$.
- Elements in $G$ of order **not** equal to 7 $\geq 29$.

Now both cases lead to contradictions:

- $n_5 = 21$:
\begin{align*}
\abs{G}  &= \abs{\theset{\text{elements of order } 5} \disjoint \theset{\text{elements of order not } 5}} \\
&\geq n_5(5-1) + 31 = 21(4) + 31 = 115 > 105 = \abs{G}
.\end{align*}

- $n_7 = 15$:
\begin{align*}
\abs{G}  &= \abs{\theset{\text{elements of order } 7} \disjoint \theset{\text{elements of order not } 7}} \\
&\geq n_7(7-1) + 29 = 15(6) + 29 = 119 > 105 = \abs{G}
.\end{align*}

### d

Suppose $P$ is normal and recall $\abs{P} = 3, \abs{Q} = 5, \abs{R} = 7$.

- $P\intersect QR = \theset{e}$ since $(3, 35) = 1$ 
- $R\intersect PQ = \theset{e}$ since $(5, 21) = 1$ 
- $Q\intersect RP = \theset{e}$ since $(7, 15) = 1$ 

We also have $PQR = G$ since $\abs{PQR} = \abs{G}$ (???).

We thus have an internal direct product 
\begin{align*}
G \cong P\cross Q \cross R \cong \ZZ_3 \cross \ZZ_5 \cross \ZZ_7 \cong \ZZ_{105}
.\end{align*}
by the Chinese Remainder Theorem, which is cyclic.


## 3

> Just fiddling with computations.
> Context hints that we should be considering things like $x^2$ and $a+b$.

### a
\begin{align*}
2a  = (2a)^2 = 4a^2 = 4a \implies 2a = 0
.\end{align*}

Note that this implies $x = -x$ for all $x\in R$.

### b
\begin{align*}
a+b = (a+b)^2 &= a^2 + ab + ba + b^2 = a + ab + ba + b \\
&\implies ab + ba = 0 \\
&\implies ab = -ba \\
&\implies ab = ba \quad\text{by (a)}
.\end{align*}

## 4

> Theorem: $F\units$ is always cyclic for $F$ a field

### a

Since $\abs{F} = q$ and $[E:F] = k$, we have $\abs{E} = q^k$ and $\abs{E\units} = q^k-1$.
Noting that $\zeta \in E\units$ we must have $n = o(\zeta) \divides \abs{E\units} = q^k-1$ by Lagrange's theorem.

### b

Rephrasing (a), we have 
\begin{align*}
n \divides q^k-1 
&\iff q^k-1 \cong 0 \mod n \\
&\iff q^k \cong 1 \mod n \\
&\iff m \definedas o(q) \divides k
.\end{align*}

### c

Since $m\divides k \iff k = \ell m$, (**claim**) there is an intermediate subfield $M$ such that
\begin{align*}
E \leq M \leq F \quad k = [F:E] = [F:M] [M:E] = \ell m
,\end{align*}

so $M$ is a degree $m$ extension of $E$.

Now consider $M\units$. 
By the argument in (a), $n$ divides $q^m - 1 = \abs{M\units}$, and $M\units$ is cyclic, so it contains a cyclic subgroup $H$ of order $n$.

But then $x\in H \implies p(x)\definedas x^n-1 = 0$, and since $p(x)$ has at most $n$ roots in a field. 
So $H = \theset{x \in M \suchthat x^n-1 = 0}$, i.e. $H$ contains all solutions to $x^n-1$ in $E[x]$.

But $\zeta$ is one such solution, so $\zeta \in H \subset M\units \subset M$.
Since $F[\zeta]$ is the smallest field extension containing $\zeta$, we must have $F = M$, so $\ell = 1$, and $k = m$.

> Todo: **revisit**, tricky!

## 5

> One-step submodule test.

### a

It suffices to show that 
$$
r\in R, ~t_1, t_2\in \Tor(M) \implies rt_1 + t_2 \in \Tor(M)
.$$

We have
\begin{align*}
t_1 \in \Tor(M) &\implies \exists s_1 \neq 0 \text{ such that } s_1 t_1  = 0 \\
t_2 \in \Tor(M) &\implies \exists s_2 \neq 0 \text{ such that } s_2 t_2  = 0 
.\end{align*}

Since $R$ is an integral domain, $s_1 s_2 \neq 0$.
Then
\begin{align*}
s_1 s_2(rt_1 + t_2) 
&= s_1 s_2 r t_1 + s_1 s_2t_2 \\
&= s_2 r (s_1 t_1) + s_1 (s_2 t_2)  \quad\text{since $R$ is commutative} \\
&=  s_2 r(0) + s_1(0) \\
&= 0
.\end{align*}

### b

Let $R = \ZZ/6\ZZ$ as a $\ZZ/6\ZZ \dash$module, which is not an integral domain as a ring.

Then $[3]_6\actson [2]_6 = [0]_6$ and $[2]_6\actson [3]_6 = [0]_6$, but $[2]_6 + [3]_6 = [5]_6$, where 5 is coprime to 6, and thus $[n]_6\actson [5]_6 = [0] \implies [n]_6 = [0]_6$. So $[5]_6$ is *not* a torsion element.

So the set of torsion elements are not closed under addition, and thus not a submodule.

### c

Suppose $R$ has zero divisors $a,b \neq 0$ where $ab = 0$.
Then for any $m\in M$, we have $b\actson m \definedas bm \in M$ as well, but then 
$$
a\actson bm = (ab)\actson m = 0\actson m = 0_M
,$$ 
so $m$ is a torsion element for any $m$.

$\qed$

## 6

> Prime ideal: $\mathfrak{p}$ is prime iff $ab \in \mathfrak{p} \implies a\in \mathfrak{p}$ or $b\in \mathfrak{p}$.
> Silly fact: 0 is in every ideal!
> 
> **Zorn's Lemma:** Given a poset, if every chain has an upper bound, then there is a maximal element. (Chain: totally ordered subset.)
> 
> **Corollary:** If $S\subset R$ is multiplicatively closed with $0\not\in S$ then $\theset{I \normal R \suchthat J\intersect S = \emptyset}$ has a maximal element.
> (TODO: PROVE)
>
> **Theorem:** If $R$ is commutative, maximal $\implies$ prime for ideals.
> (TODO: PROVE)
>
> **Theorem:** Non-units are contained in a maximal ideal. (See HW?)

### a

Let $\mathfrak{p}$ be prime and $x\in N$.
Then $x^k = 0 \in \mathfrak{p}$ for some $k$, and thus $x^k = x x^{k-1} \in \mathfrak p$.
Since $\mathfrak p$ is prime, inductively we obtain $x\in\mathfrak p$.

### b

Let $S = \theset{r^k \mid k\in \NN}$ be the set of positive powers of $r$. 
Then $S^2 \subseteq S$, since $r^{k_1}r^{k_2} = r^{k_1+k_2}$ is also a positive power of $r$, and $0\not\in S$ since $r\neq 0$ and $r\not\in N$.

By the corollary, $\theset{I \normal R \suchthat I\intersect S = \emptyset}$ has a maximal element $\mathfrak{p}$.

Since $R$ is commutative, $\mathfrak{p}$ is prime.

### c

Suppose $R$ has a unique prime ideal $\mathfrak{p}$.

Suppose $r\in R$ is not a unit, and toward a contradiction, suppose that $r$ is also not nilpotent.

Since $r$ is not a unit, $r$ is contained in some maximal (and thus prime) ideal, and thus $r \in \mathfrak{p}$.

Since $r\not\in N$, by (b) there is a maximal ideal $\mathfrak{m}$ that avoids all positive powers of $r$. 
Since $\mathfrak{m}$ is prime, we must have $\mathfrak{m} = \mathfrak{p}$.
But then $r\not\in \mathfrak{p}$, a contradiction.

## 7

> Galois Theory.
> 
> **Galois** = normal + separable.
> 
> **Separable**: Minimal polynomial of every element has distinct roots.
> 
> **Normal (if separable)**: Splitting field of an irreducible polynomial.

> Definition: $\zeta$ is a primitive root of unity iff $o(\zeta) = n$ in $F\units$.
> 
> $\phi(p^k) = p^{k-1}(p-1)$

> The lattice: 

![](figures/2019-12-24-13-19-15.png)

Let $K = \QQ(\zeta)$. 
Then $K$ is the splitting field of $f(x) = x^n - 1$, which is irreducible over $\QQ$, so $K/\QQ$ is normal.
We also have $f'(x) = nx^{n-1}$ and $\gcd(f, f') = 1$ since they can not share any roots.

> Or equivalently, $f$ splits into distinct linear factors $f(x) = \prod_{k\leq n}(x-\zeta^k)$.

Since it is a Galois extension, $\abs{\Gal(K/\QQ)} = [K: \QQ] = \phi(n)$ for the totient function.

We can now define maps
\begin{align*}
\tau_j: K &\to K \\
\zeta &\mapsto \zeta^j 
\end{align*}

and if we restrict to $j$ such that $\gcd(n, j) = 1$, this yields $\phi(n)$ maps.
Noting that if $\zeta$ is a primitive root, then $(n, j) = 1$ implies that that $\zeta^j$ is also a primitive root, and hence another root of $\min(\zeta, \QQ)$, and so these are in fact automorphisms of $K$ that fix $\QQ$ and thus elements of $\Gal(K/\QQ)$.

So define a map
\begin{align*}
\theta: \ZZ_n\units &\to K \\
[j]_n &\mapsto \tau_j
.\end{align*}

from the *multiplicative* group of units to the Galois group.

The claim is that this is a surjective homomorphism, and since both groups are the same size, an isomorphism.

**Surjectivity:**

Letting $\sigma \in K$ be arbitrary, noting that $[K: \QQ]$ has a basis $\theset{1, \zeta, \zeta^2, \cdots, \zeta^{n-1}}$, it suffices to specify $\sigma(\zeta)$ to fully determine the automorphism.
(Since $\sigma(\zeta^k) = \sigma(\zeta)^k$.)

In particular, $\sigma(\zeta)$ satisfies the polynomial $x^n - 1$, since $\sigma(\zeta)^n = \sigma(\zeta^n) = \sigma(1) = 1$, which means $\sigma(\zeta)$ is another root of unity and $\sigma(\zeta) = \zeta^k$ for some $1\leq k \leq n$.

Moreover, since $o(\zeta) = n \in K\units$, we must have $o(\zeta^k) = n \in K\units$ as well. Noting that $\theset{\zeta^i}$ forms a cyclic subgroup $H\leq K\units$, then $o(\zeta^k) = n \iff (n, k) = 1$ (by general theory of cyclic groups).

Thus $\theta$ is surjective.

**Homomorphism:**

\begin{align*}
\tau_j \circ \tau_k (\zeta) =\tau_j(\zeta^k) = \zeta^{jk} \implies
\tau_{jk} = \theta(jk) = \tau_j \circ \tau_k
.\end{align*}

**Part 2:**

We have $K \cong \ZZ_{20}\units$ and $\phi(20) = 8$, so $K \cong \ZZ_8$, so we have the following subgroups and corresponding intermediate fields:

- $0 \sim \QQ(\zeta_{20})$
- $\ZZ_2 \sim \QQ(\omega_1)$
- $\ZZ_4 \sim \QQ(\omega_2)$
- $\ZZ_8 \sim \QQ$

For some elements $\omega_i$ which exist by the primitive element theorem.


## 8

### a.

Let $\vector v \in \Lambda$, so $\vector v = \sum_{i=1}^n r_i \vector e_i$ where $r_i \in \ZZ$ for all $i$.

Then if $\vector x = \sum_{j=1}^n s_j \vector e_j \in \Lambda$ is arbitrary, we have $s_j \in \ZZ$ for all $j$ and 
\begin{align*}
\inner{\vector v}{\vector x} 
&= \inner{\sum_{i=1}^n r_i \vector e_i}{\sum_{j=1}^n s_j \vector e_j } \\
&= \sum_{i=1}^n \sum_{j=1}^n r_i s_j \inner{\vector e_i}{\vector e_j }  \in \ZZ
\end{align*}

since this is a sum of products of integers (since $\inner{\vector e_i}{\vector e_j} \in \ZZ$ for each $i, j$ pair by assumption) so $\vector v \in \Lambda\dual$ by definition.

### b. 


**$\det M \neq 0$**:

Suppose $\det M = 0$. Then $\ker M \neq \vector 0$, so let $\vector v \in \ker M$ be given by $\vector v = \sum_{i=1}^n v_i \vector e_i \neq \vector 0$. 

Note that 
\begin{align*}
M\vector v = 0 &\implies
\left[
\begin{array}{ccc}
\vector e_1 \cdot \vector e_1 & \vector e_1 \cdot \vector e_2 & \cdots \\
\vector e_2 \cdot \vector e_1 & \vector e_2 \cdot \vector e_2 & \cdots \\
\vdots & \vdots & \ddots
\end{array}
\right]
\left[\begin{array}{c}
v_1 \\ v_2 \\ \vdots
\end{array}\right] = \vector 0 \\ \\
&\implies \sum_{j=1}^n v_j\inner{\vector e_k}{\vector e_j} = 0 \qtext{for each fixed} k
.\end{align*}

We can now note that $\inner{\vector e_k}{\vector v} = \sum_{j=1}^n v_j \inner{\vector e_k}{\vector e_j} = 0$ for every $k$ by the above observation, which forces $\vector v = 0$ by non-degeneracy of $\inner{\wait}{\wait}$, a contradiction. 

$\qed$

*Alternative proof:*

Write $M = A^tA$ where $A$ has the $\vector e_i$ as columns. Then
\begin{align*}
M\vector x = 0 
&\implies A^t A \vector x = 0 \\
&\implies \vector x^t A^t A \vector x = 0 \\
&\implies \norm{A \vector x}^2  = 0 \\
&\implies A\vector x = 0 \\
&\implies \vector x = 0
,\end{align*}

since $A$ has full rank because the $\vector e_i$ are linearly independent.

$\qed$

Let $A = [\vector e_1^t, \cdots, \vector e_n^t]$ be the matrix with $\vector e_i$ in the $i$th column.

**The rows of $A\inv$ span $\Lambda\dual$**:

Equivalently, the columns of $A^{-t}$ span $\Lambda\dual$.

Let $B = A^{-t}$ and let $\vector b_i$ denote the columns of $B$, so $\im B = \spanof{\theset{\vector b_i}}$.


Since $A \in \GL(n, \ZZ)$, $A\inv, A^t, A^{-t} \in \GL(n, \ZZ)$ as well.

\begin{align*}
\vector v \in \Lambda\dual 
&\implies \inner{\vector e_i}{\vector v} = z_i \in \ZZ \quad \forall i \\
&\implies A^t \vector v = \vector z \definedas [z_1, \cdots, z_n] \in \ZZ^n \\
&\implies \vector v = A^{-t} \vector z \definedas B\vector z \in \im B \\
&\implies \vector v \in \im B \\
&\implies \Lambda\dual \subseteq \im B
,\end{align*}

and

\begin{align*}
B^t A = (A^{-t})^t A = A\inv A = I \\
\implies \vector b_i \cdot \vector e_j = \delta_{ij} \in \ZZ \\
\implies \im B \subseteq \spanof~ \Lambda\dual
.\end{align*}

$\qed$

### c.

?

# Spring 2019

## 1

> $A$ is diagonalizable iff $\min_A(x)$ is separable.
> See [further discussion here](https://math.stackexchange.com/questions/3027664/if-a-is-invertible-and-an-is-diagonalizable-then-a-is-diagonalizable).

Claim: If $A \in \Gl(m, \FF)$ is invertible and $A^n/\FF$ is diagonalizable, then $A/\FF$ is diagonalizable.


Let $A \in \Gl(m, \FF)$. 
Since $A^n$ is diagonalizable, $\min_{A^n}(x) \in \FF[x]$ is separable and thus factors as a product of $m$ **distinct** linear factors:

$$
\min_{A^n}(x) = \prod_{i=1}^m (x-\lambda_i), \quad \min_{A^n}(A^n) = 0
$$

where $\theset{\lambda_i}_{i=1}^m \subset \FF$ are the **distinct** eigenvalues of $A^n$.

Moreover $A\in \GL(m,\FF) \implies A^n \in \GL(m,\FF)$: $A$ is invertible $\iff \det(A) = d \in \FF\units$, and so $\det(A^n) = \det(A)^n = d^n \in \FF\units$ using the fact that the determinant is a ring morphism $\det: \mat (m\times m) \to\FF$ and $\FF\units$ is closed under multiplication.

So $A^n$ is invertible, and thus has trivial kernel, and thus zero is not an eigenvalue, so $\lambda_i \neq 0$ for any $i$.

Since the $\lambda_i$ are distinct and nonzero, this implies $x^k$ is not a factor of $\mu_{A^n}(x)$ for any $k\geq 0$. 
Thus the $m$ terms in the product correspond to precisely $m$ **distinct linear** factors.

We can now construct a polynomial that annihilates $A$, namely
$$
q_A(x) \definedas \min_{A^n}(x^n) = \prod_{i=1}^m (x^n-\lambda_i) \in \FF[x],
$$

where we can note that $q_A(A) = \min_{A^n}(A^n) = 0$, and so $\min_A(x) \divides q_A(x)$ by minimality.

We now claim that $q_A(x)$ has exactly $n\cdot m$ distinct linear factors in $\bar \FF[x]$, which reduces to showing that no pair $x^n-\lambda_i, x^n-\lambda_j$ share a root.
and that $x^n-\lambda_i$ does not have multiple roots.

- For the first claim, we can factor
  \[
  x^n - \lambda_i = \prod_{k=1}^n (x - \lambda_i^{1\over n} e^{2\pi i k \over n}) \definedas \prod_{k=1}^n (x-\lambda^{1\over n} \zeta_n^k)
  ,\]
  where we now use the fact that $i\neq j \implies \lambda_i^{1\over n} \neq \lambda_j^{1\over n}$. 
  Thus no term in the above product appears as a factor in $x^n - \lambda_j$ for $j\neq i$.

- For the second claim, we can check that $\dd{}{x}\qty{x^n - \lambda_i} = nx^{n-1}\neq 0\in \FF$, and $\gcd(x^n-\lambda_i, nx^{n-1}) = 1$ since the latter term has only the roots $x=0$ with multiplicity $n-1$, whereas $\lambda_i\neq 0 \implies$ zero is not a root of $x^n-\lambda_i$.

But now since $q_A(x)$ has exactly distinct linear factors in $\bar \FF[x]$ and $\min_A(x) \divides q_A(x)$, $\min_A(x) \in \FF[x]$ can only have distinct linear factors, and $A$ is thus diagonalizable over $\FF$.

$\qed$

## 2

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

$\qed$

## 3

> - Sylow theorems:
> - $n_p \cong 1 \mod p$
> - $n_p \divides m$.

It turns out that $n_3 = 1$ and $n_5 = 1$, so $G \cong S_3 \cross S_5$ since both subgroups are normal.

There is only one possibility for $S_5$, namely $S_5\cong \ZZ/(5)$.

There are two possibilities for $S_3$, namely $S_3 \cong \ZZ/(3^2)$ and $\ZZ/(3)^2$.

Thus

- $G \cong \ZZ/(9) \cross \ZZ/(5)$, or
- $G \cong \ZZ/(3)^2 \cross \ZZ/(5)$.

$\qed$

## 4 \label{problem:session_1_2_4_soln}

Concepts Used:

- Notation: $X/G$ is the set of $G\dash$orbits
- Notation: $X^g = \theset{x\in x\suchthat g\cdot x = x}$
- Burnside's formula: $\abs G \abs{X/G} = \sum \abs {X^g}$.

### a


Strategy: Burnside.

- Define a sample space $\Omega = G \cross G$, so $\abs{\Omega} = \abs{G}^2$.

- Identify the event we want to analyze: $A \definedas \theset{(g,h) \in G\cross G \suchthat [g,h] = 1}$.
  - Define and note: 
    \[
    A_g \definedas \theset{(g, h) \suchthat h\in H, [g, h] = 1} \implies A = \disjoint_{g\in G} A_g
    .\]

- Set $n$ be the number of conjugacy classes, note we want to show $P(A) = n / \abs{G}$.
 
- Let $G$ act on itself by conjugation, which partitions $G$ into conjugacy classes.

  - What are the orbits? 
    $$
    \mathcal{O}_g = \theset{hgh\inv \suchthat h\in G}
    ,$$ 
    which is the conjugacy class of $g$.

  - What are the fixed points? 
    $$X^g = \theset{h\in G \suchthat hgh\inv = g},$$ 
    which are the elements of $G$ that commute with $g$, which is precisely $A_g$.

- Note $\abs{X/G} = n$, the number of conjugacy classes.

- Note that 
  $$
  \abs{A} = \abs{\disjoint_{g\in G} A_g} = \sum_{g\in G} \abs{A_g} = \sum_{g\in G}\abs{X^g}
  .$$


- Apply Burnside
$$
\abs{X / G} = \frac { 1 } { | G | } \sum _ { g \in G } \left| X ^ { g } \right|,
$$
- Rearrange and use definition:
$$
n \abs{G}
= \abs{X/G} \abs{G}
= \sum _ { g \in G } \left| X ^ { g } \right|
$$
- Compute probability:
\[
P(A)
= {\abs A \over \abs \Omega} 
= \frac{\sum_{ g \in G } \left| X ^ { g } \right|}{\abs{G}^2} 
= \frac{\abs{X/G}\abs{G}}{\abs{G}^2} 
= \frac{n \abs{G}}{\abs{G}^2} 
= \frac n {\abs G}
.\]

$\qed$

### b

Class equation:
\[
\abs G = Z(G) + \sum_{\substack{\text{One $x$ from each} \\ \text{conjugacy class}}}[G: Z(x)]
\]

where $Z(x) = \theset{g\in G \suchthat [g, x] = 1}$.

### c

> Todo: revisit.

As shown in part 1,
$$
\mathcal{O}_x = \theset{g\actson x \suchthat g\in G} = \theset{h\in G \suchthat ghg\inv = h} = C_G(g)
,$$
and by the class equation

$$
\abs{G} = \abs{Z(G)} + \sum_{\substack{\text{One $x$ from each} \\ \text{conjugacy class}}}[G: Z(x)]
$$

Now note

- Each element of $Z(G)$ is in its own conjugacy class, contributing $\abs{Z(G)}$ classes to $n$.

- Every other class of elements in $G\setminus Z(G)$ contains at least 2 elements
  - Claim: each such class contributes **at least** $\frac 1 2 \abs{G \setminus Z(G)}$.

Thus
\[
n &\leq \abs{Z(G)} + \frac 1 2\abs{G \setminus Z(G)} \\
&= \abs{Z(G)} + \frac 1 2\abs{G} - \frac 1 2 \abs{Z(G)} \\
&= \frac 1 2 \abs{G} + \frac 1 2 \abs{Z(G)} \\
\\
\implies \frac n {\abs G}
&\leq \frac 1 2 \frac{\abs{G}}{\abs{G}}  + \frac 1 2 \frac{\abs{Z(G)}}{\abs{G}} \\
&= \frac 1 2 + \frac 1 2 \frac 1 {[G: Z(G)]}
.\]


## 5

### a

- Suppose toward a contradiction $\tor(M)$ has rank $n \geq 1$.
- Then $\tor(M)$ has a linearly independent generating set $B = \theset{\vector r_1, \cdots, \vector r_n}$, so in particular
\[  
\sum_{i=1}^n s_i \vector r_i = 0 \implies s_i = 0_R \,\forall i
.\]
- Let $\vector r$ be any of of these generating elements.
- Since $\vector r\in \tor(M)$, there exists an $s\in R\setminus 0_R$ such that $s\vector r = 0_M$.
- Then $s\vector r = 0$ with $s\neq 0$, so $\theset{\vector r} \subseteq B$ is *not* a linearly independent set, a contradiction.

$\qed$

### b

- Let $n = \rank M$, and let $\mathcal B = \theset{\vector r_i}_{i=1}^n \subseteq R$ be a generating set.
- Let $\tilde M \definedas M/\tor(M)$ and $\pi: M \to M'$ be the canonical quotient map.

- **Claim:** 
  $\tilde \mcb \definedas \pi(\mathcal B) = \theset{\vector r_i + \tor(M)}$ is a basis for $\tilde M$.

  - **Linearly Independent:**

    - Suppose that
  \[
  \sum_{i=1}^n s_i (\vector r_i + \tor(M)) = \vector 0_{\tilde M}
  .\]

    - Then  
  \[  
  \sum_{i=1}^n (s_i \vector r_i) + \tor(M)
  .\]
    - Since $\tilde{\vector x} = 0 \in \tilde M \iff \tilde{\vector x} = \vector x + \tor(M)$ where $\vector x \in \tor(M)$, this forces $
  \[
  \sum_{i=1}^n s_i \vector r_i \in \tor(M) \implies \exists \alpha \in R\nonzero \text{ such that }
  \alpha_i \sum s_i \vector r_i = \vector 0_M
  .\]

    - But since $R$ is an integral domain and $\alpha \neq 0$, we must have $s_i = 0$ for all $i$.

  - **Spanning:**

    - Write $\pi(\mathcal B) = \theset{\vector r_i + \Tor(M)}_{i=1}^n$ as a set of cosets.

    - Letting $\vector x \in M'$ be arbitrary, we can write $\vector x = \vector m + \tor(M)$ for some $\vector m \in M$ where $\pi(\vector m) = \vector x$ by surjectivity of $\pi$.

    - Since $\mathcal B$ is a basis for $M$, we have $\vector m = \sum_{i=1}^n s_i \vector r_i$, and so
  \[
  \vector x
  &= \pi(\vector m) \\
  &= \pi\qty{ \sum_{i=1}^n s_i \vector r_i} \\
  &= \sum_{i=1}^n s_i \pi(\vector r_i) \\
  &= \sum_{i=1}^n s_i \vector (\vector r_i + \tor(M))
  ,\]
  which expresses $\vector{x}$ as a linear combination of elements in $\mathcal B'$.

### c

**$M$ is not free:**
**Claim**: If $I \normal R$ is a free $R\dash$module, then $I$ is a principal ideal.

*Proof:*
Let $I = \generators{B}$ for some basis -- if $B$ contains more than 1 element, say $m_1$ and $m_2$, then $m_2m_1 - m_1 m_2 = 0$ is a linear dependence, so $B$ has only one element $m$.

But then $I = \generators{m} = R_m$ is cyclic as an $R\dash$ module and thus principal as an ideal of $R$. 
The result follows by the contrapositive.


**$M$ is rank 1**:
For any module, we can take an element $M\neq 0_M$ and consider its cyclic module $Rm$.

Thus the rank of $M$ is at least 1, since $\theset{m}$ is a subset of a spanning set.
It can not be linearly dependent, since $R$ is an integral domain and $M\subseteq R$, so $\alpha m = 0 \implies \alpha = 0$.

However, the rank is at most 1 since $R$ is commutative.
If we take two elements $\vector m, \vector n \in M$, then since $m, n\in R$ as well, we have $nm = mn$ and so
$$
(n)\vector m + (-m)\vector n = 0_R = 0_M
$$
is a linear dependence.
2
**$M$ is torsion-free**:

Let $x \in \tor M$, then there exists some $r\neq 0\in R$ such that $rx = 0$.
But $x\in R$ and $R$ is an integral domain, so $x=0$, and thus $\tor(M) = \theset{0_R}$.

$\qed$

## 6

### a

Define the set of proper ideals
$$
S = \theset{J \suchthat I   \subseteq J < R}
,$$

which is a poset under set inclusion.

Given a chain $J_1 \subseteq \cdots$, there is an upper bound $J \definedas \union J_i$, so Zorn's lemma applies.

### b
$\implies$:

We will show that $x\in J(R) \implies 1+x \in R\units$, from which the result follows by letting $x=rx$.

Let $x\in J(R)$, so it is in every maximal ideal, and suppose toward a contradiction that $1+x$ is **not** a unit.

Then consider $I = \generators{1+x} \normal R$. 
Since $1+x$ is not a unit, we can't write $s(1+x) = 1$ for any $s\in R$, and so $1 \not\in I$ and $I\neq R$

So $I < R$ is proper and thus contained in some maximal proper ideal $\mathfrak{m} < R$ by part (1), and so we have $1+x \in \mathfrak{m}$.
Since $x\in J(R)$, $x\in \mathfrak{m}$ as well.

But then $(1+x) - x = 1 \in \mathfrak{m}$ which forces $\mathfrak{m} = R$.

$\impliedby$

Fix $x\in R$, and suppose $1+rx$ is a unit for all $r\in R$.

 
Suppose towards a contradiction that there is a maximal ideal $\mathfrak{m}$ such that $x\not \in \mathfrak{m}$ and thus $x\not\in J(R)$.

Consider 
$$
M' \definedas \theset{rx + m \suchthat r\in R,~ m\in M}
.$$

Since $\mathfrak{m}$ was maximal, $\mathfrak{m} \subsetneq M'$ and so $M' = R$.

So every element in $R$ can be written as $rx + m$ for some $r\in R, m\in M$.
But $1\in R$, so we have 
$$
1 = rx + m
.$$ 

So let $s = -r$ and write $1 = sx - m$, and so $m = 1 + sx$.

Since $s\in R$ by assumption $1+sx$ is a unit and thus $m \in \mathfrak{m}$ is a unit, a contradiction.

So $x\in \mathfrak{m}$ for every $\mathfrak{m}$ and thus $x\in J(R)$.

### c

> - $\mathfrak N(R) = \theset{x\in R \suchthat x^n = 0 \text{ for some } n}$.
> - $J(R) = \spec_{\text{max}}(R) = \displaystyle\intersect_{\mm \text{ maximal}} \mm$.

We want to show $J(R) = \mathfrak N(R)$.

$\mathfrak N(R) \subseteq J(R)$:

We'll use the fact $x\in \mathfrak N(R) \implies x^n = 0 \implies 1 + rx$ is a unit $\iff x\in J(R)$ by (b):
$$
\sum_{k=1}^{n-1} (-x)^k = \frac{1 - (-x)^n}{1- (-x)} = (1+x)\inv
.$$

$J(R) \subseteq \mathfrak N(R)$:

Let $x \in J(R) \setminus \mathfrak N(R)$.

Since $R$ is finite, $x^m = x$ for some $m > 0$.
Without loss of generality, we can suppose $x^2 = x$ by replacing $x^m$ with $x^{2m}$.

If $1-x$ is not a unit, then $\generators{1-x}$ is a nontrivial proper ideal, which by (a) is contained in some maximal ideal $\mm$. 
But then $x\in \mm$ and $1-x \in \mm \implies x + (1-x) = 1 \in \mm$, a contradiction.

So $1-x$ is a unit, so let $u = (1-x)\inv$.

Then
\[
(1-x)x &= x - x^2 = x - x = 0 \\
&\implies u (1-x)x = x = 0 \\
&\implies x=0
.\]

## 7

> Work with matrix of all ones instead.
> Eyeball eigenvectors.
> Coefficients in minimal polynomial: size of largest Jordan block
> Dimension of eigenspace: number of Jordan blocks

### a

Let $A$ be the matrix in the question, and $B$ be the matrix containing 1's in every entry.

- Noting that $B = A+I$, we have
  \[
  &B\vector x = \lambda \vector x \\
  &\iff (A+I) \vector x = \lambda \vector x \\
  &\iff A \vector x = (\lambda - 1) \vector x
  ,\]
    so we will find the eigenvalues of $B$ and subtract one from each.

- Note that $B\vector v = \thevector{\sum v_i, \sum v_i, \cdots, \sum v_i}$, i.e. it has the effect of summing all of the entries of $\vector v$ and placing that sum in each component.

- We proceed by finding $p$ eigenvectors and eigenvalues, since the JCF and minimal polynomials will involve eigenvalues and the transformation matrix will involve (generalized) eigenvectors.

- Claim: each vector of the form $\vector p_i \definedas \vector e_1 - \vector e_{i+1} = \thevector{1, 0, 0,\cdots, 0 -1, 0, \cdots, 0 }$ where $i\neq j$ is also an eigenvector with eigenvalues $\lambda_0 = 0$, and this gives $p-1$ linearly independent vectors spanning the eigenspace $E_{\lambda_0}$
  - Compute $$B \vector p_i = \thevector{ 1 + 0 + \cdots + 0 + (-1) + 0 + \cdots + 0} = \thevector{0, 0, \cdots, 0}$$
  - So every $\vector p_i \in \ker(B)$, so they are eigenvectors with eigenvalue 0.
  - Since the first component is fixed and we have $p-1$ choices for where to place a $-1$, this yields $p-1$ possibilities for $\vector p_i$
  - These are linearly independent since the $(p-1)\times (p-1)$ matrix $\thevector{ \vector p_1^t, \cdots, \vector p_{p-1}^t}$ satisfies
  \[
  \det 
\begin{bmatrix}
1 & 1 & 1 & \cdots & 1\\
-1 & 0  & 0 & \cdots & 0\\
0 & -1  & 0 & \cdots & 0\\
0 & 0 & -1 & \cdots & 0\\
\vdots & \vdots  & \vdots & \ddots & \vdots \\
0 & 0  & 0 & \cdots & -1\\
\end{bmatrix}
= (1) \cdot \det 
\begin{bmatrix}
-1 & 0  & 0 & \cdots & 0\\
0 & -1  & 0 & \cdots & 0\\
0 & 0 & -1 & \cdots & 0\\
\vdots & \vdots  & \vdots & \ddots & \vdots \\
0 & 0  & 0 & \cdots & -1\\
\end{bmatrix}
 = (-1)^{p-2} \neq 0
.\]

  where the first equality follows from expanding along the first row and noting this is the first minor, and every other minor contains a row of zeros.

- Claim: $\vector v_1 = \thevector{1, 1, \cdots, 1}$ is an eigenvector with eigenvalue $\lambda_1 = p$.
  - Compute $$B\vector v = \thevector{\sum_{i=1}^p 1, \sum_{i=1}^p 1, \cdots, \sum_{i=1}^p 1} = \thevector{p, p, \cdots, p} = p \thevector{1, 1, \cdots, 1} = p\vector{v}_1,$$ thus $\lambda_1 = p$
  - $\dim E_{\lambda_1} = 1$ since the eigenspaces are orthogonal and $E_{\lambda_0} \oplus E_{\lambda_1} \leq F^p$ is a subspace, so $p > \dim(E_{\lambda_0}) + \dim E_{\lambda_1} = p-1 + \dim E_{\lambda_1}$ and it isn't zero dimensional.


- Using that the eigenvalues of $A$ are $1+\lambda_i$ for $\lambda_i$ the above eigenvalues for $B$,
\[
\spec(B) \definedas \theset{(\lambda_i, m_i)} &=  \theset{(p, 1), (0, p-1)}  \implies \chi_{B}(x) = (x-p)x^{p-1} \\ 
\implies \spec(A) &= \theset{(p-1,1), (-1, p-1) }  \implies \chi_{A}(x) = (x- p+1)(x+1)^{p-1} \\
\]

> Note: we can always read off the *characteristic* polynomial from the spectrum.


- The dimensions of eigenspaces are preserved, thus
\[
JCF_\QQ(A)
=  J_{p-1}^{1} \oplus (p-1)J_{-1}^1
=
\left[\begin{array}{r|r|r|r|r|r}
p-1 & 0 & 0 & \cdots & 0 & 0 \\
\hline
0& -1 & 0 & 0 & 0 & 0 \\ \hline
0& 0 & -1 & 0 & 0 & 0 \\ \hline
0& 0 & 0 & \ddots & \ddots & 0 \\ \hline
0& 0 & 0 & \cdots & -1 & 0 \\ \hline
0& 0 & 0 & \cdots & 0 & -1 \\
\end{array}\right]
.\]

- The matrix $P$ such that $A = PJP\inv$ will have columns the bases of the generalized eigenspaces.
- In this case, the generalized eigenspaces are the usual eigenspaces, so
\[
P = [\vector v_1, \vector p_1, \cdots, \vector p_{p-1}] =
\left[\begin{array}{rrrrrr}
1 & 1 & 1 & 1 & 1 & 1  \\
1 & -1 & 0 & 0 & 0 & 0 \\
1 & 0 & -1 & 0 & 0 & 0 \\
1 & 0 & 0 & -1 & 0 & 0 \\
1 & \vdots & \vdots & \vdots & \ddots & \vdots\\
1 & 0 & 0 & 0 & 0 & -1 \\
\end{array}\right]
.\]

### b

For $F = \FF_p$, all eigenvalues/vectors still lie in $\FF_p$, but now $-1 = p-1$, making $(x-(p-1))(x+1)^{p-1} = (x+1)(x+1)^{p-1}$, so $\chi_{A, \FF_p}(x) = (x+1)^p$, and the Jordan blocks may merge.

- A computation shows that $(A+I)^2 = pA = 0 \in M_p(\FF_p)$ and $(A+I) \neq 0$, so $\min_{A, \FF_p}(x) = (x+1)^2$.
  - Thus the largest Jordan block corresponding to $\lambda = -1$ is of size 2
- Can check that $\det(A) = \pm 1 \in \FF_p\units$, so the vectors $\vector e_1 - \vector e_i$ are still linearly independent and thus $\dim E_{-1} = p-1$
  - So there are $p-1$ Jordan blocks for $\lambda = 0$.

Summary:
\[
\min_{A, \FF_p}(x) &= (x+1)^2 \\
\chi_{A, \FF_p}(x) &\equiv (x+1)^p \\
\dim E_{-1} &= p-1
.\]

Thus
\[
JCF_{\FF_p}(A)
=  J_{-1}^{2} \oplus (p-2)J_{-1}^1
= \left[\begin{array}{rr|r|r|r|r}
-1 & 1 & 0 & \cdots & 0 & 0 \\
0& -1 & 0 & 0 & 0 & 0 \\
\hline
0& 0 & -1 & 0 & 0 & 0 \\ \hline
0& 0 & 0 & \ddots & \ddots & 0 \\ \hline
0& 0 & 0 & \cdots & -1 & 0 \\ \hline
0& 0 & 0 & \cdots & 0 & -1 \\
\end{array}\right]
.\]

To obtain a basis for $E_{\lambda = 0}$, first note that the matrix $P = [\vector v_1, \vector p_1, \cdots , \vector p_{p-1}]$ from part (a) is singular over $\FF_p$, since
\[
\vector v_1 + \vector p_1 + \vector p_2 + \cdots + \vector p_{p-2}
&= [p-1, 0, 0, \cdots, 0, 1] \\
&= [-1, 0,0,\cdots, 0, 1] \\
&= - \vector p_{p-1}
.\]

We still have a linearly independent set given by the first $p-1$ columns of $P$, so we can extend this to a basis by finding one linearly independent generalized eigenvector.

Solving $(A-I\lambda)\vector x = \vector v_1$ is our only option (the others won't yield solutions).
This amounts to solving $B\vector x = \vector v_1$, which imposes the condition $\sum x_i = 1$, so we can choose $\vector x = [1, 0, \cdots, 0]$.

Thus
\[
P = [\vector v_1, \vector x, \vector p_1, \cdots, \vector p_{p-2}] =
\left[\begin{array}{rrrrrr}
1 & 1 & 1 & 1 & 1 & 1  \\
1 & 0 & -1 & 0 & 0 & 0 \\
1 & 0 & 0 & -1 & 0 & 0 \\
1 & \vdots & \vdots & \vdots & \ddots & \vdots \\
1 & 0 & 0 & 0 & 0 & -1\\
1 & 0 & 0 & 0 & 0 & 0 \\
\end{array}\right]
.\]

## 8

Concepts used:

- $\zeta_n \definedas e^{2\pi i \over n}$, and $\zeta_n^k$ is a primitive $n$th root of unity $\iff \gcd(n, k) = 1$
  - In general, $\zeta_n^k$ is a primitive ${n \over \gcd(n, k)}$th root of unity.
- $\deg \Phi_n(x) = \phi(n)$
- $\phi(p^k) = p^k - p^{k-1} = p^{k-1}(p-1)$ (proof: for a nontrivial gcd, the possibilities are $p, 2p, 3p, 4p, \cdots, p^{k-2}p, p^{k-1}p$.)
- $\Gal(\QQ(\zeta)/\QQ) \cong \ZZ/(n)\units$

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

# Fall 2018

## 1 \label{problem:session_1_6_1_soln}

Concepts Used:

- Sylow 2: All Sylow $p\dash$subgroups are conjugate.
- $\abs{HK} = \abs{H} \abs{K} / \abs{H\intersect K}$.
- Lagrange's Theorem: $H\leq G \implies \abs{H} \divides \abs{G}$

### a

- Every $p\dash$subgroup is contained in some Sylow $p\dash$subgroup, so $P \subseteq S_p^i$ for some $S_p^i \in \mathrm{Syl}_p(G)$.

- $P \normal G \iff gPg\inv = P$ for all $g\in G$.

- Let $S_p^j$ be any other Sylow $p\dash$subgroup, 
- Since Sylow $p\dash$subgroups are all conjugate $gS_p^i g\inv = S_p^j$ for *some* $g\in G$.

- Then 
\begin{align*}
P = gPg\inv \subseteq gS_p^i g\inv = S_p^j
.\end{align*}

### b

- If $P$ is not contained in $M$, then $M < MP$ is a proper subgroup
- By maximality of $M$, $MP = G$
- Note that $M\intersect P \leq P$ and $\abs{P} = p^c$ implies $\abs{M\intersect P} = p^a$ for some $a\leq c$ by Lagrange
- Then write
  \begin{align*}
  G = MP
  &\iff \abs{G} = \frac{\abs{M} \abs{P}}{\abs{M\intersect P}} \\ \\
  &\iff { \abs{G} \over \abs{M}} = {\abs{P}  \over \abs{M\intersect P}} = {p^c \over p^a} = p^{c-a} \definedas p^b
  \end{align*}

  where $a\leq c \implies 0 \leq c-b \leq c$ so $0\leq b \leq c$.

## 2 \label{problem:session_1_6_2_soln}

Concepts used:

- Orbit: $G\cdot x \definedas \theset{g\cdot x \suchthat g\in G} \subseteq X$
- Stabilizer: $G_x \definedas \theset{g\in G\suchthat g\cdot x = x} \leq G$
- Orbit-Stabilizer: $G\cdot x \simeq G/G_x$.
- $abc\in H \iff b\in a\inv H c\inv$
- Set of orbits for $G\actson X$, notated $X/G$.
- Set of fixed points for $G\actson X$, notated $X^g$.
- Burnside's Lemma: $\abs{X/G} \cdot \abs{G} = \sum_{g\in G} \abs{X^g}$ 
  - Number of orbits equals average number of fixed points.

### a

- Fix $x$ and let $y\in G_x$ be another element in the orbit of $x$.
- Then there exists a $g\in G$ such that $g\cdot x = y$, so $x = g\inv \cdot y$
- Then
\begin{align*}
h \in G\cdot x 
&\iff h\cdot x = x \qtext{by being in the stabilizer} \\
&\iff h\cdot (g\inv \cdot y) = g\inv \cdot y \qtext{using that $x, y$ are in the same orbit} \\
&\iff (g h g\inv) \cdot y = y \\
&\iff ghg\inv \in G_y \qtext{by the defn of the stabilizer}\\
&\iff h\in g\inv G_y g
,\end{align*}

so every $h\in G\cdot x$ is conjugate to some element in $G_y$.

### b

Let $G$ act on its subgroups by conjugation, 

- The orbit $G\cdot H$ is the set of all subgroups conjugate to $H$, and

- The stabilizer of $H$ is $G_H = N_G(H)$.

- By orbit-stabilizer,
\begin{align*}
G\cdot H = [G: G_H] = [G: N_G(H)]
.\end{align*}

- Since $\abs H = n$, and all of its conjugate also have order $n$.

- Note that 
\begin{align*}
H\leq N_G(H) \implies \abs{H} \leq \abs{N_G(H)} \implies {1\over \abs{N_G(H)}} \leq {1\over \abs{H}}
,\end{align*}

- Now *strictly* bound the size of the union by overcounting their intersections at the identity:
\begin{align*}
\abs{\union_{g\in G}gHg\inv} 
&< (\text{Number of Conjugates of } H) \cdot (\text{Size of each conjugate}) \\ 
&\qquad \qquad\textit{strictly overcounts since they intersect in at least the identity} \\
& = [G: N_G(H)] \abs{H} \\
&= {\abs{G} \over \abs{N_G(H)}} \abs{H} \qtext{since $G$ is finite} \\
&\leq {\abs G \over \abs H} \abs H \\
&= \abs{G}
.\end{align*}

### c

- Let $G\actson X$ transitively where $\abs{X} \geq 2$
- An action is transitive iff there is only one orbit, so $\abs{X/G} = 1$.
- Apply Burnside's Lemma
\begin{align*}
1 = \abs{X/G} = \frac{1}{\abs G} \sum_{g\in G} \abs{X^g} \implies \abs{G} = \sum_{g\in G} \abs{X^g}
\end{align*}
- Note that $X^e = X$, since the identity must fix every element, so $\abs{X^e} \geq 2$.
- Not *every* other term in the sum can be greater than 1, otherwise the RHS is greater than the size of $G$
- Thus we must have $\abs{X^g} = 0$ for some $g\in G$, i.e. $g$ has no fixed points in $X$.

## 3

Let $L/K/F$.

### a

**False**: 
Take $L/K/F = \QQ(\zeta_2, \sqrt[3] 2) \to \QQ(\sqrt[3] 2) \to \QQ$.

Then $L/F$ is Galois, since it is the splitting field of $x^3 - 2$ and $\QQ$ has characteristic zero.

But $K/F$ is not Galois, since it is not the splitting field of any irreducible polynomial.

### b

**True**: 
If $L/F$ is Galois, then $L/K$ is normal and separable:

- $L/K$ is normal, since if $\sigma: L \injects \overline K$ lifts the identity on $K$ and fixes $L$, i-t also lifts the identity on $F$ and fixes $L$ (and $\overline K = \overline F$).

- $L/K$ is separable, since $F[x] \subseteq K[x]$, and so if $\alpha \in L$ where $f(x) \definedas \min(\alpha, F)$ has no repeated factors, then $f'(x) \definedas \min(\alpha, K)$ divides $f$ and thus can not have repeated factors.

### c

**False**: 
Use the fact that every quadratic extension is Galois, and take $L/K/F = \QQ(\sqrt[4] 2) \to \QQ(\sqrt 2) \to \QQ$.

Then each successive extension is quadratic (thus Galois) but $\QQ(\sqrt[4] 2)$ is not the splitting field of any polynomial (noting that it does not split $x^4 - 2$ completely.)

## 4

Let $m(x)$ be the minimal polynomial of $\phi$.
If the polynomial $f(x) = x$ doesn't divide $m$, then $f$ does not have zero as an eigenvalue, so $\phi$ is nonsingular and since $0$ is nilpotent, $\phi + 0$ works.

Otherwise, write $\phi(x) = x^m \rho(x)$ where $\gcd(x, \rho(x)) = 1$.

Then
\begin{align*}
V \cong \frac{k[x]}{m(x)} \cong \frac{k[x]}{(x^m)} \oplus \frac{k[x]}{(\rho)}
\definedas U \oplus W
\end{align*}
by the Chinese Remainder theorem.

We can now note that $\restrictionof{\phi}{U}$ is nilpotent because it has characteristic polynomial $x^m$, and $\restrictionof{\phi}{W}$ is nonsingular since $\lambda = 0$ is not an eigenvalue by construction.

## 5

### a

Letting $\vector v$ be fixed, since $\theset{A^j \vector v}$ spans $V$ we have 
\begin{align*}
B\vector v = \sum_{j=0}^{n-1}c_j A^j \vector v
.\end{align*}

So let $p(x) = \sum_{j=0}^{n-1}c_jx^j$.
Then consider how $B$ acts on any basis vector $A^k \vector v$.

We have 
\begin{align*}
BA^k \vector v 
&= A^k B\vector v \\
&= A^k p(A) \vector v \\
&= p(A) A^k \vector v
,\end{align*}

so $B = p(A)$ as operators since their actions agree on every basis vector in $V$.

### b

$\implies$:

If $\theset{A^j \vector v_k \suchthat 0\leq j \leq n-1}$ is linearly independent, this means that $A$ does satisfy any polynomial of degree $d < n$.

So $\deg m_A(x) = n$, and since $m_A(x)$ divides $\chi_A(x)$ and both are monic degree polynomials of degree $n$, they must be equal.

$\impliedby$:

Let $A\actson k[x]$ by $A \actson p(x) \definedas p(A)$.
This induces an invariant factor decomposition $V =\cong \bigoplus k[x]/(f_i)$.
Since the product of the invariant factors is the characteristic polynomial, the largest invariant factor is the minimal polynomial, and these two are equal, there can only be one invariant factor and thus the invariant factor decomposition is
$$
V\cong \frac{k[x]}{(\chi_A(x))}
$$
as an isomorphism of $k[x]\dash$modules.

So $V$ is a cyclic $k[x]$ module, which means that $V = k[x]\actson \vector v$ for some $\vector v\in V$ such that $\ann(\vector v) = \chi_A(x)$.

> I.e. there is some element $\vector v\in V$ whose orbit is all of $V$.

But then noting that monomials span $k[x]$, we can write
\begin{align*}
V &\cong
k[x] \actson \vector v \\
&\definedas \theset{f(x) \actson \vector v \suchthat f \in k[x]} \\
&= \spanof_k \theset{x^k \actson \vector v \suchthat k \geq 0} \\
&\definedas \spanof_k \theset{A^k\vector v \suchthat k \geq 0}
.\end{align*}

Moreover, we can note that if $k \geq \deg \chi_A(x)$, then $A^k$ is a linear combination of $\theset{A^j \mid 0 \leq j \leq n-1}$, and so
\begin{align*}
V &\cong \spanof_k \theset{A^k\vector v \suchthat k \geq 0} \\
&= \spanof_k \theset{A^k\vector v \suchthat 1 \leq k \leq n-1}
.\end{align*}

$\qed$

## 6

### a

By the correspondence theorem, submodules of $M/N$ biject with submodules $A$ of $M$ containing $N$.

So 

- $M$ is maximal:

- $\iff$ no such (proper, nontrivial) submodule $A$ exists 

- $\iff$ there are no (proper, nontrivial) submodules of $M/N$ 

- $\iff M/N$ is simple.

### b

Identify $\ZZ\dash$modules with abelian groups, then by (a), $N$ is maximal $\iff$ $M/N$ is simple $\iff$ $M/N$ has no nontrivial proper subgroups.

By Cauchy's theorem, if $\abs{M/N} = ab$ is a composite number, then $a\divides ab \implies$ there is an element (and thus a subgroup) of order $a$.
In this case, $M/N$ contains a nontrivial proper cyclic subgroup, so $M/N$ is not simple.
So $\abs{M/N}$ can not be composite, and therefore must be prime.

### c

Let $G = \theset{x \in \CC \suchthat x^n=1 \text{ for some }n\in \NN}$, and suppose $H < G$ is a proper subgroup.

Then there must be a prime $p$ such that the $\zeta_{p^k} \not \in H$ for all $k$ greater than some constant $m$ -- otherwise, we can use the fact that if $\zeta_{p^k} \in H$ then $\zeta_{p^\ell} \in H$ for all $\ell \leq k$, and if $\zeta_{p^k} \in H$ for all $p$ and all $k$ then $H = G$.

But this means there are infinitely many elements in $G\setminus H$, and so $\infty = [G: H] = \abs{G/H}$ is not a prime. 
Thus by (b), $H$ can not be maximal, a contradiction.

$\qed$


## 7

### a

Let $\phi$ denote the map in question, it suffices to show that $\phi$ is $R\dash$linear, i.e. $\phi(s\vector x + \vector y) = s\phi(\vector x) + \phi(\vector y)$:

\begin{align*}
\phi(s\vector x + \vector y) 
&= r(s\vector x + \vector y) \\
&= rs\vector x + r\vector y \\
&= s(r\vector x) + (r\vector y) \\
&= s\phi(\vector x) + \phi(\vector y)
.\end{align*}

### b

We identify $\ker \phi = \theset{x\in R \suchthat rx = 0}$, and since $r\neq 0$ by assumption, this implies each such $x$ is a zero divisor by definition (and $\ker \phi$ is nonempty by assumption).

Similarly, we identify $\im \phi = \theset{y = rx \suchthat x\in R}$. 
So let $y\in \im \phi$.
Since $r$ is a zero divisor, there exists some $z\in R$ such that $rz = 0$.

But then 
$$
yz = rxz = xrz = x\cdot 0 = 0
$$ 
since $R$ is commutative, so $y$ is a zero divisor.


### c

> See 1964 Annals "Properties of rings with a finite number of zero divisors"

Let $Z \definedas \theset{z_i}_{i=1}^n$ be the set of $n$ zero divisors in $R$.
Let $\phi_i$ be the $n$ maps $x \mapsto z_i x$, and let $K_i = \ker \phi_i$ be the corresponding kernels.

Fix an $i$.
By (b), $K_i$ consists of zero divisors, so 
$$
\abs{K_i} \leq n < \infty \quad \text{for each } i
.$$

Now consider $R/K_i \definedas \theset{r + K_i}$.
By the first isomorphism theorem, $R/K_i \cong \im \phi$, and by (b) every element in the image is a zero divisor, so 
$$
[R: K_i] = \abs{R/K_i} = \abs{\im \phi_i} \leq n 
.$$

But then 
$$
\abs{R} = [R:K_i]\cdot \abs{K_i} \leq n\cdot n = n^2 
.$$

### d

By (c), if there are exactly 2 zero divisors then $\abs{R} \leq 4$.
Since every element in a finite ring is either a unit or a zero divisor, and $\abs{R\units} \geq 2$ since $\pm 1$ are always units, we must have $\abs{R} = 4$.

Since the characteristic of a ring must divide its size, we have $\ch R = 2$ or $4$.

Using the hint, we see that only $\ZZ/(4)$ has characteristic 4, which has exactly 2 zero divisors given by $[0]_4$ and $[2]_4$.

If $R$ has characteristic 2, we can check the other 3 possibilities.

We can write $\ZZ/(2)[t]/(t^2) = \theset{a + bt \suchthat a,b\in \ZZ/(2)}$, and checking the multiplication table we have

\begin{align*}
\begin{array}{c|cccc}
			& 0 & 1 	& t & 1+t 	\\ \hline
0 		& 0 & 0 	& 0 & 0   	\\ 
1 		& 0 & 1 	& t & 1+t 	\\ 
t 		& 0 & t 	& \mathbf{0} & t   	\\ 
1 + t & 0 & 1+t & t & 1   	\\ 
\end{array}
,\end{align*}

and so we find that $t, 0$ are the zero divisors.

In $\ZZ/(2)[t]/(t^2 - t)$, we can check that $t^2 = t \implies t t^2 = t^2 \implies t(t^2 + 1) = 0 \implies t(t+1) = 0$, so both $t$ and $t+1$ are zero divisors, along with zero, so this is not a possibility.

Similarly, in $\ZZ/(2)[t]/(t^2 + t + 1)$, we can check the bottom-right corner of the multiplication table to find
\begin{align*}
\left[\begin{array}{c|cc}
	& t 	& 1 +t \\ \hline
t & 1+t & 1 \\
t & 1 	& t \\
\end{array}\right]
,\end{align*}

and so this ring only has one zero divisor.

Thus the only possibilities are:

\begin{align*}
R &\cong \ZZ/(4) \\
R &\cong \ZZ/(2)[t] / (t^2)
.\end{align*}

$\qed$

# Spring 2018

## 1 \label{problem:session_1_5_1_soln}

Concepts Used:

- Centralizer: $C_G(x) = \theset{g\in G \suchthat [gx] = 1}$.
- Class Equation: $\abs{G} = \abs{Z(G)} + \sum [G: C_G(x_i)]$
- $G/Z(G)$ cyclic $\iff G$ is abelian.
  
  > *Proof:*
    \begin{align*}
    G/Z(G) = \generators{xZ} 
    &\iff g\in G \implies gZ = x^mZ \\
    &\iff g(x^m)\inv \in Z \\
    &\iff g = x^m z \qtext{for some}z\in Z\\
    &\implies gh = x^mz_1 x^n z_2 = x^n z_2 x^m z_1 = hg
    .\end{align*}

- Every group of order $p^2$ is abelian.
- Classification of finite abelian groups.

### a

Strategy: get $p$ to divide $\abs{Z(G)}$.

- Apply the class equation:
\begin{align*}
\abs{G} = \abs{Z(G)} + \sum [G: C_G(x_i)]
.\end{align*}

- Since $C_G(x_i) \leq G$ and $\abs{G} = p^k$, by Lagrange $\abs{C_G(x_i)} = p^\ell$ for some $0\leq \ell \leq k$.
- Since $\abs{G} = p^k$ for some $k$ and $Z(G), C_G(x_i) \leq G$ are subgroups, their orders are powers of $p$.
- Use $$[G: C_G(x_i)] = 1 \iff C_G(x_i) = G \iff \theset{g\in G\suchthat gx_ig\inv = x_i} = G \iff x_i \in Z(G).$$
  - Thus every index appearing in the sum is greater than 1, and thus equal to $p^{\ell_i}$ for some $1\leq \ell_i \leq k$
  - So $p$ divides every term in the sum

- Rearrange 
\begin{align*}
\abs{G} -  \sum [G: C_G(x_i)]
= \abs{Z(G)} 
.\end{align*}

- $p$ divides both terms on the LHS, so must divide the RHS, so $\abs{Z(G)} \geq p$.


### b

Strategy: examine $\abs{G/Z(G)}$ by cases.

- $1$: Then $G = Z(G)$ and $G$ is abelian.
- $p$: Then $G/Z(G)$ is cyclic so $G$ is abelian
- $p^2$: Not possible, since $\abs {Z(G)} > 1$ by (a).

### c

- By Sylow

  - $n_5 \divides 7^2,\quad n_5\cong 1\mod 5 \implies n_5\in\theset{1, 7, 49}\setminus\theset{7, 49} = \theset{1} \implies n_5 = 1$
  - $n_7 \divides 5^2, \quad n_7 \cong 1 \mod 7 \implies n_7 \in \theset{1, 5, 25}\setminus\theset{5, 25} =\theset{1} \implies n_7 = 1$

- By recognition of direct products, $G = S_5 \cross S_7$
  - By above, $S_5, S_7\normal G$
  - Check $S_5\intersect S_7 = \theset{e}$ since they have coprime order.
  - Check $S_5S_7 = G$ since $\abs{S_5 S_7} = 5^2 7^2 = \abs{G}$

- By (b), $S_5, S_7$ are abelian since they are groups of order $p^2$
- The direct product of abelian groups is abelian.

### d

1. $\ZZ_{5^2} \cross \ZZ_{7^2}$
1. $\ZZ_{5}^2 \cross \ZZ_{7^2}$
1. $\ZZ_{5^2} \cross \ZZ_{7}^2$
1. $\ZZ_{5}^2 \cross \ZZ_{7}^2$

$\qed$

## 2

> Not the nicest proof! Would be better to replace the ad-hoc computations at the end..

### a

Note that $g(x) = x^2 - 4x + 2$ has roots $\beta = 2 \pm \sqrt{2}$, and so $f$ has roots 
\begin{align*}
\alpha_1 &= \sqrt{2 + \sqrt 2} \\
\alpha_2 &= \sqrt{2 - \sqrt 2} \\
\alpha_3 &= -\alpha_1 \\
\alpha_4 &= -\alpha_2
.\end{align*}

and splitting field $K = \QQ(\theset{\alpha_i})$.

### b

$K$ is the splitting field of a separable polynomial and thus Galois over $\QQ$.
Moreover, Since $f$ is irreducible by Eisenstein with $p=2$, the Galois group is a transitive subgroup of $S^4$, so the possibilities are:

- $S_4$
- $A_4$
- $D_4$
- $\ZZ/(2) \cross \ZZ/(2)$
- $\ZZ/(4)$

We can note that $g$ splits over $L \definedas \QQ(\sqrt 2)$, an extension of degree 2.

We can now note that $\min(\alpha, L)$ is given by $p(x) = x^2 - (2 + \sqrt 2)$, and so $[K: L] = 2$.

We then have
\begin{align*}
[K: \QQ] = [K: L] [L : \QQ] = (2)(2) = 4
.\end{align*}

This $\abs{\Gal(K/\QQ)} = 4$, which leaves only two possibilities:

- $\ZZ/(2) \cross \ZZ/(2)$
- $\ZZ/(4)$

We can next check orders of elements.
Take
\begin{align*}
\sigma &\in \Gal(K/\QQ) \\
\alpha_1 &\mapsto \alpha_2
.\end{align*}


Computations show that 

- $\alpha_1^2 \alpha_2^2 = 2$, so $\alpha_1 \alpha_2 = \sqrt 2$
- $\alpha_1^2 = 2 + \sqrt 2 \implies \sqrt 2 = \alpha_1^2 - 2$

and thus
\begin{align*}
\sigma^2(\alpha_1) &= \sigma(\alpha_2) \\
&= \sigma\left(\frac{\sqrt 2}{\alpha_1}\right) \\
&= \frac{\sigma(\sqrt 2)}{\sigma(\alpha_1)} \\
&= \frac{\sigma(\alpha_1^2 - 2)}{\alpha_2} \\
&= \frac{\alpha_2^2 - 2}{\alpha_2} \\
&= \alpha_2 -2\alpha_2\inv \\
&= \alpha_2 - \frac{2\alpha_1}{\sqrt 2} \\
&= \alpha_2 -\alpha_1 \sqrt 2 \\
&\neq \alpha_1
,\end{align*}

and so the order of $\sigma$ is strictly greater than 2, and thus 4, and thus $\Gal(K/\QQ) = \theset{\sigma^k \suchthat 1\leq k \leq 4} \cong \ZZ/(4)$.

### c


?? The subgroup of index 2 $\generators{\sigma^2}$ corresponds to the field extension $Q(\sqrt 2) / \QQ$.

## 3

> Moral: $H_1 \intersect H_2 \iff E_1 E_2$, $H_1 H_2 \iff E_1 \intersect E_2$.

### a

By the Galois correspondence, it suffices to show that the fixed field of $H_1 \intersect H_2$ is $E_1 E_2$.

Let $\sigma \in H_1 \intersect H_2$; then $\sigma \in \Aut(K)$ fixes both $E_1$ and $E_2$.

> Not sure if this works -- compositum is not literally product..?

Writing $x \in E_1E_2$ as $x=e_1 e_2$, we have 
$$
\sigma(x) = \sigma(e_1 e_2) = \sigma(e_1) \sigma(e_2) = e_1 e_2  =x,
$$

so $\sigma$ fixes $E_1 E_2$.

### b

That $H_1 H_2 \subseteq G$ is clear, since if $\sigma = \tau_1 \tau_2 \in H_1 H_2$, then each $\tau_i$ is an automorphism of $K$ that fixes $E_i \supseteq \QQ$, so each $\tau_i$ fixes $\QQ$ and thus $\sigma$ fixes $\QQ$.

That it is a subgroup follows from the fact that elements commute. (?)
 
To see this, let $\sigma = \sigma_1 \sigma_2 \in H_1 H_2$.

Note that $\sigma_1(e) = e$ for all $e\in E_1$ by definition, since $H_1$ fixes $E_1$, and $\sigma_2(e) \in E_1$ (?).

Then 
$$
\sigma_1(e) = e \quad \forall e \in E_1 \implies \sigma_1(\sigma_2(e)) = \sigma_2(e) 
$$  

and substituting $e = \sigma_1(e)$ on the RHS yields

\begin{align*}
\sigma_1 \sigma_2(e) = \sigma_2 \sigma_1(e)
,\end{align*}

where a similar proof holds for $e\in E_2$ and thus for arbitrary $x\in E_1 E_2$.


### c

By the Galois correspondence, the subgroup $H_1H_2 \leq G$ will correspond to an intermediate field $E$ such that $K/E/\QQ$ and $E$ is the fixed field of $H_1 H_2$.

But if $\sigma \in H_1 H_2$, then $\sigma = \tau_1 \tau_2$ where $\tau_i$ is an automorphism of $K$ that fixes $E_i$, and so $\sigma(x) = x \iff \tau_1\tau_2(x) = x \iff \tau_2(x) = x ~\&~ \tau_1(x) = x \iff x \in E_1 \intersect E_2$.

# Spring 2015

## 4

# Spring 2013

## 6

Lemma: every $\vector v\in V$ is $T\dash$cyclic $\iff \chi_T(x)/\kk$ is irreducible.

- $\implies$: Same as argument below.
- $\impliedby$: Suppose $f$ is irreducible, then $f$ is equal to the minimal polynomial of $T$.
- 

### a

Let $f$ be the characteristic polynomial of $T$.

$\implies$:

- By contrapositive, suppose there is a proper nonzero invariant subspace $W<V$ with $T(W) \subseteq W$, we will show the characteristic polynomial $f \definedas \chi_{V, T}(x)$ is reducible.
- Since $T(W)\subseteq W$, the restriction $g\definedas \chi_{V, T}(x) \mid_W: W\to W$ is a linear operator on $W$.
- Claim: $g$ divides $f$ in $\FF[x]$ and $\deg(g) < \deg(f)$.
  - Matrix-dependent proof: \todo{Is there a proof without matrices? What if $V$ is infinite dimensional?}
    - Choose an ordered basis for $W$, say $\mcb_W \definedas \theset{\vector w_1, \cdots, \vector w_k}$ where $k=\dim_F(W)$
    - Claim: this can be extended to a basis of $V$, say $\mcb_V \definedas \theset{\vector w_1, \cdots, \vector w_k, \vector v_1, \cdots, \vector v_j}$ where $k+j = \dim_F(V)$.\todo{How to extend basis?}
      - Note that since $W<V$ is proper, $j\geq 1$.
    - Restrict $T$ to $W$ to get $T_W$, then let $B = [T_W]_{\mcb_W}$ be the matrix representation of $T_W$ with respect to $\mcb_W$.
    - Now consider the matrix representation $[T]_{\mcb_V}$, in block form this is given by
    \begin{align*}
    [T]_{\mcb_V} = 
    \begin{bmatrix}
    B & C \\
    0 & D
    \end{bmatrix}
    \end{align*}
      where we've used that $W<V$ is proper to get the existence of $C, D$ (there is at least one additional row/column since $j\geq 1$ in the extended basis.)
    \todo{Why?}
    - Now expand along the first column block to obtain
    \begin{align*}
    \chi_{T, V}(x) \definedas \det([T]_{\mcb_V} - xI) = \det(B - xI)\cdot \det(D - xI) \definedas \chi_{T, W}(x) \cdot \det(D-xI)
    .\end{align*}
    - Claim: $\det(D - xI) \in xF[x]$ is nontrivial
    - The claim follows because this forces $\deg(\det(D-xI)) \geq 1$ and so $\chi_{T, W}(x)$ is a proper divisor of $\chi_{T, V}(x)$.
- Thus $f$ is reducible.

$\impliedby$

- Suppose $f$ is reducible, then we will produce a proper $T\dash$invariant subspace.
- Claim: if $f$ is reducible, there exists a nonzero, noncyclic vector $\vector v$.
- Then $\spanof_k\theset{T^j\vector v}_{j=1}^d$ is a $T\dash$invariant subspace that is nonzero, and not the entire space since $\vector v$ is not cyclic.

### b

Characterization of diagonalizability: $T$ is diagonalizable over $F \iff \min_{T, F}$ is squarefree in $\bar{F}[x]$?

- Let $\min_{T, F}(x)$ be the minimal polynomial of $T$ and $\chi_{T, F}(x)$ be its characteristic polynomial.
- By Cayley-Hamilton, $\min_{T, F}(x)$ divides $\chi_{T, F}$
- Since $\chi_{T, F}$ is irreducible, these polynomials are equal.
- Claim: $T/F$ is diagonalizable $\iff \min_{T, F}$ splits over $F$ and is squarefree.
- Replace $F$ with its algebraic closure, then $\min_{T, F}$ splits.
- Claim: in characteristic zero, every irreducible polynomial is separable
  - Proof: it must be the case that either $\gcd(f, f') = 1$ or $f' \equiv 0$, where the second case only happens in characteristic $p>0$.
  - The first case is true because $\deg f' < \deg f$, and if $\gcd(f, f') = p$, then $\deg p < \deg f$ and $p\divides f$ forces $p=1$ since $f$ is irreducible.
- So $\min_{T, F}$ splits into distinct linear factors
- Thus $T$ is diagonalizable.

# Spring 2013

## 1

Possibly useful facts:

- Normal subgroups correspond to normal extensions (any polynomial with one root in the extension $L/k$ splits in $L$)
- If $L$ is finite and separable (automatic if $K$ is finite or characteristic zero), then $L/k$ is normal iff $L$ is the splitting field of an irreducible polynomial in $k[x]$.


## 2
