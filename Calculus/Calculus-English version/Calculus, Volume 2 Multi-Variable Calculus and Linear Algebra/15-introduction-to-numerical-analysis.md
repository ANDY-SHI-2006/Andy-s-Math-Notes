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


### 15.6 Interpolating Polynomials

Given $f$ at $n+1$ distinct points $x_{0},\dots,x_{n}$, find $P$ of degree $\le n$ with
$$
 P(x_{k})=f(x_{k})\qquad(k=0,\dots,n).\tag{15.4}
$$
Such a $P$ is the best approximation in the interpolation seminorm (distance $=0$).

**Theorem 15.1 (Uniqueness).** If $P,Q$ have degree $\le n$ and agree at $n+1$ distinct points, then $P\equiv Q$.

*Proof.* $R=P-Q$ is a polynomial of degree $\le n$ with $n+1$ distinct zeros, hence $R\equiv0$. ∎

**Lagrange construction.** Set
$$
 A(x)=\prod_{j=0}^{n}(x-x_{j}),\qquad
 A_{k}(x)=\prod_{\substack{j=0\\j\neq k}}^{n}(x-x_{j}).\tag{15.5–15.6}
$$
Then $A_{k}(x_{k})=\prod_{j\neq k}(x_{k}-x_{j})\neq0$.

**Theorem 15.2 (Existence).** The unique interpolating polynomial is
$$
 P(x)=\sum_{k=0}^{n}\frac{f(x_{k})A_{k}(x)}{A_{k}(x_{k})}.\tag{15.8}
$$

**Lagrange interpolation formula.** Writing $L_{k}(x)=A_{k}(x)/A_{k}(x_{k})$,
$$
 P(x)=\sum_{k=0}^{n}f(x_{k})L_{k}(x),\qquad
 L_{k}(x)=\prod_{\substack{j=0\\j\neq k}}^{n}\frac{x-x_{j}}{x_{k}-x_{j}}.\tag{15.9–15.10}
$$
Equivalently $L_{k}(x)=A_{k}(x)/A'(x_{k})$ because $A'(x_{k})=A_{k}(x_{k})$.

**Example.** Interpolate values $y_{0},y_{1},y_{2},y_{3}$ at $-2,-1,1,2$:
$$
 \begin{aligned}
 L_{0}&=-\tfrac1{12}(x+1)(x-1)(x-2), &
 L_{1}&=\hphantom{-}\tfrac16(x+2)(x-1)(x-2),\\
 L_{2}&=-\tfrac16(x+2)(x+1)(x-2), &
 L_{3}&=\hphantom{-}\tfrac1{12}(x+2)(x+1)(x-1).
 \end{aligned}
$$
Then $P(x)=y_{0}L_{0}(x)+y_{1}L_{1}(x)+y_{2}L_{2}(x)+y_{3}L_{3}(x)$.


### 15.7 Equally Spaced Interpolation Points

Let $x_{j}=x_{0}+jh$ ($j=0,\dots,n$) with spacing $h>0$, and set $t=(x-x_{0})/h$.  The Lagrange coefficients (15.10) become
$$
 L_{k}(x)=\prod_{\substack{j=0\\j\neq k}}^{n}\frac{t-j}{\,k-j\,}.\tag{15.11}
$$
The product of the $t$‑independent factors simplifies to
$$
 \prod_{\substack{j=0\\j\neq k}}^{n}\frac1{k-j}
 =\frac{(-1)^{n-k}}{n!}\binom{n}{k},\tag{15.12}
$$
so
$$
 L_{k}(x_{0}+th)=\frac{(-1)^{n-k}}{n!}\binom{n}{k}\prod_{\substack{j=0\\j\neq k}}^{n}(t-j).\tag{15.13}
$$
For tabulated values of $t$, $P(x_{0}+th)$ is obtained by multiplying the $f(x_{k})$ by the tabulated $L_{k}$ and adding.

---

### 15.8 Error Analysis in Polynomial Interpolation

