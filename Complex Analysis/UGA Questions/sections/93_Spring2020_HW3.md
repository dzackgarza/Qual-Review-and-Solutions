# Spring 2020 Homework 3

## Problems From Tie

### 1

Problem
: Prove that if $f$ has two Laurent series expansions,
  $$
  \begin{aligned} f(z) = \sum c_n(z-a)^n \quad\text{and}\quad f(z) = \sum c_n'(z-a)^n\end{aligned}
  $$
  then $c_n = c_n'$.

#### Solution

By taking the difference of two such expansions, it suffices to show that if $f$ is identically zero and $f(z) = \sum_{n=-\infty}^\infty c_n (z-a)^n$ about some point $a$, then $c_n = 0$ for all $n$.

Under this assumption, let $D_\eps(a)$ be a disc about $a$ and $\gamma$ be any contoured contained in its interior.
Then for each $n$, we can apply the formula

\begin{align*}
c_n
&= \frac 1 {2\pi i } \int_\gamma \frac{f(\xi)}{\qty{\xi - a}^{n+1}} ~d\xi \\
&= \frac 1 {2\pi i } \int_\gamma \frac{0}{\qty{\xi - a}^{n+1}} ~d\xi \quad\text{by assumption} \\
&= 0
,\end{align*}

which shows that $c_n = 0$ for all $n$.

$\qed$

### 2

Problem
: Find Laurent series expansions of
  $$\begin{aligned}\frac{1}{1-z^2} + \frac{1}{3-z}\end{aligned}$$
  How many such expansions are there? In what domains are each valid?

#### Solution

Note that $f$ has poles at $z=-1, 1, 3$, all with multiplicity 1, and so there are 3 regions to consider:

1. $\abs{z} < 1$
2. $1 < \abs{z} < 3$
3. $3 < \abs{z}$.

\begin{center}
\begin{tikzpicture}
\pgfplotsset{every x tick label/.append style={font=\tiny, yshift=0.5ex}}
\pgfplotsset{every y tick label/.append style={font=\tiny, xshift=0.5ex}}
\begin{axis}[
    xmin=-6,
    xmax=6,
    ymin=-4,
    ymax=4,
		xtick = {-1, -3, 3, 1},
		ytick = {-1, -3, 3, 1},
    axis equal,
    axis lines=middle,
    disabledatascaling]

\fill[red] [opacity=0.5] (0,0) circle [radius=1];
\fill[orange] [opacity=0.2] (0,0) circle [radius=3];
\fill[cyan] [opacity=0.1] (0,0) circle [radius=5];

\draw[->][cyan][opacity=0.3] (axis cs:3.0, 3.0) -- (axis cs:4, 4);
\draw[->][cyan][opacity=0.3] (axis cs:-3.0, 3.0) -- (axis cs:-4, 4);
\draw[->][cyan][opacity=0.3] (axis cs:3.0, -3.0) -- (axis cs:4, -4);
\draw[->][cyan][opacity=0.3] (axis cs:-3.0, -3.0) -- (axis cs:-4, -4);

\node[font=\tiny] at (axis cs:0,1) [anchor=north west] {Region 1};
\node[font=\tiny] at (axis cs:1,2) [anchor=north west] {Region 2};
\node[font=\tiny] at (axis cs:2,3) [anchor=north west] {Region 3};

\node at (axis cs:2.5,5) [anchor=north east] {$\mathbb{C}$};
\end{axis}
\end{tikzpicture}
\end{center}


**Region 1:**
Take the following expansion:

\begin{align*}
f(z)
&= \frac{1}{1-z^2} + \frac{1}{3-z} \\
&= \sum_{n\geq 0} z^{2n} + \frac 1 3 \qty{ \frac{1}{1 - \frac 3 z}  } \\
&= \sum_{n\geq 0} z^{2n} + \frac 1 3 \sum_{n\geq 0} \qty{\frac 1 3}^n z^n \\
&= \sum_{n\geq 0} z^{2n} + \sum_{n\geq 0} \qty{\frac 1 3}^{n+1} z^n \\
.\end{align*}

Noting $\abs{z^2} < 1$ implies then $\abs{z} < 1$, and that the first term converges for $\abs{z^2} < 1$ and the second for $\abs{\frac z 3} < 1 \iff \abs{z} < 3$, this expansion converges to $f$ on the region $\abs{z} < 1$.

