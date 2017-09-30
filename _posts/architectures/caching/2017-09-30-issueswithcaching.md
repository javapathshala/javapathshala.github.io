---
layout: page
header:
    image_fullwidth: "cam.jpg"
breadcrumb: true
sidebar: right
title: "Issues With Caching"
teaser: "Caching can encounter challenges that include, for example, the problem of cache warm-up, where cache needs to be loaded with enough active data to reduce cache misses and allow it to start improving I/O response times."
image:
    thumb:  homepage_patterns-thumb.jpg
comments: true
categories:
          - architectures
          - caching
tags:
- architectures
- caching
---
- There are also problems associated with caching software, most notably issues of data integrity and cache coherence in clustered deployments.
- In response, some suppliers have chosen to implement only write-through cache, whereas others have resolved the coherence issue by replicating data between cluster nodes.
- There will always be a trade-off between latency and resiliency and so it becomes dependent on the user to look at whether write-cache is an essential requirement of the deployment.
- One other consideration is the algorithms or logic used to determine what to cache. Some solutions use simple “least recently used” policies to discard data; others are more complex and look at the data for clues as to which should be retained in cache.
- Users should look at the cache occupancy criteria and ensure the rules fit the types of data they expect the cache to manage.
