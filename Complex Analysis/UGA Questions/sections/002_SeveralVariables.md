# Several Variables (8155h)

## 1
Is the following function continuous, differentiable, continuously differentiable?
\[  
f: \RR^2 &\to \RR  \\
f(x, y) &= 
\begin{cases}
{xy \over \sqrt{x^2 + y^2}} & (x, y) \neq (0, 0) \\
0 & \text{else}.
\end{cases}
\]

## 2

### a 
Complete this definition: "$f: \RR^n\to \RR^m$ is real-differentiable a point $p\in \RR^n$ iff there exists a linear transformation..."

### b
Give an example of a function $f:\RR^2\to \RR$ whose first-order partial derivatives exist everywhere but $f$ is not differentiable at $(0, 0)$.

### c
Give an example of a function $f: \RR^2 \to \RR$ which is real-differentiable everywhere but nowhere complex-differentiable.

## 3
Let $f:\RR^2\to \RR$.

### a
Define in terms of linear transformations what it means for $f$ to be differentiable at a point $(a, b) \in \RR^2$.

### b
State a version of the inverse function theorem in this setting.

### c
Identify $\RR^2$ with $\CC$ and give a necessary and sufficient condition for a real-differentiable function at $(a, b)$ to be complex differentiable at the point $a+ib$.

## 4
Let $f = u+iv$ be complex-differentiable with continuous partial derivatives at a point $z = re^{i\theta}$ with $r\neq 0$.
Show that
\[  
\dd{u}{r} = {1\over r}\dd{v}{\theta} \qquad \dd{v}{r} = -{1\over r}\dd{u}{\theta}
.\]

## 5
Let $P = (1, 3) \in \RR^2$ and define
\[  
f(s, t) \definedas ps^3 -6st + t^2
.\]

### a
State the conclusion of the implicit function theorem concerning $f(s, t) = 0$ when $f$ is considered a function $\RR^2\to\RR$.

### b
State the above conclusion when $f$ is considered a function $\CC^2\to \CC$.

### c
Use the implicit function theorem for a function $\RR\cross \RR^2 \to \RR^2$ to prove (b).

