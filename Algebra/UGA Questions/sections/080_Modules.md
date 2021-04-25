# Modules

## General Questions

### Fall 2018 #6 $\done$
Let $R$ be a commutative ring, and let $M$ be an $R\dash$module. 
An $R\dash$submodule $N$ of $M$ is maximal if there is no $R\dash$module $P$ with $N \subsetneq P \subsetneq M$.

a.
Show that an $R\dash$submodule $N$ of $M$ is maximal $\iff M /N$ is a simple $R\dash$module: i.e., $M /N$ is nonzero and has no proper, nonzero $R\dash$submodules.

b.
Let $M$ be a $\ZZ\dash$module. Show that a $\ZZ\dash$submodule $N$ of $M$ is maximal $\iff \#M /N$ is a prime number.

c.
Let $M$ be the $\ZZ\dash$module of all roots of unity in $\CC$ under multiplication.
Show that there is no maximal $\ZZ\dash$submodule of $M$.

:::{.solution}


\envlist
:::{.concept}
\envlist

- Todo
:::


:::{.proof title="of a"}
By the correspondence theorem, submodules of $M/N$ biject with submodules $A$ of $M$ containing $N$.

So 

- $M$ is maximal:

- $\iff$ no such (proper, nontrivial) submodule $A$ exists 

- $\iff$ there are no (proper, nontrivial) submodules of $M/N$ 

- $\iff M/N$ is simple.

:::

:::{.proof title="of b"}
Identify $\ZZ\dash$modules with abelian groups, then by (a), $N$ is maximal $\iff$ $M/N$ is simple $\iff$ $M/N$ has no nontrivial proper subgroups.
\

By Cauchy's theorem, if $\abs{M/N} = ab$ is a composite number, then $a\divides ab \implies$ there is an element (and thus a subgroup) of order $a$.
In this case, $M/N$ contains a nontrivial proper cyclic subgroup, so $M/N$ is not simple.
So $\abs{M/N}$ can not be composite, and therefore must be prime.

:::

:::{.proof title="of c"}
Let $G = \theset{x \in \CC \suchthat x^n=1 \text{ for some }n\in \NN}$, and suppose $H < G$ is a proper subgroup.

Then there must be a prime $p$ such that the $\zeta_{p^k} \not \in H$ for all $k$ greater than some constant $m$ -- otherwise, we can use the fact that if $\zeta_{p^k} \in H$ then $\zeta_{p^\ell} \in H$ for all $\ell \leq k$, and if $\zeta_{p^k} \in H$ for all $p$ and all $k$ then $H = G$.

But this means there are infinitely many elements in $G\setminus H$, and so $\infty = [G: H] = \abs{G/H}$ is not a prime. 
Thus by (b), $H$ can not be maximal, a contradiction.


:::

:::

### Fall 2019 Final #2  $\work$
Consider the $\ZZ\dash$submodule $N$ of $\ZZ^3$ spanned by 
\[
f_1 &= [-1, 0, 1], \\
f_2 &= [2,-3,1], \\
f_3 &= [0, 3, 1], \\
f_4 &= [3,1,5]
.\] 
Find a basis for $N$ and describe $\ZZ^3/N$.

### Spring 2018 #6 $\work$
Let
\[
M &= \{(w, x, y, z) \in \ZZ^4 \suchthat w + x + y + z \in 2\ZZ\} \\
N &= \ts{
(w, x, y, z) \in \ZZ^4 \suchthat 4\divides (w - x),~ 4\divides (x - y),~ 4\divides ( y - z)
}
.\]

a.
Show that $N$ is a $\ZZ\dash$submodule of $M$ .

b.
Find vectors $u_1 , u_2 , u_3 , u_4 \in \ZZ^4$ and integers $d_1 , d_2 , d_3 , d_4$ such that
\[
\{
u_1 , u_2 , u_3 , u_4 
\} 
&& \text{is a free basis for }M
\\
\{
d_1 u_1,~ d_2 u_2,~ d_3 u_3,~ d_4 u_4 
\}
&& \text{is a free basis for }N
\]

c.
Use the previous part to describe $M/N$ as a direct sum of cyclic $\ZZ\dash$modules.

### Spring 2018 #7 $\work$
Let $R$ be a PID and $M$ be an $R\dash$module. Let $p$ be a prime element of $R$. The module $M$ is called *$\generators{p}\dash$primary* if for every $m \in M$ there exists $k > 0$ such that $p^k m = 0$.

