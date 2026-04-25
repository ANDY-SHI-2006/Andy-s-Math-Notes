[<- Previous: 9. Complex Numbers](09-complex-numbers.md) | [Next: 11. Sequences and Series of Functions ->](11-sequences-and-series-of-functions.md)

# 10. Sequences, Infinite Series, Improper Integrals

## 10.1 Zeno's Paradox

### 10.1.1 The Racecourse Paradox

Zeno of Elea (495鈥?35 B.C.) argued that a runner can never reach the end of a racecourse: he must first cover half the distance, then half of what remains, then half of that, *ad infinitum*.

If the runner covers the first half in $T$ minutes, the total time is represented by the **infinite series**:

$$
T+\frac{T}{2}+\frac{T}{4}+\cdots+\frac{T}{2^{n}}+\cdots.
$$

**Partial sums.**

$$
s_{n}=T+\frac{T}{2}+\cdots+\frac{T}{2^{n-1}}=\Bigl(2-\frac{1}{2^{n-1}}\Bigr)T.
$$

Since $1/2^{n-1}\to 0$, we have $s_{n}\to 2T$. Thus the series has **sum** $2T$, resolving the paradox.

### 10.1.2 A Divergent Variant

Suppose instead the runner's speed decreases so that the portion from $1/2^{n-1}$ to $1/2^{n}$ takes $T/n$ minutes. The total time is:

$$
T+\frac{T}{2}+\frac{T}{3}+\cdots+\frac{T}{n}+\cdots.
$$

**Integral estimate.** The harmonic partial sums satisfy:

$$
1+\frac{1}{2}+\cdots+\frac{1}{n}\ge\log(n+1).
$$

Hence $s_{n}\ge T\log(n+1)\to+\infty$. The runner never arrives鈥擹eno is right in this case.

> **Convergent** series have partial sums approaching a finite limit; **divergent** series do not.

### 10.1.3 Historical Remarks

- **17th century:** Widespread use of infinite series; Newton discovered the **binomial series**.
- **Binomial theorem:** $(1+x)^{n}=\displaystyle\sum_{k=0}^{n}\binom{n}{k}x^{k}$ for integer $n\ge 0$.
- Newton extended this to arbitrary real exponents (no rigorous proof at the time).
- **1812:** Gauss published the first thorough and rigorous treatment of convergence.
- **1821:** Cauchy introduced the analytic definition of limit in *Cours d'analyse alg茅brique*, laying the foundations of modern convergence theory.

## 10.2 Sequences

### 10.2.1 Definition

A **sequence** is a function $f$ whose domain is the set of positive integers. The value $f(n)$ is called the $n$th **term**.

**Notation.** $\{f(n)\}$, or $a_{n}, s_{n}, x_{n}, u_{n}$, etc.

**Examples.**
- $a_{n}=1/n$: $\;1,\tfrac{1}{2},\tfrac{1}{3},\tfrac{1}{4},\ldots$
- $a_{2n-1}=1$, $a_{2n}=2n^{2}$: $\;1,2,1,8,1,18,\ldots$
- **Fibonacci** (recursion): $a_{1}=a_{2}=1$, $a_{n+1}=a_{n}+a_{n-1}$: $\;1,1,2,3,5,8,13,\ldots$

### 10.2.2 Limit of a Sequence

**Definition.** A sequence $\{f(n)\}$ has **limit** $L$ if:

> For every $\epsilon>0$, there exists $N$ such that $|f(n)-L|<\epsilon$ for all $n\ge N$.

We write $\displaystyle\lim_{n\to\infty}f(n)=L$ or $f(n)\to L$.

A sequence with no limit is **divergent**.

### 10.2.3 Complex-Valued Sequences

If $f=u+iv$ and $L=a+ib$, then:

$$
f(n)\to L\quad\Longleftrightarrow\quad u(n)\to a\;\text{ and }\;v(n)\to b.
$$

Hence:

$$
\lim_{n\to\infty}f(n)=\lim_{n\to\infty}u(n)+i\lim_{n\to\infty}v(n).
$$

> For complex $f$: $f(n)\to\infty$ means $|f(n)|\to+\infty$.

### 10.2.4 Basic Limit Formulas

| Formula | Condition |
|---------|-----------|
| $\displaystyle\lim_{n\to\infty}\dfrac{1}{n^{\alpha}}=0$ | $\alpha>0$ |
| $\displaystyle\lim_{n\to\infty}x^{n}=0$ | $|x|<1$ |
| $\displaystyle\lim_{n\to\infty}\dfrac{(\log n)^{a}}{n^{b}}=0$ | $a>0$, $b>0$ |
| $\displaystyle\lim_{n\to\infty}n^{1/n}=1$ | 鈥?|
| $\displaystyle\lim_{n\to\infty}\Bigl(1+\dfrac{a}{n}\Bigr)^{n}=e^{a}$ | $a\in\mathbb{R}$ |

### 10.2.5 Algebra of Limits

If $f(n)\to L$ and $g(n)\to M$, then:
- $f(n)+g(n)\to L+M$
- $f(n)g(n)\to LM$
- $f(n)/g(n)\to L/M$ (if $M\neq 0$)

