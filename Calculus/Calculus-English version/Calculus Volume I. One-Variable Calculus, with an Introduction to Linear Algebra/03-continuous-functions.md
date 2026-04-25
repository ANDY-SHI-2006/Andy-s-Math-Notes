[<- Previous: 2. Some Applications of Integration](02-some-applications-of-integration.md) | [Next: 4. Differential Calculus ->](04-differential-calculus.md)

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

[<- Previous: 2. Some Applications of Integration](02-some-applications-of-integration.md) | [Next: 4. Differential Calculus ->](04-differential-calculus.md)
