
---
title: Real Analysis Qualifying Exam Questions
---

# Spring 2020

## 1

Prove that if $f: [0, 1] \to \RR$ is continuous then
\begin{align*}
\lim_{k\to\infty} \int_0^1 kx^{k-1} f(x) \,dx = f(1)
.\end{align*}

## 2

Let $m_*$ denote the Lebesgue outer measure on $\RR$.

a. Prove that for every $E\subseteq \RR$ there exists a Borel set $B$ containing $E$ such that
  \begin{align*}
  m_*(B) = m_*(E)
  .\end{align*}

b. Prove that if $E\subseteq \RR$ has the property that
  \begin{align*}
  m_*(A) = m_*(A\intersect E) + m_*(A\intersect E^c)
  \end{align*}
  for every set $A\subseteq \RR$, then there exists a Borel set $B\subseteq \RR$ such that $E = B\setminus N$ with $m_*(N) = 0$.

    Be sure to address the case when $m_*(E) = \infty$.

## 3

a. Prove that if $g\in L^1(\RR)$ then
\begin{align*}
\lim_{N\to\infty} \int_{\abs{x} \geq N} \abs{f(x)} \,dx = 0
,\end{align*}
and demonstrate that it is not necessarily the case that $f(x) \to 0$ as $\abs{x}\to \infty$.

b. Prove that if $f\in L^1([1, \infty])$ and is decreasing, then $\lim_{x\to\infty}f(x) =0$ and in fact $\lim_{x\to \infty} xf(x) = 0$.

c. If $f: [1, \infty) \to [0, \infty)$ is decreasing with $\lim_{x\to \infty} xf(x) = 0$, does this ensure that $f\in L^1([1, \infty))$?

## 4

Let $f, g\in L^1(\RR)$. 
Argue that $H(x, y) \definedas f(y) g(x-y)$ defines a function in $L^1(\RR^2)$ and deduce from this fact that
\begin{align*}
(f\ast g)(x) \definedas \int_\RR f(y) g(x-y) \,dy
\end{align*}
defines a function in $L^1(\RR)$ that satisfies 
\begin{align*}
\norm{f\ast g}_1 \leq \norm{f}_1 \norm{g}_1
.\end{align*}

## 5

Compute the following limit and justify your calculations:
\begin{align*}
\lim_{n\to\infty} \int_0^n \qty{1 + {x^2 \over n}}^{-(n+1)} \,dx
.\end{align*}

## 6

a. Show that
  \begin{align*}
  L^2([0, 1]) \subseteq L^1([0, 1]) \qtext{and} \ell^1(\ZZ) \subseteq \ell^2(\ZZ)
  .\end{align*}

b. For $f\in L^1([0, 1])$ define
  \begin{align*}
  \hat{f}(n) \definedas \int_0^1 f(x) e^{-2\pi i n x} \, dx
  .\end{align*}

  Prove that if $f\in L^1([0, 1])$ and $\theset{\hat f(n)} \in \ell^1(\ZZ)$ then
  \begin{align*}
  S_N f(x) \definedas \sum_{\abs n \leq N} \hat f (n) e^{2\pi i n x}
  .\end{align*}
  converges uniformly on $[0, 1]$ to a continuous function $g$ such that $g = f$ almost everywhere.

  > Hint: One approach is to argue that if $f\in L^1([0, 1])$ with $\theset{\hat f (n)} \in \ell^1(\ZZ)$ then $f\in L^2([0, 1])$.

# Fall 2019

## 1. 
Let $\{a_n\}_{n=1}^\infty$ be a sequence of real numbers.

a. Prove that if $\displaystyle\lim_{n→∞} a_n = 0$, then 
$$
\lim _{n \rightarrow \infty} \frac{a_{1}+\cdots+a_{n}}{n}=0
$$

b. Prove that if $\displaystyle\sum_{n=1}^{\infty} \frac{a_{n}}{n}$ converges, then 
$$
\lim _{n \rightarrow \infty} \frac{a_{1}+\cdots+a_{n}}{n}=0
$$

## 2. 

