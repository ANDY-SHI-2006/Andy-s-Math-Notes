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

