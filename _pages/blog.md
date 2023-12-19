---
layout: page
title: Astro Blog
permalink: /blog
---

Artículos para seguir el movimiento de los planetas y su influencia en nuestra vida. Suscríbete a nuestro newsletter y no te pierdas de los principales tránsitos que nos influyen entre otros temas relacionados con: Mitología, Tarot, Antroposifía, Constelaciones, entre otros.

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
