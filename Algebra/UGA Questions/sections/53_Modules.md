# Modules

## General Questions

### Fall 2019 Final #2 
Consider the $\ZZ\dash$submodule $N$ of $\ZZ^3$ spanned by $f_1 = [-1, 0, 1], f_2 = [2,-3,1], f_3 = [0, 3, 1], f_4 = [3,1,5]$. Find a basis for $N$ and describe $\ZZ^3/N$.

### Spring 2018 #6.

Let
$$
M = \{(w, x, y, z) \in \ZZ^4 \suchthat w + x + y + z \in 2\ZZ\}
,$$

and

$$
N = \{(w, x, y, z) \in \ZZ^4 \suchthat 4\divides (w - x),~ 4\divides (x - y),~ 4\divides ( y - z)\}
.$$

a. Show that $N$ is a $\ZZ\dash$submodule of $M$ .

b. Find vectors $u_1 , u_2 , u_3 , u_4 \in \ZZ^4$ and integers $d_1 , d_2 , d_3 , d_4$ such that
$$
\{u_1 , u_2 , u_3 , u_4 \}
$$
is a free basis for $M$, and
$$
\{d_1 u_1,~ d_2 u_2,~ d_3 u_3,~ d_4 u_4 \}
$$
is a free basis for $N$ .

c. Use the previous part to describe $M/N$ as a direct sum of cyclic $\ZZ\dash$modules.

### Fall 2018 #6 $\bowtie$

Let $R$ be a commutative ring, and let $M$ be an $R\dash$module. 
An $R\dash$submodule $N$ of $M$ is maximal if there is no $R\dash$module $P$ with $N \subsetneq P \subsetneq M$.

a. Show that an $R\dash$submodule $N$ of $M$ is maximal $\iff M /N$ is a simple $R\dash$module: i.e., $M /N$ is nonzero and has no proper, nonzero $R\dash$submodules.

b. Let $M$ be a $\ZZ\dash$module. Show that a $\ZZ\dash$submodule $N$ of $M$ is maximal $\iff \#M /N$ is a prime number.

c. Let $M$ be the $\ZZ\dash$module of all roots of unity in $\CC$ under multiplication.
Show that there is no maximal $\ZZ\dash$submodule of $M$.

:::{.solution}
a

By the correspondence theorem, submodules of $M/N$ biject with submodules $A$ of $M$ containing $N$.

So 

- $M$ is maximal:

- $\iff$ no such (proper, nontrivial) submodule $A$ exists 

- $\iff$ there are no (proper, nontrivial) submodules of $M/N$ 

- $\iff M/N$ is simple.

b

Identify $\ZZ\dash$modules with abelian groups, then by (a), $N$ is maximal $\iff$ $M/N$ is simple $\iff$ $M/N$ has no nontrivial proper subgroups.

By Cauchy's theorem, if $\abs{M/N} = ab$ is a composite number, then $a\divides ab \implies$ there is an element (and thus a subgroup) of order $a$.
In this case, $M/N$ contains a nontrivial proper cyclic subgroup, so $M/N$ is not simple.
So $\abs{M/N}$ can not be composite, and therefore must be prime.

c

Let $G = \theset{x \in \CC \suchthat x^n=1 \text{ for some }n\in \NN}$, and suppose $H < G$ is a proper subgroup.

Then there must be a prime $p$ such that the $\zeta_{p^k} \not \in H$ for all $k$ greater than some constant $m$ -- otherwise, we can use the fact that if $\zeta_{p^k} \in H$ then $\zeta_{p^\ell} \in H$ for all $\ell \leq k$, and if $\zeta_{p^k} \in H$ for all $p$ and all $k$ then $H = G$.

But this means there are infinitely many elements in $G\setminus H$, and so $\infty = [G: H] = \abs{G/H}$ is not a prime. 
Thus by (b), $H$ can not be maximal, a contradiction.


:::

### Spring 2018 #7.

Let $R$ be a PID and $M$ be an $R\dash$module. Let $p$ be a prime element of $R$. The module $M$ is called *$\generators{p}\dash$primary* if for every $m \in M$ there exists $k > 0$ such that $p^k m = 0$.

