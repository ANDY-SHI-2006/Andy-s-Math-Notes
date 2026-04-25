[<- Previous: 12. Vector Algebra](12-vector-algebra.md) | [Next: 14. Calculus of Vector-Valued Functions ->](14-calculus-of-vector-valued-functions.md)

# 13. Applications of Vector Algebra to Analytic Geometry

## 13.1 Introduction

This chapter applies vector algebra to the study of **lines, planes, and conic sections**. Chapter 14 will combine vector algebra with calculus for curves and mechanics.

### 13.1.1 Geometry as a Deductive System

- **Euclid (~300 B.C.):** Began with axioms describing points and lines; listed ten axioms from which all theorems were deduced.
- **Hilbert (1862–1943):** In *Grundlagen der Geometrie* (1899) gave a rigorous axiomatization with five undefined concepts—**point, line, on, between, congruence**—and fifteen axioms for plane geometry.

### 13.1.2 The Analytic Approach

Analytic geometry defines concepts such as point, line, and "on" in terms of **real numbers**, producing an **analytic model** of Euclidean geometry. Properties of real numbers are used to deduce Hilbert's axioms. This chapter indicates how primitive concepts may be defined numerically and gives proofs to illustrate the methods.

## 13.2 Lines in $n$-Space

### 13.2.1 Points and Vectors

A **point** is simply a vector in $V_n$ (an ordered $n$-tuple of real numbers). We use the words "point" and "vector" interchangeably. The space $V_n$ is called an **analytic model** of $n$-dimensional Euclidean space, or simply **Euclidean $n$-space**.

### 13.2.2 Definition of a Line

**Definition.** Let $P$ be a given point and $A$ a nonzero vector. The set of all points of the form $P+tA$, where $t$ runs through all real numbers, is called the **line through $P$ parallel to $A$**.

Notation:
$$
L(P;A)=\{P+tA\mid t\in\mathbb{R}\}.
$$

A point $Q$ is **on** the line $L(P;A)$ if $Q\in L(P;A)$.

- $P$ itself corresponds to $t=0$.
- $A$ is called a **direction vector** for the line.
- The line $L(O;A)$ through the origin is the linear span of $A$.
- The line $L(P;A)$ is obtained by translating the linear span of $A$ by the vector $P$.

> Geometrically, each point $P+tA$ can be visualized as the tip of a geometric vector drawn from the origin. As $t$ varies, the point traces out a straight line through $P$ parallel to $A$.

## 13.3 Some Simple Properties of Straight Lines

### 13.3.1 Equivalent Descriptions of a Line

**Theorem 13.1.** Two lines $L(P;A)$ and $L(P;B)$ through the same point $P$ are equal if and only if the direction vectors $A$ and $B$ are parallel.

**Theorem 13.2.** Two lines $L(P;A)$ and $L(Q;A)$ with the same direction vector $A$ are equal if and only if $Q$ lies on $L(P;A)$.

> Thus the direction vector may be replaced by any parallel vector, and the base point may be replaced by any other point on the line.

### 13.3.2 Parallel Lines

**Definition.** Two lines $L(P;A)$ and $L(Q;B)$ are **parallel** if their direction vectors $A$ and $B$ are parallel.

**Theorem 13.3 (Parallel Postulate).** Given a line $L$ and a point $Q$ not on $L$, there is one and only one line $L'$ containing $Q$ and parallel to $L$.

> Historical note: Gauss, Bolyai, and Lobatchevski showed that this postulate cannot be derived from Euclid's other axioms, leading to non-Euclidean geometries.

### 13.3.3 Two Points Determine a Line

**Theorem 13.4.** If $P\neq Q$, there is a unique line containing both $P$ and $Q$:
$$
L=\{P+t(Q-P)\mid t\in\mathbb{R}\}.
$$

**Test for incidence.** A point $Q$ lies on $L(P;A)$ if and only if $Q-P$ is a scalar multiple of $A$.

### 13.3.4 Linear Dependence and Collinearity

**Theorem 13.5.** Two vectors $A$ and $B$ in $V_n$ are linearly dependent if and only if they lie on the same line through the origin.

## 13.4 Lines and Vector-Valued Functions

### 13.4.1 Parametric Vector Equation

A line can be described by a **vector-valued function**
$$
X(t)=P+tA, \qquad t\in\mathbb{R}.
$$
The scalar $t$ is called a **parameter**; $t$ may be interpreted as **time** and $X(t)$ as the **position vector** of a moving particle.

Through two distinct points $P$ and $Q$:
$$
X(t)=P+t(Q-P) \qquad\text{or}\qquad X(t)=tQ+(1-t)P.
$$

### 13.4.2 Scalar Parametric Equations

In components, with $P=(p,q,r)$ and $A=(a,b,c)$:
$$
x=p+ta, \qquad y=q+tb, \qquad z=r+tc.
$$
These are the **scalar parametric equations** of the line.

