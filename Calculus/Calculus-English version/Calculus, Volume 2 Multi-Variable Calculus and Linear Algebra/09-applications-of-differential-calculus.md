# Chapter 9 — Applications of Differential Calculus

### 9.1 Partial Differential Equations

An equation involving a scalar field $f$ and its partial derivatives is a **partial differential equation** (PDE).

**Examples.**
- First-order: $\dfrac{\partial f(x,y)}{\partial x}=0$.\tag{9.1}
- Second-order (2-D **Laplace equation**): $\dfrac{\partial^2f}{\partial x^2}+\dfrac{\partial^2f}{\partial y^2}=0$.\tag{9.2}

Both are homogeneous **linear** PDEs: $L(f)=0$ with $L$ a linear differential operator.

**Comparison with ODEs.**
- $f'(x)=0$ has 1-D solution space: $f(x)=C$.
- $\partial f/\partial x=0$ has **infinite-dimensional** solution space: $f(x,y)=g(y)$ for arbitrary $g$.
- In solving first-order PDEs, integration introduces an arbitrary function, leading to infinitely many independent solutions.

- A systematic study of existence/uniqueness with auxiliary conditions is beyond this text; only special cases are treated.
