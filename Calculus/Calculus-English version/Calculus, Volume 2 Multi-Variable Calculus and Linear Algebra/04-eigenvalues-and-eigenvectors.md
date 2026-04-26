# Chapter 4 Eigenvalues and Eigenvectors


### 4.1 Linear Transformations with Diagonal Matrix Representations

Let $T\colon V\to V$ be a linear transformation on a finite-dimensional space $V$. Properties of $T$ that do not depend on the choice of basis are called **intrinsic properties**.

**Question.** Does every such $T$ have a diagonal matrix representation? In Chapter 2 (Theorem 2.14) a diagonal form was always possible when domain and codomain could use *different* bases. The new restriction here is that $V=W$ and the *same* basis must be used for both; with this restriction a diagonal representation is not always possible.

**Notation.** A diagonal matrix is written $A=\operatorname{diag}(a_{11},a_{22},\dots,a_{nn})$.

**Theorem 4.1.** Let $T\colon V\to V$ with $\dim V=n$.

- If $T$ has a diagonal matrix representation, then there exists an independent set $\{u_1,\dots,u_n\}$ in $V$ and scalars $\lambda_1,\dots,\lambda_n$ such that
  $$T(u_k)=\lambda_k u_k\qquad(k=1,\dots,n).$$
- Conversely, if independent elements $u_1,\dots,u_n$ and scalars $\lambda_1,\dots,\lambda_n$ satisfy the above, then $A=\operatorname{diag}(\lambda_1,\dots,\lambda_n)$ is a representation of $T$ relative to the basis $(u_1,\dots,u_n)$.

- **Proof sketch.** If $T$ is represented by a diagonal matrix $(a_{ik})$, then $T(e_k)=\sum_i a_{ik}e_i=a_{kk}e_k$. Conversely, if $T(u_k)=\lambda_k u_k$ with $\{u_k\}$ a basis, the matrix with $a_{kk}=\lambda_k$ and $a_{ik}=0$ ($i\neq k$) represents $T$. $\square$

> Thus the diagonalization problem is equivalent to finding independent elements $u_k$ and scalars $\lambda_k$ satisfying $T(u_k)=\lambda_k u_k$. Such $u_k$ are called **eigenvectors** and the corresponding $\lambda_k$ are called **eigenvalues** of $T$.


### 4.2 Eigenvectors and Eigenvalues of a Linear Transformation

**Definition.** Let $T\colon S\to V$ be linear ($S$ a subspace of $V$, not necessarily finite-dimensional). A scalar $\lambda$ is an **eigenvalue** of $T$ if there is a nonzero $x\in S$ such that

$$T(x)=\lambda x.$$

The element $x$ is an **eigenvector** belonging to $\lambda$. (By definition the zero vector is excluded.)

- Each eigenvector determines exactly one eigenvalue.

---

**Examples.**

1. **Multiplication by a fixed scalar $c$.** $T(x)=cx$. Every nonzero element is an eigenvector with eigenvalue $c$.

2. **Eigenspace $E(\lambda)$.** For an eigenvalue $\lambda$,
   $$E(\lambda)=\{x\in S\mid T(x)=\lambda x\}.$$
   $E(\lambda)$ is a subspace of $S$ (closed under linear combinations). If finite-dimensional, $\dim E(\lambda)\ge1$. Note: $E(\lambda)=N(T-\lambda I)$.

3. **Zero eigenvalue.** $0$ is an eigenvalue $\iff$ $N(T)$ contains a nonzero element.

4. **Reflection in the $xy$-plane** ($V=V_3(\mathbb R)$). $T(\boldsymbol i)=\boldsymbol i$, $T(\boldsymbol j)=\boldsymbol j$, $T(\boldsymbol k)=-\boldsymbol k$.
   - Eigenvalue $1$: every nonzero vector in the $xy$-plane.
   - Eigenvalue $-1$: vectors $c\boldsymbol k$ ($c\neq0$).

