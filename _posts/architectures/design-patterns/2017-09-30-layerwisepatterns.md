---
layout: page
header:
    image_fullwidth: "cam.jpg"
breadcrumb: true
sidebar: right
title: "Layer Wise Design Patterns"
teaser: "Layered archietctures allows to use different design patterns at different layers. This post descttibes a taxonomy of design pattrens that could/should be used in each layer of architecture."
image:
    thumb:  homepage_patterns-thumb.jpg
comments: true
categories:
          - architectures
          - design-patterns
tags:
- architectures
- design-patterns
- layer wise patterns
- architecture layers patterns
---

#### Presentation Layer
- Intercepting Filter - Intercepts incoming requests and outgoing responses and applies a filter.
- Context Object - Encapsulates state in a protocol-independent way to be shared throughout your application
- Front Controller - A container to hold the common processing logic that occurs within the presentation tier
- Application Controller - Centralizes control, retrieval, and invocation of view and command processing
- View Helper - Encourages the separation of formatting-related code from other business logic
- Composite View - suggests composing a View from numerous atomic pieces
- Dispatcher View - defers business processing until view processing has been performed.

#### Business Layer
- Business Delegate -reduces coupling between remote tiers and provides an entry point for accessing remote services in the business tier.
- Service Locator - encapsulates the implementation mechanisms for looking up business service components.
- Session Facade - provides coarse-grained services to the clients by hiding the complexities of the business service interactions.
- Application Service - centralizes and aggregates behavior to provide a uniform service layer to the business tier services.
- Business Object -implements your conceptual domain model using an object model.
- Composite Entity -implements a Business Object using local entity beans and POJOs.
- Transfer Object -provides the best techniques and strategies to exchange data across tiers
- T O Assembler -constructs a composite Transfer Object from various sources
- Value List Handler -uses the GoF iterator pattern to provide query execution and processing services

#### Integration Layer

- Data Access Object -enables loose coupling between the business and resource tiers
- Service Activator -enables asynchronous processing in your enterprise applications using JMS.
- Domain Store -provides a powerful mechanism to implement transparent persistence for your object model.
- Web Service Broker -exposes and brokers one or more services in your application to external clients as a web service using XML and standard web protocols
