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
