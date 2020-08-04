# Cell Complexes and "Attaching Map" Spaces

## 1 (Fall '07). 
Describe a cell complex structure on the torus $T = S^1 \times S^1$ and use
this to compute the homology groups of $T$. 

> To justify your answer you will need to consider the attaching maps in detail.

## 2 (Fall '04). 
Let $X$ be the space formed by identifying the boundary of a
Möbius band with a meridian of the torus $T^2$. 

Compute $\pi_1 (X)$ and $H_* (X)$.

## 3 (Spring '06). 
Compute the homology of the space $X$ obtained by attaching a Möbius band to $\RP^2$ via a homeomorphism of its boundary circle to the standard $\RP^1$ in $\RP^2$.

## 4 (Spring '14). 
Let $X$ be a space obtained by attaching two 2-cells to the torus $S^1 \times S^1$, one along a simple closed curve $\theset{x} \times S^1$ and the other along $\theset{y} \times S^1$ for two points $x \neq y$ in $S^1$ .

a. Draw an embedding of $X$ in $\RR^3$ and calculate its fundamental group.

b. Calculate the homology groups of $X$.

## 5 (Fall '07). 
Let $X$ be the space obtained as the quotient of a disjoint union of a 2-sphere $S^2$ and a torus $T = S^1 \times S^1$ by identifying the equator in $S^2$ with a circle $S^1 \times \theset{p}$ in $T$. 

Compute the homology groups of $X$.

## 6 (Spring '06). 
Let $X = S^2 / \theset{p_1 = \cdots = p_k }$ be the topological space obtained from the 2-sphere by identifying $k$ distinct points on it ($k \geq 2$).

Find:

a. The fundamental group of $X$.

b. The Euler characteristic of $X$.

c. The homology groups of $X$.

## 7 (Fall '16). 
Let $X$ be the topological space obtained as the quotient of the sphere $S^2 = \theset{\vector x \in \RR^3 \suchthat \norm{\vector x} = 1}$ under the equivalence relation $\vector x \sim -\vector x$ for $\vector x$ in the equatorial circle, i.e. for $\vector x = (x_1, x_2, 0)$. 

Calculate $H_* (X; \ZZ)$ from a CW complex description of $X$.

## 8 (Fall '17).
Compute, by any means available, the fundamental group and all the homology groups of the space obtained by gluing one copy $A$ of $S^2$ to another copy $B$ of $S^2$ via a two-sheeted covering space map from the equator of $A$ onto the equator of $B$.

## 9 (Spring '14). 
Use cellular homology to calculate the homology groups of $S^n \times S^m$.

## 10 (Fall '09/Fall '12). 
Denote the points of $S^1 \times I$ by $(z, t)$ where $z$ is a unit complex number and $0 \leq t \leq 1$. 
Let $X$ denote the quotient of $S^1 \times I$ given by identifying $(z, 1)$ and $(z_2 , 0)$ for all $z \in S^1$. 

Give a cell structure, with attaching maps, for $X$, and use it to compute $\pi_1 (X, \ast)$ and $H_1 (X)$.

## 11 (Spring '15). 
Let $X = S_1 \cup S_2 \subset \RR^3$ be the union of two spheres of radius 2, one about $(1, 0, 0)$ and the other about $(-1, 0, 0)$, i.e. 
\begin{align*}
S_1 &= \theset{(x, y,z) \mid (x-1)^2 + y^2 +z^2 = 4} \\
S_2 &= \theset{(x, y, z) \mid (x + 1)^2 + y^2 + z^2 = 4}
.\end{align*}

a. Give a description of $X$ as a CW complex.

b. Write out the cellular chain complex of $X$.

c. Calculate $H_* (X; Z)$.

## 12 (Spring '06). 
Let $M$ and $N$ be finite CW complexes.

a. Describe a cellular structure of $M \times N$ in terms of the cellular structures of $M$ and $N$.

b. Show that the Euler characteristic of $M \times N$ is the product of the Euler characteristics of $M$ and $N$.

## 13 (Spring '07). 
Suppose the space $X$ is obtained by attaching a 2-cell to the torus $S^1 \times S^1$.

In other words, $X$ is the quotient space of the disjoint union of the closed disc $\DD^2$ and the torus $S^1 \times S^1$ by the identification $x \sim f(x)$ where $S^1$ is the boundary of the unit disc and $f : S^1 \to S^1 \times S^1$ is a continuous map.

What are the possible homology groups of $X$? 
Justify your answer.

## 14 (Spring '15). 
Let $X$ be the topological space constructed by attaching a closed 2-disk $\DD^2$ to the circle $S^1$ by a continuous map $\partial\DD^2 \to S^1$ of degree $d > 0$ on the boundary circle.

a.  Show that every continuous map $X \to X$ has a fixed point.

