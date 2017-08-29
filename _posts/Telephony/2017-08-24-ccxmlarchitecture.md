---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "CCXML Applications"
teaser: It consists of a collection of CCXML documents that control and manage objects
tags:
    - Telephony
categories:
    - Telephony
---

- It consists of a collection of CCXML documents that control and manage objects
- CCXML Session – the execution of a CCXML document or sequence of documents.  Each CCXML document is a separate session that can be, uniquely, identified and referenced.
- Connections (sometimes called “call legs”) or phone connections or system resources to manage interaction with a voice dialog
-  Conference objects used to mix media streams
-  Dialog, which may interact with other Connections or Conferences using one-way or two-way audio streams, often controlled by VXML dialog environments
- Send and/or receive asynchronous events associated with these entities.
- Directly manipulate Connection and Conference objects
- Using <accept>, <createconference> <join>
- Start and kill voice dialogs using language elements
- Standardized events like dialog.exit
- Create other CCXML sessions Using <createccxml>

#The following list represents the features that CCXML provides (VoiceXML lacks):
Routing: Routes calls to the next available line in a group; or find me/follow me capability to track a person down at multiple possible locations.
Bridging: Connects a call between two call legs.
Outbound Calling: Initiates a call and starts one or more VoiceXML dialogs once a connection is established.
Selective Call Answering: Decides whether or not to answer a call based upon caller information.
Conferencing: Allows multiple participants to join a phone conference.
Coaching: Allows a third party to connect to a call, but only have one of the participants hear what is said.
Dialog Execution: New instances of VoiceXML interpreters can be created and destroyed at will.
