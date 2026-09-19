---
layout: page
title: Q-project
permalink: /q-project/
---

{% assign sub_slugs  = "imperium,lcg"    | split: "," %}
{% assign sub_labels = "Imperium,LCGs"   | split: "," %}

<ul class="post-list">
{% for post in site.categories['q-project'] %}
  <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a> — <small>{{ post.date | date: "%Y-%m-%d" }}</small></li>
{% endfor %}
</ul>

{% unless site.categories['q-project'] %}Nothing here yet.{% endunless %}
