# Functional Analysis: General

## Fall 2019 # 4 $\done$
Let $\{u_n\}_{n=1}^∞$ be an orthonormal sequence in a Hilbert space $\mathcal{H}$.

a.
Prove that for every $x ∈ \mathcal H$ one has 
\[
\displaystyle\sum_{n=1}^{\infty}\left|\left\langle x, u_{n}\right\rangle\right|^{2} \leq\|x\|^{2}
\]

b.
Prove that for any sequence $\{a_n\}_{n=1}^\infty \in \ell^2(\NN)$ there exists an element $x\in\mathcal H$ such that 
\[
a_n = \inner{x}{u_n} \text{ for all } n\in \NN
\]
and
\[
\norm{x}^2 = \sum_{n=1}^{\infty}\left|\left\langle x, u_{n}\right\rangle\right|^{2}
\]

:::{.concept}
\envlist

- Bessel's Inequality
- Pythagoras
- Surjectivity of the Riesz map
- Parseval's Identity
- Trick -- remember to write out finite sum $S_N$, and consider $\norm{x - S_N}$.
:::

:::{.solution}
\envlist

:::{.proof title="of a"}
\envlist

- Equivalently, we can show
\[
\norm{x}^2 - \sum_{n=1}^\infty \abs{ \inner{x}{u_n} }^2 \geq 0
.\]

- Claim: the LHS is the norm of an element in $H$, and thus non-negative.
  More precisely, set $S_N\da \sum_{n=1}^N \inner{x}{u_n}u_n$, then the above is equal to
  \[
  \norm{x - \lim_{N\to\infty} S_N}^2
  .\]
  Note that if this is true, we're done.

- To see this, expand the norm in terms of inner products:
\[
  \norm{x - \lim_{N\to\infty} S_N}^2
  &= \inner{x-S_N}{x-S_N} \\
  &= \inner{x}{x} - \inner{x}{S_N} - \inner{S_N}{x} + \inner{S_N}{S_N} \\
  &= \norm{x}^2 + \norm{S_N}^2 - \qty{\inner{x}{S_N} + \conjugate{\inner{x}{S_N}} } \\
  &= \norm{x}^2 + \norm{S_N}^2 - 2\Re\qty{\inner x {S_N} } \\
  &= \norm{x}^2 + \norm{S_N}^2 - 2\Re\qty{ \inner{x} {\sum_{n=1}^N \inner{x}{u_n} u_n } } \\
  &= \norm{x}^2 + \norm{S_N}^2 - 2\Re\qty{ \sum_{n=1}^N \inner{x} {\inner{x}{u_n} u_n } } \\
  &= \norm{x}^2 + \norm{S_N}^2 - 2\Re\qty{ \sum_{n=1}^N \conjugate{\inner{x}{u_n} } \inner{x} {u_n } } \\
  &= \norm{x}^2 + \norm{S_N}^2 - 2\Re \sum_{n=1}^N \abs{\inner{x}{u_n} }^2 \\
  &= \norm{x}^2 + \norm{S_N}^2 - \sum_{n=1}^N \abs{\inner{x}{u_n} }^2 && \text{Magnitudes are real}\\
.\]


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


:::

:::{.proof title="of b"}
\envlist

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
by Pythagoras since the $u_k$ are orthogonal, where we've used normality in the last equality.

> Bonus: We didn't use completeness here, so the Fourier series may not actually converge to $x$.
If $\theset{u_n}$ is **complete** (so $x = 0 \iff \inner{x}{u_n} = 0 ~\forall n$) then the Fourier series *does* converge to $x$ and $\sum_{n=1}^{\infty}\left|\left\langle x, u_{n}\right\rangle\right|^{2}=\|x\|^{2}$ for all $x \in H$.

:::

:::


## Spring 2019 # 5 $\done$

a.
Show that $L^2([0, 1]) ⊆ L^1([0, 1])$ and argue that $L^2([0, 1])$ in fact forms a dense subset of $L^1([0, 1])$.

b.
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

:::{.concept}
\envlist

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

