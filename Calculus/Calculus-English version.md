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


## 1.16 The Basic Properties of the Integral

### 1.16.1 Theorem 1.16 — Linearity

If $f$ and $g$ are integrable on $[a, b]$, then so is $c_1 f + c_2 g$ for all real $c_1, c_2$, and:

$$
\int_a^b \bigl[c_1 f(x) + c_2 g(x)\bigr] \, dx = c_1 \int_a^b f(x) \, dx + c_2 \int_a^b g(x) \, dx.
$$

By induction, for any finite sum:

$$
\int_a^b \sum_{k=1}^{n} c_k f_k(x) \, dx = \sum_{k=1}^{n} c_k \int_a^b f_k(x) \, dx.
$$

### 1.16.2 Theorem 1.17 — Additivity with Respect to the Interval

If two of the following three integrals exist, the third also exists, and:

$$
\int_a^b f(x) \, dx + \int_b^c f(x) \, dx = \int_a^c f(x) \, dx.
$$

> **Note:** If $f$ is monotonic on $[a, b]$ and on $[b, c]$, then all three integrals exist.

### 1.16.3 Theorem 1.18 — Invariance under Translation

If $f$ is integrable on $[a, b]$, then for every real $c$:

$$
\int_a^b f(x) \, dx = \int_{a+c}^{b+c} f(x - c) \, dx.
$$

### 1.16.4 Theorem 1.19 — Expansion or Contraction

If $f$ is integrable on $[a, b]$, then for every real $k \neq 0$:

$$
\int_a^b f(x) \, dx = \frac{1}{k} \int_{ka}^{kb} f\!\left(\frac{x}{k}\right) dx.
$$

> **Note:** When $k = -1$, this is called the **reflection property**.

### 1.16.5 Theorem 1.20 — Comparison Theorem

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

### 2.2.2 Theorem 2.1 — Area Formula

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

### 2.3.1 Example 1 — Simple Region

Compute the area of the region $S$ between $f(x) = x(x-2)$ and $g(x) = x/2$ over $[0, 2]$.

Since $f \le g$ on $[0, 2]$, by Theorem 2.1:

$$
a(S) = \int_0^2 \bigl[g(x) - f(x)\bigr]\,dx = \int_0^2 \left(\frac{5}{2}x - x^2\right) dx = \frac{5}{2}\cdot\frac{2^2}{2} - \frac{2^3}{3} = \frac{7}{3}.
$$

### 2.3.2 Example 2 — Splitting the Interval

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

### 2.3.3 Example 3 — Area of a Circular Disk

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

### 2.3.4 Example 4 — Similarity Transformation

Let $f$ be nonnegative and integrable on $[a, b]$, with ordinate set $S$. Under a similarity transformation with factor $k > 0$, the set $kS$ is the ordinate set of $g(x) = kf(x/k)$ on $[ka, kb]$.

By Theorem 1.19:

$$
a(kS) = \int_{ka}^{kb} kf(x/k)\,dx = k^2 \int_a^b f(x)\,dx = k^2 \, a(S).
$$

Thus similarity with factor $k$ multiplies area by $k^2$.

### 2.3.5 Example 5 — Calculating $\int_0^a x^{1/2}\,dx$

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

### 2.3.6 Theorem 2.2 — General Power Formula

For $a > 0$, $b > 0$, and $n$ a positive integer:

$$
\int_a^b x^{1/n}\,dx = \frac{b^{1+1/n} - a^{1+1/n}}{1 + 1/n}. \tag{2.2}
$$


## 2.4 The Trigonometric Functions

### 2.4.1 Introduction

Before further applications of integration, we briefly discuss the six trigonometric functions — sine, cosine, tangent, cotangent, secant, cosecant — and their inverses. In calculus their importance lies not in triangle relations but in their **properties as functions**, especially **periodicity**.

