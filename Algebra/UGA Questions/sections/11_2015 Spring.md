# Spring 2015 ("Winter 2015")

## 1
For a prime $p$, let $G$ be a finite $p\dash$group and let $N$ be a normal subgroup of $G$ of order $p$.
Prove that $N$ is contained in the center of $G$.

## 2
Let $\FF$ be a finite field.

a. Give (with proof) the decomposition of the additive group $(\FF, +)$ into a direct sum of cyclic groups.

b. The *exponent* of a finite group is the least common multiple of the orders of its elements.
  Prove that a finite abelian group has an element of order equal to its exponent.

c. Prove that the multiplicative group $(\FF\units, \cdot)$ is cyclic.


## 3
Let $F$ be a field and $V$ a finite dimensional $F\dash$vector space, and let $A, B: V\to V$ be commuting $F\dash$linear maps.
Suppose there is a basis $\mcb_1$ with respect to which $A$ is diagonalizable and a basis $\mcb_2$ with respect to which $B$ is diagonalizable.

Prove that there is a basis $\mcb_3$ with respect to which $A$ and $B$ are both diagonalizable.


## 4
Let $N$ be a positive integer, and let $G$ be a finite group of order $N$.

a. Let $\sym G$ be the set of all bijections from $G\to G$ viewed as a group under composition.
  Note that $\sym G \cong S_N$.
  Prove that the Cayley map 
  \begin{align*}
  C: G&\to \sym G\\
  g &\mapsto (x\mapsto gx)
  \end{align*}
  is an injective homomorphism.

b. Let $\Phi: \sym G\to S_N$ be an isomorphism.
  For $a\in G$ define $\eps(a) \in \theset{\pm 1}$ to be the sign of the permutation $\Phi(C(a))$.
  Suppose that $a$ has order $d$.
  Prove that $\eps(a) = -1 \iff d$ is even and $N/d$ is odd.

c. Suppose $N> 2$ and $n\equiv 2 \mod 4$.
  Prove that $G$ is not simple.

  > Hint: use part (b).


## 5
Let $f(x) = x^4 - 5 \in \QQ[x]$.

a. Compute the Galois group of $f$ over $\QQ$.
b. Compute the Galois group of $f$ over $\QQ(\sqrt{5})$.


## 6

Let $F$ be a field and $n$ a positive integer, and consider
\begin{align*}
A=\left[\begin{array}{ccc}
1 & \dots & 1 \\
& \ddots & \\
1 & \dots & 1
\end{array}\right] \in M_{n}(F)
.\end{align*}

Show that $A$ has a Jordan normal form over $F$ and find it.

> Hint: treat the cases $n\cdot  1 \neq 0$ in $F$ and $n\cdot 1 = 0$ in $F$ separately.

## 7
Let $R$ be a commutative ring, and $S\subset R$ be a nonempty subset that does not contain 0 such that for all $x, y\in S$ we have $xy\in S$.
Let $\mci$ be the set of all ideals $I\normal R$ such that $I\intersect S = \emptyset$.

Show that for every ideal $I\in \mci$, there is an ideal $J\in \mci$ such that $I\subset J$ and $J$ is not properly contained in any other ideal in $\mci$.

Prove that every such ideal $J$ is prime.


## 8
Let $R$ be a PID and $M$ a finitely generated $R\dash$module.

a. Prove that there are $R\dash$submodules 
  \begin{align*}
  0 = M_0 \subset M_1 \subset \cdots \subset M_n = M
  \end{align*}
  such that for all $0\leq i \leq n-1$, the module $M_{i+1}/M_i$ is cyclic.

b. Is the integer $n$ in part (a) uniquely determined by $M$? 
  Prove your answer.


