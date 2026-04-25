[<- Previous: 15. Linear Spaces](15-linear-spaces.md)

# 16. Linear Transformations and Matrices

## 16.1 Linear Transformations

### 16.1.1 Definition

Let $V$ and $W$ be linear spaces over the same scalars. A function $T:V\to W$ is a **linear transformation** if:

| Property | Formula | Name |
|----------|---------|------|
| (a) | $T(x+y)=T(x)+T(y)$ | Additivity |
| (b) | $T(cx)=cT(x)$ | Homogeneity |

- Combined form: $T(ax+by)=aT(x)+bT(y)$ for all $x,y\in V$ and scalars $a,b$.
- Generalization by induction:
  $$
  T\Bigl(\sum_{i=1}^n a_i x_i\Bigr)=\sum_{i=1}^n a_i T(x_i).
  $$

**Terminology:**
- $T(x)$ is the **image** of $x$ under $T$.
- $T$ **maps** $x$ onto $T(x)$.
- For $A\subseteq V$, $T(A)=\{T(x):x\in A\}$ is the **image of $A$ under $T$**.
- $T(V)$ is the **range** of $T$.

### 16.1.2 Examples

**Example 1 — Identity transformation.** $T:V\to V$, $T(x)=x$ for all $x$. Denoted by $I$ or $I_V$.

**Example 2 — Zero transformation.** $T:V\to V$, $T(x)=O$ for all $x$. Denoted by $O$.

**Example 3 — Multiplication by a fixed scalar $c$.** $T:V\to V$, $T(x)=cx$.
- $c=1$: identity; $c=0$: zero transformation.

**Example 4 — Linear equations.** $T:V_n\to V_m$ defined by:
$$
y_i=\sum_{k=1}^n a_{ik}x_k \quad (i=1,2,\dots,m).
$$
Given $mn$ scalars $a_{ik}$, this maps $x=(x_1,\dots,x_n)$ to $y=(y_1,\dots,y_m)$.

**Example 5 — Inner product with a fixed element.** Let $V$ be a real Euclidean space and $z\in V$ fixed. Define $T:V\to\mathbb{R}$ by $T(x)=(x,z)$.

**Example 6 — Projection on a subspace.** Let $S$ be a finite-dimensional subspace of a Euclidean space $V$. Define $T:V\to S$ by $T(x)=$ projection of $x$ on $S$.

**Example 7 — Differentiation operator.** Let $V$ be the space of all real functions differentiable on $(a,b)$. Define $D:V\to W$ by $D(f)=f'$, where $W$ is the space of all derivatives.

**Example 8 — Integration operator.** Let $V=C[a,b]$. Define $T:V\to V$ by:
$$
g(x)=T(f)(x)=\int_a^x f(t)\,dt \quad\text{for }a\le x\le b.
$$

## 16.2 Null Space and Range

Throughout this section, $T:V\to W$ denotes a linear transformation.

### 16.2.1 The Range

**Theorem 16.1.** The range $T(V)$ is a **subspace** of $W$. Moreover, $T$ maps the zero element of $V$ onto the zero element of $W$.

**Proof sketch:**
- If $T(x),T(y)\in T(V)$, then $T(x)+T(y)=T(x+y)\in T(V)$.
- If $c$ is a scalar, $cT(x)=T(cx)\in T(V)$.
- Taking $c=0$ in $T(cx)=cT(x)$ gives $T(O)=O$.

### 16.2.2 The Null Space (Kernel)

**Definition.** The set of all elements in $V$ that $T$ maps onto $O$ is called the **null space** of $T$, denoted $N(T)$:
$$
N(T)=\{x\in V \mid T(x)=O\}.
$$
The null space is also called the **kernel** of $T$.

**Theorem 16.2.** The null space $N(T)$ is a **subspace** of $V$.

**Proof:** If $x,y\in N(T)$, then $T(x+y)=T(x)+T(y)=O+O=O$ and $T(cx)=cT(x)=cO=O$.

### 16.2.3 Null Spaces of the Examples in 16.1

| Example | Transformation | Null Space $N(T)$ |
|---------|---------------|-------------------|
| 1 | Identity $I$ | $\{O\}$ |
| 2 | Zero $O$ | $V$ |
| 3 | Multiplication by $c$ | $\{O\}$ if $c\neq 0$; $V$ if $c=0$ |
| 4 | Linear equations $y_i=\sum_k a_{ik}x_k$ | Solution space of $\sum_k a_{ik}x_k=0$ ($i=1,\dots,m$) |
| 5 | Inner product $(x,z)$ | $\{x\in V:(x,z)=0\}$ (orthogonal complement of $\operatorname{span}\{z\}$) |
| 6 | Projection on $S$ | $S^\perp$ (orthogonal complement of $S$) |
| 7 | Differentiation $D(f)=f'$ | All constant functions on $(a,b)$ |
| 8 | Integration $T(f)(x)=\int_a^x f(t)\,dt$ | $\{0\}$ (only the zero function) |

## 16.3 Nullity and Rank

### 16.3.1 Definitions

Let $T:V\to W$ be a linear transformation with $V$ finite-dimensional.

| Term | Symbol | Definition |
|------|--------|------------|
| **Nullity** of $T$ | $\operatorname{nullity}(T)$ | $\dim N(T)$ |
| **Rank** of $T$ | $\operatorname{rank}(T)$ | $\dim T(V)$ |

