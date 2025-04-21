---
layout: default
title: All Games
---

Here are all the games available on this site.

<div class="game-list">
  {% assign sorted_games = site.games | sort: 'date' | reverse %} {% comment %} Or sort by title: site.games | sort: 'title' {% endcomment %}
  {% for game in sorted_games %}
    {% include game_listing.html game=game %}
  {% endfor %}
</div>