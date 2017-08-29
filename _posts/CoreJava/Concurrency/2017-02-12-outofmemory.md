---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Out Of Memory (OEM)"
teaser: "Various tools for find OEMs"
categories:
          - Core-Java
          - Concurrency
---

## Visualgc
Visualgc stands for Visual Garbage Collection Monitoring Tool and you can attach it to your instrumented hostspot JVM. Main strength of visualgc is that it displays all key data graphically including class loader, garbage collection and JVM compiler performance data. The target JVM is identified by its virtual machine identifier also called as vmid. You can read more about visualgc and vmid options here.

## Jmap
Jmap is a command line utility comes with JDK6 and allows you to take a memory dump of heap in a file. It’s easy to use as shwon below:
{% highlight scss %}jmap -dump:format=b,file=heapdump 6054{% endhighlight %}

Here file specifies name of memory dump file which is "heapdump" and 6054 is PID of your Java progress. You can find the PDI by using "ps -ef” or windows task manager or by using tool called "jps"(Java Virtual Machine Process Status Tool).

## Jhat
Jhat was earlier known as hat (heap analyzer tool) but it is now part of JDK6. You can use jhat to analyze heap dump file created by using "jmap". Jhat is also a command line utility and you can rum it from cmd window as shown below:
{% highlight scss %}jhat -J-Xmx256m heapdump{% endhighlight %}

Here it will analyze memory-dump contained in file "heapdump". When you start jhat it will read this heap dump file and then start listening on http port, just point your browser into port where jhat is listening by default 7000 and then you can start analyzing objects present in heap dump.

## Eclipse Memory Analyser

Eclipse memory analyzer (MAT) is a tool from eclipse foundation to analyze java heap dump. It helps to find classloader leaks and memory leaks and helps to minimize memory consumption. You can use MAT to analyze heap dump carrying millions of object and it also helps you to extract suspect of memory leak. See here for more information.
