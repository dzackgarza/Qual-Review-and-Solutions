---
order: 20
---

# Measure Theory

:::{.fact}
Some useful tricks:

- $\mu(A\sm B) = \mu(A) - \mu(B)$ if $\mu(B) < \infty$
- Write $f = f-f_n + f_n$
- If $G$ is measurable, then there for every $\eps$ there exists an open $G \contains E$ such $m(G) \leq m(E) + \eps$
- If $E$ is measurable,
  - $E = F_{\delta} \disjoint N$ for $N$ a null set.
  - $E \disjoint N = G_{\delta}$ for $N$ a null set.
:::

## Abstract Measure Theory


:::{.definition title="Measures on measurable spaces"}
If $(X, \mcm)$ is a measurable space, then a **measure** is a function $\mu: \mcm \to [0,\infty]$ such that 

1. $\mu(\emptyset) = 0$.
2. Countable additivity: if $\ts{E_k}_{k\geq 1}$ is a countable union of disjoint sets in $X$, then 
\[
\mu\qty{\disjoint_{k\geq 1} E_k} = \sum_{k\geq 1} \mu(E_k)
.\]

If (2) only holds for finitely indexed sums, we say $\mu$ is **$\sigma\dash$additive**.
:::

:::{.proposition title="Subtraction of Measures"}
$$m(A) = m(B) + m(C) \qtext{and} m(C) < \infty \implies m(A) - m(C) = m(B).$$
:::

:::{.theorem title="Properties of measures"}
Let $(X, \mcm, \mu)$ be a measure space.
Then

1. Monotonicity: $E \subseteq F \implies \mu(E) \leq \mu(F)$.
2. Countable subadditivity: If $ts{E_k}_{k\geq 1}$ is a countable collection, 
\[
\mu\qty{\Union_{k\geq 1} E_k} \leq \sum_{k\geq 1} \mu(E_k)
.\]
:::

:::{.proposition title="Continuity of Measure"}
\[
\text{Continuity from below:} \quad 
E_{n} \nearrow E &\implies m(E_{n}) \converges{n\to\infty}\too m(E) \\
\text{Continuity from above:} \quad 
m(E_{1}) < \infty \text{ and } E_{n} \searrow E &\implies m(E_{n}) \converges{n\to\infty}\too m(E)
.\]

Mnemonic: $\lim_n \mu(E_n) = \mu(\lim E_n)$.
:::

:::{.proof title="sketches"}
\envlist

- From below: break into disjoint annuli $A_{2} = E_{2}\setminus E_{1}$, 
  - Apply countable disjoint additivity to $E = \disjoint A_{i}$.

- From above: funny step, use $E_{1} = (\disjoint E_{j}\setminus E_{j+1}) \disjoint (\intersect E_{j})$.
  - Taking measures yields a telescoping sum, and use countable additivity, then finiteness to subtract.

![image_2021-05-28-23-29-31](figures/image_2021-05-28-23-29-31.png)


:::

:::{.proof title="of continuity of measure from below, detailed"}
For any measure $\mu$,
\[
\mu(F_1) < \infty,\, F_k \decreasesto F \implies \lim_{k\to\infty}\mu(F_k) = \mu(F)
,\]
  where $F_k \searrow F$ means $F_1 \supseteq F_2 \supseteq \cdots$ with $\intersect_{k=1}^\infty F_k = F$.
  - Note that $\mu(F)$ makes sense: each $F_k \in \mathcal{B}$, which is a $\sigma\dash$algebra and closed under countable intersections.

- Take disjoint annuli by setting $E_k \da F_k \sm F_{k+1}$
- Funny step: write
\[
F_1 = F \disjoint \Disjoint_{k=1}^{\infty} E_k
.\]

  - This is because $x\in F_1$ iff $x$ is in every $F_k$, so in $F$, **or**
  - $x\not \in F_1$ but $x\in F_2$, noting incidentally $x\in F_3, F_4,\cdots$, **or**,
  - $x\not\in F_2$ but $x\in F_3$ and thus $F_4, F_4,\cdots$, and so on.

