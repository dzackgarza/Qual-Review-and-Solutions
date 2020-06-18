# Spring 2020


## 1

Suppose $p$ is a polynomial, then
\begin{align*}
\lim_{k\to\infty} \int_0^1 kx^{k-1} p(x) \, dx
&= \lim_{k\to\infty} \int_0^1 \qty{ \dd{}{x}x^k } p(x) \, dx \\
&= \lim_{k\to\infty} \left[ x^k p(x) \evalfrom_0^1 - \int_0^1 x^k \qty{\dd{}{x} p(x) } \, dx \right] \quad\text{integrating by parts}\\
&= p(1) - \lim_{k\to\infty} \int_0^1 x^k \qty{\dd{}{x} p(x) } \, dx
,\end{align*}

and thus it suffices to show that
\begin{align*}
\lim_{k\to\infty} \int_0^1 x^k \qty{\dd{}{x} p(x) } \, dx = 0
.\end{align*}

Integrating by parts a second time yields
\begin{align*}
\lim_{k\to\infty} 
\int_0^1 x^k \qty{\dd{}{x} p(x) } \, dx
&= \lim_{k\to\infty} 
{x^{k+1} \over k+1} p'(x) \evalfrom_0^1 - \int_0^1 {x^{k+1} \over k+1} \qty{ \dd{^2}{x^2}p(x)} \, dx \\
&= - \lim_{k\to\infty} \int_0^1 {x^{k+1} \over k+1} \qty{ \dd{^2}{x^2}p(x)} \, dx \\
&= - \int_0^1 \lim_{k\to\infty}  {x^{k+1} \over k+1} \qty{ \dd{^2}{x^2}p(x)} \, dx \quad\text{by DCT} \\
&= - \int_0^1 0 \qty{ \dd{^2}{x^2}p(x)} \, dx \\
&= 0
.\end{align*}

The DCT can be applied here because $f''$ is continuous and $[0, 1]$ is compact, so $f''$ is bounded on $[0, 1]$ by a constant $M$ and $\int_0^1 \abs{x^k f''(x)} \leq \int_0^1 1\cdot M = M < \infty$.

We now use the Weierstrass approximation theorem: if $f: [a, b] \to \RR$ is continuous, then for every $\eps>0$ there exists a polynomial $p_\eps(x)$ such that $\norm{f - p_\eps}_\infty < \eps$.
Thus 
\begin{align*}
\abs{ \int_0^1 kx^{k-1} p_\eps(x)\,dx - \int_0^1 kx^{k-1}f(x)\,dx  } 
&= \abs{ \int_0^1 kx^{k-1} \qty{p_\eps(x) - f(x)} \,dx  } \\
&\leq \abs{ \int_0^1 kx^{k-1} \norm{p_\eps-f}_\infty \,dx  } \\
&= \norm{p_\eps-f}_\infty \cdot \abs{ \int_0^1 kx^{k-1} \,dx  } \\
&= \norm{p_\eps-f}_\infty \cdot x^k \evalfrom_0^1 \\
&= \norm{p_\eps-f}_\infty \converges{\eps\to 0}\to 0
\end{align*}

and the integrals are equal. 
Finally, the first integral is equal to $p_\eps(1)$ for each $\eps$, which converges to $f(1)$ since uniform convergence implies pointwise convergence.


## 2

Concepts used:

- Definition: $m_*(E) = \inf_{\theset{Q_j} \covers E} \sum \abs {Q_j}$ where $\theset{Q_j}$ is a countable collection of closed cubes.
- Break $\RR$ into $\disjoint_{n\in \ZZ} [n, n+1)$

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
\implies m_*(B\setminus E) &= 0
.\end{align*}
- So take $N = B\setminus E$; this shows $m_*(N) = 0$ and $E = B\setminus (B\setminus E) = B\setminus N$.


- If $m_*(E) = \infty$
  - Apply result to $E_R\definedas E \intersect [R, R+1]^n \subset \RR^n$ for $R\in \ZZ$, so $E = \union_R E_R$
  - Obtain $B_R, N_R$ such that $E_R = B_R \setminus N_R$, $m_*(E_R) = m_*(B_R)$, and $m_*(N_R) = 0$.
  - Then $B\definedas \union_R B_R$ contains $E$ since $B_R$ contains $E_R$ for each $R$, and $B$ is still Borel.
  - And $N\definedas \union N_R$ is still null and we have $B\setminus N = E$.

