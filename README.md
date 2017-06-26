There are a few different types of error when learning;
approximation, optimization and estimation error.

* Approximation error is due to the limits of your approximator/function class
* Optimisation error is due to the fact that we normally truncate the optimisation process before it converges. Aka early stopping.
* Estimation error is due to the fact that we dont have access to the true data distribution, but rather empirical estimate.
<!-- * ?? error (what other types of error are there) -->

In this we explore estimation error, aka generalisaion (although, ). And is closely related to over/under fitting.

So to control for approximation and optimisation error, we should expect that;

* models are trained until their gradient norm is less than some threshold (ie progress has slowed to a crawl). So we are not worried about under-fitting.
* models are more than large enough (flexibility: $n$ of parameters) and complex enough (capacity: non-linearity, depth, ?) to contain the `true` (or just some $\epsilon$-approximation?) hypothesis (but how easily findable is it?).
<!-- Capacity vs flexibility -  reminds me of a basis and coefficients. -->

What about how the size of the networks effects generalisation? A separate topic. So what is this topic? How does learning dynamics effect generalisation.

Is it really sensible to consider only learning dynamics w.r.t generalisation? Other factors include; representation, capacity, (which also effect the learning dynamics?!? argh too complex...)

Should charachterise the connection between generalisation and under/over fitting? Define under/over fitting.



Relation to;
* the bias-variance tradeoff,
* adversarial perturbations,
* ?


Want to see plots of ;
* optimisation error wrt training time (and learning rate/dynamics?)
* approximation error wrt n_parameters, architecture, non-linearities, ?
* generalisation error wrt sample complexity, ?

<!-- Ahh. There are dependent on each other...
- Weight sharing changes smaple complexity
- non-linearities effect training dynamics
- optimisation algorithms work well with some architectures...
- ?

 -->

Ideally we could ses optimisation error vs approximation error vs generalisation error. How?