## 10.3 Monotonic Sequences of Real Numbers

### 10.3.1 Definitions

| Type | Condition | Notation |
|------|-----------|----------|
| **Increasing** | $f(n)\le f(n+1)$ for all $n\ge 1$ | $f(n)\nearrow$ |
| **Decreasing** | $f(n)\ge f(n+1)$ for all $n\ge 1$ | $f(n)\searrow$ |
| **Monotonic** | Increasing or decreasing | 鈥?|

A sequence is **bounded** if $|f(n)|\le M$ for some $M>0$ and all $n$; otherwise it is **unbounded**.

### 10.3.2 Theorem 10.1

A monotonic sequence **converges if and only if it is bounded**.

**Proof.**

- An unbounded sequence cannot converge (obvious).
- Let $f(n)\nearrow$ and be bounded. Let $L=\sup\{f(n)\}$ (exists by the least-upper-bound axiom).
  - $f(n)\le L$ for all $n$.
  - For any $\epsilon>0$, $L-\epsilon$ is not an upper bound, so $f(N)>L-\epsilon$ for some $N$.
  - Since $f$ is increasing: $L-\epsilon<f(n)\le L$ for all $n\ge N$.
  - Hence $0\le L-f(n)<\epsilon$, so $f(n)\to L$.
- The decreasing case is similar, with limit $=\inf\{f(n)\}$.

## 10.4 Infinite Series

### 10.4.1 Definition

Given a sequence $\{a_{k}\}$, form the **partial sums**:

$$
s_{n}=\sum_{k=1}^{n}a_{k}=a_{1}+a_{2}+\cdots+a_{n}.
$$

The sequence $\{s_{n}\}$ is called an **infinite series**, denoted:

$$
\sum_{k=1}^{\infty}a_{k}\quad\text{or}\quad a_{1}+a_{2}+a_{3}+\cdots.
$$

If $\displaystyle\lim_{n\to\infty}s_{n}=S$, the series **converges** and has **sum** $S$:

$$
\sum_{k=1}^{\infty}a_{k}=S.
$$

If $\{s_{n}\}$ diverges, the series **diverges**.

> The "sum" of a series is the **limit of partial sums**, not ordinary addition.

### 10.4.2 Examples

**Example 1 鈥?The harmonic series.** $\displaystyle\sum_{k=1}^{\infty}\frac{1}{k}$.

Since $s_{n}=\sum_{k=1}^{n}\frac{1}{k}\ge\log(n+1)\to\infty$, the harmonic series **diverges**.

**Example 2 鈥?Geometric series.** $\displaystyle\sum_{k=1}^{\infty}\frac{1}{2^{k-1}}=1+\frac{1}{2}+\frac{1}{4}+\cdots$.

Since $s_{n}=2-\dfrac{1}{2^{n-1}}\to 2$, this series **converges** with sum $2$.

### 10.4.3 Shifting the Index

The symbol $\displaystyle\sum_{k=p}^{\infty}a_{k}$ (for $p\ge 0$) differs from $\displaystyle\sum_{k=1}^{\infty}a_{k}$ by only finitely many terms. Therefore:

> **Adding or omitting a finite number of terms at the beginning does not affect convergence or divergence.**

## 10.5 Linearity of Convergent Series

### 10.5.1 Theorem 10.2

If $\sum a_{n}$ and $\sum b_{n}$ converge and $\alpha,\beta$ are complex constants, then $\sum(\alpha a_{n}+\beta b_{n})$ also converges, and:

$$
\sum_{n=1}^{\infty}(\alpha a_{n}+\beta b_{n})=\alpha\sum_{n=1}^{\infty}a_{n}+\beta\sum_{n=1}^{\infty}b_{n}.
$$

**Proof.** Apply the corresponding properties of finite sums and take limits.

### 10.5.2 Theorem 10.3

If $\sum a_{n}$ converges and $\sum b_{n}$ diverges, then $\sum(a_{n}+b_{n})$ **diverges**.

**Proof.** If $\sum(a_{n}+b_{n})$ converged, then $\sum b_{n}=\sum[(a_{n}+b_{n})-a_{n}]$ would converge by Theorem 10.2鈥攃ontradiction.

> If **both** diverge, $\sum(a_{n}+b_{n})$ may converge or diverge.

**Example.** $\sum(1/k+1/2^{k})$ diverges because $\sum 1/k$ diverges while $\sum 1/2^{k}$ converges.

## 10.6 Telescoping Series

### 10.6.1 Theorem 10.4

Let $a_{n}=b_{n}-b_{n+1}$. Then:

$$
\sum_{n=1}^{\infty}a_{n}\text{ converges}\quad\Longleftrightarrow\quad\{b_{n}\}\text{ converges}.
$$

In that case, with $L=\lim_{n\to\infty}b_{n}$:

$$
\sum_{n=1}^{\infty}a_{n}=b_{1}-L.
$$

**Proof.** The $n$th partial sum is $s_{n}=\sum_{k=1}^{n}(b_{k}-b_{k+1})=b_{1}-b_{n+1}$.

> Every series is telescoping (choose $b_{1}$ arbitrarily and set $b_{n+1}=b_{1}-s_{n}$), but the decomposition is useful only when $b_{n}$ is simple.

