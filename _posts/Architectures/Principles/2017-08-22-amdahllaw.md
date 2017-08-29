---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Amdahl’s Law"
categories:
          - Architectures
          - Principles-
---

- Is used to find the maximum expected improvement to an overall system when only part of the system is improved. It is often used in parallel computing to predict the theoretical maximum speed up using multiple processors.
- The speedup of a program using multiple processors in parallel computing is limited by the time needed for the sequential fraction of the program. For example, if a program needs 20 hours using a single processor core, and a particular portion of the program which takes one hour to execute cannot be parallelized, while the remaining 19 hours (95%) of execution time can be parallelized, then regardless of how many processors are devoted to a parallelized execution of this program, the minimum execution time cannot be less than that critical one hour. Hence the speedup is limited to at most 20×.
- Used to find the maximum expected improvement to an overall system when only part of the system is improved. It is often used in parallel computing to predict the theoretical maximum speed-up using multiple processors. The law is named after computer architect Gene Amdahl, and was presented at the AFIPS Spring Joint Computer Conference in 1967.
- The speedup of a program using multiple processors in parallel computing is limited by the time needed for the sequential fraction of the program. For example, if a program needs 20 hours using a single processor core, and a particular portion of the program which takes one hour to execute cannot be parallelized, while the remaining 19 hours (95%) of execution time can be parallelized, then regardless of how many processors are devoted to a parallelized execution of this program, the minimum execution time cannot be less than that critical one hour. Hence the speedup is limited up to 20×.
- If F is the percentage of the program which cannot run in parallel and N is the number of processes then the maximum performance gain is 1/ (F+ ((1-F)/n)).
- A visibility problem occurs if thread A reads shared data which is later changed by thread B and thread A is unaware of this change.
- An access problem can occur if several thread access and change the same shared data at the same time.
- If a variable is declared with the volatile keyword then it is guaranteed that any thread that reads the field will see the most recently written value. The volatile keyword will not perform any mutual exclusive lock on the variable.
- As of Java 5 write access to a volatile variable will also update non-volatile variables which were modified by the same thread.
