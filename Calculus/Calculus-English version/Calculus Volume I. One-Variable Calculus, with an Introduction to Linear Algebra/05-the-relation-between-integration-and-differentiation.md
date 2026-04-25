[<- Previous: 4. Differential Calculus](04-differential-calculus.md) | [Next: 6. The Logarithm, the Exponential, and the Inverse Trigonometric Functions ->](06-the-logarithm-the-exponential-and-the-inverse-trigonometric-functions.md)

# 5. The Relation between Integration and Differentiation

## 5.1 The Derivative of an Indefinite Integral

### 5.1.1 First Fundamental Theorem of Calculus

Integration and differentiation are inverse processes, analogous to squaring and taking the square root.

**Theorem 5.1 (First Fundamental Theorem of Calculus).**  
Let $f$ be integrable on $[a,x]$ for each $x\in[a,b]$. Choose $c\in[a,b]$ and define:

$$
A(x)=\int_{c}^{x}f(t)\,dt,\qquad a\le x\le b.
$$

If $f$ is continuous at a point $x$ in the open interval $(a,b)$, then the derivative $A'(x)$ exists and:

$$
A'(x)=f(x).
$$

- In words: *differentiating an indefinite integral of $f$ gives back $f$.*
- **Example**: $f(x)=x^{2}$. Then
  $$
  A(x)=\int_{c}^{x}t^{2}\,dt=\frac{x^{3}}{3}-\frac{c^{3}}{3},
  $$
  and indeed $A'(x)=x^{2}=f(x)$.

### 5.1.2 Geometric Motivation

Consider the area function $A$ over $[a,b]$.

- For $h>0$:
  $$
  \int_{x}^{x+h}f(t)\,dt=\int_{c}^{x+h}f(t)\,dt-\int_{c}^{x}f(t)\,dt=A(x+h)-A(x).
  $$
- By the **mean-value theorem for integrals** (assuming $f$ continuous on $[x,x+h]$):
  $$
  A(x+h)-A(x)=h\,f(z),\qquad x\le z\le x+h.
  $$
- Hence:
  $$
  \frac{A(x+h)-A(x)}{h}=f(z).
  $$
- As $h\to 0$, $z\to x$; if $f$ is continuous, $f(z)\to f(x)$, so $A'(x)=f(x)$.

> **Caveat:** This geometric argument assumes $f$ is continuous in a whole *neighborhood* of $x$, whereas Theorem 5.1 requires only continuity at the *single point* $x$.

### 5.1.3 Analytic Proof

Fix a point $x$ at which $f$ is continuous. The difference quotient is:

$$
\frac{A(x+h)-A(x)}{h}.
$$

Its numerator simplifies to:

$$
A(x+h)-A(x)=\int_{x}^{x+h}f(t)\,dt.
$$

Decompose $f(t)$ as $f(x)+[f(t)-f(x)]$:

$$
\begin{aligned}
A(x+h)-A(x)
&=\int_{x}^{x+h}f(x)\,dt+\int_{x}^{x+h}[f(t)-f(x)]\,dt\\[4pt]
&=h\,f(x)+\int_{x}^{x+h}[f(t)-f(x)]\,dt.
\end{aligned}
$$

Therefore:

$$
\frac{A(x+h)-A(x)}{h}=f(x)+\frac{1}{h}\int_{x}^{x+h}[f(t)-f(x)]\,dt.\tag{5.1}
$$

It remains to show that the second term tends to $0$ as $h\to 0$.

1. Let $\varepsilon>0$. By continuity of $f$ at $x$, there exists $\delta>0$ such that
   $$
   |f(t)-f(x)|<\frac{\varepsilon}{2}\quad\text{whenever}\quad |t-x|<\delta.
   $$
2. Choose $0<|h|<\delta$. Then every $t$ between $x$ and $x+h$ satisfies $|t-x|<\delta$, so:
   $$
   \Bigl|\int_{x}^{x+h}[f(t)-f(x)]\,dt\Bigr|
   \le\int_{x}^{x+h}|f(t)-f(x)|\,dt
   <\int_{x}^{x+h}\frac{\varepsilon}{2}\,dt
   =\frac{\varepsilon}{2}|h|
   <\varepsilon|h|.
   $$
3. Dividing by $|h|$ gives
   $$
   \Bigl|\frac{1}{h}\int_{x}^{x+h}[f(t)-f(x)]\,dt\Bigr|<\varepsilon.
   $$

