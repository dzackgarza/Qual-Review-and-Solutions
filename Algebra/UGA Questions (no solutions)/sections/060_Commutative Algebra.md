# Commutative Algebra

## UFDs, PIDs, etc

### Spring 2013 #2 $\done$

a.
Define a *Euclidean domain*.

b.
Define a *unique factorization domain*.

c.
Is a Euclidean domain an UFD? 
Give either a proof or a counterexample with justification.

d.
Is a UFD a Euclidean domain?
Give either a proof or a counterexample with justification.


:::{.solution}
\envlist

- $R$ is Euclidean iff it admits a Euclidean algorithm: there is a degree function $f: R\to \ZZ_{\geq 0}$ such that for all $a,b\in R$, there exist $q, r\in R$ such that $a = bq + r$ where $f(r) <f(b)$ or $r=0$.

- $R$ is a UFD iff every $r\in R$ can be written as $r = u \prod_{i=1}^n p_i$ with $n\geq 0$, $u\in R\units$, and $p_i$ irreducible.
  This is unique up to associates of the $p_i$ and reordering.

- Euclidean implies UFD:
  - Euclidean implies PID:
    - If $I \in \Id(R)$ one can use the degree function to find any $b \in I$ where $f(b)$ is minimal.
    - Then $I = \gens{b}$, since if $a\in I$ one can write $a = bq + r$ and use that $a-bq \in I \implies r\in I$.
    - But by minimality, we can't have $f(r)<f(b)$, so $r=0$ and $a \divides b$, so $b\in \gens{a}$.
    
  - PID implies UFD:
    - Use that irreducible implies prime in a PID, so every $x\in R$ has some factorization into finitely many primes.
    - Supposing $x = u_p \prod_{i=1}^m p_i = u_q \prod_{i=1}^n q_i$, use that $p_1$ divides the LHS and so $p_1$ divides the RHS.
    WLOG, $p_1\divides q_1$, so $q_1 = u_1 p_1$ for $u\in R\units$, so $x = u_q u_1 p_1 \prod_{i=2}^m q_i$ by rewriting a term on the RHS.
    - Note that this makes $p_1, q_1$ associates.
    - Continuing up to $m$, we get
  \[
  x 
  &= u_p \prod_{i=1}^m p_i \\
  &= 
  u_q \prod_{i=1}^m u_i p_i \prod_{k=m+1}^n q_i \\
  \implies 
  u_p 
  &= u_q \prod_{i=1}^m u_i \prod_{k=m+1}^n q_i \\
  \tilde u 
  &= \prod_{k=m+1}^n q_i
  ,\]
    where we've moved all units to the LHS.
    This makes $p_i, q_i$ associates for $i\leq m$.
    - But primes aren't units and the product of nontrivial primes can't be a unit, so the right-hand side product must be empty.
    - So $m=n$ and all $p_i, q_i$ are associate, QED.

- UFD does not imply Euclidean:
  - It suffices to find a UFD that is not a PID.
  - Take $R \da \CC[x, y]$, which is a UFD by the usual factorization of polynomials.
  It is not a PID, since $\gens{2, x}$ is not principal.


:::



### Fall 2017 #6 $\done$
For a ring $R$, let $U(R)$ denote the multiplicative group of units in $R$. Recall that in an integral domain $R$, $r \in R$ is called *irreducible* if $r$ is not a unit in R, and the only divisors of $r$ have the form $ru$ with $u$ a unit in $R$. 

We call a non-zero, non-unit $r \in R$ *prime* in $R$ if $r \divides ab \implies r \divides a$ or $r \divides b$. 
Consider the ring $R = \{a + b \sqrt{-5}\suchthat a, b \in Z\}$.

a.
Prove $R$ is an integral domain.

b.
Show $U(R) = \{\pm1\}$.

c.
Show $3, 2 + \sqrt{-5}$, and $2 - \sqrt{-5}$ are irreducible in $R$.

d.
Show 3 is not prime in $R$.

e.
Conclude $R$ is not a PID.


:::{.concept}
\envlist

- Integral domain: $ab=0 \implies a\neq 0 \text{ or } b\neq 0$.
- Prime: $p \divides ab \implies p\divides a$ or $b$.
- Reducible: $a = xy$ where $x, y$ are proper divisors.
- Irreducible implies prime in a UFD.
:::

:::{.solution}
\envlist

- $R$ is an integral domain:
  - Let $\alpha = a + b\sqrt{-5}$ and $\beta = c + d \sqrt{-5}$ and set $\bar \alpha, \bar \beta$ be their conjugates.
  - Then
  \[
  0 = \alpha \beta = \alpha\bar\alpha \beta\bar\beta = (a^2-5b^2)(c^2-5d^2) \in \ZZ
  ,\]
  so one factor is zero.
  - If $a^2 = 5b^2$ then $a = \sqrt{5} b \not\in \ZZ$ unless $a=b=0$.
    Otherwise, the same argument forces $c=d=0$.

- The units are $\pm 1$:
  - Use that $u\in R\units \implies N(u) = \pm 1$, and $N(\alpha) = \alpha \bar\alpha = (a+b\sqrt{-5})(a-b\sqrt{-5}) = a^2 + 5b^2 = 1$
    forces $b=0$ and $a=\pm 1$.

- Irreducible elements:
  - $2, 3$ are irreducible because if (say) $3=xy$ then $N(x)N(y) = N(3) = 9$, and if neither $x,y$ are units then $N(x) = N(y) = 3$.
    But $N(a + b\sqrt{-5}) = a^2 + 5b^2$ and $a^2 + 5b^2 = 3$ has no solutions.
    The same argument works for $2$.
  - $2\pm \sqrt{-5}$ are irreducible because $N(2 + \sqrt{-5}) = 2^2 + 5(1) = 9$, and in fact $N(2 - \sqrt{-5}) = 2^2 + 5(-1)^2 = 9$.
    By the same argument as above, this forces irreducibility.

- $3$ is not prime: 
  - We can write $6 = (3)(2) = (1 + \sqrt{-5})(1 - \sqrt{-5})$, so if we assume $3$ is prime we get $3\divides (1 \pm \sqrt{-5})$.
  - But writing $(1\pm \sqrt{-5}) = 3r$ for some $r\in R$ yields 
  \[
  (1 \pm \sqrt{-5}) = 3(a + b\sqrt{-5}) \implies 3a=1, 3b = \pm 1
  .\]
  These have no solutions $a, b\in \ZZ$. $\contradiction$

- $R$ is not a PID:
  - Use that irreducibles are prime in a UFD, which is not true here. 

:::

### Spring 2017 #4 $\done$

