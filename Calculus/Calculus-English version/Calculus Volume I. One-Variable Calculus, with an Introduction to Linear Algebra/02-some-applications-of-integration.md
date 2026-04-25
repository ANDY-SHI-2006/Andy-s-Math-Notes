[<- Previous: 1. The Concepts of Integral Calculus](01-the-concepts-of-integral-calculus.md) | [Next: 3. Continuous Functions ->](03-continuous-functions.md)

# 2. Some Applications of Integration

## 2.1 Introduction

In Section 1.18 we expressed the area of the ordinate set of a nonnegative function as an integral. In this chapter we will show that areas of more general regions can also be expressed as integrals. We will also discuss further applications of the integral to concepts such as **volume**, **work**, and **averages**. Then, at the end of the chapter, we will study properties of functions defined by integrals.

## 2.2 The Area of a Region Between Two Graphs Expressed as an Integral

### 2.2.1 Definition

If $f \le g$ on $[a, b]$, the **region between the graphs** of $f$ and $g$ is the set $S$ of all points $(x, y)$ satisfying:

$$
f(x) \le y \le g(x), \quad a \le x \le b.
$$

### 2.2.2 Theorem 2.1 鈥?Area Formula

Assume $f$ and $g$ are integrable and $f \le g$ on $[a, b]$. Then the region $S$ between their graphs is **measurable**, and its area is:

$$
a(S) = \int_a^b \bigl[g(x) - f(x)\bigr] \, dx. \tag{2.1}
$$

### 2.2.3 Proof Sketch

**Case 1:** $f, g \ge 0$. Let $G$ be the ordinate set of $g$ and $F$ the ordinate set of $f$ (minus its graph). Then $S = G - F$. By Theorems 1.10 and 1.11, both $F$ and $G$ are measurable, so:

$$
a(S) = a(G) - a(F) = \int_a^b g(x)\,dx - \int_a^b f(x)\,dx = \int_a^b \bigl[g(x) - f(x)\bigr]\,dx.
$$

**Case 2:** General $f \le g$. Choose $c > 0$ large enough so that $f + c \ge 0$ and $g + c \ge 0$. The region $T$ between $f+c$ and $g+c$ has area:

$$
a(T) = \int_a^b \bigl[(g(x)+c) - (f(x)+c)\bigr]\,dx = \int_a^b \bigl[g(x) - f(x)\bigr]\,dx.
$$

Since $T$ is congruent to $S$ (translation by $c$), $S$ is also measurable with the same area.

## 2.3 Worked Examples

### 2.3.1 Example 1 鈥?Simple Region

Compute the area of the region $S$ between $f(x) = x(x-2)$ and $g(x) = x/2$ over $[0, 2]$.

Since $f \le g$ on $[0, 2]$, by Theorem 2.1:

$$
a(S) = \int_0^2 \bigl[g(x) - f(x)\bigr]\,dx = \int_0^2 \left(\frac{5}{2}x - x^2\right) dx = \frac{5}{2}\cdot\frac{2^2}{2} - \frac{2^3}{3} = \frac{7}{3}.
$$

### 2.3.2 Example 2 鈥?Splitting the Interval

Compute the area between $f(x) = x$ and $g(x) = x^3/4$ over $[-1, 2]$.

Here $f \le g$ on $[-1, 0]$ but $g \le f$ on $[0, 2]$. We split:

$$
a(S) = \int_{-1}^{0} \bigl[g(x) - f(x)\bigr]\,dx + \int_{0}^{2} \bigl[f(x) - g(x)\bigr]\,dx
$$

$$
= \int_{-1}^{0} \left(\frac{x^3}{4} - x\right) dx + \int_{0}^{2} \left(x - \frac{x^3}{4}\right) dx = \frac{23}{16}.
$$

In general, if $[a, b]$ can be broken into subintervals where either $f \le g$ or $g \le f$:

$$
a(S) = \int_a^b |g(x) - f(x)|\,dx.
$$

### 2.3.3 Example 3 鈥?Area of a Circular Disk

A disk of radius $r$ is the region between $g(x) = \sqrt{r^2 - x^2}$ and $f(x) = -\sqrt{r^2 - x^2}$ on $[-r, r]$.

By Theorem 2.1 and the fact that $g - f = 2g$:

$$
A(r) = \int_{-r}^{r} 2g(x)\,dx = 2\int_{-r}^{r} \sqrt{r^2 - x^2}\,dx.
$$

Using Theorem 1.19 with $k = 1/r$:

