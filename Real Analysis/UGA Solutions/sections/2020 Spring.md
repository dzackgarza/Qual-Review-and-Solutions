# Spring 2020


## 1

Concepts used:

- DCT
- Weierstrass Approximation Theorem

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

- Definition of outer measure: $m_*(E) = \inf_{\theset{Q_j} \covers E} \sum \abs {Q_j}$ where $\theset{Q_j}$ is a countable collection of closed cubes.
- Break $\RR$ into $\disjoint_{n\in \ZZ} [n, n+1)$, each with finite measure.

### a

Suppose $m_*(E) = N< \infty$.

Since $m_*(E)$ is an infimum, by definition, for every $\eps> 0$ there exists a covering by closed cubes $\theset{Q_i(\eps)}_{i=1}^\infty \covers E$ such that 
$$
\sum_{i=1}^\infty \abs{Q_i(\eps)} < N + \eps
.$$

Set $\eps_n = {1\over n}$ to produce such a collection $\theset{Q_i(\eps_n)}$ and set $B_n \definedas \union_{i=1}^\infty Q_i(\eps_n)$.
Then (theorem) the outer measure of cubes is *equal* to the sum of their volumes, so 
\begin{align*}
m_*(B_n) = \sum_{i=1}^\infty \abs{Q_i(\eps_n)} < N + \eps_n = N + {1\over n}
.\end{align*}

Now set $B \definedas \intersect_{n=1}^\infty B_n$.

- Since $E\subseteq B_n$ for every $n$, $E\subseteq B$
- Since $B$ is a countable intersection of countable unions of closed sets, $B$ is Borel.
- Since $B_n \subseteq B$ for every $n$, we can apply subadditivity to obtain the inequality
\begin{align*}
E \subseteq B \subseteq B_n \implies
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
m_*(E) - m_*(E) &= m_*(B\setminus E) \qquad\qquad\text{since } m_*(E) < \infty \\ 
\implies m_*(B\setminus E) &= 0
.\end{align*}
- So take $N = B\setminus E$; this shows $m_*(N) = 0$ and $E = B\setminus (B\setminus E) = B\setminus N$.


- If $m_*(E) = \infty$
  - Apply result to $E_R\definedas E \intersect [R, R+1)^n \subset \RR^n$ for $R\in \ZZ$, so $E = \disjoint_R E_R$
  - Obtain $B_R, N_R$ such that $E_R = B_R \setminus N_R$, $m_*(E_R) = m_*(B_R)$, and $m_*(N_R) = 0$.
  - Note that
    -   $B\definedas \union_R B_R$, which is a union of Borel sets and thus still Borel
    -  $E = \union_R E_R$
    - $N\definedas B\setminus E$
    - $N' \definedas \union_R N_R$ which is a union of null sets and thus still null
  - Since $E_R \subset B_R$ for every $R$, we have $E\subset B$
  - We can compute
  \begin{align*}
  N = B\setminus E = \qty{ \union_R B_R } \setminus \qty{\union_R E_R } \subseteq \union_R \qty{B_R\setminus E_R} = N'
  \end{align*}
  where $m_*(N) = 0$ and thus subadditivity forces $m_*(N) = 0$.

## 3

### a

Stated integral equality: 

- Let $\eps > 0$
- $C_c(\RR^n) \injects L^1(\RR^n)$ is dense so choose $\theset{f_n} \to f$ with $\norm{f_n - f}_1 \to 0$.
- Choose $n \gg 1$ so that $\norm{f_n - f} < \eps$. Fix this $n$.
- Since $\theset{f_n}$ are compactly supported, choose $N_0\gg 1$ such that $f_n$ is zero outside of $B_{N_0}(\vector 0)$.
- Then
\begin{align*}
N\geq N_0 \implies \int_{\abs x > N} \abs{f} &= \int_{\abs x > N} \abs{f - f_n + f_n} \\
&\leq \int_{\abs x > N} \abs{f-f_n} + \int_{\abs x > N} \abs{f_n} \\
&= \int_{\abs x > N} \abs{f-f_n} \\ 
&\leq \int_{\abs x > N} \norm{f-f_n}_1 \\\
&= \eps \int_{\abs x > N} 1 \\
.\end{align*}

- Now check

- Now take $n\to \infty$.

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

