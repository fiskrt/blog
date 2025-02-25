---
layout: post
title: "Cross-entropy: sanity check your NN classifiers."
categories: ml
---


It has turned out the neural networks are really good at classification. The largest neural networks today are 100k-250k classifiers.
For example the OG gpt-2 used a vocab size of 50k (later made to be an power of 2 for efficiency).

We then know what the loss value should start on because a neural network with intializers like xavier etc, will produce predictions
$\hat{y}\approx \frac{1}{2}$ hence the cross entropy is $\log C$ where C are the number of classes. So according to this the gemini loss curve
would start with $C=|V|$, $\log (250e10) = 12.4$ while GPT would start at 10.4.

After training for a while and reaching let's say 2.7 in nats, then we can say it's like being random classifier in $e^2.7$ classes, which would be 15 in this case.
So out of 50k tokens, we are predicting amongst 15 tokens of which one is correct. That is pretty good.

TODO: add pictures of loss curves

This is a good way to sanity-check your classifiers.