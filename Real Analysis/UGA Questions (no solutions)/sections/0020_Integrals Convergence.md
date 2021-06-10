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
  
Prove that if $f_k \to f$ almost everywhere, then $f ∈ L^2([0, 1])$ with $\norm{f}_2 ≤ M$ and
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

## Spring 2021 # 2 $\done$

:::{.problem title="?"}
Calculate the following limit, justifying each step of your calculation:
\[
L \da \lim_{n\to \infty} \int_0^n { \cos\qty{x\over n} \over x^2 + \cos\qty{x\over n} }\dx
.\]
:::


:::{.solution}

- If interchanging a limit and integral is justified, we have
\[
L 
&\da \lim_{n\to \infty} \int_{(0, n)} {\cos\qty{x\over n} \over x^2 + \cos\qty{x\over n} } \dx \\
&= \lim_{n\to \infty} \int_{(0, \infty)} \chi_{(0, n)}(x) {\cos\qty{x\over n} \over x^2 + \cos\qty{x\over n} } \dx \\
&\equalsbecause{\text{DCT}} \int_{(0, \infty)} \lim_{n\to \infty} \chi_{(0, n)}(x) {\cos\qty{x\over n} \over x^2 + \cos\qty{x\over n} } \dx \\
&= \int_{(0, \infty)} \chi_{(0, \infty)}(x) \lim_{n\to \infty} {\cos\qty{x\over n} \over x^2 + \cos\qty{x\over n} } \dx \\
&= \int_{(0, \infty)} {\lim_{n\to \infty} \cos\qty{x\over n} \over \lim_{n\to \infty} x^2 + \cos\qty{x\over n} } \dx \\
&= \int_{(0, \infty)} {\cos\qty{\lim_{n\to \infty} {x\over n} } \over x^2 + \cos\qty{\lim_{n\to \infty} {x\over n} } } \dx \\
&= \int_{(0, \infty)} {1\over x^2 + 1}\dx \\
&= \arctan(x)\evalfrom_0^\infty \\
&= {\pi \over 2}
,\]
where we've used that $\cos(\theta)$ is continuous on $\RR$ to pass a limit inside, noting that $x$ is fixed in the integrand.

- Justifying the interchange: DCT.
  Write $f_n(x) \da \cos(x/n) / (x^2 + \cos(x/n))$.

- On $(\alpha, \infty)$ for any $\alpha > 1$:

  - We have
  \[
  \abs{f_n(x)} \leq 
  \abs{1\over x^2 + \cos(x/n)} \leq {1\over x^2-1}
  ,\]
  where we've used that $-1\leq \cos(x/n) \leq 1$ for every $x$, and so the denominator is minimized when $\cos(x/n) = -1$, and this maximizes the quantity.
  - Setting $g(x) \da 1/(x^2-1)$, we have $g\in L^1(\alpha, \infty)$ by the limit comparison test with $h(x) \da x^2$:
  \[
  {g(x) \over h(x) } \da {x^2 -1 \over x^2 } = 1 - {1\over x^2} \converges{x\to \infty}\too 1 < \infty
  ,\]
  and so $g, h$ either both converge or both diverge.
  But $\int_\alpha^\infty {1\over x^2}\dx < \infty$ by the $p\dash$test for integrals since $\alpha>1$.

- On $(0, \alpha)$:

  - Just use that $f_n(x)$ is bounded by a constant:
  \[
  \abs{f_n(x)} 
  = \abs{\cos(x/n) \over x^2 + \cos(x/n)}
  \leq \abs{\cos(x/n) \over \cos(x/n)} = 1
  ,\]
  where we've used that $x^2$ is positive, and removing it from the denominator only makes the quantity larger.
  - Then check that $\int_0^\alpha 1 \dx = \alpha < \infty$, so $1\in L^1(0, \alpha)$.
    
:::



## Spring 2021 # 5

Let \( f_n \in L^2([0, 1]) \) for \( n\in \NN \), and assume that 

- \( \norm{f_n}_2 \leq n^{-51 \over 100} \)  for all \( n\in \NN \),

- $\hat{f}_n$ is supported in the interval $[2^n, 2^{n+1}]$, so
\[
\hat{f}_n(\xi) \da \int_0^1 f_n(x) e^{2\pi i \xi \cdot x} \dx = 0 && \text{for } \xi \not\in [2^n, 2^{n+1}]
.\]

Prove that \( \sum_{n\in \NN} f_n \) converges in the Hilbert space \( L^2([0, 1]) \).

> Hint: Plancherel's identity may be helpful.


