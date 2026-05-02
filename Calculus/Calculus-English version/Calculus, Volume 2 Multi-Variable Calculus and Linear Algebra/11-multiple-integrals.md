# Chapter 11 — Multiple Integrals

### 11.1 Introduction

Volume I discussed integrals $\int_a^{b}f(x)\,dx$; Chapter 10 generalized this to line integrals. This chapter extends the concept in yet another direction: the one-dimensional interval $[a,b]$ is replaced by a two-dimensional set $Q$, called the **region of integration**.

- First: rectangular regions.
- Later: more general regions with curvilinear boundaries.

The integrand is a scalar field $f$ defined and bounded on $Q$. The resulting integral is called a **double integral**, denoted
$$
\iint_Q f \qquad\text{or}\qquad \iint_Q f(x,y)\,dx\,dy.
$$
As in the 1D case, the symbols $dx$ and $dy$ play no role in the definition, but they are useful in computations and transformations.

**Program of the chapter:**
1. Definition of the double integral (analogous to the 1D case; first for step functions, then for general functions).
2. Computation by **repeated one-dimensional integration**.
3. Connection between double integrals and line integrals.
4. Applications to area, volume, mass, center of mass, etc.
5. Extension to $n$-space.


### 11.2 Partitions of Rectangles. Step Functions

A **rectangle** $Q$ is the Cartesian product of two closed intervals:
$$
Q=[a,b]\times[c,d]=\{(x,y):x\in[a,b],\;y\in[c,d]\}.
$$

**Partition of $Q$.** Let $P_1=\{x_0,\dots,x_n\}$ be a partition of $[a,b]$ and $P_2=\{y_0,\dots,y_m\}$ a partition of $[c,d]$. The Cartesian product $P=P_1\times P_2$ is a **partition of $Q$**, decomposing $Q$ into $mn$ subrectangles. A partition $P'$ is **finer** than $P$ if $P\subseteq P'$.

The Cartesian product of two open subintervals is an **open subrectangle** (edges missing).

**Definition (Step function).** A function $f$ on a rectangle $Q$ is a **step function** if there exists a partition $P$ of $Q$ such that $f$ is constant on each open subrectangle of $P$.

- The graph consists of horizontal rectangular patches (Figure 11.3).
- Values on boundary points are well-defined but irrelevant to integration theory.
- Step functions on $Q$ form a **linear space**: if $f,g$ are step functions with partitions $P,P'$, then $c_1f+c_2g$ is constant on the open subrectangles of the common refinement $P\cup P'$.


### 11.3 The Double Integral of a Step Function

Let $P=P_1\times P_2$ partition a rectangle $Q$ into $mn$ subrectangles $Q_{ij}$, and let $f$ be a step function constant with value $c_{ij}$ on the interior of $Q_{ij}$.

**Definition.** The **double integral** of $f$ over $Q$ is
$$
\iint_Q f = \sum_{i=1}^{n}\sum_{j=1}^{m} c_{ij}\,(x_i-x_{i-1})(y_j-y_{j-1}).\tag{11.1}
$$
The value is independent of the partition, provided $f$ is constant on the open subrectangles.

Using $\Delta x_i=x_i-x_{i-1}$ and $\Delta y_j=y_j-y_{j-1}$:
$$
\iint_Q f = \sum_{i=1}^{n}\sum_{j=1}^{m} c_{ij}\,\Delta x_i\,\Delta y_j.
$$
Alternative notation: $\displaystyle\iint_Q f(x,y)\,dx\,dy$.

If $f(x,y)=k$ on the interior of $Q$,
$$
\iint_Q f = k(b-a)(d-c).\tag{11.2}
$$

**Repeated (iterated) integration.** Since $b-a=\int_a^{b}dx$ and $d-c=\int_c^{d}dy$,
$$
\iint_Q f = \int_c^{d}\Bigl[\int_a^{b}f(x,y)\,dx\Bigr]dy
= \int_a^{b}\Bigl[\int_c^{d}f(x,y)\,dy\Bigr]dx.\tag{11.3}
$$
This holds for step functions by summing over subrectangles.

**Properties** (for step functions $s,t$ on a nondegenerate rectangle $Q$):

- **Theorem 11.1 (Linearity).**
  $$
  \iint_Q\bigl[c_1s+c_2t\bigr]\,dx\,dy
  = c_1\iint_Q s\,dx\,dy + c_2\iint_Q t\,dx\,dy.
  $$
- **Theorem 11.2 (Additivity).** If $Q=Q_1\cup Q_2$ (two rectangles),
  $$
  \iint_Q s\,dx\,dy = \iint_{Q_1}s\,dx\,dy + \iint_{Q_2}s\,dx\,dy.
  $$
- **Theorem 11.3 (Comparison).** If $s\le t$ on $Q$,
  $$
  \iint_Q s\,dx\,dy \le \iint_Q t\,dx\,dy.
  $$
  In particular, $t\ge0$ on $Q$ $\Rightarrow$ $\displaystyle\iint_Q t\,dx\,dy\ge0$.


