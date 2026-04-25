[← Previous: A. Complex Numbers](a-complex-numbers.md)

# B. Iwasawa Decomposition and Others

## B.1 Groups and Subgroups

Let $SL_n$ denote the set of matrices with determinant $1$. The purpose of this appendix is to formulate in some general terms results about $SL_n$. We shall use the language of group theory.

Let $G$ be a set with a mapping $G \times G \to G$ (written as a product), associating to each pair $(x, y)$ an element $xy \in G$, satisfying:

- **GR 1 (Associativity).** $(xy)z = x(yz)$ for all $x, y, z \in G$.
- **GR 2 (Identity).** There exists $e \in G$ such that $ex = xe = x$ for all $x \in G$.
- **GR 3 (Inverse).** Given $x \in G$, there exists $x^{-1} \in G$ such that $xx^{-1} = x^{-1}x = e$.

The element $e$ is uniquely determined and called the **unit element**. The element $x^{-1}$ is also uniquely determined and called the **inverse** of $x$. A set together with such a mapping is called a **group**.

**Example.** $G = SL_n(\mathbb{R})$ with matrix multiplication is a group. Similarly $SL_n(\mathbb{C})$ is a group. The unit element is the unit matrix $I$. The subset $\{I, -I\}$ is a subgroup. Also $SL_n(\mathbb{R})$ is a subgroup of $GL_n(\mathbb{R})$ (all real matrices with non-zero determinant).

**Definition (Subgroup).** Let $G$ be a group and let $H$ be a subset which contains the unit element, and is closed under taking products and inverses (i.e. if $x, y \in H$ then $x^{-1} \in H$ and $xy \in H$). Then $H$ is a group under the same product and is called a **subgroup**.

## B.2 Iwasawa Decomposition

We now express the Gram-Schmidt orthogonalization in the context of groups and subgroups. Let $G = SL_n(\mathbb{R})$ and define:

- $U$ = subgroup of upper triangular matrices with $1$'s on the diagonal (**unipotent**):
  $$
  u(x) = \begin{pmatrix} 1 & x_{12} & \cdots & x_{1n} \\ 0 & 1 & \cdots & x_{2n} \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & 1 \end{pmatrix}.
  $$
- $A$ = subgroup of positive diagonal elements:
  $$
  a = \begin{pmatrix} a_1 & & & \\ & a_2 & & \\ & & \ddots & \\ & & & a_n \end{pmatrix}, \quad a_i > 0 \text{ for all } i.
  $$
- $K$ = subgroup of real unitary matrices $k$, satisfying ${}^t k = k^{-1}$.

**Theorem 1 (Iwasawa decomposition).** The product map $U \times A \times K \to G$ given by $(u, a, k) \mapsto uak$ is a bijection.

**Proof.** Let $e_1, \dots, e_n$ be the standard unit vectors of $\mathbb{R}^n$. Let $g = (g_{ij}) \in G$. Then $ge_i = g^{(i)} = \sum_{q=1}^n g_{qi}e_q$. There exists an upper triangular matrix $B = (b_{ij})$ with $b_{ij} = 0$ if $i > j$, such that:

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

where the diagonal elements $b_{11}, \dots, b_{nn} > 0$, and $e'_1, \dots, e'_n$ are mutually perpendicular unit vectors. Obtaining $B$ is merely applying the usual Gram-Schmidt orthogonalization process. Thus:

$$
e'_j = \sum_{i=1}^j b_{ij} g^{(i)} = \sum_{q=1}^n \sum_{i=1}^n g_{qi} b_{ij} e_q.
$$

Let $gB = k \in K$. Then $ke_i = e'_i$, so $k$ maps the orthogonal unit vectors $e_1, \dots, e_n$ to the orthogonal unit vectors $e'_1, \dots, e'_n$. Therefore $k$ is unitary, and $g = kB^{-1}$. Then $g^{-1} = Bk^{-1}$ and $B = au$ where $a$ is the diagonal matrix with $a_i = b_{ii}$ and $u$ is unipotent, $u = a^{-1}B$. This proves the surjection $G = UAK$.

For uniqueness, if $g = uak = u'a'k'$, let $u_1 = u^{-1}u'$, so using $g^t g$ one gets $a^2 u_1^{-1} = u_1 a'^2$. These matrices are lower and upper triangular respectively, with diagonals $a^2, a'^2$, so $a = a'$, and finally $u_1 = I$, proving uniqueness. ∎

The elements of $U$ are called **unipotent** because they are of the form $u(X) = I + X$, where $X$ is strictly upper triangular and $X^{n+1} = 0$. Thus $X = u - I$ is called **nilpotent**. Let:

$$
\exp Y = \sum_{j=0}^\infty \frac{Y^j}{j!} \quad \text{and} \quad \log(I+X) = \sum_{i=1}^\infty (-1)^{i+1} \frac{X^i}{i}.
$$

