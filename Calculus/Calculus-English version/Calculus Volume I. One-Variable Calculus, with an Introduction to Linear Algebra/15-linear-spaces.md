[<- Previous: 14. Calculus of Vector-Valued Functions](14-calculus-of-vector-valued-functions.md) | [Next: 16. Linear Transformations and Matrices ->](16-linear-transformations-and-matrices.md)

# 15. Linear Spaces

## 15.1 Introduction

- Throughout calculus we encounter objects that can be **added** and **multiplied by real numbers**:
  - Real numbers themselves
  - Real-valued functions
  - Complex numbers
  - Infinite series
  - Vectors in $n$-space
  - Vector-valued functions
- This chapter introduces the general concept of a **linear space** (or **vector space**) that unifies all these examples.
- A linear space is a set of elements with two operations (addition and scalar multiplication) satisfying certain axioms.

## 15.2 The Definition of a Linear Space

Let $V$ be a nonempty set of objects called **elements**. $V$ is a **linear space** if it satisfies the following ten axioms.

### 15.2.1 Closure Axioms

| Axiom | Statement |
|-------|-----------|
| **1. Closure under addition** | For every $x,y\in V$, there is a unique $x+y\in V$ |
| **2. Closure under multiplication by real numbers** | For every $x\in V$ and real $a$, there is $ax\in V$ |

### 15.2.2 Axioms for Addition

| Axiom | Statement |
|-------|-----------|
| **3. Commutative law** | $x+y=y+x$ for all $x,y\in V$ |
| **4. Associative law** | $(x+y)+z=x+(y+z)$ for all $x,y,z\in V$ |
| **5. Existence of zero element** | $\exists\,O\in V$ such that $x+O=x$ for all $x\in V$ |
| **6. Existence of negatives** | For every $x\in V$, $(-1)x$ satisfies $x+(-1)x=O$ |

### 15.2.3 Axioms for Multiplication by Numbers

| Axiom | Statement |
|-------|-----------|
| **7. Associative law** | $a(bx)=(ab)x$ for all $x\in V$ and real $a,b$ |
| **8. Distributive law for addition in $V$** | $a(x+y)=ax+ay$ for all $x,y\in V$ and real $a$ |
| **9. Distributive law for addition of numbers** | $(a+b)x=ax+bx$ for all $x\in V$ and real $a,b$ |
| **10. Existence of identity** | $1x=x$ for all $x\in V$ |

### 15.2.4 Terminology

- **Real linear space**: scalars are real numbers.
- **Complex linear space**: scalars are complex numbers (Axioms 2, 7–10 use complex numbers).
- Also called **linear vector space** or simply **vector space**.
- The multipliers are called **scalars**.
- Unless specified otherwise, "linear space" may refer to either real or complex.

## 15.3 Examples of Linear Spaces

### 15.3.1 Basic Number Spaces

**Example 1 — Real numbers:**
- $V=\mathbb{R}$, with ordinary addition and multiplication.

**Example 2 — Complex numbers:**
- $V=\mathbb{C}$, with ordinary complex addition and multiplication by **real** scalars.
- This is a **real** linear space (scalars are real, even though elements are complex).

**Example 3 — $n$-space:**
- $V=V_n$, the vector space of all $n$-tuples of real numbers, with component-wise operations.

**Example 4 — Orthogonal complement:**
- $V=$ set of all vectors in $V_n$ orthogonal to a given nonzero vector $N$.
- $n=2$: a line through $O$ with normal $N$.
- $n=3$: a plane through $O$ with normal $N$.

### 15.3.2 Function Spaces

The following are called **function spaces**. Addition and scalar multiplication are defined pointwise:
$$(f+g)(x)=f(x)+g(x),\qquad(af)(x)=af(x).$$
The zero element is the function identically zero.

| Example | Set $V$ | Notes |
|---------|---------|-------|
| **5** | All functions on a given interval | |
| **6** | All polynomials | |
| **7** | Polynomials of degree $\le n$ (fixed $n$) | Zero polynomial included. Degree $=n$ alone is **not** a linear space (closure fails) |
| **8** | Continuous functions on $[a,b]$ | Denoted $C(a,b)$ |
| **9** | Differentiable functions at a point | |
| **10** | Integrable functions on an interval | |
| **11** | Functions with $f(1)=0$ | The value $0$ is essential; replacing with $c\neq0$ violates closure |
| **12** | Solutions of $y''+ay'+by=0$ | Homogeneous linear ODE. Nonhomogeneous case fails closure |

