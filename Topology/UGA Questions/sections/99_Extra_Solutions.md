# Extra Problem Solutions

## Point Set

### Connectedness

1. \hyperref[problem:interval_is_connected]{Problem Statement} \label{problem:interval_is_connected_soln}

> [Reference](https://sites.math.washington.edu/~morrow/334_16/connected.pdf)
>
> [A potentially shorter proof](https://math.stackexchange.com/questions/934421/proof-of-that-every-interval-is-connected)

- Let $I = [0, 1] = A\union B$ be a disconnection, so
  - $A, B \neq \emptyset$
  - $A \disjoint B = I$
  - $\cl_I(A) \intersect B = A \intersect \cl_I(B) = \emptyset$.
- Let $a\in A$ and $b\in B$ where WLOG $a<b$ 
  - (since either $a<b$ or $b<a$, and $a\neq b$ since $A, B$ are disjoint)
- Let $K = [a, b]$ and define $A_K \definedas A\intersect K$ and $B_K \definedas B\intersect K$.
- Now $A_K, B_K$ is a disconnection of $K$.
- Let $s = \sup(A_K)$, which exists since $\RR$ is complete and has the LUB property
- Claim: $s \in \cl_I(A_K)$. Proof:
  - If $s\in A_K$ there's nothing to show since $A_K \subset \cl_I(A_K)$, so assume $s\in I\setminus A_K$.
  - Now let $N_s$ be an arbitrary neighborhood of $s$, then using ??? we can find an $\eps>0$ such that $B_\eps(s) \subset N_s$
  - Since $s$ is a supremum, there exists an $a\in A_K$ such that $s-\eps < a$.
  - But then $a \in B_\eps(s)$ and $a\in N_s$ with $a\neq s$.
  - Since $N_s$ was arbitrary, every $N_s$ contains a point of $A_K$ not equal to $s$, so $s$ is a limit point by definition.
- Since $s\in \cl_I(A_K)$ and $\cl_I(A_K)\intersect B_K = \emptyset$, we have $s\not \in B_K$.
- Then the subinterval $(x, b] \intersect A_K = \emptyset$ for every $x>c$ since $c \definedas \sup A_K$.
- But since $A_K \disjoint B_K = K$, we must have $(x, b] \subset B_K$, and thus $s\in \cl_I(B_K)$.
- Since $A_K, B_K$ were assumed disconnecting, $s\not \in A_K$
- But then $s\in K$ but $s\not\in A_K \disjoint B_K = K$, a contradiction.

$\qed$




## From Problem Sessions


1. \hyperref[problem:compact_closed_subspace]{Problem Statement} \label{problem:compact_closed_subspace_solution}
  - Let $X$ be compact, $A\subset X$ closed, and $\theset{U_\alpha} \covers A$ be an open cover.
  - By definition of the subspace topology, each $U_\alpha = V_\alpha \intersect A$ for some open $V_\alpha \subset X$, and $A\subset \union_\alpha V_\alpha$.
  - Since $A$ is closed in $X$, $X\setminus A$ is open.
  - Then $\theset{V_\alpha}\union \theset{X\setminus A}\covers X$ is an open cover, since every point is either in $A$ or $X\setminus A$.
  - By compactness of $X$, there is a finite subcover $\theset{U_j \suchthat j\leq N}\union \theset{X\setminus A}$
  - Then $\qty{\theset{U_j} \union \theset{X\setminus A}} \intersect A \definedas \theset{V_j}$ is a finite cover of $A$.
2. \hyperref[problem:compact_continuous]{Problem Statement} \label{problem:compact_continuous_soln}
  - Let $f:X\to Y$ be continuous with $X$ compact, and $\theset{U_\alpha} \covers f(X)$ be an open cover.
  - Then $\theset{f\inv(U_\alpha)} \covers X$ is an open cover of $X$, since $x\in X \implies f(x) \in f(X) \implies f(x) \in U_\alpha$ for some $\alpha$, so $x\in f\inv(U_\alpha)$ by definition.
  - By compactness of $X$ there is a finite subcover $\theset{f\inv(U_j) \suchthat j\leq N} \covers X$.
  - Then the finite subcover $\theset{U_j\suchthat j\leq N} \covers f(X)$, since if $y\in f(X)$, $y\in U_\alpha$ for some $\alpha$ and thus $f\inv(y) \in f\inv(U_j)$ for some $j$ since $\theset{U_j}$ is a cover of $X$.

3. \hyperref[problem:compact_closed_hausdorff]{Problem Statement} \label{problem:compact_closed_hausdorff_soln}

> Note, alternative definition of "open":

  - Let $A$ be a compact subset of $X$ a Hausdorff space, we will show $X\setminus A$ is open
  - Fix $x\in X\setminus A$.
  - Since $X$ is Hausdorff, for every $y\in A$ we can find $U_y \ni y$ and $V_x(y) \ni x$ depending on $y$ such that $U_x(y) \intersect U_y = \emptyset$.
  - Then $\theset{U_y \suchthat y\in A} \covers A$, and by compactness of $A$ there is a finite subcover corresponding to a finite collection $\theset{y_1, \cdots, y_n}$.
  - **Magic Step**: set $U = \union U_{y_i}$ and $V = \intersect V_x(y_i)$; 
    - Note $A\subset U$ and $x\in V$
    - Note $U\intersect V = \emptyset$.
  - Done: for every $x\in X\setminus A$, we have found an open set $V\ni x$ such that $V\intersect A = \emptyset$, so $x$ is an interior point and a set is open iff every point is an interior point.

 ![](figures/image_2020-06-11-20-14-26.png) 

4. \hyperref[problem:continuous_bijection_hausdorff]{Problem Statement} \label{problem:continuous_bijection_hausdorff_soln}

  - It suffices to show that $f$ is a closed map, i.e. if $U\subseteq X$ is closed then $f(U)\subseteq Y$ is again closed.
  - Let $U\in X$ be closed; since $X$ is closed, $U$ is compact 
    - Since closed subsets of compact spaces are compact.
  - Since $f$ is continuous, $f(U)$ is compact
    - Since the continuous image of a compact set is compact.
  - Since $Y$ is Hausdorff and $f(U)$ is compact, $f(U)$ is closed 
    - Since compact subsets of Hausdorff spaces are closed.

5. Todo

6. \hyperref[problem:open_but_not_in_ambient_space]{Problem Statement} \label{problem:open_but_not_in_ambient_space_soln}

  - Take $[0, 1] \subset [0, 1] \subset \RR$.
    Then $[0, 1]$ is tautologically open in $[0, 1]$ as it is the entire space, but $[0, 1]$ is not open in $\RR$ since (e.g.) $\theset{1}$ is not an interior point (every neighborhood intersects the complement $\RR\setminus[0, 1]$).

7. Todo
