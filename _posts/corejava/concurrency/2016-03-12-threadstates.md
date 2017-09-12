---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Thread States"
teaser: "Different moods of threads"
categories:
          - core-java
          - concurrency
tags:
          - core-java
          - threads
          - concurrency
---
#### States of thread
- Ready
- Waiting for some action
- Running
- Dead

#### Process of Thread
Create Thread --> start thread --> Run

#### Running State
A thread is said to be in running state when it is being executed. This thread has access to CPU.

#### Ready State
A thread in this state is ready for execution, but is not being currently executed. Once a thread in the ready state gets access to the CPU, it gets converted to running state.

#### Dead State
A thread reaches "dead" state when the run method has finished execution. This thread cannot be executed now.

#### Waiting State
In this state the thread is waiting for some action to happen. Once that action happens, the thread gets into the ready state. A waiting thread can be in one of the following states: Sleeping Suspended, Blocked, Waiting for monitor.

#### Sleep State
Thread in execution can invoke the sleep () to cease executing & free CPU. Thread would go to the "sleep" state for the specified amount of time, after which it would move to the "ready" state. It does not release lock.
