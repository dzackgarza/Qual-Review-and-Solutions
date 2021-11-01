---
order: 30
---

# Continuity

:::{.lemma title="Function discontinuous on the rationals"}
There is a function discontinuous precisely on $\QQ$.
:::

:::{.proof title="?"}
$f(x) = \frac 1 n$ if $x = r_n \in \QQ$ is an enumeration of the rationals, and zero otherwise.
The limit at every point is 0.
:::

:::{.proposition title="No functions discontinuous on the irrationals"}
There *do not* exist functions that are discontinuous precisely on $\RR\setminus \QQ$.
:::

:::{.proof title="?"}
$D_f$ is always an $F_\sigma$ set, which follows by considering the oscillation $\omega_f$.
Use that $\omega_f(x) = 0 \iff f$ is continuous at $x$, and $D_f = \union_n A_{\frac 1 n}$ where $A_\varepsilon = \theset{\omega_f \geq \varepsilon}$ is closed.
:::

