# Spring 2018

## 1 \label{problem:session_1_5_1_soln}

Concepts Used:

- Centralizer: $C_G(x) = \theset{g\in G \suchthat [gx] = 1}$.
- Class Equation: $\abs{G} = \abs{Z(G)} + \sum [G: C_G(x_i)]$
- $G/Z(G)$ cyclic $\iff G$ is abelian.
  
  > *Proof:*
    \begin{align*}
    G/Z(G) = \generators{xZ} 
    &\iff g\in G \implies gZ = x^mZ \\
    &\iff g(x^m)\inv \in Z \\
    &\iff g = x^m z \qtext{for some}z\in Z\\
    &\implies gh = x^mz_1 x^n z_2 = x^n z_2 x^m z_1 = hg
    .\end{align*}

- Every group of order $p^2$ is abelian.
- Classification of finite abelian groups.

### a

Strategy: get $p$ to divide $\abs{Z(G)}$.

- Apply the class equation:
\begin{align*}
\abs{G} = \abs{Z(G)} + \sum [G: C_G(x_i)]
.\end{align*}

- Since $C_G(x_i) \leq G$ and $\abs{G} = p^k$, by Lagrange $\abs{C_G(x_i)} = p^\ell$ for some $0\leq \ell \leq k$.
- Since $\abs{G} = p^k$ for some $k$ and $Z(G), C_G(x_i) \leq G$ are subgroups, their orders are powers of $p$.
- Use $$[G: C_G(x_i)] = 1 \iff C_G(x_i) = G \iff \theset{g\in G\suchthat gx_ig\inv = x_i} = G \iff x_i \in Z(G).$$
  - Thus every index appearing in the sum is greater than 1, and thus equal to $p^{\ell_i}$ for some $1\leq \ell_i \leq k$
  - So $p$ divides every term in the sum

- Rearrange 
\begin{align*}
\abs{G} -  \sum [G: C_G(x_i)]
= \abs{Z(G)} 
.\end{align*}

- $p$ divides both terms on the LHS, so must divide the RHS, so $\abs{Z(G)} \geq p$.


### b

Strategy: examine $\abs{G/Z(G)}$ by cases.

- $1$: Then $G = Z(G)$ and $G$ is abelian.
- $p$: Then $G/Z(G)$ is cyclic so $G$ is abelian
- $p^2$: Not possible, since $\abs {Z(G)} > 1$ by (a).

### c

- By Sylow

  - $n_5 \divides 7^2,\quad n_5\cong 1\mod 5 \implies n_5\in\theset{1, 7, 49}\setminus\theset{7, 49} = \theset{1} \implies n_5 = 1$
  - $n_7 \divides 5^2, \quad n_7 \cong 1 \mod 7 \implies n_7 \in \theset{1, 5, 25}\setminus\theset{5, 25} =\theset{1} \implies n_7 = 1$

- By recognition of direct products, $G = S_5 \cross S_7$
  - By above, $S_5, S_7\normal G$
  - Check $S_5\intersect S_7 = \theset{e}$ since they have coprime order.
  - Check $S_5S_7 = G$ since $\abs{S_5 S_7} = 5^2 7^2 = \abs{G}$

- By (b), $S_5, S_7$ are abelian since they are groups of order $p^2$
- The direct product of abelian groups is abelian.

### d

1. $\ZZ_{5^2} \cross \ZZ_{7^2}$
1. $\ZZ_{5}^2 \cross \ZZ_{7^2}$
1. $\ZZ_{5^2} \cross \ZZ_{7}^2$
1. $\ZZ_{5}^2 \cross \ZZ_{7}^2$

$\qed$

## 2

> Not the nicest proof! Would be better to replace the ad-hoc computations at the end..

### a

Note that $g(x) = x^2 - 4x + 2$ has roots $\beta = 2 \pm \sqrt{2}$, and so $f$ has roots 
\begin{align*}
\alpha_1 &= \sqrt{2 + \sqrt 2} \\
\alpha_2 &= \sqrt{2 - \sqrt 2} \\
\alpha_3 &= -\alpha_1 \\
\alpha_4 &= -\alpha_2
.\end{align*}

and splitting field $K = \QQ(\theset{\alpha_i})$.

### b

$K$ is the splitting field of a separable polynomial and thus Galois over $\QQ$.
Moreover, Since $f$ is irreducible by Eisenstein with $p=2$, the Galois group is a transitive subgroup of $S^4$, so the possibilities are:

- $S_4$
- $A_4$
- $D_4$
- $\ZZ/(2) \cross \ZZ/(2)$
- $\ZZ/(4)$

