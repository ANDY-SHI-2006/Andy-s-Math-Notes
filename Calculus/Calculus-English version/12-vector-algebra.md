[<- Previous: 11. Sequences and Series of Functions](11-sequences-and-series-of-functions.md) | [Next: 13. Applications of Vector Algebra to Analytic Geometry ->](13-applications-of-vector-algebra-to-analytic-geometry.md)

# 12. Vector Algebra

## 12.1 Historical Introduction

### 12.1.1 Origins

Vector algebra emerged from the need for analytic tools in mechanics and geometry:
- **Lagrange (1788):** Published *Mécanique analytique*, demonstrating the power of analytical methods in mechanics.
- **Hamilton (1805–1865):** Introduced **quaternions**, a new algebraic system that unified algebra and physics.
- **Gibbs (1839–1903) and Heaviside (1850–1925):** Extracted the vector concept from quaternion analysis, creating the subject of **vector algebra**.

### 12.1.2 Three Approaches to Vector Algebra

1. **Geometric:** Vectors are represented by directed line segments (arrows). Operations are defined and studied by geometric methods.
2. **Analytic:** Vectors and operations are described entirely in terms of **numbers** (components). Properties are deduced from properties of numbers.
3. **Axiomatic:** Vectors and operations are **undefined concepts** satisfying a set of axioms. This algebraic system is called a **linear space** or **linear vector space** (studied in detail in Chapter 15).

> The analytic approach is adopted here; geometric pictures are used for motivation when possible.

## 12.2 The Vector Space of $n$-Tuples of Real Numbers

### 12.2.1 Definition

An ordered $n$-tuple of real numbers
$$
A=(a_1,a_2,\dots,a_n)
$$
is called an **$n$-dimensional vector** (or $n$-dimensional point). The numbers $a_i$ are its **coordinates** or **components**. The collection of all such vectors is the **vector space of $n$-tuples**, denoted $V_n$.

> Notation: vectors by capital letters $A,B,C,\dots$; components by corresponding small letters $a,b,c,\dots$.

### 12.2.2 Equality, Addition, and Scalar Multiplication

- **Equality:** $A=B$ means $a_i=b_i$ for all $i=1,\dots,n$.
- **Addition:** $A+B=(a_1+b_1,a_2+b_2,\dots,a_n+b_n)$.
- **Scalar multiplication:** $cA=(ca_1,ca_2,\dots,ca_n)$.

### 12.2.3 Algebraic Properties

**Theorem 12.1.** For all vectors in $V_n$ and all scalars:
- **Commutativity:** $A+B=B+A$
- **Associativity:** $A+(B+C)=(A+B)+C$
- **Scalar associativity:** $c(dA)=(cd)A$
- **Distributive laws:** $c(A+B)=cA+cB$ and $(c+d)A=cA+dA$

### 12.2.4 Zero Vector, Negative, and Subtraction

- **Zero vector** $O=(0,0,\dots,0)$: satisfies $A+O=A$ for every $A$.
- **Negative:** $-A=(-1)A=(-a_1,-a_2,\dots,-a_n)$.
- **Subtraction:** $A-B=A+(-B)$; note $(A+B)-B=A$.
- $0A=O$ and $1A=A$.

### 12.2.5 Complex Numbers and Two-Dimensional Vectors

Complex numbers and vectors in $V_2$ are defined as ordered pairs of real numbers and are added in exactly the same way. They differ only when **multiplication** is introduced:
- Complex-number multiplication gives the field properties.
- For $n>2$ it is impossible to introduce multiplication in $V_n$ satisfying all field properties (only $n=1,2$ are possible).

Special products that do **not** satisfy all field properties:
- **Dot product** (Section 12.5): defined in any $V_n$; result is a **scalar**.
- **Cross product** (Section 13.9): defined only in $V_3$; result is a **vector**, but it is not commutative.

## 12.3 Geometric Interpretation for $n\le 3$

### 12.3.1 Geometric Vectors

A pair of points $A$ and $B$ defines a **geometric vector** $\overrightarrow{AB}$: an arrow from the **initial point** $A$ to the **terminal point** (tip) $B$.

