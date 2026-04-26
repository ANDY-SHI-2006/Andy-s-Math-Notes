[<- 上一章: 12. 凸集](12-凸集.md) | [下一章: B. 岩泽分解及其他 ->](b-岩泽分解及其他.md)

# A. 复数

## A.1 定义与基本性质

**复数**是一类可以进行加法和乘法运算的对象，两个复数的和与积仍然是复数，并且满足以下条件：

1. 每一个实数都是复数，如果 $\alpha, \beta$ 是实数，那么它们作为复数的和与积与作为实数的和与积相同。
2. 存在一个记为 $i$ 的复数，使得 $i^2 = -1$。
3. 每一个复数都可以唯一地写成 $a + bi$ 的形式，其中 $a, b$ 是实数。
4. 关于加法和乘法的普通算术法则成立：
   - $(\alpha\beta)\gamma = \alpha(\beta\gamma)$ 且 $(\alpha + \beta) + \gamma = \alpha + (\beta + \gamma)$
   - $\alpha(\beta + \gamma) = \alpha\beta + \alpha\gamma$ 且 $(\beta + \gamma)\alpha = \beta\alpha + \gamma\alpha$
   - $\alpha\beta = \beta\alpha$ 且 $\alpha + \beta = \beta + \alpha$
   - $1\alpha = \alpha$，$0\alpha = 0$，$\alpha + (-1)\alpha = 0$

对于每个复数 $a + bi$，我们将其与平面上的向量 $(a, b)$ 对应。设 $\alpha = a_1 + a_2 i$，$\beta = b_1 + b_2 i$。则：

$$
\alpha + \beta = a_1 + b_1 + (a_2 + b_2)i.
$$

因此，复数的加法是“按分量”进行的，对应于平面上向量的加法。

在乘法运算中，我们使用规则 $i^2 = -1$ 来简化乘积并将其写成 $a + bi$ 的形式。例如：

$$
\begin{aligned}
(2 + 3i)(1 - i) &= 2(1-i) + 3i(1-i) \\
&= 2 - 2i + 3i - 3i^2 \\
&= 2 + i + 3 \\
&= 5 + i.
\end{aligned}
$$

## A.2 共轭、逆与绝对值

设 $\alpha = a + bi$ 是一个复数。我们定义 $\bar{\alpha}$ 为 $a - bi$。复数 $\bar{\alpha}$ 称为 $\alpha$ 的**共轭**。我们立即得到：

$$
\alpha\bar{\alpha} = a^2 + b^2.
$$

借助复数的向量解释，$\alpha\bar{\alpha}$ 是点 $(a, b)$ 到原点距离的平方。

如果 $\alpha = a + bi \neq 0$，令

$$
\lambda = \frac{\bar{\alpha}}{a^2 + b^2},
$$

则 $\alpha\lambda = \lambda\alpha = 1$。数 $\lambda$ 称为 $\alpha$ 的**逆**，记为 $\alpha^{-1}$ 或 $1/\alpha$。由此可见，我们可以用非零复数作除法。

我们定义复数 $\alpha = a_1 + ia_2$ 的**绝对值**为：

$$
|\alpha| = \sqrt{a_1^2 + a_2^2}.
$$

这个绝对值就是向量 $(a_1, a_2)$ 的范数。用绝对值表示：

$$
\alpha^{-1} = \frac{\bar{\alpha}}{|\alpha|^2} \quad (\alpha \neq 0).
$$

向量范数的三角不等式现在可以对复数表述为：

$$
|\alpha + \beta| \leq |\alpha| + |\beta|.
$$

## A.3 代数基本定理

**定理 3.1（代数基本定理）。** 复数是代数闭的；换言之，每个次数 $\geq 1$ 的多项式 $f \in \mathbb{C}[t]$ 在 $\mathbb{C}$ 中都有根。

**证明。** 我们可以写成

$$
f(t) = a_n t^n + a_{n-1} t^{n-1} + \cdots + a_0
$$

其中 $a_n \neq 0$。对每个实数 $R > 0$，函数 $|f|$ 在半径为 $R$ 的闭圆盘上连续，因此在此圆盘上有最小值。另一方面，从表达式

$$
f(t) = a_n t^n \left(1 + \frac{a_{n-1}}{a_n t} + \cdots + \frac{a_0}{a_n t^n}\right)
$$

可以看出，当 $|t|$ 变得很大时，$|f(t)|$ 也变得很大。因此，存在一个正数 $R_0$，使得如果 $z_0$ 是 $|f|$ 在半径为 $R_0$ 的闭圆盘上的最小值点，那么对所有复数 $t$ 都有 $|f(t)| \geq |f(z_0)|$。换言之，$z_0$ 是 $|f|$ 的绝对最小值点。

我们将证明 $f(z_0) = 0$。将 $f$ 表示为

$$
f(t) = c_0 + c_1(t - z_0) + \cdots + c_n(t - z_0)^n.
$$

如果 $f(z_0) \neq 0$，则 $c_0 = f(z_0) \neq 0$。令 $z = t - z_0$，并设 $m$ 是满足 $c_m \neq 0$ 的最小正整数。则我们可以写成：

$$
f(t) = f_1(z) = c_0 + c_m z^m + z^{m+1} g(z)
$$

对某个多项式 $g$。令 $z_1$ 是满足 $z_1^m = -c_0/c_m$ 的复数，并考虑形如 $z = \lambda z_1$ 的值，其中 $\lambda$ 是实数，$0 \leq \lambda \leq 1$。则：

$$
f(t) = f_1(\lambda z_1) = c_0\bigl[1 - \lambda^m + \lambda^{m+1} z_1^{m+1} c_0^{-1} g(\lambda z_1)\bigr].
$$

存在 $C > 0$，使得对所有满足 $0 \leq \lambda \leq 1$ 的 $\lambda$，都有 $|z_1^{m+1} c_0^{-1} g(\lambda z_1)| \leq C$，因此：

$$
|f_1(\lambda z_1)| \leq |c_0|(1 - \lambda^m + C\lambda^{m+1}).
$$

对充分小的满足 $0 < \lambda < 1$ 的 $\lambda$，有 $0 < 1 - \lambda^m + C\lambda^{m+1} < 1$（右边的不等式等价于 $C\lambda < 1$）。于是 $|f_1(\lambda z_1)| < |c_0|$，这与假设 $|f(z_0)| \leq |f(t)|$ 对所有复数 $t$ 成立相矛盾。证明完毕。 ∎

---

[<- 上一章: 12. 凸集](12-凸集.md) | [下一章: B. 岩泽分解及其他 ->](b-岩泽分解及其他.md)
