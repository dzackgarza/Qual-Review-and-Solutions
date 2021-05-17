This document is a collection of solutions to various problems written
up by the participants of the May 2020 Analysis Qualifying Exam
Workshop. This is in no way meant to be an official source for solutions
to old exam problems, but is simply meant to be a repository of
solutions to problems worked on during the workshop. You may use this to
help you study for the analysis qualifying exam, but before you read the
solutions to any problems, you should attempt the problem on your own.

# May 2016 Qual

1.  (May 2016, \#1) Consider the function $f(x) = \frac{x}{1-x^2}$,
    $x \in (0,1)$.

    1.  By using the $\epsilon-\delta$ definition of the limit only,
        prove that $f$ is continuous on $(0,1)$. (Note: You are not
        allowed to trivialize the problem by using properties of
        limits).

        ::: {.proof}
        *Proof.* Fix $x\in (0,1)$ and let $\epsilon > 0$. Then we have
        $$\left |f(x) - f(y) \right| 
                = \left|\frac{x}{1-x^2} - \frac{y}{1-y^2}\right| 
                = \left| \frac{x(1-y^2) - y(1-x^2)}{(1-x^2)(1-y^2)} \right|
                = \left| \frac{x-y}{(1-x)(1+x)(1-y)(1+y)} \right|.$$
        Now, choose $\delta > 0$ such that
        $\delta < \min\{\frac{1}{2}(1-x)^2\epsilon, \frac{1}{2}(1-x)\}$.
        When $x - \delta < y < x + \delta$, $$\begin{aligned}
                |f(x) - f(y) | & = & 
                \left| \frac{x-y}{(1-x)(1+x)(1-y)(1+y)} \right| \\
                & \leq & \left| \frac{x-y}{(1-x)(1-y)} \right| 
                \leq  \left| \frac{x-y}{(1-x)(1-(x+ \frac{1}{2}(1 - x)))} \right| \\
                & = & \left| \frac{x-y}{(1-x)(1-(x+ \frac{1}{2}(1 - x)))} \right|
                = \left| \frac{2}{(1-x)^2} \right||x-y| \\
                & < & \epsilon.
            \end{aligned}$$

        As our choice of $x\in (0,1)$ was arbitrary, we conclude that
        $f$ is continuous on all of $(0,1)$. ◻
        :::

    2.  Is $f$ uniformly continuous on $(0,1)$? Justify your answer.

        ::: {.proof}
        *Proof.* We will show that the function $f$ is not uniformly
        continuous. Consider the sequence $(x_n)_{n=1}^\infty$ in
        $(0,1)$ defined by $x_n = \frac{n}{n+1}$. Observe that
        $$f(x_n) = \frac{\frac{n}{n+1}}{1-\left(\frac{n}{n+1}\right)^2} 
            = \frac{n(n+1)}{(n+1)^2 - n^2} = \frac{n(n+1)}{[(n+1)-n][(n+1)+n]} 
            = \frac{n(n+1)}{2n+1}$$ Written as
        $x_n = 1 - \frac{1}{n+1}$, one can more easily see that
        $(x_n)_{n=1}^\infty$ converges to $1$ in $\mathbb{R}$, hence is
        Cauchy in $(0,1)$. Now, let $\delta > 0$ and choose
        $N\in \mathbb{N}$ such that $|x_n - x_m| < \delta$ when
        $n,m \geq N$. For $\epsilon < \frac{1}{8}$ we have

        $$\begin{aligned}
              \left| f(x_n) - f(x_{n+1}) \right|
            &=& \left|\frac{n(n+1)}{2n+1} - \frac{(n+1)(n+2)}{2n+3} \right| 
            = \left|\frac{n(n+1)(2n+3) - (n+1)(n+2)(2n+1)}{(2n+1)(2n+3)}  \right| \\ 
            &=&  \left|\frac{(2n^3+5n^2+3n) - (2n^3+7n^2+7n+2)}{(2n+1)(2n+3)}  \right|
            = \left|\frac{ 2n^2+4n+2 }{4n^2 + 8n + 3}  \right| \\
            &\geq& \left| \frac{2n^2}{ 16n^2 } \right| =  \frac{1}{8}.\end{aligned}$$
        So for any $\delta > 0$, we see that there exists two points
        $x_n, x_{n+1} \in (0,1)$ such that $|x_n - x_{n+1}| < \delta$
        when $n$ is sufficiently large but
        $f(x_n) - f(x_{n+1}) | \not < \epsilon$. Therefore $f(x)$ is not
        uniformly continuous. ◻
        :::

2.  Let $\{a_k\}_{k=1}^\infty$ be a bounded sequence of real numbers and
    $E$ given by:
    $$E:= \bigg\{s \in \mathbb{R}\, \colon \, \text{ the set } \{k \in \mathbb{N}\, \colon \, a_k \geq s\} \text{ has at most finitely many elements}\bigg\}.$$
    Prove that $\limsup_{k \to \infty} a_k = \inf E$.

    ::: {.proof}
    *Proof.* Let $e \in E$. As there are only finitely many
    $a_k \geq s$, there exists some $N \in \mathbb{N}$ such that
    $a_k < e$ for all $k \geq N$. Define $T_k := \{a_k : k \geq n\}$. It
    is clear that $e$ is thus an upper bound for $T_N$. So,
    $$e \geq \sup T_N \geq \limsup a_k.$$ Thus, $\limsup a_k$ is a lower
    bound for $E$, meaning $\inf E \geq \limsup a_n$.\
    Conversely, suppose $k \in \mathbb{N}$.
    $$T_k = \{a_n : n \geq k \}.$$ So, $\sup T_k \geq a_n$ for all
    $a_n \in T_k$. Then, $\{a_k : a_k \geq \sup T_k\}$ must be finite,
    so $\{k \in \mathbb{N} : a_k \geq \sup T_k\}$ is finite. So,
    $\sup T_k \in E$ for all $k \in \mathbb{N}$. Since $\inf E$ is a
    lower bound for $E$, $\inf E \leq \sup T_k$ for all
    $k \in \mathbb{N}$. Thus,
    $$\inf E \leq \lim (\sup T_k) = \limsup a_k.$$ We have both
    inequalities, therefore $\limsup a_k = \inf E$. ◻
    :::

3.  Assume $(X,d)$ is a compact metric space.

    1.  Prove that $X$ is both complete and separable.

        ::: {.proof}
        *Proof.* ◻
        :::

    2.  Suppose $\{x_k\}_{k=1}^\infty \subseteq X$ is a sequence such
        that the series $\sum_{k=1}^\infty d(x_k, x_{k+1})$ converges.
        Prove that the sequence $\{x_k\}_{k=1}^\infty$ converges in $X$.

        ::: {.proof}
        *Proof.* ◻
        :::

4.  Suppose that $f \colon [0,2] \to \mathbb{R}$ is continuous on
    $[0,2]$ , differentiable on $(0,2)$, and such that
    $f(0) = f(2) = 0$, $f(c) = 1$ for some $c \in (0,2)$. Prove that
    there exists $x \in (0,2)$ such that $|f'(x)| >1.$

    ::: {.proof}
    *Proof.* We will consider three cases. First, suppose $c<1$. Then,
    by the mean value theorem, there exists $x\in (0,c)$ such that
    $f'(x)(c-0)=f(c)-f(0)$ so $f'(x)=\frac{f(c)}{c}=\frac{1}{c}>1$ since
    $c<1$. Similarly, if $c>1$ then by the mean value theorem there
    exits $y\in (c,2)$ such that
    $$|f'(y)|=\left\lvert\frac{f(2)-f(c)}{2-c}\right\rvert=\left\lvert \frac{-f(c)}{2-c}\right\rvert=\left\lvert\frac{-1}{2-c}\right\rvert>1$$
    since $1<c<2$.

    Now, suppose $c=1$. If there exists $x\in (0,1)$ such that $x<f(x)$
    then by the mean value theorem on the interval $(0,x)$ there exists
    $s\in (0,x)$ such that $f'(s)=\frac{f(x)}{x}>1$ since $f(x)>x$.
    Likewise, if there exists $x\in (0,1)$ such that $x>f(x)$ then the
    mean value theorem on $(x,1)$ gives a point $t\in (x,1)$ such that
    $\left\lvert f'(t)\right\rvert=\left\lvert \frac{f(1)-f(x)}{1-x}\right\rvert=\left\lvert\frac{1-f(x)}{1-x}\right\rvert>1$
    since $x>f(x)$. So, on $(0,1)$, if the proposition does not hold
    then $f(x)=x$. Similarly, if there exists $x\in (1,2)$ such that
    $f(x)>2-x$ then the mean value theorem yields a point $u\in (x,2)$
    such that
    $|f'(u)|=\left\lvert \frac{f(2)-f(x)}{2-x}\right\rvert=\left\lvert \frac{-f(x)}{2-x}\right\rvert>1$
    since $f(x)>2-x$. If there exists $y\in (1,2)$ such that $f(y)<2-y$
    then again by the mean value theorem there exists $v\in (1,y)$ such
    that
    $|f'(v)|=\left\lvert\frac{f(y)-f(1)}{y-1}\right\rvert=\left\lvert\frac{f(y)-1}{y-1}\right\rvert>1$
    since $f(y)<2-y$ so $|f(y)-1|>|y-1|$. So, on $(1,2)$ if the
    proposition does not hold then $f(x)=2-x$. However, notice that
    since $f(x)$ is differentiable at $x=1$ we cannot have $f(x)=x$ on
    $(0,1)$ and $f(x)=2-x$ on $(1,2)$. ◻
    :::

5.  Let $f_n(x) = n^\beta x(1-x^2)^n$, $x \in [0,1]$,
    $n \in \mathbb{N}$.

    1.  Prove that $\{f_n\}_{n=1}^\infty$ converges pointwise on $[0,1]$
        for every $\beta \in \mathbb{R}$.

        ::: {.proof}
        *Proof.* ◻
        :::

    2.  Show that the convergence in part (a) is uniform for all
        $\beta < \frac{1}{2}$, but not uniform for any
        $\beta \geq \frac{1}{2}$.

        ::: {.proof}
        *Proof.* ◻
        :::

6.  1.  Suppose $f \colon [-1,1] \to \mathbb{R}$ is a bounded function
        that is continuous at $0$. Let $\alpha(x) = -1$ for
        $x \in [-1,0]$ and $\alpha(x)=1$ for $x \in (0,1]$. Prove that
        $f \in \mathcal{R}(\alpha)[-1,1]$, i.e., $f$ is Riemann
        integrable with respect to $\alpha$ on $[-1,1]$, and
        $\int_{-1}^1 f d\alpha = 2f(0)$.

        ::: {.proof}
        *Proof.* Let $\epsilon>0$. Choose $\delta >0$ so that if
        $|x|<\delta$, then $|f(x)-f(0)|<\epsilon$. Let $P$ be a
        partition of $[-1,1]$ with $0 \in P$ and
        $\operatorname{mesh}(P)<\delta$. Then
        $|U(f,P,\alpha)-L(f,P,\alpha)|=|\sum_{i=1}^n(M_i-m_i)\Delta \alpha_i|=(|\sup_{x \in [0,x_k]}f(x)-\inf_{x \in [0,x_k]}f(x)|)2<4\epsilon$.
        Thus $f$ is integrable with respect to $\alpha$. Additionally,
        we have $L(f,P,\alpha)\leq 2f(0)\leq U(f,P,\alpha)$ for all
        partitions $P$ of the form described above, and so
        $\int_{-1}^1 f d\alpha = 2f(0)$. ◻
        :::

    2.  Let $g \colon [0,1] \to \mathbb{R}$ be a continuous function
        such that $\int_0^1 g(x)x^{3k+2} dx = 0$ for all
        $k = 0, 1, 2, \ldots$. Prove that $g(x) =0$ for all
        $x \in [0,1]$.

        ::: {.proof}
        *Proof.* Since $g(x)$ is continuous, so is $g(x^{1/3})$. Thus by
        the Weierstrauss Approximation Theorem, we can find a sequence
        of polynomials $(p_n(x))\to g(x^{1/3})$ uniformly. Since this
        holds for all values $x\in [0,1]$, we have that $(p_n(x^3))$
        converges to $g(x)$ uniformly. Then we have $(x^2p_n(x^3))$
        converges to $x^2g(x)$ uniformly. Note that by assumption,
        $\int_0^1 g(x)x^2p_n(x^3)dx=0$, and so
        $0 = \lim_{n \to \infty}\int_0^1 g(x)x^2p_n(x^3)dx=\int_0^1 \lim_{n \to \infty}g(x)x^2p_n(x^3)dx=\int_0^1x^2g^2(x)dx$.
        Since $x^2g^2(x)$ is non-negative, and its integral is zero, we
        conclude that $x^2g^2(x)=0$ for all $x$. Therefore, we have
        $g(x)=0$. ◻
        :::

# Metric Spaces and Topology

1.  (May 2019, \#1) Let $(M, d_M)$, $(N, d_N)$ be metric spaces. Define
    $d_{M \times N} \colon (M \times N) \times (M \times N) \to \mathbb{R}$
    by
    $$d_{M \times N}((x_1, y_1), (x_2, y_2)) := d_M(x_1, x_2) + d_N(y_1, y_2).$$

    1.  Prove that $(M \times N, d_{M \times N})$ is a metric space.

        ::: {.proof}
        *Proof.* To prove that $(M \times N, d_{M \times N})$ is a
        metric space we must prove that $d_{M\times N}$ is a metric on
        $M \times N$.

        -   Positive Definite-

            Let $(x_1,y_1), (x_2,y_2) \in M \times N$. Then since $d_M$
            is a metric on $M$, then $d_M(x_1,x_2)\geq 0$ for all
            $x_i,x_j \in M$ and $d_N$ is a metric on $N$ and likewise
            $d_N(y_1,y_2)\geq 0$ for any $y_i,y_j \in N.$

            Then by definition
            $d_{M\times N}((x_1,y_1),(x_2,y_2))=d_M(x_1,x_2)+d_N(y_1,y_2)\geq 0 + 0 =0.$
            Hence since $(x_1,y_1),(x_2,y_2)$ are arbitrary,
            $d_{M\times N}((x_1,y_1),(x_2,y_2))\geq 0$ for all
            $(x_i,y_i),(x_j,y_j)\in M \times N$.

            Suppose that $d_{M \times N}((x_1,y_1),(x_2,y_2))=0.$ By
            definition
            $d_{M \times N}((x_1,y_1),(x_2,y_2))=d_M(x_1,x_2)+d_N(y_1,y_2)$.
            Therefore $d_M(x_1,x_2)+d_N(y_1,y_2)=0$, since $d_M, d_N$
            are metrics, then $d_M(x_1,x_2)\geq 0, d_N(y_1,y_2)\geq 0$,
            which implies that $d_M(x_1,x_2)=d_N(y_1,y_2)=0$ and also
            since they are metrics we have that $x_1=x_2, y_1=y_2.$
            Hence, $(x_1,y_1)=(x_2,y_2).$

            Now suppose that $(x_1,y_1)=(x_2,y_2).$ Then
            $x_1=x_2, y_1=y_2$ and for the metrics $d_M, d_N$ we would
            have $d_M(x_1,x_2)=0, d_N(y_1,y_2)=0.$ Thus
            $d_{M \times N}((x_1,y_1),(x_2,y_2))=d_M(x_1,x_2)+d_N(y_1,y_2)=0+0=0$.

            Therefore $d_{M \times N}((x_1,y_1),(x_2,y_2))=0$ if and
            only if $(x_1,y_1)=(x_2,y_2).$

        -   Symmetric

            Let $(x_1,y_1), (x_2,y_2) \in M \times N$. Then since $d_M$
            is a metric on $M$, then $d_M(x_1,x_2)=d_M(x_2,x_1)$ for all
            $x_i,x_j \in M$ and $d_N$ is a metric on $N$ and likewise
            $d_N(y_1,y_2)=d_N(y_2,y_1)$ for any $y_i,y_j \in N.$
            Therefore, $$\begin{aligned}
                    d_{M \times N}((x_1,y_1),(x_2,y_2))&=d_M(x_1,x_2)+d_N(y_1,y_2)\\
                    &=d_M(x_2,x_1)+d_N(y_2,y_1)\\
                    &=d_{M \times N}((x_2,y_2),(x_1,y_1)).
                \end{aligned}$$

        -   Triangle Inequality

            Since $d_M, d_N$ are metrics then for all
            $x_1,x_2,x_3 \in M, y_1,y_2,y_3 \in N$ we have that
            $d_M(x_1,x_2)\leq d_M(x_1,x_3)+d_M(x_3,x_2)$ and that
            $d_N(y_1,y_2)\leq d_N(y_1,y_3)+d_N(y_3,y_2).$ Therefore,
            $$\begin{aligned}
                    d_{M \times N}((x_1,y_1),(x_2,y_2))&=d_M(x_1,x_2)+d_N(y_1,y_2)\\
                  d_M(x_1,x_2)+d_N(y_1,y_2) &\leq d_M(x_1,x_3)+d_M(x_3,x_2)+d_N(y_1,y_3)+d_N(y_3,y_2)\\
                   d_M(x_1,x_3)+d_M(x_3,x_2)+d_N(y_1,y_3)+d_N(y_3,y_2) &=d_M(x_1,x_3)+d_N(y_1,y_3)+d_M(x_3,x_2)+d_N(y_3,y_2)\\
                  d_M(x_1,x_3)+d_N(y_1,y_3)+d_M(x_3,x_2)+d_N(y_3,y_2)&=d_M((x_1,y_1),(x_3,y_3))+d_M((x_3,y_3),(x_2,y_2)). 
                \end{aligned}$$

            Hence
            $d_{M \times N}((x_1,y_1),(x_2,y_2))\leq d_M((x_1,y_1),(x_3,y_3))+d_M((x_3,y_3),(x_2,y_2)).$

        Therefore $d_{M \times N}$ is a metric on $M \times N$ and
        $(M \times N, d_{M\times N})$ is a metric space. ◻
        :::

    2.  Let $S \subseteq M$ and $T \subseteq N$ be compact sets in
        $(M, d_M)$ and $(N, d_N)$, respectively. Prove that $S \times T$
        is a compact set in $(M \times N, d_{M \times N})$.

        ::: {.proof}
        *Proof.* By part a we showed that $(M \times N, d_{M \times N})$
        is a metric space. Let $\{s_n,t_n\}$ be a sequence in
        $S \times T.$ Since $\{s_n\}$ is a sequence on a compact set $S$
        in a metric space $(M,d_M)$ then it has a convergent subsequence
        ${s_{n_k}}.$ Let $\lim_{k \to \infty}{s_{n_k}}=s_0.$

        Since $\{t_{n_k}\}$ is a sequence on a compact set $T$ in a
        metric space. Thus $\{t_{n_k}\}$ has a convergent subsequence
        $\{t_{n_{k_j}}\}.$ Let $\lim_{j\to \infty} t_{n_{k_j}}=t_0.$
        Thus $\{s_{n_{k_j}}\}$ is a subsequence of $\{s_{n_k}\}.$ And
        since $\{s_{n_k}\}$ converges to $s_0$, then any subsequence
        also converges to $s_0.$

        Let $\epsilon >0$ be given. Then for $\epsilon/2$ there exists
        $N_1, N_2\in \mathbb{N}$ such that for all
        $n_{k_j}\geq N_1, d_M(s_{n_{k_j}},s_0)<\epsilon/2$, and for all
        $n_{k_j}\geq N_2, d_N(t_{n_{k_j}},t_0)<\epsilon/2$. Choose
        $N=\text{Max}(\{N_1,N_2\}).$

        Then
        $d_{M \times N}((s_{n_{k_j}},t_{n_{k_j}}),(s_0,t_0))=d_M(s_{n_{k_j}},s_0)+d_N(t_{n_{k_j}},t_0)<\epsilon/2 + \epsilon/2 = \epsilon.$

        Therefore
        $d_{M \times N}((s_{n_{k_j}},t_{n_{k_j}}),(s_0,t_0))< \epsilon.$

        Hence $\{(s_{n_{k_j}},t_{n_{k_j}})$ converges to $(s_0,t_0).$
        Therefore $S \times T$ is sequentially compact and $S \times T$
        is therefore compact. ◻
        :::

2.  (June 2003, \#1b,c) (b) Show by example that the union of infinitely
    many compact subsets of a metric space need not be compact. (c) If
    $(X,d)$ is a metric space and $K\subset X$ is compact, define
    $d(x_0,K)=\inf_{y\in K} d(x_0,y)$. Prove that there exists a point
    $y_0\in K$ such that $d(x_0,K)=d(x_0,y_0)$.

    ::: {.proof}
    *Proof.* ◻
    :::

3.  (January 2009, \#4a) Consider the metric space $(\mathbb{Q},d)$
    where $\mathbb{Q}$ denotes the rational numbers and $d(x,y)=|x-y|$.
    Let $E=\{x\in\mathbb{Q}:x>0,\,2<x^2<3\}$. Is $E$ closed and bounded
    in $\mathbb{Q}$? Is $E$ compact in $\mathbb{Q}$?

    ::: {.proof}
    *Proof.* ◻
    :::

4.  (January 2011 \#3a) Let $(X,d)$ be a metric space, $K\subset X$ be
    compact, and $F\subset X$ be closed. If $K\cap F=\emptyset$, prove
    that there exists an $\epsilon>0$ so that $d(k,f)\geq \epsilon$ for
    all $k\in K$ and $f\in F$.

    ::: {.proof}
    *Proof.* We prove this by contrapositive. Suppose for all
    $\epsilon >0$, there exists $k \in K$, $f \in F$ such that
    $d(k,f)< \epsilon$. Then for all $n \in \mathbb{N}$, we can choose
    $k_n \in K$, $f_n \in F$ such that $d(k_n, f_n) < \frac{1}{n}$.

    Since $k_n$ is a sequence in $K$, which is compact (and therefore
    sequentially compact), there exists a subsequence
    $k_{n_j} \subseteq k_n$ with the property that $k_{n_j}$ converges
    to some $k_0 \in K$. Find $N \in \mathbb{N}$ such that for
    $n \geq N$, $d(k_{n_j}, k_0) < \frac{\epsilon}{2}$ and
    $\frac{1}{n} < \frac{\epsilon}{2}$. Then
    $$d(f_{n_j}, k_0) \leq d(f_{n_j}, k_{n_j}) + d(k_{n_j}, k_0) < \frac{\epsilon}{2} + \frac{\epsilon}{2} = \epsilon$$

    Thus, $f_{n_j}$ also converges to $k_0$, and since $F$ is closed,
    $k_0 \in F$. So $K \cap F \neq \emptyset$. ◻
    :::

5.  Let $(X,d)$ be an unbounded and connected metric space. Prove that
    for each $x_0 \in X$, the set
    $\{x \in X \, \colon \,  d(x,x_0) = r\}$ is nonempty.

    ::: {.proof}
    *Proof.* ◻
    :::

# Sequences and Series

1.  (June 2013 \#1a) Let
    $a_n =\sqrt{n}\left(\sqrt{n+1}-\sqrt{n}\right)$. Prove that
    $\lim_{n\to\infty}a_n=1/2$.

    ::: {.proof}
    *Proof.* ◻
    :::

2.  (January 2014 \#2) (a) Produce sequences $\{a_n\},\,\{b_n\}$ of
    positive real numbers such that
    $$\liminf_{n\to\infty}(a_nb_n)>\left(\liminf_{n\to\infty} a_n\right) \left(\liminf_{n\to\infty} b_n\right).$$ (b)
    If $\{a_n\},\,\{b_n\}$ are sequences of positive real numbers and
    $\{a_n\}$ converges, prove that
    $$\liminf_{n\to\infty}(a_nb_n)=\left(\lim_{n\to\infty}a_n\right)\left(\liminf_{n\to\infty}b_n\right).$$

    ::: {.proof}
    *Proof.* ◻
    :::

3.  (May 2011 \#4a) Determine the values of $x\in\mathbb{R}$ for which
    $\displaystyle\sum_{n=1}^\infty \frac{x^n}{1+n|x|^n}$ converges,
    justifying your answer carefully.

    ::: {.proof}
    *Proof.* ◻
    :::

4.  (June 2005 \#3b) If the series $\sum_{n=0}^\infty a_n$ converges
    conditionally, show that the radius of convergence of the power
    series $\sum_{n=0}^\infty a_nx^n$ is 1.

    ::: {.proof}
    *Proof.* ◻
    :::

5.  (January 2011 \#5) Suppose $\{a_n\}$ is a sequence of positive real
    numbers such that $\lim_{n\to\infty}a_n=0$ and $\sum a_n$ diverges.
    Prove that for all $x>0$ there exist integers $n(1)<n(2)<\ldots$
    such that $\sum_{k=1}^\infty a_{n(k)}=x$.\
    (Note: Many variations on this problem are possible including more
    general rearrangements. You may also wish to show that if $\sum a_n$
    converges conditionally then given any $x\in\mathbb{R}$ there is a
    rearrangement of $\{b_n\}$ of $\{a_n\}$ such that $\sum b_n=r$. See
    Rudin Thm. 3.54 for a further generalization.)

    ::: {.proof}
    *Proof.* ◻
    :::

6.  (June 2008 \# 4b) Assume $\beta >0$, $a_n>0$, $n=1,2,\ldots$, and
    the series $\sum a_n$ is divergent. Show that
    $\displaystyle \sum \frac{a_n}{\beta + a_n}$ is also divergent.

    ::: {.proof}
    *Proof.* ◻
    :::

# Continuity of Functions

# Differential Calculus

1.  (June 2005 \#1a) Use the definition of the derivative to prove that
    if $f$ and $g$ are differentiable at $x$, then $fg$ is
    differentiable at $x$.

    ::: {.proof}
    *Proof.* ◻
    :::

2.  (January 2006 \#2b) Assume that $f$ is differentiable at $a$.
    Evaluate
    $$\lim_{x\to a}\frac{a^nf(x)-x^nf(a)}{x-a},\quad n\in\mathbb{N}.$$

    ::: {.proof}
    *Proof.* ◻
    :::

3.  (June 2007 \#3a) Suppose that $f,g:\mathbb{R}\to\mathbb{R}$ are
    differentiable, that $f(x)\leq g(x)$ for all $x\in\mathbb{R}$, and
    that $f(x_0)=g(x_0)$ for some $x_0$. Prove that $f'(x_0)=g'(x_0)$.

    ::: {.proof}
    *Proof.* ◻
    :::

4.  (June 2008 \#3a) Prove that if $f'$ exists and is bounded on
    $(a,b]$, then $\lim_{x\to a^+}f(x)$ exists.

    ::: {.proof}
    *Proof.* ◻
    :::

5.  (January 2012 \#4b, extended) Let $f:\mathbb{R}\to\mathbb{R}$ be a
    differentiable function with $f'\in C(\mathbb{R})$. Assume that
    there are $a,b\in\mathbb{R}$ with $\lim_{x\to\infty}f(x)=a$ and
    $\lim_{x\to\infty}f'(x)=b$. Prove that $b=0$. Then, find a
    counterexample to show that the assumption $\lim_{x\to\infty}f'(x)$
    exists is necessary.

    ::: {.proof}
    *Proof.* ◻
    :::

6.  (June 2012 \#1a) Suppose that $f:\mathbb{R}\to\mathbb{R}$ satisfies
    $f(0)=0$. Prove that $f$ is differentiable at $x=0$ if and only if
    there is a function $g:\mathbb{R}\to\mathbb{R}$ which is continuous
    at $x=0$ and satisfies $f(x)=xg(x)$ for all $x\in\mathbb{R}$.

    ::: {.proof}
    *Proof.* ◻
    :::

# Integral Calculus

1.  (January 2006 \#4b) Suppose that $f$ is continuous and $f(x)\geq 0$
    on $[0,1]$. If $f(0)>0$, prove that $\int_0^1 f(x)dx>0$.

    ::: {.proof}
    *Proof.* ◻
    :::

2.  (June 2005 \#1b) Use the definition of the Riemann integral to prove
    that if $f$ is bounded on $[a,b]$ and is continuous everywhere
    except for finitely many points in $(a,b)$, then $f\in\mathscr{R}$
    on $[a,b]$.

    ::: {.proof}
    *Proof.* ◻
    :::

3.  (January 2010 \#5) Suppose that $f:[a,b]\to\mathbb{R}$ is
    continuous, $f\geq 0$ on $[a,b]$, and put
    $M=\sup\{f(x):x\in[a,b]\}$. Prove that
    $$\lim_{p\to\infty}\left(\int_a^b f(x)^p\,dx\right)^{1/p}=M.$$

    ::: {.proof}
    *Proof.* ◻
    :::

4.  (January 2009 \#4b) Let $f$ be a continuous real-valued function on
    $[0,1]$. Prove that there exists at least one point $\xi\in[0,1]$
    such that $\int_0^1 x^4 f(x)\,dx=\frac{1}{5}f(\xi)$.

    ::: {.proof}
    *Proof.* Assume that $f$ is a continuous real-valued function on
    $[0,1]$. Then, by the Intermediate Value Theorem we have that $f$
    attains its maximum and minimum on $[0,1]$. That is, for some
    $a,b\in[0,1]$,

    $$f(a)=\min\limits_{[0,1]}f(x) \qquad \text{and} \qquad  f(b)=\max\limits_{[0,1]}f(x).$$

    We now have $f(a)\leq f(x)\leq f(b)$ for all $x\in[0,1]$. This gives
    $$f(a)\int_0^1 x^4dx\leq \int_0^1 x^4f(x)dx\leq f(b)\int_0^1 x^4dx.$$

    By the Fundamental Theorem of Calculus we know that

    $$\int_0^1x^4dx=\frac{1}{5}.$$

    Thus, it follows that

    $$\frac{1}{5}f(a)\leq\int_0^1 x^4f(x)dx\leq \frac{1}{5}f(b)$$ giving

    $$f(a)\leq 5\int_0^1 x^4f(x)dx\leq f(b).$$

    By the Intermediate Value Theorem, there exists $\xi\in[0,1]$ such
    that

    $$f(\xi)=5\int_0^1 x^4f(x)dx.$$

    Therefore, we have that there exists $\xi\in[0,1]$ such that
    $\int_0^1 x^4 f(x)dx=\frac{1}{5}f(\xi)$. ◻
    :::

5.  (June 2009 \#5b) Let $\phi$ be a real-valued function defined on
    $[0,1]$ such that $\phi$, $\phi'$, and $\phi''$ are continuous on
    $[0,1]$. Prove that
    $$\int_0^1 \cos x \frac{x\phi'(x)-\phi(x)+\phi(0)}{x^2}\,dx<\frac{3}{2}||\phi''||_\infty,$$
    where $||\phi''||_\infty = \sup_{[0,1]}|\phi''(x)|.$ Note that $3/2$
    may not be the smallest possible constant.

    ::: {.proof}
    *Proof.* ◻
    :::

6.  (Essentialy June 2013 \#7) Prove
    Theorem [\[thm:d5-alpha\]](#thm:d5-alpha){reference-type="ref"
    reference="thm:d5-alpha"}.

    ::: {.proof}
    *Proof.* ◻
    :::

# Sequences and Series of Functions

1.  (June 2010 \#6a) Let $f:[0,1]\to\mathbb{R}$ be continuous with
    $f(0)\neq f(1)$ and define $f_n(x)=f(x^n)$. Prove that $f_n$ does
    not converge uniformly on $[0,1]$.

    ::: {.proof}
    *Proof.* ◻
    :::

2.  (January 2008 5a) Let $f_n(x) = \frac{x}{1+nx^2}$ for
    $n \in \mathbb{N}$. Let
    $\mathcal{F} := \{f_n \, \colon \, n = 1, 2, 3, \ldots\}$ and
    $[a,b]$ be any compact subset of $\mathbb{R}$. Is $\mathcal{F}$
    equicontinuous? Justify your answer.

    ::: {.proof}
    *Proof.* ◻
    :::

3.  (January 2005 \#4, June 2010 \#6b) If $f:[0,1]\to\mathbb{R}$ is
    continuous, prove that
    $$\displaystyle\lim_{n\to\infty}\int_0^1 f(x^n)\,dx=f(0).$$

    ::: {.proof}
    *Proof.* ◻
    :::

4.  (January 2020 4a) Let $M<\infty$ and $\mathcal{F} \subseteq C[a,b]$.
    Assume that each $f \in \mathcal{F}$ is differentiable on $(a,b)$
    and satisfies $|f(a)| \leq M$ and $|f'(x)| \leq M$ for all
    $x \in (a,b)$. Prove that $\mathcal{F}$ is equicontinuous on
    $[a,b]$.

    ::: {.proof}
    *Proof.* ◻
    :::

5.  (June 2005 \#5) Suppose that $f\in C([0,1])$ and that
    $\displaystyle \int_0^1 f(x)x^n\,dx=0$ for all
    $n=99,100,101,\ldots$. Show that $f\equiv 0$.\
    Note: Many variations on this problem exist. See June 2012 \#6b and
    others.

    ::: {.proof}
    *Proof.* ◻
    :::

6.  (January 2005 \#3b) Suppose $f_n:[0,1]\to\mathbb{R}$ are continuous
    functions converging uniformly to $f:[0,1]\to\mathbb{R}$. Either
    prove that
    $\displaystyle\lim_{n\to\infty}\int_{1/n}^1 f_n(x)\,dx=\int_0^1 f(x)\,dx$
    or give a counterexample.

    ::: {.proof}
    *Proof.* ◻
    :::

# Miscellaneous Topics

## Bounded Variation {#bounded-variation .unnumbered}

1.  (January 2018) Let $f \colon [a,b] \to \mathbb{R}$. Suppose
    $f \in \text{BV}[a,b]$. Prove $f$ is the difference of two
    increasing functions.

    ::: {.proof}
    *Proof.* ◻
    :::

2.  (January 2007, 6a) Let $f$ be a function of bounded variation on
    $[a,b]$. Furthermore, assume that for some $c>0$, $|f(x)| \geq c$ on
    $[a,b]$. Show that $g(x) = 1/f(x)$ is of bounded variation on
    $[a,b]$.

    ::: {.proof}
    *Proof.* ◻
    :::

3.  (January 2017, 2a) Define $f \colon [0,1] \to [-1,1]$ by
    $$f(x):= \begin{cases} x\sin\big({\frac{1}{x}}\big) & 0 < x \leq 1 \\ 0 & x = 0 \end{cases}$$
    Determine, with justification, whether $f$ is if bounded variation
    on the interval $[0,1]$.

    ::: {.proof}
    *Proof.* ◻
    :::

4.  (January 2020, 6a) Let $\{a_n\}_{n=1}^\infty \subseteq \mathbb{R}$
    and a strictly increasing sequence
    $\{x_n\}_{n=1}^\infty \subseteq (0,1)$ be given. Assume that
    $\sum_{n=1}^\infty a_n$ is absolutely convergent, and define
    $\alpha \colon [0,1] \to \mathbb{R}$ by
    $$\alpha(x):= \begin{cases} a_n &  x=x_n \\ 0 & \text{otherwise} \end{cases}.$$
    Prove or disprove: $\alpha$ has bounded variation on $[0,1]$.

    ::: {.proof}
    *Proof.* ◻
    :::

## Metric Spaces and Topology {#metric-spaces-and-topology-1 .unnumbered}

1.  Find an example of a metric space $X$ and a subset $E \subseteq X$
    such that $E$ is closed and bounded but not compact.

    ::: {.proof}
    *Proof.* ◻
    :::

2.  (May 2017 6) Let $(X,d)$ be a metric space. A function
    $f \colon X \to \mathbb{R}$ is said to be lower semi-continuous
    (l.s.c) if $f^{-1}(a,\infty)  = \{x \in X \, \colon \,  f(x)> a\}$
    is open in $X$ for every $a \in \mathbb{R}$. Analogously, $f$ is
    upper semi-continuous (u.s.c) if
    $f^{-1}(-\infty, b) = \{x \in X \, \colon \,  f(x)<b\}$ is open in
    $X$ for every $b \in \mathbb{R}$.

    ::: {.proof}
    *Proof.* ◻
    :::

    1.  Prove that a function $f \colon X \to \mathbb{R}$ is continuous
        if and only if $f$ is both l.s.c. and u.s.c.

        ::: {.proof}
        *Proof.* ◻
        :::

    2.  Prove that $f$ is lower semi-continuous if and only if
        $\liminf_{n \to \infty} f(x_n) \geq f(x)$ whenever
        $\{x_n\}_{n=1}^\infty \subseteq X$ such that $x_n \to x$ in $X$.

        ::: {.proof}
        *Proof.* ◻
        :::

3.  (January 2017 3) Let $(X,d)$ be a compact metric space. Suppose that
    $f_n \colon X \to [0,\infty)$ is a sequence of continuous functions
    with $f_n(x) \geq f_{n+1}(x)$ for all $n \in \mathbb{N}$ and
    $x \in X$, and such that $f_n \to 0$ pointwise on $X$. Prove that
    $\{f_n\}_{n=1}^\infty$ converges uniformly on $X$.

    ::: {.proof}
    *Proof.* ◻
    :::

## Integral Calculus {#integral-calculus-1 .unnumbered}

1.  (June 2014 1)Define $\alpha \colon [-1,1] \to \mathbb{R}$ by
    $$\alpha(x) := \begin{cases} -1 & x \in [-1,0] \\ 1 & x \in (0,1]. \end{cases}$$
    Let $f \colon [-1,1] \to \mathbb{R}$ be a function that is uniformly
    bounded on $[-1,1]$ and continuous at $x=0$, but not necessarily
    continuous for $x \neq 0$. Prove that $f$ is Riemann-Stieltjes
    integrable with respect to $\alpha$ over $[-1,1]$ and that
    $$\int_{-1}^1 f(x)d\alpha(x) = 2f(0).$$

    ::: {.proof}
    *Proof.* ◻
    :::

2.  (June 2017 2) Prove : $f \in \mathcal{R}(\alpha)$ on $[a,b]$ if and
    only if for any $a <c<b$, $f \in \mathcal{R}(\alpha)$ on $[a,c]$ and
    on $[c,b]$. In addition, if either condition holds, then we have
    that $$\int_a^c fd\alpha + \int_c^b fd\alpha = \int_a^b fd\alpha.$$

    ::: {.proof}
    *Proof.* ◻
    :::

3.  (Spring 2017 7) Prove that if $f \in \mathcal{R}$ on $[a,b]$ and
    $\alpha \in C^1[a,b]$, then the Riemann integral
    $\int_a^b f(x)\alpha'(x)dx$ exists and
    $$\int_a^b f(x) d\alpha(x)= \int_a^b f(x)\alpha'(x)dx.$$

    ::: {.proof}
    *Proof.* ◻
    :::

## Sequences and Series (and of Functions) {#sequences-and-series-and-of-functions .unnumbered}

1.  (January 2006 1) Let the power series series
    $\sum_{n=0}^\infty a_nx^n$ and $\sum_{n=0}^\infty b_nx^n$ have radii
    of convergence $R_1$ and $R_2$, respectively.

    ::: {.proof}
    *Proof.* ◻
    :::

    1.  If $R_1 \neq R_2$, prove that the radius of convergence, $R$, of
        the power series $\sum_{n=0}^\infty (a_n+b_n)x^n$ is
        $\min\{R_1, R_2\}$. What can be said about $R$ when $R_1 = R_2$?

        ::: {.proof}
        *Proof.* ◻
        :::

    2.  Prove that the radius of convergence, $R$, of
        $\sum_{n=0}^\infty a_nb_nx^n$ satisfies $R \geq R_1R_2$. Show by
        means of example that this inequality can be strict.

        ::: {.proof}
        *Proof.* ◻
        :::

2.  Show that the infinite series $\sum_{n=0}^\infty x^n2^{-nx}$
    converges uniformly on $[0,B]$ for any $B > 0$. Does this series
    converge uniformly on $[0,\infty)$?

    ::: {.proof}
    *Proof.* ◻
    :::

3.  (January 2006 4a) Let
    $$f_n(x) = \begin{cases} \frac{1}{n}  & x \in (\frac{1}{2^{n+1}}, \frac{1}{2^n}] \\ 0 & \text{ otherwise}.\end{cases}$$

    ::: {.proof}
    *Proof.* ◻
    :::

    Show that $\sum_{n=1}^\infty f_n$ does not satisfy the Weierstrass
    M-test but that it nevertheless converges uniformly on $\mathbb{R}$.

    ::: {.proof}
    *Proof.* ◻
    :::

4.  Let $f_n \colon [0,1) \to \mathbb{R}$ be the function defined by
    $$f_n(x):= \sum_{k=1}^n \frac{x^k}{1+x^k}.$$

    ::: {.proof}
    *Proof.* ◻
    :::

    1.  Prove that $f_n$ converges to a function
        $f \colon [0,1) \to \mathbb{R}$.

        ::: {.proof}
        *Proof.* ◻
        :::

    2.  Prove that for every $0 < a < 1$ the convergence is uniform on
        $[0,a]$.

        ::: {.proof}
        *Proof.* ◻
        :::

    3.  Prove that $f$ is differentiable on $(0,1)$.

        ::: {.proof}
        *Proof.* ◻
        :::

## January 2019 Qualifying Exam {#january-2019-qualifying-exam .unnumbered}

1.  Suppose that $f: [0,1] \to \mathbb{R}$ is differentiable and
    $f(0) = 0$. Assume that there is a $k > 0$ such that
    $$|f'(x)| \leq k|f(x)|$$ for all $x\in [0,1]$. Prove that $f(x) = 0$
    for all $x\in [0,1]$.

    ::: {.proof}
    *Proof.* Let $0<\delta_1<1$, and fix $x_1 \in (0, \delta_1]$. Since
    $f(x)$ is differentiable on all of $[0,1]$, $f(x)$ is differentiable
    on all of $(0, \delta_1)$. So by the Mean Value Theorem, there
    exists $x_2 \in (0, x_1)$ such that
    $$f'(x_2) = \frac{f(x_1) - f(0)}{x_1-0} = \frac{f(x_1)}{x_1} .$$
    Solving for $f(x_1)$, we get $f(x_1) = f'(x_2)x_1$. So by
    hypothesis, $f(x_1) = f'(x_2) x_1 \leq k|f(x_2)|x_1$. Assume for
    $x_1, x_2, \ldots, x_{n-1} \in (0,1)$ the following conditions are
    satisfied for $j\in\{1,2,\ldots, n-1\}$. $$\begin{aligned}
        x_j &\in& (0,x_{j-1}) \\
        f(x_{j-1}) &=& f'(x_j)x_{j-1} \\
        f(x_1) &\leq& k^{j-1}|f(x_j)|(x_{j-1} \cdots x_2x_1)
        \end{aligned}$$ I now claim that this inductive process is true
    for $j=n$, given that it holds for all $j \leq n$. We apply the Mean
    Value Theorem to find some $x_n \in (0, x_{n-1})$ such that
    $f'(x_n) = \frac{f(x_{n-1})}{x_{n-1}}$, then write
    $f(x_{n-1}) = f'(x_n)x_{n-1}.$ By our inductive hypothesis, we have
    $$\begin{aligned}
        |f(x_1)| &\leq& k^{n-2}|f(x_{n-1})|(x_{n-2}\cdots x_2x_1) \\
        &=& k^{n-2}|f'(x_n)x_{n-1}|(x_{n-2}\cdots x_2x_1)  \\
        &\leq& k^{n-2}(k|f(x_n)|)(x_{n-1}x_{n-2}\cdots x_2x_1) \\
        &=& k^{n-1}|f(x_n)|(x_{n-1}x_{n-2}\cdots x_2x_1).
        \end{aligned}$$

    Thus our claim holds by induction. Now, since $f$ is a continuous
    function on the closed interval, we can apply the Extreme Value
    Theorem to find some $M>0$ for which $f(x) \leq M$ for all
    $x\in [0,1]$. Thus we get $$|f(x_1)| \leq k^n M (x_n \cdots x_1)
        =(kx_n)(kx_{n-1})\cdots(kx_1)M$$ for all $n \in \mathbb{N}$. If
    $k < \frac{1}{x_1}$, then for any $\epsilon > 0$ we can find
    $N\in \mathbb{N}$ sufficiently large so that $|f(x_1)| < \epsilon$.
    Otherwise, we set $\delta_1< \frac{1}{k}$ so that $kx_1< 1$. ◻
    :::

