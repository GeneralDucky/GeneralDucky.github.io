---
layout: post
title: Installing Eclipse on Linux
---
## About Eclipse

Eclipse is an integrated development environment (IDE) made for Java.  It's possibly the most popular IDE, considering that it is free, easy to use, has numerous plugins, and has a large community.  The latest release as of this post is Eclipse 4.8 Photon, released on June 27, 2018.

## Installation

Eclipse offers 2 different installation methods: the Eclipse installer, or an individual package.  Use the individual packages: they take up less space and are easier to remove.

### 1. Make sure you have Java Development Kit (JDK) installed

To see if you have JDK installed, run the following command

```
$ java -version
java version "1.8.0_151"
Java(TM) SE Runtime Environment (build 1.8.0_151-b12)
Java HotSpot(TM) 64-Bit Server VM (build 25.151-b12, mixed mode)
```

The terminal should return something like the example given.

If the terminal did NOT return somthing resembling the example, you need to install JDK.

### 2. Download Eclipse

Download the tarball from [Eclipse's website](https://www.eclipse.org/downloads/eclipse-packages/ "Eclipse downloads") and move it into the location of choice.  I recommend using `/usr/local/lib/`.

### 3. Extract the package

```
$ mv /your/download/location/eclipse-tarball-name.tar.gz /your/other/location/
$ cd /your/other/location/
$ tar xvfz eclipse-tarball-name.tar.gz
Random information about files
More random information
Some more information
Done
```

### 4. Change owners and permissions

`tar` will not set the user and group automaticlly, so you can set it yourself.

```
$ chown -R username:groupname eclipse
$ chmod 775 -R eclipse
```

### 5. Execute

Execute Eclipse by running the following commands.

```
$ cd eclipse/
$ ./eclipse
```

Pin Eclipse to your toolbar so you don't have to run Eclipse from the terminal.