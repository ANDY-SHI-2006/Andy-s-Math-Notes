# Chapter 2 Linear Transformations and Matrices


### 2.1 Linear Transformations

**Definition.** Let $V$ and $W$ be linear spaces over the same field of scalars. A function $T\colon V\to W$ is called a **linear transformation** (or linear operator) if it satisfies:

- **(a)** $T(x+y)=T(x)+T(y)$ &nbsp; for all $x,y\in V$
- **(b)** $T(cx)=c\,T(x)$ &nbsp; for all $x\in V$ and all scalars $c$

Equivalently, $T(ax+by)=aT(x)+bT(y)$ for all $x,y\in V$ and all scalars $a,b$. By induction,

$$T\Bigl(\sum_{i=1}^n a_i x_i\Bigr)=\sum_{i=1}^n a_i T(x_i)$$

for any $n$ elements $x_1,\dots,x_n\in V$ and scalars $a_1,\dots,a_n$.

---

**Examples of linear transformations**

| # | Name | Domain / Codomain | Formula |
|---|------|-------------------|---------|
| 1 | **Identity transformation** $I$ or $I_V$ | $V\to V$ | $T(x)=x$ |
| 2 | **Zero transformation** $O$ | $V\to V$ | $T(x)=O$ |
| 3 | **Multiplication by a fixed scalar** $c$ | $V\to V$ | $T(x)=cx$. ($c=1$: identity; $c=0$: zero) |
| 4 | **Linear equations** | $V_n\to V_m$ | $y_i=\sum_{k=1}^n a_{ik}x_k$ for $i=1,\dots,m$ |
| 5 | **Inner product with a fixed element** $z$ | real Euclidean $V\to\mathbb R$ | $T(x)=(x,z)$ |
| 6 | **Projection on a subspace** $S$ | Euclidean $V\to S$ | $T(x)=$ projection of $x$ on $S$ |
| 7 | **Differentiation operator** $D$ | differentiable functions on $(a,b)$ | $D(f)=f'$ |
| 8 | **Integration operator** | continuous functions on $[a,b]$ | $g(x)=\int_a^x f(t)\,dt$ |


### 2.2 Null Space and Range

**Theorem 2.1.** Let $T\colon V\to W$ be a linear transformation. Then the range $T(V)$ is a subspace of $W$. Moreover, $T$ maps the zero element of $V$ onto the zero element of $W$.

- **Proof sketch.** Closure under addition: $T(x)+T(y)=T(x+y)\in T(V)$. Closure under scalar multiplication: $cT(x)=T(cx)\in T(V)$. Taking $c=0$ gives $T(O)=O$. $\square$

**Definition.** The set of all elements in $V$ that $T$ maps onto $O$ is called the **null space** (or **kernel**) of $T$, denoted $N(T)$:

$$N(T)=\{x\in V\mid T(x)=O\}.$$

**Theorem 2.2.** The null space of $T$ is a subspace of $V$.

- **Proof sketch.** If $x,y\in N(T)$, then $T(x+y)=T(x)+T(y)=O$ and $T(cx)=cT(x)=O$, so $x+y$ and $cx$ belong to $N(T)$. $\square$

---

**Null spaces of the examples in Section 2.1**

| # | Transformation | Null space $N(T)$ |
|---|----------------|-------------------|
| 1 | Identity $I_V$ | $\{O\}$ |
| 2 | Zero transformation | $V$ |
| 3 | Multiplication by $c$ | $\{O\}$ if $c\neq0$; $V$ if $c=0$ |
| 4 | Linear equations $y_i=\sum_k a_{ik}x_k$ | Solution set of $\sum_k a_{ik}x_k=0$ for all $i$ |
| 5 | Inner product with fixed $z$ | Set of all elements orthogonal to $z$ |
| 6 | Projection on $S$ | $S^\perp$ (the orthogonal complement of $S$) |
| 7 | Differentiation $D$ | All constant functions on $(a,b)$ |
| 8 | Integration | $\{0\}$ (only the zero function) |


### 2.3 Nullity and Rank

**Definitions.** For a linear transformation $T\colon V\to W$:
- The **nullity** of $T$ is $\dim N(T)$.
- The **rank** of $T$ is $\dim T(V)$.

**Theorem 2.3** (Nullity plus rank theorem). If $V$ is finite-dimensional, then $T(V)$ is also finite-dimensional, and