**Theorem 15.3.** Let $x_{0},\dots,x_{n}$ be distinct points in the domain of $f$, $P$ the interpolating polynomial of degree $\le n$, and $x$ any point.  If $f$ has an $(n+1)$st derivative on a closed interval $[\alpha,\beta]$ containing all $x_{k}$ and $x$, then for some $c\in(\alpha,\beta)$,
$$
 f(x)-P(x)=\frac{A(x)}{(n+1)!}\,f^{(n+1)}(c),\qquad
 A(x)=\prod_{j=0}^{n}(x-x_{j}).\tag{15.14}
$$

*Proof sketch.*  Set $F(t)=A(x)[f(t)-P(t)]-A(t)[f(x)-P(x)]$.  Then $F$ vanishes at $x_{0},\dots,x_{n}$ and at $x$, giving $n+2$ zeros in $[\alpha,\beta]$.  Applying Rolle’s theorem $n+1$ times yields $c$ with $F^{(n+1)}(c)=0$; using $A^{(n+1)}=(n+1)!$ gives (15.14). ∎

**Equally spaced case.** With $x_{j}=x_{0}+jh$ and $t=(x-x_{0})/h$,
$$
 f(x)-P(x)=\frac{f^{(n+1)}(c)}{(n+1)!}\,h^{n+1}\prod_{j=0}^{n}(t-j).\tag{15.17}
$$

**Example (Linear interpolation, $n=1$).**
$$
 f(x)-P(x)=\frac{f''(c)}{2}\,h^{2}t(t-1),\qquad t=\frac{x-x_{0}}{h}.\tag{15.18}
$$
For $x\in[x_{0},x_{0}+h]$ ($0<t<1$), $\max|t(t-1)|=\tfrac14$, so
$$
 |f(x)-P(x)|\le\frac{Mh^{2}}{8},\qquad M=\max_{[x_{0},x_{0}+h]}|f''|.
$$
For sines/cosines ($M\le1$) with one‑degree tables ($h=\pi/180$), $h^{2}/8<0.00004$; hence linear interpolation is adequate in four‑place tables.


### 15.10 Newton’s Interpolation Formula

Lagrange’s formula for the interpolating polynomial $P_{n}$ of degree $\le n$ is
$$
 P_{n}(x)=\sum_{k=0}^{n}L_{k}(x)f(x_{k}),\qquad
 L_{k}(x)=\prod_{\substack{j=0\\j\neq k}}^{n}\frac{x-x_{j}}{x_{k}-x_{j}}.\tag{15.19}
$$
Adding a new point $x_{n+1}$ with Lagrange requires recomputing *all* coefficients as degree-$n+1$ polynomials.

**Theorem 15.4.** Given $x_{0},\dots,x_{n+1}$ distinct, let $P_{n}$ agree with $f$ at $x_{0},\dots,x_{n}$ and $P_{n+1}$ agree with $f$ at $x_{0},\dots,x_{n+1}$.  Then there is a unique constant $c_{n+1}$ such that
$$
 P_{n+1}(x)=P_{n}(x)+c_{n+1}(x-x_{0})\cdots(x-x_{n}).\tag{15.20}
$$
*Proof sketch.*  $Q(x)=P_{n}(x)+c(x-x_{0})\cdots(x-x_{n})$ already agrees with $f$ at $x_{0},\dots,x_{n}$; choose $c$ so that $Q(x_{n+1})=f(x_{n+1})$. ∎

**Theorem 15.5 (Newton’s interpolation formula).** For distinct $x_{0},\dots,x_{n}$,
$$
 P_{n}(x)=f(x_{0})+\sum_{k=1}^{n}c_{k}(x-x_{0})\cdots(x-x_{k-1}).\tag{15.21}
$$
*Proof by induction using (15.20).*  The key advantage: $P_{n+1}$ is obtained from $P_{n}$ by adding one new term.

**Theorem 15.6 (Coefficients).** The leading coefficient $c_{n}$ is
$$
 c_{n}=\sum_{k=0}^{n}\frac{f(x_{k})}{A_{k}(x_{k})},\qquad
 A_{k}(x_{k})=\prod_{\substack{j=0\\j\neq k}}^{n}(x_{k}-x_{j}).\tag{15.22}
$$
*Proof.*  In Lagrange’s formula the coefficient of $x^{n}$ is $\sum f(x_{k})/A_{k}(x_{k})$; in Newton’s formula it is $c_{n}$. ∎


