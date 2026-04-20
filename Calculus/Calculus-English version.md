# 1. The Concepts of Integral Calculus

## 1.1 The Concept of Area as a Set Function

### 1.1.1 Introduction

Area is defined axiomatically: we postulate a set of fundamental properties and build the theory from them, just as Euclid did for geometry.

### 1.1.2 Set Functions and Measurable Sets

An **area function** $a$ assigns a real number $a(S)$ to each set $S$ in a collection of plane sets. Such a function (domain = sets, range = real numbers) is called a **set function**.

Sets to which an area can be assigned are called **measurable sets**; their collection is denoted $\mathscr{M}$.

- **Rectangle**: any set congruent to $\{(x, y) \mid 0 \le x \le h, \; 0 \le y \le k\}$, with area $hk$.
- **Step region**: finite union of adjacent rectangles on the $x$-axis.
- **Ordinate set**: region under the graph of a nonnegative function (approximated by inner/outer step regions).

### 1.1.3 Axioms of Area

We assume a class $\mathscr{M}$ and a set function $a$ satisfying:

| Axiom | Statement |
|-------|-----------|
| **1. Nonnegative** | $a(S) \ge 0$ for all $S \in \mathscr{M}$. |
| **2. Additive** | $S, T \in \mathscr{M} \implies S \cup T, S \cap T \in \mathscr{M}$ and $a(S \cup T) = a(S) + a(T) - a(S \cap T)$. |
| **3. Difference** | $S, T \in \mathscr{M},\; S \subseteq T \implies T - S \in \mathscr{M}$ and $a(T - S) = a(T) - a(S)$. |
| **4. Congruence** | $S \in \mathscr{M},\; T \cong S \implies T \in \mathscr{M}$ and $a(S) = a(T)$. |
| **5. Scale** | Every rectangle $R \in \mathscr{M}$ with edge lengths $h, k$ has $a(R) = hk$. |
| **6. Exhaustion** | If $S \subseteq Q \subseteq T$ for step regions $S, T$ and **only one** number $c$ satisfies $a(S) \le c \le a(T)$ for all such pairs, then $Q \in \mathscr{M}$ and $a(Q) = c$. |

### 1.1.4 Consequences

- **Monotone property**: $S \subseteq T \implies a(S) \le a(T)$.
- **Empty set**: $\varnothing \in \mathscr{M}$ and $a(\varnothing) = 0$.
- Axiom 5 excludes the trivial case $a \equiv 0$.
- Axiom 6 (exhaustion) extends measurability from step regions to general ordinate sets.

## 1.2 Intervals and Ordinate Sets

### 1.2.1 Intervals

Let $a < b$. We define:

| Interval | Notation | Inequalities | Endpoints |
|----------|----------|--------------|-----------|
| **Closed** | $[a, b]$ | $a \le x \le b$ | both included |
| **Open** | $(a, b)$ | $a < x < b$ | neither included |
| **Half-open** | $(a, b]$ | $a < x \le b$ | right included |
| **Half-open** | $[a, b)$ | $a \le x < b$ | left included |

The open interval $(a, b)$ is also called the **interior** of $[a, b]$.

### 1.2.2 Ordinate Sets

Let $f$ be a nonnegative function whose domain is a closed interval $[a, b]$. The **ordinate set of $f$** is the region in the plane between the graph of $f$ and the $x$-axis, i.e. the collection of all points $(x, y)$ satisfying:

$$
a \le x \le b, \quad 0 \le y \le f(x).
$$

### 1.2.3 Role in Integration

Ordinate sets are the geometric objects whose areas we compute by means of integral calculus. We shall define the integral first for **step functions** and then use the integral of a step function to formulate the definition of integral for more general functions.


## 1.3 Partitions and Step Functions

### 1.3.1 Partitions

A **partition** $P$ of a closed interval $[a, b]$ is a collection of points:

$$
P = \{x_0, x_1, \dots, x_n\}, \quad a = x_0 < x_1 < \dots < x_n = b.
$$

It determines $n$ closed subintervals $[x_{k-1}, x_k]$ and $n$ open subintervals $(x_{k-1}, x_k)$.

