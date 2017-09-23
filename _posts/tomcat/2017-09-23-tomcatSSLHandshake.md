---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Tomcat SSL Handshake"
teaser: "Requirement is to restrict application deployed in tomcat container to access all public certificates & make SSL handshake with only organisation provided certificate."
image:
    thumb:  tomcathandshake-thumb.jpg
categories:
          - tomcat
tags:
          -tomcat
related: true
---
By default all Trusted Certificate Authorities are stored is a Java keystore file [cacerts] placed at {% highlight java %} <Java Installation Path>\jdk1.<version>/jre/lib/security/cacerts{% endhighlight %} containing all trusted SSL certificate issued by Certificate Authority & web application deployed on tomcat can access all external web services (SOAP or REST) (https) or applications.

Requirement is to restrict tomcat to use only organisation specific certificates. To achieve the business case, we need to override the cacert file. To do this, need to create a new file that contains only required trusted certificate. Place the newly created file at  {% highlight java %}${CATALINA_BASE}/conf/cacerts{% endhighlight %}. This file contains no enteries to start off.

Once above is done, application deployed on tomcat will start throwing SSLHandshakeException for all other certificate (if application is using those) that are not listed in cacerts.

Exception seen is
<blockquote>
javax.net.ssl.SSLHandshakeException:sun.security.validator.ValidatorException:PKIX path building failed:           sun.security.provider.certpath.SunCertPathBuilderException:unable to find valid certification path to requested target
</blockquote>

For doing above first we need to first download the trusted certificate from browser in .cer format

##### To trust a new Certificate Authority:
- View the certificate presented by the server
- Find the Certificate Authority that issued the certificate
- Download the certificate of the Certificate Authority that issued the certificate
- Import the Certificate Authority's certificate in to the trusted list as test.cer

##### Steps to add certificate to the trusted list
- Open Command prompt (cmd) in administrative mode
- Navigate to <Tomcat Installation>/conf
- Check the current certificates numbers in trusted list (if any, may be you are doing for first time, so skip his step) by running command
{% highlight java %}
keytool -list -keystore cacerts > d:\beforecerts.txt
{% endhighlight %}
- open beforecerts.txt & see of number of imported certificates - Your keystore contains n entries
- Issue the following command to import the certificate test.cer
{% highlight java %}
keytool -import -trustcacerts -alias <aliasname> -file <location>\test.cer -keystore cacerts
{% endhighlight %}
- Check again current certificates numbers in trusted list
{% highlight java %}
keytool -list -keystore cacerts > d:\aftercerts.txtopen aftercerts.txt
{% endhighlight %}
- open aftercerts.txt & number of imported certificates - It should be incremented by 1

Now try to hit an external application that uses certificate that is not trusted by your tomcat & vica versa.
