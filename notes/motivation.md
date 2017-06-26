> Why do we care about generalisation?

If we could generalise perfectly we would only every need to (from) learn one thing.
Small data wouldn't be an issue. Domain transfer, no problem.

The question is, what cost to we have to pay for this?


<!-- Generalisation could be interpreted as a hierarchical structure? -->
Normally we think of generalisation as capturing some abstract pattern, allowing us to distinguish signal from noise. But this can happen at many different levels
For example: Learning to navigate a city

```
Signal: the connections between roads (a big graph)
Noise: dead ends, driveways,
  Signal: road names, iconic buildings
  Noise:
    Signal: stuff that moves
    Noise: lighting conditions, rain(bows), the sky
```

We have 'general' patterns of all sort of different levels. Buildings are defined by X, a set of roads are abstracted as Y,

Reminds me of how computer science and math is about finding the most abstract/general core of a problem and studying that. This is the goal of `generalisation` (this is yet another sense of generalisation? how does it relate??)?

<!-- What we really want is a handle into these different levels of generalisation/pattern. SO we can pass them around, use them here and there. -->
