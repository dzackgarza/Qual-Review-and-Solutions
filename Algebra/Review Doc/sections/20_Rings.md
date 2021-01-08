# Ring Theory

## Definitions

### Undergrad Review

:::{.definition title="Divisibility of Elements"}
An element \( r\in R \) is **divisible** by \( q \in R \) if and only if there exists some \( c \in R \) such that \( r = qc \).
In this case, we sometimes write \( q\divides r \).
:::

:::{.definition title="Irreducible Element"}
An element $r\in R$ is **irreducible** iff 
\[
r=ab \implies a \in R\units \text{ or }  b\in R\units
\]
:::

:::{.definition title="Prime Element"}
An element $p\in R$ is **prime** iff 
\[  
a,b \in R\units\smz, \quad ab\divides p \implies a\divides p \text{ or }  b\divides p
.\]
:::

:::{.definition title="Zero Divisor"}
An element $r\in R$ is a **zero-divisor** iff there exists an $a\in R\smz$ such that $ar = ra = 0$.
Equivalently, the map
\[  
r_\wait: R &\to R \\
x &\mapsto rx
\]
fails to be injective.
:::

:::{.definition title="Associate Elements"}
$a, b\in R$ are **associates** iff there exists a $u\in R\units$ such that $a = ub$. 
Equivalently, $a\divides b$ and $b\divides a$.
:::

:::{.definition title="Prime Ideal"}
$\mfp$ is a **prime** ideal $\iff$
\[ 
ab\in \mfp \implies a\in \mfp \txt{or} b\in \mfp
.\]
:::

:::{.definition title="Irreducible Ideal"}
An ideal $I\normal R$ is *irreducible* if it can not be written as the intersection of two larger ideals, i.e. there are not $J_1, J_2 \supseteq I$ such that $J_1 \intersect J_2 = I$.
:::

:::{.definition title="Maximal Ideal"}
$\mfm$ is **maximal** $\iff \qty{ I \normalneq R \implies I \subseteq \mfm} \iff R/I$ is a field.
:::

:::{.example}
Maximal ideals of $R[x]$ are of the form $I = (x - a_i)$ for some $a_i \in R$.
:::

:::{.definition title="Max Spectrum"}
$\maxspec(R) = \theset{\mfm \normal R \suchthat \mfm \text{ is maximal}}$ is the **max-spectrum** of $R$.
:::


### Types of Rings

:::{.definition title="Simple Modules"}
A module $M$ is **simple** iff every submodule $M' \leq M$ is either $0$ or $M$.
A ring \( R \) is simple if and only if it is simple as an \(R\dash\)module, i.e. there are no nontrivial proper ideals.
:::

:::{.definition title="Semisimple Modules"}
A module \( M \) is **simple** if and only if it admits a decomposition 
\[
M = \bigoplus_{j\in J} M_j
\]
with each \( M_j \) simple.
:::


:::{.definition title="Integral Domain"}
Slogan: no nonzero zero divisors, i.e.
\[  
a, b\in R\smz, ab = 0 \implies a = 0 \txt{or} b = 0
.\]
:::

:::{.definition title="Principal Ideal"}
$I \normal R$ *principal* when $\exists a\in R : I = \gens{a}$, i.e. whenever $I\normal R$, there is some single $a\in R$ such that $I = \gens{a}$.
:::

:::{.definition title="Principal Ideal Domain"}
A ring $R$ is *principal* iff every ideal is principal.
:::

:::{.definition title="Unique Factorization Domain"}
A ring $R$ is a *UFD* iff $R$ is an integral domain and every $r\in R\smz$ admits a decomposition
\[  
r = u \prod_{i=1}^n p_i
\]
where $u\in R\units$ and the $p_i$ irreducible, which is unique up to associates.
:::

:::{.definition title="Noetherian"}
A ring $R$ is Noetherian if the ACC holds: every ascending chain of ideals $I_1 \leq I_2 \cdots$ stabilizes in the sense that there exists some $N$ such that $I_N = I_{N+1} = \cdots$.
:::

:::{.definition title="Primary Ideal"}
An ideal $I\normal R$ is *primary* iff whenever $pq\in I$, $p\in I$ and $q^n\in I$ for some $n$.
:::


:::{.definition title="Nilradical"}
$\nilrad(R) \definedas \theset{x\in R \suchthat x^n=0\text{ for some } n}$ is the **nilradical** of $R$.
:::

:::{.definition title="Jacobson Radical"}
The **Jacobson radical** $\jacobsonrad(R)$ is the intersection of all maximal ideals, i.e.
\[  
\jacobsonrad(R) = \intersect\theset{\mfm \suchthat \mfm \in \maxspec(R) }
.\]
:::

:::{.definition title="Semisimple"}
A nonzero unital ring $R$ is **semisimple** iff $R \cong \bigoplus_{i=1}^n M_i$ with each $M_i$ a simple module.
:::

:::{.proposition title="Characterizations of Rings"}
- $R$ a commutative division ring $\implies R$ is a field
- $R$ a finite integral domain $\implies R$ is a field.
- $\FF$ a field $\implies \FF[x]$ is a Euclidean domain.
- $\FF$ a field $\implies \FF[x]$ is a PID.
- $\FF$ is a field $\iff \FF$ is a commutative simple ring.
- $R$ is a UFD $\iff R[x]$ is a UFD.
- $R$ a PID $\implies R[x]$ is a UFD
- $R$ a PID $\implies R$ Noetherian
- $R[x]$ a PID $\implies R$ is a field.
:::

