[<- Previous: 3. Continuous Functions](03-continuous-functions.md) | [Next: 5. The Relation between Integration and Differentiation ->](05-the-relation-between-integration-and-differentiation.md)

# 4. Differential Calculus

## 4.1 Historical Introduction

- **Newton and Leibniz** independently fused **integral calculus** with **differential calculus**.
- The central concept is the **derivative**, originally arising from the geometric problem of finding **tangent lines**.
- **Fermat** (early 17th century) observed that at maxima/minima, the tangent is **horizontal**; this idea generalized to finding the tangent at any point, leading to the derivative.
- **Barrow** first realized the intimate relation between area (integral) and tangent (derivative); **Newton and Leibniz** fully exploited it.

## 4.2 A Problem Involving Velocity

### 4.2.1 The Projectile Model

- A projectile is fired straight up from the ground with initial velocity $144\ \text{ft/s}$.
- Neglect friction; gravity is the only force.
- Height at time $t$:
  $$
  f(t) = 144t - 16t^2, \qquad 0 \le t \le 9.
  $$
- $f(0)=0$ and $f(9)=0$: the projectile returns to earth after $9$ seconds.

### 4.2.2 Average Velocity 鈥?The Difference Quotient

- Average velocity over $[t, t+h]$:
  $$
  \frac{f(t+h)-f(t)}{h}.
  $$
- **Example ($t=2$)**:
  - $f(2)=224$.
  - $f(2+h)=224+80h-16h^2$.
  - Average velocity $= \dfrac{80h-16h^2}{h}=80-16h$.
  - As $|h|$ gets smaller, this approaches $80$.

### 4.2.3 Instantaneous Velocity

- For general $t$:
  $$
  \frac{f(t+h)-f(t)}{h} = 144 - 32t - 16h.
  $$
- Letting $h \to 0$:
  $$
  v(t) = \lim_{h\to 0}\frac{f(t+h)-f(t)}{h} = 144 - 32t.
  $$

### 4.2.4 Properties of the Velocity Function

| Quantity | Value |
|----------|-------|
| Initial velocity | $v(0)=144$ |
| Final velocity | $v(9)=-144$ |
| Zero velocity | $v(t)=0$ at $t=\dfrac{9}{2}$ |
| Max height | $f\left(\dfrac{9}{2}\right)=324$ |

- $t < \dfrac{9}{2}$: $v(t)>0$ (rising).
- $t > \dfrac{9}{2}$: $v(t)<0$ (falling).

### 4.2.5 General Definition

- For any position function $f$, the **instantaneous velocity** is:
  $$
  v(t) = \lim_{h\to 0}\frac{f(t+h)-f(t)}{h},
  $$
  provided the limit exists.

## 4.3 The Derivative of a Function

### 4.3.1 Definition of the Derivative

- Let $f$ be defined on an open interval $(a,b)$.
- For a fixed $x$ in $(a,b)$ and $h \neq 0$, the **difference quotient** is:
  $$
  \frac{f(x+h)-f(x)}{h}.
  $$
- This measures the **average rate of change** of $f$ over $[x, x+h]$.
- The **derivative of $f$ at $x$** is the limit:
  $$
  f'(x) = \lim_{h\to 0}\frac{f(x+h)-f(x)}{h},
  $$
  provided the limit exists.
- If the limit exists, $f$ is **differentiable at $x$**.
- If $f$ is differentiable at every $x$ in $(a,b)$, then $f$ is **differentiable on $(a,b)$**.

### 4.3.2 The Derived Function and Notations

- The function $f'$ assigns to each $x$ the value $f'(x)$; it is called the **derived function** or **derivative** of $f$.
- Domain of $f'$: the set of $x$ in $(a,b)$ where the limit exists.
- **Notations**:
  - $f'(x)$, $y'$ (Lagrange)
  - $Df(x)$, $Dy$ (Cauchy)
  - $\dfrac{df(x)}{dx}$, $\dfrac{dy}{dx}$ (Leibniz)
- **Leibniz notation**: Write $\Delta y = f(x+h)-f(x)$ and $\Delta x = h$, so the difference quotient is $\dfrac{\Delta y}{\Delta x}$. As $\Delta x \to 0$, this approaches $f'(x)$, denoted $\dfrac{dy}{dx}$.
- **Caution**: $\dfrac{dy}{dx}$ is a single symbol, not a quotient of $dy$ and $dx$.

### 4.3.3 Differentiation and Higher-Order Derivatives

- The limit process producing $f'(x)$ from $f(x)$ is called **differentiation**.
- $f'$ is the **first derivative** of $f$.
- If $f'$ is differentiable, its derivative is the **second derivative**, denoted $f''$.
- Inductively, the **$n$th derivative** $f^{(n)}$ is the first derivative of $f^{(n-1)}$.
- Convention: $f^{(0)} = f$ (the zeroth derivative is the function itself).

### 4.3.4 Velocity and Acceleration

- For rectilinear motion with position function $f$:
  - **Velocity**: $v(t) = f'(t)$
  - **Acceleration**: $a(t) = v'(t) = f''(t)$
