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

- Suppose $p$ is nonconstant and has no roots, then ${1\over p}$ is entire
- Write $g(z) \definedas \frac{p(z)}{z^{n}}=a_{n}\left(\frac{a_{n-1}}{z}+\dots+\frac{a_{0}}{z^{n}}\right)$
- Outside a disc:
  - Note $\lim_{z\to \infty} = 0$ for the parenthesized terms, so there exists an $R$ large enough such that $\abs{g(z)} \geq {1\over 2} \abs{a_n}$
  - Then $\abs{p(z)} \geq {R^n\over 2} \abs{a_n}$ implies ${1\over p}$ is bounded in $\abs{z} > R$
- Inside a disc:
  - $p$ is continuous with no roots so $p$ is bounded below on $\abs{z} < R$.
  - $p$ is continuous on a compact set and thus achieves a min $A$
  - Set $B = \min(A, {R^n \over 2} \abs{a_n})$, then $p \geq B$ on $\abs{z} < R$.
- Thus $p$ is bounded below everywhere and thus ${1\over p}$ is bounded above everywhere, thus bounded.
- Thus ${1\over p}$ is constant, forcing $p$ to be constant.

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
