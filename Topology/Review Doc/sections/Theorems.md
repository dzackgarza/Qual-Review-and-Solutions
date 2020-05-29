# Theorems

Theorem
: Points are closed in $T_1$ spaces.

Theorem
: A metric space $X$ is sequentially compact iff it is complete and totally bounded.

Theorem
: A metric space is totally bounded iff every sequence has a Cauchy subsequence.

Theorem
: A metric space is compact iff it is complete and totally bounded.

Theorem (Baire)
: If $X$ is a complete metric space, then the intersection of countably many dense open sets is dense in $X$.

Theorem
: A continuous bijective open map is a homeomorphism.

Theorem
: A closed subset $A$ of a compact set $B$ is compact.

Proof
:   \hfill

    - Let $\theset{A_i} \rightrightarrows A$ be a covering of $A$ by sets open in $A$.
    - Each $A_i = B_i \intersect A$ for some $B_i$ open in $B$ (definition of subspace topology)
    - Define $V = \theset{B_i}$, then $V \rightrightarrows A$ is an open cover.
    - Since $A$ is closed, $W\definedas B\setminus A$ is open
    - Then $V\union W$ is an open cover of $B$, and has a finite subcover $\theset{V_i}$
    - Then $\theset{V_i \intersect A}$ is a finite open cover of $A$.

Theorem
: The continuous image of a compact set is compact.

Theorem
:   A closed subset of a Hausdorff space is compact.

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
