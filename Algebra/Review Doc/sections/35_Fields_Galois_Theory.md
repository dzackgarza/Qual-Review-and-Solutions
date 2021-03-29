# Galois Theory

:::{.proposition}
If $\ch k = 0$ or $k$ is finite, then every *algebraic* extension $L/k$ is separable.
:::

:::{.proposition}
If $L/k$ is algebraic, then $\Aut(L/k)$ permutes the roots of irreducible polynomials.
:::

:::{.proposition}
$\abs{\aut(L/k)} \leq [L: k]$ with equality precisely when $L/k$ is normal.
:::


:::{.theorem title="Dirichlet's Theorem on Arithmetic Progressions"}
\todo[inline]{todo}

:::


:::{.definition title="Constructible"}
\todo[inline]{todo}

:::


:::{.theorem title="Constructibility of Regular $n\dash$gons"}

:::



### Lemmas About Towers

Let $L/F/k$ be a finite tower of field extensions.


:::{.proposition title="Towers are multiplicative in degree"}
\[
[L : k] = [L: F][F: k]
.\]
:::

:::{.proposition title="Normal/Algebraic/Galois in towers"}
$L/k$ normal/algebraic/Galois $\implies L/F$ normal/algebraic/Galois.
:::

:::{.proof title="for normality"}
$\min(\alpha, F) \divides \min(\alpha, k)$, so if the latter splits in $L$ then so does the former.
:::

:::{.corollary title="?"}
$\alpha \in L$ algebraic over $k \implies \alpha$ algebraic over $F$.
:::

:::{.corollary title="?"}
$E_1/k$ normal and $E_2/k$ normal $\implies E_1E_2/k$ normal and $E_1 \intersect E_2 / k$ normal.



