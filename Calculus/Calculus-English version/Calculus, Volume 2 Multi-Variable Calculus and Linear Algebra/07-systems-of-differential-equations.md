# Chapter 7 — Systems of Differential Equations

### 7.1 Introduction

- Existence theory for higher-order equations can be reduced to the **first-order case** by introducing systems of equations.
- **Example.** The second-order equation $y''+2ty'-y=e^t$ is transformed by $y_1=y$, $y_2=y_1'$ into the system
  $$y_1'=y_2,\qquad y_2'=y_1-2ty_2+e^t.\tag{7.2}$$

**First-order linear system.** A system of $n$ equations in $n$ unknowns $y_1,\dots,y_n$:
$$\begin{aligned}
y_1'&=p_{11}(t)y_1+\cdots+p_{1n}(t)y_n+q_1(t)\\
&\;\vdots\\
y_n'&=p_{n1}(t)y_1+\cdots+p_{nn}(t)y_n+q_n(t).\end{aligned}\tag{7.3}$$

- Every $n$th-order linear equation $y^{(n)}+a_1y^{(n-1)}+\cdots+a_ny=R(t)$ can be converted to a system by setting $y_1=y$, $y_2=y_1'$, $\dots$, $y_n=y_{n-1}'$:
  $$\begin{aligned}
  y_1'&=y_2\\
  y_2'&=y_3\\
  &\;\vdots\\
  y_{n-1}'&=y_n\\
  y_n'&=-a_ny_1-a_{n-1}y_2-\cdots-a_1y_n+R(t).\end{aligned}\tag{7.5}$$

**Matrix notation.** With column vectors $Y=(y_1,\dots,y_n)^t$, $Q=(q_1,\dots,q_n)^t$ and matrix $P(t)=[p_{ij}(t)]$, the system becomes
$$Y'=P(t)Y+Q(t).\tag{7.6}$$

- Companion matrix for (7.5):
  $$P(t)=\begin{bmatrix}0&1&0&\cdots&0\\0&0&1&\cdots&0\\\vdots&\vdots&\vdots&&\vdots\\0&0&0&\cdots&1\\-a_n&-a_{n-1}&-a_{n-2}&\cdots&-a_1\end{bmatrix}.$$

**Initial-value problem.** Find $Y$ satisfying $Y'=P(t)Y+Q(t)$ and $Y(a)=B$.

- For the scalar case ($n=1$), Theorem 6.1 gives
  $$Y(x)=e^{A(x)}Y(a)+e^{A(x)}\int_a^x e^{-A(t)}Q(t)\,dt,\tag{7.7}$$
  where $A(x)=\int_a^x P(t)\,dt$.
- This formula will be generalized to matrix-valued $P$ and $Q$; we first need the calculus of matrix functions.


### 7.2 Calculus of Matrix Functions

Integration and differentiation of a matrix function are performed entrywise:
$$\int_a^b P(t)\,dt=\Bigl[\int_a^b p_{ij}(t)\,dt\Bigr],\qquad P'(t)=[p_{ij}'(t)].$$

- $P$ is continuous/differentiable at $t$ iff every entry is.
- Basic rules generalize:
  - $(P+Q)'=P'+Q'$
  - $(PQ)'=PQ'+P'Q$ (when defined)
  - Chain rule: if $F(t)=P[g(t)]$, then $F'(t)=g'(t)P'[g(t)]$.
- The zero-derivative theorem and the fundamental theorems of calculus also hold for matrix functions.

### 7.3 Infinite Series of Matrices and Norms

**Matrix exponential.** We require $e^{tA}e^{sA}=e^{(t+s)A}$ and $e^O=I$. Entrywise exponentiation $[e^{a_{ij}}]$ fails both, so we use the power series
$$e^A=\sum_{k=0}^\infty\frac{A^k}{k!}.$$

**Convergent series of matrices.** The series $\sum C_k$ converges iff every entry series $\sum c_{ij}^{(k)}$ converges; the sum is the matrix of entrywise sums.

**Matrix norm.** For $A=[a_{ij}]$,
$$\|A\|=\sum_{i=1}^m\sum_{j=1}^n|a_{ij}|.\tag{7.11}$$

**Theorem 7.1 (Fundamental properties).** For compatible matrices and scalars $c$:
$$\|A+B\|\le\|A\|+\|B\|,\qquad\|AB\|\le\|A\|\|B\|,\qquad\|cA\|=|c|\,\|A\|.$$

