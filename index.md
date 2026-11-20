---
layout: default
title: Home
featured: "mis-steaks were made."
---

## Featured Game

<div class="game-post-wrapper" markdown="0">
  {% assign game = site.games | where: "title", page.featured | first %}
  <div class="game-heading">
    <h3>{{ game.title }}</h3>
    <p class="game-jam">{{ game.jam }}</p>
  </div>
  <div>
    <a href="{{ game.link }}" target="_blank" class="thumbnail-link">
      <img class="thumbnail" src="{{ game.image | relative_url }}">
    </a>
    <p class="img-caption">
      {{ game.caption }}
    </p>
  </div>
  {{ game.content }}
</div>

## Latest Devlogs

<ul class="recent-devlogs">
  {% assign published_posts = site.posts | where_exp: "post", "post.published == true" %}
  {% for post in published_posts limit:5 %}
    <li>
      {{ post.date | date: "[%Y-%m-%d]" }} <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>