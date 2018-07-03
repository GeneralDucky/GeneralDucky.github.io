---
layout: post
title: Installing Eclipse (Linux)
---
## About Eclipse

Eclipse is an integrated development environment (IDE) made for Java.  It's possibly the most popular IDE, considering that it is free, easy to use, has numerous plugins, and has a large community.  The latest release as of this post is Eclipse 4.8 Photon, released on June 27, 2018.

## Installation

Eclipse offers 2 different installation methods: the Eclipse installer, or an individual package.  The Eclipse installer is better for people who are interested in installing multiple Eclipse packages, while the individual package is better suited for people who specialize in one programming language.

### 1. Make sure you have Java Development Kit (JDK) installed

To see if you have JDK installed, run the following command

```bash
$ java -version
java version "1.8.0_151"
Java(TM) SE Runtime Environment (build 1.8.0_151-b12)
Java HotSpot(TM) 64-Bit Server VM (build 25.151-b12, mixed mode)
```

The terminal should return something like the example given.

If you're running Java 8, consider upgrading to Java 10, as Oracle will no longer be supporting it.  Be warned, though, as Java 8 is not fully compatible with Java 10.  [Download Java 10 here.](http://www.oracle.com/technetwork/java/javase/downloads/index.html, "Link to Java 10 Downloads")

If the terminal did NOT return somthing resembling the example, you need to install JDK.