# Integration

Notation:

- "$f$ vanishes at infinity" means $f(x) \converges{\abs x \to \infty}\to 0$.
- "$f$ has small tails" means $\int_{\abs{x} \geq N} f \converges{N\to \infty}\to 0$.

## Useful Techniques

- Break integration domain up into disjoint annuli.
- Break integrals or sums into $x < 1$ and $x\geq 1$.
- Calculus techniques: Taylor series, IVT, ...
- Approximate by dense subsets of functions

- Useful facts about compactly supported continuous functions:
  - Uniformly continuous
  - Bounded


## Definitions

Definition (\$L^+\$)
:	$f\in L^+$ iff $f$ is measurable and non-negative.

Definition (Integrable)
:	A measurable function is integrable iff $\norm{f}_1 < \infty$.

Definition (The Infinity Norm)
:   \hfill
    \begin{align*}
    \norm{f}_\infty &\definedas \inf_{\alpha \geq 0} \theset{\alpha \suchthat m\theset{\abs{f} \geq \alpha} = 0}
    .\end{align*}


Definition (Essentially Bounded Functions)
: A function $f:X \to \CC$ is *essentially bounded* iff there exists a real number $c$ such that $\mu(\theset{\abs{f} > x}) = 0$, i.e. $\norm{f}_\infty < \infty$.

If $f\in L^\infty(X)$, then $f$ is equal to some bounded function $g$ almost everywhere.

Definition (L infty)
:   \hfill

    \begin{align*}
    L^\infty(X) 
    \definedas \theset{f: X\to \CC \suchthat f \text{ is essentially bounded }}
    \definedas \theset{f: X\to \CC \suchthat \pnorm{f}\infty < \infty}
    ,\end{align*}

Example:

- $f(x) = x\chi_\QQ(x)$ is essentially bounded but not bounded.



## Theorems

Useful facts about $C_c$ functions:

- Bounded almost everywhere
- Uniformly continuous


Theorem (p-Test for Integrals)
:   \hfill
\begin{align*}
\int_0^1 x^{-p} < \infty \iff  p < 1 \\
\int_1^\infty x^{-p} < \infty \iff  p > 1 
.\end{align*}


###  Convergence Theorems

Theorem (Monotone Convergence)
:   If $f_n \in L^+$ and $f_n \nearrow f$ a.e., then
    $$
    \lim \int f_n
    = \int \lim f_n = \int f
    \quad \text{i.e.}~~ \int f_n \to \int f
    .$$

    > Needs to be positive and increasing.

Theorem (Dominated Convergence)

:   If $f_n \in L^1$ and $f_n \to f$ a.e. with $\abs {f_n} \leq g$ for some $g\in L^1$, then $f\in L^1$ and
    $$
    \lim \int f_n = \int \lim f_n = \int f \quad \text{i.e.}~~ \int f_n \to \int f < \infty
    ,$$

    and more generally,
    $$
    \int \abs{f_n - f} \to 0
    .$$

    > Positivity *not* needed.

Theorem (Generalized DCT)
:   If 
    
    - $f_n \in L^1$ with $f_n \to f$ a.e., 
    - There exist $g_n \in L^1$ with $\abs{f_n} \leq g_n$, $g_n \geq 0$.
    - $g_n\to g$ a.e. with $g\in L^1$, and 
    - $\lim \int g_n = \int g$, 

    then $f\in L^1$ and $\lim \int f_n = \int f < \infty$.

    > Note that this is the DCT with $\abs{f_n} < \abs{g}$ relaxed to $\abs{f_n} < g_n \to g\in L^1$.

Proof (Generalized DCT)
:   Proceed by showing $\limsup \int f_n \leq \int f \leq \liminf \int f_n$:

    - $\int f \geq \limsup \int f_n$:
    \begin{align*}
    \int g - \int f 
    &= \int \qty{g-f} \\
    &\leq \liminf \int \qty{g_n - f_n} \quad \text{Fatou} \\
    &= \lim \int g_n + \liminf \int (-f_n) \\
    &= \lim \int g_n - \limsup \int f_n \\
    &= \int g - \limsup \int f_n \\
    \\
    \implies \int f &\geq \limsup \int f_n
    .\end{align*}

      - Here we use $g_n - f_n \converges{n\to\infty} g-f$ with 

    - $\int f \leq \liminf \int f_n$:
    \begin{align*}
    \int g + \int f 
    &= \int(g+f) \\
    &\leq \liminf \int \qty{g_n + f_n} \\
    &= \lim \int g_n + \liminf \int f_n \\
    &= \int g + \liminf f_n \\
    \\
    \int f &\leq \liminf \int f_n
    .\end{align*}
  

