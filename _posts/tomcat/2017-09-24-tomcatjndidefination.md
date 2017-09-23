---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Define JNDI Name in Tomcat"
teaser: "Define JNDI name to enble database connection via tomcat configurations"
image:
    thumb:  tomcat-thumb.jpg
categories:
          - tomcat
tags:
          -tomcat
related: true
---
You can enable connection to database using tomcat configurations. Define JNDI settings in tomcat server.xml for connecting any database type. Follow the steps below

- Modify <Tomcat Install>/conf/context.xml.  Include the following JNDI names  
{% highlight xml %}
<ResourceLink global="jdbc/{name1}" name="jdbc/{name2}" />
{% endhighlight %}
- Modify <Tomcat Install>/conf/server.xml. Find <GlobalNamingResources> and add the new resource
{% highlight xml %}
 <Resource
    auth="Container"
    logAbandoned="true"
    maxIdle="-1"
    maxWait="10000"
    removeAbandoned="true"
    validationQuery="SELECT CURRENT_TIMESTAMP"
    driverClassName="com.mysql.jdbc.Driver"
    name="jdbc/{name1}"
    password="*****" username="abc"
    url="jdbc:mysql://localhost/dbaname" />
{% endhighlight %}
- If your application uses Hibernate , Use the JNDI name in .cfg.xml as
{% highlight xml %}
<property name="connection.datasource">
  java:/comp/env/jdbc/{name2}
</property>
{% endhighlight %}
