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

### 1.3.3 Example 鈥?The Postage Function

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

> **Note:** The values of $s$ at the subdivision points are immaterial 鈥?they do not appear on the right-hand side.

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

The integration variable is a **dummy variable** 鈥?it plays no essential role. Any letter will do:

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

### 1.8.1 Motivation 鈥?Archimedes' Method

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

**Example 1 鈥?The power functions.** Let $p$ be a positive integer and $f(x) = x^p$. Then $f$ is **strictly increasing** on the nonnegative real axis (since $0 \le x < y \implies x^p < y^p$). It is piecewise monotonic on every finite interval.

**Example 2 鈥?The square-root function.** Let $f(x) = \sqrt{x}$ for $x \ge 0$. Then $f$ is **strictly increasing** on the nonnegative real axis, since for $0 \le x < y$:

$$
\sqrt{y} - \sqrt{x} = \frac{y - x}{\sqrt{y} + \sqrt{x}} > 0.
$$

**Example 3 鈥?The semicircle function.** Let $g(x) = \sqrt{r^2 - x^2}$ for $-r \le x \le r$. Then $g$ is **strictly increasing** on $[-r, 0]$ and **strictly decreasing** on $[0, r]$. Hence $g$ is piecewise monotonic on $[-r, r]$.

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

### 1.14.1 Theorem 1.13 鈥?Increasing Functions

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

### 1.14.3 Theorem 1.14 鈥?Decreasing Functions

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

## 1.16 The Basic Properties of the Integral

### 1.16.1 Theorem 1.16 鈥?Linearity

If $f$ and $g$ are integrable on $[a, b]$, then so is $c_1 f + c_2 g$ for all real $c_1, c_2$, and:

$$
\int_a^b \bigl[c_1 f(x) + c_2 g(x)\bigr] \, dx = c_1 \int_a^b f(x) \, dx + c_2 \int_a^b g(x) \, dx.
$$

By induction, for any finite sum:

$$
\int_a^b \sum_{k=1}^{n} c_k f_k(x) \, dx = \sum_{k=1}^{n} c_k \int_a^b f_k(x) \, dx.
$$

### 1.16.2 Theorem 1.17 鈥?Additivity with Respect to the Interval

If two of the following three integrals exist, the third also exists, and:

$$
\int_a^b f(x) \, dx + \int_b^c f(x) \, dx = \int_a^c f(x) \, dx.
$$

> **Note:** If $f$ is monotonic on $[a, b]$ and on $[b, c]$, then all three integrals exist.

### 1.16.3 Theorem 1.18 鈥?Invariance under Translation

If $f$ is integrable on $[a, b]$, then for every real $c$:

$$
\int_a^b f(x) \, dx = \int_{a+c}^{b+c} f(x - c) \, dx.
$$

### 1.16.4 Theorem 1.19 鈥?Expansion or Contraction

If $f$ is integrable on $[a, b]$, then for every real $k \neq 0$:

$$
\int_a^b f(x) \, dx = \frac{1}{k} \int_{ka}^{kb} f\!\left(\frac{x}{k}\right) dx.
$$

> **Note:** When $k = -1$, this is called the **reflection property**.

### 1.16.5 Theorem 1.20 鈥?Comparison Theorem

If $f$ and $g$ are integrable on $[a, b]$ and $g(x) \le f(x)$ for all $x \in [a, b]$, then:

$$
\int_a^b g(x) \, dx \le \int_a^b f(x) \, dx.
$$

In particular, if $f(x) \ge 0$ on $[a, b]$, then $\displaystyle\int_a^b f(x)\,dx \ge 0$.

## 1.17 Integration of Polynomials

### 1.17.1 Extending the Power Formula

From Section 1.15, for $b > 0$ and $p$ a positive integer:

$$
\int_0^b x^p \, dx = \frac{b^{p+1}}{p+1}. \tag{1.10}
$$

This also holds for $b = 0$. Using **Theorem 1.19** with $k = -1$, we can show (1.10) holds for negative $b$ as well:

$$
\int_0^{-b} x^p \, dx = -\int_0^b (-x)^p \, dx = (-1)^{p+1} \int_0^b x^p \, dx = \frac{(-b)^{p+1}}{p+1}.
$$

Then by additivity, for all real $a, b$ and any integer $p \ge 0$:

$$
\int_a^b x^p \, dx = \frac{b^{p+1} - a^{p+1}}{p+1}.
$$

### 1.17.2 Notation

The symbol $\displaystyle P(x)\,\Big|_a^b$ denotes $P(b) - P(a)$. Thus:

$$
\int_a^b x^p \, dx = \frac{x^{p+1}}{p+1}\,\Bigg|_a^b = \frac{b^{p+1} - a^{p+1}}{p+1}.
$$

### 1.17.3 Integrating Polynomials Term by Term

By linearity, the integral of any polynomial is obtained by integrating each term:

$$
\int_a^b \sum_{k=0}^{n} c_k x^k \, dx = \sum_{k=0}^{n} c_k \, \frac{b^{k+1} - a^{k+1}}{k+1}.
$$

**Example.** Compute $\displaystyle\int_1^3 (x^2 - 3x + 5)\,dx$:

$$
\int_1^3 (x^2 - 3x + 5)\,dx = \frac{x^3}{3}\Big|_1^3 - 3\,\frac{x^2}{2}\Big|_1^3 + 5x\Big|_1^3 = \frac{26}{3} - 12 + 10 = \frac{20}{3}.
$$

### 1.17.4 Piecewise Polynomial Integration

We can also integrate piecewise polynomial functions by splitting at sign changes. For example:

$$
\int_0^1 |x(2x-1)|\,dx = -\int_0^{1/2} x(2x-1)\,dx + \int_{1/2}^1 x(2x-1)\,dx = \frac{1}{4}.
$$

## 1.18 Proofs of the Basic Properties of the Integral

### 1.18.1 Linearity (Theorem 1.16)

We prove (A) $\int_a^b (f+g) = \int_a^b f + \int_a^b g$ and (B) $\int_a^b cf = c\int_a^b f$ separately.

**(A) Additivity.** Since $f, g$ are integrable:

$$
I(f) = \sup\left\{\int_a^b s_1 \;\bigg|\; s_1 \le f\right\}, \quad I(g) = \sup\left\{\int_a^b s_2 \;\bigg|\; s_2 \le g\right\}.
$$

By the additive property of the supremum:

$$
I(f) + I(g) = \sup\left\{\int_a^b s_1 + \int_a^b s_2 \;\bigg|\; s_1 \le f, \; s_2 \le g\right\}.
$$

If $s_1 \le f$ and $s_2 \le g$, then $s = s_1 + s_2$ is a step function below $f+g$, so:

$$
\int_a^b s_1 + \int_a^b s_2 = \int_a^b s \le I(f+g).
$$

Thus $I(f) + I(g) \le I(f+g)$. Similarly, using upper integrals:

$$
\bar{I}(f+g) \le \bar{I}(f) + \bar{I}(g) = I(f) + I(g).
$$

Since $I(f+g) \le \bar{I}(f+g)$, all inequalities become equalities, proving (A).

**(B) Homogeneity.** If $c > 0$, every step function below $cf$ has the form $cs$ where $s \le f$. Hence:

$$
I(cf) = \sup\left\{\int_a^b cs \;\bigg|\; s \le f\right\} = c \cdot I(f).
$$

Similarly $\bar{I}(cf) = c\bar{I}(f) = cI(f)$. The case $c < 0$ uses $\sup(cA) = c\inf(A)$.

### 1.18.2 Additivity with Respect to the Interval (Theorem 1.17)

Assume $a < b < c$ and $\int_a^b f$, $\int_b^c f$ exist. Let $I(f)$ and $\bar{I}(f)$ over $[a, c]$ denote the lower and upper integrals.

If $s_1 \le f$ on $[a, b]$ and $s_2 \le f$ on $[b, c]$, then the function $s$ equal to $s_1$ on $[a, b)$ and $s_2$ on $[b, c]$ is a step function below $f$ on $[a, c]$, and:

$$
\int_a^c s = \int_a^b s_1 + \int_b^c s_2.
$$

By the additive property of the supremum:

$$
I(f) = \sup\left\{\int_a^c s\right\} = \int_a^b f + \int_b^c f.
$$

Similarly $\bar{I}(f) = \int_a^b f + \int_b^c f$, proving the result.

### 1.18.3 Translation (Theorem 1.18)

Let $g(x) = f(x-c)$ on $[a+c, b+c]$. For any step function $s \le g$, define $s_1(x) = s(x+c)$ on $[a, b]$. Then $s_1 \le f$ and:

$$
\int_{a+c}^{b+c} s(x)\,dx = \int_a^b s_1(x)\,dx.
$$

Therefore:

$$
I(g) = \sup\left\{\int_{a+c}^{b+c} s\right\} = \sup\left\{\int_a^b s_1 \;\bigg|\; s_1 \le f\right\} = \int_a^b f(x)\,dx.
$$

Similarly $\bar{I}(g) = \int_a^b f$.

### 1.18.4 Expansion (Theorem 1.19)

Let $g(x) = f(x/k)$ on $[ka, kb]$ for $k > 0$. For any step function $s \le g$, define $s_1(x) = s(kx)$ on $[a, b]$. Then $s_1 \le f$ and by the expansion property for step functions:

$$
\int_{ka}^{kb} s(x)\,dx = k \int_a^b s_1(x)\,dx.
$$

Therefore:

$$
I(g) = \sup\left\{\int_{ka}^{kb} s\right\} = k \cdot \sup\left\{\int_a^b s_1 \;\bigg|\; s_1 \le f\right\} = k \int_a^b f(x)\,dx.
$$

Similarly $\bar{I}(g) = k\int_a^b f$.

### 1.18.5 Comparison (Theorem 1.20)

Assume $g \le f$ on $[a, b]$. If $s \le g$ and $t \ge f$, then $s \le t$, so $\int_a^b s \le \int_a^b t$. Hence:

$$
\int_a^b g = \sup\left\{\int_a^b s \;\bigg|\; s \le g\right\} \le \inf\left\{\int_a^b t \;\bigg|\; f \le t\right\} = \int_a^b f.
$$

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

# 3. Continuous Functions

## 3.1 Informal Description of Continuity

### 3.1.1 Intuitive Idea

- **Continuity** is one of the most important concepts in mathematics.
- Roughly: $f$ is continuous at $p$ if $f(x)$ is close to $f(p)$ whenever $x$ is near $p$.
- No sudden jumps in the values of a continuous function.

### 3.1.2 Types of Discontinuities

| Type | Description | Example |
|------|-------------|---------|
| **Jump discontinuity** | Left and right limits exist but differ | $f(x) = x - [x]$ at each integer |
| **Infinite discontinuity** | Function becomes unbounded | $f(x) = 1/x^2$ at $x = 0$ |

- **Figure 3.1(a)**: $f(x) = x - [x]$ has a jump at each integer.
  - $f(2) = 0$, but $x \to 2^-$ gives $f(x) \to 1 \neq f(2)$.
  - $f$ is **continuous from the right** at 2, but **discontinuous from the left**.
  - Continuity at a point requires both left and right continuity.

### 3.1.3 Historical Note

- Early calculus dealt almost exclusively with continuous functions.
- Discontinuous functions arose in physical problems (heat theory) in the late 18th century.
- **J. B. J. Fourier** (1758鈥?830) on heat theory forced mathematicians to examine continuity more carefully.
- A satisfactory definition was first formulated by **Augustin-Louis Cauchy** (1789鈥?857) in 1821, using the limit concept.

> "Continuity: Quality or state of being continuous. Continuous: Having continuity of parts."
> 鈥?Trying to learn continuity from a dictionary alone is like trying to learn Chinese with only a Chinese dictionary.

## 3.2 The Definition of the Limit of a Function

### 3.2.1 Limit Notation

- $\displaystyle\lim_{x \to p} f(x) = A$: "The limit of $f(x)$ as $x$ approaches $p$ is $A$."
- Alternative: $f(x) \to A$ as $x \to p$.
- $f$ need not be defined at $p$ itself.

### 3.2.2 Neighborhood of a Point

- **Definition**: Any open interval containing $p$ as its midpoint is a **neighborhood** of $p$.
- Notation: $N(p)$, $N_1(p)$, $N_2(p)$, etc.
- $N(p; r)$: neighborhood of radius $r > 0$, consisting of all $x$ with $|x - p| < r$.

### 3.2.3 Definition of Limit (Neighborhood Form)

$$
\lim_{x \to p} f(x) = A
$$

means: for every neighborhood $N_1(A)$, there exists some neighborhood $N_2(p)$ such that:

$$
f(x) \in N_1(A) \quad \text{whenever} \quad x \in N_2(p) \text{ and } x \neq p
$$
(Equation 3.1)

- $N_1(A)$ is chosen **first**: specifies how close $f(x)$ should be to $A$.
- $N_2(p)$ depends on $N_1(A)$: specifies how close $x$ should be to $p$.
- **Key**: for *every* $N_1(A)$, no matter how small, there is *some* $N_2(p)$.

### 3.2.4 Definition of Limit ($\epsilon$-$\delta$ Form)

- Radius of $N_1(A)$ = $\epsilon$ (epsilon); radius of $N_2(p)$ = $\delta$ (delta).
- Equivalent formulation:

$$
\lim_{x \to p} f(x) = A \iff \forall \epsilon > 0, \ \exists \delta > 0 \text{ such that } |f(x) - A| < \epsilon \text{ whenever } 0 < |x - p| < \delta
$$
(Equation 3.2)

### 3.2.5 Equivalent Limit Statements

The following are equivalent:

$$
\lim_{x \to p} f(x) = A, \qquad \lim_{x \to p} (f(x) - A) = 0, \qquad \lim_{x \to p} |f(x) - A| = 0
$$

Also equivalent:

$$
\lim_{x \to p} f(x) = A \iff \lim_{h \to 0} f(p + h) = A
$$

### 3.2.6 Examples

**Example 1 鈥?Constant function:**
- $f(x) = c$ for all $x$. Then $\displaystyle\lim_{x \to p} c = c$.

**Example 2 鈥?Identity function:**
- $f(x) = x$. Then $\displaystyle\lim_{x \to p} x = p$.

**Example 3 鈥?Greatest-integer function:**
- $f(x) = [x]$ at integer $p$:
  $$
  \lim_{x \to p^-} f(x) = p - 1, \qquad \lim_{x \to p^+} f(x) = p
  $$
  Left and right limits differ $\implies$ limit at $p$ does **not exist**.

**Example 4 鈥?$f(x) = 1/x^2$ at $x = 0$:**
- $f$ takes arbitrarily large values near 0.
- No real number $A$ can be the limit (violates (3.3) for any neighborhood).

**Example 5 鈥?Removable discontinuity:**
- $f(x) = 1$ for $x \neq 0$, $f(0) = 0$.
- $\displaystyle\lim_{x \to 0} f(x) = 1$ (both one-sided limits equal 1).
- Limit exists and equals 1, even though $f(0) = 0$.

### 3.2.7 One-Sided Limits

- **Right-hand limit**: $x \to p^+$ (through values $x > p$):
  $$
  \lim_{x \to p^+} f(x) = A
  $$
  means: for every $N_1(A)$, there exists $N_2(p)$ such that $f(x) \in N_1(A)$ whenever $x \in N_2(p)$ and $x > p$.
  (Equation 3.3)

- **Left-hand limit**: $x \to p^-$ (through values $x < p$): similarly defined.

- **Existence of limit**: $\displaystyle\lim_{x \to p} f(x) = A$ exists iff both one-sided limits exist and equal $A$.

## 3.3 The Definition of Continuity of a Function

### 3.3.1 Definition 鈥?Continuity at a Point

A function $f$ is **continuous at $p$** if:

1. $f$ is defined at $p$; and
2. $\displaystyle\lim_{x \to p} f(x) = f(p)$.

**Neighborhood formulation:**
- For every neighborhood $N_1[f(p)]$, there exists $N_2(p)$ such that:
  $$
  f(x) \in N_1[f(p)] \quad \text{whenever} \quad x \in N_2(p)
  $$
  (Equation 3.4)
- Note: $x \neq p$ is **not** required, since $f(p) \in N_1[f(p)]$ always.

**$\epsilon$-$\delta$ formulation:**
- For every $\epsilon > 0$, there exists $\delta > 0$ such that:
  $$
  |f(x) - f(p)| < \epsilon \quad \text{whenever} \quad |x - p| < \delta
  $$

### 3.3.2 Examples

**Example 1 鈥?Constant function:**
- $f(x) = c$. Then $\lim_{x \to p} c = c = f(p)$ for every $p$.
- **Constant functions are continuous everywhere.**

**Example 2 鈥?Identity function:**
- $f(x) = x$. Then $\lim_{x \to p} x = p = f(p)$ for every $p$.
- **The identity function is continuous everywhere.**

**Example 3 鈥?Greatest-integer function:**
- $f(x) = [x]$ is continuous at every non-integer point.
- At integers $p$: discontinuous (limit does not exist; jump discontinuity).
- However, $f$ is **continuous from the right** at each integer (right-hand limit equals $f(p)$).

**Example 4 鈥?Infinite discontinuity:**
- $f(x) = 1/x^2$ for $x \neq 0$, $f(0) = 0$.
- Discontinuous at 0; **infinite discontinuity** (function takes arbitrarily large values near 0).

**Example 5 鈥?Removable discontinuity:**
- $f(x) = 1$ for $x \neq 0$, $f(0) = 0$.
- Discontinuous at 0 because $f(0) \neq \lim_{x \to 0} f(x) = 1$.
- Could be "removed" by redefining $f(0) = 1$.
- **Jump discontinuities** (like $[x]$) cannot be removed by changing $f$ at a single point.

### 3.3.3 Types of Discontinuities Summary

| Type | Description | Example |
|------|-------------|---------|
| **Removable** | Limit exists but $\neq f(p)$ | $f(x) = 1$ ($x \neq 0$), $f(0) = 0$ |
| **Jump** | Left and right limits exist but differ | $f(x) = [x]$ at integers |
| **Infinite** | Function unbounded near $p$ | $f(x) = 1/x^2$ at $x = 0$ |

## 3.4 The Basic Limit Theorems. More Examples of Continuous Functions

### 3.4.1 Theorem 3.1 鈥?Basic Limit Rules

Let $\lim_{x \to p} f(x) = A$ and $\lim_{x \to p} g(x) = B$. Then:

| Rule | Formula |
|------|---------|
| **(i) Sum** | $\lim_{x \to p} [f(x) + g(x)] = A + B$ |
| **(ii) Difference** | $\lim_{x \to p} [f(x) - g(x)] = A - B$ |
| **(iii) Product** | $\lim_{x \to p} [f(x) \cdot g(x)] = A \cdot B$ |
| **(iv) Quotient** | $\lim_{x \to p} f(x)/g(x) = A/B$ \quad (if $B \neq 0$) |

- Special case of (iii): $\lim_{x \to p} [c \cdot g(x)] = c \cdot B$ (constant multiple).
- Proof is in Section 3.5.

### 3.4.2 Theorem 3.2 鈥?Continuity of Combinations

Let $f$ and $g$ be continuous at $p$. Then:
- $f + g$, $f - g$, $f \cdot g$ are continuous at $p$.
- $f/g$ is continuous at $p$ (if $g(p) \neq 0$).

**Proof:** Apply Theorem 3.1 with $A = f(p)$ and $B = g(p)$.

### 3.4.3 Example 1 鈥?Continuity of Polynomials

- $f(x) = x$ is continuous $\implies x^2 = x \cdot x$ is continuous (by product rule).
- By induction: $x^n$ is continuous for all positive integers $n$.
- $cx^n$ is continuous; sums of continuous functions are continuous.
- **Every polynomial** $p(x) = \sum_{k=0}^n c_k x^k$ is continuous at all points.

### 3.4.4 Example 2 鈥?Continuity of Rational Functions

- A **rational function** $r(x) = p(x)/q(x)$ (where $p, q$ are polynomials).
- Continuous wherever $q(x) \neq 0$.
- Example: $r(x) = 1/x$ is continuous everywhere except at $x = 0$.

### 3.4.5 Theorem 3.3 鈥?Squeezing Principle

Suppose $f(x) \le g(x) \le h(x)$ for all $x \neq p$ in some neighborhood $N(p)$, and:

$$
\lim_{x \to p} f(x) = \lim_{x \to p} h(x) = a
$$

Then:

$$
\lim_{x \to p} g(x) = a
$$

**Proof Sketch:**
1. Let $G(x) = g(x) - f(x) \ge 0$ and $H(x) = h(x) - f(x) \ge 0$.
2. Need to show $G(x) \to 0$ as $x \to p$, given $H(x) \to 0$.
3. For any neighborhood $N_1(0)$ of 0, since $H(x) \to 0$, there exists $N_2(p)$ such that $H(x) \in N_1(0)$ for $x \in N_2(p)$, $x \neq p$.
4. Since $0 \le G \le H$, we have $G(x) \in N_1(0)$ as well. Hence $G(x) \to 0$.

### 3.4.6 Theorem 3.4 鈥?Continuity of Indefinite Integrals

Assume $f$ is integrable on $[a, x]$ for every $x \in [a, b]$, and let:

$$
A(x) = \int_a^x f(t) \, dt
$$

Then $A$ is **continuous at each point of $[a, b]$** (one-sided continuity at endpoints).

**Proof Sketch:**
1. $A(x) - A(p) = \int_p^x f(t) \, dt$.
2. Since $f$ is bounded ($|f| \le M$ on $[a, b]$):
   $$-M|x - p| \le A(x) - A(p) \le M|x - p|$$
3. Apply squeezing principle as $x \to p$: $A(x) \to A(p)$.

### 3.4.7 Example 3 鈥?Continuity of Sine and Cosine

- $\sin x = \int_0^x \cos t \, dt$ $\implies$ sine is continuous everywhere (by Theorem 3.4).
- $\cos x = 1 - \int_0^x \sin t \, dt$ $\implies$ cosine is continuous everywhere.

### 3.4.8 Example 4 鈥?The Limit $\lim_{x \to 0} \frac{\sin x}{x} = 1$

From Section 2.5, for $0 < |x| < \pi/2$:

$$
0 < \cos x < \frac{\sin x}{x} < \frac{1}{\cos x}
$$

- As $x \to 0$: $\cos x \to 1$ (cosine is continuous at 0), so $1/\cos x \to 1$.
- By squeezing principle: $\displaystyle\lim_{x \to 0} \frac{\sin x}{x} = 1$.
- (Equation 3.6)
- Defining $f(x) = (\sin x)/x$ for $x \neq 0$ and $f(0) = 1$ makes $f$ continuous everywhere.

### 3.4.9 Example 5 鈥?Continuity of $x^r$ for Rational $r > 0$

- From Theorem 2.2: $\int_0^x t^{1/n} \, dt = \frac{x^{1+1/n}}{1 + 1/n}$ for $x > 0$, $n \ge 1$.
- By Theorems 3.4 and 3.1: $x^{1+1/n}$ is continuous for $x > 0$.
- Then $x^{1/n} = A(x)/x$ is continuous (quotient of continuous functions).
- By products: $x^{m/n}$ is continuous for any positive integers $m, n$.
- **Conclusion**: $f(x) = x^r$ is continuous for all $x > 0$ when $r$ is any positive rational number.
- At $x = 0$: right-hand continuity.

## 3.5 Proofs of the Basic Limit Theorems

### 3.5.1 Algebraic Tools

Two key properties of absolute values:
1. **Triangle inequality**: $|a + b| \le |a| + |b|$
2. **Product rule**: $|ab| = |a|\,|b|$

### 3.5.2 Proof of (i) and (ii) 鈥?Sum and Difference

**Reduction to zero limits:**
- Since $\lim_{x \to p} f(x) = A \iff \lim_{x \to p} [f(x) - A] = 0$, it suffices to prove (i) when $A = B = 0$.
- Note: $f(x) + g(x) - (A + B) = [f(x) - A] + [g(x) - B]$.

**Proof of (i) with $A = B = 0$:**
- Given $\epsilon > 0$:
  - Since $f(x) \to 0$, $\exists \delta_1 > 0$ such that $|f(x)| < \epsilon/2$ when $0 < |x - p| < \delta_1$.
  - Since $g(x) \to 0$, $\exists \delta_2 > 0$ such that $|g(x)| < \epsilon/2$ when $0 < |x - p| < \delta_2$.
- Let $\delta = \min(\delta_1, \delta_2)$. Then for $0 < |x - p| < \delta$:
  $$
  |f(x) + g(x)| \le |f(x)| + |g(x)| < \frac{\epsilon}{2} + \frac{\epsilon}{2} = \epsilon
  $$
- (Equation 3.7)

**Proof of (ii):** Entirely similar, using $|f(x) - g(x)| \le |f(x)| + |g(x)|$.

### 3.5.3 Proof of (iii) 鈥?Product

**Reduction to special case:**
- Write: $f(x)g(x) - AB = f(x)[g(x) - B] + B[f(x) - A]$.
- If (iii) holds when one limit is 0, each term on the right approaches 0, and by (i) the sum approaches 0.
- Thus it suffices to prove: if $f(x) \to A$ and $g(x) \to 0$, then $f(x)g(x) \to 0$.

**Proof of special case:**
- Given $\epsilon > 0$:
  - Since $f(x) \to A$, $\exists \delta_1 > 0$ such that $|f(x) - A| < 1$ when $0 < |x - p| < \delta_1$.
  - For such $x$: $|f(x)| = |f(x) - A + A| \le |f(x) - A| + |A| < 1 + |A|$.
  - Hence: $|f(x)g(x)| = |f(x)|\,|g(x)| < (1 + |A|)|g(x)|$.
    (Equations 3.11, 3.12)
  - Since $g(x) \to 0$, $\exists \delta_2 > 0$ such that $|g(x)| < \frac{\epsilon}{1 + |A|}$ when $0 < |x - p| < \delta_2$.
    (Equation 3.13)
- Let $\delta = \min(\delta_1, \delta_2)$. Then for $0 < |x - p| < \delta$:
  $$|f(x)g(x)| < (1 + |A|) \cdot \frac{\epsilon}{1 + |A|} = \epsilon$$
- (Equation 3.10)

### 3.5.4 Proof of (iv) 鈥?Quotient

**Reduction:**
- Write $\frac{f(x)}{g(x)} = \frac{f(x)}{B} \cdot \frac{B}{g(x)}$.
- By (iii), it suffices to prove $\frac{B}{g(x)} \to 1$, i.e., $\frac{1}{h(x)} \to 1$ where $h(x) = g(x)/B \to 1$.

**Proof that $1/h(x) \to 1$:**
- Given $\epsilon > 0$, we need $\delta > 0$ such that:
  $$\left|\frac{1}{h(x)} - 1\right| < \epsilon \quad \text{whenever} \quad 0 < |x - p| < \delta$$
  (Equation 3.14)
- Rewrite:
  $$\left|\frac{1}{h(x)} - 1\right| = \frac{|h(x) - 1|}{|h(x)|}$$
  (Equation 3.15)
- Since $h(x) \to 1$, choose $\delta > 0$ such that both hold when $0 < |x - p| < \delta$:
  $$|h(x) - 1| < \frac{\epsilon}{2} \quad \text{and} \quad |h(x) - 1| < \frac{1}{2}$$
  (Equation 3.16)
- The second inequality gives $h(x) > 1/2$, so $1/|h(x)| < 2$.
- Therefore:
  $$\frac{|h(x) - 1|}{|h(x)|} < 2 \cdot \frac{\epsilon}{2} = \epsilon$$
- This proves (3.14), completing the proof of (iv).

## 3.6 Composite Functions and Continuity

### 3.6.1 Definition of Composition

- The **composition** of $u$ and $v$ (in that order) is the function $f$ defined by:
  $$
  f(x) = u[v(x)] \quad \text{(read as "$u$ of $v$ of $x$")}
  $$
- Notation: $f = u(v)$ or $f = u \circ v$ (read as "$u$ circle $v$").
- To evaluate: first compute $v(x)$, then apply $u$ at $v(x)$.
- $f$ is defined only where $v(x)$ is in the domain of $u$.

**Examples:**
- $f(x) = \sin(x^2)$: $u(x) = \sin x$, $v(x) = x^2$, so $f = u \circ v$.
- $f(x) = \sqrt{1 - x^2}$: $u(x) = \sqrt{x}$, $v(x) = 1 - x^2$.
  - $v$ defined for all $x$, but $u$ requires $x \ge 0$.
  - So $f$ is defined only where $1 - x^2 \ge 0$, i.e., $x^2 \le 1$.

### 3.6.2 Properties of Composition

- **Associative law** (Equation 3.17):
  $$
  u \circ (v \circ w) = (u \circ v) \circ w
  $$
- **Commutative law does NOT hold** in general:
  - $u(x) = \sin x$, $v(x) = x^2$:
    - $u \circ v$: $f(x) = \sin(x^2)$
    - $v \circ u$: $g(x) = (\sin x)^2 = \sin^2 x$
  - These are different functions.

### 3.6.3 Theorem 3.5 鈥?Continuity of Composites

If $v$ is continuous at $p$ and $u$ is continuous at $q = v(p)$, then $f = u \circ v$ is continuous at $p$.

**Proof:**
1. Since $u$ is continuous at $q$: for every $N_1[u(q)]$, there exists $N_2(q)$ such that:
   $$
   u(y) \in N_1[u(q)] \quad \text{whenever} \quad y \in N_2(q)
   $$
   (Equation 3.18)
2. Since $v$ is continuous at $p$ ($q = v(p)$): for $N_2(q)$, there exists $N_3(p)$ such that:
   $$
   v(x) \in N_2(q) \quad \text{whenever} \quad x \in N_3(p)
   $$
   (Equation 3.19)
3. Let $y = v(x)$. Combining (3.18) and (3.19): for every $N_1[u(v(p))] = N_1[f(p)]$, there exists $N_3(p)$ such that:
   $$
   f(x) = u[v(x)] \in N_1[f(p)] \quad \text{whenever} \quad x \in N_3(p)
   $$
4. Hence $f$ is continuous at $p$.

### 3.6.4 Examples

**Example 1:**
- $f(x) = \sin(x^2)$ 鈥?composition of two everywhere-continuous functions.
- **$f$ is continuous everywhere.**

**Example 2:**
- $f(x) = \sqrt{1 - x^2} = u[v(x)]$, where $u(x) = \sqrt{x}$, $v(x) = 1 - x^2$.
- $v$ continuous everywhere; $u$ continuous for $x \ge 0$.
- **$f$ is continuous where $v(x) \ge 0$, i.e., $x^2 \le 1$.**

## 3.7 Bolzano's Theorem for Continuous Functions

### 3.7.1 Introduction

- This section discusses special properties of continuous functions that appear geometrically obvious but require rigorous proof.
- Most proofs rely on the **least-upper-bound axiom** for the real number system.
- **Bernard Bolzano** (1781鈥?848), a Catholic priest, was among the first to recognize that "obvious" statements about continuous functions need proof.
- His work was published posthumously in 1850 in *Paradoxien des Unendlichen*; this theorem first appeared in 1817.

### 3.7.2 Theorem 3.6 鈥?Bolzano's Theorem

Let $f$ be continuous at each point of a closed interval $[a, b]$ and assume $f(a)$ and $f(b)$ have **opposite signs**. Then there exists at least one $c \in (a, b)$ such that:

$$
f(c) = 0
$$

- **Geometric meaning**: A continuous curve crossing from below to above the $x$-axis must intersect the axis somewhere in between.

### 3.7.3 Theorem 3.7 鈥?Sign-Preserving Property

Let $f$ be continuous at $c$ and $f(c) \neq 0$. Then there exists an interval $(c - \delta, c + \delta)$ in which $f$ has the **same sign** as $f(c)$.

**Proof:**
- Suppose $f(c) > 0$. By continuity, for every $\epsilon > 0$, there exists $\delta > 0$ such that:
  $$
  f(c) - \epsilon < f(x) < f(c) + \epsilon \quad \text{whenever} \quad c - \delta < x < c + \delta
  $$
  (Equation 3.20)
- Take $\epsilon = f(c)/2$ (positive). Then:
  $$
  \frac{1}{2}f(c) < f(x) < \frac{3}{2}f(c)
  $$
- Hence $f(x) > 0$ in this interval.
- If $f(c) < 0$, take $\epsilon = -f(c)/2$; same conclusion.

> **Note:** If only one-sided continuity holds, there is a corresponding one-sided interval $[c, c + \delta)$ or $(c - \delta, c]$ with the same sign property.

### 3.7.4 Proof of Bolzano's Theorem

**Setup:**
- Assume $f(a) < 0$ and $f(b) > 0$ (WLOG).
- Let $S = \{x \in [a, b] \mid f(x) \le 0\}$.
- $S$ is nonempty ($a \in S$) and bounded above (by $b$), so $c = \sup S$ exists.

**Show $f(c) = 0$ by eliminating the other two cases:**

**Case 1: $f(c) > 0$**
- By Theorem 3.7, $f > 0$ on some interval $(c - \delta, c + \delta)$ (or $(c - \delta, c]$ if $c = b$).
- Then no points of $S$ lie to the right of $c - \delta$.
- So $c - \delta$ is an upper bound for $S$, contradicting $c = \sup S$ (least upper bound).
- **Impossible.**

**Case 2: $f(c) < 0$**
- By Theorem 3.7, $f < 0$ on some interval $(c - \delta, c + \delta)$ (or $[c, c + \delta)$ if $c = a$).
- Then $f(x) < 0$ for some $x > c$, so $x \in S$ and $x > c$.
- This contradicts $c$ being an upper bound for $S$.
- **Impossible.**

**Conclusion:**
- The only remaining possibility is $f(c) = 0$.
- Also $a < c < b$ because $f(a) < 0$ and $f(b) > 0$.

## 3.8 The Intermediate-Value Theorem for Continuous Functions

### 3.8.1 Theorem 3.8 鈥?Intermediate-Value Theorem

Let $f$ be continuous at each point of a closed interval $[a, b]$. Choose $x_1 < x_2$ in $[a, b]$ with $f(x_1) \neq f(x_2)$. Then $f$ takes on **every value between $f(x_1)$ and $f(x_2)$** somewhere in $(x_1, x_2)$.

**Proof:**
- Suppose $f(x_1) < f(x_2)$ and let $k$ be any value between them.
- Define $g(x) = f(x) - k$ on $[x_1, x_2]$.
- Then $g$ is continuous, $g(x_1) = f(x_1) - k < 0$, and $g(x_2) = f(x_2) - k > 0$.
- By Bolzano's theorem, $g(c) = 0$ for some $c \in (x_1, x_2)$.
- Hence $f(c) = k$.

> **Note:** In both Bolzano's theorem and the intermediate-value theorem, $f$ must be continuous at **every point** of $[a, b]$, including the endpoints. Figure 3.9 shows a function continuous everywhere in $[a, b]$ except at $a$; although $f(a) < 0$ and $f(b) > 0$, there is no $x$ with $f(x) = 0$.

### 3.8.2 Theorem 3.9 鈥?Existence of $n$th Roots

If $n$ is a positive integer and $a > 0$, then there is **exactly one** positive $b$ such that:

$$
b^n = a
$$

**Proof:**
1. Choose $c > 1$ such that $0 < a < c$, and let $f(x) = x^n$ on $[0, c]$.
2. $f$ is continuous on $[0, c]$, with $f(0) = 0$ and $f(c) = c^n$.
3. Since $0 < a < c < c^n$, the value $a$ lies between $f(0)$ and $f(c)$.
4. By the intermediate-value theorem, $f(x) = a$ for some $x \in (0, c)$; call it $b$.
5. **Uniqueness**: $f(x) = x^n$ is strictly increasing on $[0, c]$, so there cannot be more than one such $b$.

## 3.9 The Process of Inversion

### 3.9.1 Introduction

- **Inversion** is a method to construct new functions from given ones.
- Example: $f(x) = 2x + 1$ on $[0, 2]$ has range $[1, 5]$.
  - Each $x \in [0, 2]$ maps to exactly one $y \in [1, 5]$: $y = 2x + 1$.
  - Conversely, each $y \in [1, 5]$ comes from exactly one $x \in [0, 2]$.
  - Solving for $x$: $x = \frac{1}{2}(y - 1)$.
  - This defines $g(y) = \frac{1}{2}(y - 1)$, the **inverse** of $f$.

### 3.9.2 Definition of Inverse Function

- Let $f$ have domain $A$ and range $B$. If for each $y \in B$ there is **exactly one** $x \in A$ with $f(x) = y$, then the **inverse function** $g$ is defined on $B$ by:
  $$
  g(y) = x \quad \text{where} \quad y = f(x)
  $$
- **Key properties**:
  $$
  g[f(x)] = x \quad \text{for all } x \in A, \qquad f[g(y)] = y \quad \text{for all } y \in B
  $$

### 3.9.3 Existence of Inverses for Strictly Monotonic Functions

- A function that is **continuous and strictly monotonic** on $[a, b]$ has an inverse.
- **Reason**:
  1. By the intermediate-value theorem, $f$ takes on every value between $c = f(a)$ and $d = f(b)$.
  2. Since $f$ is strictly monotonic, $f(x_1) \neq f(x_2)$ whenever $x_1 \neq x_2$.
  3. Thus each $y$ in the range comes from exactly one $x$.

### 3.9.4 Ordered-Pair Formulation

- A function $f$ can be viewed as a set of ordered pairs $(x, y)$ with distinct first elements.
- The inverse $g$ is formed by **interchanging** $x$ and $y$: $(y, x) \in g \iff (x, y) \in f$.
- If $f$ is strictly monotonic, no two pairs have the same second element, so $g$ is indeed a function.

### 3.9.5 Example 鈥?The $n$th-Root Function

- Let $f(x) = x^n$ for $x \ge 0$ ($n$ a positive integer).
- $f$ is strictly increasing on every interval $[a, b]$ with $0 \le a \le b$.
- The inverse function $g$ is the **$n$th-root function**:
  $$
  g(y) = y^{1/n} \quad \text{for } y \ge 0
  $$

## 3.10 Properties of Functions Preserved by Inversion

### 3.10.1 Graphical Relationship

- The graphs of $f$ and its inverse $g$ are related by **reflection through the line $y = x$**.
- A point $(u, v)$ lies on the graph of $f$ iff $(v, u)$ lies on the graph of $g$.

### 3.10.2 Theorem 3.10 鈥?Monotonicity and Continuity of Inverses

Assume $f$ is strictly increasing and continuous on $[a, b]$. Let $c = f(a)$, $d = f(b)$, and let $g$ be the inverse of $f$ (defined on $[c, d]$). Then:

- **(a)** $g$ is strictly increasing on $[c, d]$.
- **(b)** $g$ is continuous on $[c, d]$.

**Proof of (a):**
- Choose $y_1 < y_2$ in $[c, d]$. Let $x_1 = g(y_1)$, $x_2 = g(y_2)$.
- Then $y_1 = f(x_1)$ and $y_2 = f(x_2)$.
- Since $f$ is strictly increasing, $y_1 < y_2 \implies x_1 < x_2$.
- Hence $g(y_1) < g(y_2)$, so $g$ is strictly increasing.

**Proof of (b):**
- Choose $y_0 \in (c, d)$ and let $x_0 = g(y_0)$, so $f(x_0) = y_0$.
- Given $\epsilon > 0$ (small enough that $x_0 \pm \epsilon \in [a, b]$), we need $\delta > 0$ such that:
  $$
  g(y_0) - \epsilon < g(y) < g(y_0) + \epsilon \quad \text{whenever} \quad y_0 - \delta < y < y_0 + \delta
  $$
  (Equation 3.22)
- Let $\delta$ be the smaller of:
  $$
  f(x_0) - f(x_0 - \epsilon) \quad \text{and} \quad f(x_0 + \epsilon) - f(x_0)
  $$
- Since $f$ is strictly increasing, this $\delta$ ensures (3.22) holds.
- A slight modification proves continuity from the right at $c$ and from the left at $d$.

> **Corresponding theorem for decreasing functions**: The inverse of a strictly decreasing continuous function is strictly decreasing and continuous. (Apply Theorem 3.10 to $-f$.)

### 3.10.3 Example 鈥?Continuity of the $n$th-Root Function

- The $n$th-root function $g(y) = y^{1/n}$ ($y \ge 0$) is the inverse of $f(x) = x^n$.
- Since $f$ is strictly increasing and continuous, by Theorem 3.10:
  - $g$ is **strictly increasing** and **continuous** on every interval $[c, d]$ with $0 \le c < d$.
- This provides an **alternate proof** of the continuity of $y^{1/n}$, independent of integration theory.
- Since products of continuous functions are continuous, the $r$th-power function $h(y) = y^r$ ($r = m/n$ positive rational, $y \ge 0$) is also continuous.

## 3.11 Inverses of Piecewise Monotonic Functions

### 3.11.1 The Problem

- Inversion requires each $y$ in the range to come from **exactly one** $x$.
- What if $f$ is **not monotonic** on $[a, b]$?
- Example: $f(x) = x^2$ on $[-c, c]$ maps to $[0, c^2]$.
  - Each $y \in (0, c^2]$ comes from **two** values: $x = \sqrt{y}$ and $x = -\sqrt{y}$.

### 3.11.2 Modern View: Multiple Single-Valued Inverses

- Older view: $g(y) = \pm\sqrt{y}$ as a "double-valued function."
- Modern view: inversion produces **two separate functions** (Equation 3.24):
  $$
  g_1(y) = \sqrt{y}, \qquad g_2(y) = -\sqrt{y} \quad \text{for } y \in [0, c^2]
  $$

### 3.11.3 Decomposing into Monotonic Pieces

- View $y = x^2$ as defining **two distinct functions** with different domains:
  $$
  f_1(x) = x^2 \quad \text{for } 0 \le x \le c, \qquad f_2(x) = x^2 \quad \text{for } -c \le x \le 0
  $$
- Each $f_i$ is monotonic on its domain and has an inverse:
  - $f_1^{-1} = g_1$ (positive square root)
  - $f_2^{-1} = g_2$ (negative square root)

### 3.11.4 General Principle

- For a **piecewise monotonic** function:
  - Decompose it into a union of monotonic pieces.
  - Invert each piece separately.
  - Each piece yields a single-valued inverse function.
- This technique will be used extensively in Chapter 6.

## 3.12 The Extreme-Value Theorem for Continuous Functions

### 3.12.1 Definitions

- **Absolute maximum**: $f$ has an absolute maximum on $S$ if $\exists c \in S$ such that $f(x) \le f(c)$ for all $x \in S$.
- **Absolute minimum**: $f$ has an absolute minimum on $S$ if $\exists d \in S$ such that $f(x) \ge f(d)$ for all $x \in S$.

**Examples (Figure 3.13):**

| Function | Domain | Absolute Min | Absolute Max |
|----------|--------|--------------|--------------|
| $f(x) = \sin x$ | $[0, \pi]$ | $0$ (at endpoints) | $1$ (at $x = \pi/2$) |
| $f(x) = 1/x$ ($x > 0$), $f(0) = 1$ | $[0, 2]$ | $1/2$ (at $x = 2$) | **None** (discontinuity at 0) |

- The second example shows that discontinuity can prevent the existence of an absolute maximum.

### 3.12.2 Theorem 3.11 鈥?Boundedness Theorem

Let $f$ be continuous on a closed interval $[a, b]$. Then $f$ is **bounded** on $[a, b]$; i.e., $\exists C \ge 0$ such that $|f(x)| \le C$ for all $x \in [a, b]$.

**Proof (by contradiction, successive bisection):**
1. Assume $f$ is unbounded on $[a, b]$.
2. Bisect $[a, b]$; $f$ must be unbounded on at least one half. Call it $[a_1, b_1]$.
3. Repeat: obtain a nested sequence $[a_n, b_n]$ of length $(b - a)/2^n$ on which $f$ is unbounded.
4. Let $A = \{a, a_1, a_2, \dots\}$ and $\alpha = \sup A$. Then $\alpha \in [a, b]$.
5. By continuity at $\alpha$: $\exists \delta > 0$ such that $|f(x) - f(\alpha)| < 1$ for $x \in (\alpha - \delta, \alpha + \delta)$.
   (Equation 3.25)
6. Hence $|f(x)| < 1 + |f(\alpha)|$ in this interval 鈥?$f$ is bounded here.
7. But $[a_n, b_n] \subset (\alpha - \delta, \alpha + \delta)$ for large $n$ (since $(b - a)/2^n < \delta$).
8. Contradiction: $f$ is bounded on $[a_n, b_n]$ yet was chosen to be unbounded there.

### 3.12.3 Supremum and Infimum of a Bounded Function

- If $f$ is bounded on $[a, b]$, define:
  $$
  \sup f = \sup\{f(x) \mid a \le x \le b\}, \qquad \inf f = \inf\{f(x) \mid a \le x \le b\}
  $$
- For any bounded function: $\inf f \le f(x) \le \sup f$ for all $x \in [a, b]$.

### 3.12.4 Theorem 3.12 鈥?Extreme-Value Theorem

Assume $f$ is continuous on $[a, b]$. Then there exist points $c, d \in [a, b]$ such that:

$$
f(c) = \sup f \quad \text{and} \quad f(d) = \inf f
$$

**Proof (for supremum):**
1. Let $M = \sup f$. Assume for contradiction that $f(x) \neq M$ for all $x \in [a, b]$.
2. Define $g(x) = M - f(x) > 0$ on $[a, b]$.
3. Then $1/g$ is continuous on $[a, b]$.
4. By Theorem 3.11, $1/g$ is bounded: $1/g(x) < C$ for some $C > 0$.
5. This implies $g(x) > 1/C$, so $M - f(x) > 1/C$, hence $f(x) < M - 1/C$.
6. But $M - 1/C < M$, contradicting $M$ being the least upper bound.
7. Therefore $f(c) = M$ for some $c \in [a, b]$.

> **Note:** For the infimum, apply the same argument to $-f$.

### 3.12.5 Consequence 鈥?Range of a Continuous Function

- If $f$ is continuous on $[a, b]$, then:
  - $\sup f$ is the **absolute maximum**.
  - $\inf f$ is the **absolute minimum**.
- By the intermediate-value theorem, the range of $f$ is the closed interval $[\inf f, \sup f]$.

## 3.13 The Small-Span Theorem for Continuous Functions (Uniform Continuity)

### 3.13.1 Definition 鈥?Span of a Function

- Let $M(f)$ and $m(f)$ denote the maximum and minimum values of $f$ on $[a, b]$.
- The **span** of $f$ on $[a, b]$:
  $$
  \text{span}(f) = M(f) - m(f)
  $$
- Some authors use **oscillation**; older texts use **saltus** (Latin for "leap").
- The span of $f$ on any subinterval cannot exceed the span on $[a, b]$.

### 3.13.2 Theorem 3.13 鈥?Small-Span Theorem

Let $f$ be continuous on a closed interval $[a, b]$. Then for every $\epsilon > 0$, there is a **partition** of $[a, b]$ into a finite number of subintervals such that the span of $f$ in **every** subinterval is less than $\epsilon$.

> This theorem is also known as the theorem on **uniform continuity**.

**Proof (by contradiction, successive bisections):**
1. Assume the theorem is false for some $\epsilon = \epsilon_0 > 0$.
2. Bisect $[a, b]$; the theorem must be false for $\epsilon_0$ in at least one half. Call it $[a_1, b_1]$.
3. Repeat: obtain a nested sequence $[a_n, b_n]$ of length $(b - a)/2^n$ where the span of $f$ is at least $\epsilon_0$.
4. Let $A = \{a, a_1, a_2, \dots\}$ and $\alpha = \sup A$. Then $\alpha \in [a, b]$.
5. By continuity at $\alpha$: there exists an interval $(\alpha - \delta, \alpha + \delta)$ in which the span of $f$ is less than $\epsilon_0$.
6. However, $[a_n, b_n] \subset (\alpha - \delta, \alpha + \delta)$ for large $n$ (since $(b - a)/2^n < \delta$).
7. Therefore the span of $f$ in $[a_n, b_n]$ is also less than $\epsilon_0$.
8. **Contradiction**: the span in $[a_n, b_n]$ was chosen to be at least $\epsilon_0$.

## 3.14 The Integrability Theorem for Continuous Functions

### 3.14.1 Theorem 3.14 鈥?Integrability of Continuous Functions

If $f$ is continuous at each point of a closed interval $[a, b]$, then $f$ is **integrable** on $[a, b]$.

**Proof:**
1. By Theorem 3.11, $f$ is bounded on $[a, b]$, so the upper integral $\bar{I}(f)$ and lower integral $\underline{I}(f)$ exist.
2. We shall prove $\bar{I}(f) = \underline{I}(f)$.

**Constructing step functions:**
3. Choose $N \ge 1$ and let $\epsilon = 1/N$.
4. By the small-span theorem, there is a partition $P = \{x_0, x_1, \dots, x_n\}$ of $[a, b]$ such that the span of $f$ in each subinterval is less than $\epsilon$.
5. Let $M_k(f)$ and $m_k(f)$ be the max and min of $f$ on $[x_{k-1}, x_k]$. Then:
   $$M_k(f) - m_k(f) < \epsilon$$

**Defining step functions:**
6. Define step functions $s_n$ and $t_n$ on $[a, b]$:
   $$
   s_n(x) = m_k(f) \text{ for } x_{k-1} < x \le x_k, \quad s_n(a) = m_1(f)
   $$
   $$
   t_n(x) = M_k(f) \text{ for } x_{k-1} \le x < x_k, \quad t_n(b) = M_n(f)
   $$
7. Then $s_n(x) \le f(x) \le t_n(x)$ for all $x \in [a, b]$.

**Comparing integrals:**
8. The integrals of the step functions:
   $$
   \int_a^b s_n = \sum_{k=1}^n m_k(f)(x_k - x_{k-1}), \qquad \int_a^b t_n = \sum_{k=1}^n M_k(f)(x_k - x_{k-1})
   $$
9. Their difference:
   $$
   \int_a^b t_n - \int_a^b s_n = \sum_{k=1}^n [M_k(f) - m_k(f)](x_k - x_{k-1}) < \epsilon \sum_{k=1}^n (x_k - x_{k-1}) = \epsilon(b - a)
   $$
10. With $\epsilon = 1/N$:
    $$
    \int_a^b t_n - \int_a^b s_n < \frac{b - a}{N}
    $$
    (Equation 3.26)

**Conclusion:**
11. The upper and lower integrals satisfy:
    $$
    \int_a^b s_n \le \underline{I}(f) \le \bar{I}(f) \le \int_a^b t_n
    $$
12. Hence:
    $$
    0 \le \bar{I}(f) - \underline{I}(f) \le \int_a^b t_n - \int_a^b s_n < \frac{b - a}{N}
    $$
13. Since this holds for every $N \ge 1$, we must have $\bar{I}(f) = \underline{I}(f)$.
14. Therefore $f$ is integrable on $[a, b]$.

## 3.15 Mean-Value Theorems for Integrals of Continuous Functions

### 3.15.1 Theorem 3.15 鈥?Mean-Value Theorem for Integrals

If $f$ is continuous on $[a, b]$, then for some $c \in [a, b]$:

$$
\int_a^b f(x) \, dx = f(c)(b - a)
$$

**Proof:**
1. Let $m$ and $M$ be the minimum and maximum values of $f$ on $[a, b]$.
2. Then $m \le f(x) \le M$ for all $x \in [a, b]$.
3. Integrating: $m(b - a) \le \int_a^b f(x) \, dx \le M(b - a)$.
4. Dividing by $b - a$: $m \le A(f) \le M$, where $A(f) = \frac{1}{b-a}\int_a^b f(x) \, dx$ is the average value.
5. By the intermediate-value theorem, $A(f) = f(c)$ for some $c \in [a, b]$.
6. Hence $\int_a^b f(x) \, dx = f(c)(b - a)$.

### 3.15.2 Theorem 3.16 鈥?Weighted Mean-Value Theorem

Assume $f$ and $g$ are continuous on $[a, b]$. If $g$ never changes sign on $[a, b]$, then for some $c \in [a, b]$:

$$
\int_a^b f(x)g(x) \, dx = f(c) \int_a^b g(x) \, dx
$$
(Equation 3.27)

**Proof:**
1. Assume $g \ge 0$ on $[a, b]$ (the case $g \le 0$ follows by applying to $-g$).
2. Since $m \le f(x) \le M$:
   $$mg(x) \le f(x)g(x) \le Mg(x)$$
3. Integrating:
   $$m\int_a^b g(x) \, dx \le \int_a^b f(x)g(x) \, dx \le M\int_a^b g(x) \, dx$$
   (Equation 3.28)
4. **Case 1**: If $\int_a^b g(x) \, dx = 0$, then $\int_a^b f(x)g(x) \, dx = 0$ as well, so (3.27) holds trivially for any $c$.
5. **Case 2**: If $\int_a^b g(x) \, dx > 0$, divide (3.28) by this integral:
   $$m \le \frac{\int_a^b f(x)g(x) \, dx}{\int_a^b g(x) \, dx} \le M$$
6. By the intermediate-value theorem, this quotient equals $f(c)$ for some $c \in [a, b]$.

> **Use**: The weighted mean-value theorem provides useful estimates for integrals of products, especially when one factor's integral is easy to compute.

# 4. Differential Calculus

## 4.1 Historical Introduction

- **Newton and Leibniz** independently fused **integral calculus** with **differential calculus**.
- The central concept is the **derivative**, originally arising from the geometric problem of finding **tangent lines**.
- **Fermat** (early 17th century) observed that at maxima/minima, the tangent is **horizontal**; this idea generalized to finding the tangent at any point, leading to the derivative.
- **Barrow** first realized the intimate relation between area (integral) and tangent (derivative); **Newton and Leibniz** fully exploited it.

## 4.2 A Problem Involving Velocity

### 4.2.1 The Projectile Model

- A projectile is fired straight up from the ground with initial velocity $144\ \text{ft/s}$.
- Neglect friction; gravity is the only force.
- Height at time $t$:
  $$
  f(t) = 144t - 16t^2, \qquad 0 \le t \le 9.
  $$
- $f(0)=0$ and $f(9)=0$: the projectile returns to earth after $9$ seconds.

### 4.2.2 Average Velocity 鈥?The Difference Quotient

- Average velocity over $[t, t+h]$:
  $$
  \frac{f(t+h)-f(t)}{h}.
  $$
- **Example ($t=2$)**:
  - $f(2)=224$.
  - $f(2+h)=224+80h-16h^2$.
  - Average velocity $= \dfrac{80h-16h^2}{h}=80-16h$.
  - As $|h|$ gets smaller, this approaches $80$.

### 4.2.3 Instantaneous Velocity

- For general $t$:
  $$
  \frac{f(t+h)-f(t)}{h} = 144 - 32t - 16h.
  $$
- Letting $h \to 0$:
  $$
  v(t) = \lim_{h\to 0}\frac{f(t+h)-f(t)}{h} = 144 - 32t.
  $$

### 4.2.4 Properties of the Velocity Function

| Quantity | Value |
|----------|-------|
| Initial velocity | $v(0)=144$ |
| Final velocity | $v(9)=-144$ |
| Zero velocity | $v(t)=0$ at $t=\dfrac{9}{2}$ |
| Max height | $f\left(\dfrac{9}{2}\right)=324$ |

- $t < \dfrac{9}{2}$: $v(t)>0$ (rising).
- $t > \dfrac{9}{2}$: $v(t)<0$ (falling).

### 4.2.5 General Definition

- For any position function $f$, the **instantaneous velocity** is:
  $$
  v(t) = \lim_{h\to 0}\frac{f(t+h)-f(t)}{h},
  $$
  provided the limit exists.

## 4.3 The Derivative of a Function

### 4.3.1 Definition of the Derivative

- Let $f$ be defined on an open interval $(a,b)$.
- For a fixed $x$ in $(a,b)$ and $h \neq 0$, the **difference quotient** is:
  $$
  \frac{f(x+h)-f(x)}{h}.
  $$
- This measures the **average rate of change** of $f$ over $[x, x+h]$.
- The **derivative of $f$ at $x$** is the limit:
  $$
  f'(x) = \lim_{h\to 0}\frac{f(x+h)-f(x)}{h},
  $$
  provided the limit exists.
- If the limit exists, $f$ is **differentiable at $x$**.
- If $f$ is differentiable at every $x$ in $(a,b)$, then $f$ is **differentiable on $(a,b)$**.

### 4.3.2 The Derived Function and Notations

- The function $f'$ assigns to each $x$ the value $f'(x)$; it is called the **derived function** or **derivative** of $f$.
- Domain of $f'$: the set of $x$ in $(a,b)$ where the limit exists.
- **Notations**:
  - $f'(x)$, $y'$ (Lagrange)
  - $Df(x)$, $Dy$ (Cauchy)
  - $\dfrac{df(x)}{dx}$, $\dfrac{dy}{dx}$ (Leibniz)
- **Leibniz notation**: Write $\Delta y = f(x+h)-f(x)$ and $\Delta x = h$, so the difference quotient is $\dfrac{\Delta y}{\Delta x}$. As $\Delta x \to 0$, this approaches $f'(x)$, denoted $\dfrac{dy}{dx}$.
- **Caution**: $\dfrac{dy}{dx}$ is a single symbol, not a quotient of $dy$ and $dx$.

### 4.3.3 Differentiation and Higher-Order Derivatives

- The limit process producing $f'(x)$ from $f(x)$ is called **differentiation**.
- $f'$ is the **first derivative** of $f$.
- If $f'$ is differentiable, its derivative is the **second derivative**, denoted $f''$.
- Inductively, the **$n$th derivative** $f^{(n)}$ is the first derivative of $f^{(n-1)}$.
- Convention: $f^{(0)} = f$ (the zeroth derivative is the function itself).

### 4.3.4 Velocity and Acceleration

- For rectilinear motion with position function $f$:
  - **Velocity**: $v(t) = f'(t)$
  - **Acceleration**: $a(t) = v'(t) = f''(t)$
- **Example** (projectile from Section 4.2): $f(t) = 144t - 16t^2$, $v(t) = 144 - 32t$.
  $$
  \frac{v(t+h)-v(t)}{h} = \frac{-32h}{h} = -32.
  $$
  Hence $a(t) = -32\ \text{ft/s}^2$ (constant).
  - Velocity decreases by $32\ \text{ft/s}$ each second.
  - In 9 seconds the total decrease is $288\ \text{ft/s}$, matching $v(0)=144$ to $v(9)=-144$.

## 4.4 Examples of Derivatives

### 4.4.1 Constant Function

- Let $f(x) = c$.
- Difference quotient:
  $$
  \frac{f(x+h)-f(x)}{h} = \frac{c-c}{h} = 0.
  $$
- Derivative:
  $$
  f'(x) = \lim_{h\to 0}0 = 0.
  $$
- **Result**: The derivative of a constant function is $0$ everywhere.

### 4.4.2 Linear Function

- Let $f(x) = mx + b$.
- Difference quotient:
  $$
  \frac{m(x+h)+b-(mx+b)}{h} = \frac{mh}{h} = m.
  $$
- **Result**:
  $$
  f'(x) = m \quad \text{for every } x.
  $$
- The derivative of a linear function is a constant function.

### 4.4.3 Positive Integer Powers

- Let $f(x)=x^n$ for a positive integer $n$.
- Using the identity $a^n-b^n=(a-b)\sum_{k=0}^{n-1}a^k b^{n-1-k}$ with $a=x+h$, $b=x$:
  $$
  \frac{(x+h)^n-x^n}{h} = \sum_{k=0}^{n-1}(x+h)^k x^{n-1-k}.
  $$
- As $h\to 0$, each of the $n$ terms approaches $x^{n-1}$.
- **Result**:
  $$
  (x^n)' = nx^{n-1}, \qquad n\in\mathbb{Z}^+.
  $$

### 4.4.4 The Sine Function

- Let $s(x)=\sin x$.
- Using $\sin y - \sin x = 2\sin\dfrac{y-x}{2}\cos\dfrac{y+x}{2}$ with $y=x+h$:
  $$
  \frac{\sin(x+h)-\sin x}{h} = \frac{\sin(h/2)}{h/2}\,\cos\left(x+\frac{h}{2}\right).
  $$
- As $h\to 0$: $\dfrac{\sin(h/2)}{h/2}\to 1$ and $\cos\left(x+\dfrac{h}{2}\right)\to\cos x$.
- **Result**:
  $$
  (\sin x)' = \cos x.
  $$

### 4.4.5 The Cosine Function

- Let $c(x)=\cos x$.
- Using $\cos y - \cos x = -2\sin\dfrac{y-x}{2}\sin\dfrac{y+x}{2}$ with $y=x+h$:
  $$
  \frac{\cos(x+h)-\cos x}{h} = -\frac{\sin(h/2)}{h/2}\,\sin\left(x+\frac{h}{2}\right).
  $$
- As $h\to 0$: $\dfrac{\sin(h/2)}{h/2}\to 1$ and $\sin\left(x+\dfrac{h}{2}\right)\to\sin x$.
- **Result**:
  $$
  (\cos x)' = -\sin x.
  $$

### 4.4.6 The $n$th-Root Function

- Let $f(x)=x^{1/n}$ for $x>0$, $n\in\mathbb{Z}^+$.
- Set $u=(x+h)^{1/n}$, $v=x^{1/n}$. Then $u^n-v^n=h$, and:
  $$
  \frac{u-v}{h} = \frac{1}{u^{n-1}+u^{n-2}v+\dots+v^{n-1}}.
  $$
- As $h\to 0$, $u\to v$, so the denominator tends to $nv^{n-1}$.
- **Result**:
  $$
  \left(x^{1/n}\right)' = \frac{1}{n}x^{1/n-1}, \qquad x>0.
  $$

### 4.4.7 Differentiability Implies Continuity

- **Theorem**: If $f$ has a derivative at $x$, then $f$ is continuous at $x$.
- **Proof sketch**: Write
  $$
  f(x+h) = f(x) + h\cdot\frac{f(x+h)-f(x)}{h}.
  $$
  As $h\to 0$, the difference quotient approaches $f'(x)$ and $h\to 0$, so $f(x+h)\to f(x)$.
- **Converse is false**: Continuity does not imply differentiability.
  - **Counterexample**: $f(x)=|x|$ is continuous at $0$ but not differentiable there, since
    $$
    \frac{|h|}{h} = \begin{cases} +1 & h>0 \\ -1 & h<0 \end{cases}
    $$
    has no limit as $h\to 0$.

## 4.5 The Algebra of Derivatives

### 4.5.1 Theorem 4.1 鈥?Basic Rules

- Let $f$ and $g$ be differentiable on a common interval.
- Then $f\pm g$, $f\cdot g$, and $f/g$ (where $g\neq 0$) are also differentiable, and:
  1. **Sum/Difference**:
     $$
     (f\pm g)' = f' \pm g'.
     $$
  2. **Product rule**:
     $$
     (fg)' = f g' + f' g.
     $$
  3. **Quotient rule** (at points where $g(x)\neq 0$):
     $$
     \left(\frac{f}{g}\right)' = \frac{g f' - f g'}{g^2}.
     $$

### 4.5.2 Linearity

- **Special case of product rule**: $(cf)' = c f'$ for any constant $c$.
- Combined with the sum rule:
  $$
  (c_1 f + c_2 g)' = c_1 f' + c_2 g'.
  $$
- By induction, for any finite sum:
  $$
  \left(\sum_{i=1}^{n} c_i f_i\right)' = \sum_{i=1}^{n} c_i f_i'.
  $$

### 4.5.3 Proof Sketches

- **Sum rule**: The difference quotient for $f+g$ splits into the sum of the two difference quotients; each tends to the respective derivative.
- **Product rule**: Add and subtract $g(x)f(x+h)$ in the numerator:
  $$
  \frac{f(x+h)g(x+h)-f(x)g(x)}{h} = g(x)\frac{f(x+h)-f(x)}{h} + f(x+h)\frac{g(x+h)-g(x)}{h}.
  $$
  As $h\to 0$: the first term $\to g(x)f'(x)$; by continuity $f(x+h)\to f(x)$, so the second term $\to f(x)g'(x)$.
- **Quotient rule**: First prove the special case
  $$
  \left(\frac{1}{g}\right)' = -\frac{g'}{g^2},
  $$
  then apply the product rule to $f\cdot(1/g)$.

### 4.5.4 Differentiating Polynomials

- Using linearity and $(x^n)'=nx^{n-1}$, differentiate any polynomial term by term:
  $$
  f(x)=\sum_{k=0}^{n}c_k x^k \quad\Longrightarrow\quad f'(x)=\sum_{k=0}^{n}k c_k x^{k-1}.
  $$
- The derivative of a degree-$n$ polynomial is a degree-$(n-1)$ polynomial.
- **Example**: $f(x)=2x^3+5x^2-7x+8 \Rightarrow f'(x)=6x^2+10x-7$.

### 4.5.5 Rational Functions

- If $r(x)=p(x)/q(x)$ with $p,q$ polynomials, apply the quotient rule wherever $q(x)\neq 0$.
- **Special case** ($r(x)=1/x^m$, $m\in\mathbb{Z}^+$, $x\neq 0$):
  $$
  r'(x)=-\frac{m}{x^{m+1}}=-m x^{-m-1}.
  $$
- This extends the power rule from positive to **negative integer exponents**.

### 4.5.6 Rational Powers

- **Theorem**: For any rational number $r$ and $x>0$:
  $$
  (x^r)' = r x^{r-1}.
  $$
- Already proved for $r=1/n$ (Section 4.4.6).
- Extend to $r=m/n$ by induction using the product rule.
- Extend to negative rationals using the quotient rule.
- **Examples**:
  - $f(x)=x^{2/3} \Rightarrow f'(x)=\frac{2}{3}x^{-1/3}$
  - $f(x)=x^{-1/2} \Rightarrow f'(x)=-\frac{1}{2}x^{-3/2}$

## 4.6 Geometric Interpretation of the Derivative as a Slope

### 4.6.1 Difference Quotient and Secant Slope

- The difference quotient
  $$
  \frac{f(x+h)-f(x)}{h}
  $$
  is the slope of the secant line through $P=(x,f(x))$ and $Q=(x+h,f(x+h))$.
- It equals $\tan\alpha$, where $\alpha$ is the angle the secant makes with the horizontal.

### 4.6.2 Derivative as Tangent Slope

- As $h\to 0$, the point $Q$ moves toward $P$ along the curve, and the secant line approaches a limiting position.
- This limiting line is the **tangent line** at $P$.
- The derivative $f'(x)$ is the **slope of the tangent line** at $(x,f(x))$:
  $$
  \text{slope of tangent} = f'(x) = \lim_{h\to 0}\frac{f(x+h)-f(x)}{h}.
  $$
- If $f'(x)$ exists, the curve has a **uniquely determined tangent line** at that point.
- The angle $\theta$ between the tangent line and the positive $x$-axis satisfies:
  $$
  \tan\theta = f'(x).
  $$

### 4.6.3 Equation of the Tangent Line

- The tangent line at $(x, f(x))$ has equation:
  $$
  Y - f(x) = f'(x)(X - x),
  $$
  where $(X, Y)$ denotes a variable point on the line.
- This is the **point鈥搒lope form** using the derivative as the slope.

### 4.6.4 Parallel and Perpendicular Lines

- Two nonvertical lines are **parallel** if and only if they have the same slope.
- Two nonvertical lines are **perpendicular** if and only if the product of their slopes is $-1$.
- These follow from the identities:
  $$
  \tan(\alpha-\beta)=\frac{\tan\alpha-\tan\beta}{1+\tan\alpha\tan\beta}, \qquad
  \cot(\alpha-\beta)=\frac{1+\tan\alpha\tan\beta}{\tan\alpha-\tan\beta}.
  $$

### 4.6.5 Sign of the Derivative

- $f'(x)>0$ on an interval: graph is **rising** (moving left to right).
- $f'(x)<0$ on an interval: graph is **falling**.
- $f'(x)=0$: **horizontal tangent**.
- At a local **maximum or minimum**, if the derivative exists, it must be zero: $f'(x)=0$.
- **Caution**: $f'(x)=0$ does not guarantee a max or min (e.g., inflection points).

## 4.7 Other Notations for Derivatives

- **Lagrange**: $f'(x),\; y',\; y'',\; y^{(n)}$.
- **Newton**: $\dot{y},\; \ddot{y}$ (dots, still used for velocity/acceleration).
- **Arbogast / Cauchy**: $Df,\; D^2f,\; D^nf$; $D$ is the **differentiation operator**.
- **Leibniz**: $\dfrac{dy}{dx}$. He regarded it as a quotient of **infinitesimals** $dy$ and $dx$.
  - This view was later replaced by the rigorous limit definition (Cauchy).
  - **Non-standard analysis** (Robinson, 1966) gave a consistent foundation for infinitesimals.

## 4.8 The Chain Rule for Differentiating Composite Functions

### 4.8.1 Composite Functions

- If $u$ and $v$ are functions with the domain of $u$ containing the range of $v$, the **composite function** $f=u\circ v$ is defined by:
  $$
  f(x) = u[v(x)].
  $$

### 4.8.2 The Chain Rule (Theorem 4.2)

- Let $f=u\circ v$. Suppose $v'(x)$ and $u'(y)$ exist, where $y=v(x)$.
- Then $f'(x)$ exists and:
  $$
  f'(x) = u'(y)\cdot v'(x) = u'[v(x)]\cdot v'(x).
  $$
- In function notation:
  $$
  (u\circ v)' = (u'\circ v)\cdot v'.
  $$
- In $u(v)$-notation:
  $$
  u(v)' = u'(v)\cdot v'.
  $$

### 4.8.3 Proof Sketch

- Let $y=v(x)$ and $k=v(x+h)-v(x)$. Then $v(x+h)=y+k$ and:
  $$
  \frac{f(x+h)-f(x)}{h} = \frac{u(y+k)-u(y)}{h}.
  $$
- **Naive approach** (valid when $k\neq 0$): multiply and divide by $k$:
  $$
  \frac{u(y+k)-u(y)}{k}\cdot\frac{k}{h} \to u'(y)\cdot v'(x) \quad (h\to 0).
  $$
- **Rigorous fix** (when $k$ may be $0$): define
  $$
  g(t) = \frac{u(y+t)-u(y)}{t} - u'(y) \quad (t\neq 0),
  $$
  with $g(0)=0$ so that $g$ is continuous at $0$. Then
  $$
  u(y+t)-u(y) = t[g(t)+u'(y)].
  $$
  Setting $t=k$ and substituting gives a formula valid even when $k=0$, yielding the same limit $u'(y)\cdot v'(x)$.

## 4.9 Applications of the Chain Rule: Related Rates and Implicit Differentiation

### 4.9.1 The Chain Rule in Leibniz Notation

- Let $y=v(x)$ and $z=u(y)=u[v(x)]=f(x)$.
- Then
  $$
  \frac{dz}{dx} = \frac{dz}{dy}\cdot\frac{dy}{dx}.
  $$
- This makes the chain rule look like a trivial algebraic cancellation of $dy$.

### 4.9.2 Related Rates

- **Problem**: A gas is pumped into a spherical balloon at $50\ \text{cm}^3/\text{s}$. How fast is the radius increasing when $r=5\ \text{cm}$?
- **Solution**:
  - $V=\frac{4}{3}\pi r^3$, so $\dfrac{dV}{dr}=4\pi r^2$.
  - By the chain rule:
    $$
    \frac{dV}{dt} = \frac{dV}{dr}\cdot\frac{dr}{dt} = 4\pi r^2\frac{dr}{dt}.
    $$
  - Substituting $dV/dt=50$ and $r=5$:
    $$
    \frac{dr}{dt} = \frac{1}{2\pi}\ \text{cm/s}.
    $$
- **Key point**: It is not necessary to express $r$ as an explicit function of $t$.

### 4.9.3 Differentiating Powers of a Function

- If $f(x)=[v(x)]^n$ with $n\in\mathbb{Z}^+$, then by the chain rule:
  $$
  f'(x) = n[v(x)]^{n-1}v'(x).
  $$
- In function notation:
  $$
  (v^n)' = n v^{n-1} v'.
  $$
- Valid also for **rational** powers whenever $v^n$ and $v^{n-1}$ are defined.
- **Example**: $f(x)=\sin(x^2)$. Let $v(x)=x^2$, $u(x)=\sin x$. Then
  $$
  f'(x)=\cos(x^2)\cdot 2x.
  $$

### 4.9.4 Implicit Differentiation

- The equation $x^2+y^2=r^2$ defines $y$ **implicitly** as a function of $x$ (actually two functions: upper and lower semicircles).
- Instead of solving for $y$, differentiate both sides with respect to $x$, remembering that $y$ is a function of $x$:
  $$
  2x + 2yy' = 0 \quad\Longrightarrow\quad y' = -\frac{x}{y}\quad (y\neq 0).
  $$
- This is **implicit differentiation**.
- Geometric meaning: at $(x,y)$ on the circle, the tangent slope is $-x/y$, while the radius slope is $y/x$; their product is $-1$, so the tangent is perpendicular to the radius.

## 4.10 Applications of Differentiation to Extreme Values of Functions

### 4.10.1 Absolute and Relative Extrema

- **Absolute maximum** on a set $S$: $f(x) \le f(c)$ for all $x \in S$.
- **Relative maximum** at $c \in S$: there exists an open interval $I$ containing $c$ such that
  $$
  f(x) \le f(c) \quad \text{for all } x \in I \cap S.
  $$
- **Relative minimum**: reverse the inequality.
- A **relative maximum** at $c$ is an absolute maximum in some neighborhood of $c$, but not necessarily on all of $S$.
- Every absolute maximum is, in particular, a relative maximum.
- An **extremum** (or extreme value) is either a relative maximum or a relative minimum.

### 4.10.2 Theorem 4.3 鈥?Vanishing of the Derivative at an Interior Extremum

- Let $f$ be defined on an open interval $I$ and have a relative maximum or minimum at an interior point $c \in I$.
- **If $f'(c)$ exists, then $f'(c)=0$**.
- **Proof sketch**: Define
  $$
  Q(x) = \frac{f(x)-f(c)}{x-c}\quad (x\neq c), \qquad Q(c)=f'(c).
  $$
  Then $Q$ is continuous at $c$. If $Q(c)=f'(c)\gt0$, the sign-preserving property gives $f(x)\gt f(c)$ for $x\gt c$ near $c$, contradicting the extremum. Similarly $Q(c)\lt0$ is impossible. Hence $Q(c)=0$, i.e. $f'(c)=0$.

### 4.10.3 Important Caveats

1. **$f'(c)=0$ does NOT imply an extremum at $c$**.
   - **Example**: $f(x)=x^3$ has $f'(0)=0$, but $0$ is not an extremum (the function is increasing through $0$).
2. **An extremum may occur where $f'(c)$ does not exist**.
   - **Example**: $f(x)=|x|$ has a relative minimum at $0$, but $f'(0)$ does not exist (sharp corner).
3. **Theorem 4.3 requires the derivative to exist** at the interior extremum. In the absence of sharp corners, the derivative must vanish at an interior extremum.

## 4.11 The Mean-Value Theorem for Derivatives

### 4.11.1 Rolle's Theorem (Theorem 4.4)

- Let $f$ be continuous on $[a,b]$ and differentiable on $(a,b)$.
- If $f(a)=f(b)$, then there exists at least one $c\in(a,b)$ such that
  $$
  f'(c)=0.
  $$
- **Geometric meaning**: If the endpoints have the same height, the curve has a horizontal tangent somewhere between them.
- **Proof sketch**: If $f'(x)\neq 0$ everywhere in $(a,b)$, then by the extreme-value theorem both extrema must occur at the endpoints. Since $f(a)=f(b)$, this forces $f$ to be constant, contradicting $f'(x)\neq 0$.

### 4.11.2 Mean-Value Theorem (Theorem 4.5)

- Let $f$ be continuous on $[a,b]$ and differentiable on $(a,b)$.
- Then there exists at least one $c\in(a,b)$ such that
  $$
  f(b)-f(a)=f'(c)(b-a),
  $$
  or equivalently
  $$
  \frac{f(b)-f(a)}{b-a}=f'(c).
  $$
- **Geometric meaning**: There is at least one point where the tangent line is parallel to the chord joining $(a,f(a))$ and $(b,f(b))$.
- **Physical interpretation**: The instantaneous speed at some moment equals the average speed over the interval.
- **Proof**: Apply Rolle's theorem to
  $$
  h(x)=f(x)(b-a)-x[f(b)-f(a)].
  $$
  Then $h(a)=h(b)$ and $h'(x)=f'(x)(b-a)-[f(b)-f(a)]$. Setting $h'(c)=0$ yields the result.
- **Note**: The theorem makes no assertion about the exact location of $c$, only that at least one such point exists somewhere in $(a,b)$.
- **Caution**: The conclusion may fail if $f$ is not differentiable at even one interior point.
  - **Example**: $f(x)=|x|$ on $[-1,2]$ is continuous and has derivative everywhere except $0$. The slope of the chord is $\frac{1}{3}$, but $f'(x)$ is never $\frac{1}{3}$.

### 4.11.3 Cauchy's Mean-Value Formula (Theorem 4.6)

- Let $f$ and $g$ be continuous on $[a,b]$ and differentiable on $(a,b)$.
- Then there exists $c\in(a,b)$ such that
  $$
  f'(c)[g(b)-g(a)] = g'(c)[f(b)-f(a)].
  $$
- **Proof**: Apply Rolle's theorem to
  $$
  h(x)=f(x)[g(b)-g(a)]-g(x)[f(b)-f(a)].
  $$
- The ordinary mean-value theorem is the special case with $g(x)=x$.

## 4.12 Applications of the Mean-Value Theorem to Geometric Properties

### 4.12.1 Monotonicity (Theorem 4.7)

- Let $f$ be continuous on $[a,b]$ and differentiable on $(a,b)$.
- **(a)** If $f'(x)>0$ for all $x\in(a,b)$, then $f$ is **strictly increasing** on $[a,b]$.
- **(b)** If $f'(x)<0$ for all $x\in(a,b)$, then $f$ is **strictly decreasing** on $[a,b]$.
- **(c)** If $f'(x)=0$ for all $x\in(a,b)$, then $f$ is **constant** on $[a,b]$.
- **Proof of (a)**: For $x<y$ in $[a,b]$, apply the mean-value theorem on $[x,y]$:
  $$
  f(y)-f(x)=f'(c)(y-x),\quad x<c<y.
  $$
  Since $f'(c)>0$ and $y-x>0$, we get $f(y)>f(x)$. Parts (b) and (c) are similar.

### 4.12.2 First-Derivative Test for Extrema (Theorem 4.8)

- Let $f$ be continuous on $[a,b]$ and differentiable on $(a,b)$ except possibly at $c$.
- **(a)** If $f'(x)>0$ for $x<c$ and $f'(x)<0$ for $x>c$ (sign changes from $+$ to $-$), then $f$ has a **relative maximum** at $c$.
- **(b)** If $f'(x)<0$ for $x<c$ and $f'(x)>0$ for $x>c$ (sign changes from $-$ to $+$), then $f$ has a **relative minimum** at $c$.
- **Proof of (a)**: By Theorem 4.7(a), $f$ is strictly increasing on $[a,c]$ and strictly decreasing on $[c,b]$. Hence $f(x)<f(c)$ for all $x\neq c$ in $(a,b)$.
- **Geometric meaning**: An extremum occurs whenever the derivative changes sign (Figure 4.12).

## 4.13 Second-Derivative Test for Extrema

### 4.13.1 Critical Points

- By the extreme-value theorem, a continuous function on $[a,b]$ attains its absolute max and min somewhere in $[a,b]$.
- If $f$ is differentiable at each interior point, extrema can occur only at:
  1. The **endpoints** $a$ and $b$;
  2. **Interior points** where $f'(x)=0$.
- Points of type (2) are called **critical points** of $f$.
- To decide whether a critical point is a max, min, or neither, study the sign of $f'$ near $c$, or use the second derivative.

### 4.13.2 Second-Derivative Test (Theorem 4.9)

- Let $c$ be a critical point of $f$ in $(a,b)$, so $f'(c)=0$.
- Assume $f''$ exists in $(a,b)$.
- **(a)** If $f''(x)<0$ in $(a,b)$, then $f$ has a **relative maximum** at $c$.
- **(b)** If $f''(x)>0$ in $(a,b)$, then $f$ has a **relative minimum** at $c$.
- **Proof of (a)**: If $f''<0$ in $(a,b)$, then by Theorem 4.7 applied to $f'$, the derivative $f'$ is strictly decreasing on $(a,b)$. Since $f'(c)=0$, $f'$ changes from positive to negative at $c$. By Theorem 4.8, $f$ has a relative maximum at $c$.
- **Practical version**: If $f''$ is continuous at $c$ and $f''(c)\neq 0$, then $f''$ has the same sign as $f''(c)$ in a neighborhood of $c$. Thus:
  - $f''(c)<0$ and $f'(c)=0$ $\Rightarrow$ relative maximum at $c$.
  - $f''(c)>0$ and $f'(c)=0$ $\Rightarrow$ relative minimum at $c$.

### 4.13.3 Convexity (Theorem 4.10)

- The sign of $f''$ also governs the **convexity** or **concavity** of $f$.
- **Theorem 4.10**: Assume $f$ is continuous on $[a,b]$ and differentiable on $(a,b)$.
  - If $f'$ is increasing on $(a,b)$, then $f$ is **convex** on $[a,b]$.
  - In particular, if $f''$ exists and is **nonnegative** in $(a,b)$, then $f$ is convex.
- **Proof sketch**: Take $x<y$ in $[a,b]$ and let $z=\alpha y+(1-\alpha)x$ with $0<\alpha<1$. Apply the mean-value theorem twice on $[x,z]$ and $[z,y]$ to get
  $$
  f(z)-f(x)=f'(c)(z-x),\quad f(y)-f(z)=f'(d)(y-z),
  $$
  with $x<c<z<d<y$. Since $f'$ is increasing, $f'(c)\le f'(d)$. Using $(1-\alpha)(z-x)=\alpha(y-z)$, this yields the convexity inequality
  $$
  f(z)\le\alpha f(y)+(1-\alpha)f(x).
  $$

## 4.14 Curve Sketching

### 4.14.1 General Procedure

1. Determine the **domain** and (if easy) the **range**.
2. Find **intercepts**:
   - $y$-intercept: $(0, f(0))$ (if $0$ is in the domain)
   - $x$-intercepts: solutions of $f(x)=0$
3. Determine **monotonicity** by the sign of $f'$.
4. Determine **convexity/concavity** by the sign of $f''$.
5. Locate points with **horizontal tangents** ($f'=0$).
6. Identify **asymptotes**.

### 4.14.2 Asymptotes

- A nonvertical line $y=mx+b$ is an **asymptote** if
  $$
  f(x)-(mx+b)\to 0 \quad \text{as } x\to\pm\infty.
  $$
- A vertical line $x=a$ is a **vertical asymptote** if $|f(x)|\to\infty$ as $x\to a$ from either side.

### 4.14.3 Example 1: $f(x)=x+\dfrac{1}{x}$ ($x\neq 0$)

- No intercepts on either axis.
- Derivatives:
  $$
  f'(x)=1-\frac{1}{x^2}, \qquad f''(x)=\frac{2}{x^3}.
  $$
- $f'(x)=0$ at $x=\pm 1$: relative **minimum** at $x=1$, relative **maximum** at $x=-1$.
- $f''(x)>0$ for $x>0$ (convex); $f''(x)<0$ for $x<0$ (concave).
- As $x\to 0$, behaves like $y=1/x$; the $y$-axis is a **vertical asymptote**.
- As $|x|\to\infty$, behaves like $y=x$; the line $y=x$ is an **asymptote**.
- $f$ is odd: $f(-x)=-f(x)$, so the graph is symmetric about the origin.

### 4.14.4 Example 2: $f(x)=\dfrac{1}{x^2+1}$

- Even function, positive for all $x$; the $x$-axis is a **horizontal asymptote**.
- Derivatives:
  $$
  f'(x)=\frac{-2x}{(x^2+1)^2}, \qquad
  f''(x)=\frac{2(3x^2-1)}{(x^2+1)^3}.
  $$
- $f'(x)<0$ for $x>0$, $f'(x)>0$ for $x<0$, $f'(0)=0$: **relative maximum** at $x=0$.
- $f''(x)>0$ if $3x^2>1$ (convex); $f''(x)<0$ if $3x^2<1$ (concave).
- **Points of inflection** at $x^2=\dfrac{1}{3}$, i.e. $x=\pm\dfrac{1}{\sqrt{3}}$, where $f''$ changes sign.

## 4.15 Worked Examples of Extremum Problems

### 4.15.1 Two Basic Principles

1. **Constant-sum, maximum-product principle**
   - Given $x+y=S$ with $x,y\gt0$, the product $xy$ is largest when $x=y=\dfrac{S}{2}$.
   - Proof: $f(x)=x(S-x)$ has $f'(x)=S-2x$, zero at $x=S/2$.

2. **Constant-product, minimum-sum principle**
   - Given $xy=P$ with $x,y\gt0$, the sum $x+y$ is smallest when $x=y=\sqrt{P}$.
   - Proof: $f(x)=x+P/x$ has $f'(x)=1-P/x^2$, zero at $x=\sqrt{P}$.

### 4.15.2 Consequences

- Among all rectangles of a given perimeter, the **square** has the largest area (Principle 1).
- **Arithmetic鈥揼eometric mean inequality**: For $a,b\gt0$,
  $$
  \sqrt{ab}\le\frac{a+b}{2},
  $$
  with equality if and only if $a=b$ (Principle 2).

### 4.15.3 Example: Minimizing Propelling Force

- A block of weight $W$ is pulled along a table by a force inclined at angle $\theta$.
- The propelling force needed to overcome friction is
  $$
  F(\theta)=\frac{\mu W}{\cos\theta+\mu\sin\theta},\qquad 0\le\theta\le\frac{\pi}{2}.
  $$
- To minimize $F$, maximize the denominator $g(\theta)=\cos\theta+\mu\sin\theta$.
- $g'(\theta)=-\sin\theta+\mu\cos\theta=0$ gives $\tan\alpha=\mu$.
- The minimum force is
  $$
  F_{\min}=\frac{\mu W}{\sqrt{1+\mu^2}}.
  $$

### 4.15.4 Example: Shortest Distance from a Point to a Parabola

- Find the shortest distance from $(0,b)$ on the $y$-axis to the parabola $x^2=4y$.
- Minimize $d^2=x^2+(y-b)^2=4y+(y-b)^2$ for $y\ge0$.
- $f'(y)=4+2(y-b)=0$ gives $y=b-2$.
- **Case $b\lt2$**: critical point $y=b-2$ is negative, so excluded. Since $f'(y)\gt0$ for $y\ge0$, the minimum occurs at the endpoint $y=0$. Minimum distance $=|b|$.
- **Case $b\ge2$**: legitimate critical point at $y=b-2$. Since $f''(y)=2\gt0$, this gives the absolute minimum. Minimum distance $=2\sqrt{b-1}$.
- The special transition value is $b=2$.

## 4.16 Partial Derivatives

### 4.16.1 Functions of Two Variables

- A **real-valued function of two real variables** has domain $X$ in the $xy$-plane and assigns a real number $f(x,y)$ to each point $(x,y)\in X$.
- **Example**: Temperature on a circular disk of radius $4$:
  $$
  f(x,y)=16-x^{2}-y^{2},\qquad x^{2}+y^{2}\le 16.
  $$
  On any circle $x^{2}+y^{2}=r^{2}$ the temperature is constant: $f=16-r^{2}$.

### 4.16.2 Geometric Representations

Two methods for visualizing $z=f(x,y)$:

| Method | Description |
|--------|-------------|
| **Surface** | Plot $(x,y,z)$ with $z=f(x,y)$ in 3-space. |
| **Level curves** | Project the intersection of $z=f(x,y)$ with horizontal planes $z=c$ onto the $xy$-plane; each curve satisfies $f(x,y)=c$. |

- **Level curves** are also called **contour lines** or **isotherms** (in temperature problems).
- Closely spaced level curves indicate rapid change (steepness); widely spaced curves indicate slow change.
- **Example**: $z=xy$ (hyperbolic paraboloid) has level curves $xy=c$.

### 4.16.3 Definition of Partial Derivatives

Cut the surface $z=f(x,y)$ with the plane $y=y_{0}$. The intersection is the curve $z=f(x,y_{0})$, a function of $x$ alone.

- **Difference quotient with respect to $x$**:
  $$
  \frac{f(x_{0}+h,y_{0})-f(x_{0},y_{0})}{h}.
  $$
- **Partial derivative with respect to $x$** at $(x_{0},y_{0})$:
  $$
  f_{1}(x_{0},y_{0})=\lim_{h\to 0}\frac{f(x_{0}+h,y_{0})-f(x_{0},y_{0})}{h}.
  $$
- **Partial derivative with respect to $y$** at $(x_{0},y_{0})$:
  $$
  f_{2}(x_{0},y_{0})=\lim_{k\to 0}\frac{f(x_{0},y_{0}+k)-f(x_{0},y_{0})}{k}.
  $$

Geometrically, $f_{1}(x_{0},y_{0})$ is the slope of the tangent to the curve $z=f(x,y_{0})$ at $x=x_{0}$; $f_{2}(x_{0},y_{0})$ is the slope of the tangent to $z=f(x_{0},y)$ at $y=y_{0}$.

### 4.16.4 Notations

| With respect to $x$ | With respect to $y$ |
|---------------------|---------------------|
| $\displaystyle\frac{\partial f}{\partial x}$ | $\displaystyle\frac{\partial f}{\partial y}$ |
| $f'_{x}(x,y)$ | $f'_{y}(x,y)$ |
| $f_{x}(x,y)$ | $f_{y}(x,y)$ |
| $f_{1}(x,y)$ | $f_{2}(x,y)$ |
| $D_{1}f(x,y)$ | $D_{2}f(x,y)$ |

If $z=f(x,y)$, one also writes $\partial z/\partial x$ and $\partial z/\partial y$.

### 4.16.5 Computation and Examples

To compute $\partial f/\partial x$, treat $y$ as constant and differentiate with respect to $x$ using the ordinary rules; similarly for $\partial f/\partial y$.

**Example 1**:
$$
f(x,y)=16-x^{2}-y^{2}\quad\Longrightarrow\quad f_{1}=-2x,\;\;f_{2}=-2y.
$$

**Example 2**:
$$
f(x,y)=x\sin y+y^{2}\cos(xy).
$$
Then
$$
f_{1}(x,y)=\sin y-y^{3}\sin(xy),
$$
$$
f_{2}(x,y)=x\cos y-xy^{2}\sin(xy)+2y\cos(xy).
$$

### 4.16.6 Second-Order Partial Derivatives

Since $f_{1}$ and $f_{2}$ are themselves functions of two variables, we may differentiate again:

| Notation | Meaning |
|----------|---------|
| $f_{1,1}=f_{xx}=\dfrac{\partial^{2}f}{\partial x^{2}}$ | Differentiate $f_{1}$ with respect to $x$ |
| $f_{1,2}=f_{xy}=\dfrac{\partial^{2}f}{\partial y\,\partial x}$ | Differentiate $f_{1}$ with respect to $y$ |
| $f_{2,1}=f_{yx}=\dfrac{\partial^{2}f}{\partial x\,\partial y}$ | Differentiate $f_{2}$ with respect to $x$ |
| $f_{2,2}=f_{yy}=\dfrac{\partial^{2}f}{\partial y^{2}}$ | Differentiate $f_{2}$ with respect to $y$ |

In $\partial$-notation:
$$
\frac{\partial^{2}f}{\partial y\,\partial x}=\frac{\partial}{\partial y}\!\left(\frac{\partial f}{\partial x}\right),\qquad
\frac{\partial^{2}f}{\partial x\,\partial y}=\frac{\partial}{\partial x}\!\left(\frac{\partial f}{\partial y}\right).
$$

- The two **mixed partial derivatives** need not be equal in general, but equality holds under mild conditions satisfied by most functions occurring in practice (discussed in Volume II).

**Example 1**: For $f(x,y)=16-x^{2}-y^{2}$:
$$
f_{1,1}=-2,\qquad f_{1,2}=f_{2,1}=0,\qquad f_{2,2}=-2.
$$

**Example 2**: For $f(x,y)=x\sin y+y^{2}\cos(xy)$:
$$
\begin{aligned}
f_{1,1}&=-y^{4}\cos(xy),\\[4pt]
f_{1,2}&=\cos y-xy^{3}\cos(xy)-3y^{2}\sin(xy)=f_{2,1},\\[4pt]
f_{2,2}&=-x\sin y-x^{2}y^{2}\cos(xy)-4xy\sin(xy)+2\cos(xy).
\end{aligned}
$$

# 5. The Relation between Integration and Differentiation

## 5.1 The Derivative of an Indefinite Integral

### 5.1.1 First Fundamental Theorem of Calculus

Integration and differentiation are inverse processes, analogous to squaring and taking the square root.

**Theorem 5.1 (First Fundamental Theorem of Calculus).**  
Let $f$ be integrable on $[a,x]$ for each $x\in[a,b]$. Choose $c\in[a,b]$ and define:

$$
A(x)=\int_{c}^{x}f(t)\,dt,\qquad a\le x\le b.
$$

If $f$ is continuous at a point $x$ in the open interval $(a,b)$, then the derivative $A'(x)$ exists and:

$$
A'(x)=f(x).
$$

- In words: *differentiating an indefinite integral of $f$ gives back $f$.*
- **Example**: $f(x)=x^{2}$. Then
  $$
  A(x)=\int_{c}^{x}t^{2}\,dt=\frac{x^{3}}{3}-\frac{c^{3}}{3},
  $$
  and indeed $A'(x)=x^{2}=f(x)$.

### 5.1.2 Geometric Motivation

Consider the area function $A$ over $[a,b]$.

- For $h>0$:
  $$
  \int_{x}^{x+h}f(t)\,dt=\int_{c}^{x+h}f(t)\,dt-\int_{c}^{x}f(t)\,dt=A(x+h)-A(x).
  $$
- By the **mean-value theorem for integrals** (assuming $f$ continuous on $[x,x+h]$):
  $$
  A(x+h)-A(x)=h\,f(z),\qquad x\le z\le x+h.
  $$
- Hence:
  $$
  \frac{A(x+h)-A(x)}{h}=f(z).
  $$
- As $h\to 0$, $z\to x$; if $f$ is continuous, $f(z)\to f(x)$, so $A'(x)=f(x)$.

> **Caveat:** This geometric argument assumes $f$ is continuous in a whole *neighborhood* of $x$, whereas Theorem 5.1 requires only continuity at the *single point* $x$.

### 5.1.3 Analytic Proof

Fix a point $x$ at which $f$ is continuous. The difference quotient is:

$$
\frac{A(x+h)-A(x)}{h}.
$$

Its numerator simplifies to:

$$
A(x+h)-A(x)=\int_{x}^{x+h}f(t)\,dt.
$$

Decompose $f(t)$ as $f(x)+[f(t)-f(x)]$:

$$
\begin{aligned}
A(x+h)-A(x)
&=\int_{x}^{x+h}f(x)\,dt+\int_{x}^{x+h}[f(t)-f(x)]\,dt\\[4pt]
&=h\,f(x)+\int_{x}^{x+h}[f(t)-f(x)]\,dt.
\end{aligned}
$$

Therefore:

$$
\frac{A(x+h)-A(x)}{h}=f(x)+\frac{1}{h}\int_{x}^{x+h}[f(t)-f(x)]\,dt.\tag{5.1}
$$

It remains to show that the second term tends to $0$ as $h\to 0$.

1. Let $\varepsilon>0$. By continuity of $f$ at $x$, there exists $\delta>0$ such that
   $$
   |f(t)-f(x)|<\frac{\varepsilon}{2}\quad\text{whenever}\quad |t-x|<\delta.
   $$
2. Choose $0<|h|<\delta$. Then every $t$ between $x$ and $x+h$ satisfies $|t-x|<\delta$, so:
   $$
   \Bigl|\int_{x}^{x+h}[f(t)-f(x)]\,dt\Bigr|
   \le\int_{x}^{x+h}|f(t)-f(x)|\,dt
   <\int_{x}^{x+h}\frac{\varepsilon}{2}\,dt
   =\frac{\varepsilon}{2}|h|
   <\varepsilon|h|.
   $$
3. Dividing by $|h|$ gives
   $$
   \Bigl|\frac{1}{h}\int_{x}^{x+h}[f(t)-f(x)]\,dt\Bigr|<\varepsilon.
   $$

Hence the second term in (5.1) vanishes as $h\to 0$, and $A'(x)=f(x)$. 鈭?
## 5.2 The Zero-Derivative Theorem

- If $f$ is constant on an open interval $(a,b)$, then $f'(x)=0$ everywhere on $(a,b)$ 鈥?an immediate consequence of the definition of the derivative.
- The converse is stated separately as Theorem 5.2:

**Theorem 5.2 (Zero-Derivative Theorem).**  
If $f'(x)=0$ for every $x$ in an open interval $I$, then $f$ is constant on $I$.

- This theorem, used in combination with the first fundamental theorem of calculus, leads to the **second fundamental theorem of calculus** (Section 5.3).

## 5.3 Primitive Functions and the Second Fundamental Theorem of Calculus

### 5.3.1 Primitive Functions

A function $P$ is called a **primitive** (or **antiderivative**) of $f$ on an open interval $I$ if:

$$
P'(x)=f(x)\quad\text{for all }x\in I.
$$

- **Example**: $\sin x$ is a primitive of $\cos x$ on every interval, since $(\sin x)'=\cos x$.
- We speak of **a** primitive, not **the** primitive: if $P$ is a primitive of $f$, so is $P+k$ for every constant $k$.
- **Uniqueness up to a constant**: Any two primitives $P$ and $Q$ of the same function $f$ differ only by a constant, because
  $$
  (P-Q)'=P'-Q'=f-f=0\quad\Longrightarrow\quad P-Q=\text{constant}
  $$
  by Theorem 5.2.

### 5.3.2 Second Fundamental Theorem of Calculus

The first fundamental theorem guarantees that a continuous function always has a primitive (obtained by integration). Combining this with the constant-difference property above yields:

**Theorem 5.3 (Second Fundamental Theorem of Calculus).**  
Assume $f$ is continuous on an open interval $I$, and let $P$ be any primitive of $f$ on $I$. Then for each $c$ and each $x$ in $I$:

$$
P(x)=P(c)+\int_{c}^{x}f(t)\,dt. \tag{5.2}
$$

Equivalently:

$$
\int_{c}^{x}f(t)\,dt=P(x)-P(c). \tag{5.3}
$$

**Proof.** Let $A(x)=\int_{c}^{x}f(t)\,dt$. By Theorem 5.1, $A'(x)=f(x)$, so $A$ is a primitive of $f$. Since two primitives differ only by a constant:
$$
A(x)-P(x)=k.
$$
Put $x=c$: $A(c)=0$, so $k=-P(c)$. Hence $A(x)-P(x)=-P(c)$, which gives (5.2). 鈭?
- In words: *knowing one primitive $P$ reduces integral evaluation to simple subtraction.*

### 5.3.3 Integration of Rational Powers

From the differentiation formula $\bigl(x^{n+1}/(n+1)\bigr)'=x^{n}$ and (5.3):

$$
\int_{a}^{b}x^{n}\,dx=\frac{b^{n+1}-a^{n+1}}{n+1},\qquad n\neq-1.
$$

| Exponent type | Validity | Restriction |
|---------------|----------|-------------|
| Nonnegative integers | Directly from power rule | None |
| Negative integers ($n\neq-1$) | $P(x)=x^{n+1}/(n+1)$ is rational | Exclude intervals containing $x=0$ |
| Rational exponents ($n\neq-1$) | Extend via general power rule (Chapter 6) | Integrand must be defined on $[a,b]$ |

- **Example** ($n=-\tfrac12$, $0<a<b$):
  $$
  \int_{a}^{b}\frac{1}{\sqrt{x}}\,dx=\int_{a}^{b}x^{-1/2}\,dx=\Bigl.\frac{x^{1/2}}{1/2}\Bigr|_{a}^{b}=2(\sqrt{b}-\sqrt{a}).
  $$

### 5.3.4 The Natural Logarithm

The power rule does **not** cover $n=-1$, since $x^{n+1}/(n+1)$ is undefined. Nevertheless, a primitive of $1/x$ exists:

$$
P(x)=\int_{1}^{x}\frac{1}{t}\,dt\qquad(x>0).
$$

- The integral exists because the integrand $1/t$ is monotonic.
- This function is called the **logarithm** (more precisely, the **natural logarithm**).
- Its properties are developed systematically in Chapter 6.

### 5.3.5 Integration of Sine and Cosine

Since $(\sin x)'=\cos x$ and $(\cos x)'=-\sin x$:

$$
\int_{a}^{b}\cos x\,dx=\sin x\Big|_{a}^{b}=\sin b-\sin a,
$$

$$
\int_{a}^{b}\sin x\,dx=-\cos x\Big|_{a}^{b}=\cos a-\cos b.
$$

- These formulas also follow directly from the definition of the integral (proved in Chapter 2).
- Further integration formulas are obtained by taking finite sums of terms $Ax^{n}$, $B\sin x$, $C\cos x$.

## 5.4 Properties of a Function Deduced from Properties of Its Derivative

If $f$ has a continuous derivative $f'$ on an open interval $I$, the second fundamental theorem gives:

$$
f(x)=f(c)+\int_{c}^{x}f'(t)\,dt\qquad\text{for all }x,c\in I. \tag{5.4}
$$

This formula expresses $f$ in terms of $f'$, allowing properties of $f$ to be deduced from properties of $f'$.

- **Monotonicity**: Suppose $f'$ is continuous and nonnegative on $I$. If $x>c$, then $\int_{c}^{x}f'(t)\,dt\ge0$, so $f(x)\ge f(c)$.  
  Hence: *a continuous nonnegative derivative implies $f$ is increasing on $I$.*

- **Convexity / concavity**: Theorem 2.9 shows that the indefinite integral of an increasing function is convex. Therefore, if $f'$ is continuous and increasing on $I$, Equation (5.4) shows that $f$ is **convex** on $I$. Similarly, $f$ is **concave** on intervals where $f'$ is continuous and decreasing.

## 5.5 The Leibniz Notation for Primitives

### 5.5.1 The Indefinite Integral Symbol

Leibniz introduced the symbol $\int f(x)\,dx$ to denote a **general primitive** of $f$:

$$
\int f(x)\,dx=P(x)+C, \tag{5.5}
$$

where $P'(x)=f(x)$ and $C$ is an arbitrary constant. Equation (5.5) is merely an alternative way of writing $P'(x)=f(x)$.

- **Example**:
  $$
  \int\cos x\,dx=\sin x+C.
  $$
- **Example** ($n\neq-1$):
  $$
  \int x^{n}\,dx=\frac{x^{n+1}}{n+1}+C.
  $$

> **Note**: $C$ represents an arbitrary constant, so each formula above describes a whole *family* of functions.

### 5.5.2 Relation to Definite Integration

Despite similar appearance, $\int f(x)\,dx$ and $\int_{a}^{b}f(x)\,dx$ are conceptually distinct 鈥?they originate from differentiation and integration respectively. The fundamental theorems connect them:

- **First FTC** (Equation 5.15):
  $$
  \int f(x)\,dx=\int_{c}^{x}f(t)\,dt+C.
  $$
  Thus $\int f(x)\,dx$ may be viewed as an indefinite integral plus a constant.

- **Second FTC** (Equation 5.16):
  $$
  \int_{a}^{b}f(x)\,dx=\Bigl[\int f(x)\,dx\Bigr]_{a}^{b}.
  $$
  In practice: evaluate any primitive at the endpoints and subtract.

### 5.5.3 Terminology and Techniques of Integration

Because of long historical usage, many textbooks call $\int f(x)\,dx$ an **indefinite integral** rather than a primitive. Since the second fundamental theorem reduces integration to finding primitives, the phrase **"technique of integration"** refers to any systematic method for finding primitives.

Three principal techniques for constructing tables of indefinite integrals:

| Technique | Basis | Location |
|-----------|-------|----------|
| **Integration by substitution** | Chain rule | Next section |
| **Integration by parts** | Product rule | Section 5.9 |
| **Integration by partial fractions** | Algebraic decomposition | End of Chapter 6 |

- These techniques explain how integral tables are built and how formulas are reduced to basic forms.
- When asked to "integrate" $\int f(x)\,dx$, what is wanted is the most general primitive of $f$.

## 5.6 Integration by Substitution

### 5.6.1 The Chain Rule in Reverse

If $Q(x)=P[g(x)]$ and $P'(x)=f(x)$, the chain rule gives:

$$
Q'(x)=P'[g(x)]g'(x)=f[g(x)]g'(x).
$$

Hence:

$$
\int f[g(x)]g'(x)\,dx=P[g(x)]+C. \tag{5.6}
$$

**Leibniz formalism.** Set $u=g(x)$ and write $du=g'(x)\,dx$. Then (5.6) becomes:

$$
\int f(u)\,du=P(u)+C.
$$

> **Note**: $dx$ and $du$ are treated as purely formal devices; each substitution step is really an application of the chain rule.

### 5.6.2 Examples 鈥?Indefinite Integrals

**Example 1.** $\displaystyle\int x^{3}\cos x^{4}\,dx$.
- Let $u=x^{4}$, $du=4x^{3}\,dx$.
- Compensate for the factor $4$:
  $$
  \int x^{3}\cos x^{4}\,dx=\tfrac14\int(\cos x^{4})(4x^{3}\,dx)=\tfrac14\int\cos u\,du=\tfrac14\sin u+C=\tfrac14\sin x^{4}+C.
  $$

**Example 2.** $\displaystyle\int\cos^{2}x\sin x\,dx$.
- Let $u=\cos x$, $du=-\sin x\,dx$.
  $$
  \int\cos^{2}x\sin x\,dx=-\int u^{2}\,du=-\frac{u^{3}}{3}+C=-\frac{\cos^{3}x}{3}+C.
  $$

**Example 3.** $\displaystyle\int\frac{\sin\sqrt{x}}{\sqrt{x}}\,dx$.
- Let $u=\sqrt{x}$, $du=\frac{1}{2\sqrt{x}}\,dx$, so $\frac{dx}{\sqrt{x}}=2\,du$.
  $$
  \int\frac{\sin\sqrt{x}}{\sqrt{x}}\,dx=2\int\sin u\,du=-2\cos u+C=-2\cos\sqrt{x}+C.
  $$

**Example 4.** $\displaystyle\int\frac{x\,dx}{\sqrt{1+x^{2}}}$.
- Let $u=1+x^{2}$, $du=2x\,dx$, so $x\,dx=\tfrac12\,du$.
  $$
  \int\frac{x\,dx}{\sqrt{1+x^{2}}}=\tfrac12\int u^{-1/2}\,du=u^{1/2}+C=\sqrt{1+x^{2}}+C.
  $$

### 5.6.3 Definite Integrals and Change of Limits

For definite integrals one may either:
1. find the indefinite integral, then evaluate at the endpoints; or
2. change the limits of integration to match the new variable $u$.

**Example (method 1).**
$$
\int_{0}^{\pi/2}\cos^{2}x\sin x\,dx=-\frac13\cos^{3}x\Big|_{0}^{\pi/2}=-\frac13(0-1)=\frac13.
$$

**Example 5 (method 2).** $\displaystyle\int_{2}^{3}\frac{(x+1)\,dx}{\sqrt{x^{2}+2x+3}}$.
- Let $u=x^{2}+2x+3$, $du=(2x+2)\,dx$, so $(x+1)\,dx=\tfrac12\,du$.
- New limits: $x=2\Rightarrow u=11$, $x=3\Rightarrow u=18$.
  $$
  \int_{2}^{3}\frac{(x+1)\,dx}{\sqrt{x^{2}+2x+3}}=\tfrac12\int_{11}^{18}u^{-1/2}\,du=\sqrt{u}\,\Big|_{11}^{18}=\sqrt{18}-\sqrt{11}.
  $$

### 5.6.4 The Substitution Theorem

**Theorem 5.4 (Substitution Theorem for Integrals).**  
Assume $g$ has a continuous derivative $g'$ on an open interval $I$. Let $J$ be the set of values taken by $g$ on $I$, and assume $f$ is continuous on $J$. Then for each $x$ and $c$ in $I$:

$$
\int_{c}^{x}f[g(t)]g'(t)\,dt=\int_{g(c)}^{g(x)}f(u)\,du. \tag{5.7}
$$

**Proof.** Let $a=g(c)$ and define:
$$
P(x)=\int_{a}^{x}f(u)\,du\quad(x\in J),\qquad Q(x)=\int_{c}^{x}f[g(t)]g'(t)\,dt\quad(x\in I).
$$
Then $P'(x)=f(x)$ and $Q'(x)=f[g(x)]g'(x)$. Set $R(x)=P[g(x)]$. By the chain rule:
$$
R'(x)=P'[g(x)]g'(x)=f[g(x)]g'(x)=Q'(x).
$$
Applying the second fundamental theorem twice:
$$
\int_{g(c)}^{g(x)}f(u)\,du=P[g(x)]-P[g(c)]=R(x)-R(c),
$$
$$
\int_{c}^{x}f[g(t)]g'(t)\,dt=Q(x)-Q(c)=R(x)-R(c).
$$
Thus the two integrals in (5.7) are equal. 鈭?
## 5.7 Integration by Parts

### 5.7.1 The Formula

From the product rule $(fg)'=f'g+fg'$ we obtain:

$$
\int f(x)g'(x)\,dx=f(x)g(x)-\int f'(x)g(x)\,dx+C. \tag{5.8}
$$

**Abbreviated form.** With $u=f(x)$, $v=g(x)$, $du=f'(x)\,dx$, $dv=g'(x)\,dx$:

$$
\int u\,dv=uv-\int v\,du+C. \tag{5.9}
$$

**Definite-integral version:**

$$
\int_{a}^{b}f(x)g'(x)\,dx=f(b)g(b)-f(a)g(a)-\int_{a}^{b}f'(x)g(x)\,dx.
$$

The idea is to choose $f$ and $g$ so that the new integral on the right is easier than the original.

### 5.7.2 Examples

**Example 1.** $\displaystyle\int x\cos x\,dx$.
- Good choice: $u=x$, $dv=\cos x\,dx$ $\Rightarrow$ $du=dx$, $v=\sin x$.
  $$
  \int x\cos x\,dx=x\sin x-\int\sin x\,dx=x\sin x+\cos x+C.
  $$
- Bad choice: $u=\cos x$, $dv=x\,dx$ $\Rightarrow$ $du=-\sin x\,dx$, $v=\tfrac12x^{2}$.
  $$
  \int x\cos x\,dx=\tfrac12x^{2}\cos x+\tfrac12\int x^{2}\sin x\,dx,
  $$
  which leads to a harder integral. (However, solving for $\int x^{2}\sin x\,dx$ and using the first result gives $\int x^{2}\sin x\,dx=2x\sin x+2\cos x-x^{2}\cos x+C$.)

**Example 2.** $\displaystyle\int x^{2}\cos x\,dx$.
- Let $u=x^{2}$, $dv=\cos x\,dx$ $\Rightarrow$ $du=2x\,dx$, $v=\sin x$.
  $$
  \int x^{2}\cos x\,dx=x^{2}\sin x-2\int x\sin x\,dx.
  $$
- Apply parts again to $\int x\sin x\,dx$ ($u=x$, $dv=\sin x\,dx$):
  $$
  \int x\sin x\,dx=-x\cos x+\sin x+C.
  $$
- Hence:
  $$
  \int x^{2}\cos x\,dx=x^{2}\sin x+2x\cos x-2\sin x+C.
  $$

**Example 3 (failure mode).** $\displaystyle\int x^{-1}\,dx$ by parts.
- Let $u=x$, $dv=x^{-2}\,dx$ $\Rightarrow$ $du=dx$, $v=-x^{-1}$.
  $$
  \int x^{-1}\,dx=-1+\int x^{-1}\,dx+C,
  $$
  which circles back. This shows the importance of the constant $C$: omitting it would give the fallacious conclusion $0=-1$.

### 5.7.3 Second Mean-Value Theorem for Integrals

**Theorem 5.5 (Second Mean-Value Theorem for Integrals).**  
Assume $g$ is continuous on $[a,b]$, and $f$ has a derivative which is continuous and never changes sign on $[a,b]$. Then for some $c$ in $[a,b]$:

$$
\int_{a}^{b}f(x)g(x)\,dx=f(a)\int_{a}^{c}g(x)\,dx+f(b)\int_{c}^{b}g(x)\,dx. \tag{5.10}
$$

**Proof.** Let $G(x)=\int_{a}^{x}g(t)\,dt$. Then $G'(x)=g(x)$ and $G(a)=0$. Integration by parts gives:

$$
\int_{a}^{b}f(x)g(x)\,dx=f(b)G(b)-\int_{a}^{b}f'(x)G(x)\,dx.
$$

By the weighted mean-value theorem, for some $c\in[a,b]$:

$$
\int_{a}^{b}f'(x)G(x)\,dx=G(c)\int_{a}^{b}f'(x)\,dx=G(c)\bigl[f(b)-f(a)\bigr].
$$

Substituting and rearranging:

$$
\int_{a}^{b}f(x)g(x)\,dx=f(b)G(b)-G(c)\bigl[f(b)-f(a)\bigr]=f(a)G(c)+f(b)\bigl[G(b)-G(c)\bigr],
$$

which is (5.10) since $G(c)=\int_{a}^{c}g(x)\,dx$ and $G(b)-G(c)=\int_{c}^{b}g(x)\,dx$. 鈭?
# 6. The Logarithm, the Exponential, and the Inverse Trigonometric Functions

## 6.1 Introduction

This chapter studies three indispensable families of functions:
- the **logarithm** and its inverse, the **exponential**;
- the **inverse trigonometric functions**.

### 6.1.1 The Elementary-Algebra Viewpoint

In elementary algebra, the logarithm to base $b$ ($b>0$, $b\neq1$) is defined by:

$$
u=\log_{b}x\quad\Longleftrightarrow\quad x=b^{u}. \tag{6.1}
$$

The fundamental property follows from the law of exponents:

$$
\log_{b}(xy)=\log_{b}x+\log_{b}y. \tag{6.2}
$$

- Base $10$ is convenient for decimal calculations; e.g. $\log_{10}0.01=-2$, $\log_{10}1000=3$.

### 6.1.2 Logical Gaps in the Elementary Approach

Defining logarithms via (6.1) raises several difficulties:

| Gap | Issue |
|-----|-------|
| **Meaning of $b^{u}$** | Easy when $u$ is integer or rational, but nontrivial when $u$ is irrational (e.g. $10^{\sqrt2}$). |
| **Existence** | Must prove that for every $x>0$ there actually exists a real $u$ with $x=b^{u}$. |
| **Laws of exponents** | The identity $b^{u}b^{v}=b^{u+v}$ must be established for *all* real exponents before (6.2) can be derived from (6.1). |

Overcoming these gaps directly is possible but long and tedious.

### 6.1.3 The Calculus Approach

A simpler and more elegant route is available through calculus:

- **Define the logarithm first** (via integration).
- **Then use logarithms to define $b^{u}$**.

This reverses the elementary order and avoids the logical gaps above.

## 6.2 Motivation for Defining the Natural Logarithm as an Integral

### 6.2.1 The Functional Equation

A key property desired for logarithms is:

$$
f(xy)=f(x)+f(y). \tag{6.3}
$$

An equation relating the values of a function at two or more points is called a **functional equation**. Rather than guessing a formula, we determine all differentiable solutions of (6.3).

### 6.2.2 Elementary Consequences

Assume $f$ satisfies (6.3) and is defined at the points indicated.

| Substitution | Result |
|--------------|--------|
| $x=y=1$ | $f(1)=0$ |
| $x=y=-1$ | $f(-1)=0$ |
| $y=-1$ | $f(-x)=f(x)$ (so $f$ is **even**) |
| $y=0$ (if $0$ is in the domain) | $f\equiv0$ |

- The zero function is the **only** solution defined on all of $\mathbb{R}$.
- Any solution that is **not** identically zero **cannot** be defined at $0$.

### 6.2.3 Differentiability and the Integral Formula

Assume $f$ has a derivative at each $x\neq0$. Fix $y$ in (6.3) and differentiate with respect to $x$ (chain rule on the left):

$$
yf'(xy)=f'(x).
$$

Setting $x=1$:

$$
f'(y)=\frac{f'(1)}{y}\qquad(y\neq0).
$$

Since $f'$ is continuous on every closed interval not containing $0$, the second fundamental theorem gives, for $x>0$ and $c=1$ (using $f(1)=0$):

$$
f(x)=f'(1)\int_{1}^{x}\frac{1}{t}\,dt. \tag{6.4}
$$

Because $f$ is even, the formula for $x<0$ involves $\int_{1}^{|x|}$. Both cases are combined as:

$$
f(x)=f'(1)\int_{1}^{|x|}\frac{1}{t}\,dt\qquad(x\neq0). \tag{6.5}
$$

### 6.2.4 Normalization and the Key Insight

If $f$ is **not** identically zero, then $f'(1)\neq0$. Dividing (6.5) by $f'(1)$ yields:

$$
g(x)=\int_{1}^{|x|}\frac{1}{t}\,dt\qquad(x\neq0), \tag{6.6}
$$

where $g(x)=f(x)/f'(1)$. Since $cf$ is a solution of (6.3) whenever $f$ is, $g$ is also a solution, and **all** non-zero solutions are scalar multiples of $g$.

> **Important caveat:** The argument above assumed that a non-zero solution exists; it did **not** prove that the function $g$ in (6.6) actually satisfies (6.3).

**The reverse idea.** Use the integral in (6.6) to *define* a function, then verify directly that it satisfies (6.3). However, (6.6) gives $g(-x)=g(x)$, so distinct numbers would have the same logarithm. To ensure distinct numbers have distinct logarithms, we restrict the definition to **positive $x$ only**.

## 6.3 The Definition of the Logarithm and Its Basic Properties

### 6.3.1 Definition

If $x$ is a positive real number, the **natural logarithm** of $x$, denoted temporarily by $L(x)$, is defined by:

$$
L(x)=\int_{1}^{x}\frac{1}{t}\,dt. \tag{6.7}
$$

- For $x>1$, $L(x)$ is the area under the hyperbola $y=1/t$ from $t=1$ to $t=x$.
- For $0<x<1$, the integral is negative (area counted with opposite orientation).

### 6.3.2 Basic Properties

**Theorem 6.1.** The logarithm function $L$ has the following properties:

| Property | Statement | Proof |
|----------|-----------|-------|
| **(a)** | $L(1)=0$ | Immediate from the definition. |
| **(b)** | $L'(x)=\dfrac1x$ for every $x>0$ | $L$ is an indefinite integral of the continuous function $1/t$; apply the first fundamental theorem. |
| **(c)** | $L(ab)=L(a)+L(b)$ for all $a,b>0$ | Additivity of the integral plus the substitution $u=t/a$. |

**Proof of (c).** For $a,b>0$:
$$
\begin{aligned}
L(ab)&=\int_{1}^{ab}\frac{dt}{t}=\int_{1}^{a}\frac{dt}{t}+\int_{a}^{ab}\frac{dt}{t}\\[4pt]
&=L(a)+\int_{a}^{ab}\frac{dt}{t}.
\end{aligned}
$$
In the last integral set $u=t/a$, $du=dt/a$:
$$
\int_{a}^{ab}\frac{dt}{t}=\int_{1}^{b}\frac{du}{u}=L(b).
$$
Hence $L(ab)=L(a)+L(b)$. 鈭?
### 6.3.3 Graph of the Natural Logarithm

- $L(1)=0$; the graph passes through $(1,0)$.
- $L'(x)=1/x>0$, so $L$ is **strictly increasing**.
- $L''(x)=-1/x^{2}<0$, so the graph is **concave**.
- As $x\to0^{+}$, $L(x)\to-\infty$; as $x\to+\infty$, $L(x)\to+\infty$.

## 6.4 The Graph of the Natural Logarithm

The shape of $y=L(x)$ follows directly from Theorem 6.1 without elaborate calculation:

- **Strictly increasing**: $L'(x)=1/x>0$ for all $x>0$.
- **Zero at $x=1$**: $L(1)=0$, so the graph lies **above** the $x$-axis for $x>1$ and **below** it for $0<x<1$.
- **Unit slope at $x=1$**: $L'(1)=1$.
- **Slope tends to $0$ as $x\to+\infty$**: $L'(x)=1/x\to0$.
- **Slope blows up as $x\to0^{+}$**: $L'(x)=1/x\to+\infty$.
- **Concave everywhere**: $L''(x)=-1/x^{2}<0$ for all $x>0$.

## 6.5 Consequences of the Functional Equation $L(ab)=L(a)+L(b)$

### 6.5.1 Unboundedness

From $L(a^{n})=nL(a)$ (proved by induction using the functional equation):

- For any $M>0$, choose an integer $n>M/L(2)$. Then:
  $$
  L(2^{n})=nL(2)>M.
  $$
  Hence $L$ is **not bounded above**.
- Taking $b=1/a$ in the functional equation gives $L(1/a)=-L(a)$. Therefore:
  $$
  L\!igl(2^{-n}\bigr)=-L(2^{n})<-M,
  $$
  so $L$ is **not bounded below**.

### 6.5.2 Existence and Uniqueness

**Theorem 6.2.** For every real number $b$ there is exactly one positive real number $a$ such that $L(a)=b$.

**Proof sketch.**
- If $b>0$, pick $n$ with $L(2^{n})>b$. On $[1,2^{n}]$ we have $L(1)=0$ and $L(2^{n})>b$, so the intermediate-value theorem guarantees at least one $a$ with $L(a)=b$. Uniqueness follows from strict monotonicity.
- If $b<0$, use $L(1/a)=-L(a)$.
- If $b=0$, then $a=1$.

Thus the graph of $L$ crosses every horizontal line exactly once.

### 6.5.3 The Number $e$

Since $L$ takes the value $1$ exactly once, we make the following definition.

**Definition.** We denote by $e$ the unique positive number for which:

$$
L(e)=1. \tag{6.8}
$$

- **Decimal value**: $e\approx2.7182818285\dots$
- **History**: The notation $e$ was introduced by Leonard Euler (1707--1783). Natural logarithms are also called **Napierian logarithms** (after John Napier, 1550--1617).
- **Notation**: The symbols $\ln x$ or $\log x$ are commonly used instead of $L(x)$.
- **Preview** (Chapter 7): explicit formulas for computing $e$ to any accuracy, and a proof that $e$ is irrational.

## 6.6 Logarithms to Any Positive Base $b\neq1$

### 6.6.1 General Solution of the Functional Equation

The most general differentiable solution of $f(xy)=f(x)+f(y)$ on the positive real axis is:

$$
f(x)=c\log x, \tag{6.9}
$$

where $c$ is a constant. When $c\neq0$, there is a unique $b>0$ with $f(b)=1$. Since $c\log b=1$, we obtain $c=1/\log b$ and (6.9) becomes:

$$
f(x)=\frac{\log x}{\log b}.
$$

### 6.6.2 Definition

**Definition.** If $b>0$, $b\neq1$, and $x>0$, the **logarithm of $x$ to the base $b$** is:

$$
\log_{b}x=\frac{\log x}{\log b}, \tag{6.10}
$$

where the logarithms on the right are natural logarithms.

- $\log_{b}b=1$.
- When $b=e$: $\log_{e}x=\log x$; natural logarithms are exactly those with base $e$.
- In higher mathematics the word "logarithm" almost invariably means **natural** logarithm.

### 6.6.3 Graphs

The graph of $y=\log_{b}x$ is obtained from $y=\log x$ by multiplying all ordinates by the factor $1/\log b$:

| Range of $b$ | Factor $1/\log b$ | Shape |
|--------------|-------------------|-------|
| $b>1$ | Positive | Same general shape as $\log x$, steeper if $1<b<e$, flatter if $b>e$. |
| $0<b<1$ | Negative | Reflection of $y=\log_{1/b}x$ through the $x$-axis. |

## 6.7 Differentiation and Integration Formulas Involving Logarithms

### 6.7.1 Basic Formulas

Since $D\log x=1/x$ for $x>0$:

$$
\int\frac{1}{x}\,dx=\log x+C.
$$

More generally, if $u=f(x)$ with $f$ continuously differentiable:

$$
\int\frac{du}{u}=\log u+C\qquad\text{or}\qquad\int\frac{f'(x)}{f(x)}\,dx=\log f(x)+C. \tag{6.11}
$$

> **Caution**: (6.11) is valid only when $u$ (or $f(x)$) is **positive**, because the logarithm is not defined for negative numbers.

### 6.7.2 Extension to Nonzero Values 鈥?The Function $L_{0}$

To accommodate functions that may be negative, define:

$$
L_{0}(x)=\log|x|=\int_{1}^{|x|}\frac{1}{t}\,dt\qquad(x\neq0). \tag{6.12}
$$

- $L_{0}$ is even; its graph is symmetric about the $y$-axis (Figure 6.4).
- $L_{0}$ also satisfies the functional equation $L_{0}(xy)=L_{0}(x)+L_{0}(y)$ for all nonzero $x,y$.
- Its derivative is:
  $$
  L_{0}'(x)=\frac{1}{x}\qquad\text{for all }x\neq0. \tag{6.13}
  $$

Hence the integration formulas extend to:

$$
\int\frac{du}{u}=\log|u|+C,\qquad\int\frac{f'(x)}{f(x)}\,dx=\log|f(x)|+C. \tag{6.14}
$$

> When evaluating definite integrals with (6.14), avoid intervals containing points where $u$ or $f(x)$ is zero.

### 6.7.3 Examples

**Example 1.** $\displaystyle\int\tan x\,dx$.
- Write $\tan x=-(\cos x)'/\cos x$. With $u=\cos x$:
  $$
  \int\tan x\,dx=-\int\frac{du}{u}=-\log|u|+C=-\log|\cos x|+C,
  $$
  valid on any interval where $\cos x\neq0$.

**Example 2.** $\displaystyle\int\log x\,dx$ (integration by parts).
- Let $u=\log x$, $dv=dx$ $\Rightarrow$ $du=dx/x$, $v=x$.
  $$
  \int\log x\,dx=x\log x-\int x\cdot\frac{1}{x}\,dx=x\log x-x+C.
  $$

**Example 3.** $\displaystyle\int\sin(\log x)\,dx$ and $\displaystyle\int\cos(\log x)\,dx$.
- For $\int\sin(\log x)\,dx$, let $u=\sin(\log x)$, $dv=dx$:
  $$
  \int\sin(\log x)\,dx=x\sin(\log x)-\int\cos(\log x)\,dx.
  $$
- Apply parts again to $\int\cos(\log x)\,dx$:
  $$
  \int\cos(\log x)\,dx=x\cos(\log x)+\int\sin(\log x)\,dx.
  $$
- Solving the two equations simultaneously:
  $$
  \begin{aligned}
  \int\sin(\log x)\,dx&=\tfrac12x\sin(\log x)-\tfrac12x\cos(\log x)+C,\\[4pt]
  \int\cos(\log x)\,dx&=\tfrac12x\sin(\log x)+\tfrac12x\cos(\log x)+C.
  \end{aligned}
  $$

## 6.8 Logarithmic Differentiation

A technique developed by Johann Bernoulli (1697) for computing derivatives of products or quotients.

### 6.8.1 The Method

Set:

$$
g(x)=\log|f(x)|.
$$

By the chain rule and $L_{0}'(x)=1/x$:

$$
g'(x)=\frac{f'(x)}{f(x)}. \tag{6.15}
$$

Hence:

$$
f'(x)=f(x)\,g'(x).
$$

The idea is that $g'(x)$ is often easier to compute than $f'(x)$ directly, especially when $f$ is a product or quotient of several simpler functions.

### 6.8.2 Example

Compute $f'(x)$ for:

$$
f(x)=x^{2}\cos x\,(1+x^{4})^{-7}.
$$

Take logarithms:
$$
\begin{aligned}
g(x)&=\log|f(x)|\\
&=2\log|x|+\log|\cos x|-7\log(1+x^{4}).
\end{aligned}
$$

Differentiate term by term:
$$
g'(x)=\frac{2}{x}-\tan x-\frac{28x^{3}}{1+x^{4}}.
$$

Multiply by $f(x)$:
$$
f'(x)=\frac{2x\cos x}{(1+x^{4})^{7}}-\frac{x^{2}\sin x}{(1+x^{4})^{7}}-\frac{28x^{5}\cos x}{(1+x^{4})^{8}}.
$$

## 6.9 Polynomial Approximations to the Logarithm

### 6.9.1 Setting Up the Integral

Replace $x$ by $1-x$ in the defining integral:

$$
\log(1-x)=\int_{1}^{1-x}\frac{dt}{t}\qquad(x<1).
$$

The change of variable $t=1-u$ gives:

$$
-\log(1-x)=\int_{0}^{x}\frac{du}{1-u}\qquad(x<1). \tag{6.16}
$$

### 6.9.2 The Approximating Polynomials

From $1-u^{n}=(1-u)(1+u+\dots+u^{n-1})$:

$$
\frac{1}{1-u}=1+u+\dots+u^{n-1}+\frac{u^{n}}{1-u}.
$$

Integrating from $0$ to $x$ ($x<1$) yields:

**Theorem 6.3.** Let
$$
P_{n}(x)=\sum_{k=1}^{n}\frac{x^{k}}{k}=x+\frac{x^{2}}{2}+\dots+\frac{x^{n}}{n}.
$$
Then for every $x<1$ and $n\ge1$:

$$
-\log(1-x)=P_{n}(x)+E_{n}(x), \tag{6.17}
$$

where the error term is:

$$
E_{n}(x)=\int_{0}^{x}\frac{u^{n}}{1-u}\,du.
$$

### 6.9.3 Error Estimates

**Theorem 6.4.** The error $E_{n}(x)$ satisfies:

- If $0<x<1$:
  $$
  \frac{x^{n+1}}{n+1}\le E_{n}(x)\le\frac{1}{1-x}\cdot\frac{x^{n+1}}{n+1}. \tag{6.18}
  $$

- If $x<0$:
  $$
  0<(-1)^{n+1}E_{n}(x)\le\frac{|x|^{n+1}}{n+1}. \tag{6.19}
  $$

**Proof sketch.** For $0<x<1$, use $1-x\le1-u\le1$ on $[0,x]$ to bound the integrand $u^{n}/(1-u)$. For $x<0$, set $t=-x$ and observe the sign alternation. 鈭?
### 6.9.4 A Formula for Computation

Subtracting (6.17) at $-x$ from (6.17) at $x$ (valid for $-1<x<1$) eliminates even powers:

**Theorem 6.5.** If $0<x<1$ and $m\ge1$:

$$
\log\frac{1+x}{1-x}=2\Bigl(x+\frac{x^{3}}{3}+\dots+\frac{x^{2m-1}}{2m-1}\Bigr)+R_{m}(x), \tag{6.20}
$$

where:

$$
\frac{x^{2m+1}}{2m+1}<R_{m}(x)\le\frac{2-x}{1-x}\cdot\frac{x^{2m+1}}{2m+1}. \tag{6.21}
$$

- **Example** ($m=2$, $x=\tfrac13$): since $(1+x)/(1-x)=2$,
  $$
  \log2=2\Bigl(\tfrac13+\tfrac1{81}\Bigr)+R_{2}\bigl(\tfrac13\bigr),\qquad\tfrac1{486}<R_{2}\bigl(\tfrac13\bigr)\le\tfrac5{486},
  $$
  giving $0.6921<\log2<0.6935$.

## 6.10 The Exponential Function

### 6.10.1 Definition

Theorem 6.2 shows that for every real $x$ there is a unique $y>0$ with $L(y)=x$. The **exponential function** (or **antilogarithm**), denoted $E$, is the inverse of $L$:

$$
y=E(x)\quad\Longleftrightarrow\quad L(y)=x.
$$

- **Domain**: all real numbers; **range**: $(0,+\infty)$.
- The graph of $E$ is the reflection of the graph of $L$ through the line $y=x$ (Figure 6.6).
- Inverse relations:
  $$
  L[E(x)]=x\quad\text{for all }x,\qquad E[L(y)]=y\quad\text{for all }y>0.
  $$

### 6.10.2 Basic Properties

**Theorem 6.6.** The exponential function satisfies:

| Property | Statement |
|----------|-----------|
| **(a)** | $E(0)=1$, $E(1)=e$. |
| **(b)** | $E'(x)=E(x)$ for every $x$. |
| **(c)** | $E(a+b)=E(a)E(b)$ for all $a,b$. |

**Proof.**
- **(a)** Follows from $L(1)=0$ and $L(e)=1$.
- **(c)** Let $x=E(a)$, $y=E(b)$, $c=L(xy)$. Then $L(x)=a$, $L(y)=b$, and $c=L(xy)=L(x)+L(y)=a+b$. Hence $E(a+b)=E(c)=xy=E(a)E(b)$.
- **(b)** Using (c), the difference quotient is:
  $$
  \frac{E(x+h)-E(x)}{h}=E(x)\,\frac{E(h)-1}{h}.
  $$
  Set $k=E(h)-1$; then $h=L(k+1)$ and
  $$
  \frac{E(h)-1}{h}=\frac{k}{L(k+1)}=\frac{1}{[L(k+1)-L(1)]/k}\to\frac{1}{L'(1)}=1
  $$
  as $h\to0$ (so $k\to0$). Thus $E'(x)=E(x)$. 鈭?
## 6.11 Exponentials Expressed as Powers of $e$

The functional equation $E(a+b)=E(a)E(b)$ implies:

$$
E(-a)=\frac{1}{E(a)},\qquad E(na)=E(a)^{n}\quad(n\in\mathbb{Z}^{+}).
$$

Taking $a=1$ gives $E(n)=e^{n}$; taking $a=1/n$ gives $E(1/n)=e^{1/n}$. Combining these:

$$
E\Bigl(\frac{n}{m}\Bigr)=E\Bigl(\frac1m\Bigr)^{n}=e^{n/m}
$$

for all positive integers $m,n$. Since $E(-r)=1/E(r)$, we obtain:

$$
\boxed{E(r)=e^{r}\quad\text{for every rational number }r.} \tag{6.22}
$$

## 6.12 The Definition of $e^{x}$ for Arbitrary Real $x$

For rational $r$ we have $e^{r}=E(r)$. We **define** $e^{x}$ for irrational $x$ by the same formula:

$$
e^{x}=E(x)\qquad\text{for every real }x. \tag{6.23}
$$

- **Justification**: with this definition the law of exponents
  $$
  e^{a}e^{b}=e^{a+b}
  $$
  holds for **all** real $a,b$, because it is simply a restatement of the functional equation $E(a+b)=E(a)E(b)$.
- **Notation**: $e^{x}$ (or $\exp x$) is the standard symbol; $E(x)$ is still used occasionally in this chapter.
- The two equations $y=e^{x}$ and $x=\log y$ mean exactly the same thing.

## 6.13 The Definition of $a^{x}$ for $a>0$ and $x$ Real

Now that $e^{x}$ is defined for arbitrary real $x$, we define general powers by:

$$
a^{x}=e^{x\log a}\qquad(a>0,\;x\in\mathbb{R}). \tag{6.24}
$$

This definition is preferable because it is meaningful for **all** positive $a$ (including $a=1$) and makes the following properties immediate:

$$
\begin{aligned}
\log a^{x}&=x\log a, & (ab)^{x}&=a^{x}b^{x},\\
a^{x}a^{y}&=a^{x+y}, & (a^{x})^{y}&=(a^{y})^{x}=a^{xy}.
\end{aligned}
$$

- If $a\neq1$, then $y=a^{x}\iff x=\log_{a}y$.
- The graph of $y=a^{x}$ is the reflection of $y=\log_{a}x$ through the line $y=x$.
- The case $a=1$ gives the horizontal line $y=1$.

## 6.14 Differentiation and Integration Formulas Involving Exponentials

### 6.14.1 Differentiation

The most remarkable property of the exponential is that it equals its own derivative:

$$
E'(x)=E(x). \tag{6.25}
$$

For a general base $a>0$, write $a^{x}=e^{x\log a}=E(x\log a)$. By the chain rule:

$$
\frac{d}{dx}(a^{x})=a^{x}\log a\qquad(a>0). \tag{6.26}
$$

The factor $\log a$ equals $1$ when $a=e$.

### 6.14.2 Integration 鈥?Basic Formulas

From the derivatives above:

$$
\int e^{x}\,dx=e^{x}+C,\qquad\int a^{x}\,dx=\frac{a^{x}}{\log a}+C\quad(a>0,\;a\neq1). \tag{6.27}
$$

With substitution $u=f(x)$, $du=f'(x)\,dx$:

$$
\int e^{f(x)}f'(x)\,dx=e^{f(x)}+C,\qquad\int a^{f(x)}f'(x)\,dx=\frac{a^{f(x)}}{\log a}+C.
$$

### 6.14.3 Examples

**Example 1.** $\displaystyle\int x^{2}e^{x^{3}}\,dx$.
- Let $u=x^{3}$, $du=3x^{2}\,dx$:
  $$
  \int x^{2}e^{x^{3}}\,dx=\tfrac13\int e^{u}\,du=\tfrac13e^{x^{3}}+C.
  $$

**Example 2.** $\displaystyle\int\frac{2^{\sqrt{x}}}{\sqrt{x}}\,dx$.
- Let $u=\sqrt{x}$, $du=\frac{1}{2\sqrt{x}}\,dx$:
  $$
  \int\frac{2^{\sqrt{x}}}{\sqrt{x}}\,dx=2\int2^{u}\,du=\frac{2^{1+\sqrt{x}}}{\log2}+C.
  $$

**Example 3.** $\displaystyle\int\cos x\,e^{2\sin x}\,dx$.
- Let $u=2\sin x$, $du=2\cos x\,dx$:
  $$
  \int\cos x\,e^{2\sin x}\,dx=\tfrac12\int e^{u}\,du=\tfrac12e^{2\sin x}+C.
  $$

**Example 4.** $\displaystyle\int e^{x}\sin x\,dx$ and $\displaystyle\int e^{x}\cos x\,dx$ (integration by parts).
- Set $u=e^{x}$, $dv=\sin x\,dx$:
  $$
  \int e^{x}\sin x\,dx=-e^{x}\cos x+\int e^{x}\cos x\,dx. \tag{6.28}
  $$
- Set $u=e^{x}$, $dv=\cos x\,dx$:
  $$
  \int e^{x}\cos x\,dx=e^{x}\sin x-\int e^{x}\sin x\,dx. \tag{6.29}
  $$
- Solving (6.28) and (6.29) simultaneously:
  $$
  \begin{aligned}
  \int e^{x}\sin x\,dx&=\tfrac12e^{x}(\sin x-\cos x)+C,\\[4pt]
  \int e^{x}\cos x\,dx&=\tfrac12e^{x}(\sin x+\cos x)+C.
  \end{aligned}
  $$

**Example 5.** $\displaystyle\int\frac{dx}{1+e^{x}}$.
- Rewrite $\dfrac1{1+e^{x}}=\dfrac{e^{-x}}{e^{-x}+1}$ and let $u=e^{-x}+1$:
  $$
  \int\frac{dx}{1+e^{x}}=-\log(1+e^{-x})+C=x-\log(1+e^{x})+C.
  $$
- Alternatively, write $\dfrac1{1+e^{x}}=1-\dfrac{e^{x}}{1+e^{x}}$ and let $u=1+e^{x}$:
  $$
  \int\frac{dx}{1+e^{x}}=x-\log(1+e^{x})+C.
  $$

## 6.15 The Hyperbolic Functions

Combinations of exponentials that occur frequently in analysis:

$$
\begin{aligned}
\sinh x&=\frac{e^{x}-e^{-x}}{2}, & \cosh x&=\frac{e^{x}+e^{-x}}{2}, & \tanh x&=\frac{\sinh x}{\cosh x}=\frac{e^{x}-e^{-x}}{e^{x}+e^{-x}},\\[4pt]
\csch x&=\frac{1}{\sinh x}, & \sech x&=\frac{1}{\cosh x}, & \coth x&=\frac{1}{\tanh x}.
\end{aligned}
$$

- The name "hyperbolic" comes from the geometric relation to a hyperbola (analogous to the relation of trigonometric functions to a circle); discussed in detail in Chapter 14.
- The hyperbolic functions possess many properties that resemble those of the trigonometric functions.

**Graphs** (Figure 6.8):
- $y=\sinh x$: odd, strictly increasing, passes through the origin.
- $y=\cosh x$: even, U-shaped with minimum $1$ at $x=0$.
- $y=\tanh x$: odd, increasing, horizontal asymptotes $y=\pm1$.

## 6.16 Derivatives of Inverse Functions

**Theorem 6.7.** Assume $f$ is strictly increasing and continuous on $[a,b]$, and let $g$ be the inverse of $f$. If $f'(x)$ exists and is nonzero at a point $x$ in $(a,b)$, then $g'(y)$ also exists and is nonzero at the corresponding point $y=f(x)$. Moreover:

$$
g'(y)=\frac{1}{f'(x)}. \tag{6.30}
$$

**Leibniz form.** With $y=f(x)$, $\dfrac{dy}{dx}=f'(x)$, $x=g(y)$, $\dfrac{dx}{dy}=g'(y)$:

$$
\frac{dx}{dy}=\frac{1}{\,\dfrac{dy}{dx}\,}.
$$

**Proof sketch.** Let $h=g(y+k)-g(y)$. Then $y+k=f(x+h)$ and $k=f(x+h)-f(x)$. Since $g$ is continuous, $h\to0$ as $k\to0$. The difference quotient becomes:

$$
\frac{g(y+k)-g(y)}{k}=\frac{h}{f(x+h)-f(x)}=\frac{1}{[f(x+h)-f(x)]/h}\to\frac{1}{f'(x)}
$$

as $k\to0$. 鈭?
## 6.17 Inverses of the Trigonometric Functions

### 6.17.1 Arc Sine

Restrict $\sin x$ to the interval $[-\tfrac{\pi}{2},\tfrac{\pi}{2}]$, where it is strictly increasing and takes every value in $[-1,1]$ exactly once.

**Definition.** $u=\arcsin v$ means $v=\sin u$ with $-\tfrac{\pi}{2}\le u\le\tfrac{\pi}{2}$.

- **Domain**: $[-1,1]$; **range**: $[-\pi/2,\pi/2]$.
- **Derivative** (from Theorem 6.7 with $f(x)=\sin x$, $f'(x)=\cos x$):
  $$
  D\arcsin x=\frac{1}{\sqrt{1-x^{2}}}\qquad(-1<x<1). \tag{6.31}
  $$
- **Integration formulas**:
  $$
  \int_{0}^{x}\frac{dt}{\sqrt{1-t^{2}}}=\arcsin x,\qquad\int\frac{dx}{\sqrt{1-x^{2}}}=\arcsin x+C.
  $$
- **By parts**:
  $$
  \int\arcsin x\,dx=x\arcsin x+\sqrt{1-x^{2}}+C.
  $$

> **Note**: Formula (6.31) can serve as the starting point for a purely analytic theory of the trigonometric functions, with no reference to geometry.

### 6.17.2 Arc Cosine

Restrict $\cos x$ to $[0,\pi]$.

**Definition.** $u=\arccos v$ means $v=\cos u$ with $0\le u\le\pi$.

- **Derivative**:
  $$
  D\arccos x=\frac{-1}{\sqrt{1-x^{2}}}\qquad(-1<x<1). \tag{6.32}
  $$
- **Relation to arc sine**:
  $$
  \arcsin x+\arccos x=\frac{\pi}{2}.
  $$
- **Integration formulas**:
  $$
  \int\frac{dx}{\sqrt{1-x^{2}}}=-\arccos x+C,\qquad\int\arccos x\,dx=x\arccos x-\sqrt{1-x^{2}}+C.
  $$

### 6.17.3 Arc Tangent

Restrict $\tan x$ to $(-\tfrac{\pi}{2},\tfrac{\pi}{2})$.

**Definition.** $u=\arctan v$ means $v=\tan u$ with $-\tfrac{\pi}{2}<u<\tfrac{\pi}{2}$.

- **Derivative**:
  $$
  D\arctan x=\frac{1}{1+x^{2}}\qquad(\text{all real }x). \tag{6.33}
  $$
- **Integration formulas**:
  $$
  \int_{0}^{x}\frac{dt}{1+t^{2}}=\arctan x,\qquad\int\frac{dx}{1+x^{2}}=\arctan x+C.
  $$
- **By parts**:
  $$
  \int\arctan x\,dx=x\arctan x-\tfrac12\log(1+x^{2})+C.
  $$

### 6.17.4 Other Inverse Trigonometric Functions

| Function | Definition | Domain |
|----------|-----------|--------|
| $\arccot x$ | $\dfrac{\pi}{2}-\arctan x$ | all real $x$ |
| $\arcsec x$ | $\arccos\dfrac1x$ | $|x|\ge1$ |
| $\arccsc x$ | $\arcsin\dfrac1x$ | $|x|\ge1$ |

## 6.18 Integration by Partial Fractions

Every rational function can be integrated in terms of polynomials, logarithms, and inverse tangents.

### 6.18.1 Preliminaries

- A quotient $f(x)/g(x)$ of two polynomials is a **rational function**.
- It is **proper** if $\deg f<\deg g$; otherwise divide to obtain a polynomial plus a proper part:
  $$
  \frac{f(x)}{g(x)}=Q(x)+\frac{R(x)}{g(x)}.
  $$
- **Algebraic theorem**: every proper rational function is a finite sum of fractions of the two types:
  $$
  \frac{A}{(x+a)^{k}},\qquad\frac{Bx+C}{(x^{2}+bx+c)^{m}},
  $$
  where $x^{2}+bx+c$ is **irreducible** ($b^{2}-4c<0$).

### 6.18.2 Case 1 鈥?Distinct Linear Factors

If $g(x)=(x-x_{1})(x-x_{2})\cdots(x-x_{n})$, then:

$$
\frac{f(x)}{g(x)}=\frac{A_{1}}{x-x_{1}}+\cdots+\frac{A_{n}}{x-x_{n}}.
$$

**Example.** $\displaystyle\int\frac{2x^{2}+5x-1}{x^{3}+x^{2}-2x}\,dx$.
- $x^{3}+x^{2}-2x=x(x-1)(x+2)$.
- $A_{1}=\tfrac12$, $A_{2}=2$, $A_{3}=-\tfrac12$ (cover-up method).
- Result: $\tfrac12\log|x|+2\log|x-1|-\tfrac12\log|x+2|+C$.

### 6.18.3 Case 2 鈥?Repeated Linear Factors

If $(x+a)^{p}$ occurs, include $p$ terms:

$$
\sum_{k=1}^{p}\frac{A_{k}}{(x+a)^{k}}.
$$

**Example.** $\displaystyle\int\frac{x^{2}+2x+3}{(x-1)(x+1)^{2}}\,dx$.
- Decompose as $\dfrac{A_{1}}{x-1}+\dfrac{A_{2}}{x+1}+\dfrac{A_{3}}{(x+1)^{2}}$.
- $A_{1}=\tfrac32$, $A_{3}=-1$ (cover-up); $A_{2}=-\tfrac12$ (substitute $x=0$ or differentiate).
- Result: $\tfrac32\log|x-1|-\tfrac12\log|x+1|+\dfrac{1}{x+1}+C$.

### 6.18.4 Case 3 鈥?Distinct Irreducible Quadratics

**Example.** $\displaystyle\int\frac{3x^{2}+2x-2}{x^{3}-1}\,dx$.
- $x^{3}-1=(x-1)(x^{2}+x+1)$.
- Decompose: $\dfrac{1}{x-1}+\dfrac{2x+3}{x^{2}+x+1}$.
- Second term: split into $\dfrac{2x+1}{x^{2}+x+1}$ (log) and $\dfrac{2}{(x+\tfrac12)^{2}+\tfrac34}$ (arctan).
- Result: $\log|x-1|+\log(x^{2}+x+1)+\tfrac{4}{\sqrt3}\arctan\!\bigl(\tfrac{2x+1}{\sqrt3}\bigr)+C$.

### 6.18.5 Case 4 鈥?Repeated Irreducible Quadratics

If $(x^{2}+bx+c)^{m}$ occurs, include $m$ terms with linear numerators:

$$
\sum_{k=1}^{m}\frac{B_{k}x+C_{k}}{(x^{2}+bx+c)^{k}}.
$$

**Example.** $\displaystyle\int\frac{x^{4}-x^{3}+2x^{2}-x+2}{(x-1)(x^{2}+2)^{2}}\,dx$.
- Decompose: $\dfrac{A}{x-1}+\dfrac{Bx+C}{x^{2}+2}+\dfrac{Dx+E}{(x^{2}+2)^{2}}$.
- Constants: $A=\tfrac13$, $B=\tfrac23$, $C=-\tfrac13$, $D=-1$, $E=0$.
- Result: $\tfrac13\log|x-1|+\tfrac13\log(x^{2}+2)-\tfrac{\sqrt2}{6}\arctan\!\bigl(\tfrac{x}{\sqrt2}\bigr)+\dfrac{1}{2(x^{2}+2)}+C$.

### 6.18.6 The Basic Integrals

All partial-fraction integrals reduce to the three forms below.

| Form | Technique | Result |
|------|-----------|--------|
| $\displaystyle\int\frac{dx}{(x+a)^{n}}$ | Direct power rule | $\log|x+a|$ if $n=1$; $\dfrac{(x+a)^{1-n}}{1-n}$ if $n>1$ |
| $\displaystyle\int\frac{x\,dx}{(x^{2}+bx+c)^{m}}$ | Write numerator as derivative of quadratic | $\tfrac12\log(x^{2}+bx+c)$ if $m=1$ |
| $\displaystyle\int\frac{dx}{(x^{2}+bx+c)^{m}}$ | Complete the square: $u^{2}+\alpha^{2}$ | $\dfrac1\alpha\arctan\!\bigl(\tfrac u\alpha\bigr)$ if $m=1$; reduction formula for $m>1$ |

**Reduction formula** (for $m>1$):

$$
\int\frac{du}{(u^{2}+\alpha^{2})^{m}}=\frac{u}{2\alpha^{2}(m-1)(u^{2}+\alpha^{2})^{m-1}}+\frac{2m-3}{2\alpha^{2}(m-1)}\int\frac{du}{(u^{2}+\alpha^{2})^{m-1}}.
$$

## 6.19 Integrals Reducible to Rational Functions

### 6.19.1 The Weierstrass Substitution

For integrals of the form $\displaystyle\int R(\sin x,\cos x)\,dx$ (where $R$ is a rational function of two variables), the substitution:

$$
u=\tan\tfrac{x}{2}
$$

converts the integrand into a rational function of $u$:

$$
\sin x=\frac{2u}{1+u^{2}},\qquad\cos x=\frac{1-u^{2}}{1+u^{2}},\qquad dx=\frac{2\,du}{1+u^{2}}.
$$

**Example 1.** $\displaystyle\int\frac{dx}{\sin x+\cos x}$.
- With $u=\tan\tfrac{x}{2}$ the integral becomes $-2\displaystyle\int\frac{du}{u^{2}-2u-1}$.
- Factor $u^{2}-2u-1=(u-a)(u-b)$ with $a=1+\sqrt2$, $b=1-\sqrt2$.
- Partial fractions give:
  $$
  \int\frac{dx}{\sin x+\cos x}=\frac{\sqrt2}{2}\log\Bigl|\tan\Bigl(\frac{x}{2}+\frac{\pi}{8}\Bigr)\Bigr|+C.
  $$

### 6.19.2 Trigonometric Substitutions for Radicals

| Radical form | Substitution | Differential | Simplification |
|--------------|--------------|--------------|----------------|
| $\sqrt{a^{2}-(cx+d)^{2}}$ | $cx+d=a\sin t$ | $c\,dx=a\cos t\,dt$ | $\sqrt{\cdots}=a\cos t$ |
| $\sqrt{a^{2}+(cx+d)^{2}}$ | $cx+d=a\tan t$ | $c\,dx=a\sec^{2}t\,dt$ | $\sqrt{\cdots}=a\sec t$ |
| $\sqrt{(cx+d)^{2}-a^{2}}$ | $cx+d=a\sec t$ | $c\,dx=a\sec t\tan t\,dt$ | $\sqrt{\cdots}=a\tan t$ |

In each case the new integrand becomes a rational function of $\sin t$ and $\cos t$.

**Example 2.** $\displaystyle\int\frac{x\,dx}{4-x^{2}+\sqrt{4-x^{2}}}$.
- Let $x=2\sin t$, $dx=2\cos t\,dt$, $\sqrt{4-x^{2}}=2\cos t$.
- The integral simplifies to $\displaystyle\int\frac{\sin t\,dt}{\cos t+\tfrac12}=-\log\Bigl|\tfrac12+\cos t\Bigr|+C=-\log\bigl(1+\sqrt{4-x^{2}}\bigr)+C$.

# 7. Polynomial Approximations to Functions

## 7.1 Introduction

Polynomials are among the simplest functions in analysis and are pleasant for numerical computation because their values require only finitely many multiplications and additions.

- In Chapter 6 the logarithm was approximated by polynomials to any desired accuracy.
- This chapter extends the idea to other functions (exponential, trigonometric, etc.).
- Goal: find a polynomial that agrees with $f$ and some of its derivatives at a given point.

**Example: approximating $e^{x}$ near $x=0$.**

Since $f^{(k)}(0)=1$ for every $k$, the polynomial of degree $n$:

$$
P_{n}(x)=\sum_{k=0}^{n}\frac{x^{k}}{k!}=1+x+\frac{x^{2}}{2!}+\cdots+\frac{x^{n}}{n!} \tag{7.1}
$$

agrees with $e^{x}$ and its first $n$ derivatives at $0$.

| Degree | Polynomial | Matches at $x=0$ |
|--------|-----------|------------------|
| $1$ | $1+x$ | $f(0), f'(0)$ |
| $2$ | $1+x+\tfrac12x^{2}$ | $f(0), f'(0), f''(0)$ |
| $n$ | $\displaystyle\sum_{k=0}^{n}\frac{x^{k}}{k!}$ | $f(0),\dots,f^{(n)}(0)$ |

- The linear polynomial $1+x$ is the tangent line at $(0,1)$.
- Higher-degree polynomials give better accuracy near $x=0$ (Figure 7.1).
- Before using such polynomials we need information about the approximation **error**; the general theory follows in the next sections.

## 7.2 The Taylor Polynomials Generated by a Function

### 7.2.1 Construction at $x=0$

Suppose $f$ has derivatives up to order $n$ at $0$. We seek a polynomial $P$ of degree $\le n$ such that:

$$
P(0)=f(0),\quad P'(0)=f'(0),\quad\dots,\quad P^{(n)}(0)=f^{(n)}(0). \tag{7.2}
$$

Write $P(x)=c_{0}+c_{1}x+\dots+c_{n}x^{n}$. Differentiating repeatedly and setting $x=0$ gives:

$$
c_{k}=\frac{f^{(k)}(0)}{k!}\qquad(k=0,1,\dots,n). \tag{7.3}
$$

(When $k=0$, $f^{(0)}(0)$ means $f(0)$.)

### 7.2.2 Taylor's Theorem

**Theorem 7.1.** If $f$ has derivatives of order $n$ at $0$, there exists one and only one polynomial of degree $\le n$ satisfying (7.2). It is given by:

$$
P(x)=\sum_{k=0}^{n}\frac{f^{(k)}(0)}{k!}\,x^{k}. \tag{7.4}
$$

### 7.2.3 Expansion about an Arbitrary Point

The same argument works at any point $a$. The unique polynomial of degree $\le n$ agreeing with $f$ and its first $n$ derivatives at $a$ is:

$$
P(x)=\sum_{k=0}^{n}\frac{f^{(k)}(a)}{k!}\,(x-a)^{k}. \tag{7.5}
$$

This is called the **Taylor polynomial of degree $n$ generated by $f$ at the point $a$**.

- **Taylor operator notation**: $T_{n}f$ or $T_{n}(f)$ denotes this polynomial; $T_{n}f(x;a)$ makes the dependence on $a$ explicit.

### 7.2.4 Examples

**Example 1** ($e^{x}$ at $0$). Since $E^{(k)}(0)=1$:

$$
T_{n}E(x)=\sum_{k=0}^{n}\frac{x^{k}}{k!}=1+x+\frac{x^{2}}{2!}+\cdots+\frac{x^{n}}{n!}.
$$

At $a=1$, where $E^{(k)}(1)=e$:

$$
T_{n}E(x;1)=\sum_{k=0}^{n}\frac{e}{k!}\,(x-1)^{k}.
$$

**Example 2** ($\sin x$ at $0$). Odd derivatives alternate $\pm1$; even derivatives vanish:

$$
T_{2n+1}(\sin x)=x-\frac{x^{3}}{3!}+\frac{x^{5}}{5!}-\cdots+(-1)^{n}\frac{x^{2n+1}}{(2n+1)!}.
$$

**Example 3** ($\cos x$ at $0$). Even derivatives alternate $\pm1$; odd derivatives vanish:

$$
T_{2n}(\cos x)=1-\frac{x^{2}}{2!}+\frac{x^{4}}{4!}-\cdots+(-1)^{n}\frac{x^{2n}}{(2n)!}.
$$

> **Observation**: $T_{2n}(\cos x)$ is the derivative of $T_{2n+1}(\sin x)$, reflecting the fact that $\cos x$ is the derivative of $\sin x$.

## 7.3 Calculus of Taylor Polynomials

### 7.3.1 Algebraic Properties of the Taylor Operator

**Theorem 7.2.** The Taylor operator $T_{n}$ has the following properties (all polynomials are generated at a common point $a$):

| Property | Formula |
|----------|---------|
| **(a) Linearity** | $T_{n}(c_{1}f+c_{2}g)=c_{1}T_{n}(f)+c_{2}T_{n}(g)$ |
| **(b) Differentiation** | $(T_{n}f)'=T_{n-1}(f')$ |
| **(c) Integration** | If $g(x)=\int_{a}^{x}f(t)\,dt$, then $T_{n+1}g(x)=\int_{a}^{x}T_{n}f(t)\,dt$ |

**Proof idea.** In each case both sides are polynomials of the same degree that agree in value and in derivatives up to the appropriate order at $a$; uniqueness (Theorem 7.1) forces equality. 鈭?
### 7.3.2 Substitution Property

**Theorem 7.3.** Let $g(x)=f(cx)$ with $c$ constant. Then:

$$
T_{n}g(x;a)=T_{n}f(cx;ca). \tag{7.6}
$$

In particular, when $a=0$: $T_{n}g(x)=T_{n}f(cx)$.

**Proof.** By the chain rule $g^{(k)}(x)=c^{k}f^{(k)}(cx)$; substitute into the Taylor formula. 鈭?
**Examples.**
- Replacing $x$ by $-x$ in $T_{n}(e^{x})$:
  $$
  T_{n}(e^{-x})=1-x+\frac{x^{2}}{2!}-\frac{x^{3}}{3!}+\cdots+(-1)^{n}\frac{x^{n}}{n!}.
  $$
- Using linearity with $\cosh x=\tfrac12e^{x}+\tfrac12e^{-x}$:
  $$
  T_{2n}(\cosh x)=1+\frac{x^{2}}{2!}+\frac{x^{4}}{4!}+\cdots+\frac{x^{2n}}{(2n)!}.
  $$
- Differentiation gives $T_{2n-1}(\sinh x)$.

### 7.3.3 Recognition by Remainder Form

**Theorem 7.4.** Let $P_{n}$ be a polynomial of degree $n\ge1$. If

$$
f(x)=P_{n}(x)+x^{n}g(x), \tag{7.7}
$$

where $g(x)\to0$ as $x\to0$, then $P_{n}=T_{n}f$ (the Taylor polynomial of $f$ at $0$).

**Proof.** Set $h(x)=f(x)-P_{n}(x)=x^{n}g(x)$. Repeated differentiation shows $h$ and its first $n$ derivatives vanish at $0$; hence $f$ agrees with $P_{n}$ through order $n$. 鈭?
**Examples.**
- From $\dfrac{1}{1-x}=1+x+\dots+x^{n}+\dfrac{x^{n+1}}{1-x}$:
  $$
  T_{n}\!\Bigl(\frac{1}{1-x}\Bigr)=1+x+\dots+x^{n}.
  $$
- Integrating:
  $$
  T_{n+1}[-\log(1-x)]=x+\frac{x^{2}}{2}+\frac{x^{3}}{3}+\cdots+\frac{x^{n+1}}{n+1}.
  $$
- Replacing $x$ by $-x^{2}$ in the first example:
  $$
  T_{2n}\!\Bigl(\frac{1}{1+x^{2}}\Bigr)=\sum_{k=0}^{n}(-1)^{k}x^{2k}.
  $$
- Integrating:
  $$
  T_{2n+1}(\arctan x)=\sum_{k=0}^{n}(-1)^{k}\frac{x^{2k+1}}{2k+1}.
  $$

## 7.4 Taylor's Formula with Remainder

### 7.4.1 The Error Term

The **error** (or **remainder**) in approximating $f$ by its Taylor polynomial $T_{n}f$ at $a$ is:

$$
E_{n}(x)=f(x)-T_{n}f(x).
$$

Hence:

$$
f(x)=\sum_{k=0}^{n}\frac{f^{(k)}(a)}{k!}\,(x-a)^{k}+E_{n}(x). \tag{7.8}
$$

### 7.4.2 Integral Form of the Remainder

**Theorem 7.5 (Linear case).** If $f$ has a continuous second derivative near $a$, then for every $x$ in this neighborhood:

$$
f(x)=f(a)+f'(a)(x-a)+E_{1}(x),\qquad E_{1}(x)=\int_{a}^{x}(x-t)f''(t)\,dt.
$$

**Theorem 7.6 (General case).** If $f$ has a continuous derivative of order $n+1$ in an interval containing $a$, then for every $x$ in this interval:

$$
E_{n}(x)=\frac{1}{n!}\int_{a}^{x}(x-t)^{n}f^{(n+1)}(t)\,dt. \tag{7.9}
$$

**Proof sketch (induction).** The case $n=1$ is Theorem 7.5. Assuming (7.9) holds for $n$, write Taylor's formula for $n+1$ and $n$ and subtract:

$$
E_{n+1}(x)=E_{n}(x)-\frac{f^{(n+1)}(a)}{(n+1)!}\,(x-a)^{n+1}.
$$

Using the integral for $E_{n}(x)$ and the identity $\dfrac{(x-a)^{n+1}}{n+1}=\int_{a}^{x}(x-t)^{n}\,dt$:

$$
E_{n+1}(x)=\frac{1}{n!}\int_{a}^{x}(x-t)^{n}\bigl[f^{(n+1)}(t)-f^{(n+1)}(a)\bigr]\,dt.
$$

Integration by parts with $u=f^{(n+1)}(t)-f^{(n+1)}(a)$ and $v=-\dfrac{(x-t)^{n+1}}{n+1}$ yields (7.9) with $n$ replaced by $n+1$. 鈭?
## 7.5 Estimates for the Error in Taylor's Formula

### 7.5.1 Error Bounds

**Theorem 7.7.** If $m\le f^{(n+1)}(t)\le M$ for all $t$ in an interval containing $a$, then for every $x$ in this interval:

- If $x>a$:
  $$
  m\frac{(x-a)^{n+1}}{(n+1)!}\le E_{n}(x)\le M\frac{(x-a)^{n+1}}{(n+1)!}.
  $$
- If $x<a$:
  $$
  m\frac{(a-x)^{n+1}}{(n+1)!}\le(-1)^{n+1}E_{n}(x)\le M\frac{(a-x)^{n+1}}{(n+1)!}.
  $$

**Proof idea.** Bound the integrand in the integral form of $E_{n}(x)$ and integrate. 鈭?
### 7.5.2 Example 鈥?Approximating $e$

For $f(x)=e^{x}$ at $a=0$ with $x=1$:

$$
e=\sum_{k=0}^{n}\frac{1}{k!}+E_{n}(1),\qquad\frac{1}{(n+1)!}\le E_{n}(1)<\frac{3}{(n+1)!}.
$$

Taking $n=12$ gives $2.718281826<e<2.718281833$, so $e\approx2.7182818$ (correct to 7 decimals).

### 7.5.3 Example 鈥?Irrationality of $e$

Multiplying the error bounds by $n!$:

$$
\frac{1}{n+1}\le n!\,e-\sum_{k=0}^{n}\frac{n!}{k!}<\frac{3}{n+1}\le\frac34\qquad(n\ge3).
$$

The sum is an integer. If $e$ were rational, $n!e$ would be an integer for large $n$, but the inequalities force the difference of two integers to be a positive number $\le\tfrac34$ 鈥?impossible. Hence $e$ is irrational.

### 7.5.4 Example 鈥?Approximating an Integral

For $\displaystyle\int_{0}^{1/2}e^{-t^{2}}\,dt$, use the Taylor polynomial of $e^{x}$ with $n=4$ and replace $x$ by $-t^{2}$:

$$
e^{-t^{2}}=1-t^{2}+\frac{t^{4}}{2!}-\frac{t^{6}}{3!}+\frac{t^{8}}{4!}+E_{4}(-t^{2}),
$$

where $-\dfrac{t^{10}}{5!}\le E_{4}(-t^{2})<0$. Integrating from $0$ to $\tfrac12$:

$$
\int_{0}^{1/2}e^{-t^{2}}\,dt=\frac12-\frac{1}{3\cdot2^{3}}+\frac{1}{5\cdot2^{5}\cdot2!}-\frac{1}{7\cdot2^{7}\cdot3!}+\frac{1}{9\cdot2^{9}\cdot4!}-\theta,
$$

with $0<\theta\le0.0000045$. Rounding to four decimals: $0.4613$.

## 7.6 Other Forms of the Remainder

### 7.6.1 Lagrange Form

Since $(x-t)^{n}$ does not change sign on $[a,x]$, the weighted mean-value theorem for integrals gives:

$$
E_{n}(x)=\frac{f^{(n+1)}(c)}{(n+1)!}\,(x-a)^{n+1}\qquad\text{for some }c\text{ between }a\text{ and }x.
$$

This is **Lagrange's form**; it resembles the earlier Taylor terms except the derivative is evaluated at an unknown point $c$.

### 7.6.2 Cauchy Form

Define $F(t)=f(t)+\sum_{k=1}^{n}\dfrac{f^{(k)}(t)}{k!}(x-t)^{k}$. Then $F(x)=f(x)$, $F(a)=T_{n}f(x;a)$, and:

$$
F'(t)=\frac{(x-t)^{n}}{n!}\,f^{(n+1)}(t).
$$

Apply Cauchy's mean-value formula to $F$ and an auxiliary function $G$ on $[a,x]$:

$$
E_{n}(x)=\frac{F'(c)}{G'(c)}\,\bigl[G(x)-G(a)\bigr]\qquad(a<c<x).
$$

- With $G(t)=(x-t)^{n+1}$: **Lagrange form** (as above).
- With $G(t)=x-t$: **Cauchy form**:
  $$
  E_{n}(x)=\frac{f^{(n+1)}(c)}{n!}\,(x-c)^{n}(x-a).
  $$
- With $G(t)=(x-t)^{p}$ ($p\ge1$): general form:
  $$
  E_{n}(x)=\frac{f^{(n+1)}(c)}{n!\,p}\,(x-c)^{n+1-p}(x-a)^{p}.
  $$

## 7.7 The o-Notation (Little-oh)

### 7.7.1 Definition

Assume $g(x) \neq 0$ for all $x \neq a$ in some interval containing $a$. The notation

$$
f(x) = o\bigl(g(x)\bigr) \quad \text{as} \quad x \to a
$$

means

$$
\lim_{x \to a} \frac{f(x)}{g(x)} = 0 .
$$

Read: "$f(x)$ is **little-oh** of $g(x)$" or "$f(x)$ is of **smaller order** than $g(x)$."

- $f(x) = o(1)$ as $x \to a$ $\;\Longleftrightarrow\;$ $f(x) \to 0$.
- $f(x) = o(x)$ as $x \to 0$ $\;\Longleftrightarrow\;$ $\dfrac{f(x)}{x} \to 0$.
- $f(x) = h(x) + o\bigl(g(x)\bigr)$ means $f(x) - h(x) = o\bigl(g(x)\bigr)$.

**Example.** $\sin x = x + o(x)$ as $x \to 0$, since $\dfrac{\sin x - x}{x} = \dfrac{\sin x}{x} - 1 \to 0$.

### 7.7.2 Taylor's Formula in o-Notation

If $f^{(n+1)}$ is continuous near $a$:

$$
f(x) = \sum_{k=0}^{n} \frac{f^{(k)}(a)}{k!}\,(x-a)^{k} + o\bigl((x-a)^{n}\bigr) \qquad \text{as } x \to a .
$$

**Common expansions** (as $x \to 0$):

| Function | Expansion |
|----------|-----------|
| $\dfrac{1}{1-x}$ | $1 + x + x^{2} + \cdots + x^{n} + o(x^{n})$ |
| $\log(1+x)$ | $x - \dfrac{x^{2}}{2} + \dfrac{x^{3}}{3} - \cdots + (-1)^{n-1}\dfrac{x^{n}}{n} + o(x^{n})$ |
| $e^{x}$ | $1 + x + \dfrac{x^{2}}{2!} + \cdots + \dfrac{x^{n}}{n!} + o(x^{n})$ |
| $\sin x$ | $x - \dfrac{x^{3}}{3!} + \dfrac{x^{5}}{5!} - \cdots + (-1)^{n-1}\dfrac{x^{2n-1}}{(2n-1)!} + o(x^{2n})$ |
| $\cos x$ | $1 - \dfrac{x^{2}}{2!} + \dfrac{x^{4}}{4!} - \cdots + (-1)^{n}\dfrac{x^{2n}}{(2n)!} + o(x^{2n+1})$ |
| $\arctan x$ | $x - \dfrac{x^{3}}{3} + \dfrac{x^{5}}{5} - \cdots + (-1)^{n-1}\dfrac{x^{2n-1}}{2n-1} + o(x^{2n})$ |

### 7.7.3 Algebra of o-Symbols

**Theorem 7.8.** As $x \to a$:

| Rule | Statement |
|------|-----------|
| (a) Addition | $o(g) \pm o(g) = o(g)$ |
| (b) Scalar | $o(cg) = o(g)$ $(c \neq 0)$ |
| (c) Product | $f \cdot o(g) = o(fg)$ |
| (d) Nesting | $o(o(g)) = o(g)$ |
| (e) Reciprocal | $\dfrac{1}{1+g(x)} = 1 - g(x) + o(g)$, if $g(x) \to 0$ |

**Example 1.** Prove $\tan x = x + \dfrac{1}{3}x^{3} + o(x^{3})$ as $x \to 0$.

*Solution.* Use $\sin x = x - \dfrac{x^{3}}{6} + o(x^{4})$ and $\cos x = 1 - \dfrac{x^{2}}{2} + o(x^{3})$. By (e):

$$
\frac{1}{\cos x} = \frac{1}{1 - \frac{1}{2}x^{2} + o(x^{3})} = 1 + \frac{1}{2}x^{2} + o(x^{2}) .
$$

Then:

$$
\tan x = \frac{\sin x}{\cos x} = \Bigl(x - \frac{x^{3}}{6} + o(x^{4})\Bigr)\Bigl(1 + \frac{x^{2}}{2} + o(x^{2})\Bigr) = x + \frac{1}{3}x^{3} + o(x^{3}) .
$$

**Example 2.** Prove $(1+x)^{1/x} = e\Bigl(1 - \dfrac{x}{2} + \dfrac{11x^{2}}{24} + o(x^{2})\Bigr)$ as $x \to 0$.

*Solution.* Write $(1+x)^{1/x} = \exp\!\Bigl(\dfrac{\log(1+x)}{x}\Bigr)$. Using $\log(1+x) = x - \dfrac{x^{2}}{2} + \dfrac{x^{3}}{3} + o(x^{3})$:

$$
\frac{\log(1+x)}{x} = 1 - \frac{x}{2} + \frac{x^{2}}{3} + o(x^{2}) .
$$

Set $u = -\dfrac{x}{2} + \dfrac{x^{2}}{3} + o(x^{2})$. Since $e^{u} = 1 + u + \dfrac{u^{2}}{2} + o(u^{2})$:

$$
e^{u} = 1 - \frac{x}{2} + \frac{x^{2}}{3} + o(x^{2}) + \frac{1}{2}\Bigl(-\frac{x}{2} + o(x)\Bigr)^{2} + o(x^{2}) = 1 - \frac{x}{2} + \frac{11x^{2}}{24} + o(x^{2}) .
$$

Hence $(1+x)^{1/x} = e \cdot e^{u}$ gives the desired result.

## 7.8 Applications to Indeterminate Forms

Taylor approximations and the $o$-notation are useful tools for evaluating limits of indeterminate forms such as $0/0$.

### 7.8.1 Example: $\displaystyle\lim_{x\to 0}\frac{a^{x}-b^{x}}{x}$

**Problem.** If $a,b>0$, determine $\displaystyle\lim_{x\to 0}\frac{a^{x}-b^{x}}{x}$.

*Solution.* Use $e^{t}=1+t+o(t)$ as $t\to 0$. Substitute $t=x\log a$ and $t=x\log b$:

$$
a^{x}=1+x\log a+o(x),\qquad b^{x}=1+x\log b+o(x).
$$

Subtract and divide by $x$:

$$
\frac{a^{x}-b^{x}}{x}=\log a-\log b+o(1)=\log\frac{a}{b}+o(1)\;\longrightarrow\;\log\frac{a}{b}.
$$

### 7.8.2 Example: $\displaystyle\lim_{x\to 0}\frac{1}{x}\Bigl(\cot x-\frac{1}{x}\Bigr)$

**Problem.** Prove the limit equals $-\dfrac{1}{3}$.

*Solution.* From $\tan x = x + \dfrac{1}{3}x^{3} + o(x^{3})$:

$$
\cot x = \frac{1}{\tan x} = \frac{1}{x}\cdot\frac{1}{1+\frac{1}{3}x^{2}+o(x^{2})} = \frac{1}{x}\Bigl(1-\frac{1}{3}x^{2}+o(x^{2})\Bigr) = \frac{1}{x}-\frac{1}{3}x+o(x).
$$

Hence:

$$
\frac{1}{x}\Bigl(\cot x-\frac{1}{x}\Bigr) = -\frac{1}{3}+o(1)\;\longrightarrow\;-\frac{1}{3}.
$$

### 7.8.3 Example: $\displaystyle\lim_{x\to 0}\frac{\log(1+ax)}{x}$

**Problem.** Prove the limit equals $a$ for every real $a$.

*Solution.* If $a=0$, trivial. For $a\neq 0$, use $\log(1+x)=x+o(x)$ and replace $x$ by $ax$:

$$
\log(1+ax)=ax+o(ax)=ax+o(x).
$$

Dividing by $x$ gives $a+o(1)\to a$.

### 7.8.4 Example: $\displaystyle\lim_{x\to 0}(1+ax)^{1/x}$

**Problem.** Prove $\displaystyle\lim_{x\to 0}(1+ax)^{1/x}=e^{a}$ for every real $a$.

*Solution.* Write $(1+ax)^{1/x}=\exp\!\Bigl(\dfrac{\log(1+ax)}{x}\Bigr)$. By Example 3, the exponent tends to $a$; by continuity of $\exp$, the limit is $e^{a}$.

> **Related limit.** Replacing $ax$ by $y$:
> $$
> \lim_{y\to 0}(1+y)^{a/y}=e^{a}.
> $$
> These relations are sometimes taken as starting points for the theory of the exponential function.

## 7.9 L'H么pital's Rule for the Indeterminate Form $0/0$

### 7.9.1 Motivation

For $\dfrac{f(x)}{g(x)}$ with $f(a)=g(a)=0$:

$$
\frac{f(x)}{g(x)}=\frac{f(x)-f(a)}{g(x)-g(a)}=\frac{\dfrac{f(x)-f(a)}{x-a}}{\dfrac{g(x)-g(a)}{x-a}}\;\longrightarrow\;\frac{f'(a)}{g'(a)}
$$

provided $f'(a), g'(a)$ exist and $g'(a)\neq 0$.

### 7.9.2 Theorem 7.9 鈥?L'H么pital's Rule ($0/0$)

Assume $f$ and $g$ have derivatives $f'(x), g'(x)$ at each point of an open interval $(a, b)$, and:

1. $\displaystyle\lim_{x\to a+}f(x)=0$ and $\displaystyle\lim_{x\to a+}g(x)=0$,
2. $g'(x)\neq 0$ for all $x\in(a,b)$,
3. $\displaystyle\lim_{x\to a+}\dfrac{f'(x)}{g'(x)}=L$.

Then $\displaystyle\lim_{x\to a+}\dfrac{f(x)}{g(x)}$ also exists and equals $L$.

> The theorem also holds for **left-handed** limits $(x\to a-)$ and **two-sided** limits $(x\to a)$.

### 7.9.3 Examples

| # | Limit | Key Step | Result |
|---|-------|----------|--------|
| 1 | $\displaystyle\lim_{x\to 0}\dfrac{\sin x}{x}$ | $\dfrac{\cos x}{1}\to 1$ | $1$ |
| 2 | $\displaystyle\lim_{x\to 0}\dfrac{x-\tan x}{x-\sin x}$ | Apply twice; cancel $1-\cos x$ | $-2$ |
| 3 | $\displaystyle\lim_{x\to 1}\dfrac{x^{c}-cx+c-1}{(x-1)^{2}}$ | Two applications | $\dfrac{c(c-1)}{2}$ |
| 6 | $\displaystyle\lim_{x\to 0+}\dfrac{\sqrt{x}}{1-e^{2\sqrt{x}}}$ | Substitute $t=\sqrt{x}$ | $-\dfrac{1}{2}$ |

**Example 2 (detail).** Let $f(x)=x-\tan x$, $g(x)=x-\sin x$. Then:

$$
\frac{f'(x)}{g'(x)}=\frac{1-\sec^{2}x}{1-\cos x}=\frac{-\tan^{2}x}{1-\cos x}=\frac{-\sin^{2}x}{\cos^{2}x(1-\cos x)}=-\frac{1+\cos x}{\cos^{2}x}\to -2.
$$

### 7.9.4 Caveats

- **Not infallible.** For $f(x)=e^{-1/x}$ ($x\neq 0$) and $g(x)=x$ as $x\to 0+$:
  $$
  \frac{f'(x)}{g'(x)}=\frac{x^{-2}e^{-1/x}}{1}=\frac{e^{-1/x}}{x^{2}},
  $$
  and repeated differentiation never resolves the indeterminacy.
- **Check the form.** A common error:
  $$
  \lim_{x\to 1}\frac{3x^{2}-2x-1}{x^{2}-x}=\lim_{x\to 1}\frac{6x-2}{2x-1}=\lim_{x\to 1}\frac{6}{2}=3\quad\text{(wrong!)}.
  $$
  The second step is invalid because $\dfrac{6x-2}{2x-1}$ is **not** $0/0$ at $x=1$. The correct limit is $4$.

### 7.9.5 Proof (Cauchy's Mean-Value Theorem)

Define $F(x)=f(x)$ for $x\neq a$, $F(a)=0$; similarly $G(x)=g(x)$ for $x\neq a$, $G(a)=0$. Both are continuous on $[a,x]$ and differentiable on $(a,x)$. By Cauchy's mean-value theorem:

$$
[F(x)-F(a)]G'(c)=[G(x)-G(a)]F'(c)\quad\text{for some }c\in(a,x).
$$

Since $F(a)=G(a)=0$ and $G'(c)=g'(c)\neq 0$, $g(x)\neq 0$:

$$
\frac{f(x)}{g(x)}=\frac{F'(c)}{G'(c)}=\frac{f'(c)}{g'(c)}.
$$

As $x\to a+$, we have $c\to a+$, so the right side tends to $L$; hence $f(x)/g(x)\to L$.

## 7.10 The Symbols $+\infty$ and $-\infty$; Extension of L'H么pital's Rule

### 7.10.1 Limits at Infinity

**Definition.** $\displaystyle\lim_{x\to+\infty}f(x)=A$ means:

> For every $\epsilon>0$, there exists $M>0$ such that $|f(x)-A|<\epsilon$ whenever $x>M$.

Similarly, $\displaystyle\lim_{x\to-\infty}f(x)=A$ means $|f(x)-A|<\epsilon$ whenever $x<-M$.

**Equivalence via substitution.** Let $F(t)=f(1/t)$ for $t\neq 0$. Then:

$$
\lim_{x\to+\infty}f(x)=A\quad\Longleftrightarrow\quad\lim_{t\to 0+}F(t)=A,
$$

$$
\lim_{x\to-\infty}f(x)=A\quad\Longleftrightarrow\quad\lim_{t\to 0-}F(t)=A.
$$

All usual limit rules (sum, product, quotient, composition) extend to $x\to\pm\infty$.

### 7.10.2 Theorem 7.10 鈥?L'H么pital's Rule at Infinity ($0/0$)

Assume $f$ and $g$ have derivatives for all $x>M$ (some $M>0$), and:

1. $\displaystyle\lim_{x\to+\infty}f(x)=0$ and $\displaystyle\lim_{x\to+\infty}g(x)=0$,
2. $g'(x)\neq 0$ for $x>M$,
3. $\displaystyle\lim_{x\to+\infty}\dfrac{f'(x)}{g'(x)}=L$.

Then:

$$
\lim_{x\to+\infty}\frac{f(x)}{g(x)}=L.
$$

> An analogous result holds for $x\to-\infty$.

**Proof sketch.** Set $F(t)=f(1/t)$, $G(t)=g(1/t)$. As $x\to+\infty$, $t=1/x\to 0+$. By the chain rule:

$$
F'(t)=-\frac{1}{t^{2}}f'\!\Bigl(\frac{1}{t}\Bigr),\qquad G'(t)=-\frac{1}{t^{2}}g'\!\Bigl(\frac{1}{t}\Bigr).
$$

The factor $-1/t^{2}$ cancels in $F'/G'$, giving $F'(t)/G'(t)=f'(x)/g'(x)\to L$. Apply Theorem 7.9 to $F/G$ as $t\to 0+$.

## 7.11 Infinite Limits

### 7.11.1 Definition

**$\lim_{x\to a}f(x)=+\infty$.** To every $M>0$, there corresponds $\delta>0$ such that:

$$
f(x)>M\qquad\text{whenever}\quad 0<|x-a|<\delta.
$$

**One-sided variants.**
- $\displaystyle\lim_{x\to a+}f(x)=+\infty$: require $0<x-a<\delta$.
- $\displaystyle\lim_{x\to a-}f(x)=+\infty$: require $0<a-x<\delta$.

**$-\infty$.** Replace $f(x)>M$ by $f(x)<-M$ in the above definitions.

### 7.11.2 Infinite Limits at Infinity

| Symbol | Meaning |
|--------|---------|
| $\displaystyle\lim_{x\to+\infty}f(x)=+\infty$ | $f(x)>M$ whenever $x>X$ (for some $X$) |
| $\displaystyle\lim_{x\to+\infty}f(x)=-\infty$ | $f(x)<-M$ whenever $x>X$ |
| $\displaystyle\lim_{x\to-\infty}f(x)=+\infty$ | $f(x)>M$ whenever $x<-X$ |
| $\displaystyle\lim_{x\to-\infty}f(x)=-\infty$ | $f(x)<-M$ whenever $x<-X$ |

### 7.11.3 Examples

| Limit | Reason |
|-------|--------|
| $\displaystyle\lim_{x\to+\infty}\log x=+\infty$ | $\log$ is increasing and unbounded on $(0,+\infty)$ |
| $\displaystyle\lim_{x\to 0+}\log x=-\infty$ | $\log x<0$ for $0<x<1$; no lower bound near $0$ |
| $\displaystyle\lim_{x\to+\infty}e^{x}=+\infty$ | From $\log$ above and inverse relation |
| $\displaystyle\lim_{x\to-\infty}e^{x}=0$ | Equivalent to $\displaystyle\lim_{x\to+\infty}e^{-x}=0$ |
| $\displaystyle\lim_{x\to+\infty}x^{\alpha}=+\infty\;(\\alpha>0)$ | Write $x^{\alpha}=e^{\alpha\log x}$ |
| $\displaystyle\lim_{x\to+\infty}x^{-\alpha}=0$ | Reciprocal of the above |
| $\displaystyle\lim_{x\to 0-}e^{-1/x}=+\infty$ | $-1/x\to+\infty$ as $x\to 0-$ |
| $\displaystyle\lim_{x\to 0+}e^{-1/x}=0$ | $-1/x\to-\infty$ as $x\to 0+$ |

## 7.12 The Behavior of $\log x$ and $e^{x}$ for Large $x$

### 7.12.1 Theorem 7.11 鈥?Growth Hierarchy

If $a>0$ and $b>0$:

$$
\lim_{x\to+\infty}\frac{(\log x)^{b}}{x^{a}}=0\qquad\text{and}\qquad\lim_{x\to+\infty}\frac{x^{b}}{e^{ax}}=0.
$$

In $o$-notation:

$$
(\log x)^{b}=o(x^{a}),\qquad x^{b}=o(e^{ax})\qquad\text{as }x\to+\infty.
$$

> **Intuition.** Powers of $\log$ grow slower than any positive power of $x$, which in turn grows slower than any exponential $e^{ax}$.

**Proof of (7.31).** For $c>0$ and $x>1$:

$$
0<\log x=\int_{1}^{x}\frac{1}{t}\,dt\le\int_{1}^{x}t^{c-1}\,dt=\frac{x^{c}-1}{c}<\frac{x^{c}}{c}.
$$

Hence $0<\dfrac{(\log x)^{b}}{x^{a}}<\dfrac{x^{bc-a}}{c^{b}}$. Choose $c=\dfrac{a}{2b}$; then $bc-a=-a/2<0$, so the right side tends to $0$.

**Proof of (7.32).** Substitute $t=e^{x}$; then $x=\log t$ and:

$$
\frac{x^{b}}{e^{ax}}=\frac{(\log t)^{b}}{t^{a}}\to 0\quad\text{as }t\to+\infty.
$$

### 7.12.2 Other Indeterminate Forms

Algebraic manipulation often reduces these to $0/0$ or $\infty/\infty$.

| Form | Example | Technique | Result |
|------|---------|-----------|--------|
| $0\cdot\infty$ | $\displaystyle\lim_{x\to 0+}x^{\alpha}\log x$ $(\alpha>0)$ | Set $t=1/x$; use Theorem 7.11 | $0$ |
| $0^{0}$ | $\displaystyle\lim_{x\to 0+}x^{x}$ | Write $x^{x}=e^{x\log x}$; use Example 2 | $1$ |
| $\infty^{0}$ | $\displaystyle\lim_{x\to+\infty}x^{1/x}$ | Set $t=1/x$; reduce to Example 3 | $1$ |
| $1^{\infty}$ | $\displaystyle\lim_{x\to+\infty}\Bigl(1+\frac{a}{x}\Bigr)^{x}$ | Replace $x$ by $1/x$ in $\lim_{x\to 0}(1+ax)^{1/x}=e^{a}$ | $e^{a}$ |
| $1^{\infty}$ | $\displaystyle\lim_{x\to+\infty}\Bigl(1+\frac{1}{x}\Bigr)^{ax}$ | Same trick | $e^{a}$ |

**General method.** For $f(x)^{g(x)}$, write:

$$
f(x)^{g(x)}=\exp\!\bigl(g(x)\log f(x)\bigr)
$$

and evaluate the exponent $g(x)\log f(x)$ by earlier methods.

# 8. Introduction to Differential Equations

## 8.1 Introduction

A **differential equation** is an equation involving at least one derivative of an unknown function.

### 8.1.1 Classification

| Type | Unknown | Example |
|------|---------|---------|
| **Ordinary** (ODE) | Function of **one** variable | $f'(x)=f(x)$ |
| **Partial** (PDE) | Function of **two or more** variables | $\dfrac{\partial^{2}f}{\partial x^{2}}+\dfrac{\partial^{2}f}{\partial y^{2}}=0$ (Laplace's equation) |

### 8.1.2 First Example 鈥?The Exponential ODE

$$
f'(x)=f(x).
$$

- Particular solution: $f(x)=e^{x}$.
- **General solution:** $f(x)=Ce^{x}$ for arbitrary constant $C$.

### 8.1.3 A Partial-Differential Equation 鈥?Laplace's Equation

$$
\frac{\partial^{2}f}{\partial x^{2}}+\frac{\partial^{2}f}{\partial y^{2}}=0.
$$

This appears in electromagnetism, fluid mechanics, and elsewhere. Sample solutions:

- $f(x,y)=x+2y$
- $f(x,y)=e^{x}\cos y$
- $f(x,y)=\log(x^{2}+y^{2})$

### 8.1.4 Historical Note

- Originated in the 17th century from problems in **geometry and mechanics**.
- Early contributors: Newton, Leibniz, the Bernoullis.
- Two main strands of study:
  1. **Special tricks** (exact equations, substitutions, etc.) 鈥?discussed later in this chapter.
  2. **Linear differential equations** 鈥?the most widely occurring type; a fuller treatment appears in Volume II.

## 8.2 Terminology and Notation

### 8.2.1 Standard Notation

- $y$ in place of $f(x)$; $y', y'', y'''$ for derivatives.
- Other letters ($u, v, z$) may also be used.

### 8.2.2 Order of a Differential Equation

The **order** is the order of the highest derivative appearing.

| Equation | Order |
|----------|-------|
| $y'=y$ | First-order |
| $y''=x^{3}y+\sin(xy')$ | Second-order |

### 8.2.3 First-Order Equations

General form:

$$
y'=f(x,y).
$$

A differentiable function $y=Y(x)$ is a **solution** on an interval $I$ if:

$$
Y'(x)=f\bigl[x,Y(x)\bigr]\quad\text{for all }x\in I.
$$

### 8.2.4 The Simplest Case 鈥?$y'=Q(x)$

When $f(x,y)$ is independent of $y$:

$$
y'=Q(x).
$$

Every solution is given by:

$$
y=\int Q(x)\,dx+C,
$$

where $C$ is an arbitrary constant of integration. Even if the integral cannot be expressed in terms of elementary functions, the equation is regarded as solved if the solution is written as an integral of a known function.

## 8.3 A First-Order Differential Equation for the Exponential Function

### 8.3.1 Theorem 8.1 鈥?Existence and Uniqueness

**Statement.** If $C$ is a given real number, there is **one and only one** function $f$ satisfying:

$$
f'(x)=f(x)\quad\text{for all }x,\qquad f(0)=C.
$$

This function is $f(x)=Ce^{x}$.

**Proof.**

- *Verification.* $f(x)=Ce^{x}$ clearly satisfies $f'=f$ and $f(0)=C$.
- *Uniqueness.* Let $g$ be any solution and define $h(x)=g(x)e^{-x}$. Then:
  $$
  h'(x)=g'(x)e^{-x}-g(x)e^{-x}=e^{-x}[g'(x)-g(x)]=0.
  $$
  By the zero-derivative theorem, $h$ is constant. Since $h(0)=g(0)e^{0}=C$, we have $h(x)\equiv C$, hence $g(x)=Ce^{x}$.

> Theorem 8.1 is the simplest example of an **existence-uniqueness theorem**.

### 8.3.2 Initial-Value Problems

In solving a first-order ODE, integration removes $y'$ and introduces an arbitrary constant $C$. The way $C$ enters depends on the equation (additive, as in $y=\int Q+C$, or multiplicative, as in $y=Ce^{x}$).

An **initial-value problem** asks for the particular solution satisfying $y(x_{0})=y_{0}$ at some point. This terminology comes from mechanics, where the prescribed value is the displacement at an initial time.

## 8.4 First-Order Linear Differential Equations

### 8.4.1 Standard Form

$$
y'+P(x)y=Q(x),
$$

where $P,Q$ are continuous on an open interval $I$.

- **Nonhomogeneous** when $Q\not\equiv 0$.
- **Homogeneous (reduced)** when $Q\equiv 0$:
  $$
  y'+P(x)y=0.
  $$

### 8.4.2 Solving the Homogeneous Equation

If $y\neq 0$ on $I$, divide by $y$:

$$
\frac{y'}{y}=-P(x)\quad\Longrightarrow\quad D\log y=-P(x).
$$

Hence:

$$
y=e^{-A(x)},\qquad A(x)=\int P(x)\,dx-C.
$$

**Theorem 8.2.** Let $P$ be continuous on $I$, $a\in I$, $b\in\mathbb{R}$. The initial-value problem

$$
y'+P(x)y=0,\quad f(a)=b
$$

has the **unique** solution on $I$:

$$
f(x)=b\,e^{-A(x)},\qquad A(x)=\int_{a}^{x}P(t)\,dt.
$$

**Proof.** Define $h(x)=g(x)e^{A(x)}$ for any solution $g$. Then $h'(x)=e^{A(x)}[g'(x)+P(x)g(x)]=0$, so $h$ is constant. Since $h(a)=g(a)=b$, we get $g(x)=b\,e^{-A(x)}$.

### 8.4.3 Solving the Nonhomogeneous Equation

Let $g$ satisfy $y'+P(x)y=Q(x)$ and set $h(x)=g(x)e^{A(x)}$ with $A(x)=\int_{a}^{x}P(t)\,dt$. Then:

$$
h'(x)=e^{A(x)}Q(x).
$$

By the second FTC:

$$
h(x)=h(a)+\int_{a}^{x}e^{A(t)}Q(t)\,dt.
$$

Since $h(a)=g(a)$, every solution of (8.5) has the form:

$$
g(x)=g(a)\,e^{-A(x)}+e^{-A(x)}\int_{a}^{x}Q(t)\,e^{A(t)}\,dt.
$$

**Theorem 8.3.** Let $P,Q$ be continuous on $I$, $a\in I$, $b\in\mathbb{R}$. The initial-value problem

$$
y'+P(x)y=Q(x),\quad f(a)=b
$$

has the **unique** solution on $I$:

$$
f(x)=b\,e^{-A(x)}+e^{-A(x)}\int_{a}^{x}Q(t)\,e^{A(t)}\,dt,\qquad A(x)=\int_{a}^{x}P(t)\,dt.
$$

### 8.4.4 Example

**Problem.** Find all solutions of $xy'+(1-x)y=e^{2x}$ on $(0,+\infty)$.

*Solution.* Divide by $x$:

$$
y'+\Bigl(\frac{1}{x}-1\Bigr)y=\frac{e^{2x}}{x},\qquad P(x)=\frac{1}{x}-1,\;Q(x)=\frac{e^{2x}}{x}.
$$

Take $a=1$ and compute:

$$
A(x)=\int_{1}^{x}\Bigl(\frac{1}{t}-1\Bigr)dt=\log x-(x-1).
$$

Hence $e^{-A(x)}=\dfrac{e^{x-1}}{x}$ and $e^{A(t)}=te^{1-t}$. By Theorem 8.3 with $f(1)=b$:

$$
f(x)=b\,\frac{e^{x-1}}{x}+\frac{e^{x-1}}{x}\int_{1}^{x}\frac{e^{2t}}{t}\cdot te^{1-t}\,dt
=b\,\frac{e^{x-1}}{x}+\frac{e^{x}}{x}(e^{x}-e).
$$

Simplifying:

$$
f(x)=\frac{e^{2x}+Ce^{x}}{x},\qquad C=be^{-1}-e.
$$

**Behavior near $x=0$.** Using $e^{2x}=1+2x+o(x)$ and $e^{x}=1+x+o(x)$:

$$
f(x)=\frac{(1+C)+(2+C)x+o(x)}{x}=\frac{1+C}{x}+(2+C)+o(1).
$$

Only the solution with $C=-1$ tends to a finite limit as $x\to 0$; that limit is $1$.

## 8.5 Physical Applications of First-Order Linear ODEs

### 8.5.1 Radioactive Decay

**Model.** $y'=-ky$ $(k>0)$.

**Solution.** $f(t)=f(0)\,e^{-kt}$.

**Half-life.** Time $T$ for which $f(T)/f(0)=\frac{1}{2}$:

$$
T=\frac{\log 2}{k}.
$$

### 8.5.2 Falling Body in a Resisting Medium

**Forces.** Gravity $mg$ downward; air resistance $-kv$ upward.

**Equation (velocity).**

$$
v'+\frac{k}{m}v=g.
$$

**Solution** (released from rest, $v(0)=0$):

$$
v(t)=\frac{mg}{k}\bigl(1-e^{-kt/m}\bigr).
$$

- **Terminal velocity:** $v\to\dfrac{mg}{k}$ as $t\to+\infty$.
- With initial velocity $v_{0}$: $v(t)=\dfrac{mg}{k}\bigl(1-e^{-kt/m}\bigr)+v_{0}\,e^{-kt/m}$.

**Equation (displacement).** $s'=v$ gives:

$$
s(t)=\frac{mg}{k}\,t+\frac{gm^{2}}{k^{2}}\bigl(e^{-kt/m}-1\bigr)\qquad(s(0)=0).
$$

### 8.5.3 Newton's Law of Cooling

**Model.** Rate of temperature change proportional to difference from surrounding temperature $M(t)$:

$$
y'=-k\bigl[y-M(t)\bigr]\quad\text{or}\quad y'+ky=kM(t).
$$

**General solution** ($f(a)=b$):

$$
f(t)=b\,e^{-kt}+e^{-kt}\int_{a}^{t}kM(u)\,e^{ku}\,du.
$$

**Example.** Body cools from $200^{\circ}$ to $100^{\circ}$ in 40 min; surrounding temperature $M=10^{\circ}$.

- $f(0)=200$ $\Rightarrow$ $f(t)=10+190\,e^{-kt}$.
- $f(40)=100$ $\Rightarrow$ $k=\dfrac{\log 19-\log 9}{40}$.
- If $M=5^{\circ}$: $f(t)=5+195\,e^{-kt}$; time to reach $100^{\circ}$ is $40\,\dfrac{\log 39-\log 19}{\log 19-\log 9}\approx 38.5$ min.

### 8.5.4 A Dilution Problem

**Setup.** Tank: 100 gal brine at 2.5 lb/gal. Inflow: 2 lb/gal at 5 gal/min. Outflow: 5 gal/min.

**Model.**

$$
y'+\frac{1}{20}y=10,\qquad y(0)=250.
$$

**Solution.**

$$
y(t)=200+50\,e^{-t/20}.
$$

- $y(t)>200$ for all $t$; $y\to 200$ as $t\to+\infty$.

### 8.5.5 Electric Circuits (RL Circuit)

**Kirchhoff's voltage law.**

$$
LI'(t)+RI(t)=V(t).
$$

**General solution** ($I(0)$ given):

$$
I(t)=I(0)\,e^{-Rt/L}+e^{-Rt/L}\int_{0}^{t}\frac{V(x)}{L}\,e^{Rx/L}\,dx.
$$

**Constant voltage** $V(t)\equiv E$:

$$
I(t)=\frac{E}{R}+\Bigl(I(0)-\frac{E}{R}\Bigr)e^{-Rt/L}.
$$

| Term | Name | Behavior as $t\to+\infty$ |
|------|------|---------------------------|
| $\dfrac{E}{R}$ | **Steady-state current** | Constant |
| $\Bigl(I(0)-\dfrac{E}{R}\Bigr)e^{-Rt/L}$ | **Transient current** | Decays to $0$ |

> **Analog computer.** A physical problem modeled by $y'+ay=Q$ can be simulated by an RL circuit with $R/L=a$ and impressed voltage $LQ$, allowing numerical data to be obtained by electrical measurement.

## 8.6 Linear Equations of Second Order with Constant Coefficients

### 8.6.1 General Form

A **second-order linear** differential equation has the form:

$$
y''+P_{1}(x)y'+P_{2}(x)y=R(x).
$$

- **Coefficients:** $P_{1}, P_{2}$.
- **Homogeneous** when $R(x)\equiv 0$.

This chapter treats only the case where $P_{1}, P_{2}$ are **constants**.

### 8.6.2 The Homogeneous Equation

$$
y''+ay'+by=0.
$$

> First completely solved by Euler (1743). It arises in a wide variety of applied problems.

## 8.7 Existence of Solutions of $y''+by=0$

We seek nontrivial solutions on $(-\infty,+\infty)$. The trivial solution $y\equiv 0$ always exists.

### 8.7.1 Example 1: $y''=0$

Here $a=b=0$. Integrating twice:

$$
y=c_{1}x+c_{2}.
$$

Conversely, every linear polynomial satisfies $y''=0$; these are **all** solutions.

### 8.7.2 Example 2: $y''+by=0$ with $b<0$

Write $b=-k^{2}$ $(k>0)$; the equation becomes $y''=k^{2}y$.

By inspection, $y=e^{kx}$ and $y=e^{-kx}$ are solutions. Hence:

$$
y=c_{1}e^{kx}+c_{2}e^{-kx}
$$

is a solution for arbitrary constants $c_{1},c_{2}$. (Theorem 8.6 will show this includes **all** solutions.)

### 8.7.3 Example 3: $y''+by=0$ with $b>0$

Write $b=k^{2}$ $(k>0)$; the equation becomes $y''=-k^{2}y$.

By inspection, $y=\cos kx$ and $y=\sin kx$ are solutions. Hence:

$$
y=c_{1}\cos kx+c_{2}\sin kx
$$

is a solution for arbitrary constants $c_{1},c_{2}$. (Theorem 8.6 will show this includes **all** solutions.)

## 8.8 Reduction of $y''+ay'+by=0$ to $y''+by=0$

### 8.8.1 The Substitution $y=uv$

Let $y=uv$. Then:

$$
y''+ay'+by=(v''+av'+bv)u+(2v'+av)u'+vu''.
$$

Choose $v$ so that the coefficient of $u'$ vanishes: $2v'+av=0$, i.e.:

$$
v=e^{-ax/2}.
$$

For this $v$: $v''=\dfrac{a^{2}v}{4}$, and:

$$
v''+av'+bv=\frac{a^{2}v}{4}-\frac{a^{2}v}{2}+bv=\frac{4b-a^{2}}{4}\,v.
$$

Hence:

$$
y''+ay'+by=\Bigl(u''+\frac{4b-a^{2}}{4}\,u\Bigr)v.
$$

### 8.8.2 Theorem 8.4

Let $y=ue^{-ax/2}$. Then on $(-\infty,+\infty)$:

$$
y''+ay'+by=0\quad\Longleftrightarrow\quad u''+\frac{4b-a^{2}}{4}\,u=0.
$$

> This reduces the general equation to the special case $u''+\lambda u=0$ already solved in Section 8.7.

## 8.9 Uniqueness Theorem for $y''+by=0$

### 8.9.1 Theorem 8.5

Assume $f$ and $g$ satisfy $y''+by=0$ on $(-\infty,+\infty)$ and:

$$
f(0)=g(0),\qquad f'(0)=g'(0).
$$

Then $f(x)=g(x)$ for all $x$.

### 8.9.2 Proof Sketch

Set $h=f-g$. Then $h$ satisfies $y''+by=0$ with $h(0)=h'(0)=0$.

**Step 1 鈥?Derivatives at $0$.** By repeated differentiation:

$$
y^{(2n)}=(-1)^{n}b^{n}y,\qquad y^{(2n-1)}=(-1)^{n-1}b^{n-1}y'.
$$

Since $h(0)=h'(0)=0$, all derivatives $h^{(n)}(0)=0$.

**Step 2 鈥?Taylor polynomials.** Every Taylor polynomial of $h$ at $0$ has all coefficients zero.

**Step 3 鈥?Remainder estimate.** By Taylor's formula with remainder (Theorem 7.6):

$$
h(x)=E_{2n-1}(x).
$$

On $[-c,c]$, $|h(x)|\le M$ implies $|h^{(2n)}(x)|\le M|b|^{n}$. By Theorem 7.7:

$$
0\le|h(x)|\le\frac{M\,|b|^{n}\,c^{2n}}{(2n)!}=\frac{MA^{2n}}{(2n)!},\qquad A=|b|^{1/2}c.
$$

Since $\dfrac{A^{m}}{m!}\to 0$ as $m\to+\infty$, we get $h(x)=0$ on $[-c,c]$. As $c$ is arbitrary, $h(x)\equiv 0$.

> The choice of $0$ is inessential; the theorem holds with initial data prescribed at any point $c$.

## 8.10 Complete Solution of $y''+by=0$

### 8.10.1 Theorem 8.6

Given $b\in\mathbb{R}$, define $u_{1},u_{2}$ on $(-\infty,+\infty)$:

| Case | $b$ | $u_{1}(x)$ | $u_{2}(x)$ |
|------|-----|-----------|-----------|
| (a) | $0$ | $1$ | $x$ |
| (b) | $<0$ ($b=-k^{2}$) | $e^{kx}$ | $e^{-kx}$ |
| (c) | $>0$ ($b=k^{2}$) | $\cos kx$ | $\sin kx$ |

Then **every** solution of $y''+by=0$ has the form:

$$
y=c_{1}u_{1}(x)+c_{2}u_{2}(x).
$$

**Proof idea.** For any solution $f$, solve:

$$
c_{1}u_{1}(0)+c_{2}u_{2}(0)=f(0),\qquad c_{1}u_{1}'(0)+c_{2}u_{2}'(0)=f'(0)
$$

for $c_{1},c_{2}$. Then $f$ and $c_{1}u_{1}+c_{2}u_{2}$ are solutions with the same value and derivative at $0$; by uniqueness (Theorem 8.5), they coincide everywhere.

## 8.11 Complete Solution of $y''+ay'+by=0$

### 8.11.1 Theorem 8.7

Let $d=a^{2}-4b$ be the **discriminant**. Then every solution has the form:

$$
y=e^{-ax/2}\bigl[c_{1}u_{1}(x)+c_{2}u_{2}(x)\bigr],
$$

where $u_{1},u_{2}$ depend on the sign of $d$:

| Case | Discriminant | $k$ | $u_{1}(x)$ | $u_{2}(x)$ | General solution |
|------|-------------|-----|-----------|-----------|-----------------|
| (a) | $d=0$ | 鈥?| $1$ | $x$ | $y=e^{-ax/2}(c_{1}+c_{2}x)$ |
| (b) | $d>0$ | $\frac{1}{2}\sqrt{d}$ | $e^{kx}$ | $e^{-kx}$ | $y=c_{1}e^{r_{1}x}+c_{2}e^{r_{2}x}$ |
| (c) | $d<0$ | $\frac{1}{2}\sqrt{-d}$ | $\cos kx$ | $\sin kx$ | $y=e^{-ax/2}(c_{1}\cos kx+c_{2}\sin kx)$ |

In case (b), $r_{1,2}=\dfrac{-a\pm\sqrt{d}}{2}$ are the roots of the **characteristic equation**:

$$
r^{2}+ar+b=0.
$$

> **Note on complex roots.** When $d<0$, the roots $r_{1},r_{2}$ are complex. The form with $\cos$ and $\sin$ is equivalent to a linear combination of $e^{r_{1}x}$ and $e^{r_{2}x}$ once the exponential is extended to complex numbers (Chapter 9).

### 8.11.2 Basis and General Solution

The pair:

$$
v_{1}=e^{-ax/2}u_{1},\qquad v_{2}=e^{-ax/2}u_{2}
$$

is a **basis** for the solution space: every solution is a linear combination of $v_{1}$ and $v_{2}$.

- A differential equation has more than one basis. Example: $y''=9y$ has bases $\{e^{3x},e^{-3x}\}$ and $\{\cosh 3x,\sinh 3x\}$.
- **Test.** $v_{1},v_{2}$ form a basis iff $v_{2}/v_{1}$ is **not** constant.

## 8.12 Nonhomogeneous Linear Equations of Second Order with Constant Coefficients

### 8.12.1 Operator Notation

Define the linear operator:

$$
L(f)=f''+af'+bf.
$$

Then the equation becomes $L(y)=R$. The operator $L$ is **linear**:

$$
L(c_{1}y_{1}+c_{2}y_{2})=c_{1}L(y_{1})+c_{2}L(y_{2}).
$$

If $y_{1},y_{2}$ both satisfy $L(y)=R$, then $L(y_{2}-y_{1})=R-R=0$; hence $y_{2}-y_{1}$ solves the homogeneous equation $L(y)=0$.

### 8.12.2 Theorem 8.8 鈥?General Solution Structure

If $y_{1}$ is a **particular solution** of $L(y)=R$, then the **general solution** is:

$$
y=c_{1}v_{1}+c_{2}v_{2}+y_{1},
$$

where $c_{1}v_{1}+c_{2}v_{2}$ is the general solution of $L(y)=0$.

### 8.12.3 Theorem 8.9 鈥?Variation of Parameters

Let $v_{1},v_{2}$ be a basis of solutions of $L(y)=0$. Define the **Wronskian**:

$$
W(x)=v_{1}(x)v_{2}'(x)-v_{2}(x)v_{1}'(x)\quad(\neq 0\text{ everywhere}).
$$

Then a particular solution of $L(y)=R$ is:

$$
y_{1}(x)=t_{1}(x)v_{1}(x)+t_{2}(x)v_{2}(x),
$$

where:

$$
t_{1}(x)=-\int\frac{v_{2}(x)R(x)}{W(x)}\,dx,\qquad t_{2}(x)=\int\frac{v_{1}(x)R(x)}{W(x)}\,dx.
$$

**Derivation.** Impose $t_{1}'v_{1}+t_{2}'v_{2}=0$. Then $y_{1}'=t_{1}v_{1}'+t_{2}v_{2}'$ and $y_{1}''=t_{1}v_{1}''+t_{2}v_{2}''+t_{1}'v_{1}'+t_{2}'v_{2}'$. Since $L(v_{1})=L(v_{2})=0$, we get $L(y_{1})=t_{1}'v_{1}'+t_{2}'v_{2}'=R$. Solving the algebraic system:

$$
t_{1}'=-\frac{v_{2}R}{W},\qquad t_{2}'=\frac{v_{1}R}{W}.
$$

> **History.** First used by Johann Bernoulli (1697) for first-order equations; extended by Lagrange (1774) to second order.

### 8.12.4 Example: $y''+y=\tan x$

On $(-\pi/2,\pi/2)$: $v_{1}=\cos x$, $v_{2}=\sin x$, $W=1$.

$$
t_{1}=-\int\sin x\tan x\,dx=\sin x-\log\bigl|\sec x+\tan x\bigr|,\qquad
 t_{2}=\int\cos x\tan x\,dx=-\cos x.
$$

Particular solution:

$$
y_{1}=t_{1}\cos x+t_{2}\sin x=-\cos x\,\log\bigl|\sec x+\tan x\bigr|.
$$

**General solution:**

$$
y=c_{1}\cos x+c_{2}\sin x-\cos x\,\log\bigl|\sec x+\tan x\bigr|.
$$

## 8.13 Special Methods for Particular Solutions (Undetermined Coefficients)

### 8.13.1 Case 1 鈥?$R(x)$ Is a Polynomial

If $R$ is a polynomial of degree $n$:

| Condition | Trial form for $y_{1}$ |
|-----------|------------------------|
| $b\neq 0$ | Polynomial of degree $n$ |
| $b=0$, $a\neq 0$ | Polynomial of degree $n+1$ |
| $a=b=0$ | Polynomial of degree $n+2$ (integrate twice) |

**Example.** $y''+y=x^{3}$.

- Homogeneous solution: $c_{1}\cos x+c_{2}\sin x$.
- Try $y_{1}=Ax^{3}+Bx^{2}+Cx+D$. Then $y_{1}''=6Ax+2B$.
- $(6Ax+2B)+(Ax^{3}+Bx^{2}+Cx+D)=x^{3}$.
- Equate coefficients: $A=1$, $B=0$, $C=-6$, $D=0$.
- Particular solution: $y_{1}=x^{3}-6x$.
- **General solution:** $y=c_{1}\cos x+c_{2}\sin x+x^{3}-6x$.

> Compared with variation of parameters, this method requires no integration.

### 8.13.2 Case 2 鈥?$R(x)=p(x)e^{mx}$

Substitute $y=u(x)e^{mx}$. The equation becomes:

$$
u''+(2m+a)u'+(m^{2}+am+b)u=p.
$$

This is Case 1 for $u$, so a polynomial solution $u_{1}$ always exists.

| Condition | Degree of $u_{1}$ |
|-----------|-------------------|
| $m^{2}+am+b\neq 0$ | Same as $\deg p$ |
| $m^{2}+am+b=0$, $2m+a\neq 0$ | $\deg p+1$ |
| $m^{2}+am+b=0$, $2m+a=0$ | $\deg p+2$ |

The particular solution is $y_{1}=u_{1}(x)e^{mx}$.

**Example.** $y''+y=xe^{3x}$.

- Substitute $y=ue^{3x}$: $u''+6u'+10u=x$.
- Try $u_{1}=Ax+B$: $u_{1}=\dfrac{5x-3}{50}$.
- Particular solution: $y_{1}=\dfrac{e^{3x}(5x-3)}{50}$.

### 8.13.3 Extensions

The method also applies when $R$ has the form:

$$
R(x)=p(x)e^{mx}\cos\alpha x\quad\text{or}\quad R(x)=p(x)e^{mx}\sin\alpha x.
$$

In either case, seek a particular solution of the form:

$$
y_{1}(x)=e^{mx}\bigl[q(x)\cos\alpha x+r(x)\sin\alpha x\bigr],
$$

where $q$ and $r$ are polynomials.

## 8.14 Physical Applications of Second-Order Linear ODEs

### 8.14.1 Simple Harmonic Motion

**Model.** $y''+k^{2}y=0$ $(k>0)$.

**Solution.**

$$
y=A\sin kx+B\cos kx=C\sin(kx+\alpha),
$$

where $C=\sqrt{A^{2}+B^{2}}$ and $\alpha=\arctan(B/A)$.

| Quantity | Formula |
|----------|---------|
| Amplitude | $C$ |
| Period | $\dfrac{2\pi}{k}$ |
| Phase angle | $kx+\alpha$ |

### 8.14.2 Damped Vibrations

**Model.** $y''+2cy'+k^{2}y=0$ $(c\neq 0,\;k>0)$.

Discriminant: $d=4(c^{2}-k^{2})$.

| Case | Condition | Form of solution | Behavior ($c>0$) | Name |
|------|-----------|------------------|------------------|------|
| (a) | $c^{2}=k^{2}$ | $y=e^{-cx}(A+Bx)$ | $\to 0$ | **Critical damping** |
| (b) | $c^{2}>k^{2}$ | $y=Ae^{(h-c)x}+Be^{-(h+c)x}$, $h=\sqrt{c^{2}-k^{2}}$ | $\to 0$ | **Overcritical damping** |
| (c) | $c^{2}<k^{2}$ | $y=Ce^{-cx}\sin(hx+\alpha)$, $h=\sqrt{k^{2}-c^{2}}$ | Oscillates, amplitude $\to 0$ | **Undercritical damping** |

> If $c<0$, some solutions become unbounded as $x\to+\infty$ (unstable).

### 8.14.3 RLC Electric Circuits

With a capacitor $C$ added to the RL circuit:

$$
LI''(t)+RI'(t)+\frac{1}{C}I(t)=V'(t).
$$

For constant voltage ($V'=0$):

$$
I''+\frac{R}{L}I'+\frac{1}{LC}I=0.
$$

This is the same type as damped vibrations, with $2c=R/L$ and $k^{2}=1/(LC)$.

| Condition | Damping type |
|-----------|-------------|
| $CR^{2}=4L$ | Critical |
| $CR^{2}>4L$ | Overcritical |
| $CR^{2}<4L$ | Undercritical |

### 8.14.4 Rocket Motion with Variable Mass

**Model.** From conservation of momentum:

$$
m(t)r''(t)=m'(t)c(t)+F(t),
$$

where $m(t)$ is mass, $c(t)$ is exhaust velocity (relative to rocket), and $F(t)$ is external force.

**Special case.** Fuel consumed at rate $k$, exhaust speed $-c$ (constant), gravity $-m(t)g$:

$$
r''(t)=\frac{kc}{w-kt}-g.
$$

- $w$ = initial total weight, $b$ = fuel weight, $T=w/k$ = total burn time.
- Velocity: $r'(t)=-c\log\dfrac{w-kt}{w}-gt$.
- Altitude at fuel exhaustion ($t=b/k$):
  $$
  r\Bigl(\frac{b}{k}\Bigr)=\frac{c(w-b)}{k}\log\frac{w-b}{w}-\frac{gb^{2}}{2k^{2}}+\frac{cb}{k}.
  $$
- Limiting case $b\to w$ (negligible carrier weight):
  $$
  \lim_{b\to w}r\Bigl(\frac{b}{k}\Bigr)=-\frac{1}{2}gT^{2}+cT.
  $$

## 8.15 Remarks on Nonlinear Differential Equations

### 8.15.1 First-Order Equations $y'=f(x,y)$

Unlike linear equations, nonlinear ODEs lack a comprehensive systematic theory. We focus on first-order equations solvable for $y'$:

$$
y'=f(x,y).
$$

### 8.15.2 Existence and Uniqueness Failures

A nonlinear equation may have **no solution** or **more than one** solution satisfying a given initial condition.

| Equation | Initial condition | Outcome |
|----------|-------------------|---------|
| $(y')^{2}-xy'+y+1=0$ | $y=0$ at $x=0$ | No solution (requires $(y')^{2}=-1$) |
| $y'=3y^{2/3}$ | $y=0$ at $x=0$ | Two solutions: $Y_{1}(x)\equiv 0$ and $Y_{2}(x)=x^{3}$ |

### 8.15.3 Implicit Formulas

Sometimes $y'$ can be eliminated to obtain a relation:

$$
F(x,y)=0,
$$

satisfied by some or all solutions.

**Example.** The equation $y'=\dfrac{y-x}{y+x}$ has solutions satisfying:

$$
\frac{1}{2}\log(x^{2}+y^{2})+\arctan\frac{y}{x}+C=0.
$$

This is an **implicit formula**; solving for $y$ explicitly is hopeless. Nevertheless, arriving at such a relation (with no derivatives of the unknown) is regarded as having "solved" or "integrated" the differential equation.

> Qualitative information about solutions can often be obtained directly from the differential equation without explicit or implicit formulas (see next section).

## 8.16 Integral Curves and Direction Fields

### 8.16.1 Integral Curves

A solution of $y'=f(x,y)$ satisfying an implicit relation $F(x,y,C)=0$ defines a curve called an **integral curve**. As $C$ varies, the collection forms a **one-parameter family** of curves.

| Equation | Family | Constant $C$ means |
|----------|--------|-------------------|
| $y'=3$ | $y=3x+C$ | $y$-intercept |
| $y'=x$ | $y=\frac{1}{2}x^{2}+C$ | Crosses $y$-axis at $(0,C)$ |
| $y'=y$ | $y=Ce^{x}$ | $y$-intercept (also slope at $y$-axis) |

### 8.16.2 Envelopes and Singular Solutions

The equation $y=x\,y'-\frac{1}{4}(y')^{2}$ has the one-parameter family:

$$
y=Cx-\frac{1}{4}C^{2}.
$$

The **envelope** of this family is $y=x^{2}$ (dotted in Figure 8.9). The envelope is itself a solution and is **not** a member of the family. By piecing together family members with portions of the envelope, further solutions can be constructed.

### 8.16.3 Finding a Differential Equation from Its Integral Curves

**Example 1.** Circles centered at the origin: $x^{2}+y^{2}=C^{2}$.

Differentiate: $2x+2yy'=0$, hence $y'=-x/y$.

**Example 2.** Circles through the origin with centers on the $x$-axis: $x^{2}+y^{2}-2Cx=0$.

- Differentiate: $x+yy'=C$.
- Eliminate $C$: $y'=\dfrac{y^{2}-x^{2}}{2xy}$.

### 8.16.4 Direction Fields

A **direction field** is constructed by drawing short line segments at various points $(a,b)$ with slope $f(a,b)$. It provides qualitative information about solutions without solving the equation.

> Different initial points $(0,b)$ on the $y$-axis yield different integral curves鈥攖his is a geometric reason for the appearance of an arbitrary constant when integrating a first-order equation.

## 8.17 First-Order Separable Equations

### 8.17.1 Definition

A **separable** equation has the form:

$$
y'=Q(x)R(y)\qquad\text{or}\qquad A(y)y'=Q(x),
$$

where $A(y)=1/R(y)$.

### 8.17.2 Theorem 8.10

Let $y=Y(x)$ solve $A(y)y'=Q(x)$ on an open interval $I$, with $Y'$, $Q$, and $A\circ Y$ continuous. Let $G$ be any primitive of $A$ ($G'=A$). Then $Y$ satisfies:

$$
G(y)=\int Q(x)\,dx+C.
$$

Conversely, any $y$ satisfying this implicit formula is a solution.

**Proof.** $A[Y(x)]Y'(x)=Q(x)$ becomes $G'[Y(x)]Y'(x)=Q(x)$, i.e. $(G\circ Y)'=Q$. Integrate.

> **Mechanical process.** Write $y'=dy/dx$, separate variables $A(y)\,dy=Q(x)\,dx$, and integrate both sides. This is justified by Theorem 8.10.

### 8.17.3 Example: $xy'+y=y^{2}$

Rewrite as:

$$
\frac{y'}{y(y-1)}=\frac{1}{x}\qquad(y\neq 0,1).
$$

The constant functions $y\equiv 0$ and $y\equiv 1$ are also solutions.

For $y\notin\{0,1\}$, separate and integrate:

$$
\int\frac{dy}{y(y-1)}=\int\frac{dx}{x}+K.
$$

Since $\dfrac{1}{y(y-1)}=\dfrac{1}{y-1}-\dfrac{1}{y}$:

$$
\log\Bigl|\frac{y-1}{y}\Bigr|=\log|x|+K\quad\Longrightarrow\quad\frac{y-1}{y}=Cx.
$$

Solving for $y$:

$$
y=\frac{1}{1-Cx}.
$$

> All solutions: $y\equiv 0$, $y\equiv 1$, and $y=\dfrac{1}{1-Cx}$ (the case $C=0$ recovers $y\equiv 1$).

## 8.18 Homogeneous First-Order Equations

### 8.18.1 Definition

A first-order equation $y'=f(x,y)$ is **homogeneous** (of degree zero) if:

$$
f(tx,ty)=f(x,y)\qquad\text{for all }t\neq 0.
$$

Equivalently, setting $t=1/x$:

$$
y'=f\Bigl(1,\frac{y}{x}\Bigr).
$$

**Examples.** $y'=\dfrac{y-x}{y+x}$, $y'=\Bigl(\dfrac{x^{2}+y^{2}}{xy}\Bigr)^{3}$, $y'=\log x-\log y$.

### 8.18.2 Reduction to a Separable Equation

Substitute $v=y/x$ (so $y=vx$, $y'=v'x+v$). Then:

$$
x\frac{dv}{dx}=f(1,v)-v,
$$

which is separable. Solve for $v$, then replace $v$ by $y/x$.

### 8.18.3 Example: $y'=\dfrac{y-x}{y+x}$

Rewrite:

$$
y'=\frac{y/x-1}{y/x+1}=\frac{v-1}{v+1}.
$$

With $v=y/x$:

$$
x\frac{dv}{dx}=\frac{v-1}{v+1}-v=-\frac{1+v^{2}}{v+1}.
$$

Separate and integrate:

$$
\int\frac{v}{1+v^{2}}\,dv+\int\frac{1}{1+v^{2}}\,dv=-\int\frac{dx}{x}+C,
$$

$$
\frac{1}{2}\log(1+v^{2})+\arctan v=-\log|x|+C.
$$

Replace $v=y/x$ and simplify ($\log x^{2}=2\log|x|$):

$$
\frac{1}{2}\log(x^{2}+y^{2})+\arctan\frac{y}{x}=C.
$$

### 8.18.4 Geometric Property 鈥?Invariance under Similarity Transformations

A **similarity transformation** multiplies all coordinates by $k>0$. For a homogeneous equation:

- Straight lines through the origin are **isoclines**.
- If $S$ is an integral curve, so is $kS$ (the image of $S$ under similarity).

**Proof sketch.** Let $S$ be $y=F(x)$ with $F'(x)=f(x,F(x))$. The curve $kS$ is $y=G(x)$ where $G(x)=kF(x/k)$. Then:

$$
G'(x)=F'\Bigl(\frac{x}{k}\Bigr)=f\Bigl(\frac{x}{k},F\Bigl(\frac{x}{k}\Bigr)\Bigr)=f\Bigl(x,kF\Bigl(\frac{x}{k}\Bigr)\Bigr)=f(x,G(x)),
$$

using homogeneity with $t=k$. Hence $kS$ is also an integral curve.

> **Converse.** If the integral curves of $y'=f(x,y)$ are invariant under all similarity transformations, then the equation is necessarily homogeneous.

## 8.19 Geometrical and Physical Problems Leading to First-Order Equations

### 8.19.1 Orthogonal Trajectories

Two curves intersect **orthogonally** if their tangents are perpendicular at the intersection point.

- Given a family satisfying $y'=f(x,y)$, the orthogonal trajectories satisfy:
  $$
  y'=-\frac{1}{f(x,y)}.
  $$
- If the original equation is separable (or homogeneous), so is the orthogonal equation.

**Example.** Find orthogonal trajectories of circles through the origin with centers on the $x$-axis.

- Family: $x^{2}+y^{2}-2Cx=0$; differential equation: $y'=\dfrac{y^{2}-x^{2}}{2xy}$.
- Orthogonal equation: $y'=\dfrac{2xy}{x^{2}-y^{2}}$ (homogeneous).
- Substituting $v=y/x$ yields the family: $x^{2}+y^{2}-2Cy=0$.
- **Result:** circles through the origin with centers on the $y$-axis.

### 8.19.2 Pursuit Problems

Point $Q$ moves along $C_{1}$; point $P$ pursues $Q$ so that $P$'s velocity is always directed toward $Q$. The locus of $P$ is a **curve of pursuit**.

With $P=(x,y)$ and $Q=(X,Y)$:

$$
y'=\frac{Y-y}{X-x}.
$$

**Example (Tractrix).** $Q$ moves on the $y$-axis; $P$ stays at distance $k$ from $Q$ and starts at $(k,0)$.

- $X=0$, $(X-x)^{2}+(Y-y)^{2}=k^{2}$ gives $Y-y=\sqrt{k^{2}-x^{2}}$.
- $y'=\dfrac{\sqrt{k^{2}-x^{2}}}{-x}$.
- Substitute $x=k\cos t$, integrate with $y(k)=0$:
  $$
  y=k\log\frac{k+\sqrt{k^{2}-x^{2}}}{x}-\sqrt{k^{2}-x^{2}}.
  $$
- This curve is called the **tractrix**.

### 8.19.3 Flow of Fluid Through an Orifice

**Setup.** Tank with cross-sectional area $A(y)$; orifice area $A_{0}$; discharge coefficient $c\approx 0.60$.

- Volume rate of change: $dV/dt=-cA_{0}\sqrt{2gy}$.
- With $V(y)=\int_{0}^{y}A(u)\,du$, chain rule gives:
  $$
  A(y)\,\frac{dy}{dt}=-cA_{0}\sqrt{2gy}.
  $$
- Separating (with $g=32$):
  $$
  \int\frac{A(y)}{\sqrt{y}}\,dy=-4.8A_{0}\int dt+C.
  $$

**Example.** $A(y)=A$ constant; level drops from 10 ft to 9 ft in 10 min (600 s).

- $-\int_{10}^{9}\dfrac{dy}{\sqrt{y}}=k\int_{0}^{600}dt$, where $k=\dfrac{4.8A_{0}}{A}$.
- $k=\dfrac{\sqrt{10}-3}{300}$.
- Time to fall from 7 ft to 1 ft: $t_{2}-t_{1}=10\,\dfrac{\sqrt{7}-1}{\sqrt{10}-3}\approx 101.3$ min.

# 9. Complex Numbers

## 9.1 Historical Introduction

The equation $x^{2}+1=0$ has no solution in the real-number system. **Complex numbers** were introduced to provide solutions to such equations.

- **16th century:** The symbol $\sqrt{-1}$ was introduced; later denoted by $i$.
- Early view: $i$ was a fictitious number whose square is $-1$. Expressions like $2+3i$ were used formally for nearly 300 years.
- **19th century:** Gauss and Hamilton independently proposed defining complex numbers as **ordered pairs** $(a,b)$ of real numbers with special arithmetic rules.

## 9.2 Definitions and Field Properties

### 9.2.1 Definition

If $a,b\in\mathbb{R}$, the pair $(a,b)$ is a **complex number**.

| Operation | Definition |
|-----------|-----------|
| **Equality** | $(a,b)=(c,d)\iff a=c$ and $b=d$ |
| **Sum** | $(a,b)+(c,d)=(a+c,\;b+d)$ |
| **Product** | $(a,b)(c,d)=(ac-bd,\;ad+bc)$ |

The number $a$ is the **real part**; $b$ is the **imaginary part**.

### 9.2.2 Theorem 9.1 鈥?Field Axioms

The set of all complex numbers satisfies the six field axioms:

| Axiom | Element | Property |
|-------|---------|----------|
| 1鈥? | 鈥?| Commutative, associative, distributive laws (addition and multiplication) |
| 4 | $(0,0)$ | Additive identity |
| 4 | $(1,0)$ | Multiplicative identity |
| 5 | $(-a,-b)$ | Additive inverse: $-(a,b)$ |
| 6 | $\bigl(\dfrac{a}{a^{2}+b^{2}},\dfrac{-b}{a^{2}+b^{2}}\bigr)$ | Multiplicative inverse (reciprocal), for $(a,b)\neq(0,0)$ |

**Quotient.** For $(a,b)\neq(0,0)$:

$$
\frac{(c,d)}{(a,b)}=(c,d)\,(a,b)^{-1}.
$$

> Since all field axioms hold, every algebraic law valid for real numbers (Theorems I.1鈥揑.15) extends to complex numbers.

## 9.3 Complex Numbers as an Extension of the Real Numbers

Let $C_{0}=\{(a,0):a\in\mathbb{R}\}$ be the set of complex numbers with zero imaginary part.

- **Addition and multiplication in $C_{0}$:**
  $$
  (a,0)+(b,0)=(a+b,0),\qquad (a,0)(b,0)=(ab,0).
  $$
- The map $f(x)=(x,0)$ is a **one-to-one correspondence** $\mathbb{R}\to C_{0}$ preserving both operations:
  $$
  f(a+b)=f(a)+f(b),\qquad f(ab)=f(a)f(b).
  $$
- Hence $\mathbb{R}$ and $C_{0}$ are **isomorphic**; we identify $x\leftrightarrow(x,0)$.
- In particular: $0=(0,0)$, $1=(1,0)$, $-1=(-1,0)$.
- $C_{0}$ is an **ordered field**: $(x,0)>0\iff x>0$.

## 9.4 The Imaginary Unit $i$

### 9.4.1 Definition

The complex number $(0,1)$ satisfies:

$$
(0,1)^{2}=(0,1)(0,1)=(-1,0)=-1.
$$

We denote it by $i$ and call it the **imaginary unit**:

$$
i^{2}=-1.
$$

### 9.4.2 The Standard Form $a+bi$

Since $(b,0)(0,1)=(0,b)$:

$$
(a,b)=(a,0)+(b,0)(0,1)=a+bi.
$$

**Theorem 9.2.** Every complex number can be written uniquely as $a+bi$ with $a,b\in\mathbb{R}$.

**Algebraic manipulations.** Using $i^{2}=-1$:

$$
(a+bi)(c+di)=ac-bd+(ad+bc)i.
$$

$$
\frac{1}{a+bi}=\frac{a-bi}{a^{2}+b^{2}}=\frac{a}{a^{2}+b^{2}}-\frac{b}{a^{2}+b^{2}}i\qquad(a+bi\neq 0).
$$

### 9.4.3 Quadratic Equations

For $ax^{2}+bx+c=0$ with real coefficients:

- If $b^{2}-4ac\ge 0$: real roots $\dfrac{-b\pm\sqrt{b^{2}-4ac}}{2a}$.
- If $b^{2}-4ac<0$: complex conjugate roots:
  $$
  r_{1,2}=\frac{-b}{2a}\pm i\,\frac{\sqrt{4ac-b^{2}}}{2a}.
  $$

### 9.4.4 Fundamental Theorem of Algebra

> **Gauss (1799).** Every polynomial equation
> $$
> a_{0}+a_{1}x+\cdots+a_{n}x^{n}=0\qquad(a_{n}\neq 0,\;n\ge 1)
> $$
> with complex coefficients has at least one solution in $\mathbb{C}$.
>
> Hence no number system more general than $\mathbb{C}$ is needed to solve polynomial equations.

## 9.5 Geometric Interpretation, Modulus and Argument

### 9.5.1 The Complex Plane

A complex number $z=x+iy$ is represented by the point $(x,y)$ in the plane. The $x$-axis is the **real axis**; the $y$-axis is the **imaginary axis**.

- **Addition/subtraction** obey the **parallelogram law**.

### 9.5.2 Polar Form

For $z=x+iy\neq 0$, write $x=r\cos\theta$, $y=r\sin\theta$:

$$
z=r(\cos\theta+i\sin\theta).
$$

| Quantity | Definition | Formula |
|----------|-----------|---------|
| **Modulus** (absolute value) | Distance from origin | $\|z\|=\sqrt{x^{2}+y^{2}}=r$ |
| **Argument** | Polar angle | $\theta=\arg z$ (determined up to $2\pi$) |
| **Principal argument** | Unique choice | $\operatorname{Arg}z\in(-\pi,\pi]$ |

### 9.5.3 Properties of the Modulus

$$
\begin{aligned}
&|z|>0\quad\text{if }z\neq 0,&&|z_{1}-z_{2}|=|z_{2}-z_{1}|,\\
&|z_{1}+z_{2}|\le|z_{1}|+|z_{2}|,&&|z_{1}z_{2}|=|z_{1}|\,|z_{2}|,\\
&\Bigl|\frac{z_{1}}{z_{2}}\Bigr|=\frac{|z_{1}|}{|z_{2}|}\quad(z_{2}\neq 0).
\end{aligned}
$$

The product formula follows from:

$$
(ac-bd)^{2}+(bc+ad)^{2}=(a^{2}+b^{2})(c^{2}+d^{2}).
$$

### 9.5.4 Complex Conjugate

For $z=x+iy$, the **conjugate** is $\bar{z}=x-iy$ (reflection in the real axis).

$$
\overline{z_{1}+z_{2}}=\bar{z}_{1}+\bar{z}_{2},\qquad
\overline{z_{1}z_{2}}=\bar{z}_{1}\bar{z}_{2},\qquad
\overline{z_{1}/z_{2}}=\bar{z}_{1}/\bar{z}_{2},\qquad
z\bar{z}=|z|^{2}.
$$

### 9.5.5 Conjugate Roots of Real Polynomials

If a real-coefficient quadratic has no real roots, its complex roots are **conjugates**.

Conversely, if $r_{1}=\alpha+i\beta$ and $r_{2}=\alpha-i\beta$ are conjugates, they are roots of:

$$
x^{2}-2\alpha x+\alpha^{2}+\beta^{2}=0.
$$

## 9.6 Complex Exponentials

### 9.6.1 Motivation

To extend $e^{z}$ to complex $z$ while preserving the law $e^{a}e^{b}=e^{a+b}$, write $z=x+iy$:

$$
e^{z}=e^{x+iy}=e^{x}e^{iy}.
$$

Set $e^{iy}=A(y)+iB(y)$. Differentiating twice and comparing with $-e^{iy}$ gives $A''=-A$, $B''=-B$. With initial values $A(0)=1$, $A'(0)=0$, $B(0)=0$, $B'(0)=1$, uniqueness yields:

$$
A(y)=\cos y,\qquad B(y)=\sin y.
$$

### 9.6.2 Definition

For $z=x+iy$:

$$
e^{z}=e^{x}(\cos y+i\sin y).
$$

When $y=0$, this reduces to the real exponential $e^{x}$.

### 9.6.3 Theorem 9.3 鈥?Law of Exponents

For all complex $a,b$:

$$
e^{a}e^{b}=e^{a+b}.
$$

**Proof.** Write $a=x+iy$, $b=u+iv$. Using the addition formulas for $\cos$ and $\sin$:

$$
e^{a}e^{b}=e^{x+u}\bigl[\cos(y+v)+i\sin(y+v)\bigr]=e^{a+b}.
$$

### 9.6.4 Theorem 9.4 鈥?Polar Form

Every $z\neq 0$ can be written as:

$$
z=re^{i\theta},
$$

where $r=|z|$ and $\theta=\arg(z)+2n\pi$. This follows from **Euler's formula**:

$$
e^{i\theta}=\cos\theta+i\sin\theta.
$$

### 9.6.5 Multiplication and Division in Polar Form

If $z_{1}=r_{1}e^{i\theta}$ and $z_{2}=r_{2}e^{i\phi}$:

$$
z_{1}z_{2}=r_{1}r_{2}\,e^{i(\theta+\phi)},\qquad
\frac{z_{1}}{z_{2}}=\frac{r_{1}}{r_{2}}\,e^{i(\theta-\phi)}.
$$

### 9.6.6 De Moivre's Formula

For any integer $n$:

$$
z^{n}=r^{n}e^{in\theta}=r^{n}\bigl(\cos n\theta+i\sin n\theta\bigr).
$$

## 9.7 Complex-Valued Functions

A **complex-valued function** takes complex numbers as values.

| Type | Domain | Example |
|------|--------|---------|
| Of a real variable | Real numbers | $f(x)=u(x)+iv(x)$ |
| Of a complex variable | Complex numbers | $f(z)=e^{z}$ |

Most elementary functions (exponential, logarithm, trigonometric) extend to complex variables.

**Periodicity of the complex exponential.** For any integer $n$:

$$
e^{z+2n\pi i}=e^{z}.
$$

Thus $e^{z}$ has period $2\pi i$.

## 9.8 Calculus of Complex-Valued Functions of a Real Variable

### 9.8.1 Definitions

Let $f(x)=u(x)+iv(x)$ with $u,v$ real-valued.

| Concept | Definition |
|---------|-----------|
| **Continuity** | $f$ continuous $\iff$ $u$ and $v$ both continuous |
| **Derivative** | $f'(x)=u'(x)+iv'(x)$ |
| **Integral** | $\displaystyle\int_{a}^{b}f(x)\,dx=\int_{a}^{b}u(x)\,dx+i\int_{a}^{b}v(x)\,dx$ |

### 9.8.2 Extended Theorems

Many theorems of real calculus carry over unchanged:

- Sum, product, and quotient rules for differentiation.
- First and second fundamental theorems of calculus.
- **Zero-derivative theorem:** If $f'(x)=0$ on an open interval $I$, then $f$ is constant on $I$.

**Proof.** $f'=u'+iv'=0$ implies $u'=v'=0$. By the real zero-derivative theorem, $u$ and $v$ are constant; hence $f$ is constant.

### 9.8.3 Differentiation and Integration of $e^{tx}$

**Theorem 9.5.** If $f(x)=e^{tx}$ for real $x$ and fixed complex $t$, then:

$$
f'(x)=te^{tx}.
$$

**Proof.** Write $t=\alpha+i\beta$. Then:

$$
f(x)=e^{\alpha x}\cos\beta x+i\,e^{\alpha x}\sin\beta x.
$$

Differentiating the real and imaginary parts and combining gives $f'(x)=(\alpha+i\beta)e^{(\alpha+i\beta)x}=te^{tx}$.

**Integration formula** ($t\neq 0$):

$$
\int e^{tx}\,dx=\frac{e^{tx}}{t}.
$$

Equating real and imaginary parts with $t=\alpha+i\beta$:

$$
\int e^{\alpha x}\cos\beta x\,dx=\frac{e^{\alpha x}(\alpha\cos\beta x+\beta\sin\beta x)}{\alpha^{2}+\beta^{2}},
$$

$$
\int e^{\alpha x}\sin\beta x\,dx=\frac{e^{\alpha x}(\alpha\sin\beta x-\beta\cos\beta x)}{\alpha^{2}+\beta^{2}}.
$$

### 9.8.4 Connection with Second-Order Linear ODEs

**Theorem 9.6.** Let $L(y)=y''+ay'+by$ with real constants $a,b$. The function $f(x)=e^{tx}$ satisfies $L(f)=0$ iff $t$ is a root of the characteristic equation:

$$
t^{2}+at+b=0.
$$

**Proof.** $f'(x)=te^{tx}$ and $f''(x)=t^{2}e^{tx}$, so $L(f)=e^{tx}(t^{2}+at+b)$. Since $e^{tx}\neq 0$, the result follows.

> If $t=\alpha+i\beta$, the real and imaginary parts $u(x)=e^{\alpha x}\cos\beta x$ and $v(x)=e^{\alpha x}\sin\beta x$ are both real solutions. Their linear combination $y=c_{1}u+c_{2}v$ is the general solution, agreeing with Theorem 8.7.

# 10. Sequences, Infinite Series, Improper Integrals

## 10.1 Zeno's Paradox

### 10.1.1 The Racecourse Paradox

Zeno of Elea (495鈥?35 B.C.) argued that a runner can never reach the end of a racecourse: he must first cover half the distance, then half of what remains, then half of that, *ad infinitum*.

If the runner covers the first half in $T$ minutes, the total time is represented by the **infinite series**:

$$
T+\frac{T}{2}+\frac{T}{4}+\cdots+\frac{T}{2^{n}}+\cdots.
$$

**Partial sums.**

$$
s_{n}=T+\frac{T}{2}+\cdots+\frac{T}{2^{n-1}}=\Bigl(2-\frac{1}{2^{n-1}}\Bigr)T.
$$

Since $1/2^{n-1}\to 0$, we have $s_{n}\to 2T$. Thus the series has **sum** $2T$, resolving the paradox.

### 10.1.2 A Divergent Variant

Suppose instead the runner's speed decreases so that the portion from $1/2^{n-1}$ to $1/2^{n}$ takes $T/n$ minutes. The total time is:

$$
T+\frac{T}{2}+\frac{T}{3}+\cdots+\frac{T}{n}+\cdots.
$$

**Integral estimate.** The harmonic partial sums satisfy:

$$
1+\frac{1}{2}+\cdots+\frac{1}{n}\ge\log(n+1).
$$

Hence $s_{n}\ge T\log(n+1)\to+\infty$. The runner never arrives鈥擹eno is right in this case.

> **Convergent** series have partial sums approaching a finite limit; **divergent** series do not.

### 10.1.3 Historical Remarks

- **17th century:** Widespread use of infinite series; Newton discovered the **binomial series**.
- **Binomial theorem:** $(1+x)^{n}=\displaystyle\sum_{k=0}^{n}\binom{n}{k}x^{k}$ for integer $n\ge 0$.
- Newton extended this to arbitrary real exponents (no rigorous proof at the time).
- **1812:** Gauss published the first thorough and rigorous treatment of convergence.
- **1821:** Cauchy introduced the analytic definition of limit in *Cours d'analyse alg茅brique*, laying the foundations of modern convergence theory.

## 10.2 Sequences

### 10.2.1 Definition

A **sequence** is a function $f$ whose domain is the set of positive integers. The value $f(n)$ is called the $n$th **term**.

**Notation.** $\{f(n)\}$, or $a_{n}, s_{n}, x_{n}, u_{n}$, etc.

**Examples.**
- $a_{n}=1/n$: $\;1,\tfrac{1}{2},\tfrac{1}{3},\tfrac{1}{4},\ldots$
- $a_{2n-1}=1$, $a_{2n}=2n^{2}$: $\;1,2,1,8,1,18,\ldots$
- **Fibonacci** (recursion): $a_{1}=a_{2}=1$, $a_{n+1}=a_{n}+a_{n-1}$: $\;1,1,2,3,5,8,13,\ldots$

### 10.2.2 Limit of a Sequence

**Definition.** A sequence $\{f(n)\}$ has **limit** $L$ if:

> For every $\epsilon>0$, there exists $N$ such that $|f(n)-L|<\epsilon$ for all $n\ge N$.

We write $\displaystyle\lim_{n\to\infty}f(n)=L$ or $f(n)\to L$.

A sequence with no limit is **divergent**.

### 10.2.3 Complex-Valued Sequences

If $f=u+iv$ and $L=a+ib$, then:

$$
f(n)\to L\quad\Longleftrightarrow\quad u(n)\to a\;\text{ and }\;v(n)\to b.
$$

Hence:

$$
\lim_{n\to\infty}f(n)=\lim_{n\to\infty}u(n)+i\lim_{n\to\infty}v(n).
$$

> For complex $f$: $f(n)\to\infty$ means $|f(n)|\to+\infty$.

### 10.2.4 Basic Limit Formulas

| Formula | Condition |
|---------|-----------|
| $\displaystyle\lim_{n\to\infty}\dfrac{1}{n^{\alpha}}=0$ | $\alpha>0$ |
| $\displaystyle\lim_{n\to\infty}x^{n}=0$ | $|x|<1$ |
| $\displaystyle\lim_{n\to\infty}\dfrac{(\log n)^{a}}{n^{b}}=0$ | $a>0$, $b>0$ |
| $\displaystyle\lim_{n\to\infty}n^{1/n}=1$ | 鈥?|
| $\displaystyle\lim_{n\to\infty}\Bigl(1+\dfrac{a}{n}\Bigr)^{n}=e^{a}$ | $a\in\mathbb{R}$ |

### 10.2.5 Algebra of Limits

If $f(n)\to L$ and $g(n)\to M$, then:
- $f(n)+g(n)\to L+M$
- $f(n)g(n)\to LM$
- $f(n)/g(n)\to L/M$ (if $M\neq 0$)

## 10.3 Monotonic Sequences of Real Numbers

### 10.3.1 Definitions

| Type | Condition | Notation |
|------|-----------|----------|
| **Increasing** | $f(n)\le f(n+1)$ for all $n\ge 1$ | $f(n)\nearrow$ |
| **Decreasing** | $f(n)\ge f(n+1)$ for all $n\ge 1$ | $f(n)\searrow$ |
| **Monotonic** | Increasing or decreasing | 鈥?|

A sequence is **bounded** if $|f(n)|\le M$ for some $M>0$ and all $n$; otherwise it is **unbounded**.

### 10.3.2 Theorem 10.1

A monotonic sequence **converges if and only if it is bounded**.

**Proof.**

- An unbounded sequence cannot converge (obvious).
- Let $f(n)\nearrow$ and be bounded. Let $L=\sup\{f(n)\}$ (exists by the least-upper-bound axiom).
  - $f(n)\le L$ for all $n$.
  - For any $\epsilon>0$, $L-\epsilon$ is not an upper bound, so $f(N)>L-\epsilon$ for some $N$.
  - Since $f$ is increasing: $L-\epsilon<f(n)\le L$ for all $n\ge N$.
  - Hence $0\le L-f(n)<\epsilon$, so $f(n)\to L$.
- The decreasing case is similar, with limit $=\inf\{f(n)\}$.

## 10.4 Infinite Series

### 10.4.1 Definition

Given a sequence $\{a_{k}\}$, form the **partial sums**:

$$
s_{n}=\sum_{k=1}^{n}a_{k}=a_{1}+a_{2}+\cdots+a_{n}.
$$

The sequence $\{s_{n}\}$ is called an **infinite series**, denoted:

$$
\sum_{k=1}^{\infty}a_{k}\quad\text{or}\quad a_{1}+a_{2}+a_{3}+\cdots.
$$

If $\displaystyle\lim_{n\to\infty}s_{n}=S$, the series **converges** and has **sum** $S$:

$$
\sum_{k=1}^{\infty}a_{k}=S.
$$

If $\{s_{n}\}$ diverges, the series **diverges**.

> The "sum" of a series is the **limit of partial sums**, not ordinary addition.

### 10.4.2 Examples

**Example 1 鈥?The harmonic series.** $\displaystyle\sum_{k=1}^{\infty}\frac{1}{k}$.

Since $s_{n}=\sum_{k=1}^{n}\frac{1}{k}\ge\log(n+1)\to\infty$, the harmonic series **diverges**.

**Example 2 鈥?Geometric series.** $\displaystyle\sum_{k=1}^{\infty}\frac{1}{2^{k-1}}=1+\frac{1}{2}+\frac{1}{4}+\cdots$.

Since $s_{n}=2-\dfrac{1}{2^{n-1}}\to 2$, this series **converges** with sum $2$.

### 10.4.3 Shifting the Index

The symbol $\displaystyle\sum_{k=p}^{\infty}a_{k}$ (for $p\ge 0$) differs from $\displaystyle\sum_{k=1}^{\infty}a_{k}$ by only finitely many terms. Therefore:

> **Adding or omitting a finite number of terms at the beginning does not affect convergence or divergence.**

## 10.5 Linearity of Convergent Series

### 10.5.1 Theorem 10.2

If $\sum a_{n}$ and $\sum b_{n}$ converge and $\alpha,\beta$ are complex constants, then $\sum(\alpha a_{n}+\beta b_{n})$ also converges, and:

$$
\sum_{n=1}^{\infty}(\alpha a_{n}+\beta b_{n})=\alpha\sum_{n=1}^{\infty}a_{n}+\beta\sum_{n=1}^{\infty}b_{n}.
$$

**Proof.** Apply the corresponding properties of finite sums and take limits.

### 10.5.2 Theorem 10.3

If $\sum a_{n}$ converges and $\sum b_{n}$ diverges, then $\sum(a_{n}+b_{n})$ **diverges**.

**Proof.** If $\sum(a_{n}+b_{n})$ converged, then $\sum b_{n}=\sum[(a_{n}+b_{n})-a_{n}]$ would converge by Theorem 10.2鈥攃ontradiction.

> If **both** diverge, $\sum(a_{n}+b_{n})$ may converge or diverge.

**Example.** $\sum(1/k+1/2^{k})$ diverges because $\sum 1/k$ diverges while $\sum 1/2^{k}$ converges.

## 10.6 Telescoping Series

### 10.6.1 Theorem 10.4

Let $a_{n}=b_{n}-b_{n+1}$. Then:

$$
\sum_{n=1}^{\infty}a_{n}\text{ converges}\quad\Longleftrightarrow\quad\{b_{n}\}\text{ converges}.
$$

In that case, with $L=\lim_{n\to\infty}b_{n}$:

$$
\sum_{n=1}^{\infty}a_{n}=b_{1}-L.
$$

**Proof.** The $n$th partial sum is $s_{n}=\sum_{k=1}^{n}(b_{k}-b_{k+1})=b_{1}-b_{n+1}$.

> Every series is telescoping (choose $b_{1}$ arbitrarily and set $b_{n+1}=b_{1}-s_{n}$), but the decomposition is useful only when $b_{n}$ is simple.

### 10.6.2 Examples

**Example 1.** $a_{n}=\dfrac{1}{n^{2}+n}=\dfrac{1}{n}-\dfrac{1}{n+1}$. Here $b_{n}=1/n$, $L=0$:

$$
\sum_{n=1}^{\infty}\frac{1}{n(n+1)}=1.
$$

**Example 2.** For $x$ not a negative integer:

$$
\frac{1}{(n+x)(n+x+1)(n+x+2)}=\frac{1}{2}\Bigl(\frac{1}{(n+x)(n+x+1)}-\frac{1}{(n+x+1)(n+x+2)}\Bigr).
$$

Hence:

$$
\sum_{n=1}^{\infty}\frac{1}{(n+x)(n+x+1)(n+x+2)}=\frac{1}{2(x+1)(x+2)}.
$$

**Example 3.** $\log\dfrac{n}{n+1}=\log n-\log(n+1)$. Since $\log n\to\infty$, the series **diverges**.

> **Caution.** In an infinite telescoping series $(b_{1}-b_{2})+(b_{2}-b_{3})+\cdots$, one cannot simply "cancel" all intermediate terms to obtain sum $b_{1}$ unless $\lim b_{n}=0$.

## 10.7 The Geometric Series

### 10.7.1 Theorem 10.5

For complex $x$:

$$
\sum_{n=0}^{\infty}x^{n}=1+x+x^{2}+\cdots=\frac{1}{1-x}\qquad\text{if }|x|<1.
$$

If $|x|\ge 1$, the series diverges.

**Proof.** The partial sum $s_{n}=1+x+\cdots+x^{n-1}$ satisfies $(1-x)s_{n}=1-x^{n}$. Hence $s_{n}=\dfrac{1-x^{n}}{1-x}\to\dfrac{1}{1-x}$ when $|x|<1$.

### 10.7.2 Derived Series (by Substitution)

| Series | Sum | Valid for |
|--------|-----|-----------|
| $1+x^{2}+x^{4}+\cdots$ | $\dfrac{1}{1-x^{2}}$ | $|x|<1$ |
| $x+x^{3}+x^{5}+\cdots$ | $\dfrac{x}{1-x^{2}}$ | $|x|<1$ |
| $1-x+x^{2}-x^{3}+\cdots$ | $\dfrac{1}{1+x}$ | $|x|<1$ |
| $1-x^{2}+x^{4}-\cdots$ | $\dfrac{1}{1+x^{2}}$ | $|x|<1$ |
| $x-x^{3}+x^{5}-\cdots$ | $\dfrac{x}{1+x^{2}}$ | $|x|<1$ |

### 10.7.3 Power Series

A series of the form $\displaystyle\sum_{n=0}^{\infty}a_{n}x^{n}$ is called a **power series**. The geometric series is the special case $a_{n}=1$.

**Differentiation of (10.25).**

$$
1+2x+3x^{2}+\cdots+nx^{n-1}+\cdots=\frac{1}{(1-x)^{2}}\qquad(|x|<1).
$$

**Integration of (10.28).** Mercator鈥揃rouncker (1668):

$$
x-\frac{x^{2}}{2}+\frac{x^{3}}{3}-\frac{x^{4}}{4}+\cdots=\log(1+x)\qquad(-1<x\le 1).
$$

**Integration of (10.29).** Gregory (1671):

$$
x-\frac{x^{3}}{3}+\frac{x^{5}}{5}-\frac{x^{7}}{7}+\cdots=\arctan x\qquad(|x|\le 1).
$$

### 10.7.4 Taylor Series

If $f$ has derivatives of all orders near $0$, Taylor's formula gives:

$$
f(x)=\sum_{k=0}^{n}a_{k}x^{k}+E_{n}(x),\qquad a_{k}=\frac{f^{(k)}(0)}{k!}.
$$

If $E_{n}(x)\to 0$ as $n\to\infty$, then:

$$
f(x)=\sum_{k=0}^{\infty}a_{k}x^{k}.
$$

The partial sums of this power series are precisely the Taylor polynomials. Conditions guaranteeing $E_{n}(x)\to 0$ will be discussed in Section 11.10.

## 10.8 Tests for Convergence

Convergence tests fall into three categories:

| Type | Form | Meaning |
|------|------|---------|
| (i) Sufficient | If $C$, then $\sum a_{n}$ converges | $C\Rightarrow$ convergence |
| (ii) Necessary | If $\sum a_{n}$ converges, then $C$ | convergence$\Rightarrow C$ |
| (iii) Necessary and sufficient | $\sum a_{n}$ converges $\iff C$ | equivalence |

### 10.8.1 Theorem 10.6 鈥?Necessary Condition

If $\sum a_{n}$ converges, then:

$$
\lim_{n\to\infty}a_{n}=0.
$$

**Proof.** $a_{n}=s_{n}-s_{n-1}\to S-S=0$.

> This is **not sufficient** (e.g. $a_{n}=1/n\to 0$ but $\sum 1/n$ diverges). Its practical use is as a **sufficient condition for divergence**: if $a_{n}\not\to 0$, the series diverges.

## 10.9 Comparison Tests for Nonnegative Series

### 10.9.1 Theorem 10.7 鈥?Bounded-Partial-Sum Criterion

If $a_{n}\ge 0$, then:

$$
\sum a_{n}\text{ converges}\quad\Longleftrightarrow\quad\{s_{n}\}\text{ is bounded above}.
$$

**Example.** $\sum 1/n!$ converges because $1/k!\le 1/2^{k-1}$, so:

$$
\sum_{k=1}^{n}\frac{1}{k!}\le\sum_{k=0}^{n-1}\Bigl(\frac{1}{2}\Bigr)^{k}\le 2.
$$

The sum is $e-1$.

### 10.9.2 Theorem 10.8 鈥?Comparison Test

Assume $a_{n}\ge 0$, $b_{n}\ge 0$, and $a_{n}\le c\,b_{n}$ for some $c>0$ and all $n\ge N$. Then:

- $\sum b_{n}$ converges $\;\Rightarrow\;$ $\sum a_{n}$ converges.
- $\sum a_{n}$ diverges $\;\Rightarrow\;$ $\sum b_{n}$ diverges.

> We say $\sum b_{n}$ **dominates** $\sum a_{n}$.

### 10.9.3 Theorem 10.9 鈥?Limit Comparison Test

Assume $a_{n}>0$, $b_{n}>0$. If:

$$
\lim_{n\to\infty}\frac{a_{n}}{b_{n}}=1,
$$

then $\sum a_{n}$ and $\sum b_{n}$ both converge or both diverge.

> The conclusion also holds if the limit is any $c>0$. If the limit is $0$, only "$\sum b_{n}$ conv. $\Rightarrow$ $\sum a_{n}$ conv." follows.

**Asymptotic equality.** Write $a_{n}\sim b_{n}$ if $\lim a_{n}/b_{n}=1$.

**Theorem 10.10.** Two series with positive, asymptotically equal terms converge or diverge together.

### 10.9.4 Examples

**Riemann zeta function.** For $s>1$:

$$
\zeta(s)=\sum_{n=1}^{\infty}\frac{1}{n^{s}}.
$$

- $\sum 1/n^{2}$ converges since $1/n^{2}\sim 1/(n^{2}+n)$.
- $\zeta(2)=\pi^{2}/6$ (Euler).

**Divergent examples.** Since $\sum 1/n$ diverges:
- $\sum 1/\sqrt{n(n+10)}$ diverges ($\sim 1/n$).
- $\sum\sin(1/n)$ diverges ($\sin(1/n)\sim 1/n$).

## 10.10 The Integral Test

### 10.10.1 Theorem 10.11

Let $f$ be positive and decreasing for $x\ge 1$. Define:

$$
s_{n}=\sum_{k=1}^{n}f(k),\qquad t_{n}=\int_{1}^{n}f(x)\,dx.
$$

Then $\{s_{n}\}$ and $\{t_{n}\}$ **both converge or both diverge**.

**Proof.** Comparing $f$ with step functions:

$$
\sum_{k=2}^{n}f(k)\le\int_{1}^{n}f(x)\,dx\le\sum_{k=1}^{n-1}f(k),
$$

i.e. $s_{n}-f(1)\le t_{n}\le s_{n-1}$. Both sequences are monotone increasing, so they are either both bounded or both unbounded.

### 10.10.2 Example 1 鈥?$p$-Series

$$
\sum_{n=1}^{\infty}\frac{1}{n^{s}}\quad\text{converges}\iff s>1.
$$

Take $f(x)=x^{-s}$. Then:

$$
t_{n}=\int_{1}^{n}\frac{dx}{x^{s}}=\begin{cases}\dfrac{n^{1-s}-1}{1-s}&s\neq 1,\\[6pt]\log n&s=1.\end{cases}
$$

- $s>1$: $n^{1-s}\to 0$, so $t_{n}\to\dfrac{1}{s-1}$. Converges.
- $s\le 1$: $t_{n}\to\infty$. Diverges (harmonic series when $s=1$).

### 10.10.3 Example 2 鈥?Logarithmic $p$-Series

$$
\sum_{n=2}^{\infty}\frac{1}{n(\log n)^{s}}\quad\text{converges}\iff s>1.
$$

The corresponding integral is:

$$
t_{n}=\int_{2}^{n}\frac{dx}{x(\log x)^{s}}=\begin{cases}\dfrac{(\log n)^{1-s}-(\log 2)^{1-s}}{1-s}&s\neq 1,\\[6pt]\log(\log n)-\log(\log 2)&s=1.\end{cases}
$$

Thus $\{t_{n}\}$ converges iff $s>1$.

## 10.11 The Root Test and the Ratio Test

### 10.11.1 Theorem 10.12 鈥?Root Test

Let $\sum a_{n}$ have nonnegative terms and suppose:

$$
\lim_{n\to\infty}a_{n}^{1/n}=R.
$$

| Case | Conclusion |
|------|-----------|
| $R<1$ | **Converges** |
| $R>1$ | **Diverges** |
| $R=1$ | **Inconclusive** |

**Proof sketch.** If $R<1$, choose $x$ with $R<x<1$; then $a_{n}\le x^{n}$ for large $n$. If $R>1$, then $a_{n}>1$ infinitely often, so $a_{n}\not\to 0$.

**Examples.**
- $\sum(\log n)^{-n}$: $a_{n}^{1/n}=1/\log n\to 0$. **Converges.**
- $\sum\bigl[n/(n+1)\bigr]^{n^{2}}$: $a_{n}^{1/n}=\bigl(1+1/n\bigr)^{-n}\to 1/e$. **Converges.**

### 10.11.2 Theorem 10.13 鈥?Ratio Test

Let $\sum a_{n}$ have positive terms and suppose:

$$
\lim_{n\to\infty}\frac{a_{n+1}}{a_{n}}=L.
$$

| Case | Conclusion |
|------|-----------|
| $L<1$ | **Converges** |
| $L>1$ | **Diverges** |
| $L=1$ | **Inconclusive** |

**Proof sketch.** If $L<1$, choose $x$ with $L<x<1$; then $a_{n+1}/a_{n}<x$ for large $n$, so $a_{n}\le cx^{n}$. If $L>1$, then $a_{n+1}>a_{n}$ eventually, so $a_{n}\not\to 0$.

> **Warning.** $a_{n+1}/a_{n}<1$ for all $n$ does **not** imply convergence (e.g. harmonic series).

**Example.** $\sum n!/n^{n}$:

$$
\frac{a_{n+1}}{a_{n}}=\Bigl(\frac{n}{n+1}\Bigr)^{n}=\frac{1}{(1+1/n)^{n}}\to\frac{1}{e}<1.
$$

**Converges.** In particular, $n!/n^{n}\to 0$, i.e. $n!=o(n^{n})$.

> Both tests are special cases of the comparison test with a geometric series.

## 10.12 Alternating Series

### 10.12.1 Definition

An **alternating series** is a series whose terms alternate in sign:
$$
\sum_{n=1}^{\infty}(-1)^{n-1}a_n = a_1 - a_2 + a_3 - a_4 + \cdots, \qquad a_n > 0.
$$

**Examples:**
- Logarithmic series: $\displaystyle \log(1+x) = x - \frac{x^2}{2} + \frac{x^3}{3} - \frac{x^4}{4} + \cdots$, converges for $-1 < x \le 1$. At $x=1$:
  $$\log 2 = 1 - \frac{1}{2} + \frac{1}{3} - \frac{1}{4} + \cdots$$
- Gregory鈥揕eibniz series (1671/1673):
  $$\frac{\pi}{4} = 1 - \frac{1}{3} + \frac{1}{5} - \frac{1}{7} + \cdots$$

> The alternating harmonic series converges (to $\log 2$), while the harmonic series $\sum 1/n$ diverges.

### 10.12.2 Leibniz's Rule

**Theorem.** If $\{a_n\}$ is **monotonic decreasing** and $a_n \to 0$, then the alternating series $\sum (-1)^{n-1}a_n$ **converges**.

**Error estimate.** If $S$ is the sum and $s_n$ the $n$th partial sum, then
$$
0 < (-1)^n(S - s_n) < a_{n+1} \qquad (n \ge 1).
$$
- The error has the **same sign** as the first neglected term $(-1)^n a_{n+1}$.
- The **absolute error** is **less than** the first neglected term.

**Proof sketch.**
- Even partial sums $s_{2n}$ form an increasing sequence: $s_{2n+2} - s_{2n} = a_{2n+1} - a_{2n+2} > 0$.
- Odd partial sums $s_{2n-1}$ form a decreasing sequence.
- Both are bounded, so $s_{2n} \to S'$ and $s_{2n-1} \to S''$.
- $S' - S'' = \lim (-a_{2n}) = 0$, hence $S' = S'' = S$.
- From $s_{2n} \nearrow S \le s_{2n+1} \searrow$, the inequalities follow.

**Examples:**
1. $\sum (-1)^{n-1}/n$ converges by Leibniz (sum = $\log 2$).
2. $\sum (-1)^n (\log n)/n$ converges: $(\log n)/n \to 0$, and for $f(x)=(\log x)/x$, $f'(x)=(1-\log x)/x^2 < 0$ when $x>e$, so the sequence decreases for $n\ge 3$.

### 10.12.3 Euler's Constant

**Construction.** Define
$$
a_{2n-1} = \frac{1}{n}, \qquad a_{2n} = \int_n^{n+1}\frac{dx}{x} = \log(n+1)-\log n.
$$
Then $a_n \to 0$ and $a_n \searrow$, so $\sum (-1)^{n-1}a_n$ converges. Its $(2n-1)$st partial sum is
$$
s_{2n-1} = 1 + \frac{1}{2} + \cdots + \frac{1}{n} - \log n.
$$
Since $s_{2n-1}$ tends to a limit, we obtain **Euler's constant**:
$$
\boxed{\lim_{n\to\infty}\Bigl(1 + \frac{1}{2} + \cdots + \frac{1}{n} - \log n\Bigr) = C}
$$

- $C \approx 0.5772156649\dots$ (to ten decimals).
- It is still **unknown** whether $C$ is rational or irrational.

**Asymptotic formula:**
$$
\sum_{k=1}^{n}\frac{1}{k} = \log n + C + o(1) \qquad (n\to\infty).
$$
Hence the partial sums of the harmonic series are asymptotically equal to $\log n$:
$$
\sum_{k=1}^{n}\frac{1}{k} \sim \log n.
$$

**Example (alternating harmonic series).** Let $s_m = \sum_{k=1}^{m}(-1)^{k-1}/k$. Separating even and odd terms for $m=2n$:
$$
s_{2n} = \sum_{k=1}^{n}\frac{1}{2k-1} - \sum_{k=1}^{n}\frac{1}{2k}
     = \sum_{k=1}^{2n}\frac{1}{k} - \sum_{k=1}^{n}\frac{1}{k}.
$$
Applying the asymptotic formula:
$$
s_{2n} = \bigl(\log 2n + C + o(1)\bigr) - \bigl(\log n + C + o(1)\bigr) = \log 2 + o(1).
$$
Therefore $s_{2n} \to \log 2$, confirming the sum of the alternating harmonic series.

## 10.13 Conditional and Absolute Convergence

### 10.13.1 Absolute Convergence Implies Convergence

**Theorem.** If $\sum |a_n|$ converges, then $\sum a_n$ also converges, and
$$
\Bigl|\sum_{n=1}^{\infty}a_n\Bigr| \le \sum_{n=1}^{\infty}|a_n|.
$$

**Proof sketch.**
- **Real case:** Let $b_n = a_n + |a_n|$. Then $b_n$ is either $0$ or $2|a_n|$, so $0 \le b_n \le 2|a_n|$. By comparison, $\sum b_n$ converges; hence $\sum a_n = \sum b_n - \sum |a_n|$ converges.
- **Complex case:** Write $a_n = u_n + iv_n$. Since $|u_n| \le |a_n|$ and $|v_n| \le |a_n|$, absolute convergence of $\sum |a_n|$ implies convergence of $\sum |u_n|$ and $\sum |v_n|$, hence of $\sum u_n$ and $\sum v_n$.
- The triangle inequality $|\sum_{k=1}^n a_k| \le \sum_{k=1}^n |a_k|$ gives the stated bound as $n\to\infty$.

### 10.13.2 Definitions

- **Absolutely convergent:** $\sum |a_n|$ converges.
- **Conditionally convergent:** $\sum a_n$ converges but $\sum |a_n|$ diverges.

> The alternating harmonic series $\sum (-1)^{n-1}/n$ is **conditionally convergent**.

**Linearity.** If $\sum a_n$ and $\sum b_n$ are absolutely convergent, so is $\sum(\alpha a_n + \beta b_n)$ for any scalars $\alpha,\beta$.

## 10.14 The Convergence Tests of Dirichlet and Abel

### 10.14.1 Abel's Partial Summation Formula

Let $\{a_n\},\{b_n\}$ be sequences of complex numbers and let $A_n = \sum_{k=1}^n a_k$. Then
$$
\boxed{\sum_{k=1}^{n}a_k b_k = A_n b_{n+1} + \sum_{k=1}^{n}A_k(b_k - b_{k+1})}
$$

**Proof.** With $A_0=0$, write $a_k = A_k - A_{k-1}$; the identity follows by rearranging the double sum.

> If $A_n b_{n+1} \to L$ and $\sum A_k(b_k - b_{k+1})$ converges, then $\sum a_k b_k$ converges.

### 10.14.2 Dirichlet's Test

**Theorem.** Let $\sum a_n$ be a series of complex terms whose partial sums form a **bounded** sequence. Let $\{b_n\}$ be a **decreasing** sequence with $b_n \to 0$. Then $\sum a_n b_n$ **converges**.

**Proof sketch.** $|A_n| \le M$ implies $A_n b_{n+1} \to 0$. Since $b_n \searrow$,
$$
|A_k(b_k - b_{k+1})| \le M(b_k - b_{k+1}),
$$
and $\sum (b_k - b_{k+1})$ is a convergent telescoping series, so $\sum A_k(b_k - b_{k+1})$ converges absolutely.

### 10.14.3 Abel's Test

**Theorem.** Let $\sum a_n$ be a **convergent** series of complex terms and let $\{b_n\}$ be a **monotonic convergent** sequence of real terms. Then $\sum a_n b_n$ **converges**.

> The proof is analogous to Dirichlet's test, using that $\{A_n\}$ is bounded and $A_n b_{n+1}$ converges.

### 10.14.4 Bounded Partial Sums of a Geometric Series on the Unit Circle

**Theorem.** For every real $\theta$ not an integer multiple of $\pi$,
$$
\sum_{k=1}^{n}e^{2ik\theta} = \frac{\sin n\theta}{\sin\theta}\,e^{i(n+1)\theta},
\qquad
\Bigl|\sum_{k=1}^{n}e^{2ik\theta}\Bigr| \le \frac{1}{|\sin\theta|}.
$$

**Proof.** Use the geometric-series formula $\sum_{k=1}^n x^k = x(x^n-1)/(x-1)$ with $x=e^{2i\theta}$; simplify using Euler's formula to obtain the closed form. The estimate follows from $|\sin n\theta|\le 1$ and $|e^{i(n+1)\theta}|=1$.

> This shows that $\sum x^n$ with $|x|=1$, $x\neq 1$ has bounded partial sums鈥攁 key example for Dirichlet's test.

### 10.14.5 Applications

**Example.** If $\{b_n\}$ is any decreasing real sequence with $b_n \to 0$ and $|x|=1$, $x\neq 1$, then by Dirichlet's test
$$
\sum_{n=1}^{\infty} b_n x^n \quad\text{converges}.
$$
- Leibniz's rule is the special case $x=-1$.
- Writing $x=e^{i\theta}$ and taking real/imaginary parts, the trigonometric series
  $$\sum_{n=1}^{\infty} b_n\cos n\theta, \qquad \sum_{n=1}^{\infty} b_n\sin n\theta$$
  both converge (for $\theta$ not a multiple of $2\pi$).

**Special case $b_n = n^{-\alpha}$ $(\alpha>0)$:**
$$
\sum_{n=1}^{\infty}\frac{e^{in\theta}}{n^{\alpha}},\quad
\sum_{n=1}^{\infty}\frac{\cos n\theta}{n^{\alpha}},\quad
\sum_{n=1}^{\infty}\frac{\sin n\theta}{n^{\alpha}}
$$
all converge. When $\alpha>1$ they converge **absolutely** (dominated by $\sum n^{-\alpha}$).

## 10.15 Rearrangements of Series

### 10.15.1 A Surprising Example

Finite sums can be rearranged without changing their value, but this is **not always true** for infinite series (Cauchy, 1833).

**Example.** The alternating harmonic series
$$
1 - \frac{1}{2} + \frac{1}{3} - \frac{1}{4} + \cdots = \log 2.
$$
Rearrange it by taking **two positive terms followed by one negative term**:
$$
1 + \frac{1}{3} - \frac{1}{2} + \frac{1}{5} + \frac{1}{7} - \frac{1}{4} + \cdots
$$
Let $t_{3m}$ be the $(3m)$th partial sum:
$$
t_{3m} = \sum_{k=1}^{2m}\frac{1}{2k-1} - \sum_{k=1}^{m}\frac{1}{2k}
     = \sum_{k=1}^{4m}\frac{1}{k} - \frac{1}{2}\sum_{k=1}^{2m}\frac{1}{k} - \frac{1}{2}\sum_{k=1}^{m}\frac{1}{k}.
$$
Using $\sum_{k=1}^{n}1/k = \log n + C + o(1)$,
$$
t_{3m} = (\log 4m + C) - \tfrac{1}{2}(\log 2m + C) - \tfrac{1}{2}(\log m + C) + o(1)
     = \tfrac{3}{2}\log 2 + o(1).
$$
Hence the rearranged series converges to $\frac{3}{2}\log 2 \neq \log 2$.

### 10.15.2 Definition of Rearrangement

A **permutation** of $\mathbb{P}=\{1,2,3,\dots\}$ is a one-to-one mapping $f:\mathbb{P}\to\mathbb{P}$. If $b_n = a_{f(n)}$, then $\sum b_n$ is called a **rearrangement** of $\sum a_n$.

### 10.15.3 Absolute Convergence Preserves the Sum

**Theorem.** Let $\sum a_n$ be **absolutely convergent** with sum $S$. Then every rearrangement of $\sum a_n$ also converges absolutely and has sum $S$.

**Proof sketch.** Let $b_n = a_{f(n)}$. Then $\sum|b_n|$ converges because its partial sums are bounded by $\sum|a_n|$. Given $\varepsilon>0$, choose $N$ so that $|A_N-S|<\varepsilon/2$ and $\sum_{k>N}|a_k|<\varepsilon/2$. Choose $M$ large enough that $\{1,\dots,N\}\subseteq\{f(1),\dots,f(M)\}$. For $n\ge M$,
$$
|B_n - S| \le |B_n - A_N| + |A_N - S| < \frac{\varepsilon}{2} + \frac{\varepsilon}{2} = \varepsilon.
$$
Thus $B_n \to S$.

### 10.15.4 Positive and Negative Parts

Define
$$
a_n^+ = \frac{a_n+|a_n|}{2} = \max(a_n,0), \qquad a_n^- = \frac{a_n-|a_n|}{2} = \min(a_n,0).
$$

**Theorem.** For a series $\sum a_n$ of real terms:
- **(a)** If $\sum a_n$ is **conditionally convergent**, both $\sum a_n^+$ and $\sum a_n^-$ **diverge**.
- **(b)** If $\sum a_n$ is **absolutely convergent**, both $\sum a_n^+$ and $\sum a_n^-$ **converge**, and
  $$\sum_{n=1}^{\infty}a_n = \sum_{n=1}^{\infty}a_n^+ + \sum_{n=1}^{\infty}a_n^-.$$

> Part (a) follows from linearity: $\sum a_n$ converges but $\sum|a_n|$ diverges, so neither signed part can converge.

### 10.15.5 Riemann's Rearrangement Theorem

**Theorem.** Let $\sum a_n$ be a **conditionally convergent** series of real terms, and let $S$ be any real number. Then there exists a rearrangement $\sum b_n$ of $\sum a_n$ which converges to $S$.

**Proof sketch.** Since $\sum a_n^+$ diverges to $+\infty$ and $\sum a_n^-$ diverges to $-\infty$ (and $a_n\to 0$), we can:
1. Take just enough positive terms so their sum **exceeds** $S$.
2. Add just enough negative terms so the sum falls **below** $S$.
3. Repeat.

Each partial sum of the rearrangement differs from $S$ by at most one term, and since $a_n\to 0$, the partial sums converge to $S$.

> **Key insight:** Absolute convergence guarantees rearrangement invariance; conditional convergence allows rearrangement to any desired sum.

## 10.16 Improper Integrals

### 10.16.1 Infinite Integrals (First Kind)

If $\int_a^b f(x)\,dx$ exists for every $b\ge a$, define the **infinite integral**
$$
\int_a^{\infty} f(x)\,dx = \lim_{b\to+\infty}\int_a^{b}f(x)\,dx.
$$
The integral **converges** if the limit exists and is finite; otherwise it **diverges**.

**Examples:**
1. $\displaystyle\int_1^{\infty}x^{-s}\,dx$ converges iff $s>1$, with value $1/(s-1)$. (Analogous to the zeta series.)
2. $\displaystyle\int_0^{\infty}\sin x\,dx$ diverges ($1-\cos b$ has no limit).
3. $\displaystyle\int_{-\infty}^{\infty}e^{-a|x|}\,dx = 2/a$ for $a>0$.

For doubly infinite intervals:
$$
\int_{-\infty}^{\infty}f(x)\,dx = \int_{-\infty}^{c}f(x)\,dx + \int_{c}^{\infty}f(x)\,dx,
$$
convergent iff **both** integrals on the right converge (the choice of $c$ is irrelevant).

### 10.16.2 Convergence Tests for Nonnegative Integrands

**Theorem (Boundedness criterion).** If $f(x)\ge 0$ for $x\ge a$, then $\int_a^{\infty}f(x)\,dx$ converges iff there exists $M>0$ such that $\int_a^b f(x)\,dx \le M$ for all $b\ge a$.

**Comparison test.** If $0\le f(x)\le g(x)$ for $x\ge a$ and $\int_a^{\infty}g$ converges, then $\int_a^{\infty}f$ also converges and $\int_a^{\infty}f \le \int_a^{\infty}g$.

**Limit comparison test.** Let $f(x)\ge 0$, $g(x)>0$ for $x\ge a$. If
$$
\lim_{x\to+\infty}\frac{f(x)}{g(x)} = c \neq 0,
$$
then $\int_a^{\infty}f$ and $\int_a^{\infty}g$ either both converge or both diverge. If $c=0$, convergence of $\int_a^{\infty}g$ implies convergence of $\int_a^{\infty}f$.

**Example.** $\int_1^{\infty}e^{-x}x^{s}\,dx$ converges for every real $s$ (compare with $x^{-2}$).

### 10.16.3 Improper Integrals of the Second Kind

Suppose $f$ is defined on $(a,b]$ and $\int_x^b f(t)\,dt$ exists for $a<x\le b$. Define
$$
\int_{a+}^{b}f(t)\,dt = \lim_{x\to a^+}\int_x^{b}f(t)\,dt.
$$

**Example.** $\displaystyle\int_{0+}^{b}t^{-s}\,dt$ converges iff $s<1$.

> **Connection between the two kinds.** By the substitution $t=1/u$,
> $$\int_x^{b}t^{-s}\,dt = \int_{1/b}^{1/x}u^{s-2}\,du,$$
> so convergence of the second-kind integral for $s$ is equivalent to convergence of the first-kind integral for $2-s$.

**Gabriel's horn.** For $f(x)=x^{-3/4}$ on $(0,1]$:
- $\int_0^1 f(x)\,dx$ **converges** (finite area),
- but $\int_0^1 \pi f(x)^2\,dx$ **diverges** (infinite volume of revolution).

If $f$ is unbounded at an interior point $c$, split:
$$
\int_{a+}^{b-}f(t)\,dt = \int_{a+}^{c}f(t)\,dt + \int_{c}^{b-}f(t)\,dt.
$$
Mixed combinations (e.g. $\int_{a+}^{\infty}$) are defined analogously.

### 10.16.4 The Gamma Function

For $s>0$ the integral
$$
\Gamma(s) = \int_{0+}^{\infty}e^{-t}t^{s-1}\,dt
$$
converges. Split it as $\int_{0+}^{1} + \int_{1}^{\infty}$:
- The second integral converges for all real $s$ (by comparison with $e^{-t/2}$).
- The first integral converges for $s>0$ (by comparison with $t^{s-1}$).

**Key property:** $\Gamma(n+1) = n!$ for every integer $n\ge 0$.

> The gamma function, introduced by Euler in 1729, extends factorials to positive real arguments.

# 11. Sequences and Series of Functions

## 11.1 Pointwise Convergence of Sequences of Functions

### 11.1.1 Definition

A sequence $\{f_n\}$ of real- or complex-valued functions with a common domain converges **pointwise** to a **limit function** $f$ on a set $S$ if for each $x\in S$:
$$
f(x) = \lim_{n\to\infty} f_n(x).
$$

### 11.1.2 Why Pointwise Convergence Is Not Enough

A central question: if each $f_n$ is continuous/differentiable/integrable, is the limit function $f$ also? In general, **no**.

**Example 1 (continuity lost).** Let $f_n(x)=x^n$ on $[0,1]$. Each $f_n$ is continuous, but
$$
\lim_{n\to\infty}f_n(x) = f(x) = \begin{cases} 0 & 0\le x<1,\\ 1 & x=1, \end{cases}
$$
which is **discontinuous** at $x=1$.

**Example 2 (integral vs. limit).** Let $f_n(x)=nx(1-x^2)^n$ on $[0,1]$. Then $f_n\to 0$ pointwise, yet
$$
\int_0^1 f_n(x)\,dx = \frac{n}{2(n+1)} \to \frac{1}{2} \neq 0 = \int_0^1 \lim_{n\to\infty}f_n(x)\,dx.
$$
> The operations of **limit** and **integration** cannot always be interchanged under mere pointwise convergence.

Historical note: Stokes, Seidel (1848), and Weierstrass recognized that an extra condition鈥攏ow called **uniform convergence**鈥攊s needed to justify interchanging limits with integration (and other operations).

## 11.2 Uniform Convergence of Sequences of Functions

### 11.2.1 Definition

A sequence $\{f_n\}$ converges **uniformly** to $f$ on a set $S$ if for every $\varepsilon>0$ there exists an integer $N$ (depending **only on $\varepsilon$**) such that
$$
|f_n(x)-f(x)| < \varepsilon \qquad\text{for all }x\in S\text{ and all }n\ge N.
$$
Symbolically: $f_n\to f$ **uniformly on** $S$.

> In pointwise convergence $N$ may depend on both $\varepsilon$ **and** $x$; in uniform convergence $N$ works for **all** $x\in S$ simultaneously.

### 11.2.2 Geometric Meaning

When $f_n$ are real-valued, $|f_n(x)-f(x)|<\varepsilon$ is equivalent to
$$
f(x)-\varepsilon < f_n(x) < f(x)+\varepsilon \qquad\text{for all }x\in S.
$$
For $n\ge N$, the **entire graph** of $f_n$ over $S$ lies inside a band of height $2\varepsilon$ centered on the graph of $f$.

## 11.3 Uniform Convergence and Continuity

**Theorem.** Assume $f_n\to f$ **uniformly** on an interval $S$. If each $f_n$ is continuous at a point $p\in S$, then the limit function $f$ is also continuous at $p$.

**Proof sketch ($\varepsilon/3$ argument).** Given $\varepsilon>0$, choose $N$ so that $|f_n(x)-f(x)|<\varepsilon/3$ for all $x\in S$ and $n\ge N$. Since $f_N$ is continuous at $p$, there is a neighborhood $N(p)$ with $|f_N(x)-f_N(p)|<\varepsilon/3$ for $x\in N(p)\cap S$. Then
$$
|f(x)-f(p)| \le |f(x)-f_N(x)| + |f_N(x)-f_N(p)| + |f_N(p)-f(p)| < \frac{\varepsilon}{3}+\frac{\varepsilon}{3}+\frac{\varepsilon}{3}=\varepsilon.
$$

### 11.3.1 Corollary for Series

**Theorem.** If a series of functions $\sum u_k$ converges **uniformly** to $f$ on $S$, and each $u_k$ is continuous at $p\in S$, then $f$ is also continuous at $p$.

Symbolically:
$$
\lim_{x\to p}\sum_{k=1}^{\infty}u_k(x) = \sum_{k=1}^{\infty}\lim_{x\to p}u_k(x).
$$
> For a uniformly convergent series we may pass to the limit **term by term**.

## 11.4 Uniform Convergence and Integration

**Theorem.** Assume $f_n\to f$ uniformly on $[a,b]$ and each $f_n$ is continuous on $[a,b]$. Define
$$
g_n(x)=\int_a^x f_n(t)\,dt, \qquad g(x)=\int_a^x f(t)\,dt.
$$
Then $g_n\to g$ **uniformly** on $[a,b]$. In symbols:
$$
\boxed{\lim_{n\to\infty}\int_a^x f_n(t)\,dt = \int_a^x \lim_{n\to\infty}f_n(t)\,dt}
$$

**Proof sketch.** Choose $N$ so that $|f_n(t)-f(t)|<\varepsilon/(b-a)$ for all $t\in[a,b]$ and $n\ge N$. Then for any $x\in[a,b]$,
$$
|g_n(x)-g(x)| \le \int_a^x|f_n(t)-f(t)|\,dt < \int_a^b\frac{\varepsilon}{b-a}\,dt = \varepsilon.
$$

### 11.4.1 Term-by-Term Integration of Series

**Theorem.** If $\sum u_k$ converges uniformly to $f$ on $[a,b]$ and each $u_k$ is continuous on $[a,b]$, then
$$
\sum_{k=1}^{\infty}\int_a^x u_k(t)\,dt = \int_a^x \sum_{k=1}^{\infty}u_k(t)\,dt \qquad (x\in[a,b]).
$$
> A uniformly convergent series may be **integrated term by term**.

## 11.5 A Sufficient Condition for Uniform Convergence

### 11.5.1 The Weierstrass M-Test

**Theorem.** Let $\sum u_n$ be a series of functions which converges pointwise to $f$ on a set $S$. If there exists a convergent series of positive constants $\sum M_n$ such that
$$
0 \le |u_n(x)| \le M_n \qquad\text{for all }n\ge 1\text{ and all }x\in S,
$$
then $\sum u_n$ **converges uniformly** on $S$.

**Proof sketch.** For each $x\in S$ the comparison test gives absolute convergence. The remainder is bounded independently of $x$:
$$
\Bigl|f(x)-\sum_{k=1}^{n}u_k(x)\Bigr| = \Bigl|\sum_{k=n+1}^{\infty}u_k(x)\Bigr| \le \sum_{k=n+1}^{\infty}|u_k(x)| \le \sum_{k=n+1}^{\infty}M_k.
$$
Since $\sum M_k$ converges, its tail can be made $<\varepsilon$ for all $n\ge N$, and the same $N$ works for every $x\in S$.

### 11.5.2 Warning on Term-by-Term Differentiation

Even for uniformly convergent series, **term-by-term differentiation** is not always valid.

**Example.** The series $\displaystyle\sum_{n=1}^{\infty}\frac{\sin nx}{n^2}$ converges **uniformly** on $\mathbb{R}$ (dominated by $\sum 1/n^2$). But the differentiated series
$$
\sum_{n=1}^{\infty}\frac{\cos nx}{n}
$$
**diverges** at $x=0$. Thus differentiation may destroy convergence.

> Justifying the interchange of differentiation and summation is harder than for integration. Power series are a notable exception.

## 11.6 Power Series and the Circle of Convergence

### 11.6.1 Definition

A **power series** in $z-a$ is an infinite series of the form
$$
\sum_{n=0}^{\infty}a_n(z-a)^n = a_0 + a_1(z-a) + a_2(z-a)^2 + \cdots,
$$
where $z,a,a_n$ may be complex. With each power series there is associated a **circle of convergence** centered at $a$ with **radius of convergence** $r$:
- converges absolutely for every $z$ with $|z-a|<r$,
- diverges for every $z$ with $|z-a|>r$.

The boundary $|z-a|=r$ may exhibit any behavior: convergence at none, some, or all boundary points.

### 11.6.2 Finding the Radius

The ratio test or root test usually determines $r$.

**Example 1.** $\displaystyle\sum_{n=0}^{\infty}\frac{z^n}{n!}$. By the ratio test,
$$
\Bigl|\frac{z^{n+1}}{(n+1)!}\cdot\frac{n!}{z^n}\Bigr| = \frac{|z|}{n+1} \to 0
$$
for every $z$. Hence $r=+\infty$; the series converges for all complex $z$. In particular,
$$
\lim_{n\to\infty}\frac{z^n}{n!}=0 \quad\text{for every fixed }z.
$$

**Example 2.** $\displaystyle\sum n^2 3^n z^n$. By the root test,
$$
(n^2 3^n |z|^n)^{1/n} = 3|z|\,n^{2/n} \to 3|z|.
$$
The series converges absolutely if $|z|<1/3$ and diverges if $|z|>1/3$; thus $r=1/3$. At every boundary point ($|z|=1/3$) the general term has absolute value $n^2\not\to 0$, so the series diverges on the boundary.

**Example 3.** $\displaystyle\sum \frac{z^n}{n}$ and $\displaystyle\sum \frac{z^n}{n^2}$ both have $r=1$.
- $\sum z^n/n$ diverges at $z=1$ but converges at all other boundary points.
- $\sum z^n/n^2$ converges at **every** boundary point (dominated by $\sum 1/n^2$).

### 11.6.3 Absolute and Uniform Convergence Inside the Disk

**Theorem 11.6.** Assume $\sum a_n z^n$ converges for some $z_1\neq 0$. Then:
- **(a)** The series converges **absolutely** for every $z$ with $|z|<|z_1|$.
- **(b)** The series converges **uniformly** on every closed disk $|z|\le R$ with $R<|z_1|$.

**Proof sketch.** Since $a_n z_1^n\to 0$, we have $|a_n z_1^n|<1$ for $n\ge N$. For $|z|\le R<|z_1|$,
$$
|a_n z^n| = |a_n z_1^n|\cdot\Bigl|\frac{z}{z_1}\Bigr|^n < \Bigl(\frac{R}{|z_1|}\Bigr)^n = t^n, \qquad 0<t<1.
$$
By the Weierstrass $M$-test with $M_n=t^n$, the series converges uniformly on the disk; absolute convergence follows.

### 11.6.4 Existence of the Circle of Convergence

**Theorem 11.7.** Assume the power series $\sum a_n z^n$ converges for at least one $z_1\neq 0$ and diverges for at least one $z_2$. Then there exists a positive real number $r$ such that the series converges absolutely if $|z|<r$ and diverges if $|z|>r$.

**Proof sketch.** Let $A$ be the set of all positive numbers $|z|$ for which the series converges. $A$ is nonempty ($|z_1|\in A$) and bounded above by $|z_2|$. Let $r=\sup A$. By Theorem 11.6, if $|z|<r$ there is $x\in A$ with $|z|<x<r$, so the series converges absolutely; if $|z|>r$ then $|z|\notin A$, so the series diverges.

> For a power series in $z-a$, the same result holds after the change of variable $Z=z-a$; the circle of convergence is centered at $a$.

## 11.7 Properties of Functions Represented by Real Power Series

### 11.7.1 Interval of Convergence

A **real power series** has the form $\sum a_n(x-a)^n$ with real $z,a,a_n$. Its circle of convergence intersects the real axis in a symmetric interval $(a-r,a+r)$, called the **interval of convergence**. The number $r$ is the radius of convergence.

Each real power series defines a sum function
$$
f(x)=\sum_{n=0}^{\infty}a_n(x-a)^n \qquad (a-r<x<a+r).
$$
The series is called the **power-series expansion** of $f$ about $a$.

### 11.7.2 Continuity and Term-by-Term Integration

**Theorem 11.8.** If $f$ is represented by the power series $\sum a_n(x-a)^n$ in $(a-r,a+r)$, then:
- $f$ is **continuous** on this interval.
- Its integral over any closed subinterval may be computed by **integrating term by term**:
  $$
  \int_a^x f(t)\,dt = \sum_{n=0}^{\infty}\frac{a_n}{n+1}(x-a)^{n+1} \qquad (a-r<x<a+r).
  $$

> The integrated series has the **same radius of convergence** as the original series.

### 11.7.3 Term-by-Term Differentiation

**Theorem 11.9.** Let $f$ be represented by $\sum a_n(x-a)^n$ in $(a-r,a+r)$. Then:
- **(a)** The differentiated series $\displaystyle\sum_{n=1}^{\infty}na_n(x-a)^{n-1}$ also has radius of convergence $r$.
- **(b)** $f$ is **differentiable** at each $x$ in the interval, and
  $$
  f'(x)=\sum_{n=1}^{\infty}na_n(x-a)^{n-1}.
  $$

**Proof sketch.** Assume $a=0$. For $0<x<r$ and small $h>0$,
$$
\frac{f(x+h)-f(x)}{h}=\sum_{n=0}^{\infty}a_n\frac{(x+h)^n-x^n}{h}.
$$
By the mean-value theorem, $(x+h)^n-x^n=hnc_n^{n-1}$ with $x<c_n<x+h$. The resulting series $\sum na_nc_n^{n-1}$ is absolutely convergent and dominates $\sum na_nx^{n-1}$, proving (a). Let $g$ be the sum of the differentiated series; integrating $g$ term by term gives $\int_0^x g(t)\,dt=f(x)-a_0$, so by the fundamental theorem of calculus $f'=g$, proving (b).

> Since every power series can be obtained by differentiating its integrated series, all three series (original, integrated, differentiated) have the **same radius of convergence**.

### 11.7.4 Taylor Coefficients and Uniqueness

Repeated term-by-term differentiation yields derivatives of **every** order. Evaluating at $x=a$:
$$
f^{(k)}(a)=k!\,a_k \qquad\Longrightarrow\qquad a_k=\frac{f^{(k)}(a)}{k!}.
$$
Hence every power-series expansion is a **Taylor series**:
$$
\boxed{f(x)=\sum_{k=0}^{\infty}\frac{f^{(k)}(a)}{k!}(x-a)^k}.
$$

**Uniqueness Theorem (11.10).** If two power series $\sum a_n(x-a)^n$ and $\sum b_n(x-a)^n$ have the same sum function in some neighborhood of $a$, then they are equal term by term:
$$
a_n=b_n=\frac{f^{(n)}(a)}{n!} \qquad (n\ge 0).
$$

> The partial sums of a power series are precisely the **Taylor polynomials** of the sum function. They converge pointwise on the interval of convergence and uniformly on every closed subinterval.

## 11.8 The Taylor Series Generated by a Function

### 11.8.1 Definition and the Two Basic Questions

If $f$ has derivatives of every order in an open interval about $a$ (i.e. $f$ is **infinitely differentiable**), we can form the **Taylor series** generated by $f$ at $a$:
$$
\sum_{k=0}^{\infty}\frac{f^{(k)}(a)}{k!}(x-a)^k.
$$

Two natural questions arise:
1. Does this series converge for any $x\neq a$?
2. If it converges, is its sum equal to $f(x)$?

Surprisingly, the answer to both is **no in general**.
- The series may fail to converge for $x\neq a$.
- Even when it converges, its sum may differ from $f(x)$.

### 11.8.2 Taylor's Formula with Remainder

Using Taylor's formula with remainder,
$$
f(x)=\sum_{k=0}^{n}\frac{f^{(k)}(a)}{k!}(x-a)^k+E_n(x),
$$
the Taylor series converges to $f(x)$ **if and only if** the error term tends to $0$:
$$
\lim_{n\to\infty}E_n(x)=0.
$$

## 11.9 A Sufficient Condition for Convergence of a Taylor Series

### 11.9.1 Integral Form of the Remainder

From Theorem 7.6,
$$
E_n(x)=\frac{1}{n!}\int_a^x(x-t)^n f^{(n+1)}(t)\,dt.
$$
With the substitution $t=x+(a-x)u$ ($u$ from $1$ to $0$), this becomes
$$
E_n(x)=\frac{(x-a)^{n+1}}{n!}\int_0^1 u^n f^{(n+1)}[x+(a-x)u]\,du.
$$

### 11.9.2 A Useful Sufficient Condition

**Theorem 11.11.** Assume $f$ is infinitely differentiable in $I=(a-r,a+r)$, and suppose there is a positive constant $A$ such that
$$
|f^{(n)}(x)|\le A^n \qquad\text{for all }n\ge 1\text{ and all }x\in I.
$$
Then the Taylor series of $f$ at $a$ converges to $f(x)$ for every $x\in I$.

**Proof sketch.** Insert the bound into the integral formula:
$$
0\le |E_n(x)|\le\frac{|x-a|^{n+1}}{n!}A^{n+1}\int_0^1 u^n\,du
  =\frac{|x-a|^{n+1}A^{n+1}}{(n+1)!}
  =\frac{B^{n+1}}{(n+1)!},
$$
where $B=A|x-a|$. Since $B^n/n!\to 0$ as $n\to\infty$ for every $B$, we have $E_n(x)\to 0$.

> The condition $|f^{(n)}|\le A^n$ is satisfied by $e^x$, $\sin x$, $\cos x$, etc., so their Taylor expansions are valid everywhere (or on the whole line).

## 11.10 Power-Series Expansions for the Exponential and Trigonometric Functions

### 11.10.1 Sine and Cosine

Since all derivatives of $\sin x$ and $\cos x$ are bounded by $1$ on $\mathbb{R}$, the condition $|f^{(n)}|\le A^n$ of Theorem 11.11 holds with $A=1$. Hence their Taylor expansions are valid for **all real $x$**:
$$
\sin x = x - \frac{x^3}{3!} + \frac{x^5}{5!} - \frac{x^7}{7!} + \cdots + (-1)^{n-1}\frac{x^{2n-1}}{(2n-1)!} + \cdots
$$
$$
\cos x = 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \frac{x^6}{6!} + \cdots + (-1)^{n}\frac{x^{2n}}{(2n)!} + \cdots
$$

### 11.10.2 The Exponential Function

For $f(x)=e^x$ we have $f^{(n)}(x)=e^x$ for all $n$. On any finite interval $(-r,r)$ we have $e^x\le e^r$, so Theorem 11.11 applies with $A=e^r$. Since $r$ is arbitrary, the expansion holds for **all real $x$**:
$$
e^x = 1 + x + \frac{x^2}{2!} + \cdots + \frac{x^n}{n!} + \cdots
$$

### 11.10.3 Analytic Development of Trigonometry

These series can be taken as **definitions** of $\sin x$ and $\cos x$. From them one derives all familiar properties:
- $\sin 0 = 0$, $\cos 0 = 1$
- $\sin(-x) = -\sin x$, $\cos(-x) = \cos x$
- $D\sin x = \cos x$, $D\cos x = -\sin x$

**Addition formulas.** Define
$$
u(x)=\sin(x+a)-\sin x\cos a-\cos x\sin a,
$$
$$
u(x)=\cos(x+a)-\cos x\cos a+\sin x\sin a,
$$
and let $f(x)=[u(x)]^2+[v(x)]^2$. Then $u'=v$ and $v'=-u$, so $f'(x)=0$; since $f(0)=0$, we get $f(x)\equiv 0$, hence $u(x)=v(x)\equiv 0$. Therefore
$$
\sin(x+a)=\sin x\cos a+\cos x\sin a,
$$
$$
\cos(x+a)=\cos x\cos a-\sin x\sin a.
$$

> The number $\pi$ may be introduced as the smallest positive $x$ with $\sin x=0$. From this one obtains period $2\pi$, $\sin(\pi/2)=1$, and $\cos(\pi/2)=0$.

## 11.11 Bernstein's Theorem

### 11.11.1 Statement

**Theorem 11.12 (Bernstein).** Assume $f$ and **all its derivatives** are nonnegative on a closed interval $[0,r]$:
$$
f(x)\ge 0 \quad\text{and}\quad f^{(n)}(x)\ge 0 \qquad\text{for all }x\in[0,r]\text{ and all }n\ge 1.
$$
Then for every $x$ with $0\le x<r$, the Taylor series of $f$ at $0$ converges to $f(x)$:
$$
f(x)=\sum_{k=0}^{\infty}\frac{f^{(k)}(0)}{k!}\,x^k.
$$

### 11.11.2 Proof Sketch

Write Taylor's formula with remainder:
$$
f(x)=\sum_{k=0}^{n}\frac{f^{(k)}(0)}{k!}\,x^k+E_n(x).
$$

**Step 1 — Error estimate.** We show
$$
\boxed{0\le E_n(x)\le\Bigl(\frac{x}{r}\Bigr)^{\!n+1}f(r)} \qquad (0<x<r).
$$
Since $(x/r)^{n+1}\to 0$, this implies $E_n(x)\to 0$.

**Step 2 — Monotonicity argument.** From the integral form of the error with $a=0$:
$$
E_n(x)=\frac{x^{n+1}}{n!}\int_0^1 u^n f^{(n+1)}(x-xu)\,du.
$$
Set $F_n(x)=E_n(x)/x^{n+1}$. Because $f^{(n+1)}$ is monotone increasing on $[0,r]$ (its derivative is nonnegative),
$$
f^{(n+1)}[x(1-u)]\le f^{(n+1)}[r(1-u)] \qquad (0\le u\le 1).
$$
Hence $F_n(x)\le F_n(r)$, i.e.
$$
\frac{E_n(x)}{x^{n+1}}\le\frac{E_n(r)}{r^{n+1}}.
$$

**Step 3 — Bounding $E_n(r)$.** Setting $x=r$ in Taylor's formula, every term of the sum is nonnegative, so $E_n(r)\le f(r)$. Combining with Step 2 yields the desired estimate.

> Bernstein's condition is weaker than the exponential bound $|f^{(n)}|\le A^n$; it applies, for example, to functions like $e^x$ and many other completely monotone functions.

## 11.12 Power Series and Differential Equations

### 11.12.1 The Method of Undetermined Coefficients

Power series can provide solutions of differential equations when other methods fail. The idea is to assume a solution of the form
$$
y=\sum_{n=0}^{\infty}a_n x^n
$$
and determine the coefficients recursively.

### 11.12.2 Example

Consider the equation
$$
(1-x^2)y''=-2y.
$$
With $y=\sum a_n x^n$ we have $y''=\sum_{n=2}^{\infty}n(n-1)a_n x^{n-2}$. Substituting and equating coefficients gives the recurrence
$$
a_{n+2}=\frac{n-2}{n+2}\,a_n.
$$

**Even coefficients:** $a_2=-a_0$, $a_4=0$, and $a_6=a_8=\cdots=0$.

**Odd coefficients:**
$$
a_{2n+1}=\frac{-1}{(2n+1)(2n-1)}\,a_1.
$$

Hence the general solution is
$$
y=a_0(1-x^2)-a_1\sum_{n=0}^{\infty}\frac{x^{2n+1}}{(2n+1)(2n-1)}.
$$
The ratio test shows convergence for $|x|<1$.

### 11.12.3 Alternative: Computing Derivatives at the Origin

Since $a_n=f^{(n)}(0)/n!$, the coefficients can also be found by repeated differentiation of the differential equation. Setting $x=0$ in $(1-x^2)y''=-2y$ gives $f''(0)=-2a_0$, so $a_2=-a_0$. Differentiating the equation successively and evaluating at $0$ yields $a_3, a_4,\dots$.

## 11.13 The Binomial Series

### 11.13.1 The Expansion

For any real $\alpha$ and $|x|<1$,
$$
\boxed{(1+x)^{\alpha}=\sum_{n=0}^{\infty}\binom{\alpha}{n}x^{n}}
$$
where the **generalized binomial coefficient** is
$$
\binom{\alpha}{n}=\frac{\alpha(\alpha-1)\cdots(\alpha-n+1)}{n!}.
$$

When $\alpha$ is a nonnegative integer, all but finitely many coefficients vanish and the series reduces to the ordinary binomial theorem.

### 11.13.2 Proof via Differential Equations

**Step 1 — Convergence.** The ratio test shows absolute convergence for $-1<x<1$.

**Step 2 — Define $f$.** Let
$$
f(x)=\sum_{n=0}^{\infty}\binom{\alpha}{n}x^{n}, \qquad |x|<1.
$$

**Step 3 — Key identity.** For all real $\alpha$ and $n\ge 0$,
$$
(n+1)\binom{\alpha}{n+1}=(\alpha-n)\binom{\alpha}{n},
\qquad\text{equivalently}\qquad
(n+1)\binom{\alpha}{n+1}+n\binom{\alpha}{n}=\alpha\binom{\alpha}{n}.
$$

**Step 4 — Differential equation.** Differentiating $f$ and using the identity:
$$
(1+x)f'(x)=\sum_{n=0}^{\infty}\Bigl[(n+1)\binom{\alpha}{n+1}+n\binom{\alpha}{n}\Bigr]x^{n}
=\alpha\sum_{n=0}^{\infty}\binom{\alpha}{n}x^{n}=\alpha f(x).
$$
Thus $f$ satisfies
$$
y'-\frac{\alpha}{x+1}\,y=0, \qquad f(0)=1.
$$

**Step 5 — Uniqueness.** By Theorem 8.3 (existence-uniqueness for first-order linear ODEs), this initial-value problem has the unique solution $y=(1+x)^{\alpha}$. Hence $f(x)=(1+x)^{\alpha}$.

# 12. Vector Algebra

## 12.1 Historical Introduction

### 12.1.1 Origins

Vector algebra emerged from the need for analytic tools in mechanics and geometry:
- **Lagrange (1788):** Published *Mécanique analytique*, demonstrating the power of analytical methods in mechanics.
- **Hamilton (1805–1865):** Introduced **quaternions**, a new algebraic system that unified algebra and physics.
- **Gibbs (1839–1903) and Heaviside (1850–1925):** Extracted the vector concept from quaternion analysis, creating the subject of **vector algebra**.

### 12.1.2 Three Approaches to Vector Algebra

1. **Geometric:** Vectors are represented by directed line segments (arrows). Operations are defined and studied by geometric methods.
2. **Analytic:** Vectors and operations are described entirely in terms of **numbers** (components). Properties are deduced from properties of numbers.
3. **Axiomatic:** Vectors and operations are **undefined concepts** satisfying a set of axioms. This algebraic system is called a **linear space** or **linear vector space** (studied in detail in Chapter 15).

> The analytic approach is adopted here; geometric pictures are used for motivation when possible.

## 12.2 The Vector Space of $n$-Tuples of Real Numbers

### 12.2.1 Definition

An ordered $n$-tuple of real numbers
$$
A=(a_1,a_2,\dots,a_n)
$$
is called an **$n$-dimensional vector** (or $n$-dimensional point). The numbers $a_i$ are its **coordinates** or **components**. The collection of all such vectors is the **vector space of $n$-tuples**, denoted $V_n$.

> Notation: vectors by capital letters $A,B,C,\dots$; components by corresponding small letters $a,b,c,\dots$.

### 12.2.2 Equality, Addition, and Scalar Multiplication

- **Equality:** $A=B$ means $a_i=b_i$ for all $i=1,\dots,n$.
- **Addition:** $A+B=(a_1+b_1,a_2+b_2,\dots,a_n+b_n)$.
- **Scalar multiplication:** $cA=(ca_1,ca_2,\dots,ca_n)$.

### 12.2.3 Algebraic Properties

**Theorem 12.1.** For all vectors in $V_n$ and all scalars:
- **Commutativity:** $A+B=B+A$
- **Associativity:** $A+(B+C)=(A+B)+C$
- **Scalar associativity:** $c(dA)=(cd)A$
- **Distributive laws:** $c(A+B)=cA+cB$ and $(c+d)A=cA+dA$

### 12.2.4 Zero Vector, Negative, and Subtraction

- **Zero vector** $O=(0,0,\dots,0)$: satisfies $A+O=A$ for every $A$.
- **Negative:** $-A=(-1)A=(-a_1,-a_2,\dots,-a_n)$.
- **Subtraction:** $A-B=A+(-B)$; note $(A+B)-B=A$.
- $0A=O$ and $1A=A$.

### 12.2.5 Complex Numbers and Two-Dimensional Vectors

Complex numbers and vectors in $V_2$ are defined as ordered pairs of real numbers and are added in exactly the same way. They differ only when **multiplication** is introduced:
- Complex-number multiplication gives the field properties.
- For $n>2$ it is impossible to introduce multiplication in $V_n$ satisfying all field properties (only $n=1,2$ are possible).

Special products that do **not** satisfy all field properties:
- **Dot product** (Section 12.5): defined in any $V_n$; result is a **scalar**.
- **Cross product** (Section 13.9): defined only in $V_3$; result is a **vector**, but it is not commutative.

## 12.3 Geometric Interpretation for $n\le 3$

### 12.3.1 Geometric Vectors

A pair of points $A$ and $B$ defines a **geometric vector** $\overrightarrow{AB}$: an arrow from the **initial point** $A$ to the **terminal point** (tip) $B$.

Geometric vectors are especially convenient for physical quantities possessing both **magnitude** and **direction** (force, displacement, velocity, acceleration). The length of the arrow measures the magnitude; the arrowhead indicates the direction.

### 12.3.2 Equivalent Vectors

Two geometric vectors $\overrightarrow{AB}$ and $\overrightarrow{CD}$ are called **equivalent** whenever
$$
B-A=D-C.
$$
Equivalently, in components: $b_1-a_1=d_1-c_1$ and $b_2-a_2=d_2-c_2$.

> Equivalent arrows have equal lengths, are parallel, and point in the same direction. The four points $A,B,C,D$ are vertices of a parallelogram.

### 12.3.3 Parallelogram Law of Addition

In a parallelogram, opposite vertices have the same sum: $A+D=B+C$. If $A=O$ (the origin), the geometric vector from $O$ to $D$ corresponds to the vector sum $D=B+C$.

> **Vector addition corresponds geometrically to the parallelogram law.** Many physical quantities combine in exactly this way.

For simplicity we write $A$ for the geometric vector $\overrightarrow{OA}$; any geometric vector equivalent to $\overrightarrow{OA}$ is also denoted by $A$.

### 12.3.4 Subtraction and Scalar Multiplication

- **Subtraction:** $B-A$ is the vector from $A$ to $B$.
- **Scalar multiplication:** If $B=cA$, the geometric vector $B$ has length $|c|$ times the length of $A$; it points in the same direction if $c>0$ and in the opposite direction if $c<0$.

### 12.3.5 Parallelism in $V_n$

**Definition.** Two vectors $A$ and $B$ in $V_n$:
- have the **same direction** if $B=cA$ for some $c>0$;
- have the **opposite direction** if $B=cA$ for some $c<0$;
- are **parallel** if $B=cA$ for some $c\neq 0$.

> The zero vector is parallel only to itself and is the only vector having the opposite direction to itself.

## 12.4 The Dot Product

### 12.4.1 Definition

If $A=(a_1,\dots,a_n)$ and $B=(b_1,\dots,b_n)$ are vectors in $V_n$, their **dot product** (or **scalar product**) is
$$
A\cdot B=\sum_{k=1}^{n}a_k b_k.
$$

### 12.4.2 Algebraic Properties

**Theorem 12.2.** For all vectors $A,B,C$ in $V_n$ and all scalars $c$:
- **(a)** $A\cdot B=B\cdot A$ (commutative law)
- **(b)** $A\cdot(B+C)=A\cdot B+A\cdot C$ (distributive law)
- **(c)** $c(A\cdot B)=(cA)\cdot B=A\cdot(cB)$ (homogeneity)
- **(d)** $A\cdot A>0$ if $A\neq O$ (positivity)
- **(e)** $A\cdot A=0$ if $A=O$

### 12.4.3 The Cauchy–Schwarz Inequality

**Theorem 12.3.** For any vectors $A,B$ in $V_n$,
$$
\boxed{(A\cdot B)^2\le(A\cdot A)(B\cdot B)}
$$
Moreover, equality holds **if and only if** one vector is a scalar multiple of the other.

**Coordinate-free proof.** If either vector is $O$ the result is trivial. Assume both are nonzero and set
$$
C=xA-yB, \qquad\text{where }x=B\cdot B,\; y=A\cdot B.
$$
By positivity, $C\cdot C\ge 0$. Expanding with properties (a)–(c):
$$
C\cdot C=x^2(A\cdot A)-2xy(A\cdot B)+y^2(B\cdot B)
=(B\cdot B)^2(A\cdot A)-2(A\cdot B)^2(B\cdot B)+(A\cdot B)^2(B\cdot B)\ge 0.
$$
Dividing by $B\cdot B>0$ yields $(B\cdot B)(A\cdot A)-(A\cdot B)^2\ge 0$, which is the desired inequality. Equality occurs iff $C=O$, i.e. $xA=yB$, meaning $A$ and $B$ are scalar multiples.

> The Cauchy–Schwarz inequality is fundamental for defining the **length** (norm) of a vector.

## 12.5 Length or Norm of a Vector

### 12.5.1 Definition

In $V_2$ and $V_3$ the length of a geometric vector follows from the theorem of Pythagoras:
$$
\text{length of }A=\sqrt{a_1^2+a_2^2}\;(V_2), \qquad
\text{length of }A=\sqrt{a_1^2+a_2^2+a_3^2}\;(V_3).
$$
This motivates the definition in $V_n$:
$$
\boxed{\|A\|=(A\cdot A)^{1/2}=\Bigl(\sum_{k=1}^{n}a_k^2\Bigr)^{1/2}}.
$$
The quantity $\|A\|$ is called the **norm** (or **length**) of $A$.

### 12.5.2 Properties of the Norm

**Theorem 12.4.** For every vector $A$ in $V_n$ and every scalar $c$:
- **(a)** $\|A\|>0$ if $A\neq O$ (positivity)
- **(b)** $\|A\|=0$ if $A=O$
- **(c)** $\|cA\|=|c|\,\|A\|$ (homogeneity)

### 12.5.3 Cauchy–Schwarz in Norm Form

The Cauchy–Schwarz inequality can be rewritten as
$$
(A\cdot B)^2\le\|A\|^2\|B\|^2 \qquad\text{or}\qquad |A\cdot B|\le\|A\|\,\|B\|.
$$

### 12.5.4 The Triangle Inequality

**Theorem 12.5.** For any vectors $A,B$ in $V_n$,
$$
\boxed{\|A+B\|\le\|A\|+\|B\|}.
$$
Equality holds **if and only if** $A=O$, or $B=O$, or $B=cA$ for some $c>0$.

**Proof.** Squaring both sides gives the equivalent inequality
$$
\|A+B\|^2\le(\|A\|+\|B\|)^2.
$$
The left side expands to $\|A\|^2+2A\cdot B+\|B\|^2$; the right side is $\|A\|^2+2\|A\|\,\|B\|+\|B\|^2$. Thus the inequality reduces to $A\cdot B\le\|A\|\,\|B\|$, which follows from $|A\cdot B|\le\|A\|\,\|B\|$.

> Conversely, the triangle inequality also implies Cauchy–Schwarz.

## 12.6 Orthogonality of Vectors

### 12.6.1 The Polarization Identity

From the proof of the triangle inequality we obtain the useful identity
$$
\|A+B\|^2=\|A\|^2+\|B\|^2+2A\cdot B,
$$
valid for any two vectors in $V_n$.

### 12.6.2 Definition of Orthogonality

In the plane, two perpendicular geometric vectors satisfy the Pythagorean theorem
$$
\|A+B\|^2=\|A\|^2+\|B\|^2.
$$
Comparing with the polarization identity gives $A\cdot B=0$.

**Definition.** Two vectors $A$ and $B$ in $V_n$ are called **perpendicular** or **orthogonal** if
$$
A\cdot B=0.
$$

### 12.6.3 The Pythagorean Identity in $V_n$

**Theorem.** Two vectors $A$ and $B$ in $V_n$ are orthogonal if and only if
$$
\|A+B\|^2=\|A\|^2+\|B\|^2.
$$
This is called the **Pythagorean identity** in $V_n$.

> Orthogonality is the natural generalization of perpendicularity to arbitrary dimension.

## 12.7 Projections and Angle Between Vectors

### 12.7.1 Projection of a Vector

Any vector $A$ can be decomposed as $A=tB+C$ where $C$ is orthogonal to $B$. The vector $tB$ is called the **projection of $A$ along $B$**.

Taking the dot product with $B$ and using $C\cdot B=0$:
$$
t=\frac{A\cdot B}{B\cdot B}=\frac{A\cdot B}{\|B\|^2}.
$$

### 12.7.2 Geometric Meaning of the Dot Product

From the right-triangle interpretation (Figure 12.11),
$$
\cos\theta=\frac{\|tB\|}{\|A\|}=\frac{t\,\|B\|}{\|A\|}=\frac{A\cdot B}{\|A\|\,\|B\|}.
$$
Hence
$$
\boxed{A\cdot B=\|A\|\,\|B\|\cos\theta}.
$$
The dot product equals the product of the lengths times the cosine of the included angle.

### 12.7.3 Angle in $V_n$

By Cauchy–Schwarz,
$$
-1\le\frac{A\cdot B}{\|A\|\,\|B\|}\le 1
$$
for any nonzero vectors. Therefore there is a unique $\theta\in[0,\pi]$ satisfying the formula above.

**Definition.** The **angle** $\theta$ between nonzero vectors $A$ and $B$ in $V_n$ is
$$
\theta=\arccos\frac{A\cdot B}{\|A\|\,\|B\|}.
$$
In particular, $\theta=\pi/2$ when $A\cdot B=0$ (orthogonal vectors).

## 12.8 The Unit Coordinate Vectors

### 12.8.1 Definition

In $V_n$ the **unit coordinate vectors** are
$$
E_1=(1,0,\dots,0),\; E_2=(0,1,0,\dots,0),\;\dots,\; E_n=(0,\dots,0,1).
$$
Each has length $1$, and distinct ones are orthogonal:
$$
E_k\cdot E_j=0 \quad (k\neq j).
$$

### 12.8.2 Standard Basis Representation

**Theorem 12.6.** Every vector $X=(x_1,\dots,x_n)$ in $V_n$ can be expressed **uniquely** as
$$
X=\sum_{k=1}^{n}x_k E_k.
$$

> **Proof.** Immediate from the definitions of addition and scalar multiplication; uniqueness follows from equality of components.

A sum $\sum c_i A_i$ is called a **linear combination** of $A_1,\dots,A_n$. Theorem 12.6 says the unit coordinate vectors **span** $V_n$ (and do so uniquely).

### 12.8.3 Notation in Low Dimensions

- In $V_2$: $E_1, E_2$ are often denoted $\boldsymbol{i}, \boldsymbol{j}$.
- In $V_3$: $E_1, E_2, E_3$ are often denoted $\boldsymbol{i}, \boldsymbol{j}, \boldsymbol{k}$.

Any vector in $V_3$ is then written $A=a_1\boldsymbol{i}+a_2\boldsymbol{j}+a_3\boldsymbol{k}$.

### 12.8.4 Algebraic Manipulations

When vectors are expressed as linear combinations of the unit coordinate vectors, operations follow the usual rules of algebra. For example,
$$
A+B=\sum_{k=1}^{n}a_k E_k+\sum_{k=1}^{n}b_k E_k=\sum_{k=1}^{n}(a_k+b_k)E_k,
$$
and the coefficient of $E_k$ is precisely the $k$th component of $A+B$.

## 12.9 The Linear Span of a Finite Set of Vectors

### 12.9.1 Definition

Let $S=\{A_1,\dots,A_k\}$ be a nonempty set of vectors in $V_n$. If a vector $X$ can be written as
$$
X=\sum_{i=1}^{k}c_i A_i,
$$
then $S$ is said to **span** $X$. The set of all vectors spanned by $S$ is called the **linear span** of $S$, denoted $L(S)$.

In other words, $L(S)$ is the set of all possible linear combinations of vectors in $S$. We say $S$ **spans the whole space** $V_n$ if $L(S)=V_n$.

### 12.9.2 Unique Spanning

**Definition.** $S$ spans $X$ **uniquely** if
$$
X=\sum_{i=1}^{k}c_i A_i=\sum_{i=1}^{k}d_i A_i \quad\Longrightarrow\quad c_i=d_i\text{ for all }i.
$$

**Theorem 12.7.** $S$ spans every vector in $L(S)$ uniquely **if and only if** $S$ spans the zero vector uniquely.

**Proof sketch.** If $S$ spans $O$ uniquely and $X$ has two representations, subtracting gives a representation of $O$; uniqueness for $O$ forces the coefficients to coincide.

## 12.10 Linear Independence

### 12.10.1 Definition

**Definition.** A set $S=\{A_1,\dots,A_k\}$ is **linearly independent** if it spans the zero vector uniquely. Otherwise $S$ is **linearly dependent**.

Equivalently:
- **Independent:** $\displaystyle\sum_{i=1}^{k}c_i A_i=O$ implies all $c_i=0$.
- **Dependent:** there exist scalars $c_1,\dots,c_k$, not all zero, with $\displaystyle\sum_{i=1}^{k}c_i A_i=O$.

> The empty set is agreed to be linearly independent.

### 12.10.2 Examples

1. A subset of an independent set is independent; a superset of a dependent set is dependent.
2. The unit coordinate vectors $E_1,\dots,E_n$ are linearly independent.
3. Any set containing the zero vector is dependent.
4. In $V_2$, $\{i,j,i+j\}$ is dependent, while $\{i,j\}$ is independent.

### 12.10.3 A Key Theorem on Dimension

**Theorem 12.8.** Let $S=\{A_1,\dots,A_k\}$ be linearly independent and let $L(S)$ be its linear span. Then every set of $k+1$ vectors in $L(S)$ is linearly dependent.

> This is the fundamental theorem that underlies the notion of dimension: a $k$-dimensional space cannot contain $k+1$ independent vectors.

**Proof sketch (induction on $k$).** For $k=1$, any two vectors in $L(S)$ are scalar multiples of $A_1$, hence dependent. For the inductive step, write $k+1$ vectors $B_i\in L(S)$ as $B_i=\sum_{j=1}^k a_{ij}A_j$. If all coefficients of $A_1$ vanish, the $B_i$'s lie in the span of $\{A_2,\dots,A_k\}$ and dependence follows from the induction hypothesis. Otherwise, eliminate $A_1$ by forming suitable linear combinations of the $B_i$'s and apply the induction hypothesis again.

### 12.10.4 Orthogonal Sets

**Definition.** A set $S=\{A_1,\dots,A_k\}$ is **orthogonal** if $A_i\cdot A_j=0$ whenever $i\neq j$.

**Theorem 12.9.** Any orthogonal set of **nonzero** vectors in $V_n$ is linearly independent. Moreover, if $X=\sum_{i=1}^{k}c_i A_i$, then the coefficients are given by
$$
\boxed{c_j=\frac{X\cdot A_j}{A_j\cdot A_j}} \qquad (j=1,\dots,k).
$$

**Proof sketch.** Assume $\sum c_i A_i=O$. Take the dot product with $A_j$; orthogonality gives $c_j(A_j\cdot A_j)=0$, and $A_j\neq O$ implies $c_j=0$. For the formula, dot $X$ with $A_j$ and use orthogonality.

### 12.10.5 Orthonormal Sets

An orthogonal set in which every vector has norm $1$ is called an **orthonormal** set. For such a set the coefficient formula simplifies to
$$
c_j=X\cdot A_j.
$$

> The unit coordinate vectors $E_1,\dots,E_n$ form the standard orthonormal set in $V_n$.

## 12.11 Bases

### 12.11.1 Definition

**Definition.** A set $S=\{A_1,\dots,A_k\}$ in $V_n$ is called a **basis** for $V_n$ if $S$ spans every vector in $V_n$ uniquely. If, in addition, $S$ is orthogonal, it is called an **orthogonal basis**.

Thus a basis is a linearly independent set which spans the whole space. The unit coordinate vectors $E_1,\dots,E_n$ form the **standard basis**; it is also an orthogonal basis.

### 12.11.2 Fundamental Properties of Bases

**Theorem 12.10.** In a given vector space $V_n$, bases have the following properties:
- **(a)** Every basis contains exactly $n$ vectors.
- **(b)** Any set of linearly independent vectors is a subset of some basis.
- **(c)** Any set of $n$ linearly independent vectors is a basis.

### 12.11.3 Proof Sketch

**Part (a) — Equal cardinality.** Let $S$ and $T$ be two bases with $k$ and $r$ vectors respectively. Since $T\subseteq L(S)=V_n$ and $T$ has $r$ vectors, Theorem 12.8 implies $r\le k$ (otherwise $T$ would be dependent). Interchanging roles gives $k\le r$. Hence $k=r$. Since $\{E_1,\dots,E_n\}$ is one basis, every basis has $n$ elements.

**Part (b) — Extension to a basis.** Let $S$ be independent. If $L(S)=V_n$, done. Otherwise pick $X\notin L(S)$ and form $S'=S\cup\{X\}$. If $S'$ were dependent, a nontrivial relation $\sum c_iA_i+c_{k+1}X=O$ would force $c_{k+1}\neq0$ (since $S$ is independent), yielding $X\in L(S)$, a contradiction. Thus $S'$ remains independent. Repeating finitely many times produces a basis (the process must stop, otherwise $n+1$ independent vectors would exist, contradicting Theorem 12.8).

**Part (c) — $n$ independent vectors form a basis.** Let $S$ be any independent set of $n$ vectors. By (b), $S\subseteq B$ for some basis $B$. By (a), $B$ has exactly $n$ elements, so $S=B$.

> Properties (a)–(c) justify calling $n$ the **dimension** of $V_n$.

## 12.12 The Complex Vector Space $V_n(\mathbb{C})$

### 12.12.1 Definition

Replacing real scalars by complex scalars in the definition of $V_n$ yields the **complex vector space** $V_n(\mathbb{C})$. Equality, addition, and scalar multiplication are defined componentwise exactly as in the real case.

Since complex numbers satisfy the same field properties as real numbers, all theorems about $V_n$ that use only field properties remain valid for $V_n(\mathbb{C})$.

### 12.12.2 The Complex Dot Product

For $V_n(\mathbb{C})$ the ordinary dot product must be modified to preserve positivity, because a sum of squares of complex numbers can be negative.

**Definition.** For $A=(a_1,\dots,a_n)$ and $B=(b_1,\dots,b_n)$ in $V_n(\mathbb{C})$,
$$
\boxed{A\cdot B=\sum_{k=1}^{n}a_k\,\overline{b}_k}
$$
where $\overline{b}_k$ is the complex conjugate of $b_k$.

> When the components are real, $\overline{b}_k=b_k$ and this agrees with the real definition.

**Theorem 12.11.** For all vectors $A,B,C$ in $V_n(\mathbb{C})$ and all complex scalars $c$:
- **(a)** $A\cdot B=\overline{B\cdot A}$
- **(b)** $A\cdot(B+C)=A\cdot B+A\cdot C$
- **(c)** $c(A\cdot B)=(cA)\cdot B=A\cdot(\overline{c}B)$
- **(d)** $A\cdot A>0$ if $A\neq O$
- **(e)** $A\cdot A=0$ if $A=O$

> Note the conjugations in (a) and (c) when factors are interchanged or scalars are moved across the dot.

### 12.12.3 Norms, Cauchy–Schwarz, and Orthogonality

The Cauchy–Schwarz inequality takes the same form:
$$
|A\cdot B|^2\le(A\cdot A)(B\cdot B).
$$
The **norm** is defined by $\|A\|=(A\cdot A)^{1/2}$, and the fundamental norm properties (Theorem 12.4) and the **triangle inequality** remain valid without change.

**Orthogonality** is defined exactly as before: $A\perp B$ means $A\cdot B=0$. The Pythagorean identity $\|A+B\|^2=\|A\|^2+\|B\|^2$ holds for orthogonal vectors in $V_n(\mathbb{C})$.

### 12.12.4 Span, Independence, and Basis

The concepts of linear span, linear independence, linear dependence, and basis are defined for $V_n(\mathbb{C})$ exactly as in the real case. Theorems 12.7 through 12.10 and their proofs are all valid without change.

> Complex vector spaces arise naturally in linear differential equations and quantum mechanics.

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

# 15. Linear Spaces

## 15.1 Introduction

- Throughout calculus we encounter objects that can be **added** and **multiplied by real numbers**:
  - Real numbers themselves
  - Real-valued functions
  - Complex numbers
  - Infinite series
  - Vectors in $n$-space
  - Vector-valued functions
- This chapter introduces the general concept of a **linear space** (or **vector space**) that unifies all these examples.
- A linear space is a set of elements with two operations (addition and scalar multiplication) satisfying certain axioms.

## 15.2 The Definition of a Linear Space

Let $V$ be a nonempty set of objects called **elements**. $V$ is a **linear space** if it satisfies the following ten axioms.

### 15.2.1 Closure Axioms

| Axiom | Statement |
|-------|-----------|
| **1. Closure under addition** | For every $x,y\in V$, there is a unique $x+y\in V$ |
| **2. Closure under multiplication by real numbers** | For every $x\in V$ and real $a$, there is $ax\in V$ |

### 15.2.2 Axioms for Addition

| Axiom | Statement |
|-------|-----------|
| **3. Commutative law** | $x+y=y+x$ for all $x,y\in V$ |
| **4. Associative law** | $(x+y)+z=x+(y+z)$ for all $x,y,z\in V$ |
| **5. Existence of zero element** | $\exists\,O\in V$ such that $x+O=x$ for all $x\in V$ |
| **6. Existence of negatives** | For every $x\in V$, $(-1)x$ satisfies $x+(-1)x=O$ |

### 15.2.3 Axioms for Multiplication by Numbers

| Axiom | Statement |
|-------|-----------|
| **7. Associative law** | $a(bx)=(ab)x$ for all $x\in V$ and real $a,b$ |
| **8. Distributive law for addition in $V$** | $a(x+y)=ax+ay$ for all $x,y\in V$ and real $a$ |
| **9. Distributive law for addition of numbers** | $(a+b)x=ax+bx$ for all $x\in V$ and real $a,b$ |
| **10. Existence of identity** | $1x=x$ for all $x\in V$ |

### 15.2.4 Terminology

- **Real linear space**: scalars are real numbers.
- **Complex linear space**: scalars are complex numbers (Axioms 2, 7–10 use complex numbers).
- Also called **linear vector space** or simply **vector space**.
- The multipliers are called **scalars**.
- Unless specified otherwise, "linear space" may refer to either real or complex.

## 15.3 Examples of Linear Spaces

### 15.3.1 Basic Number Spaces

**Example 1 — Real numbers:**
- $V=\mathbb{R}$, with ordinary addition and multiplication.

**Example 2 — Complex numbers:**
- $V=\mathbb{C}$, with ordinary complex addition and multiplication by **real** scalars.
- This is a **real** linear space (scalars are real, even though elements are complex).

**Example 3 — $n$-space:**
- $V=V_n$, the vector space of all $n$-tuples of real numbers, with component-wise operations.

**Example 4 — Orthogonal complement:**
- $V=$ set of all vectors in $V_n$ orthogonal to a given nonzero vector $N$.
- $n=2$: a line through $O$ with normal $N$.
- $n=3$: a plane through $O$ with normal $N$.

### 15.3.2 Function Spaces

The following are called **function spaces**. Addition and scalar multiplication are defined pointwise:
$$(f+g)(x)=f(x)+g(x),\qquad(af)(x)=af(x).$$
The zero element is the function identically zero.

| Example | Set $V$ | Notes |
|---------|---------|-------|
| **5** | All functions on a given interval | |
| **6** | All polynomials | |
| **7** | Polynomials of degree $\le n$ (fixed $n$) | Zero polynomial included. Degree $=n$ alone is **not** a linear space (closure fails) |
| **8** | Continuous functions on $[a,b]$ | Denoted $C(a,b)$ |
| **9** | Differentiable functions at a point | |
| **10** | Integrable functions on an interval | |
| **11** | Functions with $f(1)=0$ | The value $0$ is essential; replacing with $c\neq0$ violates closure |
| **12** | Solutions of $y''+ay'+by=0$ | Homogeneous linear ODE. Nonhomogeneous case fails closure |

> These examples show how the linear space concept unifies algebra, geometry, and analysis. A theorem proved from the axioms applies to **all** concrete examples at once.


## 15.4 Elementary Consequences of the Axioms

### 15.4.1 Uniqueness Theorems

**Theorem 15.1 — Uniqueness of the zero element.**
- In any linear space there is **one and only one** zero element.

**Proof sketch:** Suppose $O_1$ and $O_2$ are both zero. Then $O_1+O_2=O_1$ (taking $x=O_1$, $O=O_2$) and $O_2+O_1=O_2$ (taking $x=O_2$, $O=O_1$). By commutativity, $O_1=O_2$.

**Theorem 15.2 — Uniqueness of negative elements.**
- Every element $x$ has exactly one negative $y$ such that $x+y=O$.

**Proof sketch:** Suppose $y_1$ and $y_2$ are both negatives of $x$. Then:
$$
y_2+(x+y_1)=y_2+O=y_2,\qquad (y_2+x)+y_1=O+y_1=y_1.
$$
By associativity, $y_1=y_2$. The unique negative is $(-1)x$.

> **Notation:** The negative of $x$ is $-x$. The difference $y-x$ means $y+(-x)$.

### 15.4.2 Theorem 15.3 — Basic Algebraic Properties

In any linear space, for arbitrary elements $x,y$ and scalars $a,b$:

| Property | Statement |
|----------|-----------|
| **(a)** | $0x=O$ |
| **(b)** | $aO=O$ |
| **(c)** | $(-a)x=-(ax)=a(-x)$ |
| **(d)** | If $ax=O$, then either $a=0$ or $x=O$ |
| **(e)** | If $ax=ay$ and $a\neq0$, then $x=y$ |
| **(f)** | If $ax=bx$ and $x\neq O$, then $a=b$ |
| **(g)** | $-(x+y)=(-x)+(-y)=-x-y$ |
| **(h)** | $\underbrace{x+x+\cdots+x}_{n\text{ times}}=nx$ |

**Proof of (a):** Let $z=0x$. Then $z+z=0x+0x=(0+0)x=0x=z$. Adding $-z$ gives $z=O$.

**Proof of (b):** Let $z=aO$. Then $z+z=aO+aO=a(O+O)=aO=z$. Hence $z=O$.

**Proof of (c):** Let $z=(-a)x$. Then $z+ax=(-a+a)x=0x=O$, so $z=-(ax)$. Similarly $a(-x)=-(ax)$.


## 15.5 Subspaces of a Linear Space

### 15.5.1 Definition

- Let $V$ be a linear space and $S$ a nonempty subset of $V$.
- If $S$ is itself a linear space under the same operations, $S$ is called a **subspace** of $V$.

### 15.5.2 Theorem 15.4 — Subspace Criterion

Let $S$ be a nonempty subset of a linear space $V$. Then $S$ is a subspace **if and only if** $S$ satisfies the **closure axioms** (Axioms 1 and 2).

**Proof sketch:**
- If $S$ is a subspace, it satisfies all axioms, hence closure.
- Conversely, suppose $S$ satisfies closure. Axioms 3, 4, 7–10 hold automatically in $S$ because they hold in $V$.
- Need to verify Axioms 5 and 6:
  - For any $x\in S$: by closure, $0x\in S$. But $0x=O$, so $O\in S$.
  - Also $(-1)x\in S$, and $x+(-1)x=O$, so negatives exist in $S$.

### 15.5.3 Linear Combinations and Linear Span

- A **finite linear combination** of elements of $S$:
  $$
  x=\sum_{i=1}^k c_i x_i,\qquad x_i\in S,\ c_i\text{ scalars}.
  $$
- The set of all finite linear combinations of elements of $S$ satisfies the closure axioms, hence is a subspace.
- This subspace is called the **subspace spanned by $S$**, or the **linear span** of $S$, denoted $L(S)$.
- If $S$ is empty, define $L(S)=\{O\}$.

### 15.5.4 Examples

- $V_2$ is spanned by $\{\boldsymbol{i},\boldsymbol{j}\}$, also by $\{\boldsymbol{i},\boldsymbol{j},\boldsymbol{i}+\boldsymbol{j}\}$, also by $\{O,\boldsymbol{i},-\boldsymbol{i},\boldsymbol{j},-\boldsymbol{j},\boldsymbol{i}+\boldsymbol{j}\}$.
- Polynomials of degree $\le n$ are spanned by $\{1,t,t^2,\dots,t^n\}$.
- All polynomials are spanned by $\{1,t,t^2,\dots\}$ (infinite set).

### 15.5.5 Toward Bases and Dimension

- Which spaces can be spanned by a **finite** set?
- What is the **smallest** number of elements needed?
- To answer these, we introduce: **dependence, independence, bases, and dimension**.
- These concepts extend the ideas from Chapter 12 ($V_n$) to general linear spaces.


## 15.6 Dependent and Independent Sets in a Linear Space

### 15.6.1 Definition

- A set $S$ in a linear space $V$ is **dependent** if there exist distinct $x_1,\dots,x_k\in S$ and scalars $c_1,\dots,c_k$, not all zero, such that:
  $$
  \sum_{i=1}^k c_i x_i = O.
  $$
- $S$ is **independent** if it is not dependent; equivalently:
  $$
  \sum_{i=1}^k c_i x_i = O \quad\Longrightarrow\quad c_1=c_2=\cdots=c_k=0.
  $$
- The definition applies to **infinite sets** as well as finite sets.

### 15.6.2 Elementary Examples

| Example | Statement |
|---------|-----------|
| **1** | If $T\subseteq S$ and $T$ is dependent, then $S$ is dependent. (Equivalently: every subset of an independent set is independent.) |
| **2** | If one element is a scalar multiple of another, $S$ is dependent. |
| **3** | If $O\in S$, then $S$ is dependent. |
| **4** | The empty set is independent. |

### 15.6.3 Examples in Function Spaces

**Example 5:** $u_1(t)=\cos^2 t$, $u_2(t)=\sin^2 t$, $u_3(t)=1$.
- Since $u_1+u_2-u_3=O$, these three functions are dependent.

**Example 6:** $u_k(t)=t^k$ ($k=0,1,2,\dots$).
- The set $\{u_0,u_1,u_2,\dots\}$ is **independent**.
- Proof: $\sum_{k=0}^n c_k t^k=0$ for all $t$ implies each $c_k=0$ (evaluate at $t=0$, differentiate repeatedly).
  (Equation 15.1)

**Example 7:** Exponential functions $u_k(x)=e^{a_k x}$ with distinct $a_k$.
- **Independent.** Proof by induction on $n$:
  1. Assume $\sum_{k=1}^n c_k e^{a_k x}=0$. (Equation 15.2)
  2. Let $a_M$ be the largest $a_k$. Multiply by $e^{-a_M x}$:
     $$
     \sum_{k=1}^n c_k e^{(a_k-a_M)x}=0.
     $$
     (Equation 15.3)
  3. As $x\to+\infty$, terms with $k\neq M$ tend to 0, so $c_M=0$.
  4. Apply induction hypothesis to remaining $n-1$ terms.

### 15.6.4 Theorem 15.5 — Dependence in Spanned Subspaces

Let $S$ be an independent set of $k$ elements in $V$, and let $L(S)$ be its span. Then **every set of $k+1$ elements in $L(S)$ is dependent**.

**Proof:**
- When $V=V_n$, this is Theorem 12.8.
- The proof of Theorem 12.8 uses only the fact that $V_n$ is a linear space, not any special property of $V_n$.
- Hence the same proof is valid for **any** linear space $V$.

## 15.7 Bases and Dimension

### 15.7.1 Finite Basis and Dimension

**Definition.** A finite set $S$ in a linear space $V$ is a **finite basis** for $V$ if $S$ is **independent** and **spans** $V$.

| Term | Condition |
|------|-----------|
| **Finite-dimensional** | $V$ has a finite basis, or $V=\{O\}$ |
| **Infinite-dimensional** | $V$ has no finite basis |

- By convention, $\dim\{O\}=0$.

**Theorem 15.6 (Uniqueness of basis size).** Let $V$ be finite-dimensional. Then **every finite basis for $V$ has the same number of elements**.

**Proof sketch:**
- Let bases $S$ ($k$ elements) and $T$ ($m$ elements).
- $S$ independent and spans $V$ $\Rightarrow$ every set of $k+1$ elements in $V$ is dependent (Theorem 15.5).
- $T$ is independent with $m$ elements $\Rightarrow m\le k$.
- Interchange roles $\Rightarrow k\le m$.
- Hence $k=m$.

**Definition.** If $V$ has a basis of $n$ elements, $n$ is the **dimension** of $V$, written $n=\dim V$.

### 15.7.2 Examples

| Space | Dimension | Basis |
|-------|-----------|-------|
| $V_n$ | $n$ | $n$ unit coordinate vectors |
| Polynomials of degree $\le n$ | $n+1$ | $\{1,t,t^2,\dots,t^n\}$ |
| Solutions of $y''-2y'-3y=0$ | $2$ | $\{e^{-x},e^{3x}\}$ |
| All polynomials $p(t)$ | **Infinite** | $\{1,t,t^2,\dots\}$ spans, but no finite set spans |

### 15.7.3 Theorem 15.7 — Properties of Bases

Let $V$ be finite-dimensional with $\dim V=n$.

**(a) Extension.** Any independent set in $V$ is a subset of some basis for $V$.

**(b) Criterion.** Any set of $n$ independent elements in $V$ is a basis for $V$.

**Proof sketch:** Identical to parts (b) and (c) of Theorem 12.10.

### 15.7.4 Ordered Basis and Components

Let $(e_1,\dots,e_n)$ be an **ordered basis** (elements taken in a given order).

- Every $x\in V$ has a unique representation:
  $$
  x=\sum_{i=1}^n c_i e_i. \tag{15.4}
  $$
- The $n$-tuple $(c_1,\dots,c_n)$ is **uniquely determined** by $x$.
  - Proof of uniqueness: If $x=\sum d_i e_i$, then $\sum(c_i-d_i)e_i=O$. Independence implies $c_i=d_i$ for all $i$.
- $(c_1,\dots,c_n)$ are called the **components of $x$ relative to the ordered basis** $(e_1,\dots,e_n)$.

## 15.8 Inner Products, Euclidean Spaces, and Norms

### 15.8.1 Inner Product — Axiomatic Definition

In $V_n$, lengths and angles were defined via the dot product. We now generalize this to arbitrary linear spaces.

Recall the dot product in $V_n$:
$$
x\cdot y = \sum_{i=1}^n x_i y_i. \tag{15.5}
$$

**Definition (Real inner product).** A real linear space $V$ has an **inner product** if for each pair $x,y\in V$ there is a unique real number $(x,y)$ satisfying:

| Axiom | Property | Name |
|-------|----------|------|
| (1) | $(x,y)=(y,x)$ | Symmetry |
| (2) | $(x,y+z)=(x,y)+(x,z)$ | Additivity |
| (3) | $c(x,y)=(cx,y)$ | Homogeneity |
| (4) | $(x,x)>0$ if $x\neq O$ | Positivity |

- Note: Taking $c=0$ in (3) gives $(O,y)=0$ for all $y$.

A real linear space with an inner product is called a **real Euclidean space**.

**Complex inner product.** In a complex space, (1) is replaced by:
$$
(x,y)=\overline{(y,x)}. \tag{1'}
$$
- Then $(x,cy)=\bar c(x,y)$.
- Such a space is called a **complex Euclidean space** (or **unitary space**).
- The theorems below apply to both real and complex cases.

### 15.8.2 Examples of Inner Products

**Example 1:** In $V_n$, $(x,y)=x\cdot y$ (the usual dot product).

**Example 2:** In $V_2$, define $(x,y)=2x_1y_1+x_1y_2+x_2y_1+x_2y_2$.
- This is a valid inner product, showing a space may admit **more than one** inner product.

**Example 3:** In $C(a,b)$ (continuous real-valued functions on $[a,b]$):
$$
(f,g)=\int_a^b f(t)g(t)\,dt.
$$
- Analogous to (15.5): function values play the role of components, integration replaces summation.

**Example 4 (Weighted):** In $C(a,b)$ with a fixed positive function $w$:
$$
(f,g)=\int_a^b w(t)f(t)g(t)\,dt.
$$
- $w$ is called a **weight function**; Example 3 has $w(t)\equiv 1$.

**Example 5:** In the space of all real polynomials:
$$
(f,g)=\int_0^\infty e^{-t}f(t)g(t)\,dt.
$$
- The exponential factor ensures convergence for all polynomials.

### 15.8.3 Theorem 15.8 — Cauchy–Schwarz Inequality

In any Euclidean space $V$,
$$
|(x,y)|^2 \le (x,x)(y,y) \quad\text{for all }x,y\in V.
$$

- **Equality holds iff $x$ and $y$ are dependent** (i.e., one is a scalar multiple of the other).

**Proof sketch:**
- The proof for $V_n$ (Theorem 12.3) used only the axioms of the dot product (Theorem 12.2), not the specific formula.
- Hence the same proof is valid in **any** Euclidean space.
- In the complex case, one obtains $(x,y)(y,x)\le(x,x)(y,y)$, which is the same inequality since $(x,y)(y,x)=(x,y)\overline{(x,y)}=|(x,y)|^2$.

**Example.** In $C(a,b)$ with $(f,g)=\int_a^b f(t)g(t)\,dt$, the inequality becomes:
$$
\left(\int_a^b f(t)g(t)\,dt\right)^2 \le \left(\int_a^b f^2(t)\,dt\right)\left(\int_a^b g^2(t)\,dt\right).
$$

### 15.8.4 Norm

**Definition.** In a Euclidean space $V$, the **norm** of $x$ is
$$
\|x\| = (x,x)^{1/2}.
$$

In terms of norms, the Cauchy–Schwarz inequality becomes:
$$
|(x,y)| \le \|x\|\,\|y\|.
$$

- The norm depends on the choice of inner product (analogous to choice of scale/unit).

**Theorem 15.9 (Properties of norms).** In any Euclidean space, for all $x,y$ and scalars $c$:

| Property | Statement | Name |
|----------|-----------|------|
| (a) | $\|x\|=0$ iff $x=O$ | Definiteness |
| (b) | $\|x\|>0$ if $x\neq O$ | Positivity |
| (c) | $\|cx\|=|c|\,\|x\|$ | Homogeneity |
| (d) | $\|x+y\|\le\|x\|+\|y\|$ | Triangle inequality |

- Equality in (d) holds if $x=O$, $y=O$, or $y=cx$ with $c>0$.

**Proof sketch:**
- (a)–(c) follow directly from inner-product axioms.
- (d): Expand $\|x+y\|^2=(x+y,x+y)=\|x\|^2+\|y\|^2+(x,y)+\overline{(x,y)}$. By Cauchy–Schwarz, $|(x,y)|\le\|x\|\,\|y\|$, so:
  $$
  \|x+y\|^2 \le \|x\|^2+\|y\|^2+2\|x\|\,\|y\| = (\|x\|+\|y\|)^2.
  $$
- When $y=cx$ ($c>0$): $\|x+y\|=\|x+cx\|=(1+c)\|x\|=\|x\|+\|cx\|=\|x\|+\|y\|$.

### 15.8.5 Angle in a Real Euclidean Space

**Definition.** The **angle** $\theta$ ($0\le\theta\le\pi$) between nonzero $x$ and $y$ is defined by:
$$
\cos\theta = \frac{(x,y)}{\|x\|\,\|y\|}. \tag{15.6}
$$

- The Cauchy–Schwarz inequality guarantees the quotient lies in $[-1,1]$, so $\theta$ is uniquely determined.

## 15.9 Orthogonality in a Euclidean Space

### 15.9.1 Orthogonal and Orthonormal Sets

**Definition.** In a Euclidean space $V$:

| Term | Condition |
|------|-----------|
| **Orthogonal** | $(x,y)=0$ |
| **Orthogonal set** | $(x,y)=0$ for every pair of distinct $x,y\in S$ |
| **Orthonormal set** | Orthogonal set with $\|x\|=1$ for all $x\in S$ |

- The zero element is orthogonal to every element, and is the **only** element orthogonal to itself.

**Theorem 15.10 (Orthogonality implies independence).** In a Euclidean space $V$, every orthogonal set of **nonzero** elements is **independent**.

- In particular, in an $n$-dimensional Euclidean space, every orthogonal set of $n$ nonzero elements is a **basis**.

**Proof sketch:**
- Suppose $\sum_{i=1}^k c_i x_i=O$ with $x_i\in S$.
- Take inner product with $x_1$: $c_1(x_1,x_1)=0$.
- Since $x_1\neq O$, $(x_1,x_1)\neq 0$, so $c_1=0$.
- Repeat for each $x_j$ $\Rightarrow$ all $c_j=0$.
- If $|S|=n=\dim V$, then $S$ is a basis by Theorem 15.7(b).

### 15.9.2 Example — Trigonometric Functions in $C(0,2\pi)$

In $C(0,2\pi)$ with $(f,g)=\int_0^{2\pi}f(x)g(x)\,dx$, let
$$
u_0(x)=1,\quad u_{2n-1}(x)=\cos nx,\quad u_{2n}(x)=\sin nx\quad (n\ge 1).
$$

- **Orthogonality:** $\int_0^{2\pi} u_n(x)u_m(x)\,dx=0$ for $m\neq n$.
- **Norms:**
  - $\|u_0\|=\sqrt{2\pi}$
  - $\|u_{2n-1}\|=\|u_{2n}\|=\sqrt{\pi}$ for $n\ge 1$
- **Orthonormal set** $\{\varphi_0,\varphi_1,\varphi_2,\dots\}$ obtained by dividing each $u_n$ by its norm:
  $$
  \varphi_0(x)=\frac{1}{\sqrt{2\pi}},\quad \varphi_{2n-1}(x)=\frac{\cos nx}{\sqrt{\pi}},\quad \varphi_{2n}(x)=\frac{\sin nx}{\sqrt{\pi}}.
  $$

### 15.9.3 Components Relative to an Orthogonal Basis

**Theorem 15.11.** Let $V$ be finite-dimensional with $\dim V=n$, and let $S=\{e_1,\dots,e_n\}$ be an orthogonal basis. If $x=\sum_{i=1}^n c_i e_i$, then:
$$
c_j = \frac{(x,e_j)}{(e_j,e_j)} \quad\text{for }j=1,2,\dots,n. \tag{15.8}
$$

- In particular, if $S$ is **orthonormal**:
  $$
  c_j=(x,e_j). \tag{15.9}
  $$

- Equation (15.7) then becomes:
  $$
  x=\sum_{i=1}^n (x,e_i)e_i. \tag{15.10}
  $$

**Proof sketch:** Take inner product of $x=\sum c_i e_i$ with $e_j$; orthogonality kills all terms except $i=j$.

### 15.9.4 Parseval’s Formula

**Theorem 15.12.** Let $\{e_1,\dots,e_n\}$ be an orthonormal basis for $V$. Then for all $x,y\in V$:
$$
(x,y)=\sum_{i=1}^n (x,e_i)\overline{(y,e_i)}. \tag{15.11}
$$

- When $x=y$:
  $$
  \|x\|^2=\sum_{i=1}^n |(x,e_i)|^2. \tag{15.12}
  $$

**Proof sketch:** Expand $x$ and $y$ using (15.10) and apply linearity of the inner product; orthonormality yields the sum.

## 15.10 The Gram–Schmidt Process

### 15.10.1 Orthogonalization Theorem

Every finite-dimensional Euclidean space has an orthogonal basis. This follows from:

**Theorem 15.13 (Orthogonalization theorem).** Let $x_1,x_2,\dots$ be a finite or infinite sequence in a Euclidean space $V$, and let $L(x_1,\dots,x_k)$ denote the subspace spanned by the first $k$ elements. Then there exists a sequence $y_1,y_2,\dots$ in $V$ such that for each $k$:

| Property | Statement |
|----------|-----------|
| (a) | $y_k$ is orthogonal to every element in $L(y_1,\dots,y_{k-1})$ |
| (b) | $L(y_1,\dots,y_k)=L(x_1,\dots,x_k)$ |
| (c) | The sequence is **unique up to scalar factors**: if $y'_1,y'_2,\dots$ also satisfies (a) and (b), then $y'_k=c_k y_k$ for some scalar $c_k$ |

**Proof sketch (Gram–Schmidt construction):**
- Start with $y_1=x_1$.
- Assume $y_1,\dots,y_r$ constructed satisfying (a) and (b).
- Define:
  $$
  y_{r+1}=x_{r+1}-\sum_{i=1}^r a_i y_i, \tag{15.13}
  $$
  where $a_i$ are chosen to make $y_{r+1}$ orthogonal to each $y_j$ ($j\le r$).
- Taking inner product with $y_j$:
  $$
  (y_{r+1},y_j)=(x_{r+1},y_j)-a_j(y_j,y_j).
  $$
- If $y_j\neq O$, set:
  $$
  a_j=\frac{(x_{r+1},y_j)}{(y_j,y_j)}. \tag{15.14}
  $$
- If $y_j=O$, choose $a_j=0$.
- Then $y_{r+1}$ is orthogonal to $L(y_1,\dots,y_r)$, proving (a).
- Since $x_{r+1}$ and each $y_i$ lie in $L(x_1,\dots,x_{r+1})$, and conversely $x_{r+1}$ is a linear combination of $y_1,\dots,y_{r+1}$, we get (b).
- Uniqueness (c): any alternative $y'_{r+1}$ must lie in $L(y_1,\dots,y_{r+1})$ and be orthogonal to $L(y_1,\dots,y_r)$, hence is a scalar multiple of $y_{r+1}$.

### 15.10.2 The Gram–Schmidt Formulas

For an independent set $\{x_1,\dots,x_k\}$, the corresponding orthogonal set $\{y_1,\dots,y_k\}$ is given by:
$$
y_1=x_1,\qquad y_{r+1}=x_{r+1}-\sum_{i=1}^r\frac{(x_{r+1},y_i)}{(y_i,y_i)}y_i \quad (r=1,2,\dots,k-1). \tag{15.15}
$$

- If some $y_{r+1}=O$, then $x_{r+1}$ is a linear combination of $x_1,\dots,x_r$, so the original set is dependent.
- If $\{x_1,\dots,x_k\}$ is independent, then all $y_i$ are nonzero, and $\{y_1,\dots,y_k\}$ is an orthogonal basis for the same subspace.
- An **orthonormal basis** is obtained by normalizing: $e_i=y_i/\|y_i\|$.

**Corollary (Theorem 15.14).** Every finite-dimensional Euclidean space has an **orthonormal basis**.

**Projection.** For $y\neq O$, the element $\frac{(x,y)}{(y,y)}y$ is called the **projection of $x$ along $y$**. The Gram–Schmidt process constructs $y_{r+1}$ by subtracting from $x_{r+1}$ its projection along each earlier $y_i$.

### 15.10.3 Example in $V_4$

Find an orthonormal basis for the span of:
$$
x_1=(1,-1,1,-1),\quad x_2=(5,1,1,1),\quad x_3=(-3,-3,1,-3).
$$

**Step 1:** $y_1=x_1=(1,-1,1,-1)$.

**Step 2:**
$$
y_2=x_2-\frac{(x_2,y_1)}{(y_1,y_1)}y_1 = x_2-y_1 = (4,2,0,2).
$$

**Step 3:**
$$
y_3=x_3-\frac{(x_3,y_1)}{(y_1,y_1)}y_1-\frac{(x_3,y_2)}{(y_2,y_2)}y_2 = x_3-y_1+y_2 = (0,0,0,0).
$$

- Since $y_3=O$, the vectors $x_1,x_2,x_3$ are dependent; $y_1,y_2$ are independent, so the subspace has dimension 2.
- **Orthonormal basis:**
  $$
  e_1=\frac{y_1}{\|y_1\|}=\frac{1}{2}(1,-1,1,-1),\qquad e_2=\frac{y_2}{\|y_2\|}=\frac{1}{\sqrt{6}}(2,1,0,1).
  $$

### 15.10.4 Example — Legendre Polynomials

In the space of all real polynomials with inner product $(x,y)=\int_{-1}^1 x(t)y(t)\,dt$, apply Gram–Schmidt to $x_n(t)=t^n$:

| $n$ | $y_n(t)$ | $P_n(t)$ (standard Legendre) |
|-----|----------|------------------------------|
| 0 | $1$ | $1$ |
| 1 | $t$ | $t$ |
| 2 | $t^2-\frac{1}{3}$ | $\frac{1}{2}(3t^2-1)$ |
| 3 | $t^3-\frac{3}{5}t$ | $\frac{1}{2}(5t^3-3t)$ |
| 4 | $t^4-\frac{6}{7}t^2+\frac{3}{35}$ | $\frac{1}{8}(35t^4-30t^2+3)$ |
| 5 | $t^5-\frac{10}{9}t^3+\frac{5}{21}t$ | $\frac{1}{8}(63t^5-70t^3+15t)$ |

**Rodrigues formula:**
$$
y_n(t)=\frac{n!}{(2n)!}\frac{d^n}{dt^n}(t^2-1)^n,\qquad P_n(t)=\frac{1}{2^n n!}\frac{d^n}{dt^n}(t^2-1)^n.
$$

- The **normalized Legendre polynomials** are $\varphi_n=y_n/\|y_n\|$.

## 15.11 Orthogonal Complements and Projections

### 15.11.1 The Approximation Problem

Let $V$ be a Euclidean space and $S$ a finite-dimensional subspace. Given $x\in V$, find $s\in S$ minimizing the distance $\|x-s\|$.

- If $x\in S$, then $s=x$.
- Geometrically (in $V_3$ with $S$ a plane through the origin), the nearest point is obtained by dropping a perpendicular from $x$ to $S$.

### 15.11.2 Orthogonal Complement

**Definition.** An element in $V$ is **orthogonal to $S$** if it is orthogonal to every element of $S$. The set of all such elements is denoted $S^\perp$ (read "$S$ perpendicular").

- $S^\perp$ is a subspace of $V$, whether or not $S$ is.
- If $S$ is a subspace, $S^\perp$ is called the **orthogonal complement** of $S$.
- Example: If $S$ is a plane through the origin in $V_3$, then $S^\perp$ is the line through the origin perpendicular to $S$.

### 15.11.3 Theorem 15.15 — Orthogonal Decomposition

Let $V$ be a Euclidean space and $S$ a finite-dimensional subspace. Then **every** $x\in V$ can be represented **uniquely** as:
$$
x = s + s^\perp, \quad\text{where }s\in S\text{ and }s^\perp\in S^\perp. \tag{15.16}
$$

Moreover, the **Pythagorean formula** holds:
$$
\|x\|^2 = \|s\|^2 + \|s^\perp\|^2. \tag{15.17}
$$

**Proof sketch:**
- Since $S$ is finite-dimensional, it has an orthonormal basis $\{e_1,\dots,e_n\}$.
- Define:
  $$
  s = \sum_{i=1}^n (x,e_i)e_i, \qquad s^\perp = x - s. \tag{15.18}
  $$
- $s$ is a linear combination of basis elements, so $s\in S$.
- For any basis element $e_j$:
  $$
  (s^\perp,e_j) = (x,e_j) - (s,e_j) = (x,e_j) - (x,e_j) = 0.
  $$
  Hence $s^\perp$ is orthogonal to every element of $S$, so $s^\perp\in S^\perp$.
- **Uniqueness:** Suppose $x=t+t^\perp$ is another decomposition. Then $s-t=t^\perp-s^\perp$. The left side is in $S$, the right side in $S^\perp$. Thus $s-t$ is orthogonal to itself, so $s-t=O$ and $s^\perp=t^\perp$.
- **Pythagorean formula:**
  $$
  \|x\|^2=(x,x)=(s+s^\perp,s+s^\perp)=(s,s)+(s^\perp,s^\perp)=\|s\|^2+\|s^\perp\|^2.
  $$

### 15.11.4 Projection onto a Subspace

**Definition.** Let $S$ be a finite-dimensional subspace with orthonormal basis $\{e_1,\dots,e_n\}$. For $x\in V$, the element
$$
s = \sum_{i=1}^n (x,e_i)e_i
$$
is called the **projection of $x$ on the subspace $S$**.

- This projection is the unique element in $S$ that solves the approximation problem (minimizing $\|x-s\|$).
- The proof of this optimality property follows from the orthogonal decomposition theorem.

## 15.12 Best Approximation in a Finite-Dimensional Subspace

### 15.12.1 Theorem 15.16 — Approximation Theorem

Let $S$ be a finite-dimensional subspace of a Euclidean space $V$, and let $x\in V$. Then the **projection** $s$ of $x$ on $S$ is nearer to $x$ than any other element of $S$:
$$
\|x-s\| \le \|x-t\| \quad\text{for all }t\in S,
$$
with equality if and only if $t=s$.

**Proof:**
- By Theorem 15.15, $x=s+s^\perp$ with $s\in S$ and $s^\perp\in S^\perp$.
- For any $t\in S$: $x-t=(x-s)+(s-t)$.
- Since $s-t\in S$ and $x-s=s^\perp\in S^\perp$, this is an orthogonal decomposition.
- By the Pythagorean formula:
  $$
  \|x-t\|^2 = \|x-s\|^2 + \|s-t\|^2 \ge \|x-s\|^2.
  $$
- Equality holds iff $\|s-t\|=0$, i.e., $t=s$.

### 15.12.2 Example — Trigonometric Polynomial Approximation

Let $V=C(0,2\pi)$ with $(f,g)=\int_0^{2\pi}f(x)g(x)\,dx$, and let $S$ be the subspace spanned by the orthonormal set:
$$
\varphi_0(x)=\frac{1}{\sqrt{2\pi}},\quad \varphi_{2k-1}(x)=\frac{\cos kx}{\sqrt{\pi}},\quad \varphi_{2k}(x)=\frac{\sin kx}{\sqrt{\pi}} \quad (k\ge 1). \tag{15.20}
$$

- The $2n+1$ elements $\varphi_0,\dots,\varphi_{2n}$ span a subspace of dimension $2n+1$.
- Elements of $S$ are called **trigonometric polynomials**.
- For $f\in C(0,2\pi)$, the projection of $f$ on $S$ is:
  $$
  f_n = \sum_{k=0}^{2n}(f,\varphi_k)\varphi_k, \quad\text{where }(f,\varphi_k)=\int_0^{2\pi}f(x)\varphi_k(x)\,dx. \tag{15.21}
  $$
- The numbers $(f,\varphi_k)$ are the **Fourier coefficients** of $f$.
- Rewriting (15.21) in standard form:
  $$
  f_n(x) = \tfrac{1}{2}a_0 + \sum_{k=1}^n\bigl(a_k\cos kx + b_k\sin kx\bigr), \tag{15.22}
  $$
  where
  $$
  a_k = \frac{1}{\pi}\int_0^{2\pi}f(x)\cos kx\,dx, \qquad b_k = \frac{1}{\pi}\int_0^{2\pi}f(x)\sin kx\,dx.
  $$

### 15.12.3 Example — Polynomial Approximation with Legendre Polynomials

Let $V=C(-1,1)$ with $(f,g)=\int_{-1}^1 f(x)g(x)\,dx$, and let $S$ be spanned by the normalized Legendre polynomials $\varphi_0,\dots,\varphi_n$ (dimension $n+1$).

- The projection of $f$ on $S$ is $f_n=\sum_{k=0}^n(f,\varphi_k)\varphi_k$.
- This is the polynomial of degree $\le n$ minimizing $\|f-f_n\|$.

**Example:** $f(x)=\sin\pi x$.
- $(f,\varphi_0)=0$ (odd function).
- $(f,\varphi_1)=\int_{-1}^1\sqrt{\frac{3}{2}}t\sin\pi t\,dt=\sqrt{\frac{3}{2}}\frac{2}{\pi}$.
- The best linear approximation:
  $$
  f_1(t) = \sqrt{\frac{3}{2}}\frac{2}{\pi}\,\varphi_1(t) = \frac{3}{\pi}t.
  $$
- Since $(f,\varphi_2)=0$, this is also the best **quadratic** approximation.

# 16. Linear Transformations and Matrices

## 16.1 Linear Transformations

### 16.1.1 Definition

Let $V$ and $W$ be linear spaces over the same scalars. A function $T:V\to W$ is a **linear transformation** if:

| Property | Formula | Name |
|----------|---------|------|
| (a) | $T(x+y)=T(x)+T(y)$ | Additivity |
| (b) | $T(cx)=cT(x)$ | Homogeneity |

- Combined form: $T(ax+by)=aT(x)+bT(y)$ for all $x,y\in V$ and scalars $a,b$.
- Generalization by induction:
  $$
  T\Bigl(\sum_{i=1}^n a_i x_i\Bigr)=\sum_{i=1}^n a_i T(x_i).
  $$

**Terminology:**
- $T(x)$ is the **image** of $x$ under $T$.
- $T$ **maps** $x$ onto $T(x)$.
- For $A\subseteq V$, $T(A)=\{T(x):x\in A\}$ is the **image of $A$ under $T$**.
- $T(V)$ is the **range** of $T$.

### 16.1.2 Examples

**Example 1 — Identity transformation.** $T:V\to V$, $T(x)=x$ for all $x$. Denoted by $I$ or $I_V$.

**Example 2 — Zero transformation.** $T:V\to V$, $T(x)=O$ for all $x$. Denoted by $O$.

**Example 3 — Multiplication by a fixed scalar $c$.** $T:V\to V$, $T(x)=cx$.
- $c=1$: identity; $c=0$: zero transformation.

**Example 4 — Linear equations.** $T:V_n\to V_m$ defined by:
$$
y_i=\sum_{k=1}^n a_{ik}x_k \quad (i=1,2,\dots,m).
$$
Given $mn$ scalars $a_{ik}$, this maps $x=(x_1,\dots,x_n)$ to $y=(y_1,\dots,y_m)$.

**Example 5 — Inner product with a fixed element.** Let $V$ be a real Euclidean space and $z\in V$ fixed. Define $T:V\to\mathbb{R}$ by $T(x)=(x,z)$.

**Example 6 — Projection on a subspace.** Let $S$ be a finite-dimensional subspace of a Euclidean space $V$. Define $T:V\to S$ by $T(x)=$ projection of $x$ on $S$.

**Example 7 — Differentiation operator.** Let $V$ be the space of all real functions differentiable on $(a,b)$. Define $D:V\to W$ by $D(f)=f'$, where $W$ is the space of all derivatives.

**Example 8 — Integration operator.** Let $V=C[a,b]$. Define $T:V\to V$ by:
$$
g(x)=T(f)(x)=\int_a^x f(t)\,dt \quad\text{for }a\le x\le b.
$$

## 16.2 Null Space and Range

Throughout this section, $T:V\to W$ denotes a linear transformation.

### 16.2.1 The Range

**Theorem 16.1.** The range $T(V)$ is a **subspace** of $W$. Moreover, $T$ maps the zero element of $V$ onto the zero element of $W$.

**Proof sketch:**
- If $T(x),T(y)\in T(V)$, then $T(x)+T(y)=T(x+y)\in T(V)$.
- If $c$ is a scalar, $cT(x)=T(cx)\in T(V)$.
- Taking $c=0$ in $T(cx)=cT(x)$ gives $T(O)=O$.

### 16.2.2 The Null Space (Kernel)

**Definition.** The set of all elements in $V$ that $T$ maps onto $O$ is called the **null space** of $T$, denoted $N(T)$:
$$
N(T)=\{x\in V \mid T(x)=O\}.
$$
The null space is also called the **kernel** of $T$.

**Theorem 16.2.** The null space $N(T)$ is a **subspace** of $V$.

**Proof:** If $x,y\in N(T)$, then $T(x+y)=T(x)+T(y)=O+O=O$ and $T(cx)=cT(x)=cO=O$.

### 16.2.3 Null Spaces of the Examples in 16.1

| Example | Transformation | Null Space $N(T)$ |
|---------|---------------|-------------------|
| 1 | Identity $I$ | $\{O\}$ |
| 2 | Zero $O$ | $V$ |
| 3 | Multiplication by $c$ | $\{O\}$ if $c\neq 0$; $V$ if $c=0$ |
| 4 | Linear equations $y_i=\sum_k a_{ik}x_k$ | Solution space of $\sum_k a_{ik}x_k=0$ ($i=1,\dots,m$) |
| 5 | Inner product $(x,z)$ | $\{x\in V:(x,z)=0\}$ (orthogonal complement of $\operatorname{span}\{z\}$) |
| 6 | Projection on $S$ | $S^\perp$ (orthogonal complement of $S$) |
| 7 | Differentiation $D(f)=f'$ | All constant functions on $(a,b)$ |
| 8 | Integration $T(f)(x)=\int_a^x f(t)\,dt$ | $\{0\}$ (only the zero function) |

## 16.3 Nullity and Rank

### 16.3.1 Definitions

Let $T:V\to W$ be a linear transformation with $V$ finite-dimensional.

| Term | Symbol | Definition |
|------|--------|------------|
| **Nullity** of $T$ | $\operatorname{nullity}(T)$ | $\dim N(T)$ |
| **Rank** of $T$ | $\operatorname{rank}(T)$ | $\dim T(V)$ |

Since $N(T)$ is a subspace of the finite-dimensional space $V$, the nullity is well defined. The next theorem shows the rank is also finite.

### 16.3.2 Theorem 16.3 — Nullity Plus Rank

If $V$ is finite-dimensional, then $T(V)$ is finite-dimensional and:
$$
\dim N(T) + \dim T(V) = \dim V. \tag{16.1}
$$

In words: **nullity + rank = dimension of the domain**.

**Proof sketch:**
- Let $n=\dim V$ and let $\{e_1,\dots,e_k\}$ be a basis for $N(T)$, so $k=\dim N(T)$.
- By Theorem 15.7(a), extend to a basis of $V$:
  $$
  e_1,\dots,e_k,e_{k+1},\dots,e_{k+r}, \tag{16.2}
  $$
  where $k+r=n$.
- **Claim:** The $r$ elements $T(e_{k+1}),\dots,T(e_{k+r})$ form a basis for $T(V)$. \tag{16.3}

**Spanning:** If $y\in T(V)$, then $y=T(x)$ for some $x=\sum_{i=1}^{k+r}c_i e_i$. Since $T(e_1)=\dots=T(e_k)=O$,
$$
y=T(x)=\sum_{i=k+1}^{k+r}c_i T(e_i).
$$

**Independence:** Suppose $\sum_{i=k+1}^{k+r}c_i T(e_i)=O$. Then $T(\sum_{i=k+1}^{k+r}c_i e_i)=O$, so $\sum_{i=k+1}^{k+r}c_i e_i\in N(T)$. Hence it equals $\sum_{i=1}^k c_i e_i$ for some scalars. But the full set (16.2) is independent, so all $c_i=0$.

- Therefore $\dim T(V)=r$, and $k+r=n$ gives (16.1).

> **Note:** If $V$ is infinite-dimensional, then at least one of $N(T)$ or $T(V)$ is infinite-dimensional.

## 16.4 Algebraic Operations on Linear Transformations

### 16.4.1 Addition and Scalar Multiplication

Let $S,T:V\to W$ and let $c$ be a scalar. Define:
$$
(S+T)(x)=S(x)+T(x),\qquad (cT)(x)=cT(x) \quad\text{for all }x\in V. \tag{16.4}
$$

- The set of all linear transformations from $V$ to $W$ is denoted $\mathscr{L}(V,W)$.

**Theorem 16.4.** $\mathscr{L}(V,W)$ is a **linear space** under the operations (16.4).

- The zero element is the zero transformation $O$.
- The negative of $T$ is $(-1)T$.
- All ten linear-space axioms are satisfied.

### 16.4.2 Composition (Multiplication)

Let $T:U\to V$ and $S:V\to W$. The **composition** $ST:U\to W$ is defined by:
$$
(ST)(x)=S[T(x)] \quad\text{for all }x\in U.
$$

- Order matters: first apply $T$, then $S$.
- Composition is **not** commutative in general.

**Theorem 16.5 (Associative law).** If $T:U\to V$, $S:V\to W$, and $R:W\to X$, then:
$$
R(ST)=(RS)T.
$$

**Proof:** For each $x\in U$:
$$
[R(ST)](x)=R[(ST)(x)]=R[S[T(x)]]=[(RS)T](x).
$$

**Powers.** For $T:V\to V$:
$$
T^0=I,\qquad T^n=TT^{n-1}\quad (n\ge 1).
$$
- The associative law implies the **law of exponents**: $T^m T^n=T^{m+n}$ for all nonnegative integers $m,n$.

**Theorem 16.6 (Linearity of composition).** If $T:U\to V$ and $S:V\to W$ are linear, then $ST:U\to W$ is linear.

**Proof:** $(ST)(ax+by)=S[T(ax+by)]=S[aT(x)+bT(y)]=aS[T(x)]+bS[T(y)]=a(ST)(x)+b(ST)(y)$.

**Theorem 16.7 (Distributive laws).** Let $S,T\in\mathscr{L}(V,W)$ and $c$ a scalar.

**(a)** For any $R$ with values in $V$:
$$
(S+T)R=SR+TR,\qquad (cS)R=c(SR).
$$

**(b)** For any linear $R:W\to U$:
$$
R(S+T)=RS+RT,\qquad R(cS)=c(RS).
$$

## 16.5 Inverses

### 16.5.1 Left and Right Inverses

**Definition.** Let $T:V\to W$.

| Type | Condition | Formula |
|------|-----------|---------|
| **Left inverse** $S$ | $S:T(V)\to V$ and $S[T(x)]=x$ for all $x\in V$ | $ST=I_V$ |
| **Right inverse** $R$ | $R:T(V)\to V$ and $T[R(y)]=y$ for all $y\in T(V)$ | $TR=I_{T(V)}$ |

**Example (no left inverse, two right inverses).** Let $V=\{1,2\}$, $W=\{0\}$, and $T(1)=T(2)=0$.
- Two right inverses: $R(0)=1$ and $R'(0)=2$.
- No left inverse exists, since $S[T(1)]=S(0)=1$ and $S[T(2)]=S(0)=2$ would require $1=2$.

- Every function has **at least one right inverse** (choose any preimage for each $y\in T(V)$).
- Right inverses need not be unique (when some $y$ has multiple preimages).

### 16.5.2 Theorem 16.8 — Uniqueness of the Left Inverse

A function $T:V\to W$ has **at most one** left inverse. If $T$ has a left inverse $S$, then $S$ is also a right inverse.

**Proof sketch:**
- **Uniqueness:** Suppose $S$ and $S'$ are left inverses. For any $y\in T(V)$, write $y=T(x)$. Then $S(y)=S[T(x)]=x$ and $S'(y)=S'[T(x)]=x$, so $S(y)=S'(y)$.
- **Left implies right:** For $y\in T(V)$, write $y=T(x)$. Then $T[S(y)]=T[S[T(x)]]=T(x)=y$, so $S$ is a right inverse.

### 16.5.3 Theorem 16.9 — Existence of a Left Inverse

A function $T:V\to W$ has a left inverse **if and only if** $T$ is **one-to-one** on $V$; that is,
$$
x\neq y \quad\text{implies}\quad T(x)\neq T(y). \tag{16.5}
$$
Equivalently:
$$
T(x)=T(y) \quad\text{implies}\quad x=y. \tag{16.6}
$$

**Proof sketch:**
- ($\Rightarrow$) If $ST=I_V$ and $T(x)=T(y)$, apply $S$: $x=S[T(x)]=S[T(y)]=y$.
- ($\Leftarrow$) If $T$ is one-to-one, each $y\in T(V)$ has exactly one preimage $x$. Define $S(y)=x$ where $T(x)=y$. Then $S[T(x)]=x$, so $ST=I_V$.

### 16.5.4 Invertible Transformations

**Definition.** Let $T:V\to W$ be one-to-one. The **unique** left inverse of $T$ (which is also a right inverse) is denoted $T^{-1}$. We say $T$ is **invertible**, and call $T^{-1}$ the **inverse** of $T$.

- These results apply to arbitrary functions. The next sections specialize to linear transformations.

## 16.6 One-to-One Linear Transformations

### 16.6.1 Theorem 16.10 — Equivalent Conditions for One-to-One

Let $T:V\to W$ be a linear transformation. The following are **equivalent**:

**(a)** $T$ is one-to-one on $V$.

**(b)** $T$ is invertible and its inverse $T^{-1}:T(V)\to V$ is linear.

**(c)** $N(T)=\{O\}$; that is, $T(x)=O$ implies $x=O$.

**Proof sketch:**
- **(a)$\Rightarrow$(b):** Let $u,v\in T(V)$, so $u=T(x)$, $v=T(y)$. Then
  $$
  au+bv=aT(x)+bT(y)=T(ax+by).
  $$
  Applying $T^{-1}$: $T^{-1}(au+bv)=ax+by=aT^{-1}(u)+bT^{-1}(v)$, so $T^{-1}$ is linear.
- **(b)$\Rightarrow$(c):** If $T(x)=O$, apply $T^{-1}$: $x=T^{-1}(O)=O$.
- **(c)$\Rightarrow$(a):** If $T(u)=T(v)$, then $T(u-v)=O$, so $u-v=O$ by (c). Hence $u=v$.

### 16.6.2 Theorem 16.11 — Finite-Dimensional Characterizations

Let $T:V\to W$ be linear with $V$ finite-dimensional, $\dim V=n$. The following are **equivalent**:

**(a)** $T$ is one-to-one on $V$.

**(b)** $T$ preserves independence: if $e_1,\dots,e_p$ are independent in $V$, then $T(e_1),\dots,T(e_p)$ are independent in $T(V)$.

**(c)** $\dim T(V)=n$.

**(d)** If $\{e_1,\dots,e_n\}$ is a basis for $V$, then $\{T(e_1),\dots,T(e_n)\}$ is a basis for $T(V)$.

**Proof sketch:**
- **(a)$\Rightarrow$(b):** Suppose $\sum_{i=1}^p c_i T(e_i)=O$. By linearity, $T(\sum c_i e_i)=O$. By Theorem 16.10(c), $\sum c_i e_i=O$, so independence of $\{e_i\}$ gives $c_i=0$.
- **(b)$\Rightarrow$(c):** Take a basis $\{e_1,\dots,e_n\}$ of $V$. By (b), $\{T(e_i)\}$ are independent in $T(V)$, so $\dim T(V)\ge n$. By Theorem 16.3 (nullity + rank), $\dim T(V)\le n$. Hence $\dim T(V)=n$.
- **(c)$\Rightarrow$(d):** $\{T(e_i)\}$ spans $T(V)$ and there are $n=\dim T(V)$ of them, so they form a basis.
- **(d)$\Rightarrow$(a):** If $T(x)=O$, write $x=\sum c_i e_i$. Then $T(x)=\sum c_i T(e_i)=O$. By (d), $\{T(e_i)\}$ is independent, so all $c_i=0$ and $x=O$. Thus $N(T)=\{O\}$, and Theorem 16.10 gives (a).

## 16.7 Linear Transformations with Prescribed Values

### 16.7.1 Theorem 16.12 — Existence and Uniqueness

Let $\{e_1,\dots,e_n\}$ be a basis for an $n$-dimensional linear space $V$, and let $u_1,\dots,u_n$ be arbitrary elements in a linear space $W$. Then there is **one and only one** linear transformation $T:V\to W$ such that:
$$
T(e_k)=u_k \quad\text{for }k=1,2,\dots,n. \tag{16.7}
$$

This $T$ acts on an arbitrary element $x=\sum_{k=1}^n x_k e_k$ by:
$$
T(x)=\sum_{k=1}^n x_k u_k. \tag{16.8}
$$

**Proof sketch:**
- **Existence:** Define $T$ by (16.8). Linearity follows directly from the formula. If $x=e_k$, all components are 0 except the $k$th, which is 1, so $T(e_k)=u_k$.
- **Uniqueness:** Suppose $T'$ also satisfies $T'(e_k)=u_k$. Then for any $x=\sum x_k e_k$:
  $$
  T'(x)=\sum_{k=1}^n x_k T'(e_k)=\sum_{k=1}^n x_k u_k=T(x).
  $$
  Hence $T'=T$.

> A linear transformation is **completely determined** by its values on a basis.

### 16.7.2 Example in $V_2$

Determine $T:V_2\to V_2$ such that:
$$
T(i)=i+j,\qquad T(j)=2i-j.
$$

**Solution:** For $x=x_1 i+x_2 j$:
$$
T(x)=x_1 T(i)+x_2 T(j)=x_1(i+j)+x_2(2i-j)=(x_1+2x_2)i+(x_1-x_2)j.
$$

