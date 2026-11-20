---
layout: default
title: Game Jam Projects
game_category: game-jams
permalink: /game-jams/
---

## Game Jam Projects

<div markdown="0">
    {% assign cat_games = site.games | where: "published", true | where: "category", page.game_category %}
    {% assign sorted_cat_games = cat_games | sort_natural: "title" %}
    {% for game in sorted_cat_games %}
        {% include game-list-element.html %}
    {% endfor %}
</div>