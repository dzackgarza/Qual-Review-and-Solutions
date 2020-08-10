# Group Theory

## Spring 2020 #1

a. Show that any group of order 2020 is solvable.

b. Give (without proof) a classification of all abelian groups of order 2020.

c. Describe one nonabelian group of order 2020.

## Spring 2020 #2

Let $H$ be a normal subgroup of a finite group $G$ where the order of $H$ and the index of $H$ in $G$ are relatively prime.
Prove that no other subgroup of $G$ has the same order as $H$.

## Fall 2019 #1

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



## Fall 2019 #2

Let $G$ be a group of order 105 and let $P, Q, R$ be Sylow 3, 5, 7 subgroups respectively.

(a) Prove that at least one of $Q$ and $R$ is normal in $G$.

(b) Prove that $G$ has a cyclic subgroup of order 35.

(c) Prove that both $Q$ and $R$ are normal in $G$.

(d) Prove that if $P$ is normal in $G$ then $G$ is cyclic.

## Spring 2019 #3

How many isomorphism classes are there of groups of order 45?

Describe a representative from each class.

## Spring 2019 #4

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

## Fall 2018 #1

Let $G$ be a finite group whose order is divisible by a prime number $p$.
Let $P$ be a normal $p\dash$subgroup of $G$
(so $\abs P = p^c$ for some $c$).

(a) Show that $P$ is contained in every Sylow $p\dash$subgroup of $G$.

(b) Let $M$ be a maximal proper subgroup of $G$. Show that either $P \subseteq M$ or $|G/M | = p^b$ for some $b \leq c$.


## Fall 2018 #2

(a) Suppose the group $G$ acts on the set $X$ . Show that the stabilizers of elements in the same orbit are conjugate.

(b) Let $G$ be a finite group and let $H$ be a proper subgroup. Show that the union of the conjugates of $H$ is strictly smaller than $G$, i.e.
$$
\union_{g\in G} gHg\inv \subsetneq G
$$

(c) Suppose $G$ is a finite group acting transitively on a set $S$ with at least 2 elements. Show that there is an element of $G$ with no fixed points in $S$.


## Spring 2018 #1

(a) Use the Class Equation (equivalently, the conjugation action of a group on itself) to prove that any $p\dash$group (a group whose order is a positive power of a prime integer $p$) has a nontrivial center.

(b) Prove that any group of order $p^2$ (where $p$ is prime) is abelian.

(c) Prove that any group of order $5^2 \cdot 7^2$ is abelian.

(d) Write down exactly one representative in each isomorphism class of groups of order $5^2 \cdot 7^2$.

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


