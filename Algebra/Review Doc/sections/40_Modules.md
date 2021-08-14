# Modules

## Definitions and Basics

:::{.definition title="$R\dash$modules"}
Four properties:

- $r(x+y) = rx + ry$
- $(r+s)x = rs + sx$
- $(rs)x= r(s(x))$
- $1_Rx = x$

Note that $M$ is additionally an $R\dash$algebra if the multiplication map is $R\dash$bilinear and so given by $m: M^{\tensor_R 2}\to M$ satisfying
\[
r. m(a\tensor b) = m(r.a \tensor b) = m(a\tensor r.b) && \forall r\in R, a,b \in M
.\]

:::


:::{.proposition title="The one-step submodule test"}
$N\subseteq M$ is an $R\dash$submodule iff $N$ is nonempty and for every $r\in R$ and $x, y \in N$, we have $rx+y\in N$.
:::

:::{.definition title="Module Morphisms"}
A map $f: M\to N$ is a **morphism of modules** iff $f(rm + n) = rf(m) + f(n)$.
:::

:::{.proposition title="One-step module morphism test"}
A map $\phi: M\to N$ is a morphism in $\rmod$ iff
\[
\phi(r.x + y) = r.\phi(x) + \phi(y) \in N && \forall r\in R, x,y\in M
.\]
:::


:::{.remark}
Quotients of modules are easier to reason about additively, writing $M/N = \ts{x + N}$ as cosets.
Then $(x + N) + (y + N) = (x+y) + N$ and $(x+N)(y+N) = (xy) + N$.
:::

:::{.definition title="Simple modules"}
A module is **simple** iff it has no nontrivial proper submodules.
:::

:::{.definition title="Indecomposable modules"}
A module $M$ is **decomposable** iff it admits a direct sum decomposition $M \cong M_1 \oplus M_2$ with $M_1, M_2 \neq 0$.
An **indecomposable** module is defined in the obvious way.
:::

:::{.definition title="Cyclic modules"}
A module $M$ is **cyclic** if there exists a single generator $m\in M$ such that $M = mR \da \gens{ m }$.
:::

## Structure Theorems

:::{.proposition title="Isomorphism theorems"}
\[
M / \ker \phi &\cong \im \phi \\
{A+B \over B} &\cong {A\over A \intersect B} \\
{M/A \over B/A} &\cong {M\over B} \\
\correspond{
  \text{Submodules of } M \\ \text{containing }N
}
&\mapstofrom
\correspond{
  \text{Submodules of } M/N
}
\\
A &\mapstofrom A/N
.\]

Note that the lattice correspondence commutes with sums and intersections of submodules.

:::

:::{.proposition title="Recognizing direct sums"}
If $M_1, M_2 \leq M$ are submodules, then $M = M_1 \oplus M_2$ if the following conditions hold:

- $M_1 + M_2 = M$
- $M_1 \intersect M_2 = 0$
:::


## Exact Sequences

:::{.definition title="Exact Sequences"}
A sequence of \(R\dash\)module morphisms 
\[
0 \mapsvia{d_1} A \mapsvia{d_2} B \mapsvia{d_3} C \to 0
\]
is *exact* iff $\im d_i = \ker d_{i+1}$.
:::


:::{.remark}
Note that $C\cong B/d_1(A)$ always, but $B$ is not a direct sum of the outer terms unless the sequence splits.
:::


:::{.definition title="Split Exact Sequences"}
A short exact sequence 
\[
\xi: 0 \to A \mapsvia{d_1} B \mapsvia{d_2} C \to 0
\]
has a **right-splitting** iff there exists a map $s: C\to B$ such that $d_2 \circ s = \id_{C}$.
$\xi$ has a **left-splitting** iff there exists a map $t:B\to A$ such that $t \circ d_1 = \id_A$.
:::

:::{.proposition title="Equivalent conditions for splitting SESs"}
Let $\xi: 0 \to A \mapsvia{d_1} B \mapsvia{d_2}  C \to 0$ be a SES, then TFAE

- $\xi$ admits a right-splitting $s: C\to B$.
- $C$ is projective.
- $\xi$ admits a left-splitting $t: B\to A$.
- $A$ is injective.
- $\xi$ is isomorphic to a SES of the form $0\to A \to A \oplus C \to C \to 0$.

:::