Lemma
:   If $f\in L^1$, then
    \begin{align*}
    \int\abs{f_n - f} \to 0 \iff \int \abs{f_n} \to \abs{f}
    .\end{align*}

Proof 
:   Let $g_n = \abs{f_n} - \abs{f_n - f}$, then $g_n \to \abs{f}$ and 
    \begin{align*}
    \abs{g_n} = \abs{ \abs{f_n} - \abs{f_n - f} } \leq \abs{f_n - (f_n - f)} = \abs{f} \in L^1
    ,\end{align*}
    so the DCT applies to $g_n$ and
    \begin{align*}
    \norm{f_n - f}_1 = \int \abs{f_n - f} + \abs{f_n} - \abs{f_n}
    = \int \abs{f_n} - g_n\\
    \to_{DCT} \lim \int \abs{f_n} - \int \abs{f}
    .\end{align*}

Theorem (Fatou's)
:   If $f_n \in L^+$, then
    \begin{align*}
    \int \liminf_n f_n &\leq \liminf_n \int f_n \\
    \limsup_n \int f_n &\leq \int \limsup_n f_n
    .\end{align*}

Note that this has virtually no requirements (doesn't require positivity).

Theorem (Tonelli)
:   For $f(x, y)$ **non-negative and measurable**, for almost every $x\in \RR^n$, 

    - $f_x(y)$ is a **measurable** function
    - $F(x) = \int f(x, y) ~dy$ is a **measurable** function,
    - For $E$ measurable, the slices $E_x \definedas \theset{y \suchthat (x, y) \in E}$ are measurable.
    - $\int f = \int \int F$, i.e. any iterated integral is equal to the original.

Theorem (Fubini)
:   For $f(x, y)$ **integrable**, for almost every $x\in \RR^n$, 

    - $f_x(y)$ is an **integrable** function
    - $F(x) \definedas \int f(x, y) ~dy$ is an **integrable** function,
    - For $E$ measurable, the slices $E_x \definedas \theset{y \suchthat (x, y) \in E}$ are measurable.
    - $\int f = \int \int f(x,y)$, i.e. any iterated integral is equal to the original

Theorem (Fubini/Tonelli)
: If any iterated integral is **absolutely integrable**, i.e. $\int \int \abs{f(x, y)} < \infty$, then $f$ is integrable and $\int f$ equals any iterated integral.

Corollary (Measurable Slices)
:   Let $E$ be a measurable subset of $\RR^n$. Then

    - For almost every $x\in \RR^{n_1}$, the slice $E_x \definedas \theset{y \in \RR^{n_2} \mid  (x,y) \in E}$ is measurable in $\RR^{n_2}$.
    - The function

    \begin{align*}
    F: \RR^{n_1} &\to \RR \\
    x &\mapsto m(E_x) = \int_{\RR^{n_2}} \chi_{E_x} ~dy
    \end{align*}
    is measurable and 
    $$
    m(E) = \int_{\RR^{n_1}} m(E_x) ~dx 
    = \int_{\RR^{n_1}} \int_{\RR^{n_2}} \chi_{E_x} ~dy ~dx
    $$

Proof (Measurable Slices)
:   \hfill

    $\implies$:

    - Let $f$ be measurable on $\RR^n$.
    - Then the cylinders $F(x, y) = f(x)$ and $G(x, y) = f(y)$ are both measurable on $\RR^{n+1}$.
    - Write $\mathcal{A} = \theset{G \leq F} \intersect \theset{G \geq 0}$; both are measurable.


    $\impliedby$:

    - Let $A$ be measurable in $\RR^{n+1}$.
    - Define $A_x = \theset{y\in \RR \mid (x, y) \in \mathcal{A}}$, then $m(A_x) = f(x)$.
    - By the corollary, $A_x$ is measurable set, $x \mapsto A_x$ is a measurable function, and $m(A) = \int f(x) ~dx$.
    - Then explicitly, $f(x) = \chi_{A}$, which makes $f$ a measurable function.


Proposition (Differentiating Under an Integral)
:   If $\abs{\dd{}{t}f(x, t)} \leq g(x) \in L^1$, then letting $F(t) = \int f(x, t) ~dt$,
    \begin{align*}
    \dd{}{t} F(t)
    &\definedas \lim_{h \rightarrow 0} \int \frac{f(x, t+h)-f(x, t)}{h} d x \\
    &\equalsbecause{DCT} \int \dd{}{t} f(x, t) ~dx
    .\end{align*}

    To justify passing the limit, let $h_k \to 0$ be any sequence and define
    $$
    f_k(x, t) = \frac{f(x, t+h_k)-f(x, t)}{h_k}
    ,$$
    so $f_k \converges{\text{pointwise}}\to \dd{}{t}f$.

    Apply the MVT to $f_k$ to get $f_k(x, t) = f_k(\xi, t)$ for some $\xi \in [0, h_k]$, and show that $f_k(\xi, t) \in L_1$.


Proposition (Swapping Sum and Integral)
: If $f_n$ are non-negative and $\sum \int \abs f_n < \infty$, then $\sum \int f_n = \int \sum f_n$.

Proof
: MCT. Let $F_N = \sum^N f_n$ be a finite partial sum; then there are simple functions $\phi_n \nearrow f_n$ and so $\sum^N \phi_n \nearrow F_N$, so apply MCT.

Lemma
:   If $f_k \in L^1$ and $\sum \norm{f_k}_1 < \infty$ then $\sum f_k$ converges almost everywhere and in $L^1$.

Proof
:   Define $F_N = \sum^N f_k$ and $F = \lim_N F_N$, then $\norm{F_N}_1 \leq \sum^N \norm{f_k} < \infty$ so $F\in L^1$ and $\norm{F_N - F}_1 \to 0$ so the sum converges in $L^1$.
    Almost everywhere convergence: ?

## $L^1$ Facts

Lemma (Translation Invariance)
:   The Lebesgue integral is translation invariant, i.e. 
    $\int f(x) ~dx = \int f(x + h) ~dx$ for any $h$.

Proof
:   \hfill
    - For characteristic functions, $\int_E f(x+h) = \int_{E + h} f(x) = m(E+h) = m(E) = \int_E f$ by translation invariance of measure.
    - So this also holds for simple functions by linearity
    - For $f\in L^+$, choose $\phi_n \nearrow f$ so $\int \phi_n \to \int f$.
    - Similarly, $\tau_h \phi_n \nearrow \tau_h f$ so $\int \tau_h f \to \int f$
    - Finally $\theset{\int \tau_h \phi} = \theset{\int \phi}$ by step 1, and the suprema are equal by uniqueness of limits.

Lemma (Integrals Distribute Over Disjoint Sets)
: If $X \subseteq A \union B$, then $\int_X f \leq \int_A f + \int_{A^c} f$ with equality iff $X = A\disjoint B$.


Lemma (Unif. Cts. L1 Functions Vanish at Infinity)
: If $f \in L^1$ and $f$ is uniformly continuous, then $f(x) \converges{\abs{x}\to\infty}\to 0$.

> Doesn't hold for general $L^1$ functions, take any train of triangles with height 1 and summable areas.

Lemma (L1 Functions Have Small Tails)
: If $f\in L^1$, then for every $\varepsilon$ there exists a radius $R$ such that if $A = B_R(0)^c$, then $\int_A \abs f < \varepsilon$. 

Proof
:   Approximate with compactly supported functions.
    Take $g\converges{L_1}\to f$ with $g\in C_c$, then choose $N$ large enough so that $g=0$ on $E\definedas B_N(0)^c$, then $\int_E \abs{f} \leq \int_E\abs{f-g} + \int_E \abs{g}$.

Lemma (\$L^1\$ Functions Have Absolutely Continuity)
: $m(E) \to 0 \implies \int_E f \to 0$.

Proof
:   Approximate with compactly supported functions.
    Take $g\converges{L_1}\to f$, then $g \leq M$ so $\int_E{f} \leq \int_E{f-g} + \int_E g \to 0 + M \cdot m(E) \to 0$.

Lemma (\$L^1\$ Functions Are Finite Almost Everywhere)
: If $f\in L^1$, then $m(\theset{f(x) = \infty}) = 0$.

Proof 
:   Idea: Split up domain
    Let $A = \theset{f(x) = \infty}$, then $\infty > \int f = \int_A f + \int_{A^c} f = \infty \cdot m(A) + \int_{A^c} f \implies m(X) =0$.

Proposition (Continuity in \$L^1\$)
: $$\norm{\tau_h f - f}_1 \converges{h\to 0}\to 0$$

Proof
:   Approximate with compactly supported functions.
    Take $g\converges{L_1}\to f$ with $g\in C_c$.
    \begin{align*}
    \int f(x+h) - f(x) 
    &\leq \int f(x+h) - g(x+h) + \int g(x+h) - g(x) + \int g(x) - f(x) \\
    &\converges{?\to?}\to 2 \varepsilon + \int g(x+h) - g(x) \\
    &= \int_K g(x+h) - g(x) + \int_{K^c} g(x+h) - g(x)\\
    &\converges{??}\to 0
    ,\end{align*}
    which follows because we can enlarge the support of $g$ to $K$ where the integrand is zero on $K^c$, then apply uniform continuity on $K$.

Proposition (Integration by Parts, Special Case)
:   \begin{align*}
    F(x):=\int_{0}^{x} f(y) d y \quad \text { and } \quad G(x):=\int_{0}^{x} g(y) d y \\ 
    \implies
    \int_{0}^{1} F(x) g(x) d x=F(1) G(1)-\int_{0}^{1} f(x) G(x) d x
    .\end{align*}

Proof 
: Fubini-Tonelli, and sketch region to change integration bounds.

Theorem (Lebesgue Density)
: \begin{align*}
  A_{h}(f)(x):=\frac{1}{2 h} \int_{x-h}^{x+h} f(y) d y
  \implies \norm{A_h(f) - f} \converges{h\to 0}\to 0
  .\end{align*}

Proof
: Fubini-Tonelli, and sketch region to change integration bounds, and continuity in $L^1$.


## $L^p$ Spaces

Lemma
:   The following are dense subspaces of $L^2([0, 1])$:

    - Simple functions
    - Step functions
    - $C_0([0, 1])$
    - Smoothly differentiable functions $C_0^\infty([0, 1])$
    - Smooth compactly supported functions $C_c^\infty$
Theorem
:
\begin{align*}
m(X) < \infty \implies \lim_{p\to\infty} \norm{f}_p = \norm{f}_\infty 
.\end{align*}

Proof
:   \hfill
    - Let $M = \norm{f}_\infty$.
    - For any $L < M$, let $S = \theset{\abs{f} \geq L}$. 
    - Then $m(S) > 0$ and

    \begin{align*}
    \pnorm{f}p 
    &= \left( \int_X \abs{f}^p \right)^{\frac 1 p} \\
    &\geq \left( \int_S \abs{f}^p \right)^{\frac 1 p} \\
    &\geq L ~m(S)^{\frac 1 p} \converges{p\to\infty}\to L \\
    &\implies \liminf_p \pnorm{f}p \geq M
    .\end{align*}

    We also have
    \begin{align*}
    \pnorm{f}p 
    &=  \left( \int_X \abs{f}^p \right)^{\frac 1 p} \\
    &\leq \left( \int_X M^p \right)^{\frac 1 p} \\
    &= M ~m(X)^{\frac 1 p} \mapsvia{p\to\infty} M \\
    &\implies \limsup_p \pnorm{f}p \leq M \qed
    .\end{align*}


Theorem (Dual Lp Spaces)
:   For $p\neq \infty$, $(L^p)\dual \cong L^q$.

Proof (p=1)
: ?

Proof (p=2)
: Use Riesz Representation for Hilbert spaces.
 
Proof (\$p=\infty\$) 
: $L^1 \subset (L^\infty)\dual$, since the isometric mapping is always injective, but *never* surjective. 
So this containment is always proper (requires Hahn-Banach Theorem).
