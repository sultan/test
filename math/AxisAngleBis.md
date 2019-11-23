##### axis angle to rotation matrix

$ R_u = \begin{bmatrix} bb+(-\ c^2-d^2)(-\cos\theta) & bc(1-\cos\theta)-d\sin\theta & bd(1-\cos\theta)+c\sin\theta \\ bc(1-\cos\theta)+d\sin\theta & cc+(-\ b^2-d^2)(-\cos\theta) & cd(1-\cos\theta)-b\sin\theta \\ bd(1-\cos\theta)-c\sin\theta & cd(1-\cos\theta)+b\sin\theta & dd+(-\ b^2-c^2)(-\cos\theta) \end{bmatrix} $

$ R_u = \begin{bmatrix} bb+(bb-1)(-\cos\theta) & bc(1-\cos\theta)-d\sin\theta & bd(1-\cos\theta)+c\sin\theta \\ bc(1-\cos\theta)+d\sin\theta & cc+(cc-1)(-\cos\theta) & cd(1-\cos\theta)-b\sin\theta \\ bd(1-\cos\theta)-c\sin\theta & cd(1-\cos\theta)+b\sin\theta & dd+(dd-1)(-\cos\theta) \end{bmatrix} $

##### TODO

$ R_u = \overbrace{\underbrace{\begin{bmatrix}bb&bc&bd\\bc&cc&cd\\bd&cd&dd\end{bmatrix}}_{ \textstyle ({u}\otimes{u})}}^{\textstyle 1} - \overbrace{\underbrace{\begin{bmatrix}-\ c^2-d^2&bc&bd\\bc&-\ b^2-d^2&cd\\bd&cd&-\ b^2-c^2\end{bmatrix}}_{\textstyle ([u]_{\times})^2}}^{\textstyle (\cos\theta)} + \overbrace{\underbrace{\begin{bmatrix}0&-d&c\\d&0&-b\\-c&b&0\end{bmatrix}}_{\textstyle [u]_{\times}}}^{\textstyle \sin\theta} $

$ R_u = (u\otimes{u}) - (\cos\theta)([u]_{\times})^2 + (\sin\theta)[u]_{\times} $

$ \vec{v'} = \vec{u}(\vec{u}\cdot\vec{v}) - (\vec{u}\times(\vec{u}\times\vec{v}))(\cos\theta) + (\vec{u}\times\vec{v})\sin\theta $

