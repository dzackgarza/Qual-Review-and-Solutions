# Group Theory: General

## Spring 2020 #2 $\done$
Let $H$ be a normal subgroup of a finite group $G$ where the order of $H$ and the index of $H$ in $G$ are relatively prime.
Prove that no other subgroup of $G$ has the same order as $H$.

:::{.concept}
\envlist

- Division algorithm: $(a,b)= d\implies as+bt =1$ for some $s, t$.
- Coset containment trick: $X\subseteq N \iff xN = N$ for all $x$.
:::

:::{.strategy}
Recognize that it suffices to show $hN = N$.
Context cue: coprimality hints at division algorithm.
Descend to quotient so you can leverage both the order of $h$ *and* the order of cosets simultaneously.
:::

:::{.solution}
\envlist

- For ease of notation, replace $H$ in the problem with $N$ so we remember which one is normal.
- Write $n\da \# N$ and $m \da [G:N] = \#G/N$, where the quotient makes sense since $N$ is normal.
- Let $H \leq G$ with $\# H = n$, we'll show $H=N$.
  - Since $\# H = \# N$ it suffices to show $H \subseteq N$.
  - It further suffices to show $hN = N$ for all $h\in H$.
- Noting $\gcd(m, n)=1$, use the division algorithm to write $1 = ns + mt$ for some $s,t\in \ZZ$.
- The result follows from a computation:
\[
hN 
&= h^1 N \\
&= h^{ns + mt}N \\
&= h^{ns} N \cdot h^{mt}N \\
&= \qty{h^n N}^s \cdot \qty{h^t N}^m \\
&= (eN)^s \cdot N \\
&= N
,\]
  - We've used that $h\in H \implies o(h) \divides \# H = n$ by Lagrange, so $h^n = e$.
  - We've also used that $\# G/N = m$, so $(xH)^m = H$ for any $xH\in G/H$.

:::


## Spring 2019 #4 $\done$
For a finite group $G$, let $c(G)$ denote the number of conjugacy classes of $G$.

a.
Prove that if two elements of $G$ are chosen uniformly at random,then the probability they commute is precisely
$$
\frac{c(G)}{\abs G}
.$$

b.
State the class equation for a finite group.

c.
Using the class equation (or otherwise) show that the probability in part (a) is at most $$
\frac 1 2 + \frac 1 {2[G : Z(G)]}
.$$

> Here, as usual, $Z(G)$ denotes the center of $G$.


:::{.warnings}
(DZG) This is a slightly anomalous problem!
It's fun and worth doing, because it uses the major counting formulas.
Just note that the techniques used in this problem perhaps don't show up in other group theory problems.
:::


:::{.concept}
\envlist

- Notation: $X/G$ is the set of $G\dash$orbits
- Notation: $X^g = \theset{x\in X\suchthat g\cdot x = x}$
- Burnside's formula: $\#{X/G} = {1 \over \# G} \sum \# {X^g}$.
- Definition of conjugacy class: $C(g) = \ts{ hgh\inv \st h\in G }$.
:::

:::{.strategy}
Fixed points of the conjugation action are precisely commuting elements.
Apply Burnside.
Context clue: $1/[G:Z(G)]$ is weird, right? 
Use that $[G:Z(G)] = \# G/\# Z(G)$, so try to look for $\#Z(G)/\#(G)$ somewhere.
:::

:::{.solution}
\envlist

:::{.proof title="Part a"}
\envlist

- Define a sample space $\Omega = G \cross G$, so $\# {\Omega} = (\# {G})^2$.

- Identify the event we want to analyze: 
\[
A \definedas \theset{(g,h) \in G\cross G \suchthat [g,h] = 1} \subseteq \Omega
.\]
- Note that the slices are centralizers:
\[
A_g \definedas \theset{(g, h) \in \ts{ g } \cross G \suchthat [g, h] = 1} = Z(g) \implies A = \Disjoint_{g\in G} Z(g)
.\]

- Set $n$ be the number of conjugacy classes, note we want to show $P(A) = n / \abs{G}$.
 
