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


### 7.16 Nonhomogeneous Linear Systems with Constant Coefficients

Consider the nonhomogeneous initial-value problem
$$Y'(t)=AY(t)+Q(t),\qquad Y(a)=B.\tag{7.41}$$

Multiply (7.41) by $e^{-tA}$; the left side becomes $\dfrac{d}{dt}[e^{-tA}Y(t)]$:
$$\frac{d}{dt}\bigl[e^{-tA}Y(t)\bigr]=e^{-tA}Q(t).\tag{7.42}$$
Integrate from $a$ to $x$ and multiply by $e^{xA}$.

**Theorem 7.13.** Let $A$ be constant and $Q$ continuous on an interval $J$. Then (7.41) has the unique solution on $J$:
$$Y(x)=e^{(x-a)A}B+e^{xA}\int_a^x e^{-tA}Q(t)\,dt.\tag{7.43}$$

- First term: solution of the homogeneous problem $Y'=AY$, $Y(a)=B$.
- Second term: particular solution of the nonhomogeneous problem with $Y(a)=O$.

**Example.** Solve $Y'=AY+Q(t)$, $Y(0)=O$ on $(-\infty,+\infty)$ with
$$A=\begin{bmatrix}2&-1&1\\0&3&-1\\2&1&3\end{bmatrix},\quad Q(t)=\begin{bmatrix}e^{2t}\\0\\te^{2t}\end{bmatrix}.$$

Since $B=O$, (7.43) gives $Y(x)=\displaystyle\int_0^x e^{(x-t)A}Q(t)\,dt$.

Eigenvalues of $A$ are $2,2,4$ (Case 3 of §7.14):
$$e^{xA}=e^{2x}\Bigl\{I+x(A-2I)+\tfrac14(e^{2x}-2x-1)(A-2I)^2\Bigr\}.$$

After computing $e^{(x-t)A}Q(t)$, integrating term by term, and substituting
$$A-2I=\begin{bmatrix}0&-1&1\\0&1&-1\\2&1&1\end{bmatrix},\qquad (A-2I)^2=\begin{bmatrix}2&0&2\\-2&0&-2\\2&0&2\end{bmatrix},$$
the result is
$$Y(x)=e^{2x}\begin{bmatrix}\frac38e^{2x}-\frac38+\frac14x-\frac34x^2\\[4pt]-\frac38e^{2x}+\frac38+\frac34x+\frac34x^2\\[4pt]\frac38e^{2x}-\frac38-\frac34x+\frac34x^2\end{bmatrix}.$$
The rows are $y_1,y_2,y_3$.


### 7.18 The General Linear System $Y'(t)=P(t)Y(t)+Q(t)$

We now allow $P(t)$ to be non-constant. The system is
$$Y'(t)=P(t)Y(t)+Q(t),\qquad Y(a)=B.\tag{7.45}$$

**Scalar case ($n=1$).** Let $A(x)=\int_a^x P(t)\,dt$; multiply by $e^{-A(t)}$:
$$\frac{d}{dt}\bigl[e^{-A(t)}Y(t)\bigr]=e^{-A(t)}Q(t).$$
Integrate and multiply by $e^{A(x)}$:
$$Y(x)=e^{A(x)}e^{-A(a)}Y(a)+e^{A(x)}\int_a^x e^{-A(t)}Q(t)\,dt.\tag{7.47}$$

**Matrix difficulty.** The formula $\frac{d}{dt}e^{A(t)}=A'(t)e^{A(t)}$ is **not** always valid for matrix functions (e.g. $A(t)=\begin{smallmatrix}1&t\\0&0\end{smallmatrix}$). So (7.47) does not generalise directly.

**Modified argument.** Multiply (7.45) by an unknown matrix $F(t)$ and add $F'(t)Y(t)$:
$$\{F(t)Y(t)\}'=\{F'(t)+F(t)P(t)\}Y(t)+F(t)Q(t).$$
Choose $F$ so that $F'(t)+F(t)P(t)=O$, i.e.
$$F'(t)=-F(t)P(t).\tag{7.49}$$
Then $\{F(t)Y(t)\}'=F(t)Q(t)$, and if $F$ is nonsingular,
$$Y(x)=F(x)^{-1}F(a)Y(a)+F(x)^{-1}\int_a^x F(t)Q(t)\,dt.\tag{7.48}$$

**Theorem 7.14** (existence for homogeneous systems). If $A(t)$ is continuous on an open interval $J$, then $Y'=A(t)Y$, $Y(a)=B$ has a solution on $J$. (Proof deferred to §7.21.)

**Theorem 7.15.** Given $P$ continuous on $J$ and $a\in J$, there exists a nonsingular matrix function $F$ satisfying (7.49) with $F(a)=I$.
- *Proof sketch:* Solve $Y_k'=-P(x)^tY_k$, $Y_k(a)=I_k$ for each column $k$; let $G$ be the matrix with columns $Y_k$. Then $G'=-P^tG$, $G(a)=I$. Set $F=G^t$; then $F'=-FP$ and $F(a)=I$. Nonsingularity follows by constructing $H$ with $H'=PH$, $H(a)=I$; then $(FH)'=O$, so $FH=I$.

