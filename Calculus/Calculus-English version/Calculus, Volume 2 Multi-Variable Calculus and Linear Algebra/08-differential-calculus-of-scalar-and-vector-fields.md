# Chapter 8 — Differential Calculus of Scalar and Vector Fields

### 8.1 Functions from $\mathbb{R}^n$ to $\mathbb{R}^m$. Scalar and Vector Fields

- **Scalar field:** $f:\mathbb{R}^n\to\mathbb{R}$ ($m=1$). Also written $f(x)$ or $f(x_1,\dots,x_n)$.
- **Vector field:** $f:\mathbb{R}^n\to\mathbb{R}^m$ ($m>1$).
- **Inner product and norm:** $x\cdot y=\sum_{k=1}^n x_ky_k$, $\|x\|=(x\cdot x)^{1/2}$.
- Points in $\mathbb{R}^2$ denoted $(x,y)$; in $\mathbb{R}^3$ denoted $(x,y,z)$.
- Examples: temperature $f(x)$ (scalar field); wind velocity (vector field).
- This chapter extends limit, continuity, and derivative to scalar and vector fields.


### 8.2 Open Balls and Open Sets

- **Open $n$-ball:** $B(a;r)=\{x\in\mathbb{R}^n:\|x-a\|<r\}$.
  - In $\mathbb{R}^1$: open interval; in $\mathbb{R}^2$: circular disk; in $\mathbb{R}^3$: solid sphere.

**Definitions.**
- $a\in S$ is an **interior point** of $S$ if some ball $B(a)\subseteq S$.
- The set of all interior points is the **interior** $\operatorname{int}S$.
- $S$ is **open** iff $S=\operatorname{int}S$.
- An open set containing $a$ is a **neighborhood** of $a$.

**Examples.**
- Open intervals in $\mathbb{R}^1$; unions of open intervals are open.
- $[a,b]$ is **not** open.
- Cartesian product of open sets in $\mathbb{R}^1$ is open in $\mathbb{R}^2$ (e.g. open rectangle).

**Exterior and boundary.**
- $x$ is **exterior** to $S$ if some $B(x)$ contains no points of $S$; the set of such points is $\operatorname{ext}S$.
- A **boundary point** is neither interior nor exterior; the set of all boundary points is $\partial S$.
- Example: for $B(O;1)$, the exterior is $\|x\|>1$ and the boundary is $\|x\|=1$.


### 8.4 Limits and Continuity

For $f:S\to\mathbb{R}^m$ with $S\subseteq\mathbb{R}^n$:
$$\lim_{x\to a}f(x)=b\quad\Longleftrightarrow\quad\lim_{\|x-a\|\to0}\|f(x)-b\|=0.\tag{8.1–8.2}$$

- **Continuity at $a$:** $f$ is defined at $a$ and $\displaystyle\lim_{x\to a}f(x)=f(a)$.
- **Continuity on $S$:** continuous at each point of $S$.

**Theorem 8.1 (Limit laws).** If $\lim_{x\to a}f(x)=b$ and $\lim_{x\to a}g(x)=c$, then:
- (a) $\lim\,[f+g]=b+c$.
- (b) $\lim\,\lambda f=\lambda b$.
- (c) $\lim\,f\cdot g=b\cdot c$.
- (d) $\lim\,\|f\|=\|b\|$.

**Component-wise continuity.** $f=(f_1,\dots,f_m)$ is continuous at $a$ **iff** each component $f_k$ is continuous at $a$ (since $f_k(x)=f(x)\cdot e_k$ and $f(x)=\sum f_k(x)e_k$).

**Examples of continuous fields.**
- Identity function $f(x)=x$; its components $f_k(x)=x_k$.
- Every linear transformation $f:\mathbb{R}^n\to\mathbb{R}^m$.
- Polynomials in $n$ variables (finite sums/products of continuous scalar fields).
- Rational functions $P/Q$ (where defined, i.e. $Q(x)\neq0$).

**Theorem 8.2 (Composition).** If $g$ is continuous at $a$ and $f$ is continuous at $g(a)$, then $f\circ g$ is continuous at $a$.

**Example of discontinuity.** $f(x,y)=\dfrac{xy}{x^2+y^2}$ ($f(0,0)=0$) is continuous in each variable separately at $(0,0)$, but **not** continuous there as a function of two variables (along $y=x$, $f=\frac12\neq0$).


### 8.6 The Derivative of a Scalar Field with Respect to a Vector

