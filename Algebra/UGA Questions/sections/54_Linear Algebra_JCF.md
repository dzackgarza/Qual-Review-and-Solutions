# Linear Algebra: Canonical Forms

## Spring 2020 #7

Let
\[
A=\left[\begin{array}{ccc}
2 & 0 & 0 \\
4 & 6 & 1 \\
-16 & -16 & -2
\end{array}\right] \in M_{3}(\mathrm{C})
.\]

a. Find the Jordan canonical form $J$ of $A$.

b. Find an invertible matrix $P$ such that $P\inv A P = J$. 
  You should not need to compute $P\inv$.

c. Write down the minimal polynomial of $A$.

## Spring 2020 #8

Let $T:V\to V$ be a linear transformation where $V$ is a finite-dimensional vector space over $\CC$.
Prove the Cayley-Hamilton theorem: if $p(x)$ is the characteristic polynomial of $T$, then $p(T) = 0$.
You may use canonical forms.

## Spring 2012 #8
Let $V$ be a finite-dimensional vector space over a field $k$ and $T:V\to V$ a linear transformation.

a. Provide a definition for the *minimal polynomial* in $k[x]$ for $T$.

b. Define the *characteristic polynomial* for $T$.

c. Prove the Cayley-Hamilton theorem: the linear transformation $T$ satisfies its characteristic polynomial.

## Spring 2019 #7

Let $p$ be a prime number.
Let $A$ be a $p \times p$ matrix over a field $F$ with 1 in all
entries except 0 on the main diagonal.

Determine the Jordan canonical form (JCF) of $A$

(a) When $F = \QQ$,

(b) When $F = \FF_p$.

> Hint: In both cases, all eigenvalues lie in the ground field. In each case find a
matrix $P$ such that $P\inv AP$ is in JCF.


## Spring 2018 #4

Let

$$
A=\left[\begin{array}{lll}{0} & {1} & {-2} \\ {1} & {1} & {-3} \\ {1} & {2} & {-4}\end{array}\right] \in M_{3}(\mathbb{C})
$$

(a) Find the Jordan canonical form J of A.

(b) Find an invertible matrix $P$ such that $P\inv AP = J$. 

> You should not need to compute $P\inv$.


## Spring 2017 #6

Let $A$ be an $n\times n$ matrix with all entries equal to $0$ except for the $n-1$ entries just above the diagonal being equal to 2.

a. What is the Jordan canonical form of $A$, viewed as a matrix in $M_n(\CC)$?

b. Find a nonzero matrix $P\in M_n(\CC)$ such that $P\inv A P$ is in Jordan canonical form.


## Spring 2016 #1
Let
\[
A=\left(\begin{array}{ccc}
-3 & 3 & -2 \\
-7 & 6 & -3 \\
1 & -1 & 2
\end{array}\right) \in M_{3}(\mathrm{C})
.\]

a. Find the Jordan canonical form $J$ of $A$.

b. Find an invertible matrix $P$ such that $P\inv A P = J$.
  You do not need to compute $P\inv$.


## Spring 2016 #7

Let $D = \QQ[x]$ and let $M$ be a $\QQ[x]\dash$module such that
\[
M \cong \frac{\mathbb{Q}[x]}{(x-1)^{3}} \oplus \frac{\mathbb{Q}[x]}{\left(x^{2}+1\right)^{3}} \oplus \frac{\mathbb{Q}[x]}{(x-1)\left(x^{2}+1\right)^{5}} \oplus \frac{\mathbb{Q}[x]}{(x+2)\left(x^{2}+1\right)^{2}}
.\]

Determine the elementary divisors and invariant factors of $M$.







## Spring 2015 #6

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


## Fall 2014 #5
Let $T$ be a $5\times 5$ complex matrix with characteristic polynomial $\chi(x) = (x-3)^5$ and minimal polynomial $m(x) = (x-3)^2$.
Determine all possible Jordan forms of $T$.

## Spring 2013 #5
Let $T: V\to V$ be a linear map from a 5-dimensional $\CC\dash$vector space to itself and suppose $f(T) = 0$ where $f(x) = x^2 + 2x + 1$.

a. Show that there does not exist any vector $v\in V$ such that $Tv = v$, but there *does* exist a vector $w\in V$ such that $T^2 w= w$.

b. Give all of the possible Jordan canonical forms of $T$.


## $\star$ Spring 2012 #7
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

a. Find the invariant factors of $A$.

b. Express $V$ in terms of a direct sum of indecomposable $\CC[x]\dash$modules.

c. Find the Jordan canonical form of $A$.