Let $\mathfrak{n}$ denote the space of all strictly upper triangular matrices. Then $\exp: \mathfrak{n} \to U$, $Y \mapsto \exp Y$ is a bijection, whose inverse is given by the log series, $Y = \log(I+X)$. Because of nilpotency, the exp and log series are actually polynomials, defining inverse polynomial mappings between $U$ and $\mathfrak{n}$. The relations $\exp\log(I+X) = I+X$ and $\log\exp Y = Y$ hold as identities of formal power series.

## B.3 Geometric Interpretation in Dimension 2

Let $\mathfrak{h}_2$ be the upper half plane of complex numbers $z = x + iy$ with $x, y \in \mathbb{R}$ and $y > 0$. For $g = \begin{pmatrix} a & b \\ c & d \end{pmatrix} \in G = SL_2(\mathbb{R})$, define:

$$
g(z) = (az + b)(cz + d)^{-1}.
$$

Then $G$ acts on $\mathfrak{h}_2$, meaning that $I(z) = z$ for all $z$, and $g(g'(z)) = (gg')(z)$. Also, if $g(z) = z$ for all $z$, then $g = \pm I$.

To see that $z \in \mathfrak{h}_2$ implies $g(z) \in \mathfrak{h}_2$, check the transformation formula:

$$
y(g(z)) = \frac{y(z)}{|cz + d|^2},
$$

proved by direct computation.

For $w \in \mathfrak{h}_2$, let $G_w$ be the subset of elements $g \in G$ such that $g(w) = w$. Then $G_w$ is a subgroup of $G$, called the **isotropy group** of $w$.

**Theorem 2.** The isotropy group of $i$ is $K$, i.e. $K$ is the subgroup of elements $k \in G$ such that $k(i) = i$. This is the group of matrices:

$$
\begin{pmatrix} \cos\theta & \sin\theta \\ -\sin\theta & \cos\theta \end{pmatrix}, \quad \text{or equivalently } a = d, \; c = -b, \; a^2 + b^2 = 1.
$$

For $x \in \mathbb{R}$ and $a_1 > 0$, let $u(x) = \begin{pmatrix} 1 & x \\ 0 & 1 \end{pmatrix}$ and $a = \begin{pmatrix} a_1 & 0 \\ 0 & a_2 \end{pmatrix}$ with $a_2 = a_1^{-1}$. If $g = uak$, then $u(x)(z) = z + x$, and putting $y = a_1^2$, we get $a(i) = yi$, so:

$$
g(i) = uak(i) = ua(i) = yi + x = x + iy.
$$

Thus $G$ acts transitively, and we have a description of the action in terms of the Iwasawa decomposition and the coordinates of the upper half plane.

## B.4 Geometric Interpretation in Dimension 3

We use the **quaternions**, whose elements are $z = x_1 + x_2\mathbf{i} + x_3\mathbf{j} + x_4\mathbf{k}$ with $x_1, x_2, x_3, x_4 \in \mathbb{R}$, and $\mathbf{i}^2 = \mathbf{j}^2 = \mathbf{k}^2 = -1$, $\mathbf{ij} = \mathbf{k}$, $\mathbf{jk} = \mathbf{i}$, $\mathbf{ki} = \mathbf{j}$. Define:

$$
\bar{z} = x_1 - x_2\mathbf{i} - x_3\mathbf{j} - x_4\mathbf{k}.
$$

Then $z\bar{z} = x_1^2 + x_2^2 + x_3^2 + x_4^2$, and we define $|z| = (z\bar{z})^{1/2}$.

Let $\mathfrak{h}_3$ be the upper half space consisting of elements $z$ whose $\mathbf{k}$-component is $0$, and $x_3 > 0$, so we write $z = x_1 + x_2\mathbf{i} + y\mathbf{j}$ with $y > 0$. Let $G = SL_2(\mathbb{C})$, so elements of $G$ are matrices $g = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$ with $a, b, c, d \in \mathbb{C}$ and $ad - bc = 1$.

As in the case of $\mathfrak{h}_2$, define $g(z) = (az + b)(cz + d)^{-1}$. One verifies that if $z \in \mathfrak{h}_3$ then $g(z) \in \mathfrak{h}_3$, and $G$ acts on $\mathfrak{h}_3$. Since the quaternions are not commutative, we use the quotient as written $(az + b)(cz + d)^{-1}$. The $y$-coordinate transformation formula reads:

$$
y(g(z)) = \frac{y(z)}{|cz + d|^2}.
$$

