# Group Theory: General

## Spring 2020 #2 $\done$
Let $H$ be a normal subgroup of a finite group $G$ where the order of $H$ and the index of $H$ in $G$ are relatively prime.
Prove that no other subgroup of $G$ has the same order as $H$.

\todo[inline]{Work this problem.}


:::{.concept}
\envlist

- Normal subgroups are disjoint unions of (some) conjugacy classes in $G$.
  - In fact, this is a characterization of normal subgroups (i.e. $H$ is normal iff a union of conjugacy classes).
- Orbit stabilizer theorem: $\# C_g = \# G/ \# K_g$ where $C_g$ is the centralizer and $K_g$ is the conjugacy class of $g$.
  In particular, $\# C_g$ divides $\#G$.
- $x\in Z(G)$ iff $\# C_x = 1$, i.e. the size of its conjugacy class is one.
:::


:::{.proof title="due to Swaroop"}
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
- So $\# C_{i_j} \leq p-1$ for all $j$.

- Every $\# C_{i_j}$ divides $\# G$, but $p$ was the *minimal* prime dividing $\# G$, forcing $\# C_{i_j} = 1$ for all $j \geq 2$.

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

:::{.concept}
\envlist

- Notation: $X/G$ is the set of $G\dash$orbits
- Notation: $X^g = \theset{x\in x\suchthat g\cdot x = x}$
- Burnside's formula: $\abs G \abs{X/G} = \sum \abs {X^g}$.
:::

:::{.strategy}
Burnside.

:::


:::{.solution}
\envlist

:::{.proof title="Part a"}
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

:::

:::{.proof title="Part b"}
Statement of the class equation:
\[
\abs G = Z(G) + \sum_{\substack{\text{One $x$ from each} \\ \text{conjugacy class}}}[G: Z(x)]
\]
where $Z(x) = \theset{g\in G \suchthat [g, x] = 1}$.
:::


:::{.proof title="Part c"}
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

## Spring 2021 #2 $\work$

Let $H \normal G$ be a normal subgroup of a finite group $G$, where the order of $H$ is the smallest prime $p$ dividing $\abs{G}$.
Prove that $H$ is contained in the center of $G$.
