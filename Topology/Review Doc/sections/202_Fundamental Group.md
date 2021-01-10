# Theorems: Algebraic Topology


## Fundamental Group

Conjugacy in $\pi_1$:

- See Hatcher 1.19, p.28
- See Hatcher's proof that $\pi_1$ is a group
- See change of basepoint map

- For a graph $G$, we always have $\pi_1(G) \cong \ZZ^n$ where $n = |E(G - T)|$, the complement of the set of edges in any maximal tree. Equivalently, $n = 1-\chi(G)$. Moreover, $X \homotopic \bigvee^n S^1$ in this case.

To calculate $\pi_1(X)$: construct a universal cover $\tilde X$, then find a group $G \actson \tilde X$ such that $\tilde X/G = X$; then $\pi_1(X) = G$ by uniqueness of universal covers.

:::{.proposition title="?"}
$\pi_0(X) = \ZZ$ iff $X$ is simply connected.
:::

- $H_1$ is the abelianization of $\pi_1$.

- Homotopy commutes with products: $\pi_k \prod X_i = \prod \pi_k X_i$.

- Homotopy splits wedge products: $\pi_1 \bigvee X_i = \ast \pi_1 X_i$.

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
    \pi_1(X, \pt) \cong \pi_1(U_1, \pt) ~\ast_P~ \pi_1(U_2, \pt)
    $$
    where $\ast_P$ is the amalgamated free product over $P$.

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

:::{.warnings}
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
  * Nice case: $\pi_1\bigvee X = \ast \pi_1 X$ by Van Kampen.

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

# The Fundamental Group (Unsorted)

## Lemma: The fundamental group of a CW-complex only depends on the 1-skeleton, and $H^k(X)$ only depends on the $k$-skeleton.

## Definition: Homotopy


## Definition: Nullhomotopic

If $f$ is homotopic to a constant map, say $f: x \mapsto y_0$ for some fixed $y_0 \in Y$, then $f$ is said to be *nullhomotopic*. In other words, if $f:X\into Y$ is nullhomotopic, then there exists a homotopy $H: X\cross I \into Y$ such that $H(x, 0) = f(x)$ and $H(x, 1) = y_0$.

Note that constant maps (or anything homotopic) induce zero homomorphisms.

# Theorem: Any two continuous functions into a convex set are homotopic.

Proof: The linear homotopy. Supposing $X$ is convex, for any two points $x,y\in X$, the line $tx + (1-t)y$ is contained in $X$ for every $t\in[0,1]$.
So let $f, g: Z \into X$ be any continuous functions into $X$. Then define $H: Z \cross I \into X$ by $H(z,t) = tf(z) + (1-t)g(z)$, the linear homotopy between $f,g$. By convexity, the image is contained in $X$ for every $t,z$, so this is a homotopy between $f,g$.

## Definition: Homotopy Equivalence

Let $f: X \to Y$ be a continuous map, then $f$ is said to be a *homotopy equivalence* if there exists a continuous map $g: X \to Y$ such that

$f\circ g \homotopic \id_Y$ and $g\circ f \homotopic \id_X$.

Such a map $g$ is called a homotopy inverse of $f$, the pair of maps is a homotopy equivalence.

If such an $f$ exists, we write $X \homotopic Y$ and say $X$ and $Y$ have the same homotopy type, or that they are homotopy equivalent.

> Note that homotopy equivalence is strictly weaker than homeomorphic equivalence, i.e., $X\cong Y$ implies $X \homotopic Y$ but not necessarily the converse.

## Definition: Contractible

A topological space $X$ is *contractible* if $X$ is homotopy equivalent to a point, i.e. $X \homotopic \theset{x_0}$. This means that there exists a pair of homotopy inverses $f: X \into \theset{x_0}$ and $g:\theset{x_0} \into X$ such that $f\circ g = \id_{\theset{x_0}}$ and $g\circ f = \id_X$.

This is a useful property, because it supplies you with a homotopy.

# Definition: Deformation Retract

Let $X$ be a topological space and $A \subset X$ be a subspace, then a *retraction* of $X$ onto $A$ is a map $r: X\into X$ such that the image of $X$ is $A$ and $r$ restricted to $A$ is the identity map on $A$.

Note that this definition isn't very useful, as every space has at least one retraction - for example, the constant map $r:X \into \theset{x_0}$ for any $x\_0 \in X$.

A *deformation retract* is a homotopy $H:X\cross I \into X$ from the identity on $X$ to the identity on $A$ that fixes $A$ at all times. That is,
$$
H: X\cross I \to X \\
H(x, 0) = \id_X \\
H(x, 1) = \id_A \\
x\in A \implies H(x, t) \in A \quad \forall t
$$

Equivalently, this requires that $\restrictionof{H}{A} = \id_A$

A deformation retract between a space and a subspace is a homotopy equivalence, and further $X\homotopic Y$ iff there is a $Z$ such that both $X$ and $Y$ are deformation retracts of $Z$. Moreover, if $A$ and $B$ both have deformation retracts onto a common space $X$, then $A \homotopic B$.

## Definition: The Fundamental Group / 1st Homotopy Group

Given a pointed space $(X,x_0)$, we define the fundamental group $\pi_1(X)$ as follows:

- Take the set $L = \theset{\alpha: S^1\into X \mid \alpha(0) = \alpha(1) = x_0}$.
- Define an equivalence relation $\alpha \sim \beta$ iff there exists a homotopy $H: S^1 \cross I \into X$ such that $H(s, 0) = \alpha(s)$ and $H(s, 1) = \beta(s)$, i.e. if $f\homotopic g$ in $X$.
  - Symmetric:
  - Reflexive:
  - Transitive:
- Define $L/\sim$, which contains elements like $[\alpha]$ and $[\id_{x_0}]$, the equivalence classes of loops after quotienting by this relation.
- Define a product structure: for $[\alpha], [\beta] \in L/\sim$, define $[\alpha][\beta] = [\alpha \cdot \beta]$, where we just need to define a product structure on bona fide loops. Just do this by reparameterizing:
  $(f\cdot g)(s) = \mathbb{1}[s \in \left[0, \frac{1}{2}]\right]f(2s) + \mathbb{1}[s \in \left[\frac{1}{2}, 1]\right]g(2s-1)$
  - Continuous: by the pasting lemma and assumed continuity of $f, g$
  - Well-defined:
- Check that this is actually a group
  - Identity element:
  - Closure:
  - Associativity:
  - Inverses:
- Summary:
  - Elements of the fundamental group are *homotopy classes of loops*.
  - Continuous maps between spaces induce *some* homomorphism on fundamental groups.
    - Inclusions

# Theorem: $X$ is simply connected iff it has trivial fundamental group.

By definition, $X$ is simply connected iff $X$ is path connected and every loop contracts to a point.

$\Rightarrow$: Suppose $X$ is simply connected. Then every loop in $X$ contracts to a point, so if $\alpha$ is a loop in $X$, $[\alpha] = [\id_{x_0}]$, the identity element of $\pi_1(X)$. But then there is only one element in in this group.

$\Leftarrow$: Suppose $\pi_1(X) = 0$. Then there is just one element in the fundamental group, the identity element, so if $\alpha$ is a loop in $X$ then $[\alpha] = [\id_{x_0}]$. So there is a homotopy taking $\alpha$ to the constant map, which is a contraction of $\alpha$ to a point.
