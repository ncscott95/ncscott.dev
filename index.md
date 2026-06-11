---
layout: default
title: Home
---

## Recent Devlogs

<ul>
  {% assign published_posts = site.posts | where_exp: "post", "post.published == true" %}
  {% for post in published_posts limit:5 %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a> — {{ post.date | date: "%B %d, %Y" }}
    </li>
  {% endfor %}
</ul>