- Let $G$ act on itself by conjugation, which partitions $G$ into conjugacy classes.

  - What are the orbits? 
  $$
  \mathcal{O}_g = \theset{hgh\inv \suchthat h\in G}
  ,$$ 
  which is the **conjugacy class** of $g$.
  In particular, the number of orbits is the number of conjugacy classes.

  - What are the fixed points? 
  $$X^g = \theset{h\in G \suchthat hgh\inv = g},$$ 
  which are the elements of $G$ that commute with $g$, which is isomorphic to $A_g$.


- Identifying centralizers with fixed points, 
  $$
  \#{A} = \#{\Disjoint_{g\in G} Z(g) } = \sum_{g\in G} \#{Z(g)} = \sum_{g\in G}\# {X^g}
  .$$


- Apply Burnside
$$
\# {X / G} = \frac { 1 } { \# G  } \sum _ { g \in G } \# X ^ { g } ,
$$
- Note $\#{X/G} = n$, i.e. the number of conjugacy classes is the number of orbits.
- Rearrange and use definition:
$$
n \cdot \#{G}
= \qty{\#{X/G} }\cdot \#{G}
= \sum _ { g \in G } \# X ^ { g } 
$$
- Compute probability:
\[
P(A)
= {\# A \over \# \Omega} 
= \Sum_{ g \in G } \frac{\# X ^ { g }}{ ( \# {G} )^2} 
= \frac{\qty{ \# {X/G}} \cdot \#{G}}{ (\#{G})^2} 
= \frac{n \cdot \#{G}}{( \#{G} )^2} 
= \frac n {\# G}
.\]

:::

:::{.proof title="Part b"}
Statement of the class equation:
\[
\abs G = Z(G) + \sum_{\substack{\text{One $x$ from each} \\ \text{conjugacy class}}}[G: Z(x)]
\]
where $Z(x) = \theset{g\in G \suchthat [g, x] = 1}$ is the centralizer of $x$ in $G$.
:::

:::{.proof title="Part c"}
\envlist

> (DZG): I couldn't convince myself that a previous proof using the class equation actually works.
> Instead, I'll borrow the proof from [this note](https://math.berkeley.edu/~tb65536/Commuting_Probability.pdf)

- Write the event as $A = \Disjoint_{g\in G} \ts{g} \cross Z(g)$, then
\[
P(A) 
= {\# A\over (\# G)^2} 
= {1\over (\# G)^2} \sum_{g\in G} \# Z(g)
.\]
- Attempt to estimate the sum: pull out central elements $g\in Z(G)$.
  - Note $Z(g) = G$ for central $g$, so $\# Z(g) = \# G$
  - Note $g\not\int Z(G)$ implies $\# Z(g) \leq {1\over 2} \# G$, since $Z(g) \leq G$ is a subgroup, and $[G:Z(g)] \neq 1 \implies [G: Z(g)] \geq 2$.
\[
P(A) 
&= {1\over (\# G)^2 } \qty{ \sum_{g\in Z(g)} \# Z(g) + \sum_{g\not\in Z(g)} \# Z(g) } \\
&= {1\over (\# G)^2 } \qty{ \sum_{g\in Z(g)} \# G + \sum_{g\not\in Z(g)} \# Z(g) } \\
&= {1\over (\# G)^2 } \qty{ \# Z(G) \cdot \# G + \sum_{g\not\in Z(g)} \# Z(g) } \\
&\leq {1\over (\# G)^2 } \qty{ \# Z(G) \cdot \# G + \sum_{g\not\in Z(g)} {1\over 2} \# G } \\
&= {1\over (\# G)^2 } \qty{ \# Z(G) \cdot \# G + \qty{ \sum_{g\not\in Z(g)} {1\over 2} } \cdot \# G } \\
&= {1\over (\# G) } \qty{ \# Z(G) + \sum_{g\not\in Z(g)} {1\over 2} } \\
&= {1\over (\# G) } \qty{ \# Z(G) + {1\over 2} \sum_{g\not\in Z(g)} 1 } \\
&= {1\over (\# G) } \qty{ \# Z(G) + {1\over 2} \#(G \sm Z(G) ) } \\
.\]



:::

\todo[inline]{Redo part c}

:::

## Spring 2012 #2 $\work$
Let $G$ be a finite group and $p$ a prime number such that there is a normal subgroup $H\normal G$ with $\abs{H} = p^i > 1$.

a.
Show that $H$ is a subgroup of any Sylow $p\dash$subgroup of $G$.

b.
Show that $G$ contains a nonzero abelian normal subgroup of order divisible by $p$.

## Spring 2017 #1 $\work$
Let $G$ be a finite group and $\pi: G\to \sym(G)$ the Cayley representation.

> (Recall that this means that for an element $x\in G$, $\pi(x)$ acts by left translation on $G$.)

Prove that $\pi(x)$ is an odd permutation $\iff$ the order $\abs{\pi(x)}$ of $\pi(x)$ is even and $\abs{G} / \abs{\pi(x)}$ is odd.

## Fall 2016 #1 $\work$
Let $G$ be a finite group and $s, t\in G$ be two distinct elements of order 2.
Show that subgroup of $G$ generated by $s$ and $t$ is a dihedral group.

> Recall that the dihedral groups of order $2m$ for $m\geq 2$ are of the form
\[
D_{2m} = \gens{\sigma, \tau \suchthat \sigma^m = 1 = \tau^2, \tau \sigma = \sigma\inv \tau}
.\]

## Fall 2015 #1 $\work$
Let $G$ be a group containing a subgroup $H$ not equal to $G$ of finite index.
Prove that $G$ has a normal subgroup which is contained in every conjugate of $H$ which is of finite index.

## Spring 2015 #1 $\work$
For a prime $p$, let $G$ be a finite $p\dash$group and let $N$ be a normal subgroup of $G$ of order $p$.
Prove that $N$ is contained in the center of $G$.

## Fall 2014 #6 $\work$
Let $G$ be a group and $H, K < G$ be subgroups of finite index.
Show that
\[
[G: H\intersect K] \leq [G: H] ~ [G:K]
.\]

## Spring 2013 #3 $\work$
Let $P$ be a finite $p\dash$group.
Prove that every nontrivial normal subgroup of $P$ intersects the center of $P$ nontrivially.

## Fall 2019 Midterm #1  $\work$
Let $G$ be a group of order $p^2q$ for $p, q$ prime. Show that $G$ has a nontrivial normal subgroup.

## Fall 2019 Midterm #4 $\work$
Let $p$ be a prime. Show that $S_p = \gens{\tau, \sigma}$ where $\tau$ is a transposition and $\sigma$ is a $p\dash$cycle.

## Fall 2019 Midterm #5 $\work$
Let $G$ be a nonabelian group of order $p^3$ for $p$ prime. Show that $Z(G) = [G, G]$.

> Note: this is a good problem, it tests several common theorems at once.
> Proof due to Paco Adajar.

:::{.concept}
\envlist

Important notations and definitions:

-   The **center** of $G$, denoted by $Z(G)$, is the subset of elements
    of $G$ which commute with all elements of $G$. That is, if
    $x \in Z(G)$, then for all $g \in G$, $gx = xg$:
    $$Z(G) = \{ x \in G : gx = xg \, \text{for all } x \in G \}.$$

    In fact, $Z(G)$ is not just a subset of $G$, but a normal subgroup
    of $G$.

-   The **commutator subgroup** of $G$, denoted by $[G, G]$, is the
    subgroup of $G$ generated by the commutators of $G$, i.e., the
    elements of the form $ghg^{-1}h^{-1}$:
    $$[G, G] = \langle ghg^{-1}h^{-1} : g, h \in G \rangle.$$

    The commutator subgroup $[G,G]$ is the smallest normal subgroup of
    $G$ whose quotient is abelian. That is, if $H$ is a normal subgroup
    of $G$ for which $G/H$ is abelian, then $[G, G] \le H$.

    Moreover, $G$ is abelian if and only if $[G,G]$ is trivial.

Theorems to remember and know how to prove:

-   **$G/Z(G)$ Theorem**: If $G/Z(G)$ is cyclic, then $G$ is abelian,
    i.e., $G/Z(G)$ is in fact trivial.

-   **Lagrange's Theorem**: If $G$ is a group of finite order and $H$ is
    a subgroup of $G$, then the order of $H$ divides that of $G$.

    - One consequence of this is that every group of prime order is
    cyclic.

-   A $p$-group (a group of order $p^n$ for some prime $p$ and
    some positive integer $n$) has nontrivial center.

-   A consequence of the theorems above: every group of order $p^2$
    (where $p$ is prime) is abelian.

:::


:::{.solution}
Since $Z(G)$ is a subgroup of $G$ and $|G| = p^3$, by Lagrange's
theorem, $|Z(G)| \in \{1, p, p^2, p^3\}$.

Since we stipulated that $G$ is nonabelian, $|Z(G)| \ne p^3$. Also,
since $G$ is a $p$-group, it has nontrivial center, so $|Z(G)| \ne 1$.
Finally, by the $G/Z(G)$ theorem, $|Z(G)| \ne p^2$: if $|Z(G)| = p^2$,
then $|G/Z(G)| = p$ and so $G/Z(G)$ would be cyclic, meaning that $G$ is
abelian. Hence, $|Z(G)| = p$.

Then, since $|Z(G)| = p$, we have that $|G/Z(G)| = p^2$, and so $G/Z(G)$
is abelian. Thus, $[G, G] \in Z(G)$. Since $|Z(G)| = p$, then
$|[G,G]| \in \{ 1, p\}$ again by Lagrange's theorem. If $|[G,G]| = p$
then $[G,G] = Z(G)$ and we are done. And, indeed, we must have
$|[G,G]| = p$, because $G$ is nonabelian and so $|[G,G]| \ne 1$.
:::


## Spring 2021 #2 $\done$

Let $H \normal G$ be a normal subgroup of a finite group $G$, where the order of $H$ is the smallest prime $p$ dividing $\abs{G}$.
Prove that $H$ is contained in the center of $G$.

> Solution due to Swaroop Hegde.

:::{.concept}
\envlist

1. Normal subgroups are disjoint unions of (some) conjugacy classes in $G$.
  - In fact, this is a characterization of normal subgroups (i.e. $H$ is normal iff a union of conjugacy classes).
2. Orbit stabilizer theorem: $\# C_g = \# G/ \# K_g$ where $C_g$ is the centralizer and $K_g$ is the conjugacy class of $g$.
  In particular, $\# C_g$ divides $\#G$.
3. $x\in Z(G)$ iff $\# C_x = 1$, i.e. the size of its conjugacy class is one.
:::

:::{.proof title="?"}
\envlist

- Let $p \da \#H$.
- Let \( \ts{ C_i }_{i\leq n} \) be the conjugacy classes in $G$, then $G = \disjoint_{i\leq n} C_i$
- By the first fact, there is a sub-collection \( \ts{ C_{i_j}}_{j\leq k } \)  such that 
\[
H = \disjoint_{j\leq k} C_{i_j}
.\]
- The identity is always in a single conjugacy class, so $C_e = \ts{ e }$.
- Since $e\in H$, without loss of generality, label $C_{i_1} = \ts{ e }$.
- So
\[
H 
= \disjoint_{j\leq k} C_{i_j} 
= C_{i_1}{\textstyle  \coprod} \displaystyle\Disjoint_{\substack{ j\leq k \\ j\neq 1} } C_{i_j} 
.\]

- Take cardinality in the above equation 
\[
p = 1 + \sum_{\substack{ j\leq k \\ j\neq 1 }} \# C_{i_j}
.\]
- So $\# C_{i_j} \leq p-1$ for all $j\neq 1$.

- Every $\# C_{i_j}$ divides $\# G$, but $p$ was the *minimal* prime dividing $\# G$, forcing $\# C_{i_j} = 1$ for all $j \neq 1$.
  - This rules out $\# C_{i_j}$ being a prime less than $p$, but also rules out composites: if a prime $q\divides \# C_{i_j}$, then $q<p$ and $q\divides \# G$, a contradiction.

- By fact 3, each $x\in C_{i_j}$ satisfies $x\in Z(G)$.

- $\union C_{i_j} = H$, so $H \subseteq Z(G)$.

:::

