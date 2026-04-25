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
