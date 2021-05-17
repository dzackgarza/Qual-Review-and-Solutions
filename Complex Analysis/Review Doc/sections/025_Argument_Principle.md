# Rouche 

## Counting Zeros 

:::{.example}
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
- Claim: the equation $\alpha z e^z = 1$ where $\abs{\alpha} > e$ has exactly one solution in $\DD$.
- Set $f(z) = \alpha z$ and $g(z) = e^{-z}$.
- Estimate at $\abs{z} =1$ we have $\abs{g} =\abs{e^{-z}} = e^{-\Re(z)} \leq e^1 < \abs{\alpha} = \abs{f(z)}$
- $f$ has one zero at $z_0 = 0$, thus so does $f+g$.
:::