A function $f$ is **periodic** with period $p \neq 0$ if $f(x+p) = f(x)$ for all $x$ in its domain. The sine and cosine functions are periodic with period $2\pi$, where $\pi$ is the area of a unit circular disk.

### 2.4.2 Fundamental Properties of Sine and Cosine

We take the following four properties as axioms; all other properties can be deduced from them.

| Property | Statement |
|----------|-----------|
| **1. Domain** | $\sin x$ and $\cos x$ are defined for all real $x$. |
| **2. Special values** | $\cos 0 = \sin\frac{\pi}{2} = 1$, $\cos\pi = -1$. |
| **3. Cosine of a difference** | $\cos(y-x) = \cos y \cos x + \sin y \sin x$ for all $x, y$. |
| **4. Fundamental inequalities** | For $0 < x < \frac{\pi}{2}$: $0 < \cos x < \dfrac{\sin x}{x} < \dfrac{1}{\cos x}$. |

### 2.4.3 Theorem 2.3 — Deduced Properties

If $\sin$ and $\cos$ satisfy properties 1–4, then they also satisfy:

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

### 2.5.2 Theorem 2.4 — Approximation Inequalities

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

### 2.5.4 Theorem 2.5 — Basic Integrals

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

### 2.5.6 Example 1 — General Interval Formulas

For any real $a, b$:

$$
\int_a^b \cos x\,dx = \sin b - \sin a = \sin x\,\Big|_a^b, \qquad
\int_a^b \sin x\,dx = -(\cos b - \cos a) = -\cos x\,\Big|_a^b.
$$

### 2.5.7 Example 2 — Scaling the Argument

For $c \neq 0$:

$$
\int_a^b \cos cx\,dx = \frac{1}{c}(\sin cb - \sin ca), \qquad
\int_a^b \sin cx\,dx = -\frac{1}{c}(\cos cb - \cos ca).
$$

### 2.5.8 Example 3 — Powers of Sine and Cosine

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

### 2.7.4 Example — Figure-Eight Curve

- Cartesian equation: $(x^2 + y^2)^3 = y^2$
- Conversion: using $x^2 + y^2 = r^2$ and $y = r \sin \theta$:
  $$
  r^6 = r^2 \sin^2 \theta \implies r^4 = \sin^2 \theta \implies r = \sqrt{|\sin \theta|}
  $$
- Sketching via polar equation is easier than from Cartesian form alone.
  - In $0 \le \theta \le \pi/2$: $\sin \theta$ increases from $0$ to $1$, so $r$ increases from $0$ to $1$.
  - Key points: $\theta = \pi/6, \pi/4, \pi/3$.
  - The rest follows from symmetry and periodicity of $|\sin \theta|$.

### 2.7.5 Another Example — Circle

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

### 2.8.3 Theorem 2.6 — Area Formula

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

### 2.8.4 Example — Area of the Figure-Eight Curve

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

### 2.9.5 Theorem 2.7 — General Cavalieri Solid

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

### 2.9.6 Example — Solid of Revolution (Disk Method)

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
- **Constant force**: $W = c \cdot (b - a)$ (force × displacement).

**Units:**

| System | Force | Distance | Work |
|--------|-------|----------|------|
| British | pounds (lb) | feet (ft) | foot-pounds (ft-lb) |
| cgs | dynes | centimeters (cm) | dyne-centimeters (ergs) |
| mks | newtons (N) | meters (m) | newton-meters (joules) |

- $1$ newton $= 10^5$ dynes; $1$ joule $= 10^7$ ergs.

### 2.10.2 Example — Stone Thrown Upward

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

### 2.10.5 Theorem 2.8 — Work as Integral

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

### 2.10.6 Example — Work to Stretch a Spring (Hooke's Law)

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

