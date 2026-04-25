[<- Previous: 13. Applications of Vector Algebra to Analytic Geometry](13-applications-of-vector-algebra-to-analytic-geometry.md) | [Next: 15. Linear Spaces ->](15-linear-spaces.md)

# 14. Calculus of Vector-Valued Functions

## 14.1 Vector-Valued Functions of a Real Variable

### 14.1.1 Definition

A **vector-valued function of a real variable** is a function whose domain is a set of real numbers and whose range is a subset of $n$-space $V_n$.

> We have already encountered such functions in Chapter 13. For example, the line through a point $P$ parallel to a nonzero vector $A$ is the range of the vector-valued function $X(t)=P+tA$.

Vector-valued functions are denoted by capital letters $F,G,X,Y$, etc., or by small bold-face italic letters $\boldsymbol{f},\boldsymbol{g}$. The value at $t$ is written $F(t)$. In the examples studied, the domain is usually an interval which may contain one or both endpoints or which may be infinite.

## 14.2 Algebraic Operations and Components

### 14.2.1 Operations on Vector-Valued Functions

If $F$ and $G$ are vector-valued functions and $u$ is a real-valued function, all having a common domain, we define:
- **Sum:** $(F+G)(t)=F(t)+G(t)$
- **Scalar product:** $(uF)(t)=u(t)F(t)$
- **Dot product:** $(F\cdot G)(t)=F(t)\cdot G(t)$ (real-valued)
- **Cross product:** $(F\times G)(t)=F(t)\times G(t)$ (in 3-space)

### 14.2.2 Composition

If $F$ is vector-valued and $u$ is real-valued, the composition $G=F\circ u$ is the vector-valued function
$$
G(t)=F[u(t)].
$$

### 14.2.3 Component Functions

If $F$ takes values in $V_n$, each vector $F(t)$ has $n$ components, and we can write
$$
F(t)=\bigl(f_1(t),f_2(t),\dots,f_n(t)\bigr).
$$
The real-valued functions $f_1,\dots,f_n$ are called the **component functions** (or simply **components**) of $F$. We indicate this by writing $F=(f_1,\dots,f_n)$.

> Every vector-valued function gives rise to $n$ real-valued component functions, and vice versa. This componentwise viewpoint is fundamental for extending calculus to vector-valued functions.

## 14.3 Limits, Derivatives, and Integrals

### 14.3.1 Componentwise Definitions

Let $F=(f_1,\dots,f_n)$ be a vector-valued function. We define **limit**, **derivative**, and **integral** componentwise:

| Operation | Definition |
|-----------|------------|
| Limit | $\displaystyle\lim_{t\to p}F(t)=\Bigl(\lim_{t\to p}f_1(t),\dots,\lim_{t\to p}f_n(t)\Bigr)$ |
| Derivative | $\displaystyle F'(t)=\bigl(f_1'(t),\dots,f_n'(t)\bigr)$ |
| Definite integral | $\displaystyle\int_a^b F(t)\,dt=\Bigl(\int_a^b f_1(t)\,dt,\dots,\int_a^b f_n(t)\,dt\Bigr)$ |

These are meaningful whenever the components on the right are meaningful.

We say $F$ is **continuous**, **differentiable**, or **integrable** on an interval if each component has the corresponding property.

> Many theorems on limits, continuity, differentiation, and integration of real-valued functions extend directly to vector-valued functions via these componentwise definitions.

### 14.3.2 Differentiation Rules

**Theorem 14.1.** If $F$, $G$, and $u$ are differentiable on an interval, then so are $F+G$, $uF$, and $F\cdot G$, and
$$
(F+G)'=F'+G',\qquad (uF)'=u'F+uF',\qquad (F\cdot G)'=F'\cdot G+F\cdot G'.
$$
If $F$ and $G$ take values in $V_3$, we also have
$$
(F\times G)'=F'\times G+F\times G'.
$$

> The proofs are routine componentwise verifications. For $(uF)'$, writing $F=(f_1,\dots,f_n)$ gives $(uf_k)'=u'f_k+uf_k'$, whence $(uF)'=u'F+uF'$.

> Since the cross product is not commutative, preserve the order of factors in the formula for $(F\times G)'$.

### 14.3.3 Constant-Length Property

**Theorem 14.2.** If a differentiable vector-valued function $F$ has constant length on an open interval $I$, then $F\cdot F'=0$ on $I$. In other words, $F'(t)$ is perpendicular to $F(t)$ for each $t\in I$.

*Proof.* Let $g(t)=\|F(t)\|^2=F(t)\cdot F(t)$. By hypothesis $g$ is constant, so $g'=0$. But $g'=F'\cdot F+F\cdot F'=2F\cdot F'$, hence $F\cdot F'=0$. ∎

### 14.3.4 Chain Rule

**Theorem 14.3.** Let $G=F\circ u$, where $F$ is vector-valued and $u$ is real-valued. If $u$ is continuous at $t$ and $F$ is continuous at $u(t)$, then $G$ is continuous at $t$. If $u'(t)$ and $F'[u(t)]$ exist, then $G'(t)$ exists and
$$
G'(t)=F'[u(t)]\,u'(t).
$$

### 14.3.5 Properties of Integrals

**Theorem 14.4 (Linearity and Additivity).** If $F$ and $G$ are integrable on $[a,b]$, so is $c_1F+c_2G$ for all scalars $c_1,c_2$, and
$$
\int_a^b\bigl(c_1F(t)+c_2G(t)\bigr)\,dt=c_1\int_a^b F(t)\,dt+c_2\int_a^b G(t)\,dt.
$$
Also, for each $c\in[a,b]$,
$$
\int_a^b F(t)\,dt=\int_a^c F(t)\,dt+\int_c^b F(t)\,dt.
$$

**Theorem 14.5 (First Fundamental Theorem of Calculus).** Assume $F$ is continuous on $[a,b]$. If $c\in[a,b]$, define the indefinite integral
$$
A(x)=\int_c^x F(t)\,dt\qquad(a\le x\le b).
$$
Then $A'(x)$ exists and $A'(x)=F(x)$ for each $x\in(a,b)$.

