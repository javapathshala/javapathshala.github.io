---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Out of Memory - HELL :("
teaser: "Out of Memory Error - OME"
categories:
          - performance
tags:
          - performance
          - memory
---
- OutOfMemoryError (OME) in Java is a subclass of java.lang.VirtualMachineError and JVM throws java.lang.OutOfMemory Error when it ran out of memory in heap.
- OME in Java can come any time in heap mostly while you try to create an object and there is not enough space in heap to allocate that object.
- There are two type of OMEs & both of them occur because JVM ran out of memory they are quite different to each other and there solutions are independent to each other.
##### "java.lang.OutOfMemoryError: Java heap space"
Error messages denotes that Java heap does not have sufficient space and cannot be expanded further.

##### “java.lang.OutOfMemoryError: PermGen space"
- Permanent generation of heap is used to store String pool and various Meta data required by JVM related to Class, method and other java primitives.
- JVM default size of Perm Space is around "64MB" you can easily run out of memory if you have too many classes or huge number of Strings in your project.
- Important point to remember is that it doesn't depends on –Xmx value so no matter how big your total heap size you can ran OME in perm space.
Specify size of permanent generation using JVM options "-XX:PermSize" and  "-XX:MaxPermSize" E.g. -Xmx1024m -XX:MaxPermSize=256m
- Second reason: Memory leak through Classloaders and it’s very often surfaced in WebServer and application server like tomcat, webshere, glassfish or weblogic. In Application server different classloaders are used to load different web application so that you can deploy and undeploy one application without affecting other application on same server, but while undeploying if container some how keeps reference of any class loaded by application class loader than that class and all other related class will not be garbage collected and can quickly fill the PermGen space
- Third Reason: if any thread started by application doesn't exit when you undeploy your application.
- Fourth Reason : introduction of JVM options "-Xnoclassgc". This option sometime used to avoid loading and unloading of classes when there is no further live references of it just to avoid performance hit due to frequent loading and unloading, but using this option is J2EE environment can be very dangerous because many framework e.g. Struts, spring etc uses reflection to create classes and with frequent deployment and undeployment you can easily ran out of space in PermGen if earlier references was not cleaned up.
