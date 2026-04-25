# B. 岩泽分解及其他

## B.1 群与子群

令 $SL_n$ 表示行列式为 $1$ 的矩阵集合。本附录的目的是用一般的术语来表述关于 $SL_n$ 的结果。我们将使用群论的语言。

设 $G$ 是一个集合，带有一个映射 $G \times G \to G$（写成乘法），将每对 $(x, y)$ 对应到一个元素 $xy \in G$，满足：

- **GR 1（结合律）。** 对所有 $x, y, z \in G$，$(xy)z = x(yz)$。
- **GR 2（单位元）。** 存在 $e \in G$，使得对所有 $x \in G$，$ex = xe = x$。
- **GR 3（逆元）。** 给定 $x \in G$，存在 $x^{-1} \in G$，使得 $xx^{-1} = x^{-1}x = e$。

元素 $e$ 由唯一确定，称为**单位元**。元素 $x^{-1}$ 也由唯一确定，称为 $x$ 的**逆**。一个带有这样映射的集合称为**群**。

**例。** $G = SL_n(\mathbb{R})$ 关于矩阵乘法构成一个群。类似地，$SL_n(\mathbb{C})$ 也是一个群。单位元是单位矩阵 $I$。子集 $\{I, -I\}$ 是一个子群。此外，$SL_n(\mathbb{R})$ 是 $GL_n(\mathbb{R})$（所有行列式非零的实矩阵）的子群。

**定义（子群）。** 设 $G$ 是一个群，$H$ 是包含单位元的子集，并且对取乘积和逆元封闭（即如果 $x, y \in H$，则 $x^{-1} \in H$ 且 $xy \in H$）。那么 $H$ 在同样的乘法下也是一个群，称为**子群**。

## B.2 岩泽分解

我们现在在群与子群的背景下表达格拉姆-施密特正交化过程。令 $G = SL_n(\mathbb{R})$，定义：

- $U$ = 对角线上为 $1$ 的上三角矩阵子群（**幂幺**）：
  $$
  u(x) = \begin{pmatrix} 1 & x_{12} & \cdots & x_{1n} \\ 0 & 1 & \cdots & x_{2n} \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & 1 \end{pmatrix}.
  $$
- $A$ = 正对角元素子群：
  $$
  a = \begin{pmatrix} a_1 & & & \\ & a_2 & & \\ & & \ddots & \\ & & & a_n \end{pmatrix}, \quad a_i > 0 \text{ 对所有 } i.
  $$
- $K$ = 实酉矩阵 $k$ 子群，满足 ${}^t k = k^{-1}$。

**定理 1（岩泽分解）。** 乘积映射 $U \times A \times K \to G$，$(u, a, k) \mapsto uak$ 是一个双射。

**证明。** 设 $e_1, \dots, e_n$ 是 $\mathbb{R}^n$ 的标准单位向量。令 $g = (g_{ij}) \in G$。则 $ge_i = g^{(i)} = \sum_{q=1}^n g_{qi}e_q$。存在一个上三角矩阵 $B = (b_{ij})$，当 $i > j$ 时 $b_{ij} = 0$，使得：

$$
\begin{aligned}
b_{11}g^{(1)} &= e'_1, \\
b_{12}g^{(1)} + b_{22}g^{(2)} &= e'_2, \\
&\vdots \\
b_{1j}g^{(1)} + \cdots + b_{jj}g^{(j)} &= e'_j, \\
&\vdots \\
b_{1n}g^{(1)} + \cdots + b_{nn}g^{(n)} &= e'_n,
\end{aligned}
$$

其中对角元素 $b_{11}, \dots, b_{nn} > 0$，且 $e'_1, \dots, e'_n$ 是两两正交的单位向量。得到 $B$ 不过是应用通常的格拉姆-施密特正交化过程。因此：

$$
e'_j = \sum_{i=1}^j b_{ij} g^{(i)} = \sum_{q=1}^n \sum_{i=1}^n g_{qi} b_{ij} e_q.
$$