Let $f$ be a scalar field on $S\subseteq\mathbb{R}^n$ and let $a$ be an interior point of $S$. The **derivative of $f$ at $a$ with respect to $y$** is
$$f'(a;y)=\lim_{h\to0}\frac{f(a+hy)-f(a)}{h},\tag{8.4}$$
when the limit exists.

- $f'(a;O)=0$ always.
- If $f$ is **linear**, $f'(a;y)=f(y)$ for all $a,y$.

**Theorem 8.3.** Let $g(t)=f(a+ty)$. If either $g'(t)$ or $f'(a+ty;y)$ exists, so does the other, and
$$g'(t)=f'(a+ty;y).\tag{8.5}$$
In particular, $g'(0)=f'(a;y)$.

**Example.** $f(x)=\|x\|^2$. Then $g(t)=(a+ty)\cdot(a+ty)$, so $g'(t)=2a\cdot y+2ty\cdot y$ and $f'(a;y)=2a\cdot y$.

**Theorem 8.4 (Mean-value theorem for scalar fields).** If $f'(a+ty;y)$ exists for all $t\in[0,1]$, then for some $\theta\in(0,1)$,
$$f(a+y)-f(a)=f'(z;y),\qquad z=a+\theta y.$$
- *Proof:* Apply the 1-D MVT to $g(t)=f(a+ty)$ on $[0,1]$.


### 8.7 Directional Derivatives and Partial Derivatives

When $y$ is a **unit vector** ($\|y\|=1$), $f'(a;y)$ is called the **directional derivative** of $f$ at $a$ in the direction of $y$.

- **Partial derivative** with respect to $e_k$ (the $k$th unit coordinate vector):
  $$D_kf(a)=f'(a;e_k).$$
- Alternative notations:
  $$D_kf(a_1,\dots,a_n),\quad \frac{\partial f}{\partial x_k}(a_1,\dots,a_n),\quad f_{x_k}(a_1,\dots,a_n),\quad f_k.$$
- In $\mathbb{R}^2$: $\dfrac{\partial f}{\partial x}$, $\dfrac{\partial f}{\partial y}$.
- In $\mathbb{R}^3$: $\dfrac{\partial f}{\partial x}$, $\dfrac{\partial f}{\partial y}$, $\dfrac{\partial f}{\partial z}$.

### 8.8 Partial Derivatives of Higher Order

The partial derivatives of $D_1f,\dots,D_nf$ are **second-order partial derivatives**:
$$D_i(D_jf)=\frac{\partial^2f}{\partial x_i\,\partial x_j}=D_{i,j}f.$$

For $n=2$:
$$\frac{\partial^2f}{\partial x^2},\quad \frac{\partial^2f}{\partial x\,\partial y},\quad \frac{\partial^2f}{\partial y\,\partial x},\quad \frac{\partial^2f}{\partial y^2}.$$

- The two **mixed partials** $\dfrac{\partial^2f}{\partial x\,\partial y}$ and $\dfrac{\partial^2f}{\partial y\,\partial x}$ may or may not be equal.
- **Equality of mixed partials** (§8.23): $D_{1,2}f=D_{2,1}f$ at a point if one of them is continuous in a neighborhood of that point.


### 8.10 Directional Derivatives and Continuity

In one dimension, existence of $f'(a)$ implies continuity at $a$. For scalar fields, existence of $f'(a;y)$ for a given $y$ implies
$$\lim_{h\to0}f(a+hy)=f(a),$$
i.e. $f(x)\to f(a)$ along the line through $a$ in direction $y$.

- If $f'(a;y)$ exists for **every** direction $y$, then $f(x)\to f(a)$ along **every** line through $a$. One might expect $f$ to be continuous at $a$ — but this is **false**.

**Counter-example.** $f(x,y)=\dfrac{xy^2}{x^2+y^4}$ ($x\neq0$), $f(0,y)=0$.
- At $(0,0)$: $f'(O;y)$ exists for **all** directions $y$.
- Along every straight line through the origin, $f(x)\to0$.
- Yet on the parabola $x=y^2$, $f=\frac12$; since such points are arbitrarily close to $O$ and $f(O)=0$, $f$ is **not continuous** at $O$.

- Conclusion: existence of all directional derivatives is **not sufficient** for continuity. A better generalization is the **total derivative** (§8.11+).


### 8.11 The Total Derivative

Recall the 1-D first-order Taylor formula:
$$f(a+h)=f(a)+f'(a)h+hE(a,h),\qquad E(a,h)\to0\text{ as }h\to0.$$

