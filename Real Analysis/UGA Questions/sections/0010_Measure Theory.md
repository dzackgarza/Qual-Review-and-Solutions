# Measure Theory: Sets

## Spring 2020 # 2

Let $m_*$ denote the Lebesgue outer measure on $\RR$.

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
Concepts used:

- Definition of outer measure: $m_*(E) = \inf_{\theset{Q_j} \covers E} \sum \abs {Q_j}$ where $\theset{Q_j}$ is a countable collection of closed cubes.
- Break $\RR$ into $\disjoint_{n\in \ZZ} [n, n+1)$, each with finite measure.
- Theorem: $m_*(Q) = \abs{Q}$ for $Q$ a closed cube (i.e. the outer measure equals the volume).

Proof (of Theorem)
:   Statement: if $Q$ is a closed cube, then $m_*(Q) = \abs{Q}$, the usual volume.

    - $m_*(Q) \leq \abs{Q}$:
      - Since $Q\subseteq Q$, $Q\covers Q$ and $m_*(Q) \leq \abs{Q}$ since $m_*$ is an infimum over such coverings.
    - $\abs{Q} \leq m_*(Q)$:
      - Fix $\eps > 0$.
      - Let $\theset{Q_i}_{i=1}^\infty \covers Q$ be arbitrary, it suffices to show that 
          $$\abs{Q} \leq \qty{\sum_{i=1}^\infty \abs{Q_i}} + \eps.$$
      -  Pick open cubes $S_i$ such that $Q_i\subseteq S_i$ and $\abs{Q_i} \leq \abs{S_i} \leq (1+\eps)\abs{Q_i}$.
      - Then $\theset{S_i} \covers Q$, so by compactness of $Q$ pick a finite subcover with $N$ elements.

      - Note 
      \begin{align*}
      Q \subseteq \union_{i=1}^N S_i \implies \abs{Q} \leq \sum_{i=1}^N \abs{S_i} \leq \sum_{i=1}^N (1+\eps) \abs{Q_j} \leq (1+\eps)\sum_{i=1}^\infty \abs{Q_i } 
      .\end{align*}
      - Taking an infimum over coverings on the RHS preserves the inequality, so 
        $$\abs{Q} \leq (1+\eps) m_*(Q)$$
      - Take $\eps\to 0$ to obtain final inequality.


### a

- If $m_*(E) = \infty$, then take $B = \RR^n$ since $m(\RR^n) = \infty$.
- Suppose $N \definedas m_*(E) < \infty$.

- Since $m_*(E)$ is an infimum, by definition, for every $\eps> 0$ there exists a covering by closed cubes $\theset{Q_i(\eps)}_{i=1}^\infty \covers E$ depending on $\eps$ such that 
$$
\sum_{i=1}^\infty \abs{Q_i(\eps)} < N + \eps
.$$

- For each fixed $n$, set $\eps_n = {1\over n}$ to produce such a covering $\theset{Q_i(\eps_n)}_{i=1}^\infty$ and set $B_n \definedas \union_{i=1}^\infty Q_i(\eps_n)$.

- The outer measure of cubes is *equal* to the sum of their volumes, so 
\begin{align*}
m_*(B_n) = \sum_{i=1}^\infty \abs{Q_i(\eps_n)} < N + \eps_n = N + {1\over n}
.\end{align*}

- Now set $B \definedas \intersect_{n=1}^\infty B_n$.

  - Since $E\subseteq B_n$ for every $n$, $E\subseteq B$
  - Since $B$ is a countable intersection of countable unions of closed sets, $B$ is Borel.
  - Since $B_n \subseteq B$ for every $n$, we can apply subadditivity to obtain the inequality
  \begin{align*}
  E \subseteq B \subseteq B_n \implies
  N \leq m_*(B) \leq m_*(B_n) < N + {1\over n} \qtext{for all} n\in \ZZ^{\geq 1}
  .\end{align*}

- This forces $m_*(E) = m_*(B)$.


### b

Suppose $m_*(E) < \infty$.

