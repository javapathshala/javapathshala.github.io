---
layout: page
sidebar: right
breadcrumb: true
comments: true
image:
    thumb:  hollywood-thumb.jpg
title: "Dependency Inversion Principle"
teaser: "The ability to supply (inject) an external dependency into a software component. It's simply HOLLOYWOOD Law : Don’t call us, we’ll call you!"
categories:
          - architectures
          - principles
tags:
          - architectures
          - principles
          - IOC
          - Dependency injection
          - Dependency Inversion Principle
---
- The ability to supply (inject) an external dependency into a software component
- Hollywood Principle: Don’t call us, we’ll call you!
- Depend on abstractions, not on concretions.
- Giving control to an object over who it calls, but not who calls it.
- Also Known as IOC (Inversion of Control). Caller will eventually get its answer, how and when is out of control of the caller.
- IOC can make the difference between a library and a framework.
- Auto wiring ( type, name) provided by containers
- Objects rely on environment to provide dependencies rather than obtaining them.
- To allow the method to interact with a variable, you inject a variable in method
- Per this principle the way of designing a class structure is to start from high level modules to the low-level modules: High Level Classes --> Abstraction Layer --> Low Level Classes
- High-level modules should not depend on low-level modules. Both should depend on abstractions.
- Abstractions should not depend on details. Details should depend on abstractions.
- When this principle is applied, it means that the high-level classes are not working directly with low level classes, they are using interfaces as an abstract layer. In that case the creation of new low level objects inside the high level classes (if necessary) cannot be done using the operator new. Instead, some of the Creational design patterns can be used, such as Factory Method, Abstract Factory and Prototype.
- The Template Design Pattern is an example where the DIP principle is applied.
- Of course, using this principle implies an increased effort and a more complex code, but more flexible. This principle cannot be applied for every class or every module. If we have a class functionality that is more likely to remain unchanged in the future there is no need to apply this principle.
