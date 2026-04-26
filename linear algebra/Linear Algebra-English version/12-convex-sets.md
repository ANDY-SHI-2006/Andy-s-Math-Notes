[<- Previous: 11. Polynomials and Primary Decomposition](11-polynomials-and-primary-decomposition.md) | [Next: A. Complex Numbers ->](a-complex-numbers.md)

# 12. Convex Sets

## 12.1 Definitions

Let $S$ be a subset of $\mathbb{R}^m$. We say that $S$ is **convex** if given points $P, Q$ in $S$, the line segment joining $P$ to $Q$ is also contained in $S$.

We recall that the line segment joining $P$ to $Q$ is the set of all points $P + t(Q - P)$ with $0 \leq t \leq 1$, i.e. the set of points $(1 - t)P + tQ$ with $0 \leq t \leq 1$.

**Theorem 1.1.** Let $P_1, \dots, P_n$ be points of $\mathbb{R}^m$. The set of all linear combinations

$$
x_1 P_1 + \cdots + x_n P_n
$$

with $0 \leq x_i \leq 1$ and $x_1 + \cdots + x_n = 1$, is a convex set.

**Theorem 1.2.** Let $P_1, \dots, P_n$ be points of $\mathbb{R}^m$. Any convex set which contains $P_1, \dots, P_n$ also contains all linear combinations

$$
x_1 P_1 + \cdots + x_n P_n
$$

such that $0 \leq x_i \leq 1$ for all $i$, and $x_1 + \cdots + x_n = 1$.

> In view of Theorems 1.1 and 1.2, the set of linear combinations described in these theorems is the **smallest convex set** containing all points $P_1, \dots, P_n$.

The following properties have already occurred as exercises:

| Property | Statement |
|----------|-----------|
| (1) | If $S$ and $S'$ are convex sets, then the intersection $S \cap S'$ is convex. |
| (2) | Let $F: \mathbb{R}^m \to \mathbb{R}^n$ be a linear map. If $S$ is convex in $\mathbb{R}^m$, then $F(S)$ is convex in $\mathbb{R}^n$. |
| (3) | Let $F: \mathbb{R}^m \to \mathbb{R}^n$ be a linear map. If $S' \subset \mathbb{R}^n$ is convex, then $F^{-1}(S')$ is convex. |

**Examples.** Let $A$ be a vector in $\mathbb{R}^n$. The map $F(X) = A \cdot X$ is linear. Note that a point $c \in \mathbb{R}$ is a convex set. Hence the **hyperplane** $H$ consisting of all $X$ such that $A \cdot X = c$ is convex.

Furthermore, the set of all $X \in \mathbb{R}^n$ such that $A \cdot X > c$ is convex. It is called an **open half space**. Similarly, the set of points $X \in \mathbb{R}^n$ such that $A \cdot X \geq c$ is called a **closed half space**.

A hyperplane whose equation is $X \cdot N = c$ determines two closed half spaces, namely the spaces defined by the equations $X \cdot N \geq c$ and $X \cdot N \leq c$, and similarly for the open half spaces.

## 12.2 Intersections of Half Spaces

Since the intersection of convex sets is convex, the intersection of a finite number of half spaces is convex. Such an intersection can be bounded or unbounded.

**Definition (Bounded).** A subset $S$ of $\mathbb{R}^n$ is said to be **bounded** if there exists a number $c > 0$ such that $\|X\| \leq c$ for all $X \in S$.

## 12.3 Separating Hyperplanes

**Theorem 2.1.** Let $S$ be a closed convex set in $\mathbb{R}^n$. Let $P$ be a point of $\mathbb{R}^n$. Then either $P$ belongs to $S$, or there exists a hyperplane $H$ which contains $P$, and such that $S$ is contained in one of the open half spaces determined by $H$.

**Proof.** Suppose $P$ does not belong to $S$. We consider the function $f$ on the closed set $S$ given by $f(X) = \|X - P\|$. By calculus this function has a minimum on $S$. Let $Q$ be a point of $S$ such that $\|Q - P\| \leq \|X - P\|$ for all $X$ in $S$. Let $N = Q - P$. Since $P$ is not in $S$, $N \neq O$.

We contend that the hyperplane passing through $P$, perpendicular to $N$, satisfies our requirements. Let $Q'$ be any point of $S$, $Q' \neq Q$. Then for every $t$ with $0 < t \leq 1$:

$$
\|Q - P\| \leq \|Q + t(Q' - Q) - P\| = \|(Q - P) + t(Q' - Q)\|.
$$

Squaring gives

$$
(Q - P)^2 \leq (Q - P)^2 + 2t(Q - P)\cdot(Q' - Q) + t^2(Q' - Q)^2.
$$

Canceling and dividing by $t$:

$$
0 \leq 2(Q - P)\cdot(Q' - Q) + t(Q' - Q)^2.
$$

Letting $t \to 0$ yields $0 \leq (Q - P)\cdot(Q' - Q) = N\cdot(Q' - P) - N\cdot N$. But $N\cdot N > 0$. Hence:

