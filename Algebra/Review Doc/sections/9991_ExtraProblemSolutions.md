Lemma
: Every $a\in R$ for a finite ring is either a unit or a zero divisor.

Proof
: Let $a\in R$ and define $\phi(x) = ax$.
  If $\phi$ is injective, then it is surjective, so $1 = ax$ for some $x \implies x\inv = a$.
  Otherwise, $ax_1 = ax_2$ with $x_1 \neq x_2 \implies a(x_1 - x_2) = 0$ and $x_1 - x_2 \neq 0$, so $a$ is a zero divisor.

Lemma
: Maximal $\implies$ prime, but generally not the converse.

Proof
:   Suppose $\mm$ is maximal, $ab\in \mm$, and $b\not\in \mm$.
    Then there is a containment of ideals $\mm \subsetneq \mm + (b) \implies \mm + (b) = R$.

    So
    $$
    1 = m + rb \implies a = am + r(ab)
    ,$$
    but $am\in \mm$ and $ab\in \mm \implies a\in \mm$.


*Counterexample*: $(0) \in \ZZ$ is prime since $\ZZ$ is a domain, but not maximal since it is properly contained in any other ideal.

Lemma
: The nilradical is the intersection of all **prime** ideals, i.e.
  $$
  \mathfrak{N}(R) = \intersect_{\mathfrak{p} \in \spec(R)} \mathfrak{p}
  $$

Proof
:   $\mathfrak{N} \subseteq \intersect \mathfrak{p}$:
    $x \in \mathfrak{N} \implies x^n = 0 \in \mathfrak p \implies x\in \mathfrak{p} \text{ or } x^{n-1}\in\mathfrak p$.

    $\mathfrak{N}^c \subseteq \union \mathfrak{p}^c$:
    Define $S = \theset{I\normal R \suchthat a^n\not\in I \text{ for any } n}$.
    Then apply Zorn's lemma to get a maximal ideal $\mm$, and maximal $\implies$ prime.