We can note that $g$ splits over $L \definedas \QQ(\sqrt 2)$, an extension of degree 2.

We can now note that $\min(\alpha, L)$ is given by $p(x) = x^2 - (2 + \sqrt 2)$, and so $[K: L] = 2$.

We then have
\begin{align*}
[K: \QQ] = [K: L] [L : \QQ] = (2)(2) = 4
.\end{align*}

This $\abs{\Gal(K/\QQ)} = 4$, which leaves only two possibilities:

- $\ZZ/(2) \cross \ZZ/(2)$
- $\ZZ/(4)$

We can next check orders of elements.
Take
\begin{align*}
\sigma &\in \Gal(K/\QQ) \\
\alpha_1 &\mapsto \alpha_2
.\end{align*}


Computations show that 

- $\alpha_1^2 \alpha_2^2 = 2$, so $\alpha_1 \alpha_2 = \sqrt 2$
- $\alpha_1^2 = 2 + \sqrt 2 \implies \sqrt 2 = \alpha_1^2 - 2$

and thus
\begin{align*}
\sigma^2(\alpha_1) &= \sigma(\alpha_2) \\
&= \sigma\left(\frac{\sqrt 2}{\alpha_1}\right) \\
&= \frac{\sigma(\sqrt 2)}{\sigma(\alpha_1)} \\
&= \frac{\sigma(\alpha_1^2 - 2)}{\alpha_2} \\
&= \frac{\alpha_2^2 - 2}{\alpha_2} \\
&= \alpha_2 -2\alpha_2\inv \\
&= \alpha_2 - \frac{2\alpha_1}{\sqrt 2} \\
&= \alpha_2 -\alpha_1 \sqrt 2 \\
&\neq \alpha_1
,\end{align*}

and so the order of $\sigma$ is strictly greater than 2, and thus 4, and thus $\Gal(K/\QQ) = \theset{\sigma^k \suchthat 1\leq k \leq 4} \cong \ZZ/(4)$.

### c


?? The subgroup of index 2 $\generators{\sigma^2}$ corresponds to the field extension $Q(\sqrt 2) / \QQ$.

## 3

> Moral: $H_1 \intersect H_2 \iff E_1 E_2$, $H_1 H_2 \iff E_1 \intersect E_2$.

### a

By the Galois correspondence, it suffices to show that the fixed field of $H_1 \intersect H_2$ is $E_1 E_2$.

Let $\sigma \in H_1 \intersect H_2$; then $\sigma \in \Aut(K)$ fixes both $E_1$ and $E_2$.

> Not sure if this works -- compositum is not literally product..?

Writing $x \in E_1E_2$ as $x=e_1 e_2$, we have 
$$
\sigma(x) = \sigma(e_1 e_2) = \sigma(e_1) \sigma(e_2) = e_1 e_2  =x,
$$

so $\sigma$ fixes $E_1 E_2$.

### b

That $H_1 H_2 \subseteq G$ is clear, since if $\sigma = \tau_1 \tau_2 \in H_1 H_2$, then each $\tau_i$ is an automorphism of $K$ that fixes $E_i \supseteq \QQ$, so each $\tau_i$ fixes $\QQ$ and thus $\sigma$ fixes $\QQ$.

That it is a subgroup follows from the fact that elements commute. (?)
 
To see this, let $\sigma = \sigma_1 \sigma_2 \in H_1 H_2$.

Note that $\sigma_1(e) = e$ for all $e\in E_1$ by definition, since $H_1$ fixes $E_1$, and $\sigma_2(e) \in E_1$ (?).

Then 
$$
\sigma_1(e) = e \quad \forall e \in E_1 \implies \sigma_1(\sigma_2(e)) = \sigma_2(e) 
$$  

and substituting $e = \sigma_1(e)$ on the RHS yields

\begin{align*}
\sigma_1 \sigma_2(e) = \sigma_2 \sigma_1(e)
,\end{align*}

where a similar proof holds for $e\in E_2$ and thus for arbitrary $x\in E_1 E_2$.


### c

By the Galois correspondence, the subgroup $H_1H_2 \leq G$ will correspond to an intermediate field $E$ such that $K/E/\QQ$ and $E$ is the fixed field of $H_1 H_2$.

But if $\sigma \in H_1 H_2$, then $\sigma = \tau_1 \tau_2$ where $\tau_i$ is an automorphism of $K$ that fixes $E_i$, and so $\sigma(x) = x \iff \tau_1\tau_2(x) = x \iff \tau_2(x) = x ~\&~ \tau_1(x) = x \iff x \in E_1 \intersect E_2$.
