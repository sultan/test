
#### Prerequisites

Cross product

---

#### Complex numbers

$a + b\ \mathbf i$

where $a$ and $b$ are real numbers and $i^2 = -1$

---

##### Addition

$(a_1 + b_1i) + (a_2 + b_2i) = (a_1 + a_2) + (b_1 + b_2)i$

---

##### Multiplication

$(a_1 + b_1i)(a_2 + b_2i) = (a_1a_2 - b_1b_2) + (a_1b_2 + a_2b_1)i$

---

##### Rotation examples

by 0°

$x' = x\\y' = y$

$\begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}$

by 90°

$x' = -y\\y' = x$

$\begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix}$

---

##### Rotation

$x' + y'i = (x + yi)(\cos\theta + i\sin\theta) \\ = (x\cos\theta - y\sin\theta) + (x\sin\theta + y\cos\theta)i \\ x' = x\cos\theta - y\sin\theta \\ y' = x\sin\theta + y\cos\theta$

---

##### Matrix

$\begin{bmatrix}\cos\theta & -\sin\theta \\ \sin\theta & \cos\theta\end{bmatrix}$

---

##### Composition of rotations

$e^{i\theta} \ e^{i\phi} = e^{i(\theta+\phi)}$

---

#### Quaternions

---

##### Definition

A quaternion q is defined by

$q = a + b\ \mathbf i + c\ \mathbf j + d\ \mathbf k$

TODO

$i^2 = j^2 = k^2 = -1 \\ ij=-ji=k \\ jk=-kj=i \\ ki=-ik=j$

---

##### Multiplication

TODO

$q_1q_2 = (a_1 + b_1i + c_1j + d_1k)(a_2 + b_2i + c_2j + d_2k)$

TODO

$\begin{align} & (a_1a_2 - b_1b_2 - c_1c_2 - d_1d_2) \\ + & (a_1b_2 + b_1a_2 + c_1d_2 - d_1c_2)\mathbf i \\ + & (a_1c_2 + c_1a_2 + d_1b_2 - b_1d_2)\mathbf j \\ + & (a_1d_2 + d_1a_2 + b_1c_2 - c_1b_2)\mathbf k \end{align}$

---

##### Scalar and vector parts

TODO

$q = (r + \vec u)$

$(a_1,\ \vec u_1)(a_2,\ \vec u_2) = (a_1a_2 - \vec u_1 \cdot \vec u_2,\ a_1 \vec u_2 + a_2 \vec u_1 + \vec u_1 \times \vec u_2)$

where "$\cdot$" is the dot product also called scalar product

and "$\times$" is the cross product also called vector product

---

##### Exp

$q = \cos\frac{\theta}{2} + \vec u\sin\frac{\theta}{2}$

---

##### Composition of rotations

$pq =  $

---

##### Vector rotation with quaternions

$\vec {v'} = q\vec vq^{-1} = (\cos\frac{\theta}{2} + \vec u\sin\frac{\theta}{2}) \ \vec v \ (\cos\frac{\theta}{2} - \vec u\sin\frac{\theta}{2}) \\ = \vec v\cos\theta + \vec u(\vec u\cdot\vec v)(1-\cos\theta) + (\vec u\times\vec v)\sin\theta \\ = \vec u(\vec u\cdot\vec v) + (\vec v-\vec u(\vec u\cdot\vec v))\cos\theta + (\vec u\times\vec v)\sin\theta$

$= \vec u(\vec u\cdot\vec v) + ((\vec u\times\vec v)\times\vec u)\cos\theta + (\vec u\times\vec v)\sin\theta \\ = \vec v + (\vec u\times(\vec u\times\vec v))(1-\cos\theta) + (\vec u\times\vec v)\sin\theta $

$\vec {v'} = q\vec vq^{-1} = (a + bi + cj + dk)(xi + yj + zk)(a - bi - cj - dk)$

$\vec {v'} = q\vec vq^{-1} = (s + \vec u) \ \vec v \ (s - \vec u) = \vec v + 2 \vec u \times ( \vec u \times \vec v + s \vec v)$

---

##### Matrix

from quaternion

$R = \begin{bmatrix} 1-2c^2-2d^2 & 2bc-2ad & 2bd+2ac \\ 2bc+2ad & 1-2b^2-2d^2 & 2cd-2ab \\ 2bd-2ac & 2cd+2ab & 1-2b^2-2c^2 \end{bmatrix}$

from axis and angle

$R = \begin{bmatrix} b^2(1-\cos\theta)+\cos\theta & bc(1-\cos\theta)-d\sin\theta & bd(1-\cos\theta)+c\sin\theta \\ bc(1-\cos\theta)+d\sin\theta & c^2(1-\cos\theta)+\cos\theta & cd(1-\cos\theta)-b\sin\theta \\ bd(1-\cos\theta)-c\sin\theta & cd(1-\cos\theta)+b\sin\theta & d^2(1-\cos\theta)+\cos\theta \end{bmatrix}$

---

##### References

https://en.wikipedia.org/wiki/Cross_product
https://en.wikipedia.org/wiki/Dot_product
https://en.wikipedia.org/wiki/Complex_number
https://en.wikipedia.org/wiki/Quaternion
https://en.wikipedia.org/wiki/Quaternions_and_spatial_rotation
https://en.wikipedia.org/wiki/Rotation_matrix
https://fgiesen.wordpress.com/2019/02/09/rotating-a-single-vector-using-a-quaternion/

[https://en.wikipedia.org/wiki/Rodrigues'_rotation_formula](https://en.wikipedia.org/wiki/Rodrigues'_rotation_formula)

https://en.wikipedia.org/wiki/List_of_trigonometric_identities

https://en.wikipedia.org/wiki/Triple_product#Vector_triple_product