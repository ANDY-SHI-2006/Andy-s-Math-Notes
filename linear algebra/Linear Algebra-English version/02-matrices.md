[← Previous: 1. Vector Spaces](01-vector-spaces.md) | [Next: 3. Linear Mappings →](03-linear-mappings.md)

# 2. Matrices


## 2.1 The Space of Matrices

### 2.1.1 Definition

Let $K$ be a field, $m, n \ge 1$ integers. An array of numbers in $K$:

$$
A = \begin{pmatrix} a_{11} & a_{12} & \cdots & a_{1n} \\ a_{21} & a_{22} & \cdots & a_{2n} \\ \vdots & \vdots & & \vdots \\ a_{m1} & a_{m2} & \cdots & a_{mn} \end{pmatrix}
$$

is called a **matrix** in $K$, abbreviated as $(a_{ij})$ with $i = 1, \dots, m$ and $j = 1, \dots, n$.

- An $m \times n$ matrix has $m$ **rows** and $n$ **columns**.
- $a_{ij}$ is the **$ij$-entry** (or **$ij$-component**).
- $A_i = (a_{i1}, a_{i2}, \dots, a_{in})$: the **$i$-th row**.
- $A^j = \begin{pmatrix} a_{1j} \\ a_{2j} \\ \vdots \\ a_{mj} \end{pmatrix}$: the **$j$-th column** (a **column vector**).

**Example 1:**

$$
\begin{pmatrix} 1 & 1 & -2 \\ -1 & 4 & -5 \end{pmatrix}
$$

is a $2 \times 3$ matrix. Rows: $(1, 1, -2)$ and $(-1, 4, -5)$.

Special cases:
- A vector $(x_1, \dots, x_n)$ is a $1 \times n$ matrix (row vector).
- A column vector is an $n \times 1$ matrix.
- A single number $(a)$ is a $1 \times 1$ matrix.

### 2.1.2 Square Matrices

If $m = n$, the matrix is a **square matrix**.

**Example:**

$$
\begin{pmatrix} 1 & 2 \\ -1 & 0 \end{pmatrix}, \qquad \begin{pmatrix} 1 & -1 & 5 \\ 2 & 1 & -1 \\ 3 & 1 & -1 \end{pmatrix}
$$

### 2.1.3 Zero Matrix

The **zero matrix** $O$ has $a_{ij} = 0$ for all $i, j$.

> We have met: zero number $0$, zero vector $O$, and zero matrix $O$.

### 2.1.4 Addition of Matrices

Addition is defined only for matrices of the **same size**. If $A = (a_{ij})$ and $B = (b_{ij})$ are both $m \times n$:

$$
A + B = (a_{ij} + b_{ij}).
$$

**Example 2:**

$$
A = \begin{pmatrix} 1 & -1 & 0 \\ 2 & 3 & 4 \end{pmatrix}, \quad B = \begin{pmatrix} 5 & 1 & -1 \\ 2 & 1 & -1 \end{pmatrix}
$$

$$
A + B = \begin{pmatrix} 6 & 0 & -1 \\ 4 & 4 & 3 \end{pmatrix}
$$

$O + A = A + O = A$ for any matrix $A$.

### 2.1.5 Scalar Multiplication

For $c \in K$ and $A = (a_{ij})$:

$$
cA = (ca_{ij}).
$$

**Example 3:** With $A, B$ as above and $c = 2$:

$$
2A = \begin{pmatrix} 2 & -2 & 0 \\ 4 & 6 & 8 \end{pmatrix}, \qquad 2B = \begin{pmatrix} 10 & 2 & -2 \\ 4 & 2 & -2 \end{pmatrix}
$$

Also $(-1)A = -A$, and $A + (-1)A = O$.

> The matrices of a given size $m \times n$ with components in $K$ form a vector space over $K$, denoted $\operatorname{Mat}_{m \times n}(K)$. All axioms VS 1–VS 8 are satisfied.

### 2.1.6 Transpose

The **transpose** of an $m \times n$ matrix $A = (a_{ij})$ is the $n \times m$ matrix $^tA = (b_{ji})$ where $b_{ji} = a_{ij}$.

Taking the transpose interchanges rows and columns.

**Example:**

$$
A = \begin{pmatrix} 2 & 1 & 0 \\ 1 & 3 & 5 \end{pmatrix} \implies {}^tA = \begin{pmatrix} 2 & 1 \\ 1 & 3 \\ 0 & 5 \end{pmatrix}
$$

If $A = (2, 1, -4)$ is a row vector, then ${}^tA = \begin{pmatrix} 2 \\ 1 \\ -4 \end{pmatrix}$ is a column vector.

### 2.1.7 Symmetric Matrices

A matrix $A$ is **symmetric** if ${}^tA = A$. A symmetric matrix must be square.

**Example:**

$$
\begin{pmatrix} 1 & -1 & 2 \\ -1 & 0 & 3 \\ 2 & 3 & 7 \end{pmatrix}
$$

### 2.1.8 Diagonal Matrices

For a square matrix $A = (a_{ij})$, the elements $a_{11}, \dots, a_{nn}$ are its **diagonal components**.

