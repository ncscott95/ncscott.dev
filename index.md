---
layout: default
title: Home
featured: "mis-steaks were made."
---

## About Me

Hello! I'm Nathan Scott, and I am a programmer and indie game developer. I am currently a student at UC San Diego studying Computer Science, and I am a Programming Lead for the school's Video Game Development Club (VGDC). 

Game development is something of a lifelong passion of mine; I've been making video games as a hobby since I first learned to program on Scratch in elementary school, slowly growing over time to make Python text adventures and Minecraft mods in middle and high school. Nowadays, most of my work is in the Unity game engine, and I consequently do most of my programming in C#. More recently, I've begun branching out into other disciplines, picking up beginner skills in Aseprite, FL Studio, and Photoshop along the way. 

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