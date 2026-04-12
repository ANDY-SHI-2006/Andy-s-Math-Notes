# 1 Basic Logic

## 1.1 Mathematical statements

### 1.1.1 Definition of Statement
A **statement** is a declarative sentence in a given mathematical theory that satisfies the following conditions:

- **No free variables**: The sentence does not contain any free variable
- **Determinate truth value**: Its truth value (true or false) can in principle be determined
- **Law of excluded middle**: In a consistent mathematical theory, any statement is either true or false
- **Law of non-contradiction**: A statement cannot be both true and false at the same time

### 1.1.2 Example
- "2 is an even number" is a **true** statement
- "1 > 2" is a **false** statement

### 1.1.3 Example
- "$1+2$" is a computational formula, it is **not a statement**
- The inequality "$2x + 1 > 0$" contains a free variable $x$, so judging its truth value is meaningless. Therefore, it is **not a statement**

In this book, we use the symbol $:=$ to interpret the notation on the left hand side of the symbol as the expression on the right hand side. For example, "$a := 3+5$" means that we denote by $a$ the value of $3+5$. This expression is not a statement.

### 1.1.4 Definition of Axiom
An **axiom** is a statement that is:
- **Admitted as true without justification** in a mathematical theory
- **Self-evident** or **assumed as a starting point** for reasoning
- The **foundation** upon which a mathematical theory is built

### 1.1.5 Definition of Theorem
A **theorem** is a statement that is:
- **Confirmed to be true** through rigorous mathematical proof
- **Logically deduced** from axioms or other theorems
- **Important** enough to be explicitly stated and proved

### 1.1.6 Definition of Corollary
A **corollary** is a statement that is:
- **Deduced from a theorem** via straightforward reasoning
- **A direct consequence** of a previously proved theorem
- **Usually simpler** than the theorem from which it follows

### 1.1.7 Definition of Proposition
A **proposition** is:
- In general mathematical literature: synonymous with **statement** (any declarative sentence that is either true or false)
- In this book specifically: used to label **theorems that are relatively simple** or **not repeatedly applied** in the text
- A **less prominent** result compared to a theorem

## 1.2 Negation

### 1.2.1 Definition of Negation
Let $P$ be a statement. The **negation** of $P$, denoted $\neg P$ (read as "not $P$"), is a statement that satisfies:

- **Opposite truth value**: If $P$ is true, then $\neg P$ is false; if $P$ is false, then $\neg P$ is true
- **Logical inversion**: The negation completely reverses the truth value of the original statement
- **Notation**: The symbol $\neg$ is called the **negation operator** or **logical NOT**

### 1.2.3 Remark

| $P$ | $\neg P$ | $\neg\neg P$ |
|:---:|:---------:|:------------:|
|  T  |     F     |       T      |
|  F  |     T     |       F      |

## 1.3 Conjunction and disjunction

### 1.3.1 Definition of Conjunction
Let $P$ and $Q$ be statements. The **conjunction** of $P$ and $Q$, denoted $P \wedge Q$ (read as "$P$ and $Q$"), is a compound statement that satisfies:

- **True only when both are true**: $P \wedge Q$ is true if and only if both $P$ is true and $Q$ is true
- **False otherwise**: If either $P$ or $Q$ (or both) is false, then $P \wedge Q$ is false
- **Notation**: The symbol $\wedge$ is called the **conjunction operator** or **logical AND**
- **Alternative names**: Also called the **logical product** of $P$ and $Q$

### 1.3.2 Definition of Disjunction
Let $P$ and $Q$ be statements. The **disjunction** of $P$ and $Q$, denoted $P \vee Q$ (read as "$P$ or $Q$"), is a compound statement that satisfies:

- **False only when both are false**: $P \vee Q$ is false if and only if both $P$ is false and $Q$ is false
- **True otherwise**: If either $P$ or $Q$ (or both) is true, then $P \vee Q$ is true
- **Notation**: The symbol $\vee$ is called the **disjunction operator** or **logical OR**
- **Alternative names**: Also called the **logical sum** of $P$ and $Q$

### 1.3.3 Remark

| $P$ | $Q$ | $P \wedge Q$ | $P \vee Q$ | $Q \wedge P$ | $Q \vee P$ |
|:---:|:---:|:------------:|:-----------:|:------------:|:-----------:|
|  T  |  T  |       T      |      T      |       T      |      T      |
|  T  |  F  |       F      |      T      |       F      |      T      |
|  F  |  T  |       F      |      T      |       F      |      T      |
|  F  |  F  |       F      |      F      |       F      |      F      |

We observe from the table that $P \wedge Q$ and $Q \wedge P$ have the same truth value, and $P \vee Q$ and $Q \vee P$ have the same truth value.

### 1.3.4 Proposition (De Morgan's Laws)
Let $P$ and $Q$ be statements. The statements $\neg(P \wedge Q)$ and $(\neg P) \vee (\neg Q)$ have the same truth value, and $\neg(P \vee Q)$ and $(\neg P) \wedge (\neg Q)$ have the same truth value.

*Proof.* This can be observed from the following tables.

**First law:** $\neg(P \wedge Q) \equiv (\neg P) \vee (\neg Q)$

| $P$ | $Q$ | $P \wedge Q$ | $\neg(P \wedge Q)$ | $\neg P$ | $\neg Q$ | $(\neg P) \vee (\neg Q)$ |
|:---:|:---:|:------------:|:--------------------:|:---------:|:---------:|:-------------------------:|
|  T  |  T  |       T      |          F           |     F     |     F     |             F             |
|  T  |  F  |       F      |          T           |     F     |     T     |             T             |
|  F  |  T  |       F      |          T           |     T     |     F     |             T             |
|  F  |  F  |       F      |          T           |     T     |     T     |             T             |

**Second law:** $\neg(P \vee Q) \equiv (\neg P) \wedge (\neg Q)$

| $P$ | $Q$ | $P \vee Q$ | $\neg(P \vee Q)$ | $\neg P$ | $\neg Q$ | $(\neg P) \wedge (\neg Q)$ |
|:---:|:---:|:-----------:|:-------------------:|:---------:|:---------:|:---------------------------:|
|  T  |  T  |      T      |          F          |     F     |     F     |              F              |
|  T  |  F  |      T      |          F          |     F     |     T     |              F              |
|  F  |  T  |      T      |          F          |     T     |     F     |              F              |
|  F  |  F  |      F      |          T          |     T     |     T     |              T              |

## 1.4 Conditional statement

### 1.4.1 Definition of Conditional Statement
Let $P$ and $Q$ be statements. The **conditional statement** (or **implication**), denoted $P \Rightarrow Q$ (read as "if $P$, then $Q$"), is a compound statement that satisfies:

- **Equivalent form**: $P \Rightarrow Q$ has the same truth value as $(\neg P) \vee Q$
- **False only in one case**: $P \Rightarrow Q$ is false if and only if $P$ is true and $Q$ is false
- **True otherwise**: If $P$ is false, or if both $P$ and $Q$ are true, then $P \Rightarrow Q$ is true
- **Terminology**: 
  - $P$ is called the **hypothesis** (or **antecedent**)
  - $Q$ is called the **conclusion** (or **consequent**)
- **Notation**: The symbol $\Rightarrow$ is called the **implication operator**

| $P$ | $Q$ | $\neg P$ | $P \Rightarrow Q$ |
|:---:|:---:|:---------:|:-----------------:|
|  T  |  T  |     F     |         T         |
|  T  |  F  |     F     |         F         |
|  F  |  T  |     T     |         T         |
|  F  |  F  |     T     |         T         |

### 1.4.2 Remark
We observe from the table that, only in the case where $P$ is true and $Q$ is false, the statement $P \Rightarrow Q$ is false, otherwise it is true. Therefore, if one can prove $Q$ under the assumption that $P$ is true, then the statement $P \Rightarrow Q$ is true. However, the statement $P \Rightarrow Q$ itself does not signify that we are considering a proof of the statement $Q$ from $P$.

We also observe from the table that, in the case where both $P$ and $P \Rightarrow Q$ are true, the statement $Q$ must be true. This type of reasonings often appear in a mathematical proof.

### 1.4.3 Proposition (Transitivity)
Let $P$, $Q$ and $R$ be statements. If both $P \Rightarrow Q$ and $Q \Rightarrow R$ are true, then $P \Rightarrow R$ is true.

*Proof.* It suffices to treat the case where $P$ is true, since otherwise $P \Rightarrow R$ is automatically true. In the case where $P$ is true, since $P \Rightarrow Q$ is true, we deduce that $Q$ is true. Furthermore, since $Q \Rightarrow R$ is true, we deduce that $R$ is true. Therefore, $P \Rightarrow R$ is true.

### 1.4.4 Proposition
Let $P$ and $Q$ be statements. The statements $P \Rightarrow Q$ and $(\neg Q) \Rightarrow (\neg P)$ have the same truth value.

*Proof.* We could conclude from the following table.

