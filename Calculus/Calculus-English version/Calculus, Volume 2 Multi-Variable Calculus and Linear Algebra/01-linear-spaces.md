# 1. Linear Spaces

## 1.1 Introduction

A **linear space** (or **vector space**) is a general mathematical concept that unifies many examples:

- Real numbers
- Complex numbers
- Vectors in $n$-space
- Real-valued functions
- Vector-valued functions
- Infinite series

A linear space is a set of elements on which two operations — **addition** and **multiplication by numbers** (scalars) — can be performed, satisfying ten axioms listed below.

## 1.2 Definition of a Linear Space

Let $V$ be a nonempty set of objects called **elements**. $V$ is a **linear space** if it satisfies the following ten axioms.

### Closure Axioms

| Axiom | Name | Statement |
|-------|------|-----------|
| **1** | Closure under addition | For every $x,y\in V$, there is a unique $x+y\in V$. |
| **2** | Closure under multiplication | For every $x\in V$ and real $a$, there is a unique $ax\in V$. |

### Axioms for Addition

| Axiom | Name | Statement |
|-------|------|-----------|
| **3** | Commutative law | $x+y=y+x$ for all $x,y\in V$. |
| **4** | Associative law | $(x+y)+z=x+(y+z)$ for all $x,y,z\in V$. |
| **5** | Existence of zero | There exists $O\in V$ such that $x+O=x$ for all $x\in V$. |
| **6** | Existence of negatives | For every $x\in V$, $(-1)x$ satisfies $x+(-1)x=O$. |

> The element $(-1)x$ is called the **negative** of $x$ and is denoted $-x$. Thus $x+(-x)=O$.

### Axioms for Multiplication by Numbers

| Axiom | Name | Statement |
|-------|------|-----------|
| **7** | Associative law | $a(bx)=(ab)x$ for all $x\in V$ and real $a,b$. |
| **8** | Distributive law (in $V$) | $a(x+y)=ax+ay$ for all $x,y\in V$ and real $a$. |
| **9** | Distributive law (in $\mathbb{R}$) | $(a+b)x=ax+bx$ for all $x\in V$ and real $a,b$. |
| **10** | Identity | $1x=x$ for all $x\in V$. |

### Real vs. Complex Linear Spaces

- **Real linear space:** Scalars are real numbers (Axioms 2, 7–9 use real numbers).
- **Complex linear space:** Replace "real number" by "complex number" in Axioms 2, 7–9.
- When the term **linear space** is used without qualification, it may be either real or complex.

The numbers used as multipliers are called **scalars**.

## 1.3 Examples of Linear Spaces

### Number Spaces

**Example 1:** $V=\mathbb{R}$, the set of all real numbers, with ordinary addition and multiplication.

**Example 2:** $V=\mathbb{C}$, the set of all complex numbers, with ordinary addition of complex numbers and multiplication by **real** scalars. This is a **real** linear space (scalars are real, even though the elements are complex).

**Example 3:** $V=V_n$, the space of all $n$-tuples of real numbers, with componentwise addition and scalar multiplication.

**Example 4:** The set of all vectors in $V_n$ orthogonal to a given nonzero vector $N$.
- $n=2$: a line through $O$ with $N$ as normal vector.
- $n=3$: a plane through $O$ with $N$ as normal vector.

### Function Spaces

The following examples have real-valued functions as elements. Addition and scalar multiplication are defined pointwise:
$$
(f+g)(x)=f(x)+g(x),\qquad (af)(x)=a\,f(x).
$$
The zero element is the function whose values are everywhere zero.

| Example | Space | Note |
|---------|-------|------|
| 5 | All functions on a given interval | — |
| 6 | All polynomials | — |
| 7 | Polynomials of degree $\le n$ (fixed $n$) | The zero polynomial is included. Degree **exactly** $n$ is **not** a linear space (closure fails: sum of two degree-$n$ polynomials may have lower degree). |
| 8 | Continuous functions on $[a,b]$ | Denoted $C(a,b)$ |
| 9 | Functions differentiable at a given point | — |
| 10 | Functions integrable on a given interval | — |
| 11 | Functions with $f(1)=0$ | The value $0$ is essential; replacing it by $c\neq 0$ violates closure. |
| 12 | Solutions of $y''+ay'+by=0$ ($a,b$ constants) | Homogeneous linear ODE; the zero function is a solution. Nonhomogeneous equations do **not** form linear spaces (closure fails). |

## 1.4 Elementary Consequences of the Axioms

### 1.4.1 Uniqueness Theorems

**Theorem 1.1 (Uniqueness of the zero element).** In any linear space there is **one and only one** zero element.

**Proof sketch:** Suppose $O_1$ and $O_2$ are both zero elements. Then
$$
O_1+O_2=O_1 \quad\text{and}\quad O_2+O_1=O_2.
$$
By commutativity (Axiom 3), $O_1+O_2=O_2+O_1$, so $O_1=O_2$.

**Theorem 1.2 (Uniqueness of negatives).** Every element $x$ has exactly one negative.

**Proof sketch:** Suppose $y_1$ and $y_2$ are both negatives of $x$. Then $x+y_1=O$ and $x+y_2=O$. Adding $y_2$ to the first equation:
$$
y_2+(x+y_1)=y_2+O=y_2.
$$
By associativity and commutativity:
$$
y_2+(x+y_1)=(y_2+x)+y_1=O+y_1=y_1.
$$
Hence $y_1=y_2$. The unique negative of $x$ is $(-1)x$.

> **Notation:** The negative of $x$ is denoted $-x$. The **difference** $y-x$ is defined as $y+(-x)$.

### 1.4.2 Theorem 1.3 — Algebraic Properties

In any linear space, for arbitrary elements $x,y$ and scalars $a,b$:

| Property | Formula |
|----------|---------|
| (a) | $0x=O$ |
| (b) | $aO=O$ |
| (c) | $(-a)x=-(ax)=a(-x)$ |
| (d) | If $ax=O$, then $a=0$ or $x=O$ |
| (e) | If $ax=ay$ and $a\neq 0$, then $x=y$ |
| (f) | If $ax=bx$ and $x\neq O$, then $a=b$ |
| (g) | $-(x+y)=(-x)+(-y)=-x-y$ |
| (h) | $x+x=2x$, and in general $\sum_{i=1}^n x=nx$ |

**Proof sketch:**
- **(a)** Let $z=0x$. Then $z+z=0x+0x=(0+0)x=0x=z$. Adding $-z$ gives $z=O$.
- **(b)** Let $z=aO$. Then $z+z=aO+aO=a(O+O)=aO=z$. Hence $z=O$.
- **(c)** Let $z=(-a)x$. Then $z+ax=(-a)x+ax=(-a+a)x=0x=O$, so $z=-(ax)$. Similarly $a(-x)=-(ax)$.
- **(d)** If $a\neq 0$, multiply $ax=O$ by $a^{-1}$: $x=a^{-1}O=O$.
- **(e)** $ax=ay$ implies $a(x-y)=O$. By (d), since $a\neq 0$, we get $x-y=O$, so $x=y$.
- **(f)** $ax=bx$ implies $(a-b)x=O$. By (d), since $x\neq O$, we get $a-b=0$.
- **(g)** $(-x)+(-y)$ added to $x+y$ gives $(-x+x)+(-y+y)=O+O=O$.
- **(h)** By definition, $2x=x+x$, $3x=x+x+x$, etc.
