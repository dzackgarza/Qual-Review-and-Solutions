# Homology


- $H_n(X/A) \cong \tilde H_n(X, A)$ when $A\subset X$ has a neighborhood that deformation retracts onto it.
- $H_n(\bigvee_\alpha X_\alpha) = \bigoplus_\alpha H_n X_\alpha$

- Useful fact: since $\ZZ$ is free, any exact sequence of the form $0 \to \ZZ^n \to A \to \ZZ^m \to 0$ splits and $A\cong \ZZ^{n}\cross \ZZ^m$.

- Useful fact: $\tilde H_*(A\vee B) \cong H_*(A) \times H_*(B)$.

- $H_n(\bigvee_\alpha X_\alpha) = \bigoplus_\alpha H_n X_\alpha$
- $H_n(X, A) \cong H_n(X/A)$
- $H_n(X) = 0 \iff X$ has no $n\dash$cells.
- $C^0 X = \pt \implies d_1: C^1 \to C^0$ is the zero map.
- $H^*(X; \FF) = \hom(H_*(X; \FF),\FF)$ for a field.


### Constructing a CW Complex with Prescribed Homology

- Given $G = \bigoplus G_i$, and want a space such that $H_i X = G$? Construct $X = \bigvee X_i$ and then $H_i (\bigvee X_i) = \bigoplus H_i X_i$. Reduces problem to: given a group $H$, find a space $Y$ such that $H_n(Y) = G$.
  - Attach an $e^n$ to a point to get $H_n = \ZZ$
  - Then attach an $e^{n+1}$ with attaching map of degree $d$ to get $H_n = \ZZ_d$


Theorem (Mayer Vietoris)
:   Let $X = A^\circ \union B^\circ$; then there is a SES of chain complexes
    \begin{align*}
    0 \to C_n(A\intersect B) \mapsvia{x\mapsto (x, -x)} C_n(A) \oplus C_n(B) \mapsvia{(x, y) \mapsto x+y} C_n(A + B) \to 0
    \end{align*}
    
    where $C_n(A+B)$ denotes the chains that are sums of chains in $A$ and chains in $B$.
    This yields a LES in homology:

    \begin{align*}
    \cdots \to H_n(A\intersect B) \mapsvia{x\mapsto (x, -x)} H_n(A) \oplus H_n(B) \mapsvia{(x, y) \mapsto x+y} H_n(X) \to \cdots
    .\end{align*}

Theorem (Eilenberg-Zilber)
:   Given two spaces $X, Y$, there are chain maps

    \begin{align*}
    F: C_*(X\cross Y; R)              &\to C_*(X; R) \tensor_R C_*(Y; R) \\
    G: C_*(X; R) \tensor_R C_*(Y; R)  &\to C_*(X\cross Y; R) 
    \end{align*}

    such that $FG = \id$ and $GF \homotopic \id$.
    In particular,
    \begin{align*}
    H_*(X\cross Y; R) &\cong H_*(X; R) \tensor_R H_*(Y; R)
    .\end{align*}

Theorem (Kunneth)
:   There exists a short exact sequence
    $$
    0 \to \bigoplus_{i+j=k} H_j(X; R) \tensor_R H_{i}(Y; R) \to H_k(X\cross Y; R) \to \bigoplus_{i+j=k-1} \tor_R^1(H_i(X; R), H_{j}(Y; R))
    $$
    It has a non-canonical splitting given by
    $$
    H_k (X\cross Y) = \left( \bigoplus_{i+j = k} H_i X \oplus H_j Y\right) \oplus \bigoplus_{i+j = k-1}\tor(H_iX, H_j Y)
    $$


Theorem (Universal Coefficients for Change of Group)
:   For changing coefficients from $\ZZ$ to $G$ an arbitrary group, there are short exact sequences
    $$
    0 \to H_i X \tensor G \to H_i(X; G) \to \tor(H_{i-1}X, G) \to 0
    $$

    $$
    0 \to \ext (H_{i-1} X, G) \to H^i(X;G) \to \hom(H_i X, G) \to 0
    $$

    which split unnaturally:
    $$
    H_i(X;G) = (H_iX\tensor G) \oplus \tor(H_{i-1}X; G)
    $$

    $$
    H^i(X; G) = \hom(H_iX, G) \oplus \ext(H_{i-1}X; G)
    $$

    When $H_iX$ are all finitely generated, write $H_i(X; \ZZ) = \ZZ^{\beta_i} \oplus T_i$. Then
    $$
    H^i(X; \ZZ) = \ZZ^{\beta_i} \oplus T_{i-1}.
    $$


### Useful long exact sequences

$$
\cdots \to H^{i}(X)\to H^{i}(U)\oplus H^{i}(V)\to H^{i}(U\cap V)\mapsvia{\delta} H^{i+1}(X)\to \cdots
$$

$$
\cdots \to H_{i}(A)\to H_{i}(X)\to H_{i}(X,A){\stackrel{\delta }{\to }}H_{{i-1}}(A)\to \cdots
$$

### Useful Short Exact Sequences

> Note that $\ext_R^0 = \hom_R$ and $\tor_R^0 = \tensor_R$

Homology to cohomology:
$$
\displaystyle 0\to \tor_\ZZ^0 (H_{i}(X;\ZZ), A)\,{\to }\,H_{i}(X;A)\to \operatorname {Tor}_\ZZ^1 (H_{i-1}(X;\ZZ ),A)\to 0
.$$

Cohomology to dual space:
$$
0\to \ext_{\ZZ}^{1}(H_{i-1}(X; \ZZ),A)\to H^{i}(X; A)\to \ext_{\ZZ}^{0}(H_{i}(X; \ZZ),A) \to 0
.$$

Product of spaces to tensor product of homology:
$$
0\to \bigoplus _{{i+j=k}}H_{i}(X;R)\otimes _{R}H_{j}(Y;R)\to H_{k}(X\times Y;R)\to \bigoplus _{{i+j=k-1}}{\mathrm  {Tor}}_{1}^{R}(H_{i}(X;R),H_{j}(Y;R))\to 0
$$

### Useful Shortcuts

* Cohomology: If $A$ is a field, then $$H^i(X; A) \cong \hom(H_i(X; A), A)$$

* Kunneth: If $R$ is a freely generated free $R\dash$module (or a PID or a field), then
$$ 
H_{k}(X\times Y) \cong \bigoplus _{{i+j=k}}H_{i}(X)\otimes H_{j}(Y) \bigoplus_{i+j=k-1}\tor(H_i(X), H_j(X))
$$

* Universal Coefficients Theorem: If $X$ is a finite CW complex then
$$
H^i(X; \ZZ) = F(H_i(X; \ZZ)) \times T(H_{i-1}(X; \ZZ))\\
H_i(X; \ZZ) = F(H^i(X; \ZZ)) \times T(H^{i+1}(X; \ZZ))
$$