**Theorem 14.6 (Second Fundamental Theorem of Calculus).** Assume $F$ has a continuous derivative $F'$ on an open interval $I$. Then, for each $c,x\in I$,
$$
F(x)=F(c)+\int_c^x F'(t)\,dt.
$$

**Theorem 14.7 (Dot product with a constant vector).** If $F=(f_1,\dots,f_n)$ is integrable on $[a,b]$, then for every vector $C=(c_1,\dots,c_n)$ the dot product $C\cdot F$ is integrable on $[a,b]$, and
$$
C\cdot\int_a^b F(t)\,dt=\int_a^b C\cdot F(t)\,dt.
$$

*Proof.* Componentwise:
$$
C\cdot\int_a^b F(t)\,dt=\sum_{i=1}^n c_i\int_a^b f_i(t)\,dt=\int_a^b\sum_{i=1}^n c_if_i(t)\,dt=\int_a^b C\cdot F(t)\,dt.\quad\text{∎}
$$

**Theorem 14.8 (Norm inequality).** If $F$ and $\|F\|$ are integrable on $[a,b]$, then
$$
\Bigl\|\int_a^b F(t)\,dt\Bigr\|\le\int_a^b\|F(t)\|\,dt.\tag{14.1}
$$

*Proof.* Let $C=\int_a^b F(t)\,dt$. If $C=O$, (14.1) holds trivially. Assume $C\neq O$. By Theorem 14.7,
$$
\|C\|^2=C\cdot C=C\cdot\int_a^b F(t)\,dt=\int_a^b C\cdot F(t)\,dt.\tag{14.2}
$$
Since $C\cdot F(t)$ is real-valued, the Cauchy–Schwarz inequality gives
$$
\int_a^b C\cdot F(t)\,dt\le\int_a^b|C\cdot F(t)|\,dt\le\int_a^b\|C\|\,\|F(t)\|\,dt=\|C\|\int_a^b\|F(t)\|\,dt.\tag{14.3}
$$
Combining (14.2) and (14.3) yields $\|C\|^2\le\|C\|\int_a^b\|F(t)\|\,dt$. Since $\|C\|>0$, divide by $\|C\|$ to obtain (14.1). ∎

## 14.4 Applications to Curves. Tangency

### 14.4.1 Curves and Parametric Representation

Let $X$ be a vector-valued function with domain an interval $I$. As $t$ runs through $I$, the values $X(t)$ trace a set of points called the **graph** of $X$. If the values lie in 2-space or 3-space, the graph can be visualized geometrically.

- If $X$ is **continuous** on $I$, its graph is called a **curve**; more specifically, the curve **described by** $X$.
- The interval $I$ is called a **parametric interval**; each $t\in I$ is a **parameter**.
- The curve is also said to be described **parametrically** by $X$.

> Example: $X(t)=P+tA$ ($A\neq O$) describes a straight line through $P$ parallel to $A$.

### 14.4.2 Tangent Vector and Tangent Line

Form the difference quotient
$$
\frac{X(t+h)-X(t)}{h}.\tag{14.4}
$$
As $h\to0$, if $X'(t)$ exists,
$$
\lim_{h\to0}\frac{X(t+h)-X(t)}{h}=X'(t).
$$

**Definition.** Let $C$ be a curve described by a continuous vector-valued function $X$. If $X'(t)$ exists and is nonzero, the straight line through $X(t)$ parallel to $X'(t)$ is called the **tangent line** to $C$ at $X(t)$. The vector $X'(t)$ is called a **tangent vector** to $C$ at $X(t)$.

### 14.4.3 Examples

**Example 1 (Straight line).** For $X(t)=P+tA$ with $A\neq O$, we have $X'(t)=A$. The tangent line at each point coincides with the graph itself.

**Example 2 (Circle).** If $X$ describes a circle of radius $a$ centered at $P$, then $\|X(t)-P\|=a$ for each $t$. The vector $X(t)-P$ is the **radius vector**. Since it has constant length, Theorem 14.2 implies it is perpendicular to its derivative, hence perpendicular to the tangent line — consistent with elementary plane geometry.

**Example 3 (Invariance under change of parameter).** Different functions can have the same graph. Suppose $X$ is continuous on $I$ and $u$ is a differentiable real-valued function with $u'\neq0$ on an interval $J$, with range $u(J)=I$. Then
$$
Y(t)=X[u(t)]
$$
is a continuous vector-valued function having the same graph as $X$. Two such functions $X$ and $Y$ are called **equivalent**; they provide different **parametric representations** of the same curve, and $u$ defines a **change of parameter**.

By the chain rule,
$$
Y'(t)=X'[u(t)]\,u'(t).
$$
Since $u'(t)\neq0$, if $X'[u(t)]\neq0$ then $Y'(t)\neq0$ and $Y'(t)$ is parallel to $X'[u(t)]$. Therefore both representations yield the **same tangent line** at each point of the curve. Tangency is a geometric concept **invariant** under change of parameter.

### 14.4.4 Reflection Properties of the Conic Sections

Conic sections have reflection properties used in optical and acoustical design:

| Conic | Reflection property |
|-------|---------------------|
| **Ellipse** | Light rays from one focus converge at the other focus. |
| **Hyperbola** | Light rays directed toward one focus converge at the other focus. |
| **Parabola** | Light rays parallel to the axis converge at the focus. |

*Proof sketch (ellipse and hyperbola).* Place focus $F_1$ at the origin and let $\boldsymbol{u}_1$, $\boldsymbol{u}_2$ be unit vectors in the directions of $X$ and $X-F_2$, respectively. Write the focal distances $d_1=\|X\|$ and $d_2=\|X-F_2\|$, so
$$
X=d_1\boldsymbol{u}_1,\qquad X=d_2\boldsymbol{u}_2+F_2.
$$
Differentiating and using that unit vectors are perpendicular to their derivatives (Theorem 14.2):
$$
X'\cdot\boldsymbol{u}_1=d_1',\qquad X'\cdot\boldsymbol{u}_2=d_2'.\tag{14.5}
$$
Adding and subtracting gives
$$
X'\cdot(\boldsymbol{u}_1+\boldsymbol{u}_2)=d_1'+d_2',\qquad X'\cdot(\boldsymbol{u}_1-\boldsymbol{u}_2)=d_1'-d_2'.\tag{14.6}
$$

