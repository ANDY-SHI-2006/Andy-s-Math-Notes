# Exercise 1：级数收敛判断 —— 详细解答

> 题目来源：Week 8 Exercise Session（Midterm Review）
>
> 要求：判断级数是绝对收敛（absolutely convergent）、条件收敛（conditionally convergent）还是发散（divergent）。

---

## 第 (a) 题

### 题目

$$\sum_{n=2}^{\infty} \frac{(-1)^n \sqrt{n}}{\log n}$$

---

### 第一步：识别级数类型

看到 $(-1)^n$，说明这是一个**交错级数（alternating series）**。

通项可以写成 $(-1)^n a_n$ 的形式，其中：

$$a_n = \frac{\sqrt{n}}{\log n}$$

---

### 第二步：判断绝对收敛性

**绝对收敛**的意思是：把 $(-1)^n$ 去掉，只看绝对值级数是否收敛。

绝对值级数为：

$$\sum_{n=2}^{\infty} \left|\frac{(-1)^n \sqrt{n}}{\log n}\right| = \sum_{n=2}^{\infty} \frac{\sqrt{n}}{\log n}$$

---

### 第三步：用通项判别法判断绝对值级数

**通项判别法（nth term test）**：如果级数的通项不趋于 0，则级数必定发散。

我们来看 $a_n = \frac{\sqrt{n}}{\log n}$ 当 $n \to \infty$ 时的极限。

当 $n$ 很大时：
- $\sqrt{n} = n^{1/2}$ 以幂函数速度增长
- $\log n$ 以对数速度增长
- 幂函数的增长速度远快于对数函数

因此：

$$\lim_{n\to\infty} \frac{\sqrt{n}}{\log n} = +\infty$$

具体来说，可以用洛必达法则验证：

$$\lim_{x\to\infty} \frac{\sqrt{x}}{\log x} = \lim_{x\to\infty} \frac{\frac{1}{2\sqrt{x}}}{\frac{1}{x}} = \lim_{x\to\infty} \frac{x}{2\sqrt{x}} = \lim_{x\to\infty} \frac{\sqrt{x}}{2} = +\infty$$

---

### 第四步：得出结论

因为 $\lim_{n\to\infty} a_n = +\infty \neq 0$，所以：

**绝对值级数 $\sum \frac{\sqrt{n}}{\log n}$ 发散。**

更进一步，原级数的通项 $\frac{(-1)^n \sqrt{n}}{\log n}$ 的绝对值也不趋于 0，所以**原级数本身也发散**。

---

### 第 (a) 题答案

**发散（divergent）** ❌

---

---

## 第 (b) 题

### 题目

$$1 - e + \frac{e^2}{2!} - \frac{e^3}{3!} + \frac{e^4}{4!} - \cdots$$

---

### 第一步：写成规范的级数形式

观察这个级数的规律：
- 第 0 项（$n=0$）：$1 = \frac{(-e)^0}{0!}$
- 第 1 项（$n=1$）：$-e = \frac{(-e)^1}{1!}$
- 第 2 项（$n=2$）：$\frac{e^2}{2!} = \frac{(-e)^2}{2!}$
- 第 3 项（$n=3$）：$-\frac{e^3}{3!} = \frac{(-e)^3}{3!}$

所以这个级数可以写成：

$$\sum_{n=0}^{\infty} \frac{(-e)^n}{n!}$$

---

### 第二步：识别这是哪个函数的泰勒级数

回忆 $e^x$ 的泰勒级数（在 $x=0$ 处）：

$$e^x = \sum_{n=0}^{\infty} \frac{x^n}{n!} = 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \cdots$$

这个级数对所有实数 $x$ 都收敛，收敛半径 $r = \infty$。

把 $x = -e$ 代入：

$$e^{-e} = \sum_{n=0}^{\infty} \frac{(-e)^n}{n!}$$

这正是题目中的级数！

---

### 第三步：判断收敛性

因为 $e^x$ 的泰勒级数对**所有 $x \in \mathbb{R}$** 都绝对收敛（收敛半径为无穷大），而 $-e$ 是一个有限实数，所以：

$$\sum_{n=0}^{\infty} \frac{(-e)^n}{n!} = e^{-e}$$

这是一个有限的数值，级数收敛。

而且，由于 $e^x$ 的泰勒级数在任何点都是绝对收敛的（可以用比值判别法验证），所以这个级数是**绝对收敛**的。

---

### 验证：用比值判别法

$$\lim_{n\to\infty} \left|\frac{a_{n+1}}{a_n}\right| = \lim_{n\to\infty} \left|\frac{(-e)^{n+1}}{(n+1)!} \cdot \frac{n!}{(-e)^n}\right| = \lim_{n\to\infty} \frac{e}{n+1} = 0$$

因为 $0 < 1$，由比值判别法，级数**绝对收敛**。

---

### 第 (b) 题答案

**绝对收敛（absolutely convergent）** ✅

级数的和为 $e^{-e}$。

---

---

## 总结

**第 (a) 题**：级数 $\sum \frac{(-1)^n \sqrt{n}}{\log n}$ 的通项绝对值 $\frac{\sqrt{n}}{\log n}$ 趋于无穷大，不趋于 0。根据通项判别法，级数**发散**。

**第 (b) 题**：级数 $\sum \frac{(-e)^n}{n!}$ 是 $e^{-e}$ 的泰勒展开。由于 $e^x$ 的泰勒级数对所有 $x$ 都绝对收敛，所以该级数**绝对收敛**。

---

## 本题涉及的核心术语

**absolutely convergent（绝对收敛）**：$\sum |a_n|$ 收敛。

**conditionally convergent（条件收敛）**：$\sum a_n$ 收敛，但 $\sum |a_n|$ 发散。

**divergent（发散）**：级数的极限不存在或趋于无穷。

**alternating series（交错级数）**：形如 $\sum (-1)^n a_n$ 的级数。

**nth term test（通项判别法）**：若 $\lim a_n \neq 0$，则 $\sum a_n$ 发散。

**Taylor series of $e^x$**：$e^x = \sum_{n=0}^{\infty} \frac{x^n}{n!}$，对所有 $x$ 收敛。

**ratio test（比值判别法）**：若 $\lim |\frac{a_{n+1}}{a_n}| = L < 1$，则绝对收敛。
