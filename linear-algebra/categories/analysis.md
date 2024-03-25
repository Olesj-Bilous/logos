# Real analysis

##### Upper and lower bounds

A nonempty subset $R\subseteq\mathbb R$ with $a,b\in\mathbb R$ has:

- a lower bound if $a \leq r$
- an upper bound if $r \leq b$

for all $r\in R$.

Consider the set of bounds at each side $A,B\subseteq\mathbb R$ such that $a\in A$ and $b\in B$ for all lower bounds $a$ and upper bounds $b$ of $R$.

### Completeness axiom
##### Infimum and supremum

A nonempty set of bounds at one side of a nonempty subset includes its own bound at the other side:

- an infimum $inf (R) \in A$ such that $a \leq inf (R)$ for all $a\in A$
- a supremum $sup(R) \in B$ such that $sup(R) \leq b$ for all $b\in B$.

Note that $A \cup R \cup \{sup(R)\}$ is the set of lower bounds of $B$, where $sup(R) = inf(B)$.
___
Consider a map $u: \mathbb N \longrightarrow \mathbb R$.
This is called a row with element $u_i=u(i)$.

##### Row limit

If there is an $n\in\mathbb N$ for every real $\epsilon > 0$ such that $|u_i - L| \leq \epsilon$ for all $i > n$ then $L \in \mathbb R$ is the limit of $u$. We write

$$
    \lim_{i\to\infty} u_i = L.
$$

with $L = \lim u$ a shorthand.

#### Growth limit theorem

If for all $j > i$ a row $u$:

- increases $u_i \leq u_{j}$ then $\lim u = sup(u(\mathbb N))$
- decreases $u_i \geq u_j$ then $\lim u = inf(u(\mathbb N))$.

After all, there are $n$ for any $\epsilon > 0$ such that $sup(u(\mathbb N)) - \epsilon \lt u_n$.
___
A point $c \in R$ is considered a limit point of $R \subseteq \mathbb R$ if for every real $\delta \gt 0$ there is an $x \in R$ such that $0 \lt |x-c| \lt \delta$.

Consider a function $f:\mathbb R \longrightarrow\mathbb R$.

##### Limit at a real point

If there is a real $\delta \gt 0$ such that $|x-|$

___
Given $f$ differentiable over $I = [a,b]$.

#### Rolle's theorem

If $f(a) = f(b)$ there is a $\xi\in I$ for which $f'(\xi)=0$.

Since $f$ is continuous over $I$ its values are bounded and closed there. Moreover equality at the boundaries implies a local extremum.

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
We can take each term as a function of the workpoint $u_i(t) = T_i^t(x,t)$ and differentiate.

$$
    u_{i}'(t) = -\frac i {x-t}u_i(t) + \frac {i+1}{x-t}u_{i+1}(t)
$$

Thus $p(t) = P_n^t(x)$ differentiates to

$$
    p'(t) = \frac{n+1}{x-t}u_{n+1}(t)
$$

Hence the remainder in function of the workpoint $r(t) = f(x) - p(t)$ differentiates to $r'(t)=-p'(t)$. Define

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
