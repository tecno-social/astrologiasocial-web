---
layout: page
title: Astro Blog
permalink: /blog
image: assets/images/banners/blog.jpg
imageshadow: true
comments: false
---

Artículos para seguir el movimiento de los planetas y su influencia en nuestra vida. Suscríbete a nuestro newsletter y no te pierdas de los principales tránsitos que nos influyen entre otros temas relacionados con: Mitología, Tarot, Antroposifía, Constelaciones, entre otros.


<div id="categories">
Navegar por temas:
{% for category in site.categories %}
<a class="text-capitalize badge badge-primary text-small" href="{{site.baseurl}}/categories#{{ category[0] | replace: " ","-" }}">{{ category[0] }}</a>
{% endfor %}
</div>
<!-- <a class="smoothscroll badge badge-primary text-capitalize" href="{{site.baseurl}}/tags#{{ tag | replace: " ","-" }}">{{ tag }}</a> -->


<!-- Posts Index
================================================== -->
<div class="blog-grid-container">
    {% for post in site.posts %}
        {% include postbox.html %}
    {% endfor %}
</div>

<!-- Pagination
================================================== -->
<div class="bottompagination">
<span class="navigation" role="navigation">
    {% include pagination.html %}
</span>
</div>
