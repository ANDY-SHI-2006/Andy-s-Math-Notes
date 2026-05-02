# Chapter 14 — Calculus of Probabilities

### 14.1 The Definition of Probability for Uncountable Sample Spaces

Extending probability to uncountable sample spaces leads to technical difficulties not present in the countable case. To avoid them we restrict $S$ to be a subset of $\mathbb R$ or $\mathbb R^n$, and use **measurable subsets**.

**Properties of measurable subsets of $\mathbb R$.**
1. If $A$ is measurable, so is $\mathbb R-A$.
2. A countable union of measurable sets is measurable.
3. Every interval (open, closed, half-open, finite, or infinite) is measurable.

The measurable subsets of $\mathbb R$ form a Boolean $\sigma$-algebra containing all intervals. The *smallest* such algebra consists of the **Borel sets** (named after Émile Borel).  
Similarly, in $n$-space the Borel sets are the smallest Boolean $\sigma$-algebra containing all Cartesian products of intervals.

Henceforth, whenever $S\subseteq\mathbb R^n$ is used as a sample space, it is assumed to be a Borel set; the Borel subsets of $S$ themselves form a Boolean $\sigma$-algebra.

**Definition.** Let $S$ be a subset of $\mathbb R^n$ and let $\mathscr B$ be the Boolean $\sigma$-algebra of Borel subsets of $S$. A nonnegative completely additive set function $P$ defined on $\mathscr B$ with $P(S)=1$ is called a **probability measure**. The triple $(S,\mathscr B,P)$ is called a **probability space**.