:::{.proof title="?"}
Right-splitting implies direct sum:

- Use that $B \subset \ker d_2 + \im s$, writing $b = (b - sd_2(b) ) + sd_2(b)$ and noting
\[
d_2(b - sd_2(b)) = d_2(b) - d_2sd_2(b) = d_2(b) - d_2(b) = 0 
.\]
- Show $\ker d_2 \intersect \im s=0$, writing $b$ with $d_2(b) = 0$ and $b = s(c)$ for some $c$ yields
\[
0 = d_2(b) = d_2s(c) = \id_C(c) = c
.\]

:::

## Free and Projective Modules

:::{.definition title="Free Module"}
A **free** module $M$ is a module satisfying any of the following conditions:

- A universal property:
  There is a set \( \mathcal{B}  \) and a set map \( M \mapsvia{\iota} \mathcal{B}  \) such that every set map \( \mathcal{B} \mapsvia{N} \) lifts:

\begin{tikzcd}
	M \\
	\\
	{\mathcal{B}} && N
	\arrow["f", from=3-1, to=3-3]
	\arrow["{\tilde f}", dashed, from=1-1, to=3-3]
	\arrow["\iota", hook, from=3-1, to=1-1]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsMyxbMCwyLCJcXG1hdGhjYWx7Qn0iXSxbMCwwLCJNIl0sWzIsMiwiTiJdLFswLDIsImYiXSxbMSwyLCJcXHRpbGRlIGYiLDAseyJzdHlsZSI6eyJib2R5Ijp7Im5hbWUiOiJkYXNoZWQifX19XSxbMCwxLCJcXGlvdGEiLDAseyJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6InRvcCJ9fX1dXQ==)

- Existence of a basis:

  There is linearly independent (so $\sum r_i \beta_i = 0 \implies r_i = 0$) spanning set (so \( m\in M \implies m = \sum r_i \beta_i \) ) of the form \( \mathcal{B} \da \ts{ \beta_i }_{i\in I} \), 

- Direct sum decomposition:

  $M$ decomposes as $M \cong \bigoplus_{i\in I} \beta_i R$, a sum of cyclic submodules.

:::

:::{.example title="A non-free module"}
$\ZZ/6$ is a $\ZZ\dash$module that is *not* free, since the element \( [3] \) is a torsion element, where \( 2[3] = [6] = [0] \).
This uses the fact that free modules over a PID are torsionfree.
:::

:::{.definition title="Free rank"}
If a module $M$ is free, the **free rank** of $M$ is the cardinality of any basis.
:::

:::{.proposition title="?"}
Every free \(R\dash\)module admits a basis (spanning $R\dash$linearly independent set).
:::

:::{.definition title="Torsion and torsionfree"}
An element $m\in M$ is a **torsion element** if there exists a nonzero $r\in R$ such that $rm = 0_M$.
A module \( M \) is **torsion-free** if and only if for every \( x\in M \), \( mx = 0_M \implies m=0_M \), i.e. $M$ has no nonzero torsion elements.
Equivalently, defining $M_t \da \ts{ m\in M \st \exists r\in R, rm = 0_M }$ as the set of all torsion elements, $M$ is torsion free iff $M_t = 0$.
If $M_t = M$, we say $M$ is a **torsion module**.
:::

:::{.proposition title="Free implies torsionfree"}
For $R$ an integral domain, any finitely generated free \(R\dash\)module $M$ is torsionfree.
:::

:::{.proof title="that free implies torsionfree"}
\envlist

- If $M$ is finitely generated, write $M = \gens{X}$ with $X\da \ts{x_1, \cdots, x_m}$ and $\# X<\infty$ a finite generating set.
- Since $M$ is free, there is some maximal subset of generators $\mcb \da \ts{x_1, \cdots, x_n} \subseteq X$ where $n\leq m$ that is linearly independent.
- Consider $N\leq M$ defined by $\gens{\mcb}$; this is a basis for $N$ and makes $N$ free.
  The claim is now that $M\cong N$, so that any maximal linearly independent subset of generators is all of $X$.
