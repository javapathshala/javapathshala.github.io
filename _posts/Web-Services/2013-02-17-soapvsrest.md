---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "SOAP Vs REST"
teaser: "Both implementation are good in thier own sense. Choose as per business senerioas"
categories:
          - Web-Services
---
<em>REST works really well for:</em>
* Limited bandwidth and resources; remember the return structure is really in any format (developer defined). Plus, any browser can be used because the REST approach uses the standard GET, PUT, POST, and DELETE verbs.
* REST can also use the XMLHttpRequest object that most modern browsers support today, which adds an extra bonus of AJAX.
* Totally stateless operations; if an operation needs to be continued, then REST is not the best approach and SOAP may fit it better. However, if you need stateless CRUD (Create, Read, Update, and Delete) operations, then REST is it.
* Caching situations; if the information can be cached because of the totally stateless operation of the REST approach, this is perfect.

<em>That covers a lot of solutions in the above three. So why would I even consider SOAP? Again, SOAP is fairly mature and well-defined and does come with a complete specification. The REST approach is just that, an approach and is wide open for development.<em/>

So if you have the following then SOAP is a great solution:

* Asynchronous processing and invocation; if your application needs a guaranteed level of reliability and security then SOAP 1.2 offers additional standards to ensure this type of operation. Things like WSRM – WS-Reliable Messaging.
* Formal contracts; if both sides (provider and consumer) have to agree on the exchange format then SOAP 1.2 gives the rigid specifications for this type of interaction.
* Stateful operations; if the application needs contextual information and conversational state management then SOAP 1.2 has the additional specification in the WS* structure to support those things (Security, Transactions, Coordination, etc). Comparatively, the REST approach would make the developers build this custom plumbing.