### 13.4.3 Cartesian Equation in the Plane

In $V_2$, eliminating $t$ gives
$$
b(x-p)-a(y-q)=0.
$$
If $a\neq0$ this becomes the **point-slope form**
$$
y-q=\frac{b}{a}(x-p).
$$

### 13.4.4 Normal Form

Let $N=(b,-a)$. Then $N\cdot A=0$, so $N$ is a **normal vector** to the line. The Cartesian equation can be written as
$$
(X-P)\cdot N=0 \qquad\text{or}\qquad X\cdot N=P\cdot N.
$$

### 13.4.5 Distance from the Origin to a Line

**Theorem 13.6.** Let $L$ be the line in $V_2$ given by $X\cdot N=P\cdot N$, where $N$ is a nonzero normal vector. Set
$$
d=\frac{|P\cdot N|}{\|N\|}.
$$
Then every point $X$ on $L$ satisfies $\|X\|\ge d$, and $\|X\|=d$ if and only if $X$ is the projection of $P$ along $N$:
$$
X=tN, \qquad t=\frac{P\cdot N}{N\cdot N}.
$$

**Proof sketch.** Since $X\cdot N=P\cdot N$, Cauchy–Schwarz gives $|P\cdot N|=|X\cdot N|\le\|X\|\,\|N\|$, whence $\|X\|\ge d$. Equality holds iff $X$ is parallel to $N$.

### 13.4.6 Distance from a Point to a Line

If $Q$ is a point not on $L$, the **distance** from $Q$ to $L$ is
$$
\frac{|(P-Q)\cdot N|}{\|N\|}.
$$
This is the length of the projection of $P-Q$ along the normal vector $N$.

## 13.5 Planes in Euclidean $n$-Space

### 13.5.1 Definition

A **plane** in $V_n$ ($n\ge 2$) is a set of the form
$$
M=\{P+sA+tB\mid s,t\in\mathbb{R}\},
$$
where $P$ is a point and $A,B$ are **linearly independent** vectors. The vectors $A$ and $B$ are called **direction vectors** of the plane; $M$ is the plane through $P$ spanned by $A$ and $B$.

When $P=O$, the plane is simply the linear span of $A$ and $B$.

### 13.5.2 Equivalent Descriptions

**Theorem 13.7.** Two planes $M=\{P+sA+tB\}$ and $M'=\{P+sC+tD\}$ through the same point $P$ are equal if and only if $L(A,B)=L(C,D)$ (i.e. $\{A,B\}$ and $\{C,D\}$ span the same subspace).

**Theorem 13.8.** Two planes $M=\{P+sA+tB\}$ and $M'=\{Q+sA+tB\}$ spanned by the same vectors are equal if and only if $Q$ lies on $M$.

### 13.5.3 Parallel Planes

**Definition.** Two planes are **parallel** if their direction vectors span the same subspace. A vector $X$ is **parallel to** the plane $M$ if $X\in L(A,B)$.

**Theorem 13.9 (Parallel Postulate for Planes).** Given a plane $M$ and a point $Q$ not on $M$, there is one and only one plane $M'$ containing $Q$ and parallel to $M$.

### 13.5.4 Three Points Determine a Plane

**Theorem 13.10.** If $P,Q,R$ are three points not on the same line, there is a unique plane $M$ containing them:
$$
M=\{P+s(Q-P)+t(R-P)\mid s,t\in\mathbb{R}\}.
$$

**Proof sketch.** First assume $P=O$. Then $Q$ and $R$ are linearly independent and span a plane $M'$. Any other plane $M''$ through $O$ containing $Q$ and $R$ must have direction vectors $A,B$ with $Q=aA+bB$ and $R=cA+dB$. Since $ad-bc\neq0$ (otherwise $Q,R$ would be dependent), we can solve for $A$ and $B$ as linear combinations of $Q$ and $R$, so $M''\subseteq M'$ and $M'\subseteq M''$. The general case follows by translating.

### 13.5.5 Linear Dependence and Coplanarity

**Theorem 13.11.** Three vectors $A,B,C$ in $V_n$ are linearly dependent if and only if they lie on the same plane through the origin.

**Proof sketch.** If $A,B,C$ are dependent, one is a linear combination of the other two, say $C=sA+tB$. If $A,B$ are independent they span a plane containing $C$; if dependent all three lie on a line through $O$, hence on any plane through $O$ containing them. Conversely, if $A,B,C$ lie on a plane through $O$ and $A,B$ are independent, that plane is unique (Theorem 13.10), so $C=sA+tB$ and the vectors are dependent.

## 13.6 Planes and Vector-Valued Functions

### 13.6.1 Parametric Vector Equation

