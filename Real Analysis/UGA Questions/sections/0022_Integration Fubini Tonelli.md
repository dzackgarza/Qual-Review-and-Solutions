# Fubini-Tonelli

## Spring 2020 # 4 $\done$

Let $f, g\in L^1(\RR)$. 
Argue that $H(x, y) \definedas f(y) g(x-y)$ defines a function in $L^1(\RR^2)$ and deduce from this fact that
\[
(f\ast g)(x) \definedas \int_\RR f(y) g(x-y) \,dy
\]
defines a function in $L^1(\RR)$ that satisfies 
\[
\norm{f\ast g}_1 \leq \norm{f}_1 \norm{g}_1
.\]

:::{.solution}
\hfill
:::{.concept}
\hfill
- Tonelli: non-negative and measurable yields measurability of slices and equality of iterated integrals
- Fubini: $f(x, y) \in L^1$ yields *integrable* slices and equality of iterated integrals
- F/T: apply Tonelli to $\abs{f}$; if finite, $f\in L^1$ and apply Fubini to $f$
:::

\[
\norm{H(x)}_1 
&= \int _\RR \abs{H(x, y)} \, dx \\
&= \int _\RR \abs{ \int_\RR f(y)g(x-y) \,dy } \, dx \\
&\leq \int _\RR \qty{ \int_\RR \abs{f(y)g(x-y)}  \, dy } \, dx \\
&= \int _\RR \qty{ \int_\RR \abs{f(y)g(x-y)}  \, dx} \, dy \quad\text{by Tonelli} \\
&= \int _\RR \qty{ \int_\RR \abs{f(y)g(t)}  \, dt} \, dy \quad\text{setting } t=x-y, \,dt = - dx \\
&= \int _\RR \qty{ \int_\RR \abs{f(y)}\cdot \abs{g(t)}  \, dt}\, dy \\
&= \int _\RR \abs{f(y)} \cdot \qty{ \int_\RR \abs{g(t)}  \, dt}\, dy \\
&\definedas \int _\RR \abs{f(y)} \cdot \norm{g}_1 \,dy \\
&= \norm{g}_1 \int _\RR \abs{f(y)} \,dy \\
&\definedas \norm{g}_1 \norm{f}_1  \\
&< \infty \qtext{by assumption}
.\]

- $H$ is measurable on $\RR^2$:
  - If we can show $\tilde f(x, y) \definedas f(y)$ and $\tilde g(x, y) \definedas g(x-y)$ are both measurable on $\RR^2$, then $H = \tilde f \cdot \tilde g$ is a product of measurable functions and thus measurable. 
  - $f \in L^1$, and $L^1$ functions are measurable by definition.
  - The function $(x, y) \mapsto g(x-y)$ is measurable on $\RR^2$:
    - Let $g$ be measurable on $\RR$, then the cylinder function $G(x, y) = g(x)$ on $\RR^2$ is always measurable
    - Define a linear transformation $T \definedas \thevector{1, -1; 0, 1}$ which sends $(x,y) \to (x-y, y)$, then $T\in \GL(2, \RR)$ is linear and thus measurable.
    - Then $(G\circ T)(x, y) = G(x-y, y) = \tilde g(x-y)$, so $\tilde g$ is a composition of measurable functions and thus measurable.

- Apply **Tonelli** to $\abs{H}$
  - $H$ measurable implies $\abs{H}$ is measurable
  - $\abs{H}$ is non-negative
  - So the iterated integrals are equal in the extended sense
  - The calculation shows the iterated integral is finite, to $\int \abs{H}$ is finite and $H$ is thus integrable on $\RR^2$.

> Note: Fubini is not needed, since we're not calculating the actual integral, just showing $H$ is integrable.


:::



## Spring 2019 # 4 $\done$
Let $f$ be a non-negative function on $\RR^n$ and $\mathcal A = \{(x, t) ∈ \RR^n × \RR : 0 ≤ t ≤ f (x)\}$.