$$\dim N(T)+\dim T(V)=\dim V.$$

In other words, $\text{nullity}+\text{rank}=\dim V$.

- **Proof sketch.** Let $n=\dim V$ and let $\{e_1,\dots,e_k\}$ be a basis for $N(T)$, so $k=\dim N(T)$. Extend it to a basis for $V$:

  $$e_1,\dots,e_k,\;e_{k+1},\dots,e_{k+r},\qquad k+r=n.$$

  **Spanning.** For any $y=T(x)\in T(V)$, write $x=\sum_{i=1}^{k+r}c_i e_i$. Then

  $$y=T(x)=\sum_{i=1}^{k+r}c_i T(e_i)=\sum_{i=k+1}^{k+r}c_i T(e_i),$$

  since $T(e_1)=\cdots=T(e_k)=O$. Thus $\{T(e_{k+1}),\dots,T(e_{k+r})\}$ spans $T(V)$.

  **Independence.** Suppose $\sum_{i=k+1}^{k+r}c_i T(e_i)=O$. Then $T\bigl(\sum_{i=k+1}^{k+r}c_i e_i\bigr)=O$, so $\sum_{i=k+1}^{k+r}c_i e_i\in N(T)$. Hence it can be written as $\sum_{i=1}^k c_i e_i$, giving

  $$\sum_{i=1}^k c_i e_i-\sum_{i=k+1}^{k+r}c_i e_i=O.$$

  Since the full basis is independent, all $c_i=0$. Therefore $\{T(e_{k+1}),\dots,T(e_{k+r})\}$ is a basis for $T(V)$, and $\dim T(V)=r=n-k$. $\square$

> **Note.** If $V$ is infinite-dimensional, then at least one of $N(T)$ or $T(V)$ is infinite-dimensional.


### 2.5 Algebraic Operations on Linear Transformations

**Definition.** Let $S,T\colon V\to W$ and let $c$ be a scalar. Define **sum** and **scalar product** pointwise:

$$(S+T)(x)=S(x)+T(x),\qquad (cT)(x)=c\,T(x)\quad\text{for all }x\in V.$$

Denote by $\mathscr L(V,W)$ the set of all linear transformations from $V$ into $W$.

**Theorem 2.4.** The set $\mathscr L(V,W)$, with the above operations, is a linear space. The zero transformation is the zero element, and $(-1)T$ is the negative of $T$.

---

**Composition (multiplication) of transformations**

Let $T\colon U\to V$ and $S\colon V\to W$. The **composition** $ST\colon U\to W$ is defined by

$$(ST)(x)=S[T(x)]\quad\text{for all }x\in U.$$

- Diagram: $U\xrightarrow{\,T\,}V\xrightarrow{\,S\,}W$.

**Theorem 2.5** (Associativity). If $T\colon U\to V$, $S\colon V\to W$, $R\colon W\to X$, then

$$R(ST)=(RS)T.$$

- **Proof sketch.** For every $x\in U$: $[R(ST)](x)=R[S[T(x)]]=[(RS)T](x)$. $\square$

**Powers.** For $T\colon V\to V$, define inductively

$$T^0=I,\qquad T^n=T\,T^{n-1}\quad(n\ge1).$$

Then $T^mT^n=T^{m+n}$ for all nonnegative integers $m,n$.

**Theorem 2.6.** The composition of linear transformations is linear. If $T\colon U\to V$ and $S\colon V\to W$ are linear, so is $ST\colon U\to W$.

- **Proof sketch.** $(ST)(ax+by)=S[T(ax+by)]=S[aT(x)+bT(y)]=aS[T(x)]+bS[T(y)]=a(ST)(x)+b(ST)(y)$. $\square$

**Theorem 2.7** (Distributive laws). Let $S,T\in\mathscr L(V,W)$ and $c$ a scalar.

- **(a)** For any $R$ with values in $V$:
  $$(S+T)R=SR+TR,\qquad (cS)R=c(SR).$$
- **(b)** For any linear $R\colon W\to U$:
  $$R(S+T)=RS+RT,\qquad R(cS)=c(RS).$$


### 2.6 Inverses

