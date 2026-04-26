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
