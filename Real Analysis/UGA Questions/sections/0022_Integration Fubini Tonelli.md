# Fubini-Tonelli

## Spring 2020 # 4

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
Relevant concepts:

- Tonelli: non-negative and measurable yields measurability of slices and equality of iterated integrals
- Fubini: $f(x, y) \in L^1$ yields *integrable* slices and equality of iterated integrals
- F/T: apply Tonelli to $\abs{f}$; if finite, $f\in L^1$ and apply Fubini to $f$

\begin{align*}
\norm{H(x)}_1 
&= \int_\RR \abs{H(x, y)} \, dx \\
&= \int_\RR \abs{ \int_\RR f(y)g(x-y) \,dy } \, dx \\
&\leq \int_\RR \qty{ \int_\RR \abs{f(y)g(x-y)}  \, dy } \, dx \\
&= \int_\RR \qty{ \int_\RR \abs{f(y)g(x-y)}  \, dx} \, dy \quad\text{by Tonelli} \\
&= \int_\RR \qty{ \int_\RR \abs{f(y)g(t)}  \, dt} \, dy \quad\text{setting } t=x-y, \,dt = - dx \\
&= \int_\RR \qty{ \int_\RR \abs{f(y)}\cdot \abs{g(t)}  \, dt}\, dy \\
&= \int_\RR \abs{f(y)} \cdot \qty{ \int_\RR \abs{g(t)}  \, dt}\, dy \\
&\definedas \int_\RR \abs{f(y)} \cdot \norm{g}_1 \,dy \\
&= \norm{g}_1 \int_\RR \abs{f(y)} \,dy \\
&\definedas \norm{g}_1 \norm{f}_1  \\
&< \infty \qtext{by assumption}
.\end{align*}

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



## Spring 2019 # 4
Let $f$ be a non-negative function on $\RR^n$ and $\mathcal A = \{(x, t) ∈ \RR^n × \RR : 0 ≤ t ≤ f (x)\}$.

Prove the validity of the following two statements:

a. $f$ is a Lebesgue measurable function on $\RR^n \iff  \mathcal A$ is a Lebesgue measurable subset of $\RR^{n+1}$

b. If $f$ is a Lebesgue measurable function on $\RR^n$, then
\[
m(\mathcal{A})=\int _{\RR^{n}} f(x) d x=\int_{0}^{\infty} m\left(\left\{x \in \RR^{n}: f(x) \geq t\right\}\right) dt
\]

## Fall 2018 # 5
Let $f \geq 0$ be a measurable function on $\RR$.
Show that
$$
\int _{\RR} f = \int _{0}^{\infty} m(\{x: f(x)>t\}) dt
$$

## Fall 2015 # 5
Let $f, g \in L^1(\RR)$ be Borel measurable.

1. Show that 
  - The function $$F(x, y) \definedas f(x-y) g(y)$$ is Borel measurable on $\RR^2$, and
  - For almost every $y\in \RR$, $$F_y(x) \definedas f(x-y)g(y)$$ is integrable with respect to $y$.

2. Show that $f\ast g \in L^1(\RR)$ and
\[
\|f * g\|_{1} \leq \|f\|_{1} \|g\|_{1}
\]

## Spring 2014 # 5
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
