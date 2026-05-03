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


### 14.2 Countability of the Set of Points with Positive Probability

**Theorem 14.1.** Let $(S,\mathscr B,P)$ be a probability space and let $T=\{x\in S\mid P(x)>0\}$. Then $T$ is countable.

*Proof.* Partition $T$ into $T_n=\{x\mid\frac1{n+1}<P(x)\le\frac1n\}$. Each $T_n$ contains at most $n$ points (otherwise the total probability would exceed $1$). Since $T=\bigcup_n T_n$, $T$ is a countable union of finite sets.

*Consequence.* For an uncountable $S$ with equally likely outcomes, every point has probability $0$. Hence point probabilities alone do not suffice; one needs **random variables** and **distribution functions**.

### 14.3 Random Variables

**Definition.** A *random variable* is a real-valued function on a sample space $S$.  
- *One-dimensional:* $X:S\to\mathbb R$.  
- *Two-dimensional:* $(X,Y):S\to\mathbb R^2$.  
- *$n$-dimensional:* $\mathbf X:S\to\mathbb R^n$.

(The word "random" merely reminds us that the domain is a sample space.)

**Notations.**
- Outcomes: $\omega\in S$.
- $X(\omega)$: the value of $X$ at outcome $\omega$.
- Events are abbreviated: $X=t$ means $\{\omega\mid X(\omega)=t\}$, $a<X\le b$ means $\{\omega\mid a<X(\omega)\le b\}$, etc.

**Example 1.** Rolling a die; $X(\omega)=\omega$ (the face value), or $Y(\omega)=0$ if $\omega$ is even, $Y(\omega)=1$ if odd.

**Example 2.** Dart on a circular target. Natural random variables: rectangular coordinates $(x,y)$, polar coordinates $(r,\theta)$, or a single coordinate such as $r$ or $\theta$. The event "lands in the first quadrant" is $\{\omega\mid0\le\theta(\omega)\le\tfrac12\pi\}$.