- By induction: $\|A^k\|\le\|A\|^k$ for $k=1,2,\dots$

**Theorem 7.2 (Convergence test).** If $\sum_{k=1}^\infty\|C_k\|$ converges, then the matrix series $\sum_{k=1}^\infty C_k$ converges.

- *Proof sketch:* $|c_{ij}^{(k)}|\le\|C_k\|$; convergence of $\sum\|C_k\|$ implies absolute (hence ordinary) convergence of every entry series.


### 7.5 The Exponential Matrix

Using Theorem 7.2, the series
$$\sum_{k=0}^\infty\frac{A^k}{k!}\tag{7.12}$$
converges for every square matrix $A$ because $\|A^k/k!\|\le\|A\|^k/k!$ and $\sum a^k/k!$ converges for all real $a$.

**Definition.** For any $n\times n$ matrix $A$,
$$e^A=\sum_{k=0}^\infty\frac{A^k}{k!}.$$

- $e^O=I$.

### 7.6 The Differential Equation Satisfied by $e^{tA}$

Let $E(t)=e^{tA}$.

**Theorem 7.3.** For every real $t$,
$$E'(t)=E(t)A=AE(t).$$

- *Proof sketch:* $E(t)=\sum_{k=0}^\infty t^kA^k/k!$. Differentiating term by term (valid since each entry is a power series convergent for all $t$) gives
  $$E'(t)=\sum_{k=0}^\infty\frac{t^kA^{k+1}}{k!}=\Bigl(\sum_{k=0}^\infty\frac{t^kA^k}{k!}\Bigr)A=E(t)A.$$
  Since $A$ commutes with $A^k$, we also have $E'(t)=AE(t)$.

- **Key consequence:** $A$ commutes with $e^{tA}$.


### 7.7 Uniqueness Theorem for $F'(t)=AF(t)$

**Theorem 7.4 (Nonsingularity).** For any $n\times n$ matrix $A$ and any scalar $t$,
$$e^{tA}e^{-tA}=I.\tag{7.14}$$
Hence $e^{tA}$ is nonsingular with inverse $e^{-tA}$.

- *Proof sketch:* Let $F(t)=e^{tA}e^{-tA}$. Then
  $$F'(t)=e^{tA}(-Ae^{-tA})+Ae^{tA}e^{-tA}=O,$$
  since $A$ commutes with $e^{tA}$. Thus $F$ is constant; $F(0)=I$, so $F(t)\equiv I$.

**Theorem 7.5 (Uniqueness).** Let $A$ and $B$ be constant $n\times n$ matrices. The only solution of
$$F'(t)=AF(t),\qquad F(0)=B$$
is
$$F(t)=e^{tA}B.\tag{7.15}$$

- *Proof sketch:* Set $G(t)=e^{-tA}F(t)$. Then $G'(t)=e^{-tA}AF(t)-Ae^{-tA}F(t)=O$, so $G(t)\equiv G(0)=B$. Multiplying by $e^{tA}$ gives $F(t)=e^{tA}B$.

- Similarly, $F(t)=Be^{tA}$ is the unique solution of $F'(t)=F(t)A$, $F(0)=B$.


### 7.8 The Law of Exponents for Exponential Matrices

$e^{A+B}=e^Ae^B$ is **not** always true for matrices (counterexample in Exercise 13, Section 7.12). It does hold when $A$ and $B$ commute.

**Theorem 7.6.** If $AB=BA$, then
$$e^{A+B}=e^Ae^B.\tag{7.16}$$

- *Proof sketch:* Commutativity implies $B$ commutes with every power of $A$, hence with $e^{tA}$. Set $F(t)=e^{t(A+B)}-e^{tA}e^{tB}$. Then
  $$F'(t)=(A+B)e^{t(A+B)}-Ae^{tA}e^{tB}-e^{tA}Be^{tB}=(A+B)F(t).$$
  By uniqueness, $F(t)=e^{t(A+B)}F(0)=O$, so $e^{t(A+B)}=e^{tA}e^{tB}$. Set $t=1$.

- **Example.** $e^{sA}e^{tA}=e^{(s+t)A}$ for all scalars $s,t$.

### 7.9 Existence and Uniqueness for Homogeneous Linear Systems with Constant Coefficients

