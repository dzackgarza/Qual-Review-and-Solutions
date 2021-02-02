# Summer 2003

## 1 

Describe all possible covering maps between $S^2, T^2, K$

:::{.solution}

\envlist
:::{.concept}
\envlist

1. $\tilde X \surjects X$ induces $\pi_1(\tilde X) \injects \pi_1(X)$
2. $\chi(\tilde X) = n \chi (X)$
3. $\pi_n(X) = [S^n, X]$
4. $Y \to X$ with $\pi_1(Y) = 0$ and $\tilde X \homotopic \pt \implies$ every $Y\mapsvia{f} X$ is nullhomotopic.
5. $\pi_*(T^2) = [\ZZ \ast \ZZ, 0\rightarrow]$
6. $\pi_*(K) = [\ZZ \semidirect_{\ZZ_2} \ZZ, 0\rightarrow]$
7. Universal covers are homeomorphic.
8. $\pi_{\geq 2}(\tilde X) \cong \pi_{\geq 2}(X)$

:::

Spaces

- $S^2 \surjects T^2$
- $S^2 \surjects K$
- $K \surjects S^2$
- $T^2 \surjects S^2$
	- All covered by the fact that 
  $$
    \ZZ = \pi_2(S^2) \neq \pi_2(X) = 0
    $$ 
    for $X = T^2, K$.
- $K \surjects T^2$
	- Doesn't cover, would induce $\pi_1(K) \injects \pi_1(T^2) \implies \ZZ\semidirect \ZZ \injects \ZZ^2$ but this would be a non-abelian subgroup of an abelian group.
- $T^2 \surjects K$
  - ?

\todo[inline]{Not complete!}

:::

## 2

Show that $\ZZ^{\ast 2}$ has subgroups isomorphic to $\ZZ^{\ast n}$ for every $n$.

:::{.solution}


\envlist
:::{.concept}
\envlist

1. $\pi_1(\bigvee^k S^1) = \ZZ^{\ast k}$
2. $\tilde X \surjects X \implies \pi_1(\tilde X) \injects \pi_1(X)$
3. Every subgroup $G \leq \pi_1(X)$ corresponds to a covering space $X_G \surjects X$
4. $A \subseteq B \implies F(A) \leq F(B)$ for free groups.

:::

It is easier to prove the stronger claim that $\ZZ^\NN \leq \ZZ^{\ast 2}$ (i.e. the free group on countably many generators) and use fact 4 above.
Just take the covering space $\tilde X \surjects S^1 \vee S^1$ defined via the gluing map $\RR \union_{\ZZ} S^1$ which attaches a circle to each integer point, taking 0 as the base point. Then let $a$ denote a translation and $b$ denote traversing a circle, so we have $\pi_1(\tilde X) = \left<\union_{n\in\ZZ}a^nba^{-n}\right>$ which is a free group on countably many generators. Since $\tilde X$ is a covering space, $\pi_1(\tilde X) \injects \pi_1(S^1 \vee S^1) = \ZZ^{\ast 2}$. By 4, we can restrict this to $n$ generators for any $n$ to get a subgroup, and $A\leq B \leq C \implies A \leq C$ as groups.

:::

## 3

Construct a space having $H_*(X) = [\ZZ, 0, 0, 0, 0, \ZZ_4, 0, \cdots]$.

:::{.solution}

\envlist
:::{.concept}
\envlist

- Construction of Moore Spaces
- $\tilde H_n(\Sigma X) = \tilde H_{n-1}(X)$, using $\Sigma X = C_X \union_X C_X$ and Mayer-Vietoris.
:::

Take $X = e^0 \union_{\Phi_1} e^5 \union_{\Phi_2} e^6$, where
\[
\Phi_1: \del B^5 = S^4 \mapsvia{z~\mapsto z^0} e^0 \\
\Phi_2: \del B^6 = S^5 \mapsvia{z~\mapsto z^4} e^5
.\]

where $\deg \Phi_2 = 4$.
:::

## 4 

Compute the complement of a knotted solid torus in $S^3$.

:::{.solution}