### 11.4 The Definition of the Double Integral of a Function Defined and Bounded on a Rectangle

Let $f$ be bounded on a rectangle $Q$, say $|f(x,y)|\le M$ for $(x,y)\in Q$. Then $f$ is bounded below and above by constant step functions $s=-M$ and $t=M$.

Consider any two step functions $s,t$ on $Q$ satisfying
$$
s(x,y)\le f(x,y)\le t(x,y)\quad\text{for every }(x,y)\in Q.\tag{11.4}
$$

**Definition.** If there is one and only one number $I$ such that
$$
\iint_Q s\le I\le\iint_Q t\tag{11.5}
$$
for every pair of step functions satisfying (11.4), this number $I$ is called the **double integral of $f$ over $Q$**:
$$
\iint_Q f \qquad\text{or}\qquad \iint_Q f(x,y)\,dx\,dy.
$$
When such an $I$ exists, $f$ is said to be **integrable** on $Q$.

### 11.5 Upper and Lower Double Integrals

Let $S=\{\iint_Q s : s\le f,\;s\text{ step}\}$ and $T=\{\iint_Q t : f\le t,\;t\text{ step}\}$. Both are nonempty and every element of $S$ is $\le$ every element of $T$. Hence $S$ has a supremum and $T$ has an infimum, with
$$
\iint_Q s\le\sup S\le\inf T\le\iint_Q t
$$
for all $s\le f\le t$. Therefore $f$ is integrable on $Q$ **iff** $\sup S=\inf T$, in which case
$$
\iint_Q f=\sup S=\inf T.
$$

**Lower and upper integrals.**
$$
\underline{I}(f)=\sup\Bigl\{\iint_Q s : s\le f\Bigr\},\qquad
\bar{I}(f)=\inf\Bigl\{\iint_Q t : f\le t\Bigr\}.
$$

**Theorem 11.4.** Every function bounded on a rectangle $Q$ has lower and upper integrals satisfying
$$
\iint_Q s\le\underline{I}(f)\le\bar{I}(f)\le\iint_Q t
$$
for all step functions $s\le f\le t$. Moreover, $f$ is integrable on $Q$ **iff** $\underline{I}(f)=\bar{I}(f)$, and then $\displaystyle\iint_Q f=\underline{I}(f)=\bar{I}(f)$.

*The linearity, additivity, and comparison theorems of Section 11.3 extend from step functions to general integrable functions.*


### 11.6 Evaluation of a Double Integral by Repeated One-Dimensional Integration

