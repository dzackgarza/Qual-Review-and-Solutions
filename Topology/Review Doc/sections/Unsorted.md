# Unsorted 


## Common Spaces
\begin{align*}
S^n, \DD^n, T^n \RP^n, \CP^n, M, K, \Sigma_g, \RP^\infty, \CP^\infty
.\end{align*}

- Knot complements in $S^3$
- Lens spaces
- Prism spaces
- $\HP^n$
- Dunce Cap
- Matrix groups
- Pair of pants
- Covering spaces (hyperbolic geometry)
- Seifert surfaces
- Surgery
- Hawaiian earring
- Horned sphere
- Cantor set
- Simplicial Complexes
  - Nice minimal example:
  
  ![](figures/image_2020-05-22-18-58-03.png) 


## Common Operators

- Cartesian product $A\cross B$
- Wedge product $A \vee B$
- Connect Sum $A \# B$
- Quotienting $A/B$
- Puncturing $A\setminus \theset{a_i}$
- Smash product
- Join
- Cones
- Suspension
- Loop space
-  Identifying a finite number of points

## Theorems Used

Van Kampen:

The pushout is the upper-left colimit of the following diagram
\begin{center}
\begin{tikzcd}
A \disjoint_Z B   & A \ar[d] \ar[l] \
B \ar[r]          & Z \ar[l, "\iota_B"] \ar[u, "\iota_A"]
\end{tikzcd}
\end{center}

For groups, the pushout is given by the amalgamated free product: if $A = \generators{G_A \suchthat R_A}, B = \generators{G_B \suchthat R_B}$, then $A \ast_Z B = \generators{G_A, G_B \suchthat R_A, R_B, T}$ where $T$ is a set of relations given by $T = \theset{\iota_A(z) \iota_B(z)\inv \suchthat z\in Z}$.

Example: $A = \ZZ/4\ZZ = \gens{x \suchthat x^4}, B = \ZZ/6\ZZ = \gens{y \suchthat x^6}, Z = \ZZ/2\ZZ = \gens{z \suchthat z^2}$.
Then we can identify $Z$ as a subgroup of $A, B$ using $\iota_A(z) = x^2$ and $\iota_B(z) = y^3$.
So $$A\ast_Z B = \gens{x, y \suchthat x^4, y^6, x^2y^{-3}}$$.

Suppose $X = U_1 \union U_2$ such that $U_1\intersect U_2 \neq \emptyset$ is path connected.
Then taking $x_0 \in U\definedas U_1 \intersect U_2$ yields a pushout of fundamental groups

\begin{align*}
\pi_1(X; x_0) = \pi_1(U_1;x_0) \ast_{\pi_1(U; x_0)} \pi_1(U_2; x_0)
.\end{align*}


