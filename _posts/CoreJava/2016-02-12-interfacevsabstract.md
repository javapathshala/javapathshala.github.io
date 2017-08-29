---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Interface Vs Abstract Class"
teaser: "Co-Brothers with different nature."
categories:
          - Core-Java
---
* Interfaces provide a form of multiple inheritances. A class can extend only one other class.
* Interfaces are limited to public methods and constants with no implementation. Abstract classes can have a partial implementation, protected parts, static methods, etc.
* A Class may implement several interfaces. But in case of abstract class, a class may extend only one abstract class.
Interfaces are slow as it requires extra indirection to find corresponding method in in the actual class.
* Abstract classes are fast.  
* Interface contains variables that must be static and final; abstract class may contain non-final and final variables.
* Interface contains methods that must be abstract; abstract class may contain concrete methods.
* Members in an interface are public by default; abstract class may contain non-public members.
* Interface is used to "implements"; whereas abstract class is used to "extends".
* Interface can be used to achieve multiple inheritances; abstract class can be used as a single inheritance.
* Interface can "extends" another interface; abstract class can "extend" another class and "implements" multiple interfaces.
* Interface is absolutely abstract; abstract class can be invoked if a main () exists.
* Interface is more flexible than abstract class because one class can only "extends" one super class, but "implements" multiple interfaces.
* If given a choice, use interface instead of abstract class.