Since $N(T)$ is a subspace of the finite-dimensional space $V$, the nullity is well defined. The next theorem shows the rank is also finite.

### 16.3.2 Theorem 16.3 — Nullity Plus Rank

If $V$ is finite-dimensional, then $T(V)$ is finite-dimensional and:
$$
\dim N(T) + \dim T(V) = \dim V. \tag{16.1}
$$

In words: **nullity + rank = dimension of the domain**.

**Proof sketch:**
- Let $n=\dim V$ and let $\{e_1,\dots,e_k\}$ be a basis for $N(T)$, so $k=\dim N(T)$.
- By Theorem 15.7(a), extend to a basis of $V$:
  $$
  e_1,\dots,e_k,e_{k+1},\dots,e_{k+r}, \tag{16.2}
  $$
  where $k+r=n$.
- **Claim:** The $r$ elements $T(e_{k+1}),\dots,T(e_{k+r})$ form a basis for $T(V)$. \tag{16.3}

**Spanning:** If $y\in T(V)$, then $y=T(x)$ for some $x=\sum_{i=1}^{k+r}c_i e_i$. Since $T(e_1)=\dots=T(e_k)=O$,
$$
y=T(x)=\sum_{i=k+1}^{k+r}c_i T(e_i).
$$

**Independence:** Suppose $\sum_{i=k+1}^{k+r}c_i T(e_i)=O$. Then $T(\sum_{i=k+1}^{k+r}c_i e_i)=O$, so $\sum_{i=k+1}^{k+r}c_i e_i\in N(T)$. Hence it equals $\sum_{i=1}^k c_i e_i$ for some scalars. But the full set (16.2) is independent, so all $c_i=0$.

- Therefore $\dim T(V)=r$, and $k+r=n$ gives (16.1).

> **Note:** If $V$ is infinite-dimensional, then at least one of $N(T)$ or $T(V)$ is infinite-dimensional.

## 16.4 Algebraic Operations on Linear Transformations

### 16.4.1 Addition and Scalar Multiplication

Let $S,T:V\to W$ and let $c$ be a scalar. Define:
$$
(S+T)(x)=S(x)+T(x),\qquad (cT)(x)=cT(x) \quad\text{for all }x\in V. \tag{16.4}
$$

- The set of all linear transformations from $V$ to $W$ is denoted $\mathscr{L}(V,W)$.

**Theorem 16.4.** $\mathscr{L}(V,W)$ is a **linear space** under the operations (16.4).

- The zero element is the zero transformation $O$.
- The negative of $T$ is $(-1)T$.
- All ten linear-space axioms are satisfied.

### 16.4.2 Composition (Multiplication)

Let $T:U\to V$ and $S:V\to W$. The **composition** $ST:U\to W$ is defined by:
$$
(ST)(x)=S[T(x)] \quad\text{for all }x\in U.
$$

- Order matters: first apply $T$, then $S$.
- Composition is **not** commutative in general.

**Theorem 16.5 (Associative law).** If $T:U\to V$, $S:V\to W$, and $R:W\to X$, then:
$$
R(ST)=(RS)T.
$$

**Proof:** For each $x\in U$:
$$
[R(ST)](x)=R[(ST)(x)]=R[S[T(x)]]=[(RS)T](x).
$$

**Powers.** For $T:V\to V$:
$$
T^0=I,\qquad T^n=TT^{n-1}\quad (n\ge 1).
$$
- The associative law implies the **law of exponents**: $T^m T^n=T^{m+n}$ for all nonnegative integers $m,n$.

**Theorem 16.6 (Linearity of composition).** If $T:U\to V$ and $S:V\to W$ are linear, then $ST:U\to W$ is linear.

**Proof:** $(ST)(ax+by)=S[T(ax+by)]=S[aT(x)+bT(y)]=aS[T(x)]+bS[T(y)]=a(ST)(x)+b(ST)(y)$.

**Theorem 16.7 (Distributive laws).** Let $S,T\in\mathscr{L}(V,W)$ and $c$ a scalar.

**(a)** For any $R$ with values in $V$:
$$
(S+T)R=SR+TR,\qquad (cS)R=c(SR).
$$

**(b)** For any linear $R:W\to U$:
$$
R(S+T)=RS+RT,\qquad R(cS)=c(RS).
$$

## 16.5 Inverses

### 16.5.1 Left and Right Inverses

**Definition.** Let $T:V\to W$.

| Type | Condition | Formula |
|------|-----------|---------|
| **Left inverse** $S$ | $S:T(V)\to V$ and $S[T(x)]=x$ for all $x\in V$ | $ST=I_V$ |
| **Right inverse** $R$ | $R:T(V)\to V$ and $T[R(y)]=y$ for all $y\in T(V)$ | $TR=I_{T(V)}$ |

**Example (no left inverse, two right inverses).** Let $V=\{1,2\}$, $W=\{0\}$, and $T(1)=T(2)=0$.
- Two right inverses: $R(0)=1$ and $R'(0)=2$.
- No left inverse exists, since $S[T(1)]=S(0)=1$ and $S[T(2)]=S(0)=2$ would require $1=2$.

- Every function has **at least one right inverse** (choose any preimage for each $y\in T(V)$).
- Right inverses need not be unique (when some $y$ has multiple preimages).

### 16.5.2 Theorem 16.8 — Uniqueness of the Left Inverse

