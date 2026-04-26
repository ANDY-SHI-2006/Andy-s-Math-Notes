# Chapter 3 Determinants


### 3.1 Introduction

The **determinant** is a number assigned to each square matrix. We recall the definitions for orders two and three.

**Order 2:**

$$\begin{vmatrix}a_{11}&a_{12}\\a_{21}&a_{22}\end{vmatrix}=a_{11}a_{22}-a_{12}a_{21}.$$

Equivalently,

$$\det\begin{bmatrix}a_{11}&a_{12}\\a_{21}&a_{22}\end{bmatrix}=a_{11}a_{22}-a_{12}a_{21}.$$

> A determinant (vertical bars) is a **scalar**; it is conceptually distinct from the matrix itself (square brackets).

**Order 3** (expansion along the first row):

$$\det\begin{bmatrix}a_{11}&a_{12}&a_{13}\\a_{21}&a_{22}&a_{23}\\a_{31}&a_{32}&a_{33}\end{bmatrix}=a_{11}\begin{vmatrix}a_{22}&a_{23}\\a_{32}&a_{33}\end{vmatrix}-a_{12}\begin{vmatrix}a_{21}&a_{23}\\a_{31}&a_{33}\end{vmatrix}+a_{13}\begin{vmatrix}a_{21}&a_{22}\\a_{31}&a_{32}\end{vmatrix}.$$

---

**Program for the general case.** For an $n\times n$ matrix, an explicit formula containing $n!$ products exists but is unwieldy for large $n$. Instead, determinants are developed axiomatically:

1. Motivate the choice of axioms.
2. Deduce further properties from the axioms.
3. Prove existence and uniqueness of a function satisfying the axioms.


### 3.2 Motivation for the Choice of Axioms

In Volume I the scalar triple product of three vectors in 3-space was shown to equal the determinant of the matrix whose rows are the given vectors:

$$A_1\times A_2\cdot A_3=\det\begin{bmatrix}a_{11}&a_{12}&a_{13}\\a_{21}&a_{22}&a_{23}\\a_{31}&a_{32}&a_{33}\end{bmatrix}.$$

- If the rows are independent, the scalar triple product is nonzero (absolute value = volume of the parallelepiped).
- If the rows are dependent, the product is zero (volume collapses to zero).

Regarding the scalar triple product as a function $d(A_1,A_2,A_3)$ of the three row-vectors, the following properties motivate the axioms for a general determinant function:

| Property | Statement |
|----------|-----------|
| **(a) Homogeneity in each row** | $d(tA_1,A_2,A_3)=t\,d(A_1,A_2,A_3)$ for every scalar $t$ |
| **(b) Additivity in each row** | $d(A_1,A_2+C,A_3)=d(A_1,A_2,A_3)+d(A_1,C,A_3)$ for every vector $C$ |
| **(c) Equal rows give zero** | $d(A_1,A_2,A_3)=0$ whenever two rows are identical |
| **(d) Normalization** | $d(\boldsymbol i,\boldsymbol j,\boldsymbol k)=1$, where $\boldsymbol i=(1,0,0)$, $\boldsymbol j=(0,1,0)$, $\boldsymbol k=(0,0,1)$ |

> **Consequence of (b) and (c).** Taking $C=A_1$ in (b) and using (c):
> $$d(A_1,A_2+A_1,A_3)=d(A_1,A_2,A_3).$$
> Geometrically, the parallelepipeds determined by $(A_1,A_2,A_3)$ and $(A_1,A_1+A_2,A_3)$ have equal volume (same base area and same altitude).


### 3.3 A Set of Axioms for a Determinant Function

Let $A=(a_{ij})$ be an $n\times n$ matrix with rows $A_1,\dots,A_n$. A real- or complex-valued function $d$ of $n$ vectors in $n$-space is called a **determinant function of order $n$** if it satisfies the following axioms for all vectors $A_1,\dots,A_n,C$:

**Axiom 1** (Homogeneity in each row).
$$d(\dots,tA_k,\dots)=t\,d(\dots,A_k,\dots).$$

**Axiom 2** (Additivity in each row).
$$d(A_1,\dots,A_k+C,\dots,A_n)=d(A_1,\dots,A_k,\dots,A_n)+d(A_1,\dots,C,\dots,A_n).$$

**Axiom 3** (Vanishing on equal rows).
$$d(A_1,\dots,A_n)=0\quad\text{if }A_i=A_j\text{ for some }i\neq j.$$

**Axiom 4** (Normalization).
$$d(I_1,\dots,I_n)=1,$$
where $I_k$ is the $k$th unit coordinate vector.