a.
Suppose M is $\generators{p}\dash$primary. Show that if $m \in M$ and $t \in R, ~t \not\in \generators{p}$, then there exists $a \in R$ such that
$atm = m$.

b.
A submodule $S$ of $M$ is said to be *pure* if $S \cap r M = rS$ for all $r \in R$. Show that if $M$ is $\generators{p}\dash$primary, then $S$ is pure if and only if $S \cap p^k M = p^k S$ for all $k \geq 0$.


### Fall 2016 #6 $\work$
Let $R$ be a ring and $f: M\to N$ and $g: N\to M$ be $R\dash$module homomorphisms such that $g\circ f = \id_M$.
Show that $N\cong \im f \oplus \ker g$.

### Spring 2016 #4 $\work$
Let $R$ be a ring with the following commutative diagram of $R\dash$modules, where each row represents a short exact sequence of $R\dash$modules:

\begin{tikzcd}
0 \ar[r] & A \ar[d, "\alpha"] \ar[r, "f"] & B \ar[d, "\beta"] \ar[r, "g"] & C \ar[r] \ar[d, "\gamma"] & 0 \\
0 \ar[r] & A' \ar[r, "f'"] & B'\ar[r, "g'"] & C' \ar[r] & 0 
\end{tikzcd}

Prove that if $\alpha$ and $\gamma$ are isomorphisms then $\beta$ is an isomorphism.

### Spring 2015 #8 $\work$
Let $R$ be a PID and $M$ a finitely generated $R\dash$module.

a.
Prove that there are $R\dash$submodules 
\[
0 = M_0 \subset M_1 \subset \cdots \subset M_n = M
\]
such that for all $0\leq i \leq n-1$, the module $M_{i+1}/M_i$ is cyclic.

b.
Is the integer $n$ in part (a) uniquely determined by $M$? 
Prove your answer.


### Fall 2012 #6 $\work$
Let $R$ be a ring and $M$ an $R\dash$module.
Recall that $M$ is *Noetherian* iff any strictly increasing chain of submodule $M_1 \subsetneq M_2 \subsetneq \cdots$ is finite.
Call a proper submodule $M' \subsetneq M$ *intersection-decomposable* if it can not be written as the intersection of two proper submodules $M' = M_1\intersect M_2$ with $M_i \subsetneq M$.

Prove that for every Noetherian module $M$, any proper submodule $N\subsetneq M$ can be written as a finite intersection $N = N_1 \intersect \cdots \intersect N_k$ of intersection-indecomposable modules.


### Fall 2019 Final #1  $\work$
Let $A$ be an abelian group, and show $A$ is a $\ZZ\dash$module in a unique way.

### Fall 2020 #6 $\work$
Let $R$ be a ring with $1$ and let $M$ be a left \(R\dash\)module.
If $I$ is a left ideal of $R$, define 
\[
IM \da \ts{ \sum_{i=1}^{N < \infty} a_i m_i \st a_i \in I, m_i \in M, n\in \NN}
,\]
i.e. the set of finite sums of of elements of the form $am$ where \( a\in I, m\in M \).

a. Prove that $IM \leq M$ is a submodule.

b. Let $M, N$ be left \(R\dash\)modules, $I$ a nilpotent left ideal of $R$, and $f: M\to N$ an \(R\dash\)module morphism.
Prove that if the induced morphism \( \bar{f}: M/IM \to N/IN \) is surjective, then $f$ is surjective.


## Torsion and the Structure Theorem

### $\star$ Fall 2019 #5 $\done$
Let $R$ be a ring and $M$ an $R\dash$module.

> Recall that the set of torsion elements in M is defined by
\[
\tor(M) = \{m \in M \suchthat \exists r \in R, ~r \neq 0, ~rm = 0\}
.\]

a.
Prove that if $R$ is an integral domain, then $\Tor(M )$ is a submodule of $M$ .

b.
Give an example where $\Tor(M )$ is not a submodule of $M$.

c.
If $R$ has zero-divisors, prove that every non-zero $R\dash$module has non-zero torsion elements.

:::{.solution}


\envlist
:::{.concept}
\envlist

- One-step submodule test.
:::

:::{.proof title="of a"}
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

:::

:::{.proof title="of b"}
Let $R = \ZZ/6\ZZ$ as a $\ZZ/6\ZZ \dash$module, which is not an integral domain as a ring.

