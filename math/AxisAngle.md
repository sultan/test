##### axis angle to rotation matrix

$ R_u = \begin{bmatrix} bb(1-\cos\theta)+(\cos\theta) & bc(1-\cos\theta)-d\sin\theta & bd(1-\cos\theta)+c\sin\theta \\ bc(1-\cos\theta)+d\sin\theta & cc(1-\cos\theta)+(\cos\theta) & cd(1-\cos\theta)-b\sin\theta \\ bd(1-\cos\theta)-c\sin\theta & cd(1-\cos\theta)+b\sin\theta & dd(1-\cos\theta)+(\cos\theta) \end{bmatrix} $

##### TODO

$ \vec{v'} = \vec{v}\cos\theta + \vec{u}({u}\cdot{v})(1-\cos\theta) + (\vec{u}\times\vec{v})\sin\theta $

19 mul, 12 add/sub, 2 fun calls

$\color{lightgray} R_u = I\cos\theta + (u\otimes{u})(1-\cos\theta) + [u]_{\times}\sin\theta $

$\color{lightgray} R_u = I\cos\theta + \begin{bmatrix}bb&bc&bd\\bc&cc&cd\\bd&cd&dd\end{bmatrix} (1-\cos\theta) + \begin{bmatrix}0&-d&c\\d&0&-b\\-c&b&0\end{bmatrix}\sin\theta $

12 mul, 10 add/sub, 2 fun calls

##### TODO

$ \vec{v'} = \vec{u}(\vec{u}\cdot\vec{v}) + (\vec{v}-\vec{u}(\vec{u}\cdot\vec{v}))(\cos\theta) + (\vec{u}\times\vec{v})\sin\theta $

15 mul, 14 add/sub, 2 fun calls

$\color{lightgray} R_u = (u\otimes{u}) + (I-(u\otimes{u}))(\cos\theta) + [u]_{\times}\sin\theta $

$\color{lightgray} R_u = \begin{bmatrix}bb&bc&bd\\bc&cc&cd\\bd&cd&dd\end{bmatrix} + \bigg(I-\begin{bmatrix}bb&bc&bd\\bc&cc&cd\\bd&cd&dd\end{bmatrix}\bigg)(\cos\theta) + \begin{bmatrix}0&-d&c\\d&0&-b\\-c&b&0\end{bmatrix}\sin\theta $

12 mul, 18 add/sub, fun calls

##### axis angle to rotation matrix

```csharp
// temp
var sin = Sin(angle); var cos = Cos(angle); var ver = 1 - cos;
var ab = b * sin; var ac = c * sin; var ad = d * sin;
var tb = b * ver; var tc = c * ver; var td = d * ver;
var bb = b * tb; var cc = c * tc; var dd = d * td;
var bc = b * tc; var bd = b * td; var cd = c * td;
// matrix elements
var xx = bb + cos; var xy = bc - ad; var xz = bd + ac;
var yx = bc + ad; var yy = cc + cos; var yz = cd - ab;
var zx = bd - ac; var zy = cd + ab; var zz = dd + cos;
// 12 multiplications
// 10 additions/subtractions
// 2 function calls
```

##### axis angle to rotate vector

```csharp
// temp
var sin = Sin(angle); var cos = Cos(angle); var ver = 1 - cos;
var dotver = (b * x + c * y + d * z) * ver;
// vector
var _x = x * cos + b * dotver + (c * z - d * y) * sin;
var _y = y * cos + c * dotver + (d * x - b * z) * sin;
var _z = z * cos + d * dotver + (b * y - c * x) * sin;
// 19 multiplications
// 12 additions/subtractions
// 2 function calls
```