| $P$ | $Q$ | $\neg P$ | $\neg Q$ | $(\neg Q) \Rightarrow (\neg P)$ |
|:---:|:---:|:---------:|:---------:|:--------------------------------:|
|  T  |  T  |     F     |     F     |                T                 |
|  T  |  F  |     F     |     T     |                F                 |
|  F  |  T  |     T     |     F     |                T                 |
|  F  |  F  |     T     |     T     |                T                 |

### 1.4.5 Definition
Let $P$ and $Q$ be two statements. The statement $(\neg Q) \Rightarrow (\neg P)$ is called the **contrapositive** of the statement $P \Rightarrow Q$. If one proves the contrapositive statement $(\neg Q) \Rightarrow (\neg P)$, then, by Proposition 1.4.4, we obtain that the statement $P \Rightarrow Q$ is also true. This method is called **proof by contraposition**.

### 1.4.6 Example
Let $n$ be an integer. We prove by contraposition that, if $n^2$ is an even number, then $n$ is an even number. Note that the contrapositive of this statement says that, if $n$ is not an even number, then $n^2$ is not an even number.

Since $n$ is an integer, if $n$ is not an even number, it must be an odd number, namely it is of the form $2k + 1$, with $k$ being an integer. Therefore:

$$n^2 = (2k + 1)^2 = 4k^2 + 4k + 1$$

is an odd number. Thus we have proved the contrapositive statement. Hence the initial statement is also true.

## 1.5 Biconditional statement

### 1.5.1 Definition
Let $P$ and $Q$ be statements. Then "$P$ if and only if $Q$" is also a statement, often denoted as $P \Leftrightarrow Q$. When $P$ and $Q$ have the same truth value, the statement $P \Leftrightarrow Q$ is true, otherwise $P \Leftrightarrow Q$ is false. By definition, the statements $P \Leftrightarrow Q$ and $Q \Leftrightarrow P$ have the same true value.

### 1.5.2 Proposition
Let $P$ and $Q$ be statements. Then $(P \Rightarrow Q) \wedge (Q \Rightarrow P)$ and $P \Leftrightarrow Q$ have the same truth value.

*Proof.* We could conclude from the following table.

| $P$ | $Q$ | $P \Rightarrow Q$ | $Q \Rightarrow P$ | $P \Leftrightarrow Q$ |
|:---:|:---:|:-----------------:|:-----------------:|:----------------------:|
|  T  |  T  |         T         |         T         |           T            |
|  T  |  F  |         F         |         T         |           F            |
|  F  |  T  |         T         |         F         |           F            |
|  F  |  F  |         T         |         T         |           T            |

### 1.5.3 Remark
The above proposition shows that, given two statements $P$ and $Q$, to prove that they have the same truth value, it suffices to prove conditional statements of both directions $P \Rightarrow Q$ and $Q \Rightarrow P$. The statement $Q \Rightarrow P$ is called the **converse** of $P \Rightarrow Q$. The contraposition of $Q \Rightarrow P$, namely $(\neg P) \Rightarrow (\neg Q)$, is called the **inverse** of $P \Rightarrow Q$. Proposition 1.4.4 shows that the converse and the inverse of a conditional statement have the same truth value. Therefore, to justify the biconditional statement $P \Leftrightarrow Q$, it also suffices to prove the conditional statement $P \Rightarrow Q$ and its inverse $(\neg P) \Rightarrow (\neg Q)$.

### 1.5.4 Example
Let $n$ be an integer. Then $n^2$ is an even number if and only if $n$ is an even number. In fact, we have proved in Example 1.4.6 that, if $n^2$ is an even number, then $n$ is an even number. It remains to check that, if $n$ is an even number, then $n^2$ is also an even number. Assume that $n$ is of the form $2k$, where $k$ is an integer. Then $n^2 = 4k^2$ is divisible by 2. Hence $n^2$ is an even number.

## 1.6 Proof by contradiction

### 1.6.1 Definition
In a consistent mathematical theory, a statement cannot be true and false at the same time. Let $P$ be a statement. If we assume that $\neg P$ is true and deduce that a certain statement is both true and false, then we say that a **contradiction** happens and the assumption $\neg P$ is false. Thus the statement $P$ is true. Such a reasoning is called **proof by contradiction**.

### 1.6.2 Example
We prove by contradiction that the equation $x^2 = 2$ does not have any rational solution. Suppose by contradiction that $p/q$ is a solution of the equation $x^2 = 2$, where $p$ is an integer and $q$ is a positive integer, which do not have common prime divisor. By definition, one has $p^2 = 2q^2$. Hence $p^2$ is an even number. By Example 1.5.4, we obtain that $p$ is an even number. Hence there exists $p_1 \in \mathbb{Z}$ such that $p = 2p_1$. Hence we deduce from $p^2 = 2q^2$ that $2p_1^2 = q^2$.

This shows that $q^2$ is an even number and hence $q$ is an even number. Thus $p$ and $q$ has 2 as a common prime divisor, which leads to a contradiction.

## Exercises

1. Let $P$ and $Q$ be statements. Use truth tables to determine the truth values of the following statements according to the truth values of $P$ and $Q$:
   - $P \wedge \neg P$
   - $P \vee \neg P$
   - $(P \vee Q) \Rightarrow (P \wedge Q)$
   - $(P \Rightarrow Q) \Rightarrow (Q \Rightarrow P)$

2. Let $P$ and $Q$ be statements.
   - (1) Show that $P \Rightarrow (Q \wedge \neg Q)$ has the same truth value as $\neg P$.
   - (2) Show that $(P \wedge \neg Q) \Rightarrow Q$ has the same truth value as $P \Rightarrow Q$.

3. Consider the following statements:
   - $P :=$ "Little Bear is happy"
   - $Q :=$ "Little Bear has done her math homework"
   - $R :=$ "Little Rabbit is happy"
   
   Express the following statements using $P$, $Q$, and $R$, along with logical connectives:
   - (1) If Little Bear is happy and has done her math homework, then Little Rabbit is happy.
   - (2) If Little Bear has done her math homework, then she is happy.
   - (3) Little Bear is happy only if she has done her math homework.

4. Does the following reasoning hold? Justify your answer.
   - It is known that Little Bear is both smart and lazy, or Little Bear is not smart.
   - It is also known that Little Bear is smart.
   - Therefore, Little Bear is lazy.

5. Does the following reasoning hold? Justify your answer.
   - It is known that at least one of the lion or the tiger is guilty.
   - It is also known that either the lion is lying or the tiger is innocent.
   - Therefore, the lion is either lying or guilty.

6. An explorer arrives at a cave with three closed doors, numbered 1, 2, and 3. Exactly one door hides treasure, while the other two conceal deadly traps.
   - Door 1 states: "The treasure is not here"
   - Door 2 states: "The treasure is not here"
   - Door 3 states: "The treasure is behind Door 2"
   
   Only one of these statements is true. Which door should the explorer open to find the treasure?

7. The Kingdom of Truth sent an envoy to the capital of the Kingdom of Lies. Upon entering the border, the envoy encountered a fork with three paths: dirt, stone, and concrete. Each path had a signpost:
   - The concrete path's sign: "This path leads to the capital, and if the dirt path leads to the capital, then the stone path also does."
   - The stone path's sign: "Neither the concrete nor the dirt path leads to the capital."
   - The dirt path's sign: "The concrete path leads to the capital, but the stone path does not."
   
   All signposts lie. Which path should the envoy take?

8. Let $a$ and $b$ be real numbers. Prove that, if $a \neq -1$ and $b \neq -1$, then $ab + a + b \neq -1$.

9. Let $a$, $b$, and $c$ be positive real numbers such that $abc > 1$ and $a + b + c < \frac{1}{a} + \frac{1}{b} + \frac{1}{c}$. Prove the following:
   - (1) None of $a$, $b$, or $c$ equals 1.
   - (2) At least one of $a$, $b$, or $c$ is greater than 1.
   - (3) At least one of $a$, $b$, or $c$ is less than 1.

10. Let $a \neq 0$ and $b$ be real numbers. For real numbers $x$ and $y$, prove that if $x \neq y$, then $ax + b \neq ay + b$.

11. Let $n \geq 2$ be an integer. Prove that if $n$ is composite, then there exists a prime number $p$ dividing $n$ such that $p \leq \sqrt{n}$.

12. Let $n$ be an integer. Prove that either 4 divides $n^2$ or 4 divides $n^2 - 1$.

13. Let $n$ be an integer. Prove that 12 divides $n^2(n^2 - 1)$.

14. Prove that any integer divisible by 4 can be written as the difference of two perfect squares.

15. Let $x$ and $y$ be non-zero integers. Prove that $x^2 - y^2 \neq 1$.

16. A plane has 300 seats and is fully booked. The first passenger ignores their assigned seat and chooses randomly. Subsequent passengers take their assigned seat if available; otherwise, they choose randomly. What is the probability that the last passenger sits in their assigned seat?