Prove that
$$
\left|\frac{d^{n}}{d x^{n}} \frac{\sin x}{x}\right| \leq \frac{1}{n}
$$

for all $x \neq 0$ and positive integers $n$.

> Hint: Consider $\displaystyle\int_0^1 \cos(tx) dt$

## 3. 
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

## 4. 
Let $\{u_n\}_{n=1}^∞$ be an orthonormal sequence in a Hilbert space $\mathcal{H}$.

a. Prove that for every $x ∈ \mathcal H$ one has 
$$
\displaystyle\sum_{n=1}^{\infty}\left|\left\langle x, u_{n}\right\rangle\right|^{2} \leq\|x\|^{2}
$$

b. Prove that for any sequence $\{a_n\}_{n=1}^\infty \in \ell^2(\NN)$ there exists an element $x\in\mathcal H$ such that 
  $$
  a_n = \inner{x}{u_n} \text{ for all } n\in \NN
  $$
  and
  $$
  \norm{x}^2 = \sum_{n=1}^{\infty}\left|\left\langle x, u_{n}\right\rangle\right|^{2}
  $$

## 5.

a. Show that if $f$ is continuous with compact support on $\RR$, then 
$$
\lim _{y \rightarrow 0} \int_{\mathbb{R}}|f(x-y)-f(x)| d x=0
$$

b. Let $f\in L^1(\RR)$ and for each $h > 0$ let 
$$
\mathcal{A}_{h} f(x):=\frac{1}{2 h} \int_{|y| \leq h} f(x-y) d y
$$

i. Prove that $\left\|\mathcal{A}_{h} f\right\|_{1} \leq\|f\|_{1}$ for all $h > 0$.

ii. Prove that $\mathcal{A}_h f → f$ in $L^1(\RR)$ as $h → 0^+$.


# Spring 2019

## 1
Let $C([0, 1])$ denote the space of all continuous real-valued functions on $[0, 1]$.
  
a. Prove that $C([0, 1])$ is complete under the uniform norm $\norm{f}_u := \displaystyle\sup_{x\in [0,1]} |f (x)|$.
b. Prove that $C([0, 1])$ is not complete under the $L^1\dash$norm $\norm{f}_1 = \displaystyle\int_0^1 |f (x)| ~dx$.

## 2
Let $\mathcal B$ denote the set of all Borel subsets of $\RR$ and $\mu : \mathcal B → [0, \infty)$ denote a finite Borel measure on $\RR$.
  
  a. Prove that if $\{F_k\}$ is a sequence of Borel sets for which $F_k \supseteq  F_{k+1}$ for all $k$, then
  $$
  \lim _{k \rightarrow \infty} \mu\left(F_{k}\right)=\mu\left(\bigcap_{k=1}^{\infty} F_{k}\right)
  $$
  b. Suppose $µ$ has the property that $µ(E) = 0$ for every $E \in \mathcal B$ with Lebesgue measure $m(E) = 0$.
    Prove that for every $ε > 0$ there exists $δ > 0$ so that if $E \in \mathcal B$ with $m(E) < δ$, then $µ(E) < ε$.

## 3 
Let $\{f_k\}$ be any sequence of functions in $L^2([0, 1])$ satisfying $\norm{f_k}_2 ≤ M$ for all $k ∈ \NN$.
  
Prove that if $f_k → f$ almost everywhere, then $f ∈ L^2([0, 1])$ with $\norm{f}_2 ≤ M$ and
$$
\lim _{k \rightarrow \infty} \int_{0}^{1} f_{k}(x) dx = \int_{0}^{1} f(x) d x
$$

> Hint: Try using Fatou’s Lemma to show that $\norm{f}_2 ≤ M$ and then try applying Egorov’s Theorem.

## 4
Let $f$ be a non-negative function on $\RR^n$ and $\mathcal A = \{(x, t) ∈ \RR^n × \RR : 0 ≤ t ≤ f (x)\}$.

