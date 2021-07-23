# Fixed Points and Degree Theory

:::{.fact title="Useful properties of the degree of a map between spheres"}
\envlist

- $\text{deg}~\id_{S^n} = 1$

- $\text{deg} (f\circ g) = \text{deg}~f \cdot \text{deg}~g$

- $\text{deg}~r = -1$ where $r$ is any rotation about a hyperplane, i.e. $r(\thevector{x_1 \cdots x_i \cdots x_n}) = \thevector{x_1 \cdots -x_i \cdots x_n}$.

- The antipodal map on $S^n\subset \RR^{n+1}$ is the composition of $n+1$ reflections, so $\text{deg}~\alpha = (-1)^{n+1}$.
:::

:::{.theorem title="Lefschetz Fixed Point"}
For $f:X\to X$, define the **trace** of $f$ to be
\[
\Lambda_f \da \sum_{k \geq 0} (-1)^k ~\mathrm{Tr}(f_* \mid H_k(X; \QQ))
\]
where $f_*: H_k(X; \QQ) \to H_k(X; \QQ)$ is the induced map on homology.
If $\Lambda_f \neq 0$ then $f$ has a fixed point.
:::

:::{.theorem title="?"}
Every $f: B^n \to B^n$ has a fixed point.
:::

:::{.proof title="?"}

:::
\todo[inline]{Proof}

:::{.theorem title="Hairy Ball"}
There is no non-vanishing tangent vector field on even dimensional spheres $S^{2n}$.
:::

:::{.theorem title="Borsuk-Ulam"}
For every $S^n \mapsvia{f} \RR^n \exists x\in S^n$ such that $f(x) = f(-x)$.
:::
