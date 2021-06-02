# Topology and Functions of One Variable

## 1 $\work$
Let $x_0 = a, x_1 = b$, and set
\[  
x_n \definedas {x_{n-1} + x_{n-2} \over 2} \quad n\geq 2
.\]

Show that $\theset{x_n}$ is a Cauchy sequence and find its limit in terms of $a$ and $b$.

## 2 $\work$
Suppose $f:\RR\to\RR$ is continuous and $\lim_{x\to \pm \infty} f(x) = 0$.
Prove that $f$ is uniformly continuous.

## 3 $\work$
Give an example of a function $f:\RR\to \RR$ that is everywhere differentiable but $f'$ is not continuous at 0.

## 4 $\work$
Suppose $\theset{g_n}$ is a uniformly convergent sequence of functions from $\RR$ to $\RR$ and $f:\RR\to \RR$ is uniformly continuous.
Prove that the sequence $\theset{f\circ g_n}$ is uniformly convergent.

## 5 $\work$
Let $f$ be differentiable on $[a, b]$.
Say that $f$ is *uniformly differentiable* iff 

\[  
\forall \varepsilon > 0,\, \exists \delta > 0 \text{ such that } \quad \abs{x-y} < \delta \implies \abs{ {f(x) - f(y) \over x-y}  - f'(y)}  < \eps
.\]

Prove that $f$ is uniformly differentiable on $[a, b] \iff f'$ is continuous on $[a, b]$.

## 6 $\work$
Suppose $A, B \subseteq \RR^n$ are disjoint and compact.
Prove that there exist $a\in A, b\in B$ such that
\[  
\norm{a - b} = \inf\theset{\norm{x-y} \suchthat x\in A,\, y\in B}
.\]

## 7 $\work$
Suppose $A, B\subseteq \RR^n$ are connected and not disjoint.
Prove that $A\union B$ is also connected.

## 8 $\work$
Suppose $\theset{f_n}_{n\in \NN}$ is a sequence of continuous functions $f_n: [0, 1]\to \RR$ such that 
\[  
f_n(x) \geq f_{n+1}(x) \geq 0 \quad \forall n\in \NN,\, \forall x\in [0, 1]
.\]
Prove that if $\theset{f_n}$ converges pointwise to $0$ on $[0, 1]$ then it converges to $0$ uniformly on $[0, 1]$.

## 9 $\work$
Show that if $E\subset [0, 1]$ is uncountable, then there is some $t\in \RR$ such that $E\intersect (-\infty ,t)$ and $E\intersect (t, \infty)$ are also uncountable.


## 1 $\work$

Suppose $f, g: [0, 1] \to \RR$ where $f$ is Riemann integrable and for $x, y\in [0, 1]$,
\[
\abs{g(x) - g(y)} \leq \abs{f(x) - f(y)}
.\]

Prove that $g$ is Riemann integrable.

# Several Variables

## 1 $\work$
Is the following function continuous, differentiable, continuously differentiable?
\[  
f: \RR^2 &\to \RR  \\
f(x, y) &= 
\begin{cases}
{xy \over \sqrt{x^2 + y^2}} & (x, y) \neq (0, 0) \\
0 & \text{else}.
\end{cases}
\]

## 2 $\work$

a.  $\work$
Complete this definition: "$f: \RR^n\to \RR^m$ is real-differentiable a point $p\in \RR^n$ iff there exists a linear transformation..."

b. $\work$
Give an example of a function $f:\RR^2\to \RR$ whose first-order partial derivatives exist everywhere but $f$ is not differentiable at $(0, 0)$.

c. $\work$
Give an example of a function $f: \RR^2 \to \RR$ which is real-differentiable everywhere but nowhere complex-differentiable.

## 3 $\work$
Let $f:\RR^2\to \RR$.

a. $\work$
Define in terms of linear transformations what it means for $f$ to be differentiable at a point $(a, b) \in \RR^2$.

b. $\work$
State a version of the inverse function theorem in this setting.

c. $\work$
Identify $\RR^2$ with $\CC$ and give a necessary and sufficient condition for a real-differentiable function at $(a, b)$ to be complex differentiable at the point $a+ib$.

## 4 $\work$
Let $f = u+iv$ be complex-differentiable with continuous partial derivatives at a point $z = re^{i\theta}$ with $r\neq 0$.
Show that
\[  
\dd{u}{r} = {1\over r}\dd{v}{\theta} \qquad \dd{v}{r} = -{1\over r}\dd{u}{\theta}
.\]

## 5 $\work$
Let $P = (1, 3) \in \RR^2$ and define
\[  
f(s, t) \definedas ps^3 -6st + t^2
.\]

a. $\work$
State the conclusion of the implicit function theorem concerning $f(s, t) = 0$ when $f$ is considered a function $\RR^2\to\RR$.

b. $\work$
State the above conclusion when $f$ is considered a function $\CC^2\to \CC$.

c. $\work$
Use the implicit function theorem for a function $\RR\cross \RR^2 \to \RR^2$ to prove (b).

> There are various approaches: using the definition of the complex derivative, the Cauchy-Riemann equations, considering total derivatives, etc.

## 6 $\work$
Let $F:\RR^2\to \RR$ be continuously differentiable with $F(0, 0) = 0$ and $\norm{\nabla F(0, 0)} < 1$.

Prove that there is some real number $r> 0$ such that $\abs{F(x, y)} < r$ whenever $\norm{(x, y)} < r$.

## 7 $\work$
State the most general version of the implicit function theorem for real functions and outline how it can be proved using the inverse function theorem.


# Several Variables: Extra Questions

## ?  
Let $f=u+iv$ be differentiable (i.e. $f'(z)$ exists) with continuous partial derivatives at a point $z=re^{i\theta}$, $r\not= 0$. 

Show that
$$
\frac{\partial u}{\partial r}=\frac{1}{r}\frac{\partial v}{\partial \theta},\quad
\frac{\partial v}{\partial r}=-\frac{1}{r}\frac{\partial u}{\partial \theta}
.$$

## ?

Give an example of a

Show that $f(z) = z^2$ is uniformly continuous in any open disk
$|z| < R$, where $R>0$ is fixed, but it is not uniformly continuous on
$\mathbb C$.

1.
Show that the function $u=u(x,y)$ given by
$$
u(x,y)=\frac{e^{ny}-e^{-ny}}{2n^2}\sin nx\quad \text{for}\ n\in {\mathbf N}
$$
is the solution on $D=\{(x,y)\ | x^2+y^2<1\}$ of the Cauchy problem for the Laplace equation
$$\frac{\partial ^2u}{\partial x^2}+\frac{\partial ^2u}{\partial y^2}=0,\quad
u(x,0)=0,\quad \frac{\partial u}{\partial y}(x,0)=\frac{\sin nx}{n}.$$

2.
Show that there exist points $(x,y)\in D$ such that $\displaystyle{\limsup_{n\to\infty} |u(x,y)|=\infty}$.

### Tie's Extra Questions: Fall 2009

Let $f=u+iv$ be differentiable (i.e. $f'(z)$ exists) with continuous
partial derivatives at a point $z=re^{i\theta}$, $r\not= 0$. Show
that
$$\frac{\partial u}{\partial r}=\frac{1}{r}\frac{\partial v}{\partial \theta},\quad
\frac{\partial v}{\partial r}=-\frac{1}{r}\frac{\partial u}{\partial \theta}.$$

## Spring 2020 HW 1 # 10

a. Show that in polar coordinates, the Cauchy-Riemann equations take the form
\[
\frac{\partial u}{\partial r}=\frac{1}{r} \frac{\partial v}{\partial \theta} \text { and } \frac{\partial v}{\partial r}=-\frac{1}{r} \frac{\partial u}{\partial \theta}
.\]

b. Use (a) to show that the logarithm function, defined as 
\[
\log z=\log r+i \theta \text { where } z=r e^{i \theta} \text { with }-\pi<\theta<\pi
.\]
is holomorphic on the region $r> 0, -\pi < \theta < \pi$.

Also show that this function is not continuous in $r>0$.


