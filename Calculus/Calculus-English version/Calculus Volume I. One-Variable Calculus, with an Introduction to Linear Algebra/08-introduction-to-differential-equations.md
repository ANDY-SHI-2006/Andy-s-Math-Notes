[<- Previous: 7. Polynomial Approximations to Functions](07-polynomial-approximations-to-functions.md) | [Next: 9. Complex Numbers ->](09-complex-numbers.md)

# 8. Introduction to Differential Equations

## 8.1 Introduction

A **differential equation** is an equation involving at least one derivative of an unknown function.

### 8.1.1 Classification

| Type | Unknown | Example |
|------|---------|---------|
| **Ordinary** (ODE) | Function of **one** variable | $f'(x)=f(x)$ |
| **Partial** (PDE) | Function of **two or more** variables | $\dfrac{\partial^{2}f}{\partial x^{2}}+\dfrac{\partial^{2}f}{\partial y^{2}}=0$ (Laplace's equation) |

### 8.1.2 First Example 鈥?The Exponential ODE

$$
f'(x)=f(x).
$$

- Particular solution: $f(x)=e^{x}$.
- **General solution:** $f(x)=Ce^{x}$ for arbitrary constant $C$.

### 8.1.3 A Partial-Differential Equation 鈥?Laplace's Equation

$$
\frac{\partial^{2}f}{\partial x^{2}}+\frac{\partial^{2}f}{\partial y^{2}}=0.
$$

This appears in electromagnetism, fluid mechanics, and elsewhere. Sample solutions:

- $f(x,y)=x+2y$
- $f(x,y)=e^{x}\cos y$
- $f(x,y)=\log(x^{2}+y^{2})$

### 8.1.4 Historical Note

- Originated in the 17th century from problems in **geometry and mechanics**.
- Early contributors: Newton, Leibniz, the Bernoullis.
- Two main strands of study:
  1. **Special tricks** (exact equations, substitutions, etc.) 鈥?discussed later in this chapter.
  2. **Linear differential equations** 鈥?the most widely occurring type; a fuller treatment appears in Volume II.

## 8.2 Terminology and Notation

### 8.2.1 Standard Notation

- $y$ in place of $f(x)$; $y', y'', y'''$ for derivatives.
- Other letters ($u, v, z$) may also be used.

### 8.2.2 Order of a Differential Equation

The **order** is the order of the highest derivative appearing.

| Equation | Order |
|----------|-------|
| $y'=y$ | First-order |
| $y''=x^{3}y+\sin(xy')$ | Second-order |

### 8.2.3 First-Order Equations

General form:

$$
y'=f(x,y).
$$

A differentiable function $y=Y(x)$ is a **solution** on an interval $I$ if:

$$
Y'(x)=f\bigl[x,Y(x)\bigr]\quad\text{for all }x\in I.
$$

### 8.2.4 The Simplest Case 鈥?$y'=Q(x)$

When $f(x,y)$ is independent of $y$:

$$
y'=Q(x).
$$

Every solution is given by:

$$
y=\int Q(x)\,dx+C,
$$

where $C$ is an arbitrary constant of integration. Even if the integral cannot be expressed in terms of elementary functions, the equation is regarded as solved if the solution is written as an integral of a known function.

## 8.3 A First-Order Differential Equation for the Exponential Function

### 8.3.1 Theorem 8.1 鈥?Existence and Uniqueness

**Statement.** If $C$ is a given real number, there is **one and only one** function $f$ satisfying:

$$
f'(x)=f(x)\quad\text{for all }x,\qquad f(0)=C.
$$

This function is $f(x)=Ce^{x}$.

**Proof.**

- *Verification.* $f(x)=Ce^{x}$ clearly satisfies $f'=f$ and $f(0)=C$.
- *Uniqueness.* Let $g$ be any solution and define $h(x)=g(x)e^{-x}$. Then:
  $$
  h'(x)=g'(x)e^{-x}-g(x)e^{-x}=e^{-x}[g'(x)-g(x)]=0.
  $$
  By the zero-derivative theorem, $h$ is constant. Since $h(0)=g(0)e^{0}=C$, we have $h(x)\equiv C$, hence $g(x)=Ce^{x}$.

> Theorem 8.1 is the simplest example of an **existence-uniqueness theorem**.

### 8.3.2 Initial-Value Problems

In solving a first-order ODE, integration removes $y'$ and introduces an arbitrary constant $C$. The way $C$ enters depends on the equation (additive, as in $y=\int Q+C$, or multiplicative, as in $y=Ce^{x}$).

An **initial-value problem** asks for the particular solution satisfying $y(x_{0})=y_{0}$ at some point. This terminology comes from mechanics, where the prescribed value is the displacement at an initial time.

## 8.4 First-Order Linear Differential Equations

### 8.4.1 Standard Form

$$
y'+P(x)y=Q(x),
$$

where $P,Q$ are continuous on an open interval $I$.

- **Nonhomogeneous** when $Q\not\equiv 0$.
- **Homogeneous (reduced)** when $Q\equiv 0$:
  $$
  y'+P(x)y=0.
  $$

### 8.4.2 Solving the Homogeneous Equation

If $y\neq 0$ on $I$, divide by $y$:

$$
\frac{y'}{y}=-P(x)\quad\Longrightarrow\quad D\log y=-P(x).
$$

Hence:

$$
y=e^{-A(x)},\qquad A(x)=\int P(x)\,dx-C.
$$

**Theorem 8.2.** Let $P$ be continuous on $I$, $a\in I$, $b\in\mathbb{R}$. The initial-value problem

$$
y'+P(x)y=0,\quad f(a)=b
$$

has the **unique** solution on $I$:

$$
f(x)=b\,e^{-A(x)},\qquad A(x)=\int_{a}^{x}P(t)\,dt.
$$

**Proof.** Define $h(x)=g(x)e^{A(x)}$ for any solution $g$. Then $h'(x)=e^{A(x)}[g'(x)+P(x)g(x)]=0$, so $h$ is constant. Since $h(a)=g(a)=b$, we get $g(x)=b\,e^{-A(x)}$.

### 8.4.3 Solving the Nonhomogeneous Equation

Let $g$ satisfy $y'+P(x)y=Q(x)$ and set $h(x)=g(x)e^{A(x)}$ with $A(x)=\int_{a}^{x}P(t)\,dt$. Then:

$$
h'(x)=e^{A(x)}Q(x).
$$

By the second FTC:

$$
h(x)=h(a)+\int_{a}^{x}e^{A(t)}Q(t)\,dt.
$$

Since $h(a)=g(a)$, every solution of (8.5) has the form:

$$
g(x)=g(a)\,e^{-A(x)}+e^{-A(x)}\int_{a}^{x}Q(t)\,e^{A(t)}\,dt.
$$

**Theorem 8.3.** Let $P,Q$ be continuous on $I$, $a\in I$, $b\in\mathbb{R}$. The initial-value problem

$$
y'+P(x)y=Q(x),\quad f(a)=b
$$

has the **unique** solution on $I$:

$$
f(x)=b\,e^{-A(x)}+e^{-A(x)}\int_{a}^{x}Q(t)\,e^{A(t)}\,dt,\qquad A(x)=\int_{a}^{x}P(t)\,dt.
$$

### 8.4.4 Example

**Problem.** Find all solutions of $xy'+(1-x)y=e^{2x}$ on $(0,+\infty)$.

*Solution.* Divide by $x$:

$$
y'+\Bigl(\frac{1}{x}-1\Bigr)y=\frac{e^{2x}}{x},\qquad P(x)=\frac{1}{x}-1,\;Q(x)=\frac{e^{2x}}{x}.
$$

Take $a=1$ and compute:

$$
A(x)=\int_{1}^{x}\Bigl(\frac{1}{t}-1\Bigr)dt=\log x-(x-1).
$$

Hence $e^{-A(x)}=\dfrac{e^{x-1}}{x}$ and $e^{A(t)}=te^{1-t}$. By Theorem 8.3 with $f(1)=b$:

$$
f(x)=b\,\frac{e^{x-1}}{x}+\frac{e^{x-1}}{x}\int_{1}^{x}\frac{e^{2t}}{t}\cdot te^{1-t}\,dt
=b\,\frac{e^{x-1}}{x}+\frac{e^{x}}{x}(e^{x}-e).
$$

Simplifying:

$$
f(x)=\frac{e^{2x}+Ce^{x}}{x},\qquad C=be^{-1}-e.
$$

**Behavior near $x=0$.** Using $e^{2x}=1+2x+o(x)$ and $e^{x}=1+x+o(x)$:

$$
f(x)=\frac{(1+C)+(2+C)x+o(x)}{x}=\frac{1+C}{x}+(2+C)+o(1).
$$

Only the solution with $C=-1$ tends to a finite limit as $x\to 0$; that limit is $1$.

## 8.5 Physical Applications of First-Order Linear ODEs

### 8.5.1 Radioactive Decay

**Model.** $y'=-ky$ $(k>0)$.

**Solution.** $f(t)=f(0)\,e^{-kt}$.

**Half-life.** Time $T$ for which $f(T)/f(0)=\frac{1}{2}$:

$$
T=\frac{\log 2}{k}.
$$

### 8.5.2 Falling Body in a Resisting Medium

**Forces.** Gravity $mg$ downward; air resistance $-kv$ upward.

**Equation (velocity).**

$$
v'+\frac{k}{m}v=g.
$$

**Solution** (released from rest, $v(0)=0$):

$$
v(t)=\frac{mg}{k}\bigl(1-e^{-kt/m}\bigr).
$$

- **Terminal velocity:** $v\to\dfrac{mg}{k}$ as $t\to+\infty$.
- With initial velocity $v_{0}$: $v(t)=\dfrac{mg}{k}\bigl(1-e^{-kt/m}\bigr)+v_{0}\,e^{-kt/m}$.

**Equation (displacement).** $s'=v$ gives:

$$
s(t)=\frac{mg}{k}\,t+\frac{gm^{2}}{k^{2}}\bigl(e^{-kt/m}-1\bigr)\qquad(s(0)=0).
$$

### 8.5.3 Newton's Law of Cooling

**Model.** Rate of temperature change proportional to difference from surrounding temperature $M(t)$:

$$
y'=-k\bigl[y-M(t)\bigr]\quad\text{or}\quad y'+ky=kM(t).
$$

**General solution** ($f(a)=b$):

$$
f(t)=b\,e^{-kt}+e^{-kt}\int_{a}^{t}kM(u)\,e^{ku}\,du.
$$

**Example.** Body cools from $200^{\circ}$ to $100^{\circ}$ in 40 min; surrounding temperature $M=10^{\circ}$.

- $f(0)=200$ $\Rightarrow$ $f(t)=10+190\,e^{-kt}$.
- $f(40)=100$ $\Rightarrow$ $k=\dfrac{\log 19-\log 9}{40}$.
- If $M=5^{\circ}$: $f(t)=5+195\,e^{-kt}$; time to reach $100^{\circ}$ is $40\,\dfrac{\log 39-\log 19}{\log 19-\log 9}\approx 38.5$ min.

### 8.5.4 A Dilution Problem

**Setup.** Tank: 100 gal brine at 2.5 lb/gal. Inflow: 2 lb/gal at 5 gal/min. Outflow: 5 gal/min.

**Model.**

$$
y'+\frac{1}{20}y=10,\qquad y(0)=250.
$$

**Solution.**

$$
y(t)=200+50\,e^{-t/20}.
$$

- $y(t)>200$ for all $t$; $y\to 200$ as $t\to+\infty$.

### 8.5.5 Electric Circuits (RL Circuit)

**Kirchhoff's voltage law.**

$$
LI'(t)+RI(t)=V(t).
$$

**General solution** ($I(0)$ given):

$$
I(t)=I(0)\,e^{-Rt/L}+e^{-Rt/L}\int_{0}^{t}\frac{V(x)}{L}\,e^{Rx/L}\,dx.
$$

**Constant voltage** $V(t)\equiv E$:

$$
I(t)=\frac{E}{R}+\Bigl(I(0)-\frac{E}{R}\Bigr)e^{-Rt/L}.
$$

| Term | Name | Behavior as $t\to+\infty$ |
|------|------|---------------------------|
| $\dfrac{E}{R}$ | **Steady-state current** | Constant |
| $\Bigl(I(0)-\dfrac{E}{R}\Bigr)e^{-Rt/L}$ | **Transient current** | Decays to $0$ |

> **Analog computer.** A physical problem modeled by $y'+ay=Q$ can be simulated by an RL circuit with $R/L=a$ and impressed voltage $LQ$, allowing numerical data to be obtained by electrical measurement.

## 8.6 Linear Equations of Second Order with Constant Coefficients

### 8.6.1 General Form

A **second-order linear** differential equation has the form:

$$
y''+P_{1}(x)y'+P_{2}(x)y=R(x).
$$

- **Coefficients:** $P_{1}, P_{2}$.
- **Homogeneous** when $R(x)\equiv 0$.

This chapter treats only the case where $P_{1}, P_{2}$ are **constants**.

### 8.6.2 The Homogeneous Equation

$$
y''+ay'+by=0.
$$

> First completely solved by Euler (1743). It arises in a wide variety of applied problems.

## 8.7 Existence of Solutions of $y''+by=0$

We seek nontrivial solutions on $(-\infty,+\infty)$. The trivial solution $y\equiv 0$ always exists.

### 8.7.1 Example 1: $y''=0$

Here $a=b=0$. Integrating twice:

$$
y=c_{1}x+c_{2}.
$$

Conversely, every linear polynomial satisfies $y''=0$; these are **all** solutions.

### 8.7.2 Example 2: $y''+by=0$ with $b<0$

Write $b=-k^{2}$ $(k>0)$; the equation becomes $y''=k^{2}y$.

By inspection, $y=e^{kx}$ and $y=e^{-kx}$ are solutions. Hence:

$$
y=c_{1}e^{kx}+c_{2}e^{-kx}
$$

is a solution for arbitrary constants $c_{1},c_{2}$. (Theorem 8.6 will show this includes **all** solutions.)

### 8.7.3 Example 3: $y''+by=0$ with $b>0$

Write $b=k^{2}$ $(k>0)$; the equation becomes $y''=-k^{2}y$.

By inspection, $y=\cos kx$ and $y=\sin kx$ are solutions. Hence:

$$
y=c_{1}\cos kx+c_{2}\sin kx
$$

is a solution for arbitrary constants $c_{1},c_{2}$. (Theorem 8.6 will show this includes **all** solutions.)

## 8.8 Reduction of $y''+ay'+by=0$ to $y''+by=0$

### 8.8.1 The Substitution $y=uv$

Let $y=uv$. Then:

$$
y''+ay'+by=(v''+av'+bv)u+(2v'+av)u'+vu''.
$$

Choose $v$ so that the coefficient of $u'$ vanishes: $2v'+av=0$, i.e.:

$$
v=e^{-ax/2}.
$$

For this $v$: $v''=\dfrac{a^{2}v}{4}$, and:

$$
v''+av'+bv=\frac{a^{2}v}{4}-\frac{a^{2}v}{2}+bv=\frac{4b-a^{2}}{4}\,v.
$$

Hence:

$$
y''+ay'+by=\Bigl(u''+\frac{4b-a^{2}}{4}\,u\Bigr)v.
$$

### 8.8.2 Theorem 8.4

Let $y=ue^{-ax/2}$. Then on $(-\infty,+\infty)$:

$$
y''+ay'+by=0\quad\Longleftrightarrow\quad u''+\frac{4b-a^{2}}{4}\,u=0.
$$

> This reduces the general equation to the special case $u''+\lambda u=0$ already solved in Section 8.7.

## 8.9 Uniqueness Theorem for $y''+by=0$

### 8.9.1 Theorem 8.5

Assume $f$ and $g$ satisfy $y''+by=0$ on $(-\infty,+\infty)$ and:

$$
f(0)=g(0),\qquad f'(0)=g'(0).
$$

Then $f(x)=g(x)$ for all $x$.

### 8.9.2 Proof Sketch

Set $h=f-g$. Then $h$ satisfies $y''+by=0$ with $h(0)=h'(0)=0$.

**Step 1 鈥?Derivatives at $0$.** By repeated differentiation:

$$
y^{(2n)}=(-1)^{n}b^{n}y,\qquad y^{(2n-1)}=(-1)^{n-1}b^{n-1}y'.
$$

Since $h(0)=h'(0)=0$, all derivatives $h^{(n)}(0)=0$.

**Step 2 鈥?Taylor polynomials.** Every Taylor polynomial of $h$ at $0$ has all coefficients zero.

**Step 3 鈥?Remainder estimate.** By Taylor's formula with remainder (Theorem 7.6):

$$
h(x)=E_{2n-1}(x).
$$

On $[-c,c]$, $|h(x)|\le M$ implies $|h^{(2n)}(x)|\le M|b|^{n}$. By Theorem 7.7:

$$
0\le|h(x)|\le\frac{M\,|b|^{n}\,c^{2n}}{(2n)!}=\frac{MA^{2n}}{(2n)!},\qquad A=|b|^{1/2}c.
$$

Since $\dfrac{A^{m}}{m!}\to 0$ as $m\to+\infty$, we get $h(x)=0$ on $[-c,c]$. As $c$ is arbitrary, $h(x)\equiv 0$.

> The choice of $0$ is inessential; the theorem holds with initial data prescribed at any point $c$.

## 8.10 Complete Solution of $y''+by=0$

### 8.10.1 Theorem 8.6

Given $b\in\mathbb{R}$, define $u_{1},u_{2}$ on $(-\infty,+\infty)$:

| Case | $b$ | $u_{1}(x)$ | $u_{2}(x)$ |
|------|-----|-----------|-----------|
| (a) | $0$ | $1$ | $x$ |
| (b) | $<0$ ($b=-k^{2}$) | $e^{kx}$ | $e^{-kx}$ |
| (c) | $>0$ ($b=k^{2}$) | $\cos kx$ | $\sin kx$ |

Then **every** solution of $y''+by=0$ has the form:

$$
y=c_{1}u_{1}(x)+c_{2}u_{2}(x).
$$

**Proof idea.** For any solution $f$, solve:

$$
c_{1}u_{1}(0)+c_{2}u_{2}(0)=f(0),\qquad c_{1}u_{1}'(0)+c_{2}u_{2}'(0)=f'(0)
$$

for $c_{1},c_{2}$. Then $f$ and $c_{1}u_{1}+c_{2}u_{2}$ are solutions with the same value and derivative at $0$; by uniqueness (Theorem 8.5), they coincide everywhere.

## 8.11 Complete Solution of $y''+ay'+by=0$

### 8.11.1 Theorem 8.7

Let $d=a^{2}-4b$ be the **discriminant**. Then every solution has the form:

$$
y=e^{-ax/2}\bigl[c_{1}u_{1}(x)+c_{2}u_{2}(x)\bigr],
$$

where $u_{1},u_{2}$ depend on the sign of $d$:

| Case | Discriminant | $k$ | $u_{1}(x)$ | $u_{2}(x)$ | General solution |
|------|-------------|-----|-----------|-----------|-----------------|
| (a) | $d=0$ | 鈥?| $1$ | $x$ | $y=e^{-ax/2}(c_{1}+c_{2}x)$ |
| (b) | $d>0$ | $\frac{1}{2}\sqrt{d}$ | $e^{kx}$ | $e^{-kx}$ | $y=c_{1}e^{r_{1}x}+c_{2}e^{r_{2}x}$ |
| (c) | $d<0$ | $\frac{1}{2}\sqrt{-d}$ | $\cos kx$ | $\sin kx$ | $y=e^{-ax/2}(c_{1}\cos kx+c_{2}\sin kx)$ |

In case (b), $r_{1,2}=\dfrac{-a\pm\sqrt{d}}{2}$ are the roots of the **characteristic equation**:

$$
r^{2}+ar+b=0.
$$

> **Note on complex roots.** When $d<0$, the roots $r_{1},r_{2}$ are complex. The form with $\cos$ and $\sin$ is equivalent to a linear combination of $e^{r_{1}x}$ and $e^{r_{2}x}$ once the exponential is extended to complex numbers (Chapter 9).

### 8.11.2 Basis and General Solution

The pair:

$$
v_{1}=e^{-ax/2}u_{1},\qquad v_{2}=e^{-ax/2}u_{2}
$$

is a **basis** for the solution space: every solution is a linear combination of $v_{1}$ and $v_{2}$.

- A differential equation has more than one basis. Example: $y''=9y$ has bases $\{e^{3x},e^{-3x}\}$ and $\{\cosh 3x,\sinh 3x\}$.
- **Test.** $v_{1},v_{2}$ form a basis iff $v_{2}/v_{1}$ is **not** constant.

## 8.12 Nonhomogeneous Linear Equations of Second Order with Constant Coefficients

### 8.12.1 Operator Notation

Define the linear operator:

$$
L(f)=f''+af'+bf.
$$

Then the equation becomes $L(y)=R$. The operator $L$ is **linear**:

$$
L(c_{1}y_{1}+c_{2}y_{2})=c_{1}L(y_{1})+c_{2}L(y_{2}).
$$

If $y_{1},y_{2}$ both satisfy $L(y)=R$, then $L(y_{2}-y_{1})=R-R=0$; hence $y_{2}-y_{1}$ solves the homogeneous equation $L(y)=0$.

### 8.12.2 Theorem 8.8 鈥?General Solution Structure

If $y_{1}$ is a **particular solution** of $L(y)=R$, then the **general solution** is:

$$
y=c_{1}v_{1}+c_{2}v_{2}+y_{1},
$$

where $c_{1}v_{1}+c_{2}v_{2}$ is the general solution of $L(y)=0$.

### 8.12.3 Theorem 8.9 鈥?Variation of Parameters

Let $v_{1},v_{2}$ be a basis of solutions of $L(y)=0$. Define the **Wronskian**:

$$
W(x)=v_{1}(x)v_{2}'(x)-v_{2}(x)v_{1}'(x)\quad(\neq 0\text{ everywhere}).
$$

Then a particular solution of $L(y)=R$ is:

$$
y_{1}(x)=t_{1}(x)v_{1}(x)+t_{2}(x)v_{2}(x),
$$

where:

$$
t_{1}(x)=-\int\frac{v_{2}(x)R(x)}{W(x)}\,dx,\qquad t_{2}(x)=\int\frac{v_{1}(x)R(x)}{W(x)}\,dx.
$$

**Derivation.** Impose $t_{1}'v_{1}+t_{2}'v_{2}=0$. Then $y_{1}'=t_{1}v_{1}'+t_{2}v_{2}'$ and $y_{1}''=t_{1}v_{1}''+t_{2}v_{2}''+t_{1}'v_{1}'+t_{2}'v_{2}'$. Since $L(v_{1})=L(v_{2})=0$, we get $L(y_{1})=t_{1}'v_{1}'+t_{2}'v_{2}'=R$. Solving the algebraic system:

$$
t_{1}'=-\frac{v_{2}R}{W},\qquad t_{2}'=\frac{v_{1}R}{W}.
$$

> **History.** First used by Johann Bernoulli (1697) for first-order equations; extended by Lagrange (1774) to second order.

### 8.12.4 Example: $y''+y=\tan x$

On $(-\pi/2,\pi/2)$: $v_{1}=\cos x$, $v_{2}=\sin x$, $W=1$.

$$
t_{1}=-\int\sin x\tan x\,dx=\sin x-\log\bigl|\sec x+\tan x\bigr|,\qquad
 t_{2}=\int\cos x\tan x\,dx=-\cos x.
$$

Particular solution:

$$
y_{1}=t_{1}\cos x+t_{2}\sin x=-\cos x\,\log\bigl|\sec x+\tan x\bigr|.
$$

**General solution:**

$$
y=c_{1}\cos x+c_{2}\sin x-\cos x\,\log\bigl|\sec x+\tan x\bigr|.
$$

## 8.13 Special Methods for Particular Solutions (Undetermined Coefficients)

### 8.13.1 Case 1 鈥?$R(x)$ Is a Polynomial

If $R$ is a polynomial of degree $n$:

| Condition | Trial form for $y_{1}$ |
|-----------|------------------------|
| $b\neq 0$ | Polynomial of degree $n$ |
| $b=0$, $a\neq 0$ | Polynomial of degree $n+1$ |
| $a=b=0$ | Polynomial of degree $n+2$ (integrate twice) |

**Example.** $y''+y=x^{3}$.

- Homogeneous solution: $c_{1}\cos x+c_{2}\sin x$.
- Try $y_{1}=Ax^{3}+Bx^{2}+Cx+D$. Then $y_{1}''=6Ax+2B$.
- $(6Ax+2B)+(Ax^{3}+Bx^{2}+Cx+D)=x^{3}$.
- Equate coefficients: $A=1$, $B=0$, $C=-6$, $D=0$.
- Particular solution: $y_{1}=x^{3}-6x$.
- **General solution:** $y=c_{1}\cos x+c_{2}\sin x+x^{3}-6x$.

> Compared with variation of parameters, this method requires no integration.

### 8.13.2 Case 2 鈥?$R(x)=p(x)e^{mx}$

Substitute $y=u(x)e^{mx}$. The equation becomes:

$$
u''+(2m+a)u'+(m^{2}+am+b)u=p.
$$

This is Case 1 for $u$, so a polynomial solution $u_{1}$ always exists.

| Condition | Degree of $u_{1}$ |
|-----------|-------------------|
| $m^{2}+am+b\neq 0$ | Same as $\deg p$ |
| $m^{2}+am+b=0$, $2m+a\neq 0$ | $\deg p+1$ |
| $m^{2}+am+b=0$, $2m+a=0$ | $\deg p+2$ |

The particular solution is $y_{1}=u_{1}(x)e^{mx}$.

**Example.** $y''+y=xe^{3x}$.

- Substitute $y=ue^{3x}$: $u''+6u'+10u=x$.
- Try $u_{1}=Ax+B$: $u_{1}=\dfrac{5x-3}{50}$.
- Particular solution: $y_{1}=\dfrac{e^{3x}(5x-3)}{50}$.

### 8.13.3 Extensions

The method also applies when $R$ has the form:

$$
R(x)=p(x)e^{mx}\cos\alpha x\quad\text{or}\quad R(x)=p(x)e^{mx}\sin\alpha x.
$$

In either case, seek a particular solution of the form:

$$
y_{1}(x)=e^{mx}\bigl[q(x)\cos\alpha x+r(x)\sin\alpha x\bigr],
$$

where $q$ and $r$ are polynomials.

## 8.14 Physical Applications of Second-Order Linear ODEs

### 8.14.1 Simple Harmonic Motion

**Model.** $y''+k^{2}y=0$ $(k>0)$.

**Solution.**

$$
y=A\sin kx+B\cos kx=C\sin(kx+\alpha),
$$

where $C=\sqrt{A^{2}+B^{2}}$ and $\alpha=\arctan(B/A)$.

| Quantity | Formula |
|----------|---------|
| Amplitude | $C$ |
| Period | $\dfrac{2\pi}{k}$ |
| Phase angle | $kx+\alpha$ |

### 8.14.2 Damped Vibrations

**Model.** $y''+2cy'+k^{2}y=0$ $(c\neq 0,\;k>0)$.

Discriminant: $d=4(c^{2}-k^{2})$.

| Case | Condition | Form of solution | Behavior ($c>0$) | Name |
|------|-----------|------------------|------------------|------|
| (a) | $c^{2}=k^{2}$ | $y=e^{-cx}(A+Bx)$ | $\to 0$ | **Critical damping** |
| (b) | $c^{2}>k^{2}$ | $y=Ae^{(h-c)x}+Be^{-(h+c)x}$, $h=\sqrt{c^{2}-k^{2}}$ | $\to 0$ | **Overcritical damping** |
| (c) | $c^{2}<k^{2}$ | $y=Ce^{-cx}\sin(hx+\alpha)$, $h=\sqrt{k^{2}-c^{2}}$ | Oscillates, amplitude $\to 0$ | **Undercritical damping** |

> If $c<0$, some solutions become unbounded as $x\to+\infty$ (unstable).

### 8.14.3 RLC Electric Circuits

With a capacitor $C$ added to the RL circuit:

$$
LI''(t)+RI'(t)+\frac{1}{C}I(t)=V'(t).
$$

For constant voltage ($V'=0$):

$$
I''+\frac{R}{L}I'+\frac{1}{LC}I=0.
$$

This is the same type as damped vibrations, with $2c=R/L$ and $k^{2}=1/(LC)$.

| Condition | Damping type |
|-----------|-------------|
| $CR^{2}=4L$ | Critical |
| $CR^{2}>4L$ | Overcritical |
| $CR^{2}<4L$ | Undercritical |

### 8.14.4 Rocket Motion with Variable Mass

**Model.** From conservation of momentum:

$$
m(t)r''(t)=m'(t)c(t)+F(t),
$$

where $m(t)$ is mass, $c(t)$ is exhaust velocity (relative to rocket), and $F(t)$ is external force.

**Special case.** Fuel consumed at rate $k$, exhaust speed $-c$ (constant), gravity $-m(t)g$:

$$
r''(t)=\frac{kc}{w-kt}-g.
$$

- $w$ = initial total weight, $b$ = fuel weight, $T=w/k$ = total burn time.
- Velocity: $r'(t)=-c\log\dfrac{w-kt}{w}-gt$.
- Altitude at fuel exhaustion ($t=b/k$):
  $$
  r\Bigl(\frac{b}{k}\Bigr)=\frac{c(w-b)}{k}\log\frac{w-b}{w}-\frac{gb^{2}}{2k^{2}}+\frac{cb}{k}.
  $$
- Limiting case $b\to w$ (negligible carrier weight):
  $$
  \lim_{b\to w}r\Bigl(\frac{b}{k}\Bigr)=-\frac{1}{2}gT^{2}+cT.
  $$

## 8.15 Remarks on Nonlinear Differential Equations

### 8.15.1 First-Order Equations $y'=f(x,y)$

Unlike linear equations, nonlinear ODEs lack a comprehensive systematic theory. We focus on first-order equations solvable for $y'$:

$$
y'=f(x,y).
$$

### 8.15.2 Existence and Uniqueness Failures

A nonlinear equation may have **no solution** or **more than one** solution satisfying a given initial condition.

| Equation | Initial condition | Outcome |
|----------|-------------------|---------|
| $(y')^{2}-xy'+y+1=0$ | $y=0$ at $x=0$ | No solution (requires $(y')^{2}=-1$) |
| $y'=3y^{2/3}$ | $y=0$ at $x=0$ | Two solutions: $Y_{1}(x)\equiv 0$ and $Y_{2}(x)=x^{3}$ |

### 8.15.3 Implicit Formulas

Sometimes $y'$ can be eliminated to obtain a relation:

$$
F(x,y)=0,
$$

satisfied by some or all solutions.

**Example.** The equation $y'=\dfrac{y-x}{y+x}$ has solutions satisfying:

$$
\frac{1}{2}\log(x^{2}+y^{2})+\arctan\frac{y}{x}+C=0.
$$

This is an **implicit formula**; solving for $y$ explicitly is hopeless. Nevertheless, arriving at such a relation (with no derivatives of the unknown) is regarded as having "solved" or "integrated" the differential equation.

> Qualitative information about solutions can often be obtained directly from the differential equation without explicit or implicit formulas (see next section).

## 8.16 Integral Curves and Direction Fields

### 8.16.1 Integral Curves

A solution of $y'=f(x,y)$ satisfying an implicit relation $F(x,y,C)=0$ defines a curve called an **integral curve**. As $C$ varies, the collection forms a **one-parameter family** of curves.

| Equation | Family | Constant $C$ means |
|----------|--------|-------------------|
| $y'=3$ | $y=3x+C$ | $y$-intercept |
| $y'=x$ | $y=\frac{1}{2}x^{2}+C$ | Crosses $y$-axis at $(0,C)$ |
| $y'=y$ | $y=Ce^{x}$ | $y$-intercept (also slope at $y$-axis) |

### 8.16.2 Envelopes and Singular Solutions

The equation $y=x\,y'-\frac{1}{4}(y')^{2}$ has the one-parameter family:

$$
y=Cx-\frac{1}{4}C^{2}.
$$

The **envelope** of this family is $y=x^{2}$ (dotted in Figure 8.9). The envelope is itself a solution and is **not** a member of the family. By piecing together family members with portions of the envelope, further solutions can be constructed.

### 8.16.3 Finding a Differential Equation from Its Integral Curves

**Example 1.** Circles centered at the origin: $x^{2}+y^{2}=C^{2}$.

Differentiate: $2x+2yy'=0$, hence $y'=-x/y$.

**Example 2.** Circles through the origin with centers on the $x$-axis: $x^{2}+y^{2}-2Cx=0$.

- Differentiate: $x+yy'=C$.
- Eliminate $C$: $y'=\dfrac{y^{2}-x^{2}}{2xy}$.

### 8.16.4 Direction Fields

A **direction field** is constructed by drawing short line segments at various points $(a,b)$ with slope $f(a,b)$. It provides qualitative information about solutions without solving the equation.

> Different initial points $(0,b)$ on the $y$-axis yield different integral curves鈥攖his is a geometric reason for the appearance of an arbitrary constant when integrating a first-order equation.

## 8.17 First-Order Separable Equations

### 8.17.1 Definition

A **separable** equation has the form:

$$
y'=Q(x)R(y)\qquad\text{or}\qquad A(y)y'=Q(x),
$$

where $A(y)=1/R(y)$.

### 8.17.2 Theorem 8.10

Let $y=Y(x)$ solve $A(y)y'=Q(x)$ on an open interval $I$, with $Y'$, $Q$, and $A\circ Y$ continuous. Let $G$ be any primitive of $A$ ($G'=A$). Then $Y$ satisfies:

$$
G(y)=\int Q(x)\,dx+C.
$$

Conversely, any $y$ satisfying this implicit formula is a solution.

**Proof.** $A[Y(x)]Y'(x)=Q(x)$ becomes $G'[Y(x)]Y'(x)=Q(x)$, i.e. $(G\circ Y)'=Q$. Integrate.

> **Mechanical process.** Write $y'=dy/dx$, separate variables $A(y)\,dy=Q(x)\,dx$, and integrate both sides. This is justified by Theorem 8.10.

### 8.17.3 Example: $xy'+y=y^{2}$

Rewrite as:

$$
\frac{y'}{y(y-1)}=\frac{1}{x}\qquad(y\neq 0,1).
$$

The constant functions $y\equiv 0$ and $y\equiv 1$ are also solutions.

For $y\notin\{0,1\}$, separate and integrate:

$$
\int\frac{dy}{y(y-1)}=\int\frac{dx}{x}+K.
$$

Since $\dfrac{1}{y(y-1)}=\dfrac{1}{y-1}-\dfrac{1}{y}$:

$$
\log\Bigl|\frac{y-1}{y}\Bigr|=\log|x|+K\quad\Longrightarrow\quad\frac{y-1}{y}=Cx.
$$

Solving for $y$:

$$
y=\frac{1}{1-Cx}.
$$

> All solutions: $y\equiv 0$, $y\equiv 1$, and $y=\dfrac{1}{1-Cx}$ (the case $C=0$ recovers $y\equiv 1$).

## 8.18 Homogeneous First-Order Equations

### 8.18.1 Definition

A first-order equation $y'=f(x,y)$ is **homogeneous** (of degree zero) if:

$$
f(tx,ty)=f(x,y)\qquad\text{for all }t\neq 0.
$$

Equivalently, setting $t=1/x$:

$$
y'=f\Bigl(1,\frac{y}{x}\Bigr).
$$

**Examples.** $y'=\dfrac{y-x}{y+x}$, $y'=\Bigl(\dfrac{x^{2}+y^{2}}{xy}\Bigr)^{3}$, $y'=\log x-\log y$.

### 8.18.2 Reduction to a Separable Equation

Substitute $v=y/x$ (so $y=vx$, $y'=v'x+v$). Then:

$$
x\frac{dv}{dx}=f(1,v)-v,
$$

which is separable. Solve for $v$, then replace $v$ by $y/x$.

### 8.18.3 Example: $y'=\dfrac{y-x}{y+x}$

Rewrite:

$$
y'=\frac{y/x-1}{y/x+1}=\frac{v-1}{v+1}.
$$

With $v=y/x$:

$$
x\frac{dv}{dx}=\frac{v-1}{v+1}-v=-\frac{1+v^{2}}{v+1}.
$$

Separate and integrate:

$$
\int\frac{v}{1+v^{2}}\,dv+\int\frac{1}{1+v^{2}}\,dv=-\int\frac{dx}{x}+C,
$$

$$
\frac{1}{2}\log(1+v^{2})+\arctan v=-\log|x|+C.
$$

Replace $v=y/x$ and simplify ($\log x^{2}=2\log|x|$):

$$
\frac{1}{2}\log(x^{2}+y^{2})+\arctan\frac{y}{x}=C.
$$

### 8.18.4 Geometric Property 鈥?Invariance under Similarity Transformations

A **similarity transformation** multiplies all coordinates by $k>0$. For a homogeneous equation:

- Straight lines through the origin are **isoclines**.
- If $S$ is an integral curve, so is $kS$ (the image of $S$ under similarity).

**Proof sketch.** Let $S$ be $y=F(x)$ with $F'(x)=f(x,F(x))$. The curve $kS$ is $y=G(x)$ where $G(x)=kF(x/k)$. Then:

$$
G'(x)=F'\Bigl(\frac{x}{k}\Bigr)=f\Bigl(\frac{x}{k},F\Bigl(\frac{x}{k}\Bigr)\Bigr)=f\Bigl(x,kF\Bigl(\frac{x}{k}\Bigr)\Bigr)=f(x,G(x)),
$$

using homogeneity with $t=k$. Hence $kS$ is also an integral curve.

> **Converse.** If the integral curves of $y'=f(x,y)$ are invariant under all similarity transformations, then the equation is necessarily homogeneous.

## 8.19 Geometrical and Physical Problems Leading to First-Order Equations

### 8.19.1 Orthogonal Trajectories

Two curves intersect **orthogonally** if their tangents are perpendicular at the intersection point.

- Given a family satisfying $y'=f(x,y)$, the orthogonal trajectories satisfy:
  $$
  y'=-\frac{1}{f(x,y)}.
  $$
- If the original equation is separable (or homogeneous), so is the orthogonal equation.

**Example.** Find orthogonal trajectories of circles through the origin with centers on the $x$-axis.

- Family: $x^{2}+y^{2}-2Cx=0$; differential equation: $y'=\dfrac{y^{2}-x^{2}}{2xy}$.
- Orthogonal equation: $y'=\dfrac{2xy}{x^{2}-y^{2}}$ (homogeneous).
- Substituting $v=y/x$ yields the family: $x^{2}+y^{2}-2Cy=0$.
- **Result:** circles through the origin with centers on the $y$-axis.

### 8.19.2 Pursuit Problems

Point $Q$ moves along $C_{1}$; point $P$ pursues $Q$ so that $P$'s velocity is always directed toward $Q$. The locus of $P$ is a **curve of pursuit**.

With $P=(x,y)$ and $Q=(X,Y)$:

$$
y'=\frac{Y-y}{X-x}.
$$

**Example (Tractrix).** $Q$ moves on the $y$-axis; $P$ stays at distance $k$ from $Q$ and starts at $(k,0)$.

- $X=0$, $(X-x)^{2}+(Y-y)^{2}=k^{2}$ gives $Y-y=\sqrt{k^{2}-x^{2}}$.
- $y'=\dfrac{\sqrt{k^{2}-x^{2}}}{-x}$.
- Substitute $x=k\cos t$, integrate with $y(k)=0$:
  $$
  y=k\log\frac{k+\sqrt{k^{2}-x^{2}}}{x}-\sqrt{k^{2}-x^{2}}.
  $$
- This curve is called the **tractrix**.

### 8.19.3 Flow of Fluid Through an Orifice

**Setup.** Tank with cross-sectional area $A(y)$; orifice area $A_{0}$; discharge coefficient $c\approx 0.60$.

- Volume rate of change: $dV/dt=-cA_{0}\sqrt{2gy}$.
- With $V(y)=\int_{0}^{y}A(u)\,du$, chain rule gives:
  $$
  A(y)\,\frac{dy}{dt}=-cA_{0}\sqrt{2gy}.
  $$
- Separating (with $g=32$):
  $$
  \int\frac{A(y)}{\sqrt{y}}\,dy=-4.8A_{0}\int dt+C.
  $$

**Example.** $A(y)=A$ constant; level drops from 10 ft to 9 ft in 10 min (600 s).

- $-\int_{10}^{9}\dfrac{dy}{\sqrt{y}}=k\int_{0}^{600}dt$, where $k=\dfrac{4.8A_{0}}{A}$.
- $k=\dfrac{\sqrt{10}-3}{300}$.
- Time to fall from 7 ft to 1 ft: $t_{2}-t_{1}=10\,\dfrac{\sqrt{7}-1}{\sqrt{10}-3}\approx 101.3$ min.

[<- Previous: 7. Polynomial Approximations to Functions](07-polynomial-approximations-to-functions.md) | [Next: 9. Complex Numbers ->](09-complex-numbers.md)
