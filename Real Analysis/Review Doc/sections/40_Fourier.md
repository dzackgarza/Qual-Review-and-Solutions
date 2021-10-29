---
order: 40
---

# Fourier Transform and Convolution

## The Fourier Transform

:::{.proposition title="?"}
If $\hat f = \hat g$ then $f=g$ almost everywhere.
:::

:::{.proposition title="Riemann-Lebesgue: Fourier transforms have small tails."}
\[
f\in L^1 \implies
\hat{f}(\xi) \rightarrow 0 \text { as }|\xi| \rightarrow \infty
,\]

if $f \in L^1$, then $\hat f$ is continuous and bounded.
:::

:::{.proof title="?"}
\envlist

- Boundedness:
\[
\abs{\hat f(\xi)} 
\leq \int \abs{f}\cdot \abs{e^{2\pi i x\cdot \xi }} 
= \pnorm{f}{1}
.\]

- Continuity:
- $\abs{\hat{f}(\xi_{n}) - \hat{f} (\xi) }$
- Apply DCT to show $a\converges{n\to\infty}\to 0$.

:::
   
:::{.theorem title="Fourier Inversion"}
\[
f(x)=\int_{\mathbb{R}^{n}} \widehat{f}(x) e^{2 \pi i x \cdot \xi} d \xi
.\]

:::

:::{.warnings}
Fubini-Tonelli does not work here!
:::
    
:::{.proof title="?"}
Idea: Fubini-Tonelli doesn't work directly, so introduce a convergence factor, take limits, and use uniqueness of limits.

- Take the modified integral:

\[
I_{t}(x)
&= \int \hat f(\xi) ~e^{2\pi i x \cdot \xi} ~e^{-\pi t^2 \abs{\xi}^2} \\
&= \int \hat f(\xi) \phi(\xi) \\
&= \int f(\xi) \hat \phi(\xi) \\
&= \int f(\xi) \widehat{\hat g}(\xi - x) \\
&= \int f(\xi) g_{t}(x - \xi)  ~d\xi \\
&= \int f(y-x) g_{t}(y) ~dy  \quad (\xi = y-x)\\
&= (f \ast g_{t}) \\
&\to f \text{ in $L^1$ as }t \to 0
.\]

- We also have
\[
\lim_{t\to 0} I_{t}(x)
&= 
\lim_{t\to 0} \int \hat f(\xi) ~e^{2\pi i x \cdot \xi} ~e^{-\pi t^2 \abs{\xi}^2} \\
&= 
\lim_{t\to 0} \int \hat f(\xi) \phi(\xi) \\
&=_{DCT} 
\int \hat f(\xi) \lim_{t\to 0} \phi(\xi) \\
&=
\int \hat f(\xi) ~e^{2\pi i x \cdot \xi} \\
.\]

- So 
\[
I_{t}(x) \to \int \hat f(\xi) ~e^{2\pi i x \cdot \xi} ~\text{ pointwise and }~\pnorm{I_{t}(x) - f(x)}{1} \to 0
.\]

- So there is a subsequence $I_{t_{n}}$ such that $I_{t_{n}}(x) \to f(x)$ almost everywhere
- Thus $f(x) = \int \hat f(\xi) ~e^{2\pi i x \cdot \xi}$ almost everywhere by uniqueness of limits. 

:::

:::{.proposition title="Eigenfunction of the Fourier transform"}
\[
g(x) \da e^{-\pi \abs{t}^2} \implies \hat g(\xi) = g(\xi) \qtext{and}
\hat g_{t}(x) = g(tx) = e^{-\pi t^2 \abs{x}^2}
.\]
:::

## Approximate Identities 

:::{.example title="of an approximation to the identity."}
\[
\phi(x) \da e^{-\pi x^2}
.\]

:::

:::{.theorem title="Convolving against an approximate identity converges in $L^1$."}
\[
\pnorm{f \ast \phi_{t} - f}{1} \converges{t\to 0}\to 0
.\]

:::

:::{.proof title="?"}
\[
\norm{f - f\ast \phi_{t}}_1 
&= \int f(x) - \int f(x-y)\phi_{t}(y) ~dy dx \\
&= \int f(x)\int \phi_{t}(y) ~dy - \int f(x-y)\phi_{t}(y) ~dy dx \\
&= \int \int \phi_{t}(y)[f(x) - f(x-y)] ~dy dx \\
&=_{FT} \int \int \phi_{t}(y)[f(x) - f(x-y)] ~dx dy \\
&= \int \phi_{t}(y) \int f(x) - f(x-y) ~dx dy \\
&= \int \phi_{t}(y) \norm{f - \tau_{y} f}_1 dy \\
&= \int_{y < \delta} \phi_{t}(y) \norm{f - \tau_{y} f}_1 dy  +
\int_{y \geq \delta} \phi_{t}(y) \norm{f - \tau_{y} f}_1 dy \\
&\leq \int_{y < \delta} \phi_{t}(y) \varepsilon +
\int_{y \geq \delta} \phi_{t}(y) \left( \norm{f}_1 + \norm{\tau_{y} f}_1 \right) dy \quad\text{by continuity in } L^1 \\
&\leq \varepsilon + 
2\norm{f}_1 \int_{y \geq \delta} \phi_{t}(y) dy \\
&\leq \varepsilon + 2\norm{f}_1 \cdot \varepsilon \quad\text{since $\phi_{t}$ has small tails} \\
&\converges{\eps\to 0}\to 0 
.\]

:::

:::{.theorem title="Convolutions vanish at infinity"}
\[
f,g \in L^1 \text{ and  bounded}  \implies \lim_{|x| \rightarrow \infty} (f * g)(x) = 0
.\]

:::

:::{.proof title="?"}

- Choose $M \geq f,g$.

- By small tails, choose $N$ such that $\int_{B_{N}^c} \abs{f}, \int_{B_{n}^c} \abs{g} < \varepsilon$

- Note 
\[
\abs{f \ast g} \leq \displaystyle\int \abs{f(x-y)} ~\abs{g(y)} ~dy \da I
.\]

- Use $\abs{x} \leq \abs{x-y} + \abs{y}$, take $\abs{x}\geq 2N$ so either
\[
\abs{x-y} \geq N \implies I \leq \int_{\theset{x-y \geq N}} \abs{f(x-y)}M ~dy\leq \varepsilon M \to 0
\]
  then
\[
\abs{y} \geq N \implies I \leq \int_{\theset{y \geq N}} M\abs{g(y)} ~dy\leq  M \varepsilon \to 0
.\]

:::

:::{.proposition title="Corollary of Young's inequality"}
Take $q = 1$ in Young's inequality to obtain
\[
\pnorm{f \ast g}p \leq \norm{f}p \norm{g}1
.\]

:::

:::{.proposition title="$L^1$ is closed under convolution."}
If $f, g \in L^1$ then $f\ast g\in L^1$.
:::