$$
Q' \cdot N > P \cdot N.
$$

This proves that $S$ is contained in the open half space defined by $X \cdot N > P \cdot N$. ∎

**Proposition.** Let $S$ be a convex set in $\mathbb{R}^n$. Then the closure of $S$ (denoted by $\bar{S}$) is convex.

**Proof.** If $P, Q$ are points in the closure, we can find points $P_k, Q_k$ of $S$ tending to $P$ and $Q$ respectively. Then $tP_k + (1-t)Q_k$ tends to $tP + (1-t)Q$, which therefore lies in the closure of $S$. ∎

**Definition (Boundary point).** Let $S$ be a convex set in $\mathbb{R}^n$. Let $P$ be a **boundary point** of $S$. This means a point such that for every $\epsilon > 0$, the open ball centered at $P$, of radius $\epsilon$ in $\mathbb{R}^n$, contains points which are in $S$, and points which are not in $S$.

**Definition (Supporting hyperplane).** A hyperplane $H$ is said to be a **supporting hyperplane** of $S$ at $P$ if $P$ is contained in $H$, and if $S$ is contained in one of the two closed half spaces determined by $H$.

**Theorem 2.2.** Let $S$ be a convex set in $\mathbb{R}^n$, and let $P$ be a boundary point of $S$. Then there exists a supporting hyperplane of $S$ at $P$.

**Proof.** Let $\bar{S}$ be the closure of $S$. Then $\bar{S}$ is convex, and $P$ is a boundary point of $\bar{S}$. If we can prove the theorem for $\bar{S}$, then it certainly follows for $S$. Thus we may assume $S$ is closed.

For each integer $k > 2$, we can find a point $P_k$ not in $S$, but at distance $< 1/k$ from $P$. By Theorem 2.1, we find a point $Q_k$ on $S$ whose distance from $P_k$ is minimal, and we let $N_k = Q_k - P_k$. Let $N'_k$ be the vector in the same direction as $N_k$ but of norm $1$. The sequence of vectors $N'_k$ has a point of accumulation $N'$ on the sphere of radius $1$, because the sphere is compact.

By Theorem 2.1, for all $X \in S$:

$$
X \cdot N_k \geq P_k \cdot N_k,
$$

whence dividing by $\|N_k\|$:

$$
X \cdot N'_k > P_k \cdot N'_k.
$$

Since $N'$ is an accumulation point of $\{N'_k\}$ and $P$ is a limit of $\{P_k\}$, it follows by continuity that for each $X$ in $S$:

$$
X \cdot N' \geq P \cdot N'.
$$

This proves our theorem. ∎

> **Remark.** Let $S$ be a convex set, and let $H$ be a hyperplane defined by $X \cdot N = a$. Assume that for all $X \in S$ we have $X \cdot N \geq a$. If $P$ is a point of $S$ lying in the hyperplane, then $P$ is a boundary point of $S$. Otherwise, for $\epsilon > 0$ sufficiently small, $P - \epsilon N$ would be a point of $S$, and thus $(P - \epsilon N)\cdot N = P\cdot N - \epsilon N\cdot N = a - \epsilon N\cdot N < a$, contrary to hypothesis. We conclude therefore that $H$ is a supporting hyperplane of $S$ at $P$.

## 12.4 Extreme Points and Supporting Hyperplanes

**Definition (Extreme point).** Let $S$ be a convex set and let $P$ be a point of $S$. We shall say that $P$ is an **extreme point** of $S$ if there do not exist points $Q_1, Q_2$ of $S$ with $Q_1 \neq Q_2$ such that $P$ can be written in the form

$$
P = tQ_1 + (1-t)Q_2 \quad \text{with} \quad 0 < t < 1.
$$

In other words, $P$ cannot lie on a line segment contained in $S$ unless it is one of the end-points of the line segment.

**Theorem 3.1.** Let $S$ be a closed convex set which is bounded. Then every supporting hyperplane of $S$ contains an extreme point.

**Proof.** Let $H$ be a supporting hyperplane, defined by the equation $X \cdot N = P_0 \cdot N$ at a boundary point $P_0$, and say $X \cdot N \geq P_0 \cdot N$ for all $X \in S$. Let $T$ be the intersection of $S$ and the hyperplane. Then $T$ is convex, closed, and bounded.

We contend that an extreme point of $T$ will also be an extreme point of $S$. To prove this, let $P$ be an extreme point of $T$, and suppose we can write $P = tQ_1 + (1-t)Q_2$ with $0 < t < 1$ and $Q_1, Q_2 \in S$. Dotting with $N$ and using $P \cdot N = P_0 \cdot N$:

$$
P_0 \cdot N = t Q_1 \cdot N + (1-t) Q_2 \cdot N. \tag{1}
$$

