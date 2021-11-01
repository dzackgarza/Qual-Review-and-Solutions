---
order: 20
---

# Basics

## Theorems
    
:::{.theorem title="Folland 0.25"}
For $E \subseteq (X, d)$ a metric space, TFAE:

- $E$ is complete and totally bounded.
- $E$ is sequentially compact: Every sequence in $E$ has a subsequence that converges to a point in $E$.
- $E$ is compact: every open cover has a finite subcover.

Note that $E$ is complete as a metric space with the induced metric iff $E$ is closed in $X$, and $E$ is bounded iff it is totally bounded.
:::

:::{.theorem title="Mean Value Theorem"}
If $f: [a, b] \to \RR$ is continuous on a closed interval and differentiable on $(a, b)$, then there exists $\xi \in [a, b]$ such that 
\[
f(b) - f(a) = f'(\xi)(b-a)
.\]


:::

:::{.theorem title="Lagrange and Cauchy Remainders"}
If $f$ is $n$ times differentiable on a neighborhood of a point $p$, say $N_\delta(p)$, then for all points $x$ in the deleted neighborhood $N_\delta(p) - \theset{p}$ , there exists a point $\xi$ strictly between $x$ and $p$ such that
\[
x \in N_\delta(p)-\theset{p} \implies f(x) 
&= \sum_{k=0}^{n-1} \frac{f^{(k)}(p)}{k!}(x-p)^k + \frac{f^{(n)}(\xi)}{n!}(x-p)^n \\ \\
&= \sum_{k=0}^{n-1} \frac{f^{(k)}(p)}{k!}(x-p)^k + \int_c^x \frac{1}{n!} \dd{^n f}{x^n}(t) (x-t)^n ~dt
\]
:::

:::{.proposition title="Sufficient condition for Taylor convergence"}
Given a point $c$ and some $\varepsilon>0$, if $f \in C^\infty(I)$ and there exists an $M$ such that 
$$
x \in N_\varepsilon(c) \implies \abs{f^{(n)}(x)} \leq M^n
$$
then the Taylor expansion about $c$ converges on $N_\varepsilon(c)$.
:::

## Topology / Sets

:::{.theorem title="Heine-Cantor"}
Every continuous function $f:X\to Y$ where $X$ is a compact metric space is uniformly continuous.
:::

:::{.proof title="?"}
Fix $\eps>0$, we'll find a $\delta$ that works for all $x\in X$ uniformly.
For every $x\in X$, pick a $\delta_x$ neighborhood satisfying the conditions for (assumed) continuity.
Take an open cover by $\delta_x/2$ balls, extract a finite subcover, take $\delta$ the minimal radius.
:::

:::{.proposition title="Compact if and only if sequentially compact for metric spaces"}
Metric spaces are compact iff they are sequentially compact, (i.e. every sequence has a convergent subsequence).
:::

:::{.proof title="?"}
Todo.
\todo[inline]{Proof.}
:::

:::{.proposition title="A unit ball that is not compact"}
The unit ball in $C([0, 1])$ with the sup norm is not compact.
:::

:::{.proof title="?"}
Take $f_k(x) = x^n$, which converges to $\chi(x=1)$. 
The limit is not continuous, so no subsequence can converge.
:::

:::{.theorem title="Heine-Borel"}
$X\subseteq \RR^n$ is compact $\iff X$ is closed and bounded.
:::

:::{.proposition title="Geometric Series"}
\[
\sum_{k=0}^\infty x^k = \frac 1 {1-x} \iff \abs{x} < 1
.\]
:::

:::{.corollary title="?"}
\[
\sum_{k=0}^\infty \frac 1 {2^k} = 1
.\]
:::

:::{.proposition title="?"}
The Cantor set is closed with empty interior.
:::

:::{.proof title="?"}
Its complement is a union of open intervals, and can't contain an interval since intervals have positive measure and $m(C_n)$ tends to zero.
:::

:::{.corollary title="?"}
The Cantor set is nowhere dense.
:::

:::{.proposition title="?"}
Singleton sets in $\RR$ are closed, and thus $\QQ$ is an $F_\sigma$ set.
:::

:::{.theorem title="Baire"}
$\RR$ is a **Baire space** 
Thus $\RR$ can not be written as a countable union of nowhere dense sets.
:::

:::{.lemma title="?"}
Any nonempty set which is bounded from above (resp. below) has a well-defined supremum (resp. infimum).
:::

## Functions

:::{.proposition title="Existence of Smooth Compactly Supported Functions"}
There exist smooth compactly supported functions, e.g. take 
\[
f(x) = e^{-\frac{1}{x^2}} \chi_{(0, \infty)}(x)
.\]
:::



## Littlewood's Principles ("Almost" Theorems)

:::{.theorem title="Egorov's Theorem"}
Let $E \subseteq \RR^d$ be measurable of positive finite measure with $f_k\to f$ almost everywhere on $E$.
Then for every $\eps > 0$ there is a closed $A_\eps \subseteq E$ with $\mu(E\sm A_\eps) < \eps$ and $f_k\to f$ uniformly on $A_\eps$.
:::

:::{.proof title="of Egorov"}


![](figures/2021-06-11_18-07-43.png)

![](figures/2021-06-11_18-07-58.png)

:::

:::{.theorem title="Lusin's Theorem"}
If $f$ is measurable and finite-valued on $E$ with $\mu(E) < \infty$ then for every $\eps>0$ there exists a closed set $F_\eps$ with
\[
F_\eps \subset F && \mu(E - F_\eps) \leq \eps
\]
where $f$ restricted to $F_\eps$ is continuous.

> Note: this means that the separate function $\tilde f \da \ro{f}{F_\eps}$ is continuous, not that the function $f$ defined on all of $E$ is continuous at points of $F_\eps$.

:::

:::{.proof title="of Lusin"}

![](figures/2021-06-11_18-04-52.png)
:::

## Unsorted

:::{.proposition title="Lipschitz implies uniformly continuous"}
If $f$ is Lipschitz on $X$, then $f$ is uniformly continuous on $X$.

Supposing that
\[
\norm{f(x) - f(y)} \leq C \norm{x-y}
,\]
for a fixed $\eps$ take $\delta(\eps) \da \eps/C$, then
\[
\norm{f(x) - f(y)}
&\leq C \norm{x-y} \\
&\leq C \delta \\
&= C \qty{\eps/C} \\
&= \eps
.\]
:::

:::{.proposition title="Finite unions of nowhere dense sets are still nowhere dense"}
A *finite* union of nowhere dense is again nowhere dense.
:::
