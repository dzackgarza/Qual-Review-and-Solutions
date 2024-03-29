# UGA Fall 2019 Problem Sets

## Problem Set One

### Exercises

:::{.problem title="Hungerford 1.6.3"}
If $\sigma = (i_1 i_2 \cdots i_r) \in S_n$ and $\tau \in S_n$, then show
that $\tau\sigma\tau^{-1} = (\tau(i_1) \tau(i_2) \cdots \tau(i_r))$.
:::

:::{.problem title="Hungerford 1.6.4"}
Show that $S_n \cong \left\langle (12), (123\cdots n)\right\rangle$ and also that
$S_n \cong \left\langle (12), (23\cdots n)\right\rangle$
:::

:::{.problem title="Hungerford 2.2.1"}
Let $G$ be a finite abelian group that is not cyclic. Show that $G$ contains a subgroup isomorphic to
$\mathbb{Z}_p \oplus \mathbb{Z}_p$ for some prime $p$.
:::

:::{.problem title="Hungerford 2.2.12.b."} 
Determine (up to isomorphism) all abelian groups of order 64; do the same for order 96.
:::

:::{.problem title="Hungerford 2.4.1"}
Let $G$ be a group and $A \trianglelefteq G$ be a normal abelian subgroup. Show that $G/A$ acts
on $A$ by conjugation and construct a homomorphism
$\varphi: G/A \to \mathrm{Aut}(A)$.
:::

:::{.problem title="Hungerford 2.4.9)."} 
Let $Z(G)$ be the center of $G$. 
Show that if $G/Z(G)$ is cyclic, then $G$ is abelian.

> Note that Hungerford uses the notation $C(G)$ for the center.

:::

:::{.problem title="Hungerford 2.5.6"}
Let $G$ be a finite group and$H \trianglelefteq G$ a normal subgroup of order $p^k$. Show that $H$ is
contained in every Sylow $p$-subgroup of $G$.
:::

:::{.problem title="Hungerford 2.5.9"}
Let $\left| G \right| = p^n q$ for some primes $p > q$. Show that $G$ contains a unique normal subgroup of
index $q$.
:::

### Qual Problems

:::{.problem}
Let $G$ be a finite group and $p$ a prime number. Let
$X_p$ be the set of Sylow-$p$ subgroups of $G$ and $n_p$ be the
cardinality of $X_p$. Let $\mathrm{Sym}(X)$ be the permutation group on
the set $X_p$.

1.  Construct a homomorphism $\rho: G \to \mathrm{Sym}(X_p)$ with image
    a transitive subgroup (i.e. with a single orbit).

2.  Deduce that if $G$ is simple then the order of $G$ divides $n_p!$.

3.  Show that for any $1\leq a \leq 4$ and any prime power $p^k$, no
    group of order $ap^k$ is simple.
:::

:::{.solution}
\envlist

1.  Define the required group action by $$\begin{aligned}
            \rho: G \to \mathrm{Sym}(X_p) \\
            g \mapsto (\gamma_g: P \mapsto gPg^{-1}).
        \end{aligned}$$ The claim is that this action is transitive on
    $X_p$. This can be equivalently stated as
    $$\forall P \in X_p, \exists g \in G, P' \in X_p \mid gP'g^{-1} = P.$$

    However, by Sylow 2, all Sylow $p-$subgroups are conjugate to each
    other, and thus this condition is satisfied.

2.  Suppose that $G$ is simple, so that we have
    $$H \trianglelefteq G \implies H = \{ e \} \text{ or } H = G.$$

    Note that $\mathrm{Sym}(X_p) = (n_p)!$, and if we have an injective
    homomorphism $G \xrightarrow{\phi} \mathrm{Sym}(X_p)$, then
    $|G| = |\phi(G)|$, since $\phi(G) \leq \mathrm{Sym}(X_p)$ will be a
    subgroup and thus have order dividing $(n_p)!$, which proves the
    statement.

    Using the $\phi$ defined in (1), we can apply the first isomorphism
    theorem
    $$G / \ker \phi \cong \mathrm{im} \phi \leq \mathrm{Sym}(X_p),$$ and
    so it suffices to show that $\ker \phi = \{e\}$.

    Note that since $\ker \phi \trianglelefteq G$ and $G$ is simple, we
    can only have $\ker \phi = \{e\}$ or $\ker \phi = G$.

    Towards a contradiction, suppose $\ker \phi = G$.

    By definition, we have $$\begin{aligned}
        \ker \phi &= \{ g\in G \mid \gamma_g = \mathrm{id}_{X_p} \} \\
        &= \{ g\in G \mid \forall P \in X_p,~ gPg^{-1} = P \} \\
        &= \bigcap_{P \in X_p} N_G(P),
        \end{aligned}$$

    and so the kernel of $\varphi$ is the intersection of all of the
    normalizers of the Sylow $p-$subgroups.

    But this means that $N_G(P) = G$ for every Sylow $p-$subgroup, which
    means that $n_p = 1$ and there is a unique $P$ which must be normal
    in $G$. Since $G$ is simple, this forces $P$ to be trivial or the
    whole group.

    Towards a contradiction, suppose $P = G$. Then $G$ is a $p-$group
    and thus has order $p^n$. But then $G$ has normal subgroups of order
    $p^k$ for all $0 < k < n$, contradicting the simplicity of $G$.

    But the only other option is that $P$ is trivial, whereas we know
    nontrivial Sylow $p-$subgroups exist by Sylow 1.

    Thus we can not have $\ker \phi = G$, and so $\ker \phi$ is trivial
    as desired.

3.  Suppose $\left| G \right| = ap^k$, where $1 \leq a \leq 4$. Then by
    Sylow 3, we have $n_p = 1 \mod p$ and $n_p$ divides $a$. If $a=1$,
    then $n_p = 1$, and so $G$ can not be simple. Moreover, if
    $p \geq a$, then $n_p \leq a$ and $n_p = 1\mod p$ forces $n_p = 1$
    again.

    So we can restrict our attention to $2 \leq a \leq 4$ and
    $p = 2, 3$, which reduces to checking the cases
    $ap^k = 2 (3^k), 4 (3^k)$, or $3 (2^k)$ for $k\geq 1$.

    If $ap^k = 2(3^k)$, we have $n_3 = 1 \mod 3$ and $n_3 \divides 2$,
    which forces $n_3 = 1$, so this can not be a simple group.

    Similarly, if $ap^k = 4(3^k)$, then $n_3 = 1 \mod 3$ and $n_3$
    divides 4, which forces $n_3 = 1$ and thus $G$ can't be simple.

    If $ap^k = 3(2^k)$, then $n_2 = 1 \mod 2$ and $n_2$ divides 3, so
    $n_2 = 1, 3$. But then $n_3! = 6$, and if $k > 1$, we have
    $3(2^k) > 6 = n_3!$, so $G$ can not be simple by the result in (2).

    If $k = 1$, then $G$ is order 6, so $G$ is isomorphic to either
    $\ZZ_6$ or $S_3$. The group $S_3$ is not simple, since
    $A_3 \trianglelefteq S_3$, and the only simple cyclic groups are of
    prime order, so $\ZZ_6$ is not simple. This exhausts all of the
    possible cases. 

