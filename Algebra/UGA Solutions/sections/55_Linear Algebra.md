# Linear Algebra: Diagonalizability

## Spring 2019 #1

> $A$ is diagonalizable iff $\min_A(x)$ is separable.
> See [further discussion here](https://math.stackexchange.com/questions/3027664/if-a-is-invertible-and-an-is-diagonalizable-then-a-is-diagonalizable).

Claim: If $A \in \Gl(m, \FF)$ is invertible and $A^n/\FF$ is diagonalizable, then $A/\FF$ is diagonalizable.


Let $A \in \Gl(m, \FF)$. 
Since $A^n$ is diagonalizable, $\min_{A^n}(x) \in \FF[x]$ is separable and thus factors as a product of $m$ **distinct** linear factors:

$$
\min_{A^n}(x) = \prod_{i=1}^m (x-\lambda_i), \quad \min_{A^n}(A^n) = 0
$$

where $\theset{\lambda_i}_{i=1}^m \subset \FF$ are the **distinct** eigenvalues of $A^n$.

Moreover $A\in \GL(m,\FF) \implies A^n \in \GL(m,\FF)$: $A$ is invertible $\iff \det(A) = d \in \FF\units$, and so $\det(A^n) = \det(A)^n = d^n \in \FF\units$ using the fact that the determinant is a ring morphism $\det: \mat (m\times m) \to\FF$ and $\FF\units$ is closed under multiplication.

So $A^n$ is invertible, and thus has trivial kernel, and thus zero is not an eigenvalue, so $\lambda_i \neq 0$ for any $i$.

Since the $\lambda_i$ are distinct and nonzero, this implies $x^k$ is not a factor of $\mu_{A^n}(x)$ for any $k\geq 0$. 
Thus the $m$ terms in the product correspond to precisely $m$ **distinct linear** factors.

We can now construct a polynomial that annihilates $A$, namely
$$
q_A(x) \definedas \min_{A^n}(x^n) = \prod_{i=1}^m (x^n-\lambda_i) \in \FF[x],
$$

where we can note that $q_A(A) = \min_{A^n}(A^n) = 0$, and so $\min_A(x) \divides q_A(x)$ by minimality.

We now claim that $q_A(x)$ has exactly $n\cdot m$ distinct linear factors in $\bar \FF[x]$, which reduces to showing that no pair $x^n-\lambda_i, x^n-\lambda_j$ share a root.
and that $x^n-\lambda_i$ does not have multiple roots.

- For the first claim, we can factor
  \[
  x^n - \lambda_i = \prod_{k=1}^n (x - \lambda_i^{1\over n} e^{2\pi i k \over n}) \definedas \prod_{k=1}^n (x-\lambda^{1\over n} \zeta_n^k)
  ,\]
  where we now use the fact that $i\neq j \implies \lambda_i^{1\over n} \neq \lambda_j^{1\over n}$. 
  Thus no term in the above product appears as a factor in $x^n - \lambda_j$ for $j\neq i$.

- For the second claim, we can check that $\dd{}{x}\qty{x^n - \lambda_i} = nx^{n-1}\neq 0\in \FF$, and $\gcd(x^n-\lambda_i, nx^{n-1}) = 1$ since the latter term has only the roots $x=0$ with multiplicity $n-1$, whereas $\lambda_i\neq 0 \implies$ zero is not a root of $x^n-\lambda_i$.

But now since $q_A(x)$ has exactly distinct linear factors in $\bar \FF[x]$ and $\min_A(x) \divides q_A(x)$, $\min_A(x) \in \FF[x]$ can only have distinct linear factors, and $A$ is thus diagonalizable over $\FF$.

$\qed$

## Spring 2013 #6

Lemma: every $\vector v\in V$ is $T\dash$cyclic $\iff \chi_T(x)/\kk$ is irreducible.

- $\implies$: Same as argument below.
- $\impliedby$: Suppose $f$ is irreducible, then $f$ is equal to the minimal polynomial of $T$.
- 

### a

Let $f$ be the characteristic polynomial of $T$.

$\implies$:

- By contrapositive, suppose there is a proper nonzero invariant subspace $W<V$ with $T(W) \subseteq W$, we will show the characteristic polynomial $f \definedas \chi_{V, T}(x)$ is reducible.
- Since $T(W)\subseteq W$, the restriction $g\definedas \chi_{V, T}(x) \mid_W: W\to W$ is a linear operator on $W$.
- Claim: $g$ divides $f$ in $\FF[x]$ and $\deg(g) < \deg(f)$.
  - Matrix-dependent proof: \todo{Is there a proof without matrices? What if $V$ is infinite dimensional?}
    - Choose an ordered basis for $W$, say $\mcb_W \definedas \theset{\vector w_1, \cdots, \vector w_k}$ where $k=\dim_F(W)$
    - Claim: this can be extended to a basis of $V$, say $\mcb_V \definedas \theset{\vector w_1, \cdots, \vector w_k, \vector v_1, \cdots, \vector v_j}$ where $k+j = \dim_F(V)$.\todo{How to extend basis?}
      - Note that since $W<V$ is proper, $j\geq 1$.
    - Restrict $T$ to $W$ to get $T_W$, then let $B = [T_W]_{\mcb_W}$ be the matrix representation of $T_W$ with respect to $\mcb_W$.
    - Now consider the matrix representation $[T]_{\mcb_V}$, in block form this is given by
    \begin{align*}
    [T]_{\mcb_V} = 
    \begin{bmatrix}
    B & C \\
    0 & D
    \end{bmatrix}
    \end{align*}
      where we've used that $W<V$ is proper to get the existence of $C, D$ (there is at least one additional row/column since $j\geq 1$ in the extended basis.)
    \todo{Why?}
    - Now expand along the first column block to obtain
    \begin{align*}
    \chi_{T, V}(x) \definedas \det([T]_{\mcb_V} - xI) = \det(B - xI)\cdot \det(D - xI) \definedas \chi_{T, W}(x) \cdot \det(D-xI)
    .\end{align*}
    - Claim: $\det(D - xI) \in xF[x]$ is nontrivial
    - The claim follows because this forces $\deg(\det(D-xI)) \geq 1$ and so $\chi_{T, W}(x)$ is a proper divisor of $\chi_{T, V}(x)$.
- Thus $f$ is reducible.

$\impliedby$

- Suppose $f$ is reducible, then we will produce a proper $T\dash$invariant subspace.
- Claim: if $f$ is reducible, there exists a nonzero, noncyclic vector $\vector v$.
- Then $\spanof_k\theset{T^j\vector v}_{j=1}^d$ is a $T\dash$invariant subspace that is nonzero, and not the entire space since $\vector v$ is not cyclic.

### b

Characterization of diagonalizability: $T$ is diagonalizable over $F \iff \min_{T, F}$ is squarefree in $\bar{F}[x]$?

- Let $\min_{T, F}(x)$ be the minimal polynomial of $T$ and $\chi_{T, F}(x)$ be its characteristic polynomial.
- By Cayley-Hamilton, $\min_{T, F}(x)$ divides $\chi_{T, F}$
- Since $\chi_{T, F}$ is irreducible, these polynomials are equal.
- Claim: $T/F$ is diagonalizable $\iff \min_{T, F}$ splits over $F$ and is squarefree.
- Replace $F$ with its algebraic closure, then $\min_{T, F}$ splits.
- Claim: in characteristic zero, every irreducible polynomial is separable
  - Proof: it must be the case that either $\gcd(f, f') = 1$ or $f' \equiv 0$, where the second case only happens in characteristic $p>0$.
  - The first case is true because $\deg f' < \deg f$, and if $\gcd(f, f') = p$, then $\deg p < \deg f$ and $p\divides f$ forces $p=1$ since $f$ is irreducible.
- So $\min_{T, F}$ splits into distinct linear factors
- Thus $T$ is diagonalizable.

# Linear Algebra: Misc

## Fall 2019 #8

### a.

Let $\vector v \in \Lambda$, so $\vector v = \sum_{i=1}^n r_i \vector e_i$ where $r_i \in \ZZ$ for all $i$.

Then if $\vector x = \sum_{j=1}^n s_j \vector e_j \in \Lambda$ is arbitrary, we have $s_j \in \ZZ$ for all $j$ and 
\[
\inner{\vector v}{\vector x} 
&= \inner{\sum_{i=1}^n r_i \vector e_i}{\sum_{j=1}^n s_j \vector e_j } \\
&= \sum_{i=1}^n \sum_{j=1}^n r_i s_j \inner{\vector e_i}{\vector e_j }  \in \ZZ
\]

since this is a sum of products of integers (since $\inner{\vector e_i}{\vector e_j} \in \ZZ$ for each $i, j$ pair by assumption) so $\vector v \in \Lambda\dual$ by definition.

### b. 


**$\det M \neq 0$**:

Suppose $\det M = 0$. Then $\ker M \neq \vector 0$, so let $\vector v \in \ker M$ be given by $\vector v = \sum_{i=1}^n v_i \vector e_i \neq \vector 0$. 

Note that 
\[
M\vector v = 0 &\implies
\left[
\begin{array}{ccc}
\vector e_1 \cdot \vector e_1 & \vector e_1 \cdot \vector e_2 & \cdots \\
\vector e_2 \cdot \vector e_1 & \vector e_2 \cdot \vector e_2 & \cdots \\
\vdots & \vdots & \ddots
\end{array}
\right]
\left[\begin{array}{c}
v_1 \\ v_2 \\ \vdots
\end{array}\right] = \vector 0 \\ \\
&\implies \sum_{j=1}^n v_j\inner{\vector e_k}{\vector e_j} = 0 \qtext{for each fixed} k
.\]

We can now note that $\inner{\vector e_k}{\vector v} = \sum_{j=1}^n v_j \inner{\vector e_k}{\vector e_j} = 0$ for every $k$ by the above observation, which forces $\vector v = 0$ by non-degeneracy of $\inner{\wait}{\wait}$, a contradiction. 

$\qed$

*Alternative proof:*

Write $M = A^tA$ where $A$ has the $\vector e_i$ as columns. Then
\[
M\vector x = 0 
&\implies A^t A \vector x = 0 \\
&\implies \vector x^t A^t A \vector x = 0 \\
&\implies \norm{A \vector x}^2  = 0 \\
&\implies A\vector x = 0 \\
&\implies \vector x = 0
,\]

since $A$ has full rank because the $\vector e_i$ are linearly independent.

$\qed$

Let $A = [\vector e_1^t, \cdots, \vector e_n^t]$ be the matrix with $\vector e_i$ in the $i$th column.

**The rows of $A\inv$ span $\Lambda\dual$**:

Equivalently, the columns of $A^{-t}$ span $\Lambda\dual$.

Let $B = A^{-t}$ and let $\vector b_i$ denote the columns of $B$, so $\im B = \spanof{\theset{\vector b_i}}$.


Since $A \in \GL(n, \ZZ)$, $A\inv, A^t, A^{-t} \in \GL(n, \ZZ)$ as well.

\[
\vector v \in \Lambda\dual 
&\implies \inner{\vector e_i}{\vector v} = z_i \in \ZZ \quad \forall i \\
&\implies A^t \vector v = \vector z \definedas [z_1, \cdots, z_n] \in \ZZ^n \\
&\implies \vector v = A^{-t} \vector z \definedas B\vector z \in \im B \\
&\implies \vector v \in \im B \\
&\implies \Lambda\dual \subseteq \im B
,\]

and

\[
B^t A = (A^{-t})^t A = A\inv A = I \\
\implies \vector b_i \cdot \vector e_j = \delta_{ij} \in \ZZ \\
\implies \im B \subseteq \spanof~ \Lambda\dual
.\]

$\qed$

### c.

\todo{Todo.}


## Fall 2018 #5

### a

Letting $\vector v$ be fixed, since $\theset{A^j \vector v}$ spans $V$ we have 
\[
B\vector v = \sum_{j=0}^{n-1}c_j A^j \vector v
.\]

So let $p(x) = \sum_{j=0}^{n-1}c_jx^j$.
Then consider how $B$ acts on any basis vector $A^k \vector v$.

We have 
\[
BA^k \vector v 
&= A^k B\vector v \\
&= A^k p(A) \vector v \\
&= p(A) A^k \vector v
,\]

so $B = p(A)$ as operators since their actions agree on every basis vector in $V$.

### b

$\implies$:

If $\theset{A^j \vector v_k \suchthat 0\leq j \leq n-1}$ is linearly independent, this means that $A$ does satisfy any polynomial of degree $d < n$.

So $\deg m_A(x) = n$, and since $m_A(x)$ divides $\chi_A(x)$ and both are monic degree polynomials of degree $n$, they must be equal.

$\impliedby$:

Let $A\actson k[x]$ by $A \actson p(x) \definedas p(A)$.
This induces an invariant factor decomposition $V =\cong \bigoplus k[x]/(f_i)$.
Since the product of the invariant factors is the characteristic polynomial, the largest invariant factor is the minimal polynomial, and these two are equal, there can only be one invariant factor and thus the invariant factor decomposition is
$$
V\cong \frac{k[x]}{(\chi_A(x))}
$$
as an isomorphism of $k[x]\dash$modules.

So $V$ is a cyclic $k[x]$ module, which means that $V = k[x]\actson \vector v$ for some $\vector v\in V$ such that $\ann(\vector v) = \chi_A(x)$.

> I.e. there is some element $\vector v\in V$ whose orbit is all of $V$.

But then noting that monomials span $k[x]$, we can write
\[
V &\cong
k[x] \actson \vector v \\
&\definedas \theset{f(x) \actson \vector v \suchthat f \in k[x]} \\
&= \spanof_k \theset{x^k \actson \vector v \suchthat k \geq 0} \\
&\definedas \spanof_k \theset{A^k\vector v \suchthat k \geq 0}
.\]

Moreover, we can note that if $k \geq \deg \chi_A(x)$, then $A^k$ is a linear combination of $\theset{A^j \mid 0 \leq j \leq n-1}$, and so
\[
V &\cong \spanof_k \theset{A^k\vector v \suchthat k \geq 0} \\
&= \spanof_k \theset{A^k\vector v \suchthat 1 \leq k \leq n-1}
.\]

$\qed$


