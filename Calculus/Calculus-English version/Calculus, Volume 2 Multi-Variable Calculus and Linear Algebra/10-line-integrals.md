# Chapter 10 — Line Integrals

### 10.1 Introduction

This chapter extends the notion of integral from intervals to curves. The interval $[a,b]$ is replaced by a curve in $n$-space described by a vector-valued function $\alpha$, and the integrand is a vector field $f$ defined on this curve. The resulting integral is called a **line integral** (or **curvilinear integral** / **contour integral**), denoted $\int f\cdot d\alpha$. The dot is used purposely to suggest an inner product of two vectors. The curve is called a **path of integration**.

Line integrals are fundamental in pure and applied mathematics, occurring in connection with work, potential energy, heat flow, change in entropy, circulation of a fluid, and other physical situations.

### 10.2 Paths and Line Integrals

**Curve vs. path.** In Volume I, a curve was the graph of a continuous vector-valued function $\alpha:J\to\mathbb{R}^{n}$ on $J=[a,b]$. For line integrals we care not only about the set of points but also the **manner** in which the curve is traced out — the function $\alpha$ itself.

**Definitions.**
- A **continuous path** in $n$-space is a continuous function $\alpha:J\to\mathbb{R}^{n}$ on a finite closed interval $J=[a,b]$.
- The path is **smooth** if $\alpha'$ exists and is continuous on $(a,b)$.
- The path is **piecewise smooth** if $[a,b]$ can be partitioned into finitely many subintervals on each of which the path is smooth.

**Definition of line integral.** Let $\alpha$ be a piecewise smooth path in $n$-space on $[a,b]$, and let $f$ be a vector field defined and bounded on the graph of $\alpha$. The **line integral of $f$ along $\alpha$** is
$$
\int f\cdot d\alpha = \int_a^{b} f[\alpha(t)]\cdot\alpha'(t)\,dt,\tag{10.1}
$$
whenever the integral on the right exists (proper or improper).

*Note:* In most practical examples $f[\alpha(t)]\cdot\alpha'(t)$ is bounded on $[a,b]$ and continuous except possibly at finitely many points, so the integral exists as a proper integral.


### 10.3 Other Notations for Line Integrals

If $C$ denotes the graph of $\alpha$, the line integral is also written
$$
\int_C f\cdot d\alpha,
$$
called **the integral of $f$ along $C$**. With endpoints $a=\alpha(a)$ and $b=\alpha(b)$,
$$
\int_a^{b} f \quad\text{or}\quad \int_a^{b} f\cdot d\alpha
$$
denotes the line integral of $f$ from $a$ to $b$ along $\alpha$. The value depends on the **path** $\alpha$, not just the endpoints.

When $a=b$ the path is **closed**; the symbol $\displaystyle\oint$ indicates integration along a closed path.

**Component form.** If $f=(f_1,\dots,f_n)$ and $\alpha=(\alpha_1,\dots,\alpha_n)$, then
$$
\int f\cdot d\alpha = \sum_{k=1}^{n} \int_a^{b} f_k[\alpha(t)]\,\alpha_k'(t)\,dt
= \int f_1\,d\alpha_1 + \cdots + f_n\,d\alpha_n.
$$

- **2D:** $x=\alpha_1(t),\; y=\alpha_2(t)$. The integral is written
  $$
  \int_C f_1\,dx + f_2\,dy
  = \int_C f_1(x,y)\,dx + f_2(x,y)\,dy.
  $$
- **3D:** $x=\alpha_1(t),\; y=\alpha_2(t),\; z=\alpha_3(t)$. The integral is written
  $$
  \int_C f_1\,dx + f_2\,dy + f_3\,dz.
  $$

**Example.** Let $f(x,y)=\sqrt{y}\,\mathbf{i}+(x^{3}+y)\,\mathbf{j}$ for $y\ge0$. Compute $\int f\cdot d\alpha$ from $(0,0)$ to $(1,1)$.

| Path | Parametrization | Result |
|------|-----------------|--------|
| (a) Straight line | $\alpha(t)=t\mathbf{i}+t\mathbf{j}$, $0\le t\le1$ | $\displaystyle\int_0^{1}\bigl(\sqrt{t}+t^{3}+t\bigr)\,dt = \frac{17}{12}$ |
| (b) Curve $x=t^{2},\;y=t^{3}$ | $\alpha(t)=t^{2}\mathbf{i}+t^{3}\mathbf{j}$, $0\le t\le1$ | $\displaystyle\int_0^{1}\bigl(2t^{5/2}+3t^{8}+3t^{5}\bigr)\,dt = \frac{59}{42}$ |

