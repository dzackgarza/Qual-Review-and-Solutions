# Homology

## Useful Facts

:::{.proposition title="Homology commutes with wedge products"}
\[
\tilde H_*(A\vee B) &\cong H_*(A) \times H_*(B) \\
H_{n}\qty{\bigvee_\alpha X_\alpha} &\cong \prod_\alpha H_{n} X_\alpha
\]
See footnotes for categorical interpretation.[^wedge]
:::
\todo[inline]{May need some good pair condition?}

:::{.example title="Application"}
\[
H_{n}(\bigvee_{k} S^n) = \ZZ^k
.\]
:::

:::{.proof title="?"}
Mayer-Vietoris. 
:::

:::{.warnings}
$H_{k} \qty{ \prod_ \alpha X_ \alpha}$ is **not** generally equal to $\prod_ \alpha \qty{ H_{k} X_ \alpha }$.
The obstruction is due to torsion -- if all groups are torsionfree, then the Kunneth theorem[^kunneth] yields 
\[
H_{k} (A\cross B) = \prod_{i+j=k} H_{i} A \tensor H_{j} B
\]
:::

:::{.theorem title="Excision"}
Todo
:::
\todo[inline]{Excision.}

- $H_{n}(X) = 0 \iff X$ has no $n\dash$cells.
- $C^0 X = \pt \implies d_{1}: C^1 \to C^0$ is the zero map.

## Known Homology

:::{.example title="Spheres"}
\[
H_{i}(S^n) = 
\begin{cases}
\ZZ & i = 0, n
\\
0 & \text{else}.
\end{cases}
\]
:::


:::{.example title="Real Projective Spaces"}

:::

:::{.example title="Complex Projective Spaces"}

:::

:::{.example title="Surfaces"}

:::

\todo[inline]{Homology examples.}

## Mayer-Vietoris

:::{.fact title="Useful algebra fact"}
Since $\ZZ$ is free and thus projective, any exact sequence of the form $0 \to \ZZ^n \to A \to \ZZ^m \to 0$ splits and $A\cong \ZZ^{n}\cross \ZZ^m$.
:::

:::{.theorem title="Mayer-Vietoris"}
> Mnemonic: $X = A \union B \leadsto (\intersect, \oplus, \union)$

Let $X = A^\circ \union B^\circ$; then there is a SES of chain complexes
\[
0 \to C_{n}(A\intersect B) \mapsvia{x\mapsto (x, -x)} C_{n}(A) \oplus C_{n}(B) \mapsvia{(x, y) \mapsto x+y} C_{n}(A + B) \to 0
\]
where $C_{n}(A+B)$ denotes the chains that are sums of chains in $A$ and chains in $B$.
This yields a LES in homology:
\[
\cdots  H_{n}(A \cap B) \xrightarrow{(i^*,~ j^*)} H_{n}(A) \oplus H_{n}(B) \xrightarrow{l^* - r^*}  H_{n}(X) \xrightarrow{\delta} H_{n-1}(A\cap B)\cdots
\]
where

- $i: A\cap B \hookrightarrow A$ induces $i^*: H_*(A\cap B) \to H_*(A)$

- $j: A\cap B \hookrightarrow B$ induces $j^*: H_*(A\cap B) \to H_*(B)$

- $l: A \hookrightarrow A\cup B$ induces $l^*: H_*(A) \to H_*(X)$

- $r: B \hookrightarrow A\cup B$ induces $r^*: H_*(B) \to H_*(X)$



More explicitly, 

