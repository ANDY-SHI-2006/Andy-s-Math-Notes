# Chapter 12 — Surface Integrals

### 12.1 Parametric Representation of a Surface

Three ways to describe a surface:
- **Implicit:** $F(x,y,z)=0$.
- **Explicit:** $z=f(x,y)$.
- **Parametric (vector):**
  $$
  \boldsymbol r(u,v)=X(u,v)\mathbf i+Y(u,v)\mathbf j+Z(u,v)\mathbf k,\qquad(u,v)\in T.\tag{12.2}
  $$

**Example 1. Sphere of radius $a$.**
$$
x=a\cos u\cos v,\quad y=a\sin u\cos v,\quad z=a\sin v,\qquad
(u,v)\in[0,2\pi]\times[-\tfrac{\pi}{2},\tfrac{\pi}{2}].\tag{12.3}
$$

**Example 2. Right circular cone (half vertex angle $\alpha$).**
$$
\boldsymbol r(u,v)=v\sin\alpha\cos u\,\mathbf i+v\sin\alpha\sin u\,\mathbf j+v\cos\alpha\,\mathbf k,
\qquad(u,v)\in[0,2\pi]\times[0,h].
$$

**Terminology.** The image $\boldsymbol r(T)$ is a **parametric surface**; if $\boldsymbol r$ is one-to-one on $T$ it is called a **simple parametric surface**. Degenerate cases (point or curve) occur when the functions are constant or depend on only one parameter.


### 12.2 The Fundamental Vector Product

For $\boldsymbol r(u,v)=X\mathbf i+Y\mathbf j+Z\mathbf k$ define
$$
\frac{\partial\boldsymbol r}{\partial u},\quad\frac{\partial\boldsymbol r}{\partial v}.
$$
Their cross product is the **fundamental vector product**:
$$
\frac{\partial\boldsymbol r}{\partial u}\times\frac{\partial\boldsymbol r}{\partial v}
=\frac{\partial(Y,Z)}{\partial(u,v)}\mathbf i
+\frac{\partial(Z,X)}{\partial(u,v)}\mathbf j
+\frac{\partial(X,Y)}{\partial(u,v)}\mathbf k.\tag{12.4}
$$

- **Regular point:** $\frac{\partial\boldsymbol r}{\partial u}$, $\frac{\partial\boldsymbol r}{\partial v}$ continuous and the cross product $\neq\mathbf 0$.
- **Singular point:** otherwise.
- **Smooth surface:** all points are regular.

**Geometric meaning.** A rectangle of area $\Delta u\,\Delta v$ in the parameter plane maps to a parallelogram of area
$$
\Bigl\|\frac{\partial\boldsymbol r}{\partial u}\times\frac{\partial\boldsymbol r}{\partial v}\Bigr\|\,\Delta u\,\Delta v.
$$
Hence $\bigl\|\frac{\partial\boldsymbol r}{\partial u}\times\frac{\partial\boldsymbol r}{\partial v}\bigr\|$ is the local area magnification factor. At regular points the cross product is normal to the **tangent plane**.

**Example 1.** Explicit surface $z=f(x,y)$:
$$
\boldsymbol r(x,y)=x\mathbf i+y\mathbf j+f(x,y)\mathbf k,\qquad
\frac{\partial\boldsymbol r}{\partial x}\times\frac{\partial\boldsymbol r}{\partial y}
=-\frac{\partial f}{\partial x}\mathbf i-\frac{\partial f}{\partial y}\mathbf j+\mathbf k.\tag{12.5}
$$
Never zero (the $z$-component is $1$).

**Example 2.** Sphere $\boldsymbol r(u,v)=a\cos u\cos v\,\mathbf i+a\sin u\cos v\,\mathbf j+a\sin v\,\mathbf k$:
$$
\frac{\partial\boldsymbol r}{\partial u}\times\frac{\partial\boldsymbol r}{\partial v}=a\cos v\,\boldsymbol r(u,v),
\qquad\Bigl\|\frac{\partial\boldsymbol r}{\partial u}\times\frac{\partial\boldsymbol r}{\partial v}\Bigr\|=a^2\cos v.
$$
Singular when $\cos v=0$ (the North Pole).