\envlist
:::{.concept}
\envlist

- $H_*(T^2) = [\ZZ, \ZZ^2, \ZZ, 0\rightarrow]$
- $N^{(1)} \homotopic S^1$, so $H_{\geq 2}(N) = 0$.
- A SES $0\to A\to B \to F \to 0$ with $F$ free splits.
- $0\to A \to B \mapsvia{\cong} C \to D \to 0$ implies $A = D = 0$.

:::

Let $N$ be the knotted solid torus, so that $\del N = T^2$, and let $X = S^3 - N$. Then

- $S^3 = N \union_{T^2} X$
- $N \cap X = T^2$

and we apply Mayer-Vietoris to the reduced homology of $S^3$:

% https://q.uiver.app/?q=WzAsMTIsWzAsMCwiSF80KFReMikiXSxbMiwwLCJIXzQoTikgXFxvcGx1cyBIXzQoWCkiXSxbNCwwLCJIXzQoU14zKSJdLFswLDIsIkhfNChUXjIpIl0sWzAsNCwiSF80KFReMikiXSxbMiw0LCJIXzQoTikgXFxvcGx1cyBIXzQoWCkiXSxbMiwyLCJIXzQoTikgXFxvcGx1cyBIXzQoWCkiXSxbNCwyLCJIXzQoU14zKSJdLFs0LDQsIkhfNChTXjMpIl0sWzAsNiwiSF80KFNeMykiXSxbMiw2LCJIXzQoTikgXFxvcGx1cyBIXzQoWCkiXSxbNCw2LCJIXzQoU14zKSJdLFs0LDVdLFs4LDldLFs5LDEwXSxbMTAsMTFdLFs1LDhdLFszLDZdLFs2LDddLFs3LDRdLFsyLDNdLFswLDFdLFsxLDJdXQ==
\begin{tikzcd}
	{H_4(T^2)} && {H_4(N) \oplus H_4(X)} && {H_4(S^3)} \\
	\\
	{H_3(T^2)} && {H_3(N) \oplus H_3(X)} && {H_3(S^3)} \\
	\\
	{H_2(T^2)} && {H_2(N) \oplus H_2(X)} && {H_2(S^3)} \\
	\\
	{H_1(S^3)} && {H_1(N) \oplus H_1(X)} && {H_1(S^3)}
	\arrow[from=5-1, to=5-3]
	\arrow[from=5-3, to=5-5]
	\arrow[from=5-5, to=7-1, out=360, in=180]
	\arrow[from=7-1, to=7-3]
	\arrow[from=7-3, to=7-5]
	\arrow[from=3-1, to=3-3]
	\arrow[from=3-3, to=3-5]
	\arrow[from=3-5, to=5-1, out=360, in=180]
	\arrow[from=5-3, to=5-5]
	\arrow[from=1-5, to=3-1, out=360, in=180]
	\arrow[from=1-1, to=1-3]
	\arrow[from=1-3, to=1-5]
\end{tikzcd}

We can plug in known information and deduce some maps:

% https://q.uiver.app/?q=WzAsMTIsWzAsMCwiMCJdLFs0LDAsIjAiXSxbMCwyLCIwIixbMjQwLDYwLDYwLDFdXSxbMCw0LCJcXFpaIixbMjQwLDYwLDYwLDFdXSxbMiw0LCJIXzIoWCkiLFsyNDAsNjAsNjAsMV1dLFsyLDIsIkhfMyhYKSIsWzI0MCw2MCw2MCwxXV0sWzQsMiwiXFxaWiIsWzI0MCw2MCw2MCwxXV0sWzQsNCwiMCIsWzI0MCw2MCw2MCwxXV0sWzAsNiwiXFxaWl57XFxvcGx1cyAyfSJdLFsyLDYsIlxcWlogXFxvcGx1cyBIXzEoWCkgIl0sWzQsNiwiMCJdLFsyLDAsIjAiXSxbMyw0LCIiLDAseyJjb2xvdXIiOlsyNDAsNjAsNjBdfV0sWzcsOF0sWzgsOSwiXFxzaW0iLDAseyJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6InRvcCJ9LCJoZWFkIjp7Im5hbWUiOiJlcGkifX19XSxbOSwxMF0sWzQsNywiIiwwLHsiY29sb3VyIjpbMjQwLDYwLDYwXX1dLFsyLDUsIiIsMCx7ImNvbG91ciI6WzI0MCw2MCw2MF19XSxbNSw2LCIiLDAseyJjb2xvdXIiOlsyNDAsNjAsNjBdfV0sWzYsMywiIiwwLHsiY29sb3VyIjpbMjQwLDYwLDYwXX1dLFsxLDJdLFswLDExXSxbMTEsMV1d
\begin{tikzcd}
	0 && 0 && 0 \\
	\\
	\textcolor{rgb,255:red,92;green,92;blue,214}{0} && \textcolor{rgb,255:red,92;green,92;blue,214}{H_3(X)} && \textcolor{rgb,255:red,92;green,92;blue,214}{\ZZ} \\
	\\
	\textcolor{rgb,255:red,92;green,92;blue,214}{\ZZ} && \textcolor{rgb,255:red,92;green,92;blue,214}{H_2(X)} && \textcolor{rgb,255:red,92;green,92;blue,214}{0} \\
	\\
	{\ZZ^{\oplus 2}} && {\ZZ \oplus H_1(X) } && 0
	\arrow[color={rgb,255:red,92;green,92;blue,214}, from=5-1, to=5-3]
	\arrow[from=5-5, to=7-1, out=360, in=180]
	\arrow["\sim", hook, two heads, from=7-1, to=7-3]
	\arrow[from=7-3, to=7-5]
	\arrow[color={rgb,255:red,92;green,92;blue,214}, from=5-3, to=5-5]
	\arrow[color={rgb,255:red,92;green,92;blue,214}, from=3-1, to=3-3]
	\arrow[color={rgb,255:red,92;green,92;blue,214}, from=3-3, to=3-5]
	\arrow[color={rgb,255:red,92;green,92;blue,214}, from=3-5, to=5-1, out=360, in=180]
	\arrow[from=1-5, to=3-1, out=360, in=180]
	\arrow[from=1-1, to=1-3]
	\arrow[from=1-3, to=1-5]
\end{tikzcd}


We then deduce:

- $H_0(X) = \ZZ$: ? (Appeal to some path-connectedness argument?)

- $H_1(X) = \ZZ$ using the SES appearing on the first row:
  \[
  0 \to \ZZ^{ \oplus 2} \to \ZZ \oplus H_1(X) \to 0
  \]
  which is thus an isomorphism.

- $H_2(X) = H_3(X) = 0$ by examining the SES spanning lines 3 and 2: 
  \[
  0 \injects H_3(X) \injects \ZZ \mapsvia{\cong_{\del_3}} \ZZ \surjects H_2(X) \surjects 0
  \]
  Claim: \( \bd_3 \) must be an isomorphism.
  If this is true, $H_3(X) \cong \ker \bd_3 = 0$ and $H_2(X) \cong \coker(\bd_3) \da \ZZ/\im(\bd_3) \cong \ZZ/\ZZ = 0$.

  \todo[inline]{Why is this true?}

:::

## 5 

Compute the homology and cohomology of a closed, connected, oriented 3-manifold $M$ with $\pi_1(M) = \ZZ^{\ast 2}$.

:::{.solution}
Facts used:

- $M$ closed, connected, oriented $\implies H_i(M)\cong H^{n-i}(M)$
- $H_1(X) = \Ab(\pi_1(X))$.
- For orientable manifolds $H_n(M^n) = \ZZ$

**Homology**

- Since $M$ is connected, $H_0 = \ZZ$
- Since $\pi_1(M) = \ZZ^{\ast 2}$, $H_1$ is the abelianization and $H_1(X) = \ZZ^2$
- Since $M$ is closed/connected/oriented, Poincaré Duality holds and $H_2 = H^{3-2} = H^1 = \mathbf{F} H_1 + \mathbf{T}H_0$ by UCT. Since $H_0=\ZZ$ is torsion-free, we have $H_2(M) = H_1(M) =  \ZZ^2$.
- Since $M$ is an orientable manifold, $H_3(M) = \ZZ$
- So $H_*(M) = [\ZZ, \ZZ^2, \ZZ^2, \ZZ, 0\rightarrow]$