## 3

### a

Stated integral equality: 

- Let $\eps > 0$
- $C_c(\RR^n) \injects L^1(\RR^n)$ is dense so choose $\theset{f_n} \covers f$ so $\norm{f_n - f}_1 \to 0$.
- Choose $n \gg 1$ so that $\norm{f_n - f} < \eps$. Fix this $n$.
- Since $\theset{f_n}$ are compactly supported, choose $N_0\gg 1$ such that $f_n$ is zero outside of $B_N(\vector 0)$.
- Then
\begin{align*}
N\geq N_0 \implies \int_{\abs x > N} \abs{f} = \int_{\abs x > N} \abs{f - f_n + f_n} \leq \int_{\abs x > N} \abs{f-f_n} + \int_{\abs x > N} \abs{f_n} = \eps+ 0 
.\end{align*}

- Now take $n\to \infty$?

To see that this doesn't force $f(x)\to 0$ as $\abs{x} \to \infty$:

- Take $f(x)$ to be a train of boxes of height 1 and area $1/2^j$ centered on even integers.
- Then the $\int_{\abs x > N} \abs{f} = \sum_{j=N}^\infty 1/2^j$ which tends to zero as $N\to \infty$.
- However $f(x) = 1$ for any even integer $x > N$, so $f(x) \not\to 0$.

### b

- Since $f$ is decreasing on $[1, \infty)$, for any $t\in [x-n, x]$ we have
\begin{align*}
x-n \leq t \leq x \implies f(x) \leq f(t) \leq f(x-n)
.\end{align*}

- Integrate over $[x, 2x]$, using monotonicity of the integral:
\begin{align*}
\int_x^{2x} f(x) \,dt \leq 
\int_x^{2x} f(t) \,dt \leq 
\int_x^{2x} f(x-n) \,dt \implies xf(x) \leq \int_x^{2x} f(t) \, dt \leq xf(x-n)
.\end{align*}

- By (a), $\lim_{x\to \infty} \int_x^{2x} f(t)~dt = 0$ (?) 
- So the LHS term $\lim_{x\to \infty} xf(x) = 0$.
- Since $x>1$, $\abs{f(x)} \leq \abs{xf(x)}$ 
- Thus $f(x) \to 0$ as well.

Alternatively showing $f(x) \converges{x\to \infty} 0$:

- Toward a contradiction, suppose not.
- If $f(x) \to -\infty$, then $f\not\in L^1(\RR)$: choose $x\gg 1$ so that $\abs{f(x)} > 1$, then 
 \begin{align*}
  \int_\RR \abs{f} \geq \int_{x}^\infty f(t)\, dt \geq \int_x^\infty 1 =\infty
 .\end{align*}

- Otherwise $f(x) \to L$ with $L < \infty$. Fix $\eps>0$.
- Choose $x\gg 1$ so that $t\geq x \implies L - \eps \leq f(t) \leq L$
- Then $\int_{x}^\infty f \geq \int_x^\infty (L-\eps) = \infty$.

### c



## 4

\begin{align*}
\norm{(f\ast g)(x)}_1 
&= \norm{\int H(x, y) \,dy }_1 \\
&= \norm{\int f(y) g(x-y) \,dy }_1 \\
&\leq \int \norm{f(y) g(x-y)}_1 \,dy \\ 
&\leq \int \abs{f(y)}\norm{g(x-y)}_1 \,dy \\ 
&\leq \int \abs{f(y)} \norm{g}_1 \,dy \\ 
&\leq \norm{g}_1 \int \abs{f(y)} \,dy \\ 
&\leq \norm{g}_1 \norm{f}_1\\ 
.\end{align*}

Todo: 

- Dependence on $x$ doesn't make sense.
-  Show $H\in L^1$: Fubini-Tonelli?

## 5 

Note that 
\begin{align*}
\lim_{n} \qty{1 + {x^2 \over n}}^{-(n+1)} 
&= {1 \over \lim_{n} \qty{1 + {x^2 \over n}}^1 \qty{1 + {x^2 \over n}}^n } \\
&= {1 \over 1 \cdot e^{x^2}} \\
&= e^{-x^2}
.\end{align*}

If passing the limit through the integral is justified, we will have $\int_0^\infty e^{-x^2} = {\sqrt \pi \over 2}$.

Todo:

- Justify, DCT?
- How to compute the integral?

## 6 


