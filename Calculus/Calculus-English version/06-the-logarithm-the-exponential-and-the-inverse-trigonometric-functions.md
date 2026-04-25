[<- Previous: 5. The Relation between Integration and Differentiation](05-the-relation-between-integration-and-differentiation.md) | [Next: 7. Polynomial Approximations to Functions ->](07-polynomial-approximations-to-functions.md)

# 6. The Logarithm, the Exponential, and the Inverse Trigonometric Functions

## 6.1 Introduction

This chapter studies three indispensable families of functions:
- the **logarithm** and its inverse, the **exponential**;
- the **inverse trigonometric functions**.

### 6.1.1 The Elementary-Algebra Viewpoint

In elementary algebra, the logarithm to base $b$ ($b>0$, $b\neq1$) is defined by:

$$
u=\log_{b}x\quad\Longleftrightarrow\quad x=b^{u}. \tag{6.1}
$$

The fundamental property follows from the law of exponents:

$$
\log_{b}(xy)=\log_{b}x+\log_{b}y. \tag{6.2}
$$

- Base $10$ is convenient for decimal calculations; e.g. $\log_{10}0.01=-2$, $\log_{10}1000=3$.

### 6.1.2 Logical Gaps in the Elementary Approach

Defining logarithms via (6.1) raises several difficulties:

| Gap | Issue |
|-----|-------|
| **Meaning of $b^{u}$** | Easy when $u$ is integer or rational, but nontrivial when $u$ is irrational (e.g. $10^{\sqrt2}$). |
| **Existence** | Must prove that for every $x>0$ there actually exists a real $u$ with $x=b^{u}$. |
| **Laws of exponents** | The identity $b^{u}b^{v}=b^{u+v}$ must be established for *all* real exponents before (6.2) can be derived from (6.1). |

Overcoming these gaps directly is possible but long and tedious.

### 6.1.3 The Calculus Approach

A simpler and more elegant route is available through calculus:

- **Define the logarithm first** (via integration).
- **Then use logarithms to define $b^{u}$**.

This reverses the elementary order and avoids the logical gaps above.

## 6.2 Motivation for Defining the Natural Logarithm as an Integral

### 6.2.1 The Functional Equation

A key property desired for logarithms is:

$$
f(xy)=f(x)+f(y). \tag{6.3}
$$

An equation relating the values of a function at two or more points is called a **functional equation**. Rather than guessing a formula, we determine all differentiable solutions of (6.3).

### 6.2.2 Elementary Consequences

Assume $f$ satisfies (6.3) and is defined at the points indicated.

| Substitution | Result |
|--------------|--------|
| $x=y=1$ | $f(1)=0$ |
| $x=y=-1$ | $f(-1)=0$ |
| $y=-1$ | $f(-x)=f(x)$ (so $f$ is **even**) |
| $y=0$ (if $0$ is in the domain) | $f\equiv0$ |

- The zero function is the **only** solution defined on all of $\mathbb{R}$.
- Any solution that is **not** identically zero **cannot** be defined at $0$.

### 6.2.3 Differentiability and the Integral Formula

Assume $f$ has a derivative at each $x\neq0$. Fix $y$ in (6.3) and differentiate with respect to $x$ (chain rule on the left):

$$
yf'(xy)=f'(x).
$$

Setting $x=1$:

$$
f'(y)=\frac{f'(1)}{y}\qquad(y\neq0).
$$

Since $f'$ is continuous on every closed interval not containing $0$, the second fundamental theorem gives, for $x>0$ and $c=1$ (using $f(1)=0$):

$$
f(x)=f'(1)\int_{1}^{x}\frac{1}{t}\,dt. \tag{6.4}
$$

Because $f$ is even, the formula for $x<0$ involves $\int_{1}^{|x|}$. Both cases are combined as:

$$
f(x)=f'(1)\int_{1}^{|x|}\frac{1}{t}\,dt\qquad(x\neq0). \tag{6.5}
$$

### 6.2.4 Normalization and the Key Insight

If $f$ is **not** identically zero, then $f'(1)\neq0$. Dividing (6.5) by $f'(1)$ yields:

$$
g(x)=\int_{1}^{|x|}\frac{1}{t}\,dt\qquad(x\neq0), \tag{6.6}
$$

where $g(x)=f(x)/f'(1)$. Since $cf$ is a solution of (6.3) whenever $f$ is, $g$ is also a solution, and **all** non-zero solutions are scalar multiples of $g$.

> **Important caveat:** The argument above assumed that a non-zero solution exists; it did **not** prove that the function $g$ in (6.6) actually satisfies (6.3).

**The reverse idea.** Use the integral in (6.6) to *define* a function, then verify directly that it satisfies (6.3). However, (6.6) gives $g(-x)=g(x)$, so distinct numbers would have the same logarithm. To ensure distinct numbers have distinct logarithms, we restrict the definition to **positive $x$ only**.

## 6.3 The Definition of the Logarithm and Its Basic Properties

### 6.3.1 Definition

If $x$ is a positive real number, the **natural logarithm** of $x$, denoted temporarily by $L(x)$, is defined by:

$$
L(x)=\int_{1}^{x}\frac{1}{t}\,dt. \tag{6.7}
$$

