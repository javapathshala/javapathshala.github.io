---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Web Services Types"
teaser: "There are 3 types of Web-services types or you can say transport mechanism. It is very important to know the differences as this will help architects to decide implementation techniques."
tags:
    #- Web-services
categories:
    - Web-Services
---

### SOAP
* XML Format
* Includes definition for error format
* Wrappers available for most languages
* WSDL to describe the service

### RPC
* Remote Procedure call
* Similar to library
* Calling functions with arguments – Function name. parameters & return values
* Body format – XML-RPC / JSON_RPC
* Single endpoint

### REST
* Representational state transfer
* Series of concept
* Uses HTTP
* URLS are resource locations
* Verbs tell the service what to do
* Status codes tells the outcome
