##### axis angle to rotation matrix

$ R_u = \begin{bmatrix} 1+(-\ c^2-d^2)(1-\cos\theta) & bc(1-\cos\theta)-d\sin\theta & bd(1-\cos\theta)+c\sin\theta \\ bc(1-\cos\theta)+d\sin\theta & 1+(-\ b^2-d^2)(1-\cos\theta) & cd(1-\cos\theta)-b\sin\theta \\ bd(1-\cos\theta)-c\sin\theta & cd(1-\cos\theta)+b\sin\theta & 1+(-\ b^2-c^2)(1-\cos\theta) \end{bmatrix} $

[Quaternion](Quaternion.md)

##### TODO

$ R_u = \overbrace{\underbrace{\begin{bmatrix}1&0&0\\0&1&0\\0&0&1\end{bmatrix}}_{\textstyle I}}^{\textstyle 1} + \overbrace{\underbrace{\begin{bmatrix}-\ c^2-d^2&bc&bd\\bc&-\ b^2-d^2&cd\\bd&cd&-\ b^2-c^2\end{bmatrix}}_{\textstyle ([u]_{\times})^2}}^{\textstyle (1-\cos\theta)} + \overbrace{\underbrace{\begin{bmatrix}0&-d&c\\d&0&-b\\-c&b&0\end{bmatrix}}_{\textstyle [u]_{\times}}}^{\textstyle \sin\theta} $

$ R_u = I + ([u]_{\times})^2(1-\cos\theta) + [u]_{\times}\sin\theta $

9/16/2

$ R_u = I + [u]_{\times}([u]_{\times}(1-\cos\theta) + I\sin\theta) $

$\color{red} \vec{v'} = \vec{v} + (\vec{u}\times(\vec{u}\times\vec{v}))(1-\cos\theta) + (\vec{u}\times\vec{v})\sin\theta $

$ \vec{v'} = \vec{v} + \vec{u}\times((\vec{u}\times\vec{v})(1-\cos\theta) + \vec{v}\sin\theta) $

18/13/2

##### axis angle to rotate vector

```csharp
// temp
var sin = Sin(angle); var cos = Cos(angle); var ver = 1 - cos;
var tx = (c * z - d * y); // cross
var ty = (d * x - b * z); // cross
var tz = (b * y - c * x); // cross
// vector
var _x = x + (c * tz - d * ty) * ver + tx * sin; // x'
var _y = y + (d * tx - b * tz) * ver + ty * sin; // y'
var _z = z + (b * ty - c * tx) * ver + tz * sin; // z'
// 18 multiplications
// 13 additions/subtractions
// 2 function calls
```

##### axis angle to rotate vector

```csharp
// temp
var sin = Sin(angle); var cos = Cos(angle); var ver = 1 - cos;
var tx = (c * z - d * y) * ver + x * sin;
var ty = (d * x - b * z) * ver + y * sin;
var tz = (b * y - c * x) * ver + z * sin;
// vector
var _x = x + (c * tz - d * ty); // x'
var _y = y + (d * tx - b * tz); // y'
var _z = z + (b * ty - c * tx); // z'
// 18 multiplications
// 13 additions/subtractions
// 2 function calls
```

##### TODO

```csharp
var sin = Sin(angle); var cos = Cos(angle); var ver = 1 - cos;
var tx = x;
var ty = y;
var tz = z;
tx = (c * tz - d * ty); // cross
ty = (d * tx - b * tz); // cross
tz = (b * ty - c * tx); // cross
tx = (c * tz - d * ty) * ver + tx * sin;
ty = (d * tx - b * tz) * ver + ty * sin;
tz = (b * ty - c * tx) * ver + tz * sin;
var _x = x + tx; // x'
var _y = y + ty; // y'
var _z = z + tz; // z'
```

```csharp
var sin = Sin(angle); var cos = Cos(angle); var ver = 1 - cos;
var tx = x;
var ty = y;
var tz = z;
tx = (c * tz - d * ty) * ver + tx * sin;
ty = (d * tx - b * tz) * ver + ty * sin;
tz = (b * ty - c * tx) * ver + tz * sin;
tx = (c * tz - d * ty); // cross
ty = (d * tx - b * tz); // cross
tz = (b * ty - c * tx); // cross
var _x = x + tx; // x'
var _y = y + ty; // y'
var _z = z + tz; // z'
```

