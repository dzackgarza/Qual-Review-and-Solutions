---
date: 2021-04-28 18:07:42
tags: 
  - Unfiled
---

[../Subjects/Contact](../Subjects/Contact.md)

Tags: #topology #contact_topology


> Convention: 
> All manifolds discussed will be smooth, real, Hausdorff, second-countable, connected, not necessarily closed/compact, possibly with boundary.


# Hyperplane Fields

These are important because of their ties to *foliations*.

*Example 1 of a Hyperplane Fields:*
Take $M=S^2$, so we have $\RR^2 \to TS^2 \to S^2$.
The tangent spaces are planes, and codimension 1 spaces are lines:

![](2020-02-01-23-22-51.png)

*Example 2 of a Hyperplane Fields:*
Let $M = \RR^3$ so $TM \cong \RR^3$. 
Write $T_pM = \spanof_\RR\theset{\partial x_1, \partial x_2, \partial x_3}$ and $T_p\dual M = \spanof_\RR\theset{dx_1, dx_2, dx_3}$ locally and define $\xi$ by the condition $$dx_3 = 0$$

![](2020-02-01-22-28-35.png)

> Idea: no movement in the $x_3$ direction, constrained to move only in $x_1, x_2$ directions. Assigns a "horizontal" hyperplane to each point in $\RR^3$.


> Remark: This is the kernel of a tangent covector at every point, i.e. a 1-form. This is a prototypical feature.

*Example 3 of a Hyperplane Fields:*
For $M=\RR^3$, write $T\dual \RR^3 = \spanof_\RR\theset{dx, dy, dz}$, and take $$\omega = dz + xdy \in \Omega^1(\RR^3)$$
This is the "standard contact structure" on $\RR^3$, and assigns hyperplanes that look like this:

![](2020-02-01-22-34-56.png)

> Remark:
> Note that this has a more twisted structure, which is what geometrically makes it contact -- no embedded (hyper) surface in $\RR^3$ can have an open subset $U$ such that $\xi$ is tangent to $p$ for every $p\in U$.

# Foliations

> *Remark:*
> Foliations arise when you have a PDE (IVP or BVP) defined on an $n\dash$manifold $M$, with some initial/boundary conditions defined on an embedded surface, and you want to find the time evolution of that system (moving you through leaves of the foliation, think of spacetime being foliated by space-like hyperplanes in General Relativity).

**Definition (Foliation):**
A *foliation* on $M$ is a hyperplane field $\xi$ satisfying one of two equivalent conditions:

1. A family of embedded surfaces $\Sigma_i \injects M$ such that $M = \disjoint_i \Sigma_i$ uniquely.
2. $\xi$ is locally diffeomorphic to the horizontal hyperplane field $dx_n = 0$.

> Note: the foliation is usually referred to by the collection $\Sigma_i$.
> Can also think of this as a smooth manifold where transition maps "preserve hyperplanes", i.e. they are functions of only one variable.

The "slices" given by the surfaces are referred to as *leaves*.

*Example of a Foliation:*
As in example 2, take $\RR^3 = \disjoint_{t\in \RR} ~t + H_{xy}$ where $H_{xy} = \theset{(x,y,z) \in \RR^3 \suchthat z=0}$ is the $xy\dash$plane and $t+ H_{xy} = \theset{(x,y,z) \in \RR^3 \suchthat t = z}$ are the vertical translates.
This yields a foliation of $\RR^3$ by planes.

*Example of a Foliation:*
Any fiber bundle $F \to E \mapsvia{\pi} B$ is foliated by leaves $L_b \definedas \theset{b} \cross \pi\inv(b)$.

*Example of a Foliation*:
Let $T = \RR^2/\ZZ^2$ be a flat torus and $q$ any irrational number; then lines $L_q$ of slope $q$ foliate $T$.

*Example of a Foliation:*
Any nonsingular vector field $X$ on a closed manifold $M$ defines a foliation; each leaf is the orbit of a point under the flow of $X$.

*Example of a Foliation:*
Take $M$ closed, $G$ a connected Lie group acting locally freely (the stabilizer of a point is a discrete subgroup of $G$). Then again $M$ is foliated by orbits of points.

*Example (The Reeb Foliation):*
Define a map out of a cylinder in cylindrical coordinates
\begin{align*}
f: (D^2)^\circ \cross \RR &\to \RR \\
(\vector x, t) &\mapsto e^{\frac{1}{1-\abs z}} - t
.\end{align*}

Adding in a component $\bd D^2 \cross \RR \cong S^1 \cross \RR$ yields a foliation of $D^2 \cross \RR$.
Then take a $\ZZ\dash$action where $z\actson (\vector x, t) = (\vector x, t+z)$; modding out by this action yields a solid torus, which still has the above foliation.

Do this to twice, gluing the two tori along their boundary to construct a copy of $S^3$, yields a foliation of $S^3$ where each leaf $L_b$ is not Hausdorff.


*Remark:*
A foliation $\theset{\Sigma_i}$ induces a decomposition on the tangent bundle of $M$, namely $TM = T(\Sigma_i) \oplus \xi$ (? check) where $\xi$ is a line bundle everywhere transverse to the $\Sigma_i$. 
In this situation, we say $\theset{\Sigma_i}$ is *transversely orientable*.
Whenever $\theset{\Sigma_i}$ is transversely orientable, it can be associated uniquely to a nonsingular 1-form $\omega$.
Then given an $f: M\to \RR^2$ (check dimension), we can study the set of critical points $S = \theset{p\in M \suchthat \omega_p \wedge df_p = 0}$.

*Remark:*
A specific type of foliation that comes up in modern research are *taut* foliations, which are codimension 1 foliations $\mathcal{F} = \theset{L_b}$ for which for every leaf $L_b$ there is a closed loop $\gamma: S^1 \to M$ intersecting $L_b$ with $\gamma$ everywhere transverse to $\mathcal{F}$.

**Theorem:**
TFAE:

1. $\mathcal{F}$ is a taut foliation.
2. There is a flow transverse to $\mathcal{F}$ that preserves some volume form on $M$.
3. There is a Riemannian metric on $M$ for which each leaf $L_b$ is a least-area hypersurface.

