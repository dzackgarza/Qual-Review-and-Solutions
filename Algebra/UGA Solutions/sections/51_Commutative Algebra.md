# Commutative Algebra


## Fall 2019 #3

> Just fiddling with computations.
> Context hints that we should be considering things like $x^2$ and $a+b$.

### a
\[
2a  = (2a)^2 = 4a^2 = 4a \implies 2a = 0
.\]

Note that this implies $x = -x$ for all $x\in R$.

### b
\[
a+b = (a+b)^2 &= a^2 + ab + ba + b^2 = a + ab + ba + b \\
&\implies ab + ba = 0 \\
&\implies ab = -ba \\
&\implies ab = ba \quad\text{by (a)}
.\]

## Fall 2019 #6

> Prime ideal: $\mathfrak{p}$ is prime iff $ab \in \mathfrak{p} \implies a\in \mathfrak{p}$ or $b\in \mathfrak{p}$.
> Silly fact: 0 is in every ideal!
> 
> **Zorn's Lemma:** Given a poset, if every chain has an upper bound, then there is a maximal element. (Chain: totally ordered subset.)
> 
> **Corollary:** If $S\subset R$ is multiplicatively closed with $0\not\in S$ then $\theset{I \normal R \suchthat J\intersect S = \emptyset}$ has a maximal element.
> (TODO: PROVE)
>
> **Theorem:** If $R$ is commutative, maximal $\implies$ prime for ideals.
> (TODO: PROVE)
>
> **Theorem:** Non-units are contained in a maximal ideal. (See HW?)

### a

Let $\mathfrak{p}$ be prime and $x\in N$.
Then $x^k = 0 \in \mathfrak{p}$ for some $k$, and thus $x^k = x x^{k-1} \in \mathfrak p$.
Since $\mathfrak p$ is prime, inductively we obtain $x\in\mathfrak p$.

### b

Let $S = \theset{r^k \mid k\in \NN}$ be the set of positive powers of $r$. 
Then $S^2 \subseteq S$, since $r^{k_1}r^{k_2} = r^{k_1+k_2}$ is also a positive power of $r$, and $0\not\in S$ since $r\neq 0$ and $r\not\in N$.

By the corollary, $\theset{I \normal R \suchthat I\intersect S = \emptyset}$ has a maximal element $\mathfrak{p}$.

Since $R$ is commutative, $\mathfrak{p}$ is prime.

### c

Suppose $R$ has a unique prime ideal $\mathfrak{p}$.

Suppose $r\in R$ is not a unit, and toward a contradiction, suppose that $r$ is also not nilpotent.

Since $r$ is not a unit, $r$ is contained in some maximal (and thus prime) ideal, and thus $r \in \mathfrak{p}$.

Since $r\not\in N$, by (b) there is a maximal ideal $\mathfrak{m}$ that avoids all positive powers of $r$. 
Since $\mathfrak{m}$ is prime, we must have $\mathfrak{m} = \mathfrak{p}$.
But then $r\not\in \mathfrak{p}$, a contradiction.

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