A **diagonal matrix** has $a_{ij} = 0$ for all $i \neq j$:

$$
\begin{pmatrix} a_1 & 0 & \cdots & 0 \\ 0 & a_2 & \cdots & 0 \\ \vdots & \vdots & & \vdots \\ 0 & 0 & \cdots & a_n \end{pmatrix}
$$

Every diagonal matrix is symmetric.

### 2.1.9 Unit Matrix

The **unit matrix** $I_n$ (or $I$) is the diagonal matrix with all diagonal components equal to $1$:

$$
I_n = \begin{pmatrix} 1 & 0 & \cdots & 0 \\ 0 & 1 & \cdots & 0 \\ \vdots & \vdots & & \vdots \\ 0 & 0 & \cdots & 1 \end{pmatrix}
$$


## 2.2 Linear Equations

### 2.2.1 Systems of Linear Equations

Let $A = (a_{ij})$ be an $m \times n$ matrix in $K$, and $b_1, \dots, b_m \in K$. A system of **linear equations**:

$$
\begin{cases}
a_{11}x_1 + \cdots + a_{1n}x_n = b_1 \\
\quad \vdots \\
a_{m1}x_1 + \cdots + a_{mn}x_n = b_m
\end{cases} \tag{*}
$$

- **Homogeneous** if all $b_i = 0$.
- $n$ = number of **unknowns**; $m$ = number of **equations**.
- $(a_{ij})$ = **matrix of coefficients**.

The **homogeneous system** associated with (*):

$$
\begin{cases}
a_{11}x_1 + \cdots + a_{1n}x_n = 0 \\
\quad \vdots \\
a_{m1}x_1 + \cdots + a_{mn}x_n = 0
\end{cases} \tag{**}
$$

The system (**) always has the **trivial solution** $x_1 = \cdots = x_n = 0$. A solution with some $x_i \neq 0$ is **non-trivial**.

### 2.2.2 Column Vector Interpretation

The homogeneous system (**) can be rewritten using column vectors $A^1, \dots, A^n$ of $A$:

$$
x_1 A^1 + \cdots + x_n A^n = O.
$$

A non-trivial solution is an $n$-tuple $X \neq O$ giving a linear dependence relation among the columns.

### 2.2.3 Theorem 2.1 — Existence of Non-Trivial Solutions

**Theorem 2.1.** Let (\*\*) be a homogeneous system of $m$ linear equations in $n$ unknowns, with $n > m$. Then the system has a **non-trivial solution** in $K$.

**Proof:** The column vectors $A^1, \dots, A^n \in K^m$. Since $\dim K^m = m$ and $n > m$, by Theorem 3.1 (Chapter I) the vectors $A^1, \dots, A^n$ are linearly dependent. Hence there exist $x_1, \dots, x_n$ not all zero such that $x_1 A^1 + \cdots + x_n A^n = O$.

### 2.2.4 The Non-Homogeneous System

Let $B = \begin{pmatrix} b_1 \\ \vdots \\ b_m \end{pmatrix}$. The system (*) can be written as:

$$
x_1 A^1 + \cdots + x_n A^n = B.
$$

### 2.2.5 Theorem 2.2 — Uniqueness of Solution

**Theorem 2.2.** Assume $m = n$ in (*) and that $A^1, \dots, A^n$ are linearly independent. Then (*) has a **unique solution** in $K$.

**Proof:** Since $A^1, \dots, A^n$ are linearly independent and $\dim K^n = n$, they form a basis of $K^n$. Hence any vector $B$ has a unique expression:

$$
B = x_1 A^1 + \cdots + x_n A^n
$$

with $x_i \in K$. Thus $X = (x_1, \dots, x_n)$ is the unique solution.


## 2.3 Multiplication of Matrices

### 2.3.1 Review of Dot Product

For $A = (a_1, \dots, a_n)$ and $B = (b_1, \dots, b_n)$ in $K^n$:

$$
A \cdot B = a_1 b_1 + \cdots + a_n b_n.
$$

**Properties:**

| Property | Statement |
|----------|-----------|
| **SP 1.** | $A \cdot B = B \cdot A$ |
| **SP 2.** | $A \cdot (B + C) = A \cdot B + A \cdot C$ |
| **SP 3.** | $(xA) \cdot B = x(A \cdot B)$ |

**Positivity (for $\mathbf{R}$):** If $A \in \mathbf{R}^n$, then $A^2 = a_1^2 + \cdots + a_n^2 \ge 0$, and $A^2 > 0$ if $A \neq O$.

> **Note:** Positivity fails for $\mathbf{C}$. Example: $A = (1, i)$, then $A \cdot A = 1 + i^2 = 0$.

**Non-degeneracy:** If $A \cdot X = 0$ for all $X \in K^n$, then $A = O$.

**Proof:** $A \cdot E_i = a_i = 0$ for each unit vector $E_i$.

### 2.3.2 Definition of Matrix Product

Let $A = (a_{ij})$ be $m \times n$ and $B = (b_{jk})$ be $n \times s$. The **product** $AB$ is the $m \times s$ matrix whose $ik$-entry is:

