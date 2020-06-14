# Spring 2020


## 1

Suppose $f\in C^\infty([0, 1])$ is smooth, then
\begin{align*}
\lim_{k\to\infty} \int_0^1 kx^{k-1} f(x) \, dx
&= \lim_{k\to\infty} \int_0^1 \qty{ \dd{}{x}x^k } f(x) \, dx \\
&= \lim_{k\to\infty} \left[ x^k f(x) \evalfrom_0^1 - \int_0^1 x^k \qty{\dd{}{x} f(x) } \, dx \right] \quad\text{integrating by parts}\\
&= f(1) - \lim_{k\to\infty} \int_0^1 x^k \qty{\dd{}{x} f(x) } \, dx
,\end{align*}

and thus it suffices to show that
\begin{align*}
\lim_{k\to\infty} \int_0^1 x^k \qty{\dd{}{x} f(x) } \, dx = 0
.\end{align*}

Integrating by parts a second time yields
\begin{align*}
\lim_{k\to\infty} 
\int_0^1 x^k \qty{\dd{}{x} f(x) } \, dx
&= \lim_{k\to\infty} 
{x^{k+1} \over k+1} f'(x) \evalfrom_0^1 - \int_0^1 {x^{k+1} \over k+1} \qty{ \dd{^2}{^2 x}f(x)} \, dx \\
&= - \lim_{k\to\infty} \int_0^1 {x^{k+1} \over k+1} \qty{ \dd{^2}{^2 x}f(x)} \, dx \\
&= - \int_0^1 \lim_{k\to\infty}  {x^{k+1} \over k+1} \qty{ \dd{^2}{^2 x}f(x)} \, dx \quad\text{by DCT} \\
&= - \int_0^1 0 \qty{ \dd{^2}{^2 x}f(x)} \, dx \\
&= 0
.\end{align*}

The DCT can be applied here because $f''$ is continuous and $[0, 1]$ is compact, so $f''$ is bounded on $[0, 1]$ by a constant $M$ and $\int_0^1 \abs{x^k f''(x)} \leq \int_0^1 1\cdot M = M < \infty$.

Using the fact that $C([0, 1], \norm{\wait}_\infty)\subseteq L^1([0, 1])$, $f$ is integrable, so if $f$ is not smooth then it can be approximated in $L^1$ by smooth functions.

### Proof 2 (Simpler)

- Show the result is true for $f(x) = x^n$ for a fixed $n$.
- By linearity, it is true for any polynomial.
- By Stone Weierstrass, $f$ is a uniform limit of polynomials.
- Uniform convergence implies $L^1$ convergence on compact intervals?

## 2

?
