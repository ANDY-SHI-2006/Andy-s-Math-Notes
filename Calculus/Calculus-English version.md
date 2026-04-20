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


## 1.6 Properties of the Integral of a Step Function

### 1.6.1 Additive Property

$$
\int_a^b \bigl[s(x) + t(x)\bigr] \, dx = \int_a^b s(x) \, dx + \int_a^b t(x) \, dx.
$$

### 1.6.2 Homogeneous Property

For every real $c$:

$$
\int_a^b c \cdot s(x) \, dx = c \int_a^b s(x) \, dx.
$$

### 1.6.3 Linearity Property

Combining the above two properties, for every real $c_1, c_2$:

$$
\int_a^b \bigl[c_1 s(x) + c_2 t(x)\bigr] \, dx = c_1 \int_a^b s(x) \, dx + c_2 \int_a^b t(x) \, dx.
$$

### 1.6.4 Comparison Theorem

If $s(x) < t(x)$ for every $x$ in $[a, b]$, then:

$$
\int_a^b s(x) \, dx < \int_a^b t(x) \, dx.
$$

### 1.6.5 Additivity with Respect to the Interval

If $a < c < b$:

$$
\int_a^c s(x) \, dx + \int_c^b s(x) \, dx = \int_a^b s(x) \, dx.
$$

### 1.6.6 Invariance under Translation

For every real $c$:

$$
\int_a^b s(x) \, dx = \int_{a+c}^{b+c} s(x - c) \, dx.
$$

### 1.6.7 Expansion or Contraction of the Interval

For every $k > 0$:

$$
\int_{ka}^{kb} s\!\left(\frac{x}{k}\right) dx = k \int_a^b s(x) \, dx.
$$

### 1.6.8 Reversed Limits and Reflection

$$
\int_b^a s(x) \, dx = -\int_a^b s(x) \, dx \quad (a < b), \qquad \int_a^a s(x) \, dx = 0.
$$

By combining with expansion for $k = -1$, we obtain the **reflection property**:

$$
\int_a^b s(x) \, dx = \int_{-b}^{-a} s(-x) \, dx.
$$


## 1.7 Other Notations for Integrals

### 1.7.1 Dummy Variables

The integration variable is a **dummy variable** — it plays no essential role. Any letter will do:

$$
\int_a^b s(x)\,dx = \int_a^b s(t)\,dt = \int_a^b s(u)\,du.
$$

### 1.7.2 Abbreviated Notation

Some authors omit the dummy variable and write simply:

$$
\int_a^b s.
$$

This makes clearer that the integral depends only on the **function $s$** and the **interval $[a,b]$**.

| Pros | Cons |
|------|------|
| Simpler formulas (e.g. $\int_a^b (s+t) = \int_a^b s + \int_a^b t$) | Awkward for substitution theorems |

### 1.7.3 Leibniz Notation

The symbol $dx$ may seem superfluous now, but it becomes an extremely useful computational device for routine integral calculations.


## 1.8 The Integral of More General Functions

### 1.8.1 Motivation — Archimedes' Method

To define the integral for a general function $f$ on $[a, b]$, we approximate $f$ from **below** and **above** by step functions $s$ and $t$:

$$
s(x) \le f(x) \le t(x).
$$

By the comparison theorem:

$$
\int_a^b s(x) \, dx \le \int_a^b t(x) \, dx.
$$

If there is **one and only one** number $I$ satisfying:

$$
\int_a^b s(x) \, dx \le I \le \int_a^b t(x) \, dx
$$

for **every** such pair $(s, t)$, then $I$ is defined to be the integral of $f$.

### 1.8.2 Boundedness Requirement

Not every function can be surrounded by step functions. For example:

$$
f(x) = \frac{1}{x} \quad (x \neq 0), \qquad f(0) = 0
$$

is **unbounded** near the origin, so it cannot be approximated from above on any interval containing $0$.

Therefore we first restrict to **bounded functions** on $[a, b]$: there exists $M > 0$ such that:

$$
|f(x)| \le M \quad \text{for all } x \in [a, b].
$$

### 1.8.3 Definition of the Integral

**Definition.** Let $f$ be defined and bounded on $[a, b]$. If there is one and only one number $I$ such that:

$$
\int_a^b s(x) \, dx \le I \le \int_a^b t(x) \, dx
$$

for every pair of step functions $s, t$ with $s \le f \le t$ on $[a, b]$, then this number $I$ is called the **integral of $f$ from $a$ to $b$**, denoted:

$$
\int_a^b f(x) \, dx \quad \text{or} \quad \int_a^b f.
$$

When such an $I$ exists, $f$ is said to be **integrable** on $[a, b]$.

### 1.8.4 Terminology and Conventions

| Term | Meaning |
|------|---------|
| **Integrand** | The function $f$ being integrated |
| **Limits of integration** | The numbers $a$ and $b$ |
| **Interval of integration** | The interval $[a, b]$ |

We also define:

$$
\int_b^a f(x) \, dx = -\int_a^b f(x) \, dx \quad (a < b), \qquad \int_a^a f(x) \, dx = 0.
$$



## 1.9 Upper and Lower Integrals

### 1.9.1 The Sets S and T

Assume $f$ is bounded on $[a, b]$. Let $s$ and $t$ be step functions with $s \le f \le t$.

Define:

- $S = \left\{\displaystyle\int_a^b s(x)\,dx \;\bigg|\; s \le f\right\}$  
  (all lower approximations)
- $T = \left\{\displaystyle\int_a^b t(x)\,dx \;\bigg|\; f \le t\right\}$  
  (all upper approximations)

Both sets are nonempty because $f$ is bounded.

### 1.9.2 The Inequality Chain

If $s \le f \le t$, then by the comparison theorem:

$$
\int_a^b s(x)\,dx \le \int_a^b t(x)\,dx.
$$

Hence every number in $S$ is less than every number in $T$. Therefore $S$ has a supremum, $T$ has an infimum, and:

$$
\int_a^b s(x)\,dx \le \sup S \le \inf T \le \int_a^b t(x)\,dx
$$

for all $s, t$ with $s \le f \le t$.

### 1.9.3 Lower and Upper Integrals

The number $\sup S$ is called the **lower integral** of $f$, denoted $I(f)$.

The number $\inf T$ is called the **upper integral** of $f$, denoted $\bar{I}(f)$.

Thus:

$$
I(f) = \sup\left\{\int_a^b s(x)\,dx \;\bigg|\; s \le f\right\}, \qquad
\bar{I}(f) = \inf\left\{\int_a^b t(x)\,dx \;\bigg|\; f \le t\right\}.
$$

### 1.9.4 Integrability Criterion

**Theorem 1.9.** Every function $f$ which is bounded on $[a, b]$ has a lower integral $I(f)$ and an upper integral $\bar{I}(f)$ satisfying:

$$
\int_a^b s(x)\,dx \le I(f) \le \bar{I}(f) \le \int_a^b t(x)\,dx
$$

for all step functions $s$ and $t$ with $s \le f \le t$. The function $f$ is integrable on $[a, b]$ if and only if its upper and lower integrals are equal, in which case:

$$
\int_a^b f(x)\,dx = I(f) = \bar{I}(f).
$$

## 1.10 The Area of an Ordinate Set Expressed as an Integral

### 1.10.1 Introduction

We already know that for a nonnegative step function, the area of its ordinate set equals its integral. We now show the same holds for any integrable nonnegative function.

Recall: the ordinate set of a nonnegative function $f$ over $[a, b]$ is:

$$
Q = \{(x, y) \mid a \le x \le b, \; 0 \le y \le f(x)\}.
$$

### 1.10.2 Integrability of the Ordinate Set

Let $f$ be a nonnegative function, integrable on $[a, b]$, and let $Q$ be its ordinate set. Then $Q$ is **measurable** and its area is:

$$
a(Q) = \int_a^b f(x)\,dx.
$$

### 1.10.3 Proof Sketch

Let $S$ and $T$ be step regions with $S \subseteq Q \subseteq T$. Then there exist step functions $s$ and $t$ with $s \le f \le t$ such that:

$$
a(S) = \int_a^b s(x)\,dx, \qquad a(T) = \int_a^b t(x)\,dx.
$$

Since $f$ is integrable, $I = \int_a^b f(x)\,dx$ is the **only** number satisfying:

$$
\int_a^b s(x)\,dx \le I \le \int_a^b t(x)\,dx
$$

for all such $s, t$. Hence $I$ is also the only number with $a(S) \le I \le a(T)$ for all step regions $S \subseteq Q \subseteq T$. By the **exhaustion property**, $Q$ is measurable and $a(Q) = I$.

### 1.10.4 Null Set Property of the Graph

Let $Q$ be the ordinate set of Theorem 1.10, and let $Q'$ be the set with the graph of $f$ removed:

$$
Q' = \{(x, y) \mid a \le x \le b, \; 0 \le y < f(x)\}.
$$

