# Rings

## Definitions



Definition (Simple Ring)
: A ring $R$ is **simple** iff every ideal $I \normal R$ is either $0$ or $R$.

Definition (Irreducible Element)
: An element $r\in R$ is **irreducible** iff $r = ab \implies a$ is a unit or $b$ is a unit.

Definition (Prime Element)
: An element $r\in R$ is **prime** iff $ab \divides r \implies a\divides r$ or $b\divides r$ whenever $a,b$ are nonzero and not units.

Definition (Prime Ideal)
: $\mathfrak{p}$ is a **prime** ideal $\iff ab\in \mathfrak p \implies a\in \mathfrak p$ or $b\in \mathfrak p$.

Definition (Prime Spectrum)
: $\spec(R) = \theset{\pr \normal R \suchthat \pr \text{ is prime}}$ is the **spectrum** of $R$.

Definition (Maximal Ideal)
: $\mathfrak m$ is **maximal** $\iff I \normalneq R \implies I \subseteq \mathfrak m$.

Examples: 

- Maximal ideals of $R[x]$ are of the form $I = (x - a_i)$ for some $a_i \in R$.

Definition (Max Spectrum)
: $\maxspec(R) = \theset{\mm \normal R \suchthat \mm \text{ is maximal}}$ is the **max-spectrum** of $R$.

Definition (Nilradical)
: $\nilrad(R) \definedas \theset{x\in R \suchthat x^n=0\text{ for some } n}$ is the **nilradical** of $R$.

Definition (Jacobson Radical)
: The **Jacobson radical** $\jacobsonrad(R)$ is the intersection of all maximal ideals, i.e.
  $$
  \jacobsonrad(R) = \intersect_{\mm \in \spec_{\text{max}}} \mm
  $$
Definition (Semisimple)
: A nonzero unital ring $R$ is **semisimple** iff $R \cong \bigoplus_{i=1}^n M_i$ with each $M_i$ a simple module.

Definition (Radical Ideal)
: An ideal $I\normal R$ is *radical* iff $a^n\in I$ implies that $a\in I$.


**Lemma (Characterizations of Rings):**

- $R$ a commutative division ring $\implies R$ is a field
- $R$ a finite integral domain $\implies R$ is a field.
- $\FF$ a field $\implies \FF[x]$ is a Euclidean domain.
- $\FF$ a field $\implies \FF[x]$ is a PID.
- $\FF$ is a field $\iff \FF$ is a commutative simple ring.
- $R$ is a UFD $\iff R[x]$ is a UFD.
- $R$ a PID $\implies R[x]$ is a UFD
- $R$ a PID $\implies R$ Noetherian
- $R[x]$ a PID $\implies R$ is a field.

**Lemma:**
Fields $\subset$ Euclidean domains  $\subset$  PIDs $\subset$ UFDs $\subset$ Integral Domains  $\subset$ Rings

- A Euclidean Domain that is not a field: $\FF[x]$ for $\FF$ a field
  - *Proof*: Use previous lemma, and $x$ is not invertible

- A PID that is not a Euclidean Domain: $\ZZ\left[\frac{1 + \sqrt{-19}}{2}\right]$.
  - *Proof*: complicated.

- A UFD that is not a PID: $\FF[x, y]$.
  - *Proof*: $\generators{x, y}$ is not principal

-  An integral domain that is not a UFD: $\ZZ[\sqrt{-5}]$
   - *Proof*: $(2+\sqrt{-5})(2-\sqrt{-5})=9=3\cdot 3$, where all factors are irreducible (check norm).

-  A ring that is not an integral domain: $\ZZ/(4)$
   - *Proof*: $2 \mod 4$ is a zero divisor.

Lemma
: In $R$ a UFD, an element $r\in R$ is prime $\iff r$ is irreducible.

Note: For $R$ an integral domain, prime $\implies$ irreducible, but generally not the converse.

*Example of a prime that is not irreducible:*
$x^2 \mod (x^2 + x) \in \QQ[x]/(x^2 + x)$. Check that $x$ is prime directly, but $x=x\cdot x$ and $x$ is not a unit.

*Example of an irreducible that is not prime:*
$3\in \ZZ[\sqrt{-5}]$. Check norm to see irreducibility, but $3 \divides 9 = (2+\sqrt{-5})(2-\sqrt{-5})$ and doesn't divide either factor.

Lemma
: If $R$ is a PID, then every element in $R$ has a unique prime factorization.

Theorem (Krull)
: Every ring has proper maximal ideals, and any proper ideal is contained in a maximal ideal.

Theorem (Artin-Wedderubrn)
: If $R$ is a nonzero, unital, *semisimple* ring then $R \cong \bigoplus_{i=1}^m \mathrm{Mat}(n_i, D_i)$, a finite sum of matrix rings over division rings.

Corollary
: If $M$ is a simple ring over $R$ a division ring, the $M$ is isomorphic to a matrix ring.

### Zorn's Lemma

Lemma
: Fields are simple rings. 

Lemma
: If $I\normal R$ is a proper ideal $\iff I$ contains no units.

Proof
: $r\in R\units \intersect I \implies r\inv r \in I \implies 1\in I \implies x\cdot 1 \in I \quad \forall x\in R$.

Lemma
: If $I_1 \subseteq I_2 \subseteq \cdots$ are ideals then $\union_j I_j$ is an ideal.

**Example Application:**
Every proper ideal is contained in a maximal ideal.

Proof
:   Let $0 < I < R$ be a proper ideal, and consider the set
    $$
    S = \theset{J \suchthat I   \subseteq J < R}
    .$$

    Note $I\in S$, so $S$ is nonempty.
    The claim is that $S$ contains a maximal element $M$.

    $S$ is a poset, ordered by set inclusion, so if we can show that every chain has an upper bound, we can apply Zorn's lemma to produce $M$.

    Let $C \subseteq S$ be a chain in $S$, so $C = \theset{C_1 \subseteq C_2 \subseteq \cdots}$ and define $\hat C = \union_i C_i$.

    **$\hat C$ is an upper bound for $C$:**
    This follows because every $C_i \subseteq \hat C$.

    **$\hat C$ is in $S$:**
    Use the fact that $I \subseteq C_i < R$ for every $C_i$ and since no $C_i$ contains a unit, $\hat C$ doesn't contain a unit, and is thus proper.

