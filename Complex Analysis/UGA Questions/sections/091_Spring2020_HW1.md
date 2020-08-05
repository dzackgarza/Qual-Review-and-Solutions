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