17. Little Bear, Little Goat, and Little Rabbit are all wearing hats. A parrot prepared four red feathers and four blue feathers to decorate their hats. The parrot selected two feathers for each hat-wearing animal to place on their hats. Each animal cannot see the feathers on their own hat but can see the feathers on the other animals' hats. Here is their conversation:
    - Little Bear: "I don't know what color the feathers on my hat are, but I know the other animals also don't know what color the feathers on their hats are."
    - Little Goat: "Haha, now even without looking at Little Bear's hat, I know what color the feathers on my hat are."
    - Little Rabbit: "Now I know what color the feathers on my hat are."
    - Little Bear: "Hmm, now I also know what color the feathers on my hat are."
    
    Question: What color are the feathers on Little Goat's hat?

18. The Sphinx tells the truth on one fixed weekday and lies on the other six. Cleopatra visits The Sphinx for three consecutive days:
    - Day 1: The Sphinx declared, "I lie on Monday and Tuesday."
    - Day 2: The Sphinx declared, "Today is either Thursday, or Saturday, or Sunday."
    - Day 3: The Sphinx declared, "I lie on Wednesday and Friday."
    
    On which day does the Sphinx tell the truth? On which days of the week did Cleopatra visit The Sphinx?


---

# 2 Sets

This book presents the fundamentals of algebra and analysis based on set theory. Set theory, proposed initially by Cantor, is the cornerstone of modern mathematics. Before the emergence of set theory, the progress of mathematics was often built upon intuition and visual imagery. Moreover, due to the limitations of available tools, the scope of mathematical research was relatively narrow—for instance, analysis was often confined to studying functions with analytic expressions. Cantor's set theory introduced a new language and new tools to mathematics, greatly advancing the development of modern mathematics.

Naive set theory regards a set as a collection of distinct objects that are clearly defined. However, treating any such collection as a set without restriction leads to paradoxes. For example, Russell's paradox considers the collection of all sets that do not contain themselves. If this collection is treated as a set, one arrives at a contradiction regardless of whether the set contains itself or not. Determining which types of collections should be considered as sets is a subtle issue that lacks universal agreement. Axiomatic set theory treats set theory itself as a structure governed by a system of axioms. These axioms ensure the existence of constructions needed in mathematics while avoiding known paradoxes, thus providing a sound foundation for mathematics.

The goal of this chapter is to introduce some fundamental concepts of set theory and basic structures to prepare for the chapters that follow. Since our aim is not to give a systematic introduction to mathematical logic, we will explain ideas as much as possible using natural language rather than formal language.

## 2.1 Roster notation

### 2.1.1 Definition
In naive set theory, a **set** refers to a certain collection of distinct objects. The objects in a set are called **elements** of it. Two sets $A$ and $B$ are said to be **equal** if they have the same elements. We denote by $A = B$ the statement "$A$ and $B$ are equal".

If $A$ is a set and $a$ is an object, we denote by $a \in A$ the statement "$a$ is an element of $A$"; we denote by $a \notin A$ the statement "$a$ is not an element of $A$". If $a$ is an element of $A$, we also say that $a$ **belongs to** $A$.

### 2.1.2 Notation
The **roster method** of representing a set refers to a notation where all elements of the set are explicitly enumerated in a single row within a pair of curly braces. For example the set consisting of the elements 1, 2 and 3 can be denoted as $\{1, 2, 3\}$. The represented set is independent of the enumeration order or element repetition. For example, one has:

$$\{1, 2, 3\} = \{3, 2, 1\} = \{1, 1, 2, 3\}$$

When representing a set using the roster method, an ellipsis $(\ldots)$ may be used to indicate elements with an obvious pattern. For example, the set of positive integers less than 100 can be written as:

$$\{1, 2, \ldots, 100\}$$

Similarly, if $n$ is a natural number the set of natural numbers not exceeding $n$ can be written as:

$$\{0, 1, \ldots, n\}$$

When no ambiguity arises, an ellipsis may also be used to omit infinitely many elements with a clear pattern. For example, the set of all even integers can be expressed in roster notation as:

$$\{\ldots, -6, -4, -2, 0, 2, 4, 6, \ldots\}$$

When representing sets using the roster method, if the elements are indexed, an ellipsis can be used to summarise elements corresponding to indices with obvious patterns. For example, if $n$ is a positive integer and for each $i \in \{1, \ldots, n\}$, a mathematical object $x_i$ is given, then the set of these objects can be written as:

$$\{x_1, \ldots, x_n\}$$

Similarly, if, for every natural number $n$, a mathematical object $y_n$ is given, then the set of these objects can be written as:

$$\{y_0, y_1, y_2, \ldots\}$$

More generally, if $I$ is a set and if, for any $i \in I$, a mathematical object $x_i$ is given, then the set of these objects can be written as:

$$\{x_i \mid i \in I\}$$

where $I$ is called the **index set** of this roster writing. For example:
- $\{2n \mid n \in \mathbb{Z}\}$ denotes the set of all even numbers
- $\{2n + 1 \mid n \in \mathbb{Z}\}$ denotes the set of all odd numbers

### 2.1.3 Definition
Let $A$ and $B$ be sets. We denote by $A \times B$ the following set of ordered pairs:

$$A \times B = \{(x, y) \mid x \in A, y \in B\}$$

and call it the **Cartesian product** of sets $A$ and $B$.

More generally, if $n$ is a positive integer and $A_1, \ldots, A_n$ be sets, we denote by $A_1 \times \cdots \times A_n$ the set of all $n$-tuples $(x_1, \ldots, x_n)$, where $x_1 \in A_1, \ldots, x_n \in A_n$.

## 2.2 Subsets and powersets

### 2.2.1 Definition
Let $A$ and $B$ be sets. If any element of $A$ is an element of $B$, we say that $A$ is a **subset** of $B$. We denote by $A \subseteq B$ or by $B \supseteq A$ the statement "$A$ is a subset of $B$".

If $A$ is a subset of $B$ and $A$ is not equal to $B$, we say that $A$ is a **proper subset** of $B$, denoted by $A \subset B$ or by $B \supset A$.

If $A$ is a subset (resp. proper subset) of $B$, we also say that $A$ is **contained** (resp. **strictly contained**) in $B$, or that $B$ **contains** (resp. **contains strictly**) $A$.

### 2.2.2 Remark
By definition, any set $A$ is a subset of itself. Moreover, for any sets $A$ and $B$, if $A \subseteq B$ and $B \subseteq A$, then the sets $A$ and $B$ have the same elements, namely $A = B$.

### 2.2.3 Definition
We denote by $\emptyset$ the set that does not contain any element, and we call it the **empty set**. By definition, the empty set is a subset of any set.

### 2.2.4 Proposition
Let $A$, $B$ and $C$ be sets. If $A \subseteq B$ and $B \subseteq C$, then $A \subseteq C$.

*Proof.* Let $x$ be an element of $A$. Since $A \subseteq B$, $x$ is an element of $B$. Since $B \subseteq C$, $x$ is an element of $C$. Therefore, one has $A \subseteq C$.

### 2.2.5 Definition
Let $X$ be a set. We denote by $\mathcal{P}(X)$ the set of all subsets of $X$, called the **power set** of $X$. Note that $\{\emptyset, X\} \subseteq \mathcal{P}(X)$.

### 2.2.6 Example
The only subset of the empty set is itself, namely $\mathcal{P}(\emptyset) = \{\emptyset\}$.

Moreover, $\mathcal{P}(\{\emptyset\}) = \{\emptyset, \{\emptyset\}\}$.

## 2.3 Set-builder notation

### 2.3.1 Definition
Let $A$ be a set. If for any $x \in A$, we fix a statement $P(x)$, then we say that $P(\cdot)$ is a **condition** on $A$. For example, "$x$ is an odd number" is a condition on $\mathbb{Z}$. If $P(x)$ is true, then we say that $x$ **satisfies** the condition $P(\cdot)$.

Let $A$ be a set and $P(\cdot)$ be a condition on $A$. We denote by:

$$\{x \in A \mid P(x)\}$$

the set of elements $x \in A$ such that $P(x)$ is true. This is a subset of $A$. Such representation of a new set by a condition on a given set is called **set-builder notation**.

### 2.3.2 Notation
Sometimes we combine the roster notation and the set-builder notation to describe a set. Let $I$ be a set. For any $i \in I$, let $x_i$ be a mathematical object. Let $P(\cdot)$ be a condition on $I$, and $I_P$ be the set $\{i \in I \mid P(i)\}$. Then we use the expression:

$$\{x_i \mid i \in I, P(i)\}$$

to denote the set $\{x_i \mid i \in I_P\}$.

### 2.3.3 Example
In the set-builder notation, it is important to fix an environmental set. Without specifying an environmental set, the expression $\{x \mid P(x)\}$ may lead to paradoxes in certain cases.


---

## 2.4 Set difference

### 2.4.1 Definition
Let $A$ and $B$ be sets. Then the set:

