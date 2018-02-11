---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Difference Between Forward & Reverse Proxy"
teaser: "Two co-brothers doing different works. Both doing opposite works"
categories:
          - Web
tags:
          - Web
          - Apache Web Server
          - Proxy Server
          - Load Balancer
          - HA Proxy
---
-	Most prime difference between is Reverse Proxy senses connections from outside(Internet) to your application servers where Forward Proxies filter connections going out from application servers.
- Reverse Proxies take origin connections from the internet and connect them to one server or a server farm, meaning multiple inbound connections from the internet are pooled into one or more connections to the servers - basically TCP Multiplexing.
- Reverse proxies are good for
  a. SSL Offloading
  b. Delegation to server farm
  c. Compression
  d. Load Balancing
  e. caching
  f. Single Sign On

- Forward Proxies are used to filter connections from visiting harmful sites. Best practice is when your application needs to talk to external system that only whitelist 1 IP for incoming connections rather from your server farm.

<em>Examples - Reverse Proxy</em>

{% highlight apacheconf %}
# Redirection to https
<VirtualHost *:80>
     ServerName javapathshala.com
     ServerAlias javapathshala.com
     Redirect / https://javapathshala.com/
</VirtualHost>

<VirtualHost *:443>
    ProxyTimeout 500
    ProxyPreserveHost On
    ProxyVia On

    ServerName javapathshala.com
    ServerAlias javapathshala.com

    SSLEngine on
    SSLCertificateFile /etc/pki/tls/private/jp.crt
    SSLCertificateKeyFile /etc/pki/tls/private/jp.key
    SSLCACertificateFile /etc/pki/tls/private/rootjp.cer

    ErrorLog /var/log/httpd/jp-site-error_log
    TransferLog /var/log/httpd/jp-site-access_log

    ProxyPass / http://xxx.xxx.x.xx/
    ProxyPassReverse / http://xxx.xxx.x.xx/
</VirtualHost>
{% endhighlight %}
