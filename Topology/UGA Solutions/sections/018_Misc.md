# Miscellaneous Algebraic Topology



## 1 (Todo)

## 2 (Todo)

## 3

> Two techniques: show $f_* = 0$ or lift to a contractible universal cover.

- Any continuous map $\RP^2 \mapsvia{f} S^1\cross S^1$ induces a group morphism $\pi_1 \RP^2 \mapsvia{f_*} \pi_1(S^1\cross S^1)$
- Identify $\pi_1 \RP^2 = \ZZ/2\ZZ$ and $\pi_1(S^1\cross S^1) = \pi_1 S^1 \cross \pi_1 S^1 = \ZZ^2$.
- But as a $\ZZ\dash$module morphism, $f_*$ will preserve torsion submodules, and since $\ZZ^2$ is free we must have $f_* = 0$.

- Lemma: $f_* = 0$ implies $f$ is nullhomotopic. \todo{Why? What is the homotopy?}
  - Note that $\widetilde{S^1\cross S^1} = \RR^2$.


## 4

- Any continuous map $\RP^n \mapsvia{f} S^1$ induces a group morphism $\pi_1\RP^n \mapsvia{f_*} \pi_1S^1$
- Identify $\pi_1\RP^n = \ZZ/2\ZZ$ and $\pi_1S^1 = \ZZ$ to obtain a group morphism $f_*: \ZZ/2\ZZ \to \ZZ$.
- Claim: $f_* = 0$.
  - Recognizing this as a map of $\ZZ\dash$modules, we must have
  \[  
  0 = [2]_2 = 2\cdot [1]_2  \implies 0 = f_*(0) = 2\cdot f_*([1]_2)
  .\]
    since $\ZZ\dash$module maps send 0 to 0.

  - But no element of the image $\ZZ$ is annihilated by $2$, so $f_*$ can only be the zero map.

- But then $f$ is nullhomotopic.

- Lemma: $f_* = 0$ implies $f$ is nullhomotopic. \todo{Why?}

## 5 (Todo)

## 6

- Note that "homotopic to a constant function" equivalently means "nullhomotopic".
- Since $f$ is not surjective, there is some point $x_0\not\in\im(f)$, and thus $f$ descends to a map $g: S^3\cross S^3 \to \RP^3\setminus\theset{x_0}$.
- Claim: the codomain deformation retracts onto $\RP^2$.
  - Why: puncture the sphere at two antipodal points
  - Then retract each hemisphere onto the equator
  - Which is a copy of $\RP^2$.

- So $f$ induces a map on $\pi_1$, $f_*:\ZZ^2 \to \ZZ/2\ZZ$