:::

:::{.problem}
Let $G$ be a finite group and let $N \trianglelefteq G$,
and let $p$ be a prime number and $Q$ a subgroup of $G$ such that
$N \subset Q$ and $Q/N$ is a Sylow $p-$subgroup of $G/N$.

1.  Prove that $Q$ contains a Sylow $p-$subgroup of $G$.

2.  Prove that every Sylow $p-$subgroup of $G/N$ is the image of a Sylow
    $p-$subgroup of $G$.
:::

:::{.solution}
*Proof.*

1.  Since $Q/N$ is a Sylow $p-$subgroup of $G/N$, we can write
    $|G/N| = p^k l$ where $\gcd(p, l) = 1$, and $|Q/N| = p^k$.

    We can then write $|G| = p^n m$ where $n\geq l$ and $l\mid m$.

    By the third isomorphism theorem, we have
    $$\frac{G/N}{Q/N} \cong G/Q$$ and so
    $$\left| \frac{G/N}{Q/N} \right| = \frac{|G/N|}{|Q/N|} = \frac{p^k l}{p^k} = l$$

    and so $|G/Q| = l$ where $(p, l) = 1$, and thus
    $$|G/Q| = |G| / |Q| = l \implies |G| = |Q|~l.$$

    We then have $$p^n m = |Q|~l,$$

    and since $(p, l) = 1$, it must be the case that $p^n$ divides
    $|Q|$. But since $Q \leq G$, this means that $Q$ itself must be a
    Sylow $p-$ subgroup of $G$.

2.  Let $P_N \in \mathrm{Syl}(p, G/N)$. By the subgroup correspondence
    theorem, $P_n = H/N$ for some $H\leq G$ such that $N \subseteq H$.

    So choose $P_H \in \mathrm{Syl}(p, H)$; the claim is that
    $P_H \in \mathrm{Syl}(p, G)$ and that $\frac{P_HN}{N} \cong P_N$,
    which exhibits $P_N$ as the image of a Sylow $p-$subgroup of $G$.

    We first have $P_H \in \mathrm{Syl}(p, G)$, which follows because we
    have $[G/N, H/N] = [G: P_H]$ from the fourth isomorphism theorem,
    and thus $[G/N, P_N] = [G : P_H]$. In particular, since $P_N$ is a
    Sylow $p-$subgroup, $p$ does not divide $[G/N, P_N]$ and thus $p$
    doesn't divide $[G: P_H]$, which makes $P_H$ a maximal $p-$subgroup
    in $G$ and thus a Sylow $p-$subgroup.

    We then have $P_HN/N = P_N$, which follows because
    $P_H \leq H \implies P_HN/N \leq H/N = P_N \leq G/N$.

    However, it is also the case that $P_HN/N \in \mathrm{Syl}(p, G/N)$.
    This follows because

    1.  $P_HN/N = P_H/P_H \cap N$ by the 2nd isomorphism theorem, so it
        is a $p-$group.

    2.  $P_H \subseteq P_HN \subseteq G \implies p$ doesn't divide
        $[G: P_HN]$, since $P_H$ is also a Sylow $p-$group of $G$ and
        thus has maximal prime power dividing $\left| G \right|$.

    3.  $N \subseteq P_H N \subseteq G \implies [G/N : P_H N/ N] = [G: P_H N]$

    Taken together, this says that $P_H N/ N$ is a $p$-group and $p$
    doesn't divide $[G/N, P_HN / N]$, so it is a maximal $p-$subgroup
    and $P_HN/N \in \mathrm{Syl}(p, G/N)$.

    But since $P_HN/N \leq P_N$ and
    $\left|P_HN/N\right| = \left|P_N\right|$, we must have
    $P_HN/N = P_N$ as desired.

 ◻
:::

:::{.problem}
Let $G$ be a finite group and $H<G$ a subgroup. Let
$n_H$ be the number of subgroups of $G$ that are conjugate to $H$. Show
that $n_H$ divides the order of $G$.
:::

:::{.solution}
.* Let $$C_H = \{ gHg^{-1} \mid g\in G \}$$ be the conjugacy class
of $H$, so $|C_H| = n_H$.

We wish to show that $n_{H}$ divides $|G|$.

**Claim 1**: $$n_{H} = [G: N_G(H)],$$ where $N_G(H) \leq G$ is the
normalizer of $H$ in $G$.

Note that if this claim is true, then we can apply Lagrange's theorem,
which states $$A \leq G \implies |G| = [A: G]~|A|,$$

which in this case translates to
$$|G| = [N_G(H) : G]~|N_G(H)| = n_H~|N_G(H)|.$$

Since $n_H$ divides the right-hand side, it must divide the left-hand
side as well, which is precisely what we would like to show.

**Proof of Claim 1**:

The normalizer of $H$ in $G$, written $N_G(H)$, is the largest subgroup
of $G$ containing $H$ such that $H \trianglelefteq N_G(H)$, i.e.
$$N_G(H) = \{g \in G ~\mid~ gHg^{-1} = H \} \leq G.$$

Now consider $S$, the set of left cosets of $N_G(H)$. Suppose there are
$k$ of them, so $$[G: N_G(H)] = |S| \coloneqq k.$$

Then $S$ can be written as
$$S = \{ g_1 N_G(H), ~g_2 N_G(H), ~\cdots, ~g_k N_G(H) \}.$$

where each $g_i$ is a distinct element of $G$ yielding a distinct coset
$g_i N_G(H)$. In particular, if $i\neq j$, then $g_i \neq g_j$, and
$g_i N_G(H) \not \in g_j N_G(H)$.

