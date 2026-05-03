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


### 14.6 Discontinuities of Distribution Functions

**Theorem 14.5 (One-sided limits).** For every real $a$,
$$
 \lim_{t\to a+}F(t)=F(a)\quad\text{(right-continuous)},\tag{14.2}
$$
$$
 \lim_{t\to a-}F(t)=F(a)-P(X=a).\tag{14.3}
$$
Hence $F$ has a jump discontinuity at $a$ of size $P(X=a)$.

*Proof sketch.* For $t>a$, $F(t)=F(a)+P(a<X\le t)$. For $t<a$, $F(t)=F(a)-P(t<X\le a)$. Set $p_n=P(a<X\le a+\frac1n)$ and $S_n=\{a+\frac1{n+1}<X\le a+\frac1n\}$. The $S_n$ are disjoint with union $\{a<X\le a+1\}$, so $\sum P(S_n)=p_1$. Since $p_n-p_{n+1}=P(S_n)$, the telescoping series gives $\lim p_n=0$, proving right continuity. A similar argument with $q_n=P(a-\frac1n<X<a)$ proves the left-limit formula.

**General characterisation.** Any real-valued function $F$ satisfying
- (a) monotone increasing,
- (b) right-continuous at each point,
- (c) $\displaystyle\lim_{t\to-\infty}F(t)=0$ and $\displaystyle\lim_{t\to+\infty}F(t)=1$,
is a distribution function of some random variable.

**Two main types.**
- **Discrete:** mass concentrated at a finite or countably infinite set of points (jump discontinuities).
- **Continuous:** mass smeared along an interval (no jumps, $P(X=a)=0$ for every $a$).


### 14.7 Discrete Distributions — Probability Mass Functions

**Probability mass function (pmf).** For a one-dimensional random variable $X$,
$$
 p(t)=P(X=t).
$$
The set of *mass points* $T=\{t\mid p(t)>0\}$ is finite or countable. $X$ is *discrete* iff $\sum_{t\in T}p(t)=1$.

**Theorem 14.6.** For any Borel set $A\subseteq\mathbb R$,
$$
 P(X\in A)=\sum_{x\in A\cap T}p(x).\tag{14.11}
$$
In particular the distribution function is
$$
 F(t)=P(X\le t)=\sum_{x\le t}p(x).
$$

**Example 1. Binomial distribution.** $X$ takes values $0,1,\dots,n$:
$$
 P(X=k)=\binom{n}{k}p^{k}q^{n-k}\quad(k=0,\dots,n),\qquad q=1-p.
$$
Then $\sum_{k=0}^{n}P(X=k)=(p+q)^{n}=1$ and
$$
 F_X(t)=\sum_{0\le k\le t}\binom{n}{k}p^{k}q^{n-k}.
$$

**Example 2. Poisson distribution.** $\lambda>0$; $X$ takes values $0,1,2,\dots$:
$$
 P(X=k)=\frac{e^{-\lambda}\lambda^{k}}{k!}\qquad(k=0,1,2,\dots).
$$
Then $\sum_{k=0}^{\infty}P(X=k)=e^{-\lambda}e^{\lambda}=1$ and
$$
 F_X(t)=e^{-\lambda}\sum_{0\le k\le t}\frac{\lambda^{k}}{k!}.
$$


### 14.9 Continuous Distributions — Density Functions

If $P(X=t)=0$ for every real $t$, then $F$ is continuous everywhere; $F$ is called a **continuous distribution** and $X$ a **continuous random variable**.

