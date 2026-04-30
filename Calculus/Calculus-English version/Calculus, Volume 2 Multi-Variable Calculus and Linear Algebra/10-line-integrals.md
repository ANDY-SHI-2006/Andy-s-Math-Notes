# Chapter 10 — Line Integrals

### 10.1 Introduction

This chapter extends the notion of integral from intervals to curves. The interval $[a,b]$ is replaced by a curve in $n$-space described by a vector-valued function $\alpha$, and the integrand is a vector field $f$ defined on this curve. The resulting integral is called a **line integral** (or **curvilinear integral** / **contour integral**), denoted $\int f\cdot d\alpha$. The dot is used purposely to suggest an inner product of two vectors. The curve is called a **path of integration**.

Line integrals are fundamental in pure and applied mathematics, occurring in connection with work, potential energy, heat flow, change in entropy, circulation of a fluid, and other physical situations.

### 10.2 Paths and Line Integrals

**Curve vs. path.** In Volume I, a curve was the graph of a continuous vector-valued function $\alpha:J\to\mathbb{R}^{n}$ on $J=[a,b]$. For line integrals we care not only about the set of points but also the **manner** in which the curve is traced out — the function $\alpha$ itself.

**Definitions.**
- A **continuous path** in $n$-space is a continuous function $\alpha:J\to\mathbb{R}^{n}$ on a finite closed interval $J=[a,b]$.
- The path is **smooth** if $\alpha'$ exists and is continuous on $(a,b)$.
- The path is **piecewise smooth** if $[a,b]$ can be partitioned into finitely many subintervals on each of which the path is smooth.

**Definition of line integral.** Let $\alpha$ be a piecewise smooth path in $n$-space on $[a,b]$, and let $f$ be a vector field defined and bounded on the graph of $\alpha$. The **line integral of $f$ along $\alpha$** is
$$
\int f\cdot d\alpha = \int_a^{b} f[\alpha(t)]\cdot\alpha'(t)\,dt,\tag{10.1}
$$
whenever the integral on the right exists (proper or improper).

*Note:* In most practical examples $f[\alpha(t)]\cdot\alpha'(t)$ is bounded on $[a,b]$ and continuous except possibly at finitely many points, so the integral exists as a proper integral.

