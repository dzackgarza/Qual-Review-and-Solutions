# Group Theory


## Fall 2019 #1

> Centralizer: 
$$
C_G(h) = Z(h) = \theset{g\in G \suchthat [g,h] = 1}
\quad\text{Centralizer}
$$
>
> Class equation: 
$$
\abs{G} = \sum_{\substack{\text{One $h$ from each } \\ \text{ conjugacy class}}} \frac{\abs{G}}{\abs{Z(h)}}
$$
> Notation:
> \[
h^g &= ghg\inv \\
h^G &= \theset{ h^g \suchthat g\in G} \quad\text{Conjugacy Class}\\
H^g &= \theset{h^g \suchthat h\in H} \\
N_G(H) &= \theset{g\in G \suchthat H^g = H} \supseteq H \quad\text{Normalizer}
.\]
>
> **Theorem 1**: $\abs{h^G} = [G: Z(h)]$
> 
> **Theorem 2**: $\abs{\theset{H^g \suchthat g\in G}} = [G: N_G(H)]$
>
> *Proof:* Let $G\actson \theset{H \suchthat H \leq G}$ by $H \mapsto gHg\inv$.
> Then the $\mathcal O_H$ is the set of conjugate subgroups, $\mathrm{Stab}(H) = N_G(H)$.
> So Orbit-Stabilizer says $\mathcal O_h \cong G/\mathrm{Stab}(H)$; then just take sizes.

> **Theorem 3:** $\union_{g\in G} H^g = \union_{g\in G} gHg\inv \subsetneq G$ for any proper $H \leq G$.
>
> *Proof:* By theorem 2, since each coset is of size $\abs{H}$, which only intersect at the identity, and there are exactly $[G: N_G(H)]$ of them
\[
\abs{\union_{g\in G} H^g} 
&= \qty{ \abs{H} - 1} [G: N_G(H)] + 1\\
&= \abs{H} [G: N_G(H)]  - [G:N_G(H)] + 1\\
&= \abs{G} \frac{\abs G}{\abs{N_G(H)}} - \frac{\abs G}{\abs{N_G(H)}} + 1 \\
&\leq \abs{H} \frac{\abs G}{\abs{H}} - \frac{\abs G}{\abs{H}} + 1 \\
&= \abs{G} - ([G: H] - 1) \\
&< \abs{G} 
.\]
> where we use the fact that $H \subseteq N_G(H) \implies \abs{H} \leq \abs{N_G(H)} \implies \frac{1}{\abs{N_G(H)}} \leq \frac{1}{\abs{H}}$, and since $H < G$ is proper, $[G:H] \geq 2$.

Since $[g_i, g_j] = 1$, we have $g_i \in Z(g_j)$ for every $i, j$.

Then
\[
g\in G 
&\implies g = g_i^h \quad \text{ for some } h \\
&\implies g \in Z(g_\mathbf{j})^h \quad\text{for every } j \text{ since }g_i \in Z(g_j) ~\forall j \\
&\implies g \in \union_{h\in G} Z(g_j)^h \quad\text{for every } j\\
&\implies G \subseteq \union_{h\in G} Z(g_j)^h \quad\text{for every } j
,\]

which by Theorem 3, if $Z(g_j) < G$ were proper, then the RHS is properly contained in $G$. 
So it must be the case that that $Z(g_j)$ is not proper and thus equal to $G$ for every $j$.

But $Z(g_i) = G \iff g_i \in Z(G)$, and so each conjugacy class is size one.
So for every $g\in G$, we have $g = g_j$ for some $j$, and thus $g = g_j \in Z(g_j) = Z(G)$, so $g$ is central.
Then $G\subseteq Z(G)$ and $G$ is abelian.


