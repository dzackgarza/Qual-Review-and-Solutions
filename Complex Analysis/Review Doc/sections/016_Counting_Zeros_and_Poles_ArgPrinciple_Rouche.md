# Counting Zeros and Poles

## Argument Principle



:::{.definition title="The logarithmic derivative"}
The **logarithmic derivative** is defined as 
\[
\del_{\log} f \da {f' \over f}
.\]
It converts all poles and zeros of $f$ into simple poles of $\del_{\log f}$.
:::

:::{.exercise title="?"}
Show that $\del_{\log}(fg) = \del_{\log} f + \del_{\log} g$, i.e. 
\[
{ (fg)' \over fg} = {f'\over f} + {g' \over g}
.\]
:::

:::{.definition title="Winding Number"}
For $\gamma \subseteq \Omega$ a closed curve not passing through a point $z_0$, the **winding number of $\gamma$ about $z_0$** (or the **index**) is defined as
\[
\Ind_{z=z_0}(\gamma) \da {1\over 2\pi i} \int_\gamma {1\over \xi -z_0}\dxi
.\]

:::

:::{.theorem title="Argument Principle, Zeros/Poles Version"}
For $f$ meromorphic in $\Omega$ with multisets of zeros \( Z_f \da \ts{ z_j } \) and poles \( P_f\da \ts{ p_k } \) (so repeated with multiplicity) 
for $\gamma \da \bd \Omega$ not intersect
\[  
{1\over 2\pi i} \int_\gamma \del_{\log} f(z) \dz
&= \# Z_f - \# P_f
,\]
where $\# Z_f$ and $\# P_f$ are the number of zeros and poles respectively, counted with multiplicity.
:::

:::{.proof title="?"}
\envlist

- If $z_0$ is a zero of $f$ of order $m$, write $f(z) = (z-z_0)^m g(z)$ with $g(z)$ holomorphic and nonzero on some neighborhood of $z_0$.
- Compute
\[
\del_{\log} f(z)
&=
\frac{m\left(z-z_{0}\right)^{m-1} g(z)+\left(z-z_{0}\right)^{m} g^{\prime}(z)}{\left(z-z_{0}\right)^{m} g(z)} \\
&= {m \over z-z_0} + \del_{\log} g(z)
,\]
so $z_0$ is a simple pole of $\del_{\log} f$ and $\res_{z=z_0} \del_{\log} f = m$.

- If $z_0$ is a pole of $f$ of order $m$, write $f(z) = (z-z_0)^{-m} g(z)$, then
\[
\del_{\log} f = {-m \over z-z_0} + \del_{\log} g
,\]
  so $z_0$ is a simple pole and $\Res_{z=z_0} \del_{\log f} = -m$.

- Now apply the residue theorem, and group residues according to sign:
\[
{1\over 2\pi i } \int_{\gamma} \del_{\log }f(z) \dz 
&= \sum_{z_i \in P_{\del_{\log} f}} \Res_{z=z_i} \del_{\log} f(z)\\
&= \sum_{z_k \in Z_f} \Res_{z=z_k} f(z) - \sum_{z_j \in P_f} \Res_{z=z_j} f(z)
.\]

:::

:::{.theorem title="Argument Principle, Index Version"}
With the same setup as above, 
\[
{1\over 2\pi i} \int_\gamma \del_{\log} f(z) \dz
&= \Ind_{w=0}(f\circ \gamma)(w)
.\]


:::

:::{.proof title="?"}
Make the change of variables $w = f(z)$, then $z=\gamma(t) \mapsto w = (f\circ \gamma)(t)$ and $\dw = f'(z) \dz$, so
\[
{1\over 2\pi i }\int_{\gamma} \del_{\log} f(z) \dz 
= {1\over 2\pi i} \int_{f\circ \gamma} {1\over w} \dw \da \Ind_{w=0} (f\circ \gamma)(w)
.\]


:::


:::{.example title="Using the index version of the argument principle"}
Let $f(z) = z^2 + z = z(z+1)$.

- $\gamma_1 \da \ts{\abs z = 2}$ contains 2 zeros and 0 poles, so $f\circ \gamma$ winds twice around zero counterclockwise.
- $\gamma_2 \da \ts{\abs z = {1\over 2}}$ contains 1 zero and 0 poles, so $f\circ \gamma$ winds once.

:::

## Rouché 

:::{.theorem title="Rouché's Theorem" ref="Rouche"}
If

- $f, g$ are meromorphic on $\Omega$
- $\gamma \subset \Omega$ is a toy contour winding about each zero/pole of $f, g$ exactly once,
- $\abs{g} < \abs{f}$ on $\gamma$

then
\[
\Ind_{z=0}(f\circ \gamma)(z) = \Ind_{z=0}((f+g)\circ \gamma)(z) \implies Z_f - P_f = Z_{f+g} - P_{f+g}
.\]
In particular, if $f, g$ are holomorphic, they have the same number of zeros in $\Omega$.

:::

\todo[inline]{Prove}

:::{.corollary title="Open Mapping"}
Any holomorphic non-constant map is an open map.
:::

\todo[inline]{Prove}

:::{.corollary title="Maximum Modulus" ref="MaximumModulus"}
If $f$ is holomorphic and nonconstant on an open connected region $\Omega$, then $\abs{f}$ can not attain a maximum on $\Omega$.
If $\Omega$ is bounded and $f$ is continuous on $\bar \Omega$, then $\max_{\bar \Omega} \abs{f}$ occurs on $\bd \Omega$.
Conversely, if $f$ attains a local supremum at $z_0 \in \Omega$, then $f$ is constant on $\Omega$.
:::

\todo[inline]{Prove}

:::{.corollary title="?"}
If $f$ is nonzero on $\Omega$, then $f$ attains a minimum on $\bd \Omega$.
This follows from applying the MMP to $1/f$.
:::

## Counting Zeros 

:::{.example}
\envlist

- Take $P(z) = z^4 + 6z + 3$.
- On $\abs{z} < 2$:
  - Set $f(z) = z^4$ and $g(z) = 6z + 3$, then $\abs{g(z)} \leq 6\abs{z} + 3 = 15 < 16= \abs{f(z)}$.
  - So $P$ has 4 zeros here.
- On $\abs{z} < 1$:
  - Set $f(z) = 6z$ and $g(z) = z^4 + 3$.
  - Check $\abs{g(z)} \leq \abs{z}^4 + 3 = 4 < 6 = \abs{f(z)}$.
  - So $P$ has 1 zero here.
:::

:::{.example}
\envlist 

- Claim: the equation $\alpha z e^z = 1$ where $\abs{\alpha} > e$ has exactly one solution in $\DD$.
- Set $f(z) = \alpha z$ and $g(z) = e^{-z}$.
- Estimate at $\abs{z} =1$ we have $\abs{g} =\abs{e^{-z}} = e^{-\Re(z)} \leq e^1 < \abs{\alpha} = \abs{f(z)}$
- $f$ has one zero at $z_0 = 0$, thus so does $f+g$.
:::

