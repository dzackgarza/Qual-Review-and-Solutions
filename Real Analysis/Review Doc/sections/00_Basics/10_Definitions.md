---
order: 10
---

# Definitions

## Convergence and Continuity

:::{.definition title="Limsup/Liminf"}
\[  
\limsup_n a_n = \lim_{n\to \infty} \sup_{j\geq n} a_j &= \inf_{n\geq 0} \sup_{j\geq n} a_j \\ 
\liminf_n a_n = \lim_{n\to \infty} \inf_{j\geq n} a_j &= \sup_{n\geq 0} \inf_{j\geq n} a_j
.\]
:::

:::{.definition title="Continuity and Uniform Continuity"}
A function $f: \RR\to \RR$ is **continuous** on $X$ iff for all $x_0\in X$,
\[
&\forall \varepsilon \quad \exists \delta(\varepsilon, x_0) \text{ such that }\quad \forall y, \abs{x_0 - y} < \delta &&\implies \abs{f(x_0) - f(y)} < \varepsilon \\
\iff &\forall \varepsilon \quad \exists \delta(\varepsilon, x_0) \text{ such that }\quad \forall h, \abs{h} < \delta &&\implies \abs{f(x_0) - f(x_0 \pm h)} < \varepsilon
.\]

$f$ is **uniformly continuous** on $X$ iff

\[
  &\forall \varepsilon \quad \exists \delta(\varepsilon) \text{ such that }\quad \forall x, y, \in X \quad \abs{x - y} < \delta &&\implies \abs{f(x) - f(y)} < \varepsilon \\
\iff &\forall \varepsilon \quad \exists \delta(\varepsilon) \text{ such that} \quad \, \forall x, h, \quad \abs{h} < \delta &&\implies \abs{f(x) - f(x \pm h)} < \varepsilon
.\]
These follow from the substitutions $x_0-y = \mp h \implies y = x_0 \pm h$.
:::

:::{.remark}
The main difference is that $\delta$ may depend on $x_0$ and $\eps$ in continuity, but only depends on $\eps$ in the uniform version.
I.e. once $\delta$ is fixed, for continuity one may only range over $x$, but in uniform continuity one can range over all pairs $x,y$.
:::

:::{.definition title="Topological Notions"}
Let $X$ be a metric space and $A$ a subset.
Let $A'$ denote the limit points of $A$, and $\bar{A} \da A\union A'$ to be its closure.

- A **neighborhood** of $p$ is an open set $U_p$ containing $p$.

- An $\eps\dash$**neighborhood** of $p$ is an open ball $B_r(p) \da \ts{q \st d(p, q) < r}$ for some $r>0$.

- A point $p\in X$ is an **accumulation point** or a **limit point** of $A$ iff every *punctured* neighborhood $U_p\sm\ts{p}$ contains a point $q\in A$, so $q\neq p$.

- If $p\in A$ and $p$ is not a limit point of $A$, then $p$ is an **isolated point** of $A$.

- $A$ is **closed**  iff $A' \subset A$, so $A$ contains all of its limit points.

- A point $p\in A$ is **interior** iff there is a neighborhood $U_p \subset A$ that is strictly contained in $A$.

- $A$ is **open** iff every point of $A$ is interior.

- $A$ is **perfect** iff $A$ is closed and $A\subset A'$, so every point of $A$ is a limit point of $A$.

- $A$ is **bounded** iff there is a real number $M$ and a point $q\in X$ such that $d(p, q) < M$ for all $p\in A$.

- $A$ is **dense** in $X$ iff every point $x\in X$ is either a point of $A$, so $x\in A$, or a limit point of $A$, so $x\in A'$.
  I.e., $X\subset A\union A'$.

  - Alternatively, $\bar{A} = X$, so the closure of $A$ is $X$.

:::

:::{.definition title="Pointwise Convergence"}
A sequence of functions \( \ts{ f_j } \)  is said to **converge pointwise** to \( f \) if and only if 
\[  
(\forall \varepsilon>0)(\forall x \in S)\left(\exists n_{0} = n_0(x, \eps) \right)\left(\forall n>n_{0}\right)\left(\left|f_{n}(x)-f(x)\right|<\varepsilon\right)
.\]
:::