$$
A(r) = 2r^2 \int_{-1}^{1} \sqrt{1 - x^2}\,dx = r^2 A(1).
$$

**Definition.** We define the number $\pi$ to be the area of a unit disk: $\pi = A(1)$. Thus:

$$
A(r) = \pi r^2.
$$

### 2.3.4 Example 4 鈥?Similarity Transformation

Let $f$ be nonnegative and integrable on $[a, b]$, with ordinate set $S$. Under a similarity transformation with factor $k > 0$, the set $kS$ is the ordinate set of $g(x) = kf(x/k)$ on $[ka, kb]$.

By Theorem 1.19:

$$
a(kS) = \int_{ka}^{kb} kf(x/k)\,dx = k^2 \int_a^b f(x)\,dx = k^2 \, a(S).
$$

Thus similarity with factor $k$ multiplies area by $k^2$.

### 2.3.5 Example 5 鈥?Calculating $\int_0^a x^{1/2}\,dx$

Consider $f(x) = x^{1/2}$ on $[0, a]$. Its ordinate set $S$ has area:

$$
a(S) = \int_0^a x^{1/2}\,dx.
$$

The region $T$ above the curve and below $y = a^{1/2}$ is the ordinate set of $g(y) = y^2$ on $[0, a^{1/2}]$:

$$
a(T) = \int_0^{a^{1/2}} y^2\,dy = \frac{1}{3}a^{3/2}.
$$

Since $a(S) + a(T) = a \cdot a^{1/2} = a^{3/2}$:

$$
\int_0^a x^{1/2}\,dx = a^{3/2} - \frac{1}{3}a^{3/2} = \frac{2}{3}a^{3/2}.
$$

### 2.3.6 Theorem 2.2 鈥?General Power Formula

For $a > 0$, $b > 0$, and $n$ a positive integer:

$$
\int_a^b x^{1/n}\,dx = \frac{b^{1+1/n} - a^{1+1/n}}{1 + 1/n}. \tag{2.2}
$$

## 2.4 The Trigonometric Functions

### 2.4.1 Introduction

Before further applications of integration, we briefly discuss the six trigonometric functions 鈥?sine, cosine, tangent, cotangent, secant, cosecant 鈥?and their inverses. In calculus their importance lies not in triangle relations but in their **properties as functions**, especially **periodicity**.

A function $f$ is **periodic** with period $p \neq 0$ if $f(x+p) = f(x)$ for all $x$ in its domain. The sine and cosine functions are periodic with period $2\pi$, where $\pi$ is the area of a unit circular disk.

### 2.4.2 Fundamental Properties of Sine and Cosine

We take the following four properties as axioms; all other properties can be deduced from them.

| Property | Statement |
|----------|-----------|
| **1. Domain** | $\sin x$ and $\cos x$ are defined for all real $x$. |
| **2. Special values** | $\cos 0 = \sin\frac{\pi}{2} = 1$, $\cos\pi = -1$. |
| **3. Cosine of a difference** | $\cos(y-x) = \cos y \cos x + \sin y \sin x$ for all $x, y$. |
| **4. Fundamental inequalities** | For $0 < x < \frac{\pi}{2}$: $0 < \cos x < \dfrac{\sin x}{x} < \dfrac{1}{\cos x}$. |

### 2.4.3 Theorem 2.3 鈥?Deduced Properties

If $\sin$ and $\cos$ satisfy properties 1鈥?, then they also satisfy:

| Property | Statement |
|----------|-----------|
| **(a) Pythagorean identity** | $\sin^2 x + \cos^2 x = 1$ for all $x$. |
| **(b) Special values** | $\sin 0 = \cos\frac{\pi}{2} = \sin\pi = 0$. |
| **(c) Even / odd** | $\cos(-x) = \cos x$, $\sin(-x) = -\sin x$. |
| **(d) Co-relations** | $\sin(\frac{\pi}{2}+x) = \cos x$, $\cos(\frac{\pi}{2}+x) = -\sin x$. |
| **(e) Periodicity** | $\sin(x+2\pi) = \sin x$, $\cos(x+2\pi) = \cos x$. |
| **(f) Addition formulas** | $\cos(x+y) = \cos x \cos y - \sin x \sin y$, $\sin(x+y) = \sin x \cos y + \cos x \sin y$. |
| **(g) Difference formulas** | $\sin a - \sin b = 2\sin\frac{a-b}{2}\cos\frac{a+b}{2}$, $\cos a - \cos b = -2\sin\frac{a-b}{2}\sin\frac{a+b}{2}$. |
| **(h) Monotonicity** | On $[0, \frac{\pi}{2}]$, $\sin$ is strictly increasing and $\cos$ is strictly decreasing. |