令 $gB = k \in K$。则 $ke_i = e'_i$，所以 $k$ 将正交单位向量 $e_1, \dots, e_n$ 映射到正交单位向量 $e'_1, \dots, e'_n$。因此 $k$ 是酉的，且 $g = kB^{-1}$。于是 $g^{-1} = Bk^{-1}$，$B = au$，其中 $a$ 是对角矩阵，$a_i = b_{ii}$，$u$ 是幂幺的，$u = a^{-1}B$。这证明了满射 $G = UAK$。

对于唯一性，如果 $g = uak = u'a'k'$，令 $u_1 = u^{-1}u'$，则利用 $g^t g$ 得到 $a^2 u_1^{-1} = u_1 a'^2$。这些矩阵分别是下三角和上三角的，对角线为 $a^2, a'^2$，所以 $a = a'$，最终 $u_1 = I$，证明了唯一性。 ∎

$U$ 的元素称为**幂幺**的，因为它们形如 $u(X) = I + X$，其中 $X$ 是严格上三角的且 $X^{n+1} = 0$。于是 $X = u - I$ 称为**幂零**的。令：

$$
\exp Y = \sum_{j=0}^\infty \frac{Y^j}{j!} \quad \text{且} \quad \log(I+X) = \sum_{i=1}^\infty (-1)^{i+1} \frac{X^i}{i}.
$$

令 $\mathfrak{n}$ 表示所有严格上三角矩阵组成的空间。则 $\exp: \mathfrak{n} \to U$，$Y \mapsto \exp Y$ 是一个双射，其逆由对数级数给出，$Y = \log(I+X)$。由于幂零性，exp 和 log 级数实际上都是多项式，定义了 $U$ 和 $\mathfrak{n}$ 之间的互逆多项式映射。关系式 $\exp\log(I+X) = I+X$ 和 $\log\exp Y = Y$ 作为形式幂级数的恒等式成立。

## B.3 二维几何解释

令 $\mathfrak{h}_2$ 为虚部大于 $0$ 的复数 $z = x + iy$（$x, y \in \mathbb{R}$，$y > 0$）组成的上半平面。对 $g = \begin{pmatrix} a & b \\ c & d \end{pmatrix} \in G = SL_2(\mathbb{R})$，定义：

$$
g(z) = (az + b)(cz + d)^{-1}.
$$

则 $G$ 作用于 $\mathfrak{h}_2$，即对所有 $z$，$I(z) = z$，且 $g(g'(z)) = (gg')(z)$。此外，如果对所有 $z$ 都有 $g(z) = z$，则 $g = \pm I$。

为了看出 $z \in \mathfrak{h}_2$ 蕴含 $g(z) \in \mathfrak{h}_2$，验证变换公式：

$$
y(g(z)) = \frac{y(z)}{|cz + d|^2},
$$

可直接计算证明。

对 $w \in \mathfrak{h}_2$，令 $G_w$ 为满足 $g(w) = w$ 的元素 $g \in G$ 的子集。则 $G_w$ 是 $G$ 的子群，称为 $w$ 的**迷向群**。

**定理 2。** $i$ 的迷向群是 $K$，即 $K$ 是满足 $k(i) = i$ 的元素 $k \in G$ 的子群。这是矩阵群：

$$
\begin{pmatrix} \cos\theta & \sin\theta \\ -\sin\theta & \cos\theta \end{pmatrix}, \quad \text{或等价地 } a = d, \; c = -b, \; a^2 + b^2 = 1.
$$

对 $x \in \mathbb{R}$ 和 $a_1 > 0$，令 $u(x) = \begin{pmatrix} 1 & x \\ 0 & 1 \end{pmatrix}$，$a = \begin{pmatrix} a_1 & 0 \\ 0 & a_2 \end{pmatrix}$，其中 $a_2 = a_1^{-1}$。如果 $g = uak$，则 $u(x)(z) = z + x$，令 $y = a_1^2$，得 $a(i) = yi$，所以：

