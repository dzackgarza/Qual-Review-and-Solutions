# Groups: Sylow Theory

## Fall 2019 #1 $\done$
Let $G$ be a finite group with $n$ distinct conjugacy classes.
Let $g_1 \cdots g_n$ be representatives of the conjugacy classes of $G$.
Prove that if $g_i g_j = g_j g_i$ for all $i, j$ then $G$ is abelian.

:::{.concept}
\envlist

- $Z(g) = G \iff g\in Z(G)$, i.e. if the centralizer of $g$ is the whole group, $g$ is central.

- If $H\leq G$ is a *proper* subgroup, then $\Union_{g\in G} hGh\inv$ is again a proper subgroup (subset?)
  I.e. $G$ is not a union of conjugates of any proper subgroup.
- So if $G$ *is* a union of conjugates of $H$, then $H$ must not be proper, i.e. $H= G$.
:::

:::{.solution}
\envlist

- We have $g_j \subseteq Z(g_k)$ for all $k$ by assumption.
- If we can show $Z(g_k) = G$ for all $k$, then $g_k \in Z(G)$ for all $k$.
  - Then each conjugacy class is size 1, and since $G = \disjoint_{i=1}^n [g_i] = \disjoint_{i=1}^n \ts{g_i}$, every $g\in G$ is some $g_i$.
  So $G \subseteq Z(G)$, forcing $G$ to be abelian.
- If we can show $G \subseteq \Union_{h\in H} h Z(g_k) h\inv$ for some $k$, this forces $Z(g_k) = G$ and $g_k \in Z(G)$.
  - If we can do this for all $k$, we're done!
- Since $g\in G$ is in some conjugacy class, write $g=hg_j h\inv$ for some $h\in G$ and some $1\leq j\leq n$.
- Now use $g_j \in Z(g_k)$ for all $k$:
\[
g\in G &\implies g = hg_j h\inv && \text{for some } h\in H \\
g_j \in Z(g_k) \forall k &\implies g\in hZ(g_k)h\inv &&\text{for some }h, \, \forall 1\leq k \leq n \\
&\implies g\in \Union_{h\in G} h Z(g_k) h\inv
&&\forall 1\leq k \leq n \\
.\]
  - Note that it's necessary to get rid of the $h$ dependence, since now now every $g\in G$ is in $\Union_{h\in G} hZ(g_k)h\inv$.
- Now
\[
G \subseteq \Union_{h\in G} hZ(g_k) \subseteq G \,\,\forall k \implies Z(g_k) = G\,\, \forall k
,\]
and we're done.



:::

## Fall 2019 Midterm #2 $\work$
Let $G$ be a finite group and let $P$ be a sylow $p\dash$subgroup for $p$ prime. Show that $N(N(P)) = N(P)$ where $N$ is the normalizer in $G$.

## Fall 2013 #2 $\work$
Let $G$ be a group of order 30.


a.
Show that $G$ has a subgroup of order 15.

b.
Show that every group of order 15 is cyclic.

c.
Show that $G$ is isomorphic to some semidirect product $\ZZ_{15} \semidirect \ZZ_2$.

d.
Exhibit three nonisomorphic groups of order 30 and prove that they are not isomorphic.
You are not required to use your answer to (c).

## Spring 2014 #2 $\work$
Let $G\subset S_9$ be a Sylow-3 subgroup of the symmetric group on 9 letters.

a.
Show that $G$ contains a subgroup $H$ isomorphic to $\ZZ_3 \cross \ZZ_3 \cross \ZZ_3$ by exhibiting an appropriate set of cycles.

b.
Show that $H$ is normal in $G$.

c.
Give generators and relations for $G$ as an abstract group, such that all generators have order 3.
Also exhibit elements of $S_9$ in cycle notation corresponding to these generators.

d.
Without appealing to the previous parts of the problem, show that $G$ contains an element of order 9.

## Fall 2014 #2 $\work$
Let $G$ be a group of order 96.

a.
Show that $G$ has either one or three 2-Sylow subgroups.

b.
Show that either $G$ has a normal subgroup of order 32, or a normal subgroup of order 16.

## Spring 2016 #3 $\work$

a.
State the three Sylow theorems.

b.
Prove that any group of order 1225 is abelian.

c.
Write down exactly one representative in each isomorphism class of abelian groups of order 1225.

## Spring 2017 #2 $\work$

a.
How many isomorphism classes of abelian groups of order 56 are there?
Give a representative for one of each class.

b.
Prove that if $G$ is a group of order 56, then either the Sylow-2 subgroup or the Sylow-7 subgroup is normal.

c.
Give two non-isomorphic groups of order 56 where the Sylow-7 subgroup is normal and the Sylow-2 subgroup is *not* normal.
Justify that these two groups are not isomorphic.

