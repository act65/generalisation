> Random intuitions, yet to be made precise.

## The area under the curve

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


Is it really true that we that we care exactly about the area under the curve?
So our problem is not only minimising $\mathcal L(x, \theta)$ but ... . How are these related? The only solution is to have some prior on how the surface behaves between data points.
If it has some regular frequency, then is probably should have one here.

## Sorting through hypotheses.

Pick learners with low under-fitting error, then of those pick the ones with low over-fitting error.

Can this be done on mini-batches? We can easily falsify a set of learners/hypotheses if they do not work on a given batch.

```
# find plausible hypotheses.
# ones that have laernt something about the data
for batch in batches:
  # super quick training. high lr, a single batch
  model.train(batch)  
  if model.low_error(batch)
    low_underfit.append(model)
  model.reset()

# pick out the ones that generalise
for model in low_underfit:
  if model.low_error(valid_data):
    best_models.append(model)
```

reminds me of ensemble methods. would be nice to combine the remaining models.

What if we could sort a function? Think of sorting as a transform that can be applied.
Sorting $L(\theta)$ requires evaluating it a bunch of times. Expensive. Is there such a thing as black box sorting?


***

Generalisation is the ability to abstract some pattern from domain X, and successfully apply it to domain Y.

Could design a good experiment for this?
