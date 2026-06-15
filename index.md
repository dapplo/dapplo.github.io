---
layout: page
author: robin
excerpt: "Dapplo - Open-source building blocks & modern applications for C# .NET and Windows"
tags: [dapplo, .net, blog, desktop, apps, greenshot, stripwolf]
comments: false
share: false
---

<div class="hero-section">
  <h1 class="hero-title">Dapplo</h1>
  <p class="hero-subtitle">Open-source building blocks and modern applications for C# .NET and Windows.</p>
  <div class="hero-actions">
    <a href="https://github.com/dapplo" class="btn-modern" target="_blank"><i class="fa fa-github"></i> View Dapplo on GitHub</a>
  </div>
</div>

<h2>Featured Projects</h2>
<div class="portfolio-grid">
  <!-- StripWolf Card -->
  <div class="portfolio-card">
    <div class="portfolio-card-header">
      <span class="portfolio-badge">New App</span>
      <i class="fa fa-book fa-lg" style="color: var(--accent-blue)"></i>
    </div>
    <h3>StripWolf</h3>
    <p>A modern, offline-capable comic book reader designed to interact with Komga media servers. Download comics, cache books locally, and read on the go with seamless synchronization.</p>
    <div class="portfolio-card-links">
      <a href="https://github.com/dapplo/StripWolf" class="btn-modern-outline" target="_blank"><i class="fa fa-github"></i> GitHub</a>
    </div>
  </div>
  
  <!-- Greenshot Card -->
  <div class="portfolio-card">
    <div class="portfolio-card-header">
      <span class="portfolio-badge greenshot">Open Source</span>
      <i class="fa fa-camera fa-lg" style="color: var(--accent-pink)"></i>
    </div>
    <h3>Greenshot</h3>
    <p>The highly popular, lightweight screenshot utility for Microsoft Windows. Robin Krom is one of the lead developers, refactoring and publishing verified versions to millions of users.</p>
    <div class="portfolio-card-links">
      <a href="https://getgreenshot.org" class="btn-modern-outline" target="_blank"><i class="fa fa-globe"></i> Website</a>
      <a href="https://github.com/greenshot/greenshot" class="btn-modern-outline" target="_blank"><i class="fa fa-github"></i> GitHub</a>
    </div>
  </div>
</div>

<div class="dapplo-blocks-section">
  <h2>Dapplo .NET Building Blocks</h2>
  <p>A collection of robust, reactive, and reusable libraries built to accelerate desktop application development in C# and .NET.</p>
  
  <div class="blocks-grid">
    {% assign sorted_blocks = site.blocks | sort:"sort_id" %}
    {% for block in sorted_blocks %}
    <div class="block-card">
      <h4>{{ block.github_project }}</h4>
      <p>{{ block.content | strip_html | strip_newlines | truncate: 120 }}</p>
      <a href="https://github.com/dapplo/{{ block.github_project }}" class="block-card-link" target="_blank">View GitHub Repository <i class="fa fa-arrow-right"></i></a>
    </div>
    {% endfor %}
  </div>
</div>