- For $x>1$, $L(x)$ is the area under the hyperbola $y=1/t$ from $t=1$ to $t=x$.
- For $0<x<1$, the integral is negative (area counted with opposite orientation).

### 6.3.2 Basic Properties

**Theorem 6.1.** The logarithm function $L$ has the following properties:

| Property | Statement | Proof |
|----------|-----------|-------|
| **(a)** | $L(1)=0$ | Immediate from the definition. |
| **(b)** | $L'(x)=\dfrac1x$ for every $x>0$ | $L$ is an indefinite integral of the continuous function $1/t$; apply the first fundamental theorem. |
| **(c)** | $L(ab)=L(a)+L(b)$ for all $a,b>0$ | Additivity of the integral plus the substitution $u=t/a$. |

**Proof of (c).** For $a,b>0$:
$$
\begin{aligned}
L(ab)&=\int_{1}^{ab}\frac{dt}{t}=\int_{1}^{a}\frac{dt}{t}+\int_{a}^{ab}\frac{dt}{t}\\[4pt]
&=L(a)+\int_{a}^{ab}\frac{dt}{t}.
\end{aligned}
$$
In the last integral set $u=t/a$, $du=dt/a$:
$$
\int_{a}^{ab}\frac{dt}{t}=\int_{1}^{b}\frac{du}{u}=L(b).
$$
Hence $L(ab)=L(a)+L(b)$. 鈭?
### 6.3.3 Graph of the Natural Logarithm

- $L(1)=0$; the graph passes through $(1,0)$.
- $L'(x)=1/x>0$, so $L$ is **strictly increasing**.
- $L''(x)=-1/x^{2}<0$, so the graph is **concave**.
- As $x\to0^{+}$, $L(x)\to-\infty$; as $x\to+\infty$, $L(x)\to+\infty$.

## 6.4 The Graph of the Natural Logarithm

The shape of $y=L(x)$ follows directly from Theorem 6.1 without elaborate calculation:

- **Strictly increasing**: $L'(x)=1/x>0$ for all $x>0$.
- **Zero at $x=1$**: $L(1)=0$, so the graph lies **above** the $x$-axis for $x>1$ and **below** it for $0<x<1$.
- **Unit slope at $x=1$**: $L'(1)=1$.
- **Slope tends to $0$ as $x\to+\infty$**: $L'(x)=1/x\to0$.
- **Slope blows up as $x\to0^{+}$**: $L'(x)=1/x\to+\infty$.
- **Concave everywhere**: $L''(x)=-1/x^{2}<0$ for all $x>0$.

## 6.5 Consequences of the Functional Equation $L(ab)=L(a)+L(b)$

### 6.5.1 Unboundedness

From $L(a^{n})=nL(a)$ (proved by induction using the functional equation):

- For any $M>0$, choose an integer $n>M/L(2)$. Then:
  $$
  L(2^{n})=nL(2)>M.
  $$
  Hence $L$ is **not bounded above**.
- Taking $b=1/a$ in the functional equation gives $L(1/a)=-L(a)$. Therefore:
  $$
  L\!igl(2^{-n}\bigr)=-L(2^{n})<-M,
  $$
  so $L$ is **not bounded below**.

### 6.5.2 Existence and Uniqueness

**Theorem 6.2.** For every real number $b$ there is exactly one positive real number $a$ such that $L(a)=b$.

**Proof sketch.**
- If $b>0$, pick $n$ with $L(2^{n})>b$. On $[1,2^{n}]$ we have $L(1)=0$ and $L(2^{n})>b$, so the intermediate-value theorem guarantees at least one $a$ with $L(a)=b$. Uniqueness follows from strict monotonicity.
- If $b<0$, use $L(1/a)=-L(a)$.
- If $b=0$, then $a=1$.

Thus the graph of $L$ crosses every horizontal line exactly once.

### 6.5.3 The Number $e$

Since $L$ takes the value $1$ exactly once, we make the following definition.

**Definition.** We denote by $e$ the unique positive number for which:

$$
L(e)=1. \tag{6.8}
$$

- **Decimal value**: $e\approx2.7182818285\dots$
- **History**: The notation $e$ was introduced by Leonard Euler (1707--1783). Natural logarithms are also called **Napierian logarithms** (after John Napier, 1550--1617).
- **Notation**: The symbols $\ln x$ or $\log x$ are commonly used instead of $L(x)$.
- **Preview** (Chapter 7): explicit formulas for computing $e$ to any accuracy, and a proof that $e$ is irrational.

## 6.6 Logarithms to Any Positive Base $b\neq1$

### 6.6.1 General Solution of the Functional Equation

The most general differentiable solution of $f(xy)=f(x)+f(y)$ on the positive real axis is:

$$
f(x)=c\log x, \tag{6.9}
$$

where $c$ is a constant. When $c\neq0$, there is a unique $b>0$ with $f(b)=1$. Since $c\log b=1$, we obtain $c=1/\log b$ and (6.9) becomes:

$$
f(x)=\frac{\log x}{\log b}.
$$

### 6.6.2 Definition

**Definition.** If $b>0$, $b\neq1$, and $x>0$, the **logarithm of $x$ to the base $b$** is:

$$
\log_{b}x=\frac{\log x}{\log b}, \tag{6.10}
$$

where the logarithms on the right are natural logarithms.

- $\log_{b}b=1$.
- When $b=e$: $\log_{e}x=\log x$; natural logarithms are exactly those with base $e$.
- In higher mathematics the word "logarithm" almost invariably means **natural** logarithm.

### 6.6.3 Graphs

The graph of $y=\log_{b}x$ is obtained from $y=\log x$ by multiplying all ordinates by the factor $1/\log b$:

| Range of $b$ | Factor $1/\log b$ | Shape |
|--------------|-------------------|-------|
| $b>1$ | Positive | Same general shape as $\log x$, steeper if $1<b<e$, flatter if $b>e$. |
| $0<b<1$ | Negative | Reflection of $y=\log_{1/b}x$ through the $x$-axis. |

## 6.7 Differentiation and Integration Formulas Involving Logarithms

### 6.7.1 Basic Formulas

Since $D\log x=1/x$ for $x>0$:

$$
\int\frac{1}{x}\,dx=\log x+C.
$$

More generally, if $u=f(x)$ with $f$ continuously differentiable:

$$
\int\frac{du}{u}=\log u+C\qquad\text{or}\qquad\int\frac{f'(x)}{f(x)}\,dx=\log f(x)+C. \tag{6.11}
$$

> **Caution**: (6.11) is valid only when $u$ (or $f(x)$) is **positive**, because the logarithm is not defined for negative numbers.

### 6.7.2 Extension to Nonzero Values 鈥?The Function $L_{0}$

To accommodate functions that may be negative, define:

$$
L_{0}(x)=\log|x|=\int_{1}^{|x|}\frac{1}{t}\,dt\qquad(x\neq0). \tag{6.12}
$$

- $L_{0}$ is even; its graph is symmetric about the $y$-axis (Figure 6.4).
- $L_{0}$ also satisfies the functional equation $L_{0}(xy)=L_{0}(x)+L_{0}(y)$ for all nonzero $x,y$.
- Its derivative is:
  $$
  L_{0}'(x)=\frac{1}{x}\qquad\text{for all }x\neq0. \tag{6.13}
  $$

Hence the integration formulas extend to:

$$
\int\frac{du}{u}=\log|u|+C,\qquad\int\frac{f'(x)}{f(x)}\,dx=\log|f(x)|+C. \tag{6.14}
$$

> When evaluating definite integrals with (6.14), avoid intervals containing points where $u$ or $f(x)$ is zero.

### 6.7.3 Examples

**Example 1.** $\displaystyle\int\tan x\,dx$.
- Write $\tan x=-(\cos x)'/\cos x$. With $u=\cos x$:
  $$
  \int\tan x\,dx=-\int\frac{du}{u}=-\log|u|+C=-\log|\cos x|+C,
  $$
  valid on any interval where $\cos x\neq0$.

**Example 2.** $\displaystyle\int\log x\,dx$ (integration by parts).
- Let $u=\log x$, $dv=dx$ $\Rightarrow$ $du=dx/x$, $v=x$.
  $$
  \int\log x\,dx=x\log x-\int x\cdot\frac{1}{x}\,dx=x\log x-x+C.
  $$

**Example 3.** $\displaystyle\int\sin(\log x)\,dx$ and $\displaystyle\int\cos(\log x)\,dx$.
- For $\int\sin(\log x)\,dx$, let $u=\sin(\log x)$, $dv=dx$:
  $$
  \int\sin(\log x)\,dx=x\sin(\log x)-\int\cos(\log x)\,dx.
  $$
- Apply parts again to $\int\cos(\log x)\,dx$:
  $$
  \int\cos(\log x)\,dx=x\cos(\log x)+\int\sin(\log x)\,dx.
  $$
- Solving the two equations simultaneously:
  $$
  \begin{aligned}
  \int\sin(\log x)\,dx&=\tfrac12x\sin(\log x)-\tfrac12x\cos(\log x)+C,\\[4pt]
  \int\cos(\log x)\,dx&=\tfrac12x\sin(\log x)+\tfrac12x\cos(\log x)+C.
  \end{aligned}
  $$

## 6.8 Logarithmic Differentiation

A technique developed by Johann Bernoulli (1697) for computing derivatives of products or quotients.

### 6.8.1 The Method

Set:

$$
g(x)=\log|f(x)|.
$$

By the chain rule and $L_{0}'(x)=1/x$:

$$
g'(x)=\frac{f'(x)}{f(x)}. \tag{6.15}
$$

Hence:

$$
f'(x)=f(x)\,g'(x).
$$

The idea is that $g'(x)$ is often easier to compute than $f'(x)$ directly, especially when $f$ is a product or quotient of several simpler functions.

### 6.8.2 Example

Compute $f'(x)$ for:

$$
f(x)=x^{2}\cos x\,(1+x^{4})^{-7}.
$$

Take logarithms:
$$
\begin{aligned}
g(x)&=\log|f(x)|\\
&=2\log|x|+\log|\cos x|-7\log(1+x^{4}).
\end{aligned}
$$

Differentiate term by term:
$$
g'(x)=\frac{2}{x}-\tan x-\frac{28x^{3}}{1+x^{4}}.
$$

Multiply by $f(x)$:
$$
f'(x)=\frac{2x\cos x}{(1+x^{4})^{7}}-\frac{x^{2}\sin x}{(1+x^{4})^{7}}-\frac{28x^{5}\cos x}{(1+x^{4})^{8}}.
$$

## 6.9 Polynomial Approximations to the Logarithm

### 6.9.1 Setting Up the Integral

Replace $x$ by $1-x$ in the defining integral:

$$
\log(1-x)=\int_{1}^{1-x}\frac{dt}{t}\qquad(x<1).
$$

The change of variable $t=1-u$ gives:

$$
-\log(1-x)=\int_{0}^{x}\frac{du}{1-u}\qquad(x<1). \tag{6.16}
$$

### 6.9.2 The Approximating Polynomials

From $1-u^{n}=(1-u)(1+u+\dots+u^{n-1})$:

$$
\frac{1}{1-u}=1+u+\dots+u^{n-1}+\frac{u^{n}}{1-u}.
$$

Integrating from $0$ to $x$ ($x<1$) yields:

**Theorem 6.3.** Let
$$
P_{n}(x)=\sum_{k=1}^{n}\frac{x^{k}}{k}=x+\frac{x^{2}}{2}+\dots+\frac{x^{n}}{n}.
$$
Then for every $x<1$ and $n\ge1$:

$$
-\log(1-x)=P_{n}(x)+E_{n}(x), \tag{6.17}
$$

where the error term is:

$$
E_{n}(x)=\int_{0}^{x}\frac{u^{n}}{1-u}\,du.
$$

### 6.9.3 Error Estimates

**Theorem 6.4.** The error $E_{n}(x)$ satisfies:

- If $0<x<1$:
  $$
  \frac{x^{n+1}}{n+1}\le E_{n}(x)\le\frac{1}{1-x}\cdot\frac{x^{n+1}}{n+1}. \tag{6.18}
  $$

- If $x<0$:
  $$
  0<(-1)^{n+1}E_{n}(x)\le\frac{|x|^{n+1}}{n+1}. \tag{6.19}
  $$

**Proof sketch.** For $0<x<1$, use $1-x\le1-u\le1$ on $[0,x]$ to bound the integrand $u^{n}/(1-u)$. For $x<0$, set $t=-x$ and observe the sign alternation. 鈭?
### 6.9.4 A Formula for Computation

Subtracting (6.17) at $-x$ from (6.17) at $x$ (valid for $-1<x<1$) eliminates even powers:

**Theorem 6.5.** If $0<x<1$ and $m\ge1$:

$$
\log\frac{1+x}{1-x}=2\Bigl(x+\frac{x^{3}}{3}+\dots+\frac{x^{2m-1}}{2m-1}\Bigr)+R_{m}(x), \tag{6.20}
$$

where:

$$
\frac{x^{2m+1}}{2m+1}<R_{m}(x)\le\frac{2-x}{1-x}\cdot\frac{x^{2m+1}}{2m+1}. \tag{6.21}
$$

- **Example** ($m=2$, $x=\tfrac13$): since $(1+x)/(1-x)=2$,
  $$
  \log2=2\Bigl(\tfrac13+\tfrac1{81}\Bigr)+R_{2}\bigl(\tfrac13\bigr),\qquad\tfrac1{486}<R_{2}\bigl(\tfrac13\bigr)\le\tfrac5{486},
  $$
  giving $0.6921<\log2<0.6935$.

## 6.10 The Exponential Function

### 6.10.1 Definition

Theorem 6.2 shows that for every real $x$ there is a unique $y>0$ with $L(y)=x$. The **exponential function** (or **antilogarithm**), denoted $E$, is the inverse of $L$:

$$
y=E(x)\quad\Longleftrightarrow\quad L(y)=x.
$$

- **Domain**: all real numbers; **range**: $(0,+\infty)$.
- The graph of $E$ is the reflection of the graph of $L$ through the line $y=x$ (Figure 6.6).
- Inverse relations:
  $$
  L[E(x)]=x\quad\text{for all }x,\qquad E[L(y)]=y\quad\text{for all }y>0.
  $$

### 6.10.2 Basic Properties

**Theorem 6.6.** The exponential function satisfies:

| Property | Statement |
|----------|-----------|
| **(a)** | $E(0)=1$, $E(1)=e$. |
| **(b)** | $E'(x)=E(x)$ for every $x$. |
| **(c)** | $E(a+b)=E(a)E(b)$ for all $a,b$. |

**Proof.**
- **(a)** Follows from $L(1)=0$ and $L(e)=1$.
- **(c)** Let $x=E(a)$, $y=E(b)$, $c=L(xy)$. Then $L(x)=a$, $L(y)=b$, and $c=L(xy)=L(x)+L(y)=a+b$. Hence $E(a+b)=E(c)=xy=E(a)E(b)$.
- **(b)** Using (c), the difference quotient is:
  $$
  \frac{E(x+h)-E(x)}{h}=E(x)\,\frac{E(h)-1}{h}.
  $$
  Set $k=E(h)-1$; then $h=L(k+1)$ and
  $$
  \frac{E(h)-1}{h}=\frac{k}{L(k+1)}=\frac{1}{[L(k+1)-L(1)]/k}\to\frac{1}{L'(1)}=1
  $$
  as $h\to0$ (so $k\to0$). Thus $E'(x)=E(x)$. 鈭?
## 6.11 Exponentials Expressed as Powers of $e$

The functional equation $E(a+b)=E(a)E(b)$ implies:

$$
E(-a)=\frac{1}{E(a)},\qquad E(na)=E(a)^{n}\quad(n\in\mathbb{Z}^{+}).
$$

Taking $a=1$ gives $E(n)=e^{n}$; taking $a=1/n$ gives $E(1/n)=e^{1/n}$. Combining these:

$$
E\Bigl(\frac{n}{m}\Bigr)=E\Bigl(\frac1m\Bigr)^{n}=e^{n/m}
$$

for all positive integers $m,n$. Since $E(-r)=1/E(r)$, we obtain:

$$
\boxed{E(r)=e^{r}\quad\text{for every rational number }r.} \tag{6.22}
$$

## 6.12 The Definition of $e^{x}$ for Arbitrary Real $x$

For rational $r$ we have $e^{r}=E(r)$. We **define** $e^{x}$ for irrational $x$ by the same formula:

$$
e^{x}=E(x)\qquad\text{for every real }x. \tag{6.23}
$$

- **Justification**: with this definition the law of exponents
  $$
  e^{a}e^{b}=e^{a+b}
  $$
  holds for **all** real $a,b$, because it is simply a restatement of the functional equation $E(a+b)=E(a)E(b)$.
- **Notation**: $e^{x}$ (or $\exp x$) is the standard symbol; $E(x)$ is still used occasionally in this chapter.
- The two equations $y=e^{x}$ and $x=\log y$ mean exactly the same thing.

## 6.13 The Definition of $a^{x}$ for $a>0$ and $x$ Real

Now that $e^{x}$ is defined for arbitrary real $x$, we define general powers by:

$$
a^{x}=e^{x\log a}\qquad(a>0,\;x\in\mathbb{R}). \tag{6.24}
$$

This definition is preferable because it is meaningful for **all** positive $a$ (including $a=1$) and makes the following properties immediate:

$$
\begin{aligned}
\log a^{x}&=x\log a, & (ab)^{x}&=a^{x}b^{x},\\
a^{x}a^{y}&=a^{x+y}, & (a^{x})^{y}&=(a^{y})^{x}=a^{xy}.
\end{aligned}
$$

- If $a\neq1$, then $y=a^{x}\iff x=\log_{a}y$.
- The graph of $y=a^{x}$ is the reflection of $y=\log_{a}x$ through the line $y=x$.
- The case $a=1$ gives the horizontal line $y=1$.

## 6.14 Differentiation and Integration Formulas Involving Exponentials

### 6.14.1 Differentiation

The most remarkable property of the exponential is that it equals its own derivative:

$$
E'(x)=E(x). \tag{6.25}
$$

For a general base $a>0$, write $a^{x}=e^{x\log a}=E(x\log a)$. By the chain rule:

$$
\frac{d}{dx}(a^{x})=a^{x}\log a\qquad(a>0). \tag{6.26}
$$

The factor $\log a$ equals $1$ when $a=e$.

### 6.14.2 Integration 鈥?Basic Formulas

From the derivatives above:

$$
\int e^{x}\,dx=e^{x}+C,\qquad\int a^{x}\,dx=\frac{a^{x}}{\log a}+C\quad(a>0,\;a\neq1). \tag{6.27}
$$

With substitution $u=f(x)$, $du=f'(x)\,dx$:

$$
\int e^{f(x)}f'(x)\,dx=e^{f(x)}+C,\qquad\int a^{f(x)}f'(x)\,dx=\frac{a^{f(x)}}{\log a}+C.
$$

### 6.14.3 Examples

**Example 1.** $\displaystyle\int x^{2}e^{x^{3}}\,dx$.
- Let $u=x^{3}$, $du=3x^{2}\,dx$:
  $$
  \int x^{2}e^{x^{3}}\,dx=\tfrac13\int e^{u}\,du=\tfrac13e^{x^{3}}+C.
  $$

**Example 2.** $\displaystyle\int\frac{2^{\sqrt{x}}}{\sqrt{x}}\,dx$.
- Let $u=\sqrt{x}$, $du=\frac{1}{2\sqrt{x}}\,dx$:
  $$
  \int\frac{2^{\sqrt{x}}}{\sqrt{x}}\,dx=2\int2^{u}\,du=\frac{2^{1+\sqrt{x}}}{\log2}+C.
  $$

**Example 3.** $\displaystyle\int\cos x\,e^{2\sin x}\,dx$.
- Let $u=2\sin x$, $du=2\cos x\,dx$:
  $$
  \int\cos x\,e^{2\sin x}\,dx=\tfrac12\int e^{u}\,du=\tfrac12e^{2\sin x}+C.
  $$

**Example 4.** $\displaystyle\int e^{x}\sin x\,dx$ and $\displaystyle\int e^{x}\cos x\,dx$ (integration by parts).
- Set $u=e^{x}$, $dv=\sin x\,dx$:
  $$
  \int e^{x}\sin x\,dx=-e^{x}\cos x+\int e^{x}\cos x\,dx. \tag{6.28}
  $$
- Set $u=e^{x}$, $dv=\cos x\,dx$:
  $$
  \int e^{x}\cos x\,dx=e^{x}\sin x-\int e^{x}\sin x\,dx. \tag{6.29}
  $$
- Solving (6.28) and (6.29) simultaneously:
  $$
  \begin{aligned}
  \int e^{x}\sin x\,dx&=\tfrac12e^{x}(\sin x-\cos x)+C,\\[4pt]
  \int e^{x}\cos x\,dx&=\tfrac12e^{x}(\sin x+\cos x)+C.
  \end{aligned}
  $$

**Example 5.** $\displaystyle\int\frac{dx}{1+e^{x}}$.
- Rewrite $\dfrac1{1+e^{x}}=\dfrac{e^{-x}}{e^{-x}+1}$ and let $u=e^{-x}+1$:
  $$
  \int\frac{dx}{1+e^{x}}=-\log(1+e^{-x})+C=x-\log(1+e^{x})+C.
  $$
- Alternatively, write $\dfrac1{1+e^{x}}=1-\dfrac{e^{x}}{1+e^{x}}$ and let $u=1+e^{x}$:
  $$
  \int\frac{dx}{1+e^{x}}=x-\log(1+e^{x})+C.
  $$

## 6.15 The Hyperbolic Functions

Combinations of exponentials that occur frequently in analysis:

$$
\begin{aligned}
\sinh x&=\frac{e^{x}-e^{-x}}{2}, & \cosh x&=\frac{e^{x}+e^{-x}}{2}, & \tanh x&=\frac{\sinh x}{\cosh x}=\frac{e^{x}-e^{-x}}{e^{x}+e^{-x}},\\[4pt]
\csch x&=\frac{1}{\sinh x}, & \sech x&=\frac{1}{\cosh x}, & \coth x&=\frac{1}{\tanh x}.
\end{aligned}
$$

- The name "hyperbolic" comes from the geometric relation to a hyperbola (analogous to the relation of trigonometric functions to a circle); discussed in detail in Chapter 14.
- The hyperbolic functions possess many properties that resemble those of the trigonometric functions.

**Graphs** (Figure 6.8):
- $y=\sinh x$: odd, strictly increasing, passes through the origin.
- $y=\cosh x$: even, U-shaped with minimum $1$ at $x=0$.
- $y=\tanh x$: odd, increasing, horizontal asymptotes $y=\pm1$.

## 6.16 Derivatives of Inverse Functions

**Theorem 6.7.** Assume $f$ is strictly increasing and continuous on $[a,b]$, and let $g$ be the inverse of $f$. If $f'(x)$ exists and is nonzero at a point $x$ in $(a,b)$, then $g'(y)$ also exists and is nonzero at the corresponding point $y=f(x)$. Moreover:

$$
g'(y)=\frac{1}{f'(x)}. \tag{6.30}
$$

**Leibniz form.** With $y=f(x)$, $\dfrac{dy}{dx}=f'(x)$, $x=g(y)$, $\dfrac{dx}{dy}=g'(y)$:

$$
\frac{dx}{dy}=\frac{1}{\,\dfrac{dy}{dx}\,}.
$$

**Proof sketch.** Let $h=g(y+k)-g(y)$. Then $y+k=f(x+h)$ and $k=f(x+h)-f(x)$. Since $g$ is continuous, $h\to0$ as $k\to0$. The difference quotient becomes:

$$
\frac{g(y+k)-g(y)}{k}=\frac{h}{f(x+h)-f(x)}=\frac{1}{[f(x+h)-f(x)]/h}\to\frac{1}{f'(x)}
$$

as $k\to0$. 鈭?
## 6.17 Inverses of the Trigonometric Functions

### 6.17.1 Arc Sine

Restrict $\sin x$ to the interval $[-\tfrac{\pi}{2},\tfrac{\pi}{2}]$, where it is strictly increasing and takes every value in $[-1,1]$ exactly once.

**Definition.** $u=\arcsin v$ means $v=\sin u$ with $-\tfrac{\pi}{2}\le u\le\tfrac{\pi}{2}$.

- **Domain**: $[-1,1]$; **range**: $[-\pi/2,\pi/2]$.
- **Derivative** (from Theorem 6.7 with $f(x)=\sin x$, $f'(x)=\cos x$):
  $$
  D\arcsin x=\frac{1}{\sqrt{1-x^{2}}}\qquad(-1<x<1). \tag{6.31}
  $$
- **Integration formulas**:
  $$
  \int_{0}^{x}\frac{dt}{\sqrt{1-t^{2}}}=\arcsin x,\qquad\int\frac{dx}{\sqrt{1-x^{2}}}=\arcsin x+C.
  $$
- **By parts**:
  $$
  \int\arcsin x\,dx=x\arcsin x+\sqrt{1-x^{2}}+C.
  $$

> **Note**: Formula (6.31) can serve as the starting point for a purely analytic theory of the trigonometric functions, with no reference to geometry.

### 6.17.2 Arc Cosine

Restrict $\cos x$ to $[0,\pi]$.

**Definition.** $u=\arccos v$ means $v=\cos u$ with $0\le u\le\pi$.

- **Derivative**:
  $$
  D\arccos x=\frac{-1}{\sqrt{1-x^{2}}}\qquad(-1<x<1). \tag{6.32}
  $$
- **Relation to arc sine**:
  $$
  \arcsin x+\arccos x=\frac{\pi}{2}.
  $$
- **Integration formulas**:
  $$
  \int\frac{dx}{\sqrt{1-x^{2}}}=-\arccos x+C,\qquad\int\arccos x\,dx=x\arccos x-\sqrt{1-x^{2}}+C.
  $$

### 6.17.3 Arc Tangent

Restrict $\tan x$ to $(-\tfrac{\pi}{2},\tfrac{\pi}{2})$.

**Definition.** $u=\arctan v$ means $v=\tan u$ with $-\tfrac{\pi}{2}<u<\tfrac{\pi}{2}$.

- **Derivative**:
  $$
  D\arctan x=\frac{1}{1+x^{2}}\qquad(\text{all real }x). \tag{6.33}
  $$
- **Integration formulas**:
  $$
  \int_{0}^{x}\frac{dt}{1+t^{2}}=\arctan x,\qquad\int\frac{dx}{1+x^{2}}=\arctan x+C.
  $$
- **By parts**:
  $$
  \int\arctan x\,dx=x\arctan x-\tfrac12\log(1+x^{2})+C.
  $$

### 6.17.4 Other Inverse Trigonometric Functions

| Function | Definition | Domain |
|----------|-----------|--------|
| $\arccot x$ | $\dfrac{\pi}{2}-\arctan x$ | all real $x$ |
| $\arcsec x$ | $\arccos\dfrac1x$ | $|x|\ge1$ |
| $\arccsc x$ | $\arcsin\dfrac1x$ | $|x|\ge1$ |

## 6.18 Integration by Partial Fractions

Every rational function can be integrated in terms of polynomials, logarithms, and inverse tangents.

### 6.18.1 Preliminaries

- A quotient $f(x)/g(x)$ of two polynomials is a **rational function**.
- It is **proper** if $\deg f<\deg g$; otherwise divide to obtain a polynomial plus a proper part:
  $$
  \frac{f(x)}{g(x)}=Q(x)+\frac{R(x)}{g(x)}.
  $$
- **Algebraic theorem**: every proper rational function is a finite sum of fractions of the two types:
  $$
  \frac{A}{(x+a)^{k}},\qquad\frac{Bx+C}{(x^{2}+bx+c)^{m}},
  $$
  where $x^{2}+bx+c$ is **irreducible** ($b^{2}-4c<0$).

### 6.18.2 Case 1 鈥?Distinct Linear Factors

If $g(x)=(x-x_{1})(x-x_{2})\cdots(x-x_{n})$, then:

$$
\frac{f(x)}{g(x)}=\frac{A_{1}}{x-x_{1}}+\cdots+\frac{A_{n}}{x-x_{n}}.
$$

**Example.** $\displaystyle\int\frac{2x^{2}+5x-1}{x^{3}+x^{2}-2x}\,dx$.
- $x^{3}+x^{2}-2x=x(x-1)(x+2)$.
- $A_{1}=\tfrac12$, $A_{2}=2$, $A_{3}=-\tfrac12$ (cover-up method).
- Result: $\tfrac12\log|x|+2\log|x-1|-\tfrac12\log|x+2|+C$.

### 6.18.3 Case 2 鈥?Repeated Linear Factors

If $(x+a)^{p}$ occurs, include $p$ terms:

$$
\sum_{k=1}^{p}\frac{A_{k}}{(x+a)^{k}}.
$$

**Example.** $\displaystyle\int\frac{x^{2}+2x+3}{(x-1)(x+1)^{2}}\,dx$.
- Decompose as $\dfrac{A_{1}}{x-1}+\dfrac{A_{2}}{x+1}+\dfrac{A_{3}}{(x+1)^{2}}$.
- $A_{1}=\tfrac32$, $A_{3}=-1$ (cover-up); $A_{2}=-\tfrac12$ (substitute $x=0$ or differentiate).
- Result: $\tfrac32\log|x-1|-\tfrac12\log|x+1|+\dfrac{1}{x+1}+C$.

### 6.18.4 Case 3 鈥?Distinct Irreducible Quadratics

**Example.** $\displaystyle\int\frac{3x^{2}+2x-2}{x^{3}-1}\,dx$.
- $x^{3}-1=(x-1)(x^{2}+x+1)$.
- Decompose: $\dfrac{1}{x-1}+\dfrac{2x+3}{x^{2}+x+1}$.
- Second term: split into $\dfrac{2x+1}{x^{2}+x+1}$ (log) and $\dfrac{2}{(x+\tfrac12)^{2}+\tfrac34}$ (arctan).
- Result: $\log|x-1|+\log(x^{2}+x+1)+\tfrac{4}{\sqrt3}\arctan\!\bigl(\tfrac{2x+1}{\sqrt3}\bigr)+C$.

### 6.18.5 Case 4 鈥?Repeated Irreducible Quadratics

If $(x^{2}+bx+c)^{m}$ occurs, include $m$ terms with linear numerators:

$$
\sum_{k=1}^{m}\frac{B_{k}x+C_{k}}{(x^{2}+bx+c)^{k}}.
$$

**Example.** $\displaystyle\int\frac{x^{4}-x^{3}+2x^{2}-x+2}{(x-1)(x^{2}+2)^{2}}\,dx$.
- Decompose: $\dfrac{A}{x-1}+\dfrac{Bx+C}{x^{2}+2}+\dfrac{Dx+E}{(x^{2}+2)^{2}}$.
- Constants: $A=\tfrac13$, $B=\tfrac23$, $C=-\tfrac13$, $D=-1$, $E=0$.
- Result: $\tfrac13\log|x-1|+\tfrac13\log(x^{2}+2)-\tfrac{\sqrt2}{6}\arctan\!\bigl(\tfrac{x}{\sqrt2}\bigr)+\dfrac{1}{2(x^{2}+2)}+C$.

### 6.18.6 The Basic Integrals

All partial-fraction integrals reduce to the three forms below.

| Form | Technique | Result |
|------|-----------|--------|
| $\displaystyle\int\frac{dx}{(x+a)^{n}}$ | Direct power rule | $\log|x+a|$ if $n=1$; $\dfrac{(x+a)^{1-n}}{1-n}$ if $n>1$ |
| $\displaystyle\int\frac{x\,dx}{(x^{2}+bx+c)^{m}}$ | Write numerator as derivative of quadratic | $\tfrac12\log(x^{2}+bx+c)$ if $m=1$ |
| $\displaystyle\int\frac{dx}{(x^{2}+bx+c)^{m}}$ | Complete the square: $u^{2}+\alpha^{2}$ | $\dfrac1\alpha\arctan\!\bigl(\tfrac u\alpha\bigr)$ if $m=1$; reduction formula for $m>1$ |

**Reduction formula** (for $m>1$):

$$
\int\frac{du}{(u^{2}+\alpha^{2})^{m}}=\frac{u}{2\alpha^{2}(m-1)(u^{2}+\alpha^{2})^{m-1}}+\frac{2m-3}{2\alpha^{2}(m-1)}\int\frac{du}{(u^{2}+\alpha^{2})^{m-1}}.
$$

## 6.19 Integrals Reducible to Rational Functions

### 6.19.1 The Weierstrass Substitution

For integrals of the form $\displaystyle\int R(\sin x,\cos x)\,dx$ (where $R$ is a rational function of two variables), the substitution:

$$
u=\tan\tfrac{x}{2}
$$

converts the integrand into a rational function of $u$:

$$
\sin x=\frac{2u}{1+u^{2}},\qquad\cos x=\frac{1-u^{2}}{1+u^{2}},\qquad dx=\frac{2\,du}{1+u^{2}}.
$$

**Example 1.** $\displaystyle\int\frac{dx}{\sin x+\cos x}$.
- With $u=\tan\tfrac{x}{2}$ the integral becomes $-2\displaystyle\int\frac{du}{u^{2}-2u-1}$.
- Factor $u^{2}-2u-1=(u-a)(u-b)$ with $a=1+\sqrt2$, $b=1-\sqrt2$.
- Partial fractions give:
  $$
  \int\frac{dx}{\sin x+\cos x}=\frac{\sqrt2}{2}\log\Bigl|\tan\Bigl(\frac{x}{2}+\frac{\pi}{8}\Bigr)\Bigr|+C.
  $$

### 6.19.2 Trigonometric Substitutions for Radicals

| Radical form | Substitution | Differential | Simplification |
|--------------|--------------|--------------|----------------|
| $\sqrt{a^{2}-(cx+d)^{2}}$ | $cx+d=a\sin t$ | $c\,dx=a\cos t\,dt$ | $\sqrt{\cdots}=a\cos t$ |
| $\sqrt{a^{2}+(cx+d)^{2}}$ | $cx+d=a\tan t$ | $c\,dx=a\sec^{2}t\,dt$ | $\sqrt{\cdots}=a\sec t$ |
| $\sqrt{(cx+d)^{2}-a^{2}}$ | $cx+d=a\sec t$ | $c\,dx=a\sec t\tan t\,dt$ | $\sqrt{\cdots}=a\tan t$ |

In each case the new integrand becomes a rational function of $\sin t$ and $\cos t$.

**Example 2.** $\displaystyle\int\frac{x\,dx}{4-x^{2}+\sqrt{4-x^{2}}}$.
- Let $x=2\sin t$, $dx=2\cos t\,dt$, $\sqrt{4-x^{2}}=2\cos t$.
- The integral simplifies to $\displaystyle\int\frac{\sin t\,dt}{\cos t+\tfrac12}=-\log\Bigl|\tfrac12+\cos t\Bigr|+C=-\log\bigl(1+\sqrt{4-x^{2}}\bigr)+C$.

[<- Previous: 5. The Relation between Integration and Differentiation](05-the-relation-between-integration-and-differentiation.md) | [Next: 7. Polynomial Approximations to Functions ->](07-polynomial-approximations-to-functions.md)
