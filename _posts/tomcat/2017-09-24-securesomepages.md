---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Secure some web pages"
teaser: "Secure your limited web pages by pushing them behind SSL. "
image:
    thumb:  message-thumb.jpg
categories:
          - tomcat
tags:
          -tomcat
          -security
related: true
---
Open your web.xml & provide your page name (jsp page ) name or use regular experssion pattern to include all pages that matches the pattern as

- Create a setenv.bat file & paste the following in Same

{% highlight xml %}
<security-constraint>
  <web-resource-collection>
      <web-resource-name>Private Pages</web-resource-name>
      <url-pattern>/app/Page1</url-pattern>
      <url-pattern>/app/Page2</url-pattern>
  </web-resource-collection>
  <user-data-constraint>
      <transport-guarantee>CONFIDENTIAL</transport-guarantee>
  </user-data-constraint>
</security-constraint>
{% endhighlight %}

The transport-guarantee value of CONFIDENTIAL makes sure that page is over SSL.
