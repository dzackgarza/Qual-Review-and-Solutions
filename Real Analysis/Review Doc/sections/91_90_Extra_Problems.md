# Extra Problems 

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

*Hint: write the following and try to estimate each term:*
\[
u(x, y) = \int_{\abs t < y} f(x - t) P_y(t) \dt + \sum_{k=0}^{\infty } \int_{A_k} f(x-t) P_y(t)\dt && A_k \da \ts{2^ky \leq \abs t < 2^{k+1}y}
.\]

Following the proof of the Lebesgue differentiation theorem, show that for $f\in L^1(\RR)$ and for almost everywhere $x\in \RR$,
\[
u(x, y) \converges{y\to 0} \to f(x)
.\]



