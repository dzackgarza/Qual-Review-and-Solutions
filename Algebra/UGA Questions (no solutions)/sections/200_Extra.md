# Extra Problems

> Many many fundamental problems here: <https://math.ucr.edu/~mpierce/teaching/qual-algebra/fun/groups/>

## Linear Algebra

1. For a division ring $D$, let $V_{i}$ be a finite dimensional vector space over $D$ for $i \in\{1, \ldots, k\}$. Suppose the sequence
\[
0 \longrightarrow V_{1} \longrightarrow V_{2} \longrightarrow \cdots V_{k} \longrightarrow 0
\]
is exact. Prove that $\sum_{i=1}^{k}(-1)^{i} \operatorname{dim}_{D} V_{i}=0$.
2. Prove that if $A$ and $B$ are invertible matrices over a field $\boldsymbol{k}$, then $A+\lambda B$ is invertible for all but finitely many $\lambda \in \boldsymbol{k}$.
3. For the ring of $n \times n$ matrices over a commutative unital ring $R$, which we'll denote $\operatorname{Mat}_{n}(R)$, recall the definition of the determinant map det: $\operatorname{Mat}_{n}(R) \rightarrow R$. For $A \in \operatorname{Mat}_{n}(R)$ also recall the definition of the classical adjoint $A^{a}$ of $A$. Prove that:
  - $\operatorname{det}\left(A^{a}\right)=\operatorname{det}(A)^{n-1}$
  - $\left(A^{a}\right)^{a}=\operatorname{det}(A)^{n-2} A$

4. If $R$ is an integral domain and $A$ is an $n \times n$ matrix over $R$, prove that if a system of linear equations $A x=0$ has a nonzero solution then $\operatorname{det} A=0$. Is the converse true? What if we drop the assumption that $R$ is an integral domain?
5. What is the companion matrix $M$ of the polynomial $f=x^{2}-x+2$ over $C$ ? Prove that $f$ is the minimal polynomial of $M$.
6. Suppose that $\phi$ and $\psi$ are commuting endomorphisms of a finite dimensional vector space $E$ over a field $\boldsymbol{k}$, so $\phi \psi=\psi \phi$.
  - Prove that if $k$ is algebraically closed, then $\phi$ and $\psi$ have a common eigenvector.
  - Prove that if $E$ has a basis consisting of eigenvectors of $\phi$ and $E$ has a basis consisting of eigenvectors of $\psi$, then $E$ has a basis consisting of vectors that are eigenvectors for both $\phi$ and $\psi$ simultaneously.

## Galois Theory

> Taken from here: <https://math.ucr.edu/~mpierce/teaching/qual-algebra/fun/galois/>

1. Suppose that for an extension field $F$ over $K$ and for $a \in F$, we have that $b \in F$ is algebraic over $K(a)$ but transcendental over $K$. Prove that $a$ is algebraic over $K(b)$.
2. Suppose that for a field $F / K$ that $a \in F$ is algebraic and has odd degree over $K$. Prove that $a^{2}$ is also algebraic and has odd degree over $K$, and furthermore that $K(a)=K\left(a^{2}\right)$
3. For a polynomial $f \in K[x]$, prove that if $r \in F$ is a root of $f$ then for any $\sigma \in \mathbf{A u t}_{K} F, \sigma(r)$ is also a root of $f$
4. Prove that as extensions of $\boldsymbol{Q}, \boldsymbol{Q}(x)$ is Galois over $\boldsymbol{Q}\left(x^{2}\right)$ but not over $\boldsymbol{Q}\left(x^{3}\right)$.
5. If $F$ is over $E$, and $E$ is $\quad$ over $K$ is $F$ necessarily over $K$ ? Answer this question for each of the words "algebraic," "normal," and "separable" in the blanks.
6. If $F$ is over $K$, and $E$ is an intermediate extension of $F$ over $K$, is $F$
necessarily over $E ?$ Answer this question for each of the words "algebraic," "normal," and "separable" in the blanks.
7. If $F$ is some (not necessarily Galois) field extension over $K$ such that $[F: K]=6$ and Aut $_{K} F \simeq S_{3}$, then $F$ is the splitting field of an irreducible cubic over $K[x]$.
8. Recall the definition of the join of two subgroups $H \vee G$ (or $H+G$ ). For $F$ a finite dimensional Galois extension over $K$ and let $A$ and $B$ be intermediate extensions. Prove that
a. $\operatorname{Aut}_{A B} F=\mathrm{Aut}_{A} F \cap \mathrm{Aut}_{B} F$
b. Aut $_{A \cap B} F=\mathrm{Aut}_{A} F \vee \mathrm{Aut}_{B} F$
9. For a field $K$ take $f \in K[x]$ and let $n=\operatorname{deg} f$. Prove that for a splitting field $F$ of $f$ over $K$ that $[F: K] \leq n !$. Furthermore prove that $[F: K]$ divides $n !$.
10. Let $F$ be the splitting field of $f \in K[x]$ over $K$. Prove that if $g \in K[x]$ is irreducible and has a root in $F$, then $g$ splits into linear factors over $F$.
11. Prove that a finite field cannot be algebraically closed.
12. For $u=\sqrt{2+\sqrt{2}}$, What is the Galois group of $\boldsymbol{Q}(u)$ over $\boldsymbol{Q} ?$ What are the intermediate fields of the extension $\boldsymbol{Q}(u)$ over $\boldsymbol{Q}$ ?
13. Characterize the splitting field and all intermediate fields of the polynomial $\left(x^{2}-2\right)\left(x^{2}-3\right)\left(x^{2}-5\right)$ over $Q$. Using this characterization, find a primitive element of the splitting field.
14. Characterize the splitting field and all intermediate fields of the polynomial $x^{4}-3$ over $Q$
15. Consider the polynomial $f=x^{3}-x+1$ in $\boldsymbol{F}_{3}[x]$. Prove that $f$ is irreducible. Calculate the degree of the splitting field of $f$ over $\boldsymbol{F}_{3}$ and the cardinality of the splitting field of $f$.
16. Given an example of a finite extension of fields that has infinitely many intermediate fields.
17. Let $u=\sqrt{3+\sqrt{2}}$. Is $\boldsymbol{Q}(u)$ a splitting field of $u$ over $\boldsymbol{Q}$ ? (MathSE)
18. Prove that the multiplicative group of units of a finite field must be cyclic, and so is generated by a single element.
19. Prove that $\boldsymbol{F}_{p^{n}}$ is the splitting field of $x^{p^{n}}-x$ over $\boldsymbol{F}_{p}$.
20. Prove that for any positive integer $n$ there is an irreducible polynomial of degree $n$ over $\boldsymbol{F}_{p}$
21. Recall the definition of a perfect field. Give an example of an imperfect field, and the prove that every finite field is perfect.
22. For $n>2$ let $\zeta_{n}$ denote a primitive $n$ th root of unity over $Q$. Prove that
\[
\left[\boldsymbol{Q}\left(\zeta_{n}+\zeta_{n}^{-1}: \boldsymbol{Q}\right)\right]=\frac{1}{2} \varphi(n)
\]
where $\varphi$ is Euler's totient function.
23. Suppose that a field $K$ with characteristic not equal to 2 contains an primitive $n$ th root of unity for some odd integer $n$. Prove that $K$ must also contain a primitive $2 n$ th root of unity.
24. Prove that the Galois group of the polynomial $x^{n}-1$ over $Q$ is abelian.
