[<- Previous: 5. Scalar Products and Orthogonality](05-scalar-products-and-orthogonality.md) | [Next: 7. Symmetric, Hermitian, and Unitary Operators ->](07-symmetric-hermitian-and-unitary-operators.md)

# 6. Determinants

## 6.1 Determinants of Order 2

### 6.1.1 Definition

For a $2 \times 2$ matrix over a field $K$:
$$
A = \begin{pmatrix} a & b \\ c & d \end{pmatrix},
$$
its **determinant** is:
$$
\begin{vmatrix} a & b \\ c & d \end{vmatrix} = ad - bc.
$$

Notation: $D(A)$, $\operatorname{Det}(A)$, or $D(A^1, A^2)$ (viewed as a function of the two columns).

**Examples:**
- $\operatorname{Det}\begin{pmatrix} 2 & 1 \\ 1 & 4 \end{pmatrix} = 2 \cdot 4 - 1 \cdot 1 = 7$
- $\operatorname{Det}\begin{pmatrix} -2 & -3 \\ 4 & 5 \end{pmatrix} = (-2) \cdot 5 - (-3) \cdot 4 = 2$

### 6.1.2 Properties

As a function of the column vectors, the determinant is **bilinear**:

$$
\operatorname{Det}\begin{pmatrix} a & b + b' \\ c & d + d' \end{pmatrix} = \operatorname{Det}\begin{pmatrix} a & b \\ c & d \end{pmatrix} + \operatorname{Det}\begin{pmatrix} a & b' \\ c & d' \end{pmatrix},
\qquad
\operatorname{Det}\begin{pmatrix} a & tb \\ c & td \end{pmatrix} = t \, \operatorname{Det}\begin{pmatrix} a & b \\ c & d \end{pmatrix}.
$$

(Analogous properties hold for the first column.)

| Property | Statement |
|----------|-----------|
| Equal columns | If two columns are equal, $\operatorname{Det}(A) = 0$. |
| Unit matrix | $\operatorname{Det}(I) = \operatorname{Det}\begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = 1$. |
| Column addition | Adding a multiple of one column to the other does not change $\operatorname{Det}(A)$. |
| Column swap | Interchanging two columns changes the sign: $\operatorname{Det}\begin{pmatrix} a & b \\ c & d \end{pmatrix} = -\operatorname{Det}\begin{pmatrix} b & a \\ d & c \end{pmatrix}$. |
| Transpose | $\operatorname{Det}(A) = \operatorname{Det}({}^tA)$, i.e. $\begin{vmatrix} a & b \\ c & d \end{vmatrix} = \begin{vmatrix} a & c \\ b & d \end{vmatrix}$. |

### 6.1.3 Linear Dependence

The vectors $\begin{pmatrix} a \\ c \end{pmatrix}$ and $\begin{pmatrix} b \\ d \end{pmatrix}$ are linearly dependent **iff** $ad - bc = 0$.

**Proof.** If $x a + y b = 0$ and $x c + y d = 0$ with $x, y$ not both $0$:
- Multiply the first by $d$, the second by $b$, and subtract: $x(ad - bc) = 0$. Since $x \neq 0$, we get $ad - bc = 0$.
- Conversely, if $ad - bc = 0$ and not both vectors are zero, say $a \neq 0$. Let $y = -a$ and $x = b$. Then $x a + y b = b a - a b = 0$ and $x c + y d = b c - a d = -(ad - bc) = 0$. Hence the columns are dependent.

## 6.2 Existence of Determinants

### 6.2.1 Determinants of Order 3

For a $3 \times 3$ matrix $A = (a_{ij})$, define its determinant by **expansion along the first row**:
$$
\operatorname{Det}(A) = a_{11} \begin{vmatrix} a_{22} & a_{23} \\ a_{32} & a_{33} \end{vmatrix} - a_{12} \begin{vmatrix} a_{21} & a_{23} \\ a_{31} & a_{33} \end{vmatrix} + a_{13} \begin{vmatrix} a_{21} & a_{22} \\ a_{31} & a_{32} \end{vmatrix}.
$$

Let $A_{ij}$ be the $(n-1) \times (n-1)$ matrix obtained by deleting the $i$-th row and $j$-th column of $A$. Then:
$$
\operatorname{Det}(A) = a_{11} \operatorname{Det}(A_{11}) - a_{12} \operatorname{Det}(A_{12}) + a_{13} \operatorname{Det}(A_{13}).
$$