**Definitions.** Let $T\colon V\to W$ be a function.
- A function $S\colon T(V)\to V$ is a **left inverse** of $T$ if $S[T(x)]=x$ for all $x\in V$, i.e. $ST=I_V$.
- A function $R\colon T(V)\to V$ is a **right inverse** of $T$ if $T[R(y)]=y$ for all $y\in T(V)$, i.e. $TR=I_{T(V)}$.

> Every function has at least one right inverse (by the axiom of choice). Right inverses need not be unique if some $y\in T(V)$ has more than one pre-image.

**Example.** Let $V=\{1,2\}$, $W=\{0\}$, $T(1)=T(2)=0$. Then $R(0)=1$ and $R'(0)=2$ are two distinct right inverses, but no left inverse exists (it would require $1=S(0)=2$).

**Theorem 2.8.** A function $T\colon V\to W$ can have at most one left inverse. If $T$ has a left inverse $S$, then $S$ is also a right inverse (hence the unique two-sided inverse).

- **Proof sketch.** If $S,S'$ are left inverses and $y=T(x)$, then $S(y)=S[T(x)]=x=S'[T(x)]=S'(y)$, so $S=S'$. Also $T[S(y)]=T[S[T(x)]]=T(x)=y$, so $S$ is a right inverse. $\square$

**Theorem 2.9.** $T$ has a left inverse if and only if $T$ is **one-to-one** (injective) on $V$; that is,

$$x\neq y\implies T(x)\neq T(y)\quad\text{equivalently}\quad T(x)=T(y)\implies x=y.$$

- **Proof sketch.** $(\Rightarrow)$ If $T(x)=T(y)$, apply a left inverse $S$: $x=S[T(x)]=S[T(y)]=y$. $(\Leftarrow)$ If $T$ is injective, each $y\in T(V)$ equals $T(x)$ for a unique $x$; define $S(y)=x$. Then $S[T(x)]=x$, so $ST=I_V$. $\square$

**Definition.** If $T\colon V\to W$ is one-to-one, its unique left inverse (which is also its right inverse) is denoted $T^{-1}$. We say $T$ is **invertible** and call $T^{-1}$ the **inverse** of $T$.


### 2.7 One-to-One Linear Transformations

**Theorem 2.10.** Let $T\colon V\to W$ be a linear transformation in $\mathscr L(V,W)$. The following are equivalent:

- **(a)** $T$ is one-to-one on $V$.
- **(b)** $T$ is invertible and its inverse $T^{-1}\colon T(V)\to V$ is linear.
- **(c)** $N(T)=\{O\}$; that is, $T(x)=O$ implies $x=O$.

- **Proof sketch.**
  - (a)$\Rightarrow$(b): If $T$ is injective, $T^{-1}$ exists (Theorem 2.9). For $u=T(x),v=T(y)\in T(V)$,
    $$T^{-1}(au+bv)=T^{-1}\bigl(aT(x)+bT(y)\bigr)=T^{-1}\bigl(T(ax+by)\bigr)=ax+by=aT^{-1}(u)+bT^{-1}(v).$$
  - (b)$\Rightarrow$(c): If $T(x)=O$, then $x=T^{-1}(O)=O$ since $T^{-1}$ is linear.
  - (c)$\Rightarrow$(a): If $T(u)=T(v)$, then $T(u-v)=O$, so $u-v=O$ by (c), hence $u=v$. $\square$

---

**Theorem 2.11** (Finite-dimensional case; $\dim V=n$). Let $T\in\mathscr L(V,W)$. The following are equivalent:

- **(a)** $T$ is one-to-one on $V$.
- **(b)** Independence is preserved: if $e_1,\dots,e_p$ are independent in $V$, then $T(e_1),\dots,T(e_p)$ are independent in $T(V)$.
- **(c)** $\dim T(V)=n$ (rank equals $\dim V$).
- **(d)** Bases are mapped to bases: if $\{e_1,\dots,e_n\}$ is a basis for $V$, then $\{T(e_1),\dots,T(e_n)\}$ is a basis for $T(V)$.