The two values differ: the integral **depends on the path**.

Using a different parametrization of the same curve, e.g. $\beta(t)=t\mathbf{i}+t^{3/2}\mathbf{j}$, yields the same value $59/42$. The integral is independent of the **parametrization** used to describe the curve (proved in the next section).


### 10.4 Basic Properties of Line Integrals

**Linearity** (with respect to the integrand):
$$
\int (af+bg)\cdot d\alpha = a\int f\cdot d\alpha + b\int g\cdot d\alpha.
$$

**Additivity** (with respect to the path): if $C=C_1\cup C_2$ traced by $\alpha$ on $[a,c]$ and $[c,b]$ respectively ($a<c<b$),
$$
\int_C f\cdot d\alpha = \int_{C_1} f\cdot d\alpha + \int_{C_2} f\cdot d\alpha.
$$

**Change of parameter.** Let $\alpha$ be defined on $[a,b]$ and let $u:[c,d]\to[a,b]$ be differentiable with $u'\neq0$ everywhere. Then
$$
\beta(t)=\alpha[u(t)]
$$
is an **equivalent** path with the same graph. If $u'>0$ on $[c,d]$, $\alpha$ and $\beta$ trace the curve in the **same direction** ($u$ is **orientation-preserving**). If $u'<0$, they trace it in **opposite directions** ($u$ is **orientation-reversing**).

**Theorem 10.1 (Invariance under change of parameter).** Let $\alpha$ and $\beta$ be equivalent piecewise smooth paths. Then
$$
\int_C f\cdot d\alpha = \int_C f\cdot d\beta
$$
if $\alpha$ and $\beta$ trace $C$ in the same direction; and
$$
\int_C f\cdot d\alpha = -\int_C f\cdot d\beta
$$
if they trace $C$ in opposite directions.

*Proof sketch.* For smooth paths, $\beta'(t)=\alpha'[u(t)]\,u'(t)$ by the chain rule. Then
$$
\int_C f\cdot d\beta = \int_c^{d} f(\alpha[u(t)])\cdot\alpha'[u(t)]\,u'(t)\,dt.
$$
Substitute $v=u(t)$, $dv=u'(t)\,dt$:
$$
\int_C f\cdot d\beta = \int_{u(c)}^{u(d)} f(\alpha(v))\cdot\alpha'(v)\,dv = \pm\int_a^{b} f(\alpha(v))\cdot\alpha'(v)\,dv = \pm\int_C f\cdot d\alpha,
$$
with $+$ when $u(c)=a,\;u(d)=b$ (same direction) and $-$ when $u(c)=b,\;u(d)=a$ (opposite direction). Extend to piecewise smooth paths by additivity.


### 10.6 The Concept of Work as a Line Integral

A particle moving along a curve under a force field $f$ does work defined by the line integral $\int f\cdot d\alpha$.

**Example 1. Work done by a constant force.** If $f=c$ (constant), the work in moving a particle from $a$ to $b$ along any piecewise smooth path is
$$
\int f\cdot d\alpha = c\cdot(b-a),
$$
the dot product of the force and the displacement vector. For $\alpha$ joining $a$ and $b$ with $\alpha'$ continuous,
$$
\int f\cdot d\alpha = \sum_{k=1}^{n} c_k\int_a^{b}\alpha_k'(t)\,dt
= \sum_{k=1}^{n} c_k\bigl[\alpha_k(b)-\alpha_k(a)\bigr]
= c\cdot\bigl[\alpha(b)-\alpha(a)\bigr] = c\cdot(b-a).
$$
Here the work depends only on the endpoints, not on the curve. Force fields with this property are called **conservative**. (The example on p.\ 325 is nonconservative.)

