
---
title: "Complex Analysis Qualifying Exam Solutions"
---

# Integrals and Cauchy's Theorem (8155d)


## 5

Show that there is no sequence of polynomials converging uniformly to $f(z) = 1/z$ on $S^1$.

Solution

- By Cauchy's integral formula, $\int_{S^1} f = 2\pi i$
- If $p_j$ is any polynomial, then $p_j$ is holomorphic in $\DD$, so $\int_{S^1} p_j = 0$.
- Contradiction: compact sets in $\CC$ are bounded, so 
  \begin{align*}
  \abs{\int f - \int p_j} \leq \int \abs{p_j - f} \leq \int \norm{p_j - f}_\infty  = \norm{p_j - f}_\infty \int_{S^1} 1 \,dz = \norm{p_j-f}_\infty \cdot 2\pi \to 0
  \end{align*}
  which forces $\int f = \int p_j = 0$.

## 9

- Note $f$ is continuous on $\CC$ since analytic implies continuous ($f$ equals its power series, where the partials sums uniformly converge to it, and uniform limit of continuous is continuous).
- Strategy: take $D$ a disc centered at a point $x\in \RR$, show $f$ is holomorphic in $D$ by Morera's theorem.
- Let $\Delta \subset D$ be a triangle in $D$.
- Case 1: If $\Delta \intersect \RR = 0$, then $f$ is holomorphic on $\Delta$ and $\int_\Delta f = 0$.
- Case 2: one side or vertex of $\Delta$ intersects $\RR$, and wlog the rest of $\Delta$ is in $\HH^+$.
  - Then let $\Delta_\eps$ be the perturbation $\Delta + i\eps = \theset{z+ i\eps \suchthat z\in \Delta}$; then $\Delta_\eps \intersect \RR = 0$ and $\int_{\Delta_\eps} f = 0$.
  - Now let $\eps\to 0$ and conclude by continuity of $f$ (???)
    - We want
    \begin{align*}
    \int_{\Delta_\eps} f = \int_a^b f(\gamma_\eps(t)) \gamma_\eps'(t)\,dt \converges{\eps\to 0}\to \int_a^b f(\gamma(t)) \gamma_\eps'(t)\,dt =\int_{\Delta}  f
    \end{align*}
    where $\gamma_\eps, \gamma$ are curves parametrizing $\Delta_\eps, \Delta$ respectively.
    - Since $\gamma, \gamma_\eps$ are closed and bounded in $\CC$, they are compact subsets. Thus it suffices to show that $f(\gamma_\eps(t)) \gamma_\eps'(t)$ converges uniformly to $f(\gamma(t))\gamma'(t)$.
    -  ??
- Case 3: $\Delta$ intersects both $\HH^+$ and $\HH^-$.
  - Break into smaller triangles, each of which falls into one of the previous two cases.

## 10

Suppose $f:\CC\to\CC$ is entire and bounded, and use Cauchy's theorem to prove that $f' \equiv 0$ and thus $f$ is constant.

Solution

- Suffices to prove $f' = 0$ because $\CC$ is connected (see Stein Ch 1, 3.4)
  - Idea: Fix $w_0$, show $f(w) = f(w_0)$ for any $w\neq w_0$
  - Connected = Path connected in $\CC$, so take $\gamma$ joining $w$ to $w_0$.
  - $f$ is a primitive for $f'$, and $\int_\gamma f' = f(w) - f(w_0)$, but $f'=0$.
