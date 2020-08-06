
---
title: Real Analysis Qualifying Exam Solutions
---



# Spring 2020


## 1

Concepts used:

- DCT
- Weierstrass Approximation Theorem

**Solution**:

- Suppose $p$ is a polynomial, then
\begin{align*}
\lim_{k\to\infty} \int_0^1 kx^{k-1} p(x) \, dx
&= \lim_{k\to\infty} \int_0^1 \qty{ \dd{}{x}x^k } p(x) \, dx \\
&= \lim_{k\to\infty} \left[ x^k p(x) \evalfrom_0^1 - \int_0^1 x^k \qty{\dd{}{x} p(x) } \, dx \right] \quad\text{integrating by parts}\\
&= p(1) - \lim_{k\to\infty} \int_0^1 x^k \qty{\dd{}{x} p(x) } \, dx
,\end{align*}

- Thus it suffices to show that
\begin{align*}
\lim_{k\to\infty} \int_0^1 x^k \qty{\dd{}{x} p(x) } \, dx = 0
.\end{align*}

- Integrating by parts a second time yields
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

  - The DCT can be applied here because $f''$ is continuous and $[0, 1]$ is compact, so $f''$ is bounded on $[0, 1]$ by a constant $M$ and 
  $$\int_0^1 \abs{x^k f''(x)} \leq \int_0^1 1\cdot M = M < \infty.$$

- Now use the Weierstrass approximation theorem: 
  - If $f: [a, b] \to \RR$ is continuous, then for every $\eps>0$ there exists a polynomial $p_\eps(x)$ such that $\norm{f - p_\eps}_\infty < \eps$.

- Thus 
\begin{align*}
\abs{ \int_0^1 kx^{k-1} p_\eps(x)\,dx - \int_0^1 kx^{k-1}f(x)\,dx  } 
&= \abs{ \int_0^1 kx^{k-1} \qty{p_\eps(x) - f(x)} \,dx  } \\
&\leq \abs{ \int_0^1 kx^{k-1} \norm{p_\eps-f}_\infty \,dx  } \\
&= \norm{p_\eps-f}_\infty \cdot \abs{ \int_0^1 kx^{k-1} \,dx  } \\
&= \norm{p_\eps-f}_\infty \cdot x^k \evalfrom_0^1 \\
&= \norm{p_\eps-f}_\infty \converges{\eps\to 0}\to 0
\end{align*}

  and the integrals are equal. 

- By the first argument, $$\int_0^1 kx^{k-1} p_\eps(x) \,dx = p_\eps(1) \text{ for each } \eps$$ 
- Since uniform convergence implies pointwise convergence, $p_\eps(1) \converges{\eps\to 0}\to f(1)$.


## 2

Concepts used:

- Definition of outer measure: $m_*(E) = \inf_{\theset{Q_j} \covers E} \sum \abs {Q_j}$ where $\theset{Q_j}$ is a countable collection of closed cubes.
- Break $\RR$ into $\disjoint_{n\in \ZZ} [n, n+1)$, each with finite measure.
- Theorem: $m_*(Q) = \abs{Q}$ for $Q$ a closed cube (i.e. the outer measure equals the volume).

Proof (of Theorem)
:   Statement: if $Q$ is a closed cube, then $m_*(Q) = \abs{Q}$, the usual volume.

    - $m_*(Q) \leq \abs{Q}$:
      - Since $Q\subseteq Q$, $Q\covers Q$ and $m_*(Q) \leq \abs{Q}$ since $m_*$ is an infimum over such coverings.
    - $\abs{Q} \leq m_*(Q)$:
      - Fix $\eps > 0$.
      - Let $\theset{Q_i}_{i=1}^\infty \covers Q$ be arbitrary, it suffices to show that 
          $$\abs{Q} \leq \qty{\sum_{i=1}^\infty \abs{Q_i}} + \eps.$$
      -  Pick open cubes $S_i$ such that $Q_i\subseteq S_i$ and $\abs{Q_i} \leq \abs{S_i} \leq (1+\eps)\abs{Q_i}$.
      - Then $\theset{S_i} \covers Q$, so by compactness of $Q$ pick a finite subcover with $N$ elements.

      - Note 
      \begin{align*}
      Q \subseteq \union_{i=1}^N S_i \implies \abs{Q} \leq \sum_{i=1}^N \abs{S_i} \leq \sum_{i=1}^N (1+\eps) \abs{Q_j} \leq (1+\eps)\sum_{i=1}^\infty \abs{Q_i } 
      .\end{align*}
      - Taking an infimum over coverings on the RHS preserves the inequality, so 
        $$\abs{Q} \leq (1+\eps) m_*(Q)$$
      - Take $\eps\to 0$ to obtain final inequality.


### a

- If $m_*(E) = \infty$, then take $B = \RR^n$ since $m(\RR^n) = \infty$.
- Suppose $N \definedas m_*(E) < \infty$.

- Since $m_*(E)$ is an infimum, by definition, for every $\eps> 0$ there exists a covering by closed cubes $\theset{Q_i(\eps)}_{i=1}^\infty \covers E$ depending on $\eps$ such that 
$$
\sum_{i=1}^\infty \abs{Q_i(\eps)} < N + \eps
.$$

- For each fixed $n$, set $\eps_n = {1\over n}$ to produce such a covering $\theset{Q_i(\eps_n)}_{i=1}^\infty$ and set $B_n \definedas \union_{i=1}^\infty Q_i(\eps_n)$.

- The outer measure of cubes is *equal* to the sum of their volumes, so 
\begin{align*}
m_*(B_n) = \sum_{i=1}^\infty \abs{Q_i(\eps_n)} < N + \eps_n = N + {1\over n}
.\end{align*}

- Now set $B \definedas \intersect_{n=1}^\infty B_n$.

  - Since $E\subseteq B_n$ for every $n$, $E\subseteq B$
  - Since $B$ is a countable intersection of countable unions of closed sets, $B$ is Borel.
  - Since $B_n \subseteq B$ for every $n$, we can apply subadditivity to obtain the inequality
  \begin{align*}
  E \subseteq B \subseteq B_n \implies
  N \leq m_*(B) \leq m_*(B_n) < N + {1\over n} \qtext{for all} n\in \ZZ^{\geq 1}
  .\end{align*}

- This forces $m_*(E) = m_*(B)$.


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


If $m_*(E) = \infty$:

- Apply result to $E_R\definedas E \intersect [R, R+1)^n \subset \RR^n$ for $R\in \ZZ$, so $E = \disjoint_R E_R$
- Obtain $B_R, N_R$ such that $E_R = B_R \setminus N_R$, $m_*(E_R) = m_*(B_R)$, and $m_*(N_R) = 0$.
- Note that
  -   $B\definedas \union_R B_R$ is a union of Borel sets and thus still Borel
  -  $E = \union_R E_R$
  - $N\definedas B\setminus E$
  - $N' \definedas \union_R N_R$ is a union of null sets and thus still null
