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

---

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

---

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

---

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

---

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

---

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

---

## 14.7 Key Takeaways

- Vector-valued calculus is performed **component-wise**.
- Most theorems from real-valued calculus (limits, continuity, differentiation, integration) extend naturally to vector-valued functions.
- The **dot product differentiation rule** and **constant length theorem** are crucial for studying curves and motion in physics.
- The **norm inequality** (Theorem 14.8) is analogous to the scalar triangle inequality for integrals.
