---
layout: page
title: Game
permalink: /game/
---

<!-- Subcategories -->
{% assign sub_slugs  = "imperium,lcg,resist"    | split: "," %}
{% assign sub_labels = "Imperium,LCGs,Resist!/Witchcraft!"   | split: "," %}

{% for slug in sub_slugs %}
  {% assign posts = site.categories[slug] %}
  <h2>{{ sub_labels[forloop.index0] }}</h2>
  {% if posts %}
    <ul class="post-list">
    {% for post in posts %}
      <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a> — <small>{{ post.date | date: "%Y-%m-%d" }}</small></li>
    {% endfor %}
    </ul>
  {% else %}
    <p>Nothing here yet.</p>
  {% endif %}
{% endfor %}
