---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Enable & Run Tomcat as HTTPS"
teaser: "Enable Tomcat Application server in https mode i.e access your application as https://{appname} rather than http://{appname}"
image:
    thumb:  tomcat-thumb.jpg
categories:
          - tomcat
tags:
          -tomcat
related: true
---
To enable first level security of your application deployed on tomcat, it is neccessary to run application with HTTPS protocol enabled. By default tomcat runs all applications on default protocol HTTP on port 8080. Follow the below steps to enable tomcat for HTTPS/SSL.

- First prerequisite is to Create digital certificate  ( refer javapathshala other post to - how to create digital certificate) & point tomcat to it as define below.
- Navigate to <Tomcat Home Dir>/conf/server.xml
- Turn SSL Engine ON. Look for "SSLEngine" & un-comment if commented
{% highlight xml %}
<Listener
    SSLEngine="on"
    className="org.apache.catalina.core.AprLifecycleListener"/>
{% endhighlight %}
- Comment out connector executor for non-SSL port 8080
{% highlight xml %}
<!--
<Connector executor="tomcatThreadPool"
    port="8080"
    protocol="HTTP/1.1"
    connectionTimeout="20000"
    redirectPort="8443" />
-->
{% endhighlight %}
- Define a SSL HTTP/1.1 Connector on port 443
{% highlight xml %}
<Connector
SSLEnabled="true"
URIEncoding="UTF-8"
keyAlias="tomcat"
keystoreFile="${catalina.base}/conf/.keystore"
port="443"
protocol="org.apache.coyote.http11.Http11NioProtocol"
scheme="https"
secure="true"/>

<Connector
   clientAuth="false" port="8443" minSpareThreads="5" maxSpareThreads="75"
   enableLookups="true" disableUploadTimeout="true"
   acceptCount="100" maxThreads="200"
   scheme="https" secure="true" SSLEnabled="true"
   keystoreFile="${catalina.home}/conf/Dimit.jks"
   keystoreType="JKS" keystorePass="dimit123"
   truststoreFile="${catalina.home}/conf/cacerts.jks"
   truststoreType="JKS" truststorePass="dimit123"
   SSLVerifyClient="require"
   SSLEngine="on" SSLVerifyDepth="2" sslProtocol="TLS1.2v"
/>
{% endhighlight %}

Access Tomcat as https://localhost:8443
