---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Concurrent Hash Map"
teaser: "Superior brother of HashMap"
categories:
          - Core-Java
          - Concurrency
---
* ConcurrentHashMap allows concurrent read and thread-safe update operation.
* During update operation, ConcurrentHashMap only lock a portion of Map (only bucket) instead of whole Map.
* Concurrent update is achieved by internally dividing Map into small portion which is defined by concurrency level.
* Choose concurrency level carefully as a significant higher number can be waste of time and space and lower number may introduce thread contention in case writers over number concurrency level.
* All operations of ConcurrentHashMap are thread-safe.
* Since ConcurrentHashMap implementation doesn't lock whole Map, there is chance of read overlapping with update operations like put () and remove (). In that case result returned by get () method will reflect most recently completed operation from there start.
* Iterator returned by ConcurrentHashMap is weekly consistent, fail safe and never throw ConcurrentModificationException. In Java.
* ConcurrentHashMap doesn't allow null as key or value.
* You can use ConcurrentHashMap in place of Hashtable but with caution as CHM doesn't lock whole Map.
* During putAll () and clear () operations, concurrent read may only reflect insertion or deletion of some entries.
