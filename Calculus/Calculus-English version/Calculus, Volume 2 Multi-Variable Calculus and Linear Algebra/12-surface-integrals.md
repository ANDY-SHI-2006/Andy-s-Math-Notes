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