In particular, $S$ acts on $C_H$, $$\begin{aligned}
S &\curvearrowright C_H \\
g_i N_G(H) &\curvearrowright H = g_i H g_i^{-1},\end{aligned}$$

taking $H$ to one of its conjugate subgroups.

So define $$K \coloneqq 
\{ g_i H g_i^{-1} \mid 1 \leq i \leq k \}.$$

Note that $K \subseteq C_H$, and has at most $k$ elements.

We claim that $K$ has $k$ *distinct* elements, i.e. that each $g_{i}$
takes $H$ to a *distinct* conjugate subgroup. We have $$\begin{aligned}
g_{i} H g^{-1}_{i} 
    &= g_{j} H g^{-1}_{j} &\implies \\
g_j^{-1} g_{i} H g^{-1}_{i} g_j 
    &= H &\implies \\
(g_j^{-1} g_{i}) H (g_j^{-1} g_{i})^{-1} 
    &= H &\implies \\
g_j^{-1} g_{i} &\in N_G(H) &\implies \\
g_i &\in g_j N_G(H) &\implies \\
g_i &= g_j,\end{aligned}$$

where the last line follows because we assumed that each coset contains
at most one $g_i$.

Thus $K$ has $k$ distinct elements, and so
$$= k = |K| \leq |C_H| = n_H.$$

We now claim that $k \geq n_H$ as well.

Let $H' \in C_H$ be any subgroup conjugate to $H$, so $H' = gHg^{-1}$
for some $g\in G$. Then $g = g_i$ for some $i$, so $g \in g_{i} N_G(H)$.

Thus $g = g_{i} n$ for some $n\in N_G(H)$, but
$n\in N_G(H) \iff nHn^{-1} = H$ by definition, and so we have
$$\begin{aligned}
    H' 
    &= gHg^{-1} \\
    &= (g_i n) H (g_i n)^{-1} \\
    &= g_i (n H n^{-1}) g_i^{-1} \\
    &= g_i H g_i^{-1} \in K.\end{aligned}$$

Since $H' \in C_H$ was an arbitrary subgroup conjugate to $H$, this says
that $C_H \subseteq K$ and thus $$n_H = |C_H| \leq |K| = k$$

Thus $$[G: N_G(H)] = k = |M| = |K| = n_H,$$ which is what we wanted to
show. ◻
:::

:::{.problem}
Let $G=S_5$, the symmetric group on 5 elements. Identify
all conjugacy classes of elements in $G$, provide a representative from
each class, and prove that this list is complete.
:::

:::{.solution}


:::{.claim title="1"}
Conjugacy classes in $S_n$ are completely
determined by cycle type.
:::

This follows because of the result on homework 1, which says that for
any two cycles $\tau,\sigma\in S_n$, we have
$$\tau(s_1~s_2~\cdots~s_k)\tau^{-1} = (\tau(s^1)~\tau(s^2)~\cdots~\tau(s_k)).$$

In particular, this shows that the cycle type of a single cycle is
invariant under conjugation. If an element $\sigma \in S_n$ is comprised
of multiple cycles, say $\sigma = \sigma_1 \cdots \sigma_\ell$, then
$$\tau(\sigma)\tau^{-1} = \tau(\sigma_1 \cdots \sigma_\ell)\tau^{-1} 
= (\tau\sigma_1\tau^{-1})\cdots(\tau\sigma_\ell\tau^{-1}),$$

which shows that the entire cycle type is preserved under conjugation.
So each conjugacy class has exactly one cycle type, and distinct classes
have distinct cycle types, so this completely determines the conjugacy
classes.

**Claim 2:** Cycle types in $S_n$ are in bijective correspondence with
integer partitions of $n$.

This follows because any integer partition of $n$ can be used to obtain
a canonical representative of a conjugacy class of $S_n$: if
$n = a_1 + a_2 + \cdots a_n$, we simply take a cycle of length $a_1$ the
first $a_1$ integers in order, a cycle of length $a_2$ containing the
integers $a_1 + 1$ to $a_2$ in order, and so on.

Conversely, any permutation can be written as a product of disjoint
cycles, and when the cycles for fixed points are added in, every integer
between 1 and $n$ will appear, and the sum of the lengths of all cycles
must sum to $n$. Thus taking the cycle lengths yields an integer
partition of $n$.

All integer partitions of 5 are given below, along with a canonical
representative of the associated conjugacy class. $$\begin{aligned}
    5 && (1~2~3~4~5) \\
    4 + 1 && (1~2~3~4)(5) \\
    3 + 2 &&  (1~2~3)(4~5) \\
    3 + 1 + 1 && (1~2~3)(4)(5) \\
    2 + 2 + 1 && (1~2)(3~4)(5) \\
    2 + 1 + 1 + 1 && (1~2)(3)(4)(5) \\
    1 + 1 + 1 + 1 + 1 && (1)(2)(3)(4)(5) \\\end{aligned}$$ ◻
:::

## Problem Set Two

### Exercises

:::{.problem title="Hungerford 2.1.9"}
Let $G$ be a finitely generated abelian group in which no element (except 0) has finite order. Show that
$G$ is a free abelian group.
:::

:::{.problem title="Hungerford 2.1.10"}
\envlist

1.  Show that the additive group of rationals $\mathbb Q$ is not
    finitely generated.

2.  Show that $\mathbb Q$ is not free.

3.  Conclude that Exercise 9 is false if the hypothesis "finitely
    generated" is omitted.
:::

:::{.problem title="Hungerford 2.5.8"}
Show that if every Sylow $p-$subgroup of a finite group $G$ is normal for every prime $p$, then $G$ is the
direct product of its Sylow subgroups.
:::

:::{.problem title="Hungerford 2.6.4"}
What is the center of the quaternion group $Q_8$? Show that $Q_8/Z(Q_8)$ is abelian.
:::

:::{.problem title="Hungerford 2.6.9"}
Classify up to isomorphism all groups of order 18. Do the same for orders 20 and 30.
:::

:::{.problem title="Hungerford 1.9.1"}
Show that every non-identity element in a free group $F$ has infinite order.
:::

:::{.problem title="Hungerford 1.9.3"}
Let $F$ be a free group and for a fixed integer $n$, let $H_n$ be the subgroup generated by the set
$\{ x^n \mid x \in F \}$. Show that $H_n \trianglelefteq F$.
:::

### Qual Problems

:::{.problem}
List all groups of order 14 up to isomorphism.
:::

