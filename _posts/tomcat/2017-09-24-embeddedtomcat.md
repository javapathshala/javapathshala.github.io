---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Web Application with Embedded Tomcat... Run as Jar"
teaser: "this post describes a process of running Web application through Jar File. Yes you heard right"
image:
    thumb:  tomcatjar-thumb.jpg
categories:
          - tomcat
tags:
          -tomcat
related: true
---
As you all know we require a application server to run a web app but what if you are delivering to a client who does not have any knowledge to setting up servers & deploying applications & from your (vendor) prospective, you do not want to get into all mess again & again for different clients (Setting up again & again).

Best way to get rid of *setting up again & again* is to embed application server within web app & deliver as JAR file to client. Client just have to run the jar or make it executable.  

Follow the below process to achieve the target
- Create a maven project (web app) with packaging as WAR.
- Do what ever you want to design or display in your webapp (should have Web.xml :) )
- Modify the pom to create a  jar file with war file. Include the shown plugin in <build> </build> as
{% highlight xml %}
<build>
  <plugins>
    <plugin>
      <groupId>org.apache.tomcat.maven</groupId>
      <artifactId>tomcat7-maven-plugin</artifactId>
      <version>2.1</version>
      <executions>
        <execution>
          <id>tomcat-run</id>
          <goals>
            <goal>exec-war-only</goal>
          </goals>
          <phase>package</phase>
          <configuration>
            <path>/jp-embed-tomcat</path>
            <attachArtifactClassifier>
              exec-war
            </attachArtifactClassifier>
            <attachArtifactClassifierType>
              jar
            </attachArtifactClassifierType>
            <finalName>test.jar</finalName>
            <charset>utf-8</charset>
            <update>true</update>
          </configuration>
        </execution>
      </executions>
    </plugin>
  </plugins>
</build>
{% endhighlight %}

Note above plugin itself embed Tomcat version 7.0.30. Please do not use version 2.2 of plugin as it has some defects & jar won't work. Also this plugin does not work with Tomcat 8 but i am looking into reasons & solutions. May be version 2.3 of plugin accepts Tomcat 8.

Now run the jar as  
{% highlight java %}
 java -jar test.jar
{% endhighlight %}

this will start the application & you can access the web app through browser

So we achieve running a web application without implicitly installing  tomcat server.
