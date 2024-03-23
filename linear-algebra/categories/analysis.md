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

$$ T_{i\leq m+1}^c(x,z) = \frac 1 {i!} (x-c)^i f^{(i)}(z) $$

##### Taylor polynomial

$$ P_{n\leq m}^c(x) = \sum_{i=0}^n T_i^c(x,c) $$

where $c$ is the workpoint and $n$ the degree of expansion.
We can take each term as a function of the workpoint and differentiate.

$$ 
u_i(t) = T_i^t(x,t) \\
u_{i>0}'(t) = -\frac i {x-t}u_i(t) + \frac {i+1}{x-t}u_{i+1}(t) $$
Thus the following holds for the polynomial.
$$
p(t) = P_n^t(x) \\
p'(t) = \frac{n+1}{x-t}u_{n+1}(t) $$

Hence the remainder in function of the workpoint $r(t) = f(x) - p(t)$ differentiates to $r'(t)=-p'(t)$.

$$ d(t) = r(t) - \left(\frac{x-t}{x-c}\right)^{n+1}r(c) $$

Clearly $d(x)=d(c)=0=d'(\xi)$ for some $\xi\in I$. Hence

$$ r(c) = -\frac 1{n+1}\frac{(x-c)^{n+1}}{(x-\xi)^n}r'(\xi) $$

##### Lagrange remainder

$$
    R_n^c(x) = T_{n+1}^c(x,\xi)
$$

#### Taylor's theorem

$$f(x)=P_n^c(x)+R_n^c(x).$$

___
This may easily be extended for $f$ partially differentiable $m+1$ times over $I = [c,x]$ where $x - c = \mathbf v \in\mathbb R^n$ by considering $s(\lambda) = c + \lambda\mathbf v$ for $\lambda \in [0,1]$.

$$g(\lambda) = f(s(\lambda))$$

$$g'(\lambda) = \nabla f(s(\lambda)) \cdot \mathbf v$$

$$ = \sum_{i=1}^n v^i\frac{\partial f(s(\lambda))}{\partial s^i}$$

We introduce $\alpha \in \mathbb N^n$ and denote $|\alpha| = \sum_{i=1}^n \alpha_i$.

###### Multivariate Taylor term

$$ T_\alpha^c(x, \lambda) = \left( \prod_{i=1}^n \frac 1 {{\alpha_i}!} \left( v^i \frac {\partial}{\partial s^i} \right)^{\alpha_i} \right)f(s(\lambda))$$

for $|\alpha|\leq m+1$.


##### Multivariate Taylor polynomial

$$ P_{k\leq m}^c(x) = \sum_{|\alpha|\leq k} T_\alpha^c(x, 0) $$

Evidently $u_\alpha(\lambda) = T_\alpha^{s(\lambda)}(x, \lambda) = (1-\lambda)^{|\alpha|}T_\alpha^c(x, \lambda)$ since $x - s(\lambda) = (1 - \lambda)\mathbf v$.
This differentiates to $$
    u'_\alpha(\lambda) = \sum_{i=1}^n \frac {-|\alpha|} {1-\lambda}u_\alpha(\lambda) + \frac {\alpha_i+1} {1-\lambda}u_{\partial_i\alpha}(\lambda)
$$ where $(\partial_i \alpha)_{j\neq i} = \alpha_i$ and $(\partial_i \alpha)_i = \alpha_i+1.$
Hence $p(\lambda) = \sum_{|\alpha|\leq k} u_\alpha(\lambda)$ differentiates to $$
    p'(\lambda) = \sum_{|\alpha| = k + 1} \frac {k+1} {1-\lambda}u_{\alpha}(\lambda)
$$

Taking $r(\lambda)=f(x)-p(\lambda)$ we define 
$$d(\lambda) = r(\lambda) - (1-\lambda)^{k+1}r(0)$$

##### Multivariate Lagrange remainder

$$
    R_k^c(x) = \sum_{|\alpha| = k + 1} T_\alpha^c(x,\xi)
$$ for some $\xi\in [0,1]$.
___
