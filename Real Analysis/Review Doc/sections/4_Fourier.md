# Fourier Transform and Convolution

## The Fourier Transform

Definition (Convolution)
: $$f * g(x)=\int f(x-y) g(y) d y .$$


Definition (The Fourier Transform)
: \begin{align*}
  \hat f(\xi) = \int f(x) ~e^{2\pi i x \cdot \xi} ~dx
  .\end{align*}

Lemma
: If $\hat f = \hat g$ then $f=g$ almost everywhere.

Lemma (Riemann-Lebesgue: Fourier transforms have small tails)
: 
\begin{align*}
f\in L^1 \implies
\hat{f}(\xi) \rightarrow 0 \text { as }|\xi| \rightarrow \infty
.\end{align*}

Lemma
: If $f \in L^1$, then $\hat f$ is continuous and bounded.

Proof
:   \hfill 
    - Boundedness:
    \begin{align*}
    \abs{\hat f(\xi)} 
    \leq \int \abs{f}\cdot \abs{e^{2\pi i x\cdot \xi }} 
    = \pnorm{f}{1}
    .\end{align*}

    - Continuity:
      - Apply DCT to show $\abs{\hat f(\xi_n) - \hat f(\xi)} \converges{n\to\infty}\to 0$.


Theorem (Fourier Inversion)
:   \hfill
    \begin{align*}
    f(x)=\int_{\mathbb{R}^{n}} \widehat{f}(x) e^{2 \pi i x \cdot \xi} d \xi
    .\end{align*}

Proof
:   Idea: Fubini-Tonelli doesn't work directly, so introduce a convergence factor, take limits, and use uniqueness of limits.

    - Take the modified integral:
    
    \begin{align*}
    I_t(x)
    &= \int \hat f(\xi) ~e^{2\pi i x \cdot \xi} ~e^{-\pi t^2 \abs{\xi}^2} \\
    &= \int \hat f(\xi) \phi(\xi) \\
    &= \int f(\xi) \hat \phi(\xi) \\
    &= \int f(\xi) \widehat{\hat g}(\xi - x) \\
    &= \int f(\xi) g_t(x - \xi)  ~d\xi \\
    &= \int f(y-x) g_t(y) ~dy  \quad (\xi = y-x)\\
    &= (f \ast g_t) \\
    &\to f \text{ in $L^1$ as }t \to 0
    .\end{align*}

    - We also have
    \begin{align*}
    \lim_{t\to 0} I_t(x)
    &= 
    \lim_{t\to 0} \int \hat f(\xi) ~e^{2\pi i x \cdot \xi} ~e^{-\pi t^2 \abs{\xi}^2} \\
    &= 
    \lim_{t\to 0} \int \hat f(\xi) \phi(\xi) \\
    &=_{DCT} 
    \int \hat f(\xi) \lim_{t\to 0} \phi(\xi) \\
    &=
    \int \hat f(\xi) ~e^{2\pi i x \cdot \xi} \\
    .\end{align*}

    - So 
    \begin{align*}
    I_t(x) \to \int \hat f(\xi) ~e^{2\pi i x \cdot \xi} ~\text{ pointwise and }~\pnorm{I_t(x) - f(x)}{1} \to 0
    .\end{align*}

    - So there is a subsequence $I_{t_n}$ such that $I_{t_n}(x) \to f(x)$ almost everywhere
    - Thus $f(x) = \int \hat f(\xi) ~e^{2\pi i x \cdot \xi}$ almost everywhere by uniqueness of limits. 


Proposition (Eigenfunction of the Fourier Transform)
:
\begin{align*}
g(x) \definedas e^{-\pi \abs{t}^2} \implies \hat g(\xi) = g(\xi) \qtext{and} \\
\hat g_t(x) = g(tx) = e^{-\pi t^2 \abs{x}^2},
.\end{align*}

Proposition (Properties of the Fourier Transform)
: 
\begin{align*}
??? & ??
.\end{align*}

