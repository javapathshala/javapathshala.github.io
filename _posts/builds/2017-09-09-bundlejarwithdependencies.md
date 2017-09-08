---
layout: page
header:
    image_fullwidth: "cam.jpg"
breadcrumb: true
sidebar: right
title: "Maven -  Package as Jar"
teaser: "Maven script can help to package your application as JAR bundle. That's great ! But if you need to have dependencies jars package into a same jar so that you execute jar. Yes MAVEN plugins surely helps us ! "
image:
    thumb:  build-thumb.jpg
comments: true
categories:
          - builds
          - maven
tags:
          - Shade Plugin
---

There are multiple ways to achieve jar with dependencies included. But the most flexiable & extensiable is via maven plugin - Shade plugin (<em>https://maven.apache.org/plugins/maven-shade-plugin/<em>).

Shadow Plugin provides flexiabilty to even exclude jar files from final deployable bundle

Paste the below code in <build> <plugins> selection

{% highlight scss %}
<!-- Maven Shade Plugin -->
<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-shade-plugin</artifactId>
    <version>2.3</version>
    <executions>
        <!-- Run shade goal on package phase -->
        <execution>
            <phase>package</phase>
            <goals>
                <goal>shade</goal>
            </goals>
            <configuration>
                <finalName>${project.artifactId}-${project.version}</finalName>
                <artifactSet>
                    <excludes>
                        <!-- Examples-->
                        <exclude>org.slf4j:*</exclude>
                        <exclude>org.hibernate:*</exclude>
                        <exclude>org.springframework:spring-core</exclude>
                    </excludes>
                </artifactSet>                        
            </configuration>
        </execution>
    </executions>
</plugin>
{% endhighlight %}
