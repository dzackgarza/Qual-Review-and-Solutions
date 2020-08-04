# Extra Problems

## Basics
- Show that for $A\subseteq X$, $\cl_X(A)$ is the smallest closed subset containing $A$.
- Show that the diagonal map $\Delta(x) = (x, x)$ is continuous.
- Show that if $A_i \subseteq X$, then $\cl_X(\union_i A_i) = \union_i \cl_X(A_i)$.
- Show that $\RR$ is not homeomorphic to $[0, \infty)$.

## Topologies 
- Show that the set $(x, y) \in \RR^2$ such that at least one of $x, y$ is rational with the subspace topology is a connected space.


## Connectedness
- Prove that $X$ is connected iff the only clopen subsets are $\emptyset, X$.
- Show that:
  - Connected does not imply path connected
  - Connected and locally path connected *does* imply path connected
  - Path connected implies connected
- Use the fact that intervals are connected to prove the intermediate value theorem.
- Prove that the continuous image of a connected set is connected.
- Show that if $X$ is locally path connected, then 
  - Every open subset of $X$ is again locally path-connected.
  - $X$ is connected $\iff X$ is path-connected.
  - Every path component of $X$ is a connected component of $X$.
  - Every connected component of $X$ is open in $X$.
- Show that $[0, 1]$ is connected.
- Show that in a metrizable space
- Show that $[0, 1]$ is connected.
  \hyperref[problem:interval_is_connected_soln]{Solution} \label{problem:interval_is_connected}

## Compactness
- Show that every compact metric space is complete.
- Show that if $X$ is second countable and Hausdorff, or a metric space, then TFAE:
  - $X$ is compact
  - Every infinite subset $A\subseteq X$ has a limit point in $X$.
  - Every sequence in $X$ has a convergent subsequence in $X$. 
- Show that if $f: A\to B$ is a continuous map between metric spaces and $K\subset A$ is compact, then $\restrictionof{f}{K}$ is uniformly continuous.
- Show that if $f:X\to Y$ is continuous and $X$ is compact then $f(X)$ is compact.
- Show that if $f:X\to \RR$ and $X$ is compact then $f$ is bounded and attains its min/max.
- Show that a finite product or union compact spaces is again compact.
- Show that a quotient of a compact space is again compact.
- Show that if $X$ is compact and $A\subseteq X$ is closed then $A$ is compact.
- Show that if $X$ is Hausdorff and $A\subseteq X$ is compact then $A$ is closed.
- Show that if $X$ is a metric space and $A\subseteq X$ is compact then $A$ is bounded.
- Show that a continuous map from a compact space to a Hausdorff space is closed.
- Show that an injective continuous map from a compact space to a Hausdorff space is an embedding (a homeomorphism onto its image).
- Show that $[0, 1]$ is compact.
- Show that a compact Hausdorff space is is metrizable iff it is second-countable.
- Show that if $X$ is metrizable, then $X$ is compact
- Give an example of a space that is compact but not sequentially compact, and vice versa.
- Show that a sequentially compact space is totally bounded.
- Show that $\RR$ with the cofinite topology is compact.
- Show that $[0, 1]$ is compact without using the Heine-Borel theorem.

## Separation

- Show that $X$ is Hausdorff iff $\Delta(X)$ is closed in $X\cross X$.
- Prove that $X, Y$ are Hausdorff iff $X\cross Y$ is Hausdorff.
- Show that $\RR$ is separable.
- Show that any space with the indiscrete topology is separable.
- Show that any countable space with the discrete topology is separable.
- Show that the minimal uncountable order with the order topology is not separable.
- Show that every first countable space is second countable.
- Show that every metric space is Hausdorff in its metric topology.

## Hausdorff Spaces

- Show that a closed subset of a Hausdorff space need not be compact.
- Show that in a *compact* Hausdorff space, $A$ is closed iff $A$ is compact.
- Show that a local homeomorphism between compact Hausdorff spaces is a covering space.


## From Problem Sessions

1. Let $X$ be a compact space and let $A$ be a closed subspace. 
  Show that $A$ is compact. 
  \hyperref[problem:compact_closed_subspace_solution]{Solution} \label{problem:compact_closed_subspace}
  
2. Let $f : X \to Y$ be a continuous function, with $X$ compact. 
  Show that $f(X)$ is compact.
  \hyperref[problem:compact_continuous_soln]{Solution} \label{problem:compact_continuous}
 
3. Let $A$ be a compact subspace of a Hausdorff space $X$. 
  Show that $A$ is closed.
  \hyperref[problem:compact_closed_hausdorff_soln]{Solution} \label{problem:compact_closed_hausdorff}

4. Show that a continuous bijection from a compact space to a Hausdorff space is a homeomorphism.
  \hyperref[problem:continuous_bijection_hausdorff_soln]{Solution} \label{problem:continuous_bijection_hausdorff}

5. Let $A \subset X$ be a connected subspace.
  Show that if $B\subset X$ satisfies $A\subseteq B \subseteq \bar{A}$, then $B$ is connected.

6. Give an example of spaces $A\subseteq B \subseteq X$ such that $A$ is open in $B$ but $A$ is *not* open in $X$.\hyperref[problem:open_but_not_in_ambient_space_soln]{Solution} \label{problem:open_but_not_in_ambient_space}

7. Show that any infinite set with the cofinite topology is compact.

