[<- Previous: 3. Linear Mappings](03-linear-mappings.md) | [Next: 5. Scalar Products and Orthogonality ->](05-scalar-products-and-orthogonality.md)

# 4. Linear Maps and Matrices

## 4.1 The Linear Map Associated with a Matrix

### 4.1.1 Definition

Let $A$ be an $m \times n$ matrix. The **linear map associated with $A$** is:

$$
L_A: K^n \to K^m, \quad L_A(X) = AX
$$

for every column vector $X \in K^n$.

$L_A$ is linear by properties of matrix multiplication:

$$
A(X + Y) = AX + AY, \qquad A(cX) = cAX.
$$

**Example:** If $A = \begin{pmatrix} 2 & 1 \\ -1 & 5 \end{pmatrix}$ and $X = \begin{pmatrix} 3 \\ 7 \end{pmatrix}$, then:

$$
L_A(X) = \begin{pmatrix} 2 & 1 \\ -1 & 5 \end{pmatrix} \begin{pmatrix} 3 \\ 7 \end{pmatrix} = \begin{pmatrix} 6 + 7 \\ -3 + 35 \end{pmatrix} = \begin{pmatrix} 13 \\ 32 \end{pmatrix}.
$$

### 4.1.2 Theorem 1.1 — Uniqueness

**Theorem 1.1.** If $A, B$ are $m \times n$ matrices and $L_A = L_B$, then $A = B$.

**Proof:** $A_i \cdot X = B_i \cdot X$ for all $X$ and all rows $i$. Hence $(A_i - B_i) \cdot X = 0$ for all $X$. By non-degeneracy of the dot product, $A_i - B_i = O$, so $A_i = B_i$ for all $i$. Thus $A = B$.

### 4.1.3 Kernel Interpretation

A homogeneous system $AX = O$ can be interpreted as:

$$
\text{Set of solutions} = \operatorname{Ker} L_A.
$$


## 4.2 The Matrix Associated with a Linear Map

### 4.2.1 Special Case — $K^n \to K$

Let $L: K^n \to K$ be linear. There exists a **unique** vector $A \in K^n$ such that $L = L_A$, i.e.:

$$
L(X) = A \cdot X.
$$

**Proof:** Let $a_i = L(E_i)$ where $E_i$ are unit vectors. Then:

$$
L(X) = L(x_1 E_1 + \cdots + x_n E_n) = x_1 L(E_1) + \cdots + x_n L(E_n) = x_1 a_1 + \cdots + x_n a_n = X \cdot A.
$$

### 4.2.2 Theorem 2.1 — General Case

**Theorem 2.1.** Let $L: K^n \to K^m$ be linear. Then there exists a **unique** matrix $A$ such that $L = L_A$.

**Proof:** Let $E^1, \dots, E^n$ be unit column vectors in $K^n$, and $e^1, \dots, e^m$ in $K^m$. Write $X = x_1 E^1 + \cdots + x_n E^n$. By linearity:

$$
L(X) = x_1 L(E^1) + \cdots + x_n L(E^n).
$$

Each $L(E^j)$ can be written as $L(E^j) = a_{1j} e^1 + \cdots + a_{mj} e^m$. Hence:

$$
L(X) = \sum_{j=1}^n x_j \sum_{i=1}^m a_{ij} e^i = \sum_{i=1}^m \left(\sum_{j=1}^n a_{ij} x_j\right) e^i = AX.
$$

The $j$-th column of $A$ is $L(E^j)$. Uniqueness follows from Theorem 1.1.

### 4.2.3 Examples

**Example 1 — Projection:** $F: \mathbf{R}^3 \to \mathbf{R}^2$, $F(x_1, x_2, x_3) = (x_1, x_2)$.

$$
A = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \end{pmatrix}.
$$

**Example 2 — Identity:** $I: \mathbf{R}^n \to \mathbf{R}^n$. Associated matrix is $I_n$.

**Example 3:** $L: \mathbf{R}^4 \to \mathbf{R}^2$ with:

$$
L(E^1) = \begin{pmatrix} 2 \\ 1 \end{pmatrix}, \; L(E^2) = \begin{pmatrix} 3 \\ -1 \end{pmatrix}, \; L(E^3) = \begin{pmatrix} -5 \\ 4 \end{pmatrix}, \; L(E^4) = \begin{pmatrix} 1 \\ 7 \end{pmatrix}.
$$

