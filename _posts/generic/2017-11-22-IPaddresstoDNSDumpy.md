---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Web Application -How to Map IP to DNS for Testing"
teaser: "Website or Blog on Jekyll ? It's awesome, user friendly, clean & easy to use."
categories:
          - jekyll
tags:
          - Jekyll
          - ruby
          - static website generator
---
-	Download latest ruby installer for windows - rubyinstaller-2.4.2-2-x64.ex <em>https://rubyinstaller.org/downloads/</em>
-	Run the application executable & install in C:\Ruby24-x64
-	Now we will update ruby with gems required for jekyll
-	Open command prompt & navigate to installation directory of ruby  - C:\Ruby24-x64\bin.Make sure you are connected to Internet as below commands download required gems from gems repository.
  -	Run the following commands to update gems
{% highlight ruby %}
gem install jekyll bundler
{% endhighlight %}

- create  a new jekyll site as
{% highlight ruby %}
jekyll  new mynewsite
{% endhighlight %}

- Bundle newly created website
{% highlight ruby %}
cd mynewsite
bundle exec jekyll  serve
{% endhighlight %}

-	You can access – http://localhost:4000
-	4000 is default port but site can be mapped to another port as –
{% highlight ruby %}
bundle exec jekyll serve --port 4001
{% endhighlight %}
