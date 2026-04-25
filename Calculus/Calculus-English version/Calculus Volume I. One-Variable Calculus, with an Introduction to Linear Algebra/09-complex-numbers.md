[<- Previous: 8. Introduction to Differential Equations](08-introduction-to-differential-equations.md) | [Next: 10. Sequences, Infinite Series, Improper Integrals ->](10-sequences-infinite-series-improper-integrals.md)

# 9. Complex Numbers

## 9.1 Historical Introduction

The equation $x^{2}+1=0$ has no solution in the real-number system. **Complex numbers** were introduced to provide solutions to such equations.

- **16th century:** The symbol $\sqrt{-1}$ was introduced; later denoted by $i$.
- Early view: $i$ was a fictitious number whose square is $-1$. Expressions like $2+3i$ were used formally for nearly 300 years.
- **19th century:** Gauss and Hamilton independently proposed defining complex numbers as **ordered pairs** $(a,b)$ of real numbers with special arithmetic rules.

## 9.2 Definitions and Field Properties

### 9.2.1 Definition

If $a,b\in\mathbb{R}$, the pair $(a,b)$ is a **complex number**.

| Operation | Definition |
|-----------|-----------|
| **Equality** | $(a,b)=(c,d)\iff a=c$ and $b=d$ |
| **Sum** | $(a,b)+(c,d)=(a+c,\;b+d)$ |
| **Product** | $(a,b)(c,d)=(ac-bd,\;ad+bc)$ |

The number $a$ is the **real part**; $b$ is the **imaginary part**.

### 9.2.2 Theorem 9.1 鈥?Field Axioms

The set of all complex numbers satisfies the six field axioms:

| Axiom | Element | Property |
|-------|---------|----------|
| 1鈥? | 鈥?| Commutative, associative, distributive laws (addition and multiplication) |
| 4 | $(0,0)$ | Additive identity |
| 4 | $(1,0)$ | Multiplicative identity |
| 5 | $(-a,-b)$ | Additive inverse: $-(a,b)$ |
| 6 | $\bigl(\dfrac{a}{a^{2}+b^{2}},\dfrac{-b}{a^{2}+b^{2}}\bigr)$ | Multiplicative inverse (reciprocal), for $(a,b)\neq(0,0)$ |

**Quotient.** For $(a,b)\neq(0,0)$:

$$
\frac{(c,d)}{(a,b)}=(c,d)\,(a,b)^{-1}.
$$

> Since all field axioms hold, every algebraic law valid for real numbers (Theorems I.1鈥揑.15) extends to complex numbers.

## 9.3 Complex Numbers as an Extension of the Real Numbers

Let $C_{0}=\{(a,0):a\in\mathbb{R}\}$ be the set of complex numbers with zero imaginary part.

- **Addition and multiplication in $C_{0}$:**
  $$
  (a,0)+(b,0)=(a+b,0),\qquad (a,0)(b,0)=(ab,0).
  $$
- The map $f(x)=(x,0)$ is a **one-to-one correspondence** $\mathbb{R}\to C_{0}$ preserving both operations:
  $$
  f(a+b)=f(a)+f(b),\qquad f(ab)=f(a)f(b).
  $$
- Hence $\mathbb{R}$ and $C_{0}$ are **isomorphic**; we identify $x\leftrightarrow(x,0)$.
- In particular: $0=(0,0)$, $1=(1,0)$, $-1=(-1,0)$.
- $C_{0}$ is an **ordered field**: $(x,0)>0\iff x>0$.

## 9.4 The Imaginary Unit $i$

### 9.4.1 Definition

The complex number $(0,1)$ satisfies:

$$
(0,1)^{2}=(0,1)(0,1)=(-1,0)=-1.
$$

We denote it by $i$ and call it the **imaginary unit**:

$$
i^{2}=-1.
$$

### 9.4.2 The Standard Form $a+bi$

Since $(b,0)(0,1)=(0,b)$:

$$
(a,b)=(a,0)+(b,0)(0,1)=a+bi.
$$

**Theorem 9.2.** Every complex number can be written uniquely as $a+bi$ with $a,b\in\mathbb{R}$.

**Algebraic manipulations.** Using $i^{2}=-1$:

$$
(a+bi)(c+di)=ac-bd+(ad+bc)i.
$$

$$
\frac{1}{a+bi}=\frac{a-bi}{a^{2}+b^{2}}=\frac{a}{a^{2}+b^{2}}-\frac{b}{a^{2}+b^{2}}i\qquad(a+bi\neq 0).
$$

### 9.4.3 Quadratic Equations

For $ax^{2}+bx+c=0$ with real coefficients:

- If $b^{2}-4ac\ge 0$: real roots $\dfrac{-b\pm\sqrt{b^{2}-4ac}}{2a}$.
- If $b^{2}-4ac<0$: complex conjugate roots:
  $$
  r_{1,2}=\frac{-b}{2a}\pm i\,\frac{\sqrt{4ac-b^{2}}}{2a}.
  $$

### 9.4.4 Fundamental Theorem of Algebra

> **Gauss (1799).** Every polynomial equation
> $$
> a_{0}+a_{1}x+\cdots+a_{n}x^{n}=0\qquad(a_{n}\neq 0,\;n\ge 1)
> $$
> with complex coefficients has at least one solution in $\mathbb{C}$.
>
> Hence no number system more general than $\mathbb{C}$ is needed to solve polynomial equations.

## 9.5 Geometric Interpretation, Modulus and Argument

### 9.5.1 The Complex Plane

A complex number $z=x+iy$ is represented by the point $(x,y)$ in the plane. The $x$-axis is the **real axis**; the $y$-axis is the **imaginary axis**.

- **Addition/subtraction** obey the **parallelogram law**.

### 9.5.2 Polar Form

For $z=x+iy\neq 0$, write $x=r\cos\theta$, $y=r\sin\theta$:

$$
z=r(\cos\theta+i\sin\theta).
$$

| Quantity | Definition | Formula |
|----------|-----------|---------|
| **Modulus** (absolute value) | Distance from origin | $\|z\|=\sqrt{x^{2}+y^{2}}=r$ |
| **Argument** | Polar angle | $\theta=\arg z$ (determined up to $2\pi$) |
| **Principal argument** | Unique choice | $\operatorname{Arg}z\in(-\pi,\pi]$ |

### 9.5.3 Properties of the Modulus

$$
\begin{aligned}
&|z|>0\quad\text{if }z\neq 0,&&|z_{1}-z_{2}|=|z_{2}-z_{1}|,\\
&|z_{1}+z_{2}|\le|z_{1}|+|z_{2}|,&&|z_{1}z_{2}|=|z_{1}|\,|z_{2}|,\\
&\Bigl|\frac{z_{1}}{z_{2}}\Bigr|=\frac{|z_{1}|}{|z_{2}|}\quad(z_{2}\neq 0).
\end{aligned}
$$

The product formula follows from:

$$
(ac-bd)^{2}+(bc+ad)^{2}=(a^{2}+b^{2})(c^{2}+d^{2}).
$$

### 9.5.4 Complex Conjugate

For $z=x+iy$, the **conjugate** is $\bar{z}=x-iy$ (reflection in the real axis).

$$
\overline{z_{1}+z_{2}}=\bar{z}_{1}+\bar{z}_{2},\qquad
\overline{z_{1}z_{2}}=\bar{z}_{1}\bar{z}_{2},\qquad
\overline{z_{1}/z_{2}}=\bar{z}_{1}/\bar{z}_{2},\qquad
z\bar{z}=|z|^{2}.
$$

### 9.5.5 Conjugate Roots of Real Polynomials

If a real-coefficient quadratic has no real roots, its complex roots are **conjugates**.

Conversely, if $r_{1}=\alpha+i\beta$ and $r_{2}=\alpha-i\beta$ are conjugates, they are roots of:

$$
x^{2}-2\alpha x+\alpha^{2}+\beta^{2}=0.
$$

## 9.6 Complex Exponentials

### 9.6.1 Motivation

To extend $e^{z}$ to complex $z$ while preserving the law $e^{a}e^{b}=e^{a+b}$, write $z=x+iy$:

$$
e^{z}=e^{x+iy}=e^{x}e^{iy}.
$$

Set $e^{iy}=A(y)+iB(y)$. Differentiating twice and comparing with $-e^{iy}$ gives $A''=-A$, $B''=-B$. With initial values $A(0)=1$, $A'(0)=0$, $B(0)=0$, $B'(0)=1$, uniqueness yields:

$$
A(y)=\cos y,\qquad B(y)=\sin y.
$$

### 9.6.2 Definition

For $z=x+iy$:

$$
e^{z}=e^{x}(\cos y+i\sin y).
$$

When $y=0$, this reduces to the real exponential $e^{x}$.

### 9.6.3 Theorem 9.3 鈥?Law of Exponents

For all complex $a,b$:

$$
e^{a}e^{b}=e^{a+b}.
$$

**Proof.** Write $a=x+iy$, $b=u+iv$. Using the addition formulas for $\cos$ and $\sin$:

$$
e^{a}e^{b}=e^{x+u}\bigl[\cos(y+v)+i\sin(y+v)\bigr]=e^{a+b}.
$$

### 9.6.4 Theorem 9.4 鈥?Polar Form

Every $z\neq 0$ can be written as:

$$
z=re^{i\theta},
$$

