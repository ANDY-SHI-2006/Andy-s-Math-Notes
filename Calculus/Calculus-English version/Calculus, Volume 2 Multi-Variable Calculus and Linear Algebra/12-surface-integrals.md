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

