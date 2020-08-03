
---
title: "Algebra Qualifying Exam Questions"
---

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
\begin{align*}
D_{2m} = \gens{\sigma, \tau \suchthat \sigma^m = 1 = \tau^2, \tau \sigma = \sigma\inv \tau}
.\end{align*}

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
  \begin{align*}
  C: G&\to \sym G\\
  g &\mapsto (x\mapsto gx)
  \end{align*}
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
\begin{align*}
[G: H\intersect K] \leq [G: H] ~ [G:K]
.\end{align*}

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



# Commutative Algebra

## Spring 2020 #5

Let $R$ be a ring and $f: M\to N$ and $g: N\to M$ be $R\dash$module homomorphisms such that $g\circ f = \id_M$.
Show that $N \cong \im f \oplus \ker g$.

## Fall 2019 #3

Let $R$ be a ring with the property that for every $a \in R, a^2 = a$.

(a) Prove that $R$ has characteristic 2.

(b) Prove that $R$ is commutative.


## Fall 2019 #6

Let $R$ be a commutative ring with multiplicative identity. Assume Zorn's Lemma.

(a) Show that
$$
N = \{r \in R \mid r^n = 0 \text{ for some } n > 0\}
$$
is an ideal which is contained in any prime ideal.

(b) Let $r$ be an element of $R$ not in $N$.
Let $S$ be the collection of all proper ideals of $R$ not containing any positive power of $r$. Use Zorn's Lemma to prove that
there is a prime ideal in $S$.

(c) Suppose that $R$ has exactly one prime ideal $P$ . Prove that every element $r$ of $R$ is either nilpotent or a unit.

## Spring 2019 #6

Let $R$ be a commutative ring with 1.

> Recall that $x \in R$ is nilpotent iff $xn = 0$ for
some positive integer $n$.

(a) Show that every proper ideal of $R$ is contained within a maximal ideal.

(b) Let $J(R)$ denote the intersection of all maximal ideals of $R$.

    Show that $x \in J(R) \iff 1 + rx$ is a unit for all $r \in R$.

(c) Suppose now that $R$ is finite. Show that in this case $J(R)$ consists precisely
of the nilpotent elements in R.


## Fall 2018 #7

Let $R$ be a commutative ring.

(a) Let $r \in R$. Show that the map
\begin{align*}
r\bullet : R &\to R \\
x &\mapsto r x
.\end{align*}
is an $R\dash$module endomorphism of $R$.

(b) We say that $r$ is a **zero-divisor** if r$\bullet$ is not injective.
Show that if $r$ is a zero-divisor and $r \neq 0$, then the kernel and image of $R$ each consist of zero-divisors.

(c) Let $n \geq 2$ be an integer. Show: if $R$ has exactly $n$ zero-divisors, then $\#R \leq n^2$ .

(d) Show that up to isomorphism there are exactly two commutative rings $R$ with precisely 2 zero-divisors.

> You may use without proof the following fact: every ring of order 4 is isomorphic to exactly one of the
following:
$$
\frac{ \ZZ }{ 4\ZZ}, \quad
\frac{ \frac{  \ZZ }{ 2\ZZ} [t]}{(t^2 + t + 1)}, \quad
\frac{ \frac{ \ZZ }{ 2\ZZ} [t]}{ (t^2 - t)}, \quad
\frac{ \frac{ \ZZ}{2\ZZ}[t]}{(t^2 )}
.$$


## Spring 2018 #5

Let 
$$
M=\left(\begin{array}{ll}{a} & {b} \\ {c} & {d}\end{array}\right)
\quad \text{and} \quad 
N=\left(\begin{array}{cc}{x} & {u} \\ {-y} & {-v}\end{array}\right)
$$

over a commutative ring $R$, where $b$ and $x$ are units of $R$. 
Prove that
$$
M N=\left(\begin{array}{ll}{0} & {0} \\ {0} & {*}\end{array}\right)
\implies MN = 0
.$$


## Spring 2018 #8

Let $R = C[0, 1]$ be the ring of continuous real-valued functions on the interval $[0, 1]$. Let I be an ideal of $R$.

(a) Show that if $f \in I, a \in [0, 1]$ are such that $f (a) \neq 0$, then there exists $g \in I$ such that $g(x) \geq 0$ for all $x \in [0, 1]$, and $g(x) > 0$ for all $x$ in some open neighborhood of $a$.

(b) If $I \neq R$, show that the set $Z(I) = \{x \in [0, 1] \suchthat f(x) = 0 \text{ for all } f \in I\}$ is nonempty.