$$B \setminus A := \{x \in B \mid x \notin A\}$$

is called the **set difference** of $B$ and $A$.

### 2.4.2 Example
Let $A$ be a set, $P(\cdot)$ be a condition on $A$. Then:

$$\{x \in A \mid P(x)\} = A \setminus \{x \in A \mid \neg P(x)\}$$

### 2.4.3 Proposition
Let $A$ and $B$ be sets. Then $B \setminus A = \emptyset$ if and only if $B \subseteq A$.

### 2.4.4 Proposition
Let $A$ and $B$ be sets. Then:

$$(A \setminus B) \cup (A \cap B) = A$$

$$(A \setminus B) \cap (A \cap B) = \emptyset$$

*Proof.* An element of $A$ either belongs to $B$ or does not belong to $B$. Therefore:

$$A = \{x \in A \mid x \in B\} \cup \{x \in A \mid x \notin B\} = (A \cap B) \cup (A \setminus B)$$

Since $x \in B$ and $x \notin B$ cannot hold at the same time, we have:

$$(A \cap B) \cap (A \setminus B) = \emptyset$$

## 2.5 Quantifiers

### 2.5.1 Definition
Let $A$ be a set and $P(\cdot)$ be a condition on $A$.

- The statement "$\forall x \in A, P(x)$" means "for every element $x$ of $A$, the statement $P(x)$ is true"
- The statement "$\exists x \in A, P(x)$" means "there exists an element $x$ of $A$ such that $P(x)$ is true"

The symbols $\forall$ and $\exists$ are called **quantifiers**. The first is called the **universal quantifier** and the second is called the **existential quantifier**.

### 2.5.2 Example
Let $P(\cdot)$ be any condition on the empty set $\emptyset$. Note that:

- "$\exists x \in \emptyset, P(x)$" is always **false**
- "$\forall x \in \emptyset, P(x)$" is always **true**

### 2.5.3 Proposition
(1) The statements "$\forall x \in A, P(x)$" and "$\{x \in A \mid \neg P(x)\} = \emptyset$" have the same truth value.

(2) The statements "$\exists x \in A, P(x)$" and "$\{x \in A \mid P(x)\} \neq \emptyset$" have the same truth value.

*Proof.* By Proposition 2.4.3, $\{x \in A \mid P(x)\} = A$ if and only if $\{x \in A \mid \neg P(x)\} = \emptyset$. 

Note that "$\forall x \in A, P(x)$" means "$\{x \in A \mid P(x)\} = A$", and "$\exists x \in A, P(x)$" means "$\{x \in A \mid P(x)\} \neq \emptyset$".

## 2.6 Sufficient and necessary conditions

### 2.6.1 Definition
Let $A$ be a set, $P(\cdot)$ and $Q(\cdot)$ be conditions on $A$. If:

$$\{x \in A \mid P(x)\} \subseteq \{x \in A \mid Q(x)\}$$

we say that $P(\cdot)$ is a **sufficient condition** of $Q(\cdot)$ on $A$, and that $Q(\cdot)$ is a **necessary condition** of $P(\cdot)$ on $A$.

### 2.6.2 Proposition
Let $A$ be a set, $P(\cdot)$ and $Q(\cdot)$ be conditions on $A$.

(1) $P(\cdot)$ is a sufficient condition of $Q(\cdot)$ if and only if:

$$\forall x \in A, (P(x) \Rightarrow Q(x))$$

(2) $P(\cdot)$ is a necessary condition of $Q(\cdot)$ if and only if:

$$\forall x \in A, (Q(x) \Rightarrow P(x))$$

(3) $P(\cdot)$ is both a sufficient and necessary condition of $Q(\cdot)$ if and only if:

$$\{x \in A \mid P(x)\} = \{x \in A \mid Q(x)\}$$

*Proof.* (1) By 2.4.3, $P(\cdot)$ is a sufficient condition of $Q(\cdot)$ if and only if:

$$\{x \in A \mid P(x)\} \setminus \{x \in A \mid Q(x)\} = \emptyset$$

This is equivalent to:

$$\{x \in A \mid P(x) \text{ and } \neg Q(x)\} = \emptyset$$

Namely, "$\forall x \in A, (P(x) \Rightarrow Q(x))$".

(2) Similar to (1).

(3) Follows from the definition of set equality.

## 2.7 Union

### 2.7.1 Definition
Let $I$ be a set. For any $i \in I$, let $A_i$ be a set. We say that the set $A$ is the **union** of $(A_i)_{i \in I}$ if:

$$A = \{x \mid \exists i \in I, x \in A_i\}$$

We denote:

$$A = \bigcup_{i \in I} A_i$$

### 2.7.2 Notation
Let $n$ be a positive integer, $A_1, \ldots, A_n$ be sets. We denote:

$$\bigcup_{i=1}^n A_i := A_1 \cup A_2 \cup \cdots \cup A_n$$

### 2.7.3 Proposition
Let $I$ be a set and $(A_i)_{i \in I}$ be a family of sets parametrised by $I$. Let $A = \bigcup_{i \in I} A_i$. Then:

(1) For any $i \in I$, one has $A_i \subseteq A$.

(2) If $B$ is a set such that $A_i \subseteq B$ for every $i \in I$, then $A \subseteq B$.

*Proof.* For any $i \in I$, if $x \in A_i$, then by definition $x \in A$. Hence $A_i \subseteq A$.

If $A_i \subseteq B$ for every $i \in I$, then for any $x \in A$, there exists $i \in I$ such that $x \in A_i \subseteq B$. Hence $x \in B$. Therefore $A \subseteq B$.

### 2.7.4 Corollary
Let $B$ and $I$ be sets. For any $i \in I$, let $P_i(\cdot)$ be a condition on $B$. Then:

$$\{x \in B \mid \exists i \in I, P_i(x)\} = \bigcup_{i \in I} \{x \in B \mid P_i(x)\}$$

### 2.7.5 Proposition
Let $(A_i)_{i \in I}$ be a family of sets, and $B$ be a set. Then:

$$\left(\bigcup_{i \in I} A_i\right) \setminus B = \bigcup_{i \in I} (A_i \setminus B)$$

$$B \setminus \left(\bigcup_{i \in I} A_i\right) = \bigcap_{i \in I} (B \setminus A_i)$$

## 2.8 Intersection

### 2.8.1 Definition
Let $I$ be a non-empty set and $(A_i)_{i \in I}$ be a family of sets parametrised by $I$. We say that the set $A$ is the **intersection** of $(A_i)_{i \in I}$ if:

$$A = \{x \mid \forall i \in I, x \in A_i\}$$

We denote:

$$A = \bigcap_{i \in I} A_i$$

### 2.8.2 Notation
Let $n$ be a positive integer, $A_1, \ldots, A_n$ be sets. We denote:

$$\bigcap_{i=1}^n A_i := A_1 \cap A_2 \cap \cdots \cap A_n$$

Therefore:

$$A \cap B = \{x \mid x \in A \text{ and } x \in B\}$$

