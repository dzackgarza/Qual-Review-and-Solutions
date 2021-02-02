# Summer 2003

## 1 

Describe all possible covering maps between $S^2, T^2, K$

:::{.solution}
Useful facts:

1. $\tilde X \surjects X$ induces $\pi_1(\tilde X) \injects \pi_1(X)$
2. $\chi(\tilde X) = n \chi (X)$
3. $\pi_n(X) = [S^n, X]$
4. $Y \to X$ with $\pi_1(Y) = 0$ and $\tilde X \homotopic \pt \implies$ every $Y\mapsvia{f} X$ is nullhomotopic.
5. $\pi_*(T^2) = [\ZZ \ast \ZZ, 0\rightarrow]$
6. $\pi_*(K) = [\ZZ \semidirect_{\ZZ_2} \ZZ, 0\rightarrow]$
7. Universal covers are homeomorphic.
8. $\pi_{\geq 2}(\tilde X) \cong \pi_{\geq 2}(X)$

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

:::

## 2

Show that $\ZZ^{\ast 2}$ has subgroups isomorphic to $\ZZ^{\ast n}$ for every $n$.

:::{.solution}
Facts Used

1. $\pi_1(\bigvee^k S^1) = \ZZ^{\ast k}$
2. $\tilde X \surjects X \implies \pi_1(\tilde X) \injects \pi_1(X)$
3. Every subgroup $G \leq \pi_1(X)$ corresponds to a covering space $X_G \surjects X$
4. $A \subseteq B \implies F(A) \leq F(B)$ for free groups.

It is easier to prove the stronger claim that $\ZZ^\NN \leq \ZZ^{\ast 2}$ (i.e. the free group on countably many generators) and use fact 4 above.

Just take the covering space $\tilde X \surjects S^1 \vee S^1$ defined via the gluing map $\RR \union_{\ZZ} S^1$ which attaches a circle to each integer point, taking 0 as the base point. Then let $a$ denote a translation and $b$ denote traversing a circle, so we have $\pi_1(\tilde X) = \left<\union_{n\in\ZZ}a^nba^{-n}\right>$ which is a free group on countably many generators. Since $\tilde X$ is a covering space, $\pi_1(\tilde X) \injects \pi_1(S^1 \vee S^1) = \ZZ^{\ast 2}$. By 4, we can restrict this to $n$ generators for any $n$ to get a subgroup, and $A\leq B \leq C \implies A \leq C$ as groups.


:::


## 3

Construct a space having $H_*(X) = [\ZZ, 0, 0, 0, 0, \ZZ_4, 0\rightarrow]$.

:::{.solution}
Facts used:

- Construction of Moore Spaces
- $\tilde H_n(\Sigma X) = \tilde H_{n-1}(X)$, using $\Sigma X = C_X \union_X C_X$ and Mayer-Vietoris.

Take $X = e^0 \union_{\Phi_1} e^5 \union_{\Phi_2} e^6$, where
\begin{align*}
\Phi_1: \del B^5 = S^4 \mapsvia{z~\mapsto z^0} e^0 \\
\Phi_2: \del B^6 = S^5 \mapsvia{z~\mapsto z^4} e^5
.\end{align*}

where $\deg \Phi_2 = 4$.

:::


## 4 

Compute the complement of a knotted solid torus in $S^3$.

:::{.solution}
Facts used:

- $H_*(T^2) = [\ZZ, \ZZ^2, \ZZ, 0\rightarrow]$
- $N^{(1)} \homotopic S^1$, so $H_{\geq 2}(N) = 0$.
- A SES $0\to A\to B \to F \to 0$ with $F$ free splits.
- $0\to A \to B \mapsvia{\cong} C \to D \to 0$ implies $A = D = 0$.

Let $N$ be the knotted solid torus, so that $\del N = T^2$, and let $X = S^3 - N$. Then

