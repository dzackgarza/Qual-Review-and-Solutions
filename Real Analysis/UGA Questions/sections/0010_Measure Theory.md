# Measure Theory: Sets

## Spring 2020 # 2 $\done$

Let $m_*$ denote the Lebesgue outer measure on \( \RR \).

### a. 
Prove that for every $E\subseteq \RR$ there exists a Borel set $B$ containing $E$ such that
\[
m_*(B) = m_*(E)
.\]

### b. 
Prove that if $E\subseteq \RR$ has the property that
\[
m_*(A) = m_*(A\intersect E) + m_*(A\intersect E^c)
\]
for every set $A\subseteq \RR$, then there exists a Borel set $B\subseteq \RR$ such that $E = B\setminus N$ with $m_*(N) = 0$.

Be sure to address the case when $m_*(E) = \infty$.

:::{.solution}
\hfill
:::{.concept}
\hfill
- Definition of outer measure: 
  \[ 
  m_*(E) = \inf_{\theset{Q_j} \covers E} \sum \abs {Q_j}
  \] 
  where $\theset{Q_j}$ is a countable collection of closed cubes.
- Break $\RR$ into $\disjoint_{n\in \ZZ} [n, n+1)$, each with finite measure.
- Theorem: $m_*(Q) = \abs{Q}$ for $Q$ a closed cube (i.e. the outer measure equals the volume).
:::


:::{.proof}
\hfill
- $m_*(Q) \leq \abs{Q}$:
- Since $Q\subseteq Q$, $Q\covers Q$ and $m_*(Q) \leq \abs{Q}$ since $m_*$ is an infimum over such coverings.
- $\abs{Q} \leq m_*(Q)$:
- Fix $\eps > 0$.
- Let $\theset{Q_i}_{i=1}^\infty \covers Q$ be arbitrary, it suffices to show that 
    $$\abs{Q} \leq \qty{\sum_{i=1}^\infty \abs{Q_i}} + \eps.$$
-  Pick open cubes $S_i$ such that $Q_i\subseteq S_i$ and $\abs{Q_i} \leq \abs{S_i} \leq (1+\eps)\abs{Q_i}$.
- Then $\theset{S_i} \covers Q$, so by compactness of $Q$ pick a finite subcover with $N$ elements.

- Note 
\[
Q \subseteq \union_{i=1}^N S_i \implies \abs{Q} \leq \sum_{i=1}^N \abs{S_i} \leq \sum_{i=1}^N (1+\eps) \abs{Q_j} \leq (1+\eps)\sum_{i=1}^\infty \abs{Q_i } 
.\]
- Taking an infimum over coverings on the RHS preserves the inequality, so 
  $$\abs{Q} \leq (1+\eps) m_*(Q)$$
- Take $\eps\to 0$ to obtain final inequality.
:::

### a

- If $m_*(E) = \infty$, then take $B = \RR^n$ since $m(\RR^n) = \infty$.
- Suppose $N \definedas m_*(E) < \infty$.

- Since $m_*(E)$ is an infimum, by definition, for every $\eps> 0$ there exists a covering by closed cubes $\theset{Q_i(\eps)}_{i=1}^\infty \covers E$ depending on $\eps$ such that 
$$
\sum_{i=1}^\infty \abs{Q_i(\eps)} < N + \eps
.$$

- For each fixed $n$, set $\eps_n = {1\over n}$ to produce such a covering $\theset{Q_i(\eps_n)}_{i=1}^\infty$ and set $B_n \definedas \union_{i=1}^\infty Q_i(\eps_n)$.

- The outer measure of cubes is *equal* to the sum of their volumes, so 
\[
m_*(B_n) = \sum_{i=1}^\infty \abs{Q_i(\eps_n)} < N + \eps_n = N + {1\over n}
.\]

- Now set $B \definedas \intersect_{n=1}^\infty B_n$.

  - Since $E\subseteq B_n$ for every $n$, $E\subseteq B$
  - Since $B$ is a countable intersection of countable unions of closed sets, $B$ is Borel.
  - Since $B_n \subseteq B$ for every $n$, we can apply subadditivity to obtain the inequality
  \[
  E \subseteq B \subseteq B_n \implies
  N \leq m_*(B) \leq m_*(B_n) < N + {1\over n} \qtext{for all} n\in \ZZ^{\geq 1}
  .\]

- This forces $m_*(E) = m_*(B)$.


### b

Suppose $m_*(E) < \infty$.

- By (a), find a Borel set $B\supseteq E$ such that $m_*(B) = m_*(E)$
- Note that $E\subseteq B \implies B\intersect E = E$ and $B\intersect E^c = B\setminus E$.
- By assumption, 
\[
m_*(B) &= m_*(B\intersect E) + m_*(B\intersect E^c) \\
m_*(E) &= m_*(E) + m_*(B\setminus E) \\ 
m_*(E) - m_*(E) &= m_*(B\setminus E) \qquad\qquad\text{since } m_*(E) < \infty \\ 
\implies m_*(B\setminus E) &= 0
.\]
- So take $N = B\setminus E$; this shows $m_*(N) = 0$ and $E = B\setminus (B\setminus E) = B\setminus N$.


If $m_*(E) = \infty$:

- Apply result to $E_R\definedas E \intersect [R, R+1)^n \subset \RR^n$ for $R\in \ZZ$, so $E = \disjoint_R E_R$
- Obtain $B_R, N_R$ such that $E_R = B_R \setminus N_R$, $m_*(E_R) = m_*(B_R)$, and $m_*(N_R) = 0$.
- Note that
  -   $B\definedas \union_R B_R$ is a union of Borel sets and thus still Borel
  -  $E = \union_R E_R$
  - $N\definedas B\setminus E$
  - $N' \definedas \union_R N_R$ is a union of null sets and thus still null
