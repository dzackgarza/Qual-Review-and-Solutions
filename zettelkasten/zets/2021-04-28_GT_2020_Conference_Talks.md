---
date: 2021-04-28 18:16:29
tags: 
  - Unfiled
---

[Conference and Seminar Talks](Conference%20and%20Seminar%20Talks)

# Joint GT/UGA Topology Seminar: Monday January 13th

## Talk 1: Knot Floer Homology and Cosmetic Surgeries

Dehn surgery: fundamental procedure for building 3-manifolds.

Outline

- Background on problem
- Results (known and new)
- Tools
- Proof


### Basics

Let $K\injects S^3$ be a knot.
Pick a rational number $p/q$ or $\infty$.
Can perform $p/q\dash$surgery (i.e. Dehn surgery) to obtain $S_{p/q}^3(K) \definedas (S^3\setminus K) \disjoint_f (D^2 \cross S^1)$ where $\bd D^2 \cross \pt \mapsto -p\mu + q\lambda$ where $\mu = ?, \lambda$ is the Seifert fiber (?).

Is this a unique operation?
I.e. do different knots yield different 3-manifolds?

Question:
Can different surgeries on the same knot yield different 3-manifolds?

**Definition:**
Two surgeries are *purely cosmetic* iff there is an orientation-preserving diffeomorphism between them.
If there is an orientation *reversing* diffeomorphism, they are said to be chirally cosmetic.

**Conjecture:**
There are no purely cosmetic surgeries.

Remark:
The conjecture can be stated for $K \injects Y^3$

> Note: don't know what $Y^3$ is.

Remark:
There exist chirally cosmetic surgeries.

Example:
$+9$ and $+\frac 9 2$ surgery on $T_{2, 3}$, or $+r, -r$ on any ampichiral knot.

Remark:
Meant to generalize the "knot complement problem", i.e. are knots determined by their complements?

Theorem (Gordon-Luecke 89):
If $S_r^3(K) = S^3 = S_\infty^3(K)$, then $r=\infty$.
(I.e. the only trivial surgery really is the trivial surgery?)

### Known Results

Suppose $K\subset S^3$is nontrivial, and two Dehn surgeries with different slopes are diffeomorphic.

- Computing $H^1 = \ZZ_p$ forces $p=p'$.
- By Boyer-Lines '91, the Alexander polynomial satisfies $\Delta_k''(1) = 0$.
- By Osvath-Szabo-Wu ('05, '09), $q$ and $q'$ have opposite signs (not necessarily $q=-q'$).
  - So there at most two ways of getting the same manifold from cosmetic surgeries.
- By Wang '06, $g\neq 1$
- By Ni-Wu '10, $\tau(K) = 0, q' = -q$, and $q^2 = -1 \mod p$.

**Theorem:**
Let $q > 0$, so $q' < 0$.
Then

- $p = 1, 2$
- If $p=2$, then $q = 1$ and $g=2$.
- If $p=1$, then $q \leq \frac{t+2g}{2g(g-1)}$

where $g$ is the genus and $t$ is the *Heegard-Floer thickness*.

Moreover, the knot Floer homology satisfies some further conditions (stronger than e.g. $\tau(K) = 0$).


Note that if $t < 4$, then the last condition forces $q=1, g=2$.
We then only have to consider two slopes.

Corollary:
The corollary holds for *thin knots* (i.e. thickness zero), e.g. all alternating and quasialternating knots.

For knots up to 16 crossings, $t\leq 2$ (from computations of knot-Floer homology on 1.6 million knots?)
When $K$ is thin, this condition can be stated in terms of the Alexander polynomial.

**Theorem:**
If $K$ is thin and has purely cosmetic surgery, then

- $g(K) = 2$
- The slopes are $\pm 1, \pm 2$
- The coefficients of the Alexander polynomial occur in ratios: $\Delta_k(t) = nt^2 - 4nt + (6n+1) - 4nt\inv  + nt^{-2}$ for some $n$, 

This is computationally effective:

- Number of prime knots with at most 16 crossings: 1.7 million
- Number with $\tau = 0$: 450,000
- Number satisfying the conditions in the theorem: 337

For each of these, need to consider $\pm 1, \pm 2$.
Noting from $HF$ will distinguish these surgeries.
Can use SnapPea to compute hyperbolic invariants -- most are distinguished by hyperbolic volume, or Chern-Simons invariant.

Could potentially take connect sums of the above knots, but eventually they stop satisfying the necessary condition.
In fact, the conjecture holds if all prime summands of $K$ have less than 16 crossings.

**Theorem (Ichihara-Song-Mattman-Saito):**
The conjecture holds for all 2-bridge knots.

**Theorem (Tao):**
Conjecture holds for arbitrary connected sums.

> So if there is a knot with cosmetic surgery, it is not prime.

Remark:
Futer-Purcell-Schleimer independently proved a similar result using hyperbolic techniques.


### Tools

What we'll want

1. Need some 3-manifold invariant to distinguish different surgeries
2. A knot invariant
3. A surgery formula computing (1) from (2) and the slope $p, q$.

