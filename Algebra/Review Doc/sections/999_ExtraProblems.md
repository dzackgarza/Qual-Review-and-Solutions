# Extra Problems

## Group Theory

### Basic Structure


15. Show that any cyclic group is abelian.
16. Show that if $G/Z(G)$ is cyclic then $G$ is abelian.
17. Show that the intersection of two subgroups is again a subgroup.
18. Show that if $G \actson X$ is a group action, then the stabilizer $G_x$ of a point is a subgroup.
4. Show that $G=H\cross K$ iff the conditions for recognizing direct products hold.
5. Show that if $H, K \normal G$ and $H\intersect K = \emptyset$, then $hk=kh$ for all $h\in H,k\in K$.
10. Show that every normal subgroup of $G$ is contained in $Z(G)$.
14. Show that $\abs{G}/\abs{H} = [G: H]$.
15. Show that the order of any element in a group divides the order of the group.
16. Show that $\phi(n) = n \prod{p\mid n}\qty{1 - {1\over p}}$.
17. Show that $Z(G) \subseteq C_G(H) \subseteq N_G(H)$.
18. Show that $G/N$ is abelian iff $[G, G] \leq N$.
19. Give a counterexample where $H,K\leq G$ but $HK$ is not a subgroup of $G$.
20. Show that if $H,K\normal G$ are normal subgroups that intersect trivially, then $[H, K] = 1$ (so $hk = kh$ for all $k$ and $h$).
21. Give an example showing that normality is not transitive: i.e. $H\normal K \normal G$ with $H$ *not* normal in $G$.

### Primes in Group Theory

- Show that any group of prime order is cyclic and simple.
- Analyze groups of order $pq$ with $q<p$.

  > Hint: consider the cases when $p$ does or does not divide $q-1$.

  - Show that if $q$ does not divide $p-1$, then $G$ is cyclic.
  - Show that $G$ is never simple. 

9. Analyze groups of order $p^2 q$.
10. Show that no group of order $p^2 q^2$ is simple for $p<q$ primes.
10. Show that a group of order $p^2 q^2$ has a normal Sylow subgroup. 
10. Show that a group of order $p^2 q^2$ where $q$ does not divide $p^2-1$ and $p$ does not divide $q^2-1$ is abelian.
11. Show that every group of order $pqr$ with $p<q<r$ primes contains a normal Sylow subgroup.
11. Show that every $p\dash$group is nilpotent.
11. Show that every $p\dash$group is solvable.
9. Show that $p\dash$groups have nontrivial centers.
10. Show that any normal $p\dash$ subgroup is contained in every Sylow $p\dash$subgroup of $G$.

### p-Groups

- Show that every $p\dash$group has a nontrivial center.
- Show that every group of order $p$ is cyclic.
- Show that every group of order $p^2$ is abelian and classify them.
  
  > Hint: Consider $G/Z(G)$.

- Let $O_P(G)$ be the intersection of all Sylow $p\dash$subgroups of $G$.
  Show that $O_p(G) \normal G$, is maximal among all normal $p\dash$subgroups of $G$
- Let $P\in \syl_p(H)$ where $H\normal G$ and show that $P\intersect H \in \syl_p(H)$.
- Show that Sylow $p_i\dash$subgroups $S_{p_1}, S_{p_2}$ for distinct primes $p_1\neq p_2$ intersect trivially.

### Classification

10. Show that no group of order 36 is simple.
10. Show that no group of order 90 is simple.
11. Show that all groups of order 45 are abelian.

### Group Actions

1. Show that the stabilizer of an element $G_x$ is a subgroup of $G$.
2. Show that if $x, y$ are in the same orbit, then their stabilizers are conjugate.
3. Show that the stabilizer of an element need not be a normal subgroup?

### Series

6. Show that $A_n$ is simple for $n\geq 5$
8. Give a necessary and sufficient condition for a cyclic group to be solvable.
9. Prove that every simple abelian group is cyclic.

### Misc

- Show that the size of a conjugacy class divides the order of a group.

- Show that $\Inn(G) \normal Aut(G)$

- Show that $\Inn(G) \cong G / Z(G)$

- Show that the kernel of the map $G\to \aut(G)$ given by $g\mapsto (h\mapsto ghg\inv)$ is $Z(G)$.

- Show that $C_G(H) \subseteq N_G(H) \leq G$.

- Show that $N_G(H) / C_G(H) \cong A \leq Aut(H)$

- Given $H\subseteq G$, let $S(H)= \bigcup_{g\in G} gHg^{-1}$, so $\abs{S(H)}$ is the number of conjugates to $H$. 
  Show that $\abs{S(H)} = [G : N_G(H)]$.
  - That is, the number of subgroups conjugate to $H$ equals the index of the normalizer of $H$.

- Show that $Z(G) = \bigcap_{a\in G} C_G(a)$.

- Show that the centralizer $G_G(H)$ of a subgroup is again a subgroup.

- Show that $C_G(H) \normal N_G(H)$ is a normal subgroup.

