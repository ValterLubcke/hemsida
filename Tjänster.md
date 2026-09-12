---
title: Tjänster
layout: rest
description: Vanliga paket på tjänster vi erbjuder!
type: parent
order: 3
---

<div class="section main">
	<div class="container">
		{% assign mypages = site.pages | where: "type", "projekt 2" %}
		{% for page in mypages %}
		<a class="button" href="{{ page.url | relative_url }}">{{ page.title }}</a>
		{% endfor %}
	</div>
</div>