**Example 1.** Let:
$$
A = \begin{pmatrix} 2 & 1 & 0 \\ 1 & 1 & 4 \\ -3 & 2 & 5 \end{pmatrix}.
$$
Then $A_{11} = \begin{pmatrix} 1 & 4 \\ 2 & 5 \end{pmatrix}$, $A_{12} = \begin{pmatrix} 1 & 4 \\ -3 & 5 \end{pmatrix}$, $A_{13} = \begin{pmatrix} 1 & 1 \\ -3 & 2 \end{pmatrix}$, and:
$$
\operatorname{Det}(A) = 2(5 - 8) - 1(5 + 12) + 0 = -23.
$$

### 6.2.2 Properties

**Theorem 2.1.** The determinant satisfies:

1. **Multilinear:** As a function of each column, $D$ is linear. If $A^j = C + C'$, then:
   $$
   D(A^1, \dots, C + C', \dots, A^n) = D(A^1, \dots, C, \dots, A^n) + D(A^1, \dots, C', \dots, A^n),
   $$
   and $D(A^1, \dots, tA^j, \dots, A^n) = t \, D(A^1, \dots, A^j, \dots, A^n)$.

2. **Alternating:** If two adjacent columns are equal ($A^j = A^{j+1}$), then $D(A) = 0$.

3. **Normalization:** $D(I) = 1$.

> In the $3 \times 3$ case, these are proved by direct computation using the definition (*).

### 6.2.3 Expansion by Any Row or Column

Expansion can be done along any row, with signs following the chessboard pattern:
$$
\begin{pmatrix} + & - & + \\ - & + & - \\ + & - & + \end{pmatrix}.
$$

For example, along the second row:
$$
\operatorname{Det}(A) = -a_{21} \operatorname{Det}(A_{21}) + a_{22} \operatorname{Det}(A_{22}) - a_{23} \operatorname{Det}(A_{23}).
$$

Expanding all terms gives the explicit formula:
$$
\operatorname{Det}(A) = a_{11}a_{22}a_{33} - a_{11}a_{32}a_{23} - a_{12}a_{21}a_{33} + a_{12}a_{23}a_{31} + a_{13}a_{21}a_{32} - a_{13}a_{22}a_{31}.
$$

**Theorem 2.2.** The determinant satisfies expansion according to rows and columns, and $\operatorname{Det}(A) = \operatorname{Det}({}^tA)$.

**Example 2.** Compute:
$$
\begin{vmatrix} 3 & 0 & 1 \\ 1 & 2 & 5 \\ -1 & 4 & 2 \end{vmatrix}
$$
by the second column: $2 \begin{vmatrix} 3 & 1 \\ -1 & 2 \end{vmatrix} - 4 \begin{vmatrix} 3 & 1 \\ 1 & 5 \end{vmatrix} = 2(7) - 4(14) = -42$.

### 6.2.4 The n×n Case

A function $F: K^n \times \cdots \times K^n \to K$ is **multilinear** if it is linear in each variable when the others are fixed. It is **alternating** if $F(\dots, A^j, A^j, \dots) = 0$ whenever two adjacent arguments are equal.

**Theorem 2.3.** There exists a multilinear alternating function $F: K^n \times \cdots \times K^n \to K$ with $F(I) = 1$. Such a function is **uniquely** determined by these three properties.

**Existence (by induction).** Assume determinants defined for $(n-1) \times (n-1)$ matrices. For fixed $i$ ($1 \le i \le n$), define:
$$
D(A) = \sum_{j=1}^n (-1)^{i+j} a_{ij} \operatorname{Det}(A_{ij}).
$$
This is the **expansion according to the $i$-th row**. One verifies that $D$ satisfies properties 1, 2, and 3.

**Theorem 2.4.** Determinants satisfy expansion according to rows and columns. For any column $A^j$:
$$
D(A) = \sum_{i=1}^n (-1)^{i+j} a_{ij} D(A_{ij}).
$$

**Example 3.** Compute:
$$
\begin{vmatrix} 1 & 2 & 1 \\ -1 & 3 & 1 \\ 0 & 1 & 5 \end{vmatrix}
$$
by the third row (which has a zero):
$$
(-1)^{3+1} \cdot 0 \cdot \operatorname{Det}(A_{31}) + (-1)^{3+2} \cdot 1 \cdot \begin{vmatrix} 1 & 1 \\ -1 & 1 \end{vmatrix} + (-1)^{3+3} \cdot 5 \cdot \begin{vmatrix} 1 & 2 \\ -1 & 3 \end{vmatrix} = -1(2) + 5(5) = 23.
$$

## 6.3 Additional Properties of Determinants

### 6.3.1 Deduced Properties

The following properties follow from multilinearity, alternation, and normalization (Theorem 2.1):

