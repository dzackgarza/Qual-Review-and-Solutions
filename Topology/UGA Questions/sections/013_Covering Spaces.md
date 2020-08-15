# Covering Spaces

## 1 (Spring 11/Spring '14) $\done$

### a  
Give the definition of a **covering space** $\hat{X}$
(and **covering map** $p : \hat{X} \to X$) for a topological space $X$.

### b  
State the homotopy lifting property of covering spaces. 
Use it to show that a covering map $p : \hat{X} \to X$ induces an injection 
$$
p^\ast : \pi_1 (\hat{X}, \hat{x}) \to \pi_1 (X, p(\hat{x}))
$$ 
on fundamental groups.

### c
Let $p : \hat{X} \to X$ be a covering map with $Y$ and $X$ path-connected. 
Suppose that the induced map $p^\ast$ on $\pi_1$ is an isomorphism. 

Prove that $p$ is a homeomorphism.

\todo[inline]{Not done?}
:::{.solution}
\hfill
:::{.concept}
\hfill

:::

### a 
\todo[inline]{Todo}.

### b

Homotopy lifting property:

\begin{center}
\begin{tikzcd}
                                                                   &  & \tilde X \arrow[dd, "\pi"] \\
                                                                   &  &                            \\
Y\cross I \arrow[rr, "H"] \arrow[rruu, "\exists \tilde H", dashed] &  & X                         
\end{tikzcd}
\end{center}

$\pi$ clearly induces a map $p_*$ on $\pi_1$ by functoriality, so we'll show that $\ker p_*$ is trivial.
Let $\gamma: S^1 \to \tilde X \in \pi_1(\tilde X)$ and suppose $\alpha \definedas p_*(\gamma) = [e] \in \pi_1(X)$. 
We'll show $\gamma \homotopic [e]$ in $\pi_1(\tilde X)$.


Since $\alpha = [e]$, $\alpha \homotopic \const$ and thus there is a homotopy $H: I\cross S^1 \to X$ such that $H_0 = \const(x_0)$ and $H_1 = \gamma$.
By the HLP, this lifts to $\tilde H: I\cross S^1 \to \tilde X$.
Noting that $\pi\inv(\const(x_0))$ is still a constant loop, this says that $\gamma$ is homotopic to a constant loop and thus nullhomotopic. 

### c

Since both spaces are path-connected, the degree o the covering map $\pi$ is precisely the index of the included fundamental group.
This forces $\pi$ to be a degree 1 covering and hence a homeomorphism.
:::


## 2 (Fall '06/Fall '09/Fall '15) $\work$

### a 
Give the definitions of **covering space** and **deck transformation** (or covering transformation).

### b 
Describe the universal cover of the Klein bottle and its group of deck transformations.

### c 
Explicitly give a collection of deck transformations on $$\theset{(x, y) \mid -1 \leq x \leq 1, -\infty < y < \infty}$$ such that the quotient is a Möbius band.

### d
Find the universal cover of $\RP^2 \times S^1$ and explicitly describe its group of deck transformations.

## 3 (Spring '06/Spring '07/Spring '12) $\work$

### a
What is the definition of a **regular** (or Galois) covering space?

### b
State, without proof, a criterion in terms of the fundamental group for a covering map $p : \tilde X \to X$ to be regular.

### c  
Let $\Theta$ be the topological space formed as the union of a circle and its diameter (so this space looks exactly like the letter $\Theta$). 
Give an example of a covering space of $\Theta$ that is not regular.

## 4 (Spring '08) $\work$
Let $S$ be the closed orientable surface of genus 2 and let $C$ be the commutator subgroup of $\pi_1 (S, \ast)$. Let $\tilde S$ be the cover corresponding to $C$. 
Is the covering map $\tilde S \to S$ regular? 

> The term "normal" is sometimes used as a synonym for regular in this context.

What is the group of deck transformations?

Give an example of a nontrivial element of $\pi_1 (S, \ast)$ which lifts to a trivial deck transformation.

## 5 (Fall '04) $\work$
Describe the 3-fold connected covering spaces of $S^1 \lor S^1$.

## 6 (Spring '17) $\done$
Find all three-fold covers of the wedge of two copies of $\RP^2$ .
Justify your answer.

:::{.solution}
\hfill
:::{.concept}
\hfill

:::
Note $\pi_1 \RP^2 = \ZZ/2\ZZ$, so $\pi_1 X = (\ZZ/2\ZZ)^2$.