Previously used 

- Cassem-Gordon and Cassem-Walker invariants, and
- Alexander polynomial ($\implies \Delta''(1) = 0$)

For (1), we'll use Heegard-Floer homology for the 3-manifold invariant:
Associated to a closed oriented 3-manifold $Y$ a graded vector space $\widehat{HF}(Y)$. 
In our case, it will be over $\ZZ/(2)$, and splits over $\mathrm{Spin}^c$ structures as $\widehat{HF}(Y) = \bigoplus_{s\in \mathrm{Spin}^c(Y)} \widehat{HF}(Y; s)$.

> Note that $\mathrm{Spin}^c(Y)$ can be put in correspondence with $H^1(Y)$.

For (2), we'll use knot Floer homology, namely a reformulation following H-Rasmussen-Watson.
To a knot $K \subset S^3$, associate

- An immersed collection of closed curves $\Gamma = (\gamma_0, \cdots, \gamma_n)$ in the punctured torus $T$:
  - I.e. a graded immersed Lagrangian
  - Defined up to homotopy equivalence, where homotopies can't cross the puncture.

  ![Image](figures/2020-01-13-15:14.png)\

- Some grading data ($\times 2$, Alexander and Maslov) amounting to labeling each component of $\Gamma$ with an integer. 
  (Important to proof!)

- (From world of immersed Lagrangians) A bounding cochain, i.e. a subset of self-intersection points of $\Gamma$.

Interpret the Alexander grading as specifying a lift $\bar \Gamma$  of $\Gamma$ from $T$ to $\bar T$, a $\ZZ\dash$fold covering space of $T$:

![Image](figures/2020-01-13-15:22.png)\

Examples (These are curves wrapped around cylinders):

![The unknot](figures/2020-01-13-15:25.png)

![$T_{2,3}$](figures/2020-01-13-15:24.png)

![Figure 8](figures/2020-01-13-15:25.png)

![$C_{2,1}(T_{2, 3})](figures/2020-01-13-15:27.png)

![$9_{44}$](figures/2020-01-13-15:28.png)

Somehow, this last example is representative.

A surgery formula: $\widehat{HF}(S_{p/q}^3(K))$ is floer homology in $T$ of $\Gamma$ with $\ell_{p,q}$ a line of slope $p/q$, i.e. it is generated by minimal intersection points $\Gamma \intersect \ell_{p, q}$. 
(This gives a chain complex, count bi-gons.)

For the $\mathrm{spin}^c$ decomposition, look at $\bar T$ with different lifts of $\ell_{p, q}$.









## Talk 2: Branched Covers Bounding $\QQ H B^4$

> Joint work with Aceto, Meier, A. Miller, M. Miller, Stipsicz.

**Definition:**
Two knots $K_0, K_1$ are **concordant** iff they cobound an annulus, i.e. there exists a smooth cylinder $S^1 \cross I$ embedded in $S^3 \cross I$ such that $S^1 \cross\theset{i}$ in $S^3 \cross \theset{i}$ is $K_i$.

The concordance group is an abelian group defined by $C = \theset{\text{knots in } S^3}/\sim$ where we identify knots that are concordant.

Theorem (Fox-Milnor 66):
If $K$ is slice, then $\Delta_K(t) = f(t) f(t\inv ) \in \ZZ[t^{\pm 1}]$.

Remark:
Define $A(k) \definedas H_1(\tilde{ S^3\setminus K}, \ZZ)$ as the integral homology of the infinite cyclic cover as a $\ZZ[t^{\pm 1}]\dash$module.
This is equal to $H_1(S^3\setminus K; \ZZ[t^{\pm 1}])$.
Then $\Delta_k(t) \definedas \mathrm{ord}(A(k))$.
Given an element of $M_{n, m}$ we get $\ZZ[t^{\pm 1}]^m \to \ZZ[t^{\pm 1}]^n \to A(k) \to 0$.
We can consider the ideal generated by all the minors (the order ideal), and if this ideal is principal we call the generator $\Delta_k(t)$.

$V - tV^t$ (the Seifert matrix?) is a square presentation matrix for $A(k)$, so $\Delta_k(t) = \det(V - tV^t)$.
Note that this is easy to compute. 
Example: for the figure 8, $\Delta_{4, 1}(t) = \det([1-t, t; -1, -1+t]) = -t^2 + 3t - 1$.

There is a notion of algebraically slice, and an algebraically slice knot implies Fox-Milnor.

Theorem (Casson-Gordon, 78):
If $K$ is slice and $p$ prime then the $p^r\dash$fold branched cover $\Sigma_{p^r}(K)$ is a rational homology 3-sphere $\QQ H S^3$ and bounds a rational homology 4-ball $\QQ HB^4$.