**Cohomology**

- By Poincaré Duality, $H^*(M) = \widehat{H_*(M)} = [\ZZ, \ZZ^2, \ZZ^2, \ZZ, 0, \cdots]$. (Where the hat denotes reversing the list.)


:::


## 6

Compute $\ext(\ZZ \oplus \ZZ/2 \oplus  \ZZ/3, \ZZ \oplus  \ZZ/4 \oplus  \ZZ/5)$.

:::{.solution}


\envlist
:::{.concept}
\envlist
Facts Used:[^fix_facts_on_ext_oskar]

- Since $\ZZ$ is a free $\ZZ\dash$module,
\[
\ext(\ZZ, \ZZ/m) = 0
\]

- Using the usual projective resolution $0 \to \ZZ \to \ZZ \to \ZZ/n \to 0$, 
\[
\ext(\ZZ/n, \ZZ) = \ZZ/n
.\]

- 
\[
\ext(\ZZ/n, \ZZ/m) = (\ZZ/m) / (n \cdot \ZZ/m) \cong (\ZZ/m) / (d \cdot \ZZ/m) && 
\text{where } d \da \gcd(m, n)
.\]
  General principle: $\Ext(\ZZ/n, G) = G/nG$ 

  By applying $\Hom_\ZZ(\wait, G)$ to the above resolution: 