- If $N \not\cong M$, set $\mcb^c \da X\sm \mcb = \ts{x_{n+1}, \cdots, x_m}$ to be all generators for $M$ that the basis $\mcb$ misses.
- Then $\mcb^c \union \ts{x_{j}}$ for any $n+1\leq j \leq m$ has a linear dependence, and $r_j x_j + \sum_{k=1}^n r_n x_n = 0$ for some $r_j\neq 0$ implies $r_j x_j = - \sum_{k=1}^n r_n x_n$.
- Let $r$ be the product of all of the scalars obtained this way, so $r = \prod_{k=n+1}^m r_j$, and consider the submodule $rX \leq N \leq M$.
  We get $rM \leq N \leq M$ since $X$ is a generating set for $M$, so it now suffices to show $rM \cong M$.
- Just define a map $\phi_r: M\surjects rM$ where $m\mapsto rm$, and note $\ker \phi_r =\ts{ m\in M \st rm = 0} = 0$ since $M$ is torsionfree.
  So $M = M/\ker \phi_r \cong rM$.
:::

:::{.example title="A torsionfree module that is not free"}
$\QQ \in \mods{\ZZ}$ is torsionfree, but not free as a \(\ZZ\dash\)module.
This follows because any two elements $a/b, p/q$ are in a single ideal, since taking $d\da \gcd(b, q)$ we have $1/a = 1/d + \cdots 1/d$ and similarly $p/q = 1/a + \cdots + 1/a$, so these are in \( \gens{ 1/d }  \).
So any basis has size one, which would mean $\QQ = \ts{ \pm 1/d, \pm 2/d, \cdots }$ which in particular doesn't include the average of the first two terms.
:::

:::{.definition title="Projective Modules"}
A module $P$ is **projective** iff it satisfies any of the following conditions:

- A universal property: for every surjective $N \mapsvia{g} M$ and $P \mapsvia{f} M$, the following lift exists:

\begin{tikzcd}
	&& P \\
	\\
	N && M && 0
	\arrow["g", two heads, from=3-1, to=3-3]
	\arrow[from=3-3, to=3-5]
	\arrow["f", from=1-3, to=3-3]
	\arrow["{\exists \tilde f}"', dashed, from=1-3, to=3-1]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsNCxbMiwwLCJQIl0sWzIsMiwiTSJdLFswLDIsIk4iXSxbNCwyLCIwIl0sWzIsMSwiZyIsMCx7InN0eWxlIjp7ImhlYWQiOnsibmFtZSI6ImVwaSJ9fX1dLFsxLDNdLFswLDEsImYiXSxbMCwyLCJcXGV4aXN0cyBcXHRpbGRlIGYiLDIseyJzdHlsZSI6eyJib2R5Ijp7Im5hbWUiOiJkYXNoZWQifX19XV0=)

- Direct summand:

  $P$ is a direct summand of a free module $F$, so $F = P \oplus T$ for some module $T\leq F$.

- Splitting:

  For every SES $0\to A\to B\to P\to 0$, there is a right section $P\to B$ such that $P\to B\to P = \id_P$.

  > Note that this implies $B\cong \im(P\to B) \oplus \ker(B\to P)$.
  
- Exactness:

  The (always left-exact) covariant hom functor $\Hom(P, \wait)$ is right-exact.
:::

:::{.remark}
There is a nice way to remember the right diagrams for injective and projective modules.
The slogan is that morphisms *out* of a projective module can be *pulled* back through epimorphisms/surjections, and morphisms *into* an injective module can be *pushed* forward through monomorphisms/injections.

\begin{tikzcd}
	&&&&&& P \\
	\\
	0 && A && B && C && 0 \\
	\\
	&& I
	\arrow[from=3-1, to=3-3]
	\arrow[hook, from=3-3, to=3-5]
	\arrow[two heads, from=3-5, to=3-7]
	\arrow[from=3-7, to=3-9]
	\arrow["{\text{Pull back through surjection}}"', dashed, from=1-7, to=3-5]
	\arrow["{\text{Push forward through injections}}", dashed, from=3-5, to=5-3]
	\arrow[from=1-7, to=3-7]
	\arrow[from=3-3, to=5-3]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsNyxbMCwyLCIwIl0sWzIsMiwiQSJdLFs0LDIsIkIiXSxbNiwyLCJDIl0sWzgsMiwiMCJdLFs2LDAsIlAiXSxbMiw0LCJJIl0sWzAsMV0sWzEsMiwiIiwwLHsic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoiaG9vayIsInNpZGUiOiJ0b3AifX19XSxbMiwzLCIiLDAseyJzdHlsZSI6eyJoZWFkIjp7Im5hbWUiOiJlcGkifX19XSxbMyw0XSxbNSwyLCJcXHRleHR7UHVsbCBiYWNrIHRocm91Z2ggc3VyamVjdGlvbn0iLDIseyJzdHlsZSI6eyJib2R5Ijp7Im5hbWUiOiJkYXNoZWQifX19XSxbMiw2LCJcXHRleHR7UHVzaCBmb3J3YXJkIHRocm91Z2ggaW5qZWN0aW9uc30iLDAseyJzdHlsZSI6eyJib2R5Ijp7Im5hbWUiOiJkYXNoZWQifX19XSxbNSwzXSxbMSw2XV0=)

:::

:::{.proposition title="Free implies projective"}
Any free $M\in \rmod$ is projective.
:::

:::{.proof title="?"}
\envlist

- Let $M$ be free, so that the universal property gives us this diagram:

\begin{tikzcd}
	M \\
	\\
	{\mathcal{B}} && N
	\arrow["f", from=3-1, to=3-3]
	\arrow["{\tilde f}", dashed, from=1-1, to=3-3]
	\arrow["\iota", hook, from=3-1, to=1-1]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsMyxbMCwyLCJcXG1hdGhjYWx7Qn0iXSxbMCwwLCJNIl0sWzIsMiwiTiJdLFswLDIsImYiXSxbMSwyLCJcXHRpbGRlIGYiLDAseyJzdHlsZSI6eyJib2R5Ijp7Im5hbWUiOiJkYXNoZWQifX19XSxbMCwxLCJcXGlvdGEiLDAseyJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6InRvcCJ9fX1dXQ==)