Remark:
$\Sigma_{p^r}(K_1 \# K_2) = \Sigma_{p^r} K_1 \# \Sigma_{p^r} K_2$.
The following map measures the obstruction to being slice: $\beta_{p^r}: \rho \to \Theta^3_\QQ$, where $[K] \to [\Sigma_{p^r} K]$.

Question:
How good is $\beta_{p^r}$ as a slice obstruction?

$\beta_2$ is pretty good for 2-bridge knots, i.e.

Theorem (Lisca 07):
If $K$ is a connected sum of 2-bridge knots, then $\beta_2(K) = 0 \implies K$ is slice.

> Note: there are non-slice knots with $\beta_2 =0$.

Theorem (Casson-Haner 81):
For each $s>0$, $\Sigma(2, 2s-1, 2s+1) \cong \Sigma_2(T_{2s-1, 2s+1})$ bounds a contractible manifold.

Theorem (Litherland 78):
Torus knots are $L_\delta I_0$ in $\rho$. (??)

These together imply that $\ker \beta_2 \geq \ZZ^\infty$.

Theorem (Aceto-Larson 18):
$\ker \beta_2 \cong \ZZ^\infty \oplus G$.

Main Theorem:
$\intersect_{p \text{ prime }, r\in \NN} \ker \beta_{p^r} \geq (\ZZ/(2))^4$.

> Knots in here have arf invariant zero, and are torsion in the concordance group.

#### Step 1: Construction

Define $K_n \definedas (\sigma_1 \cdot \sigma_2\inv)^n$ for $\sigma_i$ in the braid group $B_3$.

Example:

![Image](figures/2020-01-13-16:28.png)\

Definition:
$K$ is strongly negative ampichiral if there exists an orientation reversing involution $\tau:S^3 \to S^3$ such that $\tau(K) = K$.

Lemma (Kawauchi 09):
If $K$ is strongly negative ampichiral, then
$K$ bounds a disc in a $X = \QQ H B^4$ with only 2-torsion in $H_1(X; \ZZ)$.

*Proof (sketch):*
Let $M_k = S_0^3(K)$ be zero surgery on the knot.

![Image](figures/2020-01-13-16:34.png)

Then $\tau: M_k \to M_k$ is fixed-point free.

Can then consider the map $\pi: M_k \to M_k/\tau$ and the associated twisted $I\dash$bundle $I \to Z \to M_k \to M_k/\tau$.
Then:

![Image](figures/2020-01-13-16:37.png)

Theorem:
If $K$ is slice, the $\Sigma_{p^r}(K)$ bounds a $\QQ H B^4$ if $p$ is prime.

Proof (Milnor 68).

There is an exact sequence

\begin{align*}
\tilde H_i(\tilde X; \ZZ_p) \mapsvia{t^{p^r} - \id} \tilde H_i(\tilde X; \ZZ_p) \to \tilde H(\Sigma_{p^r}(D); \ZZ_p) (= 0) \to 0 \\
\tilde H_i(\tilde X; \ZZ_p) \mapsvia{t - \id} \tilde H_i(\tilde X; \ZZ_p) \to \tilde H(B^4; \ZZ_p) (= 0) \to 0 
,\end{align*}

where if $t-\id$ is an isomorphism, $(t^{p^r} - \id) = (t-\id)^{p^r}$ is an isomorphism as well (note we're in $\ZZ_p$.)

Corollary:
If $p$ is an odd prime, then $\Sigma_{p^r}(K)$ bounds a $\QQ H B^4$.

![Image](figures/2020-01-13-16:44.png)

Thus $\Sigma_{2^r}(K_n) \cong \Sigma_n(K_{2^r})$ by this symmetry.

In conclusion, if $n$ is an odd prime power, then $K_n \in \intersect \ker \beta_{p^r}$.

#### Step 2: Obstruction

Theorem (Brandenbursky 16):
$K_n$ is algebraically slice iff $n$ odd.

Uses a twisted Alexander polynomial:
Take $M_k = S_0^3(K)$ a zero surgery, $G = \pi_1(M_k)$, and $A(k) = G^{(1)}/G^{(2)}$ (?).

The input is a map $X: H_1(\Sigma_{p^r}(K); \ZZ) \to \ZZ_q$.
This lets you define a character 

\begin{align*}
\alpha(X): G \to G/G^{(1)} \cong \ZZ \semidirect A(k) 
\to \ZZ\semidirect A(t) / t^{p^r} - \id 
\cong \ZZ \semidirect H_1(\Sigma_{p^r}(K))
\to \GL(K, \QQ(\zeta_q)[t^{\pm 1}] )
.\end{align*}

Then $\tilde M_k$ is the universal cover of $M_k$.
Consider $C_*(\tilde M_k) \tensor{\ZZ[G]} Y$ for $Y = (\QQ(\zeta_q)[t^{\pm 1}] )^k$, then define the twisted Alexander polynomial $\Delta_k^{\tilde X}(t) = \mathrm{ord}(H_1(M_k, Y))$.

Theorem:
If $K$ is slice, then there exists some $X$ such that $\delta_K^{\tilde X}(t) = f(t) f(t\inv)$ in $\QQ(\zeta_q)[t^{\pm 1}]$.

Open question:
Are there infinite order elements in this group?