### 2.11.2 Definition — Average Value on an Interval

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
- For $f$ with both signs: $A(x)$ = (area above $x$-axis) − (area below $x$-axis).

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
- The indefinite integral "smooths out" jumps — $A(x)$ is always continuous (proved in next chapter).


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
- **J. B. J. Fourier** (1758–1830) on heat theory forced mathematicians to examine continuity more carefully.
- A satisfactory definition was first formulated by **Augustin-Louis Cauchy** (1789–1857) in 1821, using the limit concept.

> "Continuity: Quality or state of being continuous. Continuous: Having continuity of parts."
> — Trying to learn continuity from a dictionary alone is like trying to learn Chinese with only a Chinese dictionary.


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

**Example 1 — Constant function:**
- $f(x) = c$ for all $x$. Then $\displaystyle\lim_{x \to p} c = c$.

**Example 2 — Identity function:**
- $f(x) = x$. Then $\displaystyle\lim_{x \to p} x = p$.

**Example 3 — Greatest-integer function:**
- $f(x) = [x]$ at integer $p$:
  $$
  \lim_{x \to p^-} f(x) = p - 1, \qquad \lim_{x \to p^+} f(x) = p
  $$
  Left and right limits differ $\implies$ limit at $p$ does **not exist**.

**Example 4 — $f(x) = 1/x^2$ at $x = 0$:**
- $f$ takes arbitrarily large values near 0.
- No real number $A$ can be the limit (violates (3.3) for any neighborhood).

**Example 5 — Removable discontinuity:**
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

### 3.3.1 Definition — Continuity at a Point

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

**Example 1 — Constant function:**
- $f(x) = c$. Then $\lim_{x \to p} c = c = f(p)$ for every $p$.
- **Constant functions are continuous everywhere.**

**Example 2 — Identity function:**
- $f(x) = x$. Then $\lim_{x \to p} x = p = f(p)$ for every $p$.
- **The identity function is continuous everywhere.**

**Example 3 — Greatest-integer function:**
- $f(x) = [x]$ is continuous at every non-integer point.
- At integers $p$: discontinuous (limit does not exist; jump discontinuity).
- However, $f$ is **continuous from the right** at each integer (right-hand limit equals $f(p)$).

**Example 4 — Infinite discontinuity:**
- $f(x) = 1/x^2$ for $x \neq 0$, $f(0) = 0$.
- Discontinuous at 0; **infinite discontinuity** (function takes arbitrarily large values near 0).

**Example 5 — Removable discontinuity:**
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

### 3.4.1 Theorem 3.1 — Basic Limit Rules

Let $\lim_{x \to p} f(x) = A$ and $\lim_{x \to p} g(x) = B$. Then:

| Rule | Formula |
|------|---------|
| **(i) Sum** | $\lim_{x \to p} [f(x) + g(x)] = A + B$ |
| **(ii) Difference** | $\lim_{x \to p} [f(x) - g(x)] = A - B$ |
| **(iii) Product** | $\lim_{x \to p} [f(x) \cdot g(x)] = A \cdot B$ |
| **(iv) Quotient** | $\lim_{x \to p} f(x)/g(x) = A/B$ \quad (if $B \neq 0$) |

- Special case of (iii): $\lim_{x \to p} [c \cdot g(x)] = c \cdot B$ (constant multiple).
- Proof is in Section 3.5.

### 3.4.2 Theorem 3.2 — Continuity of Combinations

Let $f$ and $g$ be continuous at $p$. Then:
- $f + g$, $f - g$, $f \cdot g$ are continuous at $p$.
- $f/g$ is continuous at $p$ (if $g(p) \neq 0$).

**Proof:** Apply Theorem 3.1 with $A = f(p)$ and $B = g(p)$.

### 3.4.3 Example 1 — Continuity of Polynomials

- $f(x) = x$ is continuous $\implies x^2 = x \cdot x$ is continuous (by product rule).
- By induction: $x^n$ is continuous for all positive integers $n$.
- $cx^n$ is continuous; sums of continuous functions are continuous.
- **Every polynomial** $p(x) = \sum_{k=0}^n c_k x^k$ is continuous at all points.

