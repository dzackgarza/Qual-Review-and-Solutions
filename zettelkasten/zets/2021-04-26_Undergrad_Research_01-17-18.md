---
date: 2021-04-26
tags: 
  - Undergrad
---


# Research Meeting Notes, January 17

We began this session with me going over a bit of what I'd read the past week (mostly Postnikov tower and rational homotopy), and started with a question about some of the most trivial examples of spectral sequences. The reply was that the long exact sequence is probably the best example, but I still need to do a bit of work to see how the LES sits inside a SS (and also how Mayer Vietoris does).

I also mentioned a bit about what I'd read about sheaf and de-Rham cohomology, and we dove into the background of that a bit. We talked about the existence of smooth bump functions - functions that are identically zero outside of a compact interval. This is surprising! Consider things like $e^{-x^2/2}$, these are almost-but-not-quite zero away from zero. But you can define something like $e^{-1/x^2}\cdot\mathbb{1}[x > 0]$; this is actually smooth at zero but *decidedly* not analytic - it's not equal to its Taylor polynomial at zero (indeed, it is identically zero).

This highlights some of the differences that pop up in sheaf theory - we think of analytic objects as "rigid" and geometric, while smooth objects are somehow more "flexible". This is seen in analysis over $\CC^1$, where local knowledge of an analytic function determines its global behavior, but even over $\RR^1$ we find that there are many ways to continuously (and even smoothly) continue a function (e.g. extend by a polynomial of any degree in a piecewise fashion). So for $C^\infty$ manifolds, a lot more can happen.

We then segued into some intersection theory, especially over projective spaces. Some important ideas here were that in flexible situations, weird singular behaviors can be avoided. For example, intersections between curves with multiplicity $\RR^n$ can be perturbed slightly so that they either intersect with the "right" multiplicity, or not at all. For example, intersections of general conic sections $ax^2 + bxy + cy^2 + dx + ey + f$ in $\RR^2$ can be perturbed to intersect either twice or zero times, but interpolating between these two situations may coalesce the roots into a single point.

Over the complex numbers (since it is algebraically closed and curves are polynomials), the slight perturbation of (say) a quadratic will always deform singular points into two separate intersections. However, the singularities of the curves may be interesting themselves, and we might want information about those - so perturbing in such a way would result in losing that information. This is why algebraic geometry requires a bit more machinery, since we want to preserve information about these difficult spots.

The right sort of setting to study this kind of thing is usually a projective space of some kind. For example, one can take $\CP^2$ and adjoin an $S^2$ at infinity; then everything intersects this sphere. This is a way of compactifying the plane in order to make intersection theory more uniform - note that this is not the same a Stone-Cech compactification, which is just adding one point and declaring neighborhoods around it to be compact. (If I recall correctly). This is forming a compact space by pasting an entire separate space onto the boundary - for example, an entire line, or a circle or sphere.

Examples of this would be like $\CP^1 = \CC^1 \cup \{\infty\}$, or $\RP{2} = \RR^2 \cup \RP{1}$ (where we identify $\RP{1} \cong S^1$, this is adding a "circle at infinity" which every quadratic would intersect in two places (but really one, since they're identified)).

Some results this yields: any hyperbola can be "compactified" to a simple curve, in the right type of geometry. These essentially become sections of an ellipse in projective space - think of attaching a 2-cell to an equatorial 1-cell; then hyperbolas are sections of ellipses that intersect the equator.

When things are purely algebraic, though, a perfectly valid question to ask is something like where the locus $x^2 + y^2 = -1$ might lie (note that this has no real solutions). These is where you naturally go into $\CC^2$, and then compactify in the same sort of way to obtain $\CP^2 = \CC^2 \cup \CP^1$ where we can look at homogenous coordinates $[x:y:z]$. But then this is just a slice of the more general equation $x^2 + y^2 = -z^2$, for the case $z=1$. This leads naturally into classical algebraic geometry, where you hope for results like:

"The number of intersections of two curves of degrees $d_1, d_2$ is equal to $d_1\cdot d_2$".
