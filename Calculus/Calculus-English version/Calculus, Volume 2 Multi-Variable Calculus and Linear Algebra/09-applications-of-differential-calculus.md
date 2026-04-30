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


### 9.10 Second-Order Taylor Formula for Scalar Fields

For a differentiable scalar field $f$ with a stationary point at $a$, write $x=a+y$. The first-order Taylor formula is
$$
f(a+y)-f(a)=\nabla f(a)\cdot y+\|y\|\,E(a,y),\quad E(a,y)\to\mathbf{0}\text{ as }y\to\mathbf{0}.
$$
At a stationary point $\nabla f(a)=\mathbf{0}$, so $f(a+y)-f(a)=\|y\|\,E(a,y)$.

To determine the sign of $f(a+y)-f(a)$ we need the quadratic form given by continuous second-order partials.

**Hessian matrix.**
$$
H(x)=\bigl[D_{ij}f(x)\bigr]_{i,j=1}^{n},
\qquad
\sum_{i=1}^{n}\sum_{j=1}^{n}D_{ij}f(a)y_iy_j = yH(a)y^{t}.
$$
When the partials are continuous, $D_{ij}f=D_{ji}f$ and $H(a)$ is symmetric.

**Theorem 9.4 (Second-order Taylor formula).** Let $f$ have continuous second-order partials $D_{ij}f$ in an $n$-ball $B(a)$. Then for all $y$ with $a+y\in B(a)$,
$$
f(a+y)-f(a)=\nabla f(a)\cdot y+\frac{1}{2!}\,yH(a+cy)y^{t},\qquad 0<c<1.\tag{9.34}
$$
Equivalently,
$$
f(a+y)-f(a)=\nabla f(a)\cdot y+\frac{1}{2!}\,yH(a)y^{t}+\|y\|^{2}E_{2}(a,y),\tag{9.35}
$$
where $E_{2}(a,y)\to 0$ as $y\to\mathbf{0}$.

**Proof sketch.** Define $g(u)=f(a+uy)$ for $u\in[-1,1]$. Apply the 1D second-order Taylor formula to $g$ on $[0,1]$:
$$
g(1)-g(0)=g'(0)+\tfrac{1}{2}g''(c),\quad 0<c<1.
$$
By the chain rule, $g'(u)=\nabla f(a+uy)\cdot y$ and $g''(u)=yH(a+uy)y^{t}$. Hence $g''(c)=yH(a+cy)y^{t}$, giving (9.34). For (9.35), define $E_2$ via
$$
\|y\|^{2}E_{2}(a,y)=\tfrac{1}{2}y\bigl[H(a+cy)-H(a)\bigr]y^{t}\quad(y\neq\mathbf{0}),
$$
and $E_{2}(a,\mathbf{0})=0$. Continuity of $D_{ij}f$ at $a$ implies $E_{2}(a,y)\to0$.


### 9.11 The Nature of a Stationary Point Determined by the Eigenvalues of the Hessian Matrix

At a stationary point $\nabla f(a)=\mathbf{0}$, so (9.35) becomes
$$
f(a+y)-f(a)=\frac{1}{2}\,yH(a)y^{t}+\|y\|^{2}E_{2}(a,y).
$$
Since $\|y\|^{2}E_{2}(a,y)=o(\|y\|^{2})$, the sign of $f(a+y)-f(a)$ for small $y$ is the same as that of the quadratic form $yH(a)y^{t}$.

**Theorem 9.5 (Sign of a quadratic form).** Let $A=[a_{ij}]$ be an $n\times n$ real symmetric matrix and let
$$
Q(y)=yAy^{t}=\sum_{i=1}^{n}\sum_{j=1}^{n}a_{ij}y_iy_j.
$$
Then:
- (a) $Q(y)>0$ for all $y\neq\mathbf{0}$ $\iff$ all eigenvalues of $A$ are positive (**positive definite**).
- (b) $Q(y)<0$ for all $y\neq\mathbf{0}$ $\iff$ all eigenvalues of $A$ are negative (**negative definite**).

*Proof sketch.* By Theorem 5.11 there is an orthogonal matrix $C$ diagonalizing $A$:
$$
Q(y)=yAy^{t}=\sum_{i=1}^{n}\lambda_i x_i^{2},\tag{9.38}
$$
where $x=yC$ and $\lambda_1,\dots,\lambda_n$ are the (real) eigenvalues of $A$. If all $\lambda_i>0$ then $Q(y)>0$ for all $y\neq\mathbf{0}$. Conversely, choosing $y$ so that $x=yC=e_k$ gives $Q(y)=\lambda_k$, hence each $\lambda_k>0$. Part (b) is analogous.

**Theorem 9.6 (Classification of stationary points).** Let $f$ have continuous second-order partials in an $n$-ball $B(a)$ and let $H(a)$ be the Hessian at a stationary point $a$. Then:
- (a) All eigenvalues of $H(a)$ positive $\implies$ $f$ has a **relative minimum** at $a$.
- (b) All eigenvalues of $H(a)$ negative $\implies$ $f$ has a **relative maximum** at $a$.
- (c) $H(a)$ has both positive and negative eigenvalues $\implies$ $f$ has a **saddle point** at $a$.

*Proof sketch.* Write $Q(y)=yH(a)y^{t}$. From (9.35),
$$
f(a+y)-f(a)=\tfrac{1}{2}Q(y)+\|y\|^{2}E_{2}(a,y).\tag{9.39}
$$
For (a), let $h>0$ be the smallest eigenvalue. Then $Q(y)>\frac{1}{2}h\|y\|^{2}$. Choose $r$ so that $|E_{2}(a,y)|<\frac{1}{4}h$ for $0<\|y\|<r$; then $f(a+y)-f(a)>0$. For (b) apply (a) to $-f$. For (c), if $\lambda_1>0$ and $\lambda_2<0$, the quadratic form takes both signs in every neighborhood of $\mathbf{0}$, so $f(a+y)-f(a)$ does too, giving a saddle point.

