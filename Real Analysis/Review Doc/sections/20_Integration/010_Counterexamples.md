# Counterexamples

## Non-integrable functions

:::{.example title="Examples of integrable functions"}
\envlist
- $\int {1\over 1 + x^2} = \arctan(x) \converges{x\to\infty}\to \pi/2 < \infty$

- Any bounded function (or continuous on a compact set, by EVT)
- $\int_0^1 {1 \over \sqrt{x}} < \infty$
- $\int_0^1 {1\over x^{1-\eps}} < \infty$
- $\int_1^\infty {1\over x^{1+\eps}} < \infty$

:::

:::{.example title="Examples of non-integrable functions"}
\envlist

- $\int_0^1 {1\over x} = \infty$.
- $\int_1^\infty {1\over x} = \infty$.
- $\int_1^\infty {1 \over \sqrt{x}} = \infty$
- $\int_1^\infty {1\over x^{1-\eps}} = \infty$
- $\int_0^1 {1\over x^{1+\eps}} = \infty$

:::

:::{.proposition title="a.e. convergence never implies $L^p$ convergence"}
Sequences $f_k \converges{a.e.}\to f$ but $f_k \converges{L^p}{\not\to} f$:

- For $1\leq p < \infty$:
	The skateboard to infinity, $f_k = \chi_{[k, k+1]}$.

	Then $f_k \converges{a.e.}\to 0$ but $\norm{f_k}_p = 1$ for all $k$.

	> Converges pointwise and a.e., but not uniformly and not in norm.

- For $p = \infty$:
  The sliding boxes $f_k = k \cdot \chi_{[0, \frac 1 k]}$.

	Then similarly $f_k \converges{a.e.}\to 0$, but $\norm{f_k}_p = 1$ and $\norm{f_k}_\infty = k \to \infty$

	> Converges a.e., but not uniformly, not pointwise, and not in norm.
:::

:::{.proposition title="The four big counterexamples in convergence"}
\envlist

1. Uniform: $f_n \uniformlyconverges f: \forall \varepsilon ~\exists N \suchthat ~n\geq N \implies \abs{f_N(x) - f(x)} < \varepsilon \quad \forall x.$
2. Pointwise: $f_n(x) \to f(x)$ for all $x$. (This is just a sequence of numbers)
3. Almost Everywhere: $f_n(x) \to f(x)$ for almost all $x$.
4. Norm: $\norm{f_n - f}_1 = \int \abs{f_n(x) - f(x)} \to 0$.

We have $1 \implies 2 \implies 3$, and in general no implication can be reversed, but (**warning**) none of $1,2,3$ imply $4$ or vice versa.


- $f_n = (1/n) \chi_{(0, n)}$. This converges uniformly to 0, but the integral is identically 1. So this satisfies 1,2,3 and not 4.

  ![image_2021-05-21-16-38-30](figures/image_2021-05-21-16-38-30.png)

- $f_n = \chi_{(n, n+1)}$ (skateboard to infinity). This satisfies 2,3 but not 1, 4.

  ![image_2021-05-21-16-42-08](figures/image_2021-05-21-16-42-08.png)

- $f_n = n\chi_{(0, \frac 1 n)}$. This satisfies 3 but not 1,2,4.

  ![image_2021-05-21-16-54-38](figures/image_2021-05-21-16-54-38.png)

- $f_n:$ one can construct a sequence where $f_n \to 0$ in $L^1$ but is not 1,2, or 3.
  The construction:

  - Break $I$ into $2$ intervals, let $f_1$ be the indicator on the first half, $f_2$ the indicator on the second.
  - Break $I$ into $2^2=4$ intervals, like $f_3$ be the indicator on the first quarter, $f_4$ on the second, etc.
  - Break $I$ into $2^k$ intervals and cyclic through $k$ indicator functions.

  ![image_2021-05-21-16-49-09](figures/image_2021-05-21-16-49-09.png)

  - Then $\int f_n = 1/2^n \to 0$, but $f_n\not\to 0$ pointwise since for every $x$, there are infinitely many $n$ for which $f_n(x) = 0$ and infinitely many for which $f_n(x) = 1$.

:::

:::{.proposition title="Functional analytic properties of $L^1$ and $L^2$"}
For any measure space $(X, \mcm, \mu)$,

- $L^1(X)$ is Banach space.
- $L^2(X)$ is a (possibly non-separable) Hilbert space.

:::

