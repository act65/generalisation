There are a few different types of error when learning;
approximation, optimization and estimation error.

* Approximation error is due to the limits of your approximator/function class
* Optimisation error is due to the fact that we normally truncate the optimisation process before it converges. Aka early stopping.
* Estimation error is due to the fact that we dont have access to the true data distribution, but rather empirical estimate.
<!-- * ?? error (what other types of error are there) -->

In this we explore estimation error, aka generalisaion (although, ). And is closely related to over/under fitting.

So to control for approximation and optimisation error, we should expect that;

* models are trained until their gradient norm is less than some threshold (ie progress has slowed to a crawl).
*

What about how the size of the networks effects generalisation? A separate topic. So what is this topic? How does learning dynamics effect generalisation.

Is it really sensible to consider only learning dynamics w.r.t generalisation? Other factors include; representation, capacity, (which also effect the learning dynamics?!? argh too complex...)

Should charachterise the connection between generalisation and under/over fitting? Define under/over fitting.
