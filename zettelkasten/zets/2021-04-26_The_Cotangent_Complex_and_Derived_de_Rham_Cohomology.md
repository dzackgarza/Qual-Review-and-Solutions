---
date: 2021-04-26
tags: 
  - Unfiled
---

# The Cotangent Complex and Derived de Rham Cohomology

- Reference: [MSRI Workshop on Derived AG, Birational Geometry, Moduli Spaces](https://www.msri.org/workshops/862/schedules/25958).

- Specific Video: <https://www.youtube.com/watch?v=zRPa-VAvl6Q>

## Motivation

Basic affine objects in AG: commutative rings, replace with simplicial commutative rings which we'll use as a base diagram.
Later: derived stacks and geometric derived stacks.
Here is an evolution of objects. and how we can think about them:

:::{.example title="Algebraic Spaces"}
Algebraic schemes/spaces, e.g. $\PP^n$.
Think of these as étale sheaves of sets (think functor of points), identified as discrete spaces:
\[  
\mathcal{S}_{\leq 0} \da \ts{\text{Discrete spaces}}
.\]
Every component is contractible, so there are no higher homotopy groups and we think of these as 0-truncated spaces.
:::

:::{.example title="Stacks"}
For $X$ a smooth and proper $k\dash$scheme, the Picard stack 
\[
\underline{\Pic}_{X/k}
\]
is an Artin stack, which is a subclass Deligne-Mumford stacks.
Note that this still has automorphisms given by global units on $X$.
Think of these as 
\[  
\mathcal{S}_{\leq 1} \da \ts{\text{Étale sheaves of groupoids}}
,\]
where the notation now suggests 1-truncated spaces, and we can take fundamental groupoids $\Pi_0$ since there is now 1-homotopy.
:::

:::{.remark}
Note that the Picard stack can be identified as a mapping stack,
\[  
\underline{\Map}(X, K(\GG_m, 1))
.\]
:::

:::{.example title="Higher Stacks"}
$K(\GG_m, n)$ is a "higher stack", thought of as a sheaf taking values in $n\dash$truncated spaces $\mathcal{S}_{\leq n}$, i.e. a space where when basing at any point, there are no homotopy groups above degree $n$:
\[  
\mathcal{S}_{\leq n} \da \ts{\text{Étale sheaves of $n\dash$truncated spaces}}
.\]
This is a stack with a single point, where the isotopy is $K(\GG_m, n-1)$.
:::

:::{.remark}
Note that these are all built from affine schemes with a few acceptable moves.
:::

:::{.remark}
(DZG) The definitions of $\mathcal{S}_{j}$ above aren't explicitly stated, so these are guesses at slightly more precise definitions.
:::


:::{.example title="?"}
In stack notation, we can write
\[  
B\GG_m &= K(\GG_m, 1) \cong [\pt/\GG_m] \\
K(\GG_m, 2) &= [\pt / B\GG_m]
,\]
where the latter is a smooth Artin stack.
Mapping into this gives the Picard groupoid of a scheme.
These are higher geometric stacks that still have some "smoothness" properties.
:::

:::{.question}
What does it mean to give a map from a scheme $X$ into a higher stack?
:::

:::{.remark title="The fundamental process for building stacks"}
Note that the category of étale schemes taking values in $\mathcal{S}_{\leq n}$ is enriched in topological spaces.
There is a topological space 
\[
M\da \Map(X, K(\GG_m, n))
\]
where the homotopy groups are 
\[  
\pi_i M = 
\begin{cases}
H^{n-i}_{\et}(X, \GG_m) & 0\leq i \leq n \\
0 & \text{else}
\end{cases}
.\]
So this higher geometric stack that says something about higher étale cohomology groups.
We thus have étale sheaves taking values in higher topological spaces, and has some geometric meaning.
They're also built from geometric objects: namely, iterating taking quotients by smooth actions.
$K(\GG_m, 1)$ is a quotient by a smooth algebraic group, $K(\GG_m, 2)$ is now a smooth *Artin stack*, and we can keep going.
This is the fundamental process for building geometric higher stacks.
:::


:::{.remark}
Why derive things?
Schemes are equipped with sheaves of commutative rings, so the basic idea is let the sheaves take values in groupoids, stacks, etc.
So we can consider replacing the structure sheaf $\OO_X$ is itself a sheaf of spaces, and this is the fundamental idea of derived algebraic geometry.
:::

## Derived Schemes

Consider $\spec k\tensor_{k[x]}^L k$, a derived tensor product.
This is a *simplicial commutative ring*, and the basic version of an *affine derived scheme*.
This is a complex $C^\wait$ with homology in degree 0 and 1, where 
\[
H_1 = \Tor^1(k\tensor_{k[x]} k)
\]
So analogously, we'll start with derived schemes and take quotients by smooth groups.
In the end, we get derived stacks.

:::{.example title="Fundamental"}
An example is $\mathcal{M}_\phi$, the moduli of objects in some DG category $\mathcal{C}$.
:::

## Simplicial Rings

We need to agree on what the local affine modules will look like. 
For our purposes, they'll be simplicial commutative rings.
Consider the **derived category** $\mathcal{C} \da D(\ZZ)_{\geq 0}$ and its connective[^def_connective]
objects, which are chain complexes $C_\wait$ where $H_{< 0}(C_\wait) = 0$.
There is a **derived tensor product** 
$\tensor^L$
which makes $\mathcal{C}$ into a symmetric monoidal category.

Basic idea: we want to look at commutative algebra objects in this symmetric monoidal category $({D}(\ZZ), \tensor^L)$.[^familiar_move]
Note that of working in a symmetric monoidal abelian category, we will be looking at connective chain complexes, and simplicial rings are one way of studying commutative algebra objects here.

[^familiar_move]: 
This is a familiar move: people in the 60s knew one could do AG in some ambient symmetric monoidal abelian category.

[^def_connective]:
**Connective** means $H_{<0} = 0$.


We have some choices for making sense of DAG:

- $E_\infty\dash$ring spectra

- Simplicial commutative rings.

- Over $\QQ$, $\QQ\dash$commutative DGAs.

Our choice here will be the following: 

:::{.definition title="Simplicial Commutative Ring"}
Let $\Delta$ denote the *simplex category*, the category of non-empty finite ordered sets with order-preserving maps.
We have the following situation:

\begin{tikzcd}
\left[0\right]
  \ar[r, shift right=2.0ex] \ar[r] \ar[r, shift left=2.0ex] 
& \left[1\right] 
  \ar[l]
  \ar[r, shift right=2.0ex] \ar[r] \ar[r, shift left=2.0ex] 
& \left[2\right]
  \ar[l, shift right=1.00ex]
  \ar[l, shift left=1.00ex]
& \cdots
\\
\ts{0}
& \ts{0\to 1} 
& \ts{0\to 1\to 2} 
& \cdots
\end{tikzcd}

The arrows going up are **face maps** (or **coface maps**), and the others are **degeneracy** maps.
If $\mathcal{C}$ is a category, then $s\mathcal{C} \da \Fun(\Delta\op, \mathcal{C})$ is the category of simplicial objects of $\mathcal{C}$.
:::


:::{.remark}
An analogy: simplicial commutative $k\dash$algebras enrich usual $k\dash$algebras much like the derived category $D(k)$ enriches $k\dash$modules.
:::


## Examples of Simplicial Categories

### a: Simplicial Sets and Topological Spaces

$\ssets \homotopic \Top$: this is not an equivalence of categories, but rather they have *equivalent homotopy theories*[^equiv_homotopy_theories], where we have notions of *weak equivalence*[^def_weak_equivalence] on each side.
Here there is an $n\dash$simplex on the LHS ($\ssets$), 
\[
\Delta^n = \hom_{\Delta}(\wait, [n])
\]
and on the RHS we have 
\[
\Delta^n_{\text{Top}}\da\ts{\tv{x_0, \cdots, x_n} \in \RR^n \st x_i\geq0,\, \sum x_i = 1}
\]

If you make a functor $\Delta^n \mapstofrom \Delta^n_{\text{Top}}$, then by Yoneda the presheaf category $\Presh(\Delta) \da \Fun(\Delta\op, \set)$ is generated by representable objects.
Everything on in $\ssets$ is generated by taking colimits of the $\Delta^n$, so we can make some assignment and extend by colimits to get a functor $\ssets \to \Top$.
We have a notion of weak equivalence for $\Top$, and so the notion of weak equivalence on $\ssets$ is just given by pullback along the functor $\ssets\to \Top$, and this induces an equivalence of homotopy theories.
The inverse functor $\Top \to \ssets$ is the **singular complex construction**.
Considering $\Delta^\wait_{\Top}$, this is a cosimplicial object in $\Top$.

:::{.remark}
$\Top$ will denote that 1-category, while $\mcTop$ will be its full $\infty\dash$category.
:::

So we have a natural cosimplicial object in $\Top$, 
so 
\[
\text{Sing}(X) \da \Hom_{\Top}(\Delta_{\Top}^\wait, X)
\]
is a simplicial object in $\ssets$.
As in singular homology, we can get a simplicial abelian group by taking the free abelian group $\ZZ[\Sing(X)]$.
Note that this is just composing functors $\Delta\op \to\Sets$ and $\Sets\to \mods{\ZZ}$.
We can use this to create a chain complex $C_\wait(\ZZ[\text{Sing}(X)])$, and as expected, we get the singular homology:
\[
H_i(C_\wait) \cong H^\Sing_i(X, \ZZ)
\]


[^def_weak_equivalence]: 
A **weak equivalence** is an isomorphism on $\pi_0$, and for each choice of basepoint, an isomorphism on all $\pi_{\geq 1}$ on each side.


[^equiv_homotopy_theories]: 
Theory up to weak equivalence.

### b: Simplicial Abelian Groups

We can take simplicial abelian groups $s\Ab$ and the connective objects $D(\ZZ)_{\geq 0}$; these have equivalent homotopy theories.
There is a notion of weak equivalence on the RHS, quasi-isomorphism, and asking if the literal underlying spaces on the LHS are weakly equivalence as spaces.
A specific way of doing this is the **Dold-Kan** correspondence:

:::{.proposition title="Dold-Kan Correspondence"}
Suppose we have a simplicial abelian group $M_\wait$, then we have face maps going to the left:
\begin{tikzcd}
  M_0
& M_1
  \ar[l, shift right=0.75ex, "\del_1"'] 
  \ar[l, shift left=0.75ex, "\del_2"] 
& M_2
  \ar[l, shift right=1.05ex] 
  \ar[l] 
  \ar[l, shift left=1.05ex] 
& \cdots
  \ar[l, shift right=2.15ex] 
  \ar[l, shift right=0.75ex] 
  \ar[l, shift left=0.75ex] 
  \ar[l, shift left=2.15ex] 
\end{tikzcd}
We make this into a chain complex by setting the differential to a graded sum:
\begin{tikzcd}
    M_0 
&&  M_1
  \ar[ll, "\sum (-1)^i \del_i"']
&&  M_2
  \ar[ll, "\sum (-1)^i \del_i"']
&&  \cdots
  \ar[ll]
\end{tikzcd}
The homology of this complex turns out to be the same as the homotopy groups of the simplicial abelian group viewed as a topological space.


:::

### c: Simplicial Commutative $k\dash$Algebras

Defined as 
\[
s\mathrm{CAlg}_k \da \Fun(\Delta\op,\mathrm{CAlg}_k)
,\]
where $k$ is some commutative ring.
This was studied by Quillen, and an impetus for model categories.
Models give a notion of weak equivalence and a "right way" of computing: for the usual derived category of a ring, this is taking free/projective/injective resolutions.
So the LHS is sometimes called a **non-abelian derived category**.

:::{.fact}
For $R\in \mathrm{sCAlg}$, the homotopy groups $\pi_* R$ have a graded commutative ring structure: $xy = (-1)^{\abs x \abs y}yx$ and $x^2 =0$ for elements $x$ with $\abs{x}$ odd. 
This is useful because it gives us some graded ring to associated to $R$.
:::

:::{.remark}
The category of simplicial abelian groups is equivalent to $\mathrm{Ch}(\ZZ)_{\geq 0}$; i.e. chain complexes of abelian groups concentrated in non-negative degree.
This also yields an equivalence of homotopy theories.
:::

A different perspective on simplicial commutative rings: 
there is an adjunction from sets to commutative $k\dash$algebras

\[  
\Set &\mapstofrom{}{} \mathrm{CAlg}_k \\
S &\mapsto K[S]
.\]
i.e. we send a set to the polynomial ring generated by $S$.
Any time such an adjunction exists, given an $R\in \mathrm{CAlg}_k$ we can construct a **simplicial resolution** $S^\wait$ and a map $S^\wait \to R$.
This resolution has the following structure:
\[  
S^0 = k[R], \,\, \text{the free commutative algebra on }R
.\]
Using the unit and counit maps of the adjunction, one obtains a canonical simplicial object,
\begin{tikzcd}
  k[R]
    \ar[r, shift right=2.0ex] 
    \ar[r, shift left=2.0ex] 
& k[k[R]] 
    \ar[l]
    \ar[r, shift right=2.0ex] 
    \ar[r] 
    \ar[r, shift left=2.0ex] 
& \cdots 
    \ar[l, shift right=1.00ex]
    \ar[l, shift left=1.00ex]
\end{tikzcd}
Moreover, $S^\wait \mapsvia{\sim} R$ is a homotopy equivalence.
So we've taken an arbitrary $k\dash$algebra and replaced it with a *simplicial* $k\dash$algebra which is given by polynomial rings in each degree, typically in infinitely many variables, which has the same homology.
This is the analog of a projective resolution.

Now define $\mathrm{CAlg}_k^{\text{poly}}$ as the category of finitely generated polynomial rings, and suppose you have a functor
\[  
\mathrm{CAlg}_k^{\text{poly}} 
\mapsvia{F} 
\mathcal{C}
\]
where $\mathcal{C}$ is a "reasonable" category or possible in $\infty\dash$category.
We can consider the category 
$\Ind(\mathrm{CAlg}_k^{\text{poly}})$ 
given by formally adjoining filtered colimits.
We have the following diagram,
\begin{tikzcd}
  \mathrm{CAlg}_k^{\text{poly}} 
    \ar[d, hook]
    \ar[r, "F"]
& \mathcal{C}
\\
  \Ind(\mathrm{CAlg}_k^{\text{poly}})
    \ar[d, hook, "\text{Constant diagrams}"']
    \ar[ur, "\exists \tilde F"']
& 
\\
  \mathrm{sCAlg}_k
  \ar[uur, bend right, "\exists LF"']
&
\end{tikzcd}
where the bottom inclusion is given by viewing a commutative ring as the constant simplicial commutative ring, and
the extension $\tilde F$ exists by applying $F$ to any colimit diagram.
The functor $LF$ is a derived functor that exists if $\mathcal{C}$ has certain colimits.

So starting with a functor defined on finitely generated polynomial rings, i.e. affine spaces, we get a simplicial derived functor.
For $R\in \mathrm{CAlg}_k$, using $S^\wait \mapsvia{\sim} R$, we can apply $F$ level-wise to get a new simplicial object $F(S^\wait) \in \mathcal{C}$.
Then $LF(R)$ is defined by taking the colimit over $\Delta$ yields the geometric realization, i.e. 
\[
LF(R) \da \hocolim_{\Delta} F(S^\wait) = \abs{F(S^\wait)}
\]
So we can promote functors on polynomial rings to functors on simplicial commutative rings.
This ends up being a Kan extension.
There is a nice universal property here, namely that functors out of $\mathrm{sAlg}_k$ are equivalent to functors out of $\mathrm{CAlg}_k^{\text{poly}}$ that satisfy some additional properties.

The last example will be the cotangent complex.

## The Cotangent Complex

There are 3 equivalent ways to view the cotangent complex.

### 1: A Derived Functor Approach

Use this derived functor approach: it will essentially be the derived functor of taking $\Omega^1$.
Suppose $k \to R$ in commutative rings, denote by $S^\wait$ again the canonical resolution of $R$, yielding a diagram
\begin{tikzcd}
k 
  \ar[rd, ""]
  \ar[rr, ""] 
& 
& R
\\
& S^\wait 
  \ar[ru, "\sim"] 
& 
\end{tikzcd}
Take Kahler differentials degree-wise to get 
$\Omega^1_{S^\wait/k}$
.
Now base-change along this map to get a simplicial $R\dash$module,
\[  
\Omega^1_{S^\wait/k} \tensor_{S^\wait} R \,\, \in \mathrm{sMod}\dash R
.\]
We can now use Dold-Kan to view this as a connective object in $D(R)_{\geq 0}$, the derived category of $R$, yielding $\mathrm{sMod}\dash R \homotopic D(R)_{\geq 0}$, so we define the **cotangent complex of $R/k$** as
\[  
L_{R/k} \da \Omega^1_{S^\wait/k} \tensor_{S^\wait} R \,\, \in D(R)_{\geq 0}
.\]

This turns out to work if you take a resolution other than the canonical one.
A downside to this definition is that it's not clear how/why it might depend on the resolution.


### 2: Extending Functors

We can define them by taking a map
\[  
\mathrm{CAlg}_k^{\text{poly}} \mapsvia{\Omega^1_{\wait/k}} D(k)_{\geq 0}
\]
to the connective objects in the derived category of $k$.
We can extend to get a diagram
\begin{tikzcd}
  \mathrm{CAlg}_k^{\text{poly}} 
  \ar[rr, "{\Omega^1_{\wait/k}}"] 
  \ar[dd, hook]
&& D(k)_{\geq 0}
\\
\\
  \mathrm{sCalg}_k
  \ar[rruu, "{\Omega^1_{\wait/k}}"'] 
&& 
\end{tikzcd}

It then turns out that
$L_{R/k} \homotopic L\Omega^1_{R/k}$.
Here it's not quite clear why this lands in $\mods{k}$ instead of $\mods{R}$, or how the $R\dash$module structure works here.

### 3: A Universal Property

Let $k\to R\to S$ where $k$ is a commutative ring and $R, S$ are ordinary (or simplicial) commutative rings.
Let $M\in \mods{S}$ in $D(S)_{\geq 0}$. 
There is a natural enrichment in topological spaces, so we'll write $\Map$ for homs with their topological structure.
In particular, these have homotopy groups.
The universal property that the cotangent complex has comes from an equivalence
\[  
\Map_R(L_{R/k}, M) 
\homotopic
\Map_{\mathrm{sCAlg}_{k//S}}(R, S\oplus M)
.\]
where the latter is in the category of simplicial commutative $k\dash$algebras with a *fixed* map to $S$, a bit like a comma category.
This makes sense because $R\to S$ is a fixed map, and $S\oplus M$ has a projection to $S$, i.e. this is a square zero extension.

:::{.remark}
The point of simplicial commutative rings is that this extension still makes sense, even when $M$ is a chain complex.
It's still possible to make this into a simplicial commutative ring.
This may look familiar from the exercises in Hartshorne, since it resembles the definition of Kahler differentials.
:::


#### Exercises Using the Universal Property

:::{.exercise title="?"}
Prove that
\[  
\pi_0 L_{R/k} \cong \Omega^1_{R/k}
.\]
This is exactly lifting through the square zero extension.
This is similar to having a lift
\begin{tikzcd}
& S\oplus M
    \ar[d]
\\
  R 
    \ar[r, "f"]
    \ar[ur, dotted, "\tilde f"]
& S
\end{tikzcd}
where giving $\tilde f$ is like giving a derivation $R\to M$.
So the RHS comma category mapping space in the previous equivalence is denoted the "space of derivations of $R$ and $M$" (whatever that means)
:::


:::{.exercise title="?"}
You can base-change the cotangent complex of $R/K$ to $S$ and obtain an exact triangle/cofiber sequence
\begin{tikzcd}
  S \tensor_R^L L_{R/k}
    \ar[r]
& L_{S/k}
    \ar[r]
&   L_{S/R}
\end{tikzcd}
This follows from the universal property above, and is a form of "transitivity".
:::

:::{.exercise title="?"}
Given a diagram
\begin{tikzcd}
  K 
    \ar[r]
    \ar[d]
& R 
    \ar[d]
\\
  T 
    \ar[r]
& R\tensor_k^L T 
\end{tikzcd}
show that 
\[  
T\tensor_k^L L_{R/k} \cong L_{R\tensor_k^L T / T}
.\]
:::

All of these follow from just the mapping space property, but require thinking about what it means to compute maps in a comma category.


:::{.exercise title="?"}
Let $R$ be a perfect $\FF_p\dash$algebra, so the Frobenius is an isomorphism:
\[  
F: R &\mapsvia{\sim} R\\
x &\mapsto x^p
.\]
Show that $L_{R/\FF_p} \cong 0$.
:::

## Derived de Rham Cohomology

We can make a specific functor:
\[  
\calg_k^{\poly} 
&\to
D(k)\\
R &\mapsto \dR_{R/k} \da \qty{R\to \Omega^1_{R/k} \to \Omega^2_{R/k} \to \cdots}
,\]
which takes a polynomial ring $R$ to its algebraic de Rham complex.
If $R$ is finitely generated, then the complex is bounded.
One can formally extend by deriving this functor to obtain
\begin{tikzcd}
  \calg_k^\poly 
    \ar[rr, "\dR_{\wait/k}"]
    \ar[dd, hook]
&&
  D(k)
\\ \\
  \scalg_k
    \ar[uurr, "L\dR_{\wait/k}"']
\end{tikzcd}

:::{.remark}
The point is that we know de Rham cohomology behaves well for smooth things, and we want to extend to non-smooth things.
:::

:::{.warnings}
Suppose $k \in \alg_\QQ$, noting that we're in characteristic zero, and let $R \in \calg_k^\poly$ be a polynomial ring.
Then $\dR_{R/k} \cong k$ by the Poincaré lemma, just the cohomology of affine space.
Then $L\dR_{S/k} \cong k$, which is disappointing.
:::

### The Hodge Filtration

How to fix this: we have the Hodge filtration $F_H^\wait \dR_{R/k}$, and the graded pieces are given by 
\[
\gr^i_H \dR_{R/k} \cong \Omega^i_{R/k}[-i] \cong \Lambda^i \Omega^1_{R/k}
,\]
a shifted version of the $i$th exterior power 1-forms.
Taking these gradings is compatible with colimits, so we can remember the filtration in the Kan extension, yielding a canonical Hodge filtration on $L\dR$, $F^*_H L \dR_{\wait/k}$.
The graded pieces are given by
\[  
\gr^i_H L\dR_{\wait /k} \cong L \Lambda^i L_{R/k}[-i]
,\]
i.e. you take derived exterior powers of the cotangent complex, shifted by some degrees.
This follows because doing the Kan extension on the graded pieces is deriving the functor $\gr^i_H \dR_{\wait/k}$.
We can complete with respect to this filtration, which we'll write has 

\[
\hat{L\dR_{\wait/k}} \da \inverselim L\dR_{\wait/k} / F_H^i
,\]
where you quotient out by the $i$th piece of the filtration.
Note that this definition is a general way of taking completions.[^what_its_like]

[^what_its_like]: 
This is like defining the $p\dash$adics as the limit of $\ZZ/p^n\ZZ$.


:::{.theorem title="Bhatt, Grothendieck, Hartshorne"}
Suppose $X/\CC$ is finite type, then
\[
R \Gamma(X,  \hat{ L\dR_{\OO_X/ k} } ) 
\cong
R \Gamma_{\Sing}(X(\CC), \CC)
,\]
where the RHS is the singular cohomology of the $\CC\dash$points.
This is a generalization of Grothendieck's theorem in the smooth case.
A positive feature is that this doesn't depend on a choice of putting $X$ in an ambient smooth scheme.
:::


