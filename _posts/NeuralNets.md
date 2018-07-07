---
layout: post
title: Music Generation with Neural Networks
keywords: 
  - Neural Network
---

In this post, we'll examine a few music generating neural networks. We'll present some generated music first, then we'll try to edit the neural networks to see if we can do better.  

My machine uses Intel i5-7500 processor with a GeForce GTX 1070 NVIDIA GPU.
### Initial Results without edits

We start off with results from [Daniel Johnson's](http://www.hexahedria.com/2015/08/03/composing-music-with-recurrent-neural-networks/) recurrent neural network. Training data came from http://www.piano-midi.de/.  

After 10000 epochs, which took me about 6 hours with GPU acceleration, I got the following:
<a href="/music/composition.mp3" download>composition.mp3</a>

The network did a good job on rhythm (it's clear that the music is written in 4/4 time using standard note values). However, there's not really a clear melody. In addition, the music shifts keys several times, leading to dissonant chords.  