:::{.problem}
Let $G$ be a group of order $p^3$ for some prime $p$.
Show that either $G$ is abelian, or $\left| Z(G) \right| = p$.
:::

:::{.problem}
Let $p,q$ be distinct primes, and let $k$ denote the
smallest positive integer such that $p$ divides $q^k - 1$. Show that no
group of order $pq^k$ is simple.
:::

:::{.problem}
Show that $S_4$ is a solvable, nonabelian group.
:::

## Problem Set Three

### Exercises

:::{.problem title="Hungerford 2.7.10"}
Show that $S_n$ is solvable for$n\leq 4$ but $S_3$ and $S_4$ are not nilpotent.
:::

:::{.problem title="Hungerford 2.8.3"}
Show that if $N$ is a simple normal subgroup of a group $G$ and $G/N$ has a composition series, then $G$ has
a composition series.
:::

:::{.problem title="Hungerford 2.8.9"}
Show that any group of order $p^2 q$(for primes $p,q$) is solvable.
:::

:::{.problem title="Hungerford 5.1.1"}
Let $F/K$ be a field extension. 
Show that

1.  $[F: K] = 1$ iff $F = K$.

2.  If $[F: K]$ is prime, then there are no intermediate fields between
    $F$ and $K$.

3.  If $u\in F$ has degree $n$ over $K$, then $n$ divides $[F: K]$.

:::

:::{.problem title="Hungerford 5.1.8"}
Show that if $u\in F$ is algebraic of odd degree over $K$, then so is $u^2$, and moreover $K(u) = K(u^2)$.
:::

:::{.problem title="Hungerford 5.1.14"}
\envlist


1.  If $F = \mathbb{Q}(\sqrt 2, \sqrt 3)$, compute $[F: \mathbb{Q}]$ and
    find a basis of $F/\mathbb{Q}$.

2.  Do the same for $\mathbb{Q}(i, \sqrt 3, \zeta_3)$ where $\zeta_3$ is
    a complex third root of 1.

:::

:::{.problem title="Hungerford 5.1.16"}
Show that in $\mathbb{C}$, the fields $\mathbb{Q}(i) \cong \mathbb{Q}(\sqrt 2)$ as vector spaces, but
not as fields. 
:::

### Qual Problems

:::{.problem}
Let $R$ and $S$ be commutative rings with multiplicative
identity.

1.  Prove that when $R$ is a field, every non-zero ring homomorphism
    $\phi: R\to S$ is injective.

2.  Does (a) still hold if we only assume that $R$ is a domain? If so,
    prove it, and if not provide a counterexample.
:::

:::{.problem}
Determine for which integers the ring
$\mathbb{Z}/n\mathbb{Z}$ is a direct sum of fields. Carefully prove your
answer.
:::

:::{.problem}
Suppose that $R$ is a commutative ring. Show that an
element $r\in R$ is not invertible iff it is contained in a maximal
ideal.
:::

:::{.problem}
\envlist


1.  Give the definition that a group $G$ must satisfy the be solvable.

2.  Show that every group $G$ of order 36 is solvable.

> Hint: You may assume that $S^4$ is solvable.

:::

## Problem Set Four

### Exercises

:::{.problem title="Hungerford 5.3.7"}
If $F$ is algebraically closed and$E$ is the set of all elements in $F$ that are algebraic over a field
$K$, then $E$ is an algebraic closure of $K$.
:::

:::{.problem title="Hungerford 5.3.8"}
Show that no finite field is algebraically closed.

*Hint: if $K = \{a_i\}_{i=0}^n$, consider*
\[ 
f(x) = a_1 + \prod_{i=0}^n (x - a_i) \in K[x]
\] 
*where $a_1 \neq 0$.*

:::

:::{.problem title="Hungerford 5.5.2"}
Show that if $p\in\mathbb Z$ is prime, then $a^p = a$ for all $a\in\mathbb Z_p$, or equivalently
$c^p \equiv c \mod p$ for all $c\in\mathbb Z$.
:::

:::{.problem title="Hungerford 5.5.3"}
Show that if $|K| = p^n$, then every element of $K$ has a unique $p$th root in $K$.
:::

:::{.problem title="Hungerford 5.5.10"}
Show that every element in a finite field can be written as the sum of two squares.
:::

:::{.problem title="Hungerford 5.6.1"}
Let $F/K$ be a field extension. Let $\mathrm{char} K = p \neq 0$ and let $n\geq 1$ be an integer such that
$(p, n) = 1$. If $v\in F$ and $nv \in K$, then $v\in K$.
:::

:::{.problem title="Hungerford 5.6.8"}
If $\mathrm{char} K = p \neq 0$ and $[F: K]$ is finite and not divisible by $p$, then $F$ is separable over $K$.
:::

### Qual Problems

:::{.problem}
Suppose that $\alpha$ is a root in $\mathbb C$ of
$P(x) = x^{17} - 2$. How many field homomorphisms are there from
$\mathbb Q (\alpha)$ to:

1.  $\mathbb C$,

2.  $\mathbb R$,

3.  $\overline{\mathbb Q}$, the algebraic closure of $\mathbb Q$?
:::

:::{.problem}
Let $C/F$ be an algebraic field extension. Prove that
the following are equivalent:

1.  Every non-constant polynomial $f\in F[x]$ factors into linear
    factors over $C[x]$.

2.  For every (not necessarily finite) algebraic extension $E/F$, there
    is a ring homomorphism $\alpha: E \to C$ such that $\alpha \mid_F$
    is the identity on $F$.

*Hint: use Zorn's Lemma.*

:::

:::{.problem}
Let $R$ be a commutative ring containing a field $k$,
and suppose that $\dim_k R < \infty$. Let $\alpha \in R$.

1.  Show that there exist $n\in \mathbb N$ and
    $\{ c_0, c_1, \cdots c_{n-1}\} \subseteq k$ such that
    $$a^n + c_{n-1}a^{n-1} + \cdots + c_1 a + c_0 = 0.$$

2.  Suppose that (a) holds and show that if $c_0 \neq 0$ then $a$ is a
    unit in $R$.

3.  Suppose that (a) holds and show that if $a$ is not a zero divisor in
    $R$, then $a$ is invertible.
:::

## Problem Set Five

### Exercises

:::{.problem title="Hungerford 5.3.5"}
Show that if $f\in K[x]$ has degree $n$ and $F$ is a splitting field of $f$ over $K$, the $[F: K]$ divides
$n!$.
:::