A plane can be described by a **vector-valued function of two variables**:
$$
X(s,t)=P+sA+tB, \qquad s,t\in\mathbb{R}.
$$
The scalars $s$ and $t$ are **parameters**; the presence of two parameters gives the plane its two-dimensional quality.

### 13.6.2 Scalar Parametric Equations

In $V_3$, with $P=(p_1,p_2,p_3)$, $A=(a_1,a_2,a_3)$, $B=(b_1,b_2,b_3)$, and $X(s,t)=(x,y,z)$:
$$
x=p_1+sa_1+tb_1, \qquad y=p_2+sa_2+tb_2, \qquad z=p_3+sa_3+tb_3.
$$
These are the **scalar parametric equations** of the plane.

### 13.6.3 Cartesian Equation

The parameters $s$ and $t$ can always be eliminated from the three scalar equations to obtain a single linear equation of the form
$$
ax+by+cz=d,
$$
called a **Cartesian equation** of the plane.

**Example.** Let $P=(1,2,3)$, $A=(1,2,1)$, $B=(1,-4,-1)$. The parametric equations are
$$
x=1+s+t, \qquad y=2+2s-4t, \qquad z=3+s-t.
$$
From the first and third equations, $x-1=s+t$ and $z-3=s-t$. Adding and subtracting give $2s=x+z-4$ and $2t=x-z+2$. Substituting into the equation for $y$ yields the Cartesian equation
$$
x+y-3z=-6.
$$

> A systematic study of linear Cartesian equations is given in Section 13.16.

## 13.7 The Cross Product

### 13.7.1 Definition

For vectors $A=(a_1,a_2,a_3)$ and $B=(b_1,b_2,b_3)$ in $V_3$, the **cross product** is
$$
A\times B=(a_2b_3-a_3b_2,\; a_3b_1-a_1b_3,\; a_1b_2-a_2b_1).
$$

### 13.7.2 Algebraic Properties