where $r=|z|$ and $\theta=\arg(z)+2n\pi$. This follows from **Euler's formula**:

$$
e^{i\theta}=\cos\theta+i\sin\theta.
$$

### 9.6.5 Multiplication and Division in Polar Form

If $z_{1}=r_{1}e^{i\theta}$ and $z_{2}=r_{2}e^{i\phi}$:

$$
z_{1}z_{2}=r_{1}r_{2}\,e^{i(\theta+\phi)},\qquad
\frac{z_{1}}{z_{2}}=\frac{r_{1}}{r_{2}}\,e^{i(\theta-\phi)}.
$$

### 9.6.6 De Moivre's Formula

For any integer $n$:

$$
z^{n}=r^{n}e^{in\theta}=r^{n}\bigl(\cos n\theta+i\sin n\theta\bigr).
$$

## 9.7 Complex-Valued Functions

A **complex-valued function** takes complex numbers as values.

| Type | Domain | Example |
|------|--------|---------|
| Of a real variable | Real numbers | $f(x)=u(x)+iv(x)$ |
| Of a complex variable | Complex numbers | $f(z)=e^{z}$ |

Most elementary functions (exponential, logarithm, trigonometric) extend to complex variables.

**Periodicity of the complex exponential.** For any integer $n$:

$$
e^{z+2n\pi i}=e^{z}.
$$

Thus $e^{z}$ has period $2\pi i$.

## 9.8 Calculus of Complex-Valued Functions of a Real Variable

### 9.8.1 Definitions

Let $f(x)=u(x)+iv(x)$ with $u,v$ real-valued.

| Concept | Definition |
|---------|-----------|
| **Continuity** | $f$ continuous $\iff$ $u$ and $v$ both continuous |
| **Derivative** | $f'(x)=u'(x)+iv'(x)$ |
| **Integral** | $\displaystyle\int_{a}^{b}f(x)\,dx=\int_{a}^{b}u(x)\,dx+i\int_{a}^{b}v(x)\,dx$ |

### 9.8.2 Extended Theorems

Many theorems of real calculus carry over unchanged:

- Sum, product, and quotient rules for differentiation.
- First and second fundamental theorems of calculus.
- **Zero-derivative theorem:** If $f'(x)=0$ on an open interval $I$, then $f$ is constant on $I$.

**Proof.** $f'=u'+iv'=0$ implies $u'=v'=0$. By the real zero-derivative theorem, $u$ and $v$ are constant; hence $f$ is constant.

### 9.8.3 Differentiation and Integration of $e^{tx}$

**Theorem 9.5.** If $f(x)=e^{tx}$ for real $x$ and fixed complex $t$, then:

$$
f'(x)=te^{tx}.
$$

**Proof.** Write $t=\alpha+i\beta$. Then:

$$
f(x)=e^{\alpha x}\cos\beta x+i\,e^{\alpha x}\sin\beta x.
$$

Differentiating the real and imaginary parts and combining gives $f'(x)=(\alpha+i\beta)e^{(\alpha+i\beta)x}=te^{tx}$.

**Integration formula** ($t\neq 0$):

$$
\int e^{tx}\,dx=\frac{e^{tx}}{t}.
$$

Equating real and imaginary parts with $t=\alpha+i\beta$:

$$
\int e^{\alpha x}\cos\beta x\,dx=\frac{e^{\alpha x}(\alpha\cos\beta x+\beta\sin\beta x)}{\alpha^{2}+\beta^{2}},
$$

$$
\int e^{\alpha x}\sin\beta x\,dx=\frac{e^{\alpha x}(\alpha\sin\beta x-\beta\cos\beta x)}{\alpha^{2}+\beta^{2}}.
$$

### 9.8.4 Connection with Second-Order Linear ODEs

**Theorem 9.6.** Let $L(y)=y''+ay'+by$ with real constants $a,b$. The function $f(x)=e^{tx}$ satisfies $L(f)=0$ iff $t$ is a root of the characteristic equation:

$$
t^{2}+at+b=0.
$$

**Proof.** $f'(x)=te^{tx}$ and $f''(x)=t^{2}e^{tx}$, so $L(f)=e^{tx}(t^{2}+at+b)$. Since $e^{tx}\neq 0$, the result follows.

> If $t=\alpha+i\beta$, the real and imaginary parts $u(x)=e^{\alpha x}\cos\beta x$ and $v(x)=e^{\alpha x}\sin\beta x$ are both real solutions. Their linear combination $y=c_{1}u+c_{2}v$ is the general solution, agreeing with Theorem 8.7.

[<- Previous: 8. Introduction to Differential Equations](08-introduction-to-differential-equations.md) | [Next: 10. Sequences, Infinite Series, Improper Integrals ->](10-sequences-infinite-series-improper-integrals.md)
