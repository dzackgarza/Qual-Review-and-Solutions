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