:::{.problem title="Hungerford 5.3.12"}
Let $E$ be an intermediate field extension in $K \leq E \leq F$.

1.  Show that if $u\in F$ is separable over over $K$, then $u$ is
    separable over $E$.

2.  Show that if $F$ is separable over $K$, then $F$ is separable over
    $E$ and $E$ is separable over $K$.
:::

:::{.problem title="Hungerford 5.3.13"}
Show that if $[F: K] < \infty$, then the following conditions are equivalent:

1.  $F$ is Galois over $K$

2.  $F$ is separable over $K$ and $F$ is a splitting field of some
    polynomial $f\in K[x]$.

3.  $F$ is a splitting field over $K$ of some polynomial $f\in K[x]$
    whose irreducible factors are separable.
:::

:::{.problem title="Hungerford 5.4.1"}
Suppose that $f\in K[x]$ splits in$F$ as $$f = \prod_{i=1}^k (x-u_i)^{n_i}$$ with the $u_i$ distinct and
each $n_i \geq 1$. Let
$$g(x) = \prod_{i=1}^k (x-u_i) = \sum_{i=1}^k v_i x^i$$

and let $E  = K(\{v_i\}_{i=1}^k)$. Then show that the following hold:

1.  $F$ is a splitting field of $g$ over $E$.

2.  $F$ is Galois over $E$.

3.  $\mathrm{Aut}_E(F) = \mathrm{Aut}_K(F)$.
:::

:::{.problem title="Hungerford 5.4.10 a/g/h"}
Determine the Galois groups of the following polynomials over the corresponding fields:

1.  $x^4- 5$ over $\mathbb Q, \mathbb Q(\sqrt 5), \mathbb Q(i\sqrt 5)$.

2.  $x^3 - 2$ over $\mathbb Q$.

3.  $(x^3-2)(x^2-5)$ over $\mathbb Q$.
:::

:::{.problem title="Hungerford 5.6.11"}
If $f \in K[x]$ is irreducible of degree $m > 0$ and $\mathrm{char}(K)$ does not divide $m$, then $f$ is
separable.
:::

### Qual Problems

:::{.problem}
Let $E/F$ be a Galois field extension, and let $K/F$ be
an intermediate field of $E/F$. Show that $K$ is normal over $F$ iff
$\mathrm{Gal}(E/K) \trianglelefteq \mathrm{Gal}(E/F)$.
:::

:::{.problem}
Let $F \subset L$ be fields such that $L/F$ is a Galois
field extension with Galois group equal to
$D_8 = \left< \sigma,\tau \mid \sigma^4 = \tau^2 = 1,~ \sigma\tau = \tau \sigma^3 \right>$.
Show that there are fields $F \subset E \subset K \subset L$ such that
$E/F$ and $K/E$ are Galois field extensions, but $K/F$ is not Galois.
:::

:::{.problem}
Let $f(x) = x^3 - 7$.

1.  Let $K$ be the splitting field for $f$ over $\mathbb Q$. Describe
    the Galois group of $K / \mathbb Q$ and the intermediate fields
    between $\mathbb Q$ and $K$. Which intermediate fields are not
    Galois over $\mathbb Q$?

2.  Let $L$ be the splitting field for $f$ over $\mathbb R$. What is the
    Galois group $L/ \mathbb R$?

3.  Let $M$ be the splitting field for $f$ over $\mathbb F_{13}$, the
    field with 13 elements. What is the Galois group of
    $M / \mathbb F_{13}$?
:::

## Problem Set Six

### Exercises

:::{.problem title="Hungerford 5.4.11"}
Determine all subgroups of the Galois group and all intermediate fields of the splitting (over
$\mathbb{Q}$) of the polynomial $(x^{3}-2)(x^{2}-3)\in \mathbb{Q}[x]$.
:::

:::{.problem title="Hungerford 5.4.12"}
Let $K$ be a subfield of$\mathbb{R}$ and let $f \in K[x]$ be an irreducible quartic. If $f$ has
exactly 2 real roots, the Galois group of $f$ is either $S_{4}$ or
$D_{4}$.
:::

:::{.problem title="Hungerford 5.8.3"}
Let $\phi$ be the Euler function.

1.  $\phi(n)$ is even for $n>2$.

2.  find all $n>0$ such that $\phi(n)=2$.
:::

:::{.problem title="Hungerford 5.8.9"}
If $n>2$ and $\zeta$ is a primitive $n$th root of unity over $\mathbb{Q}$, then
$[\mathbb{Q}(\zeta + \zeta^{-1}): \mathbb{Q}]=\phi(n)/2.$
:::

:::{.problem title="Hungerford 5.9.1"}
If $F$ is a radical extension field of $K$ and $E$ is an intermediate field, then $F$ is a radical extension
of $E$.
:::

:::{.problem title="Hungerford 5.9.3"}
Let $K$ be a field, $f\in K[x]$ an irreducible polynomial of degree $n\geq 5$ and $F$ a splitting field of
$f$ over $K$. Assume that $Aut_{k}(F)\simeq S_{n}$. Let $u$ be a root of
$f$ in $F$. Then,

1.  $K(u)$ is not Galois over $K$; $[K(u):K]=n$ and $Aut_{K}(K(u))=1$
    (and hence solvable).

2.  Every normal closure over $K$ that contains $u$ also contains an
    isomorphic copy of $F$.

3.  There is no radical extension field $E$ of $K$ such that
    $K\subset K(u)\subset E$.
:::

### Qual Problems

:::{.problem}
\envlist

1.  Let $K$ be a field. State the main theorem of Galois theory for a
    finite field extension L/K

2.  Let $\zeta_{43} := e^{2\pi i /43}$. Describe the group of all field
    automorphisms
    $\sigma : \mathbb{Q} (\zeta_{43})\rightarrow \mathbb{Q} (\zeta_{43})$.

3.  How many proper subfields are there in the field
    $\mathbb{Q} (\zeta_{43})$?
:::

:::{.problem}
Let $F$ be a field and let $f(x)\in F[x]$.

1.  Define what is a splitting field of $f(x)$ over $F$.

2.  Let $F$ be a finite field with $q$ elements. Let $E/F$ be a finite
    extension of degree $n>0$. Exhibit an explicit polynomial
    $g(x)\in F[x]$ such that $E/F$ is a splitting of $g(x)$ over $F$.
    Fully justify your answer.

3.  Show that the extension $E/F$ in (2) is a Galois extension.
:::

