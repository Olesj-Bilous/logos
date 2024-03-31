# Real analysis

###### Upper and lower bounds

A nonempty subset $R\subseteq\mathbb R$ with $a,b\in\mathbb R$ has:

- a lower bound $a \in R^\geq$ if $r \geq a$
- an upper bound $b \in R^\leq$ if $r \leq b$

for all $r\in R$.
The subset is considered bounded if bounds exist on both sides.

### Completeness axiom
##### Infimum and supremum

A nonempty set of bounds at one side of a nonempty subset includes its own bound at the opposite side:

- an infimum $\inf_R \in R^\geq$ such that $a \leq \inf_R$ for all $a\in R^\geq$
- a supremum $\sup_R \in R^\leq$ such that $b \geq \sup_R$ for all $b\in R^\leq$.

Note that $R^\leq \cup R \cup \{\ \sup_R\ \}$ is the set of lower bounds of $R^\geq$, where $\sup_R = \inf_{R^\geq}$.
___
Consider a map $u: \mathbb N \longrightarrow \mathbb R$.
This is called a row with element $u_i=u(i)$.

All elements of a row beyond an appropriate index $n\in\mathbb N$ may be found within an arbitrarily small bound of proximity $\epsilon \in \mathbb R$ to a limiting value $L \in \mathbb R$.

##### Row limit

If there is an $n$ for every $\epsilon > 0$ such that $|u_i - L| \lt \epsilon$ for all $i > n$ then $L$ is the limit of $u$. We write

$$
    \lim_{i\to\infty} u_i = L.
$$

with $L = \lim u$ a shorthand.
A row is said to converge to its limit. If no such limit exists the row is divergent.

#### Monotonic limit theorem
###### Increasing and decreasing rows

If for all $j > i$:

- $u_j \geq u_i$ then $u$ is increasing and $\lim u = \sup_{u(\mathbb N)}$
- $u_i \geq u_j$ then $u$ is decreasing and $\lim u = \inf_{u(\mathbb N)}$.

After all, there are $n$ for any $\epsilon > 0$ such that ${\sup_{u(\mathbb N)}} - \epsilon \lt u_n$.

###### Limes inferior et superior

Consider the row $u^{\sup}$ where $u_i^{\sup} = \sup_{U_i}$ for $U_i = \{\ u_j \in u\ |\ j \geq i \ \}$. Then 

$$
    \limsup u = \lim u^{\sup}.\\
    \liminf u = \lim u^{\inf}
$$

is defined analogously.
Evidently $u$ converges if $\limsup u = \liminf u$.

A partial row is obtained by omitting elements from a row without affecting its ordering or cardinality.

#### Bolzano Weierstrass theorem

Every bounded row has a convergent partial row.

For any $i$ consider $S_i = \{\ j \ |\ u_j \lt u_i \}$ and $L_i = \{\ j \ |\ u_j \geq u_i \}$. Then define $N_i = S_i$ if $|S_i| \notin \mathbb N$ and $N_i = L_i$ otherwise. Take $M_n = \bigcap_{j\leq n} N_j$.
If either $|S_i|, |S_j| \in \mathbb N$ or $|S_i|, |S_j| \notin \mathbb N$ then $N_i \cap N_j \in \{\ N_i, N_j \ \} $. Should $|S_i| \in \mathbb N$ whereas $|S_j| \notin \mathbb N$ then $S_i \subset S_j$ so $L_i \cap S_j = S_j \setminus S_i$ and $|N_i \cap N_j| \notin \mathbb N$.
Hence $M_n \notin \mathbb N$ for all $n$. 
We may now consider $S = \{\ i \in M \ \big|\ |S_i| \notin \mathbb N \ \}$ and $L = \{\ i \in M \ \big|\ |S_i| \in \mathbb N \ \}$ where $M = \{\ i > 0 \ |\ i \in M_{i-1}\ \}$. Evidently $u(S), u(L)$ are monotonic and bounded. If $|S| \in \mathbb N$ then $|L| \notin \mathbb N$ since $|S \cup L| = |M| \notin \mathbb N$.
___
###### Limit point

A point $c \in D$ is considered a limit point of $D \subseteq \mathbb R$ if for every real $\delta$ there is an $x \in R$ such that $0 \lt |x-c| \lt \delta$.

Consider a function $f:D \longrightarrow R$ where $D,R\subseteq\mathbb R$ and $c$ is a limit point of $D$.

##### Limit at a real point

If there is a real $\delta \gt 0$ for every real $\epsilon \gt 0$ such that $|f(x)-L| \lt \epsilon$ whenever $|c-x| \lt \delta$ then $L\in\mathbb R$ is the limit of $f$ at $c$.

$$
    \lim_{x\to c} f(x)=L
$$

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