A function $T:V\to W$ has **at most one** left inverse. If $T$ has a left inverse $S$, then $S$ is also a right inverse.

**Proof sketch:**
- **Uniqueness:** Suppose $S$ and $S'$ are left inverses. For any $y\in T(V)$, write $y=T(x)$. Then $S(y)=S[T(x)]=x$ and $S'(y)=S'[T(x)]=x$, so $S(y)=S'(y)$.
- **Left implies right:** For $y\in T(V)$, write $y=T(x)$. Then $T[S(y)]=T[S[T(x)]]=T(x)=y$, so $S$ is a right inverse.

### 16.5.3 Theorem 16.9 — Existence of a Left Inverse

A function $T:V\to W$ has a left inverse **if and only if** $T$ is **one-to-one** on $V$; that is,
$$
x\neq y \quad\text{implies}\quad T(x)\neq T(y). \tag{16.5}
$$
Equivalently:
$$
T(x)=T(y) \quad\text{implies}\quad x=y. \tag{16.6}
$$

**Proof sketch:**
- ($\Rightarrow$) If $ST=I_V$ and $T(x)=T(y)$, apply $S$: $x=S[T(x)]=S[T(y)]=y$.
- ($\Leftarrow$) If $T$ is one-to-one, each $y\in T(V)$ has exactly one preimage $x$. Define $S(y)=x$ where $T(x)=y$. Then $S[T(x)]=x$, so $ST=I_V$.

### 16.5.4 Invertible Transformations

**Definition.** Let $T:V\to W$ be one-to-one. The **unique** left inverse of $T$ (which is also a right inverse) is denoted $T^{-1}$. We say $T$ is **invertible**, and call $T^{-1}$ the **inverse** of $T$.

- These results apply to arbitrary functions. The next sections specialize to linear transformations.

## 16.6 One-to-One Linear Transformations

### 16.6.1 Theorem 16.10 — Equivalent Conditions for One-to-One

Let $T:V\to W$ be a linear transformation. The following are **equivalent**:

**(a)** $T$ is one-to-one on $V$.

**(b)** $T$ is invertible and its inverse $T^{-1}:T(V)\to V$ is linear.

**(c)** $N(T)=\{O\}$; that is, $T(x)=O$ implies $x=O$.

**Proof sketch:**
- **(a)$\Rightarrow$(b):** Let $u,v\in T(V)$, so $u=T(x)$, $v=T(y)$. Then
  $$
  au+bv=aT(x)+bT(y)=T(ax+by).
  $$
  Applying $T^{-1}$: $T^{-1}(au+bv)=ax+by=aT^{-1}(u)+bT^{-1}(v)$, so $T^{-1}$ is linear.
- **(b)$\Rightarrow$(c):** If $T(x)=O$, apply $T^{-1}$: $x=T^{-1}(O)=O$.
- **(c)$\Rightarrow$(a):** If $T(u)=T(v)$, then $T(u-v)=O$, so $u-v=O$ by (c). Hence $u=v$.

### 16.6.2 Theorem 16.11 — Finite-Dimensional Characterizations

Let $T:V\to W$ be linear with $V$ finite-dimensional, $\dim V=n$. The following are **equivalent**:

**(a)** $T$ is one-to-one on $V$.

**(b)** $T$ preserves independence: if $e_1,\dots,e_p$ are independent in $V$, then $T(e_1),\dots,T(e_p)$ are independent in $T(V)$.

**(c)** $\dim T(V)=n$.

**(d)** If $\{e_1,\dots,e_n\}$ is a basis for $V$, then $\{T(e_1),\dots,T(e_n)\}$ is a basis for $T(V)$.

**Proof sketch:**
- **(a)$\Rightarrow$(b):** Suppose $\sum_{i=1}^p c_i T(e_i)=O$. By linearity, $T(\sum c_i e_i)=O$. By Theorem 16.10(c), $\sum c_i e_i=O$, so independence of $\{e_i\}$ gives $c_i=0$.
- **(b)$\Rightarrow$(c):** Take a basis $\{e_1,\dots,e_n\}$ of $V$. By (b), $\{T(e_i)\}$ are independent in $T(V)$, so $\dim T(V)\ge n$. By Theorem 16.3 (nullity + rank), $\dim T(V)\le n$. Hence $\dim T(V)=n$.
- **(c)$\Rightarrow$(d):** $\{T(e_i)\}$ spans $T(V)$ and there are $n=\dim T(V)$ of them, so they form a basis.
- **(d)$\Rightarrow$(a):** If $T(x)=O$, write $x=\sum c_i e_i$. Then $T(x)=\sum c_i T(e_i)=O$. By (d), $\{T(e_i)\}$ is independent, so all $c_i=0$ and $x=O$. Thus $N(T)=\{O\}$, and Theorem 16.10 gives (a).

## 16.7 Linear Transformations with Prescribed Values

### 16.7.1 Theorem 16.12 — Existence and Uniqueness

Let $\{e_1,\dots,e_n\}$ be a basis for an $n$-dimensional linear space $V$, and let $u_1,\dots,u_n$ be arbitrary elements in a linear space $W$. Then there is **one and only one** linear transformation $T:V\to W$ such that:
$$
T(e_k)=u_k \quad\text{for }k=1,2,\dots,n. \tag{16.7}
$$