**4. Column interchange.** If the $i$-th and $j$-th columns ($i \neq j$) are interchanged, the determinant changes by a sign.

**Proof.** First for adjacent columns $j, j+1$: in $D(\dots, A^j + A^{j+1}, A^j + A^{j+1}, \dots)$, expand by multilinearity. The two terms with equal columns vanish by property 2, leaving:
$$
0 = D(\dots, A^{j+1}, A^j, \dots) + D(\dots, A^j, A^{j+1}, \dots).
$$
For non-adjacent columns, use successive adjacent swaps.

**5. Equal columns.** If any two columns $A^i = A^j$ ($i \neq j$), then $D(A) = 0$.

**Proof.** Bring the equal columns together by adjacent interchanges (each changes sign) until they are adjacent; then apply property 2.

**6. Column addition.** Adding a scalar multiple of one column to another does not change the determinant.

**Proof.** $D(\dots, A^k + tA^j, \dots) = D(\dots, A^k, \dots) + t D(\dots, A^j, \dots)$. In the second term, $A^j$ appears in both the $k$-th and $j$-th places, so it equals 0 by property 5.

### 6.3.2 Efficient Computation

Using property 6 (valid for rows too, since $\operatorname{Det}(A) = \operatorname{Det}({}^tA)$), we simplify determinants by creating zeros. The goal is to make all but one element in a column (or row) equal to 0, then expand along that column.

**Example 1.** Compute:
$$
\begin{vmatrix} 3 & 0 & 1 \\ 1 & 2 & 5 \\ -1 & 4 & 2 \end{vmatrix}
$$
Subtract twice row 2 from row 3:
$$
\begin{vmatrix} 3 & 0 & 1 \\ 1 & 2 & 5 \\ -3 & 0 & -8 \end{vmatrix}.
$$
Expand along column 2 (only one non-zero term):
$$
2 \begin{vmatrix} 3 & 1 \\ -3 & -8 \end{vmatrix} = 2(-24 + 3) = -42.
$$

**Example 2.** Compute:
$$
\begin{vmatrix} 1 & 3 & 1 & 1 \\ 2 & 1 & 5 & 2 \\ 1 & -1 & 2 & 3 \\ 4 & 1 & -3 & 7 \end{vmatrix}
$$
Add row 3 to rows 2 and 4; add $3 \times$ row 3 to row 1:
$$
\begin{vmatrix} 4 & 0 & 7 & 10 \\ 3 & 0 & 7 & 5 \\ 1 & -1 & 2 & 3 \\ 5 & 0 & -1 & 10 \end{vmatrix}.
$$
Expand along column 2:
$$
(-1)^{3+2}(-1) \begin{vmatrix} 4 & 7 & 10 \\ 3 & 7 & 5 \\ 5 & -1 & 10 \end{vmatrix} = \begin{vmatrix} 4 & 7 & 10 \\ 3 & 7 & 5 \\ 5 & -1 & 10 \end{vmatrix}.
$$
Subtract $2 \times$ row 2 from rows 1 and 3:
$$
\begin{vmatrix} -2 & -7 & 0 \\ 3 & 7 & 5 \\ -1 & -15 & 0 \end{vmatrix}.
$$
Expand along column 3:
$$
(-1)^{2+3} \cdot 5 \begin{vmatrix} -2 & -7 \\ -1 & -15 \end{vmatrix} = -5(30 - 7) = -115.
$$

## 6.4 Cramer's Rule

### 6.4.1 Theorem 4.1

