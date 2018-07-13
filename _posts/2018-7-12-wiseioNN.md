---
layout: post
title: Music Generation using Text Generation
keywords: 
  - Music Generation
  - Neural Networks
---
In this post, we'll look at Josh Bloom's method to music generation, of which a step-by-step description can be found [here](https://wise.io/2015/06/19/asking-rnn-and-ltsm-what-would-mozart-write/).

Josh uses the Humdrum \*\*kern format developed by Ohio State University to represent music in a character-based format, where each note is denoted by a group of symbols. For example, a quarter note middle c would be represented as *4c*.

Using the \*\* kern format, it is now possible treat the music as text, allowing the use of a text generating neural network to generate more music. In his blog, Josh uses Andrej Karpathy's [character-level recurrent neural network](https://github.com/karpathy/char-rnn).

Using a machine with Intel i5-7500 processor and a GeForce GTX 1070 NVIDIA GPU, it took me about 30 minutes to train 50 epochs. After training, I got the following result when the training data came from Mozart: <a href="/music/wiseioMozart.mp3" download>mozart.mp3</a>  
And from Beethoven: <a href="/music/wiseioBeethoven.mp3" download>beethoven.mp3</a>  

The music has good rhythm, and the piece is overall in the correct key. However, there's no melody, and the left hand has way too many notes for a classical piece. 




