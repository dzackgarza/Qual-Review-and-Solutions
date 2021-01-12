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

:::{.proof title="of Cauchy's inequality"}
\envlist
- Given $z_0\in \Omega$, pick the largest disc $D_R(z_0) \subset \Omega$ and let $C_R = \bd D_R$.
- Then apply the integral formula.
:::


:::{.proposition title="Residues for simple poles (order 1)"}
If $z_0$ is a simple pole of $f$, then
\[  
\res_{z_0}f = \lim_{z\to z_0} (z-z_0) f(z)
.\]
:::

:::{.example title="Residue of a simple pole (order 1)"}
Let $f(z) = \frac{1}{1+z^2}$, then $\Res(i, f) = \frac{1}{2i}$.
:::

:::{.proposition title="For higher order poles"}
If $f$ has a pole $z_0$ of order $n$, then
\[  
\res_{z=z_0} f = \lim_{z\to z_0} {1 \over (n-1)!} \qty{\dd{}{z}}^{n-1} (z-z_0)^n f(z)
.\]
:::

