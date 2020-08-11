# $L^2$ and Fourier Analysis

## Spring 2020 # 6

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



## Fall 2017 # 5
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

## Spring 2017 # 5
Let $f, g \in L^2(\RR)$. 
Prove that the formula
\[
h(x) \definedas \int _{-\infty}^{\infty} f(t) g(x-t) \, dt
\]
defines a uniformly continuous function $h$ on $\RR$.

## Spring 2015 # 6
Let $f \in L^1(\RR)$ and $g$ be a bounded measurable function on $\RR$.

1. Show that the convolution $f\ast g$ is well-defined, bounded, and uniformly continuous on $\RR$.
2. Prove that one further assumes that $g \in C^1(\RR)$ with bounded derivative, then $f\ast g \in C^1(\RR)$ and
\[
\frac{d}{d x}(f * g)=f *\left(\frac{d}{d x} g\right)
\]

## Fall 2014 # 5

1. Let $f \in C_c^0(\RR^n)$, and show
\[
\lim _{t \to 0} \int_{\RR^n} |f(x+t) - f(x)| \, dx = 0
.\]

2. Extend the above result to $f\in L^1(\RR^n)$ and show that
\[
f\in L^1(\RR^n), \quad g\in L^\infty(\RR^n) \quad
\implies f \ast g \text{ is bounded and uniformly continuous. }
\]


