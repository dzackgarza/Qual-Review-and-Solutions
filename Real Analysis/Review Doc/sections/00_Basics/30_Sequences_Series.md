# Sequences and Series

## Sequences

:::{.proposition title="The Cauchy condensation test"}
For $\ts{a_k}$ is a non-increasing sequence in $\RR$ then
\[
\sum_{k\geq 1} a_k < \infty \iff \sum_{k\geq 1} 2^k a_{2^k}<\infty
.\]
:::

:::{.proof title="showing a useful trick"}
Show that
\[
\sum a_k \leq \sum 2^k a_{2^k} \leq 2 \sum a_k
\]
using 
\[
\sum a_k = a_0 + a_1 + a_2 + a_3 + \cdots
\leq \qty{a_1} + \qty{a_2 + a_2} + \qty {a_3 + a_3 + a_3 + a_3} + \cdots \\
\]
where each group with $a_k$ has $2^k$ terms.

:::

## Series

:::{.proposition title="p-tests"}
Let $n$ be a fixed dimension and set $B = \theset{x\in \RR^n \suchthat \norm{x} \leq 1}$. 
\[
\sum \frac 1 {n^p} < \infty &\iff p>1 \\
\int_\varepsilon^\infty \frac 1 {x^p} < \infty 
&\iff p>1 \\
\int_0^1 \frac 1 {x^p} < \infty 
&\iff p<1 \\
\int_B \frac{1}{\abs{x}^p} < \infty &\iff p < n \\
\int_{B^c} \frac{1}{\abs{x}^p} < \infty &\iff p > n \\
.\]
:::

:::{.proposition title="Comparison Test"}
If $0\leq a_n \leq b_n$, then 

- $\sum b_n < \infty \implies \sum a_n < \infty$, and 
- $\sum a_n = \infty \implies \sum b_n = \infty$.

:::

:::{.proposition title="Small Tails for Series of Functions"}
If $\sum f_n$ converges then $f_n \to 0$ uniformly.
:::

:::{.corollary title="Term by Term Continuity Theorem"}
If $f_n$ are continuous and $\sum f_n \to f$ converges uniformly, then $f$ is continuous.
:::

:::{.proposition title="Cauchy criterion for sums"}
$f_n$ are uniformly Cauchy (so $\norm{f_n - f_m}_\infty < \eps$) iff $f_n$ is uniformly convergent.
:::

## Uniform Convergence

:::{.proposition title="Testing Uniform Convergence: The Sup Norm Test"}
$f_n \to f$ uniformly iff there exists an $M_n$ such that $\norm{f_n - f}_\infty \leq M_n \to 0$.
:::

:::{.remark title="Negating the Sup Norm test"}
**Negating**: find an $x$ which depends on $n$ for which $\norm{f_n}_\infty > \eps$ (negating small tails) or $\norm{f_n - f_m} > \eps$ (negating the Cauchy criterion).
:::

:::{.proposition title="$C(I)$ is complete"}
The space $X = C([0, 1])$, continuous functions $f: [0, 1] \to \RR$, equipped with the norm 
\[
\norm{f}_\infty \da \sup_{x\in [0, 1]} \abs{f(x)}
\]
is a **complete** metric space.

:::

:::{.proof}
\envlist

1.  Let $\theset{f_k}$ be Cauchy in $X$.

2.  Define a candidate limit using pointwise convergence:

    Fix an $x$; since
  \[
  \abs{f_k(x) - f_j(x)}  \leq \norm{f_k - f_k} \to 0
  \] 
    the sequence $\theset{f_k(x)}$ is Cauchy in $\RR$.
    So define $f(x) \definedas \lim_k f_k(x)$.


3.  Show that $\norm{f_k - f} \to 0$:
  \[
  \abs{f_k(x) - f_j(x)} < \varepsilon ~\forall x \implies \lim_{j} \abs{f_k(x) - f_j(x)} <\varepsilon ~\forall x
  \]
    Alternatively, $\norm{f_k-f} \leq \norm{f_k - f_N} + \norm{f_N - f_j}$, where $N, j$ can be chosen large enough to bound each term by $\varepsilon/2$.

4.  Show that $f\in X$:

    The uniform limit of continuous functions is continuous.

:::

:::{.remark}
In other cases, you may need to show the limit is bounded, or has bounded derivative, or whatever other conditions define $X$.
:::

:::{.theorem title="Weierstrass Approximation"}
If $[a, b] \subset \RR$ is a closed interval and $f$ is continuous, then for every $\eps> 0$ there exists a polynomial $p_\eps$ such that $\norm{f- p_\eps}_{L^\infty([a, b])} \converges{\eps \to 0}\to 0$.

Equivalently, polynomials are dense in the Banach space $C([0, 1], \norm{\wait}_\infty)$.
:::