## Fall 2017 #2 $\work$

a.
Classify the abelian groups of order 36.

  > For the rest of the problem, assume that $G$ is a non-abelian group of order 36. 
  > You may assume that the only subgroup of order 12 in $S_4$ is $A_4$ and that $A_4$ has no subgroup of order 6.

b.
Prove that if the 2-Sylow subgroup of $G$ is normal, $G$ has a normal subgroup $N$ such that $G/N$ is isomorphic to $A_4$.

c.
Show that if $G$ has a normal subgroup $N$ such that $G/N$ is isomorphic to $A_4$ and a subgroup $H$ isomorphic to $A_4$ it must be the direct product of $N$ and $H$.

d.
Show that the dihedral group of order 36 is a non-abelian group of order 36 whose Sylow-2 subgroup is not normal.

## Fall 2012 #2 $\work$
Let $G$ be a group of order 30.

a.
Show that $G$ contains normal subgroups of orders 3, 5, and 15.

b.
Give all possible presentations and relations for $G$.

c.
Determine how many groups of order 30 there are up to isomorphism.

## Fall 2018 #1 $\done$ 
Let $G$ be a finite group whose order is divisible by a prime number $p$.
Let $P$ be a normal $p\dash$subgroup of $G$
(so $\abs P = p^c$ for some $c$).

a.
Show that $P$ is contained in every Sylow $p\dash$subgroup of $G$.

b.
Let $M$ be a maximal proper subgroup of $G$. Show that either $P \subseteq M$ or $|G/M | = p^b$ for some $b \leq c$.

:::{.concept}
\envlist

- Sylow 2: All Sylow $p\dash$subgroups are conjugate.
- $\abs{HK} = \abs{H} \abs{K} / \abs{H\intersect K}$.
- Lagrange's Theorem: $H\leq G \implies \abs{H} \divides \abs{G}$

:::

:::{.solution}
\envlist

:::{.proof title="of a"}
\envlist

- Every $p\dash$subgroup is contained in some Sylow $p\dash$subgroup, so $P \subseteq S_p^i$ for some $S_p^i \in \mathrm{Syl}_p(G)$.

- $P \normal G \iff gPg\inv = P$ for all $g\in G$.

- Let $S_p^j$ be any other Sylow $p\dash$subgroup, 
- Since Sylow $p\dash$subgroups are all conjugate $gS_p^i g\inv = S_p^j$ for *some* $g\in G$.

- Then 
\[
P = gPg\inv \subseteq gS_p^i g\inv = S_p^j
.\]

:::

:::{.proof title="of b"}
\envlist

- If $P$ is not contained in $M$, then $M < MP$ is a proper subgroup
- By maximality of $M$, $MP = G$
- Note that $M\intersect P \leq P$ and $\abs{P} = p^c$ implies $\abs{M\intersect P} = p^a$ for some $a\leq c$ by Lagrange
- Then write
  \[
  G = MP
  &\iff \abs{G} = \frac{\abs{M} \abs{P}}{\abs{M\intersect P}} \\ \\
  &\iff { \abs{G} \over \abs{M}} = {\abs{P}  \over \abs{M\intersect P}} = {p^c \over p^a} = p^{c-a} \definedas p^b
  \]

  where $a\leq c \implies 0 \leq c-b \leq c$ so $0\leq b \leq c$.

:::

:::

## Fall 2019 #2  $\done$
Let $G$ be a group of order 105 and let $P, Q, R$ be Sylow 3, 5, 7 subgroups respectively.

a.
Prove that at least one of $Q$ and $R$ is normal in $G$.

b.
Prove that $G$ has a cyclic subgroup of order 35.

c.
Prove that both $Q$ and $R$ are normal in $G$.

d.
Prove that if $P$ is normal in $G$ then $G$ is cyclic.

:::{.concept}
\envlist

- The $pqr$ theorem.
- Sylow 3: $\abs{G} = p^n m$ implies $n_p \divides m$ and $n_p \cong 1 \mod p$.

- **Theorem**: If $H, K \leq G$ and any of the following conditions hold, $HK$ is a subgroup:
  - $H\normal G$ (wlog)
  - $[H, K] = 1$
  - $H \leq N_G(K)$ 

- **Theorem**: For a positive integer $n$, all groups of order $n$ are cyclic $\iff n$ is
squarefree and, for each pair of distinct primes $p$ and $q$ dividing $n$, $q - 1 \neq 0 \mod p$.

- **Theorem:** 
\[
A_i\normal G, \quad G = A_1 \cdots A_k,\quad A_k \intersect \prod_{i\neq k} A_i = \emptyset \implies G = \prod A_i
.\]

- The intersection of subgroups is a again a subgroup.
- Any subgroups of coprime order intersect trivially?

:::

:::{.solution}
\envlist

