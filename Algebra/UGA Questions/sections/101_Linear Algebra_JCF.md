# Linear Algebra: Canonical Forms

## $\star$ Spring 2012 #8 $\work$
Let $V$ be a finite-dimensional vector space over a field $k$ and $T:V\to V$ a linear transformation.

a.
Provide a definition for the *minimal polynomial* in $k[x]$ for $T$.

b. 
Define the *characteristic polynomial* for $T$.

c. 
Prove the Cayley-Hamilton theorem: the linear transformation $T$ satisfies its characteristic polynomial.

## $\star$ Spring 2020 #8 $\work$
Let $T:V\to V$ be a linear transformation where $V$ is a finite-dimensional vector space over $\CC$.
Prove the Cayley-Hamilton theorem: if $p(x)$ is the characteristic polynomial of $T$, then $p(T) = 0$.
You may use canonical forms.

## $\star$ Spring 2012 #7 $\work$
Consider the following matrix as a linear transformation from $V\definedas \CC^5$ to itself:
\[
A=\left(\begin{array}{ccccc}
-1 & 1 & 0 & 0 & 0 \\
-4 & 3 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 & 1 \\
0 & 0 & 0 & 1 & 0 \\
0 & 0 & 0 & 0 & 2
\end{array}\right)
.\]

a. 
Find the invariant factors of $A$.

b. 
Express $V$ in terms of a direct sum of indecomposable $\CC[x]\dash$modules.

c.
Find the Jordan canonical form of $A$.


## Fall 2019 Final #8 $\work$
Exhibit the rational canonical form for

  - $A\in M_6(\QQ)$ with minimal polynomial $(x-1)(x^2 + 1)^2$.
  - $A\in M_{10}(\QQ)$ with minimal polynomial $(x^2+1)^2(x^3 + 1)$.

## Fall 2019 Final #9 $\work$
Exhibit the rational and Jordan canonical forms for the following matrix $A\in M_4(\CC)$:
  \[
  A=\left(\begin{array}{cccc}
  2 & 0 & 0 & 0 \\
  1 & 1 & 0 & 0 \\
  -2 & -2 & 0 & 1 \\
  -2 & 0 & -1 & -2
  \end{array}\right)
  .\]

## Spring 2016 #7 $\work$
Let $D = \QQ[x]$ and let $M$ be a $\QQ[x]\dash$module such that
\[
M \cong \frac{\mathbb{Q}[x]}{(x-1)^{3}} \oplus \frac{\mathbb{Q}[x]}{\left(x^{2}+1\right)^{3}} \oplus \frac{\mathbb{Q}[x]}{(x-1)\left(x^{2}+1\right)^{5}} \oplus \frac{\mathbb{Q}[x]}{(x+2)\left(x^{2}+1\right)^{2}}
.\]

Determine the elementary divisors and invariant factors of $M$.

## Spring 2020 #7 $\work$
Let
\[
A=\left[\begin{array}{ccc}
2 & 0 & 0 \\
4 & 6 & 1 \\
-16 & -16 & -2
\end{array}\right] \in M_{3}(\mathrm{C})
.\]

a.
Find the Jordan canonical form $J$ of $A$.

b.
Find an invertible matrix $P$ such that $P\inv A P = J$. 
You should not need to compute $P\inv$.

c.
Write down the minimal polynomial of $A$.

## Spring 2019 #7 $\done$ 
Let $p$ be a prime number.
Let $A$ be a $p \times p$ matrix over a field $F$ with 1 in all
entries except 0 on the main diagonal.

Determine the Jordan canonical form (JCF) of $A$

a. 
When $F = \QQ$,

b.
When $F = \FF_p$.

> Hint: In both cases, all eigenvalues lie in the ground field. In each case find a
matrix $P$ such that $P\inv AP$ is in JCF.


:::{.strategy}
\envlist

- Work with matrix of all ones instead.
- Eyeball eigenvectors.
- Coefficients in minimal polynomial: size of largest Jordan block
- Dimension of eigenspace: number of Jordan blocks
:::


:::{.solution}


\envlist
:::{.concept}
\envlist

- Todo
:::


