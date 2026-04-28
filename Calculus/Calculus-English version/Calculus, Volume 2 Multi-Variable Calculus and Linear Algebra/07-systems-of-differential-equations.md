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


### 7.13 Putzer's Method for Calculating $e^{tA}$

By Cayley–Hamilton, every power $A^k$ ($k\ge n$) is a linear combination of $I,A,\dots,A^{n-1}$. Hence $e^{tA}$ can be written as a polynomial in $A$:
$$e^{tA}=\sum_{k=0}^{n-1}q_k(t)A^k.\tag{7.27}$$

**Theorem 7.9 (Putzer).** Let $\lambda_1,\dots,\lambda_n$ be the eigenvalues of $A$. Define
$$P_0(A)=I,\qquad P_k(A)=\prod_{m=1}^{k}(A-\lambda_m I),\quad k=1,\dots,n.\tag{7.28}$$
Then
$$e^{tA}=\sum_{k=0}^{n-1}r_{k+1}(t)P_k(A),\tag{7.29}$$
where the scalar functions $r_1,\dots,r_n$ satisfy the triangular linear system
$$\begin{cases}
r_1'(t)=\lambda_1 r_1(t), & r_1(0)=1,\\[4pt]
r_{k+1}'(t)=\lambda_{k+1}r_{k+1}(t)+r_k(t), & r_{k+1}(0)=0,\quad k=1,\dots,n-1.
\end{cases}\tag{7.30}$$

- The system (7.30) is triangular, so it is solved in succession.
- The polynomials $P_k(A)$ are easy to compute once eigenvalues are known.
- *Proof sketch:* Define $F(t)$ by the RHS of (7.29). Show $F(0)=I$ and $F'(t)=AF(t)$ using the recursion (7.28) and $P_n(A)=O$ (Cayley–Hamilton). Uniqueness gives $F(t)=e^{tA}$.

**Example 1** ($2\times2$, repeated eigenvalue $\lambda$). Solve (7.30):
- $r_1(t)=e^{\lambda t}$, $r_2(t)=te^{\lambda t}$.
- $P_0=I$, $P_1=A-\lambda I$.
- $$e^{tA}=e^{\lambda t}I+te^{\lambda t}(A-\lambda I)=e^{\lambda t}(1-\lambda t)I+te^{\lambda t}A.\tag{7.33}$$

**Example 2** ($2\times2$, distinct eigenvalues $\lambda\neq\mu$). Solve (7.30):
- $r_1(t)=e^{\lambda t}$, $r_2(t)=\dfrac{e^{\lambda t}-e^{\mu t}}{\lambda-\mu}$.
- $$e^{tA}=\frac{\lambda e^{\mu t}-\mu e^{\lambda t}}{\lambda-\mu}\,I+\frac{e^{\lambda t}-e^{\mu t}}{\lambda-\mu}\,A.\tag{7.34}$$

**Complex conjugate pair** $\lambda=\alpha+i\beta$, $\mu=\alpha-i\beta$ ($\beta\neq0$). From (7.34) the imaginary parts cancel, giving a real formula:
$$e^{tA}=\frac{e^{\alpha t}}{\beta}\bigl[(\beta\cos\beta t-\alpha\sin\beta t)\,I+\sin\beta t\,A\bigr].\tag{7.35}$$


### 7.14 Alternate Methods for Calculating $e^{tA}$ in Special Cases

**Theorem 7.10** (all eigenvalues equal to $\lambda$).
$$e^{tA}=e^{\lambda t}\sum_{k=0}^{n-1}\frac{t^k}{k!}(A-\lambda I)^k.\tag{7.36}$$
- *Proof sketch:* $e^{tA}=e^{\lambda tI}e^{t(A-\lambda I)}$. The series for $e^{t(A-\lambda I)}$ truncates at $k=n-1$ because $(A-\lambda I)^n=O$ by Cayley–Hamilton.

**Theorem 7.11** ($n$ distinct eigenvalues $\lambda_1,\dots,\lambda_n$).
$$e^{tA}=\sum_{k=1}^{n}e^{t\lambda_k}L_k(A),\qquad
L_k(A)=\prod_{\substack{j=1\\j\neq k}}^{n}\frac{A-\lambda_j I}{\lambda_k-\lambda_j}.$$
- The $L_k(A)$ are **Lagrange interpolation coefficients**.
- *Proof sketch:* Define $F(t)$ by the RHS; verify $F'=AF$ using $(A-\lambda_k I)L_k(A)=O$, and $F(0)=I$ via $\sum_k L_k(A)=I$.

**Theorem 7.12** (two distinct eigenvalues, $\lambda$ mult. $n-1$, $\mu$ mult. $1$, $n\ge 3$).
$$e^{tA}=e^{\lambda t}\sum_{k=0}^{n-2}\frac{t^k}{k!}(A-\lambda I)^k
+\left\{\frac{e^{\mu t}}{(\mu-\lambda)^{n-1}}-\frac{e^{\lambda t}}{(\mu-\lambda)^{n-1}}\sum_{k=0}^{n-2}\frac{t^k}{k!}(\mu-\lambda)^k\right\}(A-\lambda I)^{n-1}.$$
- *Proof sketch:* Expand $e^{t(A-\lambda I)}$; for $k\ge n-1$ use $(A-\lambda I)^{n-1+r}=(\mu-\lambda)^r(A-\lambda I)^{n-1}$ (from Cayley–Hamilton) and sum the remaining exponential series.

**Formulas for $3\times3$ matrices.**

| Case | Eigenvalues | Formula |
|------|-------------|---------|
| 1 | $\lambda,\lambda,\lambda$ | $e^{tA}=e^{\lambda t}\bigl[I+t(A-\lambda I)+\tfrac12t^2(A-\lambda I)^2\bigr]$ |
| 2 | $\lambda,\mu,\nu$ (distinct) | $e^{tA}=\sum e^{\lambda_i t}\dfrac{\prod_{j\neq i}(A-\lambda_j I)}{\prod_{j\neq i}(\lambda_i-\lambda_j)}$ |
| 3 | $\lambda,\lambda,\mu$ | $e^{tA}=e^{\lambda t}[I+t(A-\lambda I)]+\dfrac{e^{\mu t}-e^{\lambda t}}{(\mu-\lambda)^2}(A-\lambda I)^2-\dfrac{te^{\lambda t}}{\mu-\lambda}(A-\lambda I)^2$ |

**Example.** $A=\begin{bmatrix}0&1&0\\0&0&1\\2&-5&4\end{bmatrix}$ has eigenvalues $1,1,2$ (Case 3).
$$e^{tA}=e^t\{I+t(A-I)\}+(e^{2t}-e^t)(A-I)^2-te^t(A-I)^2.\tag{7.39}$$
Collecting powers of $A$:
$$e^{tA}=(-2te^t+e^{2t})I+\{(3t+2)e^t-2e^{2t}\}A-\{(t+1)e^t-e^{2t}\}A^2.\tag{7.40}$$