### 3.4.4 Example 2 — Continuity of Rational Functions

- A **rational function** $r(x) = p(x)/q(x)$ (where $p, q$ are polynomials).
- Continuous wherever $q(x) \neq 0$.
- Example: $r(x) = 1/x$ is continuous everywhere except at $x = 0$.

### 3.4.5 Theorem 3.3 — Squeezing Principle

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

### 3.4.6 Theorem 3.4 — Continuity of Indefinite Integrals

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

### 3.4.7 Example 3 — Continuity of Sine and Cosine

- $\sin x = \int_0^x \cos t \, dt$ $\implies$ sine is continuous everywhere (by Theorem 3.4).
- $\cos x = 1 - \int_0^x \sin t \, dt$ $\implies$ cosine is continuous everywhere.

### 3.4.8 Example 4 — The Limit $\lim_{x \to 0} \frac{\sin x}{x} = 1$

From Section 2.5, for $0 < |x| < \pi/2$:

$$
0 < \cos x < \frac{\sin x}{x} < \frac{1}{\cos x}
$$

- As $x \to 0$: $\cos x \to 1$ (cosine is continuous at 0), so $1/\cos x \to 1$.
- By squeezing principle: $\displaystyle\lim_{x \to 0} \frac{\sin x}{x} = 1$.
- (Equation 3.6)
- Defining $f(x) = (\sin x)/x$ for $x \neq 0$ and $f(0) = 1$ makes $f$ continuous everywhere.

### 3.4.9 Example 5 — Continuity of $x^r$ for Rational $r > 0$

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

### 3.5.2 Proof of (i) and (ii) — Sum and Difference

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

### 3.5.3 Proof of (iii) — Product

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

### 3.5.4 Proof of (iv) — Quotient

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

### 3.6.3 Theorem 3.5 — Continuity of Composites

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
- $f(x) = \sin(x^2)$ — composition of two everywhere-continuous functions.
- **$f$ is continuous everywhere.**

**Example 2:**
- $f(x) = \sqrt{1 - x^2} = u[v(x)]$, where $u(x) = \sqrt{x}$, $v(x) = 1 - x^2$.
- $v$ continuous everywhere; $u$ continuous for $x \ge 0$.
- **$f$ is continuous where $v(x) \ge 0$, i.e., $x^2 \le 1$.**

## 3.7 Bolzano's Theorem for Continuous Functions

### 3.7.1 Introduction

- This section discusses special properties of continuous functions that appear geometrically obvious but require rigorous proof.
- Most proofs rely on the **least-upper-bound axiom** for the real number system.
- **Bernard Bolzano** (1781–1848), a Catholic priest, was among the first to recognize that "obvious" statements about continuous functions need proof.
- His work was published posthumously in 1850 in *Paradoxien des Unendlichen*; this theorem first appeared in 1817.

### 3.7.2 Theorem 3.6 — Bolzano's Theorem

Let $f$ be continuous at each point of a closed interval $[a, b]$ and assume $f(a)$ and $f(b)$ have **opposite signs**. Then there exists at least one $c \in (a, b)$ such that:

$$
f(c) = 0
$$

- **Geometric meaning**: A continuous curve crossing from below to above the $x$-axis must intersect the axis somewhere in between.

### 3.7.3 Theorem 3.7 — Sign-Preserving Property

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

### 3.8.1 Theorem 3.8 — Intermediate-Value Theorem

Let $f$ be continuous at each point of a closed interval $[a, b]$. Choose $x_1 < x_2$ in $[a, b]$ with $f(x_1) \neq f(x_2)$. Then $f$ takes on **every value between $f(x_1)$ and $f(x_2)$** somewhere in $(x_1, x_2)$.

