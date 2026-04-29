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
