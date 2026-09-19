---
layout: page
title: Game
permalink: /game/
---

<ul class="post-list">
{% for post in site.categories.game %}
  <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a> — <small>{{ post.date | date: "%Y-%m-%d" }}</small></li>
{% endfor %}
</ul>

{% unless site.categories.game %}Nothing here yet.{% endunless %}
