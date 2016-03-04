---
layout: post
title:  "New block and deployment to NuGet"
excerpt: "Continuous integration to the rescue"
modified: 2015-03-01
tags: [post]
comments: true
image:
  feature: sample-image-5.jpg
  credit: WeGraphics
  creditlink: http://wegraphics.net/downloads/free-ultimate-blurred-background-pack/
---

As Greenshot needed updates to the way it was connecting to Jira and Confluence, I wrote a new block: [Dapplo.JsonRest]({% post_url 2015-03-01-blocks-on-nuget %})
And thanks to the great Continuous Integration system [AppVeyor](http://www.appveyor.com/), it was very easy to automate deployment to NuGet.
