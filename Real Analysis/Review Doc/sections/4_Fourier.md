# Fourier Series and Convolution

Definition (Convolution)
: $$f * g(x)=\int f(x-y) g(y) d y .$$

Definition (Dilation)
: $$ \phi_{t}(x)=t^{-n} \phi\left(t^{-1} x\right).$$

Definition (The Fourier Transform)
: \begin{align*}
  \hat f(\xi) = \int f(x) ~e^{2\pi i x \cdot \xi} ~dx
  .\end{align*}

Lemma
: $\hat f = \hat g \implies f=g$ almost everywhere.

Lemma (Riemann-Lebesgue)
: \hfill

  \begin{align*}
  f\in L^1 \implies
  \hat{f}(\xi) \rightarrow 0 \text { as }|\xi| \rightarrow \infty
  .\end{align*}

    > Motto: Fourier transforms have small tails.

Lemma
: If $f \in L^1$, then $\hat f$ is continuous and bounded.

Proof
: $\abs{\hat f} \leq \int \abs{f}\cdot \abs{e^{\cdots}} \leq \norm{f}_1$, and the DCT shows that $\abs{\hat f(\xi_n) - \hat f(\xi)} \to 0$.

Lemma
: \hfill

  \begin{align*}
  r^{-1} \definedas p^{-1} + q^{-1} - 1 \implies \norm{f \ast g}_r \leq \norm{f}_p \norm{g}_q
  .\end{align*}
  
- Useful variant - take $q = 1$ to get $\norm{f \ast g}_p \leq \norm{f}_p \norm{g}_1$
- Take $p=1$ to show $L_1$ is closed under $\ast$.



Definition (Approximation to the Identity)
: ?
\begin{align*}
\phi(x) = e^{-\pi x^2} \\
\phi_t(x) = t^{-n} \phi(\frac x t)
.\end{align*}
