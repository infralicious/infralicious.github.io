---
layout: single
title: Blog
description: "News from Infralicious, newest first."
permalink: /blog/
toc: false
---

News from Infralicious, newest first.
We publish one short post per release.
Each post states what changed and why it matters.

{% for post in site.posts %}
## [{{ post.title }}]({{ post.url | relative_url }})

{{ post.date | date: "%B %d, %Y" }}.
{{ post.excerpt | strip_html | strip }}

{% endfor %}