5. **Rotation of the plane through angle $\alpha$.**
   - Over $\mathbb C$: $T(z)=e^{i\alpha}z$; every $z\neq0$ is an eigenvector with eigenvalue $e^{i\alpha}$.
   - Over $\mathbb R$ ($V_2(\mathbb R)$): real eigenvalues exist only if $\alpha$ is an integer multiple of $\pi$. Otherwise there are no real eigenvalues or eigenvectors.

6. **Differentiation operator** $D(f)=f'$. Eigenvectors (eigenfunctions) satisfy $f'=\lambda f$, giving $f(x)=ce^{\lambda x}$ ($c\neq0$). The eigenvalue is $\lambda$.

7. **Integration operator** $T(f)(x)=\int_a^x f(t)\,dt$. The equation $\int_a^x f(t)\,dt=\lambda f(x)$ has no nonzero solutions (differentiation yields $f=\lambda f'$, but substituting $x=a$ forces $f=0$). Hence $T$ has no eigenfunctions.

8. **Subspace spanned by an eigenvector.** If $x$ is an eigenvector for $\lambda$, the line $L(x)=\{cx\}$ is mapped into itself by $T$:
   $$T(cx)=cT(x)=c\lambda x=\lambda(cx).$$
   Every nonzero element of $L(x)$ is also an eigenvector for $\lambda$.

**Definition.** A subspace $U\subseteq S$ is **invariant under $T$** if $T$ maps every element of $U$ into $U$. The subspace spanned by an eigenvector is invariant.


### 4.3 Linear Independence of Eigenvectors Corresponding to Distinct Eigenvalues

**Theorem 4.2.** Let $u_1,\dots,u_k$ be eigenvectors of $T\colon S\to V$ with distinct eigenvalues $\lambda_1,\dots,\lambda_k$. Then $u_1,\dots,u_k$ are independent.

- **Proof sketch** (induction on $k$). Assume $\sum_{i=1}^k c_iu_i=O$. Applying $T$ gives $\sum_{i=1}^k c_i\lambda_i u_i=O$. Subtracting $\lambda_k$ times the first equation yields
  $$\sum_{i=1}^{k-1}c_i(\lambda_i-\lambda_k)u_i=O.$$
  By the induction hypothesis $c_i(\lambda_i-\lambda_k)=0$ for $i<k$; since the eigenvalues are distinct, $c_i=0$ for $i<k$. Hence $c_k=0$ as well. $\square$

> **Warning.** The converse is false: independent eigenvectors need not have distinct eigenvalues (e.g. the identity transformation has only $\lambda=1$).

---

**Theorem 4.3.** If $\dim V=n$, every $T\colon V\to V$ has at most $n$ distinct eigenvalues. If $T$ has exactly $n$ distinct eigenvalues, the corresponding eigenvectors form a basis for $V$, and the matrix of $T$ relative to this basis is diagonal.

- **Proof sketch.** $n+1$ distinct eigenvalues would give $n+1$ independent vectors in an $n$-dimensional space, a contradiction. The second statement follows from Theorems 4.1 and 4.2. $\square$

> **Note.** $n$ distinct eigenvalues is a **sufficient** but not **necessary** condition for diagonalizability. The necessary and sufficient condition (Theorem 4.1) is the existence of $n$ independent eigenvectors.


### 4.5 The Finite-Dimensional Case. Characteristic Polynomials

If $\dim V=n$, the eigenvalue problem for $T\colon V\to V$ can be solved with determinants. The equation $T(x)=\lambda x$ is equivalent to

$$(\lambda I-T)(x)=O.$$

Let $T_\lambda=\lambda I-T$. Then $\lambda$ is an eigenvalue $\iff$ $T_\lambda$ is not invertible $\iff$ the matrix $\lambda I-A$ is singular, where $A$ is any matrix representation of $T$. By Theorem 3.13,

$$\lambda\text{ is an eigenvalue}\iff\det(\lambda I-A)=0.$$

---

**Theorem 4.4.** For any $n\times n$ matrix $A$, the function

$$f(\lambda)=\det(\lambda I-A)$$

is a polynomial in $\lambda$ of degree $n$. Its leading term is $\lambda^n$ and its constant term is $f(0)=\det(-A)=(-1)^n\det A$.

- **Verification.**
  - $n=1$: $f(\lambda)=\lambda-a_{11}$.
  - $n=2$: $f(\lambda)=(\lambda-a_{11})(\lambda-a_{22})-a_{12}a_{21}=\lambda^2-(\operatorname{tr}A)\lambda+\det A$.
  - $n=3$: expansion shows the highest-degree term is $\lambda^3$.

**Definition.** The polynomial $f(\lambda)=\det(\lambda I-A)$ is called the **characteristic polynomial** of $A$.

---

**Theorem 4.5.** Let $T\colon V\to V$ with $\dim V=n$, and let $A$ be a matrix representation of $T$ relative to some basis. Then the set of eigenvalues of $T$ consists of those roots of the characteristic polynomial of $A$ that lie in the scalar field $F$ ( $\mathbb R$ or $\mathbb C$).

> Although $A$ depends on the basis, the set of eigenvalues of $T$ does not. Hence the roots of the characteristic polynomial are basis-independent. In fact, the characteristic polynomial itself is independent of the basis (proved later).


### 4.6 Calculation of Eigenvalues and Eigenvectors in the Finite-Dimensional Case

Eigenvalues are the roots of $f(\lambda)=\det(\lambda I-A)$. For each eigenvalue $\lambda$, the eigenvectors are the nonzero solutions of

$$AX=\lambda X\qquad\text{or}\qquad(\lambda I-A)X=O.$$

---

**Example 1** — Distinct eigenvalues.
$$A=\begin{bmatrix}2&1&1\\2&3&4\\-1&-1&-2\end{bmatrix},\qquad f(\lambda)=(\lambda-1)(\lambda+1)(\lambda-3).$$

| $\lambda$ | Eigenvectors | $\dim E(\lambda)$ |
|-----------|-------------|-------------------|
| $1$ | $t(1,-1,0)$, $t\neq0$ | $1$ |
| $-1$ | $t(0,1,-1)$, $t\neq0$ | $1$ |
| $3$ | $t(2,3,-1)$, $t\neq0$ | $1$ |

The three eigenvectors are independent (Theorem 4.2).

---

**Example 2** — Repeated eigenvalue, one-dimensional eigenspace.
$$A=\begin{bmatrix}2&-1&1\\0&3&-1\\2&1&3\end{bmatrix},\qquad f(\lambda)=(\lambda-2)^2(\lambda-4).$$

| $\lambda$ | Eigenvectors | $\dim E(\lambda)$ |
|-----------|-------------|-------------------|
| $2$ (double) | $t(-1,1,1)$, $t\neq0$ | $1$ |
| $4$ | $t(1,-1,1)$, $t\neq0$ | $1$ |

Even though $\lambda=2$ is a double root, its eigenspace is only one-dimensional.

---

**Example 3** — Repeated eigenvalue, two-dimensional eigenspace.
$$A=\begin{bmatrix}2&1&1\\2&3&2\\3&3&4\end{bmatrix},\qquad f(\lambda)=(\lambda-1)^2(\lambda-7).$$

| $\lambda$ | Eigenvectors | $\dim E(\lambda)$ |
|-----------|-------------|-------------------|
| $7$ | $t(1,2,3)$, $t\neq0$ | $1$ |
| $1$ (double) | $a(1,0,-1)+b(0,1,-1)$, $a,b$ not both $0$ | $2$ |

Here there are three independent eigenvectors despite only two distinct eigenvalues.