Prove the validity of the following two statements:

  a. $f$ is a Lebesgue measurable function on $\RR^n \iff  \mathcal A$ is a Lebesgue measurable subset of $\RR^{n+1}$
  
  b. If $f$ is a Lebesgue measurable function on $\RR^n$, then
  $$
  m(\mathcal{A})=\int_{\mathbb{R}^{n}} f(x) d x=\int_{0}^{\infty} m\left(\left\{x \in \mathbb{R}^{n}: f(x) \geq t\right\}\right) d t
  $$

## 5

a.  Show that $L^2([0, 1]) ⊆ L^1([0, 1])$ and argue that $L^2([0, 1])$ in fact forms a dense subset of $L^1([0, 1])$.

b.  Let $Λ$ be a continuous linear functional on $L^1([0, 1])$.
  
    Prove the Riesz Representation Theorem for $L^1([0, 1])$ by following the steps below:


    i. Establish the existence of a function $g ∈ L^2([0, 1])$ which represents $Λ$ in the sense that
    $$
    Λ(f ) = f (x)g(x) dx \text{ for all } f ∈ L^2([0, 1]).
    $$

    > Hint: You may use, without proof, the Riesz Representation Theorem for $L^2([0, 1])$.

    ii. Argue that the $g$ obtained above must in fact belong to $L^∞([0, 1])$ and represent $Λ$ in the sense that
    $$
    \Lambda(f)=\int_{0}^{1} f(x) \overline{g(x)} d x \quad \text { for all } f \in L^{1}([0,1])
    $$
    with
    $$
    \|g\|_{L^{\infty}([0,1])}=\|\Lambda\|_{L^{1}([0,1])\dual}
    $$

# Fall 2018

## 1
Let $f(x) = \frac 1 x$.
Show that $f$ is uniformly continuous on $(1, \infty)$ but not on $(0,\infty)$.

## 2
Let $E\subset \RR$ be a Lebesgue measurable set.
Show that there is a Borel set $B \subset E$ such that $m(E\setminus B) = 0$.

## 3
Suppose $f(x)$ and $xf(x)$ are integrable on $\RR$.
Define $F$ by
$$
F(t):=\int_{-\infty}^{\infty} f(x) \cos (x t) d x
$$
Show that 
$$
F^{\prime}(t)=-\int_{-\infty}^{\infty} x f(x) \sin (x t) d x.
$$


## 4
Let $f\in L^1([0, 1])$.
Prove that
$$
\lim_{n \to \infty} \int_{0}^{1} f(x) \abs{\sin n x} ~d x= \frac{2}{\pi} \int_{0}^{1} f(x) ~d x
$$

> Hint: Begin with the case that $f$ is the characteristic function of an interval.

## 5
Let $f \geq 0$ be a measurable function on $\RR$.
Show that
$$
\int_{\mathbb{R}} f=\int_{0}^{\infty} m(\{x: f(x)>t\}) d t
$$

## 6
Compute the following limit and justify your calculations:
$$
\lim_{n \rightarrow \infty} \int_{1}^{n} \frac{d x}{\left(1+\frac{x}{n}\right)^{n} \sqrt[n]{x}}
$$

# Spring 2018

## 1
Define
$$
E:=\left\{x \in \mathbb{R}:\left|x-\frac{p}{q}\right|<q^{-3} \text { for infinitely many } p, q \in \mathbb{N}\right\}.
$$

Prove that $m(E) = 0$.

## 2
Let
$$
f_{n}(x):=\frac{x}{1+x^{n}}, \quad x \geq 0.
$$

a. Show that this sequence converges pointwise and find its limit. Is the convergence uniform on $[0, \infty)$?

b. Compute 
$$
\lim _{n \rightarrow \infty} \int_{0}^{\infty} f_{n}(x) d x
$$

## 3
Let $f$ be a non-negative measurable function on $[0, 1]$. 

Show that
$$
\lim _{p \rightarrow \infty}\left(\int_{[0,1]} f(x)^{p} d x\right)^{\frac{1}{p}}=\|f\|_{\infty}.
$$

## 4
Let $f\in L^2([0, 1])$ and suppose
$$
\int_{[0,1]} f(x) x^{n} d x=0 \text { for all integers } n \geq 0.
$$
Show that $f = 0$ almost everywhere.


## 5

Suppose that