:::{.problem}
Let $K \subset L \subset M$ be a tower of finite degree
field extensions. In each of the following parts, either prove the
assertion or give a counterexample (with justification).

1.  If $M/K$ is Galois, then $L/K$ is Galois

2.  If $M/K$ is Galois, then $M/L$ is Galois.
:::

## Problem Set Seven

### Exercises

:::{.problem title="Hungerford 4.1.3"}
Let $I$ be a left ideal of a ring$R$, and let $A$ be an $R-$module.

1.  Show that if $S$ is a nonempty subset of $A$, then
  \[
  IS \coloneqq \left\{ \sum_{i=1}^n r_i a_i \mid n\in \mathbb{N}^*; r_i \in I; a_i \in S \right\}
  \]
    is a submodule of $A$.

  > Note that if $S = \{a\}$, then $IS = Ia = \{ra \mid r\in I\}$.

2.  If $I$ is a two-sided ideal, then $A/IA$ is an $R/I$ module with the
    action of $R/I$ given by $$(r+I)(a+IA) = ra + IA.$$
:::

:::{.problem title="Hungerford 4.1.5"}
If $R$ has an identity, then a nonzero unitary $R\dash$module is **simple** if its only submodules are $0$
and $A$.

1.  Show that every simple $R-$module is cyclic.

2.  If $A$ is simple, every $R-$module endomorphism is either the zero
    map or an isomorphism.
:::

:::{.problem title="Hungerford 4.1.7"}
\envlist


1.  Show that if $A,B$ are $R$-modules, then the set
    $\mathrm{Hom}_R(A, B)$ is all $R$-module homomorphisms $A \to B$ is
    an abelian group with $f+g$ given on $a\in A$ by
    $$(f+g)(a) \coloneqq f(a) + g(a) \in B.$$

    Also show that the identity element is the zero map.

2.  Show that $\mathrm{Hom}_R(A, A)$ is a ring with identity, where
    multiplication is given by composition of functions.

    *Note that $\mathrm{Hom}_R(A, A)$ is called the **endomorphism
    ring** of A.*

3.  Show that $A$ is a left $\mathrm{Hom}_R(A, A)$-module with an action
    defined by
    $$a\in A, f\in \mathrm{Hom}_R(A, A) \implies f \curvearrowright a \coloneqq f(a).$$
:::

:::{.problem title="Hungerford 4.1.12"}
Let the following be a commutative diagram of $R$-modules and $R$-module homomorphisms with exact rows:

Prove the following:

1.  If $\alpha_1$ is an epimorphisms and $\alpha_2, \alpha_4$ are
    monomorphisms then $\alpha_3$ is a monomorphism.

2.  If $\alpha_5$ is a monomorphism and $\alpha_2, \alpha_4$ are
    epimorphisms then $\alpha_3$ is an epimorphism.
:::

:::{.problem title="Hungerford 4.2.4"}
Let $R$ be a principal ideal domain,$A$ a unitary left $R$-module, and $p\in R$ a prime (and thus
irreducible) element. Define $$\begin{aligned}
    pA &\coloneqq \{ pa \mid a\in A\} \\
    A[p] &\coloneqq \{ a\in A \mid pa = 0\}.\end{aligned}$$

Show the following:

1.  $R/(p)$ is a field.

2.  $pA$ and $A[p]$ are submodules of $A$.

3.  $A/pA$ is a vector space over $R/(p)$, with
    $$(r + (p))(a + pA) = ra + pA.$$

4.  $A[p]$ is a vector space over $R/(p)$ with $$(r + (p))a = ra.$$
:::

:::{.problem title="Hungerford 4.2.8"}
If $V$ is a finite dimensional vector space and
$$V^m \coloneqq V \oplus V \oplus \cdots \oplus V \quad \text{($m$ summands)},$$
then for each $m\geq 1$, $V^m$ is finite dimensional and
$\dim V^m = m(\dim V)$.
:::

:::{.problem title="Hungerford 4.2.9"}
If $F_1, F_2$ are free modules of a ring with the invariant dimension property, then
$$\mathrm{rank}(F_1 \oplus F_2) = \mathrm{rank} F_1 + \mathrm{rank} F_2.$$
:::

### Qual Problems

:::{.problem}
Let $F$ be a field and let $f(x) \in F[x]$.

1.  State the definition of a splitting field of $f(x)$ over $F$.

2.  Let $F$ be a finite field with $q$ elements. Let $E/F$ be a finite
    extension of degree $n>0$. Exhibit an explicit polynomial
    $g(x) \in F[x]$ such that $E/F$ is a splitting field of $g$ over
    $F$. Fully justify your answer.

3.  Show that the extension in $(b)$ is a Galois extension.
:::

:::{.problem}
Let $R$ be a commutative ring and let $M$ be an
$R$-module. Recall that for $\mu \in M$, the *annihilator* of $\mu$ is
the set $$\mathrm{Ann}(\mu) = \{ r\in R \mid r\mu = 0\}.$$

Suppose that $I$ is an ideal in $R$ which is maximal with respect to the
property there exists a nonzero element $\mu \in M$ such that
$I = \mathrm{Ann}(\mu)$.

Prove that $I$ is a *prime* ideal in $R$.
:::

:::{.problem}
Suppose that $R$ is a principal ideal domain and
$I \trianglelefteq R$ is an ideal. If $a\in I$ is an irreducible
element, show that $I = Ra$.
:::

## Problem Set Eight

### Exercises

:::{.problem title="Hungerford 4.4.1"}
Show the following:

1.  For any abelian group $A$ and any positive integer $m$,
  \[
  \mathrm{Hom}(\mathbb{Z}_m, A) \cong A[m] \coloneqq \{ a\in A \mid ma = 0\}
  .\]

2.  $\mathrm{Hom}(\mathbb{Z}_m, \mathbb{Z}_n) \cong \mathbb{Z}_{\mathrm{gcd}(m,n)}$.

3.  As a $\mathbb{Z}-$module, $\mathbb{Z}_m^* = 0$.

4.  For each $k\geq 1$, $\mathbb{Z}_m$ is a $\mathbb{Z}_{mk}-$module,
    and as a $\mathbb{Z}_{mk}$ module,
    $\mathbb{Z}_m^* \cong \mathbb{Z}_m$.
:::