- Fix $z_0\in \CC$, let $B$ be the bound for $f$, so $\abs{f(z)} \leq B$ for all $z$.
- Apply Cauchy inequalities: if $f$ is holomorphic on $U\supset \bar D_R(z_0)$ then setting $\norm{f}_C \definedas \sup_{z\in C} \abs{f(z)}$,
  \begin{align*}
  \abs{f^{(n)} (z_0)} \leq {n! \norm{f}_C \over R^n}
  .\end{align*}
  - Yields $\abs{ f'(z_0) } \leq B/R$
- Take $R\to \infty$, QED.



# Liouville's Theorem, Power Series (8155e)

## 1

Suppose $f$ is analytic on $\Omega \supseteq \DD$ whose power series $\sum a_n z^n$ has radius of convergence 1.

a. Give an example of an $f$ which converges at every point on $S^1$.
b. Give an example of an $f$ which is analytic at $z=1$ but $\sum a_n$ diverges.
c. Prove that $f$ can not be analytic at every point of $S^1$.


Solution:

a. Take $\sum {z^n \over n^2}$; then $\abs{z}\leq 1 \implies \abs{z^n\over n^2} \leq {1\over n^2}$ which is summable, so the series converges for $\abs{z}\leq 1$.

b. Take $\sum {z^n \over n}$; then $z=1$ yields the harmonic series, which diverges.
  
    - For $z\in S^1\setminus\theset{1}$, we have $z = e^{2\pi it}$ for $0<t<2\pi$. 
    - So fix $t$.
    
    - Toward applying the Dirichlet test, set $a_n = 1/n, b_n = z^n$.
    
    - Then for all $N$,
    \begin{align*}
    \abs{\sum_{n=1}^N b_n}
    = \abs{\sum_{n=1}^N b_n}
    = \abs{\sum_{n=1}^N z^n}
    = \abs{  {z-z^{N+1} \over \abs{1 - z}} } 
    \leq {2 \over 1-z} < \infty
    .\end{align*}
    
    - Thus $\sum a_n b_n < \infty$ and $\sum z^n/n$ converges.

c. ?


## 5

Prove the Fundamental Theorem of Algebra: every non-constant polynomial $p(z) = a_nz^n + \cdots + a_0 \in \CC[x]$ has a root in $\CC$.

Solution:

- Strategy: By contradiction with Liouville's Theorem
- Suppose $p$ is non-constant and has no roots.
- Claim: $1/p(z)$ is a bounded holomorphic function on $\CC$.
  - Holomorphic: clear? Since $p$ has no roots.
  - Bounded: for $z\neq 0$, write
    \begin{align*}
    \frac{P(z)}{z^{n}}=a_{n}+\left(\frac{a_{n-1}}{z}+\cdots+\frac{a_{0}}{z^{n}}\right)
    .\end{align*}

  - The term in parentheses goes to 0 as $\abs{z}\to \infty$
  - Thus there exists an $R>0$ such that
    \begin{align*}
    \abs{z} > R \implies \abs{P(z) \over z^n} \geq c \definedas {\abs{a_n} \over 2}
    .\end{align*}

  - So $p$ is bounded below when $\abs{z} > R$
  - Since $p$ is continuous and has no roots in $\abs{z} \leq R$, it is bounded below when $\abs{z} \leq R$.
  - Thus $p$ is bounded below on $\CC$ and thus $1/p$ is bounded above on $\CC$.
- By Liouville's theorem, $1/p$ is constant and thus $p$ is constant, a contradiction.


## 6

Find all entire functions $f$ which satisfy the following inequality, and prove the list is complete:
\begin{align*}
\abs{f(z)} \geq \abs z
.\end{align*}

Solution:

- Suppose $f$ is entire and define $g(z) \definedas {z \over f(z)}$.
- By the inequality, $\abs{g(z)} \leq 1$, so $g$ is bounded.
- $g$ potentially has singularities at the zeros $Z_f \definedas f\inv(0)$, but since $f$ is entire, $g$ is holomorphic on $\CC\setminus Z_f$.
- Claim: $Z_f = \theset{0}$.
  - If $f(z) = 0$, then $\abs{z} \leq \abs{f(z)} = 0$ which forces $z=0$.
- We can now apply Riemann's removable singularity theorem:
  - Check $g$ is bounded on some open subset $D\smz$, clear since it's bounded everywhere
  - Check $g$ is holomorphic on $D\smz$, clear since the only singularity of $g$ is $z=0$.
- By Riemann's removable singularity theorem, the singularity $z = 0$ is removable and $g$ has an extension to an entire function $\tilde g$.
- By continuity, we have $\abs{\tilde g(z)} \leq 1$ on all of $\CC$
  - If not, then $\abs{\tilde g(0)} = 1+\eps > 1$, but then there would be a domain $\Omega \subseteq \CC\smz$ such that $1 < \abs{\tilde g(z)} \leq 1 +\eps$ on $\Omega$, a contradiction.
- By Liouville, $\tilde g$ is constant, so $\tilde g(z) = c_0$ with $\abs {c_0} \leq 1$
- Thus $f(z) = c_0\inv z \definedas cz$ where $\abs{c}\geq 1$

Thus all such functions are of the form $f(z) = cz$ for some $c\in \CC$ with $\abs{c}\geq 1$.

# Laurent Expansions and Singularities (8155f)

## 1

Let $f(z) = {z+1\over z(z-1)}$.

About $z=0$:

\begin{align*}
f(z) 
&= (z+1) \qty{- {1 \over z} + {1\over z-1} } \\
&=  -(z+1) \qty{{1\over z} + \sum_{n=0}^\infty z^n } \\
&= -(z+1)\sum_{n=-1}^\infty z^n \\
&= {1\over z} + 2\sum_{n=0}^\infty z^n \\
&= -{1\over z} -2 - 2z - 2z^2 - \cdots
.\end{align*}

About $z=1$:

\begin{align*}
f(z) 
&= \qty{(1-z) -2 \over 1-z} \qty{1 \over 1 - (1-z)} \\
&= \qty{1 - {2\over 1-z}} \sum_{n=0}^\infty (1-z)^n \\ 
&= \sum_{n=0}^\infty (1-z)^n - 2 \sum_{n=-1}^\infty (1-z)^n \\
&= -{2\over 1-z} - \sum_{n=0}^\infty (1-z)^n \\
&= {2\over z-1} + \sum_{n=0}^\infty (-1)^{n+1} (z-1)^n \\
&= {2\over z-1} - 1 + (z-1) - (z-1)^2 + \cdots
.\end{align*}


## 2

\begin{align*}
e^{1\over z} = \sum_{n=0}^\infty {1\over n!} \qty{1\over z}^n = 1 + {1\over z} + {1 \over 2z^2} + {1\over 6z^3} + \cdots
.\end{align*}

\begin{align*}
\cos\qty{1\over z} 
&= {1\over 2}\qty{ e^{i\over z} + e^{-{i\over z}} }  \\
&= {1\over 2} \sum_{n=0}^\infty {1\over n!}\qty{ \qty{i\over z}^n + \qty{-i \over z}^n  } \\
&= \sum_{n=0}^\infty {(-1)^n \over (2n)!} \qty{1\over z}^{2n}
.\end{align*}

## 8

Idea: show their $f-g$ is analytic by taking away all of the negative powers, and bounded by (c).

# Rouche's Theorem (8155h)

## 1

Note

- $f_1(z) = 1+z$, which has the single root $z=-1$ which is not inside $\abs{z} < 1$.
- $f_2(z) = 1 + z + {1\over 2}z^2 = (z - (1+i))(z- (1-i))$, and $\abs{1\pm i} = \sqrt 2 >1$.

- Note that $p_n(z) \converges{n\to\infty}e^z$ uniformly on any compact set.
- Let $r$ be arbitrary and fix $N \definedas \DD_r(0)$, then $p_n(z) \to e^z$ uniformly on $\bar{N}$.
- Set $g_n(z) \definedas p_n(z) / e^z$, then $g_n \to 1$ uniformly on $\bar N$.
- Choose $n\gg 0$ so that $\abs{f(z) - 1} < \eps < 1$ for all $z\in \bar{N}$.
- So take $h(z) = 1$, then on $\bd N$,?


## 2

> Multiple versions of Rouches theorem!

- Set $h(z) = 3z^2$ and $g(z) = z^3 + bz + b^2$.
- Then on $\abs{z} = 1$,
\begin{align*}
\abs{g(z)} \leq 1 + b + b^2 < 3 = 3\abs{z}^2 = \abs{3z^2} = \abs{h}
,\end{align*}
  so $g, h$ have the same number of roots in $\abs{z} \leq_? 1$.

- But $h$ evidently has two roots in this region.


## 4

- Set $h(z) = -4z^3$ and $g(z) = z^7 - 1$, then on $\abs{z} = 1$,
\begin{align*}
\abs{g(z)} = \abs{z^7 - 1} \leq 1 + 1 = 2 < 4 = \abs{-4z^3} = \abs{h(z)}
.\end{align*}

- So $h$ and $h+g$ have the same number of roots, but $h$ has three roots here.

 