- $f_n, f \in L^1$,
- $f_n \to f$ almost everywhere, and
- $\int\left|f_{n}\right| \rightarrow \int|f|$.

Show that $\int f_{n} \rightarrow \int f$

# Fall 2017

## 1
Let 
$$
f(x) = s \sum_{n=0}^{\infty} \frac{x^{n}}{n !}.
$$

Describe the intervals on which $f$ does and does not converge uniformly.

## 2
Let $f(x) = x^2$ and $E \subset [0, \infty) \definedas \RR^+$.

1. Show that
$$
m^*(E) = 0 \iff m^*(f(E)) = 0.
$$

2. Deduce that the map

\begin{align*}
\phi: \mathcal{L}(\RR^+) &\to \mathcal{L}(\RR^+) \\
E &\mapsto f(E)
\end{align*}
  is a bijection from the class of Lebesgue measurable sets of $[0, \infty)$ to itself.

## 3
Let 
$$
S = \spanof_\CC\theset{\chi_{(a, b)} \suchthat a, b \in \RR},
$$
the complex linear span of characteristic functions of intervals of the form $(a, b)$.

Show that for every $f\in L^1(\RR)$, there exists a sequence of functions $\theset{f_n} \subset S$ such that 
$$
\lim _{n \rightarrow \infty}\left\|f_{n}-f\right\|_{1}=0
$$

## 4
Let
$$
f_{n}(x)=n x(1-x)^{n}, \quad n \in \mathbb{N}.
$$

1. Show that $f_n \to 0$ pointwise but not uniformly on $[0, 1]$.
    
    > Hint: Consider the maximum of $f_n$.

2. 
$$
\lim _{n \rightarrow \infty} \int_{0}^{1} n(1-x)^{n} \sin x d x=0
$$

## 5
Let $\phi$ be a compactly supported smooth function that vanishes outside of an interval $[-N, N]$ such that $\int_{\mathrm{R}} \phi(x) d x=1$.

For $f\in L^1(\RR)$, define
$$
K_{j}(x):=j \phi(j x), \quad \quad f \ast K_{j}(x):=\int_{\mathbb{R}} f(x-y) K_{j}(y) ~d y
$$
and prove the following:

1. Each $f\ast K_j$ is smooth and compactly supported.

2. 
$$
\lim _{j \rightarrow \infty}\left\|f * K_{j}-f\right\|_{1}=0
$$

> Hint:
$$
\lim _{y \rightarrow 0} \int_{\mathbb{R}}|f(x-y)-f(x)| d y=0
$$


## 6
Let $X$ be a complete metric space and define a norm
$$
\|f\|:=\max \{|f(x)|: x \in X\}.
$$

Show that $(C^0(\RR), \norm{\wait} )$ (the space of continuous functions $f: X\to \RR$) is complete.

# Spring 2017

## 1

Let $K$ be the set of numbers in $[0, 1]$ whose decimal expansions do not use the digit $4$.

> We use the convention that when a decimal number ends with 4 but all other digits are
different from 4, we replace the digit $4$ with $399\cdots$. For example, $0.8754 = 0.8753999\cdots$.

Show that $K$ is a compact, nowhere dense set without isolated points, and find the
Lebesgue measure $m(K)$.

## 2

a. Let $\mu$ be a measure on a measurable space $(X, \mathcal M)$ and $f$ a positive measurable function.
  
    Define a measure $\lambda$ by
$$
\lambda(E):=\int_{E} f ~d \mu, \quad E \in \mathcal{M}
$$

    Show that for $g$ any positive measurable function, 
$$
\int_{X} g ~d \lambda=\int_{X} f g ~d \mu
$$

b. Let $E \subset \RR$ be a measurable set such that 
$$
\int_{E} x^{2} ~d m=0.
$$
  Show that $m(E) = 0$.

## 3

Let
$$
f_{n}(x)=a e^{-n a x}-b e^{-n b x} \quad \text{ where } 0 < a < b.
$$

Show that 

a. $\sum_{n=1}^{\infty}\left|f_{n}\right| \text { is not in } L^{1}([0, \infty), m)$

  > Hint: $f_n(x)$ has a root $x_n$.