**Theorem 7.7.** Let $A$ be a constant $n\times n$ matrix and $B$ a given $n$-dimensional vector. The initial-value problem
$$Y'(t)=AY(t),\qquad Y(0)=B\tag{7.17}$$
has a unique solution on $(-\infty,+\infty)$, given by
$$Y(t)=e^{tA}B.\tag{7.18}$$

- More generally, $Y(a)=B$ gives $Y(t)=e^{(t-a)A}B$.
- *Proof sketch:* Differentiation gives $Y'=Ae^{tA}B=AY$. For uniqueness, let $Z$ be another solution and set $G(t)=e^{-tA}Z(t)$; then $G'=O$, so $G(t)\equiv B$, hence $Z(t)=e^{tA}B=Y(t)$.


### 7.10 The Problem of Calculating $e^{tA}$

**Diagonal case.** If $A=\operatorname{diag}(\lambda_1,\dots,\lambda_n)$, then
$$e^{tA}=\operatorname{diag}(e^{t\lambda_1},\dots,e^{t\lambda_n}).$$

**Diagonalizable case.** If $C^{-1}AC=D$ with $D$ diagonal, then $A^k=CD^kC^{-1}$ and
$$e^{tA}=Ce^{tD}C^{-1}.$$

**Example 1.** $A=\begin{bmatrix}5&4\\1&2\end{bmatrix}$.
- Eigenvalues $\lambda_1=6$, $\lambda_2=1$.
- $C=\begin{bmatrix}4&-1\\1&1\end{bmatrix}$, $C^{-1}=\frac15\begin{bmatrix}1&1\\-1&4\end{bmatrix}$.
- $$e^{tA}=\frac15\begin{bmatrix}4e^{6t}+e^t&4e^{6t}-4e^t\\e^{6t}-e^t&e^{6t}+4e^t\end{bmatrix}.$$

**Example 2.** Solve $Y'=AY$ with $A=\begin{bmatrix}5&4\\1&2\end{bmatrix}$ and $Y(0)=\begin{bmatrix}2\\3\end{bmatrix}$.
- By Theorem 7.7, $Y(t)=e^{tA}Y(0)$.
- Solution: $y_1=4e^{6t}-2e^t$, $y_2=e^{6t}+2e^t$.

**When $A$ is not diagonalizable.** Most methods are complicated. A practical method valid for **all** matrices (due to E. J. Putzer, 1966) is based on the **Cayley–Hamilton theorem** — every square matrix satisfies its own characteristic equation. This will be discussed in later sections.


### 7.11 The Cayley–Hamilton Theorem

**Theorem 7.8.** Let $A$ be $n\times n$ and let
$$f(\lambda)=\det(\lambda I-A)=\lambda^n+c_{n-1}\lambda^{n-1}+\cdots+c_1\lambda+c_0\tag{7.19}$$
be its characteristic polynomial. Then $f(A)=O$; i.e.
$$A^n+c_{n-1}A^{n-1}+\cdots+c_1A+c_0I=O.\tag{7.20}$$

- *Proof sketch:* From $(\lambda I-A)\{\operatorname{cof}(\lambda I-A)\}^t=f(\lambda)I$ and the fact that $\{\operatorname{cof}(\lambda I-A)\}^t=\sum_{k=0}^{n-1}\lambda^kB_k$, equate coefficients of like powers of $\lambda$ to obtain the system (7.25). Multiply these equations by $A^n,A^{n-1},\dots,I$ and add; all terms on the left cancel, leaving $O=f(A)$.

- **Application:** Every power $A^m$ ($m\ge n$) can be expressed as a polynomial in $A$ of degree $<n$.
- If $c_0\neq0$ (i.e. $A$ is invertible), $A^{-1}$ is also a polynomial in $A$:
  $$A^{-1}=-\frac1{c_0}(A^{n-1}+c_{n-1}A^{n-2}+\cdots+c_1I).$$

**Example.** $A=\begin{bmatrix}5&4&0\\1&2&0\\1&2&2\end{bmatrix}$ has $f(\lambda)=\lambda^3-9\lambda^2+20\lambda-12$.
- Hence $A^3=9A^2-20A+12I$, $A^4=61A^2-168A+108I$, etc.
- Inverse: $A^{-1}=\frac1{12}(A^2-9A+20I)$.
