---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "TimeZone Aware Tomcat!"
teaser: "Run Tomcat with timezone of your choice"
image:
    thumb:  tomcat-thumb.jpg
categories:
          - tomcat
tags:
          -tomcat
related: true
---
You can set the timezone in which you want to run your tomcat. This helps in case tomcat hostimg multiple timezone applications, thus required a need to set a universal time zone so that reports , database operations are all performed in single time zone.

- Create a setenv.bat file & paste the following in Same

{% highlight dos %}
set JAVA_OPTS=-Duser.timezone=UTC
{% endhighlight %}

- Copy the file in <tomcat>/bin

- restart tomcat.
