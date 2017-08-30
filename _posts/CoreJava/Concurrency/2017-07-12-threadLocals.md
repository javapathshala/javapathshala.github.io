---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Thread Locals"
teaser: "Another way to achieve thread-safety apart from writing immutable classes"
categories:
          - core-java
          - concurrency
---
* ThreadLocal in Java is another way to achieve thread-safety apart from writing immutable classes. In multi-threaded applications there is a cost of synchronization or locking which greatly affects scalability of application, but there is no choice other than synchronize if you are sharing objects between multiple threads.
* ThreadLocal in Java is a different way to achieve thread-safety but doesn't address synchronization requirement, instead it eliminates sharing by providing explicitly copy of object to each thread. Since Object is no more shared there is no requirement of synchronization which can improve scalability and performance of application. Associated with thread scope only.
* On basic level ThreadLocal provides Thread Confinement which is extension of local variable. While local variable only accessible on block they are declared, ThreadLocal are visible only in Single Thread. No two Threads can see each other’s ThreadLocal variable. Real Life example of ThreadLocal is in J2EE application servers which uses java ThreadLocal variable to keep track of transaction and security Context. It makes lot of sense to share heavy object like Database Connection as ThreadLocal in order to avoid excessive creation and cost of locking in case of sharing global instance.
* Each thread holds an exclusive copy of ThreadLocal variable which becomes eligible to Garbage collection after thread finished or died, normally or due to any Exception, given those ThreadLocal variable doesn't have any other live references.
* ThreadLocal variables in Java are generally private static fields in Classes and maintain its state inside Thread.
* Every thread that accesses a ThreadLocal variable via its get or set method has its own, independently initialized copy of the variable
* After a thread goes away, all of its copies of thread-local instances are subject to garbage collection
* You can set any object in Thread Local and this object will be global and local to the specific thread which is accessing this object.
* Inheritable ThreadLocal: When a child thread is created, the child receives initial values for all inheritable thread-local variables for which the parent has values. Normally the child's values will be identical to the parent's; however, the child's value can be made an arbitrary function of the parent's by overriding the childValue method in this class.
* ThreadLocal must always be reset to avoid thread pools in application servers