> These examples show how the linear space concept unifies algebra, geometry, and analysis. A theorem proved from the axioms applies to **all** concrete examples at once.


## 15.4 Elementary Consequences of the Axioms

### 15.4.1 Uniqueness Theorems

**Theorem 15.1 — Uniqueness of the zero element.**
- In any linear space there is **one and only one** zero element.

**Proof sketch:** Suppose $O_1$ and $O_2$ are both zero. Then $O_1+O_2=O_1$ (taking $x=O_1$, $O=O_2$) and $O_2+O_1=O_2$ (taking $x=O_2$, $O=O_1$). By commutativity, $O_1=O_2$.

**Theorem 15.2 — Uniqueness of negative elements.**
- Every element $x$ has exactly one negative $y$ such that $x+y=O$.

**Proof sketch:** Suppose $y_1$ and $y_2$ are both negatives of $x$. Then:
$$
y_2+(x+y_1)=y_2+O=y_2,\qquad (y_2+x)+y_1=O+y_1=y_1.
$$
By associativity, $y_1=y_2$. The unique negative is $(-1)x$.

> **Notation:** The negative of $x$ is $-x$. The difference $y-x$ means $y+(-x)$.

### 15.4.2 Theorem 15.3 — Basic Algebraic Properties

In any linear space, for arbitrary elements $x,y$ and scalars $a,b$:

| Property | Statement |
|----------|-----------|
| **(a)** | $0x=O$ |
| **(b)** | $aO=O$ |
| **(c)** | $(-a)x=-(ax)=a(-x)$ |
| **(d)** | If $ax=O$, then either $a=0$ or $x=O$ |
| **(e)** | If $ax=ay$ and $a\neq0$, then $x=y$ |
| **(f)** | If $ax=bx$ and $x\neq O$, then $a=b$ |
| **(g)** | $-(x+y)=(-x)+(-y)=-x-y$ |
| **(h)** | $\underbrace{x+x+\cdots+x}_{n\text{ times}}=nx$ |

**Proof of (a):** Let $z=0x$. Then $z+z=0x+0x=(0+0)x=0x=z$. Adding $-z$ gives $z=O$.

**Proof of (b):** Let $z=aO$. Then $z+z=aO+aO=a(O+O)=aO=z$. Hence $z=O$.

**Proof of (c):** Let $z=(-a)x$. Then $z+ax=(-a+a)x=0x=O$, so $z=-(ax)$. Similarly $a(-x)=-(ax)$.


## 15.5 Subspaces of a Linear Space

### 15.5.1 Definition

- Let $V$ be a linear space and $S$ a nonempty subset of $V$.
- If $S$ is itself a linear space under the same operations, $S$ is called a **subspace** of $V$.

### 15.5.2 Theorem 15.4 — Subspace Criterion

Let $S$ be a nonempty subset of a linear space $V$. Then $S$ is a subspace **if and only if** $S$ satisfies the **closure axioms** (Axioms 1 and 2).

**Proof sketch:**
- If $S$ is a subspace, it satisfies all axioms, hence closure.
- Conversely, suppose $S$ satisfies closure. Axioms 3, 4, 7–10 hold automatically in $S$ because they hold in $V$.
- Need to verify Axioms 5 and 6:
  - For any $x\in S$: by closure, $0x\in S$. But $0x=O$, so $O\in S$.
  - Also $(-1)x\in S$, and $x+(-1)x=O$, so negatives exist in $S$.

### 15.5.3 Linear Combinations and Linear Span

- A **finite linear combination** of elements of $S$:
  $$
  x=\sum_{i=1}^k c_i x_i,\qquad x_i\in S,\ c_i\text{ scalars}.
  $$
- The set of all finite linear combinations of elements of $S$ satisfies the closure axioms, hence is a subspace.
- This subspace is called the **subspace spanned by $S$**, or the **linear span** of $S$, denoted $L(S)$.
- If $S$ is empty, define $L(S)=\{O\}$.

### 15.5.4 Examples

