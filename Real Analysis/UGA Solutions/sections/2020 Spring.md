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

Concepts used:

- Definition: $m_*(E) = \inf_{\theset{Q_j} \covers E} \sum \abs {Q_j}$ where $\theset{Q_j}$ is a countable collection of closed cubes.

### a

Suppose $m_*(E) = N< \infty$.

Since $m_*(E)$ is an infimum, by definition, for every $\eps> 0$ there exists a covering by closed cubes $\theset{Q_i(\eps)}_{i=1}^\infty \covers E$ such that $\sum_{i=1}^\infty \abs{Q_i(\eps)} < N + \eps$.

Set $\eps_n = {1\over n}$ to produce such a collection $\theset{Q_i(\eps_n)}$ and set $B_n \definedas \union_{i=1}^\infty Q_i(\eps_n)$.
Then (theorem) the outer measure of cubes is *equal* to the sum of their volumes, so 
\begin{align*}
m_*(B_n) = \sum \abs{Q_i(\eps_n)} < N + \eps_n = N + {1\over n}
.\end{align*}

Now set $B \definedas \intersect_{n=1}^\infty B_n$.

- Since $E\subseteq B_n$ for every $n$, $E\subseteq B$
- Since $B$ is a countable intersection of countable unions of closed sets, $B$ is Borel.
- Since $B_n \subseteq B$ for every $n$, we can apply subadditivity to obtain the inequality
\begin{align*}
N \leq m_*(B) \leq m_*(B_n) < N + {1\over n} \qtext{for all} n\in \ZZ^{\geq 1}
.\end{align*}

This forces $m_*(E) = m_*(B)$.

If $m_*(E) = \infty$, then take $B = \RR^n$ since $m(\RR^n) = \infty$.

### b

Suppose $m_*(E) < \infty$.

- By (a), find a Borel set $B\supseteq E$ such that $m_*(B) = m_*(E)$
- Note that $E\subseteq B \implies B\intersect E = E$ and $B\intersect E^c = B\setminus E$.
- By assumption, 
\begin{align*}
m_*(B) &= m_*(B\intersect E) + m_*(B\intersect E^c) \\
m_*(E) &= m_*(E) + m_*(B\setminus E) \\ 
m_*(E) - m_*(E) &= m_*(B\setminus E) \quad\text{since} m_*(E) < \infty \\ 
\implies m_*(B\setminus E) = 0
.\end{align*}

- So take $N = B\setminus E$; this shows $m_*(N) = 0$ and $E = B\setminus (B\setminus E) = B\setminus N$.
- If $m_*(E) = \infty$, ?
  - Apply result to $E_R\definedas E \intersect B_R(\vector 0)$ in $\RR^n$, so $E = \union_R E_R$
  - Obtain $B_R, N_R$ such that $E_R = B_R \setminus N_R$, $m_*(E_R) = m_*(B_R)$, and $m_*(N_R) = 0$.
  - Take $B = \union_R B_R$; then continuity of measure gives $m_*(E_R) \to m_*(E)$ and $m_*(B_R) \to m_*(B)$ and since $m_*(E_R)= m_*(B_R)$ for every $R$, uniqueness of limits gives $m_*(E) = m_*(B)$.
  - ?? Show $N\definedas E\setminus B$ has outer measure zero.

## 3


