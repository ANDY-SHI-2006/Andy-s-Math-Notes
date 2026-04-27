# Chapter 6 — Linear Differential Equations

### 6.1 Historical Introduction

- Differential equations originated in the 17th century with Newton, Leibniz, and the Bernoullis, who solved simple first- and second-order equations arising from geometry and mechanics.
- Early work (~1690) aimed to express all solutions in terms of elementary functions using addition, subtraction, multiplication, division, composition, and integration.
- Special techniques such as **separation of variables** and **integrating factors** were discovered before the end of the 17th century.
- In the 18th century Euler, Lagrange, and Laplace developed more systematic procedures.
- It became clear that only a few differential equations are solvable by elementary means. Mathematicians shifted focus to:
  - Existence of solutions.
  - Deducing properties of solutions from the equation itself.
  - Treating differential equations as **new sources of functions**.
- **Cauchy (1820s)**: first existence theorem — every first-order equation $y'=f(x,y)$ has a solution whenever $f(x,y)$ satisfies certain general conditions.
  - Example: the **Riccati equation** $y'=P(x)y^2+Q(x)y+R(x)$.
  - Cauchy's work implies existence of a solution on $(-r,r)$ about the origin, provided $P,Q,R$ have power-series expansions.
- **Liouville (1841)**: showed that in some cases the Riccati solution cannot be obtained by elementary means.
- **Linear differential equations** are among the few types for which general results can be obtained. Simple cases (first order and second order with constant coefficients) were discussed in Volume I.


### 6.2 Review of Results Concerning Linear Equations of First and Second Orders

**First-order linear equation.**
$$y'+P(x)y=Q(x).\tag{6.1}$$

**Theorem 6.1 (Existence–Uniqueness).** Assume $P$ and $Q$ are continuous on an open interval $J$. For any $a\in J$ and any real $b$, there is exactly one function $y=f(x)$ satisfying (6.1) and $f(a)=b$, given by
$$f(x)=be^{-A(x)}+e^{-A(x)}\int_a^x Q(t)e^{A(t)}\,dt,\tag{6.2}$$
where $A(x)=\int_a^x P(t)\,dt$.

**Second-order linear equation.**
$$P_0(x)y''+P_1(x)y'+P_2(x)y=R(x).$$

- If $P_0,P_1,P_2,R$ are continuous on $J$ and $P_0$ is never zero on $J$, solutions always exist on $J$ (Section 6.5).
- No general explicit formula analogous to (6.2) exists for variable coefficients.
- If the coefficients are **constants** and $R=0$, all solutions are explicit.

**Theorem 6.2 (Constant coefficients, homogeneous).** Consider
$$y''+ay'+by=0,\tag{6.3}$$
with real constants $a,b$. Let $d=a^2-4b$ be the **discriminant** of the **characteristic equation**
$$r^2+ar+b=0.\tag{6.5}$$
Every solution on $(-\infty,+\infty)$ has the form
$$y=e^{-ax/2}\bigl[c_1u_1(x)+c_2u_2(x)\bigr].\tag{6.4}$$

| Case | Condition | $u_1(x)$ | $u_2(x)$ | General solution |
|---|---|---|---|---|
| (a) | $d=0$ | $1$ | $x$ | $y=e^{-ax/2}(c_1+c_2x)$ |
| (b) | $d>0$ | $e^{kx}$ | $e^{-kx}$ | $y=c_1e^{r_1x}+c_2e^{r_2x}$ |
| (c) | $d<0$ | $\cos kx$ | $\sin kx$ | $y=e^{-ax/2}(c_1\cos kx+c_2\sin kx)$ |

where $k=\frac12\sqrt d$ (real) or $k=\frac12\sqrt{-d}$ (imaginary), and
$$r_1=\frac{-a+\sqrt d}{2},\qquad r_2=\frac{-a-\sqrt d}{2}.$$

- *Complex roots.* When $d<0$, write $r_1=-\frac a2+ik$, $r_2=-\frac a2-ik$. The complex exponentials
  $$f_1(x)=e^{r_1x}=e^{-ax/2}(\cos kx+i\sin kx),$$
  $$f_2(x)=e^{r_2x}=e^{-ax/2}(\cos kx-i\sin kx)$$
  are complex solutions; their real and imaginary parts yield the real basis $\{e^{-ax/2}\cos kx,\;e^{-ax/2}\sin kx\}$.


### 6.4 Linear Differential Equations of Order $n$

A linear differential equation of order $n$ has the form
$$P_0(x)y^{(n)}+P_1(x)y^{(n-1)}+\cdots+P_n(x)y=R(x).\tag{6.6}$$