**Region 2:**
Take the following expansion:

\begin{align*}
f(z)
&= \frac{1}{1-z^2} + \frac{1}{3-z} \\
&= -\frac{1}{z^2} \qty{\frac{1}{1 - \frac{1}{z^2}}} - \frac 1 3 \qty{ \frac{1}{1 - \frac z 3}  }  \\
&=-\frac 1 {z^2} \sum_{n\geq 0} z^{-2n} + \sum_{n\geq 0} \qty{\frac 1 3}^{n+1} z^n \\
&= -\sum_{n\geq 2}\frac{1}{z^{2n}}  + \sum_{n\geq 0} \qty{\frac 1 3}^{n+1} z^n \\
.\end{align*}

By construction, the first term converges for $\abs{ \frac{1}{z^2} } < 1 \iff \abs{z} > 1$ and the second for $\abs{z} < 3$.

**Region 3:**
Take the following expansion:

\begin{align*}
f(z)
&= \frac{1}{1-z^2} + \frac{1}{3-z} \\
&= -\frac{1}{z^2} \qty{\frac{1}{1 - \frac{1}{z^2}}} - \frac 1 z \qty{\frac 1 {1 - \frac 3 z}} \\
&= - \frac 1 {z^2} \sum_{n\geq 0} \frac{1}{z^{2n}} - \frac 1 z \sum_{n\geq 0}3^n \frac{1}{z^n} \\
&= - \sum_{n\geq 2} \frac{1}{z^{2n}} - \sum_{n\geq 1}
\qty{ \frac 1 3 }^{n-1}
\frac{1}{z^n}
.\end{align*}

> Note: in principle, terms could be collected here.

By construction, this converges on $\theset{\abs z^2 > 1} \intersect \theset{\abs z > 3} = \theset{\abs z > 3}$.

$\qed$


### 3

Problem
: Let $P, Q$ be polynomials with no common zeros. Assume $a$ is a root of
$Q$.
  Find the principal part of $P/Q$ at $z=a$ in terms of $P$ and $Q$ if $a$ is (1) a simple root, and (2) a double root.

#### Solution

We'll use the following definition: if $f: \CC \to \CC$ is analytic with Laurent expansion $f(z) = \sum_{k=-\infty}^\infty c_k (z-a)^k$ at the point $a\in\CC$, then the **principal part** of $f$ at $a$ is given by
$$
\sum_{k=-1}^{-\infty} c_k (z-a)^k = c_{-1}(z-a)\inv + c_{-2}(z-a)^{-2} + \cdots
.$$

Without loss of generality (by performing polynomial long division if necessary), assume that $\deg P < \deg Q$.
By the method used in the theorem that proves meromorphic functions are rational, if we let $a_1, \cdots, a_n$ be the finitely many zeros of $Q(z)$, these are the finitely many poles of $P(z)/Q(z)$, and we can write
\begin{align*}
{P(z) \over Q(z)} \definedas f(z) = P_\infty(z) + \sum_{i=1}^n P_{a_i}(z)
\end{align*}
where $P_w(z)$ denotes the principal part of $f$ at the point $w$.

Note that if $w$ is a pole of order $\ell$, we can explicitly write
$$
P_w(z) = {\alpha_1 \over z-w} + {\alpha_2 \over (z-w)^2} + \cdots + {\alpha_\ell \over (z-w)^\ell}
$$
for some constants $\alpha_i \in \CC$,
and thus the first equation expresses $f$ in terms of its partial fraction decomposition.