- $V_2$ is spanned by $\{\boldsymbol{i},\boldsymbol{j}\}$, also by $\{\boldsymbol{i},\boldsymbol{j},\boldsymbol{i}+\boldsymbol{j}\}$, also by $\{O,\boldsymbol{i},-\boldsymbol{i},\boldsymbol{j},-\boldsymbol{j},\boldsymbol{i}+\boldsymbol{j}\}$.
- Polynomials of degree $\le n$ are spanned by $\{1,t,t^2,\dots,t^n\}$.
- All polynomials are spanned by $\{1,t,t^2,\dots\}$ (infinite set).

### 15.5.5 Toward Bases and Dimension

- Which spaces can be spanned by a **finite** set?
- What is the **smallest** number of elements needed?
- To answer these, we introduce: **dependence, independence, bases, and dimension**.
- These concepts extend the ideas from Chapter 12 ($V_n$) to general linear spaces.


## 15.6 Dependent and Independent Sets in a Linear Space

### 15.6.1 Definition

- A set $S$ in a linear space $V$ is **dependent** if there exist distinct $x_1,\dots,x_k\in S$ and scalars $c_1,\dots,c_k$, not all zero, such that:
  $$
  \sum_{i=1}^k c_i x_i = O.
  $$
- $S$ is **independent** if it is not dependent; equivalently:
  $$
  \sum_{i=1}^k c_i x_i = O \quad\Longrightarrow\quad c_1=c_2=\cdots=c_k=0.
  $$
- The definition applies to **infinite sets** as well as finite sets.

### 15.6.2 Elementary Examples

| Example | Statement |
|---------|-----------|
| **1** | If $T\subseteq S$ and $T$ is dependent, then $S$ is dependent. (Equivalently: every subset of an independent set is independent.) |
| **2** | If one element is a scalar multiple of another, $S$ is dependent. |
| **3** | If $O\in S$, then $S$ is dependent. |
| **4** | The empty set is independent. |

### 15.6.3 Examples in Function Spaces

**Example 5:** $u_1(t)=\cos^2 t$, $u_2(t)=\sin^2 t$, $u_3(t)=1$.
- Since $u_1+u_2-u_3=O$, these three functions are dependent.

**Example 6:** $u_k(t)=t^k$ ($k=0,1,2,\dots$).
- The set $\{u_0,u_1,u_2,\dots\}$ is **independent**.
- Proof: $\sum_{k=0}^n c_k t^k=0$ for all $t$ implies each $c_k=0$ (evaluate at $t=0$, differentiate repeatedly).
  (Equation 15.1)

**Example 7:** Exponential functions $u_k(x)=e^{a_k x}$ with distinct $a_k$.
- **Independent.** Proof by induction on $n$:
  1. Assume $\sum_{k=1}^n c_k e^{a_k x}=0$. (Equation 15.2)
  2. Let $a_M$ be the largest $a_k$. Multiply by $e^{-a_M x}$:
     $$
     \sum_{k=1}^n c_k e^{(a_k-a_M)x}=0.
     $$
     (Equation 15.3)
  3. As $x\to+\infty$, terms with $k\neq M$ tend to 0, so $c_M=0$.
  4. Apply induction hypothesis to remaining $n-1$ terms.

### 15.6.4 Theorem 15.5 — Dependence in Spanned Subspaces

Let $S$ be an independent set of $k$ elements in $V$, and let $L(S)$ be its span. Then **every set of $k+1$ elements in $L(S)$ is dependent**.

**Proof:**
- When $V=V_n$, this is Theorem 12.8.
- The proof of Theorem 12.8 uses only the fact that $V_n$ is a linear space, not any special property of $V_n$.
- Hence the same proof is valid for **any** linear space $V$.

## 15.7 Bases and Dimension

### 15.7.1 Finite Basis and Dimension

**Definition.** A finite set $S$ in a linear space $V$ is a **finite basis** for $V$ if $S$ is **independent** and **spans** $V$.

| Term | Condition |
|------|-----------|
| **Finite-dimensional** | $V$ has a finite basis, or $V=\{O\}$ |
| **Infinite-dimensional** | $V$ has no finite basis |

- By convention, $\dim\{O\}=0$.

**Theorem 15.6 (Uniqueness of basis size).** Let $V$ be finite-dimensional. Then **every finite basis for $V$ has the same number of elements**.

