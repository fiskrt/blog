---
layout: post
title: "Transformers: a historical tale of removing complexity"
categories: ml
---
![image](https://github.com/fiskrt/minima/assets/43207511/94be79bd-de02-4f6f-91c3-48530583f10e)

It all starts with RNNs in 2014 [[1]](#1) $h_t=f(h_{t-1}, x)$. Of-course there is a longer and richer background before this, but in essence it all built up to that RNNs where degrading with length since the hidden state is overflowed with information, so instead of basing the next state on the previous we also have an aggregated context vector $c$ of the hidden states, but to prevent putting all previous information into one fixed-size vector, we select what is important and put more importance to those states. This is the fundamental idea of attention and should make a lot of intuitive sense, for example while you are reading these words your attention is  and to  and when we encode the sequence $x$ we get some hidden states $h_0, h_1, \ldots, h_T$

![image](https://github.com/fiskrt/blog/assets/43207511/d5f7d344-d12d-4329-898c-f1fd033d6d35)

### Why use the terms query, key and value?
Given that the authors spent a combined 70 years at Google it is natural that the language they used is inspiried by search, formally retrieval systems.
We can demonstrate this in the following manner by thinking of a hash table. Let the content of the hash-table be $m$ rows of vectors where each vector is $n$ numbers, i.e the content is $V\in\mathbb{R}^{m\times n}$. Then we define $\alpha\in\mathbb{R}^m$ such that $\sum_{i=0}^m \alpha_i=1$. Then to look up row $j$ we set $\alpha_i=\delta_{ij}$ for all $i$ and do $\alpha^TV$.

$\alpha_i=$

To be continued...

### Why remove the encoder?
So Vaswani et al. took the leap by removing the reccurent part of the network but they were still thinking in terms of encoder and decoder architectures, specifacally machine translation. But it did not take them long to realize their invention was more general, and a few months later [[3]](#3) they removed the encoder and used it for generation.

simplied it further to make it more parallelizable and computational efficient 

### Attention is turing-complete
We can make a programming language out of a transformer encoder. I.e we can input a sequence and write a program that for example reverses the sequence, using a RASP compiler [[4]](#4) we can then compile this program into attention weights, such that when we input our sequence to the transformer, the output is the reverse sequence. But reversing 

## References
<a id="1">[1]</a> 
[Neural Machine Translation by Jointly Learning to Align and Translate](https://arxiv.org/abs/1409.0473)

<a id="2">[2]</a> 
[Attention Is All You Need](https://arxiv.org/abs/1706.03762)

Years at Google (in author order) 6,17.5,6,14,12,2,8,3

<a id="3">[3]</a> 
[Generating Wikipedia by Summarizing Long Sequences](https://arxiv.org/abs/1801.10198)

<a id="4">[4]</a> 
[https://github.com/tech-srl/RASP](https://github.com/tech-srl/RASP)

