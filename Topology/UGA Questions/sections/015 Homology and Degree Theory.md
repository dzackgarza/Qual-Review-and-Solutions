# Homology and Degree Theory

## 1 (Spring '09). 
Compute the homology of the one-point union of $S^1 \times S^1$ and $S^1$.

## 2 (Fall '06). 

a.  State the **Mayer-Vietoris theorem**.

b.  Use it to compute the homology of the space $X$ obtained by gluing two solid tori along their boundary as follows. 
    Let $\DD^2$ be the unit disk and let $S^1$ be the unit circle in the complex plane $\CC$. 
    Let $A = S^1 \times \DD^2$ and $B = \DD^2 \times S^1$. 
    
    Then $X$ is the quotient space of the disjoint union $A \disjoint B$ obtained by identifying $(z, w) \in A$ with $(zw^3 , w) \in B$ for all $(z, w) \in S^1 \times S^1$.

## 3 (Fall '12). 
Let $A$ and $B$ be circles bounding disjoint disks in the plane $z = 0$ in $\RR^3$. 
Let $X$ be the subset of the upper half-space of $\RR^3$ that is the union of the plane $z = 0$ and a (topological) cylinder that intersects the plane in $\partial C = A \cup B$.

Compute $H_* (X)$ using the Mayer--Vietoris sequence.

## 4 (Fall '14). 
Compute the integral homology groups of the space $X = Y \cup Z$ which is the union of the sphere 
$$
Y = \theset{x^2 + y^2 + z^2 = 1}
$$ 
and the ellipsoid 
$$
Z =  \theset{x^2 + y^2 + {z^2 \over 4} = 1}
.$$

## 5 (Spring '08). 
Let $X$ consist of two copies of the solid torus $\DD^2 \times S^1$, glued together by the identity map along the boundary torus $S^1 \times S^1$.
Compute the homology groups of $X$.

## 6 (Spring '17). 
Use the circle along which the connected sum is performed and the Mayer-Vietoris long exact sequence to compute the homology of $\RP^2 \# \RP^2$.

## 7 (Fall '15). 
Express a Klein bottle as the union of two annuli. 

Use the Mayer Vietoris sequence and this decomposition to compute its homology.

## 8 (Spring '09). 
Let $X$ be the topological space obtained by identifying three distinct points on $S^2$. 
Calculate $H_* (X; Z)$.

## 9 (Fall '05). 
Compute $H_0$ and $H_1$ of the complete graph $K_5$ formed by taking five points and joining each pair with an edge.

## 10 (Fall '18). 
Compute the homology of the subset $X \subset \RR^3$ formed as the union of the unit sphere, the $z\dash$axis, and the $xy\dash$plane.

## 11 (Spring '05/Fall '13). 
Let $X$ be the topological space formed by filling in two circles $S^1 \times \theset{p_1 }$ and $S^1 \times \theset{p_2 }$ in the torus $S^1 \times S^1$ with disks.

Calculate the fundamental group and the homology groups of $X$.

## 12 (Spring '19). 
a.  Consider the quotient space 
    $$
    T^2 = \RR^2 / \sim \qtext{where} (x, y) \sim (x + m, y + n) \text{ for } m, n \in \ZZ
    ,$$ 
    and let $A$ be any $2 \times 2$ matrix whose entries are integers such that $\det A = 1$. 
    
    Prove that the action of $A$ on $\RR^2$ descends via the quotient $\RR^2 \to T^2$ to induce a homeomorphism $T^2 \to T^2$.

b.  Using this homeomorphism of $T^2$, we define a new quotient space 
    $$
    T_A^3 \definedas {T^2\cross \RR \over \sim} \qtext{where} ((x, y), t) \sim (A(x, y), t + 1)
    $$
    Compute $H_1 (T_A^3 )$ if $A=\left(\begin{array}{ll} 1 & 1 \\ 0 & 1 \end{array}\right).$

## 13 (Spring '12). 
Give a self-contained proof that the zeroth homology $H_0 (X)$ is isomorphic to $\ZZ$ for every path-connected space $X$.

## 14 (Fall '18). 
It is a fact that if $X$ is a single point then $H_1 (X) = \theset{0}$. 

One of the following is the correct justification of this fact in terms of the singular chain complex. 

Which one is correct and why is it correct?

a. $C_1 (X) = \theset{0}$.

b. $C_1 (X) \neq \theset{0}$ but $\ker \partial_1 = 0$ with $\partial_1 : C_1 (X) \to C_0 (X)$.

c. $\ker \partial_1 \neq 0$ but $\ker \partial_1 = \im\partial_2$ with $\partial_2 : C_2 (X) \to C_1 (X)$.

## 15 (Fall '10). 
Compute the homology groups of $S^2 \times S^2$.

## 16 (Fall '16). 
Let $\Sigma$ be a closed orientable surface of genus $g$.
Compute $H_i(S^1 \times \Sigma; Z)$ for $i = 0, 1, 2, 3$.

## 17 (Spring '07). 
Prove that if $A$ is a retract of the topological space $X$, then for all nonnegative integers $n$ there is a group $G_n$ such that $H_{n} (X) \cong H_{n} (A) \oplus G_n$.

> Here $H_{n}$ denotes the $n$th singular homology group with integer coefficients.

## 18 (Spring '13). 
Does there exist a map of degree 2013 from $S^2 \to S^2$.

## 19 (Fall '18). 
For each $n \in \ZZ$ give an example of a map $f_n : S^2 \to S^2$. 

For which $n$ must any such map have a fixed point?

## 20 (Spring '09).
a.  What is the degree of the antipodal map on the $n$-sphere? 
    (No justification required)

b.  Define a CW complex homeomorphic to the real projective $n\dash$space $\RP^n$.

c.  Let $\pi : \RP^n \to X$ be a covering map. Show that if $n$ is even, $\pi$ is a homeomorphism.

## 21 (Fall '17). 
Let $A \subset X$. 
Prove that the relative homology group $H_0 (X, A)$ is trivial if and only if $A$ intersects every path component of $X$.

## 22 (Fall '18). 
Let $\DD$ be a closed disk embedded in the torus $T = S^1 \times S^1$ and let $X$ be the result of removing the interior of $\DD$ from $T$ . 
Let $B$ be the boundary of $X$, i.e. the circle boundary of the original closed disk $\DD$. 

Compute $H_i (T, B)$ for all $i$.

## 23 (Fall '11). 
For any $n \geq 1$ let $S^n = \theset{(x_0 , \cdots , x_n )\mid \sum x_i^2 =1}$ denote the $n$ dimensional unit sphere and let $$E = \theset{(x_0 , . . . , x_n )\mid x_n = 0}$$ denote the "equator".

Find, for all $k$, the relative homology $H_k (S^n , E)$.

## 24 (Spring '12/Spring '15). 
Suppose that $U$ and $V$ are open subsets of a space $X$, with $X = U \cup V$. 
Find, with proof, a general formula relating the Euler characteristics of $X, U, V$, and $U \cap V$. 

> You may assume that the homologies of $U, V, U \cap V, X$ are finite-dimensional so that their Euler characteristics are well defined.



