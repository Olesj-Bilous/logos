Given $f$ differentiable over $I = [a,b]$.

#### Rolle's theorem

If $f(a) = f(b)$ there is an $x\in I$ for which $f'(x)=0$.

The values of $f$ are bounded and closed over $I$. Moreover $f$ is locally extreme there.

#### Mean value theorem

There is an $x\in I$ such that
$$ f'(x) = \frac{f(b)-f(a)}{b-a}. $$
In the light of the fundamental theorem this can also be expressed as
$$ \int_a^bf'(t)dt = (b-a)f'(x). $$
Consider
$$ g(x) = f(x)-f(a) - \frac{x-a}{b-a}(f(b)-f(a)). $$
Then $g(a) = g(b) = 0 = g'(\xi)$ for some $\xi$.
___
We traverse $f^{(i\leq n)}$ for $f$ differentiable $n+1$ times over $[c,x]$ along parameter $t\in[0,1]$ and differentiate.
$$g_i(t) = f^{(i)}(c + (x - c)t)$$
$$g_i'(t) = (x - c)g_{i+1}(t)$$ 

By the mean value theorem there is a $z_i\in[0,t]$ such that
$$g_{i}(t) = g_{i}(0) + tg_i'(z_i) $$
Starting from $$f(x) = f(c) + (x - c)g_1(z_0)$$ this provides either bounds for an approximation of $f$ or grounds considering
$$tg_{i+1}(z_i)
        = \int_0^t g_{i+1}(s)ds$$
       $$= f^{(i+1)}(c)t + (x-c)\int_0^tsg_{i+2}(z_{i+1})ds.
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
This may easily be extended for $f$ partially differentiable $m$ times over $I = [c,x]$ where $c - x = \mathbf v \in\mathbb R^n$ by considering $u(t) = c + t\mathbf v$ for $t \in [0,1]$.

$$g(t) = f(u(t))$$

$$g'(t) = \nabla f(u(t)) \cdot \mathbf v$$

$$ = \sum_{i=1}^n v_i\frac{\partial f(u(t))}{\partial u_i}$$

Evidently $g(t)=g(0)+tg'(z)$ for some $z$, hence $tg'(z) = \int_0^tg'(s)ds$.
Considering $N=\{i\leq n\}$ and $\mathbf i \in N^{k<m}$ we see
$$
    g_{\mathbf i}(t) = \frac{\partial^k f(u(t))}{\prod_{h=1}^k\partial u_{\mathbf i_h}}
$$
$$
    g_{\mathbf i}'(t) = \mathbf g_{\partial\mathbf i}(t) \cdot \mathbf v
$$
noting $\mathbf g_{\partial\mathbf i}^j = g_\mathbf j(t)$ where $\mathbf j\in\partial\mathbf i = \mathbf i \times N$ such that $\mathbf j_{k+1} = j$.
Hence there is some $z_\mathbf i$ such that
$$g_{\mathbf i}(t) = g_{\mathbf i}(0) + t\mathbf g_{\partial\mathbf i}(z_\mathbf i) \cdot \mathbf v$$
$$t\mathbf g^j_{\partial\mathbf i}(z^j_\mathbf i) = \int_0^t\mathbf g^j_{\partial\mathbf i}(s)ds$$
$$=g_{\mathbf j}(0)t+\int_0^ts\mathbf g_{\partial\mathbf j}(z_\mathbf j) \cdot \mathbf vds$$
___
