## Ring Theory

Basic Structure

- Show that if an ideal $I\normal R$ contains a unit then $I = R$.
- Show that $R\units$ need not be closed under addition.

Ideals

:::{.problem title="Units or Zero Divisors"}
Every $a\in R$ for a finite ring is either a unit or a zero divisor.
:::
:::{.solution}
\hfill
- Let $a\in R$ and define $\phi(x) = ax$.
- If $\phi$ is injective, then it is surjective, so $1 = ax$ for some $x \implies x\inv = a$.
- Otherwise, $ax_1 = ax_2$ with $x_1 \neq x_2 \implies a(x_1 - x_2) = 0$ and $x_1 - x_2 \neq 0$
- So $a$ is a zero divisor.
:::

:::{.problem title="Maximal implies prime"}
Maximal $\implies$ prime, but generally not the converse.
:::
:::{.solution}

- Suppose $\mm$ is maximal, $ab\in \mm$, and $b\not\in \mm$.

- Then there is a containment of ideals $\mm \subsetneq \mm + (b) \implies \mm + (b) = R$.

- So
\[
1 = m + rb \implies a = am + r(ab)
,\]
  but $am\in \mm$ and $ab\in \mm \implies a\in \mm$.


*Counterexample*: 
$(0) \in \ZZ$ is prime since $\ZZ$ is a domain, but not maximal since it is properly contained in any other ideal.
:::


- Show that every proper ideal is contained in a maximal ideal
- Show that if $x\in R$ a PID, then $x$ is irreducible $\iff \gens{x}\normal R$ is maximal.
- Show that intersections, products, and sums of ideals are ideals.
- Show that the union of two ideals need not be an ideal.
- Show that every ring has a proper maximal ideal.
- Show that $I\normal R$ is maximal iff $R/I$ is a field.
- Show that $I \normal R$ is prime iff $R/I$ is an integral domain.
- Show that $\union_{\mfm \in \maxspec(R)} = R\setminus R\units$.
- Show that $\maxspec(R) \subsetneq \spec(R)$ but the containment is strict.
- $\star$ Show that if $x$ is not a unit, then $x$ is contained in some maximal ideal.
- Show that every prime ideal is radical.
- Show that the nilradical is given by $\nilrad(R) = \rad(0)$.
- Show that $\text{rad}(IJ) = \text{rad}(I) \intersect \text{rad}(J)$
- Show that if $\spec(R) \subseteq \maxspec(R)$ then $R$ is a UFD.
- Show that if $R$ is Noetherian then every ideal is finitely generated.

Characterizing Certain Ideals

- Show that the nilradical of a ring is the intersection of all prime ideals $I\normal R$.
- Show that for an ideal $I\normal R$, its radical is the intersection of all prime ideals containing $I$.
- Show that $\rad(I)$ is the intersection of all prime ideals containing $I$.

:::{.problem title="Jacobson radical is bigger than the nilradical"}
The nilradical is contained in the Jacobson radical, i.e.
\[
\mathfrak N(R) \subseteq J(R)
.\]
:::
:::{.solution}
Maximal $\implies$ prime, and so if $x$ is in every prime ideal, it is necessarily in every maximal ideal as well.
:::

:::{.problem title="Mod by nilradical to kill nilpotents"}
$R/\mathfrak \nilrad(R)$ has no nonzero nilpotent elements.
:::
:::{.solution}
\hfill
\[
a + \mathfrak N(R)\text{ nilpotent } &\implies (a+ \mathfrak N(R))^n \definedas a^n + \mathfrak N(R)= \mathfrak N(R) \\
&\implies a^n \in \mathfrak N(R) \\
&\implies \exists \ell \text{ such that } (a^n)^\ell = 0 \\
&\implies a\in \mathfrak N(R)
.
\]
:::

:::{.problem title="Nilradical is intersection of primes"}
The nilradical is the intersection of all prime ideals, i.e.
\[
\mathfrak{N}(R) = \intersect_{\mathfrak{p} \in \spec(R)} \mathfrak{p}
\]
:::
:::{.solution}
- $\mathfrak{N} \subseteq \intersect \mathfrak{p}$:

- $x \in \mathfrak{N} \implies x^n = 0 \in \mathfrak p \implies x\in \mathfrak{p} \text{ or } x^{n-1}\in\mathfrak p$.

- $\mathfrak{N}^c \subseteq \union \mathfrak{p}^c$:

- Define $S = \theset{I\normal R \suchthat a^n\not\in I \text{ for any } n}$.

- Then apply Zorn's lemma to get a maximal ideal $\mm$, and maximal $\implies$ prime.
:::

Misc

- Show that localizing a ring at a prime ideal produces a local ring.
- Show that $R$ is a local ring iff for every $x\in R$, either $x$ or $1-x$ is a unit.
- Show that if $R$ is a local ring then $R\setminus R\units$ is a proper ideal that is contained in the Jacobson radical $J(R)$.
- Show that if $R\neq 0$ is a ring in which every non-unit is nilpotent then $R$ is local.
- Show that every prime ideal is primary.
- Show that every prime ideal is irreducible.
- Show that