The group $G = SL_2(\mathbb{C})$ has the Iwasawa decomposition $G = UAK$, where:
- $U$ = group of elements $u(x) = \begin{pmatrix} 1 & x \\ 0 & 1 \end{pmatrix}$ with $x \in \mathbb{C}$;
- $A$ = same group as before (positive diagonal);
- $K$ = complex unitary group of elements $k$ such that ${}^t\bar{k} = k^{-1}$.

**Theorem 3.** The isotropy group $G_{\mathbf{j}}$ is $K$. If $g = uak$ with $u \in U$, $a \in A$, $k \in K$, $u = u(x)$ and $y = y(a)$, then $g(\mathbf{j}) = x + y\mathbf{j}$.

Thus $G$ acts transitively, and the Iwasawa decomposition follows trivially from this group action.

**Proof of the Iwasawa decomposition from the above two properties.** Let $g \in G$ and $g(\mathbf{j}) = x + y\mathbf{j}$. Let $u = u(x)$ and $a$ be such that $y = a_1/a_2 = a_1^2$. Let $g' = ua$. Then by the second property, $g(\mathbf{j}) = g'(\mathbf{j})$, so $\mathbf{j} = g^{-1}g'(\mathbf{j})$. By the first property, $g^{-1}g' = k$ for some $k \in K$, so $g'k^{-1} = uak^{-1} = g$, concluding the proof. ∎

## B.5 The Conjugation Action

By a **homomorphism** $f: G \to G'$ of a group into another we mean a mapping satisfying $f(e_G) = f(e_{G'})$ and $f(g_1g_2) = f(g_1)f(g_2)$ for all $g_1, g_2 \in G$. A homomorphism is called an **isomorphism** if it has an inverse homomorphism. An isomorphism of $G$ with itself is called an **automorphism** of $G$. The set of automorphisms of $G$, denoted by $\operatorname{Aut}(G)$, is a group under composition.

Let $X$ be a set. A bijective map $\sigma: X \to X$ is called a **permutation**. The set of permutations of $X$ is a group, denoted by $\operatorname{Perm}(X)$.

By an **action** of a group $G$ on $X$ we mean a map $G \times X \to X$, $(g, x) \mapsto gx$, satisfying $ex = x$ and $g_1(g_2x) = (g_1g_2)x$. Given $g \in G$, the map $x \mapsto gx$ is a permutation of $X$, and $g \mapsto \sigma(g)$ is a homomorphism of $G$ into $\operatorname{Perm}(X)$.

The **conjugation action** of $G$ on itself is defined for $g, g' \in G$ by $\mathbf{c}(g)g' = gg'g^{-1}$. The map $g \mapsto \mathbf{c}(g)$ is a homomorphism of $G$ into $\operatorname{Aut}(G)$.

Consider $G = SL_n(\mathbb{R})$. Let:
- $\mathfrak{a}$ = vector space of diagonal matrices $\operatorname{diag}(h_1, \dots, h_n)$ with trace $0$ ($\sum h_i = 0$);
- $\mathfrak{n}$ = vector space of strictly upper triangular matrices $(h_{ij})$ with $h_{ij} = 0$ if $i \geq j$;
- ${}^t\mathfrak{n}$ = vector space of strictly lower diagonal matrices;
- $\mathfrak{g}$ = vector space of $n \times n$ matrices of trace $0$.

Then $\mathfrak{g} = \mathfrak{a} \oplus \mathfrak{n} \oplus {}^t\mathfrak{n}$, and $A$ acts by conjugation. Let $E_{ij}$ ($i < j$) be the matrix with $ij$-component $1$ and all others $0$. Then:

$$
\mathbf{c}(a)E_{ij} = (a_i/a_j)E_{ij} = a^{\alpha_{ij}}E_{ij},
$$

where $\alpha_{ij}$ is a homomorphism of $A$ into $\mathbb{R}^+$ (positive real multiplicative group). The set of such homomorphisms is called the set of **regular characters**, denoted by $\mathscr{R}(\mathfrak{n})$. We have:

$$
\mathfrak{n} = \bigoplus_{\alpha \in \mathscr{R}(\mathfrak{n})} \mathfrak{n}_\alpha,
$$

where $\mathfrak{n}_\alpha$ is the set of elements $X \in \mathfrak{n}$ such that $aXa^{-1} = a^\alpha X$. Similarly ${}^t\mathfrak{n} = \bigoplus_\alpha ({}^t\mathfrak{n})_{-\alpha}$.

## B.6 Lie Algebra and Regular Representation

By an **algebra** we mean a vector space with a bilinear map into itself, called a product. We make $\mathfrak{g}$ into an algebra by defining the **Lie product** of $X, Y \in \mathfrak{g}$ to be:

$$
[X, Y] = XY - YX.
$$