### 2.4.4 Proof Sketch

- **(a)** Set $x = y$ in property 3 and use $\cos 0 = 1$.
- **(b)** Follows from (a) with $x = 0, \frac{\pi}{2}, \pi$ and $\sin\frac{\pi}{2} = 1$.
- **(c)** Evenness of $\cos$ follows from property 3 with $y = 0$. Oddness of $\sin$ follows from $\cos(\frac{\pi}{2}-x) = \sin x$ and property 3.
- **(d)** Use $\cos(\frac{\pi}{2}-x) = \sin x$ (set $y = \frac{\pi}{2}$ in property 3).
- **(e)** Repeated application of (d).
- **(f)** Replace $x$ by $-x$ in property 3 and use even/odd properties; then apply (d).
- **(g)** Replace $y$ by $-y$ in the sine addition formula, then add/subtract.
- **(h)** From property 4, $\sin x$ and $\cos x$ are positive on $(0, \frac{\pi}{2})$. Using (g) with $0 < b < a < \frac{\pi}{2}$ shows $\sin a > \sin b$ and $\cos a < \cos b$.

### 2.4.5 Double-Angle Formulas

Setting $y = x$ in the addition formulas:

$$
\sin 2x = 2\sin x \cos x, \qquad \cos 2x = \cos^2 x - \sin^2 x = 1 - 2\sin^2 x.
$$

By the Pythagorean identity, $|\sin x| \le 1$ and $|\cos x| \le 1$ for all $x$.

## 2.5 Integration Formulas for the Sine and Cosine

### 2.5.1 Integrability

By Theorem 2.3(h), $\sin$ and $\cos$ are strictly monotonic on each quarter-period. Hence they are **piecewise monotonic** and therefore **integrable** on every finite interval.

### 2.5.2 Theorem 2.4 鈥?Approximation Inequalities

If $0 < a \le \frac{\pi}{2}$ and $n \ge 1$, then:

$$
\frac{a}{n} \sum_{k=1}^{n} \cos\frac{ka}{n} < \sin a < \frac{a}{n} \sum_{k=0}^{n-1} \cos\frac{ka}{n}. \tag{2.6}
$$

### 2.5.3 Proof Sketch

Use the trigonometric identity (provable by difference formulas and telescoping):

$$
2\sin\frac{x}{2} \sum_{k=1}^{n} \cos kx = \sin\left(n+\frac{1}{2}\right)x - \sin\frac{x}{2}. \tag{2.7}
$$

Dividing by $2\sin\frac{x}{2}$ (for $x \neq 2m\pi$) gives closed forms for $\sum\cos kx$ and $\sum_{k=0}^{n-1}\cos kx$. Substituting $x = a/n$ and using the fundamental inequality $\cos\theta < \frac{\sin\theta}{\theta}$ yields (2.6).

### 2.5.4 Theorem 2.5 鈥?Basic Integrals

For every real $a$:

$$
\int_0^a \cos x \, dx = \sin a, \qquad \int_0^a \sin x \, dx = 1 - \cos a. \tag{2.13, 2.14}
$$

### 2.5.5 Proof Sketch

**Step 1.** For $0 < a \le \frac{\pi}{2}$, apply **Theorem 1.14** (calculation formula for monotonic functions) together with the inequalities (2.6) of Theorem 2.4. This gives (2.13) directly.

**Step 2.** Extend to all real $a$ using:
- Reflection property: $\int_0^{-a} \cos x\,dx = -\int_0^{a} \cos x\,dx$
- Translation and periodicity: $\cos(x+\pi) = -\cos x$
- Periodicity with period $2\pi$

**Step 3.** Deduce (2.14) from (2.13) via the co-relation $\sin x = \cos(x - \frac{\pi}{2})$ and translation:

$$
\int_0^a \sin x\,dx = \int_{-\pi/2}^{a-\pi/2} \cos x\,dx = 1 - \cos a.
$$

### 2.5.6 Example 1 鈥?General Interval Formulas

For any real $a, b$:

$$
\int_a^b \cos x\,dx = \sin b - \sin a = \sin x\,\Big|_a^b, \qquad
\int_a^b \sin x\,dx = -(\cos b - \cos a) = -\cos x\,\Big|_a^b.
$$

