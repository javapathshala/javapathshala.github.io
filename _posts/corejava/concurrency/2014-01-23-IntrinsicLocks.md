---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Intrinsic Locks - Synchronization"
teaser: "Every object has a natural lock associated with it known as an intrinsic lock.A thread that needs to access object's fields has to acquire the object's intrinsic lock, use it & then release the intrinsic lock when it's done with them. During the time thread hold the lock, no other thread can acquire the same lock."
categories:
          - core-java
          - concurrency
tags:
          - core-java
          - concurrency
          - synchronization
---
## Ways to Synchronize

### Synchronized Methods
When a thread invokes a synchronized method, it automatically acquires the intrinsic lock for that method's object and releases it when the method returns. The lock release occurs even if the return was caused by an uncaught exception.

In case of static synchronized method, thread acquires a lock for the class object rather then method's object.

### Synchronized Block (using *this*)
Unlike synchronized methods, synchronized statements must specify the object that provides the intrinsic lock.

{% highlight java %}
public void updateStatus(String status) {
    synchronized(this) {
        newStatus = status;
        counter++;
    }
    statusList.add(status);
}
{% endhighlight %}
In above both assigning new status and increment counter are  inside synchronized block & hence thread safe but adding to list is out side & hence not thread safe.

### Synchronized Block (using *object instance*)
A way to improve concurrency with fine-grained synchronization.
class Increment has two instance fields, c1 and c2, that are not related. All updates of these fields must be synchronized, but there's no reason to prevent an update of c1 from being interleaved with an update of c2 — and doing so reduces concurrency by creating unnecessary blocking. Instead of using synchronized methods or otherwise using the lock associated with this, we create two objects solely to provide locks.
{% highlight java %}
public class MsLunch {
    private long c1 = 0;
    private long c2 = 0;
    private Object lock1 = new Object();
    private Object lock2 = new Object();

    public void inc1() {
        synchronized(lock1) {
            c1++;
        }
    }

    public void inc2() {
        synchronized(lock2) {
            c2++;
        }
    }
}
{% endhighlight %}

### Reentrant Synchronization
This happens when a thread acquire the same lock more than once.  Arises when synchronized code, directly or indirectly, invokes a method that also contains synchronized code, and both sets of code use the same lock. Without reentrant synchronization, synchronized code would have to take many additional precautions to avoid having a thread cause itself to block.