:::{.definition title="Uniform Convergence"}
\[
(\forall \varepsilon>0)\left(\exists n_{0} = n_0(\eps) \right)(\forall x \in S)\left(\forall n>n_{0}\right)\left(\left|f_{n}(x)-f(x)\right|<\varepsilon\right)
.\]
Negated:[^Negated_uniform_convergence]
\[  
(\exists \varepsilon>0)\left(\forall n_{0} = n_0 (\eps) \right)(\exists x = x(n_0) \in S)\left(\exists n>n_{0}\right)\left(\left|f_{n}(x)-f(x)\right| \geq \varepsilon\right)
.\]

[^Negated_uniform_convergence]: Slogan: to negate, find a bad $x$ depending on $n_0$ that are larger than some $\eps$.

:::

## Function Spaces

:::{.definition title="Completeness"}
A metric space is **complete** if every Cauchy sequence converges.
:::

:::{.fact}
If $X$ is complete, then absolutely convergent implies convergent.
:::

:::{.definition title="Nowhere Dense Sets"}
Recall that a set $S$ in $X$ is **dense** $\iff$ every open $U\subseteq X$ intersects $S$.
A set $S$ is **nowhere dense** in $X$ $\iff$ the closure of $S$ has empty interior $\iff$ every subset (or interval) contains an open set (or a subinterval) that does not intersect $S$.
This just says $S$ is not dense in any subset $S' \subseteq X$, by negating what it means to be dense.
:::

:::{.definition title="Meager Sets"}
A set is **meager** if it is a *countable* union of nowhere dense sets.
:::

:::{.definition title="Baire Space"}
A space $X$ is a **Baire space** if and only if every countable intersections of open, dense sets is still dense.
:::

## Measure Theory

:::{.definition title="Limsup and Liminf of Sets"}
\[
\liminf_{n} E_{n} \da \Union_{N=1}^\infty \Intersect_{n=N}^\infty E_{n} &= \theset{x \suchthat x\in E_{n} \text{ for all but finitely many } n}  \\
\limsup_{n} E_{n} \da \Intersect_{N=1}^\infty \Union_{n=N}^{\infty} E_{n} &= \theset{x \suchthat x\in E_{n} \text{ for infinitely many } n} 
.\]

  
:::

:::{.remark}
How to derive these definitions: use that $\inf$ corresponds to intersections/existence and $\sup$ corresponds to unions/forall.

- For $\liminf E_n$: 
  - $x\in \liminf E_n \iff$ there exists some $N$ such that $x\in \intersect_{n\geq N} E_n$, i.e. $x\in E_n$ for all $n\geq N$.
    So $x$ is in *all* but finitely many $n$.
  - How to remember:  $\liminf_{n} x_n = \sup_{n} \inf_{k\geq n} x_n$ for sequences, where sups look like unions and infs look like intersections.
  - Alternatively: there exists an $n$ (union) such that for all $k\geq n$ (intersection)...
    

- For $\limsup E_n$: 
  - $x\in \limsup E_n \iff$ for every $N$, there exists some $n\geq N$ such that $x\in E_n$.
    So $x$ is an infinitely many $E_n$.
  - How to remember:  $\limsup_{n} x_n = \inf{n} \sup{k\geq n} x_n$ for sequences, where sups look like unions and infs look like intersections.
  - Alternatively: for all $n$ (intersection) there exists a $k\geq n$ (union)...

It's also useful to note that $\liminf E_n \subseteq \limsup E_n$, since $\liminf E_n$ are elements that are eventually in all sets, and $\limsup E_n$ are elements in infinitely many sets.

Why these are useful: for finite measure spaces,
\[
\mu\qty{\liminf_n E_n }\leq \liminf_n \mu(E_n) \leq \lim_n \mu(E_n) \leq \limsup_n \mu(E_n) \leq \mu\qty{\limsup_n E_n}
.\]
If the $\limsup$ and $\liminf$ sets are equal, then one can define the set $\lim_n E_n \da \union_n E_n$ if $E_n \increasesto E$ or $\lim_n E_n \da \intersect_n E_n$ if $E_n\decreasesto E$ in which case continuity of measure states
\[
\mu\qty{\lim_n E_n} = \lim_n \mu(E_n)
.\]



:::

:::{.definition title="$F_\sigma$ and $G_\delta$ Sets"}
An $F_\sigma$ set is a union of closed sets, and a $G_\delta$ set is an intersection of opens. [^Mnemonic_Ferme]

[^Mnemonic_Ferme]: 
Mnemonic: "F" stands for *ferme*, which is "closed" in French, and $\sigma$ corresponds to a "sum", i.e. a union.

:::

