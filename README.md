For years I didn't understand the reasons behind the definition of matrix multiplication. It seemed awkward and arbitrary.

Now I can see that it is simple and purposeful, and I believe I can share this insight with you shortly.

# The basis

Whenever you are evaluating a *column* vector, you must always consider the *basis* in regard to which it is defined.

We must also understand that a column vector is *not* an actual vector, in the strict sense! It is only the ordered set of *coordinates* of a vector with regard to a *specified* basis.

A vector does *not* have any inherent coordinates. Depending on coordinate system, it will have different coordinates, yet it may also be the entity in regard to which coordinates are defined.

A vector does not change upon changing coordinate system, only its coordinates do.

A vector is a static geometric entity in terms of which other vectors may be described.

A column vector is merely the description of a single vector on the basis of multiple other vectors, which has no inherent meaning unless it is known which vectors form the basis of that description.

# Coordinate transformations

## vector transformations

Generally speaking, it is assumed that any column vector refers to a well-known but unspecified unit basis, unless otherwise specified. That's why we see expressions of the kind:

```math
Av = v'
```

which are taken to mean:

```math
A_{{\mathbf e}}v_{{\mathbf e}} = v'_{{\mathbf e}}
```

where ${\mathbf e}$ is taken to be the unit *basis*.

However, the meaning of the formula above is not immediately evident. We are transforming a vector defined with regard to the unit basis into another vector within the same basis, yet how are we to motivate or interpret this?

An expression more closely related to the prior discussion would be the following:

```math
A_{{\mathbf e}}v_{{\mathbf a}} = v_{{\mathbf e}}
```

Here we can really appreciate the definition of matrix multiplication.

We can interpret $A_{{\mathbf e}}$ as the column vectors *of* the basis of an alternative coordinate system ${\mathbf a}$, *in regard to* the unit basis ${\mathbf e}$.

In other words, $A_{\mathbf e}$ is the way the vectors of the alternative coordinate system look to us, from our unit basis.

From the perspective of that alternative coordinate system, however, their basis vectors look to them the way the unit basis looks to us from our perspective ($A_{{\mathbf a}} = I_{\mathbf e}$, as we shall show later).

We denote by $v_{\mathbf a}$ the column vector consisting of the coordinates of a vector $v$ in regard to the alternative basis ${\mathbf a}$.

That is to say, $v_{\mathbf a}$ is the way $v$ looks from the basis ${\mathbf a}$.

For clarity, a distinction is made between the column vector $v_{\mathbf e}$ with regard to the unit basis, and the vector $v$ which has no inherent coordinates.

We could also have written our expression as follows:

```math
v_{\mathbf e} = \sum_i^n{(v_{\mathbf a})_i A_{\mathbf e}^{*i}}
```

where $A_{\mathbf e}^{*i}$ is the $i^{th}$ column vector of $A_{\mathbf e}$.

In effect, we are multiplying each coordinate in $v_{\mathbf a}$ with the corresponding representation of its component in $A_{\mathbf e}$, and taking the sum of all such products.

Thereby we construct the representation of $v$ as $v_{\mathbf e}$ from:
- its representation as $v_{\mathbf a}$
- and the representation of ${\mathbf a}$ as $A_{\mathbf e}$

We can also easily obtain the following, ommitting the ${\mathbf e}$ subscript from now on for brevity:

```math
v_{\mathbf a} = A^{-1}v \\
```
```math
A_{\mathbf a}^{*i} = A^{-1}A^{*i}
```
```math
A_{\mathbf a} = I
```

## matrix transformations

We can take our scheme a step further:

```math
```
