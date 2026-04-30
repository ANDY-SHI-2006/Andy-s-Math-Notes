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


### 9.4 The One-Dimensional Wave Equation

The displacement $y=f(x,t)$ of a vibrating string satisfies
$$\frac{\partial^2f}{\partial t^2}=c^2\frac{\partial^2f}{\partial x^2},\tag{9.12}$$
with initial conditions
$$f(x,0)=F(x),\qquad D_2f(x,0)=G(x).\tag{9.13}$$

**Theorem 9.2 (d'Alembert's solution).** If $G$ is differentiable and $F$ is twice differentiable on $\mathbb{R}^1$, then
$$f(x,t)=\frac{F(x+ct)+F(x-ct)}{2}+\frac{1}{2c}\int_{x-ct}^{x+ct}G(s)\,ds.\tag{9.11}$$

- *Derivation sketch:* Factor the wave operator:
  $$L_1L_2f=0,\qquad L_1=\frac{\partial}{\partial t}-c\frac{\partial}{\partial x},\quad L_2=\frac{\partial}{\partial t}+c\frac{\partial}{\partial x}.$$
- Set $u=L_2f$; then $L_1u=0$, so $u(x,t)=\varphi(x+ct)$ by Theorem 9.1.
- Find $v$ with $L_2v=u$; then $L_2(f-v)=0$, so $f-v=\psi(x-ct)$.
- Hence $f(x,t)=\varphi_1(x+ct)+\varphi_2(x-ct)$.
- Use (9.13) to determine $\varphi_1,\varphi_2$; integrating yields (9.11).

**Interpretation.** The solution is a superposition of two waves traveling with speed $c$, one to the right ($F(x-ct)$) and one to the left ($F(x+ct)$).


### 9.6 Derivatives of Functions Defined Implicitly

A surface $F(x,y,z)=0$ may define $z$ implicitly as $z=f(x,y)$.

**Implicit differentiation.** Set $g(x,y)=F[x,y,f(x,y)]=0$. By the chain rule:
$$\frac{\partial g}{\partial x}=D_1F+D_3F\frac{\partial f}{\partial x}=0,\qquad \frac{\partial g}{\partial y}=D_2F+D_3F\frac{\partial f}{\partial y}=0.$$
Hence, where $D_3F\neq0$:
$$\frac{\partial f}{\partial x}=-\frac{D_1F}{D_3F},\qquad \frac{\partial f}{\partial y}=-\frac{D_2F}{D_3F}.\tag{9.20–9.21}$$
Or more compactly:
$$\frac{\partial f}{\partial x}=-\frac{\partial F/\partial x}{\partial F/\partial z},\qquad \frac{\partial f}{\partial y}=-\frac{\partial F/\partial y}{\partial F/\partial z}.$$

**Theorem 9.3.** If $F(x_1,\dots,x_n)=0$ defines $x_n=f(x_1,\dots,x_{n-1})$ and $D_nF\neq0$, then
$$D_kf=-\frac{D_kF}{D_nF}.\tag{9.22}$$

**Two constraints, one parameter.** If $F(x,y,z)=0$ and $G(x,y,z)=0$ define a curve $x=X(z)$, $y=Y(z)$, differentiate both with respect to $z$ and solve the linear system for $X'(z),Y'(z)$. By Cramer's rule (using **Jacobian determinants**):
$$X'(z)=\frac{\partial(F,G)/\partial(y,z)}{\partial(F,G)/\partial(x,y)},\qquad Y'(z)=\frac{\partial(F,G)/\partial(z,x)}{\partial(F,G)/\partial(x,y)}.\tag{9.25}$$

- **Jacobian notation:**
  $$\frac{\partial(f_1,\dots,f_n)}{\partial(x_1,\dots,x_n)}=\det\bigl[D_jf_i\bigr].$$


### 9.7 Worked Examples

**Example 1.** $g(x,y)=0$ defines $y=Y(x)$. Then
$$Y'(x)=-\frac{\partial g/\partial x}{\partial g/\partial y}.\tag{9.26}$$

**Example 2.** Eliminate $y$ from $z=f(x,y)$ and $g(x,y)=0$ to get $z=h(x)$. Then
$$h'(x)=\frac{\partial(f,g)/\partial(x,y)}{\partial g/\partial y}=\frac{g_yf_x-f_yg_x}{g_y}.$$

