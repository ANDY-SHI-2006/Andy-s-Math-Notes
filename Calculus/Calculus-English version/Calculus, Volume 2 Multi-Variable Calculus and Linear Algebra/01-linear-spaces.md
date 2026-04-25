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

## 1.6 Subspaces of a Linear Space

### 1.6.1 Definition and Criterion

**Definition.** Let $V$ be a linear space. A nonempty subset $S\subseteq V$ is called a **subspace** of $V$ if $S$ is itself a linear space under the same operations of addition and scalar multiplication.

**Theorem 1.4 (Subspace criterion).** A nonempty subset $S$ of a linear space $V$ is a subspace **if and only if** $S$ satisfies the **closure axioms**:
- $x+y\in S$ for all $x,y\in S$.
- $ax\in S$ for all $x\in S$ and all scalars $a$.

**Proof sketch:**
- ($\Rightarrow$) Immediate: a subspace satisfies all axioms, hence closure.
- ($\Leftarrow$) If $S$ is closed under addition and scalar multiplication:
  - Axioms 3, 4, 7–10 hold automatically in $S$ because they hold for all elements of $V$.
  - For Axiom 5 (zero element): take any $x\in S$ and $a=0$; then $0x=O\in S$ by Theorem 1.3(a).
  - For Axiom 6 (negatives): take $a=-1$; then $(-1)x=-x\in S$, and $x+(-x)=O$.

### 1.6.2 Linear Combinations and Span

**Definition.** Let $S$ be a subset of $V$. An element $x\in V$ of the form
$$
x=\sum_{i=1}^k c_i x_i,
$$
where $x_1,\dots,x_k\in S$ and $c_1,\dots,c_k$ are scalars, is called a **finite linear combination** of elements of $S$.

The set of all finite linear combinations of elements of $S$ is called the **subspace spanned by $S$** (or the **linear span** of $S$), denoted $L(S)$.

- $L(S)$ satisfies the closure axioms, hence is a subspace of $V$.
- If $S$ is empty, we define $L(S)=\{O\}$.

### 1.6.3 Examples of Spanning Sets

Different sets may span the same subspace.

| Space | Spanning set(s) |
|-------|-----------------|
| $V_2$ | $\{i,j\}$, $\{i,j,i+j\}$, $\{O,i,-i,j,-j,i+j\}$ |
| Polynomials of degree $\le n$ | $\{1,t,t^2,\dots,t^n\}$, $\{1,t/2,t^2/3,\dots,t^n/(n+1)\}$, $\{1,(1+t),(1+t)^2,\dots,(1+t)^n\}$ |
| All polynomials | $\{1,t,t^2,\dots\}$ (infinite set) |

> These examples lead naturally to the concepts of **dependence**, **independence**, **bases**, and **dimension** — the subject of the next sections.

## 1.7 Dependent and Independent Sets in a Linear Space

### 1.7.1 Definitions

**Definition.** A set $S$ in a linear space $V$ is called **dependent** if there exist distinct elements $x_1,\dots,x_k\in S$ and scalars $c_1,\dots,c_k$, **not all zero**, such that
$$
\sum_{i=1}^k c_i x_i = O.
$$
An equation $\sum c_i x_i = O$ with not all $c_i=0$ is called a **nontrivial representation** of $O$.

The set $S$ is called **independent** if it is **not** dependent; equivalently,
$$
\sum_{i=1}^k c_i x_i = O \quad\text{implies}\quad c_1=c_2=\dots=c_k=0
$$
for every finite choice of distinct elements $x_i\in S$ and scalars $c_i$.

> These terms also apply to the elements themselves: elements of an independent set are called **independent elements**.

### 1.7.2 Elementary Properties

| Example | Statement |
|---------|-----------|
| 1 | If $T\subseteq S$ and $T$ is dependent, then $S$ is dependent. (Equivalently: every subset of an independent set is independent.) |
| 2 | If one element of $S$ is a scalar multiple of another, then $S$ is dependent. |
| 3 | If $O\in S$, then $S$ is dependent. |
| 4 | The **empty set** is independent. |

### 1.7.3 Examples in Function Spaces

**Example 5:** $u_1(t)=\cos^2 t$, $u_2(t)=\sin^2 t$, $u_3(t)=1$.
- Since $u_1+u_2-u_3=O$, these three functions are dependent.