- Now take measures, and note that we get a telescoping sum:
\[
\mu(F_1) 
&= \mu(F) + \sum_{k=1}^\infty \mu(E_k) \\
&= \mu(F) + \lim_{N\to\infty} \sum_{k=1}^N \mu(E_k) \\
&\da \mu(F) + \lim_{N\to\infty} \sum_{k=1}^N \mu(F_k \sm F_{k+1} ) \\
&\da \mu(F) + \lim_{N\to\infty} \sum_{k=1}^N \mu(F_k) - \mu(F_{k+1} ) \hspace{5em}\text{to be justified}\\
&= \mu(F) + \lim_{N\to\infty} 
[
(\mu(F_1) - \mu(F_2)) +  
(\mu(F_2) - \mu(F_3)) +  
\cdots \\ 
& \hspace{8em} + (\mu(F_{N-1}) - \mu(F_N)) +  
(\mu(F_N) - \mu(F_{N+1})) 
] \\ \\
&= \mu(F) + \lim_{N\to\infty} \mu(F_1) - \mu(F_{N+1}) \\
&= \mu(F) + \mu(F_1) - \lim_{N\to\infty} \mu(F_{N+1})
.\]

- Justifying the measure subtraction: the general statement is that for any pair of sets $A\subseteq X$, $\mu(X\sm A) = \mu(X) - \mu(A)$ when $\mu(A) < \infty$:
  \[
  X &= A \disjoint (X\sm A) \\
  \implies \mu(X) &= \mu(A) + \mu(X\sm A) && \text{countable additivity} \\
  \implies \mu(X) -\mu(A) &= \mu(X\sm A) && \text{if } \mu(A) < \infty 
  .\]


- Now use that $\mu(F_1)<\infty$ to justify subtracting it from both sides:
\[
\mu(F_1)
&= \mu(F) + \mu(F_1) - \lim_{N\to\infty} \mu(F_{N+1}) \\
\implies
0
&= \mu(F_1) - \lim_{N\to\infty} \mu(F_{N+1}) \\
\lim_{N\to\infty} \mu(F_{N+1})
&= \mu(F_1) 
.\]

- Now use that $\lim_{N\to\infty}\mu(F_{N+1}) = \lim_{N\to\infty} \mu(F_N)$ to conclude.
:::

## Outer Measure

:::{.proposition title="Properties of Outer Measure"}
\envlist

1. Monotonicity: $E\subseteq F \implies m_*(E) \leq m_*(F)$.
2. Countable Subadditivity: $m_*(\union E_{i}) \leq \sum m_*(E_{i})$.
3. Approximation: For all $E$ there exists a $G \supseteq E$ such that $m_*(G) \leq m_*(E) + \varepsilon$.
4. Disjoint[^1] Additivity: $m_*(A \disjoint B) = m_*(A) + m_*(B)$. 

[^1]: This holds for outer measure **iff** $\mathrm{dist}(A, B) > 0$.

:::

:::{.definition title="Lebesgue Measurability"}
A set $E$ is **measurable** iff it can be approximated by an open set in $m_*$, so there exists $G\contains E$ with $m_*(G\sm E) < \eps$.
:::

## Measures on $\RR^d$

:::{.proposition title="Opens are unions of almost disjoint intervals."}
Every open subset of $\RR$ (resp $\RR^n$) can be written as a unique countable union of disjoint (resp. almost disjoint) intervals (resp. cubes).
:::

:::{.proposition title="Translation and Dilation Invariance"}
Lebesgue measure is translation and dilation invariant.
:::

:::{.proof title="of translation/dilation invariance"}
\envlist

- This is obvious for cubes: 
  - For translation, if $Q_i \covers E$ then $Q_i + k \covers E + k$.
    One can then show $m_*(E + k) \leq \sum \abs{Q_i + k} = \sum \abs{Q_i}\leq m_*(E) + \eps$ for all $\eps$, and get the reverse inequality by writing $E = (E+y)-y$.
  - For dilation, use that $m_*(t(A\disjoint B)) = tm_*(A\disjoint B)$, which is useful because we cover with disjoint cubes.
    Then use that $tQ_i \covers tE$ to get $tm_*(E) \leq t\sum \abs{Q_i} = \sum \abs{tQ_i} \leq m_*(tE) + \eps$ and similarly reverse to get equality.
