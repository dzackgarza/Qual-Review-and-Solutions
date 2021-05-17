# Zeros and Poles

:::{.definition title="Meromorphic"}
A function $f:\Omega\to\CC$ is *meromorphic* iff there exists a sequence $\theset{z_n}$ such that

- $\theset{z_n}$ has no limit points in $\Omega$.
- $f$ is holomorphic in $\Omega\setminus\theset{z_n}$.
- $f$ has poles at the points $\theset{z_n}$.

If $f$ is either holomorphic or has a pole at $z=\infty$ is said to be meromorphic on $\CP^1$.
:::

:::{.definition title="Poles (and associated terminology)"}
A *pole* $z_0$ of a meromorphic function $f(z)$ is a zero of $g(z) \definedas {1\over f(z)}$.
If there exists an $n$ such that
\[  
\lim_{z\to z_0}\qty{z-z_0}^nf(z)
\]
is holomorphic and nonzero in a neighborhood of $z_0$, then the minimal such $n$ is the *order* of the pole.
A pole of order 1 is said to be a *simple pole*.

The pole $z_0$ is *isolated* iff there exists a neighborhood of $z_0$ containing no other poles of $f$.
:::

:::{.definition title="Principal Part and Residue"}
In a Laurent series $f(z) \definedas \sum_{n\in \ZZ} c_n (z-z_0)^n$, the *principal part of $f$ at $z_0$* consists of terms with negative degree:
\[  
P_f(z) \definedas \sum_{n=1}^\infty c_{-n}(z-z_0)^{-n}
.\]

The *residue* of $f$ at $z_0$ is the coefficient $c_{-1}$.
:::

:::{.definition title="Removable Singularities"}
If $z_0$ is a singularity of $f$ and there exists a $g$ such that $f(z) = g(z)$ for all $z$ in some deleted neighborhood $U\setminus\theset{z_0}$, then $z_0$ is a *removable singularity* of $f$.
:::

:::{.definition title="Essential Singularity"}
A singularity $z_0$ is *essential* iff it is neither removable nor a pole.

Equivalently, a Laurent series expansion about $z_0$ has a principal part with infinitely many terms.
:::

## Counting Zeros 

:::{.example}
- Take $P(z) = z^4 + 6z + 3$.
- On $\abs{z} < 2$:
  - Set $f(z) = z^4$ and $g(z) = 6z + 3$, then $\abs{g(z)} \leq 6\abs{z} + 3 = 15 < 16= \abs{f(z)}$.
  - So $P$ has 4 zeros here.
- On $\abs{z} < 1$:
  - Set $f(z) = 6z$ and $g(z) = z^4 + 3$.
  - Check $\abs{g(z)} \leq \abs{z}^4 + 3 = 4 < 6 = \abs{f(z)}$.
  - So $P$ has 1 zero here.
:::

:::{.example}
- Claim: the equation $\alpha z e^z = 1$ where $\abs{\alpha} > e$ has exactly one solution in $\DD$.
- Set $f(z) = \alpha z$ and $g(z) = e^{-z}$.
- Estimate at $\abs{z} =1$ we have $\abs{g} =\abs{e^{-z}} = e^{-\Re(z)} \leq e^1 < \abs{\alpha} = \abs{f(z)}$
- $f$ has one zero at $z_0 = 0$, thus so does $f+g$.
:::
