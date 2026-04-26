[<- Previous: 6. Determinants](06-determinants.md) | [Next: 8. Eigenvectors and Eigenvalues ->](08-eigenvectors-and-eigenvalues.md)

# 7. Symmetric, Hermitian, and Unitary Operators

## 7.1 Symmetric Operators

Let $V$ be a finite dimensional vector space over the real or complex numbers, with a positive definite scalar product. Let $A: V \to V$ be a linear map. We study three important special cases of such maps (symmetric, hermitian, unitary), which are also represented by matrices bearing the same names when a basis of $V$ has been chosen.

### 7.1.1 Setup

Throughout this section, $V$ is a finite dimensional vector space over a field $K$, with a fixed non-degenerate scalar product $\langle v, w \rangle$.

> We may take $V = K^n$ and fix the scalar product to be the ordinary dot product $\langle X, Y \rangle = {}^tX Y$.

A linear map $A: V \to V$ is called an **operator**.

### 7.1.2 The Transpose of an Operator

**Lemma 1.1.** Let $A: V \to V$ be an operator. Then there exists a **unique** operator $B: V \to V$ such that for all $v, w \in V$:

$$
\langle Av, w \rangle = \langle v, Bw \rangle.
$$

**Proof.** Given $w \in V$, define $L(v) = \langle Av, w \rangle$. Then $L \in V^*$ (a functional). By Theorem 6.2 (Chapter V), there exists a unique $w' \in V$ such that $L(v) = \langle v, w' \rangle$ for all $v$. Define $Bw = w'$.

Linearity of $B$:
- $\langle v, B(w_1+w_2) \rangle = \langle Av, w_1+w_2 \rangle = \langle v, Bw_1 \rangle + \langle v, Bw_2 \rangle = \langle v, Bw_1+Bw_2 \rangle$.
- $\langle v, B(cw) \rangle = \langle Av, cw \rangle = c\langle v, Bw \rangle = \langle v, cBw \rangle$.

Hence $B$ is linear.

This operator $B$ is called the **transpose** of $A$, denoted ${}^tA$. Thus:

$$
\langle Av, w \rangle = \langle v, {}^tA w \rangle \quad \text{for all } v, w \in V.
$$

An operator $A$ is **symmetric** (with respect to the fixed scalar product) if:

$$
{}^tA = A.
$$

Equivalently, $A$ is symmetric iff $\langle Av, w \rangle = \langle v, Aw \rangle$ for all $v, w$.

**Example 1.** Let $V = K^n$ with the ordinary dot product. For a matrix $A$ and column vectors $X, Y$:

$$
\langle AX, Y \rangle = {}^t(AX)Y = {}^tX {}^tA Y = \langle X, {}^tA Y \rangle.
$$

Thus the transpose of the operator is represented by the transpose of the associated matrix.

### 7.1.3 Formal Properties of the Transpose

**Theorem 1.2.** Let $A, B$ be operators and $c \in K$. Then:

| Formula | Statement |
|---------|-----------|
| **Sum** | ${}^t(A+B) = {}^tA + {}^tB$ |
| **Product** | ${}^t(AB) = {}^tB {}^tA$ |
| **Scalar** | ${}^t(cA) = c{}^tA$ |
| **Double transpose** | ${}^{tt}A = A$ |

**Proof of product formula.** For all $v, w \in V$:

$$
\langle ABv, w \rangle = \langle Bv, {}^tA w \rangle = \langle v, {}^tB {}^tA w \rangle.
$$

Hence ${}^t(AB) = {}^tB {}^tA$. The other formulas follow similarly.

## 7.2 Hermitian Operators

Throughout this section, $V$ is a finite dimensional vector space over $\mathbf{C}$, with a fixed positive definite hermitian product $\langle v, w \rangle$.

> We may take $V = \mathbf{C}^n$ with the standard hermitian product $\langle X, Y \rangle = {}^tX \bar{Y}$.

### 7.2.1 The Adjoint of an Operator

For each $w \in V$, the map $L_w(v) = \langle Av, w \rangle$ is a functional.

