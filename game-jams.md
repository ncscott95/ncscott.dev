---
layout: default
title: Game Jam Projects
game_category: game-jams
permalink: /game-jams/
---

## Game Jam Projects

<div markdown="0">
{% assign cat_games = site.games | where: "published", true | where: "category", page.game_category %}
{% for game in cat_games %}
    {% include game-list-element.html %}
{% endfor %}
</div>