**Example 2. Principle of work and energy.** A particle of mass $m$ moves under $f$ with speed $v(t)$; kinetic energy is $\tfrac{1}{2}mv^{2}(t)$. Then
$$
\int_{r(a)}^{r(b)} f\cdot d\mathbf{r} = \tfrac{1}{2}mv^{2}(b)-\tfrac{1}{2}mv^{2}(a).
$$
*Proof.* By Newton's second law, $f[r(t)]=m\mathbf{r}''(t)=m\mathbf{v}'(t)$. Hence
$$
f[r(t)]\cdot\mathbf{r}'(t) = m\mathbf{v}'(t)\cdot\mathbf{v}(t)
= \tfrac{1}{2}m\frac{d}{dt}\bigl(\mathbf{v}(t)\cdot\mathbf{v}(t)\bigr)
= \tfrac{1}{2}m\frac{d}{dt}\bigl(v^{2}(t)\bigr).
$$
Integrating from $a$ to $b$ gives the result.


### 10.7 Line Integrals with Respect to Arc Length

Let $\alpha$ be a path with $\alpha'$ continuous on $[a,b]$. The arc-length function is
$$
s(t)=\int_a^{t}\|\alpha'(u)\|\,du,\qquad s'(t)=\|\alpha'(t)\|.
$$

**Definition.** Let $\varphi$ be a scalar field defined and bounded on $C$ (the graph of $\alpha$). The **line integral of $\varphi$ with respect to arc length** along $C$ is
$$
\int_C \varphi\,ds = \int_a^{b} \varphi[\alpha(t)]\,s'(t)\,dt,
$$
whenever the integral on the right exists.

**Relation to vector line integrals.** If $\varphi[\alpha(t)] = f[\alpha(t)]\cdot T(t)$, where $T(t)=d\alpha/ds$ is the unit tangent vector, then
$$
\int_C \varphi\,ds = \int_C f\cdot d\alpha,
$$
because
$$
f[\alpha(t)]\cdot\alpha'(t)
= f[\alpha(t)]\cdot\frac{d\alpha}{ds}\,\frac{ds}{dt}
= f[\alpha(t)]\cdot T(t)\,s'(t)
= \varphi[\alpha(t)]\,s'(t).
$$

**Flow and circulation.** When $f$ is a velocity field, $f\cdot T$ is the tangential component of velocity. The integral $\int_C f\cdot T\,ds$ is called the **flow integral** of $f$ along $C$; when $C$ is closed it is called the **circulation** of $f$ along $C$. These terms are standard in fluid-flow theory.


### 10.8 Further Applications of Line Integrals

**Mass and center of mass.** A curve $C$ in 3-space can represent a wire with density $\varphi(x,y,z)$ (mass per unit length). The total mass is
$$
M = \int_C \varphi(x,y,z)\,ds.
$$
The **center of mass** $(\bar{x},\bar{y},\bar{z})$ is defined by
$$
\bar{x}M = \int_C x\varphi\,ds,\qquad
\bar{y}M = \int_C y\varphi\,ds,\qquad
\bar{z}M = \int_C z\varphi\,ds.
$$
A wire of constant density is called **uniform**; its center of mass is also called the **centroid**.

**Example 1.** Helix $\alpha(t)=a\cos t\,\mathbf{i}+a\sin t\,\mathbf{j}+bt\,\mathbf{k}$, $0\le t\le2\pi$, with density $\varphi=x^{2}+y^{2}+z^{2}$.
- $s'(t)=\|\alpha'(t)\|=\sqrt{a^{2}+b^{2}}$.
- Mass:
  $$
  M=\sqrt{a^{2}+b^{2}}\int_0^{2\pi}(a^{2}+b^{2}t^{2})\,dt
  =\sqrt{a^{2}+b^{2}}\Bigl(2\pi a^{2}+\tfrac{8}{3}\pi^{3}b^{2}\Bigr).
  $$
- $\bar{z}$ coordinate:
  $$
  \bar{z}M = \sqrt{a^{2}+b^{2}}\int_0^{2\pi}bt(a^{2}+b^{2}t^{2})\,dt
  = b\sqrt{a^{2}+b^{2}}\bigl(2\pi^{2}a^{2}+4\pi^{4}b^{2}\bigr).
  $$

**Moment of inertia.** If $\delta(x,y,z)$ is the perpendicular distance from $(x,y,z)$ on $C$ to an axis $L$, the moment of inertia about $L$ is
$$
I_L = \int_C \delta^{2}(x,y,z)\,\varphi(x,y,z)\,ds.
$$
The moments about the coordinate axes are denoted $I_x,I_y,I_z$.

