[<- Previous: 12. Convex Sets](12-convex-sets.md) | [Next: B. Iwasawa Decomposition and Others ->](b-iwasawa-decomposition-and-others.md)

# A. Complex Numbers

## A.1 Definitions and Basic Properties

The **complex numbers** are a set of objects which can be added and multiplied, the sum and product of two complex numbers being also a complex number, and satisfy the following conditions:

1. Every real number is a complex number, and if $\alpha, \beta$ are real numbers, then their sum and product as complex numbers are the same as their sum and product as real numbers.
2. There is a complex number denoted by $i$ such that $i^2 = -1$.
3. Every complex number can be written uniquely in the form $a + bi$ where $a, b$ are real numbers.
4. The ordinary laws of arithmetic concerning addition and multiplication are satisfied:
   - $(\alpha\beta)\gamma = \alpha(\beta\gamma)$ and $(\alpha + \beta) + \gamma = \alpha + (\beta + \gamma)$
   - $\alpha(\beta + \gamma) = \alpha\beta + \alpha\gamma$ and $(\beta + \gamma)\alpha = \beta\alpha + \gamma\alpha$
   - $\alpha\beta = \beta\alpha$ and $\alpha + \beta = \beta + \alpha$
   - $1\alpha = \alpha$, $0\alpha = 0$, $\alpha + (-1)\alpha = 0$

With each complex number $a + bi$, we associate the vector $(a, b)$ in the plane. Let $\alpha = a_1 + a_2 i$ and $\beta = b_1 + b_2 i$. Then:

$$
\alpha + \beta = a_1 + b_1 + (a_2 + b_2)i.
$$

Hence addition of complex numbers is carried out "componentwise" and corresponds to addition of vectors in the plane.

In multiplying complex numbers, we use the rule $i^2 = -1$ to simplify a product and to put it in the form $a + bi$. For instance:

$$
\begin{aligned}
(2 + 3i)(1 - i) &= 2(1-i) + 3i(1-i) \\
&= 2 - 2i + 3i - 3i^2 \\
&= 2 + i + 3 \\
&= 5 + i.
\end{aligned}
$$

## A.2 Conjugate, Inverse, and Absolute Value

Let $\alpha = a + bi$ be a complex number. We define $\bar{\alpha}$ to be $a - bi$. The complex number $\bar{\alpha}$ is called the **conjugate** of $\alpha$. We see at once that:

$$
\alpha\bar{\alpha} = a^2 + b^2.
$$

With the vector interpretation of complex numbers, $\alpha\bar{\alpha}$ is the square of the distance of the point $(a, b)$ from the origin.

If $\alpha = a + bi \neq 0$, and we let

$$
\lambda = \frac{\bar{\alpha}}{a^2 + b^2},
$$

then $\alpha\lambda = \lambda\alpha = 1$. The number $\lambda$ is called the **inverse** of $\alpha$, and is denoted by $\alpha^{-1}$ or $1/\alpha$. We see that we can divide by complex numbers $\neq 0$.

We define the **absolute value** of a complex number $\alpha = a_1 + ia_2$ to be:

$$
|\alpha| = \sqrt{a_1^2 + a_2^2}.
$$

This absolute value is none other than the norm of the vector $(a_1, a_2)$. In terms of absolute values:

$$
\alpha^{-1} = \frac{\bar{\alpha}}{|\alpha|^2} \quad (\alpha \neq 0).
$$

The triangle inequality for the norm of vectors can now be stated for complex numbers:

$$
|\alpha + \beta| \leq |\alpha| + |\beta|.
$$

## A.3 The Fundamental Theorem of Algebra

**Theorem 3.1 (Fundamental Theorem of Algebra).** The complex numbers are algebraically closed; in other words, every polynomial $f \in \mathbb{C}[t]$ of degree $\geq 1$ has a root in $\mathbb{C}$.

**Proof.** We may write

$$
f(t) = a_n t^n + a_{n-1} t^{n-1} + \cdots + a_0
$$

with $a_n \neq 0$. For every real $R > 0$, the function $|f|$ is continuous on the closed disc of radius $R$, and hence has a minimum value on this disc. On the other hand, from the expression

$$
f(t) = a_n t^n \left(1 + \frac{a_{n-1}}{a_n t} + \cdots + \frac{a_0}{a_n t^n}\right)
$$

we see that when $|t|$ becomes large, $|f(t)|$ also becomes large. Consequently, there exists a positive number $R_0$ such that, if $z_0$ is a minimum point of $|f|$ on the closed disc of radius $R_0$, then $|f(t)| \geq |f(z_0)|$ for all complex numbers $t$. In other words, $z_0$ is an absolute minimum for $|f|$.

We shall prove that $f(z_0) = 0$. We express $f$ in the form

$$
f(t) = c_0 + c_1(t - z_0) + \cdots + c_n(t - z_0)^n.
$$

If $f(z_0) \neq 0$, then $c_0 = f(z_0) \neq 0$. Let $z = t - z_0$, and let $m$ be the smallest integer $> 0$ such that $c_m \neq 0$. Then we can write:

$$
f(t) = f_1(z) = c_0 + c_m z^m + z^{m+1} g(z)
$$

for some polynomial $g$. Let $z_1$ be a complex number such that $z_1^m = -c_0/c_m$, and consider values of $z$ of type $z = \lambda z_1$ where $\lambda$ is real, $0 \leq \lambda \leq 1$. Then:

$$
f(t) = f_1(\lambda z_1) = c_0\bigl[1 - \lambda^m + \lambda^{m+1} z_1^{m+1} c_0^{-1} g(\lambda z_1)\bigr].
$$

There exists a number $C > 0$ such that for all $\lambda$ with $0 \leq \lambda \leq 1$ we have $|z_1^{m+1} c_0^{-1} g(\lambda z_1)| \leq C$, and hence:

$$
|f_1(\lambda z_1)| \leq |c_0|(1 - \lambda^m + C\lambda^{m+1}).
$$

For sufficiently small $\lambda$ with $0 < \lambda < 1$ we have $0 < 1 - \lambda^m + C\lambda^{m+1} < 1$ (the right inequality amounts to $C\lambda < 1$). Then $|f_1(\lambda z_1)| < |c_0|$, contradicting the hypothesis that $|f(z_0)| \leq |f(t)|$ for all complex numbers $t$. This concludes the proof. ∎
---

[<- Previous: 12. Convex Sets](12-convex-sets.md) | [Next: B. Iwasawa Decomposition and Others ->](b-iwasawa-decomposition-and-others.md)
