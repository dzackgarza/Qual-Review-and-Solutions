# Spring 2020


## 1

Suppose $f\in C^\infty(\RR)$ is smooth, then
\begin{align*}
\lim_{k\to\infty} \int_0^1 kx^{k-1} f(x) \, dx
&= \lim_{k\to\infty} \int_0^1 \qty{ \dd{}{x}x^k } f(x) \, dx \\
&= \lim_{k\to\infty} \left[ x^k f(x) \evalfrom_0^1 - \int_0^1 x^k \qty{\dd{}{x} f(x) } \, dx \right] \\
&= f(1) - \lim_{k\to\infty} \int_0^1 x^k \qty{\dd{}{x} f(x) } \, dx
,\end{align*}

and thus it suffices to show that $\int_0^1 x^k \qty{\dd{}{x} f(x) } \, dx \converges{k\to\infty}\to 0$.

