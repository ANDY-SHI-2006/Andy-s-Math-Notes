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
