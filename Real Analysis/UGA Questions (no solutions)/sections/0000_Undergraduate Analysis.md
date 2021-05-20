# Undergraduate Analysis: Uniform Convergence

## Fall 2018 # 1 $\done$
Let $f(x) = \frac 1 x$.
Show that $f$ is uniformly continuous on $(1, \infty)$ but not on $(0,\infty)$.

:::{.concept}
\envlist
- Uniform continuity:
\[  
\forall \varepsilon>0, \exists \delta(\eps)>0 \quad\text{such that}\quad \abs{x-y}<\delta \implies \abs{f(x) - f(y)} < \eps
.\]
- Negating uniform continuity:
  $\exists \eps > 0$ such that $\forall \delta(\eps)$ there exist $x, y$ such that $\abs{x-y} < \delta$ *and* $\abs{f(x) - f(y)} > \eps$.

- Archimedean property: for all $x,y\in \RR$ there exists an $n \in \NN$ such that $nx>y$.
  Take $x=\eps, y=1$, so $n\eps > 1$ and ${1\over n} < \eps$.
:::

:::{.solution}

:::{.claim}
$f(x) = \frac 1 x$ is uniformly continuous on $(c, \infty)$ for any $c > 0$.
:::

:::{.proof title="of claim"}
\envlist

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
.\]

:::

:::{.claim}
$f$ is *not* uniformly continuous when $c=0$.
:::

:::{.proof title="of claim"}
\envlist

- Take $\varepsilon < 1$, and let $\delta = \delta(\eps)$ be arbitrary.
- Let $x_n = \frac 1 n$ for $n\geq 1$.
- Choose $n$ large enough such that ${1\over n} < \delta$, then
\[
\abs{x_n - x_{n+1}} = \frac 1 n - \frac 1 {n+1} = {1\over n(n+1) } < {1\over n} < \delta
,\]
  - Why this can be done: by the Archimedean property of $\RR$, for any $\delta\in \RR$, one can choose
  choose $n$ such that $n\delta > 1$.
  We've also used that $n+1 > 1$ so ${1\over n+1}< 1$
- Note that $f(x_n) = n$, so
\[
\abs{f(x_{n+1}) - f(x_{n})} = (n+1) - n = 1 > \varepsilon
.\]

:::


:::


## Fall 2017 # 1 $\done$
Let 
\[
f(x) = \sum _{n=0}^{\infty} \frac{x^{n}}{n !}.
\]

Describe the intervals on which $f$ does and does not converge uniformly.

:::{.concept}
\envlist
- $f_N\to f$ uniformly $\iff$ $\norm{f_N - f}_\infty \to 0$.
  - Applied to sums: 
  \[
\sum_{0 \leq k\leq N} f_n \converges{u}\to \sum_{k\geq 0} f_n \iff \norm{\sum_{k\geq N+1} f_n }_{\infty} \to 0
  .\]
- $\sum_{n=0}^\infty c_n x^n \definedas \lim_{N\to \infty} \sum_{n=0}^N c_n x^n$
  - I.e. an infinite sum is defined as the pointwise limit of its partial sums.
- If $\sum_{n=0}^\infty f_n(x)$ converges uniformly on a set $A$, then $\sup_{x\in A} \abs{f_n(x)} = \norm{f_n}_{\infty, A} \to 0$.
- $M\dash$test: if $f_n:A \to\CC$ with $\norm{f_n}_\infty < M_n$ and $\sum M_n < \infty$, then $\sum f_n$ converges uniformly and absolutely.
  - If the $f_n$ are continuous, the uniform limit theorem implies $\sum f_n$ is continuous.
:::

:::{.solution}
\envlist

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

  - Note: we've used that $e^x$ is equal to its power series expansion.

- This argument shows that $f$ converges on any bounded set.


:::{.claim}
$f$ does not converge on $\RR$.
:::

- This follows by small (sup norm) tails for sequences of functions: $\sum f_k$ converging uniformly on $A$ implies $\norm{f_k}_{\infty, A}\converges{k\to\infty}\too 0$.
- Take $B_N$ a ball of radius $N$ about 0, then for $N>1$,
\[
\norm{x^k/k!}_{\infty, B_N} = N^k/k! \converges{N\to\infty}\too \infty
.\]
:::

## Fall 2014 # 1 $\done$
Let $\theset{f_n}$ be a sequence of continuous functions such that $\sum f_n$ converges uniformly.

Prove that $\sum f_n$ is also continuous.


:::{.concept}
\envlist

- The uniform limit theorem.
- $\eps/3$ trick.
:::

:::{.solution}
\envlist

:::{.claim}
If $F_N\to F$ uniformly with each $F_N$ continuous, then $F$ is continuous.
:::

:::{.proof title="of claim"}
\envlist