b. 
$$
\sum_{n=1}^{\infty} f_{n} \text { is in } L^{1}([0, \infty), m) 
\quad \text { and } \quad 
\int_{0}^{\infty} \sum_{n=1}^{\infty} f_{n}(x) ~d m=\ln \frac{b}{a}
$$

## 4
Let $f(x, y)$ on $[-1, 1]^2$ be defined by 
$$
f(x, y) = \begin{cases}
\frac{x y}{\left(x^{2}+y^{2}\right)^{2}} & (x, y) \neq (0, 0) \\
0 & (x, y) = (0, 0)
\end{cases}
$$
Determine if $f$ is integrable.


## 5
Let $f, g \in L^2(\RR)$. 
Prove that the formula
$$
h(x):=\int_{-\infty}^{\infty} f(t) g(x-t) d t
$$
defines a uniformly continuous function $h$ on $\RR$.

## 5
Show that the space $C^1([a, b])$ is a Banach space when equipped with the norm
$$
\|f\|:=\sup _{x \in[a, b]}|f(x)|+\sup _{x \in[a, b]}\left|f^{\prime}(x)\right|.
$$

# Fall 2016 (Neil-ish)

## 1

Define
$$
f(x) = \sum_{n=1}^{\infty} \frac{1}{n^{x}}.
$$ 

Show that $f$ converges to a differentiable function on $(1, \infty)$ and that
$$
f'(x)  =\sum_{n=1}^{\infty}\left(\frac{1}{n^{x}}\right)^{\prime}.
$$

> Hint:
$$
\left(\frac{1}{n^{x}}\right)^{\prime}=-\frac{1}{n^{x}} \ln n
$$

## 2

Let $f, g: [a, b] \to \RR$ be measurable with
$$
\int_{a}^{b} f(x) ~d x=\int_{a}^{b} g(x) ~d x.
$$

Show that either

1. $f(x) = g(x)$ almost everywhere, or
2. There exists a measurable set $E \subset [a, b]$ such that
$$
\int_{E} f(x) ~d x>\int_{E} g(x) ~d x
$$


## 3

Let $f\in L^1(\RR)$.
Show that
$$
\lim _{x \rightarrow 0} \int_{\mathbb{R}}|f(y-x)-f(y)| d y=0
$$

## 4
Let $(X, \mathcal M, \mu)$ be a measure space and suppose $\theset{E_n} \subset \mathcal M$ satisfies
$$
\lim _{n \rightarrow \infty} \mu\left(X \backslash E_{n}\right)=0.
$$

Define
$$
G \definedas \theset{x\in X \suchthat x\in E_n \text{ for only finitely many  } n}.
$$

Show that $G \in \mathcal M$ and $\mu(G) = 0$.


## 5

Let $\phi\in L^\infty(\RR)$. Show that the following limit exists and satisfies the equality
$$
\lim _{n \rightarrow \infty}\left(\int_{\mathbb{R}} \frac{|\phi(x)|^{n}}{1+x^{2}} d x\right)^{\frac{1}{n}} = \norm{\phi}_\infty.
$$

## 6

Let $f, g \in L^2(\RR)$. Show that
$$
\lim _{n \rightarrow \infty} \int_{\mathbb{R}} f(x) g(x+n) d x=0
$$

# Spring 2016 (Neil-ish)

## 1
For $n\in \NN$, define
$$
e_{n}=\left(1+\frac{1}{n}\right)^{n} 
\quad \text { and } \quad 
E_{n}=\left(1+\frac{1}{n}\right)^{n+1}
$$

Show that $e_n < E_n$, and prove Bernoulli's inequality:
$$
(1+x)^{n} \geq 1+n x \text { for }-1<x<\infty \text { and } n \in \mathbb{N}
$$

Use this to show the following:

1. The sequence $e_n$ is increasing.
2. The sequence $E_n$ is decreasing.
3. $2 < e_n < E_n < 4$.
4. $\lim _{n \rightarrow \infty} e_{n}=\lim _{n \rightarrow \infty} E_{n}$.