- **Ellipse:** $d_1+d_2$ is constant, so $d_1'+d_2'=0$. By (14.6), $X'\cdot(\boldsymbol{u}_1+\boldsymbol{u}_2)=0$.
- **Hyperbola:** $d_1-d_2$ is constant, so $d_1'-d_2'=0$. By (14.6), $X'\cdot(\boldsymbol{u}_1-\boldsymbol{u}_2)=0$.

Let $T=X'/\|X'\|$ be the unit tangent vector. Then:
- On the ellipse: $T\cdot\boldsymbol{u}_2=-T\cdot\boldsymbol{u}_1$, so $\cos\theta_2=-\cos\theta_1$, giving $\theta_2=\pi-\theta_1$.
- On the hyperbola: $T\cdot\boldsymbol{u}_2=T\cdot\boldsymbol{u}_1$, so $\cos\theta_2=\cos\theta_1$, giving $\theta_2=\theta_1$.

These angle relations are exactly the reflection properties.

## 14.5 Applications to Curvilinear Motion. Velocity, Speed, and Acceleration

### 14.5.1 Definitions

Consider a particle whose position at time $t$ is given by a vector-valued function $X(t)$. The vector-valued function $X$ serves as a natural mathematical model for the motion.

**Terminology:**
- $X(t)$ — **position function** (or **position vector**)
- $X'(t)$ — **velocity vector** at time $t$
- $\|X'(t)\|$ — **speed** at time $t$
- $X''(t)$ — **acceleration vector**

**Notation.** Often the position function is denoted by $\boldsymbol{r}$, the velocity by $\boldsymbol{v}$, the speed by $v$, and the acceleration by $\boldsymbol{a}$:
$$
\boldsymbol{v}=\boldsymbol{r}',\qquad v=\|\boldsymbol{v}\|,\qquad \boldsymbol{a}=\boldsymbol{v}'=\boldsymbol{r}''.
$$

The velocity vector lies along the tangent line to the path. The speed measures how fast the particle is moving; the acceleration measures the rate of change of velocity (speed or direction, or both). Unlike velocity, the acceleration vector does not necessarily lie along the tangent line.

### 14.5.2 Linear Motion

**Example 1.** For motion along a line,
$$
\boldsymbol{r}(t)=P+f(t)A,\qquad A\neq O,
$$
the velocity, speed, and acceleration are
$$
\boldsymbol{v}(t)=f'(t)A,\qquad v(t)=\|\boldsymbol{v}(t)\|=|f'(t)|\,\|A\|,\qquad \boldsymbol{a}(t)=f''(t)A.
$$
If $f'(t)$ and $f''(t)$ are nonzero, the acceleration is parallel to the velocity.

### 14.5.3 Circular Motion

**Example 2.** In polar coordinates $x=r\cos\theta$, $y=r\sin\theta$, fix $r=a$ and let $\theta$ vary. The point $(x,y)$ traces a circle of radius $a$. With $\theta=f(t)$,
$$
\boldsymbol{r}(t)=a\cos f(t)\,\boldsymbol{i}+a\sin f(t)\,\boldsymbol{j},
\qquad\boldsymbol{v}(t)=-af'(t)\sin f(t)\,\boldsymbol{i}+af'(t)\cos f(t)\,\boldsymbol{j}.
$$
The speed is
$$
v(t)=\|\boldsymbol{v}(t)\|=a\,|f'(t)|.
$$
The factor $|f'(t)|=|d\theta/dt|$ is called the **angular speed**.

**Constant angular speed.** If $\theta=\omega t$ ($\omega>0$ constant),
$$
\boldsymbol{r}(t)=a\cos\omega t\,\boldsymbol{i}+a\sin\omega t\,\boldsymbol{j},\qquad
\boldsymbol{v}(t)=-\omega a\sin\omega t\,\boldsymbol{i}+\omega a\cos\omega t\,\boldsymbol{j},\qquad
v(t)=a\omega.
$$
The acceleration is
$$
\boldsymbol{a}(t)=-\omega^2a\cos\omega t\,\boldsymbol{i}-\omega^2a\sin\omega t\,\boldsymbol{j}=-\omega^2\boldsymbol{r}(t),
$$
which is always directed **opposite** to the position vector — i.e. toward the center of the circle. This is called **centripetal** ("center-seeking") acceleration.

> If the particle has mass $m$, Newton's second law gives force $m\boldsymbol{a}(t)$, directed toward the center. The equal and opposite reaction is called **centrifugal** ("center-fleeing").

### 14.5.4 Motion on an Ellipse

**Example 3.** For an ellipse $x^2/a^2+y^2/b^2=1$, introduce the **eccentric angle** $\theta$:
$$
x=a\cos\theta,\qquad y=b\sin\theta.
$$
With $\theta=f(t)$, the position function is
$$
\boldsymbol{r}(t)=a\cos f(t)\,\boldsymbol{i}+b\sin f(t)\,\boldsymbol{j}.
$$
If $\theta=\omega t$ ($\omega$ constant),
$$
\boldsymbol{v}(t)=\omega(-a\sin\omega t\,\boldsymbol{i}+b\cos\omega t\,\boldsymbol{j}),\qquad
v(t)=\omega(a^2\sin^2\omega t+b^2\cos^2\omega t)^{1/2},
$$
$$
\boldsymbol{a}(t)=-\omega^2(a\cos\omega t\,\boldsymbol{i}+b\sin\omega t\,\boldsymbol{j})=-\omega^2\boldsymbol{r}(t).
$$
Thus, when the eccentric angle changes at a constant rate, the acceleration is centripetal.

### 14.5.5 Motion on a Helix

**Example 4.** A point $(x,y,z)$ revolves around the $z$-axis at constant distance $a$ while moving parallel to the $z$-axis so that its $z$-component is proportional to the angle of revolution. The path is a **circular helix**:
$$
x=a\cos\theta,\qquad y=a\sin\theta,\qquad z=b\theta.\tag{14.7}
$$
Here $a>0$, $b\neq0$. As $\theta$ varies from $0$ to $2\pi$, the $x$ and $y$ coordinates return to their original values while $z$ changes from $0$ to $2\pi b$. The number $2\pi b$ is the **pitch** of the helix.

