# Groups: Group Actions

## Fall 2012 #1 $\work$
Let $G$ be a finite group and $X$ a set on which $G$ acts.

a.
Let $x\in X$ and $G_x \definedas \theset{g\in G \suchthat g\cdot x = x}$. 
Show that $G_x$ is a subgroup of $G$.

b.
Let $x\in X$ and $G\cdot x \definedas \theset{g\cdot x \suchthat g\in G}$.
Prove that there is a bijection between elements in $G\cdot x$ and the left cosets of $G_x$ in $G$.

## Fall 2015 #2 $\work$
Let $G$ be a finite group, $H$ a $p\dash$subgroup, and $P$ a sylow $p\dash$subgroup for $p$ a prime.
Let $H$ act on the left cosets of $P$ in $G$ by left translation.

Prove that this is an orbit under this action of length 1.

Prove that $xP$ is an orbit of length 1 $\iff H$ is contained in $xPx\inv$.

## Spring 2016 #5 $\work$
Let $G$ be a finite group acting on a set $X$.
For $x\in X$, let $G_x$ be the stabilizer of $x$ and $G\cdot x$ be the orbit of $x$.

a.
Prove that there is a bijection between the left cosets $G/G_x$ and $G\cdot x$.

b.
Prove that the center of every finite $p\dash$group $G$ is nontrivial by considering that action of $G$ on $X=G$ by conjugation.

## Fall 2017 #1 $\work$
Suppose the group $G$ acts on the set $A$. 
Assume this action is faithful (recall that this means that the kernel of the homomorphism from $G$ to $\sym(A)$ which gives the action is trivial) and transitive (for all $a, b$ in $A$, there exists $g$ in $G$ such that $g \cdot a = b$.)

a.
For $a \in A$, let $G_a$ denote the stabilizer of $a$ in $G$. 
Prove that for any $a \in A$, 
$$
\Intersect_{\sigma\in G} \sigma G_a \sigma\inv = \theset{1}
.$$

b.
Suppose that $G$ is abelian. Prove that $|G| = |A|$. Deduce that every abelian transitive subgroup of $S_n$ has order $n$.

## Fall 2018 #2 $\done$

a.
Suppose the group $G$ acts on the set $X$ . Show that the stabilizers of elements in the same orbit are conjugate.

b.
Let $G$ be a finite group and let $H$ be a proper subgroup. Show that the union of the conjugates of $H$ is strictly smaller than $G$, i.e.
\[
\Union_{g\in G} gHg\inv \subsetneq G
\]

c.
Suppose $G$ is a finite group acting transitively on a set $S$ with at least 2 elements. Show that there is an element of $G$ with no fixed points in $S$.

:::{.concept}
\envlist

- Orbit: $G\cdot x \definedas \theset{g\cdot x \suchthat g\in G} \subseteq X$
- Stabilizer: $G_x \definedas \theset{g\in G\suchthat g\cdot x = x} \leq G$
- Orbit-Stabilizer: $G\cdot x \simeq G/G_x$.
- $abc\in H \iff b\in a\inv H c\inv$
- Set of orbits for $G\actson X$, notated $X/G$.
- Set of fixed points for $G\actson X$, notated $X^g$.
- Burnside's Lemma: $\abs{X/G} \cdot \abs{G} = \sum_{g\in G} \abs{X^g}$ 
  - Number of orbits equals average number of fixed points.

:::

:::{.solution}
\envlist

:::{.proof title="of a"}
\envlist

- Fix $x$, then $y\in \Orb(x) \implies g\cdot x = y$ for some $g$, and $x = g\inv \cdot y$.
- Then
\[
h \in \Stab(x)
&\iff h\cdot x = x && \text{by being in the stabilizer} \\
&\iff h\cdot (g\inv \cdot y) = g\inv \cdot y \\
&\iff (g h g\inv) \cdot y = y \\
&\iff ghg\inv \in G_y && \text{by definition}\\
&\iff h\in g ^{-1}  \Stab(y) g
,\]
so $\Stab(x) = g\inv \Stab(y) g$.

:::

:::{.proof title="of b"}
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
\abs{\Union_{g\in G}gHg\inv} 
&< (\text{Number of Conjugates of } H) \cdot (\text{Size of each conjugate}) \\ 
& \text{strictly overcounts since they intersect in at least the identity} \\
&= [G: N_G(H)] \abs{H} \\
&= {\abs{G} \over \abs{N_G(H)}} \abs{H} \\
& \text{since $G$ is finite} \\
&\leq {\abs G \over \abs H} \abs H \\
&= \abs{G}
.\]

:::

:::{.proof title="of c"}
\envlist

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

:::

