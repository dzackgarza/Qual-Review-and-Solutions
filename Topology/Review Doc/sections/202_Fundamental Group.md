# Theorems: Algebraic Topology


## Fundamental Group

Conjugacy in $\pi_1$:

- See Hatcher 1.19, p.28
- See Hatcher's proof that $\pi_1$ is a group
- See change of basepoint map

- For a graph $G$, we always have $\pi_1(G) \cong \ZZ^n$ where $n = |E(G - T)|$, the complement of the set of edges in any maximal tree. Equivalently, $n = 1-\chi(G)$. Moreover, $X \homotopic \bigvee^n S^1$ in this case.

To calculate $\pi_1(X)$: construct a universal cover $\tilde X$, then find a group $G \actson \tilde X$ such that $\tilde X/G = X$; then $\pi_1(X) = G$ by uniqueness of universal covers.

## Homotopy

\todo{Merge Van Kampen theorems.}

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

    \todo[inline]{Formulate in terms of pushouts.}

    ![](figures/image_2020-06-01-00-07-39.png)

Note that the hypothesis that $U\cap V$ is path-connected is necessary: take $S^1$ with $U,V$ neighborhoods of the poles, whose intersection is two disjoint components.

Example (of pushing out with Van Kampen)
:   $A = \ZZ/4\ZZ = \gens{x \suchthat x^4}, B = \ZZ/6\ZZ = \gens{y \suchthat x^6}, Z = \ZZ/2\ZZ = \gens{z \suchthat z^2}$.
  
  Then we can identify $Z$ as a subgroup of $A, B$ using $\iota_A(z) = x^2$ and $\iota_B(z) = y^3$.
  
  So $$A\ast_Z B = \gens{x, y \suchthat x^4, y^6, x^2y^{-3}}$$.



:::{.theorem title="Whitehead's Theorem"}
A map $X \mapsvia{f} Y$ on CW complexes that is a weak homotopy equivalence (inducing isomorphisms in homotopy) is in fact a homotopy equivalence.
:::

:::{.warning}
Individual maps may not work: take $S^2 \cross \RP^3$ and $S^3 \cross \RP^2$ which have isomorphic homotopy but not homology.
:::


:::{.theorem title="Hurewicz"}
The Hurewicz map on an $n-1\dash$connected space $X$ is an isomorphism $\pi_{k\leq n}X \to H_{k\leq n} X$.

> I.e. for the minimal $i\geq 2$ for which $\pi_iX \neq 0$ but $\pi_{\leq i-1}X = 0$, $\pi_iX \cong H_iX$.
:::

:::{.theorem title="Cellular Approximation"}
Any continuous map between CW complexes is homotopy equivalent to a cellular map.
:::

**Applications**:

- $\pi_{k\leq n}S^n = 0$
- $\pi_n(X) \cong \pi_n(X^{(n)})$

:::{.theorem title="Freudenthal Suspension"}
\todo[inline]{Todo}
:::


- $\pi_{i\geq 2}(X)$ is always abelian.

* The ranks of $\pi_0$ and $H_0$ are the number of path components, and $\pi_0(X) = \ZZ$ iff $X$ is simply connected.
	* $X$ simply connected $\implies \pi_k(X) \cong H_k(X)$ up to and including the first nonvanishing $H_k$
  * $H_1(X) = \mathrm{Ab}(\pi_1 X)$, the abelianization.

* $\pi_k \bigvee X \neq \prod \pi_k X$ (counterexample: $S^1 \vee S^2$)
  * Nice case: $\pi_1\bigvee X = \bigast \pi_1 X$ by Van Kampen.

* $\pi_i(\hat X) \cong \pi_i(X)$ for $i\geq 2$ whenever $\hat X \surjects X$ is a universal cover.

* $\pi_i(S^n) = 0$ for $i < n$, $\pi_n(S^n) = \ZZ$
  * Not necessarily true that $\pi_i(S^n) = 0$ when $i > n$!!!
    * E.g. $\pi_3(S^2) = \ZZ$ by Hopf fibration

* $S^n / S^k \homotopic S^n \vee \Sigma S^{k}$
  * $\Sigma S^n = S^{n+1}$

* General mantra: homotopy plays nicely with products, homology with wedge products.[^pullbacks]
* $\pi_k\prod X = \prod \pi_k X$ by LES.[^homotopyproduct]

In general, homotopy groups behave nicely under homotopy pull-backs (e.g., fibrations and products), but not homotopy push-outs (e.g., cofibrations and wedges). Homology is the opposite.



Constructing a $K(\pi, 1)$: since $\pi = \left< S \mid R\right> = F(S)/R$, take $\bigvee^{|S|} S^1 \union_{|R|} e^2$. In English, wedge a circle for each generator and attach spheres for relations.

:::{.proposition title="Contracting Spaces in Products"}
\[
X\cross \RR^n \homotopic X \cross \pt \cong X
.\]
:::

---

[^pullbacks]: More generally, in $\mathbf{Top}$, we can look at $A \from \pt \to B$ -- then $A\cross B$ is the pullback and $A \vee B$ is the pushout. In this case, homology $h: \mathbf{Top} \to \mathbf{Grp}$ takes pushouts to pullbacks but doesn't behave well with pullbacks. Similarly, while $\pi$ takes pullbacks to pullbacks, it doesn't behave nicely with pushouts.


[^homotopyproduct]: This follows because $X\cross Y \surjects X$ is a fiber bundle, so use LES in homotopy and the fact that $\pi_{i\geq 2} \in \mathbf{Ab}$.
