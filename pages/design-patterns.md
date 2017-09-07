---
layout: page
breadcrumb: true
sidebar: right
title: "All Design Patterns Wisdoms!"
subheadline: ""
teaser: "Check out all blog posts for <em>Design Patterns</em>. Click on a headline to read the teaser."
header:
   image_fullwidth: "cam.jpg"
permalink: "/architectures/design-patterns/"
---
<div id="blog-index" class="row">
	<div class="small-12 columns t30">
		<dl class="accordion" data-accordion>
			{% assign counter = 1 %}
			{% for post in site.categories.design-patterns limit:1000 %}
			<dd class="accordion-navigation">
			<a href="#panel{{ counter }}"><span class="iconfont"></span> {% if post.subheadline %}{{ post.subheadline }} › {% endif %}<strong>{{ post.title }}</strong></a>
				<div id="panel{{ counter }}" class="content">
					{% if post.meta_description %}{{ post.meta_description | strip_html | escape }}{% elsif post.teaser %}{{ post.teaser | strip_html | escape }}{% endif %}
					<a href="{{ site.url }}{{ site.baseurl }}{{ post.url }}" title="Read {{ post.title | escape_once }}"><strong>{{ site.data.language.read_more }}</strong></a><br><br>
				</div>
			</dd>
			{% assign counter=counter | plus:1 %}
			{% endfor %}
		</dl>
	</div><!-- /.small-12.columns -->
</div><!-- /.row -->