$$
g(i) = uak(i) = ua(i) = yi + x = x + iy.
$$

因此 $G$ 是传递作用的，并且我们用岩泽分解和上半平面坐标描述了该作用。

## B.4 三维几何解释

我们使用**四元数**，其元素为 $z = x_1 + x_2\mathbf{i} + x_3\mathbf{j} + x_4\mathbf{k}$，其中 $x_1, x_2, x_3, x_4 \in \mathbb{R}$，且 $\mathbf{i}^2 = \mathbf{j}^2 = \mathbf{k}^2 = -1$，$\mathbf{ij} = \mathbf{k}$，$\mathbf{jk} = \mathbf{i}$，$\mathbf{ki} = \mathbf{j}$。定义：

$$
\bar{z} = x_1 - x_2\mathbf{i} - x_3\mathbf{j} - x_4\mathbf{k}.
$$

则 $z\bar{z} = x_1^2 + x_2^2 + x_3^2 + x_4^2$，我们定义 $|z| = (z\bar{z})^{1/2}$。

令 $\mathfrak{h}_3$ 为上半空间，由 $\mathbf{k}$-分量为 $0$ 且 $x_3 > 0$ 的元素 $z$ 组成，故我们写成 $z = x_1 + x_2\mathbf{i} + y\mathbf{j}$，$y > 0$。令 $G = SL_2(\mathbb{C})$，于是 $G$ 的元素是矩阵 $g = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$，其中 $a, b, c, d \in \mathbb{C}$ 且 $ad - bc = 1$。

如同 $\mathfrak{h}_2$ 的情形，定义 $g(z) = (az + b)(cz + d)^{-1}$。可以验证如果 $z \in \mathfrak{h}_3$，则 $g(z) \in \mathfrak{h}_3$，且 $G$ 作用于 $\mathfrak{h}_3$。由于四元数不可交换，我们按所写的用商 $(az + b)(cz + d)^{-1}$。$y$-坐标变换公式为：

$$
y(g(z)) = \frac{y(z)}{|cz + d|^2}.
$$

群 $G = SL_2(\mathbb{C})$ 有岩泽分解 $G = UAK$，其中：
- $U$ = 元素 $u(x) = \begin{pmatrix} 1 & x \\ 0 & 1 \end{pmatrix}$ 组成的群，$x \in \mathbb{C}$；
- $A$ = 与之前相同的群（正对角）；
- $K$ = 元素 $k$ 的复酉群，满足 ${}^t\bar{k} = k^{-1}$。

**定理 3。** 迷向群 $G_{\mathbf{j}}$ 是 $K$。如果 $g = uak$，$u \in U$，$a \in A$，$k \in K$，$u = u(x)$ 且 $y = y(a)$，则 $g(\mathbf{j}) = x + y\mathbf{j}$。

因此 $G$ 是传递作用的，并且岩泽分解从这个群作用平凡地得出。

**由上述两条性质证明岩泽分解。** 令 $g \in G$ 且 $g(\mathbf{j}) = x + y\mathbf{j}$。令 $u = u(x)$，$a$ 满足 $y = a_1/a_2 = a_1^2$。令 $g' = ua$。则由第二个性质，$g(\mathbf{j}) = g'(\mathbf{j})$，所以 $\mathbf{j} = g^{-1}g'(\mathbf{j})$。由第一个性质，$g^{-1}g' = k$ 对某个 $k \in K$，所以 $g'k^{-1} = uak^{-1} = g$，证明完毕。 ∎

## B.5 共轭作用

一个群到另一个群的**同态** $f: G \to G'$ 是指满足 $f(e_G) = f(e_{G'})$ 且 $f(g_1g_2) = f(g_1)f(g_2)$（对所有 $g_1, g_2 \in G$）的映射。一个同态如果存在逆同态，则称为**同构**。一个群到自身的同构称为该群的**自同构**。$G$ 的自同构集合记为 $\operatorname{Aut}(G)$，在复合下构成一个群。

