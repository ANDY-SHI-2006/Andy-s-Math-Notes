# Chapter 15 — Introduction to Numerical Analysis

### 15.2 Approximations by Polynomials

**Taylor polynomial (point-matching).** If $f$ has $n$ derivatives at $a$, the unique polynomial $P$ of degree $\le n$ with
$$
 P(a)=f(a),\;P'(a)=f'(a),\;\dots,\;P^{(n)}(a)=f^{(n)}(a)
$$
is
$$
 P(x)=\sum_{k=0}^{n}\frac{f^{(k)}(a)}{k!}(x-a)^{k}.
$$
With error $E_{n}(x)=f(x)-P(x)$,
$$
 f(x)=P(x)+E_{n}(x),\qquad
 E_{n}(x)=\frac{1}{n!}\int_{a}^{x}(x-t)^{n}f^{(n+1)}(t)\,dt
 =\frac{f^{(n+1)}(c)}{(n+1)!}(x-a)^{n+1},
$$
where $c$ lies between $a$ and $x$.

**Interpolating polynomial (value-matching).** Given distinct points $x_{0},x_{1},\dots,x_{n}$, the unique polynomial $P$ of degree $\le n$ satisfying
$$
 P(x_{k})=f(x_{k})\qquad(k=0,\dots,n)\tag{15.1}
$$
is called the **interpolating polynomial**.  The $n+1$ coefficients are obtained from a linear system (Cramer’s rule in principle; practical methods in later sections).

**Least-square approximation.** For $f$ integrable on $[a,b]$, seek a polynomial $P$ of degree $\le n$ minimizing the mean-square error
$$
 \int_{a}^{b}\bigl|f(x)-P(x)\bigr|^{2}\,dx.
$$
For continuous $f$ such a $P$ exists and is unique; Legendre polynomials (Section 1.14) play a fundamental role.


### 15.3 Polynomial Approximation and Normed Linear Spaces

**Definition (Norm).** Let $V$ be a linear space.  A real-valued function $N$ on $V$ is a **norm** if
- (a) $N(f)\ge0$;
- (b) $N(cf)=|c|\,N(f)$;
- (c) $N(f+g)\le N(f)+N(g)$;
- (d) $N(f)=0\;\Longrightarrow\;f=O$.

A space with a norm is a **normed linear space** (written $\|f\|$ instead of $N(f)$).  If (d) fails, $N$ is a **seminorm**.

**Example 1 (Taylor seminorm).** $V=$ functions with an $n$th derivative at $a$:
$$
 N(f)=\sum_{k=0}^{n}\bigl|f^{(k)}(a)\bigr|.
$$
This is a seminorm (e.g. $N\bigl((x-a)^{n+1}\bigr)=0$).

**Example 2 (Interpolation seminorm).** For distinct points $x_{0},\dots,x_{n}\in[a,b]$:
$$
 N(f)=\sum_{k=0}^{n}\bigl|f(x_{k})\bigr|.
$$
Again a seminorm.

**Example 3 (Square / $L^{2}$ norm).** For $f$ continuous on $[a,b]$,
$$
 \|f\|_{2}=\biggl(\int_{a}^{b}|f(x)|^{2}\,dx\biggr)^{1/2}.\tag{15.2}
$$
This is a norm inherited from the inner product $(f,g)=\int_{a}^{b}f\bar g\,dx$.  On the larger space of merely integrable functions it is only a seminorm.

**Example 4 (Max / $L^{\infty}$ norm).** For $f$ continuous on $[a,b]$,
$$
 \|f\|_{\infty}=\max_{a\le x\le b}|f(x)|.
$$


### 15.4 Fundamental Problems in Polynomial Approximation

Let $C$ be continuous functions on $[a,b]$, $S$ the subspace of polynomials of degree $\le n$, and a norm $\|\cdot\|$ fixed on $C$.  A polynomial $P\in S$ is a **best approximation** to $f$ if
$$
 \|f-P\|\le\|f-Q\|\qquad\forall\,Q\in S.
$$
Three natural questions: **Existence**, **Uniqueness**, **Construction**.

**Taylor seminorm.** The best approximation is the Taylor polynomial
$$
 P(x)=\sum_{k=0}^{n}\frac{f^{(k)}(a)}{k!}(x-a)^{k},\tag{15.3}
$$
with $\|f-P\|=0$; uniqueness follows from Theorem 7.1 (Vol. I).

**Inner-product norms.** Theorem 1.16 guarantees a unique best approximation: the **orthogonal projection** of $f$ onto $S$,
$$
 P(x)=\sum_{k=0}^{n}(f,e_{k})\,e_{k}(x),
$$
where $\{e_{k}\}$ is an orthonormal basis of $S$.

*Example (Legendre polynomials on $[-1,1]$).* With $(f,g)=\int_{-1}^{1}fg\,dx$, the normalized Legendre polynomials $\varphi_{k}(x)=\sqrt{\frac{2k+1}{2}}\,P_{k}(x)$ form an orthonormal basis.  The projection of $f$ is
$$
 f_{n}(x)=\sum_{k=0}^{n}(f,\varphi_{k})\,\varphi_{k}(x),\qquad
 (f,\varphi_{k})=\int_{-1}^{1}f(t)\varphi_{k}(t)\,dt.
$$
The first six normalized polynomials are
$$
 \begin{aligned}
 \varphi_{0}&=\sqrt{\tfrac12}, &\varphi_{1}&=\sqrt{\tfrac32}\,x, &\varphi_{2}&=\tfrac12\sqrt{\tfrac52}(3x^{2}-1),\\
 \varphi_{3}&=\tfrac12\sqrt{\tfrac72}(5x^{3}-3x), &\varphi_{4}&=\tfrac18\sqrt{\tfrac92}(35x^{4}-30x^{2}+3), &\varphi_{5}&=\tfrac18\sqrt{\tfrac{11}{2}}(63x^{5}-70x^{3}+15x).
 \end{aligned}
$$

Interpolation seminorm → Section 15.6; max norm → later sections.

