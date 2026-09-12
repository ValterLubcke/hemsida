---
title: Tidigare projekt
layout: rest
description: Tidigare arbeten.
type: parent
order: 3
---

<div class="section main">
	<div class="container">
		{% assign mypages = site.pages | where: "type", "projekt" %}
		{% for page in mypages %}
		<a class="button" href="{{ page.url | relative_url }}">{{ page.title }}</a>
		{% endfor %}
	</div>
</div>