## Algebraic

### Homotopy

> Todo: Merge the two van Kampen theorems.


Theorem (Van Kampen)
:   The pushout is the northwest colimit of the following diagram
    \begin{center}
    \begin{tikzcd}
    A \disjoint_Z B   & A \ar[d] \ar[l] \\
    B \ar[u]\ar[r]          & Z \ar[l, "\iota_B"] \ar[u, "\iota_A"]
    \end{tikzcd}
    \end{center}

    For groups, the pushout is given by the amalgamated free product: if $A = \generators{G_A \suchthat R_A}, B = \generators{G_B \suchthat R_B}$, then $$A \ast_Z B = \generators{G_A, G_B \suchthat R_A, R_B, T}$$ where $T$ is a set of relations given by $$T = \theset{\iota_A(z) \iota_B(z)\inv \suchthat z\in Z}.$$


    Suppose $X = U_1 \union U_2$ such that $U_1\intersect U_2 \neq \emptyset$ is **path connected** (necessary condition).
    Then taking $x_0 \in U\definedas U_1 \intersect U_2$ yields a pushout of fundamental groups

    \begin{align*}
    \pi_1(X; x_0) = \pi_1(U_1;x_0) \ast_{\pi_1(U; x_0)} \pi_1(U_2; x_0)
    .\end{align*}


Theorem (Van Kampen)
:   If $X = U \union V$ where $U, V, U\intersect V$ are all path-connected then

    \begin{align*}
    \pi_1(X) = \pi_1 U \ast_{\pi_1(U \intersect V)} \pi_1 V
    ,\end{align*}

    where the amalgamated product can be computed as follows: 
    If we have presentations

    \begin{align*} 
    \pi_{1}(U, w) &=
    \left\langle u_{1}, \cdots, u_{k} \suchthat \alpha_{1}, \cdots, \alpha_{l}\right\rangle \\ 
    \pi_{1}(V, w) &=\left\langle v_{1}, \cdots, v_{m} \suchthat \beta_{1}, \cdots, \beta_{n}\right\rangle \\ 
    \pi_{1}(U \cap V, w) &=\left\langle w_{1}, \cdots, w_{p} \suchthat \gamma_{1}, \cdots, \gamma_{q}\right\rangle 
    \end{align*}

    then

    \begin{align*}
    \pi_{1}(X, w) 
    &= \left\langle u_{1}, \cdots, u_{k}, v_{1}, \cdots, v_{m}\right\rangle \\ 
    &\mod 
    \left\langle \alpha_{1}, \cdots, \alpha_{l}, \beta_{1}, \cdots, \beta_{n}, I\left(w_{1}\right) J\left(w_{1}\right)^{-1}, \cdots, I\left(w_{p}\right) J\left(w_{p}\right)^{-1}\right\rangle \\
    &= \frac{\pi_1(U) \ast \pi_1(B)} {\generators{\theset{I(w_i) J(w_i)\inv \suchthat 1\leq i \leq p}}}
    \end{align*}

    where

    \begin{align*}
    I: \pi_{1}(U \cap V, w) &\rightarrow \pi_{1}(U, w) \\
    J: \pi_{1}(U \cap V, w) &\rightarrow \pi_{1}(V, w)
    .\end{align*}

Theorem (Seifert-van Kampen Theorem)
:   Suppose $X = U_1 \union U_2$ where $U \definedas U_1 \intersect U_2 \neq \emptyset$ is path-connected, and let $\pt \in U$. Then the maps $i_1: U_1 \into X$ and $i_2: U_2 \into X$ induce the following group homomorphisms:

    $$
    i_1^*: \pi_1(U_1 ,\pt) \into \pi_1(X, \pt) \\
    i_2^*: \pi_1(U_2 ,\pt) \into \pi_1(X, \pt)
    $$

    and letting $P = \pi_1(U), \pt$, there is a natural isomorphism

    $$
    \pi_1(X, \pt) \cong \pi_1(U_1, \pt) ~\bigast_P~ \pi_1(U_2, \pt)
    $$
    where $\bigast_P$ is the amalgamated free product over $P$.

    > (Todo: formulate in terms of pushouts)

![](figures/image_2020-06-01-00-07-39.png)

**Examples**

Example
: $A = \ZZ/4\ZZ = \gens{x \suchthat x^4}, B = \ZZ/6\ZZ = \gens{y \suchthat x^6}, Z = \ZZ/2\ZZ = \gens{z \suchthat z^2}$.
  Then we can identify $Z$ as a subgroup of $A, B$ using $\iota_A(z) = x^2$ and $\iota_B(z) = y^3$.
  So $$A\ast_Z B = \gens{x, y \suchthat x^4, y^6, x^2y^{-3}}$$.


- Computing $\pi_1(S^1 \vee S^1)$
- Computing $\pi_1(S^1 \cross S^1)$
- Counterexample when $U\cap V$ isn't path-connected: $S^1$ with $U,V$ neighborhoods of the poles.

### Homology

Useful fact: since $\ZZ$ is free, any exact sequence of the form $0 \to \ZZ^n \to A \to \ZZ^m \to 0$ splits and $A\cong \ZZ^{n}\cross \ZZ^m$.

Useful fact: $\tilde H_*(A\vee B) \cong H_*(A) \times H_*(B)$.

Theorem (Mayer Vietoris)
:   Let $X = A^\circ \union B^\circ$; then there is a SES of chain complexes
    \begin{align*}
    0 \to C_n(A\intersect B) \mapsvia{x\mapsto (x, -x)} C_n(A) \oplus C_n(B) \mapsvia{(x, y) \mapsto x+y} C_n(A + B) \to 0
    \end{align*}
    
    where $C_n(A+B)$ denotes the chains that are sums of chains in $A$ and chains in $B$.
    This yields a LES in homology:

    \begin{align*}
    \cdots \to H_n(A\intersect B) \mapsvia{x\mapsto (x, -x)} H_n(A) \oplus H_n(B) \mapsvia{(x, y) \mapsto x+y} H_n(X) \to \cdots
    .\end{align*}

    
