---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Immutable Classes"
teaser: To create an immutable class following steps should be followed:"
categories:
          - core-java
tags:
          - core-java
---
- Create a final class.
- Set the values of properties using constructor only.
- Make the properties of the class final and private
- Do not provide any setters for these properties.
- If the instance fields include references to mutable objects, don't allow those objects to be changed
- Don't provide methods that modify the mutable objects.
- Don't share references to the mutable objects. Never store references to external, mutable objects passed to the constructor; if necessary, create copies, and store references to the copies. Similarly, create copies of your internal mutable objects when necessary to avoid returning the originals in your methods.
- Since the state of the immutable objects cannot be changed once they are created they are automatically synchronized/thread-safe.
- All wrapper classes in java.lang are immutable – String, Integer, Boolean, Character, Byte, Short, Long, Float, Double, BigDecimal, BigInteger
- The best use of the immutable objects is as the keys of a map.