- $S^3 = N \union_{T^2} X$
- $N \cap X = T^2$


and we apply Mayer-Vietoris to $S^3$:

\begin{align*}
4\qquad H_4(T^2) \to H_4(N) \times H_4(X) \to H_4(S^3) \\
3\qquad H_3(T^2) \to H_3(N) \times H_3(X) \to H_3(S^3) \\
2\qquad H_2(T^2) \to H_2(N) \times H_2(X) \to H_2(S^3) \\
1\qquad H_1(T^2) \to H_1(N) \times H_1(X) \to H_1(S^3) \\
0\qquad H_0(T^2) \to H_0(N) \times H_0(X) \to H_0(S^3) \\
.\end{align*}

where we can plug in known information and deduce some maps:

\begin{align}
4\qquad &0 \to &0 \qquad\to &0 \mapsvia{\del_4} \\
3\qquad &0 \to &H_3(X) \qquad\to &\ZZ \mapsvia{\del_3}\\
2\qquad &\ZZ \to &H_2(X) \qquad\to &0 \mapsvia{\del_2}\\
1\qquad &\ZZ^2 \cong &\ZZ \times H_1(X) \qquad\to &0 \mapsvia{\del_1}\\
0\qquad &\ZZ \to &\ZZ \times H_0(X) \qquad\to &\ZZ \to 0 \\
\end{align}


We then deduce:
- $H_0(X) = \ZZ$ by the splitting of the line 0 SES 
  $$
  0 \to \ZZ \to \ZZ \cross H_0(X) \to \ZZ \to 0
  $$ 
  yielding $Z\cross H_0(X) \cong \ZZ \times \ZZ$.
- $H_1(X) = \ZZ$ by the line 1 SES 
  $$
  0 \to \ZZ^2 \to \ZZ \cross H_1(X) \to 0
  $$ 
  which yields an isomorphism.
- $H_2(X) = H_3(X) = 0$ by examining the SES spanning lines 3 and 2: 
  $$
  0 \injects H_3(X) \injects \ZZ \mapsvia{\cong_{\del_3}} \ZZ \surjects H_2(X) \surjects 0
  $$
 	Since $\del_3$ must be an isomorphism, this forces the edge terms to be zero.


:::

## 5 

Compute the homology and cohomology of a closed, connected, oriented 3-manifold $M$ with $\pi_1(M) = \ZZ^{\ast 2}$.

:::{.solution}
Facts used:

- $M$ closed, connected, oriented $\implies H_i(M)\cong H^{n-i}(M)$
- $H_1(X) = \pi_1(X) / [\pi_1(X), \pi_1(X)]$
- For orientable manifolds $H_n(M^n) = \ZZ$

**Homology**

- Since $M$ is connected, $H_0 = \ZZ$
- Since $\pi_1(M) = \ZZ^{\ast 2}$, $H_1$ is the abelianization and $H_1(X) = \ZZ^2$
- Since $M$ is closed/connected/oriented, Poincaré Duality holds and $H_2 = H^{3-2} = H^1 = \mathbf{F} H_1 + \mathbf{T}H_0$ by UCT. Since $H_0=\ZZ$ is torsion-free, we have $H_2(M) = H_1(M) =  \ZZ^2$.
- Since $M$ is an orientable manifold, $H_3(M) = \ZZ$
- So $H_*(M) = [\ZZ, \ZZ^2, \ZZ^2, \ZZ, 0\rightarrow]$

**Cohomology**

- By Poincaré Duality, $H^*(M) = \widehat{H_*(M)} = [\ZZ, \ZZ^2, \ZZ^2, \ZZ, 0\rightarrow]$. (Where the hat denotes reversing the list.)


:::


## 6

Compute $\ext(\ZZ \oplus \ZZ/2 \oplus  \ZZ/3, \ZZ \oplus  \ZZ/4 \oplus  \ZZ/5)$

