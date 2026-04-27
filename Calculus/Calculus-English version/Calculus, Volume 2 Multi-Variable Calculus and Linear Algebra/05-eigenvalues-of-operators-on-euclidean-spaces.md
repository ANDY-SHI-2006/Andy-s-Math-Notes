# Chapter 5 Eigenvalues of Operators Acting on Euclidean Spaces


### 5.1 Eigenvalues and Inner Products

**Inner-product axioms.**

*Real Euclidean space:*
- **(1)** $(x,y)=(y,x)$ &nbsp;(symmetry)
- **(2)** $(x+z,y)=(x,y)+(z,y)$ &nbsp;(linearity)
- **(3)** $(cx,y)=c(x,y)$ &nbsp;(homogeneity)
- **(4)** $(x,x)>0$ if $x\neq O$ &nbsp;(positivity)

*Complex Euclidean space:*
- **(1$'$)** $(x,y)=\overline{(y,x)}$ &nbsp;(Hermitian symmetry)
- **(2)** Same linearity in the first argument
- **(3)** $(cx,y)=c(x,y)$ for complex $c$
- **(3$'$)** $(x,cy)=\bar c(x,y)$
- **(4)** $(x,x)>0$ if $x\neq O$ (meaningful because $(x,x)$ is real)

---

**Theorem 5.1.** Let $E$ be a Euclidean space, $V$ a subspace of $E$, and $T\colon V\to E$ a linear transformation having an eigenvalue $\lambda$ with eigenvector $x$. Then

$$\lambda=\frac{(T(x),x)}{(x,x)}.$$

- **Proof.** $T(x)=\lambda x$ gives $(T(x),x)=(\lambda x,x)=\lambda(x,x)$; divide by $(x,x)\neq0$. $\square$

From Hermitian symmetry we also obtain the companion formula

$$\bar\lambda=\frac{(x,T(x))}{(x,x)}.$$

Hence:
- $\lambda$ is **real** $\iff$ $(T(x),x)=(x,T(x))$.
- $\lambda$ is **pure imaginary** $\iff$ $(T(x),x)=-(x,T(x))$.


### 5.2 Hermitian and Skew-Hermitian Transformations

**Definition.** Let $E$ be a Euclidean space and $V$ a subspace of $E$.
- $T\colon V\to E$ is **Hermitian** (or **symmetric** in the real case) if
  $$(T(x),y)=(x,T(y))\quad\text{for all }x,y\in V.$$
- $T$ is **skew-Hermitian** (or **skew-symmetric** in the real case) if
  $$(T(x),y)=-(x,T(y))\quad\text{for all }x,y\in V.$$

---

**Examples.**

1. **Symmetry and skew-symmetry in $C(a,b)$.** With $(f,g)=\int_a^b f(t)g(t)\,dt$:
   - Symmetric: $\displaystyle\int_a^b\{f(t)Tg(t)-g(t)Tf(t)\}\,dt=0$.
   - Skew-symmetric: $\displaystyle\int_a^b\{f(t)Tg(t)+g(t)Tf(t)\}\,dt=0$.

2. **Multiplication by a fixed function.** $T(f)=pf$ is symmetric because the integrand in the symmetry condition is identically zero.

3. **Differentiation operator** $D(f)=f'$ on the subspace $V=\{f\in C(a,b)\mid f(a)=f(b)\}$. Integration by parts gives
   $$\int_a^b\{f(t)g'(t)+g(t)f'(t)\}\,dt=f(b)g(b)-f(a)g(a)=0,$$
   so $D$ is skew-symmetric. The only eigenfunctions in $V$ are the constant functions (eigenvalue $0$).

4. **Sturm–Liouville operator.** Let $V$ consist of all $f$ with a continuous second derivative on $[a,b]$ satisfying
   $$p(a)f(a)=0,\qquad p(b)f(b)=0$$
   for a fixed $p\in C(a,b)$ with continuous derivative. With another fixed $q\in C(a,b)$, define
   $$T(f)=(pf')'+qf.$$
   Then $T$ is symmetric on $V$. Its eigenfunctions are the nonzero solutions of
   $$(pf')'+qf=\lambda f$$
   satisfying the above boundary conditions.


### 5.3 Eigenvalues and Eigenvectors of Hermitian and Skew-Hermitian Operators

**Theorem 5.2.** Assume $T$ has an eigenvalue $\lambda$.

- **(a)** If $T$ is Hermitian, $\lambda$ is real: $\lambda=\bar\lambda$.
- **(b)** If $T$ is skew-Hermitian, $\lambda$ is pure imaginary: $\lambda=-\bar\lambda$.

- **Proof.** From Theorem 5.1,
  $$\lambda=\frac{(T(x),x)}{(x,x)},\qquad\bar\lambda=\frac{(x,T(x))}{(x,x)}.$$
  For Hermitian $T$ we have $(T(x),x)=(x,T(x))$, so $\lambda=\bar\lambda$. For skew-Hermitian $T$ we have $(T(x),x)=-(x,T(x))$, so $\lambda=-\bar\lambda$. $\square$

> In the real case, a symmetric operator has real eigenvalues (no new restriction). A real skew-symmetric operator must have eigenvalues that are both real and pure imaginary, hence all its eigenvalues are $0$ (if any exist).


### 5.4 Orthogonality of Eigenvectors Corresponding to Distinct Eigenvalues

**Theorem 5.3.** Let $T$ be Hermitian or skew-Hermitian, and let $\lambda,\mu$ be distinct eigenvalues with eigenvectors $x,y$. Then $x$ and $y$ are orthogonal: $(x,y)=0$.

- **Proof.** We have
  $$(T(x),y)=(\lambda x,y)=\lambda(x,y),\qquad(x,T(y))=(x,\mu y)=\bar\mu(x,y).$$
  If $T$ is Hermitian, $\lambda(x,y)=\bar\mu(x,y)=\mu(x,y)$; since $\lambda\neq\mu$, $(x,y)=0$. If $T$ is skew-Hermitian, $\lambda(x,y)=-\bar\mu(x,y)=\mu(x,y)$, and again $(x,y)=0$. $\square$

**Example.** For the Sturm–Liouville equation $(pf')'+qf=\lambda f$ with boundary conditions $p(a)f(a)=p(b)f(b)=0$, any two eigenfunctions belonging to distinct eigenvalues are orthogonal. In particular, for $f''+k^2f=0$ on $[0,\pi]$ with $f(0)=f(\pi)=0$, the nonzero solutions are $f(t)=\sin nt$ ($n=\pm1,\pm2,\dots$). Theorem 5.3 yields the familiar orthogonality relation
  $$\int_0^\pi\sin nt\,\sin mt\,dt=0\qquad(m\neq n).$$


### 5.6 Existence of an Orthonormal Set of Eigenvectors

**Theorem 5.4.** Let $\dim V=n$ and let $T\colon V\to V$ be Hermitian or skew-Hermitian. Then there exist $n$ eigenvectors $u_1,\dots,u_n$ of $T$ which form an **orthonormal basis** for $V$. Hence the matrix of $T$ relative to this basis is the diagonal matrix $\Lambda=\operatorname{diag}(\lambda_1,\dots,\lambda_n)$.

- **Proof sketch** (induction on $n$).
  - $n=1$: any eigenvector of norm 1 is an orthonormal basis.
  - Assume the theorem holds for dimension $n-1$. Choose an eigenvalue $\lambda_1$ of $T$ and a corresponding eigenvector $u_1$ of norm 1. Let $S^\perp=\{x\in V\mid(x,u_1)=0\}$.
  - *Dimension.* Extend $u_1$ to a basis and orthonormalize; then $S^\perp$ is spanned by the remaining $n-1$ vectors, so $\dim S^\perp=n-1$.
  - *Invariance.* If $x\in S^\perp$ and $T$ is Hermitian,
    $$(T(x),u_1)=(x,T(u_1))=(x,\lambda_1u_1)=\lambda_1(x,u_1)=0,$$
    so $T(x)\in S^\perp$. (A similar calculation holds for skew-Hermitian $T$.)
  - Apply the induction hypothesis on $S^\perp$ to obtain $n-1$ orthonormal eigenvectors $u_2,\dots,u_n$. Then $(u_1,\dots,u_n)$ is an orthonormal basis for $V$. $\square$


### 5.7 Matrix Representations for Hermitian and Skew-Hermitian Operators

**Theorem 5.5.** Let $(e_1,\dots,e_n)$ be any basis for $V$ and $T\colon V\to V$ linear.

- **(a)** $T$ is Hermitian $\iff$ $(T(e_j),e_i)=(e_j,T(e_i))$ for all $i,j$.
- **(b)** $T$ is skew-Hermitian $\iff$ $(T(e_j),e_i)=-(e_j,T(e_i))$ for all $i,j$.

- **Proof sketch.** Write $x=\sum x_je_j$ and $y=\sum y_ie_i$. Then
  $$(T(x),y)=\sum_{j,i}x_j\bar y_i(T(e_j),e_i),\qquad(x,T(y))=\sum_{j,i}x_j\bar y_i(e_j,T(e_i)).$$
  Comparing coefficients gives the result. $\square$

---

**Theorem 5.6.** Let $(e_1,\dots,e_n)$ be an **orthonormal** basis and let $A=(a_{ij})$ be the matrix of $T$ relative to this basis.

- **(a)** $T$ is Hermitian $\iff$ $a_{ij}=\bar a_{ji}$ for all $i,j$.
- **(b)** $T$ is skew-Hermitian $\iff$ $a_{ij}=-\bar a_{ji}$ for all $i,j$.

- **Proof sketch.** Since $T(e_j)=\sum_k a_{kj}e_k$, taking the inner product with $e_i$ gives
  $$(T(e_j),e_i)=\sum_k a_{kj}(e_k,e_i)=a_{ij}.$$
  Conjugating and interchanging indices: $\bar a_{ji}=(e_j,T(e_i))$. Apply Theorem 5.5. $\square$


### 5.8 Hermitian and Skew-Hermitian Matrices. The Adjoint of a Matrix

**Definition.** A square matrix $A=(a_{ij})$ is **Hermitian** if $a_{ij}=\bar a_{ji}$ for all $i,j$; it is **skew-Hermitian** if $a_{ij}=-\bar a_{ji}$.

Let $\bar A$ denote the entrywise conjugate of $A$. Then
- $A$ is Hermitian $\iff$ $A=\bar A^{\,t}$.
- $A$ is skew-Hermitian $\iff$ $A=-\bar A^{\,t}$.

**Definition.** For any matrix $A$, the **adjoint** $A^*$ is the transpose of the conjugate:

$$A^*=\bar A^{\,t}.$$

Thus $A$ is Hermitian $\iff$ $A=A^*$ (also called **self-adjoint**), and skew-Hermitian $\iff$ $A=-A^*$.


### 5.9 Diagonalization of a Hermitian or Skew-Hermitian Matrix

**Theorem 5.7.** Every $n\times n$ Hermitian or skew-Hermitian matrix $A$ is similar to the diagonal matrix $\Lambda=\operatorname{diag}(\lambda_1,\dots,\lambda_n)$ of its eigenvalues. Moreover,

$$\Lambda=C^{-1}AC,$$

where $C$ is a nonsingular matrix whose inverse is its adjoint: $C^{-1}=C^*$.

- **Proof sketch.** Let $T$ be the transformation represented by $A$ relative to the standard orthonormal basis. By Theorem 5.4, $V$ has an orthonormal basis of eigenvectors $(u_1,\dots,u_n)$. The matrix $C$ relating the two bases satisfies $[u_1,\dots,u_n]=[e_1,\dots,e_n]C$. Since $(u_j,u_i)=\delta_{ji}$,
  $$(u_j,u_i)=\sum_k c_{kj}\bar c_{ki},$$
  which means $CC^*=I$. Hence $C^{-1}=C^*$. $\square$

> The $j$th column of $C$ consists of the components of the eigenvector $u_j$ (normalized) relative to the standard basis.

**Example.** The real Hermitian matrix $A=\begin{pmatrix}2&2\\2&5\end{pmatrix}$ has eigenvalues $1$ and $6$ with orthonormal eigenvectors $u_1=\frac1{\sqrt5}(2,-1)$ and $u_2=\frac1{\sqrt5}(1,2)$. Hence
$$C=\frac1{\sqrt5}\begin{pmatrix}2&1\\-1&2\end{pmatrix},\qquad C^{\!t}AC=\begin{pmatrix}1&0\\0&6\end{pmatrix}.$$


### 5.10 Unitary Matrices. Orthogonal Matrices

**Definition.** A square matrix $A$ is **unitary** if $AA^*=I$. It is **orthogonal** if $AA^t=I$.

> Every real unitary matrix is orthogonal (since $A^*=A^t$). By Theorem 5.7, Hermitian and skew-Hermitian matrices are diagonalized by unitary matrices; real Hermitian matrices are diagonalized by real orthogonal matrices.

**Definition.** A matrix $A$ is **symmetric** if $A=A^t$; it is **skew-symmetric** if $A=-A^t$.

| Property | Hermitian | skew-Hermitian | symmetric | skew-symmetric |
|----------|-----------|----------------|-----------|----------------|
| Diagonal entries | real | pure imaginary | arbitrary | $0$ |
| Real case | $A=A^t$ | $A=-A^t$ | $A=A^t$ | $A=-A^t$ |

**Examples.**

1. If $A$ is real, $A^*=A^t$. Thus every real Hermitian matrix is symmetric, but a symmetric matrix with complex entries need not be Hermitian.
2. $A=\begin{pmatrix}1+i&2\\3-i&4i\end{pmatrix}$ gives $\bar A=\begin{pmatrix}1-i&2\\3+i&-4i\end{pmatrix}$, $A^t=\begin{pmatrix}1+i&3-i\\2&4i\end{pmatrix}$, $A^*=\begin{pmatrix}1-i&3+i\\2&-4i\end{pmatrix}$.
3. Both $\begin{pmatrix}1&2\\2&3\end{pmatrix}$ and $\begin{pmatrix}1&2+i\\2-i&3\end{pmatrix}$ are Hermitian; the first is symmetric, the second is not.
4. Both $\begin{pmatrix}0&-2\\2&0\end{pmatrix}$ and $\begin{pmatrix}i&-2\\2&3i\end{pmatrix}$ are skew-Hermitian; the first is skew-symmetric, the second is not.

---

**Decompositions.** Every square matrix $A$ can be written uniquely as
- $A=B+C$ where $B=\tfrac12(A+A^*)$ is Hermitian and $C=\tfrac12(A-A^*)$ is skew-Hermitian.
- $A=S+K$ where $S=\tfrac12(A+A^t)$ is symmetric and $K=\tfrac12(A-A^t)$ is skew-symmetric.

**Example.** If $A$ is orthogonal, then $1=\det(AA^t)=(\det A)^2$, so $\det A=\pm1$.

### 5.12 Quadratic Forms

Let $V$ be a **real** Euclidean space and let $T:V\to V$ be a symmetric operator ($(T(x),y)=(x,T(y))$). The real-valued function
$$Q(x)=(T(x),x)$$
is called the **quadratic form associated with $T$**.

**Theorem 5.8.** Let $(e_1,\dots,e_n)$ be an orthonormal basis for $V$, $T$ symmetric with matrix $A=(a_{ij})$. Then
$$Q(x)=\sum_{i=1}^n\sum_{j=1}^n a_{ij}x_i x_j \quad\text{if } x=\sum_{i=1}^n x_i e_i.\tag{5.7}$$

- *Proof sketch:* $T(x)=\sum x_i T(e_i)$; then $(T(x),x)=\sum_{i,j}x_i x_j(T(e_i),e_j)=\sum_{i,j}a_{ij}x_i x_j$ since $a_{ij}=(T(e_i),e_j)$.

**Definition.** Given any orthonormal basis and any $n\times n$ matrix $A=(a_{ij})$, the function
$$Q(x)=\sum_{i=1}^n\sum_{j=1}^n a_{ij}x_i x_j\tag{5.8}$$
is the **quadratic form associated with $A$**.

- If $A$ is diagonal, $Q(x)=\sum_{i=1}^n a_{ii}x_i^2$, called a **diagonal form**.

**Theorem 5.9.** Let $X=[x_1,\dots,x_n]$ be a $1\times n$ row matrix. Then $XAX^t$ is a $1\times 1$ matrix with entry
$$\sum_{i=1}^n\sum_{j=1}^n a_{ij}x_i x_j.\tag{5.9}$$

- *Proof sketch:* $XA=[y_1,\dots,y_n]$ with $y_j=\sum_i x_i a_{ij}$; then $XAX^t=\sum_j y_j x_j=\sum_{i,j}a_{ij}x_i x_j$.

It is customary to identify the $1\times 1$ matrix with its entry and write simply $Q(x)=XAX^t$.

**Example 1.** $A=\begin{bmatrix}1&-1\\-3&5\end{bmatrix}$, $X=[x_1,x_2]$.
$$XAX^t=x_1^2-4x_1x_2+5x_2^2.$$

**Example 2.** $B=\begin{bmatrix}1&-2\\-2&5\end{bmatrix}$, $X=[x_1,x_2]$.
$$XBX^t=x_1^2-4x_1x_2+5x_2^2.$$

- Different matrices can yield the same quadratic form; only the symmetric part matters.

**Theorem 5.10.** For any $n\times n$ matrix $A$ and row $X$,
$$XAX^t=XBX^t,\quad B=\tfrac12(A+A^t).$$

- *Proof sketch:* $(XAX^t)^t=XA^tX^t$, so $XAX^t=\frac12XAX^t+\frac12XA^tX^t=XBX^t$.

### 5.13 Reduction of a Real Quadratic Form to a Diagonal Form

A real symmetric matrix $A$ is Hermitian, so by Theorem 5.7 it is similar to $\Lambda=\operatorname{diag}(\lambda_1,\dots,\lambda_n)$ and $\Lambda=C^tAC$ with $C$ orthogonal. This $C$ converts $XAX^t$ to a diagonal form.

**Theorem 5.11.** Let $XAX^t$ be the quadratic form of a real symmetric matrix $A$, and let $C$ be orthogonal with $\Lambda=C^tAC$. Then
$$XAX^t=Y\Lambda Y^t=\sum_{i=1}^n\lambda_i y_i^2,$$
where $Y=XC$ and $\lambda_1,\dots,\lambda_n$ are the eigenvalues of $A$.

- *Proof sketch:* $C^{-1}=C^t$, so $Y=XC\Rightarrow X=YC^t$. Then $XAX^t=(YC^t)A(YC^t)^t=Y(C^tAC)Y^t=Y\Lambda Y^t$.

- The transformation $Y=XC$ **reduces** the quadratic form to diagonal form.

**Example 1.** For the identity matrix, $XIX^t=\sum x_i^2=\|X\|^2$. Under $Y=XC$ with $C$ orthogonal, $\Lambda=CIC^t=I$, so $\|X\|^2=\|Y\|^2$. A linear transformation preserving every vector length is called an **isometry**.

**Example 2.** Reduce $Q(x)=2x_1^2+4x_1x_2+5x_2^2$.

- $A=\begin{bmatrix}2&2\\2&5\end{bmatrix}$; eigenvalues $\lambda_1=1$, $\lambda_2=6$.
- Orthonormal eigenvectors: $u_1=\frac1{\sqrt5}(2,-1)$, $u_2=\frac1{\sqrt5}(1,2)$.
- Orthogonal $C=\frac1{\sqrt5}\begin{bmatrix}2&1\\-1&2\end{bmatrix}$.
- Diagonal form: $Y\Lambda Y^t=y_1^2+6y_2^2$.

**Geometric interpretation.** The transformation $Y=XC$ rotates the basis $\{i,j\}$ onto $\{u_1,u_2\}$. The set $XAX^t=c$ is the same ellipse as $Y\Lambda Y^t=c$, i.e. $y_1^2+6y_2^2=c$ ($c>0$). In the original coordinates this is $2x_1^2+4x_1x_2+5x_2^2=c$.

### 5.14 Applications to Analytic Geometry

Reduction of a quadratic form to diagonal form identifies the set of points $(x,y)$ satisfying a Cartesian equation
$$ax^2+bxy+cy^2+dx+ey+f=0.\tag{5.10}$$
This set is always a **conic section** (ellipse, hyperbola, parabola, or a degenerate case). The type is governed by the second-degree terms, i.e. by the quadratic form $ax^2+bxy+cy^2$.

Writing $x_1=x$, $x_2=y$ and
$$XAX^t=ax_1^2+bx_1x_2+cx_2^2,\qquad A=\begin{bmatrix}a&b/2\\b/2&c\end{bmatrix},$$
a rotation $Y=XC$ reduces this to $\lambda_1y_1^2+\lambda_2y_2^2$, where $\lambda_1,\lambda_2$ are the eigenvalues of $A$. Relative to the new axes determined by orthonormal eigenvectors $u_1,u_2$, Equation (5.10) becomes
$$\lambda_1y_1^2+\lambda_2y_2^2+d'y_1+e'y_2+f=0.\tag{5.11}$$

- No mixed term $y_1y_2$ appears; the conic type is read off from $\lambda_1,\lambda_2$:
  - **Ellipse**: $\lambda_1,\lambda_2$ have the same sign ($\lambda_1\lambda_2>0$)
  - **Hyperbola**: $\lambda_1,\lambda_2$ have opposite signs ($\lambda_1\lambda_2<0$)
  - **Parabola**: either $\lambda_1$ or $\lambda_2$ is zero ($\lambda_1\lambda_2=0$)

**Example 1.** $2x^2+4xy+5y^2+4x+13y-\tfrac14=0$.

- Matrix $A=\begin{bmatrix}2&2\\2&5\end{bmatrix}$; eigenvalues $\lambda_1=1$, $\lambda_2=6$.
- Orthogonal $C=\frac1{\sqrt5}\begin{bmatrix}2&1\\-1&2\end{bmatrix}$.
- Rotation $X=YC^t$ gives $x_1=\frac1{\sqrt5}(2y_1+y_2)$, $x_2=\frac1{\sqrt5}(-y_1+2y_2)$.
- Linear part becomes $-\sqrt5\,y_1+6\sqrt5\,y_2$.
- Transformed equation: $y_1^2+6y_2^2-\sqrt5\,y_1+6\sqrt5\,y_2-\frac14=0$.
- Completing squares: $\bigl(y_1-\frac12\sqrt5\bigr)^2+6\bigl(y_2+\frac12\sqrt5\bigr)^2=9$.
- This is an **ellipse** with centre $\bigl(\frac12\sqrt5,-\frac12\sqrt5\bigr)$ in the $y_1y_2$-system.
- Translation $z_1=y_1-\frac12\sqrt5$, $z_2=y_2+\frac12\sqrt5$ yields standard form
  $$\frac{z_1^2}{9}+\frac{z_2^2}{3/2}=1.$$

**Example 2.** $2x^2-4xy-y^2-4x+10y-13=0$.

- Matrix $A=\begin{bmatrix}2&-2\\-2&-1\end{bmatrix}$; eigenvalues $\lambda_1=3$, $\lambda_2=-2$.
- Same eigenvectors; rotation as above gives
  $$3y_1^2-2y_2^2-\frac{18}{\sqrt5}y_1+\frac{16}{\sqrt5}y_2-13=0.$$
- Completing squares: $3\bigl(y_1-\frac35\sqrt5\bigr)^2-2\bigl(y_2-\frac45\sqrt5\bigr)^2=12$.
- This is a **hyperbola**; in translated $z_1z_2$-coordinates:
  $$\frac{z_1^2}{4}-\frac{z_2^2}{6}=1.$$

**Example 3.** $9x^2+24xy+16y^2-20x+15y=0$.

- Matrix $A=\begin{bmatrix}9&12\\12&16\end{bmatrix}$; eigenvalues $\lambda_1=25$, $\lambda_2=0$.
- Orthogonal $C=\frac15\begin{bmatrix}3&-4\\4&3\end{bmatrix}$.
- Transformed equation simplifies to $y_1^2+y_2=0$, a **parabola** with vertex at the origin.

**Example 4. Degenerate cases.** Eigenvalues alone do not reveal degeneracy.

- $x^2+2y^2=1$ (ellipse), $x^2+2y^2=0$ (single point), $x^2+2y^2=-1$ (empty set) all have the same eigenvalues.
- $y^2=0$ ($x$-axis) and $y^2-1=0$ (two parallel lines) are degenerate parabolas.
- $x^2-4y^2=0$ (two intersecting lines) is a degenerate hyperbola.

For a **nondegenerate** conic the type is determined by the sign of the product $\lambda_1\lambda_2$. The characteristic polynomial of $A$ is
$$\det\begin{bmatrix}\lambda-a&-b/2\\-b/2&\lambda-c\end{bmatrix}=\lambda^2-(a+c)\lambda+\Bigl(ac-\frac14b^2\Bigr).$$
Hence
$$\lambda_1\lambda_2=ac-\frac14b^2=\frac14(4ac-b^2).$$

The number $4ac-b^2$ is the **discriminant** of the quadratic form $ax^2+bxy+cy^2$:

| Discriminant | Conic type |
|---|---|
| $4ac-b^2>0$ | Ellipse |
| $4ac-b^2<0$ | Hyperbola |
| $4ac-b^2=0$ | Parabola |

(In Examples 1, 2, 3 the discriminant is $34$, $-24$, $0$ respectively.)
