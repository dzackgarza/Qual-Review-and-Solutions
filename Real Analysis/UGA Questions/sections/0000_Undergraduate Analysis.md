# Undergraduate Analysis: Uniform Convergence

## Fall 2018 # 1
Let $f(x) = \frac 1 x$.
Show that $f$ is uniformly continuous on $(1, \infty)$ but not on $(0,\infty)$.

:::{.solution}
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


:::



## Fall 2017 # 1
Let 
$$
f(x) = s \sum_{n=0}^{\infty} \frac{x^{n}}{n !}.
$$

Describe the intervals on which $f$ does and does not converge uniformly.

## Fall 2014 # 1
Let $\theset{f_n}$ be a sequence of continuous functions such that $\sum f_n$ converges uniformly.

Prove that $\sum f_n$ is also continuous.

## Spring 2017 # 4
Let $f(x, y)$ on $[-1, 1]^2$ be defined by 
$$
f(x, y) = \begin{cases}
\frac{x y}{\left(x^{2}+y^{2}\right)^{2}} & (x, y) \neq (0, 0) \\
0 & (x, y) = (0, 0)
\end{cases}
$$
Determine if $f$ is integrable.

## Spring 2015 # 1
Let $(X, d)$ and $(Y, \rho)$ be metric spaces, $f: X\to Y$, and $x_0 \in X$.

Prove that the following statements are equivalent:

1. For every $\varepsilon > 0 \quad \exists \delta > 0$ such that $\rho( f(x), f(x_0)  ) < \varepsilon$ whenever $d(x, x_0) < \delta$.
2. The sequence $\theset{f(x_n)}_{n=1}^\infty \to f(x_0)$ for every sequence $\theset{x_n} \to x_0$ in $X$.

## Fall 2014 # 2
Let $I$ be an index set and $\alpha: I \to (0, \infty)$.

1. Show that
$$
\sum_{i \in I} a(i):=\sup _{\substack{ J \subset I \\ J \text { finite }}} \sum_{i \in J} a(i)<\infty \implies I \text{ is countable.}
$$

2. Suppose $I = \QQ$ and $\sum_{q \in \mathbb{Q}} a(q)<\infty$.
  Define
  $$
  f(x):=\sum_{\substack{q \in \mathbb{Q}\\ q \leq x}} a(q).
  $$
  Show that $f$ is continuous at $x \iff x\not\in \QQ$.


## Spring 2014 # 2
Let $\theset{a_n}$ be a sequence of real numbers such that
$$
\theset{b_n} \in \ell^2(\NN) \implies \sum a_n b_n < \infty.
$$
Show that $\sum a_n^2 < \infty$.

> Note: Assume $a_n, b_n$ are all non-negative.



# General Analysis

## Spring 2020 # 1

Prove that if $f: [0, 1] \to \RR$ is continuous then
\[
\lim_{k\to\infty} \int_0^1 kx^{k-1} f(x) \,dx = f(1)
.\]

:::{.solution}

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



:::



## Fall 2019 # 1. 
Let $\{a_n\}_{n=1}^\infty$ be a sequence of real numbers.

a. Prove that if $\displaystyle\lim_{n→∞} a_n = 0$, then 
\[
\lim _{n \rightarrow \infty} \frac{a_{1}+\cdots+a_{n}}{n}=0
\]

b. Prove that if $\displaystyle\sum_{n=1}^{\infty} \frac{a_{n}}{n}$ converges, then 
\[
\lim _{n \rightarrow \infty} \frac{a_{1}+\cdots+a_{n}}{n}=0
\]

:::{.solution}

> Cesaro mean/summation. Break series apart into pieces that can be handled separately.

### a

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

### b

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

:::



## Fall 2018 # 4
Let $f\in L^1([0, 1])$.
Prove that
$$
\lim_{n \to \infty} \int_{0}^{1} f(x) \abs{\sin n x} ~d x= \frac{2}{\pi} \int_{0}^{1} f(x) ~d x
$$

> Hint: Begin with the case that $f$ is the characteristic function of an interval.

## Fall 2017 # 4
Let
\[
f_{n}(x) = n x(1-x)^{n}, \quad n \in \NN.
\]

1. Show that $f_n \to 0$ pointwise but not uniformly on $[0, 1]$.
    
  > Hint: Consider the maximum of $f_n$.

2. 
\[
\lim _{n \to \infty} \int _{0}^{1} n(1-x)^{n} \sin x \, dx = 0
\]

## Spring 2017 # 3

Let
\[
f_{n}(x) = a e^{-n a x} - b e^{-n b x} \quad \text{ where } 0 < a < b.
\]

Show that 

a. $\sum_{n=1}^{\infty} \left|f_{n}\right|$ is not in $L^{1}([0, \infty), m)$

  > Hint: $f_n(x)$ has a root $x_n$.

b. 
\[
\sum_{n=1}^{\infty} f_{n} \text { is in } L^{1}([0, \infty), m) 
\qtext{and}
\int _{0}^{\infty} \sum _{n=1}^{\infty} f_{n}(x) \,dm = \ln \frac{b}{a}
\]

## Fall 2016 # 1

Define
\[
f(x) = \sum_{n=1}^{\infty} \frac{1}{n^{x}}.
\] 

Show that $f$ converges to a differentiable function on $(1, \infty)$ and that
\[
f'(x)  =\sum_{n=1}^{\infty}\left(\frac{1}{n^{x}}\right)^{\prime}.
\]

> Hint:
\[
\left(\frac{1}{n^{x}}\right)' = -\frac{1}{n^{x}} \ln n
\]

## Fall 2016 # 5

Let $\phi\in L^\infty(\RR)$. Show that the following limit exists and satisfies the equality
\[
\lim _{n \to \infty} \left(\int _{\mathbb{R}} \frac{|\phi(x)|^{n}}{1+x^{2}} \, dx \right) ^ {\frac{1}{n}} 
= \norm{\phi}_\infty.
\]

## Fall 2016 # 6

Let $f, g \in L^2(\RR)$. Show that
\[
\lim _{n \to \infty} \int _{\RR} f(x) g(x+n) \,dx = 0
\]

## Spring 2016 # 1
For $n\in \NN$, define
\[]
e_{n} = \left (1+ {1\over n} \right)^{n} 
\qtext{and}
E_{n} = \left( 1+ {1\over n} \right)^{n+1}
\]

Show that $e_n < E_n$, and prove Bernoulli's inequality:
\[
(1+x)^{n} \geq 1+n x \text { for }-1<x<\infty \text { and } n \in \mathbb{N}
\]

Use this to show the following:

1. The sequence $e_n$ is increasing.
2. The sequence $E_n$ is decreasing.
3. $2 < e_n < E_n < 4$.
4. $\lim _{n \to \infty} e_{n} = \lim _{n \to \infty} E_{n}$.

## Fall 2015 # 1
Define
$$
f(x)=c_{0}+c_{1} x^{1}+c_{2} x^{2}+\ldots+c_{n} x^{n} \text { with } n \text { even and } c_{n}>0.
$$

Show that there is a number $x_m$ such that $f(x_m) \leq f(x)$ for all $x\in \RR$.


