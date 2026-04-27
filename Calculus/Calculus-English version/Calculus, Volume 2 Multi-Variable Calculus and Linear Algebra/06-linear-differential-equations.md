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