The functions $P_0,\dots,P_n$ are the **coefficients**; they are assumed continuous on an interval $J$ (bounded or unbounded).

**Singular points.** Points where $P_0(x)=0$ are called **singular points** and may introduce complications. To avoid them we assume $P_0$ is never zero on $J$; dividing by $P_0$ gives the standard form with leading coefficient $1$:
$$y^{(n)}+P_1(x)y^{(n-1)}+\cdots+P_n(x)y=R(x).\tag{6.7}$$

**Operator notation.** Let $\mathscr C(J)$ be the linear space of all real-valued functions continuous on $J$, and $\mathscr C^n(J)$ the subspace of functions whose first $n$ derivatives exist and are continuous on $J$. Define the **linear differential operator of order $n$**
$$L=D^n+P_1D^{n-1}+\cdots+P_n,$$
so that
$$L(f)=f^{(n)}+P_1f^{(n-1)}+\cdots+P_nf.$$

Equation (6.7) is written compactly as
$$L(y)=R.\tag{6.8}$$

- $L$ is linear: $L(y_1+y_2)=L(y_1)+L(y_2)$ and $L(cy)=cL(y)$.

**Homogeneous and non-homogeneous equations.**
- $L(y)=0$ is the **homogeneous equation** corresponding to $L(y)=R$.
- If $R\not\equiv0$, $L(y)=R$ is a **non-homogeneous equation**.
- The non-homogeneous equation can always be solved once the corresponding homogeneous equation is solved.

**Solution space.** The set of solutions of $L(y)=0$ is the null space $N(L)$ of $L$, also called the **solution space**. Although $\mathscr C^n(J)$ is infinite-dimensional, the solution space is always finite-dimensional. In fact,
$$\dim N(L)=n.\tag{6.9}$$

Equation (6.9) is the **dimensionality theorem** for linear differential operators; it will be deduced from an existence–uniqueness theorem.


### 6.5 The Existence–Uniqueness Theorem

**Theorem 6.3 (Existence–Uniqueness for Linear Equations of Order $n$).** Let $P_1,\dots,P_n$ be continuous on an open interval $J$ and let
$$L=D^n+P_1D^{n-1}+\cdots+P_n.$$
If $x_0\in J$ and $k_0,\dots,k_{n-1}$ are given real numbers, then there exists **one and only one** function $y=f(x)$ satisfying the homogeneous equation $L(y)=0$ on $J$ and the initial conditions
$$f(x_0)=k_0,\;f'(x_0)=k_1,\;\dots,\;f^{(n-1)}(x_0)=k_{n-1}.$$

- The vector $(f(x_0),f'(x_0),\dots,f^{(n-1)}(x_0))$ in $n$-space is the **initial-value vector** of $f$ at $x_0$.
- The theorem says: choose any point $x_0\in J$ and any vector in $n$-space; there is exactly one solution with that initial-value vector at $x_0$.
- For $n=2$: prescribed $f(x_0)$ and $f'(x_0)$ determine a unique solution.
- *Proof strategy:* obtained as a corollary of more general existence–uniqueness theorems in Chapter 7. An alternate proof for constant coefficients is given in Section 7.9.

### 6.6 The Dimension of the Solution Space of a Homogeneous Linear Equation

**Theorem 6.4 (Dimensionality Theorem).** Let $L:\mathscr C^n(J)\to\mathscr C(J)$ be a linear differential operator of order $n$,
$$L=D^n+P_1D^{n-1}+\cdots+P_n.\tag{6.10}$$
Then the solution space of $L(y)=0$ has dimension $n$.

- *Proof sketch:* Define $T:N(L)\to V_n$ by $T(f)=(f(x_0),f'(x_0),\dots,f^{(n-1)}(x_0))$. By Theorem 6.3, $T(f)=0$ implies $f=0$, so $T$ is one-to-one on $N(L)$. Hence $T^{-1}$ is one-to-one and maps $V_n$ onto $N(L)$. By Theorem 2.11, $\dim N(L)=\dim V_n=n$.

**Theorem 6.5.** Let $L$ be of order $n$. If $u_1,\dots,u_n$ are $n$ independent solutions of $L(y)=0$ on $J$, then every solution on $J$ has the form
$$f(x)=\sum_{k=1}^n c_k u_k(x).\tag{6.11}$$

- The linear combination (6.11) with arbitrary constants $c_1,\dots,c_n$ is called the **general solution**.
- The dimensionality theorem guarantees a basis of $n$ solutions always exists, but gives no general method for finding it. Special methods exist for special equations, notably **constant-coefficient** equations.
