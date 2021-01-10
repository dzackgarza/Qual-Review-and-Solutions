# Theorems: Algebraic Topology

:::{.proposition title="$\pi_0$ detects simply connectedness"}
$\pi_{0}(X) = \ZZ$ iff $X$ is simply connected.
:::

## Fundamental Group

### Conjugacy in $\pi_{1}$:

- See Hatcher 1.19, p.28
- See Hatcher's proof that $\pi_{1}$ is a group
- See change of basepoint map

### Calculating $\pi_1$ Using Universal Covers

To calculate $\pi_{1}(X)$: construct a universal cover $\tilde X$, then find a group $G \actson \tilde X$ such that $\tilde X/G = X$; then $\pi_{1}(X) = G$ by uniqueness of universal covers.


## Homotopy

\todo{Merge Van Kampen theorems.}


:::{.theorem title="Van Kampen 1"}
The pushout is the northwest colimit of the following diagram

\begin{tikzcd}
A \disjoint_{Z} B   & A \ar[d] \ar[l] \\
B \ar[u]\ar[r]          & Z \ar[l, "\iota_{B}"] \ar[u, "\iota_{A}"]
\end{tikzcd}

For groups, the pushout is given by the amalgamated free product: if $A = \generators{G_{A} \suchthat R_{A}}, B = \generators{G_{B} \suchthat R_{B}}$, then $$A \ast_{Z} B = \generators{G_{A}, G_{B} \suchthat R_{A}, R_{B}, T}$$ where $T$ is a set of relations given by $$T = \theset{\iota_{A}(z) \iota_{B}(z)\inv \suchthat z\in Z}.$$

Suppose $X = U_{1} \union U_{2}$ such that $U_{1}\intersect U_{2} \neq \emptyset$ is **path connected** (necessary condition).
Then taking $x_{0} \in U\da U_{1} \intersect U_{2}$ yields a pushout of fundamental groups
\[
\pi_{1}(X; x_{0}) = \pi_{1}(U_{1};x_{0}) \ast_{\pi_{1}(U; x_{0})} \pi_{1}(U_{2}; x_{0})
.\]

:::

:::{.theorem title="Van Kampen 2"}
If $X = U \union V$ where $U, V, U\intersect V$ are all path-connected then

\[
\pi_{1}(X) = \pi_{1} U \ast_{\pi_{1}(U \intersect V)} \pi_{1} V
,\]

where the amalgamated product can be computed as follows: 
If we have presentations

\[ 
\pi_{1}(U, w) &=
\left\langle u_{1}, \cdots, u_{k} \suchthat \alpha_{1}, \cdots, \alpha_{l}\right\rangle \\ 
\pi_{1}(V, w) &=\left\langle v_{1}, \cdots, v_{m} \suchthat \beta_{1}, \cdots, \beta_{n}\right\rangle \\ 
\pi_{1}(U \cap V, w) &=\left\langle w_{1}, \cdots, w_{p} \suchthat \gamma_{1}, \cdots, \gamma_{q}\right\rangle 
\]

then

\[
\pi_{1}(X, w) 
&= \left\langle u_{1}, \cdots, u_{k}, v_{1}, \cdots, v_{m}\right\rangle \\ 
&\mod 
\left\langle \alpha_{1}, \cdots, \alpha_{l}, \beta_{1}, \cdots, \beta_{n}, I\left(w_{1}\right) J\left(w_{1}\right)^{-1}, \cdots, I\left(w_{p}\right) J\left(w_{p}\right)^{-1}\right\rangle \\
&= \frac{\pi_{1}(U) \ast \pi_{1}(B)} {\generators{\theset{I(w_{i}) J(w_{i})\inv \suchthat 1\leq i \leq p}}}
\]

where

\[
I: \pi_{1}(U \cap V, w) &\rightarrow \pi_{1}(U, w) \\
J: \pi_{1}(U \cap V, w) &\rightarrow \pi_{1}(V, w)
.\]

