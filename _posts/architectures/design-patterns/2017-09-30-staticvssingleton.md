---
layout: page
header:
    image_fullwidth: "cam.jpg"
breadcrumb: true
sidebar: right
title: "Static Class Vs SingleTon Pattern"
teaser: "WoW ! Both have their own usage but still investigation is required - which one to use ?"
image:
    thumb:  homepage_patterns-thumb.jpg
comments: true
categories:
          - architectures
          - design-patterns
tags:
- architectures
- design-patterns
- static class vs singleton
- singleton
- static class
---

- Singleton is more object oriented.
- Singleton can use inheritance & polymorphism to extend a base class, implement an interface. E.g. java.lang.Runtime is a singleton class but call to get Runtime () returns different implementation based on JVM. If this is made static, it would be difficult to return different implementation.
- Static class cannot inherit their instance members.
- Singleton can be initialized lazily or asynchronously but static class is first loaded.
- Static classes do make sense:
    - If class is just providing global access to methods & not maintaining any state. This is high performance as compared to singleton class as static binding occurs at compile time.
    - E.g. java.lang.Math is a static class with all static methods.