### 2.5.7 Example 2 鈥?Scaling the Argument

For $c \neq 0$:

$$
\int_a^b \cos cx\,dx = \frac{1}{c}(\sin cb - \sin ca), \qquad
\int_a^b \sin cx\,dx = -\frac{1}{c}(\cos cb - \cos ca).
$$

### 2.5.8 Example 3 鈥?Powers of Sine and Cosine

Using $\sin^2 x = \frac{1}{2}(1 - \cos 2x)$:

$$
\int_0^a \sin^2 x\,dx = \frac{a}{2} - \frac{1}{4}\sin 2a, \qquad
\int_0^a \cos^2 x\,dx = \frac{a}{2} + \frac{1}{4}\sin 2a.
$$

## 2.6 A Geometric Description of the Sine and Cosine

### 2.6.1 Radian Measure via Sector Area

- On the unit circle $x^2 + y^2 = 1$, define the **radian measure** of an angle by twice the area of the corresponding circular sector.
- For a sector with central angle $\theta$, area $= \frac{1}{2}\theta$, so $\theta$ is the arc length on the unit circle.

### 2.6.2 Geometric Definitions

- Let $(x, y)$ be the endpoint of an arc of length $t$ on the unit circle, starting at $(1, 0)$ and moving counterclockwise.
- Define:
  $$
  \cos t = x, \qquad \sin t = y.
  $$
- This agrees with the analytic definitions and satisfies $-1 \le \sin t, \cos t \le 1$.

### 2.6.3 Pythagorean Identity

- Since $(x, y)$ lies on the unit circle:
  $$
  \sin^2 t + \cos^2 t = 1.
  $$

### 2.6.4 Cosine Difference Formula

- From the geometric definition, the distance between two points on the unit circle corresponding to arc lengths $x$ and $y$ is invariant under rotation. This yields:
  $$
  \cos(y - x) = \cos y \cos x + \sin y \sin x.
  $$
- Setting $y = \frac{\pi}{2}$ gives the reduction formulas:
  $$
  \sin\left(\frac{\pi}{2} - x\right) = \cos x, \qquad
  \cos\left(\frac{\pi}{2} - x\right) = \sin x.
  $$

### 2.6.5 Fundamental Inequalities

- For $0 < x < \frac{\pi}{2}$:
  $$
  0 < \cos x < \frac{\sin x}{x} < \frac{1}{\cos x}.
  $$
- **Geometric proof**: Compare the area of the circular sector ($x/2$), the inscribed triangle ($\frac{1}{2}\sin x$), and the circumscribed triangle ($\frac{1}{2}\tan x$).
- These inequalities imply the limit:
  $$
  \lim_{x \to 0} \frac{\sin x}{x} = 1.
  $$

## 2.7 Polar Coordinates

### 2.7.1 Definition

- A point $P$ distinct from the origin is located by **polar coordinates** $(r, \theta)$:
  - $r > 0$: radial distance from origin to $P$
  - $\theta$: angle (in radians) between the positive $x$-axis and segment $\overline{OP}$
- Relation to rectangular coordinates $(x, y)$:
  $$
  x = r \cos \theta, \qquad y = r \sin \theta
  $$
  (Equation 2.15)

### 2.7.2 Non-Uniqueness of Polar Coordinates

- If $(r, \theta)$ represents $P$, so does $(r, \theta + 2n\pi)$ for any integer $n$.
- The radial distance is unique: $r = \sqrt{x^2 + y^2}$.
- The polar angle $\theta$ is determined only up to integer multiples of $2\pi$.
- **Origin**: $r = 0$ and $\theta$ may be any real number.

### 2.7.3 Polar Equations

- Let $f$ be a nonnegative function on $[a, b]$. The set of points with $r = f(\theta)$ is the **graph of $f$ in polar coordinates**.
- The equation $r = f(\theta)$ is called a **polar equation**.
- Some curves have simpler polar equations than Cartesian equations.

### 2.7.4 Example 鈥?Figure-Eight Curve

- Cartesian equation: $(x^2 + y^2)^3 = y^2$
- Conversion: using $x^2 + y^2 = r^2$ and $y = r \sin \theta$:
  $$
  r^6 = r^2 \sin^2 \theta \implies r^4 = \sin^2 \theta \implies r = \sqrt{|\sin \theta|}
  $$