- **Proof sketch.**
  - (a)$\Rightarrow$(b): $\sum c_i T(e_i)=O\implies T(\sum c_i e_i)=O\implies\sum c_i e_i=O\implies c_i=0$.
  - (b)$\Rightarrow$(c): Take a basis $\{e_1,\dots,e_n\}$ for $V$. By (b), $\{T(e_i)\}$ are independent, so $\dim T(V)\ge n$. By Theorem 2.3, $\dim T(V)\le n$. Hence $\dim T(V)=n$.
  - (c)$\Rightarrow$(d): $\{T(e_i)\}$ spans $T(V)$ because $T(x)=T(\sum c_i e_i)=\sum c_i T(e_i)$. Since $\dim T(V)=n$, it is a basis.
  - (d)$\Rightarrow$(a): If $T(x)=O$ with $x=\sum c_i e_i$, then $\sum c_i T(e_i)=O$. By (d) the $T(e_i)$ are independent, so all $c_i=0$, hence $x=O$. $\square$


### 2.9 Linear Transformations with Prescribed Values

**Theorem 2.12.** Let $\{e_1,\dots,e_n\}$ be a basis for an $n$-dimensional linear space $V$, and let $u_1,\dots,u_n$ be arbitrary elements in a linear space $W$. Then there exists one and only one linear transformation $T\colon V\to W$ such that

$$T(e_k)=u_k\qquad\text{for }k=1,2,\dots,n.$$

Moreover, if $x=\sum_{k=1}^n x_k e_k$, then

$$T(x)=\sum_{k=1}^n x_k u_k.$$

- **Proof sketch.**
  - *Existence:* Define $T$ by the formula above; linearity follows directly. For $x=e_k$, all $x_j=0$ except $x_k=1$, so $T(e_k)=u_k$.
  - *Uniqueness:* If $T'$ also satisfies $T'(e_k)=u_k$, then for any $x=\sum x_k e_k$,
    $$T'(x)=\sum_{k=1}^n x_k T'(e_k)=\sum_{k=1}^n x_k u_k=T(x).$$
    Hence $T'=T$. $\square$

**Example.** Determine $T\colon V_2\to V_2$ such that $T(\boldsymbol i)=\boldsymbol i+\boldsymbol j$ and $T(\boldsymbol j)=2\boldsymbol i-\boldsymbol j$.

If $x=x_1\boldsymbol i+x_2\boldsymbol j$, then by linearity

$$T(x)=x_1T(\boldsymbol i)+x_2T(\boldsymbol j)=x_1(\boldsymbol i+\boldsymbol j)+x_2(2\boldsymbol i-\boldsymbol j)=(x_1+2x_2)\boldsymbol i+(x_1-x_2)\boldsymbol j.$$


### 2.10 Matrix Representations of Linear Transformations

Let $T\in\mathscr L(V,W)$ with $\dim V=n$ and $\dim W=m$. Choose ordered bases $(e_1,\dots,e_n)$ for $V$ and $(w_1,\dots,w_m)$ for $W$. Each $T(e_k)$ can be written uniquely as

$$T(e_k)=\sum_{i=1}^m t_{ik}\,w_i\qquad(k=1,\dots,n).$$

The scalars $t_{ik}$ form an $m\times n$ **matrix** $(t_{ik})$ whose $k$th column contains the components of $T(e_k)$ relative to $(w_1,\dots,w_m)$. This is the **matrix representation of $T$** relative to the given bases.

**Theorem 2.13.** Let $x=\sum_{k=1}^n x_k e_k$ have components $(x_1,\dots,x_n)$ and let $T(x)=\sum_{i=1}^m y_i w_i$ have components $(y_1,\dots,y_m)$. Then

$$y_i=\sum_{k=1}^n t_{ik}\,x_k\qquad(i=1,\dots,m).$$

- **Proof sketch.** $T(x)=\sum_k x_k T(e_k)=\sum_k x_k\sum_i t_{ik}w_i=\sum_i\bigl(\sum_k t_{ik}x_k\bigr)w_i$. Comparing coefficients of $w_i$ yields the formula. $\square$

> **Correspondence.** Once bases are fixed, every linear transformation $T\colon V\to W$ determines a unique $m\times n$ matrix, and conversely every $m\times n$ matrix determines a unique linear transformation via (2.10) and Theorem 2.12.

---

**Example 1.** From a given $2\times3$ matrix $\begin{pmatrix}3&1&-2\\1&0&4\end{pmatrix}$ (usual bases for $V_3$ and $V_2$):

$$y_1=3x_1+x_2-2x_3,\qquad y_2=x_1+4x_3.$$

