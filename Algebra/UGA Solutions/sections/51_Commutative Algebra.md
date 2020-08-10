# Commutative Algebra



## Spring 2019 #6

### a

Define the set of proper ideals
$$
S = \theset{J \suchthat I   \subseteq J < R}
,$$

which is a poset under set inclusion.

Given a chain $J_1 \subseteq \cdots$, there is an upper bound $J \definedas \union J_i$, so Zorn's lemma applies.

### b
$\implies$:

We will show that $x\in J(R) \implies 1+x \in R\units$, from which the result follows by letting $x=rx$.

Let $x\in J(R)$, so it is in every maximal ideal, and suppose toward a contradiction that $1+x$ is **not** a unit.

Then consider $I = \generators{1+x} \normal R$. 
Since $1+x$ is not a unit, we can't write $s(1+x) = 1$ for any $s\in R$, and so $1 \not\in I$ and $I\neq R$

So $I < R$ is proper and thus contained in some maximal proper ideal $\mathfrak{m} < R$ by part (1), and so we have $1+x \in \mathfrak{m}$.
Since $x\in J(R)$, $x\in \mathfrak{m}$ as well.

But then $(1+x) - x = 1 \in \mathfrak{m}$ which forces $\mathfrak{m} = R$.

$\impliedby$

Fix $x\in R$, and suppose $1+rx$ is a unit for all $r\in R$.

 
Suppose towards a contradiction that there is a maximal ideal $\mathfrak{m}$ such that $x\not \in \mathfrak{m}$ and thus $x\not\in J(R)$.

Consider 
$$
M' \definedas \theset{rx + m \suchthat r\in R,~ m\in M}
.$$

Since $\mathfrak{m}$ was maximal, $\mathfrak{m} \subsetneq M'$ and so $M' = R$.

So every element in $R$ can be written as $rx + m$ for some $r\in R, m\in M$.
But $1\in R$, so we have 
$$
1 = rx + m
.$$ 

So let $s = -r$ and write $1 = sx - m$, and so $m = 1 + sx$.

Since $s\in R$ by assumption $1+sx$ is a unit and thus $m \in \mathfrak{m}$ is a unit, a contradiction.

So $x\in \mathfrak{m}$ for every $\mathfrak{m}$ and thus $x\in J(R)$.

### c

> - $\mathfrak N(R) = \theset{x\in R \suchthat x^n = 0 \text{ for some } n}$.
> - $J(R) = \spec_{\text{max}}(R) = \displaystyle\intersect_{\mm \text{ maximal}} \mm$.

We want to show $J(R) = \mathfrak N(R)$.

$\mathfrak N(R) \subseteq J(R)$:

We'll use the fact $x\in \mathfrak N(R) \implies x^n = 0 \implies 1 + rx$ is a unit $\iff x\in J(R)$ by (b):
$$
\sum_{k=1}^{n-1} (-x)^k = \frac{1 - (-x)^n}{1- (-x)} = (1+x)\inv
.$$

$J(R) \subseteq \mathfrak N(R)$:

Let $x \in J(R) \setminus \mathfrak N(R)$.

Since $R$ is finite, $x^m = x$ for some $m > 0$.
Without loss of generality, we can suppose $x^2 = x$ by replacing $x^m$ with $x^{2m}$.

If $1-x$ is not a unit, then $\generators{1-x}$ is a nontrivial proper ideal, which by (a) is contained in some maximal ideal $\mm$. 
But then $x\in \mm$ and $1-x \in \mm \implies x + (1-x) = 1 \in \mm$, a contradiction.

So $1-x$ is a unit, so let $u = (1-x)\inv$.

Then
\[
(1-x)x &= x - x^2 = x - x = 0 \\
&\implies u (1-x)x = x = 0 \\
&\implies x=0
.\]

## Fall 2018 #7

### a