**Example 6:** $u_k(t)=t^k$ ($k=0,1,2,\dots$).
- The set $\{u_0,u_1,u_2,\dots\}$ is **independent**.
- Proof: $\sum_{k=0}^n c_k t^k=0$ for all $t$ implies each $c_k=0$ (evaluate at $t=0$, differentiate repeatedly).
  (Equation 1.1)

**Example 7:** Exponential functions $u_k(x)=e^{a_k x}$ with distinct $a_k$.
- **Independent.** Proof by induction on $n$:
  1. Assume $\sum_{k=1}^n c_k e^{a_k x}=0$. (Equation 1.2)
  2. Let $a_M$ be the largest $a_k$. Multiply by $e^{-a_M x}$:
     $$
     \sum_{k=1}^n c_k e^{(a_k-a_M)x}=0.
     $$
     (Equation 1.3)
  3. As $x\to+\infty$, terms with $k\neq M$ tend to 0, so $c_M=0$.
  4. Apply induction hypothesis to remaining $n-1$ terms.

### 1.7.4 Theorem 1.5 — Dependence in Spanned Subspaces

Let $S$ be an independent set of $k$ elements in $V$, and let $L(S)$ be its span. Then **every set of $k+1$ elements in $L(S)$ is dependent**.

**Proof sketch:**
- When $k=1$, $S=\{x_1\}$ with $x_1\neq O$. Any two elements in $L(S)$ are $y_1=c_1 x_1$ and $y_2=c_2 x_1$. Then $c_2 y_1-c_1 y_2=O$ is a nontrivial relation, so $\{y_1,y_2\}$ is dependent.
- Induction step: assume true for $k-1$. Let $T=\{y_1,\dots,y_{k+1}\}\subseteq L(S)$, and write $y_i=\sum_{j=1}^k a_{ij}x_j$ (Equation 1.4).
  - **Case 1:** All $a_{i1}=0$. Then each $y_i\in L(S')$ where $S'=\{x_2,\dots,x_k\}$ has $k-1$ independent elements. By induction, $T$ is dependent.
  - **Case 2:** Some $a_{i1}\neq 0$; assume $a_{11}\neq 0$. Set $c_i=a_{i1}/a_{11}$. Then each $c_i y_1-y_i$ is a linear combination of $x_2,\dots,x_k$. By the induction hypothesis applied to these $k$ elements in the span of $k-1$ independent elements, they are dependent. Hence there exist scalars $t_i$, not all zero, with $\sum_{i=2}^{k+1} t_i(c_i y_1-y_i)=O$, which is a nontrivial relation among $y_1,\dots,y_{k+1}$. Therefore $T$ is dependent.

## 1.8 Bases and Dimension

### 1.8.1 Finite Basis and Dimension

**Definition.** A finite set $S$ in a linear space $V$ is a **finite basis** for $V$ if $S$ is **independent** and **spans** $V$.

| Term | Condition |
|------|-----------|
| **Finite-dimensional** | $V$ has a finite basis, or $V=\{O\}$ |
| **Infinite-dimensional** | $V$ has no finite basis |

- By convention, $\dim\{O\}=0$.

**Theorem 1.6 (Uniqueness of basis size).** Let $V$ be finite-dimensional. Then **every finite basis for $V$ has the same number of elements**.

**Proof sketch:**
- Let bases $S$ ($k$ elements) and $T$ ($m$ elements).
- $S$ independent and spans $V$ $\Rightarrow$ every set of $k+1$ elements in $V$ is dependent (Theorem 1.5).
- $T$ is independent with $m$ elements $\Rightarrow m\le k$.
- Interchange roles $\Rightarrow k\le m$.
- Hence $k=m$.

**Definition.** If $V$ has a basis of $n$ elements, $n$ is the **dimension** of $V$, written $n=\dim V$.

### 1.8.2 Examples

| Space | Dimension | Basis |
|-------|-----------|-------|
| $V_n$ | $n$ | $n$ unit coordinate vectors |
| Polynomials of degree $\le n$ | $n+1$ | $\{1,t,t^2,\dots,t^n\}$ |
| Solutions of $y''-2y'-3y=0$ | $2$ | $\{e^{-x},e^{3x}\}$ |
| All polynomials $p(t)$ | **Infinite** | $\{1,t,t^2,\dots\}$ spans, but no finite set spans |

### 1.8.3 Theorem 1.7 — Properties of Bases

Let $V$ be finite-dimensional with $\dim V=n$.

**(a) Extension.** Any independent set in $V$ is a subset of some basis for $V$.

**(b) Criterion.** Any set of $n$ independent elements in $V$ is a basis for $V$.

**Proof sketch:**
- **(a):** Let $S=\{x_1,\dots,x_k\}$ be independent. If $L(S)=V$, done. Otherwise pick $y\notin L(S)$. Then $S'=S\cup\{y\}$ is independent (if $\sum c_i x_i+c_{k+1}y=O$, then $c_{k+1}\neq 0$ since $S$ is independent, so $y\in L(S)$, contradiction). Repeat; the process terminates in finitely many steps, yielding a basis containing $S$.
- **(b):** By (a), $S$ is contained in a basis $B$. But $|B|=n=|S|$, so $S=B$.

## 1.9 Components

Let $V$ be a linear space of dimension $n$ and consider an **ordered basis** $(e_1,\dots,e_n)$ (elements taken in a given order).

- Every $x\in V$ has a unique representation:
  $$
  x=\sum_{i=1}^n c_i e_i. \tag{1.5}
  $$
- The $n$-tuple $(c_1,\dots,c_n)$ is **uniquely determined** by $x$.
  - Proof of uniqueness: If $x=\sum d_i e_i$, then $\sum(c_i-d_i)e_i=O$. Independence implies $c_i=d_i$ for all $i$.
- $(c_1,\dots,c_n)$ are called the **components of $x$ relative to the ordered basis** $(e_1,\dots,e_n)$.

## 1.10 Inner Products, Euclidean Spaces, and Norms

### 1.10.1 Inner Product — Axiomatic Definition

In $V_n$, lengths and angles were defined via the dot product. We now generalize this to arbitrary linear spaces.

Recall the dot product in $V_n$:
$$
x\cdot y = \sum_{i=1}^n x_i y_i. \tag{1.6}
$$

**Definition (Real inner product).** A real linear space $V$ has an **inner product** if for each pair $x,y\in V$ there is a unique real number $(x,y)$ satisfying:

| Axiom | Property | Name |
|-------|----------|------|
| (1) | $(x,y)=(y,x)$ | Symmetry |
| (2) | $(x,y+z)=(x,y)+(x,z)$ | Additivity |
| (3) | $c(x,y)=(cx,y)$ | Homogeneity |
| (4) | $(x,x)>0$ if $x\neq O$ | Positivity |

- Note: Taking $c=0$ in (3) gives $(O,y)=0$ for all $y$.

A real linear space with an inner product is called a **real Euclidean space**.

**Complex inner product.** In a complex space, (1) is replaced by:
$$
(x,y)=\overline{(y,x)}. \tag{1'}
$$
- Then $(x,cy)=\bar c(x,y)$.
- Such a space is called a **complex Euclidean space** (or **unitary space**).
- The theorems below apply to both real and complex cases.

### 1.10.2 Examples of Inner Products

**Example 1:** In $V_n$, $(x,y)=x\cdot y$ (the usual dot product).

**Example 2:** In $V_2$, define $(x,y)=2x_1y_1+x_1y_2+x_2y_1+x_2y_2$.
- This is a valid inner product, showing a space may admit **more than one** inner product.

**Example 3:** In $C(a,b)$ (continuous real-valued functions on $[a,b]$):
$$
(f,g)=\int_a^b f(t)g(t)\,dt.
$$
- Analogous to (1.6): function values play the role of components, integration replaces summation.

**Example 4 (Weighted):** In $C(a,b)$ with a fixed positive function $w$:
$$
(f,g)=\int_a^b w(t)f(t)g(t)\,dt.
$$
- $w$ is called a **weight function**; Example 3 has $w(t)\equiv 1$.

**Example 5:** In the space of all real polynomials:
$$
(f,g)=\int_0^\infty e^{-t}f(t)g(t)\,dt.
$$
- The exponential factor ensures convergence for all polynomials.

### 1.10.3 Theorem 1.8 — Cauchy–Schwarz Inequality

In any Euclidean space $V$,
$$
|(x,y)|^2 \le (x,x)(y,y) \quad\text{for all }x,y\in V.
$$

- **Equality holds iff $x$ and $y$ are dependent** (i.e., one is a scalar multiple of the other).

**Proof sketch:**
- If either $x=O$ or $y=O$, the result is trivial.
- Assume $x,y$ nonzero. Let $z=ax+by$. Then $(z,z)\ge 0$ for all $a,b$.
- Using properties (1$'$), (2), and (3$'$):
  $$
  (z,z)=a\bar a(x,x)+a\bar b(x,y)+b\bar a(y,x)+b\bar b(y,y)\ge 0.
  $$
- Taking $a=(y,y)$ and $b=-(x,y)$, cancelling the positive factor $(y,y)$:
  $$
  (y,y)(x,x)\ge(x,y)(y,x)=|(x,y)|^2.
  $$
- Equality holds iff $z=O$, which means $x$ and $y$ are dependent.

**Example.** In $C(a,b)$ with $(f,g)=\int_a^b f(t)g(t)\,dt$, the inequality becomes:
$$
\left(\int_a^b f(t)g(t)\,dt\right)^2 \le \left(\int_a^b f^2(t)\,dt\right)\left(\int_a^b g^2(t)\,dt\right).
$$

### 1.10.4 Norm

**Definition.** In a Euclidean space $V$, the **norm** of $x$ is
$$
\|x\| = (x,x)^{1/2}.
$$

In terms of norms, the Cauchy–Schwarz inequality becomes:
$$
|(x,y)| \le \|x\|\,\|y\|.
$$

- The norm depends on the choice of inner product (analogous to choice of scale/unit).

**Theorem 1.9 (Properties of norms).** In any Euclidean space, for all $x,y$ and scalars $c$:

| Property | Statement | Name |
|----------|-----------|------|
| (a) | $\|x\|=0$ iff $x=O$ | Definiteness |
| (b) | $\|x\|>0$ if $x\neq O$ | Positivity |
| (c) | $\|cx\|=|c|\,\|x\|$ | Homogeneity |
| (d) | $\|x+y\|\le\|x\|+\|y\|$ | Triangle inequality |

- Equality in (d) holds if $x=O$, $y=O$, or $y=cx$ with $c>0$.

**Proof sketch:**
- (a)–(c) follow directly from inner-product axioms.
- (d): Expand $\|x+y\|^2=(x+y,x+y)=\|x\|^2+\|y\|^2+(x,y)+\overline{(x,y)}$. By Cauchy–Schwarz, $|(x,y)|\le\|x\|\,\|y\|$, so:
  $$
  \|x+y\|^2 \le \|x\|^2+\|y\|^2+2\|x\|\,\|y\| = (\|x\|+\|y\|)^2.
  $$
- When $y=cx$ ($c>0$): $\|x+y\|=\|x+cx\|=(1+c)\|x\|=\|x\|+\|cx\|=\|x\|+\|y\|$.

### 1.10.5 Angle in a Real Euclidean Space

**Definition.** The **angle** $\theta$ ($0\le\theta\le\pi$) between nonzero $x$ and $y$ is defined by:
$$
\cos\theta = \frac{(x,y)}{\|x\|\,\|y\|}. \tag{1.7}
$$

- The Cauchy–Schwarz inequality guarantees the quotient lies in $[-1,1]$, so $\theta$ is uniquely determined.

## 1.11 Orthogonality in a Euclidean Space

### 1.11.1 Orthogonal and Orthonormal Sets

**Definition.** In a Euclidean space $V$:

| Term | Condition |
|------|-----------|
| **Orthogonal** | $(x,y)=0$ |
| **Orthogonal set** | $(x,y)=0$ for every pair of distinct $x,y\in S$ |
| **Orthonormal set** | Orthogonal set with $\|x\|=1$ for all $x\in S$ |

- The zero element is orthogonal to every element, and is the **only** element orthogonal to itself.

**Theorem 1.10 (Orthogonality implies independence).** In a Euclidean space $V$, every orthogonal set of **nonzero** elements is **independent**.

- In particular, in an $n$-dimensional Euclidean space, every orthogonal set of $n$ nonzero elements is a **basis**.

**Proof sketch:**
- Suppose $\sum_{i=1}^k c_i x_i=O$ with $x_i\in S$.
- Take inner product with $x_1$: $c_1(x_1,x_1)=0$.
- Since $x_1\neq O$, $(x_1,x_1)\neq 0$, so $c_1=0$.
- Repeat for each $x_j$ $\Rightarrow$ all $c_j=0$.
- If $|S|=n=\dim V$, then $S$ is a basis by Theorem 1.7(b).

### 1.11.2 Example — Trigonometric Functions in $C(0,2\pi)$

In $C(0,2\pi)$ with $(f,g)=\int_0^{2\pi}f(x)g(x)\,dx$, let
$$
u_0(x)=1,\quad u_{2n-1}(x)=\cos nx,\quad u_{2n}(x)=\sin nx\quad (n\ge 1).
$$

- **Orthogonality:** $\int_0^{2\pi} u_n(x)u_m(x)\,dx=0$ for $m\neq n$.
- **Norms:**
  - $\|u_0\|=\sqrt{2\pi}$
  - $\|u_{2n-1}\|=\|u_{2n}\|=\sqrt{\pi}$ for $n\ge 1$
- **Orthonormal set** $\{\varphi_0,\varphi_1,\varphi_2,\dots\}$ obtained by dividing each $u_n$ by its norm:
  $$
  \varphi_0(x)=\frac{1}{\sqrt{2\pi}},\quad \varphi_{2n-1}(x)=\frac{\cos nx}{\sqrt{\pi}},\quad \varphi_{2n}(x)=\frac{\sin nx}{\sqrt{\pi}}.
  $$

### 1.11.3 Components Relative to an Orthogonal Basis

**Theorem 1.11.** Let $V$ be finite-dimensional with $\dim V=n$, and let $S=\{e_1,\dots,e_n\}$ be an orthogonal basis. If $x=\sum_{i=1}^n c_i e_i$, then:
$$
c_j = \frac{(x,e_j)}{(e_j,e_j)} \quad\text{for }j=1,2,\dots,n. \tag{1.9}
$$

- In particular, if $S$ is **orthonormal**:
  $$
  c_j=(x,e_j). \tag{1.10}
  $$

- Equation (1.8) then becomes:
  $$
  x=\sum_{i=1}^n (x,e_i)e_i. \tag{1.11}
  $$

**Proof sketch:** Take inner product of $x=\sum c_i e_i$ with $e_j$; orthogonality kills all terms except $i=j$.

### 1.11.4 Parseval’s Formula

**Theorem 1.12.** Let $\{e_1,\dots,e_n\}$ be an orthonormal basis for $V$. Then for all $x,y\in V$:
$$
(x,y)=\sum_{i=1}^n (x,e_i)\overline{(y,e_i)}. \tag{1.12}
$$

- When $x=y$:
  $$
  \|x\|^2=\sum_{i=1}^n |(x,e_i)|^2. \tag{1.13}
  $$

**Proof sketch:** Expand $x$ and $y$ using (1.11) and apply linearity of the inner product; orthonormality yields the sum.

> Equation (1.12) is named after M. A. Parseval (circa 1776–1836). Equation (1.13) generalizes the Pythagorean theorem.

## 1.12 The Gram–Schmidt Process

### 1.12.1 Orthogonalization Theorem

Every finite-dimensional Euclidean space has an orthogonal basis. This follows from:

**Theorem 1.13 (Orthogonalization theorem).** Let $x_1,x_2,\dots$ be a finite or infinite sequence in a Euclidean space $V$, and let $L(x_1,\dots,x_k)$ denote the subspace spanned by the first $k$ elements. Then there exists a sequence $y_1,y_2,\dots$ in $V$ such that for each $k$:

| Property | Statement |
|----------|-----------|
| (a) | $y_k$ is orthogonal to every element in $L(y_1,\dots,y_{k-1})$ |
| (b) | $L(y_1,\dots,y_k)=L(x_1,\dots,x_k)$ |
| (c) | The sequence is **unique up to scalar factors**: if $y'_1,y'_2,\dots$ also satisfies (a) and (b), then $y'_k=c_k y_k$ for some scalar $c_k$ |

**Proof sketch (Gram–Schmidt construction):**
- Start with $y_1=x_1$.
- Assume $y_1,\dots,y_r$ constructed satisfying (a) and (b).
- Define:
  $$
  y_{r+1}=x_{r+1}-\sum_{i=1}^r a_i y_i, \tag{1.14}
  $$
  where $a_i$ are chosen to make $y_{r+1}$ orthogonal to each $y_j$ ($j\le r$).
- Taking inner product with $y_j$:
  $$
  (y_{r+1},y_j)=(x_{r+1},y_j)-a_j(y_j,y_j).
  $$
- If $y_j\neq O$, set:
  $$
  a_j=\frac{(x_{r+1},y_j)}{(y_j,y_j)}. \tag{1.15}
  $$
- If $y_j=O$, choose $a_j=0$.
- Then $y_{r+1}$ is orthogonal to $L(y_1,\dots,y_r)$, proving (a).
- Since $x_{r+1}$ and each $y_i$ lie in $L(x_1,\dots,x_{r+1})$, and conversely $x_{r+1}$ is a linear combination of $y_1,\dots,y_{r+1}$, we get (b).
- Uniqueness (c): any alternative $y'_{r+1}$ must lie in $L(y_1,\dots,y_{r+1})$ and be orthogonal to $L(y_1,\dots,y_r)$, hence is a scalar multiple of $y_{r+1}$.

### 1.12.2 The Gram–Schmidt Formulas

For an independent set $\{x_1,\dots,x_k\}$, the corresponding orthogonal set $\{y_1,\dots,y_k\}$ is given by:
$$
y_1=x_1,\qquad y_{r+1}=x_{r+1}-\sum_{i=1}^r\frac{(x_{r+1},y_i)}{(y_i,y_i)}y_i \quad (r=1,2,\dots,k-1). \tag{1.16}
$$

- If some $y_{r+1}=O$, then $x_{r+1}$ is a linear combination of $x_1,\dots,x_r$, so the original set is dependent.
- If $\{x_1,\dots,x_k\}$ is independent, then all $y_i$ are nonzero, and $\{y_1,\dots,y_k\}$ is an orthogonal basis for the same subspace.
- An **orthonormal basis** is obtained by normalizing: $e_i=y_i/\|y_i\|$.

**Corollary (Theorem 1.14).** Every finite-dimensional Euclidean space has an **orthonormal basis**.

**Projection.** For $y\neq O$, the element $\frac{(x,y)}{(y,y)}y$ is called the **projection of $x$ along $y$**. The Gram–Schmidt process constructs $y_{r+1}$ by subtracting from $x_{r+1}$ its projection along each earlier $y_i$.

### 1.12.3 Example in $V_4$

Find an orthonormal basis for the span of:
$$
x_1=(1,-1,1,-1),\quad x_2=(5,1,1,1),\quad x_3=(-3,-3,1,-3).
$$

**Step 1:** $y_1=x_1=(1,-1,1,-1)$.

**Step 2:**
$$
y_2=x_2-\frac{(x_2,y_1)}{(y_1,y_1)}y_1 = x_2-y_1 = (4,2,0,2).
$$

**Step 3:**
$$
y_3=x_3-\frac{(x_3,y_1)}{(y_1,y_1)}y_1-\frac{(x_3,y_2)}{(y_2,y_2)}y_2 = x_3-y_1+y_2 = (0,0,0,0).
$$

- Since $y_3=O$, the vectors $x_1,x_2,x_3$ are dependent; $y_1,y_2$ are independent, so the subspace has dimension 2.
- **Orthonormal basis:**
  $$
  e_1=\frac{y_1}{\|y_1\|}=\frac{1}{2}(1,-1,1,-1),\qquad e_2=\frac{y_2}{\|y_2\|}=\frac{1}{\sqrt{6}}(2,1,0,1).
  $$

### 1.12.4 Example — Legendre Polynomials

In the space of all real polynomials with inner product $(x,y)=\int_{-1}^1 x(t)y(t)\,dt$, apply Gram–Schmidt to $x_n(t)=t^n$:

| $n$ | $y_n(t)$ | $P_n(t)$ (standard Legendre) |
|-----|----------|------------------------------|
| 0 | $1$ | $1$ |
| 1 | $t$ | $t$ |
| 2 | $t^2-\frac{1}{3}$ | $\frac{1}{2}(3t^2-1)$ |
| 3 | $t^3-\frac{3}{5}t$ | $\frac{1}{2}(5t^3-3t)$ |
| 4 | $t^4-\frac{6}{7}t^2+\frac{3}{35}$ | $\frac{1}{8}(35t^4-30t^2+3)$ |
| 5 | $t^5-\frac{10}{9}t^3+\frac{5}{21}t$ | $\frac{1}{8}(63t^5-70t^3+15t)$ |

**Rodrigues formula:**
$$
y_n(t)=\frac{n!}{(2n)!}\frac{d^n}{dt^n}(t^2-1)^n,\qquad P_n(t)=\frac{1}{2^n n!}\frac{d^n}{dt^n}(t^2-1)^n.
$$

- The **normalized Legendre polynomials** are $\varphi_n=y_n/\|y_n\|$.

## 1.13 Orthogonal Complements and Projections

### 1.13.1 The Approximation Problem

Let $V$ be a Euclidean space and $S$ a finite-dimensional subspace. Given $x\in V$, find $s\in S$ minimizing the distance $\|x-s\|$.

- If $x\in S$, then $s=x$.
- Geometrically (in $V_3$ with $S$ a plane through the origin), the nearest point is obtained by dropping a perpendicular from $x$ to $S$.

### 1.13.2 Orthogonal Complement

**Definition.** An element in $V$ is **orthogonal to $S$** if it is orthogonal to every element of $S$. The set of all such elements is denoted $S^\perp$ (read "$S$ perpendicular").

- $S^\perp$ is a subspace of $V$, whether or not $S$ is.
- If $S$ is a subspace, $S^\perp$ is called the **orthogonal complement** of $S$.
- Example: If $S$ is a plane through the origin in $V_3$, then $S^\perp$ is the line through the origin perpendicular to $S$.

### 1.13.3 Theorem 1.15 — Orthogonal Decomposition

Let $V$ be a Euclidean space and $S$ a finite-dimensional subspace. Then **every** $x\in V$ can be represented **uniquely** as:
$$
x = s + s^\perp, \quad\text{where }s\in S\text{ and }s^\perp\in S^\perp. \tag{1.17}
$$

Moreover, the **Pythagorean formula** holds:
$$
\|x\|^2 = \|s\|^2 + \|s^\perp\|^2. \tag{1.18}
$$

**Proof sketch:**
- Since $S$ is finite-dimensional, it has an orthonormal basis $\{e_1,\dots,e_n\}$.
- Define:
  $$
  s = \sum_{i=1}^n (x,e_i)e_i, \qquad s^\perp = x - s. \tag{1.19}
  $$
- $s$ is a linear combination of basis elements, so $s\in S$.
- For any basis element $e_j$:
  $$
  (s^\perp,e_j) = (x,e_j) - (s,e_j) = (x,e_j) - (x,e_j) = 0.
  $$
  Hence $s^\perp$ is orthogonal to every element of $S$, so $s^\perp\in S^\perp$.
- **Uniqueness:** Suppose $x=t+t^\perp$ is another decomposition. Then $s-t=t^\perp-s^\perp$. The left side is in $S$, the right side in $S^\perp$. Thus $s-t$ is orthogonal to itself, so $s-t=O$ and $s^\perp=t^\perp$.
- **Pythagorean formula:**
  $$
  \|x\|^2=(x,x)=(s+s^\perp,s+s^\perp)=(s,s)+(s^\perp,s^\perp)=\|s\|^2+\|s^\perp\|^2.
  $$

### 1.13.4 Projection onto a Subspace

**Definition.** Let $S$ be a finite-dimensional subspace with orthonormal basis $\{e_1,\dots,e_n\}$. For $x\in V$, the element
$$
s = \sum_{i=1}^n (x,e_i)e_i
$$
is called the **projection of $x$ on the subspace $S$**.

- This projection is the unique element in $S$ that solves the approximation problem (minimizing $\|x-s\|$).
- The proof of this optimality property follows from the orthogonal decomposition theorem.
