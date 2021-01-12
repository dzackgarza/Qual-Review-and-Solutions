# Residues


:::{.remark}
Check: do you need residues? 
You may be able to just compute an integral directly:
\[
\int_\gamma f = \int_a^b f(z(t))\, z'(t) && \text{for } z(t) \text{ a parameterization of } \gamma
.\]

:::


:::{.theorem title="Cauchy's Inequality" ref="CauchyInequality"}
For $z_0 \in D_R(z_0) \subset \Omega$, we have
\[
\abs{ f^{(n)} (z_0) } 
\leq \frac{n !}{2 \pi} \int_{0}^{2 \pi} \frac{ \norm{f}_{\infty} } {R^{n+1}} R \,d\theta
= \frac{n !\norm{f}_{\infty}}{R^n} 
,\]
where $\norm{f}_{\infty}\definedas \sup_{z\in C_R} \abs{f(z)}$.

:::{.slogan}
The $n$th Taylor coefficient of an analytic function is at most $\sup_{\abs z = R} \abs{f}/R^n$.
:::


:::

:::{.proof}
\envlist
- Given $z_0\in \Omega$, pick the largest disc $D_R(z_0) \subset \Omega$ and let $C_R = \bd D_R$.
- Then apply the integral formula.
:::

:::{.theorem title="The Residue Theorem"}
If $f$ is holomorphic on an open set $\Omega$ containing a curve $\gamma$ and its interior $\gamma^\circ$, except for finitely many poles $\theset{z_k}_{k=1}^N \subset \gamma^\circ$.
Then
\[  
\int_\gamma f(z) \,dz = 2\pi i \sum_{k=1}^N \res_{z_k} f
.\]
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

