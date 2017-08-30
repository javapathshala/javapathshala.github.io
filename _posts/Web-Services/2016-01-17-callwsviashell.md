---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Call REST Web Service using Shell Script"
teaser: "Yes ! It's true. You can invoke or consume or call a Web Service from inside a Linux/Unix shell script. This is same as doing from java or php or .net client. Actually most simple to call or invoke a web service is through shell scripting."
categories:
    - web-services
---
Let's consider a REST web service that adds two numbers. Also you need to pass a token (string or numeric) as a parameter (consider this as a example - do not think over it as a functionality )

##### Web Service
{% highlight scss %}http://<Host Name>/jp-addws/svc/rs/Add/numbers/$num1/$num2{% endhighlight %}

##### Parameters - token & userid Request
{% highlight scss %}http://<Host Name>/jp-addws/svc/rs/Add/numbers/10/20?token=123&userid=789{% endhighlight %}

##### Shell Script
{% highlight scss %}
echo "Invoking Addition service to add two numbers";
num1=10
num2=20
result=
result=$(curl -X GET -i -H
        "Accept: application/json" -H
        "Content-Type: application/xml"
        -d "token=123&userid=789"
        http://<Host Name>/jp-addws/svc/rs/Add/numbers/$num1/$num2)
echo "###############"
echo "Got response from Phone service"
echo $result
exit
{% endhighlight %}
