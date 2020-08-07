# Group Theory


## Fall 2019 #1

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
> \[
h^g &= ghg\inv \\
h^G &= \theset{ h^g \suchthat g\in G} \quad\text{Conjugacy Class}\\
H^g &= \theset{h^g \suchthat h\in H} \\
N_G(H) &= \theset{g\in G \suchthat H^g = H} \supseteq H \quad\text{Normalizer}
.\]
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
\[
\abs{\union_{g\in G} H^g} 
&= \qty{ \abs{H} - 1} [G: N_G(H)] + 1\\
&= \abs{H} [G: N_G(H)]  - [G:N_G(H)] + 1\\
&= \abs{G} \frac{\abs G}{\abs{N_G(H)}} - \frac{\abs G}{\abs{N_G(H)}} + 1 \\
&\leq \abs{H} \frac{\abs G}{\abs{H}} - \frac{\abs G}{\abs{H}} + 1 \\
&= \abs{G} - ([G: H] - 1) \\
&< \abs{G} 
.\]
> where we use the fact that $H \subseteq N_G(H) \implies \abs{H} \leq \abs{N_G(H)} \implies \frac{1}{\abs{N_G(H)}} \leq \frac{1}{\abs{H}}$, and since $H < G$ is proper, $[G:H] \geq 2$.

Since $[g_i, g_j] = 1$, we have $g_i \in Z(g_j)$ for every $i, j$.

Then
\[
g\in G 
&\implies g = g_i^h \quad \text{ for some } h \\
&\implies g \in Z(g_\mathbf{j})^h \quad\text{for every } j \text{ since }g_i \in Z(g_j) ~\forall j \\
&\implies g \in \union_{h\in G} Z(g_j)^h \quad\text{for every } j\\
&\implies G \subseteq \union_{h\in G} Z(g_j)^h \quad\text{for every } j
,\]

which by Theorem 3, if $Z(g_j) < G$ were proper, then the RHS is properly contained in $G$. 
So it must be the case that that $Z(g_j)$ is not proper and thus equal to $G$ for every $j$.

But $Z(g_i) = G \iff g_i \in Z(G)$, and so each conjugacy class is size one.
So for every $g\in G$, we have $g = g_j$ for some $j$, and thus $g = g_j \in Z(g_j) = Z(G)$, so $g$ is central.
Then $G\subseteq Z(G)$ and $G$ is abelian.


## Fall 2019 #2 

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
\[
A_i\normal G, \quad G = A_1 \cdots A_k,\quad A_k \intersect \prod_{i\neq k} A_i = \emptyset \implies G = \prod A_i
.\]

- The intersection of subgroups is a again a subgroup.
- Any subgroups of coprime order intersect trivially?


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

### b (Todo)

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


## Spring 2019 #3

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

## Spring 2019 #4

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


## Fall 2018 #1 

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

## Fall 2018 #2 

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

# Spring 2018 #1 

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

$\qed$


