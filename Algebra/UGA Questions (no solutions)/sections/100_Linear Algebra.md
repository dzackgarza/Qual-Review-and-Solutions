# Linear Algebra: Diagonalizability

## Fall 2017 #7 $\work$
Let $F$ be a field and let $V$ and $W$ be vector spaces over $F$ . 

Make $V$ and $W$ into $F[x]\dash$modules via linear operators $T$ on $V$ and $S$ on $W$ by defining $X \cdot v = T (v)$ for all $v \in V$ and $X \cdot w = S(w)$ for all w $\in$ W . 

Denote the resulting $F[x]\dash$modules by $V_T$ and $W_S$ respectively.

a.
Show that an $F[x]\dash$module homomorphism from $V_T$ to $W_S$ consists of an $F\dash$linear transformation $R : V \to W$ such that $RT = SR$.

b.
Show that $VT \cong WS$ as $F[x]\dash$modules $\iff$ there is an $F\dash$linear isomorphism $P : V \to W$ such that $T = P\inv SP$.

c.
Recall that a module $M$ is *simple* if $M \neq 0$ and any proper submodule of $M$ must be zero. Suppose that $V$ has dimension 2. Give an example of $F$, $T$ with $V_T$ simple.

d.
Assume $F$ is algebraically closed. Prove that if $V$ has dimension 2, then any $V_T$ is not simple.

## Spring 2015 #3 $\work$
Let $F$ be a field and $V$ a finite dimensional $F\dash$vector space, and let $A, B: V\to V$ be commuting $F\dash$linear maps.
Suppose there is a basis $\mcb_1$ with respect to which $A$ is diagonalizable and a basis $\mcb_2$ with respect to which $B$ is diagonalizable.

Prove that there is a basis $\mcb_3$ with respect to which $A$ and $B$ are both diagonalizable.

## Fall 2016 #2 $\work$
Let $A, B$ be two $n\times n$ matrices with the property that $AB = BA$.
Suppose that $A$ and $B$ are diagonalizable.
Prove that $A$ and $B$ are *simultaneously* diagonalizable.

## Spring 2019 #1 $\done$

Let $A$ be a square matrix over the complex numbers.
Suppose that $A$ is nonsingular
and that $A^{2019}$ is diagonalizable over $\CC$.

Show that $A$ is also diagonalizable over $\CC$.

:::{.concept}
\envlist

