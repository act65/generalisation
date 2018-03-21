## Flat/sharp minima

<!--
- Minima w.r.t what? Inputs, parameters, outputs?
- Flatness wrt to what? Inputs, parameters, perturbations, test data, ?

What about other types of minima?
- strongly convex??
- ??
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

__Definition 5.__ Imperfect stability metric

Given $x in \mathbb R^n, \epsilon > 0$ and $A \in\mathbb  R^{n\times p}$, we define the $(C_{\epsilon},A)$-sharpness of $f$ at $x$ as:

$$\phi_{x,f} (\epsilon, A) = max_{y\in C_{\epsilon}} \frac{f(x + Ay) - f(x)}{1+f(x)}$$


<!-- The maximum direction (in A) computed via finite difference -->



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


__Definition 2.__ Risk

The generalisation error is defined as the difference between the expected risk and the empirical risk.

$$
\begin{aligned}
R[w] = \mathbb E_{z\sim D} \big[ f(w; z) \big] \\
R_S[w] = \frac{1}{n} \sum_n f(w; z_i) \\
\epsilon_{generalisation} = R_S[w] - R[w] \\
\end{aligned}
$$

__Definition 3.__ Expected extended generalisation error

$$
\begin{aligned}
\mathbb E_G(D, D_0) = \sum_{h\in H} p(h \mid D_0) \mathbb E(D\backslash D_0, h) - \sum_{h\in H} p_{D_0}(h \mid D) \mathbb E(D\backslash D_0, h)
\end{aligned}
$$

* Over-fitting error: relevant for measuring the learner has focused too much on the training set.
* Under-fitting error: relevant for measuring whether the learner sufficiently approximates the training set.

?? Can be formulated as the integrals of the difference between the models trained on empirical and true data.

__Definition 4.__ Performance on some other metric

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

This is nice? We are really asking, how does training on loss F generalise to loss G?

__Definition 5.__ Invariance to transforms

A models ability to generalise is measured as the size of the set of possible transforms that our learned function is invariant to.

$$
\mathcal G = \big\{ t\in \mathcal T: f_{\theta}(x) \approx f_{\theta}(t(x))\big\}
$$

E.g. Take a sentence, perturb it (rearrange words, use different words), yet the meaning still remains the same. (in contrast to memory, which would not understand the transformed input, as it has not been observed)

We would expect our function to be invariant to __all__ types of `noise` (define 'noise' here).

This actually implies that $\mathcal X$ is generated by

$$
\begin{aligned}
\mathcal X :&= \mathcal T \times \mathcal X_{base} \\
&= \{ t(x) : t \in \mathcal T ,x \in \mathcal X_{base}\} \\
\end{aligned}
$$
<!-- See Sokolic 20176 -->

<!--
What is the conserved quantity?!? If we transform x, with t(x), and still get the same result, then some type of information much have been conserved? -->

<!-- It seems funny that this formulation has nothing to do with the loss function. Although it does have implications for the loss.

Invariance to transforms implies that the transform is low rank in some way, collapsing in certain directions. Or that the jacobian has some structure (not full rank) and can be decomposed.
 -->

#### Overfitting



#### Underfitting



## Memorization

__Definition 1.__ Zhang et al.

> We operationalize the definition of “memorization” as the behavior exhibited by DNNs trained on noise.

Bit I assume they mean; the behaviour exhibited by DNNs trained on `noise`, that reach some low training loss. Ie the phonomena in Zhang et al.

<!-- There are a few ways to train on noise. Some actually are helpful. Define training on noise -->

__Definition 2.__ Explicit representation of the data

No compression.

__Definition 3.__ ???


## Stability (aka robustness?)

__Definition 1.__ Sensitivity measured with gini

 <!-- Does the frequency distribution need to be centered, or around zero? -->

__Definition 2.__ (something from dynamical systems?)



<!-- ## Complexity () they are really talking about stablity? how easily labels can be flipped.-->

__Definition 1 or 3?.__ Critical sample ratio

$$
\begin{aligned}
argmax_i f_i(x) \neq argmax_j f_j(\hat x) \\
s.t. \; \parallel x-\hat x\parallel_{\infty} \le r \\
\end{aligned}
$$


__Definition 4.__

A randomized algorithm A is $\epsilon$-uniformly stable if for all data sets $S,S' \in Z_n$ such that $S$ and $S$? differ in at most one example, we have

$$
sup_z \mathbb E_A \big[ f(A(S), z)-f(A(S'), z) \big] \le \epsilon
$$


__Definition 5.__ Stable learning algorithm

Consider the algorithm $A$ and the hypothesis $A_{S_m}(x)$. The learning algorithm $A$ is stable if for any training set $S_m$
$$
max_{x\in\mathbb R^N} \parallel J(x)\parallel_2 \le 1
$$
where $\parallel · \parallel_2 denotes the spectral norm.



## Complexity

__Definition 1.__ Central limit theorem

$$
R(\hat f) \le R_{emp}(\hat f) + \frac{\sqrt{Var_{x,y} l(\hat f(x), y)}}{\sqrt N}
$$

__Definition 2.__ Minimum description length


__Definition 3.__ Magnitude of the derivative

What about change in the hessian, or higher orders? Some sort of weighted sum of these (up to infinity... at some point -- which point -- they will go to zero) makes the most sense to me.

A simple function is linear. A complex function is non-linear. 
But a simple 'first-order' non-linear function could have constant hessian, making it 'simpler' than a function with changing hessian?!

When the inputs change the outputs change in 'predictable' ways.

Closely related to Lipchitz?