The same argument shows $Q'$ is measurable with $a(Q') = a(Q)$. By the **difference property**:

$$
a(Q - Q') = a(Q) - a(Q') = 0.
$$

**Theorem 1.11.** Let $f$ be a nonnegative function, integrable on $[a, b]$. Then the **graph** of $f$:

$$
\{(x, y) \mid a \le x \le b, \; y = f(x)\}
$$

is measurable and has **area equal to 0**.


## 1.11 Informal Remarks on the Theory and Technique of Integration

### 1.11.1 Two Fundamental Questions

Two fundamental questions arise at this stage:

1. **Theory of Integration**: Which bounded functions are integrable?
2. **Technique of Integration**: Given that a function $f$ is integrable, how do we compute $\int_a^b f(x)\,dx$?

A complete answer to question (1) lies beyond the scope of an introductory course. Instead, we shall give partial answers which require only elementary ideas.

### 1.11.2 Monotonic Functions

First we introduce an important class of functions known as **monotonic functions**. In the following section we define these functions and give a number of examples. Then we prove that **all bounded monotonic functions are integrable**.

Fortunately, most of the functions that occur in practice are monotonic or sums of monotonic functions, so the results of this miniature theory of integration are quite comprehensive.

### 1.11.3 Technique of Integration

The discussion of "Technique of Integration" begins in Section 1.23, where we calculate the integral $\int_0^b x^p\,dx$ when $p$ is a positive integer. Then we develop general properties of the integral, such as **linearity** and **additivity**, and show how these properties help us to extend our knowledge of integrals of specific functions.

## 1.12 Monotonic and Piecewise Monotonic Functions

### 1.12.1 Definitions

Let $f$ be defined on a set $S$.

| Term | Condition for all $x < y$ in $S$ |
|------|--------------------------------------|
| **Increasing** | $f(x) \le f(y)$ |
| **Strictly increasing** | $f(x) < f(y)$ |
| **Decreasing** | $f(x) \ge f(y)$ |
| **Strictly decreasing** | $f(x) > f(y)$ |

A function is **monotonic** on $S$ if it is either increasing or decreasing on $S$.
A function is **strictly monotonic** if it is strictly increasing or strictly decreasing.

### 1.12.2 Piecewise Monotonic Functions

A function $f$ is **piecewise monotonic** on $[a, b]$ if there exists a partition $P$ of $[a, b]$ such that $f$ is monotonic on each open subinterval of $P$.

In particular, step functions are piecewise monotonic.

### 1.12.3 Examples

**Example 1 — The power functions.** Let $p$ be a positive integer and $f(x) = x^p$. Then $f$ is **strictly increasing** on the nonnegative real axis (since $0 \le x < y \implies x^p < y^p$). It is piecewise monotonic on every finite interval.

**Example 2 — The square-root function.** Let $f(x) = \sqrt{x}$ for $x \ge 0$. Then $f$ is **strictly increasing** on the nonnegative real axis, since for $0 \le x < y$:

$$
\sqrt{y} - \sqrt{x} = \frac{y - x}{\sqrt{y} + \sqrt{x}} > 0.
$$

**Example 3 — The semicircle function.** Let $g(x) = \sqrt{r^2 - x^2}$ for $-r \le x \le r$. Then $g$ is **strictly increasing** on $[-r, 0]$ and **strictly decreasing** on $[0, r]$. Hence $g$ is piecewise monotonic on $[-r, r]$.


## 1.13 Integrability of Bounded Monotonic Functions

### 1.13.1 Theorem 1.12

**Theorem 1.12.** If $f$ is monotonic on a closed interval $[a, b]$, then $f$ is integrable on $[a, b]$.

### 1.13.2 Proof Sketch (Increasing Case)

We prove the theorem for increasing functions; the decreasing case is analogous.

Let $I(f)$ and $\bar{I}(f)$ denote the lower and upper integrals of $f$. We shall prove that $I(f) = \bar{I}(f)$.

Let $n$ be a positive integer and partition $[a, b]$ into $n$ **equal** subintervals $[x_{k-1}, x_k]$ with:

$$
x_k - x_{k-1} = \frac{b - a}{n} \quad \text{for each } k = 1, 2, \dots, n.
$$

Define step functions $s_n$ and $t_n$ by:

$$
s_n(x) = f(x_{k-1}), \qquad t_n(x) = f(x_k) \quad \text{if } \; x_{k-1} < x < x_k.
$$