This $T$ acts on an arbitrary element $x=\sum_{k=1}^n x_k e_k$ by:
$$
T(x)=\sum_{k=1}^n x_k u_k. \tag{16.8}
$$

**Proof sketch:**
- **Existence:** Define $T$ by (16.8). Linearity follows directly from the formula. If $x=e_k$, all components are 0 except the $k$th, which is 1, so $T(e_k)=u_k$.
- **Uniqueness:** Suppose $T'$ also satisfies $T'(e_k)=u_k$. Then for any $x=\sum x_k e_k$:
  $$
  T'(x)=\sum_{k=1}^n x_k T'(e_k)=\sum_{k=1}^n x_k u_k=T(x).
  $$
  Hence $T'=T$.

> A linear transformation is **completely determined** by its values on a basis.

### 16.7.2 Example in $V_2$

Determine $T:V_2\to V_2$ such that:
$$
T(i)=i+j,\qquad T(j)=2i-j.
$$

**Solution:** For $x=x_1 i+x_2 j$:
$$
T(x)=x_1 T(i)+x_2 T(j)=x_1(i+j)+x_2(2i-j)=(x_1+2x_2)i+(x_1-x_2)j.
$$

## 16.8 Matrix Representations of Linear Transformations

### 16.8.1 Construction of the Matrix

Let $T:V\to W$ with $\dim V=n$ and $\dim W=m$. Choose ordered bases $(e_1,\dots,e_n)$ for $V$ and $(w_1,\dots,w_m)$ for $W$.

Each $T(e_k)$ can be written uniquely as:
$$
T(e_k)=\sum_{i=1}^m t_{ik}w_i.
$$

The scalars $t_{ik}$ form the **components** of $T(e_k)$ relative to $(w_1,\dots,w_m)$. Arranging these as column vectors side by side gives the $m\times n$ **matrix representation** of $T$:
$$
(t_{ik})=\begin{bmatrix}t_{11}&t_{12}&\cdots&t_{1n}\\t_{21}&t_{22}&\cdots&t_{2n}\\\vdots&\vdots&&\vdots\\t_{m1}&t_{m2}&\cdots&t_{mn}\end{bmatrix}.
$$

- First subscript $i$ = row, second subscript $k$ = column.
- Column $k$ contains the components of $T(e_k)$.

### 16.8.2 Theorem 16.13 — Matrix Action on Components

Let $x=\sum_{k=1}^n x_k e_k$ with components $(x_1,\dots,x_n)$. Then $T(x)=\sum_{i=1}^m y_i w_i$ where:
$$
y_i=\sum_{k=1}^n t_{ik}x_k \quad\text{for }i=1,2,\dots,m. \tag{16.13}
$$

**Proof:**
$$
T(x)=\sum_{k=1}^n x_k T(e_k)=\sum_{k=1}^n x_k\sum_{i=1}^m t_{ik}w_i=\sum_{i=1}^m\Bigl(\sum_{k=1}^n t_{ik}x_k\Bigr)w_i.
$$

> **One-to-one correspondence:** Every linear transformation $T:V\to W$ determines a unique $m\times n$ matrix $(t_{ik})$ (for fixed bases). Conversely, every $m\times n$ matrix determines a unique linear transformation via (16.10).

### 16.8.3 Example 1 — From Matrix to Transformation

Given the $2\times 3$ matrix:
$$
\begin{bmatrix}3&1&-2\\1&0&4\end{bmatrix},
$$
with the usual unit coordinate-vector bases for $V_3$ and $V_2$. This represents $T:V_3\to V_2$ where:
$$
y_1=3x_1+x_2-2x_3,\qquad y_2=x_1+4x_3.
$$

### 16.8.4 Example 2 — From Transformation to Matrix

Let $D$ be the differentiation operator from the space $V$ of polynomials of degree $\le 3$ (dimension 4, basis $\{1,x,x^2,x^3\}$) to the space $W$ of polynomials of degree $\le 2$ (dimension 3, basis $\{1,x,x^2\}$).

Compute images of basis elements:
$$
D(1)=0,\quad D(x)=1,\quad D(x^2)=2x,\quad D(x^3)=3x^2.
$$

Reading off coefficients as **columns**:
$$
\begin{bmatrix}0&1&0&0\\0&0&2&0\\0&0&0&3\end{bmatrix}.
$$

**Effect of basis ordering:**
- If $W$ uses basis $(x^2,x,1)$ instead, the matrix becomes:
  $$
  \begin{bmatrix}0&0&0&3\\0&0&2&0\\0&1&0&0\end{bmatrix}.
  $$
- If $V$ uses basis $(1,1+x,1+x+x^2,1+x+x^2+x^3)$ and $W$ uses $(1,x,x^2)$:
  $$
  \begin{bmatrix}0&1&1&1\\0&0&2&2\\0&0&0&3\end{bmatrix}.
  $$

## 16.9 Diagonal Form of Matrix Representations

### 16.9.1 Theorem 16.14 — Diagonalization

Let $V$ and $W$ be finite-dimensional with $\dim V=n$, $\dim W=m$, and let $T\in\mathscr{L}(V,W)$ have rank $r=\dim T(V)$. Then there exist a basis $(e_1,\dots,e_n)$ for $V$ and a basis $(w_1,\dots,w_m)$ for $W$ such that:
$$
T(e_i)=w_i \quad\text{for }i=1,2,\dots,r, \tag{16.14}
$$
and
$$
T(e_i)=O \quad\text{for }i=r+1,\dots,n. \tag{16.15}
$$