- Since $E_R \subset B_R$ for every $R$, we have $E\subset B$
- We can compute
\begin{align*}
N = B\setminus E = \qty{ \union_R B_R } \setminus \qty{\union_R E_R } \subseteq \union_R \qty{B_R\setminus E_R} = \union_R N_R \definedas N'
\end{align*}
where $m_*(N') = 0$ since $N'$ is null, and thus subadditivity forces $m_*(N) = 0$.

## 3

Concepts used:

- Limits
- Cauchy Criterion for Integrals: $\int_a^\infty f(x) \,dx$ converges iff for every $\eps>0$ there exists an $M_0$ such that $A,B\geq M_0$ implies $\abs{\int_A^B f} < \eps$, i.e. $\abs{\int_A^B f} \converges{A\to\infty}\to 0$.
- Integrals of $L^1$ functions have vanishing tails: $\int_{N}^\infty \abs{f} \converges{N\to\infty}\to 0$.
- Mean Value Theorem for Integrals: $\int_a^b f(t)\, dt = (b-a) f(c)$ for some $c\in [a, b]$.

### a

Stated integral equality: 

- Let $\eps > 0$
- $C_c(\RR^n) \injects L^1(\RR^n)$ is dense so choose $\theset{f_n} \to f$ with $\norm{f_n - f}_1 \to 0$.
- Since $\theset{f_n}$ are compactly supported, choose $N_0\gg 1$ such that $f_n$ is zero outside of $B_{N_0}(\vector 0)$.
- Then
\begin{align*}
N\geq N_0 \implies \int_{\abs x > N} \abs{f} &= \int_{\abs x > N} \abs{f - f_n + f_n} \\
&\leq \int_{\abs x > N} \abs{f-f_n} + \int_{\abs x > N} \abs{f_n} \\
&= \int_{\abs x > N} \abs{f-f_n} \\ 
&\leq \int_{\abs x > N} \norm{f-f_n}_1 \\
&= \norm{f_n-f}_1 \qty{\int_{\abs x > N} 1} \\
&\converges{n\to\infty}\to 0 \qty{\int_{\abs x > N} 1} \\
&= 0\\
&\converges{N\to\infty}\to 0
.\end{align*}


To see that this doesn't force $f(x)\to 0$ as $\abs{x} \to \infty$:

- Take $f(x)$ to be a train of rectangles of height 1 and area $1/2^j$ centered on even integers.
- Then $$\int_{\abs x > N} \abs{f} = \sum_{j=N}^\infty 1/2^j \converges{N\to\infty}\to 0$$ as the tail of a convergent sum. 
- However $f(x) = 1$ for infinitely many even integers $x > N$, so $f(x) \not\to 0$ as $\abs{x}\to\infty$.

### b

#### Solution 1 ("Trick")

- Since $f$ is decreasing on $[1, \infty)$, for any $t\in [x-n, x]$ we have
\begin{align*}
x-n \leq t \leq x \implies f(x) \leq f(t) \leq f(x-n)
.\end{align*}

- Integrate over $[x, 2x]$, using monotonicity of the integral:
\begin{align*}
\int_x^{2x} f(x) \,dt \leq 
\int_x^{2x} f(t) \,dt \leq 
\int_x^{2x} f(x-n) \,dt \\ 
\implies 
f(x) \int_x^{2x} \,dt \leq 
\int_x^{2x} f(t) \,dt \leq 
f(x-n) \int_x^{2x} \,dt  \\
\implies xf(x) \leq \int_x^{2x} f(t) \, dt \leq xf(x-n)
.\end{align*}

- By the Cauchy Criterion for integrals, $\lim_{x\to \infty} \int_x^{2x} f(t)~dt = 0$.
- So the LHS term $xf(x) \converges{x\to\infty}\to 0$.
- Since $x>1$, $\abs{f(x)} \leq \abs{xf(x)}$ 
- Thus $f(x) \converges{x\to\infty}\to 0$ as well.

#### Solution 2 (Variation on the Trick)

- Use mean value theorem for integrals:
\begin{align*}
\int_x^{2x} f(t)\, dt = xf(c_x) \quad\text{for some $c_x \in [x, 2x]$ depending on $x$}
.\end{align*}

- Since $f$ is decreasing, 
\begin{align*}
x\leq c_x \leq 2x 
&\implies f(2x)\leq f(c_x) \leq f(x) \\
&\implies 2xf(2x)\leq 2xf(c_x) \leq 2xf(x) \\
&\implies 2xf(2x)\leq 2x\int_x^{2x} f(t)\, dt \leq 2xf(x) \\
.\end{align*}

- By Cauchy Criterion, $\int_x^{2x} f \to 0$.
- So $2x f(2x) \to 0$, which by a change of variables gives $uf(u) \to 0$.
- Since $u\geq 1$, $f(u) \leq uf(u)$ so $f(u) \to 0$ as well.

#### Solution 3 (Contradiction)
\hfill
Just showing $f(x) \converges{x\to \infty}\to 0$:

- Toward a contradiction, suppose not.
- Since $f$ is decreasing, it can not diverge to $+\infty$
- If $f(x) \to -\infty$, then $f\not\in L^1(\RR)$: choose $x_0 \gg 1$ so that $t\geq x_0 \implies f(t) < -1$, then 
- Then $t\geq x_0 \implies \abs{f(t)} \geq 1$, so
 \begin{align*}
\int_1^\infty \abs{f} \geq \int_{x_0}^\infty \abs{f(t) } \, dt \geq \int_{x_0}^\infty 1 =\infty
 .\end{align*}

- Otherwise $f(x) \to L\neq 0$, some finite limit.
- If $L>0$:
  - Fix $\eps>0$, choose $x_0\gg 1$ such that $t\geq x_0 \implies L-\eps \leq f(t) \leq L$
  - Then $$\int_1^\infty f \geq \int_{x_0}^\infty f \geq \int_{x_0}^\infty \qty{L-\eps}\,dt = \infty$$
- If $L<0$:
  - Fix $\eps > 0$, choose $x_0\gg 1$ such that $t\geq x_0 \implies L \leq f(t) \leq L + \eps$.
  - Then $$\int_1^\infty f \geq \int_{x_0}^\infty f \geq \int_{x_0}^\infty \qty{L}\,dt = \infty$$

Showing $xf(x) \converges{x\to \infty}\to 0$.

- Toward a contradiction, suppose not.
- (How to show that $xf(x) \not\to + \infty$?)
- If $xf(x)\to -\infty$
  - Choose a sequence $\Gamma = \theset{\hat x_i}$ such that $x_i \to \infty$ and $x_i f(x_i) \to -\infty$.
  - Choose a subsequence $\Gamma' = \theset{x_i}$ such that $x_if(x_i) \leq -1$ for all $i$ and $x_i \leq x_{i+1}$.
  - Choose a further subsequence $S = \theset{x_i \in \Gamma' \suchthat 2x_i  < x_{i+1}}$.
  - Then since $f$ is always decreasing, for $t\geq x_0$, $\abs f$ is increasing, and $\abs{f(x_i)} \leq \abs{f(2x_i)}$, so
  \begin{align*}
  \int_1^{\infty} \abs{f} \geq \int_{x_0}^\infty \abs{f} \geq \sum_{x_i \in S} \int_{x_i}^{2x_i} \abs{f(t)} \, dt \geq 
  \sum_{x_i \in S} \int_{x_i}^{2x_i} \abs{f(x_i)} &= \sum_{x_i \in S} x_i f(x_i) \to \infty
  .\end{align*}

- If $xf(x) \to L \neq 0$ for $0 < L< \infty$:
  - Fix $\eps> 0$, choose an infinite sequence $\theset{x_i}$ such that $L-\eps \leq x_i f(x_i) \leq L$ for all $i$.
\begin{align*}
\int_1^\infty \abs{f} \geq \sum_S \int_{x_i}^{2x_i} \abs{f(t)}\,dt \geq \sum_S \int_{x_i}^{2x_i} f(x_i) \,dt = \sum_S x_i f(x_i) \geq \sum_S \qty{L-\eps} \to \infty
.\end{align*}
- If $xf(x) \to L \neq 0$ for $-\infty < L < 0$:
  - Fix $\eps> 0$, choose an infinite sequence $\theset{x_i}$ such that $L \leq x_i f(x_i) \leq L + \eps$ for all $i$.
\begin{align*}
\int_1^\infty \abs{f} \geq \sum_S \int_{x_i}^{2x_i} \abs{f(t)}\,dt \geq \sum_S \int_{x_i}^{2x_i} f(x_i) \,dt = \sum_S x_i f(x_i) \geq \sum_S \qty{L} \to \infty
.\end{align*}

#### Solution 4 (Akos's Suggestion)

For $x\geq 1$, 
\begin{align*}
\abs{xf(x)} = \abs{ \int_x^{2x} f(x) \, dt } \leq \int_x^{2x} \abs{f(x)} \, dt \leq \int_x^{2x} \abs{f(t)}\, dt \leq \int_x^{\infty} \abs{f(t)} \,dt \converges{x\to\infty}\to 0
\end{align*}
  where we've used 
  
  - Since $f$ is decreasing and $\lim_{x\to\infty}f(x) =0$ from part (a), $f$ is non-negative.
  - Since $f$ is positive and decreasing, for every $t\in[a, b]$ we have $\abs{f(a)} \leq \abs{f(t)}$.
  - By part (a), the last integral goes to zero.

#### Solution 5 (Peter's)

- Toward a contradiction, produce a sequence $x_i\to\infty$ with $x_i f(x_i) \to \infty$ and $x_if(x_i) > \eps > 0$, then
\begin{align*}
\int f(x) \, dx 
&\geq \sum_{i=1}^\infty \int_{x_i}^{x_{i+1}} f(x) \, dx \\
&\geq \sum_{i=1}^\infty \int_{x_i}^{x_{i+1}} f(x_{i+1}) \, dx \\
&=    \sum_{i=1}^\infty f(x_{i+1}) \int_{x_i}^{x_{i+1}} \, dx \\
&\geq \sum_{i=1}^\infty (x_{i+1} - x_i) f(x_{i+1}) \\
&\geq \sum_{i=1}^\infty (x_{i+1} - x_i) {\eps \over x_{i+1}} \\
&= \eps \sum_{i=1}^\infty \qty{ 1 - {x_{i-1} \over x_i}} \to \infty
\end{align*}
  which can be ensured by passing to a subsequence where $\sum {x_{i-1} \over x_i} < \infty$.

### c

- No: take $f(x) = {1\over x\ln x}$
- Then by a $u\dash$substitution,
  \begin{align*}
  \int_0^x f = \ln\qty{\ln (x)} \converges{x\to\infty}\to \infty
  \end{align*}
  is unbounded, so $f\not\in L^1([1, \infty))$.
- But 
  \begin{align*}
  xf(x) = { 1 \over \ln(x)} \converges{x\to\infty} \to 0
  .\end{align*}


## 4

Relevant concepts:

- Tonelli: non-negative and measurable yields measurability of slices and equality of iterated integrals
- Fubini: $f(x, y) \in L^1$ yields *integrable* slices and equality of iterated integrals
- F/T: apply Tonelli to $\abs{f}$; if finite, $f\in L^1$ and apply Fubini to $f$

\begin{align*}
\norm{H(x)}_1 
&= \int_\RR \abs{H(x, y)} \, dx \\
&= \int_\RR \abs{ \int_\RR f(y)g(x-y) \,dy } \, dx \\
&\leq \int_\RR \qty{ \int_\RR \abs{f(y)g(x-y)}  \, dy } \, dx \\
&= \int_\RR \qty{ \int_\RR \abs{f(y)g(x-y)}  \, dx} \, dy \quad\text{by Tonelli} \\
&= \int_\RR \qty{ \int_\RR \abs{f(y)g(t)}  \, dt} \, dy \quad\text{setting } t=x-y, \,dt = - dx \\
&= \int_\RR \qty{ \int_\RR \abs{f(y)}\cdot \abs{g(t)}  \, dt}\, dy \\
&= \int_\RR \abs{f(y)} \cdot \qty{ \int_\RR \abs{g(t)}  \, dt}\, dy \\
&\definedas \int_\RR \abs{f(y)} \cdot \norm{g}_1 \,dy \\
&= \norm{g}_1 \int_\RR \abs{f(y)} \,dy \\
&\definedas \norm{g}_1 \norm{f}_1  \\
&< \infty \qtext{by assumption}
.\end{align*}

- $H$ is measurable on $\RR^2$:
  - If we can show $\tilde f(x, y) \definedas f(y)$ and $\tilde g(x, y) \definedas g(x-y)$ are both measurable on $\RR^2$, then $H = \tilde f \cdot \tilde g$ is a product of measurable functions and thus measurable. 
  - $f \in L^1$, and $L^1$ functions are measurable by definition.
  - The function $(x, y) \mapsto g(x-y)$ is measurable on $\RR^2$:
    - Let $g$ be measurable on $\RR$, then the cylinder function $G(x, y) = g(x)$ on $\RR^2$ is always measurable
    - Define a linear transformation $T \definedas \thevector{1, -1; 0, 1}$ which sends $(x,y) \to (x-y, y)$, then $T\in \GL(2, \RR)$ is linear and thus measurable.
    - Then $(G\circ T)(x, y) = G(x-y, y) = \tilde g(x-y)$, so $\tilde g$ is a composition of measurable functions and thus measurable.

- Apply **Tonelli** to $\abs{H}$
  - $H$ measurable implies $\abs{H}$ is measurable
  - $\abs{H}$ is non-negative
  - So the iterated integrals are equal in the extended sense
  - The calculation shows the iterated integral is finite, to $\int \abs{H}$ is finite and $H$ is thus integrable on $\RR^2$.

> Note: Fubini is not needed, since we're not calculating the actual integral, just showing $H$ is integrable.

## 5 

Concepts used:

- DCT
- Passing limits through products and quotients

Note that 
\begin{align*}
\lim_{n} \qty{1 + {x^2 \over n}}^{-(n+1)} 
&= {1 \over \lim_{n} \qty{1 + {x^2 \over n}}^1 \qty{1 + {x^2 \over n}}^n } \\
&= {1 \over 1 \cdot e^{x^2}} \\
&= e^{-x^2}
.\end{align*}

If passing the limit through the integral is justified, we will have
\begin{align*}
\lim_{n\to\infty} \int_0^n \qty{ 1 + {x^2\over n}}^{-(n+1)}\, dx 
&= \lim_{n\to\infty} \int_\RR \chi_{[0, n]} \qty{ 1 + {x^2\over n}}^{-(n+1)} \, dx  \\
&= \int_\RR \lim_{n\to\infty} \chi_{[0, n]} \qty{ 1 + {x^2\over n}}^{-(n+1)} \, dx  \qtext{by the DCT} \\
&= \int_\RR \lim_{n\to\infty} \qty{ 1 + {x^2\over n}}^{-(n+1)} \, dx  \\
&= \int_0^\infty e^{-x^2}  \\
&= {\sqrt \pi \over 2}
.\end{align*}

Computing the last integral:

\begin{align*}
\qty{\int_\RR e^{-x^2}\, dx}^2
&= \qty{\int_\RR e^{-x^2}\,dx} \qty{\int_\RR e^{-y^2}\,dx} \\
&= \int_\RR \int_\RR e^{-(x+y)^2}\, dx \\
&= \int_0^{2\pi} \int_0^\infty e^{-r^2} r\, dr \, d\theta \qquad u=r^2 \\
&= {1\over 2} \int_0^{2\pi } \int_0^\infty e^{-u}\, du \, d\theta \\
&= {1\over 2} \int_0^{2\pi} 1 \\
&= \pi
,\end{align*}
and now use the fact that the function is even so $\int_0^\infty f = {1\over 2} \int_\RR f$.

Justifying the DCT:

- Apply Bernoulli's inequality: 
\begin{align*}
{1 + {x^2\over n}}^{n+1} \geq {1 + {x^2\over n}}\qty{1 + x^2} \geq {1 + x^2}
,\end{align*}
  where the last inequality follows from the fact that $1 + {x^2 \over n} \geq 1$

\todo{Flesh out}

\todo{}


## 6 

Concepts used:

- For $e_n(x) \definedas e^{2\pi i n x}$, the set $\theset{e_n}$ is an orthonormal basis for $L^2([0, 1])$.
- For any orthonormal sequence in a Hilbert space, we have Bessel's inequality:
  \begin{align*}
  \sum_{k=1}^{\infty}\left|\left\langle x, e_{k}\right\rangle\right|^{2} \leq\|x\|^{2}
  .\end{align*}
- When $\theset{e_n}$ is a basis, the above is an *equality* (Parseval)
- Arguing uniform convergence: since $\theset{\hat f(n)} \in \ell^1(\ZZ)$, we should be able to apply the $M$ test.

### a

Claim: $\ell^1(\ZZ) \subseteq \ell^2(\ZZ)$.

- Set $\vector c = \theset{c_k \suchthat k\in \ZZ} \in \ell^1(\ZZ)$.
- It suffices to show that if $\sum_{k\in \ZZ} \abs{c_k} < \infty$ then $\sum_{k\in \ZZ} \abs {c_k}^2 < \infty$.
- Let $S = \theset{c_k \suchthat \abs{c_k} \leq 1}$, then $c_k \in S \implies \abs{c_k}^2 \leq \abs{c_k}$
- Claim: $S^c$ can only contain finitely many elements, all of which are finite.
  - If not, either $S^c \definedas \theset{c_j}_{j=1}^\infty$ is infinite with every $\abs{c_j} > 1$, which forces $$\sum_{c_k\in S^c} \abs{c_k} = \sum_{j=1}^\infty \abs{c_j} > \sum_{j=1}^\infty 1 = \infty.$$
  - If any $c_j = \infty$, then $\sum_{k\in \ZZ} \abs{c_k} \geq c_j = \infty$.
- So $S^c$ is a finite set of finite integers, let $N = \max \theset{\abs{c_j}^2 \suchthat c_j \in S^c} < \infty$.
- Rewrite the sum
\begin{align*}
\sum_{k\in \ZZ} \abs{c_k}^2 
&= \sum_{c_k\in S} \abs{c_k}^2 + \sum_{c_k \in S^c} \abs{c_k}^2 \\
&\leq \sum_{c_k\in S} \abs{c_k} + \sum_{c_k \in S^c} \abs{c_k}^2 \\
&\leq \sum_{k\in \ZZ} \abs{c_k} + \sum_{c_k \in S^c} \abs{c_k}^2 \quad\text{since the $\abs{c_k}$ are all positive} \\
&= \norm{\vector c}_{\ell^1} + \sum_{c_k \in S^c} \abs{c_k}^2 \\
&\leq \norm{\vector c}_{\ell^1} + \abs{S^c}\cdot N \\
&< \infty
.\end{align*}

Claim: $L^2([0, 1]) \subseteq L^1([0, 1])$.

- It suffices to show that $\int \abs{f}^2 < \infty \implies \int \abs{f} < \infty$.
- Define $S = \theset{x\in [0, 1] \suchthat \abs{f(x)} \leq 1}$, then $x\in S^c \implies \abs{f(x)}^2 \geq \abs{f(x)}$.

- Break up the integral:
\begin{align*}
\int_\RR \abs f 
&= \int_S \abs f + \int_{S^c} \abs f \\
&\leq \int_S \abs{f} + \int_{S^c} \abs{f}^2 \\
&\leq \int_S \abs{f} + \norm{f}_2 \\
&\leq \sup_{x\in S}\theset{\abs{f(x)}} \cdot \mu(S) + \norm{f}_2 \\
&= 1 \cdot \mu(S) + \norm{f}_2 \quad\text{by definition of } S\\
&\leq 1 \cdot \mu([0, 1]) + \norm{f}_2 \quad\text{since } S\subseteq [0, 1] \\
&= 1 + \norm{f}_2 \\
&< \infty
.\end{align*}


> Note: this proof shows $L^2(X) \subseteq L^1(X)$ whenever $\mu(X) < \infty$.

# Fall 2019

## 1

> Cesaro mean/summation. Break series apart into pieces that can be handled separately.

## a

Prove a stronger result: 
$$
a_k \to S \implies S_N\definedas \frac 1 N \sum_{k=1}^N a_k \to S
.$$

> Idea: once $N$ is large enough, $a_k \approx S$, and all smaller terms will die off as $N\to \infty$.
>
> See [this MSE answer](https://math.stackexchange.com/questions/514802/convergence-of-series-implies-convergence-of-cesaro-mean).

- Use convergence $a_k \to S$: choose $M$ large enough such that 
$$
k\geq M+1 \implies \abs{a_k - S} < \varepsilon
.$$


Then
\begin{align*}
\left|\left(\frac{1}{N} \sum_{k=1}^{N} a_{k}\right)-S\right| 
&= {1\over N} \abs{ \qty{\sum_{k=1}^N a_k} - NS  } \\
&= {1\over N} \abs{ \qty{\sum_{k=1}^N a_k} - \sum_{k=1}^N S  } \\
&=\frac{1}{N}\left|\sum_{k=1}^{N}\left(a_{k}-S\right)\right| \\
&\leq \frac{1}{N} \sum_{k=1}^{N}\left|a_{k}-S\right| \\
&= {1\over N} \sum_{k=1}^M \abs{a_k - S} + \sum_{k=M+1}^N \abs{a_k - S} \\
&\leq {1\over N} \sum_{k=1}^M \abs{a_k - S} + \sum_{k=M+1}^N {\eps \over 2} \\
&= {1\over N} \sum_{k=1}^M \abs{a_k - S} + (N - M){\eps \over 2} \\
&\converges{\eps\to 0}\to {1\over N} \sum_{k=1}^M \abs{a_k - S} + 0 \\
&\converges{N\to \infty}\to 0 + 0
.\end{align*}
  
> Note: $M$ is fixed, so the last sum is some constant $c$, and $c/N \to 0$ as $N\to\infty$ for any constant.
> To be more careful, choose $M$ first to get $\eps/2$ for the tail, then choose $N(M)>M$ for the remaining truncated part of the sum. 

## b

- Define
\begin{align*}
\Gamma_n \definedas \sum_{k=n}^\infty \frac{a_k}{k}
.\end{align*}

- $\Gamma_1 = \sum_{k=1}^n \frac{ a_k } k$ is the original series and each $\Gamma_n$ is a tail of $\Gamma_1$, so by assumption $\Gamma_n \converges{n\to\infty}\to 0$.

- Compute
\begin{align*}
\frac 1 n \sum_{k=1}^n a_k 
&= \frac 1 n (\Gamma_1 + \Gamma_2 + \cdots + \Gamma_{n} \mathbf{- \Gamma_{n+1}}) \\
.\end{align*}

- This comes from consider the following summation:
\begin{tikzcd}
\Gamma_1:&\arrow[dash, ddddd]   & a_1 & + \frac{a_2}{2} & + \frac{a_3}{3} & + \cdots &     &                                    &          &  &  &  \\
\Gamma_2:                                                       &               &     & \frac{a_2}{2}   & + \frac{a_3}{3} & + \cdots &     &                                    &          &  &  &  \\
\Gamma_3:                                                       &               &     &                 & \frac{a_3}{3}   & + \cdots &     &                                    &          &  &  &  \\
 \arrow[dash, rrrrrrrrrr] &&&&&&&&&&{}&   \\
\sum_{i=1}^n \Gamma_i:                                          &               & a_1 & +a_2            & +a_3            & + \cdots & a_n & + \frac{a_{n+1}}{n+1}              & + \cdots &  &  &  \\
& {}               &     &                 &                 &          &     &   &          &  &  & 
\end{tikzcd}

- Use part (a): since $\Gamma_n \converges{n\to\infty}\to 0$, we have ${1\over n} \sum_{k=1}^n \Gamma_k \converges{n\to\infty}\to 0$.
- Also a minor check: $\Gamma_n \to 0 \implies {1\over n}\Gamma_n \to 0$.
- Then
\begin{align*}
\frac 1 n \sum_{k=1}^n a_k 
&= \frac 1 n (\Gamma_1 + \Gamma_2 + \cdots + \Gamma_{n} \mathbf{- \Gamma_{n+1}}) \\
&= \qty{ {1\over n } \sum_{k=0}^n \Gamma_k } - \qty{{1\over n}\Gamma_{n+1} } \\
&\converges{n\to\infty}\to 0
.\end{align*}

$\qed$

## 2

> DCT, and bounding in the right place. Don't evaluate the actual integral!

- By induction on the number of limits we can pass through the integral.
- For $n=1$ we first pass one derivative into the integral: let $x_n \to x$ be any sequence converging to $x$, then
\begin{align*}
\dd{}{x} {\sin(x) \over x} 
&= \dd{}{x} \int_0^1 \cos(tx)\,dt  \\
&= \lim_{x_n\to x} {1\over x_n - x} \qty{ \int_0^1 \cos(t x_n)\,dt  - \int_0^1 \cos(tx) \,dt} \\
&= \lim_{x_n\to x} \qty{ \int_0^1 { \cos(tx_n)  - \cos(tx) \over x_n - x}   \,dt} \\
&= \lim_{x_n\to x} \qty{ \int_0^1 \qty{t\sin(tx)\mid_{x=\xi_n}}  \,dt} \qtext{where} \xi_n \in [x_n, x] \text{ by MVT}, \xi_n\to x \\
&= \lim_{\xi_n\to x} \qty{ \int_0^1 t \sin(t \xi_n)  \,dt}  \\
&=_{\text{DCT}}  \int_0^1 \lim_{\xi_n \to x} t \sin(t \xi_n)  \,dt \\
&= \int_0^1 t\sin(tx) \,dt \\
.\end{align*}

- Taking absolute values we obtain an upper bound 
\begin{align*}
\abs{ \dd{}{x} {\sin(x) \over x} } 
&= \abs{ \int_0^1 t\sin(tx) \,dt } \\
&\leq \int_0^1 \abs{t\sin(tx)} \,dt \\
&\leq \int_0^1 1 \, dt = 1
,\end{align*}
  since $t\in [0, 1] \implies \abs{t} < 1$, and $\abs{\sin(xt)} \leq 1$ for any $x$ and $t$.

- Note that this bound also justifies the DCT, since the functions $f_n(t) = t\sin(t \xi_n )$ are uniformly dominated by $g(t) = 1$ on $L^1([0, 1])$.

> Note: integrating by parts here yields the actual formula:
\begin{align*}
\int_0^1 t\sin(tx) \,dt 
&=_{\text{IBP}} \qty{-t\cos(tx) \over x}\mid_{t=0}^{t=1} - \int_0^1 {\cos(tx) \over x} \,dt \\
&= {-\cos(x) \over x} - {\sin(x) \over x^2} \\
&= {x\cos(x) - \sin(x) \over x^2}
.\end{align*}

- For the inductive step, we assume that we can pass $n-1$ limits through the integral and show we can pass the $n$th through as well.
\begin{align*}
\dd{^n}{x^n} {\sin(x) \over x} 
&= \dd{^n}{x^n} \int_0^1 \cos(tx)\,dt  \\
&= \dd{}{x} \int_0^1 \dd{^{n-1}}{x^{n-1}} \cos(tx)\,dt  \\
&= \dd{}{x} \int_0^1 t^{n-1} f_{n-1}(x, t) \,dt 
\end{align*}
  - Note that $f_n(x, t) = \pm \sin(tx)$ when $n$ is odd and $f_n(x, t) = \pm \cos(tx)$ when $n$ is even, and a constant factor of $t$ is multiplied when each derivative is taken.

- We continue as in the base case:
\begin{align*}
\dd{}{x} \int_0^1 t^{n-1} f_{n-1}(x, t) \,dt 
&= \lim_{x_k\to x} \int_0^1 t^{n-1} \qty{ f_{n-1}(x_n, t) - f_{n-1}(x, t) \over x_n - x} \,dt \\
&=_{\text{IVT}} \lim_{x_k\to x} \int_0^1 t^{n-1} \dd{f_{n-1}}{x}(\xi_k, t) \,dt \quad\text{where } \xi_k\in [x_k, x],\, \xi_k \to x \\
&=_{\text{DCT}} \int_0^1 \lim_{x_k\to x} t^{n-1} \dd{f_{n-1}}{x}(\xi_k, t) \,dt \\
&\definedas \int_0^1 \lim_{x_k\to x} t^{n} f_n(\xi_k, t) \,dt \\
&\definedas \int_0^1 t^{n} f_n(x, t) \,dt 
.\end{align*}
  - We've used the fact that $f_0(x) = \cos(tx)$ is smooth as a function of $x$, and in particular continuous 
  - The DCT is justified because the functions $h_{n, k}(x, t) = t^n f_n(\xi_k, t)$ are again uniformly (in $k$) bounded by 1 since $t\leq 1 \implies t^n \leq 1$ and each $f_n$ is a sin or cosine.

- Now take absolute values
\begin{align*}
\abs {\dd{^n}{x^n} {\sin(x) \over x}  }
&= \abs{ \int_0^1 -t^n f_n(x, t) ~dt } \\ 
&\leq \int_0^1 \abs{t^n f_n(x, t)} ~dt \\
&\leq \int_0^1 \abs{t^n} \abs{f_n(x, t)} ~dt \\
&\leq \int_0^1 \abs{ t^n} \cdot 1 ~dt \\ 
&\leq \int_0^1 t^n ~dt \quad\text{since $t$ is positive} \\ 
&= \frac{1}{n+1} \\
&< \frac{1}{n}
.\end{align*}
  - We've again used the fact that $f_n(x, t)$ is of the form $\pm \cos(tx)$ or $\pm \sin(tx)$, both of which are bounded by 1.

$\qed$

## 3

Concepts used:

- Borel-Cantelli: for a sequence of sets $X_n$, 
\begin{align*}
\limsup_n X_n &= \theset{x \suchthat x\in X_n \text{ for infinitely many $n$} } 
&= \intersect_{m\in \NN} \union_{n\geq m} X_n
\\
\liminf_n X_n &= \theset{x \suchthat x\in X_n \text{ for all but finitely many $n$} }
&= \union_{m\in \NN} \intersect_{n\geq m} X_n
.\end{align*}

- Properties of logs and exponentials:
\begin{align*}
\prod_n e^{x_n} = e^{\Sigma_n x_n} \quad\text{and} \quad \sum_n \log(x_n) = \log\left(\prod_n x_n\right)
.\end{align*}

- Tails of convergent sums vanish.
-  Continuity of measure: $B_n \searrow B$ and $\mu(B_0)<\infty$ implies $\lim_n \mu(B_n) = \mu(B)$, and $B_n\nearrow B \implies \lim_n \mu(B_n) = \mu(B)$.

### a

- The Borel $\sigma\dash$algebra is closed under countable unions/intersections/complements, 
- $B = \limsup_n B_n$ is an intersection of unions of measurable sets.

### b

- Tails of convergent sums go to zero, so $\sum_{n\geq M} \mu(B_n) \mapsvia{M\to\infty} 0$, 
- $B_M \definedas \intersect_{m = 1}^M \union_{n\geq m} B_n \searrow B$.

\begin{align*}
\mu(B_M) 
&= \mu\left(\intersect_{m\in \NN} \union_{n\geq m} B_n\right) \\
&\leq \mu\left( \union_{n\geq m} B_n \right) \quad \text{for all } m\in \NN \text{ by countable subadditivity} \\ 
&\to 0
,\end{align*}

- The result follows by continuity of measure.

### c

- To show $\mu(B) = 1$, we'll show $\mu(B^c) = 0$.

- Let $B_k = \intersect_{m=1}^\infty \union_{n = m}^K B_n$. Then
\begin{align*}
\mu(B_K^c) 
&= \mu \left(\union_{m=1}^\infty \intersect_{n=m}^K B_n^c\right) \\
&\leq \sum_{m=1}^\infty \mu\left( \intersect_{n=m}^K B_n^c \right) \quad\text{ by subadditivity} \\
&= \sum_{m=1}^\infty \prod_{n=m}^K \qty{1 - \mu(B_n)} \quad \text{by assumption} \\ 
&\leq \sum_{m=1}^\infty \prod_{n=m}^K e^{-\mu(B_n^c)} \quad\text{by hint} \\
&= \sum_{m=1}^\infty \exp{-\sum_{n=m}^K \mu(B_n^c)} \\
&\converges{K\to\infty}\to 0
\end{align*}
  since $\displaystyle\sum_{n=m}^K \mu(B_n^c) \converges{K\to\infty}\to \infty$ by assumption 

- We can apply continuity of measure since $B_K^c \mapsvia{K\to\infty} B^c$.

> Proving the hint: ?

$\qed$

## 4

Concepts used:

- Bessel's Inequality
- Pythagoras
- Surjectivity of the Riesz map
- Parseval's Identity
- Trick -- remember to write out finite sum $S_N$, and consider $\norm{x - S_N}$.


### a

**Claim:**
\begin{align*}
0 \leq \left\|x-\sum_{n=1}^{N}\left\langle x, u_{n}\right\rangle u_{n}\right\|^{2}
&= \|x\|^{2}-\sum_{n=1}^{N}\left|\left\langle x, u_{n}\right\rangle\right|^{2} \\ 
&\implies
\sum_{n=1}^{\infty}\left|\left\langle x, u_{n}\right\rangle\right|^{2} \leq\|x\|^{2}
.\end{align*}

*Proof:*
Let $S_N = \sum_{n=1}^N \inner{x}{u_n} u_n$. 
Then
\begin{align*}
0 
&\leq \norm{x - S_N}^2 \\ 
&= \inner{x - S_n}{x - S_N} \\
&= \norm{x}^2 - \sum_{n=1}^N \abs{\inner{x}{u_n}}^2 \\
&\mapsvia{N\to\infty} \norm{x}^2 - \sum_{n=1}^N \abs{\inner{x}{u_n}}^2
.\end{align*}


### b

1. Fix $\theset{a_n} \in \ell^2$, then note that $\sum \abs{a_n}^2 < \infty \implies$ the tails vanish.

2. Define 
$$
x \definedas \displaystyle\lim_{N\to\infty} S_N = \lim_{N\to \infty} \sum_{k=1}^N a_k u_k
$$

3. $\theset{S_N}$ Cauchy (by 1) and $H$ complete $\implies x\in H$.

4.  
$$
\inner{x}{u_n} = \inner{\sum_k a_k u_k}{u_n} = \sum_k a_k \inner{u_k}{u_n} = a_n \quad \forall n\in \NN
$$ 
since the $u_k$ are all orthogonal.

5.
$$
\norm{x}^2 = \norm{\sum_k a_k u_k}^2 = \sum_k \norm{a_k u_k}^2 = \sum_k \abs{a_k}^2
$$ 
by Pythagoras since the $u_k$ are normal.

> Bonus: We didn't use completeness here, so the Fourier series may not actually converge to $x$.
If $\theset{u_n}$ is **complete** (so $x = 0 \iff \inner{x}{u_n} = 0 ~\forall n$) then the Fourier series *does* converge to $x$ and $\sum_{n=1}^{\infty}\left|\left\langle x, u_{n}\right\rangle\right|^{2}=\|x\|^{2}$ for all $x \in H$.

$\qed$

## 5

> Continuity in $L^1$ (recall that DCT won't work! Notes 19.4, prove it for a dense subset first).
>
> Lebesgue differentiation in 1-dimensional case. See HW 5.6.

## a

Choose $g\in C_c^0$ such that $\norm{f- g}_1 \to 0$.

By translation invariance, $\norm{\tau_h f - \tau_h g}_1 \to 0$.

Write
\begin{align*}
\norm{\tau f - f}_1 
&= \norm{\tau_h f - g + g - \tau_h g + \tau_h g - f}_1 \\
&\leq \norm{\tau_h f - \tau_h g} + \norm{g - f} + \norm{\tau_h g - g} \\
&\to \norm{\tau_h g - g}
,\end{align*}

so it suffices to show that $\norm{\tau_h g - g} \to 0$ for $g\in C_c^0$.

Fix $\varepsilon > 0$.
Enlarge the support of $g$ to $K$ such that
\begin{align*}
\abs{h} \leq 1 \text{ and } x \in K^c \implies \abs{g(x-h) - g(x)} = 0
.\end{align*}

By uniform continuity of $g$, pick $\delta \leq 1$ small enough such that 
$$
x\in K, ~\abs{h} \leq \delta \implies \abs{g(x-h) -g(x)} < \varepsilon
,$$

then
$$
\int_K \abs{g(x-h) - g(x)} \leq \int_K \varepsilon = \varepsilon \cdot m(K) \to 0.
$$


## b

We have
\begin{align*}
\int_\RR \abs{A_h(f)(x)} ~dx 
&= \int_\RR \abs{\frac{1}{2h} \int_{x-h}^{x+h} f(y)~dy} ~dx \\
&\leq \frac{1}{2h} \int_\RR \int_{x-h}^{x+h} \abs{f(y)} ~dy ~dx    \\
&=_{FT} \frac{1}{2h} \int_\RR \int_{y-h}^{y+h} \abs{f(y)} ~\mathbf{dx} ~\mathbf{dy}    \\
&= \int_\RR \abs{f(y)} ~{dy} \\
&= \norm{f}_1
.\end{align*}

and (rough sketch)

\begin{align*}
\int_\RR \abs{A_h(f)(x) - f(x)} ~dx 
&= \int_\RR \abs{ \left(\frac{1}{2h} \int_{B(h, x)} f(y)~dy\right) - f(x)}~dx \\
&= \int_\RR \abs{ \left(\frac{1}{2h} \int_{B(h, x)} f(y)~dy\right) - \frac{1}{2h}\int_{B(h, x)} f(x) ~dy}~dx \\
&\leq_{FT} \frac{1}{2h} \int_\RR  \int_{B(h, x)}\abs{ f(y-x) - f(x)} ~\mathbf{dx} ~\mathbf{dy} \\
&\leq \frac 1 {2h} \int_\RR \norm{\tau_x f - f}_1 ~dy \\
&\to 0 \quad\text{by (a)}
.\end{align*}

$\qed$

# Spring 2019

## 1

### a

- Let $\theset{f_n}$ be  a Cauchy sequence in $C(I, \norm{\wait}_\infty)$, so $\lim_n\lim_m \norm{f_m - f_n}_\infty = 0$, we will show it converges to some $f$ in this space.
- For each fixed $x_0 \in [0, 1]$, the sequence of real numbers $\theset{f_n(x_0)}$ is Cauchy in $\RR$ since
$$
x_0\in I \implies \abs{f_m(x_0) - f_n(x_0)} \leq \sup_{x\in I} \abs{f_m(x) - f_n(x)} \definedas \norm{f_m - f_n}_\infty \converges{m>n\to\infty}\to 0,
$$
- Since $\RR$ is complete, this sequence converges and we can define $f(x) \definedas \lim_{k\to \infty} f_n(x)$.
- Thus $f_n\to f$ pointwise by construction
- Claim: $\norm{f - f_n} \converges{n\to\infty}\to 0$, so $f_n$ converges to $f$ in $C([0, 1], \norm{\wait}_\infty)$.

  - Proof:
    - Fix $\eps > 0$; we will show there exists an $N$ such that $n\geq N \implies \norm{f_n - f} < \eps$
    - Fix an $x_0 \in I$. Since $f_n \to f$ pointwise, choose $N_1$ large enough so that $$n\geq N_1 \implies \abs{f_n(x_0) - f(x_0)} < \eps/2.$$
    - Since $\norm{f_n - f_m}_\infty \to 0$, choose and $N_2$ large enough so that $$n, m \geq N_2 \implies \norm{f_n - f_m}_\infty < \eps/2.$$
    - Then for $n, m \geq \max(N_1, N_2)$, we have
  \begin{align*}
        \abs{f_n(x_0) - f(x_0)} 
  &=    \abs{f_n(x_0) - f(x_0) + f_m(x_0) - f_m(x_0)} \\
  &=    \abs{f_n(x_0) - f_m(x_0) + f_m(x_0) - f(x_0)} \\
  &\leq \abs{f_n(x_0) - f_m(x_0)} + \abs{f_m(x_0) - f(x_0)} \\
  &<  \abs{f_n(x_0) - f_m(x_0)} + {\eps \over 2} \\
  &\leq  \sup_{x\in I} \abs{f_n(x) - f_m(x)} + {\eps \over 2} \\
  &<  \norm{f_n - f_m}_\infty + {\eps \over 2} \\
  &\leq  {\eps \over 2} + {\eps \over 2} \\ 
  \implies \abs{f_n(x_0) - f(x_0)} &< \eps\\
  \implies \sup_{x\in I} \abs{f_n(x_0) - f(x_0)} &\leq \sup_{x\in I} \eps \quad\text{by order limit laws} \\
  \implies \norm{f_n - f} &\leq \eps\\
  .\end{align*}

- $f$ is the uniform limit of continuous functions and thus continuous, so $f\in C([0, 1])$.

### b

- It suffices to produce a Cauchy sequence that does not converge to a continuous function. 

- Take the following sequence of functions:
  - $f_1$ increases linearly from 0 to 1 on $[0, 1/2]$ and is 1 on $[1/2, 1]$
  - $f_2$ is 0 on $[0, 1/4]$ increases linearly from 0 to 1 on $[1/4, 1/2]$ and is 1 on $[1/2, 1]$
  - $f_3$ is 0 on $[0, 3/8]$ increases linearly from 0 to 1 on $[3/8, 1/2]$ and is 1 on $[1/2, 1]$
  - $f_3$ is 0 on $[0, (1/2 - 3/8)/2]$ increases linearly from 0 to 1 on $[(1/2 - 3/8)/2, 1/2]$ and is 1 on $[1/2, 1]$

  > Idea: take sequence starting points for the triangles: $0, 0 + {1\over 4}, 0 + {1 \over 4} + {1\over 8}, \cdots$ which converges to $1/2$ since $\sum_{k=1}^\infty{1\over 2^k} = -{1\over 2} + \sum_{k=0}^\infty  {1\over 2^k}$.


![](figures/image_2020-06-29-20-40-22.png)

- Then each $f_n$ is clearly integrable, since its graph is contained in the unit square.
- $\theset{f_n}$ is Cauchy: geometrically subtracting areas yields a single triangle whose area tends to 0.
- But $f_n$ converges to $\chi_{[{1\over 2}, 1]}$ which is discontinuous.

> Todo: show that $\int_0^1 \abs{f_n(x) - f_m(x)} \,dx \to 0$ rigorously, show that no $g\in L^1([0, 1])$ can converge to this indicator function.

## 2


### a

> See Folland p.26

- Lemma 1: $\mu(\disjoint_{k=1}^\infty E_k) = \lim_{N\to\infty} \sum_{k=1}^N \mu(E_k)$.

- Suppose $F_0 \supseteq F_1 \supseteq \cdots$.
- Let $A_k = F_k \setminus F_{k+1}$, since the $F_k$ are nested the $A_k$ are disjoint
- Set $A \definedas \disjoint_{k=1}^\infty A_k$ and $F \definedas \intersect_{k=1}^\infty F_k$.
- Note $X = X\setminus Y ~\disjoint~ X\intersect Y$ for any two sets (just write $X\setminus Y \definedas X\intersect  Y^c$)
- Note that $A$ contains anything that was removed from $F_0$ when passing from any $F_j$ to $F_{j+1}$, while $F$ contains everything that is never removed at any stage, and these are disjoint possibilities.
- Thus $F_0 = F \disjoint A$, so 
\begin{align*}
\mu(F_0) 
&= \mu(F) + \mu(A) \\
&= \mu(F) + \mu(\disjoint_{k=1}^\infty A_k) \\
&= \mu(F) + \lim_{n\to\infty} \sum_{k=0}^n \mu(A_k) \quad \text{by countable additivity}\\
&= \mu(F) + \lim_{n\to\infty} \sum_{k=0}^n \mu(F_k) - \mu(F_{k+1}) \\
&= \mu(F) + \lim_{n\to\infty} \left( \mu(F_1) - \mu(F_n) \right) \quad\text{(Telescoping)} \\
&=\mu(F) + \mu(F_1) - \lim_{N\to\infty} \mu(F_n)
,\end{align*}

- Since $\mu$ is a finite measure, $\mu(F_1) < \infty$ and can be subtracted, yielding
\begin{align*}
\mu(F_1) &= \mu(F) + \mu(F_1) - \lim_{n\to\infty} \mu(F_n) \\
\implies \mu(F) &= \lim_{n\to\infty} \mu(F_n) \\
\implies \mu\qty{\intersect_{k=1}^\infty F_k} &= \lim_{n\to\infty} \mu(F_n)
.\end{align*}

### b

- Toward a contradiction, negate the implication: suppose there exists an $\eps>0$ such that for all $\delta$, we have $m(E) < \delta$ but $\mu(E) > \eps$.
- The sequence $\theset{\delta_n \definedas {1\over 2^n}}_{n\in \NN}$ and produce sets $A_n\in \mcb$ such $m(A_n) < {1\over 2^n}$ but $\mu(A_n) > \varepsilon$.
- Define
\begin{align*}
F_n &\definedas \union_{j\geq n} A_j \\
C_m &\definedas \intersect_{k=1}^m F_k \\
A &\definedas C_\infty \definedas \intersect_{k=1}^\infty F_k 
.\end{align*}

- Note that $F_1 \supseteq F_2 \supseteq \cdots$, since each increase in index unions fewer sets.
- By continuity for the Lebesgue measure, 
\begin{align*}
m(A) 
= m \qty{\intersect_{k=1}^\infty F_k }
= \lim_{k\to \infty} m (F_k) 
= \lim_{k\to\infty} m\qty{\union_{j\geq k} A_j } 
\leq \lim_{k\to\infty} \sum_{j\geq k} m(A_j) 
= \lim_{k\to\infty} \sum_{j\geq k} {1\over 2^n} 
= 0
,\end{align*}
  which follows because this is the tail of a convergent sum

- Thus $m(A) = 0$ and by assumption, this implies $\mu(A) = 0$.

- However, by part (a),
\begin{align*}
\mu(A) = \lim_n \mu\left( \union_{k=n}^\infty A_k \right)
\geq \lim_n \mu(A_n) = \lim_n \varepsilon = \varepsilon > 0
.\end{align*}
\todo{All messed up.}

## 3

Concepts used:

- Definition of $L^+$: space of measurable function $X\to [0, \infty]$.
- Fatou: For any sequence of $L^+$ functions, $\int \liminf f_n \leq \liminf \int f_n$.
- Egorov's Theorem: If $E\subseteq \RR^n$ is measurable, $m(E) > 0$, $f_k:E\to \RR$ a sequence of measurable functions where $\lim_{n\to\infty} f_n(x)$ exists and is finite a.e., then $f_n\to f$ *almost uniformly*: for every $\eps>0$ there exists a closed subset $F_\eps \subseteq E$ with $m(E\setminus F) < \eps$ and $f_n\to f$ uniformly on $F$.


$L^2$ bound:

- Since $f_k \to f$ almost everywhere, $\liminf_n f_n(x) = f(x)$ a.e.
- $\norm{f_n}_2 < \infty$ implies each $f_n$ is measurable and thus $\abs{f_n}^2 \in L^+$, so we can apply Fatou:

\begin{align*}
\norm{f}_2^2
&= \int \abs{f(x)}^2  \\
&= \int \liminf_n \abs{f_n(x)}^2 \\
&\underset{\text{Fatou}}\leq\liminf_n \int \abs{f_n(x)}^2 \\
&\leq \liminf_n M \\
&= M
.\end{align*}

- Thus $\norm{f}_2 \leq \sqrt{M} < \infty$ implying $f\in L^2$.

Equality of Integrals: \todo{What is the "right" proof here that uses the first part?}

- Take the sequence $\eps_n = {1\over n}$
- Apply Egorov's theorem: obtain a set $F_\eps$ such that $f_n \to f$ uniformly on $F_\eps$ and $m(I\setminus F_\eps) < \eps$. 
\begin{align*}
\lim_{n\to \infty} \abs{ \int_0^1 f_n - f }
&\leq \lim_{n\to\infty} \int_0^1 \abs{f_n - f} \\
&= \lim_{n\to\infty} \qty{ \int_{F_\eps} \abs{f_n - f} + \int_{I\setminus F_\eps} \abs{f_n - f} } \\
&= \int_{F_\eps} \lim_{n\to\infty} \abs{f_n - f} + \lim_{n\to\infty} \int_{I\setminus F_\eps} \abs{f_n - f} \quad\text{by uniform convergence} \\ 
&= 0 + \lim_{n\to\infty} \int_{I\setminus F_\eps} \abs{f_n - f}
,\end{align*}

  so it suffices to show $\int_{I\setminus F_\eps} \abs{f_n - f} \converges{n\to\infty}\to 0$.

- We can obtain a bound using Holder's inequality with $p=q=2$:
\begin{align*}
\int_{I\setminus F_\eps} \abs{f_n - f} 
&\leq \qty{ \int_{I\setminus F_\eps} \abs{f_n - f}^2 } \qty{ \int_{I\setminus F_\eps} \abs{1}^2  } \\
&= \qty{ \int_{I\setminus F_\eps} \abs{f_n - f}^2 } \mu(F_\eps) \\
&\leq \norm{f_n - f}_2 \mu(F_\eps) \\
&\leq \qty{ \norm{f_n}_2 + \norm{f}_2 } \mu(F_\eps) \\
&\leq 2M \cdot \mu(F_\eps)
\end{align*}
  where $M$ is now a constant not depending on $\eps$ or $n$.

- Now take a nested sequence of sets $F_{\eps}$ with $\mu(F_\eps) \to 0$ and applying continuity of measure yields the desired statement.



## 4

> See S&S p.82.

### a

$\implies$:

- Suppose $f$ is a measurable function.
- Note that $\mathcal{A} = \theset{f(x) - t \geq 0} \intersect \theset{t \geq 0}$.
- Define $F(x, t) = f(x)$, $G(x, t) = t$, which are cylinders on measurable functions and thus measurable.
- Define $H(x, y) = F(x, t) - G(x, t)$, which are linear combinations of measurable functions and thus measurable.
- Then $\mathcal{A} = \theset{H \geq 0} \intersect \theset{G \geq 0}$ as a countable intersection of measurable sets, which is again measurable.


$\impliedby$:

- Suppose $\mca$ is a measurable set.
- Then FT on $\chi_{\mca}$ implies that for almost every $x\in \RR^n$, the $x\dash$slices $\mca_x$ are measurable and $
\begin{align*}
\mathcal{A}_x \definedas \theset{t\in \RR \suchthat (x, t) \in \mathcal{A}} = [0, f(x)] \implies m(\mathcal A_x) = f(x) - 0 = f(x)
\end{align*}

- But $x \mapsto m(\mathcal A_x)$ is a measurable function, and is exactly the function $x \mapsto f(x)$, so $f$ is measurable.


### b

- Note
\begin{align*}
\mathcal{A} &= \theset{(x, t) \in \RR^n\cross \RR \suchthat 0 \leq t \leq f(x)} 
\\
\mathcal{A}_t &= \theset{x
\in \RR^n \suchthat t\leq f(x) }
.\end{align*}

- Then
\begin{align*}
\int_{\RR^n} f(x) ~dx 
&= \int_{\RR^n} \int_0^{f(x)} 1 ~dt~dx \\
&= \int_{\RR^n} \int_{0}^\infty \chi_\mathcal{A} ~dt~dx \\
&\overset{F.T.}= \int_{0}^\infty \int_{\RR^n} \chi_\mathcal{A} ~dx~dt\\
&= \int_0^\infty m(\mathcal{A}_t) ~dt
,\end{align*}
  where we just use that $\int \int \chi_\mathcal{A} = m(\mathcal{A})$

- By F.T., all of these integrals are equal. \todo{Why is FT justified.}

## 5

Concepts used:

- Holders' inequality: $\norm{fg}_1 \leq \norm{f}_p \norm{f}_q$
- Riesz Representation for $L^2$: If $\Lambda \in (L^2)\dual$ then there exists a unique $g\in L^2$ such that $\Lambda(f) = \int fg$.
- $\norm{f}_{L^\infty(X)} \definedas \inf \theset{t\geq 0 \suchthat \abs{f(x)} \leq t \text{ almost everywhere} }$.
- **Lemma**:  $m(X) < \infty \implies L^p(X) \subset L^2(X)$.

> *Proof:*
> Write Holder's inequality as $\norm{fg}_1 \leq \norm{f}_a \norm{g}_b$ where $\frac 1 a + \frac 1 b = 1$, then
\begin{align*}
\norm{f}_p^p = \norm{\abs f^p}_1 \leq \norm{\abs f^p}_a ~\norm{1}_b
.\end{align*}
>
> Now take $a = \frac 2 p$ and this reduces to 
\begin{align*}
\norm{f}_p^p &\leq \norm{f}_2^p ~m(X)^{\frac 1 b} \\
\implies \norm{f}_p &\leq \norm{f}_2 \cdot O(m(X)) < \infty
.\end{align*}


### a

- Note $X = [0, 1] \implies m(X) = 1$.
- By Holder's inequality with $p=q=2$, 
\begin{align*}
\norm{f}_1 = \norm{f\cdot 1}_1 \leq \norm{f}_2 \cdot \norm{1}_2 = \norm{f}_2 \cdot m(X)^{\frac 1 2} = \norm{f}_2,
\end{align*}

- Thus $L^2(X) \subseteq L^1(X)$ 
- Since they share a common dense subset (simple functions) $L^2$ is dense in $L^1$ \todo{What theorem is this using?}

### b

Let $\Lambda \in L^1(X)\dual$ be arbitrary.

#### (i): Existence of $g$ Representing $\Lambda$.

- Let $f\in L^2\subseteq L^1$ be arbitrary

- Claim: $\Lambda\in L^1(X)\dual \implies \Lambda \in L^2(X)\dual$.

  - Suffices to show that $\norm{\Gamma}_{L^2(X)\dual} \definedas \sup_{\norm{f}_2 = 1} \abs{\Gamma(f)} < \infty$, since bounded implies continuous.

  - By the lemma, $\norm{f}_1 \leq C\norm{f}_2$ for some constant $C \approx m(X)$.

  - Note $$\norm{\Lambda}_{L^1(X)\dual} \definedas \displaystyle\sup_{\norm{f}_1 = 1} \abs{\Lambda(f)}$$

  - Define $\hat f = {f\over \norm{f}_1}$ so $\norm{\hat f}_1 = 1$

  - Since $\norm{\Lambda}_{1\dual}$ is a supremum over *all* $f \in L^1(X)$ with $\norm{f}_1 =1$, 
  \begin{align*}
  \abs{\Lambda(\hat f)} \leq \norm{\Lambda}_{(L^1(X))\dual}
  ,\end{align*}

  - Then
  \begin{align*}
\frac{\abs{\Lambda(f)}}{\norm{f}_1} &= \abs{\Lambda(\hat f)} \leq \norm{\Lambda}_{L^1(X)\dual} \\
  \implies \abs{\Lambda(f)} 
  &\leq \norm{\Lambda}_{1\dual} \cdot \norm{f}_1 \\
  &\leq \norm{\Lambda}_{1\dual} \cdot C \norm{f}_2 < \infty \quad\text{by assumption}
  ,\end{align*}

  - So $\Lambda \in (L^2)\dual$.

- Now apply Riesz Representation for $L^2$: there is a $g \in L^2$ such that $$f\in L^2 \implies \Lambda(f) = \inner{f}{g} \definedas \int_0^1 f(x) \bar{g(x)}\, dx.$$

#### (ii): $g$ is in $L^\infty$

- It suffices to show $\norm{g}_{L^\infty(X)} < \infty$.
- Since we're assuming $\norm{\Gamma}_{L^1(X)\dual} < \infty$, it suffices to show the stated equality. \todo{Is this assumed..? Or did we show it..?}

- Claim: $\norm{\Lambda}_{L^1(X)\dual} =\norm{g}_{L^\infty(X)}$
  - The result follows because $\Lambda$ was assumed to be in $L^1(X)\dual$, so $\norm{\Lambda}_{L^1(X)\dual} < \infty$.
  - $\leq$: 
  \begin{align*}
  \norm{\Lambda}_{L^1(X)\dual} 
  &= \sup_{\norm{f}_1 = 1} \abs{\Lambda(f)} \\
&= \sup_{\norm{f}_1 = 1} \abs{\int_X f \bar g} \quad\text{by (i)}\\
  &= \sup_{\norm{f}_1 = 1} \int_X \abs{f \bar g} \\
  &\definedas \sup_{\norm{f}_1 = 1} \norm{fg}_1 \\
  &\leq \sup_{\norm{f}_1 = 1} \norm{f}_1 \norm{g}_\infty \quad\text{by Holder with } p=1,q=\infty\\
  &= \norm{g}_\infty
  ,\end{align*}

  - $\geq$:

    - Suppose toward a contradiction that $\norm{g}_\infty > \norm{\Lambda}_{1\dual}$.

    - Then there exists some $E\subseteq X$ with $m(E) > 0$ such that $$x\in E \implies \abs{g(x)} > \norm{\Lambda}_{L^1(X)\dual}.$$

    - Define 
    \begin{align*}
    h = \frac{1}{m(E)} \frac{\overline{g}}{\abs g} \chi_E
    .\end{align*}
  
    - Note $\norm{h}_{L^1(X)} = 1$.
    
    - Then
    \begin{align*}
    \Lambda(h) &= \int_X hg \\
    &\definedas \int_X \frac{1}{m(E)} \frac{g \overline g}{\abs g} \chi_E \\
    &= \frac{1}{m(E)} \int_E \abs{g} \\
    &\geq \frac{1}{m(E)} \norm{g}_\infty m(E) \\
    &= \norm{g}_\infty \\
    &> \norm{\Lambda}_{L^1(X)\dual}
    ,\end{align*}
      a contradiction since $\norm{\Lambda}_{L^1(X)\dual}$ is the supremum over all $h_\alpha$ with $\norm{h_\alpha}_{L^1(X)} = 1$.


#  Fall 2018

## 1

Concepts used:

- Uniform continuity.

Show a stronger statement: $f(x) = \frac 1 x$ is uniformly continuous on any interval of the form $(c, \infty)$ where $c > 0$.

- Note that
$$
\abs{x}, \abs y > c > 0 \implies \abs{xy} = \abs{x}\abs{y} > c^2 \implies \frac{1}{\abs{xy}} < \frac 1 {c^{2}}
.$$

- Letting $\varepsilon$ be arbitrary, choose $\delta < \varepsilon c^2$.
 - Note that $\delta$ does not depend on $x, y$.
- Then
\begin{align*}
\abs{f(x) - f(y)}
&= \abs{\frac 1 x - \frac 1 y} \\
&= \frac{\abs{x-y}}{xy} \\
&\leq \frac{\delta}{xy} \\
&< \frac{\delta}{c^2} \\
&< \varepsilon
,\end{align*}
  which shows uniform continuity.

To see that $f$ is not uniformly continuous when $c=0$:

> Note: negating uniform continuity says $\exists \eps > 0$ such that $\forall \delta(\eps)$ there exist $x, y$ such that $\abs{x-y} < \delta$ *and* $\abs{f(x) - f(y)} > \eps$.

- Let $\varepsilon < 1$.
- Let $x_n = \frac 1 n$ for $n\geq 1$.
- Choose $n$ large enough such that $\abs{x_n - x_{n+1}} = \frac 1 n - \frac 1 {n+1} < \delta$.
  - Why this can be done: by the archimedean property of $\RR$, choose $n$ such that ${1\over n} < \eps$.
  - Then
  \begin{align*}
  {1 \over n} - {1\over n+1} = {1 \over n(n+1)} \leq {1\over n} < \eps \quad\text{since }n+1 > 1
  .\end{align*}
- Note $f(x_n) = n$ and thus $$\abs{f(x_n) - f(x_{n+1})} = n - (n+1) = 1 > \varepsilon.$$

$\qed$

## 2

Concepts used:

- Definition of measurability: there exists an open $O\supset E$ such that $m_*(O\setminus E) < \eps$ for all $\eps> 0$.
- Theorem: $E$ is Lebesgue measurable iff there exists a closed set $F\subseteq E$ such that $m_*(E\setminus F) < \eps$ for all $\eps>0$.
- Every $F_\sigma, G_\delta$ is Borel.
- Claim: $E$ is measurable $\iff$ for every $\varepsilon$ there exist $F_\varepsilon \subset E \subset G_\varepsilon$ with $F_\varepsilon$ closed and $G_\varepsilon$ open and $m(G_\varepsilon \setminus E)< \varepsilon$ and $m(E\setminus F_\varepsilon) < \varepsilon$.
  - Proof: existence of $G_\eps$ is the definition of measurability.
  - Existence of $F_\eps$: ?

- Claim: $E$ is measurable $\implies$ there exists an open $O\supseteq E$ such that $m(O\setminus E) = 0$.
  - Since $E$ is measurable, for each $n\in \NN$ choose $G_n \supseteq E$ such that $m_*(G_n\setminus E) < {1\over n}$.
  - Set $O_N \definedas \intersect_{n=1}^N G_n$ and $O\definedas \intersect_{n=1}^\infty G_n$.
  - Suppose $E$ is bounded.
    - Note $O_N \searrow O$ and $m_*(O_1) < \infty$ if $E$ is bounded, since in this case
    \begin{align*}
    m_*(G_n\setminus E) = m_*(G_1) - m_*(E) < 1 \iff m_*(G_1) < m_*(E) + {1\over n} < \infty
    .\end{align*}
    - Note $O_N \setminus E \searrow O \setminus E$ since $O_N\setminus E \definedas O_N \intersect E^c \supseteq O_{N+1} \intersect E^c$ for all $N$, and again $m_*(O_1 \setminus E) < \infty$.
    - So it's valid to apply continuity of measure from above:
\begin{align*}
m_*(O\setminus E) 
&= \lim_{N\to\infty} m_*(O_N\setminus E) \\ 
&\leq \lim_{N\to \infty} m_*(G_N\setminus E) \\ 
&= \lim_{N\to\infty} {1\over N} = 0
,\end{align*}
      where the inequality uses subadditivity on $\intersect_{n=1}^N G_n \subseteq G_N$
  - Suppose $E$ is unbounded.
    - Write $E^k = E \intersect [k, k+1]^d \subset \RR^d$ as the intersection of $E$ with an annulus, and note that $E = \disjoint_{k\in \NN} E_k$.
    - Each $E_k$ is bounded, so apply the previous case to obtain $O_k \supseteq E_k$ with $m(O_k\setminus E_k) = 0$.
    - So write $O_k = E_k \disjoint N_k$ where $N_k \definedas O_k \setminus E_k$ is a null set.
    - Define $O = \union_{k\in \NN} O_k$, note that $E\subseteq O$.
    - Now note
\begin{align*}
O\setminus E 
&= \qty{\disjoint_k O_k}\setminus \qty{\disjoint_K E_k} \\
&\subseteq \disjoint_k \qty{O_k \setminus E_k} \\
\implies m_*(O\setminus E) 
&\leq m_*\qty{\disjoint \qty{O_k \setminus E_k} } = 0
,\end{align*}
  since any countable union of null sets is again null.
  - So $O\supseteq E$ with $m(O\setminus E) = 0$.
- Theorem: since $E$ is measurable, $E^c$ is measurable
  - Proof: It suffices to write $E^c$ as the union of two measurable sets, $E^c = S \union (E^c - S)$, where $S$ is to be determined.
  - We'll produce an $S$ such that $m_*(E^c - S) = 0$ and use the fact that any subset of a null set is measurable.
  - Since $E$ is measurable, for every $\eps > 0$ there exists an open $\OO_\eps \supseteq E$ such that $m_*(\OO_\eps \setminus E) < \eps$.
  - Take the sequence $\theset{\eps_n \definedas {1\over n}}$ to produce a sequence of sets $\OO_n$.
  - Note that each $\OO_n^c$ is closed and 
  \begin{align*}
  \OO_n \supseteq E \iff \OO_n^c \subseteq E^c
  .\end{align*}
  - Set $S \definedas \union_n \OO_n^c$, which is a union of closed sets, thus an $F_\sigma$ set, thus Borel, thus measurable.
  - Note that $S\subseteq E^c$ since each $\OO_n \subseteq E^c$.
  - Note that
  \begin{align*}
  E^c\setminus S 
  &\definedas E^c \setminus \qty{\union_{n=1}^\infty \OO_n^c} \\
&\definedas E^c \intersect \qty{\union_{n=1}^\infty \OO_n^c}^c  \quad\text{definition of set minus} \\ 
  &= E^c \intersect \qty{\intersect_{n=1}^\infty \OO_n}^c  \quad \text{De Morgan's law}\\
  &= E^c \union \qty{\intersect_{n=1}^\infty \OO_n}  \\
  &\definedas \qty{ \intersect_{n=1}^\infty \OO_n} \setminus E \\
  & \subseteq \OO_N \setminus E \quad \text{for every } N\in \NN
  .\end{align*}
  - Then by subadditivity,
    $$
    m_*(E^c\setminus S) \leq m_*(\OO_N \setminus E) \leq {1\over N} \quad \forall N \implies m_*(E^c\setminus S) = 0
    .$$
  - Thus $E^c\setminus S$ is measurable.
  
### Indirect Proof

- Since $E$ is measurable, $E^c$ is measurable.
- Since $E^c$ is measurable exists an open $O\supseteq E^c$ such that $m(O\setminus E^c) = 0$.
- Set $B \definedas O^c$, then $O\supseteq E^c \iff \OO^c \subseteq E \iff B\subseteq E$.
- Computing measures yields 
\begin{align*}
E\setminus B \definedas E\setminus  \OO^c \definedas E\intersect (\OO^c)^c = E\intersect \OO = \OO \intersect(E^c)^c \definedas \OO \setminus E^c
,\end{align*}
  thus $m(E\setminus B) = m(\OO\setminus E^c) = 0$.
- Since $\OO$ is open, $B$ is closed and thus Borel.


### Direct Proof

? \todo{Try to construct the set.}


## 3

Concepts used:

-  Mean Value Theorem
- DCT

\begin{align*}
\dd{}{t} F(t) 
&= \dd{}{t} \int_\RR f(x) \cos(xt) ~dx \\
&\overset{DCT}= \int_\RR f(x) \dd{}{t} \cos(xt) ~dx \\
&= \int_\RR xf(x) \cos(xt)~dx
,\end{align*}
so it only remains to justify the DCT.

- Fix $t$, then let $t_n \to t$ be arbitrary.
- Define 
$$
h_n(x, t) = f(x)
\left(\frac{\cos(tx) - \cos(t_n x)}{t_n - t}\right) \converges{n\to\infty}\to \dd{}{t} \qty{f(x) \cos(xt)}
$$
 since $\cos(tx)$ is differentiable in $t$ and this is the limit definition of differentiability.

- Note that
\begin{align*}
\dd{}{t} \cos(tx) 
&\definedas \lim_{t_n \to t} \frac{\cos(tx) - \cos(t_n x)}{t_n - t} \\
&\overset{MVT} = \dd{}{t}\cos(tx)\mid_{t  = \xi_n} \hspace{6em} \text{for some } \xi_n \in [t, t_n] \text{ or } [t_n, t] \\
&= x\sin(\xi_n x)
\end{align*}
  where $\xi_n \converges{n\to\infty}\to t$ since wlog $t_n \leq \xi_n \leq t$ and $t_n \nearrow t$.

- We then have $$\abs{h_n(x)} = \abs{f(x) x\sin(\xi_n x)} \leq \abs{xf(x)}\quad\text{since } \abs{\sin(\xi_n x)} \leq  1$$ for every $x$ and every $n$.
- Since $xf(x) \in L^1(\RR)$ by assumption, the DCT applies. 

## 4

Case of characteristic function

- First suppose $f(x) = \chi_{[0, 1]}(x)$.
- Note that $\sin(nx)$ has a period of $2\pi/n$, and thus $\floor{n\over 2\pi}$ full periods in $[0, 1]$.
- Taking the absolute value yields a new function with half the period, so a period of $\pi/n$ and $\floor{\pi / n}$ full periods in $[0, 1]$.
- We can compute the integral over one full period (which is independent of *which* period is chosen), and since $\sin(x)$ is positive and agrees with $\abs{\sin(nx)}$ on the first period, we have
\begin{align*}
\int_{\text{One Period}} \abs{\sin(nx)} \, dx 
&= \int_0^{\pi/n} \sin(nx)\,dx \\
&= {1\over n} \int_0^\pi \sin(u) \,du \quad u = nx \\
&= {1\over n} -\cos(u)\mid_0^\pi \\
&= {2 \over n}
.\end{align*}


- Then break the integral up into integrals over periods $P_1, P_2, \cdots, P_N$ where $N \definedas \floor{n/\pi}$:
\begin{align*}
\int_0^1 \abs{\sin(nx)} \, dx 
&= \qty{ \sum_{j=1}^{N} \int_{P_j} \abs{\sin(nx)} \, dx } +  \int_{N\floor{\pi/n}}^1 \abs{\sin(nx)}\,dx \\
&= \qty{ \sum_{j=1}^{N} {2\over n} } +  \int_{N\floor{\pi/n}}^1 \abs{\sin(nx)}\,dx \\
&= N \qty{2\over n} +  \int_{N\floor{\pi/n}}^1 \abs{\sin(nx)}\,dx \\
&\definedas \floor{n \over \pi} {2\over n} +  \int_{N\floor{\pi/n}}^1 \abs{\sin(nx)}\,dx \\
&= {2\over \pi} + \int_{N\floor{\pi/n}}^1 \abs{\sin(nx)}\,dx \\
&\definedas {2\over \pi} + R(n) 
\end{align*}
  so it suffices to show that $R(n) \converges{n\to\infty}\to 0$. \todo{Need to justify removing floor function and cancellation.}

- Showing this: ???????????? \todo{No clue how to show this.}

General case

\todo{Not sure. Approximate $f$ by simple functions...?}

## 5

Concepts used:

- Claim: If $E\subseteq \RR^a \cross \RR^b$ is a measurable set, then for almost every $y\in \RR^b$, the slice $E^y$ is measurable and
\begin{align*}
m(E) = \int_{\RR^b} m(E^y) \,dy
.\end{align*}
  - Set $g = \chi_E$, which is non-negative and measurable, so apply Tonelli.
  - Conclude that $g^y = \chi_{E^y}$ is measurable, the function $y\mapsto \int g^y(x)\, dx$ is measurable, and $\int \int g^y(x)\,dx \,dy = \int g$.
  - But $\int g = m(E)$ and $\int\int g^y(x) \,dx\,dy = \int m(E^y)\,dy$.

**Solution**

> Note: $f$ is a function $\RR\to \RR$ in the original problem, but here I've assumed $f:\RR^n\to \RR$.

- Since $f\geq 0$, set 
$$
E\definedas \theset{(x, t) \in \RR^{n} \cross \RR \suchthat f(x) > t}
= \theset{(x, t) \in \RR^n \cross \RR \suchthat 0 \leq t < f(x)}
.$$
- Claim: since $f$ is measurable, $E$ is measurable and thus $m(E)$ makes sense.
  - Since $f$ is measurable, $F(x, t) \definedas t - f(x)$ is measurable on $\RR^n \cross \RR$.
  - Then write $E = \theset{F < 0} \intersect \theset{t\geq 0}$ as an intersection of measurable sets.
- We have slices 
\begin{align*}
E^t &\definedas \theset{x\in \RR^n \suchthat (x, t) \in E} = \theset{x\in \RR^n \suchthat 0 \leq t < f(x)} \\
E^x &\definedas \theset{t\in \RR \suchthat (x, t) \in E} = \theset{t\in \RR \suchthat 0 \leq t \leq f(x)} = [0, f(x)]
.\end{align*}
  - $E_t$ is precisely the set that appears in the original RHS integrand.
  - $m(E^x) = f(x)$.
- Claim: $\chi_E$ satisfies the conditions of Tonelli, and thus $m(E) = \int \chi_E$ is equal to any iterated integral.
  - Non-negative: clear since $0\leq \chi_E \leq 1$
  - Measurable: characteristic functions of measurable sets are measurable.

- Conclude:
  1. For almost every $x$, $E^x$ is a measurable set, $x\mapsto m(E^x)$ is a measurable function, and $m(E) = \int_{\RR^n} m(E^x) \, dx$ 
  2. For almost every $t$, $E^t$ is a measurable set, $t\mapsto m(E^t)$ is a measurable function, and $m(E) = \int_{\RR} m(E^t) \, dt$ 
- On one hand,
\begin{align*}
m(E) 
&= \int_{\RR^{n+1}} \chi_E(x, t) \\
&= \int_{\RR} \int_{\RR^n} \chi_E(x, t) \,dt \,dx \quad\text{by Tonelli}\\
&= \int_{\RR^n} m(E^x) \,dx \quad\text{first conclusion}\\
&= \int_{\RR^n} f(x) \,dx 
.\end{align*}
- On the other hand,
\begin{align*}
m(E) 
&= \int_{\RR^{n+1}} \chi_E(x, t) \\
&= \int_\RR \int_{\RR^n} \chi_E(x, t) \, dx \,dt \quad\text{by Tonelli} \\
&= \int_\RR m(E^t) \,dt \quad\text{second conclusion}
.\end{align*}

- Thus
\begin{align*}
\int_{\RR^n} f \,dx = m(E) = \int_\RR m(E^t) \,dt = \int_\RR m\qty{\theset{x\suchthat f(x) > t}}
.\end{align*}

$\qed$

## 6

- Note that $x^{1\over n} \converges{n\to\infty}\to 1$ for any $0 < x < \infty$.
- Thus the integrand converges to ${1\over e^x}$, which is integrable on $(0, \infty)$ and integrates to 1.
- Break the integrand up:
\begin{align*}
\int_0^\infty {1 \over  \qty{ 1 + {x\over n} }^n x^{1\over n}} \,dx
= \int_0^1 {1 \over  \qty{ 1 + {x\over n} }^n x^{1\over n}} \,dx
= \int_1^\infty {1 \over  \qty{ 1 + {x\over n} }^n x^{1\over n}} \,dx
.\end{align*}

# Spring 2018

## 1

Concepts used:

- Borel-Cantelli: If $\theset{E_k}_{k\in\ZZ}\subset 2^\RR$ is a countable collection of Lebesgue measurable sets with $\sum_{k\in \ZZ} m(E_k) < \infty$, then almost every $x\in \RR$ is in *at most finitely* many $E_k$.
  - Equivalently (?), $m(\limsup_{k\to\infty} E_k) = 0$, where $\limsup_{k\to\infty} E_k = \intersect_{k=1}^\infty \union_{j\geq k} E_j$, the elements which are in $E_k$ for infinitely many $k$.

**Solution**:

- Strategy: Borel-Cantelli.

- We'll show that $m(E) \intersect [n, n+1] = 0$ for all $n\in \ZZ$; then the result follows from 
\begin{align*}
m(E) = m \qty{\union_{n\in \ZZ} E \intersect [n, n+1]} \leq \sum_{n=1}^\infty m(E \intersect [n, n+1]) = 0
.\end{align*}

- By translation invariance of measure, it suffices to show $m(E \intersect [0, 1]) = 0$.
  - So WLOG, replace $E$ with $E\intersect [0, 1]$.

- Define
\begin{align*}
E_j \definedas \theset{x\in [0, 1] \suchthat \
\exists p\in \ZZ^{\geq 0} \text{ s.t. } \abs{x - \frac{p}{j} } < \frac 1 {j^3}} 
.\end{align*}

  - Note that $E_j \subseteq \disjoint_{p\in \ZZ^{\geq 0}} B_{j^{-3}}\qty{p\over j}$, i.e. a union over integers $p$ of intervals of radius $1/j^3$ around the points $p/j$.
    Since $1/j^3 < 1/j$, this union is in fact disjoint.

- Importantly, note that 
  \begin{align*}
\limsup_{j\to\infty} E_j \definedas \intersect_{n=1}^\infty \union_{j=n}^\infty E_j = E
  \end{align*}
  
  since 
  
  \begin{align*}
  x \in \limsup_j E_j 
  &\iff x \in E_j \text{ for infinitely many } j  \\
  &\iff \text{ there are infinitely many $j$ for which there exist a $p$ such that } \abs{x - {p\over j}} < j^{-3}  \\
  &\iff \text{ there are infinitely many such pairs $p, j$}  \\
  &\iff x\in E
  .\end{align*}

- Intersecting with $[0, 1]$, we can write $E_j$ as a union of intervals:
\begin{align*}
E_j =& \qty{0, {j^{-3}}} 
\quad \disjoint \quad 
B_{j^{-3}}\qty{1\over j} \disjoint
B_{j^{-3}}\qty{2\over j} \disjoint
\cdots \disjoint
B_{j^{-3}}\qty{j-1\over j} 
\quad \disjoint \quad 
(1 - {j^{-3}}, 1)
,\end{align*}
  where we've separated out the "boundary" terms to emphasize that they are balls about $0$ and $1$ intersected with $[0, 1]$.


- Since $E_j$ is a union of open sets, it is Borel and thus Lebesgue measurable.

- Computing the measure of $E_j$:

  - For a fixed $j$, there are exactly $j+1$ possible choices for a numerator ($0, 1, \cdots, j$), thus there are exactly $j+1$ sets appearing in the above decomposition.

  - The first and last intervals are length $1 \over j^3$ 
  - The remaining $(j+1)-2 = j-1$ intervals are twice this length, $2 \over j^3$
  - Thus
  $$
  m(E_j) = 2 \qty{1 \over j^3} + (j-1) \qty{2 \over j^3} = {2 \over j^2}
  $$

- Note that 
\begin{align*}
\sum_{j\in \NN} m(E_j) =  2\sum_{j\in \NN} \frac 1 {j^2} < \infty
,\end{align*}
  which converges by the $p\dash$test for sums.
  
- But then
\begin{align*}
m(E) 
&= m(\limsup_j E_j) \\
&= m(\intersect_{n\in \NN} \union_{j\geq n} E_j) \\
&\leq m(\union_{j\geq N} E_j) \quad\text{for every } N \\
&\leq \sum_{j\geq N} m(E_j) \\
&\converges{N\to\infty}\to 0 \quad\text{}
.\end{align*}

- Thus $E$ is measurable as a subset of a null set and $m(E) = 0$.

$\qed$


## 2

### a

Claim: $f_n$ does not converge uniformly to its limit.

- Note each $f_n(x)$ is clearly continuous on $(0, \infty)$, since it is a quotient of continuous functions where the denominator is never zero.

- Note 
\begin{align*}
x < 1 \implies x^n \converges{n\to\infty}\to 0\qtext{and} x>1 \implies x^n \converges{n\to\infty}\to \infty
.\end{align*}

- Thus
\begin{align*}
f_n(x) = \frac{x}{1+ x^n}\converges{n\to\infty}\longrightarrow
f(x) \definedas
\begin{cases}
x, & 0 \leq x < 1 \\
\frac 1 2, & x = 1 \\
0, & x > 1 \\
\end{cases}
.\end{align*}

- If $f_n \to f$ uniformly on $[0, \infty)$, it would converge uniformly on every subset and thus uniformly on $(0, \infty)$.
  - Then $f$ would be a uniform limit of continuous functions on $(0, \infty)$ and thus continuous on $(0, \infty)$.
  - By uniqueness of limits, $f_n$ would converge to the pointwise limit $f$ above, which is not continuous at $x=1$, a contradiction.

### b

- If the DCT applies, interchange the limit and integral:
    \begin{align*}
    \lim_{n\to\infty }\int_0^\infty f_n(x)\, dx 
&= \int_0^\infty \lim_{n\to\infty}f_n(x) \, dx \quad\text{DCT}\\
    &=\int_0^\infty f(x) \,dx \\
    &= \int_0^1 x \,dx + \int_1^\infty 0\, dx \\
    &= {1\over 2}x^2 \evalfrom_0^1 \\
    &= {1\over 2}
    .\end{align*}

- To justify the DCT, write 
\begin{align*}
\int_0^\infty f_n(x)
= \int_0^1 f_n(x) + \int_1^\infty f_n(x)
.\end{align*}

- $f_n$ restricted to $(0, 1)$ is uniformly bounded by $g_0(x) = 1$ in the first integral, since
  \begin{align*}
  x \in [0, 1] \implies \frac{x}{1+x^n} < \frac{1}{1+x^n} < 1 \definedas g(x)
  \end{align*}
  so 
  \begin{align*}
  \int_0^1 f_n(x)\,dx \leq \int_0^1 1 \,dx = 1 < \infty
  .\end{align*}
  Also note that $g_0\cdot \chi_{(0, 1)} \in L^1((0, \infty))$.

- The $f_n$ restricted to $(1, \infty)$ are uniformly bounded by $g_1(x) = {1\over x^{2}}$ on $[1, \infty)$, since
  \begin{align*}
  x \in (1, \infty) \implies \frac{x}{1+x^n} \leq {x \over x^n} = {1 \over x^{n-1}} \leq {1\over x^2}\in L^1([1, \infty) \text{ when } n\geq 3
  ,\end{align*}
  by the $p\dash$test for integrals.

- So set $$g \definedas g_0 \cdot \chi_{(0, 1)} + g_1 \cdot \chi_{[1, \infty)},$$ then by the above arguments $g \in L^1((0, \infty))$ and $f_n \leq g$ everywhere, so the DCT applies.

## 3

Concepts used:

- $\norm{f}_\infty \definedas \inf_t {\theset{ t\suchthat m\qty{\theset{x\in \RR^n \suchthat f(x) > t}} = 0 } }$, i.e. this is the lowest upper bound that holds almost everywhere.

**Solution**:

- $\norm{f}_p \leq \norm{f}_\infty$:
  - Note $\abs{f(x)} \leq \norm{f}_\infty$ almost everywhere and taking $p$th powers preserves this inequality.
  - Thus
  \begin{align*}
  \abs{f(x)} &\leq \norm{f}_\infty \quad\text{a.e. by definition} \\
  \implies 
  \abs{f(x)}^p &\leq \norm{f}_\infty^p \quad\text{for } p\geq 0 \\  
  \implies
  \norm{f}_p^p 
  &= \int_X \abs{f(x)}^p ~dx \\
  &\leq \int_X \norm{f}_\infty^p ~dx  \\
  &= \norm{f}_\infty^p \int_X 1\,dx \\ 
  &= \norm{f}_\infty^p \cdot m(X) \quad\text{since the norm doesn't depend on }x \\
  &= \norm{f}_\infty^p \qquad \text{since } m(X) = 1
  .\end{align*}

    - Thus $\norm{f}_p \leq \norm{f}_\infty$ for all $p$ and taking $\lim_{p\to\infty}$ preserves this inequality.

- $\norm{f}_p \geq \norm{f}_\infty$:
  - Fix $\varepsilon > 0$.

  - Define 
  \begin{align*}
  S_\varepsilon \definedas \theset{x\in \RR^n \suchthat \abs{f(x)} \geq \norm{f}_\infty - \varepsilon}
  .\end{align*}

    - Note that $m(S_\eps) > 0$; otherwise if $m(S_\eps) = 0$, then $t\definedas \norm{f}_\infty - \eps < \norm{f}_\eps$.
    But this produces a *smaller* upper bound almost everywhere than $\norm{f}_\eps$, contradicting the definition of $\norm{f}_\eps$ as an infimum over such bounds.
    


  - Then
  \begin{align*}
  \norm{f}_p^p 
  &= \int_X \abs{f(x)}^p ~dx \\
  &\geq \int_{S_\varepsilon} \abs{f(x)}^p ~dx \quad\text{since } S_\eps \subseteq X \\
  &\geq \int_{S_\varepsilon} \abs{\norm{f}_\infty - \varepsilon}^p ~dx \quad\text{since on } S_\eps, \abs{f} \geq \norm{f}_\infty - \eps \\
  &= \abs{\norm{f}_\infty - \varepsilon}^p \cdot m(S_\varepsilon) \quad\text{since the integrand is independent of }x \\
  & \geq 0 \quad\text{since } m(S_\eps) > 0
  \end{align*}
  
  - Taking $p$th roots for $p\geq 1$ preserves the inequality, so
  \begin{align*}
  \implies \norm{f}_p &\geq \abs{\norm{f}_\infty - \varepsilon} \cdot m(S_\varepsilon)^{\frac 1 p} 
  \converges{p\to\infty}\to \abs{\norm{f}_\infty - \varepsilon} 
  \converges{\varepsilon \to 0}\to \norm{f}_\infty
  \end{align*}
  where we've used the fact that above arguments work 

  - Thus $\norm{f}_p \geq \norm{f}_\infty$.

$\qed$

## 4



### Proof 1: Using Fourier Transforms

Concepts used:

- Weierstrass Approximation: A uniformly continuous function on a compact set can be uniformly approximated by polynomials.

**Solution**:

- Fix $k \in \ZZ$.
- Since $e^{2\pi i k x}$ is continuous on the compact interval $[0, 1]$, it is uniformly continuous.
- Thus there is a sequence of polynomials $P_\ell$ such that 
$$
P_{\ell, k} \converges{\ell\to\infty}\to e^{2\pi i k x} \text{ uniformly on } [0,1]
.$$

- Note applying linearity to the assumption $\int f(x) \, x^n$, we have
$$
\int f(x) x^n \,dx = 0 ~\forall n \implies \int f(x) p(x) \,dx = 0 
$$
  for any polynomial $p(x)$, and in particular for $P_{\ell, k}(x)$ for every $\ell$ and every $k$.

- But then  
\begin{align*}
\inner{f}{e_k} 
&= \int_0^1 f(x) e^{-2\pi i k x} ~dx \\
&= \int_0^1 f(x) \lim_{\ell \to \infty} P_\ell(x) \\
&= \lim_{\ell \to \infty}  \int_0^1 f(x) P_\ell(x) \quad\quad \text{by uniform convergence on a compact interval} \\
&= \lim_{\ell \to \infty} 0 \quad\text{by assumption}\\
&= 0 \quad \forall k\in \ZZ
,\end{align*}
 so $f$ is orthogonal to every $e_k$. 

- Thus $f\in S^\perp \definedas \spanof_\CC\theset{e_k}_{k\in \ZZ}^\perp \subseteq L^2([0, 1])$, but since this is a basis, $S$ is dense and thus $S^\perp = \theset{0}$ in $L^2([0, 1])$.

- Thus $f\equiv 0$ in $L^2([0, 1])$, which implies that $f$ is zero almost everywhere.

$\qed$

### Alternative Proof

Concepts used

- $C^1([0, 1])$ is dense in $L^2([0, 1])$
- Polynomials are dense in $L^p(X, \mathcal{M}, \mu)$ for any $X\subseteq \RR^n$ compact and $\mu$ a finite measure, for all $1\leq p < \infty$.
  - Use Weierstrass Approximation, then uniform convergence implies $L^p(\mu)$ convergence by DCT.

**Solution**:

- By density of polynomials, for $f\in L^2([0, 1])$ choose $p_\eps(x)$ such that $\norm{f - p_\eps} < \eps$ by Weierstrass approximation.
- Then on one hand,
\begin{align*}
\norm{f(f-p_\eps)}_1 
&= \norm{f^2}_1 - \norm{f\cdot p_\eps}_1 \\
&= \norm{f^2}_1 - 0 \quad\text{by assumption} \\
&= \norm{f}_2^2
.\end{align*}

  - Where we've used that $\norm{f^2}_1 = \int \abs{f^2} = \int \abs{f}^2 = \norm{f}_2^2$.

- On the other hand
\begin{align*}
\norm{f(f-p_\eps)} 
&\leq \norm{f}_1 \norm{f-p_\eps}_\infty \quad\text{by Holder} \\
&\leq \eps \norm{f}_1  \\
&\leq \eps \norm{f}_2 \sqrt{m(X)} \\ 
&= \eps \norm{f}_2 \quad\text{since } m(X)= 1
.\end{align*}
  - Where we've used that $\norm{fg}_1 = \int \abs{fg} = \int \abs{f}\abs{g} \leq \int \norm{f}_\infty \abs{g} = \norm{f}_\infty \norm{g}_1$.

- Combining these,
\begin{align*}
\norm{f}_2^2 \leq \norm{f}_2 \eps \implies \norm{f}_2 < \eps \to 0,
.\end{align*}
  so $\norm{f}_2 = 0$, which implies $f=0$ almost everywhere.

## 5

Concepts used:

- $\int \abs{f_n - f} \to \iff \int f_n = \int f$.
- Fatou:
\begin{align*}
\int \liminf f_n \leq \liminf \int f_n \\
\int \limsup f_n \geq \limsup \int f_n
.\end{align*}

**Solution**:

- Since $\int \abs{f_n} \converges{n\to\infty}\to \int \abs{f}$, define
\begin{align*}
h_n &= \abs{f_n - f} &\converges{n\to\infty}\to 0 ~a.e.\\
g_n &= \abs{f_n} + \abs{f} &\converges{n\to\infty}\to 2\abs {f} ~a.e.
\end{align*}

  - Note that $g_n - h_n \converges{n\to\infty}\to 2\abs{f} - 0 = 2\abs{f}$.

- Then
\begin{align*}
\int 2 \abs {f} 
&= \int \liminf_n (g_n - h_n) \\
&= \int \liminf_n(g_n) + \int \liminf_n(-h_n) \\
&= \int \liminf_n(g_n) - \int \limsup_n(h_n) \\
&= \int 2 \abs{f} - \int \limsup_n(h_n) \\
&\leq \int 2\abs{f} - \limsup_n \int h_n \quad\text{by Fatou}
,\end{align*}

- Since $f\in L^1$, $\int 2\abs{f}  = 2\norm{f}_1 < \infty$ and it makes sense to subtract it from both sides, thus
\begin{align*}
0 &\leq - \limsup_n \int h_n \\
&\definedas - \limsup_n \int \abs{f_n - f}
.\end{align*}
  which forces $\limsup_n \int \abs{f_n -f}  = 0$, since
    
    - The integral of a nonnegative function is nonnegative, so $\int \abs{f_n - f} \geq 0$.
    - So $\qty{ -\int \abs{f_n - f} } \leq 0$.
    - But the above inequality shows $\qty{ -\int \abs{f_n - f} } \geq 0$ as well.
- Since $\liminf_n \int h_n \leq \limsup_n \int h_n = 0$, $\lim_n \int h_n$ exists and is equal to zero.

- But then 
\begin{align*}
\abs{\int f_n - \int f}
&= \abs{\int f_n -f}
\leq \int \abs{f_n - f}
,\end{align*}
  and taking $\lim_{n\to\infty}$ on both sides yields
  \begin{align*}
  \lim_{n\to\infty} \abs{\int f_n - \int f} \leq \lim_{n\to\infty} \int \abs{f_n - f} = 0
  ,\end{align*}
  so $\lim_{n\to\infty} \int f_n = \int f$.

$\qed$

# Fall 2017

## 1

Note that $f(x) = e^x$ is entire and thus equal to its power series.
So $f(x) = \sum_{j=0}^\infty \frac 1 {j!}x^j$.

Letting $f_N(x) = \sum_{j=1}^N \frac 1 {j!} x^j$, we have $f_N(x) \to f(x)$ pointwise on $(-\infty ,\infty)$.

For any compact interval $[-M, M]$, we have

\begin{align*}
\norm{f_N(x) - f(x)}_\infty
&= \sup_{-M\leq x \leq M} ~\abs{\sum_{j=N+1}^\infty \frac 1 {j!} x^j} \\
&\leq \sup_{-M\leq x \leq M} ~ \sum_{j=N+1}^\infty \frac 1 {j!} \abs{x}^j \\
&\leq \sum_{j=N+1}^\infty \frac 1 {j!} M^j \\
&\leq \sum_{j=0}^\infty \frac 1 {j!} M^j \\
&= e^M \\
&<\infty
,\end{align*}

so $f_N \to f$ uniformly on $[-M, M]$ by the M-test.
Thus it converges on any bounded interval.

It does not converge on $\RR$, since $x^N$ is unbounded.

## 2

### a

It suffices to consider the bounded case, i.e. $E \subseteq B_M(0)$ for some $M$.
Then write $E_n = B_n(0) \intersect E$ and apply the theorem to $E_n$, and by subadditivity, $m^*(E) = m^*(\union_n E_n) \leq \sum_n m^*(E_n) = 0$.

**Lemma:** 
$f(x) = x^2, f\inv(x) = \sqrt{x}$ are Lipschitz on any compact subset of $[0, \infty)$.
 
*Proof:*
Let $g = f$ or $f\inv$. 
Then $g\in C^1([0, M])$ for any $M$, so $g$ is differentiable and $g'$ is continuous.
Since $g'$ is continuous on a compact interval, it is bounded, so $\abs{g'(x)} \leq L$ for all $x$.
Applying the MVT,
\begin{align*}
\abs{f(x) - f(y)} = f'(c) \abs{x-y} \leq L \abs{x-y}
.\end{align*}
  
**Lemma:** 
If $g$ is Lipschitz on $\RR^n$, then $m(E) = 0 \implies m(g(E)) = 0$.

*Proof:*
If $g$ is Lipschitz, then 
$$
g(B_r(x)) \subseteq B_{Lr}(x)
,$$ 
which is a dilated ball/cube, and so 
$$
m^*(B_{Lr}(x)) \leq L^n \cdot m^*(B_{r}(x))
.$$

Now choose $\theset{Q_j} \rightrightarrows E$; then $\theset{g(Q_j)} \rightrightarrows g(E)$.

By the above observation,
\begin{align*}
\abs{g(Q_j)} \leq L^n \abs{Q_j}
,\end{align*}

and so 
\begin{align*}
m^*(g(E)) \leq \sum_j \abs{g(Q_j)} \leq \sum_j L^n \abs{Q_j} = L^n \sum_j \abs{Q_j} \to 0 
.\end{align*}

Now just take $g(x) = x^2$ for one direction, and $g(x) = f\inv(x) = \sqrt{x}$ for the other.
$\qed$

### b

> Lemma: $E$ is measurable iff $E = K \disjoint N$ for some $K$ compact, $N$ null.

Write $E = K \disjoint N$ where $K$ is compact and $N$ is null.

Then $\phi\inv(E) = \phi\inv(K \disjoint N) = \phi\inv(K) \disjoint \phi\inv(N)$.

Since $\phi\inv(N)$ is null by part (a) and $\phi\inv(K)$ is the preimage of a compact set under a continuous map and thus compact, $\phi\inv(E) = K' \disjoint N'$ where $K'$ is compact and $N'$ is null, so $\phi\inv(E)$ is measurable.

So $\phi$ is a measurable function, and thus yields a well-defined map $\mathcal L(\RR) \to \mathcal L(\RR)$ since it preserves measurable sets.
Restricting to $[0, \infty)$, $f$ is bijection, and thus so is $\phi$.

$\qed$

## 3

> From homework: $E$ is Lebesgue measurable iff there exists a finite union of closed cubes $A$ such that $m(E\Delta A) < \varepsilon$.

It suffices to show that $S$ is dense in simple functions, and since simple functions are *finite* linear combinations of characteristic functions, it suffices to show this for $\chi_A$ for $A$ a measurable set.

Let $s = \chi_{A}$.
By regularity of the Lebesgue measure, choose an open set $O \supseteq A$ such that $m(O\setminus A) < \varepsilon$.

$O$ is an open subset of $\RR$, and thus $O = \disjoint_{j\in \NN} I_j$ is a disjoint union of countably many open intervals.

Now choose $N$ large enough such that $m(O \Delta I_{N, n}) < \varepsilon = \frac 1 n$ where we define $I_{N, n} \definedas \disjoint_{j=1}^N I_j$.

Now define $f_n = \chi_{I_{N, n}}$, then
\begin{align*}
\norm{s - f_n}_1 = \int \abs{\chi_A - \chi_{I_{N, n}}} = m(A \Delta I_{N, n}) \converges{n\to\infty}\longrightarrow 0
.\end{align*}

Since any simple function is a finite linear combination of $\chi_{A_i}$, we can do this for each $i$ to extend this result to all simple functions.
But simple functions are dense in $L^1$, so $S$ is dense in $L^1$.

## 4

### a

Let $G(x) = \sum_{n=1}^\infty nx(1-x)^n$. 
Applying the ratio test, we have
\begin{align*}
\abs{\frac{(n+1)x(1-x)^{n+1}}{nx(1-x)^n}} = \frac{n+1}{n} \abs{1-x} \converges{n\to\infty}\to \abs{1-x} < 1 \iff 0 \leq x \leq 2
,\end{align*}

and in particular, this series converges on $[0, 2]$. 
Thus its terms go to zero, and $nx(1-x)^n \to 0$ on $[0, 1] \subset [0, 2]$.

To see that the convergence is not uniform, let $x_n = \frac 1 n$ and $\varepsilon > \frac 1 e$, then
\begin{align*}
\sup_{x\in [0, 1]}\abs{nx(1-x)^n - 0} 
\geq \abs{nx_n (1-x_n)^n} 
= \abs{\left( 1 - \frac 1 n\right)^n} 
\converges{n\to\infty}\to e\inv
> \varepsilon
.\end{align*}


### b

> Note: could use the first part with $\sin(x) \leq x$, but then integral ends up more complicated.

Noting that $\sin(x) \leq 1$, we have
We have
\begin{align*}
\abs{\int_0^1  n(1-x)^{n} \sin(x)} 
&\leq \int_0^1  \abs{n(1-x)^n \sin(x)} \\
&\leq \int_0^1  \abs{n (1-x)^n}  \\
&= n\int_0^1 (1-x)^n \\
&= -\frac{n(1-x)^{n+1}}{n+1} \\
&\converges{n\to\infty}\longrightarrow 0
.\end{align*}

## 5


### a

**Lemma:** If $\phi \in C_c^1$, then
$(f \ast \phi)' = f \ast \phi'$ almost everywhere.

*Silly Proof:*

\begin{align*}
\mathcal{F}(
	(f \ast \phi)'
 )
&= 2\pi i \xi ~\mathcal{F}(f\ast \phi) \\
&= 2\pi i \xi ~ \mathcal{F}(f) ~ \mathcal{F}(\phi) \\
&= \mathcal{F}(f) \cdot \left( 2\pi i \xi ~\mathcal{F}(\phi)\right) \\
&= \mathcal{F}(f) \cdot \mathcal{F}(\phi') \\
&= \mathcal{F}(f\ast \phi')
.\end{align*}

*Actual proof*:

\begin{align*}
(f\ast \phi)'(x)
&= (\phi\ast f)'(x) \\
&= \lim_{h\to 0} \frac{(\phi\ast f)'(x+h) - (\phi\ast f)'(x)}{h} \\
&= \lim_{h\to 0} \int \frac{\phi(x + h - y) - \phi(x - y)}{h} f(y) \\
&\overset{DCT}=  \int \lim_{h\to 0} \frac{\phi(x + h - y) - \phi(x - y)}{h} f(y) \\
&= \int \phi'(x-y) f(y) \\
&= (\phi' \ast f)(x) \\
&= (f \ast \phi')(x)
.\end{align*}
 

 To see that the DCT is justified, we can apply the MVT on the interval $[0, h]$ to $f$ to obtain

\begin{align*}
\frac{\phi(x + h - y) - \phi(x - y)}{h}
&= \phi'(c) \quad c\in [0, h]
,\end{align*}
 
and since $\phi'$ is continuous and compactly supported, $\phi'$ is bounded by some $M < \infty$ by the extreme value theorem and thus
\begin{align*}
\int \abs{\frac{\phi(x + h - y) - \phi(x - y)}{h} f(y)} 
&= \int \abs{\phi'(c) f(y)} \\
&\leq \int \abs{M}\abs{f} \\
&= \abs{M} \int \abs{f} < \infty
,\end{align*}

since $f\in L^1$ by assumption, so we can take $g\definedas \abs{M} \abs{f}$ as the dominating function.

Applying this theorem infinitely many times shows that $f\ast \phi$ is smooth.

To see that $f\ast \phi$ is compactly supported, approximate $f$ by a *continuous* compactly supported function $h$, so $\norm{h - f}_1 \converges{L^1}\to 0$. 

Now let $g_x(y) = \phi(x-y)$, and note that $\mathrm{supp}(g) = x - \mathrm{supp}(\phi)$ which is still compact.
 
But since $\mathrm{supp}(h)$ is bounded, there is some $N$ such that 
$$
\abs{x} > N \implies A_x\definedas \mathrm{supp}(h) \intersect \mathrm{supp}(g_x) = \emptyset
$$

and thus 
\begin{align*}
(h\ast \phi)(x) 
&= \int_\RR \phi(x-y) h(y)~dy \\
&= \int_{A_x} g_x(y) h(y) \\
&= 0
,\end{align*}

so $\theset{x \suchthat f\ast g(x) = 0}$ is open, and its complement is closed and bounded and thus compact.

### b

\begin{align*}
\norm{f\ast K_j - f}_1 
&= \int \abs{\int f(x-y) K_j(y) ~dy  - f(x)}~dx \\
&= \int \abs{\int f(x-y) K_j(y) ~dy  - \int f(x) K_j(y) ~ dy}~dx \\
&= \int \abs{\int ( f(x-y) - f(x) ) K_j(y) ~dy } ~dx \\
&\leq \int \int \abs{(f(x-y) - f(x))} \cdot \abs{K_j(y)} ~ dy~dx \\
&\overset{FT}= \int \int \abs{(f(x-y) - f(x))} \cdot \abs{K_j(y)} \mathbf{~ dx~dy}\\
&= \int \abs{K_j(y)} \left( \int \abs{(f(x-y) - f(x))}  ~ dx\right) ~dy \\
&= \int \abs{K_j(y)} \cdot \norm{f - \tau_y f}_1 ~dy
.\end{align*}

We now split the integral up into pieces. 

1. Chose $\delta$ small enough such that
 $\abs{y} < \delta \implies \norm{f - \tau_y f}_1 < \varepsilon$ by continuity of translation in $L^1$, and

2. Since $\phi$ is compactly supported, choose $J$ large enough such that
$$
j > J \implies \int_{\abs{y} \geq \delta} \abs{K_j(y)} ~dy 
= \int_{\abs{y} \geq \delta} \abs{j\phi(jy)} = 0
$$

Then
\begin{align*}
\norm{f\ast K_j - f}_1 
&\leq 
\int \abs{K_j(y)} \cdot \norm{f - \tau_y f}_1 ~dy \\
&= \int_{\abs y < \delta} \abs{K_j(y)} \cdot \norm{f - \tau_y f}_1 ~dy 
+ \int_{\abs y \geq  \delta} \abs{K_j(y)} \cdot \norm{f - \tau_y f}_1 ~dy \\
&= \varepsilon \int_{\abs y \geq  \delta} \abs{K_j(y)} + 0 \\
&\leq \varepsilon(1) \to 0
.\end{align*}

$\qed$

## 6

> Should be supremum maybe..?

Let $\theset{f_k}$ be a Cauchy sequence, so $\norm{f_k} < \infty$ for all $k$.
Then for a fixed $x$, the sequence $f_k(x)$ is Cauchy in $\RR$ and thus converges to some $f(x)$, so define $f$ by $f(x) \definedas \lim_{k\to\infty} f_k(x)$.

Then $\norm{f_k - f} = \max_{x\in X}\abs{f_k(x) - f(x)} \converges{k\to\infty}\to 0$, and thus $f_k \to f$ uniformly and thus $f$ is continuous. It just remains to show that $f$ has bounded norm.

Choose $N$ large enough so that $\norm{f - f_N} < \varepsilon$, and write $\norm{f_N} \definedas M < \infty$

\begin{align*}
\norm{f} \leq \norm{f - f_N} + \norm{f_N} < \varepsilon + M < \infty
.\end{align*}



# Spring 2017

## 1

Concepts used:

- Definition: $A$ is *nowhere dense* $\iff$ every interval $I$ contains a subinterval $S \subseteq A^c$.
  - Equivalently, the interior of the closure is empty, $\qty{\bar K}^\circ = \emptyset$.

**Solution**

Claim: **$K$ is compact**.

- It suffices to show that $K^c \definedas [0, 1]\setminus K$ is open; 
  Then $K$ will be a closed and bounded subset of $\RR$ and thus compact by Heine-Borel.

- Strategy: write $K^c$ as the union of open balls (since these form a basis for the Euclidean topology on $\RR$).
  
  - Do this by showing every point $x\in K^c$ is an interior point, i.e. $x$ admits a neighborhood $N_x$ such that $N_x \subseteq K^c$.

- Identify $K^c$ as the set of real numbers in $[0, 1]$ whose decimal expansion **does** contain a 4.
  
  - We will show that there exists a neighborhood small enough such that all points in it contain a $4$ in their decimal expansions.

- Let $x\in K^c$, suppose a 4 occurs as the $k$th digit, and write
\[  
x = 0.d_1 d_2 \cdots d_{k-1}~ 4 ~d_{k+1}\cdots 
= \qty{\sum_{j=1}^k d_j 10^{-j}} + \qty{4\cdot 10^{-k}} + \qty{\sum_{j=k+1}^\infty d_j 10^{-j}}
.\]

- Set $r_x < 10^{-k}$ and let $y \in [0, 1] \intersect B_{r_x}(x)$ be arbitrary and write 
\[  
y = \sum_{j=1}^\infty c_j 10^{-j}
.\]

- Thus $\abs{x-y} < r_x < 10^{-k}$, and the first $k$ digits of $x$ and $y$ must agree:

  - We first compute the difference:
\[  
x - y &= \sum_{i=1}^\infty d_j 10^{-j} - \sum_{i=1}^\infty c_j 10^{-j} = \sum_{i=1}^\infty \qty{d_j - c_j} 10^{-j} \\
\]
  - Thus (claim)
\[
\abs{x-y} &\leq \sum_{j=1}^\infty \abs{d_j - c_j} 10^j < 10^{-k} \iff \abs{d_j - c_j} = 0 \quad \forall j\leq k
.\]
  - Otherwise we can note that any term $\abs{d_j - c_j}\geq 1$ and there is a contribution to $\abs{x-y}$ of at least $1\cdot 10^{-j}$ for some $j < k$, whereas
\[  
j < k \iff 10^{-j} > 10^{-k}
,\]
  a contradiction.
  
- This means that for all $j \leq k$ we have $d_j = c_j$, and in particular $d_k = 4 = c_k$, so $y$ has a 4 in its decimal expansion.

- But then $K^c = \union_x B_{r_x}(x)$ is a union of open sets and thus open.


Claim: **$K$ is nowhere dense and $m(K) = 0$:**

- Strategy: Show $\qty{\bar K}^\circ = \emptyset$.
- Since $K$ is closed, $\bar K = K$, so it suffices to show that $K$ does not properly contain any interval.
- It suffices to show $m(K^c) = 1$, since this implies $m(K) = 0$ and since any interval has strictly positive measure, this will mean $K$ can not contain an interval.

- As in the construction of the Cantor set, let 

  - $K_0$ denote $[0, 1]$ with 1 interval $\left({4 \over 10}, {5 \over 10} \right)$ of length $1 \over 10$ deleted, so 
  \[m(K_0^c) = {1\over 10}.\]
  - $K_1$ denote $K_0$ with 9 intervals $\left({1 \over 100}, {5\over 100}\right), ~\left({14 \over 100}, {15 \over 100}\right), \cdots \left({94\over 100}, {95 \over 100}\right)$ of length ${1 \over 100}$ deleted, so 
  \[m(K_1^c) = {1\over 10} + {9 \over 100}.\]
  - $K_n$ denote $K_{n-1}$ with $9^{n}$ such intervals of length $1 \over 10^{n+1}$ deleted, so 
  \[m(K_n^c) = {1\over 10} + {9 \over 100} + \cdots + {9^{n} \over 10^{n+1}}.\]

- Then compute 
\[
m(K^c) 
= \sum_{j=0}^\infty {9^n \over 10^{n+1} } 
= {1\over 10} \sum_{j=0}^\infty \qty{9\over 10}^n 
= {1 \over 10} \qty{ {1 \over 1 - {9 \over 10 } } } 
= 1.
\]

Claim: **$K$ has no isolated points**:

- A point $x\in K$ is isolated iff there there is an open ball $B_r(x)$ containing $x$ such that $B_r(x) \subsetneq K^c$.
  - So every point in this ball **should** have a 4 in its decimal expansion.

- Strategy: show that if $x\in K$, every neighborhood of $x$ intersects $K$.

- Note that $m(K_n) = \left( \frac 9 {10} \right)^n \converges{n\to\infty}\to 0$ 
- Also note that we deleted open intervals, and the endpoints of these intervals are never deleted.
  - Thus endpoints of deleted intervals are elements of $K$.

- Fix $x$. Then for every $\varepsilon$, by the Archimedean property of $\RR$, choose $n$ such that $\left( \frac 9 {10} \right)^n < \varepsilon$.

- Then there is an endpoint $x_n$ of some deleted interval $I_n$ satisfying \[\abs{x - x_n} \leq  \left( \frac 9 {10} \right)^n < \eps.\]

- So every ball containing $x$ contains some endpoint of a removed interval, and thus an element of $K$.


## 2

Concepts used:

- Absolute continuity of measures: $\lambda \ll \mu \iff E\in\mathcal{M}, \mu(E) = 0 \implies \lambda(E) = 0$.
- Radon-Nikodym: if $\lambda \ll \mu$, then there exists a measurable function $\dd{\lambda}{\mu} \definedas f$ where $\lambda(E) = \int_E f \,d\mu$.
- Chebyshev's inequality:
\[  
A_c \definedas \theset{ x\in X \suchthat \abs{f(x)} \geq c  } \implies \mu(A_c) \leq c^{-p} \int_{A_c} \abs{f}^p \,d\mu \quad \forall 0 < p < \infty
.\]

### a

- Strategy: use approximation by simple functions to show absolute continuity and apply Radon-Nikodym 

- Claim: $\lambda \ll \mu$, i.e. $\mu(E) = 0 \implies \lambda(E) = 0$.

  - Note that if this holds, by Radon-Nikodym, $f = \dd{\lambda}{\mu} \implies d\lambda = f d\mu$, which would yield 
  \[  
  \int g ~d\lambda = \int g f ~d\mu
  .\]

- So let $E$ be measurable and suppose $\mu(E) = 0$.

- Then
\[
\lambda(E) \definedas \int_E f ~d\mu 
&= \lim_{n\to\infty} \theset{\int_E s_n \,d\mu \suchthat s_n \definedas \sum_{j=1}^\infty c_j \mu(E_j),\, s_n \nearrow f}
\]
  where we take a sequence of simple functions increasing to $f$.

- But since each $E_j \subseteq E$, we must have $\mu(E_j) = 0$ for any such $E_j$, so every such $s_n$ must be zero and thus $\lambda(E) = 0$.

\todo{What is the final step in this approximation?}

### b

- Set $g(x) = x^2$, note that $g$ is positive and measurable.
- By part (a), there exists a positive $f$ such that for any $E\subseteq \RR$,
\[
\int_E g ~dm = \int_E gf ~d\mu 
\]

  - The LHS is zero by assumption and thus so is the RHS.

  - $m \ll \mu$ by construction.

  - Note that $gf$ is positive.

- Define $A_k = \theset{x\in X \suchthat gf \cdot \chi_E > {1 \over k} }$, for $k\in \ZZ^{\geq 0}$

- Then by Chebyshev with $p=1$, for every $k$ we have

\[
\mu(A_k) \leq k \int_E gf ~d\mu = 0
\]

- Then noting that $A_k \searrow A \definedas \theset{x\in X \suchthat gf\cdot \chi_E(x)  > 0}$, we have $\mu(A) = 0$.

- Since $gf$ is positive, we have 
\[
x\in E \iff gf\chi_E(x) > 0 \iff x\in A
\]
  so $E = A$ and $\mu(E) = \mu(A)$.

- But $m \ll \mu$ and $\mu(E) = 0$, so we can conclude that $m(E) = 0$.


## 3

### a

Letting $x_n \definedas \frac 1 n$, we have

\begin{align*}
\sum_{k=1}^\infty \abs{f_k(x)} \geq \abs{f_n(x_n)} 
=\abs{ae^{-ax} - be^{-bx}} \definedas M
.\end{align*}

In particular, $\sup_{x} \abs{f_n(x)} \not\to 0$, so the terms do not go to zero and the sum can not converge.

### b

?

## 4

Switching to polar coordinates and integrating over a half-circle contained in $I^2$, we have
\begin{align*}
\int_{I^2} f \geq \int_0^\pi \int_0^1 \frac{\cos(\theta)\sin(\theta)}{r^2} ~dr~d\theta = \infty
,\end{align*}

so $f$ is not integrable.

## 5

## 6

> See https://math.stackexchange.com/questions/507263/prove-that-c1a-b-with-the-c1-norm-is-a-banach-space

- Denote this norm $\norm{\wait}_u$

- Let $f_n$ be a Cauchy sequence in this space, so $\norm{f_n}_u < \infty$ for every $n$ and $\norm{f_j - f_k}_u \converges{j, k\to\infty}\to 0$.

and define a candidate limit: for each $x\in I$, set \[f(x) \definedas \lim_{n\to\infty} f_n(x).\]

- Note that 
\[ 
\norm{f_n}_\infty &\leq \norm{f_n}_u < \infty \\
\norm{f_n'}_\infty &\leq \norm{f_n}_u < \infty
.\]

  - Thus both $f_n, f_n'$ are Cauchy sequences in $C^0([a, b], \norm{\wait}_\infty)$, which is a Banach space, so they converge.

- So 
  - $f_n \to f$ uniformly (by uniqueness of limits), 
  - $f_n' \to g$ uniformly for some $g$, and
  - $f, g\in C^0([a, b])$.

- Claim: $g = f'$
  - For any fixed $a\in I$, we have
  \[
  f_n(x) - f_n(a) \quad &\converges{u}\to f(x) - f(a) \\
  \int_a^x f'_n  \quad &\converges{u}\to \int_a^x  g
  .\]
  - By the FTC, the left-hand sides are equal.
  - By uniqueness of limits so are the right-hand sides, so $f' = g$.

- Claim: the limit $f$ is an element in this space.
  - Since $f, f'\in C^0([a, b])$, they are bounded, and so $\norm{f}_u < \infty$. 

- Claim: $\norm{f_n - f}_u \converges{n\to\infty}\to 0$

- Thus the Cauchy sequence $\theset{f_n}$ converges to a function $f$ in the $u\dash$norm where $f$ is an element of this space, making it complete.

# Fall 2016

## 1

- Set $f_N(x) \definedas \sum_{n=1}^N n^{-x}$, so $f(x) = \lim_{N\to\infty} f_N(x)$.
- If an interchange of limits is justified, we have
\[  
\dd{}{x} \lim_{N\to\infty} \sum_{n=1}^N n^{-x}
&= \lim_{h\to 0} \lim_{N\to\infty} {1\over h} \left[ \qty{\sum_{n=1}^N n^{-x}} - \qty{\sum_{n=1}^N n^{-(x+h)} }\right] \\
&\equalsbecause{?} \lim_{N\to\infty} \lim_{h\to 0} {1\over h} \left[ \qty{\sum_{n=1}^N n^{-x}} - \qty{\sum_{n=1}^N n^{-(x+h)} }\right] \\
&= \lim_{N\to\infty} \lim_{h\to 0} {1\over h} \left[ {\sum_{n=1}^N n^{-x}} - {n^{-(x+h)} }\right] \quad\text{(1)} \\
&= \lim_{N\to\infty} \sum_{n=1}^N \lim_{h\to 0} {1\over h} \left[ n^{-x} - n^{-(x+h)} \right] \quad\text{since this is a finite sum} \\
&\definedas \lim_{N\to\infty} \sum_{n=1}^N \dd{}{x}\qty{1 \over n^x} \\ 
&= \lim_{N\to\infty} \sum_{n=1}^N -{\ln(n) \over n^x}
,\]
  where the combining of sums in (1) is valid because $\sum n^{-x}$ is absolutely convergent for $x>1$ by the $p\dash$test.

- Thus it suffices to justify the interchange of limits and show that the last sum converges on $(1, \infty)$.

- Claim: $\sum n^{-x}\ln(n)$ converges.
  - Use the fact that for any fixed $\eps>0$,
  \[  
  \lim_{n\to\infty} {\ln(n) \over n^\eps} 
  \equalsbecause{L.H.} \lim_{n\to\infty}{1/n \over \eps n^{\eps-1}} 
  = \lim_{n\to\infty} {1\over \eps n^\eps} = 0
  ,\]
  - This implies that for a fixed $\eps >0$ and for any constant $c>0$ there exists an $N$ large enough such that $n\geq N$ implies $\ln(n)/n^\eps < c$, i.e. $\ln(n) < c n^{\eps}$.
  - Taking $c=1$, we have $n\geq N \implies \ln(n) < n^\eps$
  - We thus break up the sum:
  \[  
  \sum_{n\in \NN} {\ln(n) \over n^x} 
  &= \sum_{n=1}^{N-1} { \ln(n) \over n^x} + \sum_{n=N}^\infty {\ln(n) \over n^x} \\
  &\leq \sum_{n=1}^{N-1} { \ln(n) \over n^x} + \sum_{n=N}^\infty {n^\eps \over n^x} \\
  &\definedas C_\eps + \sum_{n=N}^\infty {n^\eps \over n^x} \quad \text{with $C_\eps<\infty$ a constant}\\
  &= C_\eps + \sum_{n=N}^\infty {1 \over n^{x-\eps}}
  ,\]
  where the last term converges by the $p\dash$test if $x-\eps > 1$.

  - But $\eps$ can depend on $x$, and if $x\in (1, \infty)$ is fixed we can choose $\eps < \abs{x-1}$ to ensure this. 


- Claim: the interchange of limits is justified.
\todo{?}



## 2


- Suppose it is *not* the case that $f=g$ almost everywhere; then letting $A\definedas \theset{x\in [a,b] \suchthat f(x) \neq g(x)}$, we have $m(A) > 0$.
- Write 
\[  
A = A_1\disjoint A_2 \definedas \theset{f>g} \disjoint \theset{f<g}
,\]
  then $m(A_1) > 0$ or $m(A_2) > 0$ (or both).

- Wlog (by relabeling $f, g$ if necessary), suppose $m(A_1) > 0$, and take $E\definedas A_1$.

- Then on $E$, we have $f(x)>g(x)$ pointwise. 
  This is preserved by monotonicity of the integral, thus
  \[  
  f(x) > g(x) \text{ on } E \implies \int_{E} f(x)\,dx > \int_{E} g(x)\, dx 
  .\] 

## 3

Concepts used:

- $C_c^\infty \injects L^p$ is dense.
- If $f

- Fixing notation, set $\tau_x f(y) \definedas f(y-x)$; we then want to show
\[  
\norm{\tau_x f -f}_{L^1} \converges{x\to 0}\to 0
.\]
- Claim: by an $\eps/3$ argument, it suffices to show this for compactly supported functions:
  - Since $f\in L^1$, choose $g_n\subset C_c^\infty(\RR^1)$ smooth and compactly supported so that $$\norm{f-g}_{L^1} < \eps.$$
  - Claim: $\norm{\tau_x f - \tau_x g} < \eps$.
    - Proof 1: translation invariance of the integral.
    - Proof 2: Apply a change of variables:
  \[  
    \norm{\tau_x f - \tau_x g}_1
    &\definedas \int_\RR \abs{\tau_x f(y) - \tau_x g(y)}\, dy \\
    &= \int_\RR \abs{f(y-x) - g(y-x)}\, dy  \\
    &= \int_\RR \abs{f(u) - g(u)}\, du \qquad (u=y-x,\, du=dy) \\
    &= \norm{f-g}_1 \\
    &< \eps
  .\]
  - Then
  \[  
  \norm{\tau_x f - f}_1 
  &= \norm{\tau_x f - \tau_x g + \tau_x g - g +g - f}_{1} \\
  &\leq \norm{\tau_x f - \tau_x g}_1 + \norm{\tau_x g - g}_1 + \norm{g - f}_{1} \\
  &\leq 2\eps + \norm{\tau_x g - g}_1
  .\]

- To show this for compactly supported functions:
  - Let $g\in C_c^\infty(\RR^1)$, let $E = \supp(g)$, and write
  \[  
  \norm{\tau_x g - g}_1 
  &= \int_\RR \abs{g(y-x) - g(y)}\,dy \\
  &= \int_E \abs{g(y-x) - g(y)} \,dy + \int_{E^c} \abs{g(y-x) - g(y)} \,dy\\
  &= \int_E \abs{g(y-x) - g(y)} \,dy 
  .\]

  - But $g$ is smooth and compactly supported on $E$, and thus uniformly continuous on $E$, so
  \[  
  \lim_{x\to 0} \int_E \abs{g(y-x) - g(y)} \,dy 
  &= \int_E \lim_{x\to 0} \abs{g(y-x) - g(y)} \,dy \\
  &= \int_E 0 \,dy \\
  &= 0
  .\]

## 4

- Claim: $G\in \mcm$.
  - Claim:
  \[  
  G = \qty{ \intersect_{N=1}^\infty \union_{n=N}^\infty E_n}^c = \union_{N=1}^\infty \intersect_{n=N}^\infty E_n^c
  .\]

    - This follows because $x$ is in the RHS $\iff$ $x\in E_n^c$ for all but finitely many $n$ $\iff$ $x\in E_n$ for at most finitely many $n$.

  - But $\mcm$ is a $\sigma\dash$algebra, and this shows $G$ is obtained by countable unions/intersections/complementes of measurable sets, so $G\in \mcm$. 

- Claim: $\mu(G) = 0$.

  - We have
  \[  
  \mu(G)
  &= \mu\qty{\union_{N=1}^\infty \intersect_{n=N}^\infty E_n^c} \\
  &\leq \sum_{N=1}^\infty \mu \qty{\intersect_{n=N}^\infty E_n^c}  \\
  &\leq \sum_{N=1}^\infty \mu(E_M^c) \\ 
  &\definedas \sum_{N=1}^\infty \mu(X\setminus E_N) \\
  &\converges{N\to\infty}\to 0
  .\]
  \todo{Last step seems wrong!}

## 5

Let $L$ be the LHS and $R$ be the RHS.

Claim: $L\leq R$.
  - Since $\abs \phi \leq \norm{\phi}_\infty$ a.e., we can write 
  \[  
  L^{1\over n} 
  &\definedas \int_\RR { \abs{\phi(x)}^n \over 1+ x^2} \\
  &\leq \int_\RR { \norm{\phi}_\infty^n \over 1+ x^2}  \\
  &= \norm{\phi}_\infty^n \int_\RR {1\over 1 + x^2} \\
  &= \norm{\phi}_\infty^n \arctan(x)\evalfrom_{-\infty}^{\infty}  \\
  &= \norm{\phi}_\infty^n \qty{{\pi \over 2} - {-\pi \over 2} }  \\
  &= \pi \norm{\phi}_\infty^n \\ \\
  \implies L^{1\over n} &\leq \sqrt[n]{\pi \norm{\phi}_\infty^n} \\ 
  \implies L &\leq \pi^{1\over n} \norm{\phi}_\infty \\
  &\converges{n\to \infty }\to \norm{\phi}_\infty
  ,\]
  where we've used the fact that $c^{1\over n} \converges{n\to\infty}\to 1$ for any constant $c$. \todo[inline]{Actually true? Need conditions?}
  
Claim: $R\leq L$.

- Use the fact that $L^2$ has small tails: if $h\in L^2(\RR)$, then for any $\eps > 0$, 
\[  
\forall \eps,\, \exist t \\lim_{t\to \pm \infty} \int_{\abs{x} \geq \abs{t}} h(x) \,dx < \eps
.\]



## 6
  

# Spring 2016

## 1

# Spring 2014

## 1
