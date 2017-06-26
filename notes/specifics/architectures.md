## Path sums

Let $x \in \mathbb R^p, y \in \mathbb R^q$. Let $\sigma$ be some element wise non-linearity. Assume $q = 1$ for simplicity.

Let a __wide__ network be the transform $f_{wide}(x) = A\sigma (Bx)$ such that $A \in \mathbb R^{q\times n}, B\in\mathbb R^{n\times p}$. Then $f_{wide}(x)$ is a path sum over $n\times p$ paths.

Let a __deep__ network be a transform, of depth $d$ and width $w$. $f_{deep}(x) = W_{d_k}\sigma(... W_{d_i}\sigma (... \sigma(W_{d_1}x)))$. Let $w = p$ for simplicity. Then $f_{wide}(x)$ is a path sum over $w^d$ paths.

NOTE: groups of paths are `entangled` by the non-linearities. This makes it hard to write down...

Pick two networks, $f_{wide}, f_{deep}$, such that they have the same number of paths, $n\times p = w^d$. The wide network has many more parameters than the deep network, as the deep network shares parameters across its paths. (TODO a picture would be good)

<!-- And the deep network has many more non-linearities? -->

Because of this sharing;

* the `sample complexity per parameter ratio` is lower. (parameters are trained on more data). Just like in 'typical' weight sharing.
* Gradients contain `more information` about how to change each parameter. More feedback is provided because each parameter is used more times.
* The `noise along each path` cancels, but the patterns remain. More data means a stronger ratio between patterns and noise. Like more accurate estimates of the gradients. Reduced bias and reduced variance? (but werent we arguing for noisy estimates???). So for a given parameter, $\theta_k$, path $p_i$ says do X given $x_a$ and path $p_j$ says do Y given $x_b$, etc... Averaged over a very large number of ...?s
*


This forces the parameters (especially ones early in the network) to generalise across many tasks/paths.

<!-- This means that these learned do actually build from simple-> complex. As the lower layers will quickly converge, due to the high redundancy in the signal, due to many paths sharing those weights, ...  -->

Each path is calculating something distinct. But by sharing parameters, ...?
