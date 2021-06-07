# Extras

:::{.exercise title="?"}
Compute the following limits:

- $\lim_{n\to\infty} \sum_{k\geq 1} {1\over k^2} \sin^n(k)$
- $\lim_{n\to\infty} \sum_{k\geq 1} {1\over k} e^{-k/n}$
:::

:::{.solution}
For the first, use that
\[
\abs{ \sum_{k\geq 1} {1\over k^2} \sin^n(k) }
\leq
\sum_{k\geq 1} \abs{ {1\over k^2} \sin^n(k) }
\sum_{k\geq 1} \abs{ {1\over k^2}} < \infty
,\]
since $\abs{\sin(x)} \leq 1$ and $x^n < x$ for $\abs{x}\leq 1$.
By the dominated convergence theorem, we can pass the limit inside.
Using the same fact as above, $\lim_{n\to\infty}\sin^n(x) = 0$,

For the second, the claim is that it diverges (very slowly).
Note that $\lim_{n\to\infty} e^{-k/n} = 1$ for any $k$.
By Fatou, we have
\[
\liminf_{n\to\infty} \sum_{k\geq 1} {e^{-k/n} \over k}
\geq \sum_{k\geq 1} \liminf_{n\to\infty} {e^{-k/n} \over k} 
= \sum_{k\geq 1} {1 \over k} 
= \infty
.\]
:::

:::{.exercise title="?"}
Let $(\Omega,\mcb)$ be a measurable space with a Borel $\sigma\dash$algebra and $\mu_n: \mcb \to [0, \infty]$ be a $\sigma\dash$additive measure for each $n$.
Show that the following map is again a $\sigma\dash$additive measure on $\mcb$:
\[
\mu(B) \da \sum_{n\geq 1} \mu_n(B)
.\]
:::

:::{.solution}
Apply Fubini-Tonelli to commute two sums:
\[
\mu\qty{\Union_{1\leq k \leq M} E_k}\da 
&= \sum_{n\geq 1} \mu_n\qty{\Union_{1\leq k \leq M} E_k}\\
&= \sum_{n\geq 1} \sum_{1\leq k \leq M} \mu_n\qty{E_k}\\
&= \sum_{1\leq k \leq M}\sum_{n\geq 1} \mu_n\qty{E_k} \text{FT} \\
&\da \sum_{1\leq k \leq M} \mu(E_k)
.\]
:::



