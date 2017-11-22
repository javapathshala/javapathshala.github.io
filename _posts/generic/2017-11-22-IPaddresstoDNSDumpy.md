---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Web Application -How to Map IP to DNS for Testing"
teaser: "This post describes how to host a web application with domain name but only on team access (not for outside world - you need to buy a domain name for that)."
categories:
          - generic
tags:
          - generic
          - Web Application
---

Normally whenever we build web applicatios using any agreeded technology stack , we endup in access url like <em>http://<server ip/hostname>:portnumber/myapp</em>. If you have many applications hosting on different servers ,it's difficult to remember IP or hostname for that server. 

Work around is to have dummy or fake Domain name (not registered with any registar) e.g.  http://<server ip/hostname>:portnumber/myapp changes to http://www.myapp.com/myapp

To make it happen we would simply modify  hosts file, which is essentially a list of IP/hostname associations which any DNS lookup will check first.

Host file is located at different locations in different OS. For windows it resides in <em>c:/windows/system32/drivers/etc/</em> folder . Make sure you open host file (hosts) in admin mode to save changes.

In hosts file find the entry for localhost and add an entry as shown below
{% highlight java %}
127.0.0.1       www.myapp.com
{% endhighlight %}

All set, access your application as http://www.myapp.com/myapp