**Proof sketch:**
- Let bases $S$ ($k$ elements) and $T$ ($m$ elements).
- $S$ independent and spans $V$ $\Rightarrow$ every set of $k+1$ elements in $V$ is dependent (Theorem 15.5).
- $T$ is independent with $m$ elements $\Rightarrow m\le k$.
- Interchange roles $\Rightarrow k\le m$.
- Hence $k=m$.

**Definition.** If $V$ has a basis of $n$ elements, $n$ is the **dimension** of $V$, written $n=\dim V$.

### 15.7.2 Examples

| Space | Dimension | Basis |
|-------|-----------|-------|
| $V_n$ | $n$ | $n$ unit coordinate vectors |
| Polynomials of degree $\le n$ | $n+1$ | $\{1,t,t^2,\dots,t^n\}$ |
| Solutions of $y''-2y'-3y=0$ | $2$ | $\{e^{-x},e^{3x}\}$ |
| All polynomials $p(t)$ | **Infinite** | $\{1,t,t^2,\dots\}$ spans, but no finite set spans |

### 15.7.3 Theorem 15.7 — Properties of Bases

Let $V$ be finite-dimensional with $\dim V=n$.

**(a) Extension.** Any independent set in $V$ is a subset of some basis for $V$.

**(b) Criterion.** Any set of $n$ independent elements in $V$ is a basis for $V$.

**Proof sketch:** Identical to parts (b) and (c) of Theorem 12.10.

### 15.7.4 Ordered Basis and Components

Let $(e_1,\dots,e_n)$ be an **ordered basis** (elements taken in a given order).

- Every $x\in V$ has a unique representation:
  $$
  x=\sum_{i=1}^n c_i e_i. \tag{15.4}
  $$
- The $n$-tuple $(c_1,\dots,c_n)$ is **uniquely determined** by $x$.
  - Proof of uniqueness: If $x=\sum d_i e_i$, then $\sum(c_i-d_i)e_i=O$. Independence implies $c_i=d_i$ for all $i$.
- $(c_1,\dots,c_n)$ are called the **components of $x$ relative to the ordered basis** $(e_1,\dots,e_n)$.

## 15.8 Inner Products, Euclidean Spaces, and Norms

### 15.8.1 Inner Product — Axiomatic Definition

In $V_n$, lengths and angles were defined via the dot product. We now generalize this to arbitrary linear spaces.

Recall the dot product in $V_n$:
$$
x\cdot y = \sum_{i=1}^n x_i y_i. \tag{15.5}
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

### 15.8.2 Examples of Inner Products

**Example 1:** In $V_n$, $(x,y)=x\cdot y$ (the usual dot product).

**Example 2:** In $V_2$, define $(x,y)=2x_1y_1+x_1y_2+x_2y_1+x_2y_2$.
- This is a valid inner product, showing a space may admit **more than one** inner product.

**Example 3:** In $C(a,b)$ (continuous real-valued functions on $[a,b]$):
$$
(f,g)=\int_a^b f(t)g(t)\,dt.
$$
- Analogous to (15.5): function values play the role of components, integration replaces summation.

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

### 15.8.3 Theorem 15.8 — Cauchy–Schwarz Inequality

In any Euclidean space $V$,
$$
|(x,y)|^2 \le (x,x)(y,y) \quad\text{for all }x,y\in V.
$$

- **Equality holds iff $x$ and $y$ are dependent** (i.e., one is a scalar multiple of the other).

**Proof sketch:**
- The proof for $V_n$ (Theorem 12.3) used only the axioms of the dot product (Theorem 12.2), not the specific formula.
- Hence the same proof is valid in **any** Euclidean space.
- In the complex case, one obtains $(x,y)(y,x)\le(x,x)(y,y)$, which is the same inequality since $(x,y)(y,x)=(x,y)\overline{(x,y)}=|(x,y)|^2$.

**Example.** In $C(a,b)$ with $(f,g)=\int_a^b f(t)g(t)\,dt$, the inequality becomes:
$$
\left(\int_a^b f(t)g(t)\,dt\right)^2 \le \left(\int_a^b f^2(t)\,dt\right)\left(\int_a^b g^2(t)\,dt\right).
$$

### 15.8.4 Norm

**Definition.** In a Euclidean space $V$, the **norm** of $x$ is
$$
\|x\| = (x,x)^{1/2}.
$$

In terms of norms, the Cauchy–Schwarz inequality becomes:
$$
|(x,y)| \le \|x\|\,\|y\|.
$$