:::{.strategy}
We can always read off the *characteristic* polynomial from the spectrum.
:::


:::{.proof title="of a"}
Let $A$ be the matrix in the question, and $B$ be the matrix containing 1's in every entry.

- Noting that $B = A+I$, we have
  \[
  &B\vector x = \lambda \vector x \\
  &\iff (A+I) \vector x = \lambda \vector x \\
  &\iff A \vector x = (\lambda - 1) \vector x
  ,\]
    so we will find the eigenvalues of $B$ and subtract one from each.

- Note that $B\vector v = \thevector{\sum v_i, \sum v_i, \cdots, \sum v_i}$, i.e. it has the effect of summing all of the entries of $\vector v$ and placing that sum in each component.

- We proceed by finding $p$ eigenvectors and eigenvalues, since the JCF and minimal polynomials will involve eigenvalues and the transformation matrix will involve (generalized) eigenvectors.

:::{.claim title="1"}
Each vector of the form $\vector p_i \definedas \vector e_1 - \vector e_{i+1} = \thevector{1, 0, 0,\cdots, 0 -1, 0, \cdots, 0 }$ where $i\neq j$ is also an eigenvector with eigenvalues $\lambda_0 = 0$, and this gives $p-1$ linearly independent vectors spanning the eigenspace $E_{\lambda_0}$
:::

:::{.claim title="2"}
$\vector v_1 = \thevector{1, 1, \cdots, 1}$ is an eigenvector with eigenvalue $\lambda_1 = p$.
:::

- Using that the eigenvalues of $A$ are $1+\lambda_i$ for $\lambda_i$ the above eigenvalues for $B$,
\[
\spec(B) \definedas \theset{(\lambda_i, m_i)} &=  \theset{(p, 1), (0, p-1)}  \implies \chi_{B}(x) = (x-p)x^{p-1} \\ 
\implies \spec(A) &= \theset{(p-1,1), (-1, p-1) }  \implies \chi_{A}(x) = (x- p+1)(x+1)^{p-1} \\
\]

- The dimensions of eigenspaces are preserved, thus
\[
JCF_\QQ(A)
=  J_{p-1}^{1} \oplus (p-1)J_{-1}^1
=
\left[\begin{array}{r|r|r|r|r|r}
p-1 & 0 & 0 & \cdots & 0 & 0 \\
\hline
0& -1 & 0 & 0 & 0 & 0 \\ \hline
0& 0 & -1 & 0 & 0 & 0 \\ \hline
0& 0 & 0 & \ddots & \ddots & 0 \\ \hline
0& 0 & 0 & \cdots & -1 & 0 \\ \hline
0& 0 & 0 & \cdots & 0 & -1 \\
\end{array}\right]
.\]

- The matrix $P$ such that $A = PJP\inv$ will have columns the bases of the generalized eigenspaces.
- In this case, the generalized eigenspaces are the usual eigenspaces, so
\[
P = [\vector v_1, \vector p_1, \cdots, \vector p_{p-1}] =
\left[\begin{array}{rrrrrr}
1 & 1 & 1 & 1 & 1 & 1  \\
1 & -1 & 0 & 0 & 0 & 0 \\
1 & 0 & -1 & 0 & 0 & 0 \\
1 & 0 & 0 & -1 & 0 & 0 \\
1 & \vdots & \vdots & \vdots & \ddots & \vdots\\
1 & 0 & 0 & 0 & 0 & -1 \\
\end{array}\right]
.\]

:::

:::{.proof title="of claim 1"}
\envlist

