# Chapter 8 — Differential Calculus of Scalar and Vector Fields

### 8.1 Functions from $\mathbb{R}^n$ to $\mathbb{R}^m$. Scalar and Vector Fields

- **Scalar field:** $f:\mathbb{R}^n\to\mathbb{R}$ ($m=1$). Also written $f(x)$ or $f(x_1,\dots,x_n)$.
- **Vector field:** $f:\mathbb{R}^n\to\mathbb{R}^m$ ($m>1$).
- **Inner product and norm:** $x\cdot y=\sum_{k=1}^n x_ky_k$, $\|x\|=(x\cdot x)^{1/2}$.
- Points in $\mathbb{R}^2$ denoted $(x,y)$; in $\mathbb{R}^3$ denoted $(x,y,z)$.
- Examples: temperature $f(x)$ (scalar field); wind velocity (vector field).
- This chapter extends limit, continuity, and derivative to scalar and vector fields.


### 8.2 Open Balls and Open Sets

- **Open $n$-ball:** $B(a;r)=\{x\in\mathbb{R}^n:\|x-a\|<r\}$.
  - In $\mathbb{R}^1$: open interval; in $\mathbb{R}^2$: circular disk; in $\mathbb{R}^3$: solid sphere.

**Definitions.**
- $a\in S$ is an **interior point** of $S$ if some ball $B(a)\subseteq S$.
- The set of all interior points is the **interior** $\operatorname{int}S$.
- $S$ is **open** iff $S=\operatorname{int}S$.
- An open set containing $a$ is a **neighborhood** of $a$.

**Examples.**
- Open intervals in $\mathbb{R}^1$; unions of open intervals are open.
- $[a,b]$ is **not** open.
- Cartesian product of open sets in $\mathbb{R}^1$ is open in $\mathbb{R}^2$ (e.g. open rectangle).

**Exterior and boundary.**
- $x$ is **exterior** to $S$ if some $B(x)$ contains no points of $S$; the set of such points is $\operatorname{ext}S$.
- A **boundary point** is neither interior nor exterior; the set of all boundary points is $\partial S$.
- Example: for $B(O;1)$, the exterior is $\|x\|>1$ and the boundary is $\|x\|=1$.


### 8.4 Limits and Continuity

For $f:S\to\mathbb{R}^m$ with $S\subseteq\mathbb{R}^n$:
$$\lim_{x\to a}f(x)=b\quad\Longleftrightarrow\quad\lim_{\|x-a\|\to0}\|f(x)-b\|=0.\tag{8.1–8.2}$$

- **Continuity at $a$:** $f$ is defined at $a$ and $\displaystyle\lim_{x\to a}f(x)=f(a)$.
- **Continuity on $S$:** continuous at each point of $S$.

**Theorem 8.1 (Limit laws).** If $\lim_{x\to a}f(x)=b$ and $\lim_{x\to a}g(x)=c$, then:
- (a) $\lim\,[f+g]=b+c$.
- (b) $\lim\,\lambda f=\lambda b$.
- (c) $\lim\,f\cdot g=b\cdot c$.
- (d) $\lim\,\|f\|=\|b\|$.

**Component-wise continuity.** $f=(f_1,\dots,f_m)$ is continuous at $a$ **iff** each component $f_k$ is continuous at $a$ (since $f_k(x)=f(x)\cdot e_k$ and $f(x)=\sum f_k(x)e_k$).

**Examples of continuous fields.**
- Identity function $f(x)=x$; its components $f_k(x)=x_k$.
- Every linear transformation $f:\mathbb{R}^n\to\mathbb{R}^m$.
- Polynomials in $n$ variables (finite sums/products of continuous scalar fields).
- Rational functions $P/Q$ (where defined, i.e. $Q(x)\neq0$).

**Theorem 8.2 (Composition).** If $g$ is continuous at $a$ and $f$ is continuous at $g(a)$, then $f\circ g$ is continuous at $a$.

**Example of discontinuity.** $f(x,y)=\dfrac{xy}{x^2+y^2}$ ($f(0,0)=0$) is continuous in each variable separately at $(0,0)$, but **not** continuous there as a function of two variables (along $y=x$, $f=\frac12\neq0$).
