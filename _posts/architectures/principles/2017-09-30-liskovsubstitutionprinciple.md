---
layout: page
sidebar: right
breadcrumb: true
comments: true
image:
    thumb:  design-thumb.jpg
title: "Liskov Substitution Principle"
teaser: "Derived classes must be substitutable for their base classes."
categories:
          - architectures
          - principles
tags:
          - architectures
          - principles
          - Liskov Substitution Principle
---
- Derived classes must be substitutable for their base classes.
- Subclasses/Derived should be substitutable for their base classes i.e. a user of a base class should continue to function properly if a derivative of that base class is passed to it. Popularly known as Strong behavioral subtyping.
- If S is a subtype of T, then objects of type T may be replaced with objects of type S (i.e., objects of type S may be substituted for objects of type T) without altering any of the desirable properties of that program (correctness, task performed, etc.).
- Methods that use references to the base classes must be able to use the objects of the derived classes without knowing it. The idea here is that the subtypes must be replaceable for the super type references without affecting the program execution.
- This principle is very closely related to Open Closed Principle (OCP), violation of LSP in turn violates the OCP. If the subtype is not replaceable for the supertype reference, then to support the subtype instances as well we go ahead and make changes to the existing code and add the support. This is a clear violation of OCP.
