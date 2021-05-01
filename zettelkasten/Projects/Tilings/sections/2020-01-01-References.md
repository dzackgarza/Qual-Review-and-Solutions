# References and Basics

**References:**

- Survey Paper: Anton Zorich, [Flat Surfaces](https://arxiv.org/abs/math/0609392)
- Alex Eskin, Andrei Okounkov, [Asymptotics of numbers of branched coverings of a torus and volumes of moduli spaces of holomorphic differentials](https://arxiv.org/abs/math/0006171)
- Alex Eskin, Howard Masur, Anton Zorich, [Moduli Spaces of Abelian Differentials: The Principal Boundary, Counting Problems and the Siegel--Veech Constants
](https://arxiv.org/abs/math/0202134)
- Alex Eskin, Andrei Okounkov, [Pillowcases and quasimodular forms](https://arxiv.org/abs/math/0505545)
- Vincent Delecroix, Elise Goujard, Peter Zograf, Anton Zorich, [Contribution of one-cylinder square-tiled surfaces to Masur-Veech volumes](https://arxiv.org/abs/1903.10904)
  - See Phil for appendix! 
- Engel, [Hurwitz Theory of Elliptic Orbifolds, I](https://arxiv.org/abs/1706.06738)
- Engel, [Hurwitz Theory of Elliptic Orbifolds, II](https://arxiv.org/abs/1809.07434)

**Definition:**
A map $\pi: \Sigma \to \Sigma'$ of Riemann surfaces is said to be *ramified* at a point $p\in \Sigma'$ iff in local charts $\pi$ has the form $z\mapsto z^n$ for some $n>1$.

> I.e. all points in a punctured neighborhood of $\pi(p)$ have $n$ preimages.

**Definition:**
If $\pi$ is ramified at $p$, the number of preimages $n$ is referred to as $e_p$, the *ramification index of $p$*.

*Fact:*
$\vector{\beta}(\Sigma_g) = [1, 2g, 1, 0, \cdots]$ and $\chi(\Sigma) = 2-2g$.

**Theorem:**
If $\pi$ is an unramified covering map of degree $n$, then $\chi(\Sigma') = n\chi(\Sigma)$.

**Theorem (Riemann-Hurwitz):**
If $\pi: \Sigma \to \Sigma'$ is a ramified covering map of degree $N$, then

\begin{align*}
\chi(\Sigma') = N \chi(\Sigma) - \sum (e_p - 1) \quad\text{ i.e. } 2 g(\Sigma') - 2=  N(2g(\Sigma) - 2)  + \sum (e_p - 1)
.\end{align*}

*Another useful form:*
Let $r \in \Sigma'$ be the number of ramification points, and $b$ the number of branch points, i.e. their images in $\Sigma$.
Then

\begin{align*}
\chi(\Sigma') = N(\chi(\Sigma) - b) + r
.\end{align*}


**Holomorphic Forms:**
A holomorphic $p\dash$form on $X$ is a section of $\Lambda^p T\dual X$, the $p$th exterior power of the holomorphic cotangent bundle of $X$.

For $n = \dim_\CC X$, the $n\dash$forms are an important special case.
Any such form $w$ is given in local coordinates $(z_1, \cdots, z_n)$ by 

\begin{align*}
w = w(z_1, \cdots, z_n) dz_1 \wedge \cdots \wedge dz_n
\end{align*}

for some holomorphic function $w: \CC^n \to ?$.

**Canonical Bundle:**
Given a complex manifold $M$, we can define the tangent bundle $\CC^n \to TM \to M$ and the cotangent bundle $\CC^n \to T\dual M \to M$, which we'll just denote $T\dual M$.
Then the canonical bundle is the bundle $\CC\to \Lambda^n T\dual M \to M?$, denoted by $\omega$, obtained by taking the $n$th exterior power.

It is a theorem that the fibers are in fact complex lines $\CC^1$.
For vector bundles, this is referred to as the *determinant bundle*.
If $M$ is a smooth manifold, then $\omega$ has a global section.

> Note: a holomorphic $n\dash$form is exactly the same as a section of the canonical bundle.

Interesting aside: a Calabi-Yau is a manifold with a nowhere vanishing holomorphic $n\dash$form, which implies that the canonical bundle admits a map to a trivial line bundle that is an isomorphism, i.e. the canonical bundle is trivial.

*Exercise:*
For $\Sigma_g$ a compact Riemann surface of genus $g$, the dimension of the space of holomorphic sections of the canonical bundle, i.e. the space of holomorphic differentials on $\Sigma_G$, is given by $\dim H^0(X; \Omega) = g$ (the genus of the surface).
Proof: use Riemann-Roch.

Classification of elliptic orbifolds of dimension 2:
Define $(n_1, \cdots; m_1, \cdots)$ as the *profile*, where $n_i$ are *elliptic* points (locally look like quotient by $\ZZ/n\ZZ$), and $m_i$ are *corner reflectors* (locally look like quotient by a dihedral group):

![Image](figures/2020-01-29-20:44.png)\


Conformal (or equivalently complex) structures on a genus $g$ surface form a moduli space $\MM_g$ of dimension $3g-3$ for $g > 1$.

Let $\alpha$ be any partition of $2g-2$, and $\mch(\alpha)$ the moduli space of pairs $(\Sigma_g, \omega)$ where $\Sigma_g$ is a Riemann surface of genus $g$ and $\omega$ is a holomorphic 1-form (Abelian differential) on $M$ with the orders of its zeros given by $\alpha$.
Letting $\mch$ be the moduli space of all abelian differentials on Riemann surfaces of genus $g$ is stratified by $\mch(\alpha)$ as $\alpha$ ranges over all partitions.
For flat tori, $\mch = \GL_+(2, \RR)/\SL(2, \ZZ)$.

For $\Sigma_g$ a Riemann surface, there is a formula (Gauss-Bonnet in the flat metric) relating the degrees of the zeros of a holomorphic 1-form to the genus:

\begin{align*}
\sum d_j = 2g-2
.\end{align*}



# Notes on Paper

> Reference: [https://arxiv.org/abs/math/0609392](https://arxiv.org/abs/math/0609392)

## Section  1

Flat surfaces are characterized as surfaces with a flat metric and (finitely many?) cone-like singularities.
These surfaces appear to be isomorphic to moduli spaces of holomorphic 1-forms.
It is profitable to study the orbit of the surface under the Teichmüller geodesic flow, as well as a $\GL_n$ action.

Some introductory surveys:

- A. Eskin [E], 
- G. Forni [For2], 
- P. Hubert and T. Schmidt [HuSdt5] 
- H. Masur [Ma7],
- H. Masur and S. Tabachnikov [MaT] 
- J. Smillie [S].


We usually associate

- Constant positive curvature = $S^2$
- Constant zero curvature = $S^1 \cross S^1 \definedas T^1 = \Sigma_1$
- Constant negative curvature = $\Sigma_g$ for $g\geq 2$, a surface of higher genus

**Proposition:**
Any surface can be given a flat metric, possibly introducing singular points.

> Idea: Push all of the curvature into a cone point.

*Example:*
The standard cube embedded in $\RR^3$.

This is a flat surface with 8 cone points located at the vertices.
Note that the metric is non-degenerate on the edges, since any neighborhood of a point on an edge is still homeomorphic to $\RR^2$:

![Image](figures/2020-01-11-23:54.png)

Any neighborhood of a vertex is isometric to the vertex of the usual notion of a cone.
The cone angle can be measured by cutting a cone from the base to the vertex, yielding a flat pattern that sits in $\RR_2$, and measuring the "missing" angle in the resulting circle:

![Image](figures/2020-01-12-00:00.png)

This shows that the cone angle of the cube is $3\pi/2$, which coincides with the fact that there are 3 square (and thus 3 right angles) adjacent to any cone point.

**Definition:**
Geodesic (todo)

**Definition:**
Ergodic (todo)

> Here this means that a typical geodesic will visit any region in phase space and time spent in a region is proportional to volume.


**Definition:**
Holonomy and Holonomy group (todo)

General (wildly open) problem:

- Describe the behavior of a generic geodesic on a surface
- Prove that the geodesic flow is ergodic on a typical flat surface
- Does almost every surface have a closed geodesic that does not pass through singular points?
  - If so, how many?
  - Find the (asymptotic) number of such closed geodesics of length shorter than $L$

This remains unsolved for $S^2$ with 3 singularities (equivalent to a certain billiards problem). 
It is not even known if any flat sphere admits a single closed geodesic.

Flat surfaces have nontrivial holonomy, which makes them resemble Riemannian manifolds more than flat tori.

If we take the surface and puncture the conical points, it is locally isometric to the punctured Euclidean plane.
This allows a notion of parallel transport of tangent vectors.

Parallel transports along homotopically trivial loops are always the identity; otherwise, for homotopically nontrivial loops this rotates the vector by some angle.
Parallel transport around a cone point rotates by exactly the cone angle.
Nontrivial holonomy forces geodesics to self-intersect many times.

> Exercise: parallel transport a vector around the cone point of a cube.

The flat torus has trivial linear holonomy -- all geodesics either close up, or never self-intersect and produce a dense winding path.

**Definition:**
A translation surface is closed orientable surface with a flat metric, a finite number of conical singularities, and trivial linear holonomy.

Note that trivial linear holonomy implies that cone angles are all integer multiples of $2\pi$.

> Convention: we assume all flat surfaces come with a distinguished direction.

Remark:
Billiards gives rise to a flat surface with nontrivial linear holonomy. 

**Definition:**
A half-translation surface is a surface with a flat metric and holonomy group $\ZZ/(2)$.

> In this case, a vector $\vector v$ may come back as $-\vector v$ after parallel transport.

We'll often consider families of flat surface sharing the same genus and number/type of conical singularities.
These will correspond to strata of moduli spaces of one-forms.

It will often be useful to let $\SL(2, \RR)$ act on these families, consider the orbits, and take its closure.

Central problem / conjecture:
Taking the closure of an orbit under the action of $\GL^+(2, \RR)$ is a complex subvariety, so both the moduli space of holomorphic one-forms and the moduli space of quadratic differentials resemble homogeneous spaces under the action of a unipotent group.

The there is a projection from these orbits (Teichmüller discs)  to the moduli space of complex structures (?), which will be denoted $\MM_g$.
It is well-known that moduli spaces are not homogeneous spaces, but the conjecture here is that they behave as if they were.

## Section 2: Motivations

Open problems in rectangular billiards:

1. Describe the behavior of a billiard trajectory in a generic triangle, and prove that the billiard flow is ergodic.
2. Does (almost) any table have at least one regular periodic trajectory? Is it preserved under deformations?
3. Asymptotically in length, how many periodic trajectories are there? 
4. Does any obtuse triangle have a single periodic trajectory?

*Known example:* 
Acute triangles have at least 1, see Fagnano trajectory 

*Fox-Kershner construction:*
Yields a way to go from billiard trajectories to geodesics on a flat surface.
General idea: glue two copies of the billiard table along the edge to get a flat sphere; then paths lift to geodesics.
Such surfaces are not "very flat", i.e. they have nontrivial linear holonomy.

