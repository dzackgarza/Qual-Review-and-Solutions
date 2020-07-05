# Functional Analysis

## Definitions

Notation: $H$ denotes a Hilbert space.

Definition (Orthonormal Sequence)
: ?

Definition (Basis)
: ?

Definition (Complete)
: A collection of vectors $\theset{u_n}\subset H$ is *complete* iff $\inner{x}{u_n} = 0$ for all $n \iff x = 0$ in $H$.

Definition (Dual Space)
: 
\begin{align*}
X\dual \definedas \theset{L :X\to \CC \suchthat L \text{ is continuous }}
.\end{align*}

Definition
:   A map $L: X \to \CC$ is a linear functional iff
    \begin{align*}
    L(\alpha\vector x + \vector y) = \alpha L(\vector x) + L(\vector y).
    .\end{align*}

Definition (Operator Norm)
: 
\begin{align*}
\norm{L}_{X\dual} \definedas \sup_{ \substack{x\in X \\ \norm{x} = 1} } \abs{L(x)}
.\end{align*}

Definition (Banach Space)
: A complete normed vector space.

Definition (Hilbert Space)
: An inner product space which is a Banach space under the induced norm.

## Theorems

Theorem (Bessel's Inequality)
:   \hfill
    \begin{align*}
    \left\|x-\sum_{n=1}^{N}\left\langle x, u_{n}\right\rangle u_{n}\right\|^{2}=\|x\|^{2}-\sum_{n=1}^{N}\left|\left\langle x, u_{n}\right\rangle\right|^{2}
    \end{align*}
    and thus
    \begin{align*}
    \sum_{n=1}^{\infty}\left|\left\langle x, u_{n}\right\rangle\right|^{2} \leq\|x\|^{2}
    .\end{align*}


Proof
:   \hfill 

    - Let $S_N = \sum_{n=1}^N \inner{x}{u_n} u_n$
    \begin{align*}
    \norm{x - S_N}^2 
    &= \inner{x - S_n}{x - S_N} \\
    &= \norm{x}^2 + \norm{S_N}^2 - 2\Re\inner{x}{S_N} \\
    &= \norm{x}^2 + \norm{S_N}^2 - 2\Re \inner{x}{\sum_{n=1}^N \inner{x}{u_n}u_n} \\
    &= \norm{x}^2 + \norm{S_N}^2 - 2\Re \sum_{n=1}^N \inner{x}{ \inner{x}{u_n}u_n} \\
    &= \norm{x}^2 + \norm{S_N}^2 - 2\Re \sum_{n=1}^N \overline{\inner{x}{u_n}}\inner{x}{u_n} \\
    &= \norm{x}^2 + \left\|\sum_{n=1}^N \inner{x}{u_n} u_n\right\|^2 - 2 \sum_{n=1}^N \abs{\inner{x}{u_n}}^2 \\
    &= \norm{x}^2 + \sum_{n=1}^N \abs{\inner{x}{u_n}}^2 - 2 \sum_{n=1}^N \abs{\inner{x}{u_n}}^2 \\
    &= \norm{x}^2 - \sum_{n=1}^N \abs{\inner{x}{u_n}}^2
    .\end{align*}

    - By continuity of the norm and inner product, we have
    \begin{align*}
    \lim_{N\to\infty} \norm{x - S_N}^2 
    &= \lim_{N\to\infty} \norm{x}^2 - \sum_{n=1}^N \abs{\inner{x}{u_n}}^2 \\
    \implies \norm{x - \lim_{N\to\infty} S_N}^2 &= \norm{x}^2 - \lim_{N\to\infty}\sum_{n=1}^N \abs{\inner{x}{u_n}}^2\\
    \implies 
    \norm{x - \sum_{n=1}^\infty \inner{x}{u_n} u_n}^2 &= \norm{x}^2 - 
    \sum_{n=1}^\infty \abs{\inner{x}{u_n}}^2
    .\end{align*}

    - Then noting that $0 \leq \norm{x - S_N}^2$, 
    \begin{align*}
    0 &\leq 
    \norm{x}^2 - 
    \sum_{n=1}^\infty \abs{\inner{x}{u_n}}^2 \\
    \implies 
    \sum_{n=1}^\infty \abs{\inner{x}{u_n}}^2 &\leq 
    \norm{x}^2 \qed
    .\end{align*}




Theorem (Riesz Representation for Hilbert Spaces)
:   If $\Lambda$ is a continuous linear functional on a Hilbert space $H$, then there exists a unique $y \in H$ such that
    \begin{align*}
    \forall x\in H,\quad \Lambda(x) = \inner{x}{y}.
    .\end{align*}

Proof
:   \hfill
    - Define $M \definedas \ker \Lambda$.
    - Then $M$ is a closed subspace and so $H = M \oplus M^\perp$
    - There is some $z\in M^\perp$ such that $\norm{z} = 1$.
    - Set $u \definedas \Lambda(x) z - \Lambda(z) x$
    - Check 

    $$\Lambda(u) = \Lambda(\Lambda(x) z - \Lambda(z) x) = \Lambda(x) \Lambda(z) - \Lambda(z) \Lambda(x) = 0 \implies u\in M$$

    - Compute

    \begin{align*}
    0 &= \inner{u}{z} \\ 
    &= \inner{\Lambda(x) z - \Lambda(z) x}{z} \\
    &= \inner{\Lambda(x) z}{z} - \inner{\Lambda(z) x}{z} \\
    &= \Lambda(x) \inner{z}{z} - \Lambda(z) \inner{x}{z} \\
    &= \Lambda(x) \norm{z}^2 - \Lambda(z) \inner{x}{z} \\
    &= \Lambda(x) - \Lambda(z) \inner{x}{z} \\
    &= \Lambda(x) -  \inner{x}{\overline{\Lambda(z)} z}
    ,\end{align*}

    - Choose $y \definedas \overline{\Lambda(z)} z$.
    - Check uniqueness:

    \begin{align*}
    \inner{x}{y} &= \inner{x}{y'} \quad\forall x \\
    \implies  \inner{x}{y-y'} &= 0 \quad\forall x \\
    \implies \inner{y-y'}{y-y'} &= 0 \\
    \implies \norm{y-y'} &= 0 \\
    \implies y-y' &= \vector 0 \implies y = y'
    .\end{align*}

Theorem (Continuous iff Bounded)
:   Let $L:X \to \CC$ be a linear functional, then the following are equivalent:

    1. $L$ is continuous
    2. $L$ is continuous at zero
    3. $L$ is bounded, i.e. $\exists c\geq 0 \suchthat \abs{L(x)} \leq c \norm{x}$ for all $x\in H$

Proof
:   \hfill
    $2 \implies 3$:
    Choose $\delta < 1$ such that 
    $$
    \norm{x} \leq \delta \implies \abs{L(x)} < 1.
    $$
    Then
    \begin{align*}
    \abs{L(x)} 
    &= \abs{L\left( \frac{\norm x}{\delta} \frac{\delta }{\norm x} x \right)} \\
    &= \frac{\norm x}{\delta} ~\abs{L\left( \delta \frac{x }{\norm x} \right)} \\
    &\leq \frac{\norm x}{\delta} 1
    ,\end{align*}
    so we can take $c = \frac 1 \delta$. $\qed$

    $3 \implies 1$:

    We have $\abs{L(x-y)} \leq c\norm{x-y}$, so given $\varepsilon \geq 0$ simply choose $\delta = \frac \varepsilon c$.

Theorem (Operator Norm is a Norm)
: If $H$ is a Hilbert space, then $(H\dual, \norm{\wait}_{\text{op}})$ is a normed space.

Proof
: The only nontrivial property is the triangle inequality, but
\begin{align*}
\norm{L_1 + L_2} = \sup \abs{L_1(x) + L_2(x)} \leq \sup L_1(x) + \sup L_2(x) = \norm{L_1} + \norm{L_2}
.\end{align*}

Theorem (Completeness in Operator Norm)
: If $X$ is a normed vector space, then $(X\dual, \norm{\wait}_{\text{op}})$ is a Banach space.

Proof
:   \hfill
    - Let $\theset{L_n}$ be Cauchy in $X\dual$.
    
    - Then for all $x\in C$, $\theset{L_n(x)} \subset \CC$ is Cauchy and converges to something denoted $L(x)$.
    
    - Need to show $L$ is continuous and $\norm{L_n - L} \to 0$.
    
    - Since $\theset{L_n}$ is Cauchy in $X\dual$, choose $N$ large enough so that
    \begin{align*}
    n, m \geq N \implies \norm{L_n - L_m} < \varepsilon \implies \abs{L_m(x) - L_n(x)} < \varepsilon \quad \forall x \suchthat \norm{x} = 1
    .\end{align*}
    
    - Take $n\to \infty$ to obtain
    \begin{align*}m \geq N 
    &\implies \abs{L_m(x) - L(x)} < \varepsilon \quad \forall x \suchthat \norm{x} = 1\\
    &\implies \norm{L_m - L} < \varepsilon \to 0
    .\end{align*}
    
    - Continuity:
    \begin{align*}
    \abs{L(x)} &= \abs{L(x) - L_n(x) + L_n(x)} \\
    &\leq  \abs{L(x) - L_n(x)} + \abs{L_n(x)} \\
    &\leq \varepsilon \norm{x} + c\norm{x} \\
    &= (\varepsilon + c)\norm{x} \qed
    .\end{align*}


