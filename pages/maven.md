---
layout: page
breadcrumb: true
sidebar: right
title: "All Design Patterns Wisdoms!"
subheadline: ""
teaser: "Check out all blog posts for <em>Design Pattens</em>. Click on a headline to read the teaser."
header:
   image_fullwidth: "cam.jpg"
permalink: "/builds/maven/"
---
{% for post in site.categories.maven limit:1000 %}
  {% include  _categoriesposts.html %}
{% endfor %}