### 1.3.2 Step Functions

A **step function** $s$ on $[a, b]$ is a function for which there exists a partition $P$ such that $s$ is **constant** on each open subinterval of $P$. That is, for each $k = 1, 2, \dots, n$, there is a real number $s_k$ such that:

$$
s(x) = s_k \quad \text{if } \; x_{k-1} < x < x_k.
$$

> **Note:** The values at the endpoints $x_{k-1}$ and $x_k$ are well-defined but need not equal $s_k$.

Step functions are also called **piecewise constant functions**.

### 1.3.3 Example — The Postage Function

A familiar example is the postage function: the cost of first-class mail is constant over each ounce interval and jumps at integer ounce marks.

### 1.3.4 Refinement

If $P'$ is obtained from $P$ by adjoining additional subdivision points, then $P'$ is called a **refinement** of $P$, and we say $P'$ is **finer** than $P$.

If a function is a step function relative to $P$, it is also a step function relative to every refinement $P'$.

## 1.4 Sum and Product of Step Functions

### 1.4.1 Sum of Step Functions

Let $s$ and $t$ be step functions on $[a, b]$, with partitions $P_1$ and $P_2$ respectively. Their **sum** is defined pointwise:

$$
u(x) = s(x) + t(x), \quad a \le x \le b.
$$

To show $u$ is a step function, take the **common refinement** $P$ of $P_1$ and $P_2$ (i.e. all points of $P_1$ together with all points of $P_2$). Since both $s$ and $t$ are constant on each open subinterval of $P$, so is $u$.

### 1.4.2 Product of Step Functions

The **product** $v = s \cdot t$, defined by:

$$
v(x) = s(x) \cdot t(x), \quad a \le x \le b,
$$

is also a step function, by the same argument using the common refinement.

### 1.4.3 Scalar Multiplication

If $t(x) = c$ is constant on $[a, b]$, then $v = c \cdot s$ is a step function obtained by multiplying each function value of $s$ by $c$.

## 1.5 The Definition of the Integral for Step Functions

### 1.5.1 Definition

Let $s$ be a step function on $[a, b]$, constant on the open subintervals of a partition $P = \{x_0, x_1, \dots, x_n\}$. Denote by $s_k$ the constant value on $(x_{k-1}, x_k)$. The **integral of $s$ from $a$ to $b$** is:

$$
\int_a^b s(x) \, dx = \sum_{k=1}^{n} s_k \cdot (x_k - x_{k-1}).
$$

> **Note:** The values of $s$ at the subdivision points are immaterial — they do not appear on the right-hand side.

### 1.5.2 Geometric Interpretation

For a nonnegative step function, the integral equals the **area of its ordinate set** (a finite union of rectangles). Vertical line segments at subdivision points have zero area and make no contribution.

### 1.5.3 Independence of Partition

The value of the integral is independent of the choice of partition, as long as $s$ is constant on its open subintervals. Inserting additional subdivision points splits one term $s_k(x_k - x_{k-1})$ into two terms whose sum is unchanged; by repeated insertion, the integral is the same for every refinement of $P$.

# 14. Calculus of Vector-Valued Functions

## 14.1 Vector-Valued Functions of a Real Variable

### 14.1.1 Definition

A **vector-valued function of a real variable** is a function whose domain is a set of real numbers and whose range is a subset of $n$-space $V_n$.

### 14.1.2 Notation

| Notation | Description |
|----------|-------------|
| Capital letters | $F, G, X, Y$, etc. |
| Small bold-face italic letters | $\mathbf{f}, \mathbf{g}$, etc. |
| Value at $t$ | $F(t)$ or $\mathbf{f}(t)$ |
| Domain | Usually an interval (finite or infinite) |

### 14.1.3 Example: Line in $n$-Space

The line through a point $P$ parallel to a nonzero vector $A$:

$$
X(t) = P + tA \quad \text{for all real } t
$$


## 14.2 Algebraic Operations and Components

### 14.2.1 Basic Operations

If $F$ and $G$ are vector-valued functions and $u$ is a real-valued function (all with a common domain), we define:

| Operation | Formula | Result Type |
|-----------|---------|-------------|
| **Addition** | $(F + G)(t) = F(t) + G(t)$ | Vector-valued |
| **Scalar multiplication** | $(uF)(t) = u(t)F(t)$ | Vector-valued |
| **Dot product** | $(F \cdot G)(t) = F(t) \cdot G(t)$ | Real-valued |
| **Cross product** (in 3-space) | $(F \times G)(t) = F(t) \times G(t)$ | Vector-valued |

### 14.2.2 Composition

If $F$ is vector-valued and $u$ is real-valued, the composition $G = F \circ u$ is:

$$
G(t) = F[u(t)]
$$

### 14.2.3 Component Functions

If $F$ has values in $V_n$, then each vector $F(t)$ has $n$ components:

$$
F(t) = \bigl(f_1(t), f_2(t), \dots, f_n(t)\bigr)
$$

We write $F = (f_1, \dots, f_n)$, where $f_k$ is the **$k$th component** of $F$.


## 14.3 Limits, Derivatives, and Integrals

### 14.3.1 Component-Wise Definitions

For a vector-valued function $F = (f_1, \dots, f_n)$, limit, derivative, and integral are defined **component by component**:

**Limit:**
$$
\lim_{t \to p} F(t) = \left( \lim_{t \to p} f_1(t), \dots, \lim_{t \to p} f_n(t) \right)
$$

**Derivative:**
$$
F'(t) = \bigl(f'_1(t), \dots, f'_n(t)\bigr)
$$

**Definite Integral:**
$$
\int_a^b F(t) \, dt = \left( \int_a^b f_1(t) \, dt, \dots, \int_a^b f_n(t) \, dt \right)
$$

> **Note:** These operations are valid whenever the components on the right are meaningful.

### 14.3.2 Continuity, Differentiability, and Integrability

$F$ is **continuous**, **differentiable**, or **integrable** on an interval if and only if **each component** of $F$ has the corresponding property on that interval.


## 14.4 Differentiation Rules

### 14.4.1 Theorem 14.1 — Basic Differentiation Formulas

If $F, G$, and $u$ are differentiable on an interval, then so are $F + G$, $uF$, and $F \cdot G$, and we have:

| Rule | Formula |
|------|---------|
| **Sum rule** | $(F + G)' = F' + G'$ |
| **Scalar product rule** | $(uF)' = u'F + uF'$ |
| **Dot product rule** | $(F \cdot G)' = F' \cdot G + F \cdot G'$ |
| **Cross product rule** (in $V_3$) | $(F \times G)' = F' \times G + F \times G'$ |

> **Key Point:** The cross product is **not commutative**, so the order of factors in $(F \times G)'$ must be preserved.

### 14.4.2 Theorem 14.2 — Constant Length Property

If a vector-valued function $F$ is differentiable and has **constant length** on an open interval $I$, then:

$$
F \cdot F' = 0 \quad \text{on } I
$$

**Interpretation:** $F(t)$ is **perpendicular** to $F'(t)$ for each $t \in I$.

**Proof Sketch:** Let $g(t) = \|F(t)\|^2 = F(t) \cdot F(t)$. Since $\|F(t)\|$ is constant, $g$ is constant, so $g' = 0$. Then:

$$
g' = F' \cdot F + F \cdot F' = 2F \cdot F' = 0 \implies F \cdot F' = 0
$$

### 14.4.3 Theorem 14.3 — Chain Rule for Vector-Valued Functions

Let $G = F \circ u$, where $F$ is vector-valued and $u$ is real-valued.

- If $u$ is continuous at $t$ and $F$ is continuous at $u(t)$, then $G$ is continuous at $t$.
- If the derivatives $u'(t)$ and $F'[u(t)]$ exist, then $G'(t)$ exists and:

$$
G'(t) = F'[u(t)] \, u'(t)
$$


## 14.5 Integration of Vector-Valued Functions

### 14.5.1 Theorem 14.4 — Linearity and Additivity

**Linearity:** If $F$ and $G$ are integrable on $[a, b]$, then so is $c_1 F + c_2 G$ for all scalars $c_1, c_2$, and:

$$
\int_a^b \bigl(c_1 F(t) + c_2 G(t)\bigr) \, dt = c_1 \int_a^b F(t) \, dt + c_2 \int_a^b G(t) \, dt
$$

**Additivity:** For each $c \in [a, b]$:

$$
\int_a^b F(t) \, dt = \int_a^c F(t) \, dt + \int_c^b F(t) \, dt
$$

### 14.5.2 Theorem 14.5 — First Fundamental Theorem of Calculus

Assume $F$ is a vector-valued function continuous on $[a, b]$. If $c \in [a, b]$, define the indefinite integral:

$$
A(x) = \int_c^x F(t) \, dt \quad \text{if } a \le x \le b
$$

Then $A'(x)$ exists, and:

$$
A'(x) = F(x) \quad \text{for each } x \in (a, b)
$$

### 14.5.3 Theorem 14.6 — Second Fundamental Theorem of Calculus

Assume the vector-valued function $F$ has a continuous derivative $F'$ on an open interval $I$. Then for each choice of $c$ and $x$ in $I$:

$$
F(x) = F(c) + \int_c^x F'(t) \, dt
$$

### 14.5.4 Theorem 14.7 — Dot Product with a Constant Vector

If $F = (f_1, \dots, f_n)$ is integrable on $[a, b]$, then for every vector $C = (c_1, \dots, c_n)$, the dot product $C \cdot F$ is integrable on $[a, b]$, and:

$$
C \cdot \int_a^b F(t) \, dt = \int_a^b C \cdot F(t) \, dt
$$

**Proof Sketch:**

$$
C \cdot \int_a^b F(t) \, dt = \sum_{i=1}^n c_i \int_a^b f_i(t) \, dt = \int_a^b \sum_{i=1}^n c_i f_i(t) \, dt = \int_a^b C \cdot F(t) \, dt
$$

### 14.5.5 Theorem 14.8 — Norm Inequality for Integrals

If $F$ and $\|F\|$ are integrable on $[a, b]$, then:

$$
\Bigl\| \int_a^b F(t) \, dt \Bigr\| \le \int_a^b \|F(t)\| \, dt
$$

**Proof Sketch:**

Let $C = \int_a^b F(t) \, dt$.

1. If $C = O$, the inequality holds trivially.
2. If $C \neq O$, apply Theorem 14.7 and the Cauchy-Schwarz inequality:

$$
\|C\|^2 = C \cdot C = C \cdot \int_a^b F(t) \, dt = \int_a^b C \cdot F(t) \, dt
$$

Then:

$$
\int_a^b C \cdot F(t) \, dt \le \int_a^b |C \cdot F(t)| \, dt \le \int_a^b \|C\| \, \|F(t)\| \, dt = \|C\| \int_a^b \|F(t)\| \, dt
$$

Dividing by $\|C\| > 0$ gives the result.


## 14.6 Summary Table

| Theorem | Statement |
|---------|-----------|
| **14.1** | Differentiation rules for sum, scalar product, dot product, and cross product |
| **14.2** | Constant length $\implies F \perp F'$ (i.e., $F \cdot F' = 0$) |
| **14.3** | Chain rule: $(F \circ u)'(t) = F'[u(t)] \, u'(t)$ |
| **14.4** | Linearity and additivity of the integral |
| **14.5** | First FTC: $\frac{d}{dx} \int_c^x F(t) \, dt = F(x)$ |
| **14.6** | Second FTC: $F(x) = F(c) + \int_c^x F'(t) \, dt$ |
| **14.7** | $C \cdot \int_a^b F = \int_a^b C \cdot F$ |
| **14.8** | $\bigl\| \int_a^b F \bigr\| \le \int_a^b \|F\|$ |


## 14.7 Key Takeaways

- Vector-valued calculus is performed **component-wise**.
- Most theorems from real-valued calculus (limits, continuity, differentiation, integration) extend naturally to vector-valued functions.
- The **dot product differentiation rule** and **constant length theorem** are crucial for studying curves and motion in physics.
- The **norm inequality** (Theorem 14.8) is analogous to the scalar triangle inequality for integrals.