**Theorem 7.16.** Given $P$, $Q$ continuous on an open interval $J$, the solution of (7.51) is
$$Y(x)=F(x)^{-1}Y(a)+F(x)^{-1}\int_a^x F(t)Q(t)\,dt,\tag{7.52}$$
where $F(x)$ is the transpose of the matrix whose $k$th column solves
$$Y'(x)=-P(x)^tY(x),\qquad Y(a)=I_k.\tag{7.53}$$

- Note: finding $F$ requires solving $n$ homogeneous linear systems, so the formula is mainly of theoretical value.


### 7.19 A Power-Series Method for Solving Homogeneous Linear Systems

Consider the homogeneous system
$$Y'(x)=A(x)Y(x),\qquad Y(0)=B,\tag{7.54}$$
where $A(x)$ has a power-series expansion convergent for $|x|<r_1$:
$$A(x)=A_0+xA_1+x^2A_2+\cdots+x^kA_k+\cdots.$$

Seek a solution of the same form:
$$Y(x)=B_0+xB_1+x^2B_2+\cdots+x^kB_k+\cdots.$$

Equating coefficients of like powers of $x$ gives the recursion
$$B_1=A_0B,\qquad (k+1)B_{k+1}=\sum_{r=0}^{k}A_rB_{k-r}\quad(k=1,2,\dots).\tag{7.55}$$

- The vectors $B_1,B_2,\dots$ are determined in succession.
- If the resulting series converges for $|x|<r_2$, it solves (7.54) for $|x|<r$ where $r=\min\{r_1,r_2\}$.

**Constant-coefficient case.** If $A(x)=A$ (constant), then $A_0=A$ and $A_k=O$ for $k\ge 1$. The recursion reduces to
$$B_1=AB,\qquad (k+1)B_{k+1}=AB_k\quad(k\ge 1),$$
giving $B_k=\dfrac{1}{k!}A^kB$. Hence
$$Y(x)=B+\sum_{k=1}^{\infty}\frac{x^k}{k!}A^kB=e^{xA}B,$$
which agrees with the earlier result for constant-coefficient systems.


### 7.21 Proof of the Existence Theorem by Successive Approximations

Consider the homogeneous system
$$Y'(t)=A(t)Y(t),\qquad Y(a)=B,\tag{7.56}$$
with $A(t)$ continuous on an open interval $J$.

**Method of successive approximations (Picard).** Define
$$Y_0(x)=B,\qquad Y_{k+1}(x)=B+\int_a^x A(t)Y_k(t)\,dt\quad(k=0,1,2,\dots).\tag{7.58}$$

**Example (constant $A$).** $Y_k(x)=\bigl(\sum_{r=0}^k (xA)^r/r!\bigr)B$, so $Y_k\to e^{xA}B$.

**Convergence.** Write $Y_k$ as a telescoping sum:
$$Y_k(x)=Y_0(x)+\sum_{m=0}^{k-1}\{Y_{m+1}(x)-Y_m(x)\}.\tag{7.59}$$
On any closed bounded subinterval $J_1\subset J$ containing $a$, let $M$ bound $\|A(t)\|$ and $L$ be the length of $J_1$. By induction,
$$\|Y_{m+1}(x)-Y_m(x)\|\le\|B\|\frac{M^{m+1}|x-a|^{m+1}}{(m+1)!}\le\|B\|\frac{(ML)^{m+1}}{(m+1)!}.$$
Hence $\sum_m\|Y_{m+1}-Y_m\|$ is dominated by $\|B\|(e^{ML}-1)$ and converges **uniformly** on $J_1$.

**Properties of the limit $Y(x)=\lim_{k\to\infty}Y_k(x)$:**
- (a) $Y$ is continuous on $J_1$ (uniform limit of continuous functions).
- (b) $Y(x)=B+\int_a^x A(t)Y(t)\,dt$ (interchange limit and integral).
- (c) $Y(a)=B$ and $Y'(x)=A(x)Y(x)$ on $J_1$ (Fundamental Theorem of Calculus).

Since $J_1$ is arbitrary, the solution exists on all of $J$.

**Theorem 7.17 (Uniqueness).** If $A(t)$ is continuous on $J$, the system $Y'=AY$ has at most one solution with $Y(a)=B$.
- *Proof sketch:* For two solutions $Y,Z$, set $W=Z-Y$. Then $W(x)=\int_a^x A(t)W(t)\,dt$, whence $\|W(x)\|\le M\bigl|\int_a^x\|W(t)\|\,dt\bigr|$. Iterating gives $\|W(x)\|\le M^mM_1|x-a|^m/m!\to0$.

**Theorem 7.18 (Existence–Uniqueness).** If $A$ is continuous on an open interval $J$, then for every $a\in J$ and every vector $B$, the system $Y'=AY$, $Y(a)=B$ has **exactly one** solution on $J$.


### 7.22 Successive Approximations for First-Order Nonlinear Systems

