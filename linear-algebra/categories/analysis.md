# Analysis

Given $f$ continuously differentiable over $I = [a,b]$.

#### Rolle's theorem

If $f(a) = f(b)$ there is an $x\in I$ for which $f'(x)=0$.

The values of $f$ are bounded and closed over $I$. Moreover $f$ is either constant or locally extreme there.

#### Mean value theorem

 There is an $x\in I$ such that $$
    \frac {f(b)-f(a)}{b-a} = f'(x).
$$ In the light of the fundamental theorem this can also be expressed as $$
    \int_a^b f'(t)dt = f'(x)(b-a).
$$ Consider $$g(x)=f(x)-f(a) - \frac {x-a}{b-a}(f(b)-f(a)).$$ Then $g(a) = g(b) = 0 = g'(x)$ for some $x$.
___
We traverse $f^{(i<n)}$ for $f \in C^n$ over $[c,x]$ along parameter $t\in[0,1]$ and differentiate. $$
\begin{aligned}
    g_i(t) &= f^{(i)}(c + (x - c)t) \\
    g'_i(t) &= (x - c)g_{i+1}(t)
\end{aligned}
$$ By the mean value theorem there is a $\mu_{i}(t)$ such that $$
    g_{i}(t) = g_{i}(0) + t(x - c)\mu_{i}(t)
$$ where $\mu_{i}(t) = g_{i+1}(z)$ for some $z\in[0,t]$. Starting from $$f(x) = f(c) + (x - c)\mu_0(1)$$ this provides grounds or bounds for approximation considering
$$
\begin{aligned}
    t\mu_{i}(t)
        &= \int_0^t g_{i+1}(s)ds\\ 
        &= f^{(i+1)}(c)t + (x-c)\int_0^tt\mu_{i+1}(t).
\end{aligned}
$$

##### Taylor polynomial

$$
    P_n(x) = \sum_{i=0}^{n} \frac{1}{i!}(x - c)^if^{(i)}(c)
$$

##### Lagrange remainder

$$
    R_n(x) = \frac{1}{(n+1)!}(x - c)^{n+1}f^{(n+1)}(\xi)
$$

Where $\mu_{i}(t) = g_{i+1}(z)$ set $\xi=c+(x-c)z$ to conclude

#### Taylor's theorem

$$f=P_n+R_n.$$

___
