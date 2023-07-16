---
layout: post
title: "Transformers: a historical tale"
categories: ml
---

# Transformers: A history of removing complexity
![image](https://github.com/fiskrt/minima/assets/43207511/94be79bd-de02-4f6f-91c3-48530583f10e)

It all starts with RNNs in 2014 [[1]](#1) $h_t=f(h_{t-1}, x)$. Of-course there is a longer and richer background before this, but in essence it all built up to that RNNs where degrading with length since the hidden state is overflowed with information, so instead of basing the next state on the previous we also have an aggregated context vector $c$ of the hidden states, but to prevent putting all previous information into one fixed-size vector, we select what is important and put more importance to those states. This is the fundamental idea of attention and should make a lot of intuitive sense, for example while you are reading these words your attention is  and to  and when we encode the sequence $x$ we get some hidden states $h_0, h_1, \ldots, h_T$


Given that the authors spent a combined 70 years at Google it is natural that the language they used is inspiried by search, formally retrieval systems. 

6,17.5,6,14,12,2,8,3

## References
<a id="1">[1]</a> 
[Neural Machine Translation by Jointly Learning to Align and Translate](https://arxiv.org/abs/1409.0473)
