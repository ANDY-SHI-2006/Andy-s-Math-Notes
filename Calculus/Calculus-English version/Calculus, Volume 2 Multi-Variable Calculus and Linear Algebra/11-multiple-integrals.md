# Chapter 11 — Multiple Integrals

### 11.1 Introduction

Volume I discussed integrals $\int_a^{b}f(x)\,dx$; Chapter 10 generalized this to line integrals. This chapter extends the concept in yet another direction: the one-dimensional interval $[a,b]$ is replaced by a two-dimensional set $Q$, called the **region of integration**.

- First: rectangular regions.
- Later: more general regions with curvilinear boundaries.

The integrand is a scalar field $f$ defined and bounded on $Q$. The resulting integral is called a **double integral**, denoted
$$
\iint_Q f \qquad\text{or}\qquad \iint_Q f(x,y)\,dx\,dy.
$$
As in the 1D case, the symbols $dx$ and $dy$ play no role in the definition, but they are useful in computations and transformations.

**Program of the chapter:**
1. Definition of the double integral (analogous to the 1D case; first for step functions, then for general functions).
2. Computation by **repeated one-dimensional integration**.
3. Connection between double integrals and line integrals.
4. Applications to area, volume, mass, center of mass, etc.
5. Extension to $n$-space.


### 11.2 Partitions of Rectangles. Step Functions

A **rectangle** $Q$ is the Cartesian product of two closed intervals:
$$
Q=[a,b]\times[c,d]=\{(x,y):x\in[a,b],\;y\in[c,d]\}.
$$

**Partition of $Q$.** Let $P_1=\{x_0,\dots,x_n\}$ be a partition of $[a,b]$ and $P_2=\{y_0,\dots,y_m\}$ a partition of $[c,d]$. The Cartesian product $P=P_1\times P_2$ is a **partition of $Q$**, decomposing $Q$ into $mn$ subrectangles. A partition $P'$ is **finer** than $P$ if $P\subseteq P'$.

The Cartesian product of two open subintervals is an **open subrectangle** (edges missing).

**Definition (Step function).** A function $f$ on a rectangle $Q$ is a **step function** if there exists a partition $P$ of $Q$ such that $f$ is constant on each open subrectangle of $P$.

- The graph consists of horizontal rectangular patches (Figure 11.3).
- Values on boundary points are well-defined but irrelevant to integration theory.
- Step functions on $Q$ form a **linear space**: if $f,g$ are step functions with partitions $P,P'$, then $c_1f+c_2g$ is constant on the open subrectangles of the common refinement $P\cup P'$.


### 11.3 The Double Integral of a Step Function

Let $P=P_1\times P_2$ partition a rectangle $Q$ into $mn$ subrectangles $Q_{ij}$, and let $f$ be a step function constant with value $c_{ij}$ on the interior of $Q_{ij}$.

**Definition.** The **double integral** of $f$ over $Q$ is
$$
\iint_Q f = \sum_{i=1}^{n}\sum_{j=1}^{m} c_{ij}\,(x_i-x_{i-1})(y_j-y_{j-1}).\tag{11.1}
$$
The value is independent of the partition, provided $f$ is constant on the open subrectangles.

Using $\Delta x_i=x_i-x_{i-1}$ and $\Delta y_j=y_j-y_{j-1}$:
$$
\iint_Q f = \sum_{i=1}^{n}\sum_{j=1}^{m} c_{ij}\,\Delta x_i\,\Delta y_j.
$$
Alternative notation: $\displaystyle\iint_Q f(x,y)\,dx\,dy$.

If $f(x,y)=k$ on the interior of $Q$,
$$
\iint_Q f = k(b-a)(d-c).\tag{11.2}
$$

**Repeated (iterated) integration.** Since $b-a=\int_a^{b}dx$ and $d-c=\int_c^{d}dy$,
$$
\iint_Q f = \int_c^{d}\Bigl[\int_a^{b}f(x,y)\,dx\Bigr]dy
= \int_a^{b}\Bigl[\int_c^{d}f(x,y)\,dy\Bigr]dx.\tag{11.3}
$$
This holds for step functions by summing over subrectangles.

**Properties** (for step functions $s,t$ on a nondegenerate rectangle $Q$):

- **Theorem 11.1 (Linearity).**
  $$
  \iint_Q\bigl[c_1s+c_2t\bigr]\,dx\,dy
  = c_1\iint_Q s\,dx\,dy + c_2\iint_Q t\,dx\,dy.
  $$
- **Theorem 11.2 (Additivity).** If $Q=Q_1\cup Q_2$ (two rectangles),
  $$
  \iint_Q s\,dx\,dy = \iint_{Q_1}s\,dx\,dy + \iint_{Q_2}s\,dx\,dy.
  $$
- **Theorem 11.3 (Comparison).** If $s\le t$ on $Q$,
  $$
  \iint_Q s\,dx\,dy \le \iint_Q t\,dx\,dy.
  $$
  In particular, $t\ge0$ on $Q$ $\Rightarrow$ $\displaystyle\iint_Q t\,dx\,dy\ge0$.