### 2.8.3 Remark
In set theory, it does not make sense to consider the intersection of an empty family of sets. Indeed, if the index set $I$ were empty, the condition "$\forall i \in I, x \in A_i$" would be always true, leading to the set of all sets, which does not exist (Russell's paradox).

### 2.8.4 Proposition
Let $I$ be a non-empty set and $(A_i)_{i \in I}$ be a family of sets parametrised by $I$. Let $A = \bigcap_{i \in I} A_i$. Then:

(1) For any $i \in I$, one has $A \subseteq A_i$.

(2) If $B$ is a set such that $B \subseteq A_i$ for every $i \in I$, then $B \subseteq A$.

### 2.8.5 Corollary
Let $B$ be a set, $I$ be a non-empty set. For any $i \in I$, let $P_i(\cdot)$ be a condition on $B$. Then:

$$\{x \in B \mid \forall i \in I, P_i(x)\} = \bigcap_{i \in I} \{x \in B \mid P_i(x)\}$$

### 2.8.6 Proposition
Let $B$ be a set, $(A_i)_{i \in I}$ be a non-empty family of sets. Then:

$$\left(\bigcap_{i \in I} A_i\right) \setminus B = \bigcap_{i \in I} (A_i \setminus B)$$

$$B \setminus \left(\bigcap_{i \in I} A_i\right) = \bigcup_{i \in I} (B \setminus A_i)$$

### 2.8.7 Proposition
Let $I$ be a set and $(A_i)_{i \in I}$ be a family of sets parametrised by $I$. Let $B$ be a set. The following equalities hold:

(1) $B \cap \left(\bigcup_{i \in I} A_i\right) = \bigcup_{i \in I} (B \cap A_i)$

(2) $B \cup \left(\bigcap_{i \in I} A_i\right) = \bigcap_{i \in I} (B \cup A_i)$

(3) $\left(\bigcup_{i \in I} A_i\right)^c = \bigcap_{i \in I} A_i^c$

(4) $\left(\bigcap_{i \in I} A_i\right)^c = \bigcup_{i \in I} A_i^c$

*(De Morgan's laws for unions and intersections)*



---

# 3 Correspondences

## 3.1 Correspondence and its inverse

### 3.1.1 Definition
We call a **correspondence** any triplet of the form:

$$f = (D_f, A_f, \Gamma_f)$$

where $D_f$, $A_f$ are two sets, called respectively the **departure set** and the **arrival set** of $f$, and $\Gamma_f$ is a subset of $D_f \times A_f$, called the **graph** of $f$.

If $X$ and $Y$ are two sets and $f$ is a correspondence of the form $(X, Y, \Gamma_f)$, we say that $f$ is a correspondence from $X$ to $Y$.

### 3.1.2 Definition
Let $f$ be a correspondence. We denote by $f^{-1}$ the correspondence defined as follows:

- $D_{f^{-1}} := A_f$
- $A_{f^{-1}} := D_f$
- $\Gamma_{f^{-1}} := \{(y, x) \in A_f \times D_f \mid (x, y) \in \Gamma_f\}$

The correspondence $f^{-1}$ is called the **inverse correspondence** of $f$. Clearly:

$$(f^{-1})^{-1} = f$$

namely $f$ is the inverse correspondence of $f^{-1}$.

### 3.1.3 Example
Let $X$ be a set. Denote by $\Delta_X$ the following subset of $X \times X$:

$$\Delta_X = \{(x, x) \mid x \in X\}$$

called the **diagonal subset** of $X \times X$. The correspondence $(X, X, \Delta_X)$ is called the **identity correspondence** of $X$, denoted as $\text{Id}_X$. By definition, one has $\text{Id}_X^{-1} = \text{Id}_X$.

### 3.1.4 Example
Let $X$ and $Y$ be two sets. There is a correspondence from $X$ to $Y$ whose graph is the empty set. This correspondence is called the **empty correspondence** from $X$ to $Y$. Note that the inverse correspondence of the empty correspondence from $X$ to $Y$ is the empty correspondence from $Y$ to $X$.

## 3.2 Illustration of a correspondence

### 3.2.1 Remark
A correspondence can be viewed as an oriented graph. The elements of $D_f$ and $A_f$ are illustrated by two groups of vertices. For any ordered pair in the graph $\Gamma_f$, we link the corresponding vertices by an arrow.

The inverse correspondence $f^{-1}$ can be visualised by inverting the direction of the arrows.

### 3.2.2 Remark
We can also represent a correspondence $f$ by a table, whose rows are labelled by elements of $D_f$ and whose columns are labelled by elements of $A_f$. For each pair in $\Gamma_f$ we mark the cell of corresponding coordinates by a ✓.

Its inverse correspondence can be represented by the transposed table.

### 3.2.3 Remark
A correspondence from $\mathbb{R}$ to $\mathbb{R}$ can be illustrated by its graph in the coordinate plane.

## 3.3 Image and preimage

### 3.3.1 Definition
Let $X$ and $Y$ be sets, and $f$ be a correspondence from $X$ to $Y$.

If $(x, y)$ is an element of $\Gamma_f$, we say that $x$ is a **preimage** of $y$ under $f$, and $y$ is an **image** of $x$ under $f$.

If $A$ is a set, we denote by $f(A)$ the set:

$$f(A) = \{y \in A_f \mid \exists x \in A, (x, y) \in \Gamma_f\}$$

called the **image** of $A$ by the correspondence $f$.

If $B$ is a set, the set $f^{-1}(B)$ is called the **preimage** of $B$ by the correspondence $f$. Note that it is by definition the image of $B$ by the inverse correspondence $f^{-1}$.

### 3.3.2 Definition
Let $f$ be a correspondence. The set $f(D_f)$ is called the **range** of $f$, denoted as $\text{Im}(f)$. The set $f^{-1}(A_f)$ is called the **domain of definition** of $f$, denoted as $\text{Dom}(f)$.

Note that the domain of definition of a correspondence $f$ is the projection of the graph $\Gamma_f$ to the departure set $D_f$, and the range of a correspondence $f$ is the projection of the graph $\Gamma_f$ to the arrival set $A_f$.

For any sets $A$ and $B$:

$$f(A) \subseteq \text{Im}(f), \quad f^{-1}(B) \subseteq \text{Dom}(f)$$

Moreover:

$$\text{Dom}(f) = \text{Im}(f^{-1}), \quad \text{Im}(f) = \text{Dom}(f^{-1})$$

### 3.3.3 Example
The domain of definition and the range of a correspondence from $\mathbb{R}$ to $\mathbb{R}$ can both be $[-1, 1]$.

### 3.3.4 Proposition
Let $f$ be a correspondence.

(1) If $A$ and $A'$ are two sets such that $A' \subseteq A$, then $f(A') \subseteq f(A)$.

(2) If $B$ and $B'$ are two sets such that $B' \subseteq B$, then $f^{-1}(B') \subseteq f^{-1}(B)$.

### 3.3.5 Proposition
Let $f$ be a correspondence. The following equalities hold:

$$\text{Im}(f) = f(\text{Dom}(f)), \quad \text{Dom}(f) = f^{-1}(\text{Im}(f))$$

### 3.3.6 Proposition
Let $f$ be a correspondence.

(1) Let $A$ be a set and $y$ be a mathematical object. Then $y \in f(A)$ if and only if $A \cap f^{-1}(\{y\}) \neq \emptyset$.

(2) Let $B$ be a set and $x$ be a mathematical object. Then $x \in f^{-1}(B)$ if and only if $B \cap f(\{x\}) \neq \emptyset$.

### 3.3.7 Proposition
Let $f$ be a correspondence.

(1) Let $I$ be a set and $(A_i)_{i \in I}$ be a family of sets parametrised by $I$. Then:

$$f\left(\bigcup_{i \in I} A_i\right) = \bigcup_{i \in I} f(A_i)$$

Moreover, if $I$ is not empty, then:

$$f\left(\bigcap_{i \in I} A_i\right) \subseteq \bigcap_{i \in I} f(A_i)$$

(2) Let $I$ be a set and $(B_i)_{i \in I}$ be a family of sets parametrised by $I$. Then:

$$f^{-1}\left(\bigcup_{i \in I} B_i\right) = \bigcup_{i \in I} f^{-1}(B_i)$$

Moreover, if $I$ is not empty, then:

$$f^{-1}\left(\bigcap_{i \in I} B_i\right) = \bigcap_{i \in I} f^{-1}(B_i)$$

## 3.4 Composition

### 3.4.1 Definition
Let $f$ and $g$ be correspondences. We define the **composite** of $g$ and $f$ as the correspondence $g \circ f$ from $D_f$ to $A_g$ whose graph $\Gamma_{g \circ f}$ is composed of the elements $(x, z)$ of $D_f \times A_g$ such that there exists some object $y$ satisfying $(x, y) \in \Gamma_f$ and $(y, z) \in \Gamma_g$.

In other words:

$$\Gamma_{g \circ f} = \{(x, z) \in D_f \times A_g \mid \exists y \in A_f \cap D_g, (x, y) \in \Gamma_f \text{ and } (y, z) \in \Gamma_g\}$$

### 3.4.2 Proposition
Let $f$ and $g$ be correspondences. The following equality holds:

$$(g \circ f)^{-1} = f^{-1} \circ g^{-1}$$

### 3.4.3 Proposition
Let $f$, $g$ and $h$ be correspondences. The following equality holds:

$$h \circ (g \circ f) = (h \circ g) \circ f$$

(Associativity of composition)

### 3.4.4 Proposition
Let $X$ and $Y$ be sets, $f$ be a correspondence from $X$ to $Y$. Then:

$$f \circ \text{Id}_X = f = \text{Id}_Y \circ f$$

### 3.4.5 Proposition
Let $f$ and $g$ be correspondences.

(1) For any set $A$, $(g \circ f)(A) = g(f(A))$.

In particular, $\text{Im}(g \circ f) = g(\text{Im}(f)) \subseteq \text{Im}(g)$.

If in addition $\text{Dom}(g) \subseteq \text{Im}(f)$, then $\text{Im}(g \circ f) = \text{Im}(g)$.

(2) For any set $B$, $(g \circ f)^{-1}(B) = f^{-1}(g^{-1}(B))$.

In particular, $\text{Dom}(g \circ f) = f^{-1}(\text{Dom}(g)) \subseteq \text{Dom}(f)$.

If in addition $\text{Im}(f) \subseteq \text{Dom}(g)$, then $\text{Dom}(g \circ f) = \text{Dom}(f)$.

## 3.5 Surjectivity

### 3.5.1 Definition
Let $f$ be a correspondence. If $A_f = \text{Im}(f)$, we say that $f$ is **surjective**.

### 3.5.2 Proposition
Let $f$ be a correspondence.

(1) The correspondence $f$ is surjective if and only if $f \circ f^{-1} = \text{Id}_{A_f}$.

(2) If $f$ is surjective, then for any set $B$: $f(f^{-1}(B)) = B \cap A_f = B$.

### 3.5.3 Proposition
Let $f$ and $g$ be correspondences.

(1) If both $f$ and $g$ are surjective, and if $A_g = D_f$, then $g \circ f$ is surjective.

(2) If $g \circ f$ is surjective, then $g$ is surjective.

### 3.5.4 Proposition
Let $f$ and $g$ be correspondences.

If $g \circ f$ is defined and is surjective, and if $f$ is a mapping (see Definition 3.7.1), then $g$ is surjective.

## 3.6 Injectivity

### 3.6.1 Definition
Let $f$ be a correspondence. If each element of $D_f$ has at most one image under $f$, we say that $f$ is **injective**.

### 3.6.2 Remark
Functions form a special case of correspondences. The definition of injectivity for correspondences is consistent with that for functions.

### 3.6.3 Proposition
Let $f$ be a correspondence.

(1) $f$ is injective if and only if: for any set $A$, $f^{-1}(f(A)) \subseteq A$.

(2) If $f$ is injective, then for any set $A$: $f^{-1}(f(A)) = A \cap \text{Dom}(f)$.

### 3.6.4 Proposition
Let $f$ and $g$ be correspondences.

(1) If both $f$ and $g$ are injective, and if $A_g = D_f$, then $g \circ f$ is injective.

(2) If $g \circ f$ is injective, then $f$ is injective.

### 3.6.5 Proposition
Let $f$ and $g$ be correspondences.

If $g \circ f$ is defined and is injective, and if $g$ is a mapping, then $f$ is injective.

### 3.6.6 Proposition
Let $f$ be a correspondence, and $I$ be a non-empty set.

(1) For any family of sets $(B_i)_{i \in I}$:

$$f^{-1}\left(\bigcap_{i \in I} B_i\right) = \bigcap_{i \in I} f^{-1}(B_i)$$

(2) For any family of sets $(A_i)_{i \in I}$:

$$f\left(\bigcup_{i \in I} A_i\right) = \bigcup_{i \in I} f(A_i)$$

If moreover $f$ is injective, then:

$$f\left(\bigcap_{i \in I} A_i\right) = \bigcap_{i \in I} f(A_i)$$

## 3.7 Mappings

### 3.7.1 Definition
A correspondence $f$ is said to be a **mapping** if any element of $D_f$ has exactly one image under $f$. In other words, $f$ is a mapping if and only if it is both:
- Every element in $D_f$ has at least one image (total)
- Every element in $D_f$ has at most one image (injective as a correspondence)

### 3.7.2 Notation
Let $X$ and $Y$ be sets. We denote by $Y^X$ the set of all mappings from $X$ to $Y$.

### 3.7.3 Example
(1) Let $X$ be a set. The identity correspondence $\text{Id}_X$ is a mapping from $X$ to $X$, called the **identity mapping** of $X$.

(2) Let $X$ and $Y$ be sets. A correspondence from $X$ to $Y$ whose graph is empty is not a mapping unless $X = \emptyset$.

### 3.7.4 Remark
Let $f: X \to Y$ be a mapping, $I$ be a set.

(1) For any family of sets $(A_i)_{i \in I}$:

$$f\left(\bigcup_{i \in I} A_i\right) = \bigcup_{i \in I} f(A_i)$$

For any family of sets $(B_i)_{i \in I}$:

$$f^{-1}\left(\bigcup_{i \in I} B_i\right) = \bigcup_{i \in I} f^{-1}(B_i)$$

(2) If $I$ is non-empty:

$$f^{-1}\left(\bigcap_{i \in I} B_i\right) = \bigcap_{i \in I} f^{-1}(B_i)$$

For any family of sets $(B_i)_{i \in I}$:

$$f^{-1}\left(\bigcap_{i \in I} B_i\right) = \bigcap_{i \in I} f^{-1}(B_i)$$

(3) For any set $B$: $f(f^{-1}(B)) \subseteq B$. Since $\text{Dom}(f) = X$, for any subset $A$ of $X$: $A \subseteq f^{-1}(f(A))$. If $f$ is injective, $f^{-1}(f(A)) = A$.

### 3.7.5 Proposition
Let $f$ and $g$ be mappings. Suppose that $\text{Im}(f) \subseteq D_g$. Then the composite $g \circ f$ is also a mapping.

### 3.7.6 Remark
Let $f: X \to Y$ and $g: Y \to Z$ be mappings.

(1) If $f$ and $g$ are both surjective, so is $g \circ f$. If $g \circ f$ is surjective, so is $g$.

(2) If $f$ and $g$ are both injective, so is $g \circ f$. If $g \circ f$ is injective, so is $f$.

## 3.8 Bijection

### 3.8.1 Definition
Let $f$ be a mapping. If $f^{-1}$ is also a mapping, we say that $f$ is a **bijection** (or **bijective mapping**). A bijection from a set $X$ to itself is called a **permutation** of $X$.

### 3.8.2 Proposition
Let $X$ and $Y$ be sets, $f$ be a correspondence from $X$ to $Y$. Then $f$ is a bijection if and only if there exists a mapping $g: Y \to X$ such that $g \circ f = \text{Id}_X$ and $f \circ g = \text{Id}_Y$.

*Proof.* If $f$ is a bijection, then $f$ and $f^{-1}$ are both mappings. By Proposition 3.7.5, $f^{-1} \circ f$ and $f \circ f^{-1}$ are mappings. Since identity correspondences are mappings, we have $f^{-1} \circ f = \text{Id}_X$ and $f \circ f^{-1} = \text{Id}_Y$.

Conversely, if $g$ exists with these properties, then $f$ and $g$ are both surjective mappings. Since identity correspondences are surjective mappings, by Proposition 3.5.3, $f$ and $g$ are surjective. Since identity correspondences are injective, by Proposition 3.6.5, $f$ and $g$ are injective.

### 3.8.3 Proposition
Let $f: X \to Y$ and $g: Y \to Z$ be bijections. Then $g \circ f: X \to Z$ is also a bijection.

*Proof.* This is a direct consequence of Propositions 3.7.5, 3.6.4 and 3.5.4.

### 3.8.4 Proposition
Let $X$ and $Y$ be sets, $f$ be a correspondence from $X$ to $Y$. If $f$ is injective and surjective, then $f$ is a bijection.

## 3.9 Direct product

### 3.9.1 Definition
Let $I$ be a set and $(A_i)_{i \in I}$ be a family of sets parametrised by $I$. We denote by $\prod_{i \in I} A_i$ the set of all mappings $f$ from $I$ to $\bigcup_{i \in I} A_i$ such that $f(i) \in A_i$ for every $i \in I$. This set is called the **direct product** of $(A_i)_{i \in I}$.

### 3.9.2 Notation
Let $n$ be a non-zero natural number. If $(A_i)_{1 \leq i \leq n}$ is a family of sets, then:

$$\prod_{i=1}^n A_i = A_1 \times A_2 \times \cdots \times A_n$$

### 3.9.3 Axiom (Axiom of choice)
In this book, we adopt the following axiom: If $(A_i)_{i \in I}$ is a family of non-empty sets, then $\prod_{i \in I} A_i$ is also non-empty.

### 3.9.4 Proposition
Let $I$ be a set and $(A_i)_{i \in I}$ be a family of sets parametrised by $I$. Let $X$ be a set. The mapping:

$$X^{\prod_{i \in I} A_i} \longrightarrow \prod_{i \in I} X^{A_i}, \quad f \longmapsto (f_i)_{i \in I}$$

is bijective, where $f_i: A_i \to X$ is the mapping such that $f_i(a_i) = f((a_j)_{j \in I})$ with $a_j$ being a fixed element of $A_j$ for $j \neq i$.

## 3.10 Restriction and extension

### 3.10.1 Definition
Let $f$ and $g$ be correspondences. If $\Gamma_f \subseteq \Gamma_g$, we say that $f$ is a **restriction** of $g$, or that $g$ is an **extension** of $f$.

### 3.10.2 Proposition
Let $g$ be a correspondence.

(1) If $f$ is a restriction of $g$, then $D_f \subseteq D_g$ and $\text{Dom}(f) \subseteq \text{Dom}(g)$.

(2) If $f$ and $f'$ are both restrictions of $g$ with $D_f = D_{f'}$, then $f = f'$.

### 3.10.3 Definition
Let $X$ be a set and $A$ be a subset of $X$. The restriction of the identity correspondence $\text{Id}_X$ to $A \times X$ is called the **inclusion correspondence** from $A$ to $X$, denoted as $\iota_A: A \hookrightarrow X$.

## 3.11 Equivalence relation

### 3.11.1 Definition
Let $X$ be a set. We call **binary relation** on $X$ any correspondence $R$ from $X$ to $X$ such that $\text{Dom}(R) = X$.

Let $R$ be a binary relation on $X$:
- $R$ is **reflexive** if $(x, x) \in \Gamma_R$ for every $x \in X$
- $R$ is **symmetric** if $(x, y) \in \Gamma_R$ implies $(y, x) \in \Gamma_R$
- $R$ is **transitive** if $(x, y) \in \Gamma_R$ and $(y, z) \in \Gamma_R$ imply $(x, z) \in \Gamma_R$

A binary relation that is reflexive, symmetric, and transitive is called an **equivalence relation**.

### 3.11.2 Notation
We often denote an equivalence relation by the symbol $\sim$. We write $x \sim y$ instead of $(x, y) \in \Gamma_\sim$.

### 3.11.3 Definition
Let $X$ be a set and $\sim$ be an equivalence relation on $X$. For $x \in X$, the set:

$$[x]_\sim := \{y \in X \mid y \sim x\}$$

is called the **equivalence class** of $x$ under $\sim$.

### 3.11.4 Lemma
Let $X$ be a set and $\sim$ be a symmetric and transitive binary relation on $X$. Then:

(1) If $[x]_\sim \cap [y]_\sim \neq \emptyset$, then $[x]_\sim = [y]_\sim$.

(2) $x \sim y$ if and only if $[x]_\sim = [y]_\sim$.

### 3.11.5 Definition
Let $X$ be a set, $\sim$ be an equivalence relation on $X$. A subset $A$ of $X$ is called an **equivalence class** under $\sim$ if there exists $x \in X$ such that $A = [x]_\sim$.

### 3.11.6 Proposition
Let $X$ be a set and $\sim$ be an equivalence relation on $X$. Then:

$$X = \bigcup_{A \in X/\sim} A$$

where $X/\sim$ denotes the set of all equivalence classes under $\sim$.

*Proof.* By Lemma 3.11.4, two equivalence classes under $\sim$ are either disjoint or equal. Since every element $x \in X$ belongs to its equivalence class $[x]_\sim$, the equality holds.

### 3.11.7 Example
Let $p$ be a natural number. Consider the binary relation $\sim$ on $\mathbb{Z}$ defined by $x \sim y$ if $p$ divides $x - y$. This is an equivalence relation. When $p = 2$, there are two equivalence classes: the set of even integers and the set of odd integers.

### 3.11.8 Proposition
Let $X$ be a set, $\sim$ be an equivalence relation on $X$, and $\pi: X \to X/\sim$ be the canonical projection. Let $f: X \to Y$ be a mapping such that $x \sim x'$ implies $f(x) = f(x')$. Then there exists a unique mapping $\bar{f}: X/\sim \to Y$ such that $f = \bar{f} \circ \pi$.

### 3.11.9 Definition
Let $X$ be a set, $\sim$ be an equivalence relation on $X$, and $f: X \to Y$ be a mapping satisfying the condition in Proposition 3.11.8. The mapping $\bar{f}: X/\sim \to Y$ is said to be **induced** by $f$ by passing to the quotient.

### 3.11.10 Corollary
Let $f: X \to Y$ be a mapping of sets. The binary relation $\sim$ on $X$ defined by $x \sim x'$ if $f(x) = f(x')$ is an equivalence relation. The mapping $f$ induces by passing to quotient a mapping $\bar{f}: X/\sim \to Y$ which is injective, and $\text{Im}(\bar{f}) = \text{Im}(f)$.



---

# 4 Ordering

## 4.1 Partially ordered set

### 4.1.1 Definition
Let $X$ be a set and $R$ be a binary relation on $X$ (see Definition 3.11.1).

- If, for any $(x, y) \in X \times X$, $xRy$ and $yRx$ imply $x = y$, then $R$ is **antisymmetric**.
- If $R$ is reflexive, transitive, and antisymmetric, then $R$ is a **partial order** and $(X, R)$ is a **partially ordered set**.

If $R$ is a partial order on $X$, then its inverse correspondence is also a partial order on $X$.

Let $R$ be a partial order on $X$. If, for any $(x, y) \in X \times X$, $xRy$ or $yRx$ holds, then $R$ is a **total order** and $(X, R)$ is a **totally ordered set**.

### 4.1.2 Notation
Given a binary relation represented by a certain symbol, we often use the mirror-symmetric symbol to represent the inverse of this binary relation. For instance, if we use $\leq$ to represent a partial order, then $\geq$ represents the inverse of $\leq$.

### 4.1.3 Example
Let $X$ be a set, $\mathcal{P}(X)$ be the power set of $X$. Then the inclusion relation $\subseteq$ is a partial order on $\mathcal{P}(X)$.

### 4.1.4 Example
Consider a partially ordered set $(X, \leq)$ and let $A$ be a subset of $X$. The restriction of $\leq$ to $A$ defines a partial order on $A$, referred to as the **induced partial order** on $A$.

### 4.1.5 Proposition
Let $(X, \leq)$ be a partially ordered set. Define $<$ by:

$$\forall (x, y) \in X \times X, \quad x < y \text{ if and only if } (x \leq y \text{ and } x \neq y)$$

Then $<$ has the following properties:

(1) **Irreflexivity**: for any $x \in X$, $x < x$ does not hold.

(2) **Asymmetry**: for any $(x, y) \in X \times X$, if $x < y$, then $y < x$ does not hold.

(3) **Transitivity**: for any $x, y, z \in X$, if $x < y$ and $y < z$, then $x < z$.

### 4.1.6 Notation
Let $(X, \leq)$ be a partially ordered set. For $a \in X$:

$$X_{\leq a} = \{x \in X \mid x \leq a\}$$

$$X_{< a} = \{x \in X \mid x < a\}$$

### 4.1.7 Definition
We call **strict partial order** a binary relation which is irreflexive, asymmetric, and transitive. The relation $<$ in Proposition 4.1.5 is called the **strict partial order associated with** $\leq$.

## 4.2 Monotonic functions

### 4.2.1 Definition
Let $I$ and $X$ be partially ordered sets, $f$ be a function from $I$ to $X$.

(a) If for $a < b$ in $\text{Dom}(f)$, $f(a) \leq f(b)$, then $f$ is **increasing**.

(b) If for $a < b$ in $\text{Dom}(f)$, $f(a) < f(b)$, then $f$ is **strictly increasing**.

(c) If for $a < b$ in $\text{Dom}(f)$, $f(a) \geq f(b)$, then $f$ is **decreasing**.

(d) If for $a < b$ in $\text{Dom}(f)$, $f(a) > f(b)$, then $f$ is **strictly decreasing**.

A function is **monotonic** if it is either increasing or decreasing. If strictly increasing or strictly decreasing, it is **strictly monotonic**.

### 4.2.2 Example
Let $X$ be a partially ordered set, $A \subseteq X$ with induced partial order. The inclusion mapping $\iota_A: A \to X$ is strictly increasing.

### 4.2.3 Proposition
Let $f$ and $g$ be functions between partially ordered sets.

(1) If $f$ and $g$ are both increasing or both decreasing, then $g \circ f$ is increasing.

(2) If $f$ and $g$ are both strictly increasing or both strictly decreasing, then $g \circ f$ is strictly increasing.

(3) If one of $g$ and $f$ is increasing and the other is decreasing, then $g \circ f$ is decreasing.

(4) If one is strictly increasing and the other strictly decreasing, then $g \circ f$ is strictly decreasing.

### 4.2.4 Proposition
Let $I$ and $X$ be partially ordered sets, $f$ a function from $I$ to $X$.

(1) If $f$ is monotonic and injective, then it is strictly monotonic.

(2) If $I$ is totally ordered and $f$ is strictly monotonic, then it is injective.

### 4.2.5 Proposition
Let $X$ be a totally ordered set, $Y$ a partially ordered set, $f$ an injective function from $X$ to $Y$. If $f$ is monotonic, then so is $f^{-1}$. Moreover, $f^{-1}$ and $f$ have the same direction of monotonicity.

## 4.3 Supremum and infimum

### 4.3.1 Definition
Let $(X, \leq)$ be a partially ordered set, $A$ a subset of $X$.

(a) $M \in X$ is an **upper bound** of $A$ if $\forall x \in A, x \leq M$. If $A$ admits an upper bound in $Y \supseteq A$, $A$ is **bounded from above in $Y$**. If bounded from above in $A$, the unique upper bound in $A$ is $\max_{\leq} A$, the **greatest element** of $A$.

(b) $m \in X$ is a **lower bound** of $A$ if $\forall x \in A, m \leq x$. Similar definitions apply for bounded from below and $\min_{\leq} A$, the **least element**.

(c) $f: I \to X$ is **bounded from above/below** if $\text{Im}(f)$ is. If both, $f$ is **bounded**.

(d) If the set of upper bounds of $A$ in $Y$ has a least element, this is the **supremum** of $A$ in $Y$, denoted $\sup_{(Y, \leq)} A$.

(e) If the set of lower bounds of $A$ in $Y$ has a greatest element, this is the **infimum** of $A$ in $Y$, denoted $\inf_{(Y, \leq)} A$.

### 4.3.2 Notation
Let $(X, \leq)$ be a partially ordered set, $A, Y \subseteq X$ with $A \subseteq Y$. We denote:

- $A_Y^u$ = set of all upper bounds of $A$ in $Y$
- $A_Y^\ell$ = set of all lower bounds of $A$ in $Y$

When $Y = X$, we write $A^u$ and $A^\ell$.

We often abbreviate $\min_{\leq} A$, $\max_{\leq} A$, $\sup_{(X, \leq)} A$, $\inf_{(X, \leq)} A$ as $\min A$, $\max A$, $\sup A$, $\inf A$.

### 4.3.3 Notation
For a function $f: I \to X$ or family $(x_i)_{i \in I}$:

$$\max_{i \in I} f(i), \quad \min_{i \in I} f(i), \quad \sup_{i \in I} f(i), \quad \inf_{i \in I} f(i)$$

$$\max_{i \in I} x_i, \quad \min_{i \in I} x_i, \quad \sup_{i \in I} x_i, \quad \inf_{i \in I} x_i$$

### 4.3.4 Example
In $\mathbb{N}$ with usual order, $0$ is the least element but there is no greatest element.

### 4.3.5 Proposition
Let $(X, \leq)$ be a partially ordered set, $A, Z, Y \subseteq X$ with $A \subseteq Z \subseteq Y$.

(1) If $A$ has a greatest element, $\max A = \sup_{(Y, \leq)} A$.

(2) If $A$ has a least element, $\min A = \inf_{(Y, \leq)} A$.

(3) If $\sup_{(Y, \leq)} A \in Z$, then $\sup_{(Y, \leq)} A = \sup_{(Z, \leq)} A$.

(4) If $\inf_{(Y, \leq)} A \in Z$, then $\inf_{(Y, \leq)} A = \inf_{(Z, \leq)} A$.

### 4.3.6 Proposition
Let $(X, \leq)$ be a partially ordered set, $A, B, Y \subseteq X$ with $A \subseteq B \subseteq Y$.

(1) If both have suprema in $Y$: $\sup_{(Y, \leq)} A \leq \sup_{(Y, \leq)} B$.

(2) If both have infima in $Y$: $\inf_{(Y, \leq)} A \geq \inf_{(Y, \leq)} B$.

### 4.3.7 Proposition
Let $(X, \leq)$ be a partially ordered set, $f, g: I \to X$ with $f(t) \leq g(t)$ for all $t \in I$.

(1) If infima exist: $\inf_{t \in I} f(t) \leq \inf_{t \in I} g(t)$.

(2) If suprema exist: $\sup_{t \in I} f(t) \leq \sup_{t \in I} g(t)$.

### 4.3.8 Proposition
Let $I$ be totally ordered, $X$ partially ordered, $f: I \to X$, $J \subseteq I$ without upper bound in $I$.

(1) If $f$ is increasing: $f(I)^u = f(J)^u$.

(2) If $f$ is decreasing: $f(I)^\ell = f(J)^\ell$.

### 4.3.9 Proposition
Let $(X, \leq)$ be partially ordered, $Y \subseteq X$, $(A_i)_{i \in I}$ a family of subsets of $Y$, $A = \bigcup_{i \in I} A_i$.

(1) If each $A_i$ has supremum $y_i$ in $Y$:

$$A^u = \{y_i \mid i \in I\}^u$$

and $\sup_{(Y, \leq)} A = \sup_{(Y, \leq)} \{y_i \mid i \in I\}$.

(2) Similar for infima.

## 4.4 Intervals

### 4.4.1 Notation
Let $(X, \leq)$ be a totally ordered set. For $(a, b) \in X \times X$:

$$[a, b] = \{x \in X \mid a \leq x \leq b\}$$

Note $[a, b] = \emptyset$ when $a \not\leq b$.

### 4.4.2 Definition
Let $(X, \leq)$ be a partially ordered set, $I \subseteq X$. If for any $(x, y) \in I \times I$, $[x, y] \subseteq I$, then $I$ is an **interval** in $X$.

### 4.4.3 Example
For $(a, b) \in X \times X$:

$$]a, b[ := \{x \in X \mid a < x < b\}$$

$$[a, b[ := \{x \in X \mid a \leq x < b\}$$

$$]a, b] := \{x \in X \mid a < x \leq b\}$$

$$[a, b] := \{x \in X \mid a \leq x \leq b\}$$

All are intervals. Also:

$$X_{< a}, \quad X_{\leq a}, \quad X_{> a}, \quad X_{\geq a}$$

are intervals, and $X$ itself is an interval.

### 4.4.4 Proposition
Let $(X, \leq)$ be a partially ordered set, $(I_\alpha)_{\alpha \in \Lambda}$ a family of intervals.

(1) $\bigcap_{\alpha \in \Lambda} I_\alpha$ is an interval.

(2) If $(X, \leq)$ is totally ordered and $\bigcap_{\alpha \in \Lambda} I_\alpha \neq \emptyset$, then $\bigcup_{\alpha \in \Lambda} I_\alpha$ is an interval.

### 4.4.5 Definition
Let $(X, \leq)$ be a partially ordered set, $I$ a non-empty interval. If $I$ has a supremum in $X$, $\sup I$ is the **right endpoint**. If $I$ has an infimum, $\inf I$ is the **left endpoint**.

### 4.4.6 Proposition
Let $(X, \leq)$ be totally ordered, $I$ an interval.

(1) If $I$ has supremum $b$: $[x, b[ \subseteq I$ for any $x \in I$.

(2) If $I$ has infimum $a$: $]a, x] \subseteq I$ for any $x \in I$.

### 4.4.7 Proposition
Let $(X, \leq)$ be totally ordered, $I$ a non-empty interval with supremum $b$ and infimum $a$. Then $I$ equals one of: $[a, b]$, $]a, b]$, $[a, b[$, $]a, b[$.

### 4.4.8 Definition
Let $(X, \leq)$ be totally ordered. If for any $x < z$, there exists $y$ with $x < y < z$, then $(X, \leq)$ is **dense**.

### 4.4.9 Example
$(\mathbb{Q}, \leq)$ is dense. $(\mathbb{Z}, \leq)$ is not dense.

### 4.4.10 Proposition
Let $(X, \leq)$ be dense totally ordered, $a \leq b$. For any of the intervals $[a, b]$, $]a, b]$, $[a, b[$, $]a, b[$:

$$\inf I = a, \quad \sup I = b$$

## 4.5 Order-completeness

### 4.5.1 Definition
Let $(X, \leq)$ be a partially ordered set. If any subset has a supremum in $X$, $(X, \leq)$ is **order-complete**. An order-complete partially ordered set is never empty.

### 4.5.2 Proposition
Let $(X, \leq)$ be order-complete. Then any subset has an infimum. Moreover, $X$ has a greatest and a least element.

### 4.5.3 Example
$(\mathcal{P}(A), \subseteq)$ is order-complete:

$$\sup_{i \in I} A_i = \bigcup_{i \in I} A_i, \quad \inf_{i \in I} A_i = \bigcap_{i \in I} A_i \text{ (for } I \neq \emptyset\text{)}$$

### 4.5.4 Definition
Let $f: X \to X$. If $f(x) = x$, then $x$ is a **fixed point** of $f$.

### 4.5.5 Theorem (Knaster-Tarski Fixed Point Theorem)
Let $(X, \leq)$ be order-complete, $f: X \to X$ increasing. Then the set of fixed points $F = \{x \in X \mid f(x) = x\}$, with induced partial order, is order-complete. In particular, $f$ has at least one fixed point.

### 4.5.6 Theorem (Cantor-Bernstein)
Let $X$ and $Y$ be sets. If there exist injective mappings $X \to Y$ and $Y \to X$, then there exists a bijection $X \to Y$.

### 4.5.7 Lemma
Let $(X, \leq)$ be a partially ordered set.

(1) If $A \subseteq B$, then $B^u \subseteq A^u$ and $B^\ell \subseteq A^\ell$.

(2) For any $A \in \mathcal{P}(X)$: $A \subseteq (A^u)^\ell \cap (A^\ell)^u$.

### 4.5.8 Theorem (MacNeille Completion)
Let $(X, \leq)$ be a partially ordered set. Define:

$$\hat{X} := \{A \in \mathcal{P}(X) \mid (A^u)^\ell = A\}$$

(1) $(\hat{X}, \subseteq)$ is order-complete.

(2) For any $A \in \mathcal{P}(X)$: $A^\ell \in \hat{X}$.

(3) The mapping $X \to \hat{X}$, $x \mapsto \hat{x} := \{x\}^\ell$ is strictly increasing.

(4) For $A \in \hat{X}$: $A = \sup_{\hat{x} \in A} \hat{x}$.

(5) If $A^u = \emptyset$, then $A = X$; if $A^u \neq \emptyset$, then $A = \inf_{x \in A^u} \hat{x}$.