b.  Explain how to obtain all the connected covering spaces of $X$.

## 15 (Spring '11). 
Let $X$ be a topological space obtained by attaching a 2-cell to $\RP^2$ via some map $f: S^1 \to \RP^2$ . 

What are the possibilities for the homology $H_* (X; Z)$?

## 16 (Spring '12). 
For any integer $n \geq 2$ let $X_n$ denote the space formed by attaching a 2-cell to the circle $S^1$ via the attaching map 
\begin{align*}
a_n: S^1 &\to S^1 \\
e^{i\theta} &\mapsto e^{in\theta}
.\end{align*}

a.  Compute the fundamental group and the homology of $X_n$.

b.  Exactly one of the $X_n$ (for $n \geq 2$) is homeomorphic to a surface. 
    Identify, with proof, both this value of $n$ and the surface that $X_n$ is homeomorphic to (including a description of the homeomorphism).

## 17 (Spring '09). 
Let $X$ be a CW complex and let $\pi : Y \to X$ be a covering space.

a. Show that $Y$ is compact iff $X$ is compact and $\pi$ has finite degree.

b.  Assume that $\pi$ has finite degree $d$. 
    Show show that $\chi (Y ) = d \chi (X)$.

c.  Let $\pi :\RP^N \to X$ be a covering map. 
    Show that if $N$ is even, $\pi$ is a homeomorphism.