**Example 2.** Differentiation $D\colon V\to W$, where $V=\{\text{polynomials of degree }\le3\}$ (basis $1,x,x^2,x^3$) and $W=\{\text{polynomials of degree }\le2\}$ (basis $1,x,x^2$).

| $D$ applied to basis of $V$ | Result in basis of $W$ |
|----------------------------|------------------------|
| $D(1)=0$ | $(0,0,0)$ |
| $D(x)=1$ | $(1,0,0)$ |
| $D(x^2)=2x$ | $(0,2,0)$ |
| $D(x^3)=3x^2$ | $(0,0,3)$ |

Matrix (columns as above):
$$\begin{pmatrix}0&1&0&0\\0&0&2&0\\0&0&0&3\end{pmatrix}.$$

If the basis of $W$ is reordered to $(x^2,x,1)$, the matrix becomes
$$\begin{pmatrix}0&0&0&3\\0&0&2&0\\0&1&0&0\end{pmatrix}.$$

With $V$ basis $(1,\,1+x,\,1+x+x^2,\,1+x+x^2+x^3)$ and $W$ basis $(1,x,x^2)$:
$$D(1)=0,\;D(1+x)=1,\;D(1+x+x^2)=1+2x,\;D(1+x+x^2+x^3)=1+2x+3x^2,$$
giving matrix
$$\begin{pmatrix}0&1&1&1\\0&0&2&2\\0&0&0&3\end{pmatrix}.$$


### 2.11 Construction of a Matrix Representation in Diagonal Form

**Theorem 2.14.** Let $V$ and $W$ be finite-dimensional, $\dim V=n$, $\dim W=m$. Let $T\in\mathscr L(V,W)$ and let $r=\dim T(V)$ be its rank. Then there exist a basis $(e_1,\dots,e_n)$ for $V$ and a basis $(w_1,\dots,w_m)$ for $W$ such that

$$T(e_i)=w_i\quad\text{for }i=1,\dots,r,\qquad T(e_i)=O\quad\text{for }i=r+1,\dots,n.$$

Hence the matrix of $T$ relative to these bases has $t_{11}=\cdots=t_{rr}=1$ and all other entries zero.

- **Proof sketch.**
  1. *Basis for $W$.* Since $\dim T(V)=r$, pick a basis $w_1,\dots,w_r$ for $T(V)$ and extend it to a basis $(w_1,\dots,w_m)$ for $W$.
  2. *First $r$ basis vectors of $V$.* For each $w_i$ ($i\le r$) choose $e_i\in V$ with $T(e_i)=w_i$.
  3. *Remaining basis vectors of $V$.* Let $k=\dim N(T)=n-r$ (Theorem 2.3). Choose a basis $e_{r+1},\dots,e_{r+k}$ for $N(T)$.
  4. *Independence.* Suppose $\sum_{i=1}^{r+k}c_i e_i=O$. Applying $T$ gives $\sum_{i=1}^r c_i w_i=O$, so $c_1=\cdots=c_r=0$. Then $\sum_{i=r+1}^{r+k}c_i e_i=O$, and since these form a basis for $N(T)$, the remaining $c_i$ are also zero. Thus $(e_1,\dots,e_{r+k})$ is a basis for $V$. $\square$

**Example.** The differentiation operator $D\colon V\to W$ (polynomials of degree $\le3$ to degree $\le2$). Here $T(V)=W$, so $r=3$.

| Construction | Choice |
|-------------|--------|
| Basis for $W$ | $(1,\;x,\;x^2)$ |
| Pre-images in $V$ | $D(x)=1,\;D(\tfrac12x^2)=x,\;D(\tfrac13x^3)=x^2$ |
| Basis for $N(D)$ | $(1)$ (constants) |
| Basis for $V$ | $\bigl(x,\;\tfrac12x^2,\;\tfrac13x^3,\;1\bigr)$ |

Matrix representation:
$$\begin{pmatrix}1&0&0&0\\0&1&0&0\\0&0&1&0\end{pmatrix}.$$


### 2.13 Linear Spaces of Matrices

**Definition.** An $m\times n$ **matrix** $A=(a_{ij})$ is a function on the index set $I_{m,n}=\{(i,j)\mid1\le i\le m,\;1\le j\le n\}$; the value $a_{ij}=A(i,j)$ is the $ij$**-entry**.

