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