**Example 3.** $2x=v^2-u^2$, $y=uv$ define $u,v$ as functions of $x,y$.
$$\frac{\partial u}{\partial x}=-\frac{u}{u^2+v^2},\quad \frac{\partial v}{\partial x}=\frac{v}{u^2+v^2},\quad
\frac{\partial u}{\partial y}=\frac{v}{u^2+v^2},\quad \frac{\partial v}{\partial y}=\frac{u}{u^2+v^2}.$$

**Example 4.** $u=F(x+u,yu)$. With $u=g(x,y)$:
$$\frac{\partial u}{\partial x}=\frac{-D_1F}{D_1F+yD_2F-1},\qquad
\frac{\partial u}{\partial y}=\frac{-g(x,y)D_2F}{D_1F+yD_2F-1}.$$

**Example 5.** Eliminate $u$ from $x=u+v$, $y=uv^2$ to get $F(x,y,v)=xv^2-v^3-y=0$, defining $v=h(x,y)$.
$$\frac{\partial h}{\partial x}=\frac{h}{3h-2x},\qquad \frac{\partial h}{\partial y}=\frac{1}{2xh-3h^2}.$$

**Example 6.** $F(x,y,z)=0$ defines $z=f(x,y)$. The second derivative:
$$\frac{\partial^2f}{\partial x^2}=-\frac{F_{zz}(F_x)^2-2F_{xz}F_zF_x+(F_z)^2F_{xx}}{(F_z)^3}.\tag{9.30}$$
- Derived by differentiating $\partial f/\partial x=-F_x/F_z$ via the quotient rule and chain rule.


### 9.9 Maxima, Minima, and Saddle Points

A surface $z=f(x,y)$ is a level surface of $F(x,y,z)=f(x,y)-z$. If $f$ is differentiable,
$$
\nabla F = \frac{\partial f}{\partial x}\mathbf{i}+\frac{\partial f}{\partial y}\mathbf{j}-\mathbf{k}.
$$
The tangent plane at $P_1=(x_1,y_1,z_1)$ is $z-z_1=A(x-x_1)+B(y-y_1)$, where $A=D_1f(x_1,y_1)$ and $B=D_2f(x_1,y_1)$.

When $A=B=0$, $P_1$ is a **stationary point** of the surface and $(x_1,y_1)$ is a **stationary (critical) point** of $f$; the tangent plane is horizontal. Stationary points fall into three categories: **maxima, minima, and saddle points**.

**Definitions.**

- **Absolute maximum** at $a$ in $S$: $f(x)\le f(a)$ for all $x\in S$.
- **Relative (local) maximum** at $a$: the inequality holds on some $n$-ball $B(a)\subseteq S$.
- **Absolute/relative minimum** defined with the opposite inequality.
- **Extremum**: a number that is either a relative maximum or a relative minimum.

**First-order necessary condition.** If $f$ has an extremum at an interior point $a$ and is differentiable there, then $\nabla f(a)=\mathbf{0}$. (Proof sketch: hold each component fixed and reduce to the 1D case.)

- For $n=2$: $\partial f/\partial x=\partial f/\partial y=0$ gives a horizontal tangent plane at $(a,f(a))$.
- However, $\nabla f(a)=\mathbf{0}$ does **not** guarantee an extremum — this occurs at **saddle points**.

**Definition (Saddle point).** Let $f$ be differentiable at $a$. If $\nabla f(a)=\mathbf{0}$ then $a$ is a stationary point. It is a **saddle point** if every $n$-ball $B(a)$ contains points $x$ with $f(x)<f(a)$ and other points with $f(x)>f(a)$.

| Example | $f(x,y)$ | Type at origin | Notes |
|---------|----------|----------------|-------|
| 1 | $2-x^2-y^2$ | Relative (and absolute) maximum | Paraboloid of revolution |
| 2 | $x^2+y^2$ | Relative (and absolute) minimum | Paraboloid of revolution |
| 3 | $xy$ | Saddle point | Hyperbolic paraboloid; $\partial f/\partial x=\partial f/\partial y=0$ at origin, but $f>0$ in quadrants I, III and $f<0$ in II, IV |
| 4 | $x^3-3xy^2$ | Saddle point ("monkey saddle") | Three peaks near origin |
| 5 | $x^2y^2$ | Relative (and absolute) minimum | Valley surrounded by four mountains; $f\ge 0$ everywhere |
| 6 | $1-x^2$ | Relative (and absolute) maximum | Cylinder with generators parallel to $y$-axis |

