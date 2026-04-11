# 1 Basic Logic

The purpose of this chapter is to introduce the mathematical logic language used throughout the book, including the fundamentals of propositional logic and predicate logic. By studying this chapter, students will master the basic methods of mathematical reasoning, laying a solid foundation for learning algebra and analysis.

## 1.1 Mathematical statements

### 1.1.1 Definition
We call **statement** a declarative sentence without free variable in a given mathematical theory, whose truth value (that is, true or false) can in principle be determined. In a consistent mathematical theory, any statement is either true or false, but cannot be true and false in the same time.

### 1.1.2 Example
- "2 is an even number" is a **true** statement
- "1 > 2" is a **false** statement

### 1.1.3 Example
- "$1+2$" is a computational formula, it is **not a statement**
- The inequality "$2x + 1 > 0$" contains a free variable $x$, so judging its truth value is meaningless. Therefore, it is **not a statement**

In this book, we use the symbol $:=$ to interpret the notation on the left hand side of the symbol as the expression on the right hand side. For example, "$a := 3+5$" means that we denote by $a$ the value of $3+5$. This expression is not a statement.

### 1.1.4 Definition
In a mathematical theory, statements admitted as true without justification are called the **axioms**. All statements that can be rigorously deduced from axioms are true. A statement that is confirmed to be true through rigorous mathematical proof is called a **theorem**. A statement that can be deduced from a theorem via straightforward reasoning is usually referred to as a **corollary** of that theorem.

In mathematical literature, a statement is often called a **proposition**. In this book, the term "proposition" is rather used to label theorems that are relatively simple or not repeatedly applied in the book.

### 1.1.5 Remark
Some mathematical conjectures have neither been proved nor disproved. However, these conjectures have similar forms with the statements the truth values of which have been determined. In principle the truth values of these conjectures could be determined in the future. They should be classified as statements. Furthermore, there exist declarative sentences that are neither provable nor disprovable within a certain mathematical theory. However, in an enriched axiomatic mathematical theory, their truth values can be in principle determined. Such declarative sentences should also be recognised as statements in the enriched mathematical theory.

## 1.2 Negation

Starting from given statements, compound statements can be constructed through the syntax of construction. This section introduces the negation of statements.

### 1.2.1 Definition
Let $P$ be a statement. Then the sentence "not $P$" is also a statement, called the **negation** of $P$. It has the opposite true value of that of $P$. Sometimes we denote the statement "not $P$" as $\neg P$.

### 1.2.2 Notation
When a statement is expressed by a linking verb of judgement, its negation can be expressed by negating the linking verb. For example, the negation of the statement "2 is an even number" can be expressed as "2 is not an even number".

If a statement is expressed as a relation linked by a relation symbol, its negation could be expressed by overlaying the relation symbol with a diagonal line from the upper right to the lower left. For example, the negation of "$1 > 2$" can be expressed as "$1 \not> 2$".

### 1.2.3 Remark
The double negation of a statement $P$ has the same truth value as that of the statement $P$. This point can be seen by the table of truth values as follows, where T stands for "true" and F stands for "false".

| $P$ | $\neg P$ | $\neg\neg P$ |
|:---:|:---------:|:------------:|
|  T  |     F     |       T      |
|  F  |     T     |       F      |

## 1.3 Conjunction and disjunction

### 1.3.1 Definition
Let $P$ and $Q$ be statements. Then "$P$ and $Q$" is a statement, called the **conjunction** of $P$ and $Q$, often denoted as $P \wedge Q$. When both $P$ and $Q$ are true, the statement $P \wedge Q$ is true, otherwise it is false.

Similarly, the sentence "$P$ or $Q$" is a statement, called the **disjunction** of $P$ and $Q$, often denoted as $P \vee Q$. When both $P$ and $Q$ are false, the statement $P \vee Q$ is false, otherwise it is true.

### 1.3.2 Remark
We describe the truth values of conjunction and disjunction in the following table.

| $P$ | $Q$ | $P \wedge Q$ | $P \vee Q$ | $Q \wedge P$ | $Q \vee P$ |
|:---:|:---:|:------------:|:-----------:|:------------:|:-----------:|
|  T  |  T  |       T      |      T      |       T      |      T      |
|  T  |  F  |       F      |      T      |       F      |      T      |
|  F  |  T  |       F      |      T      |       F      |      T      |
|  F  |  F  |       F      |      F      |       F      |      F      |

We observe from the table that $P \wedge Q$ and $Q \wedge P$ have the same truth value, and $P \vee Q$ and $Q \vee P$ have the same truth value.

### 1.3.3 Proposition (De Morgan's Laws)
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

### 1.4.1 Definition
Let $P$ and $Q$ be statements. The sentence "if $P$, then $Q$" is a statement, often denoted as $P \Rightarrow Q$. It has the same truth value as that of $(\neg P) \vee Q$. A statement of this form is called a **conditional statement**. We describe its true value in the following table.

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
