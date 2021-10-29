## Morera's Theorem 

:::{.theorem title="Morera's Theorem" ref="Morera"}
If $f$ is continuous on a domain $\Omega$ and $\int_T f = 0$ for every triangle $T\subset \Omega$, then $f$ is holomorphic.
:::

:::{.slogan}
If every integral along a triangle vanishes, implies holomorphic.
:::

:::{.corollary title="Sufficient condition for a sequence to converge to a holomorphic function"}
If \( \ts{ f_n }_{n\in \NN} \) is a holomorphic sequence on a region \( \Omega  \) which uniformly converges to $f$ on every compact subset $K \subseteq \Omega$, then $f$ is holomorphic, and $f_n' \to f'$ uniformly on every such compact subset $K$.
:::

:::{.proof title="?"}
Commute limit with integral and apply Morera's theorem.
:::

:::{.remark}
This can be applied to series of the form $\sum_k f_k(z)$.
:::

### Symmetric Regions

In this section, take $\Omega$ to be a region symmetric about the real axis, so $z\in \Omega \iff \bar{z} \in \Omega$.
Partition this set as $\Omega^+ \subseteq \HH, I \subseteq \RR, \Omega^- \subseteq \bar{\HH}$.

:::{.theorem title="Symmetry Principle"}
Suppose that $f^+$ is holomorphic on $\Omega^+$ and $f^-$ is holomorphic on $\Omega^-$, and $f$ extends continuously to $I$ with $f^+(x) = f^-(x)$ for $x\in I$.
Then the following piecewise-defined function is holomorphic on $\Omega$:
\[
f(z) 
\da
\begin{cases}
f^+(z) & z\in \Omega^+ 
\\
f^-(z) & z\in \Omega^-
\\
f^+(z) = f^-(z) & z\in I.
\end{cases}
\]
:::

:::{.proof title="?"}
Apply Morera?
:::

:::{.theorem title="Schwarz Reflection " ref="SchwarzReflection"}
If $f$ is continuous and holomorphic on $\HH^+$ and real-valued on $\RR$, then the extension defined by $F^-(z) = \bar{f(\bar{z})}$ for $z\in \HH^-$ is a well-defined holomorphic function on $\CC$.
:::

:::{.proof title="?"}
Apply the symmetry principle.
:::

:::{.remark}
$\HH^+, \HH^-$ can be replaced with any region symmetric about a line segment $L\subseteq \RR$.
:::

