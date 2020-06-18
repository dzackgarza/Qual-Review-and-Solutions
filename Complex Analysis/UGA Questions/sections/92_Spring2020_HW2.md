# Spring 2020 Homework 2

> Note on notation: I sometimes use $f_x \definedas \dd{f}{x}$ to denote partial derivatives, and $\bd_z^n f$ as $f^{(n)}(z)$.

# Stein And Shakarchi

## 2.6.1

Show that
\begin{align*}
\int_{0}^{\infty} \sin \left(x^{2}\right) d x=\int_{0}^{\infty} \cos \left(x^{2}\right) d x=\frac{\sqrt{2 \pi}}{4}
.\end{align*}

> Hint: integrate $e^{-x^2}$ over the following contour, using the fact that $\int_{-\infty}^{\infty} e^{-x^{2}} d x=\sqrt{\pi}$:


![Image](figures/2020-02-03-13:51.png)\

**Solution:**

Consider $f(z) = e^{-z^2}$; since $f$ is entire we have $\oint_\gamma f(z)~dz = 0$ for every closed curve $\gamma$.
In particular, the integral around the following path $\gamma \definedas \gamma_1 \ast \gamma_2 \ast \gamma_3$ (denoting concatenated paths) is zero for any radius $R$:


![Image](figures/2020-02-05-21:12.png)\

Let $I_i$ denote $\int_{\gamma_i} f(z) ~dz$.
Then 
$$
I_1 \converges{R\to\infty}\to \int_0^\infty e^{-x^2}~dx = \frac  1 2 \sqrt{\pi}
$$ 
by the hint, using the fact that $g(x) = e^{-x^2}$ is even.

**Claim:** 
$$I_2 \converges{R\to\infty}\to 0.$$

Parameterize $\gamma_2$ as $\gamma_2(t) = Re^{it}$ where $t\in [0, \pi/4]$; then