令 $X$ 是一个集合。双射 $\sigma: X \to X$ 称为**置换**。$X$ 的置换集合是一个群，记为 $\operatorname{Perm}(X)$。

群 $G$ 在 $X$ 上的**作用**是指一个映射 $G \times X \to X$，$(g, x) \mapsto gx$，满足 $ex = x$ 且 $g_1(g_2x) = (g_1g_2)x$。给定 $g \in G$，映射 $x \mapsto gx$ 是 $X$ 的一个置换，且 $g \mapsto \sigma(g)$ 是 $G$ 到 $\operatorname{Perm}(X)$ 的一个同态。

$G$ 在自身上的**共轭作用**定义为：对 $g, g' \in G$，$\mathbf{c}(g)g' = gg'g^{-1}$。映射 $g \mapsto \mathbf{c}(g)$ 是 $G$ 到 $\operatorname{Aut}(G)$ 的一个同态。

考虑 $G = SL_n(\mathbb{R})$。令：
- $\mathfrak{a}$ = 对角矩阵 $\operatorname{diag}(h_1, \dots, h_n)$ 组成的向量空间，迹为 $0$（$\sum h_i = 0$）；
- $\mathfrak{n}$ = 严格上三角矩阵 $(h_{ij})$ 组成的向量空间，$h_{ij} = 0$（若 $i \geq j$）；
- ${}^t\mathfrak{n}$ = 严格下对角矩阵组成的向量空间；
- $\mathfrak{g}$ = 迹为 $0$ 的 $n \times n$ 矩阵组成的向量空间。

则 $\mathfrak{g} = \mathfrak{a} \oplus \mathfrak{n} \oplus {}^t\mathfrak{n}$，且 $A$ 通过共轭作用。令 $E_{ij}$（$i < j$）为 $ij$-分量为 $1$、其余为 $0$ 的矩阵。则：

$$
\mathbf{c}(a)E_{ij} = (a_i/a_j)E_{ij} = a^{\alpha_{ij}}E_{ij},
$$

其中 $\alpha_{ij}$ 是 $A$ 到 $\mathbb{R}^+$（正实数乘法群）的一个同态。这样的同态集合称为**正则特征**集合，记为 $\mathscr{R}(\mathfrak{n})$。我们有：

$$
\mathfrak{n} = \bigoplus_{\alpha \in \mathscr{R}(\mathfrak{n})} \mathfrak{n}_\alpha,
$$

其中 $\mathfrak{n}_\alpha$ 是满足 $aXa^{-1} = a^\alpha X$ 的元素 $X \in \mathfrak{n}$ 的集合。类似地 ${}^t\mathfrak{n} = \bigoplus_\alpha ({}^t\mathfrak{n})_{-\alpha}$。

## B.6 Lie 代数与正则表示

**代数**是指一个带有到自身的双线性映射（称为乘积）的向量空间。我们通过定义 $X, Y \in \mathfrak{g}$ 的**Lie 积**为：

$$
[X, Y] = XY - YX.
$$

这个乘积是双线性的但不是结合的。我们称 $\mathfrak{g}$ 为 $G$ 的**Lie 代数**。令线性映射空间 $\mathscr{L}(\mathfrak{g}, \mathfrak{g})$ 记为 $\operatorname{End}(\mathfrak{g})$，其元素称为 $\mathfrak{g}$ 的**自同态**。$\mathfrak{g}$ 在自身上的**正则表示**是映射 $\mathfrak{g} \to \operatorname{End}(\mathfrak{g})$，将每个 $X \in \mathfrak{g}$ 对应到自同态 $L(X)$，使得：

$$
L(X)(Y) = [X, Y].
$$

注意 $X \mapsto L(X)$ 是一个线性映射。

> **练习。** 验证记 $L(X)$ 为 $D_X$，则对所有 $Y, Z \in \mathfrak{g}$ 有**导子性质**：
> $$
> D_X[Y, Z] = [D_X Y, Z] + [Y, D_X Z],
> $$
> 或用括号记号：$[X, [Y, Z]] = [[X, Y], Z] + [Y, [X, Z]]$。