:::{.problem title="Hungerford 4.4.3"}
Let$\pi: \mathbb{Z} \to \mathbb{Z}_2$ be the canonical epimorphism. Show
that the induced map
$\overline{\pi}: \mathrm{Hom}(\mathbb Z_2, \mathbb Z) \to \mathrm{Hom}(\mathbb Z_2, \mathbb Z_2)$
is the zero map. Conclude that $\overline{\pi}$ is not an epimorphism.
:::

:::{.problem title="Hungerford 4.4.5"}
Let $R$ be a unital ring, show that there is a ring homomorphism $\mathrm{Hom}_R(R, R) \to R^{op}$ where
$\mathrm{Hom}_R$ denotes left $R-$module homomorphisms. Conclude that if
$R$ is commutative, then there is a ring isomorphism
$\mathrm{Hom}_R(R, R) \cong R$.
:::

:::{.problem title="Hungerford 4.4.9"}
Show that for any homomorphism$f: A \to B$ of left $R-$modules the following diagram is commutative:

where $\theta_A, \theta_B$ are as in Theorem 4.12 and $f^*$ is the map
induced on $A^{**} \coloneqq \mathrm{Hom}_R(\mathrm{Hom}(A, R), R)$ by
the map $$\overline f: \mathrm{Hom}(B, R) \to \mathrm{Hom}_R(A, R).$$
:::

:::{.problem title="Hungerford 4.6.2"}
Show that every free module over a unital integral domain is torsion-free. Show that the converse is false.
:::

:::{.problem title="Hungerford 4.6.3"}
Let $A$ be a cyclic $R-$module of order $r \in R$.

1.  Show that if $s$ is relatively prime to $r$, then $sA = A$ and
    $A[s] = 0$.

2.  If $s$ divides $r$, so $sk = r$, then $sA \cong R/(k)$ and
    $A[s] \cong R/(s)$.
:::

:::{.problem title="Hungerford 4.6.6"}
Let $A, B$ be cyclic modules over $R$of nonzero orders $r,s$ respectively, where $r$ is *not* relatively
prime to $s$. Show that the invariant factors of $A \oplus B$ are
$\mathrm{gcd}(r, s)$ and $\mathrm{lcm}(r, s)$.
:::

### Qual Problems

:::{.problem}
Let $R$ be a PID. Let $n > 0$ and $A \in M_n(R)$ be a
square $n\times n$ matrix with coefficients in $R$.

Consider the $R$-module $M \coloneqq R^n / \mathrm{im}(A)$.

1.  Give a necessary and sufficient condition for $M$ to be a torsion
    module (i.e. every nonzero element is torsion). Justify your answer.

2.  Let $F$ be a field and now let $R \coloneqq F[x]$. Give an example
    of an integer $n>0$ and an $n \times n$ square matrix $A \in M_n(R)$
    such that $M \coloneqq R^n/\mathrm{im}(A)$ is isomorphic as an
    $R-$module to $R \times F$.
:::

:::{.problem}
\envlist


1.  State the structure theorem for finitely generated modules over a
    PID.

2.  Find the decomposition of the $\mathbb{Z}-$module $M$ generated by
    $w,x,y,z$ satisfying the relations $$\begin{aligned}
            3w + 12y + 3x + 6z &=0 \\
            6y &= 0 \\
            -3w -3x + 6y &= 0.
        \end{aligned}$$
:::

:::{.problem}
Let $R$ be a commutative ring and $M$ an $R-$module.

1.  Define what a torsion element of $M$ is .

2.  Given an example of a ring $R$ and a cyclic $R-$module $M$ such that
    $M$ is infinite and $M$ contains a nontrivial torsion element $m$.
    Justify why $m$ is torsion.

3.  Show that if $R$ is a domain, then the subset of elements of $M$
    that are torsion is an $R-$submodule of $M$. Clearly show where the
    hypothesis that $R$ is a domain is used.
:::

## Problem Set Nine

### Exercises

:::{.problem title="Hungerford 7.1.3"}
\envlist


1.  Show that the center of the ring $M_n(R)$ consists of matrices of
    the form $rI_n$ where $r$ is in the center of $R$.

    *Hint: Every such matrix must commute with $\epsilon_{ij}$, the matrix with $1_R$ in the $i,j$ position and zeros elsewhere.*

2.  Show that $Z(M_n(R)) \cong Z(R)$.
:::

:::{.problem title="Hungerford 7.1.5"}
\envlist


1.  Show that if $A, B$ are (skew)-symmetric then $A+B$ is
    (skew)-symmetric.

2.  Let $R$ be commutative. Show that if $A,B$ are symmetric, then $AB$
    is symmetric $\iff AB=BA$. Also show that for any matrix
    $B \in M_n(R)$, both $BB^t$ and $B+B^t$ are always symmetric, and
    $B-B^t$ is always skew-symmetric.
:::

:::{.problem title="Hungerford 7.1.7"}
Show that similarity is an equivalence relation on $M_n(R)$, and \*equivalence\* is an equivalence
relation on $M_{m\times n}(R)$.
:::

:::{.problem title="Hungerford 7.2.2"}
Show that an $n\times m$ matrix $A$over a division ring $D$ has an $m\times n$ left inverse $B$ (so
$BA = I_m$) $\iff \mathrm{rank} A = m$. Similarly, show $A$ has a right
$m\times n$ inverse $\iff \mathrm{rank} A = n$.
:::

:::{.problem title="Hungerford 7.2.4"}
\envlist


1.  Show that a system of linear equations 
  \[
  a_{11} x_{1}+a_{12} x_{2} + &\cdots + a_{1 m} x_{m}=b_{1} \\ 
  & \vdots \\ 
  a_{n 1} x_{1}+a_{n 2} x_{2}+&\cdots+a_{n m} x_{m}=b_{n}
  \]
  has a simultaneous solution $\iff$ the corresponding matrix equation
  $AX = B$ has a solution, where
  $A = (a_{ij}), X = [x_1, \cdots, x_m]^t$, and
  $B = [b_1, \cdots , b_n]^t$.

2.  If $A_1, B_1$ are matrices obtained from $A, B$ respectively by
  performing the same sequence of elementary **row** operations, then
  $X$ is a solution of $AX=B$ $\iff$ $X$ is a solution of
  $A_1 X = B_1$.

