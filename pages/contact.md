---
layout: page
sidebar: right
title: "Contact"
meta_title: "Contact and use our contact form"
subheadline: "Contact "
teaser: "Get in touch with me? Use Social Media channel."
permalink: "/contact/"
---
If you need to contact me for paid journals on various topic, email me to get my whatspps channel.

<ul class="inline-list social-icons">
{% for social_item in site.data.socialmedia %}
  <li><a href="{{ social_item.url }}" target="_blank" class="{{ social_item.class }}" title="{{ social_item.title }}"></a></li>
{% endfor %}
</ul>