**Theorem 2.1.** Given a functional $L$ on $V$, there exists a unique $w' \in V$ such that $L(v) = \langle v, w' \rangle$ for all $v \in V$.

**Proof.** Similar to the real case (Theorem 6.2, Chapter V).

> **Remark.** The association $w \mapsto L_w$ is *not* an isomorphism $V \to V^*$, since $L_{\alpha w} = \bar{\alpha} L_w$.

**Lemma 2.2.** Given an operator $A: V \to V$, there exists a unique operator $A^*: V \to V$ such that for all $v, w \in V$:

$$
\langle Av, w \rangle = \langle v, A^* w \rangle.
$$

**Proof.** Similar to Lemma 1.1.

The operator $A^*$ is called the **adjoint** of $A$. Note that $A^*$ is linear (not anti-linear).

**Example.** Let $V = \mathbf{C}^n$ with the standard form. For a matrix $A$ and column vectors $X, Y$:

$$
\langle AX, Y \rangle = {}^t(AX)\bar{Y} = {}^tX {}^tA \bar{Y} = {}^tX \overline{(\overline{{}^tA}\, Y)} = \langle X, {}^t\bar{A}\, Y \rangle.
$$

Thus $A^* = {}^t\bar{A}$.

An operator $A$ is called **hermitian** (or **self-adjoint**) if $A^* = A$, i.e.:

$$
\langle Av, w \rangle = \langle v, Aw \rangle \quad \text{for all } v, w \in V.
$$

A complex square matrix $A$ is hermitian if ${}^t\bar{A} = A$ (equivalently ${}^tA = \bar{A}$).

### 7.2.2 Formal Properties of the Adjoint

**Theorem 2.3.** Let $A, B$ be operators and $\alpha \in \mathbf{C}$. Then:

| Formula | Statement |
|---------|-----------|
| **Sum** | $(A+B)^* = A^* + B^*$ |
| **Product** | $(AB)^* = B^* A^*$ |
| **Scalar** | $(\alpha A)^* = \bar{\alpha} A^*$ |
| **Double adjoint** | $A^{**} = A$ |

**Proof of scalar rule.** For all $v, w \in V$:

$$
\langle \alpha Av, w \rangle = \alpha \langle Av, w \rangle = \alpha \langle v, A^* w \rangle = \langle v, \bar{\alpha} A^* w \rangle.
$$

Hence $(\alpha A)^* = \bar{\alpha} A^*$. The other formulas follow similarly.

**Polarization identities.** For all $v, w \in V$:

$$
\begin{aligned}
\langle A(v+w), v+w \rangle - \langle A(v-w), v-w \rangle &= 2\big[\langle Aw, v \rangle + \langle Av, w \rangle\big], \\
\langle A(v+w), v+w \rangle - \langle Av, v \rangle - \langle Aw, w \rangle &= \langle Av, w \rangle + \langle Aw, v \rangle.
\end{aligned}
$$

(Verifications are trivial by expanding the left-hand sides.)

### 7.2.3 Characterizations of Hermitian Operators

**Theorem 2.4.** Let $A$ be an operator such that $\langle Av, v \rangle = 0$ for all $v \in V$. Then $A = O$.

**Proof.** By the second polarization identity, $\langle Aw, v \rangle + \langle Av, w \rangle = 0$ for all $v, w$. Replacing $v$ by $iv$ gives $-\langle Aw, v \rangle + \langle Av, w \rangle = 0$. Adding yields $2\langle Av, w \rangle = 0$, so $A = O$.

**Theorem 2.5.** Let $A$ be an operator. Then $A$ is hermitian if and only if $\langle Av, v \rangle$ is real for all $v \in V$.

**Proof.**
- ($\implies$) If $A = A^*$: $\langle Av, v \rangle = \langle v, Av \rangle = \overline{\langle Av, v \rangle}$, so the value is real.
- ($\impliedby$) If $\langle Av, v \rangle$ is real for all $v$:
  $$
  \langle Av, v \rangle = \overline{\langle Av, v \rangle} = \langle v, Av \rangle = \langle A^*v, v \rangle.
  $$
  Hence $\langle (A-A^*)v, v \rangle = 0$ for all $v$. By Theorem 2.4, $A - A^* = O$.