**Theorem 11.5 (Fubini's theorem for rectangles).** Let $f$ be defined and bounded on a rectangle $Q=[a,b]\times[c,d]$, and assume $f$ is integrable on $Q$. For each fixed $y\in[c,d]$, assume the one-dimensional integral $\int_a^{b}f(x,y)\,dx$ exists and denote its value by $A(y)$. If $\int_c^{d}A(y)\,dy$ exists, then it equals the double integral:
$$
\iint_Q f(x,y)\,dx\,dy = \int_c^{d}\Bigl[\int_a^{b}f(x,y)\,dx\Bigr]dy.\tag{11.6}
$$

*Proof sketch.* For step functions $s\le f\le t$ on $Q$,
$$
\int_a^{b}s(x,y)\,dx \le A(y) \le \int_a^{b}t(x,y)\,dx.
$$
Integrating with respect to $y$ over $[c,d]$ and using (11.3),
$$
\iint_Q s \le \int_c^{d}A(y)\,dy \le \iint_Q t.
$$
Since $f$ is integrable on $Q$, the only number between all such lower and upper sums is $\iint_Q f$.

**Interchanging the order of integration:**
$$
\iint_Q f(x,y)\,dx\,dy = \int_a^{b}\Bigl[\int_c^{d}f(x,y)\,dy\Bigr]dx,\tag{11.7}
$$
provided $\int_c^{d}f(x,y)\,dy$ exists for each fixed $x\in[a,b]$ and is integrable on $[a,b]$.


### 11.7 Geometric Interpretation of the Double Integral as a Volume

If $f\ge0$ on $Q$, the set
$$
S=\{(x,y,z):(x,y)\in Q,\;0\le z\le f(x,y)\}
$$
is called the **ordinate set** of $f$ over $Q$. It consists of the points between the rectangle $Q$ and the surface $z=f(x,y)$.

For each $y\in[c,d]$, the cross-sectional area cut by a plane parallel to the $xz$-plane is
$$
A(y)=\int_a^{b}f(x,y)\,dx.
$$
Since $A(y)$ is integrable on $[c,d]$, the volume of $S$ is
$$
v(S)=\int_c^{d}A(y)\,dy=\iint_Q f(x,y)\,dx\,dy.
$$
Thus for nonnegative integrands, the double integral equals the volume of the ordinate set.

Equation (11.7) gives another way to compute the volume: integrate cross-sectional areas cut by planes parallel to the $yz$-plane.


### 11.8 Worked Examples

**Example 1.** Evaluate $\displaystyle\iint_Q (x\sin y - ye^{x})\,dx\,dy$ for $Q=[-1,1]\times[0,\pi/2]$.

Integrate first with respect to $x$:
$$
A(y)=\int_{-1}^{1}(x\sin y - ye^{x})\,dx
= \Bigl(\tfrac{x^{2}}{2}\sin y - ye^{x}\Bigr)\Big|_{-1}^{1}
= -ey + y/e.
$$
Then
$$
\iint_Q (x\sin y - ye^{x})\,dx\,dy
= \int_0^{\pi/2}(-ey+y/e)\,dy
= (1/e - e)\,\frac{\pi^{2}}{8}.
$$

*Check (integrate first with respect to $y$):*
$$
\int_{-1}^{1}\Bigl[-x\cos y - \tfrac{1}{2}y^{2}e^{x}\Bigr]_{0}^{\pi/2}dx
= \int_{-1}^{1}\bigl(-\tfrac{\pi^{2}}{8}e^{x}+x\bigr)\,dx
= (1/e-e)\,\frac{\pi^{2}}{8}.
$$

**Example 2.** Evaluate $\displaystyle\iint_Q \sqrt{|y-x^{2}|}\,dx\,dy$ for $Q=[-1,1]\times[0,2]$.

Split at $y=x^{2}$:
$$
H(x)=\int_0^{2}\sqrt{|y-x^{2}|}\,dy
= \int_0^{x^{2}}\sqrt{x^{2}-y}\,dy + \int_{x^{2}}^{2}\sqrt{y-x^{2}}\,dy
= \tfrac{2}{3}x^{3} + \tfrac{2}{3}(2-x^{2})^{3/2}.
$$
Then
$$
\iint_Q \sqrt{|y-x^{2}|}\,dx\,dy
= \int_{-1}^{1}\Bigl[\tfrac{2}{3}x^{3}+\tfrac{2}{3}(2-x^{2})^{3/2}\Bigr]dx
= \tfrac{4}{3}\int_0^{1}(2-x^{2})^{3/2}\,dx.
$$
Using $\displaystyle\int(2-x^{2})^{3/2}\,dx = \tfrac{1}{3}\bigl[x(2-x^{2})^{3/2}+3x\sqrt{2-x^{2}}+6\arcsin(x/\sqrt{2})\bigr]$,
$$
\iint_Q \sqrt{|y-x^{2}|}\,dx\,dy = \frac{4}{3} + \frac{\pi}{2}.
$$


### 11.10 Integrability of Continuous Functions

**Theorem 11.6.** If $f$ is continuous on a rectangle $Q=[a,b]\times[c,d]$, then $f$ is integrable on $Q$. Moreover, the value can be obtained by iterated integration:
$$
\iint_Q f = \int_c^{d}\Bigl[\int_a^{b}f(x,y)\,dx\Bigr]dy
= \int_a^{b}\Bigl[\int_c^{d}f(x,y)\,dy\Bigr]dx.\tag{11.8}
$$

*Proof sketch.*
1. **Integrability.** By Theorem 9.8, $f$ is bounded on $Q$. Choose $\varepsilon>0$. By the small-span theorem (Theorem 9.10), there is a partition of $Q$ into subrectangles $Q_1,\dots,Q_n$ such that the span of $f$ in each $Q_k$ is $<\varepsilon$. Let $m_k,M_k$ be the min and max of $f$ on $Q_k$. Define step functions $s(x)=m_k$, $t(x)=M_k$ on $\operatorname{int}Q_k$. Then $s\le f\le t$ and
   $$
   \iint_Q t - \iint_Q s = \sum_{k=1}^{n}(M_k-m_k)\,a(Q_k) < \varepsilon\,a(Q).
   $$
   Since $\iint_Q s\le\underline{I}(f)\le\bar{I}(f)\le\iint_Q t$, we get $0\le\bar{I}(f)-\underline{I}(f)\le\varepsilon\,a(Q)$. Letting $\varepsilon\to0$ gives $\underline{I}(f)=\bar{I}(f)$.

2. **Equality with iterated integral.** For fixed $y\in[c,d]$, $A(y)=\int_a^{b}f(x,y)\,dx$ exists by continuity. To show $A$ is continuous on $[c,d]$:
   $$
   |A(y)-A(y_1)|\le(b-a)\max_{x\in[a,b]}|f(x,y)-f(x,y_1)|.
   $$
   By uniform continuity of $f$ on $Q$, the right side $\to0$ as $y\to y_1$. Hence $A$ is continuous, so $\int_c^{d}A(y)\,dy$ exists and equals $\iint_Q f$ by Theorem 11.5. The reverse order is analogous.


### 11.11 Integrability of Bounded Functions with Discontinuities

**Definition (Set of content zero).** A bounded subset $A$ of the plane is said to have **content zero** if for every $\varepsilon>0$ there is a finite set of rectangles whose union contains $A$ and the sum of whose areas does not exceed $\varepsilon$.

In other words, a bounded set of content zero can be enclosed in a union of rectangles of arbitrarily small total area.

**Properties of content-zero sets:**
- (a) Any finite set of points has content zero.
- (b) The union of finitely many bounded sets of content zero also has content zero.
- (c) Every subset of a set of content zero has content zero.
- (d) Every line segment has content zero.

**Theorem 11.7.** Let $f$ be defined and bounded on a rectangle $Q=[a,b]\times[c,d]$. If the set of discontinuities of $f$ in $Q$ is a set of content zero, then the double integral $\displaystyle\iint_Q f$ exists.

*Proof sketch.* Let $|f|\le M$ on $Q$ and let $D$ be the discontinuity set. Given $\delta>0$, choose a partition $P$ of $Q$ such that the sum of areas of subrectangles containing points of $D$ is $<\delta$ (possible since $D$ has content zero). On these subrectangles set $s=-M$, $t=M$; on the remaining subrectangles define $s,t$ as in Theorem 11.6. Then $s\le f\le t$ on $Q$ and
$$
\iint_Q t - \iint_Q s \le \varepsilon\,a(Q) + 2M\delta.\tag{11.9}
$$
The first term comes from continuous subrectangles (span $<\varepsilon$); the second from subrectangles meeting $D$ (area $<\delta$, height $2M$). Hence $0\le\bar{I}(f)-\underline{I}(f)\le\varepsilon\,a(Q)+2M\delta$. Let $\varepsilon\to0$ to get $\bar{I}(f)-\underline{I}(f)\le2M\delta$; since $\delta$ is arbitrary, $\bar{I}(f)=\underline{I}(f)$.


### 11.12 Double Integrals Extended over More General Regions

To integrate over a bounded region $S$, enclose $S$ in a rectangle $Q$ and extend $f$ to $Q$ by
$$
\tilde{f}(x,y)=\begin{cases}f(x,y)&(x,y)\in S,\\0&(x,y)\in Q-S.\end{cases}\tag{11.10}
$$
If $\tilde{f}$ is integrable on $Q$, we say $f$ is **integrable on $S$** and define
$$
\iint_S f = \iint_Q \tilde{f}.
$$

**Type I and Type II regions.**
- **Type I:** $S=\{(x,y):a\le x\le b,\;\varphi_1(x)\le y\le\varphi_2(x)\}$, where $\varphi_1,\varphi_2$ are continuous on $[a,b]$ with $\varphi_1\le\varphi_2$.
- **Type II:** $T=\{(x,y):c\le y\le d,\;\psi_1(y)\le x\le\psi_2(y)\}$, where $\psi_1,\psi_2$ are continuous on $[c,d]$ with $\psi_1\le\psi_2$.

**Theorem 11.8.** The graph of a continuous function on an interval has content zero.

*Proof sketch.* By the small-span theorem, partition the interval so that the span of $\varphi$ on each subinterval is $<\varepsilon/(b-a)$. The graph then lies in a finite union of rectangles of total area $\varepsilon$.

**Theorem 11.9 (Type I).** Let $S$ be a Type I region between the graphs of $\varphi_1$ and $\varphi_2$. If $f$ is bounded on $S$ and continuous on $\operatorname{int}S$, then
$$
\iint_S f(x,y)\,dx\,dy = \int_a^{b}\Bigl[\int_{\varphi_1(x)}^{\varphi_2(x)}f(x,y)\,dy\Bigr]dx.\tag{11.11}
$$

*Proof sketch.* The boundary of $S$ has content zero, so $\tilde{f}$ is integrable on $Q$. For fixed $x$, $\int_c^{d}\tilde{f}(x,y)\,dy$ exists and equals $\int_{\varphi_1(x)}^{\varphi_2(x)}f(x,y)\,dy$; apply Theorem 11.5.

**Type II analogue:**
$$
\iint_T f(x,y)\,dx\,dy = \int_c^{d}\Bigl[\int_{\psi_1(y)}^{\psi_2(y)}f(x,y)\,dx\Bigr]dy.\tag{11.13}
$$

Some regions are both Type I and Type II (e.g. circles, ellipses); the order of integration is immaterial. It is often worthwhile to examine both orders before evaluating.


### 11.13 Applications to Area and Volume

**Area.** For a Type I region $S=\{(x,y):a\le x\le b,\;\varphi_1(x)\le y\le\varphi_2(x)\}$,
$$
\iint_S dx\,dy = \int_a^{b}\bigl[\varphi_2(x)-\varphi_1(x)\bigr]\,dx,
$$
which equals the area of $S$ (Theorem 2.1 of Volume I).

**Volume of an ordinate set.** If $f\ge0$ on $S$, the set
$$
\{(x,y,z):(x,y)\in S,\;0\le z\le f(x,y)\}
$$
is the ordinate set of $f$ over $S$. Its volume is
$$
V = \iint_S f(x,y)\,dx\,dy = \int_a^{b}\Bigl[\int_{\varphi_1(x)}^{\varphi_2(x)}f(x,y)\,dy\Bigr]dx.
$$
The inner integral is the area of a cross section cut by a plane parallel to the $yz$-plane; the double integral integrates these cross-sectional areas.

**Volume between two surfaces.** If $f\le g$ are continuous on $S$, then
$$
\iint_S \bigl[g(x,y)-f(x,y)\bigr]\,dx\,dy
$$
equals the volume of the solid lying between the graphs of $g$ and $f$. (Analogous for Type II regions.)


### 11.14 Worked Examples

**Example 1. Volume of an ellipsoid.** $\displaystyle\frac{x^{2}}{a^{2}}+\frac{y^{2}}{b^{2}}+\frac{z^{2}}{c^{2}}=1$.

The solid lies between $g(x,y)=c\sqrt{1-x^{2}/a^{2}-y^{2}/b^{2}}$ and $f=-g$ over the elliptical region $S=\{(x,y):x^{2}/a^{2}+y^{2}/b^{2}\le1\}$. By symmetry,
$$
V = \iint_S (g-f) = 2\iint_S g
= 8c\int_0^{a}\Bigl[\int_0^{b\sqrt{1-x^{2}/a^{2}}}\sqrt{1-\tfrac{x^{2}}{a^{2}}-\tfrac{y^{2}}{b^{2}}}\,dy\Bigr]dx.
$$
With $A=\sqrt{1-x^{2}/a^{2}}$ and $y=Ab\sin t$, the inner integral becomes $\tfrac{\pi b}{4}(1-x^{2}/a^{2})$. Hence
$$
V = 8c\int_0^{a}\frac{\pi b}{4}\Bigl(1-\frac{x^{2}}{a^{2}}\Bigr)dx = \frac{4}{3}\pi abc.
$$
For $a=b=c$ (sphere): $V=\tfrac{4}{3}\pi a^{3}$.

**Example 2. Changing the order of integration.** Given
$$
\int_0^{1}\Bigl[\int_{x^{2}}^{x}f(x,y)\,dy\Bigr]dx,
$$
the region is Type I between $y=x^{2}$ and $y=x$ for $0\le x\le1$ (Figure 11.11). As Type II:
$$
\int_0^{1}\Bigl[\int_{y}^{\sqrt{y}}f(x,y)\,dx\Bigr]dy.
$$

**Example 3. Changing the order of integration.** Given
$$
\int_0^{3}\Bigl[\int_{4y/3}^{\sqrt{25-y^{2}}}f(x,y)\,dx\Bigr]dy,
$$
the region is Type II between $x=4y/3$ and $x=\sqrt{25-y^{2}}$ for $0\le y\le3$ (a circular sector, Figure 11.12). Reversing the order splits it into two Type I regions:
$$
\int_0^{4}\Bigl[\int_0^{3x/4}f(x,y)\,dy\Bigr]dx
+ \int_4^{5}\Bigl[\int_0^{\sqrt{25-x^{2}}}f(x,y)\,dy\Bigr]dx.
$$


### 11.16 Further Applications of Double Integrals

For a thin plate with density $f(x,y)$ (mass per unit area) over a region $S$:

- **Total mass:** $\displaystyle m(S)=\iint_S f(x,y)\,dx\,dy$
- **Average density:** $\displaystyle\frac{\iint_S f}{\iint_S dx\,dy}$
- **Center of mass:**
  $$
  \bar{x}\,m(S)=\iint_S xf(x,y)\,dx\,dy,\qquad
  \bar{y}\,m(S)=\iint_S yf(x,y)\,dx\,dy.\tag{11.14}
  $$
- **Centroid** (constant density $f=c$): $\bar{x}\,a(S)=\iint_S x\,dx\,dy$, $\bar{y}\,a(S)=\iint_S y\,dx\,dy$
- **Moment of inertia** about line $L$:
  $$
  I_L=\iint_S \delta^{2}(x,y)\,f(x,y)\,dx\,dy,
  $$
  where $\delta$ is the perpendicular distance to $L$.
- About coordinate axes:
  $$
  I_x=\iint_S y^{2}f\,dx\,dy,\qquad I_y=\iint_S x^{2}f\,dx\,dy.
  $$
- **Polar moment of inertia** about the origin:
  $$
  I_0=I_x+I_y=\iint_S (x^{2}+y^{2})f\,dx\,dy.
  $$

**Example 1.** Annulus $S=\{(x,y):b^{2}\le x^{2}+y^{2}\le a^{2}\}$ with constant density $c$.
$$
I_0=c\iint_S (x^{2}+y^{2})\,dx\,dy
=\frac{\pi c}{2}(a^{4}-b^{4})
= m\,\frac{a^{2}+b^{2}}{2},\qquad m=\pi c(a^{2}-b^{2}).
$$

**Example 2.** Centroid of the region bounded by $y=\sin x$ and $0\le x\le\pi$.
By symmetry $\bar{x}=\pi/2$.
$$
\bar{y}=\frac{\iint_S y\,dx\,dy}{\iint_S dx\,dy}
=\frac{\int_0^{\pi}\frac{1}{2}\sin^{2}x\,dx}{2}
=\frac{\pi}{8}.
$$


### 11.17 Two Theorems of Pappus

**First theorem (Volume of a solid of revolution).** Let $Q$ be a plane region lying between the graphs of two continuous functions $f$ and $g$ over $[a,b]$ ($0\le g\le f$). Let $S$ be the solid obtained by rotating $Q$ about the $x$-axis. Then
$$
v(S) = 2\pi\bar{y}\,a(Q),\tag{11.15}
$$
where $\bar{y}$ is the $y$-coordinate of the centroid of $Q$ and $a(Q)$ is its area.

*Proof sketch.* $v(S)=\pi\int_a^{b}[f^{2}(x)-g^{2}(x)]\,dx$ and $\bar{y}\,a(Q)=\int_a^{b}\frac{1}{2}[f^{2}(x)-g^{2}(x)]\,dx$; comparing gives (11.15).

**Example 1. Volume of a torus.** A disk of radius $R$ with center at distance $b>R$ from the axis:
$$
v(S)=2\pi b\,(\pi R^{2})=2\pi^{2}R^{2}b.
$$

**Example 2. Centroid of a semicircular disk.** $Q=\{(x,y):x^{2}+y^{2}\le R^{2},\;y\ge0\}$. Rotating about the $x$-axis gives a sphere of volume $\frac{4}{3}\pi R^{3}$. Hence
$$
\tfrac{4}{3}\pi R^{3}=2\pi\bar{y}\,(\tfrac{1}{2}\pi R^{2})\quad\Longrightarrow\quad\bar{y}=\frac{4R}{3\pi}.
$$

**Second theorem (Centroid of a union).** Let $A$ and $B$ be thin plates (disjoint or intersecting in a set of content zero) with masses $m(A),m(B)$ and centroids $C_A,C_B$. Then the centroid of $A\cup B$ is
$$
C = \frac{m(A)C_A+m(B)C_B}{m(A)+m(B)}.\tag{11.16}
$$
This is a **convex combination** of $C_A$ and $C_B$; hence $C$ lies on the line segment joining $C_A$ and $C_B$.


### 11.19 Green's Theorem in the Plane

**Theorem 11.10 (Green's theorem).** Let $P$ and $Q$ be continuously differentiable scalar fields on an open set $S$ in the $xy$-plane. Let $C$ be a piecewise smooth Jordan curve, and let $R$ denote the union of $C$ and its interior, with $R\subseteq S$. Then
$$
\iint_R \Bigl(\frac{\partial Q}{\partial x}-\frac{\partial P}{\partial y}\Bigr)\,dx\,dy
= \oint_C P\,dx+Q\,dy,\tag{11.18}
$$
where the line integral is taken around $C$ in the **counterclockwise** direction.

The identity (11.18) is equivalent to the two formulas:
$$
\iint_R \frac{\partial Q}{\partial x}\,dx\,dy = \oint_C Q\,dy,\tag{11.19}
\qquad
-\iint_R \frac{\partial P}{\partial y}\,dx\,dy = \oint_C P\,dx.\tag{11.20}
$$

*Proof sketch for special regions.*
- **For (11.20) on a Type I region** $R=\{(x,y):a\le x\le b,\;f(x)\le y\le g(x)\}$:
  $$
  -\iint_R \frac{\partial P}{\partial y}\,dx\,dy
  = \int_a^{b}\Bigl[\int_{g(x)}^{f(x)}\frac{\partial P}{\partial y}\,dy\Bigr]dx
  = \int_a^{b}P[x,f(x)]\,dx - \int_a^{b}P[x,g(x)]\,dx.
  $$
  The line integral $\oint_C P\,dx$ splits into $\int_{C_1}P\,dx+\int_{C_2}P\,dx$ (vertical segments contribute $0$). With $\alpha(t)=t\mathbf{i}+f(t)\mathbf{j}$ on $C_1$ and $\alpha(t)=t\mathbf{i}+g(t)\mathbf{j}$ on $C_2$ (reversed),
  $$
  \oint_C P\,dx = \int_a^{b}P[t,f(t)]\,dt - \int_a^{b}P[t,g(t)]\,dt.
  $$
  Matching gives (11.20).
- **For (11.19)** a similar argument works on Type II regions.
- For general regions, decompose into finitely many regions of both types; "crosscuts" are introduced (Figure 11.15). The line integrals along crosscuts cancel in pairs, and the sum over subregions equals the integral along the boundary of $R$.


### 11.20 Some Applications of Green's Theorem

**Example 1.** Work done by $f(x,y)=(y+3x)\,\mathbf{i}+(2y-x)\,\mathbf{j}$ around the ellipse $4x^{2}+y^{2}=4$ (counterclockwise).
- $P=y+3x$, $Q=2y-x$, so $\partial Q/\partial x-\partial P/\partial y=-2$.
- By Green's theorem: $\displaystyle\oint_C P\,dx+Q\,dy=\iint_R(-2)\,dx\,dy=-2\,a(R)=-4\pi$ (since $a(R)=\pi ab=2\pi$).

**Example 2.** $\displaystyle\oint_C(5-xy-y^{2})\,dx-(2xy-x^{2})\,dy$ around the unit square.
- $P=5-xy-y^{2}$, $Q=x^{2}-2xy$, so $\partial Q/\partial x-\partial P/\partial y=3x$.
- $\displaystyle\oint_C=3\iint_R x\,dx\,dy=3\bar{x}=3\cdot\tfrac{1}{2}=\tfrac{3}{2}$.

**Example 3. Area as a line integral.** Taking $Q=\tfrac{1}{2}x$, $P=-\tfrac{1}{2}y$ (so $\partial Q/\partial x-\partial P/\partial y=1$):
$$
a(R)=\frac{1}{2}\oint_C -y\,dx+x\,dy
=\frac{1}{2}\int_a^{b}\begin{vmatrix}X(t)&Y(t)\\X'(t)&Y'(t)\end{vmatrix}dt.
$$

### 11.21 A Necessary and Sufficient Condition for a 2D Vector Field to Be a Gradient

**Definition (Simply connected).** An open connected set $S$ in the plane is **simply connected** if for every Jordan curve $C$ lying in $S$, the inner region of $C$ is also a subset of $S$. Intuitively, $S$ has no "holes." An open connected set that is not simply connected is called **multiply connected**.

**Theorem 11.11.** Let $f(x,y)=P(x,y)\,\mathbf{i}+Q(x,y)\,\mathbf{j}$ be continuously differentiable on an open simply connected set $S$. Then $f$ is a gradient on $S$ **if and only if**
$$
\frac{\partial P}{\partial y}=\frac{\partial Q}{\partial x}\quad\text{everywhere on }S.\tag{11.23}
$$

*Proof sketch.* Necessity is clear. For sufficiency: in any open connected plane set, two points can be joined by a simple step-polygon. Let $C_1,C_2$ be two such polygons joining $a$ to $x$ in $S$. Their difference forms finitely many polygonal regions $R_1,\dots,R_m\subseteq S$ (since $S$ is simply connected). By Green's theorem,
$$
\int_{\Gamma_k}P\,dx+Q\,dy=\pm\iint_{R_k}\Bigl(\frac{\partial Q}{\partial x}-\frac{\partial P}{\partial y}\Bigr)dx\,dy=0,
$$
so the line integrals along $C_1$ and $C_2$ are equal. Path independence implies $f$ is a gradient (as in Theorem 10.4).


### 11.23 Green's Theorem for Multiply Connected Regions

**Theorem 11.12.** Let $C_1,\dots,C_n$ be $n$ piecewise smooth Jordan curves such that:
- (a) No two curves intersect.
- (b) $C_2,\dots,C_n$ all lie in the interior of $C_1$.
- (c) For $i\neq j$ with $i,j>1$, $C_i$ lies in the exterior of $C_j$.

Let $R$ be the region consisting of the union of $C_1$ with that portion of the interior of $C_1$ not inside any of $C_2,\dots,C_n$. If $P,Q$ are continuously differentiable on an open set containing $R$, then
$$
\iint_R \Bigl(\frac{\partial Q}{\partial x}-\frac{\partial P}{\partial y}\Bigr)dx\,dy
= \oint_{C_1}(P\,dx+Q\,dy) - \sum_{k=2}^{n}\oint_{C_k}(P\,dx+Q\,dy).\tag{11.24}
$$

*Proof sketch.* Introduce crosscuts to decompose $R$ into simply connected regions; apply Green's theorem to each and add. The line integrals along crosscuts cancel (traversed once in each direction).

**Theorem 11.13 (Invariance under deformation).** Let $P,Q$ be continuously differentiable on an open connected set $S$ with $\partial P/\partial y=\partial Q/\partial x$ on $S$. Let $C_1,C_2$ be piecewise smooth Jordan curves in $S$ with $C_2$ in the interior of $C_1$, and assume the points inside $C_1$ but outside $C_2$ lie in $S$. Then
$$
\oint_{C_1}P\,dx+Q\,dy = \oint_{C_2}P\,dx+Q\,dy,\tag{11.25}
$$
both traversed in the same direction.

*Proof.* Apply (11.24) with $n=2$. Since $\partial Q/\partial x-\partial P/\partial y=0$ on $S$, the double integral vanishes, giving (11.25).

*Interpretation:* If $\partial P/\partial y=\partial Q/\partial x$ in $S$, the value of a line integral around a simple closed curve in $S$ is unchanged when the path is deformed to another such curve, provided all intermediate curves remain in $S$. The set $S$ need not be simply connected.


### 11.24 The Winding Number

To define "counterclockwise" analytically for arbitrary closed curves, we introduce the **winding number**.

Let $C$ be a piecewise smooth closed curve described by $\alpha(t)=X(t)\,\mathbf{i}+Y(t)\,\mathbf{j}$ on $[a,b]$. Let $P_0=(x_0,y_0)$ be a point not on $C$. The **winding number** of $\alpha$ with respect to $P_0$ is
$$
W(\alpha;P_0)=\frac{1}{2\pi}\int_a^{b}
\frac{[X(t)-x_0]Y'(t)-[Y(t)-y_0]X'(t)}{[X(t)-x_0]^{2}+[Y(t)-y_0]^{2}}\,dt.\tag{11.27}
$$
Equivalently,
$$
W(\alpha;P_0)=\frac{1}{2\pi}\oint_C
\frac{-(y-y_0)\,dx+(x-x_0)\,dy}{(x-x_0)^{2}+(y-y_0)^{2}}.\tag{11.28}
$$

**Properties.**
- The value is always an **integer** (positive, negative, or zero).
- If $C$ is a Jordan curve: $W=0$ when $P_0$ is **outside** $C$; $W=+1$ or $-1$ when $P_0$ is **inside** $C$.
- The value is the same ($+1$ or $-1$) for **every** point inside $C$.

**Orientation.** If $W(\alpha;P_0)=+1$ for every $P_0$ inside $C$, $\alpha$ traces $C$ in the **positive (counterclockwise)** direction. If $W=-1$, it traces $C$ in the **negative (clockwise)** direction.

*Proof sketch for Jordan curves.* Let $S=\mathbb{R}^{2}\setminus\{(x_0,y_0)\}$. The integrand in (11.28) satisfies $\partial P/\partial y=\partial Q/\partial x$ on $S$. By Theorem 11.13, $C$ can be replaced by a circle centered at $(x_0,y_0)$ without changing the integral. For a positively oriented circle, $X(t)=a\cos t+x_0$, $Y(t)=a\sin t+y_0$, the integrand in (11.27) is identically $1$, so $W=\frac{1}{2\pi}\int_0^{2\pi}1\,dt=1$. For negative orientation, $W=-1$.


### 11.26 Change of Variables in a Double Integral

Recall the 1D substitution formula:
$$
\int_a^{b}f(x)\,dx = \int_c^{d}f[g(t)]\,g'(t)\,dt,\tag{11.29}
$$
where $a=g(c)$, $b=g(d)$.

**2D analogue.** A mapping from the $uv$-plane to the $xy$-plane is given by
$$
x=X(u,v),\qquad y=Y(u,v),\tag{11.30}
$$
or in vector form
$$
\mathbf{r}(u,v)=X(u,v)\,\mathbf{i}+Y(u,v)\,\mathbf{j},\qquad (u,v)\in T.\tag{11.31}
$$
If the mapping is one-to-one and $X,Y$ have continuous partials, then
$$
\iint_S f(x,y)\,dx\,dy = \iint_T f[X(u,v),Y(u,v)]\,|J(u,v)|\,du\,dv,\tag{11.32}
$$
where the **Jacobian determinant** is
$$
J(u,v)=\det\begin{bmatrix}\dfrac{\partial X}{\partial u}&\dfrac{\partial X}{\partial v}\\[6pt]\dfrac{\partial Y}{\partial u}&\dfrac{\partial Y}{\partial v}\end{bmatrix}
=\frac{\partial(X,Y)}{\partial(u,v)}.
$$

The formula also holds if the mapping fails to be one-to-one or $J=0$ on a set of content zero.

**Geometric motivation.** For a small rectangle in the $uv$-plane with sides $\Delta u,\Delta v$, define
$$
V_1=\frac{\partial\mathbf{r}}{\partial u},\qquad V_2=\frac{\partial\mathbf{r}}{\partial v}.
$$
The image is approximately a parallelogram with sides $V_1\Delta u$ and $V_2\Delta v$, whose area is
$$
\|(V_1\Delta u)\times(V_2\Delta v)\|=\|V_1\times V_2\|\,\Delta u\,\Delta v = |J(u,v)|\,\Delta u\,\Delta v.
$$
Thus $|J|$ acts as a local **magnification factor** for area. When $f\equiv1$,
$$
\iint_S dx\,dy = \iint_T |J(u,v)|\,du\,dv.\tag{11.33}
$$

**Singular points.** If $J(u,v)=0$, the vectors $V_1,V_2$ are parallel and the parallelogram degenerates. The transformation formula remains valid provided singular points form a set of content zero.