Geometric vectors are especially convenient for physical quantities possessing both **magnitude** and **direction** (force, displacement, velocity, acceleration). The length of the arrow measures the magnitude; the arrowhead indicates the direction.

### 12.3.2 Equivalent Vectors

Two geometric vectors $\overrightarrow{AB}$ and $\overrightarrow{CD}$ are called **equivalent** whenever
$$
B-A=D-C.
$$
Equivalently, in components: $b_1-a_1=d_1-c_1$ and $b_2-a_2=d_2-c_2$.

> Equivalent arrows have equal lengths, are parallel, and point in the same direction. The four points $A,B,C,D$ are vertices of a parallelogram.

### 12.3.3 Parallelogram Law of Addition

In a parallelogram, opposite vertices have the same sum: $A+D=B+C$. If $A=O$ (the origin), the geometric vector from $O$ to $D$ corresponds to the vector sum $D=B+C$.

> **Vector addition corresponds geometrically to the parallelogram law.** Many physical quantities combine in exactly this way.

For simplicity we write $A$ for the geometric vector $\overrightarrow{OA}$; any geometric vector equivalent to $\overrightarrow{OA}$ is also denoted by $A$.

### 12.3.4 Subtraction and Scalar Multiplication

- **Subtraction:** $B-A$ is the vector from $A$ to $B$.
- **Scalar multiplication:** If $B=cA$, the geometric vector $B$ has length $|c|$ times the length of $A$; it points in the same direction if $c>0$ and in the opposite direction if $c<0$.

### 12.3.5 Parallelism in $V_n$

**Definition.** Two vectors $A$ and $B$ in $V_n$:
- have the **same direction** if $B=cA$ for some $c>0$;
- have the **opposite direction** if $B=cA$ for some $c<0$;
- are **parallel** if $B=cA$ for some $c\neq 0$.

> The zero vector is parallel only to itself and is the only vector having the opposite direction to itself.

## 12.4 The Dot Product

### 12.4.1 Definition

If $A=(a_1,\dots,a_n)$ and $B=(b_1,\dots,b_n)$ are vectors in $V_n$, their **dot product** (or **scalar product**) is
$$
A\cdot B=\sum_{k=1}^{n}a_k b_k.
$$

### 12.4.2 Algebraic Properties

**Theorem 12.2.** For all vectors $A,B,C$ in $V_n$ and all scalars $c$:
- **(a)** $A\cdot B=B\cdot A$ (commutative law)
- **(b)** $A\cdot(B+C)=A\cdot B+A\cdot C$ (distributive law)
- **(c)** $c(A\cdot B)=(cA)\cdot B=A\cdot(cB)$ (homogeneity)
- **(d)** $A\cdot A>0$ if $A\neq O$ (positivity)
- **(e)** $A\cdot A=0$ if $A=O$

### 12.4.3 The Cauchy–Schwarz Inequality

**Theorem 12.3.** For any vectors $A,B$ in $V_n$,
$$
\boxed{(A\cdot B)^2\le(A\cdot A)(B\cdot B)}
$$
Moreover, equality holds **if and only if** one vector is a scalar multiple of the other.

**Coordinate-free proof.** If either vector is $O$ the result is trivial. Assume both are nonzero and set
$$
C=xA-yB, \qquad\text{where }x=B\cdot B,\; y=A\cdot B.
$$
By positivity, $C\cdot C\ge 0$. Expanding with properties (a)–(c):
$$
C\cdot C=x^2(A\cdot A)-2xy(A\cdot B)+y^2(B\cdot B)
=(B\cdot B)^2(A\cdot A)-2(A\cdot B)^2(B\cdot B)+(A\cdot B)^2(B\cdot B)\ge 0.
$$
Dividing by $B\cdot B>0$ yields $(B\cdot B)(A\cdot A)-(A\cdot B)^2\ge 0$, which is the desired inequality. Equality occurs iff $C=O$, i.e. $xA=yB$, meaning $A$ and $B$ are scalar multiples.