Hence the second term in (5.1) vanishes as $h\to 0$, and $A'(x)=f(x)$. 鈭?
## 5.2 The Zero-Derivative Theorem

- If $f$ is constant on an open interval $(a,b)$, then $f'(x)=0$ everywhere on $(a,b)$ 鈥?an immediate consequence of the definition of the derivative.
- The converse is stated separately as Theorem 5.2:

**Theorem 5.2 (Zero-Derivative Theorem).**  
If $f'(x)=0$ for every $x$ in an open interval $I$, then $f$ is constant on $I$.

- This theorem, used in combination with the first fundamental theorem of calculus, leads to the **second fundamental theorem of calculus** (Section 5.3).

## 5.3 Primitive Functions and the Second Fundamental Theorem of Calculus

### 5.3.1 Primitive Functions

A function $P$ is called a **primitive** (or **antiderivative**) of $f$ on an open interval $I$ if:

$$
P'(x)=f(x)\quad\text{for all }x\in I.
$$

- **Example**: $\sin x$ is a primitive of $\cos x$ on every interval, since $(\sin x)'=\cos x$.
- We speak of **a** primitive, not **the** primitive: if $P$ is a primitive of $f$, so is $P+k$ for every constant $k$.
- **Uniqueness up to a constant**: Any two primitives $P$ and $Q$ of the same function $f$ differ only by a constant, because
  $$
  (P-Q)'=P'-Q'=f-f=0\quad\Longrightarrow\quad P-Q=\text{constant}
  $$
  by Theorem 5.2.

### 5.3.2 Second Fundamental Theorem of Calculus

The first fundamental theorem guarantees that a continuous function always has a primitive (obtained by integration). Combining this with the constant-difference property above yields:

**Theorem 5.3 (Second Fundamental Theorem of Calculus).**  
Assume $f$ is continuous on an open interval $I$, and let $P$ be any primitive of $f$ on $I$. Then for each $c$ and each $x$ in $I$:

$$
P(x)=P(c)+\int_{c}^{x}f(t)\,dt. \tag{5.2}
$$

Equivalently:

$$
\int_{c}^{x}f(t)\,dt=P(x)-P(c). \tag{5.3}
$$

**Proof.** Let $A(x)=\int_{c}^{x}f(t)\,dt$. By Theorem 5.1, $A'(x)=f(x)$, so $A$ is a primitive of $f$. Since two primitives differ only by a constant:
$$
A(x)-P(x)=k.
$$
Put $x=c$: $A(c)=0$, so $k=-P(c)$. Hence $A(x)-P(x)=-P(c)$, which gives (5.2). 鈭?
- In words: *knowing one primitive $P$ reduces integral evaluation to simple subtraction.*

### 5.3.3 Integration of Rational Powers

From the differentiation formula $\bigl(x^{n+1}/(n+1)\bigr)'=x^{n}$ and (5.3):

$$
\int_{a}^{b}x^{n}\,dx=\frac{b^{n+1}-a^{n+1}}{n+1},\qquad n\neq-1.
$$

| Exponent type | Validity | Restriction |
|---------------|----------|-------------|
| Nonnegative integers | Directly from power rule | None |
| Negative integers ($n\neq-1$) | $P(x)=x^{n+1}/(n+1)$ is rational | Exclude intervals containing $x=0$ |
| Rational exponents ($n\neq-1$) | Extend via general power rule (Chapter 6) | Integrand must be defined on $[a,b]$ |

- **Example** ($n=-\tfrac12$, $0<a<b$):
  $$
  \int_{a}^{b}\frac{1}{\sqrt{x}}\,dx=\int_{a}^{b}x^{-1/2}\,dx=\Bigl.\frac{x^{1/2}}{1/2}\Bigr|_{a}^{b}=2(\sqrt{b}-\sqrt{a}).
  $$

### 5.3.4 The Natural Logarithm

The power rule does **not** cover $n=-1$, since $x^{n+1}/(n+1)$ is undefined. Nevertheless, a primitive of $1/x$ exists:

$$
P(x)=\int_{1}^{x}\frac{1}{t}\,dt\qquad(x>0).
$$

- The integral exists because the integrand $1/t$ is monotonic.
- This function is called the **logarithm** (more precisely, the **natural logarithm**).
- Its properties are developed systematically in Chapter 6.

### 5.3.5 Integration of Sine and Cosine

Since $(\sin x)'=\cos x$ and $(\cos x)'=-\sin x$:

$$
\int_{a}^{b}\cos x\,dx=\sin x\Big|_{a}^{b}=\sin b-\sin a,
$$