$$
(AB)_{ik} = \sum_{j=1}^{n} a_{ij} b_{jk} = a_{i1} b_{1k} + a_{i2} b_{2k} + \cdots + a_{in} b_{nk}.
$$

In terms of row vectors $A_i$ of $A$ and column vectors $B^k$ of $B$:

$$
(AB)_{ik} = A_i \cdot B^k.
$$

Thus:

$$
AB = \begin{pmatrix} A_1 \cdot B^1 & \cdots & A_1 \cdot B^s \\ \vdots & & \vdots \\ A_m \cdot B^1 & \cdots & A_m \cdot B^s \end{pmatrix}.
$$

Matrix multiplication generalizes the dot product.

**Example 1:**

$$
A = \begin{pmatrix} 2 & 1 & 5 \\ 1 & 3 & 2 \end{pmatrix}, \quad B = \begin{pmatrix} 3 & 4 \\ -1 & 2 \\ 2 & 1 \end{pmatrix}
$$

$$
AB = \begin{pmatrix} 15 & 15 \\ 4 & 12 \end{pmatrix}
$$

**Example 2:**

$$
C = \begin{pmatrix} 1 & 3 \\ -1 & -1 \end{pmatrix}, \quad BC = \begin{pmatrix} -1 & 5 \\ -3 & -5 \\ 1 & 5 \end{pmatrix}, \quad A(BC) = \begin{pmatrix} 0 & 30 \\ -8 & 0 \end{pmatrix}
$$

### 2.3.3 Matrix-Vector Products

If $A$ is $m \times n$ and $B$ is $n \times 1$ (column vector), then $AB$ is an $m \times 1$ column vector:

$$
\begin{pmatrix} a_{11} & \cdots & a_{1n} \\ \vdots & & \vdots \\ a_{m1} & \cdots & a_{mn} \end{pmatrix} \begin{pmatrix} b_1 \\ \vdots \\ b_n \end{pmatrix} = \begin{pmatrix} c_1 \\ \vdots \\ c_m \end{pmatrix}, \quad c_i = \sum_{j=1}^{n} a_{ij} b_j.
$$

If $X = (x_1, \dots, x_m)$ is a row vector ($1 \times m$), then $XA$ is a $1 \times n$ row vector:

$$
(y_1, \dots, y_n), \quad y_k = \sum_{i=1}^{m} x_i a_{ik}.
$$

### 2.3.4 Distributivity

**Theorem 3.1.** Let $A, B, C$ be matrices with compatible sizes. Then:

$$
A(B + C) = AB + AC, \qquad A(xB) = x(AB).
$$

**Proof:** The $ik$-component of $A(B+C)$ is $A_i \cdot (B^k + C^k) = A_i \cdot B^k + A_i \cdot C^k$, which equals the $ik$-component of $AB + AC$. Similarly for scalar multiplication.

### 2.3.5 Associativity

**Theorem 3.2.** Let $A$ be $m \times n$, $B$ be $n \times r$, $C$ be $r \times s$. Then:

$$
(AB)C = A(BC).
$$

**Proof:** The $il$-component of $(AB)C$ is:

$$
\sum_{k=1}^{r} \left[\sum_{j=1}^{n} a_{ij} b_{jk}\right] c_{kl} = \sum_{j=1}^{n} \sum_{k=1}^{r} a_{ij} b_{jk} c_{kl}.
$$

The same sum is obtained from $A(BC)$.

### 2.3.6 Invertible Matrices

A square $n \times n$ matrix $A$ is **invertible** (or **non-singular**) if there exists an $n \times n$ matrix $B$ such that:

$$
AB = BA = I_n.
$$

Such $B$ is **unique**: if $AC = CA = I_n$, then $B = B I_n = B(AC) = (BA)C = I_n C = C$.

This unique $B$ is called the **inverse** of $A$, denoted $A^{-1}$.

### 2.3.7 Powers of Matrices

For a square matrix $A$:
- $A^m = A \cdots A$ ($m$ times), for integer $m \ge 1$
- $A^0 = I$
- $A^{r+s} = A^r A^s$ for integers $r, s \ge 0$

### 2.3.8 Transpose of a Product

**Theorem 3.3.** Let $A, B$ be matrices which can be multiplied. Then:

$$
{}^t(AB) = {}^tB \, {}^tA.
$$

**Proof:** Let $AB = C$ with $c_{ik} = \sum_{j} a_{ij} b_{jk}$. The $ki$-component of ${}^tC$ is $c_{ik}$. The $ki$-component of ${}^tB \, {}^tA$ is $\sum_{j} b_{kj}' a_{ji}' = \sum_{j} b_{jk} a_{ij} = c_{ik}$.

### 2.3.9 Matrix Form of Linear Equations

A system of linear equations can be written as:

$$
AX = B
$$

where $A$ is $m \times n$, $X$ is an $n \times 1$ column vector, and $B$ is an $m \times 1$ column vector.

[← Previous: 1. Vector Spaces](01-vector-spaces.md) | [Next: 3. Linear Mappings →](03-linear-mappings.md)