> The Cauchy–Schwarz inequality is fundamental for defining the **length** (norm) of a vector.

## 12.5 Length or Norm of a Vector

### 12.5.1 Definition

In $V_2$ and $V_3$ the length of a geometric vector follows from the theorem of Pythagoras:
$$
\text{length of }A=\sqrt{a_1^2+a_2^2}\;(V_2), \qquad
\text{length of }A=\sqrt{a_1^2+a_2^2+a_3^2}\;(V_3).
$$
This motivates the definition in $V_n$:
$$
\boxed{\|A\|=(A\cdot A)^{1/2}=\Bigl(\sum_{k=1}^{n}a_k^2\Bigr)^{1/2}}.
$$
The quantity $\|A\|$ is called the **norm** (or **length**) of $A$.

### 12.5.2 Properties of the Norm

**Theorem 12.4.** For every vector $A$ in $V_n$ and every scalar $c$:
- **(a)** $\|A\|>0$ if $A\neq O$ (positivity)
- **(b)** $\|A\|=0$ if $A=O$
- **(c)** $\|cA\|=|c|\,\|A\|$ (homogeneity)

### 12.5.3 Cauchy–Schwarz in Norm Form

The Cauchy–Schwarz inequality can be rewritten as
$$
(A\cdot B)^2\le\|A\|^2\|B\|^2 \qquad\text{or}\qquad |A\cdot B|\le\|A\|\,\|B\|.
$$

### 12.5.4 The Triangle Inequality

**Theorem 12.5.** For any vectors $A,B$ in $V_n$,
$$
\boxed{\|A+B\|\le\|A\|+\|B\|}.
$$
Equality holds **if and only if** $A=O$, or $B=O$, or $B=cA$ for some $c>0$.

**Proof.** Squaring both sides gives the equivalent inequality
$$
\|A+B\|^2\le(\|A\|+\|B\|)^2.
$$
The left side expands to $\|A\|^2+2A\cdot B+\|B\|^2$; the right side is $\|A\|^2+2\|A\|\,\|B\|+\|B\|^2$. Thus the inequality reduces to $A\cdot B\le\|A\|\,\|B\|$, which follows from $|A\cdot B|\le\|A\|\,\|B\|$.

> Conversely, the triangle inequality also implies Cauchy–Schwarz.

## 12.6 Orthogonality of Vectors

### 12.6.1 The Polarization Identity

From the proof of the triangle inequality we obtain the useful identity
$$
\|A+B\|^2=\|A\|^2+\|B\|^2+2A\cdot B,
$$
valid for any two vectors in $V_n$.

### 12.6.2 Definition of Orthogonality

In the plane, two perpendicular geometric vectors satisfy the Pythagorean theorem
$$
\|A+B\|^2=\|A\|^2+\|B\|^2.
$$
Comparing with the polarization identity gives $A\cdot B=0$.

**Definition.** Two vectors $A$ and $B$ in $V_n$ are called **perpendicular** or **orthogonal** if
$$
A\cdot B=0.
$$

### 12.6.3 The Pythagorean Identity in $V_n$

**Theorem.** Two vectors $A$ and $B$ in $V_n$ are orthogonal if and only if
$$
\|A+B\|^2=\|A\|^2+\|B\|^2.
$$
This is called the **Pythagorean identity** in $V_n$.

> Orthogonality is the natural generalization of perpendicularity to arbitrary dimension.

## 12.7 Projections and Angle Between Vectors

### 12.7.1 Projection of a Vector

Any vector $A$ can be decomposed as $A=tB+C$ where $C$ is orthogonal to $B$. The vector $tB$ is called the **projection of $A$ along $B$**.

Taking the dot product with $B$ and using $C\cdot B=0$:
$$
t=\frac{A\cdot B}{B\cdot B}=\frac{A\cdot B}{\|B\|^2}.
$$

### 12.7.2 Geometric Meaning of the Dot Product

