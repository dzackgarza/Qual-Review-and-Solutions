# Functional Analysis: General

## Fall 2019 # 4. 
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


:::



## Spring 2019 # 5

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

## Spring 2016 # 6
Without using the Riesz Representation Theorem, compute
\[
\sup \left\{\left|\int_{0}^{1} f(x) e^{x} d x\right| \suchthat f \in L^{2}([0,1], m),~~ \|f\|_{2} \leq 1\right\}
\]

## Spring 2015 # 5
Let $\mathcal H$ be a Hilbert space.

1. Let $x\in \mathcal H$ and $\theset{u_n}_{n=1}^N$ be an orthonormal set.
  Prove that the best approximation to $x$ in $\mathcal H$ by an element in $\spanof_\CC\theset{u_n}$ is given by
  $$
  \hat x \definedas \sum_{n=1}^N \inner{x}{u_n}u_n.
  $$
2. Conclude that finite dimensional subspaces of $\mathcal H$ are always closed.

## Fall 2015 # 6
Let $f: [0, 1] \to \RR$ be continuous.
Show that
\[
\sup \left\{\|f g\|_{1} \suchthat g \in L^{1}[0,1],~~ \|g\|_{1} \leq 1\right\}=\|f\|_{\infty}
\]

## Fall 2014 # 6
Let $1 \leq p,q \leq \infty$ be conjugate exponents, and show that
\[
f \in L^p(\RR^n) \implies \|f\|_{p} = \sup _{\|g\|_{q}=1}\left|\int f(x) g(x) d x\right|
\]

# Functional Analysis: Banach Spaces

## Spring 2019 # 1
Let $C([0, 1])$ denote the space of all continuous real-valued functions on $[0, 1]$.
  
a. Prove that $C([0, 1])$ is complete under the uniform norm $\norm{f}_u := \displaystyle\sup_{x\in [0,1]} |f (x)|$.

b. Prove that $C([0, 1])$ is not complete under the $L^1\dash$norm $\norm{f}_1 = \displaystyle\int_0^1 |f (x)| ~dx$.

:::{.solution}

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


:::



## Spring 2017 # 5
Show that the space $C^1([a, b])$ is a Banach space when equipped with the norm
\[
\|f\|:=\sup _{x \in[a, b]}|f(x)|+\sup _{x \in[a, b]}\left|f^{\prime}(x)\right|.
\]

## Fall 2017 # 6
Let $X$ be a complete metric space and define a norm
$$
\|f\|:=\max \{|f(x)|: x \in X\}.
$$

Show that $(C^0(\RR), \norm{\wait} )$ (the space of continuous functions $f: X\to \RR$) is complete.