## 2
Let $0 < \lambda < 1$ and construct a Cantor set $C_\lambda$ by successively removing middle intervals of length $\lambda$.

Prove that $m(C_\lambda) = 0$.

## 3
Let $f$ be Lebesgue measurable on $\RR$ and $E \subset \RR$ be measurable such that
$$
0<A=\int_{E} f(x) d x<\infty.
$$

Show that for every $0 < t < 1$, there exists a measurable set $E_t \subset E$ such that
$$
\int_{E_{t}} f(x) d x=t A.
$$

## 4
Let $E \subset \RR$ be measurable with $m(E) < \infty$. 
Define
$$
f(x)=m(E \cap(E+x)).
$$

Show that

1. $f\in L^1(\RR)$.
2. $f$ is uniformly continuous.
3. $\lim _{|x| \rightarrow \infty} f(x)=0$

> Hint: 
$$
\chi_{E \cap(E+x)}(y)=\chi_{E}(y) \chi_{E}(y-x)
$$

## 5
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

## 6
Without using the Riesz Representation Theorem, compute
$$
\sup \left\{\left|\int_{0}^{1} f(x) e^{x} d x\right| \suchthat f \in L^{2}([0,1], m),~~ \|f\|_{2} \leq 1\right\}
$$

# Fall 2015

## 1
Define
$$
f(x)=c_{0}+c_{1} x^{1}+c_{2} x^{2}+\ldots+c_{n} x^{n} \text { with } n \text { even and } c_{n}>0.
$$

Show that there is a number $x_m$ such that $f(x_m) \leq f(x)$ for all $x\in \RR$.


## 2
Let $f: \RR \to \RR$ be Lebesgue measurable.

1. Show that there is a sequence of simple functions $s_n(x)$ such that $s_n(x) \to f(x)$ for all $x\in \RR$.
2. Show that there is a Borel measurable function $g$ such that $g = f$ almost everywhere.

## 3
Compute the following limit:
$$
\lim _{n \rightarrow \infty} \int_{1}^{n} \frac{n e^{-x}}{1+n x^{2}} ~\sin \left(\frac x n\right) ~d x
$$

## 4
Let $f: [1, \infty) \to \RR$ such that $f(1) = 1$ and
$$
f^{\prime}(x)= \frac{1} {x^{2}+f(x)^{2}}
$$

Show that the following limit exists and satisfies the equality
$$
\lim _{x \rightarrow \infty} f(x) \leq 1 + \frac \pi 4
$$


## 5
Let $f, g \in L^1(\RR)$ be Borel measurable.

1. Show that 
  - The function $$F(x, y) \definedas f(x-y) g(y)$$ is Borel measurable on $\RR^2$, and
  - For almost every $y\in \RR$, $$F_y(x) \definedas f(x-y)g(y)$$ is integrable with respect to $y$.
2. Show that $f\ast g \in L^1(\RR)$ and
$$
\|f * g\|_{1} \leq\|f\|_{1}\|g\|_{1}
$$

## 6
Let $f: [0, 1] \to \RR$ be continuous.
Show that
$$
\sup \left\{\|f g\|_{1} \suchthat g \in L^{1}[0,1],~~ \|g\|_{1} \leq 1\right\}=\|f\|_{\infty}
$$

# Spring 2015

## 1
Let $(X, d)$ and $(Y, \rho)$ be metric spaces, $f: X\to Y$, and $x_0 \in X$.

Prove that the following statements are equivalent:

1. For every $\varepsilon > 0 \quad \exists \delta > 0$ such that $\rho( f(x), f(x_0)  ) < \varepsilon$ whenever $d(x, x_0) < \delta$.
2. The sequence $\theset{f(x_n)}_{n=1}^\infty \to f(x_0)$ for every sequence $\theset{x_n} \to x_0$ in $X$.

## 2
Let $f: \RR \to \CC$ be continuous with period 1. Prove that
$$
\lim _{N \rightarrow \infty} \frac{1}{N} \sum_{n=1}^{N} f(n \alpha)=\int_{0}^{1} f(t) d t \quad \forall \alpha \in \RR\setminus\QQ.
$$