### 10.6.2 Examples

**Example 1.** $a_{n}=\dfrac{1}{n^{2}+n}=\dfrac{1}{n}-\dfrac{1}{n+1}$. Here $b_{n}=1/n$, $L=0$:

$$
\sum_{n=1}^{\infty}\frac{1}{n(n+1)}=1.
$$

**Example 2.** For $x$ not a negative integer:

$$
\frac{1}{(n+x)(n+x+1)(n+x+2)}=\frac{1}{2}\Bigl(\frac{1}{(n+x)(n+x+1)}-\frac{1}{(n+x+1)(n+x+2)}\Bigr).
$$

Hence:

$$
\sum_{n=1}^{\infty}\frac{1}{(n+x)(n+x+1)(n+x+2)}=\frac{1}{2(x+1)(x+2)}.
$$

**Example 3.** $\log\dfrac{n}{n+1}=\log n-\log(n+1)$. Since $\log n\to\infty$, the series **diverges**.

> **Caution.** In an infinite telescoping series $(b_{1}-b_{2})+(b_{2}-b_{3})+\cdots$, one cannot simply "cancel" all intermediate terms to obtain sum $b_{1}$ unless $\lim b_{n}=0$.

## 10.7 The Geometric Series

### 10.7.1 Theorem 10.5

For complex $x$:

$$
\sum_{n=0}^{\infty}x^{n}=1+x+x^{2}+\cdots=\frac{1}{1-x}\qquad\text{if }|x|<1.
$$

If $|x|\ge 1$, the series diverges.

**Proof.** The partial sum $s_{n}=1+x+\cdots+x^{n-1}$ satisfies $(1-x)s_{n}=1-x^{n}$. Hence $s_{n}=\dfrac{1-x^{n}}{1-x}\to\dfrac{1}{1-x}$ when $|x|<1$.

### 10.7.2 Derived Series (by Substitution)

| Series | Sum | Valid for |
|--------|-----|-----------|
| $1+x^{2}+x^{4}+\cdots$ | $\dfrac{1}{1-x^{2}}$ | $|x|<1$ |
| $x+x^{3}+x^{5}+\cdots$ | $\dfrac{x}{1-x^{2}}$ | $|x|<1$ |
| $1-x+x^{2}-x^{3}+\cdots$ | $\dfrac{1}{1+x}$ | $|x|<1$ |
| $1-x^{2}+x^{4}-\cdots$ | $\dfrac{1}{1+x^{2}}$ | $|x|<1$ |
| $x-x^{3}+x^{5}-\cdots$ | $\dfrac{x}{1+x^{2}}$ | $|x|<1$ |

### 10.7.3 Power Series

A series of the form $\displaystyle\sum_{n=0}^{\infty}a_{n}x^{n}$ is called a **power series**. The geometric series is the special case $a_{n}=1$.

**Differentiation of (10.25).**

$$
1+2x+3x^{2}+\cdots+nx^{n-1}+\cdots=\frac{1}{(1-x)^{2}}\qquad(|x|<1).
$$

**Integration of (10.28).** Mercator鈥揃rouncker (1668):

$$
x-\frac{x^{2}}{2}+\frac{x^{3}}{3}-\frac{x^{4}}{4}+\cdots=\log(1+x)\qquad(-1<x\le 1).
$$

**Integration of (10.29).** Gregory (1671):

$$
x-\frac{x^{3}}{3}+\frac{x^{5}}{5}-\frac{x^{7}}{7}+\cdots=\arctan x\qquad(|x|\le 1).
$$

### 10.7.4 Taylor Series

If $f$ has derivatives of all orders near $0$, Taylor's formula gives:

$$
f(x)=\sum_{k=0}^{n}a_{k}x^{k}+E_{n}(x),\qquad a_{k}=\frac{f^{(k)}(0)}{k!}.
$$

If $E_{n}(x)\to 0$ as $n\to\infty$, then:

$$
f(x)=\sum_{k=0}^{\infty}a_{k}x^{k}.
$$

The partial sums of this power series are precisely the Taylor polynomials. Conditions guaranteeing $E_{n}(x)\to 0$ will be discussed in Section 11.10.

## 10.8 Tests for Convergence

Convergence tests fall into three categories:

| Type | Form | Meaning |
|------|------|---------|
| (i) Sufficient | If $C$, then $\sum a_{n}$ converges | $C\Rightarrow$ convergence |
| (ii) Necessary | If $\sum a_{n}$ converges, then $C$ | convergence$\Rightarrow C$ |
| (iii) Necessary and sufficient | $\sum a_{n}$ converges $\iff C$ | equivalence |

### 10.8.1 Theorem 10.6 鈥?Necessary Condition

If $\sum a_{n}$ converges, then:

$$
\lim_{n\to\infty}a_{n}=0.
$$

**Proof.** $a_{n}=s_{n}-s_{n-1}\to S-S=0$.

> This is **not sufficient** (e.g. $a_{n}=1/n\to 0$ but $\sum 1/n$ diverges). Its practical use is as a **sufficient condition for divergence**: if $a_{n}\not\to 0$, the series diverges.