With $\theta=\omega t$ ($\omega$ constant):
$$
\boldsymbol{r}(t)=a\cos\omega t\,\boldsymbol{i}+a\sin\omega t\,\boldsymbol{j}+b\omega t\,\boldsymbol{k},
$$
$$
\boldsymbol{v}(t)=-\omega a\sin\omega t\,\boldsymbol{i}+\omega a\cos\omega t\,\boldsymbol{j}+b\omega\,\boldsymbol{k},
\qquad
\boldsymbol{a}(t)=-\omega^2(a\cos\omega t\,\boldsymbol{i}+a\sin\omega t\,\boldsymbol{j}).
$$
The acceleration is parallel to the $xy$-plane and directed toward the $z$-axis.

Eliminating $\theta$ from the first two equations of (14.7) gives $x^2+y^2=a^2$, a circular cylinder of radius $a$ about the $z$-axis. The helix winds around this cylinder.

## 14.6 The Unit Tangent, the Principal Normal, and the Osculating Plane

### 14.6.1 The Unit Tangent Vector

For a motion described by a vector-valued function $X$, the **unit tangent vector** is defined by
$$
T(t)=\frac{X'(t)}{\|X'(t)\|},
\qquad\text{whenever }\|X'(t)\|\neq0.
$$
Note that $\|T(t)\|=1$ for all $t$.

Since $T$ has constant length, Theorem 14.2 implies $T$ is perpendicular to its derivative $T'$.

> As the particle moves along the curve, $T$ can change only in direction. The tendency of $T$ to change direction is measured by $T'$.

### 14.6.2 The Principal Normal and the Osculating Plane

If the motion is linear, $T'=O$. If $T'\neq O$, the unit vector in the direction of $T'$ is called the **principal normal** to the curve, denoted by $N$:
$$
N(t)=\frac{T'(t)}{\|T'(t)\|},\qquad\text{whenever }\|T'(t)\|\neq0.
$$

When $T(t)$ and $N(t)$ are attached to the curve at $X(t)$, they determine a plane called the **osculating plane** of the curve. If three points $X(t_1),X(t_2),X(t_3)$ approach $X(t_1)$ as $t_2,t_3\to t_1$, the plane through them approaches the osculating plane. Thus the osculating plane is the plane that **best fits** the curve at each point.

> If the curve is a plane curve (not a straight line), the osculating plane coincides with the plane of the curve.

### 14.6.3 Decomposition of Acceleration

**Theorem 14.9.** For a motion described by $\boldsymbol{r}$, let $v(t)=\|\boldsymbol{r}'(t)\|$ denote the speed. Then the acceleration vector $\boldsymbol{a}$ is a linear combination of $T$ and $T'$:
$$
\boldsymbol{a}(t)=v'(t)T(t)+v(t)T'(t).\tag{14.8}
$$
If $T'(t)\neq O$, we also have
$$
\boldsymbol{a}(t)=v'(t)T(t)+v(t)\,\|T'(t)\|\,N(t).\tag{14.9}
$$

*Proof.* From $\boldsymbol{v}(t)=v(t)T(t)$, differentiate:
$$
\boldsymbol{a}(t)=\boldsymbol{v}'(t)=v'(t)T(t)+v(t)T'(t),
$$
which proves (14.8). To obtain (14.9), substitute $T'(t)=\|T'(t)\|\,N(t)$. ∎

> The acceleration vector always lies in the osculating plane. The coefficients of $T(t)$ and $N(t)$ in (14.9) are called the **tangential** and **normal components** of acceleration, respectively:
> - $v'(t)$ — tangential component (change in speed)
> - $v(t)\|T'(t)\|$ — normal component (change in direction)

### 14.6.4 Geometric Interpretation for Plane Curves

For a plane curve, write the unit tangent as
$$
T(t)=\cos\alpha(t)\,\boldsymbol{i}+\sin\alpha(t)\,\boldsymbol{j},
$$
where $\alpha(t)$ is the angle of inclination of the tangent vector (Figure 14.11). Differentiating,
$$
T'(t)=-\sin\alpha(t)\,\alpha'(t)\,\boldsymbol{i}+\cos\alpha(t)\,\alpha'(t)\,\boldsymbol{j}=\alpha'(t)\,\boldsymbol{u}(t),
$$
where $\boldsymbol{u}(t)$ is a unit vector. Therefore
$$
\|T'(t)\|=|\alpha'(t)|.
$$
This shows that $\|T'(t)\|$ measures the **rate of change of the angle of inclination** of the tangent vector.

- When $\alpha'(t)>0$, the angle is increasing and $\boldsymbol{u}(t)=N(t)$.
- When $\alpha'(t)<0$, the angle is decreasing and $\boldsymbol{u}(t)=-N(t)$.

Note that $\boldsymbol{u}(t)$ makes angle $\alpha(t)+\frac{\pi}{2}$ with the $x$-axis, since
$$
\boldsymbol{u}(t)=-\sin\alpha(t)\,\boldsymbol{i}+\cos\alpha(t)\,\boldsymbol{j}=\cos\Bigl(\alpha(t)+\frac{\pi}{2}\Bigr)\boldsymbol{i}+\sin\Bigl(\alpha(t)+\frac{\pi}{2}\Bigr)\boldsymbol{j}.
$$

## 14.7 The Definition of Arc Length

### 14.7.1 Rectifiable Curves

To define the length of a curve described by a vector-valued function $\boldsymbol{r}$ on $[a,b]$, inscribe a polygon whose vertices are points on the curve. Given a partition
$$
P=\{t_0,t_1,\dots,t_n\},\qquad a=t_0<t_1<\cdots<t_n=b,
$$
let $\pi(P)$ be the polygon with vertices $\boldsymbol{r}(t_0),\boldsymbol{r}(t_1),\dots,\boldsymbol{r}(t_n)$. The length of $\pi(P)$ is
$$
|\pi(P)|=\sum_{k=1}^{n}\|\boldsymbol{r}(t_k)-\boldsymbol{r}(t_{k-1})\|.
$$

