---
layout: default
title: Releases
permalink: /releases/
tags: show_in_header_menu
---

{% for project_release in site.github.releases %}
* [{{ project_release.name }}]({{ project_release.html_url }})
{% endfor %}	