- Follows from an $\varepsilon/3$ argument: 
  \[  
  \abs{F(x) - F(y} \leq 
  \abs{F(x) - F_N(x)} + \abs{F_N(x) - F_N(y)} + \abs{F_N(y) - F(y)} 
  \leq \eps \to 0
  .\]

  - The first and last $\eps/3$ come from uniform convergence of $F_N\to F$.
  - The middle $\eps/3$ comes from continuity of each $F_N$.

:::

- Now setting $F_N\definedas \sum_{n=1}^N f_n$ yields a finite sum of continuous functions, which is continuous.
- Each $F_N$ is continuous and $F_N\to F$ uniformly, so $F$ is continuous.

:::

## Spring 2017 # 4 $\done$
Let $f(x, y)$ on $[-1, 1]^2$ be defined by 
$$
f(x, y) = \begin{cases}
\frac{x y}{\left(x^{2}+y^{2}\right)^{2}} & (x, y) \neq (0, 0) \\
0 & (x, y) = (0, 0)
\end{cases}
$$
Determine if $f$ is integrable.

:::{.concept}
\envlist
- Just Calculus.
- $1/r$ is not integrable on $(0, 1)$.
:::

:::{.solution}
Switching to polar coordinates and integrating over the quarter of the unit disc $D \intersect Q_1 \subseteq I^2$ in quadrant 1, we have
\[
\int_{I^2} f \, dA
&\geq \int_D f \, dA \\
&= \int_0^{\pi/2} \int_0^1 \frac{r^2 \cos(\theta)\sin(\theta)}{r^4} ~r~\dr\dtheta  \\
&= \int_0^{\pi/2} \int_0^1 \frac{\cos(\theta)\sin(\theta)}{r} \dr\dtheta  \\
&= \qty{ \int_0^1 {1\over r } \dr} \qty{ \int_0^{\pi/2} \cos(\theta)\sin(\theta) \dtheta }  \\
&= \qty{ \int_0^1 {1\over r } \dr} \qty{ \int_0^{1} u \du }  && u=\sin(\theta)\\
&= {1\over 2}\qty{ \int_0^1 {1\over r } \dr} \\
&\too \infty
.\]
:::

## Spring 2015 # 1 $\done$
Let $(X, d)$ and $(Y, \rho)$ be metric spaces, $f: X\to Y$, and $x_0 \in X$.

Prove that the following statements are equivalent:

1. For every $\varepsilon > 0 \quad \exists \delta > 0$ such that $\rho( f(x), f(x_0)  ) < \varepsilon$ whenever $d(x, x_0) < \delta$.
2. The sequence $\theset{f(x_n)}_{n=1}^\infty \to f(x_0)$ for every sequence $\theset{x_n} \to x_0$ in $X$.

:::{.concept}
\envlist
- What it means for a sequence to converge.
- Trading $N$s for $\delta$s.

:::

:::{.solution}
\envlist

:::{.proof title="1 $\implies$ 2"}
\envlist

- Let $\theset{x_n} \converges{n\to\infty}\to x_0$ be arbitrary; we want to show $\theset{f(x_n)}\converges{n\to\infty}\to f(x_0)$.
  - We thus want to show that for every $\eps>0$, there exists an $N(\eps)$ such that \[n\geq N(\eps) \implies \rho(f(x_n),  f(x_0)) < \eps.\]
- Let $\eps>0$ be arbitrary, then by (1) choose $\delta$ such that $\rho(f(x), f(x_0)) < \eps$ when $d(x, x_0) < \delta$.
- Since $x_n\to x$, there is some $N$ such that $n\geq N \implies d(x_n, x_0) < \delta$
- Then for $n\geq N$, $d(x_n, x_0) < \delta$ and thus $\rho(f(x_n), f(x_0)) < \eps$, so $f(x_n)\to f(x_0)$ by definition.


:::

:::{.proof title="$2\implies 1$"}

> The direct implication is not a good idea here, since you need a handle on *all* $x$ in a neighborhood of $x_0$, not just a specific sequence.

- By contrapositive, show that $\not 1\implies \not 2$. 
- Need to show: if $f$ is not $\eps\dash\delta$ continuous at $x_0$, then there exists a sequence $x_n\to x_0$ where $f(x_n)\not\to f(x_0)$.
- Negating $1$, we have that there exists an $\eps>0$ such that for all $\delta$, there exists an $x$ with $d(x, x_0) < \delta$ but $\rho(f(x), f(x_0))>\eps$
- So take a sequence of deltas $\delta_n = {1\over n}$, apply this to produce a sequence $x_n$ with $d(x_n, x_0) < \delta_n \da {1\over n} \too 0$ and $\rho(f(x_n), f(x_0)) > \eps$ for all $n$.
- This yields a sequence $x_n \to x_0$ where $f(x_n) \not\to f(x_0)$.

:::

:::


## Fall 2014 # 2  $\work$
Let $I$ be an index set and $\alpha: I \to (0, \infty)$.

a.
Show that
\[
\sum_{i \in I} a(i):=\sup _{\substack{ J \subset I \\ J \text { finite }}} \sum_{i \in J} a(i)<\infty \implies I \text{ is countable.}
\]

b.
Suppose $I = \QQ$ and $\sum_{q \in \mathbb{Q}} a(q)<\infty$.
Define
\[
f(x):=\sum_{\substack{q \in \mathbb{Q}\\ q \leq x}} a(q).
\]
Show that $f$ is continuous at $x \iff x\not\in \QQ$.


:::{.concept}
\envlist

- Can always filter sets $X$ with a function $X\to \RR$.
- Countable union of countable sets is still countable.
- Continuity: $\lim_{y\to x} f(y) = f(x)$ from either side.
- Trick: pick enumerations of countable sets and reindex sums
:::


:::{.solution}
\envlist

:::{.proof title="of a"}
\envlist

- Set $S \definedas \sum_{i\in I} \alpha(i)$, we will show that $S<\infty \implies I$ is countable.
- Write 
\[
I = \Union_{n\geq 0} S_n, &&
S_n \definedas \theset{i\in I \suchthat \alpha(i) \geq {1\over n}}
.\]
  - Note that $S_n \subseteq S$ for all $n$, so $\sum_{i\in I}\alpha(i) \geq \sum_{i\in S_n} \alpha(i)$ for all $n$.
  - It suffices to show that $S_n$ is countable, since $I$ is a countable union of $S_n$.
- There is an inequality
\[  
\infty 
&> S \da \sum_{i\in I} \alpha(i) \\
&\geq \sum_{i\in S_n} \alpha(i) \\
&\geq \sum_{i\in S_n} {1\over n} \\
&= {1\over n} \sum_{i\in S_n} 1 \\
&= \qty{1\over n} \# S_n \\ \\
\implies \infty &> n S \geq \# S_n
.\]
:::


First consider the case of $x\in \QQ$.
Strat: show $\lim_{y\to x^+}f(y) \neq f(x)$.

:::{.proof title="of b, at rationals"}
\envlist

- Fix an enumeration of $\QQ$, say $\QQ = \ts{q_k}_{k\in \ZZ^{\geq 0}}$.
  Without loss of generality, relabel so $q_0 = x$.
- Change the indexing set by defining a section
\[
A(x) \da \ts{ k\in \ZZ^{\geq 0 } \st q_k < x } 
.\]

- Rewrite the sum
\[
f(q_0) \da \sum_{\substack{q\in \QQ \\ q\leq x}} \alpha(q) = \sum_{k\in A(x)} \alpha(q_k)
.\]

- Let $y>q_0$ be arbitrary, and note some facts:
  - $A(y) \supset A(q_0)$, since there is always a rational in $(q_0, y)$.
    This also implies $f(y) > f(x)$, i.e. $f$ is monotone increasing.
  - Since $q_0 < y$, the index $k=0$ is contained in $A(y)$ by definition.
  - The index $k=0$ is *not* contained in $A(x)$ by definition.
- There is a strict inequality
\[
f(y) \da \sum_{k\in A(y)} \alpha(q_k) > \sum_{k\in A(x)} \alpha(q_k) \da f(q_0)
.\]
- Adding the missing index $\ts{0}$ to the right-hand side makes this an inequality.
  Set $A'(x) \da A(x)\union \ts{0}$, then
\[
f(y) \da \sum_{k\in A(y)} \alpha(q_k) 
&\geq \sum_{k\in A'(x)} \alpha(q_k) \\
&= \alpha(q_0) + \sum_{k \in A(x)} \alpha(q_k) \\
&\da \alpha(q_0) + f(q_0) \\
&> f(q_0)
,\]
where in the last step we've used that $\alpha$ is strictly positive.

- Since $f$ is monotone increasing and the set $\ts{f(y) \st y>q_0}$ is bounded below by $q_0$, the right limit $\lim_{y\to q_0^+} f(y)$ exists.
- By order limit laws, applying it to the above inequality preserves the inequality:
\[
\lim_{y\to q_0^+} f(y) \geq \alpha(q_0) + f(q_0) > f(q_0)
.\]

:::


:::{.proof title="of b"}
\envlist

- Fix an enumeration \( \ts{ q_k }_{k\in \NN} = \QQ \).
- Trick: reindex to sum over a set of *indices* instead of rationals
  - Set 
  \[
  A(x) \da \ts{ k\in \NN \st q_k \leq x } \implies f(x) \da \sum_{k\in A(x)} \alpha(q_k)
  .\]
  - This makes it clear that $f$ is monotone increasing, since $y<x \implies A(y) \subseteq A(x) \implies f(y) < f(x)$.
  - This also makes lower continuity clear for $x\da q_m$ any rational, since $y\increasesto q_m \implies A(x) \increasesto A(q_m)$ and $m\in A(q_m)$.


:::



:::{.proof title="of b, at irrationals"}


:::


:::



## Spring 2014 # 2  $\done$

Let $\theset{a_n}$ be a sequence of real numbers such that
\[
\theset{b_n} \in \ell^2(\NN) \implies \sum a_n b_n < \infty.
\]
Show that $\sum a_n^2 < \infty$.

> Note: Assume $a_n, b_n$ are all non-negative.

\todo[inline]{Have someone check!}
:::{.solution}
\envlist
- Define a sequence of operators 
\[  
T_N: \ell^2 &\to \ell^1\\
\theset{b_n} &\mapsto \sum_{n=1}^N a_n b_n
.\]
- By assumption, these are well defined: the image is $\ell^1$ since $\abs{T_N(\theset{b_n})} < \infty$ for all $N$ and all $\theset{b_n} \in \ell^2$.
- So each $T_N \in \qty{\ell^2}\dual$ is a linear functional on $\ell^2$.
- For each $x\in \ell^2$, we have $\norm{T_N(x)}_{\RR} = \sum_{n=1}^N a_n b_n < \infty$ by assumption, so each $T_N$ is pointwise bounded.
- By the Uniform Boundedness Principle, $\sup_N \norm{T_N}_{\text{op}} < \infty$.
- Define $T = \lim_{N \to\infty } T_N$, then $\norm{T}_{\text{op}} < \infty$.
- By the Riesz Representation theorem,
\[  
\sqrt{\sum a_n^2} \definedas \norm{\theset{a_n}}_{\ell^2} = \norm{T}_{\qty{\ell^2}\dual} = \norm{T}_{\text{op}} < \infty
.\]

- So $\sum a_n^2 < \infty$.
:::



# General Analysis

## Spring 2020 # 1 $\done$

Prove that if $f: [0, 1] \to \RR$ is continuous then
\[
\lim_{k\to\infty} \int_0^1 kx^{k-1} f(x) \,dx = f(1)
.\]

:::{.concept}
\envlist

- DCT
- Weierstrass Approximation Theorem
:::

:::{.solution}
\envlist

- Suppose $p$ is a polynomial, then
\[
\lim_{k\to\infty} \int_0^1 kx^{k-1} p(x) \, dx
&= \lim_{k\to\infty} \int_0^1 \qty{ \dd{}{x}x^k } p(x) \, dx \\
&= \lim_{k\to\infty} \left[ x^k p(x) \evalfrom_0^1 - \int_0^1 x^k \qty{\dd{p}{x}(x) } \, dx \right] \quad\text{integrating by parts}\\
&= p(1) - \lim_{k\to\infty} \int_0^1 x^k \qty{\dd{p}{x}(x) } \, dx
,\]

- Thus it suffices to show that
\[
\lim_{k\to\infty} \int_0^1 x^k \qty{\dd{p}{x} (x) } \, dx = 0
.\]

- Integrating by parts a second time yields
\[
\lim_{k\to\infty} 
\int_0^1 x^k \qty{\dd{p}{x}(x) } \, dx
&= \lim_{k\to\infty} 
{x^{k+1} \over k+1} \dd{p}{x}(x) \evalfrom_0^1 - \int_0^1 {x^{k+1} \over k+1} \qty{ \dd{^2 p}{x^2}(x)} \, dx \\
&= \lim_{k\to\infty} {p'(1) \over k+1} - \lim_{k\to\infty} \int_0^1 {x^{k+1} \over k+1} \qty{ \dd{^2p}{x^2}(x)} \, dx \\
&= - \lim_{k\to\infty} \int_0^1 {x^{k+1} \over k+1} \qty{ \dd{^2p}{x^2}(x)} \, dx \\
&= - \int_0^1 \lim_{k\to\infty}  {x^{k+1} \over k+1} \qty{ \dd{^2p}{x^2}(x)} \, dx \quad\text{by DCT} \\
&= - \int_0^1 0 \qty{ \dd{^2p}{x^2}(x)} \, dx \\
&= 0
.\]

  - The DCT can be applied here because polynomials are smooth and $[0, 1]$ is compact, so $\dd{^2 p}{x^2}$ is bounded on $[0, 1]$ by some constant $M$ and 
  \[ \int_0^1 \abs{x^k \dd{^2 p}{x^2} (x)} \leq \int_0^1 1\cdot M = M < \infty.\]

- So the result holds when $f$ is a polynomial.

- Now use the Weierstrass approximation theorem: 
  - If $f: [a, b] \to \RR$ is continuous, then for every $\eps>0$ there exists a polynomial $p_\eps(x)$ such that $\norm{f - p_\eps}_\infty < \eps$.

- Thus 
\[
\abs{ \int_0^1 kx^{k-1} p_\eps(x)\,dx - \int_0^1 kx^{k-1}f(x)\,dx  } 
&= \abs{ \int_0^1 kx^{k-1} \qty{p_\eps(x) - f(x)} \,dx  } \\
&\leq \abs{ \int_0^1 kx^{k-1} \norm{p_\eps-f}_\infty \,dx  } \\
&= \norm{p_\eps-f}_\infty \cdot \abs{ \int_0^1 kx^{k-1} \,dx  } \\
&= \norm{p_\eps-f}_\infty \cdot x^k \evalfrom_0^1 \\
&= \norm{p_\eps-f}_\infty \\ \\
&\converges{\eps\to 0}\to 0
\]

  and the integrals are equal. 

- By the first argument, $$\int_0^1 kx^{k-1} p_\eps(x) \,dx = p_\eps(1) \text{ for each } \eps$$ 
- Since uniform convergence implies pointwise convergence, $p_\eps(1) \converges{\eps\to 0}\to f(1)$.

:::

## Fall 2019 # 1 $\done$
Let $\{a_n\}_{n=1}^\infty$ be a sequence of real numbers.

a.
Prove that if $\displaystyle\lim_{n\to \infty } a_n = 0$, then 
\[
\lim _{n \rightarrow \infty} \frac{a_{1}+\cdots+a_{n}}{n}=0
\]

b.
Prove that if $\displaystyle\sum_{n=1}^{\infty} \frac{a_{n}}{n}$ converges, then 
\[
\lim _{n \rightarrow \infty} \frac{a_{1}+\cdots+a_{n}}{n}=0
\]

:::{.solution}
\envlist

:::{.concept}
\envlist
- Cesaro mean/summation. 
- Break series apart into pieces that can be handled separately.
- Idea: once $N$ is large enough, $a_k \approx S$, and all smaller terms will die off as $N\to \infty$.
  - See [this MSE answer](https://math.stackexchange.com/questions/514802/convergence-of-series-implies-convergence-of-cesaro-mean).
:::

:::{.proof title="of a"}
\envlist

- Prove a stronger result: 
\[
a_k \to S \implies S_N\definedas \frac 1 N \sum_{k=1}^N a_k \to S
.\]

- For any $\eps> 0$, use convergence $a_k \to S$: choose (and fix) $M = M(\eps)$ large enough such that 
\[
k\geq M+1 \implies \abs{a_k - S} < \varepsilon
.\]

- With $M$ fixed, choose $N = N(M, \eps)$ large enough so that ${1\over N} \sum_{k=1}^{M} \abs{a_k - S} < \eps$.

- Then
\[
\left|\left(\frac{1}{N} \sum_{k=1}^{N} a_{k}\right)-S\right| 
&= {1\over N} \abs{ \qty{\sum_{k=1}^N a_k} - NS  } \\
&= {1\over N} \abs{ \qty{\sum_{k=1}^N a_k} - \sum_{k=1}^N S  } \\
&=\frac{1}{N}\left|\sum_{k=1}^{N}\left(a_{k}-S\right)\right| \\
&\leq \frac{1}{N} \sum_{k=1}^{N}\left|a_{k}-S\right| \\
&= {1\over N} \sum_{k=1}^{M} \abs{a_k - S} + \sum_{k=M+1}^N \abs{a_k - S} \\
&\leq {1\over N} \sum_{k=1}^{M} \abs{a_k - S} + \sum_{k=M+1}^N {\eps } \quad \text{since } a_k \to S\\
&= {1\over N} \sum_{k=1}^{M} \abs{a_k - S} + (N - M){\eps } \\
&\leq \eps + (N(M, \eps) - M(\eps))\eps
.\]

:::

\todo[inline]{Revisit, not so clear that the last line can be made smaller than $\eps$, since $M, N$ both depend on $\eps$...}

:::{.proof title="of b"}
\envlist

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

:::

## Fall 2018 # 4 $\done$
Let $f\in L^1([0, 1])$.
Prove that
\[
\lim_{n \to \infty} \int_{0}^{1} f(x) \abs{\sin n x} ~d x= \frac{2}{\pi} \int_{0}^{1} f(x) ~d x
\]

> Hint: Begin with the case that $f$ is the characteristic function of an interval.

\todo[inline]{Ask someone to check the last approximation part.}

:::{.solution}
\envlist
:::{.concept}
\envlist
- Converting floor/ceiling functions to inequalities: $x-1 \leq \floor{x} \leq x$.
:::

Case of a characteristic function of an interval $[a, b]$:

- First suppose $f(x) = \chi_{[a, b]}(x)$.
- Note that $\sin(nx)$ has a period of $2\pi/n$, and thus $\floor{ (b-a) \over (2\pi / n)} = \floor{n(b-a)\over 2\pi}$ full periods in $[a, b]$.
- Taking the absolute value yields a new function with half the period
  - So $\abs{\sin(nx)}$ has a period of $\pi/n$ with $\floor{n(b-a) \over \pi}$ full periods in $[a, b]$.
- We can compute the integral over one full period (which is independent of *which* period is chosen)
  - We can use translation invariance of the integral to compute this over the period $0$ to $\pi/n$.
  - Since $\sin(nx)$ is positive, it equals $\abs{\sin(nx)}$ on its first period, so we have
\[
\int_{\text{One Period}} \abs{\sin(nx)} \, dx 
&= \int_0^{\pi/n} \sin(nx)\,dx \\
&= {1\over n} \int_0^\pi \sin(u) \,du \quad u = nx \\
&= {1\over n} \qty{-\cos(u)\mid_0^\pi} \\
&= {2 \over n}
.\]


- Then break the integral up into integrals over full periods $P_1, P_2, \cdots, P_N$ where $N \definedas \floor{n(b-a)/\pi}$
- Noting that each period is of length $\pi\over n$, so letting $L_n$ be the regions falling *outside* of a full period, we have

- Thus
\[
\int_a^b \abs{\sin(nx)} \, dx 
&= \qty{ \sum_{j=1}^{N} \int_{P_j} \abs{\sin(nx)} \, dx } +  \int_{L_n} \abs{\sin(nx)}\,dx \\
&= \qty{ \sum_{j=1}^{N} {2\over n} } +  \int_{L_n} \abs{\sin(nx)}\,dx \\
&= N \qty{2\over n} +  \int_{L_n} \abs{\sin(nx)}\,dx \\
&\definedas \floor{(b-a) n \over \pi} {2\over n} +  R_n \\
&\definedas (b-a)C_n + R_n 
\]
  where (claim) $C_n \converges{n\to\infty}\to {2\over \pi}$ and $R(n) \converges{n\to\infty}\to 0$. 

- $C_n \to {2\over \pi}$:
\[  
{n-1 \over n} \qty{2\over \pi} = {n-1 \over \pi} \qty{2\over n} \leq \floor{n\over \pi}\qty{2\over n} \leq {n \over \pi}\qty{2\over n} = {2 \over \pi}
,\]
  then use the fact that ${n-1 \over n} \to 1$.
  - Then equality follows by the Squeeze theorem.

- $R_n \to 0$:
  - We use the fact that $m(L_n) \to 0$, then $\int_{L_n} \abs{\sin(nx)} \leq \int_{L_n} 1 = m(L_n) \to 0$.
  - This follows from the fact that $L_n$ is the complement of $\union_j P_j$, the set of full periods, so
\[  
m(L_n) 
&= m(b-a) - \sum m(P_j) \\
&= \qty{b-a} -  \floor{n(b-a) \over \pi}\qty{\pi \over n} \\
&\converges{n\to \infty}\to (b-a) - (b-a) \\
&= 0
.\]
  where we've used the fact that
\[  
\qty{\pi \over n} \qty{(b-a)n-1 \over \pi} 
&\leq \floor{n(b-a) \over \pi}\qty{\pi \over n}  \\
&\leq \qty{\pi \over n} \qty{(b-a)n\over \pi}  \\
&= (b-a)
,\]
  then taking $n\to \infty$ sends the LHS to $b-a$, forcing the middle term to be $b-a$ by the Squeeze theorem.


General case:

- By linearity of the integral, the result holds for simple functions:
  - If $f = \sum c_j \chi_{E_j}$ where $E_j = [a_j, b_j]$, we have
  \[  
  \int_0^1 f(x) \abs{\sin(nx)}\,dx 
  &= \int_0^1 \sum c_j \chi_{E_j}(x) \abs{\sin(nx)}\,dx  \\
  &= \sum c_j \int_0^1 \chi_{E_j}(x) \abs{\sin(nx)}\,dx \\
  &= \sum c_j (b_j - a_j) {2\over \pi} \\
  &= {2\over \pi} \sum c_j (b_j - a_j) \\
  &= {2\over \pi} \sum c_j m(E_j) \\
  &\definedas {2\over \pi} \int_0^1 f
  .\]
- Since $f\in L^1$, where simple functions are dense, choose $s_n\nearrow f$ where $\norm{s_N - f}_1 < \eps$, then
\[  
\abs{ \int_0^1 f(x) \abs{\sin(nx)} \,dx - \int_0^1 s_N(x) \abs{\sin(nx)}\,dx } 
&= \abs{ \int_0^1 \qty{f(x) - s_N(x)} \abs{\sin(nx)} \,dx } \\
&\leq \int_0^1 \abs{ f(x) - s_N(x)} \abs{\sin(nx)} \,dx \\
&= \norm{ \qty{f - s_N} \abs{\sin(nx)} }_1 \\
&\leq \norm{f-s_N}_1 \cdot \norm{\abs{\sin(nx)}}_\infty \quad\text{by Holder}\\
&\leq \eps \cdot 1
,\]


- So the integrals involving $s_N$ converge to the integral involving $f$, and
\[
\lim_{n\to\infty} \int f(x)\abs{\sin(nx)} 
&= \lim_{n\to\infty} \lim_{N\to\infty} \int s_N(x) \abs{\sin(nx)} \\
&= \lim_{N\to\infty} \lim_{n\to\infty} \int s_N(x) \abs{\sin(nx)} \quad\text{because ?}\\
&= \lim_{N\to \infty} {2\over \pi} \int s_N(x) \\
&= {2\over \pi} \int f
,\]
  which is the desired result.
:::

## Fall 2017 # 4 $\done$
Let
\[
f_{n}(x) = n x(1-x)^{n}, \quad n \in \NN.
\]

a. 
Show that $f_n \to 0$ pointwise but not uniformly on $[0, 1]$.

b. 
Show that
\[
\lim _{n \to \infty} \int _{0}^{1} n(1-x)^{n} \sin x \, dx = 0
\]

> Hint for (a): Consider the maximum of $f_n$.

:::{.solution}
\envlist
:::{.concept}
\envlist
- $\sum f_n < \infty \iff \sup f_n \to 0$.
- Negating uniform convergence: $f_n\not\to f$ uniformly iff $\exists \eps$ such that $\forall N(\eps)$ there exists an $x_N$ such that $\abs{f(x_N) - f(x)} > \eps$.
- Exponential inequality: $1+y \leq e^y$ for all $y\in \RR$.
:::

a.

$f_n\to 0$ pointwise:

- Finding the maximum: can check that $\dd{f_n}{x} = x(1-x)^{n-1} \qty{1 + (n^2-1)x}$
- This has critical points $x=0, 1, {-1 \over n^2 + 1}$, and the latter is a global max on $[0, 1]$.
- Set $x_n \definedas {-1 \over n^2 + 1}$
- Compute
\[  
\lim f_n(x_n) = \lim_{n\to \infty } {-n \over n^2 + 1} \qty{1 + x_n}^n = 0\cdot 1 = 0
.\]
- So $\sup f_n \to 0$, forcing $f_n \to 0$ pointwise.


The convergence is not uniform:

- Let $x_n = \frac 1 n$ and $\varepsilon > e\inv$, then
\[
\norm{nx(1-x)^n - 0}_\infty
&\geq \abs{nx_n (1-x_n)^n} \\
&= \abs{\left( 1 - \frac 1 n\right)^n} \\
&> e^{-1} \\
&> \varepsilon
.\]

  - Here we've used that $(1 + {x\over n})^n \leq e^x$ for all $x\in \RR$ and all $n$.
  - Follows from $1+y \leq e^y$ applied to $y = x/n$.

- Thus $\norm{f_n - 0}_\infty = \norm{f_n}_\infty > e^{-1} > 0$.


b.

\todo[inline]{Possible to use part a with $\sin(x) \leq x$ on $[0, \pi/2]$?}

- Noting that $\sin(x) \leq 1$, we have
\[
\abs{\int_0^1  n(1-x)^{n} \sin(x)} 
&\leq \int_0^1  \abs{n(1-x)^n \sin(x)} \\
&\leq \int_0^1  \abs{n (1-x)^n}  \\
&= n\int_0^1 (1-x)^n \\
&= -\frac{n(1-x)^{n+1}}{n+1} \\
&\converges{n\to\infty}\longrightarrow 0
.\]
:::

## Spring 2017 # 3 $\work$

Let
\[
f_{n}(x) = a e^{-n a x} - b e^{-n b x} \quad \text{ where } 0 < a < b.
\]

Show that 

a. 
$\sum_{n=1}^{\infty} \left|f_{n}\right|$ is not in $L^{1}([0, \infty), m)$

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
\envlist
:::{.concept}
\envlist
:::

a.

- $f_n$ has a root:
\[  
ae^{-nax} = be^{-nbx} 
&\iff {1\over n} = e^{-nbx} e^{nax} = e^{n(b-a)x}
\iff x = {\ln\qty{a\over b} \over n(a-b)} \definedas x_n
.\]

- Thus $f_n$ only changes sign at $x_n$, and is strictly positive on one side of $x_n$.
- Then
\[  
\int_\RR \sum_n \abs{f_n(x)}\,dx 
&= \sum_n \int_\RR \abs{f_n(x)} \,dx \\
&\geq \sum_n \int_{x_n}^\infty f_n(x) \, dx \\
&= \sum_n {1\over n} \qty{ e^{-bnx} - e^{-anx}\evalfrom_{x_n}^\infty } \\
&= \sum_n {1\over n} \qty{ e^{-bnx_n} - e^{-anx_n} }
.\]


b.

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
\envlist
:::{.concept}
\envlist
- ?
:::

- Set $f_N(x) \definedas \sum_{n=1}^N n^{-x}$, so $f(x) = \lim_{N\to\infty} f_N(x)$.
- If an interchange of limits is justified, we have
\[  
\dd{}{x} \lim_{N\to\infty} \sum_{n=1}^N n^{-x}
&= \lim_{h\to 0} \lim_{N\to\infty} {1\over h} \left[ \qty{\sum_{n=1}^N n^{-x}} - \qty{\sum_{n=1}^N n^{-(x+h)} }\right] \\
&\eq_{?} \lim_{N\to\infty} \lim_{h\to 0} {1\over h} \left[ \qty{\sum_{n=1}^N n^{-x}} - \qty{\sum_{n=1}^N n^{-(x+h)} }\right] \\
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
  \eq^{L.H.} \lim_{n\to\infty}{1/n \over \eps n^{\eps-1}} 
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
\todo[inline]{Add concepts.}

:::{.solution}
\envlist
:::{.concept}
\envlist
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

\todo[inline]{Rewrite solution.}

:::{.concept}
\envlist
- Cauchy Schwarz: $\norm{fg}_1 \leq \norm{f}_1 \norm{g}_1$.
- Small tails in $L^p$.
:::


:::{.solution}
\envlist

- Use the fact that $L^p$ has small tails: if $h\in L^2(\RR)$, then for any $\eps > 0$, 
\[  
\forall \eps,\, \exists N\in \NN \qst \int_{\abs{x} \geq {N}} \abs{h(x)}^2 \,dx < \eps
.\]

- So choose $N$ large enough so that
\[  
\int_{\norm{x} \geq N}\abs{g(x)}^2 < \eps \\
\int_{\norm{x} \geq N}\abs{f(x)}^2 < \eps \\
.\]

- Then write
\[  
\int_{\RR^d} f(x) g(x+n) \,dx = \int_{\norm{x} \leq N} f(x)g(x+n)\,dx + \int_{\norm{x} \geq N} f(x) g(x+n)\,dx
.\]

- Bounding the second term: apply Cauchy-Schwarz
\[  
\int_{\norm{x} \geq N} f(x) g(x+n)\,dx
\leq 
\qty{ \int_{\norm{x} \geq N} \abs{f(x)}^2}^{1\over 2} \cdot 
\qty{ \int_{\norm{x} \geq N} \abs{g(x)}^2}^{1\over 2}
\leq \eps^{1\over 2} \cdot \norm{g}_2
.\]

- Bounding the first term: also Cauchy-Schwarz, after variable changes
\[  
\int_{\norm{x} \leq N} f(x) g(x+n)\,dx 
&= \int_{-N}^N f(x) g(x+n)\,dx \\
&= \int_{-N+n}^{N+n} f(x-n) g(x)\,dx \\
&\leq \int_{-N+n}^{\infty} f(x-n) g(x)\,dx \\
&\leq \qty{\int_{-N+n}^{\infty} \abs{f(x-n)}^2}^{1\over 2}\cdot \qty{\int_{-N+n}^{\infty} \abs{g(x)}^2}^{1\over 2} \\
&\leq \norm{f}_2 \cdot \eps^{1\over 2}
.\]

- Then as long as $n\geq 2N$, we have
\[  
\int \abs{f(x) g(x+n)} \leq \qty{\norm{f}_2 + \norm{g}_2} \cdot \eps^{1\over 2} 
.\]
:::

## Spring 2016 # 1  $\work$

For $n\in \NN$, define
\[
e_{n} = \left (1+ {1\over n} \right)^{n} 
\qtext{and}
E_{n} = \left( 1+ {1\over n} \right)^{n+1}
\]

Show that $e_n < E_n$, and prove Bernoulli's inequality:
\[
(1+x)^n \geq 1+nx && -1 < x < \infty  ,\,\, n\in \NN
.\]


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

## Fall 2020 \# 1
Show that if $x_n$ is a decreasing sequence of positive real numbers such that $\sum_{n=1}^\infty x_n$ converges, then
$$
\lim_{n\to\infty} n x_n = 0.
$$

## Fall 2020 \# 3
Let $f$ be a non-negative Lebesgue measurable function on $[1, \infty)$.

a.
Prove that
\[  
1 \leq \qty{
{1 \over b-a} \int_a^b f(x) \,dx
}\qty{
{1\over b-a} \int_a^b {1 \over f(x)}\, dx
}
\]
for any $1\leq a < b <\infty$.

b.
Prove that if $f$ satisfies
\[  
\int_1^t f(x) \, dx \leq t^2 \log(t)
\]
for all $t\in [1, \infty)$, then
\[  
\int_1^\infty {1\over f(x) \,dx} = \infty
.\]

> Hint: write
\[  
\int_1^\infty {1\over f(x) \, dx} = \sum_{k=0}^\infty \int_{2^k}^{2^{k+1}} {1 \over f(x)}\,dx
.\]


