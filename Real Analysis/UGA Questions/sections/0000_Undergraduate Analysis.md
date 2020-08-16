# Undergraduate Analysis: Uniform Convergence

## Fall 2018 # 1 $\done$
Let $f(x) = \frac 1 x$.
Show that $f$ is uniformly continuous on $(1, \infty)$ but not on $(0,\infty)$.


:::{.solution}
\hfill
:::{.concept}
\hfill
- Uniform continuity:
\[  
\forall \varepsilon>0, \exists \delta(\eps)>0 \qtext{such that} \abs{x-y}<\delta \implies \abs{f(x) - f(y)} < \varepsilon
.\]
- Negating uniform continuity:
  $\exists \eps > 0$ such that $\forall \delta(\eps)$ there exist $x, y$ such that $\abs{x-y} < \delta$ *and* $\abs{f(x) - f(y)} > \eps$.
:::

**Claim**:
$f(x) = \frac 1 x$ is uniformly continuous on $(c, \infty)$ for any $c > 0$.

- Note that
$$
\abs{x}, \abs y > c > 0 \implies \abs{xy} = \abs{x}\abs{y} > c^2 \implies \frac{1}{\abs{xy}} < \frac 1 {c^{2}}
.$$

- Letting $\varepsilon$ be arbitrary, choose $\delta < \varepsilon c^2$.
  - Note that $\delta$ does not depend on $x, y$.

- Then
\[
\abs{f(x) - f(y)}
&= \abs{\frac 1 x - \frac 1 y} \\
&= \frac{\abs{x-y}}{xy} \\
&\leq \frac{\delta}{xy} \\
&< \frac{\delta}{c^2} \\
&< \varepsilon
,\]
  which shows uniform continuity.

**Claim**: $f$ is *not* uniformly continuous when $c=0$.

- Toward a contradiction, let $\varepsilon < 1$.
- Let $x_n = \frac 1 n$ for $n\geq 1$.
- Choose $n$ large enough such that $\abs{x_n - x_{n+1}} = \frac 1 n - \frac 1 {n+1} < \delta$.
  - Why this can be done: by the archimedean property of $\RR$, choose $n$ such that ${1\over n} < \eps$.
  - Then
  \[
  {1 \over n} - {1\over n+1} = {1 \over n(n+1)} \leq {1\over n} < \eps \quad\text{since }n+1 > 1
  .\]
- Note $f(x_n) = n$ and thus 
\[
\abs{f(x_{n+1}) - f(x_{n})} = (n+1) - n = 1 > \varepsilon
,\]
  a contradiction.
:::


## Fall 2017 # 1 $\done$
Let 
\[
f(x) = \sum _{n=0}^{\infty} \frac{x^{n}}{n !}.
\]

Describe the intervals on which $f$ does and does not converge uniformly.

:::{.solution}
\hfill
:::{.concept}
\hfill
- $f_N\to f$ uniformly $\iff$ $\norm{f_N - f}_\infty \to 0$.
- $\sum_{n=0}^\infty c_n x^n \definedas \lim_{N\to \infty} \sum_{n=0}^N c_n x^n$
  - I.e. an infinite sum is defined as the pointwise limit of its partial sums.
- If $\sum_{n=0}^\infty g_n(x)$ converges uniformly on a set $A$, then $\sup_{x\in A} \abs{f_n(x)} \to 0$.
:::

- Set $f_N(x) = \sum_{n=1}^N {x^n \over n!}$.
  - Then by definition, $f_N(x) \to f(x)$ pointwise on $\RR$.

- For any compact interval $[-M, M]$, we have
\[
\norm{f_N(x) - f(x)}_\infty
&= \sup_{-M \leq x \leq M} ~\abs{\sum_{n=N+1}^\infty {x^n \over {n!}} } \\
&\leq \sup_{-M\leq x \leq M} ~\sum_{n=N+1}^\infty \abs{ {x^n \over {n!}} } \\
&\leq \sum_{n=N+1}^\infty {M^n \over n!} \\
&\leq \sum_{n=0}^\infty {M^n \over  {n!} } \quad\text{since all additional terms are positive} \\
&= e^M \\
&<\infty
,\]
  so $f_N \to f$ uniformly on $[-M, M]$ by the M-test.

  > Here we've used that $e^x$ is equal to its power series expansion.

- Thus $f$ converges on any bounded interval, since any bounded interval is contained in some larger compact interval.

**Claim**: 
$f$ does not converge on $\RR$.

