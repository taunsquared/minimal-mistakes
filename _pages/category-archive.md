---
layout: archive
permalink: /scribbles/categories/
title: "scribbles"
author_profile: true
---

Bits of this and that. 

{% include group-by-array collection=site.posts field="categories" %}

{% for category in group_names %}
  {% assign posts = group_items[forloop.index0] %}
  <h2 id="{{ category | slugify }}" class="archive__subtitle">{{ category }}</h2>
  <div class="grid__wrapper">
    {% for post in posts %}
      {% include archive-single.html type="grid" %}
    {% endfor %}
  </div>
{% endfor %}