Therefore, the matrix $(t_{ik})$ of $T$ relative to these bases has all entries zero except the first $r$ diagonal entries:
$$
t_{11}=t_{22}=\dots=t_{rr}=1.
$$

**Proof sketch:**
1. **Basis for $W$:** Since $\dim T(V)=r$, choose a basis $w_1,\dots,w_r$ for $T(V)$ and extend it to a basis for $W$:
   $$
   (w_1,\dots,w_r,w_{r+1},\dots,w_m). \tag{16.16}
   $$

2. **First $r$ basis elements of $V$:** For each $w_i$ ($i\le r$), choose $e_i\in V$ with $T(e_i)=w_i$.

3. **Remaining basis elements of $V$:** Let $k=\dim N(T)$. By Theorem 16.3, $n=k+r$. Choose a basis $e_{r+1},\dots,e_{r+k}$ for $N(T)$. Then $T(e_i)=O$ for $i>r$.

4. **Independence of $(e_1,\dots,e_r,e_{r+1},\dots,e_{r+k})$:** \tag{16.17}
   Suppose $\sum_{i=1}^{r+k}c_i e_i=O$ (16.18). Applying $T$:
   $$
   \sum_{i=1}^{r+k}c_i T(e_i)=\sum_{i=1}^r c_i w_i=O.
   $$
   Since $w_1,\dots,w_r$ are independent, $c_1=\dots=c_r=0$.
   The remaining sum $\sum_{i=r+1}^{r+k}c_i e_i=O$ implies $c_{r+1}=\dots=c_{r+k}=0$ because $e_{r+1},\dots,e_{r+k}$ form a basis for $N(T)$.

5. Since $\dim V=n=r+k$, these $n$ independent elements form a basis for $V$.

### 16.9.2 Example — Differentiation Operator in Diagonal Form

Let $D$ map polynomials of degree $\le 3$ (space $V$, $\dim V=4$) to polynomials of degree $\le 2$ (space $W$, $\dim W=3$).

- $T(V)=W$, so $\operatorname{rank}(D)=3$.
- Choose basis for $W$: $(1,x,x^2)$.
- Preimages in $V$: $D(x)=1$, $D(\tfrac{1}{2}x^2)=x$, $D(\tfrac{1}{3}x^3)=x^2$.
- Null space $N(D)$: constant polynomials, basis $(1)$.
- Basis for $V$: $(x,\tfrac{1}{2}x^2,\tfrac{1}{3}x^3,1)$.
- Matrix representation:
  $$
  \begin{bmatrix}1&0&0&0\\0&1&0&0\\0&0&1&0\end{bmatrix}.
  $$

## 16.10 Linear Spaces of Matrices

### 16.10.1 Definition and Notation

An $m\times n$ **matrix** is a function $A$ whose domain is the set of pairs $I_{m,n}=\{(i,j):1\le i\le m,\;1\le j\le n\}$. The value $A(i,j)$ is called the **$ij$-entry** (or $ij$-element) and is denoted $a_{ij}$.

| Type | Condition |
|------|-----------|
| **Square matrix** | $m=n$ |
| **Row matrix** | $m=1$ |
| **Column matrix** | $n=1$ |

Compact notation: $A=(a_{ij})$ or $A=(a_{ij})_{i,j=1}^{m,n}$.

Two matrices are **equal** iff they have the same size and $a_{ij}=b_{ij}$ for all $(i,j)$.

### 16.10.2 Addition and Scalar Multiplication

**Definition.** For $m\times n$ matrices $A=(a_{ij})$ and $B=(b_{ij})$, and scalar $c$:
$$
A+B=(a_{ij}+b_{ij}),\qquad cA=(ca_{ij}).
$$
Addition is defined **only** when $A$ and $B$ have the same size.

**Example:**
$$
A=\begin{bmatrix}1&2&-3\\-1&0&4\end{bmatrix},\quad B=\begin{bmatrix}5&0&1\\1&-2&3\end{bmatrix}
$$
gives
$$
A+B=\begin{bmatrix}6&2&-2\\0&-2&7\end{bmatrix},\quad 2A=\begin{bmatrix}2&4&-6\\-2&0&8\end{bmatrix},\quad (-1)B=\begin{bmatrix}-5&0&-1\\-1&2&-3\end{bmatrix}.
$$

### 16.10.3 The Space $M_{m,n}$

The collection of all $m\times n$ matrices (with real or complex entries) is a **linear space**, denoted $M_{m,n}$.

- The **zero matrix** $O$ has all entries equal to 0.
- **Dimension:** $\dim M_{m,n}=mn$.
- **Basis:** The $mn$ matrices $E_{ij}$ having 1 in position $(i,j)$ and 0 elsewhere.
  - Example: a basis for $2\times 3$ matrices consists of the six matrices:
    $$
    \begin{bmatrix}1&0&0\\0&0&0\end{bmatrix},\;
    \begin{bmatrix}0&1&0\\0&0&0\end{bmatrix},\;
    \begin{bmatrix}0&0&1\\0&0&0\end{bmatrix},\;
    \begin{bmatrix}0&0&0\\1&0&0\end{bmatrix},\;
    \begin{bmatrix}0&0&0\\0&1&0\end{bmatrix},\;
    \begin{bmatrix}0&0&0\\0&0&1\end{bmatrix}.
    $$

