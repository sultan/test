##### quaternion to rotation matrix

$ R_q = \begin{bmatrix} 1-2cc-2dd & 2bc-2ad & 2bd+2ac \\ 2bc+2ad & 1-2bb-2dd & 2cd-2ab \\ 2bd-2ac & 2cd+2ab & 1-2bb-2cc \end{bmatrix} $

$\color{lightgray} R_u = \begin{bmatrix} 1+(-\ c^2-d^2)(1-\cos\theta) & bc(1-\cos\theta)-d\sin\theta & bd(1-\cos\theta)+c\sin\theta \\ bc(1-\cos\theta)+d\sin\theta & 1+(-\ b^2-d^2)(1-\cos\theta) & cd(1-\cos\theta)-b\sin\theta \\ bd(1-\cos\theta)-c\sin\theta & cd(1-\cos\theta)+b\sin\theta & 1+(-\ b^2-c^2)(1-\cos\theta) \end{bmatrix} $

##### TODO

$\color{lightgray} \vec{v'} = q\vec{v}q^{-1} = (a+\vec{u}) \ \vec{v} \ (a-\vec{u}) = \vec{v} + 2\vec{u}\times(\vec{u}\times\vec{v}) + 2a(\vec{u}\times\vec{v}) $

$\color{lightgray} R_q = I + 2([u]_{\times})^2 + 2a[u]_{\times} $

$ \vec{v'} = \vec{v} + (\vec{u}\times(\vec{u}\times\vec{v}))(1-\cos\theta) + (\vec{u}\times\vec{v})\sin\theta $

$ R_u = I + ([u]_{\times})^2(1-\cos\theta) + [u]_{\times}\sin\theta $

$\color{lightgray} R_u = I + \begin{bmatrix}-\ c^2-d^2&bc&bd\\bc&-\ b^2-d^2&cd\\bd&cd&-\ b^2-c^2\end{bmatrix}(1-\cos\theta) + \begin{bmatrix}0&-d&c\\d&0&-b\\-c&b&0\end{bmatrix}\sin\theta $

##### TODO

$ \vec{v'} = q\vec{v}q^{-1} = (a+\vec{u}) \ \vec{v} \ (a-\vec{u}) = \vec{v} + 2\vec{u}\times(\vec{u}\times\vec{v}+a\vec{v}) $

18/12 or 15/15

$\color{lightgray} R_q = I + 2[u]_{\times}([u]_{\times} + aI) $

$\color{lightgray} \vec{v'} = \vec{v} + \vec{u}\times((\vec{u}\times\vec{v})(1-\cos\theta) + \vec{v}\sin\theta) $

$\color{lightgray} R_u = I + [u]_{\times}([u]_{\times}(1-\cos\theta) + I\sin\theta) $

$\color{lightgray} R_u = I + \begin{bmatrix}0&-d&c\\d&0&-b\\-c&b&0\end{bmatrix}\bigg(\begin{bmatrix}0&-d&c\\d&0&-b\\-c&b&0\end{bmatrix}(1-\cos\theta) + I\sin\theta\bigg) $

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

