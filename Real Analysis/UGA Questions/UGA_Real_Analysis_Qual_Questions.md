
---
title: UGA Real Analysis Qualifying Exam Questions and Solutions
hidesolutions: false
todos: true
---

**Preface**

I'd like to extend my gratitude to Peter Woolfitt for supplying many solutions and checking many proofs of the rest in problem sessions.


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

\todo[inline]{Walk through.}
\todo[inline]{Add concepts.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- $f_N\to f$ uniformly $\iff$ $\norm{f_N - f} \to 0$.
- $\sum_{n=0}^\infty c_n x^n \definedas \lim_{N\to \infty} \sum_{n=0}^N c_n x^n$, i.e. an infinite sum is defined pointwise as the limit of its partial sums.
:::

- Set $f_N(x) = \sum_{n=1}^N {x^n \over n!}$.
  - Then by definition, $f_N(x) \to f(x)$ pointwise on $\RR$.

- For any compact interval $[-M, M]$, we have
\[
\norm{f_N(x) - f(x)}_\infty
&= \sup_{-M\leq x \leq M} ~\abs{\sum_{n=N+1}^\infty {x^n \over {n!}} } \\
&\leq \sup_{-M\leq x \leq M} ~\sum_{n=N+1}^\infty \abs{ {x^n \over {n!}} } \\
&\leq \sum_{n=N+1}^\infty {M^n \over n!} \\
&\leq \sum_{n=0}^\infty {M^n \over  {n!} } \\
&= e^M \\
&<\infty
,\]
  so $f_N \to f$ uniformly on $[-M, M]$ by the M-test.

- Thus $f$ converges on any bounded interval.

It does not converge on $\RR$, since $x^N$ is unbounded.
:::


## Fall 2014 # 1 $\work$
Let $\theset{f_n}$ be a sequence of continuous functions such that $\sum f_n$ converges uniformly.

Prove that $\sum f_n$ is also continuous.

## Spring 2017 # 4 $\done$
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

Switching to polar coordinates and integrating over a half-circle contained in $I^2$, we have
\[
\int_{I^2} f \geq \int_0^\pi \int_0^1 \frac{\cos(\theta)\sin(\theta)}{r^2} ~dr~d\theta = \infty
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
$$
\sum_{i \in I} a(i):=\sup _{\substack{ J \subset I \\ J \text { finite }}} \sum_{i \in J} a(i)<\infty \implies I \text{ is countable.}
$$

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

# Measure Theory: Sets

## Spring 2020 # 2 $\done$

Let $m_*$ denote the Lebesgue outer measure on \( \RR \).

### a. 
Prove that for every $E\subseteq \RR$ there exists a Borel set $B$ containing $E$ such that
\[
m_*(B) = m_*(E)
.\]

### b. 
Prove that if $E\subseteq \RR$ has the property that
\[
m_*(A) = m_*(A\intersect E) + m_*(A\intersect E^c)
\]
for every set $A\subseteq \RR$, then there exists a Borel set $B\subseteq \RR$ such that $E = B\setminus N$ with $m_*(N) = 0$.

Be sure to address the case when $m_*(E) = \infty$.

:::{.solution}
\hfill
:::{.concept}
\hfill
- Definition of outer measure: 
  \[ 
  m_*(E) = \inf_{\theset{Q_j} \covers E} \sum \abs {Q_j}
  \] 
  where $\theset{Q_j}$ is a countable collection of closed cubes.
- Break $\RR$ into $\disjoint_{n\in \ZZ} [n, n+1)$, each with finite measure.
- Theorem: $m_*(Q) = \abs{Q}$ for $Q$ a closed cube (i.e. the outer measure equals the volume).
:::


:::{.proof}
\hfill
- $m_*(Q) \leq \abs{Q}$:
- Since $Q\subseteq Q$, $Q\covers Q$ and $m_*(Q) \leq \abs{Q}$ since $m_*$ is an infimum over such coverings.
- $\abs{Q} \leq m_*(Q)$:
- Fix $\eps > 0$.
- Let $\theset{Q_i}_{i=1}^\infty \covers Q$ be arbitrary, it suffices to show that 
    $$\abs{Q} \leq \qty{\sum_{i=1}^\infty \abs{Q_i}} + \eps.$$
-  Pick open cubes $S_i$ such that $Q_i\subseteq S_i$ and $\abs{Q_i} \leq \abs{S_i} \leq (1+\eps)\abs{Q_i}$.
- Then $\theset{S_i} \covers Q$, so by compactness of $Q$ pick a finite subcover with $N$ elements.

- Note 
\[
Q \subseteq \union_{i=1}^N S_i \implies \abs{Q} \leq \sum_{i=1}^N \abs{S_i} \leq \sum_{i=1}^N (1+\eps) \abs{Q_j} \leq (1+\eps)\sum_{i=1}^\infty \abs{Q_i } 
.\]
- Taking an infimum over coverings on the RHS preserves the inequality, so 
  $$\abs{Q} \leq (1+\eps) m_*(Q)$$
- Take $\eps\to 0$ to obtain final inequality.
:::

### a

- If $m_*(E) = \infty$, then take $B = \RR^n$ since $m(\RR^n) = \infty$.
- Suppose $N \definedas m_*(E) < \infty$.

- Since $m_*(E)$ is an infimum, by definition, for every $\eps> 0$ there exists a covering by closed cubes $\theset{Q_i(\eps)}_{i=1}^\infty \covers E$ depending on $\eps$ such that 
$$
\sum_{i=1}^\infty \abs{Q_i(\eps)} < N + \eps
.$$

- For each fixed $n$, set $\eps_n = {1\over n}$ to produce such a covering $\theset{Q_i(\eps_n)}_{i=1}^\infty$ and set $B_n \definedas \union_{i=1}^\infty Q_i(\eps_n)$.

- The outer measure of cubes is *equal* to the sum of their volumes, so 
\[
m_*(B_n) = \sum_{i=1}^\infty \abs{Q_i(\eps_n)} < N + \eps_n = N + {1\over n}
.\]

- Now set $B \definedas \intersect_{n=1}^\infty B_n$.

  - Since $E\subseteq B_n$ for every $n$, $E\subseteq B$
  - Since $B$ is a countable intersection of countable unions of closed sets, $B$ is Borel.
  - Since $B_n \subseteq B$ for every $n$, we can apply subadditivity to obtain the inequality
  \[
  E \subseteq B \subseteq B_n \implies
  N \leq m_*(B) \leq m_*(B_n) < N + {1\over n} \qtext{for all} n\in \ZZ^{\geq 1}
  .\]

- This forces $m_*(E) = m_*(B)$.


### b

Suppose $m_*(E) < \infty$.

- By (a), find a Borel set $B\supseteq E$ such that $m_*(B) = m_*(E)$
- Note that $E\subseteq B \implies B\intersect E = E$ and $B\intersect E^c = B\setminus E$.
- By assumption, 
\[
m_*(B) &= m_*(B\intersect E) + m_*(B\intersect E^c) \\
m_*(E) &= m_*(E) + m_*(B\setminus E) \\ 
m_*(E) - m_*(E) &= m_*(B\setminus E) \qquad\qquad\text{since } m_*(E) < \infty \\ 
\implies m_*(B\setminus E) &= 0
.\]
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
\[
N = B\setminus E = \qty{ \union_R B_R } \setminus \qty{\union_R E_R } \subseteq \union_R \qty{B_R\setminus E_R} = \union_R N_R \definedas N'
\]
where $m_*(N') = 0$ since $N'$ is null, and thus subadditivity forces $m_*(N) = 0$.
:::

## Fall 2019 # 3. $\done$
Let $(X, \mathcal B, µ)$ be a measure space with $µ(X) = 1$ and $\{B_n\}_{n=1}^\infty$ be a sequence of $\mathcal B$-measurable subsets of $X$, and
$$
B \definedas \theset{x\in X \suchthat x\in B_n \text{ for infinitely many } n}.
$$

a. Argue that $B$ is also a $\mathcal{B} \dash$measurable subset of $X$.

b. Prove that if $\sum_{n=1}^\infty \mu(B_n) < \infty$ then $\mu(B)= 0$.

c. Prove that if  $\sum_{n=1}^\infty \mu(B_n) = \infty$ **and** the sequence of set complements $\theset{B_n^c}_{n=1}^\infty$ satisfies
$$
\mu\left(\bigcap_{n=k}^{K} B_{n}^{c}\right)=\prod_{n=k}^{K}\left(1-\mu\left(B_{n}\right)\right)
$$
for all positive integers $k$ and $K$ with $k < K$, then $µ(B) = 1$.

> Hint: Use the fact that $1 - x ≤ e^{-x}$ for all $x$.

:::{.solution}
\hfill
:::{.concept}
\hfill
- Borel-Cantelli: for a sequence of sets $X_n$, 
\[
\limsup_n X_n &= \theset{x \suchthat x\in X_n \text{ for infinitely many $n$} } 
&= \intersect_{m\in \NN} \union_{n\geq m} X_n
\\
\liminf_n X_n &= \theset{x \suchthat x\in X_n \text{ for all but finitely many $n$} }
&= \union_{m\in \NN} \intersect_{n\geq m} X_n
.\]

- Properties of logs and exponentials:
\[
\prod_n e^{x_n} = e^{\Sigma_n x_n} \quad\text{and} \quad \sum_n \log(x_n) = \log\left(\prod_n x_n\right)
.\]

- Tails of convergent sums vanish.
-  Continuity of measure: $B_n \searrow B$ and $\mu(B_0)<\infty$ implies $\lim_n \mu(B_n) = \mu(B)$, and $B_n\nearrow B \implies \lim_n \mu(B_n) = \mu(B)$.

:::

### a

- The Borel $\sigma\dash$algebra is closed under countable unions/intersections/complements, 
- $B = \limsup_n B_n$ is an intersection of unions of measurable sets.

### b

- Tails of convergent sums go to zero, so $\sum_{n\geq M} \mu(B_n) \mapsvia{M\to\infty} 0$, 
- $B_M \definedas \intersect_{m = 1}^M \union_{n\geq m} B_n \searrow B$.

\[
\mu(B_M) 
&= \mu\left(\intersect_{m\in \NN} \union_{n\geq m} B_n\right) \\
&\leq \mu\left( \union_{n\geq m} B_n \right) \quad \text{for all } m\in \NN \text{ by countable subadditivity} \\ 
&\to 0
,\]

- The result follows by continuity of measure.

### c

- To show $\mu(B) = 1$, we'll show $\mu(B^c) = 0$.

- Let $B_k = \intersect_{m=1}^\infty \union_{n = m}^K B_n$. Then
\[
\mu(B_K^c) 
&= \mu \left(\union_{m=1}^\infty \intersect_{n=m}^K B_n^c\right) \\
&\leq \sum_{m=1}^\infty \mu\left( \intersect_{n=m}^K B_n^c \right) \quad\text{ by subadditivity} \\
&= \sum_{m=1}^\infty \prod_{n=m}^K \qty{1 - \mu(B_n)} \quad \text{by assumption} \\ 
&\leq \sum_{m=1}^\infty \prod_{n=m}^K e^{-\mu(B_n^c)} \quad\text{by hint} \\
&= \sum_{m=1}^\infty \exp{-\sum_{n=m}^K \mu(B_n^c)} \\
&\converges{K\to\infty}\to 0
\]
  since $\displaystyle\sum_{n=m}^K \mu(B_n^c) \converges{K\to\infty}\to \infty$ by assumption 

- We can apply continuity of measure since $B_K^c \mapsvia{K\to\infty} B^c$.

\todo[inline]{How to prove the hint..?}
:::

## Spring 2019 # 2 $\done$
Let $\mathcal B$ denote the set of all Borel subsets of $\RR$ and $\mu : \mathcal B → [0, \infty)$ denote a finite Borel measure on $\RR$.
  
### a 
Prove that if $\{F_k\}$ is a sequence of Borel sets for which $F_k \supseteq  F_{k+1}$ for all $k$, then
\[
\lim _{k \rightarrow \infty} \mu\left(F_{k}\right)=\mu\left(\bigcap_{k=1}^{\infty} F_{k}\right)
\]

### b 
Suppose $µ$ has the property that $µ(E) = 0$ for every $E \in \mathcal B$ with Lebesgue measure $m(E) = 0$.

Prove that for every $ε > 0$ there exists $δ > 0$ so that if $E \in \mathcal B$ with $m(E) < δ$, then $µ(E) < ε$.

\todo[inline]{Add concepts.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- ?
:::

### a

> See Folland p.26

- Lemma 1: $\mu(\disjoint_{k=1}^\infty E_k) = \lim_{N\to\infty} \sum_{k=1}^N \mu(E_k)$.

- Suppose $F_0 \supseteq F_1 \supseteq \cdots$.
- Let $A_k = F_k \setminus F_{k+1}$, since the $F_k$ are nested the $A_k$ are disjoint
- Set $A \definedas \disjoint_{k=1}^\infty A_k$ and $F \definedas \intersect_{k=1}^\infty F_k$.
- Note $X = X\setminus Y ~\disjoint~ X\intersect Y$ for any two sets (just write $X\setminus Y \definedas X\intersect  Y^c$)
- Note that $A$ contains anything that was removed from $F_0$ when passing from any $F_j$ to $F_{j+1}$, while $F$ contains everything that is never removed at any stage, and these are disjoint possibilities.
- Thus $F_0 = F \disjoint A$, so 
\[
\mu(F_0) 
&= \mu(F) + \mu(A) \\
&= \mu(F) + \mu(\disjoint_{k=1}^\infty A_k) \\
&= \mu(F) + \lim_{n\to\infty} \sum_{k=0}^n \mu(A_k) \quad \text{by countable additivity}\\
&= \mu(F) + \lim_{n\to\infty} \sum_{k=0}^n \mu(F_k) - \mu(F_{k+1}) \\
&= \mu(F) + \lim_{n\to\infty} \left( \mu(F_1) - \mu(F_n) \right) \quad\text{(Telescoping)} \\
&=\mu(F) + \mu(F_1) - \lim_{N\to\infty} \mu(F_n)
,\]

- Since $\mu$ is a finite measure, $\mu(F_1) < \infty$ and can be subtracted, yielding
\[
\mu(F_1) &= \mu(F) + \mu(F_1) - \lim_{n\to\infty} \mu(F_n) \\
\implies \mu(F) &= \lim_{n\to\infty} \mu(F_n) \\
\implies \mu\qty{\intersect_{k=1}^\infty F_k} &= \lim_{n\to\infty} \mu(F_n)
.\]

### b

- Toward a contradiction, negate the implication: suppose there exists an $\eps>0$ such that for all $\delta$, we have $m(E) < \delta$ but $\mu(E) > \eps$.
- The sequence $\theset{\delta_n \definedas {1\over 2^n}}_{n\in \NN}$ and produce sets $A_n\in \mcb$ such $m(A_n) < {1\over 2^n}$ but $\mu(A_n) > \varepsilon$.
- Define
\[
F_n &\definedas \union_{j\geq n} A_j \\
C_m &\definedas \intersect_{k=1}^m F_k \\
A &\definedas C_\infty \definedas \intersect_{k=1}^\infty F_k 
.\]

- Note that $F_1 \supseteq F_2 \supseteq \cdots$, since each increase in index unions fewer sets.
- By continuity for the Lebesgue measure, 
\[
m(A) 
= m \qty{\intersect_{k=1}^\infty F_k }
= \lim_{k\to \infty} m (F_k) 
= \lim_{k\to\infty} m\qty{\union_{j\geq k} A_j } 
\leq \lim_{k\to\infty} \sum_{j\geq k} m(A_j) 
= \lim_{k\to\infty} \sum_{j\geq k} {1\over 2^n} 
= 0
,\]
  which follows because this is the tail of a convergent sum

- Thus $m(A) = 0$ and by assumption, this implies $\mu(A) = 0$.

- However, by part (a),
\[
\mu(A) = \lim_n \mu\left( \union_{k=n}^\infty A_k \right)
\geq \lim_n \mu(A_n) = \lim_n \varepsilon = \varepsilon > 0
.\]
:::
\todo[inline]{All messed up!}

## Fall 2018 # 2 $\done$
Let $E\subset \RR$ be a Lebesgue measurable set.
Show that there is a Borel set $B \subset E$ such that $m(E\setminus B) = 0$.

\todo[inline]{Move this to review notes to clean things up.}

:::{.solution}
\hfill
:::{.concept}
\hfill
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
    \[
    m_*(G_n\setminus E) = m_*(G_1) - m_*(E) < 1 \iff m_*(G_1) < m_*(E) + {1\over n} < \infty
    .\]
    - Note $O_N \setminus E \searrow O \setminus E$ since $O_N\setminus E \definedas O_N \intersect E^c \supseteq O_{N+1} \intersect E^c$ for all $N$, and again $m_*(O_1 \setminus E) < \infty$.
    - So it's valid to apply continuity of measure from above:
\[
m_*(O\setminus E) 
&= \lim_{N\to\infty} m_*(O_N\setminus E) \\ 
&\leq \lim_{N\to \infty} m_*(G_N\setminus E) \\ 
&= \lim_{N\to\infty} {1\over N} = 0
,\]
      where the inequality uses subadditivity on $\intersect_{n=1}^N G_n \subseteq G_N$
  - Suppose $E$ is unbounded.
    - Write $E^k = E \intersect [k, k+1]^d \subset \RR^d$ as the intersection of $E$ with an annulus, and note that $E = \disjoint_{k\in \NN} E_k$.
    - Each $E_k$ is bounded, so apply the previous case to obtain $O_k \supseteq E_k$ with $m(O_k\setminus E_k) = 0$.
    - So write $O_k = E_k \disjoint N_k$ where $N_k \definedas O_k \setminus E_k$ is a null set.
    - Define $O = \union_{k\in \NN} O_k$, note that $E\subseteq O$.
    - Now note
\[
O\setminus E 
&= \qty{\disjoint_k O_k}\setminus \qty{\disjoint_K E_k} \\
&\subseteq \disjoint_k \qty{O_k \setminus E_k} \\
\implies m_*(O\setminus E) 
&\leq m_*\qty{\disjoint \qty{O_k \setminus E_k} } = 0
,\]
  since any countable union of null sets is again null.
  - So $O\supseteq E$ with $m(O\setminus E) = 0$.
- Theorem: since $E$ is measurable, $E^c$ is measurable
  - Proof: It suffices to write $E^c$ as the union of two measurable sets, $E^c = S \union (E^c - S)$, where $S$ is to be determined.
  - We'll produce an $S$ such that $m_*(E^c - S) = 0$ and use the fact that any subset of a null set is measurable.
  - Since $E$ is measurable, for every $\eps > 0$ there exists an open $\OO_\eps \supseteq E$ such that $m_*(\OO_\eps \setminus E) < \eps$.
  - Take the sequence $\theset{\eps_n \definedas {1\over n}}$ to produce a sequence of sets $\OO_n$.
  - Note that each $\OO_n^c$ is closed and 
  \[
  \OO_n \supseteq E \iff \OO_n^c \subseteq E^c
  .\]
  - Set $S \definedas \union_n \OO_n^c$, which is a union of closed sets, thus an $F_\sigma$ set, thus Borel, thus measurable.
  - Note that $S\subseteq E^c$ since each $\OO_n \subseteq E^c$.
  - Note that
  \[
  E^c\setminus S 
  &\definedas E^c \setminus \qty{\union_{n=1}^\infty \OO_n^c} \\
&\definedas E^c \intersect \qty{\union_{n=1}^\infty \OO_n^c}^c  \quad\text{definition of set minus} \\ 
  &= E^c \intersect \qty{\intersect_{n=1}^\infty \OO_n}^c  \quad \text{De Morgan's law}\\
  &= E^c \union \qty{\intersect_{n=1}^\infty \OO_n}  \\
  &\definedas \qty{ \intersect_{n=1}^\infty \OO_n} \setminus E \\
  & \subseteq \OO_N \setminus E \quad \text{for every } N\in \NN
  .\]
  - Then by subadditivity,
    $$
    m_*(E^c\setminus S) \leq m_*(\OO_N \setminus E) \leq {1\over N} \quad \forall N \implies m_*(E^c\setminus S) = 0
    .$$
  - Thus $E^c\setminus S$ is measurable.
:::
  
### Indirect Proof

- Since $E$ is measurable, $E^c$ is measurable.
- Since $E^c$ is measurable exists an open $O\supseteq E^c$ such that $m(O\setminus E^c) = 0$.
- Set $B \definedas O^c$, then $O\supseteq E^c \iff \OO^c \subseteq E \iff B\subseteq E$.
- Computing measures yields 
\[
E\setminus B \definedas E\setminus  \OO^c \definedas E\intersect (\OO^c)^c = E\intersect \OO = \OO \intersect(E^c)^c \definedas \OO \setminus E^c
,\]
  thus $m(E\setminus B) = m(\OO\setminus E^c) = 0$.
- Since $\OO$ is open, $B$ is closed and thus Borel.

### Direct Proof (Todo)

\todo[inline]{Try to construct the set.}
:::

## Spring 2018 # 1 $\done$
Define
$$
E:=\left\{x \in \mathbb{R}:\left|x-\frac{p}{q}\right|<q^{-3} \text { for infinitely many } p, q \in \mathbb{N}\right\}.
$$

Prove that $m(E) = 0$.

:::{.solution}
\hfill
:::{.concept}
\hfill
- Borel-Cantelli: If $\theset{E_k}_{k\in\ZZ}\subset 2^\RR$ is a countable collection of Lebesgue measurable sets with $\sum_{k\in \ZZ} m(E_k) < \infty$, then almost every $x\in \RR$ is in *at most finitely* many $E_k$.
  - Equivalently (?), $m(\limsup_{k\to\infty} E_k) = 0$, where $\limsup_{k\to\infty} E_k = \intersect_{k=1}^\infty \union_{j\geq k} E_j$, the elements which are in $E_k$ for infinitely many $k$.
:::

- Strategy: Borel-Cantelli.

- We'll show that $m(E) \intersect [n, n+1] = 0$ for all $n\in \ZZ$; then the result follows from 
\[
m(E) = m \qty{\union_{n\in \ZZ} E \intersect [n, n+1]} \leq \sum_{n=1}^\infty m(E \intersect [n, n+1]) = 0
.\]

- By translation invariance of measure, it suffices to show $m(E \intersect [0, 1]) = 0$.
  - So WLOG, replace $E$ with $E\intersect [0, 1]$.

- Define
\[
E_j \definedas \theset{x\in [0, 1] \suchthat \
\exists p\in \ZZ^{\geq 0} \text{ s.t. } \abs{x - \frac{p}{j} } < \frac 1 {j^3}} 
.\]

  - Note that $E_j \subseteq \disjoint_{p\in \ZZ^{\geq 0}} B_{j^{-3}}\qty{p\over j}$, i.e. a union over integers $p$ of intervals of radius $1/j^3$ around the points $p/j$.
    Since $1/j^3 < 1/j$, this union is in fact disjoint.

- Importantly, note that 
  \[
\limsup_{j\to\infty} E_j \definedas \intersect_{n=1}^\infty \union_{j=n}^\infty E_j = E
  \]
  
  since 
  
  \[
  x \in \limsup_j E_j 
  &\iff x \in E_j \text{ for infinitely many } j  \\
  &\iff \text{ there are infinitely many $j$ for which there exist a $p$ such that } \abs{x - {p\over j}} < j^{-3}  \\
  &\iff \text{ there are infinitely many such pairs $p, j$}  \\
  &\iff x\in E
  .\]

- Intersecting with $[0, 1]$, we can write $E_j$ as a union of intervals:
\[
E_j =& \qty{0, {j^{-3}}} 
\quad \disjoint \quad 
B_{j^{-3}}\qty{1\over j} \disjoint
B_{j^{-3}}\qty{2\over j} \disjoint
\cdots \disjoint
B_{j^{-3}}\qty{j-1\over j} 
\quad \disjoint \quad 
(1 - {j^{-3}}, 1)
,\]
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
\[
\sum_{j\in \NN} m(E_j) =  2\sum_{j\in \NN} \frac 1 {j^2} < \infty
,\]
  which converges by the $p\dash$test for sums.
  
- But then
\[
m(E) 
&= m(\limsup_j E_j) \\
&= m(\intersect_{n\in \NN} \union_{j\geq n} E_j) \\
&\leq m(\union_{j\geq N} E_j) \quad\text{for every } N \\
&\leq \sum_{j\geq N} m(E_j) \\
&\converges{N\to\infty}\to 0 \quad\text{}
.\]

- Thus $E$ is measurable as a subset of a null set and $m(E) = 0$.
:::

## Fall 2017 # 2 $\done$
Let $f(x) = x^2$ and $E \subset [0, \infty) \definedas \RR^+$.

1. Show that
\[
m^*(E) = 0 \iff m^*(f(E)) = 0.
\]

2. Deduce that the map

\[
\phi: \mathcal{L}(\RR^+) &\to \mathcal{L}(\RR^+) \\
E &\mapsto f(E)
\]
  is a bijection from the class of Lebesgue measurable sets of $[0, \infty)$ to itself.

\todo[inline]{Walk through.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- ?
:::

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
\[
\abs{f(x) - f(y)} = f'(c) \abs{x-y} \leq L \abs{x-y}
.\]
  
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
\[
\abs{g(Q_j)} \leq L^n \abs{Q_j}
,\]

and so 
\[
m^*(g(E)) \leq \sum_j \abs{g(Q_j)} \leq \sum_j L^n \abs{Q_j} = L^n \sum_j \abs{Q_j} \to 0 
.\]

Now just take $g(x) = x^2$ for one direction, and $g(x) = f\inv(x) = \sqrt{x}$ for the other.
$\qed$

### b

> Lemma: $E$ is measurable iff $E = K \disjoint N$ for some $K$ compact, $N$ null.

Write $E = K \disjoint N$ where $K$ is compact and $N$ is null.

Then $\phi\inv(E) = \phi\inv(K \disjoint N) = \phi\inv(K) \disjoint \phi\inv(N)$.

Since $\phi\inv(N)$ is null by part (a) and $\phi\inv(K)$ is the preimage of a compact set under a continuous map and thus compact, $\phi\inv(E) = K' \disjoint N'$ where $K'$ is compact and $N'$ is null, so $\phi\inv(E)$ is measurable.

So $\phi$ is a measurable function, and thus yields a well-defined map $\mathcal L(\RR) \to \mathcal L(\RR)$ since it preserves measurable sets.
Restricting to $[0, \infty)$, $f$ is bijection, and thus so is $\phi$.
:::

## Spring 2017 # 2 $\done$

### a 
Let $\mu$ be a measure on a measurable space $(X, \mathcal M)$ and $f$ a positive measurable function.
  
  Define a measure $\lambda$ by
\[
\lambda(E):=\int_{E} f ~d \mu, \quad E \in \mathcal{M}
\]

Show that for $g$ any positive measurable function, 
\[
\int_{X} g ~d \lambda=\int_{X} f g ~d \mu
\]

### b 
Let $E \subset \RR$ be a measurable set such that 
\[
\int_{E} x^{2} ~d m=0.
\]
Show that $m(E) = 0$.

:::{.solution}
\hfill
:::{.concept}
\hfill
- Absolute continuity of measures: $\lambda \ll \mu \iff E\in\mathcal{M}, \mu(E) = 0 \implies \lambda(E) = 0$.
- Radon-Nikodym: if $\lambda \ll \mu$, then there exists a measurable function $\dd{\lambda}{\mu} \definedas f$ where $\lambda(E) = \int_E f \,d\mu$.
- Chebyshev's inequality:
\[  
A_c \definedas \theset{ x\in X \suchthat \abs{f(x)} \geq c  } \implies \mu(A_c) \leq c^{-p} \int_{A_c} \abs{f}^p \,d\mu \quad \forall 0 < p < \infty
.\]
:::

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

\todo[inline]{What is the final step in this approximation?}

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
:::

## Fall 2016 # 4 $\done$
Let $(X, \mathcal M, \mu)$ be a measure space and suppose $\theset{E_n} \subset \mathcal M$ satisfies
\[
\lim _{n \rightarrow \infty} \mu\left(X \backslash E_{n}\right)=0.
\]

Define
\[
G \definedas \theset{x\in X \suchthat x\in E_n \text{ for only finitely many  } n}.
\]

Show that $G \in \mathcal M$ and $\mu(G) = 0$.

\todo[inline]{Add concepts.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- ?
:::

- Claim: $G\in \mcm$.
  - Claim:
  \[  
  G = \qty{ \intersect_{N=1}^\infty \union_{n=N}^\infty E_n}^c = \union_{N=1}^\infty \intersect_{n=N}^\infty E_n^c
  .\]

    - This follows because $x$ is in the RHS $\iff$ $x\in E_n^c$ for all but finitely many $n$ $\iff$ $x\in E_n$ for at most finitely many $n$.

  - But $\mcm$ is a $\sigma\dash$algebra, and this shows $G$ is obtained by countable unions/intersections/complements of measurable sets, so $G\in \mcm$. 

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

\todo[inline]{Last step seems wrong!}
:::

## Spring 2016 # 3 $\work$
Let $f$ be Lebesgue measurable on $\RR$ and $E \subset \RR$ be measurable such that
$$
0<A=\int_{E} f(x) d x<\infty.
$$

Show that for every $0 < t < 1$, there exists a measurable set $E_t \subset E$ such that
$$
\int_{E_{t}} f(x) d x=t A.
$$

## Spring 2016 # 5 $\work$
Let $(X, \mathcal M, \mu)$ be a measure space. For $f\in L^1(\mu)$ and $\lambda > 0$, define
$$
\phi(\lambda)=\mu(\{x \in X | f(x)>\lambda\}) 
\quad \text { and } \quad 
\psi(\lambda)=\mu(\{x \in X | f(x)<-\lambda\})
$$

Show that $\phi, \psi$ are Borel measurable and
$$
\int_{X}|f| ~d \mu=\int_{0}^{\infty}[\phi(\lambda)+\psi(\lambda)] ~d \lambda
$$

## Fall 2015 # 2 $\work$
Let $f: \RR \to \RR$ be Lebesgue measurable.

1. Show that there is a sequence of simple functions $s_n(x)$ such that $s_n(x) \to f(x)$ for all $x\in \RR$.
2. Show that there is a Borel measurable function $g$ such that $g = f$ almost everywhere.

## Spring 2015 # 3 $\work$

Let $\mu$ be a finite Borel measure on $\RR$ and $E \subset \RR$ Borel. 
Prove that the following statements are equivalent:

1. $\forall \varepsilon > 0$ there exists $G$ open and $F$ closed such that 
$$
F \subseteq E \subseteq G \quad \text{and} \quad \mu(G\setminus F) < \varepsilon.
$$
2. There exists a $V \in G_\delta$ and $H \in F_\sigma$ such that 
$$
H \subseteq E \subseteq V \quad \text{and}\quad \mu(V\setminus H) = 0
$$

## Spring 2014 # 3 $\work$
Let $f: \RR \to \RR$ and suppose
$$
\forall x\in \RR,\quad f(x) \geq \limsup _{y \rightarrow x} f(y)
$$
Prove that $f$ is Borel measurable.

## Spring 2014 # 4 $\work$
Let $(X, \mathcal M, \mu)$ be a measure space and suppose $f$ is a measurable function on $X$.
Show that
$$
\lim _{n \rightarrow \infty} \int_{X} f^{n} ~d \mu =
\begin{cases}
\infty & \text{or} \\
\mu(f\inv(1)),
\end{cases}
$$
and characterize the collection of functions of each type.

## Spring 2017 # 1 $\done$

Let $K$ be the set of numbers in $[0, 1]$ whose decimal expansions do not use the digit $4$.

> We use the convention that when a decimal number ends with 4 but all other digits are
different from 4, we replace the digit $4$ with $399\cdots$. For example, $0.8754 = 0.8753999\cdots$.

Show that $K$ is a compact, nowhere dense set without isolated points, and find the
Lebesgue measure $m(K)$.

:::{.solution}
\hfill
:::{.concept}
\hfill
- Definition: $A$ is *nowhere dense* $\iff$ every interval $I$ contains a subinterval $S \subseteq A^c$.
  - Equivalently, the interior of the closure is empty, $\qty{\bar K}^\circ = \emptyset$.
:::

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
:::

## Spring 2016 # 2 $\work$
Let $0 < \lambda < 1$ and construct a Cantor set $C_\lambda$ by successively removing middle intervals of length $\lambda$.

Prove that $m(C_\lambda) = 0$.

# Measure Theory: Functions

## Fall 2016 # 2 $\done$

Let $f, g: [a, b] \to \RR$ be measurable with
$$
\int_{a}^{b} f(x) ~d x=\int_{a}^{b} g(x) ~d x.
$$

Show that either

1. $f(x) = g(x)$ almost everywhere, or
2. There exists a measurable set $E \subset [a, b]$ such that
\[]
\int _{E} f(x) \, dx > \int _{E} g(x) \, dx
\]

\todo[inline]{Add concepts.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- ?
:::

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
:::

## Spring 2016 # 4 $\work$
Let $E \subset \RR$ be measurable with $m(E) < \infty$. 
Define
\[
f(x)=m(E \cap(E+x)).
\]

Show that

1. $f\in L^1(\RR)$.
2. $f$ is uniformly continuous.
3. $\lim _{|x| \to \infty} f(x) = 0$.

> Hint: 
\[
\chi_{E \cap(E+x)}(y)=\chi_{E}(y) \chi_{E}(y-x)
\]


# Integrals: Convergence

## Fall 2019 # 2 $\done$

Prove that
\[
\left| \frac{d^{n}}{d x^{n}} \frac{\sin x}{x}\right| \leq \frac{1}{n}
\]

for all $x \neq 0$ and positive integers $n$.

> Hint: Consider $\displaystyle\int_0^1 \cos(tx) dt$

:::{.solution}
\hfill
:::{.concept}
\hfill
- DCT
- Bounding in the right place. 
  Don't evaluate the actual integral!
:::

- By induction on the number of limits we can pass through the integral.
- For $n=1$ we first pass one derivative into the integral: let $x_n \to x$ be any sequence converging to $x$, then
\[
\dd{}{x} {\sin(x) \over x} 
&= \dd{}{x} \int_0^1 \cos(tx)\,dt  \\
&= \lim_{x_n\to x} {1\over x_n - x} \qty{ \int_0^1 \cos(t x_n)\,dt  - \int_0^1 \cos(tx) \,dt} \\
&= \lim_{x_n\to x} \qty{ \int_0^1 { \cos(tx_n)  - \cos(tx) \over x_n - x}   \,dt} \\
&= \lim_{x_n\to x} \qty{ \int_0^1 \qty{t\sin(tx)\mid_{x=\xi_n}}  \,dt} \qtext{where} \xi_n \in [x_n, x] \text{ by MVT}, \xi_n\to x \\
&= \lim_{\xi_n\to x} \qty{ \int_0^1 t \sin(t \xi_n)  \,dt}  \\
&=_{\text{DCT}}  \int_0^1 \lim_{\xi_n \to x} t \sin(t \xi_n)  \,dt \\
&= \int_0^1 t\sin(tx) \,dt \\
.\]

- Taking absolute values we obtain an upper bound 
\[
\abs{ \dd{}{x} {\sin(x) \over x} } 
&= \abs{ \int_0^1 t\sin(tx) \,dt } \\
&\leq \int_0^1 \abs{t\sin(tx)} \,dt \\
&\leq \int_0^1 1 \, dt = 1
,\]
  since $t\in [0, 1] \implies \abs{t} < 1$, and $\abs{\sin(xt)} \leq 1$ for any $x$ and $t$.

- Note that this bound also justifies the DCT, since the functions $f_n(t) = t\sin(t \xi_n )$ are uniformly dominated by $g(t) = 1$ on $L^1([0, 1])$.

> Note: integrating by parts here yields the actual formula:
\[
\int_0^1 t\sin(tx) \,dt 
&=_{\text{IBP}} \qty{-t\cos(tx) \over x}\mid_{t=0}^{t=1} - \int_0^1 {\cos(tx) \over x} \,dt \\
&= {-\cos(x) \over x} - {\sin(x) \over x^2} \\
&= {x\cos(x) - \sin(x) \over x^2}
.\]

- For the inductive step, we assume that we can pass $n-1$ limits through the integral and show we can pass the $n$th through as well.
\[
\dd{^n}{x^n} {\sin(x) \over x} 
&= \dd{^n}{x^n} \int_0^1 \cos(tx)\,dt  \\
&= \dd{}{x} \int_0^1 \dd{^{n-1}}{x^{n-1}} \cos(tx)\,dt  \\
&= \dd{}{x} \int_0^1 t^{n-1} f_{n-1}(x, t) \,dt 
\]
  - Note that $f_n(x, t) = \pm \sin(tx)$ when $n$ is odd and $f_n(x, t) = \pm \cos(tx)$ when $n$ is even, and a constant factor of $t$ is multiplied when each derivative is taken.

- We continue as in the base case:
\[
\dd{}{x} \int_0^1 t^{n-1} f_{n-1}(x, t) \,dt 
&= \lim_{x_k\to x} \int_0^1 t^{n-1} \qty{ f_{n-1}(x_n, t) - f_{n-1}(x, t) \over x_n - x} \,dt \\
&=_{\text{IVT}} \lim_{x_k\to x} \int_0^1 t^{n-1} \dd{f_{n-1}}{x}(\xi_k, t) \,dt \quad\text{where } \xi_k\in [x_k, x],\, \xi_k \to x \\
&=_{\text{DCT}} \int_0^1 \lim_{x_k\to x} t^{n-1} \dd{f_{n-1}}{x}(\xi_k, t) \,dt \\
&\definedas \int_0^1 \lim_{x_k\to x} t^{n} f_n(\xi_k, t) \,dt \\
&\definedas \int_0^1 t^{n} f_n(x, t) \,dt 
.\]
  - We've used the fact that $f_0(x) = \cos(tx)$ is smooth as a function of $x$, and in particular continuous 
  - The DCT is justified because the functions $h_{n, k}(x, t) = t^n f_n(\xi_k, t)$ are again uniformly (in $k$) bounded by 1 since $t\leq 1 \implies t^n \leq 1$ and each $f_n$ is a sin or cosine.

- Now take absolute values
\[
\abs {\dd{^n}{x^n} {\sin(x) \over x}  }
&= \abs{ \int_0^1 -t^n f_n(x, t) ~dt } \\ 
&\leq \int_0^1 \abs{t^n f_n(x, t)} ~dt \\
&\leq \int_0^1 \abs{t^n} \abs{f_n(x, t)} ~dt \\
&\leq \int_0^1 \abs{ t^n} \cdot 1 ~dt \\ 
&\leq \int_0^1 t^n ~dt \quad\text{since $t$ is positive} \\ 
&= \frac{1}{n+1} \\
&< \frac{1}{n}
.\]
  - We've again used the fact that $f_n(x, t)$ is of the form $\pm \cos(tx)$ or $\pm \sin(tx)$, both of which are bounded by 1.
:::

## Spring 2020 # 5 $\done$

Compute the following limit and justify your calculations:
\[
\lim_{n\to\infty} \int_0^n \qty{1 + {x^2 \over n}}^{-(n+1)} \,dx
.\]

\todo[inline]{Not finished, flesh out.}
\todo[inline]{Walk through.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- DCT
- Passing limits through products and quotients
:::

Note that 
\[
\lim_{n} \qty{1 + {x^2 \over n}}^{-(n+1)} 
&= {1 \over \lim_{n} \qty{1 + {x^2 \over n}}^1 \qty{1 + {x^2 \over n}}^n } \\
&= {1 \over 1 \cdot e^{x^2}} \\
&= e^{-x^2}
.\]

If passing the limit through the integral is justified, we will have
\[
\lim_{n\to\infty} \int_0^n \qty{ 1 + {x^2\over n}}^{-(n+1)}\, dx 
&= \lim_{n\to\infty} \int_\RR \chi_{[0, n]} \qty{ 1 + {x^2\over n}}^{-(n+1)} \, dx  \\
&= \int_\RR \lim_{n\to\infty} \chi_{[0, n]} \qty{ 1 + {x^2\over n}}^{-(n+1)} \, dx  \qtext{by the DCT} \\
&= \int_\RR \lim_{n\to\infty} \qty{ 1 + {x^2\over n}}^{-(n+1)} \, dx  \\
&= \int_0^\infty e^{-x^2}  \\
&= {\sqrt \pi \over 2}
.\]

Computing the last integral:

\[
\qty{\int_\RR e^{-x^2}\, dx}^2
&= \qty{\int_\RR e^{-x^2}\,dx} \qty{\int_\RR e^{-y^2}\,dx} \\
&= \int_\RR \int_\RR e^{-(x+y)^2}\, dx \\
&= \int_0^{2\pi} \int_0^\infty e^{-r^2} r\, dr \, d\theta \qquad u=r^2 \\
&= {1\over 2} \int_0^{2\pi } \int_0^\infty e^{-u}\, du \, d\theta \\
&= {1\over 2} \int_0^{2\pi} 1 \\
&= \pi
,\]
and now use the fact that the function is even so $\int_0^\infty f = {1\over 2} \int_\RR f$.

Justifying the DCT:

- Apply Bernoulli's inequality: 
\[
{1 + {x^2\over n}}^{n+1} \geq {1 + {x^2\over n}}\qty{1 + x^2} \geq {1 + x^2}
,\]
  where the last inequality follows from the fact that $1 + {x^2 \over n} \geq 1$
:::

## Spring 2019 # 3 $\done$
Let $\{f_k\}$ be any sequence of functions in $L^2([0, 1])$ satisfying $\norm{f_k}_2 ≤ M$ for all $k ∈ \NN$.
  
Prove that if $f_k → f$ almost everywhere, then $f ∈ L^2([0, 1])$ with $\norm{f}_2 ≤ M$ and
$$
\lim _{k \rightarrow \infty} \int_{0}^{1} f_{k}(x) dx = \int_{0}^{1} f(x) d x
$$

> Hint: Try using Fatou’s Lemma to show that $\norm{f}_2 ≤ M$ and then try applying Egorov’s Theorem.

:::{.solution}
\hfill
:::{.concept}
\hfill
- Definition of $L^+$: space of measurable function $X\to [0, \infty]$.
- Fatou: For any sequence of $L^+$ functions, $\int \liminf f_n \leq \liminf \int f_n$.
- Egorov's Theorem: If $E\subseteq \RR^n$ is measurable, $m(E) > 0$, $f_k:E\to \RR$ a sequence of measurable functions where $\lim_{n\to\infty} f_n(x)$ exists and is finite a.e., then $f_n\to f$ *almost uniformly*: for every $\eps>0$ there exists a closed subset $F_\eps \subseteq E$ with $m(E\setminus F) < \eps$ and $f_n\to f$ uniformly on $F$.
:::

$L^2$ bound:

- Since $f_k \to f$ almost everywhere, $\liminf_n f_n(x) = f(x)$ a.e.
- $\norm{f_n}_2 < \infty$ implies each $f_n$ is measurable and thus $\abs{f_n}^2 \in L^+$, so we can apply Fatou:

\[
\norm{f}_2^2
&= \int \abs{f(x)}^2  \\
&= \int \liminf_n \abs{f_n(x)}^2 \\
&\underset{\text{Fatou}}\leq\liminf_n \int \abs{f_n(x)}^2 \\
&\leq \liminf_n M \\
&= M
.\]

- Thus $\norm{f}_2 \leq \sqrt{M} < \infty$ implying $f\in L^2$.

\todo[inline]{What is the "right" proof here that uses the first part?}
Equality of Integrals: 

- Take the sequence $\eps_n = {1\over n}$
- Apply Egorov's theorem: obtain a set $F_\eps$ such that $f_n \to f$ uniformly on $F_\eps$ and $m(I\setminus F_\eps) < \eps$. 
\[
\lim_{n\to \infty} \abs{ \int_0^1 f_n - f }
&\leq \lim_{n\to\infty} \int_0^1 \abs{f_n - f} \\
&= \lim_{n\to\infty} \qty{ \int_{F_\eps} \abs{f_n - f} + \int_{I\setminus F_\eps} \abs{f_n - f} } \\
&= \int_{F_\eps} \lim_{n\to\infty} \abs{f_n - f} + \lim_{n\to\infty} \int_{I\setminus F_\eps} \abs{f_n - f} \quad\text{by uniform convergence} \\ 
&= 0 + \lim_{n\to\infty} \int_{I\setminus F_\eps} \abs{f_n - f}
,\]

  so it suffices to show $\int_{I\setminus F_\eps} \abs{f_n - f} \converges{n\to\infty}\to 0$.

- We can obtain a bound using Holder's inequality with $p=q=2$:
\[
\int_{I\setminus F_\eps} \abs{f_n - f} 
&\leq \qty{ \int_{I\setminus F_\eps} \abs{f_n - f}^2 } \qty{ \int_{I\setminus F_\eps} \abs{1}^2  } \\
&= \qty{ \int_{I\setminus F_\eps} \abs{f_n - f}^2 } \mu(F_\eps) \\
&\leq \norm{f_n - f}_2 \mu(F_\eps) \\
&\leq \qty{ \norm{f_n}_2 + \norm{f}_2 } \mu(F_\eps) \\
&\leq 2M \cdot \mu(F_\eps)
\]
  where $M$ is now a constant not depending on $\eps$ or $n$.

- Now take a nested sequence of sets $F_{\eps}$ with $\mu(F_\eps) \to 0$ and applying continuity of measure yields the desired statement.
:::

## Fall 2018 # 6 $\done$
Compute the following limit and justify your calculations:
\[
\lim_{n \rightarrow \infty} \int_{1}^{n} \frac{d x}{\left(1+\frac{x}{n}\right)^{n} \sqrt[n]{x}}
\]

\todo[inline]{Add concepts.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- ?
:::

- Note that $x^{1\over n} \converges{n\to\infty}\to 1$ for any $0 < x < \infty$.
- Thus the integrand converges to ${1\over e^x}$, which is integrable on $(0, \infty)$ and integrates to 1.
- Break the integrand up:
\[
\int_0^\infty {1 \over  \qty{ 1 + {x\over n} }^n x^{1\over n}} \,dx
= \int_0^1 {1 \over  \qty{ 1 + {x\over n} }^n x^{1\over n}} \,dx
= \int_1^\infty {1 \over  \qty{ 1 + {x\over n} }^n x^{1\over n}} \,dx
.\]
:::

## Fall 2018 # 3 $\done$
Suppose $f(x)$ and $xf(x)$ are integrable on $\RR$.
Define $F$ by
\[
F(t)\definedas \int _{-\infty}^{\infty} f(x) \cos (x t) dx
\]
Show that 
\[
F'(t)=-\int _{-\infty}^{\infty} x f(x) \sin (x t) dx
.\]

\todo[inline]{Walk through.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- Mean Value Theorem
- DCT
:::
\[
\dd{}{t} F(t) 
&= \dd{}{t} \int_\RR f(x) \cos(xt) ~dx \\
&\overset{DCT}= \int_\RR f(x) \dd{}{t} \cos(xt) ~dx \\
&= \int_\RR xf(x) \cos(xt)~dx
,\]
so it only remains to justify the DCT.

- Fix $t$, then let $t_n \to t$ be arbitrary.
- Define 
$$
h_n(x, t) = f(x)
\left(\frac{\cos(tx) - \cos(t_n x)}{t_n - t}\right) \converges{n\to\infty}\to \dd{}{t} \qty{f(x) \cos(xt)}
$$
 since $\cos(tx)$ is differentiable in $t$ and this is the limit definition of differentiability.

- Note that
\[
\dd{}{t} \cos(tx) 
&\definedas \lim_{t_n \to t} \frac{\cos(tx) - \cos(t_n x)}{t_n - t} \\
&\overset{MVT} = \dd{}{t}\cos(tx)\mid_{t  = \xi_n} \hspace{6em} \text{for some } \xi_n \in [t, t_n] \text{ or } [t_n, t] \\
&= x\sin(\xi_n x)
\]
  where $\xi_n \converges{n\to\infty}\to t$ since wlog $t_n \leq \xi_n \leq t$ and $t_n \nearrow t$.

- We then have $$\abs{h_n(x)} = \abs{f(x) x\sin(\xi_n x)} \leq \abs{xf(x)}\quad\text{since } \abs{\sin(\xi_n x)} \leq  1$$ for every $x$ and every $n$.
- Since $xf(x) \in L^1(\RR)$ by assumption, the DCT applies. 
:::

## Spring 2018 # 5 $\done$

Suppose that

- $f_n, f \in L^1$,
- $f_n \to f$ almost everywhere, and
- $\int\left|f_{n}\right| \rightarrow \int|f|$.

Show that $\int f_{n} \rightarrow \int f$.

:::{.solution}
\hfill
:::{.concept}
\hfill
- $\int \abs{f_n - f} \to \iff \int f_n = \int f$.
- Fatou:
\[
\int \liminf f_n \leq \liminf \int f_n \\
\int \limsup f_n \geq \limsup \int f_n
.\]
:::

- Since $\int \abs{f_n} \converges{n\to\infty}\to \int \abs{f}$, define
\[
h_n &= \abs{f_n - f} &\converges{n\to\infty}\to 0 ~a.e.\\
g_n &= \abs{f_n} + \abs{f} &\converges{n\to\infty}\to 2\abs {f} ~a.e.
\]

  - Note that $g_n - h_n \converges{n\to\infty}\to 2\abs{f} - 0 = 2\abs{f}$.

- Then
\[
\int 2 \abs {f} 
&= \int \liminf_n (g_n - h_n) \\
&= \int \liminf_n(g_n) + \int \liminf_n(-h_n) \\
&= \int \liminf_n(g_n) - \int \limsup_n(h_n) \\
&= \int 2 \abs{f} - \int \limsup_n(h_n) \\
&\leq \int 2\abs{f} - \limsup_n \int h_n \quad\text{by Fatou}
,\]

- Since $f\in L^1$, $\int 2\abs{f}  = 2\norm{f}_1 < \infty$ and it makes sense to subtract it from both sides, thus
\[
0 &\leq - \limsup_n \int h_n \\
&\definedas - \limsup_n \int \abs{f_n - f}
.\]
  which forces $\limsup_n \int \abs{f_n -f}  = 0$, since
    
    - The integral of a nonnegative function is nonnegative, so $\int \abs{f_n - f} \geq 0$.
    - So $\qty{ -\int \abs{f_n - f} } \leq 0$.
    - But the above inequality shows $\qty{ -\int \abs{f_n - f} } \geq 0$ as well.
- Since $\liminf_n \int h_n \leq \limsup_n \int h_n = 0$, $\lim_n \int h_n$ exists and is equal to zero.

- But then 
\[
\abs{\int f_n - \int f}
&= \abs{\int f_n -f}
\leq \int \abs{f_n - f}
,\]
  and taking $\lim_{n\to\infty}$ on both sides yields
  \[
  \lim_{n\to\infty} \abs{\int f_n - \int f} \leq \lim_{n\to\infty} \int \abs{f_n - f} = 0
  ,\]
  so $\lim_{n\to\infty} \int f_n = \int f$.
:::

## Spring 2018 # 2 $\done$
Let
\[
f_{n}(x):=\frac{x}{1+x^{n}}, \quad x \geq 0.
\]

a. Show that this sequence converges pointwise and find its limit. Is the convergence uniform on $[0, \infty)$?

b. Compute 
\[
\lim _{n \rightarrow \infty} \int_{0}^{\infty} f_{n}(x) d x
\]

\todo[inline]{Add concepts.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- ?
:::


### a

Claim: $f_n$ does not converge uniformly to its limit.

- Note each $f_n(x)$ is clearly continuous on $(0, \infty)$, since it is a quotient of continuous functions where the denominator is never zero.

- Note 
\[
x < 1 \implies x^n \converges{n\to\infty}\to 0\qtext{and} x>1 \implies x^n \converges{n\to\infty}\to \infty
.\]

- Thus
\[
f_n(x) = \frac{x}{1+ x^n}\converges{n\to\infty}\longrightarrow
f(x) \definedas
\begin{cases}
x, & 0 \leq x < 1 \\
\frac 1 2, & x = 1 \\
0, & x > 1 \\
\end{cases}
.\]

- If $f_n \to f$ uniformly on $[0, \infty)$, it would converge uniformly on every subset and thus uniformly on $(0, \infty)$.
  - Then $f$ would be a uniform limit of continuous functions on $(0, \infty)$ and thus continuous on $(0, \infty)$.
  - By uniqueness of limits, $f_n$ would converge to the pointwise limit $f$ above, which is not continuous at $x=1$, a contradiction.

### b

- If the DCT applies, interchange the limit and integral:
    \[
    \lim_{n\to\infty }\int_0^\infty f_n(x)\, dx 
&= \int_0^\infty \lim_{n\to\infty}f_n(x) \, dx \quad\text{DCT}\\
    &=\int_0^\infty f(x) \,dx \\
    &= \int_0^1 x \,dx + \int_1^\infty 0\, dx \\
    &= {1\over 2}x^2 \evalfrom_0^1 \\
    &= {1\over 2}
    .\]

- To justify the DCT, write 
\[
\int_0^\infty f_n(x)
= \int_0^1 f_n(x) + \int_1^\infty f_n(x)
.\]

- $f_n$ restricted to $(0, 1)$ is uniformly bounded by $g_0(x) = 1$ in the first integral, since
  \[
  x \in [0, 1] \implies \frac{x}{1+x^n} < \frac{1}{1+x^n} < 1 \definedas g(x)
  \]
  so 
  \[
  \int_0^1 f_n(x)\,dx \leq \int_0^1 1 \,dx = 1 < \infty
  .\]
  Also note that $g_0\cdot \chi_{(0, 1)} \in L^1((0, \infty))$.

- The $f_n$ restricted to $(1, \infty)$ are uniformly bounded by $g_1(x) = {1\over x^{2}}$ on $[1, \infty)$, since
  \[
  x \in (1, \infty) \implies \frac{x}{1+x^n} \leq {x \over x^n} = {1 \over x^{n-1}} \leq {1\over x^2}\in L^1([1, \infty) \text{ when } n\geq 3
  ,\]
  by the $p\dash$test for integrals.

- So set $$g \definedas g_0 \cdot \chi_{(0, 1)} + g_1 \cdot \chi_{[1, \infty)},$$ then by the above arguments $g \in L^1((0, \infty))$ and $f_n \leq g$ everywhere, so the DCT applies.
:::

## Fall 2016 # 3 $\done$

Let $f\in L^1(\RR)$.
Show that
\[
\lim _{x \to 0} \int _{\RR} \abs{f(y-x)-f(y)} \, dy = 0
\]
\todo[inline]{Missing some stuff.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- $C_c^\infty \injects L^p$ is dense.
- If $f$...?
:::

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
:::

## Fall 2015 # 3 $\work$
Compute the following limit:
\[
\lim _{n \rightarrow \infty} \int_{1}^{n} \frac{n e^{-x}}{1+n x^{2}} \, \sin \left(\frac x n\right) \, dx
\]

## Fall 2015 # 4 $\work$
Let $f: [1, \infty) \to \RR$ such that $f(1) = 1$ and
\[
f^{\prime}(x)= \frac{1} {x^{2}+f(x)^{2}}
\]

Show that the following limit exists and satisfies the equality
\[
\lim _{x \rightarrow \infty} f(x) \leq 1 + \frac \pi 4
\]

# Integrals: Approximation

## Spring 2018 # 3 $\done$
Let $f$ be a non-negative measurable function on $[0, 1]$. 

Show that
\[
\lim _{p \rightarrow \infty}\left(\int_{[0,1]} f(x)^{p} d x\right)^{\frac{1}{p}}=\|f\|_{\infty}.
\]

:::{.solution}
\hfill
:::{.concept}
\hfill
- $\norm{f}_\infty \definedas \inf_t {\theset{ t\suchthat m\qty{\theset{x\in \RR^n \suchthat f(x) > t}} = 0 } }$, i.e. this is the lowest upper bound that holds almost everywhere.
:::

- $\norm{f}_p \leq \norm{f}_\infty$:
  - Note $\abs{f(x)} \leq \norm{f}_\infty$ almost everywhere and taking $p$th powers preserves this inequality.
  - Thus
  \[
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
  .\]

    - Thus $\norm{f}_p \leq \norm{f}_\infty$ for all $p$ and taking $\lim_{p\to\infty}$ preserves this inequality.

- $\norm{f}_p \geq \norm{f}_\infty$:
  - Fix $\varepsilon > 0$.

  - Define 
  \[
  S_\varepsilon \definedas \theset{x\in \RR^n \suchthat \abs{f(x)} \geq \norm{f}_\infty - \varepsilon}
  .\]

    - Note that $m(S_\eps) > 0$; otherwise if $m(S_\eps) = 0$, then $t\definedas \norm{f}_\infty - \eps < \norm{f}_\eps$.
    But this produces a *smaller* upper bound almost everywhere than $\norm{f}_\eps$, contradicting the definition of $\norm{f}_\eps$ as an infimum over such bounds.
    


  - Then
  \[
  \norm{f}_p^p 
  &= \int_X \abs{f(x)}^p ~dx \\
  &\geq \int_{S_\varepsilon} \abs{f(x)}^p ~dx \quad\text{since } S_\eps \subseteq X \\
  &\geq \int_{S_\varepsilon} \abs{\norm{f}_\infty - \varepsilon}^p ~dx \quad\text{since on } S_\eps, \abs{f} \geq \norm{f}_\infty - \eps \\
  &= \abs{\norm{f}_\infty - \varepsilon}^p \cdot m(S_\varepsilon) \quad\text{since the integrand is independent of }x \\
  & \geq 0 \quad\text{since } m(S_\eps) > 0
  \]
  
  - Taking $p$th roots for $p\geq 1$ preserves the inequality, so
  \[
  \implies \norm{f}_p &\geq \abs{\norm{f}_\infty - \varepsilon} \cdot m(S_\varepsilon)^{\frac 1 p} 
  \converges{p\to\infty}\to \abs{\norm{f}_\infty - \varepsilon} 
  \converges{\varepsilon \to 0}\to \norm{f}_\infty
  \]
  where we've used the fact that above arguments work 

  - Thus $\norm{f}_p \geq \norm{f}_\infty$.


:::



## Spring 2018 # 4 $\done$
Let $f\in L^2([0, 1])$ and suppose
$$
\int _{[0,1]} f(x) x^{n} d x=0 \text { for all integers } n \geq 0.
$$
Show that $f = 0$ almost everywhere.

## Spring 2015 # 2 $\done$
Let $f: \RR \to \CC$ be continuous with period 1. 
Prove that
\[
\lim _{N \rightarrow \infty} \frac{1}{N} \sum_{n=1}^{N} f(n \alpha)=\int_{0}^{1} f(t) d t \quad \forall \alpha \in \RR\setminus\QQ.
\]

> Hint: show this first for the functions $f(t) = e^{2\pi i k t}$ for $k\in \ZZ$.

\todo[inline]{Add concepts.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- ?
:::

### Proof 1: Using Fourier Transforms
\hfill
:::{.concept}
\hfill
- Weierstrass Approximation: A uniformly continuous function on a compact set can be uniformly approximated by polynomials.
:::

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
\[
\inner{f}{e_k} 
&= \int_0^1 f(x) e^{-2\pi i k x} ~dx \\
&= \int_0^1 f(x) \lim_{\ell \to \infty} P_\ell(x) \\
&= \lim_{\ell \to \infty}  \int_0^1 f(x) P_\ell(x) \quad\quad \text{by uniform convergence on a compact interval} \\
&= \lim_{\ell \to \infty} 0 \quad\text{by assumption}\\
&= 0 \quad \forall k\in \ZZ
,\]
 so $f$ is orthogonal to every $e_k$. 

- Thus $f\in S^\perp \definedas \spanof_\CC\theset{e_k}_{k\in \ZZ}^\perp \subseteq L^2([0, 1])$, but since this is a basis, $S$ is dense and thus $S^\perp = \theset{0}$ in $L^2([0, 1])$.

- Thus $f\equiv 0$ in $L^2([0, 1])$, which implies that $f$ is zero almost everywhere.

$\qed$

### Alternative Proof
\hfill
:::{.concept}
\hfill
- $C^1([0, 1])$ is dense in $L^2([0, 1])$
- Polynomials are dense in $L^p(X, \mathcal{M}, \mu)$ for any $X\subseteq \RR^n$ compact and $\mu$ a finite measure, for all $1\leq p < \infty$.
  - Use Weierstrass Approximation, then uniform convergence implies $L^p(\mu)$ convergence by DCT.
:::

- By density of polynomials, for $f\in L^2([0, 1])$ choose $p_\eps(x)$ such that $\norm{f - p_\eps} < \eps$ by Weierstrass approximation.
- Then on one hand,
\[
\norm{f(f-p_\eps)}_1 
&= \norm{f^2}_1 - \norm{f\cdot p_\eps}_1 \\
&= \norm{f^2}_1 - 0 \quad\text{by assumption} \\
&= \norm{f}_2^2
.\]

  - Where we've used that $\norm{f^2}_1 = \int \abs{f^2} = \int \abs{f}^2 = \norm{f}_2^2$.

- On the other hand
\[
\norm{f(f-p_\eps)} 
&\leq \norm{f}_1 \norm{f-p_\eps}_\infty \quad\text{by Holder} \\
&\leq \eps \norm{f}_1  \\
&\leq \eps \norm{f}_2 \sqrt{m(X)} \\ 
&= \eps \norm{f}_2 \quad\text{since } m(X)= 1
.\]
  - Where we've used that $\norm{fg}_1 = \int \abs{fg} = \int \abs{f}\abs{g} \leq \int \norm{f}_\infty \abs{g} = \norm{f}_\infty \norm{g}_1$.

- Combining these,
\[
\norm{f}_2^2 \leq \norm{f}_2 \eps \implies \norm{f}_2 < \eps \to 0,
.\]
  so $\norm{f}_2 = 0$, which implies $f=0$ almost everywhere.


:::



## Fall 2014 # 4
Let $g\in L^\infty([0, 1])$
Prove that
\[
\int _{[0,1]} f(x) g(x)\, dx = 0 
\quad\text{for all continuous } f:[0, 1] \to \RR 
\implies g(x) = 0 \text{ almost everywhere. }
\]


# $L^1$

## Spring 2020 # 3 $\done$

a. Prove that if $g\in L^1(\RR)$ then
\[
\lim_{N\to \infty} \int _{\abs{x} \geq N} \abs{f(x)} \, dx = 0
,\]
and demonstrate that it is not necessarily the case that $f(x) \to 0$ as $\abs{x}\to \infty$.

b. Prove that if $f\in L^1([1, \infty])$ and is decreasing, then $\lim_{x\to\infty}f(x) =0$ and in fact $\lim_{x\to \infty} xf(x) = 0$.

c. If $f: [1, \infty) \to [0, \infty)$ is decreasing with $\lim_{x\to \infty} xf(x) = 0$, does this ensure that $f\in L^1([1, \infty))$?

:::{.solution}
\hfill
:::{.concept}
\hfill
- Limits
- Cauchy Criterion for Integrals: $\int_a^\infty f(x) \,dx$ converges iff for every $\eps>0$ there exists an $M_0$ such that $A,B\geq M_0$ implies $\abs{\int_A^B f} < \eps$, i.e. $\abs{\int_A^B f} \converges{A\to\infty}\to 0$.
- Integrals of $L^1$ functions have vanishing tails: $\int_{N}^\infty \abs{f} \converges{N\to\infty}\to 0$.
- Mean Value Theorem for Integrals: $\int_a^b f(t)\, dt = (b-a) f(c)$ for some $c\in [a, b]$.
:::

### a

Stated integral equality: 

- Let $\eps > 0$
- $C_c(\RR^n) \injects L^1(\RR^n)$ is dense so choose $\theset{f_n} \to f$ with $\norm{f_n - f}_1 \to 0$.
- Since $\theset{f_n}$ are compactly supported, choose $N_0\gg 1$ such that $f_n$ is zero outside of $B_{N_0}(\vector 0)$.
- Then
\[
N\geq N_0 \implies \int_{\abs x > N} \abs{f} &= \int_{\abs x > N} \abs{f - f_n + f_n} \\
&\leq \int_{\abs x > N} \abs{f-f_n} + \int_{\abs x > N} \abs{f_n} \\
&= \int_{\abs x > N} \abs{f-f_n} \\ 
&\leq \int_{\abs x > N} \norm{f-f_n}_1 \\
&= \norm{f_n-f}_1 \qty{\int_{\abs x > N} 1} \\
&\converges{n\to\infty}\to 0 \qty{\int_{\abs x > N} 1} \\
&= 0\\
&\converges{N\to\infty}\to 0
.\]


To see that this doesn't force $f(x)\to 0$ as $\abs{x} \to \infty$:

- Take $f(x)$ to be a train of rectangles of height 1 and area $1/2^j$ centered on even integers.
- Then $$\int_{\abs x > N} \abs{f} = \sum_{j=N}^\infty 1/2^j \converges{N\to\infty}\to 0$$ as the tail of a convergent sum. 
- However $f(x) = 1$ for infinitely many even integers $x > N$, so $f(x) \not\to 0$ as $\abs{x}\to\infty$.

### b

#### Solution 1 ("Trick")

- Since $f$ is decreasing on $[1, \infty)$, for any $t\in [x-n, x]$ we have
\[
x-n \leq t \leq x \implies f(x) \leq f(t) \leq f(x-n)
.\]

- Integrate over $[x, 2x]$, using monotonicity of the integral:
\[
\int_x^{2x} f(x) \,dt \leq 
\int_x^{2x} f(t) \,dt \leq 
\int_x^{2x} f(x-n) \,dt \\ 
\implies 
f(x) \int_x^{2x} \,dt \leq 
\int_x^{2x} f(t) \,dt \leq 
f(x-n) \int_x^{2x} \,dt  \\
\implies xf(x) \leq \int_x^{2x} f(t) \, dt \leq xf(x-n)
.\]

- By the Cauchy Criterion for integrals, $\lim_{x\to \infty} \int_x^{2x} f(t)~dt = 0$.
- So the LHS term $xf(x) \converges{x\to\infty}\to 0$.
- Since $x>1$, $\abs{f(x)} \leq \abs{xf(x)}$ 
- Thus $f(x) \converges{x\to\infty}\to 0$ as well.

#### Solution 2 (Variation on the Trick)

- Use mean value theorem for integrals:
\[
\int_x^{2x} f(t)\, dt = xf(c_x) \quad\text{for some $c_x \in [x, 2x]$ depending on $x$}
.\]

- Since $f$ is decreasing, 
\[
x\leq c_x \leq 2x 
&\implies f(2x)\leq f(c_x) \leq f(x) \\
&\implies 2xf(2x)\leq 2xf(c_x) \leq 2xf(x) \\
&\implies 2xf(2x)\leq 2x\int_x^{2x} f(t)\, dt \leq 2xf(x) \\
.\]

- By Cauchy Criterion, $\int_x^{2x} f \to 0$.
- So $2x f(2x) \to 0$, which by a change of variables gives $uf(u) \to 0$.
- Since $u\geq 1$, $f(u) \leq uf(u)$ so $f(u) \to 0$ as well.

#### Solution 3 (Contradiction)

Just showing $f(x) \converges{x\to \infty}\to 0$:

- Toward a contradiction, suppose not.
- Since $f$ is decreasing, it can not diverge to $+\infty$
- If $f(x) \to -\infty$, then $f\not\in L^1(\RR)$: choose $x_0 \gg 1$ so that $t\geq x_0 \implies f(t) < -1$, then 
- Then $t\geq x_0 \implies \abs{f(t)} \geq 1$, so
 \[
\int_1^\infty \abs{f} \geq \int_{x_0}^\infty \abs{f(t) } \, dt \geq \int_{x_0}^\infty 1 =\infty
 .\]

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
  \[
  \int_1^{\infty} \abs{f} \geq \int_{x_0}^\infty \abs{f} \geq \sum_{x_i \in S} \int_{x_i}^{2x_i} \abs{f(t)} \, dt \geq 
  \sum_{x_i \in S} \int_{x_i}^{2x_i} \abs{f(x_i)} &= \sum_{x_i \in S} x_i f(x_i) \to \infty
  .\]

- If $xf(x) \to L \neq 0$ for $0 < L< \infty$:
  - Fix $\eps> 0$, choose an infinite sequence $\theset{x_i}$ such that $L-\eps \leq x_i f(x_i) \leq L$ for all $i$.
\[
\int_1^\infty \abs{f} \geq \sum_S \int_{x_i}^{2x_i} \abs{f(t)}\,dt \geq \sum_S \int_{x_i}^{2x_i} f(x_i) \,dt = \sum_S x_i f(x_i) \geq \sum_S \qty{L-\eps} \to \infty
.\]
- If $xf(x) \to L \neq 0$ for $-\infty < L < 0$:
  - Fix $\eps> 0$, choose an infinite sequence $\theset{x_i}$ such that $L \leq x_i f(x_i) \leq L + \eps$ for all $i$.
\[
\int_1^\infty \abs{f} \geq \sum_S \int_{x_i}^{2x_i} \abs{f(t)}\,dt \geq \sum_S \int_{x_i}^{2x_i} f(x_i) \,dt = \sum_S x_i f(x_i) \geq \sum_S \qty{L} \to \infty
.\]

#### Solution 4 (Akos's Suggestion)

For $x\geq 1$, 
\[
\abs{xf(x)} = \abs{ \int_x^{2x} f(x) \, dt } \leq \int_x^{2x} \abs{f(x)} \, dt \leq \int_x^{2x} \abs{f(t)}\, dt \leq \int_x^{\infty} \abs{f(t)} \,dt \converges{x\to\infty}\to 0
\]
  where we've used 
  
  - Since $f$ is decreasing and $\lim_{x\to\infty}f(x) =0$ from part (a), $f$ is non-negative.
  - Since $f$ is positive and decreasing, for every $t\in[a, b]$ we have $\abs{f(a)} \leq \abs{f(t)}$.
  - By part (a), the last integral goes to zero.

#### Solution 5 (Peter's)

- Toward a contradiction, produce a sequence $x_i\to\infty$ with $x_i f(x_i) \to \infty$ and $x_if(x_i) > \eps > 0$, then
\[
\int f(x) \, dx 
&\geq \sum_{i=1}^\infty \int_{x_i}^{x_{i+1}} f(x) \, dx \\
&\geq \sum_{i=1}^\infty \int_{x_i}^{x_{i+1}} f(x_{i+1}) \, dx \\
&=    \sum_{i=1}^\infty f(x_{i+1}) \int_{x_i}^{x_{i+1}} \, dx \\
&\geq \sum_{i=1}^\infty (x_{i+1} - x_i) f(x_{i+1}) \\
&\geq \sum_{i=1}^\infty (x_{i+1} - x_i) {\eps \over x_{i+1}} \\
&= \eps \sum_{i=1}^\infty \qty{ 1 - {x_{i-1} \over x_i}} \to \infty
\]
  which can be ensured by passing to a subsequence where $\sum {x_{i-1} \over x_i} < \infty$.

### c

- No: take $f(x) = {1\over x\ln x}$
- Then by a $u\dash$substitution,
  \[
  \int_0^x f = \ln\qty{\ln (x)} \converges{x\to\infty}\to \infty
  \]
  is unbounded, so $f\not\in L^1([1, \infty))$.
- But 
  \[
  xf(x) = { 1 \over \ln(x)} \converges{x\to\infty} \to 0
  .\]



:::

## Fall 2019 # 5. $\done$

### a
Show that if $f$ is continuous with compact support on $\RR$, then 
\[
\lim _{y \rightarrow 0} \int_{\mathbb{R}}|f(x-y)-f(x)| d x=0
\]

### b 
Let $f\in L^1(\RR)$ and for each $h > 0$ let 
\[
\mathcal{A}_{h} f(x):=\frac{1}{2 h} \int_{|y| \leq h} f(x-y) d y
\]

i. Prove that $\left\|\mathcal{A}_{h} f\right\|_{1} \leq\|f\|_{1}$ for all $h > 0$.

ii. Prove that $\mathcal{A}_h f → f$ in $L^1(\RR)$ as $h → 0^+$.

\todo[inline]{Walk through.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- Continuity in $L^1$ (recall that DCT won't work! Notes 19.4, prove it for a dense subset first).
- Lebesgue differentiation in 1-dimensional case. See HW 5.6.
:::

### a

Choose $g\in C_c^0$ such that $\norm{f- g}_1 \to 0$.

By translation invariance, $\norm{\tau_h f - \tau_h g}_1 \to 0$.

Write
\[
\norm{\tau f - f}_1 
&= \norm{\tau_h f - g + g - \tau_h g + \tau_h g - f}_1 \\
&\leq \norm{\tau_h f - \tau_h g} + \norm{g - f} + \norm{\tau_h g - g} \\
&\to \norm{\tau_h g - g}
,\]

so it suffices to show that $\norm{\tau_h g - g} \to 0$ for $g\in C_c^0$.

Fix $\varepsilon > 0$.
Enlarge the support of $g$ to $K$ such that
\[
\abs{h} \leq 1 \text{ and } x \in K^c \implies \abs{g(x-h) - g(x)} = 0
.\]

By uniform continuity of $g$, pick $\delta \leq 1$ small enough such that 
$$
x\in K, ~\abs{h} \leq \delta \implies \abs{g(x-h) -g(x)} < \varepsilon
,$$

then
\[
\int_K \abs{g(x-h) - g(x)} \leq \int_K \varepsilon = \varepsilon \cdot m(K) \to 0.
\]

### b

We have
\[
\int_\RR \abs{A_h(f)(x)} ~dx 
&= \int_\RR \abs{\frac{1}{2h} \int_{x-h}^{x+h} f(y)~dy} ~dx \\
&\leq \frac{1}{2h} \int_\RR \int_{x-h}^{x+h} \abs{f(y)} ~dy ~dx    \\
&=_{FT} \frac{1}{2h} \int_\RR \int_{y-h}^{y+h} \abs{f(y)} ~\mathbf{dx} ~\mathbf{dy}    \\
&= \int_\RR \abs{f(y)} ~{dy} \\
&= \norm{f}_1
,\]

and (rough sketch)

\[
\int_\RR \abs{A_h(f)(x) - f(x)} ~dx 
&= \int_\RR \abs{ \left(\frac{1}{2h} \int_{B(h, x)} f(y)~dy\right) - f(x)}~dx \\
&= \int_\RR \abs{ \left(\frac{1}{2h} \int_{B(h, x)} f(y)~dy\right) - \frac{1}{2h}\int_{B(h, x)} f(x) ~dy}~dx \\
&\leq_{FT} \frac{1}{2h} \int_\RR  \int_{B(h, x)}\abs{ f(y-x) - f(x)} ~\mathbf{dx} ~\mathbf{dy} \\
&\leq \frac 1 {2h} \int_\RR \norm{\tau_x f - f}_1 ~dy \\
&\to 0 \quad\text{by (a)}
.\]

:::


## Fall 2017 # 3 $\done$
Let 
$$
S = \spanof_\CC\theset{\chi_{(a, b)} \suchthat a, b \in \RR},
$$
the complex linear span of characteristic functions of intervals of the form $(a, b)$.

Show that for every $f\in L^1(\RR)$, there exists a sequence of functions $\theset{f_n} \subset S$ such that 
\[
\lim _{n \rightarrow \infty}\left\|f_{n}-f\right\|_{1}=0
\]

\todo[inline]{Walk through.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- From homework: $E$ is Lebesgue measurable iff there exists a finite union of closed cubes $A$ such that $m(E\Delta A) < \varepsilon$.
:::

It suffices to show that $S$ is dense in simple functions, and since simple functions are *finite* linear combinations of characteristic functions, it suffices to show this for $\chi_A$ for $A$ a measurable set.

Let $s = \chi_{A}$.
By regularity of the Lebesgue measure, choose an open set $O \supseteq A$ such that $m(O\setminus A) < \varepsilon$.

$O$ is an open subset of $\RR$, and thus $O = \disjoint_{j\in \NN} I_j$ is a disjoint union of countably many open intervals.

Now choose $N$ large enough such that $m(O \Delta I_{N, n}) < \varepsilon = \frac 1 n$ where we define $I_{N, n} \definedas \disjoint_{j=1}^N I_j$.

Now define $f_n = \chi_{I_{N, n}}$, then
\[
\norm{s - f_n}_1 = \int \abs{\chi_A - \chi_{I_{N, n}}} = m(A \Delta I_{N, n}) \converges{n\to\infty}\longrightarrow 0
.\]

Since any simple function is a finite linear combination of $\chi_{A_i}$, we can do this for each $i$ to extend this result to all simple functions.
But simple functions are dense in $L^1$, so $S$ is dense in $L^1$.
:::



## Spring 2015 # 4 $\work$
Define
$$
f(x, y):=\left\{\begin{array}{ll}{\frac{x^{1 / 3}}{(1+x y)^{3 / 2}}} & {\text { if } 0 \leq x \leq y} \\ {0} & {\text { otherwise }}\end{array}\right.
$$

Carefully show that $f \in L^1(\RR^2)$.

## Fall 2014 # 3 $\work$
Let $f\in L^1(\RR)$. Show that
\[
\forall\varepsilon > 0 \exists \delta > 0 \text{ such that } \qquad 
m(E) < \delta 
\implies 
\int _{E} |f(x)| \, dx < \varepsilon
\]

## Spring 2014 # 1 $\work$

1. Give an example of a continuous $f\in L^1(\RR)$ such that $f(x) \not\to 0$ as$\abs x \to \infty$.

2. Show that if $f$ is *uniformly* continuous, then
\[
\lim_{\abs x \to \infty} f(x) = 0.
\]



# Fubini-Tonelli

## Spring 2020 # 4 $\done$

Let $f, g\in L^1(\RR)$. 
Argue that $H(x, y) \definedas f(y) g(x-y)$ defines a function in $L^1(\RR^2)$ and deduce from this fact that
\[
(f\ast g)(x) \definedas \int_\RR f(y) g(x-y) \,dy
\]
defines a function in $L^1(\RR)$ that satisfies 
\[
\norm{f\ast g}_1 \leq \norm{f}_1 \norm{g}_1
.\]

:::{.solution}
\hfill
:::{.concept}
\hfill
- Tonelli: non-negative and measurable yields measurability of slices and equality of iterated integrals
- Fubini: $f(x, y) \in L^1$ yields *integrable* slices and equality of iterated integrals
- F/T: apply Tonelli to $\abs{f}$; if finite, $f\in L^1$ and apply Fubini to $f$
:::

\[
\norm{H(x)}_1 
&= \int _\RR \abs{H(x, y)} \, dx \\
&= \int _\RR \abs{ \int_\RR f(y)g(x-y) \,dy } \, dx \\
&\leq \int _\RR \qty{ \int_\RR \abs{f(y)g(x-y)}  \, dy } \, dx \\
&= \int _\RR \qty{ \int_\RR \abs{f(y)g(x-y)}  \, dx} \, dy \quad\text{by Tonelli} \\
&= \int _\RR \qty{ \int_\RR \abs{f(y)g(t)}  \, dt} \, dy \quad\text{setting } t=x-y, \,dt = - dx \\
&= \int _\RR \qty{ \int_\RR \abs{f(y)}\cdot \abs{g(t)}  \, dt}\, dy \\
&= \int _\RR \abs{f(y)} \cdot \qty{ \int_\RR \abs{g(t)}  \, dt}\, dy \\
&\definedas \int _\RR \abs{f(y)} \cdot \norm{g}_1 \,dy \\
&= \norm{g}_1 \int _\RR \abs{f(y)} \,dy \\
&\definedas \norm{g}_1 \norm{f}_1  \\
&< \infty \qtext{by assumption}
.\]

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


:::



## Spring 2019 # 4 $\done$
Let $f$ be a non-negative function on $\RR^n$ and $\mathcal A = \{(x, t) ∈ \RR^n × \RR : 0 ≤ t ≤ f (x)\}$.

Prove the validity of the following two statements:

a. $f$ is a Lebesgue measurable function on $\RR^n \iff  \mathcal A$ is a Lebesgue measurable subset of $\RR^{n+1}$

b. If $f$ is a Lebesgue measurable function on $\RR^n$, then
\[
m(\mathcal{A})=\int _{\RR^{n}} f(x) d x=\int_{0}^{\infty} m\left(\left\{x \in \RR^{n}: f(x) \geq t\right\}\right) dt
\]

\todo[inline]{Add concepts.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- See S&S p.82.
:::

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
\[
\mathcal{A}_x \definedas \theset{t\in \RR \suchthat (x, t) \in \mathcal{A}} = [0, f(x)] \implies m(\mathcal A_x) = f(x) - 0 = f(x)
\]

- But $x \mapsto m(\mathcal A_x)$ is a measurable function, and is exactly the function $x \mapsto f(x)$, so $f$ is measurable.


### b

- Note
\[
\mathcal{A} &= \theset{(x, t) \in \RR^n\cross \RR \suchthat 0 \leq t \leq f(x)} 
\\
\mathcal{A}_t &= \theset{x
\in \RR^n \suchthat t\leq f(x) }
.\]

- Then
\[
\int_{\RR^n} f(x) ~dx 
&= \int_{\RR^n} \int_0^{f(x)} 1 ~dt~dx \\
&= \int_{\RR^n} \int_{0}^\infty \chi_\mathcal{A} ~dt~dx \\
&\overset{F.T.}= \int_{0}^\infty \int_{\RR^n} \chi_\mathcal{A} ~dx~dt\\
&= \int_0^\infty m(\mathcal{A}_t) ~dt
,\]
  where we just use that $\int \int \chi_\mathcal{A} = m(\mathcal{A})$

- By F.T., all of these integrals are equal. 
  \todo[inline]{Why is FT justified.}

:::

## Fall 2018 # 5 $\done$
Let $f \geq 0$ be a measurable function on $\RR$.
Show that
\[
\int _{\RR} f = \int _{0}^{\infty} m(\{x: f(x)>t\}) dt
\]

:::{.solution}
\hfill
:::{.concept}
\hfill
- Claim: If $E\subseteq \RR^a \cross \RR^b$ is a measurable set, then for almost every $y\in \RR^b$, the slice $E^y$ is measurable and
\[
m(E) = \int_{\RR^b} m(E^y) \,dy
.\]
  - Set $g = \chi_E$, which is non-negative and measurable, so apply Tonelli.
  - Conclude that $g^y = \chi_{E^y}$ is measurable, the function $y\mapsto \int g^y(x)\, dx$ is measurable, and $\int \int g^y(x)\,dx \,dy = \int g$.
  - But $\int g = m(E)$ and $\int\int g^y(x) \,dx\,dy = \int m(E^y)\,dy$.
:::

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
\[
E^t &\definedas \theset{x\in \RR^n \suchthat (x, t) \in E} = \theset{x\in \RR^n \suchthat 0 \leq t < f(x)} \\
E^x &\definedas \theset{t\in \RR \suchthat (x, t) \in E} = \theset{t\in \RR \suchthat 0 \leq t \leq f(x)} = [0, f(x)]
.\]
  - $E_t$ is precisely the set that appears in the original RHS integrand.
  - $m(E^x) = f(x)$.
- Claim: $\chi_E$ satisfies the conditions of Tonelli, and thus $m(E) = \int \chi_E$ is equal to any iterated integral.
  - Non-negative: clear since $0\leq \chi_E \leq 1$
  - Measurable: characteristic functions of measurable sets are measurable.

- Conclude:
  1. For almost every $x$, $E^x$ is a measurable set, $x\mapsto m(E^x)$ is a measurable function, and $m(E) = \int_{\RR^n} m(E^x) \, dx$ 
  2. For almost every $t$, $E^t$ is a measurable set, $t\mapsto m(E^t)$ is a measurable function, and $m(E) = \int_{\RR} m(E^t) \, dt$ 
- On one hand,
\[
m(E) 
&= \int_{\RR^{n+1}} \chi_E(x, t) \\
&= \int_{\RR} \int_{\RR^n} \chi_E(x, t) \,dt \,dx \quad\text{by Tonelli}\\
&= \int_{\RR^n} m(E^x) \,dx \quad\text{first conclusion}\\
&= \int_{\RR^n} f(x) \,dx 
.\]
- On the other hand,
\[
m(E) 
&= \int_{\RR^{n+1}} \chi_E(x, t) \\
&= \int_\RR \int_{\RR^n} \chi_E(x, t) \, dx \,dt \quad\text{by Tonelli} \\
&= \int_\RR m(E^t) \,dt \quad\text{second conclusion}
.\]

- Thus
\[
\int_{\RR^n} f \,dx = m(E) = \int_\RR m(E^t) \,dt = \int_\RR m\qty{\theset{x\suchthat f(x) > t}}
.\]

:::



## Fall 2015 # 5 $\work$
Let $f, g \in L^1(\RR)$ be Borel measurable.

1. Show that 
  - The function $$F(x, y) \definedas f(x-y) g(y)$$ is Borel measurable on $\RR^2$, and
  - For almost every $y\in \RR$, $$F_y(x) \definedas f(x-y)g(y)$$ is integrable with respect to $y$.

2. Show that $f\ast g \in L^1(\RR)$ and
\[
\|f * g\|_{1} \leq \|f\|_{1} \|g\|_{1}
\]

## Spring 2014 # 5 $\work$
Let $f, g \in L^1([0, 1])$ and for all $x\in [0, 1]$ define
\[
F(x) \definedas \int _{0}^{x} f(y) \, dy 
\qtext{and}
G(x)\definedas \int _{0}^{x} g(y) \, dy.
\]

Prove that
\[
\int _{0}^{1} F(x) g(x) \, dx = 
F(1) G(1) - \int _{0}^{1} f(x) G(x) \, dx
\]

# $L^2$ and Fourier Analysis

## Spring 2020 # 6 $\done$

### a
Show that
\[
L^2([0, 1]) \subseteq L^1([0, 1]) \qtext{and} \ell^1(\ZZ) \subseteq \ell^2(\ZZ)
.\]

### b
For $f\in L^1([0, 1])$ define
\[
\hat{f}(n) \definedas \int _0^1 f(x) e^{-2\pi i n x} \, dx
.\]

Prove that if $f\in L^1([0, 1])$ and $\theset{\hat f(n)} \in \ell^1(\ZZ)$ then
\[
S_N f(x) \definedas \sum_{\abs n \leq N} \hat f (n) e^{2 \pi i n x}
.\]
converges uniformly on $[0, 1]$ to a continuous function $g$ such that $g = f$ almost everywhere.

> Hint: One approach is to argue that if $f\in L^1([0, 1])$ with $\theset{\hat f (n)} \in \ell^1(\ZZ)$ then $f\in L^2([0, 1])$.

:::{.solution}
\hfill
:::{.concept}
\hfill
- For $e_n(x) \definedas e^{2\pi i n x}$, the set $\theset{e_n}$ is an orthonormal basis for $L^2([0, 1])$.
- For any orthonormal sequence in a Hilbert space, we have Bessel's inequality:
  \[
  \sum_{k=1}^{\infty}\left|\left\langle x, e_{k}\right\rangle\right|^{2} \leq\|x\|^{2}
  .\]
- When $\theset{e_n}$ is a basis, the above is an *equality* (Parseval)
- Arguing uniform convergence: since $\theset{\hat f(n)} \in \ell^1(\ZZ)$, we should be able to apply the $M$ test.
:::

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
\[
\sum_{k\in \ZZ} \abs{c_k}^2 
&= \sum_{c_k\in S} \abs{c_k}^2 + \sum_{c_k \in S^c} \abs{c_k}^2 \\
&\leq \sum_{c_k\in S} \abs{c_k} + \sum_{c_k \in S^c} \abs{c_k}^2 \\
&\leq \sum_{k\in \ZZ} \abs{c_k} + \sum_{c_k \in S^c} \abs{c_k}^2 \quad\text{since the $\abs{c_k}$ are all positive} \\
&= \norm{\vector c}_{\ell^1} + \sum_{c_k \in S^c} \abs{c_k}^2 \\
&\leq \norm{\vector c}_{\ell^1} + \abs{S^c}\cdot N \\
&< \infty
.\]

Claim: $L^2([0, 1]) \subseteq L^1([0, 1])$.

- It suffices to show that $\int \abs{f}^2 < \infty \implies \int \abs{f} < \infty$.
- Define $S = \theset{x\in [0, 1] \suchthat \abs{f(x)} \leq 1}$, then $x\in S^c \implies \abs{f(x)}^2 \geq \abs{f(x)}$.

- Break up the integral:
\[
\int_\RR \abs f 
&= \int_S \abs f + \int_{S^c} \abs f \\
&\leq \int_S \abs{f} + \int_{S^c} \abs{f}^2 \\
&\leq \int_S \abs{f} + \norm{f}_2 \\
&\leq \sup_{x\in S}\theset{\abs{f(x)}} \cdot \mu(S) + \norm{f}_2 \\
&= 1 \cdot \mu(S) + \norm{f}_2 \quad\text{by definition of } S\\
&\leq 1 \cdot \mu([0, 1]) + \norm{f}_2 \quad\text{since } S\subseteq [0, 1] \\
&= 1 + \norm{f}_2 \\
&< \infty
.\]


> Note: this proof shows $L^2(X) \subseteq L^1(X)$ whenever $\mu(X) < \infty$.
:::


## Fall 2017 # 5 $\done$
Let $\phi$ be a compactly supported smooth function that vanishes outside of an interval $[-N, N]$ such that $\int _{\RR} \phi(x) \, dx = 1$.

For $f\in L^1(\RR)$, define
\[
K_{j}(x) \definedas j \phi(j x), 
\qquad 
f \ast K_{j}(x) \definedas \int_{\RR} f(x-y) K_{j}(y) \, dy
\]
and prove the following:

1. Each $f\ast K_j$ is smooth and compactly supported.

2. 
\[
\lim _{j \to \infty} \norm{f * K_{j}-f}_{1} = 0
\]

> Hint:
\[
\lim _{y \to 0} \int _{\RR} |f(x-y)-f(x)| dy = 0
\]

\todo[inline]{Add concepts.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- ?
:::


### a

**Lemma:** If $\phi \in C_c^1$, then
$(f \ast \phi)' = f \ast \phi'$ almost everywhere.

*Silly Proof:*

\[
\mathcal{F}(
	(f \ast \phi)'
 )
&= 2\pi i \xi ~\mathcal{F}(f\ast \phi) \\
&= 2\pi i \xi ~ \mathcal{F}(f) ~ \mathcal{F}(\phi) \\
&= \mathcal{F}(f) \cdot \left( 2\pi i \xi ~\mathcal{F}(\phi)\right) \\
&= \mathcal{F}(f) \cdot \mathcal{F}(\phi') \\
&= \mathcal{F}(f\ast \phi')
.\]

*Actual proof*:

\[
(f\ast \phi)'(x)
&= (\phi\ast f)'(x) \\
&= \lim_{h\to 0} \frac{(\phi\ast f)'(x+h) - (\phi\ast f)'(x)}{h} \\
&= \lim_{h\to 0} \int \frac{\phi(x + h - y) - \phi(x - y)}{h} f(y) \\
&\overset{DCT}=  \int \lim_{h\to 0} \frac{\phi(x + h - y) - \phi(x - y)}{h} f(y) \\
&= \int \phi'(x-y) f(y) \\
&= (\phi' \ast f)(x) \\
&= (f \ast \phi')(x)
.\]
 

 To see that the DCT is justified, we can apply the MVT on the interval $[0, h]$ to $f$ to obtain

\[
\frac{\phi(x + h - y) - \phi(x - y)}{h}
&= \phi'(c) \quad c\in [0, h]
,\]
 
and since $\phi'$ is continuous and compactly supported, $\phi'$ is bounded by some $M < \infty$ by the extreme value theorem and thus
\[
\int \abs{\frac{\phi(x + h - y) - \phi(x - y)}{h} f(y)} 
&= \int \abs{\phi'(c) f(y)} \\
&\leq \int \abs{M}\abs{f} \\
&= \abs{M} \int \abs{f} < \infty
,\]

since $f\in L^1$ by assumption, so we can take $g\definedas \abs{M} \abs{f}$ as the dominating function.

Applying this theorem infinitely many times shows that $f\ast \phi$ is smooth.

To see that $f\ast \phi$ is compactly supported, approximate $f$ by a *continuous* compactly supported function $h$, so $\norm{h - f}_1 \converges{L^1}\to 0$. 

Now let $g_x(y) = \phi(x-y)$, and note that $\mathrm{supp}(g) = x - \mathrm{supp}(\phi)$ which is still compact.
 
But since $\mathrm{supp}(h)$ is bounded, there is some $N$ such that 
$$
\abs{x} > N \implies A_x\definedas \mathrm{supp}(h) \intersect \mathrm{supp}(g_x) = \emptyset
$$

and thus 
\[
(h\ast \phi)(x) 
&= \int_\RR \phi(x-y) h(y)~dy \\
&= \int_{A_x} g_x(y) h(y) \\
&= 0
,\]

so $\theset{x \suchthat f\ast g(x) = 0}$ is open, and its complement is closed and bounded and thus compact.

### b

\[
\norm{f\ast K_j - f}_1 
&= \int \abs{\int f(x-y) K_j(y) ~dy  - f(x)}~dx \\
&= \int \abs{\int f(x-y) K_j(y) ~dy  - \int f(x) K_j(y) ~ dy}~dx \\
&= \int \abs{\int ( f(x-y) - f(x) ) K_j(y) ~dy } ~dx \\
&\leq \int \int \abs{(f(x-y) - f(x))} \cdot \abs{K_j(y)} ~ dy~dx \\
&\overset{FT}= \int \int \abs{(f(x-y) - f(x))} \cdot \abs{K_j(y)} \mathbf{~ dx~dy}\\
&= \int \abs{K_j(y)} \left( \int \abs{(f(x-y) - f(x))}  ~ dx\right) ~dy \\
&= \int \abs{K_j(y)} \cdot \norm{f - \tau_y f}_1 ~dy
.\]

We now split the integral up into pieces. 

1. Chose $\delta$ small enough such that
 $\abs{y} < \delta \implies \norm{f - \tau_y f}_1 < \varepsilon$ by continuity of translation in $L^1$, and

2. Since $\phi$ is compactly supported, choose $J$ large enough such that
$$
j > J \implies \int_{\abs{y} \geq \delta} \abs{K_j(y)} ~dy 
= \int_{\abs{y} \geq \delta} \abs{j\phi(jy)} = 0
$$

Then
\[
\norm{f\ast K_j - f}_1 
&\leq 
\int \abs{K_j(y)} \cdot \norm{f - \tau_y f}_1 ~dy \\
&= \int_{\abs y < \delta} \abs{K_j(y)} \cdot \norm{f - \tau_y f}_1 ~dy 
+ \int_{\abs y \geq  \delta} \abs{K_j(y)} \cdot \norm{f - \tau_y f}_1 ~dy \\
&= \varepsilon \int_{\abs y \geq  \delta} \abs{K_j(y)} + 0 \\
&\leq \varepsilon(1) \to 0
.\]


:::



## Spring 2017 # 5 $\work$
Let $f, g \in L^2(\RR)$. 
Prove that the formula
\[
h(x) \definedas \int _{-\infty}^{\infty} f(t) g(x-t) \, dt
\]
defines a uniformly continuous function $h$ on $\RR$.

## Spring 2015 # 6 $\work$
Let $f \in L^1(\RR)$ and $g$ be a bounded measurable function on $\RR$.

1. Show that the convolution $f\ast g$ is well-defined, bounded, and uniformly continuous on $\RR$.
2. Prove that one further assumes that $g \in C^1(\RR)$ with bounded derivative, then $f\ast g \in C^1(\RR)$ and
\[
\frac{d}{d x}(f * g)=f *\left(\frac{d}{d x} g\right)
\]

## Fall 2014 # 5 $\work$

1. Let $f \in C_c^0(\RR^n)$, and show
\[
\lim _{t \to 0} \int_{\RR^n} |f(x+t) - f(x)| \, dx = 0
.\]

2. Extend the above result to $f\in L^1(\RR^n)$ and show that
\[
f\in L^1(\RR^n), \quad g\in L^\infty(\RR^n) \quad
\implies f \ast g \text{ is bounded and uniformly continuous. }
\]



# Functional Analysis: General

## Fall 2019 # 4 $\done$
Let $\{u_n\}_{n=1}^∞$ be an orthonormal sequence in a Hilbert space $\mathcal{H}$.

### a 
Prove that for every $x ∈ \mathcal H$ one has 
\[
\displaystyle\sum_{n=1}^{\infty}\left|\left\langle x, u_{n}\right\rangle\right|^{2} \leq\|x\|^{2}
\]

### b
Prove that for any sequence $\{a_n\}_{n=1}^\infty \in \ell^2(\NN)$ there exists an element $x\in\mathcal H$ such that 
\[
a_n = \inner{x}{u_n} \text{ for all } n\in \NN
\]
and
\[
\norm{x}^2 = \sum_{n=1}^{\infty}\left|\left\langle x, u_{n}\right\rangle\right|^{2}
\]

:::{.solution}
\hfill
:::{.concept}
\hfill
- Bessel's Inequality
- Pythagoras
- Surjectivity of the Riesz map
- Parseval's Identity
- Trick -- remember to write out finite sum $S_N$, and consider $\norm{x - S_N}$.
:::

### a

**Claim:**
\[
0 \leq \left\|x-\sum_{n=1}^{N}\left\langle x, u_{n}\right\rangle u_{n}\right\|^{2}
&= \|x\|^{2}-\sum_{n=1}^{N}\left|\left\langle x, u_{n}\right\rangle\right|^{2} \\ 
&\implies
\sum_{n=1}^{\infty}\left|\left\langle x, u_{n}\right\rangle\right|^{2} \leq\|x\|^{2}
.\]

*Proof:*
Let $S_N = \sum_{n=1}^N \inner{x}{u_n} u_n$. 
Then
\[
0 
&\leq \norm{x - S_N}^2 \\ 
&= \inner{x - S_n}{x - S_N} \\
&= \norm{x}^2 - \sum_{n=1}^N \abs{\inner{x}{u_n}}^2 \\
&\mapsvia{N\to\infty} \norm{x}^2 - \sum_{n=1}^N \abs{\inner{x}{u_n}}^2
.\]


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

:::

## Spring 2019 # 5 $\done$

### a  
Show that $L^2([0, 1]) ⊆ L^1([0, 1])$ and argue that $L^2([0, 1])$ in fact forms a dense subset of $L^1([0, 1])$.

### b  
Let $Λ$ be a continuous linear functional on $L^1([0, 1])$.
  
Prove the Riesz Representation Theorem for $L^1([0, 1])$ by following the steps below:

i. Establish the existence of a function $g ∈ L^2([0, 1])$ which represents $Λ$ in the sense that
  \[
  Λ(f ) = f (x)g(x) dx \text{ for all } f ∈ L^2([0, 1]).
  \]

  > Hint: You may use, without proof, the Riesz Representation Theorem for $L^2([0, 1])$.

ii. Argue that the $g$ obtained above must in fact belong to $L^∞([0, 1])$ and represent $Λ$ in the sense that
  \[
  \Lambda(f)=\int_{0}^{1} f(x) \overline{g(x)} d x \quad \text { for all } f \in L^{1}([0,1])
  \]
  with
  \[
  \|g\|_{L^{\infty}([0,1])} = \|\Lambda\|_{L^{1}([0,1])\dual}
  \]

:::{.solution}
\hfill
:::{.concept}
\hfill
- Holders' inequality: $\norm{fg}_1 \leq \norm{f}_p \norm{f}_q$
- Riesz Representation for $L^2$: If $\Lambda \in (L^2)\dual$ then there exists a unique $g\in L^2$ such that $\Lambda(f) = \int fg$.
- $\norm{f}_{L^\infty(X)} \definedas \inf \theset{t\geq 0 \suchthat \abs{f(x)} \leq t \text{ almost everywhere} }$.
- **Lemma**:  $m(X) < \infty \implies L^p(X) \subset L^2(X)$.

  :::{.proof}
  \hfill
  - Write Holder's inequality as $\norm{fg}_1 \leq \norm{f}_a \norm{g}_b$ where $\frac 1 a + \frac 1 b = 1$, then
  \[
  \norm{f}_p^p = \norm{\abs f^p}_1 \leq \norm{\abs f^p}_a ~\norm{1}_b
  .\]

  - Now take $a = \frac 2 p$ and this reduces to 
  \[
  \norm{f}_p^p &\leq \norm{f}_2^p ~m(X)^{\frac 1 b} \\
  \implies \norm{f}_p &\leq \norm{f}_2 \cdot O(m(X)) < \infty
  .\]
  :::
:::


### a

- Note $X = [0, 1] \implies m(X) = 1$.
- By Holder's inequality with $p=q=2$, 
\[
\norm{f}_1 = \norm{f\cdot 1}_1 \leq \norm{f}_2 \cdot \norm{1}_2 = \norm{f}_2 \cdot m(X)^{\frac 1 2} = \norm{f}_2,
\]

- Thus $L^2(X) \subseteq L^1(X)$ 
- Since they share a common dense subset (simple functions) $L^2$ is dense in $L^1$ 
  \todo[inline]{What theorem is this using?}

### b

Let $\Lambda \in L^1(X)\dual$ be arbitrary.

#### 1: Existence of $g$ Representing $\Lambda$.

Let $f\in L^2\subseteq L^1$ be arbitrary.

Claim: $\Lambda\in L^1(X)\dual \implies \Lambda \in L^2(X)\dual$.

- Suffices to show that $\norm{\Gamma}_{L^2(X)\dual} \definedas \sup_{\norm{f}_2 = 1} \abs{\Gamma(f)} < \infty$, since bounded implies continuous.

- By the lemma, $\norm{f}_1 \leq C\norm{f}_2$ for some constant $C \approx m(X)$.

- Note $$\norm{\Lambda}_{L^1(X)\dual} \definedas \displaystyle\sup_{\norm{f}_1 = 1} \abs{\Lambda(f)}$$

- Define $\hat f = {f\over \norm{f}_1}$ so $\norm{\hat f}_1 = 1$

- Since $\norm{\Lambda}_{1\dual}$ is a supremum over *all* $f \in L^1(X)$ with $\norm{f}_1 =1$, 
\[
\abs{\Lambda(\hat f)} \leq \norm{\Lambda}_{(L^1(X))\dual}
,\]

- Then
\[
\frac{\abs{\Lambda(f)}}{\norm{f}_1} &= \abs{\Lambda(\hat f)} \leq \norm{\Lambda}_{L^1(X)\dual} \\
\implies \abs{\Lambda(f)} 
&\leq \norm{\Lambda}_{1\dual} \cdot \norm{f}_1 \\
&\leq \norm{\Lambda}_{1\dual} \cdot C \norm{f}_2 < \infty \quad\text{by assumption}
,\]

- So $\Lambda \in (L^2)\dual$.

Now apply Riesz Representation for $L^2$: there is a $g \in L^2$ such that $$f\in L^2 \implies \Lambda(f) = \inner{f}{g} \definedas \int_0^1 f(x) \bar{g(x)}\, dx.$$

#### 2: $g$ is in $L^\infty$

- It suffices to show $\norm{g}_{L^\infty(X)} < \infty$.
- Since we're assuming $\norm{\Gamma}_{L^1(X)\dual} < \infty$, it suffices to show the stated equality. 
  \todo[inline]{Is this assumed..? Or did we show it..?}

- Claim: $\norm{\Lambda}_{L^1(X)\dual} =\norm{g}_{L^\infty(X)}$
  - The result will follow since $\Lambda$ was assumed to be in $L^1(X)\dual$, so $\norm{\Lambda}_{L^1(X)\dual} < \infty$.
  - $\leq$: 
  \[
  \norm{\Lambda}_{L^1(X)\dual} 
  &= \sup_{\norm{f}_1 = 1} \abs{\Lambda(f)} \\
&= \sup_{\norm{f}_1 = 1} \abs{\int_X f \bar g} \quad\text{by (i)}\\
  &= \sup_{\norm{f}_1 = 1} \int_X \abs{f \bar g} \\
  &\definedas \sup_{\norm{f}_1 = 1} \norm{fg}_1 \\
  &\leq \sup_{\norm{f}_1 = 1} \norm{f}_1 \norm{g}_\infty \quad\text{by Holder with } p=1,q=\infty\\
  &= \norm{g}_\infty
  ,\]

  - $\geq$:

    - Suppose toward a contradiction that $\norm{g}_\infty > \norm{\Lambda}_{1\dual}$.

    - Then there exists some $E\subseteq X$ with $m(E) > 0$ such that $$x\in E \implies \abs{g(x)} > \norm{\Lambda}_{L^1(X)\dual}.$$

    - Define 
    \[
    h = \frac{1}{m(E)} \frac{\overline{g}}{\abs g} \chi_E
    .\]
  
    - Note $\norm{h}_{L^1(X)} = 1$.
    
    - Then
    \[
    \Lambda(h) &= \int_X hg \\
    &\definedas \int_X \frac{1}{m(E)} \frac{g \overline g}{\abs g} \chi_E \\
    &= \frac{1}{m(E)} \int_E \abs{g} \\
    &\geq \frac{1}{m(E)} \norm{g}_\infty m(E) \\
    &= \norm{g}_\infty \\
    &> \norm{\Lambda}_{L^1(X)\dual}
    ,\]
      a contradiction since $\norm{\Lambda}_{L^1(X)\dual}$ is the supremum over all $h_\alpha$ with $\norm{h_\alpha}_{L^1(X)} = 1$.

:::



## Spring 2016 # 6 $\work$
Without using the Riesz Representation Theorem, compute
\[
\sup \left\{\left|\int_{0}^{1} f(x) e^{x} d x\right| \suchthat f \in L^{2}([0,1], m),~~ \|f\|_{2} \leq 1\right\}
\]

## Spring 2015 # 5 $\work$
Let $\mathcal H$ be a Hilbert space.

1. Let $x\in \mathcal H$ and $\theset{u_n}_{n=1}^N$ be an orthonormal set.
  Prove that the best approximation to $x$ in $\mathcal H$ by an element in $\spanof_\CC\theset{u_n}$ is given by
  $$
  \hat x \definedas \sum_{n=1}^N \inner{x}{u_n}u_n.
  $$
2. Conclude that finite dimensional subspaces of $\mathcal H$ are always closed.

## Fall 2015 # 6 $\work$
Let $f: [0, 1] \to \RR$ be continuous.
Show that
\[
\sup \left\{\|f g\|_{1} \suchthat g \in L^{1}[0,1],~~ \|g\|_{1} \leq 1\right\}=\|f\|_{\infty}
\]

## Fall 2014 # 6 $\work$
Let $1 \leq p,q \leq \infty$ be conjugate exponents, and show that
\[
f \in L^p(\RR^n) \implies \|f\|_{p} = \sup _{\|g\|_{q}=1}\left|\int f(x) g(x) d x\right|
\]

# Functional Analysis: Banach Spaces

## Spring 2019 # 1 $\done$
Let $C([0, 1])$ denote the space of all continuous real-valued functions on $[0, 1]$.
  
a. Prove that $C([0, 1])$ is complete under the uniform norm $\norm{f}_u := \displaystyle\sup_{x\in [0,1]} |f (x)|$.

b. Prove that $C([0, 1])$ is not complete under the $L^1\dash$norm $\norm{f}_1 = \displaystyle\int_0^1 |f (x)| ~dx$.

\todo[inline]{Add concepts.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- ?
:::


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
  \[
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
  .\]

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

\todo[inline]{show that $\int_0^1 \abs{f_n(x) - f_m(x)} \,dx \to 0$ rigorously, show that no $g\in L^1([0, 1])$ can converge to this indicator function.}

:::



## Spring 2017 # 6 $\done$
Show that the space $C^1([a, b])$ is a Banach space when equipped with the norm
\[
\|f\|:=\sup _{x \in[a, b]}|f(x)|+\sup _{x \in[a, b]}\left|f^{\prime}(x)\right|.
\]

\todo[inline]{Add concepts.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- See <https://math.stackexchange.com/questions/507263/prove-that-c1a-b-with-the-c1-norm-is-a-banach-space/>
:::

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
:::



## Fall 2017 # 6 $\done$
Let $X$ be a complete metric space and define a norm
$$
\|f\|:=\max \{|f(x)|: x \in X\}.
$$

Show that $(C^0(\RR), \norm{\wait} )$ (the space of continuous functions $f: X\to \RR$) is complete.

\todo[inline]{Add concepts.}
\todo[inline]{Shouldn't this be a supremum? The max may not exist?}
\todo[inline]{Review and clean up.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- ?
:::


Let $\theset{f_k}$ be a Cauchy sequence, so $\norm{f_k} < \infty$ for all $k$.
Then for a fixed $x$, the sequence $f_k(x)$ is Cauchy in $\RR$ and thus converges to some $f(x)$, so define $f$ by $f(x) \definedas \lim_{k\to\infty} f_k(x)$.

Then $\norm{f_k - f} = \max_{x\in X}\abs{f_k(x) - f(x)} \converges{k\to\infty}\to 0$, and thus $f_k \to f$ uniformly and thus $f$ is continuous. It just remains to show that $f$ has bounded norm.

Choose $N$ large enough so that $\norm{f - f_N} < \varepsilon$, and write $\norm{f_N} \definedas M < \infty$

\[
\norm{f} \leq \norm{f - f_N} + \norm{f_N} < \varepsilon + M < \infty
.\]
:::
