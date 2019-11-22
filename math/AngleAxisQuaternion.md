##### quaternion to rotation matrix

$ R_q = \begin{bmatrix} 2bb+2aa-1 & 2bc-2ad & 2bd+2ac \\ 2bc+2ad & 2cc+2aa-1 & 2cd-2ab \\ 2bd-2ac & 2cd+2ab & 2dd+2aa-1 \end{bmatrix} $

[AxisAngle](AxisAngle.md)

##### TODO

$ \vec{v'} = q\vec{v}q^{-1} = (a+\vec{u}) \ \vec{v} \ (a-\vec{u}) = 2({u}\cdot{v})\vec{u} + 2a(\vec{u}\times\vec{v}) + (2a^2-1)\vec{v} $

21/12 or 19/14

$ R_q = 2({u}\otimes{u}) +2a[u]_{\times} +(2a^2-1)I $

##### TODO

$ \vec{v'} = q\vec{v}q^{-1} = (a+\vec{u}) \ \vec{v} \ (a-\vec{u}) = 2(({u}\cdot{v})\vec{u} + a(a\vec{v}+\vec{u}\times\vec{v})) - \vec{v} $

20/14 or 18/16

$ R_q = 2(({u}\otimes{u})+a(aI+[u]_{\times}))-I $

##### TODO

$ \vec{v'} = q\vec{v}q^{-1} = (a+\vec{u}) \ \vec{v} \ (a-\vec{u}) = 2(({u}\cdot{v})\vec{u} + a(\vec{u}\times\vec{v}) + (a^2-\frac{1}{2})\vec{v}) $

$ R_q = 2(({u}\otimes{u}) +a[u]_{\times} +(a^2-\frac{1}{2})I) $

##### quaternion to rotation matrix TODO

```csharp
// temp
var aa = 2 * a * a - 1; // cos
var tb = b * 2; var tc = c * 2; var td = d * 2; // 
var ab = tb * a; var ac = tc * a; var ad = td * a; // cross
var bb = tb * b; var cc = tc * c; var dd = td * d; // dot
var bc = tb * c; var bd = tb * d; var cd = tc * d; // dot
// matrix elements
var xx = bb + aa; var xy = bc - ad; var xz = bd + ac; // x' row
var yx = bc + ad; var yy = cc + aa; var yz = cd - ab; // y' row
var zx = bd - ac; var zy = cd + ab; var zz = dd + aa; // z' row
// 14 multiplications
// 10 additions/subtractions
```

##### quaternion to rotate vector

```csharp

```