## 10.9 Comparison Tests for Nonnegative Series

### 10.9.1 Theorem 10.7 鈥?Bounded-Partial-Sum Criterion

If $a_{n}\ge 0$, then:

$$
\sum a_{n}\text{ converges}\quad\Longleftrightarrow\quad\{s_{n}\}\text{ is bounded above}.
$$

**Example.** $\sum 1/n!$ converges because $1/k!\le 1/2^{k-1}$, so:

$$
\sum_{k=1}^{n}\frac{1}{k!}\le\sum_{k=0}^{n-1}\Bigl(\frac{1}{2}\Bigr)^{k}\le 2.
$$

The sum is $e-1$.

### 10.9.2 Theorem 10.8 鈥?Comparison Test

Assume $a_{n}\ge 0$, $b_{n}\ge 0$, and $a_{n}\le c\,b_{n}$ for some $c>0$ and all $n\ge N$. Then:

- $\sum b_{n}$ converges $\;\Rightarrow\;$ $\sum a_{n}$ converges.
- $\sum a_{n}$ diverges $\;\Rightarrow\;$ $\sum b_{n}$ diverges.

> We say $\sum b_{n}$ **dominates** $\sum a_{n}$.

### 10.9.3 Theorem 10.9 鈥?Limit Comparison Test

Assume $a_{n}>0$, $b_{n}>0$. If:

$$
\lim_{n\to\infty}\frac{a_{n}}{b_{n}}=1,
$$

then $\sum a_{n}$ and $\sum b_{n}$ both converge or both diverge.

> The conclusion also holds if the limit is any $c>0$. If the limit is $0$, only "$\sum b_{n}$ conv. $\Rightarrow$ $\sum a_{n}$ conv." follows.

**Asymptotic equality.** Write $a_{n}\sim b_{n}$ if $\lim a_{n}/b_{n}=1$.

**Theorem 10.10.** Two series with positive, asymptotically equal terms converge or diverge together.

### 10.9.4 Examples

**Riemann zeta function.** For $s>1$:

$$
\zeta(s)=\sum_{n=1}^{\infty}\frac{1}{n^{s}}.
$$

- $\sum 1/n^{2}$ converges since $1/n^{2}\sim 1/(n^{2}+n)$.
- $\zeta(2)=\pi^{2}/6$ (Euler).

**Divergent examples.** Since $\sum 1/n$ diverges:
- $\sum 1/\sqrt{n(n+10)}$ diverges ($\sim 1/n$).
- $\sum\sin(1/n)$ diverges ($\sin(1/n)\sim 1/n$).

## 10.10 The Integral Test

### 10.10.1 Theorem 10.11

Let $f$ be positive and decreasing for $x\ge 1$. Define:

$$
s_{n}=\sum_{k=1}^{n}f(k),\qquad t_{n}=\int_{1}^{n}f(x)\,dx.
$$

Then $\{s_{n}\}$ and $\{t_{n}\}$ **both converge or both diverge**.

**Proof.** Comparing $f$ with step functions:

$$
\sum_{k=2}^{n}f(k)\le\int_{1}^{n}f(x)\,dx\le\sum_{k=1}^{n-1}f(k),
$$

i.e. $s_{n}-f(1)\le t_{n}\le s_{n-1}$. Both sequences are monotone increasing, so they are either both bounded or both unbounded.

### 10.10.2 Example 1 鈥?$p$-Series

$$
\sum_{n=1}^{\infty}\frac{1}{n^{s}}\quad\text{converges}\iff s>1.
$$

Take $f(x)=x^{-s}$. Then:

$$
t_{n}=\int_{1}^{n}\frac{dx}{x^{s}}=\begin{cases}\dfrac{n^{1-s}-1}{1-s}&s\neq 1,\\[6pt]\log n&s=1.\end{cases}
$$

- $s>1$: $n^{1-s}\to 0$, so $t_{n}\to\dfrac{1}{s-1}$. Converges.
- $s\le 1$: $t_{n}\to\infty$. Diverges (harmonic series when $s=1$).

### 10.10.3 Example 2 鈥?Logarithmic $p$-Series

$$
\sum_{n=2}^{\infty}\frac{1}{n(\log n)^{s}}\quad\text{converges}\iff s>1.
$$

The corresponding integral is:

$$
t_{n}=\int_{2}^{n}\frac{dx}{x(\log x)^{s}}=\begin{cases}\dfrac{(\log n)^{1-s}-(\log 2)^{1-s}}{1-s}&s\neq 1,\\[6pt]\log(\log n)-\log(\log 2)&s=1.\end{cases}
$$

Thus $\{t_{n}\}$ converges iff $s>1$.

## 10.11 The Root Test and the Ratio Test

### 10.11.1 Theorem 10.12 鈥?Root Test

Let $\sum a_{n}$ have nonnegative terms and suppose:

$$
\lim_{n\to\infty}a_{n}^{1/n}=R.
$$

| Case | Conclusion |
|------|-----------|
| $R<1$ | **Converges** |
| $R>1$ | **Diverges** |
| $R=1$ | **Inconclusive** |

