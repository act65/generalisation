
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
\mathbf H_h = (I_p \otimes \nabla f^T)\cdot \mathbf H_g \cdot \nabla f + (\nabla_g \otimes I_n) \cdot \mathbf H_f \\
$$