**Proof:**
- Suppose $f(x_1) < f(x_2)$ and let $k$ be any value between them.
- Define $g(x) = f(x) - k$ on $[x_1, x_2]$.
- Then $g$ is continuous, $g(x_1) = f(x_1) - k < 0$, and $g(x_2) = f(x_2) - k > 0$.
- By Bolzano's theorem, $g(c) = 0$ for some $c \in (x_1, x_2)$.
- Hence $f(c) = k$.

> **Note:** In both Bolzano's theorem and the intermediate-value theorem, $f$ must be continuous at **every point** of $[a, b]$, including the endpoints. Figure 3.9 shows a function continuous everywhere in $[a, b]$ except at $a$; although $f(a) < 0$ and $f(b) > 0$, there is no $x$ with $f(x) = 0$.

### 3.8.2 Theorem 3.9 — Existence of $n$th Roots

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

### 3.9.5 Example — The $n$th-Root Function

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

### 3.10.2 Theorem 3.10 — Monotonicity and Continuity of Inverses

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

### 3.10.3 Example — Continuity of the $n$th-Root Function

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

### 3.12.2 Theorem 3.11 — Boundedness Theorem

Let $f$ be continuous on a closed interval $[a, b]$. Then $f$ is **bounded** on $[a, b]$; i.e., $\exists C \ge 0$ such that $|f(x)| \le C$ for all $x \in [a, b]$.

**Proof (by contradiction, successive bisection):**
1. Assume $f$ is unbounded on $[a, b]$.
2. Bisect $[a, b]$; $f$ must be unbounded on at least one half. Call it $[a_1, b_1]$.
3. Repeat: obtain a nested sequence $[a_n, b_n]$ of length $(b - a)/2^n$ on which $f$ is unbounded.
4. Let $A = \{a, a_1, a_2, \dots\}$ and $\alpha = \sup A$. Then $\alpha \in [a, b]$.
5. By continuity at $\alpha$: $\exists \delta > 0$ such that $|f(x) - f(\alpha)| < 1$ for $x \in (\alpha - \delta, \alpha + \delta)$.
   (Equation 3.25)
6. Hence $|f(x)| < 1 + |f(\alpha)|$ in this interval — $f$ is bounded here.
7. But $[a_n, b_n] \subset (\alpha - \delta, \alpha + \delta)$ for large $n$ (since $(b - a)/2^n < \delta$).
8. Contradiction: $f$ is bounded on $[a_n, b_n]$ yet was chosen to be unbounded there.

### 3.12.3 Supremum and Infimum of a Bounded Function

- If $f$ is bounded on $[a, b]$, define:
  $$
  \sup f = \sup\{f(x) \mid a \le x \le b\}, \qquad \inf f = \inf\{f(x) \mid a \le x \le b\}
  $$
- For any bounded function: $\inf f \le f(x) \le \sup f$ for all $x \in [a, b]$.

### 3.12.4 Theorem 3.12 — Extreme-Value Theorem

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

### 3.12.5 Consequence — Range of a Continuous Function

- If $f$ is continuous on $[a, b]$, then:
  - $\sup f$ is the **absolute maximum**.
  - $\inf f$ is the **absolute minimum**.
- By the intermediate-value theorem, the range of $f$ is the closed interval $[\inf f, \sup f]$.


## 3.13 The Small-Span Theorem for Continuous Functions (Uniform Continuity)

### 3.13.1 Definition — Span of a Function

- Let $M(f)$ and $m(f)$ denote the maximum and minimum values of $f$ on $[a, b]$.
- The **span** of $f$ on $[a, b]$:
  $$
  \text{span}(f) = M(f) - m(f)
  $$
- Some authors use **oscillation**; older texts use **saltus** (Latin for "leap").
- The span of $f$ on any subinterval cannot exceed the span on $[a, b]$.

### 3.13.2 Theorem 3.13 — Small-Span Theorem

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

### 3.14.1 Theorem 3.14 — Integrability of Continuous Functions

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

### 3.15.1 Theorem 3.15 — Mean-Value Theorem for Integrals

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

