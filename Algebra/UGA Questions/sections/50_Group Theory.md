# Group Theory

## Spring 2020 #1

a. Show that any group of order 2020 is solvable.

b. Give (without proof) a classification of all abelian groups of order 2020.

c. Describe one nonabelian group of order 2020.

## Spring 2020 #2

Let $H$ be a normal subgroup of a finite group $G$ where the order of $H$ and the index of $H$ in $G$ are relatively prime.
Prove that no other subgroup of $G$ has the same order as $H$.

## Fall 2019 #1 $\bowtie$ 

Let $G$ be a finite group with $n$ distinct conjugacy classes.
Let $g_1 \cdots g_n$ be representatives of the conjugacy classes of $G$.

Prove that if $g_i g_j = g_j g_i$ for all $i, j$ then $G$ is abelian.

:::{.solution}

Concepts used:

- Centralizer: 
  \[
  C_G(h) = Z(h) = \theset{g\in G \suchthat [g,h] = 1}
  \quad\text{Centralizer}
\]
- Class equation: 
  \[
  \abs{G} = \sum_{\substack{\text{One $h$ from each } \\ \text{ conjugacy class}}} \frac{\abs{G}}{\abs{Z(h)}}
  \]
- Notation:
  \[
  h^g &= ghg\inv \\
  h^G &= \theset{ h^g \suchthat g\in G} \quad\text{Conjugacy Class}\\
  H^g &= \theset{h^g \suchthat h\in H} \\
  N_G(H) &= \theset{g\in G \suchthat H^g = H} \supseteq H \quad\text{Normalizer}
  .\]

**Solution**:

**Claim 1**: $\abs{h^G} = [G: Z(h)]$

**Claim 2**: $\abs{\theset{H^g \suchthat g\in G}} = [G: N_G(H)]$

- *Proof:* Let $G\actson \theset{H \suchthat H \leq G}$ by $H \mapsto gHg\inv$.
- Then the $\mathcal O_H$ is the set of conjugate subgroups, $\mathrm{Stab}(H) = N_G(H)$.
- So Orbit-Stabilizer says $\mathcal O_h \cong G/\mathrm{Stab}(H)$; then just take sizes.

**Claim 3:** $\union_{g\in G} H^g = \union_{g\in G} gHg\inv \subsetneq G$ for any proper $H \leq G$.

- *Proof:* By theorem 2, since each coset is of size $\abs{H}$, which only intersect at the identity, and there are exactly $[G: N_G(H)]$ of them
  \[
  \abs{\union_{g\in G} H^g} 
  &= \qty{ \abs{H} - 1} [G: N_G(H)] + 1\\
  &= \abs{H} [G: N_G(H)]  - [G:N_G(H)] + 1\\
  &= \abs{G} \frac{\abs G}{\abs{N_G(H)}} - \frac{\abs G}{\abs{N_G(H)}} + 1 \\
  &\leq \abs{H} \frac{\abs G}{\abs{H}} - \frac{\abs G}{\abs{H}} + 1 \\
  &= \abs{G} - ([G: H] - 1) \\
  &< \abs{G} 
  ,\]
  where we use the fact that $H \subseteq N_G(H) \implies \abs{H} \leq \abs{N_G(H)} \implies \frac{1}{\abs{N_G(H)}} \leq \frac{1}{\abs{H}}$, and since $H < G$ is proper, $[G:H] \geq 2$.

- Since $[g_i, g_j] = 1$, we have $g_i \in Z(g_j)$ for every $i, j$.

- Then
  \[
  g\in G 
  &\implies g = g_i^h \quad \text{ for some } h \\
  &\implies g \in Z(g_\mathbf{j})^h \quad\text{for every } j \text{ since }g_i \in Z(g_j) ~\forall j \\
  &\implies g \in \union_{h\in G} Z(g_j)^h \quad\text{for every } j\\
  &\implies G \subseteq \union_{h\in G} Z(g_j)^h \quad\text{for every } j
  ,\]

  which by Theorem 3, if $Z(g_j) < G$ were proper, then the RHS is properly contained in $G$. 
- So it must be the case that that $Z(g_j)$ is not proper and thus equal to $G$ for every $j$.

- But $Z(g_i) = G \iff g_i \in Z(G)$, and so each conjugacy class is size one.
- So for every $g\in G$, we have $g = g_j$ for some $j$, and thus $g = g_j \in Z(g_j) = Z(G)$, so $g$ is central.
- Then $G\subseteq Z(G)$ and $G$ is abelian.

