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


### 6.7 The Algebra of Constant-Coefficient Operators

A **constant-coefficient operator** $A$ has the form
$$A=a_0D^n+a_1D^{n-1}+\cdots+a_{n-1}D+a_n,\tag{6.12}$$
where $D$ is the derivative operator and $a_0,\dots,a_n$ are real constants. If $a_0\neq0$, $A$ has **order $n$**.

- Applied to $y$:
  $$A(y)=a_0y^{(n)}+a_1y^{(n-1)}+\cdots+a_{n-1}y'+a_ny.$$
- We work on $(-\infty,+\infty)$ with $\mathscr C^\infty$ (infinitely differentiable functions); $y\in\mathscr C^\infty$ implies $A(y)\in\mathscr C^\infty$.

**Algebraic properties.**
- Constant-coefficient operators form a linear space closed under addition, scalar multiplication, and composition (multiplication).
- They **commute**: $D^rD^s=D^sD^r$ for all $r,s$, hence $AB=BA$ for any two such operators.

**Characteristic polynomial.** With each $A$ associate the polynomial
$$p_A(r)=a_0r^n+a_1r^{n-1}+\cdots+a_n.$$
Conversely, every real polynomial corresponds to a unique constant-coefficient operator.

**Theorem 6.6.** Let $A,B$ have characteristic polynomials $p_A,p_B$ and let $\lambda\in\mathbb R$. Then

- (a) $A=B$ iff $p_A=p_B$.
- (b) $p_{A+B}=p_A+p_B$.
- (c) $p_{AB}=p_A\cdot p_B$.
- (d) $p_{\lambda A}=\lambda\,p_A$.

- *Proof sketch:* If $p_A=p_B$ they have the same coefficients, so $A=B$. Conversely, if $A=B$, apply both to $y=e^{rx}$; since $y^{(k)}=r^ke^{rx}$, we get $A(y)=p_A(r)e^{rx}$ and $B(y)=p_B(r)e^{rx}$, hence $p_A(r)=p_B(r)$ for all $r$. Parts (b)–(d) follow from the definition.

**Operator factorization.** By Theorem 6.6, factorizations of $p_A$ yield factorizations of $A$:
- If $p_A(r)=p_B(r)p_C(r)$, then $A=BC$.
- If
  $$p_A(r)=a_0(r-r_1)(r-r_2)\cdots(r-r_n),\tag{6.13}$$
  then
  $$A=a_0(D-r_1)(D-r_2)\cdots(D-r_n).$$

- The roots $r_1,\dots,r_n$ of $p_A(r)=0$ form the **characteristic equation** of $A$.
- Complex roots occur in conjugate pairs $\alpha\pm i\beta$; each pair gives a real quadratic factor $r^2-2\alpha r+\alpha^2+\beta^2$.
- Hence every $p_A$ factors into linear and quadratic polynomials with real coefficients, and $A$ factors into first- and second-order real constant-coefficient operators.

**Example 1.** $A=D^2-5D+6$.
$$p_A(r)=r^2-5r+6=(r-2)(r-3)\quad\Rightarrow\quad A=(D-2)(D-3).$$

**Example 2.** $A=D^4-2D^3+2D^2-2D+1$.
$$p_A(r)=(r-1)^2(r^2+1)\quad\Rightarrow\quad A=(D-1)(D-1)(D^2+1).$$


### 6.8 Determination of a Basis of Solutions by Factorization

**Theorem 6.7.** If $L=A_1A_2\cdots A_k$ is a product of constant-coefficient operators, then
$$N(A_i)\subseteq N(L)\quad\text{for each }i.\tag{6.14}$$

- *Proof sketch:* If $A_k(u)=0$, then $L(u)=(A_1\cdots A_{k-1})(0)=0$. Since the factors commute, any factor can be placed last.
- If $L(u)=0$ we say $L$ **annihilates** $u$.

#### Case I — Real Distinct Roots

**Theorem 6.8.** If $p_L(r)=0$ has $n$ distinct real roots $r_1,\dots,r_n$, the general solution of $L(y)=0$ is
$$y=\sum_{k=1}^n c_ke^{r_kx}.\tag{6.16}$$

- *Basis:* $u_k(x)=e^{r_kx}$ for $k=1,\dots,n$.