## 16.11 Isomorphism Between Linear Transformations and Matrices

### 16.11.1 The Mapping $m:\mathscr{L}(V,W)\to M_{m,n}$

Fix ordered bases $(e_1,\dots,e_n)$ for $V$ and $(w_1,\dots,w_m)$ for $W$. For $T\in\mathscr{L}(V,W)$, define $m(T)$ to be its matrix representation:
$$
T(e_k)=\sum_{i=1}^m t_{ik}w_i \quad\Rightarrow\quad m(T)=(t_{ik})_{i,k=1}^{m,n}. \tag{16.19–16.20}
$$

This defines a function $m:\mathscr{L}(V,W)\to M_{m,n}$ whose range is all of $M_{m,n}$ (every matrix represents some $T$).

### 16.11.2 Theorem 16.15 — Isomorphism Theorem

For all $S,T\in\mathscr{L}(V,W)$ and scalars $c$:
$$
m(S+T)=m(S)+m(T),\qquad m(cT)=cm(T).
$$
Moreover,
$$
m(S)=m(T) \quad\text{implies}\quad S=T,
$$
so $m$ is **one-to-one** on $\mathscr{L}(V,W)$.

**Proof sketch:**
- Let $S(e_k)=\sum_i s_{ik}w_i$ and $T(e_k)=\sum_i t_{ik}w_i$. Then
  $$
  (S+T)(e_k)=S(e_k)+T(e_k)=\sum_i(s_{ik}+t_{ik})w_i,
  $$
  so $m(S+T)=(s_{ik}+t_{ik})=m(S)+m(T)$. Similarly $m(cT)=cm(T)$.
- If $m(S)=m(T)$, then $S(e_k)=T(e_k)$ for every basis element $e_k$. By Theorem 16.12 (prescribed values), $S=T$.

### 16.11.3 Consequences

- The function $m$ is an **isomorphism** between $\mathscr{L}(V,W)$ and $M_{m,n}$.
- Addition and scalar multiplication are preserved under this correspondence.
- Since $m$ is one-to-one and onto:
  $$
  \dim\mathscr{L}(V,W)=\dim M_{m,n}=mn.
  $$
- **Identity matrix:** If $V=W$ and the same basis is used, the matrix of the identity transformation $I:V\to V$ is the $n\times n$ diagonal matrix with 1s on the diagonal. This is called the **identity** (or **unit**) matrix, denoted $I$ or $I_n$.

## 16.12 Multiplication of Matrices

### 16.12.1 Definition

Let $A=(a_{ij})$ be $m\times p$ and $B=(b_{ij})$ be $p\times n$. The **product** $AB=C$ is the $m\times n$ matrix with entries:
$$
c_{ij}=\sum_{k=1}^p a_{ik}b_{kj}. \tag{16.22}
$$

- $AB$ is defined **only when** the number of columns of $A$ equals the number of rows of $B$.
- **Row–column interpretation:** $c_{ij}=A_i\cdot B^j$, the dot product of the $i$th row of $A$ with the $j$th column of $B$.

**Example 1:**
$$
A=\begin{bmatrix}3&1&2\\-1&1&0\end{bmatrix}\;(2\times 3),\quad B=\begin{bmatrix}4&6\\5&-1\\0&2\end{bmatrix}\;(3\times 2)
\quad\Rightarrow\quad AB=\begin{bmatrix}17&21\\1&-7\end{bmatrix}.
$$

**Example 2:**
$$
A=\begin{bmatrix}2&1&-3\\1&2&4\end{bmatrix},\quad B=\begin{bmatrix}-2\\1\\2\end{bmatrix}
\quad\Rightarrow\quad AB=\begin{bmatrix}-9\\8\end{bmatrix}.
$$

**Example 3 (noncommutativity):**
$$
A=\begin{bmatrix}1&2\\-1&1\end{bmatrix},\quad B=\begin{bmatrix}3&4\\5&2\end{bmatrix}
\quad\Rightarrow\quad AB=\begin{bmatrix}13&8\\2&-2\end{bmatrix},\quad BA=\begin{bmatrix}-1&10\\3&12\end{bmatrix}.
$$
In general $AB\neq BA$. If $AB=BA$, we say $A$ and $B$ **commute**.

**Example 4 (identity matrix):**
$$
I_3\begin{bmatrix}2\\3\\4\end{bmatrix}=\begin{bmatrix}2\\3\\4\end{bmatrix},\qquad
\begin{bmatrix}1&2&3\\4&5&6\end{bmatrix}I_3=\begin{bmatrix}1&2&3\\4&5&6\end{bmatrix}.
$$

### 16.12.2 Theorem 16.16 — Matrix of a Composition

Let $T:U\to V$ and $S:V\to W$ be linear transformations. For fixed bases,
$$
m(ST)=m(S)\,m(T).
$$

**Proof sketch:** Let $m(S)=(s_{ik})$ and $m(T)=(t_{kj})$. Then
$$
ST(u_j)=S[T(u_j)]=S\Bigl(\sum_k t_{kj}v_k\Bigr)=\sum_k t_{kj}S(v_k)=\sum_k t_{kj}\sum_i s_{ik}w_i=\sum_i\Bigl(\sum_k s_{ik}t_{kj}\Bigr)w_i.
$$
Hence the $ij$-entry of $m(ST)$ is $\sum_k s_{ik}t_{kj}$, which is exactly the $ij$-entry of $m(S)m(T)$.