a.
Let $R$ be an integral domain with quotient field $F$.
Suppose that $p(x), a(x), b(x)$ are monic polynomials in $F[x]$ with $p(x) = a(x) b(x)$ and with $p(x) \in R[x]$, $a(x)$ not in $R[x]$, and both $a(x), b(x)$ not constant.

  Prove that $R$ is not a UFD.

  > (You may assume Gauss' lemma)

b.
Prove that $\ZZ[2\sqrt{2}]$ is not a UFD.

  > Hint: let $p(x) = x^2-2$.

:::{.concept}
\envlist

- Gauss' lemma: for $R$ a UFD with fraction field $F$, if $f$ is reducible in $F[x]$ with $f=pq$ then there are $r,s\in R$ such that $f = (rp)(sq)$ reduces in $R[x]$.
- Corollary: $R$ is a UFD iff $R[x]$ is a UFD.
:::

:::{.solution}

:::{.proof title="of 1"}
\envlist

- The important assumption is $a(x)\not\in R[x]$, we'll assume $R$ is a UFD and try to contradict this.
- Write $f(x) = a(x)b(x)\in F[x]$, then if $R$ is a UFD we have $r,s\in F$ such that $f(x) = ra(x) sb(x) \in R[x]$.
- Since $a(x), b(x)$ are monic and $f=ab$, $f$ is monic, and by the factorization in $R[x]$ we have $rs=1$.
  So $r,s\in R\units$.
- Then using that $ra(x)\in R[x]$, we have $r\inv ra(x) = a(x)\in R[x]$. $\contradiction$

:::


:::{.proof title="of b"}
\envlist

- Set $R = \ZZ[2\sqrt 2], F = \QQ[2\sqrt 2]$.
- Let $p(x) \da x^2-2 \in R[x]$ which splits as $p(x) = (x+ \sqrt{2} )(x - \sqrt{2} ) \da a(x) b(x) \in F[x]$.
- Note neither $a(x), b(x)$ are in $R[x]$.
  - Explicitly, every monic linear $p\in R[x]$ is of the form $x + 2t\sqrt{2}$ with $t\in \ZZ$, and $\pm \sqrt{2} \neq 2t\sqrt{2}$ for any $t$.
- So we have $p(x) \in R[x]$ splitting as $p=ab$ in $F[x]$ with $a\not \in R[x]$, so part (a) applies.

:::

:::

## Ideals (Prime, Maximal, Proper, Principal, etc)

### Fall 2013 #3 $\work$

a.
Define *prime ideal*, give an example of a nontrivial ideal in the ring $\ZZ$ that is not prime, and prove that it is not prime.

b.
Define *maximal ideal*, give an example of a nontrivial maximal ideal in $\ZZ$ and prove that it is maximal.



:::{.solution}


:::{.proof title="of 1"}
\envlist

- $\mfp$ is **prime** iff $xy\in \mfp \implies x\in \mfp$ or $y\in \mfp$.
- An ideal $I\normal \ZZ$ that is not prime: $8\ZZ$

:::

:::



### Fall 2014 #8 $\work$
Let $R$ be a nonzero commutative ring without unit such that $R$ does not contain a proper maximal ideal.
Prove that for all $x\in R$, the ideal $xR$ is proper.

> You may assume the axiom of choice.

### Fall 2014 #7 $\done$
Give a careful proof that $\CC[x, y]$ is not a PID.

:::{.concept}
\envlist

- If $R[x]$ is a PID, then $R$ is a field (not explicitly used).
- In $P \da R[x_1, \cdots, x_n]$, there are degree functions $\deg_{x_n}: P\to \ZZ_{\geq 0}$.
:::

:::{.solution}
\envlist

- The claim is that $I \da \gens{x, y}$ is not principal.
- Toward a contradiction, if so, then $\gens{x, y} = \gens{f}$.
- So write $x = fg$ for some $g\in \CC[x, y]$, then 
  - $\deg_x(x) = 1$, so $\deg_x(fg) = 1$ which forces $\deg_x(f) \leq 1$.
  - $\deg_y(y) = 1$, so $\deg_y(fg) = 1$ which forces $\deg_y(f) \leq 1$.
  - So $f(x, y) = ax + by + c$ for some $a,b,c\in \CC$.
  - $\deg_x(y) = 0$ and thus $\deg_x(fg) = 0$, forcing $a=0$
  - $\deg_y(x) = 0$ and thus $\deg_y(fg) = 0$, forcing $b=0$
  - So $f(x, y) = c \in \CC$.
- But $\CC[x]$ is a field, so $c$ is a unit in $\CC$ and thus $\CC[x, y]$, so $\gens{f} = \gens{c} = \CC[x, y]$.
- This is a contradiction, since $1\not\in \gens{x, y}$:
  - Every element in $\alpha(x, y) \in\gens{x, y}$ is of the form $\alpha(x, y) = xp(x, y) + yq(x, y)$.
  - But $\deg_x(\alpha) \geq 1, \deg_y(\alpha)\geq 1$, while $\deg_x(1) = \deg_y(1) = 0$.
  - So $\gens{x, y} \neq \CC[x, y]$.
- Alternatively, $\gens{x, y}$ is proper since $\CC[x, y] / \gens{x, y} \cong \CC \neq \CC[x, y]$.
:::



### Spring 2019 #6 $\done$
Let $R$ be a commutative ring with 1.

> Recall that $x \in R$ is nilpotent iff $xn = 0$ for
some positive integer $n$.

a.
Show that every proper ideal of $R$ is contained within a maximal ideal.

b.
Let $J(R)$ denote the intersection of all maximal ideals of $R$.
Show that $x \in J(R) \iff 1 + rx$ is a unit for all $r \in R$.

c.
Suppose now that $R$ is finite. Show that in this case $J(R)$ consists precisely
of the nilpotent elements in R.

:::{.concept}
\envlist

- Definitions:
\[
N(R) &\da \theset{x\in R \suchthat x^n = 0 \text{ for some } n} \\
J(R) &\da \intersect _{\mfm \in \mspec} \mfm
.\]

- Zorn's lemma: if $P$ is a poset in which every chain has an upper bound, $P$ contains a maximal element.


:::

:::{.solution}
\envlist

:::{.proof title="of a"}
Define the set of proper ideals
$$
S = \theset{J \suchthat I   \subseteq J < R}
,$$

which is a poset under set inclusion.

Given a chain $J_1 \subseteq \cdots$, there is an upper bound $J \definedas \union J_i$, so Zorn's lemma applies.


:::

:::{.proof title="of b, $\implies$"}
$\implies$:

- We will show that $x\in J(R) \implies 1+x \in R\units$, from which the result follows by letting $x=rx$.

- Let $x\in J(R)$, so it is in every maximal ideal, and suppose toward a contradiction that $1+x$ is **not** a unit.

- Then consider $I = \generators{1+x} \normal R$. 
Since $1+x$ is not a unit, we can't write $s(1+x) = 1$ for any $s\in R$, and so $1 \not\in I$ and $I\neq R$

- So $I < R$ is proper and thus contained in some maximal proper ideal $\mathfrak{m} < R$ by part (1), and so we have $1+x \in \mathfrak{m}$.
Since $x\in J(R)$, $x\in \mathfrak{m}$ as well.

- But then $(1+x) - x = 1 \in \mathfrak{m}$ which forces $\mathfrak{m} = R$.

:::

:::{.proof title="of b, $\impliedby$"}
$\impliedby$

- Fix $x\in R$, and suppose $1+rx$ is a unit for all $r\in R$.

 
- Suppose towards a contradiction that there is a maximal ideal $\mathfrak{m}$ such that $x\not \in \mathfrak{m}$ and thus $x\not\in J(R)$.

- Consider 
\[
M' \definedas \theset{rx + m \suchthat r\in R,~ m\in M}
.\]

- Since $\mathfrak{m}$ was maximal, $\mathfrak{m} \subsetneq M'$ and so $M' = R$.

- So every element in $R$ can be written as $rx + m$ for some $r\in R, m\in M$.
But $1\in R$, so we have 
\[
1 = rx + m
.\] 

- So let $s = -r$ and write $1 = sx - m$, and so $m = 1 + sx$.

- Since $s\in R$ by assumption $1+sx$ is a unit and thus $m \in \mathfrak{m}$ is a unit, a contradiction.

- So $x\in \mathfrak{m}$ for every $\mathfrak{m}$ and thus $x\in J(R)$.

:::

:::{.proof title="of c: $J(R) = \mathfrak N(R)$"}
$\mathfrak N(R) \subseteq J(R)$:

- Use the fact $x\in \mathfrak N(R) \implies x^n = 0 \implies 1 + rx$ is a unit $\iff x\in J(R)$ by (b):
$$
\sum_{k=1}^{n-1} (-x)^k = \frac{1 - (-x)^n}{1- (-x)} = (1+x)\inv
.$$

$J(R) \subseteq \mathfrak N(R)$:

- Let $x \in J(R) \setminus \mathfrak N(R)$.

- Since $R$ is finite, $x^m = x$ for some $m > 0$.

- Without loss of generality, we can suppose $x^2 = x$ by replacing $x^m$ with $x^{2m}$.

- If $1-x$ is not a unit, then $\generators{1-x}$ is a nontrivial proper ideal, which by (a) is contained in some maximal ideal $\mm$. 
But then $x\in \mm$ and $1-x \in \mm \implies x + (1-x) = 1 \in \mm$, a contradiction.

- So $1-x$ is a unit, so let $u = (1-x)\inv$.

- Then
\[
(1-x)x &= x - x^2 = x - x = 0 \\
&\implies u (1-x)x = x = 0 \\
&\implies x=0
.\]

:::

:::

### Spring 2018 #8 $\done$
Let $R = C[0, 1]$ be the ring of continuous real-valued functions on the interval $[0, 1]$. Let I be an ideal of $R$.

a.
Show that if $f \in I, a \in [0, 1]$ are such that $f (a) \neq 0$, then there exists $g \in I$ such that $g(x) \geq 0$ for all $x \in [0, 1]$, and $g(x) > 0$ for all $x$ in some open neighborhood of $a$.

b.
If $I \neq R$, show that the set $Z(I) = \{x \in [0, 1] \suchthat f(x) = 0 \text{ for all } f \in I\}$ is nonempty.

c.
Show that if $I$ is maximal, then there exists $x_0 \in [0, 1]$ such that $I = \{ f \in R \suchthat f (x_0 ) = 0\}$.

:::{.remark}
Cool problem, but pretty specific topological tricks needed.
:::

:::{.solution}
\envlist

:::{.proof title="of a"}
\envlist

- Suppose $c\da f(a)\neq 0$, noting that $c$ may not be positive.
- By continuity, pick $\eps$ small enough so that $\abs{x-a}<\eps \implies \abs{f(x) - f(a)} < c/2$.
  Since we're on the interval, we have $f(x) \in (f(a) - c/2, f(a) + c/2) = (c/2, 3c/2)$ which is a ball of radius $c/2$ about $c$, which thus doesn't intersect $0$.
- So $f(x) \neq 0$ on this ball, and $g \da f^2 > 0$ on it.
  Note that ideals are closed under products, so $g\in I$
- Moreover $f^2(x) \geq 0$ since squares are non-negative, so $g\geq 0$ on $[0, 1]$.
:::

:::{.proof title="of b"}
\envlist

- By contrapositive, suppose $V(I)= \emptyset$, we'll show $I$ contains a unit and thus $I=R$.
- For each fixed $x\in [0, 1]$, since $V(I)$ is empty there is some $f_x$ such that $f_x(x) \neq 0$.
- By (a), there is some $g_x$ with $g_x(x) > 0$ on a neighborhood $U_x\ni x$ and $g_x \geq 0$ everywhere.
- Ranging over all $x$ yields a collection $\ts{(g_x, U_x) \st x\in [0, 1]}$ where $\ts{U_x}\covers [0, 1]$.
- By compactness there is a finite subcover, yielding a finite collection $\ts{(g_k, U_k)}_{k=1}^n$ for some $n$.
- Define the candidate unit as 
\[
G(x) \da {1\over \sum_{k=1}^n g_k(x)}
.\]
- This is well-defined: fix an $x$, then the denominator is zero at $x$ iff $g_k(x) = 0$ for all $k$.
  But since the $U_k$ form an open cover, $x\in U_\ell$ for some $\ell$, and $g_\ell > 0$ on $U_\ell$.
- Since ideals are closed under sums, $H\da {1\over G} \da \sum g_k \in I$.
  But $H$ is clearly a unit since $HG = \id$.

:::

:::{.proof title="of c"}
\envlist

- If $I\normal R$ is maximal, $I\neq R$, and so by (b) we have $V(I) \neq \emptyset$.
- So there is some $x_0\in[0, 1]$ with $f(x_0) = 0$ for all $f\in I$.
- Define $\mfm_{x_0} \da \ts{f\in R \st f(x_0) = 0}$, which is clearly an ideal.
  - This is a proper ideal, since constant nonzero functions are continuous and thus in $R$, not not $\mfm_{x_0}$.
- We thus have $I \subseteq \mfm_{x_0}$, and by maximality they are equal.

:::

\todo[inline]{I'm not super convinced by c!}

:::


## Zero Divisors and Nilpotents

### Spring 2014 #5 $\done$
Let $R$ be a commutative ring and $a\in R$.
Prove that $a$ is not nilpotent $\iff$ there exists a commutative ring $S$ and a ring homomorphism $\phi: R\to S$ such that $\phi(a)$ is a unit.

> Note: by definition, $a$ is nilpotent $\iff$ there is a natural number $n$ such that $a^n = 0$.


:::{.solution}
$\not A\implies \not B$:

- Suppose $a$ is nilpotent, so $a^m = 0_R$, and suppose $\phi: R\to S$ is a ring morphism.
- Ring morphisms send zero to zero, so $0_S = \phi(0_R) = \phi(a^m) = \phi(a)^m$ and $\phi(a)$ is nilpotent.
- But nontrivial rings can't contain nilpotent units: if $u$ is a unit and $ut= 1$ with $u^k=0$, then $1 = 1^k = (ut)^k = u^k t^k=0$ and $R=0$.


$A\implies B$:

- If $a$ is not nilpotent, localize at the infinite multiplicative subset $A \da \ts{1, a, a^2, \cdots}$ to obtain $R\localize{A}$.
  Since $0\not\in A$, this is not the zero ring.
- By the universal property, there is a map $\phi: R\to R\localize{A}$, and the claim is that $\phi(a)$ is a unit in $R\localize{A}$.
- More directly, $\phi(a) = [a/1] \in \ts{p,q \st p\in R, q\in A}$, which has inverse $[a/1]$.

:::

### Spring 2021 #5 $\done$

:::{.problem title="Spring 2021"}
Suppose that $f(x) \in (\ZZ/n\ZZ)[x]$ is a zero divisor.
Show that there is a nonzero $a\in \ZZ/n\ZZ$ with $af(x) = 0$.
:::

:::{.solution}
\envlist

- Write $f(x) = \sum_{k=0}^n a_k x^k$, and supposing it's a zero divisor choose $g(x) = \sum_{k=0}^m b_k x^k$ of minimal degree so that $g\neq 0, b_m\neq 0$, and $f(x)g(x) = 0$.
- The claim is that the top coefficient $b_m$ will suffice.
- Write the product:
\[
0 = f(x)g(x) 
= (a_0 + \cdots + a_{n-1}x^{n-1} + a_n x^n)
(b_0 + \cdots + b_{m-1}x^{m-1} + b_m x^m)
.\]
- Equating coefficients, the coefficient for $x^{m+n}$ must be zero, so (**importantly**) $a_n b_m = 0$.
  - Since $a_n b_m=0$, consider $a_ng(x)$.
    This has degree $d_1 \leq m-1$ but satisfies $a_ng(x)f(x) = a_n(g(x)f(x)) = 0$, so by minimality $a_ng(x) = 0$.
  - This forces $a_n b_0 = \cdots = a_n b_{m-1} = 0$, so $a_n$ annihilates all of the $b_k$.
- Now consider the coefficient of $x^{m+n-1}$, given by $a_{n-1}b_m + a_{n}b_{m-1}$.
  - The second term $a_n b_{m-1}=0$ since $a_n$ annihilates all $b_k$, so (**importantly**) $a_{n-1} b_m = 0$.
  - Considering now $a_{n-1}g(x)$:
    - The same argument shows this has degree $d_2 \leq m-1$ but $a_{n-1}g(x)f(x) = 0$, so $a_{n-1}g(x) = 0$.
    - So $a_{n-1}$ annihilates all $b_k$, and allowing this process to continue inductively.
- For good measure, the coefficient of $x^{m+n-2}$ is $a_{n-2}b_m + a_{n-1}b_{m-1} + a_{n}b_{m-2}$.
  - Note that $a_n, a_{n-1}$ annihilate all $b_k$, so (**importantly**) $a_{n-2} b_m=0$, and so on.

- Thus $a_k b_m = 0$ for all $0\leq k \leq n$, and by linearity and commutativity, we have
\[
b_m f(x) = b_m \sum_{k=0}^n a_k x^k = \sum_{k=0}^n (b_m a_k) x^k = 0
.\]

:::

### Fall 2018 #7 $\done$
Let $R$ be a commutative ring.

a.
Let $r \in R$. Show that the map
\[
r\bullet : R &\to R \\
x &\mapsto r x
.\]
is an $R\dash$module endomorphism of $R$.

b.
We say that $r$ is a **zero-divisor** if $r\bullet$ is not injective.
Show that if $r$ is a zero-divisor and $r \neq 0$, then the kernel and image of $R$ each consist of zero-divisors.

c.
Let $n \geq 2$ be an integer. Show: if $R$ has exactly $n$ zero-divisors, then $\#R \leq n^2$ .

d.
Show that up to isomorphism there are exactly two commutative rings $R$ with precisely 2 zero-divisors.

> You may use without proof the following fact: every ring of order 4 is isomorphic to exactly one of the
following:
\[
\frac{ \ZZ }{ 4\ZZ}, \quad
\frac{ \frac{  \ZZ }{ 2\ZZ} [t]}{(t^2 + t + 1)}, \quad
\frac{ \frac{ \ZZ }{ 2\ZZ} [t]}{ (t^2 - t)}, \quad
\frac{ \frac{ \ZZ}{2\ZZ}[t]}{(t^2 )}
.\]

:::{.concept}
\envlist

- Testing module morphisms: $\phi(sm + n) = s\phi(m) + \phi(n)$.
- First isomorphism theorem used for sizes: $R/\ker f \cong \im f$, so $\# R = \# \ker f \cdot \# \im f$.
- See 1964 Annals "Properties of rings with a finite number of zero divisors"
:::

:::{.solution}
\envlist

:::{.proof title="of a"}
\envlist

- Let $\phi$ denote the map in question, it suffices to show that $\phi$ is $R\dash$linear, i.e. $\phi(s\vector x + \vector y) = s\phi(\vector x) + \phi(\vector y)$:
\[
\phi(s\vector x + \vector y) 
&= r(s\vector x + \vector y) \\
&= rs\vector x + r\vector y \\
&= s(r\vector x) + (r\vector y) \\
&= s\phi(\vector x) + \phi(\vector y)
.\]
:::

:::{.proof title="of b"}
Let $\phi_r(x) \da rx$ be the multiplication map.

- Let $x\in \ker \phi_r \da \ts{x\in R \st rx = 0}$.

- Since $R$ is commutative $0 = rx = xr$, and so $r\in \ker \phi_x$, so $\ker \phi_x \neq 0$ and $x$ is a zero divisor by definition.

- Let $y\in \im \phi_r \da \theset{y \da rx \suchthat x\in R}$, we want to show $\ker \phi_y$ is nontrivial by producing some $z$ such that $yz=0$.
  Write $y\da rx$ for some $x\in R$.

- Since $r$ is a zero divisor, we can produce some $z\neq 0 \in \ker \phi_r$, so $rz = 0$. 

- Now using that $R$ is commutative, we can compute
\[
yz = (rx)z = (xr)z = x (rz) = x(0) = 0
,\]
so $z\in \ker \phi_y$.
:::

:::{.proof title="of c"}
\envlist

- Let $Z \definedas \theset{z_i}_{i=1}^n$ be the set of $n$ zero divisors in $R$.
- Let $\phi_i$ be the $n$ maps $x \mapsto z_i x$, and let $K_i = \ker \phi_i$ be the corresponding kernels.
- Fix an $i$.
- By (b), $K_i$ consists of zero divisors, so 
\[
\abs{K_i} \leq n < \infty \quad \text{for each } i
.\]

- Now consider $R/K_i \definedas \theset{r + K_i}$.
- By the first isomorphism theorem, $R/K_i \cong \im \phi$, and by (b) every element in the image is a zero divisor, so 
\[
[R: K_i] = \abs{R/K_i} = \abs{\im \phi_i} \leq n 
.\]

- But then 
\[
\abs{R} = [R:K_i]\cdot \abs{K_i} \leq n\cdot n = n^2 
.\]

:::

:::{.proof title="of d"}
\envlist

- By (c), if there are exactly 2 zero divisors then $\abs{R} \leq 4$.
Since every element in a finite ring is either a unit or a zero divisor, and $\abs{R\units} \geq 2$ since $\pm 1$ are always units, we must have $\abs{R} = 4$.

- Since the characteristic of a ring must divide its size, we have $\ch R = 2$ or $4$.

- Using the hint, we see that only $\ZZ/(4)$ has characteristic 4, which has exactly 2 zero divisors given by $[0]_4$ and $[2]_4$.

- If $R$ has characteristic 2, we can check the other 3 possibilities.

- We can write $\ZZ/(2)[t]/(t^2) = \theset{a + bt \suchthat a,b\in \ZZ/(2)}$, and checking the multiplication table we have
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

- In $\ZZ/(2)[t]/(t^2 - t)$, we can check that $t^2 = t \implies t t^2 = t^2 \implies t(t^2 + 1) = 0 \implies t(t+1) = 0$, so both $t$ and $t+1$ are zero divisors, along with zero, so this is not a possibility.

- Similarly, in $\ZZ/(2)[t]/(t^2 + t + 1)$, we can check the bottom-right corner of the multiplication table to find
\[
\left[\begin{array}{c|cc}
	& t 	& 1 +t \\ \hline
t & 1+t & 1 \\
t & 1 	& t \\
\end{array}\right]
,\]

  and so this ring only has one zero divisor.

- Thus the only possibilities are:
\[
R &\cong \ZZ/(4) \\
R &\cong \ZZ/(2)[t] / (t^2)
.\]

:::

:::



## Zorn's Lemma

### Fall 2013 #4 $\work$
Let $R$ be a commutative ring with $1\neq 0$.
Recall that $x\in R$ is *nilpotent* iff $x^n = 0$ for some positive integer $n$.

a.
Show that the collection of nilpotent elements in $R$ forms an ideal.

b.
Show that if $x$ is nilpotent, then $x$ is contained in every prime ideal of $R$.

c.
  Suppose $x\in R$ is not nilpotent and let $S = \theset{x^n \suchthat n\in \NN}$.
  There is at least on ideal of $R$ disjoint from $S$, namely $(0)$.

  By Zorn's lemma the set of ideals disjoint from $S$ has a maximal element with respect to inclusion, say $I$.
  In other words, $I$ is disjoint from $S$ and if $J$ is any ideal disjoint from $S$ with $I\subseteq J \subseteq R$ then $J=I$ or $J=R$.

  Show that $I$ is a prime ideal.

d. 
Deduce from (a) and (b) that the set of nilpotent elements of $R$ is the intersection of all prime ideals of $R$.

### Fall 2015 #3 $\done$
Let $R$ be a rng (a ring without 1) which contains an element $u$ such that for all $y\in R$, there exists an $x\in R$ such that $xu=y$.

Prove that $R$ contains a maximal left ideal.

> Hint: imitate the proof (using Zorn's lemma) in the case where $R$ does have a 1.

:::{.solution}
\envlist

- Define the map
\[
\phi_u: R &\to R\\
x &\mapsto xu
,\]
  which is right-multiplication by $u$.
  By assumption, $\phi_u$ is surjective, so the principal ideal $Ru$ equals $R$.

- Then $K \da \ker \phi_u \in \Id(R)$ is an ideal.
- $K$ is proper -- otherwise, noting $Ru=R$, if $K=R$ we have $Ru = 0$ and thus $R=0$.
  So suppose $R\neq 0$.
- Take a poset $S \da \ts{J\in \Id(R) \st J \contains K, J\neq R}$, the set of all ideals containing $K$, ordered by subset inclusion.
  Note that $K \in S$, so $S$ is nonempty.
- Apply Zorn's lemma: let $C: C_1 \subseteq C_2 \subseteq \cdots$ be a chain (totally ordered sub-poset) in $S$.
  If $C$ is the empty chain, $K$ is an upper bound.
  Otherwise, if $C$ is nonempty, define $\hat{C} \da \Union_{i=1}^\infty C_i$.
  - $\hat{C}$ is an ideal: if $a,b\in \hat{C}$, then $a\in C_i, b\in C_j$ for some $i,j$.
  But without loss of generality, using that chains are totally ordered, $C_i \subseteq C_j$, so $a,b\in C_j$ and thus $ab\in C_j$.
  Similarly for $x\in \hat{C}$, $x\in C_j$ for some $j$, and thus $Rx \subseteq C_j$ since $C_j$ is an ideal.
  - $\hat{C}$ is in $S$:
  It clearly contains $K$, since for example $K \subseteq C_1 \subseteq \hat{C}$.
    - That $\hat{C} \neq R$: an ideal equals $R$ iff it contains a unit.
    But if $r\in \hat{C}$ is a unit, $r\in C_j$ for some $j$ is a unit, making $C_j=R$. $\contradiction$
- So by Zorn's lemma, $\hat{C}$ contains a maximal ideal (incidentally containing $K$).
:::

### Spring 2015 #7 $\done$
Let $R$ be a commutative ring, and $S\subset R$ be a nonempty subset that does not contain 0 such that for all $x, y\in S$ we have $xy\in S$.
Let $\mci$ be the set of all ideals $I\normal R$ such that $I\intersect S = \emptyset$.

Show that for every ideal $I\in \mci$, there is an ideal $J\in \mci$ such that $I\subset J$ and $J$ is not properly contained in any other ideal in $\mci$.

Prove that every such ideal $J$ is prime.


:::{.solution}
\envlist

- Restating, take the poset $S\da \ts{J\in \Id(R) \st J \intersect S = \emptyset, I\neq R, I \subseteq J}$ ordered by inclusion.
  Note that $S$ is nonempty since it contains $I$.
  It suffices to produce a maximal element of $S$.
- Applying Zorn's lemma, let $C: C_1 \subseteq C_2 \subseteq \cdots$ be a chain and define $\hat{C} \da \union C_i$.
- By standard arguments, $\hat{C} \in \Id(R)$ and $\hat{C} \contains I$, and it suffices to show $\hat{C} \intersect S = \emptyset$ and $\hat{C}\neq R$.
- $\hat{C} \intersect S = \emptyset$:
  - By contradiction, if $x\in \hat{C} \intersect S$ then $x\in C_j$ for some $j$, and $x\in S$.
    But then $x \in C_j \intersect S = \emptyset$.
- $\hat{C} \neq R$:
  - By contradiction, if so then $1 \in \hat{C} \implies 1 \in C_j$ for some $j$, forcing $C_j = R$.
- So Zorn's lemma applies and we obtain some ideal $\mfp$, which we now claim is prime.
- Let $ab\in \mfp$, we want to show $a\in \mfp$ or $b\in\mfp$.
- Suppose not, then neither $a,b\in \mfp$. 
  By maximality, $\mfp + Ra = R$, and so $\mfp + Ra$ intersects $S$.
  Similarly $\mfp + Rb = R$ so $\mfp + Rb$ intersects $S$.
- Produce elements $x\da p_1 + r_1a, y\da p_2 + r_2b\in S$, then since $S$ is multiplicatively closed,
\[
xy&\da (p_1 + r_1 a)(p_2 + r_2b)\in S \\
&\implies p_1 p_2 + p_1r_2 b + p_2 r_1 a + r_1 r_2 ab \in S \\ 
&\implies xy\in \mfp + \mfp Rb + \mfp Ra + R\mfp && \text{since } p_i, ab\in \mfp \\
&\implies xy \in (\mfp + Rb + Ra + R)\mfp \subseteq \mfp
.\]
  But then $xy\in S \intersect \mfp$, a contradiction.

:::

### Spring 2013 #1 $\done$
Let $R$ be a commutative ring.

a.
Define a *maximal ideal* and prove that $R$ has a maximal ideal.

b.
Show than an element $r\in R$ is not invertible $\iff r$ is contained in a maximal ideal.

c.
Let $M$ be an $R\dash$module, and recall that for $0\neq \mu \in M$, the *annihilator* of $\mu$ is the set
\[
\ann(\mu) = \theset{r\in R \suchthat r\mu = 0}
.\]
  Suppose that $I$ is an ideal in $R$ which is maximal with respect to the property that there exists an element $\mu \in M$ such that $I = \ann(\mu)$ for some $\mu \in M$.
  In other words, $I = \ann(\mu)$ but there does not exist $\nu\in M$ with $J = \ann(\nu) \subsetneq R$ such that $I\subsetneq J$.

  Prove that $I$ is a prime ideal.


:::{.solution}
\envlist

:::{.proof title="part a and b"}
\envlist

- Maximal: a proper ideal $I\normal R$, so $I\neq R$, such that if $J\contains I$ is any other ideal, $J = R$.
- Existence of a maximal ideal: use that $0\in \Id(R)$ always, so $S\da \ts{I\in \Id(R) \st I\neq R}$ is a nonempty poset under subset inclusion.
  Applying the usual Zorn's lemma argument produces a maximal element.
:::

:::{.proof title="part c"}
$\impliedby$:
By contrapositive: if $r\in R$ is a unit and $\mfm$ is maximal, then $r\in \mfm \implies \mfm = R$, contradicting that $\mfm$ is proper.


$\implies$:

- Suppose $a$ is not a unit, we'll produce a maximal ideal containing it.
- Let $I\da Ra$ be the principal ideal generated by $a$, then $Ra \neq R$ since $a$ is not a unit.
- Take a poset $S \da \ts{J\in \Id(R) \st J\contains Ra, J\neq R}$ ordered by set inclusion.
  - Let $C_*$ be a chain in $S$, set $\hat{C} \da \union C_i$.
    Then $\hat{C} \in S$:

    - $\hat{C} \neq R$, since if so it contains a unit, forcing some $C_i$ to contain a unit and thus equal $R$.
    - $\hat{C} \contains Ra$, since e.g. $\hat{C} \contains C_1 \contains Ra$.
    - $\hat{C}$ is an ideal since $xy\in \hat{C} \implies x\in C_i, y\in C_j$ and $C_i \subseteq C_j$ without loss of generality, so $xy\in C_j \subseteq \hat{C}$.
- Then $Ra \subseteq \hat{C}$, some maximal ideal.

:::

:::{.proof title="of d"}
\envlist

- Write $I \da \Ann(u)$ for some $u$, and toward a contradiction suppose $ab\in I$ but $a,b\not\in I$.
- Then $abu=0$ but $au\neq 0, bu\neq 0$.
- Since $abu=0$, we have $a\in \Ann(bu)$.
  Note that $\Ann(bu) \contains \Ann(u)$, since $su = 0\implies bsu=sbu=0$.
- We can't have $\Ann(bu) = R$, since if $sbu=0$ for all $s\in R$, so we could take $s=1$ to get $bu=0$ and $b\in \Ann(u)$.
- By maximality, this forces $\Ann(u) = \Ann(bu)$, so $sbu = 0 \implies su=0$ for any $s\in R$.
- Now take $s=a$, and since $abu=0$ we get $au=0$ and $a\in \Ann(u)$. $\contradiction$

:::


:::

### Fall 2019 #6 $\done$
Let $R$ be a commutative ring with multiplicative identity. Assume Zorn's Lemma.

a.
Show that
$$
N = \{r \in R \mid r^n = 0 \text{ for some } n > 0\}
$$
is an ideal which is contained in any prime ideal.

b.
Let $r$ be an element of $R$ not in $N$.
Let $S$ be the collection of all proper ideals of $R$ not containing any positive power of $r$. Use Zorn's Lemma to prove that
there is a prime ideal in $S$.

c.
Suppose that $R$ has exactly one prime ideal $P$ . Prove that every element $r$ of $R$ is either nilpotent or a unit.

:::{.concept}
\envlist

- Prime ideal: $\mathfrak{p}$ is prime iff $ab \in \mathfrak{p} \implies a\in \mathfrak{p}$ or $b\in \mathfrak{p}$.
- Silly fact: 0 is in every ideal!
 
- **Zorn's Lemma:** Given a poset, if every chain has an upper bound, then there is a maximal element. (Chain: totally ordered subset.)
 
- **Corollary:** If $S\subset R$ is multiplicatively closed with $0\not\in S$ then $\theset{I \normal R \suchthat J\intersect S = \emptyset}$ has a maximal element.

  \todo[inline]{Prove this}

- **Theorem:** If $R$ is commutative, maximal $\implies$ prime for ideals.

  \todo[inline]{Prove this}

- **Theorem:** Non-units are contained in a maximal ideal. (See HW?)

:::

:::{.solution}
\envlist

:::{.proof title="of a"}
\envlist

- Let $\mathfrak{p}$ be prime and $x\in N$.
- Then $x^k = 0 \in \mathfrak{p}$ for some $k$, and thus $x^k = x x^{k-1} \in \mathfrak p$.
- Since $\mathfrak p$ is prime, inductively we obtain $x\in\mathfrak p$.
:::

:::{.proof title="of b"}
\envlist

- Let $S = \theset{r^k \mid k\in \NN}$ be the set of positive powers of $r$. 

- Then $S^2 \subseteq S$, since $r^{k_1}r^{k_2} = r^{k_1+k_2}$ is also a positive power of $r$, and $0\not\in S$ since $r\neq 0$ and $r\not\in N$.

- By the corollary, $\theset{I \normal R \suchthat I\intersect S = \emptyset}$ has a maximal element $\mathfrak{p}$.

- Since $R$ is commutative, $\mathfrak{p}$ is prime.

:::

:::{.proof title="of c"}
\envlist

- Suppose $R$ has a unique prime ideal $\mathfrak{p}$.

- Suppose $r\in R$ is not a unit, and toward a contradiction, suppose that $r$ is also not nilpotent.

- Since $r$ is not a unit, $r$ is contained in some maximal (and thus prime) ideal, and thus $r \in \mathfrak{p}$.

- Since $r\not\in N$, by (b) there is a maximal ideal $\mathfrak{m}$ that avoids all positive powers of $r$. 
Since $\mathfrak{m}$ is prime, we must have $\mathfrak{m} = \mathfrak{p}$.
  But then $r\not\in \mathfrak{p}$, a contradiction.

:::

:::


## Noetherian Rings

### Fall 2015 #4 $\done$
Let $R$ be a PID and $(a_1) < (a_2) < \cdots$ be an ascending chain of ideals in $R$.
Prove that for some $n$, we have $(a_j) = (a_n)$ for all $j\geq n$.

:::{.solution}
\envlist

- Let $I\da \union Ra_i$ which is an ideal in a PID and thus $I = Rb$ for some $b$.
- Using that $b\in I$, which is a union, we have $Rb\in Ra_m$ for some $m$.
- Thus $I = R_b \subseteq Ra_m$, and $Ra_m \subseteq I$ by definition of $I$, so $Rb = Ra_m$.
- In particular, since $Ra_{m} \subseteq Ra_{m+1}$ by assumption, and $Ra_{m+1} \subseteq Rb \subseteq Ra_m$ since $Rb = I$, we have $Ra_m = Ra_{m+1}$.
  So inductively, the chain stabilizes at $m$.
:::

### Spring 2021 #6 $\work$

a. 
Carefully state the definition of **Noetherian** for a commutative ring $R$.

b. 
Let $R$ be a subset of $\ZZ[x]$ consisting of all polynomials 
\[
f(x) = a_ 0 + a_1 x + a_2 x^2 + \cdots + a_nx^n
\]
such that $a_k$ is even for $1\leq k \leq n$.
Show that $R$ is a subring of $\ZZ[x]$.

c. Show that $R$ is not Noetherian.

  > *Hint: consider the ideal generated by \( \ts{ 2x^k \st 1\leq k \in \ZZ } \).*



:::{.solution}

- A ring is **Noetherian** iff $R$ satisfies the ascending chain condition: every chain of ideals $A_1 \subseteq A_2 \subseteq \cdots$ eventually stabilizes, so $A_m \subseteq A_{m+1} = A_{m+2} = \cdots$.

- That $R$ is a subring of $\ZZ[x]$:
  - $(R, +)$ is an abelian subgroup: note that $f(x) + g(x) = \sum a_k x^k + \sum b_k x^k = \sum (a_k + b_k) x^k$, so if $a_k, b_k$ are even then $a_k + b_k$ is even.
    It's closed under inverses, since $a_k$ is even iff $-a_k$ is even, and contains zero.
  - $(R, \cdot)$ is a submonoid: $f(x) g(x) = \sum_{n=1}^N \qty{ \sum_{k=1}^n a_k b_{n-k}} x^k$ where without loss of generality, $\deg f = \deg g = n$ by setting coefficients to zero.
    Then sums and products of even integers are even, so $fg \in R$.

- That $R$ is not Noetherian: it suffices to show that $R$ contains an ideal that is not finitely generated.
- The claim is that setting $S \da \ts{2x^k}_{k\in \ZZ_{\geq 1}}$ and taking 
\[
I \da \gens{S} = \sum_{k\in \ZZ_{\geq 1}} R\cdot 2x^k \da \ts{ \sum_{i=1}^m r_k(x) 2x^k \st r_k(x) \in 2\ZZ[x], m\in \ZZ_{\geq 0}}
\]
  yields an ideal that is not finitely generated.

- Suppose toward a contradiction that $\ts{g_1, g_2, \cdots, g_M}$ were a finite generating set, where each $g_i \in I$.

\todo[inline]{???}


:::

## Simple Rings

### Fall 2017 #5 $\done$
A ring \( R \) is called *simple* if its only two-sided ideals are $0$ and $R$.

a.
Suppose $R$ is a commutative ring with 1. Prove $R$ is simple if and only if $R$ is a field.

b.
Let $k$ be a field. Show the ring $M_n (k)$, $n \times n$ matrices with entries in $k$, is a simple ring.


:::{.concept}
\envlist

- Nonzero proper ideals contain at least one nonzero element.
- $I=R$ when $1\in I$.
- Effects of special matrices: let $A_{ij}$ be a matrix with only a 1 in the $ij$ position.
  - Left-multiplying $A_{ij}M$ moves row $j$ to row $i$ and zeros out the rest of $M$.
  - Right-multiplying $MA_{ij}$ moves column $i$ to column $j$ and zeros out the rest.
  - So $A_{ij} M A_{kl}$ moves entry $j, k$ to $i, l$ and zeros out the rest.
:::

:::{.solution}

:::{.proof title="of a"}
$\implies$:

- Suppose $\Id(R) = \ts{\gens{0}, \gens{1}}$.
  Then for any nonzero $r\in R$, the ideal $\gens{r} = \gens{1}$ is the entire ring.
- In particular, $1\in \gens{r}$, so we can write $a = tr$ for some $t\in R$.
- But then $r\in R\units$ with $t\da r\inv$.

$\impliedby$:

- Suppose $R$ is a field and $I\in \Id(R)$ is an ideal.
- If $I \neq \gens{0}$ is proper and nontrivial, then $I$ contains at least one nonzero element $a\in I$.
- Since $R$ is a field, $a\inv \in R$, and $aa\inv = 1\in I$ forces $I = \gens{1}$.

:::

:::{.proof title="of b"}

- Let $J\normal R$ be a nonzero two-sided ideal, noting that $R$ is noncommutative -- the claim is that $J$ contains $I_n$, the $n\times n$ identity matrix, and thus $J = R$.
- Pick a nonzero element $M\in I$, then $M$ has a nonzero entry $m{ij}$.
- Let $A_{ij}$ be the matrix with a 1 in the $i,j$ position and zeros elsewhere.
  - Left-multiplying $A_{ij}M$ moves row $j$ to row $i$ and zeros out the rest of $M$.
  - Right-multiplying $MA_{ij}$ moves column $i$ to column $j$ and zeros out the rest.
  - So $A_{ij} M A_{kl}$ moves entry $j, k$ to $i, l$ and zeros out the rest.
- So define $B \da A_{i, i}MA_{j, i}$, which movies $m_{ij}$ to the $i,i$ position on the diagonal and has zeros elsewhere.
- Then $m_{ij}\inv \eps_{ii} \da A_{ii}$ is a matrix with $1$ in the $i, i$ spot for any $i$.
  Since $I$ is an ideal, we have $\eps_{ii}\in I$ for every $i$.
- We can write the identity $I_n$ as $\sum_{i=1}^n \eps_{ii}$, so $I_n \in I$ and $I=R$.

:::

:::

### Spring 2016 #8 $\done$
Let $R$ be a simple rng (a nonzero ring which is not assume to have a 1, whose only two-sided ideals are $(0)$ and $R$) satisfying the following two conditions:

i. $R$ has no zero divisors, and
ii. If $x\in R$ with $x\neq 0$ then $2x\neq 0$, where $2x\definedas x+x$.

Prove the following:

a.
For each $x\in R$ there is one and only one element $y\in R$ such that $x = 2y$.

b.
Suppose $x,y\in R$ such that $x\neq 0$ and $2(xy) = x$, then $yz = zy$ for all $z\in R$.

> You can get partial credit for (b) by showing it in the case $R$ has a 1.

:::{.concept}
\envlist

- $R$ has no left zero divisors iff $R$ has the left cancellation property: $xa=xb \implies a=b$.
- $R$ has no right zero divisors iff $R$ has the right cancellation property: $ax=bx \implies a=b$.
:::

:::{.solution}
Note: solutions borrowed from folks on Math twitter!

:::{.proof title="part 1"}
\envlist

- Existence: the claim is that $2R \da \ts{2y \st y\in R}$ is a nontrivial two-sided ideal of $R$, forcing $2R = R$ by simpleness.
  - That $2R \neq 0$ follows from condition (1):
  Provided $y\neq 0$, we have $2y\neq 0$, and so if $R\neq 0$ then there exists some nonzero $a\in R$, in which case $2a\neq 0$ and $2a\in 2R$.
  - That $2R$ is a right ideal: clear, since $(2y)\cdot r = 2(yr)\in 2R$.
  - That $2R$ is a left ideal: use that multiplication is distributive:
  \[
  r\cdot 2y \da r(y+y) = ry + ry \da 2(ry) \in 2R
  .\]
- So $2R = R$ by simpleness.
- Uniqueness: 
  - Use the contrapositive of condition (1), so that $2x = 0 \implies x=0$.
  - Suppose toward a contradiction that $x=2y_1 = 2y_2$, then
  \[
  0 = x-x = 2y_1 - 2y_2 = 2(y_1 - y_2) \implies y_1 - y_2 = 0 \implies y_1 = y_2
  .\]
:::

:::{.proof title="part 2"}
\envlist

- First we'll show $z=2(yz)$:
\[
xy + xy &= x \\
\implies xy + xy - x &= 0 \\
\implies xyz + xyz - xz &= 0 \\
\implies x(yz + yz - z) &= 0 \\
\implies yz + yz - z &= 0 && \text{since } x\neq 0 \text{ and no zero divisors }\\
\implies 2(yz) &= z 
.\]

- Now we'll show $z=2(zy)$:
\[
yz + yz &= z \\
\implies zyz + zyz &= zz \\
\implies zyz + zyz - zz &= 0 \\
\implies (zy + zy - z)z &= 0\\
\implies z=0 \text{ or } zy+zy-z &= 0 && \text{ no zero divisors } 
.\]

- Then if $z=0$, we have $yz = 0 = zy$ and we're done.
- Otherwise, $2(zy) = z$, and thus
\[
2(zy) = z = 2(yz) \implies 2(zy - yz) = 0 \implies zy-yz = 0
,\]
so $zy=yz$.
:::

:::{.proof title="of 2, if $R$ is unital"}
\envlist

- If $1\in R$, 
\[
2xy &= x \\
\implies 2xy-x &= 0 \\
\implies x(2y-1) &= 0 \\
\implies 2y-1 &= 0 && x\neq 0 \text{ and no zero divisors}\\
\implies 2y &= 1
.\]
- Now use
\[
1\cdot z &= z\cdot 1 \\
\implies (2y)z &= z(2y) \\
\implies (y+y)z &= z(y+y) \\
\implies yz+yz &= zy+zy \\
\implies 2(yz) &= 2(zy) \\
\implies 2(yz-zy) &= 0 \\
\implies yz-zy &= 0 \\
,\]
using condition (2).
:::

:::

## Unsorted

### Fall 2019 #3 $\done$
Let $R$ be a ring with the property that for every $a \in R, a^2 = a$.

a.
Prove that $R$ has characteristic 2.

b.
Prove that $R$ is commutative.


:::{.strategy}
\envlist

- Just fiddle with direct computations.
- Context hint: that we should be considering things like $x^2$ and $a+b$.

:::

:::{.solution}
\envlist

:::{.proof title="of a"}
\[
2a  = (2a)^2 = 4a^2 = 4a \implies 2a = 0
.\]
Note that this implies $x = -x$ for all $x\in R$.
:::

:::{.proof title="of b"}
\[
a+b = (a+b)^2 &= a^2 + ab + ba + b^2 = a + ab + ba + b \\
&\implies ab + ba = 0 \\
&\implies ab = -ba \\
&\implies ab = ba \quad\text{by (a)}
.\]

:::

:::


### Spring 2018 #5 $\done$
Let 
\[
M=\left(\begin{array}{ll}{a} & {b} \\ {c} & {d}\end{array}\right)
\quad \text{and} \quad 
N=\left(\begin{array}{cc}{x} & {u} \\ {-y} & {-v}\end{array}\right)
\]

over a commutative ring $R$, where $b$ and $x$ are units of $R$. 
Prove that
\[
M N=\left(\begin{array}{ll}{0} & {0} \\ {0} & {*}\end{array}\right)
\implies MN = 0
.\]

:::{.solution}
\envlist

- Multiply everything out to get
\[
\matt{ax-by}{au-bv}{cx-dy}{cu-dv}
,\]
  so it suffices to show $cu=dv$ given
  \[
  ax &= by \\
  cx &= dy \\
  au &= bv
  .\]

- Writing $cu$:
  - Use that $b\in R\units$, left-multiply (1) by $b\inv$ to get $b\inv a x = y$
  - Substitute $y$ into (2) to get $cx = d(b\inv a x)$.
  - Since $x\in R\units$, right-multiply by $x\inv$ to get $c = db\inv a$ and thus $cu = db\inv a u$.
  - Summary:
  \[
  ax = by 
  &\implies b\inv ax = y \\
  &\implies cx = dy = d(b\inv a x) \\
  &\implies c = db\inv a \\
  &\implies cu = db\inv au 
  .\]

- Writing $dv$:
  - Left-multiply (3) by $b\inv$ to get $b\inv au = v$.
  - Left-multiply by $d$ to get $db\inv au = dv$
  - Summary:
  \[
  au = bv 
  &\implies b\inv a u = v \\
  &\implies db\inv au = dv
  .\]

- So 
\[
cu = db\inv a u = dv
.\]

:::




### Spring 2014 #6 $\work$
 $R$ be a commutative ring with identity and let $n$ be a positive integer.

a.
Prove that every surjective $R\dash$linear endomorphism $T: R^n \to R^n$ is injective.

b.
Show that an injective $R\dash$linear endomorphism of $R^n$ need not be surjective.


