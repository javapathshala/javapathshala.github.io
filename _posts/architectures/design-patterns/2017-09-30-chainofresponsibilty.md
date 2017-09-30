---
layout: page
header:
    image_fullwidth: "cam.jpg"
breadcrumb: true
sidebar: right
title: "Chain of Responsibilty"
teaser: "Actually bad habit. Throw your Responsibilty to others. Is what this pattern says - NO :). -	The Chain of Responsibility is known as a behavioural pattern, as it's used to manage algorithms, relationships and responsibilities between objects. Complete java exception framework is built on *chain of responsibilities*"
image:
    thumb:  chain-thumb.jpg
comments: true
categories:
          - architectures
          - design-patterns
tags:
- architectures
- design-patterns
- Chain of Responsibilty
- exception handling
---

-	Chain of Responsibility allows several classes to attempt to handle a request, independently of any other object along the chain. Once the request is handled, it completes its journey through the chain.
-	Chain of responsibility is a design pattern where a sender sends a request to a chain of objects, where the objects in the chain decide themselves who to honour the request. If an object in the chain decides not to serve the request, it forwards the request to the next object in the chain
-	The Handler defines the interface required to handle request, while the ConcreteHandlers handle requests that they are responsible for.  If the ConcreteHandler cannot handle the request, it passes the request onto its successor, which it maintains a link to.
-	The objects in the chain just need to know how to forward the request to other objects.  This decoupling is a huge advantage, as you can change the chain at runtime.
-	Chain of responsibility helps to decouple sender of a request and receiver of the request with some trade-offs.
-	Responsibility is outsourced. In a chain of objects, the responsibility of deciding who to serve the request is left to the objects participating in the chains. It is similar to ‘passing the question in a quiz scenario’.
-	When the quiz master asks a question to a person, if he doesn’t knows the answer, he passes the question to next person and so on. When one person answers the question, the passing flow stops. Sometimes, the passing might reach the last person and still nobody gives the answer.
-	Sender will not know which object in the chain will serve its request.
-	Every node in chain will have the responsibility to decide, if they can serve the request.
-	If node decides to forward the request, it should be capable of choosing the next node and forward it.
-	There is a possibility where none of the node may serve the request.
-	There may be scenarios where a node is capable of solving the request but may not get a chance for it. Though there is a candidate who can solve the problem, but since nobody forwarded the request to it, it was not given a chance to serve and final result is the request goes unattended failure. This happens because of improper chain sequence. A chain sequence may not be suitable for all scenarios.
-	Examples: Coin sorting machine, ATM money dispenser, Servlet Filter and finally java’s own Exception Handling.
