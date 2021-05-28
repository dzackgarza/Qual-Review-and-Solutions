# Rouche's Theorem (8155h)

## 1 $\done$

Prove that for every $n\in \ZZ^{\geq 0}$ the following polynomial has no roots in the open unit disc:
\[
f_n(x) \definedas \sum_{k=0}^n {z^k \over k!}
.\]

> Hint: check $n=1,2$ directly.

:::{.solution}
\hfill
:::{.concept}
\hfill

:::
Note

- $f_1(z) = 1+z$, which has the single root $z=-1$ which is not inside $\abs{z} < 1$.
- $f_2(z) = 1 + z + {1\over 2}z^2 = (z - (1+i))(z- (1-i))$, and $\abs{1\pm i} = \sqrt 2 >1$.

- Note that $p_n(z) \converges{n\to\infty}e^z$ uniformly on any compact set.
- Let $r$ be arbitrary and fix $N \definedas \DD_r(0)$, then $p_n(z) \to e^z$ uniformly on $\bar{N}$.
- Set $g_n(z) \definedas p_n(z) / e^z$, then $g_n \to 1$ uniformly on $\bar N$.
- Choose $n\gg 0$ so that $\abs{f(z) - 1} < \eps < 1$ for all $z\in \bar{N}$.
- So take $h(z) = 1$, then on $\bd N$,?

:::


## 2 $\done$
Assume that $\abs b < 1$ and show that the following polynomial has exactly two roots (counting multiplicity) in $\abs{z} < 1$:
\[
f(z) \definedas z^3 + 3z^2 + bz + b^2
.\]

:::{.solution}
\hfill
:::{.concept}
\hfill
Multiple versions of Rouches theorem!
:::

- Set $h(z) = 3z^2$ and $g(z) = z^3 + bz + b^2$.
- Then on $\abs{z} = 1$,
\begin{align*}
\abs{g(z)} \leq 1 + b + b^2 < 3 = 3\abs{z}^2 = \abs{3z^2} = \abs{h}
,\end{align*}
  so $g, h$ have the same number of roots in $\abs{z} \leq_? 1$.

- But $h$ evidently has two roots in this region.

:::


## 3 $\work$
Let $c\in \CC$ with $\abs{c} < {1\over 3}$.
Show that on the open set $\theset{z\in \CC \suchthat \Re(z) < 1}$, the function $f(z) \definedas ce^z$ has exactly one fixed point.


## 4 $\done$
How many roots does the following polynomial have in the open disc $\abs{z} < 1$?
\[
f(z) = z^7 - 4z^3 - 1
.\]

:::{.solution}
\hfill
:::{.concept}
\hfill

:::
- Set $h(z) = -4z^3$ and $g(z) = z^7 - 1$, then on $\abs{z} = 1$,
\begin{align*}
\abs{g(z)} = \abs{z^7 - 1} \leq 1 + 1 = 2 < 4 = \abs{-4z^3} = \abs{h(z)}
.\end{align*}

- So $h$ and $h+g$ have the same number of roots, but $h$ has three roots here.
:::


## 5 $\done$
Let $n\in \ZZ^{\geq 0}$ and show that the equation
\[
e^z = az^n
\]
has $n$ solutions in the open unit disc if $\abs{a} > e$, and no solutions if $\abs{a} < {1\over e}$.

## 6 $\work$
Let $f$ be analytic in a domain $D$ and fix $z_0 \in D$ with $w_0 \definedas f(z_0)$.
Suppose $z_0$ is a zero of $f(z) - w_0$ with finite multiplicity $m$.
Show that there exists $\delta >0$ and $\eps > 0$ such that for each $w$ such that $0 < \abs{w-w_0} < \eps$, the equation $f(z) - w = 0$ has exactly $m$ *distinct* solutions inside the disc $\abs{z-z_0} < \delta$.


## 7 $\work$
For $k=1,2,\cdots, n$, suppose $\abs{a_k} < 1$ and
\[
f(z) \definedas \qty{z - a_1 \over 1 - \bar a_q z} \qty{z-a_2 \over 1 - \bar a_2 z} \cdots \qty{z - a_n \over 1 - \bar a_n z}
.\]
Show that $f(z) = b$ has $n$ solutions in $\abs{z} < 1$.


## 8 $\work$
For each $n\in \ZZ^{\geq 1}$, let
\[
P_n(z) = 1 + z + {1\over 2!} z^2 + \cdots + {1\over n!}z^n
.\]
Show that for sufficiently large $n$, the polynomial $P_n$ has no zeros in $\abs{z} < 10$, while the polynomial $P_n(z) - 1$ has precisely 3 zeros there.

## 9 $\work$
Prove that
\[
\max_{\abs z = 1} \abs{a_0 + a_1 z + \cdots + a_{n-1}z^{n-1} + z^n} \geq 1
.\]

> Hint: the first part of the problem asks for a statement of Rouche's theorem.

## 10 $\work$
Use Rouche's theorem to prove the Fundamental Theorem of Algebra.



# Extras


## ?
Apply Rouché's Theorem to prove the Fundamental Theorem of Algebra: 

If
$$
P_n(z) = a_0 + a_1z + \cdots + a_{n-1}z^{n-1} + a_nz^n\quad  (a_n \neq 0)
$$
is a polynomial of degree $n$, then it has $n$ zeros in $\mathbb{C}$.


## ?
Suppose $f$ is entire and there exist $A, R >0$ and natural number
$N$ such that 
$$|f(z)| \geq A |z|^N\ \text{for}\ |z| \geq R.$$ 

Show that (i) $f$ is a polynomial and (ii) the degree of $f$ is at least
$N$.

### Tie's Extra Questions: Fall 2009

Apply Rouché's Theorem to prove the Fundamental Theorem of Algebra: If
$$P_n(z) = a_0 + a_1z + \cdots + a_{n-1}z^{n-1} + a_nz^n\quad  (a_n \neq 0)$$
is a polynomial of degree n, then it has n zeros in $\mathbb C$.

### Spring 20202 HW 3 #  8

Prove the fundamental theorem of Algebra using

a.  
Rouche's Theorem.

b. 
The maximum modulus principle.

### Spring 20202 HW 3 #  11

Find the number of roots of $p(z) = 4z^4 - 6z + 3$ in $\abs{z} < 1$ and
$1 < \abs{z} < 2$ respectively.

### Spring 20202 HW 3 #  12

Prove that $z^4 + 2z^3 -2z + 10$ has exactly one root in each open
quadrant.

### Spring 20202 HW 3 #  13

Prove that for $a> 0$, $z\tan z - a$ has only real roots.