## 18 (Spring '18). 
For topological spaces $X, Y$ the **mapping cone** $C(f )$ of a map $f : X \to Y$ is defined to be the quotient space 
\begin{align*}
(X \times [0, 1])\disjoint Y / \sim &\qtext{where}  \\ 
(x, 0) &\sim (x', 0) \qtext{for all} x, x' \in X \text{ and } \\ 
(x, 1) &\sim f (x) \qtext{for all } x \in X
.\end{align*}


Let $\phi_k : S^n \to S^n$ be a degree $k$ map for some integer $k$. 

Find $H_i(C(\phi_k ))$ for all $i$.

## 19 (Fall '18). 
Prove that a finite CW complex must be Hausdorff.

# Surfaces

## 1 (Fall '05). 
State the classification theorem for surfaces (compact, without boundary, but not necessarily orientable). 
For each surface in the classification, indicate the structure of the first homology group and the value of the Euler characteristic. 

Also, explain briefly how the 2-holed torus and the connected sum $\RP^2 \# \RP^2$ fit into the classification.

## 2 (Spring '16). 
Give a list without repetitions of all compact surfaces (orientable or non-orientable and with or without boundary) that have Euler characteristic negative one. 

Explain why there are no repetitions on your list.

## 3 (Spring '07). 
Describe the topological classification of all compact connected surfaces $M$ without boundary having Euler characteristic $\chi(M )\geq -2$. 

No proof is required.

## 4 (Spring '09). 
How many surfaces are there, up to homeomorphism, which are: 

- Connected, 
- Compact, 
- Possibly with boundary, 
- Possibly nonorientable, and 
- With Euler characteristic -3? 

Describe one representative from each class.

## 5 (Fall '13). 
Prove that the Euler characteristic of a compact surface with boundary which has $k$ boundary components is less than or equal to $2 - k$.

## 6 (Spring '13). 
What surface is represented by the $6\dash$gon with edges identified according to the symbol $xyzxy\inv z\inv$ ?

## 7 (Spring '15). 
Let $X$ be the topological space obtained as the quotient space of a regular $2n\dash$gon ($n \geq 2$) in $\RR^2$ by identifying opposite edges via translations in the plane. 

First show that X is a compact, orientable surface without boundary, and then identify its genus as a function of $n$.

## 8 (Fall '10).
a.  Show that any compact connected surface with nonempty boundary is homotopy equivalent to a wedge of circles 

    > Hint: you may assume that any compact connected surface without boundary is given by identifying edges of a polygon in pairs.

b.  For each surface appearing in the classification of compact surfaces with nonempty boundary, say how many circles are needed in the wedge from part (a). 

    > Hint: you should be able to do this even if you have not done part (a).

## 9 (Fall '04). 
Let $M_g^2$ be the compact oriented surface of genus $g$. 

Show that there exists a continuous map $f : M_g^2 \to S^2$ which is not homotopic to a constant map.

## 10 (Spring '11) 
Show that $\RP^2 \lor S^1$ is *not* homotopy equivalent to a compact surface (possibly with boundary).

## 11 (Fall '14). 
Identify (with proof, but of course you can appeal to the classification of surfaces) all of the compact surfaces without boundary that have a cell decomposition having exactly one 0-cell and exactly two 1-cells (with no restriction on the number of cells of dimension larger than 1).

## 12 (Fall '11). 
For any natural number $g$ let $\Sigma_g$ denote the (compact, orientable) surface of genus $g$. 

Determine, with proof, all valued of $g$ with the property that there exists a covering space $\pi : \Sigma_5 \to \Sigma_g$ . 

> Hint: How does the Euler characteristic behave for covering spaces?

## 13 (Spring '14). 
Find *all* surfaces, orientable and non-orientable, which can be covered by a closed surface (i.e. compact with empty boundary) of genus 2. 
Prove that your answer is correct.

## 14 (Spring '18).
a. Write down (without proof) a presentation for $\pi_1 (\Sigma_2 , p)$ where $\Sigma_2$ is a closed, connected, orientable genus 2 surface and $p$ is any point on $\Sigma_2$ .

b.  Show that $\pi_1 (\Sigma_2 , p)$ is not abelian by showing that it surjects onto a free group of rank 2.

c.  Show that there is no covering space map from $\Sigma_2$ to $S^1 \times S^1$ . 
    You may use the fact that $\pi_1 (S^1 \times S^1 ) \cong \ZZ^2$ together with the result in part (b) above.

## 15 (Fall '16). 
Give an example, with explanation, of a closed curve in a surfaces which is not nullhomotopic but is nullhomologous.

## 16 (Fall '17). 
Let $M$ be a compact orientable surface of genus $2$ without boundary. 

Give an example of a pair of loops $$\gamma_0 , \gamma_1 : S^1 \to M$$ with $\gamma_0 (1) = \gamma_1 (1)$ such that there is a continuous map $\Gamma: [0, 1] \times S^1 \to M$ such that 
$$
\Gamma(0, t) = \gamma_0 (t), \quad \Gamma(1, t) = \gamma_1 (t) \qtext{for all} t \in S^1
,$$ 
but such that there is no such map $\Gamma$ with the additional property that $\Gamma_s (1) = \gamma_0 (1)$ for all $s \in [0, 1]$.

(You are not required to prove that your example satisfies the stated property.)

## 17 (Fall '18). 
Let $C$ be cylinder. 
Let $I$ and $J$ be disjoint closed intervals contained in $\partial C$. 

What is the Euler characteristic of the surface $S$ obtained by identifying $I$ and $J$? 

Can all surface with nonempty boundary and with this Euler characteristic be obtained from this construction?

## 18 (Spring '19). 
Let $\Sigma$ be a compact connected surface and let  $p_1, \cdots , p_k \in \Sigma$.

Prove that $H_2 \qty{\Sigma \setminus \union_{i=1}^k {p_i} } = 0$.

# Fixed points

## 1 (Fall '14). 
Prove that, for every continuous map $f : B^2 \to B^2$, there is a point $x$ such that $f (x) = x$. 

> This is the $n = 2$ case of the Brouwer fixed point theorem; your proof shouldn't appeal to either of the Brouwer or the Lefschetz fixed point theorems.

## 2 (Spring '18). 
Prove or disprove: 

Every continuous map from $S^2$ to $S^2$ has a fixed point.

## 3 (Spring '11)
a. State the **Lefschetz Fixed Point Theorem** for a finite simplicial complex $X$.

b. Use degree theory to prove this theorem in case $X = S^n$.

## 4 (Spring '12).
a. Prove that for every continuous map $f : S^2 \to S^2$ there is some $x$ such that either $f (x) = x$ or $f (x) = -x$. 

> Hint: Where $A : S^2 \to S^2$ is the antipodal map, you are being asked to prove that either $f$ or $A \circ f$ has a fixed point.

b. Exhibit a continuous map $f : S^3 \to S^3$ such that for every $x \in S^3$, $f (x)$ is equal to neither $x$ nor $-x$.

> Hint: It might help to first think about how you could do this for a map from $S^1$ to $S^1$.

## 5 (Spring '14). 
Show that a map $S^n \to S^n$ has a fixed point unless its degree is equal to the degree of the antipodal map $a : x \to -x$.

## 6 (Spring '08). 
Give an example of a homotopy class of maps of $S^1 \lor  S^1$ each member of which must have a fixed point, and also an example of a map of $S^1 \lor S^1$ which doesn't have a fixed point.

## 7 (Spring '17). 
Prove or disprove: 

Every map from $\RP^2 \lor \RP^2$ to itself has a fixed point.

## 8 (Fall '09). 
Find all homotopy classes of maps from $S^1 \times \DD^2$ to itself such that every element of the homotopy class has a fixed point.

## 9 (Spring '10). 
Let $X$ and $Y$ be finite connected simplicial complexes and let $f : X \to Y$ and $g : Y \to X$ be basepoint-preserving maps. 

Show that no matter how you homotope $f \lor g : X \lor Y \to X \lor Y$, there will always be a fixed point.

## 10 (Fall '12) 
Let $f = \id_{\RP^2} \lor \ast$ and $g = \ast \lor id_{S^1}$ be two maps of $\RP^2 \lor S^1$ to itself where $\ast$ denotes the constant map of a space to its basepoint.

Show that one map is homotopic to a map with no fixed points, while the other is not.

## 11 (Spring '09). 
View the torus $T$ as the quotient space $\RR^2 /\ZZ^2$. 

Let $A$ be a $2 \times 2$ matrix with $\ZZ$ coefficients.

a. Show that the linear map $A : \RR^2 \to \RR^2$ descends to a continuous map $\mca : T \to T$.

b. Show that, with respect to a suitable basis for $H_1 (T ; \ZZ)$, the matrix $A$ represents the map induced on $H_1$ by $\mca$.

c. Find a necessary and sufficient condition on $A$ for $\mca$ to be homotopic to the identity.

d. Find a necessary and sufficient condition on $A$ for $\mca$ to be homotopic to a map with no fixed points.

## 12 (Spring '19). 
a. Use the Lefschetz fixed point theorem to show that any degree-one map $f : S^2 \to S^2$ has at least one fixed point.

b. Give an example of a map $f : \RR^2 \to \RR^2$ having no fixed points.

c. Give an example of a degree-one map $f : S^2 \to S^2$ having exactly one fixed point.

## 13 (Fall '10). 
For which compact connected surfaces $\Sigma$ (with or without boundary) does there exist a continuous map $f : \Sigma \to \Sigma$ that is homotopic to the identity and has no fixed point? 

Explain your answer fully.

## 14 (Spring '16). 
Use the Brouwer fixed point theorem to show that an $n \times n$ matrix with nonnegative entries has a real eigenvalue.

# Miscellaneous algebraic topology

## 1 (Fall '14). 
Prove that $\RR^2$ is not homeomorphic to $\RR^n$ for $n > 2$.

## 2 (Spring '12). 
Prove that any finite tree is contractible, where a **tree** is a connected graph that contains no closed edge paths.

## 3 (Spring '13). 
Show that any continuous map $f : \RP^2 \to S^1 \times S^1$ is necessarily null-homotopic.

## 4 (Fall '11). 
Prove that, for $n \geq 2$, every continuous map $f: \RP^n \to S^1$ is null-homotopic.

## 5 (Spring '06). 
Let $S^2 \to \RP^2$ be the universal covering map. 

Is this map null-homotopic? 
Give a proof of your answer.

## 6 (Spring '17). 
Suppose that a map $f : S^3 \times S^3 \to \RP^3$ is not surjective. 

Prove that $f$ is homotopic to a constant function.

## 7 (Fall '06). 
Prove that there does not exist a continuous map $f : S^2 \to S^2$ from the unit sphere in $\RR^3$ to itself such that $f (\vector x) \perp \vector x$ 
(as vectors in $\RR^3$ for all $\vector x \in S^2$).

## 8 (Spring '08). 
Let $f$ be the map of $S^1 \times [0, 1]$ to itself defined by
$$
f (e^{i\theta} , s) = (e^{i(\theta+2\pi s)} , s)
,$$ 
so that $f$ restricts to the identity on the two boundary circles of $S^1 \times [0, 1]$. 

Show that $f$ is homotopic to the identity by a homotopy $f_t$ that is stationary on one of the boundary circles, but not by any homotopy that is stationary on both boundary circles. 

> Hint: Consider what $f$ does to the path $s \mapsto (e^{i\theta_0} , s)$ for fixed $e^{i\theta_0} \in S^1$.

## 9 (Spring '17). 
Show that $S^1 \times S^1$ is not the union of two disks (where there is no assumption that the disks intersect along their boundaries).

## 10 (Spring '14). 
Suppose that $X \subset Y$ and $X$ is a deformation retract of $Y$. 

Show that if $X$ is a path connected space, then $Y$ is path connected.

## 11 (Spring '05). 
Do one of the following:

a. Give (with justification) a contractible subset $X \subset \RR^2$ which is not a retract of $\RR^2$ .

b. Give (with justification) two topological spaces that have the same homology groups but that are not homotopy equivalent.

## 12 (Spring '16). 
Recall that the **suspension** of a topological space, denoted $SX$, is the quotient space formed from $X \times [-1, 1]$ by identifying $(x, 1)$ with $(y, 1)$ for all $x, y \in X$, and also identifying $(x, -1)$ with $(y, -1)$ for all $x, y \in X$.

a. Show that $SX$ is the union of two contractible subspaces.

b. Prove that if $X$ is path-connected then $\pi_1 (SX) = \theset{0}$.

c. For all $n \geq 1$, prove that $H_{n} (X) \cong H_{n+1} (SX)$.