- WLOG replace $f$ with $-f$ to make $f$ increasing (since $\norm{f}_1 = \norm{f}_2$).
- Otherwise $f(x) \to L$ with $L < \infty$. Fix $\eps>0$.
- Choose $x\gg 1$ so that $t\geq x \implies L - \eps \leq f(t) \leq L$
- Then $\int_{x}^\infty f \geq \int_x^\infty (L-\eps) = \infty$.

### c

- No: take $f(x) = {1\over x\ln x}$
- Then $\int f = \ln\qty{\ln (x)} \to \infty$ is unbounded, so $f\not\in L^1([1, \infty))$.
- But $xf(x) = 1/\ln(x) \to 0$


## 4

Relevant concepts:

- Tonelli: non-negative and measurable yields measurability of slices and equality of iterated integrals
- Fubini:i $f(x, y) \in L^1$ yields *integrable* slices and equality of iterated integrals
- F/T: apply Tonelli to $\abs{f}$; if finite, $f\in L^1$ and apply Fubini to $f$

\begin{align*}
\norm{(f\ast g)(x)}_1 
&= \norm{\int_\RR H(x, y) \,dy }_1 \\
&\definedas \norm{\int_\RR f(y) g(x-y) \,dy }_1 \\
&\leq \int_\RR \norm{f(y) g(x-y)}_1 \,dy \\ 
&\leq \int_\RR \abs{f(y)} \cdot \norm{g(x-y)}_1 \,dy \\ 
&\leq \int_\RR \abs{f(y)} \cdot \norm{g}_1 \,dy \\ 
&\leq \norm{g}_1 \int_\RR \abs{f(y)} \,dy \\ 
&\leq \norm{g}_1 \norm{f}_1\\ 
&< \infty \qtext{by assumption}
.\end{align*}

Todo: 

- Change of variables for $x-y$?
- How to justify F/T?

## 5 

Note that 
\begin{align*}
\lim_{n} \qty{1 + {x^2 \over n}}^{-(n+1)} 
&= {1 \over \lim_{n} \qty{1 + {x^2 \over n}}^1 \qty{1 + {x^2 \over n}}^n } \\
&= {1 \over 1 \cdot e^{x^2}} \\
&= e^{-x^2}
.\end{align*}

If passing the limit through the integral is justified, we will have $\int_0^\infty e^{-x^2} = {\sqrt \pi \over 2}$.

Computing the integral:

\begin{align*}
\qty{\int_\RR e^{-x^2}\, dx}^2
&= \qty{\int_\RR e^{-x^2}\,dx} \qty{\int_\RR e^{-y^2}\,dx} \\
&= \int_\RR \int_\RR e^{-(x+y)^2}\, dx \\
&= \int_0^{2\pi} \int_0^\infty e^{-r^2} r\, dr \, d\theta \qquad u=r^2 \\
&= {1\over 2} \int_0^{2\pi } \int_0^\infty e^{-u}\, du \, d\theta \\
&= {1\over 2} \int_0^{2\pi} 1 \\
&= \pi
,\end{align*}
and now use the fact that the function is even.

Todo:

- Justify, MCT? Possible have 
\begin{align*}
f_n(x) \definedas {1 \over \qty{1+{x^2 \over n}}^{n+1} } \nearrow e^{-x^2}
.\end{align*}

## 6 

Concepts used:

- For $e_n(x) \definedas 2^{2\pi i n x}$, the set $\theset{e_n}$ is an orthonormal basis for $L^2([0, 1])$.
- For any orthonormal set in a Hilbert space, Bessel's inequality:
  \begin{align*}
  \sum_{k=1}^{\infty}\left|\left\langle x, e_{k}\right\rangle\right|^{2} \leq\|x\|^{2}
  .\end{align*}
- When a basis, the above is an inequality (Parseval)
- Arguing uniform convergence: since $\theset{\hat f(n)} \in \ell^1(\ZZ)$, we should be able to apply the $M$ test.

Want to show
\begin{align*}
\int_0^1 \abs{f(x)}^2 \,dx &\leq \int_0^1 \abs{f(x)} \,dx \\
\sum_{n=1}^\infty \abs{c_n}^2 &\leq \sum_{n=1}^\infty \abs{c_n}
.\end{align*}

- First inequality: ?
- Second inequality: break into 2 pieces?
