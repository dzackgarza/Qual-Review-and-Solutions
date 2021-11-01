---
order: 50
---

# Commuting Limiting Operations

:::{.proposition title="Limits of bounded functions need not be bounded"}
\[  
\lim_{n\to \infty}\sup_{x\in X} \abs{f_n(x) } \neq \sup_{x\in X} \abs{\lim_{n\to\infty} f_n(x) }
.\]
:::

:::{.proposition title="Limits of continuous functions need not be continuous"}
\[  
\lim_{k\to \infty} \lim_{n\to\infty} f_n(x_k) \neq
\lim_{n\to \infty} \lim_{k\to\infty} f_n(x_k)
.\]
:::

:::{.proposition title="Limits of differentiable functions need not be differentiable"}
\[  
\lim_{n\to \infty} \dd{}{x} f_n \neq \dd{}{n} \qty{\lim_{n\to \infty} f_n}
.\]
Note that uniform convergence of $f_n$ and $f_n'$ is sufficient to guarantee that $f$ is differentiable.
Even worse: every continuous function is a uniform limit of polynomials by the Weierstrass approximation theorem.
:::

:::{.example title="?"}
As a counterexample:
\[
f_n(x) \da \sqrt{x^2 + {1\over n}} \converges{n\to\infty}\too f(x) \da \abs{x}
,\]
and this convergence is even uniform.
:::

:::{.example title="?"}
\[
f_n(x) \da {x\over 1 + nx^2}
.\]
Then by Calculus, $f_n(x) \leq 1/2\sqrt{n} \da M_n$ and $f_n\to 0$ uniformly, so $f' = 0$.
But 
\[
f_n'(x) = {1-nx^2 \over\qty{1 + nx^2}^2}
,\]
and $f_n'(0) \to 1$.
:::

:::{.proposition title="?"}
\[  
\lim_{n\to \infty} \int_a^b f_n(x) \,dx \neq \int_a^b \lim_{n\to \infty} \qty{ f_n(x) } \,dx
.\]
:::

