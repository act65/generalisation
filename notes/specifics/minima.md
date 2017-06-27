
$$
\frac{\partial L}{\partial x_i} =
\frac{\partial L}{\partial o_i}
\frac{\partial o_i}{\partial \theta}
\frac{\partial \theta}{\partial x_i}
$$

So if $\frac{\partial L}{\partial o_i} \frac{\partial o_i}{\partial \theta}$ is `flat` then it makes it `easier` for $\frac{\partial L}{\partial x_i}$ to be `flat`.


***
Balduzzi's eqn

$$
f \circ g = h \\
\mathbb R^n \mathop{\rightarrow}^f \mathbb R^m \mathop{\rightarrow}^g \mathbb R^p \\
(\nabla_g \otimes I_n) \cdot \mathbf H_f  + (I_p \otimes \nabla f^T)\cdot \mathbf H_g \cdot \nabla f = \mathbf H_h\\
$$

Where we know that;
*  $g$ is convex, therefore $\mathbf H_g$ is positive semi-definite.


***

Flat minima imply local symmetry (as at the minima the function is invariant to transforms.) But what sort of symmetry is this??
Which symmetries would we want to be invariant to? Or there many/any we would want to be invariant to?