We have $Q_1 \cdot N, Q_2 \cdot N \geq P_0 \cdot N$. If one of these is $> P_0 \cdot N$, say $Q_1 \cdot N > P_0 \cdot N$, then the right-hand side of (1) is $> t P_0 \cdot N + (1-t) P_0 \cdot N = P_0 \cdot N$, which is impossible. Hence both $Q_1, Q_2$ lie in the hyperplane, contradicting the hypothesis that $P$ is an extreme point of $T$.

We now find an extreme point of $T$. Among all points of $T$, there is at least one whose first coordinate is smallest, because $T$ is closed and bounded. (The image of $T$ under this projection has a greatest lower bound which is taken on by an element of $T$ since $T$ is closed.) Let $T_1$ be the subset of $T$ consisting of all points whose first coordinate equals this smallest one. Then $T_1$ is closed and bounded. We can find a point of $T_1$ whose second coordinate is smallest among all points of $T_1$, and the set $T_2$ of all points of $T_1$ having this second coordinate is closed and bounded. Proceeding in this way, we find a point $P = (p_1, \dots, p_n)$ of $T$ having successively smallest first, second, $\dots$, $n$-th coordinate.

We assert that $P$ is an extreme point of $T$. Suppose $P = tX + (1-t)Y$ with $0 < t < 1$, where $X = (x_1, \dots, x_n)$ and $Y = (y_1, \dots, y_n)$ are in $T$. Then $x_1, y_1 \geq p_1$, and $p_1 = tx_1 + (1-t)y_1$. If $x_1$ or $y_1 > p_1$, then $tx_1 + (1-t)y_1 > p_1$, impossible. Hence $x_1 = y_1 = p_1$. Proceeding inductively, suppose $x_i = y_i = p_i$ for $i = 1, \dots, r$. Then if $r < n$:

$$
p_{r+1} = tx_{r+1} + (1-t)y_{r+1},
$$

and the same argument gives $x_{r+1} = y_{r+1} = p_{r+1}$. It follows that $X = Y = P$, whence $P$ is an extreme point. This proves our theorem. ∎

## 12.5 The Krein-Milman Theorem

Let $E$ be a set of points in $\mathbb{R}^n$ (with at least one point in it). We wish to describe the smallest convex set containing $E$. It is the intersection of all convex sets containing $E$, because this intersection is convex and is clearly smallest.

We can also describe this smallest convex set in another way. Let $E^c$ be the set of all linear combinations

$$
t_1 P_1 + \cdots + t_m P_m
$$

of points $P_1, \dots, P_m$ in $E$ with real coefficients $t_i$ such that

$$
0 \leq t_i \leq 1 \quad \text{and} \quad t_1 + \cdots + t_m = 1.
$$

Then $E^c$ is convex. Any convex set containing $E$ must contain $E^c$, and hence $E^c$ is the smallest convex set containing $E$. We call $E^c$ the **convex closure** (or **convex hull**) of $E$.

Let $S$ be a convex set and let $E$ be the set of its extreme points. Then $E^c \subset S$. We ask for conditions under which $E^c = S$.

> **Examples.** An unbounded convex set need not be the convex closure of its extreme points (e.g. the closed upper half plane, which has no extreme points). Also, an open convex set need not be the convex closure of its extreme points (the interior of an egg has no extreme points). The Krein-Milman theorem states that if we eliminate these two possibilities, then no other troubles can occur.

**Theorem 4.1 (Krein-Milman Theorem).** Let $S$ be a closed, bounded, convex set in $\mathbb{R}^n$. Then $S$ is the smallest closed convex set containing the extreme points of $S$. Equivalently, $S$ is the convex closure of its extreme points.

**Proof.** Let $S'$ be the intersection of all closed convex sets containing the extreme points of $S$. Then $S' \subset S$. We must show that $S$ is contained in $S'$.

Let $P \in S$, and suppose $P \notin S'$. By Theorem 2.1, there exists a hyperplane $H$ passing through $P$, defined by an equation $X \cdot N = c$, such that $X \cdot N > c$ for all $X \in S'$. Let $L: \mathbb{R}^n \to \mathbb{R}$ be the linear map $L(X) = X \cdot N$. Then $L(P) = c$, and $L(P)$ is not contained in $L(S')$.

Since $S$ is closed and bounded, the image $L(S)$ is closed and bounded, and this image is also convex. Hence $L(S)$ is a closed interval, say $[a, b]$, containing $c$. Thus $a \leq c \leq b$. Let $H_a$ be the hyperplane defined by $X \cdot N = a$.

By the remark following Theorem 2.2, we know that $H_a$ is a supporting hyperplane of $S$. By Theorem 3.1, we conclude that $H_a$ contains an extreme point of $S$. This extreme point lies in $S'$. But for all $X$ in $S'$ we have $X \cdot N > c \geq a$, contradicting the fact that the extreme point satisfies $X \cdot N = a$. This proves the Krein-Milman theorem. ∎

---

[<- Previous: 11. Polynomials and Primary Decomposition](11-polynomials-and-primary-decomposition.md) | [Next: A. Complex Numbers ->](a-complex-numbers.md)
