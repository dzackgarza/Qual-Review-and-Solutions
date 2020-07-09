# Laurent Expansions and Singularities (8155f)

## 1

Let $f(z) = {z+1\over z(z-1)}$.

About $z=0$:

\begin{align*}
f(z) 
&= (z+1) \qty{- {1 \over z} + {1\over z-1} } \\
&=  -(z+1) \qty{{1\over z} + \sum_{n=0}^\infty z^n } \\
&= -(z+1)\sum_{n=-1}^\infty z^n \\
&= {1\over z} + 2\sum_{n=0}^\infty z^n \\
&= -{1\over z} -2 - 2z - 2z^2 - \cdots
.\end{align*}

About $z=1$:

\begin{align*}
f(z) 
&= \qty{(1-z) -2 \over 1-z} \qty{1 \over 1 - (1-z)} \\
&= \qty{1 - {2\over 1-z}} \sum_{n=0}^\infty (1-z)^n \\ 
&= \sum_{n=0}^\infty (1-z)^n - 2 \sum_{n=-1}^\infty (1-z)^n \\
&= -{2\over 1-z} - \sum_{n=0}^\infty (1-z)^n \\
&= {2\over z-1} + \sum_{n=0}^\infty (-1)^{n+1} (z-1)^n \\
&= {2\over z-1} - 1 + (z-1) - (z-1)^2 + \cdots
.\end{align*}


## 2

\begin{align*}
e^{1\over z} = \sum_{n=0}^\infty {1\over n!} \qty{1\over z}^n = 1 + {1\over z} + {1 \over 2z^2} + {1\over 6z^3} + \cdots
.\end{align*}

\begin{align*}
\cos\qty{1\over z} 
&= {1\over 2}\qty{ e^{i\over z} + e^{-{i\over z}} }  \\
&= {1\over 2} \sum_{n=0}^\infty {1\over n!}\qty{ \qty{i\over z}^n + \qty{-i \over z}^n  } \\
&= \sum_{n=0}^\infty {(-1)^n \over (2n)!} \qty{1\over z}^{2n}
.\end{align*}

## 8

Idea: show their $f-g$ is analytic by taking away all of the negative powers, and bounded by (c).