- Compute $$B \vector p_i = \thevector{ 1 + 0 + \cdots + 0 + (-1) + 0 + \cdots + 0} = \thevector{0, 0, \cdots, 0}$$
- So every $\vector p_i \in \ker(B)$, so they are eigenvectors with eigenvalue 0.
- Since the first component is fixed and we have $p-1$ choices for where to place a $-1$, this yields $p-1$ possibilities for $\vector p_i$
- These are linearly independent since the $(p-1)\times (p-1)$ matrix $\thevector{ \vector p_1^t, \cdots, \vector p_{p-1}^t}$ satisfies
\[
\det 
\begin{bmatrix}
1 & 1 & 1 & \cdots & 1\\
-1 & 0  & 0 & \cdots & 0\\
0 & -1  & 0 & \cdots & 0\\
0 & 0 & -1 & \cdots & 0\\
\vdots & \vdots  & \vdots & \ddots & \vdots \\
0 & 0  & 0 & \cdots & -1\\
\end{bmatrix}
&= (1) \cdot \det 
\begin{bmatrix}
-1 & 0  & 0 & \cdots & 0\\
0 & -1  & 0 & \cdots & 0\\
0 & 0 & -1 & \cdots & 0\\
\vdots & \vdots  & \vdots & \ddots & \vdots \\
0 & 0  & 0 & \cdots & -1\\
\end{bmatrix}
\\
&= (-1)^{p-2} \neq 0
.\]

where the first equality follows from expanding along the first row and noting this is the first minor, and every other minor contains a row of zeros.

:::

:::{.proof title="of claim 2"}
\envlist

- Compute $$B\vector v = \thevector{\sum_{i=1}^p 1, \sum_{i=1}^p 1, \cdots, \sum_{i=1}^p 1} = \thevector{p, p, \cdots, p} = p \thevector{1, 1, \cdots, 1} = p\vector{v}_1,$$ thus $\lambda_1 = p$
- $\dim E_{\lambda_1} = 1$ since the eigenspaces are orthogonal and $E_{\lambda_0} \oplus E_{\lambda_1} \leq F^p$ is a subspace, so $p > \dim(E_{\lambda_0}) + \dim E_{\lambda_1} = p-1 + \dim E_{\lambda_1}$ and it isn't zero dimensional.

:::

:::{.proof title="of b"}
For $F = \FF_p$, all eigenvalues/vectors still lie in $\FF_p$, but now $-1 = p-1$, making $(x-(p-1))(x+1)^{p-1} = (x+1)(x+1)^{p-1}$, so $\chi_{A, \FF_p}(x) = (x+1)^p$, and the Jordan blocks may merge.

- A computation shows that $(A+I)^2 = pA = 0 \in M_p(\FF_p)$ and $(A+I) \neq 0$, so $\min_{A, \FF_p}(x) = (x+1)^2$.
  - Thus the largest Jordan block corresponding to $\lambda = -1$ is of size 2
- Can check that $\det(A) = \pm 1 \in \FF_p\units$, so the vectors $\vector e_1 - \vector e_i$ are still linearly independent and thus $\dim E_{-1} = p-1$
  - So there are $p-1$ Jordan blocks for $\lambda = 0$.

Summary:
\[
\min_{A, \FF_p}(x) &= (x+1)^2 \\
\chi_{A, \FF_p}(x) &\equiv (x+1)^p \\
\dim E_{-1} &= p-1
.\]

Thus
\[
JCF_{\FF_p}(A)
=  J_{-1}^{2} \oplus (p-2)J_{-1}^1
= \left[\begin{array}{rr|r|r|r|r}
-1 & 1 & 0 & \cdots & 0 & 0 \\
0& -1 & 0 & 0 & 0 & 0 \\
\hline
0& 0 & -1 & 0 & 0 & 0 \\ \hline
0& 0 & 0 & \ddots & \ddots & 0 \\ \hline
0& 0 & 0 & \cdots & -1 & 0 \\ \hline
0& 0 & 0 & \cdots & 0 & -1 \\
\end{array}\right]
.\]

To obtain a basis for $E_{\lambda = 0}$, first note that the matrix $P = [\vector v_1, \vector p_1, \cdots , \vector p_{p-1}]$ from part (a) is singular over $\FF_p$, since
\[
\vector v_1 + \vector p_1 + \vector p_2 + \cdots + \vector p_{p-2}
&= [p-1, 0, 0, \cdots, 0, 1] \\
&= [-1, 0,0,\cdots, 0, 1] \\
&= - \vector p_{p-1}
.\]

We still have a linearly independent set given by the first $p-1$ columns of $P$, so we can extend this to a basis by finding one linearly independent generalized eigenvector.

