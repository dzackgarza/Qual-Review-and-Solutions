# Integrals: Approximation

## Spring 2018 # 3
Let $f$ be a non-negative measurable function on $[0, 1]$. 

Show that
$$
\lim _{p \rightarrow \infty}\left(\int_{[0,1]} f(x)^{p} d x\right)^{\frac{1}{p}}=\|f\|_{\infty}.
$$

## Spring 2018 # 4
Let $f\in L^2([0, 1])$ and suppose
$$
\int _{[0,1]} f(x) x^{n} d x=0 \text { for all integers } n \geq 0.
$$
Show that $f = 0$ almost everywhere.

## Spring 2015 # 2
Let $f: \RR \to \CC$ be continuous with period 1. 
Prove that
\[
\lim _{N \rightarrow \infty} \frac{1}{N} \sum_{n=1}^{N} f(n \alpha)=\int_{0}^{1} f(t) d t \quad \forall \alpha \in \RR\setminus\QQ.
\]

> Hint: show this first for the functions $f(t) = e^{2\pi i k t}$ for $k\in \ZZ$.


## Fall 2014 # 4
Let $g\in L^\infty([0, 1])$
Prove that
\[
\int _{[0,1]} f(x) g(x)\, dx = 0 
\quad\text{for all continuous } f:[0, 1] \to \RR 
\implies g(x) = 0 \text{ almost everywhere. }
\]


# $L^1$

## Spring 2020 # 3

a. Prove that if $g\in L^1(\RR)$ then
\[
\lim_{N\to \infty} \int _{\abs{x} \geq N} \abs{f(x)} \, dx = 0
,\]
and demonstrate that it is not necessarily the case that $f(x) \to 0$ as $\abs{x}\to \infty$.

b. Prove that if $f\in L^1([1, \infty])$ and is decreasing, then $\lim_{x\to\infty}f(x) =0$ and in fact $\lim_{x\to \infty} xf(x) = 0$.

c. If $f: [1, \infty) \to [0, \infty)$ is decreasing with $\lim_{x\to \infty} xf(x) = 0$, does this ensure that $f\in L^1([1, \infty))$?

## Fall 2019 # 5.

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

## Fall 2017 # 3
Let 
$$
S = \spanof_\CC\theset{\chi_{(a, b)} \suchthat a, b \in \RR},
$$
the complex linear span of characteristic functions of intervals of the form $(a, b)$.

Show that for every $f\in L^1(\RR)$, there exists a sequence of functions $\theset{f_n} \subset S$ such that 
$$
\lim _{n \rightarrow \infty}\left\|f_{n}-f\right\|_{1}=0
$$

## Spring 2015 # 4
Define
$$
f(x, y):=\left\{\begin{array}{ll}{\frac{x^{1 / 3}}{(1+x y)^{3 / 2}}} & {\text { if } 0 \leq x \leq y} \\ {0} & {\text { otherwise }}\end{array}\right.
$$

Carefully show that $f \in L^1(\RR^2)$.

## Fall 2014 # 3
Let $f\in L^1(\RR)$. Show that
\[
\forall\varepsilon > 0 \exists \delta > 0 \text{ such that } \qquad 
m(E) < \delta 
\implies 
\int _{E} |f(x)| \, dx < \varepsilon
\]

## Spring 2014 # 1

1. Give an example of a continuous $f\in L^1(\RR)$ such that $f(x) \not\to 0$ as$\abs x \to \infty$.

2. Show that if $f$ is *uniformly* continuous, then
\[
\lim_{\abs x \to \infty} f(x) = 0.
\]


# Fubini-Tonelli

## Spring 2020 # 4

Let $f, g\in L^1(\RR)$. 
Argue that $H(x, y) \definedas f(y) g(x-y)$ defines a function in $L^1(\RR^2)$ and deduce from this fact that
\[
(f\ast g)(x) \definedas \int_\RR f(y) g(x-y) \,dy
\]
defines a function in $L^1(\RR)$ that satisfies 
\[
\norm{f\ast g}_1 \leq \norm{f}_1 \norm{g}_1
.\]

## Spring 2019 # 4
Let $f$ be a non-negative function on $\RR^n$ and $\mathcal A = \{(x, t) ∈ \RR^n × \RR : 0 ≤ t ≤ f (x)\}$.

Prove the validity of the following two statements:

a. $f$ is a Lebesgue measurable function on $\RR^n \iff  \mathcal A$ is a Lebesgue measurable subset of $\RR^{n+1}$

b. If $f$ is a Lebesgue measurable function on $\RR^n$, then
\[
m(\mathcal{A})=\int _{\RR^{n}} f(x) d x=\int_{0}^{\infty} m\left(\left\{x \in \RR^{n}: f(x) \geq t\right\}\right) dt
\]

## Fall 2018 # 5
Let $f \geq 0$ be a measurable function on $\RR$.
Show that
$$
\int _{\RR} f = \int _{0}^{\infty} m(\{x: f(x)>t\}) dt
$$

## Fall 2015 # 5
Let $f, g \in L^1(\RR)$ be Borel measurable.

1. Show that 
  - The function $$F(x, y) \definedas f(x-y) g(y)$$ is Borel measurable on $\RR^2$, and
  - For almost every $y\in \RR$, $$F_y(x) \definedas f(x-y)g(y)$$ is integrable with respect to $y$.

2. Show that $f\ast g \in L^1(\RR)$ and
\[
\|f * g\|_{1} \leq \|f\|_{1} \|g\|_{1}
\]

## Spring 2014 # 5
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