### 12.3 The Fundamental Vector Product as a Normal to the Surface

Let $C^*$ be a smooth curve in $T$, described by $\boldsymbol\alpha(t)=U(t)\mathbf i+V(t)\mathbf j$, and let $C=\boldsymbol r(C^*)$ be its image on the surface. The composite function
$$
\boldsymbol\rho(t)=\boldsymbol r[\boldsymbol\alpha(t)]
$$
has derivative (by the chain rule)
$$
\boldsymbol\rho'(t)=\frac{\partial\boldsymbol r}{\partial u}\,U'(t)+\frac{\partial\boldsymbol r}{\partial v}\,V'(t).\tag{12.6}
$$
Since both $\partial\boldsymbol r/\partial u$ and $\partial\boldsymbol r/\partial v$ are perpendicular to their cross product, so is $\boldsymbol\rho'(t)$. Hence at each point of $C$ the vector
$$
\frac{\partial\boldsymbol r}{\partial u}\times\frac{\partial\boldsymbol r}{\partial v}
$$
is **normal to the surface** $\boldsymbol r(T)$.

At a regular point $P$ this vector is nonzero; the plane through $P$ with this normal is the **tangent plane** to the surface at $P$.


### 12.5 Area of a Parametric Surface

**Definition.** For $S=\boldsymbol r(T)$,
$$
 a(S)=\iint_T\Bigl\|\frac{\partial\boldsymbol r}{\partial u}\times\frac{\partial\boldsymbol r}{\partial v}\Bigr\|\,du\,dv.\tag{12.7}
$$
In Jacobian form:
$$
 a(S)=\iint_T\sqrt{\Bigl(\frac{\partial(Y,Z)}{\partial(u,v)}\Bigr)^2+\Bigl(\frac{\partial(Z,X)}{\partial(u,v)}\Bigr)^2+\Bigl(\frac{\partial(X,Y)}{\partial(u,v)}\Bigr)^2}\,du\,dv.\tag{12.8}
$$

**Explicit surface** $z=f(x,y)$, with $T$ the projection on the $xy$-plane:
$$
 a(S)=\iint_T\sqrt{1+\Bigl(\frac{\partial f}{\partial x}\Bigr)^2+\Bigl(\frac{\partial f}{\partial y}\Bigr)^2}\,dx\,dy.\tag{12.9}
$$
If $\gamma$ is the angle between the normal and $\mathbf k$, then $\|\partial\boldsymbol r/\partial x\times\partial\boldsymbol r/\partial y\|=1/\cos\gamma$, giving the **area cosine principle**:
$$
 a(T)=a(S)\cos\gamma.\tag{12.11}
$$

**Implicit surface** $F(x,y,z)=0$ (with $F_z\neq0$):
$$
 a(S)=\iint_T\frac{\sqrt{F_x^2+F_y^2+F_z^2}}{|F_z|}\,dx\,dy.\tag{12.12}
$$

**Example 1. Hemisphere of radius $a$.** Using the parametric representation (12.13),
$$
 \Bigl\|\frac{\partial\boldsymbol r}{\partial u}\times\frac{\partial\boldsymbol r}{\partial v}\Bigr\|=a^2\cos v,
 \qquad a(S)=a^2\int_0^{2\pi}\!\int_0^{\pi/2}\!\cos v\,dv\,du=2\pi a^2.
$$

**Example 2. Pappus theorem for surface area.** A curve of length $L$ in the $xz$-plane, $z=f(x)$, $a\le x\le b$, rotated about the $z$-axis generates a surface of revolution
$$
 \boldsymbol r(u,v)=u\cos v\,\mathbf i+u\sin v\,\mathbf j+f(u)\,\mathbf k.