- To show $M$ is projective, we need to produce a lift in the following diagram, where $B, C$ are arbitrary:

\begin{tikzcd}
	&& M \\
	\\
	B && C && 0
	\arrow[from=3-3, to=3-5]
	\arrow["f", from=1-3, to=3-3]
	\arrow["{\exists \tilde f}"', dashed, from=1-3, to=3-1]
	\arrow["g", two heads, from=3-1, to=3-3]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsNCxbMiwwLCJQIl0sWzIsMiwiQyJdLFswLDIsIkIiXSxbNCwyLCIwIl0sWzEsM10sWzAsMSwiZiJdLFswLDIsIlxcZXhpc3RzIFxcdGlsZGUgZiIsMix7InN0eWxlIjp7ImJvZHkiOnsibmFtZSI6ImRhc2hlZCJ9fX1dLFsyLDEsImciLDAseyJzdHlsZSI6eyJoZWFkIjp7Im5hbWUiOiJlcGkifX19XV0=)

- It suffices to produce a map $\mathcal{B}\to B$, since the universal property then provides $M\to B$.
  Here's the schematic:  

\begin{tikzcd}
	&& {\mathcal{B}} & {\ts{e_i}} \\
	\\
	&& M \\
	\\
	B && C && 0 \\
	{\ts{g\inv f(e_i)}} && {} & {\ts{f(e_i)}}
	\arrow[from=5-3, to=5-5]
	\arrow["f", from=3-3, to=5-3]
	\arrow["{\exists \tilde f}"', dashed, from=3-3, to=5-1]
	\arrow["g", two heads, from=5-1, to=5-3]
	\arrow[hook, from=1-3, to=3-3]
	\arrow[dotted, maps to, from=1-4, to=6-4]
	\arrow[dotted, maps to, from=6-4, to=6-1]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsOSxbMiwyLCJNIl0sWzIsNCwiQyJdLFswLDQsIkIiXSxbNCw0LCIwIl0sWzIsMCwiXFxtYXRoY2Fse0J9Il0sWzMsMCwiXFx0c3tlX2l9Il0sWzIsNV0sWzMsNSwiXFx0c3tmKGVfaSl9Il0sWzAsNSwiXFx0c3tnXFxpbnYgZihlX2kpfSJdLFsxLDNdLFswLDEsImYiXSxbMCwyLCJcXGV4aXN0cyBcXHRpbGRlIGYiLDIseyJzdHlsZSI6eyJib2R5Ijp7Im5hbWUiOiJkYXNoZWQifX19XSxbMiwxLCJnIiwwLHsic3R5bGUiOnsiaGVhZCI6eyJuYW1lIjoiZXBpIn19fV0sWzQsMCwiIiwwLHsic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoiaG9vayIsInNpZGUiOiJ0b3AifX19XSxbNSw3LCIiLDAseyJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJtYXBzIHRvIn0sImJvZHkiOnsibmFtZSI6ImRvdHRlZCJ9fX1dLFs3LDgsIiIsMCx7InN0eWxlIjp7InRhaWwiOnsibmFtZSI6Im1hcHMgdG8ifSwiYm9keSI6eyJuYW1lIjoiZG90dGVkIn19fV1d)

