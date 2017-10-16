---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Get All Constraints from database"
teaser: "Queries mentioned below are useful in getting knowledge about all constraints in a database. This is usefull in cases where you have huge database & thus tables"
categories:
          - database
tags:
          - database
          - sql-queries
---
{% highlight sql %}
select constraint_name, table_schema, table_name
from information_schema.table_constraints
where
constraint_schema = '<your db schema>'
{% endhighlight %}