a. Suppose M is $\generators{p}\dash$primary. Show that if $m \in M$ and $t \in R, ~t \not\in \generators{p}$, then there exists $a \in R$ such that
$atm = m$.

b. A submodule $S$ of $M$ is said to be *pure* if $S \cap r M = rS$ for all $r \in R$. Show that if $M$ is $\generators{p}\dash$primary, then $S$ is pure if and only if $S \cap p^k M = p^k S$ for all $k \geq 0$.


### Fall 2016 #6
Let $R$ be a ring and $f: M\to N$ and $g: N\to M$ be $R\dash$module homomorphisms such that $g\circ f = \id_M$.
Show that $N\cong \im f \oplus \ker g$.


### Spring 2016 #4

Let $R$ be a ring with the following commutative diagram of $R\dash$modules, where each row represents a short exact sequence of $R\dash$modules:

\begin{center}
\begin{tikzcd}
0 \ar[r] & A \ar[d, "\alpha"] \ar[r, "f"] & B \ar[d, "\beta"] \ar[r, "g"] & C \ar[r] \ar[d, "\gamma"] & 0 \\
0 \ar[r] & A' \ar[r, "f'"] & B'\ar[r, "g'"] & C' \ar[r] & 0 
\end{tikzcd}
\end{center}

Prove that if $\alpha$ and $\gamma$ are isomorphisms then $\beta$ is an isomorphism.


### Spring 2015 #8
Let $R$ be a PID and $M$ a finitely generated $R\dash$module.

a. Prove that there are $R\dash$submodules 
  \[
  0 = M_0 \subset M_1 \subset \cdots \subset M_n = M
  \]
  such that for all $0\leq i \leq n-1$, the module $M_{i+1}/M_i$ is cyclic.

b. Is the integer $n$ in part (a) uniquely determined by $M$? 
  Prove your answer.



### Fall 2012 #6

Let $R$ be a ring and $M$ an $R\dash$module.
Recall that $M$ is *Noetherian* iff any strictly increasing chain of submodule $M_1 \subsetneq M_2 \subsetneq \cdots$ is finite.
Call a proper submodule $M' \subsetneq M$ *intersection-decomposable* if it can not be written as the intersection of two proper submodules $M' = M_1\intersect M_2$ with $M_i \subsetneq M$.

Prove that for every Noetherian module $M$, any proper submodule $N\subsetneq M$ can be written as a finite intersection $N = N_1 \intersect \cdots \intersect N_k$ of intersection-indecomposable modules.


### Fall 2019 Final #1 
Let $A$ be an abelian group, and show $A$ is a $\ZZ\dash$module in a unique way.


## Torsion and the Structure Theorem

### $\star$ Fall 2019 #5 $\bowtie$

Let $R$ be a ring and $M$ an $R\dash$module.

> Recall that the set of torsion elements in M is defined by
$$
\tor(m) = \{m \in M \suchthat \exists r \in R, ~r \neq 0, ~rm = 0\}
.$$

a. Prove that if $R$ is an integral domain, then $\Tor(M )$ is a submodule of $M$ .

b. Give an example where $\Tor(M )$ is not a submodule of $M$.

c. If $R$ has zero-divisors, prove that every non-zero $R\dash$module has non-zero torsion elements.

:::{.solution}

> One-step submodule test.

#### a

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

#### b

Let $R = \ZZ/6\ZZ$ as a $\ZZ/6\ZZ \dash$module, which is not an integral domain as a ring.

Then $[3]_6\actson [2]_6 = [0]_6$ and $[2]_6\actson [3]_6 = [0]_6$, but $[2]_6 + [3]_6 = [5]_6$, where 5 is coprime to 6, and thus $[n]_6\actson [5]_6 = [0] \implies [n]_6 = [0]_6$. So $[5]_6$ is *not* a torsion element.

So the set of torsion elements are not closed under addition, and thus not a submodule.

#### c

Suppose $R$ has zero divisors $a,b \neq 0$ where $ab = 0$.
Then for any $m\in M$, we have $b\actson m \definedas bm \in M$ as well, but then 
$$
a\actson bm = (ab)\actson m = 0\actson m = 0_M
,$$ 
so $m$ is a torsion element for any $m$.


:::