**Proof sketch.** If $R<1$, choose $x$ with $R<x<1$; then $a_{n}\le x^{n}$ for large $n$. If $R>1$, then $a_{n}>1$ infinitely often, so $a_{n}\not\to 0$.

**Examples.**
- $\sum(\log n)^{-n}$: $a_{n}^{1/n}=1/\log n\to 0$. **Converges.**
- $\sum\bigl[n/(n+1)\bigr]^{n^{2}}$: $a_{n}^{1/n}=\bigl(1+1/n\bigr)^{-n}\to 1/e$. **Converges.**

### 10.11.2 Theorem 10.13 鈥?Ratio Test

Let $\sum a_{n}$ have positive terms and suppose:

$$
\lim_{n\to\infty}\frac{a_{n+1}}{a_{n}}=L.
$$

| Case | Conclusion |
|------|-----------|
| $L<1$ | **Converges** |
| $L>1$ | **Diverges** |
| $L=1$ | **Inconclusive** |

**Proof sketch.** If $L<1$, choose $x$ with $L<x<1$; then $a_{n+1}/a_{n}<x$ for large $n$, so $a_{n}\le cx^{n}$. If $L>1$, then $a_{n+1}>a_{n}$ eventually, so $a_{n}\not\to 0$.

> **Warning.** $a_{n+1}/a_{n}<1$ for all $n$ does **not** imply convergence (e.g. harmonic series).

**Example.** $\sum n!/n^{n}$:

$$
\frac{a_{n+1}}{a_{n}}=\Bigl(\frac{n}{n+1}\Bigr)^{n}=\frac{1}{(1+1/n)^{n}}\to\frac{1}{e}<1.
$$

**Converges.** In particular, $n!/n^{n}\to 0$, i.e. $n!=o(n^{n})$.

> Both tests are special cases of the comparison test with a geometric series.

## 10.12 Alternating Series

### 10.12.1 Definition

An **alternating series** is a series whose terms alternate in sign:
$$
\sum_{n=1}^{\infty}(-1)^{n-1}a_n = a_1 - a_2 + a_3 - a_4 + \cdots, \qquad a_n > 0.
$$

**Examples:**
- Logarithmic series: $\displaystyle \log(1+x) = x - \frac{x^2}{2} + \frac{x^3}{3} - \frac{x^4}{4} + \cdots$, converges for $-1 < x \le 1$. At $x=1$:
  $$\log 2 = 1 - \frac{1}{2} + \frac{1}{3} - \frac{1}{4} + \cdots$$
- Gregory鈥揕eibniz series (1671/1673):
  $$\frac{\pi}{4} = 1 - \frac{1}{3} + \frac{1}{5} - \frac{1}{7} + \cdots$$

> The alternating harmonic series converges (to $\log 2$), while the harmonic series $\sum 1/n$ diverges.

### 10.12.2 Leibniz's Rule

**Theorem.** If $\{a_n\}$ is **monotonic decreasing** and $a_n \to 0$, then the alternating series $\sum (-1)^{n-1}a_n$ **converges**.

**Error estimate.** If $S$ is the sum and $s_n$ the $n$th partial sum, then
$$
0 < (-1)^n(S - s_n) < a_{n+1} \qquad (n \ge 1).
$$
- The error has the **same sign** as the first neglected term $(-1)^n a_{n+1}$.
- The **absolute error** is **less than** the first neglected term.

**Proof sketch.**
- Even partial sums $s_{2n}$ form an increasing sequence: $s_{2n+2} - s_{2n} = a_{2n+1} - a_{2n+2} > 0$.
- Odd partial sums $s_{2n-1}$ form a decreasing sequence.
- Both are bounded, so $s_{2n} \to S'$ and $s_{2n-1} \to S''$.
- $S' - S'' = \lim (-a_{2n}) = 0$, hence $S' = S'' = S$.
- From $s_{2n} \nearrow S \le s_{2n+1} \searrow$, the inequalities follow.

**Examples:**
1. $\sum (-1)^{n-1}/n$ converges by Leibniz (sum = $\log 2$).
2. $\sum (-1)^n (\log n)/n$ converges: $(\log n)/n \to 0$, and for $f(x)=(\log x)/x$, $f'(x)=(1-\log x)/x^2 < 0$ when $x>e$, so the sequence decreases for $n\ge 3$.

### 10.12.3 Euler's Constant

**Construction.** Define
$$
a_{2n-1} = \frac{1}{n}, \qquad a_{2n} = \int_n^{n+1}\frac{dx}{x} = \log(n+1)-\log n.
$$
Then $a_n \to 0$ and $a_n \searrow$, so $\sum (-1)^{n-1}a_n$ converges. Its $(2n-1)$st partial sum is
$$
s_{2n-1} = 1 + \frac{1}{2} + \cdots + \frac{1}{n} - \log n.
$$
Since $s_{2n-1}$ tends to a limit, we obtain **Euler's constant**:
$$
\boxed{\lim_{n\to\infty}\Bigl(1 + \frac{1}{2} + \cdots + \frac{1}{n} - \log n\Bigr) = C}
$$

- $C \approx 0.5772156649\dots$ (to ten decimals).
- It is still **unknown** whether $C$ is rational or irrational.

