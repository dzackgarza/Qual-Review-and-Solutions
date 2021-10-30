# Extra Problems from Problem Sets

## 2010 6.1


:::{.problem title="?"}
Show that 
\[
\int_{\BB^n} {1 \over \abs{x}^p } \dx &< \infty \iff p < n \\ \\ \\ 
\int_{\RR^n\sm \BB^n} {1 \over \abs{x}^p } \dx &< \infty \iff p > n 
.\]
:::



:::{.solution}
oh boy
asdsa

:::


## 2010 6.2

Show that 
\[
\int_{\RR^n} \abs{ f} = \int_0^{\infty } m(A_t)\dt && A_t \da \ts{x\in \RR^n \st \abs{f(x)} > t}
.\]

## 2010 6.5

Suppose $F \subseteq \RR$ with $m(F^c) < \infty$ and let \( \delta(x) \da d(x, F) \) and
\[
I_F(x) \da \int_\RR { \delta(y) \over \abs{x-y}^2 } \dy
.\]

a. Show that \( \delta \) is continuous.

b. Show that if $x\in F^c$ then $I_F(x) = \infty$.

c. Show that $I_F(x) < \infty$ for almost every $x$




## 2010 7.1

Let $(X, \mathcal{M}, \mu)$ be a measure space and prove the following properties of $L^ \infty (X, \mathcal{M}, \mu)$:

- If $f, g$ are measurable on $X$ then 
\[
\norm{fg}_1 \leq \norm{f}_1 \norm{g}_{\infty }
.\]

- $\norm{\wait}_{\infty }$ is a norm on $L^{\infty }$ making it a Banach space.

- $\norm{f_n - f}_{\infty } \converges{n\to \infty }\to 0 \iff$ there exists an $E\in \mathcal{M}$ such that $\mu(X\sm E) = 0$ and $f_n \to f$ uniformly on $E$. 

- Simple functions are dense in $L^{\infty }$.


## 2010 7.2

Show that for $0 < p < q \leq \infty$, $\norm{a}_{\ell^q} \leq \norm{a}_{\ell^p}$ over $\CC$, where $\norm{a}_{\infty } \da \sup_j \abs{a_j}$.

## 2010 7.3

Let $f, g$ be non-negative measurable functions on $[0, \infty)$ with
\[
A &\da \int_0^{\infty } f(y) y^{-1/2} \dy < \infty \\
B &\da \qty{ \int_0^{\infty } \abs{ g(y) } }^2 \dy < \infty  
.\]

Show that
\[
\int_0^{\infty } \qty{ \int_0^{\infty } f(y) \dy } {g(x) \over x} \dx \leq AB
.\]

## 2010 7.4

Let $(X, \mathcal{M}, \mu)$ be a measure space and $0 < p < q< \infty$.
Prove that if $L^q(X) \subseteq L^p(X)$, then $X$ does not contain sets of arbitrarily large finite measure.

## 2010 7.5

Suppose $0 < a < b \leq \infty$, and find examples of functions $f \in L^p((0, \infty ))$ if and only if:

- $a < p < b$

- $a \leq p \leq b$

- $p = a$

*Hint: consider functions of the following form:*
\[
f(x) \da x^{- \alpha} \abs{ \log(x) }^{ \beta}
.\]

## 2010 7.6

Define
\[
F(x) &\da \qty{ \sin(\pi x) \over \pi x}^2 \\
G(x) &\da 
\begin{cases}
1 - \abs{x} & \abs{x} \leq 1
\\
0 & \text{else}.
\end{cases}
\]

a. Show that $\fourier{G}(\xi) = F(\xi)$

b. Compute $\fourier{F}$.

c. Give an example of a function $g\not \in L^1(\RR)$ which is the Fourier transform of an $L^1$ function.

*Hint: write \( \fourier{G}(\xi) = H(\xi) + H(-\xi) \)  where*
\[
H(\xi) \da e^{2\pi i \xi} \int_0^1 y e^{2\pi i y \xi }\dy 
.\]

## 2010 7.7

Show that for each \( \epsilon>0 \) the following function is the Fourier transform of an $L^1(\RR^n)$ function:
\[
F(\xi) \da \qty{1 \over 1 + \abs{\xi}^2}^{\epsilon}
.\]


*Hint: show that*

\[
K_\delta(x) &\da \delta^{-n/2} e^{-\pi \abs{x}^2 \over \delta} \\
f(x) &\da \int_0^{\infty } K_{\delta}(x) e^{-\pi \delta} \delta^{\epsilon - 1} \,d \delta \\
\Gamma(s) &\da \int_0^{\infty } e^{-t} t^{s-1} \dt \\
\implies \fourier{f}(\xi) &= \int_0^{\infty } e^{- \pi \delta \abs{\xi}^2} e^{ -\pi \delta} \delta^{\epsilon - 1}
= \pi^{-s} \Gamma(\epsilon) F(\xi)
.\]