### 3.15.2 Theorem 3.16 — Weighted Mean-Value Theorem

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

### 4.2.2 Average Velocity — The Difference Quotient

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

### 4.5.1 Theorem 4.1 — Basic Rules

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
- This is the **point–slope form** using the derivative as the slope.

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

### 4.10.2 Theorem 4.3 — Vanishing of the Derivative at an Interior Extremum

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
- **Arithmetic–geometric mean inequality**: For $a,b\gt0$,
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

Hence the second term in (5.1) vanishes as $h\to 0$, and $A'(x)=f(x)$. ∎

## 5.2 The Zero-Derivative Theorem

- If $f$ is constant on an open interval $(a,b)$, then $f'(x)=0$ everywhere on $(a,b)$ — an immediate consequence of the definition of the derivative.
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
Put $x=c$: $A(c)=0$, so $k=-P(c)$. Hence $A(x)-P(x)=-P(c)$, which gives (5.2). ∎

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

Despite similar appearance, $\int f(x)\,dx$ and $\int_{a}^{b}f(x)\,dx$ are conceptually distinct — they originate from differentiation and integration respectively. The fundamental theorems connect them:

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

### 5.6.2 Examples — Indefinite Integrals

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
Thus the two integrals in (5.7) are equal. ∎

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

which is (5.10) since $G(c)=\int_{a}^{c}g(x)\,dx$ and $G(b)-G(c)=\int_{c}^{b}g(x)\,dx$. ∎

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
Hence $L(ab)=L(a)+L(b)$. ∎

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

### 6.7.2 Extension to Nonzero Values — The Function $L_{0}$

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

**Proof sketch.** For $0<x<1$, use $1-x\le1-u\le1$ on $[0,x]$ to bound the integrand $u^{n}/(1-u)$. For $x<0$, set $t=-x$ and observe the sign alternation. ∎

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
  as $h\to0$ (so $k\to0$). Thus $E'(x)=E(x)$. ∎

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

### 6.14.2 Integration — Basic Formulas

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

as $k\to0$. ∎

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

### 6.18.2 Case 1 — Distinct Linear Factors

If $g(x)=(x-x_{1})(x-x_{2})\cdots(x-x_{n})$, then:

$$
\frac{f(x)}{g(x)}=\frac{A_{1}}{x-x_{1}}+\cdots+\frac{A_{n}}{x-x_{n}}.
$$

**Example.** $\displaystyle\int\frac{2x^{2}+5x-1}{x^{3}+x^{2}-2x}\,dx$.
- $x^{3}+x^{2}-2x=x(x-1)(x+2)$.
- $A_{1}=\tfrac12$, $A_{2}=2$, $A_{3}=-\tfrac12$ (cover-up method).
- Result: $\tfrac12\log|x|+2\log|x-1|-\tfrac12\log|x+2|+C$.

### 6.18.3 Case 2 — Repeated Linear Factors

If $(x+a)^{p}$ occurs, include $p$ terms:

$$
\sum_{k=1}^{p}\frac{A_{k}}{(x+a)^{k}}.
$$

**Example.** $\displaystyle\int\frac{x^{2}+2x+3}{(x-1)(x+1)^{2}}\,dx$.
- Decompose as $\dfrac{A_{1}}{x-1}+\dfrac{A_{2}}{x+1}+\dfrac{A_{3}}{(x+1)^{2}}$.
- $A_{1}=\tfrac32$, $A_{3}=-1$ (cover-up); $A_{2}=-\tfrac12$ (substitute $x=0$ or differentiate).
- Result: $\tfrac32\log|x-1|-\tfrac12\log|x+1|+\dfrac{1}{x+1}+C$.

### 6.18.4 Case 3 — Distinct Irreducible Quadratics

