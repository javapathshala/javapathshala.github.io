---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Install Jenkins on Red Hat Linux"
teaser: "This post describes how to install Jenkins & supporting plugins to a Linux (Red Hat) system. Follow the below steps in sequence"
categories:
          - generic
tags:
          - generic
          - Jenkins
          - Continuous Integration
---
1. Download java using the following command
{% highlight shell %}
curl -v -j -k -L -H "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u151-b12/e758a0de34e24606bca991d704f6dcbf/jdk-8u151-linux-x64.rpm > jdk-8u151-linux-x64.rpm
{% endhighlight %}
You can change the version of java of your choice

2. Install java
{% highlight shell %}
sudo rpm -i jdk-8u151-linux-x64.rpm
{% endhighlight %}
it will get installed in /usr/java/jdk1.8.0_151/

3. Before installing Jenkins, create the following folders
{% highlight shell %}
/var/log/jenkins
/var/lib/jenkins
/var/cache/jenkins.
/etc/sysconfig/jenkins
{% endhighlight %}

3. Install Jenkins - You use the above process as for java - that is downloading using curl command & then installing rpm. Other way around is to use below commands (internally it does the same)

a. Add the Jenkins repository to the yum repos
{% highlight shell %}
sudo wget -O /etc/yum.repos.d/jenkins.repo http://pkg.jenkins-ci.org/redhat/jenkins.repo
{% endhighlight %}

b. add key
{% highlight shell %}
sudo rpm --import https://jenkins-ci.org/redhat/jenkins-ci.org.key
{% endhighlight %}

c. Install Jenkins
{% highlight shell %}
sudo yum install jenkins
{% endhighlight %}

4. Starting/Stopping Jenkins Service
{% highlight shell %}
sudo service jenkins start
sudo service jenkins stop
sudo service jenkins restart
{% endhighlight %}

5. Installation of supporting plugins - ANT
	1. Download Apache Ant from http://ant.apache.org/bindownload.cgi - apache-ant-1.10.1.tar.gz
	2. Extract the tar file in /usr/ant/apache-ant-1.10.1/
	3. Set the ANT_OPTS environment variable: export ANT_OPTS="-Xmx256M"
	4. Set the ANT_HOME environment variable to the directory where you installed Ant: export ANT_HOME=${ant_dir}.
	5. Set the PATH environment variable to include the directory where you installed the Ant bin directory: export PATH=${ANT_HOME}/bin:${JAVA_HOME}/bin:${PATH}

Above is required only if your project uses ANT for build script.

Access the Jenkins - http://localhost:8080
For login for first time, you need to know the admin password. This is present in file -
{% highlight shell %}
/var/lib/jenkins/secrets/initialAdminPassword
{% endhighlight %}

Once you login as admin , go ahead to create more users.

Happy JobBING