:::

:::{.theorem title="Non-measurable sets exist"}
There is a non-measurable set $A\subseteq \RR$.
:::

:::{.proof title="Constructing a non-measurable set"}
\envlist

- Use AOC to choose one representative from every coset of $\RR/\QQ$ on $[0, 1)$, which is countable, and assemble them into a set $N$
- Enumerate the rationals in $[0, 1]$ as $q_{j}$, and define $N_{j} = N + q_{j}$. These intersect trivially.
- Define $M \da \disjoint N_{j}$, then $[0, 1) \subseteq  M \subseteq [-1, 2)$, so the measure must be between 1 and 3.
- By translation invariance, $m(N_{j}) = m(N)$, and disjoint additivity forces $m(M) = 0$, a contradiction.
:::

:::{.proposition title="Limsups/infs of measurable sets are measurable."}
If $A_{n}$ are all measurable, $\limsup A_{n}$ and $\liminf A_{n}$ are measurable.
:::

:::{.proof title="That limsups/infs are measurable"}
Measurable sets form a sigma algebra, and these are expressed as countable unions/intersections of measurable sets.
:::

:::{.theorem title="Borel-Cantelli"}
Let $\{E_{k}\}$ be a countable collection of measurable sets.
Then
$$
\sum_{k} m(E_{k}) < \infty \implies \text{ almost every } x\in \RR \text{ is in at most finitely many } E_{k}
.$$
:::

:::{.proof title="of Borel-Cantelli"}
\envlist

- If $E = \limsup_{j} E_{j}$ with $\sum m(E_{j}) < \infty$ then $m(E) = 0$.
- If $E_{j}$ are measurable, then $\limsup_{j} E_{j}$ is measurable.
- If $\sum_{j} m(E_{j}) < \infty$, then $\sum_{j=N}^\infty m(E_{j}) \converges{N\to\infty}\to 0$ as the tail of a convergent sequence.
- $E = \limsup_{j} E_{j} = \intersect_{k=1}^\infty \union_{j=k}^\infty E_{j} \implies E \subseteq \union_{j=k}^\infty$ for all $k$
- $E \subset \union_{j=k}^\infty \implies m(E) \leq \sum_{j=k}^\infty m(E_{j}) \converges{k\to\infty}\to 0$.
:::

:::{.proposition title="Extending the class of measurable functions."}

- Characteristic functions are measurable
- If $f_{n}$ are measurable, so are $\abs{f_{n}}, \limsup f_{n}, \liminf f_{n}, \lim f_{n}$, 
- Sums and differences of measurable functions are measurable, 
- Cones $F(x,y) = f(x)$ are measurable, 
- Compositions $f\circ T$ for $T$ a linear transformation are measurable,
- "Convolution-ish" transformations $(x,y) \mapsto f(x-y)$ are measurable
:::

:::{.proof title="Convolution"}
Take the cone on $f$ to get $F(x, y) = f(x)$, then compose $F$ with the linear transformation $T = [1, -1; 1, 0]$.
:::


:::{.definition title="$\sigma\dash$finiteness"}
A measure space $(X, \mcm, \mu)$ is **$\sigma\dash$finite** if $X$ can be written as a union of countably many measurable sets with finite measure.
:::


:::{.proposition title="Regularity of measure"}
If $(X, \mcb, \mu)$ is a Borel measure space where $\mu$ is finite on all balls of finite radius, then for any $E \in \mcb$ and any $\eps>0$,

- There exists an open set $O$  with $E \subset O$ and $\mu(O\sm E) < \eps$
- There exists a closed set $F$ with $F\subset E$ and $\mu(E\sm F) < \eps$.

:::

:::{.problem title="?"}
Show that $E$ is measurable iff $E$ is regular in either sense above.
:::

## Exercises


:::{.problem title="?"}
Show that if $\sum \mu(E_k) < \infty$ then almost every $x\in X$ is in at most finitely many $E_k$.
:::


asdasds


