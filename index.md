---
layout: default
title: Home
featured: "frogolf"
---

## Featured Game

<div class="game-post-wrapper" markdown="0">
  {% assign game = site.games | where: "title", page.featured | first %}
  {% if game %}
    {% include game-list-element.html %}
  {% endif %}
</div>

## Recent Devlogs

<ul class="recent-devlogs">
  {% assign published_posts = site.posts | where_exp: "post", "post.published == true" %}
  {% for post in published_posts limit:5 %}
    <li>
      {{ post.date | date: "[%Y-%m-%d]" }} <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>