$$
\int_{a}^{b}\sin x\,dx=-\cos x\Big|_{a}^{b}=\cos a-\cos b.
$$

- These formulas also follow directly from the definition of the integral (proved in Chapter 2).
- Further integration formulas are obtained by taking finite sums of terms $Ax^{n}$, $B\sin x$, $C\cos x$.

## 5.4 Properties of a Function Deduced from Properties of Its Derivative

If $f$ has a continuous derivative $f'$ on an open interval $I$, the second fundamental theorem gives:

$$
f(x)=f(c)+\int_{c}^{x}f'(t)\,dt\qquad\text{for all }x,c\in I. \tag{5.4}
$$

This formula expresses $f$ in terms of $f'$, allowing properties of $f$ to be deduced from properties of $f'$.

- **Monotonicity**: Suppose $f'$ is continuous and nonnegative on $I$. If $x>c$, then $\int_{c}^{x}f'(t)\,dt\ge0$, so $f(x)\ge f(c)$.  
  Hence: *a continuous nonnegative derivative implies $f$ is increasing on $I$.*

- **Convexity / concavity**: Theorem 2.9 shows that the indefinite integral of an increasing function is convex. Therefore, if $f'$ is continuous and increasing on $I$, Equation (5.4) shows that $f$ is **convex** on $I$. Similarly, $f$ is **concave** on intervals where $f'$ is continuous and decreasing.

## 5.5 The Leibniz Notation for Primitives

### 5.5.1 The Indefinite Integral Symbol

Leibniz introduced the symbol $\int f(x)\,dx$ to denote a **general primitive** of $f$:

$$
\int f(x)\,dx=P(x)+C, \tag{5.5}
$$

where $P'(x)=f(x)$ and $C$ is an arbitrary constant. Equation (5.5) is merely an alternative way of writing $P'(x)=f(x)$.

- **Example**:
  $$
  \int\cos x\,dx=\sin x+C.
  $$
- **Example** ($n\neq-1$):
  $$
  \int x^{n}\,dx=\frac{x^{n+1}}{n+1}+C.
  $$

> **Note**: $C$ represents an arbitrary constant, so each formula above describes a whole *family* of functions.

### 5.5.2 Relation to Definite Integration

Despite similar appearance, $\int f(x)\,dx$ and $\int_{a}^{b}f(x)\,dx$ are conceptually distinct 鈥?they originate from differentiation and integration respectively. The fundamental theorems connect them:

- **First FTC** (Equation 5.15):
  $$
  \int f(x)\,dx=\int_{c}^{x}f(t)\,dt+C.
  $$
  Thus $\int f(x)\,dx$ may be viewed as an indefinite integral plus a constant.

- **Second FTC** (Equation 5.16):
  $$
  \int_{a}^{b}f(x)\,dx=\Bigl[\int f(x)\,dx\Bigr]_{a}^{b}.
  $$
  In practice: evaluate any primitive at the endpoints and subtract.

### 5.5.3 Terminology and Techniques of Integration

Because of long historical usage, many textbooks call $\int f(x)\,dx$ an **indefinite integral** rather than a primitive. Since the second fundamental theorem reduces integration to finding primitives, the phrase **"technique of integration"** refers to any systematic method for finding primitives.

Three principal techniques for constructing tables of indefinite integrals:

| Technique | Basis | Location |
|-----------|-------|----------|
| **Integration by substitution** | Chain rule | Next section |
| **Integration by parts** | Product rule | Section 5.9 |
| **Integration by partial fractions** | Algebraic decomposition | End of Chapter 6 |

- These techniques explain how integral tables are built and how formulas are reduced to basic forms.
- When asked to "integrate" $\int f(x)\,dx$, what is wanted is the most general primitive of $f$.

## 5.6 Integration by Substitution

### 5.6.1 The Chain Rule in Reverse

If $Q(x)=P[g(x)]$ and $P'(x)=f(x)$, the chain rule gives:

$$
Q'(x)=P'[g(x)]g'(x)=f[g(x)]g'(x).
$$

Hence:

$$
\int f[g(x)]g'(x)\,dx=P[g(x)]+C. \tag{5.6}
$$

**Leibniz formalism.** Set $u=g(x)$ and write $du=g'(x)\,dx$. Then (5.6) becomes:

$$
\int f(u)\,du=P(u)+C.
$$

> **Note**: $dx$ and $du$ are treated as purely formal devices; each substitution step is really an application of the chain rule.

### 5.6.2 Examples 鈥?Indefinite Integrals