**Example 1.** $(D^3-7D+6)y=0$.
- $L=(D-1)(D-2)(D+3)$.
- Basis: $e^x$, $e^{2x}$, $e^{-3x}$.
- General solution: $y=c_1e^x+c_2e^{2x}+c_3e^{-3x}$.

#### Case II — Repeated Real Roots

**Theorem 6.9.** For a root $r$ of multiplicity $m$, the $m$ functions
$$e^{rx},\;xe^{rx},\;\dots,\;x^{m-1}e^{rx}$$
are independent and are annihilated by $(D-r)^m$.

- *Proof sketch:* Induction on $m$. The key step:
  $$(D-r)(x^{m-1}e^{rx})=(m-1)x^{m-2}e^{rx}=(m-1)u_{m-1}(x),$$
  and $(D-r)^{m-1}$ annihilates $u_{m-1}$.

**Example 2.** $L(y)=0$ with $L=D^3-D^2-8D+12=(D-2)^2(D+3)$.
- From $(D-2)^2$: $e^{2x}$, $xe^{2x}$.
- From $(D+3)$: $e^{-3x}$.
- General solution: $y=c_1e^{2x}+c_2xe^{2x}+c_3e^{-3x}$.

**Example 3.** $(D^6+2D^5-2D^3-D^2)y=0$.
- $L=D^2(D-1)(D+1)^3$.
- Basis: $1$, $x$ (from $D^2$); $e^x$ (from $D-1$); $e^{-x}$, $xe^{-x}$, $x^2e^{-x}$ (from $(D+1)^3$).
- General solution: $y=c_1+c_2x+c_3e^x+(c_4+c_5x+c_6x^2)e^{-x}$.

#### Case III — Complex Roots

Each conjugate pair $\alpha\pm i\beta$ corresponds to a real quadratic factor
$$D^2-2\alpha D+\alpha^2+\beta^2.\tag{6.18}$$

- Null space contains $e^{\alpha x}\cos\beta x$ and $e^{\alpha x}\sin\beta x$.
- If the pair has multiplicity $m$, the basis functions are
  $$x^{q-1}e^{\alpha x}\cos\beta x,\qquad x^{q-1}e^{\alpha x}\sin\beta x,\qquad q=1,\dots,m.$$

**Example 4.** $y'''-4y''+13y'=0$.
- Roots: $0$, $2\pm3i$.
- General solution: $y=c_1+e^{2x}(c_2\cos3x+c_3\sin3x)$.

**Example 5.** $y'''-2y''+4y'-8y=0$.
- Roots: $2$, $\pm2i$.
- General solution: $y=c_1e^{2x}+c_2\cos2x+c_3\sin2x$.

