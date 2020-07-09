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