The method extends to nonlinear systems
$$Y'=F(t,Y),\qquad Y(a)=B.\tag{7.66}$$
Define the Picard iterates by
$$Y_0(x)=B,\qquad Y_{k+1}(x)=B+\int_a^x F\bigl[t,Y_k(t)\bigr]\,dt\quad(k=0,1,2,\dots).\tag{7.67}$$
Under suitable conditions on $F$, the sequence converges to a solution.

**Example 1.** $y'=x^2+y^2$, $y(0)=0$.
- $Y_0=0$,
- $Y_1=x^3/3$,
- $Y_2=x^3/3+x^7/63$,
- $Y_3=x^3/3+x^7/63+2x^{11}/2076+x^{15}/59535$.
- Degrees grow rapidly ($Y_4$ has degree 31, $Y_5$ has degree 63).

**Example 2.** $y'=2x+e^y$, $y(0)=0$.
- $Y_1=x^2+x$,
- $Y_2=x^2+\int_0^x e^{t^2+t}\,dt$ — the integral is not elementary.

- The practical value of successive approximations is mainly **theoretical** (proving existence); explicit computation is often intractable.


### 7.23 Existence–Uniqueness Theorem for First-Order Nonlinear Systems

Consider the nonlinear system
$$Y'=F(x,Y),\qquad Y(a)=B.$$

**Assumptions on $F$ in a set** $S=\{(x,Y):|x-a|\le h,\;\|Y-B\|\le k\}$:
1. **Boundedness:** $\|F(x,Y)\|\le M$ for all $(x,Y)\in S$.
2. **Continuity:** $G(x)=F(x,Y(x))$ is continuous whenever $Y$ is continuous and $(x,Y(x))\in S$.
3. **Lipschitz condition:** $\|F(x,Y)-F(x,Z)\|\le A\|Y-Z\|$ for all $(x,Y),(x,Z)\in S$.

**Theorem 7.19 (Picard–Lindelöf).** Let $c=\min\{h,k/M\}$ and $I=(a-c,a+c)$. Then there is **exactly one** function $Y$ on $I$ with $Y(a)=B$, $(x,Y(x))\in S$, and
$$Y'(x)=F(x,Y(x))\quad\text{for each }x\in I.$$

- *Proof sketch:* Define Picard iterates $Y_0=B$,
  $$Y_{m+1}(x)=B+\int_a^x F\bigl[t,Y_m(t)\bigr]\,dt.\tag{7.69}$$
- Induction shows $(x,Y_m(x))\in S$ for all $m$ and $x\in I$.
- Using the Lipschitz condition, one proves by induction
  $$\|Y_{m+1}(x)-Y_m(x)\|\le\frac{MA^m|x-a|^{m+1}}{(m+1)!}\le\frac{MA^mc^{m+1}}{(m+1)!}.$$
- Hence $\sum\|Y_{m+1}-Y_m\|$ converges uniformly on $I$; the limit $Y$ satisfies the integral equation $Y(x)=B+\int_a^x F[t,Y(t)]\,dt$.
- Uniqueness follows by the same Gronwall-type argument as in the linear case.


### 7.25 Successive Approximations and Fixed Points of Operators

The Picard iterates for $Y'=AY$, $Y(a)=B$ can be written as
$$Y_{k+1}(x)=B+\int_a^x AY_k(t)\,dt.$$
Define the **operator** $T$ by
$$T(Y)(x)=B+\int_a^x AY(t)\,dt.$$
Then $Y_{k+1}=T(Y_k)$, and the solution $Y$ of the initial-value problem satisfies the integral equation $Y=T(Y)$.

- A function $Y$ with $Y=T(Y)$ is called a **fixed point** of the operator $T$.
- Many problems in analysis reduce to finding fixed points of suitably defined operators.
- The rest of the chapter develops this viewpoint systematically (normed linear spaces, contraction mappings, Banach fixed-point theorem).


### 7.26 Normed Linear Spaces

**Definition.** A **norm** on a linear space $S$ is a real-valued function $N$ (written $\|x\|$) satisfying:
- (a) $\|x\|\ge 0$ for all $x\in S$.
- (b) $\|cx\|=|c|\,\|x\|$ for all scalars $c$.
- (c) $\|x+y\|\le\|x\|+\|y\|$ (triangle inequality).
- (d) $\|x\|=0\implies x=O$.

A linear space with a norm is called a **normed linear space**. The quantity $\|x-y\|$ is the **distance** from $x$ to $y$.

**Example (max norm).** On $C(J)$, the space of continuous real-valued functions on a closed bounded interval $J$,
$$\|\varphi\|=\max_{x\in J}|\varphi(x)|.$$
This norm does **not** arise from an inner product. For instance, with $x(t)=t$ and $y(t)=1-t$ on $[0,1]$,
$$\|x\|=\|y\|=\|x+y\|=\|x-y\|=1,$$
which violates the parallelogram law $\|x+y\|^2+\|x-y\|^2=2\|x\|^2+2\|y\|^2$ required of all inner-product norms.