*Note:* If all eigenvalues of $H(a)$ are zero, Theorem 9.6 gives no information; higher-order derivatives would be needed.


### 9.12 Second-Derivative Test for Extrema of Functions of Two Variables

For $n=2$ the classification can be determined from $D_{1,1}f(a)$ and $\det H(a)$.

**Theorem 9.7.** Let $a$ be a stationary point of $f(x_1,x_2)$ with continuous second-order partials in a 2-ball $B(a)$. Set
$$
A=D_{1,1}f(a),\quad B=D_{1,2}f(a),\quad C=D_{2,2}f(a),\quad
\Delta=\det H(a)=\det\begin{bmatrix}A&B\\B&C\end{bmatrix}=AC-B^{2}.
$$
Then:
- (a) $\Delta<0$ $\implies$ **saddle point** at $a$.
- (b) $\Delta>0$ and $A>0$ $\implies$ **relative minimum** at $a$.
- (c) $\Delta>0$ and $A<0$ $\implies$ **relative maximum** at $a$.
- (d) $\Delta=0$ $\implies$ test is **inconclusive**.

*Proof sketch.* The characteristic equation is $\lambda^{2}-(A+C)\lambda+\Delta=0$, so
$$
\lambda_1+\lambda_2=A+C,\qquad \lambda_1\lambda_2=\Delta.
$$
If $\Delta<0$, the eigenvalues have opposite signs $\to$ saddle point. If $\Delta>0$, they have the same sign; since $AC>B^{2}\ge0$, $A$ and $C$ share the same sign, which must be the sign of both eigenvalues. For (d), see Examples 4 and 5 of Section 9.9 (both have $\Delta=0$ at the origin, but one is a saddle point and the other a relative minimum).

*Alternative approach:* Even when Theorem 9.7 applies, rewriting the function as a sum of squares may be simpler. Example: $f(x,y)=e^{1/g(x,y)}$ with $g(x,y)=x^{2}+2+\cos^{2}y-2\cos y$ can be rewritten as $g(x,y)=1+x^{2}+(1-\cos y)^{2}$, showing relative maxima at $(0,2n\pi)$ for any integer $n$.


### 9.14 Extrema with Constraints: Lagrange's Multipliers

**Problem.** Determine extreme values of a scalar field $f(\mathbf{x})$ when $\mathbf{x}$ is restricted to a subset of the domain of $f$.

- **Example 1.** Minimize distance to the origin on a surface $S$: $f(x,y,z)=(x^{2}+y^{2}+z^{2})^{1/2}$, constraint $S$.
- **Example 2.** Find max/min temperature on a curve $C$ in 3-space.

**The method of Lagrange's multipliers.** If $f(x_1,\dots,x_n)$ has a relative extremum subject to $m$ constraints
$$
g_1(x_1,\dots,x_n)=0,\quad\dots,\quad g_m(x_1,\dots,x_n)=0,\tag{9.40}
$$
with $m<n$, then there exist scalars $\lambda_1,\dots,\lambda_m$ such that
$$
\nabla f=\lambda_1\nabla g_1+\cdots+\lambda_m\nabla g_m\tag{9.41}
$$
at each extremum point. The scalars $\lambda_i$ are **Lagrange's multipliers**.

*Practical use:* Solve the system of $n+m$ equations consisting of the $m$ constraints (9.40) and the $n$ scalar equations from (9.41) for the $n+m$ unknowns $x_1,\dots,x_n,\lambda_1,\dots,\lambda_m$.

The method is valid when:
- $f$ and $g_1,\dots,g_m$ are differentiable.
- The number of constraints $m$ is less than the number of variables $n$.
- Not all Jacobian determinants of the constraint functions with respect to $m$ of the variables are zero at the extremum.

**Geometric argument for Example 1.** As $r$ increases, the level surface $f=r$ first touches $S$ at the nearest point(s). At a contact point the tangent planes coincide, so $\nabla f$ and $\nabla g$ are parallel: $\nabla f=\lambda\nabla g$.

**Geometric argument for Example 2.** Let $C$ be the intersection of $g_1=0$ and $g_2=0$. Parameterize $C$ by $\alpha(t)$ and set $\varphi(t)=f[\alpha(t)]$. At an interior extremum $t_1$, $\varphi'(t_1)=\nabla f[\alpha(t_1)]\cdot\alpha'(t_1)=0$, so $\nabla f$ is normal to $C$. Since $\nabla g_1$ and $\nabla g_2$ are also normal to $C$, if they are independent then $\nabla f$ lies in their span:
$$
\nabla f=\lambda_1\nabla g_1+\lambda_2\nabla g_2.
$$
Independence of $\nabla g_1,\nabla g_2$ $\iff$ their cross product is nonzero, i.e. not all Jacobian determinants
$$
\frac{\partial(g_1,g_2)}{\partial(y,z)},\quad \frac{\partial(g_1,g_2)}{\partial(z,x)},\quad \frac{\partial(g_1,g_2)}{\partial(x,y)}
$$
are zero. If $\nabla g_1$ and $\nabla g_2$ are dependent, the method may fail (e.g. $g_1=z$, $g_2=z^{2}-(y-1)^{3}$ at $(0,1,0)$ where $\nabla g_2=\mathbf{0}$).