> Hint: show this first for the functions $f(t) = e^{2\pi i k t}$ for $k\in \ZZ$.

## 3 

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

## 4
Define
$$
f(x, y):=\left\{\begin{array}{ll}{\frac{x^{1 / 3}}{(1+x y)^{3 / 2}}} & {\text { if } 0 \leq x \leq y} \\ {0} & {\text { otherwise }}\end{array}\right.
$$

Carefully show that $f \in L^1(\RR^2)$.


## 5
Let $\mathcal H$ be a Hilbert space.

1. Let $x\in \mathcal H$ and $\theset{u_n}_{n=1}^N$ be an orthonormal set.
  Prove that the best approximation to $x$ in $\mathcal H$ by an element in $\spanof_\CC\theset{u_n}$ is given by
  $$
  \hat x \definedas \sum_{n=1}^N \inner{x}{u_n}u_n.
  $$
2. Conclude that finite dimensional subspaces of $\mathcal H$ are always closed.


## 6
Let $f \in L^1(\RR)$ and $g$ be a bounded measurable function on $\RR$.

1. Show that the convolution $f\ast g$ is well-defined, bounded, and uniformly continuous on $\RR$.
2. Prove that one further assumes that $g \in C^1(\RR)$ with bounded derivative, then $f\ast g \in C^1(\RR)$ and
$$
\frac{d}{d x}(f * g)=f *\left(\frac{d}{d x} g\right)
$$

# Fall 2014

## 1
Let $\theset{f_n}$ be a sequence of continuous functions such that $\sum f_n$ converges uniformly.

Prove that $\sum f_n$ is also continuous.


## 2
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

## 3
Let $f\in L^1(\RR)$. Show that
$$
\forall\varepsilon > 0 ~~\exists \delta > 0 \text{ such that } m(E) < \delta \implies \int_{E}|f(x)| d x<\varepsilon
$$

## 4
Let $g\in L^\infty([0, 1])$
Prove that
$$
\int_{[0,1]} f(x) g(x) d x=0 \quad\text{for all continuous } f:[0, 1] \to \RR \implies g(x) = 0 \text{ almost everywhere. }
$$

## 5

1. Let $f \in C_c^0(\RR^n)$, and show
$$
\lim _{t \rightarrow 0} \int_{\mathbb{R}^{n}}|f(x+t)-f(x)| d x=0.
$$

2. Extend the above result to $f\in L^1(\RR^n)$ and show that
$$
f\in L^1(\RR^n),~ g\in L^\infty(\RR^n) \implies f \ast g \text{ is bounded and uniformly continuous. }
$$

## 6
Let $1 \leq p,q \leq \infty$ be conjugate exponents, and show that
$$
f \in L^p(\RR^n) \implies \|f\|_{p}=\sup _{\|g\|_{q}=1}\left|\int f(x) g(x) d x\right|
$$

# Spring 2014

## 1

1. Give an example of a continuous $f\in L^1(\RR)$ such that $f(x) \not\to 0$ as$\abs x \to \infty$.

2. Show that if $f$ is *uniformly* continuous, then
$$
\lim_{\abs x \to \infty} f(x) = 0.
$$

## 2
Let $\theset{a_n}$ be a sequence of real numbers such that
$$
\theset{b_n} \in \ell^2(\NN) \implies \sum a_n b_n < \infty.
$$
Show that $\sum a_n^2 < \infty$.

> Note: Assume $a_n, b_n$ are all non-negative.


## 3
Let $f: \RR \to \RR$ and suppose
$$
\forall x\in \RR,\quad f(x) \geq \limsup _{y \rightarrow x} f(y)
$$
Prove that $f$ is Borel measurable.


## 4
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

## 5
Let $f, g \in L^1([0, 1])$ and for all $x\in [0, 1]$ define
$$
F(x):=\int_{0}^{x} f(y) d y \quad \text { and } \quad G(x):=\int_{0}^{x} g(y) d y.
$$

Prove that
$$
\int_{0}^{1} F(x) g(x) d x=F(1) G(1)-\int_{0}^{1} f(x) G(x) d x
$$