- Since $E_R \subset B_R$ for every $R$, we have $E\subset B$
- We can compute
\[
N = B\setminus E = \qty{ \union_R B_R } \setminus \qty{\union_R E_R } \subseteq \union_R \qty{B_R\setminus E_R} = \union_R N_R \definedas N'
\]
where $m_*(N') = 0$ since $N'$ is null, and thus subadditivity forces $m_*(N) = 0$.
:::

## Fall 2019 # 3. $\done$
Let $(X, \mathcal B, µ)$ be a measure space with $µ(X) = 1$ and $\{B_n\}_{n=1}^\infty$ be a sequence of $\mathcal B$-measurable subsets of $X$, and
$$
B \definedas \theset{x\in X \suchthat x\in B_n \text{ for infinitely many } n}.
$$

a. Argue that $B$ is also a $\mathcal{B} \dash$measurable subset of $X$.

b. Prove that if $\sum_{n=1}^\infty \mu(B_n) < \infty$ then $\mu(B)= 0$.

c. Prove that if  $\sum_{n=1}^\infty \mu(B_n) = \infty$ **and** the sequence of set complements $\theset{B_n^c}_{n=1}^\infty$ satisfies
$$
\mu\left(\bigcap_{n=k}^{K} B_{n}^{c}\right)=\prod_{n=k}^{K}\left(1-\mu\left(B_{n}\right)\right)
$$
for all positive integers $k$ and $K$ with $k < K$, then $µ(B) = 1$.

> Hint: Use the fact that $1 - x ≤ e^{-x}$ for all $x$.

:::{.solution}
\hfill
:::{.concept}
\hfill
- Borel-Cantelli: for a sequence of sets $X_n$, 
\[
\limsup_n X_n &= \theset{x \suchthat x\in X_n \text{ for infinitely many $n$} } 
&= \intersect_{m\in \NN} \union_{n\geq m} X_n
\\
\liminf_n X_n &= \theset{x \suchthat x\in X_n \text{ for all but finitely many $n$} }
&= \union_{m\in \NN} \intersect_{n\geq m} X_n
.\]

- Properties of logs and exponentials:
\[
\prod_n e^{x_n} = e^{\Sigma_n x_n} \quad\text{and} \quad \sum_n \log(x_n) = \log\left(\prod_n x_n\right)
.\]

- Tails of convergent sums vanish.
-  Continuity of measure: $B_n \searrow B$ and $\mu(B_0)<\infty$ implies $\lim_n \mu(B_n) = \mu(B)$, and $B_n\nearrow B \implies \lim_n \mu(B_n) = \mu(B)$.

:::

### a

- The Borel $\sigma\dash$algebra is closed under countable unions/intersections/complements, 
- $B = \limsup_n B_n$ is an intersection of unions of measurable sets.

### b

- Tails of convergent sums go to zero, so $\sum_{n\geq M} \mu(B_n) \mapsvia{M\to\infty} 0$, 
- $B_M \definedas \intersect_{m = 1}^M \union_{n\geq m} B_n \searrow B$.

\[
\mu(B_M) 
&= \mu\left(\intersect_{m\in \NN} \union_{n\geq m} B_n\right) \\
&\leq \mu\left( \union_{n\geq m} B_n \right) \quad \text{for all } m\in \NN \text{ by countable subadditivity} \\ 
&\to 0
,\]

- The result follows by continuity of measure.

### c

- To show $\mu(B) = 1$, we'll show $\mu(B^c) = 0$.

- Let $B_k = \intersect_{m=1}^\infty \union_{n = m}^K B_n$. Then
\[
\mu(B_K^c) 
&= \mu \left(\union_{m=1}^\infty \intersect_{n=m}^K B_n^c\right) \\
&\leq \sum_{m=1}^\infty \mu\left( \intersect_{n=m}^K B_n^c \right) \quad\text{ by subadditivity} \\
&= \sum_{m=1}^\infty \prod_{n=m}^K \qty{1 - \mu(B_n)} \quad \text{by assumption} \\ 
&\leq \sum_{m=1}^\infty \prod_{n=m}^K e^{-\mu(B_n^c)} \quad\text{by hint} \\
&= \sum_{m=1}^\infty \exp{-\sum_{n=m}^K \mu(B_n^c)} \\
&\converges{K\to\infty}\to 0
\]
  since $\displaystyle\sum_{n=m}^K \mu(B_n^c) \converges{K\to\infty}\to \infty$ by assumption 

- We can apply continuity of measure since $B_K^c \mapsvia{K\to\infty} B^c$.

\todo[inline]{How to prove the hint..?}
:::

## Spring 2019 # 2 $\done$
Let $\mathcal B$ denote the set of all Borel subsets of $\RR$ and $\mu : \mathcal B → [0, \infty)$ denote a finite Borel measure on $\RR$.
  
### a 
Prove that if $\{F_k\}$ is a sequence of Borel sets for which $F_k \supseteq  F_{k+1}$ for all $k$, then
\[
\lim _{k \rightarrow \infty} \mu\left(F_{k}\right)=\mu\left(\bigcap_{k=1}^{\infty} F_{k}\right)
\]

### b 
Suppose $µ$ has the property that $µ(E) = 0$ for every $E \in \mathcal B$ with Lebesgue measure $m(E) = 0$.

Prove that for every $ε > 0$ there exists $δ > 0$ so that if $E \in \mathcal B$ with $m(E) < δ$, then $µ(E) < ε$.

\todo[inline]{Add concepts.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- ?
:::

### a

> See Folland p.26

- Lemma 1: $\mu(\disjoint_{k=1}^\infty E_k) = \lim_{N\to\infty} \sum_{k=1}^N \mu(E_k)$.

- Suppose $F_0 \supseteq F_1 \supseteq \cdots$.
- Let $A_k = F_k \setminus F_{k+1}$, since the $F_k$ are nested the $A_k$ are disjoint
- Set $A \definedas \disjoint_{k=1}^\infty A_k$ and $F \definedas \intersect_{k=1}^\infty F_k$.
- Note $X = X\setminus Y ~\disjoint~ X\intersect Y$ for any two sets (just write $X\setminus Y \definedas X\intersect  Y^c$)
- Note that $A$ contains anything that was removed from $F_0$ when passing from any $F_j$ to $F_{j+1}$, while $F$ contains everything that is never removed at any stage, and these are disjoint possibilities.
- Thus $F_0 = F \disjoint A$, so 
\[
\mu(F_0) 
&= \mu(F) + \mu(A) \\
&= \mu(F) + \mu(\disjoint_{k=1}^\infty A_k) \\
&= \mu(F) + \lim_{n\to\infty} \sum_{k=0}^n \mu(A_k) \quad \text{by countable additivity}\\
&= \mu(F) + \lim_{n\to\infty} \sum_{k=0}^n \mu(F_k) - \mu(F_{k+1}) \\
&= \mu(F) + \lim_{n\to\infty} \left( \mu(F_1) - \mu(F_n) \right) \quad\text{(Telescoping)} \\
&=\mu(F) + \mu(F_1) - \lim_{N\to\infty} \mu(F_n)
,\]

- Since $\mu$ is a finite measure, $\mu(F_1) < \infty$ and can be subtracted, yielding
\[
\mu(F_1) &= \mu(F) + \mu(F_1) - \lim_{n\to\infty} \mu(F_n) \\
\implies \mu(F) &= \lim_{n\to\infty} \mu(F_n) \\
\implies \mu\qty{\intersect_{k=1}^\infty F_k} &= \lim_{n\to\infty} \mu(F_n)
.\]

### b

- Toward a contradiction, negate the implication: suppose there exists an $\eps>0$ such that for all $\delta$, we have $m(E) < \delta$ but $\mu(E) > \eps$.
- The sequence $\theset{\delta_n \definedas {1\over 2^n}}_{n\in \NN}$ and produce sets $A_n\in \mcb$ such $m(A_n) < {1\over 2^n}$ but $\mu(A_n) > \varepsilon$.
- Define
\[
F_n &\definedas \union_{j\geq n} A_j \\
C_m &\definedas \intersect_{k=1}^m F_k \\
A &\definedas C_\infty \definedas \intersect_{k=1}^\infty F_k 
.\]

- Note that $F_1 \supseteq F_2 \supseteq \cdots$, since each increase in index unions fewer sets.
- By continuity for the Lebesgue measure, 
\[
m(A) 
= m \qty{\intersect_{k=1}^\infty F_k }
= \lim_{k\to \infty} m (F_k) 
= \lim_{k\to\infty} m\qty{\union_{j\geq k} A_j } 
\leq \lim_{k\to\infty} \sum_{j\geq k} m(A_j) 
= \lim_{k\to\infty} \sum_{j\geq k} {1\over 2^n} 
= 0
,\]
  which follows because this is the tail of a convergent sum

- Thus $m(A) = 0$ and by assumption, this implies $\mu(A) = 0$.

- However, by part (a),
\[
\mu(A) = \lim_n \mu\left( \union_{k=n}^\infty A_k \right)
\geq \lim_n \mu(A_n) = \lim_n \varepsilon = \varepsilon > 0
.\]
:::
\todo[inline]{All messed up!}

## Fall 2018 # 2 $\done$
Let $E\subset \RR$ be a Lebesgue measurable set.
Show that there is a Borel set $B \subset E$ such that $m(E\setminus B) = 0$.

\todo[inline]{Move this to review notes to clean things up.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- Definition of measurability: there exists an open $O\supset E$ such that $m_*(O\setminus E) < \eps$ for all $\eps> 0$.
- Theorem: $E$ is Lebesgue measurable iff there exists a closed set $F\subseteq E$ such that $m_*(E\setminus F) < \eps$ for all $\eps>0$.
- Every $F_\sigma, G_\delta$ is Borel.
- Claim: $E$ is measurable $\iff$ for every $\varepsilon$ there exist $F_\varepsilon \subset E \subset G_\varepsilon$ with $F_\varepsilon$ closed and $G_\varepsilon$ open and $m(G_\varepsilon \setminus E)< \varepsilon$ and $m(E\setminus F_\varepsilon) < \varepsilon$.
  - Proof: existence of $G_\eps$ is the definition of measurability.
  - Existence of $F_\eps$: ?

- Claim: $E$ is measurable $\implies$ there exists an open $O\supseteq E$ such that $m(O\setminus E) = 0$.
  - Since $E$ is measurable, for each $n\in \NN$ choose $G_n \supseteq E$ such that $m_*(G_n\setminus E) < {1\over n}$.
  - Set $O_N \definedas \intersect_{n=1}^N G_n$ and $O\definedas \intersect_{n=1}^\infty G_n$.
  - Suppose $E$ is bounded.
    - Note $O_N \searrow O$ and $m_*(O_1) < \infty$ if $E$ is bounded, since in this case
    \[
    m_*(G_n\setminus E) = m_*(G_1) - m_*(E) < 1 \iff m_*(G_1) < m_*(E) + {1\over n} < \infty
    .\]
    - Note $O_N \setminus E \searrow O \setminus E$ since $O_N\setminus E \definedas O_N \intersect E^c \supseteq O_{N+1} \intersect E^c$ for all $N$, and again $m_*(O_1 \setminus E) < \infty$.
    - So it's valid to apply continuity of measure from above:
\[
m_*(O\setminus E) 
&= \lim_{N\to\infty} m_*(O_N\setminus E) \\ 
&\leq \lim_{N\to \infty} m_*(G_N\setminus E) \\ 
&= \lim_{N\to\infty} {1\over N} = 0
,\]
      where the inequality uses subadditivity on $\intersect_{n=1}^N G_n \subseteq G_N$
  - Suppose $E$ is unbounded.
    - Write $E^k = E \intersect [k, k+1]^d \subset \RR^d$ as the intersection of $E$ with an annulus, and note that $E = \disjoint_{k\in \NN} E_k$.
    - Each $E_k$ is bounded, so apply the previous case to obtain $O_k \supseteq E_k$ with $m(O_k\setminus E_k) = 0$.
    - So write $O_k = E_k \disjoint N_k$ where $N_k \definedas O_k \setminus E_k$ is a null set.
    - Define $O = \union_{k\in \NN} O_k$, note that $E\subseteq O$.
    - Now note
\[
O\setminus E 
&= \qty{\disjoint_k O_k}\setminus \qty{\disjoint_K E_k} \\
&\subseteq \disjoint_k \qty{O_k \setminus E_k} \\
\implies m_*(O\setminus E) 
&\leq m_*\qty{\disjoint \qty{O_k \setminus E_k} } = 0
,\]
  since any countable union of null sets is again null.
  - So $O\supseteq E$ with $m(O\setminus E) = 0$.
- Theorem: since $E$ is measurable, $E^c$ is measurable
  - Proof: It suffices to write $E^c$ as the union of two measurable sets, $E^c = S \union (E^c - S)$, where $S$ is to be determined.
  - We'll produce an $S$ such that $m_*(E^c - S) = 0$ and use the fact that any subset of a null set is measurable.
  - Since $E$ is measurable, for every $\eps > 0$ there exists an open $\OO_\eps \supseteq E$ such that $m_*(\OO_\eps \setminus E) < \eps$.
  - Take the sequence $\theset{\eps_n \definedas {1\over n}}$ to produce a sequence of sets $\OO_n$.
  - Note that each $\OO_n^c$ is closed and 
  \[
  \OO_n \supseteq E \iff \OO_n^c \subseteq E^c
  .\]
  - Set $S \definedas \union_n \OO_n^c$, which is a union of closed sets, thus an $F_\sigma$ set, thus Borel, thus measurable.
  - Note that $S\subseteq E^c$ since each $\OO_n \subseteq E^c$.
  - Note that
  \[
  E^c\setminus S 
  &\definedas E^c \setminus \qty{\union_{n=1}^\infty \OO_n^c} \\
&\definedas E^c \intersect \qty{\union_{n=1}^\infty \OO_n^c}^c  \quad\text{definition of set minus} \\ 
  &= E^c \intersect \qty{\intersect_{n=1}^\infty \OO_n}^c  \quad \text{De Morgan's law}\\
  &= E^c \union \qty{\intersect_{n=1}^\infty \OO_n}  \\
  &\definedas \qty{ \intersect_{n=1}^\infty \OO_n} \setminus E \\
  & \subseteq \OO_N \setminus E \quad \text{for every } N\in \NN
  .\]
  - Then by subadditivity,
    $$
    m_*(E^c\setminus S) \leq m_*(\OO_N \setminus E) \leq {1\over N} \quad \forall N \implies m_*(E^c\setminus S) = 0
    .$$
  - Thus $E^c\setminus S$ is measurable.
:::
  
### Indirect Proof

- Since $E$ is measurable, $E^c$ is measurable.
- Since $E^c$ is measurable exists an open $O\supseteq E^c$ such that $m(O\setminus E^c) = 0$.
- Set $B \definedas O^c$, then $O\supseteq E^c \iff \OO^c \subseteq E \iff B\subseteq E$.
- Computing measures yields 
\[
E\setminus B \definedas E\setminus  \OO^c \definedas E\intersect (\OO^c)^c = E\intersect \OO = \OO \intersect(E^c)^c \definedas \OO \setminus E^c
,\]
  thus $m(E\setminus B) = m(\OO\setminus E^c) = 0$.
- Since $\OO$ is open, $B$ is closed and thus Borel.

### Direct Proof (Todo)

\todo[inline]{Try to construct the set.}
:::

## Spring 2018 # 1 $\done$
Define
$$
E:=\left\{x \in \mathbb{R}:\left|x-\frac{p}{q}\right|<q^{-3} \text { for infinitely many } p, q \in \mathbb{N}\right\}.
$$

Prove that $m(E) = 0$.

:::{.solution}
\hfill
:::{.concept}
\hfill
- Borel-Cantelli: If $\theset{E_k}_{k\in\ZZ}\subset 2^\RR$ is a countable collection of Lebesgue measurable sets with $\sum_{k\in \ZZ} m(E_k) < \infty$, then almost every $x\in \RR$ is in *at most finitely* many $E_k$.
  - Equivalently (?), $m(\limsup_{k\to\infty} E_k) = 0$, where $\limsup_{k\to\infty} E_k = \intersect_{k=1}^\infty \union_{j\geq k} E_j$, the elements which are in $E_k$ for infinitely many $k$.
:::

- Strategy: Borel-Cantelli.

- We'll show that $m(E) \intersect [n, n+1] = 0$ for all $n\in \ZZ$; then the result follows from 
\[
m(E) = m \qty{\union_{n\in \ZZ} E \intersect [n, n+1]} \leq \sum_{n=1}^\infty m(E \intersect [n, n+1]) = 0
.\]

- By translation invariance of measure, it suffices to show $m(E \intersect [0, 1]) = 0$.
  - So WLOG, replace $E$ with $E\intersect [0, 1]$.

- Define
\[
E_j \definedas \theset{x\in [0, 1] \suchthat \
\exists p\in \ZZ^{\geq 0} \text{ s.t. } \abs{x - \frac{p}{j} } < \frac 1 {j^3}} 
.\]

  - Note that $E_j \subseteq \disjoint_{p\in \ZZ^{\geq 0}} B_{j^{-3}}\qty{p\over j}$, i.e. a union over integers $p$ of intervals of radius $1/j^3$ around the points $p/j$.
    Since $1/j^3 < 1/j$, this union is in fact disjoint.

- Importantly, note that 
  \[
\limsup_{j\to\infty} E_j \definedas \intersect_{n=1}^\infty \union_{j=n}^\infty E_j = E
  \]
  
  since 
  
  \[
  x \in \limsup_j E_j 
  &\iff x \in E_j \text{ for infinitely many } j  \\
  &\iff \text{ there are infinitely many $j$ for which there exist a $p$ such that } \abs{x - {p\over j}} < j^{-3}  \\
  &\iff \text{ there are infinitely many such pairs $p, j$}  \\
  &\iff x\in E
  .\]

- Intersecting with $[0, 1]$, we can write $E_j$ as a union of intervals:
\[
E_j =& \qty{0, {j^{-3}}} 
\quad \disjoint \quad 
B_{j^{-3}}\qty{1\over j} \disjoint
B_{j^{-3}}\qty{2\over j} \disjoint
\cdots \disjoint
B_{j^{-3}}\qty{j-1\over j} 
\quad \disjoint \quad 
(1 - {j^{-3}}, 1)
,\]
  where we've separated out the "boundary" terms to emphasize that they are balls about $0$ and $1$ intersected with $[0, 1]$.


- Since $E_j$ is a union of open sets, it is Borel and thus Lebesgue measurable.

- Computing the measure of $E_j$:

  - For a fixed $j$, there are exactly $j+1$ possible choices for a numerator ($0, 1, \cdots, j$), thus there are exactly $j+1$ sets appearing in the above decomposition.

  - The first and last intervals are length $1 \over j^3$ 
  - The remaining $(j+1)-2 = j-1$ intervals are twice this length, $2 \over j^3$
  - Thus
  $$
  m(E_j) = 2 \qty{1 \over j^3} + (j-1) \qty{2 \over j^3} = {2 \over j^2}
  $$

- Note that 
\[
\sum_{j\in \NN} m(E_j) =  2\sum_{j\in \NN} \frac 1 {j^2} < \infty
,\]
  which converges by the $p\dash$test for sums.
  
- But then
\[
m(E) 
&= m(\limsup_j E_j) \\
&= m(\intersect_{n\in \NN} \union_{j\geq n} E_j) \\
&\leq m(\union_{j\geq N} E_j) \quad\text{for every } N \\
&\leq \sum_{j\geq N} m(E_j) \\
&\converges{N\to\infty}\to 0 \quad\text{}
.\]

- Thus $E$ is measurable as a subset of a null set and $m(E) = 0$.
:::

## Fall 2017 # 2 $\done$
Let $f(x) = x^2$ and $E \subset [0, \infty) \definedas \RR^+$.

1. Show that
\[
m^*(E) = 0 \iff m^*(f(E)) = 0.
\]

2. Deduce that the map

\[
\phi: \mathcal{L}(\RR^+) &\to \mathcal{L}(\RR^+) \\
E &\mapsto f(E)
\]
  is a bijection from the class of Lebesgue measurable sets of $[0, \infty)$ to itself.

\todo[inline]{Walk through.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- ?
:::

### a

It suffices to consider the bounded case, i.e. $E \subseteq B_M(0)$ for some $M$.
Then write $E_n = B_n(0) \intersect E$ and apply the theorem to $E_n$, and by subadditivity, $m^*(E) = m^*(\union_n E_n) \leq \sum_n m^*(E_n) = 0$.

**Lemma:** 
$f(x) = x^2, f\inv(x) = \sqrt{x}$ are Lipschitz on any compact subset of $[0, \infty)$.
 
*Proof:*
Let $g = f$ or $f\inv$. 
Then $g\in C^1([0, M])$ for any $M$, so $g$ is differentiable and $g'$ is continuous.
Since $g'$ is continuous on a compact interval, it is bounded, so $\abs{g'(x)} \leq L$ for all $x$.
Applying the MVT,
\[
\abs{f(x) - f(y)} = f'(c) \abs{x-y} \leq L \abs{x-y}
.\]
  
**Lemma:** 
If $g$ is Lipschitz on $\RR^n$, then $m(E) = 0 \implies m(g(E)) = 0$.

*Proof:*
If $g$ is Lipschitz, then 
$$
g(B_r(x)) \subseteq B_{Lr}(x)
,$$ 
which is a dilated ball/cube, and so 
$$
m^*(B_{Lr}(x)) \leq L^n \cdot m^*(B_{r}(x))
.$$

Now choose $\theset{Q_j} \rightrightarrows E$; then $\theset{g(Q_j)} \rightrightarrows g(E)$.

By the above observation,
\[
\abs{g(Q_j)} \leq L^n \abs{Q_j}
,\]

and so 
\[
m^*(g(E)) \leq \sum_j \abs{g(Q_j)} \leq \sum_j L^n \abs{Q_j} = L^n \sum_j \abs{Q_j} \to 0 
.\]

Now just take $g(x) = x^2$ for one direction, and $g(x) = f\inv(x) = \sqrt{x}$ for the other.
$\qed$

### b

> Lemma: $E$ is measurable iff $E = K \disjoint N$ for some $K$ compact, $N$ null.

Write $E = K \disjoint N$ where $K$ is compact and $N$ is null.

Then $\phi\inv(E) = \phi\inv(K \disjoint N) = \phi\inv(K) \disjoint \phi\inv(N)$.

Since $\phi\inv(N)$ is null by part (a) and $\phi\inv(K)$ is the preimage of a compact set under a continuous map and thus compact, $\phi\inv(E) = K' \disjoint N'$ where $K'$ is compact and $N'$ is null, so $\phi\inv(E)$ is measurable.

So $\phi$ is a measurable function, and thus yields a well-defined map $\mathcal L(\RR) \to \mathcal L(\RR)$ since it preserves measurable sets.
Restricting to $[0, \infty)$, $f$ is bijection, and thus so is $\phi$.
:::

## Spring 2017 # 2 $\done$

### a 
Let $\mu$ be a measure on a measurable space $(X, \mathcal M)$ and $f$ a positive measurable function.
  
  Define a measure $\lambda$ by
\[
\lambda(E):=\int_{E} f ~d \mu, \quad E \in \mathcal{M}
\]

Show that for $g$ any positive measurable function, 
\[
\int_{X} g ~d \lambda=\int_{X} f g ~d \mu
\]

### b 
Let $E \subset \RR$ be a measurable set such that 
\[
\int_{E} x^{2} ~d m=0.
\]
Show that $m(E) = 0$.

:::{.solution}
\hfill
:::{.concept}
\hfill
- Absolute continuity of measures: $\lambda \ll \mu \iff E\in\mathcal{M}, \mu(E) = 0 \implies \lambda(E) = 0$.
- Radon-Nikodym: if $\lambda \ll \mu$, then there exists a measurable function $\dd{\lambda}{\mu} \definedas f$ where $\lambda(E) = \int_E f \,d\mu$.
- Chebyshev's inequality:
\[  
A_c \definedas \theset{ x\in X \suchthat \abs{f(x)} \geq c  } \implies \mu(A_c) \leq c^{-p} \int_{A_c} \abs{f}^p \,d\mu \quad \forall 0 < p < \infty
.\]
:::

### a

- Strategy: use approximation by simple functions to show absolute continuity and apply Radon-Nikodym 

- Claim: $\lambda \ll \mu$, i.e. $\mu(E) = 0 \implies \lambda(E) = 0$.

  - Note that if this holds, by Radon-Nikodym, $f = \dd{\lambda}{\mu} \implies d\lambda = f d\mu$, which would yield 
  \[  
  \int g ~d\lambda = \int g f ~d\mu
  .\]

- So let $E$ be measurable and suppose $\mu(E) = 0$.

- Then
\[
\lambda(E) \definedas \int_E f ~d\mu 
&= \lim_{n\to\infty} \theset{\int_E s_n \,d\mu \suchthat s_n \definedas \sum_{j=1}^\infty c_j \mu(E_j),\, s_n \nearrow f}
\]
  where we take a sequence of simple functions increasing to $f$.

- But since each $E_j \subseteq E$, we must have $\mu(E_j) = 0$ for any such $E_j$, so every such $s_n$ must be zero and thus $\lambda(E) = 0$.

\todo[inline]{What is the final step in this approximation?}

### b

- Set $g(x) = x^2$, note that $g$ is positive and measurable.
- By part (a), there exists a positive $f$ such that for any $E\subseteq \RR$,
\[
\int_E g ~dm = \int_E gf ~d\mu 
\]

  - The LHS is zero by assumption and thus so is the RHS.

  - $m \ll \mu$ by construction.

  - Note that $gf$ is positive.

- Define $A_k = \theset{x\in X \suchthat gf \cdot \chi_E > {1 \over k} }$, for $k\in \ZZ^{\geq 0}$

- Then by Chebyshev with $p=1$, for every $k$ we have

\[
\mu(A_k) \leq k \int_E gf ~d\mu = 0
\]

- Then noting that $A_k \searrow A \definedas \theset{x\in X \suchthat gf\cdot \chi_E(x)  > 0}$, we have $\mu(A) = 0$.

- Since $gf$ is positive, we have 
\[
x\in E \iff gf\chi_E(x) > 0 \iff x\in A
\]
  so $E = A$ and $\mu(E) = \mu(A)$.

- But $m \ll \mu$ and $\mu(E) = 0$, so we can conclude that $m(E) = 0$.
:::

## Fall 2016 # 4 $\done$
Let $(X, \mathcal M, \mu)$ be a measure space and suppose $\theset{E_n} \subset \mathcal M$ satisfies
\[
\lim _{n \rightarrow \infty} \mu\left(X \backslash E_{n}\right)=0.
\]

Define
\[
G \definedas \theset{x\in X \suchthat x\in E_n \text{ for only finitely many  } n}.
\]

Show that $G \in \mathcal M$ and $\mu(G) = 0$.

\todo[inline]{Add concepts.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- ?
:::

- Claim: $G\in \mcm$.
  - Claim:
  \[  
  G = \qty{ \intersect_{N=1}^\infty \union_{n=N}^\infty E_n}^c = \union_{N=1}^\infty \intersect_{n=N}^\infty E_n^c
  .\]

    - This follows because $x$ is in the RHS $\iff$ $x\in E_n^c$ for all but finitely many $n$ $\iff$ $x\in E_n$ for at most finitely many $n$.

  - But $\mcm$ is a $\sigma\dash$algebra, and this shows $G$ is obtained by countable unions/intersections/complements of measurable sets, so $G\in \mcm$. 

- Claim: $\mu(G) = 0$.

  - We have
  \[  
  \mu(G)
  &= \mu\qty{\union_{N=1}^\infty \intersect_{n=N}^\infty E_n^c} \\
  &\leq \sum_{N=1}^\infty \mu \qty{\intersect_{n=N}^\infty E_n^c}  \\
  &\leq \sum_{N=1}^\infty \mu(E_M^c) \\ 
  &\definedas \sum_{N=1}^\infty \mu(X\setminus E_N) \\
  &\converges{N\to\infty}\to 0
  .\]

\todo[inline]{Last step seems wrong!}
:::

## Spring 2016 # 3 $\work$
Let $f$ be Lebesgue measurable on $\RR$ and $E \subset \RR$ be measurable such that
$$
0<A=\int_{E} f(x) d x<\infty.
$$

Show that for every $0 < t < 1$, there exists a measurable set $E_t \subset E$ such that
$$
\int_{E_{t}} f(x) d x=t A.
$$

## Spring 2016 # 5 $\work$
Let $(X, \mathcal M, \mu)$ be a measure space. For $f\in L^1(\mu)$ and $\lambda > 0$, define
$$
\phi(\lambda)=\mu(\{x \in X | f(x)>\lambda\}) 
\quad \text { and } \quad 
\psi(\lambda)=\mu(\{x \in X | f(x)<-\lambda\})
$$

Show that $\phi, \psi$ are Borel measurable and
$$
\int_{X}|f| ~d \mu=\int_{0}^{\infty}[\phi(\lambda)+\psi(\lambda)] ~d \lambda
$$

## Fall 2015 # 2 $\work$
Let $f: \RR \to \RR$ be Lebesgue measurable.

1. Show that there is a sequence of simple functions $s_n(x)$ such that $s_n(x) \to f(x)$ for all $x\in \RR$.
2. Show that there is a Borel measurable function $g$ such that $g = f$ almost everywhere.

## Spring 2015 # 3 $\work$

Let $\mu$ be a finite Borel measure on $\RR$ and $E \subset \RR$ Borel. 
Prove that the following statements are equivalent:

1. $\forall \varepsilon > 0$ there exists $G$ open and $F$ closed such that 
$$
F \subseteq E \subseteq G \quad \text{and} \quad \mu(G\setminus F) < \varepsilon.
$$
2. There exists a $V \in G_\delta$ and $H \in F_\sigma$ such that 
$$
H \subseteq E \subseteq V \quad \text{and}\quad \mu(V\setminus H) = 0
$$

## Spring 2014 # 3 $\work$
Let $f: \RR \to \RR$ and suppose
$$
\forall x\in \RR,\quad f(x) \geq \limsup _{y \rightarrow x} f(y)
$$
Prove that $f$ is Borel measurable.

## Spring 2014 # 4 $\work$
Let $(X, \mathcal M, \mu)$ be a measure space and suppose $f$ is a measurable function on $X$.
Show that
$$
\lim _{n \rightarrow \infty} \int_{X} f^{n} ~d \mu =
\begin{cases}
\infty & \text{or} \\
\mu(f\inv(1)),
\end{cases}
$$
and characterize the collection of functions of each type.

## Spring 2017 # 1 $\done$

Let $K$ be the set of numbers in $[0, 1]$ whose decimal expansions do not use the digit $4$.

> We use the convention that when a decimal number ends with 4 but all other digits are
different from 4, we replace the digit $4$ with $399\cdots$. For example, $0.8754 = 0.8753999\cdots$.

Show that $K$ is a compact, nowhere dense set without isolated points, and find the
Lebesgue measure $m(K)$.

:::{.solution}
\hfill
:::{.concept}
\hfill
- Definition: $A$ is *nowhere dense* $\iff$ every interval $I$ contains a subinterval $S \subseteq A^c$.
  - Equivalently, the interior of the closure is empty, $\qty{\bar K}^\circ = \emptyset$.
:::

Claim: **$K$ is compact**.

- It suffices to show that $K^c \definedas [0, 1]\setminus K$ is open; 
  Then $K$ will be a closed and bounded subset of $\RR$ and thus compact by Heine-Borel.

- Strategy: write $K^c$ as the union of open balls (since these form a basis for the Euclidean topology on $\RR$).
  
  - Do this by showing every point $x\in K^c$ is an interior point, i.e. $x$ admits a neighborhood $N_x$ such that $N_x \subseteq K^c$.

- Identify $K^c$ as the set of real numbers in $[0, 1]$ whose decimal expansion **does** contain a 4.
  
  - We will show that there exists a neighborhood small enough such that all points in it contain a $4$ in their decimal expansions.

- Let $x\in K^c$, suppose a 4 occurs as the $k$th digit, and write
\[  
x = 0.d_1 d_2 \cdots d_{k-1}~ 4 ~d_{k+1}\cdots 
= \qty{\sum_{j=1}^k d_j 10^{-j}} + \qty{4\cdot 10^{-k}} + \qty{\sum_{j=k+1}^\infty d_j 10^{-j}}
.\]

- Set $r_x < 10^{-k}$ and let $y \in [0, 1] \intersect B_{r_x}(x)$ be arbitrary and write 
\[  
y = \sum_{j=1}^\infty c_j 10^{-j}
.\]

- Thus $\abs{x-y} < r_x < 10^{-k}$, and the first $k$ digits of $x$ and $y$ must agree:

  - We first compute the difference:
\[  
x - y &= \sum_{i=1}^\infty d_j 10^{-j} - \sum_{i=1}^\infty c_j 10^{-j} = \sum_{i=1}^\infty \qty{d_j - c_j} 10^{-j} \\
\]
  - Thus (claim)
\[
\abs{x-y} &\leq \sum_{j=1}^\infty \abs{d_j - c_j} 10^j < 10^{-k} \iff \abs{d_j - c_j} = 0 \quad \forall j\leq k
.\]
  - Otherwise we can note that any term $\abs{d_j - c_j}\geq 1$ and there is a contribution to $\abs{x-y}$ of at least $1\cdot 10^{-j}$ for some $j < k$, whereas
\[  
j < k \iff 10^{-j} > 10^{-k}
,\]
  a contradiction.
  
- This means that for all $j \leq k$ we have $d_j = c_j$, and in particular $d_k = 4 = c_k$, so $y$ has a 4 in its decimal expansion.

- But then $K^c = \union_x B_{r_x}(x)$ is a union of open sets and thus open.


Claim: **$K$ is nowhere dense and $m(K) = 0$:**

- Strategy: Show $\qty{\bar K}^\circ = \emptyset$.
- Since $K$ is closed, $\bar K = K$, so it suffices to show that $K$ does not properly contain any interval.
- It suffices to show $m(K^c) = 1$, since this implies $m(K) = 0$ and since any interval has strictly positive measure, this will mean $K$ can not contain an interval.

- As in the construction of the Cantor set, let 

  - $K_0$ denote $[0, 1]$ with 1 interval $\left({4 \over 10}, {5 \over 10} \right)$ of length $1 \over 10$ deleted, so 
  \[m(K_0^c) = {1\over 10}.\]
  - $K_1$ denote $K_0$ with 9 intervals $\left({1 \over 100}, {5\over 100}\right), ~\left({14 \over 100}, {15 \over 100}\right), \cdots \left({94\over 100}, {95 \over 100}\right)$ of length ${1 \over 100}$ deleted, so 
  \[m(K_1^c) = {1\over 10} + {9 \over 100}.\]
  - $K_n$ denote $K_{n-1}$ with $9^{n}$ such intervals of length $1 \over 10^{n+1}$ deleted, so 
  \[m(K_n^c) = {1\over 10} + {9 \over 100} + \cdots + {9^{n} \over 10^{n+1}}.\]

- Then compute 
\[
m(K^c) 
= \sum_{j=0}^\infty {9^n \over 10^{n+1} } 
= {1\over 10} \sum_{j=0}^\infty \qty{9\over 10}^n 
= {1 \over 10} \qty{ {1 \over 1 - {9 \over 10 } } } 
= 1.
\]

Claim: **$K$ has no isolated points**:

- A point $x\in K$ is isolated iff there there is an open ball $B_r(x)$ containing $x$ such that $B_r(x) \subsetneq K^c$.
  - So every point in this ball **should** have a 4 in its decimal expansion.

- Strategy: show that if $x\in K$, every neighborhood of $x$ intersects $K$.

- Note that $m(K_n) = \left( \frac 9 {10} \right)^n \converges{n\to\infty}\to 0$ 
- Also note that we deleted open intervals, and the endpoints of these intervals are never deleted.
  - Thus endpoints of deleted intervals are elements of $K$.

- Fix $x$. Then for every $\varepsilon$, by the Archimedean property of $\RR$, choose $n$ such that $\left( \frac 9 {10} \right)^n < \varepsilon$.

- Then there is an endpoint $x_n$ of some deleted interval $I_n$ satisfying \[\abs{x - x_n} \leq  \left( \frac 9 {10} \right)^n < \eps.\]

- So every ball containing $x$ contains some endpoint of a removed interval, and thus an element of $K$.
:::

## Spring 2016 # 2 $\work$
Let $0 < \lambda < 1$ and construct a Cantor set $C_\lambda$ by successively removing middle intervals of length $\lambda$.

Prove that $m(C_\lambda) = 0$.

# Measure Theory: Functions

## Fall 2016 # 2 $\done$

Let $f, g: [a, b] \to \RR$ be measurable with
$$
\int_{a}^{b} f(x) ~d x=\int_{a}^{b} g(x) ~d x.
$$

Show that either

1. $f(x) = g(x)$ almost everywhere, or
2. There exists a measurable set $E \subset [a, b]$ such that
\[]
\int _{E} f(x) \, dx > \int _{E} g(x) \, dx
\]

\todo[inline]{Add concepts.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- ?
:::

- Suppose it is *not* the case that $f=g$ almost everywhere; then letting $A\definedas \theset{x\in [a,b] \suchthat f(x) \neq g(x)}$, we have $m(A) > 0$.
- Write 
\[  
A = A_1\disjoint A_2 \definedas \theset{f>g} \disjoint \theset{f<g}
,\]
  then $m(A_1) > 0$ or $m(A_2) > 0$ (or both).

- Wlog (by relabeling $f, g$ if necessary), suppose $m(A_1) > 0$, and take $E\definedas A_1$.

- Then on $E$, we have $f(x)>g(x)$ pointwise. 
  This is preserved by monotonicity of the integral, thus
  \[  
  f(x) > g(x) \text{ on } E \implies \int_{E} f(x)\,dx > \int_{E} g(x)\, dx 
  .\] 
:::

## Spring 2016 # 4 $\work$
Let $E \subset \RR$ be measurable with $m(E) < \infty$. 
Define
\[
f(x)=m(E \cap(E+x)).
\]

Show that

1. $f\in L^1(\RR)$.
2. $f$ is uniformly continuous.
3. $\lim _{|x| \to \infty} f(x) = 0$.

> Hint: 
\[
\chi_{E \cap(E+x)}(y)=\chi_{E}(y) \chi_{E}(y-x)
\]

