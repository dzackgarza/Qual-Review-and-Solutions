# Theorems

Theorem (Summation by Parts)
:   Define the forward difference operator $\Delta f_k = f_{k+1} - f_k$, then
    \begin{align*}
    \sum_{k=m}^n f_k \Delta g_k  + \sum_{k=m}^{n-1} g_{k+1}\Delta f_k = f_n g_{n+1} - f_m g_m
    .\end{align*}

    > Note: compare to $\int_a^b f \, dg  + \int_a^b g\, df = f(b) g(b) - f(a) g(a)$.

Theorem (Morera's Theorem)
: If $f$ is continuous on a domain $\Omega$ and $\int_T f = 0$ for every triangle $T\subset \Omega$, then $f$ is holomorphic.

Theorem (Cauchy Integral Formula)
:   Suppose $f$ is holomorphic on $\Omega$, then 

    \begin{align*}
    f(z) = {1 \over 2\pi i} \oint_{\bd \Omega}
    \end{align*}
    and
    \begin{align*}
    \dd{^nf }{z^n}(z) - {n! \over 2\pi i} \oint_{\bd \Omega} {f\xi \over (\xi - z)^{n+1}} \,d\xi
    .\end{align*}


Theorem (Cauchy's Inequality)
:   For $z_o \in D_R(z_0) \subset \Omega$, we have

    \begin{align*}
    \left|f^{(n)}\left(z_{0}\right)\right| \leq \frac{n !}{2 \pi} \int_{0}^{2 \pi} \frac{\|f\|_{C_{R}}}{R^{n+1}} R d \theta=\frac{n !\|f\|_{C_{R}}}{R^{n}} 
    .\end{align*}

Theorem (Liouville)
: If $f$ is entire and bounded, $f$ is constant.


Theorem (Argument Principle)
: ?

Theorem (Green's)
:   If $\Omega \subseteq \CC$ is bounded with $\bd \Omega$ piecewise smooth and $f, g\in C^1(\bar \Omega)$, then $$\int_{\bd \Omega} f\, dx + g\, dy = \iint_{\Omega} \qty{ \dd{g}{x} - \dd{f}{y} } \, dA.$$

Theorem (Rouche)
: If $f, g$ are analytic on a domain $\Omega$ with finitely many zeros in $\Omega$ and $\gamma \subset \Omega$ is a closed curve surrounding each point exactly once, where $\abs{g} < \abs{f}$ on $\gamma$, then $f$ and $f+g$ have the same number of zeros.

Example
:   \hfill 

    - Take $P(z) = z^4 + 6z + 3$.
    - On $\abs{z} < 2$:
      - Set $f(z) = z^4$ and $g(z) = 6z + 3$, then $\abs{g(z)} \leq 6\abs{z} + 3 = 15 < 16= \abs{f(z)}$.
      - So $P$ has 4 zeros here.
    - On $\abs{z} < 1$:
      - Set $f(z) = 6z$ and $g(z) = z^4 + 3$.
      - Check $\abs{g(z)} \leq \abs{z}^4 + 3 = 4 < 6 = \abs{f(z)}$.
      - So $P$ has 1 zero here.

Example
:   \hfill

    - Claim: the equation $\alpha z e^z = 1$ where $\abs{\alpha} > e$ has exactly one solution in $\DD$.
    - Set $f(z) = \alpha z$ and $g(z) = e^{-z}$.
    - Estimate at $\abs{z} =1$ we have $\abs{g} =\abs{e^{-z}} = e^{-\Re(z)} \leq e^1 < \abs{\alpha} = \abs{f(z)}$
    - $f$ has one zero at $z_0 = 0$, thus so does $f+g$.

Theorem (Open Mapping)
: Any holomorphic non-constant map is an open map.


Theorem (Maximum Modulus)
:   If $f$ is holomorphic and nonconstant on an open region $\Omega$, then $\abs{f}$ can not attain a maximum on $\Omega$.
    If $\Omega$ is bounded and $f$ is continuous on $\bar \Omega$, then $\max_{\bar \Omega} \abs{f}$ occurs on $\bd \Omega$.
  
    Conversely, if $f$ attains a local maximum at $z_0 \in \Omega$, then $f$ is constant on $\Omega$.


Theorem (Casorati-Weierstrass)
: If $f$ is holomorphic on $\Omega\setminus\theset{z_0}$ where $z_0$ is an essential singularity, then for every $V\subset \Omega\setminus\theset{z_0}$, $f(V)$ is dense in $\CC$.

Theorem (Cayley Transform)
: The fractional linear transformation given by $F(z) = {i - z \over i + z}$ maps $\DD\to \HH$ with inverse $G(w) = i {1-w \over 1 + w}$.

Theorem (Continuation Principle)
: If $f$ is holomorphic on a bounded connected domain $\Omega$ and there exists a sequence $\theset{z_i}$ with a limit point in $\Omega$ such that $f(z_i) = 0$, then $f\equiv 0$ on $\Omega$.


Theorem (Schwarz Reflection)
:   If $f$ is continuous and holomorphic on $\HH^+$ and real-valued on $\RR$, then the extension defined by $F(z) = \bar{f(\bar{z})}$ for $z\in \HH^-$ is a well-defined holomorphic function on $\CC$.

Note: $\HH^+, \HH^-$ can be replaced with any region symmetric about a line segment $L\subseteq \RR$.

Theorem (Schwarz Lemma)
:   If $f: \DD \to \DD$ is holomorphic with $f(0) = 0$, then

    1. $\abs{f(z)} \leq \abs z$ for all $z\in \DD$
    2. $\abs{f'(0)} \leq 1$.

    Moreover, if $\abs{f(z)} = \abs{z}$ for any $z$ or $\abs{f'(0)} = 1$, then $f$ is a rotation
