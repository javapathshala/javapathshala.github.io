---
layout: page
header:
    image_fullwidth: "cam.jpg"
breadcrumb: true
sidebar: right
title: "Eviction policy"
teaser: "A cache eviction policy is an algorithm according to which an existing element is removed from a cache when a new element is added. The eviction policy is applied to ensure that the size of the cache does not exceed a maximum size. "
image:
    thumb:  homepage_patterns-thumb.jpg
comments: true
categories:
          - architectures
          - caching
tags:
- architectures
- design-patterns
- singletons
---
Least Recently Used (LRU) is one of the most popular among a number of eviction policies. LRU earned its popularity for being the best in capturing temporal and spatial locality of data access.

A minor disadvantage or LRU is its sensitivity to a full scan. The sensitivity manifests itself in evicting accumulated frequently accessed cache elements when accessing data that does not satisfy the requirement of temporal locality. This disadvantage is minor because LRU recovers from full scans quickly.