:::

:::{.theorem title="Van Kampen 3"}
Suppose $X = U_{1} \union U_{2}$ where $U \da U_{1} \intersect U_{2} \neq \emptyset$ is path-connected, and let $\pt \in U$. Then the maps $i_{1}: U_{1} \into X$ and $i_{2}: U_{2} \into X$ induce the following group homomorphisms:

$$
i_{1}^*: \pi_{1}(U_{1} ,\pt) \into \pi_{1}(X, \pt) \\
i_{2}^*: \pi_{1}(U_{2} ,\pt) \into \pi_{1}(X, \pt)
$$

and letting $P = \pi_{1}(U), \pt$, there is a natural isomorphism

$$
\pi_{1}(X, \pt) \cong \pi_{1}(U_{1}, \pt) ~\ast_{P}~ \pi_{1}(U_{2}, \pt)
$$
where $\ast_{P}$ is the amalgamated free product over $P$.

\todo[inline]{Formulate in terms of pushouts.}

![](figures/image_{2020}-06-01-00-07-39.png)

Note that the hypothesis that $U\cap V$ is path-connected is necessary: take $S^1$ with $U,V$ neighborhoods of the poles, whose intersection is two disjoint components.


:::

:::{.example title="Pushing out with van Kampen"}
$A = \ZZ/4\ZZ = \gens{x \suchthat x^4}, B = \ZZ/6\ZZ = \gens{y \suchthat x^6}, Z = \ZZ/2\ZZ = \gens{z \suchthat z^2}$.
Then we can identify $Z$ as a subgroup of $A, B$ using $\iota_{A}(z) = x^2$ and $\iota_{B}(z) = y^3$.
So $$A\ast_{Z} B = \gens{x, y \suchthat x^4, y^6, x^2y^{-3}}$$.

:::

:::{.theorem title="Whitehead's Theorem"}
A map $X \mapsvia{f} Y$ on CW complexes that is a weak homotopy equivalence (inducing isomorphisms in homotopy) is in fact a homotopy equivalence.
:::

:::{.warnings}
Individual maps may not work: take $S^2 \cross \RP^3$ and $S^3 \cross \RP^2$ which have isomorphic homotopy but not homology.
:::

:::{.theorem title="Hurewicz"}
The Hurewicz map on an $n-1\dash$connected space $X$ is an isomorphism $\pi_{k\leq n}X \to H_{k\leq n} X$.

> I.e. for the minimal $i\geq 2$ for which $\pi_{iX} \neq 0$ but $\pi_{\leq i-1}X = 0$, $\pi_{iX} \cong H_{iX}$.

:::

:::{.theorem title="Cellular Approximation"}
Any continuous map between CW complexes is homotopy equivalent to a cellular map.
:::

:::{.example title="Applications of cellular approximation"}
\envlist

- $\pi_{k\leq n}S^n = 0$
- $\pi_{n}(X) \cong \pi_{n}(X^{(n)})$
:::

:::{.theorem title="Freudenthal Suspension"}

:::
\todo[inline]{Theorem}

## Unsorted Facts

- For a graph $G$, we always have $\pi_{1}(G) \cong \ZZ^n$ where $n = |E(G - T)|$, the complement of the set of edges in any maximal tree. Equivalently, $n = 1-\chi(G)$. Moreover, $X \homotopic \bigvee^n S^1$ in this case.


- $\pi_{i\geq 2}(X)$ is always abelian.

* The ranks of $\pi_{0}$ and $H_{0}$ are the number of path components, and $\pi_{0}(X) = \ZZ$ iff $X$ is simply connected.

	* $X$ simply connected $\implies \pi_{k}(X) \cong H_{k}(X)$ up to and including the first nonvanishing $H_{k}$
  * $H_{1}(X) = \mathrm{Ab}(\pi_{1} X)$, the abelianization.