**Definition.** If there exists a positive number $M$ such that
$$
|\pi(P)|\le M\tag{14.10}
$$
for **all** partitions $P$ of $[a,b]$, then the curve is said to be **rectifiable**, and its **arc length**, denoted by $\Lambda(a,b)$, is defined as the least upper bound of the set of all numbers $|\pi(P)|$. If no such $M$ exists, the curve is called **nonrectifiable**.

> Note that whenever (14.10) holds,
> $$
> |\pi(P)|\le\Lambda(a,b)\le M.\tag{14.11}
> $$

### 14.7.2 Arc Length and the Integral of Speed

**Theorem 14.10.** Denote by $\boldsymbol{v}(t)$ the velocity vector of the curve with position vector $\boldsymbol{r}(t)$, and let $v(t)=\|\boldsymbol{v}(t)\|$ denote the speed. If $\boldsymbol{v}$ is continuous on $[a,b]$, the curve is rectifiable and its length satisfies
$$
\Lambda(a,b)\le\int_a^b v(t)\,dt.\tag{14.12}
$$

*Proof.* For each partition $P$,
$$
\begin{aligned}
|\pi(P)|&=\sum_{k=1}^{n}\|\boldsymbol{r}(t_k)-\boldsymbol{r}(t_{k-1})\|
=\sum_{k=1}^{n}\Bigl\|\int_{t_{k-1}}^{t_k}\boldsymbol{r}'(t)\,dt\Bigr\|\\
&=\sum_{k=1}^{n}\Bigl\|\int_{t_{k-1}}^{t_k}\boldsymbol{v}(t)\,dt\Bigr\|
\le\sum_{k=1}^{n}\int_{t_{k-1}}^{t_k}\|\boldsymbol{v}(t)\|\,dt
=\int_a^b v(t)\,dt.
\end{aligned}
$$
Thus $\int_a^b v(t)\,dt$ is an upper bound for all $|\pi(P)|$, proving rectifiability and (14.12). ∎

> In a later section we shall prove that the inequality in (14.12) is, in fact, an **equality**. The proof uses the **additivity** of arc length.

## 14.8 Additivity of Arc Length

### 14.8.1 The Additive Property

If a rectifiable curve is cut into two pieces, the length of the whole equals the sum of the lengths of the parts.

**Theorem 14.11.** Consider a rectifiable curve of length $\Lambda(a,b)$ traced out by $\boldsymbol{r}(t)$ on $[a,b]$. If $a<c<b$, let $C_1$ and $C_2$ be the curves traced out on $[a,c]$ and $[c,b]$, respectively. Then $C_1$ and $C_2$ are also rectifiable, and
$$
\Lambda(a,b)=\Lambda(a,c)+\Lambda(c,b).
$$

### 14.8.2 Proof

Let $P_1$ and $P_2$ be arbitrary partitions of $[a,c]$ and $[c,b]$. Their union is a partition $P$ of $[a,b]$, and
$$
|\pi(P_1)|+|\pi(P_2)|=|\pi(P)|\le\Lambda(a,b).\tag{14.13}
$$
Hence $|\pi(P_1)|$ and $|\pi(P_2)|$ are bounded, so $C_1$ and $C_2$ are rectifiable. From (14.13),
$$
|\pi(P_1)|\le\Lambda(a,b)-|\pi(P_2)|.
$$
Keep $P_2$ fixed and let $P_1$ vary. Since $\Lambda(a,b)-|\pi(P_2)|$ is an upper bound for all $|\pi(P_1)|$, it is at least their least upper bound:
$$
\Lambda(a,c)\le\Lambda(a,b)-|\pi(P_2)|\quad\Longrightarrow\quad|\pi(P_2)|\le\Lambda(a,b)-\Lambda(a,c).
$$
Now let $P_2$ vary. By the same reasoning,
$$
\Lambda(c,b)\le\Lambda(a,b)-\Lambda(a,c),
$$
i.e.
$$
\Lambda(a,c)+\Lambda(c,b)\le\Lambda(a,b).\tag{14.14}
$$

For the reverse inequality, start with any partition $P$ of $[a,b]$ and adjoin $c$ to obtain partitions $P_1$ of $[a,c]$ and $P_2$ of $[c,b]$. Then
$$
|\pi(P)|\le|\pi(P_1)|+|\pi(P_2)|\le\Lambda(a,c)+\Lambda(c,b).
$$
Thus $\Lambda(a,c)+\Lambda(c,b)$ is an upper bound for all $|\pi(P)|$, so
$$
\Lambda(a,b)\le\Lambda(a,c)+\Lambda(c,b).
$$
Combined with (14.14), this yields $\Lambda(a,b)=\Lambda(a,c)+\Lambda(c,b)$. ∎

## 14.9 The Arc-Length Function

### 14.9.1 Definition

- Let a curve be traced out by a position vector $\boldsymbol{r}(t)$.
- The **arc-length function** $s$ is defined by:
  $$
  s(t)=\Lambda(a,t)\quad\text{if }t>a,\qquad s(a)=0.
  $$
- $s(a)=0$ means motion begins at $t=a$.

### 14.9.2 Monotonicity

**Theorem 14.12.** For any rectifiable curve, the arc-length function $s$ is monotonically increasing on $[a,b]$:
$$
s(t_1)\le s(t_2)\quad\text{if }a\le t_1<t_2\le b.
$$
(Equation 14.15)

**Proof:**
$$
s(t_2)-s(t_1)=\Lambda(a,t_2)-\Lambda(a,t_1)=\Lambda(t_1,t_2)\ge0.
$$

### 14.9.3 Derivative of Arc Length

