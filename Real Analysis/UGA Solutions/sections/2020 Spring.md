# Spring 2020


## 1

Suppose $f\in C^\infty(\RR)$ is smooth, then
\begin{align*}
\lim_{k\to\infty} \int_0^1 kx^{k-1} f(x) \, dx
&= \lim_{k\to\infty} \int_0^1 \qty{ \dd{}{x}x^k } f(x) \, dx \\
&= \lim_{k\to\infty} \left[ x^k f(x) \evalfrom_0^1 - \int_0^1 x^k \qty{\dd{}{x} f(x) } \, dx \right] \quad\text{integrating by parts}\\
&= f(1) - \lim_{k\to\infty} \int_0^1 x^k \qty{\dd{}{x} f(x) } \, dx
,\end{align*}

and thus it suffices to show that $\lim_{k\to\infty} \int_0^1 x^k \qty{\dd{}{x} f(x) } \, dx = 0$.

Integrating by parts a second time yields
\begin{align*}
\int_0^1 x^k \qty{\dd{}{x} f(x) } \, dx
&= {x^{k+1} \over k+1} f'(x) \evalfrom_0^1 - \int_0^1 {x^{k+1} \over k+1} \qty{ \dd{^2}{^2 x}f(x)} \, dx
.\end{align*}
