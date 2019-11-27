##### quaternion to rotation matrix

$ R_q = \begin{bmatrix} a^2+b^2-c^2-d^2 & 2bc-2ad & 2bd+2ac \\ 2bc+2ad & a^2-b^2+c^2-d^2 & 2cd-2ab \\ 2bd-2ac & 2cd+2ab & a^2-b^2-c^2+d^2 \end{bmatrix} $

+++

$ \vec{v'} = q\vec{v}q^{-1} = (a+\vec{u}) \ \vec{v} \ (a-\vec{u}) = (a^2+({u}\cdot{u}))\vec{v} + 2\vec{u}\times((\vec{u}\times\vec{v}) + a\vec{v}) $

$ R_q = (a^2+({u}\cdot{u}))I + 2[u]_{\times}([u]_{\times} + a) $

+++

$ R_q = \overbrace{\underbrace{\begin{bmatrix}1&0&0\\0&1&0\\0&0&1\end{bmatrix}}_{\textstyle I}}^{\textstyle a^2} + \overbrace{\underbrace{\begin{bmatrix}1&0&0\\0&1&0\\0&0&1\end{bmatrix}}_{\textstyle I}}^{\textstyle b^2+c^2+d^2} + \overbrace{\underbrace{\begin{bmatrix}-\ c^2-d^2&bc&bd\\bc&-\ b^2-d^2&cd\\bd&cd&-\ b^2-c^2\end{bmatrix}}_{\textstyle ([u]_{\times})^2}}^{\textstyle 2} + \overbrace{\underbrace{\begin{bmatrix}0&-d&c\\d&0&-b\\-c&b&0\end{bmatrix}}_{\textstyle [u]_{\times}}}^{\textstyle 2a} $

$ R_q = a^2I + ({u}\cdot{u})I + 2([u]_{\times})^2 + 2a[u]_{\times} $

$ \vec{v'} = q\vec{v}q^{-1} = (a+\vec{u}) \ \vec{v} \ (a-\vec{u}) = a^2\vec{v} + ({u}\cdot{u})\vec{v} + 2\vec{u}\times(\vec{u}\times\vec{v}) + 2a(\vec{u}\times\vec{v}) $

+++

$ \vec{v'} = q\vec{v}q^{-1} = (a+\vec{u}) \ \vec{v} \ (a-\vec{u}) = (a^2-({u}\cdot{u}))\vec{v} + 2(\vec{u}({u}\cdot{v}) + a(\vec{u}\times\vec{v})) $

$ R_q = (a^2-({u}\cdot{u}))I + 2(({u}\otimes{u}) + a[u]_{\times}) $

+++

$ R_q = \overbrace{\underbrace{\begin{bmatrix}1&0&0\\0&1&0\\0&0&1\end{bmatrix}}_{\textstyle I}}^{\textstyle a^2} - \overbrace{\underbrace{\begin{bmatrix}1&0&0\\0&1&0\\0&0&1\end{bmatrix}}_{\textstyle I}}^{\textstyle b^2+c^2+d^2} + \overbrace{\underbrace{\begin{bmatrix}bb&bc&bd\\bc&cc&cd\\bd&cd&dd\end{bmatrix}}_{ \textstyle ({u}\otimes{u})}}^{\textstyle 2} + \overbrace{\underbrace{\begin{bmatrix}0&-d&c\\d&0&-b\\-c&b&0\end{bmatrix}}_{\textstyle [u]_{\times}}}^{\textstyle 2a} $

$ R_q = a^2I - ({u}\cdot{u})I + 2({u}\otimes{u}) + 2a[u]_{\times} $

$ \vec{v'} = q\vec{v}q^{-1} = (a+\vec{u}) \ \vec{v} \ (a-\vec{u}) = a^2\vec{v} - ({u}\cdot{u})\vec{v} + 2\vec{u}({u}\cdot{v}) + 2a(\vec{u}\times\vec{v}) $

+++

$ \vec{v'} = q\vec{v}q^{-1} = (a+\vec{u}) \ \vec{v} \ (a-\vec{u}) = a^2\vec{v} + \vec{u}({u}\cdot{v}) + \vec{u}\times((\vec{u}\times\vec{v}) + 2a\vec{v}) $

$ R_q = a^2I + ({u}\otimes{u}) + [u]_{\times}([u]_{\times} + 2a) $

+++

$ \vec{v'} = q\vec{v}q^{-1} = (a+\vec{u}) \ \vec{v} \ (a-\vec{u}) = a^2\vec{v} + \vec{u}({u}\cdot{v}) + \vec{u}\times(\vec{u}\times\vec{v}) + 2a(\vec{u}\times\vec{v}) $

$ R_q = a^2I + ({u}\otimes{u}) + ([u]_{\times})^2 + 2a[u]_{\times} $

$ R_q = \overbrace{\underbrace{\begin{bmatrix}1&0&0\\0&1&0\\0&0&1\end{bmatrix}}_{\textstyle I}}^{\textstyle a^2} + \overbrace{\underbrace{\begin{bmatrix}bb&bc&bd\\bc&cc&cd\\bd&cd&dd\end{bmatrix}}_{ \textstyle ({u}\otimes{u})}}^{\textstyle 1} + \overbrace{\underbrace{\begin{bmatrix}-\ c^2-d^2&bc&bd\\bc&-\ b^2-d^2&cd\\bd&cd&-\ b^2-c^2\end{bmatrix}}_{\textstyle ([u]_{\times})^2}}^{\textstyle 1} + \overbrace{\underbrace{\begin{bmatrix}0&-d&c\\d&0&-b\\-c&b&0\end{bmatrix}}_{\textstyle [u]_{\times}}}^{\textstyle 2a} $

+++