* $\pi_{k} \bigvee X \neq \prod \pi_{k} X$ (counterexample: $S^1 \vee S^2$)
  * Nice case: $\pi_{1}\bigvee X = \ast \pi_{1} X$ by Van Kampen.

* $\pi_{i}(\hat X) \cong \pi_{i}(X)$ for $i\geq 2$ whenever $\hat X \surjects X$ is a universal cover.

* $\pi_{i}(S^n) = 0$ for $i < n$, $\pi_{n}(S^n) = \ZZ$
  * Not necessarily true that $\pi_{i}(S^n) = 0$ when $i > n$!!!
    * E.g. $\pi_{3}(S^2) = \ZZ$ by Hopf fibration

* $S^n / S^k \homotopic S^n \vee \Sigma S^{k}$
  * $\Sigma S^n = S^{n+1}$

* General mantra: homotopy plays nicely with products, homology with wedge products.[^pullbacks]
* $\pi_{k}\prod X = \prod \pi_{k} X$ by LES.[^homotopyproduct]

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

- $H_{1}$ is the abelianization of $\pi_{1}$.

- Homotopy commutes with products: $\pi_{k} \prod X_{i} = \prod \pi_{k} X_{i}$.

- Homotopy splits wedge products: $\pi_{1} \bigvee X_{i} = \ast \pi_{1} X_{i}$.


:::{.proposition title="?"}
$\pi_1 X$ for $X$ a CW-complex only depends on the 1-skeleton $X^{1}$, and $H_k(X)$ only depends on the $k$-skeleton.
:::


:::{.remark}
This is useful in practice: to compute $H_k$, you are free to attach $n\dash$cells for $n\geq k+1$.
:::


:::{.theorem title="?"}
Any two continuous functions into a convex set are homotopic.
:::

:::{.proof title="?"}
The linear homotopy. Supposing $X$ is convex, for any two points $x,y\in X$, the line $tx + (1-t)y$ is contained in $X$ for every $t\in[0,1]$.
So let $f, g: Z \into X$ be any continuous functions into $X$. Then define $H: Z \cross I \into X$ by $H(z,t) = tf(z) + (1-t)g(z)$, the linear homotopy between $f,g$. By convexity, the image is contained in $X$ for every $t,z$, so this is a homotopy between $f,g$.
:::


## Definition: The Fundamental Group / 1st Homotopy Group

Given a pointed space $(X,x_{0})$, we define the fundamental group $\pi_{1}(X)$ as follows:

- Take the set $L = \theset{\alpha: S^1\into X \mid \alpha(0) = \alpha(1) = x_{0}}$.
- Define an equivalence relation $\alpha \sim \beta$ iff there exists a homotopy $H: S^1 \cross I \into X$ such that $H(s, 0) = \alpha(s)$ and $H(s, 1) = \beta(s)$, i.e. if $f\homotopic g$ in $X$.
  - Symmetric:
  - Reflexive:
  - Transitive:
- Define $L/\sim$, which contains elements like $[\alpha]$ and $[\id_{x_{0}}]$, the equivalence classes of loops after quotienting by this relation.
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

# Theorem: $X$ is simply connected iff it has trivial fundamental group.

By definition, $X$ is simply connected iff $X$ is path connected and every loop contracts to a point.

$\Rightarrow$: Suppose $X$ is simply connected. Then every loop in $X$ contracts to a point, so if $\alpha$ is a loop in $X$, $[\alpha] = [\id_{x_{0}}]$, the identity element of $\pi_{1}(X)$. But then there is only one element in in this group.

$\Leftarrow$: Suppose $\pi_{1}(X) = 0$. Then there is just one element in the fundamental group, the identity element, so if $\alpha$ is a loop in $X$ then $[\alpha] = [\id_{x_{0}}]$. So there is a homotopy taking $\alpha$ to the constant map, which is a contraction of $\alpha$ to a point.
