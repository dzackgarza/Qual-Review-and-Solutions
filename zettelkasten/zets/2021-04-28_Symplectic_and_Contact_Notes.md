---
date: 2021-04-28 18:08:16
tags: 
  - Unfiled
---

[../Subjects/Contact](../Subjects/Contact.md)
[Symplectic](Symplectic)
[zets/2021-04-28_More_Weinstein_Notes](zets/2021-04-28_More_Weinstein_Notes.md)

Topic: Weinstein Surgery and More

References:

- [Mike Usher's Notes](https://usherugamath.files.wordpress.com/2019/05/8230-s19.pdf)
- From Stein to Weinstein and Back (Cieliebak and Eliashberg)

# Why Care About Contact/Symplectic Geometry

*Open Problem:**
Does every triangular billiards admit a periodic orbit?

*Answer (1775):* 
Yes for acute triangles, there is at least one periodic orbit:

![](2020-02-01-23-59-05.png)

For arbitrary triangles: unknown!

Historically, the study of periodic orbits motivated the definition of *contact structures*.

**Definition (Hyperplane Field):**
A *hyperplane* field $\xi$ is a codimension 1 sub-bundle $\RR^{n-1} \to \xi \to M$ of the tangent bundle $\RR^n \to TM \to M$.

> See examples.

**Definition (Contact Manifold)**
A smooth manifold with a hyperplane field $(M^{2n+1}, \xi)$ is *contact* iff $\xi = \ker \alpha$ for some $\alpha \in \Omega^1(M)$ where $\alpha \wedge (d\alpha)^n$ is a top/volume form in $\Omega^{2n+1}(M)$

> Note that $\lambda \wedge (d\lambda)^n = 0$ defines a foliation?

**Definition (Reeb Vector Field):**
There is a canonical vector field on every contact manifold: the Reeb vector field $X$. This satisfies $\lambda(X) = 1$ and $\iota_x d\lambda = 0$.

> *Remark:*
> Contact manifolds are cylinder-like boundaries of symplectic manifolds; namely if $M$ is contact then we can pick any $C^1$ increasing function $f: \RR \to \RR^+$  (e.g. $f(t) = e^t$) and obtain an exact symplectic form $\omega = d(f\lambda)$ on $M_C \definedas M \cross \RR$.

> Any such $f$ induces a Hamiltonian vector field on $M_C$, and the Reeb vector field is the restriction to $M \cross \theset{0}$.


# Why Care About Contact Structures 

Let $M$ be a symplectic manifold and $H: M \to \RR$ a Hamiltonian.

For regular values $r\in \RR$ of the  Hamiltonian, $H\inv(r) \subset M$ is a submanifold $Y\subset M$ with a smooth vector field $X_H$ called a *regular level set*.

**Question:**
Does $X_H$ have a closed orbit on every regular level set?
What conditions do you need to guarantee the existence of a closed orbit?

Turns out not to depend on $H$, and only on the hypersurface $Y$.
The existence of a closed orbit is equivalent to the existence of a closed embedded curve $\gamma$ that is everywhere tangent to $\ker(\restrictionof{\omega}{Y})$.

**Question:**
When is such a curve guaranteed to exist?

**Theorem (Weinstein, 1972):** 
If $Y$ is convex.

**Theorem (Rabinowitz)**: 
If $Y$ is "star-shaped" (exists a point $p$ that can "see" all points via straight lines).

**Theorem (1987):**
Every contact-type hypersurface in the symplectic manifold $(\RR^{2n}, \omega)$ contains a periodic orbit.

**Conjecture (Weinstein, 1978):**
Let $(M, \xi)$ be a closed (compact) contact manifold with a Reeb vector field $X$ and $H^1(M; \RR) = 0$. Then $X$ admits a periodic orbit.

**Theorem (Weinstein, Dimension 3, Overtwisted. 1993):**
Let $(M, \lambda, \xi)$ be a closed contact 3-manifold where $\lambda$ is overtwisted. 
Then the **Reeb vector field** $X$ admits a periodic orbit.

# Definitions

**Definition (Hamiltonian)**:
A smooth function $H: M \to \RR$ will be referred to as an energy functional or a *Hamiltonian*.
If we have $H: M\cross I \to \RR$, we'll refer to this as a *time-dependent Hamiltonian*, i.e. the time slices $H_t: M \to \RR$ given by $H_t(p) = H(p, t)$ are Hamiltonians.

> *Remark:*
> If $(M, \omega)$ is a symplectic manifold, each $H_t: M \to I$ induces a unique vector field $X_{H_t}$ characterized by the property $\iota_{X_{H_t}}\omega = -dH_t$ where $\iota$ is the interior product.

**Definition (Symplectic Manifold):**
Recall that $M^{2n}$ is a **symplectic manifold** iff $W$ is smooth of even dimension and admits a 

- closed: $d\omega = 0$
- nondegenerate $\omega_p: T_p M \cross T_p M \to \RR$; $\omega_p(\vector v,\vector w) = 0~~\forall \vector w \implies \vector v= 0$.
- skew-symmetric: $\omega_p(\vector v, \vector w) = \omega_p(\vector w, \vector v)$. 
- bilinear: Lifts to a map $T_pM\tensor T_P M \to \RR$
- 2-form 
$$
\omega \in \Omega^2(M) = \Gamma^{\infty}(\bigwedge^2 T\dual M)
.$$ 

> *Motivation*: 
> There is Hamiltonian $H$ in the background, we want this to induce a vector field $V_H$ and thus a flow.

> Motivation for definitions: we want an "antisymmetric inner product".
>
> - *Closed:* 
  The lie derivative of $\omega$ along $V_H$ is 0, i.e. $\mathcal{L}_{V_H}(\omega) = 0$.
>
>  - *Nondegenerate:* 
    Implies that for every $dH$ there exists a vector field $V_H$ such that $dH = \omega(V_H, \wait)$.
>
> - *Skew-symmetry:*
    $H$ should be constant along flow lines, i.e. $dH(V_H) = \omega(V_H, V_H) = 0$
>
> - *Bilinear:*
    Send any form $\inner{\wait}{\wait}: V\times V \to k$ to the linear map $f: V \to V\dual$ where $f(v) = \inner{v}{\wait}$. If the pairing is nondegenerate, $\ker f = 0$, and we get an identification $V\cong V\dual$.

> **Important Remark**
> $\omega$ being nondegenerate yields $TM \cong T\dual M$, which can be combined with $\iota$ to obtain an isomorphism $\mathfrak{X}(M) \cong \Omega^1(M)$.
So we can freely trade 1-forms for vector fields. Very useful!
>
> MOST IMPORTANTLY: for any smooth functional $f: M \to \RR$, we can associate to it a vector field $X_f$.

**Definition (Hamiltonian vector field):**
Given a smooth functional $H: (M, \omega) \to \RR$, the associated *Hamiltonian vector field* is the unique field $X_H$ satisfying $\omega(X_H, \wait) = dH$.

> Remark: Conservation of energy
> Since $\omega$ is alternating,
\begin{align*}
X_H(H) = dH(X_H) = \omega(X_H, X_H) = 0
.\end{align*}

**Proposition:**
$(M, \omega \in \Omega^2(M))$ is symplectic iff $\omega^n \neq 0$ everywhere (c.f. Mike Hutchings).

**Corollary:**
Every symplectic manifold is orientable (since it has a nonvanishing volume form).

> **Important Remark:**
Symplectic structures on smooth manifolds give us a way to generate *flows* on a manifold (by defining a Hamiltonian or a symplectic vector field).

**Definition (Exact Symplectic Manifold):**
$W$ is an *exact* symplectic manifold iff there exists a 1-form $\lambda \in \Omega^1(W)$ such that $d\lambda \in \Omega^2(W)$ is non-degenerate.

> **Remark**:
> If $(W, \lambda)$ is exact symplectic then $(W, d\lambda)$ is symplectic.
> $\lambda$ is sometimes referred to as a *Liouville form*.

> **Important Remark:**
> If $(W, \lambda)$ is exact and $H: \RR \cross M \to \RR$ is smooth, then the *Hamiltonian flow* $\phi_H^t: M \to M$ is defined for all time and is an *exact symplectomorphism*.

**Theorem:**
There are no closed (compact and boundaryless) exact symplectic manifolds.

*Proof:*
\begin{align*}
\int_{\bd M} \lambda \wedge \omega^{n-1} 
&= \int_M d(\lambda \wedge \omega^{n-1}) \\ 
&= \int_M d\lambda \wedge \omega^{n-1} + (-1)^{\abs \lambda}\lambda\wedge d\omega^{n-1} \\
&= \int_M \omega \wedge \omega^{n-1} + (-1)^{\abs\lambda} \lambda \wedge 0 \\
&= \int_M \omega^n \\
&= \mathrm{Vol}_{\text{Sp}}(M) \\
&> 0
,\end{align*}

so $\bd M \neq 0$, and thus $M$ can not be closed.

$\qed$

**Definition (Liouville Vector Field):**
Let $(W, \lambda)$ be exact symplectic.
The Liouville vector field on $(W, \omega = d\lambda)$ is the (unique) vector field $X$ such that $\iota_x \omega = \lambda$.

> Remark:
> $X$ induces a flow $\psi^{X, t}$, and for any compact embedded surface $\Sigma_g \injects W$ we have
\begin{align*}
\psi^{X, t *} d \lambda&= e^{t} d \lambda \implies \\
\operatorname{Area}_{d \lambda}\left(\psi^{X, t}(S)\right)
&:=\int_{\psi^{X, t}(S)} d \lambda\\
&=\int_{S} (\psi^{X, t})^* d \lambda\\
&=e^{t} \operatorname{Area}_{d \lambda}(S)
\end{align*}
>
> This says that the flow lines of $X$ "dilate" the areas of surfaces at an exponential rate, or that $X$ is an "infinitesimal generator" of a canonical dilation..

> Remark:
> This is useful because even if $W$ isn't compact, we can obtain $W$ as the "limit" of compact submanifolds where we inflate along this flow.

**Theorem:**
A Liouville vector field $X$ satisfies $\mathcal{L}_X \omega = \omega$, where $\mathcal{L}_X$ is the Lie Derivative.

*Proof:*
\begin{align*}
\mathcal{L}_X \omega = [d, \iota_X] \omega = \iota_X(d\omega) + d(\iota_x \omega) = \iota_x(d\omega) + d\lambda = \iota_X(0) + d\lambda = d\lambda = \omega
.\end{align*}

> Use the fact that $\omega$ is closed, so $d\omega = 0$.

$\qed$

**Definition (Contact Type):**
For $(W, \lambda)$ an exact symplectic manifold, a codimension 1 submanifold $Y \subset W$ is of *restricted contact-type* iff $X$ is transverse to $Y$, i.e. for every $p\in Y$, we have $X(p) \not\in T_p(Y)$.

We say $Y$ is of *contact type* iff there is a neighborhood $U \supset Y$ and a one-form $\lambda$ with $d\lambda = \restrictionof{\omega}{U}$ making $(U, \lambda)$ of restricted contact type.

> Remark:
>$(U, \lambda)$ is of restricted contact type iff $\restrictionof{\lambda}{U}$ is a contact form.

**Definition (Hypersurface of contact type):**
For $(X, \omega)$ a symplectic manifold, a hypersurface $\Sigma \injects X$ is of *contact-type* iff there is a contact form $\lambda$ such that $d\lambda = \restrictionof{\omega}{Y}$.

**Definition (Liouville Domain):**
$(W, \lambda)$ is a Liouville domain iff $W$ is a *compact* exact symplectic manifold with boundary such that the Liouville vector field $X$ points outwards on $\bd W$ transversally.

> Remark:
> This condition implies that $\bd W$ is a contact manifold with contact form $\alpha = \restrictionof{\lambda}{\bd W}$.

**Definition (Isotropic):**
Let $\Lambda$ be the image of an embedded sphere $S^k \to W$.
Then $\Lambda$ is *isotropic* iff $\restrictionof{\lambda}{\Lambda} = 0$.

**Definition (Weinstein Surgery):**
Let $(W, \lambda)$ be a Liouville domain (although we won't need compactness).

> Recall: $(W, \lambda)$ is a $2n\dash$dimensional exact symplectic manifold with contact-type boundary $\bd W$ such that the Liouville vector field $X$ points outwards along $\bd W$.

Weinstein surgery takes 

- $(W, \lambda)$ a $2n\dash$dimensional manifold
- That is exact and symplectic
- With contact-type boundary $\bd W$
- Where the Liouville vector field points outward along $\bd W$

and produces a distinct manifold $(W(\Lambda), \lambda')$ with the above properties which is obtained by surgery along $\Lambda$ an isotropic embedded sphere.
Thus $W(\Lambda)$ is obtained from attaching a $k\dash$handle to $W$ along $\Lambda$. 

## Aside on Surgery

### Analogy: CW Cell Attachment

Given $X$, we can form $\tilde X = X^n \disjoint_\phi e^n$ where $e^n \cong D^n$ is an $n\dash$cell and $\phi: S^{n-1} \to X$ is the characteristic/attaching map.

> Remark: Why $S^{n-1}$? Really it's $\bd e^n = \bd D^n = S^{n-1}$.

![](2020-02-05-00-22-18.png)

Problem:
This doesn't "see" the smooth structure, and CW complexes can have singular points (e.g. $S^2 = e^0 \disjoint e^2$.

![](2020-02-05-12-25-15.png)

Solution:
Use *tubular neighborhoods*.


**Definition (Surgery):**
Given a manifold $M^n$ where $n=p+q$, then $p\dash$surgery on $M$, denoted $\mathcal{S}(M)$, result of cutting out $S^p \cross D^q$ and gluing back in $D^{p+1} \cross S^{q-1}$.

Let $\Gamma_{p, q} = S^p \cross D^q$, call this our "surgery cell".
As in the CW case, we want to attach this cell via an embedding of its boundary into $M$.

We can compute
$$
\bd(S^p\cross D^q) = S^p \cross S^{q-1} = \bd(\mathbf{D^{p+1} \cross S^{q-1}})
$$ 

then the above says
$$
\bd \Gamma_{p, q} = S^p \cross S^q = \bd \Gamma_{p+1, q-1}
$$

So fix any embedding 
$$\phi: \Gamma_{p, q} \to M$$

Note that this restricts to some map (abusing notation) 
$$\phi: \bd \Gamma_{p, q} \to M$$

So by the above observation, we can trade this in for a map
\begin{align*}
\phi: \bd\Gamma_{p+1, q-1} \to M
.\end{align*}

And so we can use this as an attaching map:
\begin{align*}
\mathcal{S}_p(M) \definedas M\setminus \phi(\Gamma_{p, q})^\circ \disjoint_\phi \Gamma_{p+1, q-1} 
.\end{align*}


**Definition (Handle Attachment)**
Given a manifold $(M^n, \bd M^n)$ with boundary, attaching a $p\dash$handle to $M$, denoted $H_p(M)$, is given by $p\dash$surgery on $\bd M$, i.e. 
\begin{align*}
H_p(M)^\circ    &= M \\
\bd H_p(M)      &= \mathcal{S}_k(\bd M)
.\end{align*}

> Remark: we need conditions on the embedding of the normal bundle for this to work.

**Examples of Handles :**
$S^1 \cross D^2 \cong \bar T$, a solid torus.

A useful table:

![](2020-02-05-00-59-19.png)

> See examples of surgery

**Definition (Weinstein Surgery):**
We now add a $k\dash$handle along $\Lambda \subset \bd W$ to yield some $W'$, where $\bd W'$ is obtained by surgery in $\bd W$ along $\Lambda$.  

# Why Care About Weinstein Surgery

**Theorem:** 
Every compact contact 3-manifold arises as a combination of (2 different variants of) Weinstein surgeries on $S^3$.

> Compare to theorem: 
Every compact 3-manifold arises as surgery on a link.

**Theorem:** 
Weinstein surgery on a *loose Legendrian* knot yields an overtwisted contact structure.

> Compare: 
Every compact manifold is surgery on a link and admits a contact structure.

> However, not every compact 3-manifold $M$ admits a *fillable* contact structure $(M, \xi)$ (roughly: admits a symplectic manifold $(X, \omega)$ with $\bd X = M$ and some compatibility between $\xi, \omega$) -- need framing to be realizable as a *Legendrian* framing.

**Theorem:** 
Weinstein surgery along a loose Legendrian sphere yields an overtwisted contact manifold.
