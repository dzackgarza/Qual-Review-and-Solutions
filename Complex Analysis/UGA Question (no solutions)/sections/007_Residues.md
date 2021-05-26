# Residues

## $\work$

:::{.problem title="?"}
Calculate
\[
\int_0^\infty {1 \over (1+z)^2 (z+9x^2)} \, dx
.\]
:::

## $\work$

:::{.problem title="?"}
Let $a>0$ and calculate
\[
\int_0^\infty {x\sin(x) \over x^2 + a^2} \,dx
.\]

:::


## $\work$

:::{.problem title="?"}
Calculate
\[
\int_0^\infty {\sqrt x \over (x+1)^2} \,dx
.\]

:::

## $\work$

:::{.problem title="?"}
Calculate
\[
\int_0^\infty {\cos(x) - \cos(4x) \over x^2} \, dx
.\]
:::

## $\work$

:::{.problem title="?"}
Let $a>0$ and calculate
\[
\int_0^\infty {x^2 \over (x^2 + a^2)^2} \, dx
.\]
:::

## $\work$

:::{.problem title="?"}
Calculate
\[
\int_0^\infty {\sin(x) \over x}\, dx
.\]
:::

## $\work$

:::{.problem title="?"}
Calculate
\[
\int_0^\infty {\sin(x) \over x(x^2+1)}\, dx
.\]

:::

## $\work$

:::{.problem title="?"}
Calculate
\[
\int_0^\infty {\sqrt x \over 1 + x^2} \, dx
.\]

:::

## $\work$

:::{.problem title="?"}
Calculate
\[
\int_{-\infty}^\infty {1+x^2 \over 1+x^4}\, dx
.\]

:::

## $\work$

:::{.problem title="?"}
Let $a>0$ and calculate
\[
\int_0^\infty {\cos(x) \over (x^2 + a^2)^2}\, dx
.\]
:::

## $\work$

:::{.problem title="?"}
Calculate
\[
\int_0^\infty {\sin^3(x) \over x^3} \, dx
.\]
:::


## $\work$

:::{.problem title="?"}
Let $n\in \ZZ^{\geq 1}$ and $0<\theta<\pi$ and show that
\[
{1\over 2\pi i} \int_{\abs z = 2} {z^n \over 1 -3z\cos(\theta) + z^2} \,dz = {\sin(n\theta) \over \sin(\theta)}
.\]
:::


## $\work$

:::{.problem title="?"}
Suppose $a>b>0$ and calculate
\[
\int_0^{2\pi} {1 \over (a+b\cos(\theta))^2} \,d\theta
.\]

:::



# Extra Questions

## $\work$

:::{.problem title="?"}
Suppose that $f$ is an analytic function in the region $D$ which
contains the point $a$. Let
$$F(z)= z-a-qf(z),\quad \text{where}\quad q \ \text{is a complex
parameter}.$$ 

1.
Let $K\subset D$ be a circle with the center at
point $a$ and also we assume that $f(z)\not =0$ for $z\in K$. Prove
that the function $F$ has one and only one zero $z=w$ on the closed
disc $\bar{K}$ whose boundary is the circle $K$ if 
\[
\displaystyle{ |q|<\min_{z\in K} \frac{|z-a|}{|f(z)|}.}
.\]

2.
Let $G(z)$ be an analytic function on the disk $\bar{K}$. Apply
the residue theorem to prove that
\[
\displaystyle{ \frac{G(w)}{F'(w)}=\frac{1}{2\pi i}\int_K \frac{G(z)}{F(z)} dz,}
\]
where $w$ is the zero from (1).

:::

## $\work$

:::{.problem title="?"}
Evaluate 
\[
\displaystyle{ \int_{0}^{\infty}\frac{x\sin x}{x^2+a^2} \, dx }
.\]

:::

## $\work$

:::{.problem title="?"}
Show that 
$$
\displaystyle \int_0^\infty \frac{x^{a-1}}{1+x^n} dx=\frac{\pi}{n\sin \frac{a\pi}{n}}
$$ 
using complex analysis, $0< a <
n$. Here $n$ is a positive integer.

:::


## $\done$

:::{.problem title="?"}
Show that
\[
\int_0^{\infty} {\cos(x) \over x^2 + b^2}\dx = {\pi e^{-b} \over 2b}
.\]
:::

:::{.solution}
\envlist

- Let $I$ be the integral over $\RR$.
  Since $f(x)$ is even, the original integral is ${1\over 2}I$.

- Write $f(z) = e^{iz} / (z^2 + b^2)$.
  Take a semicircular contour $\Gamma \da \gamma_1 + \gamma_2$ where $\gamma_1$ is $[-R, R]$ on $\RR$ and $\gamma_2$ is the usual half-circle of radius $R$.

- Claim: $\int_{\gamma_2} f \converges{R\to\infty}\too 0$, so $\int_\Gamma \to \int_\RR f(z)$.
  - Easy estimate, just be careful with the $i$ in the exponent:
  \[
  \abs{f} = { \abs{e^{iz} } \over \abs{z^2 + b^2} } = {e^{-\Re z} \over \abs{z^2 + b^2} } \leq {1\over \abs{z^2 + b^2}} \converges{R\to\infty}\too 0
  .\]

- Compute $\int_\Gamma f$ by residues: factor $z^2 + b^2 = (z+ib)(z-ib)$, so the contour only contains the order 1 pole $z_0 = ib$.

- Compute the residue:
\[
\Res_{z=ib}f = \lim_{z\to ib} (z-ib) {e^{iz} \over (z+ib)(z-ib) } = { e^{iz} \over z+ib} \evalfrom_{z=ib} = {e^{i(ib)} \over 2ib} = {e^{-b} \over 2ib}
.\]
- So the intermediate integral is $I$ is $2\pi i$ times this, i.e. $I = \pi e^{-b} / b$.
- And the original integral is ${1\over 2}I = \pi e^{-b} \over 2b$.

:::



