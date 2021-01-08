**Problem** [\[prob:1.9\]](#prob:1.9){reference-type="ref"
reference="prob:1.9"}

::: {.proof}
*Proof.*

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
    possible cases. $\qed$

 ◻
:::

**Problem** [\[prob:1.10\]](#prob:1.10){reference-type="ref"
reference="prob:1.10"}

::: {.proof}
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

**Problem** [\[prob:1.11\]](#prob:1.11){reference-type="ref"
reference="prob:1.11"}

::: {.proof}
*Proof.* Let $$C_H = \{ gHg^{-1} \mid g\in G \}$$ be the conjugacy class
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

**Problem** [\[prob:1.12\]](#prob:1.12){reference-type="ref"
reference="prob:1.12"}

::: {.proof}
*Proof.* **Claim 1**: Conjugacy classes in $S_n$ are completely
determined by cycle type.

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
