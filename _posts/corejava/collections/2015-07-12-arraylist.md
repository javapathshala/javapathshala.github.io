---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Array Lists "
teaser: " A Growable Friend"
categories:
          - core-java
          - collections
tags:
        - core-java
        - collections
        - arraylist
related: true
---
- Growable / Uses array to store elements / Resizable
- Can contain heterogeneous objects as everything is stored as objects.
- Non-Synchronized.
- Fast insertion & fast random access as it implements RandomAccess marker interface.
- Powerful insertion and search mechanisms than arrays
- Beneficial over LinkedList for fast iteration when not lot of insertion and deletion.
- Ordered by index position.
- More powerful than String [] array
- ArrayList supports both Iterator and ListIterator for iteration but it’s recommended to use ListIterator as it allows the programmer to traverse the list in either direction, modify the list during iteration, and obtain the Iterator's current position in the list. But while using ListIterator you need to be little careful because ListIterator has no current element; its cursor position always lies between the element that would be returned by a call to previous () and the element that would be returned by a call to next ().
- CopyonWriteArrayList is recommended for concurrent multi-threading environment as it is optimized for multiple concurrent read and creates copy for write operation.
- When ArrayList gets full it creates another array and uses System.arrayCopy() to copy all elements from one array to another array.
- ArrayList are fail-fast it means if ArrayList is structurally modified at any time after the Iterator is created, in any way except through the iterator's own remove or add methods, the Iterator will throw a ConcurrentModificationException. Thus, in the face of concurrent modification, the Iterator fails quickly and cleanly, that's why it’s called fail-fast.
- An application can increase the capacity of an ArrayList instance before adding a large number of elements using the ensureCapacity operation. This may reduce the amount of incremental reallocation due to incremental filling of ArrayList.
- If we set ArrayList reference null in Java all the elements inside ArrayList becomes eligible to garbage collection in java, provided there are no more reference exists for those objects.
- List add() method is the fastest. Add (int, E) Methods specifying insertion position have to copy all array elements to the right from insertion point by System.arraycopy() call, that’s why these methods have O(n) complexity. Runs in amortized constant time
- Remove (int) This method removes a single element at given position. After that all elements from the right are shifted to the left via System.arraycopy call, that’s why this method has O(n) complexity.
