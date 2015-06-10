---
layout: default
title: Releases
permalink: /releases/
tags: show_in_header_menu
---

{% for repository in site.github.releases %}
  * [{{ repository.name }}]({{ repository.html_url }})
	{% if repository.name contains "Dapplo.Config" %}
	* Looping!
	{% for release in repository.releases %}
    * [{{ release.name }}]({{ release.html_url }})
	{% endfor %}		
	{% endif %}
{% endfor %}

