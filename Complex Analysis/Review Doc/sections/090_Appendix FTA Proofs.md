# Unsorted Theorems





:::{.theorem title="Riemann's Removable Singularity Theorem"}
If $f$ is holomorphic on $\Omega$ except possibly at $z_0$ and $f$ is bounded on $\Omega\setminus\theset{z_0}$, then $z_0$ is a removable singularity.
:::



:::{.theorem title="Little Picard"}
If $f:\CC\to \CC$ is entire and nonconstant, then $\im(f)$ is either $\CC$ or $\CC\sm\ts{z_0}$ for some point $z_0$.
:::
\todo{???}


:::{.corollary}
The ring of holomorphic functions on a domain in $\CC$ has no zero divisors.
:::

:::{.proof}
???
:::
\todo[inline]{Find the proof!}

Morera

:::{.proposition title="Bounded Complex Analytic Functions form a Banach Space"}
For $\Omega\subseteq\CC$, show that $A(\CC)\definedas \theset{f: \Omega \to \CC \st f\text{ is bounded}}$ is a Banach space.
:::

:::{.proof}
?

> Apply Morera's Theorem and Cauchy's Theorem

:::


# Appendix: Proofs of the Fundamental Theorem of Algebra

### Fundamental Theorem of Algebra: Argument Principle 

- Let $P(z) = a_nz^n + \cdots + a_0$ and $g(z) = P'(z)/P(z)$, note $P$ is holomorphic
- Since $\lim_{\abs z \to \infty} P(z) = \infty$, there exist an $R>0$ such that $P$ has no roots in $\theset{\abs{z} \geq R}$.
- Apply the argument principle:
\begin{align*}
N(0) = {1\over 2\pi i} \oint_{\abs{\xi} = R} g(\xi) \,d\xi
.\end{align*}
- Check that $\lim_{\abs{z\to \infty}}zg(z) = n$, so $g$ has a simple pole at $\infty$
- Then $g$ has a Laurent series ${n\over z} + {c_2 \over z^2} + \cdots$
- Integrate term-by-term to get $N(0) = n$.



### Fundamental Theorem of Algebra: Rouche's Theorem

- Let $P(z) = a_nz^n + \cdots + a_0$
- Set $f(z) = a_n z^n$ and $g(z) = P(z) - f(z) = a_{n-1}z^{n-1} + \cdots + a_0$, so $f+g = P$.
- Choose $R > \max\qty{ { \abs{a_{n-1}} + \cdots + \abs{a_0} \over \abs{a_n} }, 1}$, then

\begin{align*}
|g(z)| 
&\definedas |a_{n-1}z^{n-1} + \cdots + a_1 z + a_0 | \\
&\leq |a_{n-1}z^{n-1}| + \cdots + |a_1 z| + |a_0 | \quad\text{by the triangle inequality} \\
&= |a_{n-1}|\cdot |z^{n-1}| + \cdots + |a_1|\cdot| z| + |a_0 | \\
&=  |a_{n-1}|\cdot R^{n-1} + \cdots + |a_1| R + |a_0 | \\
&\leq |a_{n-1}|\cdot R^{n-1}+|a_{n-2}|\cdot R^{n-1} + \cdots + |a_1| \cdot R^{n-1} + |a_0 |\cdot R^{n-1} \quad\text{since } R>1 \implies R^{a+b} \geq R^a \\
&= R^{n-1} \left( |a_{n-1}| + |a_{n-2}| + \cdots + |a_1| + |a_0| \right) \\
&\leq R^{n-1} \left( |a_n|\cdot R \right) \quad\text{by choice of } R   \\
&= R^{n} |a_n| \\
&= |a_n z^n| \\
&\definedas  |f(z)|
\end{align*}

- Then $a_n z^n$ has $n$ zeros in $\abs{z} < R$, so $f+g$ also has $n$ zeros.

### Fundamental Theorem of Algebra: Liouville's Theorem


- Suppose $p$ is nonconstant and has no roots, then ${1\over p}$ is entire.
  We will show it is also bounded and thus constant, a contradiction.
- Write $p(z) = z^n \left(a_n + \frac{a_{n-1}}{z}+\dots+\frac{a_{0}}{z^{n}}\right)$
- Outside a disc:
  - Note that $p(z) \converges{z\to \infty }\to \infty$. so there exists an $R$ large enough such that $\abs{p(z)} \geq {1\over A}$ for any fixed chosen constant $A$.
  - Then $\abs{ 1/p(z)} \leq A$ outside of $\abs{z} >R$, i.e. $1/p(z)$ is bounded there.
- Inside a disc:
  - $p$ is continuous with no roots and thus must be bounded below on $\abs{z} < R$.
  - $p$ is entire and thus continuous, and since $\bar{D}_r(0)$ is a compact set, $p$ achieves a min $A$ there
  - Set $C \da \min(A, B)$, then $\abs{p(z)} \geq C$ on all of $\CC$ and thus $\abs{1/p(z)} \leq C$ everywhere. 
  - So $1/p(z)$ is bounded an entire and thus constant by Liouville's theorem -- but this forces $p$ to be constant. $\contradiction$

### Fundamental Theorem of Algebra: Open Mapping Theorem

- $p$ induces a continuous map $\CP^1 \to \CP^1$
- The continuous image of compact space is compact; 
- Since the codomain is Hausdorff space, the image is closed.
- $p$ is holomorphic and non-constant, so by the Open Mapping Theorem, the image is open.
- Thus the image is clopen in $\CP^1$.
- The image is nonempty, since $p(1) = \sum a_i \in \CC$
- $\CP^1$ is connected
- But the only nonempty clopen subset of a connected space is the entire space.
- So $p$ is surjective, and $p\inv(0)$ is nonempty.
- So $p$ has a root.
