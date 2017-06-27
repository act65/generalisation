There are a few different types of error when learning;
approximation, optimization and estimation error.
<!-- and ??? can i think of other types?
there are multiple parts to each?
estimation error could include- robustness, ?,  -->

* Approximation error is due to the limits of your approximator/function class
* Optimisation error is due to the fact that we normally truncate the optimisation process before it converges. Aka early stopping.
* Estimation error is due to the fact that we dont have access to the true data distribution, but rather empirical estimate.
<!-- * ?? error (what other types of error are there) -->

In this we explore estimation error, aka generalisaion (although, ). And is closely related to over/under fitting.

Questions we will explore;

* What is generalisation?
* How do the learning dynamics of optimisation effect generalisation?
* How does the `capacity` and `flexibility` of learners effect generalisation?

Is it really sensible to consider only learning dynamics w.r.t generalisation? Other factors include; representation, capacity, (which also effect the learning dynamics?!? argh too complex...)

Want to see plots of;
* optimisation error wrt training time (and learning rate/dynamics?)
* approximation error wrt n_parameters, architecture, non-linearities, ?
* generalisation error wrt sample complexity, ?

Ideally we could see optimisation error vs approximation error vs generalisation error. How?

<!-- Ahh. There are dependent on each other...
- Weight sharing changes smaple complexity
- non-linearities effect training dynamics
- optimisation algorithms work well with some architectures...
- ?

 -->
