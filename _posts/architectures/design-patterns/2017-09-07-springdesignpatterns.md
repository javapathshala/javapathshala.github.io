---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Spring Design Patterns"
teaser: " Design Patterns used by Spring framework "
categories:
          - architectures
          - design-patterns
---
-	Dependency injection/ or IOC (inversion of control) – Is the main principle behind decoupling process.
-	Factory – Spring uses factory pattern to create objects of beans using Application Context reference.
-	Proxy – used heavily in AOP & remoting.
-	Singleton – by default, beans defined in spring config file (xml) are only created once. No matter how many calls were made using getBean() method, it will always have only one bean. This is because; by default, all beans in spring are singletons.
This can be overridden by using Prototype bean scope. Then spring will create a new bean object for every request.
-	Model View Controller – The advantage with Spring MVC is that your controllers are POJOs as opposed to being servlets. This makes for easier testing of controllers. One thing to note is that the controller is only required to return a logical view name, and the view selection is left to a separate View-Resolver. This makes it easier to reuse controllers for different view technologies.
-	Front Controller – Spring provides Dispatcher-Servlet to ensure an incoming request gets dispatched to your controllers.
-	View Helper – Spring has several custom JSP tags, and velocity macros, to assist in separating code from presentation in views.
-	Template method – used extensively to deal with boilerplate repeated code (such as closing connections cleanly, etc.). For example JdbcTemplate, JmsTemplate, JpaTemplate.
