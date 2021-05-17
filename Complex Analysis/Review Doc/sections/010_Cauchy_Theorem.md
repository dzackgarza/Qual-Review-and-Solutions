# Theorems

## Basic Results

:::{.definition title="Complex Integral"}
\[
\int_{\gamma} f d z:=\int_{I} f(\gamma(t)) \gamma^{\prime}(t) \dt
= \int_\gamma (u+iv)\dx \wedge (-v+iu)\dy
.\]
:::

:::{.proposition title="Crude integral estimate"}
Define the *length* of a curve by
\[
\operatorname{len}(\gamma) \da\int_\gamma \abs{\dz} = \int_I \abs{\gamma'(t)} \dt
.\]

Then there is an estimate of the following form:
\[
\left|\int_{\gamma} f d z\right| \leq \int_{\gamma}|f||d z| \leq\left(\sup _{\gamma}|f|\right) \cdot \operatorname{len}(\gamma)
.\]

:::

:::{.exercise title="Primitives imply vanishing integral"}
Show that if $f$ has a primitive $F$ on $\Omega$ then $\int_\gamma f = 0$ for every closed curve $\gamma \subseteq \Omega$.
:::

:::{.theorem title="Goursat"}
If $f$ is analytic on a rectangle $R$ with horizontal and vertical sides, then $\int_{\bd R} f = 0$.
:::

:::{.theorem title="Cauchy's Theorem" ref="CauchyTheorem"}
If $f$ is holomorphic on $\Omega$, then 
\[  
\int_{\bd \Omega} f(z) \, dz = 0
.\]

> Slogan: closed path integrals of holomorphic functions vanish.

:::


## Applications of Cauchy's Theorem

:::{.theorem title="Cauchy Integral Formula" ref="CauchyIntegral"}
Suppose $f$ is holomorphic on $\Omega$, then 
\[
f(z) = {1 \over 2\pi i} \oint_{\bd \Omega} {f(\xi) \over \xi-z}\,d\xi
\]
and
\[
\dd{^nf }{z^n}(z) = {n! \over 2\pi i} \int_{\bd \Omega} {f(\xi) \over (\xi - z)^{n+1}} \,d\xi
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