## Approximate Identities 

Definition (Dilation)
: 
\begin{align*}
\phi_{t}(x) = t^{-n} \phi\left(t^{-1} x\right)
.\end{align*}


Definition (Approximation to the Identity)
:   For $\phi\in L^1$, the dilations satisfy $\int \phi_t = \int \phi$, and if $\int \phi = 1$ then $\phi$ is an *approximate identity*. 
    
    Example: $\phi(x) = e^{-\pi x^2}$


Theorem (Convolution Against Approximate Identities Converge in \$L^1\$)
: 
\begin{align*}
\pnorm{f \ast \phi_t - f}{1} \converges{t\to 0}\to 0
.\end{align*}


Proof
: 
\begin{align*}
\norm{f - f\ast \phi_t}_1 
&= \int f(x) - \int f(x-y)\phi_t(y) ~dy dx \\
&= \int f(x)\int \phi_t(y) ~dy - \int f(x-y)\phi_t(y) ~dy dx \\
&= \int \int \phi_t(y)[f(x) - f(x-y)] ~dy dx \\
&=_{FT} \int \int \phi_t(y)[f(x) - f(x-y)] ~dx dy \\
&= \int \phi_t(y) \int f(x) - f(x-y) ~dx dy \\
&= \int \phi_t(y) \norm{f - \tau_y f}_1 dy \\
&= \int_{y < \delta} \phi_t(y) \norm{f - \tau_y f}_1 dy  +
\int_{y \geq \delta} \phi_t(y) \norm{f - \tau_y f}_1 dy \\
&\leq \int_{y < \delta} \phi_t(y) \varepsilon +
\int_{y \geq \delta} \phi_t(y) \left( \norm{f}_1 + \norm{\tau_y f}_1 \right) dy \quad\text{by continuity in } L^1 \\
&\leq \varepsilon + 
2\norm{f}_1 \int_{y \geq \delta} \phi_t(y) dy \\
&\leq \varepsilon + 2\norm{f}_1 \cdot \varepsilon \quad\text{since $\phi_t$ has small tails} \\
&\converges{\eps\to 0}\to 0 
.\end{align*}

Theorem (Convolutions Vanish at Infinity)
: 
\begin{align*}
f,g \in L^1 \text{ and  bounded}  \implies \lim_{|x| \rightarrow \infty} (f * g)(x) = 0
.\end{align*}

Proof
:   \hfill
    
    - Choose $M \geq f,g$.
    
    - By small tails, choose $N$ such that $\int_{B_N^c} \abs{f}, \int_{B_n^c} \abs{g} < \varepsilon$

    - Note 
    \begin{align*}
    \abs{f \ast g} \leq \displaystyle\int \abs{f(x-y)} ~\abs{g(y)} ~dy \definedas I
    .\end{align*}

    - Use $\abs{x} \leq \abs{x-y} + \abs{y}$, take $\abs{x}\geq 2N$ so either
    \begin{align*}
    \abs{x-y} \geq N \implies I \leq \int_{\theset{x-y \geq N}} \abs{f(x-y)}M ~dy\leq \varepsilon M \to 0
    \end{align*}
      then
    \begin{align*}
      \abs{y} \geq N \implies I \leq \int_{\theset{y \geq N}} M\abs{g(y)} ~dy\leq  M \varepsilon \to 0
    .\end{align*}


Proposition (Young's Inequality?)
:
\begin{align*}
{1\over r} \definedas {1\over p} + {1\over q} - 1 \implies \pnorm{f \ast g}{r} \leq \pnorm{f}{p} \norm{g}{q}
.\end{align*}

Corollary
: Take $q = 1$ to obtain
\begin{align*}
\pnorm{f \ast g}p \leq \norm{f}p \norm{g}1
.\end{align*}

Corollary
: If $f, g \in L^1$ then $f\ast g\in L^1$.

