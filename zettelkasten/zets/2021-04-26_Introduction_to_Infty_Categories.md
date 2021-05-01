---
date: 2020-11-28
tags: 
  - Unfiled
---

# Introduction to $\infty\dash$Categories

> These are notes roughly transcribed from [this video](https://www.youtube.com/watch?v=3IjAy0gHRyY)

## Preliminary Definitions

Dealing with size issues: take a Grothendieck Universe $\mathcal{U}$, which are the sets whose subsets are closed under all of the usual set operations (small).


:::{.definition title="$\infty\dash$Category"}
An $\infty\dash$category $\mathcal{C}$ is a (large) simplicial set $\mathcal{C}$ such that any diagram of the form

\begin{tikzcd}
	{\Lambda_i^n} && {\mathcal{C}} \\
	\\
	{\Delta_n}
	\arrow[from=1-1, to=3-1]
	\arrow[from=1-1, to=1-3]
	\arrow["{\exists}"', from=3-1, to=1-3, dashed]
\end{tikzcd}

admits the indicated lift, where $\Lambda_i^n$ is an $i\dash$horn (a simplex missing the $i$th face) for $0 < i < n$.
:::


:::{.remark}
This is a specialized notion of a Kan complex, and in particular all $\infty\dash$categories are Kan complexes.
All inner horns are fillable, i.e. simplicial sets are *inner* Kan complexes.
Different to Kan complexes, which include all $i$.
:::

:::{.definition title="Functors between $\infty\dash$categories"}
A **functor** between two $\infty\dash$categories is a map between simplicial sets.
:::

:::{.definition title="Nerve of a category"}
Given an ordinary category $\mathcal{C}$, define the **nerve** of $\mathcal{C}$ to be the simplicial set given by
\[  
N(\mathcal{C})_n \da \ts{\text{Functors } F: [n] \to \mathcal{C}}
\]
where $[n]$ is the poset category on $\ts{1, 2, \cdots, n}$.
So an $n\dash$simplex is a diagram of objects $X_0, \cdots, X_n \in \Ob(\mathcal{C})$ and a sequence of maps.
This defines an $\infty\dash$category, and there is a correspondence
\[  
\correspond{\text{ Functors } F: \mathcal{C} \to \mathcal{D}}
&\iff
\correspond{\infty\dash\text{Functors } \hat F: N(\mathcal{C}) \to N(\mathcal{D})}
.\]
Note that taking the nerve of a category preserves the usual categorical structure, since the objects are the 0-simplices and the morphisms are the 1-simplices.
:::



:::{.remark}
For $\mathcal{C}$ an $\infty\dash$category, we can define $\mathcal{C}_0$ to be the "objects" and $\mathcal{C}_1$ to be the "morphisms", although we don't have a good notion of composition yet.
There will be boundary map: a 1-simplex has two boundary points, i.e. two objects $a, b \in \mathcal{C}_0$, so we can think of this as a map $f: a\to b$ where $a = \del_1 f, b= \del_0 f$[^on_bd_notation]
are the first and second vertices respectively.
We'll also have "degeneracy" maps going up from $\mathcal{C}_0 \to \mathcal{C}_1$, which we should think of as assigning identity morphisms to objects, or conversely that the identity morphism is the degenerate 1-simplex at an object.

[^on_bd_notation]: This notation $\bd_i$ denotes the boundary operator that drops the $i$th vertex. 

:::

## Equivalences

:::{.definition title="Equivalence of Morphisms"}
Given two morphisms $f, g: a\to b$ in an $\infty\dash$category, we say $f\homotopic g$ are **equivalent** iff there is a 2-simplex filling in the following diagram:

\begin{tikzcd}
    && {b}  \\
    &&      \\
{a} && {b}
\arrow["{\id_b}", from=1-3, to=3-3]
\arrow["{f}"{name=0}, from=3-1, to=1-3]
\arrow["{g}"', from=3-1, to=3-3]
\arrow[Rightarrow, from=0, to=3-3, shorten <=4pt, shorten >=4pt]
\end{tikzcd}
[Link to diagram](https://q.uiver.app/?q=WzAsMyxbMCwyLCJhIl0sWzIsMCwiYiJdLFsyLDIsImIiXSxbMSwyLCJcXGlkX2IiXSxbMCwxLCJmIl0sWzAsMiwiZyIsMl0sWzQsMiwiIiwwLHsibGVuZ3RoIjo3MH1dXQ==)

:::

:::{.remark}
This turns out to be an equivalence relation.
Note that in an ordinary category, if two morphisms are equivalent then they are already equal.
:::

:::{.definition title="Composition of morphisms"}
For 1-simplices $f: a\to b, g:b\to c$, a **composition** of $f$ and $g$ is a 2-simplex $\sigma$ filling in the following diagram:
\begin{tikzcd}
	&& {b} \\
	\\
	{a} &&&& {c}
	\arrow["{f}", from=3-1, to=1-3]
	\arrow["{g}", from=1-3, to=3-5]
	\arrow["{\exists h}"' {name=0, inner sep=0}, from=3-1, to=3-5, dotted]
	\arrow[Rightarrow, from=0, to=1-3, shorten <=6pt, shorten >=6pt, "\sigma"]
\end{tikzcd}
[Link to diagram](https://q.uiver.app/?q=WzAsMyxbMCwyLCJhIl0sWzQsMiwiYyJdLFsyLDAsImIiXSxbMCwyLCJmIl0sWzIsMSwiZyJdLFswLDFdLFs1LDIsIiIsMCx7Imxlbmd0aCI6NzB9XV0=)

In this case, $h \da \bd_1 \sigma$ and we write $h \homotopic g\circ f$.
:::

:::{.remark}
Note that we're not fixing a choice, but it is well-defined up to the equivalence relation we're using.
This is similar to how e.g. coproducts are not baked into the structure of a category, but are instead only well-defined up to canonical isomorphism -- and in fact, this characterization is sometimes preferable.
:::


:::{.definition title="Equivalences of objects"}
If $f: a\to b$ is a morphism in an $\infty\dash$category $\mathcal{C}$, then we say $f$ is an **equivalence** if there exists a morphism $g:b\to a$ such that $\id_a \homotopic g\circ f$ and $\id_b \homotopic f\circ g$.
This is equivalent to finding 2-simplices $\sigma, \sigma'$ that fill the following two diagrams:


\begin{tikzcd}
	&& {b} \\
	&&&&& {} \\
	{a} && {a} && {b}
	\arrow["{f}"{name=0}, from=3-1, to=1-3]
	\arrow["{\exists g}", from=1-3, to=3-3, dashed]
	\arrow["{\id_a}"', from=3-1, to=3-3]
	\arrow["{\id_b}"{name=1}, from=1-3, to=3-5]
	\arrow["{\exists g}", from=3-5, to=3-3, dashed]
	\arrow[Rightarrow, "{\sigma}"', from=0, to=3-3, shorten <=4pt, shorten >=4pt]
	\arrow[Rightarrow, "{\sigma'}", from=1, to=3-3, shorten <=4pt, shorten >=4pt]
\end{tikzcd}
[Link to diagram](https://q.uiver.app/?q=WzAsNSxbMCwyLCJhIl0sWzIsMCwiYiJdLFsyLDIsImEiXSxbNSwxXSxbNCwyLCJiIl0sWzAsMSwiZiJdLFsxLDIsIlxcZXhpc3RzIGciLDAseyJzdHlsZSI6eyJib2R5Ijp7Im5hbWUiOiJkYXNoZWQifX19XSxbMCwyLCJcXGlkX2EiLDJdLFsxLDQsIlxcaWRfYiJdLFs0LDIsIlxcZXhpc3RzIGciLDAseyJzdHlsZSI6eyJib2R5Ijp7Im5hbWUiOiJkYXNoZWQifX19XSxbNSwyLCJcXHNpZ21hIiwyLHsibGVuZ3RoIjo3MH1dLFs4LDIsIlxcc2lnbWEnIiwwLHsibGVuZ3RoIjo3MH1dXQ==)

:::

:::{.remark}
This is close to what we'd require for an isomorphism in an ordinary category, but we now allow the compositions to only be "weakly equivalent" or homotopic to the identities.
:::

:::{.definition title="Functor Categories"}
For $\mathcal{C}, \mathcal{D}$ simplicial sets, we can define a simplicial set $\Fun(\mathcal{C}, \mathcal{D})$ whose $n\dash$simplices are given by
\[  
\Fun(\mathcal{C}, \mathcal{D})_n \da \ts{ \text{Simplicial maps } F: \mathcal{C} \cross \Delta^n \to \mathcal{D}}
.\]
:::

:::{.remark}
Note that the 0-simplices recover functors if these are ordinary categories.
If $\mathcal{D}$ is an $\infty\dash$category, then this functor category is again an $\infty\dash$category.

:::

:::{.definition title="Morphisms of functors / natural transformations"}
A **morphism** in $\Fun(\mathcal{C}, \mathcal{D})$, say $\eta: F\to G$, is a functor $\eta: C\cross \Delta^n \to \mathcal{D}$ such that
\[  
\ro{\eta}{\mathcal{C} \cross \ts{0}} &= F \\
\ro{\eta}{\mathcal{C} \cross \ts{1}} &= G
.\]
We call such an $\eta$ a **natural transformation** from $F$ to $G$.
:::

:::{.remark}
Being an equivalence in $\Fun(\mathcal{C}, \mathcal{D})$ is equivalent to being a pointwise equivalence.
I.e., $\eta$ is an equivalence iff the map $\eta_{{C}}$ given by partially applying an object of $\mathcal{C}$ (i.e. a 1-simplex $\Delta^n \to \mathcal{D}$) is an equivalence in $\mathcal{D}$ for all objects $C\in \Ob(\mathcal{C})$.
:::

:::{.definition title="Equivalences of $\infty\dash$categories"}
A functor $f:\mathcal{C}\to \mathcal{D}$ of $\infty\dash$categories is an **equivalence** iff there exists a functor $g: \mathcal{D}\to \mathcal{C}$ and natural equivalences
\[  
f\circ g &\mapsvia{\sim} \id_{\mathcal{D}} \\
g\circ f &\mapsvia{\sim} \id_{\mathcal{C}} 
.\]
If there exists such an equivalence, we will write $\mathcal{C}\homotopic \mathcal{D}$.
:::

:::{.remark}
For ordinary categories, there is a characteristic property that is much easier to write down in general than an explicit equivalence, namely being essentially surjective and fully faithful.
We need the notion of mapping spaces to make that precise here.
:::

## Composition

:::{.definition title="Mapping Spaces"}
For $a, b\in \Ob(\mathcal{C})$, we define a simplicial set $\Map_{\mathcal{C}}(a, b)$ as the following pullback:

\begin{tikzcd}
	{\Map_{\mathcal{C}}(a, b)} && {\Fun(\Delta^1, \mathcal{C})} \\
	& {} \\
	{\Delta^0} && {\mathcal{C} \cross \mathcal{C}}
	\arrow["{(f, g)}", from=1-3, to=3-3]
	\arrow["{(a, b)}"', from=3-1, to=3-3]
	\arrow[from=1-1, to=3-1, dashed]
	\arrow[from=1-1, to=1-3, dashed]
	\arrow["\lrcorner"{very near start, rotate=0}, from=1-1, to=2-2, phantom]
\end{tikzcd}
[Link to diagram](https://q.uiver.app/?q=WzAsNSxbMCwwLCJNYXAoYSwgYikiXSxbMiwwLCJcXEZ1bihcXERlbHRhXm4sIFxcbWF0aGNhbHtDfSkiXSxbMCwyLCJcXERlbHRhXjAiXSxbMiwyLCJcXG1hdGhjYWx7Q30gXFxjcm9zcyBcXG1hdGhjYWx7Q30iXSxbMSwxXSxbMSwzXSxbMiwzLCIoYSwgYikiLDJdLFswLDIsIiIsMix7InN0eWxlIjp7ImJvZHkiOnsibmFtZSI6ImRhc2hlZCJ9fX1dLFswLDEsIiIsMCx7InN0eWxlIjp7ImJvZHkiOnsibmFtZSI6ImRhc2hlZCJ9fX1dLFswLDQsIiIsMCx7InN0eWxlIjp7Im5hbWUiOiJjb3JuZXIifX1dXQ==)

:::

:::{.remark}
Here we use the fact if $F\in \Fun(\Delta^1, \mathcal{C})$, this data includes two maps $f, g: \Delta^0 \to \mathcal{C}$ given by restricting to the two vertices of $\Delta^1$.
This allows us to define a map $(f, g)$ into $\mathcal{C}^2$.
In that product, we also have the point $a, b$, which allows defining the bottom map $(a, b)$.

Also note that if $\mathcal{C}$ is in fact an $\infty\dash$category, then $\Map_{\mathcal{C}}(a, b)$ is a Kan complex.
The 0-simplices in it are precisely the morphisms in $\Fun(\Delta^n, \mathcal{C})$ with endpoints $a, b$, and there is a filling 1-simplex between any two such morphisms iff they are equivalent.
We can thus conclude that
\[  
\pi_0 \Map_{\mathcal{C}}(a, b) = \ts{\text{Equivalence classes of morphism } f:a\to b}
.\]
:::

:::{.definition title="Fully Faithful"}
A functor $f: \mathcal{C} \to \mathcal{D}$ is **fully faithful** the induced maps
\[  
f_*: \Map_{\mathcal{C}}(a, b) \to \Map_{\mathcal{D}}(f(a), f(b))
\]
is a homotopy equivalence of Kan complexes for all pairs of objects $a, b\in \Ob(\mathcal{C})$.
:::

:::{.remark}
Note that this does imply bijections on (equivalence classes) of morphisms in hom sets, i.e. on $\pi_0$, but in general this is much more because we are requiring an induced isomorphism on all higher homotopy groups as well.
:::

:::{.warnings}
This is not something that can easily be checked on *just* morphisms.
:::

:::{.definition title="Essentially Surjective"}
A functor $f:\mathcal{C}\to \mathcal{D}$ is **essentially surjective** iff for every $d\in \mathcal{D}$, there exists an object $c\in \mathcal{C}$ and an equivalence $d \homotopic f(c)$.
:::

:::{.theorem title="Characterization of equivalence of $\infty\dash$categories"}
A functor $f: \mathcal{C}\to \mathcal{D}$ is an equivalence iff $f$ is fully faithful and essentially surjective.
:::

:::{.definition title="Full Subcategories"}
Let $S \subset \mathcal{C}_0$ be some subset of objects, and define $\mathcal{C}_S \subset \mathcal{C}$ as a simplicial subset given by 
\[  
\mathcal{C}_S \da \ts{\text{All simplices with vertices in } S}
.\]
:::

:::{.remark}
That this is an $\infty\dash$category follows from checking definitions.

If we first *saturate* $S$ under equivalence of objects, i.e. form the larger subset $\bar S \supseteq S$ consisting of all objects in $\mathcal{C}$ which are equivalent to some object in $S$, this produces a functor
\[  
F: \mathcal{C}_S \injects \mathcal{C}_{\bar S}
,\]
which is fully faithful and essentially surjective[^why_obvious] and thus an equivalence.
So if you're interested in categories up to equivalence, this replacement is always a valid move.

[^why_obvious]: This is purportedly "obvious": being essentially surjective is clear, and fully faithful follows from defining mapping spaces as pullbacks, and writing it out yields an equality of simplicial sets.

:::


## Homotopic (and Contractible Spaces of) Choices

:::{.remark}
Note that the pullback construction from before seems to generalize:

\begin{tikzcd}
	{\Map_{\mathcal{C}}\qty{\ts{a_1, \cdots, a_n}} } && {\Fun(\Delta^{n-1}, \mathcal{C})} \\
	& {} \\
	{\Delta^0} && {\mathcal{C}^n}
	\arrow[from=1-3, to=3-3]
	\arrow[from=3-1, to=3-3]
	\arrow[from=1-1, to=3-1, dashed]
	\arrow[from=1-1, to=1-3, dashed]
	\arrow["\lrcorner"{very near start, rotate=0}, from=1-1, to=2-2, phantom]
\end{tikzcd}
[Link to diagram](https://q.uiver.app/?q=WzAsNSxbMCwwLCJNYXAoYSwgYikiXSxbMiwwLCJcXEZ1bihcXERlbHRhXm4sIFxcbWF0aGNhbHtDfSkiXSxbMCwyLCJcXERlbHRhXjAiXSxbMiwyLCJcXG1hdGhjYWx7Q30gXFxjcm9zcyBcXG1hdGhjYWx7Q30iXSxbMSwxXSxbMSwzXSxbMiwzLCIoYSwgYikiLDJdLFswLDIsIiIsMix7InN0eWxlIjp7ImJvZHkiOnsibmFtZSI6ImRhc2hlZCJ9fX1dLFswLDEsIiIsMCx7InN0eWxlIjp7ImJvZHkiOnsibmFtZSI6ImRhc2hlZCJ9fX1dLFswLDQsIiIsMCx7InN0eWxlIjp7Im5hbWUiOiJjb3JuZXIifX1dXQ==)

This can be thought of as the space of $n\dash$simplices whose vertices are at the $n+1$ given objects.
We can define compositions of morphisms by taking $n=3$, and applying boundary operators yields maps


\begin{tikzcd}
	&& {\Map_{\mathcal C}(a,b,c)} \\
	\\
	{\Map_{\mathcal C}(b,c) \cross \Map_{\mathcal C}(a, b)} &&&& {\Map_{\mathcal C}(a, c)}
	\arrow["{\bd_1}", from=1-3, to=3-5]
	\arrow["{f = (\bd_0, \bd_2)}"', from=1-3, to=3-1]
	\arrow["{\exists h}"', from=3-1, to=3-5, dashed]
\end{tikzcd}
[Link to diagram](https://q.uiver.app/?q=WzAsMyxbMiwwLCJcXE1hcF97XFxtYXRoY2FsIEN9KGEsYixjKSJdLFs0LDIsIlxcTWFwX3tcXG1hdGhjYWwgQ30oYSwgYykiXSxbMCwyLCJcXE1hcF97XFxtYXRoY2FsIEN9KGIsYykgXFxjcm9zcyBcXE1hcF97XFxtYXRoY2FsIEN9KGEsIGIpIl0sWzAsMSwiXFxiZF8xIl0sWzAsMiwiZiA9IChcXGJkXzAsIFxcYmRfMikiLDJdLFsyLDEsIlxcZXhpc3RzIGgiLDIseyJzdHlsZSI6eyJib2R5Ijp7Im5hbWUiOiJkYXNoZWQifX19XV0=)

where the existence of $h$ follows from the fact that $f$ is an equivalence and can thus be inverted.
This is induced by maps on Kan complexes

\begin{tikzcd}
	&& {\Delta^2} \\
	\\
	{\Lambda_1^2} &&&& {\Delta^1}
	\arrow[from=3-1, to=1-3]
	\arrow[from=3-5, to=1-3, hook']
	\arrow[from=3-1, to=3-5, dashed]
\end{tikzcd}
[Link to diagram](https://q.uiver.app/?q=WzAsMyxbMiwwLCJcXERlbHRhXjIiXSxbMCwyLCJcXExhbWJkYV8xXjIiXSxbNCwyLCJcXERlbHRhXjEiXSxbMSwwXSxbMiwwLCIiLDIseyJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6ImJvdHRvbSJ9fX1dLFsxLDIsIiIsMix7InN0eWxlIjp7ImJvZHkiOnsibmFtZSI6ImRhc2hlZCJ9fX1dXQ==)

where we're taking the inner horn and the outer face respectively.
This can be thought of as horn-filling in families.
:::

:::{.remark}
Why is this important?
Given two morphisms, we can pick a composition, and there are multiple ways to do so.
We can then look at the middle face to define the actual composition, up to equivalence of morphisms.
This relies on a choice of homotopy inverse $s$, allowing us to define a map $\circ_s$.
But given an equivalence, there is a unique homotopy inverse up to homotopy, so any two choices of $s$, say $s$ and $s'$ give homotopic maps $\circ_s$ and $\circ_{s'}$.
In good situations, we have even more: the space of such choices will be contractible, which is stronger than there just being a homotopy between any two choices.
So composition is "unique", it's just that there's not one preferred choice.
:::

:::{.remark}
Associativity follows from a similar line of reasoning applied to $\Map_{\mathcal{C}}(a,b,c,d)$ on four objects.
Compare this to Segal categories, where such spaces are part of the data: categories weakly enriched in spaces, and $\infty\dash$categories recover this for free.
There is a way to think of $\infty\dash$categories as "categories enriched in Kan complexes" with a more strict condition of associativity.
:::

:::{.remark}
We recover all of ordinary category theory when the mapping spaces are discrete.
Looking at Kan complexes also yields $\infty\dash$categories where all of the morphisms are invertible, so these are in fact $\infty\dash$groupoids.
For us, "spaces" and Kan complexes are synonymous, and the $\infty\dash$category of spaces will be the fundamental example we run with.
:::