From the right-triangle interpretation (Figure 12.11),
$$
\cos\theta=\frac{\|tB\|}{\|A\|}=\frac{t\,\|B\|}{\|A\|}=\frac{A\cdot B}{\|A\|\,\|B\|}.
$$
Hence
$$
\boxed{A\cdot B=\|A\|\,\|B\|\cos\theta}.
$$
The dot product equals the product of the lengths times the cosine of the included angle.

### 12.7.3 Angle in $V_n$

By Cauchy–Schwarz,
$$
-1\le\frac{A\cdot B}{\|A\|\,\|B\|}\le 1
$$
for any nonzero vectors. Therefore there is a unique $\theta\in[0,\pi]$ satisfying the formula above.

**Definition.** The **angle** $\theta$ between nonzero vectors $A$ and $B$ in $V_n$ is
$$
\theta=\arccos\frac{A\cdot B}{\|A\|\,\|B\|}.
$$
In particular, $\theta=\pi/2$ when $A\cdot B=0$ (orthogonal vectors).

## 12.8 The Unit Coordinate Vectors

### 12.8.1 Definition

In $V_n$ the **unit coordinate vectors** are
$$
E_1=(1,0,\dots,0),\; E_2=(0,1,0,\dots,0),\;\dots,\; E_n=(0,\dots,0,1).
$$
Each has length $1$, and distinct ones are orthogonal:
$$
E_k\cdot E_j=0 \quad (k\neq j).
$$

### 12.8.2 Standard Basis Representation

**Theorem 12.6.** Every vector $X=(x_1,\dots,x_n)$ in $V_n$ can be expressed **uniquely** as
$$
X=\sum_{k=1}^{n}x_k E_k.
$$

> **Proof.** Immediate from the definitions of addition and scalar multiplication; uniqueness follows from equality of components.

A sum $\sum c_i A_i$ is called a **linear combination** of $A_1,\dots,A_n$. Theorem 12.6 says the unit coordinate vectors **span** $V_n$ (and do so uniquely).

### 12.8.3 Notation in Low Dimensions

- In $V_2$: $E_1, E_2$ are often denoted $\boldsymbol{i}, \boldsymbol{j}$.
- In $V_3$: $E_1, E_2, E_3$ are often denoted $\boldsymbol{i}, \boldsymbol{j}, \boldsymbol{k}$.

Any vector in $V_3$ is then written $A=a_1\boldsymbol{i}+a_2\boldsymbol{j}+a_3\boldsymbol{k}$.

### 12.8.4 Algebraic Manipulations

When vectors are expressed as linear combinations of the unit coordinate vectors, operations follow the usual rules of algebra. For example,
$$
A+B=\sum_{k=1}^{n}a_k E_k+\sum_{k=1}^{n}b_k E_k=\sum_{k=1}^{n}(a_k+b_k)E_k,
$$
and the coefficient of $E_k$ is precisely the $k$th component of $A+B$.

## 12.9 The Linear Span of a Finite Set of Vectors

### 12.9.1 Definition

Let $S=\{A_1,\dots,A_k\}$ be a nonempty set of vectors in $V_n$. If a vector $X$ can be written as
$$
X=\sum_{i=1}^{k}c_i A_i,
$$
then $S$ is said to **span** $X$. The set of all vectors spanned by $S$ is called the **linear span** of $S$, denoted $L(S)$.

In other words, $L(S)$ is the set of all possible linear combinations of vectors in $S$. We say $S$ **spans the whole space** $V_n$ if $L(S)=V_n$.

### 12.9.2 Unique Spanning

**Definition.** $S$ spans $X$ **uniquely** if
$$
X=\sum_{i=1}^{k}c_i A_i=\sum_{i=1}^{k}d_i A_i \quad\Longrightarrow\quad c_i=d_i\text{ for all }i.
$$

**Theorem 12.7.** $S$ spans every vector in $L(S)$ uniquely **if and only if** $S$ spans the zero vector uniquely.

**Proof sketch.** If $S$ spans $O$ uniquely and $X$ has two representations, subtracting gives a representation of $O$; uniqueness for $O$ forces the coefficients to coincide.

## 12.10 Linear Independence

### 12.10.1 Definition

