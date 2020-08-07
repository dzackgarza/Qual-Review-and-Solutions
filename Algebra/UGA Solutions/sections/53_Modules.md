# Modules

## Torsion and the Structure Theorem

## Spring 2020 #6
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

## Fall 2019 #5

> One-step submodule test.

### a

It suffices to show that 
$$
r\in R, ~t_1, t_2\in \Tor(M) \implies rt_1 + t_2 \in \Tor(M)
.$$

We have
\[
t_1 \in \Tor(M) &\implies \exists s_1 \neq 0 \text{ such that } s_1 t_1  = 0 \\
t_2 \in \Tor(M) &\implies \exists s_2 \neq 0 \text{ such that } s_2 t_2  = 0 
.\]

Since $R$ is an integral domain, $s_1 s_2 \neq 0$.
Then
\[
s_1 s_2(rt_1 + t_2) 
&= s_1 s_2 r t_1 + s_1 s_2t_2 \\
&= s_2 r (s_1 t_1) + s_1 (s_2 t_2)  \quad\text{since $R$ is commutative} \\
&=  s_2 r(0) + s_1(0) \\
&= 0
.\]

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

## Spring 2019 #5

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

    - Then using the definition of coset addition/multiplication, we can write this as
  \[  
  \sum_{i=1}^n \qty { s_i \vector r_i + \tor(M)} = 
  \qty{ \sum_{i=1}^n  s_i \vector r_i} + \tor(M)  = 0_{\tilde M}
  .\]
    - Since $\tilde{\vector x} = 0 \in \tilde M \iff \tilde{\vector x} = \vector x + \tor(M)$ where $\vector x \in \tor(M)$, this forces $\sum s_i \vector r_i \in \tor(M)$.

    - Then there exists a scalar $\alpha\in R\nonzero$ such that $\alpha \sum s_i \vector r_i = 0_M$.

    - Since $R$ is an integral domain and $\alpha \neq 0$, we must have $\sum s_i \vector r_i = 0_M$.

    - Since $\theset{\vector r_i}$ was linearly independent in $M$, we must have $s_i = 0_R$ for all $i$.

  - **Spanning:**

    - Write $\pi(\mathcal B) = \theset{\vector r_i + \Tor(M)}_{i=1}^n$ as a set of cosets.

    - Letting $\vector x \in M'$ be arbitrary, we can write $\vector x = \vector m + \tor(M)$ for some $\vector m \in M$ where $\pi(\vector m) = \vector x$ by surjectivity of $\pi$.

    - Since $\mathcal B$ is a basis for $M$, we have $\vector m = \sum_{i=1}^n s_i \vector r_i$, and so
  \[
  \vector x
  &= \pi(\vector m) \\
  &\definedas \pi\qty{ \sum_{i=1}^n s_i \vector r_i} \\
  &= \sum_{i=1}^n s_i \pi(\vector r_i) \quad\text{since $\pi$ is an $R\dash$module morphism}\\
  &\definedas \sum_{i=1}^n s_i \vector (\vector r_i + \tor(M))
  ,\]
  which expresses $\vector{x}$ as a linear combination of elements in $\mathcal B'$.

### c

> Notation: Let $0_R$ denote $0\in R$ regarded as a ring element, and $\vector 0 \in R$ denoted $0_R$ regarded as a module element (where $R$ is regarded as an $R\dash$module over itself)

**$M$ is not free:**

- **Claim**: If $I\subseteq R$ is an ideal *and* a free $R\dash$module, then $I$ is principal .

  - Suppose $I$ is free and let $I = \generators{B}$ for some basis, we will show $\abs{B} = 1$>
  - Toward a contradiction, suppose $\abs{B} \geq 2$ and let $m_1, m_2\in B$.
  - Then  since $R$ is commutative, $m_2 m_1 - m_1 m_2 = 0$ and this yields a linear dependence
  - So $B$ has only one element $m$.

  - But then $I = \gens{m} = R_m$ is cyclic as an $R\dash$ module and thus principal as an ideal of $R$. 

  - Now since $M$ was assumed to *not* be principal, $M$ is not free (using the contrapositive of the claim).

**$M$ is rank 1**:

- For any module, we can take an element $\vector m\in M\nonzero$ and consider the cyclic submodule $R\vector m$.

- Since $M$ is not principle, it is not the zero ideal, and contains at least two elements. So we can consider an element $\vector m\in M$.

- We have $\rank_R(M) \geq 1$, since $R\vector m \leq M$ and $\theset{m}$ is a subset of some spanning set.

- $R\vector m$ can not be linearly dependent, since $R$ is an integral domain and $M\subseteq R$, so $\alpha \vector m = \vector 0 \implies \alpha = 0_R$.

- Claim: since $R$ is commutative, $\rank_R(M) \leq 1$.

  - If we take two elements $\vector m, \vector n \in M\nonzero$, then since $m, n\in R$ as well, we have $nm = mn$ and so
\[
(n)\vector m + (-m)\vector n = 0_R = \vector 0
\]
  is a linear dependence.

**$M$ is torsion-free**:

- Let $\vector x \in \tor M$, then there exists some $r\neq 0\in R$ such that $r\vector x = \vector 0$.

- But $\vector x\in R$ as well and $R$ is an integral domain, so $\vector x=0_R$, and thus $\tor(M) = \theset{0_R}$.

$\qed$