At the subdivision points, define $s_n$ and $t_n$ so that $s_n \le f \le t_n$ throughout $[a, b]$.

Then:

$$
\int_a^b t_n(x)\,dx - \int_a^b s_n(x)\,dx = \sum_{k=1}^{n} \bigl[f(x_k) - f(x_{k-1})\bigr] \frac{b-a}{n} = \frac{(b-a)[f(b) - f(a)]}{n},
$$

where the last equality follows from the **telescoping property**.

Since:

$$
\int_a^b s_n \le I(f) \le \bar{I}(f) \le \int_a^b t_n,
$$

we obtain:

$$
0 \le \bar{I}(f) - I(f) \le \int_a^b t_n - \int_a^b s_n = \frac{(b-a)[f(b) - f(a)]}{n}.
$$

This holds for **every** integer $n \ge 1$. Letting $n \to \infty$, the right-hand side tends to $0$. Therefore:

$$
\bar{I}(f) = I(f),
$$

which proves that $f$ is integrable on $[a, b]$.

## 1.14 Calculation of the Integral of a Bounded Monotonic Function

### 1.14.1 Theorem 1.13 — Increasing Functions

**Theorem 1.13.** Assume $f$ is increasing on $[a, b]$. Let $x_k = a + k\,\dfrac{b-a}{n}$ for $k = 0, 1, \dots, n$. If $I$ is any number satisfying:

$$
\frac{b-a}{n} \sum_{k=0}^{n-1} f(x_k) \le I \le \frac{b-a}{n} \sum_{k=1}^{n} f(x_k)
$$

for every integer $n \ge 1$, then:

$$
I = \int_a^b f(x)\,dx.
$$

### 1.14.2 Proof Sketch

Let $s_n$ and $t_n$ be the special approximating step functions from the proof of Theorem 1.12 (uniform partition into $n$ equal parts). Then:

$$
\int_a^b s_n(x)\,dx \le I \le \int_a^b t_n(x)\,dx
$$

for every $n \ge 1$. But $\int_a^b f(x)\,dx$ satisfies the same inequalities. Using Equation (1.8):

$$
0 \le \Bigl|I - \int_a^b f(x)\,dx\Bigr| \le \frac{C}{n}
$$

for every $n \ge 1$. Letting $n \to \infty$ gives $I = \int_a^b f(x)\,dx$.

### 1.14.3 Theorem 1.14 — Decreasing Functions

**Theorem 1.14.** Assume $f$ is decreasing on $[a, b]$. Let $x_k = a + k\,\dfrac{b-a}{n}$ for $k = 0, 1, \dots, n$. If $I$ is any number satisfying:

$$
\frac{b-a}{n} \sum_{k=1}^{n} f(x_k) \le I \le \frac{b-a}{n} \sum_{k=0}^{n-1} f(x_k)
$$

for every integer $n \ge 1$, then:

$$
I = \int_a^b f(x)\,dx.
$$


## 1.15 Calculation of the Integral $\int_0^b x^p \, dx$

### 1.15.1 Theorem 1.15

If $p$ is a positive integer and $b > 0$, we have:

$$
\int_0^b x^p \, dx = \frac{b^{p+1}}{p+1}.
$$

The integral exists because the integrand $x^p$ is bounded and increasing on $[0, b]$.

### 1.15.2 Proof

We use the inequalities:

$$
\sum_{k=1}^{n-1} k^p < \frac{n^{p+1}}{p+1} < \sum_{k=1}^{n} k^p,
$$

valid for every integer $n \ge 1$ and $p \ge 1$ (provable by mathematical induction).

Multiplying by $\dfrac{b^{p+1}}{n^{p+1}}$:

$$
\frac{b}{n} \sum_{k=1}^{n-1} \left(\frac{kb}{n}\right)^p < \frac{b^{p+1}}{p+1} < \frac{b}{n} \sum_{k=1}^{n} \left(\frac{kb}{n}\right)^p.
$$

Let $f(x) = x^p$ and $x_k = \dfrac{kb}{n}$ for $k = 0, 1, \dots, n$. Then:

$$
\frac{b}{n} \sum_{k=0}^{n-1} f(x_k) < \frac{b^{p+1}}{p+1} < \frac{b}{n} \sum_{k=1}^{n} f(x_k).
$$

These are exactly the inequalities (1.9) of **Theorem 1.13** with $a = 0$ and $I = \dfrac{b^{p+1}}{p+1}$. Therefore:

$$
\int_0^b x^p \, dx = \frac{b^{p+1}}{p+1}.
$$

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