**Theorem 4.1 (Cramer's rule).** Let $A^1, \dots, A^n$ be column vectors with $D(A^1, \dots, A^n) \neq 0$. Let $B$ be a column vector. If $x_1 A^1 + \cdots + x_n A^n = B$, then for each $j$:
$$
x_j = \frac{D(A^1, \dots, B, \dots, A^n)}{D(A^1, \dots, A^n)},
$$
where $B$ occurs in the $j$-th column.

**Proof.** Replace the $j$-th column of $A$ by $B$:
$$
D(A^1, \dots, B, \dots, A^n) = D(A^1, \dots, x_1 A^1 + \cdots + x_n A^n, \dots, A^n).
$$
By multilinearity (property 1), this equals:
$$
x_1 D(A^1, \dots, A^1, \dots, A^n) + \cdots + x_j D(A^1, \dots, A^n) + \cdots + x_n D(A^1, \dots, A^n, \dots, A^n).
$$
Every term except the $j$-th has two equal columns, so equals 0 by property 5. The $j$-th term is $x_j D(A^1, \dots, A^n)$. Hence:
$$
D(A^1, \dots, B, \dots, A^n) = x_j D(A^1, \dots, A^n).
$$

### 6.4.2 Example

Solve:
$$
\begin{cases} 3x + 2y + 4z = 1 \\ 2x - y + z = 0 \\ x + 2y + 3z = 1 \end{cases}
$$

Then:
$$
x = \frac{\begin{vmatrix} 1 \u0026 2 \u0026 4 \\ 0 \u0026 -1 \u0026 1 \\ 1 \u0026 2 \u0026 3 \end{vmatrix}}{\begin{vmatrix} 3 \u0026 2 \u0026 4 \\ 2 \u0026 -1 \u0026 1 \\ 1 \u0026 2 \u0026 3 \end{vmatrix}}, \quad
y = \frac{\begin{vmatrix} 3 \u0026 1 \u0026 4 \\ 2 \u0026 0 \u0026 1 \\ 1 \u0026 1 \u0026 3 \end{vmatrix}}{\begin{vmatrix} 3 \u0026 2 \u0026 4 \\ 2 \u0026 -1 \u0026 1 \\ 1 \u0026 2 \u0026 3 \end{vmatrix}}, \quad
z = \frac{\begin{vmatrix} 3 \u0026 2 \u0026 1 \\ 2 \u0026 -1 \u0026 0 \\ 1 \u0026 2 \u0026 1 \end{vmatrix}}{\begin{vmatrix} 3 \u0026 2 \u0026 4 \\ 2 \u0026 -1 \u0026 1 \\ 1 \u0026 2 \u0026 3 \end{vmatrix}}.
$$

The column $B = \begin{pmatrix} 1 \\ 0 \\ 1 \end{pmatrix}$ shifts from the first column (for $x$) to the second (for $y$) to the third (for $z$). Computing gives:
$$
x = -\tfrac{1}{5}, \qquad y = 0, \qquad z = \tfrac{2}{5}.
$$

### 6.4.3 Linear Independence Criterion

**Theorem 4.2.** Let $A^1, \dots, A^n$ be column vectors in $K^n$.
- If they are linearly dependent, then $D(A^1, \dots, A^n) = 0$.
- If $D(A^1, \dots, A^n) \neq 0$, then they are linearly independent.

**Proof.** If dependent, there exist $x_1, \dots, x_n$ not all $0$ with $\sum x_k A^k = O$. Suppose $x_j \neq 0$. Then $A^j = \sum_{k \neq j} y_k A^k$. By multilinearity:
$$
D(A^1, \dots, A^n) = \sum_{k \neq j} y_k D(A^1, \dots, A^k, \dots, A^n) = 0,
$$
since each determinant has the $k$-th column equal to the $j$-th column.

**Corollary 4.3.** If $D(A^1, \dots, A^n) \neq 0$, then for any $B \in K^n$ there exist $x_1, \dots, x_n$ such that $x_1 A^1 + \cdots + x_n A^n = B$.

**Proof.** The columns are linearly independent, hence form a basis of $K^n$.

> In terms of linear equations: if a system of $n$ equations in $n$ unknowns has coefficient matrix with non-zero determinant, then it has a unique solution, given by Cramer's rule.

**Theorem 4.4.** $D(A^1, \dots, A^n) = 0$ if and only if $A^1, \dots, A^n$ are linearly dependent.

## 6.5 Triangulation of a Matrix by Column Operations

### 6.5.1 Column Operations

The two column operations used for computing determinants:

| Operation | Description |
|-----------|-------------|
| **COL 1** | Add a scalar multiple of one column to another. |
| **COL 2** | Interchange two columns. |

Matrices $A$ and $B$ are **column equivalent** if $B$ is obtained from $A$ by a succession of COL 1 and COL 2 operations.

**Proposition 5.1.** If $A$ and $B$ are column equivalent, then:
- $\operatorname{rank} A = \operatorname{rank} B$
- $A$ is invertible $\iff$ $B$ is invertible
- $\operatorname{Det}(A) = 0 \iff \operatorname{Det}(B) = 0$

**Proof.** Interchanging columns does not change the column space. Adding $x A^2$ to $A^1$ leaves the span of $\{A^1 + xA^2, A^2, \dots, A^n\}$ equal to the span of $\{A^1, \dots, A^n\}$. Hence column spaces are equal, so ranks are equal. The determinant changes only by a sign under COL 2 and is unchanged under COL 1, so $\operatorname{Det}(A) = 0 \iff \operatorname{Det}(B) = 0$. If $A$ is invertible, $\operatorname{rank} A = n$, so $\operatorname{rank} B = n$, hence $B$ is invertible.

### 6.5.2 Triangular Form

**Theorem 5.2.** Every $n \times n$ matrix $A$ is column equivalent to a lower triangular matrix:
$$
B = \begin{pmatrix} b_{11} & 0 & \cdots & 0 \\ b_{21} & b_{22} & \cdots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ b_{n1} & b_{n2} & \cdots & b_{nn} \end{pmatrix}.
$$

**Proof (by induction on $n$).** For $n = 1$, trivial. For $n > 1$:
- If the first row of $A$ is all zeros, apply induction to the bottom-right $(n-1) \times (n-1)$ block.
- Otherwise, use column interchanges (COL 2) to make $a_{11} \neq 0$. Then add suitable multiples of the first column to the others (COL 1) to zero out $b_{12}, \dots, b_{1n}$. Now apply induction to the submatrix obtained by deleting the first row and first column.

### 6.5.3 Invertibility Criterion

**Theorem 5.3.** Let $A = (A^1, \dots, A^n)$ be a square matrix. The following are equivalent:

| Condition | Statement |
|-----------|-----------|
| **(a)** | $A$ is invertible. |
| **(b)** | The columns $A^1, \dots, A^n$ are linearly independent. |
| **(c)** | $D(A) \neq 0$. |

**Proof.** (a) $\iff$ (b) was proved in Chapter IV, Theorem 2.2. By Proposition 5.1 and Theorem 5.2, we may assume $A$ is triangular. Then $\operatorname{Det}(A)$ is the product of the diagonal elements, which is $0$ iff some diagonal element is $0$, equivalently the columns are dependent.

## 6.6 Permutations

### 6.6.1 Definition

Let $J_n = \{1, \dots, n\}$. A **permutation** of $J_n$ is a bijection:

$$
\sigma: J_n \to J_n.
$$

The set $\{\sigma(1), \dots, \sigma(n)\}$ consists of $n$ distinct integers, hence is a rearrangement of $\{1, \dots, n\}$.

**Inverse permutation:** For each $k \in J_n$, there exists a unique $j \in J_n$ such that $\sigma(j) = k$. The **inverse** $\sigma^{-1}: J_n \to J_n$ is defined by $\sigma^{-1}(k) = j$.

**Composition:** If $\sigma, \tau$ are permutations of $J_n$, their **composite** is:

$$
(\sigma \circ \tau)(i) = \sigma(\tau(i)).
$$

We usually omit the circle and write $\sigma\tau$. The composite of permutations is again a permutation.

**Properties:**
- $\sigma\sigma^{-1} = \operatorname{id} = \sigma^{-1}\sigma$
- $(\sigma_1 \cdots \sigma_r)^{-1} = \sigma_r^{-1} \cdots \sigma_1^{-1}$

### 6.6.2 Transpositions

A **transposition** is a permutation which interchanges two numbers and leaves the others fixed.

**Properties:**
- The inverse of a transposition $\tau$ is itself: $\tau^2 = \operatorname{id}$.
- **Proposition 6.1.** Every permutation of $J_n$ can be expressed as a product of transpositions.

### 6.6.3 Notation

A permutation $\sigma$ of $\{1, \dots, n\}$ is denoted by:

$$
\begin{bmatrix} 1 & \cdots & n \\ \sigma(1) & \cdots & \sigma(n) \end{bmatrix}.
$$

**Example 1:**
- $\sigma = \begin{bmatrix} 1 & 2 & 3 \\ 2 & 1 & 3 \end{bmatrix}$ is a transposition.
- If $\sigma' = \begin{bmatrix} 1 & 2 & 3 \\ 3 & 1 & 2 \end{bmatrix}$, then:
  $$
  \sigma\sigma' = \begin{bmatrix} 1 & 2 & 3 \\ 3 & 2 & 1 \end{bmatrix}.
  $$
- The inverse of $\sigma'$ is:
  $$
  \sigma'^{-1} = \begin{bmatrix} 1 & 2 & 3 \\ 2 & 3 & 1 \end{bmatrix}.
  $$

### 6.6.4 Decomposition into Transpositions

**Example 2.** Express $\sigma = \begin{bmatrix} 1 & 2 & 3 \\ 3 & 1 & 2 \end{bmatrix}$ as a product of transpositions.

Let $\tau$ interchange 3 and 1 (fixing 2). Then:

$$
\tau\sigma = \begin{bmatrix} 1 & 2 & 3 \\ 1 & 3 & 2 \end{bmatrix} = \tau',
$$

where $\tau'$ interchanges 2 and 3. Hence $\sigma = \tau\tau'$.

**Example 3.** Express $\sigma = \begin{bmatrix} 1 & 2 & 3 & 4 \\ 2 & 3 & 4 & 1 \end{bmatrix}$ as a product of transpositions.

Let $\tau_1$ interchange 1 and 2. Then:

$$
\tau_1\sigma = \begin{bmatrix} 1 & 2 & 3 & 4 \\ 1 & 3 & 4 & 2 \end{bmatrix}.
$$

Let $\tau_2$ interchange 2 and 3. Then:

$$
\tau_2\tau_1\sigma = \begin{bmatrix} 1 & 2 & 3 & 4 \\ 1 & 2 & 4 & 3 \end{bmatrix} = \tau_3,
$$

where $\tau_3$ interchanges 3 and 4. Hence $\sigma = \tau_1\tau_2\tau_3$.

### 6.6.5 The Sign of a Permutation

**Proposition 6.2.** To each permutation $\sigma$ of $J_n$ it is possible to assign a **sign** $\epsilon(\sigma) \in \{1, -1\}$ satisfying:

| Condition | Statement |
|-----------|-----------|
| **(a)** | If $\tau$ is a transposition, $\epsilon(\tau) = -1$. |
| **(b)** | $\epsilon(\sigma\sigma') = \epsilon(\sigma)\epsilon(\sigma')$. |

**Definition via determinant:** If $A = (A^1, \dots, A^n)$ is an $n \times n$ matrix with $D(A) \neq 0$:

$$
\epsilon(\sigma) = \frac{D(A^{\sigma(1)}, \dots, A^{\sigma(n)})}{D(A^1, \dots, A^n)}.
$$

The sign is well-defined: it does not depend on the choice of columns, nor on the particular sequence of transpositions used.

### 6.6.6 Even and Odd Permutations

**Corollary 6.3.** If $\sigma = \tau_1 \cdots \tau_s$ with each $\tau_i$ a transposition, then:

$$
\epsilon(\sigma) = (-1)^s.
$$

Thus $s$ is even iff $\epsilon(\sigma) = 1$, and odd iff $\epsilon(\sigma) = -1$.

**Corollary 6.4.** For any permutation $\sigma$:

$$
\epsilon(\sigma) = \epsilon(\sigma^{-1}).
$$

**Proof:** $1 = \epsilon(\operatorname{id}) = \epsilon(\sigma\sigma^{-1}) = \epsilon(\sigma)\epsilon(\sigma^{-1})$.

**Terminology:**
- A permutation is **even** if $\epsilon(\sigma) = 1$.
- A permutation is **odd** if $\epsilon(\sigma) = -1$.
- Every transposition is odd.

> **Example 4.** The permutation in Example 2 is **even** (product of 2 transpositions). The permutation in Example 3 is **odd** (product of 3 transpositions).

## 6.7 Expansion Formula and Uniqueness of Determinants

### 6.7.1 Expansion Formula

**3 × 3 case.** Let $X^1, X^2, X^3 \in K^3$ and $(b_{ij})$ be a $3 \times 3$ matrix. If:

$$
A^j = \sum_{k=1}^3 b_{kj} X^k \quad (j=1,2,3),
$$

then by multilinearity:

$$
D(A^1,A^2,A^3) = \sum_{k=1}^3\sum_{l=1}^3\sum_{m=1}^3 b_{k1}b_{l2}b_{m3}\,D(X^k,X^l,X^m).
$$

Writing $k=\sigma(1)$, $l=\sigma(2)$, $m=\sigma(3)$ for a permutation $\sigma$ of $\{1,2,3\}$:

$$
D(A^1,A^2,A^3) = \sum_\sigma b_{\sigma(1),1}b_{\sigma(2),2}b_{\sigma(3),3}\,D(X^{\sigma(1)},X^{\sigma(2)},X^{\sigma(3)}).
$$

**General case — Lemma 7.1.** Let $X^1,\dots,X^n$ be vectors in $n$-space and $B=(b_{ij})$ an $n\times n$ matrix. Let:

$$
A^j = \sum_{i=1}^n b_{ij}X^i.
$$

Then:

$$
D(A^1,\dots,A^n) = \sum_\sigma \epsilon(\sigma)\,b_{\sigma(1),1}\cdots b_{\sigma(n),n}\,D(X^1,\dots,X^n),
$$

where the sum is over all permutations $\sigma$ of $\{1,\dots,n\}$.

**Proof sketch.** Expand $D(A^1,\dots,A^n)$ by multilinearity in each column. Terms where $\sigma$ is not injective (i.e. $\sigma(i)=\sigma(j)$ for some $i\neq j$) vanish because the determinant has two equal columns. For permutations, $D(X^{\sigma(1)},\dots,X^{\sigma(n)}) = \epsilon(\sigma)D(X^1,\dots,X^n)$ by Proposition 6.2.

### 6.7.2 Uniqueness of the Determinant

**Theorem 7.2.** Determinants are uniquely determined by properties 1, 2, and 3 (multilinearity, alternation, normalization). For $A=(a_{ij})$:

$$
D(A^1,\dots,A^n) = \sum_\sigma \epsilon(\sigma)\,a_{\sigma(1),1}\cdots a_{\sigma(n),n}.
$$

**Proof.** Apply Lemma 7.1 with $X^j=E^j$ (unit vectors) and $b_{ij}=a_{ij}$. Since $D(E^1,\dots,E^n)=1$, the formula follows immediately.

**Verification for 2 × 2.** For $A=\begin{pmatrix}a&b\\c&d\end{pmatrix}$:

$$
\begin{aligned}
D(A) &= D(aE^1+cE^2,\;bE^1+dE^2) \\
&= abD(E^1,E^1)+cbD(E^2,E^1)+adD(E^1,E^2)+cdD(E^2,E^2) \\
&= -bcD(E^1,E^2)+adD(E^1,E^2) \\
&= ad-bc.
\end{aligned}
$$

Thus any function $D$ satisfying the basic properties is given by the $2\times 2$ formula.

### 6.7.3 Multiplicativity and Transpose

**Theorem 7.3.** Let $A,B$ be $n\times n$ matrices. Then:

$$
\operatorname{Det}(AB)=\operatorname{Det}(A)\operatorname{Det}(B).
$$

**Proof.** Let $C=AB$ and let $C^k$ be the $k$-th column of $C$. Then:

$$
C^k = b_{1k}A^1+\cdots+b_{nk}A^n.
$$

By Lemma 7.1:

$$
\begin{aligned}
D(AB) &= D(C^1,\dots,C^n) \\
&= \sum_\sigma\epsilon(\sigma)\,b_{\sigma(1),1}\cdots b_{\sigma(n),n}\,D(A^1,\dots,A^n) \\
&= D(B)\,D(A).
\end{aligned}
$$

**Corollary 7.4.** If $A$ is invertible, then:

$$
\operatorname{Det}(A^{-1})=\operatorname{Det}(A)^{-1}.
$$

**Proof.** $1=D(I)=D(AA^{-1})=D(A)D(A^{-1})$.

**Theorem 7.5.** Let $A$ be a square matrix. Then:

$$
\operatorname{Det}(A)=\operatorname{Det}({}^tA).
$$

**Proof.** From Theorem 7.2:

$$
\operatorname{Det}(A)=\sum_\sigma\epsilon(\sigma)\,a_{\sigma(1),1}\cdots a_{\sigma(n),n}.
$$

If $\sigma(j)=k$, then $a_{\sigma(j),j}=a_{k,\sigma^{-1}(k)}$. Since each integer $1,\dots,n$ occurs exactly once among $\sigma(1),\dots,\sigma(n)$, the product equals:

$$
a_{1,\sigma^{-1}(1)}\cdots a_{n,\sigma^{-1}(n)}.
$$

Using $\epsilon(\sigma)=\epsilon(\sigma^{-1})$:

$$
\operatorname{Det}(A)=\sum_\sigma\epsilon(\sigma^{-1})\,a_{1,\sigma^{-1}(1)}\cdots a_{n,\sigma^{-1}(n)}=\sum_\sigma\epsilon(\sigma)\,a_{1,\sigma(1)}\cdots a_{n,\sigma(n)},
$$

which is precisely the expansion for $\operatorname{Det}({}^tA)$.

## 6.8 Inverse of a Matrix

### 6.8.1 The 2 × 2 Case

Let $A=\begin{pmatrix}a&b\\c&d\end{pmatrix}$ with $\det(A)=ad-bc\neq 0$. To find $X=\begin{pmatrix}x&y\\z&w\end{pmatrix}$ such that $AX=I$:

- First column: $\begin{cases} ax+bz=1 \\ cx+dz=0 \end{cases}$
- Second column: $\begin{cases} ay+bw=0 \\ cy+dw=1 \end{cases}$

**Example:** For $A=\begin{pmatrix}2&1\\4&3\end{pmatrix}$:

| Unknown | Value |
|---------|-------|
| $x$ | $\frac{3}{2}$ |
| $z$ | $-2$ |
| $y$ | $-\frac{1}{2}$ |
| $w$ | $1$ |

Hence:

$$
X=\begin{pmatrix}\frac{3}{2}&-\frac{1}{2}\\-2&1\end{pmatrix},
$$

and one verifies $AX=XA=I$.

### 6.8.2 Definition and Uniqueness

For an $n\times n$ matrix $A$, a matrix $B$ such that $AB=I$ and $BA=I$ is called the **inverse** of $A$, denoted $A^{-1}$.

**Uniqueness.** If $C$ is also an inverse, then $C=CI=C(AB)=(CA)B=IB=B$.

A square matrix with $\det(A)\neq 0$, or equivalently one that admits an inverse, is called **non-singular**.

### 6.8.3 Theorem 8.1 — Formula for the Inverse

**Theorem 8.1.** Let $A=(a_{ij})$ be $n\times n$ with $D(A)\neq 0$. Let $E^j$ be the $j$-th unit column vector, and let:

$$
b_{ij}=\frac{D(A^1,\dots,E^j,\dots,A^n)}{D(A)},
$$

where $E^j$ occurs in the $i$-th place. Then $B=(b_{ij})$ is the inverse of $A$.

**Proof.**
- **Existence ($AX=I$):** The $j$-th column of $X$ satisfies $E^j=x_{1j}A^1+\cdots+x_{nj}A^n$. By Cramer's rule:
  $$
x_{ij}=\frac{D(A^1,\dots,E^j,\dots,A^n)}{D(A)}=b_{ij}.
  $$
- **Verification ($XA=I$):** Since $D({}^tA)\neq 0$, there exists $Y$ with ${}^tA\,Y=I$. Taking transposes gives ${}^tY A=I$. Then:
  $$
  XA=I(XA)=({}^tY A)(XA)={}^tY(AX)A={}^tY I A={}^tY A=I.
  $$

### 6.8.4 Explicit Formula via Cofactors

Expanding the numerator determinant of $b_{ij}$ along its $i$-th column yields a single non-zero term. Let $A_{ji}$ denote the submatrix obtained from $A$ by deleting the $j$-th row and $i$-th column. Then:

$$
b_{ij}=\frac{(-1)^{i+j}\det(A_{ji})}{\det(A)}.
$$

Hence:

$$
A^{-1}={}^t\!\left(\frac{(-1)^{i+j}\det(A_{ij})}{\det(A)}\right).
$$

> In words: form the **cofactor matrix** $C=(c_{ij})$ with $c_{ij}=(-1)^{i+j}\det(A_{ij})$, take its transpose (the **adjugate**), and divide by $\det(A)$.

## 6.9 The Rank of a Matrix and Subdeterminants

### 6.9.1 Rank via Subdeterminants

Since determinants test linear independence, they can be used to determine the rank of a matrix.

**Example 1.** Let:

$$
A=\begin{pmatrix}3&1&2&5\\1&2&-1&2\\1&1&0&1\end{pmatrix}.
$$

This $3\times 4$ matrix has rank at most 3. The subdeterminant from columns 1, 2, 4:

$$
\begin{vmatrix}3&1&5\\1&2&2\\1&1&1\end{vmatrix}=-4\neq 0,
$$

so $\operatorname{rank} A = 3$.

It may happen that some $3\times 3$ subdeterminant is 0 while the rank is still 3. For instance, let:

$$
B=\begin{pmatrix}3&1&2&5\\1&2&-1&2\\4&3&1&1\end{pmatrix}.
$$

The first three columns have determinant 0 (row 3 = row 1 + row 2). But columns 2, 3, 4 give a non-zero determinant, so $\operatorname{rank} B = 3$.

> **General principle.** For a $3\times 4$ matrix, if the rank is $\le 2$, then **every** $3\times 3$ subdeterminant is 0. Conversely, if every $3\times 3$ subdeterminant is 0, the rank is $\le 2$.

**Example 2.** Let:

$$
C=\begin{pmatrix}3&1&2&5\\1&2&-1&2\\4&3&1&7\end{pmatrix}.
$$

Every $3\times 3$ subdeterminant is 0, so $\operatorname{rank} C\le 2$. However:

$$
\begin{vmatrix}3&1\\1&2\end{vmatrix}=5\neq 0,
$$

so the first two rows are linearly independent. Hence $\operatorname{rank} C = 2$. (Indeed, row 3 = row 1 + row 2.)

---

[<- Previous: 5. Scalar Products and Orthogonality](05-scalar-products-and-orthogonality.md) | [Next: 7. Symmetric, Hermitian, and Unitary Operators ->](07-symmetric-hermitian-and-unitary-operators.md)