\begin{tikzcd}
 &  &  &  & \cdots \arrow[lllldd, out=0, in=-180, "\delta_{3}"'] 
 \\
 &  &  &  &  
 \\
H_{2}(A\cap B) \arrow[rr] \arrow[rr, "{(i^*, -j^*)_2}"] &  & H_{2} A \oplus H_{2} B \arrow[rr, "(l^* - r^*)_2"] &  & H_{2} (A\cup B) \arrow[lllldd, "\delta_{2}"', out=0, in=-180] 
\\
 &  &  &  &  
 \\
H_{1}(A\cap B) \arrow[rr, "{(i^*, -j^*)_1}"] &  & H_{1} A \oplus H_{1} B \arrow[rr, "(l^*-r^*)_1"] &  & H_{1} (A\cup B) \arrow[lllldd, "\delta_{1}"', out=0, in=-180] 
\\
 &  &  &  &  
 \\
H_{0} (A\cap B) \arrow[rr, "{(i^*, -j^*)_0}"] &  & H_{0} A \oplus H_{0} B \arrow[rr, "(l^* - r^*)_0"] &  & H_{0} (A\cup B) \arrow[lllldd, "\delta_{0}"', out=0, in=-180] 
\\
 &  &  &  &  
 \\
0 &  &  &  &
\end{tikzcd}

The connecting homomorphisms $\delta_{n} :H_{n}(X) \to H_{n-1}(X)$ are defined by taking a class $[\alpha] \in H_{n}(X)$, writing it as an $n$-cycle $z$, then decomposing $z = \sum c_{i}$ where each $c_{i}$ is an $x+y$ chain. Then $\del(c_{i}) = \del(x+y) = 0$, since the boundary of a cycle is zero, so $\del(x) = -\del(y)$. So then just define $\delta([\alpha]) = [\del x] = [-\del y]$.

Handy mnemonic diagram:
\[
\begin{matrix}
 && A\intersect B & \\
&\diagup &  & \diagdown \\
A\union B & & \longleftarrow &  & A \oplus B
\end{matrix}
.\]

:::

:::{.example title="Application: computing the homology of a connect sum"}
$H_*(A \# B)$: Use the fact that $A\# B = A \union_{S^n} B$ to apply Mayer-Vietoris.
:::


### Application: Isomorphisms in the homology of spheres.

:::{.proposition title="?"}
\[H^i(S^n) \cong H^{i-1}(S^{n-1}).\]
:::

:::{.proof}
Write $X = A \cup B$, the northern and southern hemispheres, so that $A \cap B = S^{n-1}$, the equator. In the LES, we have:

\[
H^{i+1}(S^n) \xrightarrow{} H^i(S^{n-1}) \xrightarrow{} H^iA \oplus H^i B \xrightarrow{} H^i S^n \xrightarrow{} H^{i-1}(S^{n-1}) \xrightarrow{} H^{i-1}A \oplus H^{i-1}B
.\]

But $A, B$ are contractible, so $H^iA= H^iB = 0$, so we have

\[
H^{i+1}(S^n) \xrightarrow{} H^{i}(S^{n-1}) \xrightarrow{} 0 \oplus 0 \xrightarrow{}H^i(S^n) \xrightarrow{} H^{i-1}(S^{n-1}) \xrightarrow{} 0
.\]

In particular, we have the shape $0 \to A \to B \to 0$ in an exact sequence, which is always an isomorphism.

:::


:::{.theorem title="Kunneth"}
There exists a short exact sequence
\[
0 \to \prod_{i+j=k} H_{j}(X; R) \tensor_{R} H_{i}(Y; R) \to H_{k}(X\cross Y; R) \to \prod_{i+j=k-1} \tor_{R}^1(H_{i}(X; R), H_{j}(Y; R))
.\]
If $R$ is a free \(R\dash\)module, a PID, or a field, then there is a (non-canonical) splitting given by
\[
H_{k} (X\cross Y) \cong \left( \prod_{i+j = k} H_{i} X \oplus H_{j} Y\right) \cross \prod_{i+j = k-1}\tor(H_{i}X, H_{j} Y) \\
\]
:::

:::{.corollary title="Nicest case of Kunneth"}
If $R$ is a freely generated free $R\dash$module (or a PID or a field), then
$$ 
H_{k}(X\times Y) \cong \bigoplus _{{i+j=k}}H_{i}(X)\otimes H_{j}(Y) \bigoplus_{i+j=k-1}\tor(H_{i}(X), H_{j}(X))
$$

:::



:::{.theorem title="UCT for Change of Group"}
For changing coefficients from $\ZZ$ to $G$ an arbitrary group, there are short exact sequences

\[
0\to \tor_\ZZ^0 (H_{i}(X;\ZZ), A) &\to H_{i}(X;A)\to \Tor_\ZZ^1 (H_{i-1}(X;\ZZ ),A)\to 0 \\
& \quad \Downarrow \\ \\
0 \to H_{i} X \tensor G &\to H_{i}(X; G) \to \tor_\ZZ^1(H_{i-1}X, G) \to 0 
\]
and 
\[
0\to \ext_{\ZZ}^{1}(H_{i-1}(X; \ZZ),A) &\to H^{i}(X; A)\to \ext_{\ZZ}^{0}(H_{i}(X; \ZZ),A) \to 0 \\
&\quad \Downarrow \\ \\ 
0 \to \ext (H_{i-1} X, G) &\to H^i(X;G) \to \hom(H_{i} X, G) \to 0
.\]
These split unnaturally:
\[
H_{i}(X;G) &= (H_{iX}\tensor G) \oplus \tor(H_{i-1}X; G) \\
H^i(X; G) &= \hom(H_{i}X, G) \oplus \ext(H_{i-1}X; G)
\]

When all of the $H_{i}X$ are all finitely generated, writing $H_{i}(X; \ZZ) = \ZZ^{\beta_{i}} \oplus T_{i}$ we have
$$
H^i(X; \ZZ) = \ZZ^{\beta_{i}} \oplus T_{i-1}.
$$

:::



:::{.remark}
If $A$ is a field, then $$H^i(X; A) \cong \hom(H_{i}(X; A), A)$$
:::


### Useful Shortcuts



* Universal Coefficients Theorem: If $X$ is a finite CW complex then
$$
H^i(X; \ZZ) = F(H_{i}(X; \ZZ)) \times T(H_{i-1}(X; \ZZ))\\
H_{i}(X; \ZZ) = F(H^i(X; \ZZ)) \times T(H^{i+1}(X; \ZZ))
$$

## Cellular Homology

* $S^n$ has the CW complex structure of 2 $k$-cells for each $0\leq k \leq n$.

How to compute:

1. Write cellular complex $$0 \to C^n \to C^{n-1} \to \cdots C^2 \to C^1 \to C^0 \to 0$$
2. Compute differentials $\del_{i}: C^i \to C^{i-1}$
    3. *Note: if $C^0$ is a point, $\del_{1}$ is the zero map.*
    4. *Note: $H_{n} X = 0 \iff C^n = \emptyset$.*
    5. Compute degrees: Use $\del_{n}(e_{i}^n) = \sum_{i} d_{i} e_{i}^{n-1}$ where $$d_{i} = \deg(\text{Attach }e_{i}^n \to \text{Collapse } X^{n-1}\dash\text{skeleton}),$$ which is a map $S^{n-1} \to S^{n-1}$.
	    1. Alternatively, choose orientations for both spheres. Then pick a point in the target, and look at points in the fiber. Sum them up with a weight of +1 if the orientations match and -1 otherwise.
    6. Note that $\ZZ^m \mapsvia{f} \ZZ^n$ has an $n\times m$ matrix
    7. Row reduce, image is span of rows with pivots. Kernel can be easily found by taking RREF, padding with zeros so matrix is square and has all diagonals, then reading down diagonal - if a zero is encountered on $n$th element, take that column vector as a basis element with $-1$ substituted in for the $n$th entry.
    e.g.
    
    \[
    \begin{matrix}
    \mathbf1&2&0&2\\0&0&\mathbf1&-1\\0&0&0&\mathbf0
    \end{matrix} 
    \to
    \begin{matrix}
    \mathbf1&2&0&2\\0&\mathbf0&0&0\\0&0&\mathbf1&-1\\0&0&0&\mathbf0
    \end{matrix}
    \begin{matrix}
    \mathbf1&2&0&2\\0&\mathbf0&0&0\\0&0&\mathbf1&-1\\0&0&0&\mathbf0
    \end{matrix} \\
    \ker = 
    \begin{matrix}
    2\\-1\\0\\0
    \end{matrix} 
    \begin{matrix}
    3\\0\\-1\\-1
    \end{matrix}\\
    \im = \generators{a+2b+2d,c-d}
    .\]
     
    6. Or look at elementary divisors, say $n_{i}$, then the image is isomorphic to $\bigoplus n_{i} \ZZ$


[^kunneth]: The generalization of Kunneth is as follows: write $\mathcal{P}(n, k)$ be the set of partitions of $n$ into $k$ parts, i.e. $\mathbf{x} \in \mathcal{P}(n,k) \implies \mathbf{x} = (x_{1}, x_{2}, \ldots, x_{k})$ where $\sum x_{i}  = n$. Then
$$
H_{n}\qty{\prod_{j=1}^k X_{j}} = \bigoplus_{\mathbf{x} \in \mathcal{P}(n,k)} \bigotimes_{i=1}^{k} H_{x_{i}}(X_{i}).
$$
[^wedge]: $\bigvee$ is the coproduct in the category $\mathbf{Top}_0$ of pointed topological spaces, and alternatively, $X\vee Y$ is the pushout in $\mathbf{Top}$ of $X \from \pt \to Y$


# Homology


## Relative Homology

- $H_{n}(X/A) \cong \tilde H_{n}(X, A)$ when $A\subset X$ has a neighborhood that deformation retracts onto it.

- LES of a pair
  - $(A \injects X) \mapsto (A, X, X/A)$

- For CW complexes $X = \theset{X^{(i)}}$, we have 
\[
H_{n}(X^{(k)},X^{(k-1)}) \cong \begin{cases}\ZZ[\theset{e^n}]~ &k=n,\\ 0 &\text{otherwise}\end{cases} \qquad\text{ since } X^k/X^{k-1} \cong \bigvee S^k
\]
- $H_{n}(X, A) \cong_? H_{n}(X/A, \pt)$

## Cohomology


- $H^*(X; \FF) = \hom(H_*(X; \FF),\FF)$ for a field.
