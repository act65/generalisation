## Flat/sharp minima

<!--
- Minima w.r.t what? Inputs, parameters, outputs?
- Flatness wrt to what? Inputs, parameters, perturbations, test data, ?
-->

__Definition 1.__ Volume below some threshold

Given $\epsilon > 0$, a minimum $\theta$, and a loss $L$, we define $C(L, \theta, \epsilon)$ as the largest (using inclusion as the partial order over the subsets of $\theta$) connected set containing $\theta$ such that $\forall\theta' \in C(L, \theta, \epsilon),\;L(\theta') < L(\theta) + \epsilon$. The $\epsilon$- flatness will be defined as the volume of $C(L, \theta, \epsilon)$. We will call this measure the volume $\epsilon$-flatness

_The volume below some threshold around the neighborhood_

__Definition 2.__ The max within some neighborhood

Let $B2(\epsilon, \theta$) be an Euclidean ball centered on a minimum $\theta$ with radius $\epsilon$. Then, for a non-negative valued loss function L, the $\epsilon$-sharpness will be defined as proportional to
$max_{\theta'∈B2(\epsilon,\theta)} \frac{L(\theta') - L(\theta)}{1 + L(\theta)}$.

_The finite difference, or first order approximation (?), normalised by height?_

__Definition 3.__ Sensitivity to data

$\sum_{i} \frac{\partial L}{\partial x_i}$

_Makes sense intuitively? If we provide a new 'test' input,_ $x_t$ _then we would expect that the loss wouldnt change much, as the surface is quite flat._
<!--
I guess this is where the high dimensionality bites us?
Flatness in HD is hard?  
-->

__Definition 4.__ The curvature

The spectral norm of the hessian. Aka largest singular value. But what about the others singular values...?

<!--
But there are probably other measures of the curvature w.r.t flatness?
- different norms, or ??
-->

But we don't really care about negative curvature. Although it means we have an instability, it just results in increased performance. So we only care about positive curvature.



<!--
Would be nice to show either;
- these definitions are equivalent,
- they are talking about different things and have different implications.

- What about the ratio/distribution of sharpness in different dimensions?
-->
## Generalisation

> is the performance of our trained model on/doing some thing other than what it was trained for.

<!-- Closely related to transfer. Without it, we could claim that these things 'learn'. Would be closer to our idea of memorisation. -- what happened to that pic, sharp-> memorisation, smooth -> generalisation. -->

__Definition 1.__ Loss on different data

In general there are no restrictions of where this data comes from. However, we are often interested in a 'held-out' set of data produced by the same process as the training data. (why do we care?)

And this is - related to - under/overfitting and estimation error.

__Definition 2.__ Performance on some other metric

In general there are no restrictions on this metric. However, we are often interested in the case where our loss function and our evaluation metric share the same global minima. (for example, ce and accuracy?)
<!-- I would like to see a visual of ce and accuracy varying smoothly as a fn of the parameters or inputs -->


<!--
What about other restrictions we could put on the relationship between loss and metric?
* match local minima?
* match higher order gradients at minima?
* ?
-->

And this is - related to - transfer learning.
Multi task (not cross domain.)

__Definition 3.__ ???




## Memorization

__Definition 1.__ Zhang et al.

> We operationalize the definition of “memorization” as the behavior exhibited by DNNs trained on noise.

Bit I assume they mean; the behaviour exhibited by DNNs trained on `noise`, that reach some low training loss. Ie the phonomena in Zhang et al.

<!-- There are a few ways to train on noise. Some actually are helpful. Define training on noise -->

__Definition 2.__ Explicit representation of the data

No compression.

__Definition 3.__ ???


## Stability

__Definition 1.__