Thus if $a$ is a simple root of $Q(z)$, it is a simple pole of $f$, and thus we have $P_a(z) = {\alpha_1 \over z-a}$, which consists of a single term.
Since we can write $f(z) = P_\infty(z) + P_a(z) + \cdots$ where none of the remaining terms involve $a$, it follows by definition that $\alpha_1 = \Res(f, a)$ and so
\begin{align*}
P_a(z) = { \Res(f(z), a) \over z-a}
,\end{align*}
where we can use a known formula to express $\Res(f(z), a) = {P(a) \over Q'(a)}$.

Similarly, if now $a$ is a root of multiplicity 2 of $Q(z)$, $a$ is a pole of order 2 of $f$ and $P_a(z) = {\alpha_1 \over z-a} + {\alpha_2 \over (z-a)^2}$ with precisely two terms.
Thus as before, $\alpha_1 = \Res(f(z), a)$, and now $\alpha_2 = \Res((z-a)f(z), a)$, and we have
\begin{align*}
P_a(z) = { \Res(f(z), a) \over z-a} + {\Res((z-a)f(z), a) \over (z-a)^2}
.\end{align*}

$\qed$

\newpage

### 4

Problem
:   Let $f$ be non-constant, analytic in $\abs{z} > 0$, where $f(z_n) = 0$
for infinitely many points $z_n$ with $\lim_{n\to\infty} z_n = 0$.

    Show that $z=0$ is an essential singularity for $f$.

    > Example: $f(z) = \sin(1/z)$.

#### Solution

We first note that $z=0$ is in fact a singularity of $f$, since the zeros of analytic functions are isolated.

The point $z=0$ can not be a pole because (by definition) this would force $\lim_{z\to 0} \abs{f(z)} = \infty$.
Explicitly, this would mean that for every $R > 0$, there would exist a $\delta > 0$ such that $z\in D_\delta(0) \implies \abs{f(z)} > R$.

However, since $z_n \to 0$ and $f(z_n) = 0 < R$ for every $n$, every $D_\delta(0)$ contains a point $z_N$ that violates this condition.

Similarly, $z=0$ can not be removable, since the function
$$
g(z) =
\begin{cases}
0 & z=0 \\
f(z) & \text{otherwise}
\end{cases}
$$
defines an analytic continuation of $f$.
However, it is a theorem that the zeros of an analytic function are isolated, whereas every neighborhood of $z=0$ (which is a zero of $g$) contains infinitely many distinct zeros of the form $z_n$, a contradiction.

$\qed$

### 5

Problem
: Show that if $f$ is entire and $\lim_{z\to\infty}f(z) = \infty$, then
$f$ is a polynomial.

#### Solution

Since $f$ is entire, it is analytic on $\CC$, so there is an expansion $f(z) = \sum_{k=0}^\infty c_k z^k$ that converges to $f$ everywhere.
Let $F(z) = f(1/z)$; then $\lim_{z\to 0} F(z) = \infty$ by assumption.

This also implies that since $z=\infty$ is a pole of $f$, the point $z=0$ is a pole of $F$, say of order $N$.

However, we can expand $F(z) = \sum_{k=0}^\infty c_k {1 \over z^k}$.
Since this is a Laurent expansion for $F$ about $z=0$, which is a pole of order $N$, we must in fact have
$F(z) = \sum_{k=0}^N c_k {1 \over z_k}$, i.e. there are only $N$ terms in this expansion.

This implies that $f(z) = \sum_{k=0}^N c_k z^k$, which has finitely many terms and is thus a polynomial.


$\qed$


### 6

Problem
:   \hfill
    a. Show that
    $$\begin{aligned}\int_0^{2\pi} \log\abs{1 - e^{i\theta}}~d\theta = 0\end{aligned}$$
    b. Show that this identity is equivalent to SS 3.8.9:
    \begin{align*}
    \int_0^1 \log(\sin(\pi x)) ~dx = -\log 2
    .\end{align*}

#### Solution Part (a)

Let $I$ be the integral in question, then substituting $z = e^{i\theta}$ and ${dz \over iz} = d\theta$ yields
\begin{align*}
I &= \int_{S^1} {\log \abs{1 - z} \over iz} ~dz \definedas \Re\qty{ \int_{S^1} f(z)~dz }
,\end{align*}

where
$$
f(z) \definedas{\log(1-z) \over iz}
,$$
$S^1$ denotes the unit circle in $\CC$, and since by definition
$$
\log_\CC(z) = \log_\RR(\abs{z}) + i \arg(z)
$$
where the subscripts denote the complex and real logarithms respectively, we have
$$
\log_\CC\abs{1 - z} = \Re\qty{\log_\CC \qty{1-z}}
.$$

So it suffices to show that $\int_{S^1} f(z) ~dz = 0$.

The claim is that $z=0$ is a removable singularity and thus $f$ is holomorphic in the unit disc.
The singularity is removable because we have
\begin{align*}
\lim_{z\to 0} f(z)
&= \lim_{z\to 0} {\log(1-z) \over iz} \\
&= \lim_{z\to 0} { {1 \over 1-z}  \over i} \quad\quad\text{by L'Hopital's} \\
&= -i
,\end{align*}

so the modified function
\begin{align*}
F(z) = \begin{cases}
-i & z = 0 \\
f(z) & \text{otherwise}
\end{cases}
\end{align*}
is holomorphic, making $z=0$ removable.

Since $f$ is also analytic, the Cauchy-Goursat theorem applies and $\int_{S^1} f = 0$.

#### Solution Part (b)

> No clue how to relate these two!

### 7

Problem
: Let $0<a<4$ and evaluate $$\begin{aligned}
    \int_0^\infty \frac{x^{\alpha-1}}{1+x^3} ~dx\end{aligned}$$

#### Solution

Let $I$ denote the integral in question.
We will compute this using a closed contour and the residue theorem, so first note that
$$
z^3 + 1 = (z+1)(z - e^{i\pi 3})(z - e^{-i \pi 3}) \definedas (z- r_1)(z-r_2)(z-r_3)
.$$

Defining $z^\alpha = e^{\alpha \log z}$ for $\alpha \in \RR$, we'll take the following contour $\Gamma$ shown in blue along with a branch cut for the logarithm function indicated in red:

\begin{center}
\begin{tikzpicture}
\pgfplotsset{every x tick label/.append style={font=\tiny, yshift=0.5ex}}
\pgfplotsset{every y tick label/.append style={font=\tiny, xshift=0.5ex}}
\begin{axis}[
    xmin=-6,
    xmax=12,
    ymin=-2,
    ymax=10,
		xtick = {0},
		ytick = {0},
    axis equal,
    axis lines=middle,
    disabledatascaling]
\node[font=\tiny] at (axis cs:0,10) [anchor=north east] {$iR$};
\node[font=\tiny] at (axis cs:10,0) [anchor=north east] {$R$};
\node[fill=black,draw,rounded corners,circle, scale=0.15] at (180/3:1cm) {};
\node[font=\tiny] at (180/3:1cm)[anchor = north west] {$r_2 = e^{i\pi/3}$};
\node[fill=black,draw,rounded corners,circle, scale=0.15] at (180:1cm) {};
\node[font=\tiny] at (180:1cm)[anchor = south east] {$r_1 = -1$};
\node[fill=black,draw,rounded corners,circle, scale=0.15] at (-180/3:1cm) {};
\node[font=\tiny] at (-180/3:1cm)[anchor = north west] {$r_3 =e^{-i\pi/3}$};
\node[font=\tiny] at (axis cs:9,11) [anchor=north west] {$\mathbb{C}$};
\node[font=\tiny] at (180/3.5: 4cm) [anchor=north west] {$\Gamma$};
\begin{scope}[thick,decoration={
    markings,
    mark=at position 0.5 with {\arrow{>}}}
    ]

		\draw [blue, domain=0:90, postaction={decorate}] plot ({10*cos(\x)}, {10*sin(\x)});
		\draw[-][blue][opacity=0.9, postaction={decorate}] (axis cs:0, 0) -- (axis cs:10, 0);
		\draw[-][blue][opacity=0.9, postaction={decorate}] (axis cs:0, 10) -- (axis cs:0, 0);
    \draw[-][red][opacity=0.9, very thick] (axis cs:0, 0) -- (axis cs:0, -5);
\end{scope}
\end{axis}
\end{tikzpicture}
\end{center}

Letting
$$
f(z) \definedas \frac{z^{\alpha-1}}{z^3 + 1} \definedas {P(z) \over Q(z)}
,$$
we find that only $z=r_2$ will contribute a term to $\int_\Gamma f$.
Noting that each pole is simple of order 1, we have
$$
\res(f(z), {z = r_i}) = {P(r_i) \over Q'(r_i)} = {r_i^{\alpha-1} \over 3r_i^2} = {r_i^{\alpha - 3} \over 3 }
$$
We thus have
\begin{align*}
\res(f(z), z=r_2)
&= \frac 1 3 { e^{i \pi (\alpha - 3) \over 3} } \\
\implies \int_\Gamma f(z) ~dz
&= {2\pi i \over 3} { e^{i \pi (\alpha - 3) \over 3} }
.\end{align*}

We can now compute the contributions to the integral along the semicircular arc and the portion along the imaginary axis.

Along the arc, Jordan's lemma applies since ${1 \over R^3 + 1} \converges{R\to\infty}\to 0$, and thus this contribution vanishes.

Along the imaginary axis, we can make the following change of variables:
\begin{align*}
\int_{R}^{0} f(iy) ~dy
&= -\int_0^R {(iy)^{\alpha-1} \over (iy)^3 + 1} ~dy \\
&= -\frac 1 i \int_0^R {t^{\alpha-1} \over t^3 + 1} ~dt \quad\quad\quad (t = iz,~ dt = idz)\\
&= i I
,\end{align*}

which is $i$ times the original integral.

We thus have
\begin{align*}
\res(f(z), {z = r_2})
&= \int_\Gamma f \\
&= \int_0^R f + \int_{C_R} f + \int_{iR}^{0} f  \\
&\converges{R\to\infty}\to I + 0 +iI \\
&= (1+i)I
,\end{align*}

and so
\begin{align*}
I
= { \res(f(z), {z = r_2}) \over 1+i}
= {2\pi i \over 3(1+i)} { e^{i \pi (\alpha - 3) \over 3} }
.\end{align*}

$\qed$

> Note: this seems to be wrong, because plugging in $a=1,2,3$ doesn't result in a real value.

### 8

Problem
:   Prove the fundamental theorem of Algebra using

    a.  Rouche's Theorem.
    b. The maximum modulus principle.

#### Solution (Rouche)

We want to show that every $f \in \CC[x]$ has precisely $n$ roots, and we'll use the follow formulation of Rouche's theorem:

Theorem (Rouche)
: If $f, g$ are holomorphic on $D(z_0)$ with $f,g\neq 0$ and $\abs{f-g} < \abs f + \abs g$ on $\bd D(z_0)$, then $f$ and $g$ has the same number of zeros within $D$.

We'll also use without proof the fact that the function $h(z) = z^n$ has precisely $n$ zeros (counted with multiplicity).

Suppose $f(z) = a_n z^n + \cdots + a_1 z + a_0$ where $a_n \neq 0$ and define
$$
g(z) \definedas a_n z^n
.$$

Noting that polynomials are entire, $f, g$ are nonzero by assumption, and fixing $\abs{z} = R > 1$, we have
\begin{align*}
\abs{f - g}
&= \abs{ a_{n-1} z^{n-1}  + \cdots + a_1 z + a_0 }  \\
&= \abs{ a_{n-1} z^{n-1}  + \cdots + a_1 z + a_0 + a_{n}z^n - a_{n}z^n }  \\
&\leq \abs{ a_{n-1} z^{n-1}  + \cdots + a_1 z + a_0 + a_{n}z^n } + \abs{ -a_{n}z^n }  \quad \text{ by the triangle inequality} \\
&= \abs{f} + \abs{g}
\end{align*}

the conditions of Rouche's theorem apply and $f, g$ have the same number of roots.
Since $g$ has precisely $n$ roots, $f$ does as well.

> This is much simpler than other proofs out there, so I suspect something is slightly wrong but I couldn't sort out what it was.

$\qed$

#### Solution (Maximum Modulus Principle)

Toward a contradiction, suppose $f$ is non-constant and has *no* zeros.
Then $g(z) \definedas 1/f(z)$ is non-constant and holomorphic on $\CC$.

Using the fact that $\lim_{z\to\infty} f(z) = \infty$ for any polynomial $f$, pick $R$ large enough such that
$$
\abs{z} \geq R \implies \abs{f(z)} > \abs{f(0)}
,$$
which inverted yields,
$$
\abs{z} \geq R \implies \abs{g(z)} < \abs{g(0)}
.$$

Noting that $S_R \definedas \theset{\abs{z} \geq R }$ is closed (as the complement of the open set $\theset{\abs{z} < R}$), bounded (by the argument above), and thus compact by Heine-Borel, $g$ attains a maximum on $S_R$.

But by the maximum modulus principle, this forces $g$ to be constant, and since $g = {1 \over f}$, it must also be true that $f$ is constant.

$\qed$

### 9

Problem
:   Let $f$ be analytic in a region $D$ and $\gamma$ a rectifiable curve in
$D$ with interior in $D$.

    Prove that if $f(z)$ is real for all $z\in \gamma$, then $f$ is constant.

#### Solution

Without loss of generality, assume $0\in D$ (by considering the translate $f(z) - w$ if necessary) and $\gamma$ is not entirely contained in $\RR$ (by taking a homotopic curve).

Since $f$ is analytic in $D$, we can write its Laurent series expansion about $z=0$:
$$
f(z) = c_0 + c_1 z + \cdots \quad \text{ for } z\in D
.$$

For $z \in \gamma$ we can write $z = x + iy$ where $y\neq 0$.

Then
\begin{align*}
f(z) &= f(x+iy) \\
&= c_0 + c_1(x+iy) + c_2(x+iy)^2 + \cdots \\
&= c_0  + \qty{c_1 x + c_2 x^2 + \cdots} + i\qty{c_1 y + c_2 y^2 + c_2 xy + \cdots} \\
&\subset \RR \quad\text{by assumption}
,\end{align*}

where the second parenthesized term must vanish for all $x+iy \in \gamma$,

But since there is at least one $z\in \gamma$ with $y\neq 0$, this forces $c_1 = c_2 = \cdots = 0$, and thus $f(z) = c_0$ must be constant.

$\qed$

### 10

Problem
: For $a> 0$, evaluate
  $$\begin{aligned} \int_0^{\pi/2} \frac{d\theta}{a + \sin^2 \theta}\end{aligned}$$

#### Solution

We have
\begin{align*}
I &\definedas
\int_0^{\pi/2} \frac{1}{1 + \sin^2(\theta)} ~d\theta \\
&= \int_{\gamma_1} \frac{1}{a + \qty{\frac{z - z\inv}{2i}}^2} ~\frac{-i~dz}{z} \quad\text{where $\gamma_1$ is $\frac 1 4$ of the unit circle $S^1$}\\
&= -i \int_{\gamma_1} \frac 1 z \qty{\frac{1}{a + \qty{-\frac 1 4}\qty{z^2 -2 + z^{-2}}  }  } ~dz\\
&= 4i \int_{\gamma_1} \frac 1 z \qty{ \frac{1}{z^2 - (2 + 4a) + z^{-2}} } ~dz\\
&= 4i \int_{\gamma_1} \frac{z}{z^4 - \qty{2+4a}z^2 + 1} ~dz \\
&= i \oint_{S^1} \frac{z}{z^4 - \qty{2+4a}z^2 + 1} ~dz \\
&= \frac i 2 \oint_{2\cdot S^1} \frac{1}{u^2 - (2+4a)u + 1} ~du \quad \quad \text{using } u = z^2, \frac 1 2 ~du = z~dz \\
&\definedas \frac i 2 \oint_{2\cdot S^1} \frac{1}{f_a(u)} ~du \\
&= \frac i 2 \cdot 2\pi i \cdot \sum \Res\qty{\frac{1}{f_a(u)}, {u=r_i} }
,\end{align*}

where $2\cdot S^1$ denotes the contour wrapping around the unit circle twice and $r_i$ denote the poles contained in the region bounded by $S^1$.
We can now compute the last integral by the residue theorem.

Factor the denominator as
$$
f_a(u) = u^2 -(2+4a)u + 1 = (u-r_1)(u-r_2)
,$$
where the $r_i$ are given by $(1 + 2a) \pm 4\sqrt{a^2 + a}$ using the quadratic formula.
We can then write a partial fraction decomposition
\begin{align*}
\frac{1}{f_a(u)}
&\definedas \frac{1}{u^2 - (2+4a)u + 1} \\
&= \frac{1}{(u-r_1)(u-r_2)} \\
&= \frac{A}{u-r_1} + \frac{B}{u-r_2} \\
&= \frac{\Res_{u=r_1} 1/f(u)}{u-r_1} + \frac{\Res_{u=r_2} 1/f(u) }{u-r_2} \\
&= \frac{1/f'(r_1)}{u-r_1} + \frac{1/f'(r_2)}{u-r_2} \\
&= -\frac{1}{8\sqrt{a^2+a}(u-r_1)} + \frac{1}{8\sqrt{a^2+a}(u-r_2)}
.\end{align*}

Since $\abs{r_2} = \abs{(1+2a) + 4\sqrt{a^2 + a}} > 1$, we find that the only relevant pole inside of $S^1$ is $r_1$.
Reading off the residue from the above decomposition, we thus have
\begin{align*}
I
&= \frac i 2 \cdot 2\pi i \cdot \sum \Res_{u=r_i} \frac{1}{f_a(u)} \\
&= -\pi \cdot \res_{u=r_1} \frac{1}{f_a(u)} \\
&= \frac{\pi}{8\sqrt{a^2+a}}
.\end{align*}

$\qed$

> Note: I know I'm off by a constant here at least, since $a=1$ should reduce to $\pi/2\sqrt 2$.

### 11

Problem
: Find the number of roots of $p(z) = 4z^4 - 6z + 3$ in $\abs{z} < 1$ and
$1 < \abs{z} < 2$ respectively.

#### Solution

For $\abs{z} < 1$, take $f(z) = -6z$ and $g(z) = z^4+3$, noting that $f+g = p$.
Using the maximum modulus principal, we know that the max/mins of $f, g$ occur on $\abs{z} = 1$, on which we have
$$
\abs{g(z)} = 4 < 6 = \abs{f(z)}
,$$

so Rouche's theorem applies and both $p$ and $f$ have the same number of zeros.
Since $f$ clearly has **one** zero, $p$ has one zero in this region.

Now consider $\abs{z} < 2$ and set $f(z) = z^4$ and $g(z) = -6z+3$.
By a similar argument, we have
$$
\abs{g(z)} = 15 < 16 = \abs{f}
$$
on $\abs{z} = 2$, and thus $f$ and $p$ have the same number of zeros in this region.
Since $f$ has **four** zeros here, so does $p$.

Thus $p$ has $4-1 = \mathbf{3}$ **zeros** on $1 \leq \abs{z} \leq 2$.

$\qed$

### 12

Problem
: Prove that $z^4 + 2z^3 -2z + 10$ has exactly one root in each open
quadrant.

#### Solution

Let $f(z) = z^4 +2z^3 -2z + 10$, and consider the following contour:

![Image](figures/2020-03-18-11:02.png)\

By the argument principle, we have
\begin{align*}
\Delta_\Gamma \arg f(z) = 2\pi\qty{ Z - P }
,\end{align*}

where $Z$ is the number of zeros of $f$ in the region $\Omega$ enclosed by $\Gamma$ and $P$ is the number of poles in $\Omega$.


Since polynomials are holomorphic on $\CC$, by the argument principle it suffices to show that

- $f$ does not have any roots on the real or imaginary axes
- $f$ does not vanish on $\Gamma$, and
- $\Delta_\Gamma \arg f(z) = 1$, where $\Delta_\Gamma$ denotes the total change in the argument of $f$ over $\Gamma$.

It will follow by symmetry that $f$ has exactly one root in each quadrant.

Claim
:   \hfill
    - $f$ has no roots on the coordinate axes.
    - $\Delta_{\gamma_1}\arg f(z) = 0$
    - $\Delta_{\gamma_2}\arg f(z) = 2\pi$
    - $\Delta_{\gamma_3}\arg f(z) = 0$

Given the claim, we would have

\begin{align*}
\Delta_\Gamma \arg f(z) = 2\pi = 2\pi \qty{Z - 0} \implies Z = 1
,\end{align*}

which is what we wanted to show.

**Proof of Claim**:

$\gamma_2$:
For $R\gg 0$, we have $f(z) \sim z^4$.
Along $\gamma_2$, the argument of $z$ ranges from $0$ to $\frac \pi 2$, and thus the argument of $z^4$ ranges from $0$ to $4\cdot \frac \pi 2 = 2\pi$.

$\gamma_1$:
By cases, for $z\in \RR$,

- If $\abs{z} > 1$, then $z^3 > z$ and so
  \begin{align*}
  f(z)
  &= (z^4 +10) + (2z^3 - 2z)  \\
  &> (z^4 + 10) + (2z - 2z) \\
  &= z^4 +10 \\
  &> 0
  ,\end{align*}
  so $f$ is strictly positive and does not change argument on $(\pm 1,\pm \infty)$ or $i\cdot(\pm 1, \pm \infty)$.

- If $\abs{z} \leq 1$,
  \begin{align*}
  \abs{-z^4 -2z^3 + 2z}
  &\leq \abs{z}^4 + 2\abs{z}^3 + 2\abs{z} \\
  &\leq 1 + 2 + 2 \\
  &= 5  \\
  &< 10 \\
  \implies f(z) &= 10 - (-z^4 - 2z^3 + 2z) > 0
  ,\end{align*}
  so $f$ is strictly positive and does not change argument $(0, \pm 1)$ or $i\cdot(0, \pm 1)$.

$\qed$

### 13

Problem
: Prove that for $a> 0$, $z\tan z - a$ has only real roots.

#### Solution

We can extend Rouche's theorem in the following way: if $f = g+h$ with $\abs{g} > \abs{h}$ on $\gamma$ then $Z_f - P_f = Z_g - P_g$, where $Z, P$ denote the number of zeros and poles respectively.

So we proceed by explicitly counting the number of real roots $Z_f$ of $f(z) = z\tan(z) - a$ on a certain arbitrary real interval, then extend that interval to a rectangle in $\CC$ and apply Rouche to show that there are still $Z_f$ zeros within the rectangle.
This will imply that the only roots on that region are real, and in the limit as the length of the interval goes to infinity, this will remain true (since any potential root must fall within such a bounded rectangle).

Fix some parameter $N\in \QQ$ (to be determined) and consider the interval $[-N\pi-\eps, N\pi+\eps]$ for some $0 < \eps \ll 1$.
In this interval, we can compute $\sin(x) = 0 \iff x = 2k\pi$, yielding $2N+1$ zeros (including $x=0$), and thus $x\tan(x)$ has exactly $2N+1$ zeros here.

We can also compute $\cos(x) = 0 \iff x = (2k+1)\pi$, yielding $2N$ zeros and thus $2N$ poles of $x\tan(x)$.

Thus letting $\tilde Z_f, \tilde P_f$ denote the number of real zeros/poles of $f$, we have
$$
\tilde Z_f - \tilde P_f = (2N+1) - 2N = 1.
$$

> I got stuck here. It's not clear that $g(z) = z\tan(z), h(z) = a$ works at all.
> Trying to analyze the related function $\tan(z) - {a \over z}$ didn't seem to help either.
> General idea: decompose $f = g + h$, try to bound $\abs{h} < \abs{g}$ on edges of the rectangle $R=[-N\pi, N\pi] \cross i[-N\pi, N\pi]$, use Rouche to get $Z_f - P_f = Z_g - P_g \implies Z_f = P_f + Z_g - P_g$ and use the fact that $\cos(z)$ has only real zeros to count $P_f$ in $R$.

### 14

Problem
:   Let $f$ be nonzero, analytic on a bounded region $\Omega$ and continuous
on its closure $\overline \Omega$.

    Show that if $\abs{f(z)} \equiv M$ is constant for $z\in \partial \Omega$, then $f(z) \equiv Me^{i\theta}$ for some real constant $\theta$.

#### Solution

By the maximum modulus principle applied to $f$ in $\bar \Omega$, we know that $\max \abs{f} = M$.
Similarly, the maximum modulus principle applied to $\frac 1 f$ in $\bar{\Omega^c}$ since $f$ is nonzero in $\Omega$, and we can conclude that $\min \abs{f} = M$ as well.
Thus $\abs{f} = M$ is constant on $\bar \Omega$.

So consider the function $g(z) = \abs{f(z)}$; from the above observation, we find that $g(\bar \Omega) = \theset{M}$.
Letting $S_M$ be the circle of radius $M$, this implies that $f(\Omega) \subseteq S_M$.
In particular, $S_M \subset \CC$ is a closed set.

However, by the open mapping theorem, $f(\Omega) \subset \CC$ must be an open set.
A basis for the topology on $\CC$ is given by open discs, so in particular, the open sets of $\CC$ have real dimension either zero or two.
Since $S_M$ has real dimension 1, $f(\Omega)$ must have dimension zero and is thus a collection of points.
Since $f$ is continuous, the image can only be one point, i.e. $f(\Omega) = \pt \in S_M$.
So $f$ is constant.

$\qed$