Then $[3]_6\actson [2]_6 = [0]_6$ and $[2]_6\actson [3]_6 = [0]_6$, but $[2]_6 + [3]_6 = [5]_6$, where 5 is coprime to 6, and thus $[n]_6\actson [5]_6 = [0] \implies [n]_6 = [0]_6$. So $[5]_6$ is *not* a torsion element.

So the set of torsion elements are not closed under addition, and thus not a submodule.

:::

:::{.proof title="of c"}
Suppose $R$ has zero divisors $a,b \neq 0$ where $ab = 0$.
Then for any $m\in M$, we have $b\actson m \definedas bm \in M$ as well, but then 
$$
a\actson bm = (ab)\actson m = 0\actson m = 0_M
,$$ 
so $m$ is a torsion element for any $m$.

:::

:::

### $\star$ Spring 2019 #5 $\done$
Let $R$ be an integral domain. Recall that if $M$ is an $R\dash$module, the *rank* of $M$ is
defined to be the maximum number of $R\dash$linearly independent elements of $M$ .

a.
Prove that for any $R\dash$module $M$, the rank of $\tor(M )$ is 0.

b.
Prove that the rank of $M$ is equal to the rank of of $M/\tor(M )$.

c.
Suppose that M is a non-principal ideal of $R$.

Prove that $M$ is torsion-free of rank 1 but not free.

:::{.solution}


\envlist
:::{.concept}
\envlist

- Todo
:::

:::{.proof title="of a"}
\envlist

- Suppose toward a contradiction $\tor(M)$ has rank $n \geq 1$.
- Then $\tor(M)$ has a linearly independent generating set $B = \theset{\vector r_1, \cdots, \vector r_n}$, so in particular
\[  
\sum_{i=1}^n s_i \vector r_i = 0 \implies s_i = 0_R \,\forall i
.\]
- Let $\vector r$ be any of of these generating elements.
- Since $\vector r\in \tor(M)$, there exists an $s\in R\setminus 0_R$ such that $s\vector r = 0_M$.
- Then $s\vector r = 0$ with $s\neq 0$, so $\theset{\vector r} \subseteq B$ is *not* a linearly independent set, a contradiction.

:::

:::{.proof title="of b"}
\envlist

- Let $n = \rank M$, and let $\mathcal B = \theset{\vector r_i}_{i=1}^n \subseteq R$ be a generating set.
- Let $\tilde M \definedas M/\tor(M)$ and $\pi: M \to M'$ be the canonical quotient map.

:::{.claim}
\[
\tilde \mcb \definedas \pi(\mathcal B) = \theset{\vector r_i + \tor(M)}
\]
is a basis for $\tilde M$.
:::

Note that the proof follows immediately.

:::

:::{.proof title="of claim: linearly independent"}
\envlist

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


:::

:::{.proof title="of claim: spanning"}
\envlist

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

:::

:::{.proof title="of c"}

> Notation: Let $0_R$ denote $0\in R$ regarded as a ring element, and $\vector 0 \in R$ denoted $0_R$ regarded as a module element (where $R$ is regarded as an $R\dash$module over itself)

:::{.proof title="that $M$ is not free"}
\envlist
- **Claim**: If $I\subseteq R$ is an ideal *and* a free $R\dash$module, then $I$ is principal .

  - Suppose $I$ is free and let $I = \generators{B}$ for some basis, we will show $\abs{B} = 1$>
  
  - Toward a contradiction, suppose $\abs{B} \geq 2$ and let $m_1, m_2\in B$.
  
  - Then  since $R$ is commutative, $m_2 m_1 - m_1 m_2 = 0$ and this yields a linear dependence
  
  - So $B$ has only one element $m$.

  - But then $I = \gens{m} = R_m$ is cyclic as an $R\dash$ module and thus principal as an ideal of $R$. 

  - Now since $M$ was assumed to *not* be principal, $M$ is not free (using the contrapositive of the claim).


:::

:::{.proof title="that $M$ is rank 1"}
\envlist

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


:::


:::


### $\star$ Spring 2020 #6 $\done$
Let $R$ be a ring with unity.

a.
Give a definition for a free module over $R$.

b.
Define what it means for an $R\dash$module to be torsion free.

c.
Prove that if $F$ is a free module, then any short exact sequence of $R\dash$modules of the following form splits:
\[
0 \to N \to M \to F \to 0
.\]

d.
Let $R$ be a PID. 
Show that any finitely generated $R\dash$module $M$ can be expressed as a direct sum of a torsion module and a free module.
  
