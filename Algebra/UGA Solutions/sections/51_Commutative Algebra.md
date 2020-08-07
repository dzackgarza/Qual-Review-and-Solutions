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


