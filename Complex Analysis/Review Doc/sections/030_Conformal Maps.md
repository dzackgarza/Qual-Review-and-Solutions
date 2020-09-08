# Conformal Maps

Notation: 

- $S \definedas \theset{x + iy \suchthat x\in \RR,\, 0<y<\pi}$.
- $\DD$ the disc
- $\HH$ the upper half plane
- $X_{1\over 2}$: a "half" version of $X$.

:::{.theorem title="Classification of Conformal Maps"}
There are 8 major types of conformal maps:

| Type/Domains | Formula | 
| ------------ | ------- |
| Translation/Dilation/Rotation | $z\mapsto e^{i\theta}(cz + h)$ |
| Sectors to sectors | $z\mapsto z^n$ |
| $\DD_{1\over 2} \to \HH_{1\over 2}$, the first quadrant | $z\mapsto {1+z \over 1-z}$ |
| $\HH\to S$ | $z\mapsto \log(z)$ | 
| $\DD_{1\over 2} \to S_{1\over 2}$ | $z\mapsto \log(z)$ |
| $S_{1\over 2} \to \DD_{1\over 2}$ | $z\mapsto e^{iz}$ |
| $\DD_{1\over 2} \to \HH$ |  $z\mapsto {1\over 2}\qty{z + {1\over z}}$ |
| $S_{1\over 2} \to \HH$ | $z\mapsto \sin(z)$ |

:::

Conformal maps $\DD\to\DD$ have the form
\begin{align*}
g(z) = \lambda {1-a \over 1 - \bar a z}, \quad \abs{a} < 1, \quad \abs{\lambda} = 1
.\end{align*}

## Plane to Disc

\begin{align*}
\phi: \HH &\to \DD \\
\phi(z) &= {z - i \over z + i} \qquad f\inv(z) = i\qty{1 + w \over 1 - w}
.\end{align*}

## Sector to Disc

For $S_\alpha \definedas \theset{z\in\CC \suchthat 0 < \arg(z) < \alpha }$ an open sector for $\alpha$ some angle, first map the sector to the half-plane:
\begin{align*}
g: S_\alpha &\to \HH \\
g(z) &= z^{\pi \over \alpha}
.\end{align*}

Then compose with a map $\HH\to\DD$:
\begin{align*}
f: S_\alpha &\to \DD \\
f(z) &= (\phi \circ g)(z) = {z^{\pi\over \alpha} - i \over z^{\pi\over\alpha} + i}
.\end{align*}

![](figures/image_2020-07-22-13-22-46.png)

## Strip to Disc

- Map to horizontal strip by rotation $z\mapsto \lambda z$.
- Map horizontal strip to sector by $z \mapsto e^z$
- Map sector to $\HH$ by $z\mapsto z^{\pi\over\alpha}$.
- Map $\HH\to\DD$.


:::{.theorem title="Riemann Mapping"}
If $\Omega$ is simply connected, nonempty, and not $\CC$, then for every $z_0\in \Omega$ there exists a unique conformal map $F:\Omega \to \DD$ such that $F(z_0) = 0$ and $F'(z_0) > 0$.

Thus any two such sets $\Omega_1, \Omega_2$ are conformally equivalent.
:::