**Example 2.** For the helix of Example 1, $I_z$ about the $z$-axis: $\delta^{2}=x^{2}+y^{2}=a^{2}$, so
$$
I_z = \int_C (x^{2}+y^{2})(x^{2}+y^{2}+z^{2})\,ds
= a^{2}\int_C (x^{2}+y^{2}+z^{2})\,ds = Ma^{2}.
$$


### 10.10 Open Connected Sets. Independence of the Path

**Connected open set.** An open set $S\subseteq\mathbb{R}^{n}$ is **connected** if every pair of points in $S$ can be joined by a piecewise smooth path whose graph lies in $S$. That is, for every $a,b\in S$ there exists a piecewise smooth path $\alpha$ on $[a,b]$ with $\alpha(t)\in S$ for all $t$, $\alpha(a)=a$, and $\alpha(b)=b$.

**Disconnected open set.** An open set $S$ is **disconnected** if it is the union of two or more disjoint non-empty open sets. The class of open connected sets is identical with the class of open sets that are not disconnected.

**Path independence.** Let $f$ be a continuous vector field on an open connected set $S$. The line integral of $f$ from $a$ to $b$ along a piecewise smooth path in $S$ generally depends on the path. If the integral depends only on the endpoints $a$ and $b$ and not on the joining path, we say the integral is **independent of the path from $a$ to $b$**. The line integral of $f$ is **independent of the path in $S$** if this holds for every pair of points in $S$.

> Which vector fields have line integrals independent of the path? To answer this we extend the first and second fundamental theorems of calculus to line integrals.


### 10.11 The Second Fundamental Theorem of Calculus for Line Integrals

**Theorem 10.2.** Let $\varphi$ be continuous on $[a,b]$ and assume $\int_a^{b}\varphi'(t)\,dt$ exists. If $\varphi'$ is continuous on $(a,b)$, then
$$
\int_a^{b}\varphi'(t)\,dt = \varphi(b)-\varphi(a).
$$

*Proof sketch.* Define $f(x)=\int_a^{x}\varphi'(t)\,dt$. Then $f$ is continuous on $[a,b]$, differentiable on $(a,b)$ with $f'(x)=\varphi'(x)$. By the zero-derivative theorem, $f-\varphi$ is constant on $(a,b)$, hence on $[a,b]$. Since $f(a)=0$, we get $f(b)=\varphi(b)-\varphi(a)$.

**Theorem 10.3 (Second fundamental theorem for line integrals).** Let $\varphi$ be a differentiable scalar field with a continuous gradient $\nabla\varphi$ on an open connected set $S$ in $\mathbb{R}^{n}$. Then for any two points $a$ and $b$ joined by a piecewise smooth path $\alpha$ in $S$,
$$
\int_a^{b} \nabla\varphi\cdot d\alpha = \varphi(b)-\varphi(a).
$$

*Proof sketch.* For a smooth path, by the chain rule
$$
\nabla\varphi[\alpha(t)]\cdot\alpha'(t) = g'(t),\qquad g(t)=\varphi[\alpha(t)].
$$
Since $g'$ is continuous on $(a,b)$, Theorem 10.2 gives
$$
\int_a^{b}\nabla\varphi\cdot d\alpha = \int_a^{b}g'(t)\,dt = g(b)-g(a) = \varphi(b)-\varphi(a).
$$
For piecewise smooth paths, partition $[a,b]$ into subintervals where $\alpha$ is smooth; the intermediate values telescope, leaving $\varphi(b)-\varphi(a)$.

**Consequences.**
- The line integral of a gradient is **independent of the path** in any open connected set where the gradient is continuous.
- For a closed path ($b=a$): $\displaystyle\oint\nabla\varphi\cdot d\alpha = 0$.
- (Theorem 10.4, Section 10.14) Gradients are the **only** continuous vector fields with this property.


### 10.12 Applications to Mechanics

If $f=\nabla\varphi$, then $\varphi$ is a **potential function** for $f$. The level sets of $\varphi$ are called **equipotential surfaces** (3D) or **equipotential lines** (2D).

**Example 1.** Let $\varphi(x,y,z)=r^{n}$ with $r=(x^{2}+y^{2}+z^{2})^{1/2}$. Then
$$
\nabla(r^{n}) = nr^{n-2}\mathbf{r},\qquad \mathbf{r}=x\mathbf{i}+y\mathbf{j}+z\mathbf{k}.
$$
So $\varphi$ is a potential for $f(x,y,z)=nr^{n-2}\mathbf{r}$. The equipotential surfaces are concentric spheres.

