---
layout: default
title: Releases
permalink: /releases/
tags: show_in_header_menu
---

{% for repository in site.github.public_repositories %}
  * [{{ repository.name }}]({{ repository.html_url }})
{% endfor %}

{% for release in site.github.releases %}
  * [{{ releases.name }}]({{ releases.html_url }})
{% endfor %}