---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Anemic Domain Model"
teaser: "Model where business logic is implemented outside the domain objects."
image:
    thumb:  model-thumb.jpg
categories:
          - architectures
          - designs
tags:
          - architectures
          - designs
---
- The core business objects have been split into objects containing only data known as domain objects & objects containing only business logic. Logic is typically implemented in separate classes which transform the state of the domain objects.
- This pattern is a common approach in enterprise Java applications, possibly encouraged by technologies such as early versions of EJB's Entity Beans, as well as in .NET applications following the Three-Layered Services Application architecture where such objects fall into the category of "Business Entities.
- It is a procedural style design.
- Does not contain any logic [business]. All logic is placed outside the model.
- Act as container for data that can be changed and interpreted by clients
- Has no logic that ensures that it is in a legal state at any time
- Contradictory with fundamental object-oriented principles like: encapsulation, information hiding and bringing data and process (logic) together.
- Services that hold the logic are independent from a domain model object - they are stateless & thus can’t cache the calculated value
