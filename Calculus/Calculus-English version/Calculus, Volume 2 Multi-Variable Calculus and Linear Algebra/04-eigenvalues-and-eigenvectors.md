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