:::

## Fall 2019 #2  $\bowtie$

Let $G$ be a group of order 105 and let $P, Q, R$ be Sylow 3, 5, 7 subgroups respectively.

(a) Prove that at least one of $Q$ and $R$ is normal in $G$.

(b) Prove that $G$ has a cyclic subgroup of order 35.

(c) Prove that both $Q$ and $R$ are normal in $G$.

(d) Prove that if $P$ is normal in $G$ then $G$ is cyclic.

:::{.solution}
Relevant Concepts:

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

**Solution**

### a
We have 

- $n_3 \divides 5\cdot 7, \quad n_3 \cong 1 \mod 3 \implies n_3 \in \theset{1, 5, 7, 35} \setminus \theset{5, 35}$
- $n_5 \divides 3\cdot 7, \quad n_5 \cong 1 \mod 5 \implies n_5 \in \theset{1, 3, 7, 21}\setminus \theset{3, 7}$
- $n_7 \divides 3\cdot 5, \quad n_7 \cong 1 \mod 7 \implies n_7 \in \theset{1, 3, 5, 15}\setminus\theset{3, 5}$

Thus
\[
n_3 \in \theset{1, 7} \quad n_5 \in \theset{1, 21} \quad n_7 \in \theset{1, 15}
.\]

Toward a contradiction, if $n_5\neq 1$ and $n_7 \neq 1$, then 
\[
\abs{\syl(5) \union \syl(7)} = (5-1)n_5 + (7-1)n_7 + 1 
&= 4(21) + 6(15) = 174 > 105 \text{ elements}
\]
using the fact that Sylow $p\dash$subgroups for distinct primes $p$ intersect trivially (?).

### b 
\todo[inline]{Not finished!}

By (a), either $Q$ or $R$ is normal.
Thus $QR \leq G$ is a subgroup, and it has order $\abs{Q} \cdot \abs{R} = 5\cdot 7 = 35$.

By the $pqr$ theorem, since $5$ does not divide $7-1=6$, $QR$ is cyclic.

### c
We want to show $Q, R\normal G$, so we proceed by showing $\textbf{not }\qty{n_5 = 21 \text{ or } n_7 = 15}$, which is equivalent to $\qty{n_5 = 1 \text{ and } n_7 = 1}$ by the previous restrictions.

Note that we can write
\[
G = \theset{\text{elements of order } n} \disjoint \theset{\text{elements of order not } n}
.\]
for any $n$, so we count for $n=5, 7$:

- Elements in $QR$ of order **not** equal to 5: $\abs{QR - Q\theset{\id} + \theset{\id}} = 35 - 5 + 1 = 31$
- Elements in $QR$ of order **not** equal to 7: $\abs{QR - \theset{\id}R + \theset{\id}} = 35 - 7 + 1 = 29$

Since $QR \leq G$, we have

- Elements in $G$ of order **not** equal to 5 $\geq 31$.
- Elements in $G$ of order **not** equal to 7 $\geq 29$.

Now both cases lead to contradictions:

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

### d

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

## Spring 2019 #3 $\bowtie$

How many isomorphism classes are there of groups of order 45?

Describe a representative from each class.

:::{.solution}
Concepts used:

- Sylow theorems:
- $n_p \cong 1 \mod p$
- $n_p \divides m$.

**Solution**

It turns out that $n_3 = 1$ and $n_5 = 1$, so $G \cong S_3 \cross S_5$ since both subgroups are normal.

There is only one possibility for $S_5$, namely $S_5\cong \ZZ/(5)$.

There are two possibilities for $S_3$, namely $S_3 \cong \ZZ/(3^2)$ and $\ZZ/(3)^2$.

Thus

- $G \cong \ZZ/(9) \cross \ZZ/(5)$, or
- $G \cong \ZZ/(3)^2 \cross \ZZ/(5)$.

\todo[inline]{Revisit, seems short.}
:::

## Spring 2019 #4 $\bowtie$

For a finite group $G$, let $c(G)$ denote the number of conjugacy classes of $G$.

(a) Prove that if two elements of $G$ are chosen uniformly at random,then the probability they commute is precisely
$$
\frac{c(G)}{\abs G}
.$$

(b) State the class equation for a finite group.

(c) Using the class equation (or otherwise) show that the probability in part (a) is at most $$
\frac 1 2 + \frac 1 {2[G : Z(G)]}
.$$

> Here, as usual, $Z(G)$ denotes the center of $G$.

