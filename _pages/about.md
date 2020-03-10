---
permalink: /about/
title: "About"
excerpt: "Minimal Mistakes is a flexible two-column Jekyll theme."
layouts_gallery:
  #- url: /assets/images/mm-layout-splash.png
  #  image_path: /assets/images/mm-layout-splash.png
  #  alt: "splash layout example"
last_modified_at: 2019-08-27T15:46:43-04:00
toc: true
---

{% assign postsByYear = site.posts | group_by_exp:"post", "post.date | date: '%Y'"  %}
{% for year in postsByYear %}
  <h2 id="{{ year.name | slugify }}" class="archive__subtitle">{{ year.name }}</h2>
  {% for post in year.items %}
    {% include archive-single.html %}
  {% endfor %}
{% endfor %}