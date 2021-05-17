# Residues

:::{.remark}
Check: do you need residues? 
You may be able to just compute an integral 

- Directly by parameterization:
\[
\int_\gamma f = \int_a^b f(z(t))\, z'(t) && \text{for } z(t) \text{ a parameterization of } \gamma
,\]

- Finding a primitive $F$,

- Writing $z= z_0 + re^{i \theta }$

:::


:::{.proposition title="Residue formula for higher order poles"}
If $f$ has a pole $z_0$ of order $n$, then
\[  
\Res_{z=z_0} f = \lim_{z\to z_0} {1 \over (n-1)!} \qty{\dd{}{z}}^{n-1} (z-z_0)^n f(z)
.\]
:::

:::{.proposition title="Residue formula for simple poles"}
As a special case, if $z_0$ is a simple pole of $f$, then
\[  
\Res_{z=z_0}f = \lim_{z\to z_0} (z-z_0) f(z)
.\]
:::

:::{.example title="Residue of a simple pole (order 1)"}
Let $f(z) = \frac{1}{1+z^2}$, then $\Res(i, f) = \frac{1}{2i}$.
:::


:::{.theorem title="The Residue Theorem"}
Let $f$ be meromorphic on a region $\Omega$ with poles \( \ts{ \elts{z}{N} } \).
Then for any $\gamma \in \Omega\sm \ts{ \elts{z}{N} }$, 
\[
{1 \over 2\pi i } \int_\gamma f(z) \dz = \sum_{j=1}^N n_\gamma(z_j) \Res_{z=z_j} f
.\]
If $\gamma$ is a toy contour, then  
\[
{1\over 2\pi i}\int_\gamma f\dz = \sum_{j=1}^N \Res_{z=z_j}f
.\]


:::

