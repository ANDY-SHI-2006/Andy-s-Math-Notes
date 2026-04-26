[<- Previous: 2. Matrices](02-matrices.md) | [Next: 4. Linear Maps and Matrices ->](04-linear-maps-and-matrices.md)

# 3. Linear Mappings

## 3.1 Mappings

### 3.1.1 Definition

Let $S, S'$ be two sets. A **mapping** from $S$ to $S'$ is an association which to every element of $S$ associates an element of $S'$. Notation: $F: S \to S'$.

A **function** is a special type of mapping: a mapping from a set into a field $K$ (i.e. into $\mathbf{R}$, $\mathbf{C}$, or $K$).

**Terminology:**
- $T(u)$ or $Tu$: the **value** of $T$ at $u$, or the **image** of $u$ under $T$.
- **Image** of $T$: the set of all $T(u)$ for $u \in S$.
- **Image of $W$ under $T$**: for $W \subset S$, the set $\{T(w) \mid w \in W\}$, denoted $T(W)$.
- $x \mapsto F(x)$: denotes the image of $x$ under $F$.

**Example 1:** $f: \mathbf{R} \to \mathbf{R}$, $f(x) = x^2$. Image = $\{y \ge 0\}$.

**Example 2:** $g: [0, \infty) \to \mathbf{R}$, $g(x) = x^{1/2}$.

**Example 3:** $D: S \to S$, where $S$ is the set of infinitely differentiable functions on $(0, 1)$, and $Df = df/dt$.

**Example 4:** $\mathscr{I}: S \to S'$, where $S$ = continuous functions on $[0, 1]$, $S'$ = differentiable functions on $[0, 1]$, and:

$$
(\mathscr{I}f)(x) = \int_0^x f(t) \, dt.
$$

**Example 5:** $L: \mathbf{R}^3 \to \mathbf{R}$, $L(X) = A \cdot X$ where $A = (2, 3, -1)$. Then $L(1, 1, -1) = 6$.

**Example 6:** $F: \mathbf{R}^2 \to \mathbf{R}^2$, $F(x, y) = (2x, 2y)$. The image of the unit circle $x^2 + y^2 = 1$ is the circle of radius 2.

### 3.1.2 Operations on Mappings

Let $F, G: S \to V$ be mappings into a vector space $V$.
- **Sum:** $(F + G)(t) = F(t) + G(t)$
- **Scalar multiple:** $(cF)(t) = cF(t)$ for $c \in K$

These satisfy axioms VS 1–VS 8, so mappings form a vector space.

### 3.1.3 Coordinate Functions

Let $F: S \to K^n$ be a mapping. Then $F(t) = (f_1(t), \dots, f_n(t))$, where $f_i: S \to K$ are the **coordinate functions** of $F$.

If $K = \mathbf{R}$ and $S$ is an interval $J$, then $F: J \to \mathbf{R}^n$ is a **(parametric) curve** in $n$-space.

**Example 9:** $F: \mathbf{R} \to \mathbf{R}^3$, $F(t) = (2t, 10^t, t^3)$. Coordinate functions: $f_1(t) = 2t$, $f_2(t) = 10^t$, $f_3(t) = t^3$.

### 3.1.4 Composition of Mappings

Let $F: U \to V$ and $G: V \to W$. The **composite mapping** $G \circ F: U \to W$ is defined by:

$$
(G \circ F)(t) = G(F(t)).
$$

**Associativity:** For $F: U \to V$, $G: V \to W$, $H: W \to S$:

$$
H \circ (G \circ F) = (H \circ G) \circ F.
$$

**Proof:** Both sides evaluated at $u$ give $H(G(F(u)))$.

### 3.1.5 Injective, Surjective, Bijective

Let $f: S \to S'$ be a mapping.

| Property | Definition |
|----------|------------|
| **Injective** (one-to-one) | $f(x) = f(y) \implies x = y$ |
| **Surjective** (onto) | Image of $f$ = all of $S'$ |
| **Bijective** | Both injective and surjective |

**Example 10:** $f(x) = x^2$ from $\mathbf{R} \to \mathbf{R}$ is **not** injective ($f(1) = f(-1) = 1$) and **not** surjective (image is $[0, \infty)$).

