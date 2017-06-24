Why does the combination of NNs and SGD generalise so well?
Why does ?

> What are the candidate hypotheses (to explain ?)? How can they be tested?

__Conjecture 1.__ Bouncing around with SGD

SGD works because it is noisy, it bounces around, and is more likely to bounce out of sharp minima than flat minima. Therefore SGD learns flat minima.
Therefore SGD generalises better.

_Could calculate non-stochastic gradients and then test with/without added stochasticity. Would like a proof showing that it is easier to bounce out of sharp minima (it seems intuitively obvious). what conditions are necessary for this to occur, some L-liptschitz fn?_

__Conjecture 2.__ Rank dependent sensitivity

Wide networks tend to have fewer large eigenvalues than deep networks. Large eigenvalues lead to sharp minima which dont generalise well. Therefore, wide nets generalise better.

<!--
How can this actually be tested?
Will need to control for ???
Deep nets have the advantage that they can build more complex functions from fewer parameters,

Ohhh. I think I see?
 -->

<!-- There is always some way to resacle layers such that the number of eigenvalues of the hessian greater than $M$ is $r−min_{k\in K}(n_k)$. -->
