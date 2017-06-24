EmpiricalWhat does the evidence tell us?

## Empircical evidence

__Exhibit 1.__ Memorisation of noise

DNNs can learn to shatter noise.

__Exhibit 2.__ Speed of learning (un)structured data

DNNs learn structured data faster than unstructured.

(structured meaning there is some structure/pattern to the inputs and their associated labels, in contrast, random labelings of inputs -should- have no structure)

__Exhibit 3.__ Robustness to label noise

Even with extra ordinary amounts of label noise, it is still possible learn patterns.

__Exhibit 4.__ Small pertubations to inputs cause problems

Adversarial pertunations of an inputs can `easily` change its labelling.

## Deductive evidence

__Exhibit 1.__ The stability of minima can be arbitrarily scaled

Let $a$ be some constant value and $\rho$ be a non-negative homogenous function such that $\rho(ax) = a\rho(x)$. Then

__TODO__. this doesnt work, yet.
$$
\begin{align}
\rho(W_{i+1}\rho(W_ix)) &= \rho(aW_{i+1}\rho(a^{-1}W_ix))  \\
\frac{\partial y}{\partial W_i} = I \otimes \rho(W_ix)&\neq a I \otimes \rho(W_ix) \\
\end{align}
$$

_So we can arbitrarily scale a to be very large, while giving the same result. However, a small pertubation to_ $W_i$ _is now different. It is scaled by a._