### 16.12.3 Theorem 16.17 — Algebraic Laws

**(a) Associative law:** If $A(BC)$ and $(AB)C$ are meaningful,
$$
A(BC)=(AB)C.
$$

**(b) Distributive laws:** If $A,B$ have the same size and the products are meaningful,
$$
(A+B)C=AC+BC \quad\text{(right distributive)},
$$
$$
C(A+B)=CA+CB \quad\text{(left distributive)}.
$$

**Proof sketch:** Introduce linear transformations $R,S,T$ with $A=m(R)$, $B=m(S)$, $C=m(T)$. The matrix laws follow from the corresponding laws for composition of transformations (Theorems 16.5 and 16.7), using Theorem 16.16.

### 16.12.4 Powers of a Square Matrix

For a square matrix $A$:
$$
A^0=I,\qquad A^n=AA^{n-1}\quad (n\ge 1).
$$

## 16.13 Systems of Linear Equations

### 16.13.1 Formulation

A **system of $m$ linear equations in $n$ unknowns** has the form:
$$
\sum_{k=1}^n a_{ik}x_k=c_i \quad\text{for }i=1,2,\dots,m. \tag{16.23}
$$

- $A=(a_{ij})$ is the **coefficient matrix**.
- A **solution** is an $n$-tuple $(x_1,\dots,x_n)$ satisfying all equations.

In terms of the linear transformation $T:V_n\to V_m$ defined by $y_i=\sum_k a_{ik}x_k$, the system becomes:
$$
T(x)=c,\quad\text{where }c=(c_1,\dots,c_m).
$$

| Condition | Meaning |
|-----------|---------|
| Has a solution | $c\in T(V)$ (range of $T$) |
| Exactly one solution | $T$ is one-to-one |
| More than one solution | $\dim N(T)\ge 1$ |

**Examples:**
- **No solution:** $x+y=1$, $x+y=2$.
- **Exactly one solution:** $x+y=1$, $x-y=0$ $\Rightarrow$ $(x,y)=(\tfrac12,\tfrac12)$.
- **More than one solution:** $x+y=1$ (one equation, two unknowns).

### 16.13.2 Homogeneous and Nonhomogeneous Systems

The system obtained by setting all $c_i=0$:
$$
\sum_{k=1}^n a_{ik}x_k=0 \quad (i=1,\dots,m)
$$
is called the **homogeneous system** corresponding to (16.23). Its solution set is exactly the **null space** $N(T)$.

A system with $c\neq O$ is called **nonhomogeneous**.

### 16.13.3 Theorem 16.18 — Relation Between Solutions

Assume the nonhomogeneous system $T(x)=c$ has a particular solution $b$.

**(a)** If $x$ is any solution of the nonhomogeneous system, then $v=x-b$ is a solution of the homogeneous system.

**(b)** If $v$ is any solution of the homogeneous system, then $x=v+b$ is a solution of the nonhomogeneous system.

**Proof:** $T(v)=T(x-b)=T(x)-T(b)=c-c=O$.

> Thus, finding all solutions of a nonhomogeneous system splits into:
> 1. Find one particular solution $b$.
> 2. Find all solutions of the homogeneous system (the null space $N(T)$).

### 16.13.4 General Solution

Let $k=\dim N(T)$ (the nullity of $T$). If $v_1,\dots,v_k$ is a basis for $N(T)$, then:

- **General solution of the homogeneous system:**
  $$
  v=t_1v_1+\dots+t_kv_k,\quad t_i\text{ arbitrary scalars}.
  $$

- **General solution of the nonhomogeneous system:**
  $$
  x=b+t_1v_1+\dots+t_kv_k.
  $$

**Example:** The system $x+y=2$.
- Homogeneous: $x+y=0$, null space = $\{(t,-t)\}=\operatorname{span}\{(1,-1)\}$.
- Particular solution: $b=(0,2)$.
- General solution: $(x,y)=(0,2)+t(1,-1)$, or $x=t$, $y=2-t$.

## 16.14 Computation Techniques — Gauss-Jordan Elimination

### 16.14.1 Row Operations

To solve a linear system computationally, we apply three **elementary row operations** on the **augmented matrix** $[A|c]$:

1. **Interchange** two rows.
2. **Multiply** a row by a nonzero scalar.
3. **Add** a multiple of one row to another.

These operations produce an **equivalent system** (same solution set).

### 16.14.2 Example 1 — Unique Solution

Solve:
$$
\begin{cases}
2x-5y+4z=-3\\
x-2y+\phantom{0}z=\phantom{-}5\\
x-4y+6z=10
\end{cases}
$$

**Augmented matrix:**
$$
\left[\begin{array}{ccc|c}
2&-5&4&-3\\1&-2&1&5\\1&-4&6&10
\end{array}\right]. \tag{16.24}
$$

**Step 1:** Swap $R_1\leftrightarrow R_2$, then $R_2\leftarrow R_2-2R_1$, $R_3\leftarrow R_3-R_1$:
$$
\left[\begin{array}{ccc|c}
1&-2&1&5\\0&-1&2&-13\\0&-2&5&5
\end{array}\right]. \tag{16.26}
$$