$$
A = \begin{pmatrix} 2 & 3 & -5 & 1 \\ 1 & -1 & 4 & 7 \end{pmatrix}.
$$

**Example 4 — Rotations:** $L: \mathbf{R}^2 \to \mathbf{R}^2$ is a **rotation** by angle $\theta$ if:

$$
R(\theta) = \begin{pmatrix} \cos\theta & -\sin\theta \\ \sin\theta & \cos\theta \end{pmatrix}.
$$

Then $L(E^1) = (\cos\theta, \sin\theta)$ and $L(E^2) = (-\sin\theta, \cos\theta)$. For $\theta = \pi/2$:

$$
R\left(\frac{\pi}{2}\right) = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}.
$$

### 4.2.4 Correspondence of Operations

Matrix operations correspond to linear map operations:

| Matrix Operation | Linear Map Operation |
|------------------|----------------------|
| $A + B$ | $L_A + L_B$ |
| $cA$ | $cL_A$ |
| $BA$ | $G \circ F$ (if $G = L_B$, $F = L_A$) |

For $F: K^n \to K^m$ and $G: K^m \to K^s$ with matrices $A, B$:

$$
(G \circ F)(X) = G(F(X)) = B(AX) = (BA)X.
$$

### 4.2.5 Theorem 2.2 — Invertibility Criterion

**Theorem 2.2.** Let $A$ be $n \times n$ with columns $A^1, \dots, A^n$. Then $A$ is invertible if and only if $A^1, \dots, A^n$ are linearly independent.

**Proof:**
- ($\impliedby$) If $A^1, \dots, A^n$ are independent, they form a basis of $K^n$. There exists $B$ such that $BA^j = E^j$ for all $j$, i.e. $BA = I$.
- ($\implies$) If $A$ is invertible, $\operatorname{Ker} L_A = \{O\}$ (since $AX = O \implies X = O$). Thus $A^1, \dots, A^n$ are independent.


## 4.3 Bases, Matrices, and Linear Maps

### 4.3.1 Matrix of a Linear Map Relative to Bases

