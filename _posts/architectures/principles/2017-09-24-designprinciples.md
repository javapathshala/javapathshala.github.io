---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Design Principles"
teaser: "Design principles are the substance of architecture. It’s architect sincere liability to respect the design principles while designing an application of any size or complexity. Design principles are the backbone & inspiration behind all existing design patterns. "
image:
    thumb:  design-thumb.jpg
categories:
- architectures
- principles
tags:
- architectures
- principles
---
Prime aim of an architect is to GET IT RIGHT.  Design principles are different from Design patterns in a sense that knowledge of design principles will evolve the design patterns. Architecture design is dead without these design principles & Architect should have foresightedness to uses these. Most generic Design principles are:

##### Encapsulation
Encapsulation is famously known as data hiding. It’s a protective barrier that prevents the code and data being randomly accessed by other code defined outside the class. Principle is implemented by:
- Making the fields in a class private
- Only providing access to the fields via public methods [getter & setter methods].
- The public methods are the access points to the class. A class can have total control over what is stored in its fields.

##### Inheritance
It represents the parent-child relationship.  It passes the knowledge down the hierarchy in family tree. Classes are created in hierarchical fashion having relationships with each other. Relationship created allows methods in parental class to pass down the hierarchy. Implementing inheritance encourages the reuse of existing objects.

##### Polymorphism
Polymorphism is a combination of two Greek words: poly means “many” & morphos means forms. So literally Polymorphism means “many forms”.  Taking a school time chemistry example Element CARBON is polymorphic in nature i.e. it can be found in more than one form: diamond & graphite & both exhibits unique features.  In OOPS we can also apply the same principle & change the behaviour runtime.

##### The Open Closed Principle

This states that the classes or module should be open for extension only & closed for modification. That means design your classes such a way that their behaviour can be modified without change in source code.

In OOPS, this is achieved by using fundamentals of inheritance & polymorphism.

For change in functionality, create a new class that could reuse the code of original class through interfaces. This principle can also be implemented by defining abstracted interfaces where the implementations can be changed and multiple implementations could be created and polymorphically substituted for each other.

##### The Liskov Substitution Principle
Subclasses should be substitutable for their base classes. Derived classes should be substitutable for their base classes. That is, a user of a base class should continue to function properly if a derivative of that base class is passed to it. Popularly known as Strong behavioural subtyping.

##### The Dependency Inversion Principle
- Hollywood Principle: Don’t call us, we’ll call you!
- The ability to supply (inject) an external dependency into a software component
- Giving control to an object over who it calls, but not who calls it.
- Also Known as IOC (Inversion of Control). Caller will eventually get its answer, how and when is out of control of the caller.
- IOC can make the difference between a library and a framework.
- Auto wiring ( type, name) provided by containers
- Objects rely on environment to provide dependencies rather than obtaining them.
- To allow the method to interact with a variable, you inject a variable in method

##### Interface Segregation Principle (SIP)
This principle is implemented for clean development & aims to make software easily changeable. Segregation splits interfaces which are very large into smaller and more specific ones so that clients will only have to know about the methods that are of interest to them, thus provides decoupling.

##### Low Coupling
Coupling is a measure of “connection” between two elements. Objective here is to have LOW COUPLING. An element with low coupling is not dependent on too many other elements. A class with high coupling relies on many other classes. So remove unnecessary class coupling.

##### High Cohesion
High cohesion means responsibilities of a given objects are strongly related and highly focused.

Desire Architecture should have high cohesion & low coupling. Breaking programs into classes and subsystems is an example of activities that increase the cohesive properties of a system
