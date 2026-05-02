# Chapter 13 — Set Functions and Elementary Probability

### 13.1 Historical Introduction

- **1654** — Gamblers’ dispute led Pascal and Fermat to formulate the first principles of probability (problems posed by Chevalier de Méré).
- **1657** — Christiaan Huygens published the first book on probability, *De Ratiociniis in Ludo Aleae*.
- **18th century** — Rapid development by Jakob Bernoulli and Abraham de Moivre.
- **1812** — Laplace’s *Théorie Analytique des Probabilités* extended probability to scientific and practical problems (theory of errors, actuarial mathematics, statistical mechanics).
- **1933** — A. N. Kolmogorov gave the modern axiomatic foundation (*Foundations of Probability Theory*); probability became part of the broader discipline of **measure theory**.

This chapter presents the basic notions of modern elementary probability and its connections to measure theory.


### 13.2 Finitely Additive Set Functions

A **set function** $f:\mathscr A\to\mathbb R$ assigns a real number to each set in a class $\mathscr A$.

**Finite additivity.** $f$ is *finitely additive* if
$$
 f(A\cup B)=f(A)+f(B)\quad\text{whenever }A,B\in\mathscr A\text{ are disjoint and }A\cup B\in\mathscr A.\tag{13.1}
$$
*Examples:* area, length, mass.

**Boolean algebra.** A nonempty class $\mathscr A$ of subsets of a universal set $S$ is a *Boolean algebra* if it is closed under finite unions and complements:
$$
 A\cup B\in\mathscr A\quad\text{and}\quad A'\in\mathscr A.
$$
Then it is also closed under intersections and differences: $A\cap B=(A'\cup B')'$, $A-B=A\cap B'$.
- Smallest Boolean algebra: $\mathscr A_0=\{\varnothing,S\}$.
- Largest Boolean algebra: $\mathscr A_1=$ all subsets of $S$.

**Theorem 13.1.** If $f$ is finitely additive on a Boolean algebra $\mathscr A$, then for all $A,B\in\mathscr A$:
$$
 f(A\cup B)=f(A)+f(B-A),\tag{13.2}
$$
$$
 f(A\cup B)=f(A)+f(B)-f(A\cap B).\tag{13.3}
$$
*Proof.* (13.2) follows from (13.1) because $A$ and $B-A$ are disjoint with union $A\cup B$. For (13.3), write $A\cup B=(A\cap B')\cup B$ and $A=(A\cap B')\cup(A\cap B)$, apply (13.1) to both, and subtract.


### 13.3 Finitely Additive Measures

A **finitely additive measure** (or simply a **measure**) is a nonnegative finitely additive set function $f:\mathscr A\to\mathbb R$.

**Theorem 13.2 (Properties of measures).** Let $f$ be a finitely additive measure on a Boolean algebra $\mathscr A$. Then for all $A,B\in\mathscr A$:
- **(a)** $f(A\cup B)\le f(A)+f(B)$.  
- **(b)** $f(B-A)=f(B)-f(A)$ if $A\subseteq B$.  
- **(c)** $f(A)\le f(B)$ if $A\subseteq B$ *(monotone property)*.  
- **(d)** $f(\varnothing)=0$.

*Proof.* (a) follows from (13.3); (b) from (13.2); (c) from (b); (d) by taking $A=B=\varnothing$ in (b).

**Example.** *Counting measure.* Let $S=\{a_1,\dots,a_n\}$ and let $\nu(A)$ be the number of elements in $A$. Then $\nu$ is a finitely additive measure on the power set of $S$.


### 13.5 The Definition of Probability for Finite Sample Spaces

A **probability measure** $P$ on a Boolean algebra $\mathscr B$ of subsets of a sample space $S$ is a set function satisfying
- **(a)** finite additivity,
- **(b)** nonnegativity,
- **(c)** $P(S)=1$.

In other words, probability is a measure that assigns the value $1$ to the whole space.

