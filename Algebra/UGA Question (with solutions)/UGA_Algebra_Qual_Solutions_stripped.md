
# Preface

I'd like to extend my gratitude to the following people for helping supply solutions and proofs:

-   Paco Adajar
-   Swaroop Hegde

Many other solutions contain input and ideas from other graduate students and faculty members at UGA, along with questions and answers posted on Math Stack Exchange or Math Overflow.

# Group Theory: General

## Cosets

### Spring 2020 \#2 \( \done \) {#spring-2020-2-done}

Let \( H \) be a normal subgroup of a finite group \( G \) where the order of \( H \) and the index of \( H \) in \( G \) are relatively prime. Prove that no other subgroup of \( G \) has the same order as \( H \).

::: {.concept}
```{=tex}
\envlist
```
-   Division algorithm: \( (a,b)= d\implies as+bt =1 \) for some \( s, t \).
-   Coset containment trick: \( X\subseteq N \iff xN = N \) for all \( x \).
:::

::: {.strategy}
Recognize that it suffices to show \( hN = N \). Context cue: coprimality hints at division algorithm. Descend to quotient so you can leverage both the order of \( h \) *and* the order of cosets simultaneously.
:::

::: {.solution}
```{=tex}
\envlist
```
-   For ease of notation, replace \( H \) in the problem with \( N \) so we remember which one is normal.
-   Write \( n\coloneqq\# N \) and \( m \coloneqq[G:N] = \#G/N \), where the quotient makes sense since \( N \) is normal.
-   Let \( H \leq G \) with \( \# H = n \), we'll show \( H=N \).
    -   Since \( \# H = \# N \) it suffices to show \( H \subseteq N \).
    -   It further suffices to show \( hN = N \) for all \( h\in H \).
-   Noting \( \gcd(m, n)=1 \), use the division algorithm to write \( 1 = ns + mt \) for some \( s,t\in {\mathbb{Z}} \).
-   The result follows from a computation:
    \[
    hN 
    &= h^1 N \\
    &= h^{ns + mt}N \\
    &= h^{ns} N \cdot h^{mt}N \\
    &= \qty{h^n N}^s \cdot \qty{h^t N}^m \\
    &= (eN)^s \cdot N \\
    &= N
    ,\]
    -   We've used that \( h\in H \implies o(h) \bigm|\# H = n \) by Lagrange, so \( h^n = e \).
    -   We've also used that \( \# G/N = m \), so \( (xH)^m = H \) for any \( xH\in G/H \).
:::

### Fall 2014 \#6 \( \done \) {#fall-2014-6-done}

Let \( G \) be a group and \( H, K < G \) be subgroups of finite index. Show that
\[
[G: H\cap K] \leq [G: H] ~ [G:K]
.\]

::: {.concept}
```{=tex}
\envlist
```
-   For \( H, K\leq G \), intersection is again a subgroup of everything: \( H\int K \leq H, K, G \) by the one-step subgroup test.
-   Counting in towers: \( A\leq B \leq C \implies [C:A] = [C:B][B:A] \).
-   Fundamental theorem of cosets: \( xH = yH \iff xy^{-1}\in H \).
-   Common trick: just list out all of the darn cosets!
:::

::: {.strategy}
Count in towers, show that distinct coset reps stay distinct.
:::

::: {.solution}
```{=tex}
\envlist
```
-   \( H \cap K \leq H \leq G \implies [G: H \cap K] = [G: H] [H : H \cap K] \)
-   So it suffices to show \( [H: H \cap K] \leq [G: K] \)
-   Write \( H/H \cap K = \left\{{ h_1 J, \cdots, h_m J }\right\} \) as distinct cosets where \( J \coloneqq H \cap J \).
-   Then \( h_i J\neq h_j J \iff h_i h_j^{-1}\not\in J = H \cap K \).
-   \( H \) is a subgroup, so \( h_i h_j^{-1}\in H \) forces this not to be in \( K \).
-   But then \( h_i K \neq h_j K \), so these are distinct cosets in \( G/K \).
-   So \( \#G/K \geq m \).
:::

### Spring 2013 \#3 \( \done \) {#spring-2013-3-done}

Let \( P \) be a finite \( p{\hbox{-}} \)group. Prove that every nontrivial normal subgroup of \( P \) intersects the center of \( P \) nontrivially.

```{=tex}
\todo[inline]{Clean up, sketchy argument.}
```
::: {.solution}
```{=tex}
\envlist
```
-   Let \( N{~\trianglelefteq~}P \), then for each conjugacy class \( [n_i] \) in \( N \), \( H \cap[g_i] = [g_i] \) or is empty.
-   \( G = {\textstyle\coprod}_{i\leq M} [g_i] \) is a disjoint union of conjugacy classes, and the conjugacy classes of \( H \) are of the form \( [g_i] \cap H \).
-   Then pull out the center
    \[
    H = \displaystyle\coprod_{i\leq M} [g_i] \cap H = \qty{ Z(G) \cap H } {\textstyle\coprod}\displaystyle\coprod_{i\leq M'} [g_i]
    .\]
-   Taking cardinalities,
    \[
    \# H = \# \qty{ Z(G) \cap H} + \sum_{i\leq M'} \# [g_i]
    .\]
-   \( p \) divides \( H \) since \( H\leq P \) and \( P \) is a \( p{\hbox{-}} \)group.
-   Each \( \# [g_i] \geq 2 \) since the trivial conjugacy classes appear in the center, forcing \( \# [g_i] \geq p \).
-   \( p \) divides \( \# [g_i] \) since \( \# [g_i] \) must divide \( \# P = p^k \)
-   So \( p \) must divide the remaining term \( Z(G) \cap H \), which makes it nontrivial.
:::

## Burnside / Class Equation

### Spring 2019 \#4 \( \done \) {#spring-2019-4-done}

For a finite group \( G \), let \( c(G) \) denote the number of conjugacy classes of \( G \).

a.  Prove that if two elements of \( G \) are chosen uniformly at random,then the probability they commute is precisely
    \[
    \frac{c(G)}{{\left\lvert {G} \right\rvert}}
    .\]

b.  State the class equation for a finite group.

c.  Using the class equation (or otherwise) show that the probability in part (a) is at most
    \[
    \frac 1 2 + \frac 1 {2[G : Z(G)]}
    .\]

> Here, as usual, \( Z(G) \) denotes the center of \( G \).

::: {.warnings}
(DZG) This is a slightly anomalous problem! It's fun and worth doing, because it uses the major counting formulas. Just note that the techniques used in this problem perhaps don't show up in other group theory problems.
:::

::: {.concept}
```{=tex}
\envlist
```
-   Notation: \( X/G \) is the set of \( G{\hbox{-}} \)orbits
-   Notation: \( X^g = \left\{{x\in X{~\mathrel{\Big|}~}g\cdot x = x}\right\} \)
-   Burnside's formula: \( \#{X/G} = {1 \over \# G} \sum \# {X^g} \).
-   Definition of conjugacy class: \( C(g) = \left\{{ hgh^{-1}{~\mathrel{\Big|}~}h\in G }\right\} \).
:::

::: {.strategy}
Fixed points of the conjugation action are precisely commuting elements. Apply Burnside. Context clue: \( 1/[G:Z(G)] \) is weird, right? Use that \( [G:Z(G)] = \# G/\# Z(G) \), so try to look for \( \#Z(G)/\#(G) \) somewhere. Count sizes of centralizers.
:::

::: {.solution}
```{=tex}
\envlist
```
::: {.proof title="Part a"}
```{=tex}
\envlist
```
-   Define a sample space \( \Omega = G \times G \), so \( \# {\Omega} = (\# {G})^2 \).

-   Identify the event we want to analyze:
    \[
    A \coloneqq\left\{{(g,h) \in G\times G {~\mathrel{\Big|}~}[g,h] = 1}\right\} \subseteq \Omega
    .\]

-   Note that the slices are centralizers:
    \[
    A_g \coloneqq\left\{{(g, h) \in \left\{{ g }\right\} \times G {~\mathrel{\Big|}~}[g, h] = 1}\right\} = Z(g) \implies A = \displaystyle\coprod_{g\in G} Z(g)
    .\]

-   Set \( n \) be the number of conjugacy classes, note we want to show \( P(A) = n / {\left\lvert {G} \right\rvert} \).

-   Let \( G \) act on itself by conjugation, which partitions \( G \) into conjugacy classes.

    -   What are the orbits?
        \[
        \mathcal{O}_g = \left\{{hgh^{-1}{~\mathrel{\Big|}~}h\in G}\right\}
        ,\]
        which is the **conjugacy class** of \( g \). In particular, the number of orbits is the number of conjugacy classes.

    -   What are the fixed points?
        \[X^g = \left\{{h\in G {~\mathrel{\Big|}~}hgh^{-1}= g}\right\},\]
        which are the elements of \( G \) that commute with \( g \), which is isomorphic to \( A_g \).

-   Identifying centralizers with fixed points,
    \[
    \#{A} = \#{\displaystyle\coprod_{g\in G} Z(g) } = \sum_{g\in G} \#{Z(g)} = \sum_{g\in G}\# {X^g}
    .\]

-   Apply Burnside
    \[
    \# {X / G} = \frac { 1 } { \# G  } \sum _ { g \in G } \# X ^ { g } ,
    \]

-   Note \( \#{X/G} = n \), i.e. the number of conjugacy classes is the number of orbits.

-   Rearrange and use definition:
    \[
    n \cdot \#{G}
    = \qty{\#{X/G} }\cdot \#{G}
    = \sum _ { g \in G } \# X ^ { g } 
    \]

-   Compute probability:
    \[
    P(A)
    = {\# A \over \# \Omega} 
    =  \displaystyle\sum _{ g \in G } \frac{\# X ^ { g }}{ ( \# {G} )^2} 
    = \frac{\qty{ \# {X/G}} \cdot \#{G}}{ (\#{G})^2} 
    = \frac{n \cdot \#{G}}{( \#{G} )^2} 
    = \frac n {\# G}
    .\]
:::

::: {.proof title="Part b"}
Statement of the class equation:
\[
{\left\lvert {G} \right\rvert} = Z(G) + \sum_{\substack{\text{One $x$ from each} \\ \text{conjugacy class}}}[G: Z(x)]
\]
where \( Z(x) = \left\{{g\in G {~\mathrel{\Big|}~}[g, x] = 1}\right\} \) is the centralizer of \( x \) in \( G \).
:::

::: {.proof title="Part c"}
```{=tex}
\envlist
```
> (DZG): I couldn't convince myself that a previous proof using the class equation actually works. Instead, I'll borrow the proof from [this note](https://math.berkeley.edu/~tb65536/Commuting_Probability.pdf)

-   Write the event as \( A = \displaystyle\coprod_{g\in G} \left\{{g}\right\} \times Z(g) \), then
    \[
    P(A) 
    = {\# A\over (\# G)^2} 
    = {1\over (\# G)^2} \sum_{g\in G} \# Z(g)
    .\]
-   Attempt to estimate the sum: pull out central elements \( g\in Z(G) \).
    -   Note \( Z(g) = G \) for central \( g \), so \( \# Z(g) = \# G \)
    -   Note
        \[
        g\not\in Z(G)\implies \# Z(g) \leq {1\over 2} \# G
        ,\]
        since \( Z(g) \leq G \) is a subgroup, and
        \[
        [G:Z(g)] \neq 1 \implies [G: Z(g)] \geq 2
        .\]
-   Use these facts to calculate:
    \[
    P(A) 
    &= {1\over (\# G)^2 } \qty{ \sum_{g\in Z(g)} \# Z(g) + \sum_{g\not\in Z(g)} \# Z(g) } \\
    &= {1\over (\# G)^2 } \qty{ \sum_{g\in Z(g)} \# G + \sum_{g\not\in Z(g)} \# Z(g) } \\
    &= {1\over (\# G)^2 } \qty{ \# Z(G) \cdot \# G + \sum_{g\not\in Z(g)} \# Z(g) } \\
    &\leq {1\over (\# G)^2 } \qty{ \# Z(G) \cdot \# G + \sum_{g\not\in Z(g)} {1\over 2} \# G } \\
    &= {1\over (\# G)^2 } \qty{ \# Z(G) \cdot \# G + \qty{ \sum_{g\not\in Z(g)} {1\over 2} } \cdot \# G } \\
    &= {1\over (\# G) } \qty{ \# Z(G) + \sum_{g\not\in Z(g)} {1\over 2} } \\
    &= {1\over (\# G) } \qty{ \# Z(G) + {1\over 2} \sum_{g\not\in Z(g)} 1 } \\
    &= {1\over (\# G) } \qty{ \# Z(G) + {1\over 2} \#(G \setminus Z(G) ) } \\
    &= {1\over (\# G) } \qty{ \# Z(G) + {1\over 2} \#G - {1\over 2} \# Z(G) } \\
    &= {1\over (\# G) } \qty{ {1\over 2} \# Z(G) + {1\over 2} \#G  } \\
    &= {1\over 2} \qty{1 + { \# Z(G) \over \# G }} \\
    &= {1\over 2} \qty{1 + { 1 \over [G : Z(G)]  }}
    .\]
:::

```{=tex}
\todo[inline]{Redo part c}
```
:::

## Group Actions / Representations

### Spring 2017 \#1 \( \done \) {#spring-2017-1-done}

Let \( G \) be a finite group and \( \pi: G\to \operatorname{Sym}(G) \) the Cayley representation.

> (Recall that this means that for an element \( x\in G \), \( \pi(x) \) acts by left translation on \( G \).)

Prove that \( \pi(x) \) is an odd permutation \( \iff \) the order \( {\left\lvert {\pi(x)} \right\rvert} \) of \( \pi(x) \) is even and \( {\left\lvert {G} \right\rvert} / {\left\lvert {\pi(x)} \right\rvert} \) is odd.

::: {.warnings}
(DZG): This seems like an unusually hard group theory problem. My guess is this year's qual class spent more time than usual on the proof of Cayley's theorem.
:::

::: {.concept}
```{=tex}
\envlist
```
-   \( \operatorname{Sym}(G) \coloneqq{\operatorname{Aut}}_{\mathsf{Set}}(G, G) \) is the group of set morphisms from \( G \) to itself, i.e. permutations of elements of \( G \).
-   More standard terminology: this is related to the **left regular representation** where \( g\mapsto \phi_g \) where \( \phi_g(x) = gx \), regarded instead as a permutation representation.
    -   This action is transitive!
-   Cayley's theorem: every \( G \) is isomorphic to a subgroup of a permutation group. In particular, take \( \left\{{ \phi_g {~\mathrel{\Big|}~}G\in G }\right\} \) with function composition as a subgroup of \( {\operatorname{Aut}}_{\mathsf{Set}}(G) \).
:::

::: {.solution}
```{=tex}
\envlist
```
> (DZG): Warning!! I haven't checked this solution very carefully, and this is kind of a delicate parity argument. Most of the key ideas are borrowed [from here](https://math.stackexchange.com/questions/3028603/show-that-phig-is-an-even-permutation).

-   Write \( k \coloneqq o(\pi_g) \), then since \( \pi \) is injective, \( k = o(g) \) in \( G \).
-   Since \( \pi_g \) as a cycle is obtained from the action of \( g \), we can pick an element \( x_0 \) in \( G \), take the orbit under the action, and obtain a cycle of length \( k \) since the order of \( g \) is \( k \). Then continue by taking any \( x_1 \) not in the first orbit and taking *its* orbit. Continuing this way exhausts all group elements and yields a decomposition into disjoint cycles:
    \[
    \pi_g = 
    (x_0, gx_0, g^2 x_0, \cdots, g^{k-1} x_0)
    (x_1, gx_1, g^2 x_1, \cdots, g^{k-1} x_1)
    \cdots
    (x_m, gx_m, g^2 x_m, \cdots, g^{k-1} x_m)
    .\]
-   So there are \( m \) orbits all of length exactly \( k \). Proceed by casework.
-   If \( k \) is even:
    -   This yields \( m \) odd cycles, and thus \( \pi \) has zero (an even number) of even cycles.
    -   Thus \( \pi \in \ker \operatorname{sgn} \) and is an even permutation.
-   If \( k \) is odd
    -   This yields \( m \) even cycles, thus an even number of even cycles iff \( m \) is even
-   The claim is that the number of orbit representatives \( m \) is equal to \( [G:H] = \# G/H \) for \( H = \left\langle{ g }\right\rangle \).
    -   Proof: define a map
        \[
        \left\{{ \text{Orbit representatives } x_i }\right\} &\to G/H \\
        x &\mapsto xH
        .\]
    -   This is injective and surjective because
        \[
        xH = yH &\iff xy^{-1}\in H = \left\langle{ g }\right\rangle \\
        &\iff xy^{-1}= g^\ell \\
        &\iff x=g^\ell y \\
        &\iff y\in {\mathcal{O}}_x
        ,\]
        so \( y \) and \( x \) are in the same orbit and have the same orbit representative.
-   We now have
    \[
    \pi_g \text{ is an even permutation } \iff 
    \begin{cases}
    k \text{ is odd and } m \text{ is even} &  
    \\
    \text{ or } & \\
    k \text{ is even}
     & .
    \end{cases}
    \]
-   Everything was an iff, so flip the evens to odds:
    \[
    \pi_g \text{ is an odd permutation } \iff 
    \begin{cases}
    k \text{ is even and } m \text{ is odd} &  
    \\
    \text{ or } & \\
    k \text{ is odd}
     & .
    \end{cases}
    .\]
-   Then just recall that \( k\coloneqq o(\pi_g) \) and
    \[
    m= [G: \left\langle{ g }\right\rangle] = \# G / \# \left\langle{ g }\right\rangle= \# G / o(g) = \# G/ o(\pi_g)
    .\]
:::

### Fall 2015 \#1 \( \done \) {#fall-2015-1-done}

Let \( G \) be a group containing a subgroup \( H \) not equal to \( G \) of finite index. Prove that \( G \) has a normal subgroup which is contained in every conjugate of \( H \) which is of finite index.

> (DZG) A remark: it's not the conjugates that should be finite index here, but rather the normal subgroup.

::: {.solution}
```{=tex}
\envlist
```
-   Let \( H\leq G \) and define \( n\coloneqq[G:H] \).
-   Write \( G/H = \left\{{ x_1 H, \cdots, x_n H }\right\} \) for the finitely many cosets.
-   Let \( G \) act on \( G/H \) by left translation, so \( g\cdot xH \coloneqq gxH \).. Call the action \( \psi: G\to \operatorname{Sym}(G/H) \).
-   Then \( {\operatorname{Stab}}(xH) = xHx^{-1} \) is a subgroup conjugate to \( H \), and \( K\coloneqq\ker \psi = \displaystyle\bigcap_{i=1}^n xHx^{-1} \) is the intersection of all conjugates of \( H \).
-   Kernels are normal, so \( K{~\trianglelefteq~}G \), and \( K\subseteq xHx^{-1} \) for all \( x \), meaning \( K \) is contained in every conjugate of \( H \).
-   The index \( [G:K] \) is finite since \( G/K \cong \operatorname{im}\psi \) by the first isomorphism theorem, and \( \# \operatorname{im}\psi \leq \# \operatorname{Sym}(G/H) = \# S_n = n! < \infty \).
:::

## Conjugacy Classes

### Spring 2021 \#2 \( \done \) {#spring-2021-2-done}

Let \( H {~\trianglelefteq~}G \) be a normal subgroup of a finite group \( G \), where the order of \( H \) is the smallest prime \( p \) dividing \( {\left\lvert {G} \right\rvert} \). Prove that \( H \) is contained in the center of \( G \).

> Solution due to Swaroop Hegde, typed up + modifications added by DZG.

::: {.concept}
```{=tex}
\envlist
```
1.  Normal subgroups are disjoint unions of (some) conjugacy classes in \( G \).

-   In fact, this is a characterization of normal subgroups (i.e. \( H \) is normal iff a union of conjugacy classes).

2.  Orbit stabilizer theorem: \( \# C_g = \# G/ \# K_g \) where \( C_g \) is the centralizer and \( K_g \) is the conjugacy class of \( g \). In particular, \( \# C_g \) divides \( \#G \).
3.  \( x\in Z(G) \) iff \( \# C_x = 1 \), i.e. the size of its conjugacy class is one.
:::

::: {.proof title="?"}
```{=tex}
\envlist
```
-   Let \( p \coloneqq\#H \).

-   Let \( \left\{{ C_i }\right\}_{i\leq n} \) be the conjugacy classes in \( G \), then \( G = {\textstyle\coprod}_{i\leq n} C_i \)

-   By the first fact, there is a sub-collection \( \left\{{ C_{i_j}}\right\}_{j\leq k } \) such that
    \[
    H = {\textstyle\coprod}_{j\leq k} C_{i_j}
    .\]

-   The identity is always in a single conjugacy class, so \( C_e = \left\{{ e }\right\} \).

-   Since \( e\in H \), without loss of generality, label \( C_{i_1} = \left\{{ e }\right\} \).

-   So
    \[
    H 
    = {\textstyle\coprod}_{j\leq k} C_{i_j} 
    = C_{i_1}{\textstyle  \coprod} \displaystyle\displaystyle\coprod_{\substack{ j\leq k \\ j\neq 1} } C_{i_j} 
    .\]

-   Take cardinality in the above equation
    \[
    p = 1 + \sum_{\substack{ j\leq k \\ j\neq 1 }} \# C_{i_j}
    .\]

-   So \( \# C_{i_j} \leq p-1 \) for all \( j\neq 1 \).

-   Every \( \# C_{i_j} \) divides \( \# G \), but \( p \) was the *minimal* prime dividing \( \# G \), forcing \( \# C_{i_j} = 1 \) for all \( j \neq 1 \).

    -   This rules out \( \# C_{i_j} \) being a prime less than \( p \), but also rules out composites: if a prime \( q\bigm|\# C_{i_j} \), then \( q<p \) and \( q\bigm|\# G \), a contradiction.

-   By fact 3, each \( x\in C_{i_j} \) satisfies \( x\in Z(G) \).

-   \( \cup C_{i_j} = H \), so \( H \subseteq Z(G) \).
:::

### Spring 2015 \#1 \( \done \) {#spring-2015-1-done}

For a prime \( p \), let \( G \) be a finite \( p{\hbox{-}} \)group and let \( N \) be a normal subgroup of \( G \) of order \( p \). Prove that \( N \) is contained in the center of \( G \).

::: {.concept}
```{=tex}
\envlist
```
-   Definition of conjugacy class: \( [x] = \left\{{gxg^{-1}{~\mathrel{\Big|}~}g\in G}\right\} \).
-   A conjugacy class \( [x] \) is trivial iff \( [x] = \left\{{ x }\right\} \) iff \( x\in Z(G) \).
-   Sizes of conjugacy classes divide the order of the group they live in.
    -   This is orbit-stabilizer: \( G\curvearrowright G \) by \( g\cdot x \coloneqq gxg^{-1} \), so \( {\mathcal{O}}(x) = [x] \). Then \( \# {\mathcal{O}}(x) = \# G / \# {\operatorname{Stab}}(x) \), so \( \# {\mathcal{O}}(x) \) divides \( \# G \).
:::

::: {.solution}
```{=tex}
\envlist
```
-   Use that \( N{~\trianglelefteq~}G \iff N = {\textstyle\coprod}' [n_i] \) is a *disjoint* union of (full) conjugacy classes.
-   Take cardinalities:
    \[
    p = \# N = \sum_{i=1}^m \# [n_i] = 1 + \sum_{i=2}^m [n_i]
    .\]
-   The size of each conjugacy class divides the size of \( H \) by orbit-stabilizer, so \( \# [n_i] \bigm|p \) for each \( i \).
-   But the entire second term must sum to \( p-1 \) for this equality to hold, which forces \( \#[n_i] = 1 \) (and incidentally \( m=p-1 \))
-   Then \( [n_i] = \left\{{ n_i }\right\} \iff n_i \in Z(G) \), and this holds for all \( i \), so \( N \subseteq Z(G) \).
:::

## Unsorted / Counting Arguments

### Fall 2019 Midterm \#5 \( \done \) {#fall-2019-midterm-5-done}

Let \( G \) be a nonabelian group of order \( p^3 \) for \( p \) prime. Show that \( Z(G) = [G, G] \).

> Note: this is a good problem, it tests several common theorems at once. Proof due to Paco Adajar.

::: {.concept}
```{=tex}
\envlist
```
Important notations and definitions:

-   The **center** of \( G \), denoted by \( Z(G) \), is the subset of elements of \( G \) which commute with all elements of \( G \). That is, if \( x \in Z(G) \), then for all \( g \in G \), \( gx = xg \):
    \[Z(G) = \{ x \in G : gx = xg \, \text{for all } g \in G \}.\]

    In fact, \( Z(G) \) is not just a subset of \( G \), but a normal subgroup of \( G \).

-   The **commutator subgroup** of \( G \), denoted by \( [G, G] \), is the subgroup of \( G \) generated by the commutators of \( G \), i.e., the elements of the form \( ghg^{-1}h^{-1} \):
    \[[G, G] = \langle ghg^{-1}h^{-1} : g, h \in G \rangle.\]

    The commutator subgroup \( [G,G] \) is the smallest normal subgroup of \( G \) whose quotient is abelian. That is, if \( H \) is a normal subgroup of \( G \) for which \( G/H \) is abelian, then \( [G, G] \le H \).

    Moreover, \( G \) is abelian if and only if \( [G,G] \) is trivial.

Theorems to remember and know how to prove:

-   **\( G/Z(G) \) Theorem**: If \( G/Z(G) \) is cyclic, then \( G \) is abelian, i.e., \( G/Z(G) \) is in fact trivial.

-   **Lagrange's Theorem**: If \( G \) is a group of finite order and \( H \) is a subgroup of \( G \), then the order of \( H \) divides that of \( G \).

    -   One consequence of this is that every group of prime order is cyclic.

-   A \( p \)-group (a group of order \( p^n \) for some prime \( p \) and some positive integer \( n \)) has nontrivial center.

-   A consequence of the theorems above: every group of order \( p^2 \) (where \( p \) is prime) is abelian.
:::

::: {.solution}
Since \( Z(G) \) is a subgroup of \( G \) and \( |G| = p^3 \), by Lagrange's theorem, \( |Z(G)| \in \{1, p, p^2, p^3\} \).

Since we stipulated that \( G \) is nonabelian, \( |Z(G)| \ne p^3 \). Also, since \( G \) is a \( p \)-group, it has nontrivial center, so \( |Z(G)| \ne 1 \). Finally, by the \( G/Z(G) \) theorem, \( |Z(G)| \ne p^2 \): if \( |Z(G)| = p^2 \), then \( |G/Z(G)| = p \) and so \( G/Z(G) \) would be cyclic, meaning that \( G \) is abelian. Hence, \( |Z(G)| = p \).

Then, since \( |Z(G)| = p \), we have that \( |G/Z(G)| = p^2 \), and so \( G/Z(G) \) is abelian. Thus, \( [G, G] \in Z(G) \). Since \( |Z(G)| = p \), then \( |[G,G]| \in \{ 1, p\} \) again by Lagrange's theorem. If \( |[G,G]| = p \) then \( [G,G] = Z(G) \) and we are done. And, indeed, we must have \( |[G,G]| = p \), because \( G \) is nonabelian and so \( |[G,G]| \ne 1 \).
:::

### Spring 2012 \#2 \( \done \) {#spring-2012-2-done}

Let \( G \) be a finite group and \( p \) a prime number such that there is a normal subgroup \( H{~\trianglelefteq~}G \) with \( {\left\lvert {H} \right\rvert} = p^i > 1 \).

a.  Show that \( H \) is a subgroup of any Sylow \( p{\hbox{-}} \)subgroup of \( G \).

b.  Show that \( G \) contains a nonzero abelian normal subgroup of order divisible by \( p \).

::: {.concept}
```{=tex}
\envlist
```
-   \( p \) groups have nontrivial centers.
-   Definition of maximality and \( p{\hbox{-}} \)groups
-   Sylows are conjugate
-   \( Z(G) \char G \) always.
-   Transitivity of characteristic: \( A \char B \) and \( B{~\trianglelefteq~}C \) implies \( A {~\trianglelefteq~}C \).
:::

::: {.strategy}
Just use maximality for (a). For (b), centers are always abelian, so \( Z(H) \) is good to consider, just need to ensure it's normal in \( G \). Use transitivity of characteristic.
:::

::: {.solution}
```{=tex}
\envlist
```
::: {.proof title="of a"}
```{=tex}
\envlist
```
-   By definition, \( S\in {\operatorname{Syl}}_p(G) \iff S \) is a *maximal* \( p{\hbox{-}} \)subgroup: \( S<G \) is a \( p{\hbox{-}} \)group, so \( \#S = p^k \) for some \( k \), \( S \) is a proper subgroup, and \( S \) is maximal in the sense that there are no proper \( p{\hbox{-}} \)subgroups \( S' \) with \( S \subseteq S' \subseteq G \).
-   Since \( \# H = p^i \), \( H \) is a \( p{\hbox{-}} \)subgroup of \( G \).
-   If \( H \) is maximal, then by definition \( H\in {\operatorname{Syl}}_p(G) \)
-   Otherwise, if \( H \) is not maximal, there exists an \( H' \supseteq H \) with \( H'\leq G \) a \( p{\hbox{-}} \)subgroup properly containing \( H \).
    -   In this apply the same argument to \( H' \): this yields a proper superset containment at every stage, and since \( G \) is finite, there is no infinite ascending chain of proper supersets.
    -   So this terminates in some maximal \( p{\hbox{-}} \)subgroup \( S \), i.e. a Sylow \( p{\hbox{-}} \)subgroup.
-   So \( H \subseteq S \) for some \( S\in {\operatorname{Syl}}_p(G) \).
-   All Sylows are conjugate, so for any \( S' \in {\operatorname{Syl}}_p(G) \) we can write \( S' = gSg^{-1} \) for some \( g \).
-   Then using that \( H \) is normal, \( H \subseteq S \implies H = gHg^{-1}\subseteq gSg^{-1}\coloneqq S' \). So \( H \) is contained in every Sylow \( p{\hbox{-}} \)subgroup.
:::

::: {.proof title="of b"}
```{=tex}
\envlist
```
-   Claim: \( Z(H) \leq H \) works.
    -   It is nontrivial since \( H \) is a \( p{\hbox{-}} \)group and \( p{\hbox{-}} \)groups have nontrivial centers
    -   It is abelian since \( Z(Z(H)) = Z(H) \).
    -   \( \#Z(H) = p^\ell \) for some \( \ell \leq i \) by Lagrange
-   It thus remains to show that \( Z(H) {~\trianglelefteq~}G \).
-   Use that \( Z(H) \char H \) and use transitivity of characteristic to conclude \( Z(H) {~\trianglelefteq~}H \).
-   That \( Z(H) \char H \): let \( \psi \in {\operatorname{Aut}}(H) \) and \( x=\psi(y)\in \psi(Z(H)) \) so \( y\in Z(H) \), then for arbitrary \( h\in H \),
    \[
     \psi(y)h 
     &= \psi(y) (\psi \circ \psi^{-1})(h) \\
     &= \psi( y \cdot \psi^{-1}(h) ) \\
     &= \psi( \psi^{-1}(h) \cdot y ) && \text{since } \psi^{-1}(h)\in H, \, y\in Z(H) \\
     &= h\psi(y)
     .\]
-   That \( A \char B {~\trianglelefteq~}C \implies A{~\trianglelefteq~}C \):
    -   \( A\char B \) iff \( A \) is fixed by every \( \psi\in {\operatorname{Aut}}(B) \)., WTS \( cAc^{-1}= A \) for all \( c\in C \).
    -   Since \( B{~\trianglelefteq~}C \), the automorphism \( \psi({-}) \coloneqq c({-})c^{-1} \) descends to an element of \( {\operatorname{Aut}}(B) \).
    -   Then \( \psi(A) = A \) since \( A\char B \), so \( cAc^{-1}= A \) and \( A{~\trianglelefteq~}C \).
:::
:::

### Fall 2016 \#1 \( \done \) {#fall-2016-1-done}

Let \( G \) be a finite group and \( s, t\in G \) be two distinct elements of order 2. Show that subgroup of \( G \) generated by \( s \) and \( t \) is a dihedral group.

> Recall that the dihedral groups of order \( 2m \) for \( m\geq 2 \) are of the form
> \[
> D_{2m} = \left\langle{\sigma, \tau {~\mathrel{\Big|}~}\sigma^m = 1 = \tau^2, \tau \sigma = \sigma^{-1}\tau}\right\rangle
> .\]

::: {.solution}
```{=tex}
\envlist
```
-   Suppose \( G = \left\langle{ a, b}\right\rangle \) with \( a^2 = b^2 = e \), satisfying some unknown relations.

-   Consider \( ab \). Since \( G \) is finite, this has finite order, so \( (ab)^n = e \) for some \( n\geq 2 \).

-   Note \( \left\langle{ab, b}\right\rangle \subseteq \left\langle{a, b}\right\rangle \), since any finite word in \( ab, b \) is also a finite word in \( a, b \).

-   Since \( (ab)b = ab^2 = a \), we have \( \left\langle{ab, b}\right\rangle \subseteq \left\langle{a, b}\right\rangle \), so \( \left\langle{ab, b}\right\rangle = \left\langle{a, b}\right\rangle \).

-   Write \( D_{2n} = F(r, s) / \ker \pi \) for \( \pi: F(r, s)\to D_{2n} \) the canonical presentation map.

-   Define
    \[
    \psi: F(r, s) &\to G \\
    r &\mapsto ab \\
    t &\mapsto b
    .\]

-   This is clearly surjective since it hits all generators.

-   We'll show that \( ab, a \) satisfy all of the relations defining \( D_{2n} \), which factors \( \psi \) through \( \ker \pi \), yielding a surjection \( \tilde \psi: D_{2n} \twoheadrightarrow G \).

    -   \( (ab)^n = e \) by construction, \( b^2 = e \) by assumption, and
        \[
        b (ab) b^{-1}= babb^{-1}= ba = b^{-1}a^{-1}= (ab)^{-1}
        ,\]
        corresponding to the relation \( srs^{-1}= r^{-1} \). Here we've used that \( o(a) = o(b) = 2 \) implies \( a=a^{-1}, b=b^{-1} \).

-   Surjectivity of \( \tilde \psi \) yields \( 2n = \# D_{2n} \geq \# G \).

-   The claim is that \( \# G \geq 2n \), which forces \( \# G = 2n \). Then \( \tilde \psi \) will be a surjective group morphism between groups of the same order, and thus an isomorphism.

    -   We have \( \left\langle{ ab }\right\rangle\leq G \), so \( n\bigm|\# G \).
    -   Since \( b\not\in \left\langle{ ab }\right\rangle \), this forces \( \# G > n \), so \( \# G \geq 2n \).

> Remark: see a more direct proof in [Theorem 2.1 and Theorem 1.1 here](https://kconrad.math.uconn.edu/blurbs/grouptheory/dihedral2.pdf)
:::

### Fall 2019 Midterm \#1 \( \work \) {#fall-2019-midterm-1-work}

Let \( G \) be a group of order \( p^2q \) for \( p, q \) prime. Show that \( G \) has a nontrivial normal subgroup.

::: {.solution}
```{=tex}
\envlist
```
-   Write \( \# G = p^2 q \)

-   Cases: first assume \( p>q \), then do \( q<p \).

-   In any case, we have
    \[
    n_p \bigm|q &,\, n_p \equiv 1 \pmod p \implies n_p \in \left\{{ 1,q }\right\} \\ \\
    n_q \bigm|p^2 &,\, n_q \equiv 1 \pmod q \implies n_q \in \in \left\{{ 1, p, p^2}\right\} 
    .\]

-   **Case 1:** \( :p>q \).

-   If \( p>q \), then \( p\geq q+2 \) since \( p+1 \) can't be prime.

-   So \( q \) is not congruent to \( 1\pmod p \), forcing \( n_p = 1 \).

-   **Case 2:**: \( p< q \):

-   For the same reasons as above, \( p\not\equiv 1\pmod q \) forces \( n_q\neq p \).

-   If \( n_q = 1 \), we're done.

-   If \( n_q = p^2 \):

    -   Finer analysis....
:::

### Fall 2019 Midterm \#4 \( \work \) {#fall-2019-midterm-4-work}

Let \( p \) be a prime. Show that \( S_p = \left\langle{\tau, \sigma}\right\rangle \) where \( \tau \) is a transposition and \( \sigma \) is a \( p{\hbox{-}} \)cycle.

# Groups: Group Actions

## Fall 2012 \#1 \( \work \) {#fall-2012-1-work}

Let \( G \) be a finite group and \( X \) a set on which \( G \) acts.

a.  Let \( x\in X \) and \( G_x \coloneqq\left\{{g\in G {~\mathrel{\Big|}~}g\cdot x = x}\right\} \). Show that \( G_x \) is a subgroup of \( G \).

b.  Let \( x\in X \) and \( G\cdot x \coloneqq\left\{{g\cdot x {~\mathrel{\Big|}~}g\in G}\right\} \). Prove that there is a bijection between elements in \( G\cdot x \) and the left cosets of \( G_x \) in \( G \).

## Fall 2015 \#2 \( \work \) {#fall-2015-2-work}

Let \( G \) be a finite group, \( H \) a \( p{\hbox{-}} \)subgroup, and \( P \) a sylow \( p{\hbox{-}} \)subgroup for \( p \) a prime. Let \( H \) act on the left cosets of \( P \) in \( G \) by left translation.

Prove that this is an orbit under this action of length 1.

Prove that \( xP \) is an orbit of length 1 \( \iff H \) is contained in \( xPx^{-1} \).

## Spring 2016 \#5 \( \work \) {#spring-2016-5-work}

Let \( G \) be a finite group acting on a set \( X \). For \( x\in X \), let \( G_x \) be the stabilizer of \( x \) and \( G\cdot x \) be the orbit of \( x \).

a.  Prove that there is a bijection between the left cosets \( G/G_x \) and \( G\cdot x \).

b.  Prove that the center of every finite \( p{\hbox{-}} \)group \( G \) is nontrivial by considering that action of \( G \) on \( X=G \) by conjugation.

## Fall 2017 \#1 \( \work \) {#fall-2017-1-work}

Suppose the group \( G \) acts on the set \( A \). Assume this action is faithful (recall that this means that the kernel of the homomorphism from \( G \) to \( \operatorname{Sym}(A) \) which gives the action is trivial) and transitive (for all \( a, b \) in \( A \), there exists \( g \) in \( G \) such that \( g \cdot a = b \).)

a.  For \( a \in A \), let \( G_a \) denote the stabilizer of \( a \) in \( G \). Prove that for any \( a \in A \),
    \[
    \displaystyle\bigcap_{\sigma\in G} \sigma G_a \sigma^{-1}= \left\{{1}\right\}
    .\]

b.  Suppose that \( G \) is abelian. Prove that \( |G| = |A| \). Deduce that every abelian transitive subgroup of \( S_n \) has order \( n \).

## Fall 2018 \#2 \( \done \) {#fall-2018-2-done}

a.  Suppose the group \( G \) acts on the set \( X \) . Show that the stabilizers of elements in the same orbit are conjugate.

b.  Let \( G \) be a finite group and let \( H \) be a proper subgroup. Show that the union of the conjugates of \( H \) is strictly smaller than \( G \), i.e.
    \[
    \displaystyle\bigcup_{g\in G} gHg^{-1}\subsetneq G
    \]

c.  Suppose \( G \) is a finite group acting transitively on a set \( S \) with at least 2 elements. Show that there is an element of \( G \) with no fixed points in \( S \).

::: {.concept}
```{=tex}
\envlist
```
-   Orbit: \( G\cdot x \coloneqq\left\{{g\cdot x {~\mathrel{\Big|}~}g\in G}\right\} \subseteq X \)
-   Stabilizer: \( G_x \coloneqq\left\{{g\in G{~\mathrel{\Big|}~}g\cdot x = x}\right\} \leq G \)
-   Orbit-Stabilizer: \( G\cdot x \simeq G/G_x \).
-   \( abc\in H \iff b\in a^{-1}H c^{-1} \)
-   Set of orbits for \( G\curvearrowright X \), notated \( X/G \).
-   Set of fixed points for \( G\curvearrowright X \), notated \( X^g \).
-   Burnside's Lemma: \( {\left\lvert {X/G} \right\rvert} \cdot {\left\lvert {G} \right\rvert} = \sum_{g\in G} {\left\lvert {X^g} \right\rvert} \)
    -   Number of orbits equals average number of fixed points.
:::

::: {.solution}
```{=tex}
\envlist
```
::: {.proof title="of a"}
```{=tex}
\envlist
```
-   Fix \( x \) and let \( y\in G_x \) be another element in the orbit of \( x \).
-   Then there exists a \( g\in G \) such that \( g\cdot x = y \), so \( x = g^{-1}\cdot y \)
-   Then
    \[
    h \in G\cdot x 
    &\iff h\cdot x = x && \text{by being in the stabilizer} \\
    &\iff h\cdot (g^{-1}\cdot y) = g^{-1}\cdot y && \text{using that $x, y$ are in the same orbit} \\
    &\iff (g h g^{-1}) \cdot y = y \\
    &\iff ghg^{-1}\in G_y && \text{by the defn of the stabilizer}\\
    &\iff h\in g ^{-1}  G_y g
    ,\]

so every \( h\in G\cdot x \) is conjugate to some element in \( G_y \).
:::

::: {.proof title="of b"}
Let \( G \) act on its subgroups by conjugation,

-   The orbit \( G\cdot H \) is the set of all subgroups conjugate to \( H \), and

-   The stabilizer of \( H \) is \( G_H = N_G(H) \).

-   By orbit-stabilizer,
    \[
    G\cdot H = [G: G_H] = [G: N_G(H)]
    .\]

-   Since \( {\left\lvert {H} \right\rvert} = n \), and all of its conjugate also have order \( n \).

-   Note that
    \[
    H\leq N_G(H) \implies {\left\lvert {H} \right\rvert} \leq {\left\lvert {N_G(H)} \right\rvert} \implies {1\over {\left\lvert {N_G(H)} \right\rvert}} \leq {1\over {\left\lvert {H} \right\rvert}}
    ,\]

-   Now *strictly* bound the size of the union by overcounting their intersections at the identity:
    \[
    {\left\lvert {\displaystyle\bigcup_{g\in G}gHg^{-1}} \right\rvert} 
    &< (\text{Number of Conjugates of } H) \cdot (\text{Size of each conjugate}) \\ 
    & \text{strictly overcounts since they intersect in at least the identity} \\
    &= [G: N_G(H)] {\left\lvert {H} \right\rvert} \\
    &= {{\left\lvert {G} \right\rvert} \over {\left\lvert {N_G(H)} \right\rvert}} {\left\lvert {H} \right\rvert} \\
    & \text{since $G$ is finite} \\
    &\leq {{\left\lvert {G} \right\rvert} \over {\left\lvert {H} \right\rvert}} {\left\lvert {H} \right\rvert} \\
    &= {\left\lvert {G} \right\rvert}
    .\]
:::

::: {.proof title="of c"}
```{=tex}
\envlist
```
-   Let \( G\curvearrowright X \) transitively where \( {\left\lvert {X} \right\rvert} \geq 2 \)
-   An action is transitive iff there is only one orbit, so \( {\left\lvert {X/G} \right\rvert} = 1 \).
-   Apply Burnside's Lemma
    \[
    1 = {\left\lvert {X/G} \right\rvert} = \frac{1}{{\left\lvert {G} \right\rvert}} \sum_{g\in G} {\left\lvert {X^g} \right\rvert} \implies {\left\lvert {G} \right\rvert} = \sum_{g\in G} {\left\lvert {X^g} \right\rvert}
    \]
-   Note that \( X^e = X \), since the identity must fix every element, so \( {\left\lvert {X^e} \right\rvert} \geq 2 \).
-   Not *every* other term in the sum can be greater than 1, otherwise the RHS is greater than the size of \( G \)
-   Thus we must have \( {\left\lvert {X^g} \right\rvert} = 0 \) for some \( g\in G \), i.e. \( g \) has no fixed points in \( X \).
:::
:::

# Groups: Sylow Theory

## Fall 2019 \#1 \( \done \) {#fall-2019-1-done}

Let \( G \) be a finite group with \( n \) distinct conjugacy classes. Let \( g_1 \cdots g_n \) be representatives of the conjugacy classes of \( G \). Prove that if \( g_i g_j = g_j g_i \) for all \( i, j \) then \( G \) is abelian.

::: {.concept}
```{=tex}
\envlist
```
-   Centralizer:
    \[
    C_G(h) = Z(h) = \left\{{g\in G {~\mathrel{\Big|}~}[g,h] = 1}\right\}
    \quad\text{Centralizer}
    \]
-   Class equation:
    \[
    {\left\lvert {G} \right\rvert} = \sum_{\substack{\text{One $h$ from each } \\ \text{ conjugacy class}}} \frac{{\left\lvert {G} \right\rvert}}{{\left\lvert {Z(h)} \right\rvert}}
    \]
-   Notation:
    \[
    h^g &= ghg^{-1}\\
    h^G &= \left\{{ h^g {~\mathrel{\Big|}~}g\in G}\right\} \quad\text{Conjugacy Class}\\
    H^g &= \left\{{h^g {~\mathrel{\Big|}~}h\in H}\right\} \\
    N_G(H) &= \left\{{g\in G {~\mathrel{\Big|}~}H^g = H}\right\} \supseteq H \quad\text{Normalizer}
    .\]
:::

::: {.solution}
```{=tex}
\envlist
```
::: {.claim title="1"}
\[
{\left\lvert {h^G} \right\rvert} = [G: Z(h)]
.\]
:::

::: {.claim title="2"}
\[
{\left\lvert {\left\{{H^g {~\mathrel{\Big|}~}g\in G}\right\}} \right\rvert} = [G: N_G(H)]
.\]
:::

::: {.proof title="of claim 2"}
```{=tex}
\envlist
```
-   Let \( G\curvearrowright\left\{{H {~\mathrel{\Big|}~}H \leq G}\right\} \) by \( H \mapsto gHg^{-1} \).
-   Then the \( \mathcal O_H \) is the set of conjugate subgroups, \( \mathrm{Stab}(H) = N_G(H) \).
-   So Orbit-Stabilizer says \( \mathcal O_h \cong G/\mathrm{Stab}(H) \); then just take sizes.
:::

::: {.claim title="3"}
\( \cup_{g\in G} H^g = \cup_{g\in G} gHg^{-1}\subsetneq G \) for any proper \( H \leq G \).
:::

::: {.proof title="of claim 3"}
-   By theorem 2, since each coset is of size \( {\left\lvert {H} \right\rvert} \), which only intersect at the identity, and there are exactly \( [G: N_G(H)] \) of them
    \[
    {\left\lvert {\cup_{g\in G} H^g} \right\rvert} 
    &= \qty{ {\left\lvert {H} \right\rvert} - 1} [G: N_G(H)] + 1\\
    &= {\left\lvert {H} \right\rvert} [G: N_G(H)]  - [G:N_G(H)] + 1\\
    &= {\left\lvert {G} \right\rvert} \frac{{\left\lvert {G} \right\rvert}}{{\left\lvert {N_G(H)} \right\rvert}} - \frac{{\left\lvert {G} \right\rvert}}{{\left\lvert {N_G(H)} \right\rvert}} + 1 \\
    &\leq {\left\lvert {H} \right\rvert} \frac{{\left\lvert {G} \right\rvert}}{{\left\lvert {H} \right\rvert}} - \frac{{\left\lvert {G} \right\rvert}}{{\left\lvert {H} \right\rvert}} + 1 \\
    &= {\left\lvert {G} \right\rvert} - ([G: H] - 1) \\
    &< {\left\lvert {G} \right\rvert} 
    ,\]
    where we use the fact that \( H \subseteq N_G(H) \implies {\left\lvert {H} \right\rvert} \leq {\left\lvert {N_G(H)} \right\rvert} \implies \frac{1}{{\left\lvert {N_G(H)} \right\rvert}} \leq \frac{1}{{\left\lvert {H} \right\rvert}} \), and since \( H < G \) is proper, \( [G:H] \geq 2 \).

-   Since \( [g_i, g_j] = 1 \), we have \( g_i \in Z(g_j) \) for every \( i, j \).

-   Then
    \[
    g\in G 
    &\implies g = g_i^h \quad \text{ for some } h \\
    &\implies g \in Z(g_\mathbf{j})^h \quad\text{for every } j \text{ since }g_i \in Z(g_j) ~\forall j \\
    &\implies g \in \cup_{h\in G} Z(g_j)^h \quad\text{for every } j\\
    &\implies G \subseteq \cup_{h\in G} Z(g_j)^h \quad\text{for every } j
    ,\]

    which by Theorem 3, if \( Z(g_j) < G \) were proper, then the RHS is properly contained in \( G \).

-   So it must be the case that that \( Z(g_j) \) is not proper and thus equal to \( G \) for every \( j \).

-   But \( Z(g_i) = G \iff g_i \in Z(G) \), and so each conjugacy class is size one.

-   So for every \( g\in G \), we have \( g = g_j \) for some \( j \), and thus \( g = g_j \in Z(g_j) = Z(G) \), so \( g \) is central.

-   Then \( G\subseteq Z(G) \) and \( G \) is abelian.
:::
:::

## Fall 2019 Midterm \#2 \( \work \) {#fall-2019-midterm-2-work}

Let \( G \) be a finite group and let \( P \) be a sylow \( p{\hbox{-}} \)subgroup for \( p \) prime. Show that \( N(N(P)) = N(P) \) where \( N \) is the normalizer in \( G \).

## Fall 2013 \#2 \( \work \) {#fall-2013-2-work}

Let \( G \) be a group of order 30.

a.  Show that \( G \) has a subgroup of order 15.

b.  Show that every group of order 15 is cyclic.

c.  Show that \( G \) is isomorphic to some semidirect product \( {\mathbb{Z}}_{15} \rtimes{\mathbb{Z}}_2 \).

d.  Exhibit three nonisomorphic groups of order 30 and prove that they are not isomorphic. You are not required to use your answer to (c).

## Spring 2014 \#2 \( \work \) {#spring-2014-2-work}

Let \( G\subset S_9 \) be a Sylow-3 subgroup of the symmetric group on 9 letters.

a.  Show that \( G \) contains a subgroup \( H \) isomorphic to \( {\mathbb{Z}}_3 \times{\mathbb{Z}}_3 \times{\mathbb{Z}}_3 \) by exhibiting an appropriate set of cycles.

b.  Show that \( H \) is normal in \( G \).

c.  Give generators and relations for \( G \) as an abstract group, such that all generators have order 3. Also exhibit elements of \( S_9 \) in cycle notation corresponding to these generators.

d.  Without appealing to the previous parts of the problem, show that \( G \) contains an element of order 9.

## Fall 2014 \#2 \( \work \) {#fall-2014-2-work}

Let \( G \) be a group of order 96.

a.  Show that \( G \) has either one or three 2-Sylow subgroups.

b.  Show that either \( G \) has a normal subgroup of order 32, or a normal subgroup of order 16.

## Spring 2016 \#3 \( \work \) {#spring-2016-3-work}

a.  State the three Sylow theorems.

b.  Prove that any group of order 1225 is abelian.

c.  Write down exactly one representative in each isomorphism class of abelian groups of order 1225.

## Spring 2017 \#2 \( \work \) {#spring-2017-2-work}

a.  How many isomorphism classes of abelian groups of order 56 are there? Give a representative for one of each class.

b.  Prove that if \( G \) is a group of order 56, then either the Sylow-2 subgroup or the Sylow-7 subgroup is normal.

c.  Give two non-isomorphic groups of order 56 where the Sylow-7 subgroup is normal and the Sylow-2 subgroup is *not* normal. Justify that these two groups are not isomorphic.

## Fall 2017 \#2 \( \work \) {#fall-2017-2-work}

a.  Classify the abelian groups of order 36.

    > For the rest of the problem, assume that \( G \) is a non-abelian group of order 36. You may assume that the only subgroup of order 12 in \( S_4 \) is \( A_4 \) and that \( A_4 \) has no subgroup of order 6.

b.  Prove that if the 2-Sylow subgroup of \( G \) is normal, \( G \) has a normal subgroup \( N \) such that \( G/N \) is isomorphic to \( A_4 \).

c.  Show that if \( G \) has a normal subgroup \( N \) such that \( G/N \) is isomorphic to \( A_4 \) and a subgroup \( H \) isomorphic to \( A_4 \) it must be the direct product of \( N \) and \( H \).

d.  Show that the dihedral group of order 36 is a non-abelian group of order 36 whose Sylow-2 subgroup is not normal.

## Fall 2012 \#2 \( \work \) {#fall-2012-2-work}

Let \( G \) be a group of order 30.

a.  Show that \( G \) contains normal subgroups of orders 3, 5, and 15.

b.  Give all possible presentations and relations for \( G \).

c.  Determine how many groups of order 30 there are up to isomorphism.

## Fall 2018 \#1 \( \done \) {#fall-2018-1-done}

Let \( G \) be a finite group whose order is divisible by a prime number \( p \). Let \( P \) be a normal \( p{\hbox{-}} \)subgroup of \( G \) (so \( {\left\lvert {P} \right\rvert} = p^c \) for some \( c \)).

a.  Show that \( P \) is contained in every Sylow \( p{\hbox{-}} \)subgroup of \( G \).

b.  Let \( M \) be a maximal proper subgroup of \( G \). Show that either \( P \subseteq M \) or \( |G/M | = p^b \) for some \( b \leq c \).

::: {.concept}
```{=tex}
\envlist
```
-   Sylow 2: All Sylow \( p{\hbox{-}} \)subgroups are conjugate.
-   \( {\left\lvert {HK} \right\rvert} = {\left\lvert {H} \right\rvert} {\left\lvert {K} \right\rvert} / {\left\lvert {H\cap K} \right\rvert} \).
-   Lagrange's Theorem: \( H\leq G \implies {\left\lvert {H} \right\rvert} \bigm|{\left\lvert {G} \right\rvert} \)
:::

::: {.solution}
```{=tex}
\envlist
```
::: {.proof title="of a"}
```{=tex}
\envlist
```
-   Every \( p{\hbox{-}} \)subgroup is contained in some Sylow \( p{\hbox{-}} \)subgroup, so \( P \subseteq S_p^i \) for some \( S_p^i \in \mathrm{Syl}_p(G) \).

-   \( P {~\trianglelefteq~}G \iff gPg^{-1}= P \) for all \( g\in G \).

-   Let \( S_p^j \) be any other Sylow \( p{\hbox{-}} \)subgroup,

-   Since Sylow \( p{\hbox{-}} \)subgroups are all conjugate \( gS_p^i g^{-1}= S_p^j \) for *some* \( g\in G \).

-   Then
    \[
    P = gPg^{-1}\subseteq gS_p^i g^{-1}= S_p^j
    .\]
:::

::: {.proof title="of b"}
```{=tex}
\envlist
```
-   If \( P \) is not contained in \( M \), then \( M < MP \) is a proper subgroup

-   By maximality of \( M \), \( MP = G \)

-   Note that \( M\cap P \leq P \) and \( {\left\lvert {P} \right\rvert} = p^c \) implies \( {\left\lvert {M\cap P} \right\rvert} = p^a \) for some \( a\leq c \) by Lagrange

-   Then write
    \[
    G = MP
    &\iff {\left\lvert {G} \right\rvert} = \frac{{\left\lvert {M} \right\rvert} {\left\lvert {P} \right\rvert}}{{\left\lvert {M\cap P} \right\rvert}} \\ \\
    &\iff { {\left\lvert {G} \right\rvert} \over {\left\lvert {M} \right\rvert}} = {{\left\lvert {P} \right\rvert}  \over {\left\lvert {M\cap P} \right\rvert}} = {p^c \over p^a} = p^{c-a} \coloneqq p^b
    \]

    where \( a\leq c \implies 0 \leq c-b \leq c \) so \( 0\leq b \leq c \).
:::
:::

## Fall 2019 \#2 \( \done \) {#fall-2019-2-done}

Let \( G \) be a group of order 105 and let \( P, Q, R \) be Sylow 3, 5, 7 subgroups respectively.

a.  Prove that at least one of \( Q \) and \( R \) is normal in \( G \).

b.  Prove that \( G \) has a cyclic subgroup of order 35.

c.  Prove that both \( Q \) and \( R \) are normal in \( G \).

d.  Prove that if \( P \) is normal in \( G \) then \( G \) is cyclic.

::: {.concept}
```{=tex}
\envlist
```
-   The \( pqr \) theorem.

-   Sylow 3: \( {\left\lvert {G} \right\rvert} = p^n m \) implies \( n_p \bigm|m \) and \( n_p \cong 1 \pmod p \).

-   **Theorem**: If \( H, K \leq G \) and any of the following conditions hold, \( HK \) is a subgroup:

    -   \( H{~\trianglelefteq~}G \) (wlog)
    -   \( [H, K] = 1 \)
    -   \( H \leq N_G(K) \)

-   **Theorem**: For a positive integer \( n \), all groups of order \( n \) are cyclic \( \iff n \) is squarefree and, for each pair of distinct primes \( p \) and \( q \) dividing \( n \), \( q - 1 \neq 0 \pmod p \).

-   **Theorem:**
    \[
    A_i{~\trianglelefteq~}G, \quad G = A_1 \cdots A_k,\quad A_k \cap\prod_{i\neq k} A_i = \emptyset \implies G = \prod A_i
    .\]

-   The intersection of subgroups is a again a subgroup.

-   Any subgroups of coprime order intersect trivially?
:::

::: {.solution}
```{=tex}
\envlist
```
::: {.proof title="of 1"}
```{=tex}
\envlist
```
-   We have

-   \( n_3 \bigm|5\cdot 7, \quad n_3 \cong 1 \pmod 3 \implies n_3 \in \left\{{1, 5, 7, 35}\right\} \setminus \left\{{5, 35}\right\} \)

-   \( n_5 \bigm|3\cdot 7, \quad n_5 \cong 1 \pmod 5 \implies n_5 \in \left\{{1, 3, 7, 21}\right\}\setminus \left\{{3, 7}\right\} \)

-   \( n_7 \bigm|3\cdot 5, \quad n_7 \cong 1 \pmod 7 \implies n_7 \in \left\{{1, 3, 5, 15}\right\}\setminus\left\{{3, 5}\right\} \)

-   Thus
    \[
    n_3 \in \left\{{1, 7}\right\} \quad n_5 \in \left\{{1, 21}\right\} \quad n_7 \in \left\{{1, 15}\right\}
    .\]

-   Toward a contradiction, if \( n_5\neq 1 \) and \( n_7 \neq 1 \), then
    \[
    {\left\lvert {{\operatorname{Syl}}(5) \cup{\operatorname{Syl}}(7)} \right\rvert} = (5-1)n_5 + (7-1)n_7 + 1 
    &= 4(21) + 6(15) = 174 > 105 \text{ elements}
    \]
    using the fact that Sylow \( p{\hbox{-}} \)subgroups for distinct primes \( p \) intersect trivially (?).
:::

::: {.proof title="of 2"}
```{=tex}
\envlist
```
-   By (a), either \( Q \) or \( R \) is normal.
-   Thus \( QR \leq G \) is a subgroup, and it has order \( {\left\lvert {Q} \right\rvert} \cdot {\left\lvert {R} \right\rvert} = 5\cdot 7 = 35 \).
-   By the \( pqr \) theorem, since \( 5 \) does not divide \( 7-1=6 \), \( QR \) is cyclic.
:::

```{=tex}
\todo[inline]{Part (b) not finished!}
```
::: {.proof title="of 3"}
```{=tex}
\envlist
```
-   We want to show \( Q, R{~\trianglelefteq~}G \), so we proceed by showing \( \textbf{not }\qty{n_5 = 21 \text{ or } n_7 = 15} \), which is equivalent to \( \qty{n_5 = 1 \text{ and } n_7 = 1} \) by the previous restrictions.

-   Note that we can write
    \[
    G = \left\{{\text{elements of order } n}\right\} {\textstyle\coprod}\left\{{\text{elements of order not } n}\right\}
    .\]
    for any \( n \), so we count for \( n=5, 7 \):

    -   Elements in \( QR \) of order **not** equal to 5: \( {\left\lvert {QR - Q\left\{{\operatorname{id}}\right\} + \left\{{\operatorname{id}}\right\}} \right\rvert} = 35 - 5 + 1 = 31 \)
    -   Elements in \( QR \) of order **not** equal to 7: \( {\left\lvert {QR - \left\{{\operatorname{id}}\right\}R + \left\{{\operatorname{id}}\right\}} \right\rvert} = 35 - 7 + 1 = 29 \)

-   Since \( QR \leq G \), we have

    -   Elements in \( G \) of order **not** equal to 5 \( \geq 31 \).
    -   Elements in \( G \) of order **not** equal to 7 \( \geq 29 \).

-   Now both cases lead to contradictions:

    -   \( n_5 = 21 \):
        \[
        {\left\lvert {G} \right\rvert}  &= {\left\lvert {\left\{{\text{elements of order } 5}\right\} {\textstyle\coprod}\left\{{\text{elements of order not } 5}\right\}} \right\rvert} \\
        &\geq n_5(5-1) + 31 = 21(4) + 31 = 115 > 105 = {\left\lvert {G} \right\rvert}
        .\]

    -   \( n_7 = 15 \):
        \[
        {\left\lvert {G} \right\rvert}  &= {\left\lvert {\left\{{\text{elements of order } 7}\right\} {\textstyle\coprod}\left\{{\text{elements of order not } 7}\right\}} \right\rvert} \\
        &\geq n_7(7-1) + 29 = 15(6) + 29 = 119 > 105 = {\left\lvert {G} \right\rvert}
        .\]
:::

::: {.proof title="of 4"}
Suppose \( P \) is normal and recall \( {\left\lvert {P} \right\rvert} = 3, {\left\lvert {Q} \right\rvert} = 5, {\left\lvert {R} \right\rvert} = 7 \).

-   \( P\cap QR = \left\{{e}\right\} \) since \( (3, 35) = 1 \)
-   \( R\cap PQ = \left\{{e}\right\} \) since \( (5, 21) = 1 \)
-   \( Q\cap RP = \left\{{e}\right\} \) since \( (7, 15) = 1 \)

We also have \( PQR = G \) since \( {\left\lvert {PQR} \right\rvert} = {\left\lvert {G} \right\rvert} \) (???).

We thus have an internal direct product
\[
G \cong P\times Q \times R \cong {\mathbb{Z}}_3 \times{\mathbb{Z}}_5 \times{\mathbb{Z}}_7 \cong {\mathbb{Z}}_{105}
.\]
by the Chinese Remainder Theorem, which is cyclic.
:::
:::

## Spring 2021 \#3 \( \work \) {#spring-2021-3-work}

a.  Show that every group of order \( p^2 \) with \( p \) prime is abelian.

b.  State the 3 Sylow theorems.

c.  Show that any group of order \( 4225 = 5^2 13^2 \) is abelian.

d.  Write down one representative from each isomorphism class of abelian groups of order 4225.

## Fall 2020 \#1 \( \work \) {#fall-2020-1-work}

a.  Using Sylow theory, show that every group of order \( 2p \) where \( p \) is prime is not simple.

b.  Classify all groups of order \( 2p \) and justify your answer. For the nonabelian group(s), give a presentation by generators and relations.

## Fall 2020 \#2 \( \work \) {#fall-2020-2-work}

Let \( G \) be a group of order 60 whose Sylow 3-subgroup is normal.

a.  Prove that \( G \) is solvable.

b.  Prove that the Sylow 5-subgroup is also normal.

# Groups: Classification

## Spring 2020 \#1 \( \work \) {#spring-2020-1-work}

a.  Show that any group of order 2020 is solvable.

b.  Give (without proof) a classification of all abelian groups of order 2020.

c.  Describe one nonabelian group of order 2020.

```{=tex}
\todo[inline]{Work this problem.}
```
## Spring 2019 \#3 \( \done \) {#spring-2019-3-done}

How many isomorphism classes are there of groups of order 45?

Describe a representative from each class.

::: {.concept}
```{=tex}
\envlist
```
-   Sylow theorems:
-   \( n_p \cong 1 \pmod p \)
-   \( n_p \bigm|m \).
:::

::: {.solution}
```{=tex}
\envlist
```
-   It turns out that \( n_3 = 1 \) and \( n_5 = 1 \), so \( G \cong S_3 \times S_5 \) since both subgroups are normal.

-   There is only one possibility for \( S_5 \), namely \( S_5\cong {\mathbb{Z}}/(5) \).

-   There are two possibilities for \( S_3 \), namely \( S_3 \cong {\mathbb{Z}}/(3^2) \) and \( {\mathbb{Z}}/(3)^2 \).

-   Thus

-   \( G \cong {\mathbb{Z}}/(9) \times{\mathbb{Z}}/(5) \), or

-   \( G \cong {\mathbb{Z}}/(3)^2 \times{\mathbb{Z}}/(5) \).
:::

```{=tex}
\todo[inline]{Revisit, seems short.}
```
## Spring 2012 \#3 \( \work \) {#spring-2012-3-work}

Let \( G \) be a group of order 70.

a.  Show that \( G \) is not simple.

b.  Exhibit 3 nonisomorphic groups of order 70 and prove that they are not isomorphic.

## Fall 2016 \#3 \( \work \) {#fall-2016-3-work}

How many groups are there up to isomorphism of order \( pq \) where \( p<q \) are prime integers?

## Spring 2018 \#1 \( \done \) {#spring-2018-1-done}

a.  Use the Class Equation (equivalently, the conjugation action of a group on itself) to prove that any \( p{\hbox{-}} \)group (a group whose order is a positive power of a prime integer \( p \)) has a nontrivial center.

b.  Prove that any group of order \( p^2 \) (where \( p \) is prime) is abelian.

c.  Prove that any group of order \( 5^2 \cdot 7^2 \) is abelian.

d.  Write down exactly one representative in each isomorphism class of groups of order \( 5^2 \cdot 7^2 \).

::: {.concept}
```{=tex}
\envlist
```
-   Centralizer: \( C_G(x) = \left\{{g\in G {~\mathrel{\Big|}~}[gx] = 1}\right\} \).

-   Class Equation: \( {\left\lvert {G} \right\rvert} = {\left\lvert {Z(G)} \right\rvert} + \sum [G: C_G(x_i)] \)

-   \( G/Z(G) \) cyclic \( \iff G \) is abelian.
    \[
    G/Z(G) = \left\langle{xZ}\right\rangle 
    &\iff g\in G \implies gZ = x^mZ \\
    &\iff g(x^m)^{-1}\in Z \\
    &\iff g = x^m z {\quad \operatorname{for some} \quad}z\in Z\\
    &\implies gh = x^mz_1 x^n z_2 = x^n z_2 x^m z_1 = hg
    .\]

-   Every group of order \( p^2 \) is abelian.

-   Classification of finite abelian groups.
:::

::: {.solution}
```{=tex}
\envlist
```
::: {.proof title="of a"}
Strategy: get \( p \) to divide \( {\left\lvert {Z(G)} \right\rvert} \).

-   Apply the class equation:
    \[
    {\left\lvert {G} \right\rvert} = {\left\lvert {Z(G)} \right\rvert} + \sum [G: C_G(x_i)]
    .\]

-   Since \( C_G(x_i) \leq G \) and \( {\left\lvert {G} \right\rvert} = p^k \), by Lagrange \( {\left\lvert {C_G(x_i)} \right\rvert} = p^\ell \) for some \( 0\leq \ell \leq k \).

-   Since \( {\left\lvert {G} \right\rvert} = p^k \) for some \( k \) and \( Z(G), C_G(x_i) \leq G \) are subgroups, their orders are powers of \( p \).

-   Use
    \[[G: C_G(x_i)] = 1 \iff C_G(x_i) = G \iff \left\{{g\in G{~\mathrel{\Big|}~}gx_ig^{-1}= x_i}\right\} = G \iff x_i \in Z(G).\]

    -   Thus every index appearing in the sum is greater than 1, and thus equal to \( p^{\ell_i} \) for some \( 1\leq \ell_i \leq k \)
    -   So \( p \) divides every term in the sum

-   Rearrange
    \[
    {\left\lvert {G} \right\rvert} -  \sum [G: C_G(x_i)]
    = {\left\lvert {Z(G)} \right\rvert} 
    .\]

-   \( p \) divides both terms on the LHS, so must divide the RHS, so \( {\left\lvert {Z(G)} \right\rvert} \geq p \).
:::

::: {.proof title="of b"}
Strategy: examine \( {\left\lvert {G/Z(G)} \right\rvert} \) by cases.

-   \( 1 \): Then \( G = Z(G) \) and \( G \) is abelian.
-   \( p \): Then \( G/Z(G) \) is cyclic so \( G \) is abelian
-   \( p^2 \): Not possible, since \( {\left\lvert {Z(G)} \right\rvert} > 1 \) by (a).
:::

::: {.proof title="of c"}
```{=tex}
\envlist
```
-   By Sylow

    -   \( n_5 \bigm|7^2,\quad n_5\cong 1\pmod 5 \implies n_5\in\left\{{1, 7, 49}\right\}\setminus\left\{{7, 49}\right\} = \left\{{1}\right\} \implies n_5 = 1 \)
    -   \( n_7 \bigm|5^2, \quad n_7 \cong 1 \pmod 7 \implies n_7 \in \left\{{1, 5, 25}\right\}\setminus\left\{{5, 25}\right\} =\left\{{1}\right\} \implies n_7 = 1 \)

-   By recognition of direct products, \( G = S_5 \times S_7 \)

    -   By above, \( S_5, S_7{~\trianglelefteq~}G \)
    -   Check \( S_5\cap S_7 = \left\{{e}\right\} \) since they have coprime order.
    -   Check \( S_5S_7 = G \) since \( {\left\lvert {S_5 S_7} \right\rvert} = 5^2 7^2 = {\left\lvert {G} \right\rvert} \)

-   By (b), \( S_5, S_7 \) are abelian since they are groups of order \( p^2 \)

-   The direct product of abelian groups is abelian.
:::

::: {.proof title="of d"}
```{=tex}
\envlist
```
-   \( {\mathbb{Z}}_{5^2} \times{\mathbb{Z}}_{7^2} \)
-   \( {\mathbb{Z}}_{5}^2 \times{\mathbb{Z}}_{7^2} \)
-   \( {\mathbb{Z}}_{5^2} \times{\mathbb{Z}}_{7}^2 \)
-   \( {\mathbb{Z}}_{5}^2 \times{\mathbb{Z}}_{7}^2 \)
:::
:::

# Groups: Simple and Solvable

## \( \star \) Fall 2016 \#7 \( \work \) {#star-fall-2016-7-work}

a.  Define what it means for a group \( G \) to be *solvable*.

b.  Show that every group \( G \) of order 36 is solvable.

> Hint: you can use that \( S_4 \) is solvable.

## Spring 2015 \#4 \( \work \) {#spring-2015-4-work}

Let \( N \) be a positive integer, and let \( G \) be a finite group of order \( N \).

a.  Let \( \operatorname{Sym}G \) be the set of all bijections from \( G\to G \) viewed as a group under composition. Note that \( \operatorname{Sym}G \cong S_N \). Prove that the Cayley map
    \[
    C: G&\to \operatorname{Sym}G\\
    g &\mapsto (x\mapsto gx)
    \]
    is an injective homomorphism.

b.  Let \( \Phi: \operatorname{Sym}G\to S_N \) be an isomorphism. For \( a\in G \) define \( \varepsilon(a) \in \left\{{\pm 1}\right\} \) to be the sign of the permutation \( \Phi(C(a)) \). Suppose that \( a \) has order \( d \). Prove that \( \varepsilon(a) = -1 \iff d \) is even and \( N/d \) is odd.

c.  Suppose \( N> 2 \) and \( n\equiv 2 \pmod 4 \). Prove that \( G \) is not simple.

> Hint: use part (b).

## Spring 2014 \#1 \( \work \) {#spring-2014-1-work}

Let \( p, n \) be integers such that \( p \) is prime and \( p \) does not divide \( n \). Find a real number \( k = k (p, n) \) such that for every integer \( m\geq k \), every group of order \( p^m n \) is not simple.

## Fall 2013 \#1 \( \work \) {#fall-2013-1-work}

Let \( p, q \) be distinct primes.

a.  Let \( \mkern 1.5mu\overline{\mkern-1.5muq\mkern-1.5mu}\mkern 1.5mu \in {\mathbb{Z}}_p \) be the class of \( q\pmod p \) and let \( k \) denote the order of \( \mkern 1.5mu\overline{\mkern-1.5muq\mkern-1.5mu}\mkern 1.5mu \) as an element of \( {\mathbb{Z}}_p^{\times} \). Prove that no group of order \( pq^k \) is simple.

b.  Let \( G \) be a group of order \( pq \), and prove that \( G \) is not simple.

## Spring 2013 \#4 \( \work \) {#spring-2013-4-work}

Define a *simple group*. Prove that a group of order 56 can not be simple.

## Fall 2019 Midterm \#3 \( \work \) {#fall-2019-midterm-3-work}

Show that there exist no simple groups of order 148.

# Commutative Algebra

## Spring 2020 \#5 \( \done \) {#spring-2020-5-done}

Let \( R \) be a ring and \( f: M\to N \) and \( g: N\to M \) be \( R{\hbox{-}} \)module homomorphisms such that \( g\circ f = \operatorname{id}_M \). Show that \( N \cong \operatorname{im}f \oplus \ker g \).

## Fall 2019 \#3 \( \work \) {#fall-2019-3-work}

Let \( R \) be a ring with the property that for every \( a \in R, a^2 = a \).

a.  Prove that \( R \) has characteristic 2.

b.  Prove that \( R \) is commutative.

::: {.concept}
```{=tex}
\envlist
```
-   Todo
:::

::: {.strategy}
```{=tex}
\envlist
```
-   Just fiddle with direct computations.
-   Context hint: that we should be considering things like \( x^2 \) and \( a+b \).
:::

::: {.solution}
```{=tex}
\envlist
```
::: {.proof title="of a"}
\[
2a  = (2a)^2 = 4a^2 = 4a \implies 2a = 0
.\]
Note that this implies \( x = -x \) for all \( x\in R \).
:::

::: {.proof title="of b"}
\[
a+b = (a+b)^2 &= a^2 + ab + ba + b^2 = a + ab + ba + b \\
&\implies ab + ba = 0 \\
&\implies ab = -ba \\
&\implies ab = ba \quad\text{by (a)}
.\]
:::
:::

## Fall 2019 \#6 \( \done \) {#fall-2019-6-done}

Let \( R \) be a commutative ring with multiplicative identity. Assume Zorn's Lemma.

a.  Show that
    \[
    N = \{r \in R \mathrel{\Big|}r^n = 0 \text{ for some } n > 0\}
    \]
    is an ideal which is contained in any prime ideal.

b.  Let \( r \) be an element of \( R \) not in \( N \). Let \( S \) be the collection of all proper ideals of \( R \) not containing any positive power of \( r \). Use Zorn's Lemma to prove that there is a prime ideal in \( S \).

c.  Suppose that \( R \) has exactly one prime ideal \( P \) . Prove that every element \( r \) of \( R \) is either nilpotent or a unit.

::: {.concept}
```{=tex}
\envlist
```
-   Prime ideal: \( \mathfrak{p} \) is prime iff \( ab \in \mathfrak{p} \implies a\in \mathfrak{p} \) or \( b\in \mathfrak{p} \).

-   Silly fact: 0 is in every ideal!

-   **Zorn's Lemma:** Given a poset, if every chain has an upper bound, then there is a maximal element. (Chain: totally ordered subset.)

-   **Corollary:** If \( S\subset R \) is multiplicatively closed with \( 0\not\in S \) then \( \left\{{I {~\trianglelefteq~}R {~\mathrel{\Big|}~}J\cap S = \emptyset}\right\} \) has a maximal element.

    ```{=tex}
    \todo[inline]{Prove this}
    ```

-   **Theorem:** If \( R \) is commutative, maximal \( \implies \) prime for ideals.

    ```{=tex}
    \todo[inline]{Prove this}
    ```

-   **Theorem:** Non-units are contained in a maximal ideal. (See HW?)
:::

::: {.solution}
```{=tex}
\envlist
```
::: {.proof title="of a"}
```{=tex}
\envlist
```
-   Let \( \mathfrak{p} \) be prime and \( x\in N \).
-   Then \( x^k = 0 \in \mathfrak{p} \) for some \( k \), and thus \( x^k = x x^{k-1} \in \mathfrak p \).
-   Since \( \mathfrak p \) is prime, inductively we obtain \( x\in\mathfrak p \).
:::

::: {.proof title="of b"}
```{=tex}
\envlist
```
-   Let \( S = \left\{{r^k \mathrel{\Big|}k\in {\mathbb{N}}}\right\} \) be the set of positive powers of \( r \).

-   Then \( S^2 \subseteq S \), since \( r^{k_1}r^{k_2} = r^{k_1+k_2} \) is also a positive power of \( r \), and \( 0\not\in S \) since \( r\neq 0 \) and \( r\not\in N \).

-   By the corollary, \( \left\{{I {~\trianglelefteq~}R {~\mathrel{\Big|}~}I\cap S = \emptyset}\right\} \) has a maximal element \( \mathfrak{p} \).

-   Since \( R \) is commutative, \( \mathfrak{p} \) is prime.
:::

::: {.proof title="of c"}
```{=tex}
\envlist
```
-   Suppose \( R \) has a unique prime ideal \( \mathfrak{p} \).

-   Suppose \( r\in R \) is not a unit, and toward a contradiction, suppose that \( r \) is also not nilpotent.

-   Since \( r \) is not a unit, \( r \) is contained in some maximal (and thus prime) ideal, and thus \( r \in \mathfrak{p} \).

-   Since \( r\not\in N \), by (b) there is a maximal ideal \( \mathfrak{m} \) that avoids all positive powers of \( r \). Since \( \mathfrak{m} \) is prime, we must have \( \mathfrak{m} = \mathfrak{p} \). But then \( r\not\in \mathfrak{p} \), a contradiction.
:::
:::

## Spring 2019 \#6 \( \done \) {#spring-2019-6-done}

Let \( R \) be a commutative ring with 1.

> Recall that \( x \in R \) is nilpotent iff \( xn = 0 \) for some positive integer \( n \).

a.  Show that every proper ideal of \( R \) is contained within a maximal ideal.

b.  Let \( J(R) \) denote the intersection of all maximal ideals of \( R \). Show that \( x \in J(R) \iff 1 + rx \) is a unit for all \( r \in R \).

c.  Suppose now that \( R \) is finite. Show that in this case \( J(R) \) consists precisely of the nilpotent elements in R.

::: {.concept}
```{=tex}
\envlist
```
-   Definitions:
    \[
    N(R) &\coloneqq\left\{{x\in R {~\mathrel{\Big|}~}x^n = 0 \text{ for some } n}\right\} \\
    J(R) &\coloneqq\cap_{{\mathfrak{m}}\in \operatorname{mSpec}} {\mathfrak{m}}
    .\]

-   Zorn's lemma: if \( P \) is a poset in which every chain has an upper bound, \( P \) contains a maximal element.
:::

::: {.solution}
```{=tex}
\envlist
```
::: {.proof title="of a"}
Define the set of proper ideals
\[
S = \left\{{J {~\mathrel{\Big|}~}I   \subseteq J < R}\right\}
,\]

which is a poset under set inclusion.

Given a chain \( J_1 \subseteq \cdots \), there is an upper bound \( J \coloneqq\cup J_i \), so Zorn's lemma applies.
:::

::: {.proof title="of b, $\\implies$"}
\( \implies \):

-   We will show that \( x\in J(R) \implies 1+x \in R^{\times} \), from which the result follows by letting \( x=rx \).

-   Let \( x\in J(R) \), so it is in every maximal ideal, and suppose toward a contradiction that \( 1+x \) is **not** a unit.

-   Then consider \( I = \left\langle{1+x}\right\rangle {~\trianglelefteq~}R \). Since \( 1+x \) is not a unit, we can't write \( s(1+x) = 1 \) for any \( s\in R \), and so \( 1 \not\in I \) and \( I\neq R \)

-   So \( I < R \) is proper and thus contained in some maximal proper ideal \( \mathfrak{m} < R \) by part (1), and so we have \( 1+x \in \mathfrak{m} \). Since \( x\in J(R) \), \( x\in \mathfrak{m} \) as well.

-   But then \( (1+x) - x = 1 \in \mathfrak{m} \) which forces \( \mathfrak{m} = R \).
:::

::: {.proof title="of b, $\\impliedby$"}
\( \impliedby \)

-   Fix \( x\in R \), and suppose \( 1+rx \) is a unit for all \( r\in R \).

-   Suppose towards a contradiction that there is a maximal ideal \( \mathfrak{m} \) such that \( x\not \in \mathfrak{m} \) and thus \( x\not\in J(R) \).

-   Consider
    \[
    M' \coloneqq\left\{{rx + m {~\mathrel{\Big|}~}r\in R,~ m\in M}\right\}
    .\]

-   Since \( \mathfrak{m} \) was maximal, \( \mathfrak{m} \subsetneq M' \) and so \( M' = R \).

-   So every element in \( R \) can be written as \( rx + m \) for some \( r\in R, m\in M \). But \( 1\in R \), so we have
    \[
    1 = rx + m
    .\]

-   So let \( s = -r \) and write \( 1 = sx - m \), and so \( m = 1 + sx \).

-   Since \( s\in R \) by assumption \( 1+sx \) is a unit and thus \( m \in \mathfrak{m} \) is a unit, a contradiction.

-   So \( x\in \mathfrak{m} \) for every \( \mathfrak{m} \) and thus \( x\in J(R) \).
:::

::: {.proof title="of c"}
-   We want to show \( J(R) = \mathfrak N(R) \).

\( \mathfrak N(R) \subseteq J(R) \):

-   We'll use the fact \( x\in \mathfrak N(R) \implies x^n = 0 \implies 1 + rx \) is a unit \( \iff x\in J(R) \) by (b):
    \[
    \sum_{k=1}^{n-1} (-x)^k = \frac{1 - (-x)^n}{1- (-x)} = (1+x)^{-1}
    .\]

-   \( J(R) \subseteq \mathfrak N(R) \):

-   Let \( x \in J(R) \setminus \mathfrak N(R) \).

-   Since \( R \) is finite, \( x^m = x \) for some \( m > 0 \).

-   Without loss of generality, we can suppose \( x^2 = x \) by replacing \( x^m \) with \( x^{2m} \).

-   If \( 1-x \) is not a unit, then \( \left\langle{1-x}\right\rangle \) is a nontrivial proper ideal, which by (a) is contained in some maximal ideal \( {\mathfrak{m}} \). But then \( x\in {\mathfrak{m}} \) and \( 1-x \in {\mathfrak{m}}\implies x + (1-x) = 1 \in {\mathfrak{m}} \), a contradiction.

-   So \( 1-x \) is a unit, so let \( u = (1-x)^{-1} \).

-   Then
    \[
    (1-x)x &= x - x^2 = x - x = 0 \\
    &\implies u (1-x)x = x = 0 \\
    &\implies x=0
    .\]
:::
:::

## Fall 2018 \#7 \( \done \) {#fall-2018-7-done}

Let \( R \) be a commutative ring.

a.  Let \( r \in R \). Show that the map
    \[
    r\bullet : R &\to R \\
    x &\mapsto r x
    .\]
    is an \( R{\hbox{-}} \)module endomorphism of \( R \).

b.  We say that \( r \) is a **zero-divisor** if \( r\bullet \) is not injective. Show that if \( r \) is a zero-divisor and \( r \neq 0 \), then the kernel and image of \( R \) each consist of zero-divisors.

c.  Let \( n \geq 2 \) be an integer. Show: if \( R \) has exactly \( n \) zero-divisors, then \( \#R \leq n^2 \) .

d.  Show that up to isomorphism there are exactly two commutative rings \( R \) with precisely 2 zero-divisors.

> You may use without proof the following fact: every ring of order 4 is isomorphic to exactly one of the following:
> \[
> \frac{ {\mathbb{Z}}}{ 4{\mathbb{Z}}}, \quad
> \frac{ \frac{  {\mathbb{Z}}}{ 2{\mathbb{Z}}} [t]}{(t^2 + t + 1)}, \quad
> \frac{ \frac{ {\mathbb{Z}}}{ 2{\mathbb{Z}}} [t]}{ (t^2 - t)}, \quad
> \frac{ \frac{ {\mathbb{Z}}}{2{\mathbb{Z}}}[t]}{(t^2 )}
> .\]

::: {.concept}
```{=tex}
\envlist
```
-   Todo
-   See 1964 Annals "Properties of rings with a finite number of zero divisors"
:::

::: {.solution}
```{=tex}
\envlist
```
::: {.proof title="of a"}
```{=tex}
\envlist
```
-   Let \( \phi \) denote the map in question, it suffices to show that \( \phi \) is \( R{\hbox{-}} \)linear, i.e. \( \phi(s\mathbf{x} + \mathbf{y}) = s\phi(\mathbf{x}) + \phi(\mathbf{y}) \):
    \[
    \phi(s\mathbf{x} + \mathbf{y}) 
    &= r(s\mathbf{x} + \mathbf{y}) \\
    &= rs\mathbf{x} + r\mathbf{y} \\
    &= s(r\mathbf{x}) + (r\mathbf{y}) \\
    &= s\phi(\mathbf{x}) + \phi(\mathbf{y})
    .\]
:::

::: {.proof title="of b"}
```{=tex}
\envlist
```
-   We identify \( \ker \phi = \left\{{x\in R {~\mathrel{\Big|}~}rx = 0}\right\} \), and since \( r\neq 0 \) by assumption, this implies each such \( x \) is a zero divisor by definition (and \( \ker \phi \) is nonempty by assumption).

-   Similarly, we identify \( \operatorname{im}\phi = \left\{{y = rx {~\mathrel{\Big|}~}x\in R}\right\} \). So let \( y\in \operatorname{im}\phi \).

-   Since \( r \) is a zero divisor, there exists some \( z\in R \) such that \( rz = 0 \).

-   But then
    \[
    yz = rxz = xrz = x\cdot 0 = 0
    \]
    since \( R \) is commutative, so \( y \) is a zero divisor.
:::

::: {.proof title="of c"}
```{=tex}
\envlist
```
-   Let \( Z \coloneqq\left\{{z_i}\right\}_{i=1}^n \) be the set of \( n \) zero divisors in \( R \).

-   Let \( \phi_i \) be the \( n \) maps \( x \mapsto z_i x \), and let \( K_i = \ker \phi_i \) be the corresponding kernels.

-   Fix an \( i \).

-   By (b), \( K_i \) consists of zero divisors, so
    \[
    {\left\lvert {K_i} \right\rvert} \leq n < \infty \quad \text{for each } i
    .\]

-   Now consider \( R/K_i \coloneqq\left\{{r + K_i}\right\} \).

-   By the first isomorphism theorem, \( R/K_i \cong \operatorname{im}\phi \), and by (b) every element in the image is a zero divisor, so
    \[
    [R: K_i] = {\left\lvert {R/K_i} \right\rvert} = {\left\lvert {\operatorname{im}\phi_i} \right\rvert} \leq n 
    .\]

-   But then
    \[
    {\left\lvert {R} \right\rvert} = [R:K_i]\cdot {\left\lvert {K_i} \right\rvert} \leq n\cdot n = n^2 
    .\]
:::

::: {.proof title="of d"}
```{=tex}
\envlist
```
-   By (c), if there are exactly 2 zero divisors then \( {\left\lvert {R} \right\rvert} \leq 4 \). Since every element in a finite ring is either a unit or a zero divisor, and \( {\left\lvert {R^{\times}} \right\rvert} \geq 2 \) since \( \pm 1 \) are always units, we must have \( {\left\lvert {R} \right\rvert} = 4 \).

-   Since the characteristic of a ring must divide its size, we have \( \operatorname{ch}R = 2 \) or \( 4 \).

-   Using the hint, we see that only \( {\mathbb{Z}}/(4) \) has characteristic 4, which has exactly 2 zero divisors given by \( [0]_4 \) and \( [2]_4 \).

-   If \( R \) has characteristic 2, we can check the other 3 possibilities.

-   We can write \( {\mathbb{Z}}/(2)[t]/(t^2) = \left\{{a + bt {~\mathrel{\Big|}~}a,b\in {\mathbb{Z}}/(2)}\right\} \), and checking the multiplication table we have
    \[
    \begin{array}{c|cccc}
              & 0 & 1     & t & 1+t   \\ \hline
    0       & 0 & 0     & 0 & 0     \\ 
    1       & 0 & 1     & t & 1+t   \\ 
    t       & 0 & t     & \mathbf{0} & t    \\ 
    1 + t & 0 & 1+t & t & 1     \\ 
    \end{array}
    ,\]

    and so we find that \( t, 0 \) are the zero divisors.

-   In \( {\mathbb{Z}}/(2)[t]/(t^2 - t) \), we can check that \( t^2 = t \implies t t^2 = t^2 \implies t(t^2 + 1) = 0 \implies t(t+1) = 0 \), so both \( t \) and \( t+1 \) are zero divisors, along with zero, so this is not a possibility.

-   Similarly, in \( {\mathbb{Z}}/(2)[t]/(t^2 + t + 1) \), we can check the bottom-right corner of the multiplication table to find
    \[
    \left[\begin{array}{c|cc}
      & t     & 1 +t \\ \hline
    t & 1+t & 1 \\
    t & 1   & t \\
    \end{array}\right]
    ,\]

    and so this ring only has one zero divisor.

-   Thus the only possibilities are:
    \[
    R &\cong {\mathbb{Z}}/(4) \\
    R &\cong {\mathbb{Z}}/(2)[t] / (t^2)
    .\]
:::
:::

## Spring 2018 \#5 \( \work \) {#spring-2018-5-work}

Let
\[
M=\left(\begin{array}{ll}{a} & {b} \\ {c} & {d}\end{array}\right)
\quad \text{and} \quad 
N=\left(\begin{array}{cc}{x} & {u} \\ {-y} & {-v}\end{array}\right)
\]

over a commutative ring \( R \), where \( b \) and \( x \) are units of \( R \). Prove that
\[
M N=\left(\begin{array}{ll}{0} & {0} \\ {0} & {*}\end{array}\right)
\implies MN = 0
.\]

## Spring 2018 \#8 \( \work \) {#spring-2018-8-work}

Let \( R = C[0, 1] \) be the ring of continuous real-valued functions on the interval \( [0, 1] \). Let I be an ideal of \( R \).

a.  Show that if \( f \in I, a \in [0, 1] \) are such that \( f (a) \neq 0 \), then there exists \( g \in I \) such that \( g(x) \geq 0 \) for all \( x \in [0, 1] \), and \( g(x) > 0 \) for all \( x \) in some open neighborhood of \( a \).

b.  If \( I \neq R \), show that the set \( Z(I) = \{x \in [0, 1] {~\mathrel{\Big|}~}f(x) = 0 \text{ for all } f \in I\} \) is nonempty.

c.  Show that if \( I \) is maximal, then there exists \( x_0 \in [0, 1] \) such that \( I = \{ f \in R {~\mathrel{\Big|}~}f (x_0 ) = 0\} \).

## Fall 2017 \#5 \( \work \) {#fall-2017-5-work}

A ring \( R \) is called *simple* if its only two-sided ideals are \( 0 \) and \( R \).

a.  Suppose \( R \) is a commutative ring with 1. Prove \( R \) is simple if and only if \( R \) is a field.

b.  Let \( k \) be a field. Show the ring \( M_n (k) \), \( n \times n \) matrices with entries in \( k \), is a simple ring.

## Fall 2017 \#6 \( \work \) {#fall-2017-6-work}

For a ring \( R \), let \( U(R) \) denote the multiplicative group of units in \( R \). Recall that in an integral domain \( R \), \( r \in R \) is called *irreducible* if \( r \) is not a unit in R, and the only divisors of \( r \) have the form \( ru \) with \( u \) a unit in \( R \).

We call a non-zero, non-unit \( r \in R \) *prime* in \( R \) if \( r \bigm|ab \implies r \bigm|a \) or \( r \bigm|b \). Consider the ring \( R = \{a + b \sqrt{-5}{~\mathrel{\Big|}~}a, b \in Z\} \).

a.  Prove \( R \) is an integral domain.

b.  Show \( U(R) = \{\pm1\} \).

c.  Show \( 3, 2 + \sqrt{-5} \), and \( 2 - \sqrt{-5} \) are irreducible in \( R \).

d.  Show 3 is not prime in \( R \).

e.  Conclude \( R \) is not a PID.

## Spring 2017 \#3 \( \work \) {#spring-2017-3-work}

Let \( R \) be a commutative ring with 1. Suppose that \( M \) is a free \( R{\hbox{-}} \)module with a finite basis \( X \).

a.  Let \( I {~\trianglelefteq~}R \) be a proper ideal. Prove that \( M/IM \) is a free \( R/I{\hbox{-}} \)module with basis \( X' \), where \( X' \) is the image of \( X \) under the canonical map \( M\to M/IM \).

b.  Prove that any two bases of \( M \) have the same number of elements. You may assume that the result is true when \( R \) is a field.

## Spring 2017 \#4 \( \work \) {#spring-2017-4-work}

a.  Let \( R \) be an integral domain with quotient field \( F \). Suppose that \( p(x), a(x), b(x) \) are monic polynomials in \( F[x] \) with \( p(x) = a(x) b(x) \) and with \( p(x) \in R[x] \), \( a(x) \) not in \( R[x] \), and both \( a(x), b(x) \) not constant.

    Prove that \( R \) is not a UFD.

    > (You may assume Gauss' lemma)

b.  Prove that \( {\mathbb{Z}}[2\sqrt{2}] \) is not a UFD.

    > Hint: let \( p(x) = x^2-2 \).

## Spring 2016 \#8 \( \work \) {#spring-2016-8-work}

Let \( R \) be a simple rng (a nonzero ring which is not assume to have a 1, whose only two-sided ideals are \( (0) \) and \( R \)) satisfying the following two conditions:

i.  \( R \) has no zero divisors, and
ii. If \( x\in R \) with \( x\neq 0 \) then \( 2x\neq 0 \), where \( 2x\coloneqq x+x \).

Prove the following:

a.  For each \( x\in R \) there is one and only one element \( y\in R \) such that \( x = 2y \).

b.  Suppose \( x,y\in R \) such that \( x\neq 0 \) and \( 2(xy) = x \), then \( yz = zy \) for all \( z\in R \).

> You can get partial credit for (b) by showing it in the case \( R \) has a 1.

## Fall 2015 \#3 \( \work \) {#fall-2015-3-work}

Let \( R \) be a rng (a ring without 1) which contains an element \( u \) such that for all \( y\in R \), there exists an \( x\in R \) such that \( xu=y \).

Prove that \( R \) contains a maximal left ideal.

> Hint: imitate the proof (using Zorn's lemma) in the case where \( R \) does have a 1.

## Fall 2015 \#4 \( \work \) {#fall-2015-4-work}

Let \( R \) be a PID and \( (a_1) < (a_2) < \cdots \) be an ascending chain of ideals in \( R \). Prove that for some \( n \), we have \( (a_j) = (a_n) \) for all \( j\geq n \).

## Spring 2015 \#7 \( \work \) {#spring-2015-7-work}

Let \( R \) be a commutative ring, and \( S\subset R \) be a nonempty subset that does not contain 0 such that for all \( x, y\in S \) we have \( xy\in S \). Let \( {\mathcal{I}} \) be the set of all ideals \( I{~\trianglelefteq~}R \) such that \( I\cap S = \emptyset \).

Show that for every ideal \( I\in {\mathcal{I}} \), there is an ideal \( J\in {\mathcal{I}} \) such that \( I\subset J \) and \( J \) is not properly contained in any other ideal in \( {\mathcal{I}} \).

Prove that every such ideal \( J \) is prime.

## Fall 2014 \#7 \( \work \) {#fall-2014-7-work}

Give a careful proof that \( {\mathbb{C}}[x, y] \) is not a PID.

## Fall 2014 \#8 \( \work \) {#fall-2014-8-work}

Let \( R \) be a nonzero commutative ring without unit such that \( R \) does not contain a proper maximal ideal. Prove that for all \( x\in R \), the ideal \( xR \) is proper.

> You may assume the axiom of choice.

## Spring 2014 \#5 \( \work \) {#spring-2014-5-work}

Let \( R \) be a commutative ring and \( a\in R \). Prove that \( a \) is not nilpotent \( \iff \) there exists a commutative ring \( S \) and a ring homomorphism \( \phi: R\to S \) such that \( \phi(a) \) is a unit.

> Note: by definition, \( a \) is nilpotent \( \iff \) there is a natural number \( n \) such that \( a^n = 0 \).

## Spring 2014 \#6 \( \work \) {#spring-2014-6-work}

\( R \) be a commutative ring with identity and let \( n \) be a positive integer.

a.  Prove that every surjective \( R{\hbox{-}} \)linear endomorphism \( T: R^n \to R^n \) is injective.

b.  Show that an injective \( R{\hbox{-}} \)linear endomorphism of \( R^n \) need not be surjective.

## Fall 2013 \#3 \( \work \) {#fall-2013-3-work}

a.  Define *prime ideal*, give an example of a nontrivial ideal in the ring \( {\mathbb{Z}} \) that is not prime, and prove that it is not prime.

b.  Define *maximal ideal*, give an example of a nontrivial maximal ideal in \( {\mathbb{Z}} \) and prove that it is maximal.

## Fall 2013 \#4 \( \work \) {#fall-2013-4-work}

Let \( R \) be a commutative ring with \( 1\neq 0 \). Recall that \( x\in R \) is *nilpotent* iff \( x^n = 0 \) for some positive integer \( n \).

a.  Show that the collection of nilpotent elements in \( R \) forms an ideal.

b.  Show that if \( x \) is nilpotent, then \( x \) is contained in every prime ideal of \( R \).

c.  Suppose \( x\in R \) is not nilpotent and let \( S = \left\{{x^n {~\mathrel{\Big|}~}n\in {\mathbb{N}}}\right\} \). There is at least on ideal of \( R \) disjoint from \( S \), namely \( (0) \).

By Zorn's lemma the set of ideals disjoint from \( S \) has a maximal element with respect to inclusion, say \( I \). In other words, \( I \) is disjoint from \( S \) and if \( J \) is any ideal disjoint from \( S \) with \( I\subseteq J \subseteq R \) then \( J=I \) or \( J=R \).

Show that \( I \) is a prime ideal.

d.  Deduce from (a) and (b) that the set of nilpotent elements of \( R \) is the intersection of all prime ideals of \( R \).

## Spring 2013 \#1 \( \work \) {#spring-2013-1-work}

Let \( R \) be a commutative ring.

a.  Define a *maximal ideal* and prove that \( R \) has a maximal ideal.

b.  Show than an element \( r\in R \) is not invertible \( \iff r \) is contained in a maximal ideal.

c.  Let \( M \) be an \( R{\hbox{-}} \)module, and recall that for \( 0\neq \mu \in M \), the *annihilator* of \( \mu \) is the set
    \[
    \operatorname{Ann}(\mu) = \left\{{r\in R {~\mathrel{\Big|}~}r\mu = 0}\right\}
    .\]
    Suppose that \( I \) is an ideal in \( R \) which is maximal with respect to the property that there exists an element \( \mu \in M \) such that \( I = \operatorname{Ann}(\mu) \) for some \( \mu \in M \). In other words, \( I = \operatorname{Ann}(\mu) \) but there does not exist \( \nu\in M \) with \( J = \operatorname{Ann}(\nu) \subsetneq R \) such that \( I\subsetneq J \).

Prove that \( I \) is a prime ideal.

## Spring 2013 \#2 \( \work \) {#spring-2013-2-work}

a.  Define a *Euclidean domain*.

b.  Define a *unique factorization domain*.

c.  Is a Euclidean domain an UFD? Give either a proof or a counterexample with justification.

d.  Is a UFD a Euclidean domain? Give either a proof or a counterexample with justification.

## Spring 2021 \#5 \( \work \) {#spring-2021-5-work}

Suppose that \( f(x) \in ({\mathbb{Z}}/n{\mathbb{Z}})[x] \) is a zero divisor. Show that there is a nonzero \( a\in {\mathbb{Z}}/n{\mathbb{Z}} \) with \( af(x) = 0 \).

## Spring 2021 \#6

a.  Carefully state the definition of **Noetherian** for a commutative ring \( R \).

b.  Let \( R \) be a subset of \( {\mathbb{Z}}[x] \) consisting of all polynomials
    \[
    f(x) = a_ 0 + a_1 x + a_2 x^2 + \cdots + a_nx^n
    \]
    such that \( a_k \) is even for \( 1\leq k \leq n \). Show that \( R \) is a subring of \( {\mathbb{Z}}[x] \).

c.  Show that \( R \) is not Noetherian.

> *Hint: consider the ideal generated by \( \left\{{ 2x^k {~\mathrel{\Big|}~}1\leq k \in {\mathbb{Z}}}\right\} \).*

# Fields and Galois Theory

## \( \star \) Fall 2016 \#5 \( \work \) {#star-fall-2016-5-work}

How many monic irreducible polynomials over \( {\mathbb{F}}_p \) of prime degree \( \ell \) are there? Justify your answer.

## \( \star \) Fall 2013 \#7 \( \work \) {#star-fall-2013-7-work}

Let \( F = {\mathbb{F}}_2 \) and let \( \mkern 1.5mu\overline{\mkern-1.5muF\mkern-1.5mu}\mkern 1.5mu \) denote its algebraic closure.

a.  Show that \( \mkern 1.5mu\overline{\mkern-1.5muF\mkern-1.5mu}\mkern 1.5mu \) is not a finite extension of \( F \).

b.  Suppose that \( \alpha \in \mkern 1.5mu\overline{\mkern-1.5muF\mkern-1.5mu}\mkern 1.5mu \) satisfies \( \alpha^{17} = 1 \) and \( \alpha\neq 1 \). Show that \( F(\alpha)/F \) has degree 8.

## Fall 2019 \#4 \( \done \) {#fall-2019-4-done}

Let \( F \) be a finite field with \( q \) elements. Let \( n \) be a positive integer relatively prime to \( q \) and let \( \omega \) be a primitive \( n \)th root of unity in an extension field of \( F \). Let \( E = F [\omega] \) and let \( k = [E : F] \).

a.  Prove that \( n \) divides \( q^{k}-1 \).

b.  Let \( m \) be the order of \( q \) in \( {\mathbb{Z}}/n{\mathbb{Z}}^{\times} \). Prove that \( m \) divides \( k \).

c.  Prove that \( m = k \).

```{=tex}
\todo[inline]{Revisit, tricky!}
```
::: {.concept}
```{=tex}
\envlist
```
-   \( {\mathbb{F}}^{\times} \) is always cyclic for \( {\mathbb{F}} \) a field.
-   Lagrange: \( H\leq G \implies \#H \bigm|\# G \).
:::

::: {.solution}
```{=tex}
\envlist
```
::: {.proof title="of a"}
```{=tex}
\envlist
```
-   Since \( {\left\lvert {F} \right\rvert} = q \) and \( [E:F] = k \), we have \( {\left\lvert {E} \right\rvert} = q^k \) and \( {\left\lvert {E^{\times}} \right\rvert} = q^k-1 \).

-   Noting that \( \zeta \in E^{\times} \) we must have \( n = o(\zeta) \bigm|{\left\lvert {E^{\times}} \right\rvert} = q^k-1 \) by Lagrange's theorem.
:::

::: {.proof title="of b"}
```{=tex}
\envlist
```
-   Rephrasing (a), we have
    \[
    n \bigm|q^k-1 
    &\iff q^k-1 \cong 0 \pmod n \\
    &\iff q^k \cong 1 \pmod n \\
    &\iff m \coloneqq o(q) \bigm|k
    .\]
:::

::: {.proof title="of c"}
```{=tex}
\envlist
```
-   Since \( m\bigm|k \iff k = \ell m \), (**claim**) there is an intermediate subfield \( M \) such that
    \[
    E \leq M \leq F \quad k = [F:E] = [F:M] [M:E] = \ell m
    ,\]

    so \( M \) is a degree \( m \) extension of \( E \).

-   Now consider \( M^{\times} \).

-   By the argument in (a), \( n \) divides \( q^m - 1 = {\left\lvert {M^{\times}} \right\rvert} \), and \( M^{\times} \) is cyclic, so it contains a cyclic subgroup \( H \) of order \( n \).

-   But then \( x\in H \implies p(x)\coloneqq x^n-1 = 0 \), and since \( p(x) \) has at most \( n \) roots in a field.

-   So \( H = \left\{{x \in M {~\mathrel{\Big|}~}x^n-1 = 0}\right\} \), i.e. \( H \) contains all solutions to \( x^n-1 \) in \( E[x] \).

-   But \( \zeta \) is one such solution, so \( \zeta \in H \subset M^{\times}\subset M \).

-   Since \( F[\zeta] \) is the smallest field extension containing \( \zeta \), we must have \( F = M \), so \( \ell = 1 \), and \( k = m \).
:::
:::

## Fall 2019 \#7 \( \done \) {#fall-2019-7-done}

Let \( \zeta_n \) denote a primitive \( n \)th root of 1 \( \in {\mathbb{Q}} \). You may assume the roots of the minimal polynomial \( p_n(x) \) of \( \zeta_n \) are exactly the primitive \( n \)th roots of 1.

Show that the field extension \( {\mathbb{Q}}(\zeta_n ) \) over \( {\mathbb{Q}} \) is Galois and prove its Galois group is \( ({\mathbb{Z}}/n{\mathbb{Z}})^{\times} \).

How many subfields are there of \( {\mathbb{Q}}(\zeta_{20} ) \)?

::: {.concept}
```{=tex}
\envlist
```
-   **Galois** = normal + separable.

-   **Separable**: Minimal polynomial of every element has distinct roots.

-   **Normal (if separable)**: Splitting field of an irreducible polynomial.

-   \( \zeta \) is a primitive root of unity \( \iff o(\zeta) = n \) in \( {\mathbb{F}}^{\times} \).

-   \( \phi(p^k) = p^{k-1}(p-1) \)

-   The lattice:

    ![image_2021-04-17-02-44-48](figures/image_2021-04-17-02-44-48.png)
:::

::: {.solution}
```{=tex}
\envlist
```
Let \( K = {\mathbb{Q}}(\zeta) \). Then \( K \) is the splitting field of \( f(x) = x^n - 1 \), which is irreducible over \( {\mathbb{Q}} \), so \( K/{\mathbb{Q}} \) is normal. We also have \( f'(x) = nx^{n-1} \) and \( \gcd(f, f') = 1 \) since they can not share any roots.

> Or equivalently, \( f \) splits into distinct linear factors \( f(x) = \prod_{k\leq n}(x-\zeta^k) \).

Since it is a Galois extension, \( {\left\lvert {\operatorname{Gal}(K/{\mathbb{Q}})} \right\rvert} = [K: {\mathbb{Q}}] = \phi(n) \) for the totient function.

We can now define maps
\[
\tau_j: K &\to K \\
\zeta &\mapsto \zeta^j 
\]
and if we restrict to \( j \) such that \( \gcd(n, j) = 1 \), this yields \( \phi(n) \) maps. Noting that if \( \zeta \) is a primitive root, then \( (n, j) = 1 \) implies that that \( \zeta^j \) is also a primitive root, and hence another root of \( \min(\zeta, {\mathbb{Q}}) \), and so these are in fact automorphisms of \( K \) that fix \( {\mathbb{Q}} \) and thus elements of \( \operatorname{Gal}(K/{\mathbb{Q}}) \).

So define a map
\[
\theta: {\mathbb{Z}}_n^{\times}&\to K \\
[j]_n &\mapsto \tau_j
.\]

from the *multiplicative* group of units to the Galois group.

The claim is that this is a surjective homomorphism, and since both groups are the same size, an isomorphism.

::: {.proof title="of surjectivity"}
Letting \( \sigma \in K \) be arbitrary, noting that \( [K: {\mathbb{Q}}] \) has a basis \( \left\{{1, \zeta, \zeta^2, \cdots, \zeta^{n-1}}\right\} \), it suffices to specify \( \sigma(\zeta) \) to fully determine the automorphism. (Since \( \sigma(\zeta^k) = \sigma(\zeta)^k \).)

In particular, \( \sigma(\zeta) \) satisfies the polynomial \( x^n - 1 \), since \( \sigma(\zeta)^n = \sigma(\zeta^n) = \sigma(1) = 1 \), which means \( \sigma(\zeta) \) is another root of unity and \( \sigma(\zeta) = \zeta^k \) for some \( 1\leq k \leq n \).

Moreover, since \( o(\zeta) = n \in K^{\times} \), we must have \( o(\zeta^k) = n \in K^{\times} \) as well. Noting that \( \left\{{\zeta^i}\right\} \) forms a cyclic subgroup \( H\leq K^{\times} \), then \( o(\zeta^k) = n \iff (n, k) = 1 \) (by general theory of cyclic groups).

Thus \( \theta \) is surjective.
:::

::: {.proof title="of being a homomorphism"}
\[
\tau_j \circ \tau_k (\zeta) =\tau_j(\zeta^k) = \zeta^{jk} \implies
\tau_{jk} = \theta(jk) = \tau_j \circ \tau_k
.\]
:::

::: {.proof title="of part 2"}
We have \( K \cong {\mathbb{Z}}_{20}^{\times} \) and \( \phi(20) = 8 \), so \( K \cong {\mathbb{Z}}_8 \), so we have the following subgroups and corresponding intermediate fields:

-   \( 0 \sim {\mathbb{Q}}(\zeta_{20}) \)
-   \( {\mathbb{Z}}_2 \sim {\mathbb{Q}}(\omega_1) \)
-   \( {\mathbb{Z}}_4 \sim {\mathbb{Q}}(\omega_2) \)
-   \( {\mathbb{Z}}_8 \sim {\mathbb{Q}} \)

For some elements \( \omega_i \) which exist by the primitive element theorem.
:::
:::

## Spring 2019 \#2 \( \done \) {#spring-2019-2-done}

Let \( F = {\mathbb{F}}_p \) , where \( p \) is a prime number.

a.  Show that if \( \pi(x) \in F[x] \) is irreducible of degree \( d \), then \( \pi(x) \) divides \( x^{p^d} - x \).

b.  Show that if \( \pi(x) \in F[x] \) is an irreducible polynomial that divides \( x^{p^n} - x \), then \( \deg \pi(x) \) divides \( n \).

::: {.concept}
```{=tex}
\envlist
```
-   Go to a field extension.
    -   Orders of multiplicative groups for finite fields are known.
-   \( {\mathbb{GF}}(p^n) \) is the splitting field of \( x^{p^n} - x \in {\mathbb{F}}_p[x] \).
-   \( x^{p^d} - x \bigm|x^{p^n} - x \iff d \bigm|n \)
-   \( {\mathbb{GF}}(p^d) \leq {\mathbb{GF}}(p^n) \iff d\bigm|n \)
-   \( x^{p^n} - x = \prod f_i(x) \) over all irreducible monic \( f_i \) of degree \( d \) dividing \( n \).
:::

::: {.solution}
```{=tex}
\envlist
```
::: {.proof title="of a"}
We can consider the quotient \( K = \displaystyle{\frac{{\mathbb{F}}_p[x]}{\left\langle{\pi(x)}\right\rangle}} \), which since \( \pi(x) \) is irreducible is an extension of \( {\mathbb{F}}_p \) of degree \( d \) and thus a field of size \( p^d \) with a natural quotient map of rings \( \rho: {\mathbb{F}}_p[x] \to K \).

Since \( K^{\times} \) is a group of size \( p^d-1 \), we know that for any \( y \in K^{\times} \), we have by Lagrange's theorem that the order of \( y \) divides \( p^d-1 \) and so \( y^{p^d} = y \).

So every element in \( K \) is a root of \( q(x) = x^{p^d}-x \).

Since \( \rho \) is a ring morphism, we have

\[
\rho(q(x)) = \rho(x^{p^d} - x) &= \rho(x)^{p^d} - \rho(x)
= 0 \in K \\
&\iff q(x) \in \ker \rho \\
&\iff q(x) \in \left\langle{\pi(x)}\right\rangle \\
&\iff \pi(x) \bigm|q(x) = x^{p^d}-x
,\]
where we've used that "to contain is to divide" in the last step.
:::

::: {.proof title="of b"}
::: {.claim}
\( \pi(x) \) divides \( x^{p^n}-x \iff \deg \pi \) divides \( n \).
:::

::: {.proof title="of claim, $\\implies$"}
Let \( L \cong {\mathbb{GF}}(p^n) \) be the splitting field of \( \phi_n(x) \coloneqq x^{p^n}-x \); then since \( \pi \bigm|\phi_n \) by assumption, \( \pi \) splits in \( L \). Let \( \alpha \in L \) be any root of \( \pi \); then there is a tower of extensions \( {\mathbb{F}}_p \leq {\mathbb{F}}_p(\alpha) \leq L \).

Then \( {\mathbb{F}}_p \leq {\mathbb{F}}_p(\alpha) \leq L \), and so
\[
n &= [L: {\mathbb{F}}_p] \\
&= [L: {\mathbb{F}}_p(\alpha)]~[{\mathbb{F}}_p(\alpha): {\mathbb{F}}_p] \\
&= \ell d
,\]

for some \( \ell \in {\mathbb{Z}}^{\geq 1} \), so \( d \) divides \( n \).
:::

::: {.proof title="of claim, $\\impliedby$"}
\( \impliedby \): If \( d\bigm|n \), use the fact (claim) that \( x^{p^n} - x = \prod f_i(x) \) over all irreducible monic \( f_i \) of degree \( d \) dividing \( n \). So \( f = f_i \) for some \( i \).
:::
:::
:::

## Spring 2019 \#8 \( \done \) {#spring-2019-8-done}

Let \( \zeta = e^{2\pi i/8} \).

a.  What is the degree of \( {\mathbb{Q}}(\zeta)/{\mathbb{Q}} \)?

b.  How many quadratic subfields of \( {\mathbb{Q}}(\zeta) \) are there?

c.  What is the degree of \( {\mathbb{Q}}(\zeta, \sqrt[4] 2) \) over \( {\mathbb{Q}} \)?

::: {.concept}
```{=tex}
\envlist
```
-   \( \zeta_n \coloneqq e^{2\pi i \over n} \), and \( \zeta_n^k \) is a primitive \( n \)th root of unity \( \iff \gcd(n, k) = 1 \)
    -   In general, \( \zeta_n^k \) is a primitive \( {n \over \gcd(n, k)} \)th root of unity.
-   \( \deg \Phi_n(x) = \phi(n) \)
-   \( \phi(p^k) = p^k - p^{k-1} = p^{k-1}(p-1) \)
    -   Proof: for a nontrivial gcd, the possibilities are
        \[
        p, 2p, 3p, 4p, \cdots, p^{k-2}p, p^{k-1}p
        .\]
-   \( \operatorname{Gal}({\mathbb{Q}}(\zeta)/{\mathbb{Q}}) \cong {\mathbb{Z}}/(n)^{\times} \)
:::

::: {.solution}
```{=tex}
\envlist
```
Let \( K = {\mathbb{Q}}(\zeta) \).

::: {.proof title="of a"}
```{=tex}
\envlist
```
-   \( \zeta \coloneqq e^{2\pi i / 8} \) is a primitive \( 8 \)th root of unity
-   The minimal polynomial of an \( n \)th root of unity is the \( n \)th cyclotomic polynomial \( \Phi_n \)
-   The degree of the field extension is the degree of \( \Phi_8 \), which is
    \[
    \phi(8) = \phi(2^3) = 2^{3-1} \cdot (2-1) = 4
    .\]
-   So \( [{\mathbb{Q}}(\zeta): {\mathbb{Q}}] = 4 \).
:::

::: {.proof title="of b"}
```{=tex}
\envlist
```
-   \( \operatorname{Gal}({\mathbb{Q}}(\zeta)/{\mathbb{Q}}) \cong {\mathbb{Z}}/(8)^{\times}\cong {\mathbb{Z}}/(4) \) by general theory
-   \( {\mathbb{Z}}/(4) \) has exactly one subgroup of index 2.
-   Thus there is exactly **one** intermediate field of degree 2 (a quadratic extension).
:::

::: {.proof title="of c"}
```{=tex}
\envlist
```
-   Let \( L = {\mathbb{Q}}(\zeta, \sqrt[4] 2) \).

-   Note \( {\mathbb{Q}}(\zeta) = {\mathbb{Q}}(i, \sqrt 2) \)

    -   \( {\mathbb{Q}}(i, \sqrt{2})\subseteq {\mathbb{Q}}(\zeta) \)
        -   \( \zeta_8^2 = i \), and \( \zeta_8 = \sqrt{2}^{-1}+ i\sqrt{2}^{-1} \) so \( \zeta_8 + \zeta_8 ^{-1}= 2/\sqrt{2} = \sqrt{2} \).
    -   \( {\mathbb{Q}}(\zeta) \subseteq {\mathbb{Q}}(i, \sqrt{2}) \):
        -   \( \zeta = e^{2\pi i / 8} = \sin(\pi/4) + i\cos(\pi/4) = {\sqrt 2 \over 2}\qty{1+i} \).

-   Thus \( L = {\mathbb{Q}}(i, \sqrt{2})(\sqrt[4]{2}) = {\mathbb{Q}}(i, \sqrt 2, \sqrt[4] 2) = {\mathbb{Q}}(i, \sqrt[4]{2}) \).

    -   Uses the fact that \( {\mathbb{Q}}(\sqrt 2) \subseteq {\mathbb{Q}}(\sqrt[4] 2) \) since \( \sqrt[4]{2}^2 = \sqrt{2} \)

-   Conclude
    \[
    [L: {\mathbb{Q}}] = [L: {\mathbb{Q}}(\sqrt[4] 2)] ~[{\mathbb{Q}}(\sqrt[4] 2): {\mathbb{Q}}] = 2 \cdot 4 = 8
    \]
    using the fact that the minimal polynomial of \( i \) over any subfield of \( {\mathbb{R}} \) is always \( x^2 + 1 \), so \( \min_{{\mathbb{Q}}(\sqrt[4] 2)}(i) = x^2 + 1 \) which is degree 2.
:::
:::

## Fall 2018 \#3 \( \done \) {#fall-2018-3-done}

Let \( F \subset K \subset L \) be finite degree field extensions. For each of the following assertions, give a proof or a counterexample.

a.  If \( L/F \) is Galois, then so is \( K/F \).

b.  If \( L/F \) is Galois, then so is \( L/K \).

c.  If \( K/F \) and \( L/K \) are both Galois, then so is \( L/F \).

::: {.concept}
```{=tex}
\envlist
```
-   Every quadratic extension over \( {\mathbb{Q}} \) is Galois.
:::

::: {.solution}
Let \( L/K/F \).

::: {.proof title="of a"}
**False**: Take \( L/K/F = {\mathbb{Q}}(\zeta_2, \sqrt[3] 2) \to {\mathbb{Q}}(\sqrt[3] 2) \to {\mathbb{Q}} \).

Then \( L/F \) is Galois, since it is the splitting field of \( x^3 - 2 \) and \( {\mathbb{Q}} \) has characteristic zero.

But \( K/F \) is not Galois, since it is not the splitting field of any irreducible polynomial.
:::

::: {.proof title="of b"}
**True**: If \( L/F \) is Galois, then \( L/K \) is normal and separable:

-   \( L/K \) is normal, since if \( \sigma: L \hookrightarrow\overline K \) lifts the identity on \( K \) and fixes \( L \), i-t also lifts the identity on \( F \) and fixes \( L \) (and \( \overline K = \overline F \)).

-   \( L/K \) is separable, since \( F[x] \subseteq K[x] \), and so if \( \alpha \in L \) where \( f(x) \coloneqq\min(\alpha, F) \) has no repeated factors, then \( f'(x) \coloneqq\min(\alpha, K) \) divides \( f \) and thus can not have repeated factors.
:::

::: {.proof title="of c"}
**False**: Use the fact that every quadratic extension is Galois, and take \( L/K/F = {\mathbb{Q}}(\sqrt[4] 2) \to {\mathbb{Q}}(\sqrt 2) \to {\mathbb{Q}} \).

Then each successive extension is quadratic (thus Galois) but \( {\mathbb{Q}}(\sqrt[4] 2) \) is not the splitting field of any polynomial (noting that it does not split \( x^4 - 2 \) completely.)
:::
:::

## Spring 2018 \#2 \( \done \) {#spring-2018-2-done}

Let \( f(x) = x^4 - 4x^2 + 2 \in {\mathbb{Q}}[x] \).

a.  Find the splitting field \( K \) of \( f \), and compute \( [K: {\mathbb{Q}}] \).

b.  Find the Galois group \( G \) of \( f \), both as an explicit group of automorphisms, and as a familiar abstract group to which it is isomorphic.

c.  Exhibit explicitly the correspondence between subgroups of \( G \) and intermediate fields between \( {\mathbb{Q}} \) and \( k \).

```{=tex}
\todo[inline]{Not the nicest proof! Would be better to replace the ad-hoc computations at the end.}
```
::: {.concept}
```{=tex}
\envlist
```
-   Todo
:::

::: {.solution}
```{=tex}
\envlist
```
::: {.proof title="of a"}
Note that \( g(x) = x^2 - 4x + 2 \) has roots \( \beta = 2 \pm \sqrt{2} \), and so \( f \) has roots
\[
\alpha_1 &= \sqrt{2 + \sqrt 2} \\
\alpha_2 &= \sqrt{2 - \sqrt 2} \\
\alpha_3 &= -\alpha_1 \\
\alpha_4 &= -\alpha_2
.\]

and splitting field \( K = {\mathbb{Q}}(\left\{{\alpha_i}\right\}) \).
:::

::: {.proof title="of b"}
\( K \) is the splitting field of a separable polynomial and thus Galois over \( {\mathbb{Q}} \). Moreover, Since \( f \) is irreducible by Eisenstein with \( p=2 \), the Galois group is a transitive subgroup of \( S^4 \), so the possibilities are:

-   \( S_4 \)
-   \( A_4 \)
-   \( D_4 \)
-   \( {\mathbb{Z}}/(2) \times{\mathbb{Z}}/(2) \)
-   \( {\mathbb{Z}}/(4) \)

We can note that \( g \) splits over \( L \coloneqq{\mathbb{Q}}(\sqrt 2) \), an extension of degree 2.

We can now note that \( \min(\alpha, L) \) is given by \( p(x) = x^2 - (2 + \sqrt 2) \), and so \( [K: L] = 2 \).

We then have
\[
[K: {\mathbb{Q}}] = [K: L] [L : {\mathbb{Q}}] = (2)(2) = 4
.\]

This \( {\left\lvert {\operatorname{Gal}(K/{\mathbb{Q}})} \right\rvert} = 4 \), which leaves only two possibilities:

-   \( {\mathbb{Z}}/(2) \times{\mathbb{Z}}/(2) \)
-   \( {\mathbb{Z}}/(4) \)

We can next check orders of elements. Take
\[
\sigma &\in \operatorname{Gal}(K/{\mathbb{Q}}) \\
\alpha_1 &\mapsto \alpha_2
.\]

Computations show that

-   \( \alpha_1^2 \alpha_2^2 = 2 \), so \( \alpha_1 \alpha_2 = \sqrt 2 \)
-   \( \alpha_1^2 = 2 + \sqrt 2 \implies \sqrt 2 = \alpha_1^2 - 2 \)

and thus
\[
\sigma^2(\alpha_1) &= \sigma(\alpha_2) \\
&= \sigma\left(\frac{\sqrt 2}{\alpha_1}\right) \\
&= \frac{\sigma(\sqrt 2)}{\sigma(\alpha_1)} \\
&= \frac{\sigma(\alpha_1^2 - 2)}{\alpha_2} \\
&= \frac{\alpha_2^2 - 2}{\alpha_2} \\
&= \alpha_2 -2\alpha_2^{-1}\\
&= \alpha_2 - \frac{2\alpha_1}{\sqrt 2} \\
&= \alpha_2 -\alpha_1 \sqrt 2 \\
&\neq \alpha_1
,\]

and so the order of \( \sigma \) is strictly greater than 2, and thus 4, and thus \( \operatorname{Gal}(K/{\mathbb{Q}}) = \left\{{\sigma^k {~\mathrel{\Big|}~}1\leq k \leq 4}\right\} \cong {\mathbb{Z}}/(4) \).
:::

::: {.proof title="of c"}
?? The subgroup of index 2 \( \left\langle{\sigma^2}\right\rangle \) corresponds to the field extension \( Q(\sqrt 2) / {\mathbb{Q}} \).
:::

```{=tex}
\todo[inline]{Finish (c)}
```
:::

## Spring 2018 \#3 \( \done \) {#spring-2018-3-done}

Let \( K \) be a Galois extension of \( {\mathbb{Q}} \) with Galois group \( G \), and let \( E_1 , E_2 \) be intermediate fields of \( K \) which are the splitting fields of irreducible \( f_i (x) \in {\mathbb{Q}}[x] \).

Let \( E = E_1 E_2 \subset K \).

Let \( H_i = \operatorname{Gal}(K/E_i) \) and \( H = \operatorname{Gal}(K/E) \).

a.  Show that \( H = H_1 \cap H_2 \).

b.  Show that \( H_1 H_2 \) is a subgroup of \( G \).

c.  Show that
    \[
    \operatorname{Gal}(K/(E_1 \cap E_2 )) = H_1 H_2
    .\]

::: {.concept}
```{=tex}
\envlist
```
-   The Galois correspondence:
    -   \( H_1 \cap H_2 \rightleftharpoons E_1 E_2 \),
    -   \( H_1 H_2 \rightleftharpoons E_1 \cap E_2 \).
:::

::: {.solution}
```{=tex}
\envlist
```
::: {.proof title="of a"}
By the Galois correspondence, it suffices to show that the fixed field of \( H_1 \cap H_2 \) is \( E_1 E_2 \).

Let \( \sigma \in H_1 \cap H_2 \); then \( \sigma \in {\operatorname{Aut}}(K) \) fixes both \( E_1 \) and \( E_2 \).

> Not sure if this works -- compositum is not literally product..?

Writing \( x \in E_1E_2 \) as \( x=e_1 e_2 \), we have
\[
\sigma(x) = \sigma(e_1 e_2) = \sigma(e_1) \sigma(e_2) = e_1 e_2  =x,
\]

so \( \sigma \) fixes \( E_1 E_2 \).
:::

::: {.proof title="of b"}
That \( H_1 H_2 \subseteq G \) is clear, since if \( \sigma = \tau_1 \tau_2 \in H_1 H_2 \), then each \( \tau_i \) is an automorphism of \( K \) that fixes \( E_i \supseteq {\mathbb{Q}} \), so each \( \tau_i \) fixes \( {\mathbb{Q}} \) and thus \( \sigma \) fixes \( {\mathbb{Q}} \).

::: {.claim}
All elements in this subset commute.
:::

::: {.proof title="of claim"}
```{=tex}
\envlist
```
-   Let \( \sigma = \sigma_1 \sigma_2 \in H_1 H_2 \).

-   Note that \( \sigma_1(e) = e \) for all \( e\in E_1 \) by definition, since \( H_1 \) fixes \( E_1 \), and \( \sigma_2(e) \in E_1 \) (?).

-   Then
    \[
    \sigma_1(e) = e \quad \forall e \in E_1 \implies \sigma_1(\sigma_2(e)) = \sigma_2(e) 
    \]
    and substituting \( e = \sigma_1(e) \) on the RHS yields
    \[
    \sigma_1 \sigma_2(e) = \sigma_2 \sigma_1(e)
    ,\]
    where a similar proof holds for \( e\in E_2 \) and thus for arbitrary \( x\in E_1 E_2 \).
:::
:::

::: {.proof title="of c"}
By the Galois correspondence, the subgroup \( H_1H_2 \leq G \) will correspond to an intermediate field \( E \) such that \( K/E/{\mathbb{Q}} \) and \( E \) is the fixed field of \( H_1 H_2 \).

But if \( \sigma \in H_1 H_2 \), then \( \sigma = \tau_1 \tau_2 \) where \( \tau_i \) is an automorphism of \( K \) that fixes \( E_i \), and so
\[
\sigma(x) = x \iff \tau_1\tau_2(x) = x
&\iff \tau_2(x) = x 
\\
&~\&~ 
\\
\tau_1(x) = x &\iff x \in E_1 \cap E_2
.\]
.
:::
:::

## Spring 2020 \#4 \( \work \) {#spring-2020-4-work}

Let \( f(x) = x^4-2 \in {\mathbb{Q}}[x] \).

a.  Define what it means for a finite extension field \( E \) of a field \( F \) to be a Galois extension.

b.  Determine the Galois group \( \operatorname{Gal}(E/{\mathbb{Q}}) \) for the polynomial \( f(x) \), and justify your answer carefully.

c.  Exhibit a subfield \( K \) in \( (b) \) such that \( {\mathbb{Q}}\leq K \leq E \) with \( K \) not a Galois extension over \( {\mathbb{Q}} \). Explain.

## Spring 2020 \#3 \( \work \) {#spring-2020-3-work}

Let \( E \) be an extension field of \( F \) and \( \alpha\in E \) be algebraic of odd degree over \( F \).

a.  Show that \( F(\alpha) = F(\alpha^2) \).

b.  Prove that \( \alpha^{2020} \) is algebraic of odd degree over \( F \).

## Fall 2017 \#4 \( \work \) {#fall-2017-4-work}

a.  Let \( f (x) \) be an irreducible polynomial of degree 4 in \( {\mathbb{Q}}[x] \) whose splitting field \( K \) over \( {\mathbb{Q}} \) has Galois group \( G = S_4 \).

    Let \( \theta \) be a root of \( f(x) \). Prove that \( {\mathbb{Q}}[\theta] \) is an extension of \( {\mathbb{Q}} \) of degree 4 and that there are no intermediate fields between \( {\mathbb{Q}} \) and \( {\mathbb{Q}}[\theta] \).

b.  Prove that if \( K \) is a Galois extension of \( {\mathbb{Q}} \) of degree 4, then there is an intermediate subfield between \( K \) and \( {\mathbb{Q}} \).

## Fall 2017 \#3 \( \work \) {#fall-2017-3-work}

Let \( F \) be a field. Let \( f(x) \) be an irreducible polynomial in \( F[x] \) of degree \( n \) and let \( g(x) \) be any polynomial in \( F[x] \). Let \( p(x) \) be an irreducible factor (of degree \( m \)) of the polynomial \( f(g(x)) \).

Prove that \( n \) divides \( m \). Use this to prove that if \( r \) is an integer which is not a perfect square, and \( n \) is a positive integer then every irreducible factor of \( x^{2n} - r \) over \( {\mathbb{Q}}[x] \) has even degree.

## Spring 2017 \#7 \( \work \) {#spring-2017-7-work}

Let \( F \) be a field and let \( f(x) \in F[x] \).

a.  Define what a splitting field of \( f(x) \) over \( F \) is.

b.  Let \( F \) now be a finite field with \( q \) elements. Let \( E/F \) be a finite extension of degree \( n>0 \). Exhibit an explicit polynomial \( g(x) \in F[x] \) such that \( E/F \) is a splitting field of \( g(x) \) over \( F \). Fully justify your answer.

c.  Show that the extension \( E/F \) in (b) is a Galois extension.

## Spring 2017 \#8 \( \work \) {#spring-2017-8-work}

a.  Let \( K \) denote the splitting field of \( x^5 - 2 \) over \( {\mathbb{Q}} \). Show that the Galois group of \( K/{\mathbb{Q}} \) is isomorphic to the group of invertible matrices
    \[
    \left(\begin{array}{ll}
    a & b \\
    0 & 1
    \end{array}\right) 
    {\quad \operatorname{where} \quad} a\in {\mathbb{F}}_5^{\times}\text{ and } b\in {\mathbb{F}}_5
    .\]

b.  Determine all intermediate fields between \( K \) and \( {\mathbb{Q}} \) which are Galois over \( {\mathbb{Q}} \).

## Fall 2016 \#4 \( \work \) {#fall-2016-4-work}

Set \( f(x) = x^3 - 5 \in {\mathbb{Q}}[x] \).

a.  Find the splitting field \( K \) of \( f(x) \) over \( {\mathbb{Q}} \).

b.  Find the Galois group \( G \) of \( K \) over \( {\mathbb{Q}} \).

c.  Exhibit explicitly the correspondence between subgroups of \( G \) and intermediate fields between \( {\mathbb{Q}} \) and \( K \).

## Spring 2016 \#2 \( \work \) {#spring-2016-2-work}

Let \( K = {\mathbb{Q}}[\sqrt 2 + \sqrt 5] \).

a.  Find \( [K: {\mathbb{Q}}] \).

b.  Show that \( K/{\mathbb{Q}} \) is Galois, and find the Galois group \( G \) of \( K/{\mathbb{Q}} \).

c.  Exhibit explicitly the correspondence between subgroups of \( G \) and intermediate fields between \( {\mathbb{Q}} \) and \( K \).

## Spring 2016 \#6 \( \work \) {#spring-2016-6-work}

Let \( K \) be a Galois extension of a field \( F \) with \( [K: F] = 2015 \). Prove that \( K \) is an extension by radicals of the field \( F \).

## Fall 2015 \#5 \( \work \) {#fall-2015-5-work}

Let \( u = \sqrt{2 + \sqrt{2}} \), \( v = \sqrt{2 - \sqrt{2}} \), and \( E = {\mathbb{Q}}(u) \).

a.  Find (with justification) the minimal polynomial \( f(x) \) of \( u \) over \( {\mathbb{Q}} \).

b.  Show \( v\in E \), and show that \( E \) is a splitting field of \( f(x) \) over \( {\mathbb{Q}} \).

c.  Determine the Galois group of \( E \) over \( {\mathbb{Q}} \) and determine all of the intermediate fields \( F \) such that \( {\mathbb{Q}}\subset F \subset E \).

## Fall 2015 \#6 \( \work \) {#fall-2015-6-work}

a.  Let \( G \) be a finite group. Show that there exists a field extension \( K/F \) with \( \operatorname{Gal}(K/F) = G \).

    > You may assume that for any natural number \( n \) there is a field extension with Galois group \( S_n \).

b.  Let \( K \) be a Galois extension of \( F \) with \( {\left\lvert {\operatorname{Gal}(K/F)} \right\rvert} = 12 \). Prove that there exists an intermediate field \( E \) of \( K/F \) with \( [E: F] = 3 \).

c.  With \( K/F \) as in (b), does an intermediate field \( L \) necessarily exist satisfying \( [L: F] = 2 \)? Give a proof or counterexample.

## Spring 2015 \#2 \( \work \) {#spring-2015-2-work}

Let \( {\mathbb{F}} \) be a finite field.

a.  Give (with proof) the decomposition of the additive group \( ({\mathbb{F}}, +) \) into a direct sum of cyclic groups.

b.  The *exponent* of a finite group is the least common multiple of the orders of its elements. Prove that a finite abelian group has an element of order equal to its exponent.

c.  Prove that the multiplicative group \( ({\mathbb{F}}^{\times}, \cdot) \) is cyclic.

## Spring 2015 \#5 \( \work \) {#spring-2015-5-work}

Let \( f(x) = x^4 - 5 \in {\mathbb{Q}}[x] \).

a.  Compute the Galois group of \( f \) over \( {\mathbb{Q}} \).

b.  Compute the Galois group of \( f \) over \( {\mathbb{Q}}(\sqrt{5}) \).

## Fall 2014 \#1 \( \work \) {#fall-2014-1-work}

Let \( f\in {\mathbb{Q}}[x] \) be an irreducible polynomial and \( L \) a finite Galois extension of \( {\mathbb{Q}} \). Let \( f(x) = g_1(x)g_2(x)\cdots g_r(x) \) be a factorization of \( f \) into irreducibles in \( L[x] \).

a.  Prove that each of the factors \( g_i(x) \) has the same degree.

b.  Give an example showing that if \( L \) is not Galois over \( {\mathbb{Q}} \), the conclusion of part (a) need not hold.

## Fall 2014 \#3 \( \work \) {#fall-2014-3-work}

Consider the polynomial \( f(x) = x^4 - 7 \in {\mathbb{Q}}[x] \) and let \( E/{\mathbb{Q}} \) be the splitting field of \( f \).

a.  What is the structure of the Galois group of \( E/{\mathbb{Q}} \)?

b.  Give an explicit description of all of the intermediate subfields \( {\mathbb{Q}}\subset K \subset E \) in the form \( K = {\mathbb{Q}}(\alpha), {\mathbb{Q}}(\alpha, \beta), \cdots \) where \( \alpha, \beta \), etc are complex numbers. Describe the corresponding subgroups of the Galois group.

## Spring 2014 \#3 \( \work \) {#spring-2014-3-work}

Let \( F\subset C \) be a field extension with \( C \) algebraically closed.

a.  Prove that the intermediate field \( C_{\text{alg}} \subset C \) consisting of elements algebraic over \( F \) is algebraically closed.

b.  Prove that if \( F\to E \) is an algebraic extension, there exists a homomorphism \( E\to C \) that is the identity on \( F \).

## Spring 2014 \#4 \( \work \) {#spring-2014-4-work}

Let \( E\subset {\mathbb{C}} \) denote the splitting field over \( {\mathbb{Q}} \) of the polynomial \( x^3 - 11 \).

a.  Prove that if \( n \) is a squarefree positive integer, then \( \sqrt{n}\not\in E \).

    > Hint: you can describe all quadratic extensions of \( {\mathbb{Q}} \) contained in \( E \).

b.  Find the Galois group of \( (x^3 - 11)(x^2 - 2) \) over \( {\mathbb{Q}} \).

c.  Prove that the minimal polynomial of \( 11^{1/3} + 2^{1/2} \) over \( {\mathbb{Q}} \) has degree 6.

## Fall 2013 \#5 \( \work \) {#fall-2013-5-work}

Let \( L/K \) be a finite extension of fields.

a.  Define what it means for \( L/K \) to be *separable*.

b.  Show that if \( K \) is a finite field, then \( L/K \) is always separable.

c.  Give an example of a finite extension \( L/K \) that is not separable.

## Fall 2013 \#6 \( \work \) {#fall-2013-6-work}

Let \( K \) be the splitting field of \( x^4-2 \) over \( {\mathbb{Q}} \) and set \( G = \operatorname{Gal}(K/{\mathbb{Q}}) \).

a.  Show that \( K/{\mathbb{Q}} \) contains both \( {\mathbb{Q}}(i) \) and \( {\mathbb{Q}}(\sqrt[4]{2}) \) and has degree 8 over \( {\mathbb{Q}} \)/

b.  Let \( N = \operatorname{Gal}(K/{\mathbb{Q}}(i)) \) and \( H = \operatorname{Gal}(K/{\mathbb{Q}}(\sqrt[4]{2})) \). Show that \( N \) is normal in \( G \) and \( NH = G \).

    > Hint: what field is fixed by \( NH \)?

c.  Show that \( \operatorname{Gal}(K/{\mathbb{Q}}) \) is generated by elements \( \sigma, \tau \), of orders 4 and 2 respectively, with \( \tau \sigma\tau^{-1}= \sigma^{-1} \).

    > Equivalently, show it is the dihedral group of order 8.

d.  How many distinct quartic subfields of \( K \) are there? Justify your answer.

## Spring 2013 \#7 \( \work \) {#spring-2013-7-work}

Let \( f(x) = g(x) h(x) \in {\mathbb{Q}}[x] \) and \( E,B,C/{\mathbb{Q}} \) be the splitting fields of \( f,g,h \) respectively.

a.  Prove that \( \operatorname{Gal}(E/B) \) and \( \operatorname{Gal}(E/C) \) are normal subgroups of \( \operatorname{Gal}(E/{\mathbb{Q}}) \).

b.  Prove that \( \operatorname{Gal}(E/B) \cap\operatorname{Gal}(E/C) = \left\{{1}\right\} \).

c.  If \( B\cap C = {\mathbb{Q}} \), show that \( \operatorname{Gal}(E/B) \operatorname{Gal}(E/C) = \operatorname{Gal}(E/{\mathbb{Q}}) \).

d.  Under the hypothesis of (c), show that \( \operatorname{Gal}(E/{\mathbb{Q}}) \cong \operatorname{Gal}(E/B) \times \operatorname{Gal}(E/C) \).

e.  Use (d) to describe \( \operatorname{Gal}({\mathbb{Q}}[\alpha]/{\mathbb{Q}}) \) where \( \alpha = \sqrt 2 + \sqrt 3 \).

## Spring 2013 \#8 \( \work \) {#spring-2013-8-work}

Let \( F \) be the field with 2 elements and \( K \) a splitting field of \( f(x) = x^6 + x^3 + 1 \) over \( F \). You may assume that \( f \) is irreducible over \( F \).

a.  Show that if \( r \) is a root of \( f \) in \( K \), then \( r^9 = 1 \) but \( r^3\neq 1 \).

b.  Find \( \operatorname{Gal}(K/F) \) and express each intermediate field between \( F \) and \( K \) as \( F(\beta) \) for an appropriate \( \beta \in K \).

## Fall 2012 \#3 \( \work \) {#fall-2012-3-work}

Let \( f(x) \in {\mathbb{Q}}[x] \) be an irreducible polynomial of degree 5. Assume that \( f \) has all but two roots in \( {\mathbb{R}} \). Compute the Galois group of \( f(x) \) over \( {\mathbb{Q}} \) and justify your answer.

## Fall 2012 \#4 \( \work \) {#fall-2012-4-work}

Let \( f(x) \in {\mathbb{Q}}[x] \) be a polynomial and \( K \) be a splitting field of \( f \) over \( {\mathbb{Q}} \). Assume that \( [K:{\mathbb{Q}}] = 1225 \) and show that \( f(x) \) is solvable by radicals.

## Spring 2012 \#1 \( \work \) {#spring-2012-1-work}

Suppose that \( F\subset E \) are fields such that \( E/F \) is Galois and \( {\left\lvert {\operatorname{Gal}(E/F)} \right\rvert} = 14 \).

a.  Show that there exists a unique intermediate field \( K \) with \( F\subset K \subset E \) such that \( [K: F] = 2 \).

b.  Assume that there are at least two distinct intermediate subfields \( F \subset L_1, L_2 \subset E \) with \( [L_i: F]= 7 \). Prove that \( \operatorname{Gal}(E/F) \) is nonabelian.

## Spring 2012 \#4 \( \work \) {#spring-2012-4-work}

Let \( f(x) = x^7 - 3\in {\mathbb{Q}}[x] \) and \( E/{\mathbb{Q}} \) be a splitting field of \( f \) with \( \alpha \in E \) a root of \( f \).

a.  Show that \( E \) contains a primitive 7th root of unity.

b.  Show that \( E\neq {\mathbb{Q}}(\alpha) \).

## Fall 2019 Midterm \#6 \( \work \) {#fall-2019-midterm-6-work}

Compute the Galois group of \( f(x) = x^3-3x -3\in {\mathbb{Q}}[x]/{\mathbb{Q}} \).

## Fall 2019 Midterm \#7 \( \work \) {#fall-2019-midterm-7-work}

Show that a field \( k \) of characteristic \( p\neq 0 \) is perfect \( \iff \) for every \( x\in k \) there exists a \( y\in k \) such that \( y^p=x \).

## Fall 2019 Midterm \#8 \( \work \) {#fall-2019-midterm-8-work}

Let \( k \) be a field of characteristic \( p\neq 0 \) and \( f\in k[x] \) irreducible. Show that \( f(x) = g(x^{p^d}) \) where \( g(x) \in k[x] \) is irreducible and separable.

Conclude that every root of \( f \) has the same multiplicity \( p^d \) in the splitting field of \( f \) over \( k \).

## Fall 2019 Midterm \#9 \( \work \) {#fall-2019-midterm-9-work}

Let \( n\geq 3 \) and \( \zeta_n \) be a primitive \( n \)th root of unity. Show that \( [{\mathbb{Q}}(\zeta_n + \zeta_n^{-1}): {\mathbb{Q}}] = \phi(n)/2 \) for \( \phi \) the totient function. 10.

Let \( L/K \) be a finite normal extension.

a.  Show that if \( L/K \) is cyclic and \( E/K \) is normal with \( L/E/K \) then \( L/E \) and \( E/K \) are cyclic.

b.  Show that if \( L/K \) is cyclic then there exists exactly one extension \( E/K \) of degree \( n \) with \( L/E/K \) for each divisor \( n \) of \( [L:K] \).

## Spring 2021 \#4 \( \work \) {#spring-2021-4-work}

Define
\[
f(x) \coloneqq x^4 + 4x^2 + 64 \in {\mathbb{Q}}[x]
.\]

a.  Find the splitting field \( K \) of \( f \) over \( {\mathbb{Q}} \).

b.  Find the Galois group \( G \) of \( f \).

c.  Exhibit explicitly the correspondence between subgroups of \( G \) and intermediate fields between \( {\mathbb{Q}} \) and \( K \).

## Spring 2021 \#7 \( \done \) {#spring-2021-7-done}

Let \( p \) be a prime number and let \( F \) be a field of characteristic \( p \). Show that if \( a\in F \) is not a \( p \)th power in \( F \), then \( x^p-a \in F[x] \) is irreducible.

::: {.strategy}
```{=tex}
\envlist
```
-   By contrapositive, show that \( f(x) \coloneqq x^p-a \in {\mathbb{F}}[x] \) reducible \( \implies a \) is a \( p \)th power in \( {\mathbb{F}} \).
-   Eventually show \( a^\ell = b^p \) for some \( \ell\in {\mathbb{N}} \) and some \( b\in {\mathbb{F}} \), then \( \gcd(\ell, p) = 1 \) forces \( b=a \) and \( \ell=p \).
-   Use the fact that the constant term of any \( g\in {\mathbb{F}}[x] \) is actually in \( {\mathbb{F}} \).
:::

::: {.concept}
```{=tex}
\envlist
```
-   Reducible: \( f\in {\mathbb{F}}[x] \) is reducible iff there exists \( g, h\in {\mathbb{F}}[x] \) nonconstant with \( f = g h \).
    -   Importantly, this factorization needs to happen in \( {\mathbb{F}}[x] \), since we can *always* find such factorizations in the splitting field \( \operatorname{SF}(f)[x] \).
-   Bezout's identity: \( \gcd(p, q) = d \implies \) there exist \( s,t\in {\mathbb{Z}} \) such that
    \[
    sp + tq = d
    .\]
:::

::: {.solution}
```{=tex}
\envlist
```
-   WTS: \( f(x) \coloneqq x^p - a\in {\mathbb{F}}[x] \) reducible \( \implies f \) has a root in the *base field* \( {\mathbb{F}} \).

-   Write \( f(x) = g(x) h(x) \) and factor \( f(x) = \prod_{i=1}^p (x- r_i) \in \operatorname{SF}(f)[x] \) where the \( r_i \) are not necessarily distinct roots.

-   WLOG, \( g(x) = \prod_{i=1}^\ell (x-r_i) \) for some \( 1\leq \ell \leq p-1 \), i.e. rearrange the factors so that \( g \) is the first \( \ell \) of them.

    -   \( \ell \neq 1, p \) since \( f \) is reducible, making \( g, h \) nonconstant.

-   Set \( R_\ell \coloneqq\prod_{i=1}^\ell r_i \), which is the constant term in \( g \), so \( R_\ell \in {\mathbb{F}} \) since \( g\in {\mathbb{F}}[x] \).

-   Each \( r_i \) is a root of \( f \), so \( r_i^p - a = 0 \) for all \( i \), so \( r_i^p = a \).

-   Trick: what is the \( p \)th power of \( R_\ell \)?
    \[
    R_\ell^p 
    &\coloneqq\qty{ \prod_{i=1}^\ell}^p \\
    &= \prod_{i=1}^\ell r_i^p \\
    &= \prod_{i=1}^\ell a \\
    &= a^\ell
    ,\]
    so \( R_\ell^p = a^\ell \).

-   Use Bezout: \( \gcd(\ell, p) = 1 \) since \( p \) is prime, so write \( tp + s\ell = 1 \) for some \( t,s\in {\mathbb{Z}} \)

-   Use this to build a root of \( f \) that's in \( {\mathbb{F}} \): write
    \[
    a &= a^1\\
    &= a^{tp + s\ell} \\
    &= a^{tp} a^{s\ell} \\
    &=a^{tp} (a^\ell)^s\\
    &= a^{tp} (R_\ell^p)^s \\
    &= (a^t R_\ell^s)^p \\
    &\coloneqq\beta^p
    ,\]
    so \( a = \beta^p \).

    -   Check \( \beta\in {\mathbb{F}} \): use that \( R_\ell \in {\mathbb{F}} \) since it was a constant term of a polynomial in \( {\mathbb{F}}[x] \), \( a\in {\mathbb{F}} \) by assumption, and fields are closed under taking powers and products.
:::

## Fall 2020 \#3 \( \work \) {#fall-2020-3-work}

a.  Define what it means for a finite extension of fields \( E \) over \( F \) to be a *Galois* extension.

b.  Determine the Galois group of \( f(x) = x^3 - 7 \) over \( {\mathbb{Q}} \), and justify your answer carefully.

c.  Find all subfields of the splitting field of \( f(x) \) over \( {\mathbb{Q}} \).

## Fall 2020 \#4 \( \work \) {#fall-2020-4-work}

Let \( K \) be a Galois extension of \( F \), and let \( F \subset E \subset K \) be inclusions of fields. Let \( G \coloneqq\operatorname{Gal}(K/F) \) and \( H \coloneqq\operatorname{Gal}(K/E) \), and suppose \( H \) contains \( N_G(P) \), where \( P \) is a Sylow \( p \)-subgroup of \( G \) for \( p \) a prime. Prove that \( [E: F] \equiv 1 \pmod p \).

# Modules

## General Questions

### Fall 2018 \#6 \( \done \) {#fall-2018-6-done}

Let \( R \) be a commutative ring, and let \( M \) be an \( R{\hbox{-}} \)module. An \( R{\hbox{-}} \)submodule \( N \) of \( M \) is maximal if there is no \( R{\hbox{-}} \)module \( P \) with \( N \subsetneq P \subsetneq M \).

a.  Show that an \( R{\hbox{-}} \)submodule \( N \) of \( M \) is maximal \( \iff M /N \) is a simple \( R{\hbox{-}} \)module: i.e., \( M /N \) is nonzero and has no proper, nonzero \( R{\hbox{-}} \)submodules.

b.  Let \( M \) be a \( {\mathbb{Z}}{\hbox{-}} \)module. Show that a \( {\mathbb{Z}}{\hbox{-}} \)submodule \( N \) of \( M \) is maximal \( \iff \#M /N \) is a prime number.

c.  Let \( M \) be the \( {\mathbb{Z}}{\hbox{-}} \)module of all roots of unity in \( {\mathbb{C}} \) under multiplication. Show that there is no maximal \( {\mathbb{Z}}{\hbox{-}} \)submodule of \( M \).

::: {.concept}
```{=tex}
\envlist
```
-   Todo
:::

::: {.solution}
```{=tex}
\envlist
```
::: {.proof title="of a"}
By the correspondence theorem, submodules of \( M/N \) biject with submodules \( A \) of \( M \) containing \( N \).

So

-   \( M \) is maximal:

-   \( \iff \) no such (proper, nontrivial) submodule \( A \) exists

-   \( \iff \) there are no (proper, nontrivial) submodules of \( M/N \)

-   \( \iff M/N \) is simple.
:::

::: {.proof title="of b"}
Identify \( {\mathbb{Z}}{\hbox{-}} \)modules with abelian groups, then by (a), \( N \) is maximal \( \iff \) \( M/N \) is simple \( \iff \) \( M/N \) has no nontrivial proper subgroups.\

By Cauchy's theorem, if \( {\left\lvert {M/N} \right\rvert} = ab \) is a composite number, then \( a\bigm|ab \implies \) there is an element (and thus a subgroup) of order \( a \). In this case, \( M/N \) contains a nontrivial proper cyclic subgroup, so \( M/N \) is not simple. So \( {\left\lvert {M/N} \right\rvert} \) can not be composite, and therefore must be prime.
:::

::: {.proof title="of c"}
Let \( G = \left\{{x \in {\mathbb{C}}{~\mathrel{\Big|}~}x^n=1 \text{ for some }n\in {\mathbb{N}}}\right\} \), and suppose \( H < G \) is a proper subgroup.

Then there must be a prime \( p \) such that the \( \zeta_{p^k} \not \in H \) for all \( k \) greater than some constant \( m \) -- otherwise, we can use the fact that if \( \zeta_{p^k} \in H \) then \( \zeta_{p^\ell} \in H \) for all \( \ell \leq k \), and if \( \zeta_{p^k} \in H \) for all \( p \) and all \( k \) then \( H = G \).

But this means there are infinitely many elements in \( G\setminus H \), and so \( \infty = [G: H] = {\left\lvert {G/H} \right\rvert} \) is not a prime. Thus by (b), \( H \) can not be maximal, a contradiction.
:::
:::

### Fall 2019 Final \#2 \( \work \) {#fall-2019-final-2-work}

Consider the \( {\mathbb{Z}}{\hbox{-}} \)submodule \( N \) of \( {\mathbb{Z}}^3 \) spanned by
\[
f_1 &= [-1, 0, 1], \\
f_2 &= [2,-3,1], \\
f_3 &= [0, 3, 1], \\
f_4 &= [3,1,5]
.\]
Find a basis for \( N \) and describe \( {\mathbb{Z}}^3/N \).

### Spring 2018 \#6 \( \work \) {#spring-2018-6-work}

Let
\[
M &= \{(w, x, y, z) \in {\mathbb{Z}}^4 {~\mathrel{\Big|}~}w + x + y + z \in 2{\mathbb{Z}}\} \\
N &= \left\{{
(w, x, y, z) \in {\mathbb{Z}}^4 {~\mathrel{\Big|}~}4\bigm|(w - x),~ 4\bigm|(x - y),~ 4\bigm|( y - z)
}\right\}
.\]

a.  Show that \( N \) is a \( {\mathbb{Z}}{\hbox{-}} \)submodule of \( M \) .

b.  Find vectors \( u_1 , u_2 , u_3 , u_4 \in {\mathbb{Z}}^4 \) and integers \( d_1 , d_2 , d_3 , d_4 \) such that
    \[
    \{
    u_1 , u_2 , u_3 , u_4 
    \} 
    && \text{is a free basis for }M
    \\
    \{
    d_1 u_1,~ d_2 u_2,~ d_3 u_3,~ d_4 u_4 
    \}
    && \text{is a free basis for }N
    \]

c.  Use the previous part to describe \( M/N \) as a direct sum of cyclic \( {\mathbb{Z}}{\hbox{-}} \)modules.

### Spring 2018 \#7 \( \work \) {#spring-2018-7-work}

Let \( R \) be a PID and \( M \) be an \( R{\hbox{-}} \)module. Let \( p \) be a prime element of \( R \). The module \( M \) is called *\( \left\langle{p}\right\rangle{\hbox{-}} \)primary* if for every \( m \in M \) there exists \( k > 0 \) such that \( p^k m = 0 \).

a.  Suppose M is \( \left\langle{p}\right\rangle{\hbox{-}} \)primary. Show that if \( m \in M \) and \( t \in R, ~t \not\in \left\langle{p}\right\rangle \), then there exists \( a \in R \) such that \( atm = m \).

b.  A submodule \( S \) of \( M \) is said to be *pure* if \( S \cap r M = rS \) for all \( r \in R \). Show that if \( M \) is \( \left\langle{p}\right\rangle{\hbox{-}} \)primary, then \( S \) is pure if and only if \( S \cap p^k M = p^k S \) for all \( k \geq 0 \).

### Fall 2016 \#6 \( \work \) {#fall-2016-6-work}

Let \( R \) be a ring and \( f: M\to N \) and \( g: N\to M \) be \( R{\hbox{-}} \)module homomorphisms such that \( g\circ f = \operatorname{id}_M \). Show that \( N\cong \operatorname{im}f \oplus \ker g \).

### Spring 2016 \#4 \( \work \) {#spring-2016-4-work}

Let \( R \) be a ring with the following commutative diagram of \( R{\hbox{-}} \)modules, where each row represents a short exact sequence of \( R{\hbox{-}} \)modules:

```{=tex}
\begin{tikzcd}
0 \ar[r] & A \ar[d, "\alpha"] \ar[r, "f"] & B \ar[d, "\beta"] \ar[r, "g"] & C \ar[r] \ar[d, "\gamma"] & 0 \\
0 \ar[r] & A' \ar[r, "f'"] & B'\ar[r, "g'"] & C' \ar[r] & 0 
\end{tikzcd}
```
Prove that if \( \alpha \) and \( \gamma \) are isomorphisms then \( \beta \) is an isomorphism.

### Spring 2015 \#8 \( \work \) {#spring-2015-8-work}

Let \( R \) be a PID and \( M \) a finitely generated \( R{\hbox{-}} \)module.

a.  Prove that there are \( R{\hbox{-}} \)submodules
    \[
    0 = M_0 \subset M_1 \subset \cdots \subset M_n = M
    \]
    such that for all \( 0\leq i \leq n-1 \), the module \( M_{i+1}/M_i \) is cyclic.

b.  Is the integer \( n \) in part (a) uniquely determined by \( M \)? Prove your answer.

### Fall 2012 \#6 \( \work \) {#fall-2012-6-work}

Let \( R \) be a ring and \( M \) an \( R{\hbox{-}} \)module. Recall that \( M \) is *Noetherian* iff any strictly increasing chain of submodule \( M_1 \subsetneq M_2 \subsetneq \cdots \) is finite. Call a proper submodule \( M' \subsetneq M \) *intersection-decomposable* if it can not be written as the intersection of two proper submodules \( M' = M_1\cap M_2 \) with \( M_i \subsetneq M \).

Prove that for every Noetherian module \( M \), any proper submodule \( N\subsetneq M \) can be written as a finite intersection \( N = N_1 \cap\cdots \cap N_k \) of intersection-indecomposable modules.

### Fall 2019 Final \#1 \( \work \) {#fall-2019-final-1-work}

Let \( A \) be an abelian group, and show \( A \) is a \( {\mathbb{Z}}{\hbox{-}} \)module in a unique way.

### Fall 2020 \#6 \( \work \) {#fall-2020-6-work}

Let \( R \) be a ring with \( 1 \) and let \( M \) be a left \( R{\hbox{-}} \)module. If \( I \) is a left ideal of \( R \), define
\[
IM \coloneqq\left\{{ \sum_{i=1}^{N < \infty} a_i m_i {~\mathrel{\Big|}~}a_i \in I, m_i \in M, n\in {\mathbb{N}}}\right\}
,\]
i.e. the set of finite sums of of elements of the form \( am \) where \( a\in I, m\in M \).

a.  Prove that \( IM \leq M \) is a submodule.

b.  Let \( M, N \) be left \( R{\hbox{-}} \)modules, \( I \) a nilpotent left ideal of \( R \), and \( f: M\to N \) an \( R{\hbox{-}} \)module morphism. Prove that if the induced morphism \( \mkern 1.5mu\overline{\mkern-1.5muf\mkern-1.5mu}\mkern 1.5mu: M/IM \to N/IN \) is surjective, then \( f \) is surjective.

## Torsion and the Structure Theorem

### \( \star \) Fall 2019 \#5 \( \done \) {#star-fall-2019-5-done}

Let \( R \) be a ring and \( M \) an \( R{\hbox{-}} \)module.

> Recall that the set of torsion elements in M is defined by
> \[
> \operatorname{Tor}(M) = \{m \in M {~\mathrel{\Big|}~}\exists r \in R, ~r \neq 0, ~rm = 0\}
> .\]

a.  Prove that if \( R \) is an integral domain, then \( \operatorname{Tor}(M ) \) is a submodule of \( M \) .

b.  Give an example where \( \operatorname{Tor}(M ) \) is not a submodule of \( M \).

c.  If \( R \) has zero-divisors, prove that every non-zero \( R{\hbox{-}} \)module has non-zero torsion elements.

::: {.concept}
```{=tex}
\envlist
```
-   One-step submodule test.
:::

::: {.solution}
```{=tex}
\envlist
```
::: {.proof title="of a"}
It suffices to show that
\[
r\in R, ~t_1, t_2\in \operatorname{Tor}(M) \implies rt_1 + t_2 \in \operatorname{Tor}(M)
.\]

We have
\[
t_1 \in \operatorname{Tor}(M) &\implies \exists s_1 \neq 0 \text{ such that } s_1 t_1  = 0 \\
t_2 \in \operatorname{Tor}(M) &\implies \exists s_2 \neq 0 \text{ such that } s_2 t_2  = 0 
.\]

Since \( R \) is an integral domain, \( s_1 s_2 \neq 0 \). Then
\[
s_1 s_2(rt_1 + t_2) 
&= s_1 s_2 r t_1 + s_1 s_2t_2 \\
&= s_2 r (s_1 t_1) + s_1 (s_2 t_2)  \quad\text{since $R$ is commutative} \\
&=  s_2 r(0) + s_1(0) \\
&= 0
.\]
:::

::: {.proof title="of b"}
Let \( R = {\mathbb{Z}}/6{\mathbb{Z}} \) as a \( {\mathbb{Z}}/6{\mathbb{Z}}{\hbox{-}} \)module, which is not an integral domain as a ring.

Then \( [3]_6\curvearrowright[2]_6 = [0]_6 \) and \( [2]_6\curvearrowright[3]_6 = [0]_6 \), but \( [2]_6 + [3]_6 = [5]_6 \), where 5 is coprime to 6, and thus \( [n]_6\curvearrowright[5]_6 = [0] \implies [n]_6 = [0]_6 \). So \( [5]_6 \) is *not* a torsion element.

So the set of torsion elements are not closed under addition, and thus not a submodule.
:::

::: {.proof title="of c"}
Suppose \( R \) has zero divisors \( a,b \neq 0 \) where \( ab = 0 \). Then for any \( m\in M \), we have \( b\curvearrowright m \coloneqq bm \in M \) as well, but then
\[
a\curvearrowright bm = (ab)\curvearrowright m = 0\curvearrowright m = 0_M
,\]
so \( m \) is a torsion element for any \( m \).
:::
:::

### \( \star \) Spring 2019 \#5 \( \done \) {#star-spring-2019-5-done}

Let \( R \) be an integral domain. Recall that if \( M \) is an \( R{\hbox{-}} \)module, the *rank* of \( M \) is defined to be the maximum number of \( R{\hbox{-}} \)linearly independent elements of \( M \) .

a.  Prove that for any \( R{\hbox{-}} \)module \( M \), the rank of \( \operatorname{Tor}(M ) \) is 0.

b.  Prove that the rank of \( M \) is equal to the rank of of \( M/\operatorname{Tor}(M ) \).

c.  Suppose that M is a non-principal ideal of \( R \).

Prove that \( M \) is torsion-free of rank 1 but not free.

::: {.concept}
```{=tex}
\envlist
```
-   Todo
:::

:::{.solution} `\envlist`{=tex}

::: {.proof title="of a"}
```{=tex}
\envlist
```
-   Suppose toward a contradiction \( \operatorname{Tor}(M) \) has rank \( n \geq 1 \).
-   Then \( \operatorname{Tor}(M) \) has a linearly independent generating set \( B = \left\{{\mathbf{r}_1, \cdots, \mathbf{r}_n}\right\} \), so in particular
    \[  
    \sum_{i=1}^n s_i \mathbf{r}_i = 0 \implies s_i = 0_R \,\forall i
    .\]
-   Let \( \mathbf{r} \) be any of of these generating elements.
-   Since \( \mathbf{r}\in \operatorname{Tor}(M) \), there exists an \( s\in R\setminus 0_R \) such that \( s\mathbf{r} = 0_M \).
-   Then \( s\mathbf{r} = 0 \) with \( s\neq 0 \), so \( \left\{{\mathbf{r}}\right\} \subseteq B \) is *not* a linearly independent set, a contradiction.
:::

::: {.proof title="of b"}
```{=tex}
\envlist
```
-   Let \( n = \operatorname{rank}M \), and let \( \mathcal B = \left\{{\mathbf{r}_i}\right\}_{i=1}^n \subseteq R \) be a generating set.
-   Let \( \tilde M \coloneqq M/\operatorname{Tor}(M) \) and \( \pi: M \to M' \) be the canonical quotient map.

::: {.claim}
\[
\tilde {\mathcal{B}}\coloneqq\pi(\mathcal B) = \left\{{\mathbf{r}_i + \operatorname{Tor}(M)}\right\}
\]
is a basis for \( \tilde M \).
:::

Note that the proof follows immediately.
:::

::: {.proof title="of claim: linearly independent"}
```{=tex}
\envlist
```
-   Suppose that
    \[
    \sum_{i=1}^n s_i (\mathbf{r}_i + \operatorname{Tor}(M)) = \mathbf{0}_{\tilde M}
    .\]

-   Then using the definition of coset addition/multiplication, we can write this as
    \[  
    \sum_{i=1}^n \qty { s_i \mathbf{r}_i + \operatorname{Tor}(M)} = 
    \qty{ \sum_{i=1}^n  s_i \mathbf{r}_i} + \operatorname{Tor}(M)  = 0_{\tilde M}
    .\]

-   Since \( \tilde{\mathbf{x}} = 0 \in \tilde M \iff \tilde{\mathbf{x}} = \mathbf{x} + \operatorname{Tor}(M) \) where \( \mathbf{x} \in \operatorname{Tor}(M) \), this forces \( \sum s_i \mathbf{r}_i \in \operatorname{Tor}(M) \).

-   Then there exists a scalar \( \alpha\in R^{\bullet} \) such that \( \alpha \sum s_i \mathbf{r}_i = 0_M \).

-   Since \( R \) is an integral domain and \( \alpha \neq 0 \), we must have \( \sum s_i \mathbf{r}_i = 0_M \).

-   Since \( \left\{{\mathbf{r}_i}\right\} \) was linearly independent in \( M \), we must have \( s_i = 0_R \) for all \( i \).
:::

::: {.proof title="of claim: spanning"}
```{=tex}
\envlist
```
-   Write \( \pi(\mathcal B) = \left\{{\mathbf{r}_i + \operatorname{Tor}(M)}\right\}_{i=1}^n \) as a set of cosets.

-   Letting \( \mathbf{x} \in M' \) be arbitrary, we can write \( \mathbf{x} = \mathbf{m} + \operatorname{Tor}(M) \) for some \( \mathbf{m} \in M \) where \( \pi(\mathbf{m}) = \mathbf{x} \) by surjectivity of \( \pi \).

-   Since \( \mathcal B \) is a basis for \( M \), we have \( \mathbf{m} = \sum_{i=1}^n s_i \mathbf{r}_i \), and so
    \[
    \mathbf{x}
    &= \pi(\mathbf{m}) \\
    &\coloneqq\pi\qty{ \sum_{i=1}^n s_i \mathbf{r}_i} \\
    &= \sum_{i=1}^n s_i \pi(\mathbf{r}_i) \quad\text{since $\pi$ is an $R{\hbox{-}}$module morphism}\\
    &\coloneqq\sum_{i=1}^n s_i \mathbf{(}\mathbf{r}_i + \operatorname{Tor}(M))
    ,\]
    which expresses \( \mathbf{x} \) as a linear combination of elements in \( \mathcal B' \).
:::

::: {.proof title="of c"}
> Notation: Let \( 0_R \) denote \( 0\in R \) regarded as a ring element, and \( \mathbf{0} \in R \) denoted \( 0_R \) regarded as a module element (where \( R \) is regarded as an \( R{\hbox{-}} \)module over itself)

::: {.proof title="that $M$ is not free"}
```{=tex}
\envlist
```
-   **Claim**: If \( I\subseteq R \) is an ideal *and* a free \( R{\hbox{-}} \)module, then \( I \) is principal .

    -   Suppose \( I \) is free and let \( I = \left\langle{B}\right\rangle \) for some basis, we will show \( {\left\lvert {B} \right\rvert} = 1 \)\>

    -   Toward a contradiction, suppose \( {\left\lvert {B} \right\rvert} \geq 2 \) and let \( m_1, m_2\in B \).

    -   Then since \( R \) is commutative, \( m_2 m_1 - m_1 m_2 = 0 \) and this yields a linear dependence

    -   So \( B \) has only one element \( m \).

    -   But then \( I = \left\langle{m}\right\rangle = R_m \) is cyclic as an \( R{\hbox{-}} \) module and thus principal as an ideal of \( R \).

    -   Now since \( M \) was assumed to *not* be principal, \( M \) is not free (using the contrapositive of the claim).
:::

::: {.proof title="that $M$ is rank 1"}
```{=tex}
\envlist
```
-   For any module, we can take an element \( \mathbf{m}\in M^{\bullet} \) and consider the cyclic submodule \( R\mathbf{m} \).

-   Since \( M \) is not principle, it is not the zero ideal, and contains at least two elements. So we can consider an element \( \mathbf{m}\in M \).

-   We have \( \operatorname{rank}_R(M) \geq 1 \), since \( R\mathbf{m} \leq M \) and \( \left\{{m}\right\} \) is a subset of some spanning set.

-   \( R\mathbf{m} \) can not be linearly dependent, since \( R \) is an integral domain and \( M\subseteq R \), so \( \alpha \mathbf{m} = \mathbf{0} \implies \alpha = 0_R \).

-   Claim: since \( R \) is commutative, \( \operatorname{rank}_R(M) \leq 1 \).

    -   If we take two elements \( \mathbf{m}, \mathbf{n} \in M^{\bullet} \), then since \( m, n\in R \) as well, we have \( nm = mn \) and so
        \[
        (n)\mathbf{m} + (-m)\mathbf{n} = 0_R = \mathbf{0}
        \]
        is a linear dependence.

**\( M \) is torsion-free**:

-   Let \( \mathbf{x} \in \operatorname{Tor}M \), then there exists some \( r\neq 0\in R \) such that \( r\mathbf{x} = \mathbf{0} \).

-   But \( \mathbf{x}\in R \) as well and \( R \) is an integral domain, so \( \mathbf{x}=0_R \), and thus \( \operatorname{Tor}(M) = \left\{{0_R}\right\} \).
:::
:::

### \( \star \) Spring 2020 \#6 \( \done \) {#star-spring-2020-6-done}

Let \( R \) be a ring with unity.

a.  Give a definition for a free module over \( R \).

b.  Define what it means for an \( R{\hbox{-}} \)module to be torsion free.

c.  Prove that if \( F \) is a free module, then any short exact sequence of \( R{\hbox{-}} \)modules of the following form splits:
    \[
    0 \to N \to M \to F \to 0
    .\]

d.  Let \( R \) be a PID. Show that any finitely generated \( R{\hbox{-}} \)module \( M \) can be expressed as a direct sum of a torsion module and a free module.

> You may assume that a finitely generated torsionfree module over a PID is free.

::: {.solution}
Let \( R \) be a ring with 1.

::: {.proof title="of a"}
An \( R{\hbox{-}} \)module \( M \) is **free** if any of the following conditions hold:

-   \( M \) admits an \( R{\hbox{-}} \)linearly independent spanning set \( \left\{{\mathbf{b}_\alpha}\right\} \), so
    \[m\in M \implies m = \sum_\alpha r_\alpha \mathbf{b}_\alpha\]
    and
    \[\sum_\alpha r_\alpha \mathbf{b}_\alpha = 0_M \implies r_\alpha = 0_R\]
    for all \( \alpha \).
-   \( M \) admits a decomposition \( M \cong \bigoplus_{\alpha} R \) as a direct sum of \( R{\hbox{-}} \)submodules.
-   There is a nonempty set \( X \) an monomorphism \( X\hookrightarrow M \) of sets such that for every \( R{\hbox{-}} \)module \( N \), every set map \( X\to N \) lifts to a unique \( R{\hbox{-}} \)module morphism \( M\to N \), so the following diagram commutes:

```{=tex}
\begin{tikzcd}
M \ar[rd, dotted, "\exists ! \tilde f"] & \\
X \ar[u, hook] \ar[r, "f"] & N
\end{tikzcd}
```
Equivalently,
\[
\mathop{\mathrm{Hom}}_{\mathsf{Set}}(X, \mathop{\mathrm{Forget}}(N)) \xrightarrow{\sim} \mathop{\mathrm{Hom}}_{{\mathsf{R}{\hbox{-}}\mathsf{Mod}}}(M, N)
.\]
:::

::: {.proof title="of b"}
```{=tex}
\envlist
```
-   Define the annihilator:
    \[
    \operatorname{Ann}(m) \coloneqq\left\{{r\in R {~\mathrel{\Big|}~}r\cdot m = 0_M}\right\} {~\trianglelefteq~}R
    .\]
    -   Note that \( mR \cong R/\operatorname{Ann}(m) \).
-   Define the torsion submodule:
    \[
    M_t \coloneqq\left\{{m\in M {~\mathrel{\Big|}~}\operatorname{Ann}(m) \neq 0}\right\} \leq M
    \]
-   \( M \) is **torsionfree** iff \( M_t = 0 \) is the trivial submodule.
:::

::: {.proof title="of c"}
```{=tex}
\envlist
```
-   Let the following be an SES where \( F \) is a free \( R{\hbox{-}} \)module:
    \[
    0 \to N \to M \xrightarrow{\pi} F \to 0
    .\]

-   Since \( F \) is free, there is a generating set \( X = \left\{{x_\alpha}\right\} \) and a map \( \iota:X\hookrightarrow F \) satisfying the 3rd property from (a).

    -   If we construct any map \( f: X\to M \), the universal property modules will give a lift \( \tilde f: F\to M \)

-   Identify \( X \) with \( \iota(X) \subseteq F \).

-   For every \( x\in X \), the preimage \( \pi^{-1}(x) \) is nonempty by surjectivity. So arbitrarily pick any preimage.

-   \( \left\{{\iota(x_\alpha)}\right\} \subseteq F \) and \( \pi \) is surjective, so choose fibers \( \left\{{y_\alpha}\right\} \subseteq M \) such that \( \pi(y_\alpha) = \iota(x_\alpha) \) and define
    \[
    f: X&\to M \\
    x_\alpha &\mapsto y_\alpha
    .\]

-   The universal property yields \( h: F\to M \):

```{=tex}
\begin{tikzcd}
& & & X=\left\{{x_\alpha}\right\} \ar[dd, hook, "\iota"]\ar[ddl, "f"'] &  \\ \\
0 \ar[r]& N \ar[r] & M\ar[r, "\pi"'] & \ar[l, bend right, dotted ,"\exists ! h"'] F \ar[r] & 0
\end{tikzcd}
```
-   It remains to check that it's a section.
    -   Write \( f= \sum r_i x_i \), then since both maps are \( R{\hbox{-}} \)module morphism, by \( R{\hbox{-}} \)linearity we can write
        \[
        (\pi \circ h)(f) 
        &= (\pi \circ h)\qty{ \sum r_i x_i } \\
        &= \sum r_i (\pi \circ h)(x_i)
        ,\]
        but since \( h(x_i) \in \pi^{-1}(x_i) \), we have \( (\pi \circ h)(x_i) = x_i \). So this recovers \( f \).
:::

::: {.proof title="of c, shorter proof"}
```{=tex}
\envlist
```
-   Free implies projective

    -   Universal property of **projective** objects: for every epimorphism \( \pi:M\twoheadrightarrow N \) and every \( f:P\to N \) there exists a unique lift \( \tilde f: P\to M \):

    ```{=tex}
    \begin{tikzcd}
    & P\ar[d, "f"] \ar[dl, dotted, "\exists ! \tilde f"'] \\
    M \ar[r, "\pi"] & N
    \end{tikzcd}
    ```
    -   Construct \( \phi \) in the following diagram using the same method as above (surjectivity to pick elements in preimage):

```{=tex}
\begin{tikzcd}
    && X \\
    \\
    && F \\
    \\
    M && N && 0
    \arrow["\iota", hook, from=1-3, to=3-3]
    \arrow["f", from=3-3, to=5-3]
    \arrow["\pi"', two heads, from=5-1, to=5-3]
    \arrow[from=5-3, to=5-5]
    \arrow["{\exists \tilde \phi}"', dashed, from=3-3, to=5-1]
    \arrow["\phi"', curve={height=24pt}, from=1-3, to=5-1]
\end{tikzcd}
```
> [Link to Diagram](https://q.uiver.app/?q=WzAsNSxbMCw0LCJNIl0sWzIsNCwiTiJdLFs0LDQsIjAiXSxbMiwyLCJGIl0sWzIsMCwiWCJdLFs0LDMsIlxcaW90YSIsMCx7InN0eWxlIjp7InRhaWwiOnsibmFtZSI6Imhvb2siLCJzaWRlIjoidG9wIn19fV0sWzMsMSwiZiJdLFswLDEsIlxccGkiLDIseyJzdHlsZSI6eyJoZWFkIjp7Im5hbWUiOiJlcGkifX19XSxbMSwyXSxbMywwLCJcXGV4aXN0cyBcXHRpbGRlIFxccGhpIiwyLHsic3R5bGUiOnsiYm9keSI6eyJuYW1lIjoiZGFzaGVkIn19fV0sWzQsMCwiXFxwaGkiLDIseyJjdXJ2ZSI6NH1dXQ==)

-   Now take the identity map, then commutativity is equivalent to being a section.

```{=tex}
\begin{tikzcd}
 & & & F\ar[d, "\one_F"]\ar[dl, "\exists ! h"'] & \\
0 \ar[r] & N\ar[r] & M\ar[r] & F \ar[r] & 0
\end{tikzcd}
```
:::

::: {.proof title="of d"}
```{=tex}
\envlist
```
There is a SES

```{=tex}
\begin{tikzcd}
0 \ar[r] & M_t \ar[r] & M \ar[r] & M/M_t \ar[r] & 0
\end{tikzcd}
```
::: {.claim}
\( M/M_t \) is a free \( R{\hbox{-}} \)module, so this sequence splits and \( M\cong M_t \oplus {M\over M_t} \), where \( M_t \) is a torsion \( R{\hbox{-}} \)module.

> Note that by the hint, since \( R \) is a PID, it suffices to show that \( M/M_t \) is torsionfree.
:::

-   Let \( m+M_t \in M/M_t \) be arbitrary. Suppose this is a torsion element, the claim is that it must be the trivial coset. This will follow if \( m\in M_t \)
-   Since this is torsion, there exists \( r\in R \) such that
    \[
    M_t = r(m + M_t) \coloneqq(rm) + M_t \implies rm\in M_t
    .\]
-   Then \( rm \) is torsion in \( M \), so there exists some \( s\in R \) such \( s(rm) = 0_M \).
-   Then \( (sr)m = 0_M \) which forces \( m\in M_t \)
:::
:::

### Spring 2012 \#5 \( \work \) {#spring-2012-5-work}

Let \( M \) be a finitely generated module over a PID \( R \).

a.  \( M_t \) be the set of torsion elements of \( M \), and show that \( M_t \) is a submodule of \( M \).

b.  Show that \( M/M_t \) is torsion free.

c.  Prove that \( M \cong M_t \oplus F \) where \( F \) is a free module.

### Spring 2017 \#5 \( \work \) {#spring-2017-5-work}

Let \( R \) be an integral domain and let \( M \) be a nonzero torsion \( R{\hbox{-}} \)module.

a.  Prove that if \( M \) is finitely generated then the annihilator in \( R \) of \( M \) is nonzero.

b.  Give an example of a non-finitely generated torsion \( R{\hbox{-}} \)module whose annihilator is \( (0) \), and justify your answer.

### Fall 2019 Final \#3 \( \work \) {#fall-2019-final-3-work}

Let \( R = k[x] \) for \( k \) a field and let \( M \) be the \( R{\hbox{-}} \)module given by
\[
M=\frac{k[x]}{(x-1)^{3}} \oplus \frac{k[x]}{\left(x^{2}+1\right)^{2}} \oplus \frac{k[x]}{(x-1)\left(x^{2}+1\right)^{4}} \oplus \frac{k[x]}{(x+2)\left(x^{2}+1\right)^{2}}
.\]
Describe the elementary divisors and invariant factors of \( M \).

### Fall 2019 Final \#4 \( \work \) {#fall-2019-final-4-work}

Let \( I = (2, x) \) be an ideal in \( R = {\mathbb{Z}}[x] \), and show that \( I \) is not a direct sum of nontrivial cyclic \( R{\hbox{-}} \)modules.

### Fall 2019 Final \#5 \( \work \) {#fall-2019-final-5-work}

Let \( R \) be a PID.

a.  Classify irreducible \( R{\hbox{-}} \)modules up to isomorphism.

b.  Classify indecomposable \( R{\hbox{-}} \)modules up to isomorphism.

### Fall 2019 Final \#6 \( \work \) {#fall-2019-final-6-work}

Let \( V \) be a finite-dimensional \( k{\hbox{-}} \)vector space and \( T:V\to V \) a non-invertible \( k{\hbox{-}} \)linear map. Show that there exists a \( k{\hbox{-}} \)linear map \( S:V\to V \) with \( T\circ S = 0 \) but \( S\circ T\neq 0 \).

### Fall 2019 Final \#7 \( \work \) {#fall-2019-final-7-work}

Let \( A\in M_n({\mathbb{C}}) \) with \( A^2 = A \). Show that \( A \) is similar to a diagonal matrix, and exhibit an explicit diagonal matrix similar to \( A \).

### Fall 2019 Final \#10 \( \work \) {#fall-2019-final-10-work}

Show that the eigenvalues of a Hermitian matrix \( A \) are real and that \( A = PDP^{-1} \) where \( P \) is an invertible matrix with orthogonal columns.

### Fall 2020 \#7 \( \work \) {#fall-2020-7-work}

Let \( A \in \operatorname{Mat}(n\times n, {\mathbb{R}}) \) be arbitrary. Make \( {\mathbb{R}}^n \) into an \( {\mathbb{R}}[x]{\hbox{-}} \)module by letting \( f(x).\mathbf{v} \coloneqq f(A)(\mathbf{v}) \) for \( f(\mathbf{v})\in {\mathbb{R}}[x] \) and \( \mathbf{v} \in {\mathbb{R}}^n \). Suppose that this induces the following direct sum decomposition:
\[
{\mathbb{R}}^n \cong
{ {\mathbb{R}}[x] \over \left\langle{ (x-1)^3 }\right\rangle }
\oplus
{ {\mathbb{R}}[x] \over \left\langle{ (x^2+1)^2 }\right\rangle }
\oplus
{ {\mathbb{R}}[x] \over \left\langle{ (x-1)(x^2-1)(x^2+1)^4 }\right\rangle }
\oplus
{ {\mathbb{R}}[x] \over \left\langle{ (x+2)(x^2+1)^2 }\right\rangle }
.\]

a.  Determine the elementary divisors and invariant factors of \( A \).

b.  Determine the minimal polynomial of \( A \).

c.  Determine the characteristic polynomial of \( A \).

# Linear Algebra: Diagonalizability

## Fall 2017 \#7 \( \work \) {#fall-2017-7-work}

Let \( F \) be a field and let \( V \) and \( W \) be vector spaces over \( F \) .

Make \( V \) and \( W \) into \( F[x]{\hbox{-}} \)modules via linear operators \( T \) on \( V \) and \( S \) on \( W \) by defining \( X \cdot v = T (v) \) for all \( v \in V \) and \( X \cdot w = S(w) \) for all w \( \in \) W .

Denote the resulting \( F[x]{\hbox{-}} \)modules by \( V_T \) and \( W_S \) respectively.

a.  Show that an \( F[x]{\hbox{-}} \)module homomorphism from \( V_T \) to \( W_S \) consists of an \( F{\hbox{-}} \)linear transformation \( R : V \to W \) such that \( RT = SR \).

b.  Show that \( VT \cong WS \) as \( F[x]{\hbox{-}} \)modules \( \iff \) there is an \( F{\hbox{-}} \)linear isomorphism \( P : V \to W \) such that \( T = P^{-1}SP \).

c.  Recall that a module \( M \) is *simple* if \( M \neq 0 \) and any proper submodule of \( M \) must be zero. Suppose that \( V \) has dimension 2. Give an example of \( F \), \( T \) with \( V_T \) simple.

d.  Assume \( F \) is algebraically closed. Prove that if \( V \) has dimension 2, then any \( V_T \) is not simple.

## Spring 2015 \#3 \( \work \) {#spring-2015-3-work}

Let \( F \) be a field and \( V \) a finite dimensional \( F{\hbox{-}} \)vector space, and let \( A, B: V\to V \) be commuting \( F{\hbox{-}} \)linear maps. Suppose there is a basis \( {\mathcal{B}}_1 \) with respect to which \( A \) is diagonalizable and a basis \( {\mathcal{B}}_2 \) with respect to which \( B \) is diagonalizable.

Prove that there is a basis \( {\mathcal{B}}_3 \) with respect to which \( A \) and \( B \) are both diagonalizable.

## Fall 2016 \#2 \( \work \) {#fall-2016-2-work}

Let \( A, B \) be two \( n\times n \) matrices with the property that \( AB = BA \). Suppose that \( A \) and \( B \) are diagonalizable. Prove that \( A \) and \( B \) are *simultaneously* diagonalizable.

## Spring 2019 \#1 \( \done \) {#spring-2019-1-done}

Let \( A \) be a square matrix over the complex numbers. Suppose that \( A \) is nonsingular and that \( A^{2019} \) is diagonalizable over \( {\mathbb{C}} \).

Show that \( A \) is also diagonalizable over \( {\mathbb{C}} \).

::: {.concept}
```{=tex}
\envlist
```
-   \( A \) is diagonalizable iff \( \min_A(x) \) is separable.
    -   See [further discussion here](https://math.stackexchange.com/questions/3027664/if-a-is-invertible-and-an-is-diagonalizable-then-a-is-diagonalizable).
:::

::: {.solution}
```{=tex}
\envlist
```
::: {.claim}
If \( A \in \operatorname{GL}(m, {\mathbb{F}}) \) is invertible and \( A^n/{\mathbb{F}} \) is diagonalizable, then \( A/{\mathbb{F}} \) is diagonalizable.
:::

::: {.proof title="of claim"}
-   Let \( A \in \operatorname{GL}(m, {\mathbb{F}}) \).

-   Since \( A^n \) is diagonalizable, \( \min_{A^n}(x) \in {\mathbb{F}}[x] \) is separable and thus factors as a product of \( m \) **distinct** linear factors:
    \[
    \min_{A^n}(x) = \prod_{i=1}^m (x-\lambda_i), \quad \min_{A^n}(A^n) = 0
    \]

    where \( \left\{{\lambda_i}\right\}_{i=1}^m \subset {\mathbb{F}} \) are the **distinct** eigenvalues of \( A^n \).

-   Moreover \( A\in \operatorname{GL}(m,{\mathbb{F}}) \implies A^n \in \operatorname{GL}(m,{\mathbb{F}}) \): \( A \) is invertible \( \iff \det(A) = d \in {\mathbb{F}}^{\times} \), and so \( \det(A^n) = \det(A)^n = d^n \in {\mathbb{F}}^{\times} \) using the fact that the determinant is a ring morphism \( \det: \operatorname{Mat}(m\times m) \to{\mathbb{F}} \) and \( {\mathbb{F}}^{\times} \) is closed under multiplication.

-   So \( A^n \) is invertible, and thus has trivial kernel, and thus zero is not an eigenvalue, so \( \lambda_i \neq 0 \) for any \( i \).

-   Since the \( \lambda_i \) are distinct and nonzero, this implies \( x^k \) is not a factor of \( \mu_{A^n}(x) \) for any \( k\geq 0 \). Thus the \( m \) terms in the product correspond to precisely \( m \) **distinct linear** factors.

-   We can now construct a polynomial that annihilates \( A \), namely
    \[
    q_A(x) \coloneqq\min_{A^n}(x^n) = \prod_{i=1}^m (x^n-\lambda_i) \in {\mathbb{F}}[x],
    \]

    where we can note that \( q_A(A) = \min_{A^n}(A^n) = 0 \), and so \( \min_A(x) \bigm|q_A(x) \) by minimality.

::: {.claim}
\( q_A(x) \) has exactly \( nm \) distinct linear factors in \( { \mkern 1.5mu\overline{\mkern-1.5mu \mathbb{F}\mkern-1.5mu}\mkern 1.5mu }[x] \)
:::

-   This reduces to showing that no pair \( x^n-\lambda_i, x^n-\lambda_j \) share a root. and that \( x^n-\lambda_i \) does not have multiple roots.

-   For the first claim, we can factor
    \[
    x^n - \lambda_i = \prod_{k=1}^n (x - \lambda_i^{1\over n} e^{2\pi i k \over n}) \coloneqq\prod_{k=1}^n (x-\lambda^{1\over n} \zeta_n^k)
    ,\]
    where we now use the fact that \( i\neq j \implies \lambda_i^{1\over n} \neq \lambda_j^{1\over n} \). Thus no term in the above product appears as a factor in \( x^n - \lambda_j \) for \( j\neq i \).

-   For the second claim, we can check that \( {\frac{\partial }{\partial x}\,}\qty{x^n - \lambda_i} = nx^{n-1}\neq 0\in {\mathbb{F}} \), and \( \gcd(x^n-\lambda_i, nx^{n-1}) = 1 \) since the latter term has only the roots \( x=0 \) with multiplicity \( n-1 \), whereas \( \lambda_i\neq 0 \implies \) zero is not a root of \( x^n-\lambda_i \).

But now since \( q_A(x) \) has exactly distinct linear factors in \( \mkern 1.5mu\overline{\mkern-1.5mu{\mathbb{F}}\mkern-1.5mu}\mkern 1.5mu[x] \) and \( \min_A(x) \bigm|q_A(x) \), \( \min_A(x) \in {\mathbb{F}}[x] \) can only have distinct linear factors, and \( A \) is thus diagonalizable over \( {\mathbb{F}} \).
:::
:::

# Linear Algebra: Misc

## \( \star \) Spring 2012 \#6 \( \work \) {#star-spring-2012-6-work}

Let \( k \) be a field and let the group \( G = \operatorname{GL}(m, k) \times\operatorname{GL}(n, k) \) acts on the set of \( m\times n \) matrices \( M_{m, n}(k) \) as follows:
\[
(A, B) \cdot X = AXB^{-1}
\]
where \( (A, B) \in G \) and \( X\in M_{m, n}(k) \).

a.  State what it means for a group to act on a set. Prove that the above definition yields a group action.

b.  Exhibit with justification a subset \( S \) of \( M_{m, n}(k) \) which contains precisely one element of each orbit under this action.

## \( \star \) Spring 2014 \#7 \( \work \) {#star-spring-2014-7-work}

Let \( G = \operatorname{GL}(3, {\mathbb{Q}}[x]) \) be the group of invertible \( 3\times 3 \) matrices over \( {\mathbb{Q}}[x] \). For each \( f\in {\mathbb{Q}}[x] \), let \( S_f \) be the set of \( 3\times 3 \) matrices \( A \) over \( {\mathbb{Q}}[x] \) such that \( \det(A) = c f(x) \) for some nonzero constant \( c\in {\mathbb{Q}} \).

a.  Show that for \( (P, Q) \in G\times G \) and \( A\in S_f \), the formula
    \[
    (P, Q)\cdot A \coloneqq PAQ^{-1}
    \]
    gives a well defined map \( G\times G \times S_f \to S_f \) and show that this map gives a group action of \( G\times G \) on \( S_f \).

b.  For \( f(x) = x^3(x^2+1)^2 \), give one representative from each orbit of the group action in (a), and justify your assertion.

## Fall 2012 \#7 \( \work \) {#fall-2012-7-work}

Let \( k \) be a field of characteristic zero and \( A, B \in M_n(k) \) be two square \( n\times n \) matrices over \( k \) such that \( AB - BA = A \). Prove that \( \det A = 0 \).

Moreover, when the characteristic of \( k \) is 2, find a counterexample to this statement.

## Fall 2012 \#8 \( \work \) {#fall-2012-8-work}

Prove that any nondegenerate matrix \( X\in M_n({\mathbb{R}}) \) can be written as \( X = UT \) where \( U \) is orthogonal and \( T \) is upper triangular.

## Fall 2012 \#5 \( \work \) {#fall-2012-5-work}

Let \( U \) be an infinite-dimensional vector space over a field \( k \), \( f: U\to U \) a linear map, and \( \left\{{u_1, \cdots, u_m}\right\} \subset U \) vectors such that \( U \) is generated by \( \left\{{u_1, \cdots, u_m, f^d(u_1), \cdots, f^d(u_m)}\right\} \) for some \( d\in {\mathbb{N}} \).

Prove that \( U \) can be written as a direct sum \( U \cong V\oplus W \) such that

1.  \( V \) has a basis consisting of some vector \( v_1, \cdots v_n, f^d(v_1), \cdots, f^d(v_n) \) for some \( d\in {\mathbb{N}} \), and
2.  \( W \) is finite-dimensional.

Moreover, prove that for any other decomposition \( U \cong V' \oplus W' \), one has \( W' \cong W \).

## Fall 2015 \#7 \( \work \) {#fall-2015-7-work}

a.  Show that two \( 3\times 3 \) matrices over \( {\mathbb{C}} \) are similar \( \iff \) their characteristic polynomials are equal and their minimal polynomials are equal.

b.  Does the conclusion in (a) hold for \( 4\times 4 \) matrices? Justify your answer with a proof or counterexample.

## Fall 2014 \#4 \( \work \) {#fall-2014-4-work}

Let \( F \) be a field and \( T \) an \( n\times n \) matrix with entries in \( F \). Let \( I \) be the ideal consisting of all polynomials \( f\in F[x] \) such that \( f(T) =0 \).

Show that the following statements are equivalent about a polynomial \( g\in I \):

a.  \( g \) is irreducible.

b.  If \( k\in F[x] \) is nonzero and of degree strictly less than \( g \), then \( k[T] \) is an invertible matrix.

## Fall 2015 \#8 \( \work \) {#fall-2015-8-work}

Let \( V \) be a vector space over a field \( F \) and \( V {}^{ \check{} } \) its dual. A *symmetric bilinear form* \( ({-}, {-}) \) on \( V \) is a map \( V\times V\to F \) satisfying
\[
(av_1 + b v_2, w) = a(v_1, w) + b(v_2, w) {\quad \operatorname{and} \quad} (v_1, v_2) = (v_2, v_1)
\]
for all \( a, b\in F \) and \( v_1, v_2 \in V \). The form is *nondegenerate* if the only element \( w\in V \) satisfying \( (v, w) = 0 \) for all \( v\in V \) is \( w=0 \).

Suppose \( ({-}, {-}) \) is a nondegenerate symmetric bilinear form on \( V \). If \( W \) is a subspace of \( V \), define
\[
W^{\perp} \coloneqq\left\{{v\in V {~\mathrel{\Big|}~}(v, w) = 0 \text{ for all } w\in W}\right\}
.\]

a.  Show that if \( X, Y \) are subspaces of \( V \) with \( Y\subset X \), then \( X^{\perp} \subseteq Y^{\perp} \).

b.  Define an injective linear map
    \[
    \psi: Y^{\perp}/X^{\perp} \hookrightarrow(X/Y) {}^{ \check{} }
    \]
    which is an isomorphism if \( V \) is finite dimensional.

## Fall 2018 \#4 \( \done \) {#fall-2018-4-done}

Let \( V \) be a finite dimensional vector space over a field (the field is not necessarily algebraically closed).

Let \( \phi : V \to V \) be a linear transformation. Prove that there exists a decomposition of \( V \) as \( V = U \oplus W \) , where \( U \) and \( W \) are \( \phi{\hbox{-}} \)invariant subspaces of \( V \) , \(  {\left.{{\phi}} \right|_{{U}} }  \) is nilpotent, and \(  {\left.{{\phi}} \right|_{{W}} }  \) is nonsingular.

```{=tex}
\todo[inline]{Revisit.}
```
::: {.solution}
Let \( m(x) \) be the minimal polynomial of \( \phi \). If the polynomial \( f(x) = x \) doesn't divide \( m \), then \( f \) does not have zero as an eigenvalue, so \( \phi \) is nonsingular and since \( 0 \) is nilpotent, \( \phi + 0 \) works.

Otherwise, write \( \phi(x) = x^m \rho(x) \) where \( \gcd(x, \rho(x)) = 1 \).

Then
\[
V \cong \frac{k[x]}{m(x)} \cong \frac{k[x]}{(x^m)} \oplus \frac{k[x]}{(\rho)}
\coloneqq U \oplus W
\]
by the Chinese Remainder theorem.

We can now note that \(  {\left.{{\phi}} \right|_{{U}} }  \) is nilpotent because it has characteristic polynomial \( x^m \), and \(  {\left.{{\phi}} \right|_{{W}} }  \) is nonsingular since \( \lambda = 0 \) is not an eigenvalue by construction.
:::

## Fall 2018 \#5 \( \done \) {#fall-2018-5-done}

Let \( A \) be an \( n \times n \) matrix.

a.  Suppose that \( v \) is a column vector such that the set \( \{v, Av, . . . , A^{n-1} v\} \) is linearly independent. Show that any matrix \( B \) that commutes with \( A \) is a polynomial in \( A \).

b.  Show that there exists a column vector \( v \) such that the set \( \{v, Av, . . . , A^{n-1} v\} \) is linearly independent \( \iff \) the characteristic polynomial of \( A \) equals the minimal polynomial of A.

::: {.concept}
```{=tex}
\envlist
```
-   Powers of \( A \) commute with polynomials in \( A \).
-   The image of a linear map is determined by the image of a basis
:::

::: {.strategy}
```{=tex}
\envlist
```
-   Use Cayley-Hamilton to relate the minimal polynomial to a linear dependence.
-   Get a lower bound on the degree of the minimal polynomial.
-   Use \( A\curvearrowright k[x] \) to decompose into cyclic \( k[x]{\hbox{-}} \)modules, and use special form of denominators in the invariant factors.
-   Reduce to monomials.
:::

::: {.solution}
```{=tex}
\envlist
```
::: {.proof title="of a"}
Letting \( \mathbf{v} \) be fixed, since \( \left\{{A^j \mathbf{v}}\right\} \) spans \( V \) we have A
\[
B\mathbf{v} = \sum_{j=0}^{n-1}c_j A^j \mathbf{v}
.\]

So let \( p(x) = \sum_{j=0}^{n-1}c_jx^j \). Then consider how \( B \) acts on any basis vector \( A^k \mathbf{v} \).

We have
\[
BA^k \mathbf{v} 
&= A^k B\mathbf{v} \\
&= A^k p(A) \mathbf{v} \\
&= p(A) A^k \mathbf{v}
,\]

so \( B = p(A) \) as operators since their actions agree on every basis vector in \( V \).
:::

::: {.proof title="of b, $\\implies$"}
\( \implies \):

If \( \left\{{A^j \mathbf{v}_k {~\mathrel{\Big|}~}0\leq j \leq n-1}\right\} \) is linearly independent, this means that \( A \) does satisfy any polynomial of degree \( d < n \).

So \( \deg m_A(x) = n \), and since \( m_A(x) \) divides \( \chi_A(x) \) and both are monic degree polynomials of degree \( n \), they must be equal.
:::

::: {.proof title="of b, $\\impliedby$"}
\( \impliedby \):

Let \( A\curvearrowright k[x] \) by \( A \curvearrowright p(x) \coloneqq p(A) \). This induces an invariant factor decomposition \( V =\cong \bigoplus k[x]/(f_i) \). Since the product of the invariant factors is the characteristic polynomial, the largest invariant factor is the minimal polynomial, and these two are equal, there can only be one invariant factor and thus the invariant factor decomposition is
\[
V\cong \frac{k[x]}{(\chi_A(x))}
\]
as an isomorphism of \( k[x]{\hbox{-}} \)modules.

So \( V \) is a cyclic \( k[x] \) module, which means that \( V = k[x]\curvearrowright\mathbf{v} \) for some \( \mathbf{v}\in V \) such that \( \operatorname{Ann}(\mathbf{v}) = \chi_A(x) \), i.e. there is some element \( \mathbf{v}\in V \) whose orbit is all of \( V \).

But then noting that monomials span \( k[x] \) as a \( k{\hbox{-}} \)module, we can write
\[
V &\cong
k[x] \curvearrowright\mathbf{v} \\
&\coloneqq\left\{{f(x) \curvearrowright\mathbf{v} {~\mathrel{\Big|}~}f \in k[x]}\right\} \\
&= {\operatorname{span}}_k \left\{{x^k \curvearrowright\mathbf{v} {~\mathrel{\Big|}~}k \geq 0}\right\} \\
&\coloneqq{\operatorname{span}}_k \left\{{A^k\mathbf{v} {~\mathrel{\Big|}~}k \geq 0}\right\}
.\]

Moreover, we can note that if \( \ell \geq \deg \chi_A(x) \), then \( A^\ell \) is a linear combination of \( \left\{{A^j \mathrel{\Big|}0 \leq j \leq n-1}\right\} \), and so
\[
V &\cong {\operatorname{span}}_k \left\{{A^\ell\mathbf{v} {~\mathrel{\Big|}~}\ell \geq 0}\right\} \\
&= {\operatorname{span}}_k \left\{{A^\ell \mathbf{v} {~\mathrel{\Big|}~}1 \leq \ell \leq n-1}\right\}
.\]
:::
:::

## Fall 2019 \#8 \( \work \) {#fall-2019-8-work}

Let \( \{e_1, \cdots, e_n \} \) be a basis of a real vector space \( V \) and let
\[
\Lambda \coloneqq\left\{{ \sum r_i e_i \mathrel{\Big|}r_i \in {\mathbb{Z}}}\right\}
\]

Let \( \cdot \) be a non-degenerate (\( v \cdot w = 0 \) for all \( w \in V \iff v = 0 \)) symmetric bilinear form on \( V \) such that the Gram matrix \( M = (e_i \cdot e_j ) \) has integer entries.

Define the dual of \( \Lambda \) to be
\[
\Lambda  {}^{ \check{} }\coloneqq\{v \in V {~\mathrel{\Big|}~}v \cdot x \in {\mathbb{Z}}\text{ for all } x \in \Lambda
\}
.\]

a.  Show that \( \Lambda \subset \Lambda  {}^{ \check{} } \).

b.  Prove that \( \det M \neq 0 \) and that the rows of \( M^{-1} \) span \( \Lambda {}^{ \check{} } \).

c.  Prove that \( \det M = |\Lambda {}^{ \check{} }/\Lambda| \).

```{=tex}
\todo[inline]{Todo, missing part (c).}
```
::: {.solution}
```{=tex}
\envlist
```
::: {.proof title="of a"}
```{=tex}
\envlist
```
-   Let \( \mathbf{v} \in \Lambda \), so \( \mathbf{v} = \sum_{i=1}^n r_i \mathbf{e}_i \) where \( r_i \in {\mathbb{Z}} \) for all \( i \).

-   Then if \( \mathbf{x} = \sum_{j=1}^n s_j \mathbf{e}_j \in \Lambda \) is arbitrary, we have \( s_j \in {\mathbb{Z}} \) for all \( j \) and
    \[
    {\left\langle {\mathbf{v}},~{\mathbf{x}} \right\rangle} 
    &= {\left\langle {\sum_{i=1}^n r_i \mathbf{e}_i},~{\sum_{j=1}^n s_j \mathbf{e}_j } \right\rangle} \\
    &= \sum_{i=1}^n \sum_{j=1}^n r_i s_j {\left\langle {\mathbf{e}_i},~{\mathbf{e}_j } \right\rangle}  \in {\mathbb{Z}}
    \]
    since this is a sum of products of integers (since \( {\left\langle {\mathbf{e}_i},~{\mathbf{e}_j} \right\rangle} \in {\mathbb{Z}} \) for each \( i, j \) pair by assumption) so \( \mathbf{v} \in \Lambda {}^{ \check{} } \) by definition.
:::

::: {.proof title="of b"}
::: {.claim}
The determinant is nonzero.
:::

-   Suppose \( \det M = 0 \). Then \( \ker M \neq \mathbf{0} \), so let \( \mathbf{v} \in \ker M \) be given by \( \mathbf{v} = \sum_{i=1}^n v_i \mathbf{e}_i \neq \mathbf{0} \).

-   Note that
    \[
    M\mathbf{v} = 0 &\implies
    \left[
    \begin{array}{ccc}
    \mathbf{e}_1 \cdot \mathbf{e}_1 & \mathbf{e}_1 \cdot \mathbf{e}_2 & \cdots \\
    \mathbf{e}_2 \cdot \mathbf{e}_1 & \mathbf{e}_2 \cdot \mathbf{e}_2 & \cdots \\
    \vdots & \vdots & \ddots
    \end{array}
    \right]
    \left[\begin{array}{c}
    v_1 \\ v_2 \\ \vdots
    \end{array}\right] = \mathbf{0} \\ \\
    &\implies \sum_{j=1}^n v_j{\left\langle {\mathbf{e}_k},~{\mathbf{e}_j} \right\rangle} = 0 {\quad \operatorname{for each fixed} \quad} k
    .\]

-   We can now note that \( {\left\langle {\mathbf{e}_k},~{\mathbf{v}} \right\rangle} = \sum_{j=1}^n v_j {\left\langle {\mathbf{e}_k},~{\mathbf{e}_j} \right\rangle} = 0 \) for every \( k \) by the above observation, which forces \( \mathbf{v} = 0 \) by non-degeneracy of \( {\left\langle {{-}},~{{-}} \right\rangle} \), a contradiction.
:::

::: {.proof title="of c"}
```{=tex}
\envlist
```
???

```{=tex}
\todo[inline]{Missing work!}
```
:::
:::

::: {.solution title="Alternative"}
Write \( M = A^tA \) where \( A \) has the \( \mathbf{e}_i \) as columns. Then
\[
M\mathbf{x} = 0 
&\implies A^t A \mathbf{x} = 0 \\
&\implies \mathbf{x}^t A^t A \mathbf{x} = 0 \\
&\implies {\left\lVert {A \mathbf{x}} \right\rVert}^2  = 0 \\
&\implies A\mathbf{x} = 0 \\
&\implies \mathbf{x} = 0
,\]

since \( A \) has full rank because the \( \mathbf{e}_i \) are linearly independent.

Let \( A = [\mathbf{e}_1^t, \cdots, \mathbf{e}_n^t] \) be the matrix with \( \mathbf{e}_i \) in the \( i \)th column.

::: {.claim}
The rows of \( A^{-1} \) span \( \Lambda {}^{ \check{} } \). Equivalently, the columns of \( A^{-t} \) span \( \Lambda {}^{ \check{} } \).
:::

-   Let \( B = A^{-t} \) and let \( \mathbf{b}_i \) denote the columns of \( B \), so \( \operatorname{im}B = {\operatorname{span}}{\left\{{\mathbf{b}_i}\right\}} \).

-   Since \( A \in \operatorname{GL}(n, {\mathbb{Z}}) \), \( A^{-1}, A^t, A^{-t} \in \operatorname{GL}(n, {\mathbb{Z}}) \) as well.
    \[
    \mathbf{v} \in \Lambda {}^{ \check{} }
    &\implies {\left\langle {\mathbf{e}_i},~{\mathbf{v}} \right\rangle} = z_i \in {\mathbb{Z}}\quad \forall i \\
    &\implies A^t \mathbf{v} = \mathbf{z} \coloneqq[z_1, \cdots, z_n] \in {\mathbb{Z}}^n \\
    &\implies \mathbf{v} = A^{-t} \mathbf{z} \coloneqq B\mathbf{z} \in \operatorname{im}B \\
    &\implies \mathbf{v} \in \operatorname{im}B \\
    &\implies \Lambda {}^{ \check{} }\subseteq \operatorname{im}B
    ,\]
    and
    \[
    B^t A = (A^{-t})^t A = A^{-1}A = I \\
    \implies \mathbf{b}_i \cdot \mathbf{e}_j = \delta_{ij} \in {\mathbb{Z}}\\
    \implies \operatorname{im}B \subseteq {\operatorname{span}}~ \Lambda {}^{ \check{} }
    .\]
:::

## Spring 2013 \#6 \( \done \) {#spring-2013-6-done}

Let \( V \) be a finite dimensional vector space over a field \( F \) and let \( T: V\to V \) be a linear operator with characteristic polynomial \( f(x) \in F[x] \).

a.  Show that \( f(x) \) is irreducible in \( F[x] \iff \) there are no proper nonzero subspaces \( W< V \) with \( T(W) \subseteq W \).

b.  If \( f(x) \) is irreducible in \( F[x] \) and the characteristic of \( F \) is 0, show that \( T \) is diagonalizable when we extend the field to its algebraic closure.

```{=tex}
\todo[inline]{Is there a proof without matrices? What if $V$ is infinite dimensional?}
\todo[inline]{How to extend basis?}
```
::: {.concept}
```{=tex}
\envlist
```
-   Every \( \mathbf{v}\in V \) is \( T{\hbox{-}} \)cyclic \( \iff \chi_T(x)/{\mathbb{k}} \) is irreducible.
    -   \( \implies \): Same as argument below.
    -   \( \impliedby \): Suppose \( f \) is irreducible, then \( f \) is equal to the minimal polynomial of \( T \).
-   Characterization of diagonalizability: \( T \) is diagonalizable over \( F \iff \min_{T, F} \) is squarefree in \( \mkern 1.5mu\overline{\mkern-1.5muF\mkern-1.5mu}\mkern 1.5mu[x] \)?
:::

::: {.solution}
```{=tex}
\envlist
```
Let \( f \) be the characteristic polynomial of \( T \).

::: {.proof title="of a, $\\implies$. Matrix-dependent"}
\( \implies \):

-   By contrapositive, suppose there is a proper nonzero invariant subspace \( W<V \) with \( T(W) \subseteq W \), we will show the characteristic polynomial \( f \coloneqq\chi_{V, T}(x) \) is reducible.
-   Since \( T(W)\subseteq W \), the restriction \( g\coloneqq\chi_{V, T}(x) \mathrel{\Big|}_W: W\to W \) is a linear operator on \( W \).

::: {.claim}
\( g \) divides \( f \) in \( {\mathbb{F}}[x] \) and \( \deg(g) < \deg(f) \).
:::

-   Choose an ordered basis for \( W \), say \( {\mathcal{B}}_W \coloneqq\left\{{\mathbf{w}_1, \cdots, \mathbf{w}_k}\right\} \) where \( k=\dim_F(W) \)

-   Claim: this can be extended to a basis of \( V \), say \( {\mathcal{B}}_V \coloneqq\left\{{\mathbf{w}_1, \cdots, \mathbf{w}_k, \mathbf{v}_1, \cdots, \mathbf{v}_j}\right\} \) where \( k+j = \dim_F(V) \).

    -   Note that since \( W<V \) is proper, \( j\geq 1 \).

-   Restrict \( T \) to \( W \) to get \( T_W \), then let \( B = [T_W]_{{\mathcal{B}}_W} \) be the matrix representation of \( T_W \) with respect to \( {\mathcal{B}}_W \).

-   Now consider the matrix representation \( [T]_{{\mathcal{B}}_V} \), in block form this is given by
    \[
    [T]_{{\mathcal{B}}_V} = 
    \begin{bmatrix}
    B & C \\
    0 & D
    \end{bmatrix}
    \]
    where we've used that \( W<V \) is proper to get the existence of \( C, D \) (there is at least one additional row/column since \( j\geq 1 \) in the extended basis.) `\todo[inline]{Why?}`{=tex}

-   Now expand along the first column block to obtain
    \[
    \chi_{T, V}(x) \coloneqq\det([T]_{{\mathcal{B}}_V} - xI) = \det(B - xI)\cdot \det(D - xI) \coloneqq\chi_{T, W}(x) \cdot \det(D-xI)
    .\]

-   Claim: \( \det(D - xI) \in xF[x] \) is nontrivial

-   The claim follows because this forces \( \deg(\det(D-xI)) \geq 1 \) and so \( \chi_{T, W}(x) \) is a proper divisor of \( \chi_{T, V}(x) \).

-   Thus \( f \) is reducible.
:::

::: {.proof title="of a, $\\impliedby$"}
\( \impliedby \)

-   Suppose \( f \) is reducible, then we will produce a proper \( T{\hbox{-}} \)invariant subspace.
-   Claim: if \( f \) is reducible, there exists a nonzero, noncyclic vector \( \mathbf{v} \).
-   Then \( {\operatorname{span}}_k\left\{{T^j\mathbf{v}}\right\}_{j=1}^d \) is a \( T{\hbox{-}} \)invariant subspace that is nonzero, and not the entire space since \( \mathbf{v} \) is not cyclic.
:::

::: {.proof title="of b"}
```{=tex}
\envlist
```
-   Let \( \min_{T, F}(x) \) be the minimal polynomial of \( T \) and \( \chi_{T, F}(x) \) be its characteristic polynomial.
-   By Cayley-Hamilton, \( \min_{T, F}(x) \) divides \( \chi_{T, F} \)
-   Since \( \chi_{T, F} \) is irreducible, these polynomials are equal.
-   Claim: \( T/F \) is diagonalizable \( \iff \min_{T, F} \) splits over \( F \) and is squarefree.
-   Replace \( F \) with its algebraic closure, then \( \min_{T, F} \) splits.
-   Claim: in characteristic zero, every irreducible polynomial is separable
    -   Proof: it must be the case that either \( \gcd(f, f') = 1 \) or \( f' \equiv 0 \), where the second case only happens in characteristic \( p>0 \).
    -   The first case is true because \( \deg f' < \deg f \), and if \( \gcd(f, f') = p \), then \( \deg p < \deg f \) and \( p\bigm|f \) forces \( p=1 \) since \( f \) is irreducible.
-   So \( \min_{T, F} \) splits into distinct linear factors
-   Thus \( T \) is diagonalizable.
:::
:::

## Fall 2020 \#8 \( \work \) {#fall-2020-8-work}

Let \( A\in \operatorname{Mat}(n\times n, {\mathbb{C}}) \) such that the group generated by \( A \) under multiplication is finite. Show that
\[
\operatorname{Tr}(A^{-1}) ={\overline{{\operatorname{Tr}(A) }}}
,\]
where \( {\overline{{({-})}}} \) denotes taking the complex conjugate and \( \operatorname{Tr}({-}) \) is the trace.

# Linear Algebra: Canonical Forms

## \( \star \) Spring 2012 \#8 \( \work \) {#star-spring-2012-8-work}

Let \( V \) be a finite-dimensional vector space over a field \( k \) and \( T:V\to V \) a linear transformation.

a.  Provide a definition for the *minimal polynomial* in \( k[x] \) for \( T \).

b.  Define the *characteristic polynomial* for \( T \).

c.  Prove the Cayley-Hamilton theorem: the linear transformation \( T \) satisfies its characteristic polynomial.

## \( \star \) Spring 2020 \#8 \( \work \) {#star-spring-2020-8-work}

Let \( T:V\to V \) be a linear transformation where \( V \) is a finite-dimensional vector space over \( {\mathbb{C}} \). Prove the Cayley-Hamilton theorem: if \( p(x) \) is the characteristic polynomial of \( T \), then \( p(T) = 0 \). You may use canonical forms.

## \( \star \) Spring 2012 \#7 \( \work \) {#star-spring-2012-7-work}

Consider the following matrix as a linear transformation from \( V\coloneqq{\mathbb{C}}^5 \) to itself:
\[
A=\left(\begin{array}{ccccc}
-1 & 1 & 0 & 0 & 0 \\
-4 & 3 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 & 1 \\
0 & 0 & 0 & 1 & 0 \\
0 & 0 & 0 & 0 & 2
\end{array}\right)
.\]

a.  Find the invariant factors of \( A \).

b.  Express \( V \) in terms of a direct sum of indecomposable \( {\mathbb{C}}[x]{\hbox{-}} \)modules.

c.  Find the Jordan canonical form of \( A \).

## Fall 2019 Final \#8 \( \work \) {#fall-2019-final-8-work}

Exhibit the rational canonical form for

-   \( A\in M_6({\mathbb{Q}}) \) with minimal polynomial \( (x-1)(x^2 + 1)^2 \).
-   \( A\in M_{10}({\mathbb{Q}}) \) with minimal polynomial \( (x^2+1)^2(x^3 + 1) \).

## Fall 2019 Final \#9 \( \work \) {#fall-2019-final-9-work}

Exhibit the rational and Jordan canonical forms for the following matrix \( A\in M_4({\mathbb{C}}) \):
\[
  A=\left(\begin{array}{cccc}
  2 & 0 & 0 & 0 \\
  1 & 1 & 0 & 0 \\
  -2 & -2 & 0 & 1 \\
  -2 & 0 & -1 & -2
  \end{array}\right)
  .\]

## Spring 2016 \#7 \( \work \) {#spring-2016-7-work}

Let \( D = {\mathbb{Q}}[x] \) and let \( M \) be a \( {\mathbb{Q}}[x]{\hbox{-}} \)module such that
\[
M \cong \frac{\mathbb{Q}[x]}{(x-1)^{3}} \oplus \frac{\mathbb{Q}[x]}{\left(x^{2}+1\right)^{3}} \oplus \frac{\mathbb{Q}[x]}{(x-1)\left(x^{2}+1\right)^{5}} \oplus \frac{\mathbb{Q}[x]}{(x+2)\left(x^{2}+1\right)^{2}}
.\]

Determine the elementary divisors and invariant factors of \( M \).

## Spring 2020 \#7 \( \work \) {#spring-2020-7-work}

Let
\[
A=\left[\begin{array}{ccc}
2 & 0 & 0 \\
4 & 6 & 1 \\
-16 & -16 & -2
\end{array}\right] \in M_{3}(\mathrm{C})
.\]

a.  Find the Jordan canonical form \( J \) of \( A \).

b.  Find an invertible matrix \( P \) such that \( P^{-1}A P = J \).

    > You should not need to compute \( P^{-1} \).

c.  Write down the minimal polynomial of \( A \).

## Spring 2019 \#7 \( \done \) {#spring-2019-7-done}

Let \( p \) be a prime number. Let \( A \) be a \( p \times p \) matrix over a field \( F \) with 1 in all entries except 0 on the main diagonal.

Determine the Jordan canonical form (JCF) of \( A \)

a.  When \( F = {\mathbb{Q}} \),

b.  When \( F = {\mathbb{F}}_p \).

> Hint: In both cases, all eigenvalues lie in the ground field. In each case find a matrix \( P \) such that \( P^{-1}AP \) is in JCF.

::: {.strategy}
```{=tex}
\envlist
```
-   Work with matrix of all ones instead.
-   Eyeball eigenvectors.
-   Coefficients in minimal polynomial: size of largest Jordan block
-   Dimension of eigenspace: number of Jordan blocks
-   We can always read off the *characteristic* polynomial from the spectrum.
:::

::: {.concept}
```{=tex}
\envlist
```
-   Todo
:::

::: {.solution}
```{=tex}
\envlist
```
::: {.proof title="of a"}
Let \( A \) be the matrix in the question, and \( B \) be the matrix containing 1's in every entry.

-   Noting that \( B = A+I \), we have
    \[
    &B\mathbf{x} = \lambda \mathbf{x} \\
    &\iff (A+I) \mathbf{x} = \lambda \mathbf{x} \\
    &\iff A \mathbf{x} = (\lambda - 1) \mathbf{x}
    ,\]
    so we will find the eigenvalues of \( B \) and subtract one from each.

-   Note that \( B\mathbf{v} = {\left[ {\sum v_i, \sum v_i, \cdots, \sum v_i} \right]} \), i.e. it has the effect of summing all of the entries of \( \mathbf{v} \) and placing that sum in each component.

-   We proceed by finding \( p \) eigenvectors and eigenvalues, since the JCF and minimal polynomials will involve eigenvalues and the transformation matrix will involve (generalized) eigenvectors.

::: {.claim title="1"}
Each vector of the form \( \mathbf{p}_i \coloneqq\mathbf{e}_1 - \mathbf{e}_{i+1} = {\left[ {1, 0, 0,\cdots, 0 -1, 0, \cdots, 0 } \right]} \) where \( i\neq j \) is also an eigenvector with eigenvalues \( \lambda_0 = 0 \), and this gives \( p-1 \) linearly independent vectors spanning the eigenspace \( E_{\lambda_0} \)
:::

::: {.claim title="2"}
\( \mathbf{v}_1 = {\left[ {1, 1, \cdots, 1} \right]} \) is an eigenvector with eigenvalue \( \lambda_1 = p \).
:::

-   Using that the eigenvalues of \( A \) are \( 1+\lambda_i \) for \( \lambda_i \) the above eigenvalues for \( B \),
    \[
    \operatorname{Spec}(B) \coloneqq\left\{{(\lambda_i, m_i)}\right\} &=  \left\{{(p, 1), (0, p-1)}\right\}  \implies \chi_{B}(x) = (x-p)x^{p-1} \\ 
    \implies \operatorname{Spec}(A) &= \left\{{(p-1,1), (-1, p-1) }\right\}  \implies \chi_{A}(x) = (x- p+1)(x+1)^{p-1} \\
    \]

-   The dimensions of eigenspaces are preserved, thus
    \[
    JCF_{\mathbb{Q}}(A)
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

-   The matrix \( P \) such that \( A = PJP^{-1} \) will have columns the bases of the generalized eigenspaces.

-   In this case, the generalized eigenspaces are the usual eigenspaces, so
    \[
    P = [\mathbf{v}_1, \mathbf{p}_1, \cdots, \mathbf{p}_{p-1}] =
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

::: {.proof title="of claim 1"}
```{=tex}
\envlist
```
-   Compute
    \[B \mathbf{p}_i = {\left[ { 1 + 0 + \cdots + 0 + (-1) + 0 + \cdots + 0} \right]} = {\left[ {0, 0, \cdots, 0} \right]}\]
-   So every \( \mathbf{p}_i \in \ker(B) \), so they are eigenvectors with eigenvalue 0.
-   Since the first component is fixed and we have \( p-1 \) choices for where to place a \( -1 \), this yields \( p-1 \) possibilities for \( \mathbf{p}_i \)
-   These are linearly independent since the \( (p-1)\times (p-1) \) matrix \( {\left[ { \mathbf{p}_1^t, \cdots, \mathbf{p}_{p-1}^t} \right]} \) satisfies
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

::: {.proof title="of claim 2"}
```{=tex}
\envlist
```
-   Compute
    \[B\mathbf{v} = {\left[ {\sum_{i=1}^p 1, \sum_{i=1}^p 1, \cdots, \sum_{i=1}^p 1} \right]} = {\left[ {p, p, \cdots, p} \right]} = p {\left[ {1, 1, \cdots, 1} \right]} = p\mathbf{v}_1,\]
    thus \( \lambda_1 = p \)
-   \( \dim E_{\lambda_1} = 1 \) since the eigenspaces are orthogonal and \( E_{\lambda_0} \oplus E_{\lambda_1} \leq F^p \) is a subspace, so \( p > \dim(E_{\lambda_0}) + \dim E_{\lambda_1} = p-1 + \dim E_{\lambda_1} \) and it isn't zero dimensional.
:::

::: {.proof title="of b"}
For \( F = {\mathbb{F}}_p \), all eigenvalues/vectors still lie in \( {\mathbb{F}}_p \), but now \( -1 = p-1 \), making \( (x-(p-1))(x+1)^{p-1} = (x+1)(x+1)^{p-1} \), so \( \chi_{A, {\mathbb{F}}_p}(x) = (x+1)^p \), and the Jordan blocks may merge.

-   A computation shows that \( (A+I)^2 = pA = 0 \in M_p({\mathbb{F}}_p) \) and \( (A+I) \neq 0 \), so \( \min_{A, {\mathbb{F}}_p}(x) = (x+1)^2 \).
    -   Thus the largest Jordan block corresponding to \( \lambda = -1 \) is of size 2
-   Can check that \( \det(A) = \pm 1 \in {\mathbb{F}}_p^{\times} \), so the vectors \( \mathbf{e}_1 - \mathbf{e}_i \) are still linearly independent and thus \( \dim E_{-1} = p-1 \)
    -   So there are \( p-1 \) Jordan blocks for \( \lambda = 0 \).

Summary:
\[
\min_{A, {\mathbb{F}}_p}(x) &= (x+1)^2 \\
\chi_{A, {\mathbb{F}}_p}(x) &\equiv (x+1)^p \\
\dim E_{-1} &= p-1
.\]

Thus
\[
JCF_{{\mathbb{F}}_p}(A)
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

To obtain a basis for \( E_{\lambda = 0} \), first note that the matrix \( P = [\mathbf{v}_1, \mathbf{p}_1, \cdots , \mathbf{p}_{p-1}] \) from part (a) is singular over \( {\mathbb{F}}_p \), since
\[
\mathbf{v}_1 + \mathbf{p}_1 + \mathbf{p}_2 + \cdots + \mathbf{p}_{p-2}
&= [p-1, 0, 0, \cdots, 0, 1] \\
&= [-1, 0,0,\cdots, 0, 1] \\
&= - \mathbf{p}_{p-1}
.\]

We still have a linearly independent set given by the first \( p-1 \) columns of \( P \), so we can extend this to a basis by finding one linearly independent generalized eigenvector.

Solving \( (A-I\lambda)\mathbf{x} = \mathbf{v}_1 \) is our only option (the others won't yield solutions). This amounts to solving \( B\mathbf{x} = \mathbf{v}_1 \), which imposes the condition \( \sum x_i = 1 \), so we can choose \( \mathbf{x} = [1, 0, \cdots, 0] \).

Thus
\[
P = [\mathbf{v}_1, \mathbf{x}, \mathbf{p}_1, \cdots, \mathbf{p}_{p-2}] =
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

## Spring 2018 \#4 \( \work \) {#spring-2018-4-work}

Let
\[
A=\left[\begin{array}{lll}{0} & {1} & {-2} \\ {1} & {1} & {-3} \\ {1} & {2} & {-4}\end{array}\right] \in M_{3}(\mathbb{C})
\]

a.  Find the Jordan canonical form \( J \) of \( A \).

b.  Find an invertible matrix \( P \) such that \( P^{-1}AP = J \).

    > You should not need to compute \( P^{-1} \).

## Spring 2017 \#6 \( \work \) {#spring-2017-6-work}

Let \( A \) be an \( n\times n \) matrix with all entries equal to \( 0 \) except for the \( n-1 \) entries just above the diagonal being equal to 2.

a.  What is the Jordan canonical form of \( A \), viewed as a matrix in \( M_n({\mathbb{C}}) \)?

b.  Find a nonzero matrix \( P\in M_n({\mathbb{C}}) \) such that \( P^{-1}A P \) is in Jordan canonical form.

## Spring 2016 \#1 \( \work \) {#spring-2016-1-work}

Let
\[
A=\left(\begin{array}{ccc}
-3 & 3 & -2 \\
-7 & 6 & -3 \\
1 & -1 & 2
\end{array}\right) \in M_{3}(\mathrm{C})
.\]

a.  Find the Jordan canonical form \( J \) of \( A \).

b.  Find an invertible matrix \( P \) such that \( P^{-1}A P = J \). You do not need to compute \( P^{-1} \).

## Spring 2015 \#6 \( \work \) {#spring-2015-6-work}

Let \( F \) be a field and \( n \) a positive integer, and consider
\[
A=\left[\begin{array}{ccc}
1 & \dots & 1 \\
& \ddots & \\
1 & \dots & 1
\end{array}\right] \in M_{n}(F)
.\]

Show that \( A \) has a Jordan normal form over \( F \) and find it.

> Hint: treat the cases \( n\cdot 1 \neq 0 \) in \( F \) and \( n\cdot 1 = 0 \) in \( F \) separately.

## Fall 2014 \#5 \( \work \) {#fall-2014-5-work}

Let \( T \) be a \( 5\times 5 \) complex matrix with characteristic polynomial \( \chi(x) = (x-3)^5 \) and minimal polynomial \( m(x) = (x-3)^2 \). Determine all possible Jordan forms of \( T \).

## Spring 2013 \#5 \( \work \) {#spring-2013-5-work}

Let \( T: V\to V \) be a linear map from a 5-dimensional \( {\mathbb{C}}{\hbox{-}} \)vector space to itself and suppose \( f(T) = 0 \) where \( f(x) = x^2 + 2x + 1 \).

a.  Show that there does not exist any vector \( v\in V \) such that \( Tv = v \), but there *does* exist a vector \( w\in V \) such that \( T^2 w= w \).

b.  Give all of the possible Jordan canonical forms of \( T \).

## Spring 2021 \#1 \( \work \) {#spring-2021-1-work}

Let m
\[
A \coloneqq
\begin{bmatrix}
r & 1 & -1 \\
-6 & -1 & 2 \\
2 & 1 & 1
\end{bmatrix}
\in \operatorname{Mat}(3\times 3, {\mathbb{C}})
.\]

a.  Find the Jordan canonical form \( J \) of \( A \).

b.  Find an invertible matrix \( P \) such that \( J = P ^{-1}A P \).

> You should not need to compute \( P^{-1} \)

c.  Write down the minimal polynomial of \( A \).

## Fall 2020 \#5 \( \work \) {#fall-2020-5-work}

Consider the following matrix:
\[
B \coloneqq
\begin{bmatrix}
1 & 3 & 3
\\
2 & 2 & 3
\\
-1 & -2 & -2
\end{bmatrix}
.\]

a.  Find the minimal polynomial of \( B \).

b.  Find a \( 3\times 3 \) matrix \( J \) in Jordan canonical form such that \( B = JPJ^{-1} \) where \( P \) is an invertible matrix.