\begin{align*}
\abs{I_2} 
&= \abs{ \int_{\gamma_2} f(z) ~dz} \\
&= \abs{ \int_0^{\pi/4} f(\gamma_2(t)) ~\gamma_2'(t) ~dt } \\
&= \abs{ \int_0^{\pi/4} e^{-\qty{ Re^{it}  }^2} iRe^{it} ~dt }\\
&\leq \int_0^{\pi/4} \abs{ e^{-\qty{ Re^{it}  }^2} iRe^{it}} ~dt \\
&\leq \int_0^{\pi/4} \abs{ R e^{-R^2} e^{-\qty{e^{it}  }^2}}  ~dt \\
&= \abs{ Re^{-R^2}} ~\int_0^{\pi/4} \abs{ e^{-{ e^{2it}  }} } ~dt \\
&= \abs{R e^{-R^2} } \cdot C \\
&\to 0
,\end{align*}

where $C$ is a constant that does not depend on $R$.

To compute $I_3$, parameterize $\gamma_3(t) = te^{i\pi/4}$ with $t\in [0, R]$; then $\gamma_3'(t) = e^{i\pi/4}$.

For notational convenience, let $I_C = \int_0^\infty \cos\qty{t^2} ~dt$ and $I_S = \int_0^\infty \sin\qty{t^2}~dt$.

> Note that $I_C$ is the original integral we are looking for.

We then have

\begin{align*}
- I_3 
&= \int_{\gamma_3} f(z) ~dz \\
&= \int_0^R f(\gamma_3(t))~ \gamma_3'(t) ~dt \\
&= \int_0^R e^{-\qty{te^{i\pi/4}}^2} e^{i\pi/4} ~dt\\
&= e^{i\pi/4} \int_0^R e^{-it^2} ~dt \\
&= \frac{1+i}{\sqrt 2} \int_0^R \cos(t^2) - i\sin(t^2) ~dt\\
&\converges{R\to\infty}\longrightarrow 
\frac{1+i}{\sqrt 2} \qty{ I_C - i I_S} \\
&= \frac{1}{\sqrt 2} \qty{ I_C + I_S  } + \frac{i}{\sqrt 2 }\qty{I_C - I_S} \\
.\end{align*}

Since $0 = I_1 + I_2 + I_3$, we can write

\begin{align*}
0 &= \frac 1 2 \sqrt{\pi}  - \frac{1}{\sqrt 2} \qty{ I_C + I_S  } - \frac{i}{\sqrt 2 }\qty{I_C - I_S} 
.\end{align*}

Equating real and imaginary parts, we can conclude that $I_C = I_S$ (since the LHS is zero, and in particular has imaginary part zero), so this yields

\begin{align*}
\frac 1 2 \sqrt \pi = \frac 2 {\sqrt 2} I_C \implies I_C = \frac{\sqrt {2\pi}}{4} 
.\end{align*}

$\qed$


## 2.6.2

Show that

\begin{align*}
\int_{0}^{\infty} \frac{\sin x}{x} d x=\frac{\pi}{2}
.\end{align*}

> Hint: use the fact that this integral equals $\frac{1}{2 i} \int_{-\infty}^{\infty} \frac{e^{i x}-1}{x} d x$, and integrate around an indented semicircle.

**Solution:**

We'll proceed by integrating $f(z) = \frac{e^{iz} - 1}{z}$ along the following contour, which bounds a region in which $f$ is holomorphic:

![Image](figures/2020-02-07-21:15.png)\

Let $\Gamma$ be the curve enclosing the shown region, then

\begin{align*}
0 = \int_\Gamma f = \int_{\gamma_1} f + \int_{\sigma_1} f + \int_{\gamma_2} f + \int_{\sigma_2} f
.\end{align*}

Note that $\int_{\gamma_1} f + \int_{\gamma_2} f \to \int_{-\infty}^{\infty} f(x) ~dx$.

Claim 1:
$\int_{\sigma_1} f \to 0$.


\begin{align*}
\int_{\sigma_1} f(z) ~dz 
&= \int_{\sigma_1} \frac{e^{iz} - 1}{z} ~dz \\
&= \int_{\sigma_1} \frac{ \qty{1 + iz + O(z^3)} -1 }{z} ~dz \quad\text{by expanding $e^{iz}$ as a power series} \\
&= \int_{\sigma_1} i - O(z) ~dz \\
&= \int_0^\pi \qty{ i + O(\eps) } i\eps e^{i\theta} ~d\theta \quad\text{} \quad\text{writing $z=\eps e^{i\theta}$} \\
&= \int_0^\pi O(\eps) \\
&\converges{\eps \to 0}\to 0
.\end{align*}


*Claim 2:*
$\int_{\sigma_2} f \to -i\pi$.

\begin{align*}
\int_{\sigma_2} f(z) ~dz 
&= \int_0^\pi \frac{e^{iRe^{i\theta}} - 1}{Re^{i\theta}} \qty{iRe^{i\theta}} ~d\theta \\
&= i \int_0^\pi e^{iRe^{i\theta}} - 1 ~d\theta \\
&\leq i \int_0^\pi e^{i\Im\qty{ Re^{i\theta}} } - 1 ~d\theta \\
&= i \int_0^\pi e^{-R\sin(\theta)} - 1 ~d\theta \\
&= i \int_0^\pi e^{-R\qty{ \theta + O(\theta^3) }} - 1 ~d\theta \\
&= i e^{-R} \int_0^\pi e^{\theta + O(\theta^3)} ~d\theta - i \int_0^\pi ~d\theta\\
&\converges{R\to\infty}\to 0 -i\int_0^\pi ~d\theta \\
&= -i\pi
.\end{align*}

Taken together, this yields

\begin{align*}
0 &= \int_\RR f(x) ~dx -i\pi \\
\implies \int_{\RR} \frac{e^{ix} - 1}{x} &= i\pi \\
\implies \int_{\RR} \frac{\cos(z) - 1}{z} ~dz + i \int_\RR \frac{\sin(z)}{z} ~dz &= i \pi \\
\implies \int_\RR \frac{\sin(z)}{z} ~dz &= \pi \quad\text{equating imaginary parts} \\
\implies \int_0^\infty \frac{\sin(z)}{z} ~dz &= \frac{\pi}{2} \quad\text{since the integrand is even}
.\end{align*}

$\qed$

## 2.6.5

Suppose $f\in C_\CC^1(\Omega)$ and $T\subset \Omega$ is a triangle with $T^\circ \subset \Omega$.
Apply Green's theorem to show that $\int_T f(z) ~dz = 0$.

Assume that $f'$ is continuous and prove Goursat's theorem.

> Hint: Green's theorem states

\begin{align*}
\int_{T} F d x+G d y=\int_{T^\circ}\left(\frac{\partial G}{\partial x}-\frac{\partial F}{\partial y}\right) d x d y
.\end{align*}

**Solution:**
Let $T$ be such a triangle bounding a region $R$, so $\bd R = T$.
Since $f\in C^1_\CC(\Omega)$, $f_x, f_y$ exist on $\Omega$.
Since the partials are continuous, $f'(z)$ exists on $\Omega$, $f$ satisfies the Cauchy-Riemann equations on $\Omega$.

Thus
$$
\dd{f}{\bar z} = 0 \implies f_x = \frac 1 i f_y \implies if_x -f_y = 0
.$$

Since the partials are continuous, the conditions for Green's theorem are satisfied and we obtain

\begin{align*}
\int_T f ~dz 
&= \int_{\bd R} f \qty{dx + idy} \\
&= \int_{\bd R} f dx + if dy \\
&= \iint_R  \qty{ i f_x - f_y } ~dA \quad\text{by Green's theorem} \\
&= \iint_R 0 ~dA \quad\text{by observation above} \\
&= 0
.\end{align*}

Thus if $f$ is holomorphic with continuous partials on $\Omega$, then $\int_T f = 0$ for all such triangles, which is Goursat's theorem.

$\qed$

## 2.6.6

Suppose that $f$ is holomorphic on a punctured open set $\Omega\setminus\theset{w_0}$ and let $T\subset \Omega$ be a triangle containing $w_0$.
Prove that if $f$ is bounded near $w_0$, then $\int_T f(z) ~dz = 0$.


**Solution:**
Let $T_1$ be a triangle entirely contained in $T$ which still encloses $w_0$:

![Image](figures/2020-02-08-13:43.png)\

We can then triangulate the region between $T$ and $T_1$, and since $f$ is holomorphic on these shaded regions (since they do not contain $w_0$), $\int f$ vanishes along each such triangle.
Thus 
$$
\int_T f = \int_{T_1} f
.$$

Since $T_1$ still satisfies the hypotheses applying to $T$, replace $T$ with $T_1$ and continue this process inductively to obtain a sequence of triangles $T_k$ for $k\in \NN$.

Since $f$ is bounded, say by $M$, we can obtain the estimate

\begin{align*}
\int_{T} f = \int_{T_k} f \leq M \abs{T_k} \converges{k\to\infty}\to 0
,\end{align*}

since the perimeter of $T_k$ evidently goes to zero.

$\qed$

## 2.6.7

Suppose $f: \DD \to \CC$ is holomorphic and let $d \definedas \sup_{z, w\in \DD}\abs{f(z) - f(w)}$ be the diameter of the image of $f$.
Show that $2 \abs{f'(0)} \leq d$, and that equality holds iff $f$ is linear, so $f(z) = a_1 z + a_2$.

> Hint: $2f'(0) = \frac{1}{2\pi i} \int_{\abs \xi = r} \frac{ f(\xi) - f(-\xi)  }{\xi^2} ~d\xi$ whenever $0<r<1$.

**Solution:**

Let $0< r < 1$ and $C_r$ be a circle of radius $r$ centered at zero.
Let $g(\xi) = \frac{f(\xi) - f(-\xi)}{\xi^2}$, then as per the hint we have

\begin{align*}
\abs{2 f'(0)} 
&= \abs{ \frac 1 {2\pi i} \int_{C_r} g(\xi) ~d\xi}  \\
&\leq \frac{1}{2\pi} \int_{C_r} \abs{g(\xi)} ~d\xi \\
&\leq \frac{1}{2\pi } \sup_{\xi \in C_r} \abs{g(\xi)} ~\abs{C_r} \\
&\leq \frac{1}{2\pi} \frac{d}{r^2} \cdot 2\pi r \\
&= \frac{d}{r} \\
&\converges{r\to 1}\to d
,\end{align*}

which yields the desired inequality.

If $f$ is linear, so $f(z) = az + b$, noting that $g(\xi) = \frac{2a}{\xi}$ we find

\begin{align*}
2 f'(0) 
&\leq \frac 1 {2\pi i } \int_{C_r} g(\xi) ~d\xi \\
&= \frac{1}{2\pi i} \int_{C_r} \frac{2a}{\xi} ~d\xi \\
&= \frac {2a}{2\pi i} \int_{C_r} \frac 1 \xi ~d\xi \\
&= \frac{2a}{2\pi i} {2\pi i}  \\
&= 2a
,\end{align*}

where a direct computation shows that $2f'(0) = 2a$, making this an equality.

$\qed$


## 2.6.8

Suppose that $f$ is holomorphic on the strip $S = \theset{x+iy \suchthat x\in \RR,~ -1<y<1}$ with $\abs{f(z)} \leq A \qty{1 + \abs z}^\nu$ for $\nu$ some fixed real number.
Show that for all $z\in S$, for each integer $n\geq 0$ there exists an $A_n \geq 0$ such that $\abs{f^{(n)}(x)} \leq A_n (1 + \abs x)^\nu$ for all $x\in \RR$.

> Hint: Use the Cauchy inequalities.

Let $x\in \RR$, $0 < R < 1$, and $C_R = \theset{z\in \CC \suchthat \abs{z-x} = R}$ be a circle centered at $x$.
Note that if $z$ is in the region enclosed by $C_R$, we have 
$$
\abs{z} \leq \abs{x} + R \implies 1 + \abs{z} \leq 1 + \abs{x} + R
$$ 
by the triangle inequality.

We can then obtain the following estimate

\begin{align*}
\abs{f^{(n)}(x)} &
\leq \frac{n!}{R^n} \norm{f}_{C_R} \\
&\leq \frac{n!}{R^n} ~A \qty{1 + \abs{x} + R}^\nu \\
&\leq \frac{n!}{R^n} ~A \qty{ \qty{1+R} \qty{1+\abs x} }^\nu \quad\text{since $R, \abs{x}$ are positive}\\
&= \frac{n!}{R^n} ~A \qty{1+R}^\nu \qty{1+\abs x}^\nu \\
&\converges{R\to 1}\to {2^\nu} {An!}\qty{1 + \abs x}^\nu 
,\end{align*}

So taking $A_n \definedas {2^\nu} {An!}$ suffices.

$\qed$

## 2.6.9

Let $\Omega \subset \CC$ be open and bounded and $\phi: \Omega \to \Omega$ holomorphic.
Prove that if there exists a point $z_0 \in \Omega$ such that $\phi(z_0) = z_0$ and $\phi'(z_0) = 1$, then $\phi$ is linear.

> Hint: assume $z_0 = 0$ (explain why this can be done) and write $\phi(z)  = z + a_n z^n + O(z^{n+1})$ near $0$.
  Let $\phi_k = \phi \circ \phi \circ \cdots \circ \phi$ and prove that $\phi_k(z) = z + ka_nz^n  + O(z^{n+1})$.
  Apply Cauchy's inequalities and let $k\to \infty$ to conclude.


**Solution:**
WLOG, suppose $z_0 = 0$, since $z$ can be replaced with $z-z_0$ in what follows.
Since $\phi$ is holomorphic, it is analytic on $\Omega$, so it can be expanded in a power series in a neighborhood of $z_0 = 0$.

Suppose toward a contradiction that $\phi$ is *not* linear, in which case there is an $n\geq 2$ such that the power series expansion has the form

\begin{align*}
\phi(z) = z + a_n z^n + O(z^{n+1}) \quad\quad\textbf{ where } a_n \neq 0
,\end{align*}

where we've used the fact that $\phi(0) = 0 \implies a_0 = 0$ and $\phi'(0) = 1 \implies a_1 = 1$.

Then consider 

\begin{align*}
\phi_2(z) &= \phi \circ \phi (z) \\
&= \phi(z) + a_n \qty{ \phi(z)}^n + O(z^{n+1}) \\
&= z + a_n z^n + a_n\qty{ z + a_n z^n + O(z^{n+1})  }^n + O(z^{n+1}) \\
&= z + a_n z^n + a_n\sum_{k=0}^n (a_n z^n)^k z^{n-k} + O(z^{n+1}) \\
&= z + a_n z^n + a_n\qty{z^n + O\qty{z^{n^2}}  } + O(z^{n+1}) \\
&= z + 2a_n z^n + O(z^{n+1})
.\end{align*}

Inductively, this yields

\begin{align*}
\phi_k(z) &= z + k a_nz^n + O(z^{n+1})
,\end{align*}

and we can thus compute $\phi^{(n)}_k(z) = n! k a_n + O(z)$ and thus $\phi^{(n)}_k(0) = n! k a_n$.

Taking a circle of fixed radius $R \in (0, 1)$ centered at zero and applying the estimate from Cauchy's inequality, and noting since $\Omega$ is bounded and $\phi(\Omega) \subset \Omega$ implies that $\abs{ \phi(z) }$ is uniformly bounded by some $M$, we have

\begin{align*}
\abs{k a_n} &= \frac{1}{n!} \phi^{(n)}_k(0) \\
&\leq \frac{\norm{\phi_k}_{C_R}}{R^{n+1}} \\
&\leq \frac{M}{R^{n+1}} \\
\implies k \abs{a_n} &\leq \frac{M}{R^{n+1}} \definedas c_0 \quad\text{where $c_0$ is a fixed constant}\\
\implies \lim_{k\to\infty} k \abs{a_n} &\leq c_0
,\end{align*}

which forces $a_n = 0$, a contradiction.

$\qed$

## 2.6.10

Can every continuous function on $\bar \DD$ be uniformly approximated by polynomials in the variable $z$?

> Hint: compare to Weierstrass for the real interval.

**Solution:**
No; consider the function $f(z) = \bar z$.
This function is known to *not* be holomorphic, but since polynomials are entire, if $P_n(z) \to f$ uniformly on the compact set $\bar \DD$, this would force $f$ to be holomorphic as well.

## 2.6.13

Suppose $f$ is analytic, defined on all of $\CC$, and for each $z_0 \in \CC$ there is at least one coefficient in the expansion $f(z) = \sum_{n=0}^\infty c_n(z-z_0)^n$ is zero.
Prove that $f$ is a polynomial.

> Hint: use the fact that $c_n n! = f^{(n)}(z_0)$ and use a countability argument.


**Solution:**
Toward a contradiction, suppose that $f$ is not a polynomial, so $f^{(n)}(z) \not\equiv 0$ for any $n$.
Since $f$ is analytic, each $f^{(n)}$ is analytic, and analytic functions vanish for at most countably many values.
So for every $n\in \NN$, the following set is countable:

\begin{align*}
Z_n \definedas \theset{z_0 \in \CC \suchthat f^{(n)}(z_0) = 0}
.\end{align*}

But then we can define the following set:

\begin{align*}
Z \definedas \union_{n\in \NN} Z_n
,\end{align*}

which is a countable union of countable sets and thus countable.

However, by hypothesis, $\CC \subset Z$, which is a contradiction.
So $f^{(n)}(z) \equiv 0$ for some finite $n$, making $f$ a polynomial.

$\qed$

## 2.6.14

Suppose that $f$ is holomorphic in an open set containing $\DD$ except for a pole $z_0 \in \bd \DD$.
Let $\sum_{n=0}^\infty a_n z^n$ be the power series expansion of $f$ in $\DD$, and show that $\lim \frac{a_n}{a_{n+1}} = z_0$.

**Solution:**
Suppose $z_0$ is a pole of order $p$; we can then write 
$$f(z) = c(z_0 - z)^{-p} + g(z)$$ 
for some constant $C$ where $g(z)$ has no poles and is holomorphic on an open set $\Omega \supseteq \DD$.

Since $g$ is analytic on $\Omega$, write 
$$
g(z) = \sum_{n=0}^\infty b_n z^n
.$$

Since $\abs{z_0} = 1$, and in particular is not zero, division by $z_0$ is justified and we can take the following expansion:

\begin{align*}
f(z) 
&= \frac{c}{\qty{z_0 - z}^p} + \sum_{n=0}^\infty b_n z^n \\
&= \frac{c}{z_0^p} \qty{ \frac{1}{1 - \qty{\frac{z}{z_0}}} }^p + \sum_{n=0}^\infty b_n z^n \\
&= \frac{c}{z_0^p} \sum_{n=0}^\infty {p-1 + n \choose p-1} \qty{\frac{z}{z_0}}^n + \sum_{n=0}^\infty b_n z^n \\
&= \sum_{n=0}^\infty \left[ \frac{c}{z_0^{p+n}} {p-1 + n \choose p-1} + b_n \right] z^n 
.\end{align*}

Equating coefficients, we obtain

\begin{align*}
a_n = \frac{c}{z_0^{p+n}} {p-1 + n \choose p-1} + b_n 
.\end{align*}

We can then observe that ${n\choose k} / {n+1 \choose k} \converges{n\to\infty}\to 1$ for any $k$, which also holds for $n$ replaced by $n+c_0$ for any constant $c_0$.
Moreover, since $g(z)$ is holomorphic, $b_n \to 0$, so we can proceed to compute the ratio

\begin{align*}
\frac{a_n}{a_{n+1}} &=
\frac{
\frac{c}{z_0^{p+n}} {p-1 + n \choose p-1} + b_n 
}{
\frac{c}{z_0^{p+n+1}} {p-1 + n +1\choose p-1} + b_{n+1}
}\\ \\
&= 
\frac{
cz_0 {n+p-1 \choose p-1} + b_n z_0^{p+n+1} 
}{
c {(n+p-1) + 1 \choose p -1} + b_{n+1} z_0^{p+n+1}
} \\ \\
&\converges{n\to\infty}\to \lim_{n\to \infty}
\frac{
cz_0 {n+p-1 \choose p-1}
}{
c {(n+p-1) + 1 \choose p -1}
}  \quad\quad\text{passing the limit through the quotient and sums respectively} \\ \\
&= z_0 \lim_{n\to\infty }
\frac{
{n+p-1 \choose p-1}
}{
{(n+p-1) + 1 \choose p -1}
} \\ \\
&= z_0
.\end{align*}

$\qed$

## 2.6.15

Suppose $f$ is continuous and nonvanishing on $\bar \DD$, and holomorphic in $\DD$.
Prove that if $\abs{z} = 1 \implies \abs{f(z)} = 1$, then $f$ is constant.

> Hint: Extend $f$ to all of $\CC$ by $f(z) = 1/ \bar{f(1/\bar z)}$ for any $\abs{z} > 1$, and argue as in the Schwarz reflection principle.

**Solution:**
Since $f$ is continuous on a compact set, it is bounded.
We then make the following extension:

\begin{align*}
F: \CC &\to \CC \\
z &\mapsto
\begin{cases}
f(z) & z\in \bar\DD \\
{1}/{ \bar{f ({ {1}/{ \bar{z}} })  }} & z\in \CC\setminus \bar\DD
\end{cases}
.\end{align*}

We will now argue that $F$ is bounded and entire, and thus constant by Liouville's theorem.

Since $F$ is holomorphic on $\DD^\circ$ and $\qty{\DD^\circ}^c$ by construction, it remains to show that $F$ is also holomorphic on $\bd \DD$.
Let $z\in \bd\DD$ be a fixed point; then by Morera's theorem, $F$ will be holomorphic at $z$ if the contour integral around every rectangle containing $z$ vanishes.

Let $\Gamma$ be such a rectangle, and let $\Gamma_1, \Gamma_2$ be two contours that run along $\Gamma$ in the interior and exterior of the disc respectively, with circular arcs at radii $1\pm \eps$:

![Image](figures/2020-02-13-19:19.png)\

However, since $F$ is known to be holomorphic away from $\bd \DD$, 

\begin{align*}
\int_\Gamma F = \lim_{\eps \to 0} \qty{\int_{\Gamma_1} F + \int_{\Gamma_2} F} = \lim_{\eps \to 0} \qty{ 0 + 0 } = 0
.\end{align*}

$\qed$

# Additional Problems

## Problem 1

*Proposition:*
$L = \lim \abs{a_{n+1}}/\abs{a_n} \implies L = \lim \sqrt[n]{a_n}$

**Proof:**

> Following a proof by Pete.

WLOG, we'll take all terms to be positive and drop absolute values.

Since the ratios converge to $L$, we have

\begin{align*}
L = \lim \frac{a_{n+1}}{a_n} = \liminf \frac{a_{n+1}} {a_n}
.\end{align*}

Let $\eps$ be arbitrary and let $c_0 = L + \eps$, and let $R = \lim_{n\to\infty}\sqrt[n]{a_n}$.
Since the above limit exists, for $n$ large enough, that $\frac{a_{n+1}}{a_n} \leq c_0$.
Then

\begin{align*}
a_{n+1} &\leq c_0 a_n \\
\implies a_{n+k} &\leq c_0^k a_n \\
\implies a_{n+k} &\leq c_0^{n+k} \qty{\frac{a_n}{c_0^n}} \\
\implies \qty{a_{n+k}}^{\frac 1 {n+k}} &\leq c_0 \qty{  \frac{a_n}{c_0^n}}^{\frac 1 {n+k}}\\
\implies 
R 
= \lim_{n\to\infty} \qty{a_n}^{\frac 1 n} 
= \lim_{k\to\infty} \qty{a_{n+k}}^{\frac 1 {n+k}} 
&\leq \lim_{k\to\infty} c_0 \qty{  \frac{a_n}{c_0^n}}^{\frac 1 {n+k}} = c_0 = L + \eps\\
.\end{align*}

So $R \leq L + \eps$ for every $\eps>0$, and thus $R = L$.

$\qed$

## Problem 2

*Proposition:*
If $f$ is a power series centered at the origin, then $f$ has a power series expansion about any point in its domain.

**Proof:**
Let $D_R$ be the disc of convergence for $f$ and let $z_0 \in D_R$ and take a disc $z_0 \in D \subset D_R$. 
We can then find a power series expansion about $z_0$, namely

\begin{align*}
f(z)
&= \frac{1}{2\pi i } \int_{\bd D} \frac{f(\xi)}{\xi - z} ~d\xi \\
&= \frac{1}{2\pi i } \int_{\bd D} \frac{f(\xi)}{\xi - z_0 + z_0 - z} ~d\xi \\
&= \frac{1}{2\pi i } \int_{\bd D} f(\xi) \qty{ \frac{1}{\qty{\xi - z_0} - \qty{ z - z_0} }} ~d\xi \\
&= \frac{1}{2\pi i } \int_{\bd D} \frac{f(\xi)}{\xi - z_0} \qty{ \frac{1}{1 - \qty{ \frac{z - z_0}{\xi - z_0}  } }} ~d\xi \\
&= \frac{1}{2\pi i } \int_{\bd D} \frac{f(\xi)}{\xi - z_0} \sum_{j=0}^\infty   \qty{ \frac{z - z_0}{\xi - z_0}  }^j  ~d\xi \\
&= \frac{1}{2\pi i } \int_{\bd D} \sum_{j=0}^\infty \frac{f(\xi)}{ \qty{\xi - z_0}^{j+1} } \qty{ {z - z_0} }^j  ~d\xi \\
&= \frac{1}{2\pi i } \sum_{j=0}^\infty \int_{\bd D} \frac{f(\xi)}{ \qty{\xi - z_0}^{j+1} } \qty{ {z - z_0} }^j  ~d\xi \quad\text{since the series converges uniformly on $D$} \\
&= \sum_{j=0}^\infty \qty{ \frac{1}{2\pi i } \int_{\bd D} \frac{f(\xi)}{ \qty{\xi - z_0}^{j+1} } ~d\xi} \qty{ {z - z_0} }^j  \\
&\definedas \sum_{j=0}^\infty a_j (z-z_0)^j
.\end{align*}

$\qed$


## Problem 3

### a

*Proposition:*
$\sum n z^n$ does not converge for any $\abs{z} = 1$.

**Proof:**


\begin{align*}
a_n = nz^n \implies \abs{a_n} = n\abs{z}^n = n \converges{n\to\infty}{\not\to} 0
.\end{align*}


### b

*Proposition:*
$\sum_n z^n/n^2$ converges for every $\abs{z} \leq 1$.

**Proof:**

\begin{align*}
\abs{ \sum_n \frac{z^n}{n^2}  } \leq \sum_n \abs{ \frac{z^n}{n^2}  } \leq \sum_n \abs{ \frac 1 {n^2}  } = \frac{\pi^2}{6} < \infty
.\end{align*}


### c

*Proposition:*
$\sum z^n/n$ converges for every $\abs{z}\leq 1$ except $z=1$.

**Proof:**
By Abel's test, since $\theset{a_n = \frac 1 n} \searrow 0$ and this sequence is bounded by 1, $f(z) = \sum a_n z^n$ converges for $z\in \bar\DD \setminus\theset{1}$.
To see that $f(1)$ diverges, we just note that $f(1) = \sum \frac 1 n$ is the harmonic series, which is known to diverge.


## Problem 4

*Proposition:*
Let $\gamma$ denote a circle centered at the origin of radius $r$ with positive orientation.
Then if $\abs \alpha \leq r \leq \abs \beta$,

\begin{align*}
\int_{\gamma} \frac{d z}{(z-\alpha)(z-\beta)}=\frac{2 \pi i}{\alpha-\beta}
.\end{align*}

**Proof:**
By partial fraction decomposition, we have

\begin{align*}
\int_\gamma \frac{1}{\qty{z-\alpha}\qty{z-\beta}} ~dz 
&= \frac 1 {\alpha-\beta}\qty{\int_\gamma \frac{1}{z-\alpha} ~dz - \int_\gamma \frac{1}{z-\beta} ~dz } \\
&= \frac{1}{\alpha- \beta} \int_\gamma \frac{1}{z-\alpha} ~dz \quad\text{since } \beta > r \text{ and thus } g(z) \definedas \frac{1}{z-\beta} \text{ is holomorphic in  } D_r \\
&= \frac{1}{\alpha - \beta} \int_{\gamma} \frac 1 w ~dw \\
&= \frac{2\pi i}{\alpha - \beta}
.\end{align*}


## Problem 5

*Proposition:*
Suppose $f$ is continuous for $x\geq x_0, 0\leq y \leq b$ and $\lim_{x\to\infty}f(x+iy) = A$ independent of $y$.
Let $\gamma_x \definedas \theset{z\suchthat z = x+it,~ 0\leq t \leq b}$, then
\begin{align*}
\lim _{x \rightarrow+\infty} \int_{\gamma_{x}} f(z) d z=i A b
.\end{align*}


**Proof:**

> ??? 
> Seems like this should involve integrating over the rectangular contour $[x_0, R] \cross i[0, b]$ and taking $R\to\infty$, but it's not clear what the integral over the whole contour is or even any of the edges.

## Problem 6

*Proposition:*
There exists a function $f$ that is holomorphic on $0 < \abs z < 1$ with $\int_{\bd D_r(0)} = 0$ for all $r<1$ but $f$ is not holomorphic at $z=0$.

**Proof:**
Since holomorphic functions are continuous, it suffices to find a function that is discontinuous at zero for which the contour integral vanishes.
To this end, take $f(z) = \frac 1 {z^2}$, which is clearly discontinuous at zero, and

\begin{align*}
\int_\gamma f = \int_0^{2\pi} \frac 1 {r e^{it}} ~dt = 0
.\end{align*}


## Problem 7

Let $f$ be analytic on $\Omega$ and $f'(z_0) \neq 0$ for some $z_0 \in \Omega$.
Show that if $C$ is a circle centered at $z_0$ of sufficiently small radius, then

\begin{align*}
\frac{2 \pi i}{f^{\prime}\left(z_{0}\right)}=\int_{C} \frac{d z}{f(z)-f\left(z_{0}\right)}
.\end{align*}

**Proof:**

We'll use the formula

\begin{align*}
f'(a) = \frac 1 {2\pi i} \int_\gamma \frac{f(\xi)}{\qty{\xi - a}^2} ~d\xi
.\end{align*}

Note that by the inverse function theorem, we have

\begin{align*}
(f\inv )' (f(z)) f'(z) = 1 \implies \frac{1}{f'(z)} = (f\inv)' (f(z))
.\end{align*}

Applying Cauchy's Integral Formula, we obtain

\begin{align*}
\frac{1}{f'(z_0)} 
&= (f\inv)' (f(z_0)) \\
&= \frac {1}{2\pi i} \int_\gamma \frac{f\inv(\xi)}{\qty{\xi - f(z_0)}^2} ~d\xi\\
&= \frac 1 {2\pi i } \int_\gamma \frac{w f'(w)}{\qty{f(w) - f(z_0)}^2}~dw
\quad\quad\quad \qty{ \xi = f(w),~d\xi=f'(w)~dw }\\
\implies \frac{2\pi i}{f'(z_0)} &=
\int_\gamma \frac{w f'(w)}{\qty{f(w) - f(z_0)}^2}~dw =_{??} \int_\gamma \frac{1}{f(w) -f(z_0)} ~dw
.\end{align*}

> It's not clear to me how to prove the last equality!
> It seems like this is where we would use the fact that $f$ is analytic, but expanding in a power series doesn't seem to help remove the square in the denominator.

## Problem 8

*Proposition:*
Let $u, v \in C^1(\RR^2)$.
Then $f = u + iv$ has derivative $f'(z_0) = x_0 + iy_0$ iff

\begin{align*}
\lim _{r \rightarrow 0} \frac{1}{\pi r^{2}} \int_{\left|z-z_{0}\right|=r} f(z) d z=0
.\end{align*}


**Proof:**
Let $\gamma_r$ be a circle of radius $r$ about $z_0$ and $D_r$ be the region it bounds.
Then

\begin{align*}
\int_{\gamma_r} f ~dz
&= \int_{\gamma_r} u~dx - v ~dy + i~\int_{\gamma_r} v~dx + u~dy \\
&= \iint_{D_r} \qty{ v_x - u_y }~dA - i~\iint_{D_r} \qty{ u_x+ v_y } \\
&= \pi r^2 \qty{ (v_x - u_y)(w_1) + i(u_x + v_y)(w_2)  } \quad\text{ for some $w_i \in D_r$ by the MVT} \\
\implies ~~~ \frac{1}{\pi r^2} \int_{\gamma_r} f ~dz &= (v_x - u_y)(w_1) + i(u_x + v_y)(w_2)  \\
\converges{r\to 0}\to ~~&(v_x - u_y)(z_0) + i (u_x + v_y)(z_0)
,\end{align*}

and this limit is zero iff the Cauchy-Riemann equations hold at $z_0$ iff $f'(z_0)$ exists.

$\qed$


## Problem 9

*Proposition:*
Let $\gamma$ be piecewise smooth with interior $\Omega_1$ and exterior $\Omega_2$.
Assume $f'$ exists on an open set containing $\gamma$ and $\Omega_2$.
Show that if $\lim_{z\to\infty}f(z) = A$, then

\begin{align*}
\frac{1}{2 \pi i} \int_{\gamma} \frac{f(\xi)}{\xi-z} d \xi=\left\{\begin{array}{ll}{A,} & {\text { if } z \in \Omega_{1}} \\ {-f(z)+A,} & {\text { if } z \in \Omega_{2}}\end{array}\right
.\end{align*}

**Proof:**

Idea: take $z$ small enough such that $\frac 1 z \in \Omega_2$, then $f$ is holomorphic for such $z$ since $f'$ exists, so take a Laurent expansion $f(z) = \sum_{j=0}^\infty a_j z^{-j}$. 
We can deduce that $a_0 = A$, and integrate term by term:

\begin{align*}
\frac 1 {2\pi i}\int_\gamma \frac{f(\xi)}{\xi - z}~d\xi 
&= \frac 1 {2\pi i}\int_\gamma \sum_{j=0}^\infty \frac{a_j}{z^j\qty{\xi - z}} ~d\xi\\
&= \frac 1 {2\pi i} \sum_{j=0}^\infty \int_\gamma \frac{a_jz^{-j}}{\xi - z} ~d\xi \\
&\definedas \frac 1 {2\pi i} \sum_{j=0}^\infty \int_\gamma \frac{g_j(\xi)}{\xi - z} ~d\xi \\
&= -\frac 1 {2\pi i} \sum_{j=1}^\infty 2\pi i ~ g_j(z) \\
&= -\sum_{j=1}^\infty a_j z^{-j} \\
&= -\qty{ \sum_{j=0}^\infty a_j z^{-j} - a_0} \\
&= - f(z) + A
.\end{align*}


> Note: pretty sure this is not right. Also not sure how to compute for $z\in \Omega_1$ without using the residue theorem.

## Problem 10

*Proposition:*
Let $f$ be bounded and analytic and $a\neq b \in \CC$ be fixed, then the following limit exists:

\begin{align*}
\lim _{R \rightarrow \infty} \int_{|z|=R} \frac{f(z)}{(z-a)(z-b)} d z
.\end{align*}

Then $f$ must be constant.

**Proof:**

Then take $R$ large enough such that $a, b$ are contained in a disc of radius $R$ and let $\gamma$ be its boundary. 
By partial fractions we have

\begin{align*}
\int_\gamma \frac{f}{(z-a)(z-b)}
&= \frac{1}{b-a} \qty{ \int_\gamma \frac {f(z)} {z-b} - \int_\gamma \frac {f(z)} {z-a}  }  \\
&= \frac{1}{b-a} \qty{ 2\pi i f(b) + 2\pi i  f(a)  } \\
&=\frac{2\pi i \qty{f(b) - f(a) }}{b-a} \\
&\converges{R\to\infty}\to \frac{2\pi i \qty{f(b) - f(a) }}{b-a}
\end{align*}

since this is a constant independent of $R$.

## Problem 11

*Proposition:*
Suppose $f$ is entire and $\frac{f(z)}{z} \converges{z\to\infty}\to 0$.
Then $f$ must be constant.

**Proof:**
Since $f$ is entire, it is in fact *equal* to its Taylor series expansion, and thus

\begin{align*}
z\inv f(z) 
&= z\inv \sum_{j=0}^\infty \frac{\bd_z^n f}{n!} z^j \\
&= \sum_{j=0}^\infty \frac{\bd_z^n f(z)}{n!} z^{j-1} \\
&= z\inv f(z) + f'(z) + O(z) \\
&\converges{z\to \infty}\to f'(z)
.\end{align*}

Since $z\inv f(z) \to 0$ by assumption, we must have $f'(z) \equiv 0$, which forces $f$ to be constant.



## Problem 12

*Proposition:*
Let $f$ be analytic on $\Omega$ and $\gamma$ a closed curve in $\Omega$.
Then for any $z_0 \in \Omega\setminus \gamma$,

\begin{align*}
\int_{\gamma} \frac{f^{\prime}(z)}{z-z_{0}} d z=\int_{\gamma} \frac{f(z)}{\left(z-z_{0}\right)^{2}} d z
.\end{align*}

**Proof:**
Since $f$ is analytic, it uniformly converges to its power series on $\Omega$ and we can integrate term-by-term.
So write $f(z) = \sum_{j\in \NN} a_j (z-z_0)^j$.

We can first compute the LHS:


\begin{align*}
(z-z_0)\inv f'(z) 
&= (z-z_0)\inv \sum_{j\in \NN} a_j (z-z_0)^j \\
&= (z-z_0)\inv \sum_{j\in \NN} a_{j+1} (z-z_0)^j \\
&= \sum_{j\in \NN} a_{j+1} (z-z_0)^{j-1} \\
&= \frac{a_1}{z-z_0} + 2a_2 + O(z-z_0) \\
\implies \int_\gamma \frac{f'(z)}{z-z_0} 
&= \int_\gamma \frac{a_1}{z-z_0} + O(1) + O(z-z_0) ~dz \\
&= \int_\gamma \frac{a_1}{z-z_0} ~dz \\
&= 2\pi i ~a_1
.\end{align*}


And similarly the RHS:

\begin{align*}
(z-z_0)^{-2} f(z) 
&= (z-z_0)^{-2} \sum_{j=0}^\infty a_j (z-z_0)^j \\
&= \sum_{j=0}^\infty a_j (z-z_0)^{j-2} \\
&= \frac{a_1}{z-z_0} + O(\qty{z-z_0}^{-2}) + O(z-z_0) \\
\implies \int_\gamma \frac{f(z)}{\qty{z-z_0}^2} ~dz 
&= \int_\gamma \frac{a_1}{z-z_0} + O(\qty{ z-z_0}^{-2}) + O(z-z_0) ~dz \\
&= \int_\gamma \frac{a_1}{z-z_0} \\
&= 2\pi i ~a_1
.\end{align*}

$\qed$


## Problem 13
Compute

\begin{align*}
\int_{|z|=1}\left(z+\frac{1}{z}\right)^{2 n} \frac{d z}{z}
.\end{align*}

Use this to show that 

\begin{align*}
\int_{0}^{2 \pi} \cos ^{2 n} \theta d \theta=2 \pi \frac{1 \cdot 3 \cdot 5 \cdots(2 n-1)}{2 \cdot 4 \cdot 6 \cdots(2 n)}
.\end{align*}

**Solution:**

Using the Binomial theorem, we can expand

\begin{align*}
\int_\gamma z\inv \qty{z+ z\inv}^{2n}  ~dz
&= \int_\gamma z\inv \sum_{j=0}^{\infty} {2n \choose j} z^j z^{2n - j} ~dz\\
&= \int_\gamma \sum_{j=0}^{\infty} {2n \choose j} z^{2n-2j - 1} ~dz \\
&= \int_\gamma {2n \choose n} z\inv + O(z^{-3}) + O(z) ~dz \\
&= 2\pi i {2n \choose n}
.\end{align*}

Now writing $\cos(\theta) = \frac 1 2 \qty{z + z\inv}$ where 
$$
z=e{i\theta} \implies dz = iz~d\theta \implies d\theta = -iz~dz
,$$ 

letting $\gamma$ denote the unit circle, we have

\begin{align*}
\int_{\theta}^{2\pi} \cos^{2n}\qty{\theta} ~d\theta 
&= -\int_\gamma \qty{\frac 1 2 \qty{z + z\inv } }^{2n} ~iz~dz \\
&= -\frac{i}{2^n} \int_\gamma\qty{z + z\inv}^{2n} \frac{dz}{z} \\
&= -\frac{i}{2^n} \qty{2\pi i {2n \choose n  }} \\
&= \frac{\pi}{2^{n-1}} {2n \choose n}
.\end{align*}

> I assume this is equal to the given expression!

$\qed$
