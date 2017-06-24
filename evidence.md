What does the evidence tell us?
__TODO__ would like to test these myself...
Reproductions of results, links to sources, ...

## Empirical evidence

__Exhibit 1.__ Memorisation of noise

DNNs can learn to shatter noise.

__Exhibit 2.__ Robustness to label noise

Even with extraordinary amounts of label noise, it is still possible learn patterns.

__Exhibit 3.__ Speed of learning noised data

DNNs learn un-noised data faster than noised.

(unnoised meaning there is some structure/pattern to the inputs and their associated labels, in contrast, random labelings of inputs -should- have no structure)

__Exhibit 4.__ Small pertubations to inputs cause problems

Adversarial pertunations of an inputs can `easily` change its labelling.

__Exhibit 5.__ Batch size effects generalisation



<!-- Potential qualms with this evidence.
- How does training time effect this?
- What about learning rate?
 -->


__Exhibit 5.__ The distribution of eigenvalues of the hessian is ???

Lots of small ones, few negative ones, a very small number of large positive values.

## Proofs

__Theorem 1.__ The stability of minima can be arbitrarily scaled

Let $a$ be some constant value and $\rho$ be a non-negative homogenous function such that $\rho(ax) = a\rho(x)$. Then

__TODO__. this doesnt work, yet.
$$
\begin{align}
W_{i+1}\rho(W_ix) &= aW_{i+1}\rho(a^{-1}W_ix)  \\
\frac{\partial y}{\partial W_{i+1}} = I \otimes \rho(W_ix)&\neq a I \otimes \rho(a^{-1}W_ix) \\
\end{align}
$$

_So we can arbitrarily scale a to be very large, while giving the same result. However, a small pertubation to_ $W_i$ _is now different. It is scaled by a._

<!-- But the key question is what sort of minima does SGD tend to settle on? So what if they can be arbitrarily scaled, they arent in reality. -->

<!-- But wait a minute. For everything we make more sensitive, we have to make something else less sensitive, so the distribution of sensitivity over all parameters is conserved? -->
