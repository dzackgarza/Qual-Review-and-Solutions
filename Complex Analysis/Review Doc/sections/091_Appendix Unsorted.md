# Appendix

## Misc Basic Algebra


:::{.fact title="Standard forms of conic sections"}
\envlist

- Circle: $x^2 + y^2 = r^2$
- Ellipse: $\qty{\frac x a}^2  + \qty{\frac y b}^2 = 1$
- Hyperbola: $\qty{\frac x a}^2  - \qty{\frac y b}^2 = 1$
  - Rectangular Hyperbola: $xy = \frac{c^2}{2}$.
- Parabola: $-4ax + y^2 = 0$.

Mnemonic:
Write $f(x, y) = Ax^2 + Bxy + Cy^2 + \cdots$, then consider the discriminant $\Delta = B^2 - 4AC$:

- $\Delta < 0 \iff$ ellipse
  - $\Delta < 0$ and $A=C, B=0 \iff$ circle
- $\Delta = 0 \iff$ parabola
- $\Delta > 0 \iff$ hyperbola
:::

:::{.fact title="Completing the square"}
\[
x^2 - bx = (x - s)^2 - s^2 \quad\text{where} s = \frac{b}{2} \\
x^2 + bx = (x + s)^2 - s^2 \quad\text{where} s = \frac{b}{2}
.\]
:::

:::{.fact}
The sum of the interior angles of an $n\dash$gon is $(n-2)\pi$, where each angle is $\frac{n-2}{n}\pi$.
:::


:::{.definition title="The Dirichlet Problem"}
Given a bounded piecewise continuous function $u:S^1\to \RR$, is there a unique extension to a continuous harmonic function $\tilde u: \DD\to \RR$?

:::

:::{.remark}
More generally, this is a boundary value problem for a region where the *values* of the function on the boundary are given.
Compare to prescribing conditions on the normal vector on the boundary, which would be a Neumann BVP.
Why these show up: a harmonic function on a simply connected region has a harmonic conjugate, and solutions of BVPs are always analytic functions with harmonic real/imaginary parts.
:::

:::{.example title="Dirichlet problem on the strip"}
See section 27, example 1 in Brown and Churchill.
On the strip $(x, y)\in (0, \pi) \cross (0, \infty)$, set up the BVP for temperature on a thin plate with no sinks/sources:
\[
\laplacian T = 0 && T(0, y) = 0,\, T(\pi, y) = 0 \,\,\forall y \\ \\
T(x, 0) = \sin(x) && T(x, y) \converges{y\to\infty}\too 0
.\]

Then the following function is harmonic on $\RR^2$ and satisfies that Dirichlet problem:
\[
T(x ,y) = e^{-y} \sin(x) = \Re(-ie^{iz}) = \Im(e^{iz})
.\]
:::

:::{.definition title="Logarithmic Derivative"}
The **logarithmic derivative** of $f$ is $(\ln f)' = f'/f$.
:::

:::{.remark}
Why this is useful: deriving the argument principle.
If $f$ has a pole of order $n$ at $z_0$, then write $f(z) = (z-z_0)^{-n} g(z)$ with $g$ analytic in a neighborhood of $z_0$.
Then a direct computation of the derivatives will show
\[
(\ln f)' \da {f'(z) \over f(z)} = -{n\over z-z_0} + {g'(z) \over g(z)}
.\]
Thus
\[
{1\over 2\pi i } \int_\gamma (\ln f)' = -n
,\]
for $\gamma$ a small circle about $z_0$.
A similar argument for $z_0$ a **zero** of $f$ yields
\[
{1\over 2\pi i } \int_\gamma h = +n
.\]
:::



:::{.exercise title="?"}
Show that there is no continuous square root function defined on all of $\CC$.
:::

:::{.solution}
Suppose $f(z)^2 = z$. 
Then $f$ is a section to the covering map
\[
p: \CC\units &\to \CC\units \\
z & \mapsto z^2
,\]
so $p\circ f = \id$.
Using $\pi_1(\CC\units) = \ZZ$, the induced maps are $p_*(1) = 2$ and $f_*(1) = n$ for some $n\in \ZZ$.
But then $p_* \circ f_*$ is multiplication by $2n$, contradicting $p_* \circ f_* = \id$ by functoriality.
:::