- **Example** (projectile from Section 4.2): $f(t) = 144t - 16t^2$, $v(t) = 144 - 32t$.
  $$
  \frac{v(t+h)-v(t)}{h} = \frac{-32h}{h} = -32.
  $$
  Hence $a(t) = -32\ \text{ft/s}^2$ (constant).
  - Velocity decreases by $32\ \text{ft/s}$ each second.
  - In 9 seconds the total decrease is $288\ \text{ft/s}$, matching $v(0)=144$ to $v(9)=-144$.

## 4.4 Examples of Derivatives

### 4.4.1 Constant Function

- Let $f(x) = c$.
- Difference quotient:
  $$
  \frac{f(x+h)-f(x)}{h} = \frac{c-c}{h} = 0.
  $$
- Derivative:
  $$
  f'(x) = \lim_{h\to 0}0 = 0.
  $$
- **Result**: The derivative of a constant function is $0$ everywhere.

### 4.4.2 Linear Function

- Let $f(x) = mx + b$.
- Difference quotient:
  $$
  \frac{m(x+h)+b-(mx+b)}{h} = \frac{mh}{h} = m.
  $$
- **Result**:
  $$
  f'(x) = m \quad \text{for every } x.
  $$
- The derivative of a linear function is a constant function.

### 4.4.3 Positive Integer Powers

- Let $f(x)=x^n$ for a positive integer $n$.
- Using the identity $a^n-b^n=(a-b)\sum_{k=0}^{n-1}a^k b^{n-1-k}$ with $a=x+h$, $b=x$:
  $$
  \frac{(x+h)^n-x^n}{h} = \sum_{k=0}^{n-1}(x+h)^k x^{n-1-k}.
  $$
- As $h\to 0$, each of the $n$ terms approaches $x^{n-1}$.
- **Result**:
  $$
  (x^n)' = nx^{n-1}, \qquad n\in\mathbb{Z}^+.
  $$

### 4.4.4 The Sine Function

- Let $s(x)=\sin x$.
- Using $\sin y - \sin x = 2\sin\dfrac{y-x}{2}\cos\dfrac{y+x}{2}$ with $y=x+h$:
  $$
  \frac{\sin(x+h)-\sin x}{h} = \frac{\sin(h/2)}{h/2}\,\cos\left(x+\frac{h}{2}\right).
  $$
- As $h\to 0$: $\dfrac{\sin(h/2)}{h/2}\to 1$ and $\cos\left(x+\dfrac{h}{2}\right)\to\cos x$.
- **Result**:
  $$
  (\sin x)' = \cos x.
  $$

### 4.4.5 The Cosine Function

- Let $c(x)=\cos x$.
- Using $\cos y - \cos x = -2\sin\dfrac{y-x}{2}\sin\dfrac{y+x}{2}$ with $y=x+h$:
  $$
  \frac{\cos(x+h)-\cos x}{h} = -\frac{\sin(h/2)}{h/2}\,\sin\left(x+\frac{h}{2}\right).
  $$
- As $h\to 0$: $\dfrac{\sin(h/2)}{h/2}\to 1$ and $\sin\left(x+\dfrac{h}{2}\right)\to\sin x$.
- **Result**:
  $$
  (\cos x)' = -\sin x.
  $$

### 4.4.6 The $n$th-Root Function

- Let $f(x)=x^{1/n}$ for $x>0$, $n\in\mathbb{Z}^+$.
- Set $u=(x+h)^{1/n}$, $v=x^{1/n}$. Then $u^n-v^n=h$, and:
  $$
  \frac{u-v}{h} = \frac{1}{u^{n-1}+u^{n-2}v+\dots+v^{n-1}}.
  $$
- As $h\to 0$, $u\to v$, so the denominator tends to $nv^{n-1}$.
- **Result**:
  $$
  \left(x^{1/n}\right)' = \frac{1}{n}x^{1/n-1}, \qquad x>0.
  $$

### 4.4.7 Differentiability Implies Continuity

- **Theorem**: If $f$ has a derivative at $x$, then $f$ is continuous at $x$.
- **Proof sketch**: Write
  $$
  f(x+h) = f(x) + h\cdot\frac{f(x+h)-f(x)}{h}.
  $$
  As $h\to 0$, the difference quotient approaches $f'(x)$ and $h\to 0$, so $f(x+h)\to f(x)$.
- **Converse is false**: Continuity does not imply differentiability.
  - **Counterexample**: $f(x)=|x|$ is continuous at $0$ but not differentiable there, since
    $$
    \frac{|h|}{h} = \begin{cases} +1 & h>0 \\ -1 & h<0 \end{cases}
    $$
    has no limit as $h\to 0$.

## 4.5 The Algebra of Derivatives

### 4.5.1 Theorem 4.1 鈥?Basic Rules

- Let $f$ and $g$ be differentiable on a common interval.
- Then $f\pm g$, $f\cdot g$, and $f/g$ (where $g\neq 0$) are also differentiable, and:
  1. **Sum/Difference**:
     $$
     (f\pm g)' = f' \pm g'.
     $$
  2. **Product rule**:
     $$
     (fg)' = f g' + f' g.
     $$
  3. **Quotient rule** (at points where $g(x)\neq 0$):
     $$
     \left(\frac{f}{g}\right)' = \frac{g f' - f g'}{g^2}.
     $$