:::{.solution}

Concepts Used:

- Notation: $X/G$ is the set of $G\dash$orbits
- Notation: $X^g = \theset{x\in x\suchthat g\cdot x = x}$
- Burnside's formula: $\abs G \abs{X/G} = \sum \abs {X^g}$.

**Solution**

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


:::



## Fall 2018 #1 $\bowtie$

Let $G$ be a finite group whose order is divisible by a prime number $p$.
Let $P$ be a normal $p\dash$subgroup of $G$
(so $\abs P = p^c$ for some $c$).

(a) Show that $P$ is contained in every Sylow $p\dash$subgroup of $G$.

(b) Let $M$ be a maximal proper subgroup of $G$. Show that either $P \subseteq M$ or $|G/M | = p^b$ for some $b \leq c$.

:::{.solution}
Concepts Used:

- Sylow 2: All Sylow $p\dash$subgroups are conjugate.
- $\abs{HK} = \abs{H} \abs{K} / \abs{H\intersect K}$.
- Lagrange's Theorem: $H\leq G \implies \abs{H} \divides \abs{G}$

**Solution**

### a

- Every $p\dash$subgroup is contained in some Sylow $p\dash$subgroup, so $P \subseteq S_p^i$ for some $S_p^i \in \mathrm{Syl}_p(G)$.

- $P \normal G \iff gPg\inv = P$ for all $g\in G$.

- Let $S_p^j$ be any other Sylow $p\dash$subgroup, 
- Since Sylow $p\dash$subgroups are all conjugate $gS_p^i g\inv = S_p^j$ for *some* $g\in G$.

- Then 
\[
P = gPg\inv \subseteq gS_p^i g\inv = S_p^j
.\]

### b

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



## Fall 2018 #2 $\bowtie$

(a) Suppose the group $G$ acts on the set $X$ . Show that the stabilizers of elements in the same orbit are conjugate.

(b) Let $G$ be a finite group and let $H$ be a proper subgroup. Show that the union of the conjugates of $H$ is strictly smaller than $G$, i.e.
$$
\union_{g\in G} gHg\inv \subsetneq G
$$

(c) Suppose $G$ is a finite group acting transitively on a set $S$ with at least 2 elements. Show that there is an element of $G$ with no fixed points in $S$.

:::{.solution}
Concepts used:

- Orbit: $G\cdot x \definedas \theset{g\cdot x \suchthat g\in G} \subseteq X$
- Stabilizer: $G_x \definedas \theset{g\in G\suchthat g\cdot x = x} \leq G$
- Orbit-Stabilizer: $G\cdot x \simeq G/G_x$.
- $abc\in H \iff b\in a\inv H c\inv$
- Set of orbits for $G\actson X$, notated $X/G$.
- Set of fixed points for $G\actson X$, notated $X^g$.
- Burnside's Lemma: $\abs{X/G} \cdot \abs{G} = \sum_{g\in G} \abs{X^g}$ 
  - Number of orbits equals average number of fixed points.

**Solution**

### a

- Fix $x$ and let $y\in G_x$ be another element in the orbit of $x$.
- Then there exists a $g\in G$ such that $g\cdot x = y$, so $x = g\inv \cdot y$
- Then
\[
h \in G\cdot x 
&\iff h\cdot x = x \qtext{by being in the stabilizer} \\
&\iff h\cdot (g\inv \cdot y) = g\inv \cdot y \qtext{using that $x, y$ are in the same orbit} \\
&\iff (g h g\inv) \cdot y = y \\
&\iff ghg\inv \in G_y \qtext{by the defn of the stabilizer}\\
&\iff h\in g\inv G_y g
,\]

so every $h\in G\cdot x$ is conjugate to some element in $G_y$.

### b

Let $G$ act on its subgroups by conjugation, 

- The orbit $G\cdot H$ is the set of all subgroups conjugate to $H$, and

- The stabilizer of $H$ is $G_H = N_G(H)$.

- By orbit-stabilizer,
\[
G\cdot H = [G: G_H] = [G: N_G(H)]
.\]

- Since $\abs H = n$, and all of its conjugate also have order $n$.

- Note that 
\[
H\leq N_G(H) \implies \abs{H} \leq \abs{N_G(H)} \implies {1\over \abs{N_G(H)}} \leq {1\over \abs{H}}
,\]