- Sketching via polar equation is easier than from Cartesian form alone.
  - In $0 \le \theta \le \pi/2$: $\sin \theta$ increases from $0$ to $1$, so $r$ increases from $0$ to $1$.
  - Key points: $\theta = \pi/6, \pi/4, \pi/3$.
  - The rest follows from symmetry and periodicity of $|\sin \theta|$.

### 2.7.5 Another Example 鈥?Circle

- Cartesian: $x^2 + y^2 = 4$
- Polar: $r = 2$ (much simpler)

## 2.8 The Integral for Area in Polar Coordinates

### 2.8.1 Radial Set

- Let $f \ge 0$ on $[a, b]$ with $0 \le b - a \le 2\pi$.
- The **radial set** of $f$ over $[a, b]$:
  $$
  R = \{(r, \theta) \mid 0 \le r \le f(\theta), \ a \le \theta \le b\}
  $$
- If $f$ is constant, $R$ is a circular sector.

### 2.8.2 Area of a Step Function's Radial Set

- For a step function $s$ with values $s_k$ on subintervals $(\theta_{k-1}, \theta_k)$:
  - Each piece is a circular sector of radius $s_k$ and angle $(\theta_k - \theta_{k-1})$.
  - Area of one sector: $\frac{1}{2}(\theta_k - \theta_{k-1})s_k^2$.
  - Total area (non-overlapping since $b - a \le 2\pi$):
    $$
    a(S) = \frac{1}{2} \sum_{k=1}^{n} s_k^2 (\theta_k - \theta_{k-1}) = \frac{1}{2} \int_a^b s^2(\theta) \, d\theta
    $$

### 2.8.3 Theorem 2.6 鈥?Area Formula

Let $R$ be the radial set of a nonnegative function $f$ over $[a, b]$ ($0 \le b - a \le 2\pi$), and assume $R$ is measurable. If $f^2$ is integrable on $[a, b]$, then:

$$
a(R) = \frac{1}{2} \int_a^b f^2(\theta) \, d\theta
$$

**Proof Sketch:**

1. Choose step functions $s, t$ with $0 \le s \le f \le t$ on $[a, b]$.
2. Their radial sets satisfy $S \subseteq R \subseteq T$.
3. By monotonicity of area: $a(S) \le a(R) \le a(T)$.
4. Using the step-function area formula:
   $$
   \frac{1}{2}\int_a^b s^2 \le a(R) \le \frac{1}{2}\int_a^b t^2
   $$
5. Since $f^2$ is integrable and $s^2 \le f^2 \le t^2$, the squeeze principle gives:
   $$
   2a(R) = \int_a^b f^2(\theta) \, d\theta
   $$

### 2.8.4 Example 鈥?Area of the Figure-Eight Curve

- For $r = \sqrt{|\sin \theta|}$, we have $f^2(\theta) = |\sin \theta|$.
- By symmetry, compute the first-quadrant portion and multiply by 4:
  $$
  a(R) = 4 \cdot \frac{1}{2} \int_0^{\pi/2} \sin \theta \, d\theta = 2\Bigl[-\cos \theta\Bigr]_0^{\pi/2} = 2(1 - 0) = 2
  $$

## 2.9 Application of Integration to the Calculation of Volume

### 2.9.1 Measurable Sets and Volume Function

- We assume a class $\mathscr{A}$ of **measurable sets** (solids) in 3D space and a **volume function** $v$ assigning each $S \in \mathscr{A}$ a number $v(S)$.
- The axioms for volume parallel those for area, with one key difference: **Cavalieri's principle** replaces congruence invariance.

### 2.9.2 Axioms for Volume

| Axiom | Statement |
|-------|-----------|
| **1. Nonnegative** | $v(S) \ge 0$ for all $S \in \mathscr{A}$ |
| **2. Additive** | $v(S \cup T) = v(S) + v(T) - v(S \cap T)$ |
| **3. Difference** | If $S \subseteq T$, then $v(T - S) = v(T) - v(S)$ |
| **4. Cavalieri's principle** | If $S, T$ are Cavalieri solids and $a(S \cap F) \le a(T \cap F)$ for every plane $F \perp L$, then $v(S) \le v(T)$ |
| **5. Scale (box)** | A box with edges $a, b, c$ has volume $abc$ |
| **6. Convexity** | Every convex set is in $\mathscr{A}$ |

- **Cavalieri solid**: A solid whose cross-sections perpendicular to a given line $L$ are all measurable plane sets.
- **Intuition**: A Cavalieri solid is like a stack of thin sheets; sliding sheets in their own planes changes shape but not volume.