**Theorem 13.12.** For all vectors $A,B,C$ in $V_3$ and all scalars $c$:
- **(a)** $A\times B=-(B\times A)$ (skew symmetry)
- **(b)** $A\times(B+C)=(A\times B)+(A\times C)$ (distributive law)
- **(c)** $c(A\times B)=(cA)\times B$ (homogeneity)
- **(d)** $A\cdot(A\times B)=0$ (orthogonality to $A$)
- **(e)** $B\cdot(A\times B)=0$ (orthogonality to $B$)
- **(f)** $\|A\times B\|^2=\|A\|^2\|B\|^2-(A\cdot B)^2$ (Lagrange's identity)
- **(g)** $A\times B=O$ iff $A$ and $B$ are linearly dependent

> Note: The cross product is **not associative**. For example, $i\times(i\times j)=-j$ but $(i\times i)\times j=O$.

### 13.7.3 Fundamental Geometric Properties

**Theorem 13.13.** Let $A$ and $B$ be linearly independent vectors in $V_3$.
- **(a)** $A$, $B$, $A\times B$ are linearly independent.
- **(b)** Every vector $N$ in $V_3$ orthogonal to both $A$ and $B$ is a scalar multiple of $A\times B$.

### 13.7.4 Geometric Interpretation

**Direction.** The vector $A\times B$ is perpendicular to both $A$ and $B$. In a **right-handed** coordinate system its direction is determined by the **right-hand rule**: when $A$ is rotated into $B$, the thumb points in the direction of $A\times B$.

**Magnitude.** Using $A\cdot B=\|A\|\,\|B\|\cos\theta$ in Lagrange's identity:
$$
\|A\times B\|^2=\|A\|^2\|B\|^2(1-\cos^2\theta)=\|A\|^2\|B\|^2\sin^2\theta.
$$
Hence
$$
\boxed{\|A\times B\|=\|A\|\,\|B\|\sin\theta}.
$$
Since $\|B\|\sin\theta$ is the altitude of the parallelogram determined by $A$ and $B$, the length of $A\times B$ equals the **area** of that parallelogram.

### 13.7.5 Standard Basis Relations

$$
i\times j=k, \qquad j\times k=i, \qquad k\times i=j.
$$

> The cross product is defined only in $V_3$ and produces a vector, not a scalar.

## 13.8 The Cross Product Expressed as a Determinant

### 13.8.1 Determinants of Order Two

The **determinant** of order two is defined by
$$
\begin{vmatrix} a & b \\ c & d \end{vmatrix}=ad-bc.
$$
Interchanging two rows or two columns changes the sign:
$$
\begin{vmatrix} a & b \\ c & d \end{vmatrix}=-\begin{vmatrix} b & a \\ d & c \end{vmatrix}.
$$

### 13.8.2 Cross Product via 2x2 Determinants

Each component of $A\times B$ can be written as a second-order determinant:
$$
A\times B=\Bigl(\begin{vmatrix} a_2 & a_3 \\ b_2 & b_3 \end{vmatrix},\; \begin{vmatrix} a_3 & a_1 \\ b_3 & b_1 \end{vmatrix},\; \begin{vmatrix} a_1 & a_2 \\ b_1 & b_2 \end{vmatrix}\Bigr).
$$
In terms of the unit coordinate vectors:
$$
A\times B=\begin{vmatrix} a_2 & a_3 \\ b_2 & b_3 \end{vmatrix}i+\begin{vmatrix} a_3 & a_1 \\ b_3 & b_1 \end{vmatrix}j+\begin{vmatrix} a_1 & a_2 \\ b_1 & b_2 \end{vmatrix}k.
$$

### 13.8.3 Determinants of Order Three

A third-order determinant is expanded along its first row:
$$
\begin{vmatrix} a_1 & a_2 & a_3 \\ b_1 & b_2 & b_3 \\ c_1 & c_2 & c_3 \end{vmatrix}
=a_1\begin{vmatrix} b_2 & b_3 \\ c_2 & c_3 \end{vmatrix}
-a_2\begin{vmatrix} b_1 & b_3 \\ c_1 & c_3 \end{vmatrix}
+a_3\begin{vmatrix} b_1 & b_2 \\ c_1 & c_2 \end{vmatrix}.
$$

### 13.8.4 Compact Determinant Form of the Cross Product

When the first row consists of vectors, the determinant is meaningful and yields the cross product in compact form:
$$
\boxed{A\times B=\begin{vmatrix} i & j & k \\ a_1 & a_2 & a_3 \\ b_1 & b_2 & b_3 \end{vmatrix}}
$$

**Example.** For $A=2i-8j+3k$ and $B=4j+3k$:
$$
A\times B=\begin{vmatrix} i & j & k \\ 2 & -8 & 3 \\ 0 & 4 & 3 \end{vmatrix}
=\begin{vmatrix} -8 & 3 \\ 4 & 3 \end{vmatrix}i
-\begin{vmatrix} 2 & 3 \\ 0 & 3 \end{vmatrix}j
+\begin{vmatrix} 2 & -8 \\ 0 & 4 \end{vmatrix}k
=-36i-6j+8k.
$$

## 13.9 The Scalar Triple Product

### 13.9.1 Definition and Determinant Form

The **scalar triple product** $A\cdot B\times C$ means $A\cdot(B\times C)$. It is a scalar, and can be computed as a single third-order determinant:
$$
A\cdot B\times C=\begin{vmatrix} a_1 & a_2 & a_3 \\ b_1 & b_2 & b_3 \\ c_1 & c_2 & c_3 \end{vmatrix}.
$$

### 13.9.2 Criterion for Linear Dependence

**Theorem 13.14.** Three vectors $A,B,C$ in $V_3$ are linearly dependent if and only if
$$
A\cdot B\times C=0.
$$

**Proof sketch.** If $A,B,C$ are dependent, one is a linear combination of the other two; taking the dot product with their cross product yields $0$. Conversely, if $A\cdot(B\times C)=0$ and $B,C$ are independent, write $A=aB+bC+c(B\times C)$. Dotting with $B\times C$ gives $c=0$, so $A$ lies in the span of $B$ and $C$.

**Example.** For $(2,3,-1)$, $(3,-7,5)$, $(1,-5,2)$:
$$
\begin{vmatrix} 2 & 3 & -1 \\ 3 & -7 & 5 \\ 1 & -5 & 2 \end{vmatrix}=27\neq0,
$$
so the vectors are independent.

### 13.9.3 Geometric Interpretation

The absolute value $|A\cdot B\times C|$ equals the **volume** of the parallelepiped determined by $A,B,C$.

- Base area $=\|A\times B\|$
- Altitude $=\|C\|\cos\phi$ (where $\phi$ is the angle between $A\times B$ and $C$)
- Volume $=\|A\times B\|\,\|C\|\cos\phi=(A\times B)\cdot C$

If $A,B,C$ are coplanar, the parallelepiped degenerates and the scalar triple product is zero.

### 13.9.4 Algebraic Properties

**Cyclic symmetry:**
$$
A\times B\cdot C=B\times C\cdot A=C\times A\cdot B.
$$

**Interchangeability of dot and cross:**
$$
A\times B\cdot C=A\cdot B\times C.
$$

Because of this, the scalar triple product is often denoted by the symbol $[ABC]$ without indicating the dot or cross.

## 13.10 Cramer's Rule for Three Linear Equations

### 13.10.1 Vector Formulation

Consider the system
$$
\begin{aligned}
a_1x+b_1y+c_1z&=d_1,\\
a_2x+b_2y+c_2z&=d_2,\\
a_3x+b_3y+c_3z&=d_3.
\end{aligned}
$$
Let $A=(a_1,a_2,a_3)$, $B=(b_1,b_2,b_3)$, $C=(c_1,c_2,c_3)$, $D=(d_1,d_2,d_3)$. The system becomes the single vector equation
$$
xA+yB+zC=D.
$$

### 13.10.2 Derivation

Dot both sides with $B\times C$:
$$
x[A\,B\,C]+y[B\,B\,C]+z[C\,B\,C]=[D\,B\,C].
$$
Since $[B\,B\,C]=[C\,B\,C]=0$, the coefficients of $y$ and $z$ drop out:
$$
x=\frac{[D\,B\,C]}{[A\,B\,C]} \qquad\text{provided }[A\,B\,C]\neq0.
$$
Similar arguments give
$$
y=\frac{[A\,D\,C]}{[A\,B\,C]}, \qquad z=\frac{[A\,B\,D]}{[A\,B\,C]}.
$$

### 13.10.3 Cramer's Rule in Determinant Form

Writing the scalar triple products as determinants yields **Cramer's rule**:
$$
\boxed{x=\frac{\begin{vmatrix}d_1&b_1&c_1\\d_2&b_2&c_2\\d_3&b_3&c_3\end{vmatrix}}{\Delta},\quad
y=\frac{\begin{vmatrix}a_1&d_1&c_1\\a_2&d_2&c_2\\a_3&d_3&c_3\end{vmatrix}}{\Delta},\quad
z=\frac{\begin{vmatrix}a_1&b_1&d_1\\a_2&b_2&d_2\\a_3&b_3&d_3\end{vmatrix}}{\Delta}}
$$
where $\displaystyle\Delta=\begin{vmatrix}a_1&b_1&c_1\\a_2&b_2&c_2\\a_3&b_3&c_3\end{vmatrix}=[A\,B\,C]$.

### 13.10.4 Existence and Uniqueness

- If $[A\,B\,C]\neq0$, the vectors $A,B,C$ are linearly independent and form a basis for $V_3$. Every vector $D$ is then spanned uniquely, so the system has a **unique solution**.
- If $[A\,B\,C]=0$, the vectors $A,B,C$ lie on a plane through the origin. The system has **no solution** unless $D$ lies in the same plane, in which case there are **infinitely many solutions**.

## 13.11 Normal Vectors to Planes

### 13.11.1 Definition

Let $M=\{P+sA+tB\}$ be a plane through $P$ spanned by $A$ and $B$. A vector $N$ in $V_3$ is **perpendicular to $M$** if $N$ is perpendicular to both $A$ and $B$. If, in addition, $N\neq O$, then $N$ is called a **normal vector** to the plane.

> If $N\cdot A=N\cdot B=0$, then $N\cdot(sA+tB)=0$ for all $s,t$, so $N$ is orthogonal to every vector in the linear span of $A$ and $B$. Also, if $N$ is normal to $M$, so is $tN$ for every $t\neq0$.

### 13.11.2 Normal Form of a Plane

**Theorem 13.15.** Let $M=\{P+sA+tB\}$ and let $N=A\times B$. Then:
- **(a)** $N$ is a normal vector to $M$.
- **(b)** $M$ is the set of all $X$ in $V_3$ satisfying
  $$
  (X-P)\cdot N=0.
  $$

**Proof sketch.** (a) follows since $A\times B$ is orthogonal to both $A$ and $B$ and $A\times B\neq O$ (because $A,B$ are independent). For (b), if $X\in M$ then $X-P$ lies in $L(A,B)$, hence is orthogonal to $N$, so $X$ satisfies the equation. Conversely, if $X$ satisfies the equation, write $X-P=sA+tB+uN$ (possible since $A,B,N$ are independent by Theorem 13.13). Dotting with $N$ gives $u=0$, so $X-P=sA+tB$ and $X\in M$.

### 13.11.3 Distance from the Origin

**Theorem 13.16.** Let $M$ be a plane through $P$ with nonzero normal vector $N$, and let
$$
d=\frac{|P\cdot N|}{\|N\|}.
$$
Then every $X$ on $M$ satisfies $\|X\|\ge d$, and $\|X\|=d$ if and only if $X$ is the projection of $P$ along $N$:
$$
X=tN, \qquad t=\frac{P\cdot N}{N\cdot N}.
$$

**Proof.** Since $X\cdot N=P\cdot N$ for $X\in M$, the Cauchy–Schwarz inequality gives $|P\cdot N|=|X\cdot N|\le\|X\|\,\|N\|$, whence $\|X\|\ge d$. Equality holds iff $X$ is parallel to $N$.

### 13.11.4 Distance from a Point to a Plane

If $Q$ is a point not on $M$, the **distance** from $Q$ to $M$ is
$$
\frac{|(P-Q)\cdot N|}{\|N\|}.
$$
This is the length of the projection of $P-Q$ onto the normal direction. The number $d$ above is the distance from the **origin** to the plane.

## 13.12 Linear Cartesian Equations for Planes

### 13.12.1 The General Form

Writing $N=(a,b,c)$, $P=(x_1,y_1,z_1)$, and $X=(x,y,z)$, the normal equation $(X-P)\cdot N=0$ becomes
$$
a(x-x_1)+b(y-y_1)+c(z-z_1)=0.
$$
Transposing gives the standard **linear Cartesian equation**
$$
\boxed{ax+by+cz=d_1}, \qquad d_1=ax_1+by_1+cz_1=P\cdot N.
$$
Conversely, every linear equation with $a,b,c$ not all zero represents a plane with normal vector $N=(a,b,c)$.

### 13.12.2 Distance from the Origin

Since $d_1=P\cdot N$,
$$
|d_1|=|P\cdot N|=d\,\|N\|,
\qquad\text{so}\qquad
\boxed{d=\frac{|d_1|}{\|N\|}}.
$$
In particular $|d_1|=d$ when the normal has length $1$. The plane passes through the origin iff $d_1=0$.

### 13.12.3 Intercepts

Rewriting $ax+by+cz=d_1$ as
$$
\frac{x}{d_1/a}+\frac{y}{d_1/b}+\frac{z}{d_1/c}=1
$$
(when $a,b,c\neq0$) shows the $x$-, $y$-, and $z$-**intercepts**.

**Example.** $2x+6y+3z=6$ has normal $N=(2,6,3)$ and intercept form
$$
\frac{x}{3}+\frac{y}{1}+\frac{z}{2}=1,
$$
so the plane meets the axes at $(3,0,0)$, $(0,1,0)$, $(0,0,2)$. Its distance from the origin is $d=6/\|N\|=6/7$.

### 13.12.4 Parallel and Perpendicular Planes

- **Parallel planes** share a common normal. Their equations are
  $$
  ax+by+cz=d_1, \qquad ax+by+cz=d_2.
  $$
  The **perpendicular distance** between them is $\displaystyle\frac{|d_1-d_2|}{\|N\|}$.

- **Perpendicular planes:** two planes are perpendicular if a normal of one is perpendicular to a normal of the other.

- **Angle between planes:** the angle $\theta$ between their normal vectors.

## 13.13 The Conic Sections

### 13.13.1 Definition as Sections of a Cone

A moving line $G$ intersecting a fixed line $A$ at a point $P$, making a constant angle $\theta$ ($0<\theta<\pi/2$), generates a **right circular cone** in 3-space.
- $G$ = generator, $A$ = axis, $P$ = vertex.
- The upper and lower portions are called **nappes**.

**Conic sections** (or **conics**) are curves obtained by slicing the cone with a plane not passing through the vertex:
- **Parabola:** the cutting plane is parallel to a line of the cone through the vertex.
- **Ellipse:** the plane cuts just one nappe.
- **Hyperbola:** the plane cuts both nappes (two branches).

### 13.13.2 Historical Importance

- **Apollonius** (3rd century B.C.): systematic treatment of conics.
- **Galileo:** projectiles follow parabolic paths (neglecting air resistance).
- **Kepler (~1600):** planetary orbits are elliptical.
- **Newton (~1680):** an elliptical orbit implies an inverse-square law of gravitation.
- Conics also describe trajectories of atomic particles, and are used in the design of lenses, mirrors, and architecture.

### 13.13.3 Focal Definitions

| Conic | Definition |
|---|---|
| **Ellipse** | Set of points with $d_1+d_2=\text{constant}$, where $d_1,d_2$ are distances to two fixed **foci** $F_1,F_2$. |
| **Circle** | Special case of an ellipse in which the two foci coincide. |
| **Hyperbola** | Set of points with $\|d_1-d_2\|=\text{constant}$. |
| **Parabola** | Set of points equidistant from a fixed point $F$ (focus) and a fixed line (directrix). |

### 13.13.4 The Dandelin Sphere Proof

**Theorem (Dandelin, 1822).** The focal property of an ellipse follows from its definition as a section of a cone.

**Proof sketch.** Draw two spheres $S_1$ and $S_2$ tangent to the cutting plane and to the cone. Let $F_1,F_2$ be their points of tangency with the plane, and let $C_1,C_2$ be the circles of tangency with the cone.

For any point $P$ on the ellipse, the generator through $P$ meets $C_1$ and $C_2$ at $A_1$ and $A_2$. Since $PF_1$ and $PA_1$ are two tangents from $P$ to $S_1$, they have equal length; similarly $|PF_2|=|PA_2|$. Hence
$$
|PF_1|+|PF_2|=|PA_1|+|PA_2|=|A_1A_2|,
$$
which is the constant distance between the parallel circles $C_1$ and $C_2$ measured along the cone. Thus $F_1$ and $F_2$ are foci of the ellipse.

> Modifications of this argument work for the hyperbola (one sphere in each nappe) and the parabola (one sphere tangent to the cutting plane at the focus).

## 13.14 Eccentricity of Conic Sections

### 13.14.1 Unified Definition

A **conic section** can be defined as the locus of a point $X$ moving in a plane so that the ratio of its distance from a fixed point $F$ (the **focus**) to its distance from a fixed line $L$ (the **directrix**) is a constant $e$ (the **eccentricity**):
$$
\frac{\|X-F\|}{d(X,L)}=e.
$$

| Eccentricity | Conic |
|---|---|
| $0<e<1$ | **Ellipse** |
| $e=1$ | **Parabola** |
| $e>1$ | **Hyperbola** |

> The number $e$ here is the eccentricity, not to be confused with Euler's number.

### 13.14.2 Distance to a Line

If $N$ is a normal vector to $L$ and $P$ is any point on $L$, the distance from $X$ to $L$ is
$$
d(X,L)=\frac{|(X-P)\cdot N|}{\|N\|}.
$$
When $\|N\|=1$ this simplifies to $d(X,L)=|(X-P)\cdot N|$, and the defining equation becomes
$$
\|X-F\|=e\,|(X-P)\cdot N|.
$$

### 13.14.3 Standard Vector Equation

Place the focus $F$ in the negative half-plane determined by $L$, and let $P$ be the point of $L$ nearest to $F$. Then $P-F=dN$ where $d=\|P-F\|>0$ is the distance from focus to directrix. Replacing $P$ by $F+dN$ yields:

**Theorem 13.17.** Let $C$ be a conic with eccentricity $e$, focus $F$, and directrix $L$ at distance $d$ from $F$. If $N$ is a unit normal to $L$ and $F$ lies in the negative half-plane, then $C$ consists of all points $X$ satisfying
$$
\boxed{\|X-F\|=e\,|(X-F)\cdot N-d|}.
$$

## 13.15 Polar Equations for Conic Sections

### 13.15.1 Focus at the Origin

When the focus is placed at the origin, Theorem 13.17 simplifies to
$$
\|X\|=e\,|X\cdot N-d|.
$$
Take the directrix $L$ to be vertical with unit normal $N=i$. In polar coordinates $(r,\theta)$:
$$
\|X\|=r, \qquad X\cdot N=r\cos\theta.
$$
Hence the basic equation becomes
$$
r=e\,|r\cos\theta-d|.
$$

### 13.15.2 Deriving the Polar Form

**Case 1 — $X$ lies to the left of $L$** ($r\cos\theta<d$). Then $|r\cos\theta-d|=d-r\cos\theta$, so
$$
r=e(d-r\cos\theta) \quad\Longrightarrow\quad \boxed{r=\frac{ed}{e\cos\theta+1}}.
$$

**Case 2 — $X$ lies to the right of $L$** ($r\cos\theta>d$). Then $|r\cos\theta-d|=r\cos\theta-d$, so
$$
r=e(r\cos\theta-d) \quad\Longrightarrow\quad \boxed{r=\frac{ed}{e\cos\theta-1}}.
$$
Since $r>0$, the second case requires $e>1$; thus points to the right of $L$ occur only for the **hyperbola**.

### 13.15.3 Summary Theorem

**Theorem 13.18.** Let $C$ be a conic with eccentricity $e$, focus at the origin, and vertical directrix $L$ at distance $d$ to the right of the focus.
- If $0<e\le 1$ (ellipse or parabola), every point of $C$ lies to the left of $L$ and satisfies
  $$
  r=\frac{ed}{e\cos\theta+1}.
  $$
- If $e>1$ (hyperbola), there is a branch on each side of $L$. Points on the **left** branch satisfy the equation above; points on the **right** branch satisfy
  $$
  r=\frac{ed}{e\cos\theta-1}.
  $$

> Polar equations for other positions of the directrix are obtained by rotating the coordinate system.

## 13.16 Conic Sections Symmetric About the Origin

### 13.16.1 Achieving Symmetry

A set is **symmetric about the origin** if $-X$ belongs to the set whenever $X$ does. For a conic with eccentricity $e\neq1$, the focus and directrix can always be placed so that the curve is symmetric about the origin.

Starting from $\|X-F\|=e\,|(X-F)\cdot N-d|$ and setting $a=ed+eF\cdot N$, the basic equation becomes
$$
\|X-F\|=|eX\cdot N-a|.
$$
Squaring and requiring the equation to hold for both $X$ and $-X$ forces
$$
(F-eaN)\cdot X=0 \quad\text{for all }X\text{ on the curve},
$$
which is satisfied if and only if $F=eaN$. Solving $a=ed+e^2a$ gives
$$
\boxed{a=\frac{ed}{1-e^2}}, \qquad \boxed{F=\frac{e^2d}{1-e^2}\,N}.
$$
Note that $a>0$ when $e<1$ and $a<0$ when $e>1$.

> For a **parabola** ($e=1$) this relation cannot be satisfied (since $d\neq0$); a parabola has no symmetry about the origin.

### 13.16.2 The Symmetric Equation

**Theorem 13.19.** Let $C$ be a conic with eccentricity $e\neq1$ and focus at distance $d$ from directrix $L$. If $N$ is a unit normal to $L$ and $F=eaN$ with $a$ as above, then $C$ is the set of all $X$ satisfying
$$
\boxed{\|X\|^2+e^2a^2=e^2(X\cdot N)^2+a^2}.
$$
This equation is unchanged when $X$ is replaced by $-X$, confirming symmetry.

### 13.16.3 Axes and Vertices

Because of this symmetry, the ellipse and hyperbola each have **two foci** and **two directrices**, symmetrically located about the center.

- **Vertices:** the points $X=\pm aN$. The segment joining them is the **major axis** (ellipse) or **transverse axis** (hyperbola).
- **Minor axis:** let $N'$ be a unit vector orthogonal to $N$. Setting $X=bN'$ gives $b^2=a^2(1-e^2)$, so
  $$
  b=a\sqrt{1-e^2} \qquad (e<1).
  $$
  The segment joining $\pm bN'$ is the **minor axis** of the ellipse.

### 13.16.4 The Circle as a Limiting Case

If $e=0$, Equation (13.34) reduces to $\|X\|=a$, the equation of a circle of radius $a$. This can be viewed as a limiting case of an ellipse in which $e\to0$ and $d\to\infty$ with $ed\to a$.

## 13.17 Cartesian Equations for the Conic Sections

### 13.17.1 Ellipse and Hyperbola (Standard Form)

With $N=i$ and $X=(x,y)$, the symmetric equation (13.34) becomes
$$
x^2(1-e^2)+y^2=a^2(1-e^2),
\qquad\text{i.e.}\qquad
\boxed{\frac{x^2}{a^2}+\frac{y^2}{a^2(1-e^2)}=1}.
$$
This represents both the **ellipse** ($e<1$) and the **hyperbola** ($e>1$).

- **Foci:** $(\pm ae,0)$; **directrices:** $x=\pm a/e$.

**Ellipse** ($e<1$). Let $b=a\sqrt{1-e^2}$. Then
$$
\boxed{\frac{x^2}{a^2}+\frac{y^2}{b^2}=1}, \qquad c=ae=\sqrt{a^2-b^2}.
$$

**Hyperbola** ($e>1$). Let $b=|a|\sqrt{e^2-1}$. Then
$$
\boxed{\frac{x^2}{a^2}-\frac{y^2}{b^2}=1}, \qquad c=|a|\,e=\sqrt{a^2+b^2}.
$$
Solving for $y$ gives $y=\pm\frac{b}{|a|}\sqrt{x^2-a^2}$. For large $x$,
$$
y_1-y_2=\frac{b}{|a|}(x-\sqrt{x^2-a^2})=\frac{|a|b}{x+\sqrt{x^2-a^2}}\to0,
$$
so the lines $y=\pm\frac{b}{|a|}x$ are **asymptotes**.

### 13.17.2 Other Orientations and Translations

If the directrices are horizontal ($N=j$), interchange $x$ and $y$:
$$
\frac{y^2}{a^2}+\frac{x^2}{a^2(1-e^2)}=1.
$$
A translation by $X_0=(x_0,y_0)$ moves the center to $(x_0,y_0)$; replace $x$ by $x-x_0$ and $y$ by $y-y_0$.

### 13.17.3 Parabola

For $e=1$, take directrix $x=-c$ and focus $(c,0)$. Equation (13.20) gives
$$
(x-c)^2+y^2=|x+c|^2 \quad\Longrightarrow\quad \boxed{y^2=4cx}.
$$
- **Vertex:** origin (midpoint of focus and directrix).
- **Axis:** the $x$-axis.
- Opens right if $c>0$, left if $c<0$.

If the focus is on the $y$-axis at $(0,c)$ with directrix $y=-c$:
$$
\boxed{x^2=4cy}.
$$

**Translated parabolas:**
$$
(y-y_0)^2=4c(x-x_0) \quad\text{or}\quad (x-x_0)^2=4c(y-y_0).
$$
The first has focus $(x_0+c,y_0)$, directrix $x=x_0-c$, axis $y=y_0$.

> A parabola has **no asymptotes**.

[<- Previous: 12. Vector Algebra](12-vector-algebra.md) | [Next: 14. Calculus of Vector-Valued Functions ->](14-calculus-of-vector-valued-functions.md)