- The norm depends on the choice of inner product (analogous to choice of scale/unit).

**Theorem 15.9 (Properties of norms).** In any Euclidean space, for all $x,y$ and scalars $c$:

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

### 15.8.5 Angle in a Real Euclidean Space

**Definition.** The **angle** $\theta$ ($0\le\theta\le\pi$) between nonzero $x$ and $y$ is defined by:
$$
\cos\theta = \frac{(x,y)}{\|x\|\,\|y\|}. \tag{15.6}
$$

- The Cauchy–Schwarz inequality guarantees the quotient lies in $[-1,1]$, so $\theta$ is uniquely determined.

## 15.9 Orthogonality in a Euclidean Space

### 15.9.1 Orthogonal and Orthonormal Sets

**Definition.** In a Euclidean space $V$:

| Term | Condition |
|------|-----------|
| **Orthogonal** | $(x,y)=0$ |
| **Orthogonal set** | $(x,y)=0$ for every pair of distinct $x,y\in S$ |
| **Orthonormal set** | Orthogonal set with $\|x\|=1$ for all $x\in S$ |

- The zero element is orthogonal to every element, and is the **only** element orthogonal to itself.

**Theorem 15.10 (Orthogonality implies independence).** In a Euclidean space $V$, every orthogonal set of **nonzero** elements is **independent**.

- In particular, in an $n$-dimensional Euclidean space, every orthogonal set of $n$ nonzero elements is a **basis**.

**Proof sketch:**
- Suppose $\sum_{i=1}^k c_i x_i=O$ with $x_i\in S$.
- Take inner product with $x_1$: $c_1(x_1,x_1)=0$.
- Since $x_1\neq O$, $(x_1,x_1)\neq 0$, so $c_1=0$.
- Repeat for each $x_j$ $\Rightarrow$ all $c_j=0$.
- If $|S|=n=\dim V$, then $S$ is a basis by Theorem 15.7(b).

### 15.9.2 Example — Trigonometric Functions in $C(0,2\pi)$

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

### 15.9.3 Components Relative to an Orthogonal Basis

**Theorem 15.11.** Let $V$ be finite-dimensional with $\dim V=n$, and let $S=\{e_1,\dots,e_n\}$ be an orthogonal basis. If $x=\sum_{i=1}^n c_i e_i$, then:
$$
c_j = \frac{(x,e_j)}{(e_j,e_j)} \quad\text{for }j=1,2,\dots,n. \tag{15.8}
$$

- In particular, if $S$ is **orthonormal**:
  $$
  c_j=(x,e_j). \tag{15.9}
  $$

- Equation (15.7) then becomes:
  $$
  x=\sum_{i=1}^n (x,e_i)e_i. \tag{15.10}
  $$

**Proof sketch:** Take inner product of $x=\sum c_i e_i$ with $e_j$; orthogonality kills all terms except $i=j$.

### 15.9.4 Parseval’s Formula

**Theorem 15.12.** Let $\{e_1,\dots,e_n\}$ be an orthonormal basis for $V$. Then for all $x,y\in V$:
$$
(x,y)=\sum_{i=1}^n (x,e_i)\overline{(y,e_i)}. \tag{15.11}
$$

- When $x=y$:
  $$
  \|x\|^2=\sum_{i=1}^n |(x,e_i)|^2. \tag{15.12}
  $$

**Proof sketch:** Expand $x$ and $y$ using (15.10) and apply linearity of the inner product; orthonormality yields the sum.

## 15.10 The Gram–Schmidt Process

### 15.10.1 Orthogonalization Theorem

Every finite-dimensional Euclidean space has an orthogonal basis. This follows from:

**Theorem 15.13 (Orthogonalization theorem).** Let $x_1,x_2,\dots$ be a finite or infinite sequence in a Euclidean space $V$, and let $L(x_1,\dots,x_k)$ denote the subspace spanned by the first $k$ elements. Then there exists a sequence $y_1,y_2,\dots$ in $V$ such that for each $k$:

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
  y_{r+1}=x_{r+1}-\sum_{i=1}^r a_i y_i, \tag{15.13}
  $$
  where $a_i$ are chosen to make $y_{r+1}$ orthogonal to each $y_j$ ($j\le r$).
