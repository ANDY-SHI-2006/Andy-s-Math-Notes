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


### 14.5 Distribution Functions

**Definition.** The *distribution function* of a one-dimensional random variable $X$ is
$$
 F(t)=P(X\le t),\qquad t\in\mathbb R.
$$
(Sometimes written $F_X$ to emphasise the variable.)

If $X$ is bounded with range in $[a,b]$, then $F(t)=0$ for $t<a$ and $F(t)=1$ for $t\ge b$.

**Theorem 14.2 (Basic properties).** For $a<b$:
- **(a)** $0\le F(t)\le 1$ for all $t$.
- **(b)** $P(a<X\le b)=F(b)-F(a)$.
- **(c)** $F$ is monotone nondecreasing.

**Theorem 14.3 (Other interval types).** For $a<b$:
- $P(a\le X\le b)=F(b)-F(a)+P(X=a)$.
- $P(a<X<b)=F(b)-F(a)-P(X=b)$.
- $P(a\le X<b)=F(b)-F(a)+P(X=a)-P(X=b)$.

All four intervals have the same probability iff $P(X=a)=P(X=b)=0$.

**Theorem 14.4 (Limits at infinity).**
$$
 \lim_{t\to-\infty}F(t)=0,\qquad\lim_{t\to+\infty}F(t)=1.\tag{14.1}
$$
*Proof sketch.* Write $S$ as a countable disjoint union of intervals $(-n,-n+1]$ and $(n,n+1]$; the sums telescope to $P(S)=L_2-L_1$, where $L_1=\lim_{t\to-\infty}F(t)$ and $L_2=\lim_{t\to+\infty}F(t)$. Since $P(S)=1$ and $0\le L_1\le L_2\le1$, we get $L_1=0$, $L_2=1$.

**Examples.**
- **Uniform on $[0,1]$:** $F(t)=0$ ($t<0$), $F(t)=t$ ($0\le t\le1$), $F(t)=1$ ($t\ge1$).
- **Cauchy:** $F(t)=\tfrac12+\tfrac1{\pi}\arctan t$.

