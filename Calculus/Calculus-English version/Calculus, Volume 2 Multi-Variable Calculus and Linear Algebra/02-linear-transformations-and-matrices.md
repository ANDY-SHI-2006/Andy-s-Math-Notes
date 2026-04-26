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
