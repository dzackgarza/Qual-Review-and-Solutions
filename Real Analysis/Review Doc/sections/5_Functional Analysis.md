# Functional Analysis

Notation: $H$ denotes a Hilbert space.

Definition (Orthonormal Sequence)
: ?

Definition (Basis)
: ?

Definition (Complete)
: A collection of vectors $\theset{u_n}\subset H$ is *complete* iff $\inner{x}{u_n} = 0$ for all $n \iff x = 0$ in $H$.

Theorem (Bessel's Inequality)
:
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


