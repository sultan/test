##### axis angle to rotation matrix

$ R_u = \begin{bmatrix} 1+(-\ c^2-d^2)(1-\cos\theta) & bc(1-\cos\theta)-d\sin\theta & bd(1-\cos\theta)+c\sin\theta \\ bc(1-\cos\theta)+d\sin\theta & 1+(-\ b^2-d^2)(1-\cos\theta) & cd(1-\cos\theta)-b\sin\theta \\ bd(1-\cos\theta)-c\sin\theta & cd(1-\cos\theta)+b\sin\theta & 1+(-\ b^2-c^2)(1-\cos\theta) \end{bmatrix} $

##### TODO

$ R_u = \overbrace{\underbrace{\begin{bmatrix}1&0&0\\0&1&0\\0&0&1\end{bmatrix}}_{\textstyle I}}^{\textstyle 1} + \overbrace{\underbrace{\begin{bmatrix}-\ c^2-d^2&bc&bd\\bc&-\ b^2-d^2&cd\\bd&cd&-\ b^2-c^2\end{bmatrix}}_{\textstyle ([u]_{\times})^2}}^{\textstyle (1-\cos\theta)} + \overbrace{\underbrace{\begin{bmatrix}0&-d&c\\d&0&-b\\-c&b&0\end{bmatrix}}_{\textstyle [u]_{\times}}}^{\textstyle \sin\theta} $

$ R_u = I + ([u]_{\times})^2(1-\cos\theta) + [u]_{\times}\sin\theta $

$ \vec{v'} = \vec{v} + (\vec{u}\times(\vec{u}\times\vec{v}))(1-\cos\theta) + (\vec{u}\times\vec{v})\sin\theta $

##### TODO

$\color{lightgray} R_q = I + 2[u]_{\times}([u]_{\times} + aI) $

$\color{lightgray} \vec{v'} = \vec{v} + \vec{u}\times((\vec{u}\times\vec{v})(1-\cos\theta) + \vec{v}\sin\theta) $

$\color{lightgray} R_u = I + [u]_{\times}([u]_{\times}(1-\cos\theta) + I\sin\theta) $

$\color{lightgray} R_u = I + \begin{bmatrix}0&-d&c\\d&0&-b\\-c&b&0\end{bmatrix}\bigg(\begin{bmatrix}0&-d&c\\d&0&-b\\-c&b&0\end{bmatrix}(1-\cos\theta) + I\sin\theta\bigg) $