**Asymptotic formula:**
$$
\sum_{k=1}^{n}\frac{1}{k} = \log n + C + o(1) \qquad (n\to\infty).
$$
Hence the partial sums of the harmonic series are asymptotically equal to $\log n$:
$$
\sum_{k=1}^{n}\frac{1}{k} \sim \log n.
$$

**Example (alternating harmonic series).** Let $s_m = \sum_{k=1}^{m}(-1)^{k-1}/k$. Separating even and odd terms for $m=2n$:
$$
s_{2n} = \sum_{k=1}^{n}\frac{1}{2k-1} - \sum_{k=1}^{n}\frac{1}{2k}
     = \sum_{k=1}^{2n}\frac{1}{k} - \sum_{k=1}^{n}\frac{1}{k}.
$$
Applying the asymptotic formula:
$$
s_{2n} = \bigl(\log 2n + C + o(1)\bigr) - \bigl(\log n + C + o(1)\bigr) = \log 2 + o(1).
$$
Therefore $s_{2n} \to \log 2$, confirming the sum of the alternating harmonic series.

## 10.13 Conditional and Absolute Convergence

### 10.13.1 Absolute Convergence Implies Convergence

**Theorem.** If $\sum |a_n|$ converges, then $\sum a_n$ also converges, and
$$
\Bigl|\sum_{n=1}^{\infty}a_n\Bigr| \le \sum_{n=1}^{\infty}|a_n|.
$$

**Proof sketch.**
- **Real case:** Let $b_n = a_n + |a_n|$. Then $b_n$ is either $0$ or $2|a_n|$, so $0 \le b_n \le 2|a_n|$. By comparison, $\sum b_n$ converges; hence $\sum a_n = \sum b_n - \sum |a_n|$ converges.
- **Complex case:** Write $a_n = u_n + iv_n$. Since $|u_n| \le |a_n|$ and $|v_n| \le |a_n|$, absolute convergence of $\sum |a_n|$ implies convergence of $\sum |u_n|$ and $\sum |v_n|$, hence of $\sum u_n$ and $\sum v_n$.
- The triangle inequality $|\sum_{k=1}^n a_k| \le \sum_{k=1}^n |a_k|$ gives the stated bound as $n\to\infty$.

### 10.13.2 Definitions

- **Absolutely convergent:** $\sum |a_n|$ converges.
- **Conditionally convergent:** $\sum a_n$ converges but $\sum |a_n|$ diverges.

> The alternating harmonic series $\sum (-1)^{n-1}/n$ is **conditionally convergent**.

**Linearity.** If $\sum a_n$ and $\sum b_n$ are absolutely convergent, so is $\sum(\alpha a_n + \beta b_n)$ for any scalars $\alpha,\beta$.

## 10.14 The Convergence Tests of Dirichlet and Abel

### 10.14.1 Abel's Partial Summation Formula

Let $\{a_n\},\{b_n\}$ be sequences of complex numbers and let $A_n = \sum_{k=1}^n a_k$. Then
$$
\boxed{\sum_{k=1}^{n}a_k b_k = A_n b_{n+1} + \sum_{k=1}^{n}A_k(b_k - b_{k+1})}
$$

**Proof.** With $A_0=0$, write $a_k = A_k - A_{k-1}$; the identity follows by rearranging the double sum.

> If $A_n b_{n+1} \to L$ and $\sum A_k(b_k - b_{k+1})$ converges, then $\sum a_k b_k$ converges.

### 10.14.2 Dirichlet's Test

**Theorem.** Let $\sum a_n$ be a series of complex terms whose partial sums form a **bounded** sequence. Let $\{b_n\}$ be a **decreasing** sequence with $b_n \to 0$. Then $\sum a_n b_n$ **converges**.

**Proof sketch.** $|A_n| \le M$ implies $A_n b_{n+1} \to 0$. Since $b_n \searrow$,
$$
|A_k(b_k - b_{k+1})| \le M(b_k - b_{k+1}),
$$
and $\sum (b_k - b_{k+1})$ is a convergent telescoping series, so $\sum A_k(b_k - b_{k+1})$ converges absolutely.

### 10.14.3 Abel's Test

**Theorem.** Let $\sum a_n$ be a **convergent** series of complex terms and let $\{b_n\}$ be a **monotonic convergent** sequence of real terms. Then $\sum a_n b_n$ **converges**.

> The proof is analogous to Dirichlet's test, using that $\{A_n\}$ is bounded and $A_n b_{n+1}$ converges.

### 10.14.4 Bounded Partial Sums of a Geometric Series on the Unit Circle

**Theorem.** For every real $\theta$ not an integer multiple of $\pi$,
$$
\sum_{k=1}^{n}e^{2ik\theta} = \frac{\sin n\theta}{\sin\theta}\,e^{i(n+1)\theta},
\qquad
\Bigl|\sum_{k=1}^{n}e^{2ik\theta}\Bigr| \le \frac{1}{|\sin\theta|}.
$$

**Proof.** Use the geometric-series formula $\sum_{k=1}^n x^k = x(x^n-1)/(x-1)$ with $x=e^{2i\theta}$; simplify using Euler's formula to obtain the closed form. The estimate follows from $|\sin n\theta|\le 1$ and $|e^{i(n+1)\theta}|=1$.

