
![pic](../assets/intuition.png)

This suggest that a small pertubation to $x$ should result in a small change in loss, if we want to generalise.

Want something like
$$
\begin{align}
\mathbb E[\mathcal L(x_i)] &= \sum_i p(x_i)\mathcal L(x_i) \\
&= \int \mathcal L(x)dx \tag{if x is uniform}
\end{align}
$$
the integral over all likely inputs. This is a way to measure the area under the graph. It should be easy to see that an approximation that generalises should have far lower area.