### 4.5.2 Linearity

- **Special case of product rule**: $(cf)' = c f'$ for any constant $c$.
- Combined with the sum rule:
  $$
  (c_1 f + c_2 g)' = c_1 f' + c_2 g'.
  $$
- By induction, for any finite sum:
  $$
  \left(\sum_{i=1}^{n} c_i f_i\right)' = \sum_{i=1}^{n} c_i f_i'.
  $$

### 4.5.3 Proof Sketches

- **Sum rule**: The difference quotient for $f+g$ splits into the sum of the two difference quotients; each tends to the respective derivative.
- **Product rule**: Add and subtract $g(x)f(x+h)$ in the numerator:
  $$
  \frac{f(x+h)g(x+h)-f(x)g(x)}{h} = g(x)\frac{f(x+h)-f(x)}{h} + f(x+h)\frac{g(x+h)-g(x)}{h}.
  $$
  As $h\to 0$: the first term $\to g(x)f'(x)$; by continuity $f(x+h)\to f(x)$, so the second term $\to f(x)g'(x)$.
- **Quotient rule**: First prove the special case
  $$
  \left(\frac{1}{g}\right)' = -\frac{g'}{g^2},
  $$
  then apply the product rule to $f\cdot(1/g)$.

### 4.5.4 Differentiating Polynomials

- Using linearity and $(x^n)'=nx^{n-1}$, differentiate any polynomial term by term:
  $$
  f(x)=\sum_{k=0}^{n}c_k x^k \quad\Longrightarrow\quad f'(x)=\sum_{k=0}^{n}k c_k x^{k-1}.
  $$
- The derivative of a degree-$n$ polynomial is a degree-$(n-1)$ polynomial.
- **Example**: $f(x)=2x^3+5x^2-7x+8 \Rightarrow f'(x)=6x^2+10x-7$.

### 4.5.5 Rational Functions

- If $r(x)=p(x)/q(x)$ with $p,q$ polynomials, apply the quotient rule wherever $q(x)\neq 0$.
- **Special case** ($r(x)=1/x^m$, $m\in\mathbb{Z}^+$, $x\neq 0$):
  $$
  r'(x)=-\frac{m}{x^{m+1}}=-m x^{-m-1}.
  $$
- This extends the power rule from positive to **negative integer exponents**.

### 4.5.6 Rational Powers

- **Theorem**: For any rational number $r$ and $x>0$:
  $$
  (x^r)' = r x^{r-1}.
  $$
- Already proved for $r=1/n$ (Section 4.4.6).
- Extend to $r=m/n$ by induction using the product rule.
- Extend to negative rationals using the quotient rule.
- **Examples**:
  - $f(x)=x^{2/3} \Rightarrow f'(x)=\frac{2}{3}x^{-1/3}$
  - $f(x)=x^{-1/2} \Rightarrow f'(x)=-\frac{1}{2}x^{-3/2}$

## 4.6 Geometric Interpretation of the Derivative as a Slope

### 4.6.1 Difference Quotient and Secant Slope

- The difference quotient
  $$
  \frac{f(x+h)-f(x)}{h}
  $$
  is the slope of the secant line through $P=(x,f(x))$ and $Q=(x+h,f(x+h))$.
- It equals $\tan\alpha$, where $\alpha$ is the angle the secant makes with the horizontal.

### 4.6.2 Derivative as Tangent Slope

- As $h\to 0$, the point $Q$ moves toward $P$ along the curve, and the secant line approaches a limiting position.
- This limiting line is the **tangent line** at $P$.
- The derivative $f'(x)$ is the **slope of the tangent line** at $(x,f(x))$:
  $$
  \text{slope of tangent} = f'(x) = \lim_{h\to 0}\frac{f(x+h)-f(x)}{h}.
  $$
- If $f'(x)$ exists, the curve has a **uniquely determined tangent line** at that point.
- The angle $\theta$ between the tangent line and the positive $x$-axis satisfies:
  $$
  \tan\theta = f'(x).
  $$

### 4.6.3 Equation of the Tangent Line

- The tangent line at $(x, f(x))$ has equation:
  $$
  Y - f(x) = f'(x)(X - x),
  $$
  where $(X, Y)$ denotes a variable point on the line.
- This is the **point鈥搒lope form** using the derivative as the slope.

### 4.6.4 Parallel and Perpendicular Lines

- Two nonvertical lines are **parallel** if and only if they have the same slope.
- Two nonvertical lines are **perpendicular** if and only if the product of their slopes is $-1$.
- These follow from the identities:
  $$
  \tan(\alpha-\beta)=\frac{\tan\alpha-\tan\beta}{1+\tan\alpha\tan\beta}, \qquad
  \cot(\alpha-\beta)=\frac{1+\tan\alpha\tan\beta}{\tan\alpha-\tan\beta}.
  $$

### 4.6.5 Sign of the Derivative

- $f'(x)>0$ on an interval: graph is **rising** (moving left to right).
- $f'(x)<0$ on an interval: graph is **falling**.
- $f'(x)=0$: **horizontal tangent**.
- At a local **maximum or minimum**, if the derivative exists, it must be zero: $f'(x)=0$.
- **Caution**: $f'(x)=0$ does not guarantee a max or min (e.g., inflection points).

