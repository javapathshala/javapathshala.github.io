---
layout: page
header:
    image_fullwidth: "cam.jpg"
breadcrumb: true
show_meta: true
sidebar: right
title: "Microservices Features"
teaser: "Application as a set of loosely coupled"
image:
    thumb:  sign-thumb.jpg
comments: true
categories:
          - microservices
tags:
    - Spring Boot
    - Microservices features
    - Microservices advantages
    - Microservices prons
    - Microservices meaning
---
- Application as a set of loosely coupled
- Set of collaborating services
- Single Responsibility
- Each service implements a set of narrowly, related functions
- Services communicate using either synchronous protocols such as HTTP/REST or asynchronous protocols such as AMQP.
- Services can be developed and deployed independently of one another
- Each service has its own database in order to decouple from other services. No centralized database, thus so there's data decentralization. Can use any database, thus enabling polygate.
- Runs in its own process & thus can be deployed, upgraded, scaled, and restarted independent of other services in the application
- Each service can be developed in any language that is best fits for the requirement – Polygate
- Developer is only concentrated on a particular service, so the code base will be very small, and the developer will know the code very well.
- Enables the continuous delivery and deployment of large, complex applications.
- Better testability - services are smaller and faster to test
- Better deployability - services can be deployed independently
- Each service follows “two pizza team” principle. Each team can develop, deploy and scale their services independently of all of the other teams.
- Each microservice is relatively small
- Improved fault isolation. For example, if there is a memory leak in one service then only that service will be affected. The other services will continue to handle requests. 