| Term | Condition |
|------|-----------|
| **Square matrix** | $m=n$ |
| **Row matrix** | $1\times n$ |
| **Column matrix** | $m\times1$ |

Two matrices are **equal** iff they have the same size and $a_{ij}=b_{ij}$ for all $(i,j)$.

---

**Algebraic operations on matrices**

For $A=(a_{ij})$ and $B=(b_{ij})$ of the same size, and any scalar $c$:

$$A+B=(a_{ij}+b_{ij}),\qquad cA=(ca_{ij}).$$

**Example.**
$$A=\begin{pmatrix}1&2&-3\\-1&0&4\end{pmatrix},\quad B=\begin{pmatrix}5&0&1\\1&-2&3\end{pmatrix}$$
$$A+B=\begin{pmatrix}6&2&-2\\0&-2&7\end{pmatrix},\quad 2A=\begin{pmatrix}2&4&-6\\-2&0&8\end{pmatrix},\quad (-1)B=\begin{pmatrix}-5&0&-1\\-1&2&-3\end{pmatrix}.$$

---

**The space $M_{m,n}$.** The set of all $m\times n$ matrices (with real or complex entries) is a linear space denoted $M_{m,n}$.

- **Dimension:** $\dim M_{m,n}=mn$.
- **Standard basis:** the $mn$ matrices having a single entry $1$ and all others $0$. For $2\times3$ matrices the six basis matrices are
  $$\begin{pmatrix}1&0&0\\0&0&0\end{pmatrix},\;\begin{pmatrix}0&1&0\\0&0&0\end{pmatrix},\;\begin{pmatrix}0&0&1\\0&0&0\end{pmatrix},\;\begin{pmatrix}0&0&0\\1&0&0\end{pmatrix},\;\begin{pmatrix}0&0&0\\0&1&0\end{pmatrix},\;\begin{pmatrix}0&0&0\\0&0&1\end{pmatrix}.$$


### 2.14 Isomorphism between Linear Transformations and Matrices

Fix bases $(e_1,\dots,e_n)$ for $V$ and $(w_1,\dots,w_m)$ for $W$. For $T\in\mathscr L(V,W)$ write

$$T(e_k)=\sum_{i=1}^m t_{ik}\,w_i\qquad(k=1,\dots,n)$$

and define $m(T)=(t_{ik})$, the $m\times n$ matrix representation of $T$ relative to these bases. This defines a map

$$m\colon\mathscr L(V,W)\to M_{m,n}.$$

**Theorem 2.15** (Isomorphism theorem). For all $S,T\in\mathscr L(V,W)$ and all scalars $c$:

$$m(S+T)=m(S)+m(T),\qquad m(cT)=c\,m(T),$$

and

$$m(S)=m(T)\implies S=T.$$

Hence $m$ is a one-to-one linear transformation from $\mathscr L(V,W)$ onto $M_{m,n}$.

- **Proof sketch.** If $S(e_k)=\sum_i s_{ik}w_i$ and $T(e_k)=\sum_i t_{ik}w_i$, then
  $$(S+T)(e_k)=\sum_i(s_{ik}+t_{ik})w_i,\qquad (cT)(e_k)=\sum_i(ct_{ik})w_i,$$
  so the entries of $m(S+T)$ and $m(cT)$ are exactly $s_{ik}+t_{ik}$ and $ct_{ik}$. If $m(S)=m(T)$, then $S(e_k)=T(e_k)$ for every basis element, so $S=T$. Since every $m\times n$ matrix defines a unique linear transformation (Theorem 2.12), $m$ is onto. $\square$

> The map $m$ is called an **isomorphism**; the spaces $\mathscr L(V,W)$ and $M_{m,n}$ are **isomorphic**. Consequently, $\dim\mathscr L(V,W)=\dim M_{m,n}=mn$.

**Identity matrix.** If $V=W$ and the same basis is used, the matrix of the identity transformation $I\colon V\to V$ is the $n\times n$ diagonal matrix with every diagonal entry $1$ and all others $0$. This is called the **identity** (or **unit**) matrix, denoted $I$ or $I_n$.


### 2.15 Multiplication of Matrices

**Definition.** Let $A=(a_{ij})$ be $m\times p$ and $B=(b_{ij})$ be $p\times n$. Their **product** $AB=C$ is the $m\times n$ matrix with entries

