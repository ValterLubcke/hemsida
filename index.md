---
title: hem
layout: hem
type: parent
order: 1
---

<div class="section header">
	<div class="container">
		<img class="main-logo" src="{{ "/assets/img/logo.svg" | relative_url }}">
		<h3 class="section-heading">Spara livets viktigaste stunder</h3>
		<p class="section-description">
			Trivs bäst med kameran där det händer saker.<br>
			Sport, event och andra tillfällen där människor skapar minnen tillsamans.
		</p>
		<div id="navbar-wrapper">
<div id="navbar">
<img id="brand" class="hide" src="{{ "/assets/img/logo.svg" | relative_url }}">
                {% assign current_url = page.url %}
                {% assign mypages = site.pages | where: "type", "parent" | sort: "order" %}
                {% for page in mypages %}
<a class="button{% if page.url == current_url %} active{% endif %}" href="{{ page.url | relative_url }}">{{ page.title }}</a>
                {% endfor %}
</div>
</div>
	</div>
</div>

<div class="section main">
	<div class="container">
		<div class="row" id="gallery">
		{% assign coll = site.collections | where: "label", "hem" | first %}
		{% assign list = coll.files | sort: "basename" %}
		{% assign l = coll.files.size | divided_by: 3 | ceil %}
		<div class="one-third column">
			{% for image in list limit: l %}
			<article class="thumb">
				<img class="lozad u-max-full-width" data-src="{{ coll.label | append: '/' | append: image.name }}" alt="{{ image.basename }}" />
			</article>
			{% endfor %}
		</div>
		<div class="one-third column">
			{% for image in list offset: l limit: l %}
			<article class="thumb">
				<img class="lozad u-max-full-width" data-src="{{ coll.label | append: '/' | append: image.name }}" alt="{{ image.basename }}" />
			</article>
			{% endfor %}
		</div>
		<div class="one-third column">
			{% assign l2 = l | times: 2 %}
			{% for image in list offset: l2 %}
			<article class="thumb">
				<img class="lozad u-max-full-width" data-src="{{ coll.label | append: '/' | append: image.name }}" alt="{{ image.basename }}" />
			</article>
			{% endfor %}
		</div>
	</div>
	</div>
</div>