:::{.solution}
Facts Used:
[^fix_facts_on_ext_oskar]

1. $\ext(\ZZ, \ZZ/m) = 0$ since $\ZZ$ is a free $\ZZ\dash$module.
2. $\ext(\ZZ/n, \ZZ) = \ZZ/n$ using the usual projective resolution $0 \to \ZZ \to \ZZ \to \ZZ/n \to 0$
3. Contravariant Hom takes coproducts to products:
\[
\ext(\bigoplus_{i\in I} A_i, \prod_{k\in K} B_k) = \prod_{i\in I} \prod_{k\in K} \ext(A_i, B_k)
.\]

Write 
\[
A_* &\da A_1 \oplus A_2 \oplus A_3 \da \ZZ \oplus  \ZZ/2 \oplus  \ZZ/3 \\
B_* &\da B_1 \oplus B_2 \oplus B_3 \da \ZZ \oplus \ZZ/4 \oplus  \ZZ/5
.\]


Break it up into a bigraded complex, take Ext of the pieces, and sum over the complex:

$\ext(\downarrow, \rightarrow)$ | $\ZZ$   | $\ZZ_4$ | $\ZZ_5$
--------------------------------|---------|---------|--------
$\ZZ$                           | 0       | 0       | 0
$\ZZ_2$                         | $\ZZ_2$ | $\ZZ_2$ | 0
$\ZZ_3$                         | $\ZZ_3$ | 0       | 0

So the answer is $\ZZ_2 \times \ZZ_2 \times \ZZ_3 = \ZZ_{12}$. 

[^fix_facts_on_ext_oskar]: 
Thanks to Oskar Henriksson for some fixes/clarifications and further explanations here!

:::


## 7 

Show there is no homeomorphism $\CP^2\selfmap_f$ such that $f(\CP^1)$ is disjoint from $\CP_1 \subset \CP_2$.

:::{.solution}
Facts used:

1. Every homeomorphism induces isomorphisms on homotopy/homology/cohomology.
2. $H^*(\CP^2) = \ZZ[\alpha] / (\alpha^2)$ where $\deg \alpha = 2$.
3. $[f(X)] = f_*([X])$
4. $a\dot{} b = 0 \implies a=0~\text{or}~b=0$ (nondegeneracy).

Supposing such a homeomorphism exists, we would have $[\CP^1] \dot{} [f(\CP^1)] = 0$ by the definition of these submanifolds being disjoint.

But $[\CP^1]\dot{}[f(\CP^1)] = [\CP^1]\dot{} f_*([\CP^1])$, where
$$
f_*: H^*(\CP^2) \to H^*(\CP^2)
$$
is the induced map on cohomology.

Since the intersection pairing is nondegenerate, either $[\CP^1] = 0$ or $f_*([\CP^1]) = 0$.

We know that $H^*(\CP^2) = \ZZ[\alpha] / \alpha^2$ where $\alpha = [\CP^1]$, however, so this forces $f_*([\CP^1]) = 0$. But since this was a generator of $H^*$, we have $f_*(H^*(\CP^2)) = 0$, so $f$ is not an isomorphism on cohomology. 


:::

## 8 

Describe the universal cover of $X = (S^1 \cross S^1) \vee S^2$ and compute $\pi_2(X)$.

:::{.solution}
Facts used:

- $\pi_{\geq 2}(\tilde X) \cong \pi_{\geq 2}(X)$
- Structure of the universal cover of a wedge product
- $\RR^2 \surjects_p T^2 = S^1 \cross S^1$

$\tilde X = \RR^2 \union_{\ZZ^2} S^2$, so $\pi_2(X) \cong \pi_2(\tilde X) = \prod_{i,j \in \ZZ^2} \ZZ = \ZZ^{\ZZ^2} = \ZZ^{\aleph_0}$.

:::

## 9

Let $S^3 \to E \to S^5$ be a fiber bundle and compute $H_3(E)$.