**Definition.** A set $S=\{A_1,\dots,A_k\}$ is **linearly independent** if it spans the zero vector uniquely. Otherwise $S$ is **linearly dependent**.

Equivalently:
- **Independent:** $\displaystyle\sum_{i=1}^{k}c_i A_i=O$ implies all $c_i=0$.
- **Dependent:** there exist scalars $c_1,\dots,c_k$, not all zero, with $\displaystyle\sum_{i=1}^{k}c_i A_i=O$.

> The empty set is agreed to be linearly independent.

### 12.10.2 Examples

1. A subset of an independent set is independent; a superset of a dependent set is dependent.
2. The unit coordinate vectors $E_1,\dots,E_n$ are linearly independent.
3. Any set containing the zero vector is dependent.
4. In $V_2$, $\{i,j,i+j\}$ is dependent, while $\{i,j\}$ is independent.

### 12.10.3 A Key Theorem on Dimension

**Theorem 12.8.** Let $S=\{A_1,\dots,A_k\}$ be linearly independent and let $L(S)$ be its linear span. Then every set of $k+1$ vectors in $L(S)$ is linearly dependent.

> This is the fundamental theorem that underlies the notion of dimension: a $k$-dimensional space cannot contain $k+1$ independent vectors.

**Proof sketch (induction on $k$).** For $k=1$, any two vectors in $L(S)$ are scalar multiples of $A_1$, hence dependent. For the inductive step, write $k+1$ vectors $B_i\in L(S)$ as $B_i=\sum_{j=1}^k a_{ij}A_j$. If all coefficients of $A_1$ vanish, the $B_i$'s lie in the span of $\{A_2,\dots,A_k\}$ and dependence follows from the induction hypothesis. Otherwise, eliminate $A_1$ by forming suitable linear combinations of the $B_i$'s and apply the induction hypothesis again.

### 12.10.4 Orthogonal Sets

**Definition.** A set $S=\{A_1,\dots,A_k\}$ is **orthogonal** if $A_i\cdot A_j=0$ whenever $i\neq j$.

**Theorem 12.9.** Any orthogonal set of **nonzero** vectors in $V_n$ is linearly independent. Moreover, if $X=\sum_{i=1}^{k}c_i A_i$, then the coefficients are given by
$$
\boxed{c_j=\frac{X\cdot A_j}{A_j\cdot A_j}} \qquad (j=1,\dots,k).
$$

**Proof sketch.** Assume $\sum c_i A_i=O$. Take the dot product with $A_j$; orthogonality gives $c_j(A_j\cdot A_j)=0$, and $A_j\neq O$ implies $c_j=0$. For the formula, dot $X$ with $A_j$ and use orthogonality.

### 12.10.5 Orthonormal Sets

An orthogonal set in which every vector has norm $1$ is called an **orthonormal** set. For such a set the coefficient formula simplifies to
$$
c_j=X\cdot A_j.
$$

> The unit coordinate vectors $E_1,\dots,E_n$ form the standard orthonormal set in $V_n$.

## 12.11 Bases

### 12.11.1 Definition

**Definition.** A set $S=\{A_1,\dots,A_k\}$ in $V_n$ is called a **basis** for $V_n$ if $S$ spans every vector in $V_n$ uniquely. If, in addition, $S$ is orthogonal, it is called an **orthogonal basis**.

Thus a basis is a linearly independent set which spans the whole space. The unit coordinate vectors $E_1,\dots,E_n$ form the **standard basis**; it is also an orthogonal basis.

### 12.11.2 Fundamental Properties of Bases

**Theorem 12.10.** In a given vector space $V_n$, bases have the following properties:
- **(a)** Every basis contains exactly $n$ vectors.
- **(b)** Any set of linearly independent vectors is a subset of some basis.
- **(c)** Any set of $n$ linearly independent vectors is a basis.

### 12.11.3 Proof Sketch

