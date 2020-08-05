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
