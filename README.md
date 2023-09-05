For years I didn't understand the reasons behind the definition of matrix multiplication. It seemed awkward and arbitrary.

Now I can see that it is simple and purposeful, and I believe I can share this insight with you shortly.

# The basis

Whenever we evaluate a *column* vector, we must always consider the *basis* in respect to which it *represents* a vector.

We must also understand that a column vector is *not* an actual vector, in the strict sense! It is only the ordered set of *coordinates* of a vector with respect to a *specified* basis.

A vector does *not* have any inherent coordinates. Depending on choice of basis, it will have different coordinates, yet it may also become an entity in respect to which a coordinate is defined.

A vector does not change upon changing basis, only its coordinates do.

A vector is a geometric entity on the basis of which other vectors may be defined.

A column vector is merely one such definition, which has no inherent meaning unless it is known which vectors form its basis.

# Coordinate transformations

## Vector coordinate transformations

Generally speaking, it is tacitly assumed that any column vector refers to a well-known unit basis, unless otherwise specified. That's why we see expressions of the kind:

```math
Av = v'
```

which are taken to mean:

```math
{\mathbf a}_{{\mathbf e}}v_{{\mathbf e}} = v'_{{\mathbf e}}
```

where ${\mathbf e}$ is taken to be the unit basis, and $A$ is rewritten as an ordered set of vectors ${\mathbf a} = (a\_i)\_i$ represented with respect to ${\mathbf e}$: $A = {\mathbf a}\_{\mathbf e} = ( A^{*i} = a_{i, \mathbf e} )\_i$, where $A^{*i}$ is the $i^{th}$ column vector of $A$.

We denote by $v_{\mathbf s}$ the column vector consisting of the coordinates of vector $v$ with respect to any basis ${\mathbf s}$.

However, the meaning of the product formula above is not immediately evident. We transform a vector with respect to an invariant basis, yet how are we to motivate or interpret the structure of this operation?

An expression more closely related to the prior discussion would be the following:

```math
{\mathbf a}_{\mathbf e}v_{{\mathbf a}} = v_{{\mathbf e}}
```

Here we can really appreciate the definition of matrix multiplication.

We can interpret ${\mathbf a}_{\mathbf e}$ as the column vectors *of* an alternative basis ${\mathbf a}$, *with respect to* the unit basis ${\mathbf e}$.

In other words, ${\mathbf a}_{\mathbf e}$ is the way the vectors of the alternative basis look to us, from our unit basis.

From the perspective of that alternative basis, however, their basis vectors look to them the way the unit basis looks to us from our perspective (${\mathbf a}\_{\mathbf a} = {\mathbf e}\_{\mathbf e}$, as we shall show later, where ${\mathbf e}_{\mathbf e} = I$ is the identity matrix).

$v_{\mathbf a}$ is the way $v$ looks from the perspective of basis ${\mathbf a}$, whereas $v_{\mathbf e}$ is the way it looks to us. 

We could also have written our expression as follows:

```math
v_{\mathbf e} = \sum_i^n{v_{{\mathbf a}, i}{\mathbf a}_{{\mathbf e}, i}}
```

In effect, we are summing over the vectors representing ${\mathbf a}$ with respect to ${\mathbf e}$, each scaled by the corresponding component of $v_{\mathbf a}$.

We derive the way $v$ looks to us, from the way the vectors of the basis $\mathbf a$ look to us, and the way $v$ looks from the basis $\mathbf a$.

This approach allows us to re-interpret the initial product formula in a more intuitive manner:

```math
{\mathbf a}_{\mathbf e}v_{\mathbf e} = v'_{\mathbf e}
```

We transform $v$ by substituting the unit basis for basis ${\mathbf a}$ when evaluating $v_{\mathbf e}$.

We can also easily obtain the following, adopting an enhanced notation where $v_M$ is taken to be $v_{f(M)}$, and $M\_N$ to be ${f(M)}\_{f(N)}$, with $f(M) = {\mathbf m}$ such that $M = {\mathbf m}_{\mathbf e}$ for any $M$, $N$, ommitting $I$ subscripts for brevity:

```math
A v_A = v
```
```math
v_A = A^{-1}v
```

A consequence proves the aforementioned.

```math
A_A^{*i} = A^{-1}A^{*i}
```
```math
A_A = I
```

## Matrix transformations

We can take our scheme a step further:

```math
v_B = B^{-1}v = B^{-1}A v_A
```

This allows us to transform vectors between arbitrary bases given their representations with respect to the unit base.

Taking advantage of the new notation, we can also refine our notion of the matrix product as a transformation.

```math
Av = v_{A^{-1}}
```
```math
BAv = Bv_{A^{-1}} = v_{A^{-1}B^{-1}}
```

Further abstracting, we may consider $A$ as the transformation from $\mathbf e$ to $\mathbf a$. On the other hand, $B$ transforms $A$ to a transformation from $\mathbf e$ to $\mathbf p$ where $BA = \mathbf p_e$