**Example 1.** $\displaystyle\int x^{3}\cos x^{4}\,dx$.
- Let $u=x^{4}$, $du=4x^{3}\,dx$.
- Compensate for the factor $4$:
  $$
  \int x^{3}\cos x^{4}\,dx=\tfrac14\int(\cos x^{4})(4x^{3}\,dx)=\tfrac14\int\cos u\,du=\tfrac14\sin u+C=\tfrac14\sin x^{4}+C.
  $$

**Example 2.** $\displaystyle\int\cos^{2}x\sin x\,dx$.
- Let $u=\cos x$, $du=-\sin x\,dx$.
  $$
  \int\cos^{2}x\sin x\,dx=-\int u^{2}\,du=-\frac{u^{3}}{3}+C=-\frac{\cos^{3}x}{3}+C.
  $$

**Example 3.** $\displaystyle\int\frac{\sin\sqrt{x}}{\sqrt{x}}\,dx$.
- Let $u=\sqrt{x}$, $du=\frac{1}{2\sqrt{x}}\,dx$, so $\frac{dx}{\sqrt{x}}=2\,du$.
  $$
  \int\frac{\sin\sqrt{x}}{\sqrt{x}}\,dx=2\int\sin u\,du=-2\cos u+C=-2\cos\sqrt{x}+C.
  $$

**Example 4.** $\displaystyle\int\frac{x\,dx}{\sqrt{1+x^{2}}}$.
- Let $u=1+x^{2}$, $du=2x\,dx$, so $x\,dx=\tfrac12\,du$.
  $$
  \int\frac{x\,dx}{\sqrt{1+x^{2}}}=\tfrac12\int u^{-1/2}\,du=u^{1/2}+C=\sqrt{1+x^{2}}+C.
  $$

### 5.6.3 Definite Integrals and Change of Limits

For definite integrals one may either:
1. find the indefinite integral, then evaluate at the endpoints; or
2. change the limits of integration to match the new variable $u$.

**Example (method 1).**
$$
\int_{0}^{\pi/2}\cos^{2}x\sin x\,dx=-\frac13\cos^{3}x\Big|_{0}^{\pi/2}=-\frac13(0-1)=\frac13.
$$

**Example 5 (method 2).** $\displaystyle\int_{2}^{3}\frac{(x+1)\,dx}{\sqrt{x^{2}+2x+3}}$.
- Let $u=x^{2}+2x+3$, $du=(2x+2)\,dx$, so $(x+1)\,dx=\tfrac12\,du$.
- New limits: $x=2\Rightarrow u=11$, $x=3\Rightarrow u=18$.
  $$
  \int_{2}^{3}\frac{(x+1)\,dx}{\sqrt{x^{2}+2x+3}}=\tfrac12\int_{11}^{18}u^{-1/2}\,du=\sqrt{u}\,\Big|_{11}^{18}=\sqrt{18}-\sqrt{11}.
  $$

### 5.6.4 The Substitution Theorem

**Theorem 5.4 (Substitution Theorem for Integrals).**  
Assume $g$ has a continuous derivative $g'$ on an open interval $I$. Let $J$ be the set of values taken by $g$ on $I$, and assume $f$ is continuous on $J$. Then for each $x$ and $c$ in $I$:

$$
\int_{c}^{x}f[g(t)]g'(t)\,dt=\int_{g(c)}^{g(x)}f(u)\,du. \tag{5.7}
$$

**Proof.** Let $a=g(c)$ and define:
$$
P(x)=\int_{a}^{x}f(u)\,du\quad(x\in J),\qquad Q(x)=\int_{c}^{x}f[g(t)]g'(t)\,dt\quad(x\in I).
$$
Then $P'(x)=f(x)$ and $Q'(x)=f[g(x)]g'(x)$. Set $R(x)=P[g(x)]$. By the chain rule:
$$
R'(x)=P'[g(x)]g'(x)=f[g(x)]g'(x)=Q'(x).
$$
Applying the second fundamental theorem twice:
$$
\int_{g(c)}^{g(x)}f(u)\,du=P[g(x)]-P[g(c)]=R(x)-R(c),
$$
$$
\int_{c}^{x}f[g(t)]g'(t)\,dt=Q(x)-Q(c)=R(x)-R(c).
$$
Thus the two integrals in (5.7) are equal. 鈭?
## 5.7 Integration by Parts

### 5.7.1 The Formula

From the product rule $(fg)'=f'g+fg'$ we obtain:

$$
\int f(x)g'(x)\,dx=f(x)g(x)-\int f'(x)g(x)\,dx+C. \tag{5.8}
$$

**Abbreviated form.** With $u=f(x)$, $v=g(x)$, $du=f'(x)\,dx$, $dv=g'(x)\,dx$:

$$
\int u\,dv=uv-\int v\,du+C. \tag{5.9}
$$

**Definite-integral version:**

$$
\int_{a}^{b}f(x)g'(x)\,dx=f(b)g(b)-f(a)g(a)-\int_{a}^{b}f'(x)g(x)\,dx.
$$

The idea is to choose $f$ and $g$ so that the new integral on the right is easier than the original.

### 5.7.2 Examples

**Example 1.** $\displaystyle\int x\cos x\,dx$.
- Good choice: $u=x$, $dv=\cos x\,dx$ $\Rightarrow$ $du=dx$, $v=\sin x$.
  $$
  \int x\cos x\,dx=x\sin x-\int\sin x\,dx=x\sin x+\cos x+C.
  $$
- Bad choice: $u=\cos x$, $dv=x\,dx$ $\Rightarrow$ $du=-\sin x\,dx$, $v=\tfrac12x^{2}$.
  $$
  \int x\cos x\,dx=\tfrac12x^{2}\cos x+\tfrac12\int x^{2}\sin x\,dx,
  $$
  which leads to a harder integral. (However, solving for $\int x^{2}\sin x\,dx$ and using the first result gives $\int x^{2}\sin x\,dx=2x\sin x+2\cos x-x^{2}\cos x+C$.)

**Example 2.** $\displaystyle\int x^{2}\cos x\,dx$.
- Let $u=x^{2}$, $dv=\cos x\,dx$ $\Rightarrow$ $du=2x\,dx$, $v=\sin x$.
  $$
  \int x^{2}\cos x\,dx=x^{2}\sin x-2\int x\sin x\,dx.
  $$
- Apply parts again to $\int x\sin x\,dx$ ($u=x$, $dv=\sin x\,dx$):
  $$
  \int x\sin x\,dx=-x\cos x+\sin x+C.
  $$
- Hence:
  $$
  \int x^{2}\cos x\,dx=x^{2}\sin x+2x\cos x-2\sin x+C.
  $$

**Example 3 (failure mode).** $\displaystyle\int x^{-1}\,dx$ by parts.
- Let $u=x$, $dv=x^{-2}\,dx$ $\Rightarrow$ $du=dx$, $v=-x^{-1}$.
  $$
  \int x^{-1}\,dx=-1+\int x^{-1}\,dx+C,
  $$
  which circles back. This shows the importance of the constant $C$: omitting it would give the fallacious conclusion $0=-1$.

### 5.7.3 Second Mean-Value Theorem for Integrals

**Theorem 5.5 (Second Mean-Value Theorem for Integrals).**  
Assume $g$ is continuous on $[a,b]$, and $f$ has a derivative which is continuous and never changes sign on $[a,b]$. Then for some $c$ in $[a,b]$:

$$
\int_{a}^{b}f(x)g(x)\,dx=f(a)\int_{a}^{c}g(x)\,dx+f(b)\int_{c}^{b}g(x)\,dx. \tag{5.10}
$$

**Proof.** Let $G(x)=\int_{a}^{x}g(t)\,dt$. Then $G'(x)=g(x)$ and $G(a)=0$. Integration by parts gives:

$$
\int_{a}^{b}f(x)g(x)\,dx=f(b)G(b)-\int_{a}^{b}f'(x)G(x)\,dx.
$$

By the weighted mean-value theorem, for some $c\in[a,b]$:

$$
\int_{a}^{b}f'(x)G(x)\,dx=G(c)\int_{a}^{b}f'(x)\,dx=G(c)\bigl[f(b)-f(a)\bigr].
$$

Substituting and rearranging:

$$
\int_{a}^{b}f(x)g(x)\,dx=f(b)G(b)-G(c)\bigl[f(b)-f(a)\bigr]=f(a)G(c)+f(b)\bigl[G(b)-G(c)\bigr],
$$

which is (5.10) since $G(c)=\int_{a}^{c}g(x)\,dx$ and $G(b)-G(c)=\int_{c}^{b}g(x)\,dx$. 鈭?

[<- Previous: 4. Differential Calculus](04-differential-calculus.md) | [Next: 6. The Logarithm, the Exponential, and the Inverse Trigonometric Functions ->](06-the-logarithm-the-exponential-and-the-inverse-trigonometric-functions.md)