**Definition.** A scalar field $f:S\to\mathbb{R}$ is **differentiable at $a$** if there exists a linear transformation $T_a:\mathbb{R}^n\to\mathbb{R}$ and a scalar function $E(a,v)$ such that
$$f(a+v)=f(a)+T_a(v)+\|v\|E(a,v)\tag{8.7}$$
for $\|v\|<r$, with $E(a,v)\to0$ as $\|v\|\to0$.

- $T_a$ is called the **total derivative** of $f$ at $a$ (introduced by W. H. Young, 1908; M. Fréchet, 1911).
- The error $\|v\|E(a,v)$ is $o(\|v\|)$.

**Theorem 8.5.** If $f$ is differentiable at $a$ with total derivative $T_a$, then:
- (i) $f'(a;y)$ exists for every $y\in\mathbb{R}^n$ and $T_a(y)=f'(a;y)$.
- (ii) $f'(a;y)$ is linear in $y$:
  $$f'(a;y)=\sum_{k=1}^n D_kf(a)\,y_k.\tag{8.9}$$
- *Proof sketch:* Set $v=hy$ in (8.7); divide by $h$ and let $h\to0$ to get $T_a(y)=f'(a;y)$. Then use linearity: $T_a(y)=\sum y_kT_a(e_k)=\sum y_kD_kf(a)$.


### 8.12 The Gradient of a Scalar Field

From (8.9), the total derivative can be written as a dot product:
$$f'(a;y)=\sum_{k=1}^n D_kf(a)\,y_k=\nabla f(a)\cdot y,$$
where the **gradient** of $f$ at $a$ is the vector of partial derivatives:
$$\nabla f(a)=\bigl(D_1f(a),\dots,D_nf(a)\bigr)=\operatorname{grad}f(a).$$

- First-order Taylor formula in gradient form:
  $$f(a+v)=f(a)+\nabla f(a)\cdot v+\|v\|E(a,v).\tag{8.12}$$

**Theorem 8.6.** If $f$ is differentiable at $a$, then $f$ is continuous at $a$.
- *Proof:* $|f(a+v)-f(a)|\le\|\nabla f(a)\|\|v\|+\|v\||E(a,v)|\to0$.

**Geometric interpretation.** For a unit vector $y$, let $\theta$ be the angle between $y$ and $\nabla f(a)$. Then
$$f'(a;y)=\nabla f(a)\cdot y=\|\nabla f(a)\|\cos\theta.$$
- Maximum rate of change: $\|\nabla f(a)\|$, achieved when $y$ points in the direction of $\nabla f(a)$.
- Directional derivative is $0$ when $y$ is orthogonal to $\nabla f(a)$.

**Coordinate forms.**
- In $\mathbb{R}^2$: $\nabla f=\dfrac{\partial f}{\partial x}i+\dfrac{\partial f}{\partial y}j$.
- In $\mathbb{R}^3$: $\nabla f=\dfrac{\partial f}{\partial x}i+\dfrac{\partial f}{\partial y}j+\dfrac{\partial f}{\partial z}k$.


### 8.13 A Sufficient Condition for Differentiability

Existence of all partials does **not** imply differentiability (e.g. $f(x,y)=\dfrac{xy^2}{x^2+y^4}$ from §8.10 has $D_1f(O)$ and $D_2f(O)$ but is not differentiable at $O$).

**Theorem 8.7.** If $D_1f,\dots,D_nf$ exist in some ball $B(a)$ and are **continuous** at $a$, then $f$ is differentiable at $a$.
- A field satisfying this is called **continuously differentiable** at $a$.

- *Proof sketch:* Write $v=\lambda u$ with $\|u\|=1$ and telescope:
  $$f(a+v)-f(a)=\sum_{k=1}^n\bigl[f(b_k+\lambda u_ke_k)-f(b_k)\bigr],\quad b_k=a+\lambda v_{k-1}.$$
  Apply the 1-D MVT to each term:
  $$f(b_k+\lambda u_ke_k)-f(b_k)=\lambda u_kD_kf(c_k).$$
  Hence
  $$f(a+v)-f(a)-\nabla f(a)\cdot v=\lambda\sum_{k=1}^n\bigl[D_kf(c_k)-D_kf(a)\bigr]u_k=\|v\|E(a,v).$$
  As $\|v\|\to0$, $c_k\to a$; continuity of $D_kf$ gives $E(a,v)\to0$.


### 8.15 A Chain Rule for Derivatives of Scalar Fields