## 4.7 Other Notations for Derivatives

- **Lagrange**: $f'(x),\; y',\; y'',\; y^{(n)}$.
- **Newton**: $\dot{y},\; \ddot{y}$ (dots, still used for velocity/acceleration).
- **Arbogast / Cauchy**: $Df,\; D^2f,\; D^nf$; $D$ is the **differentiation operator**.
- **Leibniz**: $\dfrac{dy}{dx}$. He regarded it as a quotient of **infinitesimals** $dy$ and $dx$.
  - This view was later replaced by the rigorous limit definition (Cauchy).
  - **Non-standard analysis** (Robinson, 1966) gave a consistent foundation for infinitesimals.

## 4.8 The Chain Rule for Differentiating Composite Functions

### 4.8.1 Composite Functions

- If $u$ and $v$ are functions with the domain of $u$ containing the range of $v$, the **composite function** $f=u\circ v$ is defined by:
  $$
  f(x) = u[v(x)].
  $$

### 4.8.2 The Chain Rule (Theorem 4.2)

- Let $f=u\circ v$. Suppose $v'(x)$ and $u'(y)$ exist, where $y=v(x)$.
- Then $f'(x)$ exists and:
  $$
  f'(x) = u'(y)\cdot v'(x) = u'[v(x)]\cdot v'(x).
  $$
- In function notation:
  $$
  (u\circ v)' = (u'\circ v)\cdot v'.
  $$
- In $u(v)$-notation:
  $$
  u(v)' = u'(v)\cdot v'.
  $$

### 4.8.3 Proof Sketch

- Let $y=v(x)$ and $k=v(x+h)-v(x)$. Then $v(x+h)=y+k$ and:
  $$
  \frac{f(x+h)-f(x)}{h} = \frac{u(y+k)-u(y)}{h}.
  $$
- **Naive approach** (valid when $k\neq 0$): multiply and divide by $k$:
  $$
  \frac{u(y+k)-u(y)}{k}\cdot\frac{k}{h} \to u'(y)\cdot v'(x) \quad (h\to 0).
  $$