- Here we write $\mcb \da \ts{e_i}$, included into $M$, and mapped by $f$ to $C$.
  Then use surjectivity to choose preimages in $B$ under $g$ arbitrarily, and this defines a morphism $\mcb \to B$.

:::

:::{.example title="Projective $\not\implies$ free"}
Let \( R_1, R_2 \) be two nontrivial rings and set \( R \da R_1 \oplus R_2 \).
Then \( R_1, R_2 \) are projective \( R\dash \)modules by construction, but each factor contains \( R\dash \)torsion:
setting \( e \da (0, 1) \in R \) we have \( e \actson R_1 = 0_{R_1} \).
Since free implies torsionfree, \( R_1 \) can not be a free \(R\dash\)module.
:::

## Classification of Modules over a PID

:::{.proposition title="STFGMPID"}
Let $M$ be a finitely generated modules over a PID $R$.
Then there is an **invariant factor** decomposition

\begin{align*}
M \cong F \bigoplus_{i=1}^m R/(r_i) \quad\text{where } r_1 \divides r_2 \divides \cdots
\end{align*}

and similarly an **elementary divisor** decomposition:
\[
M \cong F \bigoplus_{i=1}^n R/ \gens{p_i^{e_i}}
\]
where $F$ is free of finite rank and the $p_i$ are *not necessarily distinct* primes in $R$.
:::

:::{.proposition title="Principal Ideals are Free"}
If $I \normal R$ is an ideal of $R$, then $I$ is a free $R\dash$module iff $I$ is a principal ideal.
:::

:::{.proof title="?"}
$\implies$:

Suppose $I$ is free as an $R\dash$module, and let $B = \theset{\vector m_j}_{j\in J} \subseteq I$ be a basis so we can write $M = \generators{B}$.
Suppose that $\abs{B} \geq 2$, so we can pick at least 2 basis elements $\vector m_1\neq \vector m_2$, and consider
$$
\vector c = \vector m_1 \vector m_2 - \vector m_2 \vector m_1,
$$

which is also an element of $M$ .
Since $R$ is an integral domain, $R$ is commutative, and so
$$
\vector c = \vector m_1 \vector m_2 - \vector m_2 \vector m_1 = \vector m_1 \vector m_2 - \vector m_1 \vector m_2 = \vector 0_M
$$

However, this exhibits a linear dependence between $\vector m_1$ and $\vector m_2$, namely that there exist $\alpha_1, \alpha_2 \neq 0_R$ such that $\alpha_1 \vector m_1 + \alpha_2 \vector m_2 = \vector 0_M$; this follows because $M \subset R$ means that we can take $\alpha_1 = -m_2, \alpha_2 = m_1$. This contradicts the assumption that $B$ was a basis, so we must have $\abs{B} = 1$ and so $B = \theset{\vector m}$ for some $\vector m \in I$. But then $M = \generators{B} = \generators{\vector m}$ is generated by a single element, so $M$ is principal.

$\impliedby$:
Suppose $M\normal R$ is principal, so $M = \generators{\vector m}$ for some $\vector m \neq \vector{0}_M \in M \subset R$.

Then $x\in M \implies x = \alpha\vector m$ for some element $\alpha\in R$ and we just need to show that $\alpha\vector m = \vector 0_M \implies \alpha = 0_R$ in order for $\theset{\vector m}$ to be a basis for $M$, making $M$ a free $R\dash$module.
But since $M \subset R$, we have $\alpha, m \in R$ and $\vector 0_M = 0_R$, and since $R$ is an integral domain, we have $\alpha m = 0_R \implies \alpha = 0_R$ or $m = 0_R$.
Since $m \neq 0_R$, this forces $\alpha = 0_R$, which allows $\theset{m}$ to be a linearly independent set and thus a basis for $M$ as an $R\dash$module.