**Step 2:** $R_2\leftarrow -R_2$, then $R_3\leftarrow R_3+2R_2$:
$$
\left[\begin{array}{ccc|c}
1&-2&1&5\\0&1&-2&13\\0&0&1&31
\end{array}\right]. \tag{16.27}
$$

**Back-substitution:** $z=31$, $y=13+2z=75$, $x=5+2y-z=124$.

Or continue to **reduced row-echelon form**:
$$
\left[\begin{array}{ccc|c}
1&0&0&124\\0&1&0&75\\0&0&1&31
\end{array}\right]. \tag{16.25}
$$

### 16.14.3 Example 2 — More Than One Solution

System of 3 equations in 5 unknowns (same left part as Example 1):
$$
\begin{cases}
2x-5y+4z+\phantom{0}u-v=-3\\
x-2y+\phantom{0}z-\phantom{0}u+v=\phantom{-}5\\
x-4y+6z+2u-v=10
\end{cases} \tag{16.28}
$$

Row reduction yields:
$$
\left[\begin{array}{ccccc|c}
1&0&0&-16&19&124\\0&1&0&-9&11&75\\0&0&1&-3&4&31
\end{array}\right].
$$

Solving for the leading variables $x,y,z$ in terms of free variables $u,v$:
$$
x=124+16u-19v,\quad y=75+9u-11v,\quad z=31+3u-4v.
$$

Let $u=t_1$, $v=t_2$. The general solution is:
$$
(x,y,z,u,v)=(124,75,31,0,0)+t_1(16,9,3,1,0)+t_2(-19,-11,-4,0,1).
$$

- $(124,75,31,0,0)$ is a **particular solution**.
- $(16,9,3,1,0)$ and $(-19,-11,-4,0,1)$ are independent solutions of the homogeneous system, forming a basis for $N(T)$.

### 16.14.4 Example 3 — No Solution

System differing from Example 1 only in the $(3,3)$ entry:
$$
\begin{cases}
2x-5y+4z=-3\\
x-2y+\phantom{0}z=\phantom{-}5\\
x-4y+5z=10
\end{cases} \tag{16.29}
$$

Same row operations lead to:
$$
\left[\begin{array}{ccc|c}
1&-2&1&5\\0&1&-2&13\\0&0&0&31
\end{array}\right]. \tag{16.30}
$$

The last row states $0=31$, a contradiction. **No solution exists.**

### 16.14.5 Overdetermined Systems

If there are **more equations than unknowns**, the Gauss-Jordan process still applies.

- If an added equation is satisfied by the existing solution, the augmented matrix acquires a **row of zeros** at the bottom.
- If an added equation is **not** satisfied, the bottom row becomes $[0\;\dots\;0\;|\;a]$ with $a\neq 0$, indicating **no solution**.

## 16.15 Inverses of Square Matrices

### 16.15.1 Nonsingular Matrices

**Definition.** A square $n\times n$ matrix $A$ is **nonsingular** if there exists an $n\times n$ matrix $B$ such that $BA=I$. Such $B$ is called a **left inverse** of $A$.

Let $T:V_n\to V_n$ be the linear transformation with matrix $m(T)=A$ (using the standard basis).

**Theorem 16.20.** $A$ is nonsingular **if and only if** $T$ is invertible. Moreover, if $BA=I$, then $B=m(T^{-1})$.

**Proof sketch:**
- ($\Rightarrow$) Assume $BA=I$. If $T(x)=O$, let $X$ be the column of components of $x$. Then $AX=O$, so $B(AX)=IX=X=O$. Hence $x=O$ and $T$ is one-to-one, therefore invertible. From $TT^{-1}=I$ we get $Am(T^{-1})=I$; left-multiplying by $B$ gives $m(T^{-1})=B$.
- ($\Leftarrow$) If $T$ is invertible, then $m(T^{-1})m(T)=I$, so $A$ is nonsingular.

**Properties:**
- A nonsingular matrix has a **unique** inverse, denoted $A^{-1}$.
- If $AB=I$, then $B=A^{-1}$ (left inverse = right inverse).
- $(A^{-1})^{-1}=A$.

### 16.15.2 Computing the Inverse

Let $A=(a_{ij})$ be nonsingular with inverse $A^{-1}=(b_{ij})$. The defining equation $AA^{-1}=I$ gives:
$$
\sum_{k=1}^n a_{ik}b_{kj}=\delta_{ij}, \tag{16.31}
$$
where $\delta_{ij}=1$ if $i=j$ and $0$ otherwise (Kronecker delta).

For each fixed $j$, this is a linear system with coefficient matrix $A$ and right-hand side $e_j$ (the $j$th unit coordinate vector). Solving these $n$ systems yields the $n$ columns of $A^{-1}$.

**Practical method — Gauss-Jordan on $[A\,|\,I]$:**

Since all $n$ systems share the same coefficient matrix $A$, solve them simultaneously:

1. Form the **augmented matrix** $[A\,|\,I]$.
2. Apply row operations to reduce the left block to $I$.
3. If successful, the right block becomes $A^{-1}$:
   $$
   [A\,|\,I] \xrightarrow{\text{row ops}} [I\,|\,A^{-1}].
   $$

> **Note:** It is not necessary to know in advance whether $A$ is nonsingular. If $A$ is **singular** (not nonsingular), the Gauss-Jordan process will at some stage produce a zero on the diagonal, and it will be impossible to transform $A$ into $I$.

[<- Previous: 15. Linear Spaces](15-linear-spaces.md)
