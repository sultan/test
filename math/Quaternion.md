##### quaternion to rotation matrix

$ R_q = \begin{bmatrix} 1-2cc-2dd & 2bc-2ad & 2bd+2ac \\ 2bc+2ad & 1-2bb-2dd & 2cd-2ab \\ 2bd-2ac & 2cd+2ab & 1-2bb-2cc \end{bmatrix} $

[AA](AxisAngleAlternative.md)

##### TODO

$\color{red} R_q = \overbrace{\underbrace{\begin{bmatrix}1&0&0\\0&1&0\\0&0&1\end{bmatrix}}_{\textstyle I}}^{\textstyle 1} + \overbrace{\underbrace{\begin{bmatrix}-\ c^2-d^2&bc&bd\\bc&-\ b^2-d^2&cd\\bd&cd&-\ b^2-c^2\end{bmatrix}}_{\textstyle ([u]_{\times})^2}}^{\textstyle 2} + \overbrace{\underbrace{\begin{bmatrix}0&-d&c\\d&0&-b\\-c&b&0\end{bmatrix}}_{\textstyle [u]_{\times}}}^{\textstyle 2a} $

$\color{red} R_q = I + 2([u]_{\times})^2 + 2a[u]_{\times} $

12/12 or 9/15

$ \vec{v'} = q\vec{v}q^{-1} = (a+\vec{u}) \ \vec{v} \ (a-\vec{u}) = \vec{v} + 2\vec{u}\times(\vec{u}\times\vec{v}) + 2a(\vec{u}\times\vec{v}) $



##### quaternion to rotation matrix TODO

```csharp
// temp
var tb = b * 2; var tc = c * 2; var td = d * 2; // 
var ab = tb * a; var ac = tc * a; var ad = td * a; // cross
var bb = tb * b; var cc = tc * c; var dd = td * d; // dot
var bc = tb * c; var bd = tb * d; var cd = tc * d; // dot
// matrix elements
var xx = 1 - cc - dd; var xy = bc - ad; var xz = bd + ac; // x' row
var yx = bc + ad; var yy = 1 - bb - dd; var yz = cd - ab; // y' row
var zx = bd - ac; var zy = cd + ab; var zz = 1 - bb - cc; // z' row
// 12 multiplications
// 12 additions/subtractions
```

##### quaternion to rotate vector

```csharp
// temp
var tx = c * z - d * y + x * a;
var ty = d * x - b * z + y * a;
var tz = b * y - c * x + z * a;
// vector
var _x = 2 * (c * tz - d * ty) + x; // x'
var _y = 2 * (d * tx - b * tz) + y; // y'
var _z = 2 * (b * ty - c * tx) + z; // z'
//
//
```

##### TODO

$ \vec{v'} = q\vec{v}q^{-1} = (a+\vec{u}) \ \vec{v} \ (a-\vec{u}) = \vec{v} + 2\vec{u}\times(\vec{u}\times\vec{v}+a\vec{v}) $

18/12 or 15/15

