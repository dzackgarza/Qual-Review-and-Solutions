# Modules


### Fall 2019 Final #2 
Consider the $\ZZ\dash$submodule $N$ of $\ZZ^3$ spanned by $f_1 = [-1, 0, 1], f_2 = [2,-3,1], f_3 = [0, 3, 1], f_4 = [3,1,5]$. Find a basis for $N$ and describe $\ZZ^3/N$.

### Spring 2018 #6.

Let
$$
M = \{(w, x, y, z) \in \ZZ^4 \suchthat w + x + y + z \in 2\ZZ\}
,$$

and

$$
N = \{(w, x, y, z) \in \ZZ^4 \suchthat 4\divides (w - x),~ 4\divides (x - y),~ 4\divides ( y - z)\}
.$$

(a) Show that $N$ is a $\ZZ\dash$submodule of $M$ .

(b) Find vectors $u_1 , u_2 , u_3 , u_4 \in \ZZ^4$ and integers $d_1 , d_2 , d_3 , d_4$ such that
$$
\{u_1 , u_2 , u_3 , u_4 \}
$$
is a free basis for $M$, and
$$
\{d_1 u_1,~ d_2 u_2,~ d_3 u_3,~ d_4 u_4 \}
$$
is a free basis for $N$ .

(c) Use the previous part to describe $M/N$ as a direct sum of cyclic $\ZZ\dash$modules.

### Fall 2018 #6.

Let $R$ be a commutative ring, and let $M$ be an $R\dash$module. 
An $R\dash$submodule $N$ of $M$ is maximal if there is no $R\dash$module $P$ with $N \subsetneq P \subsetneq M$.

(a) Show that an $R\dash$submodule $N$ of $M$ is maximal $\iff M /N$ is a simple $R\dash$module: i.e., $M /N$ is nonzero and has no proper, nonzero $R\dash$submodules.

(b) Let $M$ be a $\ZZ\dash$module. Show that a $\ZZ\dash$submodule $N$ of $M$ is maximal $\iff \#M /N$ is a prime number.

(c) Let $M$ be the $\ZZ\dash$module of all roots of unity in $\CC$ under multiplication.
Show that there is no maximal $\ZZ\dash$submodule of $M$.

### Spring 2018 #7.

Let $R$ be a PID and $M$ be an $R\dash$module. Let $p$ be a prime element of $R$. The module $M$ is called *$\generators{p}\dash$primary* if for every $m \in M$ there exists $k > 0$ such that $p^k m = 0$.

(a) Suppose M is $\generators{p}\dash$primary. Show that if $m \in M$ and $t \in R, ~t \not\in \generators{p}$, then there exists $a \in R$ such that
$atm = m$.

(b) A submodule $S$ of $M$ is said to be *pure* if $S \cap r M = rS$ for all $r \in R$. Show that if $M$ is $\generators{p}\dash$primary, then $S$ is pure if and only if $S \cap p^k M = p^k S$ for all $k \geq 0$.


### Fall 2016 #6
Let $R$ be a ring and $f: M\to N$ and $g: N\to M$ be $R\dash$module homomorphisms such that $g\circ f = \id_M$.
Show that $N\cong \im f \oplus \ker g$.


### Spring 2016 #4

Let $R$ be a ring with the following commutative diagram of $R\dash$modules, where each row represents a short exact sequence of $R\dash$modules:

\begin{center}
\begin{tikzcd}
0 \ar[r] & A \ar[d, "\alpha"] \ar[r, "f"] & B \ar[d, "\beta"] \ar[r, "g"] & C \ar[r] \ar[d, "\gamma"] & 0 \\
0 \ar[r] & A' \ar[r, "f'"] & B'\ar[r, "g'"] & C' \ar[r] & 0 
\end{tikzcd}
\end{center}

Prove that if $\alpha$ and $\gamma$ are isomorphisms then $\beta$ is an isomorphism.


### Spring 2015 #8
Let $R$ be a PID and $M$ a finitely generated $R\dash$module.

a. Prove that there are $R\dash$submodules 
  \[
  0 = M_0 \subset M_1 \subset \cdots \subset M_n = M
  \]
  such that for all $0\leq i \leq n-1$, the module $M_{i+1}/M_i$ is cyclic.

b. Is the integer $n$ in part (a) uniquely determined by $M$? 
  Prove your answer.



### Fall 2012 #6
Let $R$ be a ring and $M$ an $R\dash$module.
Recall that $M$ is *Noetherian* iff any strictly increasing chain of submodule $M_1 \subsetneq M_2 \subsetneq \cdots$ is finite.
Call a proper submodule $M' \subsetneq M$ *intersection-decomposable* if it can not be written as the intersection of two proper submodules $M' = M_1\intersect M_2$ with $M_i \subsetneq M$.

Prove that for every Noetherian module $M$, any proper submodule $N\subsetneq M$ can be written as a finite intersection $N = N_1 \intersect \cdots \intersect N_k$ of intersection-indecomposable modules.


