[← Previous: 8. Eigenvectors and Eigenvalues](08-eigenvectors-and-eigenvalues.md) | [Next: 10. Triangulation of Matrices and Linear Maps →](10-triangulation-of-matrices-and-linear-maps.md)

# 9. Polynomials and Matrices

## 9.1 Polynomials

Let $K$ be a field. A **polynomial** over $K$ is a formal expression:

$$
f(t) = a_n t^n + a_{n-1} t^{n-1} + \cdots + a_0,
$$

where $a_i \in K$ and $t$ is a variable.

### 9.1.1 Operations on Polynomials

Given $g(t) = b_m t^m + \cdots + b_0$ (assume $n \ge m$ by padding with zeros):

| Operation | Formula |
|-----------|---------|
| **Sum** | $(f+g)(t) = (a_n+b_n)t^n + \cdots + (a_0+b_0)$ |
| **Scalar multiple** | $(cf)(t) = ca_n t^n + \cdots + ca_0$ for $c \in K$ |
| **Product** | $(fg)(t) = c_{n+m}t^{n+m} + \cdots + c_0$, where $c_k = \sum_{i=0}^k a_i b_{k-i}$ |

Thus polynomials form a vector space over $K$.

### 9.1.2 Degree and Terminology

For $f(t) = a_n t^n + \cdots + a_0$ with $a_n \neq 0$:

| Term | Definition |
|------|------------|
| **Coefficients** | $a_0, a_1, \dots, a_n$ |
| **Degree** | $\deg f = n$ |
| **Leading coefficient** | $a_n$ |
| **Constant term** | $a_0$ |
| **Linear polynomial** | Polynomial of degree 1 |

For the zero polynomial: $\deg 0 = -\infty$, with conventions:

$$
-\infty + (-\infty) = -\infty, \qquad -\infty + a = -\infty, \qquad -\infty < a.
$$

**Theorem 1.1.** Let $f, g$ be polynomials over $K$. Then:

$$
\deg(fg) = \deg f + \deg g.
$$

**Proof.** If $f(t) = a_n t^n + \cdots$ ($a_n \neq 0$) and $g(t) = b_m t^m + \cdots$ ($b_m \neq 0$), then $f(t)g(t) = a_n b_m t^{n+m} + \text{lower degree terms}$, with $a_n b_m \neq 0$. Hence $\deg(fg) = n+m$. If $f=0$ or $g=0$, the convention on $-\infty$ gives the result.

A number $\alpha$ is a **root** of $f$ if $f(\alpha) = 0$.

### 9.1.3 Factorization over $\mathbf{C}$

**Theorem 1.2.** Let $f$ be a polynomial with complex coefficients, $\deg f \ge 1$. Then $f$ has a root in $\mathbf{C}$.

> (Fundamental theorem of algebra. Proof postponed to an appendix.)

**Theorem 1.3.** Let $f$ be a polynomial with complex coefficients, leading coefficient $1$, and $\deg f = n \ge 1$. Then there exist complex numbers $\alpha_1, \dots, \alpha_n$ such that:

$$
f(t) = (t-\alpha_1)\cdots(t-\alpha_n).
$$

The numbers $\alpha_1, \dots, \alpha_n$ are uniquely determined up to a permutation. Every root $\alpha$ of $f$ equals some $\alpha_i$, and conversely.

> (Proof given in Chapter XI.)

Let $\alpha_1, \dots, \alpha_r$ be the distinct roots of $f$ in $\mathbf{C}$. Then:

$$
f(t) = (t-\alpha_1)^{m_1} \cdots (t-\alpha_r)^{m_r},
$$

with integers $m_1, \dots, m_r > 0$, uniquely determined. The integer $m_i$ is called the **multiplicity** of $\alpha_i$ in $f$.


## 9.2 Polynomials of Matrices and Linear Maps

The set of polynomials with coefficients in $K$ is denoted $K[t]$.

Let $A$ be a square matrix with coefficients in $K$. For $f \in K[t]$ with $f(t) = a_n t^n + \cdots + a_0$, define:

$$
f(A) = a_n A^n + \cdots + a_0 I.
$$

### 9.2.1 Basic Properties

**Example 1.** Let $f(t) = 3t^2 - 2t + 5$ and $A = \begin{pmatrix}1&-1\\2&0\end{pmatrix}$. Then:

$$
f(A) = 3A^2 - 2A + 5I = \begin{pmatrix}0&-1\\2&-1\end{pmatrix}.
$$

**Theorem 2.1.** Let $f, g \in K[t]$ and $A$ a square matrix over $K$. Then:

| Property | Statement |
|----------|-----------|
| **Sum** | $(f+g)(A) = f(A) + g(A)$ |
| **Product** | $(fg)(A) = f(A)g(A)$ |
| **Scalar** | $(cf)(A) = cf(A)$ for $c \in K$ |

**Proof of product.** If $(fg)(t) = \sum_k c_k t^k$ with $c_k = \sum_{i=0}^k a_i b_{k-i}$, then:

$$
(fg)(A) = \sum_k c_k A^k = \sum_{i,j} a_i b_j A^{i+j} = \left(\sum_i a_i A^i\right)\left(\sum_j b_j A^j\right) = f(A)g(A).
$$

**Example 2.** If $f(t) = (t-1)(t+3) = t^2 + 2t - 3$, then:

$$
f(A) = (A-I)(A+3I) = A^2 + 2A - 3I.
$$

**Example 3.** If $f(t) = (t-\alpha_1)\cdots(t-\alpha_n)$, then:

$$
f(A) = (A-\alpha_1 I)\cdots(A-\alpha_n I).
$$

### 9.2.2 Polynomials of Linear Maps

Let $V$ be a vector space over $K$ and $A: V \to V$ an operator. Define $A^n$ by iteration ($A^0 = I$). Then $A^{m+n} = A^m A^n$.

If $f \in K[t]$, we define $f(A)$ in the same way. The same rules as in Theorem 2.1 hold for operators.

### 9.2.3 Existence of an Annihilating Polynomial

**Theorem 2.2.** Let $A$ be an $n \times n$ matrix over a field $K$. Then there exists a non-zero polynomial $f \in K[t]$ such that $f(A) = O$.

**Proof.** The space of $n \times n$ matrices over $K$ has dimension $n^2$. Hence the powers $I, A, A^2, \dots, A^N$ are linearly dependent for $N > n^2$. Thus there exist $a_0, \dots, a_N \in K$, not all zero, with:

$$
a_N A^N + \cdots + a_0 I = O.
$$

Let $f(t) = a_N t^N + \cdots + a_0$.

> **Note.** Theorem 2.2 also holds for linear maps on finite dimensional vector spaces. Later in Chapter X, §2, an explicit polynomial $P(t)$ with $P(A) = O$ will be constructed (the characteristic polynomial). By dividing by the leading coefficient, one may assume $f$ is monic.

[← Previous: 8. Eigenvectors and Eigenvalues](08-eigenvectors-and-eigenvalues.md) | [Next: 10. Triangulation of Matrices and Linear Maps →](10-triangulation-of-matrices-and-linear-maps.md)