> The first two axioms state that $d$ is a **multilinear** function of its rows. A weaker version of Axiom 3 is sometimes used:
>
> **Axiom 3$'$.** $d(A_1,\dots,A_n)=0$ if $A_k=A_{k+1}$ for some $k$.
>
> It is a remarkable fact that for a given $n$ there is one and only one function satisfying Axioms 1, 2, 3$'$, and 4.

---

**Theorem 3.1.** A determinant function satisfying Axioms 1, 2, and 3$'$ has the following further properties:

- **(a)** $d(A_1,\dots,A_n)=0$ if some row $A_k=O$.
- **(b)** $d$ changes sign if two adjacent rows are interchanged:
  $$d(\dots,A_k,A_{k+1},\dots)=-d(\dots,A_{k+1},A_k,\dots).$$
- **(c)** $d$ changes sign if any two rows $A_i,A_j$ ($i\neq j$) are interchanged.
- **(d)** Axiom 3 holds: $d=0$ whenever any two rows are equal.
- **(e)** $d=0$ if the rows are linearly dependent.

- **Proof sketch.**
  - (a) Set $t=0$ in Axiom 1.
  - (b) Let both rows $k$ and $k+1$ equal $A_k+A_{k+1}$; by 3$'$, $d=0$. Expanding by additivity gives four terms; the first and last vanish by 3$'$, leaving $d(\dots,A_k,A_{k+1},\dots)+d(\dots,A_{k+1},A_k,\dots)=0$.
  - (c) Interchange $A_i$ and $A_j$ ($i<j$) by moving $A_j$ leftward through $j-i$ adjacent swaps, then moving $A_i$ rightward through $j-i-1$ swaps — an odd total, so the sign reverses.
  - (d) If $A_i=A_j$, swapping them gives the same matrix, yet (c) says the sign changes; hence $d=-d$, so $d=0$.
  - (e) If $A_1=\sum_{k=2}^n t_k A_k$, then by linearity in the first row
    $$d(A_1,\dots,A_n)=\sum_{k=2}^n t_k\,d(A_k,A_2,\dots,A_n)=0,$$
    since each summand has two equal rows. $\square$


### 3.4 Computation of Determinants

**Example 1** — $2\times2$ determinant. Using multilinearity and Axioms 3$'$ and 4:

$$\det\begin{bmatrix}a_{11}&a_{12}\\a_{21}&a_{22}\end{bmatrix}=a_{11}a_{22}-a_{12}a_{21}.$$

This argument also shows that a determinant function of order 2 exists and is unique.

---

**Example 2** — Diagonal matrix. If $A=\operatorname{diag}(a_{11},\dots,a_{nn})$, then $A_k=a_{kk}I_k$. By repeated homogeneity,

$$\det A=d(a_{11}I_1,\dots,a_{nn}I_n)=a_{11}\cdots a_{nn}\,d(I_1,\dots,I_n)=a_{11}\cdots a_{nn}.$$

---

**Example 3** — Upper triangular matrix. Let

$$U=\begin{bmatrix}u_{11}&u_{12}&\cdots&u_{1n}\\0&u_{22}&\cdots&u_{2n}\\\vdots&&\ddots&\vdots\\0&0&\cdots&u_{nn}\end{bmatrix}.$$

