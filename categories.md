---
layout: page
title: Categories
permalink: /categories/
---

<div class="categories">
{% assign sorted_categories = site.categories | sort %}
{% for category in sorted_categories %}
  <h2 id="{{ category[0] | slugify }}">{{ category[0] }}</h2>
  <ul>
    {% for post in category[1] %}
      <li>
        <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span> — 
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </li>
    {% endfor %}
  </ul>
{% endfor %}
</div>
