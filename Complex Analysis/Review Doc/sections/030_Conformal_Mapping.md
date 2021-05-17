# Conformal Maps


:::{.fact}
A bijective holomorphic map automatically has a holomorphic inverse.
This can be weakened: an injective holomorphic map satisfies $f'(z) \neq 0$ and $f ^{-1}$ is well-defined on its range and holomorphic.
:::



## Plane to Disc

\[
\phi: \HH &\to \DD \\
\phi(z) &= {z - i \over z + i} \qquad f\inv(z) = i\qty{1 + w \over 1 - w}
.\]

## Sector to Disc

For $S_\alpha \da \theset{z\in\CC \suchthat 0 < \arg(z) < \alpha }$ an open sector for $\alpha$ some angle, first map the sector to the half-plane:
\[
g: S_\alpha &\to \HH \\
g(z) &= z^{\pi \over \alpha}
.\]

Then compose with a map $\HH\to\DD$:
\[
f: S_\alpha &\to \DD \\
f(z) &= (\phi \circ g)(z) = {z^{\pi\over \alpha} - i \over z^{\pi\over\alpha} + i}
.\]

![](figures/image_2020-07-22-13-22-46.png)

## Strip to Disc

- Map to horizontal strip by rotation $z\mapsto \lambda z$.
- Map horizontal strip to sector by $z \mapsto e^z$
- Map sector to $\HH$ by $z\mapsto z^{\pi\over\alpha}$.
- Map $\HH\to\DD$.