- Show that $C_G(G) = Z(G)$.

- Show that for $H\leq G$, $C_H(x) = H \intersect C_G(x)$.

### Nonstandard Topics

- Show that $H~\text{char}~G \Rightarrow H \unlhd G$
  
  > Thus "characteristic" is a strictly stronger condition than normality

- Show that $H ~\text{char}~ K ~\text{char}~G \Rightarrow H ~\text{char}~ G$
  
  > So "characteristic" is a transitive relation for subgroups.

- Show that if $H \leq G$, $K\normal G$ is a normal subgroup, and $H~\text{char}~K$ then $H$ is normal in  $G$.

  > So normality is not transitive, but strengthening one to "characteristic" gives a weak form of transitivity.

## Ring Theory

1. Show that if $x\in R$ a PID, then $x$ is irreducible $\iff \gens{x}\normal R$ is maximal.

## Field Theory

1. What is $[\QQ(\sqrt 2 + \sqrt 3): \QQ]$?
2. What is $[\QQ(2^{3\over 2}) : \QQ]$?
3. Show that every field is simple.
4. Show that any field morphism is either 0 or injective.
5. Show that if $p\in \QQ[x]$ and $r\in \QQ$ is a rational root, then in fact $r\in \ZZ$.
6. If $\theset{\alpha_i}_{i=1}^n \subset F$ are algebraic over $K$, show that $K[\alpha_1, \cdots, \alpha_n] = K(\alpha_1, \cdots, \alpha_n)$.
7. Show that the Galois group of $x^n - 2$ is $D_n$, the dihedral group on $n$ vertices.
8. Compute all intermediate field extensions of $\QQ(\sqrt 2, \sqrt 3)$, show it is equal to $\QQ(\sqrt 2 + \sqrt 3)$, and find a corresponding minimal polynomial.
 
![](figures/image_2020-06-01-20-56-35.png)

9. Compute all intermediate field extensions of $\QQ(2^{1\over 4}, \zeta_8)$.
10. Show that $\QQ(2^{1\over 3})$ and $\QQ(\zeta_3 2^{1\over 3})$
11. Show that if $L/K$ is separable, then $L$ is normal $\iff$ there exists a polynomial $p(x) = \prod_{i=1}^n x- \alpha_i\in K[x]$ such that $L = K(\alpha_1, \cdots, \alpha_n)$ (so $L$ is the splitting field of $p$).
12. Is $\QQ(2^{1\over 3})/\QQ$ normal? 
13. Show that any finite integral domain is a field.
14. Prove that if $R$ is an integral domain, then $R[t]$ is again an integral domain.
15. Show that $ff(R[t]) = ff(R)(t)$.
16. Prove that $x^{p^n}-x$ is the product of all monic irreducible polynomials in $\FF_p[x]$ with degree dividing $n$.
17. Prove that an irreducible $\pi(x)\in \FF_p[x]$ divides $x^{p^n}-x \iff \deg \pi(x)$ divides $n$.
18. Show that a field with $p^n$ elements has exactly one subfield of size $p^d$ for every $d$ dividing $n$.
19. Show that  $\GF(p^n)$ is the splitting field of $x^{p^n} - x \in \FF_p[x]$.
20. Show that $x^{p^d} - x \divides x^{p^n} - x \iff d \divides n$
21. Show that $\GF(p^d) \leq \GF(p^n) \iff d\divides n$
22. Show that $x^{p^n} - x = \prod f_i(x)$ over all irreducible monic $f_i$ of degree $d$ dividing $n$.
23. Compute the Galois group of $x^n - 1 \in \QQ[x]$ as a function of $n$.
24. Identify all of the elements of the Galois group of $x^p-2$ for $p$ an odd prime (note: this has a complicated presentation).
25. Classify the five groups of order 12.
25. Classify the four groups of order 28.
26. Show if $G$ is finite, then $G$ is solvable $\iff$ all of its composition factors are of prime order.
27. Show that if $N$ and $G/N$ are solvable, then $G$ is solvable.
28. Show that $S_n$ is generated by disjoint cycles.
28. Show that $S_n$ is generated by transpositions.
29. Show that an $m\dash$cycle is an odd permutation iff $m$ is an even number.
30. Show that a permutation is odd iff it has an odd number of even cycles.
31. Prove Burnside's theorem.
32. 

## Modules and Linear Algebra

1. Prove the Cayley-Hamilton theorem.
2. Prove that the minimal polynomial divides the characteristic polynomial.
3. Prove that the cokernel of $A\in \mat(n\times n, \ZZ)$ is finite $\iff \det A \neq 0$, and show that in this case $\abs{\coker(A)} = \abs{\det(A)}$.
4. Show that a nilpotent operator is diagonalizable.
5. Show that if $A,B$ are diagonalizable and $[A, B] = 0$ then $A,B$ are simultaneously diagonalizable.
6. Does diagonalizable imply invertible? The converse?

## Commutative Algebra

1. Show that a finitely generated module over a Noetherian local ring is flat iff it is free using Nakayama and Tor.