> You may assume that a finitely generated torsionfree module over a PID is free.



:::{.solution}
Let $R$ be a ring with 1.


:::{.proof title="of a"}
An $R\dash$module $M$ is **free** if any of the following conditions hold:

- $M$ admits an $R\dash$linearly independent spanning set $\theset{\vector b_\alpha}$, so $$m\in M \implies m = \sum_\alpha r_\alpha \vector b_\alpha$$ and $$\sum_\alpha r_\alpha \vector b_\alpha = 0_M \implies r_\alpha = 0_R$$ for all $\alpha$.
- $M$ admits a decomposition $M \cong \bigoplus_{\alpha} R$ as a direct sum of $R\dash$submodules.
- There is a nonempty set $X$ an monomorphism $X\injects M$ of sets such that for every $R\dash$module $N$, every set map $X\to N$ lifts to a unique $R\dash$module morphism $M\to N$, so the following diagram commutes:

\begin{tikzcd}
M \ar[rd, dotted, "\exists ! \tilde f"] & \\
X \ar[u, hook] \ar[r, "f"] & N
\end{tikzcd}

Equivalently,
\[
\Hom_\Set(X, \Forget(N)) \mapsvia{\sim} \Hom_{\rmod}(M, N)
.\]


:::

:::{.proof title="of b"}
\envlist

- Define the annihilator:
\[
\Ann(m) \definedas \theset{r\in R \suchthat r\cdot m = 0_M} \normal R
.\]
  - Note that $mR \cong R/\Ann(m)$.
- Define the torsion submodule:
\[
M_t \definedas \theset{m\in M \suchthat \Ann(m) \neq 0} \leq M
\]
- $M$ is **torsionfree** iff $M_t = 0$ is the trivial submodule.

:::

:::{.proof title="of c"}
\envlist

- Let the following be an SES where $F$ is a free $R\dash$module:
\[
0 \to N \to M \mapsvia{\pi} F \to 0
.\]

- Since $F$ is free, there is a generating set $X = \theset{x_\alpha}$ and a map $\iota:X\injects F$ satisfying the 3rd property from (a).
  - If we construct any map $f: X\to M$, the universal property modules will give a lift $\tilde f: F\to M$

- Identify $X$ with $\iota(X) \subseteq F$. 
- For every $x\in X$, the preimage $\pi\inv(x)$ is nonempty by surjectivity.
  So arbitrarily pick any preimage.
- $\theset{\iota(x_\alpha)} \subseteq F$ and $\pi$ is surjective, so choose fibers $\theset{y_\alpha} \subseteq M$ such that $\pi(y_\alpha) = \iota(x_\alpha)$ and define
\[
f: X&\to M \\
x_\alpha &\mapsto y_\alpha
.\]
- The universal property yields $h: F\to M$:

\begin{tikzcd}
& & & X=\theset{x_\alpha} \ar[dd, hook, "\iota"]\ar[ddl, "f"'] &  \\ \\
0 \ar[r]& N \ar[r] & M\ar[r, "\pi"'] & \ar[l, bend right, dotted ,"\exists ! h"'] F \ar[r] & 0
\end{tikzcd}

- It remains to check that it's a section.
  - Write $f= \sum r_i x_i$, then since both maps are $R\dash$module morphism, by $R\dash$linearity we can write
  \[
  (\pi \circ h)(f) 
  &= (\pi \circ h)\qty{ \sum r_i x_i } \\
  &= \sum r_i (\pi \circ h)(x_i)
  ,\]
  but since $h(x_i) \in \pi\inv(x_i)$, we have $(\pi \circ h)(x_i) = x_i$.
  So this recovers $f$.


:::

:::{.proof title="of c, shorter proof"}
\envlist

- Free implies projective

- Universal property of **projective** objects: for every epimorphism $\pi:M\surjects N$ and every $f:P\to N$ there exists a unique lift $\tilde f: P\to M$:

\begin{tikzcd}
 & P\ar[d, "f"] \ar[dl, dotted, "\exists ! \tilde f"'] \\
M \ar[r, "\pi"] & N
\end{tikzcd}

- Take the identity map:

\begin{tikzcd}
 & & & F\ar[d, "\id_F"]\ar[dl, "\exists ! h"'] & \\
0 \ar[r] & N\ar[r] & M\ar[r] & F \ar[r] & 0
\end{tikzcd}

:::


:::{.proof title="of d"}
\envlist

- Claim: if $R$ is a PID and $M$ is a finitely generated $R\dash$module, then $M \cong M_t \oplus M/M_t$ where $M_t \leq M$ is the torsion submodule.
- Claim: $M/M_t$ is torsionfree, and since a f.g. torsion free module over a PID is free, $M/M_t$ is free.
  - Let $m+M_t \in M/M_t$ and suppose it is torsion, we will show that is must be the zero coset.
  - Then there exists an $r\in R$ such that $r(m + M_t) = M_t$
  - Then $rm + M_t = M_t$, so $rm\in M_t$.
  - By definition of $M_t$, every element is torsion, so there exists some $s\in R$ such $s(rm) = 0_M$.
  - Then $(sr)m = 0_M$ which forces $m\in M_t$
  - Then $m + M_t = M_t$, so $m+ M_t$ is the zero coset.
- There is a SES

\begin{tikzcd}
0 \ar[r] & M_t \ar[r] & M \ar[r] & M/M_t \ar[r] & 0
\end{tikzcd}

  and since $M/M_t$ is free, by (c) this sequence splits and $M \cong M \oplus M/M_t$.

:::





:::

### Spring 2012 #5 $\work$
Let $M$ be a finitely generated module over a PID $R$.

a.
$M_t$ be the set of torsion elements of $M$, and show that $M_t$ is a submodule of $M$.

b.
Show that $M/M_t$ is torsion free.

c.
Prove that $M \cong M_t \oplus F$ where $F$ is a free module.

### Spring 2017 #5 $\work$
Let $R$ be an integral domain and let $M$ be a nonzero torsion $R\dash$module.

a.
Prove that if $M$ is finitely generated then the annihilator in $R$ of $M$ is nonzero.

b.
Give an example of a non-finitely generated torsion $R\dash$module whose annihilator is $(0)$, and justify your answer.

### Fall 2019 Final #3 $\work$
Let $R = k[x]$ for $k$ a field and let $M$ be the $R\dash$module given by
\[
M=\frac{k[x]}{(x-1)^{3}} \oplus \frac{k[x]}{\left(x^{2}+1\right)^{2}} \oplus \frac{k[x]}{(x-1)\left(x^{2}+1\right)^{4}} \oplus \frac{k[x]}{(x+2)\left(x^{2}+1\right)^{2}}
.\]
Describe the elementary divisors and invariant factors of $M$.

### Fall 2019 Final #4 $\work$
Let $I = (2, x)$ be an ideal in $R = \ZZ[x]$, and show that $I$ is not a direct sum of nontrivial cyclic $R\dash$modules.

### Fall 2019 Final #5 $\work$
Let $R$ be a PID. 

a.
Classify irreducible $R\dash$modules up to isomorphism.

b.
Classify indecomposable $R\dash$modules up to isomorphism.

### Fall 2019 Final #6 $\work$
Let $V$ be a finite-dimensional $k\dash$vector space and $T:V\to V$ a non-invertible $k\dash$linear map. Show that there exists a $k\dash$linear map $S:V\to V$ with $T\circ S = 0$ but $S\circ T\neq 0$. 

### Fall 2019 Final #7 $\work$
Let $A\in M_n(\CC)$ with $A^2 = A$. Show that $A$ is similar to a diagonal matrix, and exhibit an explicit diagonal matrix similar to $A$.

### Fall 2019 Final #10 $\work$
Show that the eigenvalues of a Hermitian matrix $A$ are real and that $A = PDP\inv$ where $P$ is an invertible matrix with orthogonal columns.




### Fall 2020 #7 $\work$

Let $A \in \Mat(n\times n, \RR)$ be arbitrary.
Make $\RR^n$ into an $\RR[x]\dash$module by letting $f(x).\vector{v} \da f(A)(\vector{v})$ for $f(\vector{v})\in \RR[x]$ and $\vector{v} \in \RR^n$.
Suppose that this induces the following direct sum decomposition:
\[
\RR^n \cong
{ \RR[x] \over \gens{ (x-1)^3 } }
\oplus
{ \RR[x] \over \gens{ (x^2+1)^2 } }
\oplus
{ \RR[x] \over \gens{ (x-1)(x^2-1)(x^2+1)^4 } }
\oplus
{ \RR[x] \over \gens{ (x+2)(x^2+1)^2 } }
.\]

a. Determine the elementary divisors and invariant factors of $A$.

b. Determine the minimal polynomial of $A$.

c. Determine the characteristic polynomial of $A$.

