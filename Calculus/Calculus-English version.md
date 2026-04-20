# 1. The Concepts of Integral Calculus


## 1.6 The Concept of Area as a Set Function

### 1.6.1 Introduction and Motivation

When a mathematician attempts to develop a general theory encompassing many different concepts, he tries to isolate common properties which seem to be basic to each of the particular applications he has in mind. He then uses these properties as fundamental building blocks of his theory. Euclid used this process when he developed elementary geometry as a deductive system based on a set of axioms. We used the same process in our axiomatic treatment of the real number system, and we shall use it once more in our discussion of area.

### 1.6.2 Set Functions and Measurable Sets

When we assign an area to a plane region, we associate a number with a set $S$ in the plane. From a purely mathematical viewpoint, this means that we have a function $a$ (an **area function**) which assigns a real number $a(S)$ (the **area of $S$**) to each set $S$ in some given collection of sets. A function of this kind, whose domain is a collection of sets and whose function values are real numbers, is called a **set function**.

The basic problem is this: Given a plane set $S$, what area $a(S)$ shall we assign to $S$?

Our approach to this problem is to start with a number of properties we feel area should have and take these as **axioms for area**. Any set function which satisfies these axioms will be called an area function. To make certain we are not discussing an empty theory, it is necessary to show that an area function actually exists. We shall not attempt to do this here. Instead, we assume the existence of an area function and deduce further properties from the axioms.

Before we state the axioms for area, we will make a few remarks about the collection of sets in the plane to which an area can be assigned. These sets will be called **measurable sets**; the collection of all measurable sets will be denoted by $\mathscr{M}$. The axioms contain enough information about the sets in $\mathscr{M}$ to enable us to prove that all geometric figures arising in the usual applications of calculus are in $\mathscr{M}$ and that their areas can be calculated by integration.

One of the axioms (Axiom 5) states that every rectangle is measurable and that its area is the product of the lengths of its edges. The term "rectangle" as used here refers to any set congruent to a set of the form

$$
\{(x, y) \mid 0 \le x \le h, \; 0 \le y \le k\},
$$

where $h \ge 0$ and $k \ge 0$. The numbers $h$ and $k$ are called the lengths of the edges of the rectangle. We consider a line segment or a point to be a special case of a rectangle by allowing $h$ or $k$ (or both) to be zero.

From rectangles we can build up more complicated sets. The union of a finite collection of adjacent rectangles with their bases resting on the $x$-axis is called a **step region**. The axioms imply that each step region is measurable and that its area is the sum of the areas of the rectangular pieces.

The region $Q$ shown in Figure 1.15(a) is an example of an **ordinate set**. Its upper boundary is the graph of a nonnegative function. Axiom 6 will enable us to prove that many ordinate sets are measurable and that their areas can be calculated by approximating such sets by inner and outer step regions, as shown in Figure 1.15(b) and (c).

### 1.6.3 Axiomatic Definition of Area

We assume there exists a class $\mathscr{M}$ of measurable sets in the plane and a set function $a$, whose domain is $\mathscr{M}$, with the following properties:

| Axiom | Statement |
|-------|-----------|
| **1. Nonnegative property** | For each set $S$ in $\mathscr{M}$, we have $a(S) \ge 0$. |
| **2. Additive property** | If $S$ and $T$ are in $\mathscr{M}$, then $S \cup T$ and $S \cap T$ are in $\mathscr{M}$, and we have $a(S \cup T) = a(S) + a(T) - a(S \cap T)$. |
| **3. Difference property** | If $S$ and $T$ are in $\mathscr{M}$ with $S \subseteq T$, then $T - S$ is in $\mathscr{M}$, and we have $a(T - S) = a(T) - a(S)$. |
| **4. Invariance under congruence** | If a set $S$ is in $\mathscr{M}$ and if $T$ is congruent to $S$, then $T$ is also in $\mathscr{M}$ and we have $a(S) = a(T)$. |
| **5. Choice of scale** | Every rectangle $R$ is in $\mathscr{M}$. If the edges of $R$ have lengths $h$ and $k$, then $a(R) = hk$. |
| **6. Exhaustion property** | Let $Q$ be a set that can be enclosed between two step regions $S$ and $T$, so that $S \subseteq Q \subseteq T$. If there is one and only one number $c$ which satisfies the inequalities $a(S) \le c \le a(T)$ for all step regions $S$ and $T$ satisfying (1.1), then $Q$ is measurable and $a(Q) = c$. |

### 1.6.4 Interpretation of the Axioms

Axiom 1 simply states that the area of a plane measurable set is either a positive number or zero.

Axiom 2 tells us that when a set is formed from two pieces (which may overlap), the area of the union is the sum of the areas of the two parts minus the area of their intersection. In particular, if the intersection has zero area, the area of the whole is the sum of the areas of the two parts.

If we remove a measurable set $S$ from a larger measurable set $T$, Axiom 3 states that the remaining part, $T - S$, is measurable and its area is obtained by subtraction, $a(T - S) = a(T) - a(S)$. In particular, this axiom implies that the empty set $\varnothing$ is measurable and has zero area. Since $a(T - S) \ge 0$, Axiom 3 also implies the **monotone property**:

$$
a(S) \le a(T), \quad \text{for sets } S \text{ and } T \text{ in } \mathscr{M} \text{ with } S \subseteq T.
$$

In other words, a set which is part of another cannot have a larger area.

Axiom 4 assigns equal areas to sets having the same size and shape.

The first four axioms would be trivially satisfied if we assigned the number 0 as the area of every set in $\mathscr{M}$. Axiom 5 assigns a nonzero area to some rectangles and thereby excludes this trivial case.

Finally, Axiom 6 incorporates the Greek method of exhaustion; it enables us to extend the class of measurable sets from step regions to more general regions.

Axiom 5 assigns zero area to each line segment. Repeated use of the additive property shows that every step region is measurable and that its area is the sum of the areas of the rectangular pieces. Further elementary consequences of the axioms are discussed in the next set of exercises.
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