:::{.solution}
Facts used:

- Homotopy LES
- Hurewicz
- $0\to A\to B \to 0$ exact iff $A\cong B$

From the LES in homotopy we have

% https://q.uiver.app/?q=WzAsMTYsWzAsMCwiXFxwaV80KFNeMykiXSxbMiwwLCJcXHBpXzQoRSkiXSxbNCwwLCJcXHBpXzQoU141KSJdLFswLDIsIlxccGlfMyhTXjMpIl0sWzIsMiwiXFxwaV8zKEUpIl0sWzQsMiwiXFxwaV8zKFNeNSkiXSxbMyw0XSxbMCw0LCJcXHBpXzIoU14zKSJdLFswLDYsIlxccGlfMShTXjMpIl0sWzAsOCwiXFxwaV8wKFNeMykiXSxbMiw0LCJcXHBpXzIoRSkiXSxbNCw0LCJcXHBpXzIoU141KSJdLFsyLDYsIlxccGlfMShFKSJdLFs0LDYsIlxccGlfMShTXjUpIl0sWzIsOCwiXFxwaV8wKEUpIl0sWzQsOCwiXFxwaV8wKFNeNSkiXSxbMCwxXSxbMSwyXSxbMiwzXSxbMyw0XSxbNCw1XSxbNSw3XSxbNywxMF0sWzEwLDExXSxbMTEsOF0sWzgsMTJdLFsxMiwxM10sWzEzLDldLFs5LDE0XSxbMTQsMTVdXQ==
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


and plugging in known information yields

% https://q.uiver.app/?q=WzAsMTYsWzAsMCwiXFxwaV80KFNeMykiXSxbMiwwLCJcXHBpXzQoRSkiXSxbNCwwLCIwIl0sWzAsMiwiXFxaWiIsWzI0MCw2MCw2MCwxXV0sWzIsMiwiXFxwaV8zKEUpIixbMjQwLDYwLDYwLDFdXSxbNCwyLCIwIl0sWzMsNF0sWzAsNCwiMCJdLFswLDYsIjAiXSxbMCw4LCJcXFpaIl0sWzIsNCwiXFxwaV8yKEUpID0gMCIsWzAsNjAsNjAsMV1dLFs0LDQsIjAiXSxbMiw2LCJcXHBpXzEoRSk9MCIsWzAsNjAsNjAsMV1dLFs0LDYsIjAiXSxbMiw4LCJcXHBpXzAoRSkiXSxbNCw4LCJcXFpaIl0sWzAsMV0sWzEsMl0sWzIsM10sWzMsNCwiXFxjb25nIiwxLHsiY29sb3VyIjpbMjQwLDYwLDYwXSwic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoiaG9vayIsInNpZGUiOiJ0b3AifSwiaGVhZCI6eyJuYW1lIjoiZXBpIn19fSxbMjQwLDYwLDYwLDFdXSxbNCw1LCIiLDAseyJzdHlsZSI6eyJoZWFkIjp7Im5hbWUiOiJub25lIn19fV0sWzUsN10sWzcsMTBdLFsxMCwxMV0sWzExLDhdLFs4LDEyXSxbMTIsMTNdLFsxMyw5XSxbOSwxNCwiIiwwLHsic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoiaG9vayIsInNpZGUiOiJ0b3AifX19XSxbMTQsMTUsIiIsMCx7InN0eWxlIjp7ImhlYWQiOnsibmFtZSI6ImVwaSJ9fX1dXQ==
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

where

- Rows 3 and 4 force $\pi_3(E) \cong \ZZ$, 
- Rows 0 and 1 force $\pi_0(E) = \ZZ$ (todo: not clear if this is true... is it even needed here?)
- The remaining rows force $\pi_1(E) = \pi_2(E) = 0$.

By Hurewicz, we thus have $H_3(E) = \pi_3(E) = \ZZ$. 

  
:::