- Taking inner product with $y_j$:
  $$
  (y_{r+1},y_j)=(x_{r+1},y_j)-a_j(y_j,y_j).
  $$
- If $y_j\neq O$, set:
  $$
  a_j=\frac{(x_{r+1},y_j)}{(y_j,y_j)}. \tag{15.14}
  $$
- If $y_j=O$, choose $a_j=0$.
- Then $y_{r+1}$ is orthogonal to $L(y_1,\dots,y_r)$, proving (a).
- Since $x_{r+1}$ and each $y_i$ lie in $L(x_1,\dots,x_{r+1})$, and conversely $x_{r+1}$ is a linear combination of $y_1,\dots,y_{r+1}$, we get (b).
- Uniqueness (c): any alternative $y'_{r+1}$ must lie in $L(y_1,\dots,y_{r+1})$ and be orthogonal to $L(y_1,\dots,y_r)$, hence is a scalar multiple of $y_{r+1}$.

### 15.10.2 The Gram–Schmidt Formulas

For an independent set $\{x_1,\dots,x_k\}$, the corresponding orthogonal set $\{y_1,\dots,y_k\}$ is given by:
$$
y_1=x_1,\qquad y_{r+1}=x_{r+1}-\sum_{i=1}^r\frac{(x_{r+1},y_i)}{(y_i,y_i)}y_i \quad (r=1,2,\dots,k-1). \tag{15.15}
$$

- If some $y_{r+1}=O$, then $x_{r+1}$ is a linear combination of $x_1,\dots,x_r$, so the original set is dependent.
- If $\{x_1,\dots,x_k\}$ is independent, then all $y_i$ are nonzero, and $\{y_1,\dots,y_k\}$ is an orthogonal basis for the same subspace.
- An **orthonormal basis** is obtained by normalizing: $e_i=y_i/\|y_i\|$.

**Corollary (Theorem 15.14).** Every finite-dimensional Euclidean space has an **orthonormal basis**.

**Projection.** For $y\neq O$, the element $\frac{(x,y)}{(y,y)}y$ is called the **projection of $x$ along $y$**. The Gram–Schmidt process constructs $y_{r+1}$ by subtracting from $x_{r+1}$ its projection along each earlier $y_i$.

### 15.10.3 Example in $V_4$

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

### 15.10.4 Example — Legendre Polynomials

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

## 15.11 Orthogonal Complements and Projections

### 15.11.1 The Approximation Problem

Let $V$ be a Euclidean space and $S$ a finite-dimensional subspace. Given $x\in V$, find $s\in S$ minimizing the distance $\|x-s\|$.

- If $x\in S$, then $s=x$.
- Geometrically (in $V_3$ with $S$ a plane through the origin), the nearest point is obtained by dropping a perpendicular from $x$ to $S$.

### 15.11.2 Orthogonal Complement

**Definition.** An element in $V$ is **orthogonal to $S$** if it is orthogonal to every element of $S$. The set of all such elements is denoted $S^\perp$ (read "$S$ perpendicular").

- $S^\perp$ is a subspace of $V$, whether or not $S$ is.
- If $S$ is a subspace, $S^\perp$ is called the **orthogonal complement** of $S$.
- Example: If $S$ is a plane through the origin in $V_3$, then $S^\perp$ is the line through the origin perpendicular to $S$.

### 15.11.3 Theorem 15.15 — Orthogonal Decomposition

Let $V$ be a Euclidean space and $S$ a finite-dimensional subspace. Then **every** $x\in V$ can be represented **uniquely** as:
$$
x = s + s^\perp, \quad\text{where }s\in S\text{ and }s^\perp\in S^\perp. \tag{15.16}
$$

Moreover, the **Pythagorean formula** holds:
$$
\|x\|^2 = \|s\|^2 + \|s^\perp\|^2. \tag{15.17}
$$

**Proof sketch:**
- Since $S$ is finite-dimensional, it has an orthonormal basis $\{e_1,\dots,e_n\}$.
- Define:
  $$
  s = \sum_{i=1}^n (x,e_i)e_i, \qquad s^\perp = x - s. \tag{15.18}
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

### 15.11.4 Projection onto a Subspace

**Definition.** Let $S$ be a finite-dimensional subspace with orthonormal basis $\{e_1,\dots,e_n\}$. For $x\in V$, the element
$$
s = \sum_{i=1}^n (x,e_i)e_i
$$
is called the **projection of $x$ on the subspace $S$**.

