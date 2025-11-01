---
layout: page
title: Categories
permalink: /categories/
---

Browse posts by category:

{% for category in site.categories %}

- [{{ category[0] }}]({{ site.baseurl }}/categories/{{ category[0] | slugify }}/) ({{ category[1].size }} posts)
  {% endfor %}
