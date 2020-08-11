# Convergence Theorems

## Fall 2019 # 2. 

Prove that
$$
\left|\frac{d^{n}}{d x^{n}} \frac{\sin x}{x}\right| \leq \frac{1}{n}
$$

for all $x \neq 0$ and positive integers $n$.

> Hint: Consider $\displaystyle\int_0^1 \cos(tx) dt$

# $L^1$

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

## Spring 2020 # 3

a. Prove that if $g\in L^1(\RR)$ then
\[
\lim_{N\to \infty} \int _{\abs{x} \geq N} \abs{f(x)} \, dx = 0
,\]
and demonstrate that it is not necessarily the case that $f(x) \to 0$ as $\abs{x}\to \infty$.

b. Prove that if $f\in L^1([1, \infty])$ and is decreasing, then $\lim_{x\to\infty}f(x) =0$ and in fact $\lim_{x\to \infty} xf(x) = 0$.

c. If $f: [1, \infty) \to [0, \infty)$ is decreasing with $\lim_{x\to \infty} xf(x) = 0$, does this ensure that $f\in L^1([1, \infty))$?

# Fubini-Tonelli


