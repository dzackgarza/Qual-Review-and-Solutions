# Appendix
\[
dz &= dx + i~dy \\
d\bar z &= dx - i~dy \\
f_z &= f_x = i\inv f_y \\
\int_{0}^{2 \pi} e^{i \ell x} d x
&=\left\{\begin{array}{ll}{2 \pi} & {(\ell=0)} \\ {0} & {(\ell \neq 0)}\end{array}\right.
.\]

## Misc Prereq

**Standard forms of conic sections:**

- Circle: $x^2 + y^2 = r^2$
- Ellipse: $\qty{\frac x a}^2  + \qty{\frac y b}^2 = 1$
- Hyperbola: $\qty{\frac x a}^2  - \qty{\frac y b}^2 = 1$
  - Rectangular Hyperbola: $xy = \frac{c^2}{2}$.
- Parabola: $-4ax + y^2 = 0$.

> Mnemonic:
> Write $f(x, y) = Ax^2 + Bxy + Cy^2 + \cdots$, then consider the discriminant $\Delta = B^2 - 4AC$:
>
> - $\Delta < 0 \iff$ ellipse
>   - $\Delta < 0$ and $A=C, B=0 \iff$ circle
> - $\Delta = 0 \iff$ parabola
> - $\Delta > 0 \iff$ hyperbola

**Completing the square:**

\[
x^2 - bx = (x - s)^2 - s^2 \quad\text{where} s = \frac{b}{2} \\
x^2 + bx = (x + s)^2 - s^2 \quad\text{where} s = \frac{b}{2}
.\]


**Useful Properties**

- $\Re(z) = \frac 1 2 (z + \bar z)$ and $\Im(z) = \frac{1}{2i}(z - \bar z)$.
- $z\bar z = \abs{z}^2$
- $\cos(\theta) = \frac 1 2 \qty{e^{i\theta} + e^{-i\theta}}$
- $\sin(\theta) = \frac{1}{2i}\qty{e^{i\theta} - e^{-i\theta}}$.

**Useful Series**

\[
\sum_{k=1}^{n} k &=\frac{n(n+1)}{2} \\
\sum_{k=1}^{n} k^{2} &=\frac{n(n+1)(2 n+1)}{6} \\
\sum_{k=1}^{n} k^{3} &=\frac{n^{2}(n+1)^{2}}{4}  \\
\log(z) &= \sum_{j=0}^\infty (-1)^j \frac{\qty{z-a}^j}{j}
\dd{}{z} \sum_{j=0}^\infty a_j z^j &= \sum_{j=0}^\infty a_{j+1}z^j
\]