**Probability space.** The triple $(S,\mathscr B,P)$ is called a *probability space*. In elementary applications $\mathscr B$ is usually the collection of *all* subsets of $S$.

**Example.** Tossing a coin once: $S=\{h,t\}$, $\mathscr B=\{\varnothing,S,\{h\},\{t\}\}$.  
Finite additivity and $P(S)=1$ give $P(\{h\})+P(\{t\})=1$.  
- Unbiased coin: $P(\{h\})=P(\{t\})=\tfrac12$.  
- Loaded coin: any $p\in[0,1]$ with $P(\{h\})=p$, $P(\{t\})=1-p$.

**Point probabilities.** If $S=\{a_1,\dots,a_n\}$, $P$ is completely determined by its values on singletons:
$$
 P(A)=\sum_{a_i\in A}P(a_i)\qquad\text{for every }A\subseteq S.
$$
Here $P(a_i)$ is shorthand for $P(\{a_i\})$.


### 13.6 Special Terminology Peculiar to Probability Theory

**Basic terms.**
- **Outcome (sample):** an element $x$ of the sample space $S$.
- **Event:** a subset $A\in\mathscr B$ of $S$.
- **$A$ occurs:** the outcome $x$ belongs to $A$.
- **Impossible event:** $\varnothing$ (never occurs).
- **Certain event:** $S$ (always occurs).

**Likelihood.**
- *Equally likely:* $P(A)=P(B)$.
- *More likely:* $P(A)>P(B)$.
- *At least as likely:* $P(A)\ge P(B)$.

**Glossary (Table 13.1).**

| Statement | Set-theoretic meaning |
|---|---|
| At least one of $A$ or $B$ occurs | $x\in A\cup B$ |
| Both $A$ and $B$ occur | $x\in A\cap B$ |
| Neither $A$ nor $B$ occurs | $x\in A'\cap B'$ |
| $A$ occurs and $B$ does not | $x\in A\cap B'$ |
| Exactly one of $A$ or $B$ occurs | $x\in(A\cap B')\cup(A'\cap B)$ |
| Not more than one occurs | $x\in(A\cap B)'$ |
| $A$ implies $B$ | $A\subseteq B$ |
| $A$ and $B$ are mutually exclusive | $A\cap B=\varnothing$ |


### 13.8 Worked Examples

**Example 1.** Toss a coin twice; $S=\{hh,ht,th,tt\}$.  
Event $A=$ "at least one head" $=\{hh,ht,th\}$. With equally likely outcomes,
$$
 P(A)=3\cdot\tfrac14=\tfrac34.
$$

**Example 2.** Draw one card from each of two decks; $S$ has $52^2$ ordered pairs.  
Event $A=$ "at least one ace of hearts" has $52+51$ elements, so
$$
 P(A)=\frac{52+51}{52^2}=\frac1{26}-\frac1{52^2}.
$$

**Example 3.** Draw two cards from one deck (ordered); $|S|=52\cdot51$.  
Event $A=$ "one is the ace of hearts" has $2\cdot51$ elements, so
$$
 P(A)=\frac{2\cdot51}{52\cdot51}=\frac1{26}.
$$

**Example 4.** Throw three dice; $|S|=6^3$. Let $A_n$ be the set of triples with sum $n$.  
For $3\le a+b+c\le6$ we have $|A_3|=1$, $|A_4|=3$, $|A_5|=6$, $|A_6|=10$, hence
$$
 P(A)=\frac{1+3+6+10}{6^3}=\frac{20}{216}=\frac5{54}.
$$

**Example 5.** Throw one die; $S=\{1,\dots,6\}$.  
$A=\{2,4,6\}$ (even), $B=\{3,6\}$ (multiple of 3). Then $A\cup B=\{2,3,4,6\}$ and
$$
 P(A\cup B)=P(A)+P(B)-P(A\cap B)=\frac36+\frac26-\frac16=\frac46=\frac23.
$$

