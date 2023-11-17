---
layout: page
permalink: /archive
title: Archive of All Posts
---

<!-- {% for collection in site.collections %}
{% if collection.label != "pages" %}

  <h2>Entries from {{ collection.label | capitalize }}</h2>
  <ul>
    {% for item in site[collection.label] %}
      <li class="archive-links"><a href="{{ item.url }}">{{ item.title }}</a></li>
    {% endfor %}
  </ul>
  {% endif %}
{% endfor %} -->
<div class="pure-u-1 tags">
  {% for post in site.posts %}
    {% assign cur_year = post.date | date: '%Y' %}

    {% if cur_year != last_year %}
      {% unless forloop.first %}</ul>{% endunless %}

      <h3><time class="year lead d-block">{{ cur_year }}</time></h3>
      {{ '<ul class="list-unstyled">' }}

      {% assign last_year = cur_year %}
    {% endif %}

    <li class="archive-links">
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>

    {% if forloop.last %}</ul>{% endif %}
  {% endfor %}
</div>