**Part (a) — Equal cardinality.** Let $S$ and $T$ be two bases with $k$ and $r$ vectors respectively. Since $T\subseteq L(S)=V_n$ and $T$ has $r$ vectors, Theorem 12.8 implies $r\le k$ (otherwise $T$ would be dependent). Interchanging roles gives $k\le r$. Hence $k=r$. Since $\{E_1,\dots,E_n\}$ is one basis, every basis has $n$ elements.

**Part (b) — Extension to a basis.** Let $S$ be independent. If $L(S)=V_n$, done. Otherwise pick $X\notin L(S)$ and form $S'=S\cup\{X\}$. If $S'$ were dependent, a nontrivial relation $\sum c_iA_i+c_{k+1}X=O$ would force $c_{k+1}\neq0$ (since $S$ is independent), yielding $X\in L(S)$, a contradiction. Thus $S'$ remains independent. Repeating finitely many times produces a basis (the process must stop, otherwise $n+1$ independent vectors would exist, contradicting Theorem 12.8).

**Part (c) — $n$ independent vectors form a basis.** Let $S$ be any independent set of $n$ vectors. By (b), $S\subseteq B$ for some basis $B$. By (a), $B$ has exactly $n$ elements, so $S=B$.

> Properties (a)–(c) justify calling $n$ the **dimension** of $V_n$.

## 12.12 The Complex Vector Space $V_n(\mathbb{C})$

### 12.12.1 Definition

Replacing real scalars by complex scalars in the definition of $V_n$ yields the **complex vector space** $V_n(\mathbb{C})$. Equality, addition, and scalar multiplication are defined componentwise exactly as in the real case.

Since complex numbers satisfy the same field properties as real numbers, all theorems about $V_n$ that use only field properties remain valid for $V_n(\mathbb{C})$.

### 12.12.2 The Complex Dot Product

For $V_n(\mathbb{C})$ the ordinary dot product must be modified to preserve positivity, because a sum of squares of complex numbers can be negative.

**Definition.** For $A=(a_1,\dots,a_n)$ and $B=(b_1,\dots,b_n)$ in $V_n(\mathbb{C})$,
$$
\boxed{A\cdot B=\sum_{k=1}^{n}a_k\,\overline{b}_k}
$$
where $\overline{b}_k$ is the complex conjugate of $b_k$.

> When the components are real, $\overline{b}_k=b_k$ and this agrees with the real definition.

**Theorem 12.11.** For all vectors $A,B,C$ in $V_n(\mathbb{C})$ and all complex scalars $c$:
- **(a)** $A\cdot B=\overline{B\cdot A}$
- **(b)** $A\cdot(B+C)=A\cdot B+A\cdot C$
- **(c)** $c(A\cdot B)=(cA)\cdot B=A\cdot(\overline{c}B)$
- **(d)** $A\cdot A>0$ if $A\neq O$
- **(e)** $A\cdot A=0$ if $A=O$

> Note the conjugations in (a) and (c) when factors are interchanged or scalars are moved across the dot.

### 12.12.3 Norms, Cauchy–Schwarz, and Orthogonality

The Cauchy–Schwarz inequality takes the same form:
$$
|A\cdot B|^2\le(A\cdot A)(B\cdot B).
$$
The **norm** is defined by $\|A\|=(A\cdot A)^{1/2}$, and the fundamental norm properties (Theorem 12.4) and the **triangle inequality** remain valid without change.

**Orthogonality** is defined exactly as before: $A\perp B$ means $A\cdot B=0$. The Pythagorean identity $\|A+B\|^2=\|A\|^2+\|B\|^2$ holds for orthogonal vectors in $V_n(\mathbb{C})$.

### 12.12.4 Span, Independence, and Basis

The concepts of linear span, linear independence, linear dependence, and basis are defined for $V_n(\mathbb{C})$ exactly as in the real case. Theorems 12.7 through 12.10 and their proofs are all valid without change.

> Complex vector spaces arise naturally in linear differential equations and quantum mechanics.

[<- Previous: 11. Sequences and Series of Functions](11-sequences-and-series-of-functions.md) | [Next: 13. Applications of Vector Algebra to Analytic Geometry ->](13-applications-of-vector-algebra-to-analytic-geometry.md)