(c) Show that if $I$ is maximal, then there exists $x_0 \in [0, 1]$ such that $I = \{ f \in R \suchthat f (x_0 ) = 0\}$.

## Fall 2017 #5

A ring R is called *simple* if its only two-sided ideals are $0$ and $R$.

(a) Suppose $R$ is a commutative ring with 1. Prove $R$ is simple if and only if $R$ is a field.

(b) Let $k$ be a field. Show the ring $M_n (k)$, $n \times n$ matrices with entries in $k$, is a simple ring.


## Fall 2017 #6

For a ring $R$, let $U(R)$ denote the multiplicative group of units in $R$. Recall that in an integral domain $R$, $r \in R$ is called *irreducible* if $r$ is not a unit in R, and the only divisors of $r$ have the form $ru$ with $u$ a unit in $R$. 

We call a non-zero, non-unit $r \in R$ *prime* in $R$ if $r \divides ab \implies r \divides a$ or $r \divides b$. 
Consider the ring $R = \{a + b \sqrt{-5}\suchthat a, b \in Z\}$.

(a) Prove $R$ is an integral domain.

(b) Show $U(R) = \{\pm1\}$.

(c) Show $3, 2 + \sqrt{-5}$, and $2 - \sqrt{-5}$ are irreducible in $R$.

(d) Show 3 is not prime in $R$.

(e) Conclude $R$ is not a PID.


## Spring 2017 #3

Let $R$ be a commutative ring with 1.
Suppose that $M$ is a free $R\dash$module with a finite basis $X$.

a. Let $I \normal R$ be a proper ideal.
  Prove that $M/IM$ is a free $R/I\dash$module with basis $X'$, where $X'$ is the image of $X$ under the canonical map $M\to M/IM$.

b. Prove that any two bases of $M$ have the same number of elements.
  You may assume that the result is true when $R$ is a field.


## Spring 2017 #4