**Example 2 (Newtonian potential).** Newton's law: $f=-GmMr^{-3}\mathbf{r}$. Taking $n=-1$ in Example 1,
$$
\varphi(x,y,z)=GmMr^{-1}
$$
is the **Newtonian potential**, and $f=\nabla\varphi$. Work done moving $m$ from $r_1$ to $r_2$:
$$
\varphi(\mathbf{x}_1)-\varphi(\mathbf{x}_2)=GmM\Bigl(\frac{1}{r_1}-\frac{1}{r_2}\Bigr).
$$
If both points lie on the same equipotential surface, no work is done.

**Example 3 (Conservation of mechanical energy).** Let $f$ be a continuous force field with potential $\varphi$ on an open connected set $S$. By Theorem 10.3, work done moving from $a$ to $x$ equals $\varphi(x)-\varphi(a)$. From Section 10.6 (Example 2) this work also equals the change in kinetic energy $k(x)-k(a)$. Hence
$$
k(x)-k(a)=\varphi(x)-\varphi(a)\quad\Longrightarrow\quad k(x)-\varphi(x)=k(a)-\varphi(a).\tag{10.3}
$$
The scalar $-\varphi(x)$ is the **potential energy**.

- If a force field is a gradient, the **sum of kinetic and potential energies is constant** — the **principle of conservation of (mechanical) energy**.
- A force field with a potential is called **conservative**; no net work is done around a closed curve.
- Friction or viscosity makes a field nonconservative (mechanical energy converts to heat).


### 10.14 The First Fundamental Theorem of Calculus for Line Integrals

Recall the 1D first fundamental theorem: if $\varphi(x)=\int_a^{x}f(t)\,dt$, then $\varphi'(x)=f(x)$ at points of continuity.

To extend this to line integrals, let $f$ be continuous on an open connected set $S$. Fix $a\in S$ and define
$$
\varphi(x) = \int_a^{x} f\cdot d\alpha,
$$
where $\alpha$ is any piecewise smooth path in $S$ from $a$ to $x$. For $\varphi$ to be well-defined, the integral must be independent of the path.

**Theorem 10.4 (First fundamental theorem for line integrals).** Let $f$ be continuous on an open connected set $S$ in $\mathbb{R}^{n}$, and assume the line integral of $f$ is independent of the path in $S$. Fix $a\in S$ and define
$$
\varphi(x)=\int_a^{x} f\cdot d\alpha.
$$
Then $\nabla\varphi$ exists and equals $f$:
$$
\nabla\varphi(x)=f(x)\quad\text{for every }x\in S.
$$

*Proof sketch.* We show $D_k\varphi(x)=f_k(x)$. For $B(x;r)\subseteq S$ and unit vector $y$, by additivity
$$
\frac{\varphi(x+hy)-\varphi(x)}{h}=\frac{1}{h}\int_x^{x+hy}f\cdot d\alpha.
$$
Take the line segment $\alpha(t)=x+thy$ ($0\le t\le1$), so $\alpha'(t)=hy$:
$$
\frac{\varphi(x+hy)-\varphi(x)}{h}=\int_0^{1}f(x+thy)\cdot y\,dt.\tag{10.4}
$$
Set $y=e_k$ and substitute $u=ht$, $du=h\,dt$:
$$
\frac{\varphi(x+he_k)-\varphi(x)}{h}=\frac{1}{h}\int_0^{h}f_k(x+ue_k)\,du
=\frac{g(h)-g(0)}{h},\tag{10.5}
$$
where $g(t)=\int_0^{t}f_k(x+ue_k)\,du$. By the 1D first fundamental theorem, $g'(t)=f_k(x+te_k)$, so $g'(0)=f_k(x)$. Letting $h\to0$ gives $D_k\varphi(x)=f_k(x)$.


### 10.15 Necessary and Sufficient Conditions for a Vector Field to Be a Gradient

**Theorem 10.5.** Let $f$ be a vector field continuous on an open connected set $S$ in $\mathbb{R}^{n}$. The following are equivalent:
- (a) $f$ is the gradient of some potential function in $S$.
- (b) The line integral of $f$ is independent of the path in $S$.
- (c) The line integral of $f$ is zero around every piecewise smooth closed path in $S$.