## 7.3 Unitary Operators

### 7.3.1 Real Unitary Operators

Let $V$ be a finite dimensional vector space over $\mathbf{R}$ with a positive definite scalar product.

A linear map $A: V \to V$ is **unitary** (or **orthogonal**) if:

$$
\langle Av, Aw \rangle = \langle v, w \rangle \quad \text{for all } v, w \in V.
$$

**Theorem 3.1.** The following conditions on $A$ are equivalent:

| Condition | Statement |
|-----------|-----------|
| **(1)** | $A$ is unitary. |
| **(2)** | $A$ preserves norms: $\|Av\| = \|v\|$ for all $v \in V$. |
| **(3)** | $A$ maps unit vectors to unit vectors. |

**Proof.** (1) $\implies$ (2) is trivial. For (2) $\implies$ (1):

$$
\langle A(v+w), A(v+w) \rangle - \langle A(v-w), A(v-w) \rangle = 4\langle Av, Aw \rangle.
$$

By (2), the left side equals $\langle v+w, v+w \rangle - \langle v-w, v-w \rangle = 4\langle v, w \rangle$. Hence $\langle Av, Aw \rangle = \langle v, w \rangle$.

A unitary map preserves perpendicularity. However, preserving perpendicularity alone does not imply unitary (e.g. $v \mapsto 2v$ over $\mathbf{R}$ preserves perpendicularity but not norms).

**Theorem 3.2.** $A$ is unitary if and only if:

$$
{}^tA A = I.
$$

**Proof.** $\langle Av, Aw \rangle = \langle v, w \rangle \iff \langle {}^tA A v, w \rangle = \langle v, w \rangle$ for all $v, w \iff {}^tA A = I$.

> Every unitary map is invertible: if $Av = O$, then $\|v\| = \|Av\| = 0$, so $v = O$.

For $V = \mathbf{R}^n$ with the usual dot product, a real matrix $A$ is unitary (orthogonal) iff ${}^tA A = I_n$, or equivalently ${}^tA = A^{-1}$.

**Example.** The only unitary maps of $\mathbf{R}^2$ into itself have matrices of the form:

$$
\begin{pmatrix}\cos\theta & -\sin\theta \\ \sin\theta & \cos\theta\end{pmatrix} \quad \text{or} \quad \begin{pmatrix}\cos\theta & \sin\theta \\ \sin\theta & -\cos\theta\end{pmatrix}.
$$

If the determinant is $1$, the matrix is necessarily of the first type, and the map is called a **rotation**.

### 7.3.2 Complex Unitary Operators

Let $V$ be a finite dimensional vector space over $\mathbf{C}$ with a positive definite hermitian product.

A linear map $A: V \to V$ is **unitary** if:

$$
\langle Av, Aw \rangle = \langle v, w \rangle \quad \text{for all } v, w \in V.
$$

The analogue of Theorem 3.1 holds verbatim.

**Theorem 3.3.** $A$ is unitary if and only if:

$$
A^* A = I.
$$

For $V = \mathbf{C}^n$ with the standard hermitian form, a complex matrix $A$ is unitary iff ${}^t\bar{A}\, A = I_n$, or equivalently $A^* = A^{-1}$.

### 7.3.3 Unitary Maps and Orthonormal Bases

**Theorem 3.4.** Let $V$ be over $\mathbf{R}$ (with positive definite scalar product) or over $\mathbf{C}$ (with positive definite hermitian product). Let $\{v_1, \dots, v_n\}$ be an orthonormal basis of $V$.

| | Statement |
|---|-----------|
| **(a)** | If $A$ is unitary, then $\{Av_1, \dots, Av_n\}$ is an orthonormal basis. |
| **(b)** | If $\{w_1, \dots, w_n\}$ is another orthonormal basis and $Av_i = w_i$ for all $i$, then $A$ is unitary. |

**Proof.** Immediate from the definitions.
---

[<- Previous: 6. Determinants](06-determinants.md) | [Next: 8. Eigenvectors and Eigenvalues ->](08-eigenvectors-and-eigenvalues.md)