### 2.9.3 Consequences of the Axioms

- **Monotone property**: $S \subseteq T \implies v(S) \le v(T)$ (follows from Axioms 1 and 3).
- **Bounded plane sets have zero volume**: Any bounded plane set $S$ lies inside a box of arbitrarily small altitude, so $v(S) = 0$.
- If $a(S \cap F) = a(T \cap F)$ for all $F \perp L$, then $v(S) = v(T)$.

### 2.9.4 Volume of a Right Cylindrical Solid

- A **right cylindrical solid** with base area $a(B)$ and altitude $(b - a)$:
  $$
  v(S) = a(B)(b - a) = \int_a^b a_S(z) \, dz
  $$
  where $a_S(z)$ is the cross-sectional area function (constant $= a(B)$ on $[a, b]$).

### 2.9.5 Theorem 2.7 鈥?General Cavalieri Solid

Let $R$ be a Cavalieri solid with cross-sectional area function $a_R$ integrable on $[a, b]$ (zero outside). Then:

$$
v(R) = \int_a^b a_R(u) \, du
$$

**Proof Sketch:**

1. Choose step functions $s \le a_R \le t$ on $[a, b]$.
2. Construct cylindrical solids $S$ (from $s$) and $T$ (from $t$) with $v(S) = \int_a^b s$ and $v(T) = \int_a^b t$.
3. By Cavalieri's principle: $v(S) \le v(R) \le v(T)$.
4. Hence $\int_a^b s \le v(R) \le \int_a^b t$ for all such $s, t$.
5. Since $a_R$ is integrable, $v(R) = \int_a^b a_R(u) \, du$.

### 2.9.6 Example 鈥?Solid of Revolution (Disk Method)

- Let $f \ge 0$ and integrable on $[a, b]$. Revolve the ordinate set about the $x$-axis.
- Cross section at $x$ is a circular disk of radius $f(x)$, area $\pi f^2(x)$.
- Volume:
  $$
  v = \int_a^b \pi f^2(x) \, dx
  $$

**Sphere of radius $r$:**
- $f(x) = \sqrt{r^2 - x^2}$ on $[-r, r]$
- $v = \pi \int_{-r}^{r} (r^2 - x^2) \, dx = 2\pi \int_0^r (r^2 - x^2) \, dx = \frac{4}{3}\pi r^3$

### 2.9.7 Washer Method

- For two functions $0 \le f \le g$ on $[a, b]$, revolve the region between their graphs about the $x$-axis.
- Cross section at $x$ is an **annulus** with area $\pi[g^2(x) - f^2(x)]$.
- Volume:
  $$
  v = \int_a^b \pi\bigl[g^2(x) - f^2(x)\bigr] \, dx
  $$

## 2.10 Application of Integration to the Concept of Work

### 2.10.1 Work as Energy Expended

- **Work** measures energy expended by a force moving a particle along a line (the $x$-axis) from $x = a$ to $x = b$.
- Force is a function of position: $f(x)$.
  - $f(x) > 0$: force acts in positive $x$-direction
  - $f(x) < 0$: force acts in opposite direction
- **Constant force**: $W = c \cdot (b - a)$ (force 脳 displacement).

**Units:**

| System | Force | Distance | Work |
|--------|-------|----------|------|
| British | pounds (lb) | feet (ft) | foot-pounds (ft-lb) |
| cgs | dynes | centimeters (cm) | dyne-centimeters (ergs) |
| mks | newtons (N) | meters (m) | newton-meters (joules) |

- $1$ newton $= 10^5$ dynes; $1$ joule $= 10^7$ ergs.

### 2.10.2 Example 鈥?Stone Thrown Upward

- A 3 lb stone thrown upward to 15 ft.
- Gravity: $f(x) = -3$ lb (downward).
- Work by gravity from $x = 6$ ft to $x = 15$ ft:
  $$W = (-3)(15 - 6) = -27 \text{ ft-lb}$$
- Work by gravity falling from $x = 15$ ft to $x = 6$ ft:
  $$W = (-3)(6 - 15) = 27 \text{ ft-lb}$$

### 2.10.3 Fundamental Properties of Work

Let $W_a^b(f)$ denote work done by $f$ from $a$ to $b$.

| Property | Statement |
|----------|-----------|
| **1. Additive** | If $a < c < b$, then $W_a^b(f) = W_a^c(f) + W_c^b(f)$ |
| **2. Monotone** | If $f \le g$ on $[a, b]$, then $W_a^b(f) \le W_a^b(g)$ |
| **3. Elementary** | If $f(x) = c$ (constant), then $W_a^b(f) = c \cdot (b - a)$ |