This product is bilinear but not associative. We call $\mathfrak{g}$ the **Lie algebra** of $G$. Let the space of linear maps $\mathscr{L}(\mathfrak{g}, \mathfrak{g})$ be denoted by $\operatorname{End}(\mathfrak{g})$, whose elements are called **endomorphisms** of $\mathfrak{g}$. The **regular representation** of $\mathfrak{g}$ on itself is the map $\mathfrak{g} \to \operatorname{End}(\mathfrak{g})$ which to each $X \in \mathfrak{g}$ associates the endomorphism $L(X)$ such that:

$$
L(X)(Y) = [X, Y].
$$

Note that $X \mapsto L(X)$ is a linear map.

> **Exercise.** Verify that denoting $L(X)$ by $D_X$, we have the **derivation property** for all $Y, Z \in \mathfrak{g}$:
> $$
> D_X[Y, Z] = [D_X Y, Z] + [Y, D_X Z],
> $$
> or in bracket notation: $[X, [Y, Z]] = [[X, Y], Z] + [Y, [X, Z]]$.

We use $\alpha$ also to denote the character on $\mathfrak{a}$ given on a diagonal matrix $H = \operatorname{diag}(h_1, \dots, h_n)$ by $\alpha_{ij}(H) = h_i - h_j$. This is the additive version of the multiplicative character. Then each $\mathfrak{n}_\alpha$ is the $\alpha$-eigenspace for the additive character, namely for $H \in \mathfrak{a}$:

$$
[H, E_\alpha] = \alpha(H) E_\alpha.
$$

## B.7 Polar Decompositions

Let $G = SL_n(\mathbb{C})$. Let $U = U(\mathbb{C})$ be the set of strictly upper triangular matrices with components in $\mathbb{C}$. Let $D$ be the set of diagonal complex matrices with non-zero diagonal elements. Let $K$ be the set of elements $k \in SL_n(\mathbb{C})$ such that ${}^t\bar{k} = k^{-1}$. Then $K$ is a subgroup, the **complex unitary group**.

The proof of the Iwasawa decomposition works in the complex case, that is $G = UAK$, with the same $A$ in the real and complex cases.

**The quadratic map.** Let $g \in G$. Define $g^* = {}^t\bar{g}$. Then $(g_1g_2)^* = g_2^*g_1^*$. An element $g \in G$ is **hermitian** if and only if $g = g^*$. Then $gg^*$ is hermitian positive definite, i.e. for every $v \in \mathbb{C}^n$, $\langle gg^*v, v \rangle \geq 0$, and $= 0$ only if $v = 0$.

We denote by $\operatorname{SPos}_n(\mathbb{C})$ the set of all hermitian positive definite $n \times n$ matrices with determinant $1$.

**Theorem 4.** Let $p \in \operatorname{SPos}_n(\mathbb{C})$. Then $p$ has a unique square root in $\operatorname{SPos}_n(\mathbb{C})$.

**Proof.** See Chapter VIII, §5, Exercise 1. ∎

Let $H$ be a subgroup of $G$. By a (left) **coset** of $H$, we mean a subset of $G$ of the form $gH$ with some $g \in G$. Two cosets are either equal or disjoint. By $G/H$ we mean the set of cosets of $H$ in $G$.

**Theorem 5.** The quadratic map $g \mapsto gg^*$ induces a bijection $G/K \to \operatorname{SPos}_n(\mathbb{C})$.

**Proof.** Exercise. Show injectivity and surjectivity separately. ∎

**Theorem 6.** The group $G$ has the decomposition (non-unique):

$$
G = KAK.
$$

If $g \in G$ is written as a product $g = k_1bk_2$ with $k_1, k_2 \in K$ and $b \in A$, then $b$ is uniquely determined up to a permutation of the diagonal elements.

**Proof.** Given $g \in G$, by Chapter VIII, Theorem 4.4, there exists $k_1 \in K$ and $b \in A$ such that $gg^* = k_1b^2k_1^{-1}$. By the bijection of Theorem 5, there exists $k_2 \in K$ such that $g = k_1bk_2$, proving existence. For uniqueness, $b^2$ is the diagonal matrix of eigenvalues of $gg^*$, i.e. the roots of the characteristic polynomial, uniquely determined up to a permutation. ∎

Note that there is another version of the **polar decomposition** as follows.

**Theorem 7.** Abbreviate $\operatorname{SPos}_n(\mathbb{C}) = P$. Then $G = PK$, and the decomposition of an element $g = pk$ with $p \in P$, $k \in K$ is unique.

**Proof.** The existence is a rephrasing of Chapter VIII, §5, Exercise 4. For uniqueness, suppose $g = pk$. The quadratic map gives $gg^* = pp^* = p^2$. The uniqueness of the square root in Theorem 4 shows that $p$ is uniquely determined by $g$, whence so is $k$. ∎

[← Previous: A. Complex Numbers](a-complex-numbers.md)