$$c_{ij}=\sum_{k=1}^p a_{ik}\,b_{kj}\qquad(1\le i\le m,\;1\le j\le n).$$

- $AB$ is defined only when the number of columns of $A$ equals the number of rows of $B$.
- In dot-product form: $c_{ij}=A_i\cdot B^{j}$, the dot product of the $i$th row of $A$ with the $j$th column of $B$.

**Examples.**

1. $A=\begin{pmatrix}3&1&2\\-1&1&0\end{pmatrix}$ ($2\times3$), $B=\begin{pmatrix}4&6\\5&-1\\0&2\end{pmatrix}$ ($3\times2$):
   $$AB=\begin{pmatrix}17&21\\1&-7\end{pmatrix}.$$

2. $A=\begin{pmatrix}2&1&-3\\1&2&4\end{pmatrix}$ ($2\times3$), $B=\begin{pmatrix}-2\\1\\2\end{pmatrix}$ ($3\times1$):
   $$AB=\begin{pmatrix}-9\\8\end{pmatrix}.$$

3. Square matrices need not commute:
   $$A=\begin{pmatrix}1&2\\-1&1\end{pmatrix},\;B=\begin{pmatrix}3&4\\5&2\end{pmatrix}\implies AB=\begin{pmatrix}13&8\\2&-2\end{pmatrix},\;BA=\begin{pmatrix}-1&10\\3&12\end{pmatrix}.$$
   If $AB=BA$, we say $A$ and $B$ **commute**.

4. The identity matrix acts as a multiplicative identity:
   $$I_pA=A\quad(p\times n),\qquad BI_p=B\quad(m\times p).$$

---

**Theorem 2.16.** Let $T\colon U\to V$ and $S\colon V\to W$ be linear transformations (finite-dimensional). For fixed bases,

$$m(ST)=m(S)\,m(T).$$

- **Proof sketch.** With $\dim U=n$, $\dim V=p$, $\dim W=m$ and bases $(u_j),(v_k),(w_i)$, write
  $$S(v_k)=\sum_{i=1}^m s_{ik}w_i,\qquad T(u_j)=\sum_{k=1}^p t_{kj}v_k.$$
  Then
  $$ST(u_j)=S[T(u_j)]=\sum_{k=1}^p t_{kj}S(v_k)=\sum_{i=1}^m\Bigl(\sum_{k=1}^p s_{ik}t_{kj}\Bigr)w_i,$$
  so the $(i,j)$-entry of $m(ST)$ is $\sum_{k=1}^p s_{ik}t_{kj}$, which is exactly the $(i,j)$-entry of $m(S)m(T)$. $\square$

**Theorem 2.17** (Associative and distributive laws). Whenever the indicated products are defined:

- **(a)** $A(BC)=(AB)C$ &nbsp;(associative law)
- **(b)** $(A+B)C=AC+BC$ &nbsp;(right distributive law)
- **(c)** $C(A+B)=CA+CB$ &nbsp;(left distributive law)

- **Proof sketch.** Choose linear transformations $R,S,T$ whose matrices are $A,B,C$. The corresponding laws for transformations (Theorems 2.5 and 2.7) transfer to matrices via Theorem 2.16. $\square$

**Powers of a square matrix.** Define inductively

$$A^0=I,\qquad A^n=AA^{n-1}\quad(n\ge1).$$


### 2.17 Systems of Linear Equations

A **system of $m$ linear equations in $n$ unknowns** has the form

$$\sum_{k=1}^n a_{ik}\,x_k=c_i\qquad(i=1,\dots,m),$$

where $A=(a_{ij})$ is the **coefficient matrix**. In matrix form,

$$T(x)=c,$$

with $T\colon V_n\to V_m$ the linear transformation determined by $A$ and $c=(c_1,\dots,c_m)\in V_m$.

| Situation | Condition |
|-----------|-----------|
| No solution | $c\notin T(V)$ |
| Exactly one solution | Exactly one $x$ maps to $c$ |
| More than one solution | More than one $x$ maps to $c$ |

**Examples.**

1. **No solution:** $x+y=1,\;x+y=2$.
2. **Unique solution:** $x+y=1,\;x-y=0\implies(x,y)=(\tfrac12,\tfrac12)$.
3. **Infinitely many solutions:** $x+y=1$ (one equation, two unknowns).

