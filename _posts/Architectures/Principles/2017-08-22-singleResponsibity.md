---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Single Responsibility"
teaser: "A class should have one & only one reason for change. Responsibility here is reason for change. If there are two reasons for a change in a class, then there is a need to split class functionality into two."
categories:
          - Architectures
          - Principles
---

Each class will handle only one responsibility. The Single Responsibility Principle is a simple and intuitive principle, but in practice it is sometimes hard to get it right. Relate the <em>“reason to change”</em> to <em>“the responsibility of the class”</em>.

Each responsibility would be an axis for change.
It is like designing classes which are highly cohesive.
Idea is to design a class which has one responsibility or in other words caters to implementing functionality.
One responsibility doesn’t mean that the class has only one method. A responsibility can be implemented by means of different methods in the class.
Decompose the class functionalities into different classes, each of which confirms to SRP.

Why Required?
Imagine designing classes implementing more than one responsibility functionality. Ideally no harm in doing so but this would increase the class dependency which would impact other functionalities implemented in the class. The changes might or might not impact other features, but to be on safer side, teams end up testing all the dependent features. Changes get accumulate owing to the viscosity of the code making it fragile and rigid. So better to have one class per responsibility or functionality.
