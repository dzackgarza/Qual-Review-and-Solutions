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