- Now *strictly* bound the size of the union by overcounting their intersections at the identity:
\[
\abs{\union_{g\in G}gHg\inv} 
&< (\text{Number of Conjugates of } H) \cdot (\text{Size of each conjugate}) \\ 
&\qquad \qquad\textit{strictly overcounts since they intersect in at least the identity} \\
& = [G: N_G(H)] \abs{H} \\
&= {\abs{G} \over \abs{N_G(H)}} \abs{H} \qtext{since $G$ is finite} \\
&\leq {\abs G \over \abs H} \abs H \\
&= \abs{G}
.\]

### c

- Let $G\actson X$ transitively where $\abs{X} \geq 2$
- An action is transitive iff there is only one orbit, so $\abs{X/G} = 1$.
- Apply Burnside's Lemma
\[
1 = \abs{X/G} = \frac{1}{\abs G} \sum_{g\in G} \abs{X^g} \implies \abs{G} = \sum_{g\in G} \abs{X^g}
\]
- Note that $X^e = X$, since the identity must fix every element, so $\abs{X^e} \geq 2$.
- Not *every* other term in the sum can be greater than 1, otherwise the RHS is greater than the size of $G$
- Thus we must have $\abs{X^g} = 0$ for some $g\in G$, i.e. $g$ has no fixed points in $X$.


:::



## Spring 2018 #1 $\bowtie$

(a) Use the Class Equation (equivalently, the conjugation action of a group on itself) to prove that any $p\dash$group (a group whose order is a positive power of a prime integer $p$) has a nontrivial center.

(b) Prove that any group of order $p^2$ (where $p$ is prime) is abelian.

(c) Prove that any group of order $5^2 \cdot 7^2$ is abelian.

(d) Write down exactly one representative in each isomorphism class of groups of order $5^2 \cdot 7^2$.

:::{.solution}
Concepts Used:

- Centralizer: $C_G(x) = \theset{g\in G \suchthat [gx] = 1}$.
- Class Equation: $\abs{G} = \abs{Z(G)} + \sum [G: C_G(x_i)]$
- $G/Z(G)$ cyclic $\iff G$ is abelian.
  
  > *Proof:*
    \[
    G/Z(G) = \generators{xZ} 
    &\iff g\in G \implies gZ = x^mZ \\
    &\iff g(x^m)\inv \in Z \\
    &\iff g = x^m z \qtext{for some}z\in Z\\
    &\implies gh = x^mz_1 x^n z_2 = x^n z_2 x^m z_1 = hg
    .\]

- Every group of order $p^2$ is abelian.
- Classification of finite abelian groups.

### a

Strategy: get $p$ to divide $\abs{Z(G)}$.

- Apply the class equation:
\[
\abs{G} = \abs{Z(G)} + \sum [G: C_G(x_i)]
.\]

- Since $C_G(x_i) \leq G$ and $\abs{G} = p^k$, by Lagrange $\abs{C_G(x_i)} = p^\ell$ for some $0\leq \ell \leq k$.
- Since $\abs{G} = p^k$ for some $k$ and $Z(G), C_G(x_i) \leq G$ are subgroups, their orders are powers of $p$.
- Use $$[G: C_G(x_i)] = 1 \iff C_G(x_i) = G \iff \theset{g\in G\suchthat gx_ig\inv = x_i} = G \iff x_i \in Z(G).$$
  - Thus every index appearing in the sum is greater than 1, and thus equal to $p^{\ell_i}$ for some $1\leq \ell_i \leq k$
  - So $p$ divides every term in the sum

- Rearrange 
\[
\abs{G} -  \sum [G: C_G(x_i)]
= \abs{Z(G)} 
.\]

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


:::



## Fall 2012 #1
Let $G$ be a finite group and $X$ a set on which $G$ acts.

a. Let $x\in X$ and $G_x \definedas \theset{g\in G \suchthat g\cdot x = x}$. 
  Show that $G_x$ is a subgroup of $G$.

b. Let $x\in X$ and $G\cdot x \definedas \theset{g\cdot x \suchthat g\in G}$.
  Prove that there is a bijection between elements in $G\cdot x$ and the left cosets of $G_x$ in $G$.


## Fall 2012 #2
Let $G$ be a group of order 30.

a. Show that $G$ contains normal subgroups of orders 3, 5, and 15.

b. Give all possible presentations and relations for $G$.

c. Determine how many groups of order 30 there are up to isomorphism.

## Spring 2012 #2
Let $G$ be a finite group and $p$ a prime number such that there is a normal subgroup $H\normal G$ with $\abs{H} = p^i > 1$.

a. Show that $H$ is a subgroup of any Sylow $p\dash$subgroup of $G$.

