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


### 10.3 Other Notations for Line Integrals

If $C$ denotes the graph of $\alpha$, the line integral is also written
$$
\int_C f\cdot d\alpha,
$$
called **the integral of $f$ along $C$**. With endpoints $a=\alpha(a)$ and $b=\alpha(b)$,
$$
\int_a^{b} f \quad\text{or}\quad \int_a^{b} f\cdot d\alpha
$$
denotes the line integral of $f$ from $a$ to $b$ along $\alpha$. The value depends on the **path** $\alpha$, not just the endpoints.

When $a=b$ the path is **closed**; the symbol $\displaystyle\oint$ indicates integration along a closed path.

**Component form.** If $f=(f_1,\dots,f_n)$ and $\alpha=(\alpha_1,\dots,\alpha_n)$, then
$$
\int f\cdot d\alpha = \sum_{k=1}^{n} \int_a^{b} f_k[\alpha(t)]\,\alpha_k'(t)\,dt
= \int f_1\,d\alpha_1 + \cdots + f_n\,d\alpha_n.
$$

- **2D:** $x=\alpha_1(t),\; y=\alpha_2(t)$. The integral is written
  $$
  \int_C f_1\,dx + f_2\,dy
  = \int_C f_1(x,y)\,dx + f_2(x,y)\,dy.
  $$
- **3D:** $x=\alpha_1(t),\; y=\alpha_2(t),\; z=\alpha_3(t)$. The integral is written
  $$
  \int_C f_1\,dx + f_2\,dy + f_3\,dz.
  $$

**Example.** Let $f(x,y)=\sqrt{y}\,\mathbf{i}+(x^{3}+y)\,\mathbf{j}$ for $y\ge0$. Compute $\int f\cdot d\alpha$ from $(0,0)$ to $(1,1)$.

| Path | Parametrization | Result |
|------|-----------------|--------|
| (a) Straight line | $\alpha(t)=t\mathbf{i}+t\mathbf{j}$, $0\le t\le1$ | $\displaystyle\int_0^{1}\bigl(\sqrt{t}+t^{3}+t\bigr)\,dt = \frac{17}{12}$ |
| (b) Curve $x=t^{2},\;y=t^{3}$ | $\alpha(t)=t^{2}\mathbf{i}+t^{3}\mathbf{j}$, $0\le t\le1$ | $\displaystyle\int_0^{1}\bigl(2t^{5/2}+3t^{8}+3t^{5}\bigr)\,dt = \frac{59}{42}$ |

The two values differ: the integral **depends on the path**.

Using a different parametrization of the same curve, e.g. $\beta(t)=t\mathbf{i}+t^{3/2}\mathbf{j}$, yields the same value $59/42$. The integral is independent of the **parametrization** used to describe the curve (proved in the next section).


### 10.4 Basic Properties of Line Integrals

**Linearity** (with respect to the integrand):
$$
\int (af+bg)\cdot d\alpha = a\int f\cdot d\alpha + b\int g\cdot d\alpha.
$$

**Additivity** (with respect to the path): if $C=C_1\cup C_2$ traced by $\alpha$ on $[a,c]$ and $[c,b]$ respectively ($a<c<b$),
$$
\int_C f\cdot d\alpha = \int_{C_1} f\cdot d\alpha + \int_{C_2} f\cdot d\alpha.
$$

**Change of parameter.** Let $\alpha$ be defined on $[a,b]$ and let $u:[c,d]\to[a,b]$ be differentiable with $u'\neq0$ everywhere. Then
$$
\beta(t)=\alpha[u(t)]
$$
is an **equivalent** path with the same graph. If $u'>0$ on $[c,d]$, $\alpha$ and $\beta$ trace the curve in the **same direction** ($u$ is **orientation-preserving**). If $u'<0$, they trace it in **opposite directions** ($u$ is **orientation-reversing**).

**Theorem 10.1 (Invariance under change of parameter).** Let $\alpha$ and $\beta$ be equivalent piecewise smooth paths. Then
$$
\int_C f\cdot d\alpha = \int_C f\cdot d\beta
$$
if $\alpha$ and $\beta$ trace $C$ in the same direction; and
$$
\int_C f\cdot d\alpha = -\int_C f\cdot d\beta
$$
if they trace $C$ in opposite directions.

*Proof sketch.* For smooth paths, $\beta'(t)=\alpha'[u(t)]\,u'(t)$ by the chain rule. Then
$$
\int_C f\cdot d\beta = \int_c^{d} f(\alpha[u(t)])\cdot\alpha'[u(t)]\,u'(t)\,dt.
$$
Substitute $v=u(t)$, $dv=u'(t)\,dt$:
$$
\int_C f\cdot d\beta = \int_{u(c)}^{u(d)} f(\alpha(v))\cdot\alpha'(v)\,dv = \pm\int_a^{b} f(\alpha(v))\cdot\alpha'(v)\,dv = \pm\int_C f\cdot d\alpha,
$$
with $+$ when $u(c)=a,\;u(d)=b$ (same direction) and $-$ when $u(c)=b,\;u(d)=a$ (opposite direction). Extend to piecewise smooth paths by additivity.