### Fall 2019 Final #1 
Let $A$ be an abelian group, and show $A$ is a $\ZZ\dash$module in a unique way.


## Torsion and the Structure Theorem

### $\star$ Fall 2019 #5

Let $R$ be a ring and $M$ an $R\dash$module.

> Recall that the set of torsion elements in M is defined by
$$
\Tor(m) = \{m \in M \suchthat \exists r \in R, ~r \neq 0, ~rm = 0\}
.$$

(a) Prove that if $R$ is an integral domain, then $\Tor(M )$ is a submodule of $M$ .

(b) Give an example where $\Tor(M )$ is not a submodule of $M$.

(c) If $R$ has zero-divisors, prove that every non-zero $R\dash$module has non-zero torsion elements.

### $\star$ Spring 2019 #5.

Let $R$ be an integral domain. Recall that if $M$ is an $R\dash$module, the *rank* of $M$ is
defined to be the maximum number of $R\dash$linearly independent elements of $M$ .

(a) Prove that for any $R\dash$module $M$, the rank of $\tor(M )$ is 0.

(b) Prove that the rank of $M$ is equal to the rank of of $M/\tor(M )$.

(c) Suppose that M is a non-principal ideal of $R$.

    Prove that $M$ is torsion-free of rank 1 but not free.


### $\star$ Spring 2020 #6

Let $R$ be a ring with unity.

a. Give a definition for a free module over $R$.

b. Define what it means for an $R\dash$module to be torsion free.

c. Prove that if $F$ is a free module, then any short exact sequence of $R\dash$modules of the following form splits:
\[
0 \to N \to M \to F \to 0
.\]

d. Let $R$ be a PID. 
  Show that any finitely generated $R\dash$module $M$ can be expressed as a direct sum of a torsion module and a free module.
  You may assume that a finitely generated torsionfree module over a PID is free.

### Spring 2012 #5
Let $M$ be a finitely generated module over a PID $R$.

a. $M_t$ be the set of torsion elements of $M$, and show that $M_t$ is a submodule of $M$.

b. Show that $M/M_t$ is torsion free.

c. Prove that $M \cong M_t \oplus F$ where $F$ is a free module.

### Spring 2017 #5

Let $R$ be an integral domain and let $M$ be a nonzero torsion $R\dash$module.

a. Prove that if $M$ is finitely generated then the annihilator in $R$ of $M$ is nonzero.

b. Give an example of a non-finitely generated torsion $R\dash$module whose annihilator is $(0)$, and justify your answer.

### Fall 2019 Final #3 
Let $R = k[x]$ for $k$ a field and let $M$ be the $R\dash$module given by
  \[
  M=\frac{k[x]}{(x-1)^{3}} \oplus \frac{k[x]}{\left(x^{2}+1\right)^{2}} \oplus \frac{k[x]}{(x-1)\left(x^{2}+1\right)^{4}} \oplus \frac{k[x]}{(x+2)\left(x^{2}+1\right)^{2}}
  .\]
  Describe the elementary divisors and invariant factors of $M$.

### Fall 2019 Final #4 
Let $I = (2, x)$ be an ideal in $R = \ZZ[x]$, and show that $I$ is not a direct sum of nontrivial cyclic $R\dash$modules.

### Fall 2019 Final #5 
Let $R$ be a PID. 

- Classify irreducible $R\dash$modules up to isomorphism.
- Classify indecomposable $R\dash$modules up to isomorphism.

### Fall 2019 Final #6 
Let $V$ be a finite-dimensional $k\dash$vector space and $T:V\to V$ a non-invertible $k\dash$linear map. Show that there exists a $k\dash$linear map $S:V\to V$ with $T\circ S = 0$ but $S\circ T\neq 0$. 

### Fall 2019 Final #7 
Let $A\in M_n(\CC)$ with $A^2 = A$. Show that $A$ is similar to a diagonal matrix, and exhibit an explicit diagonal matrix similar to $A$.

### Fall 2019 Final #8 
Exhibit the rational canonical form for
  - $A\in M_6(\QQ)$ with minimal polynomial $(x-1)(x^2 + 1)^2$.
  - $A\in M_{10}(\QQ)$ with minimal polynomial $(x^2+1)^2(x^3 + 1)$.

### Fall 2019 Final #9 
Exhibit the rational and Jordan canonical forms for the following matrix $A\in M_4(\CC)$:
  \[
  A=\left(\begin{array}{cccc}
  2 & 0 & 0 & 0 \\
  1 & 1 & 0 & 0 \\
  -2 & -2 & 0 & 1 \\
  -2 & 0 & -1 & -2
  \end{array}\right)
  .\]

### Fall 2019 Final #10 
Show that the eigenvalues of a Hermitian matrix $A$ are real and that $A = PDP\inv$ where $P$ is an invertible matrix with orthogonal columns.