> This shows that $\sum x^n$ with $|x|=1$, $x\neq 1$ has bounded partial sums鈥攁 key example for Dirichlet's test.

### 10.14.5 Applications

**Example.** If $\{b_n\}$ is any decreasing real sequence with $b_n \to 0$ and $|x|=1$, $x\neq 1$, then by Dirichlet's test
$$
\sum_{n=1}^{\infty} b_n x^n \quad\text{converges}.
$$
- Leibniz's rule is the special case $x=-1$.
- Writing $x=e^{i\theta}$ and taking real/imaginary parts, the trigonometric series
  $$\sum_{n=1}^{\infty} b_n\cos n\theta, \qquad \sum_{n=1}^{\infty} b_n\sin n\theta$$
  both converge (for $\theta$ not a multiple of $2\pi$).

**Special case $b_n = n^{-\alpha}$ $(\alpha>0)$:**
$$
\sum_{n=1}^{\infty}\frac{e^{in\theta}}{n^{\alpha}},\quad
\sum_{n=1}^{\infty}\frac{\cos n\theta}{n^{\alpha}},\quad
\sum_{n=1}^{\infty}\frac{\sin n\theta}{n^{\alpha}}
$$
all converge. When $\alpha>1$ they converge **absolutely** (dominated by $\sum n^{-\alpha}$).

## 10.15 Rearrangements of Series

### 10.15.1 A Surprising Example

Finite sums can be rearranged without changing their value, but this is **not always true** for infinite series (Cauchy, 1833).

**Example.** The alternating harmonic series
$$
1 - \frac{1}{2} + \frac{1}{3} - \frac{1}{4} + \cdots = \log 2.
$$
Rearrange it by taking **two positive terms followed by one negative term**:
$$
1 + \frac{1}{3} - \frac{1}{2} + \frac{1}{5} + \frac{1}{7} - \frac{1}{4} + \cdots
$$
Let $t_{3m}$ be the $(3m)$th partial sum:
$$
t_{3m} = \sum_{k=1}^{2m}\frac{1}{2k-1} - \sum_{k=1}^{m}\frac{1}{2k}
     = \sum_{k=1}^{4m}\frac{1}{k} - \frac{1}{2}\sum_{k=1}^{2m}\frac{1}{k} - \frac{1}{2}\sum_{k=1}^{m}\frac{1}{k}.
$$
Using $\sum_{k=1}^{n}1/k = \log n + C + o(1)$,
$$
t_{3m} = (\log 4m + C) - \tfrac{1}{2}(\log 2m + C) - \tfrac{1}{2}(\log m + C) + o(1)
     = \tfrac{3}{2}\log 2 + o(1).
$$
Hence the rearranged series converges to $\frac{3}{2}\log 2 \neq \log 2$.

### 10.15.2 Definition of Rearrangement

A **permutation** of $\mathbb{P}=\{1,2,3,\dots\}$ is a one-to-one mapping $f:\mathbb{P}\to\mathbb{P}$. If $b_n = a_{f(n)}$, then $\sum b_n$ is called a **rearrangement** of $\sum a_n$.

### 10.15.3 Absolute Convergence Preserves the Sum

**Theorem.** Let $\sum a_n$ be **absolutely convergent** with sum $S$. Then every rearrangement of $\sum a_n$ also converges absolutely and has sum $S$.

**Proof sketch.** Let $b_n = a_{f(n)}$. Then $\sum|b_n|$ converges because its partial sums are bounded by $\sum|a_n|$. Given $\varepsilon>0$, choose $N$ so that $|A_N-S|<\varepsilon/2$ and $\sum_{k>N}|a_k|<\varepsilon/2$. Choose $M$ large enough that $\{1,\dots,N\}\subseteq\{f(1),\dots,f(M)\}$. For $n\ge M$,
$$
|B_n - S| \le |B_n - A_N| + |A_N - S| < \frac{\varepsilon}{2} + \frac{\varepsilon}{2} = \varepsilon.
$$
Thus $B_n \to S$.

### 10.15.4 Positive and Negative Parts

Define
$$
a_n^+ = \frac{a_n+|a_n|}{2} = \max(a_n,0), \qquad a_n^- = \frac{a_n-|a_n|}{2} = \min(a_n,0).
$$

**Theorem.** For a series $\sum a_n$ of real terms:
- **(a)** If $\sum a_n$ is **conditionally convergent**, both $\sum a_n^+$ and $\sum a_n^-$ **diverge**.
- **(b)** If $\sum a_n$ is **absolutely convergent**, both $\sum a_n^+$ and $\sum a_n^-$ **converge**, and
  $$\sum_{n=1}^{\infty}a_n = \sum_{n=1}^{\infty}a_n^+ + \sum_{n=1}^{\infty}a_n^-.$$

> Part (a) follows from linearity: $\sum a_n$ converges but $\sum|a_n|$ diverges, so neither signed part can converge.

### 10.15.5 Riemann's Rearrangement Theorem