Solving $(A-I\lambda)\vector x = \vector v_1$ is our only option (the others won't yield solutions).
This amounts to solving $B\vector x = \vector v_1$, which imposes the condition $\sum x_i = 1$, so we can choose $\vector x = [1, 0, \cdots, 0]$.

Thus
\[
P = [\vector v_1, \vector x, \vector p_1, \cdots, \vector p_{p-2}] =
\left[\begin{array}{rrrrrr}
1 & 1 & 1 & 1 & 1 & 1  \\
1 & 0 & -1 & 0 & 0 & 0 \\
1 & 0 & 0 & -1 & 0 & 0 \\
1 & \vdots & \vdots & \vdots & \ddots & \vdots \\
1 & 0 & 0 & 0 & 0 & -1\\
1 & 0 & 0 & 0 & 0 & 0 \\
\end{array}\right]
.\]

:::

:::

## Spring 2018 #4 $\work$
Let
\[
A=\left[\begin{array}{lll}{0} & {1} & {-2} \\ {1} & {1} & {-3} \\ {1} & {2} & {-4}\end{array}\right] \in M_{3}(\mathbb{C})
\]

a. 
Find the Jordan canonical form J of A.

b.
Find an invertible matrix $P$ such that $P\inv AP = J$. 

> You should not need to compute $P\inv$.

## Spring 2017 #6 $\work$
Let $A$ be an $n\times n$ matrix with all entries equal to $0$ except for the $n-1$ entries just above the diagonal being equal to 2.

a.
What is the Jordan canonical form of $A$, viewed as a matrix in $M_n(\CC)$?

b.
Find a nonzero matrix $P\in M_n(\CC)$ such that $P\inv A P$ is in Jordan canonical form.

## Spring 2016 #1 $\work$
Let
\[
A=\left(\begin{array}{ccc}
-3 & 3 & -2 \\
-7 & 6 & -3 \\
1 & -1 & 2
\end{array}\right) \in M_{3}(\mathrm{C})
.\]

a.
Find the Jordan canonical form $J$ of $A$.

b.
Find an invertible matrix $P$ such that $P\inv A P = J$.
You do not need to compute $P\inv$.

## Spring 2015 #6 $\work$
Let $F$ be a field and $n$ a positive integer, and consider
\[
A=\left[\begin{array}{ccc}
1 & \dots & 1 \\
& \ddots & \\
1 & \dots & 1
\end{array}\right] \in M_{n}(F)
.\]

Show that $A$ has a Jordan normal form over $F$ and find it.

> Hint: treat the cases $n\cdot  1 \neq 0$ in $F$ and $n\cdot 1 = 0$ in $F$ separately.

## Fall 2014 #5 $\work$
Let $T$ be a $5\times 5$ complex matrix with characteristic polynomial $\chi(x) = (x-3)^5$ and minimal polynomial $m(x) = (x-3)^2$.
Determine all possible Jordan forms of $T$.

## Spring 2013 #5 $\work$
Let $T: V\to V$ be a linear map from a 5-dimensional $\CC\dash$vector space to itself and suppose $f(T) = 0$ where $f(x) = x^2 + 2x + 1$.

a.
Show that there does not exist any vector $v\in V$ such that $Tv = v$, but there *does* exist a vector $w\in V$ such that $T^2 w= w$.

b.
Give all of the possible Jordan canonical forms of $T$.

## Spring 2021 #1 $\work$

Let m
\[
A \da 
\begin{bmatrix}
r & 1 & -1 \\
-6 & -1 & 2 \\
2 & 1 & 1
\end{bmatrix}
\in \Mat(3\times 3, \CC)
.\]

a. Find the Jordan canonical form $J$ of $A$.

b. Find an invertible matrix $P$ such that $J = P \inv A P$.

  *(You should not need to compute $P\inv$)*

c. Write down the minimal polynomial of $A$.


## Fall 2020 #5 $\work$

Consider the following matrix:
\[
B \da 
\begin{bmatrix}
1 & 3 & 3
\\
2 & 2 & 3
\\
-1 & -2 & -2
\end{bmatrix}
.\]

a. Find the minimal polynomial of $B$.

b. Find a $3\times 3$ matrix $J$ in Jordan canonical form such that $B = JPJ\inv$ where $P$ is an invertible matrix.



