Given $f$ differentiable over $I = [a,b]$.

#### Rolle's theorem

If $f(a) = f(b)$ there is a $\xi\in I$ for which $f'(\xi)=0$.

The values of $f$ are bounded and closed over $I$. Moreover $f$ is locally extreme there.

#### Mean value theorem

There is a $\xi\in I$ such that
$$ f'(\xi) = \frac{f(b)-f(a)}{b-a}. $$
In the light of the fundamental theorem this can also be expressed as
$$ \int_a^bf'(t)dt = (b-a)f'(\xi). $$
Consider
$$ g(x) = f(x)-f(a) - \frac{x-a}{b-a}(f(b)-f(a)). $$
Then $g(a) = g(b) = 0 = g'(\xi)$ for some $\xi\in I$.
___
Consider $f$ differentiable $m+1$ times over $I = [c,x]$.

###### Taylor term

$$ T_{i\leq m+1}^c(x) = \frac 1 {i!} (x-c)^i f^{(i)}(c) $$

##### Taylor polynomial

$$ P_{n\leq m}^c(x) = \sum_{i=0}^n T_i^c(x) $$

where $c$ is the workpoint and $n$ the degree of expansion.
We can take this polynomial as a function of the workpoint.

$$ 
u_i(t) = T_i^t(x) \\
u_{i>0}'(t) = -\frac i {x-t}u_i(t) + \frac {i+1}{x-t}u_{i+1}(t) \\
p(t) = P_n^t(x) \\
p'(t) = \frac{n+1}{x-t}T_{n+1}^t(x) $$

Hence the remainder in function of the workpoint $r(t) = f(x) - p(t)$ differentiates to $r'(t)=-p'(t)$.

$$ d(t) = r(t) - \left(\frac{x-t}{x-c}\right)^{n+1}r(c) $$

Clearly $d(x)=d(c)=0=d'(\xi)$ for some $\xi\in I$. Hence

$$ r(c) = -\frac 1{n+1}\frac{(x-c)^{n+1}}{(x-t)^n}r'(\xi) $$

##### Lagrange remainder

$$
    R_n^c(x) = T_{n+1}^\xi(x)
$$

#### Taylor's theorem

$$f(x)=P_n^c(x)+R_n^c(x).$$

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