*Proof sketch.*
- **(b) $\Rightarrow$ (a):** First fundamental theorem (Theorem 10.4).
- **(a) $\Rightarrow$ (c):** Second fundamental theorem (Theorem 10.3); for a closed path $b=a$, so $\varphi(b)-\varphi(a)=0$.
- **(c) $\Rightarrow$ (b):** Let $C_1,C_2$ be two piecewise smooth curves in $S$ with the same endpoints, traced by $\alpha$ on $[a,b]$ and $\beta$ on $[c,d]$. Define a closed path $\gamma$ by
  $$
  \gamma(t)=\begin{cases}\alpha(t),&a\le t\le b,\\\beta(b+d-t),&b\le t\le b+d-c.\end{cases}
  $$
  Then
  $$
  \oint_C f\cdot d\gamma = \int_{C_1}f\cdot d\alpha - \int_{C_2}f\cdot d\beta.
  $$
  By (c) the left side is $0$, so the two integrals are equal; hence the integral is path-independent.

*Note:* $\oint_C f\neq0$ for some closed $C$ $\Rightarrow$ $f$ is **not** a gradient. However, $\oint_C f=0$ for one (or even infinitely many) closed curves does **not** guarantee $f$ is a gradient. Example: $f(x,y)=x\,\mathbf{i}+xy\,\mathbf{j}$ has zero line integral around every circle centered at the origin, yet $f$ is not a gradient.


### 10.16 Necessary Conditions for a Vector Field to Be a Gradient

**Theorem 10.6.** Let $f=(f_1,\dots,f_n)$ be a continuously differentiable vector field on an open set $S$ in $\mathbb{R}^{n}$. If $f$ is a gradient on $S$, then
$$
D_if_j(x)=D_jf_i(x)\tag{10.6}
$$
for all $i,j=1,\dots,n$ and every $x\in S$.

*Proof sketch.* If $f=\nabla\varphi$, then $f_j=D_j\varphi$. Differentiating, $D_if_j=D_iD_j\varphi$ and $D_jf_i=D_jD_i\varphi$. Equality of mixed partials gives (10.6).

**Example 1.** $f(x,y)=3x^{2}y\,\mathbf{i}+x^{3}y\,\mathbf{j}$.
- $D_2f_1=3x^{2}$, $D_1f_2=3x^{2}y$.
- Since $D_2f_1\neq D_1f_2$ except on $x=0$ or $y=1$, $f$ is **not** a gradient on any open subset of $\mathbb{R}^{2}$.

**Example 2.** $f(x,y)=\dfrac{-y}{x^{2}+y^{2}}\,\mathbf{i}+\dfrac{x}{x^{2}+y^{2}}\,\mathbf{j}$ on $S=\mathbb{R}^{2}\setminus\{(0,0)\}$.
- $D_1f_2=D_2f_1$ everywhere on $S$.
- But $\displaystyle\oint_{\text{unit circle}} f\cdot d\alpha=\int_0^{2\pi}(\sin^{2}t+\cos^{2}t)\,dt=2\pi\neq0$.
- Hence $f$ is **not** a gradient on $S$. (The conditions of Theorem 10.6 are necessary but not always sufficient.)

*Note:* Theorem 10.6 is also sufficient on an open **convex** set (Theorem 10.9).

### 10.17 Special Methods for Constructing Potential Functions

**Method 1: Polygonal paths on a rectangle.** If $f$ is a continuous gradient on an open rectangle, integrate along segments parallel to the axes. For $f=f_1\,\mathbf{i}+f_2\,\mathbf{j}$:
$$
\varphi(x,y)=\int_a^{x}f_1(t,b)\,dt+\int_b^{y}f_2(x,t)\,dt,\tag{10.7}
$$
or equivalently
$$
\varphi(x,y)=\int_b^{y}f_2(a,t)\,dt+\int_a^{x}f_1(t,y)\,dt.\tag{10.8}
$$
Both give the same value because the line integral of a gradient is path-independent.

**Method 2: Indefinite integrals.** If $f=(f_1,f_2,f_3)=\nabla\varphi$, integrate each component:
$$
\varphi=\int f_1\,dx+A(y,z)=\int f_2\,dy+B(x,z)=\int f_3\,dz+C(x,y).
$$
Determine $A,B,C$ by inspection so all three expressions agree.

