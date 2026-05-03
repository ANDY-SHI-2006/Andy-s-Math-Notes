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