- This projection is the unique element in $S$ that solves the approximation problem (minimizing $\|x-s\|$).
- The proof of this optimality property follows from the orthogonal decomposition theorem.

## 15.12 Best Approximation in a Finite-Dimensional Subspace

### 15.12.1 Theorem 15.16 — Approximation Theorem

Let $S$ be a finite-dimensional subspace of a Euclidean space $V$, and let $x\in V$. Then the **projection** $s$ of $x$ on $S$ is nearer to $x$ than any other element of $S$:
$$
\|x-s\| \le \|x-t\| \quad\text{for all }t\in S,
$$
with equality if and only if $t=s$.

**Proof:**
- By Theorem 15.15, $x=s+s^\perp$ with $s\in S$ and $s^\perp\in S^\perp$.
- For any $t\in S$: $x-t=(x-s)+(s-t)$.
- Since $s-t\in S$ and $x-s=s^\perp\in S^\perp$, this is an orthogonal decomposition.
- By the Pythagorean formula:
  $$
  \|x-t\|^2 = \|x-s\|^2 + \|s-t\|^2 \ge \|x-s\|^2.
  $$
- Equality holds iff $\|s-t\|=0$, i.e., $t=s$.

### 15.12.2 Example — Trigonometric Polynomial Approximation

Let $V=C(0,2\pi)$ with $(f,g)=\int_0^{2\pi}f(x)g(x)\,dx$, and let $S$ be the subspace spanned by the orthonormal set:
$$
\varphi_0(x)=\frac{1}{\sqrt{2\pi}},\quad \varphi_{2k-1}(x)=\frac{\cos kx}{\sqrt{\pi}},\quad \varphi_{2k}(x)=\frac{\sin kx}{\sqrt{\pi}} \quad (k\ge 1). \tag{15.20}
$$

- The $2n+1$ elements $\varphi_0,\dots,\varphi_{2n}$ span a subspace of dimension $2n+1$.
- Elements of $S$ are called **trigonometric polynomials**.
- For $f\in C(0,2\pi)$, the projection of $f$ on $S$ is:
  $$
  f_n = \sum_{k=0}^{2n}(f,\varphi_k)\varphi_k, \quad\text{where }(f,\varphi_k)=\int_0^{2\pi}f(x)\varphi_k(x)\,dx. \tag{15.21}
  $$
- The numbers $(f,\varphi_k)$ are the **Fourier coefficients** of $f$.
- Rewriting (15.21) in standard form:
  $$
  f_n(x) = \tfrac{1}{2}a_0 + \sum_{k=1}^n\bigl(a_k\cos kx + b_k\sin kx\bigr), \tag{15.22}
  $$
  where
  $$
  a_k = \frac{1}{\pi}\int_0^{2\pi}f(x)\cos kx\,dx, \qquad b_k = \frac{1}{\pi}\int_0^{2\pi}f(x)\sin kx\,dx.
  $$

### 15.12.3 Example — Polynomial Approximation with Legendre Polynomials

Let $V=C(-1,1)$ with $(f,g)=\int_{-1}^1 f(x)g(x)\,dx$, and let $S$ be spanned by the normalized Legendre polynomials $\varphi_0,\dots,\varphi_n$ (dimension $n+1$).

- The projection of $f$ on $S$ is $f_n=\sum_{k=0}^n(f,\varphi_k)\varphi_k$.
- This is the polynomial of degree $\le n$ minimizing $\|f-f_n\|$.

**Example:** $f(x)=\sin\pi x$.
- $(f,\varphi_0)=0$ (odd function).
- $(f,\varphi_1)=\int_{-1}^1\sqrt{\frac{3}{2}}t\sin\pi t\,dt=\sqrt{\frac{3}{2}}\frac{2}{\pi}$.
- The best linear approximation:
  $$
  f_1(t) = \sqrt{\frac{3}{2}}\frac{2}{\pi}\,\varphi_1(t) = \frac{3}{\pi}t.
  $$
- Since $(f,\varphi_2)=0$, this is also the best **quadratic** approximation.

[<- Previous: 14. Calculus of Vector-Valued Functions](14-calculus-of-vector-valued-functions.md) | [Next: 16. Linear Transformations and Matrices ->](16-linear-transformations-and-matrices.md)
