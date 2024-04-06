# Real analysis

### Field axioms

The real numbers $\mathbb R$ are a field over addition $+$ and multiplication $\times$ with $0$ or $1$ as identity elements respectively.

____
##### Total order

We introduce the total order relation $a \leq b$.

Define the strict total order $a < b$ as $a \leq b$ and $b \nleq a$.
Evidently the strict order is irreflexive $a \not\lt a$ and asymmetric: $a \not\lt b$ or $b \not\lt a$.

###### Totality
- $a \leq b$ or $b \leq a$

This is also known as strong connection. The total order is clearly reflexive $a \leq a$. Moreover $b \nleq a$ is sufficient for $a \lt b$.

###### Antisymmetry
- $a = b$ if $a \leq b$ and $b \leq a$

Hence $a \lt b$ or $b \lt a$ if $a \neq b$. This is known as connection.

###### Transitivity

- $a \leq c$ if $a \leq b$ and $b \leq c$

### Order axioms

The order over the real numbers is total. For any $a,b\in\mathbb R$ the following also holds.

###### Invariance under field operations

- $a+c\leq b+c$ if $a\leq b$

This implies that $-a \lt 0$ only if $0 \lt a$.

- $0\leq ab$ if $0\leq a$ and $0\leq b$

Consider first $(a-a)b = ab + (-a)b$ and $(a-a)(b-b) = -ab + (-a)(-b)$.
For $a,b \neq 0$ we see that $ab \lt 0$ only if $a \lt 0$ only if $0 \leq b$.

____
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

Note that $R^\geq \cup R \cup \{\ \sup_R\ \}$ is the set of lower bounds of $R^\leq$, where $\sup_R = \inf_{R^\leq}$.

We denote the ill definition of the infimum or supremum of a nonempty set with no lower or upper bounds as $\inf_R = -\infty$ and $\sup_R = \infty$ respectively. These are certainly not real numbers but devices to simplify notation.

###### Open interval

Given an endpoint $c \in \mathbb R$ the open intervals $\left]-\infty,c\right[$ and $\left]c,\infty\right[$ consist of all $x \in \mathbb R$ such that $x \lt c$ or $c \lt x$ respectively.
Note that $c$ is respectively the supremum or infimum of the interval and is excluded by definition.
The open interval $\left]a, b\right[ = \left]a,\infty\right[ \cap \left]-\infty,b\right[$ for $a \lt b$.

###### $\delta$-neighborhood of a point

Given $\delta\in \mathbb R$ where $0 \lt \delta $ the $\delta$-neighborhood $D_\delta(c)$ of $c\in \mathbb R$ consists of all $x \in \mathbb R$ such that $|x-c|<\delta$.

Clearly $D_\delta(c) = \left]c-\delta,c+\delta\right[$.
___
Consider a map $u: \mathbb N \longrightarrow \mathbb R$.
This is called a row with element $u_i=u(i)$ at index $i$.
We may consider all elements of the row beyond a certain index $U_i = \{\ u_j \in u\ |\ j \geq i \ \}$.

##### Row limit

If there is an $n$ for every $\delta \gt 0$ such that $U_n \subseteq D_\delta(L)$ then $L \in \mathbb R$ is the limit of $u$.

Note that for every $0 \lt \delta_1$ there is a $0 \lt \delta_2 \lt \delta_1$ such that $D_{\delta_2}(L) \subset D_{\delta_1}(L)$. Therefore if $U_j \subseteq D_{\delta_2}(L)$ and $U_i \subseteq D_{\delta_1}(L)$ then $j \geq i$.

We write

$$
    \lim_{i\to\infty} u_i = L
$$

with $L = \lim u$ a shorthand.
A row is said to converge to its limit. If no such limit exists the row is divergent. In special cases this may be denoted $\lim u \in \{\ -\infty, \infty\ \}$ to indicate that the row diverges because it grows without bound.

#### Monotonic limit theorem
###### Increasing and decreasing rows

If for all $j > i$:

- $u_j \geq u_i$ then $u$ is increasing and $\lim u = \sup_{u(\mathbb N)}$
- $u_j \leq u_i$ then $u$ is decreasing and $\lim u = \inf_{u(\mathbb N)}$.

After all, there are $n$ for any $\delta > 0$ such that ${\sup_{u(\mathbb N)}} - \delta \lt u_n$ as long as $\sup_{u(\mathbb N)} \in \mathbb R$.

###### Limes inferior et superior

Consider the row $u^{\sup}$ where $u_i^{\sup} = \sup_{U_i}$. Then 

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

A point $c \in D$ is considered a limit point of $D \subseteq \mathbb R$ if for every $\delta \gt 0$ there is an $x \neq c$ such that $x \in D_\delta(c) \cap D$.

Clearly this is equivalent to the existence of a row $u: \mathbb N \longrightarrow D \setminus \{c\}$ that converges to $c$.

###### Closure

The closure $\partial D$ of a set $D \subseteq \mathbb R$ extends it with its limit points.

###### Closed interval

The closure of an interval $\partial \left]a,b\right[ = [a,b]$ extends it with its endpoints.
Evidently an ill defined infimum or supremum may not be included, e.g. $\partial \left] a,\infty \right[ = [ a,\infty [$.
We may take advantage of this notation to include a single endpoint of an open interval even if both exist, e.g. $[a,b[$.

Consider a map $f:D \longrightarrow R$ where $D,R\subseteq\mathbb R$ and $c$ is a limit point of $D$.

##### Limit at a real point

If there is a $\delta \gt 0$ for every $\epsilon \gt 0$ such that $f(x) \in D_\epsilon(L) \cap R$ for all $x \in D_\delta(c) \cap D$ where $x \neq c$ then $L\in\mathbb R$ is the limit of $f$ at $c$.

$$
    \lim_{x\to c} f(x)=L
$$

Clearly this condition is met only if $f \circ u$ converges to $L$ for all rows $u: \mathbb N \longrightarrow D \setminus \{c\}$ that converge to $c$.

##### Continuity

A function $f$ is continuous at a limit point $c$ of its domain if

$$
    \lim_{x\to c} f(x)=f(c).
$$

A function that is continuous at every point of an interval is said to be continuous over that interval.

#### Weierstrass theorem

A function continuous over a bounded and closed interval is bounded and closed over that interval.

Suppose it is not bounded or not closed over that interval. Then there should be a row of points in the interval for which the function grows monotonically without bound, or without attaining its limit. However, any such row has a partial row that converges to some point in the interval, for which the function must attain a defined limit in order to be continuous.
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