- Additivity extends to any finite partition: $W_a^b(f) = \sum_{k=1}^n W_k$.

### 2.10.4 Work for Step Functions

- If $s$ is a step function with value $s_k$ on $(x_{k-1}, x_k)$:
  $$
  W_a^b(s) = \sum_{k=1}^n s_k(x_k - x_{k-1}) = \int_a^b s(x) \, dx
  $$

### 2.10.5 Theorem 2.8 鈥?Work as Integral

Suppose work satisfies properties 1, 2, and 3. Then for any integrable force function $f$:

$$
W_a^b(f) = \int_a^b f(x) \, dx
$$

**Proof Sketch:**

1. Choose step functions $s \le f \le t$ on $[a, b]$.
2. By monotonicity: $W_a^b(s) \le W_a^b(f) \le W_a^b(t)$.
3. For step functions: $W_a^b(s) = \int_a^b s$ and $W_a^b(t) = \int_a^b t$.
4. Hence $\int_a^b s \le W_a^b(f) \le \int_a^b t$ for all such $s, t$.
5. Since $f$ is integrable: $W_a^b(f) = \int_a^b f(x) \, dx$.

> **Note:** Many authors simply define work as $\int_a^b f(x) \, dx$; the above provides motivation.

### 2.10.6 Example 鈥?Work to Stretch a Spring (Hooke's Law)