- *Zero diagonal entry.* If some $u_{ii}=0$, the rows are dependent (the last $n-i+1$ rows have nonzero entries only in at most $n-i$ columns), so $\det U=0$ by Theorem 3.1(e).
- *General case.* Decompose $U_1=V_1+V_1'$ with $V_1=[u_{11},0,\dots,0]$ and $V_1'=[0,u_{12},\dots,u_{1n}]$. Then
  $$\det U=\det(V_1,U_2,\dots,U_n)+\det(V_1',U_2,\dots,U_n).$$
  The second term is an upper triangular matrix with a zero on the diagonal, hence zero. Repeating for each row yields a diagonal matrix with the same diagonal entries, so

  $$\det U=u_{11}u_{22}\cdots u_{nn}.$$

---

**Example 4** — Gauss–Jordan process. The three elementary row operations affect $\det A$ as follows:

| Operation | Effect on determinant |
|-----------|----------------------|
| (1) Interchange two rows | Changes sign |
| (2) Multiply a row by $c\neq0$ | Multiplied by $c$ |
| (3) Add a multiple of one row to another | Unchanged |

Reduce $A$ to an upper triangular matrix $U$. If $p$ interchanges and scalars $c_1,\dots,c_q$ were used in (2), then

$$\det A=(-1)^p(c_1c_2\cdots c_q)^{-1}\det U.$$

> This formula follows from Axioms 1–3 alone; Axiom 4 is not needed for its proof.


### 3.5 The Uniqueness Theorem

From Example 3 of §3.4 and formula (3.8), for every $n\times n$ matrix $A$ there is a scalar $c$ (depending on $A$) such that

$$d(A_1,\dots,A_n)=c\,d(I_1,\dots,I_n).$$

This consequence uses only Axioms 1, 2, and 3.

**Theorem 3.2** (Uniqueness theorem for determinants). Let $d$ be a function satisfying all four axioms for a determinant of order $n$, and let $f$ be another function satisfying Axioms 1, 2, and 3. Then for every choice of vectors $A_1,\dots,A_n$,

$$f(A_1,\dots,A_n)=d(A_1,\dots,A_n)\,f(I_1,\dots,I_n).$$

In particular, if $f$ also satisfies Axiom 4, then $f=d$.

- **Proof sketch.** Define $g=f-d\,f(I_1,\dots,I_n)$. Both $d$ and $f$ satisfy Axioms 1–3, so $g$ does too. Hence $g(A_1,\dots,A_n)=c\,g(I_1,\dots,I_n)$ for some scalar $c$. Taking $A=I$ and using $d(I_1,\dots,I_n)=1$ (Axiom 4) gives
  $$g(I_1,\dots,I_n)=f(I_1,\dots,I_n)-f(I_1,\dots,I_n)=0.$$
  Therefore $g(A_1,\dots,A_n)=0$ for all $A_1,\dots,A_n$, which yields the desired relation. $\square$


### 3.7 The Product Formula for Determinants

**Lemma 3.3.** If $A$ is $m\times n$ and $B$ is $n\times p$, then the $i$th row of the product $AB$ is the product of the $i$th row of $A$ with $B$:

$$(AB)_i=A_iB.$$

- **Proof sketch.** The $(i,j)$-entry of $AB$ is $c_{ij}=A_i\cdot B^j$, the dot product of the $i$th row of $A$ with the $j$th column of $B$. Hence
  $$C_i=[A_i\cdot B^1,\dots,A_i\cdot B^p]=A_iB.\quad\square$$

**Theorem 3.4** (Product formula for determinants). For any $n\times n$ matrices $A$ and $B$,

$$\det(AB)=(\det A)(\det B).$$

- **Proof sketch.** By Lemma 3.3 we must show
  $$d(A_1B,\dots,A_nB)=d(A_1,\dots,A_n)\,d(B_1,\dots,B_n).$$
  Since $B_i=(IB)_i=I_iB$, the right-hand side equals $d(A_1,\dots,A_n)\,d(I_1B,\dots,I_nB)$. Fix $B$ and define
  $$f(A_1,\dots,A_n)=d(A_1B,\dots,A_nB).$$
  One verifies that $f$ satisfies Axioms 1, 2, and 3 (multilinearity and vanishing on equal rows follow directly from the corresponding properties of $d$). By the uniqueness theorem (Theorem 3.2),
  $$f(A_1,\dots,A_n)=d(A_1,\dots,A_n)\,f(I_1,\dots,I_n),$$
  which is exactly the desired formula. $\square$


### 3.8 The Determinant of the Inverse of a Nonsingular Matrix

**Theorem 3.5.** If $A$ is nonsingular, then $\det A\neq0$ and

$$\det A^{-1}=\frac1{\det A}.$$

- **Proof.** From the product formula, $(\det A)(\det A^{-1})=\det(AA^{-1})=\det I=1$. Hence $\det A\neq0$ and the formula follows. $\square$

> Theorem 3.5 shows that $\det A\neq0$ is a **necessary** condition for $A$ to be nonsingular. Later we prove it is also **sufficient**.


### 3.9 Determinants and Independence of Vectors

**Theorem 3.6.** A set of $n$ vectors $A_1,\dots,A_n$ in $n$-space is independent if and only if $d(A_1,\dots,A_n)\neq0$.

- **Proof sketch.**
  - ($\Rightarrow$) If the vectors are dependent, Theorem 3.1(e) gives $d=0$.
  - ($\Leftarrow$) Assume $A_1,\dots,A_n$ are independent. Since there are $n$ independent vectors in an $n$-dimensional space, they form a basis for $V_n$. By Theorem 2.12 there is a linear transformation $T\colon V_n\to V_n$ with $T(A_k)=I_k$ ($k=1,\dots,n$). Let $B$ be the matrix of $T$. Then $A_kB=I_k$. By Lemma 3.3, $A_kB=(AB)_k$, so $AB=I$. Thus $A$ is nonsingular and $\det A\neq0$ by Theorem 3.5. $\square$


### 3.10 The Determinant of a Block-Diagonal Matrix

A **block-diagonal matrix** with diagonal blocks $A$ and $B$ has the form

$$C=\begin{bmatrix}A&O\\O&B\end{bmatrix}.$$

**Theorem 3.7.** For any square matrices $A$ ($n\times n$) and $B$ ($m\times m$),

$$\det\begin{bmatrix}A&O\\O&B\end{bmatrix}=(\det A)(\det B).$$

- **Proof sketch.** Factor the block-diagonal matrix:
  $$\begin{bmatrix}A&O\\O&B\end{bmatrix}=\begin{bmatrix}A&O\\O&I_m\end{bmatrix}\begin{bmatrix}I_n&O\\O&B\end{bmatrix}.$$
  By the product formula,
  $$\det C=\det\begin{bmatrix}A&O\\O&I_m\end{bmatrix}\det\begin{bmatrix}I_n&O\\O&B\end{bmatrix}.$$
  Regard $\det\begin{bmatrix}A&O\\O&I_m\end{bmatrix}$ as a function of the $n$ rows of $A$. Because of the zero block in the upper right, this function satisfies all four determinant axioms of order $n$; by uniqueness it equals $\det A$. Similarly the second factor equals $\det B$. Multiplying gives the result. $\square$


### 3.12 Expansion Formulas, Minors, and Cofactors

Since $A_1=\sum_{j=1}^n a_{1j}I_j$, linearity in the first row gives

$$d(A_1,\dots,A_n)=\sum_{j=1}^n a_{1j}\,d(I_j,A_2,\dots,A_n).$$

Let $A_{kj}'$ denote the matrix obtained from $A$ by replacing row $k$ with the unit vector $I_j$. Then $d(I_j,A_2,\dots,A_n)=\det A_{1j}'$, and we obtain the **expansion formula**

$$\det A=\sum_{j=1}^n a_{kj}\det A_{kj}'\qquad\text{(expansion along the $k$th row).}$$

The number $\det A_{kj}'$ is called the **cofactor** of the entry $a_{kj}$.

---

**Minors.** The $(k,j)$ **minor** $A_{kj}$ is the $(n-1)\times(n-1)$ matrix obtained from $A$ by deleting row $k$ and column $j$.

**Theorem 3.9** (Expansion by $k$th-row minors). For $n\ge2$,

$$\det A_{kj}'=(-1)^{k+j}\det A_{kj},$$

and therefore

$$\det A=\sum_{j=1}^n(-1)^{k+j}a_{kj}\det A_{kj}.$$

- **Proof sketch.**
  - *Case $k=j=1$.* Use type-(3) row operations to clear the first column below the 1, obtaining a block-diagonal matrix; Theorem 3.7 gives $\det A_{11}'=\det A_{11}$.
  - *Case $k=1$, $j$ arbitrary.* After similar row operations, regard the result as a function $f(A_{1j})$ of the $n-1$ rows of the minor. By uniqueness, $f(A_{1j})=f(J)\det A_{1j}$. Here $f(J)=\det C$, where $C$ is the $n\times n$ matrix with a 1 in position $(1,j)$ and 1s on the diagonal elsewhere. Moving row 1 down to row $j$ requires $j-1$ adjacent swaps, so $f(J)=(-1)^{j-1}$.
  - *General $k,j$.* Move row $k$ to the top by $k-1$ adjacent swaps; each swap changes the sign of the determinant. Combining with the previous case yields the factor $(-1)^{k+j}$. $\square$


### 3.13 Existence of the Determinant Function

**Theorem 3.10.** Assume determinants of order $n-1$ exist. For any $n\times n$ matrix $A=(a_{jk})$ define

$$f(A_1,\dots,A_n)=\sum_{j=1}^n(-1)^{j+1}a_{j1}\det A_{j1}.$$

Then $f$ satisfies all four axioms for a determinant function of order $n$. Therefore, by induction, determinants of every order exist.

- **Proof sketch.** Write $f=\sum_j f_j$ where $f_j=(-1)^{j+1}a_{j1}\det A_{j1}$.

  - *Axioms 1 and 2.* If row 1 is multiplied by $t$, then $a_{11}$ is multiplied by $t$ (for $j=1$) or the first row of $A_{j1}$ is multiplied by $t$ (for $j>1$); in either case $f_j$ is multiplied by $t$. If row $k$ ($k>1$) is multiplied by $t$, the same reasoning applies. A similar argument gives additivity.

  - *Axiom 3$'$.* Suppose $A_k=A_{k+1}$. For $j\neq k,k+1$, the minor $A_{j1}$ still contains two equal rows, so $\det A_{j1}=0$. The sum reduces to the two terms $j=k$ and $j=k+1$:
    $$f=(-1)^{k+1}a_{k1}\det A_{k1}+(-1)^{k+2}a_{k+1,1}\det A_{k+1,1}.$$
    Since $A_k=A_{k+1}$ we have $a_{k1}=a_{k+1,1}$ and $A_{k1}=A_{k+1,1}$; the two terms cancel.

  - *Axiom 4.* For $A=I$ we have $a_{11}=1$, $a_{j1}=0$ ($j>1$), and $A_{11}=I_{n-1}$. Hence $f(I_1,\dots,I_n)=1\cdot\det I_{n-1}=1$. $\square$

> The same proof works with expansion along any column $k$:
> $$\det A=\sum_{j=1}^n(-1)^{j+k}a_{jk}\det A_{jk}.$$
> By uniqueness, all expansion formulas (by any row or column) give the same value.


### 3.14 The Determinant of a Transpose

**Definition.** The **transpose** of an $m\times n$ matrix $A=(a_{ij})$ is the $n\times m$ matrix $A^t$ whose $(i,j)$-entry is $a_{ji}$. The rows of $A^t$ are the columns of $A$.

**Theorem 3.11.** For any $n\times n$ matrix $A$,

$$\det A=\det A^t.$$

- **Proof sketch** (induction on $n$). The cases $n=1,2$ are immediate. Assume the theorem holds for order $n-1$, let $B=A^t=(b_{ij})$, and expand:
  $$\det A=\sum_{j=1}^n(-1)^{j+1}a_{j1}\det A_{j1},\qquad \det B=\sum_{j=1}^n(-1)^{j+1}b_{1j}\det B_{1j}.$$
  By definition of transpose, $b_{1j}=a_{j1}$ and $B_{1j}=(A_{j1})^t$. The induction hypothesis gives $\det B_{1j}=\det A_{j1}$. Hence the two sums are equal term by term, so $\det A=\det B$. $\square$


### 3.15 The Cofactor Matrix

Recall the **cofactor** of $a_{ij}$:

$$\operatorname{cof}a_{ij}=(-1)^{i+j}\det A_{ij}.$$

**Definition.** The **cofactor matrix** $\operatorname{cof}A$ is the matrix whose $(i,j)$-entry is $\operatorname{cof}a_{ij}$. (Its transpose is often called the **adjugate** of $A$.)

**Theorem 3.12.** For any $n\times n$ matrix $A$ ($n\ge2$),

$$A(\operatorname{cof}A)^t=(\det A)I.$$

In particular, if $\det A\neq0$,

$$A^{-1}=\frac1{\det A}(\operatorname{cof}A)^t.$$

- **Proof sketch.** Expanding $\det A$ along row $k$ gives $\det A=\sum_j a_{kj}\operatorname{cof}a_{kj}$. If $i\neq k$, let $B$ be $A$ with row $i$ replaced by row $k$; then $\det B=0$ and expanding along row $i$ yields $\sum_j a_{kj}\operatorname{cof}a_{ij}=0$. Hence
  $$\sum_{j=1}^n a_{kj}\operatorname{cof}a_{ij}=\begin{cases}\det A&i=k,\\0&i\neq k,\end{cases}$$
  which is exactly the $(k,i)$-entry of $A(\operatorname{cof}A)^t$. $\square$

**Theorem 3.13.** A square matrix $A$ is nonsingular if and only if $\det A\neq0$.


### 3.16 Cramer's Rule

**Theorem 3.14** (Cramer's rule). If the system $\sum_{j=1}^n a_{ij}x_j=b_i$ ($i=1,\dots,n$) has a nonsingular coefficient matrix $A$, its unique solution is

$$x_j=\frac1{\det A}\sum_{k=1}^n b_k\operatorname{cof}a_{kj}\qquad(j=1,\dots,n).$$

Equivalently,

$$x_j=\frac{\det C_j}{\det A},$$

where $C_j$ is the matrix obtained from $A$ by replacing column $j$ with the column vector $B=(b_1,\dots,b_n)$.

- **Proof sketch.** In matrix form $AX=B$, so $X=A^{-1}B=\frac1{\det A}(\operatorname{cof}A)^tB$. The $j$th component of this vector is the formula above. $\square$