:::{.proof title="of 1"}
\envlist

- We have 

- $n_3 \divides 5\cdot 7, \quad n_3 \cong 1 \mod 3 \implies n_3 \in \theset{1, 5, 7, 35} \setminus \theset{5, 35}$
- $n_5 \divides 3\cdot 7, \quad n_5 \cong 1 \mod 5 \implies n_5 \in \theset{1, 3, 7, 21}\setminus \theset{3, 7}$
- $n_7 \divides 3\cdot 5, \quad n_7 \cong 1 \mod 7 \implies n_7 \in \theset{1, 3, 5, 15}\setminus\theset{3, 5}$

- Thus
\[
n_3 \in \theset{1, 7} \quad n_5 \in \theset{1, 21} \quad n_7 \in \theset{1, 15}
.\]

- Toward a contradiction, if $n_5\neq 1$ and $n_7 \neq 1$, then 
\[
\abs{\syl(5) \union \syl(7)} = (5-1)n_5 + (7-1)n_7 + 1 
&= 4(21) + 6(15) = 174 > 105 \text{ elements}
\]
  using the fact that Sylow $p\dash$subgroups for distinct primes $p$ intersect trivially (?).

:::

:::{.proof title="of 2"}
\envlist
- By (a), either $Q$ or $R$ is normal.
- Thus $QR \leq G$ is a subgroup, and it has order $\abs{Q} \cdot \abs{R} = 5\cdot 7 = 35$.
- By the $pqr$ theorem, since $5$ does not divide $7-1=6$, $QR$ is cyclic.

:::

\todo[inline]{Part (b) not finished!}

:::{.proof title="of 3"}
\envlist

- We want to show $Q, R\normal G$, so we proceed by showing $\textbf{not }\qty{n_5 = 21 \text{ or } n_7 = 15}$, which is equivalent to $\qty{n_5 = 1 \text{ and } n_7 = 1}$ by the previous restrictions.

- Note that we can write
\[
G = \theset{\text{elements of order } n} \disjoint \theset{\text{elements of order not } n}
.\]
  for any $n$, so we count for $n=5, 7$:

  - Elements in $QR$ of order **not** equal to 5: $\abs{QR - Q\theset{\id} + \theset{\id}} = 35 - 5 + 1 = 31$
  - Elements in $QR$ of order **not** equal to 7: $\abs{QR - \theset{\id}R + \theset{\id}} = 35 - 7 + 1 = 29$

- Since $QR \leq G$, we have

  - Elements in $G$ of order **not** equal to 5 $\geq 31$.
  - Elements in $G$ of order **not** equal to 7 $\geq 29$.

- Now both cases lead to contradictions:

  - $n_5 = 21$:
\[
\abs{G}  &= \abs{\theset{\text{elements of order } 5} \disjoint \theset{\text{elements of order not } 5}} \\
&\geq n_5(5-1) + 31 = 21(4) + 31 = 115 > 105 = \abs{G}
.\]

  - $n_7 = 15$:
\[
\abs{G}  &= \abs{\theset{\text{elements of order } 7} \disjoint \theset{\text{elements of order not } 7}} \\
&\geq n_7(7-1) + 29 = 15(6) + 29 = 119 > 105 = \abs{G}
.\]

:::

:::{.proof title="of 4"}
Suppose $P$ is normal and recall $\abs{P} = 3, \abs{Q} = 5, \abs{R} = 7$.

- $P\intersect QR = \theset{e}$ since $(3, 35) = 1$ 
- $R\intersect PQ = \theset{e}$ since $(5, 21) = 1$ 
- $Q\intersect RP = \theset{e}$ since $(7, 15) = 1$ 

We also have $PQR = G$ since $\abs{PQR} = \abs{G}$ (???).

We thus have an internal direct product 
\[
G \cong P\cross Q \cross R \cong \ZZ_3 \cross \ZZ_5 \cross \ZZ_7 \cong \ZZ_{105}
.\]
by the Chinese Remainder Theorem, which is cyclic.

:::

:::

## Spring 2021 #3 $\work$

a. Show that every group of order $p^2$ with $p$ prime is abelian.

b. State the 3 Sylow theorems.

c. Show that any group of order $4225 = 5^2 13^2$ is abelian.

d. Write down one representative from each isomorphism class of abelian groups of order 4225.

## Fall 2020 #1 $\work$

a. Using Sylow theory, show that every group of order $2p$ where $p$ is prime is not simple.

b. Classify all groups of order $2p$ and justify your answer.
  For the nonabelian group(s), give a presentation by generators and relations.

## Fall 2020 #2 $\work$

Let $G$ be a group of order 60 whose Sylow 3-subgroup is normal.

a. Prove that $G$ is solvable.

b. Prove that the Sylow 5-subgroup is also normal.

