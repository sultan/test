##### quaternion to rotation matrix

$ R_q = \begin{bmatrix} 2bb+2aa-1 & 2bc-2ad & 2bd+2ac \\ 2bc+2ad & 2cc+2aa-1 & 2cd-2ab \\ 2bd-2ac & 2cd+2ab & 2dd+2aa-1 \end{bmatrix} $

[Switch to Axis Angle instead](AxisAngle.md)

##### TODO

$ R_q = \overbrace{\underbrace{\begin{bmatrix}1&0&0\\0&1&0\\0&0&1\end{bmatrix}}_{\textstyle I}}^{\textstyle (2a^2-1)} + \overbrace{\underbrace{\begin{bmatrix}bb&bc&bd\\bc&cc&cd\\bd&cd&dd\end{bmatrix}}_{ \textstyle ({u}\otimes{u})}}^{\textstyle 2} + \overbrace{\underbrace{\begin{bmatrix}0&-d&c\\d&0&-b\\-c&b&0\end{bmatrix}}_{\textstyle [u]_{\times}}}^{\textstyle 2a} $

$ R_q = (2a^2-1)I + 2({u}\otimes{u}) + 2a[u]_{\times} $

14/10 or 10/14

$ \vec{v'} = q\vec{v}q^{-1} = (a+\vec{u}) \ \vec{v} \ (a-\vec{u}) = (2a^2-1)\vec{v} + 2({u}\cdot{v})\vec{u} + 2a(\vec{u}\times\vec{v}) $

21/12 or 19/14

##### quaternion to rotation matrix

```csharp
// temp
var cos = 2 * a * a - 1; // cos
var tb = b * 2; var tc = c * 2; var td = d * 2; // 
var ab = tb * a; var ac = tc * a; var ad = td * a; // cross
var bb = tb * b; var cc = tc * c; var dd = td * d; // dot
var bc = tb * c; var bd = tb * d; var cd = tc * d; // dot
// matrix elements
var xx = bb + cos; var xy = bc - ad; var xz = bd + ac; // x' row
var yx = bc + ad; var yy = cc + cos; var yz = cd - ab; // y' row
var zx = bd - ac; var zy = cd + ab; var zz = dd + cos; // z' row
// 14 multiplications
// 10 additions/subtractions
```

##### quaternion to rotate vector

not efficient in this version

see a more efficient version for Quaternion [here](Quaternion.md)

##### TODO

$ R_q = \overbrace{\underbrace{\begin{bmatrix}bb&bc&bd\\bc&cc&cd\\bd&cd&dd\end{bmatrix}}_{\textstyle ({u}\otimes{u})} + \overbrace{\underbrace{\begin{bmatrix}0&-d&c\\d&0&-b\\-c&b&0\end{bmatrix}}_{\textstyle [u]_{\times}} + \overbrace{\underbrace{\begin{bmatrix}1&0&0\\0&1&0\\0&0&1\end{bmatrix}}_{\textstyle I}}^{\textstyle a}}^{\textstyle a}}^{\textstyle 2} - \underbrace{\begin{bmatrix}1&0&0\\0&1&0\\0&0&1\end{bmatrix}}_{\textstyle I} $

$ R_q = 2(({u}\otimes{u})+a(aI+[u]_{\times}))-I $

$ \vec{v'} = q\vec{v}q^{-1} = (a+\vec{u}) \ \vec{v} \ (a-\vec{u}) = 2(({u}\cdot{v})\vec{u} + a(a\vec{v}+\vec{u}\times\vec{v})) - \vec{v} $

##### TODO

$ R_q = \overbrace{\underbrace{\begin{bmatrix}bb&bc&bd\\bc&cc&cd\\bd&cd&dd\end{bmatrix}}_{\textstyle ({u}\otimes{u})} + \overbrace{\underbrace{\begin{bmatrix}0&-d&c\\d&0&-b\\-c&b&0\end{bmatrix}}_{\textstyle [u]_{\times}} + \overbrace{\underbrace{\begin{bmatrix}1&0&0\\0&1&0\\0&0&1\end{bmatrix}}_{\textstyle I}}^{\textstyle a-\frac{1}{2}}}^{\textstyle a}}^{\textstyle 2} $

$ \vec{v'} = q\vec{v}q^{-1} = (a+\vec{u}) \ \vec{v} \ (a-\vec{u}) = 2(({u}\cdot{v})\vec{u} + a(\vec{u}\times\vec{v}) + (a^2-\frac{1}{2})\vec{v}) $

$ R_q = 2(({u}\otimes{u}) +a[u]_{\times} +(a^2-\frac{1}{2})I) $

