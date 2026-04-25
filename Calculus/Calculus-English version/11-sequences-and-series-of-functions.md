[<- Previous: 10. Sequences, Infinite Series, Improper Integrals](10-sequences-infinite-series-improper-integrals.md) | [Next: 12. Vector Algebra ->](12-vector-algebra.md)

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

[<- Previous: 10. Sequences, Infinite Series, Improper Integrals](10-sequences-infinite-series-improper-integrals.md) | [Next: 12. Vector Algebra ->](12-vector-algebra.md)