## 2010 7 Challenge 1: Generalized Holder

Suppose that
\[
1\leq p_j \leq \infty, && \sum_{j=1}^n {1\over p_j} = {1\over r} \leq 1
.\]

Show that if $f_j \in L^{p_j}$ for each $1\leq j \leq n$, then
\[
\prod f_j \in L^r, && \norm{ \prod f_j }_r \leq \prod \norm{f_j}_{p_j}
.\]


## 2010 7 Challenge 2: Young's Inequality

Suppose $1\leq p,q,r \leq \infty$ with
\[
{1\over p } + {1 \over q} = 1 + {1 \over r}
.\]

Prove that
\[
f \in L^p, g\in L^q \implies f \convolve g \in L^r \text{ and } \norm{f \convolve g}_r \leq \norm{f}_p \norm{g}_q
.\]





## 2010 9.1

Show that the set \( \ts{ u_k(j) \da \delta_{ij} } \subseteq \ell^2(\ZZ) \) and forms an orthonormal system.


## 2010 9.2

Consider $L^2([0, 1])$ and define
\[
e_0(x) &= 1 \\
e_1(x) &= \sqrt{3}(2x-1)
.\]

a. Show that $\ts{e_0, e_1}$ is an orthonormal system.

b. Show that the polynomial $p(x)$ where $\deg(p) = 1$ which is closest to $f(x) = x^2$ in $L^2([0, 1])$ is given by
\[
h(x) = x - {1\over 6}
.\]

Compute $\norm{f - g}_2$.


## 2010 9.3

Let $E \subseteq H$ a Hilbert space.

a. Show that $E\perp \subseteq H$ is a closed subspace.

b. Show that $(E^\perp)^\perp = \cl_H(E)$.

## 2010 9.5b

Let $f\in L^1((0, 2\pi))$.

i. Show that for an \( \epsilon>0 \) one can write $f = g+h$ where $g\in L^2((0, 2\pi))$ and $\norm{H}_1 < \epsilon$.

 
## 2010 9.6

Prove that every closed convex $K \subset H$ a Hilbert space has a unique element of minimal norm.

## 2010 9 Challenge 

Let $U$ be a unitary operator on $H$ a Hilbert space, let $M \da \ts{x\in H \st Ux = x}$, let $P$ be the orthogonal projection onto $M$, and define
\[
S_N \da {1\over N} \sum_{n=0}^{N-1} U^n
.\]
Show that for all $x\in H$,
\[
\norm{ S_N x - Px}_H \converges{N\to \infty } \to 0
.\]


## 2010 10.1

Let $\nu, \mu$ be signed measures, and show that
\[
\nu \perp \mu \text{ and } \nu \ll \abs{ \mu} \implies \nu = 0
.\]


## 2010 10.2

Let $f\in L^1(\RR^n)$ with $f\neq 0$.

a. Prove that there exists a $c>0$ such that
\[
Hf(x) \geq {c \over (1 + \abs x)^n }
.\]

## 2010 10.3

Consider the function
\[
f(x) \da 
\begin{cases}
{1\over \abs{x} \qty{ \log\qty{1\over x}}^2 } &  \abs{x} \leq {1\over 2}
\\
0 & \text{else}.
\end{cases}
\]

a. Show that $f \in L^1(\RR)$.

b. Show that there exists a $c>0$ such that for all $\abs{x} \leq 1/2$,
\[
Hf(x) \geq {c \over \abs{x} \log\qty{1\over \abs x} }
.\]
Conclude that $Hf$ is not locally integrable.


## 2010 10.4

Let $f\in L^1(\RR)$ and let \( \mathcal{U}\da \ts{(x, y) \in \RR^2 \st y > 0}  \) denote the upper half plane.
For $(x, y) \in \mathcal{U}$ define 
\[
u(x, y) \da f \convolve P_y(x) && \text{where } P_y(x) \da {1\over \pi}\qty{y \over t^2 + y^2}
.\]

a. Prove that there exists a constant $C$ independent of $f$ such that for all $x\in \RR$, 
\[
\sup_{y > 0} \abs{ u(x, y) } \leq C\cdot Hf(x)
.\]


    *Hint: write the following and try to estimate each term:*
\[
u(x, y) = \int_{\abs t < y} f(x - t) P_y(t) \dt + \sum_{k=0}^{\infty } \int_{A_k} f(x-t) P_y(t)\dt && A_k \da \ts{2^ky \leq \abs t < 2^{k+1}y}
.\]

b. Following the proof of the Lebesgue differentiation theorem, show that for $f\in L^1(\RR)$ and for almost every $x\in \RR$,
\[
u(x, y) \converges{y\to 0} \to f(x)
.\]

