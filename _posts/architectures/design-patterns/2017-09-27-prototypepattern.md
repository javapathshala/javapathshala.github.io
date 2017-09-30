---
layout: page
header:
    image_fullwidth: "cam.jpg"
breadcrumb: true
sidebar: right
title: "Prototype Pattern"
teaser: "Allows making new instances by copying an existing instance ! Cheap Objects"
image:
    thumb:  prototype-thumb.jpg
comments: true
categories:
          - architectures
          - design-patterns
tags:
- architectures
- design-patterns
- prototyping
- prototype
---
- Allows making new instances by copying an existing instance.
- It is a clone object that is different from original
- Template of an object
- Minimum instance creation process
- Initially object has same state but can change after cloning or prototyping.
- Client can make new instances without knowing which specific class is initialized.
- Creation is through delegation.
- Prototype object has same properties initially
- Mandates that object have copying properties i.e. shallow or deep copy.
- Hides complexity of creating objects
- Reduces sub-classing.
- Cons – making a copy is sometimes complicates in case of complex objects – Class with circular reference difficult to clone
- Can co-exists with Factory & singleton pattern

##### Applicability
An object is loaded from database & needs to be modified multiple times with different values. So rather them loading object from DB again & again, clone the object & play with it.

##### Used When
- Multiple similar objects are used.
- Removing or adding objects at runtime
- Cost of creating an object is expensive or complex