**Example 3.** $f=(2xyz+z^{2}-2y^{2}+1)\,\mathbf{i}+(x^{2}z-4xy)\,\mathbf{j}+(x^{2}y+2xz-2)\,\mathbf{k}$.
- From $f_1$: $\varphi=x^{2}yz+xz^{2}-2xy^{2}+x+A(y,z)$.
- From $f_2$: $\varphi=x^{2}yz-2xy^{2}+B(x,z)$.
- From $f_3$: $\varphi=x^{2}yz+xz^{2}-2z+C(x,y)$.
- Matching: $A(y,z)=-2z$, $B(x,z)=xz^{2}+x-2z$, $C(x,y)=x-2xy^{2}$.
- Result: $\displaystyle\varphi(x,y,z)=x^{2}yz+xz^{2}-2xy^{2}+x-2z$.

**Method 3: Line segment on a convex set.** A set $S$ is **convex** if every pair of points can be joined by a line segment lying in $S$. If $f$ is a continuous gradient on an open convex set, use $\alpha(t)=a+t(x-a)$ ($0\le t\le1$):
$$
\varphi(x)=\int_0^{1}f\bigl(a+t(x-a)\bigr)\cdot(x-a)\,dt.\tag{10.9}
$$
If $S$ contains the origin, take $a=O$:
$$
\varphi(x)=\int_0^{1}f(tx)\cdot x\,dt.\tag{10.10}
$$


### 10.19 Applications to Exact Differential Equations of First Order

A first-order ODE $y'=f(x,y)$ can be written in differential form by multiplying by a nonzero factor $Q(x,y)$:
$$
P(x,y)\,dx+Q(x,y)\,dy=0,\tag{10.11}
$$
where $P=-fQ$. Associate the vector field $V(x,y)=P(x,y)\,\mathbf{i}+Q(x,y)\,\mathbf{j}$.

The equation (10.11) is **exact** in $S$ if $V$ is a gradient, i.e. $V=\nabla\varphi$ for some scalar field $\varphi$ on $S$. Then $\partial\varphi/\partial x=P$ and $\partial\varphi/\partial y=Q$, so (10.11) becomes
$$
\frac{\partial\varphi}{\partial x}\,dx+\frac{\partial\varphi}{\partial y}\,dy=0.
$$

**Theorem 10.7.** Assume (10.11) is exact in an open connected set $S$, and let $\varphi$ satisfy $\partial\varphi/\partial x=P$, $\partial\varphi/\partial y=Q$ in $S$. Then every solution $y=Y(x)$ of (10.11) with graph in $S$ satisfies
$$
\varphi[x,Y(x)]=C
$$
for some constant $C$. Conversely, if $\varphi(x,y)=C$ defines $y$ implicitly as a differentiable function of $x$, that function is a solution.

*Proof sketch.* Set $g(x)=\varphi[x,Y(x)]$. By the chain rule,
$$
g'(x)=D_1\varphi[x,Y(x)]+D_2\varphi[x,Y(x)]\,Y'(x)=P(x,y)+Q(x,y)\,y'.\tag{10.12}
$$
If $y$ satisfies (10.11), then $g'(x)=0$, so $g$ is constant and $\varphi(x,y)=C$. The converse follows by reversing the argument.

**Method.** Construct a potential $\varphi$; the solutions are the level curves $\varphi(x,y)=C$.

**Example 1.** $\displaystyle\frac{dy}{dx}=-\frac{3x^{2}+6xy^{2}}{6x^{2}y+4y^{3}}$
- Rewrite: $(3x^{2}+6xy^{2})\,dx+(6x^{2}y+4y^{3})\,dy=0$.
- Potential: $\varphi(x,y)=x^{3}+3x^{2}y^{2}+y^{4}$.
- Solutions: $x^{3}+3x^{2}y^{2}+y^{4}=C$.

**Integrating factors.** If (10.11) is not exact, a nonzero multiplier $\mu(x,y)$ producing an exact equation is called an **integrating factor**.

**Example 2.** $y\,dx+2x\,dy=0$ is not exact ($\partial P/\partial y=1\neq2=\partial Q/\partial x$). Multiplying by $y$:
$$
y^{2}\,dx+2xy\,dy=0,
$$
which is exact with potential $\varphi(x,y)=xy^{2}$. Solutions: $xy^{2}=C$. (Another integrating factor is $\mu=2xy^{3}$.)