a. Let $R$ be an integral domain with quotient field $F$.
  Suppose that $p(x), a(x), b(x)$ are monic polynomials in $F[x]$ with $p(x) = a(x) b(x)$ and with $p(x) \in R[x]$, $a(x)$ not in $R[x]$, and both $a(x), b(x)$ not constant.
  Prove that $R$ is not a UFD.
  (You may assume Gauss' lemma)

b. Prove that $\ZZ[2\sqrt{2}]$ is not a UFD.

  > Hint: let $p(x) = x^2-2$.


## Spring 2016 #8

Let $R$ be a simple rng (a nonzero ring which is not assume to have a 1, whose only two-sided ideals are $(0)$ and $R$) satisfying the following two conditions:

i. $R$ has no zero divisors, and
ii. If $x\in R$ with $x\neq 0$ then $2x\neq 0$, where $2x\definedas x+x$.

Prove the following:

a. For each $x\in R$ there is one and only one element $y\in R$ such that $x = 2y$.
b. Suppose $x,y\in R$ such that $x\neq 0$ and $2(xy) = x$, then $yz = zy$ for all $z\in R$.

> You can get partial credit for (b) by showing it in the case $R$ has a 1.

## Fall 2015 #3
Let $R$ be a rng (a ring without 1) which contains an element $u$ such that for all $y\in R$, there exists an $x\in R$ such that $xu=y$.

Prove that $R$ contains a maximal left ideal.

> Hint: imitate the proof (using Zorn's lemma) in the case where $R$ does have a 1.

## Fall 2015 #4
Let $R$ be a PID and $(a_1) < (a_2) < \cdots$ be an ascending chain of ideals in $R$.
Prove that for some $n$, we have $(a_j) = (a_n)$ for all $j\geq n$.

## Spring 2015 #7
Let $R$ be a commutative ring, and $S\subset R$ be a nonempty subset that does not contain 0 such that for all $x, y\in S$ we have $xy\in S$.
Let $\mci$ be the set of all ideals $I\normal R$ such that $I\intersect S = \emptyset$.

Show that for every ideal $I\in \mci$, there is an ideal $J\in \mci$ such that $I\subset J$ and $J$ is not properly contained in any other ideal in $\mci$.

Prove that every such ideal $J$ is prime.


## Fall 2014 #7
Give a careful proof that $\CC[x, y]$ is not a PID.


## Fall 2014 #8
Let $R$ be a nonzero commutative ring without unit such that $R$ does not contain a proper maximal ideal.
Prove that for all $x\in R$, the ideal $xR$ is proper.
You may assume the axiom of choice.

## Spring 2014 #5

Let $R$ be a commutative ring and $a\in R$.
Prove that $a$ is not nilpotent $\iff$ there exists a commutative ring $S$ and a ring homomorphism $\phi: R\to S$ such that $\phi(a)$ is a unit.

> Note: by definition, $a$ is nilpotent $\iff$ there is a natural number $n$ such that $a^n = 0$.

## Spring 2014 #6
Let $R$ be a commutative ring with identity and let $n$ be a positive integer.

a. Prove that every surjective $R\dash$linear endomorphism $T: R^n \to R^n$ is injective.

b. Show that an injective $R\dash$linear endomorphism of $R^n$ need not be surjective.


## Fall 2013 #3

a. Define *prime ideal*, give an example of a nontrivial ideal in the ring $\ZZ$ that is not prime, and prove that it is not prime.

b. Define *maximal ideal*, give an example of a nontrivial maximal ideal in $\ZZ$ and prove that it is maximal.


## Fall 2013 #4
Let $R$ be a commutative ring with $1\neq 0$.
Recall that $x\in R$ is *nilpotent* iff $x^n = 0$ for some positive integer $n$.

a. Show that the collection of nilpotent elements in $R$ forms an ideal.

b. Show that if $x$ is nilpotent, then $x$ is contained in every prime ideal of $R$.

c. Suppose $x\in R$ is not nilpotent and let $S = \theset{x^n \suchthat n\in \NN}$.
  There is at least on ideal of $R$ disjoint from $S$, namely $(0)$.
  By Zorn's lemma the set of ideals disjoint from $S$ has a maximal element with respect to inclusion, say $I$.
  In other words, $I$ is disjoint from $S$ and if $J$ is any ideal disjoint from $S$ with $I\subseteq J \subseteq R$ then $J=I$ or $J=R$.

  Show that $I$ is a prime ideal.

d. Deduce from (a) and (b) that the set of nilpotent elements of $R$ is the intersection of all prime ideals of $R$.

## Spring 2013 #1
Let $R$ be a commutative ring.

a. Define a *maximal ideal* and prove that $R$ has a maximal ideal.

b. Show than an element $r\in R$ is not invertible $\iff r$ is contained in a maximal ideal.

c. Let $M$ be an $R\dash$module, and recall that for $0\neq \mu \in M$, the *annihilator* of $\mu$ is the set
  \begin{align*}
  \ann(\mu) = \theset{r\in R \suchthat r\mu = 0}
  .\end{align*}
  Suppose that $I$ is an ideal in $R$ which is maximal with respect to the property that there exists an element $\mu \in M$ such that $I = \ann(\mu)$ for some $\mu \in M$.
  In other words, $I = \ann(\mu)$ but there does not exist $\nu\in M$ with $J = \ann(\nu) \subsetneq R$ such that $I\subsetneq J$.

  Prove that $I$ is a prime ideal.

## Spring 2013 #2

a. Define a *Euclidean domain*.

b. Define a *unique factorization domain*.

c. Is a Euclidean domain an UFD? 
  Give either a proof or a counterexample with justification.

d. Is a UFD a Euclidean domain?
  Give either a proof or a counterexample with justification.

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

## Fall 2019 #4

Let $F$ be a finite field with $q$ elements.

Let $n$ be a positive integer relatively prime to $q$ and let $\omega$ be a primitive $n$th root of unity in an extension field of $F$.

Let $E = F [\omega]$ and let $k = [E : F]$.

(a) Prove that $n$ divides $q^{k}-1$.

(b) Let $m$ be the order of $q$ in $\ZZ/n\ZZ\units$.
Prove that $m$ divides $k$.

(c) Prove that $m = k$.

## Fall 2019 #7

Let $\zeta_n$ denote a primitive $n$th root of 1 $\in \QQ$.
You may assume the roots of the minimal polynomial $p_n(x)$ of $\zeta_n$ are exactly the primitive $n$th roots of 1.

Show that the field extension $\QQ(\zeta_n )$ over $\QQ$ is Galois and prove its Galois group is $(\ZZ/n\ZZ)\units$.

How many subfields are there of $\QQ(\zeta_{20} )$?

## Spring 2019 #2
Let $F = \FF_p$ , where $p$ is a prime number.

(a) Show that if $\pi(x) \in F[x]$ is irreducible of degree $d$, then $\pi(x)$ divides $x^{p^d} - x$.


(b) Show that if $\pi(x) \in F[x]$ is an irreducible polynomial that divides $x^{p^n} - x$,
then $\deg \pi(x)$ divides $n$.

## Spring 2019 #8
Let $\zeta = e^{2\pi i/8}$.

(a) What is the degree of $\QQ(\zeta)/\QQ$?

(b) How many quadratic subfields of $\QQ(\zeta)$ are there?

(c) What is the degree of $\QQ(\zeta, \sqrt[4] 2)$ over $\QQ$?

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

  \begin{align*}
  \left(\begin{array}{ll}
  a & b \\
  0 & 1
  \end{array}\right) 
  \qtext{where} a\in \FF_5\units \text{ and } b\in \FF_5
  .\end{align*}

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



# Modules


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

(a) Show that $N$ is a $\ZZ\dash$submodule of $M$ .

(b) Find vectors $u_1 , u_2 , u_3 , u_4 \in \ZZ^4$ and integers $d_1 , d_2 , d_3 , d_4$ such that
$$
\{u_1 , u_2 , u_3 , u_4 \}
$$
is a free basis for $M$, and
$$
\{d_1 u_1,~ d_2 u_2,~ d_3 u_3,~ d_4 u_4 \}
$$
is a free basis for $N$ .

(c) Use the previous part to describe $M/N$ as a direct sum of cyclic $\ZZ\dash$modules.

### Fall 2018 #6.

Let $R$ be a commutative ring, and let $M$ be an $R\dash$module. 
An $R\dash$submodule $N$ of $M$ is maximal if there is no $R\dash$module $P$ with $N \subsetneq P \subsetneq M$.

(a) Show that an $R\dash$submodule $N$ of $M$ is maximal $\iff M /N$ is a simple $R\dash$module: i.e., $M /N$ is nonzero and has no proper, nonzero $R\dash$submodules.

(b) Let $M$ be a $\ZZ\dash$module. Show that a $\ZZ\dash$submodule $N$ of $M$ is maximal $\iff \#M /N$ is a prime number.

(c) Let $M$ be the $\ZZ\dash$module of all roots of unity in $\CC$ under multiplication.
Show that there is no maximal $\ZZ\dash$submodule of $M$.

### Spring 2018 #7.

Let $R$ be a PID and $M$ be an $R\dash$module. Let $p$ be a prime element of $R$. The module $M$ is called *$\generators{p}\dash$primary* if for every $m \in M$ there exists $k > 0$ such that $p^k m = 0$.

(a) Suppose M is $\generators{p}\dash$primary. Show that if $m \in M$ and $t \in R, ~t \not\in \generators{p}$, then there exists $a \in R$ such that
$atm = m$.

(b) A submodule $S$ of $M$ is said to be *pure* if $S \cap r M = rS$ for all $r \in R$. Show that if $M$ is $\generators{p}\dash$primary, then $S$ is pure if and only if $S \cap p^k M = p^k S$ for all $k \geq 0$.


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
  \begin{align*}
  0 = M_0 \subset M_1 \subset \cdots \subset M_n = M
  \end{align*}
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

### Spring 2012 #5
Let $M$ be a finitely generated module over a PID $R$.

a. $M_t$ be the set of torsion elements of $M$, and show that $M_t$ is a submodule of $M$.

b. Show that $M/M_t$ is torsion free.

c. Prove that $M \cong M_t \oplus F$ where $F$ is a free module.

### Spring 2017 #5

Let $R$ be an integral domain and let $M$ be a nonzero torsion $R\dash$module.

a. Prove that if $M$ is finitely generated then the annihilator in $R$ of $M$ is nonzero.

b. Give an example of a non-finitely generated torsion $R\dash$module whose annihilator is $(0)$, and justify your answer.

### $\star$ Fall 2019 #5

Let $R$ be a ring and $M$ an $R\dash$module.

> Recall that the set of torsion elements in M is defined by
$$
\Tor(m) = \{m \in M \suchthat \exists r \in R, ~r \neq 0, ~rm = 0\}
.$$

(a) Prove that if $R$ is an integral domain, then $\Tor(M )$ is a submodule of $M$ .

(b) Give an example where $\Tor(M )$ is not a submodule of $M$.

(c) If $R$ has zero-divisors, prove that every non-zero $R\dash$module has non-zero torsion elements.

### $\star$ Spring 2019 #5.

Let $R$ be an integral domain. Recall that if $M$ is an $R\dash$module, the *rank* of $M$ is
defined to be the maximum number of $R\dash$linearly independent elements of $M$ .

(a) Prove that for any $R\dash$module $M$, the rank of $\tor(M )$ is 0.

(b) Prove that the rank of $M$ is equal to the rank of of $M/\tor(M )$.

(c) Suppose that M is a non-principal ideal of $R$.

    Prove that $M$ is torsion-free of rank 1 but not free.


### $\star$ Spring 2020 #6

Let $R$ be a ring with unity.

a. Give a definition for a free module over $R$.

b. Define what it means for an $R\dash$module to be torsion free.

c. Prove that if $F$ is a free module, then any short exact sequence of $R\dash$modules of the following form splits:
\begin{align*}
0 \to N \to M \to F \to 0
.\end{align*}

d. Let $R$ be a PID. 
  Show that any finitely generated $R\dash$module $M$ can be expressed as a direct sum of a torsion module and a free module.
  You may assume that a finitely generated torsionfree module over a PID is free.

### Fall 2019 Final #3 
Let $R = k[x]$ for $k$ a field and let $M$ be the $R\dash$module given by
  \begin{align*}
  M=\frac{k[x]}{(x-1)^{3}} \oplus \frac{k[x]}{\left(x^{2}+1\right)^{2}} \oplus \frac{k[x]}{(x-1)\left(x^{2}+1\right)^{4}} \oplus \frac{k[x]}{(x+2)\left(x^{2}+1\right)^{2}}
  .\end{align*}
  Describe the elementary divisors and invariant factors of $M$.

### Fall 2019 Final #4 
Let $I = (2, x)$ be an ideal in $R = \ZZ[x]$, and show that $I$ is not a direct sum of nontrivial cyclic $R\dash$modules.

### Fall 2019 Final #5 
Let $R$ be a PID. 

- Classify irreducible $R\dash$modules up to isomorphism.
- Classify indecomposable $R\dash$modules up to isomorphism.

### Fall 2019 Final #6 
Let $V$ be a finite-dimensional $k\dash$vector space and $T:V\to V$ a non-invertible $k\dash$linear map. Show that there exists a $k\dash$linear map $S:V\to V$ with $T\circ S = 0$ but $S\circ T\neq 0$. 

### Fall 2019 Final #7 
Let $A\in M_n(\CC)$ with $A^2 = A$. Show that $A$ is similar to a diagonal matrix, and exhibit an explicit diagonal matrix similar to $A$.

### Fall 2019 Final #8 
Exhibit the rational canonical form for
  - $A\in M_6(\QQ)$ with minimal polynomial $(x-1)(x^2 + 1)^2$.
  - $A\in M_{10}(\QQ)$ with minimal polynomial $(x^2+1)^2(x^3 + 1)$.

### Fall 2019 Final #9 
Exhibit the rational and Jordan canonical forms for the following matrix $A\in M_4(\CC)$:
  \begin{align*}
  A=\left(\begin{array}{cccc}
  2 & 0 & 0 & 0 \\
  1 & 1 & 0 & 0 \\
  -2 & -2 & 0 & 1 \\
  -2 & 0 & -1 & -2
  \end{array}\right)
  .\end{align*}

### Fall 2019 Final #10 
Show that the eigenvalues of a Hermitian matrix $A$ are real and that $A = PDP\inv$ where $P$ is an invertible matrix with orthogonal columns.


# Linear Algebra: Canonical Forms

## Spring 2020 #7

Let
\begin{align*}
A=\left[\begin{array}{ccc}
2 & 0 & 0 \\
4 & 6 & 1 \\
-16 & -16 & -2
\end{array}\right] \in M_{3}(\mathrm{C})
.\end{align*}

a. Find the Jordan canonical form $J$ of $A$.

b. Find an invertible matrix $P$ such that $P\inv A P = J$. 
  You should not need to compute $P\inv$.

c. Write down the minimal polynomial of $A$.

## Spring 2020 #8

Let $T:V\to V$ be a linear transformation where $V$ is a finite-dimensional vector space over $\CC$.
Prove the Cayley-Hamilton theorem: if $p(x)$ is the characteristic polynomial of $T$, then $p(T) = 0$.
You may use canonical forms.

## Spring 2012 #8
Let $V$ be a finite-dimensional vector space over a field $k$ and $T:V\to V$ a linear transformation.

a. Provide a definition for the *minimal polynomial* in $k[x]$ for $T$.

b. Define the *characteristic polynomial* for $T$.

c. Prove the Cayley-Hamilton theorem: the linear transformation $T$ satisfies its characteristic polynomial.

## Spring 2019 #7

Let $p$ be a prime number.
Let $A$ be a $p \times p$ matrix over a field $F$ with 1 in all
entries except 0 on the main diagonal.

Determine the Jordan canonical form (JCF) of $A$

(a) When $F = \QQ$,

(b) When $F = \FF_p$.

> Hint: In both cases, all eigenvalues lie in the ground field. In each case find a
matrix $P$ such that $P\inv AP$ is in JCF.


## Spring 2018 #4

Let

$$
A=\left[\begin{array}{lll}{0} & {1} & {-2} \\ {1} & {1} & {-3} \\ {1} & {2} & {-4}\end{array}\right] \in M_{3}(\mathbb{C})
$$

(a) Find the Jordan canonical form J of A.

(b) Find an invertible matrix $P$ such that $P\inv AP = J$. 

> You should not need to compute $P\inv$.


## Spring 2017 #6

Let $A$ be an $n\times n$ matrix with all entries equal to $0$ except for the $n-1$ entries just above the diagonal being equal to 2.

a. What is the Jordan canonical form of $A$, viewed as a matrix in $M_n(\CC)$?

b. Find a nonzero matrix $P\in M_n(\CC)$ such that $P\inv A P$ is in Jordan canonical form.


## Spring 2016 #1
Let
\begin{align*}
A=\left(\begin{array}{ccc}
-3 & 3 & -2 \\
-7 & 6 & -3 \\
1 & -1 & 2
\end{array}\right) \in M_{3}(\mathrm{C})
.\end{align*}

a. Find the Jordan canonical form $J$ of $A$.

b. Find an invertible matrix $P$ such that $P\inv A P = J$.
  You do not need to compute $P\inv$.


## Spring 2016 #7

Let $D = \QQ[x]$ and let $M$ be a $\QQ[x]\dash$module such that
\begin{align*}
M \cong \frac{\mathbb{Q}[x]}{(x-1)^{3}} \oplus \frac{\mathbb{Q}[x]}{\left(x^{2}+1\right)^{3}} \oplus \frac{\mathbb{Q}[x]}{(x-1)\left(x^{2}+1\right)^{5}} \oplus \frac{\mathbb{Q}[x]}{(x+2)\left(x^{2}+1\right)^{2}}
.\end{align*}

Determine the elementary divisors and invariant factors of $M$.







## Spring 2015 #6

Let $F$ be a field and $n$ a positive integer, and consider
\begin{align*}
A=\left[\begin{array}{ccc}
1 & \dots & 1 \\
& \ddots & \\
1 & \dots & 1
\end{array}\right] \in M_{n}(F)
.\end{align*}

Show that $A$ has a Jordan normal form over $F$ and find it.

> Hint: treat the cases $n\cdot  1 \neq 0$ in $F$ and $n\cdot 1 = 0$ in $F$ separately.


## Fall 2014 #5
Let $T$ be a $5\times 5$ complex matrix with characteristic polynomial $\chi(x) = (x-3)^5$ and minimal polynomial $m(x) = (x-3)^2$.
Determine all possible Jordan forms of $T$.

## Spring 2013 #5
Let $T: V\to V$ be a linear map from a 5-dimensional $\CC\dash$vector space to itself and suppose $f(T) = 0$ where $f(x) = x^2 + 2x + 1$.

a. Show that there does not exist any vector $v\in V$ such that $Tv = v$, but there *does* exist a vector $w\in V$ such that $T^2 w= w$.

b. Give all of the possible Jordan canonical forms of $T$.


## $\star$ Spring 2012 #7
Consider the following matrix as a linear transformation from $V\definedas \CC^5$ to itself:
\begin{align*}
A=\left(\begin{array}{ccccc}
-1 & 1 & 0 & 0 & 0 \\
-4 & 3 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 & 1 \\
0 & 0 & 0 & 1 & 0 \\
0 & 0 & 0 & 0 & 2
\end{array}\right)
.\end{align*}

a. Find the invariant factors of $A$.

b. Express $V$ in terms of a direct sum of indecomposable $\CC[x]\dash$modules.

c. Find the Jordan canonical form of $A$.




# Linear Algebra: Diagonalizability

## Spring 2015 #3
Let $F$ be a field and $V$ a finite dimensional $F\dash$vector space, and let $A, B: V\to V$ be commuting $F\dash$linear maps.
Suppose there is a basis $\mcb_1$ with respect to which $A$ is diagonalizable and a basis $\mcb_2$ with respect to which $B$ is diagonalizable.

Prove that there is a basis $\mcb_3$ with respect to which $A$ and $B$ are both diagonalizable.

## Spring 2013 #6
Let $V$ be a finite dimensional vector space over a field $F$ and let $T: V\to V$ be a linear operator with characteristic polynomial $f(x) \in F[x]$.

a. Show that $f(x)$ is irreducible in $F[x] \iff$ there are no proper nonzero subspaces $W< V$ with $T(W) \subseteq W$.

b. If $f(x)$ is irreducible in $F[x]$ and the characteristic of $F$ is 0, show that $T$ is diagonalizable when we extend the field to its algebraic closure.

## Spring 2019 #1

Let $A$ be a square matrix over the complex numbers.
Suppose that $A$ is nonsingular
and that $A^{2019}$ is diagonalizable over $\CC$.

Show that $A$ is also diagonalizable over $\CC$.

## Fall 2017 #7
Let $F$ be a field and let $V$ and $W$ be vector spaces over $F$ . 

Make $V$ and $W$ into $F[x]\dash$modules via linear operators $T$ on $V$ and $S$ on $W$ by defining $X \cdot v = T (v)$ for all $v \in V$ and $X \cdot w = S(w)$ for all w $\in$ W . 

Denote the resulting $F[x]\dash$modules by $V_T$ and $W_S$ respectively.

(a) Show that an $F[x]\dash$module homomorphism from $V_T$ to $W_S$ consists of an $F\dash$linear transformation $R : V \to W$ such that $RT = SR$.

(b) Show that $VT \cong WS$ as $F[x]\dash$modules $\iff$ there is an $F\dash$linear isomorphism $P : V \to W$ such that $T = P\inv SP$.

(c) Recall that a module $M$ is *simple* if $M \neq 0$ and any proper submodule of $M$ must be zero. Suppose that $V$ has dimension 2. Give an example of $F$, $T$ with $V_T$ simple.

(d) Assume $F$ is algebraically closed. Prove that if $V$ has dimension 2, then any $V_T$ is not simple.

## Fall 2016 #2
Let $A, B$ be two $n\times n$ matrices with the property that $AB = BA$.
Suppose that $A$ and $B$ are diagonalizable.
Prove that $A$ and $B$ are *simultaneously* diagonalizable.

# Linear Algebra: Misc

## Fall 2012 #7
Let $k$ be a field of characteristic zero and $A, B \in M_n(k)$ be two square $n\times n$ matrices over $k$ such that $AB - BA = A$.
Prove that $\det A = 0$.

Moreover, when the characteristic of $k$ is 2, find a counterexample to this statement.

## Fall 2012 #8
Prove that any nondegenerate matrix $X\in M_n(\RR)$ can be written as $X = UT$ where $U$ is orthogonal and $T$ is upper triangular.

## Fall 2012 #5
Let $U$ be an infinite-dimensional vector space over a field $k$, $f: U\to U$ a linear map, and $\theset{u_1, \cdots, u_m} \subset U$ vectors such that $U$ is generated by $\theset{u_1, \cdots, u_m, f^d(u_1), \cdots, f^d(u_m)}$ for some $d\in \NN$.

Prove that $U$ can be written as a direct sum $U \cong V\oplus W$ such that 

1. $V$ has a basis consisting of some vector $v_1, \cdots v_n, f^d(v_1), \cdots, f^d(v_n)$ for some $d\in \NN$, and
2. $W$ is finite-dimensional.

Moreover, prove that for any other decomposition $U \cong V' \oplus W'$, one has $W' \cong W$.

## Fall 2015 #7

a. Show that two $3\times 3$ matrices over $\CC$ are similar $\iff$ their characteristic polynomials are equal and their minimal polynomials are equal.

b. Does the conclusion in (a) hold for $4\times 4$ matrices?
  Justify your answer with a proof or counterexample.

##  Fall 2018 #4

Let $V$ be a finite dimensional vector space over a field (the field is not necessarily algebraically closed).

Let $\phi : V \to V$ be a linear transformation. Prove that there exists a decomposition of $V$ as $V = U \oplus W$ , where $U$ and $W$ are $\phi\dash$invariant subspaces of $V$ , $\restrictionof{\phi}{U}$ is nilpotent, and $\restrictionof{\phi}{W}$ is nonsingular.

## Fall 2018 #5

Let $A$ be an $n \times n$ matrix.

(a) Suppose that $v$ is a column vector such that the set $\{v, Av, . . . , A^{n-1} v\}$ is linearly independent. Show that any matrix $B$ that commutes with $A$ is a polynomial in $A$.

(b) Show that there exists a column vector $v$ such that the set $\{v, Av, . . . , A^{n-1} v\}$ is linearly independent $\iff$ the characteristic polynomial of A equals the minimal polynomial of A.

## Fall 2019 #8

Let $\{e_1, \cdots, e_n \}$ be a basis of a real vector space $V$ and let
$$
\Lambda \definedas \theset{ \sum r_i e_i \mid r_i \in \ZZ}
$$

Let $\cdot$ be a non-degenerate ($v \cdot w = 0$ for all $w \in V \iff v = 0$) symmetric bilinear form on $V$ such that the Gram matrix $M = (e_i \cdot e_j )$ has integer entries.

Define the dual of $\Lambda$ to be

$$
\Lambda \dual \definedas \{v \in V \suchthat v \cdot x \in \ZZ \text{ for all } x \in \Lambda
\}
.$$

(a) Show that $\Lambda \subset \Lambda \dual$.

(b) Prove that $\det M \neq 0$ and that the rows of $M\inv$ span $\Lambda\dual$.

(c) Prove that $\det M = |\Lambda\dual /\Lambda|$.


## Spring 2012 #6
Let $k$ be a field and let the group $G = \GL(m, k) \cross \GL(n, k)$ acts on the set of $m\times n$ matrices $M_{m, n}(k)$ as follows:
\begin{align*}
(A, B) \cdot X = AXB\inv
\end{align*}
where $(A, B) \in G$ and $X\in M_{m, n}(k)$.

a. State what it means for a group to act on a set.
  Prove that the above definition yields a group action.

b. Exhibit with justification a subset $S$ of $M_{m, n}(k)$ which contains precisely one element of each orbit under this action.

## Spring 2014 #7
Let $G = \GL(3, \QQ[x])$ be the group of invertible $3\times 3$ matrices over $\QQ[x]$.
For each $f\in \QQ[x]$, let $S_f$ be the set of $3\times 3$ matrices $A$ over $\QQ[x]$ such that $\det(A) = c f(x)$ for some nonzero constant $c\in \QQ$.

a. Show that for $(P, Q) \in G\cross G$ and $A\in S_f$, the formula
  \begin{align*}
  (P, Q)\cdot A \definedas PAQ\inv
  \end{align*}
  gives a well defined map $G\cross G \cross S_f \to S_f$ and show that this map gives a group action of $G\cross G$ on $S_f$.

b. For $f(x) = x^3(x^2+1)^2$, give one representative from each orbit of the group action in (a), and justify your assertion.

## Fall 2014 #4
Let $F$ be a field and $T$ an $n\times n$ matrix with entries in $F$.
Let $I$ be the ideal consisting of all polynomials $f\in F[x]$ such that $f(T) =0$.

Show that the following statements are equivalent about a polynomial $g\in I$:

a. $g$ is irreducible.

b. If $k\in F[x]$ is nonzero and of degree strictly less than $g$, then $k[T]$ is an invertible matrix.

## Fall 2015 #8
Let $V$ be a vector space over a field $F$ and $V\dual$ its dual.
A *symmetric bilinear form* $(\wait, \wait)$ on $V$ is a map $V\cross V\to F$ satisfying
\begin{align*}
(av_1 + b v_2, w) = a(v_1, w) + b(v_2, w) \qtext{and} (v_1, v_2) = (v_2, v_1)
\end{align*}
for all $a, b\in F$ and $v_1, v_2 \in V$.
The form is *nondegenerate* if the only element $w\in V$ satisfying $(v, w) = 0$ for all $v\in V$ is $w=0$.

Suppose $(\wait, \wait)$ is a nondegenerate symmetric bilinear form on $V$.
If $W$ is a subspace of $V$, define
\begin{align*}
W\perp \definedas \theset{v\in V \suchthat (v, w) = 0 \text{ for all } w\in W}
.\end{align*}

a. Show that if $X, Y$ are subspaces of $V$ with $Y\subset X$, then $X\perp \subseteq Y\perp$.

b. Define an injective linear map 
  \begin{align*}
  \psi: Y\perp/X\perp \injects (X/Y)\dual
  \end{align*}
  which is an isomorphism if $V$ is finite dimensional.