:::{.definition title="Outer Measure"}
The **outer measure** of a set is given by
\[
m_*(E) \da \inf_{\substack{\theset{Q_{i}} \rightrightarrows E \\ \text{closed cubes}}} \sum \abs{Q_{i}}
,\]
where $\abs{Q_i}$ is the standard Euclidean volume of a cube in $\RR^n$.
:::

:::{.definition title="Lebesgue Measurable Sets"}
A subset $E\subseteq \RR^n$ is **Lebesgue measurable** iff for every $\eps> 0$ there exists an open set $O \supseteq E$ such that $m_*(O\setminus E) < \eps$.
In this case, we define $m(E) \da m_*(E)$.
:::

:::{.definition title="$L^+$: Measurable non-negative functions."}
$f\in L^+$ iff $f$ is measurable and non-negative.
:::

## Integrals and $L^p$ Spaces

:::{.definition title="Integrability"}
A measurable function is **integrable** iff $\norm{f}_1 < \infty$.
:::

:::{.definition title="The Infinity Norm / Essential supremum / Essentially bounded"}
\[
\norm{f}_\infty &\definedas \inf_{\alpha \geq 0} \theset{\alpha \suchthat \mu\qty{\theset{\abs{f} \geq \alpha}} = 0}
.\]
In words, this is the smallest upper bound that holds almost everywhere, so $\abs{f(x)} \leq \norm{f}_\infty$ holds for almost every $x$.
A function $f:X \to \CC$ is **essentially bounded** iff there exists a real number $c$ such that $\mu(\theset{\abs{f} > x}) = 0$, i.e. $\norm{f}_\infty < \infty$.
:::

:::{.definition title="$L^\infty$"}
\[
L^\infty(X)
\definedas \theset{f: X\to \CC \suchthat f \text{ is essentially bounded }}
\definedas \theset{f: X\to \CC \suchthat \pnorm{f}\infty < \infty}
.\]

:::

:::{.definition title="Convolution"}
$$f * g(x)=\int f(x-y) g(y) d y .$$
:::

:::{.definition title="Fourier Transform"}
\[
\hat f(\xi) = \int f(x) ~e^{2\pi i x \cdot \xi} ~dx
.\]

:::

:::{.definition title="Dilation"}
\[
\phi_{t}(x) = t^{-n} \phi\left(t^{-1} x\right)
.\]
:::

:::{.definition title="Approximations to the identity"}
For $\phi\in L^1$, the dilations satisfy $\int \phi_{t} = \int \phi$, and if $\int \phi = 1$ then $\phi$ is an **approximate identity**. 
:::

## Functional Analysis

:::{.definition title="Dual Norm"}
For $X$ a normed vector space and $L \in X\dual$, the **dual norm** or **operator norm** is defined by
\[
\norm{L}_{X\dual} 
\da \sup_{ \substack{x\in X \\ \norm{x} = 1} } \abs{L(x)}
= \sup_{ \substack{x\in X \\ \norm{x} \leq  1} } \abs{L(x)}
.\]

:::

:::{.definition title="Orthonormal sequence "}
A countable collection of elements \( \ts{ u_i } \)  is **orthonormal** if and only if 

1. \( \inner{u_i}{u_j} = 0 \) for all \( j \neq k \) and
2. \( \norm{u_j}^2 \da \inner{u_j}{u_j} = 1 \) for all \( j \).  

:::

:::{.definition title="Basis of a Hilbert space"}
A set $\theset{u_{n}}$ is a **basis** for a Hilbert space $\mch$ iff it is dense in $\mch$.
:::

:::{.definition title="Completeness of a Hilbert space"}
A collection of vectors $\theset{u_{n}}\subset H$ is **complete** iff $\inner{x}{u_{n}} = 0$ for all $n \iff x = 0$ in $H$.
:::

:::{.definition title="Dual of a Hilbert space"}
The **dual** of a Hilbert space \( H \) is defined as 
\[
H\dual \da \theset{L: H\to \CC \suchthat L \text{ is continuous }}
.\]

:::

:::{.definition title="Linear functionals"}
A map $L: X \to \CC$ is a **linear functional** iff
\[
L(\alpha\vector x + \vector y) = \alpha L(\vector x) + L(\vector y).
.\]
:::

:::{.definition title="Banach Space"}
A space is a **Banach space** if and only if it is a complete normed vector space.
:::

:::{.definition title="Hilbert Space"}
A **Hilbert space** is an inner product space which is a Banach space under the induced norm.
:::
