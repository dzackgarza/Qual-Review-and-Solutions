# Inequalities and Equalities

Proposition (Reverse Triangle Inequality)
:	\hfill
  \begin{align*}
  \abs{\norm{x} - \norm{y}} \leq \norm{x - y}
  .\end{align*}

Proposition (Chebyshev's Inequality)
:	\hfill
  \begin{align*}
  \mu(\{x:|f(x)|>\alpha\}) \leq\left(\frac{\pnorm{f}{p}}{\alpha}\right)^{p}
  .\end{align*}

Proposition (Holder's Inequality When Surjective)
:	\hfill
  \begin{align*}
  \frac 1 p + \frac 1 q = 1 \implies \pnorm{f g}{1} \leq \pnorm{f}{p} \pnorm{g}{q}
  .\end{align*}

*Application:*
For finite measure spaces,
\begin{align*}
1 \leq p < q \leq \infty \implies L^q \subset L^p \quad (\text{ and } \ell^p \subset \ell^q)
.\end{align*}

Proof (Holder's Inequality) 
: Fix $p, q$, let $r = \frac q p$ and $s = \frac{r}{r-1}$ so $r\inv + s\inv = 1$.
  Then let $h = \abs{f}^p$:
  
  \begin{align*}
  \pnorm{f}{p}^p 
  = \pnorm{h\cdot 1}1 \leq \pnorm{1}s \pnorm{h}r 
  = \mu(X)^{\frac 1 s} \pnorm{f}q^{\frac q r}
  \implies \pnorm{f}p 
  \leq \mu(X)^{\frac 1 p - \frac 1 q} \pnorm{f}q
  .\end{align*}

> Note: doesn't work for $\ell_p$ spaces, but just note that $\sum \abs{x_n} < \infty \implies x_n < 1$ for large enough $n$, and thus $p<q \implies \abs{x_n}^q \leq \abs{x_n}^q$.

Proof (Holder's Inequality)
:   It suffices to show this when $\norm{f}_p = \norm{g}_q = 1$, since

    \begin{align*}
    \|f g\|_{1} \leq\|f\|_{p}\|f\|_{q} \Longleftrightarrow \int \frac{|f|}{\|f\|_{p}} \frac{|g|}{\|g\|_{q}} \leq 1
    .\end{align*}

    Using $AB \leq \frac 1 p A^p + \frac 1 q B^q$, we have
    \begin{align*}
    \int|f \| g| \leq \int \frac{|f|^{p}}{p} \frac{|g|^{q}}{q}=\frac{1}{p}+\frac{1}{q}=1
    .\end{align*}


Proposition (Cauchy-Schwarz Inequality)
:	\hfill
  \begin{align*}
  \abs{\inner{f}{g}} = \pnorm{fg}1 \leq \pnorm{f}2 \pnorm{g}2
  \qtext{with equality} \iff f = \lambda g
  .\end{align*}

Note: Relates inner product to norm, and only happens to relate norms in $L^1$.

Proof
: ?

Proposition (Minkowski's Inequality:)
:	\hfill
  \begin{align*}
  1\leq p < \infty \implies \pnorm{f+g}{p} \leq \pnorm{f}{p}+ \pnorm{g}{p}
  .\end{align*}

> Note: does not handle $p=\infty$ case.
> Use to prove $L^p$ is a normed space.

Proof
:   \hfill

    - We first note
    \begin{align*}
    \abs{f+g}^p = \abs{f+g}\abs{f+g}^{p-1} \leq \left( \abs{f} + \abs{g}\right) \abs{f+g}^{p-1}
    .\end{align*}

    - Note that if $p,q$ are conjugate exponents then
    \begin{align*}
    \frac 1 q &= 1 - \frac 1 p = \frac{p-1} p \\
    q &= \frac p {p-1} 
    .\end{align*}

    - Then taking integrals yields
    \begin{align*}
    \norm{f+g}_p^p &=
    \int \abs{f+g}^p \\
    &\leq \int \left( \abs{f} + \abs{g}\right) \abs{f+g}^{p-1} \\ 
    &= \int \abs{f} \abs{f+g}^{p-1} + \int \abs{g} \abs{f+g}^{p-1} \\
    &= \norm{f(f+g)^{p-1}}_1 + \norm{g(f+g)^{p-1}}_1 \\
    &\leq \norm{f}_p ~\norm{(f+g)^{p-1})}_q + \norm{g}_p ~\norm{(f+g)^{p-1})}_q \\
    &= \left( \norm{f}_p + \norm{g}_p \right) \norm{ (f+g)^{p-1})}_q \\
    &= \left( \norm{f}_p + \norm{g}_p \right) \left( \int \abs{f+g}^{(p-1)q} \right)^{\frac 1 q} \\
    &= \left( \norm{f}_p + \norm{g}_p \right) \left( \int \abs{f+g}^{p} \right)^{1 - \frac 1 p} \\
    &= \left( \norm{f}_p + \norm{g}_p \right) \frac{\int \abs{f+g}^{p} }{\left( \int \abs{f+g}^{p} \right)^{\frac 1 p}} \\
    &= \left( \norm{f}_p + \norm{g}_p \right)  \frac{\norm{f+g}_p^p}{\norm{f+g}_p}
    \end{align*}

    - Cancelling common terms yields
    \begin{align*}
    1 &\leq \left( \norm{f}_p + \norm{g}_p \right) \frac{1}{\norm{f+g}_p} \\
    &\implies 
    \norm{f+g}_p
    \leq \norm{f}_p + \norm{g}_p 
    .\end{align*}


Proposition (Young's Inequality*)
:	  \hfill
    \[
    \begin{align*}
    \frac 1 p + \frac 1 q = \frac 1 r + 1 \implies
    \|f \ast g\|_{r} \leq\|f\|_{p}\|g\|_{q}
    .\end{align*}
    \]

**Application**:
Some useful specific cases:
\begin{align*}
\norm{f\ast g}_1      & \leq \norm{f}_1 \norm{g}_1 \\
\|f * g\|_{p}         & \leq \norm{f}_1 \norm{g}p, \\
\norm{f\ast g}_\infty & \leq \norm{f}_2 \norm{g}_2 \\
\norm{f\ast g}_\infty & \leq \norm{f}_p \norm{g}_q
.\end{align*}

Proposition (? Inequality)
:	\hfill
\begin{align*}
(a+b)^p \leq 2^p (a^p + b^p)
.\end{align*}

Proposition (Bezel's Inequality:)
:	\hfill

For $x\in H$ a Hilbert space and $\theset{e_k}$ an orthonormal sequence,
\begin{align*}
\sum_{k=1}^{\infty}\left|\left\langle x, e_{k}\right\rangle\right|^{2} \leq\|x\|^{2}
.\end{align*}

> Note: this does not need to be a basis.

Proposition (Parseval's Identity:)
:	Equality in Bessel's inequality, attained when $\theset{e_k}$ is a *basis*, i.e. it is complete, i.e. the span of its closure is all of $H$.

## Less Explicitly Used Inequalities

Proposition (AM-GM Inequality)
:	\hfill
  \begin{align*}
  \sqrt{ab} \leq \frac{a+b}{2}
  .\end{align*}


Proposition (Jensen's Inequality)
: \hfill
  \begin{align*}
  f(tx + (1-t)y) \leq tf(x) + (1-t)f(y)
  .\end{align*}

Proposition (???)
:
\begin{align*}
AB \leq {A^p \over p} + {B^q \over q}
.\end{align*}
