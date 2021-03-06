# Counting Zeros and Poles

## Argument Principle

:::{.definition title="Winding Number"}
For $\gamma \subseteq \Omega$ a closed curve not passing through a point $z_0$, the **winding number of $\gamma$ about $z_0$** is defined as
\[
n_\gamma(z_0) \da {1\over 2\pi i} \int_\gamma {1\over \xi -z_0}\dxi
.\]

:::

:::{.theorem title="Argument Principle"}
For $f$ meromorphic in $\gamma^\circ$ with zeros \( \ts{ z_j } \) and poles \( \ts{ p_k } \) repeated with multiplicity where $\gamma$ does not intersect any zeros or poles, then
\[  
\Delta_\gamma \arg f(z) \da {1\over 2\pi i} \int_\gamma {f'(z) \over f(z)} \dz = \sum_{j} n_\gamma(z_j) - \sum_k n_\gamma(p_k) = Z_f - P_f
,\]
where $Z_f$ and $P_f$ are the number of zeros and poles respectively enclosed by $\gamma$, counted with multiplicity.
:::

:::{.proof title="?"}
Residue formula applied to $f'\over f$?
:::

![](figures/2021-06-16_16-42-18.png)


:::{.remark}
This is useful in numerical computation: if you can compute this integral within an error $E < \pi$ where you know it doesn't contain a pole, you can determine if the contour contains a zero.
Canonical example: integrals in rectangles around $\Re(z) = 1/2$ for $\zeta(s)$.
:::


:::{.exercise title="?"}
Show that $\del_{\ln}(fg) = \del_{\ln} f + \del_{\ln} g$, and thus
\[
\frac{f^{\prime}(x)}{f(x)}=\frac{g^{\prime}(x)}{g(x)}+\frac{h^{\prime}(x)}{h(x)}
.\]
:::




## Rouché 
:::{.corollary title="Rouché's Theorem" ref="Rouche"}
If $f, g$ are analytic on a domain $\Omega$ with finitely many zeros in $\Omega$ and $\gamma \subset \Omega$ is a closed curve surrounding each point exactly once, where $\abs{g} < \abs{f}$ on $\gamma$, then $f$ and $f+g$ have the same number of zeros.

Alternatively:

Suppose $f = g + h$ with $g \neq 0, \infty$ on $\gamma$ with $\abs g > \abs h$ on $\gamma$.
Then $$\Delta_\gamma \arg(f) = \Delta_\gamma \arg(h)\quad\text{ and } Z_f - P_f = Z_g - P_g.$$
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