The pullback of any neighborhood of the basepoint needs to be locally homeomorphic to one of

- $S^2 \vee S^2$
- $\RP^2 \vee S^2$

And so *all* possibilities for regular covering spaces are given by

- $\bigvee^{2k} S^2$ "beads" wrapped into a necklace for any $k \geq 1$
- $\RP^2 \vee (\bigvee^k S^2) \vee \RP^2$
- $\vee^\infty S^2$, the universal cover


To get a threefold cover, we want the basepoint to lift to three preimages, so we can take

- $S^2 \vee S^2 \vee S^2$ wrapped
- $\RP^2 \vee S^2 \vee \RP^2$.


:::


## 7 (Fall '17) $\done$
Describe, as explicitly as you can, two different (non-homeomorphic) connected two-sheeted covering spaces of $\RP^2 \lor \RP^3$, and prove that they are not homeomorphic.

\todo[inline]{Expand solution.}
:::{.solution}
\hfill
:::{.concept}
\hfill

:::
- $\RP_3 \vee S^2 \vee \RP^3$, which has $\pi_2 = 0 \ast \ZZ \ast 0 = \ZZ$ since $\pi_{i\geq 1} X = \pi_{i\geq 1}\tilde X$ and $\tilde \RP^3 = S^3$.
- $\RP^2 \vee S^3 \vee \RP^2$, which has $\pi_2 = \ZZ \ast 0 \ast \ZZ = \ZZ\ast \ZZ \neq \ZZ$
:::


## 8 (Spring '19) $\done$
Is there a covering map from
$$
X_3 = \theset{x^2 + y^2 = 1} \cup \theset{(x - 2)^2 + y^2 = 1} \cup \theset{(x + 2)^2 + y^2 = 1} \subset \RR^2
$$ 
to $S^1 \vee S^1$? 
If there is, give an example; if not, give a proof.

:::{.solution}
\hfill
:::{.concept}
\hfill

:::
Yes,

![Image](figures/2020-02-04-21:50.png)
:::


## 9 (Spring '05) $\work$

a.  Suppose $Y$ is an $n$-fold connected covering space of the torus $S^1 \times S^1$. 
    Up to homeomorphism, what is $Y$? Justify your answer.

b.  Let $X$ be the topological space obtained by deleting a disk from a torus.
    Suppose $Y$ is a 3-fold covering space of $X$. 
    
    What surfaces could $Y$ be?
    Justify your answer, but you need not exhibit the covering maps explicitly.

## 10 (Spring '07) $\work$

Let $S$ be a connected surface, and let $U$ be a connected open subset of $S$. 
Let $p : \tilde S \to  S$ be the universal cover of $S$. 
Show that $p\inv (U )$ is connected if and only if the homeomorphism $i_\ast : \pi_1 (U ) \to \pi_1 (S)$ induced by the inclusion $i : U \to S$ is onto.

## 11 (Fall '10) $\work$
Suppose that X has universal cover $p : \tilde X \to X$ and let $A \subset X$ be a subspace with $p(\tilde a) = a \in A$. 
Show that there is a group isomorphism 
$$
\ker(\pi_1 (A, a) \to \pi_1 (X, a)) \cong \pi_1 (p\inv A, \bar a)
.$$

## 12 (Fall '14) $\work$
Prove that every continuous map $f : \RP^2 \to S^1$ is homotopic to a constant. 

> Hint: think about covering spaces.

## 13 (Spring '16) $\work$
Prove that the free group on two generators contains a subgroup isomorphic to the free group on five generators by constructing an appropriate covering space of $S^1 \lor S^1$.

## 14 (Fall '12) $\work$
Use covering space theory to show that $\ZZ_2 \ast \ZZ$  (that is, the free product of $\ZZ_2$ and $\ZZ$)  has two subgroups of index 2 which are not isomorphic to each other.

## 15 (Spring '17) $\work$

### a
Show that any finite index subgroup of a finitely generated free group is free. 
State clearly any facts you use about the fundamental groups of graphs.

### b  
Prove that if $N$ is a nontrivial normal subgroup of infinite index in a finitely generated free group $F$ , then $N$ is not finitely generated.

## 16 (Spring '19) $\work$
Let $p : X \to Y$ be a covering space, where $X$ is compact, path-connected, and locally path-connected. 

Prove that for each $x \in X$ the set $p\inv (\theset{p(x)})$ is finite, and has cardinality equal to the index of $p_* (\pi_1 (X, x))$ in $\pi_1 (Y, p(x))$.