**Example.** $\displaystyle\int\frac{3x^{2}+2x-2}{x^{3}-1}\,dx$.
- $x^{3}-1=(x-1)(x^{2}+x+1)$.
- Decompose: $\dfrac{1}{x-1}+\dfrac{2x+3}{x^{2}+x+1}$.
- Second term: split into $\dfrac{2x+1}{x^{2}+x+1}$ (log) and $\dfrac{2}{(x+\tfrac12)^{2}+\tfrac34}$ (arctan).
- Result: $\log|x-1|+\log(x^{2}+x+1)+\tfrac{4}{\sqrt3}\arctan\!\bigl(\tfrac{2x+1}{\sqrt3}\bigr)+C$.

### 6.18.5 Case 4 — Repeated Irreducible Quadratics

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

**Proof idea.** In each case both sides are polynomials of the same degree that agree in value and in derivatives up to the appropriate order at $a$; uniqueness (Theorem 7.1) forces equality. ∎

### 7.3.2 Substitution Property

**Theorem 7.3.** Let $g(x)=f(cx)$ with $c$ constant. Then:

$$
T_{n}g(x;a)=T_{n}f(cx;ca). \tag{7.6}
$$

In particular, when $a=0$: $T_{n}g(x)=T_{n}f(cx)$.

**Proof.** By the chain rule $g^{(k)}(x)=c^{k}f^{(k)}(cx)$; substitute into the Taylor formula. ∎

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

**Proof.** Set $h(x)=f(x)-P_{n}(x)=x^{n}g(x)$. Repeated differentiation shows $h$ and its first $n$ derivatives vanish at $0$; hence $f$ agrees with $P_{n}$ through order $n$. ∎

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

Integration by parts with $u=f^{(n+1)}(t)-f^{(n+1)}(a)$ and $v=-\dfrac{(x-t)^{n+1}}{n+1}$ yields (7.9) with $n$ replaced by $n+1$. ∎

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

**Proof idea.** Bound the integrand in the integral form of $E_{n}(x)$ and integrate. ∎

### 7.5.2 Example — Approximating $e$

For $f(x)=e^{x}$ at $a=0$ with $x=1$:

$$
e=\sum_{k=0}^{n}\frac{1}{k!}+E_{n}(1),\qquad\frac{1}{(n+1)!}\le E_{n}(1)<\frac{3}{(n+1)!}.
$$

Taking $n=12$ gives $2.718281826<e<2.718281833$, so $e\approx2.7182818$ (correct to 7 decimals).

### 7.5.3 Example — Irrationality of $e$

Multiplying the error bounds by $n!$:

$$
\frac{1}{n+1}\le n!\,e-\sum_{k=0}^{n}\frac{n!}{k!}<\frac{3}{n+1}\le\frac34\qquad(n\ge3).
$$

The sum is an integer. If $e$ were rational, $n!e$ would be an integer for large $n$, but the inequalities force the difference of two integers to be a positive number $\le\tfrac34$ — impossible. Hence $e$ is irrational.

### 7.5.4 Example — Approximating an Integral

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

## 7.9 L'Hôpital's Rule for the Indeterminate Form $0/0$

### 7.9.1 Motivation

For $\dfrac{f(x)}{g(x)}$ with $f(a)=g(a)=0$:

$$
\frac{f(x)}{g(x)}=\frac{f(x)-f(a)}{g(x)-g(a)}=\frac{\dfrac{f(x)-f(a)}{x-a}}{\dfrac{g(x)-g(a)}{x-a}}\;\longrightarrow\;\frac{f'(a)}{g'(a)}
$$

provided $f'(a), g'(a)$ exist and $g'(a)\neq 0$.

### 7.9.2 Theorem 7.9 — L'Hôpital's Rule ($0/0$)

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

## 7.10 The Symbols $+\infty$ and $-\infty$; Extension of L'Hôpital's Rule

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

### 7.10.2 Theorem 7.10 — L'Hôpital's Rule at Infinity ($0/0$)

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

### 7.12.1 Theorem 7.11 — Growth Hierarchy

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