b. Show that $G$ contains a nonzero abelian normal subgroup of order divisible by $p$.

## Spring 2012 #3
Let $G$ be a group of order 70.

a. Show that $G$ is not simple.

b. Exhibit 3 nonisomorphic groups of order 70 and prove that they are not isomorphic.

## Fall 2017 #1

Suppose the group $G$ acts on the set $A$. 
Assume this action is faithful (recall that this means that the kernel of the homomorphism from $G$ to $\sym(A)$ which gives the action is trivial) and transitive (for all $a, b$ in $A$, there exists $g$ in $G$ such that $g \cdot a = b$.)

(a) For $a \in A$, let $G_a$ denote the stabilizer of $a$ in $G$. 
Prove that for any $a \in A$, 
$$
\intersect_{\sigma\in G} \sigma G_a \sigma\inv = \theset{1}
.$$

(b) Suppose that $G$ is abelian. Prove that $|G| = |A|$. Deduce that every abelian transitive subgroup of $S_n$ has order $n$.

## Fall 2017 #2


(a) Classify the abelian groups of order 36.

For the rest of the problem, assume that $G$ is a non-abelian group of order 36. 

> You may assume that the only subgroup of order 12 in $S_4$ is $A_4$ and that $A_4$ has no subgroup of order 6.

(b) Prove that if the 2-Sylow subgroup of $G$ is normal, $G$ has a normal subgroup $N$ such that $G/N$ is isomorphic to $A_4$.

(c) Show that if $G$ has a normal subgroup $N$ such that $G/N$ is isomorphic to $A_4$ and a subgroup $H$ isomorphic to $A_4$ it must be the direct product of $N$ and $H$.

(d) Show that the dihedral group of order 36 is a non-abelian group of order 36 whose Sylow-2 subgroup is not normal.

## Spring 2017 #1

Let $G$ be a finite group and $\pi: G\to \sym(G)$ the Cayley representation.
(Recall that this means that for an element $x\in G$, $\pi(x)$ acts by left translation on $G$.)

Prove that $\pi(x)$ is an odd permutation $\iff$ the order $\abs{\pi(x)}$ of $\pi(x)$ is even and $\abs{G} / \abs{\pi(x)}$ is odd.

## Spring 2017 #2

a. How many isomorphism classes of abelian groups of order 56 are there?
  Give a representative for one of each class.

b. Prove that if $G$ is a group of order 56, then either the Sylow-2 subgroup or the Sylow-7 subgroup is normal.

c. Give two non-isomorphic groups of order 56 where the Sylow-7 subgroup is normal and the Sylow-2 subgroup is *not* normal.
  Justify that these two groups are not isomorphic.


## Fall 2016 #1
Let $G$ be a finite group and $s, t\in G$ be two distinct elements of order 2.
Show that subgroup of $G$ generated by $s$ and $t$ is a dihedral group.

> Recall that the dihedral groups of order $2m$ for $m\geq 2$ are of the form
\[
D_{2m} = \gens{\sigma, \tau \suchthat \sigma^m = 1 = \tau^2, \tau \sigma = \sigma\inv \tau}
.\]

## Fall 2016 #3
How many groups are there up to isomorphism of order $pq$ where $p<q$ are prime integers?


## $\star$ Fall 2016 #7

a. Define what it means for a group $G$ to be *solvable*.

b. Show that every group $G$ of order 36 is solvable.

  > Hint: you can use that $S_4$ is solvable.

## Spring 2016 #3

a. State the three Sylow theorems.

b. Prove that any group of order 1225 is abelian.

c. Write down exactly one representative in each isomorphism class of abelian groups of order 1225.

## Spring 2016 #5

Let $G$ be a finite group acting on a set $X$.
For $x\in X$, let $G_x$ be the stabilizer of $x$ and $G\cdot x$ be the orbit of $x$.

a. Prove that there is a bijection between the left cosets $G/G_x$ and $G\cdot x$.

b. Prove that the center of every finite $p\dash$group $G$ is nontrivial by considering that action of $G$ on $X=G$ by conjugation.

## Fall 2015 #1
Let $G$ be a group containing a subgroup $H$ not equal to $G$ of finite index.
Prove that $G$ has a normal subgroup which is contained in every conjugate of $H$ which is of finite index.

## Fall 2015 #2
Let $G$ be a finite group, $H$ a $p\dash$subgroup, and $P$ a sylow $p\dash$subgroup for $p$ a prime.
Let $H$ act on the left cosets of $P$ in $G$ by left translation.