3.  Let $C$ be the $n \times (m+1)$ matrix given by
\[
C = \left(\begin{array}{llll}{a_{11}} & {\cdots} & {a_{1 m}} & {b_{1}} \\ {} & {} & {} \\ {\cdot} & {} & {} \\ {a_{n 1}} & {\cdots} & {a_{n m}} & {b_{n}}\end{array}\right)
.\]
  Then $AX = B$ has a solution $\iff$
  $\mathrm{rank} A = \mathrm{rank} C$ and the solution is unique
  $\iff \mathrm{rank}(A) = m$.

  *Hint: use part 2.*

4.  If $B=0$, so the system $AX=B$ is homogeneous, then it has a
    nontrivial solution $\iff \mathrm{rank} A < m$ and in particular
    $n<m$.
:::

:::{.problem title="Hungerford 7.2.5"}
Let $R$ be a PID. For each positive integer $r$ and sequence of nonzero ideals
$I_1 \supset I_2 \supset \cdots \supset I_r$, choose a sequence
$d_i \in R$ such that $(d_i) = I_i$ and $d_i \mid d_{i+1}$.

For a given pair of positive integers $n, m$, let $S$ be the set of all
$n\times m$ matrices of the form
$\left(\begin{array}{ll}{L_{r}} & {0} \\ {0} & {0}\end{array}\right)$
where $r=1,2,\cdots,\min(m,n)$ and $L_r$ is a diagonal $r\times r$
matrix with main diagonal $d_i$.

Show that $S$ is a set of canonical forms under equivalence for the set
of all $n\times m$ matrices over $R$.
:::

### Qual Problems

:::{.problem}
Let $R$ be a commutative ring.

1.  Say what it means for $R$ to be a unique factorization domain (UFD).

2.  Say what it means for $R$ to be a principal ideal domain (PID)

3.  Give an example of a UFD that is not a PID. Prove that it is not a
    PID.
:::

:::{.problem}
Let $A$ be an $n\times n$ matrix over a field $F$ such
that $A$ is diagonalizable. Prove that the following are equivalent:

1.  There is a vector $v\in F^n$ such that $v, Av, \cdots A^{n-1}v$ is a
    basis for $F^n$.

2.  The eigenvalues of $A$ are distinct.
:::

:::{.problem}
Let $x,y \in \mathbb{C}$ and consider the matrix

$$M =
\left[\begin{array}{ccc}
     1 & 0 & x \\
     0 & 1 & 0 \\
     y & 0 & 1
\end{array}\right]$$

1.  Show that $[0, 1, 0]^t$ is an eigenvector of $M$.

2.  Compute the rank of $M$ as a function of $x$ and $y$.

3.  Find all values of $x$ and $y$ for which $M$ is diagonalizable.
:::

## Problem Set Ten

### Exercises

:::{.problem title="Hungerford 7.3.1"}
Let $B$ be an $R$-module. Show that if $r+r\neq 0$ for all $r\neq 0 \in R$, then an $n$-linear form
$B^n\to R$ is alternating $\iff$ it is skew-symmetric.
:::

:::{.problem title="Hungerford 7.3.5"}
If $R$ is a field and $A, B \in M_n(R)$ are invertible then the matrix $A + rB$ is invertible
for all but a finite number of $r\in R$.
:::

:::{.problem title="Hungerford 7.4.4"}
Show that if $q$ is the minimal polynomial of a linear transformation $\phi: E\to E$ with $\dim_k E = n$
then $\deg q \leq n$.
:::

:::{.problem title="Hungerford 7.4.8)."} 
Show that $A\in M_n(K)$ is similar to a diagonal matrix $\iff$ the elementary divisors of $A$ are all linear.
:::

:::{.problem title="Hungerford 7.4.10"}
Find all possible rational canonical forms for a matrix $A\in M_n(\Bbb Q)$ such that

1.  $A$ is $6\times 6$ with minimal polynomial $q(x) = (x-2)^2(x+3)$.

2.  $A$ is $7\times 7$ with $q(x) = (x^2+1)(x-7)$.

Also find all such forms when $A \in M_n(\Bbb C)$ instead, and find all
possible Jordan Canonical Forms over $\Bbb C$.
:::

:::{.problem title="Hungerford 7.5.2"}
Show that if $\phi$ is an endomorphism of a free $k$-module $E$ of finite rank, then
$p_\phi(\phi) = 0$.

*Hint: If $A$ is the matrix of $\phi$ and $B = x I_n - A$ then*
\[
B^a B = |B| I_n = p_\phi I_n \in M_n(k[x])
.\]
*If $E$ is a $k[x]$-module with structure induced by $\phi$, and $\psi$ is the $k[x]$-module endomorphism $E\to E$ with matrix given by $B$, then*
\[ 
\psi(u) = x u -\phi(u) = \phi(u) - \phi(u) = 0 && \forall u\in E
.\]

:::

:::{.problem title="Hungerford 7.5.7"}
\envlist

1.  Let $\phi,\psi$ be endomorphisms of a finite-dimensional vector
    space $E$ such that $\phi\psi = \psi \phi$. Show that if $E$ has a
    basis of eigenvectors of $\psi$, then it has a basis of eigenvectors
    for both $\psi$ and $\phi$ simultaneously.

2.  Interpret the previous part as a statement about matrices similar to
    a diagonal matrix.
:::

### Qual Problems

:::{.problem}
Let $M \in M_5(R)$ be a $5\times 5$ square matrix with
real coefficients defining a linear map $L: \Bbb{R}^5 \to \Bbb R^5$.
Assume that when considered as an element of $M_5(\Bbb C)$, then the
scalars $0, 1+i, 1+2i$ are eigenvalues of $M$.

1.  Show that the associated linear map $L$ is neither injective nor
    surjective.

2.  Compute the characteristic polynomial and minimal polynomial of $M$.

3.  How many fixed points can $L$ have?

    *(That is, how many solutions are there to the equation $L(v) = v$
    with $v\in \Bbb R^5$?)*
:::

:::{.problem}
Let $n$ be a positive integer and let $B$ denote the
$n\times n$ matrix over $\Bbb C$ such that every entry is 1. Find the
Jordan normal form of $B$.
:::

:::{.problem}
Suppose that $V$ is a 6-dimensional vector space and
that $T$ is a linear transformation on $V$ such that $T^6 = 0$ and
$T^5\neq 0$.

1.  Find a matrix for $T$ in Jordan Canonical form.

2.  Show that if $S, T$ are linear transformations on a 6-dimensional
    vector space $V$ which both satisfy $T^6=S^6=0$ and $T^5,S^5\neq 0$,
    then there exists a linear transformation $A$ from $V$ to itself
    such that $ATA^{-1} = S$.
:::