\begin{tikzcd}
	& 0 & {\Ext^1_\ZZ(\ZZ/n, G)} \\
	\\
	{\Hom_\ZZ(\ZZ, G)} & {\Hom_\ZZ(\ZZ, G)} & {\Hom_\ZZ(\ZZ/n, G)} & 0 \\
	&&& {}
	\arrow[hook', from=3-3, to=3-2]
	\arrow["{\cdot n}"', from=3-2, to=3-1]
	\arrow[two heads, from=3-1, to=1-3, out=180, in=360]
	\arrow[from=1-3, to=1-2]
	\arrow[from=3-4, to=3-3]
\end{tikzcd}

  > [Link to Diagram](https://q.uiver.app/?q=WzAsNyxbMiwwLCIwIl0sWzAsMiwiXFxIb21fXFxaWihcXFpaLCBHKSJdLFsyLDIsIlxcSG9tX1xcWlooXFxaWiwgRykiXSxbNCwyLCJcXEhvbV9cXFpaKFxcWlovbiwgRykiXSxbNCwwLCJcXEV4dF4xX1xcWlooXFxaWi9uLCBHKSJdLFs2LDIsIjAiXSxbNCwzXSxbMywyLCIiLDIseyJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6ImJvdHRvbSJ9fX1dLFsyLDEsIlxcY2RvdCBuIiwyXSxbMSw0LCIiLDAseyJzdHlsZSI6eyJoZWFkIjp7Im5hbWUiOiJlcGkifX19XSxbNCwwXSxbNSwzXV0=)

  which can be identified with:

\begin{tikzcd}
	&& 0 && {G/nG} \\
	\\
	G && G && {\Hom_\ZZ(\ZZ/n, G)} && 0 \\
	&&&& {}
	\arrow[hook', from=3-5, to=3-3]
	\arrow["{\cdot n}"', from=3-3, to=3-1]
	\arrow[two heads, from=3-1, to=1-5, out=180, in=360]
	\arrow[from=1-5, to=1-3]
	\arrow[from=3-7, to=3-5]
\end{tikzcd}

  > [Link to Diagram](https://q.uiver.app/?q=WzAsNyxbMiwwLCIwIl0sWzAsMiwiRyJdLFsyLDIsIkciXSxbNCwyLCJcXEhvbV9cXFpaKFxcWlovbiwgRykiXSxbNCwwLCJHL25HIl0sWzYsMiwiMCJdLFs0LDNdLFszLDIsIiIsMix7InN0eWxlIjp7InRhaWwiOnsibmFtZSI6Imhvb2siLCJzaWRlIjoiYm90dG9tIn19fV0sWzIsMSwiXFxjZG90IG4iLDJdLFsxLDQsIiIsMCx7InN0eWxlIjp7ImhlYWQiOnsibmFtZSI6ImVwaSJ9fX1dLFs0LDBdLFs1LDNdXQ==)

3. Contravariant Hom takes coproducts to products:
\[
\ext(\bigoplus_{i\in I} A_i, \prod_{k\in K} B_k) = \prod_{i\in I} \prod_{k\in K} \ext(A_i, B_k)
.\]

:::


Write 
\[
A_\wait &\da A_1 \oplus A_2 \oplus A_3 \da \ZZ \oplus  \ZZ/2 \oplus  \ZZ/3 \\
B_\wait &\da B_1 \oplus B_2 \oplus B_3 \da \ZZ \oplus \ZZ/4 \oplus  \ZZ/5
.\]

We can then define the bicomplex \[
C_{\wait, \wait} \da \Ext(A_\wait, B_\wait) = \bigoplus_{0 \leq i, k \leq 3} \Ext(A_i, B_k)
,\]
i.e. $C_{i, k} \da \Ext(A_i, B_k)$, which can be organized into the following diagram where we take the Ext at each position and sum them all together:

\begin{tikzcd}
	{\Ext(A_1, B_1)} && {\Ext(A_1, B_2)} && {\Ext(A_1, B_3)} \\
	\\
	{\Ext(A_2, B_1)} && {\Ext(A_2, B_2)} && {\Ext(A_2, B_3)} \\
	\\
	{\Ext(A_3, B_1)} && {\Ext(A_3, B_2)} && {\Ext(A_3, B_3)}
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsOSxbMCwwLCJcXEV4dF8xXlxcWlooQV8xLCBCXzEpIl0sWzAsMiwiXFxFeHRfMV5cXFpaKEFfMiwgQl8xKSJdLFswLDQsIlxcRXh0XzFeXFxaWihBXzMsIEJfMSkiXSxbMiwwLCJcXEV4dF8xXlxcWlooQV8xLCBCXzIpIl0sWzQsMCwiXFxFeHRfMV5cXFpaKEFfMSwgQl8zKSJdLFsyLDIsIlxcRXh0XzFeXFxaWihBXzIsIEJfMikiXSxbNCwyLCJcXEV4dF8xXlxcWlooQV8yLCBCXzMpIl0sWzIsNCwiXFxFeHRfMV5cXFpaKEFfMywgQl8yKSJdLFs0LDQsIlxcRXh0XzFeXFxaWihBXzMsIEJfMykiXV0=)

This equals the following:

\begin{tikzcd}
	{\Ext(\ZZ, \ZZ)} && {\Ext(\ZZ, \ZZ/4)} && {\Ext(\ZZ, \ZZ/5)} \\
	\\
	{\Ext(\ZZ/2, \ZZ)} && {\Ext(\ZZ/2, \ZZ/4)} && {\Ext(\ZZ/2, \ZZ/5)} \\
	\\
	{\Ext(\ZZ/3, \ZZ)} && {\Ext(\ZZ/3, \ZZ/4)} && {\Ext(\ZZ/3, \ZZ/5)}
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsOSxbMCwwLCJcXEV4dF8xXlxcWlooQV8xLCBCXzEpIl0sWzAsMiwiXFxFeHRfMV5cXFpaKEFfMiwgQl8xKSJdLFswLDQsIlxcRXh0XzFeXFxaWihBXzMsIEJfMSkiXSxbMiwwLCJcXEV4dF8xXlxcWlooQV8xLCBCXzIpIl0sWzQsMCwiXFxFeHRfMV5cXFpaKEFfMSwgQl8zKSJdLFsyLDIsIlxcRXh0XzFeXFxaWihBXzIsIEJfMikiXSxbNCwyLCJcXEV4dF8xXlxcWlooQV8yLCBCXzMpIl0sWzIsNCwiXFxFeHRfMV5cXFpaKEFfMywgQl8yKSJdLFs0LDQsIlxcRXh0XzFeXFxaWihBXzMsIEJfMykiXV0=)


Which simplifies to:

\begin{tikzcd}
	0 && 0 && 0 \\
	\\
	{\ZZ/2} && {\ZZ/2} && 0 \\
	\\
	{\ZZ/3} && {0} && {0}
\end{tikzcd}


> [Link to Diagram](https://q.uiver.app/?q=WzAsOSxbMCwwLCJcXEV4dF8xXlxcWlooQV8xLCBCXzEpIl0sWzAsMiwiXFxFeHRfMV5cXFpaKEFfMiwgQl8xKSJdLFswLDQsIlxcRXh0XzFeXFxaWihBXzMsIEJfMSkiXSxbMiwwLCJcXEV4dF8xXlxcWlooQV8xLCBCXzIpIl0sWzQsMCwiXFxFeHRfMV5cXFpaKEFfMSwgQl8zKSJdLFsyLDIsIlxcRXh0XzFeXFxaWihBXzIsIEJfMikiXSxbNCwyLCJcXEV4dF8xXlxcWlooQV8yLCBCXzMpIl0sWzIsNCwiXFxFeHRfMV5cXFpaKEFfMywgQl8yKSJdLFs0LDQsIlxcRXh0XzFeXFxaWihBXzMsIEJfMykiXV0=)

So the answer is $\ZZ/2 \oplus \ZZ/2 \oplus \ZZ/3 \cong \ZZ/2 \oplus \ZZ/6$. 

[^fix_facts_on_ext_oskar]: 
Thanks to Oskar Henriksson for some fixes/clarifications and further explanations here!

:::


## 7 

Show there is no homeomorphism $\CP^2 \mapsvia{f} \CP^2$ such that $f(\CP^1)$ is disjoint from $\CP_1 \subset \CP_2$.

:::{.solution}

\envlist
:::{.concept}
\envlist

1. Every homeomorphism induces isomorphisms on homotopy/homology/cohomology.
2. $H^*(\CP^2) = \ZZ[\alpha] / (\alpha^2)$ where $\deg \alpha = 2$.
3. $[f(X)] = f_*([X])$
4. $a\capprod b = 0 \implies a=0~\text{or}~b=0$ (nondegeneracy).

:::

Supposing such a homeomorphism exists, we would have $[\CP^1] \capprod [f(\CP^1)] = 0$ by the definition of these submanifolds being disjoint.
But $[\CP^1]\capprod[f(\CP^1)] = [\CP^1]\capprod f_*([\CP^1])$, where
\[
f_*: H^*(\CP^2) \to H^*(\CP^2)
\]
is the induced map on cohomology.
Since the intersection pairing is nondegenerate, either $[\CP^1] = 0$ or $f_*([\CP^1]) = 0$.
We know that $H^*(\CP^2) = \ZZ[\alpha] / \alpha^2$ where $\alpha = [\CP^1]$, however, so this forces $f_*([\CP^1]) = 0$. But since this was a generator of $H^*$, we have $f_*(H^*(\CP^2)) = 0$, so $f$ is not an isomorphism on cohomology. 

:::

## 8 

Describe the universal cover of $X = (S^1 \cross S^1) \vee S^2$ and compute $\pi_2(X)$.

:::{.solution}

\envlist
:::{.concept}
\envlist

- $\pi_{\geq 2}(\univcover{X} ) \cong \pi_{\geq 2}(X)$ for $\univcover{X}$ the universal cover of $X$
- Structure of the universal cover of a wedges
- $\univcover{T^2} = \RR^2$ and $\univcover{S^2} = S^2$
- By Mayer-Vietoris, $H_n(\Vee X_i) = \bigoplus H_n(X_i)$.
:::

The universal cover can be identified as
\[
\univcover{X} = \RR^2 \Vee_{i, j \in \ZZ^2} S^2
,\]
i.e. the plane with a sphere wedged onto every integer lattice point.
We can then check
\[
\pi_1(X) 
&\cong \pi_1(\univcover{X} ) \\
&= \pi_1( \RR^2 \Vee_{i, j \in \ZZ^2} S^2 ) \\
&= \pi_1( \RR^2 \Vee_{i, j \in \ZZ^2} S^2 ) \\
&= \prod_{i,j \in \ZZ^2} \pi_1(\RR^2) \cross \pi_1(S^2) \\
&= 0
,\]
using that $\pi_1(S^2) = 0$.
Then by Hurewicz, $\pi_2(X) \cong H_2(X)$, so we can compute
\[
H_2(X) 
&= H_2( \RR^2 \Vee_{i, j \in \ZZ^2} S^2 ) \\
&= \bigoplus_{i,j \in \ZZ^2} H_2(\RR^2) \oplus H_2(S^2) \\
&= \bigoplus_{i,j \in \ZZ^2} \ZZ
.\]

:::

## 9

Let $S^3 \to E \to S^5$ be a fiber bundle and compute $H_3(E)$.

:::{.solution title="Using the LES in Homotopy"}

\envlist
:::{.concept}
\envlist

- Homotopy LES: $F\to E\to B \leadsto \pi_*F() \to \pi_*(E) \to \pi_*(B)$.
- Hurewicz: $\pi_{\leq n}(X) = 0, \pi_n(X) \neq 0 \implies \pi_n(X) \cong H_n(X)$.
- $0\to A\to B \to 0$ exact iff $A\cong B$
:::

From the LES in homotopy we have

\begin{tikzcd}
	{\pi_4(S^3)} && {\pi_4(E)} && {\pi_4(S^5)} \\
	\\
	{\pi_3(S^3)} && {\pi_3(E)} && {\pi_3(S^5)} \\
	\\
	{\pi_2(S^3)} && {\pi_2(E)} & {} & {\pi_2(S^5)} \\
	\\
	{\pi_1(S^3)} && {\pi_1(E)} && {\pi_1(S^5)} \\
	\\
	{\pi_0(S^3)} && {\pi_0(E)} && {\pi_0(S^5)}
	\arrow[from=1-1, to=1-3]
	\arrow[from=1-3, to=1-5]
	\arrow[from=1-5, to=3-1, in=180, out=360]
	\arrow[from=3-1, to=3-3]
	\arrow[from=3-3, to=3-5]
	\arrow[from=3-5, to=5-1, in=180, out=360]
	\arrow[from=5-1, to=5-3]
	\arrow[from=5-3, to=5-5]
	\arrow[from=5-5, to=7-1, in=180, out=360]
	\arrow[from=7-1, to=7-3]
	\arrow[from=7-3, to=7-5]
	\arrow[from=7-5, to=9-1, in=180, out=360]
	\arrow[from=9-1, to=9-3]
	\arrow[from=9-3, to=9-5]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsMTYsWzAsMCwiXFxwaV80KFNeMykiXSxbMiwwLCJcXHBpXzQoRSkiXSxbNCwwLCJcXHBpXzQoU141KSJdLFswLDIsIlxccGlfMyhTXjMpIl0sWzIsMiwiXFxwaV8zKEUpIl0sWzQsMiwiXFxwaV8zKFNeNSkiXSxbMyw0XSxbMCw0LCJcXHBpXzIoU14zKSJdLFswLDYsIlxccGlfMShTXjMpIl0sWzAsOCwiXFxwaV8wKFNeMykiXSxbMiw0LCJcXHBpXzIoRSkiXSxbNCw0LCJcXHBpXzIoU141KSJdLFsyLDYsIlxccGlfMShFKSJdLFs0LDYsIlxccGlfMShTXjUpIl0sWzIsOCwiXFxwaV8wKEUpIl0sWzQsOCwiXFxwaV8wKFNeNSkiXSxbMCwxXSxbMSwyXSxbMiwzXSxbMyw0XSxbNCw1XSxbNSw3XSxbNywxMF0sWzEwLDExXSxbMTEsOF0sWzgsMTJdLFsxMiwxM10sWzEzLDldLFs5LDE0XSxbMTQsMTVdXQ==)

and plugging in known information yields

\begin{tikzcd}
	{\pi_4(S^3)} && {\pi_4(E)} && 0 \\
	\\
	\textcolor{rgb,255:red,92;green,92;blue,214}{\ZZ} && \textcolor{rgb,255:red,92;green,92;blue,214}{\pi_3(E)} && 0 \\
	\\
	0 && \textcolor{rgb,255:red,214;green,92;blue,92}{\pi_2(E) = 0} & {} & 0 \\
	\\
	0 && \textcolor{rgb,255:red,214;green,92;blue,92}{\pi_1(E)=0} && 0 \\
	\\
	\ZZ && {\pi_0(E)} && \ZZ
	\arrow[from=1-1, to=1-3]
	\arrow[from=1-3, to=1-5]
	\arrow[from=1-5, to=3-1, in=180, out=360]
	\arrow["\sim", color={rgb,255:red,92;green,92;blue,214}, hook, two heads, from=3-1, to=3-3]
	\arrow[no head, from=3-3, to=3-5]
	\arrow[from=3-5, to=5-1, in=180, out=360]
	\arrow[from=5-1, to=5-3]
	\arrow[from=5-3, to=5-5]
	\arrow[from=5-5, to=7-1, in=180, out=360]
	\arrow[from=7-1, to=7-3]
	\arrow[from=7-3, to=7-5]
	\arrow[from=7-5, to=9-1, in=180, out=360]
	\arrow[hook, from=9-1, to=9-3]
	\arrow[two heads, from=9-3, to=9-5]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsMTYsWzAsMCwiXFxwaV80KFNeMykiXSxbMiwwLCJcXHBpXzQoRSkiXSxbNCwwLCIwIl0sWzAsMiwiXFxaWiIsWzI0MCw2MCw2MCwxXV0sWzIsMiwiXFxwaV8zKEUpIixbMjQwLDYwLDYwLDFdXSxbNCwyLCIwIl0sWzMsNF0sWzAsNCwiMCJdLFswLDYsIjAiXSxbMCw4LCJcXFpaIl0sWzIsNCwiXFxwaV8yKEUpID0gMCIsWzAsNjAsNjAsMV1dLFs0LDQsIjAiXSxbMiw2LCJcXHBpXzEoRSk9MCIsWzAsNjAsNjAsMV1dLFs0LDYsIjAiXSxbMiw4LCJcXHBpXzAoRSkiXSxbNCw4LCJcXFpaIl0sWzAsMV0sWzEsMl0sWzIsM10sWzMsNCwiXFxjb25nIiwxLHsiY29sb3VyIjpbMjQwLDYwLDYwXSwic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoiaG9vayIsInNpZGUiOiJ0b3AifSwiaGVhZCI6eyJuYW1lIjoiZXBpIn19fSxbMjQwLDYwLDYwLDFdXSxbNCw1LCIiLDAseyJzdHlsZSI6eyJoZWFkIjp7Im5hbWUiOiJub25lIn19fV0sWzUsN10sWzcsMTBdLFsxMCwxMV0sWzExLDhdLFs4LDEyXSxbMTIsMTNdLFsxMyw5XSxbOSwxNCwiIiwwLHsic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoiaG9vayIsInNpZGUiOiJ0b3AifX19XSxbMTQsMTUsIiIsMCx7InN0eWxlIjp7ImhlYWQiOnsibmFtZSI6ImVwaSJ9fX1dXQ==)

where

- Rows 3 and 4 force $\pi_3(E) \cong \ZZ$, 
- Rows 0 and 1 force $\pi_0(E) = \ZZ$ (todo: not clear if this is true... is it even needed here?)
- The remaining rows force $\pi_1(E) = \pi_2(E) = 0$.

By Hurewicz, we thus have $H_3(E) = \pi_3(E) = \ZZ$. 
:::


:::{.solution title="Using the Serre spectral sequence"}

\todo[inline]{Four-corner spectral sequences, only homology in degrees 1,3,5,8. No differentials hit anything!}

:::

