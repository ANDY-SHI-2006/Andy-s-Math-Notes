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