**Theorem 8.8 (Chain rule).** Let $f$ be a scalar field on an open set $S\subseteq\mathbb{R}^n$ and let $r:J\to S$ be a vector-valued function ($J\subseteq\mathbb{R}$). Define $g=f\circ r$ by $g(t)=f[r(t)]$. If $r'(t)$ exists and $f$ is differentiable at $a=r(t)$, then
$$g'(t)=\nabla f(a)\cdot r'(t).\tag{8.15}$$
- *Proof sketch:* Set $y=r(t+h)-r(t)$. By Taylor's formula,
  $$\frac{g(t+h)-g(t)}{h}=\nabla f(a)\cdot\frac{r(t+h)-r(t)}{h}+\frac{\|y\|}{h}E(a,y)\to\nabla f(a)\cdot r'(t).$$

**Directional derivative along a curve.** If $r$ describes a curve $C$ and $T(t)=r'(t)/\|r'(t)\|$ is the unit tangent, then $\nabla f[r(t)]\cdot T(t)$ is the directional derivative of $f$ along $C$. For a plane curve with $T=\cos\alpha\,i+\cos\beta\,j$:
$$\nabla f\cdot T=\frac{\partial f}{\partial x}\cos\alpha+\frac{\partial f}{\partial y}\cos\beta.$$

**Level curves.** If $f(x,y)=c$ describes a curve $C$ and $g(t)=f[r(t)]=c$, then $g'(t)=\nabla f\cdot r'=0$, so:
- $\nabla f$ is **normal** to $C$.
- Directional derivative of $f$ along $C$ is $0$.
- Maximum directional derivative occurs in the direction **normal** to $C$.


### 8.16 Applications to Geometry: Level Sets and Tangent Planes

- **Level set:** $L(c)=\{x\in S:f(x)=c\}$.
  - In $\mathbb{R}^2$: **level curve**; in $\mathbb{R}^3$: **level surface**.
  - Example: isothermals ($f(x,y)=$ temperature) and lines of flow (orthogonal trajectories).

**Gradient is normal to level sets.**
- Let $\Gamma$ be any curve on $L(c)$ through $a$, parametrized by $r(t)$. Since $f[r(t)]=c$ is constant,
  $$g'(t)=\nabla f[r(t)]\cdot r'(t)=0.$$
- Hence $\nabla f(a)$ is perpendicular to every tangent vector of $L(c)$ at $a$.

**Tangent plane to a level surface** ($\mathbb{R}^3$).
- If $\nabla f(a)\neq O$, the tangent vectors span a plane with normal $\nabla f(a)$.
- Point-normal form:
  $$\nabla f(a)\cdot(x-a)=0.$$
- Cartesian form (with $a=(x_1,y_1,z_1)$):
  $$D_1f(a)(x-x_1)+D_2f(a)(y-y_1)+D_3f(a)(z-z_1)=0.$$

**Tangent line to a level curve** ($\mathbb{R}^2$).
- At $a=(x_1,y_1)$:
  $$D_1f(a)(x-x_1)+D_2f(a)(y-y_1)=0.$$


### 8.18 Derivatives of Vector Fields

For $f:S\to\mathbb{R}^m$ and $a$ an interior point of $S\subseteq\mathbb{R}^n$:
$$f'(a;y)=\lim_{h\to0}\frac{f(a+hy)-f(a)}{h}\quad\text{(a vector in }\mathbb{R}^m\text{)}.$$

- $f'(a;y)$ exists iff each component derivative $f_k'(a;y)$ exists, and
  $$f'(a;y)=\sum_{k=1}^m f_k'(a;y)e_k.$$

**Differentiability.** $f$ is differentiable at $a$ if there exists a linear transformation $T_a:\mathbb{R}^n\to\mathbb{R}^m$ such that
$$f(a+v)=f(a)+T_a(v)+\|v\|E(a,v),\tag{8.16}$$
with $E(a,v)\to O$ as $v\to O$.

**Theorem 8.9.** If $f$ is differentiable at $a$, then $f'(a;y)$ exists for every $y$ and
$$T_a(y)=f'(a;y)=\sum_{k=1}^m\bigl(\nabla f_k(a)\cdot y\bigr)e_k.\tag{8.17–8.18}$$

**Jacobian matrix.** Writing $T_a(y)=Df(a)\,y$ as a matrix product, $Df(a)$ is the $m\times n$ **Jacobian matrix** whose $kj$-entry is $D_jf_k(a)$:
$$Df(a)=\begin{bmatrix}
D_1f_1(a)&\cdots&D_nf_1(a)\\
\vdots&&\vdots\\
D_1f_m(a)&\cdots&D_nf_m(a)
\end{bmatrix}.$$

- First-order Taylor formula: $f(a+v)=f(a)+f'(a)(v)+\|v\|E(a,v)$.
