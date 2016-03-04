---
layout: page
title: Documentation
image:
  feature: sample-image-5.jpg
  credit: WeGraphics
  creditlink: http://wegraphics.net/downloads/free-ultimate-blurred-background-pack/
---

Dapplo blocks are building blocks for your application, here are the currently available blocks:
{% assign sorted_blocks = site.blocks | sort:"sort_id" %}
<div class="panel panel-info" >
	<div class="panel-heading">
		<h3 class="panel-title">Dapplo blocks</h3>
	</div>
	<div class="panel-body">
	  <ul>
		{% for block in sorted_blocks %}
		  <li>
			<a href="{{ block.url | prepend: site.baseurl }}">{{ block.github_project }}</a>
		  </li>
		{% endfor %}
	  </ul>
	</div>
</div>