**Example 6.** $y^{(5)}-9y^{(4)}+34y'''-66y''+65y'-25y=0$.
- Roots: $1$, $2\pm i$ (double).
- General solution: $y=c_1e^x+e^{2x}\bigl[(c_2+c_3x)\cos x+(c_4+c_5x)\sin x\bigr]$.


### 6.10 The Relation Between the Homogeneous and Nonhomogeneous Equations

**Theorem 6.10.** Let $L:\mathscr C^n(J)\to\mathscr C(J)$ be of order $n$. Let $u_1,\dots,u_n$ be independent solutions of $L(y)=0$ and let $y_1$ be a particular solution of $L(y)=R$ ($R\in\mathscr C(J)$). Then every solution of the nonhomogeneous equation has the form
$$f(x)=y_1(x)+\sum_{k=1}^n c_ku_k(x).\tag{6.19}$$

- *Proof sketch:* $L(f-y_1)=L(f)-L(y_1)=R-R=0$, so $f-y_1$ lies in the solution space of $L(y)=0$; hence $f-y_1$ is a linear combination of $u_1,\dots,u_n$.

- The right-hand side of (6.19) (with arbitrary constants) is the **general solution** of the nonhomogeneous equation.

- **Geometric analogy:** The solution set of $L(y)=R$ is a "parallel plane" through a particular point $y_1$; the solution space of $L(y)=0$ is the parallel plane through the origin.

- **Practical use:** Solve (1) the homogeneous equation $L(y)=0$, then (2) find one particular solution of $L(y)=R$. Section 6.11 shows (2) is always possible once (1) is solved.


### 6.11 Variation of Parameters

A method to find a particular solution $y_1$ of $L(y)=R$ given $n$ independent solutions $u_1,\dots,u_n$ of $L(y)=0$.

**Ansatz.** Seek $y_1$ in the form
$$y_1=v_1u_1+\cdots+v_nu_n=(v,u),\tag{6.20}$$
where $v=(v_1,\dots,v_n)$ and $u=(u_1,\dots,u_n)$.

**Conditions on $v$.** Impose $n$ conditions so that derivatives of $y_1$ telescope:
$$\begin{aligned}
y_1'&=(v,u')&&\text{provided }(v',u)=0,\\
y_1''&=(v,u'')&&\text{provided }(v',u')=0,\\
&\;\vdots\\
y_1^{(n-1)}&=(v,u^{(n-1)})&&\text{provided }(v',u^{(n-2)})=0,\\
y_1^{(n)}&=(v,u^{(n)})+R(x)&&\text{provided }(v',u^{(n-1)})=R(x).\end{aligned}$$

Then $L(y_1)=(v,L(u))+R(x)=R(x)$, so $y_1$ is a particular solution.

**Matrix form.** The $n$ conditions on $v'$ are
$$W(x)\,v'(x)=R(x)\begin{bmatrix}0\\\vdots\\0\\1\end{bmatrix},\tag{6.23}$$
where $W(x)$ is the **Wronskian matrix**
$$W(x)=\begin{bmatrix}u_1&u_2&\cdots&u_n\\u_1'&u_2'&\cdots&u_n'\\\vdots&\vdots&&\vdots\\u_1^{(n-1)}&u_2^{(n-1)}&\cdots&u_n^{(n-1)}\end{bmatrix}.$$

- $W(x)$ is nonsingular (proved in Section 6.12).
- Solving for $v'$ and integrating gives $v$; the term $(u,v(c))$ is a homogeneous solution and may be dropped.

**Theorem 6.11.** A particular solution of $L(y)=R$ is
$$y_1(x)=\sum_{k=1}^n u_k(x)v_k(x),$$
where the entries $v_1,\dots,v_n$ are determined by
$$v(x)=\int_c^x R(t)\,W(t)^{-1}\begin{bmatrix}0\\\vdots\\0\\1\end{bmatrix}dt.\tag{6.24}$$
(The definite integral may be replaced by any indefinite integral.)

**Example.** $y''-y=\dfrac{2}{1+e^x}$.

- Homogeneous solutions: $u_1=e^x$, $u_2=e^{-x}$.
- Wronskian: $W(x)=\begin{bmatrix}e^x&e^{-x}\\e^x&-e^{-x}\end{bmatrix}$, $\det W=-2$.
- $W^{-1}\begin{bmatrix}0\\1\end{bmatrix}=\frac12\begin{bmatrix}e^{-x}\\-e^x\end{bmatrix}$.
- $R(x)W^{-1}\begin{bmatrix}0\\1\end{bmatrix}=\begin{bmatrix}\frac{e^{-x}}{1+e^x}\\\frac{-e^x}{1+e^x}\end{bmatrix}$.
- Integrating: $v_1=-e^{-x}-x+\log(1+e^x)$, $v_2=-\log(1+e^x)$.
- General solution:
  $$y=c_1e^x+c_2e^{-x}-1-xe^x+(e^x-e^{-x})\log(1+e^x).$$


### 6.12 Nonsingularity of the Wronskian Matrix

**Theorem 6.12.** Let $u_1,\dots,u_n$ be independent solutions of $L(y)=0$ on $J$, where
$$L(y)=y^{(n)}+P_1(x)y^{(n-1)}+\cdots+P_n(x)y.\tag{6.25}$$
Let $w(x)=\det W(x)$. Then the Wronskian determinant satisfies
$$w'+P_1(x)w=0\tag{6.26}$$
on $J$, and
$$w(x)=w(c)\exp\!\left[-\int_c^x P_1(t)\,dt\right]\quad\text{(Abel's formula).}\tag{6.27}$$
Moreover, $w(x)\neq0$ for all $x\in J$.

- *Proof sketch:* Write $w=\det(u,u',\dots,u^{(n-1)})$ with $u=(u_1,\dots,u_n)$.
  - Differentiate the last row: $w'=\det(u,u',\dots,u^{(n-2)},u^{(n)})$.
  - Multiply the last row of $w$ by $P_1$: $P_1w=\det(u,u',\dots,u^{(n-2)},P_1u^{(n-1)})$.
  - Adding gives $w'+P_1w=\det(u,u',\dots,u^{(n-2)},u^{(n)}+P_1u^{(n-1)})=0$, because $u$ satisfies (6.25) so the last row is a linear combination of the preceding rows.
  - Solving (6.26) yields Abel's formula.
- To show $w(c)\neq0$ for some $c\in J$: suppose $w\equiv0$. Then at some $t_0$, $W(t_0)X=O$ has a nonzero solution $X=(c_1,\dots,c_n)$. Define $f=\sum c_ku_k$; then $L(f)=0$ and $f(t_0)=f'(t_0)=\cdots=f^{(n-1)}(t_0)=0$. By uniqueness, $f\equiv0$, forcing all $c_k=0$ — contradiction. Hence $w(c)\neq0$ for some $c$, and Abel's formula shows $w(x)\neq0$ for all $x\in J$.


### 6.13 Reduction to a System of First-Order Equations

For constant-coefficient equations, a particular solution can be found by solving a succession of first-order linear equations.

**Example.** $(D-1)(D-2)y=xe^{x+x^2}$.

- Let $u=(D-2)y$. Then $(D-1)u=xe^{x+x^2}$, a first-order equation.
- Particular solution: $u=\frac12e^{x+x^2}$.
- Then $(D-2)y=\frac12e^{x+x^2}$; solving gives $y_1(x)=\frac12e^{2x}\int_0^x e^{t^2-t}\,dt$.
- General solution: $y=c_1e^x+c_2e^{2x}+\frac12e^{2x}\int_0^x e^{t^2-t}\,dt$.

### 6.14 The Annihilator Method

If $L(y)=R$ has constant coefficients and $R$ is annihilated by some constant-coefficient operator $A$ (i.e. $A(R)=0$), apply $A$ to both sides to obtain $AL(y)=0$. Solve the higher-order homogeneous equation, then select from its solution space a function satisfying $L(y_1)=R$.

**Example 1.** $(D^4-16)y=x^4+x+1$.

- $R$ is a degree-4 polynomial, annihilated by $D^5$.
- Solve $D^5(D^4-16)y=0$. Roots: $0$ (mult. 5), $2$, $-2$, $\pm2i$.
- Since $L=D^4-16$ annihilates $e^{\pm2x},\cos2x,\sin2x$, seek a polynomial particular solution.
- Set $16y_1=ax^4+bx^3+cx^2+dx+e$; substitute into $L(y_1)=x^4+x+1$.
- Coefficients: $a=-1$, $b=c=0$, $d=-1$, $e=-\frac52$.
- Particular solution: $y_1=-\frac1{16}x^4-\frac1{16}x-\frac5{32}$.

**Example 2.** $y''-5y'+6y=xe^x$.

- $L=D^2-5D+6=(D-2)(D-3)$; homogeneous solutions $e^{2x},e^{3x}$.
- $R=xe^x$ is annihilated by $(D-1)^2$.
- Solve $(D-1)^2(D-2)(D-3)y=0$. Roots: $1,1,2,3$.
- Try $y_1=ae^x+bxe^x$ (omit $e^{2x},e^{3x}$ terms).
- Substitution gives $(2a-3b)e^x+2bxe^x=xe^x$; hence $a=\frac34$, $b=\frac12$.
- General solution: $y=c_1e^{2x}+c_2e^{3x}+\frac34e^x+\frac12xe^x$.

**Annihilators of common functions (Table 6.1).**

| Function | Annihilator |
|---|---|
| $x^{m-1}$ | $D^m$ |
| $e^{\alpha x}$ | $D-\alpha$ |
| $x^{m-1}e^{\alpha x}$ | $(D-\alpha)^m$ |
| $\cos\beta x$ or $\sin\beta x$ | $D^2+\beta^2$ |
| $x^{m-1}\cos\beta x$ or $x^{m-1}\sin\beta x$ | $(D^2+\beta^2)^m$ |
| $e^{\alpha x}\cos\beta x$ or $e^{\alpha x}\sin\beta x$ | $D^2-2\alpha D+(\alpha^2+\beta^2)$ |
| $x^{m-1}e^{\alpha x}\cos\beta x$ or $x^{m-1}e^{\alpha x}\sin\beta x$ | $[D^2-2\alpha D+(\alpha^2+\beta^2)]^m$ |

- The annihilator method is efficient when applicable, but limited to right-hand sides $R$ that have a constant-coefficient annihilator. For $e^{x^2},\log x,\tan x$, etc., use variation of parameters.


### 6.17 Linear Equations of Second Order with Analytic Coefficients

A function $f$ is **analytic** on $(x_0-r,x_0+r)$ if it has a convergent power-series expansion there. If the coefficients of a homogeneous linear equation are analytic on such an interval, then $n$ independent analytic solutions exist. We prove this for second-order equations.

**Theorem 6.13.** Let $P_1$ and $P_2$ be analytic on $(x_0-r,x_0+r)$,
$$P_1(x)=\sum_{n=0}^\infty b_n(x-x_0)^n,\qquad P_2(x)=\sum_{n=0}^\infty c_n(x-x_0)^n.$$
Then
$$y''+P_1(x)y'+P_2(x)y=0\tag{6.31}$$
has two independent solutions analytic on the same interval.

- *Proof sketch (power-series method):* Seek
  $$y=\sum_{n=0}^\infty a_n(x-x_0)^n.\tag{6.32}$$
  Substituting the series for $y$, $y'$, $y''$, $P_1$, $P_2$ into (6.31) and equating coefficients yields the **recursion formula**
  $$(n+2)(n+1)a_{n+2}=-\sum_{k=0}^n\bigl[(k+1)a_{k+1}b_{n-k}+a_kc_{n-k}\bigr].\tag{6.33}$$
  - $a_{n+2}$ is expressed in terms of $a_0,\dots,a_{n+1}$ and the coefficients of $P_1,P_2$.
  - Choose arbitrary $a_0,a_1$; the recursion defines all remaining coefficients.

- *Convergence:* Fix $x_1\neq x_0$ in the interval, $t=|x_1-x_0|$. Since $P_1,P_2$ converge absolutely at $x_1$, the terms are bounded: $|b_k|t^k\le M_1$, $|c_k|t^k\le M_2$. Define a dominating sequence $A_n$ by
  $$(n+2)(n+1)A_{n+2}=\frac{M}{t^{n+1}}\sum_{k=0}^{n+1}(k+1)A_kt^k.\tag{6.34}$$
  Then $|a_n|\le A_n$. The ratio test on $\sum A_n|x-x_0|^n$ gives limit $|x-x_0|/t$; hence convergence for $|x-x_0|<t$. Since $x_1$ is arbitrary in $(x_0-r,x_0+r)$, the series converges on the whole interval.

- *Independent solutions:* Choose initial data
  - $u_1$: $a_0=1$, $a_1=0$ $\Rightarrow$ $u_1(x_0)=1$, $u_1'(x_0)=0$.
  - $u_2$: $a_0=0$, $a_1=1$ $\Rightarrow$ $u_2(x_0)=0$, $u_2'(x_0)=1$.
  
  These are independent (different initial-value vectors).


### 6.18 The Legendre Equation

The **Legendre equation**
$$(1-x^2)y''-2xy'+\alpha(\alpha+1)y=0\tag{6.35}$$
arises in problems with spherical symmetry (attraction, heat flow). When $\alpha$ is a positive integer the equation has polynomial solutions called **Legendre polynomials**.

- Can be written as $[(x^2-1)y']'=\alpha(\alpha+1)y$, i.e. $T(y)=\lambda y$ with Sturm–Liouville operator $T(f)=(pf')'$, $p(x)=x^2-1$, $\lambda=\alpha(\alpha+1)$.
- Since $p(1)=p(-1)=0$, $T$ is symmetric on $[-1,1]$ with inner product $(f,g)=\int_{-1}^1fg\,dx$.
- Eigenfunctions for distinct eigenvalues are orthogonal (Theorem 5.3).

**Power-series solution on $(-1,1)$.** Substitute $y=\sum a_nx^n$ into (6.35) to obtain the **recursion formula**
$$a_{n+2}=-\frac{(\alpha-n)(\alpha+n+1)}{(n+1)(n+2)}a_n.\tag{6.36}$$

- Even and odd coefficients decouple:
  - $a_0$ determines $a_2,a_4,\dots$
  - $a_1$ determines $a_3,a_5,\dots$

**General solution:**
$$y=a_0u_1(x)+a_1u_2(x),\tag{6.37}$$
where $u_1$ (even) and $u_2$ (odd) are the series (6.38)–(6.39) with
$$u_1(0)=1,\;u_1'(0)=0,\qquad u_2(0)=0,\;u_2'(0)=1.$$

**Polynomial solutions.**
- If $\alpha=2m$ (even), $u_1(x)$ becomes a polynomial of degree $2m$; $u_2$ remains an infinite series.
- If $\alpha=2m+1$ (odd), $u_2(x)$ becomes a polynomial of degree $2m+1$; $u_1$ remains an infinite series.

The first few Legendre polynomials:

| $\alpha$ | Polynomial |
|---|---|
| $0$ | $1$ |
| $1$ | $x$ |
| $2$ | $1-3x^2$ |
| $3$ | $x-\frac53x^3$ |
| $4$ | $1-10x^2+\frac{35}{3}x^4$ |
| $5$ | $x-\frac{14}{3}x^3+\frac{21}{5}x^5$ |
| $6$ | $1-21x^2+63x^4-\frac{231}{5}x^6$ |


### 6.19 The Legendre Polynomials

A unified formula for the Legendre polynomials (standard normalization):
$$P_n(x)=\frac{1}{2^n}\sum_{r=0}^{[n/2]}\frac{(-1)^r(2n-2r)!}{r!(n-r)!(n-2r)!}x^{n-2r}.\tag{6.42}$$

- When $n$ is even, $P_n$ is a constant multiple of $u_1$ in (6.40); when odd, a multiple of $u_2$ in (6.41).
- The first seven polynomials in this normalization:

$$\begin{aligned}
P_0(x)&=1,\\
P_1(x)&=x,\\
P_2(x)&=\tfrac12(3x^2-1),\\
P_3(x)&=\tfrac12(5x^3-3x),\\
P_4(x)&=\tfrac18(35x^4-30x^2+3),\\
P_5(x)&=\tfrac18(63x^5-70x^3+15x),\\
P_6(x)&=\tfrac1{16}(231x^6-315x^4+105x^2-5).\end{aligned}$$

**Connection to Gram–Schmidt.**
- $P_n$ and $P_m$ are orthogonal for $m\neq n$ (eigenfunctions of a symmetric operator with distinct eigenvalues).
- $\{P_0,\dots,P_n\}$ spans the same subspace as $\{1,x,\dots,x^n\}$.
- By the uniqueness part of the orthogonalization theorem (Theorem 1.13), the Legendre polynomials coincide (up to scalar factors) with the polynomials obtained by Gram–Schmidt orthogonalization of $1,x,x^2,\dots$ on $[-1,1]$.
- The leading coefficient of $P_n$ is
  $$c_n=\frac{(2n)!}{2^n(n!)^2}.$$


### 6.20 Rodrigues' Formula

From (6.42) we rewrite the sum using
$$\frac{(2n-2r)!}{(n-2r)!}x^{n-2r}=\frac{d^n}{dx^n}x^{2n-2r},\qquad\frac{1}{r!(n-r)!}=\frac1{n!}\binom{n}{r}$$
to obtain
$$P_n(x)=\frac{1}{2^n n!}\frac{d^n}{dx^n}\sum_{r=0}^{n}(-1)^r\binom{n}{r}x^{2n-2r}.$$
The sum is the binomial expansion of $(x^2-1)^n$, giving **Rodrigues' formula**:
$$P_n(x)=\frac{1}{2^n n!}\frac{d^n}{dx^n}(x^2-1)^n.$$

**Key properties** (proofs outlined in exercises):

- **Normalization:** $P_n(1)=1$.
- **Parity:** $P_n(-x)=(-1)^nP_n(x)$ (even/odd according to $n$).
- **Orthogonality:**
  $$\int_{-1}^1 P_n(x)P_m(x)\,dx=0\quad(m\neq n).$$
- **Norm:**
  $$\|P_n\|^2=\int_{-1}^1[P_n(x)]^2\,dx=\frac{2}{2n+1}.$$
- **Expansion:** Every polynomial $f$ of degree $n$ can be written as
  $$f(x)=\sum_{k=0}^n c_kP_k(x),\qquad c_k=\frac{2k+1}{2}\int_{-1}^1 f(x)P_k(x)\,dx.$$
- **Zeros:** $P_n$ has $n$ distinct real zeros, all in $(-1,1)$.


### 6.22 The Method of Frobenius

When $P_1$ or $P_2$ in $y''+P_1y'+P_2y=0$ is **not** analytic at $x_0$, ordinary power-series solutions may fail. For equations with a **regular singular point** at $x_0$, i.e. equations of the form
$$(x-x_0)^2y''+(x-x_0)P(x)y'+Q(x)y=0,\tag{6.45}$$
where $P,Q$ are analytic near $x_0$, Frobenius (1873) developed the following method.

**Indicial equation.** The quadratic
$$t(t-1)+P(x_0)t+Q(x_0)=0\tag{6.46}$$
is called the **indicial equation**; its roots $\alpha_1,\alpha_2$ determine the form of the solutions.

**Theorem 6.14 (Roots not differing by an integer).** If $\alpha_1-\alpha_2$ is **not** an integer, there are two independent solutions
$$u_1(x)=|x-x_0|^{\alpha_1}\sum_{n=0}^\infty a_n(x-x_0)^n,\quad a_0=1,\tag{6.47}$$
$$u_2(x)=|x-x_0|^{\alpha_2}\sum_{n=0}^\infty b_n(x-x_0)^n,\quad b_0=1.\tag{6.48}$$
Both series converge for $|x-x_0|<r$.

**Theorem 6.15 (Roots differing by an integer).** If $\alpha_1-\alpha_2=N\in\mathbb Z_{\ge0}$, there is a solution $u_1$ of the form (6.47) and a second independent solution
$$u_2(x)=|x-x_0|^{\alpha_2}\sum_{n=0}^\infty b_n(x-x_0)^n+C\,u_1(x)\log|x-x_0|,\tag{6.49}$$
with $b_0=1$. The constant $C$ is nonzero when $N=0$; it may or may not be zero when $N>0$.


### 6.23 The Bessel Equation

The **Bessel equation**
$$x^2y''+xy'+(x^2-\alpha^2)y=0$$
arises in cylindrical problems (vibrations, heat flow, currents). It has the regular singular point $x_0=0$ with $P(x)=1$, $Q(x)=x^2-\alpha^2$.

**Frobenius ansatz:** $y=|x|^t\sum_{n=0}^\infty a_nx^n$.

**Indicial equation:** $t^2-\alpha^2=0$, roots $t=\pm\alpha$.

**First solution ($t=\alpha$).** The recursion gives $a_1=0$, $a_{2n+1}=0$, and
$$a_{2n}=\frac{(-1)^na_0}{2^{2n}n!(1+\alpha)(2+\alpha)\cdots(n+\alpha)}.$$
Choosing $a_0=2^{-\alpha}/\Gamma(1+\alpha)$ yields the **Bessel function of the first kind**:
$$J_\alpha(x)=\Bigl(\frac{x}{2}\Bigr)^\alpha\sum_{n=0}^\infty\frac{(-1)^n}{n!\,\Gamma(n+1+\alpha)}\Bigl(\frac{x}{2}\Bigr)^{2n}.\tag{6.59}$$

- For integer order $p=0,1,2,\dots$:
  $$J_p(x)=\sum_{n=0}^\infty\frac{(-1)^n}{n!(n+p)!}\Bigl(\frac{x}{2}\Bigr)^{2n+p}.$$

**Second solution when $\alpha$ is not an integer.** Replace $\alpha$ by $-\alpha$ in (6.59) to get $J_{-\alpha}(x)$. Then $J_\alpha$ and $J_{-\alpha}$ are independent, and the general solution for $x>0$ is
$$y=c_1J_\alpha(x)+c_2J_{-\alpha}(x).$$

**Gamma function review.**
$$\Gamma(s)=\int_0^\infty t^{s-1}e^{-t}\,dt\quad(s>0),\qquad\Gamma(s+1)=s\Gamma(s),\qquad\Gamma(n+1)=n!.$$
By (6.58), $\Gamma$ extends to all non-integer real $s$.

**Second solution when $\alpha=p$ is a nonnegative integer.** A second independent solution involves a logarithmic term (Frobenius second case). It can be written as the **Bessel function of the second kind** $K_p(x)$:
$$K_p(x)=J_p(x)\log x+x^{-p}\sum_{n=0}^\infty C_nx^n,$$
with explicit coefficients involving harmonic numbers $h_n=1+\frac12+\cdots+\frac1n$.

- General solution for integer order $p$:
  $$y=c_1J_p(x)+c_2K_p(x).$$