- If $\sum_{n=0}^\infty g_n(x)$ converges uniformly on a set $A$, then $\sup_{x\in A} \abs{f_n(x)} \to 0$.
- But taking $A = \RR$ and $g_n(x) = {x^n \over n!}$, we have 
\[  
\sup_{x\in \RR} \abs{g_n(x)} = \sup_{x\in \RR} {x^n \over n!} = \infty
.\]
:::


## Fall 2014 # 1 $\done$
Let $\theset{f_n}$ be a sequence of continuous functions such that $\sum f_n$ converges uniformly.

Prove that $\sum f_n$ is also continuous.

:::{.solution}
\hfill
**Claim:**
If $F_N\to F$ uniformly with each $F_N$ continuous, then $F$ is continuous.

- Follows from an $\varepsilon/3$ argument: 
  \[  
  \abs{F(x) - F(y} \leq 
  \abs{F(x) - F_N(x)} + \abs{F_N(x) - F_N(y)} + \abs{F_N(y) - F(y)} 
  \leq \eps \to 0
  .\]

  - The first and last $\eps/3$ come from uniform convergence of $F_N\to F$.
  - The middle $\eps/3$ comes from continuity of each $F_N$.

- Now setting $F_N\definedas \sum_{n=1}^N f_n$ yields a finite sum of continuous functions, which is continuous.
- Each $F_N$ is continuous and $F_N\to F$ uniformly, so applying the claim yields the desired result.
:::


## Spring 2017 # 4 $\work$
Let $f(x, y)$ on $[-1, 1]^2$ be defined by 
$$
f(x, y) = \begin{cases}
\frac{x y}{\left(x^{2}+y^{2}\right)^{2}} & (x, y) \neq (0, 0) \\
0 & (x, y) = (0, 0)
\end{cases}
$$
Determine if $f$ is integrable.

\todo[inline]{Redo, may just be wrong.}
\todo[inline]{Add concepts.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- ?
:::

Switching to polar coordinates and integrating over the unit disc $\DD \subseteq I^2$, we have
\[
\int_{I^2} f 
&\geq \int_   
&\geq \int_0^{2\pi} \int_0^1 \frac{\cos(\theta)\sin(\theta)}{r^4} ~r~dr~d\theta = \infty
,\]

so $f$ is not integrable.
:::

## Spring 2015 # 1 $\done$
Let $(X, d)$ and $(Y, \rho)$ be metric spaces, $f: X\to Y$, and $x_0 \in X$.

Prove that the following statements are equivalent:

1. For every $\varepsilon > 0 \quad \exists \delta > 0$ such that $\rho( f(x), f(x_0)  ) < \varepsilon$ whenever $d(x, x_0) < \delta$.
2. The sequence $\theset{f(x_n)}_{n=1}^\infty \to f(x_0)$ for every sequence $\theset{x_n} \to x_0$ in $X$.

## Fall 2014 # 2  $\work$
Let $I$ be an index set and $\alpha: I \to (0, \infty)$.

1. Show that
\[
\sum_{i \in I} a(i):=\sup _{\substack{ J \subset I \\ J \text { finite }}} \sum_{i \in J} a(i)<\infty \implies I \text{ is countable.}
\]

2. Suppose $I = \QQ$ and $\sum_{q \in \mathbb{Q}} a(q)<\infty$.
  Define
  $$
  f(x):=\sum_{\substack{q \in \mathbb{Q}\\ q \leq x}} a(q).
  $$
  Show that $f$ is continuous at $x \iff x\not\in \QQ$.


## Spring 2014 # 2  $\work$

Let $\theset{a_n}$ be a sequence of real numbers such that
$$
\theset{b_n} \in \ell^2(\NN) \implies \sum a_n b_n < \infty.
$$
Show that $\sum a_n^2 < \infty$.

> Note: Assume $a_n, b_n$ are all non-negative.



# General Analysis

## Spring 2020 # 1 $\done$

Prove that if $f: [0, 1] \to \RR$ is continuous then
\[
\lim_{k\to\infty} \int_0^1 kx^{k-1} f(x) \,dx = f(1)
.\]

:::{.solution}
\hfill
:::{.concept}
\hfill
- DCT
- Weierstrass Approximation Theorem
:::

- Suppose $p$ is a polynomial, then
\[
\lim_{k\to\infty} \int_0^1 kx^{k-1} p(x) \, dx
&= \lim_{k\to\infty} \int_0^1 \qty{ \dd{}{x}x^k } p(x) \, dx \\
&= \lim_{k\to\infty} \left[ x^k p(x) \evalfrom_0^1 - \int_0^1 x^k \qty{\dd{}{x} p(x) } \, dx \right] \quad\text{integrating by parts}\\
&= p(1) - \lim_{k\to\infty} \int_0^1 x^k \qty{\dd{}{x} p(x) } \, dx
,\]

- Thus it suffices to show that
\[
\lim_{k\to\infty} \int_0^1 x^k \qty{\dd{}{x} p(x) } \, dx = 0
.\]

- Integrating by parts a second time yields
\[
\lim_{k\to\infty} 
\int_0^1 x^k \qty{\dd{}{x} p(x) } \, dx
&= \lim_{k\to\infty} 
{x^{k+1} \over k+1} p'(x) \evalfrom_0^1 - \int_0^1 {x^{k+1} \over k+1} \qty{ \dd{^2}{x^2}p(x)} \, dx \\
&= - \lim_{k\to\infty} \int_0^1 {x^{k+1} \over k+1} \qty{ \dd{^2}{x^2}p(x)} \, dx \\
&= - \int_0^1 \lim_{k\to\infty}  {x^{k+1} \over k+1} \qty{ \dd{^2}{x^2}p(x)} \, dx \quad\text{by DCT} \\
&= - \int_0^1 0 \qty{ \dd{^2}{x^2}p(x)} \, dx \\
&= 0
.\]

  - The DCT can be applied here because $f''$ is continuous and $[0, 1]$ is compact, so $f''$ is bounded on $[0, 1]$ by a constant $M$ and 
  $$\int_0^1 \abs{x^k f''(x)} \leq \int_0^1 1\cdot M = M < \infty.$$

- Now use the Weierstrass approximation theorem: 
  - If $f: [a, b] \to \RR$ is continuous, then for every $\eps>0$ there exists a polynomial $p_\eps(x)$ such that $\norm{f - p_\eps}_\infty < \eps$.

- Thus 
\[
\abs{ \int_0^1 kx^{k-1} p_\eps(x)\,dx - \int_0^1 kx^{k-1}f(x)\,dx  } 
&= \abs{ \int_0^1 kx^{k-1} \qty{p_\eps(x) - f(x)} \,dx  } \\
&\leq \abs{ \int_0^1 kx^{k-1} \norm{p_\eps-f}_\infty \,dx  } \\
&= \norm{p_\eps-f}_\infty \cdot \abs{ \int_0^1 kx^{k-1} \,dx  } \\
&= \norm{p_\eps-f}_\infty \cdot x^k \evalfrom_0^1 \\
&= \norm{p_\eps-f}_\infty \converges{\eps\to 0}\to 0
\]

  and the integrals are equal. 

- By the first argument, $$\int_0^1 kx^{k-1} p_\eps(x) \,dx = p_\eps(1) \text{ for each } \eps$$ 
- Since uniform convergence implies pointwise convergence, $p_\eps(1) \converges{\eps\to 0}\to f(1)$.

:::

## Fall 2019 # 1 $\done$
Let $\{a_n\}_{n=1}^\infty$ be a sequence of real numbers.

### a
Prove that if $\displaystyle\lim_{n→∞} a_n = 0$, then 
\[
\lim _{n \rightarrow \infty} \frac{a_{1}+\cdots+a_{n}}{n}=0
\]

### b
Prove that if $\displaystyle\sum_{n=1}^{\infty} \frac{a_{n}}{n}$ converges, then 
\[
\lim _{n \rightarrow \infty} \frac{a_{1}+\cdots+a_{n}}{n}=0
\]

:::{.solution}
\hfill
:::{.concept}
\hfill
- Cesaro mean/summation. 
- Break series apart into pieces that can be handled separately.
:::

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
\[
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
.\]
  
> Note: $M$ is fixed, so the last sum is some constant $c$, and $c/N \to 0$ as $N\to\infty$ for any constant.
> To be more careful, choose $M$ first to get $\eps/2$ for the tail, then choose $N(M)>M$ for the remaining truncated part of the sum. 

### b

- Define
\[
\Gamma_n \definedas \sum_{k=n}^\infty \frac{a_k}{k}
.\]

- $\Gamma_1 = \sum_{k=1}^n \frac{ a_k } k$ is the original series and each $\Gamma_n$ is a tail of $\Gamma_1$, so by assumption $\Gamma_n \converges{n\to\infty}\to 0$.

- Compute
\[
\frac 1 n \sum_{k=1}^n a_k 
&= \frac 1 n (\Gamma_1 + \Gamma_2 + \cdots + \Gamma_{n} \mathbf{- \Gamma_{n+1}}) \\
.\]

- This comes from consider the following summation:
\begin{tikzcd}[row sep=small, column sep=small]
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
\[
\frac 1 n \sum_{k=1}^n a_k 
&= \frac 1 n (\Gamma_1 + \Gamma_2 + \cdots + \Gamma_{n} \mathbf{- \Gamma_{n+1}}) \\
&= \qty{ {1\over n } \sum_{k=0}^n \Gamma_k } - \qty{{1\over n}\Gamma_{n+1} } \\
&\converges{n\to\infty}\to 0
.\]
:::

## Fall 2018 # 4 $\done$
Let $f\in L^1([0, 1])$.
Prove that
$$
\lim_{n \to \infty} \int_{0}^{1} f(x) \abs{\sin n x} ~d x= \frac{2}{\pi} \int_{0}^{1} f(x) ~d x
$$
> Hint: Begin with the case that $f$ is the characteristic function of an interval.

\todo[inline]{Add concepts.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- ?
:::

Case of characteristic function

- First suppose $f(x) = \chi_{[0, 1]}(x)$.
- Note that $\sin(nx)$ has a period of $2\pi/n$, and thus $\floor{n\over 2\pi}$ full periods in $[0, 1]$.
- Taking the absolute value yields a new function with half the period, so a period of $\pi/n$ and $\floor{\pi / n}$ full periods in $[0, 1]$.
- We can compute the integral over one full period (which is independent of *which* period is chosen), and since $\sin(x)$ is positive and agrees with $\abs{\sin(nx)}$ on the first period, we have
\[
\int_{\text{One Period}} \abs{\sin(nx)} \, dx 
&= \int_0^{\pi/n} \sin(nx)\,dx \\
&= {1\over n} \int_0^\pi \sin(u) \,du \quad u = nx \\
&= {1\over n} -\cos(u)\mid_0^\pi \\
&= {2 \over n}
.\]


- Then break the integral up into integrals over periods $P_1, P_2, \cdots, P_N$ where $N \definedas \floor{n/\pi}$:
\[
\int_0^1 \abs{\sin(nx)} \, dx 
&= \qty{ \sum_{j=1}^{N} \int_{P_j} \abs{\sin(nx)} \, dx } +  \int_{N\floor{\pi/n}}^1 \abs{\sin(nx)}\,dx \\
&= \qty{ \sum_{j=1}^{N} {2\over n} } +  \int_{N\floor{\pi/n}}^1 \abs{\sin(nx)}\,dx \\
&= N \qty{2\over n} +  \int_{N\floor{\pi/n}}^1 \abs{\sin(nx)}\,dx \\
&\definedas \floor{n \over \pi} {2\over n} +  \int_{N\floor{\pi/n}}^1 \abs{\sin(nx)}\,dx \\
&= {2\over \pi} + \int_{N\floor{\pi/n}}^1 \abs{\sin(nx)}\,dx \\
&\definedas {2\over \pi} + R(n) 
\]
  so it suffices to show that $R(n) \converges{n\to\infty}\to 0$. 
  \todo[inline]{Need to justify removing floor function and cancellation.}

- Showing this: ???????????? \todo[inline]{No clue how to show this.}

General case

\todo[inline]{Not sure. Approximate $f$ by simple functions...?}
:::

## Fall 2017 # 4 $\done$
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

\todo[inline]{Add concepts.}
\todo[inline]{Walk through.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- ?
:::


### a

Let $G(x) = \sum_{n=1}^\infty nx(1-x)^n$. 
Applying the ratio test, we have
\[
\abs{\frac{(n+1)x(1-x)^{n+1}}{nx(1-x)^n}} = \frac{n+1}{n} \abs{1-x} \converges{n\to\infty}\to \abs{1-x} < 1 \iff 0 \leq x \leq 2
,\]

and in particular, this series converges on $[0, 2]$. 
Thus its terms go to zero, and $nx(1-x)^n \to 0$ on $[0, 1] \subset [0, 2]$.

To see that the convergence is not uniform, let $x_n = \frac 1 n$ and $\varepsilon > \frac 1 e$, then
\[
\sup_{x\in [0, 1]}\abs{nx(1-x)^n - 0} 
\geq \abs{nx_n (1-x_n)^n} 
= \abs{\left( 1 - \frac 1 n\right)^n} 
\converges{n\to\infty}\to e\inv
> \varepsilon
.\]


### b

> Note: could use the first part with $\sin(x) \leq x$, but then integral ends up more complicated.

Noting that $\sin(x) \leq 1$, we have
We have
\[
\abs{\int_0^1  n(1-x)^{n} \sin(x)} 
&\leq \int_0^1  \abs{n(1-x)^n \sin(x)} \\
&\leq \int_0^1  \abs{n (1-x)^n}  \\
&= n\int_0^1 (1-x)^n \\
&= -\frac{n(1-x)^{n+1}}{n+1} \\
&\converges{n\to\infty}\longrightarrow 0
.\]
:::

## Spring 2017 # 3 $\done$

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
\todo[inline]{Not complete.}
\todo[inline]{Add concepts.}
\todo[inline]{Walk through.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- ?
:::

### a

Letting $x_n \definedas \frac 1 n$, we have

\[
\sum_{k=1}^\infty \abs{f_k(x)} \geq \abs{f_n(x_n)} 
=\abs{ae^{-ax} - be^{-bx}} \definedas M
.\]

In particular, $\sup_{x} \abs{f_n(x)} \not\to 0$, so the terms do not go to zero and the sum can not converge.

### b

?
:::

## Fall 2016 # 1 $\done$

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

\todo[inline]{Add concepts.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- ?
:::

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
\todo[inline]{?}
:::

## Fall 2016 # 5 $\done$

Let $\phi\in L^\infty(\RR)$. Show that the following limit exists and satisfies the equality
\[
\lim _{n \to \infty} \left(\int _{\mathbb{R}} \frac{|\phi(x)|^{n}}{1+x^{2}} \, dx \right) ^ {\frac{1}{n}} 
= \norm{\phi}_\infty.
\]
\todo[inline]{Walk through.}
\todo[inline]{Add concepts.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- ?
:::


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

- We will show that $R\leq L + \eps$ for every $\eps>0$.
- Set 
\[  
S_\eps \definedas \theset{x\in \RR^n\suchthat \abs{\phi(x)} \geq \norm{\phi}_\infty - \eps}
.\]
- Then we have
\[  
\int_\RR {\abs{\phi(x)}^n \over 1 +x^2}\,dx
&\geq \int_{S_\eps} {\abs{\phi(x)}^n \over 1 +x^2}\,dx \quad S_\eps \subset \RR \\
&\geq \int_{S_\eps} { \qty{\norm{\phi}_\infty - \eps}^n \over 1 +x^2}\,dx  \qquad\text{by definition of }S_\eps \\
&= \qty{\norm{\phi}_\infty - \eps}^n \int_{S_\eps} { 1 \over 1 +x^2}\,dx \\
&= \qty{\norm{\phi}_\infty - \eps}^n C_\eps \qquad\text{where $C_\eps$ is some constant} \\ \\
\implies 
\qty{ \int_\RR {\abs{\phi(x)}^n \over 1 +x^2}\,dx }^{1\over n} 
&\geq \qty{\norm{\phi}_\infty - \eps} C_\eps^{1 \over n} \\
&\converges{n\to\infty}\to
\qty{\norm{\phi}_\infty - \eps} \cdot 1 \\
&\converges{\eps\to 0}\to \norm{\phi}_\infty
,\]
  where we've again used the fact that $c^{1\over n} \to 1$ for any constant.
:::

## Fall 2016 # 6 $\done$

Let $f, g \in L^2(\RR)$. Show that
\[
\lim _{n \to \infty} \int _{\RR} f(x) g(x+n) \,dx = 0
\]
\todo[inline]{Add concepts.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- ?
:::

- Use the fact that $L^p$ has small tails: if $h\in L^2(\RR)$, then for any $\eps > 0$, 
\[  
\forall \eps,\, \exists N\in \NN \qst \int_{\abs{x} \geq {N}} \abs{h(x)}^2 \,dx < \eps
.\]
\todo[inline]{How to prove small tails in $L^p$?}

- So choose $n$ large enough so the tails of both $f$ and $g$ are smaller than $\eps$.

- Apply Cauchy-Schwarz:
\[  
\abs{\int_\RR f(x) g(x+n) \,dx} 
&\leq \int_\RR \abs{f(x) g(x+n)}\,dx \\
&\leq \int_\RR
.\]
:::

## Spring 2016 # 1  $\work$

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

## Fall 2015 # 1  $\work$

Define
\[
f(x)=c_{0}+c_{1} x^{1}+c_{2} x^{2}+\ldots+c_{n} x^{n} \text { with } n \text { even and } c_{n}>0.
\]

Show that there is a number $x_m$ such that $f(x_m) \leq f(x)$ for all $x\in \RR$.
