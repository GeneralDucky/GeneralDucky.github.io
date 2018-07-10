---
layout: post
title: Music Generation with Neural Networks using Daniel Johnson's RNN
keywords: 
  - Neural Network
  - Music Generation
---

In this post, we'll examine a music generating neural network created by Daniel Johnson.

My machine uses Intel i5-7500 processor with a GeForce GTX 1070 NVIDIA GPU. Training data came from http://www.piano-midi.de/.  
A description of Daniel Johnson's neural network can be found at his [website](http://www.hexahedria.com/2015/08/03/composing-music-with-recurrent-neural-networks/).

If you don't have theano on your machine, you can find installation instructions for Ubuntu [here](http://deeplearning.net/software/theano/install_ubuntu.html).  

If your machine has a GPU, it's highly recommended to set up GPU drivers like CUDA, as this can speed up your training by several factors and help you avoid spending money. 

After 10000 epochs, which took me about 6 hours with GPU acceleration, I got the following piece of music:
<a href="/music/composition.mp3" download>composition.mp3</a>
  
Here are some samples taken while training:  
After 100 epochs: <a href="/music/hexasample100.mp3" download>sample100.mp3</a>
After 1000 epochs: <a href="/music/hexasample1000.mp3" download>sample1000.mp3</a>
After 5000 epochs: <a href="/music/hexasample5000.mp3" download>sample5000.mp3</a>

The network did a good job on rhythm (it's clear that the music is written in 4/4 time using standard note values). However, there's not really a clear melody. In addition, the music shifts keys several times, leading to dissonant chords.  