- Force to stretch a spring: $f(x) = cx$ (Hooke's law), $c > 0$.
- Work to stretch distance $a$:
  $$
  W = \int_0^a cx \, dx = \frac{ca^2}{2}
  $$
- Work is proportional to the **square** of displacement.

> Curved motion work is discussed in Volume II using line integrals.

## 2.11 Average Value of a Function

### 2.11.1 Arithmetic Mean

- For $n$ real numbers $a_1, a_2, \dots, a_n$:
  $$
  \bar{a} = \frac{1}{n} \sum_{k=1}^n a_k
  $$
  (Equation 2.17)
- If $a_k = f(x_k)$, the arithmetic mean of function values is $\frac{1}{n}\sum_{k=1}^n f(x_k)$.

### 2.11.2 Definition 鈥?Average Value on an Interval

- If $f$ is integrable on $[a, b]$, the **average value** of $f$ on $[a, b]$ is:
  $$
  A(f) = \frac{1}{b - a} \int_a^b f(x) \, dx
  $$
  (Equation 2.18)

**Geometric interpretation** (for $f \ge 0$):
- $(b - a)A(f) = \int_a^b f(x) \, dx$
- The rectangle of altitude $A(f)$ and base $[a, b]$ has area equal to the ordinate set of $f$.

### 2.11.3 Connection to Discrete Mean

- For a step function constant on $n$ equal subintervals of $[a, b]$:
  $$
  A(f) = \frac{1}{b - a} \sum_{k=1}^n f(x_k) \frac{b - a}{n} = \frac{1}{n} \sum_{k=1}^n f(x_k)
  $$
- Thus $A(f)$ extends the arithmetic mean to continuous functions.

### 2.11.4 Weighted Average

- For weights $w_1, \dots, w_n$ (nonnegative, not all zero):
  $$
  \bar{a} = \frac{\sum_{k=1}^n w_k a_k}{\sum_{k=1}^n w_k}
  $$
- Extension to integrable functions (weight function $w \ge 0$, $\int_a^b w \neq 0$):
  $$
  A(f) = \frac{\int_a^b w(x)f(x) \, dx}{\int_a^b w(x) \, dx}
  $$
  (Equation 2.19)

### 2.11.5 Applications in Physics

**Center of mass of a rod:**
- Rod of length $a$ along $x$-axis with mass density $\rho(x)$.
- Mass of portion $[0, x]$: $m(x) = \int_0^x \rho(t) \, dt$.
- **Center of mass**:
  $$
  \bar{x} = \frac{\int_0^a x\rho(x) \, dx}{\int_0^a \rho(x) \, dx}
  $$
  (weighted average of distance $x$ with weight $\rho$)

**Moment of inertia and radius of gyration:**
- **Second moment** (moment of inertia) about 0:
  $$
  \int_0^a x^2 \rho(x) \, dx
  $$
- **Radius of gyration** $r$:
  $$
  r^2 = \frac{\int_0^a x^2 \rho(x) \, dx}{\int_0^a \rho(x) \, dx}
  $$
  (weighted average of $x^2$ with weight $\rho$)

> Weighted averages also appear in probability theory, where **expectation** and **variance** play analogous roles to center of mass and moment of inertia.

## 2.12 The Integral as a Function of the Upper Limit. Indefinite Integrals

### 2.12.1 Definition

- Let $f$ be integrable on $[a, b]$. Define:
  $$
  A(x) = \int_a^x f(t) \, dt, \qquad a \le x \le b
  $$
  (Equation 2.20)
- $A(x)$ is called **an indefinite integral** of $f$.
- The lower limit $a$ is fixed; different choices of $a$ give different functions $A$.

### 2.12.2 Two Indefinite Integrals Differ by a Constant

- If $F(x) = \int_c^x f(t) \, dt$ (different lower limit $c$), then:
  $$
  A(x) - F(x) = \int_a^c f(t) \, dt
  $$
- The difference is **independent of $x$**; any two indefinite integrals of $f$ differ by a constant.

### 2.12.3 Evaluating Definite Integrals

- If $F(x) = \int_c^x f(t) \, dt$, then:
  $$
  \int_a^b f(t) \, dt = F(b) - F(a)
  $$
  (Equation 2.21)
- Notation: $F(x)\big|_a^b = F(b) - F(a)$.
- A different choice of $c$ changes $F$ by a constant, which cancels in $F(b) - F(a)$.

**Example:**
- $\int_0^x t^n \, dt = \frac{x^{n+1}}{n+1}$ (Theorem 1.15)
- $\int_a^b t^n \, dt = \frac{b^{n+1} - a^{n+1}}{n+1}$

### 2.12.4 Geometric Interpretation

- For $f \ge 0$: $A(x)$ equals the area under $f$ from $a$ to $x$.
- For $f$ with both signs: $A(x)$ = (area above $x$-axis) 鈭?(area below $x$-axis).

### 2.12.5 Monotonicity of $A(x)$

- If $f \ge 0$ on $[a, b]$, then $A$ is **increasing**:
  $$
  A(y) - A(x) = \int_x^y f(t) \, dt \ge 0 \quad (x \le y)
  $$

### 2.12.6 Convexity and Concavity

**Definition (Convex function):**
- $g$ is **convex** on $[a, b]$ if for all $x, y \in [a, b]$ and $0 < \alpha < 1$:
  $$
  g(z) \le \alpha g(y) + (1 - \alpha)g(x), \quad \text{where } z = \alpha y + (1 - \alpha)x
  $$
  (Equation 2.22)
- $g$ is **concave** if the reverse inequality holds.
- **Geometric meaning**: For convex $g$, the chord lies above the graph; for concave $g$, the chord lies below.

**Theorem 2.9:**
- Let $A(x) = \int_a^x f(t) \, dt$. Then:
  - $A$ is **convex** on intervals where $f$ is **increasing**.
  - $A$ is **concave** on intervals where $f$ is **decreasing**.

**Proof Sketch:**
1. For $f$ increasing, choose $x < y$ and $z = \alpha y + (1 - \alpha)x$.
2. Need to show: $(1 - \alpha)\int_x^z f \le \alpha\int_z^y f$.
3. Since $f$ is increasing: $f(t) \le f(z)$ on $[x, z]$ and $f(z) \le f(t)$ on $[z, y]$.
4. Integrating: $\int_x^z f \le f(z)(z - x)$ and $f(z)(y - z) \le \int_z^y f$.
5. Using $(1 - \alpha)(z - x) = \alpha(y - z)$, the inequality follows.

**Example:**
- $\cos x$ decreases on $[0, \pi]$, so $\sin x = \int_0^x \cos t \, dt$ is **concave** on $[0, \pi]$.
- $\cos x$ increases on $[\pi, 2\pi]$, so $\sin x$ is **convex** on $[\pi, 2\pi]$.

### 2.12.7 Integral of a Step Function is Piecewise Linear

- Where $f$ is constant, $A(x)$ is linear.
- Example: $f(x) = [x]$ (greatest-integer function) $\implies A(x) = \int_0^x [t] \, dt$ is piecewise linear.
- The indefinite integral "smooths out" jumps 鈥?$A(x)$ is always continuous (proved in next chapter).

[<- Previous: 1. The Concepts of Integral Calculus](01-the-concepts-of-integral-calculus.md) | [Next: 3. Continuous Functions ->](03-continuous-functions.md)
