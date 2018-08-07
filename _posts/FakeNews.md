---
layout: post
title: Fake News Detector
---
The Fake News Challenge (FNC) is a competition to explore how machine learning can contribute to the detection of fake news. The first stage of the challenge is to accomplish something called stance detection. Given a short headline and an article, we need to categorize the relationship between the article and headline into 4 categories: Disagree, Agree, Unrelated, and Discusses.

We need a method for capturing the meaning of the article and the headline if we want to be able to categorize their relationship. One architecture that can vectorize the meaning of a block of text is the encoder-decoder neural network. We are specifically interested in the encoder part, which is responsible for capturing the meaning of a block of text for the decoder section to work with. The encoder section is often a stack of LSTM nodes, with each node accepting a new word from the input text. The hidden state of the last LSTM node can be thought of as a 



The organizers of the FNC provided a database, which can be found [here](https://github.com/FakeNewsChallenge/fnc-1-baseline). Unfortunately, this database is not very good because the Disagree and Agree categories are severely underrepresented, while there are far too many entries in the Unrelated category. We'll give a method for dealing with this later.