Prove that this is an orbit under this action of length 1.

Prove that $xP$ is an orbit of length 1 $\iff H$ is contained in $xPx\inv$.


## Spring 2015 #1
For a prime $p$, let $G$ be a finite $p\dash$group and let $N$ be a normal subgroup of $G$ of order $p$.
Prove that $N$ is contained in the center of $G$.

## Spring 2015 #4
Let $N$ be a positive integer, and let $G$ be a finite group of order $N$.

a. Let $\sym G$ be the set of all bijections from $G\to G$ viewed as a group under composition.
  Note that $\sym G \cong S_N$.
  Prove that the Cayley map 
  \[
  C: G&\to \sym G\\
  g &\mapsto (x\mapsto gx)
  \]
  is an injective homomorphism.

b. Let $\Phi: \sym G\to S_N$ be an isomorphism.
  For $a\in G$ define $\eps(a) \in \theset{\pm 1}$ to be the sign of the permutation $\Phi(C(a))$.
  Suppose that $a$ has order $d$.
  Prove that $\eps(a) = -1 \iff d$ is even and $N/d$ is odd.

c. Suppose $N> 2$ and $n\equiv 2 \mod 4$.
  Prove that $G$ is not simple.

  > Hint: use part (b).


## Fall 2014 #2
Let $G$ be a group of order 96.

a. Show that $G$ has either one or three 2-Sylow subgroups.

b. Show that either $G$ has a normal subgroup of order 32, or a normal subgroup of order 16.


## Fall 2014 #6
Let $G$ be a group and $H, K < G$ be subgroups of finite index.
Show that
\[
[G: H\intersect K] \leq [G: H] ~ [G:K]
.\]

## Spring 2014 #1
Let $p, n$ be integers such that $p$ is prime and $p$ does not divide $n$.
Find a real number $k = k (p, n)$ such that for every integer $m\geq k$, every group of order $p^m n$ is not simple.


## Spring 2014 #2
Let $G\subset S_9$ be a Sylow-3 subgroup of the symmetric group on 9 letters.

a. Show that $G$ contains a subgroup $H$ isomorphic to $\ZZ_3 \cross \ZZ_3 \cross \ZZ_3$ by exhibiting an appropriate set of cycles.

b. Show that $H$ is normal in $G$.

c. Give generators and relations for $G$ as an abstract group, such that all generators have order 3.
  Also exhibit elements of $S_9$ in cycle notation corresponding to these generators.

d. Without appealing to the previous parts of the problem, show that $G$ contains an element of order 9.


## Fall 2013 #1
Let $p, q$ be distinct primes.

a. Let $\bar q \in \ZZ_p$ be the class of $q\mod p$ and let $k$ denote the order of $\bar q$ as an element of $\ZZ_p\units$.
  Prove that no group of order $pq^k$ is simple.

b. Let $G$ be a group of order $pq$, and prove that $G$ is not simple.


## Fall 2013 #2
Let $G$ be a group of order 30.

a. Show that $G$ has a subgroup of order 15.

b. Show that every group of order 15 is cyclic.

c. Show that $G$ is isomorphic to some semidirect product $\ZZ_{15} \semidirect \ZZ_2$.

d. Exhibit three nonisomorphic groups of order 30 and prove that they are not isomorphic.
  You are not required to use your answer to (c).


## Spring 2013 #3
Let $P$ be a finite $p\dash$group.
Prove that every nontrivial normal subgroup of $P$ intersects the center of $P$ nontrivially.


## Spring 2013 #4
Define a *simple group*.
Prove that a group of order 56 can not be simple.

## Fall 2019 Midterm #1 
Let $G$ be a group of order $p^2q$ for $p, q$ prime. Show that $G$ has a nontrivial normal subgroup.

## Fall 2019 Midterm #2 
Let $G$ be a finite group and let $P$ be a sylow $p\dash$subgroup for $p$ prime. Show that $N(N(P)) = N(P)$ where $N$ is the normalizer in $G$.

## Fall 2019 Midterm #3 
Show that there exist no simple groups of order 148.

## Fall 2019 Midterm #4 
Let $p$ be a prime. Show that $S_p = \gens{\tau, \sigma}$ where $\tau$ is a transposition and $\sigma$ is a $p\dash$cycle.

## Fall 2019 Midterm #5 
Let $G$ be a nonabelian group of order $p^3$ for $p$ prime. Show that $Z(G) = [G, G]$