### 15.11 Equally Spaced Points — The Forward Difference Operator

For $x_{k}=x_{0}+kh$ ($k=0,\dots,n$), Equation (15.12) gives
$$
 \frac1{A_{k}(x_{k})}=\frac{(-1)^{n-k}}{n!\,h^{n}}\binom{n}{k},
$$
so the Newton coefficient (15.23) becomes
$$
 c_{n}=\frac1{n!\,h^{n}}\sum_{k=0}^{n}(-1)^{n-k}\binom{n}{k}f(x_{k}).\tag{15.23}
$$

**Definition (Forward difference).** For fixed $h$,
$$
 \Delta f(x)=f(x+h)-f(x),\qquad \Delta^{k+1}f=\Delta(\Delta^{k}f),\qquad \Delta^{0}f=f.
$$
In general,
$$
 \Delta^{n}f(x)=\sum_{k=0}^{n}(-1)^{n-k}\binom{n}{k}f(x+kh).\tag{15.24}
$$
Hence, from (15.23)–(15.24),
$$
 c_{n}=\frac{\Delta^{n}f(x_{0})}{n!\,h^{n}}.
$$

**Newton’s formula with differences.** Equation (15.21) becomes
$$
 P_{n}(x)=f(x_{0})+\sum_{k=1}^{n}\frac{\Delta^{k}f(x_{0})}{k!\,h^{k}}\prod_{j=0}^{k-1}(x-x_{j}),\tag{15.25}
$$
and, with $t=(x-x_{0})/h$,
$$
 P_{n}(x)=f(x_{0})+\sum_{k=1}^{n}\frac{\Delta^{k}f(x_{0})}{k!}\prod_{j=0}^{k-1}(t-j).\tag{15.26}
$$


### 15.12 Factorial Polynomials

The product $t(t-1)\cdots(t-k+1)$ is the **factorial $k$th power**, denoted $t^{(k)}$:
$$
 t^{(k)}=\prod_{j=0}^{k-1}(t-j),\qquad t^{(0)}=1.
$$
With $h=1$, the forward difference operator satisfies
$$
 \Delta t^{(n)}=n\,t^{(n-1)}\qquad(n\ge1),
$$
analogous to $D(t^{n})=n t^{n-1}$.  Newton’s formula (15.26) becomes
$$
 P_{n}(x_{0}+th)=\sum_{k=0}^{n}\frac{\Delta^{k}f(x_{0})}{k!}\,t^{(k)}
 =\sum_{k=0}^{n}\binom{t}{k}\,\Delta^{k}f(x_{0}).
$$

---

### 15.14 A Minimum Problem Relative to the Max Norm

From the interpolation error (Theorem 15.3),
$$
 f(x)-P(x)=\frac{A(x)}{(n+1)!}\,f^{(n+1)}(c),\qquad
 A(x)=\prod_{j=0}^{n}(x-x_{j}).\tag{15.27}
$$
To minimize the error bound one wants to minimize
$$
 \|A\|_{\infty}=\max_{a\le x\le b}|A(x)|
$$
by an appropriate choice of the nodes $x_{0},\dots,x_{n}$.  This problem was first solved by Chebyshev and leads to the **Chebyshev polynomials**.


### 15.15 Chebyshev Polynomials

**Definition.** The **Chebyshev polynomial of the first kind** $T_{n}(x)$ is defined by
$$
 T_{n}(x)=\sum_{k=0}^{\lfloor n/2\rfloor}\binom{n}{2k}x^{n-2k}(x^{2}-1)^{k}.
$$
It arises from the real part of $(\cos\theta+i\sin\theta)^{n}$ after setting $x=\cos\theta$.

**Theorem 15.7.** For $-1\le x\le1$,
$$
 T_{n}(x)=\cos(n\arccos x).
$$

**Theorem 15.8 (Recursion).** $T_{0}(x)=1$, $T_{1}(x)=x$, and
$$
 T_{n+1}(x)=2x\,T_{n}(x)-T_{n-1}(x)\qquad(n\ge1).
$$
*Proof sketch.*  Set $x=\cos\theta$ in $\cos(n+1)\theta+\cos(n-1)\theta=2\cos\theta\cos n\theta$; equality of polynomials extends it to all $x$. ∎