**Theorem 14.13.** Let $s$ be the arc-length function and $v(t)$ the speed. If $v$ is continuous on $[a,b]$, then $s'(t)$ exists for each $t\in(a,b)$ and:
$$
\boxed{s'(t)=v(t)}
$$
(Equation 14.16)

**Proof sketch:**
1. Define $f(t)=\int_a^t v(u)\,du$. By the first FTC, $f'(t)=v(t)$.
2. Form the difference quotient:
   $$
   \left\|\frac{\boldsymbol{r}(t+h)-\boldsymbol{r}(t)}{h}\right\|.
   $$
   (Equation 14.17)
3. For $h>0$:
   $$
   \|\boldsymbol{r}(t+h)-\boldsymbol{r}(t)\|\le\Lambda(t,t+h)=s(t+h)-s(t).
   $$
4. Using Theorem 14.10:
   $$
   \left\|\frac{\boldsymbol{r}(t+h)-\boldsymbol{r}(t)}{h}\right\|\le\frac{s(t+h)-s(t)}{h}\le\frac{1}{h}\int_t^{t+h}v(u)\,du=\frac{f(t+h)-f(t)}{h}.
   $$
5. As $h\to0$: left side $\to\|\boldsymbol{r}'(t)\|=v(t)$; right side $\to f'(t)=v(t)$.
6. By squeezing, $\displaystyle\lim_{h\to0}\frac{s(t+h)-s(t)}{h}=v(t)$.

### 14.9.4 Computing Arc Length by Integration

Using (14.16) and the second FTC:
$$
s(t_2)-s(t_1)=\int_{t_1}^{t_2}s'(t)\,dt=\int_{t_1}^{t_2}v(t)\,dt.
$$
In particular:
$$
\boxed{\Lambda(a,b)=\int_a^b v(t)\,dt}.
$$

### 14.9.5 Example 1 — Circular Arc

- Circle of radius $a$: $\boldsymbol{r}(t)=a\cos t\,\boldsymbol{i}+a\sin t\,\boldsymbol{j}$.
- Velocity: $\boldsymbol{v}(t)=-a\sin t\,\boldsymbol{i}+a\cos t\,\boldsymbol{j}$.
- Speed: $v(t)=a$.
- Arc length over angle $\theta$: $\displaystyle\int_0^\theta a\,dt=a\theta$.
- **Length is proportional to subtended angle**; for unit circle ($a=1$), arc length equals angular measure.

### 14.9.6 Example 2 — Graph of a Real-Valued Function

- Graph of $f$ on $[a,b]$: $\boldsymbol{r}(t)=t\,\boldsymbol{i}+f(t)\,\boldsymbol{j}$.
- Velocity: $\boldsymbol{v}(t)=\boldsymbol{i}+f'(t)\,\boldsymbol{j}$.
- Speed: $v(t)=\sqrt{1+[f'(t)]^2}$.
- Arc length:
  $$
  \boxed{s(x)=\int_a^x\sqrt{1+[f'(t)]^2}\,dt}
  $$
  (Equation 14.18)

## 14.10 Curvature of a Curve

### 14.10.1 Curvature Vector

- For a straight line, the unit tangent $T$ is constant, so $T'=O$.
- For a non-straight curve, $T'$ measures the tendency of the tangent to change direction.
- The **curvature vector** is the rate of change of $T$ with respect to arc length:
  $$
  \frac{dT}{ds}
  $$
- By the chain rule and $s'(t)=v(t)$:
  $$
  \frac{dT}{ds}=\frac{dt}{ds}\frac{dT}{dt}=\frac{1}{s'(t)}T'(t)=\frac{1}{v(t)}T'(t).
  $$

### 14.10.2 Curvature

Since $T'(t)=\|T'(t)\|\,N(t)$, we obtain:

$$
\frac{dT}{ds}=\frac{\|T'(t)\|}{v(t)}N(t)
$$
(Equation 14.19)

The scalar factor multiplying $N(t)$ is a nonnegative number called the **curvature** $\kappa(t)$:

$$
\boxed{\kappa(t)=\frac{\|T'(t)\|}{v(t)}}
$$
(Equation 14.20)

> Thus curvature is the **length** of the curvature vector.

### 14.10.3 Example 1 — Curvature of a Circle

- Circle of radius $a$: $\boldsymbol{r}(t)=a\cos t\,\boldsymbol{i}+a\sin t\,\boldsymbol{j}$.
- $v(t)=a$, $T(t)=-\sin t\,\boldsymbol{i}+\cos t\,\boldsymbol{j}$, $T'(t)=-\cos t\,\boldsymbol{i}-\sin t\,\boldsymbol{j}$.
- $\|T'(t)\|=1$, so:
  $$
  \kappa(t)=\frac{1}{a}.
  $$
- A circle has **constant curvature**; the reciprocal of curvature is the radius.

### 14.10.4 Radius of Curvature and Osculating Circle

- When $\kappa(t)\neq0$, its reciprocal $\rho(t)=1/\kappa(t)$ is the **radius of curvature**.
- The circle in the osculating plane with radius $\rho(t)$ and center at the tip of the curvature vector is the **osculating circle**.
- It is the limiting position of circles through three nearby points on the curve — the circle that "best fits the curve."

### 14.10.5 Example 2 — Curvature of a Plane Curve

- For a plane curve, $\|T'(t)\|=|\alpha'(t)|$, where $\alpha(t)$ is the angle the tangent makes with the positive $x$-axis.
- Since $\alpha'(t)=v(t)\,d\alpha/ds$:
  $$
  \kappa(t)=\left|\frac{d\alpha}{ds}\right|.
  $$
- **Curvature = absolute value of rate of change of direction per unit arc length.**

### 14.10.6 Example 3 — Plane Curves of Constant Curvature

- If $d\alpha/ds=a$ (nonzero constant), then $\alpha=as+b$.
- Integrating: the curve is a circle (or arc) with radius $1/|a|$.
- **A plane curve of constant nonzero curvature is a circle of radius $1/\kappa$.**

### 14.10.7 Theorem 14.14 — Acceleration in Terms of Curvature

For any motion with velocity $\boldsymbol{v}$, speed $v$, acceleration $\boldsymbol{a}$, and curvature $\kappa$:

$$
\boxed{\boldsymbol{a}(t)=v'(t)T(t)+\kappa(t)v^2(t)N(t)}
$$
(Equation 14.21)

This yields a practical formula for curvature:

$$
\boxed{\kappa(t)=\frac{\|\boldsymbol{a}(t)\times\boldsymbol{v}(t)\|}{v^3(t)}}
$$
(Equation 14.22)

**Proof sketch:**
1. From (14.20): $\|T'(t)\|=\kappa v$, so $T'=\kappa vN$.
2. Substitute into (14.8): $\boldsymbol{a}=v'T+vT'=v'T+\kappa v^2N$.
3. For (14.22): form $\boldsymbol{a}\times\boldsymbol{v}=(v'T+\kappa v^2N)\times(vT)=\kappa v^3(N\times T)$.
4. Since $\|N\times T\|=1$, taking lengths gives $\|\boldsymbol{a}\times\boldsymbol{v}\|=\kappa v^3$.

> **Practical note**: Computing $\boldsymbol{v}$ and $\boldsymbol{a}$ by differentiating $\boldsymbol{r}$ is usually easier than using the definition of curvature directly.

## 14.11 Velocity and Acceleration in Polar Coordinates

### 14.11.1 Polar Unit Vectors

- Position vector: $\boldsymbol{r}=x\,\boldsymbol{i}+y\,\boldsymbol{j}=r\cos\theta\,\boldsymbol{i}+r\sin\theta\,\boldsymbol{j}=r\boldsymbol{u}_r$.
- **Radial unit vector**:
  $$
  \boldsymbol{u}_r=\cos\theta\,\boldsymbol{i}+\sin\theta\,\boldsymbol{j}.
  $$
- **Transverse unit vector** (perpendicular to $\boldsymbol{u}_r$):
  $$
  \boldsymbol{u}_\theta=\frac{d\boldsymbol{u}_r}{d\theta}=-\sin\theta\,\boldsymbol{i}+\cos\theta\,\boldsymbol{j}.
  $$
- Key derivatives:
  $$
  \frac{d\boldsymbol{u}_\theta}{d\theta}=-\cos\theta\,\boldsymbol{i}-\sin\theta\,\boldsymbol{j}=-\boldsymbol{u}_r.
  $$

### 14.11.2 Velocity in Polar Coordinates

Let $r=f(t)$ and $\theta=g(t)$. Then $\boldsymbol{r}=r\boldsymbol{u}_r$ and:

$$
\boldsymbol{v}=\frac{d\boldsymbol{r}}{dt}=\frac{dr}{dt}\boldsymbol{u}_r+r\frac{d\boldsymbol{u}_r}{dt}.
$$

Using the chain rule:

$$
\frac{d\boldsymbol{u}_r}{dt}=\frac{d\theta}{dt}\frac{d\boldsymbol{u}_r}{d\theta}=\frac{d\theta}{dt}\boldsymbol{u}_\theta.
$$
(Equation 14.24)

Hence:

$$
\boxed{\boldsymbol{v}=\frac{dr}{dt}\boldsymbol{u}_r+r\frac{d\theta}{dt}\boldsymbol{u}_\theta}
$$
(Equation 14.25)

- $\dfrac{dr}{dt}$: **radial component** of velocity.
- $r\dfrac{d\theta}{dt}$: **transverse component** of velocity.

**Speed:**

$$
v=\sqrt{\left(\frac{dr}{dt}\right)^2+\left(r\frac{d\theta}{dt}\right)^2}.
$$

### 14.11.3 Acceleration in Polar Coordinates

Differentiating (14.25) and using $d\boldsymbol{u}_\theta/dt=-(d\theta/dt)\boldsymbol{u}_r$:

$$
\boxed{\boldsymbol{a}=\left(\frac{d^2r}{dt^2}-r\left(\frac{d\theta}{dt}\right)^2\right)\boldsymbol{u}_r+\left(r\frac{d^2\theta}{dt^2}+2\frac{dr}{dt}\frac{d\theta}{dt}\right)\boldsymbol{u}_\theta}
$$
(Equation 14.26)

- **Radial component**: $\dfrac{d^2r}{dt^2}-r\left(\dfrac{d\theta}{dt}\right)^2$.
- **Transverse component**: $r\dfrac{d^2\theta}{dt^2}+2\dfrac{dr}{dt}\dfrac{d\theta}{dt}$.

### 14.11.4 Special Case — Polar Equation $r=f(\theta)$

When $\theta=t$, the curve is given by $r=f(\theta)$. Formulas simplify to:

$$
\boldsymbol{v}=\frac{dr}{d\theta}\boldsymbol{u}_r+r\boldsymbol{u}_\theta,\qquad v=\sqrt{\left(\frac{dr}{d\theta}\right)^2+r^2},
$$

$$
\boldsymbol{a}=\left(\frac{d^2r}{d\theta^2}-r\right)\boldsymbol{u}_r+2\frac{dr}{d\theta}\boldsymbol{u}_\theta.
$$

## 14.12 Plane Motion with Radial Acceleration

### 14.12.1 Condition for Radial Acceleration

- The acceleration is **radial** when the transverse component in (14.26) is zero:
  $$
  r\frac{d^2\theta}{dt^2}+2\frac{dr}{dt}\frac{d\theta}{dt}=\frac{1}{r}\frac{d}{dt}\left(r^2\frac{d\theta}{dt}\right)=0.
  $$
- Hence acceleration is radial **iff** $r^2\dfrac{d\theta}{dt}$ is constant.

### 14.12.2 Area Swept by the Position Vector

- Let $A(t)$ be the area swept out by the position vector from $t=a$ to $t$.
- **Theorem**: The time rate of change of this area is:
  $$
  \boxed{A'(t)=\frac{1}{2}r^2\frac{d\theta}{dt}}
  $$
  (Equation 14.27)

**Proof:**
1. Eliminate $t$ to express $r=R(\theta)$.
2. By Theorem 2.6, the area is:
   $$
   A(t)=\frac{1}{2}\int_{g(a)}^{g(t)}R^2(\theta)\,d\theta.
   $$
3. Differentiate via the first FTC and chain rule:
   $$
   A'(t)=\frac{1}{2}R^2[g(t)]g'(t)=\frac{1}{2}f^2(t)g'(t)=\frac{1}{2}r^2\frac{d\theta}{dt}.
   $$

### 14.12.3 Kepler's Insight

- From (14.27): acceleration is radial **iff** $A'(t)$ is constant.
- **Equivalently**: the position vector sweeps out area at a **constant rate**.

## 14.13 Cylindrical Coordinates

### 14.13.1 Definition

- A point $P=(x,y,z)$ in 3-space is described by $(r,\theta,z)$, where $(r,\theta)$ are polar coordinates in the $xy$-plane.
- $r\ge0$ is the distance from the $z$-axis to $P$.
- Constant-$r$ surfaces are **circular cylinders**.

### 14.13.2 Position Vector

$$
\boldsymbol{r}=r\boldsymbol{u}_r+z(t)\boldsymbol{k}.
$$

### 14.13.3 Velocity and Acceleration

Add the $z$-component terms to the polar formulas (14.25) and (14.26):

$$
\boldsymbol{v}=\frac{dr}{dt}\boldsymbol{u}_r+r\frac{d\theta}{dt}\boldsymbol{u}_\theta+z'(t)\boldsymbol{k},
$$

$$
\boldsymbol{a}=\left(\frac{d^2r}{dt^2}-r\left(\frac{d\theta}{dt}\right)^2\right)\boldsymbol{u}_r+\left(r\frac{d^2\theta}{dt^2}+2\frac{dr}{dt}\frac{d\theta}{dt}\right)\boldsymbol{u}_\theta+z''(t)\boldsymbol{k}.
$$

## 14.14 Applications to Planetary Motion

### 14.14.1 Kepler's Three Laws

- **First law**: Planets move in **ellipses** with the sun at one focus.
- **Second law**: The position vector from the sun to a planet sweeps out area at a **constant rate**.
- **Third law**: The square of the period is proportional to the cube of the mean distance from the sun.
  > $T^2 \propto a^3$, where $a$ is the semi-major axis.

Newton later proved that all three laws follow from his second law of motion and the universal law of gravitation.

### 14.14.2 Newton's Law of Gravitation

Assume a fixed sun of mass $M$ and a planet of mass $m$.

- Newton's second law: $\boldsymbol{F}=m\boldsymbol{a}$. (Equation 14.28)
- Universal gravitation:
  $$
  \boldsymbol{F}=-G\frac{mM}{r^2}\boldsymbol{u}_r.
  $$
- Hence the acceleration is **radial**:
  $$
  \boxed{\boldsymbol{a}=-\frac{GM}{r^2}\boldsymbol{u}_r}
  $$
  (Equation 14.29)

### 14.14.3 Proof of Kepler's Second Law

1. Since $\boldsymbol{a}$ is parallel to $\boldsymbol{r}$, we have $\boldsymbol{r}\times\boldsymbol{a}=\boldsymbol{O}$.
2. Then:
   $$
   \boldsymbol{r}\times\boldsymbol{a}=\boldsymbol{r}\times\frac{d\boldsymbol{v}}{dt}=\frac{d}{dt}(\boldsymbol{r}\times\boldsymbol{v})=\boldsymbol{O}.
   $$
3. Thus $\boldsymbol{r}\times\boldsymbol{v}=\boldsymbol{c}$ (a constant vector).
4. If $\boldsymbol{c}\neq\boldsymbol{O}$, then $\boldsymbol{r}\cdot\boldsymbol{c}=0$, so the orbit lies in a plane.
5. In polar coordinates:
   $$
   \boldsymbol{c}=\boldsymbol{r}\times\boldsymbol{v}=r^2\frac{d\theta}{dt}\,\boldsymbol{u}_r\times\boldsymbol{u}_\theta.
   $$
   (Equation 14.30)
6. Hence $\|\boldsymbol{c}\|=|r^2 d\theta/dt|=2|A'(t)|$.
7. Therefore $A'(t)$ is constant — **Kepler's second law** is proved.

### 14.14.4 Proof of Kepler's First Law

1. Form $\boldsymbol{a}\times\boldsymbol{c}$ using (14.29) and (14.30):
   $$
   \boldsymbol{a}\times\boldsymbol{c}=GM\frac{d\theta}{dt}\boldsymbol{u}_\theta=\frac{d}{dt}(GM\boldsymbol{u}_r).
   $$
2. Since $\boldsymbol{a}=d\boldsymbol{v}/dt$ and $\boldsymbol{u}_\theta=d\boldsymbol{u}_r/d\theta$:
   $$
   \frac{d}{dt}(\boldsymbol{v}\times\boldsymbol{c})=\frac{d}{dt}(GM\boldsymbol{u}_r).
   $$
3. Integrating:
   $$
   \boldsymbol{v}\times\boldsymbol{c}=GM(\boldsymbol{u}_r+\boldsymbol{e}),
   $$
   where $\boldsymbol{e}$ is a constant vector. (Equation 14.31)
4. Dot with $\boldsymbol{r}$ and use (14.30):
   $$
   GMr(1+e\cos\phi)=c^2,
   $$
   where $e=\|\boldsymbol{e}\|$, $c=\|\boldsymbol{c}\|$, and $\phi$ is the angle between $\boldsymbol{e}$ and $\boldsymbol{r}$. (Equation 14.32)
5. Let $d=c^2/(GMe)$. Then:
   $$
   r=\frac{ed}{e\cos\phi+1}.
   $$
   (Equation 14.33)
6. This is the **polar equation of a conic section** with eccentricity $e$ and focus at the sun.
7. Since planetary orbits are closed, $e<1$, so the orbit is an **ellipse**.

### 14.14.5 Proof of Kepler's Third Law

- Ellipse area: $\pi ab$, where $2a$ and $2b$ are major and minor axes.
- Period $T$: time for one orbit. Since area is swept at rate $\frac{1}{2}c$:
  $$
  \frac{1}{2}cT=\pi ab \quad\Longrightarrow\quad T=\frac{2\pi ab}{c}.
  $$
- From Section 13.22: $b^2=a^2(1-e^2)$ and $ed=a(1-e^2)$.
- Hence $c^2=GMa(1-e^2)$, and:
  $$
  T^2=\frac{4\pi^2a^2b^2}{c^2}=\frac{4\pi^2a^4(1-e^2)}{GMa(1-e^2)}=\frac{4\pi^2}{GM}a^3.
  $$
- **Conclusion**:
  $$
  \boxed{T^2=\frac{4\pi^2}{GM}a^3}
  $$
  Thus $T^2$ is proportional to $a^3$.

[<- Previous: 13. Applications of Vector Algebra to Analytic Geometry](13-applications-of-vector-algebra-to-analytic-geometry.md) | [Next: 15. Linear Spaces ->](15-linear-spaces.md)