- $A$ is diagonalizable iff $\min_A(x)$ is separable.
  - See [further discussion here](https://math.stackexchange.com/questions/3027664/if-a-is-invertible-and-an-is-diagonalizable-then-a-is-diagonalizable).

:::

:::{.solution}
\envlist

:::{.claim}
If $A \in \Gl(m, \FF)$ is invertible and $A^n/\FF$ is diagonalizable, then $A/\FF$ is diagonalizable.
:::


:::{.proof title="of claim"}
- Let $A \in \Gl(m, \FF)$. 
- Since $A^n$ is diagonalizable, $\min_{A^n}(x) \in \FF[x]$ is separable and thus factors as a product of $m$ **distinct** linear factors:
\[
\min_{A^n}(x) = \prod_{i=1}^m (x-\lambda_i), \quad \min_{A^n}(A^n) = 0
\]

  where $\theset{\lambda_i}_{i=1}^m \subset \FF$ are the **distinct** eigenvalues of $A^n$.

- Moreover $A\in \GL(m,\FF) \implies A^n \in \GL(m,\FF)$: $A$ is invertible $\iff \det(A) = d \in \FF\units$, and so $\det(A^n) = \det(A)^n = d^n \in \FF\units$ using the fact that the determinant is a ring morphism $\det: \mat (m\times m) \to\FF$ and $\FF\units$ is closed under multiplication.

- So $A^n$ is invertible, and thus has trivial kernel, and thus zero is not an eigenvalue, so $\lambda_i \neq 0$ for any $i$.

- Since the $\lambda_i$ are distinct and nonzero, this implies $x^k$ is not a factor of $\mu_{A^n}(x)$ for any $k\geq 0$. 
Thus the $m$ terms in the product correspond to precisely $m$ **distinct linear** factors.

- We can now construct a polynomial that annihilates $A$, namely
$$
q_A(x) \definedas \min_{A^n}(x^n) = \prod_{i=1}^m (x^n-\lambda_i) \in \FF[x],
$$

  where we can note that $q_A(A) = \min_{A^n}(A^n) = 0$, and so $\min_A(x) \divides q_A(x)$ by minimality.


:::{.claim}
$q_A(x)$ has exactly $nm$ distinct linear factors in $\FFbar[x]$
:::


- This reduces to showing that no pair $x^n-\lambda_i, x^n-\lambda_j$ share a root.
and that $x^n-\lambda_i$ does not have multiple roots.

- For the first claim, we can factor
  \[
  x^n - \lambda_i = \prod_{k=1}^n (x - \lambda_i^{1\over n} e^{2\pi i k \over n}) \definedas \prod_{k=1}^n (x-\lambda^{1\over n} \zeta_n^k)
  ,\]
  where we now use the fact that $i\neq j \implies \lambda_i^{1\over n} \neq \lambda_j^{1\over n}$. 
  Thus no term in the above product appears as a factor in $x^n - \lambda_j$ for $j\neq i$.

- For the second claim, we can check that $\dd{}{x}\qty{x^n - \lambda_i} = nx^{n-1}\neq 0\in \FF$, and $\gcd(x^n-\lambda_i, nx^{n-1}) = 1$ since the latter term has only the roots $x=0$ with multiplicity $n-1$, whereas $\lambda_i\neq 0 \implies$ zero is not a root of $x^n-\lambda_i$.

But now since $q_A(x)$ has exactly distinct linear factors in $\bar \FF[x]$ and $\min_A(x) \divides q_A(x)$, $\min_A(x) \in \FF[x]$ can only have distinct linear factors, and $A$ is thus diagonalizable over $\FF$.

:::



:::

# Linear Algebra: Misc

## $\star$ Spring 2012 #6 $\work$
Let $k$ be a field and let the group $G = \GL(m, k) \cross \GL(n, k)$ acts on the set of $m\times n$ matrices $M_{m, n}(k)$ as follows:
\[
(A, B) \cdot X = AXB\inv
\]
where $(A, B) \in G$ and $X\in M_{m, n}(k)$.

a.
State what it means for a group to act on a set.
Prove that the above definition yields a group action.

b.
Exhibit with justification a subset $S$ of $M_{m, n}(k)$ which contains precisely one element of each orbit under this action.

## $\star$ Spring 2014 #7 $\work$
Let $G = \GL(3, \QQ[x])$ be the group of invertible $3\times 3$ matrices over $\QQ[x]$.
For each $f\in \QQ[x]$, let $S_f$ be the set of $3\times 3$ matrices $A$ over $\QQ[x]$ such that $\det(A) = c f(x)$ for some nonzero constant $c\in \QQ$.

a.
Show that for $(P, Q) \in G\cross G$ and $A\in S_f$, the formula
\[
(P, Q)\cdot A \definedas PAQ\inv
\]
gives a well defined map $G\cross G \cross S_f \to S_f$ and show that this map gives a group action of $G\cross G$ on $S_f$.

b.
For $f(x) = x^3(x^2+1)^2$, give one representative from each orbit of the group action in (a), and justify your assertion.

## Fall 2012 #7 $\work$
Let $k$ be a field of characteristic zero and $A, B \in M_n(k)$ be two square $n\times n$ matrices over $k$ such that $AB - BA = A$.
Prove that $\det A = 0$.

Moreover, when the characteristic of $k$ is 2, find a counterexample to this statement.

## Fall 2012 #8 $\work$
Prove that any nondegenerate matrix $X\in M_n(\RR)$ can be written as $X = UT$ where $U$ is orthogonal and $T$ is upper triangular.

## Fall 2012 #5 $\work$
Let $U$ be an infinite-dimensional vector space over a field $k$, $f: U\to U$ a linear map, and $\theset{u_1, \cdots, u_m} \subset U$ vectors such that $U$ is generated by $\theset{u_1, \cdots, u_m, f^d(u_1), \cdots, f^d(u_m)}$ for some $d\in \NN$.

Prove that $U$ can be written as a direct sum $U \cong V\oplus W$ such that 

1. $V$ has a basis consisting of some vector $v_1, \cdots v_n, f^d(v_1), \cdots, f^d(v_n)$ for some $d\in \NN$, and
2. $W$ is finite-dimensional.

Moreover, prove that for any other decomposition $U \cong V' \oplus W'$, one has $W' \cong W$.

## Fall 2015 #7 $\work$

a.
Show that two $3\times 3$ matrices over $\CC$ are similar $\iff$ their characteristic polynomials are equal and their minimal polynomials are equal.

b.
Does the conclusion in (a) hold for $4\times 4$ matrices?
Justify your answer with a proof or counterexample.

## Fall 2014 #4 $\work$
Let $F$ be a field and $T$ an $n\times n$ matrix with entries in $F$.
Let $I$ be the ideal consisting of all polynomials $f\in F[x]$ such that $f(T) =0$.

Show that the following statements are equivalent about a polynomial $g\in I$:

a. $g$ is irreducible.

b. If $k\in F[x]$ is nonzero and of degree strictly less than $g$, then $k[T]$ is an invertible matrix.

## Fall 2015 #8 $\work$
Let $V$ be a vector space over a field $F$ and $V\dual$ its dual.
A *symmetric bilinear form* $(\wait, \wait)$ on $V$ is a map $V\cross V\to F$ satisfying
\[
(av_1 + b v_2, w) = a(v_1, w) + b(v_2, w) \qtext{and} (v_1, v_2) = (v_2, v_1)
\]
for all $a, b\in F$ and $v_1, v_2 \in V$.
The form is *nondegenerate* if the only element $w\in V$ satisfying $(v, w) = 0$ for all $v\in V$ is $w=0$.

Suppose $(\wait, \wait)$ is a nondegenerate symmetric bilinear form on $V$.
If $W$ is a subspace of $V$, define
\[
W^{\perp} \definedas \theset{v\in V \suchthat (v, w) = 0 \text{ for all } w\in W}
.\]

a.
Show that if $X, Y$ are subspaces of $V$ with $Y\subset X$, then $X^{\perp} \subseteq Y^{\perp}$.

b.
Define an injective linear map 
\[
\psi: Y^{\perp}/X^{\perp} \injects (X/Y)\dual
\]
which is an isomorphism if $V$ is finite dimensional.

##  Fall 2018 #4 $\done$ 
Let $V$ be a finite dimensional vector space over a field (the field is not necessarily algebraically closed).

Let $\phi : V \to V$ be a linear transformation. Prove that there exists a decomposition of $V$ as $V = U \oplus W$ , where $U$ and $W$ are $\phi\dash$invariant subspaces of $V$ , $\restrictionof{\phi}{U}$ is nilpotent, and $\restrictionof{\phi}{W}$ is nonsingular.

\todo[inline]{Revisit.}

:::{.solution}
Let $m(x)$ be the minimal polynomial of $\phi$.
If the polynomial $f(x) = x$ doesn't divide $m$, then $f$ does not have zero as an eigenvalue, so $\phi$ is nonsingular and since $0$ is nilpotent, $\phi + 0$ works.

Otherwise, write $\phi(x) = x^m \rho(x)$ where $\gcd(x, \rho(x)) = 1$.

Then
\[
V \cong \frac{k[x]}{m(x)} \cong \frac{k[x]}{(x^m)} \oplus \frac{k[x]}{(\rho)}
\definedas U \oplus W
\]
by the Chinese Remainder theorem.

We can now note that $\restrictionof{\phi}{U}$ is nilpotent because it has characteristic polynomial $x^m$, and $\restrictionof{\phi}{W}$ is nonsingular since $\lambda = 0$ is not an eigenvalue by construction.


:::

## Fall 2018 #5 $\done$
Let $A$ be an $n \times n$ matrix.

a.
Suppose that $v$ is a column vector such that the set $\{v, Av, . . . , A^{n-1} v\}$ is linearly independent. Show that any matrix $B$ that commutes with $A$ is a polynomial in $A$.

b.
Show that there exists a column vector $v$ such that the set $\{v, Av, . . . , A^{n-1} v\}$ is linearly independent $\iff$ the characteristic polynomial of $A$ equals the minimal polynomial of A.

:::{.concept}
\envlist

- Powers of $A$ commute with polynomials in $A$.
- The image of a linear map is determined by the image of a basis
:::

:::{.strategy}
\envlist

- Use Cayley-Hamilton to relate the minimal polynomial to a linear dependence.
- Get a lower bound on the degree of the minimal polynomial.
- Use $A\actson k[x]$ to decompose into cyclic $k[x]\dash$modules, and use special form of denominators in the invariant factors.
- Reduce to monomials.
:::

:::{.solution}
\envlist

:::{.proof title="of a"}
Letting $\vector v$ be fixed, since $\theset{A^j \vector v}$ spans $V$ we have A
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

:::

:::{.proof title="of b, $\implies$"}
$\implies$:

If $\theset{A^j \vector v_k \suchthat 0\leq j \leq n-1}$ is linearly independent, this means that $A$ does satisfy any polynomial of degree $d < n$.

So $\deg m_A(x) = n$, and since $m_A(x)$ divides $\chi_A(x)$ and both are monic degree polynomials of degree $n$, they must be equal.


:::

:::{.proof title="of b, $\impliedby$"}
$\impliedby$:

Let $A\actson k[x]$ by $A \actson p(x) \definedas p(A)$.
This induces an invariant factor decomposition $V =\cong \bigoplus k[x]/(f_i)$.
Since the product of the invariant factors is the characteristic polynomial, the largest invariant factor is the minimal polynomial, and these two are equal, there can only be one invariant factor and thus the invariant factor decomposition is
$$
V\cong \frac{k[x]}{(\chi_A(x))}
$$
as an isomorphism of $k[x]\dash$modules.

So $V$ is a cyclic $k[x]$ module, which means that $V = k[x]\actson \vector v$ for some $\vector v\in V$ such that $\ann(\vector v) = \chi_A(x)$, i.e. there is some element $\vector v\in V$ whose orbit is all of $V$.

But then noting that monomials span $k[x]$ as a $k\dash$module, we can write
\[
V &\cong
k[x] \actson \vector v \\
&\definedas \theset{f(x) \actson \vector v \suchthat f \in k[x]} \\
&= \spanof_k \theset{x^k \actson \vector v \suchthat k \geq 0} \\
&\definedas \spanof_k \theset{A^k\vector v \suchthat k \geq 0}
.\]

Moreover, we can note that if $\ell \geq \deg \chi_A(x)$, then $A^\ell$ is a linear combination of $\theset{A^j \mid 0 \leq j \leq n-1}$, and so
\[
V &\cong \spanof_k \theset{A^\ell\vector v \suchthat \ell \geq 0} \\
&= \spanof_k \theset{A^\ell \vector v \suchthat 1 \leq \ell \leq n-1}
.\]

:::

:::

## Fall 2019 #8 $\work$
Let $\{e_1, \cdots, e_n \}$ be a basis of a real vector space $V$ and let
\[
\Lambda \definedas \theset{ \sum r_i e_i \mid r_i \in \ZZ}
\]

Let $\cdot$ be a non-degenerate ($v \cdot w = 0$ for all $w \in V \iff v = 0$) symmetric bilinear form on $V$ such that the Gram matrix $M = (e_i \cdot e_j )$ has integer entries.

Define the dual of $\Lambda$ to be
\[
\Lambda \dual \definedas \{v \in V \suchthat v \cdot x \in \ZZ \text{ for all } x \in \Lambda
\}
.\]

a.
Show that $\Lambda \subset \Lambda \dual$.

b.
Prove that $\det M \neq 0$ and that the rows of $M\inv$ span $\Lambda\dual$.

c.
Prove that $\det M = |\Lambda\dual /\Lambda|$.

\todo[inline]{Todo, missing part (c).}

:::{.solution}
\envlist

:::{.proof title="of a"}
\envlist

- Let $\vector v \in \Lambda$, so $\vector v = \sum_{i=1}^n r_i \vector e_i$ where $r_i \in \ZZ$ for all $i$.

- Then if $\vector x = \sum_{j=1}^n s_j \vector e_j \in \Lambda$ is arbitrary, we have $s_j \in \ZZ$ for all $j$ and 
\[
\inner{\vector v}{\vector x} 
&= \inner{\sum_{i=1}^n r_i \vector e_i}{\sum_{j=1}^n s_j \vector e_j } \\
&= \sum_{i=1}^n \sum_{j=1}^n r_i s_j \inner{\vector e_i}{\vector e_j }  \in \ZZ
\]
  since this is a sum of products of integers (since $\inner{\vector e_i}{\vector e_j} \in \ZZ$ for each $i, j$ pair by assumption) so $\vector v \in \Lambda\dual$ by definition.

:::

:::{.proof title="of b"}


:::{.claim}
The determinant is nonzero.
:::

- Suppose $\det M = 0$. Then $\ker M \neq \vector 0$, so let $\vector v \in \ker M$ be given by $\vector v = \sum_{i=1}^n v_i \vector e_i \neq \vector 0$. 

- Note that 
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

- We can now note that $\inner{\vector e_k}{\vector v} = \sum_{j=1}^n v_j \inner{\vector e_k}{\vector e_j} = 0$ for every $k$ by the above observation, which forces $\vector v = 0$ by non-degeneracy of $\inner{\wait}{\wait}$, a contradiction. 
:::

:::{.proof title="of c"}
\envlist

??? 

\todo[inline]{Missing work!}

:::

:::

:::{.solution title="Alternative"}
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

Let $A = [\vector e_1^t, \cdots, \vector e_n^t]$ be the matrix with $\vector e_i$ in the $i$th column.


:::{.claim}
The rows of $A\inv$ span $\Lambda\dual$.
Equivalently, the columns of $A^{-t}$ span $\Lambda\dual$.
:::

- Let $B = A^{-t}$ and let $\vector b_i$ denote the columns of $B$, so $\im B = \spanof{\theset{\vector b_i}}$.

- Since $A \in \GL(n, \ZZ)$, $A\inv, A^t, A^{-t} \in \GL(n, \ZZ)$ as well.
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

:::

## Spring 2013 #6 $\done$
Let $V$ be a finite dimensional vector space over a field $F$ and let $T: V\to V$ be a linear operator with characteristic polynomial $f(x) \in F[x]$.

a.
Show that $f(x)$ is irreducible in $F[x] \iff$ there are no proper nonzero subspaces $W< V$ with $T(W) \subseteq W$.

b.
If $f(x)$ is irreducible in $F[x]$ and the characteristic of $F$ is 0, show that $T$ is diagonalizable when we extend the field to its algebraic closure.

\todo[inline]{Is there a proof without matrices? What if $V$ is infinite dimensional?}
\todo[inline]{How to extend basis?}

:::{.concept}
\envlist

- Every $\vector v\in V$ is $T\dash$cyclic $\iff \chi_T(x)/\kk$ is irreducible.
  - $\implies$: Same as argument below.
  - $\impliedby$: Suppose $f$ is irreducible, then $f$ is equal to the minimal polynomial of $T$.

- Characterization of diagonalizability: $T$ is diagonalizable over $F \iff \min_{T, F}$ is squarefree in $\bar{F}[x]$?

:::

:::{.solution}
\envlist

Let $f$ be the characteristic polynomial of $T$.

:::{.proof title="of a, $\implies$. Matrix-dependent"}
$\implies$:

- By contrapositive, suppose there is a proper nonzero invariant subspace $W<V$ with $T(W) \subseteq W$, we will show the characteristic polynomial $f \definedas \chi_{V, T}(x)$ is reducible.
- Since $T(W)\subseteq W$, the restriction $g\definedas \chi_{V, T}(x) \mid_W: W\to W$ is a linear operator on $W$.


:::{.claim}
$g$ divides $f$ in $\FF[x]$ and $\deg(g) < \deg(f)$.
:::

- Choose an ordered basis for $W$, say $\mcb_W \definedas \theset{\vector w_1, \cdots, \vector w_k}$ where $k=\dim_F(W)$
- Claim: this can be extended to a basis of $V$, say $\mcb_V \definedas \theset{\vector w_1, \cdots, \vector w_k, \vector v_1, \cdots, \vector v_j}$ where $k+j = \dim_F(V)$.
  - Note that since $W<V$ is proper, $j\geq 1$.
- Restrict $T$ to $W$ to get $T_W$, then let $B = [T_W]_{\mcb_W}$ be the matrix representation of $T_W$ with respect to $\mcb_W$.
- Now consider the matrix representation $[T]_{\mcb_V}$, in block form this is given by
\[
[T]_{\mcb_V} = 
\begin{bmatrix}
B & C \\
0 & D
\end{bmatrix}
\]
  where we've used that $W<V$ is proper to get the existence of $C, D$ (there is at least one additional row/column since $j\geq 1$ in the extended basis.)
\todo[inline]{Why?}

- Now expand along the first column block to obtain
\[
\chi_{T, V}(x) \definedas \det([T]_{\mcb_V} - xI) = \det(B - xI)\cdot \det(D - xI) \definedas \chi_{T, W}(x) \cdot \det(D-xI)
.\]

- Claim: $\det(D - xI) \in xF[x]$ is nontrivial

- The claim follows because this forces $\deg(\det(D-xI)) \geq 1$ and so $\chi_{T, W}(x)$ is a proper divisor of $\chi_{T, V}(x)$.

- Thus $f$ is reducible.

:::

:::{.proof title="of a, $\impliedby$"}
$\impliedby$

- Suppose $f$ is reducible, then we will produce a proper $T\dash$invariant subspace.
- Claim: if $f$ is reducible, there exists a nonzero, noncyclic vector $\vector v$.
- Then $\spanof_k\theset{T^j\vector v}_{j=1}^d$ is a $T\dash$invariant subspace that is nonzero, and not the entire space since $\vector v$ is not cyclic.

:::

:::{.proof title="of b"}
\envlist

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

:::

:::


## Fall 2020 #8 $\work$

Let $A\in \Mat(n\times n, \CC)$ such that the group generated by $A$ under multiplication is finite.
Show that
\[
\Tr(A\inv) =\conj{\Tr(A) }
,\]
where $\conj{(\wait)}$ denotes taking the complex conjugate and $\Tr(\wait)$ is the trace.