我们也用 $\alpha$ 表示 $\mathfrak{a}$ 上由对角矩阵 $H = \operatorname{diag}(h_1, \dots, h_n)$ 通过 $\alpha_{ij}(H) = h_i - h_j$ 给出的特征。这是乘法特征的加法版本。于是每个 $\mathfrak{n}_\alpha$ 是加法特征的 $\alpha$-特征空间，即对 $H \in \mathfrak{a}$：

$$
[H, E_\alpha] = \alpha(H) E_\alpha.
$$

## B.7 极分解

令 $G = SL_n(\mathbb{C})$。令 $U = U(\mathbb{C})$ 为分量在 $\mathbb{C}$ 中的严格上三角矩阵集合。令 $D$ 为对角元素非零的对角复矩阵集合。令 $K$ 为 $SL_n(\mathbb{C})$ 中满足 ${}^t\bar{k} = k^{-1}$ 的元素 $k$ 的集合。则 $K$ 是一个子群，**复酉群**。

岩泽分解的证明在复数情形也成立，即 $G = UAK$，其中实数情形和复数情形的 $A$ 相同。

**二次映射。** 令 $g \in G$。定义 $g^* = {}^t\bar{g}$。则 $(g_1g_2)^* = g_2^*g_1^*$。元素 $g \in G$ 是**厄米特**的当且仅当 $g = g^*$。于是 $gg^*$ 是厄米特正定的，即对每个 $v \in \mathbb{C}^n$，$\langle gg^*v, v \rangle \geq 0$，且仅当 $v = 0$ 时 $= 0$。

我们用 $\operatorname{SPos}_n(\mathbb{C})$ 表示所有行列式为 $1$ 的厄米特正定 $n \times n$ 矩阵的集合。

**定理 4。** 令 $p \in \operatorname{SPos}_n(\mathbb{C})$。则 $p$ 在 $\operatorname{SPos}_n(\mathbb{C})$ 中有唯一的平方根。

**证明。** 见第八章，§5，练习 1。 ∎

令 $H$ 是 $G$ 的子群。$H$ 的一个（左）**陪集**是指形如 $gH$（$g \in G$）的 $G$ 的子集。两个陪集要么相等要么不交。我们用 $G/H$ 表示 $G$ 中 $H$ 的陪集集合。

**定理 5。** 二次映射 $g \mapsto gg^*$ 诱导双射 $G/K \to \operatorname{SPos}_n(\mathbb{C})$。

**证明。** 练习。分别证明单射和满射。 ∎

**定理 6。** 群 $G$ 有（非唯一的）分解：

$$
G = KAK.
$$

如果 $g \in G$ 写成乘积 $g = k_1bk_2$，$k_1, k_2 \in K$，$b \in A$，则 $b$ 在对角元素置换的意义下由唯一确定。

**证明。** 给定 $g \in G$，由第八章，定理 4.4，存在 $k_1 \in K$ 和 $b \in A$，使得 $gg^* = k_1b^2k_1^{-1}$。由定理 5 的双射，存在 $k_2 \in K$ 使得 $g = k_1bk_2$，证明了存在性。对于唯一性，$b^2$ 是 $gg^*$ 的特征值对角矩阵，即特征多项式的根，在置换意义下唯一确定。 ∎

注意还有另一种版本的**极分解**如下。

**定理 7。** 简记 $\operatorname{SPos}_n(\mathbb{C}) = P$。则 $G = PK$，且元素 $g = pk$（$p \in P$，$k \in K$）的分解是唯一的。

**证明。** 存在性是第八章，§5，练习 4 的重述。对于唯一性，假设 $g = pk$。二次映射给出 $gg^* = pp^* = p^2$。定理 4 中平方根的唯一性表明 $p$ 由 $g$ 唯一确定，从而 $k$ 也由唯一确定。 ∎
