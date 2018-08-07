---
layout: post
title: Fake News Detector
---
The Fake News Challenge (FNC) is a competition to explore how machine learning can contribute to the detection of fake news. The first stage of the challenge is to accomplish something called stance detection. Given a short headline and an article, we need to categorize the relationship between the article and headline into 4 categories: Disagree, Agree, Unrelated, and Discusses.

The organizers of the FNC gave a database, which can be found [here](https://github.com/FakeNewsChallenge/fnc-1-baseline). Unfortunately, this database is not very good because the Disagree and Agree categories are severely underrepresented, while there are far too many entries in the Unrelated category. We'll give a method for dealing with this.

Encoder-Decoder architecture is often used 