**Theorem.** Let $\sum a_n$ be a **conditionally convergent** series of real terms, and let $S$ be any real number. Then there exists a rearrangement $\sum b_n$ of $\sum a_n$ which converges to $S$.

**Proof sketch.** Since $\sum a_n^+$ diverges to $+\infty$ and $\sum a_n^-$ diverges to $-\infty$ (and $a_n\to 0$), we can:
1. Take just enough positive terms so their sum **exceeds** $S$.
2. Add just enough negative terms so the sum falls **below** $S$.
3. Repeat.

Each partial sum of the rearrangement differs from $S$ by at most one term, and since $a_n\to 0$, the partial sums converge to $S$.

> **Key insight:** Absolute convergence guarantees rearrangement invariance; conditional convergence allows rearrangement to any desired sum.

## 10.16 Improper Integrals

### 10.16.1 Infinite Integrals (First Kind)

If $\int_a^b f(x)\,dx$ exists for every $b\ge a$, define the **infinite integral**
$$
\int_a^{\infty} f(x)\,dx = \lim_{b\to+\infty}\int_a^{b}f(x)\,dx.
$$
The integral **converges** if the limit exists and is finite; otherwise it **diverges**.

**Examples:**
1. $\displaystyle\int_1^{\infty}x^{-s}\,dx$ converges iff $s>1$, with value $1/(s-1)$. (Analogous to the zeta series.)
2. $\displaystyle\int_0^{\infty}\sin x\,dx$ diverges ($1-\cos b$ has no limit).
3. $\displaystyle\int_{-\infty}^{\infty}e^{-a|x|}\,dx = 2/a$ for $a>0$.

For doubly infinite intervals:
$$
\int_{-\infty}^{\infty}f(x)\,dx = \int_{-\infty}^{c}f(x)\,dx + \int_{c}^{\infty}f(x)\,dx,
$$
convergent iff **both** integrals on the right converge (the choice of $c$ is irrelevant).

### 10.16.2 Convergence Tests for Nonnegative Integrands

**Theorem (Boundedness criterion).** If $f(x)\ge 0$ for $x\ge a$, then $\int_a^{\infty}f(x)\,dx$ converges iff there exists $M>0$ such that $\int_a^b f(x)\,dx \le M$ for all $b\ge a$.

**Comparison test.** If $0\le f(x)\le g(x)$ for $x\ge a$ and $\int_a^{\infty}g$ converges, then $\int_a^{\infty}f$ also converges and $\int_a^{\infty}f \le \int_a^{\infty}g$.

**Limit comparison test.** Let $f(x)\ge 0$, $g(x)>0$ for $x\ge a$. If
$$
\lim_{x\to+\infty}\frac{f(x)}{g(x)} = c \neq 0,
$$
then $\int_a^{\infty}f$ and $\int_a^{\infty}g$ either both converge or both diverge. If $c=0$, convergence of $\int_a^{\infty}g$ implies convergence of $\int_a^{\infty}f$.

**Example.** $\int_1^{\infty}e^{-x}x^{s}\,dx$ converges for every real $s$ (compare with $x^{-2}$).

### 10.16.3 Improper Integrals of the Second Kind

Suppose $f$ is defined on $(a,b]$ and $\int_x^b f(t)\,dt$ exists for $a<x\le b$. Define
$$
\int_{a+}^{b}f(t)\,dt = \lim_{x\to a^+}\int_x^{b}f(t)\,dt.
$$

**Example.** $\displaystyle\int_{0+}^{b}t^{-s}\,dt$ converges iff $s<1$.

> **Connection between the two kinds.** By the substitution $t=1/u$,
> $$\int_x^{b}t^{-s}\,dt = \int_{1/b}^{1/x}u^{s-2}\,du,$$
> so convergence of the second-kind integral for $s$ is equivalent to convergence of the first-kind integral for $2-s$.

**Gabriel's horn.** For $f(x)=x^{-3/4}$ on $(0,1]$:
- $\int_0^1 f(x)\,dx$ **converges** (finite area),
- but $\int_0^1 \pi f(x)^2\,dx$ **diverges** (infinite volume of revolution).

If $f$ is unbounded at an interior point $c$, split:
$$
\int_{a+}^{b-}f(t)\,dt = \int_{a+}^{c}f(t)\,dt + \int_{c}^{b-}f(t)\,dt.
$$
Mixed combinations (e.g. $\int_{a+}^{\infty}$) are defined analogously.

### 10.16.4 The Gamma Function

For $s>0$ the integral
$$
\Gamma(s) = \int_{0+}^{\infty}e^{-t}t^{s-1}\,dt
$$
converges. Split it as $\int_{0+}^{1} + \int_{1}^{\infty}$:
- The second integral converges for all real $s$ (by comparison with $e^{-t/2}$).
- The first integral converges for $s>0$ (by comparison with $t^{s-1}$).

**Key property:** $\Gamma(n+1) = n!$ for every integer $n\ge 0$.

> The gamma function, introduced by Euler in 1729, extends factorials to positive real arguments.

[<- Previous: 9. Complex Numbers](09-complex-numbers.md) | [Next: 11. Sequences and Series of Functions ->](11-sequences-and-series-of-functions.md)
