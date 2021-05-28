# Miscellaneous Algebraic Topology

## 1 (Fall '14) $\work$ 
Prove that $\RR^2$ is not homeomorphic to $\RR^n$ for $n > 2$.

## 2 (Spring '12) $\work$ 
Prove that any finite tree is contractible, where a **tree** is a connected graph that contains no closed edge paths.

## 3 (Spring '13) $\done$
Show that any continuous map $f : \RP^2 \to S^1 \times S^1$ is necessarily null-homotopic.

:::{.solution}
\hfill
:::{.concept}
\hfill
- Two techniques: 
  - Show $f_* = 0$ 
  - Lift to a contractible universal cover.
:::

- Any continuous map $\RP^2 \mapsvia{f} S^1\cross S^1$ induces a group morphism $\pi_1 \RP^2 \mapsvia{f_*} \pi_1(S^1\cross S^1)$
- Identify $\pi_1 \RP^2 = \ZZ/2\ZZ$ and $\pi_1(S^1\cross S^1) = \pi_1 S^1 \cross \pi_1 S^1 = \ZZ^2$.
- But as a $\ZZ\dash$module morphism, $f_*$ will preserve torsion submodules, and since $\ZZ^2$ is free we must have $f_* = 0$.

- Lemma: $f_* = 0$ implies $f$ is nullhomotopic. 
\todo[inline]{Why? What is the homotopy?}
  - Note that $\widetilde{S^1\cross S^1} = \RR^2$.
:::

## 4 (Fall '11) $\done$
Prove that, for $n \geq 2$, every continuous map $f: \RP^n \to S^1$ is null-homotopic.

:::{.solution}
\hfill
:::{.concept}
\hfill

:::
- Any continuous map $\RP^n \mapsvia{f} S^1$ induces a group morphism $\pi_1\RP^n \mapsvia{f_*} \pi_1S^1$
- Identify $\pi_1\RP^n = \ZZ/2\ZZ$ and $\pi_1S^1 = \ZZ$ to obtain a group morphism $f_*: \ZZ/2\ZZ \to \ZZ$.
- Claim: $f_* = 0$.
  - Recognizing this as a map of $\ZZ\dash$modules, we must have
  \[  
  0 = [2]_2 = 2\cdot [1]_2  \implies 0 = f_*(0) = 2\cdot f_*([1]_2)
  .\]
    since $\ZZ\dash$module maps send 0 to 0.

  - But no element of the image $\ZZ$ is annihilated by $2$, so $f_*$ can only be the zero map.

- But then $f$ is nullhomotopic.

- Lemma: $f_* = 0$ implies $f$ is nullhomotopic. 
\todo[inline]{Why?}

:::

## 5 (Spring '06) $\work$ 
Let $S^2 \to \RP^2$ be the universal covering map. 

Is this map null-homotopic? 
Give a proof of your answer.

## 6 (Spring '17) $\done$
Suppose that a map $f : S^3 \times S^3 \to \RP^3$ is not surjective. 

Prove that $f$ is homotopic to a constant function.

\todo[inline]{Lost, redo.}


## 7 (Fall '06) $\work$ 
Prove that there does not exist a continuous map $f : S^2 \to S^2$ from the unit sphere in $\RR^3$ to itself such that $f (\vector x) \perp \vector x$ 
(as vectors in $\RR^3$ for all $\vector x \in S^2$).

## 8 (Spring '08) $\work$ 
Let $f$ be the map of $S^1 \times [0, 1]$ to itself defined by
$$
f (e^{i\theta} , s) = (e^{i(\theta+2\pi s)} , s)
,$$ 
so that $f$ restricts to the identity on the two boundary circles of $S^1 \times [0, 1]$. 

Show that $f$ is homotopic to the identity by a homotopy $f_t$ that is stationary on one of the boundary circles, but not by any homotopy that is stationary on both boundary circles. 

> Hint: Consider what $f$ does to the path $s \mapsto (e^{i\theta_0} , s)$ for fixed $e^{i\theta_0} \in S^1$.

## 9 (Spring '17) $\work$ 
Show that $S^1 \times S^1$ is not the union of two disks (where there is no assumption that the disks intersect along their boundaries).

## 10 (Spring '14) $\work$ 
Suppose that $X \subset Y$ and $X$ is a deformation retract of $Y$. 

Show that if $X$ is a path connected space, then $Y$ is path connected.

## 11 (Spring '05) $\work$ 
Do one of the following:

a. Give (with justification) a contractible subset $X \subset \RR^2$ which is not a retract of $\RR^2$ .

b. Give (with justification) two topological spaces that have the same homology groups but that are not homotopy equivalent.

## 12 (Spring '16) $\work$ 
Recall that the **suspension** of a topological space, denoted $SX$, is the quotient space formed from $X \times [-1, 1]$ by identifying $(x, 1)$ with $(y, 1)$ for all $x, y \in X$, and also identifying $(x, -1)$ with $(y, -1)$ for all $x, y \in X$.

a. Show that $SX$ is the union of two contractible subspaces.

b. Prove that if $X$ is path-connected then $\pi_1 (SX) = \theset{0}$.

c. For all $n \geq 1$, prove that $H_{n} (X) \cong H_{n+1} (SX)$.