:::


:::{.remark}
This says every module $M$ decomposes as $M \cong F_M \oplus M_t$ where $F_M$ is free (and thus torsionfree) and $M_t$ is torsion, and moreover $F_M \cong M/M_t$.

That $M/M_t$ is torsionfree: suppose $r(m+ M_t) = M_t$, so $rm\in M_t$ is torsion.
Then $r'(rm)=0$ for some $r'$, making $m$ torsion, and $m+ M_t = M_t$ is the zero coset.

That $F_M \cong M/M_t$: take the SES $0\to M_t\to M \to F\to 0$ to get $F\cong M/M_t$.
This splits since $F$ is free and thus projective, so $F\cong M \oplus M_t$.

:::


## Algebraic Properties

:::{.definition title="Module structure on tensor products"}
\[
r\actson (m\tensor n) \da (r\actson m)\tensor n
.\]
:::


:::{.proposition title="?"}
If $\dim_k V, \dim_k W < \infty$ then there is an isomorphism
\[
V\dual \tensor_k W \mapsvia{\sim} \Hom_{\kmod}(V, W) \\
\tilde v \tensor w &\mapsto \tilde v(\wait) w
.\]
:::


:::{.proposition title="?"}
If either of $\dim_k V, \dim_k W$ is finite, then
\[
V\dual \tensor_k W\dual \mapsvia{\sim} (V\tensor W)\dual \\
v\tensor w &\mapsto (x \tensor y \mapsto v(x) w(y))
.\]

:::


:::{.proposition title="?"}
\[
\Hom_{\kmod}(V, W) \mapsvia{\sim} \Hom_{\kmod}(W, V)\dual \\
T &\mapsto \Tr(T \circ \wait )
.\]
:::


:::{.proposition title="?"}
If $T:V \injects W$ is injective, then $T\tensor \one_X: V\tensor X \injects W\tensor X$ is also injective for any $X$.
Thus $F(\wait) = (\wait \tensor X)$ is right-exact for any $X$.
:::




:::{.example title="Computing tensor products"}
$\ZZ/2 \tensor_\ZZ \ZZ/3 = 0$:

\begin{tikzcd}
	0 && {\ZZ \tensor_\ZZ \ZZ/3} && {\ZZ \tensor_\ZZ \ZZ/3} && {\ZZ/3 \tensor_\ZZ \ZZ/2} \\
	\\
	0 && {\ZZ/3} && {\ZZ/3} && 0
	\arrow["{(\wait \times 2)}", from=3-3, to=3-5]
	\arrow["{(\wait \times 2) \cross \one}", from=1-3, to=1-5]
	\arrow[from=3-5, to=3-7]
	\arrow[from=1-5, to=1-7]
	\arrow[from=1-1, to=1-3]
	\arrow[from=3-1, to=3-3]
	\arrow["{\proj_2}"{description}, from=1-3, to=3-3]
	\arrow["{\proj_2}"{description}, from=1-5, to=3-5]
	\arrow["\cong", dashed, from=1-7, to=3-7]
\end{tikzcd}


> [Link to Diagram](https://q.uiver.app/?q=WzAsOCxbMiwwLCJcXFpaIFxcdGVuc29yX1xcWlogXFxaWi8zIl0sWzQsMCwiXFxaWiBcXHRlbnNvcl9cXFpaIFxcWlovMyJdLFsyLDIsIlxcWlovMyJdLFs0LDIsIlxcWlovMyJdLFs2LDIsIjAiXSxbNiwwLCJcXFpaLzMgXFx0ZW5zb3JfXFxaWiBcXFpaLzIiXSxbMCwyLCIwIl0sWzAsMCwiMCJdLFsyLDMsIihcXHdhaXQgXFx0aW1lcyAyKSJdLFswLDEsIihcXHdhaXQgXFx0aW1lcyAyKSBcXGNyb3NzIFxcb25lIl0sWzMsNF0sWzEsNV0sWzcsMF0sWzYsMl0sWzAsMiwiXFxwcm9qXzIiLDFdLFsxLDMsIlxccHJval8yIiwxXSxbNSw0LCJcXGNvbmciLDAseyJzdHlsZSI6eyJib2R5Ijp7Im5hbWUiOiJkYXNoZWQifX19XV0=)

:::

