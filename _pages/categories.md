---
layout: categories
title: Astro Blog (por temas)
permalink: /categories
image: assets/images/banners/blog.jpg
imageshadow: true
comments: false
---

Artículos para seguir el movimiento de los planetas y su influencia en nuestra vida. Suscríbete a nuestro newsletter y no te pierdas de los principales tránsitos que nos influyen entre otros temas relacionados con: Mitología, Tarot, Antroposifía, Constelaciones, entre otros.

Otras formas de navegación: <a class="text-capitalize badge badge-primary text-small" href="/blog">Astro Blog cronológico</a>



{% for category in site.categories %}
<h4 class="mt-5 mb-neg-30" id="{{ category[0] | replace: " ","-" }}"><span class="text-capitalize badge badge-primary text-small">{{ category[0] }}</span></h4>
<div class="blog-grid-container">
{% assign pages_list = category[1] %}
{% for post in pages_list %}
{% if post.title != null %}
{% if group == null or group == post.group %}
{% include postbox.html %}
{% endif %}
{% endif %}
{% endfor %}
{% assign pages_list = nil %}
{% assign group = nil %}
</div>
{% endfor %}