$$
Then
$$
 a(S)=2\pi\int_a^b u\sqrt{1+[f'(u)]^2}\,du=2\pi\bar x L,
$$
where $\bar x$ is the $x$-coordinate of the centroid of $C$.


### 12.7 Surface Integrals

**Definition.** For a scalar field $f$ on $S=\boldsymbol r(T)$,
$$
 \iint_{\boldsymbol r(T)} f\,dS
 = \iint_T f[\boldsymbol r(u,v)]\,\Bigl\|\frac{\partial\boldsymbol r}{\partial u}\times\frac{\partial\boldsymbol r}{\partial v}\Bigr\|\,du\,dv.\tag{12.14}
$$

**Applications.**
- **Surface area:** $f=1$ gives $a(S)=\iint_S dS$.
- **Mass and center of mass:** $m=\iint_S\rho\,dS$, and
  $$
  \bar x m=\iint_S x\rho\,dS,\quad
  \bar y m=\iint_S y\rho\,dS,\quad
  \bar z m=\iint_S z\rho\,dS.
  $$
- **Moment of inertia:** $I_L=\iint_S\delta^2\rho\,dS$, where $\delta$ is the distance to axis $L$.
- *Example:* Uniform hemisphere of radius $a$ has $\bar z=a/2$ (by symmetry $\bar x=\bar y=0$).

**Fluid flow.** Let $\mathbf F=\rho\mathbf V$ be the **flux density**. The unit normal
$$
 \mathbf n=\frac{\partial\boldsymbol r/\partial u\times\partial\boldsymbol r/\partial v}{\|\partial\boldsymbol r/\partial u\times\partial\boldsymbol r/\partial v\|}\tag{12.15}
$$
gives the mass of fluid crossing $S$ per unit time in direction $\mathbf n$:
$$
 \iint_S \mathbf F\cdot\mathbf n\,dS.
$$


### 12.8 Change of Parametric Representation

Let $\boldsymbol G(s,t)=U(s,t)\mathbf i+V(s,t)\mathbf j$ map $B$ in the $st$-plane one-to-one onto $A$ in the $uv$-plane, and define
$$
 \boldsymbol R(s,t)=\boldsymbol r[\boldsymbol G(s,t)].\tag{12.17}
$$
Then $\boldsymbol r$ and $\boldsymbol R$ are **smoothly equivalent**; they describe the same surface.

**Theorem 12.1.** The fundamental vector products are related by the Jacobian of $G$:
$$
 \frac{\partial\boldsymbol R}{\partial s}\times\frac{\partial\boldsymbol R}{\partial t}
 =\Bigl(\frac{\partial\boldsymbol r}{\partial u}\times\frac{\partial\boldsymbol r}{\partial v}\Bigr)\,
 \frac{\partial(U,V)}{\partial(s,t)}.\tag{12.18}
$$
*Proof sketch.* Apply the chain rule to $\partial\boldsymbol R/\partial s$ and $\partial\boldsymbol R/\partial t$, then cross-multiply; the mixed terms cancel and the Jacobian factor appears.

**Theorem 12.2 (Invariance of surface integrals).** If $\boldsymbol r$ and $\boldsymbol R$ are smoothly equivalent,
$$
 \iint_{\boldsymbol r(A)} f\,dS = \iint_{\boldsymbol R(B)} f\,dS.
$$
*Proof sketch.* Substitute (12.18) into the definition; the absolute value of the Jacobian factor is exactly what is needed for the change-of-variables formula in the double integral, so the two surface-integral expressions coincide.


### 12.9 Other Notations for Surface Integrals

At each regular point there are two unit normals:
$$
 \mathbf n_1=\frac{\mathbf N}{\|\mathbf N\|},\qquad \mathbf n_2=-\mathbf n_1.
$$
For a vector field $\mathbf F=P\mathbf i+Q\mathbf j+R\mathbf k$,
$$
 \iint_S \mathbf F\cdot\mathbf n\,dS
 =\pm\iint_T \mathbf F[\boldsymbol r(u,v)]\cdot\Bigl(\frac{\partial\boldsymbol r}{\partial u}\times\frac{\partial\boldsymbol r}{\partial v}\Bigr)\,du\,dv,\tag{12.19}
$$
$+$ for $\mathbf n=\mathbf n_1$, $-$ for $\mathbf n=\mathbf n_2$.

In components this becomes
$$
 \iint_S \mathbf F\cdot\mathbf n\,dS
 =\iint_T\!P\,\frac{\partial(Y,Z)}{\partial(u,v)}\,du\,dv
 +\iint_T\!Q\,\frac{\partial(Z,X)}{\partial(u,v)}\,du\,dv
 +\iint_T\!R\,\frac{\partial(X,Y)}{\partial(u,v)}\,du\,dv.\tag{12.20}
$$

**Differential-form notation.** The right-hand side is abbreviated as
$$
 \iint_S P\,dy\wedge dz + Q\,dz\wedge dx + R\,dx\wedge dy,\tag{12.22}
$$
with
$$
 \iint_S P\,dy\wedge dz = \iint_T P[\boldsymbol r(u,v)]\,\frac{\partial(Y,Z)}{\partial(u,v)}\,du\,dv.\tag{12.23}
$$
Order matters: $dy\wedge dz=-dz\wedge dy$.

**Direction-cosine form.** If $\mathbf n=(\cos\alpha,\cos\beta,\cos\gamma)$, then
$$
 \iint_S \mathbf F\cdot\mathbf n\,dS
 =\iint_S (P\cos\alpha+Q\cos\beta+R\cos\gamma)\,dS.\tag{12.25--12.26}
$$
The sign depends on the choice of normal ($\mathbf n_1$ or $\mathbf n_2$).


### 12.11 Stokes' Theorem

**Theorem 12.3 (Stokes).** Let $S=\boldsymbol r(T)$ be a smooth simple parametric surface, where $T$ is bounded by a piecewise smooth Jordan curve $\Gamma$, and let $C=\boldsymbol r(\Gamma)$. If $P,Q,R$ are continuously differentiable on $S$, then
$$
 \iint_S\Bigl(\frac{\partial R}{\partial y}-\frac{\partial Q}{\partial z}\Bigr)dy\wedge dz
 +\Bigl(\frac{\partial P}{\partial z}-\frac{\partial R}{\partial x}\Bigr)dz\wedge dx
 +\Bigl(\frac{\partial Q}{\partial x}-\frac{\partial P}{\partial y}\Bigr)dx\wedge dy
 =\int_C P\,dx+Q\,dy+R\,dz.\tag{12.27}
$$
The orientation of $C$ is inherited from the positive (counterclockwise) orientation of $\Gamma$.

**Proof sketch.** It suffices to prove the three component identities (12.28). For the $P\,dx$ part:
1. Write the surface integral as a double integral over $T$:
   $$
   \iint_S\Bigl(-\frac{\partial P}{\partial y}\,dx\wedge dy+\frac{\partial P}{\partial z}\,dz\wedge dx\Bigr)
   =\iint_T\Bigl\{-P_y\,\frac{\partial(X,Y)}{\partial(u,v)}+P_z\,\frac{\partial(Z,X)}{\partial(u,v)}\Bigr\}du\,dv.
   $$
2. Set $p(u,v)=P[X(u,v),Y(u,v),Z(u,v)]$; the integrand simplifies to
   $$
   \frac{\partial}{\partial u}\!\Bigl(p\frac{\partial X}{\partial v}\Bigr)-\frac{\partial}{\partial v}\!\Bigl(p\frac{\partial X}{\partial u}\Bigr).\tag{12.29}
   $$
3. Apply Green’s theorem in the $uv$-plane to obtain a line integral over $\Gamma$, then change variables to show it equals $\int_C P\,dx$.
4. The $Q\,dy$ and $R\,dz$ identities are proved similarly; adding the three gives (12.27).