- **Rigorous fix** (when $k$ may be $0$): define
  $$
  g(t) = \frac{u(y+t)-u(y)}{t} - u'(y) \quad (t\neq 0),
  $$
  with $g(0)=0$ so that $g$ is continuous at $0$. Then
  $$
  u(y+t)-u(y) = t[g(t)+u'(y)].
  $$
  Setting $t=k$ and substituting gives a formula valid even when $k=0$, yielding the same limit $u'(y)\cdot v'(x)$.

## 4.9 Applications of the Chain Rule: Related Rates and Implicit Differentiation

### 4.9.1 The Chain Rule in Leibniz Notation

- Let $y=v(x)$ and $z=u(y)=u[v(x)]=f(x)$.
- Then
  $$
  \frac{dz}{dx} = \frac{dz}{dy}\cdot\frac{dy}{dx}.
  $$
- This makes the chain rule look like a trivial algebraic cancellation of $dy$.

### 4.9.2 Related Rates

- **Problem**: A gas is pumped into a spherical balloon at $50\ \text{cm}^3/\text{s}$. How fast is the radius increasing when $r=5\ \text{cm}$?
- **Solution**:
  - $V=\frac{4}{3}\pi r^3$, so $\dfrac{dV}{dr}=4\pi r^2$.
  - By the chain rule:
    $$
    \frac{dV}{dt} = \frac{dV}{dr}\cdot\frac{dr}{dt} = 4\pi r^2\frac{dr}{dt}.
    $$
  - Substituting $dV/dt=50$ and $r=5$:
    $$
    \frac{dr}{dt} = \frac{1}{2\pi}\ \text{cm/s}.
    $$
- **Key point**: It is not necessary to express $r$ as an explicit function of $t$.

### 4.9.3 Differentiating Powers of a Function

- If $f(x)=[v(x)]^n$ with $n\in\mathbb{Z}^+$, then by the chain rule:
  $$
  f'(x) = n[v(x)]^{n-1}v'(x).
  $$
- In function notation:
  $$
  (v^n)' = n v^{n-1} v'.
  $$
- Valid also for **rational** powers whenever $v^n$ and $v^{n-1}$ are defined.
- **Example**: $f(x)=\sin(x^2)$. Let $v(x)=x^2$, $u(x)=\sin x$. Then
  $$
  f'(x)=\cos(x^2)\cdot 2x.
  $$

### 4.9.4 Implicit Differentiation

- The equation $x^2+y^2=r^2$ defines $y$ **implicitly** as a function of $x$ (actually two functions: upper and lower semicircles).
- Instead of solving for $y$, differentiate both sides with respect to $x$, remembering that $y$ is a function of $x$:
  $$
  2x + 2yy' = 0 \quad\Longrightarrow\quad y' = -\frac{x}{y}\quad (y\neq 0).
  $$
- This is **implicit differentiation**.
- Geometric meaning: at $(x,y)$ on the circle, the tangent slope is $-x/y$, while the radius slope is $y/x$; their product is $-1$, so the tangent is perpendicular to the radius.

## 4.10 Applications of Differentiation to Extreme Values of Functions

### 4.10.1 Absolute and Relative Extrema

- **Absolute maximum** on a set $S$: $f(x) \le f(c)$ for all $x \in S$.
- **Relative maximum** at $c \in S$: there exists an open interval $I$ containing $c$ such that
  $$
  f(x) \le f(c) \quad \text{for all } x \in I \cap S.
  $$
- **Relative minimum**: reverse the inequality.
- A **relative maximum** at $c$ is an absolute maximum in some neighborhood of $c$, but not necessarily on all of $S$.
- Every absolute maximum is, in particular, a relative maximum.
- An **extremum** (or extreme value) is either a relative maximum or a relative minimum.

### 4.10.2 Theorem 4.3 鈥?Vanishing of the Derivative at an Interior Extremum

- Let $f$ be defined on an open interval $I$ and have a relative maximum or minimum at an interior point $c \in I$.
- **If $f'(c)$ exists, then $f'(c)=0$**.
- **Proof sketch**: Define
  $$
  Q(x) = \frac{f(x)-f(c)}{x-c}\quad (x\neq c), \qquad Q(c)=f'(c).
  $$
  Then $Q$ is continuous at $c$. If $Q(c)=f'(c)\gt0$, the sign-preserving property gives $f(x)\gt f(c)$ for $x\gt c$ near $c$, contradicting the extremum. Similarly $Q(c)\lt0$ is impossible. Hence $Q(c)=0$, i.e. $f'(c)=0$.

### 4.10.3 Important Caveats

1. **$f'(c)=0$ does NOT imply an extremum at $c$**.
   - **Example**: $f(x)=x^3$ has $f'(0)=0$, but $0$ is not an extremum (the function is increasing through $0$).
2. **An extremum may occur where $f'(c)$ does not exist**.
   - **Example**: $f(x)=|x|$ has a relative minimum at $0$, but $f'(0)$ does not exist (sharp corner).
3. **Theorem 4.3 requires the derivative to exist** at the interior extremum. In the absence of sharp corners, the derivative must vanish at an interior extremum.

## 4.11 The Mean-Value Theorem for Derivatives

### 4.11.1 Rolle's Theorem (Theorem 4.4)

- Let $f$ be continuous on $[a,b]$ and differentiable on $(a,b)$.
- If $f(a)=f(b)$, then there exists at least one $c\in(a,b)$ such that
  $$
  f'(c)=0.
  $$
- **Geometric meaning**: If the endpoints have the same height, the curve has a horizontal tangent somewhere between them.
- **Proof sketch**: If $f'(x)\neq 0$ everywhere in $(a,b)$, then by the extreme-value theorem both extrema must occur at the endpoints. Since $f(a)=f(b)$, this forces $f$ to be constant, contradicting $f'(x)\neq 0$.

### 4.11.2 Mean-Value Theorem (Theorem 4.5)

- Let $f$ be continuous on $[a,b]$ and differentiable on $(a,b)$.
- Then there exists at least one $c\in(a,b)$ such that
  $$
  f(b)-f(a)=f'(c)(b-a),
  $$
  or equivalently
  $$
  \frac{f(b)-f(a)}{b-a}=f'(c).
  $$
- **Geometric meaning**: There is at least one point where the tangent line is parallel to the chord joining $(a,f(a))$ and $(b,f(b))$.
- **Physical interpretation**: The instantaneous speed at some moment equals the average speed over the interval.
- **Proof**: Apply Rolle's theorem to
  $$
  h(x)=f(x)(b-a)-x[f(b)-f(a)].
  $$
  Then $h(a)=h(b)$ and $h'(x)=f'(x)(b-a)-[f(b)-f(a)]$. Setting $h'(c)=0$ yields the result.
- **Note**: The theorem makes no assertion about the exact location of $c$, only that at least one such point exists somewhere in $(a,b)$.
- **Caution**: The conclusion may fail if $f$ is not differentiable at even one interior point.
  - **Example**: $f(x)=|x|$ on $[-1,2]$ is continuous and has derivative everywhere except $0$. The slope of the chord is $\frac{1}{3}$, but $f'(x)$ is never $\frac{1}{3}$.

### 4.11.3 Cauchy's Mean-Value Formula (Theorem 4.6)

- Let $f$ and $g$ be continuous on $[a,b]$ and differentiable on $(a,b)$.
- Then there exists $c\in(a,b)$ such that
  $$
  f'(c)[g(b)-g(a)] = g'(c)[f(b)-f(a)].
  $$
- **Proof**: Apply Rolle's theorem to
  $$
  h(x)=f(x)[g(b)-g(a)]-g(x)[f(b)-f(a)].
  $$
- The ordinary mean-value theorem is the special case with $g(x)=x$.

## 4.12 Applications of the Mean-Value Theorem to Geometric Properties

### 4.12.1 Monotonicity (Theorem 4.7)

- Let $f$ be continuous on $[a,b]$ and differentiable on $(a,b)$.
- **(a)** If $f'(x)>0$ for all $x\in(a,b)$, then $f$ is **strictly increasing** on $[a,b]$.
- **(b)** If $f'(x)<0$ for all $x\in(a,b)$, then $f$ is **strictly decreasing** on $[a,b]$.
- **(c)** If $f'(x)=0$ for all $x\in(a,b)$, then $f$ is **constant** on $[a,b]$.
- **Proof of (a)**: For $x<y$ in $[a,b]$, apply the mean-value theorem on $[x,y]$:
  $$
  f(y)-f(x)=f'(c)(y-x),\quad x<c<y.
  $$
  Since $f'(c)>0$ and $y-x>0$, we get $f(y)>f(x)$. Parts (b) and (c) are similar.

### 4.12.2 First-Derivative Test for Extrema (Theorem 4.8)

- Let $f$ be continuous on $[a,b]$ and differentiable on $(a,b)$ except possibly at $c$.
- **(a)** If $f'(x)>0$ for $x<c$ and $f'(x)<0$ for $x>c$ (sign changes from $+$ to $-$), then $f$ has a **relative maximum** at $c$.
- **(b)** If $f'(x)<0$ for $x<c$ and $f'(x)>0$ for $x>c$ (sign changes from $-$ to $+$), then $f$ has a **relative minimum** at $c$.
- **Proof of (a)**: By Theorem 4.7(a), $f$ is strictly increasing on $[a,c]$ and strictly decreasing on $[c,b]$. Hence $f(x)<f(c)$ for all $x\neq c$ in $(a,b)$.
- **Geometric meaning**: An extremum occurs whenever the derivative changes sign (Figure 4.12).

## 4.13 Second-Derivative Test for Extrema

### 4.13.1 Critical Points

- By the extreme-value theorem, a continuous function on $[a,b]$ attains its absolute max and min somewhere in $[a,b]$.
- If $f$ is differentiable at each interior point, extrema can occur only at:
  1. The **endpoints** $a$ and $b$;
  2. **Interior points** where $f'(x)=0$.
- Points of type (2) are called **critical points** of $f$.
- To decide whether a critical point is a max, min, or neither, study the sign of $f'$ near $c$, or use the second derivative.

### 4.13.2 Second-Derivative Test (Theorem 4.9)

- Let $c$ be a critical point of $f$ in $(a,b)$, so $f'(c)=0$.
- Assume $f''$ exists in $(a,b)$.
- **(a)** If $f''(x)<0$ in $(a,b)$, then $f$ has a **relative maximum** at $c$.
- **(b)** If $f''(x)>0$ in $(a,b)$, then $f$ has a **relative minimum** at $c$.
- **Proof of (a)**: If $f''<0$ in $(a,b)$, then by Theorem 4.7 applied to $f'$, the derivative $f'$ is strictly decreasing on $(a,b)$. Since $f'(c)=0$, $f'$ changes from positive to negative at $c$. By Theorem 4.8, $f$ has a relative maximum at $c$.
- **Practical version**: If $f''$ is continuous at $c$ and $f''(c)\neq 0$, then $f''$ has the same sign as $f''(c)$ in a neighborhood of $c$. Thus:
  - $f''(c)<0$ and $f'(c)=0$ $\Rightarrow$ relative maximum at $c$.
  - $f''(c)>0$ and $f'(c)=0$ $\Rightarrow$ relative minimum at $c$.

### 4.13.3 Convexity (Theorem 4.10)

- The sign of $f''$ also governs the **convexity** or **concavity** of $f$.
- **Theorem 4.10**: Assume $f$ is continuous on $[a,b]$ and differentiable on $(a,b)$.
  - If $f'$ is increasing on $(a,b)$, then $f$ is **convex** on $[a,b]$.
  - In particular, if $f''$ exists and is **nonnegative** in $(a,b)$, then $f$ is convex.
- **Proof sketch**: Take $x<y$ in $[a,b]$ and let $z=\alpha y+(1-\alpha)x$ with $0<\alpha<1$. Apply the mean-value theorem twice on $[x,z]$ and $[z,y]$ to get
  $$
  f(z)-f(x)=f'(c)(z-x),\quad f(y)-f(z)=f'(d)(y-z),
  $$
  with $x<c<z<d<y$. Since $f'$ is increasing, $f'(c)\le f'(d)$. Using $(1-\alpha)(z-x)=\alpha(y-z)$, this yields the convexity inequality
  $$
  f(z)\le\alpha f(y)+(1-\alpha)f(x).
  $$

## 4.14 Curve Sketching

### 4.14.1 General Procedure

1. Determine the **domain** and (if easy) the **range**.
2. Find **intercepts**:
   - $y$-intercept: $(0, f(0))$ (if $0$ is in the domain)
   - $x$-intercepts: solutions of $f(x)=0$
3. Determine **monotonicity** by the sign of $f'$.
4. Determine **convexity/concavity** by the sign of $f''$.
5. Locate points with **horizontal tangents** ($f'=0$).
6. Identify **asymptotes**.

### 4.14.2 Asymptotes

- A nonvertical line $y=mx+b$ is an **asymptote** if
  $$
  f(x)-(mx+b)\to 0 \quad \text{as } x\to\pm\infty.
  $$
- A vertical line $x=a$ is a **vertical asymptote** if $|f(x)|\to\infty$ as $x\to a$ from either side.

### 4.14.3 Example 1: $f(x)=x+\dfrac{1}{x}$ ($x\neq 0$)

- No intercepts on either axis.
- Derivatives:
  $$
  f'(x)=1-\frac{1}{x^2}, \qquad f''(x)=\frac{2}{x^3}.
  $$
- $f'(x)=0$ at $x=\pm 1$: relative **minimum** at $x=1$, relative **maximum** at $x=-1$.
- $f''(x)>0$ for $x>0$ (convex); $f''(x)<0$ for $x<0$ (concave).
- As $x\to 0$, behaves like $y=1/x$; the $y$-axis is a **vertical asymptote**.
- As $|x|\to\infty$, behaves like $y=x$; the line $y=x$ is an **asymptote**.
- $f$ is odd: $f(-x)=-f(x)$, so the graph is symmetric about the origin.

### 4.14.4 Example 2: $f(x)=\dfrac{1}{x^2+1}$

- Even function, positive for all $x$; the $x$-axis is a **horizontal asymptote**.
- Derivatives:
  $$
  f'(x)=\frac{-2x}{(x^2+1)^2}, \qquad
  f''(x)=\frac{2(3x^2-1)}{(x^2+1)^3}.
  $$
- $f'(x)<0$ for $x>0$, $f'(x)>0$ for $x<0$, $f'(0)=0$: **relative maximum** at $x=0$.
- $f''(x)>0$ if $3x^2>1$ (convex); $f''(x)<0$ if $3x^2<1$ (concave).
- **Points of inflection** at $x^2=\dfrac{1}{3}$, i.e. $x=\pm\dfrac{1}{\sqrt{3}}$, where $f''$ changes sign.

## 4.15 Worked Examples of Extremum Problems

### 4.15.1 Two Basic Principles

1. **Constant-sum, maximum-product principle**
   - Given $x+y=S$ with $x,y\gt0$, the product $xy$ is largest when $x=y=\dfrac{S}{2}$.
   - Proof: $f(x)=x(S-x)$ has $f'(x)=S-2x$, zero at $x=S/2$.

2. **Constant-product, minimum-sum principle**
   - Given $xy=P$ with $x,y\gt0$, the sum $x+y$ is smallest when $x=y=\sqrt{P}$.
   - Proof: $f(x)=x+P/x$ has $f'(x)=1-P/x^2$, zero at $x=\sqrt{P}$.

### 4.15.2 Consequences

- Among all rectangles of a given perimeter, the **square** has the largest area (Principle 1).
- **Arithmetic鈥揼eometric mean inequality**: For $a,b\gt0$,
  $$
  \sqrt{ab}\le\frac{a+b}{2},
  $$
  with equality if and only if $a=b$ (Principle 2).

### 4.15.3 Example: Minimizing Propelling Force

- A block of weight $W$ is pulled along a table by a force inclined at angle $\theta$.
- The propelling force needed to overcome friction is
  $$
  F(\theta)=\frac{\mu W}{\cos\theta+\mu\sin\theta},\qquad 0\le\theta\le\frac{\pi}{2}.
  $$
- To minimize $F$, maximize the denominator $g(\theta)=\cos\theta+\mu\sin\theta$.
- $g'(\theta)=-\sin\theta+\mu\cos\theta=0$ gives $\tan\alpha=\mu$.
- The minimum force is
  $$
  F_{\min}=\frac{\mu W}{\sqrt{1+\mu^2}}.
  $$

### 4.15.4 Example: Shortest Distance from a Point to a Parabola

- Find the shortest distance from $(0,b)$ on the $y$-axis to the parabola $x^2=4y$.
- Minimize $d^2=x^2+(y-b)^2=4y+(y-b)^2$ for $y\ge0$.
- $f'(y)=4+2(y-b)=0$ gives $y=b-2$.
- **Case $b\lt2$**: critical point $y=b-2$ is negative, so excluded. Since $f'(y)\gt0$ for $y\ge0$, the minimum occurs at the endpoint $y=0$. Minimum distance $=|b|$.
- **Case $b\ge2$**: legitimate critical point at $y=b-2$. Since $f''(y)=2\gt0$, this gives the absolute minimum. Minimum distance $=2\sqrt{b-1}$.
- The special transition value is $b=2$.

## 4.16 Partial Derivatives

### 4.16.1 Functions of Two Variables

- A **real-valued function of two real variables** has domain $X$ in the $xy$-plane and assigns a real number $f(x,y)$ to each point $(x,y)\in X$.
- **Example**: Temperature on a circular disk of radius $4$:
  $$
  f(x,y)=16-x^{2}-y^{2},\qquad x^{2}+y^{2}\le 16.
  $$
  On any circle $x^{2}+y^{2}=r^{2}$ the temperature is constant: $f=16-r^{2}$.

### 4.16.2 Geometric Representations

Two methods for visualizing $z=f(x,y)$:

| Method | Description |
|--------|-------------|
| **Surface** | Plot $(x,y,z)$ with $z=f(x,y)$ in 3-space. |
| **Level curves** | Project the intersection of $z=f(x,y)$ with horizontal planes $z=c$ onto the $xy$-plane; each curve satisfies $f(x,y)=c$. |

- **Level curves** are also called **contour lines** or **isotherms** (in temperature problems).
- Closely spaced level curves indicate rapid change (steepness); widely spaced curves indicate slow change.
- **Example**: $z=xy$ (hyperbolic paraboloid) has level curves $xy=c$.

### 4.16.3 Definition of Partial Derivatives

Cut the surface $z=f(x,y)$ with the plane $y=y_{0}$. The intersection is the curve $z=f(x,y_{0})$, a function of $x$ alone.

- **Difference quotient with respect to $x$**:
  $$
  \frac{f(x_{0}+h,y_{0})-f(x_{0},y_{0})}{h}.
  $$
- **Partial derivative with respect to $x$** at $(x_{0},y_{0})$:
  $$
  f_{1}(x_{0},y_{0})=\lim_{h\to 0}\frac{f(x_{0}+h,y_{0})-f(x_{0},y_{0})}{h}.
  $$
- **Partial derivative with respect to $y$** at $(x_{0},y_{0})$:
  $$
  f_{2}(x_{0},y_{0})=\lim_{k\to 0}\frac{f(x_{0},y_{0}+k)-f(x_{0},y_{0})}{k}.
  $$

Geometrically, $f_{1}(x_{0},y_{0})$ is the slope of the tangent to the curve $z=f(x,y_{0})$ at $x=x_{0}$; $f_{2}(x_{0},y_{0})$ is the slope of the tangent to $z=f(x_{0},y)$ at $y=y_{0}$.

### 4.16.4 Notations

| With respect to $x$ | With respect to $y$ |
|---------------------|---------------------|
| $\displaystyle\frac{\partial f}{\partial x}$ | $\displaystyle\frac{\partial f}{\partial y}$ |
| $f'_{x}(x,y)$ | $f'_{y}(x,y)$ |
| $f_{x}(x,y)$ | $f_{y}(x,y)$ |
| $f_{1}(x,y)$ | $f_{2}(x,y)$ |
| $D_{1}f(x,y)$ | $D_{2}f(x,y)$ |

If $z=f(x,y)$, one also writes $\partial z/\partial x$ and $\partial z/\partial y$.

### 4.16.5 Computation and Examples

To compute $\partial f/\partial x$, treat $y$ as constant and differentiate with respect to $x$ using the ordinary rules; similarly for $\partial f/\partial y$.

**Example 1**:
$$
f(x,y)=16-x^{2}-y^{2}\quad\Longrightarrow\quad f_{1}=-2x,\;\;f_{2}=-2y.
$$

**Example 2**:
$$
f(x,y)=x\sin y+y^{2}\cos(xy).
$$
Then
$$
f_{1}(x,y)=\sin y-y^{3}\sin(xy),
$$
$$
f_{2}(x,y)=x\cos y-xy^{2}\sin(xy)+2y\cos(xy).
$$

### 4.16.6 Second-Order Partial Derivatives

Since $f_{1}$ and $f_{2}$ are themselves functions of two variables, we may differentiate again:

| Notation | Meaning |
|----------|---------|
| $f_{1,1}=f_{xx}=\dfrac{\partial^{2}f}{\partial x^{2}}$ | Differentiate $f_{1}$ with respect to $x$ |
| $f_{1,2}=f_{xy}=\dfrac{\partial^{2}f}{\partial y\,\partial x}$ | Differentiate $f_{1}$ with respect to $y$ |
| $f_{2,1}=f_{yx}=\dfrac{\partial^{2}f}{\partial x\,\partial y}$ | Differentiate $f_{2}$ with respect to $x$ |
| $f_{2,2}=f_{yy}=\dfrac{\partial^{2}f}{\partial y^{2}}$ | Differentiate $f_{2}$ with respect to $y$ |

In $\partial$-notation:
$$
\frac{\partial^{2}f}{\partial y\,\partial x}=\frac{\partial}{\partial y}\!\left(\frac{\partial f}{\partial x}\right),\qquad
\frac{\partial^{2}f}{\partial x\,\partial y}=\frac{\partial}{\partial x}\!\left(\frac{\partial f}{\partial y}\right).
$$

- The two **mixed partial derivatives** need not be equal in general, but equality holds under mild conditions satisfied by most functions occurring in practice (discussed in Volume II).

**Example 1**: For $f(x,y)=16-x^{2}-y^{2}$:
$$
f_{1,1}=-2,\qquad f_{1,2}=f_{2,1}=0,\qquad f_{2,2}=-2.
$$

**Example 2**: For $f(x,y)=x\sin y+y^{2}\cos(xy)$:
$$
\begin{aligned}
f_{1,1}&=-y^{4}\cos(xy),\\[4pt]
f_{1,2}&=\cos y-xy^{3}\cos(xy)-3y^{2}\sin(xy)=f_{2,1},\\[4pt]
f_{2,2}&=-x\sin y-x^{2}y^{2}\cos(xy)-4xy\sin(xy)+2\cos(xy).
\end{aligned}
$$

[<- Previous: 3. Continuous Functions](03-continuous-functions.md) | [Next: 5. The Relation between Integration and Differentiation ->](05-the-relation-between-integration-and-differentiation.md)
