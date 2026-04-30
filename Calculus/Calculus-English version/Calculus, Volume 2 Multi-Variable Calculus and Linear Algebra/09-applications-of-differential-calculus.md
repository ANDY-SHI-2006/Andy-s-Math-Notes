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


### 9.2 A First-Order Partial Differential Equation with Constant Coefficients

**Example.** $3\,\partial f/\partial x+2\,\partial f/\partial y=0$.
- Write as $(3i+2j)\cdot\nabla f=0$; the gradient is orthogonal to $3i+2j$.
- Level curves are straight lines parallel to $3i+2j$, i.e. $2x-3y=c$.
- Hence $f(x,y)=g(2x-3y)$ for arbitrary differentiable $g$.
- Verification by chain rule: $\partial f/\partial x=2g'$, $\partial f/\partial y=-3g'$; substitute to get $6g'-6g'=0$.

**Converse (by linear change of variables).** Set $x=Au+Bv$, $y=Cu+Dv$ and choose $A,C$ so that $\partial h/\partial u=0$ where $h(u,v)=f(x,y)$. Then $h(u,v)=g(v)$, and with suitable $B,D$ one obtains $v=bx-ay$.

**Theorem 9.1.** Let $a,b$ be constants (not both zero). The general solution of
$$a\frac{\partial f}{\partial x}+b\frac{\partial f}{\partial y}=0\tag{9.10}$$
is
$$f(x,y)=g(bx-ay),\tag{9.9}$$
where $g$ is any differentiable function on $\mathbb{R}^1$.
