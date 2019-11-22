##### axis angle to rotation matrix

$ R_u = \begin{bmatrix} bb(1-\cos\theta)+(\cos\theta) & bc(1-\cos\theta)-d\sin\theta & bd(1-\cos\theta)+c\sin\theta \\ bc(1-\cos\theta)+d\sin\theta & cc(1-\cos\theta)+(\cos\theta) & cd(1-\cos\theta)-b\sin\theta \\ bd(1-\cos\theta)-c\sin\theta & cd(1-\cos\theta)+b\sin\theta & dd(1-\cos\theta)+(\cos\theta) \end{bmatrix} $

[Quaternion](AngleAxisQuaternion)

##### TODO

$ \vec{v'} = \vec{v}\cos\theta + \vec{u}({u}\cdot{v})(1-\cos\theta) + (\vec{u}\times\vec{v})\sin\theta $

19 mul, 12 add/sub, 2 fun calls

$\color{lightgray} R_u = I\cos\theta + (u\otimes{u})(1-\cos\theta) + [u]_{\times}\sin\theta $

$\color{lightgray} R_u = I\cos\theta + \begin{bmatrix}bb&bc&bd\\bc&cc&cd\\bd&cd&dd\end{bmatrix} (1-\cos\theta) + \begin{bmatrix}0&-d&c\\d&0&-b\\-c&b&0\end{bmatrix}\sin\theta $

12 mul, 10 add/sub, 2 fun calls

##### TODO

$\color{violet} \vec{v'} = \vec{u}({u}\cdot{v}) + (\vec{v}-\vec{u}({u}\cdot{v}))(\cos\theta) + (\vec{u}\times\vec{v})\sin\theta $

15 mul, 14 add/sub, 2 fun calls

$\color{lightgray} R_u = (u\otimes{u}) + (I-(u\otimes{u}))(\cos\theta) + [u]_{\times}\sin\theta $

$\color{lightgray} R_u = \begin{bmatrix}bb&bc&bd\\bc&cc&cd\\bd&cd&dd\end{bmatrix} + \bigg(I-\begin{bmatrix}bb&bc&bd\\bc&cc&cd\\bd&cd&dd\end{bmatrix}\bigg)(\cos\theta) + \begin{bmatrix}0&-d&c\\d&0&-b\\-c&b&0\end{bmatrix}\sin\theta $

12 mul, 18 add/sub, fun calls

##### axis angle to rotation matrix

```csharp
// temp
var sin = Sin(angle); var cos = Cos(angle); var ver = 1 - cos;
var ab = b * sin; var ac = c * sin; var ad = d * sin; // cross
var tb = b * ver; var tc = c * ver; var td = d * ver; // dot
var bb = b * tb; var cc = c * tc; var dd = d * td; // dot
var bc = b * tc; var bd = b * td; var cd = c * td; // dot
// matrix elements
var xx = bb + cos; var xy = bc - ad; var xz = bd + ac; // x' row
var yx = bc + ad; var yy = cc + cos; var yz = cd - ab; // y' row
var zx = bd - ac; var zy = cd + ab; var zz = dd + cos; // z' row
// 12 multiplications
// 10 additions/subtractions
// 2 function calls
```

##### axis angle to rotate vector

```csharp
// temp
var sin = Sin(angle); var cos = Cos(angle); var ver = 1 - cos;
var dot_ver = (b * x + c * y + d * z) * ver;
// vector
var _x = x * cos + b * dot_ver + (c * z - d * y) * sin; // x'
var _y = y * cos + c * dot_ver + (d * x - b * z) * sin; // y'
var _z = z * cos + d * dot_ver + (b * y - c * x) * sin; // z'
// 19 multiplications
// 12 additions/subtractions
// 2 function calls
```