The first few:
$$
 \begin{aligned}
 T_{2}&=2x^{2}-1, & T_{3}&=4x^{3}-3x, & T_{4}&=8x^{4}-8x^{2}+1,\\
 T_{5}&=16x^{5}-20x^{3}+5x, & T_{6}&=32x^{6}-48x^{4}+18x^{2}-1.
 \end{aligned}
$$
All coefficients are integers; the leading coefficient of $T_{n}$ is $2^{n-1}$.

**Theorem 15.9 (Zeros).** $T_{n}$ has $n$ simple zeros in $(-1,1)$:
$$
 x_{k}=\cos\frac{(2k+1)\pi}{2n},\qquad k=0,\dots,n-1.
$$
Hence
$$
 T_{n}(x)=2^{n-1}\prod_{k=0}^{n-1}\Bigl(x-\cos\tfrac{(2k+1)\pi}{2n}\Bigr).
$$

**Theorem 15.10 (Extrema).** On $[-1,1]$ the extreme values of $T_{n}$ are $\pm1$, taken alternately at the $n+1$ points
$$
 t_{k}=\cos\frac{k\pi}{n},\qquad k=0,\dots,n.\tag{15.30}
$$


### 15.16 A Minimal Property of Chebyshev Polynomials

**Theorem 15.11.** Let $p_{n}(x)=x^{n}+\cdots$ be any monic polynomial of degree $n\ge1$ and let $\|p_{n}\|=\max_{[-1,1]}|p_{n}|$.  Then
$$
 \|p_{n}\|\ge\|\tilde T_{n}\|,\qquad\tilde T_{n}(x)=\frac{T_{n}(x)}{2^{n-1}},\tag{15.31}
$$
with equality iff $p_{n}=\tilde T_{n}$.  (Thus $\|\tilde T_{n}\|=1/2^{n-1}$.)

*Proof sketch.*  Assume $\|p_{n}\|<1/2^{n-1}$ and set $r=\tilde T_{n}-p_{n}$.  At the $n+1$ extreme points $t_{k}=\cos(k\pi/n)$ the values $r(t_{k})$ alternate in sign, so $r$ has at least $n$ zeros; but $\deg r\le n-1$, forcing $r\equiv0$, a contradiction. ∎

**Theorem 15.12 (General interval).** For $q_{n}(x)=c_{n}x^{n}+\cdots$ on $[a,b]$,
$$
 \|q_{n}\|\ge|c_{n}|\,\frac{(b-a)^{n}}{2^{2n-1}},\tag{15.33}
$$
with equality for
$$
 q_{n}(x)=c_{n}\frac{(b-a)^{n}}{2^{2n-1}}\,T_{n}\!\Bigl(\frac{2x-a-b}{\,b-a\,}\Bigr).
$$
*Proof.*  Map $[a,b]$ to $[-1,1]$ by $t=(2x-a-b)/(b-a)$ and apply Theorem 15.11. ∎

---

### 15.17 Application to the Interpolation Error

Choosing the nodes $x_{0},\dots,x_{n}$ as the zeros of $T_{n+1}$,
$$
 x_{k}=\cos\Bigl(\frac{2k+1}{n+1}\frac{\pi}{2}\Bigr)\quad(k=0,\dots,n),
$$
gives $A(x)=T_{n+1}(x)/2^{n}$ and the error formula (15.27) becomes
$$
 f(x)-P(x)=\frac{T_{n+1}(x)}{2^{n}(n+1)!}\,f^{(n+1)}(c).
$$
Since $|T_{n+1}(x)|\le1$ on $[-1,1]$,
$$
 |f(x)-P(x)|\le\frac{1}{2^{n}(n+1)!}\,\bigl|f^{(n+1)}(c)\bigr|.
$$
For a general interval $[a,b]$ with transformed nodes $y_{k}=\frac{b-a}{2}x_{k}+\frac{a+b}{2}$,
$$
 |f(x)-P(x)|\le\frac{(b-a)^{n+1}}{2^{2n+1}(n+1)!}\,\bigl|f^{(n+1)}(c)\bigr|.
$$


