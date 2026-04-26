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
