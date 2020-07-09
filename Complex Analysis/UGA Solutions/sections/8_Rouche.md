# Rouche's Theorem (8155h)

## 1

Note

- $f_1(z) = 1+z$, which has the single root $z=-1$ which is not inside $\abs{z} < 1$.
- $f_2(z) = 1 + z + {1\over 2}z^2 = (z - (1+i))(z- (1-i))$, and $\abs{1\pm i} = \sqrt 2 >1$.

- Note that $p_n(z) \converges{n\to\infty}e^z$ uniformly on any compact set.
- Let $r$ be arbitrary and fix $N \definedas \DD_r(0)$, then $p_n(z) \to e^z$ uniformly on $\bar{N}$.
- Set $g_n(z) \definedas p_n(z) / e^z$, then $g_n \to 1$ uniformly on $\bar N$.
- Choose $n\gg 0$ so that $\abs{f(z) - 1} < \eps < 1$ for all $z\in \bar{N}$.
- So take $h(z) = 1$, then on $\bd N$,?


## 2

> Multiple versions of Rouches theorem!

- Set $h(z) = 3z^2$ and $g(z) = z^3 + bz + b^2$.
- Then on $\abs{z} = 1$,
\begin{align*}
\abs{g(z)} \leq 1 + b + b^2 < 3 = 3\abs{z}^2 = \abs{3z^2} = \abs{h}
,\end{align*}
  so $g, h$ have the same number of roots in $\abs{z} \leq_? 1$.

- But $h$ evidently has two roots in this region.


## 4

- Set $h(z) = -4z^3$ and $g(z) = z^7 - 1$, then on $\abs{z} = 1$,
\begin{align*}
\abs{g(z)} = \abs{z^7 - 1} \leq 1 + 1 = 2 < 4 = \abs{-4z^3} = \abs{h(z)}
.\end{align*}

- So $h$ and $h+g$ have the same number of roots, but $h$ has three roots here.

 