Let $V, W$ be finite dimensional with bases $\mathscr{B} = \{v_1, \dots, v_n\}$ and $\mathscr{B}' = \{w_1, \dots, w_m\}$. For $F: V \to W$ linear, the **matrix associated with $F$ relative to $\mathscr{B}, \mathscr{B}'$** is denoted $M_{\mathscr{B}'}^{\mathscr{B}}(F)$.

This is the unique matrix $A$ such that:

> If $X$ is the coordinate vector of $v \in V$ relative to $\mathscr{B}$, then $AX$ is the coordinate vector of $F(v)$ relative to $\mathscr{B}'$.

**Notation:** $X_{\mathscr{B}}(v)$ denotes the coordinate vector of $v$ relative to $\mathscr{B}$.

**Theorem 3.1.** For $v \in V$:

$$
X_{\mathscr{B}'}(F(v)) = M_{\mathscr{B}'}^{\mathscr{B}}(F) \, X_{\mathscr{B}}(v).
$$

**Corollary 3.2.** For bases $\mathscr{B}, \mathscr{B}'$ of $V$:

$$
X_{\mathscr{B}'}(v) = M_{\mathscr{B}'}^{\mathscr{B}}(\operatorname{id}) \, X_{\mathscr{B}}(v).
$$

This describes how coordinates change when the basis changes.

### 4.3.2 Constructing the Matrix

If $F(v_j) = a_{1j} w_1 + \cdots + a_{mj} w_m$, then:

$$
M_{\mathscr{B}'}^{\mathscr{B}}(F) = \begin{pmatrix} a_{11} & a_{12} & \cdots & a_{1n} \\ a_{21} & a_{22} & \cdots & a_{2n} \\ \vdots & \vdots & & \vdots \\ a_{m1} & a_{m2} & \cdots & a_{mn} \end{pmatrix}.
$$

The $j$-th column consists of the coordinates of $F(v_j)$ relative to $\mathscr{B}'$.

**Example 1:** $\dim V = 2$, $\dim W = 3$, with:
- $F(v_1) = 3w_1 - w_2 + 17w_3$
- $F(v_2) = w_1 + w_2 - w_3$

$$
M_{\mathscr{B}'}^{\mathscr{B}}(F) = \begin{pmatrix} 3 & 1 \\ -1 & 1 \\ 17 & -1 \end{pmatrix}.
$$

**Example 2:** $M_{\mathscr{B}}^{\mathscr{B}}(\operatorname{id}) = I$.

> **Warning:** If $\mathscr{B} \neq \mathscr{B}'$, then $M_{\mathscr{B}'}^{\mathscr{B}}(\operatorname{id}) \neq I$ in general.

**Example 3:** Let $\mathscr{B} = \{v_1, \dots, v_n\}$ and $\mathscr{B}' = \{w_1, \dots, w_n\}$ with:

$$
w_i = a_{i1} v_1 + \cdots + a_{in} v_n.
$$

Then $M_{\mathscr{B}}^{\mathscr{B}'}(\operatorname{id}) = {}^tA$ where $A = (a_{ij})$.

### 4.3.3 Theorem 3.3 — Linearity of the Association

**Theorem 3.3.** Let $M = M_{\mathscr{B}'}^{\mathscr{B}}$. Then:

$$
M(f + g) = M(f) + M(g), \qquad M(cf) = cM(f).
$$

The association $f \mapsto M_{\mathscr{B}'}^{\mathscr{B}}(f)$ is an **isomorphism** between $\mathscr{L}(V, W)$ and $\operatorname{Mat}_{m \times n}(K)$.

### 4.3.4 Theorem 3.4 — Composition Corresponds to Multiplication

**Theorem 3.4.** Let $F: V \to W$ and $G: W \to U$ be linear. Then:

$$
M_{\mathscr{B}''}^{\mathscr{B}'}(G) \, M_{\mathscr{B}'}^{\mathscr{B}}(F) = M_{\mathscr{B}''}^{\mathscr{B}}(G \circ F).
$$

**Proof:** The coordinate vector of $F(v)$ relative to $\mathscr{B}'$ is $AX$. The coordinate vector of $G(F(v))$ relative to $\mathscr{B}''$ is $B(AX) = (BA)X$.

### 4.3.5 Change of Basis

**Corollary 3.5.** For bases $\mathscr{B}, \mathscr{B}'$ of $V$:

$$
M_{\mathscr{B}'}^{\mathscr{B}}(\operatorname{id}) \, M_{\mathscr{B}}^{\mathscr{B}'}(\operatorname{id}) = I = M_{\mathscr{B}}^{\mathscr{B}'}(\operatorname{id}) \, M_{\mathscr{B}'}^{\mathscr{B}}(\operatorname{id}).
$$

In particular, $M_{\mathscr{B}'}^{\mathscr{B}}(\operatorname{id})$ is invertible.

**Theorem 3.6.** Let $F: V \to V$ be linear, and $\mathscr{B}, \mathscr{B}'$ be bases of $V$. Then:

$$
M_{\mathscr{B}'}^{\mathscr{B}'}(F) = N^{-1} M_{\mathscr{B}}^{\mathscr{B}}(F) N
$$

where $N = M_{\mathscr{B}}^{\mathscr{B}'}(\operatorname{id})$.

**Proof:** Apply Theorem 3.4 to $F = \operatorname{id} \circ F \circ \operatorname{id}$.

### 4.3.6 Diagonalization and Similarity

A basis $\mathscr{B}$ **diagonalizes** $F: V \to V$ if $M_{\mathscr{B}}^{\mathscr{B}}(F)$ is a diagonal matrix. If such a basis exists, $F$ is **diagonalizable**.

**Theorem 3.7.** $F$ (or its matrix $M$) can be diagonalized if and only if there exists an invertible matrix $N$ such that $N^{-1} M N$ is diagonal.

Two matrices $M, M'$ are **similar** (over $K$) if there exists invertible $N$ such that:

$$
M' = N^{-1} M N.
$$
---

[<- Previous: 3. Linear Mappings](03-linear-mappings.md) | [Next: 5. Scalar Products and Orthogonality ->](05-scalar-products-and-orthogonality.md)