---

**Homogeneous vs. nonhomogeneous systems**

- **Homogeneous:** $T(x)=O$. Always has the trivial solution $x=O$; its solution set is the null space $N(T)$.
- **Nonhomogeneous:** $T(x)=c$ with $c\neq O$.

**Theorem 2.18.** Suppose the nonhomogeneous system $T(x)=c$ has a particular solution $b$.

- **(a)** If $x$ solves $T(x)=c$, then $v=x-b$ solves $T(v)=O$.
- **(b)** If $v$ solves $T(v)=O$, then $x=v+b$ solves $T(x)=c$.

- **Proof sketch.** $T(v)=T(x-b)=T(x)-T(b)=c-c=O$, and conversely $T(v+b)=T(v)+T(b)=O+c=c$. $\square$

**General solution structure.** Let $k=\dim N(T)$ (the nullity) and let $v_1,\dots,v_k$ be a basis for $N(T)$. If $b$ is one particular solution of $T(x)=c$, then every solution has the form

$$x=b+t_1v_1+\cdots+t_kv_k,$$

with arbitrary scalars $t_1,\dots,t_k$.

**Theorem 2.19** restates this: the general solution of a nonhomogeneous system is a particular solution plus the general solution of the associated homogeneous system.

**Example.** For $x+y=2$:
- Homogeneous equation $x+y=0$ has null space spanned by $(1,-1)$.
- Particular solution: $(0,2)$.
- General solution: $(x,y)=(0,2)+t(1,-1)$, i.e. $x=t,\;y=2-t$.


### 2.18 Computation Techniques (Gauss–Jordan Elimination)

The **Gauss–Jordan elimination method** solves a linear system by performing three **elementary row operations** on its **augmented matrix** $[A\mid c]$:

1. Interchange two rows.
2. Multiply a row by a nonzero scalar.
3. Add a multiple of one row to another.

Each operation produces an **equivalent** system (same solution set). The goal is to reduce the augmented matrix to a form from which the solution can be read off directly.

---

**Example 1 — Unique solution.**

$$\begin{cases}2x-5y+4z=-3\\x-2y+\phantom{1}z=\phantom{-}5\\x-4y+6z=10\end{cases}$$

Augmented matrix and reduction steps:

$$\left[\begin{array}{rrr|r}2&-5&4&-3\\1&-2&1&5\\1&-4&6&10\end{array}\right]
\longrightarrow
\left[\begin{array}{rrr|r}1&-2&1&5\\0&-1&2&-13\\0&-2&5&5\end{array}\right]
\longrightarrow
\left[\begin{array}{rrr|r}1&-2&1&5\\0&1&-2&13\\0&0&1&31\end{array}\right]
\longrightarrow
\left[\begin{array}{rrr|r}1&0&0&124\\0&1&0&75\\0&0&1&31\end{array}\right].$$

Solution: $x=124,\;y=75,\;z=31$.

---

**Example 2 — Infinitely many solutions.** The same coefficients with two additional unknowns $u,v$:

$$\left[\begin{array}{rrrrr|r}1&0&0&-16&19&124\\0&1&0&-9&11&75\\0&0&1&-3&4&31\end{array}\right]$$

Solving for the leading variables:

$$\begin{aligned}x&=124+16u-19v,\\y&=\phantom{1}75+9u-11v,\\z&=\phantom{1}31+3u-4v.\end{aligned}$$

With free parameters $u=t_1$, $v=t_2$:

$$(x,y,z,u,v)=(124,75,31,0,0)+t_1(16,9,3,1,0)+t_2(-19,-11,-4,0,1).$$

The first vector is a particular solution; the last two form a basis for the homogeneous solution space.

---

**Example 3 — No solution.** Same as Example 1 except the $(3,3)$ entry is changed from $6$ to $5$:

$$\left[\begin{array}{rrr|r}1&-2&1&5\\0&1&-2&13\\0&0&0&31\end{array}\right].$$

The last row states $0=31$, a contradiction; the system is inconsistent.

---

**More equations than unknowns.** If an additional equation is also satisfied by the solution, elimination adds a row of zeros. If it is not satisfied, the bottom row becomes $[0\;\cdots\;0\mid a]$ with $a\neq0$, indicating no solution.
