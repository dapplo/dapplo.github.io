---
layout: default
title: Releases
permalink: /releases/
tags: show_in_header_menu
---

{% for release in site.github.releases %}
* [{{ release.name }}]({{ release.html_url }})
{{ release | jsonify }}
{% endfor %}	