:::{.proposition}
Fields $\subset$ Euclidean domains  $\subset$  PIDs $\subset$ UFDs $\subset$ Integral Domains  $\subset$ Rings
:::

:::{.example}
- A Euclidean Domain that is not a field: $\FF[x]$ for $\FF$ a field
  - *Proof*: Use previous lemma, and $x$ is not invertible

- A PID that is not a Euclidean Domain: $\ZZ\left[\frac{1 + \sqrt{-19}}{2}\right]$.
  - *Proof*: complicated.

- A UFD that is not a PID: $\FF[x, y]$.
  - *Proof*: $\gens{x, y}$ is not principal

-  An integral domain that is not a UFD: $\ZZ[\sqrt{-5}]$
   - *Proof*: $(2+\sqrt{-5})(2-\sqrt{-5})=9=3\cdot 3$, where all factors are irreducible (check norm).

-  A ring that is not an integral domain: $\ZZ/(4)$
   - *Proof*: $2 \mod 4$ is a zero divisor.
:::

:::{.proposition}
In $R$ a UFD, an element $r\in R$ is prime $\iff r$ is irreducible.
:::

Note: For $R$ an integral domain, prime $\implies$ irreducible, but generally not the converse.

$x^2 \mod (x^2 + x) \in \QQ[x]/(x^2 + x)$. Check that $x$ is prime directly, but $x=x\cdot x$ and $x$ is not a unit.


:::{.proposition}
If $R$ is a PID, then every element in $R$ has a unique prime factorization.
:::

:::{.theorem title="Krull"}
Every ring has proper maximal ideals, and any proper ideal is contained in a maximal ideal.
:::

:::{.theorem title="Artin-Wedderburn?"}
If $R$ is a nonzero, unital, *semisimple* ring then $R \cong \bigoplus_{i=1}^m \mathrm{Mat}(n_i, D_i)$, a finite sum of matrix rings over division rings.
:::


:::{.corollary}
If $M$ is a simple ring over $R$ a division ring, the $M$ is isomorphic to a matrix ring.
:::

### Toward Number Theory and Algebraic Geometry

:::{.definition title="Reduced Ring"}
A ring $R$ is *reduced* if $R$ contains no nonzero nilpotent elements. 
:::

:::{.definition title="Local Ring"}
A ring $R$ is *local* iff it contains a unique maximal ideal.
:::

:::{.definition title="Prime Spectrum"}
$\spec(R) = \theset{\pr \normal R \suchthat \pr \text{ is prime}}$ is the **spectrum** of $R$.
:::

:::{.definition title="Radical of an Ideal"}
For an ideal $I\normal R$, the radical $\rad(I) \definedas \theset{r\in R\suchthat r^n\in I\text{ for some } n\geq 0}$, so $x^n \in I \iff x\in I$.
:::

:::{.definition title="Radical Ideal"}
An ideal is *radical* iff $\rad(I) = I$. 
:::


## Misc

## Zorn's Lemma

:::{.theorem title="Zorn's Lemma"}
If $P$ is a poset in which every chain has an upper bound, then $P$ has a maximal element.
:::

Some useful propositions used when *applying* Zorn's lemma:

:::{.proposition}
Fields are simple rings. 
:::

:::{.proposition}
If $I\normal R$ is a proper ideal $\iff I$ contains no units.
:::

:::{.proof}
$r\in R\units \intersect I \implies r\inv r \in I \implies 1\in I \implies x\cdot 1 \in I \quad \forall x\in R$.
:::

:::{.proposition}
If $I_1 \subseteq I_2 \subseteq \cdots$ are ideals then $\union_j I_j$ is an ideal.
:::

:::{.proposition}
Every proper ideal is contained in a maximal ideal.
:::

:::{.proof}
Let $0 < I < R$ be a proper ideal, and consider the set
$$
S = \theset{J \suchthat I   \subseteq J < R}
.$$

Note $I\in S$, so $S$ is nonempty.
The claim is that $S$ contains a maximal element $M$.

$S$ is a poset, ordered by set inclusion, so if we can show that every chain has an upper bound, we can apply Zorn's lemma to produce $M$.

Let $C \subseteq S$ be a chain in $S$, so $C = \theset{C_1 \subseteq C_2 \subseteq \cdots}$ and define $\hat{C} = \union_i C_i$.

**$\hat{C}$ is an upper bound for $C$:**
This follows because every $C_i \subseteq \hat{C}$.

**$\hat{C}$ is in $S$:**
Use the fact that $I \subseteq C_i < R$ for every $C_i$ and since no $C_i$ contains a unit, $\hat{C}$ doesn't contain a unit, and is thus proper.
:::

:::{.example title="An irreducible element that is not prime."}
$3\in \ZZ[\sqrt{-5}]$. 
Check norm to see irreducibility, but $3 \divides 9 = (2+\sqrt{-5})(2-\sqrt{-5})$ and doesn't divide either factor.
:::