Prove the validity of the following two statements:

a. $f$ is a Lebesgue measurable function on $\RR^n \iff  \mathcal A$ is a Lebesgue measurable subset of $\RR^{n+1}$

b. If $f$ is a Lebesgue measurable function on $\RR^n$, then
\[
m(\mathcal{A})=\int _{\RR^{n}} f(x) d x=\int_{0}^{\infty} m\left(\left\{x \in \RR^{n}: f(x) \geq t\right\}\right) dt
\]

\todo[inline]{Add concepts.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- See S&S p.82.
:::

### a

$\implies$:

- Suppose $f$ is a measurable function.
- Note that $\mathcal{A} = \theset{f(x) - t \geq 0} \intersect \theset{t \geq 0}$.
- Define $F(x, t) = f(x)$, $G(x, t) = t$, which are cylinders on measurable functions and thus measurable.
- Define $H(x, y) = F(x, t) - G(x, t)$, which are linear combinations of measurable functions and thus measurable.
- Then $\mathcal{A} = \theset{H \geq 0} \intersect \theset{G \geq 0}$ as a countable intersection of measurable sets, which is again measurable.


$\impliedby$:

- Suppose $\mca$ is a measurable set.
- Then FT on $\chi_{\mca}$ implies that for almost every $x\in \RR^n$, the $x\dash$slices $\mca_x$ are measurable and
\[
\mathcal{A}_x \definedas \theset{t\in \RR \suchthat (x, t) \in \mathcal{A}} = [0, f(x)] \implies m(\mathcal A_x) = f(x) - 0 = f(x)
\]

- But $x \mapsto m(\mathcal A_x)$ is a measurable function, and is exactly the function $x \mapsto f(x)$, so $f$ is measurable.


### b

- Note
\[
\mathcal{A} &= \theset{(x, t) \in \RR^n\cross \RR \suchthat 0 \leq t \leq f(x)} 
\\
\mathcal{A}_t &= \theset{x
\in \RR^n \suchthat t\leq f(x) }
.\]

- Then
\[
\int_{\RR^n} f(x) ~dx 
&= \int_{\RR^n} \int_0^{f(x)} 1 ~dt~dx \\
&= \int_{\RR^n} \int_{0}^\infty \chi_\mathcal{A} ~dt~dx \\
&\overset{F.T.}= \int_{0}^\infty \int_{\RR^n} \chi_\mathcal{A} ~dx~dt\\
&= \int_0^\infty m(\mathcal{A}_t) ~dt
,\]
  where we just use that $\int \int \chi_\mathcal{A} = m(\mathcal{A})$

- By Tonelli, all of these integrals are equal. 
  - This is justified because $f$ was assumed measurable on $\RR^n$, thus by (a) $\mathcal{A}$ is a measurable set and thus $\chi_A$ is a measurable function on $\RR^n\cross \RR$.

:::

## Fall 2018 # 5 $\done$
Let $f \geq 0$ be a measurable function on $\RR$.
Show that
\[
\int _{\RR} f = \int _{0}^{\infty} m(\{x: f(x)>t\}) dt
\]

:::{.solution}
\hfill
:::{.concept}
\hfill
- Claim: If $E\subseteq \RR^a \cross \RR^b$ is a measurable set, then for almost every $y\in \RR^b$, the slice $E^y$ is measurable and
\[
m(E) = \int_{\RR^b} m(E^y) \,dy
.\]
  - Set $g = \chi_E$, which is non-negative and measurable, so apply Tonelli.
  - Conclude that $g^y = \chi_{E^y}$ is measurable, the function $y\mapsto \int g^y(x)\, dx$ is measurable, and $\int \int g^y(x)\,dx \,dy = \int g$.
  - But $\int g = m(E)$ and $\int\int g^y(x) \,dx\,dy = \int m(E^y)\,dy$.
:::

> Note: $f$ is a function $\RR\to \RR$ in the original problem, but here I've assumed $f:\RR^n\to \RR$.

- Since $f\geq 0$, set 
$$
E\definedas \theset{(x, t) \in \RR^{n} \cross \RR \suchthat f(x) > t}
= \theset{(x, t) \in \RR^n \cross \RR \suchthat 0 \leq t < f(x)}
.$$
- Claim: since $f$ is measurable, $E$ is measurable and thus $m(E)$ makes sense.
  - Since $f$ is measurable, $F(x, t) \definedas t - f(x)$ is measurable on $\RR^n \cross \RR$.
  - Then write $E = \theset{F < 0} \intersect \theset{t\geq 0}$ as an intersection of measurable sets.
- We have slices 
\[
E^t &\definedas \theset{x\in \RR^n \suchthat (x, t) \in E} = \theset{x\in \RR^n \suchthat 0 \leq t < f(x)} \\
E^x &\definedas \theset{t\in \RR \suchthat (x, t) \in E} = \theset{t\in \RR \suchthat 0 \leq t \leq f(x)} = [0, f(x)]
.\]
  - $E_t$ is precisely the set that appears in the original RHS integrand.
  - $m(E^x) = f(x)$.
- Claim: $\chi_E$ satisfies the conditions of Tonelli, and thus $m(E) = \int \chi_E$ is equal to any iterated integral.
  - Non-negative: clear since $0\leq \chi_E \leq 1$
  - Measurable: characteristic functions of measurable sets are measurable.

- Conclude:
  1. For almost every $x$, $E^x$ is a measurable set, $x\mapsto m(E^x)$ is a measurable function, and $m(E) = \int_{\RR^n} m(E^x) \, dx$ 
  2. For almost every $t$, $E^t$ is a measurable set, $t\mapsto m(E^t)$ is a measurable function, and $m(E) = \int_{\RR} m(E^t) \, dt$ 
- On one hand,
\[
m(E) 
&= \int_{\RR^{n+1}} \chi_E(x, t) \\
&= \int_{\RR} \int_{\RR^n} \chi_E(x, t) \,dt \,dx \quad\text{by Tonelli}\\
&= \int_{\RR^n} m(E^x) \,dx \quad\text{first conclusion}\\
&= \int_{\RR^n} f(x) \,dx 
.\]
- On the other hand,
\[
m(E) 
&= \int_{\RR^{n+1}} \chi_E(x, t) \\
&= \int_\RR \int_{\RR^n} \chi_E(x, t) \, dx \,dt \quad\text{by Tonelli} \\
&= \int_\RR m(E^t) \,dt \quad\text{second conclusion}
.\]

- Thus
\[
\int_{\RR^n} f \,dx = m(E) = \int_\RR m(E^t) \,dt = \int_\RR m\qty{\theset{x\suchthat f(x) > t}}
.\]

:::



## Fall 2015 # 5 $\work$
Let $f, g \in L^1(\RR)$ be Borel measurable.

1. Show that 
  - The function $$F(x, y) \definedas f(x-y) g(y)$$ is Borel measurable on $\RR^2$, and
  - For almost every $y\in \RR$, $$F_y(x) \definedas f(x-y)g(y)$$ is integrable with respect to $y$.

2. Show that $f\ast g \in L^1(\RR)$ and
\[
\|f * g\|_{1} \leq \|f\|_{1} \|g\|_{1}
\]

## Spring 2014 # 5 $\work$
Let $f, g \in L^1([0, 1])$ and for all $x\in [0, 1]$ define
\[
F(x) \definedas \int _{0}^{x} f(y) \, dy 
\qtext{and}
G(x)\definedas \int _{0}^{x} g(y) \, dy.
\]

Prove that
\[
\int _{0}^{1} F(x) g(x) \, dx = 
F(1) G(1) - \int _{0}^{1} f(x) G(x) \, dx
\]
