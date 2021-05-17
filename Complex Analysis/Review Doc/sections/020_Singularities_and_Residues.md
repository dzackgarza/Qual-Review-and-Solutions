# Singularities

:::{.definition title="Poles (and associated terminology)"}
A *pole* $z_0$ of a meromorphic function $f(z)$ is a zero of $g(z) \definedas {1\over f(z)}$.
If there exists an $n$ such that
\[  
\lim_{z\to z_0}\qty{z-z_0}^nf(z)
\]
is holomorphic and nonzero in a neighborhood of $z_0$, then the minimal such $n$ is the *order* of the pole.
A pole of order 1 is said to be a *simple pole*.

The pole $z_0$ is *isolated* iff there exists a neighborhood of $z_0$ containing no other poles of $f$.
:::

:::{.definition title="Principal Part and Residue"}
In a Laurent series $f(z) \definedas \sum_{n\in \ZZ} c_n (z-z_0)^n$, the *principal part of $f$ at $z_0$* consists of terms with negative degree:
\[  
P_f(z) \definedas \sum_{n=1}^\infty c_{-n}(z-z_0)^{-n}
.\]

The *residue* of $f$ at $z_0$ is the coefficient $c_{-1}$.
:::

:::{.definition title="Removable Singularities"}
If $z_0$ is a singularity of $f$ and there exists a $g$ such that $f(z) = g(z)$ for all $z$ in some deleted neighborhood $U\setminus\theset{z_0}$, then $z_0$ is a *removable singularity* of $f$.
:::

:::{.definition title="Essential Singularity"}
A singularity $z_0$ is *essential* iff it is neither removable nor a pole.

Equivalently, a Laurent series expansion about $z_0$ has a principal part with infinitely many terms.
:::

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

