---
layout: post
title: Installing Java Development Kit (JDK) on Linux
---
## About Java

Java was originally developed by Sun Microsystems, which was then incorporated into Oracle.  Even today, the most common version of Java is Oracle Java, although other versions exist, like OpenJDK and IBM Java

## Installation

First, decide which version of Java you wish to install.  This guide will install OpenJDK and Oracle Java.

### Check if Java is already installed

Run the following commands:

```
$ java -version
some stuff about java
```

If the output is NOT "Command not found", Java is already installed and running `update-alternatives` will be necessary.

### Installing Oracle Java

Download the tarball from [Oracle's website](http://www.oracle.com/technetwork/java/javase/downloads/jdk10-downloads-4416644.html).  Remember to accept Oracle's policy.

Extract the package by using

```
$ tar xvfz jdk-version_linux-x64_bin.tar.gz
Random information about files
More random information
Some more information
Done
```

where `version` is the version of JDK that you are installing.

### Installing OpenJDK

Download the tarball from [OpenJDK's website](http://jdk.java.net/10/ "OpenJDK downloads").

Extract the package by using

```
$ tar xvfz openjdk-version_linux-x64_bin.tar.gz
Random information about files
More random information
Some more information
Done
```

### Running `update-alternatives`

If there is already a previous version of Java installed, you need to run `update-alternatives` in order to configure Linux to use the version you just installed.  Use the following commands to configure the default version of Java,

```
$ update-alternatives --config java
There are 2 choices for the alternative java (providing /usr/bin/java).

  Selection    Path                                         Priority   Status
------------------------------------------------------------
  0            /usr/lib/jvm/java-11-openjdk-amd64/bin/java   ####      auto mode
  1            /usr/lib/jvm/java-11-openjdk-amd64/bin/java   ####      manual mode
* 2            /usr/lib/jvm/java-8-oracle/jre/bin/java       ####      manual mode

Press <enter> to keep the current choice[*], or type selection number: (enter selection number of preferred Java version)
$ update-alternatives --config javac
There are 2 choices for the alternative javac (providing /usr/bin/javac).

  Selection    Path                                          Priority   Status
------------------------------------------------------------
  0            /usr/lib/jvm/java-11-openjdk-amd64/bin/javac   ####      auto mode
  1            /usr/lib/jvm/java-11-openjdk-amd64/bin/javac   ####      manual mode
* 2            /usr/lib/jvm/java-8-oracle/bin/javac           ####      manual mode

Press <enter> to keep the current choice[*], or type selection number: (enter selection number of preferred Java version)
```

### Last checks

To fully ensure that you have actually installed Java, run the following:

```
$ java -version
Java(TM) SE Runtime Environment (build 1.8.0_151-b12)
Java HotSpot(TM) 64-Bit Server VM (build 25.151-b12, mixed mode)
$ which java
/path/to/java
```

You're done installing Java!  Have fun developing Java using your preferred method.
