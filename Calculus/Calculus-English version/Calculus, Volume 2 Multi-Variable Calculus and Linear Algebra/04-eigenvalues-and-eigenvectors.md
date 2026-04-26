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