If $F'$ exists and is continuous on $[a,t]$,
$$
 F(t)-F(a)=\int_a^t f(u)\,du\qquad(f=F').\tag{14.13}
$$

**Definition.** A nonnegative integrable function $f$ is a **probability density function (pdf)** of $X$ (or of $F$) provided
$$
 F(t)-F(a)=\int_a^t f(u)\,du\quad\text{for all }[a,t].\tag{14.14}
$$
Consequences:
- $F(t)=\displaystyle\int_{-\infty}^t f(u)\,du$, $\;\;\forall t$.\tag{14.15}
- $\displaystyle\int_{-\infty}^{+\infty}f(u)\,du=1$.\tag{14.16}
- For any interval,
  $$
  P(a\le X\le b)=P(a<X<b)=P(a<X\le b)=P(a\le X<b)=\int_a^b f(u)\,du.
  $$

**Note.** A distribution may have many densities (finite-point changes do not alter the integral). If $f$ is continuous at $t$, then $f(t)=F'(t)$ and the density is uniquely determined there.

---

### 14.10 Uniform Distribution over an Interval

$X$ has a **uniform distribution** on $[a,b]$ iff
$$
 F(t)=\begin{cases}
 0 & t\le a,\\[4pt]
 \dfrac{t-a}{\,b-a\,} & a<t<b,\\[8pt]
 1 & t\ge b.
 \end{cases}
$$
Its density is
$$
 f(t)=\begin{cases}
 \dfrac{1}{b-a} & a<t<b,\\[6pt]
 0 & \text{otherwise}.
 \end{cases}
$$

**Theorem 14.7.** Let $X$ take values only in $[a,b]$. Then $F$ is uniform on $[a,b]$ **iff**
$$
 P(X\in I)=P(X\in J)\tag{14.17}
$$
for every pair of subintervals $I,J\subseteq[a,b]$ of the same length; in that case $P(X\in I)=h/(b-a)$ where $h=|I|$.

*Proof sketch.* If $F$ is uniform, $P(c\le X\le c+h)=F(c+h)-F(c)=h/(b-a)$.  
Conversely, set $g(u)=P(a<X\le a+u)$ for $0<u\le b-a$.  Property (14.17) gives $g(u+v)=g(u)+g(v)$, so by Theorem 14.8 below, $g(u)=u/(b-a)$; hence $F(t)-F(a)=(t-a)/(b-a)$ and $F$ is uniform. ∎

**Theorem 14.8 (Solution of Cauchy’s functional equation).** Let $g$ be real-valued on $(0,c]$, nonnegative, and satisfy $g(u+v)=g(u)+g(v)$ whenever $u,v,u+v\in(0,c]$. Then
$$
 g(u)=\frac{u}{c}\,g(c)\qquad(0<u\le c).
$$

*Proof sketch.* Scale to $G(x)=g(cx)$ on $(0,1]$. Then $G(x+y)=G(x)+G(y)$. By induction $G(x)=nG(x/n)$ and $G(rx)=rG(x)$ for positive rationals $r$. Monotonicity (from nonnegativity) and rational approximation give $G(x)=xG(1)$ for all $x\in(0,1]$. Rescaling yields the formula. ∎

**Example.** A segment $[0,1]$ is broken at a uniformly chosen point; $X$ is the ratio of the left piece to the right piece. With $Y(\omega)=\omega$ uniform on $[0,1]$ and $X(\omega)=\omega/(1-\omega)$,
$$
 F_X(t)=P\!\left(Y\le\frac{t}{1+t}\right)=\frac{t}{1+t}\qquad(t\ge0).
$$
(For $t<0$, $F_X(t)=0$.)  Particular values: $P(X\le\tfrac12)=\tfrac13$, $P(X\ge2)=\tfrac13$.


### 14.11 Cauchy’s Distribution

$X$ has a **Cauchy distribution** iff
$$
 F(t)=\frac12+\frac1\pi\arctan t,\qquad\forall t\in\mathbb R.
$$
Its continuous density is
$$
 f(t)=\frac{1}{\pi(1+t^2)}.
$$

**Physical derivation.** A pointer pivoted at $(-1,0)$ is spun; the angle $\theta$ (uniform on $(-\tfrac12\pi,\tfrac12\pi]$) determines the line. The $y$‑intercept is $Y=\tan\theta$.  Let $a<t$, set $\alpha=\arctan a$, $\theta=\arctan t$.  Then
$$
 F_Y(t)-F_Y(a)=P(a<Y\le t)=P(\alpha<X\le\theta)=\int_\alpha^\theta\frac{du}{\pi}=\frac{\theta-\alpha}{\pi}.
$$
Letting $a\to-\infty$ ($\alpha\to-\tfrac12\pi$) gives $F_Y(t)=\dfrac{\theta+\tfrac12\pi}{\pi}=\dfrac12+\dfrac1\pi\arctan t$, confirming the Cauchy distribution.


### 14.13 Exponential Distributions

Let $\lambda>0$.  $X$ has an **exponential distribution** with parameter $\lambda$ if
$$
 F(t)=\begin{cases}
 1-e^{-\lambda t} & t\ge0,\\[4pt]
 0 & t<0,
 \end{cases}\qquad
 f(t)=\begin{cases}
 \lambda e^{-\lambda t} & t\ge0,\\[4pt]
 0 & t<0.
 \end{cases}
$$

**Memoryless (characteristic) property.** For $t,s>0$,
$$
 P(X>t+s\mid X>t)=\frac{P(X>t+s)}{P(X>t)}=\frac{e^{-\lambda(t+s)}}{e^{-\lambda t}}=e^{-\lambda s}=P(X>s).
$$
In terms of $F$,
$$
 \frac{1-F(t+s)}{1-F(t)}=1-F(s)\qquad(t,s>0).\tag{14.23}
$$

**Theorem 14.9.** If a distribution function $F$ satisfies (14.23) and $F(t)<1$ for all $t>0$, then $F(t)=1-e^{-\lambda t}$ for some $\lambda>0$.

*Proof sketch.* Set $g(t)=-\log[1-F(t)]$ ($t>0$).  Then $g$ is nonnegative and satisfies Cauchy’s equation $g(t+s)=g(t)+g(s)$.  By Theorem 14.8, $g(t)=tg(1)$ on $(0,1]$; put $\lambda=g(1)>0$.  The function $G(t)=g(t)-\lambda t$ also satisfies Cauchy’s equation and has period $1$, so $G\equiv0$ on $(0,1]$ forces $G\equiv0$ for all $t>0$.  Hence $g(t)=\lambda t$ and $F(t)=1-e^{-\lambda t}$. ∎

**Example 1 (Vacuum-tube lifetime).** $X$ exponential with $\lambda=0.001$.  Find $T$ with $P(X>T)=0.95$:
$$
 e^{-\lambda T}=0.95\quad\Longrightarrow\quad T=-\frac{\log0.95}{\lambda}\approx51.25\text{ hours}.
$$

**Example 2 (Half-life).** If $g(t)$ tubes survive out of $g(0)$, the model $\frac{g(0)-g(t)}{g(0)}=1-e^{-\lambda t}$ gives $g(t)=g(0)e^{-\lambda t}$.  The half-life $t_1$ satisfies $\tfrac12=e^{-\lambda t_1}$, so $\lambda=\frac{\log2}{t_1}$.


### 14.14 Normal Distributions

$X$ is **normal** with mean $m$ and variance $\sigma^{2}$ ($\sigma>0$) if
$$
 f(t)=\frac{1}{\sigma\sqrt{2\pi}}\,e^{-[(t-m)/\sigma]^{2}/2},\qquad
 F(t)=\frac{1}{\sigma\sqrt{2\pi}}\int_{-\infty}^{t}e^{-[(u-m)/\sigma]^{2}/2}\,du.
$$

**Standard normal.** The case $m=0$, $\sigma=1$ is denoted $\Phi$:
$$
 \Phi(t)=\frac{1}{\sqrt{2\pi}}\int_{-\infty}^{t}e^{-u^{2}/2}\,du.
$$
By the change of variable $v=(u-m)/\sigma$,
$$
 F(t)=\Phi\!\left(\frac{t-m}{\sigma}\right).
$$

**Normal approximation to the binomial (de Moivre–Laplace).** If $X\sim\operatorname{Bin}(n,p)$ and $q=1-p$,
$$
 \sum_{k=a}^{b}\binom{n}{k}p^{k}q^{n-k}
 \sim\Phi\!\left(\frac{b-np+\tfrac12}{\sqrt{npq}}\right)
 -\Phi\!\left(\frac{a-np-\tfrac12}{\sqrt{npq}}\right).\tag{14.25}
$$
The symbol $\sim$ means the ratio of the two sides $\to1$ as $n\to\infty$; this is a special case of the **central limit theorem**.  In practice the sum is replaced by the integral of the normal density over $[a-\tfrac12,\,b+\tfrac12]$.


### 14.15 Remarks on More General Distributions

A distribution function $F$ is called **mixed** if it is a convex combination of a discrete and a continuous distribution:
$$
 F(t)=c_{1}F_{1}(t)+c_{2}F_{2}(t),\tag{14.26}
$$
where $F_{1}$ is discrete, $F_{2}$ is continuous, $0<c_{1},c_{2}<1$, and $c_{1}+c_{2}=1$.

- Discrete case $\to$ summation of the pmf.
- Continuous case $\to$ integration of the pdf.
- Mixed case $\to$ use linearity (14.26).

A unified theoretical treatment of all three cases is provided by the **Riemann–Stieltjes integral**; for the most general distributions one needs the **Lebesgue–Stieltjes integral**.


### 14.17 Distributions of Functions of Random Variables

Let $Y=\varphi(X)$.  If $\varphi$ is continuous and strictly increasing on $\mathbb R$ with inverse $\psi$, then
$$
 F_{Y}(t)=P\bigl(\varphi(X)\le t\bigr)=P\bigl(X\le\psi(t)\bigr)=F_{X}\bigl[\psi(t)\bigr].\tag{14.27}
$$
Differentiating gives the density relation
$$
 f_{Y}(t)=f_{X}\bigl[\psi(t)\bigr]\,\psi'(t).
$$

**Example 1 (Linear change).** $Y=aX+b$ ($a>0$):
$$
 F_{Y}(t)=F_{X}\!\left(\frac{t-b}{a}\right),\qquad
 f_{Y}(t)=\frac1a\,f_{X}\!\left(\frac{t-b}{a}\right).
$$

**Example 2 ($Y=X^{2}$).** For $t<0$, $F_{Y}(t)=0$.  For $t>0$,
$$
 F_{Y}(t)=P(-\sqrt{t}\le X\le\sqrt{t})=F_{X}(\sqrt{t})-F_{X}(-\sqrt{t})
$$
(continuous case), and
$$
 f_{Y}(t)=\frac{f_{X}(\sqrt{t})+f_{X}(-\sqrt{t})}{2\sqrt{t}}\qquad(t>0).
$$


### 14.19 Distributions of Two-Dimensional Random Variables

For random variables $X,Y$ on a common sample space, the pair $(X,Y)$ is a **two-dimensional random variable**.

**Definition (Joint distribution function).**
$$
 F(a,b)=P(X\le a,\;Y\le b),\qquad\forall a,b\in\mathbb R.
$$

**Theorem 14.10.** If $a<b$ and $c<d$,
$$
 P(a<X\le b,\;c<Y\le d)=F(b,d)-F(a,d)-F(b,c)+F(a,c).\tag{14.28}
$$

*Proof sketch.* Decompose the rectangle $(-\infty,b]\times(-\infty,d]$ into four disjoint pieces (see Figure 14.13); adding their probabilities yields the formula. ∎

**Mass analogy.** Total mass $1$ is spread over the plane.  The discrete case concentrates mass at a finite or countable set of points; the continuous case smears it with a density.


### 14.20 Two-Dimensional Discrete Distributions

**Joint pmf.** $p(x,y)=P(X=x,Y=y)$.  The set $T=\{(x,y)\mid p(x,y)>0\}$ is finite or countable.  $(X,Y)$ is *discrete* iff
$$
 \sum_{(x,y)\in T}p(x,y)=1.\tag{14.29}
$$
Writing $p_{ij}=P(X=x_i,Y=y_j)$,
$$
 P\bigl[(X,Y)\in E\bigr]=\sum_{\substack{x_i,y_j\\(x_i,y_j)\in E}}p_{ij},\qquad
 F(x,y)=\sum_{x_i\le x}\sum_{y_j\le y}p_{ij}.\tag{14.30}
$$

**Marginal distributions.**
$$
 P(X=x_i)=\sum_{j=1}^{\infty}p_{ij},\qquad
 P(Y=y_j)=\sum_{i=1}^{\infty}p_{ij}.\tag{14.31–14.32}
$$

---

### 14.21 Two-Dimensional Continuous Distributions — Density Functions

**Joint pdf.** A nonnegative integrable $f$ is a *joint density* of $(X,Y)$ if
$$
 P\bigl[(X,Y)\in Q\bigr]=\iint_{Q}f\qquad\text{for suitable regions }Q.\tag{14.33}
$$
For a rectangle $R=[a,b]\times[c,d]$,
$$
 P(a<X\le b,\;c<Y\le d)=\iint_{R}f(x,y)\,dx\,dy
 =\int_{c}^{d}\!\int_{a}^{b}f\,dx\,dy.\tag{14.34}
$$

**Distribution function and normalization.**
$$
 F(b,d)=\int_{-\infty}^{d}\!\int_{-\infty}^{b}f(x,y)\,dx\,dy,\qquad
 \int_{-\infty}^{+\infty}\!\int_{-\infty}^{+\infty}f(x,y)\,dx\,dy=1.\tag{14.35–14.36}
$$
At points of continuity, $f(x,y)=D_{1,2}F(x,y)=D_{2,1}F(x,y)$.

**Marginal densities.**
$$
 f_{X}(x)=\int_{-\infty}^{+\infty}f(x,y)\,dy,\qquad
 f_{Y}(y)=\int_{-\infty}^{+\infty}f(x,y)\,dx.
$$

**Independence.** $X$ and $Y$ are *independent* iff
$$
 F(x,y)=F_{X}(x)\,F_{Y}(y)\quad\forall x,y.
$$

**Example (Uniform on $[0,1]^{2}$).** $f=1$ on $R=[0,1]^{2}$, $0$ elsewhere.  Then $F(x,y)=xy$ on $R$, and $X,Y$ are independent.


### 14.23 Distributions of Functions of Two Random Variables

Let $U=M(X,Y)$, $V=N(X,Y)$ with a one-to-one $C^{1}$ change of variables
$$
 u=M(x,y),\quad v=N(x,y),\qquad x=Q(u,v),\quad y=R(u,v).
$$
For any region $T$ in the $xy$‑plane with image $T'$ in the $uv$‑plane,
$$
 P\bigl[(U,V)\in T'\bigr]=P\bigl[(X,Y)\in T\bigr].\tag{14.37}
$$
Hence the joint density $g$ of $(U,V)$ is
$$
 g(u,v)=f\bigl[Q(u,v),R(u,v)\bigr]\,\biggl|\frac{\partial(Q,R)}{\partial(u,v)}\biggr|.\tag{14.39}
$$
Marginal densities are obtained by integrating $g$.

**Example 1 (Sum and difference).** $U=X+Y$, $V=X-Y$; inverse $x=\tfrac{u+v}{2}$, $y=\tfrac{u-v}{2}$, Jacobian $-\tfrac12$.  Thus
$$
 f_{X+Y}(u)=\int_{-\infty}^{\infty}f(x,\,u-x)\,dx,\qquad
 f_{X-Y}(v)=\int_{-\infty}^{\infty}f(x,\,x-v)\,dx.
$$
If $X,Y$ are independent ($f(x,y)=f_{X}(x)f_{Y}(y)$), these become the **convolution** formulas
$$
 f_{X+Y}(u)=\int_{-\infty}^{\infty}f_{X}(x)\,f_{Y}(u-x)\,dx.
$$

**Example 2 (Sum of two independent exponentials).** $f_{X}(t)=\lambda e^{-\lambda t}$, $f_{Y}(t)=\mu e^{-\mu t}$ ($t\ge0$).  For $u\ge0$,
$$
 f_{X+Y}(u)=\lambda\mu e^{-\mu u}\int_{0}^{u}e^{(\mu-\lambda)x}\,dx
 =\begin{cases}
 \lambda^{2}u\,e^{-\lambda u} & (\mu=\lambda),\\[6pt]
 \displaystyle\lambda\mu\,\frac{e^{-\lambda u}-e^{-\mu u}}{\mu-\lambda} & (\mu\neq\lambda).
 \end{cases}
$$
(For $u<0$, $f_{X+Y}(u)=0$.)

**Example 3 (Max and min of independent variables).** $U=\max\{X,Y\}$, $V=\min\{X,Y\}$.  Then
$$
 F_{U}(t)=F_{X}(t)\,F_{Y}(t),\qquad
 F_{V}(t)=F_{X}(t)+F_{Y}(t)-F_{X}(t)\,F_{Y}(t).
$$
Differentiating,
$$
 f_{U}=f_{X}F_{Y}+F_{X}f_{Y},\qquad
 f_{V}=f_{X}+f_{Y}-f_{X}F_{Y}-F_{X}f_{Y}.
$$