Let $\phi$ denote the map in question, it suffices to show that $\phi$ is $R\dash$linear, i.e. $\phi(s\vector x + \vector y) = s\phi(\vector x) + \phi(\vector y)$:

\[
\phi(s\vector x + \vector y) 
&= r(s\vector x + \vector y) \\
&= rs\vector x + r\vector y \\
&= s(r\vector x) + (r\vector y) \\
&= s\phi(\vector x) + \phi(\vector y)
.\]

### b

We identify $\ker \phi = \theset{x\in R \suchthat rx = 0}$, and since $r\neq 0$ by assumption, this implies each such $x$ is a zero divisor by definition (and $\ker \phi$ is nonempty by assumption).

Similarly, we identify $\im \phi = \theset{y = rx \suchthat x\in R}$. 
So let $y\in \im \phi$.
Since $r$ is a zero divisor, there exists some $z\in R$ such that $rz = 0$.

But then 
$$
yz = rxz = xrz = x\cdot 0 = 0
$$ 
since $R$ is commutative, so $y$ is a zero divisor.


### c

> See 1964 Annals "Properties of rings with a finite number of zero divisors"

Let $Z \definedas \theset{z_i}_{i=1}^n$ be the set of $n$ zero divisors in $R$.
Let $\phi_i$ be the $n$ maps $x \mapsto z_i x$, and let $K_i = \ker \phi_i$ be the corresponding kernels.

Fix an $i$.
By (b), $K_i$ consists of zero divisors, so 
$$
\abs{K_i} \leq n < \infty \quad \text{for each } i
.$$

Now consider $R/K_i \definedas \theset{r + K_i}$.
By the first isomorphism theorem, $R/K_i \cong \im \phi$, and by (b) every element in the image is a zero divisor, so 
$$
[R: K_i] = \abs{R/K_i} = \abs{\im \phi_i} \leq n 
.$$

But then 
$$
\abs{R} = [R:K_i]\cdot \abs{K_i} \leq n\cdot n = n^2 
.$$

### d

By (c), if there are exactly 2 zero divisors then $\abs{R} \leq 4$.
Since every element in a finite ring is either a unit or a zero divisor, and $\abs{R\units} \geq 2$ since $\pm 1$ are always units, we must have $\abs{R} = 4$.

Since the characteristic of a ring must divide its size, we have $\ch R = 2$ or $4$.

Using the hint, we see that only $\ZZ/(4)$ has characteristic 4, which has exactly 2 zero divisors given by $[0]_4$ and $[2]_4$.

If $R$ has characteristic 2, we can check the other 3 possibilities.

We can write $\ZZ/(2)[t]/(t^2) = \theset{a + bt \suchthat a,b\in \ZZ/(2)}$, and checking the multiplication table we have

\[
\begin{array}{c|cccc}
			& 0 & 1 	& t & 1+t 	\\ \hline
0 		& 0 & 0 	& 0 & 0   	\\ 
1 		& 0 & 1 	& t & 1+t 	\\ 
t 		& 0 & t 	& \mathbf{0} & t   	\\ 
1 + t & 0 & 1+t & t & 1   	\\ 
\end{array}
,\]

and so we find that $t, 0$ are the zero divisors.

In $\ZZ/(2)[t]/(t^2 - t)$, we can check that $t^2 = t \implies t t^2 = t^2 \implies t(t^2 + 1) = 0 \implies t(t+1) = 0$, so both $t$ and $t+1$ are zero divisors, along with zero, so this is not a possibility.

Similarly, in $\ZZ/(2)[t]/(t^2 + t + 1)$, we can check the bottom-right corner of the multiplication table to find
\[
\left[\begin{array}{c|cc}
	& t 	& 1 +t \\ \hline
t & 1+t & 1 \\
t & 1 	& t \\
\end{array}\right]
,\]

and so this ring only has one zero divisor.

Thus the only possibilities are:

\[
R &\cong \ZZ/(4) \\
R &\cong \ZZ/(2)[t] / (t^2)
.\]

$\qed$
