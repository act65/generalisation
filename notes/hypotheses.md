Why does the combination of NNs and SGD generalise so well?

> What do these candidate hypotheses (to explain ?)? How can they be falsified?

__Conjecture 1.__ Bouncing around with SGD

SGD works because it is noisy, it bounces around, and is more likely to bounce out of sharp minima than flat minima. Therefore SGD learns flat minima.
Therefore SGD generalises better.

_Could calculate non-stochastic gradients and then test with/without added stochasticity. Would like a proof showing that it is easier to bounce out of sharp minima (it seems intuitively obvious). what conditions are necessary for this to occur, some L-liptschitz fn?_

<!-- This argument is very reminiscent of how simulated annealing is supposed to work -->

<!-- Or is it that SGD produces a special type of stochasticity that random gaussian noise does not capture.  -->

<!--
How can this actually be tested?
Will need to control for ???
Deep nets have the advantage that they can build more complex functions from fewer parameters,

Ohhh. I think I see?
 -->

<!-- There is always some way to rescale layers such that the number of eigenvalues of the hessian greater than $M$ is $r−min_{k\in K}(n_k)$. -->

__Conjecture 2.__ Stochasticity for exploration

A distinct hypothesis from bouncing out of sharp minima is the use of stochasticity to explore many locally connected regions. The idea is that learning occurs in two phases, exploration and gradient descent.

How is this similar/different to sharp/flat minima? We could bounce between many different wide minima, while searching for a low, wide minima. (so this is less about finding general patterns and more about finding 'good' patterns, what is the difference?)

__Conjecture 3.__ Rank dependent sensitivity

Wide networks tend to have fewer large eigenvalues than deep networks. Large eigenvalues lead to sharp minima which dont generalise well. Therefore, wide nets generalise better. See Proof ?.


__Conjecture 4.__ Simple patterns are learned first

DNNs learn `simple` patterns first, before memorizing.
Easier examples are explained by some simple patterns, which are reliably learned within the first epoch of training.

_How would we prove this?_

__Conjecture 5.__ Repeated patterns are learned faster

Because we see the `same thing` more often, we have more gradient updates along a given direction, thus generalisable patterns are learned first and memorisation is not requires (or is only required to fit noise).

Data is structured. Structure means there are some shared factors. Every data point hints at this structure. ...

<!-- !!! Deep nets. Early layers get more feed back because there are exponentially more paths that each do their won thing. So weights are shared across many paths. Therefore faster learning? And generalisation. -->

__Conjecture 6.__ Restricted capacity

> This result contradicts the intuitions of traditional learning theory, which suggest that capacity should be restricted, in order to enforce the learning of (only) the most regular patterns.