- By (a), find a Borel set $B\supseteq E$ such that $m_*(B) = m_*(E)$
- Note that $E\subseteq B \implies B\intersect E = E$ and $B\intersect E^c = B\setminus E$.
- By assumption, 
\begin{align*}
m_*(B) &= m_*(B\intersect E) + m_*(B\intersect E^c) \\
m_*(E) &= m_*(E) + m_*(B\setminus E) \\ 
m_*(E) - m_*(E) &= m_*(B\setminus E) \qquad\qquad\text{since } m_*(E) < \infty \\ 
\implies m_*(B\setminus E) &= 0
.\end{align*}
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
\begin{align*}
N = B\setminus E = \qty{ \union_R B_R } \setminus \qty{\union_R E_R } \subseteq \union_R \qty{B_R\setminus E_R} = \union_R N_R \definedas N'
\end{align*}
where $m_*(N') = 0$ since $N'$ is null, and thus subadditivity forces $m_*(N) = 0$.


:::




## Fall 2019 # 3. 
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
Concepts used:

- Borel-Cantelli: for a sequence of sets $X_n$, 
\begin{align*}
\limsup_n X_n &= \theset{x \suchthat x\in X_n \text{ for infinitely many $n$} } 
&= \intersect_{m\in \NN} \union_{n\geq m} X_n
\\
\liminf_n X_n &= \theset{x \suchthat x\in X_n \text{ for all but finitely many $n$} }
&= \union_{m\in \NN} \intersect_{n\geq m} X_n
.\end{align*}

- Properties of logs and exponentials:
\begin{align*}
\prod_n e^{x_n} = e^{\Sigma_n x_n} \quad\text{and} \quad \sum_n \log(x_n) = \log\left(\prod_n x_n\right)
.\end{align*}

- Tails of convergent sums vanish.
-  Continuity of measure: $B_n \searrow B$ and $\mu(B_0)<\infty$ implies $\lim_n \mu(B_n) = \mu(B)$, and $B_n\nearrow B \implies \lim_n \mu(B_n) = \mu(B)$.

### a

- The Borel $\sigma\dash$algebra is closed under countable unions/intersections/complements, 
- $B = \limsup_n B_n$ is an intersection of unions of measurable sets.

### b

- Tails of convergent sums go to zero, so $\sum_{n\geq M} \mu(B_n) \mapsvia{M\to\infty} 0$, 
- $B_M \definedas \intersect_{m = 1}^M \union_{n\geq m} B_n \searrow B$.

\begin{align*}
\mu(B_M) 
&= \mu\left(\intersect_{m\in \NN} \union_{n\geq m} B_n\right) \\
&\leq \mu\left( \union_{n\geq m} B_n \right) \quad \text{for all } m\in \NN \text{ by countable subadditivity} \\ 
&\to 0
,\end{align*}

- The result follows by continuity of measure.

### c

- To show $\mu(B) = 1$, we'll show $\mu(B^c) = 0$.

- Let $B_k = \intersect_{m=1}^\infty \union_{n = m}^K B_n$. Then
\begin{align*}
\mu(B_K^c) 
&= \mu \left(\union_{m=1}^\infty \intersect_{n=m}^K B_n^c\right) \\
&\leq \sum_{m=1}^\infty \mu\left( \intersect_{n=m}^K B_n^c \right) \quad\text{ by subadditivity} \\
&= \sum_{m=1}^\infty \prod_{n=m}^K \qty{1 - \mu(B_n)} \quad \text{by assumption} \\ 
&\leq \sum_{m=1}^\infty \prod_{n=m}^K e^{-\mu(B_n^c)} \quad\text{by hint} \\
&= \sum_{m=1}^\infty \exp{-\sum_{n=m}^K \mu(B_n^c)} \\
&\converges{K\to\infty}\to 0
\end{align*}
  since $\displaystyle\sum_{n=m}^K \mu(B_n^c) \converges{K\to\infty}\to \infty$ by assumption 

- We can apply continuity of measure since $B_K^c \mapsvia{K\to\infty} B^c$.

> Proving the hint: ?


:::

## Spring 2019 # 2
Let $\mathcal B$ denote the set of all Borel subsets of $\RR$ and $\mu : \mathcal B → [0, \infty)$ denote a finite Borel measure on $\RR$.
  
### a 
Prove that if $\{F_k\}$ is a sequence of Borel sets for which $F_k \supseteq  F_{k+1}$ for all $k$, then
\[
\lim _{k \rightarrow \infty} \mu\left(F_{k}\right)=\mu\left(\bigcap_{k=1}^{\infty} F_{k}\right)
\]

### b 
Suppose $µ$ has the property that $µ(E) = 0$ for every $E \in \mathcal B$ with Lebesgue measure $m(E) = 0$.

Prove that for every $ε > 0$ there exists $δ > 0$ so that if $E \in \mathcal B$ with $m(E) < δ$, then $µ(E) < ε$.

:::{.solution}

### a

> See Folland p.26

- Lemma 1: $\mu(\disjoint_{k=1}^\infty E_k) = \lim_{N\to\infty} \sum_{k=1}^N \mu(E_k)$.

- Suppose $F_0 \supseteq F_1 \supseteq \cdots$.
- Let $A_k = F_k \setminus F_{k+1}$, since the $F_k$ are nested the $A_k$ are disjoint
- Set $A \definedas \disjoint_{k=1}^\infty A_k$ and $F \definedas \intersect_{k=1}^\infty F_k$.
- Note $X = X\setminus Y ~\disjoint~ X\intersect Y$ for any two sets (just write $X\setminus Y \definedas X\intersect  Y^c$)
- Note that $A$ contains anything that was removed from $F_0$ when passing from any $F_j$ to $F_{j+1}$, while $F$ contains everything that is never removed at any stage, and these are disjoint possibilities.
- Thus $F_0 = F \disjoint A$, so 
\begin{align*}
\mu(F_0) 
&= \mu(F) + \mu(A) \\
&= \mu(F) + \mu(\disjoint_{k=1}^\infty A_k) \\
&= \mu(F) + \lim_{n\to\infty} \sum_{k=0}^n \mu(A_k) \quad \text{by countable additivity}\\
&= \mu(F) + \lim_{n\to\infty} \sum_{k=0}^n \mu(F_k) - \mu(F_{k+1}) \\
&= \mu(F) + \lim_{n\to\infty} \left( \mu(F_1) - \mu(F_n) \right) \quad\text{(Telescoping)} \\
&=\mu(F) + \mu(F_1) - \lim_{N\to\infty} \mu(F_n)
,\end{align*}

- Since $\mu$ is a finite measure, $\mu(F_1) < \infty$ and can be subtracted, yielding
\begin{align*}
\mu(F_1) &= \mu(F) + \mu(F_1) - \lim_{n\to\infty} \mu(F_n) \\
\implies \mu(F) &= \lim_{n\to\infty} \mu(F_n) \\
\implies \mu\qty{\intersect_{k=1}^\infty F_k} &= \lim_{n\to\infty} \mu(F_n)
.\end{align*}

### b

- Toward a contradiction, negate the implication: suppose there exists an $\eps>0$ such that for all $\delta$, we have $m(E) < \delta$ but $\mu(E) > \eps$.
- The sequence $\theset{\delta_n \definedas {1\over 2^n}}_{n\in \NN}$ and produce sets $A_n\in \mcb$ such $m(A_n) < {1\over 2^n}$ but $\mu(A_n) > \varepsilon$.
- Define
\begin{align*}
F_n &\definedas \union_{j\geq n} A_j \\
C_m &\definedas \intersect_{k=1}^m F_k \\
A &\definedas C_\infty \definedas \intersect_{k=1}^\infty F_k 
.\end{align*}

- Note that $F_1 \supseteq F_2 \supseteq \cdots$, since each increase in index unions fewer sets.
- By continuity for the Lebesgue measure, 
\begin{align*}
m(A) 
= m \qty{\intersect_{k=1}^\infty F_k }
= \lim_{k\to \infty} m (F_k) 
= \lim_{k\to\infty} m\qty{\union_{j\geq k} A_j } 
\leq \lim_{k\to\infty} \sum_{j\geq k} m(A_j) 
= \lim_{k\to\infty} \sum_{j\geq k} {1\over 2^n} 
= 0
,\end{align*}
  which follows because this is the tail of a convergent sum

- Thus $m(A) = 0$ and by assumption, this implies $\mu(A) = 0$.

- However, by part (a),
\begin{align*}
\mu(A) = \lim_n \mu\left( \union_{k=n}^\infty A_k \right)
\geq \lim_n \mu(A_n) = \lim_n \varepsilon = \varepsilon > 0
.\end{align*}

:::
\todo{All messed up.}



## Fall 2018 # 2
Let $E\subset \RR$ be a Lebesgue measurable set.
Show that there is a Borel set $B \subset E$ such that $m(E\setminus B) = 0$.

:::{.solution}
Concepts used:

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
    \begin{align*}
    m_*(G_n\setminus E) = m_*(G_1) - m_*(E) < 1 \iff m_*(G_1) < m_*(E) + {1\over n} < \infty
    .\end{align*}
    - Note $O_N \setminus E \searrow O \setminus E$ since $O_N\setminus E \definedas O_N \intersect E^c \supseteq O_{N+1} \intersect E^c$ for all $N$, and again $m_*(O_1 \setminus E) < \infty$.
    - So it's valid to apply continuity of measure from above:
\begin{align*}
m_*(O\setminus E) 
&= \lim_{N\to\infty} m_*(O_N\setminus E) \\ 
&\leq \lim_{N\to \infty} m_*(G_N\setminus E) \\ 
&= \lim_{N\to\infty} {1\over N} = 0
,\end{align*}
      where the inequality uses subadditivity on $\intersect_{n=1}^N G_n \subseteq G_N$
  - Suppose $E$ is unbounded.
    - Write $E^k = E \intersect [k, k+1]^d \subset \RR^d$ as the intersection of $E$ with an annulus, and note that $E = \disjoint_{k\in \NN} E_k$.
    - Each $E_k$ is bounded, so apply the previous case to obtain $O_k \supseteq E_k$ with $m(O_k\setminus E_k) = 0$.
    - So write $O_k = E_k \disjoint N_k$ where $N_k \definedas O_k \setminus E_k$ is a null set.
    - Define $O = \union_{k\in \NN} O_k$, note that $E\subseteq O$.
    - Now note
\begin{align*}
O\setminus E 
&= \qty{\disjoint_k O_k}\setminus \qty{\disjoint_K E_k} \\
&\subseteq \disjoint_k \qty{O_k \setminus E_k} \\
\implies m_*(O\setminus E) 
&\leq m_*\qty{\disjoint \qty{O_k \setminus E_k} } = 0
,\end{align*}
  since any countable union of null sets is again null.
  - So $O\supseteq E$ with $m(O\setminus E) = 0$.
- Theorem: since $E$ is measurable, $E^c$ is measurable
  - Proof: It suffices to write $E^c$ as the union of two measurable sets, $E^c = S \union (E^c - S)$, where $S$ is to be determined.
  - We'll produce an $S$ such that $m_*(E^c - S) = 0$ and use the fact that any subset of a null set is measurable.
  - Since $E$ is measurable, for every $\eps > 0$ there exists an open $\OO_\eps \supseteq E$ such that $m_*(\OO_\eps \setminus E) < \eps$.
  - Take the sequence $\theset{\eps_n \definedas {1\over n}}$ to produce a sequence of sets $\OO_n$.
  - Note that each $\OO_n^c$ is closed and 
  \begin{align*}
  \OO_n \supseteq E \iff \OO_n^c \subseteq E^c
  .\end{align*}
  - Set $S \definedas \union_n \OO_n^c$, which is a union of closed sets, thus an $F_\sigma$ set, thus Borel, thus measurable.
  - Note that $S\subseteq E^c$ since each $\OO_n \subseteq E^c$.
  - Note that
  \begin{align*}
  E^c\setminus S 
  &\definedas E^c \setminus \qty{\union_{n=1}^\infty \OO_n^c} \\
&\definedas E^c \intersect \qty{\union_{n=1}^\infty \OO_n^c}^c  \quad\text{definition of set minus} \\ 
  &= E^c \intersect \qty{\intersect_{n=1}^\infty \OO_n}^c  \quad \text{De Morgan's law}\\
  &= E^c \union \qty{\intersect_{n=1}^\infty \OO_n}  \\
  &\definedas \qty{ \intersect_{n=1}^\infty \OO_n} \setminus E \\
  & \subseteq \OO_N \setminus E \quad \text{for every } N\in \NN
  .\end{align*}
  - Then by subadditivity,
    $$
    m_*(E^c\setminus S) \leq m_*(\OO_N \setminus E) \leq {1\over N} \quad \forall N \implies m_*(E^c\setminus S) = 0
    .$$
  - Thus $E^c\setminus S$ is measurable.
  
### Indirect Proof

- Since $E$ is measurable, $E^c$ is measurable.
- Since $E^c$ is measurable exists an open $O\supseteq E^c$ such that $m(O\setminus E^c) = 0$.
- Set $B \definedas O^c$, then $O\supseteq E^c \iff \OO^c \subseteq E \iff B\subseteq E$.
- Computing measures yields 
\begin{align*}
E\setminus B \definedas E\setminus  \OO^c \definedas E\intersect (\OO^c)^c = E\intersect \OO = \OO \intersect(E^c)^c \definedas \OO \setminus E^c
,\end{align*}
  thus $m(E\setminus B) = m(\OO\setminus E^c) = 0$.
- Since $\OO$ is open, $B$ is closed and thus Borel.


### Direct Proof (Todo)

? \todo[inline]{Try to construct the set.}
:::



## Spring 2018 # 1
Define
$$
E:=\left\{x \in \mathbb{R}:\left|x-\frac{p}{q}\right|<q^{-3} \text { for infinitely many } p, q \in \mathbb{N}\right\}.
$$

Prove that $m(E) = 0$.

## Fall 2017 # 2
Let $f(x) = x^2$ and $E \subset [0, \infty) \definedas \RR^+$.

1. Show that
$$
m^*(E) = 0 \iff m^*(f(E)) = 0.
$$

2. Deduce that the map

\[
\phi: \mathcal{L}(\RR^+) &\to \mathcal{L}(\RR^+) \\
E &\mapsto f(E)
\]
  is a bijection from the class of Lebesgue measurable sets of $[0, \infty)$ to itself.

## Spring 2017 # 2

a. Let $\mu$ be a measure on a measurable space $(X, \mathcal M)$ and $f$ a positive measurable function.
  
    Define a measure $\lambda$ by
$$
\lambda(E):=\int_{E} f ~d \mu, \quad E \in \mathcal{M}
$$

    Show that for $g$ any positive measurable function, 
$$
\int_{X} g ~d \lambda=\int_{X} f g ~d \mu
$$

b. Let $E \subset \RR$ be a measurable set such that 
$$
\int_{E} x^{2} ~d m=0.
$$
  Show that $m(E) = 0$.

## Fall 2016 # 4
Let $(X, \mathcal M, \mu)$ be a measure space and suppose $\theset{E_n} \subset \mathcal M$ satisfies
$$
\lim _{n \rightarrow \infty} \mu\left(X \backslash E_{n}\right)=0.
$$

Define
$$
G \definedas \theset{x\in X \suchthat x\in E_n \text{ for only finitely many  } n}.
$$

Show that $G \in \mathcal M$ and $\mu(G) = 0$.

## Spring 2016 # 3
Let $f$ be Lebesgue measurable on $\RR$ and $E \subset \RR$ be measurable such that
$$
0<A=\int_{E} f(x) d x<\infty.
$$

Show that for every $0 < t < 1$, there exists a measurable set $E_t \subset E$ such that
$$
\int_{E_{t}} f(x) d x=t A.
$$

## Spring 2016 # 5
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

## Fall 2015 # 2
Let $f: \RR \to \RR$ be Lebesgue measurable.

1. Show that there is a sequence of simple functions $s_n(x)$ such that $s_n(x) \to f(x)$ for all $x\in \RR$.
2. Show that there is a Borel measurable function $g$ such that $g = f$ almost everywhere.

## Spring 2015 # 3 

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

## Spring 2014 # 3
Let $f: \RR \to \RR$ and suppose
$$
\forall x\in \RR,\quad f(x) \geq \limsup _{y \rightarrow x} f(y)
$$
Prove that $f$ is Borel measurable.

## Spring 2014 # 4
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

## Spring 2017 # 1

Let $K$ be the set of numbers in $[0, 1]$ whose decimal expansions do not use the digit $4$.

> We use the convention that when a decimal number ends with 4 but all other digits are
different from 4, we replace the digit $4$ with $399\cdots$. For example, $0.8754 = 0.8753999\cdots$.

Show that $K$ is a compact, nowhere dense set without isolated points, and find the
Lebesgue measure $m(K)$.

## Spring 2016 # 2
Let $0 < \lambda < 1$ and construct a Cantor set $C_\lambda$ by successively removing middle intervals of length $\lambda$.

Prove that $m(C_\lambda) = 0$.

# Measure Theory: Functions

## Fall 2016 # 2

Let $f, g: [a, b] \to \RR$ be measurable with
$$
\int_{a}^{b} f(x) ~d x=\int_{a}^{b} g(x) ~d x.
$$

Show that either

1. $f(x) = g(x)$ almost everywhere, or
2. There exists a measurable set $E \subset [a, b]$ such that
$$
\int_{E} f(x) ~d x>\int_{E} g(x) ~d x
$$

## Spring 2016 # 4
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
$$
\chi_{E \cap(E+x)}(y)=\chi_{E}(y) \chi_{E}(y-x)
$$


