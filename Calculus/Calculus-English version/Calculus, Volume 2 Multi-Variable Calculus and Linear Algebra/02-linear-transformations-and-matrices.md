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