However, $x \mapsto x^2$ from $\mathbf{R}^+ \to \mathbf{R}^+$ **is** bijective.

> **Important:** The domain and codomain must be specified to determine injectivity/surjectivity.

### 3.1.6 Identity Mapping

The **identity mapping** $I_S: S \to S$ is defined by $I_S(x) = x$ for all $x \in S$. It is both injective and surjective. Also denoted $\operatorname{id}_S$ or $\operatorname{id}$.

### 3.1.7 Inverse Mappings

$F: S \to S'$ has an **inverse** if there exists $G: S' \to S$ such that:

$$
G \circ F = I_S \quad \text{and} \quad F \circ G = I_{S'}.
$$

**Key result:** $f$ has an inverse **if and only if** $f$ is bijective.

**Proof:**
- ($\implies$) If $g$ is the inverse of $f$: injectivity follows from $x = g(f(x)) = g(f(y)) = y$; surjectivity follows from $f(g(z)) = z$.
- ($\impliedby$) If $f$ is bijective: for each $z \in S'$, there exists unique $x \in S$ with $f(x) = z$. Define $g(z) = x$. Then $f(g(z)) = z$ and $g(f(x)) = x$.

**Example 11:** $f: [0, \infty) \to [0, \infty)$, $f(x) = x^2$. Inverse: $g(x) = \sqrt{x}$.

**Example 12:** $f: \mathbf{R} \to \mathbf{R}_{>0}$, $f(x) = e^x$. Inverse: logarithm.

**Example 13 — Translation:** Let $u \in V$ be fixed. $T_u: V \to V$ defined by $T_u(v) = v + u$.
- $T_{u_1 + u_2} = T_{u_1} \circ T_{u_2}$
- Inverse of $T_u$ is $T_{-u}$

## 3.2 Linear Mappings

### 3.2.1 Definition

Let $V, V'$ be vector spaces over $K$. A **linear mapping** $F: V \to V'$ satisfies:

| Property | Statement |
|----------|-----------|
| **LM 1.** Additivity | $F(u + v) = F(u) + F(v)$ for all $u, v \in V$ |
| **LM 2.** Homogeneity | $F(cv) = cF(v)$ for all $c \in K$, $v \in V$ |

If we wish to specify $K$, we say $F$ is **$K$-linear**. Usually we simply say $F$ is **linear**.

**Basic property:** $L(O) = O$ for any linear map $L: V \to W$. If $F(O) \neq O$, then $F$ is not linear.

**General property:** For any $u_1, \dots, u_n \in V$ and $a_1, \dots, a_n \in K$:

$$
T(a_1 u_1 + \cdots + a_n u_n) = a_1 T(u_1) + \cdots + a_n T(u_n).
$$

### 3.2.2 Example 1 — Coordinate Map

Let $V$ be finite dimensional with basis $\{v_1, \dots, v_n\}$. Define $F: V \to K^n$ by:

$$
F(v) = (x_1, \dots, x_n) \quad \text{where } v = x_1 v_1 + \cdots + x_n v_n.
$$

Then $F$ is linear:
- $F(v + w) = X + Y = F(v) + F(w)$
- $F(cv) = cX = cF(v)$

### 3.2.3 Example 2 — Projection

$F: \mathbf{R}^3 \to \mathbf{R}^2$, $F(x, y, z) = (x, y)$. More generally, for $r < n$:

$$
F: K^n \to K^r, \quad F(x_1, \dots, x_n) = (x_1, \dots, x_r).
$$

### 3.2.4 Example 3 — Dot Product Map

Let $A \in K^n$. Define $L_A: K^n \to K$ by $L_A(X) = X \cdot A$. This is linear by properties SP 2 and SP 3 of the dot product.

More generally, for an $m \times n$ matrix $A$:

$$
L_A: K^n \to K^m, \quad L_A(X) = AX.
$$

### 3.2.5 Example 4 — Identity and Zero Maps

- **Identity mapping** $\operatorname{id}: V \to V$, $\operatorname{id}(u) = u$.
- **Zero mapping** $O: V \to V'$, $O(u) = O$ for all $u$.

### 3.2.6 Example 6 — Space of Linear Maps

Let $\mathscr{L}(V, V')$ (or $\mathscr{L}$) denote the set of all linear mappings from $V$ to $V'$.

For $T, F \in \mathscr{L}(V, V')$:
- **Sum:** $(T + F)(u) = T(u) + F(u)$
- **Scalar multiple:** $(aT)(u) = aT(u)$ for $a \in K$

Then $T + F$ and $aT$ are linear maps, and $\mathscr{L}(V, V')$ is a vector space.

### 3.2.7 Example 7 — Derivative

Let $V$ be the space of infinitely differentiable real-valued functions. $D: V \to V$, $D(f) = df/dt$ is linear:

$$
D(f + g) = Df + Dg, \qquad D(cf) = cDf.
$$

For example, $(D + I)f = Df + f$. If $f(x) = e^x$, then $(D + I)f = 2e^x$.

### 3.2.8 Theorem 2.1 — Linear Maps Determined by Basis Values

**Theorem 2.1.** Let $\{v_1, \dots, v_n\}$ be a basis of $V$, and $w_1, \dots, w_n \in W$. There exists a **unique** linear mapping $T: V \to W$ such that:

$$
T(v_1) = w_1, \quad \dots, \quad T(v_n) = w_n.
$$

Explicitly:

$$
T(x_1 v_1 + \cdots + x_n v_n) = x_1 w_1 + \cdots + x_n w_n.
$$

**Proof:**
- **Existence:** Define $T(v) = x_1 w_1 + \cdots + x_n w_n$ where $v = x_1 v_1 + \cdots + x_n v_n$. Then:
  - $T(v + v') = (x_1 + y_1)w_1 + \cdots + (x_n + y_n)w_n = T(v) + T(v')$
  - $T(cv) = cx_1 w_1 + \cdots + cx_n w_n = cT(v)$

- **Uniqueness:** Any linear $F$ with $F(v_i) = w_i$ must satisfy:
  $$
  F(x_1 v_1 + \cdots + x_n v_n) = x_1 w_1 + \cdots + x_n w_n = T(v).
  $$

## 3.3 The Kernel and Image of a Linear Map

### 3.3.1 Kernel

Let $F: V \to W$ be a linear map. The **kernel** of $F$ is:

$$
\operatorname{Ker} F = \{v \in V \mid F(v) = O\}.
$$

**Example 1:** $L: \mathbf{R}^3 \to \mathbf{R}$, $L(x, y, z) = 3x - 2y + z$. Then $\operatorname{Ker} L$ is the set of solutions to $3x - 2y + z = 0$.

More generally, for $A \in \mathbf{R}^n$, $L_A(X) = A \cdot X$ has kernel = all $X$ perpendicular to $A$.

**Example 2:** $P: \mathbf{R}^3 \to \mathbf{R}^2$, $P(x, y, z) = (x, y)$. Then $\operatorname{Ker} P = \{(0, 0, z) \mid z \in \mathbf{R}\}$.

**Property:** $\operatorname{Ker} F$ is a **subspace** of $V$.

**Proof:**
- $F(O) = O$, so $O \in \operatorname{Ker} F$
- If $v, w \in \operatorname{Ker} F$, then $F(v + w) = F(v) + F(w) = O + O = O$
- If $c \in K$, then $F(cv) = cF(v) = cO = O$

### 3.3.2 Injectivity Criterion

For a linear map $F: V \to W$, the following are **equivalent**:

1. $\operatorname{Ker} F = \{O\}$
2. $F$ is **injective**

**Proof:**
- (1 $\implies$ 2): If $F(v) = F(w)$, then $F(v - w) = O$, so $v - w = O$, hence $v = w$.
- (2 $\implies$ 1): If $F(v) = O = F(O)$, then $v = O$ by injectivity.

### 3.3.3 Theorem 3.1 — Linear Independence Preserved

**Theorem 3.1.** Let $F: V \to W$ be linear with $\operatorname{Ker} F = \{O\}$. If $v_1, \dots, v_n$ are linearly independent in $V$, then $F(v_1), \dots, F(v_n)$ are linearly independent in $W$.

**Proof:** Suppose $x_1 F(v_1) + \cdots + x_n F(v_n) = O$. By linearity, $F(x_1 v_1 + \cdots + x_n v_n) = O$. Since $\operatorname{Ker} F = \{O\}$, we have $x_1 v_1 + \cdots + x_n v_n = O$. By linear independence of $v_i$, all $x_i = 0$.

### 3.3.4 Image

The **image** of $F$ is:

$$
\operatorname{Im} F = \{w \in W \mid \exists v \in V \text{ such that } F(v) = w\}.
$$

**Property:** $\operatorname{Im} F$ is a **subspace** of $W$.

**Proof:**
- $F(O) = O \in \operatorname{Im} F$
- If $w_1 = F(v_1)$ and $w_2 = F(v_2)$, then $w_1 + w_2 = F(v_1 + v_2) \in \operatorname{Im} F$
- $cw_1 = F(cv_1) \in \operatorname{Im} F$

### 3.3.5 Theorem 3.2 — Dimension Formula

**Theorem 3.2.** Let $L: V \to W$ be linear. Then:

$$
\dim V = \dim \operatorname{Ker} L + \dim \operatorname{Im} L.
$$

**Proof sketch:**
- Let $\{w_1, \dots, w_s\}$ be a basis of $\operatorname{Im} L$, and $v_i \in V$ with $L(v_i) = w_i$.
- Let $\{u_1, \dots, u_q\}$ be a basis of $\operatorname{Ker} L$ (omit if kernel is $\{O\}$).
- Then $\{v_1, \dots, v_s, u_1, \dots, u_q\}$ is a basis of $V$:
  - **Generate:** For any $v \in V$, $L(v) = x_1 w_1 + \cdots + x_s w_s$. Then $v - x_1 v_1 - \cdots - x_s v_s \in \operatorname{Ker} L$, so it equals $y_1 u_1 + \cdots + y_q u_q$.
  - **Independent:** If $x_1 v_1 + \cdots + x_s v_s + y_1 u_1 + \cdots + y_q u_q = O$, apply $L$ to get $x_1 w_1 + \cdots + x_s w_s = O$, so all $x_i = 0$. Then $y_1 u_1 + \cdots + y_q u_q = O$, so all $y_j = 0$.

**Example 1 (cont.):** $L(x, y, z) = 3x - 2y + z$. $\operatorname{Im} L = \mathbf{R}$ (dimension 1), so $\dim \operatorname{Ker} L = 3 - 1 = 2$.

**Example 2 (cont.):** $P: \mathbf{R}^3 \to \mathbf{R}^2$ is surjective, so $\dim \operatorname{Im} P = 2$, hence $\dim \operatorname{Ker} P = 3 - 2 = 1$.

### 3.3.6 Theorem 3.3 — Bijectivity Criterion

**Theorem 3.3.** Let $L: V \to W$ be linear with $\dim V = \dim W$. If $\operatorname{Ker} L = \{O\}$ or $\operatorname{Im} L = W$, then $L$ is **bijective**.

**Proof:**
- If $\operatorname{Ker} L = \{O\}$: by Theorem 3.2, $\dim \operatorname{Im} L = \dim W$. By Corollary 3.5 (Chapter I), $\operatorname{Im} L = W$, so $L$ is surjective. Also injective since kernel is trivial.
- If $\operatorname{Im} L = W$: by Theorem 3.2, $\dim \operatorname{Ker} L = 0$, so $\operatorname{Ker} L = \{O\}$. Hence $L$ is injective and surjective.

## 3.4 Composition and Inverse of Linear Mappings

### 3.4.1 Theorem 4.1 — Composition of Linear Maps

**Theorem 4.1.** Let $F: U \to V$ and $G: V \to W$ be linear maps. Then $G \circ F: U \to W$ is also linear.

**Proof:**
- $(G \circ F)(u + v) = G(F(u + v)) = G(F(u) + F(v)) = G(F(u)) + G(F(v)) = (G \circ F)(u) + (G \circ F)(v)$
- $(G \circ F)(cu) = G(F(cu)) = G(cF(u)) = cG(F(u)) = c(G \circ F)(u)$

### 3.4.2 Theorem 4.2 — Distributive Laws

**Theorem 4.2.** Let $F: U \to V$ and $G, H: V \to W$ be linear. Then:

$$
(G + H) \circ F = G \circ F + H \circ F, \qquad (cG) \circ F = c(G \circ F).
$$

If $T: U \to V$ is also linear:

$$
G \circ (F + T) = G \circ F + G \circ T.
$$

**Proof of first:** $((G + H) \circ F)(u) = (G + H)(F(u)) = G(F(u)) + H(F(u)) = (G \circ F)(u) + (H \circ F)(u)$.

### 3.4.3 Non-Commutativity

If $U = V = W$, we can form $F \circ G$ and $G \circ F$. In general:

$$
F \circ G \neq G \circ F.
$$

**Example:** Let $U = \mathbf{R}^3$, $F(x, y, z) = (x, y, 0)$, $G(x, y, z) = (x, z, 0)$. Then:
- $(G \circ F)(x, y, z) = (x, 0, 0)$
- $(F \circ G)(x, y, z) = (x, z, 0)$

### 3.4.4 Powers of Linear Operators

A linear map $F: V \to V$ is called an **operator**. Define:
- $F^n = F \circ F \circ \cdots \circ F$ ($n$ times) for $n \ge 1$
- $F^0 = I$ (identity map)

Then $F^{r+s} = F^r \circ F^s$ for integers $r, s \ge 0$.

### 3.4.5 Theorem 4.3 — Inverse of a Linear Map is Linear

**Theorem 4.3.** Let $F: U \to V$ be linear with inverse $G: V \to U$. Then $G$ is linear.

**Proof:** Let $u_1 = G(v_1)$ and $u_2 = G(v_2)$, so $F(u_1) = v_1$ and $F(u_2) = v_2$. Then:

$$
F(u_1 + u_2) = F(u_1) + F(u_2) = v_1 + v_2.
$$

By definition of inverse, $G(v_1 + v_2) = u_1 + u_2 = G(v_1) + G(v_2)$. Similarly $G(cv) = cG(v)$.

### 3.4.6 Corollary 4.4 — Existence of Inverse

**Corollary 4.4.** Let $F: U \to V$ be linear with $\operatorname{Ker} F = \{O\}$ and $\operatorname{Im} F = V$. Then $F$ has an inverse linear map.

**Proof:** $\operatorname{Ker} F = \{O\}$ implies injectivity; $\operatorname{Im} F = V$ implies surjectivity. Hence $F$ is bijective and has an inverse, which is linear by Theorem 4.3.

### 3.4.7 Isomorphism

A linear map $F: U \to V$ with an inverse is called an **isomorphism** (or **invertible**).

**Example 1:** $F: \mathbf{R}^2 \to \mathbf{R}^2$, $F(x, y) = (3x - y, 4x + 2y)$. The kernel is $\{O\}$ (solve $3x - y = 0$, $4x + 2y = 0$ to get $x = y = 0$). By Theorem 3.2, $\dim \operatorname{Im} F = 2$, so $\operatorname{Im} F = \mathbf{R}^2$. Hence $F$ is an isomorphism.

**Example 2:** Let $V$ have dimension $n$ with basis $\{v_1, \dots, v_n\}$. The map $L: \mathbf{R}^n \to V$ defined by:

$$
L(x_1, \dots, x_n) = x_1 v_1 + \cdots + x_n v_n
$$

is an isomorphism.

**Proof:** $\operatorname{Ker} L = \{O\}$ (by linear independence) and $\operatorname{Im} L = V$ (since $v_i$ generate $V$).

### 3.4.8 Notation

For linear maps $F, G: V \to V$, we often write $FG$ instead of $F \circ G$. Then:

$$
F(G + H) = FG + FH.
$$

But $FG \neq GF$ in general. If $F$ and $G$ commute, then arithmetic of linear maps works like arithmetic of numbers.

> Powers $I, F, F^2, F^3, \dots$ commute with each other.

## 3.5 Geometric Applications

### 3.5.1 Line Segments

The **line segment** between $v$ and $v + u$ is:

$$
\{v + tu \mid 0 \le t \le 1\}.
$$

For $t = \frac{1}{2}$: midpoint $v + \frac{1}{2}u$. For $t = \frac{1}{3}$: one-third point.

The line segment between $v$ and $w$ (where $u = w - v$):

$$
v + t(w - v) = (1 - t)v + tw, \quad 0 \le t \le 1.
$$

Equivalently: $t_1 v + t_2 w$ with $t_1, t_2 \ge 0$ and $t_1 + t_2 = 1$.

**Property:** If $L: V \to V'$ is linear, the image of a line segment is a line segment:

$$
L(t_1 v + t_2 w) = t_1 L(v) + t_2 L(w).
$$

### 3.5.2 Parallelograms

Let $v, w$ be linearly independent. The **parallelogram spanned by $v, w$** is:

$$
\{t_1 v + t_2 w \mid 0 \le t_i \le 1 \text{ for } i = 1, 2\}.
$$

A **translated parallelogram** by $u$:

$$
\{u + t_1 v + t_2 w \mid 0 \le t_i \le 1\}.
$$

**Property:** The image of a parallelogram under a linear map is a parallelogram (if non-degenerate):

$$
L(u + t_1 v + t_2 w) = L(u) + t_1 L(v) + t_2 L(w).
$$

### 3.5.3 Triangles

The **triangle spanned by $O, v, w$** (linearly independent):

$$
\{t_1 v + t_2 w \mid t_i \ge 0, \; t_1 + t_2 \le 1\}.
$$

This equals the union of all line segments from $v$ to points on $\overline{Ow}$.

A **general triangle** with vertices $v_1, v_2, v_3$ (where $v_1 - v_3$ and $v_2 - v_3$ are linearly independent):

$$
\{t_1 v_1 + t_2 v_2 + t_3 v_3 \mid t_i \ge 0, \; t_1 + t_2 + t_3 = 1\}.
$$

This is the translation by $v_3$ of the triangle spanned by $O, v_1 - v_3, v_2 - v_3$.

**Property:** The image of a triangle under a linear map is a triangle (if vertices don't lie on a straight line).

### 3.5.4 Convex Sets

A subset $S$ of $V$ is **convex** if for any $P, Q \in S$, the line segment between $P$ and $Q$ is contained in $S$.

**Theorem 5.1.** Let $P_1, \dots, P_n \in V$. The set of all linear combinations:

$$
t_1 P_1 + \cdots + t_n P_n \quad \text{with } t_i \ge 0 \text{ and } t_1 + \cdots + t_n = 1
$$

is convex.

**Proof:** Let $P = \sum t_i P_i$ and $Q = \sum s_i P_i$ with $\sum t_i = \sum s_i = 1$. For $0 \le t \le 1$:

$$
(1 - t)P + tQ = \sum [(1 - t)t_i + ts_i] P_i.
$$

The coefficients are non-negative and sum to $(1 - t) + t = 1$.

This convex set is called the convex set **spanned by** $P_1, \dots, P_n$. A triangle is a special case.

**Theorem 5.2.** Any convex set $S'$ containing $P_1, \dots, P_n$ also contains all linear combinations $t_1 P_1 + \cdots + t_n P_n$ with $t_i \ge 0$ and $\sum t_i = 1$.

**Proof:** By induction on $n$. For $n = 1$, trivial. For $n > 1$, if $t_n = 1$, done. Otherwise:

$$
t_1 P_1 + \cdots + t_n P_n = (1 - t_n)Q + t_n P_n
$$

where $Q = \sum_{i=1}^{n-1} \frac{t_i}{1 - t_n} P_i \in S'$ by induction. Since $S'$ is convex, the result follows.

**Example:** Let $L: V \to \mathbf{R}$ be linear. Then $\{v \in V \mid L(v) < 0\}$ is convex.

**Proof:** If $L(v) < 0$ and $L(w) < 0$, then for $0 < t < 1$:

$$
L(tv + (1 - t)w) = tL(v) + (1 - t)L(w) < 0.
$$

---

[<- Previous: 2. Matrices](02-matrices.md) | [Next: 4. Linear Maps and Matrices ->](04-linear-maps-and-matrices.md)
