---
layout: post
title: "Notes on Linear Algebra"
author: "Rui"
categories: documentation
tags: [documentation,sample]
image: cuba-1.jpg
---

# Notes on the book Finite-Dimensional Vector Spaces

## Chapter 1

Download [Chapter 1](https://github.com/ruimp/linalg/archive/master.zip).

Spaces {#cha:spaces}
======

Fields {#sec:fields}
------

The objects we intend to study, vector spaces, are defined over an
underlying field. It is therefore reasonable to start by studying the
structure of fields.

Let $F$ be a set where two operations are defined, *addition* $(+)$ and
*multiplication* $(\cdot)$. $F$ is a **field** if the following axioms
hold:

Let $\alpha$, $\beta$ and $\gamma \in F$ be elements of the field.

### Axioms of Addition {#sec:axioms_addition}

1.  Addition is commutative, $\alpha + \beta = \beta + \alpha$.

2.  Addition is associative,
    $\alpha + (\beta + \gamma) = (\alpha + \beta) + \gamma$.

3.  There exists an unique $0 \in F$ (neutral element) such that
    $\alpha + 0 = \alpha$ for every $\alpha \in F$.

4.  To every element $\alpha$ corresponds a (additive) inverse element
    $-\alpha$ such that $\alpha + (- \alpha ) = 0$.

### Axioms of Multiplication {#sec:axioms_multiplication}

1.  Multiplication is commutative, $\alpha \beta = \beta \alpha$.

2.  Multiplication is associative,
    $\alpha (\beta \gamma) = (\alpha \beta) \gamma$.

3.  There exists an unique $1 \in F$ (identity element) such that
    $\alpha \cdot 1 = \alpha$ for every $\alpha \in F$.

4.  To every element $\alpha$ corresponds a (multiplicative) inverse
    element $\alpha^{-1}$ such that $\alpha \alpha^{-1} = 1$.

### Axiom of Distributivity {#subsec:axiom_distributivity}

Multiplication is distributive with respect to addition,
$\alpha (\beta + \gamma) = \alpha \beta + \alpha \gamma$.

Vector Spaces {#sec:vector_spaces}
-------------

A **vector space** is a set $V$ of elements called **vectors**
satisfying the following axioms.

Let $x$, $y$, $z \in V$ and $\alpha$, $\beta \in F$ then

-   \(C\) Addition is commutative, $x + y = y + x$.

-   \(A\) Addition is associative, $x + (y + z) = (x + y) + z$.

-   \(N\) There exists an unique $0 \in V$ (neutral element) such that
    $\x + 0 = x$ for every $x \in V$.

-   \(I\) To every element $x \in V$ corresponds an (additive) inverse
    element $-x$ such that $x + (-x) = 0$.

-   \(A\) Scalar multiplication is associative,
    $\alpha (\beta x) = (\alpha \beta) x$.

-   \(D\) Scalar multiplication is distributive,
    $\alpha (x + y) = \alpha x + \alpha y$.

-   \(D\) Vector multiplication is distributive,
    $(\alpha + \beta) x = \alpha x + \beta x$.

-   \(U\) For every $x \in V$, $1 x = x$.

The relation between a vector space $V$ and the underlying field $F$ is
usually descrived by saying the $V$ is a vector space over $F$.

Every field forms a vector space over itself with the obvious operation.

Linear dependence {#sec:linear_dependence}
-----------------

A finite set $\{x_i\}$ of vectors is **linearly dependent** if there
exists a corresponding set $\{\alpha_{i}\}$ of scalars, not all zero,
such that $$\sum_{i} \alpha_{i}x_{i} = 0.$$ If, on the other hand,
$\sum_{i} \alpha_{i} x_{i} = 0 \Rightarrow \alpha_{i} = 0$ for all $i$,
then the set $\{x_{i}\}$ is **linearly independent**.

The definition of linear independence is constructed in such a way that
the empty set is linearly independent.

Every set $\{x, y\}$ of the vector field $\mathbb{C}^{1}$ (along with
$\mathbb{R}^{1}$) is linearly dependent. If $x = y = 0$ this is trivial.
Otherwise, note that we may choose coeficients $yx + (-x)y = 0$.

Linear Combinations {#sec:linear_combinations}
-------------------

Let us say that that if $x = \sum_{i} \alpha_{i} x_{i}$ then $x$ is a
**linear combination** of $\{x_{i}\}$.

[\[thm:linear_independence\]]{#thm:linear_independence
label="thm:linear_independence"} The set of non-zero vectors
$x_{1}, \dots , x_{n}$ is linearly independent if and only if some
$x_{k}$, for $2 \leq k \leq n$, is a linear combination of the
preceeding ones.

::: {.proof}
*Proof.* Suppose that $x_{1}, \dots, x_{n}$ are linearly dependent, and
choose the first $k$ for which the preceeding set of vectors is linearly
dependent. Then $$\sum_{i} \alpha_{i} x_{i} = 0$$ and therefore
$$x_{k} = - \frac{1}{\alpha_{k}} \sum_{i \neq k} \alpha_{i} x_{i}$$
which proof the necessity of the condition. The sufficency is
consequence of the fact that every set containing a linearly dependent
subset is itself such. ◻
:::

Bases {#sec:bases}
-----

A (linear) basis in a vector space $V$ is a set $X$ of linearly
independent vectors such that every vector in $V$ is a linear
combination of elements in $X$. A vector space $V$ is
**finite-dimensional** if it has a finite basis.

Let $x \in V$ and $\{x_{1}, \dots, x_{n}\}$ a basis of $V$. Then $x$ may
be writen as $$x = \sum_{i} \xi_{i} x_{i}$$ and the coefficients
$\xi_{i}$ are unique.

::: {.proof}
*Proof.* Assume that there exist coefficients $\eta_{i}$ such that
$x = \sum_{i} \eta_{i} x_{i}$. Considering the subtraction
$$\sum_{i} (\xi_{i} - \eta_{i}) x_{i} = 0$$ which emplies that
$\xi_{i} - \eta_{i} = 0$ for every $i$, because $x_{i}$ are linearly
independent. We conclude that $\xi_{i} = \eta_{i}$. ◻
:::

[\[thm:basis_refinement\]]{#thm:basis_refinement
label="thm:basis_refinement"} If $V$ is a finite-dimensional vector
space and $Y = \{y_{1}, \dots, y_{m}\}$ any set of linearly independent
vectors in $V$, then, unless $Y$ forms a basis of $V$, we can find
vectors $y_{m+1}, \dots, y_{m+p}$ so that the reunion with $Y$ is a
basis of $V$.

::: {.proof}
*Proof.* Let $X = \{x_{i}\}$ be a given finite basis of $V$. We consider
the reunion
$$Y \cup X = \{ y_{1}, \dots, y_{m}, x_{1}, \dots, x_{n}\}.$$ The proof
proceeds by iteratively applying theorem
[\[thm:linear_independence\]](#thm:linear_independence){reference-type="ref"
reference="thm:linear_independence"}. The $y_{i}$ are already linearly
independent. We then consider $x_{j}$, verifying if it may be expressed
in termos of existing set. If not, it is added to the set, else
discarded. As $X$ is a basis of $V$ we are garantied that the remaining
set will be a basis of $V$ containing $Y$. ◻
:::

Dimension {#sec:dimension}
---------

[\[thm:number_elements_basis\]]{#thm:number_elements_basis
label="thm:number_elements_basis"} The number of elements in any basis
of a finite-dimensional vector space $V$ is the same as in any other
basis.

::: {.proof}
*Proof.* Let $X = \{x_{1}, \dots, x_{n}\}$ and
$Y = \{ y_{1}, \dots, y_{m}\}$ be basis of $V$. Consider the set
$$\{y_{m}\} \cap X.$$ This set is obviously linearly dependent,
otherwise $X$ would not be a basis of $V$. If we aply theorem
[\[thm:basis_refinement\]](#thm:basis_refinement){reference-type="ref"
reference="thm:basis_refinement"} to this set, we will then get a
linearly independent set
$$\{y_{m}, x_{1}, \dots, x_{i-1}, x_{i+1}, \dots, x_{n}\},$$ where the
element $x_{i}$ was removed as described by the theorem. If we continue
in this fashing by now appending to this set $y_{m-1}, y_{m-2}, \dots$
repeatedly we will eventually replace all elements of $X$ with elements
of $Y$. We are assured that no elements of $Y$ will be removed by
following theorem
[\[thm:basis_refinement\]](#thm:basis_refinement){reference-type="ref"
reference="thm:basis_refinement"} as all elements of $Y$ are amongst
themselves linearly independent. Then $n = m$ and this concludes the
proof. ◻
:::

The **dimension** of a finite-dimensional vector space $V$ is the number
of elements in a basis of $V$.

From theorems
[\[thm:linear_independence\]](#thm:linear_independence){reference-type="ref"
reference="thm:linear_independence"} and
[\[thm:number_elements_basis\]](#thm:number_elements_basis){reference-type="ref"
reference="thm:number_elements_basis"} one may construct the following
corollary:

Every set of $n+1$ vectors in an n-dimensional vector space $V$ is
linearly dependent. A set of n vectors in $V$ is abasis if and only if
it is linearly independent, or, if and only if every vector is $V$ is a
linear combination of elements of the set.

Isomorphism {#sec:isomorphism}
-----------

Two vector spaces $U$ and $V$ (over the same field) are **isomorphic**
if there is a one-to-one correspondence between vectors $x \in U$ and
$y = T(x) \in V$ such that
$$T(\alpha x_{1} + \beta x_{2}) = \alpha T(x_{1}) + \beta T(x_{2})$$

Every n-dimensional vector space $V$ over a field $F$ is isomorphic to
$F^{n}$.

::: {.proof}
*Proof.* Let $\{x_{1}, \dots, x_{n}\}$ be a basis of $V$. Then any
$x \in V$ may be written as $\sum_{i} \xi_{i} x_{i}$ for unique
coefficients $\xi_{i}$. We define $$\begin{aligned}
    \psi:  V & \longrightarrow F^{n} \\
    x & \longmapsto (\xi_{1}, \dots, \xi_{n}).
  \end{aligned}$$ The map $\psi$ is:

-   injective: clearly the coefficients $\xi_{i}$ define a unique vector
    in $V$.

-   surjective: the image of the basis
    $\psi (x_{i}) = (0, \dots, 1, \dots, 0)$ is a basis of $F^{n}$, and
    surjectivity follows.

and therefore one-to-one. Let $x$, $y \in V$ such that
$x = \sum_{i} \xi_{i} x_{i}$ and $y = \sum_{i} \eta_{i} y_{i}$ then
$$\psi \left( \alpha x + \beta y \right) = ( \alpha x_{1} + \beta y_{1}, \dots, \alpha x_{n} + \beta y_{n}) \\
$$
$$= \alpha (x_{1}, \dots,  x_{n})  + \beta (y_{1}, \dots, y_{n}) = \alpha \psi(x) + \beta \psi(y)$$
so $\psi$ is our desired isomorphism. ◻
:::

Subspaces {#sec:subspaces}
---------

A non-empty subset $M$ of a vector space $V$ is a **subspace**, or
**linear manifold**, if along with every pair $x$, $y \in M$, then
$\alpha x + \beta y \in M$.

Let $M$ be a subspace of $V$ and $x \in M$. Then $x - x \in M$ therefore
every subspace includes the origin.

Calculus of Subspaces {#sec:calculus_subspaces}
---------------------

The intersection of any collection of subspaces is a subspace.

::: {.proof}
*Proof.* Let $M = \cap_{i} M_{i}$. Taking $x \in M_{\mu}$ and
$y \in M_{\nu}$, we may choose basis $X_{\mu}$ and $X_{\nu}$ of
$M_{\mu}$ and $M_{\nu}$ such that $x \in X_{\mu}$ and $y \in X_{\nu}$.

If $\{x, y\}$ is a linear dependent set, then we are done, for
$\alpha x + \beta y$ is contained both in $M_{\mu}$ and in $M_{\nu}$
therefore in $M$.

Otherwise, we consider a set $X_{\mu} \cup X_{\nu}$ and use theorem
[\[thm:basis_refinement\]](#thm:basis_refinement){reference-type="ref"
reference="thm:basis_refinement"} reduce it to a linear independent set,
which is guaranteed to contain $x$ and $y$. Obviously any linear
combination of $x$ and $y$ is generated by elements of this set, hence
it is contained in $M$. Then $M$ is a subspace. ◻
:::

If $S$ is a set of vector in a vector space $V$ and if $M$ is the
subspace spanned by $S$, then $M$ is the same as the set of all linear
combinations of elements of $S$.

