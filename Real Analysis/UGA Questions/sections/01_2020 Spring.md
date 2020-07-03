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