:::{.solution}
\envlist

:::{.proof title="of a"}
\envlist

- Note $X = [0, 1] \implies m(X) = 1$.
- By Holder's inequality with $p=q=2$, 
\[
\norm{f}_1 = \norm{f\cdot 1}_1 \leq \norm{f}_2 \cdot \norm{1}_2 = \norm{f}_2 \cdot m(X)^{\frac 1 2} = \norm{f}_2,
\]

- Thus $L^2(X) \subseteq L^1(X)$ 
- Since they share a common dense subset (simple functions), $L^2$ is dense in $L^1$ 


:::

Let $\Lambda \in L^1(X)\dual$ be arbitrary.

:::{.proof title="of b, Existence of $g$ representing $\Lambda$"}
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

:::

:::{.proof title="of b, $g$ is in $L^\infty$"}
\envlist

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
\envlist

:::{.proof title="of a"}
\envlist

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


:::

:::{.proof title="of b"}
\envlist

- It suffices to produce a Cauchy sequence that does not converge to a continuous function. 

- Take the following sequence of functions:
  - $f_1$ increases linearly from 0 to 1 on $[0, 1/2]$ and is 1 on $[1/2, 1]$
  - $f_2$ is 0 on $[0, 1/4]$ increases linearly from 0 to 1 on $[1/4, 1/2]$ and is 1 on $[1/2, 1]$
  - $f_3$ is 0 on $[0, 3/8]$ increases linearly from 0 to 1 on $[3/8, 1/2]$ and is 1 on $[1/2, 1]$
  - $f_3$ is 0 on $[0, (1/2 - 3/8)/2]$ increases linearly from 0 to 1 on $[(1/2 - 3/8)/2, 1/2]$ and is 1 on $[1/2, 1]$

  > Idea: take sequence starting points for the triangles: $0, 0 + {1\over 4}, 0 + {1 \over 4} + {1\over 8}, \cdots$ which converges to $1/2$ since $\sum_{k=1}^\infty{1\over 2^k} = -{1\over 2} + \sum_{k=0}^\infty  {1\over 2^k}$.


- Then each $f_n$ is clearly integrable, since its graph is contained in the unit square.
- $\theset{f_n}$ is Cauchy: geometrically subtracting areas yields a single triangle whose area tends to 0.
- But $f_n$ converges to $\chi_{[{1\over 2}, 1]}$ which is discontinuous.

\todo[inline]{show that $\int_0^1 \abs{f_n(x) - f_m(x)} \,dx \to 0$ rigorously, show that no $g\in L^1([0, 1])$ can converge to this indicator function.}

:::

:::


## Spring 2017 # 6 $\done$
Show that the space $C^1([a, b])$ is a Banach space when equipped with the norm
\[
\|f\|:=\sup _{x \in[a, b]}|f(x)|+\sup _{x \in[a, b]}\left|f^{\prime}(x)\right|.
\]

\todo[inline]{Add concepts.}

:::{.concept}
\hfill
- See 
<https://math.stackexchange.com/questions/507263/prove-that-c1a-b-with-the-c1-norm-is-a-banach-space/>
:::

:::{.solution}
\envlist

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

Let $\theset{f_k}$ be a Cauchy sequence, so $\norm{f_k} < \infty$ for all $k$.
Then for a fixed $x$, the sequence $f_k(x)$ is Cauchy in $\RR$ and thus converges to some $f(x)$, so define $f$ by $f(x) \definedas \lim_{k\to\infty} f_k(x)$.

Then $\norm{f_k - f} = \max_{x\in X}\abs{f_k(x) - f(x)} \converges{k\to\infty}\to 0$, and thus $f_k \to f$ uniformly and thus $f$ is continuous. It just remains to show that $f$ has bounded norm.

Choose $N$ large enough so that $\norm{f - f_N} < \varepsilon$, and write $\norm{f_N} \definedas M < \infty$

\[
\norm{f} \leq \norm{f - f_N} + \norm{f_N} < \varepsilon + M < \infty
.\]
:::


