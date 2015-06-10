---
layout: default
title: Releases
permalink: /releases/
tags: show_in_header_menu
---

{% for repository in site.github.public_repositories %}
		{% if repository.name contains "Dapplo.Config" %}
			{% for release in repository.releases %}
			  * [{{ release.name }}]({{ release.html_url }})
			{% endfor %}		
		{% endif %}
{% endfor %}

