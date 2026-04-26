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
