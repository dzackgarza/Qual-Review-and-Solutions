# Fixed Points and Degree Theory

:::{.fact title="Useful properties of the degree of a map between spheres"}
\envlist

- The degree of a constant map is 0.

- $f\homotopic g \iff \deg f = \deg g$, since this implies $f_* = g_*$.

- If $f$ is a homotopy equivalence, $\abs{\deg f} = 1$.
  - This is because $f\homotopic g \implies H_*(f) = H_*(g)$.

- $\deg\id_{S^n} = 1$

- $\text{deg} (f\circ g) = \degf \cdot \degg$

- $\deg(H_{x_i}) = -1$ for $H_{x_i}$ any rotation about the hyperplane $x_i = 0$, i.e. 
\[
H_{x_i}: \RR^{n+1} &\to \RR^{n+1} \\
\tv{x_1, \cdots, x_i, \cdots, x_{n+1}} 
&\mapsto
\tv{x_1, \cdots, - x_i, \cdots, x_{n+1}} 
.\]

- The antipodal map on $S^n\subset \RR^{n+1}$ is the composition of $n+1$ hyperplane reflections, so $\deg\alpha = (-1)^{n+1}$.
  - As a consequence, if $\deg f$ is even then $f$ is not homotopic to the antipodal map.

:::


:::{.exercise title="No fixed points implies homotopic to antipodal"}
Show that if $f: S^n\to S^n$ has no fixed points $\iff \deg f = (-1)^{n+1}$ and $f$ is homotopic to the antipodal map.
:::

:::{.concept}
\envlist

- If $f(x)\neq x$, the line segment $L(-x, f(x))$ does not contain $0$. 

- If $f(x) \neq -x$, the line segment $L(x, f(x))$ does not contain $0$.
:::

:::{.solution}
The straight line homotopy $H(t, x) = (1-t)f(x) + t(-x)$ is a homotopy between $f$ and the antipodal map in $\RR^{n+1}$.
Use that $H(t, x) = 0 \iff t=1/2 \iff f(x) = x$, so $H(t, \wait)$ is always a line from $x$ to $f(x)$ not passing through $0$, so $H(t, \wait) \neq 0$. 
So this descends to a homotopy of $\RR^{n+1}\smz \homotopic S^n$, or explicitly one can project
\[
H: I\cross S^n &\to S^n \\
(t, x) &\mapsto {H(t, x) \over \norm{H(t, x)}}
.\]

Less explicitly: if $f(x) \neq x$ for all $x\in S^n$, there is a unique geodesic through these two points, so let each point flow along its corresponding geodesic.
:::


:::{.exercise title="?"}
Show that if $f$ is not surjective then $\deg f = 0$.

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
