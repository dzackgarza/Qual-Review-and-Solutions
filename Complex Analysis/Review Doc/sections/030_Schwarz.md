# Schwarz Reflection

## Schwarz

:::{.theorem title="Schwarz Lemma" ref="SchwarzzLemma"}
If $f: \DD \to \DD$ is holomorphic with $f(0) = 0$, then

1. $\abs{f(z)} \leq \abs z$ for all $z\in \DD$
2. $\abs{f'(0)} \leq 1$.

Moreover, if 

- $\abs{f(z_0)} = \abs{z_0}$ for any $z_0\in \DD$, or 
- $\abs{f'(0)} = 1$, 

then $f$ is a rotation.
:::


:::{.proof title="?"}
\envlist

- Idea: apply the maximum modulus principle to $g(z) \da f(z)/z$.
- $\abs{g(z)} \leq 1$:
  - Expand $f$ at $z=0$ as $\sum_{k\geq 0} c_k z^k$.
    Since $f(0) = c_0$, we have $c_0 = 0$.
  - So $g(z) \da f(z)/z$ is holomorphic, since the singularity at $z=0$ is removable.
  - Set $\abs{z} = r < 1$, then $\abs{g(z)} = \abs{f(z)}/r \leq 1/r$ since $\abs{f(z)} \leq 1$.
  - By MMP, $\abs{g(z)} \leq 1/r$ holds in the entire disc $\abs{z} \leq r$, so take $r\to 1$ to get $\abs{g(z)} \leq 1$
- $\abs{f(z_0)} = \abs{z_0}\implies f$ is a rotation:
  - $g$ attains a maximum on $\abs{z}\leq 1$, making it constant, so $f(z) = cz$.
  - Then $\abs{z_0} = \abs{f(z_0)} = \abs{cz_0}$ since $f(z_0) = z_0$, so $\abs{c} = 1$ and $c = e^{i\theta}$ for some $\theta$.
:::


:::{.exercise title="?"}
Show that $\Aut_\CC(\CC) = \ts{ z \mapsto az+b\st a\in \CC\units, b\in \CC }$.
:::


:::{.theorem title="Biholomorphisms of the disc"}
\[
\Aut_\CC(\DD) = \ts{ z\mapsto e^{i\theta} \qty{\alpha - z \over 1 - \bar{\alpha} z} }
.\]
:::

:::{.proof title="?"}
Schwarz lemma.
:::


:::{.theorem title="?"}
\[
\Aut_\CC(\HH) = \ts{ z \mapsto {az+b \over cz+d} \st a,b,c,d\in \CC, ad-bc=1 } \cong\PSL_2(\RR)
.\]
:::



\todo[inline]{?}

# Schwarz Lemma

\todo[inline]{?}

\todo[inline]{Montel's theorem}

\todo[inline]{Normal families}

\todo[inline]{Schwarz lemma}

\todo[inline]{Equicontinuity}






