---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Domain Driven Design"
teaser: " Domain-driven way of building software should appeal to everyone – after all that software is being built for the benefit of that domain, not for the benefit of architects, developers or QAs."
categories:
          - Designs
---

- Domain-driven way of building software should appeal to everyone – after all that software is being built for the benefit of that domain, not for the benefit of architects, developers or QAs.
- DDD is implemented using frameworks like spring & hibernate. Spring uses dependency injection & hibernate uses objects with database as means of implementing DDD.
- use @Configurable to make the domain objects eligible for dependency injection (they are not instantiated by spring, so they need this special approach)
- inject repository objects in the domain objects in order to allow the domain objects to do persistence-related operations
- use a thin, stateless, transactional service layer (a facade) to coordinate the domain objects