### 15.19 Approximate Integration — The Trapezoidal Rule

Partition $[a,b]$ into $n$ equal subintervals of length $h=(b-a)/n$; set $x_{k}=a+kh$.  On $[x_{k},x_{k+1}]$ approximate $f$ by the linear interpolant
$$
 P(x)=\frac{x_{k+1}-x}{h}\,f(x_{k})+\frac{x-x_{k}}{h}\,f(x_{k+1}).\tag{15.34}
$$
Integrating $P$ over $[x_{k},x_{k+1}]$ gives the trapezoid area $h\bigl[f(x_{k})+f(x_{k+1})\bigr]/2$; summing over all subintervals yields
$$
 \int_{a}^{b}P(x)\,dx=\frac{h}{2}\Bigl(f(a)+2\sum_{k=1}^{n-1}f(a+kh)+f(b)\Bigr).\tag{15.35}
$$

**Theorem 15.13 (Trapezoidal rule).** If $f\in C^{2}[a,b]$ and $h=(b-a)/n$, then for some $c\in[a,b]$,
$$
 \int_{a}^{b}f(x)\,dx=\frac{b-a}{2n}\Bigl(f(a)+2\sum_{k=1}^{n-1}f(a+kh)+f(b)\Bigr)-\frac{(b-a)^{3}}{12n^{2}}\,f''(c).\tag{15.36}
$$

*Proof sketch.*  On each subinterval Theorem 15.3 gives $f(x)-P(x)=(x-x_{k})(x-x_{k+1})f''(c_{k})/2$.  Since $(x-x_{k})(x_{k+1}-x)\ge0$ on $[x_{k},x_{k+1}]$, integrating and using the intermediate-value property of $f''$ produces the error term $-nh^{3}f''(c)/12=-(b-a)^{3}f''(c)/(12n^{2})$. ∎


### 15.20 Simpson’s Rule

Approximate $f$ on $[a,b]$ by the quadratic $P$ agreeing with $f$ at $a$, $m=(a+b)/2$, and $b$.  With the change of variable $t=(x-a)/(m-a)$ ($t=0,1,2$ at $a,m,b$) and Newton’s formula,
$$
 \int_{a}^{b}P(x)\,dx=\frac{b-a}{2}\int_{0}^{2}\!\varphi(t)\,dt
 =\frac{b-a}{6}\bigl[P(a)+4P(m)+P(b)\bigr].\tag{15.39–15.40}
$$

**Key observation.** The error $R=\int_{a}^{b}[f(x)-P(x)]\,dx$ is *zero* not only for quadratics but also for **cubics**, because the odd integrand $t^{3}-h^{2}t$ integrates to $0$ over a symmetric interval.

**Theorem 15.14 (Simpson’s rule).** If $f\in C^{4}[a,b]$ and $m=(a+b)/2$, then for some $c\in[a,b]$,
$$
 \int_{a}^{b}f(x)\,dx=\frac{b-a}{6}\bigl[f(a)+4f(m)+f(b)\bigr]-\frac{(b-a)^{5}}{2880}\,f^{(4)}(c).\tag{15.43}
$$

*Proof sketch.*  Enforce the extra condition $P'(m)=f'(m)$, which yields the error representation
$$
 f(x)-P(x)=(x-a)(x-m)^{2}(x-b)\,\frac{f^{(4)}(z)}{4!}\tag{15.42}
$$
for some $z\in(a,b)$.  Set $B(x)=-(x-a)(x-m)^{2}(x-b)/4!\;(\ge0)$, integrate (15.42), and use the intermediate-value property of $f^{(4)}$.  Since $\int_{a}^{b}B(x)\,dx=(b-a)^{5}/2880$, (15.43) follows. ∎

**Theorem 15.15 (Extended Simpson’s rule).** With $h=(b-a)/(2n)$ and $f_{k}=f(a+kh)$,
$$
 \int_{a}^{b}f(x)\,dx=\frac{b-a}{6n}\Bigl(f(a)+4\sum_{k=1}^{n}f_{2k-1}+2\sum_{k=1}^{n-1}f_{2k}+f(b)\Bigr)-\frac{(b-a)^{5}}{2880n^{4}}\,f^{(4)}(\bar c).
$$

