
---
title: "Complex Analysis Problems"
---



# Topology and Functions of One Variable (8155a)

## 1
Let $x_0 = a, x_1 = b$, and set
\[  
x_n \definedas {x_{n-1} + x_{n-2} \over 2} \quad n\geq 2
.\]

Show that $\theset{x_n}$ is a Cauchy sequence and find its limit in terms of $a$ and $b$.

## 2
Suppose $f:\RR\to\RR$ is continuous and $\lim_{x\to \pm \infty} f(x) = 0$.
Prove that $f$ is uniformly continuous.

## 3
Give an example of a function $f:\RR\to \RR$ that is everywhere differentiable but $f'$ is not continuous at 0.

## 4
Suppose $\theset{g_n}$ is a uniformly convergent sequence of functions from $\RR$ to $\RR$ and $f:\RR\to \RR$ is uniformly continuous.
Prove that the sequence $\theset{f\circ g_n}$ is uniformly convergent.

## 5
Let $f$ be differentiable on $[a, b]$.
Say that $f$ is *uniformly differentiable* iff 

\[  
\forall \varepsilon > 0,\, \exists \delta > 0 \text{ such that } \quad \abs{x-y} < \delta \implies \abs{ {f(x) - f(y) \over x-y}  - f'(y)}  < \eps
.\]

Prove that $f$ is uniformly differentiable on $[a, b] \iff f'$ is continuous on $[a, b]$.

## 6
Suppose $A, B \subseteq \RR^n$ are disjoint and compact.
Prove that there exist $a\in A, b\in B$ such that
\[  
\norm{a - b} = \inf\theset{\norm{x-y} \suchthat x\in A,\, y\in B}
.\]

## 7
Suppose $A, B\subseteq \RR^n$ are connected and not disjoint.
Prove that $A\union B$ is also connected.

## 8
Suppose $\theset{f_n}_{n\in \NN}$ is a sequence of continuous functions $f_n: [0, 1]\to \RR$ such that 
\[  
f_n(x) \geq f_{n+1}(x) \geq 0 \quad \forall n\in \NN,\, \forall x\in [0, 1]
.\]
Prove that if $\theset{f_n}$ converges pointwise to $0$ on $[0, 1]$ then it converges to $0$ uniformly on $[0, 1]$.

## 9
Show that if $E\subset [0, 1]$ is uncountable, then there is some $t\in \RR$ such that $E\intersect (-\infty ,t)$ and $E\intersect (t, \infty)$ are also uncountable.

# Several Variables (8155h)

## 1
Is the following function continuous, differentiable, continuously differentiable?
\[  
f: \RR^2 &\to \RR  \\
f(x, y) &= 
\begin{cases}
{xy \over \sqrt{x^2 + y^2}} & (x, y) \neq (0, 0) \\
0 & \text{else}.
\end{cases}
\]

## 2

### a 
Complete this definition: "$f: \RR^n\to \RR^m$ is real-differentiable a point $p\in \RR^n$ iff there exists a linear transformation..."

### b
Give an example of a function $f:\RR^2\to \RR$ whose first-order partial derivatives exist everywhere but $f$ is not differentiable at $(0, 0)$.

### c
Give an example of a function $f: \RR^2 \to \RR$ which is real-differentiable everywhere but nowhere complex-differentiable.

## 3
Let $f:\RR^2\to \RR$.

### a
Define in terms of linear transformations what it means for $f$ to be differentiable at a point $(a, b) \in \RR^2$.

### b
State a version of the inverse function theorem in this setting.

### c
Identify $\RR^2$ with $\CC$ and give a necessary and sufficient condition for a real-differentiable function at $(a, b)$ to be complex differentiable at the point $a+ib$.

## 4
Let $f = u+iv$ be complex-differentiable with continuous partial derivatives at a point $z = re^{i\theta}$ with $r\neq 0$.
Show that
\[  
\dd{u}{r} = {1\over r}\dd{v}{\theta} \qquad \dd{v}{r} = -{1\over r}\dd{u}{\theta}
.\]

## 5
Let $P = (1, 3) \in \RR^2$ and define
\[  
f(s, t) \definedas ps^3 -6st + t^2
.\]

### a
State the conclusion of the implicit function theorem concerning $f(s, t) = 0$ when $f$ is considered a function $\RR^2\to\RR$.

### b
State the above conclusion when $f$ is considered a function $\CC^2\to \CC$.

### c
Use the implicit function theorem for a function $\RR\cross \RR^2 \to \RR^2$ to prove (b).

> There are various approaches: using the definition of the complex derivative, the Cauchy-Riemann equations, considering total derivatives, etc.

## 6
Let $F:\RR^2\to \RR$ be continuously differentiable with $F(0, 0) = 0$ and $\norm{\nabla F(0, 0)} < 1$.

Prove that there is some real number $r> 0$ such that $\abs{F(x, y)} < r$ whenever $\norm{(x, y)} < r$.

## 7
State the most general version of the implicit function theorem for real functions and outline how it can be proved using the inverse function theorem.



# Conformal Maps (8155c)

> Notation: $\DD$ is the open unit disc, $\HH$ is the open upper half-plane.

## 1
Find a conformal map from $\DD$ to $\HH$.

## 2
Find a conformal map from the strip $\theset{z\in \CC \suchthat 0 < \Im(z) < 1}$ to $\HH$.

## 3
Find a fractional linear transformation $T$ which maps $\HH$ to $\DD$, and explicitly describe the image of the first quadrant under $T$.

## 4
Find a conformal map from $\theset{z\in \CC\suchthat \abs{z-i} > 1,\, \Re(z) > 0}$ to $\HH$.

## 5
Find a conformal map from $\theset{z\in \CC \suchthat \abs{z} < 1,\, \abs{z - {1\over 2}} > {1\over 2} }$ to $\DD$.

## 6
Find a conformal  map from $\theset{\abs{z-1} < 2} \intersect \theset{\abs{z+1} < 2}$ to $\HH$.

## 7
Let $\Omega$ be the region inside the unit circle $\abs{z} = 1$ and outside the circle $\abs{z-{1\over 4}} = {1\over 4}$.

Find an injective conformal map from $\Omega$ onto some annulus $\theset{r < \abs{z} < 1}$ for some constant $r$.

## 8
Let $D$ be the region obtained by deleting the real interval $[0, 1)$ from $\DD$; find a conformal map from $D$ to $\DD$.

## 9
Find a conformal map from $\CC\setminus\theset{x\in \RR\suchthat x\leq 0}$ to $\DD$.

## 10
Find a conformal map from $\CC\setminus\theset{x\in \RR\suchthat x\geq 1}$ to $\DD$.

## 11
Find a bijective conformal map from $G$ to $\HH$, where
\[  
G \definedas \theset{z\in \CC \suchthat \abs{z-1} < \sqrt 2,\, \abs{z+1} < \sqrt 2} \setminus [0, i)
.\]

## 12
Prove that TFAE for a Möbius transformation $T$ given by $T(z) = {az + b \over cz + d}$:

a. $T$ maps $\RR\union \theset{\infty}$ to itself.
b. It is possible to choose $a,b,c,d$ to be real numbers.
c. $\bar{T(z)} = T(\bar z)$ for every $z\in \CP^1$.
d. There exist $\alpha\in \RR, \beta \in \CC\setminus \RR$ such that $T(\alpha) = \alpha$ and $T(\bar \beta) = \bar{T(\beta)}$.

# Integrals and Cauchy's Theorem (8155d)

> Some interesting problems: 3, 4, 9, 10.

## 1

Suppose $f, g: [0, 1] \to \RR$ where $f$ is Riemann integrable and for $x, y\in [0, 1]$,
\begin{align*}
\abs{g(x) - g(y)} \leq \abs{f(x) - f(y)}
.\end{align*}

Prove that $g$ is Riemann integrable.

## 2

State and prove Green's Theorem for rectangles.

Then use it to prove Cauchy's Theory for functions that are analytic in a rectangle.


## 3

Suppose $\theset{f_n}_{n\in \NN}$ is a sequence of analytic functions on $\DD^\circ \definedas \theset{z\in \CC \suchthat \abs{z} < 1}$.

Show that if $f_n\to g$ for some $g: \DD^\circ \to \CC$ uniformly on every compact $K\subset \DD^\circ$, then $g$ is analytic on $\DD^\circ$.


## 4

Suppose $\theset{f_n}_{n\in \NN}$ is a sequence of entire functions where

- $f_n \to g$ pointwise for some $g:\CC\to\CC$.
- On every line segment in $\CC$, $f_n \to g$ uniformly.

Show that 

- $g$ is entire, and
- $f_n\to g$ uniformly on every compact subset of $\CC$.


## 5

Prove that there is no sequence of polynomials that uniformly converge to $f(z) = {1\over z}$ on $S^1$.


## 6

Suppose that $f: \RR\to\RR$ is a continuous function that vanishes outside of some finite interval.
For each $z\in \CC$, define
\begin{align*}
g(z) = \int_{-\infty}^\infty f(t) e^{-izt} \,dt
.\end{align*}

Show that $g$ is entire.


## 7

Suppose $f: \CC\to \CC$ is entire and
\begin{align*}
\abs{f(z)} \leq \abs{z}^{1\over 2} \quad\text{ when } \abs{z} > 10
.\end{align*}

Prove that $f$ is constant.

## 8

Let $\gamma$ be a smooth curve joining two distinct points $a, b\in \CC$.

Prove that the function
\begin{align*}
f(z) \definedas \int_\gamma {g(w) \over w-z} \,dw
\end{align*}
is analytic in $\CC\setminus\gamma$.

## 9
Suppose that $f: \CC\to\CC$ is continuous everywhere and analytic on $\CC\setminus \RR$ and prove that $f$ is entire.

## 10
Prove Liouville's theorem: suppose $f:\CC\to\CC$ is entire and bounded. 
Use Cauchy's formula to prove that $f'\equiv 0$ and hence $f$ is constant.


# Liouville's Theorem, Power Series (8155e)

## 1

Suppose $f$ is analytic on a region $\Omega$ such that $\DD \subseteq \Omega \subseteq \CC$ and $f(z) = \sum_{n=0}^\infty a_n z^n$ is a power series with radius of convergence exactly 1.

a. Give an example of such an $f$ that converges at every point of $S^1$.

b. Given an example of such an $f$ which is analytic at $1$ but $\sum_{n=0}^\infty a_n$ diverges.

c. Prove that $f$ can not be analytic at *every* point of $S^1$.

## 2

Suppose $f$ is entire and has Taylor series $\sum a_n z^n$ about 0.

a. Express $a_n$ as a contour integral along the circle $\abs{z} = R$.

b. Apply (a) to show that the above Taylor series converges uniformly on every bounded subset of $\CC$.

c. Determine those functions $f$ for which the above Taylor series converges uniformly on all of $\CC$.


## 3

Suppose $D$ is a domain and $f, g$ are analytic on $D$.

Prove that if $fg = 0$ on $D$, then either $f \equiv 0$ or $g\equiv 0$ on $D$.


## 4

Suppose $f$ is analytic on $\DD^\circ$.
Determine with proof which of the following are possible:

a. $f\qty{1\over n} = (-1)^n$ for each $n>1$.

b. $f\qty{1\over n} = e^{-n}$ for each even integer $n>1$ while $f\qty{1\over n} = 0$ for each odd integer $n>1$.

c. $f\qty{1\over n^2} = {1\over n}$ for each integer $n>1$.

d. $f\qty{1\over n} = {n-2 \over n-1}$ for each integer $n>1$.


## 5

Prove the Fundamental Theorem of Algebra (using complex analysis).


## 6
Find all entire functions that satisfy
\begin{align*}
\abs{f(z)} \geq \abs{z} \quad \forall z\in \CC
.\end{align*}
Prove this list is complete.

## 7
Suppose $\sum_{n=0}^\infty a_n z^n$ converges for some $z_0 \neq 0$.

a. Prove that the series converges absolutely for each $z$ with $\abs z < \abs z_0$.

b. Suppose $0 < r < \abs{z_0}$ and show that the series converges uniformly on $\abs{z} \leq r$.

## 8

Suppose $f$ is entire and suppose that for some integer $n\geq 1$,
\begin{align*}
\lim_{z\to \infty} {f(z) \over z^n} = 0
.\end{align*}

Prove that $f$ is a polynomial of degree at most $n-1$.


## 9

Find all entire functions satisfying
\begin{align*}
\abs{f(z)} \leq \abs{z}^{1\over 2} \quad\text{ for } \abs{z} > 10
.\end{align*}


## 10

Prove that the following series converges uniformly on the set $\theset{z \suchthat \Im(z) < \ln 2}$:
\begin{align*}
\sum_{n=1}^\infty {\sin(nz) \over 2^n}
.\end{align*}


# Laurent Expansions and Singularities (8155f)

## 1 
Find the Laurent expansion of
\begin{align*}
f(z) = {z + 1 \over z(z-1)}
\end{align*}

about $z=0$ and $z=1$ respectively.

## 2

Find the Laurent expansions about $z=0$ of the following functions:
\begin{align*}
\exp{1\over z} \hspace{8em} \cos \qty{1\over z}
.\end{align*}

## 3

Find the Laurent expansion of 
\begin{align*}
f(z) = {z+1 \over z(z-1)^2}
\end{align*}
about $z=0$ and $z=1$ respectively.

> Hint: recall that power series can be differentiated.

## 4

For the following functions, find the Laurent series about $0$ and classify their singularities there:
\begin{align*}
{\sin^2(z) \over z} \\
z \exp{1\over z^2} \\
{1 \over z(4-z)}
.\end{align*}

## 5

Find all entire functions with have poles at $\infty$.

## 6

Find all functions on the Riemann sphere that have a simple pole at $z=2$ and a double pole at $z=\infty$, but are analytic elsewhere.

## 7
Let $f$ be entire, and discuss (with proofs and examples) the types of singularities $f$ might have (removable, pole, or essential) at $z=\infty$ in the following cases:

1. $f$ has at most finitely many zeros in $\CC$.
2. $f$ has infinitely many zeros in $\CC$.

## 8
Define
\begin{align*}
f(z) &= {\pi^2 \over \sin^2 \qty{\pi z} } \\
g(z) &= \sum_{n\in \ZZ} {1\over (z-n)^2}
.\end{align*}

a. Show that $f$ and $g$ have the same singularities in $\CC$.
b. Show that $f$ and $g$ have the same singular parts at each of their singularities.
c. Show that $f, g$ each have period one and approach zero uniformly on $0\leq x \leq 1$ as $\abs{y}\to \infty$.
d. Conclude that $f = g$.

# Residues (8155g)

## 1
Calculate
\begin{align*}
\int_0^\infty {1 \over (1+z)^2 (z+9x^2)} \, dx
.\end{align*}


## 2
Let $a>0$ and calculate
\begin{align*}
\int_0^\infty {x\sin(x) \over x^2 + a^2} \,dx
.\end{align*}


## 3
Calculate
\begin{align*}
\int_0^\infty {\sqrt x \over (x+1)^2} \,dx
.\end{align*}

## 4
Calculate
\begin{align*}
\int_0^\infty {\cos(x) - \cos(4x) \over x^2} \, dx
.\end{align*}

## 5
Let $a>0$ and calculate
\begin{align*}
\int_0^\infty {x^2 \over (x^2 + a^2)^2} \, dx
.\end{align*}

## 6
Calculate
\begin{align*}
\int_0^\infty {\sin(x) \over x}\, dx
.\end{align*}

## 7
Calculate
\begin{align*}
\int_0^\infty {\sin(x) \over x(x^2+1)}\, dx
.\end{align*}

## 8
Calculate
\begin{align*}
\int_0^\infty {\sqrt x \over 1 + x^2} \, dx
.\end{align*}

## 9
Calculate
\begin{align*}
\int_{-\infty}^\infty {1+x^2 \over 1+x^4}\, dx
.\end{align*}

## 10
Let $a>0$ and calculate
\begin{align*}
\int_0^\infty {\cos(x) \over (x^2 + a^2)^2}\, dx
.\end{align*}

## 11
Calculate
\begin{align*}
\int_0^\infty {\sin^3(x) \over x^3} \, dx
.\end{align*}

## 12
Let $n\in \ZZ^{\geq 1}$ and $0<\theta<\pi$ and show that
\begin{align*}
{1\over 2\pi i} \int_{\abs z = 2} {z^n \over 1 -3z\cos(\theta) + z^2} \,dz = {\sin(n\theta) \over \sin(\theta)}
.\end{align*}

## 13
Suppose $a>b>0$ and calculate
\begin{align*}
\int_0^{2\pi} {1 \over (a+b\cos(\theta))^2} \,d\theta
.\end{align*}


# Rouche's Theorem (8155h)

## 1

Prove that for every $n\in \ZZ^{\geq 0}$ the following polynomial has no roots in the open unit disc:
\begin{align*}
f_n(x) \definedas \sum_{k=0}^n {z^k \over k!}
.\end{align*}

> Hint: check $n=1,2$ directly.

## 2
Assume that $\abs b < 1$ and show that the following polynomial has exactly two roots (counting multiplicity) in $\abs{z} < 1$:
\begin{align*}
f(z) \definedas z^3 + 3z^2 + bz + b^2
.\end{align*}


## 3
Let $c\in \CC$ with $\abs{c} < {1\over 3}$.
Show that on the open set $\theset{z\in \CC \suchthat \Re(z) < 1}$, the function $f(z) \definedas ce^z$ has exactly one fixed point.


## 4
How many roots does the following polynomial have in the open disc $\abs{z} < 1$?
\begin{align*}
f(z) = z^7 - 4z^3 - 1
.\end{align*}


## 5
Let $n\in \ZZ^{\geq 0}$ and show that the equation
\begin{align*}
e^z = az^n
\end{align*}
has $n$ solutions in the open unit disc if $\abs{a} > e$, and no solutions if $\abs{a} < {1\over e}$.

## 6
Let $f$ be analytic in a domain $D$ and fix $z_0 \in D$ with $w_0 \definedas f(z_0)$.
Suppose $z_0$ is a zero of $f(z) - w_0$ with finite multiplicity $m$.
Show that there exists $\delta >0$ and $\eps > 0$ such that for each $w$ such that $0 < \abs{w-w_0} < \eps$, the equation $f(z) - w = 0$ has exactly $m$ *distinct* solutions inside the disc $\abs{z-z_0} < \delta$.


## 7
For $k=1,2,\cdots, n$, suppose $\abs{a_k} < 1$ and
\begin{align*}
f(z) \definedas \qty{z - a_1 \over 1 - \bar a_q z} \qty{z-a_2 \over 1 - \bar a_2 z} \cdots \qty{z - a_n \over 1 - \bar a_n z}
.\end{align*}
Show that $f(z) = b$ has $n$ solutions in $\abs{z} < 1$.


## 8
For each $n\in \ZZ^{\geq 1}$, let
\begin{align*}
P_n(z) = 1 + z + {1\over 2!} z^2 + \cdots + {1\over n!}z^n
.\end{align*}
Show that for sufficiently large $n$, the polynomial $P_n$ has no zeros in $\abs{z} < 10$, while the polynomial $P_n(z) - 1$ has precisely 3 zeros there.

## 9
Prove that
\begin{align*}
\max_{\abs z = 1} \abs{a_0 + a_1 z + \cdots + a_{n-1}z^{n-1} + z^n} \geq 1
.\end{align*}

> Hint: the first part of the problem asks for a statement of Rouche's theorem.

## 10
Use Rouche's theorem to prove the Fundamental Theorem of Algebra.




# Schwarz Lemma and Reflection Principle (8155i)

## 1
Suppose $f:\DD\to\DD$ is analytic and admits a continuous extension $\tilde f: \bar \DD \to \bar \DD$ such that $\abs{z} = 1 \implies \abs{f(z)} = 1$.

### a
Prove that $f$ is a rational function.

### b
Suppose that $z=0$ is the unique zero of $f$.
Show that
\[  
\exists n\in \NN, \lambda \in S^1 \qtext{ such that }f(z) = \lambda z^n
.\]

### c

Suppose that $a_1, \cdots, a_n \in \DD$ are the zeros of $f$ and prove that
\[  
\exists \lambda \in S^1 \qtext{such that} f(z) = \lambda \prod_{j=1}^n {z - a_j \over 1 - \bar{a_j} z}
.\]

## 2
Let $\bar B(a, r)$ denote the closed disc of radius $r$ about $a\in \CC$.
Let $f$ be holomorphic on an open set containing $\bar B(a, r)$ and let 
\[  
M \definedas \sup_{z\in \bar B(a, r)} \abs{f(z)}
.\]

Prove that 
\[  
z\in \bar B\qty{a, {r\over 2}},\,z\neq a, \qquad {\abs{ f(z) - f(a)} \over \abs{z-a}} \leq {2M \over r}
.\]

## 3
Define
\[  
G \definedas \theset{z\in \CC\suchthat \Re(z) > 0, \, \abs{z-1} > 1}
.\]

Find all of the injective conformal maps $G\to \DD$.
These may be expressed as compositions of maps, but explain why this list is complete.

## 4
Suppose $f: \HH\union \RR\to \CC$ satisfies the following:

- $f(i) = i$
- $f$ is continuous
- $f$ is analytic on $\HH$
- $f(z) \in \RR \iff z\in \RR$.

Show that $f(\HH)$ is a dense subset of $\HH$.

## 5
Suppose $f: \DD\to \HH$ is analytic and satisfies $f(0) = 2$.
Find a sharp upper bound for $\abs{f'(0)}$, and prove it is sharp by example.

## 6
Suppose $f:\DD\to\DD$ is analytic, has a single zero of order $k$ at $z=0$, and satsifies $\lim_{\abs z \to 1} \abs{f(z)} = 1$.
Give with proof a formula for $f(z)$.

## 7

### a
State the standard Schwarz reflection principle involving reflection across the real axis.

### b
Give a linear fractional transformation $T$ mapping $\DD$ to $\HH$.
Let $g(z) = \bar z$, and show
\[  
(T^{-1} \circ g \circ T)(z) = 1/\bar z
.\]

### c
Suppose that $f$ is holomorphic on $\DD$, continuous on $\bar \DD$, and real on $S^1$.
Show that $f$ must be constant.

## 8
Suppose $f, g: \DD\to \Omega$ are holomorphic

# Spring 2020 Homework 1

## 1

Geometrically describe the following subsets of $\CC$:

a. $\abs{z-1} = 1$
b. $\abs{z-1} = 2\abs{z-2}$
c. $1/z = \bar z$
d. $\Re(z) = 3$
e. $\Im(z) = a$ with $a\in \RR$.
f. $\Re(z) > a$ with $a\in \RR$.
g. $\abs{z-1} < 2\abs{z-2}$


## 2
Prove the following inequality, and explain when equality holds:
\begin{align*}
\abs{z+w} \geq \abs{ \abs{z} - \abs{w} }
.\end{align*}


## 3
Prove that the following polynomial has its roots outside of the unit circle:
\begin{align*}
p(z) = z^3 + 2z + 4
.\end{align*}

> Hint: What is the maximum value of the modulus of the first two terms if $\abs{z} \leq 1$?

## 4

a. Prove that if $c>0$,
\begin{align*}
\abs{w_1} = c\abs{w_2} \implies \abs{w_1 - c^2 w_2} = c\abs{w_1 - w_2}
.\end{align*}

b. Prove that if $c>0$ and $c\neq 1$, with $z_1\neq z_2$, then the following equation represents a circle:
    \begin{align*}
    \abs{z-z_1 \over z-z_2} = c
    .\end{align*}
    Find its center and radius.

    > Hint: use part (a)

## 5

a. Let $z, w \in \CC$ with $\bar z w \neq 1$. 
    Prove that
    \begin{align*}
    \abs{w-z \over 1 - \bar w z} < 1 \quad\text{ if } \abs{z}<1,~ \abs{w} < 1
    \end{align*}
    with equality when $\abs{z} = 1$ or $\abs{w} = 1$.

b. Prove that for a fixed $w\in \DD$, the mapping $F: z\mapsto {w-z \over 1 - \bar w z}$ satisfies

    - $F$ maps $\DD$ to itself and is holomorphic.
    - $F(0) = w$ and $F(w) = 0$.
    - $\abs{z} = 1$ implies $\abs{F(z)} = 1$.

## 6

Use $n$th roots of unity to show that
\begin{align*}
2^{n-1} \sin\qty{\pi \over n} \sin\qty{2\pi \over n} \cdots \sin\qty{(n-1)\pi \over n} = n
.\end{align*}

> Hint:
\begin{align*}
1 - \cos(2\theta) &= 2\sin^2(\theta) \\
2 \sin(2\theta) &= 2\sin(\theta) \cos(\theta)
.\end{align*}

## 7
Prove that $f(z) = \abs{z}^2$ has a derivative at $z=0$ and nowhere else.


## 8

Let $f(z)$ be analytic in a domain, and prove that $f$ is constant if it satisfies any of the following conditions:

a. $\abs{f(z)}$ is constant.
b. $\Re(f(z))$ is constant.
c. $\arg(f(z))$ is constant.
d. $\bar{f(z)}$ is analytic.

How do you generalize (a) and (b)?


## 9
Prove that if $z\mapsto f(z)$ is analytic, then $z \mapsto \bar{f(\bar z)}$ is analytic.


## 10

a. Show that in polar coordinates, the Cauchy-Riemann equations take the form
  \begin{align*}
  \frac{\partial u}{\partial r}=\frac{1}{r} \frac{\partial v}{\partial \theta} \text { and } \frac{\partial v}{\partial r}=-\frac{1}{r} \frac{\partial u}{\partial \theta}
  .\end{align*}

b. Use (a) to show that the logarithm function, defined as 
  \begin{align*}
  \log z=\log r+i \theta \text { where } z=r e^{i \theta} \text { with }-\pi<\theta<\pi
  .\end{align*}
  is holomorphic on the region $r> 0, -\pi < \theta < \pi$.

  Also show that this function is not continuous in $r>0$.

## 11

Prove that the distinct complex numbers $z_1, z_2, z_3$ are the vertices of an equilateral triangle if and only if
\begin{align*}
z_{1}^{2}+z_{2}^{2}+z_{3}^{2}=z_{1} z_{2}+z_{2} z_{3}+z_{3} z_{1}
.\end{align*}

# Spring 2020 Homework 2

> Note on notation: I sometimes use $f_x \definedas \dd{f}{x}$ to denote partial derivatives, and $\bd_z^n f$ as $f^{(n)}(z)$.

## Stein And Shakarchi

### 2.6.1

Show that
\begin{align*}
\int_{0}^{\infty} \sin \left(x^{2}\right) d x=\int_{0}^{\infty} \cos \left(x^{2}\right) d x=\frac{\sqrt{2 \pi}}{4}
.\end{align*}

> Hint: integrate $e^{-x^2}$ over the following contour, using the fact that $\int_{-\infty}^{\infty} e^{-x^{2}} d x=\sqrt{\pi}$:


![Image](figures/2020-02-03-13:51.png)\


### 2.6.2

Show that

\begin{align*}
\int_{0}^{\infty} \frac{\sin x}{x} d x=\frac{\pi}{2}
.\end{align*}

> Hint: use the fact that this integral equals $\frac{1}{2 i} \int_{-\infty}^{\infty} \frac{e^{i x}-1}{x} d x$, and integrate around an indented semicircle.

### 2.6.5

Suppose $f\in C_\CC^1(\Omega)$ and $T\subset \Omega$ is a triangle with $T^\circ \subset \Omega$.
Apply Green's theorem to show that $\int_T f(z) ~dz = 0$.

Assume that $f'$ is continuous and prove Goursat's theorem.

> Hint: Green's theorem states

\begin{align*}
\int_{T} F d x+G d y=\int_{T^\circ}\left(\frac{\partial G}{\partial x}-\frac{\partial F}{\partial y}\right) d x d y
.\end{align*}

### 2.6.6

Suppose that $f$ is holomorphic on a punctured open set $\Omega\setminus\theset{w_0}$ and let $T\subset \Omega$ be a triangle containing $w_0$.
Prove that if $f$ is bounded near $w_0$, then $\int_T f(z) ~dz = 0$.


### 2.6.7

Suppose $f: \DD \to \CC$ is holomorphic and let $d \definedas \sup_{z, w\in \DD}\abs{f(z) - f(w)}$ be the diameter of the image of $f$.
Show that $2 \abs{f'(0)} \leq d$, and that equality holds iff $f$ is linear, so $f(z) = a_1 z + a_2$.

> Hint: $2f'(0) = \frac{1}{2\pi i} \int_{\abs \xi = r} \frac{ f(\xi) - f(-\xi)  }{\xi^2} ~d\xi$ whenever $0<r<1$.


### 2.6.8

Suppose that $f$ is holomorphic on the strip $S = \theset{x+iy \suchthat x\in \RR,~ -1<y<1}$ with $\abs{f(z)} \leq A \qty{1 + \abs z}^\nu$ for $\nu$ some fixed real number.
Show that for all $z\in S$, for each integer $n\geq 0$ there exists an $A_n \geq 0$ such that $\abs{f^{(n)}(x)} \leq A_n (1 + \abs x)^\nu$ for all $x\in \RR$.

> Hint: Use the Cauchy inequalities.

### 2.6.9

Let $\Omega \subset \CC$ be open and bounded and $\phi: \Omega \to \Omega$ holomorphic.
Prove that if there exists a point $z_0 \in \Omega$ such that $\phi(z_0) = z_0$ and $\phi'(z_0) = 1$, then $\phi$ is linear.

> Hint: assume $z_0 = 0$ (explain why this can be done) and write $\phi(z)  = z + a_n z^n + O(z^{n+1})$ near $0$.
  Let $\phi_k = \phi \circ \phi \circ \cdots \circ \phi$ and prove that $\phi_k(z) = z + ka_nz^n  + O(z^{n+1})$.
  Apply Cauchy's inequalities and let $k\to \infty$ to conclude.


### 2.6.10

Can every continuous function on $\bar \DD$ be uniformly approximated by polynomials in the variable $z$?

> Hint: compare to Weierstrass for the real interval.

### 2.6.13

Suppose $f$ is analytic, defined on all of $\CC$, and for each $z_0 \in \CC$ there is at least one coefficient in the expansion $f(z) = \sum_{n=0}^\infty c_n(z-z_0)^n$ is zero.
Prove that $f$ is a polynomial.

> Hint: use the fact that $c_n n! = f^{(n)}(z_0)$ and use a countability argument.


### 2.6.14

Suppose that $f$ is holomorphic in an open set containing $\DD$ except for a pole $z_0 \in \bd \DD$.
Let $\sum_{n=0}^\infty a_n z^n$ be the power series expansion of $f$ in $\DD$, and show that $\lim \frac{a_n}{a_{n+1}} = z_0$.

### 2.6.15

Suppose $f$ is continuous and nonvanishing on $\bar \DD$, and holomorphic in $\DD$.
Prove that if $\abs{z} = 1 \implies \abs{f(z)} = 1$, then $f$ is constant.

> Hint: Extend $f$ to all of $\CC$ by $f(z) = 1/ \bar{f(1/\bar z)}$ for any $\abs{z} > 1$, and argue as in the Schwarz reflection principle.

## Additional Problems

### 1
Let $a_n\neq 0$ and show that
\begin{align*}
\lim_{n\to \infty} {\abs{a_{n+1}} \over \abs{a_n}} = L \implies \lim_{n\to\infty} \abs{a_n}^{1\over n} = L
.\end{align*}

In particular, this shows that when applicable, the ratio test can be used to calculate the radius of convergence of a power series.

### 2
Let $f$ be a power series centered at the origin.
Prove that $f$ has a power series expansion about any point in its disc of convergence.


### 3
Prove the following:

a. $\sum_{n} nz^n$ does not converge at any point of $S^1$

b. $\sum_n {z^n \over n^2}$ converges at every point of $S^1$.

c. $\sum_n {z^n \over n}$ converges at every point of $S^1$ except $z=1$.

### 4
Without using Cauchy's integral formula, show that if $\abs{a} < r < \abs{b}$, then
\begin{align*}
\int_{\gamma} \frac{d z}{(z-\alpha)(z-\beta)}=\frac{2 \pi i}{\alpha-\beta}
\end{align*}
where $\gamma$ denotes the circle centered at the origin of radius $r$ with positive orientation.

### 5
Assume $f$ is continuous in the region $\theset{x+iy \suchthat x\geq x_0, ~ 0\leq y \leq b}$, and the following limit exists independent of $y$:
\begin{align*}
\lim_{x\to +\infty}f(x+iy) = A
.\end{align*}

Show that if $\gamma_x \definedas \theset{z = x+it \suchthat 0 \leq t \leq b}$, then
\begin{align*}
\lim_{x\to +\infty} \int_{\gamma_x} f(z) \,dz = iAb
.\end{align*}


### 6
Show by example that there exists a function $f(z)$ that is holomorphic on $\theset{z\in \CC \suchthat 0 < \abs{z} < 1}$ and for all $r<1$,
\begin{align*}
\int_{\abs z = r} f(z) \, dz = 0
,\end{align*}
but $f$ is not holomorphic at $z=0$.

### 7
Let $f$ be analytic on a region $R$ and suppose $f'(z_0) \neq 0$ for some $z_0 \in R$.
Show that if $C$ is a circle of sufficiently small radius centered at $z_0$, then 
\begin{align*}
\frac{2 \pi i}{f^{\prime}\left(z_{0}\right)}=\int_{C} \frac{d z}{f(z)-f\left(z_{0}\right)}
.\end{align*}

> Hint: use the inverse function theorem.


### 8
Assume two functions $u, b: \RR^2 \to \RR$ have continuous partial derivatives at $(x_0 ,y_0)$.
Show that $f \definedas u + iv$ has derivative $f'(z_0)$ at $z_0 = =x_0 + iy_0$ if and only if
\begin{align*}
\lim _{r \rightarrow 0} \frac{1}{\pi r^{2}} \int_{\left|z-z_{0}\right|=r} f(z) d z=0
.\end{align*}


### 9 (Cauchy's Formula for Exterior Regions)

Let $\gamma$ be a piecewise smooth simple closed curve with interior $\Omega_1$ and exterior $\Omega_2$.
Assume $f'$ exists in an open set containing $\gamma$ and $\Omega_2$ with $\lim_{z\to \infty} f(z) = A$.
Show that
\begin{align*}
\frac{1}{2 \pi i} \int_{\gamma} \frac{f(\xi)}{\xi-z} d \xi=\left\{\begin{array}{ll}
A, & \text { if } z \in \Omega_{1} \\
-f(z)+A, & \text { if } z \in \Omega_{2}
\end{array}\right.
.\end{align*}


### 10
Let $f(z)$ be bounded and analytic in $\CC$.
Let $a\neq b$ be any fixed complex numbers.
Show that the following limit exists:
\begin{align*}
\lim_{R\to \infty} \int_{\abs z = R} {f(z) \over (z-a)(z-b)} \,dz
.\end{align*}

Use this to show that $f(z)$ must be constant.


### 11
Suppose $f(z)$ is entire and 
\begin{align*}
\lim_{z\to\infty} {f(z) \over z} = 0
.\end{align*}

Show that $f(z)$ is a constant.

### 12
Let $f$ be analytic in a domain $D$ and $\gamma$ be a closed curve in $D$.
For any $z_0\in D$ not on $\gamma$, show that
\begin{align*}
\int_{\gamma} \frac{f^{\prime}(z)}{\left(z-z_{0}\right)} d z=\int_{\gamma} \frac{f(z)}{\left(z-z_{0}\right)^{2}} d z
.\end{align*}
Give a generalization of this result.


### 13

Compute
\begin{align*}
\int_{\abs z = 1} \qty{z + {1\over z}}^{2n} {dz \over z}
\end{align*}
and use it to show that
\begin{align*}
\in_0^{2\pi} \cos^{2n}(\theta) \, d\theta = 2\pi \qty{1\cdot 3 \cdot 5 \cdots (2n-1) \over 2 \cdot 4 \cdot 6 \cdots (2n)}
.\end{align*}


# Spring 2020 Homework 3

## Stein and Shakarchi

### 3.8.1
Use the following formula to show that the complex zeros of $\sin(\pi z)$ are exactly the integers, and they are each of order 1:
\begin{align*}
\sin \pi z=\frac{e^{i \pi z}-e^{-i \pi z}}{2 i}
.\end{align*}

Calculate the residue of ${1\over \sin(\pi z)}$ at $z=n\in \ZZ$.


### 3.8.2

Evaluate the integral
\begin{align*}
\int_\RR {dx \over 1 + x^4}
.\end{align*}

What are the poles of ${1\over 1 + z^4}$ ?


### 3.8.4
Show that
\begin{align*}
\int_{-\infty}^{\infty} \frac{x \sin x}{x^{2}+a^{2}} d x=\pi e^{-a}, \quad \text { for all } a>0
.\end{align*}


### 3.8.5
Show that if $\xi\in \RR$, then
\begin{align*}
\int_{-\infty}^{\infty} \frac{e^{-2 \pi i x \xi}}{\left(1+x^{2}\right)^{2}} d x=\frac{\pi}{2}(1+2 \pi|\xi|) e^{-2 \pi|\xi|}
.\end{align*}


### 3.8.6
Show that
\begin{align*}
\int_{-\infty}^{\infty} \frac{d x}{\left(1+x^{2}\right)^{n+1}}=\frac{1 \cdot 3 \cdot 5 \cdots(2 n-1)}{2 \cdot 4 \cdot 6 \cdots(2 n)} \cdot \pi
.\end{align*}


### 3.8.7
Show that
\begin{align*}
\int_{0}^{2 \pi} \frac{d \theta}{(a+\cos \theta)^{2}}=\frac{2 \pi a}{\left(a^{2}-1\right)^{3 / 2}}, \quad \text { whenever } a>1
.\end{align*}


### 3.8.8
Show that if $a,b\in \RR$ with $a > \abs{b}$, then
\begin{align*}
\int_{0}^{2 \pi} \frac{d \theta}{a+b \cos \theta}=\frac{2 \pi}{\sqrt{a^{2}-b^{2}}}
.\end{align*}

### 3.8.9
Show that
\begin{align*}
\int_{0}^{1} \log (\sin \pi x) d x=-\log 2
.\end{align*}

> Hint: use the following contour.
>
> ![](figures/image_2020-06-17-21-52-40.png)

### 3.8.10
Show that if $a>0$, then
\begin{align*}
\int_{0}^{\infty} \frac{\log x}{x^{2}+a^{2}} d x=\frac{\pi}{2 a} \log a
.\end{align*}

> Hint: use the following contour.
>
> ![](figures/image_2020-06-17-21-53-19.png)

### 3.8.14
Prove that all entire functions that are injective are of the form $f(z) = az + b$ with $a,b\in \CC$ and $a\neq 0$.

> Hint: Apply the Casorati-Weierstrass theorem to $f(1/z)$.

### 3.8.15
Use the Cauchy inequalities or the maximum modulus principle to solve the following problems:

a. Prove that if $f$ is an entire function that satisfies
    \begin{align*}
    \sup _{|z|=R}|f(z)| \leq A R^{k}+B
    \end{align*}
    for all $R>0$, some integer $k\geq 0$, and some constants $A, B > 0$, then $f$ is a polynomial of degree $\leq k$.

b. Show that if $f$ is holomorphic in the unit disc, is bounded, and converges uniformly to zero in the sector $\theta < \arg(z) < \phi$ as $\abs{z} \to 0$, then $f \equiv 0$.

c. Let $w_1, \cdots w_n$ be points on $S^1 \subset \CC$.
    Prove that there exists a point $z\in S^1$ such that the product of the distances from $z$ to the points $w_j$ is at least 1.

    Conclude that there exists a point $w\in S^1$ such that the product of the above distances is *exactly* 1.

d. Show that if the real part of an entire function is bounded, then $f$ is constant.


### 3.8.17

Let $f$ be non-constant and holomorphic in an open set containing the closed unit disc.

a. Show that if $\abs{f(z)} = 1$ whenever $\abs{z} = 1$, then the image of $f$ contains the unit disc.

    > Hint: Show that $f(z) = w_0$ has a root for every $w_0 \in \DD$, for which it suffices to show that $f(z) = 0$ has a root.
    > Conclude using the maximum modulus principle.

b. If $\abs{f(z)} \geq 1$ whenever $\abs{z} = 1$ and there exists a $z_0\in \DD$ such that $\abs{f(z_0)} < 1$, then the image of $f$ contains the unit disc.


### 3.8.19

Prove that maximum principle for harmonic functions, i.e.

a. If $u$ is a non-constant real-valued harmonic function in a region $\Omega$, then $u$ can not attain a maximum or a minimum in $\Omega$.

b. Suppose $\Omega$ is a region with compact closure $\bar \Omega$.
    If $u$ is harmonic in $\Omega$ and continuous in $\bar \Omega$, then 
    \begin{align*}
    \sup _{z \in \Omega}|u(z)| \leq \sup _{z \in \bar \Omega -\Omega}|u(z)|
    .\end{align*}

> Hint: to prove (a), assume $u$ attains a local maximum at $z_0$.
> Let $f$ be holomorphic near $z_0$ with $\Re(f) = u$, and show that $f$ is not an open map.
> Then (a) implies (b).


## Problems From Tie

### 1

Problem
: Prove that if $f$ has two Laurent series expansions,
  $$
  \begin{aligned} f(z) = \sum c_n(z-a)^n \quad\text{and}\quad f(z) = \sum c_n'(z-a)^n\end{aligned}
  $$
  then $c_n = c_n'$.

### 2

Problem
: Find Laurent series expansions of
  $$\begin{aligned}\frac{1}{1-z^2} + \frac{1}{3-z}\end{aligned}$$
  How many such expansions are there? In what domains are each valid?

### 3

Problem
: Let $P, Q$ be polynomials with no common zeros. Assume $a$ is a root of
$Q$.
  Find the principal part of $P/Q$ at $z=a$ in terms of $P$ and $Q$ if $a$ is (1) a simple root, and (2) a double root.

### 4

Problem
:   Let $f$ be non-constant, analytic in $\abs{z} > 0$, where $f(z_n) = 0$
for infinitely many points $z_n$ with $\lim_{n\to\infty} z_n = 0$.

    Show that $z=0$ is an essential singularity for $f$.

    > Example: $f(z) = \sin(1/z)$.

### 5

Problem
: Show that if $f$ is entire and $\lim_{z\to\infty}f(z) = \infty$, then
$f$ is a polynomial.

### 6

Problem
:   \hfill
    a. Show (without using 3.8.9 in the S&S) that
    $$\begin{aligned}\int_0^{2\pi} \log\abs{1 - e^{i\theta}}~d\theta = 0\end{aligned}$$
    b. Show that this identity is equivalent to S&S 3.8.9:
    \begin{align*}
    \int_0^1 \log(\sin(\pi x)) ~dx = -\log 2
    .\end{align*}

### 7

Problem
: Let $0<a<4$ and evaluate $$\begin{aligned}
    \int_0^\infty \frac{x^{\alpha-1}}{1+x^3} ~dx\end{aligned}$$

### 8

Problem
:   Prove the fundamental theorem of Algebra using

    a.  Rouche's Theorem.
    b. The maximum modulus principle.

### 9

Problem
:   Let $f$ be analytic in a region $D$ and $\gamma$ a rectifiable curve in
$D$ with interior in $D$.

    Prove that if $f(z)$ is real for all $z\in \gamma$, then $f$ is constant.

### 10

Problem
: For $a> 0$, evaluate
  $$\begin{aligned} \int_0^{\pi/2} \frac{d\theta}{a + \sin^2 \theta}\end{aligned}$$

### 11

Problem
: Find the number of roots of $p(z) = 4z^4 - 6z + 3$ in $\abs{z} < 1$ and
$1 < \abs{z} < 2$ respectively.

### 12

Problem
: Prove that $z^4 + 2z^3 -2z + 10$ has exactly one root in each open
quadrant.

### 13

Problem
: Prove that for $a> 0$, $z\tan z - a$ has only real roots.

### 14

Problem
:   Let $f$ be nonzero, analytic on a bounded region $\Omega$ and continuous
on its closure $\overline \Omega$.

    Show that if $\abs{f(z)} \equiv M$ is constant for $z\in \partial \Omega$, then $f(z) \equiv Me^{i\theta}$ for some real constant $\theta$.

# Extra Questions from Jingzhi Tie

## Fall 2009

### ?


(1) Assume $\displaystyle f(z) = \sum_{n=0}^\infty c_n z^n$
converges in $|z| < R$. Show that for $r <R$,
$$\frac{1}{2 \pi} \int_0^{2 \pi} |f(r e^{i \theta})|^2 d \theta =
\sum_{n=0}^\infty |c_n|^2 r^{2n} \; .$$

(2) Deduce Liouville's theorem from (1).

### ?


Let $f$ be a continuous function in the region
$$D=\{z \suchthat  \abs{z}>R, 0\leq \arg z\leq \theta\}\quad\text{where}\quad
1\leq \theta \leq 2\pi.$$ If there exists $k$ such that
$\displaystyle{\lim_{z\to\infty} zf(z)=k}$ for $z$ in the region
$D$. 
Show that $$\lim_{R'\to\infty} \int_{L} f(z) dz=i\theta k,$$
where $L$ is the part of the circle $|z|=R'$ which lies in the
region $D$.

### ?


Suppose that $f$ is an analytic function in the region $D$ which
contains the point $a$. Let
$$F(z)= z-a-qf(z),\quad \text{where}~ q \ \text{is a complex
parameter}.$$ 

(1) Let $K\subset D$ be a circle with the center at
point $a$ and also we assume that $f(z)\not =0$ for $z\in K$. Prove
that the function $F$ has one and only one zero $z=w$ on the closed
disc $\bar{K}$ whose boundary is the circle $K$ if $\displaystyle{
|q|<\min_{z\in K} \frac{|z-a|}{|f(z)|}.}$\

(2) Let $G(z)$ be an analytic function on the disk $\bar{K}$. Apply
the residue theorem to prove that
$\displaystyle{ \frac{G(w)}{F'(w)}=\frac{1}{2\pi
i}\int_K \frac{G(z)}{F(z)} dz,}$ where $w$ is the zero from (1).\

(3) If $z\in K$, prove that the function
$\displaystyle{\frac{1}{F(z)}}$ can be represented as a convergent
series with respect to $q$: $\displaystyle{
\frac{1}{F(z)}=\sum_{n=0}^{\infty} \frac{(qf(z))^n}{(z-a)^{n+1}}.}$

### ?


Evaluate $$\displaystyle{ \int_{0}^{\infty}\frac{x\sin x}{x^2+a^2} \,
dx }.$$

### ?


Let $f=u+iv$ be differentiable (i.e. $f'(z)$ exists) with continuous
partial derivatives at a point $z=re^{i\theta}$, $r\not= 0$. Show
that
$$\frac{\partial u}{\partial r}=\frac{1}{r}\frac{\partial v}{\partial \theta},\quad
\frac{\partial v}{\partial r}=-\frac{1}{r}\frac{\partial u}{\partial \theta}.$$

### ?


Show that $\displaystyle \int_0^\infty \frac{x^{a-1}}{1+x^n}
dx=\frac{\pi}{n\sin \frac{a\pi}{n}}$ using complex analysis, $0< a <
n$. Here $n$ is a positive integer.

### ?


For $s>0$, the **gamma function** is defined by
$\displaystyle{\Gamma(s)=\int_0^{\infty} e^{-t}t^{s-1} dt}$.

1.  Show that the gamma function is analytic in the half-plane
    $\Re (s)>0$, and is still given there by the integral formula
    above.

2.  Apply the formula in the previous question to show that
    $$\Gamma(s)\Gamma(1-s)=\frac{\pi}{\sin \pi s}.$$

> Hint: You may need $\displaystyle{\Gamma(1-s)=t \int_0^{\infty}e^{-vt}(vt)^{-s} dv}$ for $t>0$.

### ?


Apply Rouché's Theorem to prove the Fundamental Theorem of Algebra: If
$$P_n(z) = a_0 + a_1z + \cdots + a_{n-1}z^{n-1} + a_nz^n\quad  (a_n \neq 0)$$
is a polynomial of degree n, then it has n zeros in $\mathbb C$.

### ?


Suppose $f$ is entire and there exist $A, R >0$ and natural number
$N$ such that $$|f(z)| \geq A |z|^N\ \text{for}\ |z| \geq R.$$ Show
that 
(i) $f$ is a polynomial and 
(ii) the degree of $f$ is at least $N$.

### ?


Let $f: {\mathbb C} \rightarrow {\mathbb C}$ be an injective
analytic (also called *univalent*) function. Show that there exist
complex numbers $a \neq 0$ and $b$ such that $f(z) = az + b$.

### ?


Let $g$ be analytic for $|z|\leq 1$ and $|g(z)| < 1$ for $|z| = 1$.

1.  Show that $g$ has a unique fixed point in $|z| < 1$.

2.  What happens if we replace $|g(z)| < 1$ with $|g(z)|\leq 1$ for
    $|z|=1$? Give an example if (a) is not true or give an proof
    if (a) is still true.

3.  What happens if we simply assume that $f$ is analytic for
    $|z| < 1$ and $|f(z)| < 1$ for $|z| < 1$? Suppose that $f(z)
    \not\equiv  z$. Can f have more than one fixed point in
    $|z| < 1$?

> Hint: The map $\displaystyle{\psi_{\alpha}(z)=\frac{\alpha-z}{1-\bar{\alpha}z}}$ may be useful.

### ?


Find a conformal map from $D = \{z :\  |z| < 1,\ |z - 1/2| > 1/2\}$
to the unit disk $\Delta=\{z: \ |z|<1\}$.

### ?


Let $f(z)$ be entire and assume values of $f(z)$ lie outside a *bounded*
open set $\Omega$. Show without using Picard's theorems that $f(z)$ is a
constant.

### ?


(1) Assume $\displaystyle f(z) = \sum_{n=0}^\infty c_n z^n$ converges
in $|z| < R$. Show that for $r <R$,
$$\frac{1}{2 \pi} \int_0^{2 \pi} |f(r e^{i \theta})|^2 d \theta
= \sum_{n=0}^\infty |c_n|^2 r^{2n} \; .$$

(2) Deduce Liouville's theorem from (1).

### ?


Let $f(z)$ be entire and assume that $f(z) \leq M |z|^2$ outside some
disk for some constant $M$. Show that $f(z)$ is a polynomial in $z$ of
degree $\leq 2$.

### ?


Let $a_n(z)$ be an analytic sequence in a domain $D$ such that
$\displaystyle \sum_{n=0}^\infty |a_n(z)|$ converges uniformly on
bounded and closed sub-regions of $D$. Show that
$\displaystyle \sum_{n=0}^\infty |a'_n(z)|$ converges uniformly on
bounded and closed sub-regions of $D$.

### ?


Let $f(z)$ be analytic in an open set $\Omega$ except possibly at a
point $z_0$ inside $\Omega$. Show that if $f(z)$ is bounded in near
$z_0$, then $\displaystyle \int_\Delta f(z) dz = 0$ for all triangles
$\Delta$ in $\Omega$.

### ?


Assume $f$ is continuous in the region:
$0< |z-a| \leq R, \; 0 \leq \arg(z-a) \leq \beta_0$
($0 < \beta_0 \leq 2 \pi$) and the limit
$\displaystyle \lim_{z \rightarrow a} (z-a) f(z) = A$ exists. Show that
$$\lim_{r \rightarrow 0} \int_{\gamma_r} f(z) dz  = i A \beta_0 \; , \; \;$$
where
$\gamma_r : = \{ z \; | \; z = a + r e^{it}, \; 0 \leq  t \leq \beta_0 \}.$


### ?


Show that $f(z) = z^2$ is uniformly continuous in any open disk
$|z| < R$, where $R>0$ is fixed, but it is not uniformly continuous on
$\mathbb C$.

### ?


(1) Show that the function $u=u(x,y)$ given by
$$u(x,y)=\frac{e^{ny}-e^{-ny}}{2n^2}\sin nx\quad \text{for}\ n\in {\mathbf N}$$
is the solution on $D=\{(x,y)\ | x^2+y^2<1\}$ of the Cauchy problem for
the Laplace equation
$$\frac{\partial ^2u}{\partial x^2}+\frac{\partial ^2u}{\partial y^2}=0,\quad
u(x,0)=0,\quad \frac{\partial u}{\partial y}(x,0)=\frac{\sin nx}{n}.$$
(2) Show that there exist points $(x,y)\in D$ such that
$\displaystyle{\limsup_{n\to\infty} |u(x,y)|=\infty}$.


## Fall 2011

### ?


(1) Assume $\displaystyle f(z) = \sum_{n=0}^\infty c_n z^n$
converges in $|z| < R$. Show that for $r <R$,
$$\frac{1}{2 \pi} \int_0^{2 \pi} |f(r e^{i \theta})|^2 d \theta =
\sum_{n=0}^\infty |c_n|^2 r^{2n} \; .$$

(2) Deduce Liouville's theorem from (1).

### ?


Let $f$ be a continuous function in the region
$$D=\{z\ |  |z|>R, 0\leq \arg Z\leq \theta\}\quad\text{where}\quad
0\leq \theta \leq 2\pi.$$ If there exists $k$ such that
$\displaystyle{\lim_{z\to\infty} zf(z)=k}$ for $z$ in the region
$D$. Show that $$\lim_{R'\to\infty} \int_{L} f(z) dz=i\theta k,$$
where $L$ is the part of the circle $|z|=R'$ which lies in the
region $D$.

### ?


Suppose that $f$ is an analytic function in the region $D$ which
contains the point $a$. Let
$$F(z)= z-a-qf(z),\quad \text{where}\quad q \ \text{is a complex
parameter}.$$ 

(1) Let $K\subset D$ be a circle with the center at
point $a$ and also we assume that $f(z)\not =0$ for $z\in K$. Prove
that the function $F$ has one and only one zero $z=w$ on the closed
disc $\bar{K}$ whose boundary is the circle $K$ if $\displaystyle{
|q|<\min_{z\in K} \frac{|z-a|}{|f(z)|}.}$\

(2) Let $G(z)$ be an analytic function on the disk $\bar{K}$. Apply
the residue theorem to prove that
$\displaystyle{ \frac{G(w)}{F'(w)}=\frac{1}{2\pi
i}\int_K \frac{G(z)}{F(z)} dz,}$ where $w$ is the zero from (1).\

(3) If $z\in K$, prove that the function
$\displaystyle{\frac{1}{F(z)}}$ can be represented as a convergent
series with respect to $q$: $\displaystyle{
\frac{1}{F(z)}=\sum_{n=0}^{\infty} \frac{(qf(z))^n}{(z-a)^{n+1}}.}$

### ?


Evaluate $\displaystyle{ \int_{0}^{\infty}\frac{x\sin x}{x^2+a^2} \,
dx }$.

### ?


Let $f=u+iv$ be differentiable (i.e. $f'(z)$ exists) with continuous
partial derivatives at a point $z=re^{i\theta}$, $r\not= 0$. Show
that
$$\frac{\partial u}{\partial r}=\frac{1}{r}\frac{\partial v}{\partial \theta},\quad
\frac{\partial v}{\partial r}=-\frac{1}{r}\frac{\partial u}{\partial \theta}.$$

### ?


Show that $\displaystyle \int_0^\infty \frac{x^{a-1}}{1+x^n}
dx=\frac{\pi}{n\sin \frac{a\pi}{n}}$ using complex analysis, $0< a <
n$. Here $n$ is a positive integer.

### ?


For $s>0$, the **gamma function** is defined by
$\displaystyle{\Gamma(s)=\int_0^{\infty} e^{-t}t^{s-1} dt}$.

1.  Show that the gamma function is analytic in the half-plane
    $\Re (s)>0$, and is still given there by the integral formula
    above.

2.  Apply the formula in the previous question to show that
    $$\Gamma(s)\Gamma(1-s)=\frac{\pi}{\sin \pi s}.$$

> Hint: You may need $\displaystyle{\Gamma(1-s)=t \int_0^{\infty}e^{-vt}(vt)^{-s} dv}$ for $t>0$.

### ?


Apply Rouché's Theorem to prove the Fundamental Theorem of Algebra: If
$$P_n(z) = a_0 + a_1z + \cdots + a_{n-1}z^{n-1} + a_nz^n\quad  (a_n \neq 0)$$
is a polynomial of degree n, then it has n zeros in $\mathbb C$.

### ?


Suppose $f$ is entire and there exist $A, R >0$ and natural number
$N$ such that $$|f(z)| \geq A |z|^N\ \text{for}\ |z| \geq R.$$ Show
that (i) $f$ is a polynomial and (ii) the degree of $f$ is at least
$N$.

### ?


Let $f: {\mathbb C} \rightarrow {\mathbb C}$ be an injective
analytic (also called univalent) function. Show that there exist
complex numbers $a \neq 0$ and $b$ such that $f(z) = az + b$.

### ?


Let $g$ be analytic for $|z|\leq 1$ and $|g(z)| < 1$ for $|z| = 1$.

-   Show that $g$ has a unique fixed point in $|z| < 1$.

-   What happens if we replace $|g(z)| < 1$ with $|g(z)|\leq 1$ for
    $|z|=1$? Give an example if (a) is not true or give an proof
    if (a) is still true.

-   What happens if we simply assume that $f$ is analytic for
    $|z| < 1$ and $|f(z)| < 1$ for $|z| < 1$? Suppose that $f(z)
    \not\equiv  z$. Can f have more than one fixed point in
    $|z| < 1$?

> Hint: The map
$\displaystyle{\psi_{\alpha}(z)=\frac{\alpha-z}{1-\bar{\alpha}z}}$
> may be useful.

### ?


Find a conformal map from $D = \{z :\  |z| < 1,\ |z - 1/2| > 1/2\}$
to the unit disk $\Delta=\{z: \ |z|<1\}$.

### ?


Let $f(z)$ be entire and assume values of $f(z)$ lie outside a
*bounded* open set $\Omega$. Show without using Picard's theorems
that $f(z)$ is a constant.

### ?


Let $f(z)$ be entire and assume values of $f(z)$ lie outside a *bounded*
open set $\Omega$. Show without using Picard's theorems that $f(z)$ is a
constant.

### ?


(1) Assume $\displaystyle f(z) = \sum_{n=0}^\infty c_n z^n$ converges
in $|z| < R$. Show that for $r <R$,
$$\frac{1}{2 \pi} \int_0^{2 \pi} |f(r e^{i \theta})|^2 d \theta
= \sum_{n=0}^\infty |c_n|^2 r^{2n} \; .$$

(2) Deduce Liouville's theorem from (1).

### ?


Let $f(z)$ be entire and assume that $f(z) \leq M |z|^2$ outside some
disk for some constant $M$. Show that $f(z)$ is a polynomial in $z$ of
degree $\leq 2$.

### ?


Let $a_n(z)$ be an analytic sequence in a domain $D$ such that
$\displaystyle \sum_{n=0}^\infty |a_n(z)|$ converges uniformly on
bounded and closed sub-regions of $D$. Show that
$\displaystyle \sum_{n=0}^\infty |a'_n(z)|$ converges uniformly on
bounded and closed sub-regions of $D$.

### ?


Let $f(z)$ be analytic in an open set $\Omega$ except possibly at a
point $z_0$ inside $\Omega$. Show that if $f(z)$ is bounded in near
$z_0$, then $\displaystyle \int_\Delta f(z) dz = 0$ for all triangles
$\Delta$ in $\Omega$.

### ?


Assume $f$ is continuous in the region:
$0< |z-a| \leq R, \; 0 \leq \arg(z-a) \leq \beta_0$
($0 < \beta_0 \leq 2 \pi$) and the limit
$\displaystyle \lim_{z \rightarrow a} (z-a) f(z) = A$ exists. Show that
$$\lim_{r \rightarrow 0} \int_{\gamma_r} f(z) dz  = i A \beta_0 \; , \; \;$$
where
$\gamma_r : = \{ z \; | \; z = a + r e^{it}, \; 0 \leq  t \leq \beta_0 \}.$


### ?


Show that $f(z) = z^2$ is uniformly continuous in any open disk
$|z| < R$, where $R>0$ is fixed, but it is not uniformly continuous on
$\mathbb C$.

(1) Show that the function $u=u(x,y)$ given by
    $$u(x,y)=\frac{e^{ny}-e^{-ny}}{2n^2}\sin nx\quad \text{for}\ n\in {\mathbf N}$$
    is the solution on $D=\{(x,y)\ | x^2+y^2<1\}$ of the Cauchy problem for
    the Laplace equation
    $$\frac{\partial ^2u}{\partial x^2}+\frac{\partial ^2u}{\partial y^2}=0,\quad
    u(x,0)=0,\quad \frac{\partial u}{\partial y}(x,0)=\frac{\sin nx}{n}.$$
(2) Show that there exist points $(x,y)\in D$ such that
    $\displaystyle{\limsup_{n\to\infty} |u(x,y)|=\infty}$.

## Spring 2014

### ?


The question provides some insight into Cauchy's theorem. Solve the
problem without using the Cauchy theorem.

1.  Evaluate the integral $\displaystyle{\int_{\gamma} z^n dz}$ for
    all integers $n$. Here $\gamma$ is any circle centered at the
    origin with the positive (counterclockwise) orientation.

2.  Same question as (a), but with $\gamma$ any circle not
    containing the origin.

3.  Show that if $|a|<r<|b|$, then
    $\displaystyle{\int_{\gamma}\frac{dz}{(z-a)(z-b)} dz=\frac{2\pi i}{a-b}}$.
    Here $\gamma$ denotes the circle centered at the origin, of
    radius $r$, with the positive orientation.

### ?


(1) Assume the infinite series
$\displaystyle  \sum_{n=0}^\infty c_n z^n$ converges in $|z| < R$
and let $f(z)$ be the limit. Show that for $r <R$,
$$\frac{1}{2 \pi} \int_0^{2 \pi} |f(r e^{i \theta})|^2 d \theta =
\sum_{n=0}^\infty |c_n|^2 r^{2n} \; .$$

(2) Deduce Liouville's theorem from (1). Liouville's theorem: If
$f(z)$ is entire and bounded, then $f$ is constant.

### ?


Let $f$ be a continuous function in the region
$$D=\{z\ |  |z|>R, 0\leq \arg Z\leq \theta\}\quad\text{where}\quad
0\leq \theta \leq 2\pi.$$ If there exists $k$ such that
$\displaystyle{\lim_{z\to\infty} zf(z)=k}$ for $z$ in the region
$D$. Show that $$\lim_{R'\to\infty} \int_{L} f(z) dz=i\theta k,$$
where $L$ is the part of the circle $|z|=R'$ which lies in the
region $D$.

### ?


Evaluate $\displaystyle{ \int_{0}^{\infty}\frac{x\sin x}{x^2+a^2} \,
dx }$.

### ?


Let $f=u+iv$ be differentiable (i.e. $f'(z)$ exists) with continuous
partial derivatives at a point $z=re^{i\theta}$, $r\not= 0$. Show
that
$$\frac{\partial u}{\partial r}=\frac{1}{r}\frac{\partial v}{\partial \theta},\quad
\frac{\partial v}{\partial r}=-\frac{1}{r}\frac{\partial u}{\partial \theta}.$$

### ?


Show that $\displaystyle \int_0^\infty \frac{x^{a-1}}{1+x^n}
dx=\frac{\pi}{n\sin \frac{a\pi}{n}}$ using complex analysis, $0< a <
n$. Here $n$ is a positive integer.

### ?


For $s>0$, the **gamma function** is defined by
$\displaystyle{\Gamma(s)=\int_0^{\infty} e^{-t}t^{s-1} dt}$.

-   Show that the gamma function is analytic in the half-plane
    $\Re (s)>0$, and is still given there by the integral formula
    above.

-   Apply the formula in the previous question to show that
    $$\Gamma(s)\Gamma(1-s)=\frac{\pi}{\sin \pi s}.$$

> Hint: You may need $\displaystyle{\Gamma(1-s)=t \int_0^{\infty}e^{-vt}(vt)^{-s} dv}$ for $t>0$.

### ?


Apply Rouché's Theorem to prove the Fundamental Theorem of Algebra: If
$$P_n(z) = a_0 + a_1z + \cdots + a_{n-1}z^{n-1} + a_nz^n\quad  (a_n \neq 0)$$
is a polynomial of degree n, then it has n zeros in $\mathbf C$.

### ?


Suppose $f$ is entire and there exist $A, R >0$ and natural number
$N$ such that $$|f(z)| \geq A |z|^N\ \text{for}\ |z| \geq R.$$ Show
that (i) $f$ is a polynomial and (ii) the degree of $f$ is at least
$N$.

### ?


Let $f: {\mathbb C} \rightarrow {\mathbb C}$ be an injective
analytic (also called univalent) function. Show that there exist
complex numbers $a \neq 0$ and $b$ such that $f(z) = az + b$.

### ?


Let $g$ be analytic for $|z|\leq 1$ and $|g(z)| < 1$ for $|z| = 1$.

-   Show that $g$ has a unique fixed point in $|z| < 1$.

-   What happens if we replace $|g(z)| < 1$ with $|g(z)|\leq 1$ for
    $|z|=1$? Give an example if (a) is not true or give an proof
    if (a) is still true.

-   What happens if we simply assume that $f$ is analytic for
    $|z| < 1$ and $|f(z)| < 1$ for $|z| < 1$? Suppose that $f(z)
    \not\equiv  z$. Can f have more than one fixed point in
    $|z| < 1$?

> Hint: The map
$\displaystyle{\psi_{\alpha}(z)=\frac{\alpha-z}{1-\bar{\alpha}z}}$
> may be useful.

### ?


Find a conformal map from $D = \{z :\  |z| < 1,\ |z - 1/2| > 1/2\}$
to the unit disk $\Delta=\{z: \ |z|<1\}$.

## Fall 2015

### ?


Let $a_n \neq 0$ and assume that $\displaystyle
\lim_{n \rightarrow \infty} \frac{|a_{n+1}|}{|a_n|} = L$. Show that
$\displaystyle
\lim_{n \rightarrow \infty}
\sqrt[n]{|a_n|} = L.
%p_n^{\frac{1}{n}} = L.$ In particular, this shows that when
applicable, the ratio test can be used to calculate the radius of
convergence of a power series.

### ?


(a) Let $z, w$ be complex numbers, such that $\bar{z} w \neq 1$.
Prove that
$$\abs{\frac{w - z}{1 - \bar{w} z}} < 1 \; \; \; \mbox{if} \; |z| < 1 \; \mbox{and}\; |w| < 1,$$
and also that
$$\abs{\frac{w - z}{1 - \bar{w} z}} = 1 \; \; \; \mbox{if} \; |z| = 1 \; \mbox{or}\; |w| = 1.$$

(b) Prove that for fixed $w$ in the unit disk $\mathbb D$, the
mapping $$F: z \mapsto \frac{w - z}{1 - \bar{w} z}$$ satisfies the
following conditions:

(i) $F$ maps $\mathbb D$ to itself and is holomorphic. 

(ii) $F$ interchanges $0$ and $w$, namely, $F(0) = w$ and
$F(w) = 0$.

(iii) $|F(z)| = 1$ if $|z| = 1$.

(iv) $F: {\mathbb D} \mapsto {\mathbb D}$ is bijective. 

> Hint: Calculate $F \circ F$.

### ?


Use $n$-th roots of unity (i.e. solutions of $z^n - 1 =0$) to show
that
$$2^{n-1} \sin\frac{\pi}{n} \sin\frac{2\pi}{n} \cdots \sin\frac{(n-1)\pi}{n}
= n
\; .$$ 

> Hint: $1 - \cos 2 \theta = 2 \sin^2 \theta,\; \sin 2 \theta = 2 \sin \theta \cos \theta$.

(a) Show that in polar coordinates, the Cauchy-Riemann
equations take the form

$$\frac{\partial u}{\partial r} = \frac{1}{r} \frac{\partial v}{\partial \theta}
\; \; \; \text{and} \; \; \;
\frac{\partial v}{\partial r} = - \frac{1}{r} \frac{\partial u}{\partial \theta}$$

(b) Use these equations to show that the logarithm function
defined by $$\log z = \log r + i \theta \; \;
\mbox{where} \; z = r e^{i \theta } \; \mbox{with} \; - \pi < \theta < \pi$$
is a holomorphic function in the region
$r>0, \; - \pi < \theta < \pi$. Also show that $\log z$ defined
above is not continuous in $r>0$.

### ?


Assume $f$ is continuous in the region:
$x \geq x_0, \; 0 \leq y \leq b$ and the limit
$$\displaystyle \lim_{x \rightarrow + \infty} f(x + iy) = A$$ exists
uniformly with respect to $y$ (independent of $y$). Show that
$$\lim_{x \rightarrow + \infty} \int_{\gamma_x} f(z) dz  = iA b \; , \; \;$$
where $\gamma_x : = \{ z \; | \; z = x + it, \; 0 \leq  t \leq b\}.$

### ?


(Cauchy's formula for "exterior" region) Let $\gamma$ be piecewise
smooth simple closed curve with interior $\Omega_1$ and exterior
$\Omega_2$. Assume $f'(z)$ exists in an open set containing $\gamma$
and $\Omega_2$ and $\lim_{z \rightarrow \infty } f(z) = A$. Show
that
$$\frac{1}{2 \pi i} \int_\gamma \frac{f(\xi)}{\xi - z} \, d \xi =
\begin{cases}
A,          &     \text{if\ $z \in \Omega_1$}, \\
-f (z) + A, &  \text{if\ $z \in \Omega_2$}
\end{cases}$$

### ?


Let $f(z)$ be bounded and analytic in $\mathbb C$. Let $a \neq b$ be
any fixed complex numbers. Show that the following limit exists
$$\lim_{R \rightarrow \infty} \int_{|z|=R} \frac{f(z)}{(z-a)(z-b)} dz.$$
Use this to show that $f(z)$ must be a constant (Liouville's
theorem).

### ?


Prove by *justifying all steps* that for all $\xi \in {\mathbb C}$
we have $\displaystyle
e^{- \pi \xi^2} = \int_{- \infty}^\infty e^{- \pi x^2} e^{2 \pi i x \xi} dx \; .$

> Hint: You may use that fact in Example 1 on p. 42 of the textbook
without proof, i.e., you may assume the above is true for real
values of $\xi$.

### ?


Suppose that $f$ is holomorphic in an open set containing the closed
unit disc, except for a pole at $z_0$ on the unit circle. Let
$\displaystyle
%f(z) = \sum_{n = 1}^\infty a_n z^n
f(z) = \sum_{n = 1}^\infty c_n z^n$ denote the the power series in
the open disc. Show that (1) $c_n \neq 0$ for all large enough
$n$'s, and (2)
$\displaystyle \lim_{n \rightarrow \infty} \frac{c_n}{c_{n+1}}= z_0$.

### ?


Let $f(z)$ be a non-constant analytic function in $|z|>0$ such that
$f(z_n) = 0$ for infinite many points $z_n$ with
$\lim_{n \rightarrow \infty} z_n =0$. Show that $z=0$ is an
essential singularity for $f(z)$. (An example of such a function is
$f(z) = \sin (1/z)$.)

### ?


Let $f$ be entire and suppose that
$\lim_{z \rightarrow \infty} f(z) = \infty$. Show that $f$ is a
polynomial.

### ?


Expand the following functions into Laurent series in the indicated
regions:

(a)
$\displaystyle f(z) = \frac{z^2 - 1}{ (z+2)(z+3)}, \; \; 2 < |z| < 3$,
$3 < |z| < + \infty$.

(b)
$\displaystyle f(z) = \sin \frac{z}{1-z}, \; \; 0 < |z-1| < + \infty$

### ?


Assume $f(z)$ is analytic in region $D$ and $\Gamma$ is a
rectifiable curve in $D$ with interior in $D$. Prove that if $f(z)$
is real for all $z \in \Gamma$, then $f(z)$ is a constant.

### ?


Find the number of roots of $z^4 - 6z + 3 =0$ in $|z|<1$ and
$1 < |z| < 2$ respectively.

### ?


Prove that $z^4 + 2 z^3 - 2z + 10 =0$ has exactly one root in each
open quadrant.

### ?


(1) Let $f(z) \in H({\mathbb D})$, $\text{Re}(f(z)) >0$,
$f(0)= a>0$. Show that $$|\frac{f(z)-a}{f(z)+a}| \leq |z|, \; \; \;
|f'(0)| \leq 2a.$$

(2) Show that the above is still true if $\text{Re}(f(z)) >0$ is
replaced with $\text{Re}(f(z)) \geq 0$.

### ?


Assume $f(z)$ is analytic in ${\mathbb D}$ and $f(0)=0$ and is not a
rotation (i.e. $f(z) \neq e^{i \theta} z$). Show that
$\displaystyle \sum_{n=1}^\infty f^{n}(z)$ converges uniformly to an
analytic function on compact subsets of ${\mathbb D}$, where
$f^{n+1}(z) = f(f^{n}(z))$.

### ?


Let $f(z) = \sum_{n=0}^\infty c_n z^n$ be analytic and one-to-one in
$|z| < 1$. For $0<r<1$, let $D_r$ be the disk $|z|<r$. Show that the
area of $f(D_r)$ is finite and is given by
$$S = \pi \sum_{n=1}^\infty n |c_n|^2 r^{2n}.$$ (Note that in
general the area of $f(D_1)$ is infinite.)

### ?


Let $f(z) = \sum_{n= -\infty}^\infty c_n z^n$ be analytic and
one-to-one in $r_0< |z| < R_0$. For $r_0<r<R<R_0$, let $D(r,R)$ be
the annulus $r<|z|<R$. Show that the area of $f(D(r,R))$ is finite
and is given by
$$S = \pi \sum_{n=- \infty}^\infty n |c_n|^2 (R^{2n} - r^{2n}).$$

## Spring 2015

### ?


Let $a_n(z)$ be an analytic sequence in a domain $D$ such that
$\displaystyle \sum_{n=0}^\infty |a_n(z)|$ converges uniformly on
bounded and closed sub-regions of $D$. Show that
$\displaystyle \sum_{n=0}^\infty |a'_n(z)|$ converges uniformly on
bounded and closed sub-regions of $D$.

### ?


Let $f_n, f$ be analytic functions on the unit disk ${\mathbb D}$.
Show that the following are equivalent.

(i) $f_n(z)$ converges to $f(z)$ uniformly on compact subsets in
$\mathbb D$.

(ii) $\int_{|z|= r} |f_n(z) - f(z)| \, |dz|$ converges to $0$ if
$0< r<1$.

### ?


Let $f$ and $g$ be non-zero analytic functions on a region $\Omega$.
Assume $|f(z)| = |g(z)|$ for all $z$ in $\Omega$. Show that
$f(z) = e^{i \theta} g(z)$ in $\Omega$ for some
$0 \leq \theta < 2 \pi$.

### ?


Suppose $f$ is analytic in an open set containing the unit disc
$\mathbb D$ and $|f(z)| =1$ when $|z|$=1. Show that either
$f(z) = e^{i \theta}$ for some $\theta \in \mathbb R$ or there are
finite number of $z_k \in \mathbb D$, $k \leq n$ and
$\theta \in \mathbb R$ such that
$\displaystyle f(z) = e^{i\theta} \prod_{k=1}^n \frac{z-z_k}{1 - \bar{z}_k z } \, .$

> Also cf. Stein et al, 1.4.7, 3.8.17

### ?


(1) Let $p(z)$ be a polynomial, $R>0$ any positive number, and
$m \geq 1$ an integer. Let
$M_R = \sup \{ |z^{m} p(z) - 1|: |z| = R  \}$. Show that $M_R>1$.

(2) Let $m \geq 1$ be an integer and
$K = \{z \in {\mathbb C}: r \leq |z| \leq R \}$ where $r<R$.
Show (i) using (1) as well as, (ii) without using (1) that there
exists a positive number $\varepsilon_0>0$ such that for each
polynomial $p(z)$,
$$\sup \{|p(z) - z^{-m}|: z \in K  \} \geq \varepsilon_0 \, .$$

### ?


Let $\displaystyle f(z) = \frac{1}{z} + \frac{1}{z^2 -1}$. Find all
the Laurent series of $f$ and describe the largest annuli in which
these series are valid.

### ?


Suppose $f$ is entire and there exist $A, R >0$ and natural number
$N$ such that $|f(z)| \leq A |z|^N$ for $|z| \geq R$. Show that (i)
$f$ is a polynomial and (ii) the degree of $f$ is at most $N$.

### ?


Suppose $f$ is entire and there exist $A, R >0$ and natural number
$N$ such that $|f(z)| \geq A |z|^N$ for $|z| \geq R$. Show that (i)
$f$ is a polynomial and (ii) the degree of $f$ is at least $N$.

### ?


(1) Explicitly write down an example of a non-zero analytic
function in $|z|<1$ which has infinitely zeros in $|z|<1$.

(2) Why does not the phenomenon in (1) contradict the uniqueness
theorem?

### ?


(1) Assume $u$ is harmonic on open set $O$ and $z_n$ is a sequence
in $O$ such that $u(z_n) = 0$ and $\lim z_n \in O$. Prove or
disprove that $u$ is identically zero. What if $O$ is a region?

(2) Assume $u$ is harmonic on open set $O$ and $u(z) = 0$ on a
disc in $O$. Prove or disprove that $u$ is identically zero. What if
$O$ is a region?

(3) Formulate and prove a Schwarz reflection principle for
harmonic functions 

> cf. Theorem 5.6 on p.60 of Stein et al.

> Hint: Verify the mean value property for your new function obtained by
Schwarz reflection principle.

### ?


Let $f$ be holomorphic in a neighborhood of $D_r(z_0)$. Show that
for any $s<r$, there exists a constant $c>0$ such that
$$||f||_{(\infty, s)} \leq c ||f||_{(1, r)},$$ where
$\displaystyle |f||_{(\infty, s)} = \text{sup}_{z \in D_s(z_0)}|f(z)|$
and $\displaystyle ||f||_{(1, r)} = \int_{D_r(z_0)} |f(z)|dx dy$.

> Note: Exercise 3.8.20 on p.107 in Stein et al is a
straightforward consequence of this stronger result using the
integral form of the Cauchy-Schwarz inequality in real analysis.

### ?


(1) Let $f$ be analytic in $\Omega: 0<|z-a|<r$ except at a
sequence of poles $a_n \in \Omega$ with
$\lim_{n \rightarrow \infty} a_n = a$. Show that for any
$w \in \mathbb C$, there exists a sequence $z_n \in \Omega$ such
that $\lim_{n \rightarrow \infty} f(z_n) = w$.

(2) Explain the similarity and difference between the above
assertion and the Weierstrass-Casorati theorem.

### ?


Compute the following integrals.

\(i\) $\displaystyle \int_0^\infty \frac{1}{(1 + x^n)^2} \, dx$,
$n \geq 1$ (ii)
$\displaystyle \int_0^\infty \frac{\cos x}{(x^2 + a^2)^2} \, dx$,
$a \in \mathbb R$ (iii)
$\displaystyle \int_0^\pi \frac{1}{a + \sin \theta} \, d \theta$,
$a>1$

\(iv\) $\displaystyle \int_0^{\frac{\pi}{2}}
\frac{d \theta}{a+ \sin ^2 \theta},$ $a >0$. (v)
$\displaystyle \int_{|z|=2} \frac{1}{(z^{5} -1) (z-3)} \, dz$ (v)
$\displaystyle \int_{- \infty}^{\infty} \frac{\sin \pi a}{\cosh \pi x + \cos \pi a} e^{- i x \xi} \, d x$,
$0< a <1$, $\xi \in \mathbb R$ (vi)
$\displaystyle \int_{|z| = 1} \cot^2 z \, dz$.

### ?


Compute the following integrals.

\(i\) $\displaystyle \int_0^\infty \frac{\sin x}{x} \, dx$ (ii)
$\displaystyle \int_0^\infty (\frac{\sin x}{x})^2 \, dx$ (iii)
$\displaystyle \int_0^\infty \frac{x^{a-1}}{(1 + x)^2} \, dx$,
$0< a < 2$

\(i\)
$\displaystyle \int_0^\infty \frac{\cos a x - \cos bx}{x^2} dx$,
$a, b >0$ (ii)
$\displaystyle \int_0^\infty \frac{x^{a-1}}{1 + x^n} \, dx$,
$0< a < n$

\(iii\) $\displaystyle \int_0^\infty \frac{\log x}{1 + x^n} \, dx$,
$n \geq 2$ (iv)
$\displaystyle \int_0^\infty \frac{\log x}{(1 + x^2)^2} dx$ (v)
$\displaystyle \int_0^{\pi} \log|1 - a \sin \theta| d \theta$,
$a \in \mathbb C$

### ?


Let $0<r<1$. Show that polynomials
$P_n(z)  = 1 + 2z + 3 z^2 + \cdots + n z^{n-1}$ have no zeros in
$|z|<r$ for all sufficiently large $n$'s.

### ?


Let $f$ be an analytic function on a region $\Omega$. Show that $f$
is a constant if there is a simple closed curve $\gamma$ in $\Omega$
such that its image $f(\gamma)$ is contained in the real axis.

### ?


(1) Show that $\displaystyle \frac{\pi^2}{\sin^2 \pi z}$ and
$\displaystyle g(z) = \sum_{n = - \infty}^{ \infty} \frac{1}{(z-n)^2}$
have the same principal part at each integer point.

(2) Show that
$\displaystyle h(z) = \frac{\pi^2}{\sin^2 \pi z} - g(z)$ is bounded
on $\mathbb C$ and conclude that
$\displaystyle \frac{\pi^2}{\sin^2 \pi z} = \sum_{n = - \infty}^{ \infty} \frac{1}{(z-n)^2} \, .$

### ?


Let $f(z)$ be an analytic function on
${\mathbb C} \backslash \{ z_0 \}$, where $z_0$ is a fixed point.
Assume that $f(z)$ is bijective from
${\mathbb C} \backslash \{ z_0 \}$ onto its image, and that $f(z)$
is bounded outside $D_r(z_0)$, where $r$ is some fixed positive
number. Show that there exist $a, b, c, d \in \mathbb C$ with
$ad-bc \neq 0$, $c \neq 0$ such that
$\displaystyle f(z) = \frac{az + b}{cz + d}$.

### ?


Assume $f(z)$ is analytic in ${\mathbb D}: |z|<1$ and $f(0)=0$ and
is not a rotation (i.e. $f(z) \neq e^{i \theta} z$). Show that
$\displaystyle \sum_{n=1}^\infty f^{n}(z)$ converges uniformly to an
analytic function on compact subsets of ${\mathbb D}$, where
$f^{n+1}(z) = f(f^{n}(z))$.

### ?


Let $f$ be a non-constant analytic function on $\mathbb D$ with
$f(\mathbb D) \subseteq \mathbb D$. Use $\psi_{a} (f(z))$ (where
$a=f(0)$, $\displaystyle \psi_a(z) = \frac{a - z}{1 - \bar{a}z}$) to
prove that $\displaystyle
\frac{|f(0)| - |z|}{1 + |f(0)||z|} \leq |f(z)| \leq
\frac{|f(0)| + |z|}{1 - |f(0)||z|}$.

### ?


Find a conformal map

1.  from $\{ z: |z - 1/2| > 1/2, \text{Re}(z)>0 \}$ to $\mathbb H$

2.  from $\{ z: |z - 1/2| > 1/2, |z| <1  \}$ to $\mathbb D$

3.  from the intersection of the disk $|z + i| < \sqrt{2}$ with
    ${\mathbb H}$ to ${\mathbb D}$.

4.  from ${\mathbb D}  \backslash [a, 1)$ to
    ${\mathbb D} \backslash [0, 1)$ ($0<a<1)$. \[ Short solution
    possible using Blaschke factor\]

5.  from $\{ z: |z| < 1, \text{Re}(z) > 0 \} \backslash (0, 1/2]$ to
    $\mathbb H$.

### ?


Let $C$ and $C'$ be two circles and let $z_1 \in C$, $z_2 \notin C$,
$z'_1 \in C'$, $z'_2 \notin C'$. Show that there is a unique
fractional linear transformation $f$ with $f(C) = C'$ and
$f(z_1) = z'_1$, $f(z_2) = z'_2$.

### ?


Assume $f_n \in H(\Omega)$ is a sequence of holomorphic functions on
the region $\Omega$ that are uniformly bounded on compact subsets
and $f \in H(\Omega)$ is such that the set
$\displaystyle \{z \in \Omega: \lim_{n \rightarrow \infty} f_n(z) = f(z) \}$
has a limit point in $\Omega$. Show that $f_n$ converges to $f$
uniformly on compact subsets of $\Omega$.

### ?


Let
$\displaystyle{\psi_{\alpha}(z)=\frac{\alpha-z}{1-\bar{\alpha}z}}$
with $|\alpha|<1$ and ${\mathbb D}=\{z:\ |z|<1\}$. Prove that

-   $\displaystyle{\frac{1}{\pi}\iint_{{\mathbb D}} |\psi'_{\alpha}|^2 dx dy =1}$.

-   $\displaystyle{\frac{1}{\pi}\iint_{{\mathbb D}} |\psi'_{\alpha}| dx dy =\frac{1-|\alpha|^2}{|\alpha|^2}
    \log \frac{1}{1-|\alpha|^2}}$.

### ?


Prove that
$\displaystyle{f(z)=-\frac{1}{2}\left(z+\frac{1}{z}\right)}$ is a
conformal map from half disc $\{z=x+iy:\ |z|<1,\ y>0\}$ to upper
half plane ${\mathbb H}=\{z=x+iy:\ y>0\}$.

### ?


Let $\Omega$ be a simply connected open set and let $\gamma$ be a
simple closed contour in $\Omega$ and enclosing a bounded region $U$
anticlockwise. Let $f: \ \Omega \to {\mathbb C}$ be a holomorphic
function and $|f(z)|\leq M$ for all $z\in \gamma$. Prove that
$|f(z)|\leq M$ for all $z\in U$.

### ?


Compute the following integrals. (i)
$\displaystyle \int_0^\infty \frac{x^{a-1}}{1 + x^n} \, dx$,
$0< a < n$ (ii)
$\displaystyle \int_0^\infty \frac{\log x}{(1 + x^2)^2}\, dx$

### ?


Let $0<r<1$. Show that polynomials
$P_n(z)  = 1 + 2z + 3 z^2 + \cdots + n z^{n-1}$ have no zeros in
$|z|<r$ for all sufficiently large $n$'s.

### ?


Let $f$ be holomorphic in a neighborhood of $D_r(z_0)$. Show that
for any $s<r$, there exists a constant $c>0$ such that
$$\|f\|_{(\infty, s)} \leq c \|f\|_{(1, r)},$$ where
$\displaystyle \|f\|_{(\infty, s)} = \text{sup}_{z \in D_s(z_0)}|f(z)|$
and $\displaystyle \|f\|_{(1, r)} = \int_{D_r(z_0)} |f(z)|dx dy$.

### ?


Let $\displaystyle{\psi_{\alpha}(z)=\frac{\alpha-z}{1-\bar{\alpha}z}}$
with $|\alpha|<1$ and ${\mathbb D}=\{z:\ |z|<1\}$. Prove that

-   $\displaystyle{\frac{1}{\pi}\iint_{{\mathbb D}} |\psi'_{\alpha}|^2 dx dy =1}$.

-   $\displaystyle{\frac{1}{\pi}\iint_{{\mathbb D}} |\psi'_{\alpha}| dx dy =\frac{1-|\alpha|^2}{|\alpha|^2}
    \log \frac{1}{1-|\alpha|^2}}$.

Prove that $\displaystyle{f(z)=-\frac{1}{2}\left(z+\frac{1}{z}\right)}$
is a conformal map from half disc $\{z=x+iy:\ |z|<1,\ y>0\}$ to upper
half plane $\mathbb H=\{z=x+iy:\ y>0\}$.

### ?


Let $\Omega$ be a simply connected open set and let $\gamma$ be a simple
closed contour in $\Omega$ and enclosing a bounded region $U$
anticlockwise. Let $f: \ \Omega \to {\mathbb C}$ be a holomorphic
function and $|f(z)|\leq M$ for all $z\in \gamma$. Prove that
$|f(z)|\leq M$ for all $z\in U$.

### ?


Compute the following integrals. (i)
$\displaystyle \int_0^\infty \frac{x^{a-1}}{1 + x^n} \, dx$, $0< a < n$
(ii) $\displaystyle \int_0^\infty \frac{\log x}{(1 + x^2)^2}\, dx$

### ?


Let $0<r<1$. Show that polynomials
$P_n(z)  = 1 + 2z + 3 z^2 + \cdots + n z^{n-1}$ have no zeros in $|z|<r$
for all sufficiently large $n$'s.

### ?


Let $f$ be holomorphic in a neighborhood of $D_r(z_0)$. Show that for
any $s<r$, there exists a constant $c>0$ such that
$$\|f\|_{(\infty, s)} \leq c \|f\|_{(1, r)},$$ where
$\displaystyle \|f\|_{(\infty, s)} = \text{sup}_{z \in D_s(z_0)}|f(z)|$
and $\displaystyle \|f\|_{(1, r)} = \int_{D_r(z_0)} |f(z)|dx dy$.

## Fall 2016

### ?


Let $u(x,y)$ be harmonic and have continuous partial derivatives of
order three in an open disc of radius $R>0$.

(a) Let two points $(a,b), (x,y)$ in this disk be given. Show that
the following integral is independent of the path in this disk
joining these points:
$$v(x,y) = \int_{a,b}^{x,y} ( -\frac{\partial u}{\partial y}dx +  \frac{\partial u}{\partial x}dy).$$\

(b) \hfill

    (i) Prove that $u(x,y)+i v(x,y)$ is an analytic function in this
disc.

    (ii) Prove that $v(x,y)$ is harmonic in this disc.

### ?


(a) $f(z)= u(x,y) +i v(x,y)$ be analytic in a domain
$D\subset {\mathbb C}$. Let $z_0=(x_0,y_0)$ be a point in $D$ which
is in the intersection of the curves $u(x,y)= c_1$ and $v(x,y)=c_2$,
where $c_1$ and $c_2$ are constants. Suppose that $f'(z_0)\neq 0$.
Prove that the lines tangent to these curves at $z_0$ are
perpendicular.

(b) Let $f(z)=z^2$ be defined in ${\mathbb C}$. 
  (i)   Describe the
        level curves of $\mbox{\textrm Re}{(f)}$ and of $\mbox{Im}{(f)}$.
  
  (ii)  What are the angles of intersections between the level curves
        $\mbox{\textrm Re}{(f)}=0$ and $\mbox{\textrm Im}{(f)}$? Is your answer in
        agreement with part a) of this question?

### ?


(a) $f: D\rightarrow {\mathbb C}$ be a continuous function, where
$D\subset {\mathbb C}$ is a domain.Let $\alpha:[a,b]\rightarrow D$
be a smooth curve. Give a precise definition of the *complex line
integral* $$\int_{\alpha} f.$$

(b) Assume that there exists a constant $M$ such that
$|f(\tau)|\leq M$ for all $\tau\in \mbox{\textrm Image}(\alpha$). Prove
that
$$\big | \int_{\alpha} f \big |\leq M \times \mbox{\textrm length}(\alpha).$$

(c) Let $C_R$ be the circle $|z|=R$, described in the
counterclockwise direction, where $R>1$. Provide an upper bound for
$\big | \int_{C_R} \dfrac{\log{(z)} }{z^2} \big |,$ which depends
[only]{.underline} on $R$ and other constants.

### ?


(a) Let Let $f:{\mathbb C}\rightarrow {\mathbb C}$ be an entire
function. Assume the existence of a non-negative integer $m$, and of
positive constants $L$ and $R$, such that for all $z$ with $|z|>R$
the inequality $$|f(z)| \leq L |z|^m$$ holds. Prove that $f$ is a
polynomial of degree $\leq m$.

(b) Let $f:{\mathbb C}\rightarrow {\mathbb C}$ be an entire
function. Suppose that there exists a real number M such that for
all $z\in {\mathbb C}$ $$\mbox{\textrm Re} (f) \leq M.$$ Prove that $f$
must be a constant.

### ?


Prove that all the roots of the complex polynomial
$$z^7 - 5 z^3 +12 =0$$ lie between the circles $|z|=1$ and $|z|=2$.

### ?


(a) Let $F$ be an analytic function inside and on a simple closed
curve $C$, except for a pole of order $m\geq 1$ at $z=a$ inside $C$.
Prove that

$$\frac{1}{2 \pi i}\oint_{C} F(\tau) d\tau = 
\lim_{\tau\rightarrow a} \frac{d^{m-1}}{d\tau^{m-1}}\big((\tau-a)^m F(\tau))\big).$$

(b) Evaluate $$\oint_{C}\frac{e^{\tau}}{(\tau^2+\pi^2)^2}d\tau$$
where $C$ is the circle $|z|=4$.

### ?


Find the conformal map that takes the upper half-plane comformally
onto the half-strip $\{
w=x+iy:\ -\pi/2<x<\pi/2\ y>0\}$.

### ?


Compute the integral
$\displaystyle{\int_{-\infty}^{\infty} \frac{e^{-2\pi ix\xi}}{\cosh\pi x}dx}$
where $\displaystyle{\cosh z=\frac{e^{z}+e^{-z}}{2}}$.
