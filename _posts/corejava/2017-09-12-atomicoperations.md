---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Atomic Operations!"
teaser: "An atomic operation is an operation which is performed as a single unit of work without the possibility of interference from other operations."
categories:
          - core-java
---
-	The Java language specification guarantees that reading or writing a variable is an atomic operation (unless the variable is of type long or double). Operations variables of type long or double are only atomic if they declared with the volatile keyword. .
-	Assume i is defined as int. The i++ (increment) operation it not an atomic operation in Java. This also applies for the other numeric types, e.g. long. etc). The i++ operation first reads the value which is currently stored in i (atomic operations) and then it adds one to it (atomic operation). But between the read and the write the value of i might have changed.
-	Since Java 1.5 the java language provides atomic variables, e.g. AtomicInteger or AtomicLong which provide methods like getAndDecrement(), getAndIncrement() and getAndSet() which are atomic.
