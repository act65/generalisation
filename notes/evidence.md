What does the evidence tell us?


Since we want to study generalisation error, we need to control for approximation and optimisation error, we should expect that;

* models are trained until their gradient norm is less than some threshold (ie progress has slowed to a crawl). So we are not worried about under-fitting.
* models are more than large enough (flexibility: $n$ of parameters) and complex enough (capacity: non-linearity, depth, ?) to contain the `true` (or just some $\epsilon$-approximation?) hypothesis (but how easily findable is it?).
<!-- Capacity vs flexibility -  reminds me of a basis and coefficients. -->


## Empirical evidence

__Exhibit 1.__ Memorisation of noise

DNNs can learn to shatter noise.

__Exhibit 2.__ Robustness to label noise

Even with extraordinary amounts of label noise, it is still possible learn patterns.

__Exhibit 3.__ Structured label noise

> We observe that both alternative sources of noise lead to better performance than the noise originating from the same dataset.

__Exhibit 3.__ Speed of learning noised data

DNNs learn un-noised data faster than noised.

(unnoised meaning there is some structure/pattern to the inputs and their associated labels, in contrast, random labelings of inputs -should- have no structure)

__Exhibit 4.__ Small pertubations to inputs cause problems

Adversarial pertunations of an inputs can `easily` change its labelling.

__Exhibit 5.__ Batch size effects generalisation



<!-- Potential qualms with this evidence.
- How does training time effect this?
- What about learning rate?
- Is that just due to batch norm?
 -->


__Exhibit 5.__ The distribution of eigenvalues of the hessian is ???

Lots of small ones, few negative ones, a very small number of large positive values.

__Exhibit 6.__ Samples near the decision boundary

We now show that the number of critical samples is much higher for a deep network (specifically, a CNN) trained on noise data compared with real data.
<!-- What about other adversarial perturbations? -->

## Proofs

__Theorem 1.__ The stability of minima can be arbitrarily scaled

Let $a$ be some constant value and $\rho$ be a non-negative homogenous function such that $\rho(ax) = a\rho(x)$. Then

__TODO__. this doesnt work, yet.
$$
\begin{aligned}
W_{i+1}\rho(W_ix) &= aW_{i+1}\rho(a^{-1}W_ix)  \\
\frac{\partial y}{\partial W_{i+1}} = I \otimes \rho(W_ix)&\neq a I \otimes \rho(a^{-1}W_ix) \\
\end{aligned}
$$

_So we can arbitrarily scale a to be very large, while giving the same result. However, a small pertubation to_ $W_i$ _is now different. It is scaled by a._

<!-- But the key question is what sort of minima does SGD tend to settle on? So what if they can be arbitrarily scaled, they arent in reality. -->

<!-- But wait a minute. For everything we make more sensitive, we have to make something else less sensitive, so the distribution of sensitivity over all parameters is conserved? -->

<!-- Doesnt actually apply to NNs. bias screws up proof -->

__Theorem 2.__ Flat minima w.r.t parameters are simpler hypotheses

> ... that flatness results in robustness to low precision arithmetic or noise in the parameter space, which, using an minimum description length-based argument, suggests a low expected overfitting.

Higher precision can give higher frequency changes, making it possible to be sharper.

<!-- A lot of these conjectures state that it must be a cts flat minima. Why? Discts could also work? -->


__Theorem 3.__ The generalisation error of invariant classifiers

> We prove that given a learning method invariant to a set of transformations of size T, the GE of this method may be up to a factor √T smaller than the GE of a non-invariant learning method.
