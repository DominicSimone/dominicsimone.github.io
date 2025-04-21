---
layout: default # Or another base layout
title: Home
---

Welcome to my web page, my name is Dominic.

## Recent Posts

{% comment %}
Get latest 5 posts 
{% endcomment %}

{% assign recent_posts = site.posts | slice: 0, 5 %} 
{% if recent_posts.size > 0 %}
  <ul>
    {% for post in recent_posts %}
      <li>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a> - {{ post.date | date: "%B %d, %Y" }}
      </li>
    {% endfor %}
  </ul>
  <p><a href="{{ '/all-posts' | relative_url }}">See all posts...</a></p>
{% else %}
  <p>No posts yet!</p>
{% endif %}

## Recent Games

{% comment %}
Get latest games and sort by date (newest first), take 5
{% endcomment %}

{% assign recent_games = site.games | sort: 'date' | reverse | slice: 0, 5 %} 
{% if recent_games.size > 0 %}
  <div class="game-list">
    {% for game in recent_games %}
      {% include game_listing.html game=game %}
    {% endfor %}
  </div>
  <p><a href="{{ '/all-games' | relative_url }}">See all games...</a></p>
{% else %}
  <p>No games added yet!</p>
{% endif %}