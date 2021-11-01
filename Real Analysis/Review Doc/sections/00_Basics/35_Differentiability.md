---
order: 35
---

# Differentiability

:::{.proposition title="Lipschitz $\iff$ differentiable with bounded derivative."}
A function $f: (a, b) \to \RR$ is Lipschitz $\iff f$ is differentiable and $f'$ is bounded.
In this case, $\abs{f'(x)} \leq C$, the Lipschitz constant.
:::

:::{.theorem title="Term by Term Differentiability Theorem"}
If $f_n$ are differentiable, $\sum f_n' \to g$ uniformly, and there exists one point[^pointwise_works_too] $x_0$ such that $\sum f_n(x)$ converges, then there exist an $f$ such that $\sum f_n \to f$ uniformly and $f' = g$.[^theorem_referfence_6.4.3_Abbott]

[^theorem_referfence_6.4.3_Abbott]: See Abbott theorem 6.4.3, pp 168.

[^pointwise_works_too]: So this implicitly holds if $f$ is the pointwise limit of $f_n$.

:::