\begin{tikzcd}
	&& {E_1 E_2} \\
	\\
	{E_1} &&&& {E_2} \\
	&& {E_1 \cap E_2} \\
	\\
	\\
	&& {k}
	\arrow["{\text{normal}}", from=3-5, to=7-3]
	\arrow[from=4-3, to=7-3, dashed, no head, "\text{normal}", near start]
	\arrow["{\text{normal}}"', from=3-1, to=7-3]
	\arrow[from=1-3, to=3-1, no head]
	\arrow[from=1-3, to=3-5, no head]
	\arrow[from=1-3, to=4-3, no head]
	\arrow[from=1-3, to=7-3, curve={height=25pt}, dashed, no head, "\text{normal}"', near start]
	\arrow[from=3-1, to=4-3, no head]
	\arrow[from=4-3, to=3-5, no head]
\end{tikzcd}

> [Link to diagram](https://q.uiver.app/?q=WzAsNSxbMiwwLCJFXzEgRV8yIl0sWzAsMiwiRV8xIl0sWzQsMiwiRV8yIl0sWzIsMywiRV8xIFxcY2FwIEVfMiJdLFsyLDYsImsiXSxbMiw0LCJcXHRleHR7bm9ybWFsfSJdLFszLDQsIiIsMix7InN0eWxlIjp7ImJvZHkiOnsibmFtZSI6ImRhc2hlZCJ9LCJoZWFkIjp7Im5hbWUiOiJub25lIn19fV0sWzEsNCwiXFx0ZXh0e25vcm1hbH0iLDJdLFswLDEsIiIsMSx7InN0eWxlIjp7ImhlYWQiOnsibmFtZSI6Im5vbmUifX19XSxbMCwyLCIiLDEseyJzdHlsZSI6eyJoZWFkIjp7Im5hbWUiOiJub25lIn19fV0sWzAsMywiIiwxLHsic3R5bGUiOnsiaGVhZCI6eyJuYW1lIjoibm9uZSJ9fX1dLFswLDQsIiIsMSx7ImN1cnZlIjozLCJzdHlsZSI6eyJib2R5Ijp7Im5hbWUiOiJkYXNoZWQifSwiaGVhZCI6eyJuYW1lIjoibm9uZSJ9fX1dLFsxLDMsIiIsMSx7InN0eWxlIjp7ImhlYWQiOnsibmFtZSI6Im5vbmUifX19XSxbMywyLCIiLDEseyJzdHlsZSI6eyJoZWFkIjp7Im5hbWUiOiJub25lIn19fV1d)

:::

:::{.proposition title="Algebraicity is transitive"}
$F/k$ algebraic and $L/F$ algebraic $\implies L/k$ algebraic.
\begin{tikzcd}
L \arrow[d, bend right=49, "\text{alg}"'] 
  \arrow[dd, dashed, bend left=49, "\text{alg}"] \\
F \arrow[d, bend right=49, "\text{alg}"']                                  \\
k
\end{tikzcd}
:::

:::{.proposition title="Separability is transitive"}
For $L/F/k$, then $L/k$ is separable \( \iff L/F,\, F/k \) are separable.
\begin{tikzcd}
L \arrow[d, bend right=49, "\text{sep}"'] 
  \arrow[dd, dashed, bend left=49, "\text{sep}"] \\
F \arrow[d, bend right=49, "\text{sep}"']                                  \\
k
\end{tikzcd}

:::

:::{.warnings}
Being Galois is **not** transitive.
Take \( \QQ\qty{ \sqrt[4]{2} } / \QQ\qty{ \sqrt{2} } / \QQ \).
:::

:::{.proposition title="?"}
If $L/k$ is algebraic, then $F/k$ separable:


\begin{tikzcd}
	{L} \\
	\\
	{F} \\
	\\
	{k}
	\arrow["{\text{algebraic}}", from=1-1, to=5-1, curve={height=-18pt}, no head]
	\arrow["{\text{separable}}", from=5-1, to=3-1, curve={height=-12pt}, dashed, no head]
\end{tikzcd}
> [Link to diagram](https://q.uiver.app/?q=WzAsMyxbMCwwLCJMIl0sWzAsMiwiRiJdLFswLDQsImsiXSxbMCwyLCJcXHRleHR7YWxnZWJyYWljfSIsMCx7ImN1cnZlIjotMywic3R5bGUiOnsiaGVhZCI6eyJuYW1lIjoibm9uZSJ9fX1dLFsyLDEsIlxcdGV4dHtzZXBhcmFibGV9IiwwLHsiY3VydmUiOi0yLCJzdHlsZSI6eyJib2R5Ijp7Im5hbWUiOiJkYXNoZWQifSwiaGVhZCI6eyJuYW1lIjoibm9uZSJ9fX1dXQ==)

Moreover, $L/F$ is additionally separable $\iff L/k$ separable:

\begin{tikzcd}
	{L} \\
	\\
	{F} \\
	\\
	{k}
	\arrow["\substack{\text{algebraic,} \\ \text{separable}}", from=1-1, to=5-1, curve={height=-18pt}, no head]
	\arrow["{\text{sep}}", from=5-1, to=3-1, curve={height=-12pt}, dashed, no head]
	\arrow["{\text{separable}}"', from=1-1, to=3-1, curve={height=12pt}, dashed, no head]
\end{tikzcd}
> [Link to diagram](https://q.uiver.app/?q=WzAsMyxbMCwwLCJMIl0sWzAsMiwiRiJdLFswLDQsImsiXSxbMCwyLCJcXHRleHR7YWxnZWJyYWljfSBcXFxcIFxcdGV4dHtzZXBhcmFibGV9IiwwLHsiY3VydmUiOi0zLCJzdHlsZSI6eyJoZWFkIjp7Im5hbWUiOiJub25lIn19fV0sWzIsMSwiXFx0ZXh0e3NlcH0iLDAseyJjdXJ2ZSI6LTIsInN0eWxlIjp7ImJvZHkiOnsibmFtZSI6ImRhc2hlZCJ9LCJoZWFkIjp7Im5hbWUiOiJub25lIn19fV0sWzAsMSwiXFx0ZXh0e3NlcGFyYWJsZX0iLDIseyJjdXJ2ZSI6Miwic3R5bGUiOnsiYm9keSI6eyJuYW1lIjoiZGFzaGVkIn0sImhlYWQiOnsibmFtZSI6Im5vbmUifX19XV0=)

:::

:::{.proposition title="?"}
If $L/k$ is Galois, then $L/F$ is **always** Galois.
Moreover, $F/k$ is Galois if and only if \( \Gal(L/F) \normal \Gal(L/k) \)

\begin{tikzcd}
	{L} \\
	\\
	{F} \\
	\\
	{k}
	\arrow["{\text{Galois}}", from=1-1, to=5-1, curve={height=-18pt}, no head]
	\arrow["{\text{Galois}}", from=5-1, to=3-1, curve={height=-12pt}, squiggly, no head]
	\arrow["{\text{Galois}}"', from=1-1, to=3-1, curve={height=12pt}, dashed, no head]
\end{tikzcd}

> [Link to diagram](https://q.uiver.app/?q=WzAsMyxbMCwwLCJMIl0sWzAsMiwiRiJdLFswLDQsImsiXSxbMCwyLCJcXHRleHR7R2Fsb2lzfSIsMCx7ImN1cnZlIjotMywic3R5bGUiOnsiaGVhZCI6eyJuYW1lIjoibm9uZSJ9fX1dLFsyLDEsIlxcdGV4dHtHYWxvaXN9IiwwLHsiY3VydmUiOi0yLCJzdHlsZSI6eyJib2R5Ijp7Im5hbWUiOiJzcXVpZ2dseSJ9LCJoZWFkIjp7Im5hbWUiOiJub25lIn19fV0sWzAsMSwiXFx0ZXh0e0dhbG9pc30iLDIseyJjdXJ2ZSI6Miwic3R5bGUiOnsiYm9keSI6eyJuYW1lIjoiZGFzaGVkIn0sImhlYWQiOnsibmFtZSI6Im5vbmUifX19XV0=)

In this case, 
\[
\Gal(F/k) \cong \frac{\Gal(L/k)}{\Gal(L/F)}
.\]

:::

### Fundamental Theorem of Galois Theory

:::{.theorem title="Fundamental Theorem of Galois Theory"}
Let $L/k$ be a Galois extension, then there is a correspondence:
\[
\correspond{\text{Subgroups } H \leq \Gal(L/k)}
&\mapstofrom
\correspond{\text{Fields }  F \text{ such}\\ \text{that } L/F/k} \\
H &\rightarrow \correspond{E^H \definedas ~\text{The fixed field of $H$}} \\
\correspond{\Gal(L/F) \definedas \theset{ \sigma \in \Gal(L/k) \suchthat \sigma(F) = F}} &\leftarrow F
\]

- This is contravariant with respect to subgroups/subfields.

- $[F: k] = [G: H]$, so degrees of extensions over the base field correspond to indices of subgroups.

- $[K : F] = \abs{H}$

- $L/F$ is Galois and $Gal(K/F) = H$

- $F/k$ is Galois $\iff H$ is normal, and $\Gal(F/k) = \Gal(L/k)/H$.

- The compositum $F_1 F_2$ corresponds to $H_1 \intersect H_2$.

- The subfield $F_1 \intersect F_2$ corresponds to $H_1 H_2$.
:::

### Examples

:::{.example title="Cyclotomic Fields"}
$\Gal(\QQ(\zeta_n)/\QQ) \cong \ZZ/(n)\units$ and is generated by maps of the form $\zeta_n \mapsto \zeta_n^j$ where $(j, n) = 1$.
I.e., the following map is an isomorphism:
\[
\ZZ/(n)\units &\to \Gal(\QQ(\zeta_n), \QQ) \\
r \mod n &\mapsto (\phi_r: \zeta_n \mapsto \zeta_n^r )
\]
:::

:::{.example title="Finite Fields"}
$\Gal(\FF_{p^n}/\FF_p) \cong \ZZ/ \gens{ n }$, a cyclic group generated by powers of the Frobenius automorphism:
\[
\varphi_p: \FF_{p^n} \to \FF_{p^n} \\
x &\mapsto x^p
\]

> See D&F p.566 example 7.

:::


:::{.example title="Quadratic Fields"}
Every degree 2 extension $L/k$ is Galois, except possibly in characteristic 2: if \( \alpha\in L \sm k\) then \( \min_{\alpha}(x) \in L[x] \) must split in $L[x]$ since \( \alpha\in L \implies \min_{\alpha}(x) = (x- \alpha)g(x) \) which forces \( \deg(g) = 1 \).
So $L$ is a splitting field.
If $\ch(k) \neq 2$, then $\dd{}{x} \min_{ \alpha}(x) = 2x - \cdots \not\equiv 0$, making $L$ separable.
:::


:::{.proposition}
If $K$ is the splitting field of an irreducible polynomial of degree $n$, then $\Gal(K/\QQ) \leq S_n$ is a transitive subgroup.
:::

:::{.corollary}
$n$ divides the order $\abs{ \Gal(K/\QQ)}$.
:::

:::{.theorem title="Splitting + Perfect implies Galois"}
\hfill

- If $\ch k = 0$ or $k$ is finite, then $k$ is perfect.

- $k = \CC,\RR, \QQ, \FF_p$ are perfect, so any finite normal extension is Galois.

- Every splitting field of a polynomial over a perfect field is Galois.
:::

:::{.proposition title="Composite Extensions"}
If $F/k$ is finite and Galois and $L/k$ is arbitrary, then $FL/L$ is Galois and
\[
\Gal(FL/L) = \Gal(F / F\intersect L) \subset \Gal(F/k)
.\]
:::


### Counterexamples

:::{.example title="?"}
\envlist

- $\QQ(\zeta_3, 2^{1/3})$ is normal but $\QQ(2^{1/3})$ is not since the irreducible polynomial $x^3 - 2$ has only one root in it.
- $\QQ(2^{1/3})$ is not Galois since its automorphism group is too small (only of size 1 instead of 3?).
- $\QQ(2^{1/4})$ is not Galois since its automorphism group is too small (only of size 2 instead of 4).
  However, the intermediate extensions $\QQ(2^{1/4}) / \QQ(2^{1/2})$ and $\QQ(\sqrt 2) / \QQ$ are Galois since they are quadratic.
  Slogan: "Being Galois is not transitive in towers."
- A quadratic extension that is not Galois: $\SF(x^2 + y) \in \FF_2(y)[x]$, which factors as $(x - \sqrt{y})^2$, making the extension not separable.
:::




